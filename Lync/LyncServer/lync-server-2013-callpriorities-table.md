---
title: 'Lync Server 2013: таблица таблица callpriorities'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: CallPriorities table
ms:assetid: 043b63ae-2d64-4f38-a0df-18aa08d6caf5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398093(v=OCS.15)
ms:contentKeyID: 48183275
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2be19538e065a1f9a25dd58da93b2752a27333e9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044231"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="callpriorities-table-in-lync-server-2013"></a><span data-ttu-id="cb79f-102">Таблица Таблица callpriorities в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cb79f-102">CallPriorities table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cb79f-103">_**Последнее изменение темы:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="cb79f-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="cb79f-104">Таблица CallPriorities является статической таблицей, в которой хранится список возможных приоритетов вызовов, таких как "emergency" (экстренный), "urgent" (срочный) или "normal" (обычный).</span><span class="sxs-lookup"><span data-stu-id="cb79f-104">The CallPriorities table is a static table that stores the list of possible call priorities, such as ‘emergency’, ‘urgent’, or ‘normal’.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cb79f-105">Столбец</span><span class="sxs-lookup"><span data-stu-id="cb79f-105">Column</span></span></th>
<th><span data-ttu-id="cb79f-106">Тип данных</span><span class="sxs-lookup"><span data-stu-id="cb79f-106">Data Type</span></span></th>
<th><span data-ttu-id="cb79f-107">Ключ или индекс</span><span class="sxs-lookup"><span data-stu-id="cb79f-107">Key/Index</span></span></th>
<th><span data-ttu-id="cb79f-108">Сведения</span><span class="sxs-lookup"><span data-stu-id="cb79f-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cb79f-109"><strong>приоритид</strong></span><span class="sxs-lookup"><span data-stu-id="cb79f-109"><strong>PriorityId</strong></span></span></p></td>
<td><p><span data-ttu-id="cb79f-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="cb79f-110">tinyint</span></span></p></td>
<td><p><span data-ttu-id="cb79f-111">Primary</span><span class="sxs-lookup"><span data-stu-id="cb79f-111">Primary</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cb79f-112"><strong>Priority</strong></span><span class="sxs-lookup"><span data-stu-id="cb79f-112"><strong>Priority</strong></span></span></p></td>
<td><p><span data-ttu-id="cb79f-113">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="cb79f-113">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cb79f-114">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="cb79f-114">Allowed values:</span></span></p>
<ul>
<li><p><span data-ttu-id="cb79f-115">0 — неизвестный</span><span class="sxs-lookup"><span data-stu-id="cb79f-115">0 - Unknown</span></span></p></li>
<li><p><span data-ttu-id="cb79f-116">1 — не срочный</span><span class="sxs-lookup"><span data-stu-id="cb79f-116">1 – Non-Urgent</span></span></p></li>
<li><p><span data-ttu-id="cb79f-117">2 — обычный</span><span class="sxs-lookup"><span data-stu-id="cb79f-117">2 - Normal</span></span></p></li>
<li><p><span data-ttu-id="cb79f-118">3 — срочный</span><span class="sxs-lookup"><span data-stu-id="cb79f-118">3 - Urgent</span></span></p></li>
<li><p><span data-ttu-id="cb79f-119">4 — экстренный</span><span class="sxs-lookup"><span data-stu-id="cb79f-119">4 - Emergency</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

