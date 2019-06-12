---
title: 'Lync Server 2013: tblEnumAttribute'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblEnumAttribute
ms:assetid: 17f8b87e-36a6-4f6a-8630-7c76b61a7595
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558617(v=OCS.15)
ms:contentKeyID: 48183523
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2662f5d0ea9b55f8e3f5320b2e385157bef8bce9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849544"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblenumattribute-in-lync-server-2013"></a><span data-ttu-id="b39a2-102">tblEnumAttribute в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b39a2-102">tblEnumAttribute in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b39a2-103">_**Тема последнего изменения:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="b39a2-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="b39a2-104">Тбленуматтрибуте — это жесткая таблица, которая содержит атрибуты видимости и поведения, которые используются в таблице node.</span><span class="sxs-lookup"><span data-stu-id="b39a2-104">tblEnumAttribute is a hardcoded table that contains the Visibility and Behavior attributes that are used in the Node table.</span></span>

### <a name="columns"></a><span data-ttu-id="b39a2-105">Столбцов</span><span class="sxs-lookup"><span data-stu-id="b39a2-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b39a2-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="b39a2-106">Column</span></span></th>
<th><span data-ttu-id="b39a2-107">Тип</span><span class="sxs-lookup"><span data-stu-id="b39a2-107">Type</span></span></th>
<th><span data-ttu-id="b39a2-108">Описание</span><span class="sxs-lookup"><span data-stu-id="b39a2-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b39a2-109">attributeID</span><span class="sxs-lookup"><span data-stu-id="b39a2-109">attributeID</span></span></p></td>
<td><p><span data-ttu-id="b39a2-110">smallint, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="b39a2-110">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="b39a2-111">Идентификатор атрибута.</span><span class="sxs-lookup"><span data-stu-id="b39a2-111">ID of the attribute.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b39a2-112">attributeName</span><span class="sxs-lookup"><span data-stu-id="b39a2-112">attributeName</span></span></p></td>
<td><p><span data-ttu-id="b39a2-113">nvarchar (256), NOT NULL</span><span class="sxs-lookup"><span data-stu-id="b39a2-113">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="b39a2-114">Имя атрибута.</span><span class="sxs-lookup"><span data-stu-id="b39a2-114">Name of the attribute.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="b39a2-115">Ключ</span><span class="sxs-lookup"><span data-stu-id="b39a2-115">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b39a2-116">Столбец</span><span class="sxs-lookup"><span data-stu-id="b39a2-116">Column</span></span></th>
<th><span data-ttu-id="b39a2-117">Описание</span><span class="sxs-lookup"><span data-stu-id="b39a2-117">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b39a2-118">attributeID</span><span class="sxs-lookup"><span data-stu-id="b39a2-118">attributeID</span></span></p></td>
<td><p><span data-ttu-id="b39a2-119">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="b39a2-119">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="table-values"></a><span data-ttu-id="b39a2-120">Значения таблицы</span><span class="sxs-lookup"><span data-stu-id="b39a2-120">Table Values</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b39a2-121">attributeID</span><span class="sxs-lookup"><span data-stu-id="b39a2-121">attributeID</span></span></th>
<th><span data-ttu-id="b39a2-122">attributeName</span><span class="sxs-lookup"><span data-stu-id="b39a2-122">attributeName</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b39a2-123">1</span><span class="sxs-lookup"><span data-stu-id="b39a2-123">1</span></span></p></td>
<td><p><span data-ttu-id="b39a2-124">Отображение.</span><span class="sxs-lookup"><span data-stu-id="b39a2-124">Visibility.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b39a2-125">2</span><span class="sxs-lookup"><span data-stu-id="b39a2-125">2</span></span></p></td>
<td><p><span data-ttu-id="b39a2-126">Расширения.</span><span class="sxs-lookup"><span data-stu-id="b39a2-126">Behavior.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="b39a2-127">См. также</span><span class="sxs-lookup"><span data-stu-id="b39a2-127">See Also</span></span>


[<span data-ttu-id="b39a2-128">tblNode в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b39a2-128">tblNode in Lync Server 2013</span></span>](lync-server-2013-tblnode.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

