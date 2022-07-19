---
title: Настройка политик трансляций с помощью PowerShell
author: mkbond007
ms.author: mabond
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
ms.openlocfilehash: e0d46c0675bd8b810f8dbce8585661184fbef74f
ms.sourcegitcommit: 791d0a341ff873145fa893ece05055729b0b8d50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/18/2022
ms.locfileid: "66838844"
---
# <a name="use-powershell-to-set-live-events-policies-in-microsoft-teams"></a>Настройка политик трансляции Microsoft Teams с помощью PowerShell

Чтобы задать и назначить параметры политики для трансляций в Teams, можно использовать следующие Windows PowerShell командлеты: 
- [Get-CsTeamsMeetingBroadcastPolicy](/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [Set-CsTeamsMeetingBroadcastPolicy](/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [New-CsTeamsMeetingBroadcastPolicy](/powershell/module/skype/new-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [Grant-CsTeamsMeetingBroadcastPolicy](/powershell/module/skype/grant-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [New-CsGroupPolicyAssignment](/powershell/module/teams/new-csgrouppolicyassignment?view=teams-ps)

Вот несколько примеров.

> [!NOTE]
> Перед выполнением этих командлетов необходимо подключиться к Skype для бизнеса PowerShell. Дополнительные сведения см. в статье ["Управление Skype для бизнеса Online с помощью Microsoft 365 или Office 365 PowerShell"](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).

## <a name="allow-users-to-schedule-live-events"></a>Разрешить пользователям планировать трансляции 

> [!NOTE]
> Эти примеры предназначены для событий, созданных в Teams. Для событий, созданных с помощью внешнего приложения или устройства, необходимо выполнить дополнительные действия. Дополнительные сведения см. в разделе ["Разрешить пользователям планировать события, созданные с помощью внешнего приложения или устройства"](set-up-for-teams-live-events.md#enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device).

**Разрешить пользователю планировать трансляции**

Если пользователю назначена глобальная политика, запустите и убедитесь, что параметр *AllowBroadcastScheduling* имеет значение *True*:
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
Затем назначьте пользователя глобальной политике, выполните следующую команду:
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

### <a name="user-scenarios"></a>Пользовательские сценарии
**Вы хотите, чтобы все пользователи в организации могли планировать трансляции**

Если пользователям назначена глобальная политика, запустите и убедитесь, что *параметр AllowBroadcastScheduling* *имеет *значение True*:
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
Если пользователям назначена не глобальная политика, запустите и убедитесь, что *параметру -AllowBroadcastScheduling* присвоено значение *True*:
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity {policy name}
```
**Вы хотите отключить планирование трансляций в организации**

Отключите планирование трансляций, выполните следующую команду:
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
Назначьте всем пользователям в организации глобальную политику, выполните следующую команду:
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

**Вы хотите, чтобы большое количество пользователей могли планировать трансляции и запретить их планированию.**

Запустите и убедитесь, *что параметр AllowBroadcastScheduling* имеет значение *True*:
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -Identity Global
```
Затем назначьте пользователя или пользователя глобальной политике, выполните следующую команду:
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

Создайте политику, которая не разрешает планирование трансляций, выполните следующую команду:
```PowerShell
New-CSTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy
```
Отключите планирование трансляций, выполните следующую команду:
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy -AllowBroadcastScheduling $false
```
Затем назначьте пользователям эту политику, выполните следующую команду:
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName DisabledBroadcastSchedulingPolicy -Verbose
```
**Вы хотите отключить планирование трансляций для большого числа пользователей и разрешить им планировать их**

Отключите планирование трансляций, выполните следующую команду:
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
Затем назначьте этих пользователей глобальной политике, выполните следующую команду:
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
Создайте политику, чтобы разрешить планирование трансляций, выполните следующую команду:
```PowerShell
New-CSTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy
```
Включите планирование трансляций, выполните следующую команду:
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy -AllowBroadcastScheduling $true
```
Затем назначьте пользователям эту политику, выполните следующую команду:
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName EnableBroadcastSchedulingpolicy -Verbose
```
## <a name="set-who-can-join-live-events"></a>Настройка пользователей, которые могут присоединяться к трансляциям
 
Задайте глобальную политику, чтобы разрешить пользователям создавать события, на которых могут присутствовать все пользователи, включая анонимных пользователей, и запускать:
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastAttendeeVisibility Everyone  
```
## <a name="set-the-recording-option-for-live-events"></a>Настройка параметра записи для трансляций
> [!NOTE]
> Этот параметр применяется только к событиям, созданным в Teams.

Задайте глобальную политику, чтобы отключить запись для трансляций:
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastRecordingMode AlwaysDisabled 
```
## <a name="set-live-captions-and-subtitles-in-live-events"></a>Настройка субтитров и субтитров в трансляциях
> [!NOTE]
> Этот параметр применяется только к событиям, созданным в Teams. 

Задайте глобальную политику, чтобы включить субтитры и субтитры (транскрибирование) для участников мероприятия:
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -AllowBroadcastTranscription $true 
```

### <a name="related-topics"></a>Связанные статьи
- [Настройка прямых трансляций Teams](set-up-for-teams-live-events.md)
- [Обзор PowerShell в Teams](../teams-powershell-overview.md)