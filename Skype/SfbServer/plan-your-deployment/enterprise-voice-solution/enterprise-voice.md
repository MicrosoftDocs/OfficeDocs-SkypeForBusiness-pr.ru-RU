---
title: Планирование корпоративной голосовой связи в Скайп Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fd8d5867-0ac9-47f8-94f0-1c3ee5e25575
description: Планирование основы в Скайп Business Server, включая сайты, регионы, сетевые связи между узлами и оценка передачи голосовых данных об использовании корпоративной голосовой связи.
ms.openlocfilehash: 413887b29a45ccdf022a4fb4c847cb0b504bb4b1
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "20977943"
---
# <a name="plan-for-enterprise-voice-in-skype-for-business-server"></a><span data-ttu-id="cf976-103">Планирование корпоративной голосовой связи в Скайп Business Server</span><span class="sxs-lookup"><span data-stu-id="cf976-103">Plan for Enterprise Voice in Skype for Business Server</span></span>
 
<span data-ttu-id="cf976-104">Планирование основы в Скайп Business Server, включая сайты, регионы, сетевые связи между узлами и оценка передачи голосовых данных об использовании корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="cf976-104">Enterprise Voice planning basics in Skype for Business Server, including sites, regions, network links between sites, and estimating voice usage traffic.</span></span>
  
<span data-ttu-id="cf976-105">Процесс развертывания для корпоративной голосовой связи зависит от существующей топологии, инфраструктуры и функциональные возможности корпоративной голосовой связи, который вы хотите обеспечить поддержку.</span><span class="sxs-lookup"><span data-stu-id="cf976-105">The deployment process for Enterprise Voice depends on your existing topology, infrastructure, and the Enterprise Voice functionality that you want to support.</span></span> <span data-ttu-id="cf976-106">Необходимые действия будут зависеть от настройки какие функции можно выбрать, но существуют другие вопросы планирования, которые необходимо выполнить на высоком уровне.</span><span class="sxs-lookup"><span data-stu-id="cf976-106">The required procedures will depend on what features you choose, but there are other planning considerations that you must make at a high level.</span></span>
  
<span data-ttu-id="cf976-107">Общие рекомендации состоят в том, чтобы учесть тип и количество развертываемых сайтов и их географическое положение, интенсивность вызовов на каждом сайте, типы сетевых каналов связи между сайтами, необходимость в избыточности и отработке отказов для функций голосовой связи на каждом сайте, а также потребность в использовании существующего оборудования УАТС.</span><span class="sxs-lookup"><span data-stu-id="cf976-107">In general, consider the type and number of sites that you want to deploy and their geographical locations, the call volume at each site, the types of network links that connect sites, whether you want to provide redundancy and failover for voice functionality for each site, and whether you want to use existing PBX equipment.</span></span> <span data-ttu-id="cf976-108">Существуют некоторые вопросы, в том числе обеспечения высокой доступности, которые следует учитывать при планировании для Скайп Business Server в целом.</span><span class="sxs-lookup"><span data-stu-id="cf976-108">There are certain considerations, such as high availability, that you should consider when you plan for Skype for Business Server as a whole.</span></span> <span data-ttu-id="cf976-109">Эти аспекты рассматриваются в данном разделе по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="cf976-109">These considerations are discussed in topics throughout this section, as needed.</span></span>
  
## <a name="sites-and-regions"></a><span data-ttu-id="cf976-110">Сайты и области</span><span class="sxs-lookup"><span data-stu-id="cf976-110">Sites and regions</span></span>

<span data-ttu-id="cf976-111">Во-первых определения сайтов в вашей топологии, где будет развертывания корпоративной голосовой связи и регионов сети, к которым принадлежат этих сайтов.</span><span class="sxs-lookup"><span data-stu-id="cf976-111">First, identify the sites in your topology where you will deploy Enterprise Voice and the network regions to which those sites belong.</span></span> <span data-ttu-id="cf976-112">В частности, рассмотрите, как вы будете обеспечивать подключение к телефонной сети общего пользования (ТСОП) для каждого узла.</span><span class="sxs-lookup"><span data-stu-id="cf976-112">In particular, consider how you will provide public switched telephone network (PSTN) connectivity to each site.</span></span> <span data-ttu-id="cf976-113">По соображениям управляемости и логистики определяющим фактором могут быть области, которым эти узлы принадлежат.</span><span class="sxs-lookup"><span data-stu-id="cf976-113">For manageability and logistical reasons, the regions to which these sites belong can be a deciding factor.</span></span> <span data-ttu-id="cf976-114">Решите, где шлюзы будет развернут локально, где будет развертываться для обеспечения связи в филиалах (SBA) и где можно настроить магистралях SIP (локально или на центральном сайте) для поставщика услуг Интернета телефонии (ITSP).</span><span class="sxs-lookup"><span data-stu-id="cf976-114">Decide where gateways will be deployed locally, where Survivable Branch Appliances (SBAs) will be deployed, and where you can configure SIP trunks (either locally or at the central site) to an Internet telephony service provider (ITSP).</span></span>
  
