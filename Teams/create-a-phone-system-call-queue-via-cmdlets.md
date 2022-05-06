---
title: Создание очереди вызовов с помощью командлетов
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: colongma
ms.topic: article
ms.assetid: 67ccda94-1210-43fb-a25b-7b9785f8a061
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.callqueues.overview"
- Phone System
- seo-marvel-apr2020
description: Узнайте, как настроить очереди вызовов с помощью командлетов
ms.openlocfilehash: bdaf538164a74a366779bd3a4928330a2bc3b085
ms.sourcegitcommit: c06d806778f3e6ea4b184bae271e55c34fd9594d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2022
ms.locfileid: "65244906"
---
# <a name="create-a-call-queue-via-cmdlets"></a>Создание очереди вызовов с помощью командлетов

## <a name="assumptions"></a>Предположения
1)  На компьютере установлен PowerShell
- Настройка компьютера [для Windows PowerShell](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
- Установленный модуль MSTeams ````  (Install-Module -Name MicrosoftTeams -Force -AllowClobber) ````
- Установленный модуль MSOnline ```` Install-Module -Name MSOnline -Force -AllowClobber ````
2)  У вас есть права на администрирование клиента
3)  Вы приобрели Microsoft Teams Телефон
4)  Агенты, списки рассылки и Teams, указанные ниже, уже созданы.

Примечание. Командлет Teams Channel, используемый ниже, является частью общедоступной предварительной версии модуля Teams PowerShell.  Дополнительные сведения см. в Teams [powerShell](teams-powershell-install.md), а также в Microsoft Teams [выпуске PowerShell](teams-powershell-release-notes.md).

Пользователи, у которых уже установлен модуль MicrosoftTeams ````Update-Module MicrosoftTeams```` , должны убедиться, что установлена самая последняя версия.


## <a name="scenario"></a>Сценарий

Будут созданы следующие три очереди вызовов:

Сведения о очереди звонков по продажам:
- Перед автосекретарем: да
- Прямой вызов из ТСОП: нет
- Язык: английский (США)
- Приветствие: нет
- Музыка на удержании: воспроизведение звукового файла
- - Имя файла: sales-hold-in-queue-music.wav
- Ответы на вызовы: пользователи
- - Bill@contoso.com
- - Mary@contoso.com
- Режим конференции: включен
- Метод маршрутизации: Attendant
- Маршрутизация на основе присутствия: выкл.
- Агенты вызовов могут отказаться от звонков: Да
- Время оповещения агента вызова: 15
- Обработка переполнения вызовов: 200
- - Перенаправление на: Adele@contoso.com
- Обработка времени ожидания вызова: 120 секунд
- - Перенаправление на: Adele@contoso.com

Сведения о очереди звонков в службу поддержки:
- Перед автосекретарем: да
- Прямой вызов из ТСОП: нет
-   Язык: английский (Соединенное Королевство)
-   Приветствие: воспроизведение звукового файла
-   - Имя файла: support-greeting.wav
-   Музыка на удержании: воспроизведение звукового файла
-   - Имя файла: support-hold-in-queue-music.wav
-   Ответ на звонок: список рассылки поддержки
-   - Support@contoso.com
-   Режим конференции: включен
-   Метод маршрутизации: самый длинный бездействующий
-   Маршрутизация на основе присутствия: Н/Д — включена по умолчанию из-за самого длительного простоя
-   Агенты вызовов могут отказаться от звонков: Нет
-   Время оповещения агента вызова: 15
-   Обработка переполнения вызовов: 200
-   - Перенаправление: поддержка общей голосовой почты
- - -   Воспроизведение звукового файла (support-shared-voicemail-greeting.wav)
- - -   Транскрибирование включено
-   Обработка времени ожидания звонков: 45 минут
-   - Перенаправление: поддержка общей голосовой почты
- - - TTS: "К сожалению, вы ждете и теперь переносите звонок на голосовую почту".
- - - Транскрибирование включено


