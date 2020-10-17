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
ms.openlocfilehash: 358a0dd6dab96b67b26c211c9f28dbc6c0842804
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48519796"
---
# <a name="simultaneous-ringing-in-lync-server-2013"></a><span data-ttu-id="6217e-102">Одновременные звонки в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6217e-102">Simultaneous ringing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6217e-103">_**Последнее изменение темы:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="6217e-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="6217e-104">Если у вызываемой абонента включен Одновременный звонок, Location-Based маршрутизация анализирует расположение вызывающей стороны и конечных точек вызываемых сторон, чтобы определить, следует ли маршрутизировать вызов.</span><span class="sxs-lookup"><span data-stu-id="6217e-104">When the called party has simultaneous ringing enabled, Location-Based Routing analyzes the location of the calling party and the endpoints of the called parties to determine whether the call should be routed.</span></span>

<span data-ttu-id="6217e-105">В следующей таблице показано, что пользователь настроен с одновременным вызовом, а Одновременный звонок является пользователем на том же сетевом сайте, на другом сетевом сайте или на неизвестном сетевом сайте.</span><span class="sxs-lookup"><span data-stu-id="6217e-105">The following table illustrates a user configured with simultaneous ringing, and the simultaneous ringing target is a user in the same network site, in a different network site, or in an unknown network site.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6217e-106">Входящий звонок PSTN для</span><span class="sxs-lookup"><span data-stu-id="6217e-106">Incoming PSTN call for</span></span></th>
<th><span data-ttu-id="6217e-107">Размещается на том же сетевом сайте, что и вызываемый</span><span class="sxs-lookup"><span data-stu-id="6217e-107">Located in the same network site as callee</span></span></th>
<th><span data-ttu-id="6217e-108">Размещается на другом сетевом сайте, чем вызываемый</span><span class="sxs-lookup"><span data-stu-id="6217e-108">Located in different network site than callee</span></span></th>
<th><span data-ttu-id="6217e-109">Находится на неизвестном сетевом сайте или не включена для маршрутизации Location-Based</span><span class="sxs-lookup"><span data-stu-id="6217e-109">Located in unknown network site or not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6217e-110">Пользователь Lync</span><span class="sxs-lookup"><span data-stu-id="6217e-110">Lync user</span></span></p></td>
<td><p><span data-ttu-id="6217e-111">Одновременный звонок разрешен</span><span class="sxs-lookup"><span data-stu-id="6217e-111">Simultaneous ring allowed</span></span></p></td>
<td><p><span data-ttu-id="6217e-112">Одновременный звонок не разрешен</span><span class="sxs-lookup"><span data-stu-id="6217e-112">Simultaneous ring not allowed</span></span></p></td>
<td><p><span data-ttu-id="6217e-113">Одновременный звонок не разрешен</span><span class="sxs-lookup"><span data-stu-id="6217e-113">Simultaneous ring not allowed</span></span></p></td>
</tr>
</tbody>
</table>

  
<span data-ttu-id="6217e-114">В следующей таблице показан вызов из пользователя Lync (то есть вызывающего абонента Lync) на том же сетевом сайте, на другом сетевом сайте или на неизвестном сетевом сайте.</span><span class="sxs-lookup"><span data-stu-id="6217e-114">The following table illustrates a call from a Lync user (i.e. Lync caller) in the same network site, in a different network site, or from an unknown network site.</span></span> <span data-ttu-id="6217e-115">Вызываемая сторона имеет конечную точку PSTN (например, мобильного телефона), настроенную в качестве одновременного абонента.</span><span class="sxs-lookup"><span data-stu-id="6217e-115">The callee has a PSTN endpoint (i.e. cellphone) configured as a simultaneous ring target.</span></span> <span data-ttu-id="6217e-116">В этом сценарии Location-Based маршрутизация определяет, будет ли вызов перенаправляться в одновременный приемник (например, мобильного телефона) вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="6217e-116">In this scenario, Location-Based Routing will determine whether the call should be routed to the simultaneous ring target (i.e. cellphone) of the callee or not.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6217e-117">Цель одновременных звонков</span><span class="sxs-lookup"><span data-stu-id="6217e-117">Simultaneous ring target</span></span></th>
<th><span data-ttu-id="6217e-118">Размещается на том же сетевом сайте, что и вызываемый</span><span class="sxs-lookup"><span data-stu-id="6217e-118">Located in the same network site as callee</span></span></th>
<th><span data-ttu-id="6217e-119">Размещается на другом сетевом сайте, чем вызываемый</span><span class="sxs-lookup"><span data-stu-id="6217e-119">Located in different network site than callee</span></span></th>
<th><span data-ttu-id="6217e-120">Находится на неизвестном сетевом сайте или не включена для маршрутизации Location-Based</span><span class="sxs-lookup"><span data-stu-id="6217e-120">Located in unknown network site or not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6217e-121">Конечная точка PSTN</span><span class="sxs-lookup"><span data-stu-id="6217e-121">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="6217e-122">Одновременный звонок разрешен через политику маршрутизации голосовых вызовов сайта вызывающего абонента</span><span class="sxs-lookup"><span data-stu-id="6217e-122">Simultaneous ring allowed through the caller’s site voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="6217e-123">Одновременный звонок разрешен через политику маршрутизации голосовых вызовов сайта вызывающего абонента</span><span class="sxs-lookup"><span data-stu-id="6217e-123">Simultaneous ring allowed through the caller’s site voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="6217e-124">Одновременный звонок разрешен через политику голосовой связи вызывающего абонента для магистрали, для которых не включена маршрутизация Location-Based</span><span class="sxs-lookup"><span data-stu-id="6217e-124">Simultaneous ring allowed through the caller’s voice policy to trunks not enabled for Location-Based Routing</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="6217e-125">См. также</span><span class="sxs-lookup"><span data-stu-id="6217e-125">See Also</span></span>


[<span data-ttu-id="6217e-126">Сценарии для маршрутизации Location-Based в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6217e-126">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

