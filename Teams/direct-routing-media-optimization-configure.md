---
title: Direct Routing Local Media Optimization
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
description: Настройка оптимизации локальных мультимедиа для прямой маршрутизации
appliesto:
- Microsoft Teams
ms.openlocfilehash: ecbbb4f01267265f9f1041e7d51652d063ced353
ms.sourcegitcommit: 2aea6ec07149a3054ee4434c8a0bffabf1a16d25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/06/2020
ms.locfileid: "46576991"
---
# <a name="configure-local-media-optimization-for-direct-routing"></a><span data-ttu-id="c6253-103">Настройка оптимизации локальных мультимедиа для прямой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="c6253-103">Configure Local Media Optimization for Direct Routing</span></span>

<span data-ttu-id="c6253-104">Конфигурация для оптимизации локальных мультимедиа основана на параметрах сети, общих с другими облачными функциями голосовой связи, такими как маршрутизация Location-Based динамические экстренные вызовы.</span><span class="sxs-lookup"><span data-stu-id="c6253-104">Configuration for Local Media Optimization is based on network settings that are common to other cloud voice features, such as Location-Based Routing and dynamic emergency calling.</span></span> <span data-ttu-id="c6253-105">Дополнительные информацию о сетевых регионах, сетевых сайтах, подсетях и доверенных IP-адресах см. в параметрах сети для [функций облачной голосовой связи.](cloud-voice-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="c6253-105">To learn more about network regions, network sites, network subnets, and trusted IP addresses, see [Network settings for cloud voice features](cloud-voice-network-settings.md).</span></span>

<span data-ttu-id="c6253-106">Перед настройкой оптимизации локальных мультимедиа см. local [media Optimization для Direct Routing.](direct-routing-media-optimization.md)</span><span class="sxs-lookup"><span data-stu-id="c6253-106">Before you configure Local Media Optimization, see [Local media Optimization for Direct Routing](direct-routing-media-optimization.md).</span></span>  

<span data-ttu-id="c6253-107">Чтобы настроить оптимизацию локальных мультимедиа, необходимо сделать следующее:</span><span class="sxs-lookup"><span data-stu-id="c6253-107">To configure Local Media Optimization, the following steps are required.</span></span> <span data-ttu-id="c6253-108">Вы можете использовать Центр администрирования Teams или PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c6253-108">You can use the Teams Admin Center or PowerShell.</span></span> <span data-ttu-id="c6253-109">Подробные сведения см. [в топологии "Управление сетью".](manage-your-network-topology.md)</span><span class="sxs-lookup"><span data-stu-id="c6253-109">For details, see [Manage your network topology](manage-your-network-topology.md).</span></span>

1. <span data-ttu-id="c6253-110">Настройте пользователя и сайты SBC (как описано в этой статье).</span><span class="sxs-lookup"><span data-stu-id="c6253-110">Configure the user and the SBC sites (as described in this article).</span></span>
2. <span data-ttu-id="c6253-111">Настройте SBCs для оптимизации локальных мультимедиа (в зависимости от спецификации поставщика SBC).</span><span class="sxs-lookup"><span data-stu-id="c6253-111">Configure the SBCs for Local Media Optimization (according to your SBC vendor specification).</span></span>

<span data-ttu-id="c6253-112">На следующей схеме показана конфигурация сети, используемая в примерах этой статьи.</span><span class="sxs-lookup"><span data-stu-id="c6253-112">The following diagram shows the network setup used in the examples throughout this article.</span></span>

<span data-ttu-id="c6253-113">![Схема, на которой показаны примеры настройки сети](media/direct-routing-media-op-9.png "Примеры настройки сети")</span><span class="sxs-lookup"><span data-stu-id="c6253-113">![Diagram showing network setup for examples](media/direct-routing-media-op-9.png "Network setup for examples")</span></span>


## <a name="configure-the-user-and-the-sbc-sites"></a><span data-ttu-id="c6253-114">Настройка пользователя и сайтов SBC</span><span class="sxs-lookup"><span data-stu-id="c6253-114">Configure the user and the SBC sites</span></span>

<span data-ttu-id="c6253-115">Чтобы настроить пользователя и сайты SBC, необходимо:</span><span class="sxs-lookup"><span data-stu-id="c6253-115">To configure the user and the SBC sites, you will need to:</span></span>

1. <span data-ttu-id="c6253-116">[Управление внешними надежными IP-адресами.](#manage-external-trusted-ip-addresses)</span><span class="sxs-lookup"><span data-stu-id="c6253-116">[Manage external trusted IP addresses](#manage-external-trusted-ip-addresses).</span></span>  

2. <span data-ttu-id="c6253-117">[Определите топологию сети,](#define-the-network-topology) настроив сетевые регионы, сетевые сайты и подсети.</span><span class="sxs-lookup"><span data-stu-id="c6253-117">[Define the network topology](#define-the-network-topology) by configuring the network regions, network sites, and network subnets.</span></span>

3. <span data-ttu-id="c6253-118">[Определите топологию](#define-the-virtual-network-topology) виртуальной сети, назначив SBC-серверы сайтам с соответствующими режимами и значениями SBC прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="c6253-118">[Define the virtual network topology](#define-the-virtual-network-topology) by assigning SBC(s) to site(s) with relevant modes and proxy SBC values.</span></span>


## <a name="configure-sbcs-for-local-media-optimization-according-to-the-sbc-vendor-specification"></a><span data-ttu-id="c6253-119">Настройка SBC для локальной оптимизации мультимедиа в соответствии со спецификацией поставщика SBC</span><span class="sxs-lookup"><span data-stu-id="c6253-119">Configure SBC(s) for Local Media Optimization according to the SBC vendor specification</span></span>

<span data-ttu-id="c6253-120">В этой статье описана конфигурация компонентов Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="c6253-120">This article describes configuration for Microsoft components.</span></span> <span data-ttu-id="c6253-121">Сведения о настройке SBC см. в документации к поставщику SBC.</span><span class="sxs-lookup"><span data-stu-id="c6253-121">For information on SBC configuration, see your SBC vendor documentation.</span></span>

<span data-ttu-id="c6253-122">Оптимизацию локальных мультимедиа поддерживают следующие поставщики SBC:</span><span class="sxs-lookup"><span data-stu-id="c6253-122">Local Media Optimization is supported by the following SBC vendors:</span></span>

| <span data-ttu-id="c6253-123">Поставщик</span><span class="sxs-lookup"><span data-stu-id="c6253-123">Vendor</span></span> | <span data-ttu-id="c6253-124">ПРОИЗВЕД</span><span class="sxs-lookup"><span data-stu-id="c6253-124">Product</span></span> |    <span data-ttu-id="c6253-125">Версия программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="c6253-125">Software version</span></span> |
|:------------|:-------|:-------|
| [<span data-ttu-id="c6253-126">Audiocodes</span><span class="sxs-lookup"><span data-stu-id="c6253-126">Audiocodes</span></span>](https://www.audiocodes.com/media/13253/connecting-audiocodes-sbc-to-microsoft-teams-direct-routing-enterprise-model-configuration-note.pdf) |    <span data-ttu-id="c6253-127">Mediant 500 SBC</span><span class="sxs-lookup"><span data-stu-id="c6253-127">Mediant 500 SBC</span></span> |   <span data-ttu-id="c6253-128">7.20A.256</span><span class="sxs-lookup"><span data-stu-id="c6253-128">7.20A.256</span></span> | 
|            |  <span data-ttu-id="c6253-129">Mediant 800 SBC</span><span class="sxs-lookup"><span data-stu-id="c6253-129">Mediant 800 SBC</span></span> |   <span data-ttu-id="c6253-130">7.20A.256</span><span class="sxs-lookup"><span data-stu-id="c6253-130">7.20A.256</span></span> | 
|            |  <span data-ttu-id="c6253-131">Mediant 2600 SBC</span><span class="sxs-lookup"><span data-stu-id="c6253-131">Mediant 2600 SBC</span></span> |  <span data-ttu-id="c6253-132">7.20A.256</span><span class="sxs-lookup"><span data-stu-id="c6253-132">7.20A.256</span></span> | 
|            |  <span data-ttu-id="c6253-133">Mediant 4000 SBC</span><span class="sxs-lookup"><span data-stu-id="c6253-133">Mediant 4000 SBC</span></span> |  <span data-ttu-id="c6253-134">7.20A.256</span><span class="sxs-lookup"><span data-stu-id="c6253-134">7.20A.256</span></span> | 
|            |  <span data-ttu-id="c6253-135">Mediant 1000B SBC</span><span class="sxs-lookup"><span data-stu-id="c6253-135">Mediant 1000B SBC</span></span> | <span data-ttu-id="c6253-136">7.20A.256</span><span class="sxs-lookup"><span data-stu-id="c6253-136">7.20A.256</span></span> | 
|            |  <span data-ttu-id="c6253-137">Mediant 9000 SBC</span><span class="sxs-lookup"><span data-stu-id="c6253-137">Mediant 9000 SBC</span></span> |  <span data-ttu-id="c6253-138">7.20A.256</span><span class="sxs-lookup"><span data-stu-id="c6253-138">7.20A.256</span></span> | 
|            |  <span data-ttu-id="c6253-139">Mediant Virtual Edition SBC</span><span class="sxs-lookup"><span data-stu-id="c6253-139">Mediant Virtual Edition SBC</span></span> |   <span data-ttu-id="c6253-140">7.20A.256</span><span class="sxs-lookup"><span data-stu-id="c6253-140">7.20A.256</span></span> | 
|            |  <span data-ttu-id="c6253-141">Mediant Cloud Edition SBC</span><span class="sxs-lookup"><span data-stu-id="c6253-141">Mediant Cloud Edition SBC</span></span> | <span data-ttu-id="c6253-142">7.20A.256</span><span class="sxs-lookup"><span data-stu-id="c6253-142">7.20A.256</span></span> |
| [<span data-ttu-id="c6253-143">Основные функции SBC на ленте</span><span class="sxs-lookup"><span data-stu-id="c6253-143">Ribbon SBC Core</span></span>](https://support.sonus.net/display/ALLDOC/SBC+8.2+-+Configure+Local+Media+Optimization)  |  <span data-ttu-id="c6253-144">SBC 5110</span><span class="sxs-lookup"><span data-stu-id="c6253-144">SBC 5110</span></span>         | <span data-ttu-id="c6253-145">8.2</span><span class="sxs-lookup"><span data-stu-id="c6253-145">8.2</span></span>  |
|            |  <span data-ttu-id="c6253-146">SBC 5210</span><span class="sxs-lookup"><span data-stu-id="c6253-146">SBC 5210</span></span>         | <span data-ttu-id="c6253-147">8.2</span><span class="sxs-lookup"><span data-stu-id="c6253-147">8.2</span></span>  |
|            |  <span data-ttu-id="c6253-148">SBC 5400</span><span class="sxs-lookup"><span data-stu-id="c6253-148">SBC 5400</span></span>         | <span data-ttu-id="c6253-149">8.2</span><span class="sxs-lookup"><span data-stu-id="c6253-149">8.2</span></span>  |
|            |  <span data-ttu-id="c6253-150">SBC 7000</span><span class="sxs-lookup"><span data-stu-id="c6253-150">SBC 7000</span></span>         | <span data-ttu-id="c6253-151">8.2</span><span class="sxs-lookup"><span data-stu-id="c6253-151">8.2</span></span>  |
|            |  <span data-ttu-id="c6253-152">SBC SWe</span><span class="sxs-lookup"><span data-stu-id="c6253-152">SBC SWe</span></span>          | <span data-ttu-id="c6253-153">8.2</span><span class="sxs-lookup"><span data-stu-id="c6253-153">8.2</span></span>  |
| [<span data-ttu-id="c6253-154">Лента SBC Edge</span><span class="sxs-lookup"><span data-stu-id="c6253-154">Ribbon SBC Edge</span></span>](https://support.sonus.net/display/UXDOC81/Best+Practice+-+Configuring+Microsoft+Teams+Local+Media+Optimization)  |  <span data-ttu-id="c6253-155">SBC SWe Lite</span><span class="sxs-lookup"><span data-stu-id="c6253-155">SBC SWe Lite</span></span> | <span data-ttu-id="c6253-156">8.1.5</span><span class="sxs-lookup"><span data-stu-id="c6253-156">8.1.5</span></span> |
|               | <span data-ttu-id="c6253-157">SBC 1000</span><span class="sxs-lookup"><span data-stu-id="c6253-157">SBC 1000</span></span> | <span data-ttu-id="c6253-158">8.1.5</span><span class="sxs-lookup"><span data-stu-id="c6253-158">8.1.5</span></span>  |
|               | <span data-ttu-id="c6253-159">SBC 2000</span><span class="sxs-lookup"><span data-stu-id="c6253-159">SBC 2000</span></span> | <span data-ttu-id="c6253-160">8.1.5</span><span class="sxs-lookup"><span data-stu-id="c6253-160">8.1.5</span></span>  |
| [<span data-ttu-id="c6253-161">TE-SYSTEMS</span><span class="sxs-lookup"><span data-stu-id="c6253-161">TE-SYSTEMS</span></span>](https://www.anynode.de/local_media_optimization/) |  <span data-ttu-id="c6253-162">anynode</span><span class="sxs-lookup"><span data-stu-id="c6253-162">anynode</span></span>          | <span data-ttu-id="c6253-163">4.0.1 и более</span><span class="sxs-lookup"><span data-stu-id="c6253-163">4.0.1+</span></span> |
| [<span data-ttu-id="c6253-164">Oracle</span><span class="sxs-lookup"><span data-stu-id="c6253-164">Oracle</span></span>](https://www.oracle.com/industries/communications/enterprise-communications/session-border-controller/microsoft.html) | <span data-ttu-id="c6253-165">AP 1100</span><span class="sxs-lookup"><span data-stu-id="c6253-165">AP 1100</span></span> | <span data-ttu-id="c6253-166">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="c6253-166">8.4.0.0.0</span></span> |
|        | <span data-ttu-id="c6253-167">AP 3900</span><span class="sxs-lookup"><span data-stu-id="c6253-167">AP 3900</span></span> | <span data-ttu-id="c6253-168">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="c6253-168">8.4.0.0.0</span></span> |
|        | <span data-ttu-id="c6253-169">AP 4600</span><span class="sxs-lookup"><span data-stu-id="c6253-169">AP 4600</span></span> | <span data-ttu-id="c6253-170">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="c6253-170">8.4.0.0.0</span></span> | 
|        | <span data-ttu-id="c6253-171">AP 6300</span><span class="sxs-lookup"><span data-stu-id="c6253-171">AP 6300</span></span> | <span data-ttu-id="c6253-172">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="c6253-172">8.4.0.0.0</span></span> |
|        | <span data-ttu-id="c6253-173">AP 6350</span><span class="sxs-lookup"><span data-stu-id="c6253-173">AP 6350</span></span> | <span data-ttu-id="c6253-174">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="c6253-174">8.4.0.0.0</span></span> | 
|        | <span data-ttu-id="c6253-175">VME</span><span class="sxs-lookup"><span data-stu-id="c6253-175">VME</span></span>     | <span data-ttu-id="c6253-176">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="c6253-176">8.4.0.0.0</span></span> |


## <a name="manage-external-trusted-ip-addresses"></a><span data-ttu-id="c6253-177">Управление внешними надежными IP-адресами</span><span class="sxs-lookup"><span data-stu-id="c6253-177">Manage external trusted IP addresses</span></span>

<span data-ttu-id="c6253-178">Внешние доверенные IP являются внешними IP-пользователями корпоративной сети.</span><span class="sxs-lookup"><span data-stu-id="c6253-178">External trusted IPs are the Internet external IPs of the enterprise network.</span></span> <span data-ttu-id="c6253-179">Это IP-адреса, используемые клиентами Microsoft Teams при подключении к Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c6253-179">These IP’s are the IP addresses used by Microsoft Teams clients when they connect to Microsoft 365.</span></span> <span data-ttu-id="c6253-180">Эти внешние IPS необходимо добавить для каждого сайта, на котором есть пользователи с локальной оптимизацией мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="c6253-180">You need to add these external IPs for each site where you have users using Local Media Optimization.</span></span>

<span data-ttu-id="c6253-181">Чтобы добавить общедоступные IP-адреса для каждого сайта, используйте New-CsTenantTrustedIPAddress управления.</span><span class="sxs-lookup"><span data-stu-id="c6253-181">To add the public IP addresses for each site, use the New-CsTenantTrustedIPAddress cmdlet.</span></span> <span data-ttu-id="c6253-182">Для клиента можно определить неограниченное количество доверенных IP-адресов.</span><span class="sxs-lookup"><span data-stu-id="c6253-182">You can define an unlimited number of trusted IP addresses for a tenant.</span></span> <span data-ttu-id="c6253-183">Если внешними IP-адресами, которые видны Microsoft 365, являются IPv4- и IPv6-адреса, необходимо добавить оба типа IP-адресов.</span><span class="sxs-lookup"><span data-stu-id="c6253-183">If the external IPs seen by Microsoft 365 are both IPv4 and IPv6 addresses, you need to add both types of IP addresses.</span></span> <span data-ttu-id="c6253-184">Для IPv4 используйте маску 32.</span><span class="sxs-lookup"><span data-stu-id="c6253-184">For IPv4, use mask 32.</span></span> <span data-ttu-id="c6253-185">Для IPv6 используйте маску 128.</span><span class="sxs-lookup"><span data-stu-id="c6253-185">For IPv6, use mask 128.</span></span> <span data-ttu-id="c6253-186">Вы можете добавить как отдельные внешние IP-адреса, так и внешние IP-подсети, указав в этом окне различные маскикбиты.</span><span class="sxs-lookup"><span data-stu-id="c6253-186">You can add both individual external IP addresses and external IP subnets by specifying different MaskBits on the cmdlet.</span></span>

```
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description>
```


<span data-ttu-id="c6253-187">Пример добавления доверенных IP-адресов.</span><span class="sxs-lookup"><span data-stu-id="c6253-187">Example of adding trusted IP addresses.</span></span>

```
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.110 -MaskBits 32 -Description "Vietnam site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.120 -MaskBits 32 -Description "Indonesia site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.130 -MaskBits 32 -Description "Singapore site trusted IP"
```


## <a name="define-the-network-topology"></a><span data-ttu-id="c6253-188">Определение топологии сети</span><span class="sxs-lookup"><span data-stu-id="c6253-188">Define the network topology</span></span>

<span data-ttu-id="c6253-189">В этом разделе описано, как определить сетевые регионы, сетевые сайты и подсети для топологии сети.</span><span class="sxs-lookup"><span data-stu-id="c6253-189">This section describes how to define the network regions, network sites, and network subnets for your network topology.</span></span>

<span data-ttu-id="c6253-190">Все параметры должны чувствительны к делу, поэтому необходимо убедиться, что используется тот же случай, который использовался при настройке.</span><span class="sxs-lookup"><span data-stu-id="c6253-190">All parameters are case sensitive so you need to ensure that you use the same case that was used during setup.</span></span>  <span data-ttu-id="c6253-191">(Например, значения GatewaySiteID "Вьетнам" и "Вьетнам" будут рассматриваться как разные сайты.)</span><span class="sxs-lookup"><span data-stu-id="c6253-191">(For example, GatewaySiteID values “Vietnam” and “vietnam” will be treated as different sites.)</span></span>

### <a name="define-network-regions"></a><span data-ttu-id="c6253-192">Определение сетевых регионов</span><span class="sxs-lookup"><span data-stu-id="c6253-192">Define network regions</span></span>

<span data-ttu-id="c6253-193">Чтобы определить сетевые регионы, используйте New-CsTenantNetworkRegion.</span><span class="sxs-lookup"><span data-stu-id="c6253-193">To define network regions, use the New-CsTenantNetworkRegion cmdlet.</span></span> <span data-ttu-id="c6253-194">Параметр RegionID — это логическое имя, которое представляет географическое положение региона и не имеет зависимостей и ограничений.</span><span class="sxs-lookup"><span data-stu-id="c6253-194">The RegionID parameter is a logical name that represents the geography of the region and has no dependencies or restrictions.</span></span> <span data-ttu-id="c6253-195">Параметр CentralSite <site ID> необязателен.</span><span class="sxs-lookup"><span data-stu-id="c6253-195">The CentralSite <site ID> parameter is optional.</span></span>

```
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

<span data-ttu-id="c6253-196">В следующем примере создается сетевой регион с названием APAC:</span><span class="sxs-lookup"><span data-stu-id="c6253-196">The following example creates a network region named APAC:</span></span>

```
New-CsTenantNetworkRegion -NetworkRegionID "APAC"  
```

###  <a name="define-network-sites"></a><span data-ttu-id="c6253-197">Определение сетевых сайтов</span><span class="sxs-lookup"><span data-stu-id="c6253-197">Define network sites</span></span>

<span data-ttu-id="c6253-198">Чтобы определить сетевые сайты, используйте New-CsTenantNetworkSite управления.</span><span class="sxs-lookup"><span data-stu-id="c6253-198">To define network sites, use the New-CsTenantNetworkSite cmdlet.</span></span> <span data-ttu-id="c6253-199">Каждый сетевой сайт должен быть связан с сетевым регионом.</span><span class="sxs-lookup"><span data-stu-id="c6253-199">Each network site must be associated with a network region.</span></span>

```
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```

<span data-ttu-id="c6253-200">В следующем примере создаются три новых сетевых сайта: Вьетнам, Индонезия и Сингапур в регионе APAC:</span><span class="sxs-lookup"><span data-stu-id="c6253-200">The following example creates three new network sites, Vietnam, Indonesia, and Singapore in the APAC region:</span></span>

```
New-CsTenantNetworkSite -NetworkSiteID "Vietnam" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Indonesia" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Singapore" -NetworkRegionID "APAC"
```

### <a name="define-network-subnets"></a><span data-ttu-id="c6253-201">Определение сетевых подсетей</span><span class="sxs-lookup"><span data-stu-id="c6253-201">Define network subnets</span></span>

<span data-ttu-id="c6253-202">Чтобы определить сетевые подсети и связать их с сетевыми сайтами, воспользуйтесь New-CsTenantNetworkSubnet-данными.</span><span class="sxs-lookup"><span data-stu-id="c6253-202">To define network subnets and associate them to network sites, use the New-CsTenantNetworkSubnet cmdlet.</span></span> <span data-ttu-id="c6253-203">Каждую сетевую подсеть можно связывать только с одним сайтом.</span><span class="sxs-lookup"><span data-stu-id="c6253-203">Each network subnet can only be associated with one site.</span></span> 

```
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>
```

<span data-ttu-id="c6253-204">В следующем примере определяются три подсети сети и они связывается с тремя сетевыми сайтами: Вьетнам, Индонезия и Сингапур:</span><span class="sxs-lookup"><span data-stu-id="c6253-204">The following example defines three network subnets and associates them with the three network sites:  Vietnam, Indonesia, and Singapore:</span></span>

```
New-CsTenantNetworkSubnet -SubnetID 192.168.1.0 -MaskBits 24 -NetworkSiteID “Vietnam”
New-CsTenantNetworkSubnet -SubnetID 192.168.2.0 -MaskBits 24 -NetworkSiteID “Indonesia”
New-CsTenantNetworkSubnet -SubnetID 192.168.3.0 -MaskBits 24 -NetworkSiteID “Singapore”
```

## <a name="define-the-virtual-network-topology"></a><span data-ttu-id="c6253-205">Определение топологии виртуальной сети</span><span class="sxs-lookup"><span data-stu-id="c6253-205">Define the virtual network topology</span></span> 

<span data-ttu-id="c6253-206">Во-первых, администратор клиента создает новую конфигурацию SBC для каждого соответствующего SBC с помощью New-CsOnlinePSTNGateway управления.</span><span class="sxs-lookup"><span data-stu-id="c6253-206">First, the tenant administrator creates a new SBC configuration for each relevant SBC by using the New-CsOnlinePSTNGateway cmdlet.</span></span>
<span data-ttu-id="c6253-207">Администратор клиента определяет топологию виртуальной сети, определяя сетевые сайты для объектов шлюза STN с помощью Set-CsOnlinePSTNGateway управления:</span><span class="sxs-lookup"><span data-stu-id="c6253-207">The tenant administrator defines the virtual network topology by specifying the network sites for the PSTN gateway objects using the Set-CsOnlinePSTNGateway cmdlet:</span></span>

```
PS C:\> Set-CsOnlinePSTNGateway -Identity <Identity> -GatewaySiteID <site ID> -MediaBypass <true/false> -BypassMode <Always/OnlyForLocalUsers> -ProxySBC  <proxy SBC FQDN or $null>
```

<span data-ttu-id="c6253-208">Обратите внимание на следующее:</span><span class="sxs-lookup"><span data-stu-id="c6253-208">Note the following:</span></span> 
   - <span data-ttu-id="c6253-209">Если у клиента один SBC, параметр -ProxySBC должен быть обязательным $null или FQDN SBC (Центральный SBC с сценариями централизованной связи).</span><span class="sxs-lookup"><span data-stu-id="c6253-209">If the customer has a single SBC, the -ProxySBC parameter must be either mandatory $null or SBC FQDN value (Central SBC with centralized trunks scenario).</span></span>
   - <span data-ttu-id="c6253-210">Параметр -MediaBypass должен иметь $true для поддержки локальной оптимизации мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="c6253-210">The -MediaBypass parameter must be set to $true in order to support Local Media Optimization.</span></span>
   - <span data-ttu-id="c6253-211">Если у SBC нет параметра -BypassMode, то X-MS-загона не будут отправлены.</span><span class="sxs-lookup"><span data-stu-id="c6253-211">If the SBC doesn’t have the -BypassMode parameter set, X-MS headers will not be sent.</span></span> 
   - <span data-ttu-id="c6253-212">Все параметры должны чувствительны к делу, поэтому необходимо убедиться, что используется тот же случай, который использовался при настройке.</span><span class="sxs-lookup"><span data-stu-id="c6253-212">All parameters are case sensitive so you need to ensure that you use the same case that was used used during setup.</span></span>  <span data-ttu-id="c6253-213">(Например, значения GatewaySiteID "Вьетнам" и "Вьетнам" будут рассматриваться как разные сайты.)</span><span class="sxs-lookup"><span data-stu-id="c6253-213">(For example, GatewaySiteID values “Vietnam” and “vietnam” will be treated as different sites.)</span></span>

<span data-ttu-id="c6253-214">В следующем примере к сетевым сайтам Вьетнама, Индонезии и Сингапура в регионе APAC добавляются три SBCs в режиме "Всегда обходить":</span><span class="sxs-lookup"><span data-stu-id="c6253-214">The following example adds three SBCs to the network sites Vietnam, Indonesia, and Singapore in the APAC region with mode Always bypass:</span></span>

```
Set-CSOnlinePSTNGateway -Identity “proxysbc.contoso.com” -GatewaySiteID “Singapore” -MediaBypass $true -BypassMode “Always” -ProxySBC $null

Set-CSOnlinePSTNGateway -Identity “VNsbc.contoso.com” -GatewaySiteID “Vietnam” -MediaBypass $true -BypassMode “Always” -ProxySBC “proxysbc.contoso.com”

Set-CSOnlinePSTNGateway -Identity “IDsbc.contoso.com” -GatewaySiteID “Indonesia” -MediaBypass $true -BypassMode “Always” -ProxySBC “proxysbc.contoso.com”
```

<span data-ttu-id="c6253-215">Примечание. Чтобы обеспечить непрерывные операции при одновременной настройке локальной оптимизации мультимедиа и маршрутизации Location-Based (LBR), для LBR необходимо включить пустую систему SBCs для LBR, задав параметр GatewaySiteLbrEnabled для $true для каждого нитерного SBC.</span><span class="sxs-lookup"><span data-stu-id="c6253-215">Note: To ensure uninterrupted operations when Local Media Optimization and Location-Based Routing (LBR) are configured at the same time, downstream SBCs must be enabled for LBR by setting the GatewaySiteLbrEnabled parameter to $true for each downstream SBC.</span></span> <span data-ttu-id="c6253-216">(Этот параметр не является обязательным для прокси-сервера SBC.)</span><span class="sxs-lookup"><span data-stu-id="c6253-216">(This setting is not mandatory for the proxy SBC.)</span></span>

<span data-ttu-id="c6253-217">На основе вышеприведенной информации direct Routing включает три фирменных заглавных для SIP приглашения и повторного приглашения, как показано в таблице ниже.</span><span class="sxs-lookup"><span data-stu-id="c6253-217">Based on the information above, Direct Routing will include three proprietary SIP Headers to SIP Invites and Re-invites as shown  in the following table.</span></span>

<span data-ttu-id="c6253-218">X-MS Headers introduced in Direct Routing on Invites and Re-Invites if BypassMode is defined:</span><span class="sxs-lookup"><span data-stu-id="c6253-218">X-MS Headers introduced in Direct Routing on Invites and Re-Invites if BypassMode is defined:</span></span>

| <span data-ttu-id="c6253-219">Header name</span><span class="sxs-lookup"><span data-stu-id="c6253-219">Header name</span></span> | <span data-ttu-id="c6253-220">Значения</span><span class="sxs-lookup"><span data-stu-id="c6253-220">Values</span></span> | <span data-ttu-id="c6253-221">Комментарии</span><span class="sxs-lookup"><span data-stu-id="c6253-221">Comments</span></span> | 
|:------------|:-------|:-------|
| <span data-ttu-id="c6253-222">X-MS-UserLocation</span><span class="sxs-lookup"><span data-stu-id="c6253-222">X-MS-UserLocation</span></span> | <span data-ttu-id="c6253-223">внутреннее/внешнее</span><span class="sxs-lookup"><span data-stu-id="c6253-223">internal/external</span></span> | <span data-ttu-id="c6253-224">Указывает, внутренний или внешний пользователь</span><span class="sxs-lookup"><span data-stu-id="c6253-224">Indicates if user is internal or external</span></span> |
| <span data-ttu-id="c6253-225">SIP-URI ПРИГЛАШЕНИЯ: +84439263000@VNsbc.contoso.com SIP /2.0</span><span class="sxs-lookup"><span data-stu-id="c6253-225">Request-URI   INVITE sip: +84439263000@VNsbc.contoso.com SIP /2.0</span></span> | <span data-ttu-id="c6253-226">SBC FQDN</span><span class="sxs-lookup"><span data-stu-id="c6253-226">SBC FQDN</span></span> | <span data-ttu-id="c6253-227">FQDN, целевое для звонка, даже если SBC не подключен напрямую к Direct Routing</span><span class="sxs-lookup"><span data-stu-id="c6253-227">The FQDN which is targeted for the call even if the SBC is not directly connected to Direct Routing</span></span> |
| <span data-ttu-id="c6253-228">X-MS-MediaPath</span><span class="sxs-lookup"><span data-stu-id="c6253-228">X-MS-MediaPath</span></span> | <span data-ttu-id="c6253-229">Пример: proxysbc.contoso.com, VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c6253-229">Example: proxysbc.contoso.com, VNsbc.contoso.com</span></span> | <span data-ttu-id="c6253-230">Порядок SBCs, которые должны использоваться для пути мультимедиа между пользователем и целевой SBC.</span><span class="sxs-lookup"><span data-stu-id="c6253-230">Order of SBCs that should be used for Media path between the user and target SBC.</span></span> <span data-ttu-id="c6253-231">Окончательный SBC всегда последний</span><span class="sxs-lookup"><span data-stu-id="c6253-231">The final SBC is always last</span></span> |
| <span data-ttu-id="c6253-232">X-MS-UserSite</span><span class="sxs-lookup"><span data-stu-id="c6253-232">X-MS-UserSite</span></span> | <span data-ttu-id="c6253-233">usersiteID</span><span class="sxs-lookup"><span data-stu-id="c6253-233">usersiteID</span></span> | <span data-ttu-id="c6253-234">Строка, определяемая администратором клиента</span><span class="sxs-lookup"><span data-stu-id="c6253-234">String defined by tenant administrator</span></span> |

## <a name="call-flows"></a><span data-ttu-id="c6253-235">Потоки вызовов</span><span class="sxs-lookup"><span data-stu-id="c6253-235">Call flows</span></span> 

<span data-ttu-id="c6253-236">Ниже показаны потоки вызовов для двух режимов:</span><span class="sxs-lookup"><span data-stu-id="c6253-236">The following shows call flows for two modes:</span></span>

- [<span data-ttu-id="c6253-237">Всегда обходить</span><span class="sxs-lookup"><span data-stu-id="c6253-237">Always Bypass</span></span>](#always-bypass-mode)
- [<span data-ttu-id="c6253-238">Только для локальных пользователей</span><span class="sxs-lookup"><span data-stu-id="c6253-238">Only for local users</span></span>](#only-for-local-users-mode)

### <a name="always-bypass-mode"></a><span data-ttu-id="c6253-239">Режим "Всегда обходить"</span><span class="sxs-lookup"><span data-stu-id="c6253-239">Always Bypass mode</span></span>

<span data-ttu-id="c6253-240">Режим "Всегда обходить" проще всего настроить.</span><span class="sxs-lookup"><span data-stu-id="c6253-240">Always Bypass mode is the simplest option to configure.</span></span> <span data-ttu-id="c6253-241">Администратор клиента может настроить один сайт для всех пользователей и веб-сайтов, если с любого сайта можно получить доступ к всем SBCs.</span><span class="sxs-lookup"><span data-stu-id="c6253-241">The tenant administrator can configure a single site for all users and SBCs if all SBCs are reachable from any site.</span></span>

<span data-ttu-id="c6253-242">В примерах приводится обойдение режима "Всегда" в следующих сценариях:</span><span class="sxs-lookup"><span data-stu-id="c6253-242">The examples show Always bypass mode for the following scenarios:</span></span>

- [<span data-ttu-id="c6253-243">Исходящие звонки, и пользователь находится в том же расположении, что и SBC</span><span class="sxs-lookup"><span data-stu-id="c6253-243">Outbound calls and the user is in the same location as the SBC</span></span>](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [<span data-ttu-id="c6253-244">Входящие звонки и пользователь находится в том же расположении, что и SBC</span><span class="sxs-lookup"><span data-stu-id="c6253-244">Inbound calls and the user is in the same location as the SBC</span></span>](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [<span data-ttu-id="c6253-245">Исходящие звонки, и пользователь является внешним</span><span class="sxs-lookup"><span data-stu-id="c6253-245">Outbound calls and the user is external</span></span>](#outbound-calls-and-the-user-is-external-with-always-bypass)
- [<span data-ttu-id="c6253-246">Входящие звонки, и пользователь является внешним</span><span class="sxs-lookup"><span data-stu-id="c6253-246">Inbound calls and the user is external</span></span>](#inbound-calls-and-the-user-is-external-with-always-bypass)

<span data-ttu-id="c6253-247">В следующей таблице показаны FQDN и IP-адреса, используемые в примерах:</span><span class="sxs-lookup"><span data-stu-id="c6253-247">The following table shows the FQDN and IP addresses used in the examples:</span></span>

| <span data-ttu-id="c6253-248">Полное доменное имя</span><span class="sxs-lookup"><span data-stu-id="c6253-248">FQDN</span></span> | <span data-ttu-id="c6253-249">Внешний IP-адрес SBC</span><span class="sxs-lookup"><span data-stu-id="c6253-249">SBC external IP address</span></span> | <span data-ttu-id="c6253-250">Внутренний IP-адрес SBC</span><span class="sxs-lookup"><span data-stu-id="c6253-250">SBC internal IP Address</span></span> | <span data-ttu-id="c6253-251">Внутренняя подсеть</span><span class="sxs-lookup"><span data-stu-id="c6253-251">Internal subnet</span></span> | <span data-ttu-id="c6253-252">Местоположение</span><span class="sxs-lookup"><span data-stu-id="c6253-252">Location</span></span> | <span data-ttu-id="c6253-253">Внешний NAT (доверенный IP-адрес)</span><span class="sxs-lookup"><span data-stu-id="c6253-253">External NAT (Trusted IP)</span></span> |
|:------------|:-------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="c6253-254">VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c6253-254">VNsbc.contoso.com</span></span> | <span data-ttu-id="c6253-255">Нет</span><span class="sxs-lookup"><span data-stu-id="c6253-255">None</span></span> | <span data-ttu-id="c6253-256">192.168.1.5</span><span class="sxs-lookup"><span data-stu-id="c6253-256">192.168.1.5</span></span> | <span data-ttu-id="c6253-257">192.168.1.0/24</span><span class="sxs-lookup"><span data-stu-id="c6253-257">192.168.1.0/24</span></span> | <span data-ttu-id="c6253-258">Вьетнам</span><span class="sxs-lookup"><span data-stu-id="c6253-258">Vietnam</span></span> | <span data-ttu-id="c6253-259">172.16.240.110</span><span class="sxs-lookup"><span data-stu-id="c6253-259">172.16.240.110</span></span> |
| <span data-ttu-id="c6253-260">IDsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c6253-260">IDsbc.contoso.com</span></span> | <span data-ttu-id="c6253-261">Нет</span><span class="sxs-lookup"><span data-stu-id="c6253-261">None</span></span> | <span data-ttu-id="c6253-262">192.168.2.5</span><span class="sxs-lookup"><span data-stu-id="c6253-262">192.168.2.5</span></span> | <span data-ttu-id="c6253-263">192.168.2.0/24</span><span class="sxs-lookup"><span data-stu-id="c6253-263">192.168.2.0/24</span></span> | <span data-ttu-id="c6253-264">Индонезия</span><span class="sxs-lookup"><span data-stu-id="c6253-264">Indonesia</span></span> | <span data-ttu-id="c6253-265">172.16.240.120</span><span class="sxs-lookup"><span data-stu-id="c6253-265">172.16.240.120</span></span> |
| <span data-ttu-id="c6253-266">proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c6253-266">proxysbc.contoso.com</span></span> | <span data-ttu-id="c6253-267">172.16.240.133</span><span class="sxs-lookup"><span data-stu-id="c6253-267">172.16.240.133</span></span> | <span data-ttu-id="c6253-268">192.168.3.5</span><span class="sxs-lookup"><span data-stu-id="c6253-268">192.168.3.5</span></span> | <span data-ttu-id="c6253-269">192.168.3.0/24</span><span class="sxs-lookup"><span data-stu-id="c6253-269">192.168.3.0/24</span></span> | <span data-ttu-id="c6253-270">Сингапур</span><span class="sxs-lookup"><span data-stu-id="c6253-270">Singapore</span></span> | <span data-ttu-id="c6253-271">172.16.240.130</span><span class="sxs-lookup"><span data-stu-id="c6253-271">172.16.240.130</span></span> |



#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a><span data-ttu-id="c6253-272">Исходящие звонки и пользователь находится в том же расположении, что и SBC с помощью always Bypass</span><span class="sxs-lookup"><span data-stu-id="c6253-272">Outbound calls and the user is in the same location as the SBC with Always Bypass</span></span>

| <span data-ttu-id="c6253-273">Режим</span><span class="sxs-lookup"><span data-stu-id="c6253-273">Mode</span></span> |    <span data-ttu-id="c6253-274">Пользователь</span><span class="sxs-lookup"><span data-stu-id="c6253-274">User</span></span> |  <span data-ttu-id="c6253-275">Местоположение</span><span class="sxs-lookup"><span data-stu-id="c6253-275">Location</span></span> |  <span data-ttu-id="c6253-276">Направление звонка</span><span class="sxs-lookup"><span data-stu-id="c6253-276">Call direction</span></span> |
|:------------|:-------|:-------| :-------|
| <span data-ttu-id="c6253-277">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="c6253-277">AlwaysBypass</span></span> |    <span data-ttu-id="c6253-278">Internal</span><span class="sxs-lookup"><span data-stu-id="c6253-278">Internal</span></span> |  <span data-ttu-id="c6253-279">Тот же сайт, что и SBC</span><span class="sxs-lookup"><span data-stu-id="c6253-279">The same site as SBC</span></span> |  <span data-ttu-id="c6253-280">Исходящее</span><span class="sxs-lookup"><span data-stu-id="c6253-280">Outbound</span></span> |

<span data-ttu-id="c6253-281">В следующей таблице показаны конфигурация и действие для конечных пользователей.</span><span class="sxs-lookup"><span data-stu-id="c6253-281">The following table shows the end user configuration and action:</span></span>

| <span data-ttu-id="c6253-282">Физическое местонахождение пользователя</span><span class="sxs-lookup"><span data-stu-id="c6253-282">User physical location</span></span>| <span data-ttu-id="c6253-283">Пользователь звонит на номер или принимает его</span><span class="sxs-lookup"><span data-stu-id="c6253-283">User makes or receives a call to/from number</span></span> | <span data-ttu-id="c6253-284">Номер телефона пользователя</span><span class="sxs-lookup"><span data-stu-id="c6253-284">User phone number</span></span>  | <span data-ttu-id="c6253-285">Политика маршрутинга голосовой почты в Интернете</span><span class="sxs-lookup"><span data-stu-id="c6253-285">Online Voice Routing Policy</span></span> | <span data-ttu-id="c6253-286">Режим, настроенный для SBC</span><span class="sxs-lookup"><span data-stu-id="c6253-286">Mode configured for SBC</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="c6253-287">Вьетнам</span><span class="sxs-lookup"><span data-stu-id="c6253-287">Vietnam</span></span> | <span data-ttu-id="c6253-288">+84 4 3926 3000</span><span class="sxs-lookup"><span data-stu-id="c6253-288">+84 4 3926 3000</span></span> | <span data-ttu-id="c6253-289">+84 4 5555 5555</span><span class="sxs-lookup"><span data-stu-id="c6253-289">+84 4 5555 5555</span></span>   | <span data-ttu-id="c6253-290">Приоритет 1: ^ \+ 84(\d {9} )$ -VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c6253-290">Priority 1: ^\+84(\d{9})$ -VNsbc.contoso.com</span></span> <br> <span data-ttu-id="c6253-291">Приоритет 2: .\* — proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c6253-291">Priority 2: .\* - proxysbc.contoso.com</span></span>   | <span data-ttu-id="c6253-292">VNsbc.contoso.com – всегда обходить</span><span class="sxs-lookup"><span data-stu-id="c6253-292">VNsbc.contoso.com – Always Bypass</span></span> <br> <span data-ttu-id="c6253-293">proxysbc.contoso.com – всегда обходить</span><span class="sxs-lookup"><span data-stu-id="c6253-293">proxysbc.contoso.com – Always Bypass</span></span>


<span data-ttu-id="c6253-294">На следующей схеме показана схема SIP для исходяшего звонка в режиме обхода Always и пользователя в том же расположении, что и SBC.</span><span class="sxs-lookup"><span data-stu-id="c6253-294">The following diagram shows the SIP ladder for an outbound call with Always bypass mode, and the user in the same location as the SBC.</span></span>

<span data-ttu-id="c6253-295">![Схема исходящие вызовы](media/direct-routing-media-op-10.png "Исходящие звонки")</span><span class="sxs-lookup"><span data-stu-id="c6253-295">![Diagram showing outbound calls](media/direct-routing-media-op-10.png "Outbound calls")</span></span>

<span data-ttu-id="c6253-296">В следующей таблице показаны X-MS-загона, отправленные direct Routing:</span><span class="sxs-lookup"><span data-stu-id="c6253-296">The following table shows the X-MS headers sent by Direct Routing:</span></span>

| <span data-ttu-id="c6253-297">Параметр</span><span class="sxs-lookup"><span data-stu-id="c6253-297">Parameter</span></span> | <span data-ttu-id="c6253-298">Пояснение</span><span class="sxs-lookup"><span data-stu-id="c6253-298">Explanation</span></span> |
|:------------|:-------|
| <span data-ttu-id="c6253-299">Пригласить +8443926300@VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c6253-299">Invite +8443926300@VNsbc.contoso.com</span></span> | <span data-ttu-id="c6253-300">Целевое FQDN SBC, определяемое в политике маршрутинга голосовой почты Online, отправляется в URI запроса.</span><span class="sxs-lookup"><span data-stu-id="c6253-300">The target FQDN of the SBC as defined in the Online Voice Routing Policy is sent in the Request URI</span></span> | 
| <span data-ttu-id="c6253-301">X-MS-UserLocation: внутреннее</span><span class="sxs-lookup"><span data-stu-id="c6253-301">X-MS-UserLocation: internal</span></span> | <span data-ttu-id="c6253-302">Поле показывает, что пользователь находится в корпоративной сети.</span><span class="sxs-lookup"><span data-stu-id="c6253-302">The field indicated that user is located inside the corporate network</span></span> |
| <span data-ttu-id="c6253-303">X-MS-MediaPath: VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c6253-303">X-MS-MediaPath: VNsbc.contoso.com</span></span> |   <span data-ttu-id="c6253-304">Указывает, какой SBC должен проходить через клиент до целевого SBC.</span><span class="sxs-lookup"><span data-stu-id="c6253-304">Specifies which SBC the client must traverse to the target SBC.</span></span> <span data-ttu-id="c6253-305">В этом случае у нас есть Always Bypass, а клиент является внутренним именем целевого клиента, от которого отправляется только имя в заглавном имени.</span><span class="sxs-lookup"><span data-stu-id="c6253-305">In this case as we have Always Bypass, and the client is internal the target name sent as the only name in the header.</span></span> | 
|<span data-ttu-id="c6253-306">X-MS-UserSite: Вьетнам</span><span class="sxs-lookup"><span data-stu-id="c6253-306">X-MS-UserSite: Vietnam</span></span> |   <span data-ttu-id="c6253-307">Поле, показанное на сайте, где находится пользователь.</span><span class="sxs-lookup"><span data-stu-id="c6253-307">The field indicated within the site the user is located.</span></span> |


#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a><span data-ttu-id="c6253-308">Входящие звонки и пользователь находится в том же расположении, что и SBC с помощью always Bypass</span><span class="sxs-lookup"><span data-stu-id="c6253-308">Inbound calls and the user is in the same location as the SBC with Always Bypass</span></span>

| <span data-ttu-id="c6253-309">Режим</span><span class="sxs-lookup"><span data-stu-id="c6253-309">Mode</span></span> |    <span data-ttu-id="c6253-310">Пользователь</span><span class="sxs-lookup"><span data-stu-id="c6253-310">User</span></span> |  <span data-ttu-id="c6253-311">Местоположение</span><span class="sxs-lookup"><span data-stu-id="c6253-311">Location</span></span> |  <span data-ttu-id="c6253-312">Направление звонка</span><span class="sxs-lookup"><span data-stu-id="c6253-312">Call direction</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="c6253-313">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="c6253-313">AlwaysBypass</span></span> |    <span data-ttu-id="c6253-314">Internal</span><span class="sxs-lookup"><span data-stu-id="c6253-314">Internal</span></span> | <span data-ttu-id="c6253-315">Тот же сайт, что и SBC</span><span class="sxs-lookup"><span data-stu-id="c6253-315">The same site as SBC</span></span> | <span data-ttu-id="c6253-316">Входящий</span><span class="sxs-lookup"><span data-stu-id="c6253-316">Inbound</span></span> |


<span data-ttu-id="c6253-317">При входящий звонок местонахождение пользователя неизвестно, и SBC должен угадать его местонахождение.</span><span class="sxs-lookup"><span data-stu-id="c6253-317">On an inbound call, the location of the user is unknown, and the SBC must guess where the user is.</span></span> <span data-ttu-id="c6253-318">Если он неправил, потребуется повторно пригласить его.</span><span class="sxs-lookup"><span data-stu-id="c6253-318">If the guess is not correct, a re-invite will be required.</span></span> <span data-ttu-id="c6253-319">В этом случае предполагается, что пользователь является внутренним, мультимедиа могут перетекать напрямую и не требуются дальнейшие действия (повторное приглашение).</span><span class="sxs-lookup"><span data-stu-id="c6253-319">This case assumes user is internal, media can flow directly, and no further actions are required (re-invite).</span></span>
<span data-ttu-id="c6253-320">SBC, подключенный к службе direct Routing, сообщает о расположении SBC, Record-Route контактов.</span><span class="sxs-lookup"><span data-stu-id="c6253-320">The SBC connected to the Direct Routing service reports the originating SBC location by providing Record-Route and Contact fields.</span></span> <span data-ttu-id="c6253-321">На основе этих полей путь к мультимедиа вычисляется путем Direct Routing.</span><span class="sxs-lookup"><span data-stu-id="c6253-321">Based on these fields, the media path is calculated by Direct Routing.</span></span>

<span data-ttu-id="c6253-322">Примечание. Учитывая, что у пользователя может быть несколько конечных точек, поддержка 183 не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="c6253-322">Note: Given that a user can have multiple endpoints, support of 183 is not possible.</span></span> <span data-ttu-id="c6253-323">В этом случае при прямой маршрутике всегда используется 180 звонка.</span><span class="sxs-lookup"><span data-stu-id="c6253-323">The Direct Routing will always use 180 Ringing in this case.</span></span> 

<span data-ttu-id="c6253-324">На следующей схеме показана схема SIP для входящие зовов с режимом AlwaysBypass, и пользователь находится в том же расположении, что и SBC.</span><span class="sxs-lookup"><span data-stu-id="c6253-324">The following diagram shows the SIP ladder for in inbound call with AlwaysBypass mode, and the user is in the same location as the SBC.</span></span>

![Схема, показывающая SIP-диаграмму](media/direct-routing-media-op-11.png)


#### <a name="outbound-calls-and-the-user-is-external-with-always-bypass"></a><span data-ttu-id="c6253-326">Исходящие звонки и внешний пользователь с помощью always Bypass</span><span class="sxs-lookup"><span data-stu-id="c6253-326">Outbound calls and the user is external with Always Bypass</span></span>

| <span data-ttu-id="c6253-327">Режим</span><span class="sxs-lookup"><span data-stu-id="c6253-327">Mode</span></span> |    <span data-ttu-id="c6253-328">Пользователь</span><span class="sxs-lookup"><span data-stu-id="c6253-328">User</span></span> |  <span data-ttu-id="c6253-329">Сайт</span><span class="sxs-lookup"><span data-stu-id="c6253-329">Site</span></span> |  <span data-ttu-id="c6253-330">Направление звонка</span><span class="sxs-lookup"><span data-stu-id="c6253-330">Call direction</span></span>
|:------------|:-------|:-------|:-------|
<span data-ttu-id="c6253-331">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="c6253-331">AlwaysBypass</span></span> |  <span data-ttu-id="c6253-332">Внешняя</span><span class="sxs-lookup"><span data-stu-id="c6253-332">External</span></span> |  <span data-ttu-id="c6253-333">Н/Д</span><span class="sxs-lookup"><span data-stu-id="c6253-333">N/A</span></span> | <span data-ttu-id="c6253-334">Исходящее</span><span class="sxs-lookup"><span data-stu-id="c6253-334">Outbound</span></span> |


<span data-ttu-id="c6253-335">На следующей схеме показана схема SIP для исходящие вызовы в режиме AlwaysBypass, а пользователь является внешним:</span><span class="sxs-lookup"><span data-stu-id="c6253-335">The following diagram shows the SIP ladder for an outbound call with AlwaysBypass mode, and the user is external:</span></span>

![Схема, показывающая SIP-диаграмму](media/direct-routing-media-op-12.png)

<span data-ttu-id="c6253-337">В следующей таблице показаны X-MS-загона, отправленные службой Direct Routing:</span><span class="sxs-lookup"><span data-stu-id="c6253-337">The following table shows the X-MS headers sent by the Direct Routing service:</span></span>

| <span data-ttu-id="c6253-338">Параметр</span><span class="sxs-lookup"><span data-stu-id="c6253-338">Parameter</span></span> |   <span data-ttu-id="c6253-339">Пояснение</span><span class="sxs-lookup"><span data-stu-id="c6253-339">Explanation</span></span> |
|:------------|:-------|
|<span data-ttu-id="c6253-340">Пригласить +8443926300@VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c6253-340">Invite +8443926300@VNsbc.contoso.com</span></span> | <span data-ttu-id="c6253-341">Целевое FQDN SBC, определяемое в политике маршрутинга голосовой почты Online, отправляется в URI запроса.</span><span class="sxs-lookup"><span data-stu-id="c6253-341">The target FQDN of the SBC as defined in the Online Voice Routing Policy is sent in the Request URI.</span></span>|
| <span data-ttu-id="c6253-342">X-MS-UserLocation: внешняя</span><span class="sxs-lookup"><span data-stu-id="c6253-342">X-MS-UserLocation: external</span></span> | <span data-ttu-id="c6253-343">В поле указано, что пользователь находится за пределами корпоративной сети.</span><span class="sxs-lookup"><span data-stu-id="c6253-343">The field indicated that user is located outside the corporate network.</span></span> |
| <span data-ttu-id="c6253-344">X-MS-MediaPath: proxysbc.contoso.com, VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c6253-344">X-MS-MediaPath: proxysbc.contoso.com, VNsbc.contoso.com</span></span>    | <span data-ttu-id="c6253-345">Указывает, какой SBC должен проходить через клиент до целевого SBC.</span><span class="sxs-lookup"><span data-stu-id="c6253-345">Specifies which SBC the client must traverse to the target SBC.</span></span> <span data-ttu-id="c6253-346">В этом случае мы всегда обходить, и клиент является внешним.</span><span class="sxs-lookup"><span data-stu-id="c6253-346">In this case as we have Always Bypass, and the client is external.</span></span> |

#### <a name="inbound-calls-and-the-user-is-external-with-always-bypass"></a><span data-ttu-id="c6253-347">Входящие звонки и внешний пользователь с помощью always Bypass</span><span class="sxs-lookup"><span data-stu-id="c6253-347">Inbound calls and the user is external with Always Bypass</span></span>

| <span data-ttu-id="c6253-348">Режим</span><span class="sxs-lookup"><span data-stu-id="c6253-348">Mode</span></span> | <span data-ttu-id="c6253-349">Пользователь</span><span class="sxs-lookup"><span data-stu-id="c6253-349">User</span></span> | <span data-ttu-id="c6253-350">Сайт</span><span class="sxs-lookup"><span data-stu-id="c6253-350">Site</span></span> |  <span data-ttu-id="c6253-351">Направление звонка</span><span class="sxs-lookup"><span data-stu-id="c6253-351">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
<span data-ttu-id="c6253-352">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="c6253-352">AlwaysBypass</span></span> |  <span data-ttu-id="c6253-353">Внешняя</span><span class="sxs-lookup"><span data-stu-id="c6253-353">External</span></span> |  <span data-ttu-id="c6253-354">Н/Д</span><span class="sxs-lookup"><span data-stu-id="c6253-354">N/A</span></span> |   <span data-ttu-id="c6253-355">Входящий</span><span class="sxs-lookup"><span data-stu-id="c6253-355">Inbound</span></span> |

<span data-ttu-id="c6253-356">Для входящий звонок SBC, подключенный к прямой маршрутике, должен отправить повторное приглашение (по умолчанию локальные соискатель всегда предлагаются), если расположение пользователя является внешним.</span><span class="sxs-lookup"><span data-stu-id="c6253-356">For an inbound call, the SBC connected to Direct Routing needs to send a re-invite (by default, local media candidates are always offered) if the location of the user is external.</span></span>  <span data-ttu-id="c6253-357">X-MediaPath вычисляется на основе Record-Route и указанного пользователя SBC.</span><span class="sxs-lookup"><span data-stu-id="c6253-357">The X-MediaPath is calculated based on Record-Route and the SBC user specified.</span></span>

<span data-ttu-id="c6253-358">На следующей схеме показана схема SIP для входящий вызовов в режиме AlwaysBypass, и пользователь является внешним.</span><span class="sxs-lookup"><span data-stu-id="c6253-358">The following diagram shows the SIP ladder for an inbound call with AlwaysBypass mode, and the user is external.</span></span>

![Схема, показывающая SIP-диаграмму](media/direct-routing-media-op-13.png)


### <a name="only-for-local-users-mode"></a><span data-ttu-id="c6253-360">Только для локальных пользователей</span><span class="sxs-lookup"><span data-stu-id="c6253-360">Only for local users mode</span></span>

<span data-ttu-id="c6253-361">Local media candidates of the target SBC will be offered only if a user is in the same location as the SBC.</span><span class="sxs-lookup"><span data-stu-id="c6253-361">Local media candidates of the target SBC will be offered only if a user is in the same location as the SBC.</span></span> <span data-ttu-id="c6253-362">Во всех остальных случаях мультимедиа проходят через внутренний или внешний IP-адрес прокси-сервера SBC.</span><span class="sxs-lookup"><span data-stu-id="c6253-362">In all other cases, media will flow through either an internal or external IP of the proxy SBC.</span></span>

<span data-ttu-id="c6253-363">Описаны следующие сценарии:</span><span class="sxs-lookup"><span data-stu-id="c6253-363">The following scenarios are described:</span></span>

- [<span data-ttu-id="c6253-364">Исходящие звонки, и пользователь находится в том же расположении, что и SBC</span><span class="sxs-lookup"><span data-stu-id="c6253-364">Outbound calls and the user is in the same location as the SBC</span></span>](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [<span data-ttu-id="c6253-365">Входящие звонки и пользователь находится в том же расположении, что и SBC</span><span class="sxs-lookup"><span data-stu-id="c6253-365">Inbound calls and the user is in the same location as the SBC</span></span>](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [<span data-ttu-id="c6253-366">Пользователь находится не в том же расположении, что и SBC, но находится в корпоративной сети</span><span class="sxs-lookup"><span data-stu-id="c6253-366">User is not at the same location as the SBC but is in the corporate network</span></span>](#user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users)
- [<span data-ttu-id="c6253-367">Входящие звонки и пользователь является внутренним, но находится в разных местах, что и SBC</span><span class="sxs-lookup"><span data-stu-id="c6253-367">Inbound calls and the user is internal but is not at the same location as the SBC</span></span>](#inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users)

<span data-ttu-id="c6253-368">В следующей таблице показаны конфигурация и действие для конечных пользователей.</span><span class="sxs-lookup"><span data-stu-id="c6253-368">The following table shows end user configuration and action:</span></span>

| <span data-ttu-id="c6253-369">Физическое местонахождение пользователя</span><span class="sxs-lookup"><span data-stu-id="c6253-369">User physical location</span></span> |  <span data-ttu-id="c6253-370">Пользователь звонит на номер или принимает его</span><span class="sxs-lookup"><span data-stu-id="c6253-370">User makes or receives a call to/from number</span></span> |  <span data-ttu-id="c6253-371">Номер телефона пользователя</span><span class="sxs-lookup"><span data-stu-id="c6253-371">User phone number</span></span> | <span data-ttu-id="c6253-372">Политика маршрутинга голосовой почты в Интернете</span><span class="sxs-lookup"><span data-stu-id="c6253-372">Online Voice Routing Policy</span></span> |   <span data-ttu-id="c6253-373">Режим, настроенный для SBC</span><span class="sxs-lookup"><span data-stu-id="c6253-373">Mode configured for SBC</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="c6253-374">Вьетнам</span><span class="sxs-lookup"><span data-stu-id="c6253-374">Vietnam</span></span> | <span data-ttu-id="c6253-375">+84 4 3926 3000</span><span class="sxs-lookup"><span data-stu-id="c6253-375">+84 4 3926  3000</span></span> |  <span data-ttu-id="c6253-376">+84 4 5555 5555</span><span class="sxs-lookup"><span data-stu-id="c6253-376">+84 4 5555 5555</span></span> | <span data-ttu-id="c6253-377">Приоритет 1: ^ \+ 84(\d {9} )$ -VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c6253-377">Priority 1: ^\+84(\d{9})$ -VNsbc.contoso.com</span></span> <br> <span data-ttu-id="c6253-378">Приоритет 2: .\* — proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c6253-378">Priority 2: .\* - proxysbc.contoso.com</span></span> | <span data-ttu-id="c6253-379">VNsbc.contoso.com – OnlyForLocalUsers Proxysbc.contoso.com – Always Bypass</span><span class="sxs-lookup"><span data-stu-id="c6253-379">VNsbc.contoso.com – OnlyForLocalUsers Proxysbc.contoso.com – Always Bypass</span></span> |

#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="c6253-380">Исходящие звонки, а пользователь находится в том же расположении, что и SBC, только для локальных пользователей</span><span class="sxs-lookup"><span data-stu-id="c6253-380">Outbound calls and the user is in the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="c6253-381">Режим</span><span class="sxs-lookup"><span data-stu-id="c6253-381">Mode</span></span> | <span data-ttu-id="c6253-382">Пользователь</span><span class="sxs-lookup"><span data-stu-id="c6253-382">User</span></span> | <span data-ttu-id="c6253-383">Сайт</span><span class="sxs-lookup"><span data-stu-id="c6253-383">Site</span></span> | <span data-ttu-id="c6253-384">Направление звонка</span><span class="sxs-lookup"><span data-stu-id="c6253-384">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="c6253-385">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="c6253-385">OnlyForLocalUsers</span></span> |   <span data-ttu-id="c6253-386">Internal</span><span class="sxs-lookup"><span data-stu-id="c6253-386">Internal</span></span> |<span data-ttu-id="c6253-387">То же, что и SBC</span><span class="sxs-lookup"><span data-stu-id="c6253-387">Same as SBC</span></span>   | <span data-ttu-id="c6253-388">Исходящее</span><span class="sxs-lookup"><span data-stu-id="c6253-388">Outbound</span></span> |

<span data-ttu-id="c6253-389">На следующей схеме показан исходящие вызовы в режиме OnlyForLocalUsers, и пользователь находится в том же расположении, что и SBC.</span><span class="sxs-lookup"><span data-stu-id="c6253-389">The following diagram shows an outbound call with OnlyForLocalUsers mode, and the user is in the same location as the SBC.</span></span> <span data-ttu-id="c6253-390">Такой же поток отображается при исходящие звонки, когда пользователь находится в том же расположении, что [и SBC.](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)</span><span class="sxs-lookup"><span data-stu-id="c6253-390">This is the same flow shown in [Outbound calls when the user is in the same location as the SBC](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span></span>

![Схема, показывающая SIP-диаграмму](media/direct-routing-media-op-14.png)


#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="c6253-392">Входящие звонки, и пользователь находится в том же расположении, что и SBC, и только для локальных пользователей</span><span class="sxs-lookup"><span data-stu-id="c6253-392">Inbound calls and the user is in the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="c6253-393">Режим</span><span class="sxs-lookup"><span data-stu-id="c6253-393">Mode</span></span> | <span data-ttu-id="c6253-394">Пользователь</span><span class="sxs-lookup"><span data-stu-id="c6253-394">User</span></span> | <span data-ttu-id="c6253-395">Сайт</span><span class="sxs-lookup"><span data-stu-id="c6253-395">Site</span></span> | <span data-ttu-id="c6253-396">Направление звонка</span><span class="sxs-lookup"><span data-stu-id="c6253-396">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="c6253-397">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="c6253-397">OnlyForLocalUsers</span></span> |   <span data-ttu-id="c6253-398">Internal</span><span class="sxs-lookup"><span data-stu-id="c6253-398">Internal</span></span> | <span data-ttu-id="c6253-399">То же, что и SBC</span><span class="sxs-lookup"><span data-stu-id="c6253-399">Same as SBC</span></span> | <span data-ttu-id="c6253-400">Входящий</span><span class="sxs-lookup"><span data-stu-id="c6253-400">Inbound</span></span> |

<span data-ttu-id="c6253-401">На следующей схеме показан входящий звонок в режиме OnlyForLocalUsers, и пользователь находится в том же расположении, что и SBC.</span><span class="sxs-lookup"><span data-stu-id="c6253-401">The following diagram shows an inbound call with OnlyForLocalUsers mode, and the user is in the same location as the SBC.</span></span> <span data-ttu-id="c6253-402">Этот поток такой же, как и при входящие звонки, если пользователь находится в том же расположении, что [и SBC.](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)</span><span class="sxs-lookup"><span data-stu-id="c6253-402">This is the same flow as shown in [Inbound calls when the user is in the same location as the SBC](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span></span>

![Схема, показывающая SIP-диаграмму](media/direct-routing-media-op-15.png)


#### <a name="user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users"></a><span data-ttu-id="c6253-404">Пользователь находится не в том же расположении, что и SBC, но находится в корпоративной сети только для локальных пользователей</span><span class="sxs-lookup"><span data-stu-id="c6253-404">User is not at the same location as the SBC but is in the corporate network with Only for local users</span></span>

| <span data-ttu-id="c6253-405">Режим</span><span class="sxs-lookup"><span data-stu-id="c6253-405">Mode</span></span> | <span data-ttu-id="c6253-406">Пользователь</span><span class="sxs-lookup"><span data-stu-id="c6253-406">User</span></span> | <span data-ttu-id="c6253-407">Сайт</span><span class="sxs-lookup"><span data-stu-id="c6253-407">Site</span></span> |<span data-ttu-id="c6253-408">Направление звонка</span><span class="sxs-lookup"><span data-stu-id="c6253-408">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="c6253-409">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="c6253-409">OnlyForLocalUsers</span></span>  | <span data-ttu-id="c6253-410">Internal</span><span class="sxs-lookup"><span data-stu-id="c6253-410">Internal</span></span> |   <span data-ttu-id="c6253-411">Отличается от SBC</span><span class="sxs-lookup"><span data-stu-id="c6253-411">Different from SBC</span></span> | <span data-ttu-id="c6253-412">Исходящее</span><span class="sxs-lookup"><span data-stu-id="c6253-412">Outbound</span></span> |

<span data-ttu-id="c6253-413">Прямая маршрутия вычисляет X-MediaPath на основе данных о расположении пользователя и режиме, настроенных на SBC.</span><span class="sxs-lookup"><span data-stu-id="c6253-413">Direct routing calculates X-MediaPath based on the reported location of the user and mode configured on the SBC.</span></span>


<span data-ttu-id="c6253-414">На следующей схеме показан исходящие вызовы в режиме OnlyForLocalUsers и внутренний пользователь, который находится не в том же расположении, что и SBC.</span><span class="sxs-lookup"><span data-stu-id="c6253-414">The following diagram shows an outbound call with OnlyForLocalUsers mode, and an internal user who is not at the same location as the SBC.</span></span>

![Схема, показывающая SIP-диаграмму](media/direct-routing-media-op-16.png)


#### <a name="inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="c6253-416">Входящий звонок и пользователь является внутренним, но находится в разных местах с SBC только для локальных пользователей</span><span class="sxs-lookup"><span data-stu-id="c6253-416">Inbound call and the user is internal but is not at the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="c6253-417">Режим</span><span class="sxs-lookup"><span data-stu-id="c6253-417">Mode</span></span> |    <span data-ttu-id="c6253-418">Пользователь</span><span class="sxs-lookup"><span data-stu-id="c6253-418">User</span></span> |  <span data-ttu-id="c6253-419">Сайт</span><span class="sxs-lookup"><span data-stu-id="c6253-419">Site</span></span> |  <span data-ttu-id="c6253-420">Направление звонка</span><span class="sxs-lookup"><span data-stu-id="c6253-420">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="c6253-421">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="c6253-421">OnlyForLocalUsers</span></span> | <span data-ttu-id="c6253-422">Internal</span><span class="sxs-lookup"><span data-stu-id="c6253-422">Internal</span></span> |    <span data-ttu-id="c6253-423">Отличается от SBC</span><span class="sxs-lookup"><span data-stu-id="c6253-423">Different from SBC</span></span> |    <span data-ttu-id="c6253-424">Входящий</span><span class="sxs-lookup"><span data-stu-id="c6253-424">Inbound</span></span> |

<span data-ttu-id="c6253-425">На следующей схеме показан входящий звонок с режимом OnlyForLocalUsers и внутренним пользователем, который находится не в том же расположении, что и SBC.</span><span class="sxs-lookup"><span data-stu-id="c6253-425">The following diagram shows an inbound call with OnlyForLocalUsers mode, and an internal user who is not at the same location as the SBC.</span></span>

![Схема, показывающая SIP-диаграмму](media/direct-routing-media-op-17.png)









