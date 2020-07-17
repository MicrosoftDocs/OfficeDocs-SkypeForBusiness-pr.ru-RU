---
title: Исследование успеха в голосовых сообщениях в Teams contoso
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
description: Исследование вариантов голосовой связи в среде Teams для международной Организации
appliesto:
- Microsoft Teams
ms.openlocfilehash: f1ba92794b2ba17cc23e1bca55800c9307707636
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786074"
---
# <a name="contoso-case-study-location-based-routing"></a><span data-ttu-id="ced85-103">Исследование успеха Contoso: Маршрутизация на основе местоположения</span><span class="sxs-lookup"><span data-stu-id="ced85-103">Contoso case study: Location-Based Routing</span></span>

<span data-ttu-id="ced85-104">Маршрутизация на основе местоположения (LBR) — это функция, которая ограничивает частотную обстановку на основе политики и физического местоположения пользователя во время помещения или приема звонка.</span><span class="sxs-lookup"><span data-stu-id="ced85-104">Location-Based Routing (LBR) is a feature that restricts toll bypass based on policy and the user's physical location at the time of placing or receiving a call.</span></span>  

## <a name="overview"></a><span data-ttu-id="ced85-105">Обзор</span><span class="sxs-lookup"><span data-stu-id="ced85-105">Overview</span></span>

<span data-ttu-id="ced85-106">Компания Contoso имеет два офиса в стране, где не разрешили обойти поставщик услуг телефонной сети общего пользования (PSTN), чтобы снизить стоимость звонков на междугородную связь.</span><span class="sxs-lookup"><span data-stu-id="ced85-106">Contoso has two offices in a country where it is illegal to bypass the Public Switched Telephone Network (PSTN) provider to decrease long-distance calling costs.</span></span> <span data-ttu-id="ced85-107">Основной офис использует подключение к Интернету, используемое главным офисом и вторым Office.</span><span class="sxs-lookup"><span data-stu-id="ced85-107">The main office has an Internet connection that is used by the main office and by the second office.</span></span> <span data-ttu-id="ced85-108">Каждый из Office использует собственный контроллер границ сеанса (SBC), подключенный к перевозчику PSTN.</span><span class="sxs-lookup"><span data-stu-id="ced85-108">Each office has their own Session Border Controller (SBC) connected to a PSTN carrier.</span></span>  
 
<span data-ttu-id="ced85-109">В этой стране компания Contoso имела LBR, настроенную для развертывания в Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="ced85-109">In this country, Contoso had LBR configured for their Skype for Business deployment.</span></span> <span data-ttu-id="ced85-110">Чтобы определить, как настроить LBR для Teams, [перенаправить план чтения Contoso для маршрутизации на основе местоположения](location-based-routing-plan.md).</span><span class="sxs-lookup"><span data-stu-id="ced85-110">To determine how to configure LBR for Teams, Contoso read [Plan Location-Based Routing for Direct Routing](location-based-routing-plan.md).</span></span> <span data-ttu-id="ced85-111">Компания Contoso определила, что в Teams и Skype для бизнеса должны выполняться те же сценарии, что и при появлении звонка, когда он может быть получен, когда звонок по коммутируемой телефонной связи может быть передан пользователю Teams, и когда вы можете передать другим пользователям Teams Звонок по коммутируемой телефонной сети.</span><span class="sxs-lookup"><span data-stu-id="ced85-111">Contoso determined that Teams and Skype for Business follow the same scenarios on when a call can be placed, when it can be received, when a PSTN call can be transferred to a Teams user, and when you can transfer another Teams user to the PSTN call.</span></span>  

<span data-ttu-id="ced85-112">Для Skype для бизнеса LBR была настроена с помощью магистрального контроллера границ (SBC) SIP, подключающегося к перевозчику PSTN.</span><span class="sxs-lookup"><span data-stu-id="ced85-112">For Skype for Business, LBR was configured with the Session Border Controller (SBC) SIP Trunk connecting to the PSTN carrier.</span></span> <span data-ttu-id="ced85-113">Для этого SBC компания Contoso проверила [список сертифицированных байтов](direct-routing-border-controllers.md) и определила, что развернутый SBC является сертифицированным для прямой маршрутизации, но не сертифицирован для пропуска мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="ced85-113">For this SBC, Contoso reviewed the [list of certified SBCs](direct-routing-border-controllers.md) and determined that the SBC deployed is certified for Direct Routing but is not certified for Media Bypass.</span></span> <span data-ttu-id="ced85-114">Для поддержки LBR необходимо, чтобы прямая маршрутизация настроилась на сайт SBC, но для этого необходимо, чтобы он был локальным выходом из Интернета, а SBC нужно настроить для обхода мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="ced85-114">To support LBR, Direct Routing needs to be configured to the SBC on-site, there needs to be a local Internet egress, and the SBC needs to be configured for Media Bypass.</span></span> <span data-ttu-id="ced85-115">На основе этих данных компания Contoso решила следующее:</span><span class="sxs-lookup"><span data-stu-id="ced85-115">Based on this information, Contoso decided the following:</span></span>

