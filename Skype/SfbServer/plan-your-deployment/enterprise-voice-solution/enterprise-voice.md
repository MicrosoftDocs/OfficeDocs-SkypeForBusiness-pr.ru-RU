---
title: Планирование корпоративной голосовой связи в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Общие сведения о планировании корпоративной голосовой связи в Skype для бизнеса Server, включая сайты, регионы, сетевые связи между сайтами и оценку трафика голосовой связи.
ms.openlocfilehash: 7ef2a37a1ab39dd9c2e40544e06cfb995e846f7a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802899"
---
# <a name="plan-for-enterprise-voice-in-skype-for-business-server"></a><span data-ttu-id="090d2-103">Планирование корпоративной голосовой связи в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="090d2-103">Plan for Enterprise Voice in Skype for Business Server</span></span>
 
<span data-ttu-id="090d2-104">Общие сведения о планировании корпоративной голосовой связи в Skype для бизнеса Server, включая сайты, регионы, сетевые связи между сайтами и оценку трафика голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="090d2-104">Enterprise Voice planning basics in Skype for Business Server, including sites, regions, network links between sites, and estimating voice usage traffic.</span></span>
  
<span data-ttu-id="090d2-105">Процесс развертывания для корпоративной голосовой связи зависит от существующей топологии, инфраструктуры и функций корпоративной голосовой связи, которые требуется поддерживать.</span><span class="sxs-lookup"><span data-stu-id="090d2-105">The deployment process for Enterprise Voice depends on your existing topology, infrastructure, and the Enterprise Voice functionality that you want to support.</span></span> <span data-ttu-id="090d2-106">Необходимые процедуры будут зависеть от выбранных функций, но есть и другие вопросы планирования, которые необходимо выполнить на высоком уровне.</span><span class="sxs-lookup"><span data-stu-id="090d2-106">The required procedures will depend on what features you choose, but there are other planning considerations that you must make at a high level.</span></span>
  
<span data-ttu-id="090d2-107">Общие рекомендации состоят в том, чтобы учесть тип и количество развертываемых сайтов и их географическое положение, интенсивность вызовов на каждом сайте, типы сетевых каналов связи между сайтами, необходимость в избыточности и отработке отказов для функций голосовой связи на каждом сайте, а также потребность в использовании существующего оборудования УАТС.</span><span class="sxs-lookup"><span data-stu-id="090d2-107">In general, consider the type and number of sites that you want to deploy and their geographical locations, the call volume at each site, the types of network links that connect sites, whether you want to provide redundancy and failover for voice functionality for each site, and whether you want to use existing PBX equipment.</span></span> <span data-ttu-id="090d2-108">Существуют некоторые особенности, такие как высокая доступность, которые следует учитывать при планировании Skype для бизнеса Server в целом.</span><span class="sxs-lookup"><span data-stu-id="090d2-108">There are certain considerations, such as high availability, that you should consider when you plan for Skype for Business Server as a whole.</span></span> <span data-ttu-id="090d2-109">Эти аспекты рассматриваются в данном разделе по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="090d2-109">These considerations are discussed in topics throughout this section, as needed.</span></span>
  
## <a name="sites-and-regions"></a><span data-ttu-id="090d2-110">Сайты и области</span><span class="sxs-lookup"><span data-stu-id="090d2-110">Sites and regions</span></span>

<span data-ttu-id="090d2-111">Сначала определите сайты в вашей топологии, в которых будут развертываться Корпоративная голосовая связь и регионы сети, к которым принадлежат эти сайты.</span><span class="sxs-lookup"><span data-stu-id="090d2-111">First, identify the sites in your topology where you will deploy Enterprise Voice and the network regions to which those sites belong.</span></span> <span data-ttu-id="090d2-112">В частности, рассмотрите, как вы будете обеспечивать подключение к телефонной сети общего пользования (ТСОП) для каждого узла.</span><span class="sxs-lookup"><span data-stu-id="090d2-112">In particular, consider how you will provide public switched telephone network (PSTN) connectivity to each site.</span></span> <span data-ttu-id="090d2-113">По соображениям управляемости и логистики определяющим фактором могут быть области, которым эти узлы принадлежат.</span><span class="sxs-lookup"><span data-stu-id="090d2-113">For manageability and logistical reasons, the regions to which these sites belong can be a deciding factor.</span></span> <span data-ttu-id="090d2-114">Решите, где будут развертываться шлюзы, где будут развертываться бесперебойные устройства филиалов (Сбас) и где можно настроить магистральные магистрали SIP (как на локальном компьютере, так и на центральном сайте) с поставщиком услуг телефонной связи через Интернет (ИТСП).</span><span class="sxs-lookup"><span data-stu-id="090d2-114">Decide where gateways will be deployed locally, where Survivable Branch Appliances (SBAs) will be deployed, and where you can configure SIP trunks (either locally or at the central site) to an Internet telephony service provider (ITSP).</span></span>
  