Сведения о очереди совместных вызовов Facilities:
- Перед автосекретарем: нет
- Прямой вызов из ТСОП: нет (только внутренние вызовы)
-   Язык: французский fr
-   Приветствие: нет
-   Музыка на удержании: по умолчанию
-   Ответ на вызовы: Команда: средства
-   Канал ответов на звонок: служба технической поддержки
-   - Владелец канала: Fred@contoso.com
-   Режим конференции: включен
-   Метод маршрутизации: Циклический перебор
-   Маршрутизация на основе присутствия: включена
-   Агенты вызовов могут отказаться от звонков: Нет
-   Время оповещения агента вызова: 15
-   Обработка переполнения вызовов: 200
-   - Отключить
-   Обработка времени ожидания звонков: 45 минут
-   - Отключить


## <a name="login"></a>Вход
Вам будет предложено ввести учетные данные Teams администратора.
```
$credential = Get-Credential
Connect-MicrosoftTeams -Credential $credential
Connect-MsolService -Credential $credential
````

## <a name="sales-queue"></a>Очередь продаж
### <a name="create-audio-files"></a>Создание звуковых файлов
Замените "d:\\" путем к папке, в которой хранятся WAV-файлы на компьютере.

````
$content = Get-Content “d:\sales-hold-in-queue-music.wav” -Encoding byte -ReadCount 0
$audioFileSalesHoldInQueueMusicID = (Import-CsOnlineAudioFile -ApplicationID HuntGroup -FileName "sales-hold-in-queue-music.wav" -Content $content).ID
````

### <a name="get-users-id"></a>Получение идентификатора пользователей
````
$userAdeleID = (Get-CsOnlineUser -Identity “sip:adele@contoso.com”).Identity
$userSalesBillID = (Get-CsOnlineUser -Identity “sip:bill@contoso.com”).Identity
$userSalesMaryID = (Get-CsOnlineUser -Identity “sip:mary@contoso.com”).Identity
````

### <a name="get-list-of-supported-languages"></a>Получение списка поддерживаемых языков
````
Get-CsAutoAttendantSupportedLanguage
````

### <a name="create-call-queue"></a>Создание очереди вызовов
````
New-CsCallQueue -Name “Sales” -AgentAlertTime 15 -AllowOptOut $true -MusicOnHoldAudioFileID $audioFileSalesHoldInQueueMusicID -OverflowAction Forward -OverflowActionTarget $userAdeleID -OverflowThreshold 200 -TimeoutAction Forward -TimeoutActionTarget $userAdeleID -TimeoutThreshold 120 -RoutingMethod Attendant -ConferenceMode $true -User @($userSalesBillID, $userSalesMaryID) -LanguageID “en-US”
````

### <a name="get-license-types"></a>Получение типов лицензий
````
Get-MsolAccountSku
````

### <a name="create-and-assign-resource-account"></a>Создание и назначение учетной записи ресурса
Примечание. Телефон номер не требуется, так как очередь вызовов заканчивается автосекретарем
- ApplicationID
- - Автосекретарь: ce933385-9390-45d1-9512-c8d228074e07
- - Очередь вызовов: 11cd3e2e-fccb-42ad-ad00-878b93575e07

Примечание. Указанный ниже тип лицензии (PHONESYSTEM_VIRTUALUSER) должен быть указан командлетом Get-MsolAccountSku выше.

````
New-CsOnlineApplicationInstance -UserPrincipalName Sales-RA@contoso.com -DisplayName "Sales" -ApplicationID "11cd3e2e-fccb-42ad-ad00-878b93575e07"

Set-MsolUser -UserPrincipalName "Sales-RA@contoso.com" -UsageLocation US

Set-MsolUserLicense -UserPrincipalName “Sales-RA@contoso.com” -AddLicenses "contoso:PHONESYSTEM_VIRTUALUSER"

$applicationInstanceID = (Get-CsOnlineUser -Identity "Sales-RA@contoso.com").Identity
$callQueueID = (Get-CsCallQueue -NameFilter "Sales").Identity

New-CsOnlineApplicationInstanceAssociation -Identities @($applicationInstanceID) -ConfigurationID $callQueueID -ConfigurationType CallQueue
````


## <a name="support-queue"></a>Очередь поддержки
### <a name="create-audio-files"></a>Создание звуковых файлов
Замените "d:\\" путем к папке, в которой хранятся WAV-файлы на компьютере.

````
$content = Get-Content “d:\support-greeting.wav” -Encoding byte -ReadCount 0
$audioFileSupportGreetingID = (Import-CsOnlineAudioFile -ApplicationID HuntGroup -FileName "support-greeting.wav" -Content $content).ID

$content = Get-Content “d:\support-hold-in-queue-music.wav” -Encoding byte -ReadCount 0
$audioFileSupportHoldInQueueMusicID = (Import-CsOnlineAudioFile -ApplicationID HuntGroup -FileName "support-hold-in-queue-music.wav" -Content $content).ID

$content = Get-Content “d:\support-shared-voicemail-greeting.wav” -Encoding byte -ReadCount 0
$audioFileSupportSharedVoicemailGreetingID = (Import-CsOnlineAudioFile -ApplicationID HuntGroup -FileName "support-shared-voicemail-greeting.wav" -Content $content).ID
````

### <a name="get-support-team-group-id"></a>Получение идентификатора группы поддержки
````
$teamSupportID = (Get-Team -displayname "Support").GroupID
````

### <a name="get-list-of-supported-languages"></a>Получение списка поддерживаемых языков
````
Get-CsAutoAttendantSupportedLanguage
````

### <a name="create-call-queue"></a>Создание очереди вызовов
````
New-CsCallQueue -Name “Support” -AgentAlertTime 15 -AllowOptOut $false -DistributionLists $teamSupportID -WelcomeMusicAudioFileID $audioFileSupportGreetingID -MusicOnHoldAudioFileID $audioFileSupportHoldInQueueMusicID -OverflowAction SharedVoicemail -OverflowActionTarget $teamSupportID -OverflowThreshold 200 -OverflowSharedVoicemailAudioFilePrompt $audioFileSupportSharedVoicemailGreetingID -EnableOverflowSharedVoicemailTranscription $true -TimeoutAction SharedVoicemail -TimeoutActionTarget $teamSupportID -TimeoutThreshold 2700 -TimeoutSharedVoicemailTextToSpeechPrompt "We're sorry to have kept you waiting and are now transferring your call to voicemail." -EnableTimeoutSharedVoicemailTranscription $true -RoutingMethod LongestIdle -ConferenceMode $true -LanguageID “en-US”
````

### <a name="get-license-types"></a>Получение типов лицензий
````
Get-MsolAccountSku
````

### <a name="create-and-assign-resource-account"></a>Создание и назначение учетной записи ресурса
Примечание. Телефон номер не требуется, так как очередь вызовов является интерфейсной для автосекретаря
- ApplicationID
- - Автосекретарь: ce933385-9390-45d1-9512-c8d228074e07
- - Очередь вызовов: 11cd3e2e-fccb-42ad-ad00-878b93575e07

Примечание. Указанный ниже тип лицензии (PHONESYSTEM_VIRTUALUSER) должен быть указан командлетом Get-MsolAccountSku выше.

````
New-CsOnlineApplicationInstance -UserPrincipalName Support-RA@contoso.com -DisplayName "Support" -ApplicationID "11cd3e2e-fccb-42ad-ad00-878b93575e07"

Set-MsolUser -UserPrincipalName "Support-RA@contoso.com" -UsageLocation US

Set-MsolUserLicense -UserPrincipalName “Support-RA@contoso.com” -AddLicenses "contoso:PHONESYSTEM_VIRTUALUSER"

$applicationInstanceID = (Get-CsOnlineUser -Identity "Support-RA@contoso.com").Identity
$callQueueID = (Get-CsCallQueue -NameFilter "Support").Identity

New-CsOnlineApplicationInstanceAssociation -Identities @($applicationInstanceID) -ConfigurationID $callQueueID -ConfigurationType CallQueue
````


## <a name="facilities-collaborative-calling-queue"></a>Очередь совместных вызовов Facilities
### <a name="get-facilities-team-group-id"></a>Получение идентификатора группы Facilities
````
$teamFacilitiesGroupID = (Get-Team -DisplayName "Facilities").GroupID
````

### <a name="get-facilities-help-desk-team-channel-id"></a>Идентификатор канала группы технической поддержки Get Facilities
````
Get-TeamChannel -GroupId $teamFacilitiesGroupID
$teamFacilitiesHelpDeskChannelID = "{assign ID from output of above command}"
````

### <a name="get-facilities-help-desk-channel-owner-user-id"></a>Получение идентификатора пользователя владельца канала службы технической поддержки Средств
````
$teamFacilitiesHelpDeskChannelUserID = (Get-TeamChannelUser -GroupId $teamFacilitiesGroupID -DisplayName "Help Desk" -Role Owner).UserId
````

### <a name="get-on-behalf-of-calling-resource-account-id"></a>Получение от имени вызывающего идентификатора учетной записи ресурса
````
$oboResourceAccountID = (Get-CsOnlineUser -Identity "MainAA-RA@contoso.com").Identity
````

### <a name="get-list-of-supported-languages"></a>Получение списка поддерживаемых языков
````
Get-CsAutoAttendantSupportedLanguage
````

### <a name="create-call-queue"></a>Создание очереди вызовов
````
New-CsCallQueue -Name “Facilities” -AgentAlertTime 15 -AllowOptOut $false -ChannelId $teamFacilitiesHelpDeskChannelID -ChannelUserObjectId $teamFacilitiesHelpDeskChannelUserID  -ConferenceMode $true -DistributionList $teamFacilitiesGroupID -LanguageID “fr-FR” -OboResourceAccountIds $oboResourceAccountID -OverflowAction DisconnectWithBusy -OverflowThreshold 200 -RoutingMethod RoundRobin -TimeoutAction Disconnect -TimeoutThreshold 2700 -UseDefaultMusicOnHold $true 
````

### <a name="get-license-types"></a>Получение типов лицензий
````
Get-MsolAccountSku
````

### <a name="create-and-assign-resource-account"></a>Создание и назначение учетной записи ресурса
Примечание. Телефон номер не требуется, так как очередь вызовов является интерфейсной для автосекретаря
- ApplicationID
- - Автосекретарь: ce933385-9390-45d1-9512-c8d228074e07
- - Очередь вызовов: 11cd3e2e-fccb-42ad-ad00-878b93575e07

Примечание. Указанный ниже тип лицензии (PHONESYSTEM_VIRTUALUSER) должен быть указан командлетом Get-MsolAccountSku выше.

````
New-CsOnlineApplicationInstance -UserPrincipalName Facilities-RA@contoso.com -DisplayName "Facilities" -ApplicationID "11cd3e2e-fccb-42ad-ad00-878b93575e07"

Set-MsolUser -UserPrincipalName "Facilities-RA@contoso.com" -UsageLocation US

Set-MsolUserLicense -UserPrincipalName “Facilities-RA@contoso.com” -AddLicenses "contoso:PHONESYSTEM_VIRTUALUSER"

$applicationInstanceID = (Get-CsOnlineUser -Identity "Facilities-RA@contoso.com").Identity
$callQueueID = (Get-CsCallQueue -NameFilter "Facilities").Identity

New-CsOnlineApplicationInstanceAssociation -Identities @($applicationInstanceID) -ConfigurationID $callQueueID -ConfigurationType CallQueue
````
