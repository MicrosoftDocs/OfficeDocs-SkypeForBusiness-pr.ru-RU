---
title: 'Lync Server 2013: переключение и переадресация звонков'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Call transfers and call forwarding
ms:assetid: 978610ec-63c7-4cf6-ad7a-9ef91559bf12
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994051(v=OCS.15)
ms:contentKeyID: 51803962
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6d5b0661cfaaef2e514f070260f44abc4ea00572
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841685"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-transfers-and-call-forwarding-in-lync-server-2013"></a><span data-ttu-id="e769e-102">Переключение и переадресация звонков в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e769e-102">Call transfers and call forwarding in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e769e-103">_**Тема последнего изменения:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="e769e-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="e769e-104">Когда задействована конечная точка PSTN, маршрутизация на основе местоположения анализирует расположение конечной точки лиственничный и конечную точку, в которую передается или пересылается звонок (например, цель передачи и перенаправления).</span><span class="sxs-lookup"><span data-stu-id="e769e-104">When a PSTN endpoint is involved, Location-Based Routing analyzes the location of the calle’s endpoint and the endpoint where the call will be transferred or forwarded to (i.e. transfer/forward target).</span></span> <span data-ttu-id="e769e-105">Маршрутизация на основе местоположения определяет, следует ли передавать или перенаправлять Звонок в зависимости от расположения обеих конечных точек.</span><span class="sxs-lookup"><span data-stu-id="e769e-105">Location-Based Routing determines whether the call should be transferred or forwarded depending on the location of both endpoints.</span></span>

<span data-ttu-id="e769e-106">В приведенной ниже таблице показан сценарий пользователя Lync в звонке с конечной точкой PSTN, и пользователь Lync передает звонок другому пользователю Lync.</span><span class="sxs-lookup"><span data-stu-id="e769e-106">The following table illustrates the scenario of a Lync user in a call with a PSTN endpoint, and the Lync user transfers the call to another Lync user.</span></span> <span data-ttu-id="e769e-107">В зависимости от расположения сетевого сайта для конечной точки получателя, маршрутизация на основе местоположения влияет на маршрут перемещения и переадресации звонков.</span><span class="sxs-lookup"><span data-stu-id="e769e-107">Depending on the network site location of the transferee’s endpoint, Location-Based Routing affects the routing of the call transfer or forward.</span></span>

### <a name="initiating-call-transfer-or-forward"></a><span data-ttu-id="e769e-108">Инициирование переключения или переадресации звонка</span><span class="sxs-lookup"><span data-stu-id="e769e-108">Initiating call transfer or forward</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e769e-109">Пользователь, инициирующий переключение или переадресацию звонка</span><span class="sxs-lookup"><span data-stu-id="e769e-109">User initiating the call transfer/forward</span></span></th>
<th><span data-ttu-id="e769e-110">Целевая конечная точка расположена на том же сетевом сайте, что и пользователь, инициирующий переключение или переадресацию звонка</span><span class="sxs-lookup"><span data-stu-id="e769e-110">Target endpoint is in same network site as user initiating call transfer or forward</span></span></th>
<th><span data-ttu-id="e769e-111">Целевая конечная точка расположена на сетевом сайте, отличном от того, где находится пользователь, инициирующий переключение или переадресацию звонка</span><span class="sxs-lookup"><span data-stu-id="e769e-111">Target endpoint is in different network site as user initiating call transfer or forward</span></span></th>
<th><span data-ttu-id="e769e-112">Целевая конечная точка находится на неизвестном сайте сети или на сайте сети не включена для маршрутизации с учетом расположения</span><span class="sxs-lookup"><span data-stu-id="e769e-112">Target endpoint is in unknown network site or network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e769e-113">Пользователь Lync</span><span class="sxs-lookup"><span data-stu-id="e769e-113">Lync user</span></span></p></td>
<td><p><span data-ttu-id="e769e-114">Переключение или переадресация звонка разрешены</span><span class="sxs-lookup"><span data-stu-id="e769e-114">Call forward or transfer is allowed</span></span></p></td>
<td><p><span data-ttu-id="e769e-115">Переключение или переадресация звонка не разрешены</span><span class="sxs-lookup"><span data-stu-id="e769e-115">Call forward or transfer is not allowed</span></span></p></td>
<td><p><span data-ttu-id="e769e-116">Переключение или переадресация звонка не разрешены</span><span class="sxs-lookup"><span data-stu-id="e769e-116">Call forward or transfer is not allowed</span></span></p></td>
</tr>
</tbody>
</table>

  

