---
title: Настройка параметров сети для маршрутизации на основе расположения
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 2/1/2019
ms.topic: article
ms.reviewer: roykuntz
audience: admin
ms.service: msteams
search.appverid: MET150
description: Сведения о том, как создавать и настраивать регионы сети, сайты и подсети для маршрутизации на основе местоположения для прямой маршрутизации.
localization_priority: Normal
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 240bbce48452edf505a61830891d0fcd6a6d199d
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2019
ms.locfileid: "37570703"
---
# <a name="configure-network-settings-for-location-based-routing"></a><span data-ttu-id="13986-103">Настройка параметров сети для маршрутизации на основе расположения</span><span class="sxs-lookup"><span data-stu-id="13986-103">Configure network settings for Location-Based Routing</span></span>

> [!INCLUDE [Preview customer token](includes/preview-feature.md)] 

<span data-ttu-id="13986-104">Если вы еще не сделали этого, прочтите [маршрут на основе местоположения для прямой маршрутизации](location-based-routing-plan.md) , чтобы просмотреть другие действия, которые необходимо выполнить перед настройкой сетевых параметров для маршрутизации на основе местоположения.</span><span class="sxs-lookup"><span data-stu-id="13986-104">If you haven't already done so, read [Plan Location-Based Routing for Direct Routing](location-based-routing-plan.md) to review other steps you'll need to take before you configure network settings for Location-Based Routing.</span></span>

<span data-ttu-id="13986-105">В этой статье описано, как настроить параметры сети для маршрутизации на основе местоположения.</span><span class="sxs-lookup"><span data-stu-id="13986-105">This article describes how to configure network settings for Location-Based Routing.</span></span> <span data-ttu-id="13986-106">После развертывания прямой маршрутизации для телефонной системы в Организации следует создать и настроить регионы сети, сетевые сайты и сетевые подсети.</span><span class="sxs-lookup"><span data-stu-id="13986-106">After you deploy Phone System Direct Routing in your organization, the next steps are to create and set up network regions, network sites, and network subnets.</span></span> <span data-ttu-id="13986-107">Для выполнения действий, описанных в этой статье, вам потребуется ознакомиться с командлетами PowerShell.</span><span class="sxs-lookup"><span data-stu-id="13986-107">To complete the steps in this article, you'll need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="13986-108">Дополнительные сведения можно найти в разделе [Общие сведения о Teams PowerShell](teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="13986-108">To learn more, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

