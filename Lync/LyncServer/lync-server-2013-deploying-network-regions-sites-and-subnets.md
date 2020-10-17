---
title: 'Lync Server 2013: развертывание областей сети, сайтов и подсетей'
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
ms.openlocfilehash: b95d9f7e38e3169474aee33a3004b388c0b13f14
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531152"
---
# <a name="deploying-network-regions-sites-and-subnets-in-lync-server-2013"></a><span data-ttu-id="e30a5-102">Развертывание областей сети, сайтов и подсетей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e30a5-102">Deploying network regions, sites, and subnets in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e30a5-103">_**Последнее изменение темы:** 2013-03-12_</span><span class="sxs-lookup"><span data-stu-id="e30a5-103">_**Topic Last Modified:** 2013-03-12_</span></span>

<span data-ttu-id="e30a5-104">После развертывания корпоративной голосовой связи необходимо настроить следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="e30a5-104">Once Enterprise Voice is deployed, you need to configure:</span></span>

  - <span data-ttu-id="e30a5-105">Регионы сети</span><span class="sxs-lookup"><span data-stu-id="e30a5-105">Network regions</span></span>

  - <span data-ttu-id="e30a5-106">Сетевые сайты</span><span class="sxs-lookup"><span data-stu-id="e30a5-106">Network sites</span></span>

  - <span data-ttu-id="e30a5-107">Подсети сети</span><span class="sxs-lookup"><span data-stu-id="e30a5-107">Network subnets</span></span>

<div>

## <a name="define-network-regions"></a><span data-ttu-id="e30a5-108">Определение областей сети</span><span class="sxs-lookup"><span data-stu-id="e30a5-108">Define Network Regions</span></span>

<span data-ttu-id="e30a5-109">Определение областей сети с помощью команды Lync Server Windows PowerShell, панели управления New — CsNetworkRegion или Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e30a5-109">Use the Lync Server Windows PowerShell command, New-CsNetworkRegion, or Lync Server Control Panel to define network regions.</span></span>

    New-CsNetworkRegion -NetworkRegionID <region ID> -CentralSite <site ID>

<span data-ttu-id="e30a5-110">Дополнительные сведения см. в статье [New – CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion).</span><span class="sxs-lookup"><span data-stu-id="e30a5-110">For more information, see [New-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion).</span></span>

<span data-ttu-id="e30a5-111">В этом примере приведенная ниже команда Windows PowerShell иллюстрирует регион сети, регион 1 (Индия), определенный в этом сценарии.</span><span class="sxs-lookup"><span data-stu-id="e30a5-111">For this example, the following Windows PowerShell command illustrates the network region, region 1 (India), defined in this scenario.</span></span>

    New-CsNetworkRegion -NetworkRegionID "India" -CentralSite "India Central Site"

<div>


</div>

</div>

<div>

## <a name="define-network-sites"></a><span data-ttu-id="e30a5-112">Определение сетевых сайтов</span><span class="sxs-lookup"><span data-stu-id="e30a5-112">Define Network Sites</span></span>

<span data-ttu-id="e30a5-113">Используйте командную консоль Lync Server Windows PowerShell, New-CsNetworkSite или панель управления Lync Server для определения сетевых сайтов.</span><span class="sxs-lookup"><span data-stu-id="e30a5-113">Use the Lync Server Windows PowerShell command, New-CsNetworkSite, or the Lync Server Control Panel to define network sites.</span></span>

    New-CsNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>

<span data-ttu-id="e30a5-114">Дополнительные сведения см. в статье [New – CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite).</span><span class="sxs-lookup"><span data-stu-id="e30a5-114">For more information, see [New-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite).</span></span>

