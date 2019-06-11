---
title: 'Lync Server 2013: Настройка Федерации с помощью Lync Online'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure federation with Lync Online
ms:assetid: a10bd1d5-c003-46db-9f57-7d55d3fa08da
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205126(v=OCS.15)
ms:contentKeyID: 48184946
ms.date: 08/15/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d690b21614ec416d82834761772cee05ee16f26e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841369"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-federation-of-lync-server-2013-with-lync-online"></a>Настройка Федерации Lync Server 2013 с помощью Lync Online

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2016-08-15_

Выполните действия, описанные в этом разделе, чтобы настроить взаимодействие между локальным развертыванием и Skype для бизнеса Online.

<span id="a"></span>

<div>

## <a name="configure-your-on-premises-edge-service-for-federation-with-skype-for-business-online"></a>Настройка локальной службы Edge для Федерации с помощью Skype для бизнеса Online

Благодаря интеграции пользователи в локальном развертывании могут взаимодействовать с пользователями Office 365 в Организации. Чтобы настроить федерацию, выполните следующие командлеты:

   ```
    Set-CSAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -UseDnsSrvRouting -EnablePartnerDiscovery $True
   ```

   ```
    New-CSHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
   ```

</div>

<span id="b"></span>

<div>

## <a name="configure-your-skype-for-business-online-tenant-for-a-shared-sip-address-space"></a>Настройка клиента Skype для бизнеса Online для общего адресного пространства SIP

Адрес по протоколу SIP – это уникальный идентификатор каждого пользователя в сети, подобный номеру телефона или адресу электронной почты. Прежде чем приступить к перемещению пользователей Lync из локальной сети в Skype для бизнеса Online, необходимо настроить клиент Office 365 таким же, чтобы он предоставил доступ к адресному пространству SIP с локальным развертыванием. Если оно не настроено, может отображаться следующее сообщение об ошибке.

Move-CsUser : HostedMigration fault: Error=(510), Description=(Клиентскому приложению этого пользователя не разрешено обращение к общему адресному пространству SIP.)

Чтобы настроить общее адресное пространство SIP, установите удаленный сеанс PowerShell в Skype для бизнеса Online, а затем выполните следующий командлет:

    Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true

Чтобы установить удаленный сеанс PowerShell в Skype для бизнеса Online, необходимо сначала установить модуль Skype для бизнеса Online для Windows PowerShell, который вы можете найти ниже [http://go.microsoft.com/fwlink/p/?LinkId=391911](http://go.microsoft.com/fwlink/p/?linkid=391911).

После установки модуля можно запустить удаленный сеанс с помощью следующих командлетов:

   ```
    Import-Module LyncOnlineConnector
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

Дополнительные сведения о том, как установить удаленный сеанс PowerShell в Skype для бизнеса Online, можно найти [в разделе Подключение к Skype для бизнеса Online с помощью Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).

Дополнительные сведения об использовании модуля PowerShell Skype для бизнеса Online можно найти в разделе [Использование Windows PowerShell для управления Skype для бизнеса Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).

</div>

<div>

## <a name="see-also"></a>См. также


[New-Кшостингпровидер](https://docs.microsoft.com/powershell/module/skype/New-CsHostingProvider)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

