---
title: 'Teams голосом: пример: Contoso'
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: Teams на примере голосовой почты для многоязычной корпорации
appliesto:
- Microsoft Teams
ms.openlocfilehash: f1ba92794b2ba17cc23e1bca55800c9307707636
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786074"
---
# <a name="contoso-case-study-location-based-routing"></a><span data-ttu-id="2c714-103">Пример работы с Contoso: Location-Based маршруты</span><span class="sxs-lookup"><span data-stu-id="2c714-103">Contoso case study: Location-Based Routing</span></span>

<span data-ttu-id="2c714-104">Location-Based Routing (LBR) — это функция, которая ограничивает обход платных номеров на основе политики и физического местонахождения пользователя во время размещения или приема звонка.</span><span class="sxs-lookup"><span data-stu-id="2c714-104">Location-Based Routing (LBR) is a feature that restricts toll bypass based on policy and the user's physical location at the time of placing or receiving a call.</span></span>  

## <a name="overview"></a><span data-ttu-id="2c714-105">Обзор</span><span class="sxs-lookup"><span data-stu-id="2c714-105">Overview</span></span>

<span data-ttu-id="2c714-106">Contoso имеет два офиса в стране, где обходить поставщика услуг телефонной сети общего звонков (STN) запрещено, чтобы снизить затраты на междугородние звонки.</span><span class="sxs-lookup"><span data-stu-id="2c714-106">Contoso has two offices in a country where it is illegal to bypass the Public Switched Telephone Network (PSTN) provider to decrease long-distance calling costs.</span></span> <span data-ttu-id="2c714-107">В главном офисе есть подключение к Интернету, которое используется основным офисом и вторым офисом.</span><span class="sxs-lookup"><span data-stu-id="2c714-107">The main office has an Internet connection that is used by the main office and by the second office.</span></span> <span data-ttu-id="2c714-108">Каждый офис имеет собственный контроллер границы сеанса (SBC), подключенный к оператору STN.</span><span class="sxs-lookup"><span data-stu-id="2c714-108">Each office has their own Session Border Controller (SBC) connected to a PSTN carrier.</span></span>  
 
<span data-ttu-id="2c714-109">В этой стране в Contoso был настроен LBR для Skype для бизнеса развертывания.</span><span class="sxs-lookup"><span data-stu-id="2c714-109">In this country, Contoso had LBR configured for their Skype for Business deployment.</span></span> <span data-ttu-id="2c714-110">Чтобы определить, как настроить LBR для Teams, ознакомьтесь со Location-Based плана маршрутии для [прямой маршрутии](location-based-routing-plan.md)Contoso.</span><span class="sxs-lookup"><span data-stu-id="2c714-110">To determine how to configure LBR for Teams, Contoso read [Plan Location-Based Routing for Direct Routing](location-based-routing-plan.md).</span></span> <span data-ttu-id="2c714-111">Компания Contoso определила, что Teams и Skype для бизнеса должны выполнять те же действия, что и при размещении звонка, при его получении, перенаправлении звонка по ПС TEAMS пользователю и перенаправлении другого Teams пользователя на звонок по СТАНДОТ.</span><span class="sxs-lookup"><span data-stu-id="2c714-111">Contoso determined that Teams and Skype for Business follow the same scenarios on when a call can be placed, when it can be received, when a PSTN call can be transferred to a Teams user, and when you can transfer another Teams user to the PSTN call.</span></span>  

<span data-ttu-id="2c714-112">Для Skype для бизнеса, LBR был настроен с помощью SIP-контроллера SIP, подключаемой к оператору STN.</span><span class="sxs-lookup"><span data-stu-id="2c714-112">For Skype for Business, LBR was configured with the Session Border Controller (SBC) SIP Trunk connecting to the PSTN carrier.</span></span> <span data-ttu-id="2c714-113">Для этого SBC Компания Contoso просмотрела список сертифицированных УАО и определила, что развернутый SBC сертифицирован для прямой маршрутизирования, но не сертифицирован для обхода мультимедиа. [](direct-routing-border-controllers.md)</span><span class="sxs-lookup"><span data-stu-id="2c714-113">For this SBC, Contoso reviewed the [list of certified SBCs](direct-routing-border-controllers.md) and determined that the SBC deployed is certified for Direct Routing but is not certified for Media Bypass.</span></span> <span data-ttu-id="2c714-114">Для поддержки LBR необходимо настроить прямую маршрутику для локального сайта SBC, локальный доступ к Интернету, а также настроить обход мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="2c714-114">To support LBR, Direct Routing needs to be configured to the SBC on-site, there needs to be a local Internet egress, and the SBC needs to be configured for Media Bypass.</span></span> <span data-ttu-id="2c714-115">На основе этой информации компания Contoso решила следующее:</span><span class="sxs-lookup"><span data-stu-id="2c714-115">Based on this information, Contoso decided the following:</span></span>

