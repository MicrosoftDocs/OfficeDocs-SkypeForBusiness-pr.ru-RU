---
title: 'Lync Server 2013: tblPrincipalRole'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblPrincipalRole
ms:assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615039(v=OCS.15)
ms:contentKeyID: 48185597
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 560f454531060a8458c8c920a1e4c5921867f3e4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849551"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipalrole-in-lync-server-2013"></a><span data-ttu-id="e7938-102">tblPrincipalRole в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e7938-102">tblPrincipalRole in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e7938-103">_**Тема последнего изменения:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="e7938-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="e7938-104">ТблпринЦипалроле включает явные роли, назначенные узлам.</span><span class="sxs-lookup"><span data-stu-id="e7938-104">tblPrincipalRole contains explicit roles assigned to nodes.</span></span>

### <a name="columns"></a><span data-ttu-id="e7938-105">Столбцов</span><span class="sxs-lookup"><span data-stu-id="e7938-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e7938-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="e7938-106">Column</span></span></th>
<th><span data-ttu-id="e7938-107">Тип</span><span class="sxs-lookup"><span data-stu-id="e7938-107">Type</span></span></th>
<th><span data-ttu-id="e7938-108">Описание</span><span class="sxs-lookup"><span data-stu-id="e7938-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e7938-109">Принроленодеид</span><span class="sxs-lookup"><span data-stu-id="e7938-109">prinRoleNodeID</span></span></p></td>
<td><p><span data-ttu-id="e7938-110">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="e7938-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="e7938-111">Идентификатор узла, к которому относится роль.</span><span class="sxs-lookup"><span data-stu-id="e7938-111">Node ID that the role applies to.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7938-112">Принролепринид</span><span class="sxs-lookup"><span data-stu-id="e7938-112">prinRolePrinID</span></span></p></td>
<td><p><span data-ttu-id="e7938-113">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="e7938-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="e7938-114">Идентификатор участника.</span><span class="sxs-lookup"><span data-stu-id="e7938-114">Principal ID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7938-115">Принролетипеид</span><span class="sxs-lookup"><span data-stu-id="e7938-115">prinRoleTypeID</span></span></p></td>
<td><p><span data-ttu-id="e7938-116">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="e7938-116">int, not null</span></span></p></td>
<td><p><span data-ttu-id="e7938-117">Идентификатор типа роли (из Тблролетипе).</span><span class="sxs-lookup"><span data-stu-id="e7938-117">Role type ID (from tblRoleType).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7938-118">Принролеупдатедби</span><span class="sxs-lookup"><span data-stu-id="e7938-118">prinRoleUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="e7938-119">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="e7938-119">int, not null</span></span></p></td>
<td><p><span data-ttu-id="e7938-120">Идентификатор участника, который последним обновил эту запись.</span><span class="sxs-lookup"><span data-stu-id="e7938-120">ID of the principal that last updated this entry.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="e7938-121">Параметры</span><span class="sxs-lookup"><span data-stu-id="e7938-121">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e7938-122">Столбец</span><span class="sxs-lookup"><span data-stu-id="e7938-122">Column</span></span></th>
<th><span data-ttu-id="e7938-123">Описание</span><span class="sxs-lookup"><span data-stu-id="e7938-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e7938-124">&lt;Принроленодеид, Принролепринид, Принролетипеид&gt;</span><span class="sxs-lookup"><span data-stu-id="e7938-124">&lt;prinRoleNodeID, prinRolePrinID, prinRoleTypeID&gt;</span></span></p></td>
<td><p><span data-ttu-id="e7938-125">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="e7938-125">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7938-126">Принроленодеид</span><span class="sxs-lookup"><span data-stu-id="e7938-126">prinRoleNodeID</span></span></p></td>
<td><p><span data-ttu-id="e7938-127">Внешний ключ с подстановкой в таблице Тблноде. Нодеид.</span><span class="sxs-lookup"><span data-stu-id="e7938-127">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7938-128">Принролепринид</span><span class="sxs-lookup"><span data-stu-id="e7938-128">prinRolePrinID</span></span></p></td>
<td><p><span data-ttu-id="e7938-129">Внешний ключ с подстановкой в таблице ТблпринЦипал. Принид.</span><span class="sxs-lookup"><span data-stu-id="e7938-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7938-130">Принролетипеид</span><span class="sxs-lookup"><span data-stu-id="e7938-130">prinRoleTypeID</span></span></p></td>
<td><p><span data-ttu-id="e7938-131">Внешний ключ с подстановкой в таблице Тблролетипе. Ртипеид.</span><span class="sxs-lookup"><span data-stu-id="e7938-131">Foreign key with lookup in tblRoleType.rtypeID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

