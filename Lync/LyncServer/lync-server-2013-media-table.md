---
title: 'Lync Server 2013: таблица медиа'
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
ms.openlocfilehash: 369e1ace7e0f3f9326896373a640597360ded81d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516176"
---
# <a name="media-table-in-lync-server-2013"></a><span data-ttu-id="88cbf-102">Таблица мультимедиа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="88cbf-102">Media table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="88cbf-103">_**Последнее изменение темы:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="88cbf-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="88cbf-p101">Каждая запись представляет один тип мультимедиа, используемый в одноранговом сеансе. Если бы использовалось более одного типа мультимедиа, один сеанс был бы представлен несколькими записями в таблице.</span><span class="sxs-lookup"><span data-stu-id="88cbf-p101">Each record represents one media type used in a peer-to-peer session. One session would be represented by multiple records in the table, if more than one media type is used.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="88cbf-p102">Таблицу мультимедиа не следует использовать для вычисления длительности мультимедиа для сеанса. Эта таблица содержит сведения об обмене мультимедиа во время сеанса. Обмен мультимедиа осуществляется с помощью запроса INVITE, а время отправки этого  запроса указывается с помощью параметра StartTime. Время отправки запроса необязательно соответствует времени запуска обмена мультимедиа, который начинается только после приема сеанса вызываемым. EndTime обычно обозначает время завершения этого сеанса.</span><span class="sxs-lookup"><span data-stu-id="88cbf-p102">The Media table should not be used to calculate the media duration for a session. This table contains the signaling details of media exchange in a session. Media exchange is done by the INVITE request, and StartTime indicates the time that the INVITE was sent out. The invite time does not necessarily mean the media start time, because media starts only after the sessionee accepts the session. The EndTime usually means the end time of this session.</span></span>



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
<th><span data-ttu-id="88cbf-110">Столбец</span><span class="sxs-lookup"><span data-stu-id="88cbf-110">Column</span></span></th>
<th><span data-ttu-id="88cbf-111">Тип данных</span><span class="sxs-lookup"><span data-stu-id="88cbf-111">Data Type</span></span></th>
<th><span data-ttu-id="88cbf-112">Ключ или индекс</span><span class="sxs-lookup"><span data-stu-id="88cbf-112">Key/Index</span></span></th>
<th><span data-ttu-id="88cbf-113">Сведения</span><span class="sxs-lookup"><span data-stu-id="88cbf-113">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="88cbf-114"><strong>сессионидтиме</strong></span><span class="sxs-lookup"><span data-stu-id="88cbf-114"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="88cbf-115">datetime</span><span class="sxs-lookup"><span data-stu-id="88cbf-115">datetime</span></span></p></td>
<td><p><span data-ttu-id="88cbf-116">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="88cbf-116">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="88cbf-117">Время запроса сеанса.</span><span class="sxs-lookup"><span data-stu-id="88cbf-117">Time of session request.</span></span> <span data-ttu-id="88cbf-118">В сочетании с параметром <strong>SessionIdSeq</strong> определяет сеанс уникальным образом.</span><span class="sxs-lookup"><span data-stu-id="88cbf-118">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="88cbf-119">Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="88cbf-119">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88cbf-120"><strong>сессионидсек</strong></span><span class="sxs-lookup"><span data-stu-id="88cbf-120"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="88cbf-121">int</span><span class="sxs-lookup"><span data-stu-id="88cbf-121">int</span></span></p></td>
<td><p><span data-ttu-id="88cbf-122">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="88cbf-122">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="88cbf-123">Идентификатор для идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="88cbf-123">ID number to identify the session.</span></span> <span data-ttu-id="88cbf-124">В сочетании с параметром <strong>SessionIdTime</strong> определяет сеанс уникальным образом.</span><span class="sxs-lookup"><span data-stu-id="88cbf-124">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="88cbf-125">Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="88cbf-125">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88cbf-126"><strong>медиаид</strong></span><span class="sxs-lookup"><span data-stu-id="88cbf-126"><strong>MediaId</strong></span></span></p></td>
<td><p><span data-ttu-id="88cbf-127">tinyint</span><span class="sxs-lookup"><span data-stu-id="88cbf-127">tinyint</span></span></p></td>
<td><p><span data-ttu-id="88cbf-128">Первичный, внешний</span><span class="sxs-lookup"><span data-stu-id="88cbf-128">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="88cbf-129">Уникальный номер, идентифицирующий этот тип мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="88cbf-129">Unique number identifying this media type.</span></span> <span data-ttu-id="88cbf-130">Дополнительные сведения см. <a href="lync-server-2013-medialist-table.md">в таблице таблица medialist в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="88cbf-130">See the <a href="lync-server-2013-medialist-table.md">MediaList table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88cbf-131"><strong>StartTime</strong></span><span class="sxs-lookup"><span data-stu-id="88cbf-131"><strong>StartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="88cbf-132">datetime</span><span class="sxs-lookup"><span data-stu-id="88cbf-132">datetime</span></span></p></td>
<td><p><span data-ttu-id="88cbf-133">Primary</span><span class="sxs-lookup"><span data-stu-id="88cbf-133">Primary</span></span></p></td>
<td><p><span data-ttu-id="88cbf-p106">Время отправки запроса мультимедиа, а не фактическое время начала обмена мультимедиа. <strong>StartTime</strong> включает в себя время настройки сеанса.</span><span class="sxs-lookup"><span data-stu-id="88cbf-p106">This is the time that a media request was sent out, not the real media start time. <strong>StartTime</strong> includes the session setup time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88cbf-136"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="88cbf-136"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="88cbf-137">datetime</span><span class="sxs-lookup"><span data-stu-id="88cbf-137">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88cbf-138">Время завершения этого сеанса.</span><span class="sxs-lookup"><span data-stu-id="88cbf-138">This is the end time of the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

