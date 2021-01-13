---
title: Удаление политики собраний RestrictedAnonymousAccess Teams для пользователей
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
description: Узнайте, как удалить политику собраний RestrictedAnonymousAccess Teams для пользователей в вашей организации.
ms.openlocfilehash: 55385cdd47f6b6c9882f8d4e8dcadc848f13755d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806259"
---
# <a name="remove-the-restrictedanonymousaccess-teams-meeting-policy-from-users"></a>Удаление политики собраний RestrictedAnonymousAccess Teams для пользователей

[Политики собраний](meeting-policies-in-teams.md) в Microsoft Teams используются для контроля функций, доступных участникам собрания для собраний, запланированных пользователями в вашей организации. 

В Teams есть встроенная политика RestrictedAnonymousAccess, которая содержит предопределяющие параметры, которые ограничивают возможность начинать собрания для анонимных пользователей. (Анонимные пользователи — это пользователи, которые не были аутентификацией.) Администраторы не могут изменять или изменять заранее задав параметры в политике собраний.

В этой статье показано, как с помощью PowerShell удалить политику собраний RestrictedAnonymousAccess для пользователей, которым назначена эта политика. Дополнительные сведения об управлении Teams с помощью PowerShell см. в обзоре [Teams PowerShell.](teams-powershell-overview.md)

## <a name="before-you-start"></a>Перед началом работы

Установите модуль Skype для бизнеса [PowerShell и подключите его.](https://www.microsoft.com/download/details.aspx?id=39366) Пошаговую инструкцию см. в [руководстве по установке Microsoft Teams PowerShell.](teams-powershell-install.md)

## <a name="get-the-teams-meeting-policy-assignments-for-your-organization"></a>Получите назначения политики собраний Teams для вашей организации

Чтобы получить задания политики собраний Teams для вашей организации, запустите следующую команду:

```powershell
Get-CsOnlineUser | Select-Object objectid, TeamsMeetingPolicy | Group-Object TeamsMeetingPolicy
```

В этом примере возвращается следующий результат, который показывает, что двум пользователям назначена политика собрания RestrictedAnonymousAccess.

```console
Count  Name                               Group
------ ----------                         ---------
233    Education_HigherEducationStudent   {@{ObjectId=755e0d21-0737-4219-b68a-23423497f61f; TeamsMeetingPolicy=Education_HigherEducationStudent...
20                                        {@{ObjectId=e27fdfb5-bb38-4032-bb33-8e8bdf086eff; TeamsMeetingPolicy=}, @{ObjectId=91c330...
2      RestrictedAnonymousAccess          {@{ObjectId=38b35ebf-cc8b-4b61-a2db-f6e67c3f614b; TeamsMeetingPolicy=RestrictedAnonymousAccess...
```

## <a name="unassign-the-restrictedanonymous-meeting-policy-from-users"></a>Отогнание от пользователей политики restrictedAnonymous meeting

Чтобы удалить политику собраний RestrictedAnonymous для пользователей, используйте для этого cmdlet [Grant-CSTeamsMeetingPolicy,](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) если у вас небольшое количество пользователей (например, менее 100). Если пользователей много (например, более 100), для отправки пакетной операции эффективнее использовать новый для [CsBatchPolicyAssignmentOperation.](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps)

### <a name="use-the-grant-csteamsmeeting-policy-cmdlet"></a>Использование Grant-CsTeamsMeeting политики

Чтобы удалить политику restrictedAnonymous meeting для пользователей, запустите следующую:

```powershell
Get-CsOnlineUser |? TeamsMeetingPolicy -eq "RestrictedAnonymousAccess" | Select-Object objectid | foreach {Grant-CsTeamsMeetingPolicy -Identity $_.ObjectId -PolicyName $null}
```

### <a name="use-the-new-csbatchpolicyassignmentoperation-cmdlet"></a>Использование New-CsBatchPolicyAssignmentOperation управления

При [назначении пакетной](assign-policies.md#assign-a-policy-to-a-batch-of-users)политики максимальное количество пользователей, для которых можно удалить или обновить политики, составляет 5000 за один раз. Например, если у вас более 5000 пользователей, необходимо отправить несколько пакетов. Для лучших результатов не от отправьте несколько пакетов за один раз. Разрешить обработку пакетов перед отправкой дополнительных пакетов.

> [!NOTE]
> Командлет [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) находится в модуле Teams PowerShell. Прежде чем выполнять эти действия, установите модуль [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams)и подключите его к ним. Пошаговую инструкцию см. в [руководстве по установке Microsoft Teams PowerShell.](teams-powershell-install.md)

Чтобы удалить политику собраний RestrictedAnonymousAccess для пакета пользователей, следуя следующим командам:

```powershell
$restrictedAnonymousUsers = @(Get-CsOnlineUser |? TeamsMeetingPolicy -eq "RestrictedAnonymousAccess" | %{ $_.ObjectId })
```

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $restrictedAnonymousUsers -OperationName "Batch unassign meeting policy"
```

#### <a name="get-the-status-of-the-batch-assignment"></a>Получить состояние назначения пакета

Каждое пакетное назначение возвращает номер операции, который можно использовать для отслеживания хода выполнения и состояния назначений, а также выявления сбоев. Например, запустите следующую:

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 62557b78-e734-42d6-952f-41a454ed6115
```

Убедитесь, **что значение ErrorCount** **— 0 (ноль),** а **overallStatus** **— завершено.**

## <a name="related-topics"></a>Статьи по теме

- [Управление политиками собраний в Teams](meeting-policies-in-teams.md)
- [Обзор PowerShell в Teams](teams-powershell-overview.md)
- [Назначение политик пользователям в Teams](assign-policies.md)
