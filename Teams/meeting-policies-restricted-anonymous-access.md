---
title: Удаление политики собраний Teams RestrictedAnonymousAccess для пользователей
ms.author: mabond
author: mkbond007
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: cebulnes, anyada
audience: admin
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords: ''
ms.custom: ''
description: Узнайте, как удалить политику собраний RestrictedAnonymousAccess Teams у пользователей в организации.
ms.openlocfilehash: e5ea203e52ca1b81ed7ce37f31c9f8cb5900c131
ms.sourcegitcommit: 472e46b6eb907f41920516616683a61f0fc6f741
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/30/2022
ms.locfileid: "66564107"
---
# <a name="remove-the-restrictedanonymousaccess-teams-meeting-policy-from-users"></a>Удаление политики собраний Teams RestrictedAnonymousAccess для пользователей

[Политики собраний](meeting-policies-overview.md) в Microsoft Teams используются для управления функциями, доступными участникам собраний для собраний, запланированных пользователями в организации. 

Teams включает встроенную политику с именем RestrictedAnonymousAccess, которая содержит предварительно определенные параметры, включающие ограничение анонимных пользователей от начала собрания. (Анонимные пользователи — это пользователи, которые не были прошедшие проверку подлинности.) Администраторы не могут изменять предопределенные параметры в политике собраний.

В этой статье показано, как с помощью PowerShell удалить политику собраний RestrictedAnonymousAccess у пользователей, которым назначена эта политика. Дополнительные сведения об управлении Teams с помощью PowerShell см. в [обзоре Teams PowerShell](teams-powershell-overview.md).

## <a name="before-you-start"></a>Перед началом работы

Установите и подключитесь к Skype для бизнеса [PowerShell](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell). Пошаговые инструкции см. в статье ["Установка Microsoft Teams PowerShell"](teams-powershell-install.md).

## <a name="get-the-teams-meeting-policy-assignments-for-your-organization"></a>Получение назначений политик собраний Teams для вашей организации

Выполните следующую команду, чтобы получить назначения политики собраний Teams для вашей организации.

```powershell
Get-CsOnlineUser | Select-Object objectid, TeamsMeetingPolicy | Group-Object TeamsMeetingPolicy
```

В этом примере возвращаются следующие выходные данные, которые показывают, что двум пользователям назначена политика собрания RestrictedAnonymousAccess.

```console
Count  Name                               Group
------ ----------                         ---------
233    Education_HigherEducationStudent   {@{ObjectId=755e0d21-0737-4219-b68a-23423497f61f; TeamsMeetingPolicy=Education_HigherEducationStudent...
20                                        {@{ObjectId=e27fdfb5-bb38-4032-bb33-8e8bdf086eff; TeamsMeetingPolicy=}, @{ObjectId=91c330...
2      RestrictedAnonymousAccess          {@{ObjectId=38b35ebf-cc8b-4b61-a2db-f6e67c3f614b; TeamsMeetingPolicy=RestrictedAnonymousAccess...
```

## <a name="unassign-the-restrictedanonymous-meeting-policy-from-users"></a>Отмена назначения политики собраний RestrictedAnonymous пользователям

Чтобы удалить политику собраний RestrictedAnonymous с пользователей, можно использовать командлет [Grant-CSTeamsMeetingPolicy](/powershell/module/skype/grant-csteamsmeetingpolicy) , если у вас небольшое количество пользователей (например, менее 100 пользователей). При наличии большого количества пользователей (например, более 100 пользователей) эффективнее использовать командлет  [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) для отправки пакетной операции.

### <a name="use-the-grant-csteamsmeeting-policy-cmdlet"></a>Использование командлета Grant-CsTeamsMeeting политики

Выполните следующую команду, чтобы удалить из пользователей политику собраний RestrictedAnonymous.

```powershell
Get-CsOnlineUser |? TeamsMeetingPolicy -eq "RestrictedAnonymousAccess" | Select-Object objectid | foreach {Grant-CsTeamsMeetingPolicy -Identity $_.ObjectId -PolicyName $null}
```

### <a name="use-the-new-csbatchpolicyassignmentoperation-cmdlet"></a>Использование New-CsBatchPolicyAssignmentOperation командлета

При [назначении пакетной](assign-policies-users-and-groups.md#assign-a-policy-to-a-batch-of-users) политики максимальное число пользователей, для которых можно удалить или обновить политики, составляет 5000 за раз. Например, если у вас более 5000 пользователей, необходимо отправить несколько пакетов. Для достижения наилучших результатов не следует отправлять несколько пакетов одновременно. Разрешить пакетам завершать обработку перед отправкой дополнительных пакетов.

> [!NOTE]
> [Командлет New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) находится в модуле Teams PowerShell. Прежде чем выполнить эти действия, установите модуль [Teams PowerShell и подключитесь к его подключению](https://www.powershellgallery.com/packages/MicrosoftTeams). Пошаговые инструкции см. в статье ["Установка Microsoft Teams PowerShell"](teams-powershell-install.md).

Выполните следующие команды, чтобы удалить политику собраний RestrictedAnonymousAccess из пакета пользователей.

```powershell
$restrictedAnonymousUsers = @(Get-CsOnlineUser |? TeamsMeetingPolicy -eq "RestrictedAnonymousAccess" | %{ $_.ObjectId })
```

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $restrictedAnonymousUsers -OperationName "Batch unassign meeting policy"
```

#### <a name="get-the-status-of-the-batch-assignment"></a>Получение состояния пакетного назначения

Каждое пакетное назначение возвращает идентификатор операции, который можно использовать для отслеживания хода выполнения и состояния назначений и выявления любых сбоев, которые могут произойти. Например, выполните следующую команду:

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 62557b78-e734-42d6-952f-41a454ed6115
```

Убедитесь, **что значение ErrorCount** **равно 0** (ноль), **а OverallStatus —** **Завершено**.

## <a name="related-topics"></a>Статьи по теме

- [Управление политиками собраний в Teams](meeting-policies-overview.md)
- [Обзор PowerShell в Teams](teams-powershell-overview.md)
- [Назначение политик пользователям в Teams](policy-assignment-overview.md)