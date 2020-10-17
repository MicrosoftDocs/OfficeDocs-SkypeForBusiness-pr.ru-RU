---
title: 'Lync Server 2013: таблица таблица usersite'
description: 'Lync Server 2013: таблица таблица usersite.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: UserSite table
ms:assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398256(v=OCS.15)
ms:contentKeyID: 48183552
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4e0fb3149b9378bbfd3f14da8176eed226e4f57f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548625"
---
# <a name="usersite-table-in-lync-server-2013"></a><span data-ttu-id="b3bf3-103">Таблица Таблица usersite в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b3bf3-103">UserSite table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b3bf3-104">_**Последнее изменение темы:** 2010-11-09_</span><span class="sxs-lookup"><span data-stu-id="b3bf3-104">_**Topic Last Modified:** 2010-11-09_</span></span>

<span data-ttu-id="b3bf3-105">Таблица Таблица usersite является вспомогательной таблицей.</span><span class="sxs-lookup"><span data-stu-id="b3bf3-105">The UserSite table is a supporting table.</span></span> <span data-ttu-id="b3bf3-106">Каждая запись представляет один сайт пользователя, определенный в параметрах конфигурации сети.</span><span class="sxs-lookup"><span data-stu-id="b3bf3-106">Each record represents one user site defined in network configuration setting.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b3bf3-107"><strong>Column</strong></span><span class="sxs-lookup"><span data-stu-id="b3bf3-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="b3bf3-108"><strong>Тип данных</strong></span><span class="sxs-lookup"><span data-stu-id="b3bf3-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="b3bf3-109"><strong>Ключ или индекс</strong></span><span class="sxs-lookup"><span data-stu-id="b3bf3-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="b3bf3-110"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="b3bf3-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b3bf3-111"><strong>усерситекэй</strong></span><span class="sxs-lookup"><span data-stu-id="b3bf3-111"><strong>UserSiteKey</strong></span></span></p></td>
<td><p><span data-ttu-id="b3bf3-112">int</span><span class="sxs-lookup"><span data-stu-id="b3bf3-112">int</span></span></p></td>
<td><p><span data-ttu-id="b3bf3-113">Primary</span><span class="sxs-lookup"><span data-stu-id="b3bf3-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="b3bf3-114">Уникальный номер, идентифицирующий сайт пользователя.</span><span class="sxs-lookup"><span data-stu-id="b3bf3-114">Unique number identifying the user site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3bf3-115"><strong>усерситенаме</strong></span><span class="sxs-lookup"><span data-stu-id="b3bf3-115"><strong>UserSiteName</strong></span></span></p></td>
<td><p><span data-ttu-id="b3bf3-116">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="b3bf3-116">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="b3bf3-117">Уникальные</span><span class="sxs-lookup"><span data-stu-id="b3bf3-117">Unique</span></span></p></td>
<td><p><span data-ttu-id="b3bf3-118">Имя сайта пользователя.</span><span class="sxs-lookup"><span data-stu-id="b3bf3-118">User site’s name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3bf3-119"><strong>регионкэй</strong></span><span class="sxs-lookup"><span data-stu-id="b3bf3-119"><strong>RegionKey</strong></span></span></p></td>
<td><p><span data-ttu-id="b3bf3-120">int</span><span class="sxs-lookup"><span data-stu-id="b3bf3-120">int</span></span></p></td>
<td><p><span data-ttu-id="b3bf3-121">Правительства</span><span class="sxs-lookup"><span data-stu-id="b3bf3-121">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b3bf3-122">Ссылка из <a href="lync-server-2013-region-table.md">таблицы Region в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="b3bf3-122">Referenced from <a href="lync-server-2013-region-table.md">Region table in Lync Server 2013</a>.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

