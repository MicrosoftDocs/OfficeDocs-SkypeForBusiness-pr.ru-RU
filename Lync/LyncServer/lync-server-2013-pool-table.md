---
title: 'Lync Server 2013: таблица pool'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Pool table
ms:assetid: 92ded8fd-d0ad-4f8a-9e6f-2e8a690fda3a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398746(v=OCS.15)
ms:contentKeyID: 48184803
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 30d849fad5f607d29395fb93355c50e16a9cbb4c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049511"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="pool-table-in-lync-server-2013"></a><span data-ttu-id="72be5-102">Таблица pool в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="72be5-102">Pool table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="72be5-103">_**Последнее изменение темы:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="72be5-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="72be5-p101">Во вспомогательной таблице Pool хранятся сведения о различных интерфейсных пулах. Каждая запись в таблице представляет один пул.</span><span class="sxs-lookup"><span data-stu-id="72be5-p101">The Pool table is a supporting table that stores information about the various Front End pools. Each record in the table represents one pool.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="72be5-106"><strong>Column</strong></span><span class="sxs-lookup"><span data-stu-id="72be5-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="72be5-107"><strong>Тип данных</strong></span><span class="sxs-lookup"><span data-stu-id="72be5-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="72be5-108"><strong>Ключ или индекс</strong></span><span class="sxs-lookup"><span data-stu-id="72be5-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="72be5-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="72be5-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="72be5-110"><strong>пулкэй</strong></span><span class="sxs-lookup"><span data-stu-id="72be5-110"><strong>PoolKey</strong></span></span></p></td>
<td><p><span data-ttu-id="72be5-111">int</span><span class="sxs-lookup"><span data-stu-id="72be5-111">int</span></span></p></td>
<td><p><span data-ttu-id="72be5-112">Primary</span><span class="sxs-lookup"><span data-stu-id="72be5-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="72be5-113">Уникальный номер, определяющий пул.</span><span class="sxs-lookup"><span data-stu-id="72be5-113">Unique number identifying this pool.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="72be5-114"><strong>пулнаме</strong></span><span class="sxs-lookup"><span data-stu-id="72be5-114"><strong>PoolName</strong></span></span></p></td>
<td><p><span data-ttu-id="72be5-115">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="72be5-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="72be5-116">Уникальный </span><span class="sxs-lookup"><span data-stu-id="72be5-116">Unique </span></span></p></td>
<td><p><span data-ttu-id="72be5-117">Полное доменное имя пула.</span><span class="sxs-lookup"><span data-stu-id="72be5-117">Pool FQDN.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

