---
title: Удаление политики собраний RestrictedAnonymousAccess Teams для пользователей
author: LanaChin
ms.author: v-lanac
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
description: Сведения о том, как удалить политику собраний RestrictedAnonymousAccess Teams для пользователей в вашей организации.
ms.openlocfilehash: 12224ec860552b17b6f7fe50396081943955a88c
ms.sourcegitcommit: b72bf3827e7145b9b6a95c84e88a7879c6e8c337
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/12/2020
ms.locfileid: "46640999"
---
# <a name="remove-the-restrictedanonymousaccess-teams-meeting-policy-from-users"></a>Удаление политики собраний RestrictedAnonymousAccess Teams для пользователей

[Политики собраний](meeting-policies-in-teams.md) в Microsoft Teams используются для управления возможностями, доступными участникам собрания для собраний, запланированных пользователями в Организации. 

Команды включают встроенную политику с именем RestrictedAnonymousAccess, которая содержит предопределенные параметры, которые включают в себя запрет на запуск собрания анонимными пользователями. (Анонимные пользователи — это пользователи, которые не прошли проверку подлинности.) Предопределенные параметры в политике собрания невозможно изменить или изменить с помощью администраторов.

В этой статье объясняется, как использовать PowerShell для удаления политики собраний RestrictedAnonymousAccess от пользователей, которым назначена эта политика. Дополнительные сведения о том, как управлять группами с помощью PowerShell, можно найти в разделе [Общие сведения о Teams PowerShell](teams-powershell-overview.md).

## <a name="before-you-start"></a>Перед началом работы

Установите и подключитесь к [модулю PowerShell Skype для бизнеса](https://www.microsoft.com/download/details.aspx?id=39366). Пошаговые инструкции можно найти в статье [Установка Microsoft Teams PowerShell](teams-powershell-install.md).

## <a name="get-the-teams-meeting-policy-assignments-for-your-organization"></a>Получение назначений политики собраний Teams для Организации

Выполните указанные ниже действия, чтобы получить назначения политики для собраний Teams для вашей организации.

```powershell
Get-CsOnlineUser | Select-Object objectid, TeamsMeetingPolicy | Group-Object TeamsMeetingPolicy
```

В этом примере возвращается приведенный ниже вывод, в котором показано, что двум пользователям назначена политика собраний RestrictedAnonymousAccess.

```console
Count  Name                               Group
------ ----------                         ---------
233    Education_HigherEducationStudent   {@{ObjectId=755e0d21-0737-4219-b68a-23423497f61f; TeamsMeetingPolicy=Education_HigherEducationStudent...
20                                        {@{ObjectId=e27fdfb5-bb38-4032-bb33-8e8bdf086eff; TeamsMeetingPolicy=}, @{ObjectId=91c330...
2      RestrictedAnonymousAccess          {@{ObjectId=38b35ebf-cc8b-4b61-a2db-f6e67c3f614b; TeamsMeetingPolicy=RestrictedAnonymousAccess...
```

## <a name="unassign-the-restrictedanonymous-meeting-policy-from-users"></a>Отмена назначения политики собрания RestrictedAnonymous пользователям

Чтобы удалить политику собраний RestrictedAnonymous от пользователей, можно использовать командлет [Grant-CSTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) , если у вас небольшое количество пользователей (например, менее 100 пользователей). Если у вас большое количество пользователей (например, более 100 пользователей), более эффективно использовать командлет [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) для отправки пакетной операции.

### <a name="use-the-grant-csteamsmeeting-policy-cmdlet"></a>Использование командлета Grant-CsTeamsMeeting

Выполните указанные ниже действия, чтобы удалить политику собраний RestrictedAnonymous из пользователей.

```powershell
Get-CsOnlineUser |? TeamsMeetingPolicy -eq "RestrictedAnonymousAccess" | Select-Object objectid | foreach {Grant-CsTeamsMeetingPolicy -Identity $_.ObjectId -PolicyName $null}
```

### <a name="use-the-new-csbatchpolicyassignmentoperation-cmdlet"></a>Использование командлета New-CsBatchPolicyAssignmentOperation

При [назначении пакетной политики](assign-policies.md#assign-a-policy-to-a-batch-of-users)максимальное количество пользователей, для которых можно удалить или изменить политики, составляет 5 000 за один раз. Например, если у вас более 5 000 пользователей, вам нужно будет отправить несколько пакетов. Для достижения наилучших результатов не отправляйте в каждый момент времени несколько пакетов. Разрешите пакетам завершить обработку перед отправкой пакетов.

> [!NOTE]
> Командлет [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) находится в модуле PowerShell Teams. Перед тем как выполнять эти действия, установите и подключитесь к [модулю PowerShell Teams](https://www.powershellgallery.com/packages/MicrosoftTeams). Пошаговые инструкции можно найти в статье [Установка Microsoft Teams PowerShell](teams-powershell-install.md).

Чтобы удалить политику собраний RestrictedAnonymousAccess из пакета пользователей, выполните указанные ниже команды.

```powershell
$restrictedAnonymousUsers = @(Get-CsOnlineUser |? TeamsMeetingPolicy -eq "RestrictedAnonymousAccess" | %{ $_.ObjectId })
```

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $restrictedAnonymousUsers -OperationName "Batch unassign meeting policy"
```

#### <a name="get-the-status-of-the-batch-assignment"></a>Получение статуса задания партии

Каждое назначение партии возвращает идентификатор операции, который можно использовать для отслеживания хода выполнения и состояния назначений, а также для выявления проблем, которые могут возникнуть. Например, выполните указанные ниже действия.

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 62557b78-e734-42d6-952f-41a454ed6115
```

Убедитесь в том, что **ErrorCount** равен **0** (нулю), а **OverallStatus** — **завершено**.

## <a name="related-topics"></a>Статьи по теме

- [Управление политиками собраний в Teams](meeting-policies-in-teams.md)
- [Обзор PowerShell в Teams](teams-powershell-overview.md)
- [Назначение политик пользователям в Teams](assign-policies.md)
