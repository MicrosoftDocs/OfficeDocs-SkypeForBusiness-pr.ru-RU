---
title: 'Lync Server 2013: командлеты расширенной 9-1-1'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enhanced 9-1-1 cmdlets
ms:assetid: e560c688-7b34-4bd7-8104-24f390644105
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415678(v=OCS.15)
ms:contentKeyID: 48185650
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6bdea8e9aeed89a52b6e288be00afb9ed5fbeb27
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533216"
---
# <a name="enhanced-9-1-1-cmdlets-in-lync-server-2013"></a><span data-ttu-id="f22ef-102">Командлеты Enhanced 9-1-1 в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f22ef-102">Enhanced 9-1-1 cmdlets in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f22ef-103">_**Последнее изменение темы:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="f22ef-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="f22ef-104">Microsoft Lync Server 2013 поставляется с командлетами, которые позволяют реализовать усиленную реализацию 9-1-1 (E9-1-1) для решения корпоративной голосовой связи и управлять ею.</span><span class="sxs-lookup"><span data-stu-id="f22ef-104">Microsoft Lync Server 2013 ships with cmdlets that allow you to implement and manage the Enhanced 9-1-1 (E9-1-1) implementation of an Enterprise Voice solution.</span></span> <span data-ttu-id="f22ef-105">Эти командлеты используются для сопоставления точек подключения с физическими адресами и для настройки параметров, которые необходимы пользователям корпоративной голосовой связи для успешного выполнения экстренных вызовов и автоматической отправки местонахождения поставщику служб экстренной помощи.</span><span class="sxs-lookup"><span data-stu-id="f22ef-105">Use these cmdlets to map connection points to physical addresses and to configure settings required for Enterprise Voice users to successfully complete emergency calls and automatically send a location to the emergency services provider.</span></span> <span data-ttu-id="f22ef-106">Невозможно настроить E9 – 1 – 1 на панели управления Lync Server, необходимо использовать командлеты.</span><span class="sxs-lookup"><span data-stu-id="f22ef-106">You cannot configure E9-1-1 from the Lync Server Control Panel, you must use cmdlets.</span></span>

<div>

## <a name="enhanced-9-1-1-cmdlets"></a><span data-ttu-id="f22ef-107">Командлеты Enhanced 9-1-1</span><span class="sxs-lookup"><span data-stu-id="f22ef-107">Enhanced 9-1-1 Cmdlets</span></span>

<span data-ttu-id="f22ef-108">Для настройки E9-1-1 используйте следующие командлеты.</span><span class="sxs-lookup"><span data-stu-id="f22ef-108">Use the following cmdlets to configure E9-1-1.</span></span>

