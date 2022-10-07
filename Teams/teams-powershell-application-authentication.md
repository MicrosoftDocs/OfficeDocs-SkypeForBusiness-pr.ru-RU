---
title: Проверка подлинности на основе приложений в модуле Teams PowerShell
author: pbafna03
ms.author: pbafna
ms.reviewer: pbafna
manager: sshastri
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Сведения о проверке подлинности на основе приложений в модуле Teams PowerShell, используемом для администрирования Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7dab0f32a6547db5522f00d4750f7eff26ea5995
ms.sourcegitcommit: 43db97b84ca70b1e6accfa7214d4106e4177a642
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/29/2022
ms.locfileid: "68218093"
---
# <a name="application-based-authentication-in-teams-powershell-module"></a>Проверка подлинности на основе приложений в модуле Teams PowerShell

Проверка подлинности на основе приложений теперь поддерживается в модуле Teams PowerShell для ограниченного набора командлетов в предварительной версии с версией 4.7.1 или более поздней. В настоящее время этот режим проверки подлинности поддерживается только в коммерческих средах.


## <a name="cmdlets-supported"></a>Поддерживаемые командлеты

Приведенные ниже командлеты уже поддерживаются, другие командлеты будут постепенно развернуты. 

  - Командлеты \*, отличные от CS (например, Get-Team)
  - Get-CsTenant
  - Get-CsOnlineUser, Get-CsOnlineVoiceUser
  - \*-CsOnlineSipDomain 
  - \*-CsPhoneNumberAssignment
  - \*-CsOnlineTelephoneNumberOrder, Get-CsOnlineTelephoneNumberType, Get-CsOnlineTelephoneNumberCountry
  - \*-CsCallQueue
  - \*-CsAutoAttendant, \*-CsAutoAttendant\*
  - \*-CsOnlineVoicemailUserSettings
  - Find-CsOnlineApplicationInstance, \*-CsOnlineApplicationInstanceAssociation, Get-CsOnlineApplicationInstanceAssociationStatus
  - \*-CsOnlineSchedule, New-CsOnlineTimeRange, New-CsOnlineDateTimeRange
  - \*-CsOnlineAudioFile
  - Find-CsGroup
  - \*-CsOnlineDialInConferencingUser, \*-CsOnlineDialInConferencingServiceNumber, \*-CsOnlineDialInConferencingBridge, Get-CsOnlineDialInConferencingLanguagesSupported, Set-CsOnlineDialInConferencingUserDefaultNumber
  - \*-CsOnlineLisLocation, \*-CsOnlineLisCivicAddress, \*-CsOnlineLisWirelessAccessPoint, \*-CsOnlineLisPort, \*-CsOnlineLisSubnet, \*-CsOnlineEnhancedEmergencyServiceDisclaimer, \*-CsOnlineLisSwitch


## <a name="examples"></a>Примеры

В следующих примерах показано, как использовать модуль Teams PowerShell Azure AD проверку подлинности на основе приложения. 

- Подключитесь с помощью отпечатка сертификата:

  ```powershell
  Connect-MicrosoftTeams -CertificateThumbprint "XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX" -ApplicationId "00000000-0000-0000-0000-000000000000" -TenantId "YYYYYYYY-YYYY-YYYY-YYYY-YYYYYYYYYYYY"
  ```
  При использовании параметра CertificateThumbprint сертификат должен быть установлен на компьютере, где выполняется команда. Сертификат должен быть установлен в хранилище сертификатов пользователя.
  
- Подключение с помощью маркеров доступа:
  
  Маркеры доступа можно получить с помощью login.microsoftonline.com конечной точки. Для этого требуются два маркера доступа : "MS Graph" и "Skype и Teams Tenant Администратор API".

  ```powershell
  $ClientSecret   = "…"
  $ApplicationID = "00000000-0000-0000-0000-000000000000"
  $TenantID = "YYYYYYYY-YYYY-YYYY-YYYY-YYYYYYYYYYYY"

  $graphtokenBody = @{   
     Grant_Type    = "client_credentials"   
     Scope         = "https://graph.microsoft.com/.default"   
     Client_Id     = $ApplicationID   
     Client_Secret = $ClientSecret   
  }  

  $graphToken = Invoke-RestMethod -Uri "https://login.microsoftonline.com/$TenantID/oauth2/v2.0/token" -Method POST -Body $graphtokenBody | Select-Object -ExpandProperty Access_Token 

  $teamstokenBody = @{   
     Grant_Type    = "client_credentials"   
     Scope         = "48ac35b8-9aa8-4d74-927d-1f4a14a0b239/.default"   
     Client_Id     = $ApplicationID   
     Client_Secret = $ClientSecret 
  } 

  $teamsToken = Invoke-RestMethod -Uri "https://login.microsoftonline.com/$TenantID/oauth2/v2.0/token" -Method POST -Body $teamstokenBody | Select-Object -ExpandProperty Access_Token 

  Connect-MicrosoftTeams -AccessTokens @("$graphToken", "$teamsToken")
  ```
  
## <a name="how-does-it-work"></a>Как это работает?

Модуль Teams PowerShell извлекает маркер на основе приложения, используя идентификатор приложения, идентификатор клиента и отпечаток сертификата. Объект приложения, подготовленный в Azure AD имеет назначенную роль каталога, которая возвращается в маркере доступа. Управление доступом на основе ролей сеанса (RBAC) настраивается с помощью сведений о роли каталога, доступных в маркере.


## <a name="setup-application-based-authentication"></a>Настройка проверки подлинности на основе приложений

Для проверки подлинности с помощью объектов приложения требуется начальное подключение. Приложение и субъект-служба используются взаимозаменяемо, но приложение похоже на объект класса, а субъект-служба — как экземпляр класса. Дополнительные сведения об этих объектах см. в [разделе "Объекты приложения и субъекта-службы" в Azure Active Directory](/azure/active-directory/develop/app-objects-and-service-principals).

Ниже приведены общие шаги по созданию приложений в Azure AD. Подробные инструкции см. в этой [статье](/azure/active-directory/develop/howto-create-service-principal-portal).

1. Регистрация приложения в Azure AD
2. Назначение разрешений API приложению
   - Для \*командлетов -Cs разрешения API не требуются.
   - Для командлетов\*, отличных от CS, необходимые разрешения microsoft API Graph: `User.Read.All`, `Group.ReadWrite.All`, `AppCatalog.ReadWrite.All`, `TeamSettings.ReadWrite.All`, , `Channel.Delete.All``ChannelSettings.ReadWrite.All`. `ChannelMember.ReadWrite.All`  
3. Создание самозаверяющего сертификата
4. Присоединение сертификата к Azure AD приложения
5. Назначение Azure AD ролей приложению

Приложению должны быть назначены соответствующие роли RBAC. Так как приложения подготавливаются в Azure AD, можно использовать любую из поддерживаемых встроенных ролей.
 
