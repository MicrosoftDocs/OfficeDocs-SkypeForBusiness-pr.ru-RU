---
title: 'Lync Server 2013: таблица AppliedBandwidthSource'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: AppliedBandwidthSource table
ms:assetid: 24fb3caf-19b3-4c0a-90d7-ca5d53de32ad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425725(v=OCS.15)
ms:contentKeyID: 48183638
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7f4c7d78353a60ad4c3bf9a7ff3efb363bd01c82
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849727"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="appliedbandwidthsource-table-in-lync-server-2013"></a><span data-ttu-id="e366f-102">Таблица AppliedBandwidthSource в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e366f-102">AppliedBandwidthSource table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e366f-103">_**Тема последнего изменения:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="e366f-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="e366f-104">Таблица Апплиедбандвидссаурце является вспомогательной таблицей.</span><span class="sxs-lookup"><span data-stu-id="e366f-104">The AppliedBandwidthSource table is a supporting table.</span></span> <span data-ttu-id="e366f-105">Каждая запись представляет один источник.</span><span class="sxs-lookup"><span data-stu-id="e366f-105">Each record represents one source.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e366f-106"><strong>Столбец</strong></span><span class="sxs-lookup"><span data-stu-id="e366f-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="e366f-107"><strong>Тип данных</strong></span><span class="sxs-lookup"><span data-stu-id="e366f-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="e366f-108"><strong>Ключ/индекс</strong></span><span class="sxs-lookup"><span data-stu-id="e366f-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="e366f-109"><strong>Сведения</strong></span><span class="sxs-lookup"><span data-stu-id="e366f-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e366f-110"><strong>Апплиедбандвидссаурцекэй</strong></span><span class="sxs-lookup"><span data-stu-id="e366f-110"><strong>AppliedBandwidthSourceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="e366f-111">целое</span><span class="sxs-lookup"><span data-stu-id="e366f-111">int</span></span></p></td>
<td><p><span data-ttu-id="e366f-112">Primary</span><span class="sxs-lookup"><span data-stu-id="e366f-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="e366f-113">Уникальный номер, идентифицирующий источник.</span><span class="sxs-lookup"><span data-stu-id="e366f-113">Unique number identifying the source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e366f-114"><strong>AppliedBandwidthSource</strong></span><span class="sxs-lookup"><span data-stu-id="e366f-114"><strong>AppliedBandwidthSource</strong></span></span></p></td>
<td><p><span data-ttu-id="e366f-115">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="e366f-115">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e366f-116">Повторя</span><span class="sxs-lookup"><span data-stu-id="e366f-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="e366f-117">Это источник установленного места для пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="e366f-117">This is the source of the bandwidth cap being imposed.</span></span> <span data-ttu-id="e366f-118">Она описывает, откуда поступают ограничения пропускной способности (например, "сервер политики", "превратить сервер" или "модальность").</span><span class="sxs-lookup"><span data-stu-id="e366f-118">It describes where the bandwidth limit is coming from (for example, “Policy Server”, “TURN Server”, or “Modality”).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

