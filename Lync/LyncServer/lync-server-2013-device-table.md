---
title: 'Lync Server 2013: таблица Device'
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
ms.openlocfilehash: 8bd5b62059329d9a2277e28f1a2ae08c25384bde
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48522436"
---
# <a name="device-table-in-lync-server-2013"></a><span data-ttu-id="97610-102">Таблица Devices в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="97610-102">Device table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="97610-103">_**Последнее изменение темы:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="97610-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="97610-p101">Таблица "Устройство" представляет собой вспомогательную таблицу, в которой хранятся сведения о различных устройствах записи и отображения. Каждому устройству соответствует одна запись в таблице.</span><span class="sxs-lookup"><span data-stu-id="97610-p101">The Device table is a supporting table that stores information about the various capture or render devices. Each record in the table represents one device.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="97610-106"><strong>Column</strong></span><span class="sxs-lookup"><span data-stu-id="97610-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="97610-107"><strong>Тип данных</strong></span><span class="sxs-lookup"><span data-stu-id="97610-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="97610-108"><strong>Ключ или индекс</strong></span><span class="sxs-lookup"><span data-stu-id="97610-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="97610-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="97610-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="97610-110"><strong>девицекэй</strong></span><span class="sxs-lookup"><span data-stu-id="97610-110"><strong>DeviceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="97610-111">int</span><span class="sxs-lookup"><span data-stu-id="97610-111">int</span></span></p></td>
<td><p><span data-ttu-id="97610-112">Primary</span><span class="sxs-lookup"><span data-stu-id="97610-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="97610-113">Уникальный номер, идентифицирующий это устройство.</span><span class="sxs-lookup"><span data-stu-id="97610-113">Unique number identifying this device.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97610-114"><strong>DeviceName</strong></span><span class="sxs-lookup"><span data-stu-id="97610-114"><strong>DeviceName</strong></span></span></p></td>
<td><p><span data-ttu-id="97610-115">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="97610-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="97610-116">Значения DeviceName и DeviceType уникальны</span><span class="sxs-lookup"><span data-stu-id="97610-116">DeviceName + DeviceType is unique</span></span></p></td>
<td><p><span data-ttu-id="97610-117">Имя устройства.</span><span class="sxs-lookup"><span data-stu-id="97610-117">Device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97610-118"><strong>DeviceType</strong></span><span class="sxs-lookup"><span data-stu-id="97610-118"><strong>DeviceType</strong></span></span></p></td>
<td><p><span data-ttu-id="97610-119">Битовая</span><span class="sxs-lookup"><span data-stu-id="97610-119">bit</span></span></p></td>
<td><p><span data-ttu-id="97610-120">Значения DeviceName и DeviceType уникальны</span><span class="sxs-lookup"><span data-stu-id="97610-120">DeviceName + DeviceType is unique</span></span></p></td>
<td><p><span data-ttu-id="97610-p102">Тип устройства. 1 - устройство записи, 0 - устройство отображения.</span><span class="sxs-lookup"><span data-stu-id="97610-p102">Device type. 1 is a capture device, 0 is a render device.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

