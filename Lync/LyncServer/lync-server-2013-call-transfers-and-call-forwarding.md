---
title: 'Lync Server 2013: передача звонков и переадресация звонков'
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
ms.openlocfilehash: a78332e2fa24c4f718cb3cdb3cbc9dc93a03601d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188032"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="call-transfers-and-call-forwarding-in-lync-server-2013"></a><span data-ttu-id="bb213-102">Передача звонков и переадресация вызовов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bb213-102">Call transfers and call forwarding in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bb213-103">_**Последнее изменение темы:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="bb213-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="bb213-104">При использовании конечной точки PSTN служба маршрутизации на основе расположения анализирует расположение конечной точки Калле и конечную точку, в которую передается или передается вызов (то есть, цель передачи/перенаправления).</span><span class="sxs-lookup"><span data-stu-id="bb213-104">When a PSTN endpoint is involved, Location-Based Routing analyzes the location of the calle’s endpoint and the endpoint where the call will be transferred or forwarded to (i.e. transfer/forward target).</span></span> <span data-ttu-id="bb213-105">Маршрутизация на основе расположения определяет, следует ли передавать или пересылать вызов в зависимости от расположения обеих конечных точек.</span><span class="sxs-lookup"><span data-stu-id="bb213-105">Location-Based Routing determines whether the call should be transferred or forwarded depending on the location of both endpoints.</span></span>

<span data-ttu-id="bb213-106">В следующей таблице показан сценарий пользователя Lync в вызове с конечной точкой PSTN, а пользователь Lync передает вызов другому пользователю Lync.</span><span class="sxs-lookup"><span data-stu-id="bb213-106">The following table illustrates the scenario of a Lync user in a call with a PSTN endpoint, and the Lync user transfers the call to another Lync user.</span></span> <span data-ttu-id="bb213-107">В зависимости от расположения сетевого сайта конечной точки участника, маршрутизация на основе расположения влияет на маршрутизацию передачи вызовов или пересылки.</span><span class="sxs-lookup"><span data-stu-id="bb213-107">Depending on the network site location of the transferee’s endpoint, Location-Based Routing affects the routing of the call transfer or forward.</span></span>

### <a name="initiating-call-transfer-or-forward"></a><span data-ttu-id="bb213-108">Инициация передачи или пересылки звонка</span><span class="sxs-lookup"><span data-stu-id="bb213-108">Initiating call transfer or forward</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bb213-109">Пользователь, инициирующий передачу или переадресацию звонка</span><span class="sxs-lookup"><span data-stu-id="bb213-109">User initiating the call transfer/forward</span></span></th>
<th><span data-ttu-id="bb213-110">Целевая конечная точка находится на том же сетевом сайте, что и пользователь, инициирующий передачу или переадресацию</span><span class="sxs-lookup"><span data-stu-id="bb213-110">Target endpoint is in same network site as user initiating call transfer or forward</span></span></th>
<th><span data-ttu-id="bb213-111">Целевая конечная точка находится на другом сетевом сайте, что и пользователь, инициирующий передачу или переадресацию вызовов</span><span class="sxs-lookup"><span data-stu-id="bb213-111">Target endpoint is in different network site as user initiating call transfer or forward</span></span></th>
<th><span data-ttu-id="bb213-112">Целевая конечная точка находится в неизвестном сетевом сайте, или сетевой сайт не включен для маршрутизации на основе расположения</span><span class="sxs-lookup"><span data-stu-id="bb213-112">Target endpoint is in unknown network site or network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bb213-113">Пользователь Lync</span><span class="sxs-lookup"><span data-stu-id="bb213-113">Lync user</span></span></p></td>
<td><p><span data-ttu-id="bb213-114">Переадресация звонков или передача разрешена</span><span class="sxs-lookup"><span data-stu-id="bb213-114">Call forward or transfer is allowed</span></span></p></td>
<td><p><span data-ttu-id="bb213-115">Переадресация вызовов и передача запрещены</span><span class="sxs-lookup"><span data-stu-id="bb213-115">Call forward or transfer is not allowed</span></span></p></td>
<td><p><span data-ttu-id="bb213-116">Переадресация вызовов и передача запрещены</span><span class="sxs-lookup"><span data-stu-id="bb213-116">Call forward or transfer is not allowed</span></span></p></td>
</tr>
</tbody>
</table>

  

