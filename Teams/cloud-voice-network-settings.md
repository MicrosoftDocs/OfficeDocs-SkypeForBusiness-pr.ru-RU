---
title: Параметры сети для функций голосовой связи в облаке
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.reviewer: roykuntz
ms.service: msteams
audience: admin
search.appverid: MET150
description: Узнайте о параметрах сети, которые необходимо настроить для Location-Based маршрутии для прямой маршрутии и улучшенных экстренных служб.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
- m365initiative-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: e97ddf7f6b7410e83a5e2257d7df6ae2ad27cb7f
ms.sourcegitcommit: 5c68298474d1782e69bde8c0940be7150cb93f6e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/23/2021
ms.locfileid: "53096286"
---
# <a name="network-settings-for-cloud-voice-features-in-microsoft-teams"></a><span data-ttu-id="36369-103">Параметры сети для облачных функций голосовой связи в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="36369-103">Network settings for cloud voice features in Microsoft Teams</span></span>

<span data-ttu-id="36369-104">Узнайте о сетевых регионах, сетевых сайтах, сетевых подсетях и доверенных IP-адресах.</span><span class="sxs-lookup"><span data-stu-id="36369-104">Learn about network regions, network sites, network subnets, and trusted IP addresses.</span></span> <span data-ttu-id="36369-105">Эти термины и понятия используются во всей [](location-based-routing-plan.md) облачной голосовой документации для маршрутизов на основе местоположения для прямой маршрутации и динамических [экстренных вызовов.](configure-dynamic-emergency-calling.md)</span><span class="sxs-lookup"><span data-stu-id="36369-105">These terms and concepts are used throughout our cloud voice documentation for [Location-Based Routing for Direct Routing](location-based-routing-plan.md) and [dynamic emergency calling](configure-dynamic-emergency-calling.md).</span></span> <span data-ttu-id="36369-106">При развертывании этих облачных функций в организации необходимо настроить параметры сети для использования с этими функциями в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="36369-106">If you're deploying these cloud features in your organization, you must configure network settings for use with these features in Microsoft Teams.</span></span>

<span data-ttu-id="36369-107">В этой статье представлен обзор параметров сети, которые часто Location-Based маршрутизов и динамических экстренных вызовов.</span><span class="sxs-lookup"><span data-stu-id="36369-107">This article gives you an overview of the network settings that are common to Location-Based Routing and dynamic emergency calling.</span></span> <span data-ttu-id="36369-108">В зависимости от облачной голосовой функции и возможности развертывания вы можете настроить некоторые или все эти параметры.</span><span class="sxs-lookup"><span data-stu-id="36369-108">Depending on the cloud voice feature and capability that you're deploying, you configure some or all these settings.</span></span> <span data-ttu-id="36369-109">По шагам по настройке этих параметров см. управление топологией сети для облачных функций в [Teams.](manage-your-network-topology.md)</span><span class="sxs-lookup"><span data-stu-id="36369-109">For steps on how to configure these settings, see [Manage your network topology for cloud features in Teams](manage-your-network-topology.md).</span></span>

> [!NOTE]
> <span data-ttu-id="36369-110">Все требования к настройкам сети, связанные с определенными функциями, задокументированы в темах конфигурации для этой функции.</span><span class="sxs-lookup"><span data-stu-id="36369-110">Any feature-specific requirements for network settings are documented in the configuration topics for that feature.</span></span>

## <a name="network-region"></a><span data-ttu-id="36369-111">Сетевой регион</span><span class="sxs-lookup"><span data-stu-id="36369-111">Network region</span></span>

