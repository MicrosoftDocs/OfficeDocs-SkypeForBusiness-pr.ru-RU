---
title: 'Lync Server 2013: таблица Device'
description: 'Lync Server 2013: таблица Device.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Device table
ms:assetid: d5a4f777-bc12-4ce8-bc0d-867d5e22b436
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398930(v=OCS.15)
ms:contentKeyID: 48185544
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 46de64a49eace52d62cbd6384fcae680b5c511b9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575645"
---
# <a name="device-table-in-lync-server-2013"></a><span data-ttu-id="68592-103">Таблица Devices в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68592-103">Device table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="68592-104">_**Последнее изменение темы:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="68592-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="68592-p101">Таблица "Устройство" представляет собой вспомогательную таблицу, в которой хранятся сведения о различных устройствах записи и отображения. Каждому устройству соответствует одна запись в таблице.</span><span class="sxs-lookup"><span data-stu-id="68592-p101">The Device table is a supporting table that stores information about the various capture or render devices. Each record in the table represents one device.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="68592-107"><strong>Column</strong></span><span class="sxs-lookup"><span data-stu-id="68592-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="68592-108"><strong>Тип данных</strong></span><span class="sxs-lookup"><span data-stu-id="68592-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="68592-109"><strong>Ключ или индекс</strong></span><span class="sxs-lookup"><span data-stu-id="68592-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="68592-110"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="68592-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="68592-111"><strong>девицекэй</strong></span><span class="sxs-lookup"><span data-stu-id="68592-111"><strong>DeviceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="68592-112">int</span><span class="sxs-lookup"><span data-stu-id="68592-112">int</span></span></p></td>
<td><p><span data-ttu-id="68592-113">Primary</span><span class="sxs-lookup"><span data-stu-id="68592-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="68592-114">Уникальный номер, идентифицирующий это устройство.</span><span class="sxs-lookup"><span data-stu-id="68592-114">Unique number identifying this device.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68592-115"><strong>DeviceName</strong></span><span class="sxs-lookup"><span data-stu-id="68592-115"><strong>DeviceName</strong></span></span></p></td>
<td><p><span data-ttu-id="68592-116">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="68592-116">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="68592-117">Значения DeviceName и DeviceType уникальны</span><span class="sxs-lookup"><span data-stu-id="68592-117">DeviceName + DeviceType is unique</span></span></p></td>
<td><p><span data-ttu-id="68592-118">Имя устройства.</span><span class="sxs-lookup"><span data-stu-id="68592-118">Device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68592-119"><strong>DeviceType</strong></span><span class="sxs-lookup"><span data-stu-id="68592-119"><strong>DeviceType</strong></span></span></p></td>
<td><p><span data-ttu-id="68592-120">Битовая</span><span class="sxs-lookup"><span data-stu-id="68592-120">bit</span></span></p></td>
<td><p><span data-ttu-id="68592-121">Значения DeviceName и DeviceType уникальны</span><span class="sxs-lookup"><span data-stu-id="68592-121">DeviceName + DeviceType is unique</span></span></p></td>
<td><p><span data-ttu-id="68592-p102">Тип устройства. 1 - устройство записи, 0 - устройство отображения.</span><span class="sxs-lookup"><span data-stu-id="68592-p102">Device type. 1 is a capture device, 0 is a render device.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

