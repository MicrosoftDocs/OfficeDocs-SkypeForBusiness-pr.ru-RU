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
ms.openlocfilehash: 11da225da1a8120f5de7ac21b3beb318326601f9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735589"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="endpoint-table-in-lync-server-2013"></a><span data-ttu-id="a304b-102">Таблица Endpoint в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a304b-102">Endpoint table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a304b-103">_**Тема последнего изменения:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="a304b-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="a304b-104">Таблица конечных точек — это вспомогательная таблица, в которой хранятся сведения о конечных точках, участвующих в сеансах, записанных в базе данных.</span><span class="sxs-lookup"><span data-stu-id="a304b-104">The Endpoint table is a supporting table that stores information about the endpoints that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="a304b-105">Каждая запись в таблице представляет одну конечную точку.</span><span class="sxs-lookup"><span data-stu-id="a304b-105">Each record in the table represents one endpoint.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a304b-106"><strong>Столбец</strong></span><span class="sxs-lookup"><span data-stu-id="a304b-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="a304b-107"><strong>Тип данных</strong></span><span class="sxs-lookup"><span data-stu-id="a304b-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="a304b-108"><strong>Ключ/индекс</strong></span><span class="sxs-lookup"><span data-stu-id="a304b-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="a304b-109"><strong>Сведения</strong></span><span class="sxs-lookup"><span data-stu-id="a304b-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a304b-110"><strong>ендпоинткэй</strong></span><span class="sxs-lookup"><span data-stu-id="a304b-110"><strong>EndpointKey</strong></span></span></p></td>
<td><p><span data-ttu-id="a304b-111">целое</span><span class="sxs-lookup"><span data-stu-id="a304b-111">int</span></span></p></td>
<td><p><span data-ttu-id="a304b-112">Primary</span><span class="sxs-lookup"><span data-stu-id="a304b-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="a304b-113">Уникальный номер, идентифицирующий эту конечную точку.</span><span class="sxs-lookup"><span data-stu-id="a304b-113">Unique number identifying this endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a304b-114"><strong>Имя</strong></span><span class="sxs-lookup"><span data-stu-id="a304b-114"><strong>Name</strong></span></span></p></td>
<td><p><span data-ttu-id="a304b-115">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="a304b-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a304b-116">Повторя</span><span class="sxs-lookup"><span data-stu-id="a304b-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="a304b-117">Имя конечной точки.</span><span class="sxs-lookup"><span data-stu-id="a304b-117">Endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a304b-118"><strong>OS</strong></span><span class="sxs-lookup"><span data-stu-id="a304b-118"><strong>OS</strong></span></span></p></td>
<td><p><span data-ttu-id="a304b-119">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="a304b-119">nvarchar(128)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a304b-120">Операционная система (ОС) конечной точки.</span><span class="sxs-lookup"><span data-stu-id="a304b-120">Operating system (OS) of the endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a304b-121"><strong>кпунаме</strong></span><span class="sxs-lookup"><span data-stu-id="a304b-121"><strong>CPUName</strong></span></span></p></td>
<td><p><span data-ttu-id="a304b-122">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="a304b-122">nvarchar(128)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a304b-123">Имя ЦП конечной точки.</span><span class="sxs-lookup"><span data-stu-id="a304b-123">CPU name of the endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a304b-124"><strong>кпунумберофкорес</strong></span><span class="sxs-lookup"><span data-stu-id="a304b-124"><strong>CPUNumberOfCores</strong></span></span></p></td>
<td><p><span data-ttu-id="a304b-125">smallint</span><span class="sxs-lookup"><span data-stu-id="a304b-125">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a304b-126">Количество ядер ЦП конечной точки.</span><span class="sxs-lookup"><span data-stu-id="a304b-126">Number of CPU cores of the endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a304b-127"><strong>кпупроцессорспид</strong></span><span class="sxs-lookup"><span data-stu-id="a304b-127"><strong>CPUProcessorSpeed</strong></span></span></p></td>
<td><p><span data-ttu-id="a304b-128">целое</span><span class="sxs-lookup"><span data-stu-id="a304b-128">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a304b-129">Тактовая частота процессора для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="a304b-129">CPU processor speed of the endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a304b-130"><strong>виртуализатионфлаг</strong></span><span class="sxs-lookup"><span data-stu-id="a304b-130"><strong>VirtualizationFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="a304b-131">tinyint</span><span class="sxs-lookup"><span data-stu-id="a304b-131">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a304b-132">Битовый флаг, указывающий на то, что система работает в виртуализованной среде.</span><span class="sxs-lookup"><span data-stu-id="a304b-132">Bit flag that indicates if the system is running in a virtualized environment:</span></span></p>
<ul>
<li><p><span data-ttu-id="a304b-133">0x0000 — None (нет)</span><span class="sxs-lookup"><span data-stu-id="a304b-133">0x0000 – None</span></span></p></li>
<li><p><span data-ttu-id="a304b-134">0x0001 — HyperV</span><span class="sxs-lookup"><span data-stu-id="a304b-134">0x0001 – HyperV</span></span></p></li>
<li><p><span data-ttu-id="a304b-135">0x0002 — VMWare</span><span class="sxs-lookup"><span data-stu-id="a304b-135">0x0002 – VMWare</span></span></p></li>
<li><p><span data-ttu-id="a304b-136">0x0004 — Virtual PC</span><span class="sxs-lookup"><span data-stu-id="a304b-136">0x0004 – Virtual PC</span></span></p></li>
<li><p><span data-ttu-id="a304b-137">0x0008 – ПК с Xen</span><span class="sxs-lookup"><span data-stu-id="a304b-137">0x0008 – Xen PC</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

