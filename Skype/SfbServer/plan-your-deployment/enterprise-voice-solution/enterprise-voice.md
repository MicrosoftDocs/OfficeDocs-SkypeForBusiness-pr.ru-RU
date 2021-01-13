---
title: Планирование Корпоративная голосовая связь в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fd8d5867-0ac9-47f8-94f0-1c3ee5e25575
description: Корпоративная голосовая связь планирования в Skype для бизнеса Server, включая сайты, регионы, сетевые соединения между сайтами и оценку трафика использования голосовой связи.
ms.openlocfilehash: 8f10eed8dfcfa7a8878b673ab76fd4d1fd40cc29
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825679"
---
# <a name="plan-for-enterprise-voice-in-skype-for-business-server"></a><span data-ttu-id="bcf28-103">Планирование Корпоративная голосовая связь в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="bcf28-103">Plan for Enterprise Voice in Skype for Business Server</span></span>
 
<span data-ttu-id="bcf28-104">Корпоративная голосовая связь планирования в Skype для бизнеса Server, включая сайты, регионы, сетевые соединения между сайтами и оценку трафика использования голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="bcf28-104">Enterprise Voice planning basics in Skype for Business Server, including sites, regions, network links between sites, and estimating voice usage traffic.</span></span>
  
<span data-ttu-id="bcf28-105">Процесс развертывания Корпоративная голосовая связь зависит от существующей топологии, инфраструктуры и Корпоративная голосовая связь функций, которые вы хотите поддерживать.</span><span class="sxs-lookup"><span data-stu-id="bcf28-105">The deployment process for Enterprise Voice depends on your existing topology, infrastructure, and the Enterprise Voice functionality that you want to support.</span></span> <span data-ttu-id="bcf28-106">Необходимые процедуры зависят от того, какие функции вы выберете, но существуют другие вопросы планирования, которые необходимо учитывать на высоком уровне.</span><span class="sxs-lookup"><span data-stu-id="bcf28-106">The required procedures will depend on what features you choose, but there are other planning considerations that you must make at a high level.</span></span>
  
<span data-ttu-id="bcf28-107">В общем необходимо учесть типы и число развертываемых сайтов и их географическое расположение, объемы вызовов, обрабатываемых каждым сайтом, типы сетевых каналов между сайтами, необходимость обеспечения избыточности и отработки отказа для функций голосовой связи для каждого сайта, а также то, предполагается ли использовать имеющееся оборудование УАТС.</span><span class="sxs-lookup"><span data-stu-id="bcf28-107">In general, consider the type and number of sites that you want to deploy and their geographical locations, the call volume at each site, the types of network links that connect sites, whether you want to provide redundancy and failover for voice functionality for each site, and whether you want to use existing PBX equipment.</span></span> <span data-ttu-id="bcf28-108">При планировании Skype для бизнеса Server в целом следует учитывать некоторые аспекты, такие как высокая доступность.</span><span class="sxs-lookup"><span data-stu-id="bcf28-108">There are certain considerations, such as high availability, that you should consider when you plan for Skype for Business Server as a whole.</span></span> <span data-ttu-id="bcf28-109">Эти аспекты также рассматриваются в статьях данного раздела.</span><span class="sxs-lookup"><span data-stu-id="bcf28-109">These considerations are discussed in topics throughout this section, as needed.</span></span>
  
## <a name="sites-and-regions"></a><span data-ttu-id="bcf28-110">Сайты и регионы</span><span class="sxs-lookup"><span data-stu-id="bcf28-110">Sites and regions</span></span>

<span data-ttu-id="bcf28-111">Сначала определите сайты в топологии, на которых будут развернуты Корпоративная голосовая связь и сетевые регионы, к которым относятся эти сайты.</span><span class="sxs-lookup"><span data-stu-id="bcf28-111">First, identify the sites in your topology where you will deploy Enterprise Voice and the network regions to which those sites belong.</span></span> <span data-ttu-id="bcf28-112">В частности, рассмотрите, как вы будете обеспечивать подключение к телефонной сети общего пользования (ТСОП) для каждого узла.</span><span class="sxs-lookup"><span data-stu-id="bcf28-112">In particular, consider how you will provide public switched telephone network (PSTN) connectivity to each site.</span></span> <span data-ttu-id="bcf28-113">По соображениям управляемости и логистики определяющим фактором могут быть области, которым эти узлы принадлежат.</span><span class="sxs-lookup"><span data-stu-id="bcf28-113">For manageability and logistical reasons, the regions to which these sites belong can be a deciding factor.</span></span> <span data-ttu-id="bcf28-114">Определите, где шлюзы будут развернуты локально, где будут развернуты устройства для обеспечения связи в филиалах и где можно настроить магистрали SIP (локально или на центральном сайте) для поставщика услуг интернет-телефонии (ITSP).</span><span class="sxs-lookup"><span data-stu-id="bcf28-114">Decide where gateways will be deployed locally, where Survivable Branch Appliances (SBAs) will be deployed, and where you can configure SIP trunks (either locally or at the central site) to an Internet telephony service provider (ITSP).</span></span>
  
