---
title: 'Lync Server 2013: командлеты веб-конференций'
description: 'Lync Server 2013: командлеты веб-конференций.'
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
ms.openlocfilehash: be86ff4487dcd2cdc79499a81e2454d7629ea49e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573625"
---
# <a name="web-conferencing-cmdlets-in-lync-server-2013"></a><span data-ttu-id="f1327-103">Командлеты веб-конференций в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f1327-103">Web conferencing cmdlets in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f1327-104">_**Последнее изменение темы:** 2013-07-29_</span><span class="sxs-lookup"><span data-stu-id="f1327-104">_**Topic Last Modified:** 2013-07-29_</span></span>

<span data-ttu-id="f1327-105">Конференц-связь и собрания по сети являются важными элементами в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f1327-105">Conferencing and online meetings are important elements in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="f1327-106">Командлеты CsConferencingConfiguration и CsConferencingPolicy являются основными средствами администрирования для управления конференциями с помощью Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f1327-106">The CsConferencingConfiguration and CsConferencingPolicy cmdlets are the primary administrative tools for managing conferences by using Windows PowerShell.</span></span>

<div>

## <a name="web-conferencing-cmdlets"></a><span data-ttu-id="f1327-107">Web Conferencing Cmdlets</span><span class="sxs-lookup"><span data-stu-id="f1327-107">Web Conferencing Cmdlets</span></span>

