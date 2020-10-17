---
title: 'Lync Server 2013: передача звонков и переадресация звонков'
description: 'Lync Server 2013: Передача вызовов и переадресация вызовов.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call transfers and call forwarding
ms:assetid: 978610ec-63c7-4cf6-ad7a-9ef91559bf12
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994051(v=OCS.15)
ms:contentKeyID: 51803962
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d9359cb64b386d022eab33e4523dfaccf784075b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565255"
---
# <a name="call-transfers-and-call-forwarding-in-lync-server-2013"></a><span data-ttu-id="00b51-103">Передача звонков и переадресация вызовов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="00b51-103">Call transfers and call forwarding in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="00b51-104">_**Последнее изменение темы:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="00b51-104">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="00b51-105">Когда применяется конечная точка PSTN, Location-Based маршрутизация анализирует расположение конечной точки Калле и конечную точку, в которую передается или передается вызов (то есть, цель передачи/перенаправления).</span><span class="sxs-lookup"><span data-stu-id="00b51-105">When a PSTN endpoint is involved, Location-Based Routing analyzes the location of the calle’s endpoint and the endpoint where the call will be transferred or forwarded to (i.e. transfer/forward target).</span></span> <span data-ttu-id="00b51-106">Маршрутизация Location-Based определяет, следует ли передавать или пересылать вызов в зависимости от расположения обеих конечных точек.</span><span class="sxs-lookup"><span data-stu-id="00b51-106">Location-Based Routing determines whether the call should be transferred or forwarded depending on the location of both endpoints.</span></span>

<span data-ttu-id="00b51-107">В следующей таблице показан сценарий пользователя Lync в вызове с конечной точкой PSTN, а пользователь Lync передает вызов другому пользователю Lync.</span><span class="sxs-lookup"><span data-stu-id="00b51-107">The following table illustrates the scenario of a Lync user in a call with a PSTN endpoint, and the Lync user transfers the call to another Lync user.</span></span> <span data-ttu-id="00b51-108">В зависимости от расположения сетевого сайта конечной точки участника, Location-Based маршрутизация влияет на маршрутизацию передачи или переадресации вызовов.</span><span class="sxs-lookup"><span data-stu-id="00b51-108">Depending on the network site location of the transferee’s endpoint, Location-Based Routing affects the routing of the call transfer or forward.</span></span>

### <a name="initiating-call-transfer-or-forward"></a><span data-ttu-id="00b51-109">Инициация передачи или пересылки звонка</span><span class="sxs-lookup"><span data-stu-id="00b51-109">Initiating call transfer or forward</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="00b51-110">Пользователь, инициирующий передачу или переадресацию звонка</span><span class="sxs-lookup"><span data-stu-id="00b51-110">User initiating the call transfer/forward</span></span></th>
<th><span data-ttu-id="00b51-111">Целевая конечная точка находится на том же сетевом сайте, что и пользователь, инициирующий передачу или переадресацию</span><span class="sxs-lookup"><span data-stu-id="00b51-111">Target endpoint is in same network site as user initiating call transfer or forward</span></span></th>
<th><span data-ttu-id="00b51-112">Целевая конечная точка находится на другом сетевом сайте, что и пользователь, инициирующий передачу или переадресацию вызовов</span><span class="sxs-lookup"><span data-stu-id="00b51-112">Target endpoint is in different network site as user initiating call transfer or forward</span></span></th>
<th><span data-ttu-id="00b51-113">Целевая конечная точка находится в неизвестном сетевом сайте или на сетевом сайте не включена маршрутизация Location-Based</span><span class="sxs-lookup"><span data-stu-id="00b51-113">Target endpoint is in unknown network site or network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="00b51-114">Пользователь Lync</span><span class="sxs-lookup"><span data-stu-id="00b51-114">Lync user</span></span></p></td>
<td><p><span data-ttu-id="00b51-115">Переадресация звонков или передача разрешена</span><span class="sxs-lookup"><span data-stu-id="00b51-115">Call forward or transfer is allowed</span></span></p></td>
<td><p><span data-ttu-id="00b51-116">Переадресация вызовов и передача запрещены</span><span class="sxs-lookup"><span data-stu-id="00b51-116">Call forward or transfer is not allowed</span></span></p></td>
<td><p><span data-ttu-id="00b51-117">Переадресация вызовов и передача запрещены</span><span class="sxs-lookup"><span data-stu-id="00b51-117">Call forward or transfer is not allowed</span></span></p></td>
</tr>
</tbody>
</table>

  

