---
title: Использование PowerShell для настройки политик трансляций
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.date: 07/10/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
audience: admin
search.appverid: MET150
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
description: Примеры использования PowerShell для настройки политик в Teams для управления тем, кто может проводить трансляции в вашей организации, и функциями, доступными в этих событиях.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ef243860ea1450dcd5539d3d5b01025e7eac55cd
ms.sourcegitcommit: 0d25efb3dae31d5199807a14baaf30e944f561ce
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/11/2023
ms.locfileid: "69767579"
---
# <a name="use-powershell-to-set-live-events-policies-in-microsoft-teams"></a>Настройка политик трансляции Microsoft Teams с помощью PowerShell

Чтобы задать и назначить параметры политики для трансляций в Teams, можно использовать следующие командлеты Windows PowerShell:

- [Get-CsTeamsMeetingBroadcastPolicy](/powershell/module/skype/get-csteamsmeetingbroadcastpolicy)
- [Set-CsTeamsMeetingBroadcastPolicy](/powershell/module/skype/set-csteamsmeetingbroadcastpolicy)
- [New-CsTeamsMeetingBroadcastPolicy](/powershell/module/skype/new-csteamsmeetingbroadcastpolicy)
- [Grant-CsTeamsMeetingBroadcastPolicy](/powershell/module/skype/grant-csteamsmeetingbroadcastpolicy)
- [New-CsGroupPolicyAssignment](/powershell/module/teams/new-csgrouppolicyassignment)

Вот несколько примеров.

> [!NOTE]
> Перед выполнением этих командлетов необходимо подключиться к Skype для бизнеса PowerShell Online. Дополнительные сведения см. в статье [Управление Skype для бизнеса Online с помощью Microsoft 365 или Office 365 PowerShell](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).

## <a name="allow-users-to-schedule-live-events"></a>Разрешить пользователям планировать трансляции

> [!NOTE]
> Эти примеры относятся к событиям, созданным в Teams.

### <a name="allow-a-user-to-schedule-live-events"></a>Разрешить пользователю планировать трансляции

Если пользователю назначена глобальная политика, запустите и убедитесь, что параметр *AllowBroadcastScheduling* имеет значение *True*:

```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```

Затем назначьте пользователя глобальной политике и выполните следующую команду:

```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

### <a name="user-scenarios"></a>Пользовательские сценарии

#### <a name="you-want-all-users-in-your-organization-to-be-able-to-schedule-live-events"></a>Вы хотите, чтобы все пользователи в вашей организации могли планировать трансляции

Если пользователям назначена глобальная политика, запустите и убедитесь, что *параметр AllowBroadcastScheduling* имеет значение *True*:

```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```

Если пользователям назначена политика, отличающаяся от глобальной, запустите и убедитесь, что для *параметра -AllowBroadcastScheduling* задано значение *True*:

```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity {policy name}
```

#### <a name="you-want-live-events-scheduling-to-be-disabled-across-your-organization"></a>Вы хотите, чтобы планирование трансляций было отключено в вашей организации

Отключите планирование трансляций, выполните следующую команду:

```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```

Назначьте всех пользователей в организации глобальной политике, выполните следующую команду:

```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

#### <a name="you-want-a-large-number-of-users-to-be-able-to-schedule-live-events-and-prevent-a-set-of-users-from-scheduling-them"></a>Вы хотите, чтобы большое количество пользователей могло планировать трансляции и не позволять набору пользователей планировать их

Запустите и убедитесь, что параметр *AllowBroadcastScheduling* имеет значение *True*:

```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -Identity Global
```

Затем назначьте пользователя или пользователей глобальной политике, выполните следующую команду:

```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

Создайте новую политику, которая не позволяет планировать трансляции, выполните следующую команду:

```PowerShell
New-CSTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy
```

Отключите планирование трансляций, выполните следующую команду:

```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy -AllowBroadcastScheduling $false
```

Затем назначьте пользователей этой политике и выполните следующую команду:

```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName DisabledBroadcastSchedulingPolicy -Verbose
```

#### <a name="you-want-to-disable-live-event-scheduling-for-a-large-number-of-the-users-and-allow-a-set-of-users-to-schedule-them"></a>Вы хотите отключить планирование трансляций для большого числа пользователей и разрешить набору пользователей планировать их

Отключите планирование трансляций, выполните следующую команду:

```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```

Затем назначьте этих пользователей глобальной политике и выполните следующую команду:

```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

Создайте политику, чтобы разрешить планирование трансляций, выполните следующую команду:

```PowerShell
New-CSTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy
```

Включите планирование трансляций, выполните:

```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy -AllowBroadcastScheduling $true
```

Затем назначьте пользователей этой политике и выполните следующую команду:

```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName EnableBroadcastSchedulingpolicy -Verbose
```

## <a name="set-who-can-join-live-events"></a>Настройка пользователей, которые могут присоединяться к трансляциям

Настройте глобальную политику, чтобы разрешить пользователям создавать события, которые могут выполнять все, включая анонимных пользователей:

```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastAttendeeVisibility Everyone  
```

## <a name="set-the-recording-option-for-live-events"></a>Настройка параметра записи для трансляций

> [!NOTE]
> Этот параметр применяется только к событиям, созданным в Teams.

Настройте глобальную политику, чтобы отключить запись для трансляций:

```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastRecordingMode AlwaysDisabled 
```

## <a name="set-live-captions-and-subtitles-in-live-events"></a>Настройка субтитров и субтитров в трансляциях

> [!NOTE]
> Этот параметр применяется только к событиям, созданным в Teams.

Настройте глобальную политику, чтобы включить субтитры и субтитры (транскрибирование) для участников мероприятия:

```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -AllowBroadcastTranscription $true 
```

### <a name="related-topics"></a>См. также

- [Настройка прямых трансляций Teams](set-up-for-teams-live-events.md)
- [Обзор PowerShell в Teams](../teams-powershell-overview.md)
