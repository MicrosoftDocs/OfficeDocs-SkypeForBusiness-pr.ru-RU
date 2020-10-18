---
title: 'Lync Server 2013: таблица сервера'
description: 'Lync Server 2013: Серверная таблица.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server table
ms:assetid: 9af89d08-d35a-48e8-b56d-6df292f973cc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398801(v=OCS.15)
ms:contentKeyID: 48184890
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 00990a91aec64063480d96a16380171990913ad4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576525"
---
# <a name="server-table-in-lync-server-2013"></a><span data-ttu-id="c1d1b-103">Таблица Server в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c1d1b-103">Server table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c1d1b-104">_**Последнее изменение темы:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="c1d1b-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="c1d1b-p101">Таблица Server является таблицей поддержки. Каждая запись в этой таблице представляет один сервер.</span><span class="sxs-lookup"><span data-stu-id="c1d1b-p101">The Server table is a supporting table. Each record represents one server.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c1d1b-107"><strong>Column</strong></span><span class="sxs-lookup"><span data-stu-id="c1d1b-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="c1d1b-108"><strong>Тип данных</strong></span><span class="sxs-lookup"><span data-stu-id="c1d1b-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="c1d1b-109"><strong>Ключ или индекс</strong></span><span class="sxs-lookup"><span data-stu-id="c1d1b-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="c1d1b-110"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="c1d1b-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c1d1b-111"><strong>серверкэй</strong></span><span class="sxs-lookup"><span data-stu-id="c1d1b-111"><strong>ServerKey</strong></span></span></p></td>
<td><p><span data-ttu-id="c1d1b-112">int</span><span class="sxs-lookup"><span data-stu-id="c1d1b-112">int</span></span></p></td>
<td><p><span data-ttu-id="c1d1b-113">Primary</span><span class="sxs-lookup"><span data-stu-id="c1d1b-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="c1d1b-114">Уникальный номер, идентифицирующий сервер.</span><span class="sxs-lookup"><span data-stu-id="c1d1b-114">Unique number identifying the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c1d1b-115"><strong>фкднорип</strong></span><span class="sxs-lookup"><span data-stu-id="c1d1b-115"><strong>FQDNOrIP</strong></span></span></p></td>
<td><p><span data-ttu-id="c1d1b-116">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="c1d1b-116">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c1d1b-117">index</span><span class="sxs-lookup"><span data-stu-id="c1d1b-117">index</span></span></p></td>
<td><p><span data-ttu-id="c1d1b-118">Строка MAC-адреса.</span><span class="sxs-lookup"><span data-stu-id="c1d1b-118">MAC address string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c1d1b-119"><strong>ServerType</strong></span><span class="sxs-lookup"><span data-stu-id="c1d1b-119"><strong>ServerType</strong></span></span></p></td>
<td><p><span data-ttu-id="c1d1b-120">int</span><span class="sxs-lookup"><span data-stu-id="c1d1b-120">int</span></span></p></td>
<td><p><span data-ttu-id="c1d1b-121">Правительства</span><span class="sxs-lookup"><span data-stu-id="c1d1b-121">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c1d1b-122">1: сервер-посредник</span><span class="sxs-lookup"><span data-stu-id="c1d1b-122">1: Mediation Server</span></span></p>
<p><span data-ttu-id="c1d1b-123">2: сервер аудио- и видеоконференций 16394: пограничная служба аудио- и видеосвязи 32769: шлюз</span><span class="sxs-lookup"><span data-stu-id="c1d1b-123">2: A/V Conferencing Server16394: A/V Edge service32769: Gateway</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c1d1b-124"><strong>пулнаме</strong></span><span class="sxs-lookup"><span data-stu-id="c1d1b-124"><strong>PoolName</strong></span></span></p></td>
<td><p><span data-ttu-id="c1d1b-125">nvarchar (512)</span><span class="sxs-lookup"><span data-stu-id="c1d1b-125">nvarchar(512)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c1d1b-p102">Пул, которому принадлежит сервер. Применяется только для серверов аудио- и видеоконференций.</span><span class="sxs-lookup"><span data-stu-id="c1d1b-p102">Pool the server belongs to. Only applicable for the A/V Conferencing Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c1d1b-128"><strong>некступдатетс</strong></span><span class="sxs-lookup"><span data-stu-id="c1d1b-128"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="c1d1b-129">datetime</span><span class="sxs-lookup"><span data-stu-id="c1d1b-129">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c1d1b-130">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="c1d1b-130">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

