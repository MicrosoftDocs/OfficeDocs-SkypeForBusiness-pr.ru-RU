---
title: 'Lync Server 2013: таблица сервера'
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
ms.openlocfilehash: ebfc08cd5a27527d5afebdae8b2fea8335f93dcb
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48510236"
---
# <a name="server-table-in-lync-server-2013"></a><span data-ttu-id="690ef-102">Таблица Server в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="690ef-102">Server table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="690ef-103">_**Последнее изменение темы:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="690ef-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="690ef-p101">Таблица Server является таблицей поддержки. Каждая запись в этой таблице представляет один сервер.</span><span class="sxs-lookup"><span data-stu-id="690ef-p101">The Server table is a supporting table. Each record represents one server.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="690ef-106"><strong>Column</strong></span><span class="sxs-lookup"><span data-stu-id="690ef-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="690ef-107"><strong>Тип данных</strong></span><span class="sxs-lookup"><span data-stu-id="690ef-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="690ef-108"><strong>Ключ или индекс</strong></span><span class="sxs-lookup"><span data-stu-id="690ef-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="690ef-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="690ef-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="690ef-110"><strong>серверкэй</strong></span><span class="sxs-lookup"><span data-stu-id="690ef-110"><strong>ServerKey</strong></span></span></p></td>
<td><p><span data-ttu-id="690ef-111">int</span><span class="sxs-lookup"><span data-stu-id="690ef-111">int</span></span></p></td>
<td><p><span data-ttu-id="690ef-112">Primary</span><span class="sxs-lookup"><span data-stu-id="690ef-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="690ef-113">Уникальный номер, идентифицирующий сервер.</span><span class="sxs-lookup"><span data-stu-id="690ef-113">Unique number identifying the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="690ef-114"><strong>фкднорип</strong></span><span class="sxs-lookup"><span data-stu-id="690ef-114"><strong>FQDNOrIP</strong></span></span></p></td>
<td><p><span data-ttu-id="690ef-115">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="690ef-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="690ef-116">index</span><span class="sxs-lookup"><span data-stu-id="690ef-116">index</span></span></p></td>
<td><p><span data-ttu-id="690ef-117">Строка MAC-адреса.</span><span class="sxs-lookup"><span data-stu-id="690ef-117">MAC address string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="690ef-118"><strong>ServerType</strong></span><span class="sxs-lookup"><span data-stu-id="690ef-118"><strong>ServerType</strong></span></span></p></td>
<td><p><span data-ttu-id="690ef-119">int</span><span class="sxs-lookup"><span data-stu-id="690ef-119">int</span></span></p></td>
<td><p><span data-ttu-id="690ef-120">Правительства</span><span class="sxs-lookup"><span data-stu-id="690ef-120">Foreign</span></span></p></td>
<td><p><span data-ttu-id="690ef-121">1: сервер-посредник</span><span class="sxs-lookup"><span data-stu-id="690ef-121">1: Mediation Server</span></span></p>
<p><span data-ttu-id="690ef-122">2: сервер аудио- и видеоконференций 16394: пограничная служба аудио- и видеосвязи 32769: шлюз</span><span class="sxs-lookup"><span data-stu-id="690ef-122">2: A/V Conferencing Server16394: A/V Edge service32769: Gateway</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="690ef-123"><strong>пулнаме</strong></span><span class="sxs-lookup"><span data-stu-id="690ef-123"><strong>PoolName</strong></span></span></p></td>
<td><p><span data-ttu-id="690ef-124">nvarchar (512)</span><span class="sxs-lookup"><span data-stu-id="690ef-124">nvarchar(512)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="690ef-p102">Пул, которому принадлежит сервер. Применяется только для серверов аудио- и видеоконференций.</span><span class="sxs-lookup"><span data-stu-id="690ef-p102">Pool the server belongs to. Only applicable for the A/V Conferencing Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="690ef-127"><strong>некступдатетс</strong></span><span class="sxs-lookup"><span data-stu-id="690ef-127"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="690ef-128">datetime</span><span class="sxs-lookup"><span data-stu-id="690ef-128">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="690ef-129">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="690ef-129">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

