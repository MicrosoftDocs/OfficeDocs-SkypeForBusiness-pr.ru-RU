---
title: 'Lync Server 2013: миграция пользователей Lync Online в локальную среду Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Migrating Lync Online users to Lync on-premises
ms:assetid: 0e29605b-db2d-4cbf-b6a9-15db6b9fdabc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn689115(v=OCS.15)
ms:contentKeyID: 62258120
ms.date: 11/13/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8a2be7414dbdc48c9e245db33e57b8238cfb2ee9
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520996"
---
# <a name="migrating-lync-online-users-to-lync-on-premises-in-lync-server-2013"></a>Миграция пользователей Lync Online в локальную среду Lync в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2015-11-13_

<div class="">


> [!IMPORTANT]  
> Эти действия необходимы только для переноса учетных записей пользователей, изначально включенных для Lync в Lync Online, перед развертыванием локального компьютера Lync. Чтобы переместить пользователей, изначально подключенных к локальной среде Lync, а затем переместить их в Lync Online, ознакомьтесь со статьей <A href="lync-server-2013-administering-users-in-a-hybrid-deployment.md">Администрирование пользователей в гибридном развертывании Lync Server 2013</A>.<BR>Кроме того, все перемещаемые пользователи должны иметь учетные записи в локальной службе Active Directory.



</div>

<div>

## <a name="migrating-user-accounts-originally-enabled-in-lync-online-to-lync-on-premises"></a>Перенос учетных записей пользователей, изначально включенных в Lync Online, в локальную среду Lync

1.  Сначала убедитесь, что ваша организация настроена для гибридной среды.
    
      - Установите средство синхронизации Azure Active Directory. Дополнительные сведения см. в статье <https://social.technet.microsoft.com/wiki/contents/articles/19098.howto-install-the-windows-azure-active-directory-sync-tool.aspx>.
    
      - Чтобы разрешить пользователям использовать единый вход для Lync Online, установите службы федерации Active Directory <https://social.technet.microsoft.com/wiki/contents/articles/1011.active-directory-federation-services-ad-fs-overview.aspx> .
    
      - В локальном развертывании в командной консоли Lync Server введите следующие командлеты, чтобы создать поставщика услуг хостинга для Lync Online:
        
           ```PowerShell
           Set-CsAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -UseDnsSrvRouting -EnablePartnerDiscovery $true
           ```
        
           ```PowerShell
            New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
           ```

2.  Убедитесь, что на локальных пограничных серверах есть цепочка сертификатов, обеспечивающая подключение к Lync Online, как показано в следующей таблице. Эту цепочку можно загрузить здесь: https://support.office.com/article/office-365-certificate-chains-0c03e6b3-e73f-4316-9e2b-bf4091ae96bb


    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Сертификат</th>
    <th>Хранилище сертификатов</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Baltimore CyberTrust Root</p></td>
    <td><p>Доверенный корневой ЦС</p></td>
    </tr>
    <tr class="even">
    <td><p>Microsoft Internet Authority (новый сертификат ЦС)</p></td>
    <td><p>Промежуточный ЦС</p></td>
    </tr>
    <tr class="odd">
    <td><p>MSIT Machine auth CA2 (новый выпуск CA2)</p></td>
    <td><p>Промежуточный ЦС</p></td>
    </tr>
    </tbody>
    </table>

3.  В локальной службе Active Directory включите затронутые учетные записи пользователей для локальной среды Lync. Это можно сделать для отдельного пользователя, введя следующий командлет:
    
        Enable-CsUser
        -Identity "username" 
        -SipAddress "sip: username@contoso.com"
        -HostingProviderProxyFqdn "sipfed.online.lync.com"
    
    Или можно создать сценарий, считывающий имена пользователей из файла и предоставляющий их в качестве входных данных для командлета Enable-CsUser:
    
        Enable-CsUser
        -Identity $Identity 
        -SipAddress $SipAddress 
        -HostingProviderProxyFqdn "sipfed.online.lync.com"

4.  Запустите DirSync, чтобы синхронизировать пользователей Lync Online с обновленными локальными пользователями Lync.

5.  Обновите некоторые записи DNS, чтобы направить весь трафик SIP в локальную среду Lync:
    
      - Обновите запись **Lyncdiscover.contoso.com** A, УКАЗАВ полное доменное имя локального обратного прокси-сервера.
    
      - Обновление *** \_ SIP *. \_ **запись SRV TLS.contoso.com, которая разрешается в общедоступный IP-адрес или виртуальный IP-адрес службы пограничной службы доступа в локальной среде Lync.
    
      - Обновление *** \_ сипфедератионтлс *. \_ **запись SRV TCP.contoso.com, которая разрешается в общедоступный IP-адрес или виртуальный IP-адрес службы пограничной службы доступа в локальной среде Lync.
    
      - Если в организации используется разделение DNS (иногда называется "Split-мозговой DNS"), убедитесь, что пользователи, разрешающие имена через внутреннюю зону DNS, направляются в пул переднего плана.

6.  Введите `Get-CsUser` командлет, чтобы проверить некоторые свойства для перемещаемых пользователей. Необходимо убедиться, что для параметра Хостингпровидерпроксифкдн задано значение, `"sipfed.online.lync.com"` а SIP-адреса настроены правильно.

