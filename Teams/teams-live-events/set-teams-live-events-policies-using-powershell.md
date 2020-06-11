---
title: Настройка политик живых событий с помощью PowerShell
author: lanachin
ms.author: v-lanac
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
description: Примеры использования PowerShell для настройки политик в Teams, чтобы управлять тем, кто может вести в организации события в реальном времени, и возможности, доступные в событиях.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 1c1131790e36fe451444a8c8a3fb25259d5741da
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/10/2020
ms.locfileid: "44691575"
---
# <a name="use-powershell-to-set-live-events-policies-in-microsoft-teams"></a>Настройка политик трансляции Microsoft Teams с помощью PowerShell

Вы можете использовать следующие командлеты Windows PowerShell для задания и назначения параметров политики для событий Live Events в teams: 
- [Get-CsTeamsMeetingBroadcastPolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [Set-CsTeamsMeetingBroadcastPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [New-CsTeamsMeetingBroadcastPolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [Grant-CsTeamsMeetingBroadcastPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingbroadcastpolicy?view=skype-ps)

Вот несколько примеров.

> [!NOTE]
> Перед выполнением этих командлетов необходимо подключиться к Skype для бизнеса Online PowerShell. Дополнительные сведения можно найти [в разделе Управление Skype для бизнеса Online с помощью Microsoft 365 или Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).

## <a name="allow-users-to-schedule-live-events"></a>Разрешение пользователям планировать Интерактивные события 

> [!NOTE]
> Эти примеры предназначены для событий, создаваемых в Teams. Для событий, произвела внешние приложения или устройства, необходимо выполнить дополнительные действия. Дополнительные сведения можно найти [в разделе Предоставление пользователям возможности планировать события, созданные с помощью внешнего приложения или устройства](set-up-for-teams-live-events.md#enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device).

**Разрешение пользователю планировать события в реальном времени**

Если пользователю назначена Глобальная политика, запустите и убедитесь, что для параметра *AllowBroadcastScheduling* задано *значение true*:
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
Затем назначьте пользователю глобальную политику, выполните:
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

### <a name="user-scenarios"></a>Пользовательские сценарии
**Вы хотите, чтобы все пользователи в вашей организации смогли планировать мероприятия в реальном времени**

Если пользователю назначена Глобальная политика, запустите и убедитесь, что для *AllowBroadcastScheduling* * установлено *значение true*:
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
Если пользователю назначена политика, отличная от глобальной политики, запустите и убедитесь, что для параметра *-AllowBroadcastScheduling* задано *значение true*:
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity {policy name}
```
**Вы хотите, чтобы планирование событий в реальном времени была отключено в вашей организации**

Отключите планирование событий в реальном времени, выполните следующие действия:
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
Назначьте глобальным политикам всех пользователей в Организации, выполните следующие действия:
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

**Вы хотите, чтобы у вас было большое количество пользователей для планирования событий в реальном времени и предотвратить их расписаний в наборе пользователей**

Запустите и убедитесь, что для *AllowBroadcastScheduling* установлено *значение true*:
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -Identity Global
```
Затем назначьте пользователю или пользователям глобальную политику, выполните:
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

Создать новую политику, которая не позволяет планировать Интерактивные события, выполните:
```PowerShell
New-CSTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy
```
Отключите планирование событий в реальном времени, выполните следующие действия:
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy -AllowBroadcastScheduling $false
```
Затем назначьте пользователям эту политику, выполните:
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName DisabledBroadcastSchedulingPolicy -Verbose
```
**Вы хотите отключить планирование событий Live для большого количества пользователей и разрешить группе пользователей планировать их**

Отключите планирование событий в реальном времени, выполните следующие действия:
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
Затем назначьте этим пользователям глобальную политику, выполните:
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
Создание политики для планирования событий в реальном времени, выполнение:
```PowerShell
New-CSTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy
```
Включить планирование событий в реальном времени, выполнить:
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy -AllowBroadcastScheduling $true
```
Затем назначьте пользователям эту политику, выполните:
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName EnableBroadcastSchedulingpolicy -Verbose
```
## <a name="set-who-can-join-live-events"></a>Выбор пользователей, которые могут присоединиться к Live Events
 
Настройте глобальную политику так, чтобы разрешить пользователям создавать события для всех пользователей, в том числе анонимных пользователей, а также выполнять указанные ниже действия.
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastAttendeeVisibility Everyone  
```
## <a name="set-the-recording-option-for-live-events"></a>Настройка параметров записи для событий в реальном времени
> [!NOTE]
> Этот параметр применяется только к событиям, созданным в Teams.

Установите для глобальной политики отключение записи для событий Live Events.
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastRecordingMode AlwaysDisabled 
```
## <a name="set-live-captions-and-subtitles-in-live-events"></a>Настройка живых подписей и субтитров в Live Events
> [!NOTE]
> Этот параметр применяется только к событиям, созданным в Teams. 

Настройте глобальную политику на включение субтитров и субтитров (транскрипция) для участников события:
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -AllowBroadcastTranscription $true 
```

### <a name="related-topics"></a>Статьи по теме
- [Настройка прямых трансляций Teams](set-up-for-teams-live-events.md)
- [Обзор PowerShell в Teams](../teams-powershell-overview.md)

