---
title: Настройка параметров сети — маршрутия на основе расположения
author: LanaChin
ms.author: v-lanac
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
ms.openlocfilehash: 8025467a0581c95a40551244948a8e6b7c0ecbc8
ms.sourcegitcommit: 3e5cac88911611c94c0330bf50af9c34db308cdf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/22/2020
ms.locfileid: "45372064"
---
# <a name="configure-network-settings-for-location-based-routing"></a><span data-ttu-id="fadbe-103">Настройка параметров сети для маршрутизации на основе расположения</span><span class="sxs-lookup"><span data-stu-id="fadbe-103">Configure network settings for Location-Based Routing</span></span>

<span data-ttu-id="fadbe-104">Если вы еще не сделали [](location-based-routing-plan.md) этого, ознакомьтесь с другими действиями, которые необходимо предпринять, прежде чем настраивать параметры сети для Location-Based Location-Based маршрутинга.</span><span class="sxs-lookup"><span data-stu-id="fadbe-104">If you haven't already done so, read [Plan Location-Based Routing for Direct Routing](location-based-routing-plan.md) to review other steps you'll need to take before you configure network settings for Location-Based Routing.</span></span>

<span data-ttu-id="fadbe-105">В этой статье описано, как настроить параметры сети для Location-Based маршрутов.</span><span class="sxs-lookup"><span data-stu-id="fadbe-105">This article describes how to configure network settings for Location-Based Routing.</span></span> <span data-ttu-id="fadbe-106">После развертывания прямой маршрутизации телефонной системы в организации необходимо создать и настроить сетевые регионы, сетевые сайты и подсети.</span><span class="sxs-lookup"><span data-stu-id="fadbe-106">After you deploy Phone System Direct Routing in your organization, the next steps are to create and set up network regions, network sites, and network subnets.</span></span>

## <a name="define-network-regions"></a><span data-ttu-id="fadbe-107">Определение сетевых регионов</span><span class="sxs-lookup"><span data-stu-id="fadbe-107">Define network regions</span></span>

<span data-ttu-id="fadbe-108">В сетевом регионе содержится коллекция сетевых сайтов, которые пересекают различные части сети по нескольким географическим областям.</span><span class="sxs-lookup"><span data-stu-id="fadbe-108">A network region contains a collection of network sites and interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="fadbe-109">Действия по настройке сетевых регионов можно найти в топологии облачных функций [Teams.](manage-your-network-topology.md)</span><span class="sxs-lookup"><span data-stu-id="fadbe-109">For steps on how to configure network regions, go to [Manage your network topology for cloud features in Teams](manage-your-network-topology.md).</span></span>

## <a name="define-network-sites"></a><span data-ttu-id="fadbe-110">Определение сетевых сайтов</span><span class="sxs-lookup"><span data-stu-id="fadbe-110">Define network sites</span></span>

<span data-ttu-id="fadbe-111">Сетевой сайт — это расположение, в котором в вашей организации имеется физическое расположение, например офис, набор зданий или комплекс зданий.</span><span class="sxs-lookup"><span data-stu-id="fadbe-111">A network site represents a location where your organization has a physical venue, such as an office, a set of buildings, or a campus.</span></span> <span data-ttu-id="fadbe-112">Каждый сетевой сайт в топологии необходимо связать с сетевым регионом.</span><span class="sxs-lookup"><span data-stu-id="fadbe-112">You must associate each network site in your topology with a network region.</span></span> <span data-ttu-id="fadbe-113">По шагам по настройке сетевых сайтов см. топологию сети для [облачных функций в Teams.](manage-your-network-topology.md)</span><span class="sxs-lookup"><span data-stu-id="fadbe-113">For steps on how to configure network sites, see [Manage your network topology for cloud features in Teams](manage-your-network-topology.md).</span></span>

<span data-ttu-id="fadbe-114">Для Location-Based маршрутов лучше всего создать отдельный сайт для каждого расположения с уникальным подключением к ДНР.</span><span class="sxs-lookup"><span data-stu-id="fadbe-114">A best practice for Location-Based Routing is to create a separate site for each location that has unique PSTN connectivity.</span></span> <span data-ttu-id="fadbe-115">Вы можете создать сайт с включенной Location-Based маршрутии или сайт, для Location-Based не включена.</span><span class="sxs-lookup"><span data-stu-id="fadbe-115">You can create a site that's enabled for Location-Based Routing or a site that's not enabled for Location-Based Routing.</span></span> <span data-ttu-id="fadbe-116">Например, может потребоваться создать сайт, для которого не включена маршрутная маршрутка Location-Based, чтобы пользователи, для которых включена маршрутная Location-Based, могли при роуминге на этот сайт звонить по ННР.</span><span class="sxs-lookup"><span data-stu-id="fadbe-116">For example, you may want to create a site that's not enabled for Location-Based Routing to allow users who are enabled for Location-Based Routing to make PSTN calls when they roam to that site.</span></span>

## <a name="define-network-subnets"></a><span data-ttu-id="fadbe-117">Определение сетевых подсетей</span><span class="sxs-lookup"><span data-stu-id="fadbe-117">Define network subnets</span></span>