- <span data-ttu-id="2c714-116">Чтобы отложить Teams LBR, пока существующий SBC не будет сертифицирован для обхода мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="2c714-116">To delay the enablement of Teams LBR until the existing SBC is certified for Media Bypass.</span></span>   

- <span data-ttu-id="2c714-117">Компания Contoso решила использовать основной сайт SBC для прямого маршрута Office 365.</span><span class="sxs-lookup"><span data-stu-id="2c714-117">Contoso decided to use the main site SBC for the Direct Route to Office 365.</span></span>  <span data-ttu-id="2c714-118">Основным сайтом SBC будет прокси-сервер SBC удаленного сайта.</span><span class="sxs-lookup"><span data-stu-id="2c714-118">The main site SBC will be the proxy SBC for the remote site.</span></span>  

- <span data-ttu-id="2c714-119">Contoso использовал сторонних консультантов из Индии для сертификации конфигурации LBR с телефонной компанией в стране.</span><span class="sxs-lookup"><span data-stu-id="2c714-119">Contoso used a third-party consultant based in India to assist with certification of the LBR configuration with the telephony company in country.</span></span>  

- <span data-ttu-id="2c714-120">Для поддержки пользователей, работающих за пределами офиса для звонков по ЗВОНКОВ по ННР, сотрудникам компании были предоставлены номера мобильных телефонов.</span><span class="sxs-lookup"><span data-stu-id="2c714-120">To support users working from outside of the office to place PSTN calls, the company issued mobile phone was provided to their employees.</span></span> 

<span data-ttu-id="2c714-121">На схемах ниже покажите до и после развертывания для страны с правилами телефонии, для Location-Based маршрутов:</span><span class="sxs-lookup"><span data-stu-id="2c714-121">The following diagrams show the before and after deployments for a country with telephony regulations that require Location-Based Routing:</span></span>

<span data-ttu-id="2c714-122">**Исходное развертывание**</span><span class="sxs-lookup"><span data-stu-id="2c714-122">**Original deployment**</span></span>

![Схема, показанная перед состоянием](media/voice-case-study-5.png)

<span data-ttu-id="2c714-124">**Развертывание с прямой маршрутией**</span><span class="sxs-lookup"><span data-stu-id="2c714-124">**Deployment with Direct Routing**</span></span>

![Схема, показанная перед состоянием](media/voice-case-study-6.png)


## <a name="configuration"></a><span data-ttu-id="2c714-126">Конфигурации:</span><span class="sxs-lookup"><span data-stu-id="2c714-126">Configuration:</span></span> 

<span data-ttu-id="2c714-127">Чтобы настроить сетевые компоненты в Teams, Компания Contoso, как и другие функции голосовой связи, придерживается инструкций из области Управление топологией [сети.](manage-your-network-topology.md)</span><span class="sxs-lookup"><span data-stu-id="2c714-127">To configure the network components in Teams, Contoso followed the instructions in [Manage your network topology for cloud voice features](manage-your-network-topology.md).</span></span> <span data-ttu-id="2c714-128">Contoso выполнила следующие действия по настройке Location-Based маршрутов:</span><span class="sxs-lookup"><span data-stu-id="2c714-128">Contoso completed the below steps to configure Location-Based Routing:</span></span> 

- <span data-ttu-id="2c714-129">Определение сетевых регионов— определен один сетевой регион.</span><span class="sxs-lookup"><span data-stu-id="2c714-129">Define Network regions -  One network region was defined.</span></span> 

- <span data-ttu-id="2c714-130">Определение сетевых сайтов. Определены два сетевых сайта.</span><span class="sxs-lookup"><span data-stu-id="2c714-130">Define Network sites - Two network sites were defined.</span></span> <span data-ttu-id="2c714-131">Один сайт для каждого расположения офиса в регионе.</span><span class="sxs-lookup"><span data-stu-id="2c714-131">One site for each office location in the region.</span></span>

- <span data-ttu-id="2c714-132">Определение сетевых подсетей. Каждый этаж в расположении офиса имеет собственную подсеть для проводной и беспроводной сети.</span><span class="sxs-lookup"><span data-stu-id="2c714-132">Define Network subnets - Each floor within an office location has their own subnet for the wired and wireless network.</span></span> <span data-ttu-id="2c714-133">В результате этой конфигурации для Contoso было 20 подсетей.</span><span class="sxs-lookup"><span data-stu-id="2c714-133">This configuration resulted in 20 subnets for Contoso.</span></span> 

- <span data-ttu-id="2c714-134">Определение доверенных IP-адресов. Ip-адреса внешнего внешнего адреса для SBC были добавлены на надежный IP-адрес.</span><span class="sxs-lookup"><span data-stu-id="2c714-134">Define trusted IP addresses - The external facing IP addresses for the SBC were added to the trusted IP address.</span></span>  

