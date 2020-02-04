---
title: 'Lync Server 2013: одновременный звонок'
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
ms.openlocfilehash: 1bcdb0d30bccfe628fd02861d257d79268046b77
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764515"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="simultaneous-ringing-in-lync-server-2013"></a><span data-ttu-id="72fc6-102">Одновременный звонок в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="72fc6-102">Simultaneous ringing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="72fc6-103">_**Тема последнего изменения:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="72fc6-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="72fc6-104">Если у вызывающего абонента есть одновременные звонки, маршрутизация на основе местоположения анализирует расположение вызывающего абонента и конечных точек вызываемого абонента, чтобы определить, следует ли перенаправлять звонок.</span><span class="sxs-lookup"><span data-stu-id="72fc6-104">When the called party has simultaneous ringing enabled, Location-Based Routing analyzes the location of the calling party and the endpoints of the called parties to determine whether the call should be routed.</span></span>

<span data-ttu-id="72fc6-105">В нижеприведенной таблице продемонстрированы варианты ситуации для пользователя, у которого настроен одновременный звонок, и различных типов вызываемых абонентов (пользователя в том же сайте сети, в другом сайте сети или на неизвестном сайте).</span><span class="sxs-lookup"><span data-stu-id="72fc6-105">The following table illustrates a user configured with simultaneous ringing, and the simultaneous ringing target is a user in the same network site, in a different network site, or in an unknown network site.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="72fc6-106">Входящий звонок ТСОП для абонента</span><span class="sxs-lookup"><span data-stu-id="72fc6-106">Incoming PSTN call for</span></span></th>
<th><span data-ttu-id="72fc6-107">на том же сетевом сайте, что и вызываемый абонент;</span><span class="sxs-lookup"><span data-stu-id="72fc6-107">Located in the same network site as callee</span></span></th>
<th><span data-ttu-id="72fc6-108">на сетевом сайте, отличном от сайта вызываемого абонента;</span><span class="sxs-lookup"><span data-stu-id="72fc6-108">Located in different network site than callee</span></span></th>
<th><span data-ttu-id="72fc6-109">Размещен на неизвестном сетевом сайте или не включен для маршрутизации с учетом расположения</span><span class="sxs-lookup"><span data-stu-id="72fc6-109">Located in unknown network site or not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="72fc6-110">Пользователь Lync</span><span class="sxs-lookup"><span data-stu-id="72fc6-110">Lync user</span></span></p></td>
<td><p><span data-ttu-id="72fc6-111">Одновременный вызов разрешен</span><span class="sxs-lookup"><span data-stu-id="72fc6-111">Simultaneous ring allowed</span></span></p></td>
<td><p><span data-ttu-id="72fc6-112">Одновременный вызов не разрешен</span><span class="sxs-lookup"><span data-stu-id="72fc6-112">Simultaneous ring not allowed</span></span></p></td>
<td><p><span data-ttu-id="72fc6-113">Одновременный вызов не разрешен</span><span class="sxs-lookup"><span data-stu-id="72fc6-113">Simultaneous ring not allowed</span></span></p></td>
</tr>
</tbody>
</table>

  
<span data-ttu-id="72fc6-114">В следующей таблице показан вызов из пользователя Lync (например, вызывающего абонента Lync) на том же сайте сети, на другом сайте сети или неизвестном сетевому сайту.</span><span class="sxs-lookup"><span data-stu-id="72fc6-114">The following table illustrates a call from a Lync user (i.e. Lync caller) in the same network site, in a different network site, or from an unknown network site.</span></span> <span data-ttu-id="72fc6-115">Конечная точка ТСОП вызываемого абонента (т. е. мобильный телефон) настроена как место назначения для одновременного поступления вызова.</span><span class="sxs-lookup"><span data-stu-id="72fc6-115">The callee has a PSTN endpoint (i.e. cellphone) configured as a simultaneous ring target.</span></span> <span data-ttu-id="72fc6-116">В этом сценарии маршрутизация на основе местоположения определяет, следует ли перенаправлять вызов в цель однорангового кольца (например, телефона) вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="72fc6-116">In this scenario, Location-Based Routing will determine whether the call should be routed to the simultaneous ring target (i.e. cellphone) of the callee or not.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="72fc6-117">Цель одновременного вызова</span><span class="sxs-lookup"><span data-stu-id="72fc6-117">Simultaneous ring target</span></span></th>
<th><span data-ttu-id="72fc6-118">на том же сетевом сайте, что и вызываемый абонент;</span><span class="sxs-lookup"><span data-stu-id="72fc6-118">Located in the same network site as callee</span></span></th>
<th><span data-ttu-id="72fc6-119">на сетевом сайте, отличном от сайта вызываемого абонента;</span><span class="sxs-lookup"><span data-stu-id="72fc6-119">Located in different network site than callee</span></span></th>
<th><span data-ttu-id="72fc6-120">Размещен на неизвестном сетевом сайте или не включен для маршрутизации с учетом расположения</span><span class="sxs-lookup"><span data-stu-id="72fc6-120">Located in unknown network site or not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="72fc6-121">Конечная точка ТСОП</span><span class="sxs-lookup"><span data-stu-id="72fc6-121">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="72fc6-122">Одновременный вызов разрешен политикой маршрутизации голосовой связи сайта вызывающего абонента</span><span class="sxs-lookup"><span data-stu-id="72fc6-122">Simultaneous ring allowed through the caller’s site voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="72fc6-123">Одновременный вызов разрешен политикой маршрутизации голосовой связи сайта вызывающего абонента</span><span class="sxs-lookup"><span data-stu-id="72fc6-123">Simultaneous ring allowed through the caller’s site voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="72fc6-124">Одновременный вызов разрешен политикой голосовой связи вызывающего абонента на магистральные каналы, для которых не включена маршрутизация на основе местоположения</span><span class="sxs-lookup"><span data-stu-id="72fc6-124">Simultaneous ring allowed through the caller’s voice policy to trunks not enabled for Location-Based Routing</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="72fc6-125">См. также</span><span class="sxs-lookup"><span data-stu-id="72fc6-125">See Also</span></span>


[<span data-ttu-id="72fc6-126">Сценарии маршрутизации на основе местоположения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="72fc6-126">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

