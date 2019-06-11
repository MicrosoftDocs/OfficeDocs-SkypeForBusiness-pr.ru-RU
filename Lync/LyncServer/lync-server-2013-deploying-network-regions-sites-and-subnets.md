---
title: 'Lync Server 2013: развертывание регионов сети, сайтов и подсетей'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying network regions, sites, and subnets
ms:assetid: c4b75601-3538-4d07-8d23-1ad90459ae48
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994067(v=OCS.15)
ms:contentKeyID: 51803978
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e75c18a582be046755a54656e9f367edabdda3e8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834531"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-network-regions-sites-and-subnets-in-lync-server-2013"></a><span data-ttu-id="e2b6c-102">Развертывание регионов сети, сайтов и подсетей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e2b6c-102">Deploying network regions, sites, and subnets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e2b6c-103">_**Тема последнего изменения:** 2013-03-12_</span><span class="sxs-lookup"><span data-stu-id="e2b6c-103">_**Topic Last Modified:** 2013-03-12_</span></span>

<span data-ttu-id="e2b6c-104">После развертывания корпоративной голосовой связи необходимо настроить следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="e2b6c-104">Once Enterprise Voice is deployed, you need to configure:</span></span>

  - <span data-ttu-id="e2b6c-105">Регионы сети</span><span class="sxs-lookup"><span data-stu-id="e2b6c-105">Network regions</span></span>

  - <span data-ttu-id="e2b6c-106">Сетевые сайты</span><span class="sxs-lookup"><span data-stu-id="e2b6c-106">Network sites</span></span>

  - <span data-ttu-id="e2b6c-107">Сетевые подсети</span><span class="sxs-lookup"><span data-stu-id="e2b6c-107">Network subnets</span></span>

<div>

## <a name="define-network-regions"></a><span data-ttu-id="e2b6c-108">Определение регионов сети</span><span class="sxs-lookup"><span data-stu-id="e2b6c-108">Define Network Regions</span></span>

<span data-ttu-id="e2b6c-109">С помощью команды Lync Server Windows PowerShell, панели управления New-Кснетворкрегион или Lync Server можно определять регионы сети.</span><span class="sxs-lookup"><span data-stu-id="e2b6c-109">Use the Lync Server Windows PowerShell command, New-CsNetworkRegion, or Lync Server Control Panel to define network regions.</span></span>

    New-CsNetworkRegion -NetworkRegionID <region ID> -CentralSite <site ID>

<span data-ttu-id="e2b6c-110">Дополнительные сведения можно найти в разделе [New-кснетворкрегион](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion).</span><span class="sxs-lookup"><span data-stu-id="e2b6c-110">For more information, see [New-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion).</span></span>

<span data-ttu-id="e2b6c-111">В этом примере Следующая команда Windows PowerShell иллюстрирует сетевую область, область 1 (Индия), определенную в этом сценарии.</span><span class="sxs-lookup"><span data-stu-id="e2b6c-111">For this example, the following Windows PowerShell command illustrates the network region, region 1 (India), defined in this scenario.</span></span>

    New-CsNetworkRegion -NetworkRegionID "India" -CentralSite "India Central Site"

<div>


</div>

</div>

<div>

## <a name="define-network-sites"></a><span data-ttu-id="e2b6c-112">Определение сетевых сайтов</span><span class="sxs-lookup"><span data-stu-id="e2b6c-112">Define Network Sites</span></span>

<span data-ttu-id="e2b6c-113">С помощью команды Lync Server Windows PowerShell, New-Кснетворксите или панели управления Lync Server можно определять сетевые сайты.</span><span class="sxs-lookup"><span data-stu-id="e2b6c-113">Use the Lync Server Windows PowerShell command, New-CsNetworkSite, or the Lync Server Control Panel to define network sites.</span></span>

    New-CsNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>

<span data-ttu-id="e2b6c-114">Дополнительные сведения можно найти в разделе [New-кснетворксите](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite).</span><span class="sxs-lookup"><span data-stu-id="e2b6c-114">For more information, see [New-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite).</span></span>

