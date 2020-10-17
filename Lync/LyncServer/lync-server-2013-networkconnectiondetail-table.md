---
title: 'Lync Server 2013: таблица Нетворкконнектиондетаил'
description: 'Lync Server 2013: таблица Нетворкконнектиондетаил.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: NetworkConnectionDetail table
ms:assetid: b48cc9a6-5232-48b5-bd20-53b68229336b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205185(v=OCS.15)
ms:contentKeyID: 48185170
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dcd0f429999b6629826a9f9369d154afe3c1af2f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561405"
---
# <a name="networkconnectiondetail-table-in-lync-server-2013"></a><span data-ttu-id="4cc8b-103">Таблица Нетворкконнектиондетаил в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4cc8b-103">NetworkConnectionDetail table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4cc8b-104">_**Последнее изменение темы:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="4cc8b-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="4cc8b-105">В таблице NetworkConnectionDetail сопоставляются типы сетевых подключений с идентификаторами сетевых подключений, используемых в базе данных качества взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="4cc8b-105">The NetworkConnectionDetail table maps network connection types to the network connection identifiers used elsewhere in the Quality of Experience database.</span></span> <span data-ttu-id="4cc8b-106">Эта таблица была введена в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4cc8b-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4cc8b-107"><strong>Column</strong></span><span class="sxs-lookup"><span data-stu-id="4cc8b-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="4cc8b-108"><strong>Тип данных</strong></span><span class="sxs-lookup"><span data-stu-id="4cc8b-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="4cc8b-109"><strong>Ключ или индекс</strong></span><span class="sxs-lookup"><span data-stu-id="4cc8b-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="4cc8b-110"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="4cc8b-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4cc8b-111"><strong>нетворкконнектиондетаилкэй</strong></span><span class="sxs-lookup"><span data-stu-id="4cc8b-111"><strong>NetworkConnectionDetailKey</strong></span></span></p></td>
<td><p><span data-ttu-id="4cc8b-112">tinyint</span><span class="sxs-lookup"><span data-stu-id="4cc8b-112">tinyint</span></span></p></td>
<td><p><span data-ttu-id="4cc8b-113">Primary</span><span class="sxs-lookup"><span data-stu-id="4cc8b-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="4cc8b-114">Уникальный идентификатор типа сетевого подключения.</span><span class="sxs-lookup"><span data-stu-id="4cc8b-114">Unique identifier for the network connection type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4cc8b-115"><strong>NetworkConnectionDetail</strong></span><span class="sxs-lookup"><span data-stu-id="4cc8b-115"><strong>NetworkConnectionDetail</strong></span></span></p></td>
<td><p><span data-ttu-id="4cc8b-116">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="4cc8b-116">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4cc8b-117">Уникальные</span><span class="sxs-lookup"><span data-stu-id="4cc8b-117">Unique</span></span></p></td>
<td><p><span data-ttu-id="4cc8b-p102">Тип сетевого подключения, который соответствует значению NetworkConnectionDetailKey. Допускаются следующие значения:</span><span class="sxs-lookup"><span data-stu-id="4cc8b-p102">Network connection type that corresponds to the NetworkConnectionDetailKey. Allowed values are:</span></span></p>
<ol>
<li><p><span data-ttu-id="4cc8b-120">0 — проводное</span><span class="sxs-lookup"><span data-stu-id="4cc8b-120">0 -- Wired</span></span></p></li>
<li><p><span data-ttu-id="4cc8b-121">1 — беспроводное</span><span class="sxs-lookup"><span data-stu-id="4cc8b-121">1 -- WiFi</span></span></p></li>
<li><p><span data-ttu-id="4cc8b-122">2 — Ethernet</span><span class="sxs-lookup"><span data-stu-id="4cc8b-122">2 -- Ethernet</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

