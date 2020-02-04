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
ms.openlocfilehash: baaf336013ec09b17b8e688889fdf27aa29ef644
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764145"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipalmemberdifference-in-lync-server-2013"></a><span data-ttu-id="aea57-102">tblPrincipalMemberDifference в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aea57-102">tblPrincipalMemberDifference in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aea57-103">_**Тема последнего изменения:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="aea57-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="aea57-104">ТблпринЦипалмембердифференце содержит изменения членства в группах (добавленные и удаленные участники), которые еще не были обработаны в последующих шагах синхронизации доменных служб Active Directory.</span><span class="sxs-lookup"><span data-stu-id="aea57-104">tblPrincipalMemberDifference contains group membership changes (both added and removed members) that have not yet been processed by the later Active Directory Domain Services Sync steps.</span></span>

### <a name="columns"></a><span data-ttu-id="aea57-105">Столбцов</span><span class="sxs-lookup"><span data-stu-id="aea57-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="aea57-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="aea57-106">Column</span></span></th>
<th><span data-ttu-id="aea57-107">Тип</span><span class="sxs-lookup"><span data-stu-id="aea57-107">Type</span></span></th>
<th><span data-ttu-id="aea57-108">Описание</span><span class="sxs-lookup"><span data-stu-id="aea57-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="aea57-109">прингуид</span><span class="sxs-lookup"><span data-stu-id="aea57-109">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="aea57-110">GUID, а не NULL</span><span class="sxs-lookup"><span data-stu-id="aea57-110">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="aea57-111">Идентификатор GUID участника измененной группы.</span><span class="sxs-lookup"><span data-stu-id="aea57-111">Principal GUID of the group that changed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aea57-112">мемберадпас</span><span class="sxs-lookup"><span data-stu-id="aea57-112">memberADPath</span></span></p></td>
<td><p><span data-ttu-id="aea57-113">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="aea57-113">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="aea57-114">Отличительное имя участника.</span><span class="sxs-lookup"><span data-stu-id="aea57-114">Distinguished name of the member.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aea57-115">мемберремовед</span><span class="sxs-lookup"><span data-stu-id="aea57-115">memberRemoved</span></span></p></td>
<td><p><span data-ttu-id="aea57-116">bit, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="aea57-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="aea57-117">Значение false, если элемент был добавлен.</span><span class="sxs-lookup"><span data-stu-id="aea57-117">False if the member was added.</span></span> <span data-ttu-id="aea57-118">Значение true, если элемент удален.</span><span class="sxs-lookup"><span data-stu-id="aea57-118">True if the member was removed.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="aea57-119">Ключ</span><span class="sxs-lookup"><span data-stu-id="aea57-119">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="aea57-120">Столбец</span><span class="sxs-lookup"><span data-stu-id="aea57-120">Column</span></span></th>
<th><span data-ttu-id="aea57-121">Описание</span><span class="sxs-lookup"><span data-stu-id="aea57-121">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="aea57-122">&lt;Прингуид, Мемберадпас&gt;</span><span class="sxs-lookup"><span data-stu-id="aea57-122">&lt;prinGuid, memberADPath&gt;</span></span></p></td>
<td><p><span data-ttu-id="aea57-123">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="aea57-123">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