<span data-ttu-id="e2b6c-115">В этом примере в приведенной ниже таблице и команде Windows PowerShell для Lync Server показаны сетевые сайты, определенные в этом сценарии.</span><span class="sxs-lookup"><span data-stu-id="e2b6c-115">For this example, the following table and Lync Server Windows PowerShell command illustrate the network sites defined in this scenario.</span></span> <span data-ttu-id="e2b6c-116">В таблице ниже приведены только те параметры, которые относятся к маршрутизации на основе местоположения.</span><span class="sxs-lookup"><span data-stu-id="e2b6c-116">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

    New-CsNetworkSite -NetworkSiteID "Delhi" -NetworkRegionID "India"
    New-CsNetworkSite -NetworkSiteID "Hyderabad" -NetworkRegionID "India"


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="e2b6c-117">Сайт 1 (Делхи)</span><span class="sxs-lookup"><span data-stu-id="e2b6c-117">Site 1 (Delhi)</span></span></th>
<th><span data-ttu-id="e2b6c-118">Сайт 2 (Хидерабад)</span><span class="sxs-lookup"><span data-stu-id="e2b6c-118">Site 2 (Hyderabad)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e2b6c-119">Идентификатор сайта</span><span class="sxs-lookup"><span data-stu-id="e2b6c-119">Site ID</span></span></p></td>
<td><p><span data-ttu-id="e2b6c-120">Сайт 1 (Делхи)</span><span class="sxs-lookup"><span data-stu-id="e2b6c-120">Site 1 (Delhi)</span></span></p></td>
<td><p><span data-ttu-id="e2b6c-121">Сайт 2 (Хидерабад)</span><span class="sxs-lookup"><span data-stu-id="e2b6c-121">Site 2 (Hyderabad)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2b6c-122">КОД региона</span><span class="sxs-lookup"><span data-stu-id="e2b6c-122">Region ID</span></span></p></td>
<td><p><span data-ttu-id="e2b6c-123">Регион 1 (Индия)</span><span class="sxs-lookup"><span data-stu-id="e2b6c-123">Region 1 (India)</span></span></p></td>
<td><p><span data-ttu-id="e2b6c-124">Регион 1 (Индия)</span><span class="sxs-lookup"><span data-stu-id="e2b6c-124">Region 1 (India)</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="define-network-subnets"></a><span data-ttu-id="e2b6c-125">Определение подсетей сети</span><span class="sxs-lookup"><span data-stu-id="e2b6c-125">Define Network Subnets</span></span>

<span data-ttu-id="e2b6c-126">С помощью команды Lync Server Windows PowerShell, New-Кснетворксубнет или панели управления Lync Server можно определять сетевые подсети и назначать их сетевым сайтам.</span><span class="sxs-lookup"><span data-stu-id="e2b6c-126">Use the Lync Server Windows PowerShell command, New-CsNetworkSubnet, or the Lync Server Control Panel to define network subnets and assign them to network sites.</span></span>

    New-CsNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>

<span data-ttu-id="e2b6c-127">Дополнительные сведения можно найти в разделе [New-кснетворксубнет](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span><span class="sxs-lookup"><span data-stu-id="e2b6c-127">For more information, see [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span></span>

<span data-ttu-id="e2b6c-128">В этом примере приведенная ниже таблица и команды Windows PowerShell иллюстрируют Назначение сетевых подсетей сетевым сайтам, Делхи и Хидерабад, определенным в этом сценарии.</span><span class="sxs-lookup"><span data-stu-id="e2b6c-128">For this example, the following table and Windows PowerShell commands illustrate the assignment of network subnets to the network sites, Delhi and Hyderabad, defined in this scenario.</span></span> <span data-ttu-id="e2b6c-129">В таблице ниже приведены только те параметры, которые относятся к маршрутизации на основе местоположения.</span><span class="sxs-lookup"><span data-stu-id="e2b6c-129">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

    New-CsNetworkSubnet -SubnetID "192.168.0.0" -MaskBits "24" -NetworkSiteID "Delhi"
    New-CsNetworkSubnet -SubnetID "192.168.1.0" -MaskBits "24" -NetworkSiteID "Hyderabad"


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="e2b6c-130">Сайт 1 (Делхи)</span><span class="sxs-lookup"><span data-stu-id="e2b6c-130">Site 1 (Delhi)</span></span></th>
<th><span data-ttu-id="e2b6c-131">Сайт 2 (Хидерабад)</span><span class="sxs-lookup"><span data-stu-id="e2b6c-131">Site 2 (Hyderabad)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e2b6c-132">КОД подсети</span><span class="sxs-lookup"><span data-stu-id="e2b6c-132">Subnet ID</span></span></p></td>
<td><p><span data-ttu-id="e2b6c-133">172.16.0.0</span><span class="sxs-lookup"><span data-stu-id="e2b6c-133">192.168.0.0</span></span></p></td>
<td><p><span data-ttu-id="e2b6c-134">192.168.1.0</span><span class="sxs-lookup"><span data-stu-id="e2b6c-134">192.168.1.0</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2b6c-135">Маски</span><span class="sxs-lookup"><span data-stu-id="e2b6c-135">Mask</span></span></p></td>
<td><p><span data-ttu-id="e2b6c-136">24</span><span class="sxs-lookup"><span data-stu-id="e2b6c-136">24</span></span></p></td>
<td><p><span data-ttu-id="e2b6c-137">24</span><span class="sxs-lookup"><span data-stu-id="e2b6c-137">24</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2b6c-138">Идентификатор сайта</span><span class="sxs-lookup"><span data-stu-id="e2b6c-138">Site ID</span></span></p></td>
<td><p><span data-ttu-id="e2b6c-139">Сайт 1 (Делхи)</span><span class="sxs-lookup"><span data-stu-id="e2b6c-139">Site 1 (Delhi)</span></span></p></td>
<td><p><span data-ttu-id="e2b6c-140">Сайт 2 (Хидерабад)</span><span class="sxs-lookup"><span data-stu-id="e2b6c-140">Site 2 (Hyderabad)</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e2b6c-141">См. также</span><span class="sxs-lookup"><span data-stu-id="e2b6c-141">See Also</span></span>


[<span data-ttu-id="e2b6c-142">Настройка маршрутизации на основе расположения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e2b6c-142">Configuring Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

