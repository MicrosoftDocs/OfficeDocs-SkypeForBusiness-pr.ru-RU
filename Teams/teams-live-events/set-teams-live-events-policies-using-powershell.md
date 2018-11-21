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
MS.collection: Teams_ITAdmin_Help
description: Примеры того, как использовать PowerShell для определения политик в группах, чтобы контролировать, кто сохранения live события в вашей организации и функции, доступные в события, которые они создают
appliesto:
- Microsoft Teams
ms.openlocfilehash: c198711d918914bbd6a1929514d7c2e9aa7dfe00
ms.sourcegitcommit: ff0c4bef4d4cbc71d51fce941aff63739a0016e9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2018
ms.locfileid: "26626225"
---
# <a name="use-powershell-to-set-live-events-policies-in-microsoft-teams"></a>Настройка политик трансляции Microsoft Teams с помощью PowerShell
> [!INCLUDE [Preview customer token](../includes/preview-feature.md)]

Можно использовать следующие командлеты Windows PowerShell для установки и назначить параметры политики для live событий в группах: 
- [Get-CsTeamsMeetingBroadcastPolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [SET-CsTeamsMeetingBroadcastPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [Новый CsTeamsMeetingBroadcastPolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [Предоставление CsTeamsMeetingBroadcastPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingbroadcastpolicy?view=skype-ps)

Вот несколько примеров.

## <a name="allow-users-to-schedule-live-events"></a>Разрешить пользователям планировать событий в реальном времени 

> [!NOTE]
> В этих примерах используются события быстрого запуска. Для внешних кодировщика событий существуют дополнительные действия, которые необходимо выполнить. Дополнительные сведения можно [Разрешить пользователям планировать события внешнего кодировщика](set-up-for-teams-live-events.md#enable-users-to-schedule-external-encoder-events).

**Предоставление разрешений пользователю для планирования событий в реальном времени**

Если пользователю назначена глобальную политику, запуск и убедитесь, что параметр *AllowBroadcastScheduling* задано значение *True*:
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
Назначьте пользователя для глобальной политики, выполните:
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

### <a name="user-scenarios"></a>Пользовательские сценарии
**Все пользователи в вашей организации должны иметь возможность планирования событий в реальном времени**

Если пользователи назначаются глобальную политику, запустите и убедитесь, что *AllowBroadcastScheduling* * имеет значение *True*:
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
Если пользователи назначена политика, отличный от глобальной политики, запуск и убедитесь, что *- AllowBroadcastScheduling* задано значение *True*:
```
Get-CsTeamsMeetingBroadcastPolicy -identity {policy name}
```
**Требуется событий в реальном времени планирования требуется запретить в организации**

Отключение планирования событий в реальном времени, выполните:
```
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
Назначение всех пользователей в вашей организации для глобальной политики, выполните:
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

**Большое число пользователи должны иметь возможность планировать события и предотвратить планирования их группы пользователей**

Запуск и убедитесь, что *AllowBroadcastScheduling* задано значение *True*:
```
Get-CsTeamsMeetingBroadcastPolicy -Identity Global
```
Затем назначение одного или нескольких пользователей для глобальной политики, выполните:
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

Создайте новую политику, которая не позволяет планирования live события, выполните:
```
New-CSTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy
```
Отключение планирования событий в реальном времени, выполните:
```
Set-CsTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy -AllowBroadcastScheduling $false
```
Затем назначение пользователей для этой политики, выполните:
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName DisabledBroadcastSchedulingPolicy -Verbose
```
**Чтобы отключить трансляция расписания для большого числа пользователей и разрешить группы пользователей, чтобы запланировать их**

Отключение планирования событий в реальном времени, выполните:
```
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
Затем назначение этих пользователей для глобальной политики, выполните:
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
Создание политики, чтобы разрешить планирование событий в реальном времени, выполните:
```
New-CSTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy
```
Включить планирование событий в реальном времени, выполните:
```
Set-CsTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy -AllowBroadcastScheduling $true
```
Затем назначение пользователей для этой политики, выполните:
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName EnableBroadcastSchedulingpolicy -Verbose
```
## <a name="set-who-can-join-live-events"></a>Набор, который сможет присоединиться к событий в реальном времени
 
Задайте для глобальной политики, чтобы разрешить пользователям создавать события, все, включая анонимных пользователей, можно посещение, выполните:
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastAttendeeVisibility Everyone  
```
## <a name="set-the-recording-option-for-live-events"></a>Установить параметр записи для событий в реальном времени
> [!NOTE]
> Этот параметр применяется только к события быстрого запуска.

Задайте для глобальной политики для отключения записи для событий в реальном времени:
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastRecordingMode AlwaysDisabled 
```
## <a name="set-transcription-and-translation-in-live-events-coming-soon"></a>Задайте транскрибирования и перевода в режиме реального времени события (ожидается в ближайшее время)
> [!NOTE]
> Этот параметр применяется только к события быстрого запуска. 

Задайте для глобальной политики для включения транскрибирования и перевода участников событий:
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -AllowBroadcastTranscription $true 
```

### <a name="related-topics"></a>Связанные разделы
- [Настройка для групп событий в реальном времени](set-up-for-teams-live-events.md)


