---
title: Настройка политик трансляции Microsoft Teams с помощью PowerShell
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 10/23/2018
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
search.appverid: MET150
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
description: Примеры использования PowerShell для задания политик в Teams, чтобы управлять тем, кто может хранить события в сети в вашей организации, и функциональные возможности, доступные в создаваемых ими событиях.
appliesto:
- Microsoft Teams
ms.openlocfilehash: f92541cfdb69237631d1552202e95e4843987a30
ms.sourcegitcommit: 9d9376c6e5e6d79e33ba54fb8ce87509a2f57754
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/17/2019
ms.locfileid: "35012976"
---
# <a name="use-powershell-to-set-live-events-policies-in-microsoft-teams"></a>Настройка политик трансляции Microsoft Teams с помощью PowerShell

Вы можете использовать следующие командлеты Windows PowerShell для задания и назначения параметров политики для событий Live Events в teams: 
- [Get-Кстеамсмитингброадкастполици](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [Set-Кстеамсмитингброадкастполици](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [New-Кстеамсмитингброадкастполици](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [Grant-Кстеамсмитингброадкастполици](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingbroadcastpolicy?view=skype-ps)

Вот несколько примеров.

## <a name="allow-users-to-schedule-live-events"></a>Разрешение пользователям планировать Интерактивные события 

> [!NOTE]
> Эти примеры предназначены для событий, создаваемых в Teams. Для событий, произвела внешние приложения или устройства, необходимо выполнить дополнительные действия. Дополнительные сведения можно найти [в разделе Предоставление пользователям возможности планировать события, созданные с помощью внешнего приложения или устройства](set-up-for-teams-live-events.md#enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device).

**Разрешение пользователю планировать события в реальном времени**

Если пользователю назначена Глобальная политика, запустите и убедитесь, что для параметра *алловброадкастсчедулинг* задано *значение true*:
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
Затем назначьте пользователю глобальную политику, выполните:
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

### <a name="user-scenarios"></a>Пользовательские сценарии
**Вы хотите, чтобы все пользователи в вашей организации смогли планировать мероприятия в реальном времени**

Если пользователю назначена Глобальная политика, запустите и убедитесь, что для *алловброадкастсчедулинг* * установлено *значение true*:
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
Если пользователю назначена политика, отличная от глобальной политики, запустите и убедитесь, что для параметра *-алловброадкастсчедулинг* задано *значение true*:
```
Get-CsTeamsMeetingBroadcastPolicy -identity {policy name}
```
**Вы хотите, чтобы планирование событий в реальном времени была отключено в вашей организации**

Отключите планирование событий в реальном времени, выполните следующие действия:
```
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
Назначьте глобальным политикам всех пользователей в Организации, выполните следующие действия:
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

**Вы хотите, чтобы у вас было большое количество пользователей для планирования событий в реальном времени и предотвратить их расписаний в наборе пользователей**

Запустите и убедитесь, что для *алловброадкастсчедулинг* установлено *значение true*:
```
Get-CsTeamsMeetingBroadcastPolicy -Identity Global
```
Затем назначьте пользователю или пользователям глобальную политику, выполните:
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

Создать новую политику, которая не позволяет планировать Интерактивные события, выполните:
```
New-CSTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy
```
Отключите планирование событий в реальном времени, выполните следующие действия:
```
Set-CsTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy -AllowBroadcastScheduling $false
```
Затем назначьте пользователям эту политику, выполните:
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName DisabledBroadcastSchedulingPolicy -Verbose
```
**Вы хотите отключить планирование событий Live для большого количества пользователей и разрешить группе пользователей планировать их**

Отключите планирование событий в реальном времени, выполните следующие действия:
```
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
Затем назначьте этим пользователям глобальную политику, выполните:
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
Создание политики для планирования событий в реальном времени, выполнение:
```
New-CSTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy
```
Включить планирование событий в реальном времени, выполнить:
```
Set-CsTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy -AllowBroadcastScheduling $true
```
Затем назначьте пользователям эту политику, выполните:
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName EnableBroadcastSchedulingpolicy -Verbose
```
## <a name="set-who-can-join-live-events"></a>Выбор пользователей, которые могут присоединиться к Live Events
 
Настройте глобальную политику так, чтобы разрешить пользователям создавать события для всех пользователей, в том числе анонимных пользователей, а также выполнять указанные ниже действия.
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastAttendeeVisibility Everyone  
```
## <a name="set-the-recording-option-for-live-events"></a>Настройка параметров записи для событий в реальном времени
> [!NOTE]
> Этот параметр применяется только к событиям, созданным в Teams.

Установите для глобальной политики отключение записи для событий Live Events.
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastRecordingMode AlwaysDisabled 
```
## <a name="set-transcription-and-translation-in-live-events-coming-soon"></a>Настройка транскрипции и перевода в Live Events (скоро)
> [!NOTE]
> Этот параметр применяется только к событиям, созданным в Teams. 

Настройте глобальную политику включения транскрипции и перевода для участников события:
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -AllowBroadcastTranscription $true 
```

### <a name="related-topics"></a>Статьи по теме
- [Настройка прямых трансляций Teams](set-up-for-teams-live-events.md)


