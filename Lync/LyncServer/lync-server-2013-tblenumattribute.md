---
title: 'Lync Server 2013: Тбленуматтрибуте'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblEnumAttribute
ms:assetid: 17f8b87e-36a6-4f6a-8630-7c76b61a7595
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558617(v=OCS.15)
ms:contentKeyID: 48183523
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f3b015d1148c3c820c27cdbe48e191bd09d2f55e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509356"
---
# <a name="tblenumattribute-in-lync-server-2013"></a><span data-ttu-id="8b0e6-102">Тбленуматтрибуте в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8b0e6-102">tblEnumAttribute in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8b0e6-103">_**Последнее изменение темы:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="8b0e6-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="8b0e6-104">Жестко запрограммированная таблица tblEnumAttribute содержит атрибуты Visibility и Behavior, которые используются в таблице Node.</span><span class="sxs-lookup"><span data-stu-id="8b0e6-104">tblEnumAttribute is a hardcoded table that contains the Visibility and Behavior attributes that are used in the Node table.</span></span>

### <a name="columns"></a><span data-ttu-id="8b0e6-105">Столбцы</span><span class="sxs-lookup"><span data-stu-id="8b0e6-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8b0e6-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="8b0e6-106">Column</span></span></th>
<th><span data-ttu-id="8b0e6-107">Тип</span><span class="sxs-lookup"><span data-stu-id="8b0e6-107">Type</span></span></th>
<th><span data-ttu-id="8b0e6-108">Описание</span><span class="sxs-lookup"><span data-stu-id="8b0e6-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8b0e6-109">attributeID</span><span class="sxs-lookup"><span data-stu-id="8b0e6-109">attributeID</span></span></p></td>
<td><p><span data-ttu-id="8b0e6-110">smallint, не может быть null</span><span class="sxs-lookup"><span data-stu-id="8b0e6-110">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="8b0e6-111">Идентификатор атрибута.</span><span class="sxs-lookup"><span data-stu-id="8b0e6-111">ID of the attribute.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b0e6-112">attributeName</span><span class="sxs-lookup"><span data-stu-id="8b0e6-112">attributeName</span></span></p></td>
<td><p><span data-ttu-id="8b0e6-113">nvarchar (256), не может быть null</span><span class="sxs-lookup"><span data-stu-id="8b0e6-113">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="8b0e6-114">Имя атрибута.</span><span class="sxs-lookup"><span data-stu-id="8b0e6-114">Name of the attribute.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="8b0e6-115">Key</span><span class="sxs-lookup"><span data-stu-id="8b0e6-115">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8b0e6-116">Столбец</span><span class="sxs-lookup"><span data-stu-id="8b0e6-116">Column</span></span></th>
<th><span data-ttu-id="8b0e6-117">Описание</span><span class="sxs-lookup"><span data-stu-id="8b0e6-117">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8b0e6-118">attributeID</span><span class="sxs-lookup"><span data-stu-id="8b0e6-118">attributeID</span></span></p></td>
<td><p><span data-ttu-id="8b0e6-119">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="8b0e6-119">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="table-values"></a><span data-ttu-id="8b0e6-120">Значения таблицы</span><span class="sxs-lookup"><span data-stu-id="8b0e6-120">Table Values</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8b0e6-121">attributeID</span><span class="sxs-lookup"><span data-stu-id="8b0e6-121">attributeID</span></span></th>
<th><span data-ttu-id="8b0e6-122">attributeName</span><span class="sxs-lookup"><span data-stu-id="8b0e6-122">attributeName</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8b0e6-123">1,1</span><span class="sxs-lookup"><span data-stu-id="8b0e6-123">1</span></span></p></td>
<td><p><span data-ttu-id="8b0e6-124">Доступности.</span><span class="sxs-lookup"><span data-stu-id="8b0e6-124">Visibility.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b0e6-125">2</span><span class="sxs-lookup"><span data-stu-id="8b0e6-125">2</span></span></p></td>
<td><p><span data-ttu-id="8b0e6-126">Такое.</span><span class="sxs-lookup"><span data-stu-id="8b0e6-126">Behavior.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="8b0e6-127">См. также</span><span class="sxs-lookup"><span data-stu-id="8b0e6-127">See Also</span></span>


[<span data-ttu-id="8b0e6-128">tblNode в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8b0e6-128">tblNode in Lync Server 2013</span></span>](lync-server-2013-tblnode.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

