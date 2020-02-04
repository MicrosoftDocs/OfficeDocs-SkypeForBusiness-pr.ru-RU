---
title: 'Lync Server 2013: Настройка Федерации с помощью Lync Online'
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
ms.openlocfilehash: ba9179f05918504df15a18b35b9c411f23919330
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726579"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-federation-of-lync-server-2013-with-lync-online"></a><span data-ttu-id="a4989-102">Настройка Федерации Lync Server 2013 с помощью Lync Online</span><span class="sxs-lookup"><span data-stu-id="a4989-102">Configure federation of Lync Server 2013 with Lync Online</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a4989-103">_**Тема последнего изменения:** 2016-08-15_</span><span class="sxs-lookup"><span data-stu-id="a4989-103">_**Topic Last Modified:** 2016-08-15_</span></span>

<span data-ttu-id="a4989-104">Выполните действия, описанные в этом разделе, чтобы настроить взаимодействие между локальным развертыванием и Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="a4989-104">Follow the steps in this section to configure interoperability between your on-premises deployment and Skype for Business Online.</span></span>

<span id="a"></span>

<div>

## <a name="configure-your-on-premises-edge-service-for-federation-with-skype-for-business-online"></a><span data-ttu-id="a4989-105">Настройка локальной службы Edge для Федерации с помощью Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="a4989-105">Configure Your On-Premises Edge Service for Federation with Skype for Business Online</span></span>

<span data-ttu-id="a4989-106">Благодаря интеграции пользователи в локальном развертывании могут взаимодействовать с пользователями Office 365 в Организации.</span><span class="sxs-lookup"><span data-stu-id="a4989-106">Federation allows users in your on-premises deployment to communicate with Office 365 users in your organization.</span></span> <span data-ttu-id="a4989-107">Чтобы настроить федерацию, выполните следующие командлеты:</span><span class="sxs-lookup"><span data-stu-id="a4989-107">To configure federation, run the following cmdlets:</span></span>

   ```powershell
    Set-CSAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -UseDnsSrvRouting -EnablePartnerDiscovery $True
   ```

   ```powershell
    New-CSHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
   ```

</div>

<span id="b"></span>

<div>

## <a name="configure-your-skype-for-business-online-tenant-for-a-shared-sip-address-space"></a><span data-ttu-id="a4989-108">Настройка клиента Skype для бизнеса Online для общего адресного пространства SIP</span><span class="sxs-lookup"><span data-stu-id="a4989-108">Configure Your Skype for Business Online Tenant for a Shared SIP Address Space</span></span>

<span data-ttu-id="a4989-109">Адрес по протоколу SIP – это уникальный идентификатор каждого пользователя в сети, подобный номеру телефона или адресу электронной почты.</span><span class="sxs-lookup"><span data-stu-id="a4989-109">A Session Initiation Protocol (SIP) address is a unique identifier for each user on a network, similar to a phone number or an email address.</span></span> <span data-ttu-id="a4989-110">Прежде чем приступить к перемещению пользователей Lync из локальной сети в Skype для бизнеса Online, необходимо настроить клиент Office 365 таким же, чтобы он предоставил доступ к адресному пространству SIP с локальным развертыванием.</span><span class="sxs-lookup"><span data-stu-id="a4989-110">Before you try to move Lync users from on-premises to Skype for Business Online, you’ll need to configure your Office 365 tenant to share the Shared Session Initiation Protocol (SIP) address space with your on-premises deployment.</span></span> <span data-ttu-id="a4989-111">Если оно не настроено, может отображаться следующее сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="a4989-111">If this is not configured, you may see the following error message:</span></span>

<span data-ttu-id="a4989-112">Move-CsUser : HostedMigration fault: Error=(510), Description=(Клиентскому приложению этого пользователя не разрешено обращение к общему адресному пространству SIP.)</span><span class="sxs-lookup"><span data-stu-id="a4989-112">Move-CsUser : HostedMigration fault: Error=(510), Description=(This user’s tenant is not enabled for shared sip address space.)</span></span>

<span data-ttu-id="a4989-113">Чтобы настроить общее адресное пространство SIP, установите удаленный сеанс PowerShell в Skype для бизнеса Online, а затем выполните следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="a4989-113">To configure a shared SIP address space, establish a remote PowerShell session with Skype for Business Online, and then run the following cmdlet:</span></span>
```powershell
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```
<span data-ttu-id="a4989-114">Чтобы установить удаленный сеанс PowerShell в Skype для бизнеса Online, необходимо сначала установить модуль Skype для бизнеса Online для Windows PowerShell, который вы можете найти ниже [http://go.microsoft.com/fwlink/p/?LinkId=391911](http://go.microsoft.com/fwlink/p/?linkid=391911).</span><span class="sxs-lookup"><span data-stu-id="a4989-114">To establish a remote PowerShell session with Skype for Business Online, you first need to install the Skype for Business Online module for Windows PowerShell, which you can get here: [http://go.microsoft.com/fwlink/p/?LinkId=391911](http://go.microsoft.com/fwlink/p/?linkid=391911).</span></span>

<span data-ttu-id="a4989-115">После установки модуля можно запустить удаленный сеанс с помощью следующих командлетов:</span><span class="sxs-lookup"><span data-stu-id="a4989-115">After you install the module, you can establish a remote session with the following cmdlets:</span></span>

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

<span data-ttu-id="a4989-116">Дополнительные сведения о том, как установить удаленный сеанс PowerShell в Skype для бизнеса Online, можно найти [в разделе Подключение к Skype для бизнеса Online с помощью Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="a4989-116">For more information about how to establish a remote PowerShell session with Skype for Business Online, see [Connecting to Skype for Business Online by using Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>

<span data-ttu-id="a4989-117">Дополнительные сведения об использовании модуля PowerShell Skype для бизнеса Online можно найти в разделе [Использование Windows PowerShell для управления Skype для бизнеса Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="a4989-117">For more information about using the Skype for Business Online PowerShell module, see [Using Windows PowerShell to manage Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a4989-118">См. также</span><span class="sxs-lookup"><span data-stu-id="a4989-118">See Also</span></span>


[<span data-ttu-id="a4989-119">New-Кшостингпровидер</span><span class="sxs-lookup"><span data-stu-id="a4989-119">New-CsHostingProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsHostingProvider)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

