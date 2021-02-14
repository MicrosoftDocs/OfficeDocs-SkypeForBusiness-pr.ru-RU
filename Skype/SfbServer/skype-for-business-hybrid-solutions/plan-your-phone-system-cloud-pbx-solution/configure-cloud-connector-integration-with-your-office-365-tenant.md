---
title: Настройка интеграции Cloud Connector с организацией Microsoft 365 или Office 365
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 0e2f2395-b890-4d16-aa2d-99d52438b89c
description: Узнайте, как настроить интеграцию Cloud Connector с вашей организацией Microsoft 365 или Office 365.
ms.openlocfilehash: bf5d8c4fb9684a205670701428fa8db30835a871
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359075"
---
# <a name="configure-cloud-connector-integration-with-your-microsoft-365-or-office-365-organization"></a>Настройка интеграции Cloud Connector с организацией Microsoft 365 или Office 365

> [!Important] 
> Выпуск Cloud Connector Edition завершится 31 июля 2021 г. вместе со Skype для бизнеса Online. После обновления вашей организации до Teams узнайте, как подключить свою локальной телефонной сети к Teams с помощью [прямой маршрутизации.](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)

Узнайте, как настроить интеграцию Cloud Connector с вашей организацией Microsoft 365 или Office 365.
  
После завершения установки Skype для бизнеса Cloud Connector Edition выполните действия, которые необходимо выполнить в этом разделе, чтобы настроить развертывание и подключить его к организации Microsoft 365 или Office 365.
  
## <a name="configure-firewall-settings"></a>Настройка параметров брандмауэра

Настройте параметры брандмауэра для внутренних и внешних параметров брандмауэра [](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports) для сети периметра, чтобы открыть необходимые порты, как описано в описании портов и протоколов в plan [for Skype for Business Cloud Connector Edition.](plan-skype-for-business-cloud-connector-edition.md)
  
## <a name="set-up-public-switched-telephone-network-pstn-gateways"></a>Настройка шлюзов телефонной сети общего слева (PSTN)

Установите магистрали на каждом шлюзе STN так, чтобы они возвращались на серверы-посредники для всех устройств. Поскольку FQDN пула одинаково для всех серверов в пуле, каждая магистраль должна указать на одно FQDN сервера-посредника или IP-адрес вместо пула серверов-посредников. Магистрали должны иметь одинаковый приоритет.
  
При использовании TLS между серверами-посредниками и шлюзами необходимо настроить шлюзы и серверы-посредники для поддержки MTLS следующим образом:
  
1. Экспорт корневого ЦС с компьютера Cloud Connector Active Directory.
    
2. Следуйте инструкциям поставщика шлюза STN для импорта корневого ЦС.
    
3. Импортировать сертификат корневого ЦС для сертификата, выданного шлюзу на серверах-посредниках. Если вам нужно получить SSL-сертификат для шлюза, это можно сделать с помощью службы центра сертификации, запущенной на компьютере Active Directory Cloud Connector следующим образом:
    
   - Измените существующий шаблон веб-сервера, чтобы включить регистрацию для пользователей, для проверки подлинности, или создайте новый шаблон веб-сервера, чтобы настроить другие свойства и включить регистрацию для пользователей, подлинность и подлинность пользователей. Подробные инструкции [см. в описании шаблонов сертификатов.](https://technet.microsoft.com/library/cc730705.aspx)
    
   - Запрос сертификата с помощью оснастки "Сертификат" для выбора включенного шаблона веб-сервера. Обязательно добавьте общее имя в subject и DNS-имя в альтернативном имени с FQDN шлюза и убедитесь, что в закрытом ключе выбран параметр "Сделать закрытый ключ экспортируемым". 
    
4. Экспортировать SSL-сертификат с закрытым ключом и следуйте инструкциям поставщика шлюза STN для импорта сертификата.
    
## <a name="update-the-domain-for-your-tenant"></a>Обновление домена для клиента

Убедитесь, что вы выполнили действия по обновлению домена в Microsoft 365 или Office 365 и добавили записи DNS. Дополнительные сведения о том, как настроить домен в Microsoft 365 или Office 365, см. в подстройки "Добавление домена в [Microsoft 365" или "Office 365".](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)
  
