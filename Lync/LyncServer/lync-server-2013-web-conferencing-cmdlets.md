---
title: 'Lync Server 2013: командлеты веб-конференций'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Web conferencing cmdlets
ms:assetid: dac4d934-1500-4799-be4d-82809d4e7eb3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415675(v=OCS.15)
ms:contentKeyID: 48185556
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a387760cbb7770a199b85c0e891c510fbdb2e72b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535396"
---
# <a name="web-conferencing-cmdlets-in-lync-server-2013"></a><span data-ttu-id="fae76-102">Командлеты веб-конференций в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fae76-102">Web conferencing cmdlets in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fae76-103">_**Последнее изменение темы:** 2013-07-29_</span><span class="sxs-lookup"><span data-stu-id="fae76-103">_**Topic Last Modified:** 2013-07-29_</span></span>

<span data-ttu-id="fae76-104">Конференц-связь и собрания по сети являются важными элементами в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fae76-104">Conferencing and online meetings are important elements in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="fae76-105">Командлеты CsConferencingConfiguration и CsConferencingPolicy являются основными средствами администрирования для управления конференциями с помощью Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fae76-105">The CsConferencingConfiguration and CsConferencingPolicy cmdlets are the primary administrative tools for managing conferences by using Windows PowerShell.</span></span>

<div>

## <a name="web-conferencing-cmdlets"></a><span data-ttu-id="fae76-106">Web Conferencing Cmdlets</span><span class="sxs-lookup"><span data-stu-id="fae76-106">Web Conferencing Cmdlets</span></span>