## <a name="network-links-between-sites"></a><span data-ttu-id="090d2-115">Сетевые каналы связи между сайтами</span><span class="sxs-lookup"><span data-stu-id="090d2-115">Network links between sites</span></span>

<span data-ttu-id="090d2-116">Кроме того, необходимо проанализировать использование пропускной способности, которое ожидается в сетевых связях между центральным сайтом и его сайтами филиалов.</span><span class="sxs-lookup"><span data-stu-id="090d2-116">You also need to consider the bandwidth usage that you expect on the network links between your central site and its branch sites.</span></span> <span data-ttu-id="090d2-117">Если вы или планируете развертывание, отказоустойчивая WAN Links между сайтами, мы рекомендуем вам развернуть шлюз на каждом сайте филиала, чтобы обеспечить локальное прекращение сеанса для пользователей на этих сайтах.</span><span class="sxs-lookup"><span data-stu-id="090d2-117">If you have, or plan to deploy, resilient WAN links between sites, we recommend that you deploy a gateway at each branch site to provide local direct inward dial (DID) termination for users at those sites.</span></span> <span data-ttu-id="090d2-118">Если устойчивые каналы глобальной сети существуют, но пропускная полоса канала глобальной сети, вероятно, будет ограничена, настройте контроль допуска звонков для этого канала.</span><span class="sxs-lookup"><span data-stu-id="090d2-118">If you have resilient WAN links, but the bandwidth on a WAN link is likely to be constrained, configure call admission control for that link.</span></span> <span data-ttu-id="090d2-119">Если вы не обладаете устойчивыми ссылками на глобальную сеть, не разместите на сайте филиала менее 1000 пользователей, а также не прошли локальные опытные администраторы Skype для бизнеса Server, мы рекомендуем развернуть бесперебойно работающее устройство филиала на сайте филиала.</span><span class="sxs-lookup"><span data-stu-id="090d2-119">If you do not have resilient WAN links, host fewer than 1000 users at your branch site, and do not have local trained Skype for Business Server administrators available, we recommend that you deploy a Survivable Branch Appliance at the branch site.</span></span> <span data-ttu-id="090d2-120">Если вы размещаете пользователей 1000 и 5000 на сайте филиала, не можете использовать устойчивое подключение к глобальной сети и прошли обучение администраторам Skype для бизнеса Server, мы рекомендуем развернуть бесперебойный сервер с небольшим шлюзом на сайте филиала.</span><span class="sxs-lookup"><span data-stu-id="090d2-120">If you host between 1000 and 5000 users at your branch site, lack a resilient WAN connection, and have trained Skype for Business Server administrators available, we recommend that you deploy a Survivable Branch Server with a small gateway at the branch site.</span></span> <span data-ttu-id="090d2-121">Также рассмотрите возможность включения обхода сервера-посредника на ограниченных каналах, если у вас есть шлюз, поддерживающий обход сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="090d2-121">Consider also enabling media bypass on constrained links if you have a gateway peer that supports media bypass.</span></span>
  
## <a name="estimating-voice-usage-and-traffic"></a><span data-ttu-id="090d2-122">Оценка объема использования и трафика голосовой связи</span><span class="sxs-lookup"><span data-stu-id="090d2-122">Estimating voice usage and traffic</span></span>

<span data-ttu-id="090d2-123">Microsoft Lync Server 2013, средство планирования использует следующие показатели для оценки трафика пользователей на каждом сайте и количество портов, необходимых для поддержки этого трафика.</span><span class="sxs-lookup"><span data-stu-id="090d2-123">The Microsoft Lync Server 2013, Planning Tool uses the following metric to estimate user traffic at each site and the number of ports that are required to support that traffic.</span></span>
  
