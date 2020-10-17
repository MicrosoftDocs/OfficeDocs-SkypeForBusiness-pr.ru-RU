---
title: 'Lync Server 2013: таблица ContentTypes'
description: 'Lync Server 2013: таблица ContentTypes.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ContentTypes table
ms:assetid: e3e38035-457c-4173-bdb9-d53a7420eba2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399007(v=OCS.15)
ms:contentKeyID: 48185723
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 446623ae0ef15d70cd6d85019dfe8eb999f3b2fe
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571685"
---
# <a name="contenttypes-table-in-lync-server-2013"></a><span data-ttu-id="e8b98-103">Таблица ContentTypes в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e8b98-103">ContentTypes table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e8b98-104">_**Последнее изменение темы:** 2010-11-07_</span><span class="sxs-lookup"><span data-stu-id="e8b98-104">_**Topic Last Modified:** 2010-11-07_</span></span>

<span data-ttu-id="e8b98-p101">Таблица ContentTypes является вспомогательной таблице, в которой содержится список типов содержимого, используемых как для одноранговых сеансов, так и для сеансов конференций. Каждая запись в таблице представляет один тип содержимого.</span><span class="sxs-lookup"><span data-stu-id="e8b98-p101">The ContentTypes table is a supporting table that stores a list of the content types used in both peer-to-peer sessions and conference sessions. Each record in the table represents one content type.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e8b98-107">Столбец</span><span class="sxs-lookup"><span data-stu-id="e8b98-107">Column</span></span></th>
<th><span data-ttu-id="e8b98-108">Тип данных</span><span class="sxs-lookup"><span data-stu-id="e8b98-108">Data Type</span></span></th>
<th><span data-ttu-id="e8b98-109">Ключ или индекс</span><span class="sxs-lookup"><span data-stu-id="e8b98-109">Key/Index</span></span></th>
<th><span data-ttu-id="e8b98-110">Сведения</span><span class="sxs-lookup"><span data-stu-id="e8b98-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e8b98-111"><strong>ContentTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="e8b98-111"><strong>ContentTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="e8b98-112">int</span><span class="sxs-lookup"><span data-stu-id="e8b98-112">int</span></span></p></td>
<td><p><span data-ttu-id="e8b98-113">Primary</span><span class="sxs-lookup"><span data-stu-id="e8b98-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="e8b98-114">Уникальный номер, идентифицирующий этот тип содержимого.</span><span class="sxs-lookup"><span data-stu-id="e8b98-114">Unique number identifying the content type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8b98-115"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="e8b98-115"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="e8b98-116">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e8b98-116">nvarchar(256)</span></span></p></td>
<td> </td>
<td><p><span data-ttu-id="e8b98-117">Имя типа содержимого.</span><span class="sxs-lookup"><span data-stu-id="e8b98-117">Content type name.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