7.  Перемещение пользователей Lync Online в локальную среду Lync.
    
    Чтобы переместить одного пользователя, введите следующую команду:
    
       ```PowerShell
       $cred = Get-Credential
       ```
    
       ```PowerShell
       Move-CsUser -Identity <username>@contoso.com -Target "<fe-pool>.contoso.com" -Credential $cred -HostedMigrationOverrideURL <URL>
       ```
    
    Можно переместить несколько пользователей с помощью командлета **Get-CsUSer** с параметром – Filter, чтобы выбрать пользователей с определенным свойством. Например, вы можете выбрать всех пользователей Lync Online, выполнив фильтрацию {Hosting Provider – EQ "sipfed.online.lync.om"}. Затем можно передать возвращенных пользователей в командлет **Move – CsUSer** , как показано ниже.
    
        Get-CsUser -Filter {Hosting Provider -eq "sipfed.online.lync.com"} | Move-CsUser -Target "<fe-pool>.contoso.com" -Credential $creds -HostedMigrationOverrideURL <URL>
    
    Формат URL-адреса, заданный для параметра **хостедмигратионоверридеурл** , должен быть URL-адресом пула, где запущена служба переноса, в следующем формате: *https:// \<Pool FQDN\> /HostedMigration/hostedmigrationService.svc*.
    
    Можно определить URL-адрес размещенной службы миграции, просмотрев URL-адрес панели управления Lync Online для учетной записи организации Microsoft 365 или Office 365.
    
    <div>
    
    ## <a name="to-determine-the-hosted-migration-service-url-for-your-organizaton"></a>Определение URL-адреса размещенной службы миграции для организатон
    
    1.  Войдите в организацию Microsoft 365 или Office 365 с правами администратора.
    
    2.  Откройте **центр администрирования Lync**.
    
    3.  При отображении **центра администрирования Lync** выберите и скопируйте URL-адрес в адресную строку вплоть до **Lync.com**. Пример URL-адреса выглядит примерно следующим образом:
        
        `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`
    
    4.  Замените **webdir** в URL-адресе на **"Администратор"**, что приводит к следующим действиям:
        
        `https://admin0a.online.lync.com`
    
    5.  Добавьте указанную ниже строку в URL-адрес: **/HostedMigration/hostedmigrationservice.svc**.
        
        Итоговый URL-адрес, который является значением **хостедмигратионоверридеурл**, должен выглядеть следующим образом:
        
        `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`
    
    </div>
    
    <div class="">
    

    > [!NOTE]  
    > Максимальный размер файлов журналов транзакций для базы данных rtcxds по умолчанию равен 16 ГБ. Это может быть недостаточно, если вы перемещаете большое число пользователей одновременно, особенно если зеркальное отображение включено. Чтобы обойти эту проблему, вы можете увеличить размер файла или регулярно создавать резервные копии файлов журналов. Для получения дополнительных сведений см <A class=uri href="https://support.microsoft.com/kb/2756725">https://support.microsoft.com/kb/2756725</A> .

    
    </div>

8.  Это действие не является обязательным. Если вам требуется интеграция с Exchange 2013 Online, необходимо использовать дополнительного поставщика услуг хостинга. Для получения дополнительных сведений см [Настройка локальной интеграции Lync Server 2013 с Exchange Online](lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md).

9.  Теперь пользователи перемещаются. Чтобы убедиться, что пользователь имеет правильные значения для атрибутов, показанных в следующей таблице, введите следующий командлет:
    
        Get-CsUser | fl DisplayName,HostingProvider,SipAddress,Enabled
    
    
    <table>
    <colgroup>
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Атрибут Active Directory</th>
    <th>Имя атрибута</th>
    <th>Правильное значение для пользователя Lync Online</th>
    <th>Правильное значение для локальных пользователей Lync</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>msRTCSIP — Деплойментлокатор</p></td>
    <td><p>хостингпровидер</p></td>
    <td><p>sipfed.online.lync.com</p></td>
    <td><p>SRV</p></td>
    </tr>
    <tr class="even">
    <td><p>msRTCSIP — PrimaryUserAddress</p></td>
    <td><p>SIPAddress</p></td>
    <td><p>sip:userName@contoso.com</p></td>
    <td><p>sip:userName@contoso.com</p></td>
    </tr>
    <tr class="odd">
    <td><p>msRTCSIP — UserEnabled</p></td>
    <td><p>Включено</p></td>
    <td><p>Да</p></td>
    <td><p>Да</p></td>
    </tr>
    </tbody>
    </table>


10. Для каждого перемещенного пользователя потребуется выйти из Lync, а затем войти снова. Когда они выполняют вход в систему, должны проверить свои списки контактов и при необходимости добавлять контакты.
    
    Обратите внимание, что запланированные собрания не переносятся из Lync Online в локальную среду Lync. После перемещения пользователи должны будут перепланировать эти собрания.
    
    После обновления DNS-записей, когда все пользователи перенаправляются на локальную версию, атрибут Хостингпровидер указывает пользователю Lync либо использовать записи SRV, либо направить их интерактивному поставщику "sipfed.online.lync.com".

</div>

</div>

<span> </span>

</div>

</div>

</div>

