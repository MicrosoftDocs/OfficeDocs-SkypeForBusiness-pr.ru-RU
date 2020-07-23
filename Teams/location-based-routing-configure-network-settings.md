---
title: Настройка параметров сети — маршрутизация на основе местоположения
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.reviewer: roykuntz
audience: admin
ms.service: msteams
search.appverid: MET150
description: Сведения о том, как создавать и настраивать регионы сети, сайты и подсети для маршрутизации на основе местоположения для прямой маршрутизации.
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
# <a name="configure-network-settings-for-location-based-routing"></a><span data-ttu-id="19c3f-103">Настройка параметров сети для маршрутизации на основе расположения</span><span class="sxs-lookup"><span data-stu-id="19c3f-103">Configure network settings for Location-Based Routing</span></span>

<span data-ttu-id="19c3f-104">Если вы еще не сделали этого, прочтите [маршрут на основе местоположения для прямой маршрутизации](location-based-routing-plan.md) , чтобы просмотреть другие действия, которые необходимо выполнить перед настройкой сетевых параметров для маршрутизации на основе местоположения.</span><span class="sxs-lookup"><span data-stu-id="19c3f-104">If you haven't already done so, read [Plan Location-Based Routing for Direct Routing](location-based-routing-plan.md) to review other steps you'll need to take before you configure network settings for Location-Based Routing.</span></span>

<span data-ttu-id="19c3f-105">В этой статье описано, как настроить параметры сети для маршрутизации на основе местоположения.</span><span class="sxs-lookup"><span data-stu-id="19c3f-105">This article describes how to configure network settings for Location-Based Routing.</span></span> <span data-ttu-id="19c3f-106">После развертывания прямой маршрутизации для телефонной системы в Организации следует создать и настроить регионы сети, сетевые сайты и сетевые подсети.</span><span class="sxs-lookup"><span data-stu-id="19c3f-106">After you deploy Phone System Direct Routing in your organization, the next steps are to create and set up network regions, network sites, and network subnets.</span></span>

## <a name="define-network-regions"></a><span data-ttu-id="19c3f-107">Определение регионов сети</span><span class="sxs-lookup"><span data-stu-id="19c3f-107">Define network regions</span></span>

<span data-ttu-id="19c3f-108">Сетевой регион включает в себя набор сетевых сайтов и соединяет различные части сети в нескольких географических регионах.</span><span class="sxs-lookup"><span data-stu-id="19c3f-108">A network region contains a collection of network sites and interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="19c3f-109">Инструкции по настройке регионов сети можно найти в статье [Управление топологией сети для функциональных возможностей облака в Teams](manage-your-network-topology.md).</span><span class="sxs-lookup"><span data-stu-id="19c3f-109">For steps on how to configure network regions, go to [Manage your network topology for cloud features in Teams](manage-your-network-topology.md).</span></span>

## <a name="define-network-sites"></a><span data-ttu-id="19c3f-110">Определение сетевых сайтов</span><span class="sxs-lookup"><span data-stu-id="19c3f-110">Define network sites</span></span>

<span data-ttu-id="19c3f-111">Сетевой сайт — это расположение, в котором Организация имеет физическое место проведения, например Office, набор зданий или кампус.</span><span class="sxs-lookup"><span data-stu-id="19c3f-111">A network site represents a location where your organization has a physical venue, such as an office, a set of buildings, or a campus.</span></span> <span data-ttu-id="19c3f-112">Вы должны связать каждый сетевой сайт в вашей топологии с сетевым регионом.</span><span class="sxs-lookup"><span data-stu-id="19c3f-112">You must associate each network site in your topology with a network region.</span></span> <span data-ttu-id="19c3f-113">Инструкции по настройке сетевых сайтов приведены [в статье Управление топологией сети для облачных функций в Teams](manage-your-network-topology.md).</span><span class="sxs-lookup"><span data-stu-id="19c3f-113">For steps on how to configure network sites, see [Manage your network topology for cloud features in Teams](manage-your-network-topology.md).</span></span>

<span data-ttu-id="19c3f-114">Лучшим вариантом для маршрутизации на основе местоположения является создание отдельного сайта для каждого местоположения с уникальной связью по протоколу PSTN.</span><span class="sxs-lookup"><span data-stu-id="19c3f-114">A best practice for Location-Based Routing is to create a separate site for each location that has unique PSTN connectivity.</span></span> <span data-ttu-id="19c3f-115">Вы можете создать сайт, для которого включена маршрутизация на основе местоположения, или сайт, для которого не включена маршрутизация на основе местоположения.</span><span class="sxs-lookup"><span data-stu-id="19c3f-115">You can create a site that's enabled for Location-Based Routing or a site that's not enabled for Location-Based Routing.</span></span> <span data-ttu-id="19c3f-116">Например, вы можете создать сайт, для которого не включена маршрутизация на основе расположения, чтобы предоставить пользователям, которые разрешено использовать маршрутизацию на основе местоположения, звонить по коммутируемой телефонной связи, когда они перемещаются на этот сайт.</span><span class="sxs-lookup"><span data-stu-id="19c3f-116">For example, you may want to create a site that's not enabled for Location-Based Routing to allow users who are enabled for Location-Based Routing to make PSTN calls when they roam to that site.</span></span>

## <a name="define-network-subnets"></a><span data-ttu-id="19c3f-117">Определение подсетей сети</span><span class="sxs-lookup"><span data-stu-id="19c3f-117">Define network subnets</span></span>

