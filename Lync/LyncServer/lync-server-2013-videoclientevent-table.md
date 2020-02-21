---
title: 'Lync Server 2013: таблица таблица videoclientevent'
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
ms.openlocfilehash: a687e503b9dfd02c296e1e96d88b93c716d7c54b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211635"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="videoclientevent-table-in-lync-server-2013"></a><span data-ttu-id="b8d45-102">Таблица Таблица videoclientevent в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b8d45-102">VideoClientEvent table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b8d45-103">_**Последнее изменение темы:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="b8d45-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="b8d45-104">Каждая запись содержит событие клиента для одной конечной точки в видеовызове.</span><span class="sxs-lookup"><span data-stu-id="b8d45-104">Each record contains client event for one endpoint in a video call.</span></span> <span data-ttu-id="b8d45-105">Как правило, один вызов состоит из двух записей, один для вызывающего абонента и один для вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="b8d45-105">Usually, one call has two records, one for caller and one for callee.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b8d45-106"><strong>Column</strong></span><span class="sxs-lookup"><span data-stu-id="b8d45-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="b8d45-107"><strong>Тип данных</strong></span><span class="sxs-lookup"><span data-stu-id="b8d45-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="b8d45-108"><strong>Ключ или индекс</strong></span><span class="sxs-lookup"><span data-stu-id="b8d45-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="b8d45-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="b8d45-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b8d45-110"><strong>конференцедатетиме</strong></span><span class="sxs-lookup"><span data-stu-id="b8d45-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b8d45-111">datetime</span><span class="sxs-lookup"><span data-stu-id="b8d45-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="b8d45-112">Primary</span><span class="sxs-lookup"><span data-stu-id="b8d45-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="b8d45-113">Ссылка из <a href="lync-server-2013-medialine-table.md">таблицы MediaLine в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="b8d45-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b8d45-114"><strong>сессионсек</strong></span><span class="sxs-lookup"><span data-stu-id="b8d45-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="b8d45-115">int</span><span class="sxs-lookup"><span data-stu-id="b8d45-115">int</span></span></p></td>
<td><p><span data-ttu-id="b8d45-116">Primary</span><span class="sxs-lookup"><span data-stu-id="b8d45-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="b8d45-117">Ссылка из <a href="lync-server-2013-medialine-table.md">таблицы MediaLine в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="b8d45-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b8d45-118"><strong>медиалинелабел</strong></span><span class="sxs-lookup"><span data-stu-id="b8d45-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="b8d45-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="b8d45-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="b8d45-120">Primary</span><span class="sxs-lookup"><span data-stu-id="b8d45-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="b8d45-121">Ссылка из <a href="lync-server-2013-medialine-table.md">таблицы MediaLine в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="b8d45-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b8d45-122"><strong>фромкаллер</strong></span><span class="sxs-lookup"><span data-stu-id="b8d45-122"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="b8d45-123">Битовая</span><span class="sxs-lookup"><span data-stu-id="b8d45-123">bit</span></span></p></td>
<td><p><span data-ttu-id="b8d45-124">Primary</span><span class="sxs-lookup"><span data-stu-id="b8d45-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="b8d45-125">0: данные вызываемого абонента</span><span class="sxs-lookup"><span data-stu-id="b8d45-125">0: Callee’s data</span></span></p>
<p><span data-ttu-id="b8d45-126">1: данные вызывающего абонента</span><span class="sxs-lookup"><span data-stu-id="b8d45-126">1: Caller’s data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b8d45-127"><strong>нетворкбандвидсловевентратио</strong></span><span class="sxs-lookup"><span data-stu-id="b8d45-127"><strong>NetworkBandwidthLowEventRatio</strong></span></span></p></td>
<td></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b8d45-128">Процентное отношение сеанса событие Ловбандвидс было вызвано для состояния "плохое".</span><span class="sxs-lookup"><span data-stu-id="b8d45-128">Percentage of session the LowBandwidth event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="b8d45-129">Доступная полоса пропускания недостаточна для приемлемого голосового интерфейса.</span><span class="sxs-lookup"><span data-stu-id="b8d45-129">The available bandwidth is insufficient for an acceptable voice experience.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b8d45-130"><strong>нетворкрецеивекуалитевентратио</strong></span><span class="sxs-lookup"><span data-stu-id="b8d45-130"><strong>NetworkReceiveQualityEventRatio</strong></span></span></p></td>
<td></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b8d45-131">Процентное отношение сеанса событие Рецеивесендкуалити было вызвано для состояния "плохое".</span><span class="sxs-lookup"><span data-stu-id="b8d45-131">Percentage of session the ReceiveSendQuality event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="b8d45-132">Качество сети в терминах нарушения или потери пакетов является серьезным и влияет на качество получаемого звука.</span><span class="sxs-lookup"><span data-stu-id="b8d45-132">Network quality in terms of jitter or packet loss is severe and impacts the quality of audio being received.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

