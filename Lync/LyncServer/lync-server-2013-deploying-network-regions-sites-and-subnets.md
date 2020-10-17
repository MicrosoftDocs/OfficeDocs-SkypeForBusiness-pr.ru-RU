---
title: 'Lync Server 2013: развертывание областей сети, сайтов и подсетей'
description: 'Lync Server 2013: развертывание областей сети, сайтов и подсетей.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying network regions, sites, and subnets
ms:assetid: c4b75601-3538-4d07-8d23-1ad90459ae48
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994067(v=OCS.15)
ms:contentKeyID: 51803978
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1c4c08cd9b78b1439000cdb4a7bbe3ffc2f99d8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561095"
---
# <a name="deploying-network-regions-sites-and-subnets-in-lync-server-2013"></a><span data-ttu-id="81cd2-103">Развертывание областей сети, сайтов и подсетей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="81cd2-103">Deploying network regions, sites, and subnets in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="81cd2-104">_**Последнее изменение темы:** 2013-03-12_</span><span class="sxs-lookup"><span data-stu-id="81cd2-104">_**Topic Last Modified:** 2013-03-12_</span></span>

<span data-ttu-id="81cd2-105">После развертывания корпоративной голосовой связи необходимо настроить следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="81cd2-105">Once Enterprise Voice is deployed, you need to configure:</span></span>

  - <span data-ttu-id="81cd2-106">Регионы сети</span><span class="sxs-lookup"><span data-stu-id="81cd2-106">Network regions</span></span>

  - <span data-ttu-id="81cd2-107">Сетевые сайты</span><span class="sxs-lookup"><span data-stu-id="81cd2-107">Network sites</span></span>

  - <span data-ttu-id="81cd2-108">Подсети сети</span><span class="sxs-lookup"><span data-stu-id="81cd2-108">Network subnets</span></span>

<div>

## <a name="define-network-regions"></a><span data-ttu-id="81cd2-109">Определение областей сети</span><span class="sxs-lookup"><span data-stu-id="81cd2-109">Define Network Regions</span></span>

<span data-ttu-id="81cd2-110">Определение областей сети с помощью команды Lync Server Windows PowerShell, панели управления New — CsNetworkRegion или Lync Server.</span><span class="sxs-lookup"><span data-stu-id="81cd2-110">Use the Lync Server Windows PowerShell command, New-CsNetworkRegion, or Lync Server Control Panel to define network regions.</span></span>

    New-CsNetworkRegion -NetworkRegionID <region ID> -CentralSite <site ID>

<span data-ttu-id="81cd2-111">Дополнительные сведения см. в статье [New – CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion).</span><span class="sxs-lookup"><span data-stu-id="81cd2-111">For more information, see [New-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion).</span></span>

<span data-ttu-id="81cd2-112">В этом примере приведенная ниже команда Windows PowerShell иллюстрирует регион сети, регион 1 (Индия), определенный в этом сценарии.</span><span class="sxs-lookup"><span data-stu-id="81cd2-112">For this example, the following Windows PowerShell command illustrates the network region, region 1 (India), defined in this scenario.</span></span>

    New-CsNetworkRegion -NetworkRegionID "India" -CentralSite "India Central Site"

<div>


</div>

</div>

<div>

## <a name="define-network-sites"></a><span data-ttu-id="81cd2-113">Определение сетевых сайтов</span><span class="sxs-lookup"><span data-stu-id="81cd2-113">Define Network Sites</span></span>

<span data-ttu-id="81cd2-114">Используйте командную консоль Lync Server Windows PowerShell, New-CsNetworkSite или панель управления Lync Server для определения сетевых сайтов.</span><span class="sxs-lookup"><span data-stu-id="81cd2-114">Use the Lync Server Windows PowerShell command, New-CsNetworkSite, or the Lync Server Control Panel to define network sites.</span></span>

    New-CsNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>

<span data-ttu-id="81cd2-115">Дополнительные сведения см. в статье [New – CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite).</span><span class="sxs-lookup"><span data-stu-id="81cd2-115">For more information, see [New-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite).</span></span>