<span data-ttu-id="f1327-108">Командлеты [New – CsClientPolicy](https://technet.microsoft.com/library/Gg425949(v=OCS.15)) и [Set – CsClientPolicy](https://technet.microsoft.com/library/Gg398300(v=OCS.15)) предоставляют дополнительные возможности для настройки Lync Server 2013 и управления им.</span><span class="sxs-lookup"><span data-stu-id="f1327-108">The [New-CsClientPolicy](https://technet.microsoft.com/library/Gg425949(v=OCS.15)) and [Set-CsClientPolicy](https://technet.microsoft.com/library/Gg398300(v=OCS.15)) cmdlets provide additional ways to configure and manage Lync Server 2013.</span></span>

<span data-ttu-id="f1327-109">**Веб-конференции**</span><span class="sxs-lookup"><span data-stu-id="f1327-109">**Web Conferencing**</span></span>

  - <span></span>  
    <span data-ttu-id="f1327-110">[Get — CsConferenceDisclaimer](https://technet.microsoft.com/library/Gg425714(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f1327-110">[Get-CsConferenceDisclaimer](https://technet.microsoft.com/library/Gg425714(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="f1327-111">[Remove — CsConferenceDisclaimer](https://technet.microsoft.com/library/Gg398243(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f1327-111">[Remove-CsConferenceDisclaimer](https://technet.microsoft.com/library/Gg398243(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="f1327-112">[Set — CsConferenceDisclaimer](https://technet.microsoft.com/library/Gg398776(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f1327-112">[Set-CsConferenceDisclaimer](https://technet.microsoft.com/library/Gg398776(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="f1327-113">[Set — Ксконференцесервер](https://technet.microsoft.com/library/Gg398738(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f1327-113">[Set-CsConferenceServer](https://technet.microsoft.com/library/Gg398738(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="f1327-114">[Get — CsConferencingConfiguration](https://technet.microsoft.com/library/Gg398965(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f1327-114">[Get-CsConferencingConfiguration](https://technet.microsoft.com/library/Gg398965(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="f1327-115">[New — CsConferencingConfiguration](https://technet.microsoft.com/library/Gg412967(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f1327-115">[New-CsConferencingConfiguration](https://technet.microsoft.com/library/Gg412967(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="f1327-116">[Remove — CsConferencingConfiguration](https://technet.microsoft.com/library/Gg412767(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f1327-116">[Remove-CsConferencingConfiguration](https://technet.microsoft.com/library/Gg412767(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="f1327-117">[Set — CsConferencingConfiguration](https://technet.microsoft.com/library/Gg412969(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f1327-117">[Set-CsConferencingConfiguration](https://technet.microsoft.com/library/Gg412969(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="f1327-118">[Get-CsConferencingPolicy](https://technet.microsoft.com/library/Gg398293(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f1327-118">[Get-CsConferencingPolicy](https://technet.microsoft.com/library/Gg398293(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="f1327-119">[Granting — CsConferencingPolicy](https://technet.microsoft.com/library/Gg425937(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f1327-119">[Grant-CsConferencingPolicy](https://technet.microsoft.com/library/Gg425937(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="f1327-120">[New — CsConferencingPolicy](https://technet.microsoft.com/library/Gg413019(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f1327-120">[New-CsConferencingPolicy](https://technet.microsoft.com/library/Gg413019(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="f1327-121">[Remove — CsConferencingPolicy](https://technet.microsoft.com/library/Gg398728(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f1327-121">[Remove-CsConferencingPolicy](https://technet.microsoft.com/library/Gg398728(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="f1327-122">[Set — CsConferencingPolicy](https://technet.microsoft.com/library/Gg425788(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f1327-122">[Set-CsConferencingPolicy](https://technet.microsoft.com/library/Gg425788(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="f1327-123">[Get — CsMeetingConfiguration](https://technet.microsoft.com/library/Gg425875(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f1327-123">[Get-CsMeetingConfiguration](https://technet.microsoft.com/library/Gg425875(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="f1327-124">[New — CsMeetingConfiguration](https://technet.microsoft.com/library/Gg398065(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f1327-124">[New-CsMeetingConfiguration](https://technet.microsoft.com/library/Gg398065(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="f1327-125">[Remove — CsMeetingConfiguration](https://technet.microsoft.com/library/Gg412775(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f1327-125">[Remove-CsMeetingConfiguration](https://technet.microsoft.com/library/Gg412775(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="f1327-126">[Set — CsMeetingConfiguration](https://technet.microsoft.com/library/Gg398648(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f1327-126">[Set-CsMeetingConfiguration](https://technet.microsoft.com/library/Gg398648(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="f1327-127">[Disable — CsMeetingRoom](https://technet.microsoft.com/library/JJ204723(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f1327-127">[Disable-CsMeetingRoom](https://technet.microsoft.com/library/JJ204723(v=OCS.15))</span></span>

  - <span data-ttu-id="f1327-128">[Enable — CsMeetingRoom](https://technet.microsoft.com/library/JJ205062(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f1327-128">[Enable-CsMeetingRoom](https://technet.microsoft.com/library/JJ205062(v=OCS.15))</span></span>

  - <span data-ttu-id="f1327-129">[Get — CsMeetingRoom](https://technet.microsoft.com/library/JJ205277(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f1327-129">[Get-CsMeetingRoom](https://technet.microsoft.com/library/JJ205277(v=OCS.15))</span></span>

  - <span data-ttu-id="f1327-130">[Move — CsMeetingRoom](https://technet.microsoft.com/library/JJ204889(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f1327-130">[Move-CsMeetingRoom](https://technet.microsoft.com/library/JJ204889(v=OCS.15))</span></span>

  - <span data-ttu-id="f1327-131">[Set — CsMeetingRoom](https://technet.microsoft.com/library/JJ204831(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f1327-131">[Set-CsMeetingRoom](https://technet.microsoft.com/library/JJ204831(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="f1327-132">[Test-CsASConference](https://technet.microsoft.com/library/JJ205227(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f1327-132">[Test-CsASConference](https://technet.microsoft.com/library/JJ205227(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="f1327-133">[Test-Ксавконференце](https://technet.microsoft.com/library/Gg412749(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f1327-133">[Test-CsAVConference](https://technet.microsoft.com/library/Gg412749(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="f1327-134">[Test-CsDataConference](https://technet.microsoft.com/library/JJ205219(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f1327-134">[Test-CsDataConference](https://technet.microsoft.com/library/JJ205219(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="f1327-135">[Test-Ксвебапп](https://technet.microsoft.com/library/Hh689989(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f1327-135">[Test-CsWebApp](https://technet.microsoft.com/library/Hh689989(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="f1327-136">[Test-Ксвебаппанонимаус](https://technet.microsoft.com/library/Hh690041(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f1327-136">[Test-CsWebAppAnonymous](https://technet.microsoft.com/library/Hh690041(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="f1327-137">[Test-CsWebScheduler](https://technet.microsoft.com/library/JJ204829(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f1327-137">[Test-CsWebScheduler](https://technet.microsoft.com/library/JJ204829(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f1327-138">См. также</span><span class="sxs-lookup"><span data-stu-id="f1327-138">See Also</span></span>


[<span data-ttu-id="f1327-139">Блог Lync Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="f1327-139">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

