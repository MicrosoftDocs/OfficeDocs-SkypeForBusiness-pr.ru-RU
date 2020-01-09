---
title: 'Lync Server 2013: переход пользователей Lync Online в локальное Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Migrating Lync Online users to Lync on-premises
ms:assetid: 0e29605b-db2d-4cbf-b6a9-15db6b9fdabc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn689115(v=OCS.15)
ms:contentKeyID: 62258120
ms.date: 11/13/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 47fb8d24a2bb112ab07d35097414141b9eaaa606
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991654"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrating-lync-online-users-to-lync-on-premises-in-lync-server-2013"></a>Миграция пользователей Lync Online в локальное Lync в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2015-11-13_

<div class="">


> [!IMPORTANT]  
> Эти действия необходимы только для миграции учетных записей пользователей, изначально включенных для Lync в Lync Online, до того как вы разрешаете локальное развертывание Lync. Чтобы переместить пользователей, изначально подключенных к локальной среде Lync, а затем переместить их в Lync Online, читайте в разделе <A href="lync-server-2013-administering-users-in-a-hybrid-deployment.md">Администрирование пользователей в гибридном развертывании Lync Server 2013</A>.<BR>Кроме того, у всех перемещаемых пользователей должны быть учетные записи в локальной службе каталогов Active Directory.



</div>

<div>

## <a name="migrating-user-accounts-originally-enabled-in-lync-online-to-lync-on-premises"></a>Перенос учетных записей пользователей, изначально включенных в Lync Online, в локальное Lync

1.  Сначала убедитесь в том, что ваша организация настроена для гибридного развертывания.
    
      - Установите средство синхронизации Azure Active Directory. Дополнительные сведения см. в статье <http://social.technet.microsoft.com/wiki/contents/articles/19098.howto-install-the-windows-azure-active-directory-sync-tool.aspx>.
    
      - Чтобы разрешить пользователям использовать единый вход для Lync Online, установите службы <http://social.technet.microsoft.com/wiki/contents/articles/1011.active-directory-federation-services-ad-fs-overview.aspx>федерации Active Directory.
    
      - В локальной среде Lync Server Management Shell введите следующие командлеты, чтобы создать поставщика услуг размещения для Lync Online:
        
           ```PowerShell
           Set-CsAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -UseDnsSrvRouting -EnablePartnerDiscovery $true
           ```
        
           ```PowerShell
            New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
           ```

2.  Убедитесь, что на локальных серверах пограничного сервера есть цепочка сертификатов, обеспечивающая подключение к Lync Online, как показано в приведенной ниже таблице. Вы можете загрузить эту цепь здесь:https://support.office.com/article/office-365-certificate-chains-0c03e6b3-e73f-4316-9e2b-bf4091ae96bb


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
    <td><p>Корневой Baltimore CyberTrust</p></td>
    <td><p>Доверенный корневой ЦС</p></td>
    </tr>
    <tr class="even">
    <td><p>Microsoft Internet Authority (сертификат нового ЦС)</p></td>
    <td><p>Промежуточный ЦС</p></td>
    </tr>
    <tr class="odd">
    <td><p>MSIT Machine Auth CA2 (новый выдающий ЦС2)</p></td>
    <td><p>Промежуточный ЦС</p></td>
    </tr>
    </tbody>
    </table>

3.  В локальной службе каталогов Active Directory включите затронутые учетные записи пользователей в локальной среде Lync. Для отдельных пользователей это можно сделать путем ввода следующего командлета:
    
        Enable-CsUser
        -Identity "username" 
        -SipAddress "sip: username@contoso.com"
        -HostingProviderProxyFqdn "sipfed.online.lync.com"
    
    Или можно создать сценарий для считывания имен пользователей из файла и передачи их как входных данных командлету Enable-CsUser:
    
        Enable-CsUser
        -Identity $Identity 
        -SipAddress $SipAddress 
        -HostingProviderProxyFqdn "sipfed.online.lync.com"

4.  Запустите DirSync, чтобы синхронизировать пользователей Lync Online с обновленными локальными пользователями Lync.

5.  Обновите некоторые записи DNS, чтобы направить весь трафик SIP на локальный Lync:
    
      - Обновите запись **lyncdiscover.contoso.com** A, указав полное доменное имя локального обратного прокси-сервера.
    
      - Обновите версию ***\_SIP *\_ . tls.contoso.com** SRV-запись, разрешаемая на общедоступный IP-адрес или виртуальную ЛС для службы Edge Access в локальной среде Lync.
    
      - Обновите ***\_сипфедератионтлс *.\_ tcp.contoso.com** SRV-запись, разрешаемая на общедоступный IP-адрес или виртуальную ЛС для службы Edge Access в локальной среде Lync.
    
      - Если в организации используется комбинированная DNS (иногда называется "разделенной DNS"), убедитесь, что пользователи, разрешающие имена во внутренней зоне DNS, направляются в интерфейсный пул.

