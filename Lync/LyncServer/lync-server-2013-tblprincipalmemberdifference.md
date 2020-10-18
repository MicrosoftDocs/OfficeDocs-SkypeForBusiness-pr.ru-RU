---
title: 'Lync Server 2013: tblPrincipalMemberDifference'
description: 'Lync Server 2013: tblPrincipalMemberDifference.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipalMemberDifference
ms:assetid: 0b94f555-6888-4fe0-a048-4660a2513276
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558612(v=OCS.15)
ms:contentKeyID: 48183379
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce7c770a6fed02dc27d2493816fae58943d391a6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573225"
---
# <a name="tblprincipalmemberdifference-in-lync-server-2013"></a><span data-ttu-id="2efbd-103">tblPrincipalMemberDifference в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2efbd-103">tblPrincipalMemberDifference in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2efbd-104">_**Последнее изменение темы:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="2efbd-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="2efbd-105">tblPrincipalMemberDifference содержит изменения членства в группах (добавленные и удаленные элементы), которые еще не были обработаны на последующих этапах синхронизации доменных служб Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2efbd-105">tblPrincipalMemberDifference contains group membership changes (both added and removed members) that have not yet been processed by the later Active Directory Domain Services Sync steps.</span></span>

### <a name="columns"></a><span data-ttu-id="2efbd-106">Столбцы</span><span class="sxs-lookup"><span data-stu-id="2efbd-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2efbd-107">Столбец</span><span class="sxs-lookup"><span data-stu-id="2efbd-107">Column</span></span></th>
<th><span data-ttu-id="2efbd-108">Тип</span><span class="sxs-lookup"><span data-stu-id="2efbd-108">Type</span></span></th>
<th><span data-ttu-id="2efbd-109">Описание</span><span class="sxs-lookup"><span data-stu-id="2efbd-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2efbd-110">прингуид</span><span class="sxs-lookup"><span data-stu-id="2efbd-110">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="2efbd-111">GUID, не NULL</span><span class="sxs-lookup"><span data-stu-id="2efbd-111">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="2efbd-112">GUID субъекта для измененной группы.</span><span class="sxs-lookup"><span data-stu-id="2efbd-112">Principal GUID of the group that changed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2efbd-113">мемберадпас</span><span class="sxs-lookup"><span data-stu-id="2efbd-113">memberADPath</span></span></p></td>
<td><p><span data-ttu-id="2efbd-114">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="2efbd-114">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="2efbd-115">Различающееся имя члена.</span><span class="sxs-lookup"><span data-stu-id="2efbd-115">Distinguished name of the member.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2efbd-116">мемберремовед</span><span class="sxs-lookup"><span data-stu-id="2efbd-116">memberRemoved</span></span></p></td>
<td><p><span data-ttu-id="2efbd-117">bit, не NULL</span><span class="sxs-lookup"><span data-stu-id="2efbd-117">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="2efbd-p101">False, если член был добавлен. True, если член был удален.</span><span class="sxs-lookup"><span data-stu-id="2efbd-p101">False if the member was added. True if the member was removed.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="2efbd-120">Key</span><span class="sxs-lookup"><span data-stu-id="2efbd-120">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2efbd-121">Столбец</span><span class="sxs-lookup"><span data-stu-id="2efbd-121">Column</span></span></th>
<th><span data-ttu-id="2efbd-122">Описание</span><span class="sxs-lookup"><span data-stu-id="2efbd-122">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2efbd-123">&lt;Прингуид, Мемберадпас&gt;</span><span class="sxs-lookup"><span data-stu-id="2efbd-123">&lt;prinGuid, memberADPath&gt;</span></span></p></td>
<td><p><span data-ttu-id="2efbd-124">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="2efbd-124">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

