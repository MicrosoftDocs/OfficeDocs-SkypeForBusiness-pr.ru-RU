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
ms.openlocfilehash: 72c6f15b2f0a219871436fe4451984abfddc947a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764079"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblscopeprincipal-in-lync-server-2013"></a><span data-ttu-id="7c036-102">tblScopePrincipal в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7c036-102">tblScopePrincipal in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7c036-103">_**Тема последнего изменения:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="7c036-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="7c036-104">ТблскопепринЦипал включает области, назначенные узлам.</span><span class="sxs-lookup"><span data-stu-id="7c036-104">tblScopePrincipal contains scopes assigned to nodes.</span></span>

### <a name="columns"></a><span data-ttu-id="7c036-105">Столбцов</span><span class="sxs-lookup"><span data-stu-id="7c036-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7c036-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="7c036-106">Column</span></span></th>
<th><span data-ttu-id="7c036-107">Тип</span><span class="sxs-lookup"><span data-stu-id="7c036-107">Type</span></span></th>
<th><span data-ttu-id="7c036-108">Описание</span><span class="sxs-lookup"><span data-stu-id="7c036-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7c036-109">скопенодеид</span><span class="sxs-lookup"><span data-stu-id="7c036-109">scopeNodeID</span></span></p></td>
<td><p><span data-ttu-id="7c036-110">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="7c036-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="7c036-111">Идентификатор узла, к которому относится область.</span><span class="sxs-lookup"><span data-stu-id="7c036-111">Node ID that the scope applies to.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c036-112">скопепринид</span><span class="sxs-lookup"><span data-stu-id="7c036-112">scopePrinID</span></span></p></td>
<td><p><span data-ttu-id="7c036-113">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="7c036-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="7c036-114">Идентификатор участника.</span><span class="sxs-lookup"><span data-stu-id="7c036-114">Principal ID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c036-115">скопеисдениед</span><span class="sxs-lookup"><span data-stu-id="7c036-115">scopeIsDenied</span></span></p></td>
<td><p><span data-ttu-id="7c036-116">bit, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="7c036-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="7c036-117">Значение true, если тип области — Deny; Значение false, если разрешено.</span><span class="sxs-lookup"><span data-stu-id="7c036-117">True if type of scope is Deny; False if Allow.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c036-118">скопеупдатедби</span><span class="sxs-lookup"><span data-stu-id="7c036-118">scopeUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="7c036-119">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="7c036-119">int, not null</span></span></p></td>
<td><p><span data-ttu-id="7c036-120">Идентификатор участника, который последним обновил эту запись.</span><span class="sxs-lookup"><span data-stu-id="7c036-120">ID of the principal that last updated this entry.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="7c036-121">Параметры</span><span class="sxs-lookup"><span data-stu-id="7c036-121">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7c036-122">Столбец</span><span class="sxs-lookup"><span data-stu-id="7c036-122">Column</span></span></th>
<th><span data-ttu-id="7c036-123">Описание</span><span class="sxs-lookup"><span data-stu-id="7c036-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7c036-124">&lt;Скопенодеид, Скопепринид&gt;</span><span class="sxs-lookup"><span data-stu-id="7c036-124">&lt;scopeNodeID, scopePrinID&gt;</span></span></p></td>
<td><p><span data-ttu-id="7c036-125">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="7c036-125">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c036-126">скопенодеид</span><span class="sxs-lookup"><span data-stu-id="7c036-126">scopeNodeID</span></span></p></td>
<td><p><span data-ttu-id="7c036-127">Внешний ключ с подстановкой в таблице Тблноде. Нодеид.</span><span class="sxs-lookup"><span data-stu-id="7c036-127">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c036-128">скопепринид</span><span class="sxs-lookup"><span data-stu-id="7c036-128">scopePrinID</span></span></p></td>
<td><p><span data-ttu-id="7c036-129">Внешний ключ с подстановкой в таблице ТблпринЦипал. Принид.</span><span class="sxs-lookup"><span data-stu-id="7c036-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

