---
title: Перемещение пользователей из Скайп для бизнеса в Интернет для локально
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 12/19/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 55733bb5-6742-4daf-8db5-1c5df86f4cea
description: 'Сводка: Узнайте, как для перемещения учетных записей пользователей из Интернета к локально в Скайп для Business Server.'
ms.openlocfilehash: 033fb0a3a2cce6c763113ca94ea8af3c652cbbf5
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2018
ms.locfileid: "25374360"
---
# <a name="move-users-from-skype-for-business-online-to-on-premises"></a>Перемещение пользователей из Скайп для бизнеса в Интернет для локально

**Сводка:** Узнайте, как для перемещения учетных записей пользователей из Интернета к локально в Скайп для Business Server.

Может понадобиться для перемещения учетных записей пользователей из Интернета к локально убедитесь, что пользователи размещаются в Интернете и локально обнаруживаются друг с другом. В обнаруживаемый друг с другом, все пользователи должны иметь состояние присутствия в локальной Active Directory. Дополнительные сведения см в [планировании гибридного подключения между Скайп Business Server и Скайп для бизнеса в Интернет](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md). Можно переместить online пользователям при локальном, например, если:

- У вас есть новых пользователей, которые должны быть созданы локально и затем перемещен в облако.

- Вашей организации развернут Скайп для бизнеса в Интернет, прежде чем оно развернуто Скайп для Business Server. Таким образом у пользователей, которые были созданы в облаке, сначала и теперь необходимо переместить при локальном прежде чем они станут переход в Скайп для бизнеса в Интернет.

В этом разделе описывается два сценария:

