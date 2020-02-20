---
title: 'Lync Server 2013: таблица таблица devicedriver'
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
ms.openlocfilehash: 0a4638676371b2de3673fbb7ff805b401ffb00dc
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147092"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="devicedriver-table-in-lync-server-2013"></a><span data-ttu-id="eb00a-102">Таблица Таблица devicedriver в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eb00a-102">DeviceDriver table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eb00a-103">_**Последнее изменение темы:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="eb00a-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="eb00a-p101">Таблица DeviceDriver является вспомогательной. Каждая запись представляет драйвер, используемый устройством захвата или отображения.</span><span class="sxs-lookup"><span data-stu-id="eb00a-p101">The DeviceDriver table is a supporting table. Each record represents a driver used by either a capture device or render device.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="eb00a-106"><strong>Column</strong></span><span class="sxs-lookup"><span data-stu-id="eb00a-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="eb00a-107"><strong>Тип данных</strong></span><span class="sxs-lookup"><span data-stu-id="eb00a-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="eb00a-108"><strong>Ключ или индекс</strong></span><span class="sxs-lookup"><span data-stu-id="eb00a-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="eb00a-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="eb00a-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="eb00a-110"><strong>девицедриверкэй</strong></span><span class="sxs-lookup"><span data-stu-id="eb00a-110"><strong>DeviceDriverKey</strong></span></span></p></td>
<td><p><span data-ttu-id="eb00a-111">int</span><span class="sxs-lookup"><span data-stu-id="eb00a-111">int</span></span></p></td>
<td><p><span data-ttu-id="eb00a-112">Primary</span><span class="sxs-lookup"><span data-stu-id="eb00a-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="eb00a-113">Уникальный номер, идентифицирующий эту запись драйвера устройства.</span><span class="sxs-lookup"><span data-stu-id="eb00a-113">Unique number identifying this device driver record.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb00a-114"><strong>Таблица devicedriver</strong></span><span class="sxs-lookup"><span data-stu-id="eb00a-114"><strong>DeviceDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="eb00a-115">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="eb00a-115">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="eb00a-116">уникальный</span><span class="sxs-lookup"><span data-stu-id="eb00a-116">unique</span></span></p></td>
<td><p><span data-ttu-id="eb00a-117">Имя драйвера устройства.</span><span class="sxs-lookup"><span data-stu-id="eb00a-117">Device driver name.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

