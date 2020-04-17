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
ms.openlocfilehash: 8a69a46d7620628c7afffb706354c0f6e7868f3d
ms.sourcegitcommit: 3dd6499416e9fbdcb48187c6322bd607290502ce
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2020
ms.locfileid: "43541596"
---
# <a name="configure-local-media-optimization-for-direct-routing"></a><span data-ttu-id="968e5-103">Настройка оптимизации локальных файлов мультимедиа для прямой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="968e5-103">Configure Local Media Optimization for Direct Routing</span></span>

<span data-ttu-id="968e5-104">Настройка оптимизации локальных файлов мультимедиа основывается на параметрах сети, которые являются общими для других функций голосовой связи в облаке, таких как маршрутизация на основе местоположения и динамический вызов экстренной помощи.</span><span class="sxs-lookup"><span data-stu-id="968e5-104">Configuration for Local Media Optimization is based on network settings that are common to other cloud voice features, such as Location-Based Routing and dynamic emergency calling.</span></span> <span data-ttu-id="968e5-105">Чтобы узнать больше о регионах сети, сетевых сайтах, подсетях сети и о доверенных IP-адресах, просмотрите [Параметры сети для функций голосовой связи в облаке](cloud-voice-network-settings.md).</span><span class="sxs-lookup"><span data-stu-id="968e5-105">To learn more about network regions, network sites, network subnets, and trusted IP addresses, see [Network settings for cloud voice features](cloud-voice-network-settings.md).</span></span>

<span data-ttu-id="968e5-106">Перед настройкой оптимизации локального мультимедиа ознакомьтесь со сведениями [об оптимизации локальных файлов для прямой маршрутизации](direct-routing-media-optimization.md).</span><span class="sxs-lookup"><span data-stu-id="968e5-106">Before you configure Local Media Optimization, see [Local media Optimization for Direct Routing](direct-routing-media-optimization.md).</span></span>  

<span data-ttu-id="968e5-107">Для настройки оптимизации локального мультимедиа необходимо выполнить указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="968e5-107">To configure Local Media Optimization, the following steps are required.</span></span> <span data-ttu-id="968e5-108">Вы можете использовать центр администрирования Teams или PowerShell.</span><span class="sxs-lookup"><span data-stu-id="968e5-108">You can use the Teams Admin Center or PowerShell.</span></span> <span data-ttu-id="968e5-109">Подробности можно найти в разделе [Управление топологией сети](manage-your-network-topology.md).</span><span class="sxs-lookup"><span data-stu-id="968e5-109">For details, see [Manage your network topology](manage-your-network-topology.md).</span></span>

1. <span data-ttu-id="968e5-110">Настройте пользователя и сайты SBC (как описано в этой статье).</span><span class="sxs-lookup"><span data-stu-id="968e5-110">Configure the user and the SBC sites (as described in this article).</span></span>
2. <span data-ttu-id="968e5-111">Настройте локальную SBCs для оптимизации локальных файлов (в соответствии со спецификацией поставщика SBC).</span><span class="sxs-lookup"><span data-stu-id="968e5-111">Configure the SBCs for Local Media Optimization (according to your SBC vendor specification).</span></span>

<span data-ttu-id="968e5-112">На приведенной ниже схеме показана настройка сети, используемая в примерах в этой статье.</span><span class="sxs-lookup"><span data-stu-id="968e5-112">The following diagram shows the network setup used in the examples throughout this article.</span></span>

<span data-ttu-id="968e5-113">![Пример схемы, показывающей параметры сети](media/direct-routing-media-op-9.png "Примеры настройки сети")</span><span class="sxs-lookup"><span data-stu-id="968e5-113">![Diagram showing network setup for examples](media/direct-routing-media-op-9.png "Network setup for examples")</span></span>


## <a name="configure-the-user-and-the-sbc-sites"></a><span data-ttu-id="968e5-114">Настройка пользователей и сайтов SBC</span><span class="sxs-lookup"><span data-stu-id="968e5-114">Configure the user and the SBC sites</span></span>

<span data-ttu-id="968e5-115">Чтобы настроить пользователя и сайты SBC, необходимо выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="968e5-115">To configure the user and the SBC sites, you will need to:</span></span>