## <a name="network-links-between-sites"></a><span data-ttu-id="cf976-115">Сетевые каналы связи между сайтами</span><span class="sxs-lookup"><span data-stu-id="cf976-115">Network links between sites</span></span>

<span data-ttu-id="cf976-116">Также необходимо учитывать использование пропускной способности, которая должна сетевых связей между центрального сайта и сайтами филиалов.</span><span class="sxs-lookup"><span data-stu-id="cf976-116">You also need to consider the bandwidth usage that you expect on the network links between your central site and its branch sites.</span></span> <span data-ttu-id="cf976-117">Если у вас есть или планируете развернуть устойчивое каналов связи ГЛОБАЛЬНОЙ сети между сайтами, рекомендуется развернуть шлюз на каждом сайте филиала для предоставления завершение локального прямого входящего набора (DID) для пользователей на этих сайтах.</span><span class="sxs-lookup"><span data-stu-id="cf976-117">If you have, or plan to deploy, resilient WAN links between sites, we recommend that you deploy a gateway at each branch site to provide local direct inward dial (DID) termination for users at those sites.</span></span> <span data-ttu-id="cf976-118">Если устойчивые каналы глобальной сети существуют, но пропускная полоса канала глобальной сети, вероятно, будет ограничена, настройте контроль допуска звонков для этого канала.</span><span class="sxs-lookup"><span data-stu-id="cf976-118">If you have resilient WAN links, but the bandwidth on a WAN link is likely to be constrained, configure call admission control for that link.</span></span> <span data-ttu-id="cf976-119">Если у вас устойчивое каналов связи ГЛОБАЛЬНОЙ сети, узла менее 1000 пользователей на сайте филиала и нет локальной обученные Скайп для администраторов Business Server доступны, мы рекомендуем развернуть устройство для обеспечения связи в филиалах на сайте филиала.</span><span class="sxs-lookup"><span data-stu-id="cf976-119">If you do not have resilient WAN links, host fewer than 1000 users at your branch site, and do not have local trained Skype for Business Server administrators available, we recommend that you deploy a Survivable Branch Appliance at the branch site.</span></span> <span data-ttu-id="cf976-120">Если узел от 1000 до 5000 пользователей на сайте филиала, где нет устойчивого подключения к WAN и у вас есть обученные Скайп для администраторов Business Server доступны, мы рекомендуем развернуть для обеспечения связи в филиалах с небольшой шлюз на сайте филиала.</span><span class="sxs-lookup"><span data-stu-id="cf976-120">If you host between 1000 and 5000 users at your branch site, lack a resilient WAN connection, and have trained Skype for Business Server administrators available, we recommend that you deploy a Survivable Branch Server with a small gateway at the branch site.</span></span> <span data-ttu-id="cf976-121">Также рассмотрите возможность включения обхода сервера-посредника на ограниченных каналах, если у вас есть шлюз, поддерживающий обход сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="cf976-121">Consider also enabling media bypass on constrained links if you have a gateway peer that supports media bypass.</span></span>
  
## <a name="estimating-voice-usage-and-traffic"></a><span data-ttu-id="cf976-122">Оценка объема использования и трафика голосовой связи</span><span class="sxs-lookup"><span data-stu-id="cf976-122">Estimating voice usage and traffic</span></span>

<span data-ttu-id="cf976-123">Microsoft Lync Server 2013, средство планирования использует следующие показатели для оценки пользовательского трафика в каждом узле и число портов, которые необходимы для поддержки этого трафика.</span><span class="sxs-lookup"><span data-stu-id="cf976-123">The Microsoft Lync Server 2013, Planning Tool uses the following metric to estimate user traffic at each site and the number of ports that are required to support that traffic.</span></span>
  
> <span data-ttu-id="cf976-124">Для **легкого трафика** (один звонок через ТСОП на одного пользователя в час) — 15 пользователей на порт.</span><span class="sxs-lookup"><span data-stu-id="cf976-124">For **Light traffic** (one PSTN call per user per hour), figure 15 users per port.</span></span>
    
> <span data-ttu-id="cf976-125">Для **среднего трафика** (2 звонка через ТСОП на одного пользователя в час) — 10 пользователей на порт.</span><span class="sxs-lookup"><span data-stu-id="cf976-125">For **Medium traffic** (2 PSTN calls per user per hour), figure 10 users per port.</span></span>
    
