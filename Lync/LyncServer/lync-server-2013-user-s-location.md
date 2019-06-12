---
title: 'Lync Server 2013: расположение пользователя'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: User's location
ms:assetid: ce57941d-086b-448e-8ada-c7d636a2a1c9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994073(v=OCS.15)
ms:contentKeyID: 51803984
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4e9eac8fce71d99e0817c57841e2539ed6423f2a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849291"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="users-location-in-lync-server-2013"></a><span data-ttu-id="db6d1-102">Расположение пользователя в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="db6d1-102">User's location in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="db6d1-103">_**Тема последнего изменения:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="db6d1-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="db6d1-104">Маршрутизация на основе местоположения использует те же сетевые регионы, сайты и подсети, определенные в Lync Server, которые используются в E9-1-1, CAC и мультимедиа, чтобы применить ограничения маршрутизации вызовов для предотвращения беспроводного звонка по протоколу PSTN.</span><span class="sxs-lookup"><span data-stu-id="db6d1-104">Location-Based Routing leverages the same network regions, sites and subnets as defined in Lync Server used by E9-1-1, CAC and Media Bypass to apply call routing restrictions to prevent PSTN toll bypass.</span></span> <span data-ttu-id="db6d1-105">Расположение пользователя определяется IP-подсетью, из которой подключены конечные точки пользователя Lync.</span><span class="sxs-lookup"><span data-stu-id="db6d1-105">A user’s location is determined by the IP subnet of the user’s Lync endpoint(s) are connected from.</span></span> <span data-ttu-id="db6d1-106">Каждая IP-подсеть связана с сетевым сайтом, которые объединяются в сетевых областях, определяемых администратором.</span><span class="sxs-lookup"><span data-stu-id="db6d1-106">Each IP subnet is associated to a network site, which are aggregated into network regions defined by the administrator.</span></span> <span data-ttu-id="db6d1-107">Маршрутизация на основе расположения применяется исходя из сайта сети данного пользователя.</span><span class="sxs-lookup"><span data-stu-id="db6d1-107">Location-Based Routing is enforced based on the user’s network site.</span></span>

<span data-ttu-id="db6d1-108">Правила маршрутизации, основанные на расположении, применяются к каждому сетевому сайту, что означает, что данный набор правил будет применяться ко всем конечным точкам, которые включены для маршрутизации на основе местоположения и находятся на одном сайте сети.</span><span class="sxs-lookup"><span data-stu-id="db6d1-108">Location-Based Routing rules are applied on a per network site basis, meaning that a given set of rules will be applied to all endpoints enabled for Location-Based Routing that are located within the same network site.</span></span> <span data-ttu-id="db6d1-109">Администраторы могут применять маршрутизацию на основе местоположения к сетевым сайтам, которым он необходим.</span><span class="sxs-lookup"><span data-stu-id="db6d1-109">Administrators can apply Location-Based Routing to network sites that require it.</span></span>

<span data-ttu-id="db6d1-110">Политики маршрутизации голосовой связи могут задаваться для каждого отдельного сетевого сайта для выявления конкретного шлюза ТСОП, через который все пользователи, расположенные на этом сайте, должны звонить на телефонные номера ТСОП.</span><span class="sxs-lookup"><span data-stu-id="db6d1-110">Voice routing policies can be defined on a per network site basis to define a particular PSTN gateway that should be used by all users located in the network site to call PSTN phone numbers.</span></span> <span data-ttu-id="db6d1-111">Такие политики маршрутизации голосовой связи будут иметь приоритет перед маршрутизацией, определяемой политикой голосовой связи пользователя, когда пользователь находится на сетевом сайте, поддерживающем маршрутизацию на основе местоположения, и это не помешает маршрутизации звонков через другие шлюзы PSTN, которые включены для Маршрутизация на основе местоположения.</span><span class="sxs-lookup"><span data-stu-id="db6d1-111">Such voice routing policies will take precedence over the routing defined by the user’s voice policy when the user is located in a network site enabled for Location-Based Routing, and it will prevent the routing of calls via other PSTN gateways that are enabled for Location-Based Routing.</span></span> <span data-ttu-id="db6d1-112">Когда пользователь Lync помещает Звонок по коммутируемой телефонной сети, политика голосовой связи пользователя определяет, может ли пользователь быть уполномочен на вызов.</span><span class="sxs-lookup"><span data-stu-id="db6d1-112">When a Lync user places a PSTN call, the user’s voice policy determines whether the user can be authorized to place the call.</span></span> <span data-ttu-id="db6d1-113">Если пользователь попытается выполнить вызов, то маршрутизация на основе местоположения определяет шлюз PSTN, с которого будет происходить звонок.</span><span class="sxs-lookup"><span data-stu-id="db6d1-113">If the user’s voice policy allows the user to place the call, Location-Based Routing determines which PSTN gateway the call should egress from.</span></span> <span data-ttu-id="db6d1-114">Маршрутизация на основе местоположения обеспечивает это определение в зависимости от местонахождения пользователя.</span><span class="sxs-lookup"><span data-stu-id="db6d1-114">Location-Based Routing makes this determination based on the user’s location.</span></span>

