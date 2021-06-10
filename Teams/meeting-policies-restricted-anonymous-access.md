---
title: Удаление политики собраний Teams RestrictedAnonymousAccess для пользователей
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: cebulnes, anyada
audience: admin
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords: ''
ms.custom: ''
description: Узнайте, как удалить политику restrictedAnonymousAccess Teams собраний для пользователей в организации.
ms.openlocfilehash: aab4b524ee0c9ab5cab3244a0897730fea0361a7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121347"
---
# <a name="remove-the-restrictedanonymousaccess-teams-meeting-policy-from-users"></a>Удаление политики собраний Teams RestrictedAnonymousAccess для пользователей

[Политики собраний](meeting-policies-in-teams.md) в Microsoft Teams используются для управления функциями, доступными участникам собрания для собраний, запланированных пользователями в организации. 

Teams включает встроенную политику RestrictedAnonymousAccess, которая содержит предопределяющие параметры, которые включают ограничение анонимных пользователей начинать собрания. (Анонимные пользователи — это пользователи, которые не были авторификацией.) Администраторы не могут изменять или изменять предопределяйте параметры в политике собраний.

В этой статье показано, как с помощью PowerShell удалить политику собраний RestrictedAnonymousAccess для пользователей, которым назначена эта политика. Дополнительные сведения об управлении Teams помощью PowerShell см. в Teams [PowerShell.](teams-powershell-overview.md)

## <a name="before-you-start"></a>Перед началом работы

Установите и подключите модуль [Skype для бизнеса PowerShell.](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell) Пошаговую инструкцию см. в [Microsoft Teams PowerShell.](teams-powershell-install.md)

## <a name="get-the-teams-meeting-policy-assignments-for-your-organization"></a>Получите Teams по назначениям политики собраний для вашей организации

Чтобы получить назначения политик Teams собраний для организации, следуйте следующим советам:

```powershell
Get-CsOnlineUser | Select-Object objectid, TeamsMeetingPolicy | Group-Object TeamsMeetingPolicy
```

В этом примере возвращается следующий результат, который показывает, что политика собраний RestrictedAnonymousAccess назначена двум пользователям.

```console
Count  Name                               Group
------ ----------                         ---------
233    Education_HigherEducationStudent   {@{ObjectId=755e0d21-0737-4219-b68a-23423497f61f; TeamsMeetingPolicy=Education_HigherEducationStudent...
20                                        {@{ObjectId=e27fdfb5-bb38-4032-bb33-8e8bdf086eff; TeamsMeetingPolicy=}, @{ObjectId=91c330...
2      RestrictedAnonymousAccess          {@{ObjectId=38b35ebf-cc8b-4b61-a2db-f6e67c3f614b; TeamsMeetingPolicy=RestrictedAnonymousAccess...
```

## <a name="unassign-the-restrictedanonymous-meeting-policy-from-users"></a>Отогнание от пользователей политики собраний RestrictedAnonymous

Чтобы удалить политику собраний RestrictedAnonymous для пользователей, используйте для этого cmdlet [Grant-CSTeamsMeetingPolicy,](/powershell/module/skype/grant-csteamsmeetingpolicy) если пользователей мало (например, менее 100). Если у вас много пользователей (например, более 100), эффективнее использовать для отправки пакетной операции [новый-CsBatchPolicyAssignmentOperation.](/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps)

### <a name="use-the-grant-csteamsmeeting-policy-cmdlet"></a>Использование Grant-CsTeamsMeeting политики

Чтобы удалить политику собраний RestrictedAnonymous для пользователей, запустите следующую:

```powershell
Get-CsOnlineUser |? TeamsMeetingPolicy -eq "RestrictedAnonymousAccess" | Select-Object objectid | foreach {Grant-CsTeamsMeetingPolicy -Identity $_.ObjectId -PolicyName $null}
```

### <a name="use-the-new-csbatchpolicyassignmentoperation-cmdlet"></a>Использование New-CsBatchPolicyAssignmentOperation управления

При [назначении пакетной](assign-policies.md#assign-a-policy-to-a-batch-of-users)политики максимальное количество пользователей, для которых можно удалить или обновить политики, составляет 5000 за один раз. Например, если у вас более 5000 пользователей, необходимо отправить несколько пакетов. Для лучших результатов не от отправки нескольких пакетов за один раз. Разрешить обработку пакетов перед отправкой дополнительных пакетов.

> [!NOTE]
> Командлет [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) находится в Teams PowerShell. Прежде чем выполнять эти действия, установите модуль [PowerShell и подключите его к Teams PowerShell.](https://www.powershellgallery.com/packages/MicrosoftTeams) Пошаговую инструкцию см. в [Microsoft Teams PowerShell.](teams-powershell-install.md)

Чтобы удалить политику собраний RestrictedAnonymousAccess для пакета пользователей, следуя следующим командам:

```powershell
$restrictedAnonymousUsers = @(Get-CsOnlineUser |? TeamsMeetingPolicy -eq "RestrictedAnonymousAccess" | %{ $_.ObjectId })
```

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $restrictedAnonymousUsers -OperationName "Batch unassign meeting policy"
```

#### <a name="get-the-status-of-the-batch-assignment"></a>Получить состояние назначения пакета

Каждое пакетное задание возвращает номер операции, который можно использовать для отслеживания хода выполнения и состояния заданий, а также выявления сбоев, которые могут возникнуть. Например, запустите следующую:

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 62557b78-e734-42d6-952f-41a454ed6115
```

Убедитесь, **что значение ErrorCount** **— 0** (ноль) и **OverallStatus** **— Завершено.**

## <a name="related-topics"></a>Статьи по теме

- [Управление политиками собраний в Teams](meeting-policies-in-teams.md)
- [Обзор PowerShell в Teams](teams-powershell-overview.md)
- [Назначение политик пользователям в Teams](assign-policies.md)