<span data-ttu-id="19c3f-118">Каждая подсеть должна быть связана с определенным сетевым сайтом.</span><span class="sxs-lookup"><span data-stu-id="19c3f-118">Each subnet must be associated with a specific network site.</span></span> <span data-ttu-id="19c3f-119">Вы можете связать несколько подсетей с одним сетевым сайтом, но вы не можете связать несколько сайтов с одной и той же подсетью.</span><span class="sxs-lookup"><span data-stu-id="19c3f-119">You can associate multiple subnets with the same network site but you can't associate multiple sites with the same subnet.</span></span> <span data-ttu-id="19c3f-120">Инструкции по настройке сетевой подсети можно найти в статье [Управление топологией сети для облачных функций в Teams](manage-your-network-topology.md).</span><span class="sxs-lookup"><span data-stu-id="19c3f-120">For steps on how to configure network subnets, go to  [Manage your network topology for cloud features in Teams](manage-your-network-topology.md).</span></span>

<span data-ttu-id="19c3f-121">Для маршрутизации, основанной на расположении, IP-подсети в расположении, где конечные точки группы могут подключаться к сети, должны быть определены и связаны с определенными сетями для обеспечения бесплатного обхода.</span><span class="sxs-lookup"><span data-stu-id="19c3f-121">For Location-Based Routing, IP subnets at the location where Teams endpoints can connect to the network must be defined and associated to a defined network to enforce toll bypass.</span></span> <span data-ttu-id="19c3f-122">Эта ассоциация подсетей позволяет расположить конечные точки на основе местоположения, чтобы определить, следует ли разрешить данный звонок по протоколу PSTN.</span><span class="sxs-lookup"><span data-stu-id="19c3f-122">This association of subnets enables Location-Based Routing to locate the endpoints geographically to determine whether a given PSTN call should be allowed.</span></span> <span data-ttu-id="19c3f-123">Поддерживаются обе подсети IPv6 и IPv4.</span><span class="sxs-lookup"><span data-stu-id="19c3f-123">Both IPv6 and IPv4 subnets are supported.</span></span> <span data-ttu-id="19c3f-124">При определении того, находится ли конечная точка Teams на сайте, маршрутизация на основе местоположения сначала проверяет соответствующий IPv6-адрес.</span><span class="sxs-lookup"><span data-stu-id="19c3f-124">When determining whether a Teams endpoint is located at a site, Location-Based Routing first checks for a matching IPv6 address.</span></span> <span data-ttu-id="19c3f-125">Если IPv6-адрес отсутствует, маршрутизация на основе местоположения проверяет адрес IPv4.</span><span class="sxs-lookup"><span data-stu-id="19c3f-125">If an IPv6 address isn't present, Location-Based Routing checks for an IPv4 address.</span></span>

## <a name="define-trusted-ip-addresses-external-subnets"></a><span data-ttu-id="19c3f-126">Определение доверенных IP-адресов (внешних подсетей)</span><span class="sxs-lookup"><span data-stu-id="19c3f-126">Define trusted IP addresses (external subnets)</span></span>

<span data-ttu-id="19c3f-127">Доверенные IP-адреса — это внешние IP-адреса в сети организации, которые используются для определения того, входит ли конечная точка пользователя в корпоративную сеть.</span><span class="sxs-lookup"><span data-stu-id="19c3f-127">Trusted IP addresses are the internet external IP addresses of the enterprise network and are used to determine whether the user's endpoint is inside the corporate network.</span></span> <span data-ttu-id="19c3f-128">Инструкции по настройке доверенных IP-адресов можно найти в статье [Управление топологией сети для функциональных возможностей облака в Teams](manage-your-network-topology.md).</span><span class="sxs-lookup"><span data-stu-id="19c3f-128">For steps on how to configure trusted IP addresses, go to  [Manage your network topology for cloud features in Teams](manage-your-network-topology.md).</span></span>

<span data-ttu-id="19c3f-129">Если внешний IP-адрес пользователя соответствует IP-адресу, указанному в списке доверенный IP-адрес, для определения внутренней подсети, в которой находится конечная точка пользователя, будет проверяться маршрутизация на основе местоположения.</span><span class="sxs-lookup"><span data-stu-id="19c3f-129">If the user's external IP address matches an IP address that's in the trusted IP address list, Location-Based Routing checks to determine the internal subnet where the user's endpoint is located.</span></span> <span data-ttu-id="19c3f-130">Если внешний IP-адрес пользователя не совпадает с IP-адресом, определенным в списке доверенный IP-адрес, конечная точка классифицируется как неизвестная, и любые вызовы по КТСОП для пользователя, для которого включена маршрутизация на основе местоположения, заблокированы.</span><span class="sxs-lookup"><span data-stu-id="19c3f-130">If the user's external IP address doesn't match any IP address that's defined in the trusted IP address list, the endpoint is classified as being at an unknown location and any PSTN calls to or from a user who is enabled for Location-Based Routing are blocked.</span></span>

## <a name="next-steps"></a><span data-ttu-id="19c3f-131">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="19c3f-131">Next steps</span></span>

<span data-ttu-id="19c3f-132">Перейдите к разделу [Включение маршрутизации на основе местоположения для прямой маршрутизации](location-based-routing-enable.md).</span><span class="sxs-lookup"><span data-stu-id="19c3f-132">Go to [Enable Location-Based Routing for Direct Routing](location-based-routing-enable.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="19c3f-133">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="19c3f-133">Related topics</span></span>

- [<span data-ttu-id="19c3f-134">Параметры сети для функций голосовой связи в облаке в Teams</span><span class="sxs-lookup"><span data-stu-id="19c3f-134">Network settings for cloud voice features in Teams</span></span>](cloud-voice-network-settings.md)
