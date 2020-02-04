---
title: 'Lync Server 2013: планирование маршрутизации на основе местоположения'
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
ms.openlocfilehash: 34a2dc25aa80e45d7e24f3a91a18b2dd83a4d554
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41751909"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="8970c-102">Планирование маршрутизации на основе местоположения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8970c-102">Planning for Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8970c-103">_**Тема последнего изменения:** 2013-07-31_</span><span class="sxs-lookup"><span data-stu-id="8970c-103">_**Topic Last Modified:** 2013-07-31_</span></span>

<span data-ttu-id="8970c-104">Сведения, представленные в данной теме, относятся к накопительным обновлениям для Lync Server 2013: февраль 2013 г.</span><span class="sxs-lookup"><span data-stu-id="8970c-104">The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>

<span data-ttu-id="8970c-105">Маршрутизация на основе местоположения позволяет ограничить маршрутизацию звонков между конечными точками VoIP и КОММУТИРУЕМыми конечными точками, основываясь на местоположении сторон в звонке.</span><span class="sxs-lookup"><span data-stu-id="8970c-105">Location-Based Routing makes it possible to restrict the routing of calls between VoIP endpoints and PSTN endpoints based on the location of the parties in the call.</span></span> <span data-ttu-id="8970c-106">Маршрутизация на основе местоположения входит в корпоративную инфраструктуру голосовой связи Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8970c-106">Location-Based Routing is part of the Lync Server 2013 Enterprise Voice infrastructure.</span></span> <span data-ttu-id="8970c-107">Маршрутизация на основе местоположения — это функция управления звонками, определяющая способ маршрутизации звонков Lync Server 2013 CU1.</span><span class="sxs-lookup"><span data-stu-id="8970c-107">Location-Based Routing is a call management feature that controls how calls are routed by Lync Server 2013 CU1.</span></span> <span data-ttu-id="8970c-108">Он принудительно устанавливает правила авторизации вызовов для направления звонков в конечные точки УАТС или PSTN, основываясь на географическом расположении вызывающего абонента Lync.</span><span class="sxs-lookup"><span data-stu-id="8970c-108">It enforces call authorization rules on whether calls can be routed to PBX or PSTN endpoints based on the Lync caller’s geographic location.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="8970c-109">Содержание</span><span class="sxs-lookup"><span data-stu-id="8970c-109">In This Section</span></span>

  - [<span data-ttu-id="8970c-110">Обзор маршрутизации на основе местоположения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8970c-110">Overview of Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-overview-of-location-based-routing.md)

  - [<span data-ttu-id="8970c-111">Инструкции по маршрутизации на основе местоположения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8970c-111">Guidance for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-guidance-for-location-based-routing.md)

  - [<span data-ttu-id="8970c-112">Сценарии маршрутизации на основе местоположения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8970c-112">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)

  - [<span data-ttu-id="8970c-113">Технические рекомендации для маршрутизации на основе расположения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8970c-113">Technical considerations for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-technical-considerations-for-location-based-routing.md)

  - [<span data-ttu-id="8970c-114">Поддержка маршрутизации на основе расположения клиентами и серверами в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8970c-114">Client and server support for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-client-and-server-support-for-location-based-routing.md)

  - [<span data-ttu-id="8970c-115">Функции, не поддерживаемые маршрутизацией на основе расположения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8970c-115">Capabilities not supported by Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-capabilities-not-supported-by-location-based-routing.md)

  - [<span data-ttu-id="8970c-116">Процесс развертывания функции маршрутизации на основе местоположения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8970c-116">Deployment process for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-location-based-routing.md)

  - [<span data-ttu-id="8970c-117">Маршрутизация на основе местоположения для конференц-связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8970c-117">Location-Based Routing for conferencing in Lync Server 2013</span></span>](lync-server-2013-location-based-routing-for-conferencing.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8970c-118">См. также</span><span class="sxs-lookup"><span data-stu-id="8970c-118">See Also</span></span>


[<span data-ttu-id="8970c-119">Планирование для корпоративного голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8970c-119">Planning for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-planning-for-enterprise-voice.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

