---
title: 'Lync Server 2013: входящие звонки'
description: 'Lync Server 2013: входящие вызовы.'
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
ms.openlocfilehash: 3a72c7fc378240f9751eae8e6c24e9cc601b08d3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547735"
---
# <a name="incoming-calls-in-lync-server-2013"></a><span data-ttu-id="57ff5-103">Входящие звонки в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="57ff5-103">Incoming calls in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="57ff5-104">_**Последнее изменение темы:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="57ff5-104">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="57ff5-105">Маршрутизация входящих вызовов пользователей, включенных для маршрутизации Location-Based, зависит от расположения конечной точки пользователя.</span><span class="sxs-lookup"><span data-stu-id="57ff5-105">The routing of incoming calls to users enabled for Location-Based Routing depends on the location of the user’s endpoint.</span></span> <span data-ttu-id="57ff5-106">Маршрутизация входящих вызовов изменяется следующим образом.</span><span class="sxs-lookup"><span data-stu-id="57ff5-106">The routing of incoming calls is affected in the following way.</span></span> <span data-ttu-id="57ff5-107">Если у пользователя есть входящий вызов конечной точки, расположенной на сетевом сайте с поддержкой маршрутизации Location-Based, а конечная точка расположена на том же сетевом сайте, что и шлюз PSTN, вызов будет перенаправлен.</span><span class="sxs-lookup"><span data-stu-id="57ff5-107">If a user has an incoming call to an endpoint located in a Location-Based Routing enabled network site, and the endpoint is located in the same network site as the PSTN gateway, the call will be routed.</span></span> <span data-ttu-id="57ff5-108">Если у пользователя есть входящий вызов конечной точки, расположенной на сетевом сайте с поддержкой маршрутизации Location-Based, а конечная точка расположена на другом сетевом сайте, отличном от шлюза PSTN, вызов не будет маршрутизироваться.</span><span class="sxs-lookup"><span data-stu-id="57ff5-108">If a user has an incoming call to an endpoint located in a Location-Based Routing enabled network site, and the endpoint is located in a different network site than the PSTN gateway, the call will not be routed.</span></span> <span data-ttu-id="57ff5-109">Если у пользователя нет конечных точек, расположенных на том же сетевом сайте, что и шлюз PSTN, из которого исходит входящий вызов, входящий вызов будет перенаправлен прямо на голосовую почту пользователя, и уведомление о пропущенном звонке будет отправлено вызываемому абоненту.</span><span class="sxs-lookup"><span data-stu-id="57ff5-109">When a user has no endpoints located in the same network site as the PSTN gateway where the incoming call is originating from, the incoming call will be routed directly to the user’s voicemail and a missed call notification will be sent to the called party.</span></span>

<span data-ttu-id="57ff5-110">Параметры переадресации звонков для пользователя, включенного для маршрутизации Location-Based, будут по-прежнему применяться, однако переадресованные звонки будут подвергаться Location-Based ограничениям маршрутизации пользователя.</span><span class="sxs-lookup"><span data-stu-id="57ff5-110">The call forwarding settings of a user that is enabled for Location-Based Routing will continue to be enforced, however, calls forwarded will be subject to Location-Based Routing restrictions of the user.</span></span>

<span data-ttu-id="57ff5-111">В следующей таблице показано, как маршрутизация Location-Based влияет на маршрутизацию входящих вызовов в зависимости от расположения конечной точки вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="57ff5-111">The following table illustrates how Location-Based Routing affects the routing of inbound calls depending on the location of the callee’s endpoint.</span></span> <span data-ttu-id="57ff5-112">Сетевой сайт шлюза PSTN включен для маршрутизации Location-Based, а маршрутизация Location-Based разрешается только для маршрутизации вызовов PSTN в конечные точки того же сетевого сайта.</span><span class="sxs-lookup"><span data-stu-id="57ff5-112">The network site of the PSTN gateway is enabled for Location-Based Routing, and Location-Based Routing only permits routing of PSTN calls to endpoints within the same network site.</span></span>

### <a name="callee-receiving-an-inbound-call-from-the-pstn"></a><span data-ttu-id="57ff5-113">Вызываемый абонент получает входящий звонок от PSTN</span><span class="sxs-lookup"><span data-stu-id="57ff5-113">Callee receiving an inbound call from the PSTN</span></span>

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
<th><span data-ttu-id="57ff5-114">Конечная точка вызываемого абонента расположена на том же сетевом сайте, что и шлюз PSTN</span><span class="sxs-lookup"><span data-stu-id="57ff5-114">Callee’s endpoint located in the same network site as PSTN gateway</span></span></th>
<th><span data-ttu-id="57ff5-115">Конечная точка вызываемого абонента не расположена на том же сетевом сайте, что и шлюз PSTN</span><span class="sxs-lookup"><span data-stu-id="57ff5-115">Callee’s endpoint not located in the same network site as PSTN gateway</span></span></th>
<th><span data-ttu-id="57ff5-116">Конечная точка вызываемого абонента расположена на неизвестном сетевом сайте или не включена для маршрутизации Location-Based</span><span class="sxs-lookup"><span data-stu-id="57ff5-116">Callee’s endpoint located in unknown network site or not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="57ff5-117">Маршрутизация входящего звонка по PSTN</span><span class="sxs-lookup"><span data-stu-id="57ff5-117">Routing of inbound PSTN call</span></span></p></td>
<td><p><span data-ttu-id="57ff5-118">Входящий вызов перенаправляется в конечные точки вызываемого абонента</span><span class="sxs-lookup"><span data-stu-id="57ff5-118">Incoming call is routed to callee’s endpoints</span></span></p></td>
<td><p><span data-ttu-id="57ff5-119">Входящий звонок не перенаправляется в конечные точки вызываемого абонента</span><span class="sxs-lookup"><span data-stu-id="57ff5-119">Incoming call is not routed to callee’s endpoints</span></span></p></td>
<td><p><span data-ttu-id="57ff5-120">Входящий звонок не перенаправляется в конечные точки вызываемого абонента</span><span class="sxs-lookup"><span data-stu-id="57ff5-120">Incoming call is not routed to callee’s endpoints</span></span></p></td>
</tr>
</tbody>
</table>

  

<div>

## <a name="see-also"></a><span data-ttu-id="57ff5-121">См. также</span><span class="sxs-lookup"><span data-stu-id="57ff5-121">See Also</span></span>


[<span data-ttu-id="57ff5-122">Сценарии для маршрутизации Location-Based в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="57ff5-122">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

