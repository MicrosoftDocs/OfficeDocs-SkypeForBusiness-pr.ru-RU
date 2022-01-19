---
title: Создание очереди вызовов с помощью cmdlets
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
description: Узнайте, как настроить очереди вызовов с помощью cmdlets
ms.openlocfilehash: 8ffbef5541a230755bb7439507e3002a5cb92462
ms.sourcegitcommit: 268660f101609852f02f3f9d1a8436f2a99dade7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2022
ms.locfileid: "62071118"
---
# <a name="create-a-call-queue-via-cmdlets"></a>Создание очереди вызовов с помощью cmdlets

## <a name="assumptions"></a>Предположения
1)  На компьютере установлена powerShell
- Настройка компьютера для [Windows PowerShell](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
- Модуль MSTeams установлен ````  (Install-Module -Name MicrosoftTeams -Force -AllowClobber) ````
- Модуль MSOnline установлен ```` Install-Module -Name MSOnline -Force -AllowClobber ````
2)  У вас есть права на администрирование клиента
3)  Вы приобрели Microsoft Teams Телефон
4)  Агенты, списки рассылки и Teams каналы, на которые ссылается ниже, уже созданы

Примечание. Командлет Teams Channel, используемый ниже, является частью общедоступных предварительных версий Teams PowerShell.  Дополнительные сведения см. в Teams предварительной версии [PowerShell](teams-powershell-install.md) и заметках о выпуске [PowerShell Microsoft Teams PowerShell.](teams-powershell-release-notes.md)

Пользователям, у которых уже установлен модуль MicrosoftTeams, необходимо установить наиболее новую ````Update-Module MicrosoftTeams```` версию.


## <a name="scenario"></a>Сценарий

Будут созданы три очереди вызовов:

Сведения о очереди вызовов продаж:
- При найме автозавода: Да
- Прямые вызовы из ОКП: Нет
- Язык: английский (США)
- Приветствие: нет
- Музыка при удержании: звуковые файлы
- - Filename: sales-hold-in-queue-music.wav
- Ответы на звонки: пользователи
- - Bill@contoso.com
- - Mary@contoso.com
- Режим конференции: в режиме
- Способ маршрутинга: Attendant
- Маршруты на основе присутствия: Выключите
- Агенты звонков могут отказаться от приема звонков: Да
- Время оповещения агента звонка: 15
- Обработка переполнения вызовов: 200
- - Перенаправить на: Adele@contoso.com
- Обработка времени вызова: 120 секунд
- - Перенаправить на: Adele@contoso.com

Сведения об очереди вызовов службы поддержки:
- При найме автозавода: Да
- Прямые вызовы из ОКП: Нет
-   Язык: английский (Соединенное Королевство)
-   Приветствие: звуковые файлы
-   - Имя файла: support-greeting.wav
-   Музыка при удержании: звуковые файлы
-   - Имя файла: support-hold-in-queue-music.wav
-   Ответ на звонки: список рассылки поддержки
-   - Support@contoso.com
-   Режим конференции: в режиме
-   Способ маршрутиста: longest Idle
-   Маршруты на основе присутствия: N/A — по умолчанию в сети из-за самой длинной неавтомайтной
-   Агенты звонков могут отказаться от приема звонков: Нет
-   Время оповещения агента звонка: 15
-   Обработка переполнения вызовов: 200
-   - Перенаправление: поддержка общей голосовой почты
- - -   Звуковые файлы (support-shared-voicemail-greeting.wav)
- - -   Транскрибация включена
-   Обработка времени вызова: 45 минут
-   - Перенаправление: поддержка общей голосовой почты
- - - TTS: "К сожалению, мы не можем ждать, а теперь перена можем перевести звонок на голосовую почту".
- - - Транскрибация включена


Сведения о очереди для совместной работы с помещениями:
- Fronted by Auto Attendant: No
- Прямые вызовы из ДНР: Нет (только внутренние вызовы)
-   Язык: французский (FR)
-   Приветствие: нет
-   Музыка при удержании: по умолчанию
-   Ответ на звонки: Группа: помещения
-   Канал ответа на звонки: службы поддержки
-   - Владелец канала: Fred@contoso.com
-   Режим конференции: в режиме
-   Способ маршрутии: Округл Илья
-   Маршруты на основе присутствия: В сети
-   Агенты звонков могут отказаться от приема звонков: Нет
-   Время оповещения агента звонка: 15
-   Обработка переполнения вызовов: 200
-   - Отключить
-   Обработка времени вызова: 45 минут
-   - Отключить


