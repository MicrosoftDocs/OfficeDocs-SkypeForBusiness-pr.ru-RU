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
ms.openlocfilehash: 60af1c90cd1dbd7855da7686950ffd135d1da5dc
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30876770"
---
# <a name="configure-network-settings-for-location-based-routing"></a><span data-ttu-id="f8314-103">Настройка параметров сети для маршрутизации на основе расположения</span><span class="sxs-lookup"><span data-stu-id="f8314-103">Configure network settings for Location-Based Routing</span></span>

> [!INCLUDE [Preview customer token](includes/preview-feature.md)] 

<span data-ttu-id="f8314-104">Если вы еще не сделано, чтение, чтобы просмотреть другие действия по [Plan Location-Based маршрутизации для непосредственного](location-based-routing-plan.md) необходимо выполнить перед настройкой параметров сети для маршрутизации на основе местоположения.</span><span class="sxs-lookup"><span data-stu-id="f8314-104">If you haven't already done so, read [Plan Location-Based Routing for Direct Routing](location-based-routing-plan.md) to review other steps you'll need to take before you configure network settings for Location-Based Routing.</span></span>

<span data-ttu-id="f8314-105">В этой статье описывается настройка параметров сети для маршрутизации на основе местоположения.</span><span class="sxs-lookup"><span data-stu-id="f8314-105">This article describes how to configure network settings for Location-Based Routing.</span></span> <span data-ttu-id="f8314-106">После развертывания прямой маршрутизации телефонной системы в вашей организации, следующие действия, чтобы создать и настроить областей сети, сетевых сайтов и подсетей.</span><span class="sxs-lookup"><span data-stu-id="f8314-106">After you deploy Phone System Direct Routing in your organization, the next steps are to create and set up network regions, network sites, and network subnets.</span></span> <span data-ttu-id="f8314-107">Чтобы выполнить действия, описанные в этой статье, вам потребуются некоторые навыки работы с помощью командлетов PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f8314-107">To complete the steps in this article, you'll need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="f8314-108">Для получения дополнительных сведений см [Команды PowerShell](teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="f8314-108">To learn more, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

## <a name="define-network-regions"></a><span data-ttu-id="f8314-109">Определение областей сети</span><span class="sxs-lookup"><span data-stu-id="f8314-109">Define network regions</span></span>
 <span data-ttu-id="f8314-110">Область сети соединения различные части сети через несколько географических областей.</span><span class="sxs-lookup"><span data-stu-id="f8314-110">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="f8314-111">Командлет [New-CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsTenantNetworkRegion?view=skype-ps) используется для определения области сети.</span><span class="sxs-lookup"><span data-stu-id="f8314-111">Use the [New-CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsTenantNetworkRegion?view=skype-ps) cmdlet to define network regions.</span></span> <span data-ttu-id="f8314-112">Обратите внимание, что параметр RegionID логическое имя, который представляет географический регион и имеет не зависимости или ограничения и CentralSite &lt;веб-сайтов идентификатор&gt; это необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="f8314-112">Note that the RegionID parameter is a logical name that represents the geography of the region and has no dependencies or restrictions and the CentralSite &lt;site ID&gt; parameter is optional.</span></span> 

