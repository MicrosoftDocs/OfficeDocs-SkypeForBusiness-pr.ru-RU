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
description: Узнайте о параметрах сети, которые необходимо настроить для Location-Based прямой маршрутии и улучшенных экстренных служб.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
- m365initiative-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 10547a99b0e63585ae39cc90a5b0cf573a9c94e3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834339"
---
# <a name="network-settings-for-cloud-voice-features-in-microsoft-teams"></a><span data-ttu-id="2a588-103">Параметры сети для функций облачного голосового связи в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2a588-103">Network settings for cloud voice features in Microsoft Teams</span></span>

<span data-ttu-id="2a588-104">Узнайте о сетевых регионах, сетевых сайтах, подсетях и доверенных IP-адресах.</span><span class="sxs-lookup"><span data-stu-id="2a588-104">Learn about network regions, network sites, network subnets, and trusted IP addresses.</span></span> <span data-ttu-id="2a588-105">Эти термины и понятия используются в нашей [](location-based-routing-plan.md) облачной документации по голосовой связи на основе местоположения для прямой маршрутации и [динамических экстренных вызовов.](configure-dynamic-emergency-calling.md)</span><span class="sxs-lookup"><span data-stu-id="2a588-105">These terms and concepts are used throughout our cloud voice documentation for [Location-Based Routing for Direct Routing](location-based-routing-plan.md) and [dynamic emergency calling](configure-dynamic-emergency-calling.md).</span></span> <span data-ttu-id="2a588-106">При развертывании этих облачных функций в организации необходимо настроить параметры сети для использования с этими функциями в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="2a588-106">If you're deploying these cloud features in your organization, you must configure network settings for use with these features in Microsoft Teams.</span></span>

<span data-ttu-id="2a588-107">В этой статье дается обзор параметров сети, которые часто Location-Based маршрутизов и динамических экстренных вызовов.</span><span class="sxs-lookup"><span data-stu-id="2a588-107">This article gives you an overview of the network settings that are common to Location-Based Routing and dynamic emergency calling.</span></span> <span data-ttu-id="2a588-108">В зависимости от функции облачного голосового голоса и возможности развертывания вы можете настроить некоторые или все эти параметры.</span><span class="sxs-lookup"><span data-stu-id="2a588-108">Depending on the cloud voice feature and capability that you're deploying, you configure some or all these settings.</span></span> <span data-ttu-id="2a588-109">Действия по настройке этих параметров см. в топологии облачных функций [в Teams.](manage-your-network-topology.md)</span><span class="sxs-lookup"><span data-stu-id="2a588-109">For steps on how to configure these settings, see [Manage your network topology for cloud features in Teams](manage-your-network-topology.md).</span></span>

> [!NOTE]
> <span data-ttu-id="2a588-110">Требования, связанные с определенными функциями, для настройки параметров сети описаны в темах конфигурации для этой функции.</span><span class="sxs-lookup"><span data-stu-id="2a588-110">Any feature-specific requirements for network settings are documented in the configuration topics for that feature.</span></span>

## <a name="network-region"></a><span data-ttu-id="2a588-111">Регион сети</span><span class="sxs-lookup"><span data-stu-id="2a588-111">Network region</span></span>

<span data-ttu-id="2a588-112">Область сети содержит коллекцию сетевых сайтов.</span><span class="sxs-lookup"><span data-stu-id="2a588-112">A network region contains a collection of network sites.</span></span> <span data-ttu-id="2a588-113">Она пересекает различные части сети по нескольким географическим областям.</span><span class="sxs-lookup"><span data-stu-id="2a588-113">It interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="2a588-114">Например, если в вашей организации много сайтов, расположенных в Индии, вы можете назначить Индию в качестве сетевого региона.</span><span class="sxs-lookup"><span data-stu-id="2a588-114">For example, if your organization has many sites located in India, you may choose to designate "India" as a network region.</span></span> <span data-ttu-id="2a588-115">Каждый сетевой сайт должен быть связан с сетевым регионом.</span><span class="sxs-lookup"><span data-stu-id="2a588-115">Each network site must be associated with a network region.</span></span>

<span data-ttu-id="2a588-116">Эти же сетевые регионы можно Location-Based маршрутии для прямой маршрутки и улучшенных экстренных служб.</span><span class="sxs-lookup"><span data-stu-id="2a588-116">The same network regions are shared by Location-Based Routing for Direct Routing and enhanced emergency services.</span></span> <span data-ttu-id="2a588-117">Если вы уже создали сетевые регионы для одной функции, создавать новые сетевые регионы для другого не нужно.</span><span class="sxs-lookup"><span data-stu-id="2a588-117">If you already created network regions for one feature, you don't have to create new network regions for the other feature.</span></span>

## <a name="network-site"></a><span data-ttu-id="2a588-118">Сетевой сайт</span><span class="sxs-lookup"><span data-stu-id="2a588-118">Network site</span></span>

<span data-ttu-id="2a588-119">Сетевой сайт — это расположение, в котором в вашей организации имеется физическое расположение, например офис, набор зданий или много зданий.</span><span class="sxs-lookup"><span data-stu-id="2a588-119">A network site represents a location where your organization has a physical venue, such as an office, a set of buildings, or a campus.</span></span> <span data-ttu-id="2a588-120">Сетевые сайты определяются как набор IP-подсетей.</span><span class="sxs-lookup"><span data-stu-id="2a588-120">Network sites are defined as a collection of IP subnets.</span></span> <span data-ttu-id="2a588-121">Каждый сетевой сайт должен быть связан с сетевым регионом.</span><span class="sxs-lookup"><span data-stu-id="2a588-121">Each network site must be associated with a network region.</span></span>

