---
title: 'Lync Server 2013: таблица Endpoint'
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
ms.openlocfilehash: 33b2f42f1cd122f9f19cfbf04a1c255894ce6e97
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137478"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="endpoint-table-in-lync-server-2013"></a><span data-ttu-id="85795-102">Таблица конечной точки в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="85795-102">Endpoint table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="85795-103">_**Последнее изменение темы:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="85795-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="85795-104">Таблица Endpoint — это вспомогательная таблица, в которой хранятся сведения о конечных точках, которые участвовали в сеансах, записанных в базе данных.</span><span class="sxs-lookup"><span data-stu-id="85795-104">The Endpoint table is a supporting table that stores information about the endpoints that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="85795-105">Каждая запись в таблице представляет одну конечную точку.</span><span class="sxs-lookup"><span data-stu-id="85795-105">Each record in the table represents one endpoint.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="85795-106"><strong>Column</strong></span><span class="sxs-lookup"><span data-stu-id="85795-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="85795-107"><strong>Тип данных</strong></span><span class="sxs-lookup"><span data-stu-id="85795-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="85795-108"><strong>Ключ или индекс</strong></span><span class="sxs-lookup"><span data-stu-id="85795-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="85795-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="85795-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="85795-110"><strong>ендпоинткэй</strong></span><span class="sxs-lookup"><span data-stu-id="85795-110"><strong>EndpointKey</strong></span></span></p></td>
<td><p><span data-ttu-id="85795-111">int</span><span class="sxs-lookup"><span data-stu-id="85795-111">int</span></span></p></td>
<td><p><span data-ttu-id="85795-112">Primary</span><span class="sxs-lookup"><span data-stu-id="85795-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="85795-113">Уникальный номер, идентифицирующий эту конечную точку.</span><span class="sxs-lookup"><span data-stu-id="85795-113">Unique number identifying this endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85795-114"><strong>Имя</strong></span><span class="sxs-lookup"><span data-stu-id="85795-114"><strong>Name</strong></span></span></p></td>
<td><p><span data-ttu-id="85795-115">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="85795-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="85795-116">Уникальные</span><span class="sxs-lookup"><span data-stu-id="85795-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="85795-117">Имя конечной точки.</span><span class="sxs-lookup"><span data-stu-id="85795-117">Endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="85795-118"><strong>СОВМЕСТИМ</strong></span><span class="sxs-lookup"><span data-stu-id="85795-118"><strong>OS</strong></span></span></p></td>
<td><p><span data-ttu-id="85795-119">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="85795-119">nvarchar(128)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="85795-120">Операционная система (ОС) конечной точки.</span><span class="sxs-lookup"><span data-stu-id="85795-120">Operating system (OS) of the endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85795-121"><strong>кпунаме</strong></span><span class="sxs-lookup"><span data-stu-id="85795-121"><strong>CPUName</strong></span></span></p></td>
<td><p><span data-ttu-id="85795-122">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="85795-122">nvarchar(128)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="85795-123">Имя ЦП конечной точки.</span><span class="sxs-lookup"><span data-stu-id="85795-123">CPU name of the endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="85795-124"><strong>кпунумберофкорес</strong></span><span class="sxs-lookup"><span data-stu-id="85795-124"><strong>CPUNumberOfCores</strong></span></span></p></td>
<td><p><span data-ttu-id="85795-125">smallint</span><span class="sxs-lookup"><span data-stu-id="85795-125">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="85795-126">Количество ядер ЦП конечной точки.</span><span class="sxs-lookup"><span data-stu-id="85795-126">Number of CPU cores of the endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85795-127"><strong>кпупроцессорспид</strong></span><span class="sxs-lookup"><span data-stu-id="85795-127"><strong>CPUProcessorSpeed</strong></span></span></p></td>
<td><p><span data-ttu-id="85795-128">int</span><span class="sxs-lookup"><span data-stu-id="85795-128">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="85795-129">Скорость ЦП конечной точки.</span><span class="sxs-lookup"><span data-stu-id="85795-129">CPU processor speed of the endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="85795-130"><strong>виртуализатионфлаг</strong></span><span class="sxs-lookup"><span data-stu-id="85795-130"><strong>VirtualizationFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="85795-131">tinyint</span><span class="sxs-lookup"><span data-stu-id="85795-131">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="85795-132">Битовый флаг, указывающий, работает ли система в виртуализированной среде:</span><span class="sxs-lookup"><span data-stu-id="85795-132">Bit flag that indicates if the system is running in a virtualized environment:</span></span></p>
<ul>
<li><p><span data-ttu-id="85795-133">0x0000 — нет</span><span class="sxs-lookup"><span data-stu-id="85795-133">0x0000 – None</span></span></p></li>
<li><p><span data-ttu-id="85795-134">0x0001 — HyperV</span><span class="sxs-lookup"><span data-stu-id="85795-134">0x0001 – HyperV</span></span></p></li>
<li><p><span data-ttu-id="85795-135">0x0002 — VMWare</span><span class="sxs-lookup"><span data-stu-id="85795-135">0x0002 – VMWare</span></span></p></li>
<li><p><span data-ttu-id="85795-136">0x0004 — Virtual PC</span><span class="sxs-lookup"><span data-stu-id="85795-136">0x0004 – Virtual PC</span></span></p></li>
<li><p><span data-ttu-id="85795-137">0x0008 — компьютер Xen</span><span class="sxs-lookup"><span data-stu-id="85795-137">0x0008 – Xen PC</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