<span data-ttu-id="e30a5-115">В этом примере приведенная ниже таблица и команда Windows PowerShell для Lync Server иллюстрируют сетевые сайты, определенные в этом сценарии.</span><span class="sxs-lookup"><span data-stu-id="e30a5-115">For this example, the following table and Lync Server Windows PowerShell command illustrate the network sites defined in this scenario.</span></span> <span data-ttu-id="e30a5-116">Только те параметры, которые относятся к Location-Based маршрутизации, включены в таблицу для целей иллюстрации.</span><span class="sxs-lookup"><span data-stu-id="e30a5-116">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

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
<th><span data-ttu-id="e30a5-117">Сайт 1 (Нью Дели)</span><span class="sxs-lookup"><span data-stu-id="e30a5-117">Site 1 (Delhi)</span></span></th>
<th><span data-ttu-id="e30a5-118">Сайт 2 (Хидерабад)</span><span class="sxs-lookup"><span data-stu-id="e30a5-118">Site 2 (Hyderabad)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e30a5-119">Идентификатор сайта</span><span class="sxs-lookup"><span data-stu-id="e30a5-119">Site ID</span></span></p></td>
<td><p><span data-ttu-id="e30a5-120">Сайт 1 (Нью Дели)</span><span class="sxs-lookup"><span data-stu-id="e30a5-120">Site 1 (Delhi)</span></span></p></td>
<td><p><span data-ttu-id="e30a5-121">Сайт 2 (Хидерабад)</span><span class="sxs-lookup"><span data-stu-id="e30a5-121">Site 2 (Hyderabad)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e30a5-122">КОД региона</span><span class="sxs-lookup"><span data-stu-id="e30a5-122">Region ID</span></span></p></td>
<td><p><span data-ttu-id="e30a5-123">Регион 1 (Индия)</span><span class="sxs-lookup"><span data-stu-id="e30a5-123">Region 1 (India)</span></span></p></td>
<td><p><span data-ttu-id="e30a5-124">Регион 1 (Индия)</span><span class="sxs-lookup"><span data-stu-id="e30a5-124">Region 1 (India)</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="define-network-subnets"></a><span data-ttu-id="e30a5-125">Определение сетевых подсетей</span><span class="sxs-lookup"><span data-stu-id="e30a5-125">Define Network Subnets</span></span>

<span data-ttu-id="e30a5-126">Используйте командную консоль Lync Server Windows PowerShell New-CsNetworkSubnet или панель управления Lync Server, чтобы определить сетевые подсети и назначить их сетевым сайтам.</span><span class="sxs-lookup"><span data-stu-id="e30a5-126">Use the Lync Server Windows PowerShell command, New-CsNetworkSubnet, or the Lync Server Control Panel to define network subnets and assign them to network sites.</span></span>

    New-CsNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>

<span data-ttu-id="e30a5-127">Дополнительные сведения см. в статье [New – CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span><span class="sxs-lookup"><span data-stu-id="e30a5-127">For more information, see [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span></span>

<span data-ttu-id="e30a5-128">В этом примере приведенная ниже таблица и команды Windows PowerShell иллюстрируют Назначение сетевых подсетей сетевым сайтам, Нью Дели и Хидерабад, определенным в этом сценарии.</span><span class="sxs-lookup"><span data-stu-id="e30a5-128">For this example, the following table and Windows PowerShell commands illustrate the assignment of network subnets to the network sites, Delhi and Hyderabad, defined in this scenario.</span></span> <span data-ttu-id="e30a5-129">Только те параметры, которые относятся к Location-Based маршрутизации, включены в таблицу для целей иллюстрации.</span><span class="sxs-lookup"><span data-stu-id="e30a5-129">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

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
<th><span data-ttu-id="e30a5-130">Сайт 1 (Нью Дели)</span><span class="sxs-lookup"><span data-stu-id="e30a5-130">Site 1 (Delhi)</span></span></th>
<th><span data-ttu-id="e30a5-131">Сайт 2 (Хидерабад)</span><span class="sxs-lookup"><span data-stu-id="e30a5-131">Site 2 (Hyderabad)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e30a5-132">Идентификатор подсети</span><span class="sxs-lookup"><span data-stu-id="e30a5-132">Subnet ID</span></span></p></td>
<td><p><span data-ttu-id="e30a5-133">192.168.0.0</span><span class="sxs-lookup"><span data-stu-id="e30a5-133">192.168.0.0</span></span></p></td>
<td><p><span data-ttu-id="e30a5-134">192.168.1.0</span><span class="sxs-lookup"><span data-stu-id="e30a5-134">192.168.1.0</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e30a5-135">Маска</span><span class="sxs-lookup"><span data-stu-id="e30a5-135">Mask</span></span></p></td>
<td><p><span data-ttu-id="e30a5-136">открыт</span><span class="sxs-lookup"><span data-stu-id="e30a5-136">24</span></span></p></td>
<td><p><span data-ttu-id="e30a5-137">открыт</span><span class="sxs-lookup"><span data-stu-id="e30a5-137">24</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e30a5-138">Идентификатор сайта</span><span class="sxs-lookup"><span data-stu-id="e30a5-138">Site ID</span></span></p></td>
<td><p><span data-ttu-id="e30a5-139">Сайт 1 (Нью Дели)</span><span class="sxs-lookup"><span data-stu-id="e30a5-139">Site 1 (Delhi)</span></span></p></td>
<td><p><span data-ttu-id="e30a5-140">Сайт 2 (Хидерабад)</span><span class="sxs-lookup"><span data-stu-id="e30a5-140">Site 2 (Hyderabad)</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e30a5-141">См. также</span><span class="sxs-lookup"><span data-stu-id="e30a5-141">See Also</span></span>


[<span data-ttu-id="e30a5-142">Настройка маршрутизации Location-Based в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e30a5-142">Configuring Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

