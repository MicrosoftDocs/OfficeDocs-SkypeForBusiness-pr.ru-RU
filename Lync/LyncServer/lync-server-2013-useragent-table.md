---
title: 'Lync Server 2013: таблица UserAgent'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: UserAgent table
ms:assetid: d6bda1c0-b053-457a-9ffa-2ae859788775
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398939(v=OCS.15)
ms:contentKeyID: 48185582
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 09bb2e3a71f81014bcb08952c03b59c93ac6a62f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849286"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="useragent-table-in-lync-server-2013"></a><span data-ttu-id="b5a50-102">Таблица UserAgent в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b5a50-102">UserAgent table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b5a50-103">_**Тема последнего изменения:** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="b5a50-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="b5a50-104">Таблица UserAgent является вспомогательной таблицей, в которой хранится список различных агентов пользователей, которые участвовали в сеансах, записанных в базе данных.</span><span class="sxs-lookup"><span data-stu-id="b5a50-104">The UserAgent table is a supporting table that stores a list of the various user agents that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="b5a50-105">Каждая запись в таблице представляет одного агента пользователя</span><span class="sxs-lookup"><span data-stu-id="b5a50-105">Each record in the table represents one user agent</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b5a50-106"><strong>Столбец</strong></span><span class="sxs-lookup"><span data-stu-id="b5a50-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="b5a50-107"><strong>Тип данных</strong></span><span class="sxs-lookup"><span data-stu-id="b5a50-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="b5a50-108"><strong>Ключ/индекс</strong></span><span class="sxs-lookup"><span data-stu-id="b5a50-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="b5a50-109"><strong>Сведения</strong></span><span class="sxs-lookup"><span data-stu-id="b5a50-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b5a50-110"><strong>Усераженткэй</strong></span><span class="sxs-lookup"><span data-stu-id="b5a50-110"><strong>UserAgentKey</strong></span></span></p></td>
<td><p><span data-ttu-id="b5a50-111">целое</span><span class="sxs-lookup"><span data-stu-id="b5a50-111">int</span></span></p></td>
<td><p><span data-ttu-id="b5a50-112">Primary</span><span class="sxs-lookup"><span data-stu-id="b5a50-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="b5a50-113">Уникальный номер, идентифицирующий агент пользователя.</span><span class="sxs-lookup"><span data-stu-id="b5a50-113">Unique number identifying this user agent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5a50-114"><strong>UserAgent</strong></span><span class="sxs-lookup"><span data-stu-id="b5a50-114"><strong>UserAgent</strong></span></span></p></td>
<td><p><span data-ttu-id="b5a50-115">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="b5a50-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b5a50-116">Повторя</span><span class="sxs-lookup"><span data-stu-id="b5a50-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="b5a50-117">Строка агента пользователя.</span><span class="sxs-lookup"><span data-stu-id="b5a50-117">User Agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5a50-118"><strong>Уатипе</strong></span><span class="sxs-lookup"><span data-stu-id="b5a50-118"><strong>UAType</strong></span></span></p></td>
<td><p><span data-ttu-id="b5a50-119">smallint</span><span class="sxs-lookup"><span data-stu-id="b5a50-119">smallint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b5a50-120">1 — сервер исправлений.</span><span class="sxs-lookup"><span data-stu-id="b5a50-120">1 is Mediation Server.</span></span></p>
<p><span data-ttu-id="b5a50-121">2 — это сервер конференц-связи с/V.</span><span class="sxs-lookup"><span data-stu-id="b5a50-121">2 is A/V Conferencing Server.</span></span></p>
<p><span data-ttu-id="b5a50-122">4 — Lync.</span><span class="sxs-lookup"><span data-stu-id="b5a50-122">4 is Lync.</span></span></p>
<p><span data-ttu-id="b5a50-123">8 — это IP-телефон.</span><span class="sxs-lookup"><span data-stu-id="b5a50-123">8 is IP Phone.</span></span></p>
<p><span data-ttu-id="b5a50-124">16 — консоль Live Meeting.</span><span class="sxs-lookup"><span data-stu-id="b5a50-124">16 is Live Meeting Console.</span></span></p>
<p><span data-ttu-id="b5a50-125">32 — средство проверки развертывания (ДВТ).</span><span class="sxs-lookup"><span data-stu-id="b5a50-125">32 is Deployment Validation Tool (DVT).</span></span></p>
<p><span data-ttu-id="b5a50-126">64 — Lync на компьютерах Macintosh.</span><span class="sxs-lookup"><span data-stu-id="b5a50-126">64 is Lync on Macintosh computers.</span></span></p>
<p><span data-ttu-id="b5a50-127">128 – это Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="b5a50-127">128 is Office Communications Server 2007 R2 Attendant.</span></span></p>
<p><span data-ttu-id="b5a50-128">256 является службой объявлений конференций.</span><span class="sxs-lookup"><span data-stu-id="b5a50-128">256 is Conferencing Announcement service.</span></span></p>
<p><span data-ttu-id="b5a50-129">512 — автоматический секретарь конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="b5a50-129">512 is Conferencing Auto Attendant.</span></span></p>
<p><span data-ttu-id="b5a50-130">1024 является приложением группы ответа.</span><span class="sxs-lookup"><span data-stu-id="b5a50-130">1024 is Response Group application.</span></span></p>
<p><span data-ttu-id="b5a50-131">2048 находится за пределами голосового контроля.</span><span class="sxs-lookup"><span data-stu-id="b5a50-131">2048 is Outside Voice Control.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