<span data-ttu-id="2a588-122">Вы также можете использовать сетевые сайты, чтобы включить и настроить экстренные вызовы.</span><span class="sxs-lookup"><span data-stu-id="2a588-122">You can also use network sites to enable and configure emergency calling.</span></span>

## <a name="network-subnet"></a><span data-ttu-id="2a588-123">Подсеть сети</span><span class="sxs-lookup"><span data-stu-id="2a588-123">Network subnet</span></span>

<span data-ttu-id="2a588-124">Каждую подсеть необходимо связывать с определенным сетевым сайтом.</span><span class="sxs-lookup"><span data-stu-id="2a588-124">Each subnet must be associated with a specific network site.</span></span> <span data-ttu-id="2a588-125">Расположение клиента определяется на основе подсети сети и связанного с ней сайта сети.</span><span class="sxs-lookup"><span data-stu-id="2a588-125">A client's location is determined based on the network subnet and the associated network site.</span></span> <span data-ttu-id="2a588-126">С одной сетевой сетью можно связать несколько подсетей, но нельзя связать несколько сайтов с одной и той же.</span><span class="sxs-lookup"><span data-stu-id="2a588-126">You can associate multiple subnets with the same network site but you can't associate multiple sites with the same subnet.</span></span>

<span data-ttu-id="2a588-127">Сведения подсети используются для определения сетевого сайта, на котором находится конечная точка, при инициаке нового сеанса.</span><span class="sxs-lookup"><span data-stu-id="2a588-127">Subnet information is used to determine the network site on which an endpoint is located when a new session is initiated.</span></span> <span data-ttu-id="2a588-128">Когда известно о расположении каждой из сторон в сеансе, облачная функция голосового звонка может применять эти сведения для определения обработки настройки и маршрутации звонка.</span><span class="sxs-lookup"><span data-stu-id="2a588-128">When the location of each party in a session is known, the cloud voice feature can apply that information to determine how to handle call setup or routing.</span></span>

<span data-ttu-id="2a588-129">Для каждого сетевого сайта определите, какие IP-подсети назначены каждому сетевому сайту.</span><span class="sxs-lookup"><span data-stu-id="2a588-129">For each network site, work with your network admin to determine which IP subnets are assigned to each network site.</span></span> <span data-ttu-id="2a588-130">В нашем примере сайту "Нью-Йорк" в регионе "Северная Америка" назначены следующие IP-подсети: 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24.</span><span class="sxs-lookup"><span data-stu-id="2a588-130">For example, the New York site in the North America region can be assigned the following IP subnets: 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24.</span></span> <span data-ttu-id="2a588-131">Если Гванес, который обычно работает в Скайне, переходит в офис в Нью-Йорке для обучения, включает свой компьютер и подключается к сети, его компьютер получает IP-адрес в одном из четырех диапазонов, выделенных для Москвы, например 172.29.80.103.</span><span class="sxs-lookup"><span data-stu-id="2a588-131">If Bob, who usually works in Detroit, travels to the New York office for training, turns on his computer and connects to the network, his computer will get an IP address in one of the four ranges that are allocated for New York, for example, 172.29.80.103.</span></span>

## <a name="trusted-ip-address"></a><span data-ttu-id="2a588-132">Надежный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="2a588-132">Trusted IP address</span></span>

<span data-ttu-id="2a588-133">Надежные IP-адреса — это внешние IP-адреса корпоративной сети.</span><span class="sxs-lookup"><span data-stu-id="2a588-133">Trusted IP addresses are the internet external IP addresses of the enterprise network.</span></span> <span data-ttu-id="2a588-134">Он определяет, находится ли конечная точка пользователя в корпоративной сети, прежде чем проверять соответствие определенного сайта.</span><span class="sxs-lookup"><span data-stu-id="2a588-134">They determine whether the user's endpoint is inside the corporate network before checking for a specific site match.</span></span>

<span data-ttu-id="2a588-135">Если внешний IP-адрес пользователя совпадает с IP-адресом, который находится в списке надежных IP-адресов, функция облачного голосового управления проверяет, чтобы определить внутреннюю подсеть, в которой находится конечная точка пользователя.</span><span class="sxs-lookup"><span data-stu-id="2a588-135">If the user's external IP address matches an IP address that's in the trusted IP address list, the cloud voice feature checks to determine the internal subnet where the user's endpoint is located.</span></span> <span data-ttu-id="2a588-136">Совпадение можно установить с IP-адресами IPv4 или IPv6 и зависит от формата IP-пакета, отправленного в параметры сети.</span><span class="sxs-lookup"><span data-stu-id="2a588-136">A match can be made against either IPv4 or IPv6 IP addresses and is dependent upon the format of the IP packet sent to the network settings.</span></span> <span data-ttu-id="2a588-137">(Если общедоступный IP-адрес имеет как IPv4, так и IPv6, необходимо добавить оба в качестве надежных IP-адресов.)</span><span class="sxs-lookup"><span data-stu-id="2a588-137">(If a public IP address has both IPv4 and IPv6, you must add both as trusted IP addresses.)</span></span>

<span data-ttu-id="2a588-138">Если внешний IP-адрес пользователя не совпадает с IP-адресом, который находится в списке надежных IP-адресов, конечная точка классифицируется как неизвестная.</span><span class="sxs-lookup"><span data-stu-id="2a588-138">If the user's external IP address doesn't match an IP address that's in the trusted IP address list, the endpoint is classified as being at an unknown location.</span></span>
