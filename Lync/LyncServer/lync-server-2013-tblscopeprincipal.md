---
title: 'Lync Server 2013: tblScopePrincipal'
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
ms.openlocfilehash: 147d71ada1d0db26e95868a7115556d30cbc2435
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141955"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblscopeprincipal-in-lync-server-2013"></a><span data-ttu-id="210a3-102">tblScopePrincipal в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="210a3-102">tblScopePrincipal in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="210a3-103">_**Последнее изменение темы:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="210a3-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="210a3-104">tblScopePrincipal содержит области, назначенные узлам.</span><span class="sxs-lookup"><span data-stu-id="210a3-104">tblScopePrincipal contains scopes assigned to nodes.</span></span>

### <a name="columns"></a><span data-ttu-id="210a3-105">Columns</span><span class="sxs-lookup"><span data-stu-id="210a3-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="210a3-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="210a3-106">Column</span></span></th>
<th><span data-ttu-id="210a3-107">Тип</span><span class="sxs-lookup"><span data-stu-id="210a3-107">Type</span></span></th>
<th><span data-ttu-id="210a3-108">Описание</span><span class="sxs-lookup"><span data-stu-id="210a3-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="210a3-109">скопенодеид</span><span class="sxs-lookup"><span data-stu-id="210a3-109">scopeNodeID</span></span></p></td>
<td><p><span data-ttu-id="210a3-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="210a3-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="210a3-111">Код узла, к которой применяется область.</span><span class="sxs-lookup"><span data-stu-id="210a3-111">Node ID that the scope applies to.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="210a3-112">скопепринид</span><span class="sxs-lookup"><span data-stu-id="210a3-112">scopePrinID</span></span></p></td>
<td><p><span data-ttu-id="210a3-113">int, не равно null</span><span class="sxs-lookup"><span data-stu-id="210a3-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="210a3-114">Код участника</span><span class="sxs-lookup"><span data-stu-id="210a3-114">Principal ID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="210a3-115">скопеисдениед</span><span class="sxs-lookup"><span data-stu-id="210a3-115">scopeIsDenied</span></span></p></td>
<td><p><span data-ttu-id="210a3-116">bit, не null</span><span class="sxs-lookup"><span data-stu-id="210a3-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="210a3-117">Значение true, если тип области — Deny; значение false, если тип области — Allow.</span><span class="sxs-lookup"><span data-stu-id="210a3-117">True if type of scope is Deny; False if Allow.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="210a3-118">скопеупдатедби</span><span class="sxs-lookup"><span data-stu-id="210a3-118">scopeUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="210a3-119">int, не null</span><span class="sxs-lookup"><span data-stu-id="210a3-119">int, not null</span></span></p></td>
<td><p><span data-ttu-id="210a3-120">Код участника, который последним обновил эту запись.</span><span class="sxs-lookup"><span data-stu-id="210a3-120">ID of the principal that last updated this entry.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="210a3-121">Keys</span><span class="sxs-lookup"><span data-stu-id="210a3-121">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="210a3-122">Столбец</span><span class="sxs-lookup"><span data-stu-id="210a3-122">Column</span></span></th>
<th><span data-ttu-id="210a3-123">Описание</span><span class="sxs-lookup"><span data-stu-id="210a3-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="210a3-124">&lt;Скопенодеид, Скопепринид&gt;</span><span class="sxs-lookup"><span data-stu-id="210a3-124">&lt;scopeNodeID, scopePrinID&gt;</span></span></p></td>
<td><p><span data-ttu-id="210a3-125">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="210a3-125">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="210a3-126">скопенодеид</span><span class="sxs-lookup"><span data-stu-id="210a3-126">scopeNodeID</span></span></p></td>
<td><p><span data-ttu-id="210a3-127">Внешний ключ с подстановкой в таблице tblNode.nodeID.</span><span class="sxs-lookup"><span data-stu-id="210a3-127">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="210a3-128">скопепринид</span><span class="sxs-lookup"><span data-stu-id="210a3-128">scopePrinID</span></span></p></td>
<td><p><span data-ttu-id="210a3-129">Внешний ключ с подстановкой в таблице tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="210a3-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

