---
title: 'Lync Server 2013: Обзор маршрутизации на основе расположения'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Location-Based Routing
ms:assetid: 4aa494bd-0d66-4335-b9e8-f758d44a7202
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994032(v=OCS.15)
ms:contentKeyID: 51803941
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7bc7320ffd8bb4d12483a882b588205d26e7e164
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051011"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="67e3b-102">Обзор маршрутизации на основе расположения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="67e3b-102">Overview of Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="67e3b-103">_**Последнее изменение темы:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="67e3b-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="67e3b-104">Маршрутизация на основе расположения вводит новый набор правил, которые изменяют маршрутизацию местных и международных звонков по PSTN, чтобы предотвратить нерекомендуемый обход.</span><span class="sxs-lookup"><span data-stu-id="67e3b-104">Location-Based Routing introduces a new set of rules that modifies the routing of national and international PSTN calls to prevent toll bypass.</span></span> <span data-ttu-id="67e3b-105">Маршрутизация на основе расположения обеспечивает гибкость для применения этих правил к определенным регионам, определенным шлюзам или только к определенному набору пользователей.</span><span class="sxs-lookup"><span data-stu-id="67e3b-105">Location-Based Routing provides the flexibility to scope these rules to specific regions, specific gateways or to specific set of users only.</span></span>

<span data-ttu-id="67e3b-106">В следующих сценариях показаны основные типы маршрутизации, основанной на расположении ограничений, могут принудительно применять:</span><span class="sxs-lookup"><span data-stu-id="67e3b-106">The following scenarios illustrate the main types of restrictions Location-Based Routing can enforce:</span></span>

  - <span data-ttu-id="67e3b-107">Входящие звонки — маршрутизация на основе расположения позволяет принудительно исходить исходящие вызовы с шлюза PSTN, расположенного в том же регионе, что и вызывающий абонент, чтобы предотвратить обход бесплатных звонков с помощью шлюза PSTN, расположенного в другом регионе объекта.</span><span class="sxs-lookup"><span data-stu-id="67e3b-107">Egress calls – Location-Based Routing can enforce outgoing calls to egress from a PSTN gateway that is located in the same region as where the caller is to prevent PSTN toll bypass, which prevents calls to egress from a PSTN gateway located in a different region as the caller.</span></span>

  - <span data-ttu-id="67e3b-108">Входные вызовы — маршрутизация на основе расположения может препятствовать входящим звонкам PSTN для звонков в конечные точки Lync, если маршрутизация шлюза PSTN не находится в том же регионе, что и Вызываемый пользователь Lync.</span><span class="sxs-lookup"><span data-stu-id="67e3b-108">Ingress calls – Location-Based Routing can prevent incoming PSTN calls to ring Lync endpoints if the PSTN gateway routing the incoming call is not located in the same region as the called Lync user.</span></span>

  - <span data-ttu-id="67e3b-109">Unknown regions — маршрутизация на основе расположения запрещает входящие и исходящие вызовы PSTN в и из пользователей, расположенных в неопределенном расположении (например, удаленные пользователи, подключающиеся из Интернета или расположенные в неизвестных регионах).</span><span class="sxs-lookup"><span data-stu-id="67e3b-109">Unknown regions – Location-Based Routing restricts incoming and outgoing PSTN calls to and from users that are located in undetermined locations (i.e. remote users connecting from the Internet or located in unknown regions).</span></span>

  - <span data-ttu-id="67e3b-110">Международные регионы — маршрутизация на основе расположения обеспечивает маршрутизацию исходящих вызовов через международные шлюзы PSTN, если не удается найти локальный шлюз для расположения пользователя.</span><span class="sxs-lookup"><span data-stu-id="67e3b-110">International regions – Location-Based Routing enforces routing of outgoing calls through international PSTN gateways if a gateway local to the user’s location cannot be found.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="67e3b-111">См. также</span><span class="sxs-lookup"><span data-stu-id="67e3b-111">See Also</span></span>


[<span data-ttu-id="67e3b-112">Планирование маршрутизации на основе расположения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="67e3b-112">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

