---
title: 'Lync Server 2013: планирование маршрутизации Location-Based'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Location-Based Routing
ms:assetid: bb035924-6b52-4f0f-8e05-b76864fb9ef3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994068(v=OCS.15)
ms:contentKeyID: 51803979
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 114f92d0963e8d61c4b0854862ff7ebd59a12b64
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48522046"
---
# <a name="planning-for-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="2cc3f-102">Планирование маршрутизации Location-Based в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2cc3f-102">Planning for Location-Based Routing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2cc3f-103">_**Последнее изменение темы:** 2013-07-31_</span><span class="sxs-lookup"><span data-stu-id="2cc3f-103">_**Topic Last Modified:** 2013-07-31_</span></span>

<span data-ttu-id="2cc3f-104">Сведения, приведенные в этом разделе, относятся к накопительным обновлениям для Lync Server 2013:2013 февраля.</span><span class="sxs-lookup"><span data-stu-id="2cc3f-104">The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>

<span data-ttu-id="2cc3f-105">Маршрутизация Location-Based позволяет ограничить маршрутизацию вызовов между конечными точками VoIP и PSTN в зависимости от расположения сторон в вызове.</span><span class="sxs-lookup"><span data-stu-id="2cc3f-105">Location-Based Routing makes it possible to restrict the routing of calls between VoIP endpoints and PSTN endpoints based on the location of the parties in the call.</span></span> <span data-ttu-id="2cc3f-106">Location-Based маршрутизация является частью инфраструктуры Lync Server 2013 Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="2cc3f-106">Location-Based Routing is part of the Lync Server 2013 Enterprise Voice infrastructure.</span></span> <span data-ttu-id="2cc3f-107">Location-Based маршрутизация — это функция управления звонками, которая управляет тем, как звонки направляются Lync Server 2013 CU1.</span><span class="sxs-lookup"><span data-stu-id="2cc3f-107">Location-Based Routing is a call management feature that controls how calls are routed by Lync Server 2013 CU1.</span></span> <span data-ttu-id="2cc3f-108">Он применяет правила авторизации вызовов для маршрутизации звонков в конечные точки УАТС или PSTN на основе географического расположения абонента Lync.</span><span class="sxs-lookup"><span data-stu-id="2cc3f-108">It enforces call authorization rules on whether calls can be routed to PBX or PSTN endpoints based on the Lync caller’s geographic location.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="2cc3f-109">Содержание</span><span class="sxs-lookup"><span data-stu-id="2cc3f-109">In This Section</span></span>

  - [<span data-ttu-id="2cc3f-110">Обзор маршрутизации Location-Based в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2cc3f-110">Overview of Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-overview-of-location-based-routing.md)

  - [<span data-ttu-id="2cc3f-111">Руководство по маршрутизации Location-Based в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2cc3f-111">Guidance for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-guidance-for-location-based-routing.md)

  - [<span data-ttu-id="2cc3f-112">Сценарии для маршрутизации Location-Based в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2cc3f-112">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)

  - [<span data-ttu-id="2cc3f-113">Технические рекомендации по маршрутизации Location-Based в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2cc3f-113">Technical considerations for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-technical-considerations-for-location-based-routing.md)

  - [<span data-ttu-id="2cc3f-114">Поддержка маршрутизации Location-Based для клиентов и серверов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2cc3f-114">Client and server support for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-client-and-server-support-for-location-based-routing.md)

  - [<span data-ttu-id="2cc3f-115">Возможности, не поддерживаемые службой маршрутизации Location-Based в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2cc3f-115">Capabilities not supported by Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-capabilities-not-supported-by-location-based-routing.md)

  - [<span data-ttu-id="2cc3f-116">Процесс развертывания для маршрутизации Location-Based в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2cc3f-116">Deployment process for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-location-based-routing.md)

  - [<span data-ttu-id="2cc3f-117">Маршрутизация на основе расположения для конференций в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2cc3f-117">Location-Based Routing for conferencing in Lync Server 2013</span></span>](lync-server-2013-location-based-routing-for-conferencing.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2cc3f-118">См. также</span><span class="sxs-lookup"><span data-stu-id="2cc3f-118">See Also</span></span>


[<span data-ttu-id="2cc3f-119">Планирование корпоративной голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2cc3f-119">Planning for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-planning-for-enterprise-voice.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

