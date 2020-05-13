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

# <a name="configure-federation-of-lync-server-2013-with-lync-online"></a><span data-ttu-id="0103a-102">Настройка Федерации Lync Server 2013 с помощью Lync Online</span><span class="sxs-lookup"><span data-stu-id="0103a-102">Configure federation of Lync Server 2013 with Lync Online</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0103a-103">_**Последнее изменение темы:** 2016-08-15_</span><span class="sxs-lookup"><span data-stu-id="0103a-103">_**Topic Last Modified:** 2016-08-15_</span></span>

<span data-ttu-id="0103a-104">Выполните действия, описанные в этом разделе, чтобы настроить взаимодействие между локальным развертыванием и Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="0103a-104">Follow the steps in this section to configure interoperability between your on-premises deployment and Skype for Business Online.</span></span>

<span id="a"></span>

<div>

## <a name="configure-your-on-premises-edge-service-for-federation-with-skype-for-business-online"></a><span data-ttu-id="0103a-105">Настройка локальной пограничной службы для Федерации со Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="0103a-105">Configure Your On-Premises Edge Service for Federation with Skype for Business Online</span></span>

<span data-ttu-id="0103a-106">Федерация позволяет пользователям в локальном развертывании общаться с Microsoft 365 или Office 365 для пользователей в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="0103a-106">Federation allows users in your on-premises deployment to communicate with Microsoft 365 or Office 365 users in your organization.</span></span> <span data-ttu-id="0103a-107">Чтобы настроить федерацию, выполните следующие командлеты:</span><span class="sxs-lookup"><span data-stu-id="0103a-107">To configure federation, run the following cmdlets:</span></span>

   ```powershell
    Set-CSAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -UseDnsSrvRouting -EnablePartnerDiscovery $True
   ```

   ```powershell
    New-CSHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
   ```

</div>

<span id="b"></span>

<div>

## <a name="configure-your-skype-for-business-online-tenant-for-a-shared-sip-address-space"></a><span data-ttu-id="0103a-108">Настройка клиента Skype для бизнеса Online для общего адресного пространства SIP</span><span class="sxs-lookup"><span data-stu-id="0103a-108">Configure Your Skype for Business Online Tenant for a Shared SIP Address Space</span></span>

<span data-ttu-id="0103a-109">SIP-адрес это уникальный идентификатор каждого пользователя в сети, аналогичный номеру телефона или адресу электронной почты.</span><span class="sxs-lookup"><span data-stu-id="0103a-109">A Session Initiation Protocol (SIP) address is a unique identifier for each user on a network, similar to a phone number or an email address.</span></span> <span data-ttu-id="0103a-110">Прежде чем попытаться переместить пользователей Lync из локальной среды в Skype для бизнеса Online, необходимо настроить организацию Microsoft 365 или Office 365 для совместного использования пространства адресов SIP с локальным развертыванием.</span><span class="sxs-lookup"><span data-stu-id="0103a-110">Before you try to move Lync users from on-premises to Skype for Business Online, you’ll need to configure your Microsoft 365 or Office 365 organization to share the Shared Session Initiation Protocol (SIP) address space with your on-premises deployment.</span></span> <span data-ttu-id="0103a-111">Если этот параметр не настроен, может появиться следующее сообщение об ошибке:</span><span class="sxs-lookup"><span data-stu-id="0103a-111">If this is not configured, you may see the following error message:</span></span>

<span data-ttu-id="0103a-112">Move-CsUser: Хостедмигратион Fault: ошибка = (510), Description = (клиент этого пользователя не включен для общего адресного пространства SIP.)</span><span class="sxs-lookup"><span data-stu-id="0103a-112">Move-CsUser : HostedMigration fault: Error=(510), Description=(This user’s tenant is not enabled for shared sip address space.)</span></span>

<span data-ttu-id="0103a-113">Чтобы настроить общее адресное пространство SIP, установите удаленный сеанс PowerShell с помощью Skype для бизнеса Online, а затем выполните следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="0103a-113">To configure a shared SIP address space, establish a remote PowerShell session with Skype for Business Online, and then run the following cmdlet:</span></span>
```powershell
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```
<span data-ttu-id="0103a-114">Чтобы установить удаленный сеанс PowerShell с Skype для бизнеса Online, сначала необходимо установить модуль Skype для бизнеса Online для Windows PowerShell, который вы можете скачать здесь: [https://go.microsoft.com/fwlink/p/?LinkId=391911](https://go.microsoft.com/fwlink/p/?linkid=391911) .</span><span class="sxs-lookup"><span data-stu-id="0103a-114">To establish a remote PowerShell session with Skype for Business Online, you first need to install the Skype for Business Online module for Windows PowerShell, which you can get here: [https://go.microsoft.com/fwlink/p/?LinkId=391911](https://go.microsoft.com/fwlink/p/?linkid=391911).</span></span>

<span data-ttu-id="0103a-115">После установки модуля можно установить удаленный сеанс со следующими командлетами:</span><span class="sxs-lookup"><span data-stu-id="0103a-115">After you install the module, you can establish a remote session with the following cmdlets:</span></span>

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

<span data-ttu-id="0103a-116">Дополнительные сведения о том, как установить удаленный сеанс PowerShell с помощью Skype для бизнеса Online, можно узнать [в статье подключение к Skype для бизнеса Online с помощью Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="0103a-116">For more information about how to establish a remote PowerShell session with Skype for Business Online, see [Connecting to Skype for Business Online by using Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>

<span data-ttu-id="0103a-117">Дополнительные сведения об использовании модуля PowerShell для Skype для бизнеса Online можно узнать [в статье Использование Windows PowerShell для управления Skype для бизнеса Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="0103a-117">For more information about using the Skype for Business Online PowerShell module, see [Using Windows PowerShell to manage Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0103a-118">См. также</span><span class="sxs-lookup"><span data-stu-id="0103a-118">See Also</span></span>


[<span data-ttu-id="0103a-119">New — CsHostingProvider</span><span class="sxs-lookup"><span data-stu-id="0103a-119">New-CsHostingProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsHostingProvider)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>