## <a name="add-dns-records-for-your-edge"></a>Добавление записей DNS для edge

Добавьте следующие записи DNS в организацию Microsoft 365 или Office 365. Дополнительные сведения о добавлении записей DNS см. в подстройки и редактировании пользовательских [записей DNS в Microsoft 365 или Office 365.](https://support.office.com/article/Add-or-edit-custom-DNS-records-in-Office-365-AF00A516-DD39-4EDA-AF3E-1EAF686C8DC9?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1)
  
1. Добавьте запись A DNS для access Edge.
    
2. Записи SRV автоматически создаются в Microsoft 365 или Office 365 и сценариях развертывания. Подтвердим, что на границе можно найти две службы SIP: \_ sip и \_ sipfederationtls.
    
     ![Подтверждение записей SRV](../../media/3c353a29-6dcc-4ed3-98db-3a6bed3e929e.png)
  
## <a name="set-up-hybrid-connectivity-between-cloud-connector-edition-and-microsoft-365-or-office-365"></a>Настройка гибридного подключения между Cloud Connector Edition и Microsoft 365 или Office 365

Чтобы настроить гибридное подключение между развертыванием Skype для бизнеса Cloud Connector Edition и организацией Microsoft 365 или Office 365, запустите следующий cmdlet в удаленном сеансе PowerShell. Чтобы узнать, как установить удаленный сеанс PowerShell, см. в этой [Windows PowerShell.](https://technet.microsoft.com/library/dn362831%28v=ocs.15%29.aspx)
  
Этот cmdlet задает внешнее FQDN edge доступа. В первой команде должна быть роль для роли \<External Access Edge FQDN\> SIP Access Edge. По умолчанию это значение должно быть ap. \<Domain Name\> .
  
```powershell
Set-CsTenantHybridConfiguration -PeerDestination <External Access Edge FQDN> -UseOnPremDialPlan $false
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True
```

> [!NOTE]
> В качестве FQDN внешнего доступа, используемого для одноранговой цели, следует установить сайт PSTN, который будет использоваться в качестве отката только в случае, если пользователь не назначен сайту STN. Дополнительные сведения см. в сведениях о развертывании одного сайта в [Cloud Connector](deploy-a-single-site-in-cloud-connector.md) и развертывании нескольких сайтов [в Cloud Connector.](deploy-multiple-sites-in-cloud-connector.md) 
  
## <a name="set-up-pstn-gateways"></a>Настройка шлюзов STN

Установите магистрали на каждом шлюзе STN так, чтобы они возвращались на серверы-посредники для всех устройств. Каждая магистраль должна указать на одно FQDN сервера-посредника или IP-адрес, а не на пул серверов-посредников, поскольку это одно и то же FQDN пула для всех серверов в пуле. Магистрали должны иметь одинаковый приоритет.
  
При использовании TLS между серверами-посредниками и шлюзами необходимо настроить шлюзы и серверы-посредники для поддержки MTLS следующим образом:
  
1. Экспорт корневого ЦС с компьютера Cloud Connector Active Directory.
    
2. Следуйте инструкциям поставщика шлюза STN для импорта корневого ЦС.
    
3. Импортировать сертификат корневого ЦС для сертификата, выданного шлюзу на серверах-посредниках. Если вам нужно получить SSL-сертификат для шлюза, это можно сделать с помощью службы центра сертификации, запущенной на компьютере Active Directory Cloud Connector следующим образом:
    
   - Измените существующий шаблон веб-сервера, чтобы включить регистрацию для пользователей, для проверки подлинности, или создайте новый шаблон веб-сервера, чтобы настроить другие свойства и включить регистрацию пользователей, подлинность и подлинность пользователей. Подробные инструкции [см. в описании шаблонов сертификатов.](https://technet.microsoft.com/library/cc730705.aspx)
    
   - Запрос сертификата с помощью оснастки "Сертификат" для выбора включенного шаблона веб-сервера. Обязательно добавьте общее имя в subject и DNS-имя в альтернативном имени с FQDN шлюза и убедитесь, что в закрытом ключе выбран параметр "Сделать закрытый ключ экспортируемым". 
    
4. Экспортировать SSL-сертификат с закрытым ключом и следуйте инструкциям поставщика шлюза STN для импорта сертификата.
    
5. Шлюзы STN на одном сайте STN должны подключаться только к серверам-посредникам на том же сайте.
    
## <a name="set-up-your-users"></a>Настройка пользователей

Войдите в Центр администрирования Microsoft 365, добавьте пользователей, для которых будут включены веб-службы голосовой связи, и назначьте этим пользователям лицензию E5 или надстройки телефонной системы. Дополнительные сведения о добавлении пользователей см. в подсети "Добавление пользователей [в Microsoft 365 для бизнеса".](https://support.office.com/article/Add-users-to-Office-365-for-business-435ccec3-09dd-4587-9ebd-2f3cad6bc2bc)
  
## <a name="enable-users-for-phone-system-voice-and-voicemail-services"></a>Включить для пользователей службы голосовой и голосовой почты телефонной системы
 
После добавления пользователей в Microsoft 365 или Office 365 включите их учетные записи для голосовых служб телефонной системы, включая голосовую почту. Чтобы включить эти возможности, необходимо войти в свою организацию Microsoft 365 или Office 365 с учетной записью, которая является ролью глобального администратора, и иметь возможность запускать удаленную powerShell. Чтобы узнать, как установить удаленный сеанс [](https://technet.microsoft.com/library/dn362831%28v=ocs.15%29.aspx) PowerShell, см. в этой Windows PowerShell
  
- Назначьте политику пользователю и настройте номер телефона бизнес-голосовой связи, который указывается в параметре **Identity:**
    
  ```powershell
  Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI <tel:+phonenumber>
  ```

    > [!NOTE]
    > Удостоверение пользователя может быть задано с помощью SIP-адреса пользователя, имени пользователя-директора или отображаемого имени Active Directory пользователя (например, "Bob Kelly"). Звездочка () также может использоваться вместе с \* отображаемой именем в качестве удостоверения пользователя. Например, идентификатор "Smith" возвращает всех пользователей, отображаемого имени которых заканчивается строкой \* "Smith".
  
Затем можно проверить, были ли добавлены и включены пользователи, с помощью следующего скрипта:
  
```powershell
# Input the user name you want to verify
$user = Get-CsOnlineUser <User name>

# For a hybrid user, the value of $user.EnterpriseVoiceEnabled should be True
$user.EnterpriseVoiceEnabled

# For a hybrid user, the value of $user.HostedVoiceMail should be True
$user.HostedVoiceMail

# For a hybrid user, the value of $user.VoicePolicy should be "HybridVoice"
$user.VoicePolicy
```

Необходимо решить, смогут ли ваши пользователи делать международные звонки. По умолчанию международные вызовы включены. You can disable or enable users for international dialing using the online Skype for Business admin center.
  
Чтобы отключить международные звонки для каждого пользователя, запустите следующий cmdlet в Skype для бизнеса Online PowerShell:
  
```powershell
Grant-CsVoiceRoutingPolicy -PolicyName InternationalCallsDisallowed -Identity $user
```

Чтобы повторно включить международные вызовы для каждого пользователя после его отключения, запустите тот же самый cmdlet, но измените значение **для PolicyName** на *InternationalCallsAllowed.*
  
## <a name="assign-users-to-pstn-sites"></a>Назначение пользователей сайтам STN

Используйте удаленную powerShell клиента, чтобы назначить сайт пользователям, даже если развернут только один сайт. Чтобы узнать, как установить удаленный сеанс PowerShell, см. в этой [Windows PowerShell.](https://technet.microsoft.com/library/dn362831%28v=ocs.15%29.aspx)
  
```powershell
# Set the site to users
Set-CsUserPstnSettings -Identity <User Name> -HybridPstnSite <PSTN Site Name>

# Review the site setting for a user
Get-CsUserPstnSettings -Identity <User Name> 

# See all the user settings in one tenant
Get-CsOnlineUser | Get-CsUserPstnSettings
```

> [!NOTE]
> Если пользователю не назначен сайт STN, гибридное подключение между развертыванием Skype для бизнеса Cloud Connector Edition и организацией Microsoft 365 или Office 365 будет возвращаться к использованию стандартного уровня клиента (одноранговая цель), чтобы можно было завершить вызовы. 
  
## <a name="configure-online-hybrid-mediation-server-settings"></a>Настройка параметров сетевого гибридного сервера-посредника
<a name="BKMK_ConfigureMediationServer"> </a>

Когда вызов P2P перенаправлен на конференцию STN, сервер конференц-связи Skype для бизнеса Online отправит приглашение серверу-посреднику Cloud Connector. Чтобы убедиться, что Microsoft 365 или Office 365 могут успешно маршрутировать это приглашение, необходимо настроить параметр в сетевом клиенте для каждого сервера-посредника Cloud Connector следующим образом: 
  
1. Создайте пользователя в Центре администрирования Microsoft 365. Используйте любое нужное имя пользователя, например "MediationServer1".
    
    Используйте SIP-домен Cloud Connector по умолчанию (первый домен SIP в INI-файле) в качестве домена пользователя.
    
    Обратите внимание, что назначение лицензии требуется только для распространения пользователя в каталог Skype для бизнеса Online. Assign a Microsoft 365 or Office 365 license (such as E5) to the account you create, allow up to one hour for the changes to propagate, verify the user accounts has been provisioned correctly to the Skype for Business online directory by running following cmdlet, then remove the license from this account.
    ```powershell
   Get-CsOnlineUser -Identity <UserPrincipalName>
   ```
    
2. Запустите удаленный сеанс PowerShell azure AD клиента с использованием учетных данных глобального администратора или администратора пользователя, а затем запустите следующий cmdlet, чтобы настроить отдел для учетной записи пользователя Azure AD, настроенной на шаге 1, на "HybridMediationServer":

   ```powershell
   Set-MsolUser -UserPrincipalName <UserPrincipalName> -Department "HybridMediationServer"
   ```

3. Запустите удаленный сеанс PowerShell клиента Skype для бизнеса, используя учетные данные администратора клиента Skype для бизнеса, а затем запустите следующий cmdlet, чтобы установить для этой учетной записи пользователя имя FQDN сервера-посредника и сервера-посредника, заменив отображаемого имени пользователя для учетной записи, созданной на шаге \<DisplayName\> 1:
    
   ```powershell
   Set-CsHybridMediationServer -Identity <DisplayName> -Fqdn <MediationServerFQDN> -AccessProxyExternalFqdn <EdgeServerExternalFQDN>
   ```

    Для удостоверения используйте отображаемую имя учетной записи пользователя, созданной для этого сервера-посредника.
    
    Для  *mediationServerFQDN*  используйте внутреннее FQDN, определенное для сервера-посредника.
    
    Для  *EdgeServerExternalFQDN*  используйте внешнее FQDN, определенное для прокси-сервера доступа к серверу. Если имеется несколько сайтов STN Cloud Connector, выберите FQDN прокси-сервера доступа к серверу, назначенное сайту, на котором расположен сервер-посредник.
    
4. Если имеется несколько серверов-посредников Cloud Connector (с несколькими сайтами, ha), повторите предыдущие шаги для каждого из них.
    
