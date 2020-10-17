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
ms.openlocfilehash: 681b6699e2542a066b9e5b0709fa64f52991b2fd
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523666"
---
# <a name="tblprincipalmemberdifference-in-lync-server-2013"></a><span data-ttu-id="1e41b-102">tblPrincipalMemberDifference в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1e41b-102">tblPrincipalMemberDifference in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1e41b-103">_**Последнее изменение темы:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="1e41b-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="1e41b-104">tblPrincipalMemberDifference содержит изменения членства в группах (добавленные и удаленные элементы), которые еще не были обработаны на последующих этапах синхронизации доменных служб Active Directory.</span><span class="sxs-lookup"><span data-stu-id="1e41b-104">tblPrincipalMemberDifference contains group membership changes (both added and removed members) that have not yet been processed by the later Active Directory Domain Services Sync steps.</span></span>

### <a name="columns"></a><span data-ttu-id="1e41b-105">Столбцы</span><span class="sxs-lookup"><span data-stu-id="1e41b-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1e41b-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="1e41b-106">Column</span></span></th>
<th><span data-ttu-id="1e41b-107">Тип</span><span class="sxs-lookup"><span data-stu-id="1e41b-107">Type</span></span></th>
<th><span data-ttu-id="1e41b-108">Описание</span><span class="sxs-lookup"><span data-stu-id="1e41b-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1e41b-109">прингуид</span><span class="sxs-lookup"><span data-stu-id="1e41b-109">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="1e41b-110">GUID, не NULL</span><span class="sxs-lookup"><span data-stu-id="1e41b-110">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="1e41b-111">GUID субъекта для измененной группы.</span><span class="sxs-lookup"><span data-stu-id="1e41b-111">Principal GUID of the group that changed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1e41b-112">мемберадпас</span><span class="sxs-lookup"><span data-stu-id="1e41b-112">memberADPath</span></span></p></td>
<td><p><span data-ttu-id="1e41b-113">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="1e41b-113">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="1e41b-114">Различающееся имя члена.</span><span class="sxs-lookup"><span data-stu-id="1e41b-114">Distinguished name of the member.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1e41b-115">мемберремовед</span><span class="sxs-lookup"><span data-stu-id="1e41b-115">memberRemoved</span></span></p></td>
<td><p><span data-ttu-id="1e41b-116">bit, не NULL</span><span class="sxs-lookup"><span data-stu-id="1e41b-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="1e41b-p101">False, если член был добавлен. True, если член был удален.</span><span class="sxs-lookup"><span data-stu-id="1e41b-p101">False if the member was added. True if the member was removed.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="1e41b-119">Key</span><span class="sxs-lookup"><span data-stu-id="1e41b-119">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1e41b-120">Столбец</span><span class="sxs-lookup"><span data-stu-id="1e41b-120">Column</span></span></th>
<th><span data-ttu-id="1e41b-121">Описание</span><span class="sxs-lookup"><span data-stu-id="1e41b-121">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1e41b-122">&lt;Прингуид, Мемберадпас&gt;</span><span class="sxs-lookup"><span data-stu-id="1e41b-122">&lt;prinGuid, memberADPath&gt;</span></span></p></td>
<td><p><span data-ttu-id="1e41b-123">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="1e41b-123">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

