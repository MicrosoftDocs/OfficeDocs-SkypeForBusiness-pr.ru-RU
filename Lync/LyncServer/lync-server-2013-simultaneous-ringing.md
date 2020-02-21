---
title: 'Lync Server 2013: одновременный Звонок'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Simultaneous ringing
ms:assetid: df02f919-4d50-4832-9300-6c51f8b4fc56
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994079(v=OCS.15)
ms:contentKeyID: 51803990
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: da250e04b3547e7ce6f00a73028ac3fcd083c30d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200352"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="simultaneous-ringing-in-lync-server-2013"></a><span data-ttu-id="d427b-102">Одновременные звонки в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d427b-102">Simultaneous ringing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d427b-103">_**Последнее изменение темы:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="d427b-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="d427b-104">Если у вызываемой абонента включен Одновременный звонок, маршрутизация на основе расположения анализирует расположение абонентской стороны и конечных точек вызываемых сторон, чтобы определить, следует ли маршрутизировать вызов.</span><span class="sxs-lookup"><span data-stu-id="d427b-104">When the called party has simultaneous ringing enabled, Location-Based Routing analyzes the location of the calling party and the endpoints of the called parties to determine whether the call should be routed.</span></span>

<span data-ttu-id="d427b-105">В следующей таблице показано, что пользователь настроен с одновременным вызовом, а Одновременный звонок является пользователем на том же сетевом сайте, на другом сетевом сайте или на неизвестном сетевом сайте.</span><span class="sxs-lookup"><span data-stu-id="d427b-105">The following table illustrates a user configured with simultaneous ringing, and the simultaneous ringing target is a user in the same network site, in a different network site, or in an unknown network site.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d427b-106">Входящий звонок PSTN для</span><span class="sxs-lookup"><span data-stu-id="d427b-106">Incoming PSTN call for</span></span></th>
<th><span data-ttu-id="d427b-107">Размещается на том же сетевом сайте, что и вызываемый</span><span class="sxs-lookup"><span data-stu-id="d427b-107">Located in the same network site as callee</span></span></th>
<th><span data-ttu-id="d427b-108">Размещается на другом сетевом сайте, чем вызываемый</span><span class="sxs-lookup"><span data-stu-id="d427b-108">Located in different network site than callee</span></span></th>
<th><span data-ttu-id="d427b-109">Находится на неизвестном сетевом сайте или не включена для маршрутизации на основе расположения</span><span class="sxs-lookup"><span data-stu-id="d427b-109">Located in unknown network site or not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d427b-110">Пользователь Lync</span><span class="sxs-lookup"><span data-stu-id="d427b-110">Lync user</span></span></p></td>
<td><p><span data-ttu-id="d427b-111">Одновременный звонок разрешен</span><span class="sxs-lookup"><span data-stu-id="d427b-111">Simultaneous ring allowed</span></span></p></td>
<td><p><span data-ttu-id="d427b-112">Одновременный звонок не разрешен</span><span class="sxs-lookup"><span data-stu-id="d427b-112">Simultaneous ring not allowed</span></span></p></td>
<td><p><span data-ttu-id="d427b-113">Одновременный звонок не разрешен</span><span class="sxs-lookup"><span data-stu-id="d427b-113">Simultaneous ring not allowed</span></span></p></td>
</tr>
</tbody>
</table>

  
<span data-ttu-id="d427b-114">В следующей таблице показан вызов из пользователя Lync (то есть вызывающего абонента Lync) на том же сетевом сайте, на другом сетевом сайте или на неизвестном сетевом сайте.</span><span class="sxs-lookup"><span data-stu-id="d427b-114">The following table illustrates a call from a Lync user (i.e. Lync caller) in the same network site, in a different network site, or from an unknown network site.</span></span> <span data-ttu-id="d427b-115">Вызываемая сторона имеет конечную точку PSTN (например, мобильного телефона), настроенную в качестве одновременного абонента.</span><span class="sxs-lookup"><span data-stu-id="d427b-115">The callee has a PSTN endpoint (i.e. cellphone) configured as a simultaneous ring target.</span></span> <span data-ttu-id="d427b-116">В этом сценарии маршрутизация на основе расположения определяет, следует ли перенаправлять вызов в цель однорангового абонента (например, мобильного телефона) вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="d427b-116">In this scenario, Location-Based Routing will determine whether the call should be routed to the simultaneous ring target (i.e. cellphone) of the callee or not.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d427b-117">Цель одновременных звонков</span><span class="sxs-lookup"><span data-stu-id="d427b-117">Simultaneous ring target</span></span></th>
<th><span data-ttu-id="d427b-118">Размещается на том же сетевом сайте, что и вызываемый</span><span class="sxs-lookup"><span data-stu-id="d427b-118">Located in the same network site as callee</span></span></th>
<th><span data-ttu-id="d427b-119">Размещается на другом сетевом сайте, чем вызываемый</span><span class="sxs-lookup"><span data-stu-id="d427b-119">Located in different network site than callee</span></span></th>
<th><span data-ttu-id="d427b-120">Находится на неизвестном сетевом сайте или не включена для маршрутизации на основе расположения</span><span class="sxs-lookup"><span data-stu-id="d427b-120">Located in unknown network site or not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d427b-121">Конечная точка PSTN</span><span class="sxs-lookup"><span data-stu-id="d427b-121">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="d427b-122">Одновременный звонок разрешен через политику маршрутизации голосовых вызовов сайта вызывающего абонента</span><span class="sxs-lookup"><span data-stu-id="d427b-122">Simultaneous ring allowed through the caller’s site voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="d427b-123">Одновременный звонок разрешен через политику маршрутизации голосовых вызовов сайта вызывающего абонента</span><span class="sxs-lookup"><span data-stu-id="d427b-123">Simultaneous ring allowed through the caller’s site voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="d427b-124">Одновременный звонок разрешен через политику голосовой связи вызывающего абонента для магистрали, для которых не включена маршрутизация на основе расположения</span><span class="sxs-lookup"><span data-stu-id="d427b-124">Simultaneous ring allowed through the caller’s voice policy to trunks not enabled for Location-Based Routing</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="d427b-125">См. также</span><span class="sxs-lookup"><span data-stu-id="d427b-125">See Also</span></span>


[<span data-ttu-id="d427b-126">Сценарии маршрутизации на основе расположения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d427b-126">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

