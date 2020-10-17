---
title: 'Lync Server 2013: исходящие вызовы'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Outgoing calls
ms:assetid: 885ffe6f-cd51-4f21-8d4f-a1ff8d818858
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994049(v=OCS.15)
ms:contentKeyID: 51803960
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6a77ddf0757cd463bb8f1b95dbecfe90fd1086c9
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48524406"
---
# <a name="outgoing-calls-in-lync-server-2013"></a><span data-ttu-id="6cfd2-102">Исходящие вызовы в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6cfd2-102">Outgoing calls in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6cfd2-103">_**Последнее изменение темы:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="6cfd2-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="6cfd2-104">Маршрутизация исходящих вызовов пользователей, для которых включена Location-Based маршрутизация, зависит от расположения в сети конечной точки пользователя.</span><span class="sxs-lookup"><span data-stu-id="6cfd2-104">The routing of outbound calls of users enabled for Location-Based Routing is affected by the network location of the user’s endpoint.</span></span> <span data-ttu-id="6cfd2-105">В следующей таблице показано, как маршрутизация Location-Based влияет на маршрутизацию исходящих вызовов в зависимости от расположения конечной точки вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="6cfd2-105">The following table illustrates how Location-Based Routing affects the routing of outbound calls depending on the location of the caller’s endpoint.</span></span>

### <a name="caller-placing-an-outbound-call-to-the-pstn"></a><span data-ttu-id="6cfd2-106">Вызывающий абонент, исходящий звонок по протоколу PSTN</span><span class="sxs-lookup"><span data-stu-id="6cfd2-106">Caller placing an outbound call to the PSTN</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="6cfd2-107">Конечная точка пользователя, расположенная на сетевом сайте, включенной для маршрутизации Location-Based</span><span class="sxs-lookup"><span data-stu-id="6cfd2-107">User endpoint located in a network site enabled for Location-Based Routing</span></span></th>
<th><span data-ttu-id="6cfd2-108">Конечная точка пользователя расположена на неизвестном сетевом сайте или не включена для маршрутизации Location-Based</span><span class="sxs-lookup"><span data-stu-id="6cfd2-108">User endpoint located in unknown network site or not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6cfd2-109">Авторизация исходящих вызовов</span><span class="sxs-lookup"><span data-stu-id="6cfd2-109">Authorization of outbound calls</span></span></p></td>
<td><p><span data-ttu-id="6cfd2-110">Вызов авторизован на основе политики голосовой связи пользователя</span><span class="sxs-lookup"><span data-stu-id="6cfd2-110">Call is authorized based on user’s voice policy</span></span></p></td>
<td><p><span data-ttu-id="6cfd2-111">Вызов авторизован на основе политики голосовой связи пользователя</span><span class="sxs-lookup"><span data-stu-id="6cfd2-111">Call is authorized based on user’s voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6cfd2-112">Маршрутизация исходящего звонка</span><span class="sxs-lookup"><span data-stu-id="6cfd2-112">Routing of outbound call</span></span></p></td>
<td><p><span data-ttu-id="6cfd2-113">Вызов перенаправляется в соответствии с политикой маршрутизации голосовой связи на сетевом сайте.</span><span class="sxs-lookup"><span data-stu-id="6cfd2-113">Call is routed according to the network site’s voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="6cfd2-114">Вызов перенаправляется в соответствии с политикой голосовой связи пользователя и только через магистральные линии, не включенные для маршрутизации Location-Based (если она доступна).</span><span class="sxs-lookup"><span data-stu-id="6cfd2-114">Call is routed according to user’s voice policy and only through trunks not enabled for Location-Based Routing (if available)</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="6cfd2-115">См. также</span><span class="sxs-lookup"><span data-stu-id="6cfd2-115">See Also</span></span>


[<span data-ttu-id="6cfd2-116">Сценарии для маршрутизации Location-Based в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6cfd2-116">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

