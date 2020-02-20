---
title: 'Lync Server 2013: tblPrincipalMeta'
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
ms.openlocfilehash: 5a1b4161a04b3107e3aff7b55ab82840ac6680e6
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141995"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblprincipalmeta-in-lync-server-2013"></a><span data-ttu-id="f57c4-102">tblPrincipalMeta в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f57c4-102">tblPrincipalMeta in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f57c4-103">_**Последнее изменение темы:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="f57c4-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="f57c4-104">tblPrincipalMeta содержит субъекты, которые необходимо обновить из доменных служб Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f57c4-104">tblPrincipalMeta contains the principals that have to be refreshed from Active Directory Domain Services.</span></span>

### <a name="columns"></a><span data-ttu-id="f57c4-105">Columns</span><span class="sxs-lookup"><span data-stu-id="f57c4-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f57c4-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="f57c4-106">Column</span></span></th>
<th><span data-ttu-id="f57c4-107">Тип</span><span class="sxs-lookup"><span data-stu-id="f57c4-107">Type</span></span></th>
<th><span data-ttu-id="f57c4-108">Описание</span><span class="sxs-lookup"><span data-stu-id="f57c4-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f57c4-109">prinID</span><span class="sxs-lookup"><span data-stu-id="f57c4-109">prinID</span></span></p></td>
<td><p><span data-ttu-id="f57c4-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="f57c4-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="f57c4-111">ИД субъекта.</span><span class="sxs-lookup"><span data-stu-id="f57c4-111">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f57c4-112">принаффилиатионсдирти</span><span class="sxs-lookup"><span data-stu-id="f57c4-112">prinAffiliationsDirty</span></span></p></td>
<td><p><span data-ttu-id="f57c4-113">bit, не равно null</span><span class="sxs-lookup"><span data-stu-id="f57c4-113">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="f57c4-114">Значение true, если назначения субъектов требуется обновить.</span><span class="sxs-lookup"><span data-stu-id="f57c4-114">True if principal affiliations have to be refreshed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f57c4-115">принаттрибутесдирти</span><span class="sxs-lookup"><span data-stu-id="f57c4-115">prinAttributesDirty</span></span></p></td>
<td><p><span data-ttu-id="f57c4-116">bit, не равно null</span><span class="sxs-lookup"><span data-stu-id="f57c4-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="f57c4-117">Значение true, если атрибуты субъектов требуется обновить.</span><span class="sxs-lookup"><span data-stu-id="f57c4-117">True if principal attributes have to be refreshed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f57c4-118">принделетед</span><span class="sxs-lookup"><span data-stu-id="f57c4-118">prinDeleted</span></span></p></td>
<td><p><span data-ttu-id="f57c4-119">bit, не равно null</span><span class="sxs-lookup"><span data-stu-id="f57c4-119">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="f57c4-120">Значение true, если субъект был удален.</span><span class="sxs-lookup"><span data-stu-id="f57c4-120">True if the principal has been deleted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f57c4-121">трикаунт</span><span class="sxs-lookup"><span data-stu-id="f57c4-121">tryCount</span></span></p></td>
<td><p><span data-ttu-id="f57c4-122">int</span><span class="sxs-lookup"><span data-stu-id="f57c4-122">int</span></span></p></td>
<td><p><span data-ttu-id="f57c4-123">Число попыток обновления субъекта из доменных служб Active Directory, предпринятых на данный момент.</span><span class="sxs-lookup"><span data-stu-id="f57c4-123">Number of attempts to refresh the principal from AD DS that have happened so far.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f57c4-124">ласттри</span><span class="sxs-lookup"><span data-stu-id="f57c4-124">lastTry</span></span></p></td>
<td><p><span data-ttu-id="f57c4-125">datetime</span><span class="sxs-lookup"><span data-stu-id="f57c4-125">datetime</span></span></p></td>
<td><p><span data-ttu-id="f57c4-p101">Метка времени для последней попытки обновления субъекта. Может иметь значение null, если попытки обновления еще не предпринимались.</span><span class="sxs-lookup"><span data-stu-id="f57c4-p101">Time stamp from the latest attempt to refresh the principal. Can be null if no refresh has been attempted yet.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f57c4-128">нексттри</span><span class="sxs-lookup"><span data-stu-id="f57c4-128">nextTry</span></span></p></td>
<td><p><span data-ttu-id="f57c4-129">datetime</span><span class="sxs-lookup"><span data-stu-id="f57c4-129">datetime</span></span></p></td>
<td><p><span data-ttu-id="f57c4-p102">Метка времени для следующего запланированного обновления. Может иметь значение null, если дальнейшее обновление не запланировано.</span><span class="sxs-lookup"><span data-stu-id="f57c4-p102">Time stamp for the next scheduled refresh. Can be null if no further refresh has been scheduled.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="f57c4-132">Keys</span><span class="sxs-lookup"><span data-stu-id="f57c4-132">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f57c4-133">Столбец</span><span class="sxs-lookup"><span data-stu-id="f57c4-133">Column</span></span></th>
<th><span data-ttu-id="f57c4-134">Описание</span><span class="sxs-lookup"><span data-stu-id="f57c4-134">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f57c4-135">prinID</span><span class="sxs-lookup"><span data-stu-id="f57c4-135">prinID</span></span></p></td>
<td><p><span data-ttu-id="f57c4-136">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="f57c4-136">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f57c4-137">prinID</span><span class="sxs-lookup"><span data-stu-id="f57c4-137">prinID</span></span></p></td>
<td><p><span data-ttu-id="f57c4-138">Внешний ключ с поиском в таблице tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="f57c4-138">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