<span data-ttu-id="81cd2-116">В этом примере приведенная ниже таблица и команда Windows PowerShell для Lync Server иллюстрируют сетевые сайты, определенные в этом сценарии.</span><span class="sxs-lookup"><span data-stu-id="81cd2-116">For this example, the following table and Lync Server Windows PowerShell command illustrate the network sites defined in this scenario.</span></span> <span data-ttu-id="81cd2-117">Только те параметры, которые относятся к Location-Based маршрутизации, включены в таблицу для целей иллюстрации.</span><span class="sxs-lookup"><span data-stu-id="81cd2-117">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

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
<th><span data-ttu-id="81cd2-118">Сайт 1 (Нью Дели)</span><span class="sxs-lookup"><span data-stu-id="81cd2-118">Site 1 (Delhi)</span></span></th>
<th><span data-ttu-id="81cd2-119">Сайт 2 (Хидерабад)</span><span class="sxs-lookup"><span data-stu-id="81cd2-119">Site 2 (Hyderabad)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="81cd2-120">Идентификатор сайта</span><span class="sxs-lookup"><span data-stu-id="81cd2-120">Site ID</span></span></p></td>
<td><p><span data-ttu-id="81cd2-121">Сайт 1 (Нью Дели)</span><span class="sxs-lookup"><span data-stu-id="81cd2-121">Site 1 (Delhi)</span></span></p></td>
<td><p><span data-ttu-id="81cd2-122">Сайт 2 (Хидерабад)</span><span class="sxs-lookup"><span data-stu-id="81cd2-122">Site 2 (Hyderabad)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81cd2-123">КОД региона</span><span class="sxs-lookup"><span data-stu-id="81cd2-123">Region ID</span></span></p></td>
<td><p><span data-ttu-id="81cd2-124">Регион 1 (Индия)</span><span class="sxs-lookup"><span data-stu-id="81cd2-124">Region 1 (India)</span></span></p></td>
<td><p><span data-ttu-id="81cd2-125">Регион 1 (Индия)</span><span class="sxs-lookup"><span data-stu-id="81cd2-125">Region 1 (India)</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="define-network-subnets"></a><span data-ttu-id="81cd2-126">Определение сетевых подсетей</span><span class="sxs-lookup"><span data-stu-id="81cd2-126">Define Network Subnets</span></span>

<span data-ttu-id="81cd2-127">Используйте командную консоль Lync Server Windows PowerShell New-CsNetworkSubnet или панель управления Lync Server, чтобы определить сетевые подсети и назначить их сетевым сайтам.</span><span class="sxs-lookup"><span data-stu-id="81cd2-127">Use the Lync Server Windows PowerShell command, New-CsNetworkSubnet, or the Lync Server Control Panel to define network subnets and assign them to network sites.</span></span>

    New-CsNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>

<span data-ttu-id="81cd2-128">Дополнительные сведения см. в статье [New – CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span><span class="sxs-lookup"><span data-stu-id="81cd2-128">For more information, see [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span></span>

<span data-ttu-id="81cd2-129">В этом примере приведенная ниже таблица и команды Windows PowerShell иллюстрируют Назначение сетевых подсетей сетевым сайтам, Нью Дели и Хидерабад, определенным в этом сценарии.</span><span class="sxs-lookup"><span data-stu-id="81cd2-129">For this example, the following table and Windows PowerShell commands illustrate the assignment of network subnets to the network sites, Delhi and Hyderabad, defined in this scenario.</span></span> <span data-ttu-id="81cd2-130">Только те параметры, которые относятся к Location-Based маршрутизации, включены в таблицу для целей иллюстрации.</span><span class="sxs-lookup"><span data-stu-id="81cd2-130">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

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
<th><span data-ttu-id="81cd2-131">Сайт 1 (Нью Дели)</span><span class="sxs-lookup"><span data-stu-id="81cd2-131">Site 1 (Delhi)</span></span></th>
<th><span data-ttu-id="81cd2-132">Сайт 2 (Хидерабад)</span><span class="sxs-lookup"><span data-stu-id="81cd2-132">Site 2 (Hyderabad)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="81cd2-133">Идентификатор подсети</span><span class="sxs-lookup"><span data-stu-id="81cd2-133">Subnet ID</span></span></p></td>
<td><p><span data-ttu-id="81cd2-134">192.168.0.0</span><span class="sxs-lookup"><span data-stu-id="81cd2-134">192.168.0.0</span></span></p></td>
<td><p><span data-ttu-id="81cd2-135">192.168.1.0</span><span class="sxs-lookup"><span data-stu-id="81cd2-135">192.168.1.0</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81cd2-136">Маска</span><span class="sxs-lookup"><span data-stu-id="81cd2-136">Mask</span></span></p></td>
<td><p><span data-ttu-id="81cd2-137">открыт</span><span class="sxs-lookup"><span data-stu-id="81cd2-137">24</span></span></p></td>
<td><p><span data-ttu-id="81cd2-138">открыт</span><span class="sxs-lookup"><span data-stu-id="81cd2-138">24</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="81cd2-139">Идентификатор сайта</span><span class="sxs-lookup"><span data-stu-id="81cd2-139">Site ID</span></span></p></td>
<td><p><span data-ttu-id="81cd2-140">Сайт 1 (Нью Дели)</span><span class="sxs-lookup"><span data-stu-id="81cd2-140">Site 1 (Delhi)</span></span></p></td>
<td><p><span data-ttu-id="81cd2-141">Сайт 2 (Хидерабад)</span><span class="sxs-lookup"><span data-stu-id="81cd2-141">Site 2 (Hyderabad)</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="81cd2-142">См. также</span><span class="sxs-lookup"><span data-stu-id="81cd2-142">See Also</span></span>


[<span data-ttu-id="81cd2-143">Настройка маршрутизации Location-Based в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="81cd2-143">Configuring Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

