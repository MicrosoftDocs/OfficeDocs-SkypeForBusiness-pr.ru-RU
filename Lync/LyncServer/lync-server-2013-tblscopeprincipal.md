---
title: 'Lync Server 2013: tblScopePrincipal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblScopePrincipal
ms:assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558639(v=OCS.15)
ms:contentKeyID: 48184009
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ece5ae542060835aefa05edb6e08b766293e2ac1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849522"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblscopeprincipal-in-lync-server-2013"></a><span data-ttu-id="5b5d6-102">tblScopePrincipal в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5b5d6-102">tblScopePrincipal in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5b5d6-103">_**Тема последнего изменения:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="5b5d6-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="5b5d6-104">ТблскопепринЦипал включает области, назначенные узлам.</span><span class="sxs-lookup"><span data-stu-id="5b5d6-104">tblScopePrincipal contains scopes assigned to nodes.</span></span>

### <a name="columns"></a><span data-ttu-id="5b5d6-105">Столбцов</span><span class="sxs-lookup"><span data-stu-id="5b5d6-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5b5d6-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="5b5d6-106">Column</span></span></th>
<th><span data-ttu-id="5b5d6-107">Тип</span><span class="sxs-lookup"><span data-stu-id="5b5d6-107">Type</span></span></th>
<th><span data-ttu-id="5b5d6-108">Описание</span><span class="sxs-lookup"><span data-stu-id="5b5d6-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5b5d6-109">Скопенодеид</span><span class="sxs-lookup"><span data-stu-id="5b5d6-109">scopeNodeID</span></span></p></td>
<td><p><span data-ttu-id="5b5d6-110">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="5b5d6-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="5b5d6-111">Идентификатор узла, к которому относится область.</span><span class="sxs-lookup"><span data-stu-id="5b5d6-111">Node ID that the scope applies to.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b5d6-112">Скопепринид</span><span class="sxs-lookup"><span data-stu-id="5b5d6-112">scopePrinID</span></span></p></td>
<td><p><span data-ttu-id="5b5d6-113">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="5b5d6-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="5b5d6-114">Идентификатор участника.</span><span class="sxs-lookup"><span data-stu-id="5b5d6-114">Principal ID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5b5d6-115">Скопеисдениед</span><span class="sxs-lookup"><span data-stu-id="5b5d6-115">scopeIsDenied</span></span></p></td>
<td><p><span data-ttu-id="5b5d6-116">bit, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="5b5d6-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="5b5d6-117">Значение true, если тип области — Deny; Значение false, если разрешено.</span><span class="sxs-lookup"><span data-stu-id="5b5d6-117">True if type of scope is Deny; False if Allow.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b5d6-118">Скопеупдатедби</span><span class="sxs-lookup"><span data-stu-id="5b5d6-118">scopeUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="5b5d6-119">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="5b5d6-119">int, not null</span></span></p></td>
<td><p><span data-ttu-id="5b5d6-120">Идентификатор участника, который последним обновил эту запись.</span><span class="sxs-lookup"><span data-stu-id="5b5d6-120">ID of the principal that last updated this entry.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="5b5d6-121">Параметры</span><span class="sxs-lookup"><span data-stu-id="5b5d6-121">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5b5d6-122">Столбец</span><span class="sxs-lookup"><span data-stu-id="5b5d6-122">Column</span></span></th>
<th><span data-ttu-id="5b5d6-123">Описание</span><span class="sxs-lookup"><span data-stu-id="5b5d6-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5b5d6-124">&lt;Скопенодеид, Скопепринид&gt;</span><span class="sxs-lookup"><span data-stu-id="5b5d6-124">&lt;scopeNodeID, scopePrinID&gt;</span></span></p></td>
<td><p><span data-ttu-id="5b5d6-125">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="5b5d6-125">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b5d6-126">Скопенодеид</span><span class="sxs-lookup"><span data-stu-id="5b5d6-126">scopeNodeID</span></span></p></td>
<td><p><span data-ttu-id="5b5d6-127">Внешний ключ с подстановкой в таблице Тблноде. Нодеид.</span><span class="sxs-lookup"><span data-stu-id="5b5d6-127">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5b5d6-128">Скопепринид</span><span class="sxs-lookup"><span data-stu-id="5b5d6-128">scopePrinID</span></span></p></td>
<td><p><span data-ttu-id="5b5d6-129">Внешний ключ с подстановкой в таблице ТблпринЦипал. Принид.</span><span class="sxs-lookup"><span data-stu-id="5b5d6-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

