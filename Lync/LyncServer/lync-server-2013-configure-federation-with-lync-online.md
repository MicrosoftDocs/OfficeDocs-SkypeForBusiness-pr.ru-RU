---
title: 'Lync Server 2013: Настройка Федерации с Lync Online'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure federation with Lync Online
ms:assetid: a10bd1d5-c003-46db-9f57-7d55d3fa08da
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205126(v=OCS.15)
ms:contentKeyID: 48184946
ms.date: 08/15/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2ce178e57b850ee4003f2596ee075d68ea14e00a
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221159"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-federation-of-lync-server-2013-with-lync-online"></a>Настройка Федерации Lync Server 2013 с помощью Lync Online

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2016-08-15_

Выполните действия, описанные в этом разделе, чтобы настроить взаимодействие между локальным развертыванием и Skype для бизнеса Online.

<span id="a"></span>

<div>

## <a name="configure-your-on-premises-edge-service-for-federation-with-skype-for-business-online"></a>Настройка локальной пограничной службы для Федерации со Skype для бизнеса Online

Федерация позволяет пользователям в локальном развертывании общаться с Microsoft 365 или Office 365 для пользователей в вашей организации. Чтобы настроить федерацию, выполните следующие командлеты:

   ```powershell
    Set-CSAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -UseDnsSrvRouting -EnablePartnerDiscovery $True
   ```

   ```powershell
    New-CSHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
   ```

</div>

<span id="b"></span>

<div>

## <a name="configure-your-skype-for-business-online-tenant-for-a-shared-sip-address-space"></a>Настройка клиента Skype для бизнеса Online для общего адресного пространства SIP

SIP-адрес это уникальный идентификатор каждого пользователя в сети, аналогичный номеру телефона или адресу электронной почты. Прежде чем попытаться переместить пользователей Lync из локальной среды в Skype для бизнеса Online, необходимо настроить организацию Microsoft 365 или Office 365 для совместного использования пространства адресов SIP с локальным развертыванием. Если этот параметр не настроен, может появиться следующее сообщение об ошибке:

Move-CsUser: Хостедмигратион Fault: ошибка = (510), Description = (клиент этого пользователя не включен для общего адресного пространства SIP.)

Чтобы настроить общее адресное пространство SIP, установите удаленный сеанс PowerShell с помощью Skype для бизнеса Online, а затем выполните следующий командлет:
```powershell
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```
Чтобы установить удаленный сеанс PowerShell с Skype для бизнеса Online, сначала необходимо установить модуль Skype для бизнеса Online для Windows PowerShell, который вы можете скачать здесь: [https://go.microsoft.com/fwlink/p/?LinkId=391911](https://go.microsoft.com/fwlink/p/?linkid=391911) .

После установки модуля можно установить удаленный сеанс со следующими командлетами:

   ```powershell
    Import-Module LyncOnlineConnector
   ```

   ```powershell
    $cred = Get-Credential
   ``` 

   ```powershell
    $CSSession = New-CsOnlineSession -Credential $cred
   ```

   ```powershell
    Import-PSSession $CSSession -AllowClobber
   ```

Дополнительные сведения о том, как установить удаленный сеанс PowerShell с помощью Skype для бизнеса Online, можно узнать [в статье подключение к Skype для бизнеса Online с помощью Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).

Дополнительные сведения об использовании модуля PowerShell для Skype для бизнеса Online можно узнать [в статье Использование Windows PowerShell для управления Skype для бизнеса Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).

</div>

<div>

## <a name="see-also"></a>См. также


[New — CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/New-CsHostingProvider)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>
