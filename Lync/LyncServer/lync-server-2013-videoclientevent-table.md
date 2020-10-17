---
title: 'Lync Server 2013: таблица таблица videoclientevent'
description: 'Lync Server 2013: таблица таблица videoclientevent.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: VideoClientEvent table
ms:assetid: e8ab963b-fe1d-45b3-b9bd-66a5f44c1629
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399039(v=OCS.15)
ms:contentKeyID: 48185891
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ae73ac2548e838241febe60a2d31f80983b01de5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568495"
---
# <a name="videoclientevent-table-in-lync-server-2013"></a><span data-ttu-id="856e1-103">Таблица Таблица videoclientevent в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="856e1-103">VideoClientEvent table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="856e1-104">_**Последнее изменение темы:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="856e1-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="856e1-105">Каждая запись содержит событие клиента для одной конечной точки в видеовызове.</span><span class="sxs-lookup"><span data-stu-id="856e1-105">Each record contains client event for one endpoint in a video call.</span></span> <span data-ttu-id="856e1-106">Как правило, один вызов состоит из двух записей, один для вызывающего абонента и один для вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="856e1-106">Usually, one call has two records, one for caller and one for callee.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="856e1-107"><strong>Column</strong></span><span class="sxs-lookup"><span data-stu-id="856e1-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="856e1-108"><strong>Тип данных</strong></span><span class="sxs-lookup"><span data-stu-id="856e1-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="856e1-109"><strong>Ключ или индекс</strong></span><span class="sxs-lookup"><span data-stu-id="856e1-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="856e1-110"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="856e1-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="856e1-111"><strong>конференцедатетиме</strong></span><span class="sxs-lookup"><span data-stu-id="856e1-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="856e1-112">datetime</span><span class="sxs-lookup"><span data-stu-id="856e1-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="856e1-113">Primary</span><span class="sxs-lookup"><span data-stu-id="856e1-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="856e1-114">Ссылка из <a href="lync-server-2013-medialine-table.md">таблицы MediaLine в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="856e1-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="856e1-115"><strong>сессионсек</strong></span><span class="sxs-lookup"><span data-stu-id="856e1-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="856e1-116">int</span><span class="sxs-lookup"><span data-stu-id="856e1-116">int</span></span></p></td>
<td><p><span data-ttu-id="856e1-117">Primary</span><span class="sxs-lookup"><span data-stu-id="856e1-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="856e1-118">Ссылка из <a href="lync-server-2013-medialine-table.md">таблицы MediaLine в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="856e1-118">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="856e1-119"><strong>медиалинелабел</strong></span><span class="sxs-lookup"><span data-stu-id="856e1-119"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="856e1-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="856e1-120">tinyint</span></span></p></td>
<td><p><span data-ttu-id="856e1-121">Primary</span><span class="sxs-lookup"><span data-stu-id="856e1-121">Primary</span></span></p></td>
<td><p><span data-ttu-id="856e1-122">Ссылка из <a href="lync-server-2013-medialine-table.md">таблицы MediaLine в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="856e1-122">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="856e1-123"><strong>фромкаллер</strong></span><span class="sxs-lookup"><span data-stu-id="856e1-123"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="856e1-124">Битовая</span><span class="sxs-lookup"><span data-stu-id="856e1-124">bit</span></span></p></td>
<td><p><span data-ttu-id="856e1-125">Primary</span><span class="sxs-lookup"><span data-stu-id="856e1-125">Primary</span></span></p></td>
<td><p><span data-ttu-id="856e1-126">0: данные вызываемого абонента</span><span class="sxs-lookup"><span data-stu-id="856e1-126">0: Callee’s data</span></span></p>
<p><span data-ttu-id="856e1-127">1: данные вызывающего абонента</span><span class="sxs-lookup"><span data-stu-id="856e1-127">1: Caller’s data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="856e1-128"><strong>нетворкбандвидсловевентратио</strong></span><span class="sxs-lookup"><span data-stu-id="856e1-128"><strong>NetworkBandwidthLowEventRatio</strong></span></span></p></td>
<td></td>
<td><p> </p></td>
<td><p><span data-ttu-id="856e1-129">Процентное отношение сеанса событие Ловбандвидс было вызвано для состояния "плохое".</span><span class="sxs-lookup"><span data-stu-id="856e1-129">Percentage of session the LowBandwidth event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="856e1-130">Доступная полоса пропускания недостаточна для приемлемого голосового интерфейса.</span><span class="sxs-lookup"><span data-stu-id="856e1-130">The available bandwidth is insufficient for an acceptable voice experience.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="856e1-131"><strong>нетворкрецеивекуалитевентратио</strong></span><span class="sxs-lookup"><span data-stu-id="856e1-131"><strong>NetworkReceiveQualityEventRatio</strong></span></span></p></td>
<td></td>
<td><p> </p></td>
<td><p><span data-ttu-id="856e1-132">Процентное отношение сеанса событие Рецеивесендкуалити было вызвано для состояния "плохое".</span><span class="sxs-lookup"><span data-stu-id="856e1-132">Percentage of session the ReceiveSendQuality event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="856e1-133">Качество сети в терминах нарушения или потери пакетов является серьезным и влияет на качество получаемого звука.</span><span class="sxs-lookup"><span data-stu-id="856e1-133">Network quality in terms of jitter or packet loss is severe and impacts the quality of audio being received.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

