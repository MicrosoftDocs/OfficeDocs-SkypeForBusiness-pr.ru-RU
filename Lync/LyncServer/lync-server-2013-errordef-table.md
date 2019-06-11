---
title: 'Lync Server 2013: таблица ErrorDef'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: ErrorDef table
ms:assetid: 6acf3b86-da61-4923-9812-300db6f66dec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398503(v=OCS.15)
ms:contentKeyID: 48184403
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ef21484d564419a5ab5cce7373ceb0b0b71e4a29
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834199"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="errordef-table-in-lync-server-2013"></a><span data-ttu-id="8f86e-102">Таблица ErrorDef в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8f86e-102">ErrorDef table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8f86e-103">_**Тема последнего изменения:** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="8f86e-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="8f86e-104">В таблице Еррордеф хранятся сведения о каждом типе ошибки, которые могут возникать.</span><span class="sxs-lookup"><span data-stu-id="8f86e-104">The ErrorDef table stores information about each type of error that may occur.</span></span> <span data-ttu-id="8f86e-105">Каждая запись имеет один тип ошибки.</span><span class="sxs-lookup"><span data-stu-id="8f86e-105">Each record is one type of error.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8f86e-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="8f86e-106">Column</span></span></th>
<th><span data-ttu-id="8f86e-107">Тип данных</span><span class="sxs-lookup"><span data-stu-id="8f86e-107">Data Type</span></span></th>
<th><span data-ttu-id="8f86e-108">Ключ/индекс</span><span class="sxs-lookup"><span data-stu-id="8f86e-108">Key/Index</span></span></th>
<th><span data-ttu-id="8f86e-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="8f86e-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8f86e-110"><strong>Еррорид</strong></span><span class="sxs-lookup"><span data-stu-id="8f86e-110"><strong>ErrorId</strong></span></span></p></td>
<td><p><span data-ttu-id="8f86e-111">целое</span><span class="sxs-lookup"><span data-stu-id="8f86e-111">int</span></span></p></td>
<td><p><span data-ttu-id="8f86e-112">Primary</span><span class="sxs-lookup"><span data-stu-id="8f86e-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="8f86e-113">Уникальный ИДЕНТИФИКАЦИОНный номер, показывающий этот тип ошибки.</span><span class="sxs-lookup"><span data-stu-id="8f86e-113">Unique ID number identifying this type of error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f86e-114"><strong>Респонсекоде</strong></span><span class="sxs-lookup"><span data-stu-id="8f86e-114"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="8f86e-115">целое</span><span class="sxs-lookup"><span data-stu-id="8f86e-115">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8f86e-116">Стандартный код ответа SIP, связанный с этой ошибкой.</span><span class="sxs-lookup"><span data-stu-id="8f86e-116">Standard SIP response code associated with this error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f86e-117"><strong>Мсдиагид</strong></span><span class="sxs-lookup"><span data-stu-id="8f86e-117"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="8f86e-118">целое</span><span class="sxs-lookup"><span data-stu-id="8f86e-118">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8f86e-119">Идентификатор диагностики (Майкрософт).</span><span class="sxs-lookup"><span data-stu-id="8f86e-119">Microsoft Diagnostic ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f86e-120"><strong>Каллтипеид</strong></span><span class="sxs-lookup"><span data-stu-id="8f86e-120"><strong>CallTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="8f86e-121">Типом</span><span class="sxs-lookup"><span data-stu-id="8f86e-121">Int</span></span></p></td>
<td><p><span data-ttu-id="8f86e-122">Другом</span><span class="sxs-lookup"><span data-stu-id="8f86e-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="8f86e-123">Тип звонка.</span><span class="sxs-lookup"><span data-stu-id="8f86e-123">Type of the call.</span></span> <span data-ttu-id="8f86e-124">Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-calltype-table.md">таблицей каллтипе в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="8f86e-124">See the <a href="lync-server-2013-calltype-table.md">CallType table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f86e-125"><strong>RequestType</strong></span><span class="sxs-lookup"><span data-stu-id="8f86e-125"><strong>RequestType</strong></span></span></p></td>
<td><p><span data-ttu-id="8f86e-126">varbinary (33)</span><span class="sxs-lookup"><span data-stu-id="8f86e-126">varbinary(33)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8f86e-127">Тип запроса, который завершился сбоем.</span><span class="sxs-lookup"><span data-stu-id="8f86e-127">Type of request that failed.</span></span></p>
<p><span data-ttu-id="8f86e-128">Эти данные можно преобразовать в текстовый формат, используя следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="8f86e-128">This data can be converted to text format by using this syntax:</span></span></p>
<p><code>cast(cast(RequestType as varbinary(max)) as varchar(max))</code></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f86e-129"><strong>Контента</strong></span><span class="sxs-lookup"><span data-stu-id="8f86e-129"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="8f86e-130">varbinary (257)</span><span class="sxs-lookup"><span data-stu-id="8f86e-130">varbinary(257)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8f86e-131">Тип контента запроса, который завершился сбоем.</span><span class="sxs-lookup"><span data-stu-id="8f86e-131">Content type of the request that failed.</span></span></p>
<p><span data-ttu-id="8f86e-132">Эти данные можно преобразовать в текстовый формат с помощью синтаксиса:</span><span class="sxs-lookup"><span data-stu-id="8f86e-132">This data can be converted to text format by using this syntaxt:</span></span></p>
<p><code>cast(cast(ContentType as varbinary(max)) as varchar(max))</code></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

