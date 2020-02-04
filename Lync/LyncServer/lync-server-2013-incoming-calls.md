---
title: 'Lync Server 2013: входящие звонки'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Incoming calls
ms:assetid: 65b9c1b4-6af7-4527-8c33-22c4442bd209
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994038(v=OCS.15)
ms:contentKeyID: 51803948
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e70e5a489cbfa581c666374e6535b898727e1fdc
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763803"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="incoming-calls-in-lync-server-2013"></a><span data-ttu-id="f5194-102">Входящие звонки в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f5194-102">Incoming calls in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f5194-103">_**Тема последнего изменения:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="f5194-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="f5194-104">Маршрутизация входящих вызовов пользователей, для которых включена маршрутизация на основе местоположения, зависит от местоположения конечной точки пользователя.</span><span class="sxs-lookup"><span data-stu-id="f5194-104">The routing of incoming calls to users enabled for Location-Based Routing depends on the location of the user’s endpoint.</span></span> <span data-ttu-id="f5194-105">Маршрутизация входящих звонков подвергается влиянию следующим образом.</span><span class="sxs-lookup"><span data-stu-id="f5194-105">The routing of incoming calls is affected in the following way.</span></span> <span data-ttu-id="f5194-106">Если у пользователя есть входящий звонок на конечную точку, расположенную на сайте, поддерживающем маршрутизацию на основе расположения, а конечная точка находится на том же сайте сети, что и шлюз PSTN, Звонок будет перенаправлен.</span><span class="sxs-lookup"><span data-stu-id="f5194-106">If a user has an incoming call to an endpoint located in a Location-Based Routing enabled network site, and the endpoint is located in the same network site as the PSTN gateway, the call will be routed.</span></span> <span data-ttu-id="f5194-107">Если у пользователя есть входящий вызов конечной точки, расположенной на сайте сети, поддерживающей маршрутизацию на основе расположения, а конечная точка находится на другом сайте сети, чем шлюз PSTN, Звонок не будет маршрутизироваться.</span><span class="sxs-lookup"><span data-stu-id="f5194-107">If a user has an incoming call to an endpoint located in a Location-Based Routing enabled network site, and the endpoint is located in a different network site than the PSTN gateway, the call will not be routed.</span></span> <span data-ttu-id="f5194-108">Если пользователь не имеет конечных точек, расположенных на том же сетевом сайте, что и шлюз ТСОП, с которого происходит входящий звонок, этот звонок будет переадресован на голосовую почту пользователя, а уведомление о пропущенном звонке будет отправлено вызываемому абоненту.</span><span class="sxs-lookup"><span data-stu-id="f5194-108">When a user has no endpoints located in the same network site as the PSTN gateway where the incoming call is originating from, the incoming call will be routed directly to the user’s voicemail and a missed call notification will be sent to the called party.</span></span>

<span data-ttu-id="f5194-109">Параметры переадресации звонков для пользователя, для которого включена маршрутизация на основе местоположения, будут по-прежнему применены, однако переадресация звонков осуществляется с ограничениями маршрутизации на основе местоположения для пользователя.</span><span class="sxs-lookup"><span data-stu-id="f5194-109">The call forwarding settings of a user that is enabled for Location-Based Routing will continue to be enforced, however, calls forwarded will be subject to Location-Based Routing restrictions of the user.</span></span>

<span data-ttu-id="f5194-110">В следующей таблице показано, как маршрутизация на основе местоположения влияет на маршрутизацию входящих вызовов в зависимости от расположения конечной точки вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="f5194-110">The following table illustrates how Location-Based Routing affects the routing of inbound calls depending on the location of the callee’s endpoint.</span></span> <span data-ttu-id="f5194-111">Сетевой сайт шлюза PSTN включен для маршрутизации с учетом расположения, а маршрутизация на основе местоположения разрешает только маршрутизацию звонков по PSTN в конечные точки на пределах того же сайта сети.</span><span class="sxs-lookup"><span data-stu-id="f5194-111">The network site of the PSTN gateway is enabled for Location-Based Routing, and Location-Based Routing only permits routing of PSTN calls to endpoints within the same network site.</span></span>

### <a name="callee-receiving-an-inbound-call-from-the-pstn"></a><span data-ttu-id="f5194-112">Вызываемый абонент получает входящий звонок от ТСОП</span><span class="sxs-lookup"><span data-stu-id="f5194-112">Callee receiving an inbound call from the PSTN</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="f5194-113">Конечная точка вызываемого абонента расположена на том же сетевом сайте, что и шлюз ТСОП</span><span class="sxs-lookup"><span data-stu-id="f5194-113">Callee’s endpoint located in the same network site as PSTN gateway</span></span></th>
<th><span data-ttu-id="f5194-114">Конечная точка вызываемого абонента не расположена на том же сетевом сайте, что и шлюз ТСОП</span><span class="sxs-lookup"><span data-stu-id="f5194-114">Callee’s endpoint not located in the same network site as PSTN gateway</span></span></th>
<th><span data-ttu-id="f5194-115">Конечная точка вызываемого абонента расположена на неизвестном сетевом сайте или не включена для маршрутизации на основе расположения</span><span class="sxs-lookup"><span data-stu-id="f5194-115">Callee’s endpoint located in unknown network site or not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f5194-116">Маршрутизация входящих звонков ТСОП</span><span class="sxs-lookup"><span data-stu-id="f5194-116">Routing of inbound PSTN call</span></span></p></td>
<td><p><span data-ttu-id="f5194-117">Входящий звонок направляется в конечные точки вызываемого абонента</span><span class="sxs-lookup"><span data-stu-id="f5194-117">Incoming call is routed to callee’s endpoints</span></span></p></td>
<td><p><span data-ttu-id="f5194-118">Входящий звонок не направляется в конечные точки вызываемого абонента</span><span class="sxs-lookup"><span data-stu-id="f5194-118">Incoming call is not routed to callee’s endpoints</span></span></p></td>
<td><p><span data-ttu-id="f5194-119">Входящий звонок не направляется в конечные точки вызываемого абонента</span><span class="sxs-lookup"><span data-stu-id="f5194-119">Incoming call is not routed to callee’s endpoints</span></span></p></td>
</tr>
</tbody>
</table>

  

<div>

## <a name="see-also"></a><span data-ttu-id="f5194-120">См. также</span><span class="sxs-lookup"><span data-stu-id="f5194-120">See Also</span></span>


[<span data-ttu-id="f5194-121">Сценарии маршрутизации на основе местоположения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f5194-121">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