<span data-ttu-id="f22ef-109">**Enhanced 9-1-1**</span><span class="sxs-lookup"><span data-stu-id="f22ef-109">**Enhanced 9-1-1**</span></span>

  - <span></span>  
    <span data-ttu-id="f22ef-110">[Get — Ксенханцедемерженцисервицедисклаимер](https://technet.microsoft.com/library/Gg412877(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f22ef-110">[Get-CsEnhancedEmergencyServiceDisclaimer](https://technet.microsoft.com/library/Gg412877(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="f22ef-111">[Remove — Ксенханцедемерженцисервицедисклаимер](https://technet.microsoft.com/library/Gg425810(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f22ef-111">[Remove-CsEnhancedEmergencyServiceDisclaimer](https://technet.microsoft.com/library/Gg425810(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="f22ef-112">[Set — Ксенханцедемерженцисервицедисклаимер](https://technet.microsoft.com/library/Gg398620(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f22ef-112">[Set-CsEnhancedEmergencyServiceDisclaimer](https://technet.microsoft.com/library/Gg398620(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="f22ef-113">[Get — КслисЦивикаддресс](https://technet.microsoft.com/library/Gg398459(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f22ef-113">[Get-CsLisCivicAddress](https://technet.microsoft.com/library/Gg398459(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="f22ef-114">[Test-КслисЦивикаддресс](https://technet.microsoft.com/library/Gg425914(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f22ef-114">[Test-CsLisCivicAddress](https://technet.microsoft.com/library/Gg425914(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="f22ef-115">[Export — CsLisConfiguration](https://technet.microsoft.com/library/Gg398539(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f22ef-115">[Export-CsLisConfiguration](https://technet.microsoft.com/library/Gg398539(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="f22ef-116">[Import — CsLisConfiguration](https://technet.microsoft.com/library/Gg398380(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f22ef-116">[Import-CsLisConfiguration](https://technet.microsoft.com/library/Gg398380(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="f22ef-117">[Debug — CsLisConfiguration](https://technet.microsoft.com/library/Gg398710(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f22ef-117">[Debug-CsLisConfiguration](https://technet.microsoft.com/library/Gg398710(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="f22ef-118">[Test-CsLisConfiguration](https://technet.microsoft.com/library/Gg398497(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f22ef-118">[Test-CsLisConfiguration](https://technet.microsoft.com/library/Gg398497(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="f22ef-119">[Publish — CsLisConfiguration](https://technet.microsoft.com/library/Gg398364(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f22ef-119">[Publish-CsLisConfiguration](https://technet.microsoft.com/library/Gg398364(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="f22ef-120">[Unpublishing — CsLisConfiguration](unhttps://technet.microsoft.com/library/Gg398364(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f22ef-120">[Unpublish-CsLisConfiguration](unhttps://technet.microsoft.com/library/Gg398364(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="f22ef-121">[Get — Кслислокатион](https://technet.microsoft.com/library/Gg412834(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f22ef-121">[Get-CsLisLocation](https://technet.microsoft.com/library/Gg412834(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="f22ef-122">[Remove — Кслислокатион](https://technet.microsoft.com/library/Gg425722(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f22ef-122">[Remove-CsLisLocation](https://technet.microsoft.com/library/Gg425722(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="f22ef-123">[Set — Кслислокатион](https://technet.microsoft.com/library/Gg398757(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f22ef-123">[Set-CsLisLocation](https://technet.microsoft.com/library/Gg398757(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="f22ef-124">[Get — Кслиспорт](https://technet.microsoft.com/library/Gg398820(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f22ef-124">[Get-CsLisPort](https://technet.microsoft.com/library/Gg398820(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="f22ef-125">[Remove — Кслиспорт](https://technet.microsoft.com/library/Gg412899(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f22ef-125">[Remove-CsLisPort](https://technet.microsoft.com/library/Gg412899(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="f22ef-126">[Set — Кслиспорт](https://technet.microsoft.com/library/Gg398700(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f22ef-126">[Set-CsLisPort](https://technet.microsoft.com/library/Gg398700(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="f22ef-127">[Get — Кслиссервицепровидер](https://technet.microsoft.com/library/Gg398116(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f22ef-127">[Get-CsLisServiceProvider](https://technet.microsoft.com/library/Gg398116(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="f22ef-128">[Remove — Кслиссервицепровидер](https://technet.microsoft.com/library/Gg398904(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f22ef-128">[Remove-CsLisServiceProvider](https://technet.microsoft.com/library/Gg398904(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="f22ef-129">[Set — Кслиссервицепровидер](https://technet.microsoft.com/library/Gg425911(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f22ef-129">[Set-CsLisServiceProvider](https://technet.microsoft.com/library/Gg425911(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="f22ef-130">[Get — Кслиссубнет](https://technet.microsoft.com/library/Gg398473(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f22ef-130">[Get-CsLisSubnet](https://technet.microsoft.com/library/Gg398473(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="f22ef-131">[Remove — Кслиссубнет](https://technet.microsoft.com/library/Gg413053(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f22ef-131">[Remove-CsLisSubnet](https://technet.microsoft.com/library/Gg413053(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="f22ef-132">[Set — Кслиссубнет](https://technet.microsoft.com/library/Gg399016(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f22ef-132">[Set-CsLisSubnet](https://technet.microsoft.com/library/Gg399016(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="f22ef-133">[Get — Кслиссвитч](https://technet.microsoft.com/library/Gg425769(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f22ef-133">[Get-CsLisSwitch](https://technet.microsoft.com/library/Gg425769(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="f22ef-134">[Remove — Кслиссвитч](https://technet.microsoft.com/library/Gg398352(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f22ef-134">[Remove-CsLisSwitch](https://technet.microsoft.com/library/Gg398352(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="f22ef-135">[Set — Кслиссвитч](https://technet.microsoft.com/library/Gg412823(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f22ef-135">[Set-CsLisSwitch](https://technet.microsoft.com/library/Gg412823(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="f22ef-136">[Get — Кслисвирелессакцесспоинт](https://technet.microsoft.com/library/Gg398117(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f22ef-136">[Get-CsLisWirelessAccessPoint](https://technet.microsoft.com/library/Gg398117(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="f22ef-137">[Remove — Кслисвирелессакцесспоинт](https://technet.microsoft.com/library/Gg398461(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f22ef-137">[Remove-CsLisWirelessAccessPoint](https://technet.microsoft.com/library/Gg398461(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="f22ef-138">[Set — Кслисвирелессакцесспоинт](https://technet.microsoft.com/library/Gg412723(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f22ef-138">[Set-CsLisWirelessAccessPoint](https://technet.microsoft.com/library/Gg412723(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="f22ef-139">[Get — CsLocationPolicy](https://technet.microsoft.com/library/Gg398911(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f22ef-139">[Get-CsLocationPolicy](https://technet.microsoft.com/library/Gg398911(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="f22ef-140">[Granting — CsLocationPolicy](https://technet.microsoft.com/library/Gg413049(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f22ef-140">[Grant-CsLocationPolicy](https://technet.microsoft.com/library/Gg413049(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="f22ef-141">[New — CsLocationPolicy](https://technet.microsoft.com/library/Gg398231(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f22ef-141">[New-CsLocationPolicy](https://technet.microsoft.com/library/Gg398231(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="f22ef-142">[Remove — CsLocationPolicy](https://technet.microsoft.com/library/Gg398727(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f22ef-142">[Remove-CsLocationPolicy](https://technet.microsoft.com/library/Gg398727(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="f22ef-143">[Set — CsLocationPolicy](https://technet.microsoft.com/library/Gg412987(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f22ef-143">[Set-CsLocationPolicy](https://technet.microsoft.com/library/Gg412987(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="f22ef-144">[Test-CsLocationPolicy](https://technet.microsoft.com/library/Gg425962(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f22ef-144">[Test-CsLocationPolicy](https://technet.microsoft.com/library/Gg425962(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="f22ef-145">[Get — CsNetworkSite](https://technet.microsoft.com/library/Gg398766(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f22ef-145">[Get-CsNetworkSite](https://technet.microsoft.com/library/Gg398766(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="f22ef-146">[New — CsNetworkSite](https://technet.microsoft.com/library/Gg398365(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f22ef-146">[New-CsNetworkSite](https://technet.microsoft.com/library/Gg398365(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="f22ef-147">[Remove — CsNetworkSite](https://technet.microsoft.com/library/Gg398135(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f22ef-147">[Remove-CsNetworkSite](https://technet.microsoft.com/library/Gg398135(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="f22ef-148">[Set — CsNetworkSite](https://technet.microsoft.com/library/Gg398295(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f22ef-148">[Set-CsNetworkSite](https://technet.microsoft.com/library/Gg398295(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f22ef-149">См. также</span><span class="sxs-lookup"><span data-stu-id="f22ef-149">See Also</span></span>


[<span data-ttu-id="f22ef-150">Блог Lync Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="f22ef-150">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

