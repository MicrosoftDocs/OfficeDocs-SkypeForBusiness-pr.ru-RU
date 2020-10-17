---
title: 'Lync Server 2013: tblPrincipalInvites'
description: 'Lync Server 2013: tblPrincipalInvites.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipalInvites
ms:assetid: 548ec156-4d1a-469d-a804-62cff226e5c2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558650(v=OCS.15)
ms:contentKeyID: 48184141
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d30d741864ed2a3cfbec8329215be33c21b3b262
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564675"
---
# <a name="tblprincipalinvites-in-lync-server-2013"></a><span data-ttu-id="d4ac1-103">tblPrincipalInvites в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d4ac1-103">tblPrincipalInvites in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d4ac1-104">_**Последнее изменение темы:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="d4ac1-104">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="d4ac1-105">tblPrincipalInvites содержит приглашения для всех подготовленных пользователей для всех узлов с включенным автоматическим приглашением.</span><span class="sxs-lookup"><span data-stu-id="d4ac1-105">tblPrincipalInvites contains invitations for all provisioned users for all nodes with auto-invite on.</span></span>

### <a name="columns"></a><span data-ttu-id="d4ac1-106">Столбцы</span><span class="sxs-lookup"><span data-stu-id="d4ac1-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d4ac1-107">Столбец</span><span class="sxs-lookup"><span data-stu-id="d4ac1-107">Column</span></span></th>
<th><span data-ttu-id="d4ac1-108">Тип</span><span class="sxs-lookup"><span data-stu-id="d4ac1-108">Type</span></span></th>
<th><span data-ttu-id="d4ac1-109">Описание</span><span class="sxs-lookup"><span data-stu-id="d4ac1-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d4ac1-110">prinID</span><span class="sxs-lookup"><span data-stu-id="d4ac1-110">prinID</span></span></p></td>
<td><p><span data-ttu-id="d4ac1-111">int, not null</span><span class="sxs-lookup"><span data-stu-id="d4ac1-111">int, not null</span></span></p></td>
<td><p><span data-ttu-id="d4ac1-112">Код участника</span><span class="sxs-lookup"><span data-stu-id="d4ac1-112">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4ac1-113">инвид</span><span class="sxs-lookup"><span data-stu-id="d4ac1-113">invID</span></span></p></td>
<td><p><span data-ttu-id="d4ac1-114">int, не null</span><span class="sxs-lookup"><span data-stu-id="d4ac1-114">int, not null</span></span></p></td>
<td><p><span data-ttu-id="d4ac1-115">Уникальный порядковый номер (на код участника), созданный для таблицы tblLastInviteId.</span><span class="sxs-lookup"><span data-stu-id="d4ac1-115">Unique sequential number (per principal ID) generated from tblLastInviteId table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4ac1-116">nodeID</span><span class="sxs-lookup"><span data-stu-id="d4ac1-116">nodeID</span></span></p></td>
<td><p><span data-ttu-id="d4ac1-117">int, не null</span><span class="sxs-lookup"><span data-stu-id="d4ac1-117">int, not null</span></span></p></td>
<td><p><span data-ttu-id="d4ac1-118">Код узла (только комната чата).</span><span class="sxs-lookup"><span data-stu-id="d4ac1-118">Node ID (chat room only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4ac1-119">креатедон</span><span class="sxs-lookup"><span data-stu-id="d4ac1-119">createdOn</span></span></p></td>
<td><p><span data-ttu-id="d4ac1-120">datetime, не null</span><span class="sxs-lookup"><span data-stu-id="d4ac1-120">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="d4ac1-121">Время создания.</span><span class="sxs-lookup"><span data-stu-id="d4ac1-121">Time of creation.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="d4ac1-122">Keys</span><span class="sxs-lookup"><span data-stu-id="d4ac1-122">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d4ac1-123">Столбец</span><span class="sxs-lookup"><span data-stu-id="d4ac1-123">Column</span></span></th>
<th><span data-ttu-id="d4ac1-124">Описание</span><span class="sxs-lookup"><span data-stu-id="d4ac1-124">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d4ac1-125">&lt;prinID, nodeID&gt;</span><span class="sxs-lookup"><span data-stu-id="d4ac1-125">&lt;prinID, nodeID&gt;</span></span></p></td>
<td><p><span data-ttu-id="d4ac1-126">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="d4ac1-126">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4ac1-127">prinID</span><span class="sxs-lookup"><span data-stu-id="d4ac1-127">prinID</span></span></p></td>
<td><p><span data-ttu-id="d4ac1-128">Внешний ключ с подстановкой в таблице tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="d4ac1-128">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4ac1-129">nodeID</span><span class="sxs-lookup"><span data-stu-id="d4ac1-129">nodeID</span></span></p></td>
<td><p><span data-ttu-id="d4ac1-130">Внешний ключ с подстановкой в таблице tblNode.nodeID.</span><span class="sxs-lookup"><span data-stu-id="d4ac1-130">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

