---
title: 'Lync Server 2013: таблица Conference'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Conference table
ms:assetid: 2a2c327c-4719-42dc-a3bb-6dbc0864d9af
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425762(v=OCS.15)
ms:contentKeyID: 48183700
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f57f7baf017507da44677cc475c99d192fe868f0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841490"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conference-table-in-lync-server-2013"></a><span data-ttu-id="f10db-102">Таблица Conference в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f10db-102">Conference table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f10db-103">_**Тема последнего изменения:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="f10db-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="f10db-104">Таблица конференции — это вспомогательная таблица.</span><span class="sxs-lookup"><span data-stu-id="f10db-104">The Conference table is a supporting table.</span></span> <span data-ttu-id="f10db-105">Каждая запись представляет одну конференцию или одноранговый сеанс.</span><span class="sxs-lookup"><span data-stu-id="f10db-105">Each record represents one conference or peer-to-peer session.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f10db-106"><strong>Столбец</strong></span><span class="sxs-lookup"><span data-stu-id="f10db-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="f10db-107"><strong>Тип данных</strong></span><span class="sxs-lookup"><span data-stu-id="f10db-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="f10db-108"><strong>Ключ/индекс</strong></span><span class="sxs-lookup"><span data-stu-id="f10db-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="f10db-109"><strong>Сведения</strong></span><span class="sxs-lookup"><span data-stu-id="f10db-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f10db-110"><strong>Конференцекэй</strong></span><span class="sxs-lookup"><span data-stu-id="f10db-110"><strong>ConferenceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="f10db-111">целое</span><span class="sxs-lookup"><span data-stu-id="f10db-111">int</span></span></p></td>
<td><p><span data-ttu-id="f10db-112">Primary</span><span class="sxs-lookup"><span data-stu-id="f10db-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="f10db-113">Уникальный номер, идентифицирующий эту запись конференции.</span><span class="sxs-lookup"><span data-stu-id="f10db-113">Unique number identifying this conference record.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f10db-114"><strong>Конфури</strong></span><span class="sxs-lookup"><span data-stu-id="f10db-114"><strong>ConfURI</strong></span></span></p></td>
<td><p><span data-ttu-id="f10db-115">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="f10db-115">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="f10db-116">повторя</span><span class="sxs-lookup"><span data-stu-id="f10db-116">unique</span></span></p></td>
<td><p><span data-ttu-id="f10db-117">Универсальный код ресурса (URI) для Конференции, если это конференция, или Диалогид, если это одноранговый сеанс.</span><span class="sxs-lookup"><span data-stu-id="f10db-117">Conference URI if this is a conference, or DialogID if this is a peer-to-peer session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f10db-118"><strong>Счет</strong></span><span class="sxs-lookup"><span data-stu-id="f10db-118"><strong>Checksum</strong></span></span></p></td>
<td><p><span data-ttu-id="f10db-119">целое</span><span class="sxs-lookup"><span data-stu-id="f10db-119">int</span></span></p></td>
<td><p><span data-ttu-id="f10db-120">индекса</span><span class="sxs-lookup"><span data-stu-id="f10db-120">index</span></span></p></td>
<td><p><span data-ttu-id="f10db-121">Контрольная сумма URI конференции.</span><span class="sxs-lookup"><span data-stu-id="f10db-121">Checksum of the conference URI.</span></span> <span data-ttu-id="f10db-122">Используется для внутренних целей.</span><span class="sxs-lookup"><span data-stu-id="f10db-122">This is used internally.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f10db-123"><strong>Некступдатетс</strong></span><span class="sxs-lookup"><span data-stu-id="f10db-123"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="f10db-124">datetime</span><span class="sxs-lookup"><span data-stu-id="f10db-124">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f10db-125">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="f10db-125">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

