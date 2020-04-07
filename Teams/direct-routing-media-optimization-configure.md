---
title: Оптимизация локальных файлов прямой маршрутизации
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 04/07/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: filippse
search.appverid: MET150
f1.keywords:
- NOCSH
description: Настройка оптимизации локальных файлов мультимедиа для прямой маршрутизации
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3097f97a856dc4e947281847c65669c23c73a408
ms.sourcegitcommit: 25e70de7c943e22fe6ac6e8d6b4353ca68f81f83
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/06/2020
ms.locfileid: "43158105"
---
# <a name="configure-local-media-optimization-for-direct-routing"></a><span data-ttu-id="5f20a-103">Настройка оптимизации локальных файлов мультимедиа для прямой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="5f20a-103">Configure Local Media Optimization for Direct Routing</span></span>

<span data-ttu-id="5f20a-104">Настройка оптимизации локальных файлов мультимедиа основывается на параметрах сети, которые являются общими для других функций голосовой связи в облаке, таких как маршрутизация на основе местоположения и динамический вызов экстренной помощи.</span><span class="sxs-lookup"><span data-stu-id="5f20a-104">Configuration for Local Media Optimization is based on network settings that are common to other cloud voice features, such as Location-Based Routing and dynamic emergency calling.</span></span> <span data-ttu-id="5f20a-105">Чтобы узнать больше о регионах сети, сетевых сайтах, подсетях сети и о доверенных IP-адресах, просмотрите [Параметры сети для функций голосовой связи в облаке](cloud-voice-network-settings.md).</span><span class="sxs-lookup"><span data-stu-id="5f20a-105">To learn more about network regions, network sites, network subnets, and trusted IP addresses, see [Network settings for cloud voice features](cloud-voice-network-settings.md).</span></span>

<span data-ttu-id="5f20a-106">Перед настройкой оптимизации локального мультимедиа ознакомьтесь со сведениями [об оптимизации локальных файлов для прямой маршрутизации](direct-routing-media-optimization.md).</span><span class="sxs-lookup"><span data-stu-id="5f20a-106">Before you configure Local Media Optimization, see [Local media Optimization for Direct Routing](direct-routing-media-optimization.md).</span></span>  

<span data-ttu-id="5f20a-107">Для настройки оптимизации локального мультимедиа необходимо выполнить указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="5f20a-107">To configure Local Media Optimization, the following steps are required.</span></span> <span data-ttu-id="5f20a-108">Вы можете использовать центр администрирования Teams или PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5f20a-108">You can use the Teams Admin Center or PowerShell.</span></span> <span data-ttu-id="5f20a-109">Подробности можно найти в разделе [Управление топологией сети](manage-your-network-topology.md).</span><span class="sxs-lookup"><span data-stu-id="5f20a-109">For details, see [Manage your network topology](manage-your-network-topology.md).</span></span>

1. <span data-ttu-id="5f20a-110">Настройте пользователя и сайты SBC (как описано в этой статье).</span><span class="sxs-lookup"><span data-stu-id="5f20a-110">Configure the user and the SBC sites (as described in this article).</span></span>
2. <span data-ttu-id="5f20a-111">Настройте локальную SBCs для оптимизации локальных файлов (в соответствии со спецификацией поставщика SBC).</span><span class="sxs-lookup"><span data-stu-id="5f20a-111">Configure the SBCs for Local Media Optimization (according to your SBC vendor specification).</span></span>

<span data-ttu-id="5f20a-112">На приведенной ниже схеме показана настройка сети, используемая в примерах в этой статье.</span><span class="sxs-lookup"><span data-stu-id="5f20a-112">The following diagram shows the network setup used in the examples throughout this article.</span></span>

<span data-ttu-id="5f20a-113">![Пример схемы, показывающей параметры сети](media/direct-routing-media-op-9.png "Примеры настройки сети")</span><span class="sxs-lookup"><span data-stu-id="5f20a-113">![Diagram showing network setup for examples](media/direct-routing-media-op-9.png "Network setup for examples")</span></span>


## <a name="configure-the-user-and-the-sbc-sites"></a><span data-ttu-id="5f20a-114">Настройка пользователей и сайтов SBC</span><span class="sxs-lookup"><span data-stu-id="5f20a-114">Configure the user and the SBC sites</span></span>

<span data-ttu-id="5f20a-115">Чтобы настроить пользователя и сайты SBC, необходимо выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="5f20a-115">To configure the user and the SBC sites, you will need to:</span></span>

