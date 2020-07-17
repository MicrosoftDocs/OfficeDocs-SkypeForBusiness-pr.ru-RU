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
ms.openlocfilehash: e53f9156b6ab6d33223c9b1d3e11a604ba0c1c31
ms.sourcegitcommit: 113e3a7314505cf78da57917ff62642125fb11fd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/14/2020
ms.locfileid: "45121609"
---
# <a name="configure-local-media-optimization-for-direct-routing"></a><span data-ttu-id="c6bd7-103">Настройка оптимизации локальных файлов мультимедиа для прямой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="c6bd7-103">Configure Local Media Optimization for Direct Routing</span></span>

<span data-ttu-id="c6bd7-104">Настройка оптимизации локальных файлов мультимедиа основывается на параметрах сети, которые являются общими для других функций голосовой связи в облаке, таких как маршрутизация на основе местоположения и динамический вызов экстренной помощи.</span><span class="sxs-lookup"><span data-stu-id="c6bd7-104">Configuration for Local Media Optimization is based on network settings that are common to other cloud voice features, such as Location-Based Routing and dynamic emergency calling.</span></span> <span data-ttu-id="c6bd7-105">Чтобы узнать больше о регионах сети, сетевых сайтах, подсетях сети и о доверенных IP-адресах, просмотрите [Параметры сети для функций голосовой связи в облаке](cloud-voice-network-settings.md).</span><span class="sxs-lookup"><span data-stu-id="c6bd7-105">To learn more about network regions, network sites, network subnets, and trusted IP addresses, see [Network settings for cloud voice features](cloud-voice-network-settings.md).</span></span>

<span data-ttu-id="c6bd7-106">Перед настройкой оптимизации локального мультимедиа ознакомьтесь со сведениями [об оптимизации локальных файлов для прямой маршрутизации](direct-routing-media-optimization.md).</span><span class="sxs-lookup"><span data-stu-id="c6bd7-106">Before you configure Local Media Optimization, see [Local media Optimization for Direct Routing](direct-routing-media-optimization.md).</span></span>  

<span data-ttu-id="c6bd7-107">Для настройки оптимизации локального мультимедиа необходимо выполнить указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="c6bd7-107">To configure Local Media Optimization, the following steps are required.</span></span> <span data-ttu-id="c6bd7-108">Вы можете использовать центр администрирования Teams или PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c6bd7-108">You can use the Teams Admin Center or PowerShell.</span></span> <span data-ttu-id="c6bd7-109">Подробности можно найти в разделе [Управление топологией сети](manage-your-network-topology.md).</span><span class="sxs-lookup"><span data-stu-id="c6bd7-109">For details, see [Manage your network topology](manage-your-network-topology.md).</span></span>

1. <span data-ttu-id="c6bd7-110">Настройте пользователя и сайты SBC (как описано в этой статье).</span><span class="sxs-lookup"><span data-stu-id="c6bd7-110">Configure the user and the SBC sites (as described in this article).</span></span>
2. <span data-ttu-id="c6bd7-111">Настройте локальную SBCs для оптимизации локальных файлов (в соответствии со спецификацией поставщика SBC).</span><span class="sxs-lookup"><span data-stu-id="c6bd7-111">Configure the SBCs for Local Media Optimization (according to your SBC vendor specification).</span></span>

<span data-ttu-id="c6bd7-112">На приведенной ниже схеме показана настройка сети, используемая в примерах в этой статье.</span><span class="sxs-lookup"><span data-stu-id="c6bd7-112">The following diagram shows the network setup used in the examples throughout this article.</span></span>

<span data-ttu-id="c6bd7-113">![Пример схемы, показывающей параметры сети](media/direct-routing-media-op-9.png "Примеры настройки сети")</span><span class="sxs-lookup"><span data-stu-id="c6bd7-113">![Diagram showing network setup for examples](media/direct-routing-media-op-9.png "Network setup for examples")</span></span>


## <a name="configure-the-user-and-the-sbc-sites"></a><span data-ttu-id="c6bd7-114">Настройка пользователей и сайтов SBC</span><span class="sxs-lookup"><span data-stu-id="c6bd7-114">Configure the user and the SBC sites</span></span>

<span data-ttu-id="c6bd7-115">Чтобы настроить пользователя и сайты SBC, необходимо выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="c6bd7-115">To configure the user and the SBC sites, you will need to:</span></span>