<span data-ttu-id="36369-112">Область сети содержит коллекцию сетевых сайтов.</span><span class="sxs-lookup"><span data-stu-id="36369-112">A network region contains a collection of network sites.</span></span> <span data-ttu-id="36369-113">Она соединяет различные части сети между несколькими географическими областями.</span><span class="sxs-lookup"><span data-stu-id="36369-113">It interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="36369-114">Например, если в вашей организации много сайтов в Индии, вы можете назначить Индию сетевым регионом.</span><span class="sxs-lookup"><span data-stu-id="36369-114">For example, if your organization has many sites located in India, you may choose to designate "India" as a network region.</span></span> <span data-ttu-id="36369-115">Каждый сетевой сайт должен быть связан с сетевым регионом.</span><span class="sxs-lookup"><span data-stu-id="36369-115">Each network site must be associated with a network region.</span></span>

<span data-ttu-id="36369-116">Эти же сетевые регионы совместно Location-Based маршрутии для прямой маршрутии и улучшенных экстренных служб.</span><span class="sxs-lookup"><span data-stu-id="36369-116">The same network regions are shared by Location-Based Routing for Direct Routing and enhanced emergency services.</span></span> <span data-ttu-id="36369-117">Если вы уже создали сетевые регионы для одной функции, создавать для нее новые сетевые регионы не нужно.</span><span class="sxs-lookup"><span data-stu-id="36369-117">If you already created network regions for one feature, you don't have to create new network regions for the other feature.</span></span>

## <a name="network-site"></a><span data-ttu-id="36369-118">Сетевой сайт</span><span class="sxs-lookup"><span data-stu-id="36369-118">Network site</span></span>

<span data-ttu-id="36369-119">Сетевой сайт — это место, где в вашей организации есть физическое расположение, например офис, набор зданий или комплекс зданий.</span><span class="sxs-lookup"><span data-stu-id="36369-119">A network site represents a location where your organization has a physical venue, such as an office, a set of buildings, or a campus.</span></span> <span data-ttu-id="36369-120">Сетевые сайты определяются как набор IP-подсетей.</span><span class="sxs-lookup"><span data-stu-id="36369-120">Network sites are defined as a collection of IP subnets.</span></span> <span data-ttu-id="36369-121">Каждый сетевой сайт должен быть связан с сетевым регионом.</span><span class="sxs-lookup"><span data-stu-id="36369-121">Each network site must be associated with a network region.</span></span>

<span data-ttu-id="36369-122">С помощью сетевых сайтов также можно включить и настроить экстренные вызовы.</span><span class="sxs-lookup"><span data-stu-id="36369-122">You can also use network sites to enable and configure emergency calling.</span></span>

## <a name="network-subnet"></a><span data-ttu-id="36369-123">Подсеть сети</span><span class="sxs-lookup"><span data-stu-id="36369-123">Network subnet</span></span>

<span data-ttu-id="36369-124">Каждая подсеть должна быть связана с определенным сетевым сайтом.</span><span class="sxs-lookup"><span data-stu-id="36369-124">Each subnet must be associated with a specific network site.</span></span> <span data-ttu-id="36369-125">Расположение клиента определяется на основе сетевой подсети и связанного сетевого сайта.</span><span class="sxs-lookup"><span data-stu-id="36369-125">A client's location is determined based on the network subnet and the associated network site.</span></span> <span data-ttu-id="36369-126">Вы можете связать несколько подсетей с одинаковым сетевым сайтом, но нельзя связать несколько сайтов с одной и той же подсетью.</span><span class="sxs-lookup"><span data-stu-id="36369-126">You can associate multiple subnets with the same network site but you can't associate multiple sites with the same subnet.</span></span>

<span data-ttu-id="36369-127">Сведения из подсети используются для определения сетевого сайта, на котором находится конечная точка при иниции нового сеанса.</span><span class="sxs-lookup"><span data-stu-id="36369-127">Subnet information is used to determine the network site on which an endpoint is located when a new session is initiated.</span></span> <span data-ttu-id="36369-128">Когда известно о расположении каждой из сторон в сеансе, облачная голосовая функция может применять эти сведения, чтобы определить, как управлять настройкой и маршрутизовой обработкой звонка.</span><span class="sxs-lookup"><span data-stu-id="36369-128">When the location of each party in a session is known, the cloud voice feature can apply that information to determine how to handle call setup or routing.</span></span>