<span data-ttu-id="bb213-117">Например: пользователь Lync в вызове с конечной точкой PSTN передает вызов другому пользователю Lync, который находится на том же сетевом сайте.</span><span class="sxs-lookup"><span data-stu-id="bb213-117">For example: a Lync user in a call with a PSTN endpoint transfers the call to another Lync user that is in the same network site.</span></span> <span data-ttu-id="bb213-118">В этом случае передача вызовов разрешена.</span><span class="sxs-lookup"><span data-stu-id="bb213-118">In this case, the call transfer is allowed.</span></span>

<span data-ttu-id="bb213-119">В следующей таблице показан сценарий пользователя Lync в вызове с другим пользователем Lync, а один из пользователей передает вызов конечной точке PSTN.</span><span class="sxs-lookup"><span data-stu-id="bb213-119">The following table illustrates the scenario of a Lync user in a call with another Lync user, and one of the users transfers the call to a PSTN endpoint.</span></span> <span data-ttu-id="bb213-120">В зависимости от расположения пользователя, на который передается вызов, в таблице подробно описывается, как маршрутизация на основе расположения влияет на вызов.</span><span class="sxs-lookup"><span data-stu-id="bb213-120">Depending on the location of the user the call is being transferred to, the table details how Location-Based Routing affects the call.</span></span>

### <a name="call-transfer-or-forward-to-pstn-endpoint"></a><span data-ttu-id="bb213-121">Передача звонка или переадресация на конечную точку PSTN</span><span class="sxs-lookup"><span data-stu-id="bb213-121">Call transfer or forward to PSTN endpoint</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bb213-122">Целевая конечная точка передачи вызовов и переадресации</span><span class="sxs-lookup"><span data-stu-id="bb213-122">Call transfer/forward endpoint target</span></span></th>
<th><span data-ttu-id="bb213-123">Пользователи Lync на одном сетевом сайте</span><span class="sxs-lookup"><span data-stu-id="bb213-123">Lync users in same network site</span></span></th>
<th><span data-ttu-id="bb213-124">Пользователи Lync в различных сетевых сайтах</span><span class="sxs-lookup"><span data-stu-id="bb213-124">Lync users in different network sites</span></span></th>
<th><span data-ttu-id="bb213-125">Один или оба пользователя Lync на неизвестном сетевом сайте или сетевом сайте не включены для маршрутизации на основе расположения</span><span class="sxs-lookup"><span data-stu-id="bb213-125">One or both Lync users in unknown network site or network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bb213-126">Конечная точка PSTN</span><span class="sxs-lookup"><span data-stu-id="bb213-126">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="bb213-127">Переадресация звонков или передача данных разрешена политикой маршрутизации голосовой связи на сайте перенесенного пользователя</span><span class="sxs-lookup"><span data-stu-id="bb213-127">Call forward or transfer allowed by the transferred user’s site voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="bb213-128">Переадресация звонков или передача данных разрешена политикой маршрутизации голосовой связи на сайте перенесенного пользователя</span><span class="sxs-lookup"><span data-stu-id="bb213-128">Call forward or transfer allowed by the transferred user’s site voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="bb213-129">Переадресация вызовов или передача, разрешенные переданными политиками голосовой связи пользователя, только через магистрали, для которых не включена маршрутизация на основе расположения</span><span class="sxs-lookup"><span data-stu-id="bb213-129">Call forward or transfer allowed by the transferred user’s voice policy only through trunks not enabled for Location-Based Routing</span></span></p></td>
</tr>
</tbody>
</table>

  
<span data-ttu-id="bb213-130">Например: пользователь Lync в вызове с другим пользователем Lync, который находится на том же сетевом сайте, передает вызов конечной точке PSTN, а передача вызовов разрешена.</span><span class="sxs-lookup"><span data-stu-id="bb213-130">For example: a Lync user in a call with another Lync user that is in the same network site transfers the call to a PSTN endpoint and the call transfer is allowed.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="bb213-131">См. также</span><span class="sxs-lookup"><span data-stu-id="bb213-131">See Also</span></span>


[<span data-ttu-id="bb213-132">Сценарии маршрутизации на основе расположения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bb213-132">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