1. <span data-ttu-id="c6bd7-116">[Управление внешними доверенными IP-адресами](#manage-external-trusted-ip-addresses).</span><span class="sxs-lookup"><span data-stu-id="c6bd7-116">[Manage external trusted IP addresses](#manage-external-trusted-ip-addresses).</span></span>  

2. <span data-ttu-id="c6bd7-117">[Определите топологию сети](#define-the-network-topology) , настроив регионы сети, сетевые сайты и сетевые подсети.</span><span class="sxs-lookup"><span data-stu-id="c6bd7-117">[Define the network topology](#define-the-network-topology) by configuring the network regions, network sites, and network subnets.</span></span>

3. <span data-ttu-id="c6bd7-118">[Определите топологию виртуальной сети](#define-the-virtual-network-topology) путем назначения SBC (-ов) на сайты, используя необходимые режимы и значения SBC-прокси.</span><span class="sxs-lookup"><span data-stu-id="c6bd7-118">[Define the virtual network topology](#define-the-virtual-network-topology) by assigning SBC(s) to site(s) with relevant modes and proxy SBC values.</span></span>


## <a name="configure-sbcs-for-local-media-optimization-according-to-the-sbc-vendor-specification"></a><span data-ttu-id="c6bd7-119">Настройка SBC (s) для оптимизации локальных файлов мультимедиа в соответствии со спецификацией поставщика SBC</span><span class="sxs-lookup"><span data-stu-id="c6bd7-119">Configure SBC(s) for Local Media Optimization according to the SBC vendor specification</span></span>

<span data-ttu-id="c6bd7-120">В этой статье описано, как настроить компоненты Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c6bd7-120">This article describes configuration for Microsoft components.</span></span> <span data-ttu-id="c6bd7-121">Сведения о настройке SBC можно найти в документации поставщика SBC.</span><span class="sxs-lookup"><span data-stu-id="c6bd7-121">For information on SBC configuration, see your SBC vendor documentation.</span></span>

<span data-ttu-id="c6bd7-122">Локальная Оптимизация файлов мультимедиа поддерживается следующими разработчиками SBC:</span><span class="sxs-lookup"><span data-stu-id="c6bd7-122">Local Media Optimization is supported by the following SBC vendors:</span></span>

| <span data-ttu-id="c6bd7-123">Поставщик</span><span class="sxs-lookup"><span data-stu-id="c6bd7-123">Vendor</span></span> | <span data-ttu-id="c6bd7-124">ПРОИЗВЕД</span><span class="sxs-lookup"><span data-stu-id="c6bd7-124">Product</span></span> |    <span data-ttu-id="c6bd7-125">Версия программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="c6bd7-125">Software version</span></span> |
|:------------|:-------|:-------| :-------|
| [<span data-ttu-id="c6bd7-126">Audiocodes</span><span class="sxs-lookup"><span data-stu-id="c6bd7-126">Audiocodes</span></span>](https://www.audiocodes.com/media/13253/connecting-audiocodes-sbc-to-microsoft-teams-direct-routing-enterprise-model-configuration-note.pdf) |    <span data-ttu-id="c6bd7-127">Mediant 500 SBC</span><span class="sxs-lookup"><span data-stu-id="c6bd7-127">Mediant 500 SBC</span></span> |   <span data-ttu-id="c6bd7-128">7.20 а. 256</span><span class="sxs-lookup"><span data-stu-id="c6bd7-128">7.20A.256</span></span> | 
|            |  <span data-ttu-id="c6bd7-129">Mediant 800 SBC</span><span class="sxs-lookup"><span data-stu-id="c6bd7-129">Mediant 800 SBC</span></span> |   <span data-ttu-id="c6bd7-130">7.20 а. 256</span><span class="sxs-lookup"><span data-stu-id="c6bd7-130">7.20A.256</span></span> | 
|            |  <span data-ttu-id="c6bd7-131">Mediant 2600 SBC</span><span class="sxs-lookup"><span data-stu-id="c6bd7-131">Mediant 2600 SBC</span></span> |  <span data-ttu-id="c6bd7-132">7.20 а. 256</span><span class="sxs-lookup"><span data-stu-id="c6bd7-132">7.20A.256</span></span> | 
|            |  <span data-ttu-id="c6bd7-133">Mediant 4000 SBC</span><span class="sxs-lookup"><span data-stu-id="c6bd7-133">Mediant 4000 SBC</span></span> |  <span data-ttu-id="c6bd7-134">7.20 а. 256</span><span class="sxs-lookup"><span data-stu-id="c6bd7-134">7.20A.256</span></span> | 
|            |  <span data-ttu-id="c6bd7-135">Функция МЕДИАНА 1000Bого SBC</span><span class="sxs-lookup"><span data-stu-id="c6bd7-135">Mediant 1000B SBC</span></span> | <span data-ttu-id="c6bd7-136">7.20 а. 256</span><span class="sxs-lookup"><span data-stu-id="c6bd7-136">7.20A.256</span></span> | 
|            |  <span data-ttu-id="c6bd7-137">Одномедианый SBC 9000</span><span class="sxs-lookup"><span data-stu-id="c6bd7-137">Mediant 9000 SBC</span></span> |  <span data-ttu-id="c6bd7-138">7.20 а. 256</span><span class="sxs-lookup"><span data-stu-id="c6bd7-138">7.20A.256</span></span> | 
|            |  <span data-ttu-id="c6bd7-139">Односрединный виртуальный SBC</span><span class="sxs-lookup"><span data-stu-id="c6bd7-139">Mediant Virtual Edition SBC</span></span> |   <span data-ttu-id="c6bd7-140">7.20 а. 256</span><span class="sxs-lookup"><span data-stu-id="c6bd7-140">7.20A.256</span></span> | 
|            |  <span data-ttu-id="c6bd7-141">SBC по выпуску "Медиана"</span><span class="sxs-lookup"><span data-stu-id="c6bd7-141">Mediant Cloud Edition SBC</span></span> | <span data-ttu-id="c6bd7-142">7.20 а. 256</span><span class="sxs-lookup"><span data-stu-id="c6bd7-142">7.20A.256</span></span> |
| [<span data-ttu-id="c6bd7-143">Базовые компоненты SBC для ленты</span><span class="sxs-lookup"><span data-stu-id="c6bd7-143">Ribbon SBC Core</span></span>](https://support.sonus.net/display/ALLDOC/SBC+8.2+-+Configure+Local+Media+Optimization)  |  <span data-ttu-id="c6bd7-144">SBC 5110</span><span class="sxs-lookup"><span data-stu-id="c6bd7-144">SBC 5110</span></span>         | <span data-ttu-id="c6bd7-145">8,2</span><span class="sxs-lookup"><span data-stu-id="c6bd7-145">8.2</span></span>  |
|            |  <span data-ttu-id="c6bd7-146">SBC 5210</span><span class="sxs-lookup"><span data-stu-id="c6bd7-146">SBC 5210</span></span>         | <span data-ttu-id="c6bd7-147">8,2</span><span class="sxs-lookup"><span data-stu-id="c6bd7-147">8.2</span></span>  |
|            |  <span data-ttu-id="c6bd7-148">SBC 5400</span><span class="sxs-lookup"><span data-stu-id="c6bd7-148">SBC 5400</span></span>         | <span data-ttu-id="c6bd7-149">8,2</span><span class="sxs-lookup"><span data-stu-id="c6bd7-149">8.2</span></span>  |
|            |  <span data-ttu-id="c6bd7-150">SBC 7000</span><span class="sxs-lookup"><span data-stu-id="c6bd7-150">SBC 7000</span></span>         | <span data-ttu-id="c6bd7-151">8,2</span><span class="sxs-lookup"><span data-stu-id="c6bd7-151">8.2</span></span>  |
|            |  <span data-ttu-id="c6bd7-152">SBC SWe</span><span class="sxs-lookup"><span data-stu-id="c6bd7-152">SBC SWe</span></span>          | <span data-ttu-id="c6bd7-153">8,2</span><span class="sxs-lookup"><span data-stu-id="c6bd7-153">8.2</span></span>  |
| [<span data-ttu-id="c6bd7-154">Ребро для SBC ленты</span><span class="sxs-lookup"><span data-stu-id="c6bd7-154">Ribbon SBC Edge</span></span>](https://support.sonus.net/display/UXDOC81/Best+Practice+-+Configuring+Microsoft+Teams+Local+Media+Optimization)  |  <span data-ttu-id="c6bd7-155">SBC SWe Lite</span><span class="sxs-lookup"><span data-stu-id="c6bd7-155">SBC SWe Lite</span></span> | <span data-ttu-id="c6bd7-156">8.1.5 (сборка 239)</span><span class="sxs-lookup"><span data-stu-id="c6bd7-156">8.1.5 (build 239)</span></span> |
| [<span data-ttu-id="c6bd7-157">TE-SYSTEMS</span><span class="sxs-lookup"><span data-stu-id="c6bd7-157">TE-SYSTEMS</span></span>](https://www.anynode.de/local_media_optimization/) |  <span data-ttu-id="c6bd7-158">anynode</span><span class="sxs-lookup"><span data-stu-id="c6bd7-158">anynode</span></span>          | <span data-ttu-id="c6bd7-159">4.0.1 +</span><span class="sxs-lookup"><span data-stu-id="c6bd7-159">4.0.1+</span></span> |
| [<span data-ttu-id="c6bd7-160">Oracle</span><span class="sxs-lookup"><span data-stu-id="c6bd7-160">Oracle</span></span>](https://www.oracle.com/industries/communications/enterprise-communications/session-border-controller/microsoft.html) | <span data-ttu-id="c6bd7-161">AP 1100</span><span class="sxs-lookup"><span data-stu-id="c6bd7-161">AP 1100</span></span> | <span data-ttu-id="c6bd7-162">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="c6bd7-162">8.4.0.0.0</span></span> |
|        | <span data-ttu-id="c6bd7-163">AP 3900</span><span class="sxs-lookup"><span data-stu-id="c6bd7-163">AP 3900</span></span> | <span data-ttu-id="c6bd7-164">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="c6bd7-164">8.4.0.0.0</span></span> |
|        | <span data-ttu-id="c6bd7-165">AP 4600</span><span class="sxs-lookup"><span data-stu-id="c6bd7-165">AP 4600</span></span> | <span data-ttu-id="c6bd7-166">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="c6bd7-166">8.4.0.0.0</span></span> | 
|        | <span data-ttu-id="c6bd7-167">AP 6300</span><span class="sxs-lookup"><span data-stu-id="c6bd7-167">AP 6300</span></span> | <span data-ttu-id="c6bd7-168">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="c6bd7-168">8.4.0.0.0</span></span> |
|        | <span data-ttu-id="c6bd7-169">AP 6350</span><span class="sxs-lookup"><span data-stu-id="c6bd7-169">AP 6350</span></span> | <span data-ttu-id="c6bd7-170">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="c6bd7-170">8.4.0.0.0</span></span> | 
|        | <span data-ttu-id="c6bd7-171">VME</span><span class="sxs-lookup"><span data-stu-id="c6bd7-171">VME</span></span>     | <span data-ttu-id="c6bd7-172">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="c6bd7-172">8.4.0.0.0</span></span> |


## <a name="manage-external-trusted-ip-addresses"></a><span data-ttu-id="c6bd7-173">Управление внешними надежными IP-адресами</span><span class="sxs-lookup"><span data-stu-id="c6bd7-173">Manage external trusted IP addresses</span></span>

<span data-ttu-id="c6bd7-174">Внешние надежные IP-адреса — это внешние IP-адреса Интернет-адресов корпоративной сети.</span><span class="sxs-lookup"><span data-stu-id="c6bd7-174">External trusted IPs are the Internet external IPs of the enterprise network.</span></span> <span data-ttu-id="c6bd7-175">Эти IP-адреса используются клиентами Microsoft Teams при подключении к Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c6bd7-175">These IP’s are the IP addresses used by Microsoft Teams clients when they connect to Microsoft 365.</span></span> <span data-ttu-id="c6bd7-176">Вам необходимо добавить эти внешние IP-адреса для каждого сайта, на котором пользователи используют локальную оптимизацию мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="c6bd7-176">You need to add these external IPs for each site where you have users using Local Media Optimization.</span></span>

<span data-ttu-id="c6bd7-177">Чтобы добавить общедоступные IP-адреса для каждого сайта, используйте командлет New-CsTenantTrustedIPAddress.</span><span class="sxs-lookup"><span data-stu-id="c6bd7-177">To add the public IP addresses for each site, use the New-CsTenantTrustedIPAddress cmdlet.</span></span> <span data-ttu-id="c6bd7-178">Вы можете определить неограниченное количество доверенных IP-адресов для клиента.</span><span class="sxs-lookup"><span data-stu-id="c6bd7-178">You can define an unlimited number of trusted IP addresses for a tenant.</span></span> <span data-ttu-id="c6bd7-179">Если внешние IP-адреса, обнаруженные Microsoft 365, являются адресами IPv4 и IPv6, необходимо добавить оба типа IP.</span><span class="sxs-lookup"><span data-stu-id="c6bd7-179">If the external IPs seen by Microsoft 365 are both IPv4 and IPv6 addresses, you need to add both types of IP addresses.</span></span> <span data-ttu-id="c6bd7-180">Для IPv4 используется маска 32.</span><span class="sxs-lookup"><span data-stu-id="c6bd7-180">For IPv4, use mask 32.</span></span> <span data-ttu-id="c6bd7-181">Для IPv6 используйте маску 128.</span><span class="sxs-lookup"><span data-stu-id="c6bd7-181">For IPv6, use mask 128.</span></span> <span data-ttu-id="c6bd7-182">Вы можете добавить как отдельные внешние IP-адреса, так и внешние IP-подсети, указав разные MaskBits в командлете.</span><span class="sxs-lookup"><span data-stu-id="c6bd7-182">You can add both individual external IP addresses and external IP subnets by specifying different MaskBits on the cmdlet.</span></span>

```
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description>
```


<span data-ttu-id="c6bd7-183">Пример добавления доверенных IP-адресов.</span><span class="sxs-lookup"><span data-stu-id="c6bd7-183">Example of adding trusted IP addresses.</span></span>

```
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.110 -MaskBits 32 -Description "Vietnam site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.120 -MaskBits 32 -Description "Indonesia site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.130 -MaskBits 32 -Description "Singapore site trusted IP"
```


## <a name="define-the-network-topology"></a><span data-ttu-id="c6bd7-184">Определение топологии сети</span><span class="sxs-lookup"><span data-stu-id="c6bd7-184">Define the network topology</span></span>

<span data-ttu-id="c6bd7-185">В этом разделе рассказывается, как определить регионы сети, сетевые сайты и сетевые подсети для топологии сети.</span><span class="sxs-lookup"><span data-stu-id="c6bd7-185">This section describes how to define the network regions, network sites, and network subnets for your network topology.</span></span>

<span data-ttu-id="c6bd7-186">Все параметры чувствительны к регистру, поэтому необходимо использовать тот же сценарий, который использовался при настройке.</span><span class="sxs-lookup"><span data-stu-id="c6bd7-186">All parameters are case sensitive so you need to ensure that you use the same case that was used during setup.</span></span>  <span data-ttu-id="c6bd7-187">(Например, GatewaySiteID значения "Вьетнам" и "Вьетнам" будут считаться разными сайтами.)</span><span class="sxs-lookup"><span data-stu-id="c6bd7-187">(For example, GatewaySiteID values “Vietnam” and “vietnam” will be treated as different sites.)</span></span>

### <a name="define-network-regions"></a><span data-ttu-id="c6bd7-188">Определение регионов сети</span><span class="sxs-lookup"><span data-stu-id="c6bd7-188">Define network regions</span></span>

<span data-ttu-id="c6bd7-189">Чтобы определить регионы сети, используйте командлет New-CsTenantNetworkRegion.</span><span class="sxs-lookup"><span data-stu-id="c6bd7-189">To define network regions, use the New-CsTenantNetworkRegion cmdlet.</span></span> <span data-ttu-id="c6bd7-190">Параметр RegionID — это логическое имя, представляющее собой географию области и не обладающее зависимостями или ограничениями.</span><span class="sxs-lookup"><span data-stu-id="c6bd7-190">The RegionID parameter is a logical name that represents the geography of the region and has no dependencies or restrictions.</span></span> <span data-ttu-id="c6bd7-191">Параметр CentralSite <site ID> является необязательным.</span><span class="sxs-lookup"><span data-stu-id="c6bd7-191">The CentralSite <site ID> parameter is optional.</span></span>

```
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

<span data-ttu-id="c6bd7-192">В следующем примере создается сетевой регион с именем APAC:</span><span class="sxs-lookup"><span data-stu-id="c6bd7-192">The following example creates a network region named APAC:</span></span>

```
New-CsTenantNetworkRegion -NetworkRegionID "APAC"  
```

###  <a name="define-network-sites"></a><span data-ttu-id="c6bd7-193">Определение сетевых сайтов</span><span class="sxs-lookup"><span data-stu-id="c6bd7-193">Define network sites</span></span>

<span data-ttu-id="c6bd7-194">Для определения сетевых сайтов используйте командлет New-CsTenantNetworkSite.</span><span class="sxs-lookup"><span data-stu-id="c6bd7-194">To define network sites, use the New-CsTenantNetworkSite cmdlet.</span></span> <span data-ttu-id="c6bd7-195">Каждый сетевой сайт должен быть связан с сетевым регионом.</span><span class="sxs-lookup"><span data-stu-id="c6bd7-195">Each network site must be associated with a network region.</span></span>

```
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```

<span data-ttu-id="c6bd7-196">В следующем примере показано создание трех новых сайтов сети, Вьетнам, Индонезия и Сингапур в регионе APAC:</span><span class="sxs-lookup"><span data-stu-id="c6bd7-196">The following example creates three new network sites, Vietnam, Indonesia, and Singapore in the APAC region:</span></span>

```
New-CsTenantNetworkSite -NetworkSiteID "Vietnam" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Indonesia" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Singapore" -NetworkRegionID "APAC"
```

### <a name="define-network-subnets"></a><span data-ttu-id="c6bd7-197">Определение подсетей сети</span><span class="sxs-lookup"><span data-stu-id="c6bd7-197">Define network subnets</span></span>

<span data-ttu-id="c6bd7-198">Чтобы определить сетевые подсети и связать их с сетевыми сайтами, используйте командлет New-CsTenantNetworkSubnet.</span><span class="sxs-lookup"><span data-stu-id="c6bd7-198">To define network subnets and associate them to network sites, use the New-CsTenantNetworkSubnet cmdlet.</span></span> <span data-ttu-id="c6bd7-199">Каждая сетевая подсеть может быть связана только с одним сайтом.</span><span class="sxs-lookup"><span data-stu-id="c6bd7-199">Each network subnet can only be associated with one site.</span></span> 

```
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>
```

<span data-ttu-id="c6bd7-200">В приведенном ниже примере определяются три подсети, которые связываются с тремя сетевыми сайтами: Вьетнам, Индонезия и Сингапур.</span><span class="sxs-lookup"><span data-stu-id="c6bd7-200">The following example defines three network subnets and associates them with the three network sites:  Vietnam, Indonesia, and Singapore:</span></span>

```
New-CsTenantNetworkSubnet -SubnetID 192.168.1.0 -MaskBits 24 -NetworkSiteID “Vietnam”
New-CsTenantNetworkSubnet -SubnetID 192.168.2.0 -MaskBits 24 -NetworkSiteID “Indonesia”
New-CsTenantNetworkSubnet -SubnetID 192.168.3.0 -MaskBits 24 -NetworkSiteID “Singapore”
```

## <a name="define-the-virtual-network-topology"></a><span data-ttu-id="c6bd7-201">Определение топологии виртуальной сети</span><span class="sxs-lookup"><span data-stu-id="c6bd7-201">Define the virtual network topology</span></span> 

<span data-ttu-id="c6bd7-202">Сначала администратор клиента создает новую конфигурацию SBC для каждого связанного SBC с помощью командлета New-CsOnlinePSTNGateway.</span><span class="sxs-lookup"><span data-stu-id="c6bd7-202">First, the tenant administrator creates a new SBC configuration for each relevant SBC by using the New-CsOnlinePSTNGateway cmdlet.</span></span>
<span data-ttu-id="c6bd7-203">Администратор клиента определяет топологию виртуальной сети, указав сетевые сайты для объектов шлюза PSTN с помощью командлета Set-CsOnlinePSTNGateway:</span><span class="sxs-lookup"><span data-stu-id="c6bd7-203">The tenant administrator defines the virtual network topology by specifying the network sites for the PSTN gateway objects using the Set-CsOnlinePSTNGateway cmdlet:</span></span>

```
PS C:\> Set-CsOnlinePSTNGateway -Identity <Identity> -GatewaySiteID <site ID> -MediaBypass <true/false> -BypassMode <Always/OnlyForLocalUsers> -ProxySBC  <proxy SBC FQDN or $null>
```

<span data-ttu-id="c6bd7-204">Обратите внимание на следующее:</span><span class="sxs-lookup"><span data-stu-id="c6bd7-204">Note the following:</span></span> 
   - <span data-ttu-id="c6bd7-205">Если у клиента есть один объект SBC, параметр-ProxySBC должен быть обязательным как обязательно $null или однорангового значения SBC (то есть центрального SBC с помощью централизованной магистрали).</span><span class="sxs-lookup"><span data-stu-id="c6bd7-205">If the customer has a single SBC, the -ProxySBC parameter must be either mandatory $null or SBC FQDN value (Central SBC with centralized trunks scenario).</span></span>
   - <span data-ttu-id="c6bd7-206">Параметр-MediaBypass должен иметь значение $true, чтобы обеспечить поддержку локальной оптимизации мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="c6bd7-206">The -MediaBypass parameter must be set to $true in order to support Local Media Optimization.</span></span>
   - <span data-ttu-id="c6bd7-207">Если для SBC не задан параметр-BypassMode, заголовки X-MS не будут отправляться.</span><span class="sxs-lookup"><span data-stu-id="c6bd7-207">If the SBC doesn’t have the -BypassMode parameter set, X-MS headers will not be sent.</span></span> 
   - <span data-ttu-id="c6bd7-208">Все параметры чувствительны к регистру, поэтому необходимо использовать тот же вариант, который использовался при настройке.</span><span class="sxs-lookup"><span data-stu-id="c6bd7-208">All parameters are case sensitive so you need to ensure that you use the same case that was used used during setup.</span></span>  <span data-ttu-id="c6bd7-209">(Например, GatewaySiteID значения "Вьетнам" и "Вьетнам" будут считаться разными сайтами.)</span><span class="sxs-lookup"><span data-stu-id="c6bd7-209">(For example, GatewaySiteID values “Vietnam” and “vietnam” will be treated as different sites.)</span></span>

<span data-ttu-id="c6bd7-210">В следующем примере добавляется три SBCs к сетевым сайтам Вьетнам, Индонезия и Сингапур в APAC области с режимом "всегда обходиться".</span><span class="sxs-lookup"><span data-stu-id="c6bd7-210">The following example adds three SBCs to the network sites Vietnam, Indonesia, and Singapore in the APAC region with mode Always bypass:</span></span>

```
Set-CSOnlinePSTNGateway -Identity “proxysbc.contoso.com” -GatewaySiteID “Singapore” -MediaBypass $true -BypassMode “Always” -ProxySBC $null

Set-CSOnlinePSTNGateway -Identity “VNsbc.contoso.com” -GatewaySiteID “Vietnam” -MediaBypass $true -BypassMode “Always” -ProxySBC “proxysbc.contoso.com”

Set-CSOnlinePSTNGateway -Identity “IDsbc.contoso.com” -GatewaySiteID “Indonesia” -MediaBypass $true -BypassMode “Always” -ProxySBC “proxysbc.contoso.com”
```

<span data-ttu-id="c6bd7-211">Примечание. для обеспечения бесперебойной работы при одновременной настройке локальной оптимизации и маршрутизации на основе местоположения (LBR) для LBR необходимо включить более подпадающую одноранговую SBCs, задав для параметра GatewaySiteLbrEnabled значение $true для каждого из этих одноименнох SBC-файлов.</span><span class="sxs-lookup"><span data-stu-id="c6bd7-211">Note: To ensure uninterrupted operations when Local Media Optimization and Location-Based Routing (LBR) are configured at the same time, downstream SBCs must be enabled for LBR by setting the GatewaySiteLbrEnabled parameter to $true for each downstream SBC.</span></span> <span data-ttu-id="c6bd7-212">(Этот параметр не является обязательным для прокси-сервера SBC).</span><span class="sxs-lookup"><span data-stu-id="c6bd7-212">(This setting is not mandatory for the proxy SBC.)</span></span>

<span data-ttu-id="c6bd7-213">В соответствии с приведенными выше сведениями прямая маршрутизация включает три собственных заголовка SIP для приглашений на SIP и повторений, как показано в приведенной ниже таблице.</span><span class="sxs-lookup"><span data-stu-id="c6bd7-213">Based on the information above, Direct Routing will include three proprietary SIP Headers to SIP Invites and Re-invites as shown  in the following table.</span></span>

<span data-ttu-id="c6bd7-214">Заголовки X-MS, введенные в прямом маршруте на приглашениях и повторных приглашениях, если определен BypassMode:</span><span class="sxs-lookup"><span data-stu-id="c6bd7-214">X-MS Headers introduced in Direct Routing on Invites and Re-Invites if BypassMode is defined:</span></span>

| <span data-ttu-id="c6bd7-215">Имя заголовка</span><span class="sxs-lookup"><span data-stu-id="c6bd7-215">Header name</span></span> | <span data-ttu-id="c6bd7-216">Данные</span><span class="sxs-lookup"><span data-stu-id="c6bd7-216">Values</span></span> | <span data-ttu-id="c6bd7-217">Комментарии</span><span class="sxs-lookup"><span data-stu-id="c6bd7-217">Comments</span></span> | 
|:------------|:-------|:-------|
| <span data-ttu-id="c6bd7-218">X-MS-UserLocation</span><span class="sxs-lookup"><span data-stu-id="c6bd7-218">X-MS-UserLocation</span></span> | <span data-ttu-id="c6bd7-219">внутренние и внешние</span><span class="sxs-lookup"><span data-stu-id="c6bd7-219">internal/external</span></span> | <span data-ttu-id="c6bd7-220">Указывает, является ли пользователь внутренним или внешним</span><span class="sxs-lookup"><span data-stu-id="c6bd7-220">Indicates if user is internal or external</span></span> |
| <span data-ttu-id="c6bd7-221">Запрос-URI INVITE SIP: + 84439263000@VNsbc.contoso.com SIP/2,0</span><span class="sxs-lookup"><span data-stu-id="c6bd7-221">Request-URI   INVITE sip: +84439263000@VNsbc.contoso.com SIP /2.0</span></span> | <span data-ttu-id="c6bd7-222">ПОЛНОЕ ДОМЕННОЕ ИМЯ SBC</span><span class="sxs-lookup"><span data-stu-id="c6bd7-222">SBC FQDN</span></span> | <span data-ttu-id="c6bd7-223">Полное доменное имя, которое предназначено для вызова, даже если SBC не подключен напрямую к прямой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="c6bd7-223">The FQDN which is targeted for the call even if the SBC is not directly connected to Direct Routing</span></span> |
| <span data-ttu-id="c6bd7-224">X-MS-MediaPath</span><span class="sxs-lookup"><span data-stu-id="c6bd7-224">X-MS-MediaPath</span></span> | <span data-ttu-id="c6bd7-225">Пример: proxysbc.contoso.com, VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c6bd7-225">Example: proxysbc.contoso.com, VNsbc.contoso.com</span></span> | <span data-ttu-id="c6bd7-226">Порядковый номер SBCs, который должен использоваться для пути к носителю между пользователем и объектом SBC.</span><span class="sxs-lookup"><span data-stu-id="c6bd7-226">Order of SBCs that should be used for Media path between the user and target SBC.</span></span> <span data-ttu-id="c6bd7-227">Конечный SBC всегда в последнюю очередь</span><span class="sxs-lookup"><span data-stu-id="c6bd7-227">The final SBC is always last</span></span> |
| <span data-ttu-id="c6bd7-228">X-MS-UserSite</span><span class="sxs-lookup"><span data-stu-id="c6bd7-228">X-MS-UserSite</span></span> | <span data-ttu-id="c6bd7-229">usersiteID</span><span class="sxs-lookup"><span data-stu-id="c6bd7-229">usersiteID</span></span> | <span data-ttu-id="c6bd7-230">Строка, определенная администратором клиента</span><span class="sxs-lookup"><span data-stu-id="c6bd7-230">String defined by tenant administrator</span></span> |

## <a name="call-flows"></a><span data-ttu-id="c6bd7-231">Потоки звонков</span><span class="sxs-lookup"><span data-stu-id="c6bd7-231">Call flows</span></span> 

<span data-ttu-id="c6bd7-232">Ниже показаны потоки звонков для двух режимов:</span><span class="sxs-lookup"><span data-stu-id="c6bd7-232">The following shows call flows for two modes:</span></span>

- [<span data-ttu-id="c6bd7-233">Всегда обходить</span><span class="sxs-lookup"><span data-stu-id="c6bd7-233">Always Bypass</span></span>](#always-bypass-mode)
- [<span data-ttu-id="c6bd7-234">Только для локальных пользователей</span><span class="sxs-lookup"><span data-stu-id="c6bd7-234">Only for local users</span></span>](#only-for-local-users-mode)

### <a name="always-bypass-mode"></a><span data-ttu-id="c6bd7-235">Режим "всегда пропускать"</span><span class="sxs-lookup"><span data-stu-id="c6bd7-235">Always Bypass mode</span></span>

<span data-ttu-id="c6bd7-236">Режим "всегда пропускать" — это самый простой параметр для настройки.</span><span class="sxs-lookup"><span data-stu-id="c6bd7-236">Always Bypass mode is the simplest option to configure.</span></span> <span data-ttu-id="c6bd7-237">Администратор клиента может настроить один сайт для всех пользователей и SBCs, если все SBCs достижимы с любого сайта.</span><span class="sxs-lookup"><span data-stu-id="c6bd7-237">The tenant administrator can configure a single site for all users and SBCs if all SBCs are reachable from any site.</span></span>

<span data-ttu-id="c6bd7-238">В примерах показан режим "всегда обойти" для следующих сценариев:</span><span class="sxs-lookup"><span data-stu-id="c6bd7-238">The examples show Always bypass mode for the following scenarios:</span></span>

- [<span data-ttu-id="c6bd7-239">Исходящие звонки и пользователь находятся в той же папке, что и SBC</span><span class="sxs-lookup"><span data-stu-id="c6bd7-239">Outbound calls and the user is in the same location as the SBC</span></span>](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [<span data-ttu-id="c6bd7-240">Входящие звонки и пользователь находятся в той же папке, что и SBC</span><span class="sxs-lookup"><span data-stu-id="c6bd7-240">Inbound calls and the user is in the same location as the SBC</span></span>](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [<span data-ttu-id="c6bd7-241">Исходящие звонки и внешние пользователи</span><span class="sxs-lookup"><span data-stu-id="c6bd7-241">Outbound calls and the user is external</span></span>](#outbound-calls-and-the-user-is-external-with-always-bypass)
- [<span data-ttu-id="c6bd7-242">Входящие звонки и внешние пользователи</span><span class="sxs-lookup"><span data-stu-id="c6bd7-242">Inbound calls and the user is external</span></span>](#inbound-calls-and-the-user-is-external-with-always-bypass)

<span data-ttu-id="c6bd7-243">В приведенной ниже таблице указаны полные доменные имена и IP-адреса, используемые в примерах.</span><span class="sxs-lookup"><span data-stu-id="c6bd7-243">The following table shows the FQDN and IP addresses used in the examples:</span></span>

| <span data-ttu-id="c6bd7-244">Полное доменное имя</span><span class="sxs-lookup"><span data-stu-id="c6bd7-244">FQDN</span></span> | <span data-ttu-id="c6bd7-245">Внешний IP-адрес для SBC</span><span class="sxs-lookup"><span data-stu-id="c6bd7-245">SBC external IP address</span></span> | <span data-ttu-id="c6bd7-246">Внутренний IP-адрес SBC</span><span class="sxs-lookup"><span data-stu-id="c6bd7-246">SBC internal IP Address</span></span> | <span data-ttu-id="c6bd7-247">Внутренняя подсеть</span><span class="sxs-lookup"><span data-stu-id="c6bd7-247">Internal subnet</span></span> | <span data-ttu-id="c6bd7-248">Местоположение</span><span class="sxs-lookup"><span data-stu-id="c6bd7-248">Location</span></span> | <span data-ttu-id="c6bd7-249">Внешний NAT (доверенный IP-адрес)</span><span class="sxs-lookup"><span data-stu-id="c6bd7-249">External NAT (Trusted IP)</span></span> |
|:------------|:-------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="c6bd7-250">VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c6bd7-250">VNsbc.contoso.com</span></span> | <span data-ttu-id="c6bd7-251">Нет</span><span class="sxs-lookup"><span data-stu-id="c6bd7-251">None</span></span> | <span data-ttu-id="c6bd7-252">192.168.1.5</span><span class="sxs-lookup"><span data-stu-id="c6bd7-252">192.168.1.5</span></span> | <span data-ttu-id="c6bd7-253">192.168.1.0/24</span><span class="sxs-lookup"><span data-stu-id="c6bd7-253">192.168.1.0/24</span></span> | <span data-ttu-id="c6bd7-254">Вьетнам</span><span class="sxs-lookup"><span data-stu-id="c6bd7-254">Vietnam</span></span> | <span data-ttu-id="c6bd7-255">172.16.240.110</span><span class="sxs-lookup"><span data-stu-id="c6bd7-255">172.16.240.110</span></span> |
| <span data-ttu-id="c6bd7-256">IDsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c6bd7-256">IDsbc.contoso.com</span></span> | <span data-ttu-id="c6bd7-257">Нет</span><span class="sxs-lookup"><span data-stu-id="c6bd7-257">None</span></span> | <span data-ttu-id="c6bd7-258">192.168.2.5</span><span class="sxs-lookup"><span data-stu-id="c6bd7-258">192.168.2.5</span></span> | <span data-ttu-id="c6bd7-259">192.168.2.0/24</span><span class="sxs-lookup"><span data-stu-id="c6bd7-259">192.168.2.0/24</span></span> | <span data-ttu-id="c6bd7-260">Индонезия</span><span class="sxs-lookup"><span data-stu-id="c6bd7-260">Indonesia</span></span> | <span data-ttu-id="c6bd7-261">172.16.240.120</span><span class="sxs-lookup"><span data-stu-id="c6bd7-261">172.16.240.120</span></span> |
| <span data-ttu-id="c6bd7-262">proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c6bd7-262">proxysbc.contoso.com</span></span> | <span data-ttu-id="c6bd7-263">172.16.240.133</span><span class="sxs-lookup"><span data-stu-id="c6bd7-263">172.16.240.133</span></span> | <span data-ttu-id="c6bd7-264">192.168.3.5</span><span class="sxs-lookup"><span data-stu-id="c6bd7-264">192.168.3.5</span></span> | <span data-ttu-id="c6bd7-265">192.168.3.0/24</span><span class="sxs-lookup"><span data-stu-id="c6bd7-265">192.168.3.0/24</span></span> | <span data-ttu-id="c6bd7-266">Сингапур</span><span class="sxs-lookup"><span data-stu-id="c6bd7-266">Singapore</span></span> | <span data-ttu-id="c6bd7-267">172.16.240.130</span><span class="sxs-lookup"><span data-stu-id="c6bd7-267">172.16.240.130</span></span> |



#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a><span data-ttu-id="c6bd7-268">Исходящие звонки и пользователь находятся в той же папке, что и SBC, но не всегда обходить</span><span class="sxs-lookup"><span data-stu-id="c6bd7-268">Outbound calls and the user is in the same location as the SBC with Always Bypass</span></span>

| <span data-ttu-id="c6bd7-269">Режиме</span><span class="sxs-lookup"><span data-stu-id="c6bd7-269">Mode</span></span> |    <span data-ttu-id="c6bd7-270">Пользователь</span><span class="sxs-lookup"><span data-stu-id="c6bd7-270">User</span></span> |  <span data-ttu-id="c6bd7-271">Местоположение</span><span class="sxs-lookup"><span data-stu-id="c6bd7-271">Location</span></span> |  <span data-ttu-id="c6bd7-272">Направление звонка</span><span class="sxs-lookup"><span data-stu-id="c6bd7-272">Call direction</span></span> |
|:------------|:-------|:-------| :-------|
| <span data-ttu-id="c6bd7-273">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="c6bd7-273">AlwaysBypass</span></span> |    <span data-ttu-id="c6bd7-274">Internal</span><span class="sxs-lookup"><span data-stu-id="c6bd7-274">Internal</span></span> |  <span data-ttu-id="c6bd7-275">Тот же сайт, что и SBC</span><span class="sxs-lookup"><span data-stu-id="c6bd7-275">The same site as SBC</span></span> |  <span data-ttu-id="c6bd7-276">Исходящее</span><span class="sxs-lookup"><span data-stu-id="c6bd7-276">Outbound</span></span> |

<span data-ttu-id="c6bd7-277">В следующей таблице приведены сведения о конфигурации и действии конечных пользователей.</span><span class="sxs-lookup"><span data-stu-id="c6bd7-277">The following table shows the end user configuration and action:</span></span>

| <span data-ttu-id="c6bd7-278">Физическое расположение пользователя</span><span class="sxs-lookup"><span data-stu-id="c6bd7-278">User physical location</span></span>| <span data-ttu-id="c6bd7-279">Пользователь выполняет или получает звонок на номер</span><span class="sxs-lookup"><span data-stu-id="c6bd7-279">User makes or receives a call to/from number</span></span> | <span data-ttu-id="c6bd7-280">Номер телефона пользователя</span><span class="sxs-lookup"><span data-stu-id="c6bd7-280">User phone number</span></span>  | <span data-ttu-id="c6bd7-281">Политика голосовой маршрутизации в сети</span><span class="sxs-lookup"><span data-stu-id="c6bd7-281">Online Voice Routing Policy</span></span> | <span data-ttu-id="c6bd7-282">Режим, настроенный для SBC</span><span class="sxs-lookup"><span data-stu-id="c6bd7-282">Mode configured for SBC</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="c6bd7-283">Вьетнам</span><span class="sxs-lookup"><span data-stu-id="c6bd7-283">Vietnam</span></span> | <span data-ttu-id="c6bd7-284">+ 84 4 3926 3000</span><span class="sxs-lookup"><span data-stu-id="c6bd7-284">+84 4 3926 3000</span></span> | <span data-ttu-id="c6bd7-285">+ 84 4 5555 5555</span><span class="sxs-lookup"><span data-stu-id="c6bd7-285">+84 4 5555 5555</span></span>   | <span data-ttu-id="c6bd7-286">Приоритет 1: ^ \+ 84 (\d {9} ) $-VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c6bd7-286">Priority 1: ^\+84(\d{9})$ -VNsbc.contoso.com</span></span> <br> <span data-ttu-id="c6bd7-287">Приоритет 2:. \*-proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c6bd7-287">Priority 2: .\* - proxysbc.contoso.com</span></span>   | <span data-ttu-id="c6bd7-288">VNsbc.contoso.com – всегда обходить</span><span class="sxs-lookup"><span data-stu-id="c6bd7-288">VNsbc.contoso.com – Always Bypass</span></span> <br> <span data-ttu-id="c6bd7-289">proxysbc.contoso.com – всегда обходить</span><span class="sxs-lookup"><span data-stu-id="c6bd7-289">proxysbc.contoso.com – Always Bypass</span></span>


<span data-ttu-id="c6bd7-290">На приведенной ниже схеме показана лестница SIP для исходящего звонка с режимом "всегда минуя", и пользователь в том же расположении, что и SBC.</span><span class="sxs-lookup"><span data-stu-id="c6bd7-290">The following diagram shows the SIP ladder for an outbound call with Always bypass mode, and the user in the same location as the SBC.</span></span>

<span data-ttu-id="c6bd7-291">![Диаграмма, показывающая исходящие вызовы](media/direct-routing-media-op-10.png "Исходящие звонки")</span><span class="sxs-lookup"><span data-stu-id="c6bd7-291">![Diagram showing outbound calls](media/direct-routing-media-op-10.png "Outbound calls")</span></span>

<span data-ttu-id="c6bd7-292">В таблице ниже указаны заголовки X-MS, отправленные с помощью Direct Routing.</span><span class="sxs-lookup"><span data-stu-id="c6bd7-292">The following table shows the X-MS headers sent by Direct Routing:</span></span>

| <span data-ttu-id="c6bd7-293">Параметр</span><span class="sxs-lookup"><span data-stu-id="c6bd7-293">Parameter</span></span> | <span data-ttu-id="c6bd7-294">Пояснение</span><span class="sxs-lookup"><span data-stu-id="c6bd7-294">Explanation</span></span> |
|:------------|:-------|
| <span data-ttu-id="c6bd7-295">Пригласить + 8443926300@VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c6bd7-295">Invite +8443926300@VNsbc.contoso.com</span></span> | <span data-ttu-id="c6bd7-296">Целевое полное доменное имя для SBC, определенное в политике голосовой маршрутизации через Интернет, отправляется в URI запроса.</span><span class="sxs-lookup"><span data-stu-id="c6bd7-296">The target FQDN of the SBC as defined in the Online Voice Routing Policy is sent in the Request URI</span></span> | 
| <span data-ttu-id="c6bd7-297">X-MS-UserLocation: Internal</span><span class="sxs-lookup"><span data-stu-id="c6bd7-297">X-MS-UserLocation: internal</span></span> | <span data-ttu-id="c6bd7-298">Поле, которое указывает, что пользователь входит в корпоративную сеть</span><span class="sxs-lookup"><span data-stu-id="c6bd7-298">The field indicated that user is located inside the corporate network</span></span> |
| <span data-ttu-id="c6bd7-299">X-MS-MediaPath: VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c6bd7-299">X-MS-MediaPath: VNsbc.contoso.com</span></span> |   <span data-ttu-id="c6bd7-300">Указывает, какой SBC — клиент должен пройти по целевому объекту SBC.</span><span class="sxs-lookup"><span data-stu-id="c6bd7-300">Specifies which SBC the client must traverse to the target SBC.</span></span> <span data-ttu-id="c6bd7-301">В этом случае, так как мы всегда обходите, а клиент является внутренним конечным именем, которое отправляется в заголовке как единственное имя.</span><span class="sxs-lookup"><span data-stu-id="c6bd7-301">In this case as we have Always Bypass, and the client is internal the target name sent as the only name in the header.</span></span> | 
|<span data-ttu-id="c6bd7-302">X-MS-UserSite: Вьетнам</span><span class="sxs-lookup"><span data-stu-id="c6bd7-302">X-MS-UserSite: Vietnam</span></span> |   <span data-ttu-id="c6bd7-303">Поле, указываемое на сайте, на котором находится пользователь.</span><span class="sxs-lookup"><span data-stu-id="c6bd7-303">The field indicated within the site the user is located.</span></span> |


#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a><span data-ttu-id="c6bd7-304">Входящие звонки и пользователь находятся в той же папке, что и SBC, но не всегда пропускать</span><span class="sxs-lookup"><span data-stu-id="c6bd7-304">Inbound calls and the user is in the same location as the SBC with Always Bypass</span></span>

| <span data-ttu-id="c6bd7-305">Режиме</span><span class="sxs-lookup"><span data-stu-id="c6bd7-305">Mode</span></span> |    <span data-ttu-id="c6bd7-306">Пользователь</span><span class="sxs-lookup"><span data-stu-id="c6bd7-306">User</span></span> |  <span data-ttu-id="c6bd7-307">Местоположение</span><span class="sxs-lookup"><span data-stu-id="c6bd7-307">Location</span></span> |  <span data-ttu-id="c6bd7-308">Направление звонка</span><span class="sxs-lookup"><span data-stu-id="c6bd7-308">Call direction</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="c6bd7-309">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="c6bd7-309">AlwaysBypass</span></span> |    <span data-ttu-id="c6bd7-310">Internal</span><span class="sxs-lookup"><span data-stu-id="c6bd7-310">Internal</span></span> | <span data-ttu-id="c6bd7-311">Тот же сайт, что и SBC</span><span class="sxs-lookup"><span data-stu-id="c6bd7-311">The same site as SBC</span></span> | <span data-ttu-id="c6bd7-312">443</span><span class="sxs-lookup"><span data-stu-id="c6bd7-312">Inbound</span></span> |


<span data-ttu-id="c6bd7-313">Во входящем звонке расположение пользователя неизвестно, и SBC должен быть указан в том месте, где находится пользователь.</span><span class="sxs-lookup"><span data-stu-id="c6bd7-313">On an inbound call, the location of the user is unknown, and the SBC must guess where the user is.</span></span> <span data-ttu-id="c6bd7-314">Если предположение не подходит, потребуется повторно пригласить приглашение.</span><span class="sxs-lookup"><span data-stu-id="c6bd7-314">If the guess is not correct, a re-invite will be required.</span></span> <span data-ttu-id="c6bd7-315">В этом случае подразумевается, что пользователь является внутренним, мультимедиа может напрямую перетекать, и дальнейшие действия не требуются (повторно пригласить).</span><span class="sxs-lookup"><span data-stu-id="c6bd7-315">This case assumes user is internal, media can flow directly, and no further actions are required (re-invite).</span></span>
<span data-ttu-id="c6bd7-316">SBC, подключенный к прямой маршрутизации, выводит на экран исходное расположение SBC, предоставляя поля "запись" и "контакт".</span><span class="sxs-lookup"><span data-stu-id="c6bd7-316">The SBC connected to the Direct Routing service reports the originating SBC location by providing Record-Route and Contact fields.</span></span> <span data-ttu-id="c6bd7-317">На основе этих полей путь к носителю рассчитывается посредством прямой маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="c6bd7-317">Based on these fields, the media path is calculated by Direct Routing.</span></span>

<span data-ttu-id="c6bd7-318">Примечание. Учитывая, что пользователь может иметь несколько конечных точек, поддержка 183 невозможна.</span><span class="sxs-lookup"><span data-stu-id="c6bd7-318">Note: Given that a user can have multiple endpoints, support of 183 is not possible.</span></span> <span data-ttu-id="c6bd7-319">В этом случае прямая маршрутизация всегда будет использовать 180 звонков.</span><span class="sxs-lookup"><span data-stu-id="c6bd7-319">The Direct Routing will always use 180 Ringing in this case.</span></span> 

<span data-ttu-id="c6bd7-320">На приведенной ниже схеме показана лестница SIP для входящего звонка в режиме AlwaysBypass, и пользователь находится в том же расположении, что и SBC.</span><span class="sxs-lookup"><span data-stu-id="c6bd7-320">The following diagram shows the SIP ladder for in inbound call with AlwaysBypass mode, and the user is in the same location as the SBC.</span></span>

![Схема, на которой показана лестница SIP](media/direct-routing-media-op-11.png)


#### <a name="outbound-calls-and-the-user-is-external-with-always-bypass"></a><span data-ttu-id="c6bd7-322">Исходящие звонки, а также пользователь с внешними пользователями с помощью функций "всегда минуя"</span><span class="sxs-lookup"><span data-stu-id="c6bd7-322">Outbound calls and the user is external with Always Bypass</span></span>

| <span data-ttu-id="c6bd7-323">Режиме</span><span class="sxs-lookup"><span data-stu-id="c6bd7-323">Mode</span></span> |    <span data-ttu-id="c6bd7-324">Пользователь</span><span class="sxs-lookup"><span data-stu-id="c6bd7-324">User</span></span> |  <span data-ttu-id="c6bd7-325">Сайт</span><span class="sxs-lookup"><span data-stu-id="c6bd7-325">Site</span></span> |  <span data-ttu-id="c6bd7-326">Направление звонка</span><span class="sxs-lookup"><span data-stu-id="c6bd7-326">Call direction</span></span>
|:------------|:-------|:-------|:-------|
<span data-ttu-id="c6bd7-327">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="c6bd7-327">AlwaysBypass</span></span> |  <span data-ttu-id="c6bd7-328">Внешняя</span><span class="sxs-lookup"><span data-stu-id="c6bd7-328">External</span></span> |  <span data-ttu-id="c6bd7-329">Н/Д</span><span class="sxs-lookup"><span data-stu-id="c6bd7-329">N/A</span></span> | <span data-ttu-id="c6bd7-330">Исходящее</span><span class="sxs-lookup"><span data-stu-id="c6bd7-330">Outbound</span></span> |


<span data-ttu-id="c6bd7-331">На приведенной ниже схеме показана лестница SIP для исходящего звонка с использованием режима AlwaysBypass, и пользователь является внешним:</span><span class="sxs-lookup"><span data-stu-id="c6bd7-331">The following diagram shows the SIP ladder for an outbound call with AlwaysBypass mode, and the user is external:</span></span>

![Схема, на которой показана лестница SIP](media/direct-routing-media-op-12.png)

<span data-ttu-id="c6bd7-333">В приведенной ниже таблице указаны заголовки X-MS, отправленные службой прямой маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="c6bd7-333">The following table shows the X-MS headers sent by the Direct Routing service:</span></span>

| <span data-ttu-id="c6bd7-334">Параметр</span><span class="sxs-lookup"><span data-stu-id="c6bd7-334">Parameter</span></span> |   <span data-ttu-id="c6bd7-335">Пояснение</span><span class="sxs-lookup"><span data-stu-id="c6bd7-335">Explanation</span></span> |
|:------------|:-------|
|<span data-ttu-id="c6bd7-336">Пригласить + 8443926300@VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c6bd7-336">Invite +8443926300@VNsbc.contoso.com</span></span> | <span data-ttu-id="c6bd7-337">Целевое полное доменное имя для SBC, определенное в политике голосовой маршрутизации через Интернет, отправляется в URI запроса.</span><span class="sxs-lookup"><span data-stu-id="c6bd7-337">The target FQDN of the SBC as defined in the Online Voice Routing Policy is sent in the Request URI.</span></span>|
| <span data-ttu-id="c6bd7-338">X-MS-UserLocation: External</span><span class="sxs-lookup"><span data-stu-id="c6bd7-338">X-MS-UserLocation: external</span></span> | <span data-ttu-id="c6bd7-339">Поле, в котором указано, что пользователь находится за пределами корпоративной сети.</span><span class="sxs-lookup"><span data-stu-id="c6bd7-339">The field indicated that user is located outside the corporate network.</span></span> |
| <span data-ttu-id="c6bd7-340">X-MS-MediaPath: proxysbc.contoso.com, VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c6bd7-340">X-MS-MediaPath: proxysbc.contoso.com, VNsbc.contoso.com</span></span>    | <span data-ttu-id="c6bd7-341">Указывает, какой SBC — клиент должен пройти по целевому объекту SBC.</span><span class="sxs-lookup"><span data-stu-id="c6bd7-341">Specifies which SBC the client must traverse to the target SBC.</span></span> <span data-ttu-id="c6bd7-342">В этом случае, так как мы всегда обходите, а клиент внешне.</span><span class="sxs-lookup"><span data-stu-id="c6bd7-342">In this case as we have Always Bypass, and the client is external.</span></span> |

#### <a name="inbound-calls-and-the-user-is-external-with-always-bypass"></a><span data-ttu-id="c6bd7-343">Входящие звонки и пользователь являются внешними по отношению к параметру "всегда минуя"</span><span class="sxs-lookup"><span data-stu-id="c6bd7-343">Inbound calls and the user is external with Always Bypass</span></span>

| <span data-ttu-id="c6bd7-344">Режиме</span><span class="sxs-lookup"><span data-stu-id="c6bd7-344">Mode</span></span> | <span data-ttu-id="c6bd7-345">Пользователь</span><span class="sxs-lookup"><span data-stu-id="c6bd7-345">User</span></span> | <span data-ttu-id="c6bd7-346">Сайт</span><span class="sxs-lookup"><span data-stu-id="c6bd7-346">Site</span></span> |  <span data-ttu-id="c6bd7-347">Направление звонка</span><span class="sxs-lookup"><span data-stu-id="c6bd7-347">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
<span data-ttu-id="c6bd7-348">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="c6bd7-348">AlwaysBypass</span></span> |  <span data-ttu-id="c6bd7-349">Внешняя</span><span class="sxs-lookup"><span data-stu-id="c6bd7-349">External</span></span> |  <span data-ttu-id="c6bd7-350">Н/Д</span><span class="sxs-lookup"><span data-stu-id="c6bd7-350">N/A</span></span> |   <span data-ttu-id="c6bd7-351">443</span><span class="sxs-lookup"><span data-stu-id="c6bd7-351">Inbound</span></span> |

<span data-ttu-id="c6bd7-352">Для входящего звонка SBC, подключенный к прямой маршрутизации, должен отправить повторное приглашение (по умолчанию предлагаются пользовательские кандидаты на носители), если расположение пользователя является внешним.</span><span class="sxs-lookup"><span data-stu-id="c6bd7-352">For an inbound call, the SBC connected to Direct Routing needs to send a re-invite (by default, local media candidates are always offered) if the location of the user is external.</span></span>  <span data-ttu-id="c6bd7-353">X-MediaPath вычисляется на основе маршрута записи и заданного пользователем SBC.</span><span class="sxs-lookup"><span data-stu-id="c6bd7-353">The X-MediaPath is calculated based on Record-Route and the SBC user specified.</span></span>

<span data-ttu-id="c6bd7-354">На приведенной ниже схеме показана лестница SIP для входящего звонка с использованием режима AlwaysBypass, и пользователь является внешним.</span><span class="sxs-lookup"><span data-stu-id="c6bd7-354">The following diagram shows the SIP ladder for an inbound call with AlwaysBypass mode, and the user is external.</span></span>

![Схема, на которой показана лестница SIP](media/direct-routing-media-op-13.png)


### <a name="only-for-local-users-mode"></a><span data-ttu-id="c6bd7-356">Только в режиме локальных пользователей</span><span class="sxs-lookup"><span data-stu-id="c6bd7-356">Only for local users mode</span></span>

<span data-ttu-id="c6bd7-357">Локальные мультимедийные варианты целевого SBC будут предлагаться только в том случае, если пользователь находится в том же расположении, что и SBC.</span><span class="sxs-lookup"><span data-stu-id="c6bd7-357">Local media candidates of the target SBC will be offered only if a user is in the same location as the SBC.</span></span> <span data-ttu-id="c6bd7-358">Во всех остальных случаях мультимедиа будет проходить через внутренний или внешний IP-адрес объекта SBC прокси.</span><span class="sxs-lookup"><span data-stu-id="c6bd7-358">In all other cases, media will flow through either an internal or external IP of the proxy SBC.</span></span>

<span data-ttu-id="c6bd7-359">Ниже описаны сценарии.</span><span class="sxs-lookup"><span data-stu-id="c6bd7-359">The following scenarios are described:</span></span>

- [<span data-ttu-id="c6bd7-360">Исходящие звонки и пользователь находятся в той же папке, что и SBC</span><span class="sxs-lookup"><span data-stu-id="c6bd7-360">Outbound calls and the user is in the same location as the SBC</span></span>](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [<span data-ttu-id="c6bd7-361">Входящие звонки и пользователь находятся в той же папке, что и SBC</span><span class="sxs-lookup"><span data-stu-id="c6bd7-361">Inbound calls and the user is in the same location as the SBC</span></span>](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [<span data-ttu-id="c6bd7-362">Пользователь не находится в том же месте, что и SBC, но входит в корпоративную сеть</span><span class="sxs-lookup"><span data-stu-id="c6bd7-362">User is not at the same location as the SBC but is in the corporate network</span></span>](#user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users)
- [<span data-ttu-id="c6bd7-363">Входящие звонки и пользователь являются внутренними, но не находятся в том же месте, что и SBC.</span><span class="sxs-lookup"><span data-stu-id="c6bd7-363">Inbound calls and the user is internal but is not at the same location as the SBC</span></span>](#inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users)

<span data-ttu-id="c6bd7-364">В приведенной ниже таблице показано, как настроить конфигурацию и действие конечного пользователя.</span><span class="sxs-lookup"><span data-stu-id="c6bd7-364">The following table shows end user configuration and action:</span></span>

| <span data-ttu-id="c6bd7-365">Физическое расположение пользователя</span><span class="sxs-lookup"><span data-stu-id="c6bd7-365">User physical location</span></span> |  <span data-ttu-id="c6bd7-366">Пользователь выполняет или получает звонок на номер</span><span class="sxs-lookup"><span data-stu-id="c6bd7-366">User makes or receives a call to/from number</span></span> |  <span data-ttu-id="c6bd7-367">Номер телефона пользователя</span><span class="sxs-lookup"><span data-stu-id="c6bd7-367">User phone number</span></span> | <span data-ttu-id="c6bd7-368">Политика голосовой маршрутизации в сети</span><span class="sxs-lookup"><span data-stu-id="c6bd7-368">Online Voice Routing Policy</span></span> |   <span data-ttu-id="c6bd7-369">Режим, настроенный для SBC</span><span class="sxs-lookup"><span data-stu-id="c6bd7-369">Mode configured for SBC</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="c6bd7-370">Вьетнам</span><span class="sxs-lookup"><span data-stu-id="c6bd7-370">Vietnam</span></span> | <span data-ttu-id="c6bd7-371">+ 84 4 3926 3000</span><span class="sxs-lookup"><span data-stu-id="c6bd7-371">+84 4 3926  3000</span></span> |  <span data-ttu-id="c6bd7-372">+ 84 4 5555 5555</span><span class="sxs-lookup"><span data-stu-id="c6bd7-372">+84 4 5555 5555</span></span> | <span data-ttu-id="c6bd7-373">Приоритет 1: ^ \+ 84 (\d {9} ) $-VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c6bd7-373">Priority 1: ^\+84(\d{9})$ -VNsbc.contoso.com</span></span> <br> <span data-ttu-id="c6bd7-374">Приоритет 2:. \*-proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c6bd7-374">Priority 2: .\* - proxysbc.contoso.com</span></span> | <span data-ttu-id="c6bd7-375">VNsbc.contoso.com — OnlyForLocalUsers Proxysbc.contoso.com — всегда обходить</span><span class="sxs-lookup"><span data-stu-id="c6bd7-375">VNsbc.contoso.com – OnlyForLocalUsers Proxysbc.contoso.com – Always Bypass</span></span> |

#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="c6bd7-376">Исходящие звонки и пользователь находятся в той же папке, что и SBC только для локальных пользователей.</span><span class="sxs-lookup"><span data-stu-id="c6bd7-376">Outbound calls and the user is in the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="c6bd7-377">Режиме</span><span class="sxs-lookup"><span data-stu-id="c6bd7-377">Mode</span></span> | <span data-ttu-id="c6bd7-378">Пользователь</span><span class="sxs-lookup"><span data-stu-id="c6bd7-378">User</span></span> | <span data-ttu-id="c6bd7-379">Сайт</span><span class="sxs-lookup"><span data-stu-id="c6bd7-379">Site</span></span> | <span data-ttu-id="c6bd7-380">Направление звонка</span><span class="sxs-lookup"><span data-stu-id="c6bd7-380">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="c6bd7-381">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="c6bd7-381">OnlyForLocalUsers</span></span> |   <span data-ttu-id="c6bd7-382">Internal</span><span class="sxs-lookup"><span data-stu-id="c6bd7-382">Internal</span></span> |<span data-ttu-id="c6bd7-383">То же, что и SBC</span><span class="sxs-lookup"><span data-stu-id="c6bd7-383">Same as SBC</span></span>   | <span data-ttu-id="c6bd7-384">Исходящее</span><span class="sxs-lookup"><span data-stu-id="c6bd7-384">Outbound</span></span> |

<span data-ttu-id="c6bd7-385">На приведенной ниже схеме показан исходящий вызов с использованием режима OnlyForLocalUsers, и пользователь находится в том же расположении, что и SBC.</span><span class="sxs-lookup"><span data-stu-id="c6bd7-385">The following diagram shows an outbound call with OnlyForLocalUsers mode, and the user is in the same location as the SBC.</span></span> <span data-ttu-id="c6bd7-386">Это тот же поток, который показан в [исходящих звонках, если пользователь находится в том же месте, что и SBC](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span><span class="sxs-lookup"><span data-stu-id="c6bd7-386">This is the same flow shown in [Outbound calls when the user is in the same location as the SBC](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span></span>

![Схема, на которой показана лестница SIP](media/direct-routing-media-op-14.png)


#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="c6bd7-388">Входящие звонки и пользователь находятся в той же папке, что и SBC только для локальных пользователей.</span><span class="sxs-lookup"><span data-stu-id="c6bd7-388">Inbound calls and the user is in the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="c6bd7-389">Режиме</span><span class="sxs-lookup"><span data-stu-id="c6bd7-389">Mode</span></span> | <span data-ttu-id="c6bd7-390">Пользователь</span><span class="sxs-lookup"><span data-stu-id="c6bd7-390">User</span></span> | <span data-ttu-id="c6bd7-391">Сайт</span><span class="sxs-lookup"><span data-stu-id="c6bd7-391">Site</span></span> | <span data-ttu-id="c6bd7-392">Направление звонка</span><span class="sxs-lookup"><span data-stu-id="c6bd7-392">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="c6bd7-393">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="c6bd7-393">OnlyForLocalUsers</span></span> |   <span data-ttu-id="c6bd7-394">Internal</span><span class="sxs-lookup"><span data-stu-id="c6bd7-394">Internal</span></span> | <span data-ttu-id="c6bd7-395">То же, что и SBC</span><span class="sxs-lookup"><span data-stu-id="c6bd7-395">Same as SBC</span></span> | <span data-ttu-id="c6bd7-396">443</span><span class="sxs-lookup"><span data-stu-id="c6bd7-396">Inbound</span></span> |

<span data-ttu-id="c6bd7-397">На приведенной ниже схеме показан входящий вызов с использованием режима OnlyForLocalUsers, и пользователь находится в том же расположении, что и SBC.</span><span class="sxs-lookup"><span data-stu-id="c6bd7-397">The following diagram shows an inbound call with OnlyForLocalUsers mode, and the user is in the same location as the SBC.</span></span> <span data-ttu-id="c6bd7-398">Это тот же поток, что и во [входящих звонках, когда пользователь находится в том же месте, что и SBC](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span><span class="sxs-lookup"><span data-stu-id="c6bd7-398">This is the same flow as shown in [Inbound calls when the user is in the same location as the SBC](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span></span>

![Схема, на которой показана лестница SIP](media/direct-routing-media-op-15.png)


#### <a name="user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users"></a><span data-ttu-id="c6bd7-400">Пользователь не находится в том же месте, что и SBC, но входит в корпоративную сеть только для локальных пользователей.</span><span class="sxs-lookup"><span data-stu-id="c6bd7-400">User is not at the same location as the SBC but is in the corporate network with Only for local users</span></span>

| <span data-ttu-id="c6bd7-401">Режиме</span><span class="sxs-lookup"><span data-stu-id="c6bd7-401">Mode</span></span> | <span data-ttu-id="c6bd7-402">Пользователь</span><span class="sxs-lookup"><span data-stu-id="c6bd7-402">User</span></span> | <span data-ttu-id="c6bd7-403">Сайт</span><span class="sxs-lookup"><span data-stu-id="c6bd7-403">Site</span></span> |<span data-ttu-id="c6bd7-404">Направление звонка</span><span class="sxs-lookup"><span data-stu-id="c6bd7-404">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="c6bd7-405">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="c6bd7-405">OnlyForLocalUsers</span></span>  | <span data-ttu-id="c6bd7-406">Internal</span><span class="sxs-lookup"><span data-stu-id="c6bd7-406">Internal</span></span> |   <span data-ttu-id="c6bd7-407">Отличается от SBC</span><span class="sxs-lookup"><span data-stu-id="c6bd7-407">Different from SBC</span></span> | <span data-ttu-id="c6bd7-408">Исходящее</span><span class="sxs-lookup"><span data-stu-id="c6bd7-408">Outbound</span></span> |

<span data-ttu-id="c6bd7-409">Прямая маршрутизация рассчитывает X-MediaPath в зависимости от того, где находится указанное расположение пользователя и режима, настроенных на SBC.</span><span class="sxs-lookup"><span data-stu-id="c6bd7-409">Direct routing calculates X-MediaPath based on the reported location of the user and mode configured on the SBC.</span></span>


<span data-ttu-id="c6bd7-410">На приведенной ниже схеме показан исходящий вызов с использованием режима OnlyForLocalUsers и внутренний пользователь, который не находится в том же месте, что и SBC.</span><span class="sxs-lookup"><span data-stu-id="c6bd7-410">The following diagram shows an outbound call with OnlyForLocalUsers mode, and an internal user who is not at the same location as the SBC.</span></span>

![Схема, на которой показана лестница SIP](media/direct-routing-media-op-16.png)


#### <a name="inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="c6bd7-412">Входящий звонок и пользователь является внутренним, но не в том же месте, что и SBC только для локальных пользователей.</span><span class="sxs-lookup"><span data-stu-id="c6bd7-412">Inbound call and the user is internal but is not at the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="c6bd7-413">Режиме</span><span class="sxs-lookup"><span data-stu-id="c6bd7-413">Mode</span></span> |    <span data-ttu-id="c6bd7-414">Пользователь</span><span class="sxs-lookup"><span data-stu-id="c6bd7-414">User</span></span> |  <span data-ttu-id="c6bd7-415">Сайт</span><span class="sxs-lookup"><span data-stu-id="c6bd7-415">Site</span></span> |  <span data-ttu-id="c6bd7-416">Направление звонка</span><span class="sxs-lookup"><span data-stu-id="c6bd7-416">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="c6bd7-417">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="c6bd7-417">OnlyForLocalUsers</span></span> | <span data-ttu-id="c6bd7-418">Internal</span><span class="sxs-lookup"><span data-stu-id="c6bd7-418">Internal</span></span> |    <span data-ttu-id="c6bd7-419">Отличается от SBC</span><span class="sxs-lookup"><span data-stu-id="c6bd7-419">Different from SBC</span></span> |    <span data-ttu-id="c6bd7-420">443</span><span class="sxs-lookup"><span data-stu-id="c6bd7-420">Inbound</span></span> |

<span data-ttu-id="c6bd7-421">На приведенной ниже схеме показан входящий вызов с использованием режима OnlyForLocalUsers и внутренний пользователь, который не находится в том же месте, что и SBC.</span><span class="sxs-lookup"><span data-stu-id="c6bd7-421">The following diagram shows an inbound call with OnlyForLocalUsers mode, and an internal user who is not at the same location as the SBC.</span></span>

![Схема, на которой показана лестница SIP](media/direct-routing-media-op-17.png)









