---
title: 'Lync Server 2013: таблица таблица errordef'
description: 'Lync Server 2013: таблица таблица errordef.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ErrorDef table
ms:assetid: 6acf3b86-da61-4923-9812-300db6f66dec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398503(v=OCS.15)
ms:contentKeyID: 48184403
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e58980a671b54007012bbbf6780e24c162aebe00
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542755"
---
# <a name="errordef-table-in-lync-server-2013"></a><span data-ttu-id="46ec3-103">Таблица Таблица errordef в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="46ec3-103">ErrorDef table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="46ec3-104">_**Последнее изменение темы:** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="46ec3-104">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="46ec3-105">В таблице таблица errordef хранятся сведения о каждом типе ошибок, которые могут возникать.</span><span class="sxs-lookup"><span data-stu-id="46ec3-105">The ErrorDef table stores information about each type of error that may occur.</span></span> <span data-ttu-id="46ec3-106">Каждая запись имеет один тип ошибки.</span><span class="sxs-lookup"><span data-stu-id="46ec3-106">Each record is one type of error.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="46ec3-107">Столбец</span><span class="sxs-lookup"><span data-stu-id="46ec3-107">Column</span></span></th>
<th><span data-ttu-id="46ec3-108">Тип данных</span><span class="sxs-lookup"><span data-stu-id="46ec3-108">Data Type</span></span></th>
<th><span data-ttu-id="46ec3-109">Ключ или индекс</span><span class="sxs-lookup"><span data-stu-id="46ec3-109">Key/Index</span></span></th>
<th><span data-ttu-id="46ec3-110">Сведения</span><span class="sxs-lookup"><span data-stu-id="46ec3-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="46ec3-111"><strong>еррорид</strong></span><span class="sxs-lookup"><span data-stu-id="46ec3-111"><strong>ErrorId</strong></span></span></p></td>
<td><p><span data-ttu-id="46ec3-112">int</span><span class="sxs-lookup"><span data-stu-id="46ec3-112">int</span></span></p></td>
<td><p><span data-ttu-id="46ec3-113">Primary</span><span class="sxs-lookup"><span data-stu-id="46ec3-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="46ec3-114">Уникальный ИДЕНТИФИКАЦИОНный номер, идентифицирующий этот тип ошибки.</span><span class="sxs-lookup"><span data-stu-id="46ec3-114">Unique ID number identifying this type of error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46ec3-115"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="46ec3-115"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="46ec3-116">int</span><span class="sxs-lookup"><span data-stu-id="46ec3-116">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="46ec3-117">Стандартный код ответа SIP, связанный с этой ошибкой.</span><span class="sxs-lookup"><span data-stu-id="46ec3-117">Standard SIP response code associated with this error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="46ec3-118"><strong>мсдиагид</strong></span><span class="sxs-lookup"><span data-stu-id="46ec3-118"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="46ec3-119">int</span><span class="sxs-lookup"><span data-stu-id="46ec3-119">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="46ec3-120">Идентификатор диагностики Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="46ec3-120">Microsoft Diagnostic ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46ec3-121"><strong>каллтипеид</strong></span><span class="sxs-lookup"><span data-stu-id="46ec3-121"><strong>CallTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="46ec3-122">Целое</span><span class="sxs-lookup"><span data-stu-id="46ec3-122">Int</span></span></p></td>
<td><p><span data-ttu-id="46ec3-123">Правительства</span><span class="sxs-lookup"><span data-stu-id="46ec3-123">Foreign</span></span></p></td>
<td><p><span data-ttu-id="46ec3-124">Тип вызова.</span><span class="sxs-lookup"><span data-stu-id="46ec3-124">Type of the call.</span></span> <span data-ttu-id="46ec3-125">Дополнительные сведения см. <a href="lync-server-2013-calltype-table.md">в таблице CallType в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="46ec3-125">See the <a href="lync-server-2013-calltype-table.md">CallType table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="46ec3-126"><strong>RequestType</strong></span><span class="sxs-lookup"><span data-stu-id="46ec3-126"><strong>RequestType</strong></span></span></p></td>
<td><p><span data-ttu-id="46ec3-127">varbinary (33)</span><span class="sxs-lookup"><span data-stu-id="46ec3-127">varbinary(33)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="46ec3-128">Тип запроса с отказом.</span><span class="sxs-lookup"><span data-stu-id="46ec3-128">Type of request that failed.</span></span></p>
<p><span data-ttu-id="46ec3-129">Эти данные можно преобразовать в текстовый формат, используя следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="46ec3-129">This data can be converted to text format by using this syntax:</span></span></p>
<p><code>cast(cast(RequestType as varbinary(max)) as varchar(max))</code></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46ec3-130"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="46ec3-130"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="46ec3-131">varbinary (257)</span><span class="sxs-lookup"><span data-stu-id="46ec3-131">varbinary(257)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="46ec3-132">Тип содержимого запроса с отказом.</span><span class="sxs-lookup"><span data-stu-id="46ec3-132">Content type of the request that failed.</span></span></p>
<p><span data-ttu-id="46ec3-133">Эти данные можно преобразовать в текстовый формат с помощью следующего синтаксиса:</span><span class="sxs-lookup"><span data-stu-id="46ec3-133">This data can be converted to text format by using this syntaxt:</span></span></p>
<p><code>cast(cast(ContentType as varbinary(max)) as varchar(max))</code></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