## <a name="network-links-between-sites"></a><span data-ttu-id="bcf28-115">Сетевые соединения между сайтами</span><span class="sxs-lookup"><span data-stu-id="bcf28-115">Network links between sites</span></span>

<span data-ttu-id="bcf28-116">Кроме того, необходимо учитывать использование пропускной способности, которое ожидается на сетевых каналах между центральным сайтом и сайтами филиалов.</span><span class="sxs-lookup"><span data-stu-id="bcf28-116">You also need to consider the bandwidth usage that you expect on the network links between your central site and its branch sites.</span></span> <span data-ttu-id="bcf28-117">Если у вас есть (или планируется) развертывание устойчивых связей WAN между сайтами, рекомендуется развернуть шлюз на каждом сайте филиала, чтобы обеспечить локальное прямое внутреннее завершение набора номера (DID) для пользователей на этих сайтах.</span><span class="sxs-lookup"><span data-stu-id="bcf28-117">If you have, or plan to deploy, resilient WAN links between sites, we recommend that you deploy a gateway at each branch site to provide local direct inward dial (DID) termination for users at those sites.</span></span> <span data-ttu-id="bcf28-118">Если устойчивые каналы глобальной сети существуют, но пропускная полоса канала глобальной сети, вероятно, будет ограничена, настройте контроль допуска звонков для этого канала.</span><span class="sxs-lookup"><span data-stu-id="bcf28-118">If you have resilient WAN links, but the bandwidth on a WAN link is likely to be constrained, configure call admission control for that link.</span></span> <span data-ttu-id="bcf28-119">Если у вас нет устойчивых связей WAN, на сайте филиала размещено менее 1000 пользователей и нет доступных локальных обученных администраторов Skype для бизнеса Server, рекомендуется развернуть устройство для связи в филиалах на сайте филиала.</span><span class="sxs-lookup"><span data-stu-id="bcf28-119">If you do not have resilient WAN links, host fewer than 1000 users at your branch site, and do not have local trained Skype for Business Server administrators available, we recommend that you deploy a Survivable Branch Appliance at the branch site.</span></span> <span data-ttu-id="bcf28-120">Если на сайте филиала размещено от 1000 до 5000 пользователей, отсутствует устойчивое подключение к WAN и доступны обученные администраторы Skype для бизнеса Server, рекомендуется развернуть сервер survivable Branch Server с небольшим шлюзом на сайте филиала.</span><span class="sxs-lookup"><span data-stu-id="bcf28-120">If you host between 1000 and 5000 users at your branch site, lack a resilient WAN connection, and have trained Skype for Business Server administrators available, we recommend that you deploy a Survivable Branch Server with a small gateway at the branch site.</span></span> <span data-ttu-id="bcf28-121">Также рассмотрите возможность включения обхода сервера-посредника на ограниченных каналах, если у вас есть шлюз, поддерживающий обход сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="bcf28-121">Consider also enabling media bypass on constrained links if you have a gateway peer that supports media bypass.</span></span>
  
## <a name="estimating-voice-usage-and-traffic"></a><span data-ttu-id="bcf28-122">Оценка использования голосовой почты и трафика</span><span class="sxs-lookup"><span data-stu-id="bcf28-122">Estimating voice usage and traffic</span></span>

<span data-ttu-id="bcf28-123">Средство планирования Microsoft Lync Server 2013 использует следующую метрику для оценки пользовательского трафика на каждом сайте и количества портов, необходимых для поддержки этого трафика.</span><span class="sxs-lookup"><span data-stu-id="bcf28-123">The Microsoft Lync Server 2013, Planning Tool uses the following metric to estimate user traffic at each site and the number of ports that are required to support that traffic.</span></span>
  
