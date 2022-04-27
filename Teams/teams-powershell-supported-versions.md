---
title: Teams PowerShell — поддерживаемые версии
author: pbafna03
ms.author: pbafna
ms.reviewer: pbafna
manager: sshastri
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Сведения о версиях, поддерживаемых Teams PowerShell, используемом для администрирования Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: c97e3c840452a20be60d6f27e2bf4c3375322be1
ms.sourcegitcommit: bd05783dfb33a63e0eb083a2135f97d110dc81a3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2022
ms.locfileid: "65059420"
---
# <a name="teams-powershell-module---supported-versions"></a>Teams PowerShell — поддерживаемые версии

Microsoft Teams версии модуля PowerShell (TPM) в серии 4.x.x или более поздней версии будут единственными поддерживаемыми в будущем. Все более ранние версии находятся в пути прекращения использования. Рекомендуется обновить модуль Teams PowerShell до последней версии.



## <a name="new-organizations"></a>Новые организации

Организации, недавно подключенные к Teams, смогут использовать модуль PowerShell Teams только в серии 4.x.x или более поздней версии, начиная с 1 апреля 2022 г.



## <a name="current-organizations-non-tpm-active"></a>Текущие организации (не активные TPM)

Организации, которые не использовали модуль Teams PowerShell в течение последних трех месяцев (с 22 января по 22 марта), смогут использовать модуль Teams PowerShell в серии 4.x.x или более поздней версии, начиная с 1 апреля 2022 г.



## <a name="current-organizations-tpm-active"></a>Текущие организации (активный TPM)

Организации, использующие модуль PowerShell Teams за последние три месяца (с 22 января по 22 января), смогут использовать модуль PowerShell Teams только в серии 4.x.x или более поздней версии, начиная с 15 июня 2022 г. Запись центра сообщений для справки — MC350371. 



## <a name="important-notes"></a>Важные примечания

- Заметки о выпуске Teams версий модуля PowerShell можно найти в Teams [заметках о выпуске PowerShell](teams-powershell-release-notes.md).

- Чтобы обновить любой модуль PowerShell, следует использовать тот же метод, который использовался для установки модуля. Например, если вы изначально использовали Install-Module, для получения последней версии следует использовать [Update-Module](/powershell/module/powershellget/update-module) .  

  ```powershell
  Update-Module MicrosoftTeams
  ```

-   При обновлении Teams PowerShell версии 1.1.6 обновите `Connect-MicrosoftTeams` скрипты для использования `New-CsOnlineSession`вместо .

-   Во время обновления не рекомендуется использовать TPM 4.x.x/3.x.x вместе с версиями, предшествующими 3.0.0. Например, не рекомендуется использовать версии 4.x.x & 2.6.0 для различных операций администрирования в одной организации. 

- Связанные изменения
  * Обновления для Get-CsOnlineUser & Get-CsOnlineVoiceUser TPM 3.x.x и более поздних версий — дополнительные сведения см. в [статье Get-CsOnlineUserGet-CsOnlineVoiceUser](/powershell/module/skype/get-csonlineuser) &  (публикация центра сообщений — MC340774).[](/powershell/module/skype/get-csonlinevoiceuser)

  * Изменения, поступающие Телефон номеров — дополнительные сведения в [Set-CsUser](/powershell/module/skype/set-csuser), [Set-CsOnlineVoiceUser](/powershell/module/skype/set-csonlinevoiceuser), [Set-CsOnlineApplicationInstanceSet-CsOnlineVoiceApplicationInstance](/powershell/module/skype/set-csonlineapplicationinstance) &  (message center post — MC316139).[](/powershell/module/skype/set-csonlinevoiceapplicationinstance)
  
  * Изменения параметров в Get-CsTenant — дополнительные сведения [в Get-CsTenant](/powershell/module/skype/get-cstenant).  

