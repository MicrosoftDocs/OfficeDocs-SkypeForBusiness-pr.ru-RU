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
ms.openlocfilehash: 848f4dc19ddf64c53c2dd30ae6ca4c8036b67c79
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764099"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipalmeta-in-lync-server-2013"></a><span data-ttu-id="8dc6c-102">tblPrincipalMeta в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8dc6c-102">tblPrincipalMeta in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8dc6c-103">_**Тема последнего изменения:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="8dc6c-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="8dc6c-104">ТблпринЦипалмета содержит участников, которые необходимо обновлять из доменных служб Active Directory.</span><span class="sxs-lookup"><span data-stu-id="8dc6c-104">tblPrincipalMeta contains the principals that have to be refreshed from Active Directory Domain Services.</span></span>

### <a name="columns"></a><span data-ttu-id="8dc6c-105">Столбцов</span><span class="sxs-lookup"><span data-stu-id="8dc6c-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8dc6c-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="8dc6c-106">Column</span></span></th>
<th><span data-ttu-id="8dc6c-107">Тип</span><span class="sxs-lookup"><span data-stu-id="8dc6c-107">Type</span></span></th>
<th><span data-ttu-id="8dc6c-108">Описание</span><span class="sxs-lookup"><span data-stu-id="8dc6c-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8dc6c-109">принид</span><span class="sxs-lookup"><span data-stu-id="8dc6c-109">prinID</span></span></p></td>
<td><p><span data-ttu-id="8dc6c-110">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="8dc6c-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="8dc6c-111">Идентификатор участника.</span><span class="sxs-lookup"><span data-stu-id="8dc6c-111">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8dc6c-112">принаффилиатионсдирти</span><span class="sxs-lookup"><span data-stu-id="8dc6c-112">prinAffiliationsDirty</span></span></p></td>
<td><p><span data-ttu-id="8dc6c-113">bit, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="8dc6c-113">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="8dc6c-114">Значение true, если присвоить участникам участники необходимо обновлять.</span><span class="sxs-lookup"><span data-stu-id="8dc6c-114">True if principal affiliations have to be refreshed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8dc6c-115">принаттрибутесдирти</span><span class="sxs-lookup"><span data-stu-id="8dc6c-115">prinAttributesDirty</span></span></p></td>
<td><p><span data-ttu-id="8dc6c-116">bit, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="8dc6c-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="8dc6c-117">Значение true, если атрибуты участника нужно обновить.</span><span class="sxs-lookup"><span data-stu-id="8dc6c-117">True if principal attributes have to be refreshed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8dc6c-118">принделетед</span><span class="sxs-lookup"><span data-stu-id="8dc6c-118">prinDeleted</span></span></p></td>
<td><p><span data-ttu-id="8dc6c-119">bit, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="8dc6c-119">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="8dc6c-120">Значение true, если участник удален.</span><span class="sxs-lookup"><span data-stu-id="8dc6c-120">True if the principal has been deleted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8dc6c-121">трикаунт</span><span class="sxs-lookup"><span data-stu-id="8dc6c-121">tryCount</span></span></p></td>
<td><p><span data-ttu-id="8dc6c-122">целое</span><span class="sxs-lookup"><span data-stu-id="8dc6c-122">int</span></span></p></td>
<td><p><span data-ttu-id="8dc6c-123">Количество попыток обновления участника из доменных служб Active Directory, произошедших в данный момент.</span><span class="sxs-lookup"><span data-stu-id="8dc6c-123">Number of attempts to refresh the principal from AD DS that have happened so far.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8dc6c-124">ласттри</span><span class="sxs-lookup"><span data-stu-id="8dc6c-124">lastTry</span></span></p></td>
<td><p><span data-ttu-id="8dc6c-125">datetime</span><span class="sxs-lookup"><span data-stu-id="8dc6c-125">datetime</span></span></p></td>
<td><p><span data-ttu-id="8dc6c-126">Метка времени последней попытки обновить участника.</span><span class="sxs-lookup"><span data-stu-id="8dc6c-126">Time stamp from the latest attempt to refresh the principal.</span></span> <span data-ttu-id="8dc6c-127">Может иметь значение null, если вы еще не пытались обновить обновление.</span><span class="sxs-lookup"><span data-stu-id="8dc6c-127">Can be null if no refresh has been attempted yet.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8dc6c-128">нексттри</span><span class="sxs-lookup"><span data-stu-id="8dc6c-128">nextTry</span></span></p></td>
<td><p><span data-ttu-id="8dc6c-129">datetime</span><span class="sxs-lookup"><span data-stu-id="8dc6c-129">datetime</span></span></p></td>
<td><p><span data-ttu-id="8dc6c-130">Метка времени для следующего запланированного обновления.</span><span class="sxs-lookup"><span data-stu-id="8dc6c-130">Time stamp for the next scheduled refresh.</span></span> <span data-ttu-id="8dc6c-131">Может иметь значение null, если дальнейшее обновление не запланировано.</span><span class="sxs-lookup"><span data-stu-id="8dc6c-131">Can be null if no further refresh has been scheduled.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="8dc6c-132">Параметры</span><span class="sxs-lookup"><span data-stu-id="8dc6c-132">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8dc6c-133">Столбец</span><span class="sxs-lookup"><span data-stu-id="8dc6c-133">Column</span></span></th>
<th><span data-ttu-id="8dc6c-134">Описание</span><span class="sxs-lookup"><span data-stu-id="8dc6c-134">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8dc6c-135">принид</span><span class="sxs-lookup"><span data-stu-id="8dc6c-135">prinID</span></span></p></td>
<td><p><span data-ttu-id="8dc6c-136">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="8dc6c-136">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8dc6c-137">принид</span><span class="sxs-lookup"><span data-stu-id="8dc6c-137">prinID</span></span></p></td>
<td><p><span data-ttu-id="8dc6c-138">Внешний ключ с подстановкой в таблице ТблпринЦипал. Принид.</span><span class="sxs-lookup"><span data-stu-id="8dc6c-138">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

