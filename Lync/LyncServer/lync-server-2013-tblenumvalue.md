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
ms.openlocfilehash: 79d1b68cd10858812a1310ebbd1f2caae913da75
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509326"
---
# <a name="tblenumvalue-in-lync-server-2013"></a><span data-ttu-id="ca2fe-102">tblEnumValue в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ca2fe-102">tblEnumValue in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ca2fe-103">_**Последнее изменение темы:** 2012-06-28_</span><span class="sxs-lookup"><span data-stu-id="ca2fe-103">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="ca2fe-104">tblEnumValue — это встроенная таблица, которая содержит значения отображения и поведения атрибутов, используемых в таблице Node.</span><span class="sxs-lookup"><span data-stu-id="ca2fe-104">tblEnumValue is a hardcoded table that contains the Visibility and Behavior values of the attributes that are used in the Node table.</span></span>

### <a name="columns"></a><span data-ttu-id="ca2fe-105">Столбцы</span><span class="sxs-lookup"><span data-stu-id="ca2fe-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ca2fe-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="ca2fe-106">Column</span></span></th>
<th><span data-ttu-id="ca2fe-107">Тип</span><span class="sxs-lookup"><span data-stu-id="ca2fe-107">Type</span></span></th>
<th><span data-ttu-id="ca2fe-108">Описание</span><span class="sxs-lookup"><span data-stu-id="ca2fe-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ca2fe-109">валуеид</span><span class="sxs-lookup"><span data-stu-id="ca2fe-109">valueID</span></span></p></td>
<td><p><span data-ttu-id="ca2fe-110">smallint, not null</span><span class="sxs-lookup"><span data-stu-id="ca2fe-110">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="ca2fe-111">ИД значения.</span><span class="sxs-lookup"><span data-stu-id="ca2fe-111">ID of the value.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca2fe-112">attributeID</span><span class="sxs-lookup"><span data-stu-id="ca2fe-112">attributeID</span></span></p></td>
<td><p><span data-ttu-id="ca2fe-113">smallint, не может быть null</span><span class="sxs-lookup"><span data-stu-id="ca2fe-113">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="ca2fe-114">ИД атрибута.</span><span class="sxs-lookup"><span data-stu-id="ca2fe-114">ID of the attribute.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca2fe-115">attributeValue</span><span class="sxs-lookup"><span data-stu-id="ca2fe-115">attributeValue</span></span></p></td>
<td><p><span data-ttu-id="ca2fe-116">nvarchar (256), not null</span><span class="sxs-lookup"><span data-stu-id="ca2fe-116">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="ca2fe-117">Имя значения.</span><span class="sxs-lookup"><span data-stu-id="ca2fe-117">Name of the value.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="ca2fe-118">Keys</span><span class="sxs-lookup"><span data-stu-id="ca2fe-118">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ca2fe-119">Столбец</span><span class="sxs-lookup"><span data-stu-id="ca2fe-119">Column</span></span></th>
<th><span data-ttu-id="ca2fe-120">Описание</span><span class="sxs-lookup"><span data-stu-id="ca2fe-120">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ca2fe-121">валуеид</span><span class="sxs-lookup"><span data-stu-id="ca2fe-121">valueID</span></span></p></td>
<td><p><span data-ttu-id="ca2fe-122">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="ca2fe-122">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca2fe-123">attributeID</span><span class="sxs-lookup"><span data-stu-id="ca2fe-123">attributeID</span></span></p></td>
<td><p><span data-ttu-id="ca2fe-124">Внешний ключ с поиском в таблице tblEnumAttribute.attributeID.</span><span class="sxs-lookup"><span data-stu-id="ca2fe-124">Foreign key with lookup in tblEnumAttribute.attributeID table.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="table-values"></a><span data-ttu-id="ca2fe-125">Значения таблицы</span><span class="sxs-lookup"><span data-stu-id="ca2fe-125">Table Values</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ca2fe-126">валуеид</span><span class="sxs-lookup"><span data-stu-id="ca2fe-126">valueID</span></span></th>
<th><span data-ttu-id="ca2fe-127">attributeID</span><span class="sxs-lookup"><span data-stu-id="ca2fe-127">attributeID</span></span></th>
<th><span data-ttu-id="ca2fe-128">attributeValue</span><span class="sxs-lookup"><span data-stu-id="ca2fe-128">attributeValue</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ca2fe-129">2</span><span class="sxs-lookup"><span data-stu-id="ca2fe-129">2</span></span></p></td>
<td><p><span data-ttu-id="ca2fe-130">1,1</span><span class="sxs-lookup"><span data-stu-id="ca2fe-130">1</span></span></p></td>
<td><p><span data-ttu-id="ca2fe-131">закрытый</span><span class="sxs-lookup"><span data-stu-id="ca2fe-131">private</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca2fe-132">4</span><span class="sxs-lookup"><span data-stu-id="ca2fe-132">3</span></span></p></td>
<td><p><span data-ttu-id="ca2fe-133">1,1</span><span class="sxs-lookup"><span data-stu-id="ca2fe-133">1</span></span></p></td>
<td><p><span data-ttu-id="ca2fe-134">scope</span><span class="sxs-lookup"><span data-stu-id="ca2fe-134">scope</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca2fe-135">4 </span><span class="sxs-lookup"><span data-stu-id="ca2fe-135">4</span></span></p></td>
<td><p><span data-ttu-id="ca2fe-136">2</span><span class="sxs-lookup"><span data-stu-id="ca2fe-136">2</span></span></p></td>
<td><p><span data-ttu-id="ca2fe-137">обычный</span><span class="sxs-lookup"><span data-stu-id="ca2fe-137">normal</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca2fe-138">5 </span><span class="sxs-lookup"><span data-stu-id="ca2fe-138">5</span></span></p></td>
<td><p><span data-ttu-id="ca2fe-139">2</span><span class="sxs-lookup"><span data-stu-id="ca2fe-139">2</span></span></p></td>
<td><p><span data-ttu-id="ca2fe-140">аудитория</span><span class="sxs-lookup"><span data-stu-id="ca2fe-140">auditorium</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca2fe-141">6 </span><span class="sxs-lookup"><span data-stu-id="ca2fe-141">6</span></span></p></td>
<td><p><span data-ttu-id="ca2fe-142">1,1</span><span class="sxs-lookup"><span data-stu-id="ca2fe-142">1</span></span></p></td>
<td><p><span data-ttu-id="ca2fe-143">окно</span><span class="sxs-lookup"><span data-stu-id="ca2fe-143">open</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="ca2fe-144">См. также</span><span class="sxs-lookup"><span data-stu-id="ca2fe-144">See Also</span></span>


[<span data-ttu-id="ca2fe-145">tblNode в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ca2fe-145">tblNode in Lync Server 2013</span></span>](lync-server-2013-tblnode.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

