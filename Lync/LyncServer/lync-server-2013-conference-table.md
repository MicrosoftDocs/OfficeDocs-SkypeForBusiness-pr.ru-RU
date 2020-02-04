---
title: 'Lync Server 2013: таблица Conference'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conference table
ms:assetid: 2a2c327c-4719-42dc-a3bb-6dbc0864d9af
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425762(v=OCS.15)
ms:contentKeyID: 48183700
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4941dc3ef59630cd77cfb0f8a51407d15ca628f7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756983"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conference-table-in-lync-server-2013"></a><span data-ttu-id="c97da-102">Таблица Conference в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c97da-102">Conference table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c97da-103">_**Тема последнего изменения:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="c97da-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="c97da-104">Таблица конференции — это вспомогательная таблица.</span><span class="sxs-lookup"><span data-stu-id="c97da-104">The Conference table is a supporting table.</span></span> <span data-ttu-id="c97da-105">Каждая запись представляет одну конференцию или одноранговый сеанс.</span><span class="sxs-lookup"><span data-stu-id="c97da-105">Each record represents one conference or peer-to-peer session.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c97da-106"><strong>Столбец</strong></span><span class="sxs-lookup"><span data-stu-id="c97da-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="c97da-107"><strong>Тип данных</strong></span><span class="sxs-lookup"><span data-stu-id="c97da-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="c97da-108"><strong>Ключ/индекс</strong></span><span class="sxs-lookup"><span data-stu-id="c97da-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="c97da-109"><strong>Сведения</strong></span><span class="sxs-lookup"><span data-stu-id="c97da-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c97da-110"><strong>конференцекэй</strong></span><span class="sxs-lookup"><span data-stu-id="c97da-110"><strong>ConferenceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="c97da-111">целое</span><span class="sxs-lookup"><span data-stu-id="c97da-111">int</span></span></p></td>
<td><p><span data-ttu-id="c97da-112">Primary</span><span class="sxs-lookup"><span data-stu-id="c97da-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="c97da-113">Уникальный номер, идентифицирующий эту запись конференции.</span><span class="sxs-lookup"><span data-stu-id="c97da-113">Unique number identifying this conference record.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c97da-114"><strong>конфури</strong></span><span class="sxs-lookup"><span data-stu-id="c97da-114"><strong>ConfURI</strong></span></span></p></td>
<td><p><span data-ttu-id="c97da-115">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="c97da-115">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="c97da-116">повторя</span><span class="sxs-lookup"><span data-stu-id="c97da-116">unique</span></span></p></td>
<td><p><span data-ttu-id="c97da-117">Универсальный код ресурса (URI) для Конференции, если это конференция, или Диалогид, если это одноранговый сеанс.</span><span class="sxs-lookup"><span data-stu-id="c97da-117">Conference URI if this is a conference, or DialogID if this is a peer-to-peer session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c97da-118"><strong>Счет</strong></span><span class="sxs-lookup"><span data-stu-id="c97da-118"><strong>Checksum</strong></span></span></p></td>
<td><p><span data-ttu-id="c97da-119">целое</span><span class="sxs-lookup"><span data-stu-id="c97da-119">int</span></span></p></td>
<td><p><span data-ttu-id="c97da-120">индекса</span><span class="sxs-lookup"><span data-stu-id="c97da-120">index</span></span></p></td>
<td><p><span data-ttu-id="c97da-121">Контрольная сумма URI конференции.</span><span class="sxs-lookup"><span data-stu-id="c97da-121">Checksum of the conference URI.</span></span> <span data-ttu-id="c97da-122">Используется для внутренних целей.</span><span class="sxs-lookup"><span data-stu-id="c97da-122">This is used internally.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c97da-123"><strong>некступдатетс</strong></span><span class="sxs-lookup"><span data-stu-id="c97da-123"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="c97da-124">datetime</span><span class="sxs-lookup"><span data-stu-id="c97da-124">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c97da-125">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="c97da-125">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