6.  Введите `Get-CsUser` командлет для проверки некоторых свойств пользователей, которых вы хотите переместить. Необходимо убедиться в том, что в Хостингпровидерпроксифкдн задано значение `"sipfed.online.lync.com"` и правильно заданы адреса SIP.

7.  Переместить пользователей Lync Online в локальное Lync.
    
    Чтобы переместить одного пользователя, введите следующее:
    
       ```PowerShell
       $cred = Get-Credential
       ```
    
       ```PowerShell
       Move-CsUser -Identity <username>@contoso.com -Target "<fe-pool>.contoso.com" -Credential $cred -HostedMigrationOverrideURL <URL>
       ```
    
    Командлет **Get-CsUSer** позволяет переместить несколько пользователей, выбрав их по некоторому свойству. Например, вы можете выбрать всех пользователей Lync Online с помощью фильтрации для {Host Provider-EQ "sipfed.online.lync.om"}. Возвращенных пользователей можно затем передать командлету **Move-CsUSer**, как показано ниже.
    
        Get-CsUser -Filter {Hosting Provider -eq "sipfed.online.lync.com"} | Move-CsUser -Target "<fe-pool>.contoso.com" -Credential $creds -HostedMigrationOverrideURL <URL>
    
    Формат URL-адреса, заданный для параметра **хостедмигратионоверридеурл** , должен быть URL-адресом пула, на котором запущена служба размещенной миграции, в следующем формате *:\<HTTPS://FQDN\>Pool/хостедмигратион/хостедмигратионсервице.СВК*.
    
    URL-адрес службы миграции с размещением можно определить по URL-адресу панели управления Lync Online для учетной записи клиента Office 365.
    
    <div>
    
    ## <a name="to-determine-the-hosted-migration-service-url-for-your-office-365-tenant"></a>Определение URL-адреса размещенной службы миграции для своего клиента Office 365
    
    1.  Выполните вход в свое клиентское приложение Office 365 как администратор.
    
    2.  Откройте **центр администрирования Lync**.
    
    3.  В **центре администрирования Lync** выберите и скопируйте URL-адрес в адресной строке на **Lync.com**. Ниже показан возможны пример URL-адреса
        
        `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`
    
    4.  После замены фрагмента **webdir** в URL-адресе фрагментом **admin** получается следующий результат:
        
        `https://admin0a.online.lync.com`
    
    5.  Добавьте к URL-адресу следующую строку: **/HostedMigration/hostedmigrationservice.svc**.
        
        Итоговый URL-адрес, который служит значением параметра **HostedMigrationOverrideUrl**, должен выглядеть следующим образом:
        
        `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`
    
    </div>
    
    <div class="">
    

    > [!NOTE]  
    > По умолчанию максимальный размер файлов журналов транзакций базы данных rtcxds составляет 16 ГБ. Это может оказаться недостаточным для одновременного перемещения большого количества пользователей, особенно если включено зеркальное отображение. Во избежание такой ситуации можно увеличить размер файлов или регулярно создавать резервные копии файлов журналов. Дополнительные сведения см. в статье <A class=uri href="http://support.microsoft.com/kb/2756725">http://support.microsoft.com/kb/2756725</A>.

    
    </div>

8.  Это необязательный шаг. Если вам нужно интегрироваться с Exchange 2013 Online, необходимо использовать дополнительного поставщика услуг размещения. Подробности можно найти [в разделе Настройка локальной интеграции Lync Server 2013 с Exchange Online](lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md).

9.  Теперь пользователи перемещаются. Чтобы проверить, что пользователь имеет правильные значения для атрибутов, показанных в таблице ниже, введите следующий командлет:
    
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
    <td><p>msRTCSIP-DeploymentLocator</p></td>
    <td><p>HostingProvider</p></td>
    <td><p>sipfed.online.lync.com</p></td>
    <td><p>SRV:</p></td>
    </tr>
    <tr class="even">
    <td><p>msRTCSIP-PrimaryUserAddress</p></td>
    <td><p>SIPAddress</p></td>
    <td><p>sip:userName@contoso.com</p></td>
    <td><p>sip:userName@contoso.com</p></td>
    </tr>
    <tr class="odd">
    <td><p>msRTCSIP-UserEnabled</p></td>
    <td><p>Включено</p></td>
    <td><p>Верно</p></td>
    <td><p>Верно</p></td>
    </tr>
    </tbody>
    </table>


10. Каждый пользователь, который был перемещен, должен выйти из Lync, а затем снова войти в систему. При входе они должны проверить свои списки контактов и в случае необходимости добавить контакты.
    
    Обратите внимание, что запланированные собрания не переносятся из Lync Online в локальное Lync. После перемещения пользователям потребуется запланировать такие собрания заново.
    
    После того как DNS-записи обновлены и все пользователи направлены на локальные, атрибут Хостингпровидер направляет пользователю Lync команду либо использовать записи SRV, либо направить их на Интернет-провайдер "sipfed.online.lync.com".

</div>

</div>

<span> </span>

</div>

</div>

</div>