- <span data-ttu-id="ced85-116">, Чтобы отложить включение в Teams LBR, пока существующий SBC не будет сертифицирован для пропуска мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="ced85-116">To delay the enablement of Teams LBR until the existing SBC is certified for Media Bypass.</span></span>   

- <span data-ttu-id="ced85-117">Компания Contoso решила использовать SBC основного сайта в качестве прямого маршрута к Office 365.</span><span class="sxs-lookup"><span data-stu-id="ced85-117">Contoso decided to use the main site SBC for the Direct Route to Office 365.</span></span>  <span data-ttu-id="ced85-118">SBC основного сайта — это межпрокси-сервер SBC для удаленного сайта.</span><span class="sxs-lookup"><span data-stu-id="ced85-118">The main site SBC will be the proxy SBC for the remote site.</span></span>  

- <span data-ttu-id="ced85-119">Компания Contoso предпользовался сторонним консультантом, основанным на Индии, для помощи в сертификации конфигурации LBR с компанией телефонной связи в стране.</span><span class="sxs-lookup"><span data-stu-id="ced85-119">Contoso used a third-party consultant based in India to assist with certification of the LBR configuration with the telephony company in country.</span></span>  

- <span data-ttu-id="ced85-120">Для поддержки пользователей, которые работают за пределами офиса для совершения КОММУТИРУЕМых звонков, компания выпустила мобильный телефон, предоставленный сотрудникам.</span><span class="sxs-lookup"><span data-stu-id="ced85-120">To support users working from outside of the office to place PSTN calls, the company issued mobile phone was provided to their employees.</span></span> 

<span data-ttu-id="ced85-121">На приведенных ниже схемах показаны развертывания до и после для страны с правилами телефонной связи, для которых требуется маршрутизация на основе местоположения.</span><span class="sxs-lookup"><span data-stu-id="ced85-121">The following diagrams show the before and after deployments for a country with telephony regulations that require Location-Based Routing:</span></span>

<span data-ttu-id="ced85-122">**Исходное развертывание**</span><span class="sxs-lookup"><span data-stu-id="ced85-122">**Original deployment**</span></span>

![Схема, показывающая состояние Before](media/voice-case-study-5.png)

<span data-ttu-id="ced85-124">**Развертывание с прямой маршрутизацией**</span><span class="sxs-lookup"><span data-stu-id="ced85-124">**Deployment with Direct Routing**</span></span>

![Схема, показывающая состояние Before](media/voice-case-study-6.png)


## <a name="configuration"></a><span data-ttu-id="ced85-126">Настройка</span><span class="sxs-lookup"><span data-stu-id="ced85-126">Configuration:</span></span> 

<span data-ttu-id="ced85-127">Чтобы настроить сетевые компоненты в Teams, компания Contoso представит инструкции в разделе [Управление топологией сети для функций голосовой связи в облаке](manage-your-network-topology.md).</span><span class="sxs-lookup"><span data-stu-id="ced85-127">To configure the network components in Teams, Contoso followed the instructions in [Manage your network topology for cloud voice features](manage-your-network-topology.md).</span></span> <span data-ttu-id="ced85-128">Компания Contoso завершила указанные ниже действия, чтобы настроить маршрутизацию на основе местоположения.</span><span class="sxs-lookup"><span data-stu-id="ced85-128">Contoso completed the below steps to configure Location-Based Routing:</span></span> 

- <span data-ttu-id="ced85-129">Определение регионов сети — определен один сетевой регион.</span><span class="sxs-lookup"><span data-stu-id="ced85-129">Define Network regions -  One network region was defined.</span></span> 

- <span data-ttu-id="ced85-130">Определение сетевых сайтов — определено два сетевых сайта.</span><span class="sxs-lookup"><span data-stu-id="ced85-130">Define Network sites - Two network sites were defined.</span></span> <span data-ttu-id="ced85-131">Один сайт для каждого местоположения Office в регионе.</span><span class="sxs-lookup"><span data-stu-id="ced85-131">One site for each office location in the region.</span></span>

- <span data-ttu-id="ced85-132">Определение сетевых подсетей — каждое этаж в местоположении офиса имеет собственную подсеть для проводных и беспроводных сетей.</span><span class="sxs-lookup"><span data-stu-id="ced85-132">Define Network subnets - Each floor within an office location has their own subnet for the wired and wireless network.</span></span> <span data-ttu-id="ced85-133">Эта конфигурация привела к 20 подсетям для contoso.</span><span class="sxs-lookup"><span data-stu-id="ced85-133">This configuration resulted in 20 subnets for Contoso.</span></span> 

- <span data-ttu-id="ced85-134">Определение доверенных IP-адресов — внешние IP-адреса для SBC были добавлены в доверенный IP-адрес.</span><span class="sxs-lookup"><span data-stu-id="ced85-134">Define trusted IP addresses - The external facing IP addresses for the SBC were added to the trusted IP address.</span></span>  

