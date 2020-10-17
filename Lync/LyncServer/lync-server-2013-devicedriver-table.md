---
title: 'Lync Server 2013: таблица таблица devicedriver'
description: 'Lync Server 2013: таблица таблица devicedriver.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DeviceDriver table
ms:assetid: ca91a0b4-98c0-49f6-af9d-7d0f8ac75f1a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398844(v=OCS.15)
ms:contentKeyID: 48185449
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3d81e2e27ff5196112c6057c429f924e5b1c3e4b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565975"
---
# <a name="devicedriver-table-in-lync-server-2013"></a><span data-ttu-id="c5061-103">Таблица Таблица devicedriver в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c5061-103">DeviceDriver table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c5061-104">_**Последнее изменение темы:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="c5061-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="c5061-p101">Таблица DeviceDriver является вспомогательной. Каждая запись представляет драйвер, используемый устройством захвата или отображения.</span><span class="sxs-lookup"><span data-stu-id="c5061-p101">The DeviceDriver table is a supporting table. Each record represents a driver used by either a capture device or render device.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c5061-107"><strong>Column</strong></span><span class="sxs-lookup"><span data-stu-id="c5061-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="c5061-108"><strong>Тип данных</strong></span><span class="sxs-lookup"><span data-stu-id="c5061-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="c5061-109"><strong>Ключ или индекс</strong></span><span class="sxs-lookup"><span data-stu-id="c5061-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="c5061-110"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="c5061-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c5061-111"><strong>девицедриверкэй</strong></span><span class="sxs-lookup"><span data-stu-id="c5061-111"><strong>DeviceDriverKey</strong></span></span></p></td>
<td><p><span data-ttu-id="c5061-112">int</span><span class="sxs-lookup"><span data-stu-id="c5061-112">int</span></span></p></td>
<td><p><span data-ttu-id="c5061-113">Primary</span><span class="sxs-lookup"><span data-stu-id="c5061-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="c5061-114">Уникальный номер, идентифицирующий эту запись драйвера устройства.</span><span class="sxs-lookup"><span data-stu-id="c5061-114">Unique number identifying this device driver record.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5061-115"><strong>DeviceDriver</strong></span><span class="sxs-lookup"><span data-stu-id="c5061-115"><strong>DeviceDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="c5061-116">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="c5061-116">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c5061-117">уникальный</span><span class="sxs-lookup"><span data-stu-id="c5061-117">unique</span></span></p></td>
<td><p><span data-ttu-id="c5061-118">Имя драйвера устройства.</span><span class="sxs-lookup"><span data-stu-id="c5061-118">Device driver name.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