<span data-ttu-id="e769e-117">Например: пользователь Lync в звонке с конечной точкой PSTN передает звонок другому пользователю Lync, который находится на том же сайте сети.</span><span class="sxs-lookup"><span data-stu-id="e769e-117">For example: a Lync user in a call with a PSTN endpoint transfers the call to another Lync user that is in the same network site.</span></span> <span data-ttu-id="e769e-118">В этом случае переключение звонка разрешено.</span><span class="sxs-lookup"><span data-stu-id="e769e-118">In this case, the call transfer is allowed.</span></span>

<span data-ttu-id="e769e-119">В приведенной ниже таблице показан сценарий пользователя Lync в вызове с другим пользователем Lync, а один из пользователей передает Звонок в конечную точку PSTN.</span><span class="sxs-lookup"><span data-stu-id="e769e-119">The following table illustrates the scenario of a Lync user in a call with another Lync user, and one of the users transfers the call to a PSTN endpoint.</span></span> <span data-ttu-id="e769e-120">В таблице подробно показано, как маршрутизация на основе расположения обрабатывает звонок в зависимости от расположения пользователя, на которого переключается этот звонок.</span><span class="sxs-lookup"><span data-stu-id="e769e-120">Depending on the location of the user the call is being transferred to, the table details how Location-Based Routing affects the call.</span></span>

### <a name="call-transfer-or-forward-to-pstn-endpoint"></a><span data-ttu-id="e769e-121">Переключение или переадресация звонка на конечную точку ТСОП</span><span class="sxs-lookup"><span data-stu-id="e769e-121">Call transfer or forward to PSTN endpoint</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e769e-122">Целевая конечная точка переключения/переадресации звонка</span><span class="sxs-lookup"><span data-stu-id="e769e-122">Call transfer/forward endpoint target</span></span></th>
<th><span data-ttu-id="e769e-123">Пользователи Lync на одном и том же сайте сети</span><span class="sxs-lookup"><span data-stu-id="e769e-123">Lync users in same network site</span></span></th>
<th><span data-ttu-id="e769e-124">Пользователи Lync на разных сетевых сайтах</span><span class="sxs-lookup"><span data-stu-id="e769e-124">Lync users in different network sites</span></span></th>
<th><span data-ttu-id="e769e-125">Один или оба пользователя Lync на неизвестном сетевом сайте или сайте сети не включены для маршрутизации с учетом расположения</span><span class="sxs-lookup"><span data-stu-id="e769e-125">One or both Lync users in unknown network site or network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e769e-126">Конечная точка ТСОП</span><span class="sxs-lookup"><span data-stu-id="e769e-126">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="e769e-127">Переключение или переадресация звонка разрешены политикой маршрутизации голосовых звонков сайта передаваемого пользователя</span><span class="sxs-lookup"><span data-stu-id="e769e-127">Call forward or transfer allowed by the transferred user’s site voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="e769e-128">Переключение или переадресация звонка разрешены политикой маршрутизации голосовых звонков сайта передаваемого пользователя</span><span class="sxs-lookup"><span data-stu-id="e769e-128">Call forward or transfer allowed by the transferred user’s site voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="e769e-129">Переключение или переадресация звонка разрешены политикой маршрутизации голосовых звонков передаваемого пользователя, но только через магистрали, для которых не включена маршрутизация на основе расположения</span><span class="sxs-lookup"><span data-stu-id="e769e-129">Call forward or transfer allowed by the transferred user’s voice policy only through trunks not enabled for Location-Based Routing</span></span></p></td>
</tr>
</tbody>
</table>

  
<span data-ttu-id="e769e-130">Например: пользователь Lync в звонке с другим пользователем Lync, который находится на том же сайте сети, передает Звонок в конечную точку PSTN, и передача вызова разрешена.</span><span class="sxs-lookup"><span data-stu-id="e769e-130">For example: a Lync user in a call with another Lync user that is in the same network site transfers the call to a PSTN endpoint and the call transfer is allowed.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="e769e-131">См. также</span><span class="sxs-lookup"><span data-stu-id="e769e-131">See Also</span></span>


[<span data-ttu-id="e769e-132">Сценарии маршрутизации на основе местоположения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e769e-132">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

