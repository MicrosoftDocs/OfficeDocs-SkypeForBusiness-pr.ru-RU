---
title: Настройка параметров сети — маршрутия на основе расположения
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.reviewer: roykuntz
audience: admin
ms.service: msteams
search.appverid: MET150
description: Узнайте, как создавать и настроить сетевые регионы, сайты и подсети для Location-Based маршрутизации для прямой маршрутизации.
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
# <a name="configure-network-settings-for-location-based-routing"></a><span data-ttu-id="46a8b-103">Настройка параметров сети для маршрутизации на основе расположения</span><span class="sxs-lookup"><span data-stu-id="46a8b-103">Configure network settings for Location-Based Routing</span></span>

<span data-ttu-id="46a8b-104">Если вы еще не сделали [](location-based-routing-plan.md) этого, ознакомьтесь с другими действиями, которые необходимо предпринять, прежде чем настраивать параметры сети для Location-Based Location-Based маршрутинга.</span><span class="sxs-lookup"><span data-stu-id="46a8b-104">If you haven't already done so, read [Plan Location-Based Routing for Direct Routing](location-based-routing-plan.md) to review other steps you'll need to take before you configure network settings for Location-Based Routing.</span></span>

<span data-ttu-id="46a8b-105">В этой статье описано, как настроить параметры сети для Location-Based маршрутов.</span><span class="sxs-lookup"><span data-stu-id="46a8b-105">This article describes how to configure network settings for Location-Based Routing.</span></span> <span data-ttu-id="46a8b-106">После развертывания прямой маршрутизации телефонной системы в организации необходимо создать и настроить сетевые регионы, сетевые сайты и подсети.</span><span class="sxs-lookup"><span data-stu-id="46a8b-106">After you deploy Phone System Direct Routing in your organization, the next steps are to create and set up network regions, network sites, and network subnets.</span></span>

## <a name="define-network-regions"></a><span data-ttu-id="46a8b-107">Определение сетевых регионов</span><span class="sxs-lookup"><span data-stu-id="46a8b-107">Define network regions</span></span>

<span data-ttu-id="46a8b-108">В сетевом регионе содержится коллекция сетевых сайтов, которые пересекают различные части сети по нескольким географическим областям.</span><span class="sxs-lookup"><span data-stu-id="46a8b-108">A network region contains a collection of network sites and interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="46a8b-109">По шагам настройки сетевых регионов перейдите в топологию управления сетью для облачных [функций в Teams.](manage-your-network-topology.md)</span><span class="sxs-lookup"><span data-stu-id="46a8b-109">For steps on how to configure network regions, go to [Manage your network topology for cloud features in Teams](manage-your-network-topology.md).</span></span>

## <a name="define-network-sites"></a><span data-ttu-id="46a8b-110">Определение сетевых сайтов</span><span class="sxs-lookup"><span data-stu-id="46a8b-110">Define network sites</span></span>

<span data-ttu-id="46a8b-111">Сетевой сайт — это расположение, в котором в вашей организации имеется физическое расположение, например офис, набор зданий или комплекс зданий.</span><span class="sxs-lookup"><span data-stu-id="46a8b-111">A network site represents a location where your organization has a physical venue, such as an office, a set of buildings, or a campus.</span></span> <span data-ttu-id="46a8b-112">Каждый сетевой сайт в топологии необходимо связать с сетевым регионом.</span><span class="sxs-lookup"><span data-stu-id="46a8b-112">You must associate each network site in your topology with a network region.</span></span> <span data-ttu-id="46a8b-113">По шагам по настройке сетевых сайтов см. в топологии "Управление топологией сети" [для облачных функций в Teams.](manage-your-network-topology.md)</span><span class="sxs-lookup"><span data-stu-id="46a8b-113">For steps on how to configure network sites, see [Manage your network topology for cloud features in Teams](manage-your-network-topology.md).</span></span>

<span data-ttu-id="46a8b-114">Для Location-Based маршрутов лучше всего создать отдельный сайт для каждого расположения с уникальным подключением к ДНР.</span><span class="sxs-lookup"><span data-stu-id="46a8b-114">A best practice for Location-Based Routing is to create a separate site for each location that has unique PSTN connectivity.</span></span> <span data-ttu-id="46a8b-115">Вы можете создать сайт с включенной Location-Based маршрутии или сайт, для Location-Based не включена.</span><span class="sxs-lookup"><span data-stu-id="46a8b-115">You can create a site that's enabled for Location-Based Routing or a site that's not enabled for Location-Based Routing.</span></span> <span data-ttu-id="46a8b-116">Например, может потребоваться создать сайт, для которого не включена маршрутная маршрутка Location-Based, чтобы пользователи, для которых включена маршрутная Location-Based, могли звонить по ННР при перенастройке на этот сайт.</span><span class="sxs-lookup"><span data-stu-id="46a8b-116">For example, you may want to create a site that's not enabled for Location-Based Routing to allow users who are enabled for Location-Based Routing to make PSTN calls when they roam to that site.</span></span>

## <a name="define-network-subnets"></a><span data-ttu-id="46a8b-117">Определение сетевых подсетей</span><span class="sxs-lookup"><span data-stu-id="46a8b-117">Define network subnets</span></span>

