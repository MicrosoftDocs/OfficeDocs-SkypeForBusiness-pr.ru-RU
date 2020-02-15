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
ms.openlocfilehash: ca0cdc7781143b0e76ff83a980f00da58c814f02
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049571"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="outgoing-calls-in-lync-server-2013"></a><span data-ttu-id="7954e-102">Исходящие вызовы в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7954e-102">Outgoing calls in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7954e-103">_**Последнее изменение темы:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="7954e-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="7954e-104">Маршрутизация исходящих вызовов пользователей, для которых включена маршрутизация на основе расположения, зависит от расположения в сети конечной точки пользователя.</span><span class="sxs-lookup"><span data-stu-id="7954e-104">The routing of outbound calls of users enabled for Location-Based Routing is affected by the network location of the user’s endpoint.</span></span> <span data-ttu-id="7954e-105">В следующей таблице показано, как маршрутизация на основе расположения влияет на маршрутизацию исходящих вызовов в зависимости от расположения конечной точки вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="7954e-105">The following table illustrates how Location-Based Routing affects the routing of outbound calls depending on the location of the caller’s endpoint.</span></span>

### <a name="caller-placing-an-outbound-call-to-the-pstn"></a><span data-ttu-id="7954e-106">Вызывающий абонент, исходящий звонок по протоколу PSTN</span><span class="sxs-lookup"><span data-stu-id="7954e-106">Caller placing an outbound call to the PSTN</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="7954e-107">Конечная точка пользователя, расположенная на сетевом сайте, для которого включена маршрутизация на основе расположения</span><span class="sxs-lookup"><span data-stu-id="7954e-107">User endpoint located in a network site enabled for Location-Based Routing</span></span></th>
<th><span data-ttu-id="7954e-108">Конечная точка пользователя находится на неизвестном сетевом сайте или не включена для маршрутизации на основе расположения</span><span class="sxs-lookup"><span data-stu-id="7954e-108">User endpoint located in unknown network site or not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7954e-109">Авторизация исходящих вызовов</span><span class="sxs-lookup"><span data-stu-id="7954e-109">Authorization of outbound calls</span></span></p></td>
<td><p><span data-ttu-id="7954e-110">Вызов авторизован на основе политики голосовой связи пользователя</span><span class="sxs-lookup"><span data-stu-id="7954e-110">Call is authorized based on user’s voice policy</span></span></p></td>
<td><p><span data-ttu-id="7954e-111">Вызов авторизован на основе политики голосовой связи пользователя</span><span class="sxs-lookup"><span data-stu-id="7954e-111">Call is authorized based on user’s voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7954e-112">Маршрутизация исходящего звонка</span><span class="sxs-lookup"><span data-stu-id="7954e-112">Routing of outbound call</span></span></p></td>
<td><p><span data-ttu-id="7954e-113">Вызов перенаправляется в соответствии с политикой маршрутизации голосовой связи на сетевом сайте.</span><span class="sxs-lookup"><span data-stu-id="7954e-113">Call is routed according to the network site’s voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="7954e-114">Вызов перенаправляется в соответствии с политикой голосовой связи пользователя и только через магистрали, для которых не включена маршрутизация на основе расположения (при наличии).</span><span class="sxs-lookup"><span data-stu-id="7954e-114">Call is routed according to user’s voice policy and only through trunks not enabled for Location-Based Routing (if available)</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="7954e-115">См. также</span><span class="sxs-lookup"><span data-stu-id="7954e-115">See Also</span></span>


[<span data-ttu-id="7954e-116">Сценарии маршрутизации на основе расположения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7954e-116">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

