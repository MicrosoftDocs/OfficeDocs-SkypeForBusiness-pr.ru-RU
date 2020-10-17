---
title: 'Lync Server 2013: расположение пользователя'
description: 'Lync Server 2013: расположение пользователя.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User's location
ms:assetid: ce57941d-086b-448e-8ada-c7d636a2a1c9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994073(v=OCS.15)
ms:contentKeyID: 51803984
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a92ec780809cdb3e1ee582ce6c348c884bbb5890
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561215"
---
# <a name="users-location-in-lync-server-2013"></a><span data-ttu-id="1988b-103">Расположение пользователя в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1988b-103">User's location in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1988b-104">_**Последнее изменение темы:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="1988b-104">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="1988b-105">Location-Based маршрутизация использует одни и те же области сети, сайты и подсети, как определено в Lync Server, используемый E9-1-1, CAC и обход сервера-посредника для применения ограничений маршрутизации вызовов для предотвращения бесплатных звонков по сети PSTN.</span><span class="sxs-lookup"><span data-stu-id="1988b-105">Location-Based Routing leverages the same network regions, sites and subnets as defined in Lync Server used by E9-1-1, CAC and Media Bypass to apply call routing restrictions to prevent PSTN toll bypass.</span></span> <span data-ttu-id="1988b-106">Расположение пользователя определяется IP-подсетью, из которой подключены конечные точки Lync пользователя.</span><span class="sxs-lookup"><span data-stu-id="1988b-106">A user’s location is determined by the IP subnet of the user’s Lync endpoint(s) are connected from.</span></span> <span data-ttu-id="1988b-107">Каждая IP-подсеть связана с сетевым сайтом, которые объединяются в сетевые области, определенные администратором.</span><span class="sxs-lookup"><span data-stu-id="1988b-107">Each IP subnet is associated to a network site, which are aggregated into network regions defined by the administrator.</span></span> <span data-ttu-id="1988b-108">Маршрутизация Location-Based применяется на основе сетевого сайта пользователя.</span><span class="sxs-lookup"><span data-stu-id="1988b-108">Location-Based Routing is enforced based on the user’s network site.</span></span>

<span data-ttu-id="1988b-109">Location-Based правила маршрутизации применяются для каждого сетевого сайта, что означает, что заданный набор правил будет применен ко всем конечным точкам, включенным для маршрутизации Location-Based, расположенным в пределах одного сетевого сайта.</span><span class="sxs-lookup"><span data-stu-id="1988b-109">Location-Based Routing rules are applied on a per network site basis, meaning that a given set of rules will be applied to all endpoints enabled for Location-Based Routing that are located within the same network site.</span></span> <span data-ttu-id="1988b-110">Администраторы могут применять Location-Based маршрутизации к сетевым сайтам, которым она необходима.</span><span class="sxs-lookup"><span data-stu-id="1988b-110">Administrators can apply Location-Based Routing to network sites that require it.</span></span>

<span data-ttu-id="1988b-111">Политики маршрутизации голосовой связи можно определить для каждого сетевого сайта, чтобы определить конкретный шлюз PSTN, который будет использоваться всеми пользователями, находящимися на сетевом сайте, для вызова телефонных номеров PSTN.</span><span class="sxs-lookup"><span data-stu-id="1988b-111">Voice routing policies can be defined on a per network site basis to define a particular PSTN gateway that should be used by all users located in the network site to call PSTN phone numbers.</span></span> <span data-ttu-id="1988b-112">Такие политики маршрутизации голосовых вызовов имеют приоритет перед маршрутизацией, определенной политикой голосовой связи пользователя, когда пользователь находится на сетевом сайте, включенном для маршрутизации Location-Based, и предотвращает маршрутизацию вызовов через другие шлюзы PSTN, для которых включена маршрутизация Location-Based.</span><span class="sxs-lookup"><span data-stu-id="1988b-112">Such voice routing policies will take precedence over the routing defined by the user’s voice policy when the user is located in a network site enabled for Location-Based Routing, and it will prevent the routing of calls via other PSTN gateways that are enabled for Location-Based Routing.</span></span> <span data-ttu-id="1988b-113">Когда пользователь Lync помещает Звонок PSTN, политика голосовой связи пользователя определяет, может ли пользователь быть авторизован для совершения звонка.</span><span class="sxs-lookup"><span data-stu-id="1988b-113">When a Lync user places a PSTN call, the user’s voice policy determines whether the user can be authorized to place the call.</span></span> <span data-ttu-id="1988b-114">Если политика голосовой связи пользователя разрешает пользователю выполнять вызов, Location-Based маршрутизация определяет шлюз PSTN, из которого будет осуществляться вызов.</span><span class="sxs-lookup"><span data-stu-id="1988b-114">If the user’s voice policy allows the user to place the call, Location-Based Routing determines which PSTN gateway the call should egress from.</span></span> <span data-ttu-id="1988b-115">Маршрутизация Location-Based выполняет это определение в зависимости от расположения пользователя.</span><span class="sxs-lookup"><span data-stu-id="1988b-115">Location-Based Routing makes this determination based on the user’s location.</span></span>

