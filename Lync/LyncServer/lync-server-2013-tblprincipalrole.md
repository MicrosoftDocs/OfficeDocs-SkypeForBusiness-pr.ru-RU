---
title: 'Lync Server 2013: tblPrincipalRole'
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
ms.openlocfilehash: 685e8ae3e767e3dc237da1698fd593a9c56021c8
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195172"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblprincipalrole-in-lync-server-2013"></a><span data-ttu-id="b4797-102">tblPrincipalRole в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b4797-102">tblPrincipalRole in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b4797-103">_**Последнее изменение темы:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="b4797-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="b4797-104">tblPrincipalRole содержит явные роли, назначенные узлам.</span><span class="sxs-lookup"><span data-stu-id="b4797-104">tblPrincipalRole contains explicit roles assigned to nodes.</span></span>

### <a name="columns"></a><span data-ttu-id="b4797-105">Columns</span><span class="sxs-lookup"><span data-stu-id="b4797-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b4797-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="b4797-106">Column</span></span></th>
<th><span data-ttu-id="b4797-107">Тип</span><span class="sxs-lookup"><span data-stu-id="b4797-107">Type</span></span></th>
<th><span data-ttu-id="b4797-108">Описание</span><span class="sxs-lookup"><span data-stu-id="b4797-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b4797-109">принроленодеид</span><span class="sxs-lookup"><span data-stu-id="b4797-109">prinRoleNodeID</span></span></p></td>
<td><p><span data-ttu-id="b4797-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="b4797-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="b4797-111">ИД узла, к которому применяется роль.</span><span class="sxs-lookup"><span data-stu-id="b4797-111">Node ID that the role applies to.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b4797-112">принролепринид</span><span class="sxs-lookup"><span data-stu-id="b4797-112">prinRolePrinID</span></span></p></td>
<td><p><span data-ttu-id="b4797-113">int, не равно null</span><span class="sxs-lookup"><span data-stu-id="b4797-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="b4797-114">ИД субъекта.</span><span class="sxs-lookup"><span data-stu-id="b4797-114">Principal ID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b4797-115">принролетипеид</span><span class="sxs-lookup"><span data-stu-id="b4797-115">prinRoleTypeID</span></span></p></td>
<td><p><span data-ttu-id="b4797-116">int, not null</span><span class="sxs-lookup"><span data-stu-id="b4797-116">int, not null</span></span></p></td>
<td><p><span data-ttu-id="b4797-117">ИД типа роли (из tblRoleType).</span><span class="sxs-lookup"><span data-stu-id="b4797-117">Role type ID (from tblRoleType).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b4797-118">принролеупдатедби</span><span class="sxs-lookup"><span data-stu-id="b4797-118">prinRoleUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="b4797-119">int, not null</span><span class="sxs-lookup"><span data-stu-id="b4797-119">int, not null</span></span></p></td>
<td><p><span data-ttu-id="b4797-120">Код участника, который последним обновил эту запись.</span><span class="sxs-lookup"><span data-stu-id="b4797-120">ID of the principal that last updated this entry.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="b4797-121">Keys</span><span class="sxs-lookup"><span data-stu-id="b4797-121">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b4797-122">Столбец</span><span class="sxs-lookup"><span data-stu-id="b4797-122">Column</span></span></th>
<th><span data-ttu-id="b4797-123">Описание</span><span class="sxs-lookup"><span data-stu-id="b4797-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b4797-124">&lt;Принроленодеид, Принролепринид, Принролетипеид&gt;</span><span class="sxs-lookup"><span data-stu-id="b4797-124">&lt;prinRoleNodeID, prinRolePrinID, prinRoleTypeID&gt;</span></span></p></td>
<td><p><span data-ttu-id="b4797-125">Основной ключ.</span><span class="sxs-lookup"><span data-stu-id="b4797-125">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b4797-126">принроленодеид</span><span class="sxs-lookup"><span data-stu-id="b4797-126">prinRoleNodeID</span></span></p></td>
<td><p><span data-ttu-id="b4797-127">Внешний ключ с поиском в таблице tblNode.nodeID.</span><span class="sxs-lookup"><span data-stu-id="b4797-127">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b4797-128">принролепринид</span><span class="sxs-lookup"><span data-stu-id="b4797-128">prinRolePrinID</span></span></p></td>
<td><p><span data-ttu-id="b4797-129">Внешний ключ с поиском в таблице tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="b4797-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b4797-130">принролетипеид</span><span class="sxs-lookup"><span data-stu-id="b4797-130">prinRoleTypeID</span></span></p></td>
<td><p><span data-ttu-id="b4797-131">Внешний ключ с поиском в таблице tblRoleType.rtypeID.</span><span class="sxs-lookup"><span data-stu-id="b4797-131">Foreign key with lookup in tblRoleType.rtypeID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

