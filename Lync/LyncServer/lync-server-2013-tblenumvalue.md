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
ms.openlocfilehash: 984dd5f161b31c40de914f363c0722657d3194ed
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142105"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblenumvalue-in-lync-server-2013"></a><span data-ttu-id="5ee48-102">tblEnumValue в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5ee48-102">tblEnumValue in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5ee48-103">_**Последнее изменение темы:** 2012-06-28_</span><span class="sxs-lookup"><span data-stu-id="5ee48-103">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="5ee48-104">tblEnumValue — это встроенная таблица, которая содержит значения отображения и поведения атрибутов, используемых в таблице Node.</span><span class="sxs-lookup"><span data-stu-id="5ee48-104">tblEnumValue is a hardcoded table that contains the Visibility and Behavior values of the attributes that are used in the Node table.</span></span>

### <a name="columns"></a><span data-ttu-id="5ee48-105">Columns</span><span class="sxs-lookup"><span data-stu-id="5ee48-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5ee48-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="5ee48-106">Column</span></span></th>
<th><span data-ttu-id="5ee48-107">Тип</span><span class="sxs-lookup"><span data-stu-id="5ee48-107">Type</span></span></th>
<th><span data-ttu-id="5ee48-108">Описание</span><span class="sxs-lookup"><span data-stu-id="5ee48-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5ee48-109">валуеид</span><span class="sxs-lookup"><span data-stu-id="5ee48-109">valueID</span></span></p></td>
<td><p><span data-ttu-id="5ee48-110">smallint, не может быть null</span><span class="sxs-lookup"><span data-stu-id="5ee48-110">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="5ee48-111">ИД значения.</span><span class="sxs-lookup"><span data-stu-id="5ee48-111">ID of the value.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ee48-112">attributeID</span><span class="sxs-lookup"><span data-stu-id="5ee48-112">attributeID</span></span></p></td>
<td><p><span data-ttu-id="5ee48-113">smallint, не может быть null</span><span class="sxs-lookup"><span data-stu-id="5ee48-113">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="5ee48-114">ИД атрибута.</span><span class="sxs-lookup"><span data-stu-id="5ee48-114">ID of the attribute.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5ee48-115">attributeValue</span><span class="sxs-lookup"><span data-stu-id="5ee48-115">attributeValue</span></span></p></td>
<td><p><span data-ttu-id="5ee48-116">nvarchar (256), not null</span><span class="sxs-lookup"><span data-stu-id="5ee48-116">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="5ee48-117">Имя значения.</span><span class="sxs-lookup"><span data-stu-id="5ee48-117">Name of the value.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="5ee48-118">Keys</span><span class="sxs-lookup"><span data-stu-id="5ee48-118">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5ee48-119">Столбец</span><span class="sxs-lookup"><span data-stu-id="5ee48-119">Column</span></span></th>
<th><span data-ttu-id="5ee48-120">Описание</span><span class="sxs-lookup"><span data-stu-id="5ee48-120">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5ee48-121">валуеид</span><span class="sxs-lookup"><span data-stu-id="5ee48-121">valueID</span></span></p></td>
<td><p><span data-ttu-id="5ee48-122">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="5ee48-122">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ee48-123">attributeID</span><span class="sxs-lookup"><span data-stu-id="5ee48-123">attributeID</span></span></p></td>
<td><p><span data-ttu-id="5ee48-124">Внешний ключ с поиском в таблице tblEnumAttribute.attributeID.</span><span class="sxs-lookup"><span data-stu-id="5ee48-124">Foreign key with lookup in tblEnumAttribute.attributeID table.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="table-values"></a><span data-ttu-id="5ee48-125">Значения таблицы</span><span class="sxs-lookup"><span data-stu-id="5ee48-125">Table Values</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5ee48-126">валуеид</span><span class="sxs-lookup"><span data-stu-id="5ee48-126">valueID</span></span></th>
<th><span data-ttu-id="5ee48-127">attributeID</span><span class="sxs-lookup"><span data-stu-id="5ee48-127">attributeID</span></span></th>
<th><span data-ttu-id="5ee48-128">attributeValue</span><span class="sxs-lookup"><span data-stu-id="5ee48-128">attributeValue</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5ee48-129">2</span><span class="sxs-lookup"><span data-stu-id="5ee48-129">2</span></span></p></td>
<td><p><span data-ttu-id="5ee48-130">1,1</span><span class="sxs-lookup"><span data-stu-id="5ee48-130">1</span></span></p></td>
<td><p><span data-ttu-id="5ee48-131">закрытый</span><span class="sxs-lookup"><span data-stu-id="5ee48-131">private</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ee48-132">4</span><span class="sxs-lookup"><span data-stu-id="5ee48-132">3</span></span></p></td>
<td><p><span data-ttu-id="5ee48-133">1,1</span><span class="sxs-lookup"><span data-stu-id="5ee48-133">1</span></span></p></td>
<td><p><span data-ttu-id="5ee48-134">scope</span><span class="sxs-lookup"><span data-stu-id="5ee48-134">scope</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5ee48-135">SP4</span><span class="sxs-lookup"><span data-stu-id="5ee48-135">4</span></span></p></td>
<td><p><span data-ttu-id="5ee48-136">2</span><span class="sxs-lookup"><span data-stu-id="5ee48-136">2</span></span></p></td>
<td><p><span data-ttu-id="5ee48-137">обычный</span><span class="sxs-lookup"><span data-stu-id="5ee48-137">normal</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ee48-138">17:00</span><span class="sxs-lookup"><span data-stu-id="5ee48-138">5</span></span></p></td>
<td><p><span data-ttu-id="5ee48-139">2</span><span class="sxs-lookup"><span data-stu-id="5ee48-139">2</span></span></p></td>
<td><p><span data-ttu-id="5ee48-140">аудитория</span><span class="sxs-lookup"><span data-stu-id="5ee48-140">auditorium</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5ee48-141">6 </span><span class="sxs-lookup"><span data-stu-id="5ee48-141">6</span></span></p></td>
<td><p><span data-ttu-id="5ee48-142">1,1</span><span class="sxs-lookup"><span data-stu-id="5ee48-142">1</span></span></p></td>
<td><p><span data-ttu-id="5ee48-143">окно</span><span class="sxs-lookup"><span data-stu-id="5ee48-143">open</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="5ee48-144">См. также</span><span class="sxs-lookup"><span data-stu-id="5ee48-144">See Also</span></span>


[<span data-ttu-id="5ee48-145">tblNode в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5ee48-145">tblNode in Lync Server 2013</span></span>](lync-server-2013-tblnode.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

