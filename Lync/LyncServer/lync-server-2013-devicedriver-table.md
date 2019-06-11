---
title: 'Lync Server 2013: таблица DeviceDriver'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DeviceDriver table
ms:assetid: ca91a0b4-98c0-49f6-af9d-7d0f8ac75f1a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398844(v=OCS.15)
ms:contentKeyID: 48185449
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ea4ab9ad8b2eda5388791c98c1e1da90d9bd5c65
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834416"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="devicedriver-table-in-lync-server-2013"></a><span data-ttu-id="ec6a2-102">Таблица DeviceDriver в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ec6a2-102">DeviceDriver table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ec6a2-103">_**Тема последнего изменения:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="ec6a2-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="ec6a2-104">Таблица Девицедривер является вспомогательной таблицей.</span><span class="sxs-lookup"><span data-stu-id="ec6a2-104">The DeviceDriver table is a supporting table.</span></span> <span data-ttu-id="ec6a2-105">Каждая запись представляет драйвер, который используется устройством захвата или устройством рендеринга.</span><span class="sxs-lookup"><span data-stu-id="ec6a2-105">Each record represents a driver used by either a capture device or render device.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ec6a2-106"><strong>Столбец</strong></span><span class="sxs-lookup"><span data-stu-id="ec6a2-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="ec6a2-107"><strong>Тип данных</strong></span><span class="sxs-lookup"><span data-stu-id="ec6a2-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="ec6a2-108"><strong>Ключ/индекс</strong></span><span class="sxs-lookup"><span data-stu-id="ec6a2-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="ec6a2-109"><strong>Сведения</strong></span><span class="sxs-lookup"><span data-stu-id="ec6a2-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ec6a2-110"><strong>Девицедриверкэй</strong></span><span class="sxs-lookup"><span data-stu-id="ec6a2-110"><strong>DeviceDriverKey</strong></span></span></p></td>
<td><p><span data-ttu-id="ec6a2-111">целое</span><span class="sxs-lookup"><span data-stu-id="ec6a2-111">int</span></span></p></td>
<td><p><span data-ttu-id="ec6a2-112">Primary</span><span class="sxs-lookup"><span data-stu-id="ec6a2-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="ec6a2-113">Уникальный номер, идентифицирующий эту запись драйвера устройства.</span><span class="sxs-lookup"><span data-stu-id="ec6a2-113">Unique number identifying this device driver record.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec6a2-114"><strong>DeviceDriver</strong></span><span class="sxs-lookup"><span data-stu-id="ec6a2-114"><strong>DeviceDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="ec6a2-115">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="ec6a2-115">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ec6a2-116">повторя</span><span class="sxs-lookup"><span data-stu-id="ec6a2-116">unique</span></span></p></td>
<td><p><span data-ttu-id="ec6a2-117">Имя драйвера устройства.</span><span class="sxs-lookup"><span data-stu-id="ec6a2-117">Device driver name.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

