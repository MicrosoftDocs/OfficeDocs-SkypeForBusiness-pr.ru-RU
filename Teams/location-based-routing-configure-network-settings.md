---
title: Настройка параметров сети — маршруты на основе расположения
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.reviewer: roykuntz
audience: admin
ms.service: msteams
search.appverid: MET150
description: Узнайте, как создавать и создавать сетевые регионы, сайты и подсети для Location-Based маршрутизации для прямой маршрутизации.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: a7dd707a6066cfe9a8dfcbcc9b3ae36d450d1dd1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822949"
---
# <a name="configure-network-settings-for-location-based-routing"></a><span data-ttu-id="4d529-103">Настройка параметров сети для маршрутизации на основе расположения</span><span class="sxs-lookup"><span data-stu-id="4d529-103">Configure network settings for Location-Based Routing</span></span>

<span data-ttu-id="4d529-104">Если вы еще не сделали [](location-based-routing-plan.md) этого, ознакомьтесь с Location-Based перенастройки плана прямой маршрутии, чтобы ознакомиться с другими действиями, которые необходимо предпринять, прежде чем настраивать параметры сети для Location-Based маршрутии.</span><span class="sxs-lookup"><span data-stu-id="4d529-104">If you haven't already done so, read [Plan Location-Based Routing for Direct Routing](location-based-routing-plan.md) to review other steps you'll need to take before you configure network settings for Location-Based Routing.</span></span>

<span data-ttu-id="4d529-105">В этой статье описано, как настроить параметры сети для Location-Based маршрутов.</span><span class="sxs-lookup"><span data-stu-id="4d529-105">This article describes how to configure network settings for Location-Based Routing.</span></span> <span data-ttu-id="4d529-106">После развертывания телефонная система прямой маршрутизации в организации необходимо создать и настроить сетевые регионы, сетевые сайты и сетевые подсети.</span><span class="sxs-lookup"><span data-stu-id="4d529-106">After you deploy Phone System Direct Routing in your organization, the next steps are to create and set up network regions, network sites, and network subnets.</span></span>

## <a name="define-network-regions"></a><span data-ttu-id="4d529-107">Определение сетевых регионов</span><span class="sxs-lookup"><span data-stu-id="4d529-107">Define network regions</span></span>

<span data-ttu-id="4d529-108">Сетевой регион содержит набор сетевых сайтов и пересекает различные части сети по нескольким географическим областям.</span><span class="sxs-lookup"><span data-stu-id="4d529-108">A network region contains a collection of network sites and interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="4d529-109">По шагам по настройке сетевых регионов перейдите в управление топологией сети для облачных функций в [Teams.](manage-your-network-topology.md)</span><span class="sxs-lookup"><span data-stu-id="4d529-109">For steps on how to configure network regions, go to [Manage your network topology for cloud features in Teams](manage-your-network-topology.md).</span></span>

## <a name="define-network-sites"></a><span data-ttu-id="4d529-110">Определение сетевых сайтов</span><span class="sxs-lookup"><span data-stu-id="4d529-110">Define network sites</span></span>

<span data-ttu-id="4d529-111">Сетевой сайт — это место, где в вашей организации есть физическое расположение, например офис, набор зданий или комплекс зданий.</span><span class="sxs-lookup"><span data-stu-id="4d529-111">A network site represents a location where your organization has a physical venue, such as an office, a set of buildings, or a campus.</span></span> <span data-ttu-id="4d529-112">Каждый сетевой сайт в топологии необходимо связать с сетевым регионом.</span><span class="sxs-lookup"><span data-stu-id="4d529-112">You must associate each network site in your topology with a network region.</span></span> <span data-ttu-id="4d529-113">По шагам по настройке сетевых сайтов см. управление топологией сети для облачных функций [в Teams.](manage-your-network-topology.md)</span><span class="sxs-lookup"><span data-stu-id="4d529-113">For steps on how to configure network sites, see [Manage your network topology for cloud features in Teams](manage-your-network-topology.md).</span></span>

<span data-ttu-id="4d529-114">Для Location-Based маршрутов лучше всего создать отдельный сайт для каждого расположения с уникальным подключением к ОКП.</span><span class="sxs-lookup"><span data-stu-id="4d529-114">A best practice for Location-Based Routing is to create a separate site for each location that has unique PSTN connectivity.</span></span> <span data-ttu-id="4d529-115">Вы можете создать сайт, на который включена Location-Based маршруты, или сайт, для Location-Based маршрутов.</span><span class="sxs-lookup"><span data-stu-id="4d529-115">You can create a site that's enabled for Location-Based Routing or a site that's not enabled for Location-Based Routing.</span></span> <span data-ttu-id="4d529-116">Например, может потребоваться создать сайт, для которого не включена маршрутная Location-Based, чтобы позволить пользователям, у которых включена маршрутная Location-Based маршрутизов, звонить по ННП при их роуминге на этот сайт.</span><span class="sxs-lookup"><span data-stu-id="4d529-116">For example, you may want to create a site that's not enabled for Location-Based Routing to allow users who are enabled for Location-Based Routing to make PSTN calls when they roam to that site.</span></span>

## <a name="define-network-subnets"></a><span data-ttu-id="4d529-117">Определение сетевых подсетей</span><span class="sxs-lookup"><span data-stu-id="4d529-117">Define network subnets</span></span>

