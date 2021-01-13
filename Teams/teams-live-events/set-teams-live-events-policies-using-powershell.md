---
title: Настройка политик трансляций с помощью PowerShell
author: cichur
ms.author: v-cichur
manager: serdars
ms.date: 07/10/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
audience: admin
search.appverid: MET150
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
description: Примеры использования PowerShell для применения политик в Teams для управления возможностью проведения трансляций в организации и доступными для них функциями.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ece22b6debd3c7d6209df96983d1d66ed5f6f3ca
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815629"
---
# <a name="use-powershell-to-set-live-events-policies-in-microsoft-teams"></a>Настройка политик трансляции Microsoft Teams с помощью PowerShell

Для настройки и назначения параметров политики для трансляций в Teams можно использовать следующие Windows PowerShell командлеты: 
- [Get-CsTeamsMeetingBroadcastPolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [Set-CsTeamsMeetingBroadcastPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [New-CsTeamsMeetingBroadcastPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [Grant-CsTeamsMeetingBroadcastPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment?view=teams-ps)

Вот несколько примеров.

> [!NOTE]
> Перед запуском этих cmdlets необходимо подключение к Skype для бизнеса Online PowerShell. Дополнительные сведения см. в управлении [Skype для бизнеса Online с помощью Microsoft 365 или Office 365 PowerShell.](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)

## <a name="allow-users-to-schedule-live-events"></a>Разрешить пользователям планировать трансляции 

> [!NOTE]
> Эти примеры можно привести для событий, произведенных в Teams. Для событий, произведенных с внешним приложением или устройством, необходимо сделать дополнительные действия. Дополнительные сведения см. в том, как включить пользователей в расписание событий, которые были произведены с помощью [внешнего приложения или устройства.](set-up-for-teams-live-events.md#enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device)

**Разрешить пользователю планировать трансляции**

Если пользователю назначена глобальная политика, запустите и убедитесь, что параметр *AllowBroadcastScheduling* имеет *true:*
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
Затем назначьте пользователя глобальной политике и запустите 3
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

### <a name="user-scenarios"></a>Сценарии для пользователей
**Вы хотите, чтобы все пользователи в организации могли планировать трансляции**

Если пользователям назначена глобальная политика, запустите и убедитесь, что для *allowBroadcastScheduling* *установлено *true:*
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
Если пользователям назначена политика, которая не является глобальной, запустите и проверьте, установлено ли для этого правила *-AllowBroadcastScheduling (Планирование AllowBroadcast)* *true:*
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity {policy name}
```
**Вы хотите отключить возможность планирования трансляций в организации**

Отключите планирование трансляций, запустите:
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
Назначьте глобальной политике всех пользователей в организации, запустите 4
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

**Вы хотите, чтобы большое количество пользователей могли планировать трансляции и не допустить их планирование для набора пользователей**

Запустите и убедитесь, что *для allowBroadcastScheduling* установлено *true:*
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -Identity Global
```
Затем назначьте пользователя или пользователей глобальной политике и запустите 3
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

Создайте политику, которая не позволяет запланировать трансляции, запустите 3
```PowerShell
New-CSTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy
```
Отключите планирование трансляций, запустите:
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy -AllowBroadcastScheduling $false
```
Затем назначьте пользователей этой политике и запустите 3
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName DisabledBroadcastSchedulingPolicy -Verbose
```
**Вы хотите отключить планирование трансляций для большого количества пользователей и разрешить набору пользователей планировать их**

Отключите планирование трансляций, запустите:
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
Затем назначьте этим пользователям глобальную политику и запустите 3
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
Затем назначьте пользователей этой политике и запустите 3
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName EnableBroadcastSchedulingpolicy -Verbose
```
## <a name="set-who-can-join-live-events"></a>Настройка того, кто может присоединяться к трансляциям
 
Установите глобальную политику, чтобы разрешить пользователям создавать события, в которых могут участвовать все пользователи, в том числе анонимные пользователи, и запускать:
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastAttendeeVisibility Everyone  
```
## <a name="set-the-recording-option-for-live-events"></a>Настройка параметра записи для трансляций
> [!NOTE]
> Этот параметр применяется только к мероприятиям, проданной в Teams.

Установите глобальную политику, чтобы отключить запись для трансляций.
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastRecordingMode AlwaysDisabled 
```
## <a name="set-live-captions-and-subtitles-in-live-events"></a>Настройка субтитров в трансляциях
> [!NOTE]
> Этот параметр применяется только к мероприятиям, проданной в Teams. 

Установите глобальную политику, чтобы включить живые субтитры (транскрипцию) для участников события:
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -AllowBroadcastTranscription $true 
```

### <a name="related-topics"></a>Статьи по теме
- [Настройка прямых трансляций Teams](set-up-for-teams-live-events.md)
- [Обзор PowerShell в Teams](../teams-powershell-overview.md)

