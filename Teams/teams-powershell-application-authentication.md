---
title: Проверка подлинности на основе приложений в модуле PowerShell Teams
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
ms.openlocfilehash: 60d9bf64233db3f5e615c0904c6eb376f187266c
ms.sourcegitcommit: 95a56dab4e30f7ad6615ebd4a4a0f61996fdc20f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2023
ms.locfileid: "69812846"
---
# <a name="application-based-authentication-in-teams-powershell-module"></a>Проверка подлинности на основе приложений в модуле PowerShell Teams

Проверка подлинности на основе приложений теперь поддерживается в модуле Teams PowerShell версии 4.7.1-preview или более поздней. В настоящее время этот режим проверки подлинности поддерживается только в коммерческих средах.


## <a name="cmdlets-supported"></a>Поддерживаемые командлеты

Сейчас поддерживаются все командлеты, за исключением командлетов, упомянутых ниже. 

  - New-Team
  - [Get| Задать| Новое| Sync]-CsOnlineApplicationInstance
  - \*-CsUserCallingSettings
  - \*-CsUserCallingDelegate
  - \*PolicyPackage\*
  - \*-CsTeamsShiftsConnection\*
  - \*-CsBatchTeamsDeployment\*


## <a name="examples"></a>Примеры

В следующих примерах показано, как использовать модуль Teams PowerShell с Azure AD проверки подлинности на основе приложения. 

- Подключение с помощью отпечатка сертификата:

  ```powershell
  Connect-MicrosoftTeams -CertificateThumbprint "XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX" -ApplicationId "00000000-0000-0000-0000-000000000000" -TenantId "YYYYYYYY-YYYY-YYYY-YYYY-YYYYYYYYYYYY"
  ```
  При использовании параметра CertificateThumbprint сертификат должен быть установлен на компьютере, где выполняется команда. Сертификат должен быть установлен в хранилище сертификатов пользователя.
  
- Подключение с помощью объекта сертификата:

  ```powershell
  Connect-MicrosoftTeams -Certificate <%X509Certificate2 object%> -ApplicationId "00000000-0000-0000-0000-000000000000" -TenantId "YYYYYYYY-YYYY-YYYY-YYYY-YYYYYYYYYYYY"
  ```
  При использовании параметра Certificate сертификат не требуется устанавливать на компьютере, где выполняется команда. Сертификат можно удаленно хранить & получить при выполнении скрипта. Параметр Certificate доступен в модуле Teams PowerShell версии 4.9.2-preview или более поздней.
  
- Подключение с помощью маркеров доступа:
  
  Маркеры доступа можно получить через конечную точку login.microsoftonline.com. Для этого требуются два маркера доступа — ресурсы MS Graph и API клиента Skype и Teams Администратор.

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

Модуль PowerShell Teams извлекает маркер на основе приложения, используя идентификатор приложения, идентификатор клиента и отпечаток сертификата. Объекту приложения, подготовленному внутри Azure AD, назначена роль каталога, которая возвращается в маркере доступа. Управление доступом на основе ролей (RBAC) сеанса настраивается с помощью сведений о роли каталога, доступных в маркере.


## <a name="setup-application-based-authentication"></a>Настройка проверки подлинности на основе приложений

Для проверки подлинности с помощью объектов приложения требуется начальное подключение. Приложение и субъект-служба используются взаимозаменяемо, но приложение похоже на объект класса, а субъект-служба — как экземпляр класса . Дополнительные сведения об этих объектах см. [в статье Объекты приложения и субъекта-службы в Azure Active Directory](/azure/active-directory/develop/app-objects-and-service-principals).

Примеры действий по созданию приложений в Azure Ad приведены ниже. Подробные инструкции см. в этой [статье](/azure/active-directory/develop/howto-create-service-principal-portal).

1. Регистрация приложения в Azure AD
2. Назначение приложению разрешений API
   - Для \*командлетов -Cs требуется разрешение Microsoft API Graph .`Organization.Read.All`
   - Для командлетов, отличных \*от Cs, требуются `Organization.Read.All`разрешения Microsoft API Graph: , , `User.Read.All`, `Group.ReadWrite.All``AppCatalog.ReadWrite.All`, `TeamSettings.ReadWrite.All`, `Channel.Delete.All`, `ChannelSettings.ReadWrite.All`, . `ChannelMember.ReadWrite.All`  
3. Создание самозаверяющего сертификата
4. Присоединение сертификата к приложению Azure AD
5. Назначение [Azure AD ролей](/microsoftteams/using-admin-roles#teams-roles-and-capabilities) приложению

Приложению должны быть назначены соответствующие роли RBAC. Так как приложения подготовлены в Azure AD, вы можете использовать любую из поддерживаемых встроенных ролей.
 