-   При использовании TPM 4.x.x или более поздней версии не рекомендуется использовать ни один из нерекомендуемых или неподдерживаемых командлетов, упомянутых [ниже](#deprecated-cmdlets). 



## <a name="deprecated-cmdlets"></a>Нерекомендуемые командлеты

- Ниже перечислены некоторые командлеты, которые были нерекомендуемыми. Подробные сведения об этом можно найти в соответствующей общедоступной документации. 
  * [Get-CsOnlineTelephoneNumber](/powershell/module/skype/get-csonlinetelephonenumber)
  * [Get-CsOnlineDialInConferencingUserInfo](/powershell/module/skype/get-csonlinedialinconferencinguserinfo), [Get-CsOnlineDialInConferencingUserState](/powershell/module/skype/get-csonlinedialinconferencinguserstate), [Enable-CsOnlineDialInConferencingUser](/powershell/module/skype/enable-csonlinedialinconferencinguser), [Disable-CsOnlineDialInConferencingUser](/powershell/module/skype/disable-csonlinedialinconferencinguser)
  * [Get-CsOnlineDirectoryTenant](/powershell/module/skype/get-csonlinedirectorytenant)
  * [New-CsOnlineAudioFile](/powershell/module/skype/new-csonlineaudiofile)
  * [Get-CsOnlineApplicationEndpoint](/powershell/module/skype/get-csonlineapplicationendpoint), [Set-CsOnlineApplicationEndpoint](/powershell/module/skype/set-csonlineapplicationendpoint), [New-CsOnlineApplicationEndpoint](/powershell/module/skype/new-csonlineapplicationendpoint), [Remove-CsOnlineApplicationEndpoint](/powershell/module/skype/remove-csonlineapplicationendpoint)
  * [Get-CsOnlineTelephoneNumberInventoryCities](/powershell/module/skype/get-csonlinetelephonenumberinventorycities), [Get-CsOnlineTelephoneNumberInventoryAreas](/powershell/module/skype/get-csonlinetelephonenumberinventoryareas), [Get-CsOnlineTelephoneNumberInventoryCountries](/powershell/module/skype/get-csonlinetelephonenumberinventorycountries), [Get-CsOnlineTelephoneNumberInventoryRegions](/powershell/module/skype/get-csonlinetelephonenumberinventoryregions), [Get-CsOnlineTelephoneNumberInventoryTypes](/powershell/module/skype/get-csonlinetelephonenumberinventorytypes), [Search-CsOnlineTelephoneNumberInventory](/powershell/module/skype/search-csonlinetelephonenumberinventory), [Select-CsOnlineTelephoneNumberInventory](/powershell/module/skype/select-csonlinetelephonenumberinventory), [Get-CsOnlineTelephoneNumberAvailableCount](/powershell/module/skype/get-csonlinetelephonenumberavailablecount), [ Clear-CsOnlineTelephoneNumberReservation](/powershell/module/skype/clear-csonlinetelephonenumberreservation), [Get-CsOnlineTelephoneNumberReservationsInformation](/powershell/module/skype/get-csonlinetelephonenumberreservationsinformation), [Get-CsOnlineDirectoryTenantNumberCities](/powershell/module/skype/get-csonlinedirectorytenantnumbercities)  
  * [Set-CsTeamsAppSetupPolicy](/powershell/module/skype/set-csteamsappsetuppolicy), [New-CsTeamsAppSetupPolicy](/powershell/module/skype/new-csteamsappsetuppolicy), [Set-CsTeamsAppPermissionPolicy](/powershell/module/skype/set-csteamsapppermissionpolicy), [New-CsTeamsAppPermissionPolicy](/powershell/module/skype/new-csteamsapppermissionpolicy)
  * [Test-CsOnlineLisCivicAddress](/powershell/module/skype/test-csonlineliscivicaddress)


- Ниже перечислены командлеты, которые не поддерживаются или Microsoft Teams сценариях. 
  * [Get| Set]-CsUserPstnSettings
  * [Get| Задать| Включить| Disable]-CsMeetingRoom
  * [Предоставить| Get| Задать| Новое| Remove]-CsConferencingPolicy
  * [Предоставить| Get| Задать| Новое| Remove]-CsClientPolicy
  * [Предоставить| Get]-CsHostedVoicemailPolicy
  * [Предоставить| Get| Задать| Новое| Remove]-CsMobilityPolicy
  * [Предоставить| Get] CsVoiceRoutingPolicy
  * [Предоставить| Get]-CsBroadcastMeetingPolicy
  * [Предоставить| Get]-CsCloudMeetingPolicy
  * [Предоставить| Get]-CsGraphPolicy
  * [Предоставить| Get| Задать| Новое| Remove]-CsExternalUserCommunicationPolicy
  * [Предоставить| Get| Set]-CsIPPhonePolicy
  * Get-CsUserServicesPolicy
  * [Get| Set]-CsBroadcastMeetingConfiguration
  * [Get| Set]-CsOAuthConfiguration
  * [Get| Set]-CsMeetingConfiguration
  * [Get| Set]-CsTenantHybridConfiguration
  * [Get| Set]-CsPushNotificationConfiguration
  * [Get| Set]-CsUCPhoneConfiguration
  * Get-CsImFilterConfiguration
  * Get-CsAudioConferencingProvider
  * [Get| Set]-CsTenantPublicProvider
  * Get-CsHostingProvider
  * [Get| Задать| Регистрация| Unregister]-CsHybridPSTNAppliance
  * [Get| Задать| Новое| Remove]-CsHybridPSTNSite
  * [Get| Set]- CsHybridMediationServer
  * [Get| Задать| Новое| Remove]-CsTenantUpdateTimeWindow
  * Get-CsUserLocationStatus
  * Invoke-CsUcsRollback
  * [Get| Задать| Новое| Remove]-CsTeamsPinnedApp
  * [Get| Задать| Новое| Remove]-CsTenantCatalogApp
  * [Get| Задать| Новое| Remove]-CsGlobalCatalogApp
  * [Get| Задать| Новое| Remove]-CsDefaultCatalogApp
  * [Get| Задать| Новое| Remove]-CsTeamsAppPreset



## <a name="related-topics"></a>Статьи по теме

[Teams о выпуске PowerShell](teams-powershell-release-notes.md)

[Установка Microsoft Teams PowerShell](teams-powershell-install.md)

[Управление Teams с Teams PowerShell](teams-powershell-managing-teams.md)

[Microsoft Teams командлета](/powershell/module/teams) 

[Skype для бизнеса командлета](/powershell/module/skype) 
