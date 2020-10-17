---
title: 'Lync Server 2013: командлеты топологии'
description: 'Lync Server 2013: командлеты топологии.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Topology cmdlets
ms:assetid: 3ed739a7-d58d-475d-8240-fa8d2c6dc7e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415648(v=OCS.15)
ms:contentKeyID: 48183942
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7f77febaa3beb4acc25bc5bc54dd0d5585fe18fc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549115"
---
# <a name="topology-cmdlets-jn-lync-server-2013"></a><span data-ttu-id="ecab7-103">Командлеты топологии ЖН Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ecab7-103">Topology cmdlets jn Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ecab7-104">_**Последнее изменение темы:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="ecab7-104">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="ecab7-105">Многие командлеты топологии, включенные в Microsoft Lync Server 2013, предназначены для использования с программой установки и построителем топологий; из-за этого существует несколько командлетов топологии, которые администраторы редко вызывают напрямую.</span><span class="sxs-lookup"><span data-stu-id="ecab7-105">Many of the topology cmdlets included in Microsoft Lync Server 2013 are designed for use with Setup and Topology Builder; because of that, there are a number of topology cmdlets that administrators will rarely call directly.</span></span> <span data-ttu-id="ecab7-106">Тем не менее, при использовании этих командлетов будут требоваться администраторы; Например, после создания новых учетных записей Kerberos необходимо выполнить командлет [Enable – CsTopology](https://technet.microsoft.com/library/Gg398398(v=OCS.15)) , чтобы изменения вступили в силу.</span><span class="sxs-lookup"><span data-stu-id="ecab7-106">However, there will be times when administrators will be required to use these cmdlets; for example, after creating new Kerberos accounts you must run the [Enable-CsTopology](https://technet.microsoft.com/library/Gg398398(v=OCS.15)) cmdlet to cause the changes to take effect.</span></span> <span data-ttu-id="ecab7-107">Кроме того, администраторы, скорее всего, будут запускать командлеты, такие как [Test-CsTopology](https://technet.microsoft.com/library/Gg398127(v=OCS.15)) и [Test-CsComputer](https://technet.microsoft.com/library/Gg398162(v=OCS.15)) , чтобы убедиться, что Lync Server 2013 правильно установлен и работает должным образом.</span><span class="sxs-lookup"><span data-stu-id="ecab7-107">In addition, administrators will likely run cmdlets such as [Test-CsTopology](https://technet.microsoft.com/library/Gg398127(v=OCS.15)) and [Test-CsComputer](https://technet.microsoft.com/library/Gg398162(v=OCS.15)) to help ensure that Lync Server 2013 has been correctly installed and is working as expected.</span></span>

<div>

## <a name="topology-cmdlets"></a><span data-ttu-id="ecab7-108">Командлеты топологии</span><span class="sxs-lookup"><span data-stu-id="ecab7-108">Topology Cmdlets</span></span>

<span data-ttu-id="ecab7-109">Ниже приведен список командлетов, которые относятся непосредственно к управлению топологией Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ecab7-109">The following is a list of cmdlets that relate directly managing your Lync Server topology:</span></span>

<span data-ttu-id="ecab7-110">**Топология**</span><span class="sxs-lookup"><span data-stu-id="ecab7-110">**Topology**</span></span>

  - <span></span>  
    <span data-ttu-id="ecab7-111">[Get — CsPool](https://technet.microsoft.com/library/Gg398992(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ecab7-111">[Get-CsPool](https://technet.microsoft.com/library/Gg398992(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="ecab7-112">[Get — CsSite](https://technet.microsoft.com/library/Gg398185(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ecab7-112">[Get-CsSite](https://technet.microsoft.com/library/Gg398185(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ecab7-113">[Set — CsSite](https://technet.microsoft.com/library/Gg413023(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ecab7-113">[Set-CsSite](https://technet.microsoft.com/library/Gg413023(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="ecab7-114">[Enable — CsTopology](https://technet.microsoft.com/library/Gg398398(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ecab7-114">[Enable-CsTopology](https://technet.microsoft.com/library/Gg398398(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ecab7-115">[Get — CsTopology](https://technet.microsoft.com/library/Gg412824(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ecab7-115">[Get-CsTopology](https://technet.microsoft.com/library/Gg412824(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ecab7-116">[Publish — CsTopology](https://technet.microsoft.com/library/Gg398953(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ecab7-116">[Publish-CsTopology](https://technet.microsoft.com/library/Gg398953(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ecab7-117">[Test-CsTopology](https://technet.microsoft.com/library/Gg398127(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ecab7-117">[Test-CsTopology](https://technet.microsoft.com/library/Gg398127(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="ecab7-118">[Export — CsConfiguration](https://technet.microsoft.com/library/Gg398627(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ecab7-118">[Export-CsConfiguration](https://technet.microsoft.com/library/Gg398627(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ecab7-119">[Import — CsConfiguration](https://technet.microsoft.com/library/Gg398800(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ecab7-119">[Import-CsConfiguration](https://technet.microsoft.com/library/Gg398800(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="ecab7-120">[Get — Кссерверверсион](https://technet.microsoft.com/library/Gg398470(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ecab7-120">[Get-CsServerVersion](https://technet.microsoft.com/library/Gg398470(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="ecab7-121">[Disable — CsComputer](https://technet.microsoft.com/library/Gg399023(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ecab7-121">[Disable-CsComputer](https://technet.microsoft.com/library/Gg399023(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ecab7-122">[Enable — CsComputer](https://technet.microsoft.com/library/Gg412815(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ecab7-122">[Enable-CsComputer](https://technet.microsoft.com/library/Gg412815(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ecab7-123">[Get — CsComputer](https://technet.microsoft.com/library/Gg425959(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ecab7-123">[Get-CsComputer](https://technet.microsoft.com/library/Gg425959(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ecab7-124">[Test-CsComputer](https://technet.microsoft.com/library/Gg398162(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ecab7-124">[Test-CsComputer](https://technet.microsoft.com/library/Gg398162(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="ecab7-125">[Get — CsNetworkInterface](https://technet.microsoft.com/library/Gg398121(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ecab7-125">[Get-CsNetworkInterface](https://technet.microsoft.com/library/Gg398121(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ecab7-126">См. также</span><span class="sxs-lookup"><span data-stu-id="ecab7-126">See Also</span></span>


[<span data-ttu-id="ecab7-127">Блог Lync Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="ecab7-127">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

