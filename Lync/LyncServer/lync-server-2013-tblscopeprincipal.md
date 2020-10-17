---
title: 'Lync Server 2013: tblScopePrincipal'
description: 'Lync Server 2013: tblScopePrincipal.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblScopePrincipal
ms:assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558639(v=OCS.15)
ms:contentKeyID: 48184009
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 63315f8525e5c2f05fe54a0f9ed9e8a97b9e8bce
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555615"
---
# <a name="tblscopeprincipal-in-lync-server-2013"></a><span data-ttu-id="6fbc4-103">tblScopePrincipal в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6fbc4-103">tblScopePrincipal in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6fbc4-104">_**Последнее изменение темы:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="6fbc4-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="6fbc4-105">tblScopePrincipal содержит области, назначенные узлам.</span><span class="sxs-lookup"><span data-stu-id="6fbc4-105">tblScopePrincipal contains scopes assigned to nodes.</span></span>

### <a name="columns"></a><span data-ttu-id="6fbc4-106">Столбцы</span><span class="sxs-lookup"><span data-stu-id="6fbc4-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6fbc4-107">Столбец</span><span class="sxs-lookup"><span data-stu-id="6fbc4-107">Column</span></span></th>
<th><span data-ttu-id="6fbc4-108">Тип</span><span class="sxs-lookup"><span data-stu-id="6fbc4-108">Type</span></span></th>
<th><span data-ttu-id="6fbc4-109">Описание</span><span class="sxs-lookup"><span data-stu-id="6fbc4-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6fbc4-110">скопенодеид</span><span class="sxs-lookup"><span data-stu-id="6fbc4-110">scopeNodeID</span></span></p></td>
<td><p><span data-ttu-id="6fbc4-111">int, не null</span><span class="sxs-lookup"><span data-stu-id="6fbc4-111">int, not null</span></span></p></td>
<td><p><span data-ttu-id="6fbc4-112">Код узла, к которой применяется область.</span><span class="sxs-lookup"><span data-stu-id="6fbc4-112">Node ID that the scope applies to.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6fbc4-113">скопепринид</span><span class="sxs-lookup"><span data-stu-id="6fbc4-113">scopePrinID</span></span></p></td>
<td><p><span data-ttu-id="6fbc4-114">int, не null</span><span class="sxs-lookup"><span data-stu-id="6fbc4-114">int, not null</span></span></p></td>
<td><p><span data-ttu-id="6fbc4-115">Код участника</span><span class="sxs-lookup"><span data-stu-id="6fbc4-115">Principal ID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6fbc4-116">скопеисдениед</span><span class="sxs-lookup"><span data-stu-id="6fbc4-116">scopeIsDenied</span></span></p></td>
<td><p><span data-ttu-id="6fbc4-117">bit, не null</span><span class="sxs-lookup"><span data-stu-id="6fbc4-117">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="6fbc4-118">Значение true, если тип области — Deny; значение false, если тип области — Allow.</span><span class="sxs-lookup"><span data-stu-id="6fbc4-118">True if type of scope is Deny; False if Allow.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6fbc4-119">скопеупдатедби</span><span class="sxs-lookup"><span data-stu-id="6fbc4-119">scopeUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="6fbc4-120">int, не null</span><span class="sxs-lookup"><span data-stu-id="6fbc4-120">int, not null</span></span></p></td>
<td><p><span data-ttu-id="6fbc4-121">Код участника, который последним обновил эту запись.</span><span class="sxs-lookup"><span data-stu-id="6fbc4-121">ID of the principal that last updated this entry.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="6fbc4-122">Keys</span><span class="sxs-lookup"><span data-stu-id="6fbc4-122">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6fbc4-123">Столбец</span><span class="sxs-lookup"><span data-stu-id="6fbc4-123">Column</span></span></th>
<th><span data-ttu-id="6fbc4-124">Описание</span><span class="sxs-lookup"><span data-stu-id="6fbc4-124">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6fbc4-125">&lt;Скопенодеид, Скопепринид&gt;</span><span class="sxs-lookup"><span data-stu-id="6fbc4-125">&lt;scopeNodeID, scopePrinID&gt;</span></span></p></td>
<td><p><span data-ttu-id="6fbc4-126">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="6fbc4-126">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6fbc4-127">скопенодеид</span><span class="sxs-lookup"><span data-stu-id="6fbc4-127">scopeNodeID</span></span></p></td>
<td><p><span data-ttu-id="6fbc4-128">Внешний ключ с подстановкой в таблице tblNode.nodeID.</span><span class="sxs-lookup"><span data-stu-id="6fbc4-128">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6fbc4-129">скопепринид</span><span class="sxs-lookup"><span data-stu-id="6fbc4-129">scopePrinID</span></span></p></td>
<td><p><span data-ttu-id="6fbc4-130">Внешний ключ с подстановкой в таблице tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="6fbc4-130">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