<span data-ttu-id="00b51-118">Например: пользователь Lync в вызове с конечной точкой PSTN передает вызов другому пользователю Lync, который находится на том же сетевом сайте.</span><span class="sxs-lookup"><span data-stu-id="00b51-118">For example: a Lync user in a call with a PSTN endpoint transfers the call to another Lync user that is in the same network site.</span></span> <span data-ttu-id="00b51-119">В этом случае передача вызовов разрешена.</span><span class="sxs-lookup"><span data-stu-id="00b51-119">In this case, the call transfer is allowed.</span></span>

<span data-ttu-id="00b51-120">В следующей таблице показан сценарий пользователя Lync в вызове с другим пользователем Lync, а один из пользователей передает вызов конечной точке PSTN.</span><span class="sxs-lookup"><span data-stu-id="00b51-120">The following table illustrates the scenario of a Lync user in a call with another Lync user, and one of the users transfers the call to a PSTN endpoint.</span></span> <span data-ttu-id="00b51-121">В зависимости от расположения пользователя, на который передается вызов, в таблице подробно описывается, как Location-Based маршрутизация влияет на вызов.</span><span class="sxs-lookup"><span data-stu-id="00b51-121">Depending on the location of the user the call is being transferred to, the table details how Location-Based Routing affects the call.</span></span>

### <a name="call-transfer-or-forward-to-pstn-endpoint"></a><span data-ttu-id="00b51-122">Передача звонка или переадресация на конечную точку PSTN</span><span class="sxs-lookup"><span data-stu-id="00b51-122">Call transfer or forward to PSTN endpoint</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="00b51-123">Целевая конечная точка передачи вызовов и переадресации</span><span class="sxs-lookup"><span data-stu-id="00b51-123">Call transfer/forward endpoint target</span></span></th>
<th><span data-ttu-id="00b51-124">Пользователи Lync на одном сетевом сайте</span><span class="sxs-lookup"><span data-stu-id="00b51-124">Lync users in same network site</span></span></th>
<th><span data-ttu-id="00b51-125">Пользователи Lync в различных сетевых сайтах</span><span class="sxs-lookup"><span data-stu-id="00b51-125">Lync users in different network sites</span></span></th>
<th><span data-ttu-id="00b51-126">Один или оба пользователя Lync на неизвестном сетевом сайте или сетевом сайте не включены для маршрутизации Location-Based</span><span class="sxs-lookup"><span data-stu-id="00b51-126">One or both Lync users in unknown network site or network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="00b51-127">Конечная точка PSTN</span><span class="sxs-lookup"><span data-stu-id="00b51-127">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="00b51-128">Переадресация звонков или передача данных разрешена политикой маршрутизации голосовой связи на сайте перенесенного пользователя</span><span class="sxs-lookup"><span data-stu-id="00b51-128">Call forward or transfer allowed by the transferred user’s site voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="00b51-129">Переадресация звонков или передача данных разрешена политикой маршрутизации голосовой связи на сайте перенесенного пользователя</span><span class="sxs-lookup"><span data-stu-id="00b51-129">Call forward or transfer allowed by the transferred user’s site voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="00b51-130">Переадресация звонков или передача, разрешенные переданными политикой голосовой связи пользователя, только через магистрали, для которых не включена маршрутизация Location-Based</span><span class="sxs-lookup"><span data-stu-id="00b51-130">Call forward or transfer allowed by the transferred user’s voice policy only through trunks not enabled for Location-Based Routing</span></span></p></td>
</tr>
</tbody>
</table>

  
<span data-ttu-id="00b51-131">Например: пользователь Lync в вызове с другим пользователем Lync, который находится на том же сетевом сайте, передает вызов конечной точке PSTN, а передача вызовов разрешена.</span><span class="sxs-lookup"><span data-stu-id="00b51-131">For example: a Lync user in a call with another Lync user that is in the same network site transfers the call to a PSTN endpoint and the call transfer is allowed.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="00b51-132">См. также</span><span class="sxs-lookup"><span data-stu-id="00b51-132">See Also</span></span>


[<span data-ttu-id="00b51-133">Сценарии для маршрутизации Location-Based в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="00b51-133">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