<span data-ttu-id="1988b-116">Расположение пользователя можно классифицировать следующими способами:</span><span class="sxs-lookup"><span data-stu-id="1988b-116">A user location can be categorized in the following ways:</span></span>

  - <span data-ttu-id="1988b-117">Пользователь находится на известном сетевом сайте, включенном для маршрутизации Location-Based, а его номер (прямой вызов) завершается на шлюзе PSTN, размещенном на том же сетевом сайте (например, Office).</span><span class="sxs-lookup"><span data-stu-id="1988b-117">The user is located in a known network site enabled for Location-Based Routing and his DID (Direct Inward Dial) number terminates on a PSTN gateway placed in the same network site (i.e. office).</span></span> <span data-ttu-id="1988b-118">Маршрутизация исходящих вызовов будет проходить через политику маршрутизации голосовой связи на сетевом сайте, в котором расположен пользователь.</span><span class="sxs-lookup"><span data-stu-id="1988b-118">The routing of outbound calls will be through the voice routing policy of the network site in which the user is located.</span></span> <span data-ttu-id="1988b-119">Входящие вызовы PSTN направляются пользователю в конечные точки, расположенные на том же сетевом сайте, что и шлюз PSTN.</span><span class="sxs-lookup"><span data-stu-id="1988b-119">Incoming PSTN calls to the user are routed to endpoints that are located in the same network site as the PSTN gateway.</span></span>

  - <span data-ttu-id="1988b-120">Пользователь находится на известном сетевом сайте, который отличается от сетевого сайта, на котором размещается шлюз PSTN.</span><span class="sxs-lookup"><span data-stu-id="1988b-120">The user is located in a known network site that is in different from the network site where the PSTN gateway is located.</span></span> <span data-ttu-id="1988b-121">(то есть пользователь в другом корпоративном офисе).</span><span class="sxs-lookup"><span data-stu-id="1988b-121">(i.e. the user traveled to another corporate office).</span></span> <span data-ttu-id="1988b-122">Маршрутизация исходящих вызовов будет использовать политику маршрутизации голосовых вызовов сетевого сайта, в котором расположен пользователь.</span><span class="sxs-lookup"><span data-stu-id="1988b-122">The routing of outbound calls will be using the voice routing policy of the network site in which the user is located.</span></span> <span data-ttu-id="1988b-123">Входящие звонки PSTN не будут перенаправляться в конечные точки, расположенные на разных сайтах, чем шлюз PSTN для предотвращения обхода бесплатных звонков по сети PSTN.</span><span class="sxs-lookup"><span data-stu-id="1988b-123">Incoming PSTN calls to the user will not be routed to endpoints that are located in different sites than the PSTN gateway to prevent PSTN toll bypassing.</span></span>

  - <span data-ttu-id="1988b-124">Если пользователь находится на сетевом сайте, неизвестном для развертывания Lync Server, Маршрутизация исходящих вызовов будет основана на политике голосовой связи, назначенной пользователю, на шлюзы PSTN, которые не привязаны к ограничениям маршрутизации Location-Based.</span><span class="sxs-lookup"><span data-stu-id="1988b-124">When a user is located in a network site that is unknown to the Lync Server deployment, the routing of outbound calls will be based on the voice policy assigned to the user to PSTN gateways not bound to Location-Based Routing restrictions.</span></span> <span data-ttu-id="1988b-125">Входящие звонки PSTN не будут перенаправляться в конечные точки, расположенные на неизвестных сетевых сайтах, чтобы предотвратить обход звонков по сети PSTN.</span><span class="sxs-lookup"><span data-stu-id="1988b-125">Incoming PSTN calls will not be routed to endpoints that are located in unknown network sites to prevent PSTN toll bypassing.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="1988b-126">См. также</span><span class="sxs-lookup"><span data-stu-id="1988b-126">See Also</span></span>


[<span data-ttu-id="1988b-127">Руководство по маршрутизации Location-Based в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1988b-127">Guidance for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-guidance-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

