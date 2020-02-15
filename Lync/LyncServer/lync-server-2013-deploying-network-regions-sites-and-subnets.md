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
ms.openlocfilehash: 46e4db701dc3d43ed30b8101ef2af5ff2e4a2ad0
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043551"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-network-regions-sites-and-subnets-in-lync-server-2013"></a><span data-ttu-id="af035-102">Развертывание областей сети, сайтов и подсетей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="af035-102">Deploying network regions, sites, and subnets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="af035-103">_**Последнее изменение темы:** 2013-03-12_</span><span class="sxs-lookup"><span data-stu-id="af035-103">_**Topic Last Modified:** 2013-03-12_</span></span>

<span data-ttu-id="af035-104">После развертывания корпоративной голосовой связи необходимо настроить следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="af035-104">Once Enterprise Voice is deployed, you need to configure:</span></span>

  - <span data-ttu-id="af035-105">Регионы сети</span><span class="sxs-lookup"><span data-stu-id="af035-105">Network regions</span></span>

  - <span data-ttu-id="af035-106">Сетевые сайты</span><span class="sxs-lookup"><span data-stu-id="af035-106">Network sites</span></span>

  - <span data-ttu-id="af035-107">Подсети сети</span><span class="sxs-lookup"><span data-stu-id="af035-107">Network subnets</span></span>

<div>

## <a name="define-network-regions"></a><span data-ttu-id="af035-108">Определение областей сети</span><span class="sxs-lookup"><span data-stu-id="af035-108">Define Network Regions</span></span>

<span data-ttu-id="af035-109">Определение областей сети с помощью команды Lync Server Windows PowerShell, панели управления New — CsNetworkRegion или Lync Server.</span><span class="sxs-lookup"><span data-stu-id="af035-109">Use the Lync Server Windows PowerShell command, New-CsNetworkRegion, or Lync Server Control Panel to define network regions.</span></span>

    New-CsNetworkRegion -NetworkRegionID <region ID> -CentralSite <site ID>

<span data-ttu-id="af035-110">Дополнительные сведения см. в статье [New – CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion).</span><span class="sxs-lookup"><span data-stu-id="af035-110">For more information, see [New-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion).</span></span>

<span data-ttu-id="af035-111">В этом примере приведенная ниже команда Windows PowerShell иллюстрирует регион сети, регион 1 (Индия), определенный в этом сценарии.</span><span class="sxs-lookup"><span data-stu-id="af035-111">For this example, the following Windows PowerShell command illustrates the network region, region 1 (India), defined in this scenario.</span></span>

    New-CsNetworkRegion -NetworkRegionID "India" -CentralSite "India Central Site"

<div>


</div>

</div>

<div>

## <a name="define-network-sites"></a><span data-ttu-id="af035-112">Определение сетевых сайтов</span><span class="sxs-lookup"><span data-stu-id="af035-112">Define Network Sites</span></span>

<span data-ttu-id="af035-113">Используйте командную консоль Lync Server Windows PowerShell, New-CsNetworkSite или панель управления Lync Server для определения сетевых сайтов.</span><span class="sxs-lookup"><span data-stu-id="af035-113">Use the Lync Server Windows PowerShell command, New-CsNetworkSite, or the Lync Server Control Panel to define network sites.</span></span>

    New-CsNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>

<span data-ttu-id="af035-114">Дополнительные сведения см. в статье [New – CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite).</span><span class="sxs-lookup"><span data-stu-id="af035-114">For more information, see [New-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite).</span></span>