<span data-ttu-id="46a8b-118">Каждую подсеть необходимо связывать с определенным сетевым сайтом.</span><span class="sxs-lookup"><span data-stu-id="46a8b-118">Each subnet must be associated with a specific network site.</span></span> <span data-ttu-id="46a8b-119">С одной сетевой сетью можно связать несколько подсетей, но нельзя связать несколько сайтов с одной и той же.</span><span class="sxs-lookup"><span data-stu-id="46a8b-119">You can associate multiple subnets with the same network site but you can't associate multiple sites with the same subnet.</span></span> <span data-ttu-id="46a8b-120">Действия по настройке сетевых подсетей можно найти в топологии облачных функций Teams в  [окне "Управление](manage-your-network-topology.md)топологией сети".</span><span class="sxs-lookup"><span data-stu-id="46a8b-120">For steps on how to configure network subnets, go to  [Manage your network topology for cloud features in Teams](manage-your-network-topology.md).</span></span>

<span data-ttu-id="46a8b-121">Для Location-Based маршрутизации IP-подсети, в которых конечные точки Teams могут подключаться к сети, должны быть определены и связаны с определенной сетью для применения платного обхода.</span><span class="sxs-lookup"><span data-stu-id="46a8b-121">For Location-Based Routing, IP subnets at the location where Teams endpoints can connect to the network must be defined and associated to a defined network to enforce toll bypass.</span></span> <span data-ttu-id="46a8b-122">Такая связь подсетей позволяет Location-Based маршрутизации для определения географических конечных точек, чтобы определить, следует ли разрешить звонок по ННР.</span><span class="sxs-lookup"><span data-stu-id="46a8b-122">This association of subnets enables Location-Based Routing to locate the endpoints geographically to determine whether a given PSTN call should be allowed.</span></span> <span data-ttu-id="46a8b-123">Поддерживаются как подсети IPv6, так и IPv4.</span><span class="sxs-lookup"><span data-stu-id="46a8b-123">Both IPv6 and IPv4 subnets are supported.</span></span> <span data-ttu-id="46a8b-124">При определении того, находится ли конечная точка Teams на сайте, Location-Based Routing сначала проверяет наличие совпадающих IPv6-адресов.</span><span class="sxs-lookup"><span data-stu-id="46a8b-124">When determining whether a Teams endpoint is located at a site, Location-Based Routing first checks for a matching IPv6 address.</span></span> <span data-ttu-id="46a8b-125">Если IPv6-адреса нет, Location-Based Routing проверяет наличие IPv4-адреса.</span><span class="sxs-lookup"><span data-stu-id="46a8b-125">If an IPv6 address isn't present, Location-Based Routing checks for an IPv4 address.</span></span>

## <a name="define-trusted-ip-addresses-external-subnets"></a><span data-ttu-id="46a8b-126">Определение доверенных IP-адресов (внешних подсетей)</span><span class="sxs-lookup"><span data-stu-id="46a8b-126">Define trusted IP addresses (external subnets)</span></span>

<span data-ttu-id="46a8b-127">Надежные IP-адреса — это внешние IP-адреса корпоративной сети, которые используются для определения того, находится ли конечная точка пользователя в корпоративной сети.</span><span class="sxs-lookup"><span data-stu-id="46a8b-127">Trusted IP addresses are the internet external IP addresses of the enterprise network and are used to determine whether the user's endpoint is inside the corporate network.</span></span> <span data-ttu-id="46a8b-128">Действия по настройке доверенных IP-адресов можно найти в топологии облачных функций [Teams.](manage-your-network-topology.md)</span><span class="sxs-lookup"><span data-stu-id="46a8b-128">For steps on how to configure trusted IP addresses, go to  [Manage your network topology for cloud features in Teams](manage-your-network-topology.md).</span></span>

<span data-ttu-id="46a8b-129">Если внешний IP-адрес пользователя совпадает с IP-адресом, который находится в списке надежных IP-адресов, Location-Based Routing проверяет, чтобы определить внутреннюю подсеть, в которой находится конечная точка пользователя.</span><span class="sxs-lookup"><span data-stu-id="46a8b-129">If the user's external IP address matches an IP address that's in the trusted IP address list, Location-Based Routing checks to determine the internal subnet where the user's endpoint is located.</span></span> <span data-ttu-id="46a8b-130">Если внешний IP-адрес пользователя не соответствует IP-адресу, определенному в списке надежных IP-адресов, конечная точка классифицируется как неизвестная, а все звонки по ННР пользователю, у которого включена маршрутка Location-Based, блокируются.</span><span class="sxs-lookup"><span data-stu-id="46a8b-130">If the user's external IP address doesn't match any IP address that's defined in the trusted IP address list, the endpoint is classified as being at an unknown location and any PSTN calls to or from a user who is enabled for Location-Based Routing are blocked.</span></span>

## <a name="next-steps"></a><span data-ttu-id="46a8b-131">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="46a8b-131">Next steps</span></span>

<span data-ttu-id="46a8b-132">Перейдите [в Location-Based для прямой маршрутинга.](location-based-routing-enable.md)</span><span class="sxs-lookup"><span data-stu-id="46a8b-132">Go to [Enable Location-Based Routing for Direct Routing](location-based-routing-enable.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="46a8b-133">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="46a8b-133">Related topics</span></span>

- [<span data-ttu-id="46a8b-134">Параметры сети для функций облачного голосового связи в Teams</span><span class="sxs-lookup"><span data-stu-id="46a8b-134">Network settings for cloud voice features in Teams</span></span>](cloud-voice-network-settings.md)