1. <span data-ttu-id="5f20a-116">[Управление внешними доверенными IP-адресами](#manage-external-trusted-ip-addresses).</span><span class="sxs-lookup"><span data-stu-id="5f20a-116">[Manage external trusted IP addresses](#manage-external-trusted-ip-addresses).</span></span>  

2. <span data-ttu-id="5f20a-117">[Определите топологию сети](#define-the-network-topology) , настроив регионы сети, сетевые сайты и сетевые подсети.</span><span class="sxs-lookup"><span data-stu-id="5f20a-117">[Define the network topology](#define-the-network-topology) by configuring the network regions, network sites, and network subnets.</span></span>

3. <span data-ttu-id="5f20a-118">[Определите топологию виртуальной сети](#define-the-virtual-network-topology) путем назначения SBC (-ов) на сайты, используя необходимые режимы и значения SBC-прокси.</span><span class="sxs-lookup"><span data-stu-id="5f20a-118">[Define the virtual network topology](#define-the-virtual-network-topology) by assigning SBC(s) to site(s) with relevant modes and proxy SBC values.</span></span>


## <a name="configure-sbcs-for-local-media-optimization-according-to-the-sbc-vendor-specification"></a><span data-ttu-id="5f20a-119">Настройка SBC (s) для оптимизации локальных файлов мультимедиа в соответствии со спецификацией поставщика SBC</span><span class="sxs-lookup"><span data-stu-id="5f20a-119">Configure SBC(s) for Local Media Optimization according to the SBC vendor specification</span></span>

<span data-ttu-id="5f20a-120">В этой статье описано, как настроить компоненты Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5f20a-120">This article describes configuration for Microsoft components.</span></span> <span data-ttu-id="5f20a-121">Информацию о настройке SBC можно найти в documenation поставщика SBC.</span><span class="sxs-lookup"><span data-stu-id="5f20a-121">For information on SBC configuration, see your SBC vendor documenation.</span></span>

<span data-ttu-id="5f20a-122">Локальная Оптимизация файлов мультимедиа поддерживается следующими разработчиками SBC:</span><span class="sxs-lookup"><span data-stu-id="5f20a-122">Local Media Optimization is supported by the following SBC vendors:</span></span>

| <span data-ttu-id="5f20a-123">Поставщик</span><span class="sxs-lookup"><span data-stu-id="5f20a-123">Vendor</span></span> | <span data-ttu-id="5f20a-124">ПРОИЗВЕД</span><span class="sxs-lookup"><span data-stu-id="5f20a-124">Product</span></span> |    <span data-ttu-id="5f20a-125">Версия программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="5f20a-125">Software version</span></span> |
|:------------|:-------|:-------| :-------|
| [<span data-ttu-id="5f20a-126">Audiocodes</span><span class="sxs-lookup"><span data-stu-id="5f20a-126">Audiocodes</span></span>](https://www.audiocodes.com/media/13253/connecting-audiocodes-sbc-to-microsoft-teams-direct-routing-enterprise-model-configuration-note.pdf) |    <span data-ttu-id="5f20a-127">Mediant 500 SBC</span><span class="sxs-lookup"><span data-stu-id="5f20a-127">Mediant 500 SBC</span></span> |   <span data-ttu-id="5f20a-128">7.20 а. 256</span><span class="sxs-lookup"><span data-stu-id="5f20a-128">7.20A.256</span></span> | 
|            |  <span data-ttu-id="5f20a-129">Mediant 800 SBC</span><span class="sxs-lookup"><span data-stu-id="5f20a-129">Mediant 800 SBC</span></span> |   <span data-ttu-id="5f20a-130">7.20 а. 256</span><span class="sxs-lookup"><span data-stu-id="5f20a-130">7.20A.256</span></span> | 
|            |  <span data-ttu-id="5f20a-131">Mediant 2600 SBC</span><span class="sxs-lookup"><span data-stu-id="5f20a-131">Mediant 2600 SBC</span></span> |  <span data-ttu-id="5f20a-132">7.20 а. 256</span><span class="sxs-lookup"><span data-stu-id="5f20a-132">7.20A.256</span></span> | 
|            |  <span data-ttu-id="5f20a-133">Mediant 4000 SBC</span><span class="sxs-lookup"><span data-stu-id="5f20a-133">Mediant 4000 SBC</span></span> |  <span data-ttu-id="5f20a-134">7.20 а. 256</span><span class="sxs-lookup"><span data-stu-id="5f20a-134">7.20A.256</span></span> | 
|            |  <span data-ttu-id="5f20a-135">Функция МЕДИАНА 1000Bого SBC</span><span class="sxs-lookup"><span data-stu-id="5f20a-135">Mediant 1000B SBC</span></span> | <span data-ttu-id="5f20a-136">7.20 а. 256</span><span class="sxs-lookup"><span data-stu-id="5f20a-136">7.20A.256</span></span> | 
|            |  <span data-ttu-id="5f20a-137">Одномедианый SBC 9000</span><span class="sxs-lookup"><span data-stu-id="5f20a-137">Mediant 9000 SBC</span></span> |  <span data-ttu-id="5f20a-138">7.20 а. 256</span><span class="sxs-lookup"><span data-stu-id="5f20a-138">7.20A.256</span></span> | 
|            |  <span data-ttu-id="5f20a-139">Односрединный виртуальный SBC</span><span class="sxs-lookup"><span data-stu-id="5f20a-139">Mediant Virtual Edition SBC</span></span> |   <span data-ttu-id="5f20a-140">7.20 а. 256</span><span class="sxs-lookup"><span data-stu-id="5f20a-140">7.20A.256</span></span> | 
|            |  <span data-ttu-id="5f20a-141">SBC по выпуску "Медиана"</span><span class="sxs-lookup"><span data-stu-id="5f20a-141">Mediant Cloud Edition SBC</span></span> | <span data-ttu-id="5f20a-142">7.20 а. 256</span><span class="sxs-lookup"><span data-stu-id="5f20a-142">7.20A.256</span></span> |
| [<span data-ttu-id="5f20a-143">Базовые компоненты SBC для ленты</span><span class="sxs-lookup"><span data-stu-id="5f20a-143">Ribbon SBC Core</span></span>](https://support.sonus.net/display/ALLDOC/SBC+8.2+-+Configure+Local+Media+Optimization)  |  <span data-ttu-id="5f20a-144">SBC 5110</span><span class="sxs-lookup"><span data-stu-id="5f20a-144">SBC 5110</span></span>         | <span data-ttu-id="5f20a-145">8,2</span><span class="sxs-lookup"><span data-stu-id="5f20a-145">8.2</span></span>  |
|            |  <span data-ttu-id="5f20a-146">SBC 5210</span><span class="sxs-lookup"><span data-stu-id="5f20a-146">SBC 5210</span></span>         | <span data-ttu-id="5f20a-147">8,2</span><span class="sxs-lookup"><span data-stu-id="5f20a-147">8.2</span></span>  |
|            |  <span data-ttu-id="5f20a-148">SBC 5400</span><span class="sxs-lookup"><span data-stu-id="5f20a-148">SBC 5400</span></span>         | <span data-ttu-id="5f20a-149">8,2</span><span class="sxs-lookup"><span data-stu-id="5f20a-149">8.2</span></span>  |
|            |  <span data-ttu-id="5f20a-150">SBC 7000</span><span class="sxs-lookup"><span data-stu-id="5f20a-150">SBC 7000</span></span>         | <span data-ttu-id="5f20a-151">8,2</span><span class="sxs-lookup"><span data-stu-id="5f20a-151">8.2</span></span>  |
|            |  <span data-ttu-id="5f20a-152">SBC SWe</span><span class="sxs-lookup"><span data-stu-id="5f20a-152">SBC SWe</span></span>          | <span data-ttu-id="5f20a-153">8,2</span><span class="sxs-lookup"><span data-stu-id="5f20a-153">8.2</span></span>  |
| [<span data-ttu-id="5f20a-154">Ребро для SBC ленты</span><span class="sxs-lookup"><span data-stu-id="5f20a-154">Ribbon SBC Edge</span></span>](https://support.sonus.net/display/UXDOC81/Microsoft+Teams+Direct+Routing+-+On+Premises+Deployment)  |  <span data-ttu-id="5f20a-155">SBC 1000</span><span class="sxs-lookup"><span data-stu-id="5f20a-155">SBC 1000</span></span>         | <span data-ttu-id="5f20a-156">8.1.1, сборка 527</span><span class="sxs-lookup"><span data-stu-id="5f20a-156">8.1.1, build 527</span></span> |
|            |  <span data-ttu-id="5f20a-157">SBC 2000</span><span class="sxs-lookup"><span data-stu-id="5f20a-157">SBC 2000</span></span>         | <span data-ttu-id="5f20a-158">8.1.1, сборка 527</span><span class="sxs-lookup"><span data-stu-id="5f20a-158">8.1.1, build 527</span></span> |
|            |  <span data-ttu-id="5f20a-159">SBC SWe Lite</span><span class="sxs-lookup"><span data-stu-id="5f20a-159">SBC SWe Lite</span></span>     | <span data-ttu-id="5f20a-160">8.1.0, сборка 222</span><span class="sxs-lookup"><span data-stu-id="5f20a-160">8.1.0, build 222</span></span> |
| [<span data-ttu-id="5f20a-161">TE-SYSTEMS</span><span class="sxs-lookup"><span data-stu-id="5f20a-161">TE-SYSTEMS</span></span>](https://www.anynode.de/local_media_optimization/) |  <span data-ttu-id="5f20a-162">anynode</span><span class="sxs-lookup"><span data-stu-id="5f20a-162">anynode</span></span>          | <span data-ttu-id="5f20a-163">4.0.1 +</span><span class="sxs-lookup"><span data-stu-id="5f20a-163">4.0.1+</span></span> |


## <a name="manage-external-trusted-ip-addresses"></a><span data-ttu-id="5f20a-164">Управление внешними надежными IP-адресами</span><span class="sxs-lookup"><span data-stu-id="5f20a-164">Manage external trusted IP addresses</span></span>

<span data-ttu-id="5f20a-165">Внешние надежные IP-адреса — это внешние IP-адреса Интернет-адресов корпоративной сети.</span><span class="sxs-lookup"><span data-stu-id="5f20a-165">External trusted IPs are the Internet external IPs of the enterprise network.</span></span> <span data-ttu-id="5f20a-166">Эти IP-адреса используются клиентами Microsoft Teams при подключении к Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5f20a-166">These IP’s are the IP addresses used by Microsoft Teams clients when they connect to Microsoft 365.</span></span> <span data-ttu-id="5f20a-167">Вам необходимо добавить эти внешние IP-адреса для каждого сайта, на котором пользователи используют локальную оптимизацию мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="5f20a-167">You need to add these external IPs for each site where you have users using Local Media Optimization.</span></span>

<span data-ttu-id="5f20a-168">Чтобы добавить общедоступные IP-адреса для каждого сайта, используйте командлет New-CsTenantTrustedIPAddress.</span><span class="sxs-lookup"><span data-stu-id="5f20a-168">To add the public IP addresses for each site, use the New-CsTenantTrustedIPAddress cmdlet.</span></span> <span data-ttu-id="5f20a-169">Вы можете определить неограниченное количество доверенных IP-адресов для клиента.</span><span class="sxs-lookup"><span data-stu-id="5f20a-169">You can define an unlimited number of trusted IP addresses for a tenant.</span></span> <span data-ttu-id="5f20a-170">Если внешние IP-адреса, обнаруженные Microsoft 365, являются адресами IPv4 и IPv6, необходимо добавить оба типа IP.</span><span class="sxs-lookup"><span data-stu-id="5f20a-170">If the external IPs seen by Microsoft 365 are both IPv4 and IPv6 addresses, you need to add both types of IP addresses.</span></span> <span data-ttu-id="5f20a-171">Для IPv4 используется маска 32.</span><span class="sxs-lookup"><span data-stu-id="5f20a-171">For IPv4, use mask 32.</span></span> <span data-ttu-id="5f20a-172">Для IPv6 используйте маску 128.</span><span class="sxs-lookup"><span data-stu-id="5f20a-172">For IPv6, use mask 128.</span></span> <span data-ttu-id="5f20a-173">Вы можете добавить как отдельные внешние IP-адреса, так и внешние IP-подсети, указав разные MaskBits в командлете.</span><span class="sxs-lookup"><span data-stu-id="5f20a-173">You can add both individual external IP addresses and external IP subnets by specifying different MaskBits on the cmdlet.</span></span>

```
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description>
```


<span data-ttu-id="5f20a-174">Пример добавления доверенных IP-адресов.</span><span class="sxs-lookup"><span data-stu-id="5f20a-174">Example of adding trusted IP addresses.</span></span>

```
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.110 -MaskBits 32 -Description "Vietnam site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.120 -MaskBits 32 -Description "Indonesia site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.130 -MaskBits 32 -Description "Singapore site trusted IP"
```


## <a name="define-the-network-topology"></a><span data-ttu-id="5f20a-175">Определение топологии сети</span><span class="sxs-lookup"><span data-stu-id="5f20a-175">Define the network topology</span></span>

<span data-ttu-id="5f20a-176">В этом разделе рассказывается, как определить регионы сети, сетевые сайты и сетевые подсети для топологии сети.</span><span class="sxs-lookup"><span data-stu-id="5f20a-176">This section describes how to define the network regions, network sites, and network subnets for your network topology.</span></span>

<span data-ttu-id="5f20a-177">Все параметры чувствительны к регистру, поэтому необходимо использовать тот же сценарий, который использовался при настройке.</span><span class="sxs-lookup"><span data-stu-id="5f20a-177">All parameters are case sensitive so you need to ensure that you use the same case that was used during setup.</span></span>  <span data-ttu-id="5f20a-178">(Например, GatewaySiteID значения "Вьетнам" и "Вьетнам" будут считаться разными сайтами.)</span><span class="sxs-lookup"><span data-stu-id="5f20a-178">(For example, GatewaySiteID values “Vietnam” and “vietnam” will be treated as different sites.)</span></span>

### <a name="define-network-regions"></a><span data-ttu-id="5f20a-179">Определение регионов сети</span><span class="sxs-lookup"><span data-stu-id="5f20a-179">Define network regions</span></span>

<span data-ttu-id="5f20a-180">Чтобы определить регионы сети, используйте командлет New-CsTenantNetworkRegion.</span><span class="sxs-lookup"><span data-stu-id="5f20a-180">To define network regions, use the New-CsTenantNetworkRegion cmdlet.</span></span> <span data-ttu-id="5f20a-181">Параметр RegionID — это логическое имя, представляющее собой географию области и не обладающее зависимостями или ограничениями.</span><span class="sxs-lookup"><span data-stu-id="5f20a-181">The RegionID parameter is a logical name that represents the geography of the region and has no dependencies or restrictions.</span></span> <span data-ttu-id="5f20a-182">Параметр CentralSite <site ID> является необязательным.</span><span class="sxs-lookup"><span data-stu-id="5f20a-182">The CentralSite <site ID> parameter is optional.</span></span>

```
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

<span data-ttu-id="5f20a-183">В следующем примере создается сетевой регион с именем APAC:</span><span class="sxs-lookup"><span data-stu-id="5f20a-183">The following example creates a network region named APAC:</span></span>

```
New-CsTenantNetworkRegion -NetworkRegionID "APAC"  
```

###  <a name="define-network-sites"></a><span data-ttu-id="5f20a-184">Определение сетевых сайтов</span><span class="sxs-lookup"><span data-stu-id="5f20a-184">Define network sites</span></span>

<span data-ttu-id="5f20a-185">Для определения сетевых сайтов используйте командлет New-CsTenantNetworkSite.</span><span class="sxs-lookup"><span data-stu-id="5f20a-185">To define network sites, use the New-CsTenantNetworkSite cmdlet.</span></span> <span data-ttu-id="5f20a-186">Каждый сетевой сайт должен быть связан с сетевым регионом.</span><span class="sxs-lookup"><span data-stu-id="5f20a-186">Each network site must be associated with a network region.</span></span>

```
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```

<span data-ttu-id="5f20a-187">В следующем примере показано создание трех новых сайтов сети, Вьетнам, Индонезия и Сингапур в регионе APAC:</span><span class="sxs-lookup"><span data-stu-id="5f20a-187">The following example creates three new network sites, Vietnam, Indonesia, and Singapore in the APAC region:</span></span>

```
New-CsTenantNetworkSite -NetworkSiteID "Vietnam" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Indonesia" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Singapore" -NetworkRegionID "APAC"
```

### <a name="define-network-subnets"></a><span data-ttu-id="5f20a-188">Определение подсетей сети</span><span class="sxs-lookup"><span data-stu-id="5f20a-188">Define network subnets</span></span>

<span data-ttu-id="5f20a-189">Чтобы определить сетевые подсети и связать их с сетевыми сайтами, используйте командлет New-CsTenantNetworkSubnet.</span><span class="sxs-lookup"><span data-stu-id="5f20a-189">To define network subnets and associate them to network sites, use the New-CsTenantNetworkSubnet cmdlet.</span></span> <span data-ttu-id="5f20a-190">Каждая сетевая подсеть может быть связана только с одним сайтом.</span><span class="sxs-lookup"><span data-stu-id="5f20a-190">Each network subnet can only be associated with one site.</span></span> 

```
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>
```

<span data-ttu-id="5f20a-191">В приведенном ниже примере определяются три подсети, которые связываются с тремя сетевыми сайтами: Вьетнам, Индонезия и Сингапур.</span><span class="sxs-lookup"><span data-stu-id="5f20a-191">The following example defines three network subnets and associates them with the three network sites:  Vietnam, Indonesia, and Singapore:</span></span>

```
New-CsTenantNetworkSubnet -SubnetID 192.168.1.0 -MaskBits 24 -NetworkSiteID “Vietnam”
New-CsTenantNetworkSubnet -SubnetID 192.168.2.0 -MaskBits 24 -NetworkSiteID “Indonesia”
New-CsTenantNetworkSubnet -SubnetID 192.168.3.0 -MaskBits 24 -NetworkSiteID “Singapore”
```

## <a name="define-the-virtual-network-topology"></a><span data-ttu-id="5f20a-192">Определение топологии виртуальной сети</span><span class="sxs-lookup"><span data-stu-id="5f20a-192">Define the virtual network topology</span></span> 

<span data-ttu-id="5f20a-193">Сначала администратор клиента создает новую конфигурацию SBC для каждого связанного SBC с помощью командлета New-CsOnlinePSTNGateway.</span><span class="sxs-lookup"><span data-stu-id="5f20a-193">First, the tenant administrator creates a new SBC configuration for each relevant SBC by using the New-CsOnlinePSTNGateway cmdlet.</span></span>
<span data-ttu-id="5f20a-194">Администратор клиента определяет топологию виртуальной сети, указав сетевые сайты для объектов шлюза PSTN с помощью командлета Set-CsOnlinePSTNGateway:</span><span class="sxs-lookup"><span data-stu-id="5f20a-194">The tenant administrator defines the virtual network topology by specifying the network sites for the PSTN gateway objects using the Set-CsOnlinePSTNGateway cmdlet:</span></span>

```
PS C:\> Set-CsOnlinePSTNGateway -Identity <Identity> -GatewaySiteID <site ID> -MediaBypass <true/false> -BypassMode <Always/OnlyForLocalUsers> -ProxySBC  <proxy SBC FQDN or $null>
```

<span data-ttu-id="5f20a-195">Обратите внимание на следующее:</span><span class="sxs-lookup"><span data-stu-id="5f20a-195">Note the following:</span></span> 
   - <span data-ttu-id="5f20a-196">Если у клиента есть один объект SBC, параметр-ProxySBC должен быть обязательным как обязательно $null или однорангового значения SBC (то есть центрального SBC с помощью централизованной магистрали).</span><span class="sxs-lookup"><span data-stu-id="5f20a-196">If the customer has a single SBC, the -ProxySBC parameter must be either mandatory $null or SBC FQDN value (Central SBC with centralized trunks scenario).</span></span>
   - <span data-ttu-id="5f20a-197">Параметр-MediaBypass должен иметь значение $true, чтобы обеспечить поддержку локальной оптимизации мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="5f20a-197">The -MediaBypass parameter must be set to $true in order to support Local Media Optimization.</span></span>
   - <span data-ttu-id="5f20a-198">Если для SBC не задан параметр-BypassMode, заголовки X-MS не будут отправляться.</span><span class="sxs-lookup"><span data-stu-id="5f20a-198">If the SBC doesn’t have the -BypassMode parameter set, X-MS headers will not be sent.</span></span> 
   - <span data-ttu-id="5f20a-199">Все параметры чувствительны к регистру, поэтому необходимо использовать тот же вариант, который использовался при настройке.</span><span class="sxs-lookup"><span data-stu-id="5f20a-199">All parameters are case sensitive so you need to ensure that you use the same case that was used used during setup.</span></span>  <span data-ttu-id="5f20a-200">(Например, GatewaySiteID значения "Вьетнам" и "Вьетнам" будут считаться разными сайтами.)</span><span class="sxs-lookup"><span data-stu-id="5f20a-200">(For example, GatewaySiteID values “Vietnam” and “vietnam” will be treated as different sites.)</span></span>

<span data-ttu-id="5f20a-201">В следующем примере добавляется три SBCs к сетевым сайтам Вьетнам, Индонезия и Сингапур в APAC области с режимом "всегда обходиться".</span><span class="sxs-lookup"><span data-stu-id="5f20a-201">The following example adds three SBCs to the network sites Vietnam, Indonesia, and Singapore in the APAC region with mode Always bypass:</span></span>

```
Set-CSOnlinePSTNGateway -Identity “proxysbc.contoso.com” -GatewaySiteID “Singapore” -MediaBypass $true -BypassMode “Always” -ProxySBC $null

Set-CSOnlinePSTNGateway -Identity “VNsbc.contoso.com” -GatewaySiteID “Vietnam” -MediaBypass $true -BypassMode “Always” -ProxySBC “proxysbc.contoso.com”

Set-CSOnlinePSTNGateway -Identity “IDsbc.contoso.com” -GatewaySiteID “Indonesia” -MediaBypass $true -BypassMode “Always” -ProxySBC “proxysbc.contoso.com”
```

<span data-ttu-id="5f20a-202">Примечание. для обеспечения бесперебойной работы при одновременной настройке локальной оптимизации и маршрутизации на основе местоположения (LBR) для LBR необходимо включить более подпадающую одноранговую SBCs, задав для параметра GatewaySiteLbrEnabled значение $true для каждого из этих одноименнох SBC-файлов.</span><span class="sxs-lookup"><span data-stu-id="5f20a-202">Note: To ensure uninterrupted operations when Local Media Optimization and Location-Based Routing (LBR) are configured at the same time, downstream SBCs must be enabled for LBR by setting the GatewaySiteLbrEnabled parameter to $true for each downstream SBC.</span></span> <span data-ttu-id="5f20a-203">(Этот параметр не является обязательным для прокси-сервера SBC).</span><span class="sxs-lookup"><span data-stu-id="5f20a-203">(This setting is not mandatory for the proxy SBC.)</span></span>

<span data-ttu-id="5f20a-204">В соответствии с приведенными выше сведениями прямая маршрутизация включает три собственных заголовка SIP для приглашений на SIP и повторений, как показано в приведенной ниже таблице.</span><span class="sxs-lookup"><span data-stu-id="5f20a-204">Based on the information above, Direct Routing will include three proprietary SIP Headers to SIP Invites and Re-invites as shown  in the following table.</span></span>

<span data-ttu-id="5f20a-205">Заголовки X-MS, введенные в прямом маршруте на приглашениях и повторных приглашениях, если определен BypassMode:</span><span class="sxs-lookup"><span data-stu-id="5f20a-205">X-MS Headers introduced in Direct Routing on Invites and Re-Invites if BypassMode is defined:</span></span>

| <span data-ttu-id="5f20a-206">Имя заголовка</span><span class="sxs-lookup"><span data-stu-id="5f20a-206">Header name</span></span> | <span data-ttu-id="5f20a-207">Данные</span><span class="sxs-lookup"><span data-stu-id="5f20a-207">Values</span></span> | <span data-ttu-id="5f20a-208">Комментарии</span><span class="sxs-lookup"><span data-stu-id="5f20a-208">Comments</span></span> | 
|:------------|:-------|:-------|
| <span data-ttu-id="5f20a-209">X-MS-UserLocation</span><span class="sxs-lookup"><span data-stu-id="5f20a-209">X-MS-UserLocation</span></span> | <span data-ttu-id="5f20a-210">внутренние и внешние</span><span class="sxs-lookup"><span data-stu-id="5f20a-210">internal/external</span></span> | <span data-ttu-id="5f20a-211">Указывает, является ли пользователь внутренним или внешним</span><span class="sxs-lookup"><span data-stu-id="5f20a-211">Indicates if user is internal or external</span></span> |
| <span data-ttu-id="5f20a-212">Запрос-URI INVITE SIP: + 84439263000@VNsbc.contoso.com SIP/2,0</span><span class="sxs-lookup"><span data-stu-id="5f20a-212">Request-URI   INVITE sip: +84439263000@VNsbc.contoso.com SIP /2.0</span></span> | <span data-ttu-id="5f20a-213">ПОЛНОЕ ДОМЕННОЕ ИМЯ SBC</span><span class="sxs-lookup"><span data-stu-id="5f20a-213">SBC FQDN</span></span> | <span data-ttu-id="5f20a-214">Полное доменное имя, которое предназначено для вызова, даже если SBC не подключен напрямую к прямой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="5f20a-214">The FQDN which is targeted for the call even if the SBC is not directly connected to Direct Routing</span></span> |
| <span data-ttu-id="5f20a-215">X-MS-MediaPath</span><span class="sxs-lookup"><span data-stu-id="5f20a-215">X-MS-MediaPath</span></span> | <span data-ttu-id="5f20a-216">Пример: proxysbc.contoso.com, VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5f20a-216">Example: proxysbc.contoso.com, VNsbc.contoso.com</span></span> | <span data-ttu-id="5f20a-217">Порядковый номер SBCs, который должен использоваться для пути к носителю между пользователем и объектом SBC.</span><span class="sxs-lookup"><span data-stu-id="5f20a-217">Order of SBCs that should be used for Media path between the user and target SBC.</span></span> <span data-ttu-id="5f20a-218">Конечный SBC всегда в последнюю очередь</span><span class="sxs-lookup"><span data-stu-id="5f20a-218">The final SBC is always last</span></span> |
| <span data-ttu-id="5f20a-219">X-MS-UserSite</span><span class="sxs-lookup"><span data-stu-id="5f20a-219">X-MS-UserSite</span></span> | <span data-ttu-id="5f20a-220">usersiteID</span><span class="sxs-lookup"><span data-stu-id="5f20a-220">usersiteID</span></span> | <span data-ttu-id="5f20a-221">Строка, определенная администратором клиента</span><span class="sxs-lookup"><span data-stu-id="5f20a-221">String defined by tenant administrator</span></span> |

## <a name="call-flows"></a><span data-ttu-id="5f20a-222">Потоки звонков</span><span class="sxs-lookup"><span data-stu-id="5f20a-222">Call flows</span></span> 

<span data-ttu-id="5f20a-223">Ниже показаны потоки звонков для двух режимов:</span><span class="sxs-lookup"><span data-stu-id="5f20a-223">The following shows call flows for two modes:</span></span>

- [<span data-ttu-id="5f20a-224">Всегда обходить</span><span class="sxs-lookup"><span data-stu-id="5f20a-224">Always Bypass</span></span>](#always-bypass-mode)
- [<span data-ttu-id="5f20a-225">Только для локальных пользователей</span><span class="sxs-lookup"><span data-stu-id="5f20a-225">Only for local users</span></span>](#only-for-local-users-mode)

### <a name="always-bypass-mode"></a><span data-ttu-id="5f20a-226">Режим "всегда пропускать"</span><span class="sxs-lookup"><span data-stu-id="5f20a-226">Always Bypass mode</span></span>

<span data-ttu-id="5f20a-227">Режим "всегда пропускать" — это самый простой параметр для настройки.</span><span class="sxs-lookup"><span data-stu-id="5f20a-227">Always Bypass mode is the simplest option to configure.</span></span> <span data-ttu-id="5f20a-228">Администратор клиента может настроить один сайт для всех пользователей и SBCs, если все SBCs достижимы с любого сайта.</span><span class="sxs-lookup"><span data-stu-id="5f20a-228">The tenant administrator can configure a single site for all users and SBCs if all SBCs are reachable from any site.</span></span>

<span data-ttu-id="5f20a-229">В примерах показан режим "всегда обойти" для следующих сценариев:</span><span class="sxs-lookup"><span data-stu-id="5f20a-229">The examples show Always bypass mode for the following scenarios:</span></span>

- [<span data-ttu-id="5f20a-230">Исходящие звонки и пользователь находятся в той же папке, что и SBC</span><span class="sxs-lookup"><span data-stu-id="5f20a-230">Outbound calls and the user is in the same location as the SBC</span></span>](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [<span data-ttu-id="5f20a-231">Входящие звонки и пользователь находятся в той же папке, что и SBC</span><span class="sxs-lookup"><span data-stu-id="5f20a-231">Inbound calls and the user is in the same location as the SBC</span></span>](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [<span data-ttu-id="5f20a-232">Исходящие звонки и внешние пользователи</span><span class="sxs-lookup"><span data-stu-id="5f20a-232">Outbound calls and the user is external</span></span>](#outbound-calls-and-the-user-is-external-with-always-bypass)
- [<span data-ttu-id="5f20a-233">Входящие звонки и внешние пользователи</span><span class="sxs-lookup"><span data-stu-id="5f20a-233">Inbound calls and the user is external</span></span>](#inbound-calls-and-the-user-is-external-with-always-bypass)

<span data-ttu-id="5f20a-234">В приведенной ниже таблице указаны полные доменные имена и IP-адреса, используемые в примерах.</span><span class="sxs-lookup"><span data-stu-id="5f20a-234">The following table shows the FQDN and IP addresses used in the examples:</span></span>

| <span data-ttu-id="5f20a-235">Полное доменное имя</span><span class="sxs-lookup"><span data-stu-id="5f20a-235">FQDN</span></span> | <span data-ttu-id="5f20a-236">Внешний IP-адрес для SBC</span><span class="sxs-lookup"><span data-stu-id="5f20a-236">SBC external IP address</span></span> | <span data-ttu-id="5f20a-237">Внутренний IP-адрес SBC</span><span class="sxs-lookup"><span data-stu-id="5f20a-237">SBC internal IP Address</span></span> | <span data-ttu-id="5f20a-238">Внутренняя подсеть</span><span class="sxs-lookup"><span data-stu-id="5f20a-238">Internal subnet</span></span> | <span data-ttu-id="5f20a-239">Местоположение</span><span class="sxs-lookup"><span data-stu-id="5f20a-239">Location</span></span> | <span data-ttu-id="5f20a-240">Внешний NAT (доверенный IP-адрес)</span><span class="sxs-lookup"><span data-stu-id="5f20a-240">External NAT (Trusted IP)</span></span> |
|:------------|:-------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="5f20a-241">VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5f20a-241">VNsbc.contoso.com</span></span> | <span data-ttu-id="5f20a-242">Нет</span><span class="sxs-lookup"><span data-stu-id="5f20a-242">None</span></span> | <span data-ttu-id="5f20a-243">192.168.1.5</span><span class="sxs-lookup"><span data-stu-id="5f20a-243">192.168.1.5</span></span> | <span data-ttu-id="5f20a-244">192.168.1.0/24</span><span class="sxs-lookup"><span data-stu-id="5f20a-244">192.168.1.0/24</span></span> | <span data-ttu-id="5f20a-245">Вьетнам</span><span class="sxs-lookup"><span data-stu-id="5f20a-245">Vietnam</span></span> | <span data-ttu-id="5f20a-246">172.16.240.110</span><span class="sxs-lookup"><span data-stu-id="5f20a-246">172.16.240.110</span></span> |
| <span data-ttu-id="5f20a-247">IDsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5f20a-247">IDsbc.contoso.com</span></span> | <span data-ttu-id="5f20a-248">Нет</span><span class="sxs-lookup"><span data-stu-id="5f20a-248">None</span></span> | <span data-ttu-id="5f20a-249">192.168.2.5</span><span class="sxs-lookup"><span data-stu-id="5f20a-249">192.168.2.5</span></span> | <span data-ttu-id="5f20a-250">192.168.2.0/24</span><span class="sxs-lookup"><span data-stu-id="5f20a-250">192.168.2.0/24</span></span> | <span data-ttu-id="5f20a-251">Индонезия</span><span class="sxs-lookup"><span data-stu-id="5f20a-251">Indonesia</span></span> | <span data-ttu-id="5f20a-252">172.16.240.120</span><span class="sxs-lookup"><span data-stu-id="5f20a-252">172.16.240.120</span></span> |
| <span data-ttu-id="5f20a-253">proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5f20a-253">proxysbc.contoso.com</span></span> | <span data-ttu-id="5f20a-254">172.16.240.133</span><span class="sxs-lookup"><span data-stu-id="5f20a-254">172.16.240.133</span></span> | <span data-ttu-id="5f20a-255">192.168.3.5</span><span class="sxs-lookup"><span data-stu-id="5f20a-255">192.168.3.5</span></span> | <span data-ttu-id="5f20a-256">192.168.3.0/24</span><span class="sxs-lookup"><span data-stu-id="5f20a-256">192.168.3.0/24</span></span> | <span data-ttu-id="5f20a-257">Сингапур</span><span class="sxs-lookup"><span data-stu-id="5f20a-257">Singapore</span></span> | <span data-ttu-id="5f20a-258">172.16.240.130</span><span class="sxs-lookup"><span data-stu-id="5f20a-258">172.16.240.130</span></span> |



#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a><span data-ttu-id="5f20a-259">Исходящие звонки и пользователь находятся в той же папке, что и SBC, но не всегда обходить</span><span class="sxs-lookup"><span data-stu-id="5f20a-259">Outbound calls and the user is in the same location as the SBC with Always Bypass</span></span>

| <span data-ttu-id="5f20a-260">Режиме</span><span class="sxs-lookup"><span data-stu-id="5f20a-260">Mode</span></span> |    <span data-ttu-id="5f20a-261">Пользователь</span><span class="sxs-lookup"><span data-stu-id="5f20a-261">User</span></span> |  <span data-ttu-id="5f20a-262">Местоположение</span><span class="sxs-lookup"><span data-stu-id="5f20a-262">Location</span></span> |  <span data-ttu-id="5f20a-263">Направление звонка</span><span class="sxs-lookup"><span data-stu-id="5f20a-263">Call direction</span></span> |
|:------------|:-------|:-------| :-------|
| <span data-ttu-id="5f20a-264">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="5f20a-264">AlwaysBypass</span></span> |    <span data-ttu-id="5f20a-265">Internal</span><span class="sxs-lookup"><span data-stu-id="5f20a-265">Internal</span></span> |  <span data-ttu-id="5f20a-266">Тот же сайт, что и SBC</span><span class="sxs-lookup"><span data-stu-id="5f20a-266">The same site as SBC</span></span> |  <span data-ttu-id="5f20a-267">Исходящее</span><span class="sxs-lookup"><span data-stu-id="5f20a-267">Outbound</span></span> |

<span data-ttu-id="5f20a-268">В следующей таблице приведены сведения о конфигурации и действии конечных пользователей.</span><span class="sxs-lookup"><span data-stu-id="5f20a-268">The following table shows the end user configuration and action:</span></span>

| <span data-ttu-id="5f20a-269">Физическое расположение пользователя</span><span class="sxs-lookup"><span data-stu-id="5f20a-269">User physical location</span></span>| <span data-ttu-id="5f20a-270">Пользователь выполняет или получает звонок на номер</span><span class="sxs-lookup"><span data-stu-id="5f20a-270">User makes or receives a call to/from number</span></span> | <span data-ttu-id="5f20a-271">Номер телефона пользователя</span><span class="sxs-lookup"><span data-stu-id="5f20a-271">User phone number</span></span>  | <span data-ttu-id="5f20a-272">Политика голосовой маршрутизации в сети</span><span class="sxs-lookup"><span data-stu-id="5f20a-272">Online Voice Routing Policy</span></span> | <span data-ttu-id="5f20a-273">Режим, настроенный для SBC</span><span class="sxs-lookup"><span data-stu-id="5f20a-273">Mode configured for SBC</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="5f20a-274">Вьетнам</span><span class="sxs-lookup"><span data-stu-id="5f20a-274">Vietnam</span></span> | <span data-ttu-id="5f20a-275">+ 84 4 3926 3000</span><span class="sxs-lookup"><span data-stu-id="5f20a-275">+84 4 3926 3000</span></span> | <span data-ttu-id="5f20a-276">+ 84 4 5555 5555</span><span class="sxs-lookup"><span data-stu-id="5f20a-276">+84 4 5555 5555</span></span>   | <span data-ttu-id="5f20a-277">Приоритет 1: ^\+84 (\d{9}) $-VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5f20a-277">Priority 1: ^\+84(\d{9})$ -VNsbc.contoso.com</span></span> <br> <span data-ttu-id="5f20a-278">Приоритет 2:. \*-proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5f20a-278">Priority 2: .\* - proxysbc.contoso.com</span></span>   | <span data-ttu-id="5f20a-279">VNsbc.contoso.com – всегда обходить</span><span class="sxs-lookup"><span data-stu-id="5f20a-279">VNsbc.contoso.com – Always Bypass</span></span> <br> <span data-ttu-id="5f20a-280">proxysbc.contoso.com – всегда обходить</span><span class="sxs-lookup"><span data-stu-id="5f20a-280">proxysbc.contoso.com – Always Bypass</span></span>


<span data-ttu-id="5f20a-281">На приведенной ниже схеме показана лестница SIP для исходящего звонка с режимом "всегда минуя", и пользователь в том же расположении, что и SBC.</span><span class="sxs-lookup"><span data-stu-id="5f20a-281">The following diagram shows the SIP ladder for an outbound call with Always bypass mode, and the user in the same location as the SBC.</span></span>

<span data-ttu-id="5f20a-282">![Диаграмма, показывающая исходящие вызовы](media/direct-routing-media-op-10.png "Исходящие звонки")</span><span class="sxs-lookup"><span data-stu-id="5f20a-282">![Diagram showing outbound calls](media/direct-routing-media-op-10.png "Outbound calls")</span></span>

<span data-ttu-id="5f20a-283">В таблице ниже указаны заголовки X-MS, отправленные с помощью Direct Routing.</span><span class="sxs-lookup"><span data-stu-id="5f20a-283">The following table shows the X-MS headers sent by Direct Routing:</span></span>

| <span data-ttu-id="5f20a-284">Параметр</span><span class="sxs-lookup"><span data-stu-id="5f20a-284">Parameter</span></span> | <span data-ttu-id="5f20a-285">Пояснение</span><span class="sxs-lookup"><span data-stu-id="5f20a-285">Explanation</span></span> |
|:------------|:-------|
| <span data-ttu-id="5f20a-286">Пригласить + 8443926300@VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5f20a-286">Invite +8443926300@VNsbc.contoso.com</span></span> | <span data-ttu-id="5f20a-287">Целевое имя объекта SBC, определенного в политике голосовой маршрутизации через Интернет, отправляется в URI запроса</span><span class="sxs-lookup"><span data-stu-id="5f20a-287">The target name of the SBC as defined in the Online Voice Routing Policy is sent in the Request URI</span></span> | 
| <span data-ttu-id="5f20a-288">X-MS-UserLocation: Internal</span><span class="sxs-lookup"><span data-stu-id="5f20a-288">X-MS-UserLocation: internal</span></span> | <span data-ttu-id="5f20a-289">Поле, которое указывает, что пользователь входит в корпоративную сеть</span><span class="sxs-lookup"><span data-stu-id="5f20a-289">The field indicated that user is located inside the corporate network</span></span> |
| <span data-ttu-id="5f20a-290">X-MS-MediaPath: VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5f20a-290">X-MS-MediaPath: VNsbc.contoso.com</span></span> |   <span data-ttu-id="5f20a-291">Указывает, какой SBC — клиент должен пройти по целевому объекту SBC.</span><span class="sxs-lookup"><span data-stu-id="5f20a-291">Specifies which SBC the client must traverse to the target SBC.</span></span> <span data-ttu-id="5f20a-292">В этом случае, так как мы всегда обходите, а клиент является внутренним конечным именем, которое отправляется в заголовке как единственное имя.</span><span class="sxs-lookup"><span data-stu-id="5f20a-292">In this case as we have Always Bypass, and the client is internal the target name sent as the only name in the header.</span></span> | 
|<span data-ttu-id="5f20a-293">X-MS-UserSite: Вьетнам</span><span class="sxs-lookup"><span data-stu-id="5f20a-293">X-MS-UserSite: Vietnam</span></span> |   <span data-ttu-id="5f20a-294">Поле, указываемое на сайте, на котором находится пользователь.</span><span class="sxs-lookup"><span data-stu-id="5f20a-294">The field indicated within the site the user is located.</span></span> |


#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a><span data-ttu-id="5f20a-295">Входящие звонки и пользователь находятся в той же папке, что и SBC, но не всегда пропускать</span><span class="sxs-lookup"><span data-stu-id="5f20a-295">Inbound calls and the user is in the same location as the SBC with Always Bypass</span></span>

| <span data-ttu-id="5f20a-296">Режиме</span><span class="sxs-lookup"><span data-stu-id="5f20a-296">Mode</span></span> |    <span data-ttu-id="5f20a-297">Пользователь</span><span class="sxs-lookup"><span data-stu-id="5f20a-297">User</span></span> |  <span data-ttu-id="5f20a-298">Местоположение</span><span class="sxs-lookup"><span data-stu-id="5f20a-298">Location</span></span> |  <span data-ttu-id="5f20a-299">Направление звонка</span><span class="sxs-lookup"><span data-stu-id="5f20a-299">Call direction</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="5f20a-300">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="5f20a-300">AlwaysBypass</span></span> |    <span data-ttu-id="5f20a-301">Internal</span><span class="sxs-lookup"><span data-stu-id="5f20a-301">Internal</span></span> | <span data-ttu-id="5f20a-302">Тот же сайт, что и SBC</span><span class="sxs-lookup"><span data-stu-id="5f20a-302">The same site as SBC</span></span> | <span data-ttu-id="5f20a-303">443</span><span class="sxs-lookup"><span data-stu-id="5f20a-303">Inbound</span></span> |


<span data-ttu-id="5f20a-304">Во входящем звонке расположение пользователя неизвестно, и SBC должен быть указан в том месте, где находится пользователь.</span><span class="sxs-lookup"><span data-stu-id="5f20a-304">On an inbound call, the location of the user is unknown, and the SBC must guess where the user is.</span></span> <span data-ttu-id="5f20a-305">Если предположение не подходит, потребуется повторно пригласить приглашение.</span><span class="sxs-lookup"><span data-stu-id="5f20a-305">If the guess is not correct, a re-invite will be required.</span></span> <span data-ttu-id="5f20a-306">В этом случае подразумевается, что пользователь является внутренним, мультимедиа может напрямую перетекать, и дальнейшие действия не требуются (повторно пригласить).</span><span class="sxs-lookup"><span data-stu-id="5f20a-306">This case assumes user is internal, media can flow directly, and no further actions are required (re-invite).</span></span>
<span data-ttu-id="5f20a-307">SBC, подключенный к прямой маршрутизации, выводит на экран исходное расположение SBC, предоставляя поля "запись" и "контакт".</span><span class="sxs-lookup"><span data-stu-id="5f20a-307">The SBC connected to the Direct Routing service reports the originating SBC location by providing Record-Route and Contact fields.</span></span> <span data-ttu-id="5f20a-308">На основе этих полей путь к носителю рассчитывается посредством прямой маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="5f20a-308">Based on these fields, the media path is calculated by Direct Routing.</span></span>

<span data-ttu-id="5f20a-309">Примечание. Учитывая, что пользователь может иметь несколько конечных точек, поддержка 183 невозможна.</span><span class="sxs-lookup"><span data-stu-id="5f20a-309">Note: Given that a user can have multiple endpoints, support of 183 is not possible.</span></span> <span data-ttu-id="5f20a-310">В этом случае прямая маршрутизация всегда будет использовать 180 звонков.</span><span class="sxs-lookup"><span data-stu-id="5f20a-310">The Direct Routing will always use 180 Ringing in this case.</span></span> 

<span data-ttu-id="5f20a-311">На приведенной ниже схеме показана лестница SIP для входящего звонка в режиме AlwaysBypass, и пользователь находится в том же расположении, что и SBC.</span><span class="sxs-lookup"><span data-stu-id="5f20a-311">The following diagram shows the SIP ladder for in inbound call with AlwaysBypass mode, and the user is in the same location as the SBC.</span></span>

![Схема, на которой показана лестница SIP](media/direct-routing-media-op-11.png)


#### <a name="outbound-calls-and-the-user-is-external-with-always-bypass"></a><span data-ttu-id="5f20a-313">Исходящие звонки, а также пользователь с внешними пользователями с помощью функций "всегда минуя"</span><span class="sxs-lookup"><span data-stu-id="5f20a-313">Outbound calls and the user is external with Always Bypass</span></span>

| <span data-ttu-id="5f20a-314">Режиме</span><span class="sxs-lookup"><span data-stu-id="5f20a-314">Mode</span></span> |    <span data-ttu-id="5f20a-315">Пользователь</span><span class="sxs-lookup"><span data-stu-id="5f20a-315">User</span></span> |  <span data-ttu-id="5f20a-316">Сайт</span><span class="sxs-lookup"><span data-stu-id="5f20a-316">Site</span></span> |  <span data-ttu-id="5f20a-317">Направление звонка</span><span class="sxs-lookup"><span data-stu-id="5f20a-317">Call direction</span></span>
|:------------|:-------|:-------|:-------|
<span data-ttu-id="5f20a-318">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="5f20a-318">AlwaysBypass</span></span> |  <span data-ttu-id="5f20a-319">Внешняя</span><span class="sxs-lookup"><span data-stu-id="5f20a-319">External</span></span> |  <span data-ttu-id="5f20a-320">Н/Д</span><span class="sxs-lookup"><span data-stu-id="5f20a-320">N/A</span></span> | <span data-ttu-id="5f20a-321">Исходящее</span><span class="sxs-lookup"><span data-stu-id="5f20a-321">Outbound</span></span> |


<span data-ttu-id="5f20a-322">На приведенной ниже схеме показана лестница SIP для исходящего звонка с использованием режима AlwaysBypass, и пользователь является внешним:</span><span class="sxs-lookup"><span data-stu-id="5f20a-322">The following diagram shows the SIP ladder for an outbound call with AlwaysBypass mode, and the user is external:</span></span>

![Схема, на которой показана лестница SIP](media/direct-routing-media-op-12.png)

<span data-ttu-id="5f20a-324">В приведенной ниже таблице указаны заголовки X-MS, отправленные службой прямой маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="5f20a-324">The following table shows the X-MS headers sent by the Direct Routing service:</span></span>

| <span data-ttu-id="5f20a-325">Параметр</span><span class="sxs-lookup"><span data-stu-id="5f20a-325">Parameter</span></span> |   <span data-ttu-id="5f20a-326">Пояснение</span><span class="sxs-lookup"><span data-stu-id="5f20a-326">Explanation</span></span> |
|:------------|:-------|
|<span data-ttu-id="5f20a-327">Пригласить + 8443926300@VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5f20a-327">Invite +8443926300@VNsbc.contoso.com</span></span> | <span data-ttu-id="5f20a-328">Целевое имя объекта SBC, определенного в политике голосовой маршрутизации через Интернет, отправляется в URI запроса.</span><span class="sxs-lookup"><span data-stu-id="5f20a-328">The target name of the SBC as defined in the Online Voice Routing Policy is sent in the Request URI.</span></span>|
| <span data-ttu-id="5f20a-329">X-MS-UserLocation: External</span><span class="sxs-lookup"><span data-stu-id="5f20a-329">X-MS-UserLocation: external</span></span> | <span data-ttu-id="5f20a-330">Поле, в котором указано, что пользователь находится за пределами корпоративной сети.</span><span class="sxs-lookup"><span data-stu-id="5f20a-330">The field indicated that user is located outside the corporate network.</span></span> |
| <span data-ttu-id="5f20a-331">X-MS-MediaPath: proxysbc.contoso.com, VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5f20a-331">X-MS-MediaPath: proxysbc.contoso.com, VNsbc.contoso.com</span></span>    | <span data-ttu-id="5f20a-332">Указывает, какой SBC — клиент должен пройти по целевому объекту SBC.</span><span class="sxs-lookup"><span data-stu-id="5f20a-332">Specifies which SBC the client must traverse to the target SBC.</span></span> <span data-ttu-id="5f20a-333">В этом случае, так как мы всегда обходите, а клиент внешне.</span><span class="sxs-lookup"><span data-stu-id="5f20a-333">In this case as we have Always Bypass, and the client is external.</span></span> |

#### <a name="inbound-calls-and-the-user-is-external-with-always-bypass"></a><span data-ttu-id="5f20a-334">Входящие звонки и пользователь являются внешними по отношению к параметру "всегда минуя"</span><span class="sxs-lookup"><span data-stu-id="5f20a-334">Inbound calls and the user is external with Always Bypass</span></span>

| <span data-ttu-id="5f20a-335">Режиме</span><span class="sxs-lookup"><span data-stu-id="5f20a-335">Mode</span></span> | <span data-ttu-id="5f20a-336">Пользователь</span><span class="sxs-lookup"><span data-stu-id="5f20a-336">User</span></span> | <span data-ttu-id="5f20a-337">Сайт</span><span class="sxs-lookup"><span data-stu-id="5f20a-337">Site</span></span> |  <span data-ttu-id="5f20a-338">Направление звонка</span><span class="sxs-lookup"><span data-stu-id="5f20a-338">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
<span data-ttu-id="5f20a-339">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="5f20a-339">AlwaysBypass</span></span> |  <span data-ttu-id="5f20a-340">Внешняя</span><span class="sxs-lookup"><span data-stu-id="5f20a-340">External</span></span> |  <span data-ttu-id="5f20a-341">Н/Д</span><span class="sxs-lookup"><span data-stu-id="5f20a-341">N/A</span></span> |   <span data-ttu-id="5f20a-342">443</span><span class="sxs-lookup"><span data-stu-id="5f20a-342">Inbound</span></span> |

<span data-ttu-id="5f20a-343">Для входящего звонка SBC, подключенный к прямой маршрутизации, должен отправить повторное приглашение (по умолчанию предлагаются пользовательские кандидаты на носители), если расположение пользователя является внешним.</span><span class="sxs-lookup"><span data-stu-id="5f20a-343">For an inbound call, the SBC connected to Direct Routing needs to send a re-invite (by default, local media candidates are always offered) if the location of the user is external.</span></span>  <span data-ttu-id="5f20a-344">X-MediaPath вычисляется на основе маршрута записи и заданного пользователем SBC.</span><span class="sxs-lookup"><span data-stu-id="5f20a-344">The X-MediaPath is calculated based on Record-Route and the SBC user specified.</span></span>

<span data-ttu-id="5f20a-345">На приведенной ниже схеме показана лестница SIP для входящего звонка с использованием режима AlwaysBypass, и пользователь является внешним.</span><span class="sxs-lookup"><span data-stu-id="5f20a-345">The following diagram shows the SIP ladder for an inbound call with AlwaysBypass mode, and the user is external.</span></span>

![Схема, на которой показана лестница SIP](media/direct-routing-media-op-13.png)


### <a name="only-for-local-users-mode"></a><span data-ttu-id="5f20a-347">Только в режиме локальных пользователей</span><span class="sxs-lookup"><span data-stu-id="5f20a-347">Only for local users mode</span></span>

<span data-ttu-id="5f20a-348">Локальные мультимедийные варианты целевого SBC будут предлагаться только в том случае, если пользователь находится в том же расположении, что и SBC.</span><span class="sxs-lookup"><span data-stu-id="5f20a-348">Local media candidates of the target SBC will be offered only if a user is in the same location as the SBC.</span></span> <span data-ttu-id="5f20a-349">Во всех остальных случаях мультимедиа будет проходить через внутренний или внешний IP-адрес объекта SBC прокси.</span><span class="sxs-lookup"><span data-stu-id="5f20a-349">In all other cases, media will flow through either an internal or external IP of the proxy SBC.</span></span>

<span data-ttu-id="5f20a-350">Ниже описаны сценарии.</span><span class="sxs-lookup"><span data-stu-id="5f20a-350">The following scenarios are described:</span></span>

- [<span data-ttu-id="5f20a-351">Исходящие звонки и пользователь находятся в той же папке, что и SBC</span><span class="sxs-lookup"><span data-stu-id="5f20a-351">Outbound calls and the user is in the same location as the SBC</span></span>](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [<span data-ttu-id="5f20a-352">Входящие звонки и пользователь находятся в той же папке, что и SBC</span><span class="sxs-lookup"><span data-stu-id="5f20a-352">Inbound calls and the user is in the same location as the SBC</span></span>](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [<span data-ttu-id="5f20a-353">Пользователь не находится в том же месте, что и SBC, но входит в корпоративную сеть</span><span class="sxs-lookup"><span data-stu-id="5f20a-353">User is not at the same location as the SBC but is in the corporate network</span></span>](#user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users)
- [<span data-ttu-id="5f20a-354">Входящие звонки и пользователь являются внутренними, но не находятся в том же месте, что и SBC.</span><span class="sxs-lookup"><span data-stu-id="5f20a-354">Inbound calls and the user is internal but is not at the same location as the SBC</span></span>](#inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users)

<span data-ttu-id="5f20a-355">В приведенной ниже таблице показано, как настроить конфигурацию и действие конечного пользователя.</span><span class="sxs-lookup"><span data-stu-id="5f20a-355">The following table shows end user configuration and action:</span></span>

| <span data-ttu-id="5f20a-356">Физическое расположение пользователя</span><span class="sxs-lookup"><span data-stu-id="5f20a-356">User physical location</span></span> |  <span data-ttu-id="5f20a-357">Пользователь выполняет или получает звонок на номер</span><span class="sxs-lookup"><span data-stu-id="5f20a-357">User makes or receives a call to/from number</span></span> |  <span data-ttu-id="5f20a-358">Номер телефона пользователя</span><span class="sxs-lookup"><span data-stu-id="5f20a-358">User phone number</span></span> | <span data-ttu-id="5f20a-359">Политика голосовой маршрутизации в сети</span><span class="sxs-lookup"><span data-stu-id="5f20a-359">Online Voice Routing Policy</span></span> |   <span data-ttu-id="5f20a-360">Режим, настроенный для SBC</span><span class="sxs-lookup"><span data-stu-id="5f20a-360">Mode configured for SBC</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="5f20a-361">Вьетнам</span><span class="sxs-lookup"><span data-stu-id="5f20a-361">Vietnam</span></span> | <span data-ttu-id="5f20a-362">+ 84 4 3926 3000</span><span class="sxs-lookup"><span data-stu-id="5f20a-362">+84 4 3926  3000</span></span> |  <span data-ttu-id="5f20a-363">+ 84 4 5555 5555</span><span class="sxs-lookup"><span data-stu-id="5f20a-363">+84 4 5555 5555</span></span> | <span data-ttu-id="5f20a-364">Приоритет 1: ^\+84 (\d{9}) $-VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5f20a-364">Priority 1: ^\+84(\d{9})$ -VNsbc.contoso.com</span></span> <br> <span data-ttu-id="5f20a-365">Приоритет 2:. \*-proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5f20a-365">Priority 2: .\* - proxysbc.contoso.com</span></span> | <span data-ttu-id="5f20a-366">VNsbc.contoso.com — OnlyForLocalUsers Proxysbc.contoso.com — всегда обходить</span><span class="sxs-lookup"><span data-stu-id="5f20a-366">VNsbc.contoso.com – OnlyForLocalUsers Proxysbc.contoso.com – Always Bypass</span></span> |

#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="5f20a-367">Исходящие звонки и пользователь находятся в той же папке, что и SBC только для локальных пользователей.</span><span class="sxs-lookup"><span data-stu-id="5f20a-367">Outbound calls and the user is in the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="5f20a-368">Режиме</span><span class="sxs-lookup"><span data-stu-id="5f20a-368">Mode</span></span> | <span data-ttu-id="5f20a-369">Пользователь</span><span class="sxs-lookup"><span data-stu-id="5f20a-369">User</span></span> | <span data-ttu-id="5f20a-370">Сайт</span><span class="sxs-lookup"><span data-stu-id="5f20a-370">Site</span></span> | <span data-ttu-id="5f20a-371">Направление звонка</span><span class="sxs-lookup"><span data-stu-id="5f20a-371">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="5f20a-372">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="5f20a-372">OnlyForLocalUsers</span></span> |   <span data-ttu-id="5f20a-373">Internal</span><span class="sxs-lookup"><span data-stu-id="5f20a-373">Internal</span></span> |<span data-ttu-id="5f20a-374">То же, что и SBC</span><span class="sxs-lookup"><span data-stu-id="5f20a-374">Same as SBC</span></span>   | <span data-ttu-id="5f20a-375">Исходящее</span><span class="sxs-lookup"><span data-stu-id="5f20a-375">Outbound</span></span> |

<span data-ttu-id="5f20a-376">На приведенной ниже схеме показан исходящий вызов с использованием режима OnlyForLocalUsers, и пользователь находится в том же расположении, что и SBC.</span><span class="sxs-lookup"><span data-stu-id="5f20a-376">The following diagram shows an outbound call with OnlyForLocalUsers mode, and the user is in the same location as the SBC.</span></span> <span data-ttu-id="5f20a-377">Это тот же поток, который показан в [исходящих звонках, если пользователь находится в том же месте, что и SBC](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span><span class="sxs-lookup"><span data-stu-id="5f20a-377">This is the same flow shown in [Outbound calls when the user is in the same location as the SBC](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span></span>

![Схема, на которой показана лестница SIP](media/direct-routing-media-op-14.png)


#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="5f20a-379">Входящие звонки и пользователь находятся в той же папке, что и SBC только для локальных пользователей.</span><span class="sxs-lookup"><span data-stu-id="5f20a-379">Inbound calls and the user is in the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="5f20a-380">Режиме</span><span class="sxs-lookup"><span data-stu-id="5f20a-380">Mode</span></span> | <span data-ttu-id="5f20a-381">Пользователь</span><span class="sxs-lookup"><span data-stu-id="5f20a-381">User</span></span> | <span data-ttu-id="5f20a-382">Сайт</span><span class="sxs-lookup"><span data-stu-id="5f20a-382">Site</span></span> | <span data-ttu-id="5f20a-383">Направление звонка</span><span class="sxs-lookup"><span data-stu-id="5f20a-383">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="5f20a-384">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="5f20a-384">OnlyForLocalUsers</span></span> |   <span data-ttu-id="5f20a-385">Internal</span><span class="sxs-lookup"><span data-stu-id="5f20a-385">Internal</span></span> | <span data-ttu-id="5f20a-386">То же, что и SBC</span><span class="sxs-lookup"><span data-stu-id="5f20a-386">Same as SBC</span></span> | <span data-ttu-id="5f20a-387">443</span><span class="sxs-lookup"><span data-stu-id="5f20a-387">Inbound</span></span> |

<span data-ttu-id="5f20a-388">На приведенной ниже схеме показан входящий вызов с использованием режима OnlyForLocalUsers, и пользователь находится в том же расположении, что и SBC.</span><span class="sxs-lookup"><span data-stu-id="5f20a-388">The following diagram shows an inbound call with OnlyForLocalUsers mode, and the user is in the same location as the SBC.</span></span> <span data-ttu-id="5f20a-389">Это тот же поток, что и во [входящих звонках, когда пользователь находится в том же месте, что и SBC](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span><span class="sxs-lookup"><span data-stu-id="5f20a-389">This is the same flow as shown in [Inbound calls when the user is in the same location as the SBC](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span></span>

![Схема, на которой показана лестница SIP](media/direct-routing-media-op-15.png)


#### <a name="user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users"></a><span data-ttu-id="5f20a-391">Пользователь не находится в том же месте, что и SBC, но входит в корпоративную сеть только для локальных пользователей.</span><span class="sxs-lookup"><span data-stu-id="5f20a-391">User is not at the same location as the SBC but is in the corporate network with Only for local users</span></span>

| <span data-ttu-id="5f20a-392">Режиме</span><span class="sxs-lookup"><span data-stu-id="5f20a-392">Mode</span></span> | <span data-ttu-id="5f20a-393">Пользователь</span><span class="sxs-lookup"><span data-stu-id="5f20a-393">User</span></span> | <span data-ttu-id="5f20a-394">Сайт</span><span class="sxs-lookup"><span data-stu-id="5f20a-394">Site</span></span> |<span data-ttu-id="5f20a-395">Направление звонка</span><span class="sxs-lookup"><span data-stu-id="5f20a-395">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="5f20a-396">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="5f20a-396">OnlyForLocalUsers</span></span>  | <span data-ttu-id="5f20a-397">Internal</span><span class="sxs-lookup"><span data-stu-id="5f20a-397">Internal</span></span> |   <span data-ttu-id="5f20a-398">Отличается от SBC</span><span class="sxs-lookup"><span data-stu-id="5f20a-398">Different from SBC</span></span> | <span data-ttu-id="5f20a-399">Исходящее</span><span class="sxs-lookup"><span data-stu-id="5f20a-399">Outbound</span></span> |

<span data-ttu-id="5f20a-400">Прямая маршрутизация рассчитывает X-MediaPath в зависимости от того, где находится указанное расположение пользователя и режима, настроенных на SBC.</span><span class="sxs-lookup"><span data-stu-id="5f20a-400">Direct routing calculates X-MediaPath based on the reported location of the user and mode configured on the SBC.</span></span>


<span data-ttu-id="5f20a-401">На приведенной ниже схеме показан исходящий вызов с использованием режима OnlyForLocalUsers и внутренний пользователь, который не находится в том же месте, что и SBC.</span><span class="sxs-lookup"><span data-stu-id="5f20a-401">The following diagram shows an outbound call with OnlyForLocalUsers mode, and an internal user who is not at the same location as the SBC.</span></span>

![Схема, на которой показана лестница SIP](media/direct-routing-media-op-16.png)


#### <a name="inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="5f20a-403">Входящий звонок и пользователь является внутренним, но не в том же месте, что и SBC только для локальных пользователей.</span><span class="sxs-lookup"><span data-stu-id="5f20a-403">Inbound call and the user is internal but is not at the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="5f20a-404">Режиме</span><span class="sxs-lookup"><span data-stu-id="5f20a-404">Mode</span></span> |    <span data-ttu-id="5f20a-405">Пользователь</span><span class="sxs-lookup"><span data-stu-id="5f20a-405">User</span></span> |  <span data-ttu-id="5f20a-406">Сайт</span><span class="sxs-lookup"><span data-stu-id="5f20a-406">Site</span></span> |  <span data-ttu-id="5f20a-407">Направление звонка</span><span class="sxs-lookup"><span data-stu-id="5f20a-407">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="5f20a-408">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="5f20a-408">OnlyForLocalUsers</span></span> | <span data-ttu-id="5f20a-409">Internal</span><span class="sxs-lookup"><span data-stu-id="5f20a-409">Internal</span></span> |    <span data-ttu-id="5f20a-410">Отличается от SBC</span><span class="sxs-lookup"><span data-stu-id="5f20a-410">Different from SBC</span></span> |    <span data-ttu-id="5f20a-411">443</span><span class="sxs-lookup"><span data-stu-id="5f20a-411">Inbound</span></span> |

<span data-ttu-id="5f20a-412">На приведенной ниже схеме показан входящий вызов с использованием режима OnlyForLocalUsers и внутренний пользователь, который не находится в том же месте, что и SBC.</span><span class="sxs-lookup"><span data-stu-id="5f20a-412">The following diagram shows an inbound call with OnlyForLocalUsers mode, and an internal user who is not at the same location as the SBC.</span></span>

![Схема, на которой показана лестница SIP](media/direct-routing-media-op-17.png)









