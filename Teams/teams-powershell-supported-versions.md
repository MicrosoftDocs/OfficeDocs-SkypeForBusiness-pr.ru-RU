---
title: Модуль Teams PowerShell — поддерживаемые версии
author: pbafna03
ms.author: pbafna
ms.reviewer: pbafna
manager: sshastri
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Сведения о версиях, поддерживаемых модулем Teams PowerShell, используемым для администрирования Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5ae244a16e934b70085b2193bee3ef21a277f7ed
ms.sourcegitcommit: 46dbff43eec9631863b74b2b49c9a29c6497d8e8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/20/2022
ms.locfileid: "67397290"
---
# <a name="teams-powershell-module---supported-versions"></a>Модуль Teams PowerShell — поддерживаемые версии

Сейчас поддерживаются только версии модуля Microsoft Teams PowerShell (TPM) серии 4.x.x или более поздней версии. Все предыдущие версии полностью прекращены с 15 июня 2022 г. & перестанут работать (сообщение центра сообщений для справки — MC350371). 

Рекомендуется выполнить обновление до последней версии модуля Teams PowerShell.


## <a name="important-notes"></a>Важные примечания

- Заметки о выпуске для всех версий модулей Teams PowerShell можно найти в заметках о [выпуске Teams PowerShell](teams-powershell-release-notes.md).

- Чтобы обновить любой модуль PowerShell, следует использовать тот же метод, который использовался для установки модуля. Например, если вы изначально использовали Install-Module, для получения последней версии следует использовать [Update-Module](/powershell/module/powershellget/update-module) .

  ```powershell
  Update-Module MicrosoftTeams
  ```

- При обновлении с модуля Teams PowerShell версии 1.1.6 обновите скрипты для использования `Connect-MicrosoftTeams` `New-CsOnlineSession`вместо .

- Во время обновления не рекомендуется использовать TPM 4.x.x/3.x.x вместе с версиями, предшествующими 3.0.0. Например, не рекомендуется использовать версии 4.x.x & 2.6.0 для различных операций администрирования в одной организации.

- Связанные изменения
  - Обновления в Get-CsOnlineUser & Get-CsOnlineVoiceUser TPM 3.x.x и более поздних версий — дополнительные сведения см. в статье [Get-CsOnlineUser](/powershell/module/skype/get-csonlineuser) & [Get-CsOnlineVoiceUser](/powershell/module/skype/get-csonlinevoiceuser) (публикация центра сообщений — MC340774).

  - Изменения, внесенные в назначение номера телефона — дополнительные сведения в [Set-CsUser](/powershell/module/skype/set-csuser), [Set-CsOnlineVoiceUser](/powershell/module/skype/set-csonlinevoiceuser), [Set-CsOnlineApplicationInstance](/powershell/module/skype/set-csonlineapplicationinstance) & [Set-CsOnlineVoiceApplicationInstance](/powershell/module/skype/set-csonlinevoiceapplicationinstance) (message center post – MC316139).

  - Изменения параметров в Get-CsTenant — дополнительные сведения в [Get-CsTenant](/powershell/module/skype/get-cstenant) (сообщение центра сообщений — MC365397).
  
  - Если в скриптах используются командлеты New/Set of Policy или Configuration с параметрами типа PSListModifier, рекомендуется использовать последнюю версию (4.2.0 или более позднюю). Запись центра сообщений для справки — MC397428.

  - [Новое| Командлеты Get]-CsCloudCallDataConnection теперь поддерживаются в версиях 4.6.0 или более поздней (публикация центра сообщений — MC408993).