<span data-ttu-id="db6d1-115">Местоположение пользователя может относиться к одному из перечисленных ниже типов.</span><span class="sxs-lookup"><span data-stu-id="db6d1-115">A user location can be categorized in the following ways:</span></span>

  - <span data-ttu-id="db6d1-116">Пользователь находится на известном сетевом сайте, для которого включена маршрутизация на основе местоположения, а его номер (прямой звонок) завершается на шлюзе PSTN, который размещен на том же сайте сети (например, Office).</span><span class="sxs-lookup"><span data-stu-id="db6d1-116">The user is located in a known network site enabled for Location-Based Routing and his DID (Direct Inward Dial) number terminates on a PSTN gateway placed in the same network site (i.e. office).</span></span> <span data-ttu-id="db6d1-117">Маршрутизация исходящих звонков будет осуществляться на основе политики маршрутизации голосовой связи сетевого сайта, на котором расположен пользователь.</span><span class="sxs-lookup"><span data-stu-id="db6d1-117">The routing of outbound calls will be through the voice routing policy of the network site in which the user is located.</span></span> <span data-ttu-id="db6d1-118">Входящие звонки ТСОП данному пользователю маршрутизируются на конечные точки, которые расположены на том же сетевом сайте, что и шлюз ТСОП.</span><span class="sxs-lookup"><span data-stu-id="db6d1-118">Incoming PSTN calls to the user are routed to endpoints that are located in the same network site as the PSTN gateway.</span></span>

  - <span data-ttu-id="db6d1-p105">Пользователь расположен на известном сайте сети, отличном от того, в котором расположен шлюз ТСОП (например, пользователь перешел в другой офис того же предприятия). Маршрутизация исходящих звонков будет выполняться на основе политики маршрутизации голосовой связи сайта сети, в котором расположен пользователь. Входящие звонки ТСОП данному пользователю не будут направляться на конечные точки, расположенные в отличных от сайта ТСОП сайтах, чтобы избежать обхода платных звонков ТСОП.</span><span class="sxs-lookup"><span data-stu-id="db6d1-p105">The user is located in a known network site that is in different from the network site where the PSTN gateway is located. (i.e. the user traveled to another corporate office). The routing of outbound calls will be using the voice routing policy of the network site in which the user is located. Incoming PSTN calls to the user will not be routed to endpoints that are located in different sites than the PSTN gateway to prevent PSTN toll bypassing.</span></span>

  - <span data-ttu-id="db6d1-123">Если пользователь находится на сетевом сайте, неизвестном для развертывания Lync Server, Маршрутизация исходящих вызовов будет основываться на политике голосовой связи, назначенной пользователю для шлюзов PSTN, не привязанных к ограничениям маршрутизации на основе местоположения.</span><span class="sxs-lookup"><span data-stu-id="db6d1-123">When a user is located in a network site that is unknown to the Lync Server deployment, the routing of outbound calls will be based on the voice policy assigned to the user to PSTN gateways not bound to Location-Based Routing restrictions.</span></span> <span data-ttu-id="db6d1-124">Входящие звонки ТСОП не будут направляться на конечные точки, расположенные на неизвестных сетевых сайтах для предотвращения обхода платных звонков ТСОП.</span><span class="sxs-lookup"><span data-stu-id="db6d1-124">Incoming PSTN calls will not be routed to endpoints that are located in unknown network sites to prevent PSTN toll bypassing.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="db6d1-125">См. также</span><span class="sxs-lookup"><span data-stu-id="db6d1-125">See Also</span></span>


[<span data-ttu-id="db6d1-126">Инструкции по маршрутизации на основе местоположения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="db6d1-126">Guidance for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-guidance-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

