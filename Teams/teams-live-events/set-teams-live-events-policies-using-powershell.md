---
title: Настройка политик трансляций с помощью PowerShell
author: HowlinWolf-92
ms.author: v-mahoffman
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
description: Примеры использования PowerShell для того, чтобы настроить политики в Teams, чтобы контролировать, кто может проводить трансляции в организации, и какие функции доступны в них.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: cda9da872d8464064c137713e8eb16ceede7941e
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2021
ms.locfileid: "60851733"
---
# <a name="use-powershell-to-set-live-events-policies-in-microsoft-teams"></a>Настройка политик трансляции Microsoft Teams с помощью PowerShell

Для настройки и назначения параметров политики для трансляций в Windows PowerShell можно использовать следующие Teams: 
- [Get-CsTeamsMeetingBroadcastPolicy](/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [Set-CsTeamsMeetingBroadcastPolicy](/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [New-CsTeamsMeetingBroadcastPolicy](/powershell/module/skype/new-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [Grant-CsTeamsMeetingBroadcastPolicy](/powershell/module/skype/grant-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [New-CsGroupPolicyAssignment](/powershell/module/teams/new-csgrouppolicyassignment?view=teams-ps)

Вот несколько примеров.

> [!NOTE]
> Перед запуском этих cmdlets необходимо подключение к Skype для бизнеса Online PowerShell. Дополнительные сведения см. в Skype для бизнеса Online с [помощью Microsoft 365 или Office 365 PowerShell.](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)

## <a name="allow-users-to-schedule-live-events"></a>Разрешить пользователям планировать трансляции 

> [!NOTE]
> Эти примеры можно привести для событий, которые были произведены в Teams. Для событий, которые были произведены с помощью внешнего приложения или устройства, необходимо сделать дополнительные действия. Дополнительные сведения см. в статьи Возможность пользователям планировать события, которые были произведены с помощью [внешнего приложения или устройства.](set-up-for-teams-live-events.md#enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device)

**Разрешить пользователю планировать трансляции**

Если пользователю назначена глобальная политика, запустите и убедитесь, что параметр *AllowBroadcastScheduling* имеет *true:*
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
Затем назначьте пользователя глобальной политике и запустите:
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

### <a name="user-scenarios"></a>Сценарии для пользователей
**Вы хотите, чтобы все пользователи в организации могли планировать трансляции**

Если пользователям назначена глобальная политика, запустите и убедитесь, что *для allowBroadcastScheduling* *установлено *true:*
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
Если пользователям назначена политика, которая не является глобальной, запустите и убедитесь, что для *-AllowBroadcastScheduling* за установлено *true:*
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity {policy name}
```
**Вы хотите отключить планирование трансляций в организации**

Отключите планирование трансляций, запустите:
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
Назначьте глобальной политике всех пользователей в организации и запустите:
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

**Вы хотите, чтобы большое количество пользователей могли планировать трансляции и запретить им планировать их**

Запустите и убедитесь, что *для allowBroadcastScheduling* за установлено *true:*
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -Identity Global
```
Затем назначьте пользователя или пользователей глобальной политике, запустите 2016.
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

Создайте политику, которая не позволяет запланировать трансляции, запустите:
```PowerShell
New-CSTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy
```
Отключите планирование трансляций, запустите:
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy -AllowBroadcastScheduling $false
```
Затем назначьте пользователей этой политике и запустите:
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName DisabledBroadcastSchedulingPolicy -Verbose
```
**Вы хотите отключить планирование трансляций для большого количества пользователей и разрешить им планировать события.**

Отключите планирование трансляций, запустите:
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
Затем назначьте этих пользователей глобальной политике и запустите:
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
Создайте политику, чтобы разрешить планирование трансляций, запустите:
```PowerShell
New-CSTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy
```
Включить планирование трансляций, выполнить:
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy -AllowBroadcastScheduling $true
```
Затем назначьте пользователей этой политике и запустите:
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName EnableBroadcastSchedulingpolicy -Verbose
```
## <a name="set-who-can-join-live-events"></a>Настройка того, кто может присоединяться к трансляциям
 
Установите глобальную политику, чтобы разрешить пользователям создавать события, которые могут посещать все пользователи, включая анонимных, а также запускать:
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastAttendeeVisibility Everyone  
```
## <a name="set-the-recording-option-for-live-events"></a>Настройка параметра записи для трансляций
> [!NOTE]
> Этот параметр применяется только к событиям, которые были произведены Teams.

Установите глобальную политику, чтобы отключить запись для трансляций:
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastRecordingMode AlwaysDisabled 
```
## <a name="set-live-captions-and-subtitles-in-live-events"></a>Настройка субтитров в трансляциях
> [!NOTE]
> Этот параметр применяется только к событиям, которые были произведены Teams. 

Установите глобальную политику, чтобы включить субтитры (транскрипцию) для участников мероприятия:
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -AllowBroadcastTranscription $true 
```

### <a name="related-topics"></a>Статьи по теме
- [Настройка прямых трансляций Teams](set-up-for-teams-live-events.md)
- [Обзор PowerShell в Teams](../teams-powershell-overview.md)