<span data-ttu-id="af035-115">В этом примере приведенная ниже таблица и команда Windows PowerShell для Lync Server иллюстрируют сетевые сайты, определенные в этом сценарии.</span><span class="sxs-lookup"><span data-stu-id="af035-115">For this example, the following table and Lync Server Windows PowerShell command illustrate the network sites defined in this scenario.</span></span> <span data-ttu-id="af035-116">Только те параметры, которые относятся к маршрутизации на основе расположения, включены в таблицу для целей иллюстрации.</span><span class="sxs-lookup"><span data-stu-id="af035-116">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

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
<th><span data-ttu-id="af035-117">Сайт 1 (Нью Дели)</span><span class="sxs-lookup"><span data-stu-id="af035-117">Site 1 (Delhi)</span></span></th>
<th><span data-ttu-id="af035-118">Сайт 2 (Хидерабад)</span><span class="sxs-lookup"><span data-stu-id="af035-118">Site 2 (Hyderabad)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="af035-119">Идентификатор сайта</span><span class="sxs-lookup"><span data-stu-id="af035-119">Site ID</span></span></p></td>
<td><p><span data-ttu-id="af035-120">Сайт 1 (Нью Дели)</span><span class="sxs-lookup"><span data-stu-id="af035-120">Site 1 (Delhi)</span></span></p></td>
<td><p><span data-ttu-id="af035-121">Сайт 2 (Хидерабад)</span><span class="sxs-lookup"><span data-stu-id="af035-121">Site 2 (Hyderabad)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="af035-122">КОД региона</span><span class="sxs-lookup"><span data-stu-id="af035-122">Region ID</span></span></p></td>
<td><p><span data-ttu-id="af035-123">Регион 1 (Индия)</span><span class="sxs-lookup"><span data-stu-id="af035-123">Region 1 (India)</span></span></p></td>
<td><p><span data-ttu-id="af035-124">Регион 1 (Индия)</span><span class="sxs-lookup"><span data-stu-id="af035-124">Region 1 (India)</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="define-network-subnets"></a><span data-ttu-id="af035-125">Определение сетевых подсетей</span><span class="sxs-lookup"><span data-stu-id="af035-125">Define Network Subnets</span></span>

<span data-ttu-id="af035-126">Используйте командную консоль Lync Server Windows PowerShell New-CsNetworkSubnet или панель управления Lync Server, чтобы определить сетевые подсети и назначить их сетевым сайтам.</span><span class="sxs-lookup"><span data-stu-id="af035-126">Use the Lync Server Windows PowerShell command, New-CsNetworkSubnet, or the Lync Server Control Panel to define network subnets and assign them to network sites.</span></span>

    New-CsNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>

<span data-ttu-id="af035-127">Дополнительные сведения см. в статье [New – CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span><span class="sxs-lookup"><span data-stu-id="af035-127">For more information, see [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span></span>

<span data-ttu-id="af035-128">В этом примере приведенная ниже таблица и команды Windows PowerShell иллюстрируют Назначение сетевых подсетей сетевым сайтам, Нью Дели и Хидерабад, определенным в этом сценарии.</span><span class="sxs-lookup"><span data-stu-id="af035-128">For this example, the following table and Windows PowerShell commands illustrate the assignment of network subnets to the network sites, Delhi and Hyderabad, defined in this scenario.</span></span> <span data-ttu-id="af035-129">Только те параметры, которые относятся к маршрутизации на основе расположения, включены в таблицу для целей иллюстрации.</span><span class="sxs-lookup"><span data-stu-id="af035-129">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

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
<th><span data-ttu-id="af035-130">Сайт 1 (Нью Дели)</span><span class="sxs-lookup"><span data-stu-id="af035-130">Site 1 (Delhi)</span></span></th>
<th><span data-ttu-id="af035-131">Сайт 2 (Хидерабад)</span><span class="sxs-lookup"><span data-stu-id="af035-131">Site 2 (Hyderabad)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="af035-132">Идентификатор подсети</span><span class="sxs-lookup"><span data-stu-id="af035-132">Subnet ID</span></span></p></td>
<td><p><span data-ttu-id="af035-133">192.168.0.0</span><span class="sxs-lookup"><span data-stu-id="af035-133">192.168.0.0</span></span></p></td>
<td><p><span data-ttu-id="af035-134">192.168.1.0</span><span class="sxs-lookup"><span data-stu-id="af035-134">192.168.1.0</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="af035-135">Маска</span><span class="sxs-lookup"><span data-stu-id="af035-135">Mask</span></span></p></td>
<td><p><span data-ttu-id="af035-136">открыт</span><span class="sxs-lookup"><span data-stu-id="af035-136">24</span></span></p></td>
<td><p><span data-ttu-id="af035-137">открыт</span><span class="sxs-lookup"><span data-stu-id="af035-137">24</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="af035-138">Идентификатор сайта</span><span class="sxs-lookup"><span data-stu-id="af035-138">Site ID</span></span></p></td>
<td><p><span data-ttu-id="af035-139">Сайт 1 (Нью Дели)</span><span class="sxs-lookup"><span data-stu-id="af035-139">Site 1 (Delhi)</span></span></p></td>
<td><p><span data-ttu-id="af035-140">Сайт 2 (Хидерабад)</span><span class="sxs-lookup"><span data-stu-id="af035-140">Site 2 (Hyderabad)</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="af035-141">См. также</span><span class="sxs-lookup"><span data-stu-id="af035-141">See Also</span></span>


[<span data-ttu-id="af035-142">Настройка маршрутизации на основе расположения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="af035-142">Configuring Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