- При использовании TPM 4.x.x или более поздней версии не рекомендуется использовать ни один из нерекомендуемых или неподдерживаемых командлетов, упомянутых [ниже](#deprecated-cmdlets).

## <a name="deprecated-cmdlets"></a>Нерекомендуемые командлеты

- Ниже перечислены некоторые командлеты, которые были нерекомендуемыми. Подробные сведения об этом можно найти в соответствующей общедоступной документации.
  - [Get-CsOnlineTelephoneNumber](/powershell/module/skype/get-csonlinetelephonenumber)
  - [Get-CsOnlineDialInConferencingUserInfo](/powershell/module/skype/get-csonlinedialinconferencinguserinfo), [Get-CsOnlineDialInConferencingUserState](/powershell/module/skype/get-csonlinedialinconferencinguserstate), [Enable-CsOnlineDialInConferencingUser](/powershell/module/skype/enable-csonlinedialinconferencinguser), [Disable-CsOnlineDialInConferencingUser](/powershell/module/skype/disable-csonlinedialinconferencinguser)
  - [Get-CsOnlineDirectoryTenant](/powershell/module/skype/get-csonlinedirectorytenant)
  - [New-CsOnlineAudioFile](/powershell/module/skype/new-csonlineaudiofile)
  - [Get-CsOnlineApplicationEndpoint](/powershell/module/skype/get-csonlineapplicationendpoint), [Set-CsOnlineApplicationEndpoint](/powershell/module/skype/set-csonlineapplicationendpoint), [New-CsOnlineApplicationEndpoint](/powershell/module/skype/new-csonlineapplicationendpoint), [Remove-CsOnlineApplicationEndpoint](/powershell/module/skype/remove-csonlineapplicationendpoint), Switch-CsOnlineApplicationEndpoint
  - [Get-CsOnlineTelephoneNumberInventoryCities](/powershell/module/skype/get-csonlinetelephonenumberinventorycities), [Get-CsOnlineTelephoneNumberInventoryAreas](/powershell/module/skype/get-csonlinetelephonenumberinventoryareas), [Get-CsOnlineTelephoneNumberInventoryCountries](/powershell/module/skype/get-csonlinetelephonenumberinventorycountries), [Get-CsOnlineTelephoneNumberInventoryRegions](/powershell/module/skype/get-csonlinetelephonenumberinventoryregions), [Get-CsOnlineTelephoneNumberInventoryTypes](/powershell/module/skype/get-csonlinetelephonenumberinventorytypes), [Search-CsOnlineTelephoneNumberInventory](/powershell/module/skype/search-csonlinetelephonenumberinventory), [Select-CsOnlineTelephoneNumberInventory](/powershell/module/skype/select-csonlinetelephonenumberinventory), [Get-CsOnlineTelephoneNumberAvailableCount](/powershell/module/skype/get-csonlinetelephonenumberavailablecount), [ Clear-CsOnlineTelephoneNumberReservation](/powershell/module/skype/clear-csonlinetelephonenumberreservation), [Get-CsOnlineTelephoneNumberReservationsInformation](/powershell/module/skype/get-csonlinetelephonenumberreservationsinformation), [Get-CsOnlineDirectoryTenantNumberCities](/powershell/module/skype/get-csonlinedirectorytenantnumbercities)
  - [Set-CsTeamsAppSetupPolicy](/powershell/module/skype/set-csteamsappsetuppolicy), [New-CsTeamsAppSetupPolicy](/powershell/module/skype/new-csteamsappsetuppolicy), [Set-CsTeamsAppPermissionPolicy](/powershell/module/skype/set-csteamsapppermissionpolicy), [New-CsTeamsAppPermissionPolicy](/powershell/module/skype/new-csteamsapppermissionpolicy)
  - [Test-CsOnlineLisCivicAddress](/powershell/module/skype/test-csonlineliscivicaddress)

- Ниже перечислены командлеты, которые не поддерживаются и не относятся к сценариям Microsoft Teams.
  - [Get| Set]-CsUserPstnSettings
  - [Get| Задать| Включить| Disable]-CsMeetingRoom
  - [Предоставить| Get| Задать| Новое| Remove]-CsConferencingPolicy
  - [Предоставить| Get| Задать| Новое| Remove]-CsClientPolicy
  - [Предоставить| Get]-CsHostedVoicemailPolicy
  - [Предоставить| Get| Задать| Новое| Remove]-CsMobilityPolicy
  - [Предоставить| Get]-CsVoiceRoutingPolicy
  - [Предоставить| Get]-CsBroadcastMeetingPolicy
  - [Предоставить| Get]-CsCloudMeetingPolicy
  - [Предоставить| Get]-CsGraphPolicy
  - [Предоставить| Get| Задать| Новое| Remove]-CsExternalUserCommunicationPolicy
  - [Предоставить| Get| Set]-CsIPPhonePolicy
  - Get-CsUserServicesPolicy
  - [Get| Set]-CsBroadcastMeetingConfiguration
  - [Get| Set]-CsOAuthConfiguration
  - [Get| Set]-CsMeetingConfiguration
  - [Get| Set]-CsTenantHybridConfiguration
  - [Get| Set]-CsPushNotificationConfiguration
  - [Get| Set]-CsUCPhoneConfiguration
  - Get-CsImFilterConfiguration
  - Get-CsAudioConferencingProvider
  - [Get| Set]-CsTenantPublicProvider
  - Get-CsHostingProvider
  - [Get| Задать| Регистрация| Unregister]-CsHybridPSTNAppliance
  - [Get| Задать| Новое| Remove]-CsHybridPSTNSite
  - [Get| Set]-CsHybridMediationServer
  - [Get| Задать| Новое| Remove]-CsTenantUpdateTimeWindow
  - Get-CsUserLocationStatus
  - Invoke-CsUcsRollback
  - [Get| Задать| Новое| Remove]-CsTeamsPinnedApp
  - [Get| Задать| Новое| Remove]-CsTenantCatalogApp
  - [Get| Задать| Новое| Remove]-CsGlobalCatalogApp
  - [Get| Задать| Новое| Remove]-CsDefaultCatalogApp
  - [Get| Задать| Новое| Remove]-CsTeamsAppPreset
  - Invoke-CsUserPreferredDataLocationSync
  - [Get| Set]-CsTeamsUpgradeStatus
  - Grant-CsPolicy
  - Set-CsOnlineDirectoryUser

## <a name="related-topics"></a>См. также

[Заметки о выпуске Teams PowerShell](teams-powershell-release-notes.md)

[Установка Microsoft Teams PowerShell](teams-powershell-install.md)

[Управление Teams с помощью Teams PowerShell](teams-powershell-managing-teams.md)

[Справочник по командлетам Microsoft Teams](/powershell/module/teams)

[Skype для бизнеса командлета](/powershell/module/skype)