<span data-ttu-id="fadbe-118">Каждую подсеть необходимо связывать с определенным сетевым сайтом.</span><span class="sxs-lookup"><span data-stu-id="fadbe-118">Each subnet must be associated with a specific network site.</span></span> <span data-ttu-id="fadbe-119">С одной сетевой сетью можно связать несколько подсетей, но нельзя связать несколько сайтов с одной и той же.</span><span class="sxs-lookup"><span data-stu-id="fadbe-119">You can associate multiple subnets with the same network site but you can't associate multiple sites with the same subnet.</span></span> <span data-ttu-id="fadbe-120">По шагам настройки сетевых подсетей перейдите в топологию своей сети для облачных [функций в Teams.](manage-your-network-topology.md)</span><span class="sxs-lookup"><span data-stu-id="fadbe-120">For steps on how to configure network subnets, go to  [Manage your network topology for cloud features in Teams](manage-your-network-topology.md).</span></span>

<span data-ttu-id="fadbe-121">Для Location-Based маршрутизации IP-подсети, в которых конечные точки Teams могут подключаться к сети, должны быть определены и связаны с определенной сетью для применения платного обхода.</span><span class="sxs-lookup"><span data-stu-id="fadbe-121">For Location-Based Routing, IP subnets at the location where Teams endpoints can connect to the network must be defined and associated to a defined network to enforce toll bypass.</span></span> <span data-ttu-id="fadbe-122">Такая связь подсетей позволяет Location-Based маршрутизации для определения географических конечных точек, чтобы определить, следует ли разрешить звонок по ННР.</span><span class="sxs-lookup"><span data-stu-id="fadbe-122">This association of subnets enables Location-Based Routing to locate the endpoints geographically to determine whether a given PSTN call should be allowed.</span></span> <span data-ttu-id="fadbe-123">Поддерживаются как подсети IPv6, так и IPv4.</span><span class="sxs-lookup"><span data-stu-id="fadbe-123">Both IPv6 and IPv4 subnets are supported.</span></span> <span data-ttu-id="fadbe-124">При определении того, находится ли конечная точка Teams на сайте, Location-Based Routing сначала проверяет наличие совпадающих IPv6-адресов.</span><span class="sxs-lookup"><span data-stu-id="fadbe-124">When determining whether a Teams endpoint is located at a site, Location-Based Routing first checks for a matching IPv6 address.</span></span> <span data-ttu-id="fadbe-125">Если IPv6-адреса нет, Location-Based Routing проверяет наличие IPv4-адреса.</span><span class="sxs-lookup"><span data-stu-id="fadbe-125">If an IPv6 address isn't present, Location-Based Routing checks for an IPv4 address.</span></span>

## <a name="define-trusted-ip-addresses-external-subnets"></a><span data-ttu-id="fadbe-126">Определение доверенных IP-адресов (внешних подсетей)</span><span class="sxs-lookup"><span data-stu-id="fadbe-126">Define trusted IP addresses (external subnets)</span></span>

<span data-ttu-id="fadbe-127">Надежные IP-адреса — это внешние IP-адреса корпоративной сети, которые используются для определения того, находится ли конечная точка пользователя в корпоративной сети.</span><span class="sxs-lookup"><span data-stu-id="fadbe-127">Trusted IP addresses are the internet external IP addresses of the enterprise network and are used to determine whether the user's endpoint is inside the corporate network.</span></span> <span data-ttu-id="fadbe-128">Действия по настройке доверенных IP-адресов можно найти в топологии облачных функций [Teams.](manage-your-network-topology.md)</span><span class="sxs-lookup"><span data-stu-id="fadbe-128">For steps on how to configure trusted IP addresses, go to  [Manage your network topology for cloud features in Teams](manage-your-network-topology.md).</span></span>

<span data-ttu-id="fadbe-129">Если внешний IP-адрес пользователя совпадает с IP-адресом, который находится в списке надежных IP-адресов, Location-Based Routing проверяет, чтобы определить внутреннюю подсеть, в которой находится конечная точка пользователя.</span><span class="sxs-lookup"><span data-stu-id="fadbe-129">If the user's external IP address matches an IP address that's in the trusted IP address list, Location-Based Routing checks to determine the internal subnet where the user's endpoint is located.</span></span> <span data-ttu-id="fadbe-130">Если внешний IP-адрес пользователя не соответствует IP-адресу, определенному в списке надежных IP-адресов, конечная точка классифицируется как неизвестная, а все звонки по ННР пользователю, у которого включена маршрутка Location-Based, блокируются.</span><span class="sxs-lookup"><span data-stu-id="fadbe-130">If the user's external IP address doesn't match any IP address that's defined in the trusted IP address list, the endpoint is classified as being at an unknown location and any PSTN calls to or from a user who is enabled for Location-Based Routing are blocked.</span></span>

## <a name="next-steps"></a><span data-ttu-id="fadbe-131">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="fadbe-131">Next steps</span></span>

<span data-ttu-id="fadbe-132">Перейдите [в Location-Based для прямой маршрутинга.](location-based-routing-enable.md)</span><span class="sxs-lookup"><span data-stu-id="fadbe-132">Go to [Enable Location-Based Routing for Direct Routing](location-based-routing-enable.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="fadbe-133">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="fadbe-133">Related topics</span></span>

- [<span data-ttu-id="fadbe-134">Параметры сети для функций облачного голосового связи в Teams</span><span class="sxs-lookup"><span data-stu-id="fadbe-134">Network settings for cloud voice features in Teams</span></span>](cloud-voice-network-settings.md)
