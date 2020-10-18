---
title: 'Lync Server 2013: Тбладупдатес'
description: 'Lync Server 2013: Тбладупдатес.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblADUpdates
ms:assetid: ba19fa16-4d2d-4635-ac32-f93e09469546
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615033(v=OCS.15)
ms:contentKeyID: 48185227
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7ab4418a10eac283d0f39d09b1c1fe15a32b2e68
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573685"
---
# <a name="tbladupdates-in-lync-server-2013"></a><span data-ttu-id="e3cb0-103">Тбладупдатес в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e3cb0-103">tblADUpdates in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e3cb0-104">_**Последнее изменение темы:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="e3cb0-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="e3cb0-105">Тбладупдатес содержит изменения доменных служб Active Directory, которые еще не были обработаны на последующих этапах синхронизации Active Directory.</span><span class="sxs-lookup"><span data-stu-id="e3cb0-105">tblADUpdates contains Active Directory Domain Services changes that have not yet been processed by the later Active Directory Sync steps.</span></span>

### <a name="columns"></a><span data-ttu-id="e3cb0-106">Столбцы</span><span class="sxs-lookup"><span data-stu-id="e3cb0-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e3cb0-107">Столбец</span><span class="sxs-lookup"><span data-stu-id="e3cb0-107">Column</span></span></th>
<th><span data-ttu-id="e3cb0-108">Тип</span><span class="sxs-lookup"><span data-stu-id="e3cb0-108">Type</span></span></th>
<th><span data-ttu-id="e3cb0-109">Описание</span><span class="sxs-lookup"><span data-stu-id="e3cb0-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e3cb0-110">прингуид</span><span class="sxs-lookup"><span data-stu-id="e3cb0-110">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="e3cb0-111">GUID, not null</span><span class="sxs-lookup"><span data-stu-id="e3cb0-111">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="e3cb0-112">Глобальный уникальный ИД измененного объекта.</span><span class="sxs-lookup"><span data-stu-id="e3cb0-112">Principal GUID of the object that changed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3cb0-113">принадпас</span><span class="sxs-lookup"><span data-stu-id="e3cb0-113">prinADPath</span></span></p></td>
<td><p><span data-ttu-id="e3cb0-114">nvarchar (384), not null</span><span class="sxs-lookup"><span data-stu-id="e3cb0-114">nvarchar (384), not null</span></span></p></td>
<td><p><span data-ttu-id="e3cb0-115">Различающееся имя объекта.</span><span class="sxs-lookup"><span data-stu-id="e3cb0-115">Distinguished name of the object.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3cb0-116">принаттрибутесчанжед</span><span class="sxs-lookup"><span data-stu-id="e3cb0-116">prinAttributesChanged</span></span></p></td>
<td><p><span data-ttu-id="e3cb0-117">bit, not null</span><span class="sxs-lookup"><span data-stu-id="e3cb0-117">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="e3cb0-118">TRUE, если изменился хотя бы один атрибут объекта.</span><span class="sxs-lookup"><span data-stu-id="e3cb0-118">True if at least one attribute of the object changed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3cb0-119">принмемберсчанжед</span><span class="sxs-lookup"><span data-stu-id="e3cb0-119">prinMembersChanged</span></span></p></td>
<td><p><span data-ttu-id="e3cb0-120">bit, not null</span><span class="sxs-lookup"><span data-stu-id="e3cb0-120">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="e3cb0-121">TRUE, если изменилось членство.</span><span class="sxs-lookup"><span data-stu-id="e3cb0-121">True if the membership changed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3cb0-122">принаффилиатионсчанжед</span><span class="sxs-lookup"><span data-stu-id="e3cb0-122">prinAffiliationsChanged</span></span></p></td>
<td><p><span data-ttu-id="e3cb0-123">bit, not null</span><span class="sxs-lookup"><span data-stu-id="e3cb0-123">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="e3cb0-124">Не используется.</span><span class="sxs-lookup"><span data-stu-id="e3cb0-124">Not used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3cb0-125">принделетед</span><span class="sxs-lookup"><span data-stu-id="e3cb0-125">prinDeleted</span></span></p></td>
<td><p><span data-ttu-id="e3cb0-126">bit, not null</span><span class="sxs-lookup"><span data-stu-id="e3cb0-126">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="e3cb0-127">TRUE, если объект был удален.</span><span class="sxs-lookup"><span data-stu-id="e3cb0-127">True if the object was deleted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3cb0-128">ластупдатед</span><span class="sxs-lookup"><span data-stu-id="e3cb0-128">lastUpdated</span></span></p></td>
<td><p><span data-ttu-id="e3cb0-129">datetime, not null</span><span class="sxs-lookup"><span data-stu-id="e3cb0-129">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="e3cb0-130">Метка времени добавления строки.</span><span class="sxs-lookup"><span data-stu-id="e3cb0-130">Time stamp of when the row was inserted.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

