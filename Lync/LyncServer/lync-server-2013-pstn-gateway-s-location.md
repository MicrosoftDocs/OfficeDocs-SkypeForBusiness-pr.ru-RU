---
title: 'Lync Server 2013: расположение шлюза PSTN'
description: 'Lync Server 2013: расположение шлюза PSTN.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PSTN gateway's location
ms:assetid: 49693a35-fad3-49ee-a71e-c7e4537b79aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994031(v=OCS.15)
ms:contentKeyID: 51803940
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4f793249908bd1f064f9038ddd90c7f5b01a61d5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565605"
---
# <a name="pstn-gateways-location-in-lync-server-2013"></a><span data-ttu-id="8ff9b-103">Расположение шлюза PSTN в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8ff9b-103">PSTN gateway's location in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8ff9b-104">_**Последнее изменение темы:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="8ff9b-104">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="8ff9b-105">Для вызовов, направляемых через шлюзы PSTN и УАТС, может потребоваться Location-Based ограничения маршрутизации в зависимости от расположения таких систем.</span><span class="sxs-lookup"><span data-stu-id="8ff9b-105">Calls routed via PSTN gateways and PBXs might require Location-Based Routing restrictions depending on the location of such systems.</span></span> <span data-ttu-id="8ff9b-106">Маршрутизация Location-Based может быть включена на уровне детализации для каждой магистрали.</span><span class="sxs-lookup"><span data-stu-id="8ff9b-106">Location-Based Routing can be enabled at the granularity on a per trunk basis.</span></span>

<span data-ttu-id="8ff9b-107">При включении магистрали Location-Based маршрутизация вводит следующий набор правил:</span><span class="sxs-lookup"><span data-stu-id="8ff9b-107">Location-Based Routing introduces the following set of rules when enabled on a trunk:</span></span>

  - <span data-ttu-id="8ff9b-108">Если для каждой магистрали включена маршрутизация Location-Based, правила, определяемые на этой магистральной линии, будут применяться только к вызовам, направляемым через эту магистраль.</span><span class="sxs-lookup"><span data-stu-id="8ff9b-108">When Location-Based Routing is enabled on a per trunk basis, the rules define on that trunk will be applied only to calls routed through that trunk.</span></span>

  - <span data-ttu-id="8ff9b-109">Чтобы не допустить использования междугородных звонков с сетевого сайта, отличающегося от сетевого сайта, на котором размещается шлюз PSTN, Location-Based маршрутизация представляет связь сетевого сайта с заданной магистралью.</span><span class="sxs-lookup"><span data-stu-id="8ff9b-109">To prevent PSTN tolls bypass where calls originate from a network site different that the network site where the PSTN gateway is located, Location-Based Routing introduces the association of a network site to a given trunk.</span></span> <span data-ttu-id="8ff9b-110">Этот параметр определяет сетевой сайт, разрешающий маршрутизацию звонков по заданному каналу магистрали.</span><span class="sxs-lookup"><span data-stu-id="8ff9b-110">This defines the network site that allows calls to be routed to a given trunk.</span></span>

<span data-ttu-id="8ff9b-111">Магистральные магистрали можно включить для маршрутизации Location-Based двумя способами:</span><span class="sxs-lookup"><span data-stu-id="8ff9b-111">Trunks can be enabled for Location-Based Routing in two ways:</span></span>

  - <span data-ttu-id="8ff9b-112">Магистраль определяется для шлюза PSTN, превратиться вызовы в PSTN.</span><span class="sxs-lookup"><span data-stu-id="8ff9b-112">The trunk is defined for a PSTN gateway that egresses calls to the PSTN.</span></span> <span data-ttu-id="8ff9b-113">Входящие вызовы, направляемые магистральной линией этого типа, будут маршрутизироваться только в конечные точки, расположенные на том же сетевом сайте, что и магистраль.</span><span class="sxs-lookup"><span data-stu-id="8ff9b-113">Incoming calls routed by a trunk of this type will be routed only to endpoints located within the same network site as the trunk.</span></span>

  - <span data-ttu-id="8ff9b-114">Магистраль задается для узла сервера-посредника, который не отбирает вызовы для пользователей PSTN и Services с устаревшими телефонами в статических расположениях (то есть УАТС-телефоны).</span><span class="sxs-lookup"><span data-stu-id="8ff9b-114">The trunk is defined for a Mediation Server peer that doesn’t egress calls to the PSTN and services users with legacy phones in a static locations (i.e. PBX phones).</span></span> <span data-ttu-id="8ff9b-115">Для этой конкретной конфигурации все входящие вызовы, направляемые магистрали этого типа, будут считаться источником с того же сетевого сайта, что и магистраль.</span><span class="sxs-lookup"><span data-stu-id="8ff9b-115">For this particular configuration, all incoming calls routed by a trunk of this type will be considered to be originating from the same network site as the trunk.</span></span> <span data-ttu-id="8ff9b-116">Вызовы от пользователей УАТС будут иметь такое же принудительное применение маршрутизации Location-Based, что и пользователи Lync, расположенные на том же сетевом сайте, что и магистраль.</span><span class="sxs-lookup"><span data-stu-id="8ff9b-116">Calls from PBX users will have the same Location-Based Routing enforcement as Lync users who are located in the same network site as the trunk.</span></span> <span data-ttu-id="8ff9b-117">Если две системы УАТС, расположенные на отдельных сетевых сайтах, подключены к серверу Lync Server, Location-Based маршрутизация разрешит маршрутизацию из одной конечной точки УАТС на одном сетевом сайте в другую конечную точку УАТС на другом сетевом сайте.</span><span class="sxs-lookup"><span data-stu-id="8ff9b-117">If two PBX systems located in separate network sites are connected through Lync Server, Location-Based Routing will allow routing from one PBX endpoint in one network site to another PBX endpoint in the other network site.</span></span> <span data-ttu-id="8ff9b-118">Этот сценарий не будет заблокирован при Location-Basedной маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="8ff9b-118">This scenario will not be blocked by Location-Based Routing.</span></span> <span data-ttu-id="8ff9b-119">В дополнение к этому сценарию и аналогично тому, как пользователь Lync в том же расположении, конечные точки, подключенные к одноранговому серверу-посреднику с такой конфигурацией, смогут совершать или принимать звонки на другой узел сервера-посредника, который не направляют вызовы в PSTN (то есть конечную точку, подключенную к другой УАТС) независимо от сетевого сайта, с которым связан</span><span class="sxs-lookup"><span data-stu-id="8ff9b-119">In addition to this scenario and in a similar way as a Lync user in the same location, endpoints connected to a Mediation Server peer with this configuration will be able to make or receive calls to and from other Mediation Server peer that do not route calls to the PSTN (i.e. an endpoint connected to a different PBX) regardless of the network site to which the Mediation Server peer is associated.</span></span> <span data-ttu-id="8ff9b-120">Все входящие звонки, исходящие звонки, передачи звонков и переадресации звонков, связанные с конечными точками PSTN, будут подвергаться маршрутизации на основе расположения для использования только шлюзов PSTN, определенных как локальные для такого сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="8ff9b-120">All inbound calls, outbound calls, call transfers and call forwards involving PSTN endpoints will be subject to Location Based Routing to use only PSTN gateways that are defined as local to such Mediation Server peer.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="8ff9b-121">См. также</span><span class="sxs-lookup"><span data-stu-id="8ff9b-121">See Also</span></span>


[<span data-ttu-id="8ff9b-122">Руководство по маршрутизации Location-Based в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8ff9b-122">Guidance for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-guidance-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

