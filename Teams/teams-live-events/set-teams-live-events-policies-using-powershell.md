---
title: Настройка политик трансляции Microsoft Teams с помощью PowerShell
author: chuckedmonson
ms.author: chucked
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
description: Примеры использования PowerShell для задания политик в Teams, чтобы управлять тем, кто может хранить события в сети в вашей организации, и функциональные возможности, доступные в создаваемых ими событиях.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 46c3522cc428ec04d830d8bdb02bad56f5dfd437
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41827117"
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
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
Затем назначьте пользователю глобальную политику, выполните:
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

### <a name="user-scenarios"></a>Пользовательские сценарии
**Вы хотите, чтобы все пользователи в вашей организации смогли планировать мероприятия в реальном времени**

Если пользователю назначена Глобальная политика, запустите и убедитесь, что для *алловброадкастсчедулинг* * установлено *значение true*:
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
Если пользователю назначена политика, отличная от глобальной политики, запустите и убедитесь, что для параметра *-алловброадкастсчедулинг* задано *значение true*:
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

Запустите и убедитесь, что для *алловброадкастсчедулинг* установлено *значение true*:
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

### <a name="related-topics"></a>См. также
- [Настройка прямых трансляций Teams](set-up-for-teams-live-events.md)