<span data-ttu-id="4d529-118">Каждая подсеть должна быть связана с определенным сетевым сайтом.</span><span class="sxs-lookup"><span data-stu-id="4d529-118">Each subnet must be associated with a specific network site.</span></span> <span data-ttu-id="4d529-119">Вы можете связать несколько подсетей с одинаковым сетевым сайтом, но нельзя связать несколько сайтов с одной и той же подсетью.</span><span class="sxs-lookup"><span data-stu-id="4d529-119">You can associate multiple subnets with the same network site but you can't associate multiple sites with the same subnet.</span></span> <span data-ttu-id="4d529-120">Действия по настройке сетевых подсетей можно найти в этой [Teams.](manage-your-network-topology.md)</span><span class="sxs-lookup"><span data-stu-id="4d529-120">For steps on how to configure network subnets, go to  [Manage your network topology for cloud features in Teams](manage-your-network-topology.md).</span></span>

<span data-ttu-id="4d529-121">Для Location-Based маршрутизации необходимо определить и связать IP-подсети, в которых Teams конечные точки могут подключаться к сети, и связать их с определенной сетью для применения платного обхода.</span><span class="sxs-lookup"><span data-stu-id="4d529-121">For Location-Based Routing, IP subnets at the location where Teams endpoints can connect to the network must be defined and associated to a defined network to enforce toll bypass.</span></span> <span data-ttu-id="4d529-122">Эта связь подсетей позволяет Location-Based маршрутизации для определения географических конечных точек, чтобы определить, следует ли разрешить звонок по ОКП.</span><span class="sxs-lookup"><span data-stu-id="4d529-122">This association of subnets enables Location-Based Routing to locate the endpoints geographically to determine whether a given PSTN call should be allowed.</span></span> <span data-ttu-id="4d529-123">Поддерживаются как подсети IPv6, так и IPv4.</span><span class="sxs-lookup"><span data-stu-id="4d529-123">Both IPv6 and IPv4 subnets are supported.</span></span> <span data-ttu-id="4d529-124">При определении того, Teams ли на сайте расположена конечная точка, Location-Based сначала проверяет наличие совпадающих IPv6-адресов.</span><span class="sxs-lookup"><span data-stu-id="4d529-124">When determining whether a Teams endpoint is located at a site, Location-Based Routing first checks for a matching IPv6 address.</span></span> <span data-ttu-id="4d529-125">Если IPv6-адреса нет, Location-Based Routing проверяет наличие IPv4-адреса.</span><span class="sxs-lookup"><span data-stu-id="4d529-125">If an IPv6 address isn't present, Location-Based Routing checks for an IPv4 address.</span></span>

## <a name="define-trusted-ip-addresses-external-subnets"></a><span data-ttu-id="4d529-126">Определение доверенных IP-адресов (внешних подсетей)</span><span class="sxs-lookup"><span data-stu-id="4d529-126">Define trusted IP addresses (external subnets)</span></span>

<span data-ttu-id="4d529-127">Надежные IP-адреса — это внешние IP-адреса корпоративной сети, которые используются для определения того, находится ли конечная точка пользователя в корпоративной сети.</span><span class="sxs-lookup"><span data-stu-id="4d529-127">Trusted IP addresses are the internet external IP addresses of the enterprise network and are used to determine whether the user's endpoint is inside the corporate network.</span></span> <span data-ttu-id="4d529-128">Действия по настройке доверенных IP-адресов можно найти в этой [Teams.](manage-your-network-topology.md)</span><span class="sxs-lookup"><span data-stu-id="4d529-128">For steps on how to configure trusted IP addresses, go to  [Manage your network topology for cloud features in Teams](manage-your-network-topology.md).</span></span>

<span data-ttu-id="4d529-129">Если внешний IP-адрес пользователя совпадает с IP-адресом из списка надежных IP-адресов, Location-Based Routing проверяет внутреннюю подсеть, в которой находится конечная точка пользователя.</span><span class="sxs-lookup"><span data-stu-id="4d529-129">If the user's external IP address matches an IP address that's in the trusted IP address list, Location-Based Routing checks to determine the internal subnet where the user's endpoint is located.</span></span> <span data-ttu-id="4d529-130">Если внешний IP-адрес пользователя не совпадает с IP-адресом, определенным в списке надежных IP-адресов, конечная точка классифицируется как неизвестная, а все звонки через ПСПУ или от пользователя, у которого включена Location-Based маршруты блокируются.</span><span class="sxs-lookup"><span data-stu-id="4d529-130">If the user's external IP address doesn't match any IP address that's defined in the trusted IP address list, the endpoint is classified as being at an unknown location and any PSTN calls to or from a user who is enabled for Location-Based Routing are blocked.</span></span>

## <a name="next-steps"></a><span data-ttu-id="4d529-131">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="4d529-131">Next steps</span></span>

<span data-ttu-id="4d529-132">Перейдите [к Location-Based прямой маршрутии.](location-based-routing-enable.md)</span><span class="sxs-lookup"><span data-stu-id="4d529-132">Go to [Enable Location-Based Routing for Direct Routing](location-based-routing-enable.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="4d529-133">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="4d529-133">Related topics</span></span>

- [<span data-ttu-id="4d529-134">Параметры сети для облачных функций голосовой связи в Teams</span><span class="sxs-lookup"><span data-stu-id="4d529-134">Network settings for cloud voice features in Teams</span></span>](cloud-voice-network-settings.md)