## <a name="define-network-regions"></a><span data-ttu-id="13986-109">Определение регионов сети</span><span class="sxs-lookup"><span data-stu-id="13986-109">Define network regions</span></span>
 <span data-ttu-id="13986-110">Сетевой регион соединяет различные части сети в нескольких географических регионах.</span><span class="sxs-lookup"><span data-stu-id="13986-110">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="13986-111">Используйте командлет [New-кстенантнетворкрегион](https://docs.microsoft.com/powershell/module/skype/New-CsTenantNetworkRegion?view=skype-ps) , чтобы определить регионы сети.</span><span class="sxs-lookup"><span data-stu-id="13986-111">Use the [New-CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsTenantNetworkRegion?view=skype-ps) cmdlet to define network regions.</span></span> <span data-ttu-id="13986-112">Обратите внимание, что параметр Регионид является логическим именем, которое представляет собой географию области и не имеет зависимостей или ограничений и &lt;не является&gt; обязательным параметром идентификатора сайта централсите.</span><span class="sxs-lookup"><span data-stu-id="13986-112">Note that the RegionID parameter is a logical name that represents the geography of the region and has no dependencies or restrictions and the CentralSite &lt;site ID&gt; parameter is optional.</span></span> 

```
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

<span data-ttu-id="13986-113">В этом примере мы создаем сетевой регион с именем Индии.</span><span class="sxs-lookup"><span data-stu-id="13986-113">In this example, we create a network region named India.</span></span> 
```
New-CsTenantNetworkRegion -NetworkRegionID "India"  
```

## <a name="define-network-sites"></a><span data-ttu-id="13986-114">Определение сетевых сайтов</span><span class="sxs-lookup"><span data-stu-id="13986-114">Define network sites</span></span>

<span data-ttu-id="13986-115">С помощью командлета [New-кстенантнетворксите](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksite?view=skype-ps) можно определять сетевые сайты.</span><span class="sxs-lookup"><span data-stu-id="13986-115">Use the [New-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksite?view=skype-ps) cmdlet to define network sites.</span></span> 

```
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```
<span data-ttu-id="13986-116">В этом примере мы создаем в регионе Индии две новые сетевые сайты, Делхи и Хидерабад.</span><span class="sxs-lookup"><span data-stu-id="13986-116">In this example, we create two new network sites, Delhi and Hyderabad, in the India region.</span></span> 
```
New-CsTenantNetworkSite -NetworkSiteID "Delhi" -NetworkRegionID "India" 
New-CsTenantNetworkSite -NetworkSiteID "Hyderabad" -NetworkRegionID "India" 
```
<span data-ttu-id="13986-117">В следующей таблице показаны сетевые сайты, определенные в этом примере.</span><span class="sxs-lookup"><span data-stu-id="13986-117">The following table shows the network sites defined in this example.</span></span> 

||<span data-ttu-id="13986-118">Сайт 1</span><span class="sxs-lookup"><span data-stu-id="13986-118">Site 1</span></span> |<span data-ttu-id="13986-119">Сайт 2</span><span class="sxs-lookup"><span data-stu-id="13986-119">Site 2</span></span> |
|---------|---------|---------|
|<span data-ttu-id="13986-120">Идентификатор сайта</span><span class="sxs-lookup"><span data-stu-id="13986-120">Site ID</span></span>    |    <span data-ttu-id="13986-121">Сайт 1 (Делхи)</span><span class="sxs-lookup"><span data-stu-id="13986-121">Site 1 (Delhi)</span></span>     |  <span data-ttu-id="13986-122">Сайт 2 (Хидерабад)</span><span class="sxs-lookup"><span data-stu-id="13986-122">Site 2 (Hyderabad)</span></span>       |
|<span data-ttu-id="13986-123">КОД региона</span><span class="sxs-lookup"><span data-stu-id="13986-123">Region ID</span></span>  |     <span data-ttu-id="13986-124">Регион 1 (Индия)</span><span class="sxs-lookup"><span data-stu-id="13986-124">Region 1 (India)</span></span>    |   <span data-ttu-id="13986-125">Регион 1 (Индия)</span><span class="sxs-lookup"><span data-stu-id="13986-125">Region 1 (India)</span></span>      |

## <a name="define-network-subnets"></a><span data-ttu-id="13986-126">Определение подсетей сети</span><span class="sxs-lookup"><span data-stu-id="13986-126">Define network subnets</span></span>

<span data-ttu-id="13986-127">С помощью командлета [New-кстенантнетворксубнет](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksubnet?view=skype-ps) можно определять сетевые подсети и связывать их с сетевыми сайтами.</span><span class="sxs-lookup"><span data-stu-id="13986-127">Use the [New-CsTenantNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksubnet?view=skype-ps) cmdlet to define network subnets and associate them to network sites.</span></span> <span data-ttu-id="13986-128">Каждая внутренняя подсеть может быть связана только с одним сайтом.</span><span class="sxs-lookup"><span data-stu-id="13986-128">Each internal subnet can only be associated with one site.</span></span> 
```
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID> 
```
<span data-ttu-id="13986-129">В этом примере мы создаем связь между подсетью 192.168.0.0 и сетевым сайтом Делхи и между подсетью 2001:4898: E8:25:844E: 926f: 85ad: dd8e и на сайте Хидерабад Network.</span><span class="sxs-lookup"><span data-stu-id="13986-129">In this example, we create an association between subnet 192.168.0.0 and the Delhi network site and between subnet 2001:4898:e8:25:844e:926f:85ad:dd8e and the Hyderabad network site.</span></span>
```
New-CsTenantNetworkSubnet -SubnetID "192.168.0.0" -MaskBits "24" -NetworkSiteID "Delhi" 
New-CsTenantNetworkSubnet -SubnetID "2001:4898:e8:25:844e:926f:85ad:dd8e" -MaskBits "120" -NetworkSiteID "Hyderabad" 
```
<span data-ttu-id="13986-130">В приведенной ниже таблице указаны подсети, определенные в этом примере.</span><span class="sxs-lookup"><span data-stu-id="13986-130">The following table shows the subnets defined in this example.</span></span> 

||<span data-ttu-id="13986-131">Сайт 1</span><span class="sxs-lookup"><span data-stu-id="13986-131">Site 1</span></span> |<span data-ttu-id="13986-132">Сайт 2</span><span class="sxs-lookup"><span data-stu-id="13986-132">Site 2</span></span> |
|---------|---------|---------|
|<span data-ttu-id="13986-133">КОД подсети</span><span class="sxs-lookup"><span data-stu-id="13986-133">Subnet ID</span></span>   |    <span data-ttu-id="13986-134">172.16.0.0</span><span class="sxs-lookup"><span data-stu-id="13986-134">192.168.0.0</span></span>     |  <span data-ttu-id="13986-135">2001:4898: E8:25:844E: 926f: 85ad: dd8e</span><span class="sxs-lookup"><span data-stu-id="13986-135">2001:4898:e8:25:844e:926f:85ad:dd8e</span></span>     |
|<span data-ttu-id="13986-136">Маски</span><span class="sxs-lookup"><span data-stu-id="13986-136">Mask</span></span>  |     <span data-ttu-id="13986-137">24</span><span class="sxs-lookup"><span data-stu-id="13986-137">24</span></span>    |   <span data-ttu-id="13986-138">120</span><span class="sxs-lookup"><span data-stu-id="13986-138">120</span></span>      |
|<span data-ttu-id="13986-139">Идентификатор сайта</span><span class="sxs-lookup"><span data-stu-id="13986-139">Site ID</span></span>  | <span data-ttu-id="13986-140">Сайт (Делхи)</span><span class="sxs-lookup"><span data-stu-id="13986-140">Site (Delhi)</span></span> | <span data-ttu-id="13986-141">Сайт 2 (Хидерабад)</span><span class="sxs-lookup"><span data-stu-id="13986-141">Site 2 (Hyderabad)</span></span> |

<span data-ttu-id="13986-142">Если вы используете несколько подсетей, вы можете импортировать CSV-файл с помощью такого сценария, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="13986-142">For multiple subnets, you can import a CSV file by using a script such as the following.</span></span>
```
Import-CSV C:\subnet.csv | foreach {New-CsTenantNetworkSubnet –SubnetID $_.SubnetID-MaskBits $_.Mask -NetworkSiteID $_.SiteID}  
```
<span data-ttu-id="13986-143">В этом примере CSV-файл выглядит примерно так:</span><span class="sxs-lookup"><span data-stu-id="13986-143">In this example, the CSV file looks something like this:</span></span>
```
Identity, Mask, SiteID 
172.11.12.0, 24, Redmond 
172.11.13.0, 24, Chicago 
172.11.14.0, 25, Vancouver 
172.11.15.0, 28, Paris
```
## <a name="define-external-subnets"></a><span data-ttu-id="13986-144">Определение внешних подсетей</span><span class="sxs-lookup"><span data-stu-id="13986-144">Define external subnets</span></span>
<span data-ttu-id="13986-145">С помощью командлета [New-кстенанттрустедипаддресс](https://docs.microsoft.com/powershell/module/skype/new-cstenanttrustedipaddress?view=skype-ps) можно определять внешние подсети и назначать их клиентам.</span><span class="sxs-lookup"><span data-stu-id="13986-145">Use the [New-CsTenantTrustedIPAddress](https://docs.microsoft.com/powershell/module/skype/new-cstenanttrustedipaddress?view=skype-ps) cmdlet to define external subnets and assign them to the tenant.</span></span> <span data-ttu-id="13986-146">Вы можете определить неограниченное количество подсетей для клиента.</span><span class="sxs-lookup"><span data-stu-id="13986-146">You can define an unlimited number of subnets for a tenant.</span></span> 
```
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description> 
```
<span data-ttu-id="13986-147">Например:</span><span class="sxs-lookup"><span data-stu-id="13986-147">For example:</span></span>
```
New-CsTenantTrustedIPAddress -IPAddress 198.51.100.0 -MaskBits 30 -Description "Contoso address"  
```

## <a name="next-steps"></a><span data-ttu-id="13986-148">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="13986-148">Next steps</span></span>
<span data-ttu-id="13986-149">Перейдите к разделу [Включение маршрутизации на основе местоположения для прямой маршрутизации](location-based-routing-enable.md).</span><span class="sxs-lookup"><span data-stu-id="13986-149">Go to [Enable Location-Based Routing for Direct Routing](location-based-routing-enable.md).</span></span>

### <a name="related-topics"></a><span data-ttu-id="13986-150">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="13986-150">Related topics</span></span>
- [<span data-ttu-id="13986-151">Планирование маршрутизации на основе расположения для прямой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="13986-151">Plan Location-Based Routing for Direct Routing</span></span>](location-based-routing-plan.md)
- [<span data-ttu-id="13986-152">Терминология маршрутизации на основе расположения</span><span class="sxs-lookup"><span data-stu-id="13986-152">Location-Based Routing terminology</span></span>](location-based-routing-terminology.md)
