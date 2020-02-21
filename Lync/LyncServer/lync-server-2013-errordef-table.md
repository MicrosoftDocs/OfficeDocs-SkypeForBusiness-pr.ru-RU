---
title: 'Lync Server 2013: таблица таблица errordef'
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
ms.openlocfilehash: 6db93ea1b09e50d48ee5e0276d90e3db3975e9fe
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213325"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="errordef-table-in-lync-server-2013"></a><span data-ttu-id="2aef5-102">Таблица Таблица errordef в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2aef5-102">ErrorDef table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2aef5-103">_**Последнее изменение темы:** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="2aef5-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="2aef5-104">В таблице таблица errordef хранятся сведения о каждом типе ошибок, которые могут возникать.</span><span class="sxs-lookup"><span data-stu-id="2aef5-104">The ErrorDef table stores information about each type of error that may occur.</span></span> <span data-ttu-id="2aef5-105">Каждая запись имеет один тип ошибки.</span><span class="sxs-lookup"><span data-stu-id="2aef5-105">Each record is one type of error.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2aef5-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="2aef5-106">Column</span></span></th>
<th><span data-ttu-id="2aef5-107">Тип данных</span><span class="sxs-lookup"><span data-stu-id="2aef5-107">Data Type</span></span></th>
<th><span data-ttu-id="2aef5-108">Ключ или индекс</span><span class="sxs-lookup"><span data-stu-id="2aef5-108">Key/Index</span></span></th>
<th><span data-ttu-id="2aef5-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="2aef5-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2aef5-110"><strong>еррорид</strong></span><span class="sxs-lookup"><span data-stu-id="2aef5-110"><strong>ErrorId</strong></span></span></p></td>
<td><p><span data-ttu-id="2aef5-111">int</span><span class="sxs-lookup"><span data-stu-id="2aef5-111">int</span></span></p></td>
<td><p><span data-ttu-id="2aef5-112">Primary</span><span class="sxs-lookup"><span data-stu-id="2aef5-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="2aef5-113">Уникальный ИДЕНТИФИКАЦИОНный номер, идентифицирующий этот тип ошибки.</span><span class="sxs-lookup"><span data-stu-id="2aef5-113">Unique ID number identifying this type of error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2aef5-114"><strong>респонсекоде</strong></span><span class="sxs-lookup"><span data-stu-id="2aef5-114"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="2aef5-115">int</span><span class="sxs-lookup"><span data-stu-id="2aef5-115">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="2aef5-116">Стандартный код ответа SIP, связанный с этой ошибкой.</span><span class="sxs-lookup"><span data-stu-id="2aef5-116">Standard SIP response code associated with this error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2aef5-117"><strong>мсдиагид</strong></span><span class="sxs-lookup"><span data-stu-id="2aef5-117"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="2aef5-118">int</span><span class="sxs-lookup"><span data-stu-id="2aef5-118">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="2aef5-119">Идентификатор диагностики Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="2aef5-119">Microsoft Diagnostic ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2aef5-120"><strong>каллтипеид</strong></span><span class="sxs-lookup"><span data-stu-id="2aef5-120"><strong>CallTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="2aef5-121">Целое</span><span class="sxs-lookup"><span data-stu-id="2aef5-121">Int</span></span></p></td>
<td><p><span data-ttu-id="2aef5-122">Правительства</span><span class="sxs-lookup"><span data-stu-id="2aef5-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="2aef5-123">Тип вызова.</span><span class="sxs-lookup"><span data-stu-id="2aef5-123">Type of the call.</span></span> <span data-ttu-id="2aef5-124">Дополнительные сведения см. <a href="lync-server-2013-calltype-table.md">в таблице CallType в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="2aef5-124">See the <a href="lync-server-2013-calltype-table.md">CallType table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2aef5-125"><strong>RequestType</strong></span><span class="sxs-lookup"><span data-stu-id="2aef5-125"><strong>RequestType</strong></span></span></p></td>
<td><p><span data-ttu-id="2aef5-126">varbinary (33)</span><span class="sxs-lookup"><span data-stu-id="2aef5-126">varbinary(33)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="2aef5-127">Тип запроса с отказом.</span><span class="sxs-lookup"><span data-stu-id="2aef5-127">Type of request that failed.</span></span></p>
<p><span data-ttu-id="2aef5-128">Эти данные можно преобразовать в текстовый формат, используя следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="2aef5-128">This data can be converted to text format by using this syntax:</span></span></p>
<p><code>cast(cast(RequestType as varbinary(max)) as varchar(max))</code></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2aef5-129"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="2aef5-129"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="2aef5-130">varbinary (257)</span><span class="sxs-lookup"><span data-stu-id="2aef5-130">varbinary(257)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="2aef5-131">Тип содержимого запроса с отказом.</span><span class="sxs-lookup"><span data-stu-id="2aef5-131">Content type of the request that failed.</span></span></p>
<p><span data-ttu-id="2aef5-132">Эти данные можно преобразовать в текстовый формат с помощью следующего синтаксиса:</span><span class="sxs-lookup"><span data-stu-id="2aef5-132">This data can be converted to text format by using this syntaxt:</span></span></p>
<p><code>cast(cast(ContentType as varbinary(max)) as varchar(max))</code></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

