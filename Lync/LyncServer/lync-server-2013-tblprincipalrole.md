---
title: 'Lync Server 2013: tblPrincipalRole'
description: 'Lync Server 2013: tblPrincipalRole.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipalRole
ms:assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615039(v=OCS.15)
ms:contentKeyID: 48185597
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f58ffda3136c254ee77f14d33dcb42af5d172c4a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573635"
---
# <a name="tblprincipalrole-in-lync-server-2013"></a><span data-ttu-id="a301c-103">tblPrincipalRole в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a301c-103">tblPrincipalRole in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a301c-104">_**Последнее изменение темы:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="a301c-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="a301c-105">tblPrincipalRole содержит явные роли, назначенные узлам.</span><span class="sxs-lookup"><span data-stu-id="a301c-105">tblPrincipalRole contains explicit roles assigned to nodes.</span></span>

### <a name="columns"></a><span data-ttu-id="a301c-106">Столбцы</span><span class="sxs-lookup"><span data-stu-id="a301c-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a301c-107">Столбец</span><span class="sxs-lookup"><span data-stu-id="a301c-107">Column</span></span></th>
<th><span data-ttu-id="a301c-108">Тип</span><span class="sxs-lookup"><span data-stu-id="a301c-108">Type</span></span></th>
<th><span data-ttu-id="a301c-109">Описание</span><span class="sxs-lookup"><span data-stu-id="a301c-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a301c-110">принроленодеид</span><span class="sxs-lookup"><span data-stu-id="a301c-110">prinRoleNodeID</span></span></p></td>
<td><p><span data-ttu-id="a301c-111">int, not null</span><span class="sxs-lookup"><span data-stu-id="a301c-111">int, not null</span></span></p></td>
<td><p><span data-ttu-id="a301c-112">ИД узла, к которому применяется роль.</span><span class="sxs-lookup"><span data-stu-id="a301c-112">Node ID that the role applies to.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a301c-113">принролепринид</span><span class="sxs-lookup"><span data-stu-id="a301c-113">prinRolePrinID</span></span></p></td>
<td><p><span data-ttu-id="a301c-114">int, not null</span><span class="sxs-lookup"><span data-stu-id="a301c-114">int, not null</span></span></p></td>
<td><p><span data-ttu-id="a301c-115">ИД субъекта.</span><span class="sxs-lookup"><span data-stu-id="a301c-115">Principal ID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a301c-116">принролетипеид</span><span class="sxs-lookup"><span data-stu-id="a301c-116">prinRoleTypeID</span></span></p></td>
<td><p><span data-ttu-id="a301c-117">int, not null</span><span class="sxs-lookup"><span data-stu-id="a301c-117">int, not null</span></span></p></td>
<td><p><span data-ttu-id="a301c-118">ИД типа роли (из tblRoleType).</span><span class="sxs-lookup"><span data-stu-id="a301c-118">Role type ID (from tblRoleType).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a301c-119">принролеупдатедби</span><span class="sxs-lookup"><span data-stu-id="a301c-119">prinRoleUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="a301c-120">int, not null</span><span class="sxs-lookup"><span data-stu-id="a301c-120">int, not null</span></span></p></td>
<td><p><span data-ttu-id="a301c-121">Код участника, который последним обновил эту запись.</span><span class="sxs-lookup"><span data-stu-id="a301c-121">ID of the principal that last updated this entry.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="a301c-122">Keys</span><span class="sxs-lookup"><span data-stu-id="a301c-122">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a301c-123">Столбец</span><span class="sxs-lookup"><span data-stu-id="a301c-123">Column</span></span></th>
<th><span data-ttu-id="a301c-124">Описание</span><span class="sxs-lookup"><span data-stu-id="a301c-124">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a301c-125">&lt;Принроленодеид, Принролепринид, Принролетипеид&gt;</span><span class="sxs-lookup"><span data-stu-id="a301c-125">&lt;prinRoleNodeID, prinRolePrinID, prinRoleTypeID&gt;</span></span></p></td>
<td><p><span data-ttu-id="a301c-126">Основной ключ.</span><span class="sxs-lookup"><span data-stu-id="a301c-126">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a301c-127">принроленодеид</span><span class="sxs-lookup"><span data-stu-id="a301c-127">prinRoleNodeID</span></span></p></td>
<td><p><span data-ttu-id="a301c-128">Внешний ключ с поиском в таблице tblNode.nodeID.</span><span class="sxs-lookup"><span data-stu-id="a301c-128">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a301c-129">принролепринид</span><span class="sxs-lookup"><span data-stu-id="a301c-129">prinRolePrinID</span></span></p></td>
<td><p><span data-ttu-id="a301c-130">Внешний ключ с поиском в таблице tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="a301c-130">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a301c-131">принролетипеид</span><span class="sxs-lookup"><span data-stu-id="a301c-131">prinRoleTypeID</span></span></p></td>
<td><p><span data-ttu-id="a301c-132">Внешний ключ с поиском в таблице tblRoleType.rtypeID.</span><span class="sxs-lookup"><span data-stu-id="a301c-132">Foreign key with lookup in tblRoleType.rtypeID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