> <span data-ttu-id="090d2-124">Для **легкого трафика** (один звонок через ТСОП на одного пользователя в час) — 15 пользователей на порт.</span><span class="sxs-lookup"><span data-stu-id="090d2-124">For **Light traffic** (one PSTN call per user per hour), figure 15 users per port.</span></span>
> 
> <span data-ttu-id="090d2-125">Для **среднего трафика** (2 звонка через ТСОП на одного пользователя в час) — 10 пользователей на порт.</span><span class="sxs-lookup"><span data-stu-id="090d2-125">For **Medium traffic** (2 PSTN calls per user per hour), figure 10 users per port.</span></span>
> 
> <span data-ttu-id="090d2-126">Для **тяжелого трафика** (3 или больше звонков через ТСОП на вызовы пользователя в час) — 5 пользователей на порт.</span><span class="sxs-lookup"><span data-stu-id="090d2-126">For **Heavy traffic** (3 or more PSTN per user calls per hour), figure 5 users per port.</span></span>
    
<span data-ttu-id="090d2-127">Число портов, в свою очередь, определяет количество серверов и шлюзов, которые должны быть необходимы.</span><span class="sxs-lookup"><span data-stu-id="090d2-127">The number of ports in turn determines the number of Mediation Servers and gateways that will be required.</span></span> <span data-ttu-id="090d2-128">Шлюзы ТСОП, которые развертывают большинство организаций, могут содержать от 2 до 960 портов.</span><span class="sxs-lookup"><span data-stu-id="090d2-128">The public switched telephone network (PSTN) gateways that most organizations consider deploying range in size from 2 ports to as many as 960 ports.</span></span> <span data-ttu-id="090d2-129">(Существуют и более крупные шлюзы, но они в основном используются поставщиками услуг телефонии.)</span><span class="sxs-lookup"><span data-stu-id="090d2-129">(There are even larger gateways, but these are used mainly by telephony service providers.)</span></span>
  
<span data-ttu-id="090d2-p106">Например, организация с 10000 пользователей и средним трафиком требуется 1000 портов. Число шлюзов равно общему числу необходимых портов, что определяется общей емкостью шлюзов.</span><span class="sxs-lookup"><span data-stu-id="090d2-p106">For example, an organization with 10,000 users and medium traffic would require 1000 ports. The number of gateways required would equal the total number of ports required as determined by the total capacity of the gateways.</span></span>
  
## <a name="components-features-and-options-of-enterprise-voice"></a><span data-ttu-id="090d2-132">Компоненты, возможности и параметры корпоративного голосовой связи</span><span class="sxs-lookup"><span data-stu-id="090d2-132">Components, features, and options of Enterprise Voice</span></span>

<span data-ttu-id="090d2-133">Ознакомьтесь со следующими разделами, чтобы получить дополнительные сведения о планировании развертывания корпоративных голосовых сообщений.</span><span class="sxs-lookup"><span data-stu-id="090d2-133">See the following sections for more information on planning your Enterprise Voice deployment.</span></span>
  
- [<span data-ttu-id="090d2-134">Компоненты, необходимые для корпоративной голосовой связи в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="090d2-134">Components required for Enterprise Voice in Skype for Business Server</span></span>](components-required-for-enterprise-voice.md)
    
- [<span data-ttu-id="090d2-135">Планирование подключения к PSTN в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="090d2-135">Plan for PSTN connectivity in Skype for Business Server</span></span>](pstn-connectivity-0.md)
    
- [<span data-ttu-id="090d2-136">Сетевые параметры для расширенных функций голосовой связи в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="090d2-136">Network settings for the advanced Enterprise Voice features in Skype for Business Server</span></span>](network-settings-for-advanced-features.md)
    
- [<span data-ttu-id="090d2-137">Планирование управления допуском звонков в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="090d2-137">Plan for call admission control in Skype for Business Server</span></span>](call-admission-control.md)
    
- [<span data-ttu-id="090d2-138">Планирование служб экстренной помощи в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="090d2-138">Plan for emergency services in Skype for Business Server</span></span>](emergency-services.md)
    
- [<span data-ttu-id="090d2-139">Планирование обхода мультимедиа в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="090d2-139">Plan for media bypass in Skype for Business</span></span>](media-bypass.md)
    
- [<span data-ttu-id="090d2-140">Планирование частных телефонных линий с помощью Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="090d2-140">Plan for private telephone lines with Skype for Business</span></span>](private-telephone-lines.md)
    
- [<span data-ttu-id="090d2-141">Планирование маршрутизации на основе местоположения в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="090d2-141">Plan for Location-Based Routing in Skype for Business</span></span>](location-based-routing.md)
    
- [<span data-ttu-id="090d2-142">Планирование функций управления звонками в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="090d2-142">Plan for call management features in Skype for Business</span></span>](call-management-features.md)
    
- [<span data-ttu-id="090d2-143">Plan for Enterprise Voice resiliency in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="090d2-143">Plan for Enterprise Voice resiliency in Skype for Business Server</span></span>](enterprise-voice-resiliency.md)
    

