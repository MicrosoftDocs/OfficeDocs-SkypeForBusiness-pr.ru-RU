---
title: 'Lync Server 2013: таблица VideoClientEvent'
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
ms.openlocfilehash: 8ff9e19288aaaa09b8c72f857f3cfcf4e5331dd7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742009"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="videoclientevent-table-in-lync-server-2013"></a><span data-ttu-id="960d6-102">Таблица VideoClientEvent в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="960d6-102">VideoClientEvent table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="960d6-103">_**Тема последнего изменения:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="960d6-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="960d6-104">Каждая запись имеет событие клиента для одной конечной точки во время видеозвонка.</span><span class="sxs-lookup"><span data-stu-id="960d6-104">Each record contains client event for one endpoint in a video call.</span></span> <span data-ttu-id="960d6-105">Обычно один звонок состоит из двух записей: одного для вызывающего и для вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="960d6-105">Usually, one call has two records, one for caller and one for callee.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="960d6-106"><strong>Столбец</strong></span><span class="sxs-lookup"><span data-stu-id="960d6-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="960d6-107"><strong>Тип данных</strong></span><span class="sxs-lookup"><span data-stu-id="960d6-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="960d6-108"><strong>Ключ/индекс</strong></span><span class="sxs-lookup"><span data-stu-id="960d6-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="960d6-109"><strong>Сведения</strong></span><span class="sxs-lookup"><span data-stu-id="960d6-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="960d6-110"><strong>конференцедатетиме</strong></span><span class="sxs-lookup"><span data-stu-id="960d6-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="960d6-111">datetime</span><span class="sxs-lookup"><span data-stu-id="960d6-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="960d6-112">Primary</span><span class="sxs-lookup"><span data-stu-id="960d6-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="960d6-113">На которую ссылается <a href="lync-server-2013-medialine-table.md">Таблица медиалине в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="960d6-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="960d6-114"><strong>сессионсек</strong></span><span class="sxs-lookup"><span data-stu-id="960d6-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="960d6-115">целое</span><span class="sxs-lookup"><span data-stu-id="960d6-115">int</span></span></p></td>
<td><p><span data-ttu-id="960d6-116">Primary</span><span class="sxs-lookup"><span data-stu-id="960d6-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="960d6-117">На которую ссылается <a href="lync-server-2013-medialine-table.md">Таблица медиалине в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="960d6-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="960d6-118"><strong>медиалинелабел</strong></span><span class="sxs-lookup"><span data-stu-id="960d6-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="960d6-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="960d6-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="960d6-120">Primary</span><span class="sxs-lookup"><span data-stu-id="960d6-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="960d6-121">На которую ссылается <a href="lync-server-2013-medialine-table.md">Таблица медиалине в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="960d6-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="960d6-122"><strong>фромкаллер</strong></span><span class="sxs-lookup"><span data-stu-id="960d6-122"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="960d6-123">бит</span><span class="sxs-lookup"><span data-stu-id="960d6-123">bit</span></span></p></td>
<td><p><span data-ttu-id="960d6-124">Primary</span><span class="sxs-lookup"><span data-stu-id="960d6-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="960d6-125">0: данные вызывающего абонента</span><span class="sxs-lookup"><span data-stu-id="960d6-125">0: Callee’s data</span></span></p>
<p><span data-ttu-id="960d6-126">1: данные вызывающего абонента</span><span class="sxs-lookup"><span data-stu-id="960d6-126">1: Caller’s data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="960d6-127"><strong>нетворкбандвидсловевентратио</strong></span><span class="sxs-lookup"><span data-stu-id="960d6-127"><strong>NetworkBandwidthLowEventRatio</strong></span></span></p></td>
<td></td>
<td><p> </p></td>
<td><p><span data-ttu-id="960d6-128">Процент сеанса, когда событие Ловбандвидс было инициировано для состояния "Bad".</span><span class="sxs-lookup"><span data-stu-id="960d6-128">Percentage of session the LowBandwidth event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="960d6-129">Доступная пропускная способность недостаточна для приемлемого голосового интерфейса.</span><span class="sxs-lookup"><span data-stu-id="960d6-129">The available bandwidth is insufficient for an acceptable voice experience.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="960d6-130"><strong>нетворкрецеивекуалитевентратио</strong></span><span class="sxs-lookup"><span data-stu-id="960d6-130"><strong>NetworkReceiveQualityEventRatio</strong></span></span></p></td>
<td></td>
<td><p> </p></td>
<td><p><span data-ttu-id="960d6-131">Процент сеанса, когда событие Рецеивесендкуалити было инициировано для состояния "Bad".</span><span class="sxs-lookup"><span data-stu-id="960d6-131">Percentage of session the ReceiveSendQuality event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="960d6-132">Качество сети в условиях нарушения или потери пакетов является существенным и влияет на качество получаемого звука.</span><span class="sxs-lookup"><span data-stu-id="960d6-132">Network quality in terms of jitter or packet loss is severe and impacts the quality of audio being received.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