## <a name="login"></a>Вход
Вам будет предложено ввести свои учетные данные Teams администратора.
```
$credential = Get-Credential
Connect-MicrosoftTeams -Credential $credential
Connect-MsolService -Credential $credential
````

## <a name="sales-queue"></a>Очередь продаж
### <a name="create-audio-files"></a>Создание звуковых файлов
Замените "d:" путем к месту хранения \\ WAV-файлов на компьютере.

````
$content = Get-Content “d:\sales-hold-in-queue-music.wav” -Encoding byte -ReadCount 0
$audioFileSalesHoldInQueueMusicID = (Import-CsOnlineAudioFile -ApplicationID HuntGroup -FileName "sales-hold-in-queue-music.wav" -Content $content).ID
````

### <a name="get-users-id"></a>Получить ИД пользователей
````
$userAdeleID = (Get-CsOnlineUser -Identity “sip:adele@contoso.com”).ObjectID
$userSalesBillID = (Get-CsOnlineUser -Identity “sip:bill@contoso.com”).ObectID
$userSalesMaryID = (Get-CsOnlineUser -Identity “sip:mary@contoso.com”).ObjectID
````

### <a name="get-list-of-supported-languages"></a>Получить список поддерживаемых языков
````
Get-CsAutoAttendantSupportedLanguage
````

### <a name="create-call-queue"></a>Создание очереди вызовов
````
New-CsCallQueue -Name “Sales” -AgentAlertTime 15 -AllowOptOut $true -MusicOnHoldAudioFileID $audioFileSalesHoldInQueueMusicID -OverflowAction Forward -OverflowActionTarget $userAdeleID -OverflowThreshold 200 -TimeoutAction Forward -TimeoutActionTarget $userAdeleID -TimeoutThreshold 120 -RoutingMethod Attendant -ConferenceMode $true -User @($userSalesBillID, $userSalesMaryID) -LanguageID “en-US”
````

### <a name="get-license-types"></a>Получить типы лицензий
````
Get-MsolAccountSku
````

### <a name="create-and-assign-resource-account"></a>Создание и назначение учетной записи ресурса
Примечание. Телефон номер, который здесь не требуется, так как очередь вызовов заканчивается автоотехнщиком
- ApplicationID
- - Автоотчет: ce933385-9390-45d1-9512-c8d228074e07
- - Очередь вызовов: 11cd3e2e-fccb-42ad-ad00-878b93575e07

````
New-CsOnlineApplicationInstance -UserPrincipalName Sales-RA@contoso.com -DisplayName "Sales" -ApplicationID "11cd3e2e-fccb-42ad-ad00-878b93575e07"

Set-MsolUser -UserPrincipalName "Sales-RA@contoso.com" -UsageLocation US

Set-MsolUserLicense -UserPrincipalName “Sales-RA@contoso.com” -AddLicenses "contoso:PHONESYSTEM_VIRTUALUSER"

$applicationInstanceID = (Get-CsOnlineUser -Identity "Sales-RA@contoso.com").ObjectID
$callQueueID = (Get-CsCallQueue -NameFilter "Sales").Identity

New-CsOnlineApplicationInstanceAssociation -Identities @($applicationInstanceID) -ConfigurationID $callQueueID -ConfigurationType CallQueue
````


## <a name="support-queue"></a>Очередь поддержки
### <a name="create-audio-files"></a>Создание звуковых файлов
Замените "d:" путем к месту хранения \\ WAV-файлов на компьютере.

````
$content = Get-Content “d:\support-greeting.wav” -Encoding byte -ReadCount 0
$audioFileSupportGreetingID = (Import-CsOnlineAudioFile -ApplicationID HuntGroup -FileName "support-greeting.wav" -Content $content).ID

$content = Get-Content “d:\support-hold-in-queue-music.wav” -Encoding byte -ReadCount 0
$audioFileSupportHoldInQueueMusicID = (Import-CsOnlineAudioFile -ApplicationID HuntGroup -FileName "support-hold-in-queue-music.wav" -Content $content).ID

$content = Get-Content “d:\support-shared-voicemail-greeting.wav” -Encoding byte -ReadCount 0
$audioFileSupportSharedVoicemailGreetingID = (Import-CsOnlineAudioFile -ApplicationID HuntGroup -FileName "support-shared-voicemail-greeting.wav" -Content $content).ID
````

### <a name="get-support-team-group-id"></a>Получить ИД группы поддержки
````
$teamSupportID = (Get-Team -displayname "Support").GroupID
````

### <a name="get-list-of-supported-languages"></a>Получить список поддерживаемых языков
````
Get-CsAutoAttendantSupportedLanguage
````

### <a name="create-call-queue"></a>Создание очереди вызовов
````
New-CsCallQueue -Name “Support” -AgentAlertTime 15 -AllowOptOut $false -DistributionLists $teamSupportID -WelcomeMusicAudioFileID $audioFileSupportGreetingID -MusicOnHoldAudioFileID $audioFileSupportHoldInQueueMusicID -OverflowAction SharedVoicemail -OverflowActionTarget $teamSupportID -OverflowThreshold 200 -OverflowSharedVoicemailAudioFilePrompt $audioFileSupportSharedVoicemailGreetingID -EnableOverflowSharedVoicemailTranscription $true -TimeoutAction SharedVoicemail -TimeoutActionTarget $teamSupportID -TimeoutThreshold 2700 -TimeoutSharedVoicemailTextToSpeechPrompt "We're sorry to have kept you waiting and are now transferring your call to voicemail." -EnableTimeoutSharedVoicemailTranscription $true -RoutingMethod LongestIdle -ConferenceMode $true -LanguageID “en-US”
````

### <a name="get-license-types"></a>Получить типы лицензий
````
Get-MsolAccountSku
````

### <a name="create-and-assign-resource-account"></a>Создание и назначение учетной записи ресурса
Примечание. Телефон номер, не требующийся здесь, так как автоотека с номером перед очереди вызовов перенастройка
- ApplicationID
- - Автоотчет: ce933385-9390-45d1-9512-c8d228074e07
- - Очередь вызовов: 11cd3e2e-fccb-42ad-ad00-878b93575e07
````
New-CsOnlineApplicationInstance -UserPrincipalName Support-RA@contoso.com -DisplayName "Support" -ApplicationID "11cd3e2e-fccb-42ad-ad00-878b93575e07"

Set-MsolUser -UserPrincipalName "Support-RA@contoso.com" -UsageLocation US

Set-MsolUserLicense -UserPrincipalName “Support-RA@contoso.com” -AddLicenses "contoso:PHONESYSTEM_VIRTUALUSER"

$applicationInstanceID = (Get-CsOnlineUser -Identity "Support-RA@contoso.com").ObjectID
$callQueueID = (Get-CsCallQueue -NameFilter "Support").Identity

New-CsOnlineApplicationInstanceAssociation -Identities @($applicationInstanceID) -ConfigurationID $callQueueID -ConfigurationType CallQueue
````


## <a name="facilities-collaborative-calling-queue"></a>Очередь для совместной работы с помещениями
### <a name="get-facilities-team-group-id"></a>Get Facilities team group ID
````
$teamFacilitiesGroupID = (Get-Team -DisplayName "Facilities").GroupID
````

### <a name="get-facilities-help-desk-team-channel-id"></a>Get Facilities Help Desk team channel ID
````
Get-TeamChannel -GroupId $teamFacilitiesGroupID
$teamFacilitiesHelpDeskChannelID = "{assign ID from output of above command}"
````

### <a name="get-facilities-help-desk-channel-ower-user-id"></a>ИД пользователя службы поддержки для канала Get Facilities
````
$teamFacilitiesHelpDeskChannelUserID = (Get-TeamChannelUser -GroupId $teamFacilitiesGroupID -DisplayName "Help Desk" -Role Owner).UserId
````

### <a name="get-on-behalf-of-calling-resource-account-id"></a>Получить от имени ИД учетной записи ресурса для звонков
````
$oboResourceAccountID = (Get-CsOnlineUser -Identity "MainAA-RA@contoso.com").ObjectID
````

### <a name="get-list-of-supported-languages"></a>Получить список поддерживаемых языков
````
Get-CsAutoAttendantSupportedLanguage
````

### <a name="create-call-queue"></a>Создание очереди вызовов
````
New-CsCallQueue -Name “Facilities” -AgentAlertTime 15 -AllowOptOut $false -ChannelId $teamFacilitiesHelpDeskChannelID -ChannelUserObjectId $teamFacilitiesHelpDeskChannelUserID  -ConferenceMode $true -DistributionList $teamFacilitiesGroupID -LanguageID “fr-FR” -OboResourceAccountIds $oboResourceAccountID -OverflowAction DisconnectWithBusy -OverflowThreshold 200 -RoutingMethod RoundRobin -TimeoutAction Disconnect -TimeoutThreshold 2700 -UseDefaultMusicOnHold $true 
````

### <a name="get-license-types"></a>Получить типы лицензий
````
Get-MsolAccountSku
````

### <a name="create-and-assign-resource-account"></a>Создание и назначение учетной записи ресурса
Примечание. Телефон номер, не требующийся здесь, так как автоотека с номером перед очереди вызовов перенастройка
- ApplicationID
- - Автоотчет: ce933385-9390-45d1-9512-c8d228074e07
- - Очередь вызовов: 11cd3e2e-fccb-42ad-ad00-878b93575e07
````
New-CsOnlineApplicationInstance -UserPrincipalName Support-RA@contoso.com -DisplayName "Facilities" -ApplicationID "11cd3e2e-fccb-42ad-ad00-878b93575e07"

Set-MsolUser -UserPrincipalName "Facilities-RA@contoso.com" -UsageLocation US

Set-MsolUserLicense -UserPrincipalName “Facilities-RA@contoso.com” -AddLicenses "contoso:PHONESYSTEM_VIRTUALUSER"

$applicationInstanceID = (Get-CsOnlineUser -Identity "Facilities-RA@contoso.com").ObjectID
$callQueueID = (Get-CsCallQueue -NameFilter "Facilities").Identity

New-CsOnlineApplicationInstanceAssociation -Identities @($applicationInstanceID) -ConfigurationID $callQueueID -ConfigurationType CallQueue
````
