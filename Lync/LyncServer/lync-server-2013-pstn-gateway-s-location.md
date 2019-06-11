---
title: 'Lync Server 2013: расположение шлюза ТСОП'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: PSTN gateway's location
ms:assetid: 49693a35-fad3-49ee-a71e-c7e4537b79aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994031(v=OCS.15)
ms:contentKeyID: 51803940
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b897d9ce438844cde7617bb7c3e1dae086605f09
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823548"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="pstn-gateways-location-in-lync-server-2013"></a><span data-ttu-id="8b0e2-102">Расположение шлюза ТСОП в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8b0e2-102">PSTN gateway's location in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8b0e2-103">_**Тема последнего изменения:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="8b0e2-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="8b0e2-104">Для звонков через шлюзы PSTN и АТС могут потребоваться ограничения маршрутизации на основе местоположения в зависимости от расположения таких систем.</span><span class="sxs-lookup"><span data-stu-id="8b0e2-104">Calls routed via PSTN gateways and PBXs might require Location-Based Routing restrictions depending on the location of such systems.</span></span> <span data-ttu-id="8b0e2-105">Маршрутизация на основе местоположения может быть включена на уровне детализации для каждой магистральной базы данных.</span><span class="sxs-lookup"><span data-stu-id="8b0e2-105">Location-Based Routing can be enabled at the granularity on a per trunk basis.</span></span>

<span data-ttu-id="8b0e2-106">При включенной на магистральной магистрали маршрутизация на основе местоположения вводит следующий набор правил:</span><span class="sxs-lookup"><span data-stu-id="8b0e2-106">Location-Based Routing introduces the following set of rules when enabled on a trunk:</span></span>

  - <span data-ttu-id="8b0e2-107">Если маршрутизация на основе местоположения включена для каждой магистрали, правила, определенные в этой магистрали, будут применены только к вызовам, направляемым через эту магистральную линию.</span><span class="sxs-lookup"><span data-stu-id="8b0e2-107">When Location-Based Routing is enabled on a per trunk basis, the rules define on that trunk will be applied only to calls routed through that trunk.</span></span>

  - <span data-ttu-id="8b0e2-108">Чтобы не допустить беспроводного тарифа на звонки с сетевого сайта, на котором размещается веб-сайт, на котором находится шлюз PSTN, при маршрутизации на основе местоположения будет введена связь сайта сети с заданной магистральной магистрали.</span><span class="sxs-lookup"><span data-stu-id="8b0e2-108">To prevent PSTN tolls bypass where calls originate from a network site different that the network site where the PSTN gateway is located, Location-Based Routing introduces the association of a network site to a given trunk.</span></span> <span data-ttu-id="8b0e2-109">Таким образом, определяется сетевой сайт, который позволяет осуществлять маршрутизацию звонков на данную магистраль.</span><span class="sxs-lookup"><span data-stu-id="8b0e2-109">This defines the network site that allows calls to be routed to a given trunk.</span></span>

<span data-ttu-id="8b0e2-110">С маршрутизацией на основе местоположения можно включить магистральные магистрали двумя способами.</span><span class="sxs-lookup"><span data-stu-id="8b0e2-110">Trunks can be enabled for Location-Based Routing in two ways:</span></span>

  - <span data-ttu-id="8b0e2-p103">Магистраль определяется для шлюза ТСОП, который переадресовывает звонки на номер ТСОП. Входящие звонки, перенаправленные на магистраль данного типа, будут перенаправлены только на конечные точки, расположенные на том же сайте сети, что и эта магистраль.</span><span class="sxs-lookup"><span data-stu-id="8b0e2-p103">The trunk is defined for a PSTN gateway that egresses calls to the PSTN. Incoming calls routed by a trunk of this type will be routed only to endpoints located within the same network site as the trunk.</span></span>

  - <span data-ttu-id="8b0e2-113">Магистраль определен для однорангового сервера-посредника, не исходящих вызовы для пользователей PSTN и Services со старыми телефонами в статических расположениях (например, телефоны УАТС).</span><span class="sxs-lookup"><span data-stu-id="8b0e2-113">The trunk is defined for a Mediation Server peer that doesn’t egress calls to the PSTN and services users with legacy phones in a static locations (i.e. PBX phones).</span></span> <span data-ttu-id="8b0e2-114">При данной конкретной конфигурации все входящие звонки, перенаправленные на магистраль данного типа, будут считаться исходящими из того же сетевого сайта, что и эта магистраль.</span><span class="sxs-lookup"><span data-stu-id="8b0e2-114">For this particular configuration, all incoming calls routed by a trunk of this type will be considered to be originating from the same network site as the trunk.</span></span> <span data-ttu-id="8b0e2-115">Звонки от пользователей УАТС будут иметь такую же принудительную подходящую маршрутизацию, как и пользователи Lync, которые находятся на том же сайте сети, что и магистраль.</span><span class="sxs-lookup"><span data-stu-id="8b0e2-115">Calls from PBX users will have the same Location-Based Routing enforcement as Lync users who are located in the same network site as the trunk.</span></span> <span data-ttu-id="8b0e2-116">Если две системы УАТС, расположенные на разных сетевых сайтах, подключены к серверу Lync Server, маршрутизация на основе местоположения позволит перенаправить маршрут из одной конечной точки УАТС на другую конечную точку УАТС на другом сайте сети.</span><span class="sxs-lookup"><span data-stu-id="8b0e2-116">If two PBX systems located in separate network sites are connected through Lync Server, Location-Based Routing will allow routing from one PBX endpoint in one network site to another PBX endpoint in the other network site.</span></span> <span data-ttu-id="8b0e2-117">Этот сценарий не будет заблокирован с помощью маршрутизации на основе местоположения.</span><span class="sxs-lookup"><span data-stu-id="8b0e2-117">This scenario will not be blocked by Location-Based Routing.</span></span> <span data-ttu-id="8b0e2-118">В дополнение к этому сценарию и к тому же, как пользователь Lync в том же расположении, конечные точки, подключенные к одноранговым узлам сервера-источника с помощью этой конфигурации, смогут совершать и принимать звонки и от другого однорангового сервера-посредника, не направлять звонки в КТСОП (i). e. Конечная точка, подключенная к другой УАТС, независимо от сетевого сайта, с которым связан сервер-участник сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="8b0e2-118">In addition to this scenario and in a similar way as a Lync user in the same location, endpoints connected to a Mediation Server peer with this configuration will be able to make or receive calls to and from other Mediation Server peer that do not route calls to the PSTN (i.e. an endpoint connected to a different PBX) regardless of the network site to which the Mediation Server peer is associated.</span></span> <span data-ttu-id="8b0e2-119">Все входящие звонки, исходящие звонки, передачи звонков и переадресации звонков с конечными точками PSTN будут подвергаться маршрутизации на основе местоположения, чтобы использовать только шлюзы PSTN, определенные как локальные для такого сервера.</span><span class="sxs-lookup"><span data-stu-id="8b0e2-119">All inbound calls, outbound calls, call transfers and call forwards involving PSTN endpoints will be subject to Location Based Routing to use only PSTN gateways that are defined as local to such Mediation Server peer.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="8b0e2-120">См. также</span><span class="sxs-lookup"><span data-stu-id="8b0e2-120">See Also</span></span>


[<span data-ttu-id="8b0e2-121">Инструкции по маршрутизации на основе местоположения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8b0e2-121">Guidance for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-guidance-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

