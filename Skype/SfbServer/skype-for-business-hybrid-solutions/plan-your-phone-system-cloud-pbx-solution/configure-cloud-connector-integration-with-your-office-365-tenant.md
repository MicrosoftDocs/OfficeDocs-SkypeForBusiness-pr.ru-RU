---
title: Настройка интеграции облачного соединители с Microsoft 365 или Office 365 организацией
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
ms.localizationpriority: medium
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 0e2f2395-b890-4d16-aa2d-99d52438b89c
description: Узнайте, как настроить интеграцию облачного соединители с Microsoft 365 или Office 365 организацией.
ms.openlocfilehash: b3b8b13669a2e52ed5146e1bd0ca179a5542e43d
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2021
ms.locfileid: "58733378"
---
# <a name="configure-cloud-connector-integration-with-your-microsoft-365-or-office-365-organization"></a>Настройка интеграции облачного соединители с Microsoft 365 или Office 365 организацией

> [!Important] 
> Cloud Connector Edition завершится 31 июля 2021 г. вместе с Skype для бизнеса Online. После обновления организации Teams, узнайте, как подключить локальной телефонной сети к Teams с помощью прямой [маршрутизации](/MicrosoftTeams/direct-routing-landing-page).

Узнайте, как настроить интеграцию облачного соединители с Microsoft 365 или Office 365 организацией.
  
После завершения Skype для бизнеса Cloud Connector Edition выполните действия в этом разделе, чтобы настроить развертывание и подключить его к Microsoft 365 или Office 365 организации.
  
## <a name="configure-firewall-settings"></a>Настройка параметров брандмауэра

Настройка параметров брандмауэра для параметров внутреннего и внешнего брандмауэра для [](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports) сети периметра для открытия необходимых портов, как описано в Портах и протоколах в [Plan for Skype для бизнеса Cloud Connector Edition.](plan-skype-for-business-cloud-connector-edition.md)
  
## <a name="set-up-public-switched-telephone-network-pstn-gateways"></a>Настройка шлюзов общедоступных переключеных телефонных сетей (PSTN)

Настройка магистрали на каждом шлюзе PSTN, чтобы указать обратно на серверы-посредники для всех устройств. Так как FQDN пула является одинаковым для всех серверов пула, каждый магистраль должен указать на один FQDN или IP-адрес сервера-посредника вместо FQDN пула посредников. Магистрали должны быть настроены в том же приоритете.
  
Если вы используете TLS между серверами-посредниками и шлюзами, вам потребуется настроить шлюзы и серверы-посредники для поддержки MTLS следующим образом:
  
1. Экспорт корневого ЦС с компьютера Cloud Connector Active Directory.
    
2. Следуйте инструкциям поставщика шлюза PSTN для импорта корневого ЦС.
    
3. Импорт сертификата Root CA для сертификата, выданного шлюзу на серверах-посредниках. Если вам необходимо получить сертификат SSL для шлюза, вы можете сделать это с помощью службы Authority сертификата, запущенной на компьютере Active Directory облачного соединителя следующим образом:
    
   - Измените существующий шаблон веб-сервера, чтобы пользователи могли зарегистрироваться с проверкой подлинности, или создать новый шаблон веб-сервера для настройки других свойств и обеспечения регистрации пользователей с проверкой подлинности. Подробные инструкции см. [в справке Шаблоны сертификатов.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc730705(v=ws.11))
    
   - Запрос сертификата с помощью оснастки сертификата для выбора шаблона веб-сервера, который вы включили. Обязательно добавьте имя Common в Subject и DNS в Альтернативное имя с FQDN шлюза и убедитесь в частном ключе, что при ключевых параметрах выбирается частный ключ, экспортируемый. 
    
4. Экспорт сертификата SSL с закрытым ключом и следуйте инструкциям поставщика шлюза PSTN для импорта сертификата.
    
## <a name="update-the-domain-for-your-tenant"></a>Обновление домена для клиента

Убедитесь, что вы выполнили действия по обновлению домена в Microsoft 365 или Office 365 и можете добавлять записи DNS. Дополнительные сведения о том, как настроить домен в Microsoft 365 или Office 365, см. в Microsoft 365 или [Office 365.](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)
  
## <a name="add-dns-records-for-your-edge"></a>Добавление записей DNS для edge