<span data-ttu-id="36369-129">Для каждого сетевого сайта определите, какие IP-подсети назначены каждому сетевому сайту.</span><span class="sxs-lookup"><span data-stu-id="36369-129">For each network site, work with your network admin to determine which IP subnets are assigned to each network site.</span></span> <span data-ttu-id="36369-130">В нашем примере сайту "Нью-Йорк" в регионе "Северная Америка" назначены следующие IP-подсети: 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24.</span><span class="sxs-lookup"><span data-stu-id="36369-130">For example, the New York site in the North America region can be assigned the following IP subnets: 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24.</span></span> <span data-ttu-id="36369-131">Если Г-н Мяк, который обычно работает в Москве, переходит в офис в Нью-Йорке для обучения, включает свой компьютер и подключается к сети, его компьютер получает IP-адрес в одном из четырех диапазонов, выделенных для Москвы, например 172.29.80.103.</span><span class="sxs-lookup"><span data-stu-id="36369-131">If Bob, who usually works in Detroit, travels to the New York office for training, turns on his computer and connects to the network, his computer will get an IP address in one of the four ranges that are allocated for New York, for example, 172.29.80.103.</span></span>

## <a name="trusted-ip-address"></a><span data-ttu-id="36369-132">Надежный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="36369-132">Trusted IP address</span></span>

<span data-ttu-id="36369-133">Надежные IP-адреса — это внешние IP-адреса корпоративной сети.</span><span class="sxs-lookup"><span data-stu-id="36369-133">Trusted IP addresses are the internet external IP addresses of the enterprise network.</span></span> <span data-ttu-id="36369-134">Они определяют, находится ли конечная точка пользователя в корпоративной сети, прежде чем проверять соответствие определенного сайта.</span><span class="sxs-lookup"><span data-stu-id="36369-134">They determine whether the user's endpoint is inside the corporate network before checking for a specific site match.</span></span>

<span data-ttu-id="36369-135">Если внешний IP-адрес пользователя совпадает с IP-адресом, который находится в списке надежных IP-адресов, функция облачного голосового управления проверяет внутреннюю подсеть, в которой находится конечная точка пользователя.</span><span class="sxs-lookup"><span data-stu-id="36369-135">If the user's external IP address matches an IP address that's in the trusted IP address list, the cloud voice feature checks to determine the internal subnet where the user's endpoint is located.</span></span> <span data-ttu-id="36369-136">Соответствие между IP-адресами IPv4 и IPv6 зависит от формата IP-пакета, отправленного в параметры сети.</span><span class="sxs-lookup"><span data-stu-id="36369-136">A match can be made against either IPv4 or IPv6 IP addresses and is dependent upon the format of the IP packet sent to the network settings.</span></span> <span data-ttu-id="36369-137">(Если общедоступный IP-адрес имеет как IPv4, так и IPv6, необходимо добавить оба ip-адреса в качестве надежных.)</span><span class="sxs-lookup"><span data-stu-id="36369-137">(If a public IP address has both IPv4 and IPv6, you must add both as trusted IP addresses.)</span></span>

<span data-ttu-id="36369-138">Если внешний IP-адрес пользователя не совпадает с IP-адресом, который находится в списке надежных IP-адресов, конечная точка классифицируется как на неизвестном месте.</span><span class="sxs-lookup"><span data-stu-id="36369-138">If the user's external IP address doesn't match an IP address that's in the trusted IP address list, the endpoint is classified as being at an unknown location.</span></span>

> [!Important]
> <span data-ttu-id="36369-139">Параметры сети не поддерживаются при развертывании облачных прокси-служб, которые изменяют IP-адреса источников из Teams клиентов.</span><span class="sxs-lookup"><span data-stu-id="36369-139">Network configuration setting lookups are not supported with cloud proxy service deployments that modify the source IP addresses from Teams clients.</span></span>
