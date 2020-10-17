---
title: 'Lync Server 2013: таблица Roles'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Roles table
ms:assetid: e8eb8a10-26b5-488b-bc8c-f9ef93f98bdb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399043(v=OCS.15)
ms:contentKeyID: 48185893
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d779e5baf1e96848f7b3957a2aeae1b823d1cf30
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511276"
---
# <a name="roles-table-in-lync-server-2013"></a><span data-ttu-id="30c92-102">Таблица Roles в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="30c92-102">Roles table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="30c92-103">_**Последнее изменение темы:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="30c92-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="30c92-104">The Roles table is a static table that stores the list of possible conference roles, such as attendee and presenter.</span><span class="sxs-lookup"><span data-stu-id="30c92-104">The Roles table is a static table that stores the list of possible conference roles, such as attendee and presenter.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="30c92-105">Столбец</span><span class="sxs-lookup"><span data-stu-id="30c92-105">Column</span></span></th>
<th><span data-ttu-id="30c92-106">Тип данных</span><span class="sxs-lookup"><span data-stu-id="30c92-106">Data Type</span></span></th>
<th><span data-ttu-id="30c92-107">Ключ или индекс</span><span class="sxs-lookup"><span data-stu-id="30c92-107">Key/Index</span></span></th>
<th><span data-ttu-id="30c92-108">Сведения</span><span class="sxs-lookup"><span data-stu-id="30c92-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="30c92-109"><strong>RoleId</strong></span><span class="sxs-lookup"><span data-stu-id="30c92-109"><strong>RoleId</strong></span></span></p></td>
<td><p><span data-ttu-id="30c92-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="30c92-110">tinyint</span></span></p></td>
<td><p><span data-ttu-id="30c92-111">Primary</span><span class="sxs-lookup"><span data-stu-id="30c92-111">Primary</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="30c92-112"><strong>Role</strong></span><span class="sxs-lookup"><span data-stu-id="30c92-112"><strong>Role</strong></span></span></p></td>
<td><p><span data-ttu-id="30c92-113">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="30c92-113">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="30c92-114">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="30c92-114">Allowed values:</span></span></p>
<ul>
<li><p><span data-ttu-id="30c92-115">0 — неизвестно</span><span class="sxs-lookup"><span data-stu-id="30c92-115">0 - Unknown</span></span></p></li>
<li><p><span data-ttu-id="30c92-116">1 — выступающий</span><span class="sxs-lookup"><span data-stu-id="30c92-116">1 - Presenter</span></span></p></li>
<li><p><span data-ttu-id="30c92-117">2 — участник</span><span class="sxs-lookup"><span data-stu-id="30c92-117">2 - Attendee</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

