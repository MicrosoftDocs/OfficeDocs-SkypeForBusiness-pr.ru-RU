---
title: 'Lync Server 2013: tblEnumValue'
description: 'Lync Server 2013: tblEnumValue.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblEnumValue
ms:assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615025(v=OCS.15)
ms:contentKeyID: 48185040
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 159f90bb96c367fcb3e11725a582a9993080d3fd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571375"
---
# <a name="tblenumvalue-in-lync-server-2013"></a><span data-ttu-id="c4a90-103">tblEnumValue в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c4a90-103">tblEnumValue in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c4a90-104">_**Последнее изменение темы:** 2012-06-28_</span><span class="sxs-lookup"><span data-stu-id="c4a90-104">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="c4a90-105">tblEnumValue — это встроенная таблица, которая содержит значения отображения и поведения атрибутов, используемых в таблице Node.</span><span class="sxs-lookup"><span data-stu-id="c4a90-105">tblEnumValue is a hardcoded table that contains the Visibility and Behavior values of the attributes that are used in the Node table.</span></span>

### <a name="columns"></a><span data-ttu-id="c4a90-106">Столбцы</span><span class="sxs-lookup"><span data-stu-id="c4a90-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c4a90-107">Столбец</span><span class="sxs-lookup"><span data-stu-id="c4a90-107">Column</span></span></th>
<th><span data-ttu-id="c4a90-108">Тип</span><span class="sxs-lookup"><span data-stu-id="c4a90-108">Type</span></span></th>
<th><span data-ttu-id="c4a90-109">Описание</span><span class="sxs-lookup"><span data-stu-id="c4a90-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c4a90-110">валуеид</span><span class="sxs-lookup"><span data-stu-id="c4a90-110">valueID</span></span></p></td>
<td><p><span data-ttu-id="c4a90-111">smallint, not null</span><span class="sxs-lookup"><span data-stu-id="c4a90-111">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="c4a90-112">ИД значения.</span><span class="sxs-lookup"><span data-stu-id="c4a90-112">ID of the value.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4a90-113">attributeID</span><span class="sxs-lookup"><span data-stu-id="c4a90-113">attributeID</span></span></p></td>
<td><p><span data-ttu-id="c4a90-114">smallint, не может быть null</span><span class="sxs-lookup"><span data-stu-id="c4a90-114">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="c4a90-115">ИД атрибута.</span><span class="sxs-lookup"><span data-stu-id="c4a90-115">ID of the attribute.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4a90-116">attributeValue</span><span class="sxs-lookup"><span data-stu-id="c4a90-116">attributeValue</span></span></p></td>
<td><p><span data-ttu-id="c4a90-117">nvarchar (256), not null</span><span class="sxs-lookup"><span data-stu-id="c4a90-117">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="c4a90-118">Имя значения.</span><span class="sxs-lookup"><span data-stu-id="c4a90-118">Name of the value.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="c4a90-119">Keys</span><span class="sxs-lookup"><span data-stu-id="c4a90-119">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c4a90-120">Столбец</span><span class="sxs-lookup"><span data-stu-id="c4a90-120">Column</span></span></th>
<th><span data-ttu-id="c4a90-121">Описание</span><span class="sxs-lookup"><span data-stu-id="c4a90-121">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c4a90-122">валуеид</span><span class="sxs-lookup"><span data-stu-id="c4a90-122">valueID</span></span></p></td>
<td><p><span data-ttu-id="c4a90-123">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="c4a90-123">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4a90-124">attributeID</span><span class="sxs-lookup"><span data-stu-id="c4a90-124">attributeID</span></span></p></td>
<td><p><span data-ttu-id="c4a90-125">Внешний ключ с поиском в таблице tblEnumAttribute.attributeID.</span><span class="sxs-lookup"><span data-stu-id="c4a90-125">Foreign key with lookup in tblEnumAttribute.attributeID table.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="table-values"></a><span data-ttu-id="c4a90-126">Значения таблицы</span><span class="sxs-lookup"><span data-stu-id="c4a90-126">Table Values</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c4a90-127">валуеид</span><span class="sxs-lookup"><span data-stu-id="c4a90-127">valueID</span></span></th>
<th><span data-ttu-id="c4a90-128">attributeID</span><span class="sxs-lookup"><span data-stu-id="c4a90-128">attributeID</span></span></th>
<th><span data-ttu-id="c4a90-129">attributeValue</span><span class="sxs-lookup"><span data-stu-id="c4a90-129">attributeValue</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c4a90-130">2</span><span class="sxs-lookup"><span data-stu-id="c4a90-130">2</span></span></p></td>
<td><p><span data-ttu-id="c4a90-131">1,1</span><span class="sxs-lookup"><span data-stu-id="c4a90-131">1</span></span></p></td>
<td><p><span data-ttu-id="c4a90-132">закрытый</span><span class="sxs-lookup"><span data-stu-id="c4a90-132">private</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4a90-133">4</span><span class="sxs-lookup"><span data-stu-id="c4a90-133">3</span></span></p></td>
<td><p><span data-ttu-id="c4a90-134">1,1</span><span class="sxs-lookup"><span data-stu-id="c4a90-134">1</span></span></p></td>
<td><p><span data-ttu-id="c4a90-135">scope</span><span class="sxs-lookup"><span data-stu-id="c4a90-135">scope</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4a90-136">4 </span><span class="sxs-lookup"><span data-stu-id="c4a90-136">4</span></span></p></td>
<td><p><span data-ttu-id="c4a90-137">2</span><span class="sxs-lookup"><span data-stu-id="c4a90-137">2</span></span></p></td>
<td><p><span data-ttu-id="c4a90-138">обычный</span><span class="sxs-lookup"><span data-stu-id="c4a90-138">normal</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4a90-139">5 </span><span class="sxs-lookup"><span data-stu-id="c4a90-139">5</span></span></p></td>
<td><p><span data-ttu-id="c4a90-140">2</span><span class="sxs-lookup"><span data-stu-id="c4a90-140">2</span></span></p></td>
<td><p><span data-ttu-id="c4a90-141">аудитория</span><span class="sxs-lookup"><span data-stu-id="c4a90-141">auditorium</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4a90-142">6 </span><span class="sxs-lookup"><span data-stu-id="c4a90-142">6</span></span></p></td>
<td><p><span data-ttu-id="c4a90-143">1,1</span><span class="sxs-lookup"><span data-stu-id="c4a90-143">1</span></span></p></td>
<td><p><span data-ttu-id="c4a90-144">окно</span><span class="sxs-lookup"><span data-stu-id="c4a90-144">open</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="c4a90-145">См. также</span><span class="sxs-lookup"><span data-stu-id="c4a90-145">See Also</span></span>


[<span data-ttu-id="c4a90-146">tblNode в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c4a90-146">tblNode in Lync Server 2013</span></span>](lync-server-2013-tblnode.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

