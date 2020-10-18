---
title: 'Lync Server 2013: таблица Endpoint'
description: 'Lync Server 2013: таблица Endpoint.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Endpoint table
ms:assetid: 500f330d-4d7d-4e88-b1cc-fef9a9de6b5c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398327(v=OCS.15)
ms:contentKeyID: 48184098
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 614872eee41b5d8e56da4b96cf5bbe3a4a1cf4d2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575625"
---
# <a name="endpoint-table-in-lync-server-2013"></a><span data-ttu-id="12bce-103">Таблица конечной точки в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12bce-103">Endpoint table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="12bce-104">_**Последнее изменение темы:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="12bce-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="12bce-105">Таблица Endpoint — это вспомогательная таблица, в которой хранятся сведения о конечных точках, которые участвовали в сеансах, записанных в базе данных.</span><span class="sxs-lookup"><span data-stu-id="12bce-105">The Endpoint table is a supporting table that stores information about the endpoints that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="12bce-106">Каждая запись в таблице представляет одну конечную точку.</span><span class="sxs-lookup"><span data-stu-id="12bce-106">Each record in the table represents one endpoint.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="12bce-107"><strong>Column</strong></span><span class="sxs-lookup"><span data-stu-id="12bce-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="12bce-108"><strong>Тип данных</strong></span><span class="sxs-lookup"><span data-stu-id="12bce-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="12bce-109"><strong>Ключ или индекс</strong></span><span class="sxs-lookup"><span data-stu-id="12bce-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="12bce-110"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="12bce-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="12bce-111"><strong>ендпоинткэй</strong></span><span class="sxs-lookup"><span data-stu-id="12bce-111"><strong>EndpointKey</strong></span></span></p></td>
<td><p><span data-ttu-id="12bce-112">int</span><span class="sxs-lookup"><span data-stu-id="12bce-112">int</span></span></p></td>
<td><p><span data-ttu-id="12bce-113">Primary</span><span class="sxs-lookup"><span data-stu-id="12bce-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="12bce-114">Уникальный номер, идентифицирующий эту конечную точку.</span><span class="sxs-lookup"><span data-stu-id="12bce-114">Unique number identifying this endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12bce-115"><strong>Название</strong></span><span class="sxs-lookup"><span data-stu-id="12bce-115"><strong>Name</strong></span></span></p></td>
<td><p><span data-ttu-id="12bce-116">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="12bce-116">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="12bce-117">Уникальные</span><span class="sxs-lookup"><span data-stu-id="12bce-117">Unique</span></span></p></td>
<td><p><span data-ttu-id="12bce-118">Имя конечной точки.</span><span class="sxs-lookup"><span data-stu-id="12bce-118">Endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12bce-119"><strong>СОВМЕСТИМ</strong></span><span class="sxs-lookup"><span data-stu-id="12bce-119"><strong>OS</strong></span></span></p></td>
<td><p><span data-ttu-id="12bce-120">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="12bce-120">nvarchar(128)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="12bce-121">Операционная система (ОС) конечной точки.</span><span class="sxs-lookup"><span data-stu-id="12bce-121">Operating system (OS) of the endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12bce-122"><strong>кпунаме</strong></span><span class="sxs-lookup"><span data-stu-id="12bce-122"><strong>CPUName</strong></span></span></p></td>
<td><p><span data-ttu-id="12bce-123">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="12bce-123">nvarchar(128)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="12bce-124">Имя ЦП конечной точки.</span><span class="sxs-lookup"><span data-stu-id="12bce-124">CPU name of the endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12bce-125"><strong>кпунумберофкорес</strong></span><span class="sxs-lookup"><span data-stu-id="12bce-125"><strong>CPUNumberOfCores</strong></span></span></p></td>
<td><p><span data-ttu-id="12bce-126">smallint</span><span class="sxs-lookup"><span data-stu-id="12bce-126">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="12bce-127">Количество ядер ЦП конечной точки.</span><span class="sxs-lookup"><span data-stu-id="12bce-127">Number of CPU cores of the endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12bce-128"><strong>кпупроцессорспид</strong></span><span class="sxs-lookup"><span data-stu-id="12bce-128"><strong>CPUProcessorSpeed</strong></span></span></p></td>
<td><p><span data-ttu-id="12bce-129">int</span><span class="sxs-lookup"><span data-stu-id="12bce-129">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="12bce-130">Скорость ЦП конечной точки.</span><span class="sxs-lookup"><span data-stu-id="12bce-130">CPU processor speed of the endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12bce-131"><strong>виртуализатионфлаг</strong></span><span class="sxs-lookup"><span data-stu-id="12bce-131"><strong>VirtualizationFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="12bce-132">tinyint</span><span class="sxs-lookup"><span data-stu-id="12bce-132">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="12bce-133">Битовый флаг, указывающий, работает ли система в виртуализированной среде:</span><span class="sxs-lookup"><span data-stu-id="12bce-133">Bit flag that indicates if the system is running in a virtualized environment:</span></span></p>
<ul>
<li><p><span data-ttu-id="12bce-134">0x0000 — нет</span><span class="sxs-lookup"><span data-stu-id="12bce-134">0x0000 – None</span></span></p></li>
<li><p><span data-ttu-id="12bce-135">0x0001 — HyperV</span><span class="sxs-lookup"><span data-stu-id="12bce-135">0x0001 – HyperV</span></span></p></li>
<li><p><span data-ttu-id="12bce-136">0x0002 — VMWare</span><span class="sxs-lookup"><span data-stu-id="12bce-136">0x0002 – VMWare</span></span></p></li>
<li><p><span data-ttu-id="12bce-137">0x0004 — Virtual PC</span><span class="sxs-lookup"><span data-stu-id="12bce-137">0x0004 – Virtual PC</span></span></p></li>
<li><p><span data-ttu-id="12bce-138">0x0008 — компьютер Xen</span><span class="sxs-lookup"><span data-stu-id="12bce-138">0x0008 – Xen PC</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