Добавьте следующие записи DNS в Microsoft 365 или Office 365 организации. Сведения о добавлении записей DNS см. в статью Добавление или изменение пользовательских записей DNS в Microsoft 365 [или Office 365.](https://support.office.com/article/Add-or-edit-custom-DNS-records-in-Office-365-AF00A516-DD39-4EDA-AF3E-1EAF686C8DC9?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1)
  
1. Добавление записи DNS Для края доступа.
    
2. Записи SRV будут автоматически создаваться Microsoft 365 или Office 365 и скриптами развертывания. Подтверди, что на границе можно найти следующие две службы SIP: \_ sip и \_ sipfederationtls.
    
     ![Подтверждение записей SRV.](../../media/3c353a29-6dcc-4ed3-98db-3a6bed3e929e.png)
  
## <a name="set-up-hybrid-connectivity-between-cloud-connector-edition-and-microsoft-365-or-office-365"></a>Настройка гибридного подключения между Cloud Connector Edition и Microsoft 365 или Office 365

Чтобы настроить гибридную связь между развертыванием Skype для бизнеса Cloud Connector Edition и вашей Microsoft 365 или Office 365 организацией, запустите следующий комдлет в удаленном сеансе PowerShell. Чтобы узнать, как установить удаленный сеанс PowerShell, см. в руб. Настройка компьютера для [Windows PowerShell.](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
  
В этом комлете задаваем внешний FQDN Access Edge. В первой из команд должна быть роль \<External Access Edge FQDN\> SIP Access Edge. По умолчанию это должно быть ap. \<Domain Name\> .
  
```powershell
Set-CsTenantHybridConfiguration -PeerDestination <External Access Edge FQDN> -UseOnPremDialPlan $false
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True
```

> [!NOTE]
> Внешний FQDN edge access, используемый для одноранговых назначений, должен быть установлен на сайте PSTN, который будет использоваться только в качестве отката в случае, если пользователь не назначен сайту PSTN. Дополнительные сведения см. в [веб-сайте Развертывание](deploy-a-single-site-in-cloud-connector.md) одного сайта в облачном соединители и развертывание нескольких сайтов [в облачном соединители.](deploy-multiple-sites-in-cloud-connector.md) 
  
## <a name="set-up-pstn-gateways"></a>Настройка шлюзов PSTN

Настройка магистрали на каждом шлюзе PSTN, чтобы указать обратно на серверы-посредники для всех устройств. Каждый магистраль должен указать на один FQDN или IP-адрес сервера-посредника вместо пула FQDN пула посредников, так как FQDN пула является одинаковым для всех серверов пула. Магистрали должны быть настроены в том же приоритете.
  
Если вы используете TLS между серверами-посредниками и шлюзами, вам потребуется настроить шлюзы и серверы-посредники для поддержки MTLS следующим образом:
  
1. Экспорт корневого ЦС с компьютера Cloud Connector Active Directory.
    
2. Следуйте инструкциям поставщика шлюза PSTN для импорта корневого ЦС.
    
3. Импорт сертификата Root CA для сертификата, выданного шлюзу на серверах-посредниках. Если вам необходимо получить сертификат SSL для шлюза, вы можете сделать это с помощью службы Authority сертификата, запущенной на компьютере Active Directory облачного соединителя следующим образом:
    
   - Измените существующий шаблон веб-сервера, чтобы пользователи могли зарегистрироваться на проверку подлинности, или создать новый шаблон веб-сервера для настройки других свойств и регистрации с проверкой подлинности. Подробные инструкции см. [в справке Шаблоны сертификатов.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc730705(v=ws.11))
    
   - Запрос сертификата с помощью оснастки сертификата для выбора шаблона веб-сервера, который вы включили. Обязательно добавьте имя Common в Subject и DNS в Альтернативное имя с FQDN шлюза и убедитесь в частном ключе, что при ключевых параметрах выбирается частный ключ, экспортируемый. 
    
4. Экспорт сертификата SSL с закрытым ключом и следуйте инструкциям поставщика шлюза PSTN для импорта сертификата.
    
5. Шлюз PSTN(ы) на одном сайте PSTN должен подключаться только к серверу-посреднику(ы) на том же сайте.
    
## <a name="set-up-your-users"></a>Настройка пользователей

Войдите в Центр администрирования Microsoft 365, добавьте пользователей, которые будут включены для сетевых голосовых служб, и назначьте этим пользователям лицензию E5 или телефонная система надстройки к лицензии E3. Дополнительные сведения о добавлении пользователей см. в [Microsoft 365 для бизнеса.](https://support.office.com/article/Add-users-to-Office-365-for-business-435ccec3-09dd-4587-9ebd-2f3cad6bc2bc)
  
## <a name="enable-users-for-phone-system-voice-and-voicemail-services"></a>Включить пользователей для телефонная система голосовой почты и голосовой почты
 
После добавления пользователей в Microsoft 365 или Office 365 включите их учетные записи для телефонная система голосовой почты, в том числе голосовой почты. Чтобы включить эти возможности, необходимо войти в Microsoft 365 или Office 365 организации с учетной записью, которая является ролью глобального администратора, и иметь возможность запуска удаленной PowerShell. Чтобы узнать, как установить удаленный сеанс PowerShell, см. в рубке: Настройка компьютера [для Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
  
- Назначьте политику пользователю и настройте номер делового голосового телефона пользователя, который указан со значением **параметра Identity:**
    
  ```powershell
  Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI <tel:+phonenumber>
  ```

    > [!NOTE]
    > Идентификация пользователя может быть указана с помощью SIP-адреса пользователя, имени основного пользователя (UPN) или имени отображения Active Directory пользователя (например, "Bob Kelly"). Символ звездочки () также можно использовать с именем \* display в качестве идентификатора пользователя. Например, идентификатор "Smith" возвращает всех пользователей, у которых есть имя отображения, которое заканчивается значением \* строки "Smith".
  
Затем можно убедиться, что пользователи были добавлены и включены с помощью следующего сценария:
  
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

Необходимо решить, смогут ли пользователи принимать международные вызовы. По умолчанию включен международный вызов. Вы можете отключить или включить пользователей для международного набора с помощью центра Skype для бизнеса администрирования.
  
Чтобы отключить международные вызовы для каждого пользователя, запустите следующий комдлет в Skype для бизнеса PowerShell:
  
```powershell
Grant-CsVoiceRoutingPolicy -PolicyName InternationalCallsDisallowed -Identity $user
```

Чтобы повторно включить международные вызовы для каждого пользователя после отключения, запустите тот же кодлет, но измените значение **для PolicyName** на *InternationalCallsAllowed*  .
  
## <a name="assign-users-to-pstn-sites"></a>Назначение пользователей сайтам PSTN

Используйте удаленный powerShell клиента для назначения сайта пользователям, даже если вы развернули только один сайт. Чтобы узнать, как установить удаленный сеанс PowerShell, см. в руб. Настройка компьютера для [Windows PowerShell.](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
  
```powershell
# Set the site to users
Set-CsUserPstnSettings -Identity <User Name> -HybridPstnSite <PSTN Site Name>

# Review the site setting for a user
Get-CsUserPstnSettings -Identity <User Name> 

# See all the user settings in one tenant
Get-CsOnlineUser | Get-CsUserPstnSettings
```

> [!NOTE]
> Если пользователю не назначен сайт PSTN, гибридное подключение между развертыванием Skype для бизнеса Cloud Connector Edition и вашей Microsoft 365 или Office 365 организации отпадет для использования по умолчанию клиента (одноранговой пункт назначения), чтобы можно было завершить вызовы. 
  
## <a name="configure-online-hybrid-mediation-server-settings"></a>Настройка веб-гибридного сервера-посредника Параметры
<a name="BKMK_ConfigureMediationServer"> </a>

Когда вызов P2P будет перенаправлен на конференцию PSTN, Skype для бизнеса сервер конференц-связи в Интернете отправит приглашение на сервер посредников облачного соединителю. Чтобы Microsoft 365 или Office 365 успешно маршрутировать это приглашение, необходимо настроить параметр в онлайн-клиенте для каждого сервера-посредника облачного соединители следующим образом: 
  
1. Создайте пользователя в Центр администрирования Microsoft 365. Используйте любое нужное имя пользователя, например "MediationServer1".
    
    Используйте по умолчанию SIP-домен Cloud Connector (первый домен SIP в .ini файле) в качестве пользовательского домена.
    
    Обратите внимание, что назначение лицензии требуется только для распространения пользователя в Skype для бизнеса каталоге. Назначьте Microsoft 365 или Office 365 лицензию (например, E5) на создаемую учетную запись, разрешить до одного часа для распространения изменений, убедитесь, что учетные записи пользователей были правильно Skype для бизнеса в каталоге Skype для бизнеса, запуская следующий кодлет, а затем удалите лицензию из этой учетной записи.
    ```powershell
   Get-CsOnlineUser -Identity <UserPrincipalName>
   ```
    
2. Запустите удаленный сеанс PowerShell Azure AD с использованием учетных данных глобального или пользовательского администратора, а затем запустите следующий кодлет, чтобы задать отдел учетной записи пользователя Azure AD, настроенной в шаге 1 на "HybridMediationServer":

   ```powershell
   Set-MsolUser -UserPrincipalName <UserPrincipalName> -Department "HybridMediationServer"
   ```

3. Запустите сеанс удаленной Skype для бизнеса PowerShell с помощью учетных данных администратора Skype для бизнеса клиента, а затем запустите следующий скоммлет, чтобы установить сервер-посредник и интерфейс сервера FQDN для этой учетной записи пользователя, заменив имя пользователя для учетной записи, созданной на \<DisplayName\> шаге 1:
    
   ```powershell
   Set-CsHybridMediationServer -Identity <DisplayName> -Fqdn <MediationServerFQDN> -AccessProxyExternalFqdn <EdgeServerExternalFQDN>
   ```

    Для identity используйте имя отображения учетной записи пользователя, созданной для этого сервера-посредника.
    
    Для  *mediationServerFQDN*  используйте внутренний FQDN, определенный для сервера-посредника.
    
    Для  *EdgeServerExternalFQDN*  используйте внешний FQDN, определенный для прокси-сервера edge Server Access. Если имеется несколько сайтов PSTN с облачным соединитетелем, выберите сервер edge Server Access Proxy FQDN, назначенный сайту, на котором расположен сервер-посредник.
    
4. Если существует несколько серверов-посредников облачного соединителя (несколько сайтов, ha), повторите предыдущие действия для каждого из них.
