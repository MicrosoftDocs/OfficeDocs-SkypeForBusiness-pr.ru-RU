---
title: 'Lync Server 2013: Обзор маршрутизации на основе местоположения'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of Location-Based Routing
ms:assetid: 4aa494bd-0d66-4335-b9e8-f758d44a7202
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994032(v=OCS.15)
ms:contentKeyID: 51803941
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 82b3a5cb2e89376a356daf54c6e5bc443ab52207
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825368"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="9af42-102">Обзор маршрутизации на основе местоположения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9af42-102">Overview of Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9af42-103">_**Тема последнего изменения:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="9af42-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="9af42-p101">Маршрутизация на основе расположения вводит новый набор правил, который изменяет маршрутизацию местных и международных звонков на номер ТСОП для предотвращения обхода платных звонков. Маршрутизация на основе расположения предоставляет гибкость для анализа этих правил в пределах определенных областей, шлюзов или только наборов пользователей.</span><span class="sxs-lookup"><span data-stu-id="9af42-p101">Location-Based Routing introduces a new set of rules that modifies the routing of national and international PSTN calls to prevent toll bypass. Location-Based Routing provides the flexibility to scope these rules to specific regions, specific gateways or to specific set of users only.</span></span>

<span data-ttu-id="9af42-106">В следующих сценариях показано, как можно принудительно использовать основные типы ограничений для маршрутизации на основе местоположения.</span><span class="sxs-lookup"><span data-stu-id="9af42-106">The following scenarios illustrate the main types of restrictions Location-Based Routing can enforce:</span></span>

  - <span data-ttu-id="9af42-107">Вызов выхода — маршрутизация на основе местоположения может принудительно применять исходящие вызовы для выхода с шлюза PSTN, который находится в той же области, что и вызывающий объект, чтобы предотвратить бесплатный звонок, что предотвращает звонки с шлюза PSTN, находящегося в другом регионе вызова.</span><span class="sxs-lookup"><span data-stu-id="9af42-107">Egress calls – Location-Based Routing can enforce outgoing calls to egress from a PSTN gateway that is located in the same region as where the caller is to prevent PSTN toll bypass, which prevents calls to egress from a PSTN gateway located in a different region as the caller.</span></span>

  - <span data-ttu-id="9af42-108">Входные вызовы – маршрутизация на основе местоположения может предотвратить входящие звонки по коммутируемой телефонной связи в конечные точки Lync, если маршрутизация шлюза PSTN не находится в той же области, что и у вызываемого пользователя Lync.</span><span class="sxs-lookup"><span data-stu-id="9af42-108">Ingress calls – Location-Based Routing can prevent incoming PSTN calls to ring Lync endpoints if the PSTN gateway routing the incoming call is not located in the same region as the called Lync user.</span></span>

  - <span data-ttu-id="9af42-109">Неизвестные регионы: Маршрутизация на основе местоположения ограничивает входящие и исходящие звонки по протоколу PSTN и от пользователей, которые находятся в неопределенном расположении (например, удаленные пользователи, подключающиеся из Интернета или расположенные в неизвестных регионах).</span><span class="sxs-lookup"><span data-stu-id="9af42-109">Unknown regions – Location-Based Routing restricts incoming and outgoing PSTN calls to and from users that are located in undetermined locations (i.e. remote users connecting from the Internet or located in unknown regions).</span></span>

  - <span data-ttu-id="9af42-110">Международные регионы: Маршрутизация на основе местоположения обеспечивает маршрутизацию исходящих звонков через международные шлюзы PSTN, если не удается найти шлюз, локальный для пользователя.</span><span class="sxs-lookup"><span data-stu-id="9af42-110">International regions – Location-Based Routing enforces routing of outgoing calls through international PSTN gateways if a gateway local to the user’s location cannot be found.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="9af42-111">См. также</span><span class="sxs-lookup"><span data-stu-id="9af42-111">See Also</span></span>


[<span data-ttu-id="9af42-112">Планирование маршрутизации на основе местоположения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9af42-112">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