<span data-ttu-id="fae76-107">Командлеты [New – CsClientPolicy](https://technet.microsoft.com/library/Gg425949(v=OCS.15)) и [Set – CsClientPolicy](https://technet.microsoft.com/library/Gg398300(v=OCS.15)) предоставляют дополнительные возможности для настройки Lync Server 2013 и управления им.</span><span class="sxs-lookup"><span data-stu-id="fae76-107">The [New-CsClientPolicy](https://technet.microsoft.com/library/Gg425949(v=OCS.15)) and [Set-CsClientPolicy](https://technet.microsoft.com/library/Gg398300(v=OCS.15)) cmdlets provide additional ways to configure and manage Lync Server 2013.</span></span>

<span data-ttu-id="fae76-108">**Веб-конференции**</span><span class="sxs-lookup"><span data-stu-id="fae76-108">**Web Conferencing**</span></span>

  - <span></span>  
    <span data-ttu-id="fae76-109">[Get — CsConferenceDisclaimer](https://technet.microsoft.com/library/Gg425714(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fae76-109">[Get-CsConferenceDisclaimer](https://technet.microsoft.com/library/Gg425714(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="fae76-110">[Remove — CsConferenceDisclaimer](https://technet.microsoft.com/library/Gg398243(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fae76-110">[Remove-CsConferenceDisclaimer](https://technet.microsoft.com/library/Gg398243(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="fae76-111">[Set — CsConferenceDisclaimer](https://technet.microsoft.com/library/Gg398776(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fae76-111">[Set-CsConferenceDisclaimer](https://technet.microsoft.com/library/Gg398776(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="fae76-112">[Set — Ксконференцесервер](https://technet.microsoft.com/library/Gg398738(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fae76-112">[Set-CsConferenceServer](https://technet.microsoft.com/library/Gg398738(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="fae76-113">[Get — CsConferencingConfiguration](https://technet.microsoft.com/library/Gg398965(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fae76-113">[Get-CsConferencingConfiguration](https://technet.microsoft.com/library/Gg398965(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="fae76-114">[New — CsConferencingConfiguration](https://technet.microsoft.com/library/Gg412967(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fae76-114">[New-CsConferencingConfiguration](https://technet.microsoft.com/library/Gg412967(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="fae76-115">[Remove — CsConferencingConfiguration](https://technet.microsoft.com/library/Gg412767(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fae76-115">[Remove-CsConferencingConfiguration](https://technet.microsoft.com/library/Gg412767(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="fae76-116">[Set — CsConferencingConfiguration](https://technet.microsoft.com/library/Gg412969(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fae76-116">[Set-CsConferencingConfiguration](https://technet.microsoft.com/library/Gg412969(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="fae76-117">[Get-CsConferencingPolicy](https://technet.microsoft.com/library/Gg398293(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fae76-117">[Get-CsConferencingPolicy](https://technet.microsoft.com/library/Gg398293(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="fae76-118">[Granting — CsConferencingPolicy](https://technet.microsoft.com/library/Gg425937(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fae76-118">[Grant-CsConferencingPolicy](https://technet.microsoft.com/library/Gg425937(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="fae76-119">[New — CsConferencingPolicy](https://technet.microsoft.com/library/Gg413019(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fae76-119">[New-CsConferencingPolicy](https://technet.microsoft.com/library/Gg413019(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="fae76-120">[Remove — CsConferencingPolicy](https://technet.microsoft.com/library/Gg398728(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fae76-120">[Remove-CsConferencingPolicy](https://technet.microsoft.com/library/Gg398728(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="fae76-121">[Set — CsConferencingPolicy](https://technet.microsoft.com/library/Gg425788(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fae76-121">[Set-CsConferencingPolicy](https://technet.microsoft.com/library/Gg425788(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="fae76-122">[Get — CsMeetingConfiguration](https://technet.microsoft.com/library/Gg425875(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fae76-122">[Get-CsMeetingConfiguration](https://technet.microsoft.com/library/Gg425875(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="fae76-123">[New — CsMeetingConfiguration](https://technet.microsoft.com/library/Gg398065(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fae76-123">[New-CsMeetingConfiguration](https://technet.microsoft.com/library/Gg398065(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="fae76-124">[Remove — CsMeetingConfiguration](https://technet.microsoft.com/library/Gg412775(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fae76-124">[Remove-CsMeetingConfiguration](https://technet.microsoft.com/library/Gg412775(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="fae76-125">[Set — CsMeetingConfiguration](https://technet.microsoft.com/library/Gg398648(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fae76-125">[Set-CsMeetingConfiguration](https://technet.microsoft.com/library/Gg398648(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="fae76-126">[Disable — CsMeetingRoom](https://technet.microsoft.com/library/JJ204723(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fae76-126">[Disable-CsMeetingRoom](https://technet.microsoft.com/library/JJ204723(v=OCS.15))</span></span>

  - <span data-ttu-id="fae76-127">[Enable — CsMeetingRoom](https://technet.microsoft.com/library/JJ205062(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fae76-127">[Enable-CsMeetingRoom](https://technet.microsoft.com/library/JJ205062(v=OCS.15))</span></span>

  - <span data-ttu-id="fae76-128">[Get — CsMeetingRoom](https://technet.microsoft.com/library/JJ205277(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fae76-128">[Get-CsMeetingRoom](https://technet.microsoft.com/library/JJ205277(v=OCS.15))</span></span>

  - <span data-ttu-id="fae76-129">[Move — CsMeetingRoom](https://technet.microsoft.com/library/JJ204889(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fae76-129">[Move-CsMeetingRoom](https://technet.microsoft.com/library/JJ204889(v=OCS.15))</span></span>

  - <span data-ttu-id="fae76-130">[Set — CsMeetingRoom](https://technet.microsoft.com/library/JJ204831(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fae76-130">[Set-CsMeetingRoom](https://technet.microsoft.com/library/JJ204831(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="fae76-131">[Test-CsASConference](https://technet.microsoft.com/library/JJ205227(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fae76-131">[Test-CsASConference](https://technet.microsoft.com/library/JJ205227(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="fae76-132">[Test-Ксавконференце](https://technet.microsoft.com/library/Gg412749(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fae76-132">[Test-CsAVConference](https://technet.microsoft.com/library/Gg412749(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="fae76-133">[Test-CsDataConference](https://technet.microsoft.com/library/JJ205219(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fae76-133">[Test-CsDataConference](https://technet.microsoft.com/library/JJ205219(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="fae76-134">[Test-Ксвебапп](https://technet.microsoft.com/library/Hh689989(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fae76-134">[Test-CsWebApp](https://technet.microsoft.com/library/Hh689989(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="fae76-135">[Test-Ксвебаппанонимаус](https://technet.microsoft.com/library/Hh690041(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fae76-135">[Test-CsWebAppAnonymous](https://technet.microsoft.com/library/Hh690041(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="fae76-136">[Test-CsWebScheduler](https://technet.microsoft.com/library/JJ204829(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fae76-136">[Test-CsWebScheduler](https://technet.microsoft.com/library/JJ204829(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="fae76-137">См. также</span><span class="sxs-lookup"><span data-stu-id="fae76-137">See Also</span></span>


[<span data-ttu-id="fae76-138">Блог Lync Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="fae76-138">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