- [Перемещение пользователей online — пользователей, которые были изначально online —, чтобы локальный](move-users-from-skype-for-business-online-to-on-premises.md#BKMK_originallyonline)

- [Переместите online пользователей (, которые были локально) локально](move-users-from-skype-for-business-online-to-on-premises.md#BKMK_originallyonprem)

## <a name="move-online-userswho-were-originally-onlineto-on-premises"></a>Перемещение пользователей online — пользователей, которые были изначально online —, чтобы локальный
<a name="BKMK_originallyonline"> </a>

Этот раздел применим только для пользователей, пользователей, которые были созданы и поддержкой Интернет-версия, однако, у которых нет учетной записи в локальный Active Directory.

Перед началом перемещения пользователей службы Online в локальную среду проверьте выполнение следующих условий.

- Локальная среда Lync Server должна быть полностью развернута и проверена. Для получения дополнительных сведений см [развертывания Lync Server 2013](https://technet.microsoft.com/library/b76795a4-4e71-4c70-a5c0-d1197fa8028c.aspx) или [Развернуть Скайп для Business Server 2015](../../deploy/deploy.md), в зависимости от того, какая версия использовании локально.

- Удаленный доступ к PowerShell должна быть настроена интерактивного клиента.

    Для этого сначала установить Скайп для бизнеса в Интернет модуля соединитель для Windows PowerShell, который вы можете получить здесь: [https://go.microsoft.com/fwlink/p/?LinkId=391911](https://go.microsoft.com/fwlink/p/?LinkId=391911).

    После установки модуля может установить удаленный сеанс, введя следующие командлеты в Скайп для консоли Business Server.

  ```
  Import-Module SkypeOnlineConnector
  ```

  ```
  $cred = Get-Credential
  ```

  ```
  $CSSession = New-CsOnlineSession -Credential $cred
  ```

  ```
  Import-PSSession $CSSession -AllowClobber
  ```

    Дополнительные сведения об использовании PowerShell с Скайп для бизнеса в Интернет можно [настроить компьютер для Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

- Общее адресное пространство SIP должна быть настроена интерактивного клиента. Для этого сначала удаленного сеанса Powershell с Скайп для бизнеса в Интернет. Затем выполните следующий командлет:

  ```
  Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True
  ```

    > [!NOTE]
    > Атрибут SharedSipAddressSpace необходимо оставаться «True», пока переход к Интернет-версия окончательный и пользователи не остаются локально.

После завершения этих действий можно перенести учетные записи пользователей, как описано в следующей процедуре:

### <a name="move-user-accounts-originally-enabled-online-to-an-on-premises-deployment"></a>Перемещение учетных записей пользователей, изначально включен в локальном развертывании Интернет-версия

1. Сначала подготовьте организацию к гибридному развертыванию, включая установку Azure Active Directory Connect и средств синхронизации. Дополнительные сведения см в [планировании гибридного подключения между Скайп Business Server и Скайп для бизнеса в Интернет](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md).

   - На локальном развертывании в Скайп для консоли Business Server, введите следующие командлеты для создания поставщика услуг размещения для Скайп для бизнеса в Интернет. Можно использовать любое значение для параметра Identity и Name.

   ```
   Set-CsAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -UseDnsSrvRouting -EnablePartnerDiscovery $true
   ```

   ```
   New-CsHostingProvider -Identity SkypeforBusinessOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
   ```

2. Убедитесь, что на пограничных серверах локальной, у вас есть цепочки сертификатов, который позволяет подключение к Скайп для бизнеса в Интернет, как показано в следующей таблице. Вы можете загрузить этот цепочки: [https://corp.sts.microsoft.com/Onboard/ADFS_Onboarding_Pack/corp_sts_certs.zip](https://corp.sts.microsoft.com/Onboard/ADFS_Onboarding_Pack/corp_sts_certs.zip).

|**Сертификат**|**Хранилище сертификатов**|
|:-----|:-----|
|Корневой Baltimore CyberTrust  <br/> |Доверенный корневой ЦС  <br/> |
|Microsoft Internet Authority (сертификат нового ЦС)  <br/> |Промежуточный ЦС  <br/> |
|MSIT Machine Auth CA2 (новый выдающий ЦС2)  <br/> |Промежуточный ЦС  <br/> |

3. В Active Directory в локальной включение учетных записей пользователя для Скайп для Business Server 2015 локально. Для отдельных пользователей это можно сделать путем ввода следующего командлета:

   ```
   Enable-CsUser
   -Identity "username "
   -SipAddress "sip: username @contoso.com"
   -HostingProviderProxyFqdn "sipfed.online.lync.com"
   ```

    Или можно создать сценарий для считывания имен пользователей из файла и передачи их как входных данных командлету Enable-CsUser:

   ```
   Enable-CsUser
   -Identity $Identity
   -SipAddress $SipAddress
   -HostingProviderProxyFqdn "sipfed.online.lync.com"
   ```

4. Синхронизация пользователей online с обновленные локальными пользователями. Для получения дополнительных сведений см [Средств интеграции каталогов](https://go.microsoft.com/fwlink/p/?LinkId=530320).

5. Обновите следующие записи DNS для направления весь трафик SIP для локального развертывания:

   - Обновите запись **lyncdiscover.contoso.com** A, указав полное доменное имя локального обратного прокси-сервера.

   - Обновление ** *_sip* . _tls.contoso.com** запись SRV для разрешения в общедоступный IP-адрес или виртуальный IP-адрес адрес пограничной службы доступа Lync локальных.

   - Обновление ** *_sipfederationtls* . _tcp.contoso.com** запись SRV для разрешения в общедоступный IP-адрес или виртуальный IP-адрес адрес службы пограничного сервера доступа из Скайп for Business Server 2015 локальной.

   - Если используемые организацией разделения DNS (иногда называется «разделенной DNS»), убедитесь в том, что пользователи, разрешение имен через внутреннюю зону DNS направляются пула переднего плана.

6. Тип `Get-CsUser` командлет, чтобы проверить некоторые свойства о пользователях, предполагается перемещать. Необходимо убедиться в том, что параметру HostingProviderProxyFQDN присвоено значение `"sipfed.online.lync.com"`, и проверить правильность задания SIP-адресов.

7. Переместите online пользователей локально.

    Чтобы переместить одного пользователя, введите следующее:

   ```
   $cred = Get-Credential
   Move-CsUser -Identity <username>@contoso.com  -Target "<fe-pool>.contoso.com " -Credential $cred -HostedMigrationOverrideURL <URL>
   ```

    Можно переместить несколько пользователей с помощью командлета **Get-CsUSer** с параметром - фильтра для выбора пользователей с определенное свойство. Например можно выделить все активные пользователи, фильтрации для {поставщиком услуг размещения - eq «sipfed.online.lync.om»}. Затем можно передать возвращенные пользователям командлета **Move-CsUSer** , как показано ниже.

   ```
   Get-CsUser -Filter {Hosting Provider -eq "sipfed.online.lync.com"} | Move-CsUser -Target "<fe-pool>.contoso.com " -Credential $creds -HostedMigrationOverrideURL <URL>
   ```

    Формат URL-адрес, указанный для параметра **HostedMigrationOverrideUrl** должен быть URL-адрес в пул, где работает размещенная служба миграции, в следующем формате: _Https://\<полное доменное имя пула\>/HostedMigration/ hostedmigrationService.svc_.

    URL-адрес службы миграции с размещением можно определить по URL-адресу панели управления Lync Online для учетной записи клиента Office 365.

### <a name="to-determine-the-hosted-migration-service-url-for-your-office-365-tenant"></a>Определение URL-адреса размещенной службы миграции для своего клиента Office 365

1. Выполните вход в свое клиентское приложение Office 365 как администратор.

2. Откройте **Центр администрирования Skype для бизнеса**.

3. Не закрывая окна **Центр администрирования Skype для бизнеса**, выделите и скопируйте URL-адрес в адресную строку в **lync.com**. Примерный URL-адрес выглядит так, как показано далее:

     `https://webdir0a.online.lync.com/lscp/?language=en-US&amp;tenantID=`

4. Заменяя **webdir** в URL-адресе на **admin**, получаем следующее:

     `https://admin0a.online.lync.com`

5. Добавьте к URL-адресу следующую строку: **/HostedMigration/hostedmigrationservice.svc**.

    Полученный URL-адрес, который соответствует значению **HostedMigrationOverrideUrl**, должен выглядеть следующим образом:

     `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`

    > [!NOTE]
    > По умолчанию максимальный размер файлов журналов транзакций базы данных rtcxds составляет 16 ГБ. Это не достаточно большой при перемещении большого числа пользователей, одновременно, особенно если зеркальное отображение включено. Во избежание такой ситуации можно увеличить размер файлов или регулярно создавать резервные копии файлов журналов. Дополнительные сведения можно [https://support.microsoft.com/kb/2756725](https://support.microsoft.com/kb/2756725).

6. Это необязательный шаг. Если требуется интеграция с Exchange 2013 Online, необходимо для использования поставщика услуг размещения дополнительных. Дополнительные сведения см [Настройка интеграции между локальной Скайп Business Server 2015 и Outlook Web App](../../deploy/integrate-with-exchange-server/outlook-web-app.md).

7. Теперь пользователи перемещаются. Чтобы проверить, что пользователь имеет правильные значения для атрибутов, показанных в таблице ниже, введите следующий командлет:

   ```
   Get-CsUser | fl DisplayName,HostingProvider,SipAddress,Enabled
   ```

| **Атрибут Active Directory**     | **Имя атрибута**     | **Правильное значение для пользователя Online** | **Правильное значение для локальных пользователей** |
|:-----------------------------------|:-----------------------|:----------------------------------|:----------------------------------------|
| msRTCSIP-DeploymentLocator  <br/>  | HostingProvider  <br/> | sipfed.Online.Lync.com  <br/>     | SRV:  <br/>                             |
| msRTCSIP-PrimaryUserAddress  <br/> | SIPAddress  <br/>      | SIP:username@Contoso.com  <br/>   | SIP:username@Contoso.com  <br/>         |
| msRTCSIP-UserEnabled  <br/>        | Включено  <br/>         | True  <br/>                       | True  <br/>                             |

10. Каждому перемещенному пользователю потребуется выйти из системы, а затем снова войти. При входе они должны проверить свои списки контактов и в случае необходимости добавить контакты.

    Следует учитывать, что запланированные собрания не переносятся из сетевого развертывания в локальное. После перемещения пользователям потребуется запланировать такие собрания заново.

    После обновления записей DNS и всех пользователей, направляются в локальной, атрибут HostingProvider пользователь переходит к используйте SRV-записи или их напрямую в Интернет-поставщика «sipfed.online.lync.com.»

## <a name="move-online-users-who-were-originally-on-premises-to-on-premises"></a>Переместите online пользователей (, которые были локально) локально
<a name="BKMK_originallyonprem"> </a>

Этот раздел применим только для пользователей, которые были созданы и включен для локального развертывания и затем перемещен из развертывания в локальной сети.

- Выполните следующие командлеты перемещение пользователя из Скайп для бизнеса Online обратно в локальную, заменяя значения параметров **Identity** и **конечного** для исправления значений для вашей среды:

  ```
  $cred=Get-Credential
  ```

  ```
  Move-CsUser -Identity username@contoso.com -Target localpool.contoso.com -Credential $cred -HostedMigrationOverrideUrl <URL>
  ```

Формат URL-адрес, указанный для параметра **HostedMigrationOverrideUrl** должен быть URL-адрес в пул, где работает размещенная служба миграции, в следующем формате:

 _Https://\<полное доменное имя пула\>/HostedMigration/hostedmigrationService.svc_. URL-адрес службы миграции с размещением можно определить по URL-адресу панели управления Lync Online для учетной записи клиента Office 365.

### <a name="to-determine-the-hosted-migration-service-url-for-your-office-365-tenant"></a>Определение URL-адреса размещенной службы миграции для своего клиента Office 365

1. Выполните вход в свое клиентское приложение Office 365 как администратор.

2. Откройте **Центр администрирования Skype для бизнеса**.

3. Не закрывая окна **Центр администрирования Skype для бизнеса**, выделите и скопируйте URL-адрес в адресную строку в **lync.com**. Примерный URL-адрес выглядит так, как показано далее:

     `https://webdir0a.online.lync.com/lscp/?language=en-US&amp;tenantID=`

4. Заменяя **webdir** в URL-адресе на **admin**, получаем следующее:

     `https://admin0a.online.lync.com`

5. Добавьте к URL-адресу следующую строку: **/HostedMigration/hostedmigrationservice.svc**.

    Полученный URL-адрес, который соответствует значению **HostedMigrationOverrideUrl**, должен выглядеть следующим образом:

     `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`