1. <span data-ttu-id="968e5-116">[Управление внешними доверенными IP-адресами](#manage-external-trusted-ip-addresses).</span><span class="sxs-lookup"><span data-stu-id="968e5-116">[Manage external trusted IP addresses](#manage-external-trusted-ip-addresses).</span></span>  

2. <span data-ttu-id="968e5-117">[Определите топологию сети](#define-the-network-topology) , настроив регионы сети, сетевые сайты и сетевые подсети.</span><span class="sxs-lookup"><span data-stu-id="968e5-117">[Define the network topology](#define-the-network-topology) by configuring the network regions, network sites, and network subnets.</span></span>

3. <span data-ttu-id="968e5-118">[Определите топологию виртуальной сети](#define-the-virtual-network-topology) путем назначения SBC (-ов) на сайты, используя необходимые режимы и значения SBC-прокси.</span><span class="sxs-lookup"><span data-stu-id="968e5-118">[Define the virtual network topology](#define-the-virtual-network-topology) by assigning SBC(s) to site(s) with relevant modes and proxy SBC values.</span></span>


## <a name="configure-sbcs-for-local-media-optimization-according-to-the-sbc-vendor-specification"></a><span data-ttu-id="968e5-119">Настройка SBC (s) для оптимизации локальных файлов мультимедиа в соответствии со спецификацией поставщика SBC</span><span class="sxs-lookup"><span data-stu-id="968e5-119">Configure SBC(s) for Local Media Optimization according to the SBC vendor specification</span></span>

<span data-ttu-id="968e5-120">В этой статье описано, как настроить компоненты Microsoft.</span><span class="sxs-lookup"><span data-stu-id="968e5-120">This article describes configuration for Microsoft components.</span></span> <span data-ttu-id="968e5-121">Информацию о настройке SBC можно найти в documenation поставщика SBC.</span><span class="sxs-lookup"><span data-stu-id="968e5-121">For information on SBC configuration, see your SBC vendor documenation.</span></span>

<span data-ttu-id="968e5-122">Локальная Оптимизация файлов мультимедиа поддерживается следующими разработчиками SBC:</span><span class="sxs-lookup"><span data-stu-id="968e5-122">Local Media Optimization is supported by the following SBC vendors:</span></span>

| <span data-ttu-id="968e5-123">Поставщик</span><span class="sxs-lookup"><span data-stu-id="968e5-123">Vendor</span></span> | <span data-ttu-id="968e5-124">ПРОИЗВЕД</span><span class="sxs-lookup"><span data-stu-id="968e5-124">Product</span></span> |    <span data-ttu-id="968e5-125">Версия программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="968e5-125">Software version</span></span> |
|:------------|:-------|:-------| :-------|
| [<span data-ttu-id="968e5-126">Audiocodes</span><span class="sxs-lookup"><span data-stu-id="968e5-126">Audiocodes</span></span>](https://www.audiocodes.com/media/13253/connecting-audiocodes-sbc-to-microsoft-teams-direct-routing-enterprise-model-configuration-note.pdf) |    <span data-ttu-id="968e5-127">Mediant 500 SBC</span><span class="sxs-lookup"><span data-stu-id="968e5-127">Mediant 500 SBC</span></span> |   <span data-ttu-id="968e5-128">7.20 а. 256</span><span class="sxs-lookup"><span data-stu-id="968e5-128">7.20A.256</span></span> | 
|            |  <span data-ttu-id="968e5-129">Mediant 800 SBC</span><span class="sxs-lookup"><span data-stu-id="968e5-129">Mediant 800 SBC</span></span> |   <span data-ttu-id="968e5-130">7.20 а. 256</span><span class="sxs-lookup"><span data-stu-id="968e5-130">7.20A.256</span></span> | 
|            |  <span data-ttu-id="968e5-131">Mediant 2600 SBC</span><span class="sxs-lookup"><span data-stu-id="968e5-131">Mediant 2600 SBC</span></span> |  <span data-ttu-id="968e5-132">7.20 а. 256</span><span class="sxs-lookup"><span data-stu-id="968e5-132">7.20A.256</span></span> | 
|            |  <span data-ttu-id="968e5-133">Mediant 4000 SBC</span><span class="sxs-lookup"><span data-stu-id="968e5-133">Mediant 4000 SBC</span></span> |  <span data-ttu-id="968e5-134">7.20 а. 256</span><span class="sxs-lookup"><span data-stu-id="968e5-134">7.20A.256</span></span> | 
|            |  <span data-ttu-id="968e5-135">Функция МЕДИАНА 1000Bого SBC</span><span class="sxs-lookup"><span data-stu-id="968e5-135">Mediant 1000B SBC</span></span> | <span data-ttu-id="968e5-136">7.20 а. 256</span><span class="sxs-lookup"><span data-stu-id="968e5-136">7.20A.256</span></span> | 
|            |  <span data-ttu-id="968e5-137">Одномедианый SBC 9000</span><span class="sxs-lookup"><span data-stu-id="968e5-137">Mediant 9000 SBC</span></span> |  <span data-ttu-id="968e5-138">7.20 а. 256</span><span class="sxs-lookup"><span data-stu-id="968e5-138">7.20A.256</span></span> | 
|            |  <span data-ttu-id="968e5-139">Односрединный виртуальный SBC</span><span class="sxs-lookup"><span data-stu-id="968e5-139">Mediant Virtual Edition SBC</span></span> |   <span data-ttu-id="968e5-140">7.20 а. 256</span><span class="sxs-lookup"><span data-stu-id="968e5-140">7.20A.256</span></span> | 
|            |  <span data-ttu-id="968e5-141">SBC по выпуску "Медиана"</span><span class="sxs-lookup"><span data-stu-id="968e5-141">Mediant Cloud Edition SBC</span></span> | <span data-ttu-id="968e5-142">7.20 а. 256</span><span class="sxs-lookup"><span data-stu-id="968e5-142">7.20A.256</span></span> |
| [<span data-ttu-id="968e5-143">Базовые компоненты SBC для ленты</span><span class="sxs-lookup"><span data-stu-id="968e5-143">Ribbon SBC Core</span></span>](https://support.sonus.net/display/ALLDOC/SBC+8.2+-+Configure+Local+Media+Optimization)  |  <span data-ttu-id="968e5-144">SBC 5110</span><span class="sxs-lookup"><span data-stu-id="968e5-144">SBC 5110</span></span>         | <span data-ttu-id="968e5-145">8,2</span><span class="sxs-lookup"><span data-stu-id="968e5-145">8.2</span></span>  |
|            |  <span data-ttu-id="968e5-146">SBC 5210</span><span class="sxs-lookup"><span data-stu-id="968e5-146">SBC 5210</span></span>         | <span data-ttu-id="968e5-147">8,2</span><span class="sxs-lookup"><span data-stu-id="968e5-147">8.2</span></span>  |
|            |  <span data-ttu-id="968e5-148">SBC 5400</span><span class="sxs-lookup"><span data-stu-id="968e5-148">SBC 5400</span></span>         | <span data-ttu-id="968e5-149">8,2</span><span class="sxs-lookup"><span data-stu-id="968e5-149">8.2</span></span>  |
|            |  <span data-ttu-id="968e5-150">SBC 7000</span><span class="sxs-lookup"><span data-stu-id="968e5-150">SBC 7000</span></span>         | <span data-ttu-id="968e5-151">8,2</span><span class="sxs-lookup"><span data-stu-id="968e5-151">8.2</span></span>  |
|            |  <span data-ttu-id="968e5-152">SBC SWe</span><span class="sxs-lookup"><span data-stu-id="968e5-152">SBC SWe</span></span>          | <span data-ttu-id="968e5-153">8,2</span><span class="sxs-lookup"><span data-stu-id="968e5-153">8.2</span></span>  |
| [<span data-ttu-id="968e5-154">Ребро для SBC ленты</span><span class="sxs-lookup"><span data-stu-id="968e5-154">Ribbon SBC Edge</span></span>](https://support.sonus.net/display/UXDOC81/Microsoft+Teams+Direct+Routing+-+On+Premises+Deployment)  |  <span data-ttu-id="968e5-155">SBC 1000</span><span class="sxs-lookup"><span data-stu-id="968e5-155">SBC 1000</span></span>         | <span data-ttu-id="968e5-156">8.1.1, сборка 527</span><span class="sxs-lookup"><span data-stu-id="968e5-156">8.1.1, build 527</span></span> |
|            |  <span data-ttu-id="968e5-157">SBC 2000</span><span class="sxs-lookup"><span data-stu-id="968e5-157">SBC 2000</span></span>         | <span data-ttu-id="968e5-158">8.1.1, сборка 527</span><span class="sxs-lookup"><span data-stu-id="968e5-158">8.1.1, build 527</span></span> |
|            |  <span data-ttu-id="968e5-159">SBC SWe Lite</span><span class="sxs-lookup"><span data-stu-id="968e5-159">SBC SWe Lite</span></span>     | <span data-ttu-id="968e5-160">8.1.0, сборка 222</span><span class="sxs-lookup"><span data-stu-id="968e5-160">8.1.0, build 222</span></span> |
| [<span data-ttu-id="968e5-161">TE-SYSTEMS</span><span class="sxs-lookup"><span data-stu-id="968e5-161">TE-SYSTEMS</span></span>](https://www.anynode.de/local_media_optimization/) |  <span data-ttu-id="968e5-162">anynode</span><span class="sxs-lookup"><span data-stu-id="968e5-162">anynode</span></span>          | <span data-ttu-id="968e5-163">4.0.1 +</span><span class="sxs-lookup"><span data-stu-id="968e5-163">4.0.1+</span></span> |
| [<span data-ttu-id="968e5-164">Oracle</span><span class="sxs-lookup"><span data-stu-id="968e5-164">Oracle</span></span>](https://www.oracle.com/industries/communications/enterprise-communications/session-border-controller/microsoft.html) | <span data-ttu-id="968e5-165">AP 1100</span><span class="sxs-lookup"><span data-stu-id="968e5-165">AP 1100</span></span> | <span data-ttu-id="968e5-166">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="968e5-166">8.4.0.0.0</span></span> |
|        | <span data-ttu-id="968e5-167">AP 3900</span><span class="sxs-lookup"><span data-stu-id="968e5-167">AP 3900</span></span> | <span data-ttu-id="968e5-168">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="968e5-168">8.4.0.0.0</span></span> |
|        | <span data-ttu-id="968e5-169">AP 4600</span><span class="sxs-lookup"><span data-stu-id="968e5-169">AP 4600</span></span> | <span data-ttu-id="968e5-170">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="968e5-170">8.4.0.0.0</span></span> | 
|        | <span data-ttu-id="968e5-171">AP 6300</span><span class="sxs-lookup"><span data-stu-id="968e5-171">AP 6300</span></span> | <span data-ttu-id="968e5-172">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="968e5-172">8.4.0.0.0</span></span> |
|        | <span data-ttu-id="968e5-173">AP 6350</span><span class="sxs-lookup"><span data-stu-id="968e5-173">AP 6350</span></span> | <span data-ttu-id="968e5-174">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="968e5-174">8.4.0.0.0</span></span> | 
|        | <span data-ttu-id="968e5-175">VME</span><span class="sxs-lookup"><span data-stu-id="968e5-175">VME</span></span>     | <span data-ttu-id="968e5-176">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="968e5-176">8.4.0.0.0</span></span> |


## <a name="manage-external-trusted-ip-addresses"></a><span data-ttu-id="968e5-177">Управление внешними надежными IP-адресами</span><span class="sxs-lookup"><span data-stu-id="968e5-177">Manage external trusted IP addresses</span></span>

<span data-ttu-id="968e5-178">Внешние надежные IP-адреса — это внешние IP-адреса Интернет-адресов корпоративной сети.</span><span class="sxs-lookup"><span data-stu-id="968e5-178">External trusted IPs are the Internet external IPs of the enterprise network.</span></span> <span data-ttu-id="968e5-179">Эти IP-адреса используются клиентами Microsoft Teams при подключении к Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="968e5-179">These IP’s are the IP addresses used by Microsoft Teams clients when they connect to Microsoft 365.</span></span> <span data-ttu-id="968e5-180">Вам необходимо добавить эти внешние IP-адреса для каждого сайта, на котором пользователи используют локальную оптимизацию мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="968e5-180">You need to add these external IPs for each site where you have users using Local Media Optimization.</span></span>

<span data-ttu-id="968e5-181">Чтобы добавить общедоступные IP-адреса для каждого сайта, используйте командлет New-CsTenantTrustedIPAddress.</span><span class="sxs-lookup"><span data-stu-id="968e5-181">To add the public IP addresses for each site, use the New-CsTenantTrustedIPAddress cmdlet.</span></span> <span data-ttu-id="968e5-182">Вы можете определить неограниченное количество доверенных IP-адресов для клиента.</span><span class="sxs-lookup"><span data-stu-id="968e5-182">You can define an unlimited number of trusted IP addresses for a tenant.</span></span> <span data-ttu-id="968e5-183">Если внешние IP-адреса, обнаруженные Microsoft 365, являются адресами IPv4 и IPv6, необходимо добавить оба типа IP.</span><span class="sxs-lookup"><span data-stu-id="968e5-183">If the external IPs seen by Microsoft 365 are both IPv4 and IPv6 addresses, you need to add both types of IP addresses.</span></span> <span data-ttu-id="968e5-184">Для IPv4 используется маска 32.</span><span class="sxs-lookup"><span data-stu-id="968e5-184">For IPv4, use mask 32.</span></span> <span data-ttu-id="968e5-185">Для IPv6 используйте маску 128.</span><span class="sxs-lookup"><span data-stu-id="968e5-185">For IPv6, use mask 128.</span></span> <span data-ttu-id="968e5-186">Вы можете добавить как отдельные внешние IP-адреса, так и внешние IP-подсети, указав разные MaskBits в командлете.</span><span class="sxs-lookup"><span data-stu-id="968e5-186">You can add both individual external IP addresses and external IP subnets by specifying different MaskBits on the cmdlet.</span></span>

```
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description>
```


<span data-ttu-id="968e5-187">Пример добавления доверенных IP-адресов.</span><span class="sxs-lookup"><span data-stu-id="968e5-187">Example of adding trusted IP addresses.</span></span>

```
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.110 -MaskBits 32 -Description "Vietnam site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.120 -MaskBits 32 -Description "Indonesia site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.130 -MaskBits 32 -Description "Singapore site trusted IP"
```


## <a name="define-the-network-topology"></a><span data-ttu-id="968e5-188">Определение топологии сети</span><span class="sxs-lookup"><span data-stu-id="968e5-188">Define the network topology</span></span>

<span data-ttu-id="968e5-189">В этом разделе рассказывается, как определить регионы сети, сетевые сайты и сетевые подсети для топологии сети.</span><span class="sxs-lookup"><span data-stu-id="968e5-189">This section describes how to define the network regions, network sites, and network subnets for your network topology.</span></span>

<span data-ttu-id="968e5-190">Все параметры чувствительны к регистру, поэтому необходимо использовать тот же сценарий, который использовался при настройке.</span><span class="sxs-lookup"><span data-stu-id="968e5-190">All parameters are case sensitive so you need to ensure that you use the same case that was used during setup.</span></span>  <span data-ttu-id="968e5-191">(Например, GatewaySiteID значения "Вьетнам" и "Вьетнам" будут считаться разными сайтами.)</span><span class="sxs-lookup"><span data-stu-id="968e5-191">(For example, GatewaySiteID values “Vietnam” and “vietnam” will be treated as different sites.)</span></span>

### <a name="define-network-regions"></a><span data-ttu-id="968e5-192">Определение регионов сети</span><span class="sxs-lookup"><span data-stu-id="968e5-192">Define network regions</span></span>

<span data-ttu-id="968e5-193">Чтобы определить регионы сети, используйте командлет New-CsTenantNetworkRegion.</span><span class="sxs-lookup"><span data-stu-id="968e5-193">To define network regions, use the New-CsTenantNetworkRegion cmdlet.</span></span> <span data-ttu-id="968e5-194">Параметр RegionID — это логическое имя, представляющее собой географию области и не обладающее зависимостями или ограничениями.</span><span class="sxs-lookup"><span data-stu-id="968e5-194">The RegionID parameter is a logical name that represents the geography of the region and has no dependencies or restrictions.</span></span> <span data-ttu-id="968e5-195">Параметр CentralSite <site ID> является необязательным.</span><span class="sxs-lookup"><span data-stu-id="968e5-195">The CentralSite <site ID> parameter is optional.</span></span>

```
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

<span data-ttu-id="968e5-196">В следующем примере создается сетевой регион с именем APAC:</span><span class="sxs-lookup"><span data-stu-id="968e5-196">The following example creates a network region named APAC:</span></span>

```
New-CsTenantNetworkRegion -NetworkRegionID "APAC"  
```

###  <a name="define-network-sites"></a><span data-ttu-id="968e5-197">Определение сетевых сайтов</span><span class="sxs-lookup"><span data-stu-id="968e5-197">Define network sites</span></span>

<span data-ttu-id="968e5-198">Для определения сетевых сайтов используйте командлет New-CsTenantNetworkSite.</span><span class="sxs-lookup"><span data-stu-id="968e5-198">To define network sites, use the New-CsTenantNetworkSite cmdlet.</span></span> <span data-ttu-id="968e5-199">Каждый сетевой сайт должен быть связан с сетевым регионом.</span><span class="sxs-lookup"><span data-stu-id="968e5-199">Each network site must be associated with a network region.</span></span>

```
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```

<span data-ttu-id="968e5-200">В следующем примере показано создание трех новых сайтов сети, Вьетнам, Индонезия и Сингапур в регионе APAC:</span><span class="sxs-lookup"><span data-stu-id="968e5-200">The following example creates three new network sites, Vietnam, Indonesia, and Singapore in the APAC region:</span></span>

```
New-CsTenantNetworkSite -NetworkSiteID "Vietnam" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Indonesia" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Singapore" -NetworkRegionID "APAC"
```

### <a name="define-network-subnets"></a><span data-ttu-id="968e5-201">Определение подсетей сети</span><span class="sxs-lookup"><span data-stu-id="968e5-201">Define network subnets</span></span>

<span data-ttu-id="968e5-202">Чтобы определить сетевые подсети и связать их с сетевыми сайтами, используйте командлет New-CsTenantNetworkSubnet.</span><span class="sxs-lookup"><span data-stu-id="968e5-202">To define network subnets and associate them to network sites, use the New-CsTenantNetworkSubnet cmdlet.</span></span> <span data-ttu-id="968e5-203">Каждая сетевая подсеть может быть связана только с одним сайтом.</span><span class="sxs-lookup"><span data-stu-id="968e5-203">Each network subnet can only be associated with one site.</span></span> 

```
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>
```

<span data-ttu-id="968e5-204">В приведенном ниже примере определяются три подсети, которые связываются с тремя сетевыми сайтами: Вьетнам, Индонезия и Сингапур.</span><span class="sxs-lookup"><span data-stu-id="968e5-204">The following example defines three network subnets and associates them with the three network sites:  Vietnam, Indonesia, and Singapore:</span></span>

```
New-CsTenantNetworkSubnet -SubnetID 192.168.1.0 -MaskBits 24 -NetworkSiteID “Vietnam”
New-CsTenantNetworkSubnet -SubnetID 192.168.2.0 -MaskBits 24 -NetworkSiteID “Indonesia”
New-CsTenantNetworkSubnet -SubnetID 192.168.3.0 -MaskBits 24 -NetworkSiteID “Singapore”
```

## <a name="define-the-virtual-network-topology"></a><span data-ttu-id="968e5-205">Определение топологии виртуальной сети</span><span class="sxs-lookup"><span data-stu-id="968e5-205">Define the virtual network topology</span></span> 

<span data-ttu-id="968e5-206">Сначала администратор клиента создает новую конфигурацию SBC для каждого связанного SBC с помощью командлета New-CsOnlinePSTNGateway.</span><span class="sxs-lookup"><span data-stu-id="968e5-206">First, the tenant administrator creates a new SBC configuration for each relevant SBC by using the New-CsOnlinePSTNGateway cmdlet.</span></span>
<span data-ttu-id="968e5-207">Администратор клиента определяет топологию виртуальной сети, указав сетевые сайты для объектов шлюза PSTN с помощью командлета Set-CsOnlinePSTNGateway:</span><span class="sxs-lookup"><span data-stu-id="968e5-207">The tenant administrator defines the virtual network topology by specifying the network sites for the PSTN gateway objects using the Set-CsOnlinePSTNGateway cmdlet:</span></span>

```
PS C:\> Set-CsOnlinePSTNGateway -Identity <Identity> -GatewaySiteID <site ID> -MediaBypass <true/false> -BypassMode <Always/OnlyForLocalUsers> -ProxySBC  <proxy SBC FQDN or $null>
```

<span data-ttu-id="968e5-208">Обратите внимание на следующее:</span><span class="sxs-lookup"><span data-stu-id="968e5-208">Note the following:</span></span> 
   - <span data-ttu-id="968e5-209">Если у клиента есть один объект SBC, параметр-ProxySBC должен быть обязательным как обязательно $null или однорангового значения SBC (то есть центрального SBC с помощью централизованной магистрали).</span><span class="sxs-lookup"><span data-stu-id="968e5-209">If the customer has a single SBC, the -ProxySBC parameter must be either mandatory $null or SBC FQDN value (Central SBC with centralized trunks scenario).</span></span>
   - <span data-ttu-id="968e5-210">Параметр-MediaBypass должен иметь значение $true, чтобы обеспечить поддержку локальной оптимизации мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="968e5-210">The -MediaBypass parameter must be set to $true in order to support Local Media Optimization.</span></span>
   - <span data-ttu-id="968e5-211">Если для SBC не задан параметр-BypassMode, заголовки X-MS не будут отправляться.</span><span class="sxs-lookup"><span data-stu-id="968e5-211">If the SBC doesn’t have the -BypassMode parameter set, X-MS headers will not be sent.</span></span> 
   - <span data-ttu-id="968e5-212">Все параметры чувствительны к регистру, поэтому необходимо использовать тот же вариант, который использовался при настройке.</span><span class="sxs-lookup"><span data-stu-id="968e5-212">All parameters are case sensitive so you need to ensure that you use the same case that was used used during setup.</span></span>  <span data-ttu-id="968e5-213">(Например, GatewaySiteID значения "Вьетнам" и "Вьетнам" будут считаться разными сайтами.)</span><span class="sxs-lookup"><span data-stu-id="968e5-213">(For example, GatewaySiteID values “Vietnam” and “vietnam” will be treated as different sites.)</span></span>

<span data-ttu-id="968e5-214">В следующем примере добавляется три SBCs к сетевым сайтам Вьетнам, Индонезия и Сингапур в APAC области с режимом "всегда обходиться".</span><span class="sxs-lookup"><span data-stu-id="968e5-214">The following example adds three SBCs to the network sites Vietnam, Indonesia, and Singapore in the APAC region with mode Always bypass:</span></span>

```
Set-CSOnlinePSTNGateway -Identity “proxysbc.contoso.com” -GatewaySiteID “Singapore” -MediaBypass $true -BypassMode “Always” -ProxySBC $null

Set-CSOnlinePSTNGateway -Identity “VNsbc.contoso.com” -GatewaySiteID “Vietnam” -MediaBypass $true -BypassMode “Always” -ProxySBC “proxysbc.contoso.com”

Set-CSOnlinePSTNGateway -Identity “IDsbc.contoso.com” -GatewaySiteID “Indonesia” -MediaBypass $true -BypassMode “Always” -ProxySBC “proxysbc.contoso.com”
```

<span data-ttu-id="968e5-215">Примечание. для обеспечения бесперебойной работы при одновременной настройке локальной оптимизации и маршрутизации на основе местоположения (LBR) для LBR необходимо включить более подпадающую одноранговую SBCs, задав для параметра GatewaySiteLbrEnabled значение $true для каждого из этих одноименнох SBC-файлов.</span><span class="sxs-lookup"><span data-stu-id="968e5-215">Note: To ensure uninterrupted operations when Local Media Optimization and Location-Based Routing (LBR) are configured at the same time, downstream SBCs must be enabled for LBR by setting the GatewaySiteLbrEnabled parameter to $true for each downstream SBC.</span></span> <span data-ttu-id="968e5-216">(Этот параметр не является обязательным для прокси-сервера SBC).</span><span class="sxs-lookup"><span data-stu-id="968e5-216">(This setting is not mandatory for the proxy SBC.)</span></span>

<span data-ttu-id="968e5-217">В соответствии с приведенными выше сведениями прямая маршрутизация включает три собственных заголовка SIP для приглашений на SIP и повторений, как показано в приведенной ниже таблице.</span><span class="sxs-lookup"><span data-stu-id="968e5-217">Based on the information above, Direct Routing will include three proprietary SIP Headers to SIP Invites and Re-invites as shown  in the following table.</span></span>

<span data-ttu-id="968e5-218">Заголовки X-MS, введенные в прямом маршруте на приглашениях и повторных приглашениях, если определен BypassMode:</span><span class="sxs-lookup"><span data-stu-id="968e5-218">X-MS Headers introduced in Direct Routing on Invites and Re-Invites if BypassMode is defined:</span></span>

| <span data-ttu-id="968e5-219">Имя заголовка</span><span class="sxs-lookup"><span data-stu-id="968e5-219">Header name</span></span> | <span data-ttu-id="968e5-220">Данные</span><span class="sxs-lookup"><span data-stu-id="968e5-220">Values</span></span> | <span data-ttu-id="968e5-221">Комментарии</span><span class="sxs-lookup"><span data-stu-id="968e5-221">Comments</span></span> | 
|:------------|:-------|:-------|
| <span data-ttu-id="968e5-222">X-MS-UserLocation</span><span class="sxs-lookup"><span data-stu-id="968e5-222">X-MS-UserLocation</span></span> | <span data-ttu-id="968e5-223">внутренние и внешние</span><span class="sxs-lookup"><span data-stu-id="968e5-223">internal/external</span></span> | <span data-ttu-id="968e5-224">Указывает, является ли пользователь внутренним или внешним</span><span class="sxs-lookup"><span data-stu-id="968e5-224">Indicates if user is internal or external</span></span> |
| <span data-ttu-id="968e5-225">Запрос-URI INVITE SIP: + 84439263000@VNsbc.contoso.com SIP/2,0</span><span class="sxs-lookup"><span data-stu-id="968e5-225">Request-URI   INVITE sip: +84439263000@VNsbc.contoso.com SIP /2.0</span></span> | <span data-ttu-id="968e5-226">ПОЛНОЕ ДОМЕННОЕ ИМЯ SBC</span><span class="sxs-lookup"><span data-stu-id="968e5-226">SBC FQDN</span></span> | <span data-ttu-id="968e5-227">Полное доменное имя, которое предназначено для вызова, даже если SBC не подключен напрямую к прямой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="968e5-227">The FQDN which is targeted for the call even if the SBC is not directly connected to Direct Routing</span></span> |
| <span data-ttu-id="968e5-228">X-MS-MediaPath</span><span class="sxs-lookup"><span data-stu-id="968e5-228">X-MS-MediaPath</span></span> | <span data-ttu-id="968e5-229">Пример: proxysbc.contoso.com, VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="968e5-229">Example: proxysbc.contoso.com, VNsbc.contoso.com</span></span> | <span data-ttu-id="968e5-230">Порядковый номер SBCs, который должен использоваться для пути к носителю между пользователем и объектом SBC.</span><span class="sxs-lookup"><span data-stu-id="968e5-230">Order of SBCs that should be used for Media path between the user and target SBC.</span></span> <span data-ttu-id="968e5-231">Конечный SBC всегда в последнюю очередь</span><span class="sxs-lookup"><span data-stu-id="968e5-231">The final SBC is always last</span></span> |
| <span data-ttu-id="968e5-232">X-MS-UserSite</span><span class="sxs-lookup"><span data-stu-id="968e5-232">X-MS-UserSite</span></span> | <span data-ttu-id="968e5-233">usersiteID</span><span class="sxs-lookup"><span data-stu-id="968e5-233">usersiteID</span></span> | <span data-ttu-id="968e5-234">Строка, определенная администратором клиента</span><span class="sxs-lookup"><span data-stu-id="968e5-234">String defined by tenant administrator</span></span> |

## <a name="call-flows"></a><span data-ttu-id="968e5-235">Потоки звонков</span><span class="sxs-lookup"><span data-stu-id="968e5-235">Call flows</span></span> 

<span data-ttu-id="968e5-236">Ниже показаны потоки звонков для двух режимов:</span><span class="sxs-lookup"><span data-stu-id="968e5-236">The following shows call flows for two modes:</span></span>

- [<span data-ttu-id="968e5-237">Всегда обходить</span><span class="sxs-lookup"><span data-stu-id="968e5-237">Always Bypass</span></span>](#always-bypass-mode)
- [<span data-ttu-id="968e5-238">Только для локальных пользователей</span><span class="sxs-lookup"><span data-stu-id="968e5-238">Only for local users</span></span>](#only-for-local-users-mode)

### <a name="always-bypass-mode"></a><span data-ttu-id="968e5-239">Режим "всегда пропускать"</span><span class="sxs-lookup"><span data-stu-id="968e5-239">Always Bypass mode</span></span>

<span data-ttu-id="968e5-240">Режим "всегда пропускать" — это самый простой параметр для настройки.</span><span class="sxs-lookup"><span data-stu-id="968e5-240">Always Bypass mode is the simplest option to configure.</span></span> <span data-ttu-id="968e5-241">Администратор клиента может настроить один сайт для всех пользователей и SBCs, если все SBCs достижимы с любого сайта.</span><span class="sxs-lookup"><span data-stu-id="968e5-241">The tenant administrator can configure a single site for all users and SBCs if all SBCs are reachable from any site.</span></span>

<span data-ttu-id="968e5-242">В примерах показан режим "всегда обойти" для следующих сценариев:</span><span class="sxs-lookup"><span data-stu-id="968e5-242">The examples show Always bypass mode for the following scenarios:</span></span>

- [<span data-ttu-id="968e5-243">Исходящие звонки и пользователь находятся в той же папке, что и SBC</span><span class="sxs-lookup"><span data-stu-id="968e5-243">Outbound calls and the user is in the same location as the SBC</span></span>](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [<span data-ttu-id="968e5-244">Входящие звонки и пользователь находятся в той же папке, что и SBC</span><span class="sxs-lookup"><span data-stu-id="968e5-244">Inbound calls and the user is in the same location as the SBC</span></span>](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [<span data-ttu-id="968e5-245">Исходящие звонки и внешние пользователи</span><span class="sxs-lookup"><span data-stu-id="968e5-245">Outbound calls and the user is external</span></span>](#outbound-calls-and-the-user-is-external-with-always-bypass)
- [<span data-ttu-id="968e5-246">Входящие звонки и внешние пользователи</span><span class="sxs-lookup"><span data-stu-id="968e5-246">Inbound calls and the user is external</span></span>](#inbound-calls-and-the-user-is-external-with-always-bypass)

<span data-ttu-id="968e5-247">В приведенной ниже таблице указаны полные доменные имена и IP-адреса, используемые в примерах.</span><span class="sxs-lookup"><span data-stu-id="968e5-247">The following table shows the FQDN and IP addresses used in the examples:</span></span>

| <span data-ttu-id="968e5-248">Полное доменное имя</span><span class="sxs-lookup"><span data-stu-id="968e5-248">FQDN</span></span> | <span data-ttu-id="968e5-249">Внешний IP-адрес для SBC</span><span class="sxs-lookup"><span data-stu-id="968e5-249">SBC external IP address</span></span> | <span data-ttu-id="968e5-250">Внутренний IP-адрес SBC</span><span class="sxs-lookup"><span data-stu-id="968e5-250">SBC internal IP Address</span></span> | <span data-ttu-id="968e5-251">Внутренняя подсеть</span><span class="sxs-lookup"><span data-stu-id="968e5-251">Internal subnet</span></span> | <span data-ttu-id="968e5-252">Местоположение</span><span class="sxs-lookup"><span data-stu-id="968e5-252">Location</span></span> | <span data-ttu-id="968e5-253">Внешний NAT (доверенный IP-адрес)</span><span class="sxs-lookup"><span data-stu-id="968e5-253">External NAT (Trusted IP)</span></span> |
|:------------|:-------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="968e5-254">VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="968e5-254">VNsbc.contoso.com</span></span> | <span data-ttu-id="968e5-255">Нет</span><span class="sxs-lookup"><span data-stu-id="968e5-255">None</span></span> | <span data-ttu-id="968e5-256">192.168.1.5</span><span class="sxs-lookup"><span data-stu-id="968e5-256">192.168.1.5</span></span> | <span data-ttu-id="968e5-257">192.168.1.0/24</span><span class="sxs-lookup"><span data-stu-id="968e5-257">192.168.1.0/24</span></span> | <span data-ttu-id="968e5-258">Вьетнам</span><span class="sxs-lookup"><span data-stu-id="968e5-258">Vietnam</span></span> | <span data-ttu-id="968e5-259">172.16.240.110</span><span class="sxs-lookup"><span data-stu-id="968e5-259">172.16.240.110</span></span> |
| <span data-ttu-id="968e5-260">IDsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="968e5-260">IDsbc.contoso.com</span></span> | <span data-ttu-id="968e5-261">Нет</span><span class="sxs-lookup"><span data-stu-id="968e5-261">None</span></span> | <span data-ttu-id="968e5-262">192.168.2.5</span><span class="sxs-lookup"><span data-stu-id="968e5-262">192.168.2.5</span></span> | <span data-ttu-id="968e5-263">192.168.2.0/24</span><span class="sxs-lookup"><span data-stu-id="968e5-263">192.168.2.0/24</span></span> | <span data-ttu-id="968e5-264">Индонезия</span><span class="sxs-lookup"><span data-stu-id="968e5-264">Indonesia</span></span> | <span data-ttu-id="968e5-265">172.16.240.120</span><span class="sxs-lookup"><span data-stu-id="968e5-265">172.16.240.120</span></span> |
| <span data-ttu-id="968e5-266">proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="968e5-266">proxysbc.contoso.com</span></span> | <span data-ttu-id="968e5-267">172.16.240.133</span><span class="sxs-lookup"><span data-stu-id="968e5-267">172.16.240.133</span></span> | <span data-ttu-id="968e5-268">192.168.3.5</span><span class="sxs-lookup"><span data-stu-id="968e5-268">192.168.3.5</span></span> | <span data-ttu-id="968e5-269">192.168.3.0/24</span><span class="sxs-lookup"><span data-stu-id="968e5-269">192.168.3.0/24</span></span> | <span data-ttu-id="968e5-270">Сингапур</span><span class="sxs-lookup"><span data-stu-id="968e5-270">Singapore</span></span> | <span data-ttu-id="968e5-271">172.16.240.130</span><span class="sxs-lookup"><span data-stu-id="968e5-271">172.16.240.130</span></span> |



#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a><span data-ttu-id="968e5-272">Исходящие звонки и пользователь находятся в той же папке, что и SBC, но не всегда обходить</span><span class="sxs-lookup"><span data-stu-id="968e5-272">Outbound calls and the user is in the same location as the SBC with Always Bypass</span></span>

| <span data-ttu-id="968e5-273">Режиме</span><span class="sxs-lookup"><span data-stu-id="968e5-273">Mode</span></span> |    <span data-ttu-id="968e5-274">Пользователь</span><span class="sxs-lookup"><span data-stu-id="968e5-274">User</span></span> |  <span data-ttu-id="968e5-275">Местоположение</span><span class="sxs-lookup"><span data-stu-id="968e5-275">Location</span></span> |  <span data-ttu-id="968e5-276">Направление звонка</span><span class="sxs-lookup"><span data-stu-id="968e5-276">Call direction</span></span> |
|:------------|:-------|:-------| :-------|
| <span data-ttu-id="968e5-277">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="968e5-277">AlwaysBypass</span></span> |    <span data-ttu-id="968e5-278">Internal</span><span class="sxs-lookup"><span data-stu-id="968e5-278">Internal</span></span> |  <span data-ttu-id="968e5-279">Тот же сайт, что и SBC</span><span class="sxs-lookup"><span data-stu-id="968e5-279">The same site as SBC</span></span> |  <span data-ttu-id="968e5-280">Исходящее</span><span class="sxs-lookup"><span data-stu-id="968e5-280">Outbound</span></span> |

<span data-ttu-id="968e5-281">В следующей таблице приведены сведения о конфигурации и действии конечных пользователей.</span><span class="sxs-lookup"><span data-stu-id="968e5-281">The following table shows the end user configuration and action:</span></span>

| <span data-ttu-id="968e5-282">Физическое расположение пользователя</span><span class="sxs-lookup"><span data-stu-id="968e5-282">User physical location</span></span>| <span data-ttu-id="968e5-283">Пользователь выполняет или получает звонок на номер</span><span class="sxs-lookup"><span data-stu-id="968e5-283">User makes or receives a call to/from number</span></span> | <span data-ttu-id="968e5-284">Номер телефона пользователя</span><span class="sxs-lookup"><span data-stu-id="968e5-284">User phone number</span></span>  | <span data-ttu-id="968e5-285">Политика голосовой маршрутизации в сети</span><span class="sxs-lookup"><span data-stu-id="968e5-285">Online Voice Routing Policy</span></span> | <span data-ttu-id="968e5-286">Режим, настроенный для SBC</span><span class="sxs-lookup"><span data-stu-id="968e5-286">Mode configured for SBC</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="968e5-287">Вьетнам</span><span class="sxs-lookup"><span data-stu-id="968e5-287">Vietnam</span></span> | <span data-ttu-id="968e5-288">+ 84 4 3926 3000</span><span class="sxs-lookup"><span data-stu-id="968e5-288">+84 4 3926 3000</span></span> | <span data-ttu-id="968e5-289">+ 84 4 5555 5555</span><span class="sxs-lookup"><span data-stu-id="968e5-289">+84 4 5555 5555</span></span>   | <span data-ttu-id="968e5-290">Приоритет 1: ^\+84 (\d{9}) $-VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="968e5-290">Priority 1: ^\+84(\d{9})$ -VNsbc.contoso.com</span></span> <br> <span data-ttu-id="968e5-291">Приоритет 2:. \*-proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="968e5-291">Priority 2: .\* - proxysbc.contoso.com</span></span>   | <span data-ttu-id="968e5-292">VNsbc.contoso.com – всегда обходить</span><span class="sxs-lookup"><span data-stu-id="968e5-292">VNsbc.contoso.com – Always Bypass</span></span> <br> <span data-ttu-id="968e5-293">proxysbc.contoso.com – всегда обходить</span><span class="sxs-lookup"><span data-stu-id="968e5-293">proxysbc.contoso.com – Always Bypass</span></span>


<span data-ttu-id="968e5-294">На приведенной ниже схеме показана лестница SIP для исходящего звонка с режимом "всегда минуя", и пользователь в том же расположении, что и SBC.</span><span class="sxs-lookup"><span data-stu-id="968e5-294">The following diagram shows the SIP ladder for an outbound call with Always bypass mode, and the user in the same location as the SBC.</span></span>

<span data-ttu-id="968e5-295">![Диаграмма, показывающая исходящие вызовы](media/direct-routing-media-op-10.png "Исходящие звонки")</span><span class="sxs-lookup"><span data-stu-id="968e5-295">![Diagram showing outbound calls](media/direct-routing-media-op-10.png "Outbound calls")</span></span>

<span data-ttu-id="968e5-296">В таблице ниже указаны заголовки X-MS, отправленные с помощью Direct Routing.</span><span class="sxs-lookup"><span data-stu-id="968e5-296">The following table shows the X-MS headers sent by Direct Routing:</span></span>

| <span data-ttu-id="968e5-297">Параметр</span><span class="sxs-lookup"><span data-stu-id="968e5-297">Parameter</span></span> | <span data-ttu-id="968e5-298">Пояснение</span><span class="sxs-lookup"><span data-stu-id="968e5-298">Explanation</span></span> |
|:------------|:-------|
| <span data-ttu-id="968e5-299">Пригласить + 8443926300@VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="968e5-299">Invite +8443926300@VNsbc.contoso.com</span></span> | <span data-ttu-id="968e5-300">Целевое имя объекта SBC, определенного в политике голосовой маршрутизации через Интернет, отправляется в URI запроса</span><span class="sxs-lookup"><span data-stu-id="968e5-300">The target name of the SBC as defined in the Online Voice Routing Policy is sent in the Request URI</span></span> | 
| <span data-ttu-id="968e5-301">X-MS-UserLocation: Internal</span><span class="sxs-lookup"><span data-stu-id="968e5-301">X-MS-UserLocation: internal</span></span> | <span data-ttu-id="968e5-302">Поле, которое указывает, что пользователь входит в корпоративную сеть</span><span class="sxs-lookup"><span data-stu-id="968e5-302">The field indicated that user is located inside the corporate network</span></span> |
| <span data-ttu-id="968e5-303">X-MS-MediaPath: VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="968e5-303">X-MS-MediaPath: VNsbc.contoso.com</span></span> |   <span data-ttu-id="968e5-304">Указывает, какой SBC — клиент должен пройти по целевому объекту SBC.</span><span class="sxs-lookup"><span data-stu-id="968e5-304">Specifies which SBC the client must traverse to the target SBC.</span></span> <span data-ttu-id="968e5-305">В этом случае, так как мы всегда обходите, а клиент является внутренним конечным именем, которое отправляется в заголовке как единственное имя.</span><span class="sxs-lookup"><span data-stu-id="968e5-305">In this case as we have Always Bypass, and the client is internal the target name sent as the only name in the header.</span></span> | 
|<span data-ttu-id="968e5-306">X-MS-UserSite: Вьетнам</span><span class="sxs-lookup"><span data-stu-id="968e5-306">X-MS-UserSite: Vietnam</span></span> |   <span data-ttu-id="968e5-307">Поле, указываемое на сайте, на котором находится пользователь.</span><span class="sxs-lookup"><span data-stu-id="968e5-307">The field indicated within the site the user is located.</span></span> |


#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a><span data-ttu-id="968e5-308">Входящие звонки и пользователь находятся в той же папке, что и SBC, но не всегда пропускать</span><span class="sxs-lookup"><span data-stu-id="968e5-308">Inbound calls and the user is in the same location as the SBC with Always Bypass</span></span>

| <span data-ttu-id="968e5-309">Режиме</span><span class="sxs-lookup"><span data-stu-id="968e5-309">Mode</span></span> |    <span data-ttu-id="968e5-310">Пользователь</span><span class="sxs-lookup"><span data-stu-id="968e5-310">User</span></span> |  <span data-ttu-id="968e5-311">Местоположение</span><span class="sxs-lookup"><span data-stu-id="968e5-311">Location</span></span> |  <span data-ttu-id="968e5-312">Направление звонка</span><span class="sxs-lookup"><span data-stu-id="968e5-312">Call direction</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="968e5-313">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="968e5-313">AlwaysBypass</span></span> |    <span data-ttu-id="968e5-314">Internal</span><span class="sxs-lookup"><span data-stu-id="968e5-314">Internal</span></span> | <span data-ttu-id="968e5-315">Тот же сайт, что и SBC</span><span class="sxs-lookup"><span data-stu-id="968e5-315">The same site as SBC</span></span> | <span data-ttu-id="968e5-316">443</span><span class="sxs-lookup"><span data-stu-id="968e5-316">Inbound</span></span> |


<span data-ttu-id="968e5-317">Во входящем звонке расположение пользователя неизвестно, и SBC должен быть указан в том месте, где находится пользователь.</span><span class="sxs-lookup"><span data-stu-id="968e5-317">On an inbound call, the location of the user is unknown, and the SBC must guess where the user is.</span></span> <span data-ttu-id="968e5-318">Если предположение не подходит, потребуется повторно пригласить приглашение.</span><span class="sxs-lookup"><span data-stu-id="968e5-318">If the guess is not correct, a re-invite will be required.</span></span> <span data-ttu-id="968e5-319">В этом случае подразумевается, что пользователь является внутренним, мультимедиа может напрямую перетекать, и дальнейшие действия не требуются (повторно пригласить).</span><span class="sxs-lookup"><span data-stu-id="968e5-319">This case assumes user is internal, media can flow directly, and no further actions are required (re-invite).</span></span>
<span data-ttu-id="968e5-320">SBC, подключенный к прямой маршрутизации, выводит на экран исходное расположение SBC, предоставляя поля "запись" и "контакт".</span><span class="sxs-lookup"><span data-stu-id="968e5-320">The SBC connected to the Direct Routing service reports the originating SBC location by providing Record-Route and Contact fields.</span></span> <span data-ttu-id="968e5-321">На основе этих полей путь к носителю рассчитывается посредством прямой маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="968e5-321">Based on these fields, the media path is calculated by Direct Routing.</span></span>

<span data-ttu-id="968e5-322">Примечание. Учитывая, что пользователь может иметь несколько конечных точек, поддержка 183 невозможна.</span><span class="sxs-lookup"><span data-stu-id="968e5-322">Note: Given that a user can have multiple endpoints, support of 183 is not possible.</span></span> <span data-ttu-id="968e5-323">В этом случае прямая маршрутизация всегда будет использовать 180 звонков.</span><span class="sxs-lookup"><span data-stu-id="968e5-323">The Direct Routing will always use 180 Ringing in this case.</span></span> 

<span data-ttu-id="968e5-324">На приведенной ниже схеме показана лестница SIP для входящего звонка в режиме AlwaysBypass, и пользователь находится в том же расположении, что и SBC.</span><span class="sxs-lookup"><span data-stu-id="968e5-324">The following diagram shows the SIP ladder for in inbound call with AlwaysBypass mode, and the user is in the same location as the SBC.</span></span>

![Схема, на которой показана лестница SIP](media/direct-routing-media-op-11.png)


#### <a name="outbound-calls-and-the-user-is-external-with-always-bypass"></a><span data-ttu-id="968e5-326">Исходящие звонки, а также пользователь с внешними пользователями с помощью функций "всегда минуя"</span><span class="sxs-lookup"><span data-stu-id="968e5-326">Outbound calls and the user is external with Always Bypass</span></span>

| <span data-ttu-id="968e5-327">Режиме</span><span class="sxs-lookup"><span data-stu-id="968e5-327">Mode</span></span> |    <span data-ttu-id="968e5-328">Пользователь</span><span class="sxs-lookup"><span data-stu-id="968e5-328">User</span></span> |  <span data-ttu-id="968e5-329">Сайт</span><span class="sxs-lookup"><span data-stu-id="968e5-329">Site</span></span> |  <span data-ttu-id="968e5-330">Направление звонка</span><span class="sxs-lookup"><span data-stu-id="968e5-330">Call direction</span></span>
|:------------|:-------|:-------|:-------|
<span data-ttu-id="968e5-331">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="968e5-331">AlwaysBypass</span></span> |  <span data-ttu-id="968e5-332">Внешняя</span><span class="sxs-lookup"><span data-stu-id="968e5-332">External</span></span> |  <span data-ttu-id="968e5-333">Н/Д</span><span class="sxs-lookup"><span data-stu-id="968e5-333">N/A</span></span> | <span data-ttu-id="968e5-334">Исходящее</span><span class="sxs-lookup"><span data-stu-id="968e5-334">Outbound</span></span> |


<span data-ttu-id="968e5-335">На приведенной ниже схеме показана лестница SIP для исходящего звонка с использованием режима AlwaysBypass, и пользователь является внешним:</span><span class="sxs-lookup"><span data-stu-id="968e5-335">The following diagram shows the SIP ladder for an outbound call with AlwaysBypass mode, and the user is external:</span></span>

![Схема, на которой показана лестница SIP](media/direct-routing-media-op-12.png)

<span data-ttu-id="968e5-337">В приведенной ниже таблице указаны заголовки X-MS, отправленные службой прямой маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="968e5-337">The following table shows the X-MS headers sent by the Direct Routing service:</span></span>

| <span data-ttu-id="968e5-338">Параметр</span><span class="sxs-lookup"><span data-stu-id="968e5-338">Parameter</span></span> |   <span data-ttu-id="968e5-339">Пояснение</span><span class="sxs-lookup"><span data-stu-id="968e5-339">Explanation</span></span> |
|:------------|:-------|
|<span data-ttu-id="968e5-340">Пригласить + 8443926300@VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="968e5-340">Invite +8443926300@VNsbc.contoso.com</span></span> | <span data-ttu-id="968e5-341">Целевое имя объекта SBC, определенного в политике голосовой маршрутизации через Интернет, отправляется в URI запроса.</span><span class="sxs-lookup"><span data-stu-id="968e5-341">The target name of the SBC as defined in the Online Voice Routing Policy is sent in the Request URI.</span></span>|
| <span data-ttu-id="968e5-342">X-MS-UserLocation: External</span><span class="sxs-lookup"><span data-stu-id="968e5-342">X-MS-UserLocation: external</span></span> | <span data-ttu-id="968e5-343">Поле, в котором указано, что пользователь находится за пределами корпоративной сети.</span><span class="sxs-lookup"><span data-stu-id="968e5-343">The field indicated that user is located outside the corporate network.</span></span> |
| <span data-ttu-id="968e5-344">X-MS-MediaPath: proxysbc.contoso.com, VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="968e5-344">X-MS-MediaPath: proxysbc.contoso.com, VNsbc.contoso.com</span></span>    | <span data-ttu-id="968e5-345">Указывает, какой SBC — клиент должен пройти по целевому объекту SBC.</span><span class="sxs-lookup"><span data-stu-id="968e5-345">Specifies which SBC the client must traverse to the target SBC.</span></span> <span data-ttu-id="968e5-346">В этом случае, так как мы всегда обходите, а клиент внешне.</span><span class="sxs-lookup"><span data-stu-id="968e5-346">In this case as we have Always Bypass, and the client is external.</span></span> |

#### <a name="inbound-calls-and-the-user-is-external-with-always-bypass"></a><span data-ttu-id="968e5-347">Входящие звонки и пользователь являются внешними по отношению к параметру "всегда минуя"</span><span class="sxs-lookup"><span data-stu-id="968e5-347">Inbound calls and the user is external with Always Bypass</span></span>

| <span data-ttu-id="968e5-348">Режиме</span><span class="sxs-lookup"><span data-stu-id="968e5-348">Mode</span></span> | <span data-ttu-id="968e5-349">Пользователь</span><span class="sxs-lookup"><span data-stu-id="968e5-349">User</span></span> | <span data-ttu-id="968e5-350">Сайт</span><span class="sxs-lookup"><span data-stu-id="968e5-350">Site</span></span> |  <span data-ttu-id="968e5-351">Направление звонка</span><span class="sxs-lookup"><span data-stu-id="968e5-351">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
<span data-ttu-id="968e5-352">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="968e5-352">AlwaysBypass</span></span> |  <span data-ttu-id="968e5-353">Внешняя</span><span class="sxs-lookup"><span data-stu-id="968e5-353">External</span></span> |  <span data-ttu-id="968e5-354">Н/Д</span><span class="sxs-lookup"><span data-stu-id="968e5-354">N/A</span></span> |   <span data-ttu-id="968e5-355">443</span><span class="sxs-lookup"><span data-stu-id="968e5-355">Inbound</span></span> |

<span data-ttu-id="968e5-356">Для входящего звонка SBC, подключенный к прямой маршрутизации, должен отправить повторное приглашение (по умолчанию предлагаются пользовательские кандидаты на носители), если расположение пользователя является внешним.</span><span class="sxs-lookup"><span data-stu-id="968e5-356">For an inbound call, the SBC connected to Direct Routing needs to send a re-invite (by default, local media candidates are always offered) if the location of the user is external.</span></span>  <span data-ttu-id="968e5-357">X-MediaPath вычисляется на основе маршрута записи и заданного пользователем SBC.</span><span class="sxs-lookup"><span data-stu-id="968e5-357">The X-MediaPath is calculated based on Record-Route and the SBC user specified.</span></span>

<span data-ttu-id="968e5-358">На приведенной ниже схеме показана лестница SIP для входящего звонка с использованием режима AlwaysBypass, и пользователь является внешним.</span><span class="sxs-lookup"><span data-stu-id="968e5-358">The following diagram shows the SIP ladder for an inbound call with AlwaysBypass mode, and the user is external.</span></span>

![Схема, на которой показана лестница SIP](media/direct-routing-media-op-13.png)


### <a name="only-for-local-users-mode"></a><span data-ttu-id="968e5-360">Только в режиме локальных пользователей</span><span class="sxs-lookup"><span data-stu-id="968e5-360">Only for local users mode</span></span>

<span data-ttu-id="968e5-361">Локальные мультимедийные варианты целевого SBC будут предлагаться только в том случае, если пользователь находится в том же расположении, что и SBC.</span><span class="sxs-lookup"><span data-stu-id="968e5-361">Local media candidates of the target SBC will be offered only if a user is in the same location as the SBC.</span></span> <span data-ttu-id="968e5-362">Во всех остальных случаях мультимедиа будет проходить через внутренний или внешний IP-адрес объекта SBC прокси.</span><span class="sxs-lookup"><span data-stu-id="968e5-362">In all other cases, media will flow through either an internal or external IP of the proxy SBC.</span></span>

<span data-ttu-id="968e5-363">Ниже описаны сценарии.</span><span class="sxs-lookup"><span data-stu-id="968e5-363">The following scenarios are described:</span></span>

- [<span data-ttu-id="968e5-364">Исходящие звонки и пользователь находятся в той же папке, что и SBC</span><span class="sxs-lookup"><span data-stu-id="968e5-364">Outbound calls and the user is in the same location as the SBC</span></span>](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [<span data-ttu-id="968e5-365">Входящие звонки и пользователь находятся в той же папке, что и SBC</span><span class="sxs-lookup"><span data-stu-id="968e5-365">Inbound calls and the user is in the same location as the SBC</span></span>](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [<span data-ttu-id="968e5-366">Пользователь не находится в том же месте, что и SBC, но входит в корпоративную сеть</span><span class="sxs-lookup"><span data-stu-id="968e5-366">User is not at the same location as the SBC but is in the corporate network</span></span>](#user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users)
- [<span data-ttu-id="968e5-367">Входящие звонки и пользователь являются внутренними, но не находятся в том же месте, что и SBC.</span><span class="sxs-lookup"><span data-stu-id="968e5-367">Inbound calls and the user is internal but is not at the same location as the SBC</span></span>](#inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users)

<span data-ttu-id="968e5-368">В приведенной ниже таблице показано, как настроить конфигурацию и действие конечного пользователя.</span><span class="sxs-lookup"><span data-stu-id="968e5-368">The following table shows end user configuration and action:</span></span>

| <span data-ttu-id="968e5-369">Физическое расположение пользователя</span><span class="sxs-lookup"><span data-stu-id="968e5-369">User physical location</span></span> |  <span data-ttu-id="968e5-370">Пользователь выполняет или получает звонок на номер</span><span class="sxs-lookup"><span data-stu-id="968e5-370">User makes or receives a call to/from number</span></span> |  <span data-ttu-id="968e5-371">Номер телефона пользователя</span><span class="sxs-lookup"><span data-stu-id="968e5-371">User phone number</span></span> | <span data-ttu-id="968e5-372">Политика голосовой маршрутизации в сети</span><span class="sxs-lookup"><span data-stu-id="968e5-372">Online Voice Routing Policy</span></span> |   <span data-ttu-id="968e5-373">Режим, настроенный для SBC</span><span class="sxs-lookup"><span data-stu-id="968e5-373">Mode configured for SBC</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="968e5-374">Вьетнам</span><span class="sxs-lookup"><span data-stu-id="968e5-374">Vietnam</span></span> | <span data-ttu-id="968e5-375">+ 84 4 3926 3000</span><span class="sxs-lookup"><span data-stu-id="968e5-375">+84 4 3926  3000</span></span> |  <span data-ttu-id="968e5-376">+ 84 4 5555 5555</span><span class="sxs-lookup"><span data-stu-id="968e5-376">+84 4 5555 5555</span></span> | <span data-ttu-id="968e5-377">Приоритет 1: ^\+84 (\d{9}) $-VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="968e5-377">Priority 1: ^\+84(\d{9})$ -VNsbc.contoso.com</span></span> <br> <span data-ttu-id="968e5-378">Приоритет 2:. \*-proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="968e5-378">Priority 2: .\* - proxysbc.contoso.com</span></span> | <span data-ttu-id="968e5-379">VNsbc.contoso.com — OnlyForLocalUsers Proxysbc.contoso.com — всегда обходить</span><span class="sxs-lookup"><span data-stu-id="968e5-379">VNsbc.contoso.com – OnlyForLocalUsers Proxysbc.contoso.com – Always Bypass</span></span> |

#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="968e5-380">Исходящие звонки и пользователь находятся в той же папке, что и SBC только для локальных пользователей.</span><span class="sxs-lookup"><span data-stu-id="968e5-380">Outbound calls and the user is in the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="968e5-381">Режиме</span><span class="sxs-lookup"><span data-stu-id="968e5-381">Mode</span></span> | <span data-ttu-id="968e5-382">Пользователь</span><span class="sxs-lookup"><span data-stu-id="968e5-382">User</span></span> | <span data-ttu-id="968e5-383">Сайт</span><span class="sxs-lookup"><span data-stu-id="968e5-383">Site</span></span> | <span data-ttu-id="968e5-384">Направление звонка</span><span class="sxs-lookup"><span data-stu-id="968e5-384">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="968e5-385">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="968e5-385">OnlyForLocalUsers</span></span> |   <span data-ttu-id="968e5-386">Internal</span><span class="sxs-lookup"><span data-stu-id="968e5-386">Internal</span></span> |<span data-ttu-id="968e5-387">То же, что и SBC</span><span class="sxs-lookup"><span data-stu-id="968e5-387">Same as SBC</span></span>   | <span data-ttu-id="968e5-388">Исходящее</span><span class="sxs-lookup"><span data-stu-id="968e5-388">Outbound</span></span> |

<span data-ttu-id="968e5-389">На приведенной ниже схеме показан исходящий вызов с использованием режима OnlyForLocalUsers, и пользователь находится в том же расположении, что и SBC.</span><span class="sxs-lookup"><span data-stu-id="968e5-389">The following diagram shows an outbound call with OnlyForLocalUsers mode, and the user is in the same location as the SBC.</span></span> <span data-ttu-id="968e5-390">Это тот же поток, который показан в [исходящих звонках, если пользователь находится в том же месте, что и SBC](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span><span class="sxs-lookup"><span data-stu-id="968e5-390">This is the same flow shown in [Outbound calls when the user is in the same location as the SBC](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span></span>

![Схема, на которой показана лестница SIP](media/direct-routing-media-op-14.png)


#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="968e5-392">Входящие звонки и пользователь находятся в той же папке, что и SBC только для локальных пользователей.</span><span class="sxs-lookup"><span data-stu-id="968e5-392">Inbound calls and the user is in the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="968e5-393">Режиме</span><span class="sxs-lookup"><span data-stu-id="968e5-393">Mode</span></span> | <span data-ttu-id="968e5-394">Пользователь</span><span class="sxs-lookup"><span data-stu-id="968e5-394">User</span></span> | <span data-ttu-id="968e5-395">Сайт</span><span class="sxs-lookup"><span data-stu-id="968e5-395">Site</span></span> | <span data-ttu-id="968e5-396">Направление звонка</span><span class="sxs-lookup"><span data-stu-id="968e5-396">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="968e5-397">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="968e5-397">OnlyForLocalUsers</span></span> |   <span data-ttu-id="968e5-398">Internal</span><span class="sxs-lookup"><span data-stu-id="968e5-398">Internal</span></span> | <span data-ttu-id="968e5-399">То же, что и SBC</span><span class="sxs-lookup"><span data-stu-id="968e5-399">Same as SBC</span></span> | <span data-ttu-id="968e5-400">443</span><span class="sxs-lookup"><span data-stu-id="968e5-400">Inbound</span></span> |

<span data-ttu-id="968e5-401">На приведенной ниже схеме показан входящий вызов с использованием режима OnlyForLocalUsers, и пользователь находится в том же расположении, что и SBC.</span><span class="sxs-lookup"><span data-stu-id="968e5-401">The following diagram shows an inbound call with OnlyForLocalUsers mode, and the user is in the same location as the SBC.</span></span> <span data-ttu-id="968e5-402">Это тот же поток, что и во [входящих звонках, когда пользователь находится в том же месте, что и SBC](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span><span class="sxs-lookup"><span data-stu-id="968e5-402">This is the same flow as shown in [Inbound calls when the user is in the same location as the SBC](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span></span>

![Схема, на которой показана лестница SIP](media/direct-routing-media-op-15.png)


#### <a name="user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users"></a><span data-ttu-id="968e5-404">Пользователь не находится в том же месте, что и SBC, но входит в корпоративную сеть только для локальных пользователей.</span><span class="sxs-lookup"><span data-stu-id="968e5-404">User is not at the same location as the SBC but is in the corporate network with Only for local users</span></span>

| <span data-ttu-id="968e5-405">Режиме</span><span class="sxs-lookup"><span data-stu-id="968e5-405">Mode</span></span> | <span data-ttu-id="968e5-406">Пользователь</span><span class="sxs-lookup"><span data-stu-id="968e5-406">User</span></span> | <span data-ttu-id="968e5-407">Сайт</span><span class="sxs-lookup"><span data-stu-id="968e5-407">Site</span></span> |<span data-ttu-id="968e5-408">Направление звонка</span><span class="sxs-lookup"><span data-stu-id="968e5-408">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="968e5-409">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="968e5-409">OnlyForLocalUsers</span></span>  | <span data-ttu-id="968e5-410">Internal</span><span class="sxs-lookup"><span data-stu-id="968e5-410">Internal</span></span> |   <span data-ttu-id="968e5-411">Отличается от SBC</span><span class="sxs-lookup"><span data-stu-id="968e5-411">Different from SBC</span></span> | <span data-ttu-id="968e5-412">Исходящее</span><span class="sxs-lookup"><span data-stu-id="968e5-412">Outbound</span></span> |

<span data-ttu-id="968e5-413">Прямая маршрутизация рассчитывает X-MediaPath в зависимости от того, где находится указанное расположение пользователя и режима, настроенных на SBC.</span><span class="sxs-lookup"><span data-stu-id="968e5-413">Direct routing calculates X-MediaPath based on the reported location of the user and mode configured on the SBC.</span></span>


<span data-ttu-id="968e5-414">На приведенной ниже схеме показан исходящий вызов с использованием режима OnlyForLocalUsers и внутренний пользователь, который не находится в том же месте, что и SBC.</span><span class="sxs-lookup"><span data-stu-id="968e5-414">The following diagram shows an outbound call with OnlyForLocalUsers mode, and an internal user who is not at the same location as the SBC.</span></span>

![Схема, на которой показана лестница SIP](media/direct-routing-media-op-16.png)


#### <a name="inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="968e5-416">Входящий звонок и пользователь является внутренним, но не в том же месте, что и SBC только для локальных пользователей.</span><span class="sxs-lookup"><span data-stu-id="968e5-416">Inbound call and the user is internal but is not at the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="968e5-417">Режиме</span><span class="sxs-lookup"><span data-stu-id="968e5-417">Mode</span></span> |    <span data-ttu-id="968e5-418">Пользователь</span><span class="sxs-lookup"><span data-stu-id="968e5-418">User</span></span> |  <span data-ttu-id="968e5-419">Сайт</span><span class="sxs-lookup"><span data-stu-id="968e5-419">Site</span></span> |  <span data-ttu-id="968e5-420">Направление звонка</span><span class="sxs-lookup"><span data-stu-id="968e5-420">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="968e5-421">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="968e5-421">OnlyForLocalUsers</span></span> | <span data-ttu-id="968e5-422">Internal</span><span class="sxs-lookup"><span data-stu-id="968e5-422">Internal</span></span> |    <span data-ttu-id="968e5-423">Отличается от SBC</span><span class="sxs-lookup"><span data-stu-id="968e5-423">Different from SBC</span></span> |    <span data-ttu-id="968e5-424">443</span><span class="sxs-lookup"><span data-stu-id="968e5-424">Inbound</span></span> |

<span data-ttu-id="968e5-425">На приведенной ниже схеме показан входящий вызов с использованием режима OnlyForLocalUsers и внутренний пользователь, который не находится в том же месте, что и SBC.</span><span class="sxs-lookup"><span data-stu-id="968e5-425">The following diagram shows an inbound call with OnlyForLocalUsers mode, and an internal user who is not at the same location as the SBC.</span></span>

![Схема, на которой показана лестница SIP](media/direct-routing-media-op-17.png)









