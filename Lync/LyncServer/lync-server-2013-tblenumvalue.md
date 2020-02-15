---
title: 'Lync Server 2013: tblEnumValue'
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
ms.openlocfilehash: d182a3689ae38d4117b45d6590bb2ccd08c0a8b7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42027060"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblenumvalue-in-lync-server-2013"></a><span data-ttu-id="fed2a-102">tblEnumValue в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fed2a-102">tblEnumValue in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fed2a-103">_**Последнее изменение темы:** 2012-06-28_</span><span class="sxs-lookup"><span data-stu-id="fed2a-103">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="fed2a-104">tblEnumValue — это встроенная таблица, которая содержит значения отображения и поведения атрибутов, используемых в таблице Node.</span><span class="sxs-lookup"><span data-stu-id="fed2a-104">tblEnumValue is a hardcoded table that contains the Visibility and Behavior values of the attributes that are used in the Node table.</span></span>

### <a name="columns"></a><span data-ttu-id="fed2a-105">Columns</span><span class="sxs-lookup"><span data-stu-id="fed2a-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fed2a-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="fed2a-106">Column</span></span></th>
<th><span data-ttu-id="fed2a-107">Тип</span><span class="sxs-lookup"><span data-stu-id="fed2a-107">Type</span></span></th>
<th><span data-ttu-id="fed2a-108">Описание</span><span class="sxs-lookup"><span data-stu-id="fed2a-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fed2a-109">валуеид</span><span class="sxs-lookup"><span data-stu-id="fed2a-109">valueID</span></span></p></td>
<td><p><span data-ttu-id="fed2a-110">smallint, не может быть null</span><span class="sxs-lookup"><span data-stu-id="fed2a-110">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="fed2a-111">ИД значения.</span><span class="sxs-lookup"><span data-stu-id="fed2a-111">ID of the value.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fed2a-112">attributeID</span><span class="sxs-lookup"><span data-stu-id="fed2a-112">attributeID</span></span></p></td>
<td><p><span data-ttu-id="fed2a-113">smallint, не может быть null</span><span class="sxs-lookup"><span data-stu-id="fed2a-113">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="fed2a-114">ИД атрибута.</span><span class="sxs-lookup"><span data-stu-id="fed2a-114">ID of the attribute.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fed2a-115">attributeValue</span><span class="sxs-lookup"><span data-stu-id="fed2a-115">attributeValue</span></span></p></td>
<td><p><span data-ttu-id="fed2a-116">nvarchar (256), not null</span><span class="sxs-lookup"><span data-stu-id="fed2a-116">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="fed2a-117">Имя значения.</span><span class="sxs-lookup"><span data-stu-id="fed2a-117">Name of the value.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="fed2a-118">Keys</span><span class="sxs-lookup"><span data-stu-id="fed2a-118">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fed2a-119">Столбец</span><span class="sxs-lookup"><span data-stu-id="fed2a-119">Column</span></span></th>
<th><span data-ttu-id="fed2a-120">Описание</span><span class="sxs-lookup"><span data-stu-id="fed2a-120">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fed2a-121">валуеид</span><span class="sxs-lookup"><span data-stu-id="fed2a-121">valueID</span></span></p></td>
<td><p><span data-ttu-id="fed2a-122">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="fed2a-122">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fed2a-123">attributeID</span><span class="sxs-lookup"><span data-stu-id="fed2a-123">attributeID</span></span></p></td>
<td><p><span data-ttu-id="fed2a-124">Внешний ключ с поиском в таблице tblEnumAttribute.attributeID.</span><span class="sxs-lookup"><span data-stu-id="fed2a-124">Foreign key with lookup in tblEnumAttribute.attributeID table.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="table-values"></a><span data-ttu-id="fed2a-125">Значения таблицы</span><span class="sxs-lookup"><span data-stu-id="fed2a-125">Table Values</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fed2a-126">валуеид</span><span class="sxs-lookup"><span data-stu-id="fed2a-126">valueID</span></span></th>
<th><span data-ttu-id="fed2a-127">attributeID</span><span class="sxs-lookup"><span data-stu-id="fed2a-127">attributeID</span></span></th>
<th><span data-ttu-id="fed2a-128">attributeValue</span><span class="sxs-lookup"><span data-stu-id="fed2a-128">attributeValue</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fed2a-129">2 </span><span class="sxs-lookup"><span data-stu-id="fed2a-129">2</span></span></p></td>
<td><p><span data-ttu-id="fed2a-130">1 </span><span class="sxs-lookup"><span data-stu-id="fed2a-130">1</span></span></p></td>
<td><p><span data-ttu-id="fed2a-131">закрытый</span><span class="sxs-lookup"><span data-stu-id="fed2a-131">private</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fed2a-132">3 </span><span class="sxs-lookup"><span data-stu-id="fed2a-132">3</span></span></p></td>
<td><p><span data-ttu-id="fed2a-133">1 </span><span class="sxs-lookup"><span data-stu-id="fed2a-133">1</span></span></p></td>
<td><p><span data-ttu-id="fed2a-134">scope</span><span class="sxs-lookup"><span data-stu-id="fed2a-134">scope</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fed2a-135">4 </span><span class="sxs-lookup"><span data-stu-id="fed2a-135">4</span></span></p></td>
<td><p><span data-ttu-id="fed2a-136">2 </span><span class="sxs-lookup"><span data-stu-id="fed2a-136">2</span></span></p></td>
<td><p><span data-ttu-id="fed2a-137">обычный</span><span class="sxs-lookup"><span data-stu-id="fed2a-137">normal</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fed2a-138">5 </span><span class="sxs-lookup"><span data-stu-id="fed2a-138">5</span></span></p></td>
<td><p><span data-ttu-id="fed2a-139">2 </span><span class="sxs-lookup"><span data-stu-id="fed2a-139">2</span></span></p></td>
<td><p><span data-ttu-id="fed2a-140">аудитория</span><span class="sxs-lookup"><span data-stu-id="fed2a-140">auditorium</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fed2a-141">6 </span><span class="sxs-lookup"><span data-stu-id="fed2a-141">6</span></span></p></td>
<td><p><span data-ttu-id="fed2a-142">1 </span><span class="sxs-lookup"><span data-stu-id="fed2a-142">1</span></span></p></td>
<td><p><span data-ttu-id="fed2a-143">окно</span><span class="sxs-lookup"><span data-stu-id="fed2a-143">open</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="fed2a-144">См. также</span><span class="sxs-lookup"><span data-stu-id="fed2a-144">See Also</span></span>


[<span data-ttu-id="fed2a-145">tblNode в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fed2a-145">tblNode in Lync Server 2013</span></span>](lync-server-2013-tblnode.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

