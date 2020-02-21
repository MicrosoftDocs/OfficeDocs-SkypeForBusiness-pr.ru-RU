---
title: 'Lync Server 2013: расположение пользователя'
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
ms.openlocfilehash: d2e0454b5f8fc891aa878623575ee3850050ba28
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213005"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="users-location-in-lync-server-2013"></a><span data-ttu-id="ca96a-102">Расположение пользователя в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ca96a-102">User's location in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ca96a-103">_**Последнее изменение темы:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="ca96a-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="ca96a-104">Маршрутизация на основе расположения использует одни и те же области сети, сайты и подсети, как определено в Lync Server, используемый E9-1-1, CAC и обход сервера-посредника для применения ограничений маршрутизации вызовов для предотвращения бесплатных звонков по сети PSTN.</span><span class="sxs-lookup"><span data-stu-id="ca96a-104">Location-Based Routing leverages the same network regions, sites and subnets as defined in Lync Server used by E9-1-1, CAC and Media Bypass to apply call routing restrictions to prevent PSTN toll bypass.</span></span> <span data-ttu-id="ca96a-105">Расположение пользователя определяется IP-подсетью, из которой подключены конечные точки Lync пользователя.</span><span class="sxs-lookup"><span data-stu-id="ca96a-105">A user’s location is determined by the IP subnet of the user’s Lync endpoint(s) are connected from.</span></span> <span data-ttu-id="ca96a-106">Каждая IP-подсеть связана с сетевым сайтом, которые объединяются в сетевые области, определенные администратором.</span><span class="sxs-lookup"><span data-stu-id="ca96a-106">Each IP subnet is associated to a network site, which are aggregated into network regions defined by the administrator.</span></span> <span data-ttu-id="ca96a-107">Маршрутизация на основе расположения применяется на основе сетевого сайта пользователя.</span><span class="sxs-lookup"><span data-stu-id="ca96a-107">Location-Based Routing is enforced based on the user’s network site.</span></span>

<span data-ttu-id="ca96a-108">Правила маршрутизации на основе расположения применяются к отдельному сетевому сайту, что означает, что заданный набор правил будет применен ко всем конечным точкам, включенным для маршрутизации на основе расположения, расположенной в пределах одного сетевого сайта.</span><span class="sxs-lookup"><span data-stu-id="ca96a-108">Location-Based Routing rules are applied on a per network site basis, meaning that a given set of rules will be applied to all endpoints enabled for Location-Based Routing that are located within the same network site.</span></span> <span data-ttu-id="ca96a-109">Администраторы могут применять маршрутизацию на основе расположения к сетевым сайтам, которым она необходима.</span><span class="sxs-lookup"><span data-stu-id="ca96a-109">Administrators can apply Location-Based Routing to network sites that require it.</span></span>

<span data-ttu-id="ca96a-110">Политики маршрутизации голосовой связи можно определить для каждого сетевого сайта, чтобы определить конкретный шлюз PSTN, который будет использоваться всеми пользователями, находящимися на сетевом сайте, для вызова телефонных номеров PSTN.</span><span class="sxs-lookup"><span data-stu-id="ca96a-110">Voice routing policies can be defined on a per network site basis to define a particular PSTN gateway that should be used by all users located in the network site to call PSTN phone numbers.</span></span> <span data-ttu-id="ca96a-111">Такие политики маршрутизации голосовых вызовов имеют приоритет перед маршрутизацией, определенной политикой голосовой связи пользователя, когда пользователь находится на сетевом сайте, для которого включена маршрутизация на основе расположения, и он предотвращает маршрутизацию вызовов через другие шлюзы PSTN, которые включены для Маршрутизация на основе расположения.</span><span class="sxs-lookup"><span data-stu-id="ca96a-111">Such voice routing policies will take precedence over the routing defined by the user’s voice policy when the user is located in a network site enabled for Location-Based Routing, and it will prevent the routing of calls via other PSTN gateways that are enabled for Location-Based Routing.</span></span> <span data-ttu-id="ca96a-112">Когда пользователь Lync помещает Звонок PSTN, политика голосовой связи пользователя определяет, может ли пользователь быть авторизован для совершения звонка.</span><span class="sxs-lookup"><span data-stu-id="ca96a-112">When a Lync user places a PSTN call, the user’s voice policy determines whether the user can be authorized to place the call.</span></span> <span data-ttu-id="ca96a-113">Если политика голосовой связи пользователя позволяет пользователю выполнять вызов, маршрутизация на основе расположения определяет шлюз PSTN, из которого будет осуществляться вызов.</span><span class="sxs-lookup"><span data-stu-id="ca96a-113">If the user’s voice policy allows the user to place the call, Location-Based Routing determines which PSTN gateway the call should egress from.</span></span> <span data-ttu-id="ca96a-114">Маршрутизация на основе расположения делает это определение на основе расположения пользователя.</span><span class="sxs-lookup"><span data-stu-id="ca96a-114">Location-Based Routing makes this determination based on the user’s location.</span></span>

