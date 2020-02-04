---
title: 'Lync Server 2013: командлеты топологии'
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
ms.openlocfilehash: b7524098f256587820beaabe31a8162591ba595d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745109"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="topology-cmdlets-jn-lync-server-2013"></a><span data-ttu-id="6f384-102">Командлеты топологии JN Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6f384-102">Topology cmdlets jn Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6f384-103">_**Тема последнего изменения:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="6f384-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="6f384-104">Многие командлеты топологии, включенные в Microsoft Lync Server 2013, предназначены для использования с построителем программы установки и топологии. из-за этого есть несколько командлетов топологии, которые администраторы редко вызывают напрямую.</span><span class="sxs-lookup"><span data-stu-id="6f384-104">Many of the topology cmdlets included in Microsoft Lync Server 2013 are designed for use with Setup and Topology Builder; because of that, there are a number of topology cmdlets that administrators will rarely call directly.</span></span> <span data-ttu-id="6f384-105">Тем не менее, в некоторых случаях необходимо, чтобы администраторы использовали эти командлеты; Например, после создания новых учетных записей Kerberos необходимо запустить командлет [Enable-кстопологи](https://technet.microsoft.com/en-us/library/Gg398398(v=OCS.15)) , чтобы изменения вступили в силу.</span><span class="sxs-lookup"><span data-stu-id="6f384-105">However, there will be times when administrators will be required to use these cmdlets; for example, after creating new Kerberos accounts you must run the [Enable-CsTopology](https://technet.microsoft.com/en-us/library/Gg398398(v=OCS.15)) cmdlet to cause the changes to take effect.</span></span> <span data-ttu-id="6f384-106">Кроме того, администраторы, как правило, смогут запускать такие командлеты, как [Test-кстопологи](https://technet.microsoft.com/en-us/library/Gg398127(v=OCS.15)) и [Test-кскомпутер](https://technet.microsoft.com/en-us/library/Gg398162(v=OCS.15)) , чтобы убедиться, что Lync Server 2013 правильно установлен и работает должным образом.</span><span class="sxs-lookup"><span data-stu-id="6f384-106">In addition, administrators will likely run cmdlets such as [Test-CsTopology](https://technet.microsoft.com/en-us/library/Gg398127(v=OCS.15)) and [Test-CsComputer](https://technet.microsoft.com/en-us/library/Gg398162(v=OCS.15)) to help ensure that Lync Server 2013 has been correctly installed and is working as expected.</span></span>

<div>

## <a name="topology-cmdlets"></a><span data-ttu-id="6f384-107">Командлеты топологии</span><span class="sxs-lookup"><span data-stu-id="6f384-107">Topology Cmdlets</span></span>

<span data-ttu-id="6f384-108">Ниже приведен список командлетов, которые непосредственно управляют топологией Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6f384-108">The following is a list of cmdlets that relate directly managing your Lync Server topology:</span></span>

<span data-ttu-id="6f384-109">**Топология**</span><span class="sxs-lookup"><span data-stu-id="6f384-109">**Topology**</span></span>

  - <span></span>  
    <span data-ttu-id="6f384-110">[Get-CsPool](https://technet.microsoft.com/en-us/library/Gg398992(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6f384-110">[Get-CsPool](https://technet.microsoft.com/en-us/library/Gg398992(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="6f384-111">[Get-CsSite](https://technet.microsoft.com/en-us/library/Gg398185(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6f384-111">[Get-CsSite](https://technet.microsoft.com/en-us/library/Gg398185(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="6f384-112">[Set-CsSite](https://technet.microsoft.com/en-us/library/Gg413023(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6f384-112">[Set-CsSite](https://technet.microsoft.com/en-us/library/Gg413023(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="6f384-113">[Enable-CsTopology](https://technet.microsoft.com/en-us/library/Gg398398(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6f384-113">[Enable-CsTopology](https://technet.microsoft.com/en-us/library/Gg398398(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="6f384-114">[Get-CsTopology](https://technet.microsoft.com/en-us/library/Gg412824(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6f384-114">[Get-CsTopology](https://technet.microsoft.com/en-us/library/Gg412824(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="6f384-115">[Publish-CsTopology](https://technet.microsoft.com/en-us/library/Gg398953(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6f384-115">[Publish-CsTopology](https://technet.microsoft.com/en-us/library/Gg398953(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="6f384-116">[Test-Кстопологи](https://technet.microsoft.com/en-us/library/Gg398127(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6f384-116">[Test-CsTopology](https://technet.microsoft.com/en-us/library/Gg398127(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="6f384-117">[Export-CsConfiguration](https://technet.microsoft.com/en-us/library/Gg398627(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6f384-117">[Export-CsConfiguration](https://technet.microsoft.com/en-us/library/Gg398627(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="6f384-118">[Import-CsConfiguration](https://technet.microsoft.com/en-us/library/Gg398800(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6f384-118">[Import-CsConfiguration](https://technet.microsoft.com/en-us/library/Gg398800(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="6f384-119">[Get-CsServerVersion](https://technet.microsoft.com/en-us/library/Gg398470(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6f384-119">[Get-CsServerVersion](https://technet.microsoft.com/en-us/library/Gg398470(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="6f384-120">[Disable-CsComputer](https://technet.microsoft.com/en-us/library/Gg399023(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6f384-120">[Disable-CsComputer](https://technet.microsoft.com/en-us/library/Gg399023(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="6f384-121">[Enable-CsComputer](https://technet.microsoft.com/en-us/library/Gg412815(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6f384-121">[Enable-CsComputer](https://technet.microsoft.com/en-us/library/Gg412815(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="6f384-122">[Get-Кскомпутер](https://technet.microsoft.com/en-us/library/Gg425959(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6f384-122">[Get-CsComputer](https://technet.microsoft.com/en-us/library/Gg425959(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="6f384-123">[Test-Кскомпутер](https://technet.microsoft.com/en-us/library/Gg398162(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6f384-123">[Test-CsComputer](https://technet.microsoft.com/en-us/library/Gg398162(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="6f384-124">[Get-CsNetworkInterface](https://technet.microsoft.com/en-us/library/Gg398121(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6f384-124">[Get-CsNetworkInterface](https://technet.microsoft.com/en-us/library/Gg398121(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6f384-125">См. также</span><span class="sxs-lookup"><span data-stu-id="6f384-125">See Also</span></span>


[<span data-ttu-id="6f384-126">Блог Lync Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="6f384-126">Lync Server PowerShell Blog</span></span>](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

