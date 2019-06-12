---
title: 'Lync Server 2013: tblEnumValue'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblEnumValue
ms:assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615025(v=OCS.15)
ms:contentKeyID: 48185040
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1758daf16575491960415647e4c9bc4b43920d26
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849555"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblenumvalue-in-lync-server-2013"></a><span data-ttu-id="944f3-102">tblEnumValue в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="944f3-102">tblEnumValue in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="944f3-103">_**Тема последнего изменения:** 2012-06-28_</span><span class="sxs-lookup"><span data-stu-id="944f3-103">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="944f3-104">Тбленумвалуе — это жесткая таблица, содержащая значения видимости и поведения атрибутов, используемых в таблице node.</span><span class="sxs-lookup"><span data-stu-id="944f3-104">tblEnumValue is a hardcoded table that contains the Visibility and Behavior values of the attributes that are used in the Node table.</span></span>

### <a name="columns"></a><span data-ttu-id="944f3-105">Столбцов</span><span class="sxs-lookup"><span data-stu-id="944f3-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="944f3-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="944f3-106">Column</span></span></th>
<th><span data-ttu-id="944f3-107">Тип</span><span class="sxs-lookup"><span data-stu-id="944f3-107">Type</span></span></th>
<th><span data-ttu-id="944f3-108">Описание</span><span class="sxs-lookup"><span data-stu-id="944f3-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="944f3-109">Валуеид</span><span class="sxs-lookup"><span data-stu-id="944f3-109">valueID</span></span></p></td>
<td><p><span data-ttu-id="944f3-110">smallint, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="944f3-110">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="944f3-111">Идентификатор значения.</span><span class="sxs-lookup"><span data-stu-id="944f3-111">ID of the value.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="944f3-112">attributeID</span><span class="sxs-lookup"><span data-stu-id="944f3-112">attributeID</span></span></p></td>
<td><p><span data-ttu-id="944f3-113">smallint, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="944f3-113">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="944f3-114">Идентификатор атрибута.</span><span class="sxs-lookup"><span data-stu-id="944f3-114">ID of the attribute.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="944f3-115">attributeValue</span><span class="sxs-lookup"><span data-stu-id="944f3-115">attributeValue</span></span></p></td>
<td><p><span data-ttu-id="944f3-116">nvarchar (256), NOT NULL</span><span class="sxs-lookup"><span data-stu-id="944f3-116">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="944f3-117">Имя значения.</span><span class="sxs-lookup"><span data-stu-id="944f3-117">Name of the value.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="944f3-118">Параметры</span><span class="sxs-lookup"><span data-stu-id="944f3-118">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="944f3-119">Столбец</span><span class="sxs-lookup"><span data-stu-id="944f3-119">Column</span></span></th>
<th><span data-ttu-id="944f3-120">Описание</span><span class="sxs-lookup"><span data-stu-id="944f3-120">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="944f3-121">Валуеид</span><span class="sxs-lookup"><span data-stu-id="944f3-121">valueID</span></span></p></td>
<td><p><span data-ttu-id="944f3-122">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="944f3-122">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="944f3-123">attributeID</span><span class="sxs-lookup"><span data-stu-id="944f3-123">attributeID</span></span></p></td>
<td><p><span data-ttu-id="944f3-124">Внешний ключ с подстановкой в таблице Тбленуматтрибуте. attributeID.</span><span class="sxs-lookup"><span data-stu-id="944f3-124">Foreign key with lookup in tblEnumAttribute.attributeID table.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="table-values"></a><span data-ttu-id="944f3-125">Значения таблицы</span><span class="sxs-lookup"><span data-stu-id="944f3-125">Table Values</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="944f3-126">Валуеид</span><span class="sxs-lookup"><span data-stu-id="944f3-126">valueID</span></span></th>
<th><span data-ttu-id="944f3-127">attributeID</span><span class="sxs-lookup"><span data-stu-id="944f3-127">attributeID</span></span></th>
<th><span data-ttu-id="944f3-128">attributeValue</span><span class="sxs-lookup"><span data-stu-id="944f3-128">attributeValue</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="944f3-129">2</span><span class="sxs-lookup"><span data-stu-id="944f3-129">2</span></span></p></td>
<td><p><span data-ttu-id="944f3-130">1</span><span class="sxs-lookup"><span data-stu-id="944f3-130">1</span></span></p></td>
<td><p><span data-ttu-id="944f3-131">закрытые</span><span class="sxs-lookup"><span data-stu-id="944f3-131">private</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="944f3-132">3</span><span class="sxs-lookup"><span data-stu-id="944f3-132">3</span></span></p></td>
<td><p><span data-ttu-id="944f3-133">1</span><span class="sxs-lookup"><span data-stu-id="944f3-133">1</span></span></p></td>
<td><p><span data-ttu-id="944f3-134">област</span><span class="sxs-lookup"><span data-stu-id="944f3-134">scope</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="944f3-135">4</span><span class="sxs-lookup"><span data-stu-id="944f3-135">4</span></span></p></td>
<td><p><span data-ttu-id="944f3-136">2</span><span class="sxs-lookup"><span data-stu-id="944f3-136">2</span></span></p></td>
<td><p><span data-ttu-id="944f3-137">нормальный</span><span class="sxs-lookup"><span data-stu-id="944f3-137">normal</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="944f3-138">5</span><span class="sxs-lookup"><span data-stu-id="944f3-138">5</span></span></p></td>
<td><p><span data-ttu-id="944f3-139">2</span><span class="sxs-lookup"><span data-stu-id="944f3-139">2</span></span></p></td>
<td><p><span data-ttu-id="944f3-140">Аудиториум</span><span class="sxs-lookup"><span data-stu-id="944f3-140">auditorium</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="944f3-141">6</span><span class="sxs-lookup"><span data-stu-id="944f3-141">6</span></span></p></td>
<td><p><span data-ttu-id="944f3-142">1</span><span class="sxs-lookup"><span data-stu-id="944f3-142">1</span></span></p></td>
<td><p><span data-ttu-id="944f3-143">запуска</span><span class="sxs-lookup"><span data-stu-id="944f3-143">open</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="944f3-144">См. также</span><span class="sxs-lookup"><span data-stu-id="944f3-144">See Also</span></span>


[<span data-ttu-id="944f3-145">tblNode в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="944f3-145">tblNode in Lync Server 2013</span></span>](lync-server-2013-tblnode.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