```
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

<span data-ttu-id="f8314-113">В этом примере мы Создание области сети с именем Индия.</span><span class="sxs-lookup"><span data-stu-id="f8314-113">In this example, we create a network region named India.</span></span> 
```
New-CsTenantNetworkRegion -NetworkRegionID "India"  
```

## <a name="define-network-sites"></a><span data-ttu-id="f8314-114">Определение сетевых узлов</span><span class="sxs-lookup"><span data-stu-id="f8314-114">Define network sites</span></span>

<span data-ttu-id="f8314-115">Используйте командлет [New-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksite?view=skype-ps) определение сетевых узлов.</span><span class="sxs-lookup"><span data-stu-id="f8314-115">Use the [New-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksite?view=skype-ps) cmdlet to define network sites.</span></span> 

```
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```
<span data-ttu-id="f8314-116">В этом примере мы создадим два новых сетевых узлов, Delhi и Hyderabad в области Индия.</span><span class="sxs-lookup"><span data-stu-id="f8314-116">In this example, we create two new network sites, Delhi and Hyderabad, in the India region.</span></span> 
```
New-CsTenantNetworkSite -NetworkSiteID "Delhi" -NetworkRegionID "India" 
New-CsTenantNetworkSite -NetworkSiteID "Hyderabad" -NetworkRegionID "India" 
```
<span data-ttu-id="f8314-117">В следующей таблице показаны сетевых узлов, определенных в этом примере.</span><span class="sxs-lookup"><span data-stu-id="f8314-117">The following table shows the network sites defined in this example.</span></span> 

||<span data-ttu-id="f8314-118">Узел 1</span><span class="sxs-lookup"><span data-stu-id="f8314-118">Site 1</span></span> |<span data-ttu-id="f8314-119">Узел 2</span><span class="sxs-lookup"><span data-stu-id="f8314-119">Site 2</span></span> |
|---------|---------|---------|
|<span data-ttu-id="f8314-120">Идентификатор сайта</span><span class="sxs-lookup"><span data-stu-id="f8314-120">Site ID</span></span>    |    <span data-ttu-id="f8314-121">Узел 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="f8314-121">Site 1 (Delhi)</span></span>     |  <span data-ttu-id="f8314-122">Узел 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="f8314-122">Site 2 (Hyderabad)</span></span>       |
|<span data-ttu-id="f8314-123">КОД региона</span><span class="sxs-lookup"><span data-stu-id="f8314-123">Region ID</span></span>  |     <span data-ttu-id="f8314-124">Область 1 (Индия)</span><span class="sxs-lookup"><span data-stu-id="f8314-124">Region 1 (India)</span></span>    |   <span data-ttu-id="f8314-125">Область 1 (Индия)</span><span class="sxs-lookup"><span data-stu-id="f8314-125">Region 1 (India)</span></span>      |

## <a name="define-network-subnets"></a><span data-ttu-id="f8314-126">Определение подсетей</span><span class="sxs-lookup"><span data-stu-id="f8314-126">Define network subnets</span></span>

<span data-ttu-id="f8314-127">Командлет [New-CsTenantNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksubnet?view=skype-ps) для определения подсетей и связывать их с сетевыми узлами.</span><span class="sxs-lookup"><span data-stu-id="f8314-127">Use the [New-CsTenantNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksubnet?view=skype-ps) cmdlet to define network subnets and associate them to network sites.</span></span> <span data-ttu-id="f8314-128">Каждый внутренней подсети может быть связано только с одного сайта.</span><span class="sxs-lookup"><span data-stu-id="f8314-128">Each internal subnet can only be associated with one site.</span></span> 
```
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID> 
```
<span data-ttu-id="f8314-129">В этом примере мы создадим связь между подсетью 192.168.0.0 и сетевым узлом Delhi и подсети 192.168.1.0 и Hyderabad сетевого узла.</span><span class="sxs-lookup"><span data-stu-id="f8314-129">In this example, we create an association between subnet 192.168.0.0 and the Delhi network site and between subnet 192.168.1.0 and the Hyderabad network site.</span></span>
```
New-CsTenantNetworkSubnet -SubnetID "192.168.0.0" -MaskBits "24" -NetworkSiteID "Delhi" 
New-CsTenantNetworkSubnet -SubnetID "192.168.1.0" -MaskBits "24" -NetworkSiteID "Hyderabad" 
```
<span data-ttu-id="f8314-130">В следующей таблице показаны подсетей, определенных в этом примере.</span><span class="sxs-lookup"><span data-stu-id="f8314-130">The following table shows the subnets defined in this example.</span></span> 

||<span data-ttu-id="f8314-131">Узел 1</span><span class="sxs-lookup"><span data-stu-id="f8314-131">Site 1</span></span> |<span data-ttu-id="f8314-132">Узел 2</span><span class="sxs-lookup"><span data-stu-id="f8314-132">Site 2</span></span> |
|---------|---------|---------|
|<span data-ttu-id="f8314-133">Идентификатор подсети</span><span class="sxs-lookup"><span data-stu-id="f8314-133">Subnet ID</span></span>   |    <span data-ttu-id="f8314-134">192.168.0.0</span><span class="sxs-lookup"><span data-stu-id="f8314-134">192.168.0.0</span></span>     |  <span data-ttu-id="f8314-135">192.168.1.0</span><span class="sxs-lookup"><span data-stu-id="f8314-135">192.168.1.0</span></span>     |
|<span data-ttu-id="f8314-136">Маска</span><span class="sxs-lookup"><span data-stu-id="f8314-136">Mask</span></span>  |     <span data-ttu-id="f8314-137">24</span><span class="sxs-lookup"><span data-stu-id="f8314-137">24</span></span>    |   <span data-ttu-id="f8314-138">24</span><span class="sxs-lookup"><span data-stu-id="f8314-138">24</span></span>      |
|<span data-ttu-id="f8314-139">Идентификатор сайта</span><span class="sxs-lookup"><span data-stu-id="f8314-139">Site ID</span></span>  | <span data-ttu-id="f8314-140">Сайт (Delhi)</span><span class="sxs-lookup"><span data-stu-id="f8314-140">Site (Delhi)</span></span> | <span data-ttu-id="f8314-141">Узел 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="f8314-141">Site 2 (Hyderabad)</span></span> |

<span data-ttu-id="f8314-142">Для нескольких подсетей можно импортировать в CSV-файл, используя следующий сценарий.</span><span class="sxs-lookup"><span data-stu-id="f8314-142">For multiple subnets, you can import a CSV file by using a script such as the following.</span></span>
```
Import-CSV C:\subnet.csv | foreach {New-CsTenantNetworkSubnet –SubnetID $_.SubnetID-MaskBits $_.Mask -NetworkSiteID $_.SiteID}  
```
<span data-ttu-id="f8314-143">В этом примере CSV-файл выглядит примерно следующим образом:</span><span class="sxs-lookup"><span data-stu-id="f8314-143">In this example, the CSV file looks something like this:</span></span>
```
Identity, Mask, SiteID 
172.11.12.0, 24, Redmond 
172.11.13.0, 24, Chicago 
172.11.14.0, 25, Vancouver 
172.11.15.0, 28, Paris
```
## <a name="define-external-subnets"></a><span data-ttu-id="f8314-144">Определить внешние подсети</span><span class="sxs-lookup"><span data-stu-id="f8314-144">Define external subnets</span></span>
<span data-ttu-id="f8314-145">Командлет [New-CsTenantTrustedIPAddress](https://docs.microsoft.com/powershell/module/skype/new-cstenanttrustedipaddress?view=skype-ps) для определения внешние подсети и назначить их к клиенту.</span><span class="sxs-lookup"><span data-stu-id="f8314-145">Use the [New-CsTenantTrustedIPAddress](https://docs.microsoft.com/powershell/module/skype/new-cstenanttrustedipaddress?view=skype-ps) cmdlet to define external subnets and assign them to the tenant.</span></span> <span data-ttu-id="f8314-146">Можно определить неограниченное число подсети для клиента.</span><span class="sxs-lookup"><span data-stu-id="f8314-146">You can define an unlimited number of subnets for a tenant.</span></span> 
```
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description> 
```
<span data-ttu-id="f8314-147">Например:</span><span class="sxs-lookup"><span data-stu-id="f8314-147">For example:</span></span>
```
New-CsTenantTrustedIPAddress -IPAddress 167.220.2.206 -MaskBits 30 -Description "Contoso address"  
```

## <a name="next-steps"></a><span data-ttu-id="f8314-148">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="f8314-148">Next steps</span></span>
<span data-ttu-id="f8314-149">Перейдите на [Включение зависимостью от расположения маршрутизации для непосредственного](location-based-routing-enable.md).</span><span class="sxs-lookup"><span data-stu-id="f8314-149">Go to [Enable Location-Based Routing for Direct Routing](location-based-routing-enable.md).</span></span>

### <a name="related-topics"></a><span data-ttu-id="f8314-150">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="f8314-150">Related topics</span></span>
- [<span data-ttu-id="f8314-151">Планирование маршрутизации на основе расположения для прямой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="f8314-151">Plan Location-Based Routing for Direct Routing</span></span>](location-based-routing-plan.md)
- [<span data-ttu-id="f8314-152">Терминология маршрутизации на основе расположения</span><span class="sxs-lookup"><span data-stu-id="f8314-152">Location-Based Routing terminology</span></span>](location-based-routing-terminology.md)
