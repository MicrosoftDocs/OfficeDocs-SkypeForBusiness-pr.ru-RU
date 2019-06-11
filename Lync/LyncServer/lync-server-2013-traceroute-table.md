---
title: 'Lync Server 2013: таблица использованием Traceroute'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: TraceRoute table
ms:assetid: b9493cef-6ece-4f13-bf68-dbf132aab4f4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205205(v=OCS.15)
ms:contentKeyID: 48185242
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1dd0f9bc3bd900d71a316bf2ff1ab7612a51194
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849344"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="traceroute-table-in-lync-server-2013"></a><span data-ttu-id="8f4a8-102">Таблица использованием Traceroute в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8f4a8-102">TraceRoute table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8f4a8-103">_**Тема последнего изменения:** 2014-02-21_</span><span class="sxs-lookup"><span data-stu-id="8f4a8-103">_**Topic Last Modified:** 2014-02-21_</span></span>

<span data-ttu-id="8f4a8-104">В таблице использованием Traceroute содержатся сведения о маршрутизации из звонков.</span><span class="sxs-lookup"><span data-stu-id="8f4a8-104">The TraceRoute table contains routing information from calls.</span></span> <span data-ttu-id="8f4a8-105">Эта таблица введена в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8f4a8-105">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8f4a8-106"><strong>Столбец</strong></span><span class="sxs-lookup"><span data-stu-id="8f4a8-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="8f4a8-107"><strong>Тип данных</strong></span><span class="sxs-lookup"><span data-stu-id="8f4a8-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="8f4a8-108"><strong>Ключ/индекс</strong></span><span class="sxs-lookup"><span data-stu-id="8f4a8-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="8f4a8-109"><strong>Сведения</strong></span><span class="sxs-lookup"><span data-stu-id="8f4a8-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8f4a8-110"><strong>Конференцедатетиме</strong></span><span class="sxs-lookup"><span data-stu-id="8f4a8-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="8f4a8-111">datetime</span><span class="sxs-lookup"><span data-stu-id="8f4a8-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="8f4a8-112">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="8f4a8-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="8f4a8-113">Дата и время начала звонка.</span><span class="sxs-lookup"><span data-stu-id="8f4a8-113">Date and time that the call began.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f4a8-114"><strong>Сессионсек</strong></span><span class="sxs-lookup"><span data-stu-id="8f4a8-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="8f4a8-115">целое</span><span class="sxs-lookup"><span data-stu-id="8f4a8-115">int</span></span></p></td>
<td><p><span data-ttu-id="8f4a8-116">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="8f4a8-116">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="8f4a8-117">Уникальный идентификатор, который используется для различения нескольких звонков, которые могли приступили к одной и той же дате и в то же время.</span><span class="sxs-lookup"><span data-stu-id="8f4a8-117">Unique identifier used to distinguish between multiple calls that might have begun on the same date and at the same time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f4a8-118"><strong>Медиалинелабел</strong></span><span class="sxs-lookup"><span data-stu-id="8f4a8-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="8f4a8-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="8f4a8-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="8f4a8-120">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="8f4a8-120">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="8f4a8-121">Представляет тип видеостроки, используемой в звонке.</span><span class="sxs-lookup"><span data-stu-id="8f4a8-121">Represents the type of video line used in the call.</span></span> <span data-ttu-id="8f4a8-122">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="8f4a8-122">Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="8f4a8-123">0 – звук</span><span class="sxs-lookup"><span data-stu-id="8f4a8-123">0 – Audio</span></span></p></li>
<li><p><span data-ttu-id="8f4a8-124">1 – видео</span><span class="sxs-lookup"><span data-stu-id="8f4a8-124">1 – Video</span></span></p></li>
<li><p><span data-ttu-id="8f4a8-125">2 — панорамное видео</span><span class="sxs-lookup"><span data-stu-id="8f4a8-125">2 – Panoramic video</span></span></p></li>
<li><p><span data-ttu-id="8f4a8-126">3 — общий доступ к приложениям и рабочим столам</span><span class="sxs-lookup"><span data-stu-id="8f4a8-126">3 – Application/Desktop sharing</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f4a8-127"><strong>Фромкаллер</strong></span><span class="sxs-lookup"><span data-stu-id="8f4a8-127"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="8f4a8-128">бит</span><span class="sxs-lookup"><span data-stu-id="8f4a8-128">bit</span></span></p></td>
<td><p><span data-ttu-id="8f4a8-129">Primary</span><span class="sxs-lookup"><span data-stu-id="8f4a8-129">Primary</span></span></p></td>
<td><p><span data-ttu-id="8f4a8-130">Конечная точка, в которой был помещен звонок.</span><span class="sxs-lookup"><span data-stu-id="8f4a8-130">Endpoint that placed the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f4a8-131"><strong>Участк</strong></span><span class="sxs-lookup"><span data-stu-id="8f4a8-131"><strong>Hop</strong></span></span></p></td>
<td><p><span data-ttu-id="8f4a8-132">целое</span><span class="sxs-lookup"><span data-stu-id="8f4a8-132">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8f4a8-133">Транзитный сетевой переход/</span><span class="sxs-lookup"><span data-stu-id="8f4a8-133">Network hop/</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f4a8-134"><strong>Ипаддресскэй</strong></span><span class="sxs-lookup"><span data-stu-id="8f4a8-134"><strong>IPAddressKey</strong></span></span></p></td>
<td><p><span data-ttu-id="8f4a8-135">целое</span><span class="sxs-lookup"><span data-stu-id="8f4a8-135">int</span></span></p></td>
<td><p><span data-ttu-id="8f4a8-136">Другом</span><span class="sxs-lookup"><span data-stu-id="8f4a8-136">Foreign</span></span></p></td>
<td><p><span data-ttu-id="8f4a8-137">Уникальный идентификатор IP-адреса.</span><span class="sxs-lookup"><span data-stu-id="8f4a8-137">Unique identifier for the IP address.</span></span> <span data-ttu-id="8f4a8-138">Информация об IP-адресах хранится в <a href="lync-server-2013-ipaddress-table.md">таблице IPAddress в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="8f4a8-138">IP address information is stored in the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f4a8-139"><strong>ПЕРЕДАЧИ</strong></span><span class="sxs-lookup"><span data-stu-id="8f4a8-139"><strong>RTT</strong></span></span></p></td>
<td><p><span data-ttu-id="8f4a8-140">целое</span><span class="sxs-lookup"><span data-stu-id="8f4a8-140">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8f4a8-141">Время обмена данными.</span><span class="sxs-lookup"><span data-stu-id="8f4a8-141">Roundtrip time.</span></span> <span data-ttu-id="8f4a8-142">Время для обмена данными измеряет время, затрачиваемое на передачу голосового пакета получателю, а затем отправляет уведомление о том, что оно получено.</span><span class="sxs-lookup"><span data-stu-id="8f4a8-142">The roundtrip time measures the amount of time it takes for a voice packet to reach its destination and then send back notification that it was received.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

