---
title: 'Lync Server 2013: Обзор маршрутизации Location-Based'
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
ms.openlocfilehash: 48fee2b9db45519ff4773b4dfe47b33745e5fb10
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520966"
---
# <a name="overview-of-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="b587b-102">Обзор маршрутизации Location-Based в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b587b-102">Overview of Location-Based Routing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b587b-103">_**Последнее изменение темы:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="b587b-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="b587b-104">В Location-Based маршрутизации представлен новый набор правил, которые изменяют маршрутизацию местных и международных звонков PSTN, чтобы предотвратить нерекомендуемый обход.</span><span class="sxs-lookup"><span data-stu-id="b587b-104">Location-Based Routing introduces a new set of rules that modifies the routing of national and international PSTN calls to prevent toll bypass.</span></span> <span data-ttu-id="b587b-105">Маршрутизация Location-Based обеспечивает гибкость для применения этих правил к определенным регионам, определенным шлюзам или только к определенному набору пользователей.</span><span class="sxs-lookup"><span data-stu-id="b587b-105">Location-Based Routing provides the flexibility to scope these rules to specific regions, specific gateways or to specific set of users only.</span></span>

<span data-ttu-id="b587b-106">В приведенных ниже сценариях показаны основные типы ограничений, которые Location-Based маршрутизации могут принудительно применять:</span><span class="sxs-lookup"><span data-stu-id="b587b-106">The following scenarios illustrate the main types of restrictions Location-Based Routing can enforce:</span></span>

  - <span data-ttu-id="b587b-107">Звонки исходящих вызовов — Location-Based маршрутизация позволяет принудительно исходить исходящие вызовы с шлюза PSTN, расположенного в том же регионе, что и вызывающий абонент, чтобы предотвратить обход бесплатных звонков с помощью шлюза PSTN, находящегося в другом регионе в качестве абонента.</span><span class="sxs-lookup"><span data-stu-id="b587b-107">Egress calls – Location-Based Routing can enforce outgoing calls to egress from a PSTN gateway that is located in the same region as where the caller is to prevent PSTN toll bypass, which prevents calls to egress from a PSTN gateway located in a different region as the caller.</span></span>

  - <span data-ttu-id="b587b-108">Входные звонки — Location-Based маршрутизация может препятствовать входящим звонкам PSTN на кольца конечных точек Lync, если маршрутизация шлюза PSTN не находится в том же регионе, что и Вызываемый пользователь Lync.</span><span class="sxs-lookup"><span data-stu-id="b587b-108">Ingress calls – Location-Based Routing can prevent incoming PSTN calls to ring Lync endpoints if the PSTN gateway routing the incoming call is not located in the same region as the called Lync user.</span></span>

  - <span data-ttu-id="b587b-109">Unknown regions — Location-Based маршрутизация запрещает входящие и исходящие вызовы PSTN между пользователями, находящимися в неопределенном расположении (например, удаленные пользователи, подключающиеся из Интернета или находящиеся в неизвестных регионах).</span><span class="sxs-lookup"><span data-stu-id="b587b-109">Unknown regions – Location-Based Routing restricts incoming and outgoing PSTN calls to and from users that are located in undetermined locations (i.e. remote users connecting from the Internet or located in unknown regions).</span></span>

  - <span data-ttu-id="b587b-110">Международные регионы — маршрутизация Location-Based обеспечивает маршрутизацию исходящих вызовов через международные шлюзы PSTN, если не удается найти локальный шлюз для расположения пользователя.</span><span class="sxs-lookup"><span data-stu-id="b587b-110">International regions – Location-Based Routing enforces routing of outgoing calls through international PSTN gateways if a gateway local to the user’s location cannot be found.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="b587b-111">См. также</span><span class="sxs-lookup"><span data-stu-id="b587b-111">See Also</span></span>


[<span data-ttu-id="b587b-112">Планирование маршрутизации Location-Based в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b587b-112">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