> <span data-ttu-id="cf976-126">Для **тяжелого трафика** (3 или больше звонков через ТСОП на вызовы пользователя в час) — 5 пользователей на порт.</span><span class="sxs-lookup"><span data-stu-id="cf976-126">For **Heavy traffic** (3 or more PSTN per user calls per hour), figure 5 users per port.</span></span>
    
<span data-ttu-id="cf976-127">Количество портов, в свою очередь определяет количество серверов-посредников и шлюзов, которые требуется указать.</span><span class="sxs-lookup"><span data-stu-id="cf976-127">The number of ports in turn determines the number of Mediation Servers and gateways that will be required.</span></span> <span data-ttu-id="cf976-128">Шлюзы ТСОП, которые развертывают большинство организаций, могут содержать от 2 до 960 портов.</span><span class="sxs-lookup"><span data-stu-id="cf976-128">The public switched telephone network (PSTN) gateways that most organizations consider deploying range in size from 2 ports to as many as 960 ports.</span></span> <span data-ttu-id="cf976-129">(Существуют и более крупные шлюзы, но они в основном используются поставщиками услуг телефонии.)</span><span class="sxs-lookup"><span data-stu-id="cf976-129">(There are even larger gateways, but these are used mainly by telephony service providers.)</span></span>
  
<span data-ttu-id="cf976-p106">Например, организация с 10000 пользователей и средним трафиком требуется 1000 портов. Число шлюзов равно общему числу необходимых портов, что определяется общей емкостью шлюзов.</span><span class="sxs-lookup"><span data-stu-id="cf976-p106">For example, an organization with 10,000 users and medium traffic would require 1000 ports. The number of gateways required would equal the total number of ports required as determined by the total capacity of the gateways.</span></span>
  
## <a name="components-features-and-options-of-enterprise-voice"></a><span data-ttu-id="cf976-132">Компоненты, функции и параметры корпоративной голосовой связи</span><span class="sxs-lookup"><span data-stu-id="cf976-132">Components, features, and options of Enterprise Voice</span></span>

<span data-ttu-id="cf976-133">В следующих разделах для получения дополнительных сведений о планировании развертывания корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="cf976-133">See the following sections for more information on planning your Enterprise Voice deployment.</span></span>
  
- [<span data-ttu-id="cf976-134">Компоненты, необходимые для корпоративной голосовой связи в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="cf976-134">Components required for Enterprise Voice in Skype for Business Server</span></span>](components-required-for-enterprise-voice.md)
    
- [<span data-ttu-id="cf976-135">Планирование подключения к ТСОП в Скайп Business Server</span><span class="sxs-lookup"><span data-stu-id="cf976-135">Plan for PSTN connectivity in Skype for Business Server</span></span>](pstn-connectivity-0.md)
    
- [<span data-ttu-id="cf976-136">Параметры сети для расширенных функций корпоративной голосовой связи в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="cf976-136">Network settings for the advanced Enterprise Voice features in Skype for Business Server</span></span>](network-settings-for-advanced-features.md)
    
- [<span data-ttu-id="cf976-137">Планирование контроля допуска звонков в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="cf976-137">Plan for call admission control in Skype for Business Server</span></span>](call-admission-control.md)
    
- [<span data-ttu-id="cf976-138">Планирование для экстренных служб в Скайп Business Server</span><span class="sxs-lookup"><span data-stu-id="cf976-138">Plan for emergency services in Skype for Business Server</span></span>](emergency-services.md)
    
- [<span data-ttu-id="cf976-139">Планирование для сервера-посредника в Скайп для бизнеса</span><span class="sxs-lookup"><span data-stu-id="cf976-139">Plan for media bypass in Skype for Business</span></span>](media-bypass.md)
    
- [<span data-ttu-id="cf976-140">Планирование частных телефонных линий с Скайп для бизнеса</span><span class="sxs-lookup"><span data-stu-id="cf976-140">Plan for private telephone lines with Skype for Business</span></span>](private-telephone-lines.md)
    
- [<span data-ttu-id="cf976-141">Планирование зависимостью от расположения маршрутизации Скайп для бизнеса</span><span class="sxs-lookup"><span data-stu-id="cf976-141">Plan for Location-Based Routing in Skype for Business</span></span>](location-based-routing.md)
    
- [<span data-ttu-id="cf976-142">Планирование функций управления вызовами в Скайп для бизнеса</span><span class="sxs-lookup"><span data-stu-id="cf976-142">Plan for call management features in Skype for Business</span></span>](call-management-features.md)
    
- [<span data-ttu-id="cf976-143">Планирование устойчивости корпоративной голосовой связи в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="cf976-143">Plan for Enterprise Voice resiliency in Skype for Business Server</span></span>](enterprise-voice-resiliency.md)
    

