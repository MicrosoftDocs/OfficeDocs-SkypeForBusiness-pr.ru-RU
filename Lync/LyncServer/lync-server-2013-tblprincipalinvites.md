---
title: 'Lync Server 2013: tblPrincipalInvites'
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
ms.openlocfilehash: ece3601ad32181d0700adbf3eb0d81eca7541b45
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142025"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblprincipalinvites-in-lync-server-2013"></a><span data-ttu-id="0a1e1-102">tblPrincipalInvites в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0a1e1-102">tblPrincipalInvites in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0a1e1-103">_**Последнее изменение темы:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="0a1e1-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="0a1e1-104">tblPrincipalInvites содержит приглашения для всех подготовленных пользователей для всех узлов с включенным автоматическим приглашением.</span><span class="sxs-lookup"><span data-stu-id="0a1e1-104">tblPrincipalInvites contains invitations for all provisioned users for all nodes with auto-invite on.</span></span>

### <a name="columns"></a><span data-ttu-id="0a1e1-105">Columns</span><span class="sxs-lookup"><span data-stu-id="0a1e1-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0a1e1-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="0a1e1-106">Column</span></span></th>
<th><span data-ttu-id="0a1e1-107">Тип</span><span class="sxs-lookup"><span data-stu-id="0a1e1-107">Type</span></span></th>
<th><span data-ttu-id="0a1e1-108">Описание</span><span class="sxs-lookup"><span data-stu-id="0a1e1-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0a1e1-109">prinID</span><span class="sxs-lookup"><span data-stu-id="0a1e1-109">prinID</span></span></p></td>
<td><p><span data-ttu-id="0a1e1-110">int, не равно null</span><span class="sxs-lookup"><span data-stu-id="0a1e1-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="0a1e1-111">Код участника</span><span class="sxs-lookup"><span data-stu-id="0a1e1-111">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0a1e1-112">инвид</span><span class="sxs-lookup"><span data-stu-id="0a1e1-112">invID</span></span></p></td>
<td><p><span data-ttu-id="0a1e1-113">int, not null</span><span class="sxs-lookup"><span data-stu-id="0a1e1-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="0a1e1-114">Уникальный порядковый номер (на код участника), созданный для таблицы tblLastInviteId.</span><span class="sxs-lookup"><span data-stu-id="0a1e1-114">Unique sequential number (per principal ID) generated from tblLastInviteId table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0a1e1-115">nodeID</span><span class="sxs-lookup"><span data-stu-id="0a1e1-115">nodeID</span></span></p></td>
<td><p><span data-ttu-id="0a1e1-116">int, не null</span><span class="sxs-lookup"><span data-stu-id="0a1e1-116">int, not null</span></span></p></td>
<td><p><span data-ttu-id="0a1e1-117">Код узла (только комната чата).</span><span class="sxs-lookup"><span data-stu-id="0a1e1-117">Node ID (chat room only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0a1e1-118">креатедон</span><span class="sxs-lookup"><span data-stu-id="0a1e1-118">createdOn</span></span></p></td>
<td><p><span data-ttu-id="0a1e1-119">datetime, не null</span><span class="sxs-lookup"><span data-stu-id="0a1e1-119">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="0a1e1-120">Время создания.</span><span class="sxs-lookup"><span data-stu-id="0a1e1-120">Time of creation.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="0a1e1-121">Keys</span><span class="sxs-lookup"><span data-stu-id="0a1e1-121">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0a1e1-122">Столбец</span><span class="sxs-lookup"><span data-stu-id="0a1e1-122">Column</span></span></th>
<th><span data-ttu-id="0a1e1-123">Описание</span><span class="sxs-lookup"><span data-stu-id="0a1e1-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0a1e1-124">&lt;prinID, nodeID&gt;</span><span class="sxs-lookup"><span data-stu-id="0a1e1-124">&lt;prinID, nodeID&gt;</span></span></p></td>
<td><p><span data-ttu-id="0a1e1-125">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="0a1e1-125">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0a1e1-126">prinID</span><span class="sxs-lookup"><span data-stu-id="0a1e1-126">prinID</span></span></p></td>
<td><p><span data-ttu-id="0a1e1-127">Внешний ключ с подстановкой в таблице tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="0a1e1-127">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0a1e1-128">nodeID</span><span class="sxs-lookup"><span data-stu-id="0a1e1-128">nodeID</span></span></p></td>
<td><p><span data-ttu-id="0a1e1-129">Внешний ключ с подстановкой в таблице tblNode.nodeID.</span><span class="sxs-lookup"><span data-stu-id="0a1e1-129">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

