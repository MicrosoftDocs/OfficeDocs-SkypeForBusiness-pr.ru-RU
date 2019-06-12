---
title: 'Lync Server 2013: tblPrincipalMeta'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblPrincipalMeta
ms:assetid: 808490d4-7d6d-47a2-b8af-b5940d47073b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615009(v=OCS.15)
ms:contentKeyID: 48184648
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3b9b067b9d04ecb32a3e43dbbd1f8435c00fa0c0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849533"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipalmeta-in-lync-server-2013"></a><span data-ttu-id="e9a50-102">tblPrincipalMeta в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9a50-102">tblPrincipalMeta in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e9a50-103">_**Тема последнего изменения:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="e9a50-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="e9a50-104">ТблпринЦипалмета содержит участников, которые необходимо обновлять из доменных служб Active Directory.</span><span class="sxs-lookup"><span data-stu-id="e9a50-104">tblPrincipalMeta contains the principals that have to be refreshed from Active Directory Domain Services.</span></span>

### <a name="columns"></a><span data-ttu-id="e9a50-105">Столбцов</span><span class="sxs-lookup"><span data-stu-id="e9a50-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e9a50-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="e9a50-106">Column</span></span></th>
<th><span data-ttu-id="e9a50-107">Тип</span><span class="sxs-lookup"><span data-stu-id="e9a50-107">Type</span></span></th>
<th><span data-ttu-id="e9a50-108">Описание</span><span class="sxs-lookup"><span data-stu-id="e9a50-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e9a50-109">Принид</span><span class="sxs-lookup"><span data-stu-id="e9a50-109">prinID</span></span></p></td>
<td><p><span data-ttu-id="e9a50-110">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="e9a50-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="e9a50-111">Идентификатор участника.</span><span class="sxs-lookup"><span data-stu-id="e9a50-111">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9a50-112">Принаффилиатионсдирти</span><span class="sxs-lookup"><span data-stu-id="e9a50-112">prinAffiliationsDirty</span></span></p></td>
<td><p><span data-ttu-id="e9a50-113">bit, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="e9a50-113">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="e9a50-114">Значение true, если присвоить участникам участники необходимо обновлять.</span><span class="sxs-lookup"><span data-stu-id="e9a50-114">True if principal affiliations have to be refreshed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9a50-115">Принаттрибутесдирти</span><span class="sxs-lookup"><span data-stu-id="e9a50-115">prinAttributesDirty</span></span></p></td>
<td><p><span data-ttu-id="e9a50-116">bit, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="e9a50-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="e9a50-117">Значение true, если атрибуты участника нужно обновить.</span><span class="sxs-lookup"><span data-stu-id="e9a50-117">True if principal attributes have to be refreshed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9a50-118">Принделетед</span><span class="sxs-lookup"><span data-stu-id="e9a50-118">prinDeleted</span></span></p></td>
<td><p><span data-ttu-id="e9a50-119">bit, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="e9a50-119">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="e9a50-120">Значение true, если участник удален.</span><span class="sxs-lookup"><span data-stu-id="e9a50-120">True if the principal has been deleted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9a50-121">Трикаунт</span><span class="sxs-lookup"><span data-stu-id="e9a50-121">tryCount</span></span></p></td>
<td><p><span data-ttu-id="e9a50-122">целое</span><span class="sxs-lookup"><span data-stu-id="e9a50-122">int</span></span></p></td>
<td><p><span data-ttu-id="e9a50-123">Количество попыток обновления участника из доменных служб Active Directory, произошедших в данный момент.</span><span class="sxs-lookup"><span data-stu-id="e9a50-123">Number of attempts to refresh the principal from AD DS that have happened so far.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9a50-124">Ласттри</span><span class="sxs-lookup"><span data-stu-id="e9a50-124">lastTry</span></span></p></td>
<td><p><span data-ttu-id="e9a50-125">datetime</span><span class="sxs-lookup"><span data-stu-id="e9a50-125">datetime</span></span></p></td>
<td><p><span data-ttu-id="e9a50-126">Метка времени последней попытки обновить участника.</span><span class="sxs-lookup"><span data-stu-id="e9a50-126">Time stamp from the latest attempt to refresh the principal.</span></span> <span data-ttu-id="e9a50-127">Может иметь значение null, если вы еще не пытались обновить обновление.</span><span class="sxs-lookup"><span data-stu-id="e9a50-127">Can be null if no refresh has been attempted yet.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9a50-128">Нексттри</span><span class="sxs-lookup"><span data-stu-id="e9a50-128">nextTry</span></span></p></td>
<td><p><span data-ttu-id="e9a50-129">datetime</span><span class="sxs-lookup"><span data-stu-id="e9a50-129">datetime</span></span></p></td>
<td><p><span data-ttu-id="e9a50-130">Метка времени для следующего запланированного обновления.</span><span class="sxs-lookup"><span data-stu-id="e9a50-130">Time stamp for the next scheduled refresh.</span></span> <span data-ttu-id="e9a50-131">Может иметь значение null, если дальнейшее обновление не запланировано.</span><span class="sxs-lookup"><span data-stu-id="e9a50-131">Can be null if no further refresh has been scheduled.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="e9a50-132">Параметры</span><span class="sxs-lookup"><span data-stu-id="e9a50-132">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e9a50-133">Столбец</span><span class="sxs-lookup"><span data-stu-id="e9a50-133">Column</span></span></th>
<th><span data-ttu-id="e9a50-134">Описание</span><span class="sxs-lookup"><span data-stu-id="e9a50-134">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e9a50-135">Принид</span><span class="sxs-lookup"><span data-stu-id="e9a50-135">prinID</span></span></p></td>
<td><p><span data-ttu-id="e9a50-136">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="e9a50-136">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9a50-137">Принид</span><span class="sxs-lookup"><span data-stu-id="e9a50-137">prinID</span></span></p></td>
<td><p><span data-ttu-id="e9a50-138">Внешний ключ с подстановкой в таблице ТблпринЦипал. Принид.</span><span class="sxs-lookup"><span data-stu-id="e9a50-138">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

