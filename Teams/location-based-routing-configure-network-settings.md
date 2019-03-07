---
title: Настройка параметров сети для маршрутизации на основе расположения
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 2/1/2019
ms.topic: article
ms.reviewer: roykuntz
ms.service: msteams
search.appverid: MET150
description: Узнайте, как создать и настроить областей сети, сайты и подсети для маршрутизации на основе расположения для прямой маршрутизации.
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 67202207b5668022f4e0b33acc2d20f3c4abd7aa
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/07/2019
ms.locfileid: "30462710"
---
# <a name="configure-network-settings-for-location-based-routing"></a><span data-ttu-id="ca660-103">Настройка параметров сети для маршрутизации на основе расположения</span><span class="sxs-lookup"><span data-stu-id="ca660-103">Configure network settings for Location-Based Routing</span></span>

> [!INCLUDE [Preview customer token](includes/preview-feature.md)] 

<span data-ttu-id="ca660-104">Если вы еще не сделано, чтение, чтобы просмотреть другие действия по [Plan Location-Based маршрутизации для непосредственного](location-based-routing-plan.md) необходимо выполнить перед развертыванием параметров сети для маршрутизации на основе местоположения.</span><span class="sxs-lookup"><span data-stu-id="ca660-104">If you haven't already done so, read [Plan Location-Based Routing for Direct Routing](location-based-routing-plan.md) to review other steps you'll need to take before you deploy network settings for Location-Based Routing.</span></span>

<span data-ttu-id="ca660-105">В этой статье описывается настройка параметров сети для маршрутизации на основе местоположения.</span><span class="sxs-lookup"><span data-stu-id="ca660-105">This article describes how to configure network settings for Location-Based Routing.</span></span> <span data-ttu-id="ca660-106">После развертывания прямой маршрутизации телефонной системы в вашей организации, следующие действия, чтобы создать и настроить областей сети, сетевых сайтов и подсетей.</span><span class="sxs-lookup"><span data-stu-id="ca660-106">After you deploy Phone System Direct Routing in your organization, the next steps are to create and set up network regions, network sites, and network subnets.</span></span> <span data-ttu-id="ca660-107">Чтобы выполнить действия, описанные в этой статье, вам потребуются некоторые навыки работы с помощью командлетов PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ca660-107">To complete the steps in this article, you'll need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="ca660-108">Для получения дополнительных сведений см [Команды PowerShell](teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="ca660-108">To learn more, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

## <a name="define-network-regions"></a><span data-ttu-id="ca660-109">Определение областей сети</span><span class="sxs-lookup"><span data-stu-id="ca660-109">Define network regions</span></span>
 <span data-ttu-id="ca660-110">Область сети соединения различные части сети через несколько географических областей.</span><span class="sxs-lookup"><span data-stu-id="ca660-110">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="ca660-111">Использование ``New-CsTenantNetworkRegion`` командлета PowerShell для определения области сети.</span><span class="sxs-lookup"><span data-stu-id="ca660-111">Use the ``New-CsTenantNetworkRegion`` PowerShell cmdlet to define network regions.</span></span> <span data-ttu-id="ca660-112">Обратите внимание, что ``RegionID`` параметр — это логическое имя, которое представляет географический регион и не имеет зависимости или ограничения и ``CentralSite <site ID>`` это необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="ca660-112">Note that the ``RegionID`` parameter is a logical name that represents the geography of the region and has no dependencies or restrictions and the ``CentralSite <site ID>`` parameter is optional.</span></span> 

