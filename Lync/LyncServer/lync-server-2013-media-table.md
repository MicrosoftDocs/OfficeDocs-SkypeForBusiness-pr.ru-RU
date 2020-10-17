---
title: 'Lync Server 2013: таблица медиа'
description: 'Lync Server 2013: таблица медиа.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media table
ms:assetid: 1e1b427f-59b5-4564-bde5-1002a80439ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398268(v=OCS.15)
ms:contentKeyID: 48183568
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 31e30d1f91c59b8e3aa7915fc0d513618d0f709f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558035"
---
# <a name="media-table-in-lync-server-2013"></a><span data-ttu-id="66e0c-103">Таблица мультимедиа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="66e0c-103">Media table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="66e0c-104">_**Последнее изменение темы:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="66e0c-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="66e0c-p101">Каждая запись представляет один тип мультимедиа, используемый в одноранговом сеансе. Если бы использовалось более одного типа мультимедиа, один сеанс был бы представлен несколькими записями в таблице.</span><span class="sxs-lookup"><span data-stu-id="66e0c-p101">Each record represents one media type used in a peer-to-peer session. One session would be represented by multiple records in the table, if more than one media type is used.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="66e0c-p102">Таблицу мультимедиа не следует использовать для вычисления длительности мультимедиа для сеанса. Эта таблица содержит сведения об обмене мультимедиа во время сеанса. Обмен мультимедиа осуществляется с помощью запроса INVITE, а время отправки этого  запроса указывается с помощью параметра StartTime. Время отправки запроса необязательно соответствует времени запуска обмена мультимедиа, который начинается только после приема сеанса вызываемым. EndTime обычно обозначает время завершения этого сеанса.</span><span class="sxs-lookup"><span data-stu-id="66e0c-p102">The Media table should not be used to calculate the media duration for a session. This table contains the signaling details of media exchange in a session. Media exchange is done by the INVITE request, and StartTime indicates the time that the INVITE was sent out. The invite time does not necessarily mean the media start time, because media starts only after the sessionee accepts the session. The EndTime usually means the end time of this session.</span></span>



</div>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="66e0c-111">Столбец</span><span class="sxs-lookup"><span data-stu-id="66e0c-111">Column</span></span></th>
<th><span data-ttu-id="66e0c-112">Тип данных</span><span class="sxs-lookup"><span data-stu-id="66e0c-112">Data Type</span></span></th>
<th><span data-ttu-id="66e0c-113">Ключ или индекс</span><span class="sxs-lookup"><span data-stu-id="66e0c-113">Key/Index</span></span></th>
<th><span data-ttu-id="66e0c-114">Сведения</span><span class="sxs-lookup"><span data-stu-id="66e0c-114">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="66e0c-115"><strong>сессионидтиме</strong></span><span class="sxs-lookup"><span data-stu-id="66e0c-115"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="66e0c-116">datetime</span><span class="sxs-lookup"><span data-stu-id="66e0c-116">datetime</span></span></p></td>
<td><p><span data-ttu-id="66e0c-117">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="66e0c-117">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="66e0c-118">Время запроса сеанса.</span><span class="sxs-lookup"><span data-stu-id="66e0c-118">Time of session request.</span></span> <span data-ttu-id="66e0c-119">В сочетании с параметром <strong>SessionIdSeq</strong> определяет сеанс уникальным образом.</span><span class="sxs-lookup"><span data-stu-id="66e0c-119">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="66e0c-120">Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="66e0c-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66e0c-121"><strong>сессионидсек</strong></span><span class="sxs-lookup"><span data-stu-id="66e0c-121"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="66e0c-122">int</span><span class="sxs-lookup"><span data-stu-id="66e0c-122">int</span></span></p></td>
<td><p><span data-ttu-id="66e0c-123">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="66e0c-123">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="66e0c-124">Идентификатор для идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="66e0c-124">ID number to identify the session.</span></span> <span data-ttu-id="66e0c-125">В сочетании с параметром <strong>SessionIdTime</strong> определяет сеанс уникальным образом.</span><span class="sxs-lookup"><span data-stu-id="66e0c-125">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="66e0c-126">Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="66e0c-126">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66e0c-127"><strong>медиаид</strong></span><span class="sxs-lookup"><span data-stu-id="66e0c-127"><strong>MediaId</strong></span></span></p></td>
<td><p><span data-ttu-id="66e0c-128">tinyint</span><span class="sxs-lookup"><span data-stu-id="66e0c-128">tinyint</span></span></p></td>
<td><p><span data-ttu-id="66e0c-129">Первичный, внешний</span><span class="sxs-lookup"><span data-stu-id="66e0c-129">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="66e0c-130">Уникальный номер, идентифицирующий этот тип мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="66e0c-130">Unique number identifying this media type.</span></span> <span data-ttu-id="66e0c-131">Дополнительные сведения см. <a href="lync-server-2013-medialist-table.md">в таблице таблица medialist в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="66e0c-131">See the <a href="lync-server-2013-medialist-table.md">MediaList table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66e0c-132"><strong>StartTime</strong></span><span class="sxs-lookup"><span data-stu-id="66e0c-132"><strong>StartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="66e0c-133">datetime</span><span class="sxs-lookup"><span data-stu-id="66e0c-133">datetime</span></span></p></td>
<td><p><span data-ttu-id="66e0c-134">Primary</span><span class="sxs-lookup"><span data-stu-id="66e0c-134">Primary</span></span></p></td>
<td><p><span data-ttu-id="66e0c-p106">Время отправки запроса мультимедиа, а не фактическое время начала обмена мультимедиа. <strong>StartTime</strong> включает в себя время настройки сеанса.</span><span class="sxs-lookup"><span data-stu-id="66e0c-p106">This is the time that a media request was sent out, not the real media start time. <strong>StartTime</strong> includes the session setup time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66e0c-137"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="66e0c-137"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="66e0c-138">datetime</span><span class="sxs-lookup"><span data-stu-id="66e0c-138">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66e0c-139">Время завершения этого сеанса.</span><span class="sxs-lookup"><span data-stu-id="66e0c-139">This is the end time of the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

