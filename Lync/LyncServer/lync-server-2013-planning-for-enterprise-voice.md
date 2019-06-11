---
title: 'Lync Server 2013: планирование для корпоративного голосовой связи'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for Enterprise Voice
ms:assetid: fd8d5867-0ac9-47f8-94f0-1c3ee5e25575
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413081(v=OCS.15)
ms:contentKeyID: 48185959
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 29732d1690e1934f811df6fc448596e987205791
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824850"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="6e643-102">Планирование для корпоративного голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6e643-102">Planning for Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6e643-103">_**Тема последнего изменения:** 2013-11-01_</span><span class="sxs-lookup"><span data-stu-id="6e643-103">_**Topic Last Modified:** 2013-11-01_</span></span>

<span data-ttu-id="6e643-104">Процесс развертывания для корпоративной голосовой связи зависит от существующей топологии, инфраструктуры и функций корпоративной голосовой связи, которые требуется поддерживать.</span><span class="sxs-lookup"><span data-stu-id="6e643-104">The deployment process for Enterprise Voice depends on your existing topology, infrastructure, and the Enterprise Voice functionality that you want to support.</span></span> <span data-ttu-id="6e643-105">Необходимые процедуры будут зависеть от выбранных функций, но есть и другие вопросы планирования, которые необходимо выполнить на высоком уровне.</span><span class="sxs-lookup"><span data-stu-id="6e643-105">The required procedures will depend on what features you choose, but there are other planning considerations that you must make at a high level.</span></span>

<span data-ttu-id="6e643-106">Общие рекомендации состоят в том, чтобы учесть тип и количество развертываемых сайтов и их географическое положение, интенсивность вызовов на каждом сайте, типы сетевых каналов связи между сайтами, необходимость в избыточности и отработке отказов для функций голосовой связи на каждом сайте, а также потребность в использовании существующего оборудования УАТС.</span><span class="sxs-lookup"><span data-stu-id="6e643-106">In general, consider the type and number of sites that you want to deploy and their geographical locations, the call volume at each site, the types of network links that connect sites, whether you want to provide redundancy and failover for voice functionality for each site, and whether you want to use existing PBX equipment.</span></span> <span data-ttu-id="6e643-107">Существуют некоторые особенности, например высокая доступность, которые следует учитывать при планировании общего программного обеспечения для связи Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6e643-107">There are certain considerations, such as high availability, that you should consider when you plan for Lync Server  communications software as a whole.</span></span> <span data-ttu-id="6e643-108">Эти аспекты рассматриваются в данном разделе по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="6e643-108">These considerations are discussed in topics throughout this section, as needed.</span></span>

<div>

## <a name="planning-considerations"></a><span data-ttu-id="6e643-109">Вопросы планирования</span><span class="sxs-lookup"><span data-stu-id="6e643-109">Planning Considerations</span></span>

<span data-ttu-id="6e643-110">Сведения о планировании решений, относящихся к развертыванию определенной возможности голосовой связи или сценарии развертывания или компоненту, можно найти в темах этого раздела.</span><span class="sxs-lookup"><span data-stu-id="6e643-110">For planning decisions that pertain to the deployment of a particular Enterprise Voice capability or deployment scenario or component, consult the topics in this section.</span></span>

  - [<span data-ttu-id="6e643-111">Определение своих требований к корпоративной голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6e643-111">Defining your requirements for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-defining-your-requirements-for-enterprise-voice.md)

  - [<span data-ttu-id="6e643-112">Оценка объема использования и трафика голосовой связи для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6e643-112">Estimating voice usage and traffic for Lync Server 2013</span></span>](lync-server-2013-estimating-voice-usage-and-traffic.md)

  - [<span data-ttu-id="6e643-113">Network settings for the advanced Enterprise Voice features in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6e643-113">Network settings for the advanced Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md)

  - [<span data-ttu-id="6e643-114">Components required for Enterprise Voice in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6e643-114">Components required for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-components-required-for-enterprise-voice.md)

  - [<span data-ttu-id="6e643-115">Планирование устойчивости корпоративной голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6e643-115">Planning for Enterprise Voice resiliency in Lync Server 2013</span></span>](lync-server-2013-planning-for-enterprise-voice-resiliency.md)

  - [<span data-ttu-id="6e643-116">Планирование интеграции единой системы обмена сообщениями Exchange в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6e643-116">Planning for Exchange Unified Messaging integration in Lync Server 2013</span></span>](lync-server-2013-planning-for-exchange-unified-messaging-integration.md)

  - [<span data-ttu-id="6e643-117">Планирование контроля допуска звонков в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6e643-117">Planning for call admission control in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-admission-control.md)

  - [<span data-ttu-id="6e643-118">Планирование чрезвычайных служб (E9-1-1) в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6e643-118">Planning for emergency services (E9-1-1) in Lync Server 2013</span></span>](lync-server-2013-planning-for-emergency-services-e9-1-1.md)

  - [<span data-ttu-id="6e643-119">Планирование обхода серверов-посредников в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6e643-119">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)

  - [<span data-ttu-id="6e643-120">Планирование частных телефонных линий с помощью Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6e643-120">Planning for private telephone lines with Lync Server 2013</span></span>](lync-server-2013-planning-for-private-telephone-lines.md)

  - [<span data-ttu-id="6e643-121">Планирование маршрутизации на основе местоположения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6e643-121">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)

  - [<span data-ttu-id="6e643-122">Планирование устойчивости корпоративной голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6e643-122">Planning for Enterprise Voice resiliency in Lync Server 2013</span></span>](lync-server-2013-planning-for-enterprise-voice-resiliency.md)

  - [<span data-ttu-id="6e643-123">Рекомендации по развертыванию для корпоративной голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6e643-123">Deployment guidelines for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deployment-guidelines-for-enterprise-voice.md)

  - [<span data-ttu-id="6e643-124">Обзор процесса развертывания для корпоративной голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6e643-124">Deployment process overview for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deployment-process-overview-for-enterprise-voice.md)

  - [<span data-ttu-id="6e643-125">Перемещение пользователей на корпоративную голосовую связь в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6e643-125">Moving users to Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-moving-users-to-enterprise-voice.md)

  - [<span data-ttu-id="6e643-126">Средство диагностики предзвонков для Lync в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6e643-126">Lync PreCall Diagnostics Tool in Lync Server 2013</span></span>](lync-server-2013-lync-precall-diagnostics-tool.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