> <span data-ttu-id="bcf28-124">Для **легкого трафика** (один звонок через ТСОП на одного пользователя в час) — 15 пользователей на порт.</span><span class="sxs-lookup"><span data-stu-id="bcf28-124">For **Light traffic** (one PSTN call per user per hour), figure 15 users per port.</span></span>
> 
> <span data-ttu-id="bcf28-125">Для **среднего трафика** (2 звонка через ТСОП на одного пользователя в час) — 10 пользователей на порт.</span><span class="sxs-lookup"><span data-stu-id="bcf28-125">For **Medium traffic** (2 PSTN calls per user per hour), figure 10 users per port.</span></span>
> 
> <span data-ttu-id="bcf28-126">Для **тяжелого трафика** (3 или больше звонков через ТСОП на вызовы пользователя в час) — 5 пользователей на порт.</span><span class="sxs-lookup"><span data-stu-id="bcf28-126">For **Heavy traffic** (3 or more PSTN per user calls per hour), figure 5 users per port.</span></span>
    
<span data-ttu-id="bcf28-127">Количество портов, в свою очередь, определяет необходимое количество серверов-посредников и шлюзов.</span><span class="sxs-lookup"><span data-stu-id="bcf28-127">The number of ports in turn determines the number of Mediation Servers and gateways that will be required.</span></span> <span data-ttu-id="bcf28-128">Шлюзы ТСОП, которые развертывают большинство организаций, могут содержать от 2 до 960 портов.</span><span class="sxs-lookup"><span data-stu-id="bcf28-128">The public switched telephone network (PSTN) gateways that most organizations consider deploying range in size from 2 ports to as many as 960 ports.</span></span> <span data-ttu-id="bcf28-129">(Существуют и более крупные шлюзы, но они в основном используются поставщиками услуг телефонии.)</span><span class="sxs-lookup"><span data-stu-id="bcf28-129">(There are even larger gateways, but these are used mainly by telephony service providers.)</span></span>
  
<span data-ttu-id="bcf28-p106">Например, организация с 10000 пользователей и средним трафиком требуется 1000 портов. Число шлюзов равно общему числу необходимых портов, что определяется общей емкостью шлюзов.</span><span class="sxs-lookup"><span data-stu-id="bcf28-p106">For example, an organization with 10,000 users and medium traffic would require 1000 ports. The number of gateways required would equal the total number of ports required as determined by the total capacity of the gateways.</span></span>
  
## <a name="components-features-and-options-of-enterprise-voice"></a><span data-ttu-id="bcf28-132">Компоненты, компоненты и параметры Корпоративная голосовая связь</span><span class="sxs-lookup"><span data-stu-id="bcf28-132">Components, features, and options of Enterprise Voice</span></span>

<span data-ttu-id="bcf28-133">Дополнительные сведения о планировании развертывания Корпоративная голосовая связь см. в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="bcf28-133">See the following sections for more information on planning your Enterprise Voice deployment.</span></span>
  
- [<span data-ttu-id="bcf28-134">Компоненты, необходимые для Корпоративная голосовая связь в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="bcf28-134">Components required for Enterprise Voice in Skype for Business Server</span></span>](components-required-for-enterprise-voice.md)
    
- [<span data-ttu-id="bcf28-135">Планирование подключения к STN в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="bcf28-135">Plan for PSTN connectivity in Skype for Business Server</span></span>](pstn-connectivity-0.md)
    
- [<span data-ttu-id="bcf28-136">Параметры сети для расширенных Корпоративная голосовая связь в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="bcf28-136">Network settings for the advanced Enterprise Voice features in Skype for Business Server</span></span>](network-settings-for-advanced-features.md)
    
- [<span data-ttu-id="bcf28-137">Планирование контроля допуска звонков в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="bcf28-137">Plan for call admission control in Skype for Business Server</span></span>](call-admission-control.md)
    
- [<span data-ttu-id="bcf28-138">Планирование экстренных служб в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="bcf28-138">Plan for emergency services in Skype for Business Server</span></span>](emergency-services.md)
    
- [<span data-ttu-id="bcf28-139">Планирование обхода мультимедиа в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="bcf28-139">Plan for media bypass in Skype for Business</span></span>](media-bypass.md)
    
- [<span data-ttu-id="bcf28-140">Планирование частных телефонных линий в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="bcf28-140">Plan for private telephone lines with Skype for Business</span></span>](private-telephone-lines.md)
    
- [<span data-ttu-id="bcf28-141">Планирование Location-Based маршрутов в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="bcf28-141">Plan for Location-Based Routing in Skype for Business</span></span>](location-based-routing.md)
    
- [<span data-ttu-id="bcf28-142">Планирование функций управления звонками в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="bcf28-142">Plan for call management features in Skype for Business</span></span>](call-management-features.md)
    
- [<span data-ttu-id="bcf28-143">Планирование устойчивости Корпоративная голосовая связь в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="bcf28-143">Plan for Enterprise Voice resiliency in Skype for Business Server</span></span>](enterprise-voice-resiliency.md)
    

