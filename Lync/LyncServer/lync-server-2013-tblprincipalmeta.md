---
title: 'Lync Server 2013: tblPrincipalMeta'
description: 'Lync Server 2013: tblPrincipalMeta.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipalMeta
ms:assetid: 808490d4-7d6d-47a2-b8af-b5940d47073b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615009(v=OCS.15)
ms:contentKeyID: 48184648
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 899fd1e450dac52afa56c1ee1de86da82b2db309
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573645"
---
# <a name="tblprincipalmeta-in-lync-server-2013"></a><span data-ttu-id="d2605-103">tblPrincipalMeta в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d2605-103">tblPrincipalMeta in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d2605-104">_**Последнее изменение темы:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="d2605-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="d2605-105">tblPrincipalMeta содержит субъекты, которые необходимо обновить из доменных служб Active Directory.</span><span class="sxs-lookup"><span data-stu-id="d2605-105">tblPrincipalMeta contains the principals that have to be refreshed from Active Directory Domain Services.</span></span>

### <a name="columns"></a><span data-ttu-id="d2605-106">Столбцы</span><span class="sxs-lookup"><span data-stu-id="d2605-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d2605-107">Столбец</span><span class="sxs-lookup"><span data-stu-id="d2605-107">Column</span></span></th>
<th><span data-ttu-id="d2605-108">Тип</span><span class="sxs-lookup"><span data-stu-id="d2605-108">Type</span></span></th>
<th><span data-ttu-id="d2605-109">Описание</span><span class="sxs-lookup"><span data-stu-id="d2605-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d2605-110">prinID</span><span class="sxs-lookup"><span data-stu-id="d2605-110">prinID</span></span></p></td>
<td><p><span data-ttu-id="d2605-111">int, not null</span><span class="sxs-lookup"><span data-stu-id="d2605-111">int, not null</span></span></p></td>
<td><p><span data-ttu-id="d2605-112">ИД субъекта.</span><span class="sxs-lookup"><span data-stu-id="d2605-112">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d2605-113">принаффилиатионсдирти</span><span class="sxs-lookup"><span data-stu-id="d2605-113">prinAffiliationsDirty</span></span></p></td>
<td><p><span data-ttu-id="d2605-114">bit, не равно null</span><span class="sxs-lookup"><span data-stu-id="d2605-114">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="d2605-115">Значение true, если назначения субъектов требуется обновить.</span><span class="sxs-lookup"><span data-stu-id="d2605-115">True if principal affiliations have to be refreshed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d2605-116">принаттрибутесдирти</span><span class="sxs-lookup"><span data-stu-id="d2605-116">prinAttributesDirty</span></span></p></td>
<td><p><span data-ttu-id="d2605-117">bit, не равно null</span><span class="sxs-lookup"><span data-stu-id="d2605-117">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="d2605-118">Значение true, если атрибуты субъектов требуется обновить.</span><span class="sxs-lookup"><span data-stu-id="d2605-118">True if principal attributes have to be refreshed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d2605-119">принделетед</span><span class="sxs-lookup"><span data-stu-id="d2605-119">prinDeleted</span></span></p></td>
<td><p><span data-ttu-id="d2605-120">bit, не равно null</span><span class="sxs-lookup"><span data-stu-id="d2605-120">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="d2605-121">Значение true, если субъект был удален.</span><span class="sxs-lookup"><span data-stu-id="d2605-121">True if the principal has been deleted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d2605-122">трикаунт</span><span class="sxs-lookup"><span data-stu-id="d2605-122">tryCount</span></span></p></td>
<td><p><span data-ttu-id="d2605-123">int</span><span class="sxs-lookup"><span data-stu-id="d2605-123">int</span></span></p></td>
<td><p><span data-ttu-id="d2605-124">Число попыток обновления субъекта из доменных служб Active Directory, предпринятых на данный момент.</span><span class="sxs-lookup"><span data-stu-id="d2605-124">Number of attempts to refresh the principal from AD DS that have happened so far.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d2605-125">ласттри</span><span class="sxs-lookup"><span data-stu-id="d2605-125">lastTry</span></span></p></td>
<td><p><span data-ttu-id="d2605-126">datetime</span><span class="sxs-lookup"><span data-stu-id="d2605-126">datetime</span></span></p></td>
<td><p><span data-ttu-id="d2605-p101">Метка времени для последней попытки обновления субъекта. Может иметь значение null, если попытки обновления еще не предпринимались.</span><span class="sxs-lookup"><span data-stu-id="d2605-p101">Time stamp from the latest attempt to refresh the principal. Can be null if no refresh has been attempted yet.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d2605-129">нексттри</span><span class="sxs-lookup"><span data-stu-id="d2605-129">nextTry</span></span></p></td>
<td><p><span data-ttu-id="d2605-130">datetime</span><span class="sxs-lookup"><span data-stu-id="d2605-130">datetime</span></span></p></td>
<td><p><span data-ttu-id="d2605-p102">Метка времени для следующего запланированного обновления. Может иметь значение null, если дальнейшее обновление не запланировано.</span><span class="sxs-lookup"><span data-stu-id="d2605-p102">Time stamp for the next scheduled refresh. Can be null if no further refresh has been scheduled.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="d2605-133">Keys</span><span class="sxs-lookup"><span data-stu-id="d2605-133">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d2605-134">Столбец</span><span class="sxs-lookup"><span data-stu-id="d2605-134">Column</span></span></th>
<th><span data-ttu-id="d2605-135">Описание</span><span class="sxs-lookup"><span data-stu-id="d2605-135">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d2605-136">prinID</span><span class="sxs-lookup"><span data-stu-id="d2605-136">prinID</span></span></p></td>
<td><p><span data-ttu-id="d2605-137">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="d2605-137">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d2605-138">prinID</span><span class="sxs-lookup"><span data-stu-id="d2605-138">prinID</span></span></p></td>
<td><p><span data-ttu-id="d2605-139">Внешний ключ с поиском в таблице tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="d2605-139">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