<span data-ttu-id="ca96a-115">Расположение пользователя можно классифицировать следующими способами:</span><span class="sxs-lookup"><span data-stu-id="ca96a-115">A user location can be categorized in the following ways:</span></span>

  - <span data-ttu-id="ca96a-116">Пользователь находится на известном сетевом сайте, для которого включена маршрутизация на основе расположения, а его номер (прямой вызов) завершается на шлюзе PSTN, размещенном на том же сетевом сайте (то есть Office).</span><span class="sxs-lookup"><span data-stu-id="ca96a-116">The user is located in a known network site enabled for Location-Based Routing and his DID (Direct Inward Dial) number terminates on a PSTN gateway placed in the same network site (i.e. office).</span></span> <span data-ttu-id="ca96a-117">Маршрутизация исходящих вызовов будет проходить через политику маршрутизации голосовой связи на сетевом сайте, в котором расположен пользователь.</span><span class="sxs-lookup"><span data-stu-id="ca96a-117">The routing of outbound calls will be through the voice routing policy of the network site in which the user is located.</span></span> <span data-ttu-id="ca96a-118">Входящие вызовы PSTN направляются пользователю в конечные точки, расположенные на том же сетевом сайте, что и шлюз PSTN.</span><span class="sxs-lookup"><span data-stu-id="ca96a-118">Incoming PSTN calls to the user are routed to endpoints that are located in the same network site as the PSTN gateway.</span></span>

  - <span data-ttu-id="ca96a-119">Пользователь находится на известном сетевом сайте, который отличается от сетевого сайта, на котором размещается шлюз PSTN.</span><span class="sxs-lookup"><span data-stu-id="ca96a-119">The user is located in a known network site that is in different from the network site where the PSTN gateway is located.</span></span> <span data-ttu-id="ca96a-120">(то есть пользователь в другом корпоративном офисе).</span><span class="sxs-lookup"><span data-stu-id="ca96a-120">(i.e. the user traveled to another corporate office).</span></span> <span data-ttu-id="ca96a-121">Маршрутизация исходящих вызовов будет использовать политику маршрутизации голосовых вызовов сетевого сайта, в котором расположен пользователь.</span><span class="sxs-lookup"><span data-stu-id="ca96a-121">The routing of outbound calls will be using the voice routing policy of the network site in which the user is located.</span></span> <span data-ttu-id="ca96a-122">Входящие звонки PSTN не будут перенаправляться в конечные точки, расположенные на разных сайтах, чем шлюз PSTN для предотвращения обхода бесплатных звонков по сети PSTN.</span><span class="sxs-lookup"><span data-stu-id="ca96a-122">Incoming PSTN calls to the user will not be routed to endpoints that are located in different sites than the PSTN gateway to prevent PSTN toll bypassing.</span></span>

  - <span data-ttu-id="ca96a-123">Если пользователь находится на сетевом сайте, неизвестном для развертывания Lync Server, Маршрутизация исходящих вызовов будет основана на политике голосовой связи, назначенной пользователю, шлюзам PSTN, не связанным с ограничениями маршрутизации на основе расположения.</span><span class="sxs-lookup"><span data-stu-id="ca96a-123">When a user is located in a network site that is unknown to the Lync Server deployment, the routing of outbound calls will be based on the voice policy assigned to the user to PSTN gateways not bound to Location-Based Routing restrictions.</span></span> <span data-ttu-id="ca96a-124">Входящие звонки PSTN не будут перенаправляться в конечные точки, расположенные на неизвестных сетевых сайтах, чтобы предотвратить обход звонков по сети PSTN.</span><span class="sxs-lookup"><span data-stu-id="ca96a-124">Incoming PSTN calls will not be routed to endpoints that are located in unknown network sites to prevent PSTN toll bypassing.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="ca96a-125">См. также</span><span class="sxs-lookup"><span data-stu-id="ca96a-125">See Also</span></span>


[<span data-ttu-id="ca96a-126">Руководство по маршрутизации на основе расположения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ca96a-126">Guidance for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-guidance-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