```
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

<span data-ttu-id="ca660-113">В этом примере мы Создание области сети с именем Индия.</span><span class="sxs-lookup"><span data-stu-id="ca660-113">In this example, we create a network region named India.</span></span> 
```
New-CsTenantNetworkRegion -NetworkRegionID "India"  
```

## <a name="define-network-sites"></a><span data-ttu-id="ca660-114">Определение сетевых узлов</span><span class="sxs-lookup"><span data-stu-id="ca660-114">Define network sites</span></span>

<span data-ttu-id="ca660-115">Использование ``New-CsTenantNetworkSite`` командлета PowerShell определение сетевых узлов.</span><span class="sxs-lookup"><span data-stu-id="ca660-115">Use the ``New-CsTenantNetworkSite`` PowerShell cmdlet to define network sites.</span></span> 

```
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```
<span data-ttu-id="ca660-116">В этом примере мы создадим два новых сетевых узлов, Delhi и Hyderabad в области Индия.</span><span class="sxs-lookup"><span data-stu-id="ca660-116">In this example, we create two new network sites, Delhi and Hyderabad, in the India region.</span></span> 
```
New-CsTenantNetworkSite -NetworkSiteID "Delhi" -NetworkRegionID "India" 
New-CsTenantNetworkSite -NetworkSiteID "Hyderabad" -NetworkRegionID "India" 
```
<span data-ttu-id="ca660-117">В следующей таблице показаны сетевых узлов, определенных в этом примере.</span><span class="sxs-lookup"><span data-stu-id="ca660-117">The following table shows the network sites defined in this example.</span></span> 

||<span data-ttu-id="ca660-118">Узел 1</span><span class="sxs-lookup"><span data-stu-id="ca660-118">Site 1</span></span> |<span data-ttu-id="ca660-119">Узел 2</span><span class="sxs-lookup"><span data-stu-id="ca660-119">Site 2</span></span> |
|---------|---------|---------|
|<span data-ttu-id="ca660-120">Идентификатор сайта</span><span class="sxs-lookup"><span data-stu-id="ca660-120">Site ID</span></span>    |    <span data-ttu-id="ca660-121">Узел 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="ca660-121">Site 1 (Delhi)</span></span>     |  <span data-ttu-id="ca660-122">Узел 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="ca660-122">Site 2 (Hyderabad)</span></span>       |
|<span data-ttu-id="ca660-123">КОД региона</span><span class="sxs-lookup"><span data-stu-id="ca660-123">Region ID</span></span>  |     <span data-ttu-id="ca660-124">Область 1 (Индия)</span><span class="sxs-lookup"><span data-stu-id="ca660-124">Region 1 (India)</span></span>    |   <span data-ttu-id="ca660-125">Область 1 (Индия)</span><span class="sxs-lookup"><span data-stu-id="ca660-125">Region 1 (India)</span></span>      |

## <a name="define-network-subnets"></a><span data-ttu-id="ca660-126">Определение подсетей</span><span class="sxs-lookup"><span data-stu-id="ca660-126">Define network subnets</span></span>

<span data-ttu-id="ca660-127">Использование ``New-CsTenantNetworkSubnet`` командлет, чтобы определить подсетей и связать их сетевых узлов.</span><span class="sxs-lookup"><span data-stu-id="ca660-127">Use the ``New-CsTenantNetworkSubnet`` cmdlet to define network subnets and associate them to network sites.</span></span> <span data-ttu-id="ca660-128">Каждый внутренней подсети может быть связано только с одного сайта.</span><span class="sxs-lookup"><span data-stu-id="ca660-128">Each internal subnet can only be associated with one site.</span></span> 
```
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID> 
```
<span data-ttu-id="ca660-129">В этом примере мы создадим связь между подсетью 192.168.0.0 и сетевым узлом Delhi и подсети 192.168.1.0 и Hyderabad сетевого узла.</span><span class="sxs-lookup"><span data-stu-id="ca660-129">In this example, we create an association between subnet 192.168.0.0 and the Delhi network site and between subnet 192.168.1.0 and the Hyderabad network site.</span></span>
```
New-CsTenantNetworkSubnet -SubnetID "192.168.0.0" -MaskBits "24" -NetworkSiteID "Delhi" 
New-CsTenantNetworkSubnet -SubnetID "192.168.1.0" -MaskBits "24" -NetworkSiteID "Hyderabad" 
```
<span data-ttu-id="ca660-130">В следующей таблице показаны подсетей, определенных в этом примере.</span><span class="sxs-lookup"><span data-stu-id="ca660-130">The following table shows the subnets defined in this example.</span></span> 

||<span data-ttu-id="ca660-131">Узел 1</span><span class="sxs-lookup"><span data-stu-id="ca660-131">Site 1</span></span> |<span data-ttu-id="ca660-132">Узел 2</span><span class="sxs-lookup"><span data-stu-id="ca660-132">Site 2</span></span> |
|---------|---------|---------|
|<span data-ttu-id="ca660-133">Идентификатор подсети</span><span class="sxs-lookup"><span data-stu-id="ca660-133">Subnet ID</span></span>   |    <span data-ttu-id="ca660-134">192.168.0.0</span><span class="sxs-lookup"><span data-stu-id="ca660-134">192.168.0.0</span></span>     |  <span data-ttu-id="ca660-135">192.168.1.0</span><span class="sxs-lookup"><span data-stu-id="ca660-135">192.168.1.0</span></span>     |
|<span data-ttu-id="ca660-136">Маска</span><span class="sxs-lookup"><span data-stu-id="ca660-136">Mask</span></span>  |     <span data-ttu-id="ca660-137">24</span><span class="sxs-lookup"><span data-stu-id="ca660-137">24</span></span>    |   <span data-ttu-id="ca660-138">24</span><span class="sxs-lookup"><span data-stu-id="ca660-138">24</span></span>      |
|<span data-ttu-id="ca660-139">Идентификатор сайта</span><span class="sxs-lookup"><span data-stu-id="ca660-139">Site ID</span></span>  | <span data-ttu-id="ca660-140">Сайт (Delhi)</span><span class="sxs-lookup"><span data-stu-id="ca660-140">Site (Delhi)</span></span> | <span data-ttu-id="ca660-141">Узел 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="ca660-141">Site 2 (Hyderabad)</span></span> |

<span data-ttu-id="ca660-142">Для нескольких подсетей можно импортировать в CSV-файл, используя следующий сценарий.</span><span class="sxs-lookup"><span data-stu-id="ca660-142">For multiple subnets, you can import a CSV file by using a script such as the following.</span></span>
```
Import-CSV C:\subnet.csv | foreach {New-CsTenantNetworkSubnet –SubnetID $_.SubnetID-MaskBits $_.Mask -NetworkSiteID $_.SiteID}  
```
<span data-ttu-id="ca660-143">В этом примере CSV-файл выглядит примерно следующим образом:</span><span class="sxs-lookup"><span data-stu-id="ca660-143">In this example, the CSV file looks something like this:</span></span>
```
Identity, Mask, SiteID 
172.11.12.0, 24, Redmond 
172.11.13.0, 24, Chicago 
172.11.14.0, 25, Vancouver 
172.11.15.0, 28, Paris
```
## <a name="define-external-subnets"></a><span data-ttu-id="ca660-144">Определить внешние подсети</span><span class="sxs-lookup"><span data-stu-id="ca660-144">Define external subnets</span></span>
<span data-ttu-id="ca660-145">Использование ``New-CsTenantTrustedIPAddress`` командлет, чтобы определить внешние подсети и назначить их к клиенту.</span><span class="sxs-lookup"><span data-stu-id="ca660-145">Use the ``New-CsTenantTrustedIPAddress`` cmdlet to define external subnets and assign them to the tenant.</span></span> <span data-ttu-id="ca660-146">Можно определить неограниченное число подсети для клиента.</span><span class="sxs-lookup"><span data-stu-id="ca660-146">You can define an unlimited number of subnets for a tenant.</span></span> 
```
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description> 
```
<span data-ttu-id="ca660-147">Например:</span><span class="sxs-lookup"><span data-stu-id="ca660-147">For example:</span></span>
```
New-CsTenantTrustedIPAddress -IPAddress 167.220.2.206 -MaskBits 30 -Description "Contoso address"  
```

## <a name="next-steps"></a><span data-ttu-id="ca660-148">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="ca660-148">Next steps</span></span>
<span data-ttu-id="ca660-149">Перейдите на [Включение зависимостью от расположения маршрутизации для непосредственного](location-based-routing-enable.md).</span><span class="sxs-lookup"><span data-stu-id="ca660-149">Go to [Enable Location-Based Routing for Direct Routing](location-based-routing-enable.md).</span></span>

### <a name="related-topics"></a><span data-ttu-id="ca660-150">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="ca660-150">Related topics</span></span>
- [<span data-ttu-id="ca660-151">Планирование маршрутизации на основе расположения для прямой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="ca660-151">Plan Location-Based Routing for Direct Routing</span></span>](location-based-routing-plan.md)
- [<span data-ttu-id="ca660-152">Терминология маршрутизации на основе расположения</span><span class="sxs-lookup"><span data-stu-id="ca660-152">Location-Based Routing terminology</span></span>](location-based-routing-terminology.md)
