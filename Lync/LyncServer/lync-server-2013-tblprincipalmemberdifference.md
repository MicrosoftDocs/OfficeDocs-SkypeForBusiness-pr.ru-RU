---
title: 'Lync Server 2013: tblPrincipalMemberDifference'
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
ms.openlocfilehash: cfdd2ff1ca0c288738005c8d0740770e7c43319f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142015"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblprincipalmemberdifference-in-lync-server-2013"></a><span data-ttu-id="237e6-102">tblPrincipalMemberDifference в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="237e6-102">tblPrincipalMemberDifference in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="237e6-103">_**Последнее изменение темы:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="237e6-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="237e6-104">tblPrincipalMemberDifference содержит изменения членства в группах (добавленные и удаленные элементы), которые еще не были обработаны на последующих этапах синхронизации доменных служб Active Directory.</span><span class="sxs-lookup"><span data-stu-id="237e6-104">tblPrincipalMemberDifference contains group membership changes (both added and removed members) that have not yet been processed by the later Active Directory Domain Services Sync steps.</span></span>

### <a name="columns"></a><span data-ttu-id="237e6-105">Columns</span><span class="sxs-lookup"><span data-stu-id="237e6-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="237e6-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="237e6-106">Column</span></span></th>
<th><span data-ttu-id="237e6-107">Тип</span><span class="sxs-lookup"><span data-stu-id="237e6-107">Type</span></span></th>
<th><span data-ttu-id="237e6-108">Описание</span><span class="sxs-lookup"><span data-stu-id="237e6-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="237e6-109">прингуид</span><span class="sxs-lookup"><span data-stu-id="237e6-109">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="237e6-110">GUID, не NULL</span><span class="sxs-lookup"><span data-stu-id="237e6-110">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="237e6-111">GUID субъекта для измененной группы.</span><span class="sxs-lookup"><span data-stu-id="237e6-111">Principal GUID of the group that changed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="237e6-112">мемберадпас</span><span class="sxs-lookup"><span data-stu-id="237e6-112">memberADPath</span></span></p></td>
<td><p><span data-ttu-id="237e6-113">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="237e6-113">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="237e6-114">Различающееся имя члена.</span><span class="sxs-lookup"><span data-stu-id="237e6-114">Distinguished name of the member.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="237e6-115">мемберремовед</span><span class="sxs-lookup"><span data-stu-id="237e6-115">memberRemoved</span></span></p></td>
<td><p><span data-ttu-id="237e6-116">bit, не NULL</span><span class="sxs-lookup"><span data-stu-id="237e6-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="237e6-p101">False, если член был добавлен. True, если член был удален.</span><span class="sxs-lookup"><span data-stu-id="237e6-p101">False if the member was added. True if the member was removed.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="237e6-119">Key</span><span class="sxs-lookup"><span data-stu-id="237e6-119">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="237e6-120">Столбец</span><span class="sxs-lookup"><span data-stu-id="237e6-120">Column</span></span></th>
<th><span data-ttu-id="237e6-121">Описание</span><span class="sxs-lookup"><span data-stu-id="237e6-121">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="237e6-122">&lt;Прингуид, Мемберадпас&gt;</span><span class="sxs-lookup"><span data-stu-id="237e6-122">&lt;prinGuid, memberADPath&gt;</span></span></p></td>
<td><p><span data-ttu-id="237e6-123">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="237e6-123">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

