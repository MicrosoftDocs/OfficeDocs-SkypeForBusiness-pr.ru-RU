---
title: 'Lync Server 2013: таблица UserAgent'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: UserAgent table
ms:assetid: d6bda1c0-b053-457a-9ffa-2ae859788775
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398939(v=OCS.15)
ms:contentKeyID: 48185582
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0ba13a18436c7a55ca68931ff2794fd584be84f9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007628"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="useragent-table-in-lync-server-2013"></a><span data-ttu-id="09bc1-102">Таблица UserAgent в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="09bc1-102">UserAgent table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="09bc1-103">_**Последнее изменение темы:** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="09bc1-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="09bc1-104">Таблица UserAgent это вспомогательная таблица, в которой хранится список различных агентов пользователей, которые участвовали в сеансах, записанных в базе данных.</span><span class="sxs-lookup"><span data-stu-id="09bc1-104">The UserAgent table is a supporting table that stores a list of the various user agents that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="09bc1-105">Каждая запись в таблице представляет одного агента пользователя</span><span class="sxs-lookup"><span data-stu-id="09bc1-105">Each record in the table represents one user agent</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="09bc1-106"><strong>Column</strong></span><span class="sxs-lookup"><span data-stu-id="09bc1-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="09bc1-107"><strong>Тип данных</strong></span><span class="sxs-lookup"><span data-stu-id="09bc1-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="09bc1-108"><strong>Ключ или индекс</strong></span><span class="sxs-lookup"><span data-stu-id="09bc1-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="09bc1-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="09bc1-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="09bc1-110"><strong>усераженткэй</strong></span><span class="sxs-lookup"><span data-stu-id="09bc1-110"><strong>UserAgentKey</strong></span></span></p></td>
<td><p><span data-ttu-id="09bc1-111">int</span><span class="sxs-lookup"><span data-stu-id="09bc1-111">int</span></span></p></td>
<td><p><span data-ttu-id="09bc1-112">Primary</span><span class="sxs-lookup"><span data-stu-id="09bc1-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="09bc1-113">Уникальное число, идентифицирующее этот агент пользователя.</span><span class="sxs-lookup"><span data-stu-id="09bc1-113">Unique number identifying this user agent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="09bc1-114"><strong>UserAgent</strong></span><span class="sxs-lookup"><span data-stu-id="09bc1-114"><strong>UserAgent</strong></span></span></p></td>
<td><p><span data-ttu-id="09bc1-115">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="09bc1-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="09bc1-116">Уникальные</span><span class="sxs-lookup"><span data-stu-id="09bc1-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="09bc1-117">Строка агента пользователя.</span><span class="sxs-lookup"><span data-stu-id="09bc1-117">User Agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="09bc1-118"><strong>UAType</strong></span><span class="sxs-lookup"><span data-stu-id="09bc1-118"><strong>UAType</strong></span></span></p></td>
<td><p><span data-ttu-id="09bc1-119">smallint</span><span class="sxs-lookup"><span data-stu-id="09bc1-119">smallint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="09bc1-120">1 — сервер-посредник.</span><span class="sxs-lookup"><span data-stu-id="09bc1-120">1 is Mediation Server.</span></span></p>
<p><span data-ttu-id="09bc1-121">2 это сервер аудио-и видеоконференций.</span><span class="sxs-lookup"><span data-stu-id="09bc1-121">2 is A/V Conferencing Server.</span></span></p>
<p><span data-ttu-id="09bc1-122">4 — Lync.</span><span class="sxs-lookup"><span data-stu-id="09bc1-122">4 is Lync.</span></span></p>
<p><span data-ttu-id="09bc1-123">8 — IP-телефон.</span><span class="sxs-lookup"><span data-stu-id="09bc1-123">8 is IP Phone.</span></span></p>
<p><span data-ttu-id="09bc1-124">16 — консоль Live Meeting.</span><span class="sxs-lookup"><span data-stu-id="09bc1-124">16 is Live Meeting Console.</span></span></p>
<p><span data-ttu-id="09bc1-125">32 — средство проверки развертывания (ДВТ).</span><span class="sxs-lookup"><span data-stu-id="09bc1-125">32 is Deployment Validation Tool (DVT).</span></span></p>
<p><span data-ttu-id="09bc1-126">64 — Lync на компьютерах Macintosh.</span><span class="sxs-lookup"><span data-stu-id="09bc1-126">64 is Lync on Macintosh computers.</span></span></p>
<p><span data-ttu-id="09bc1-127">128 это Office Communications Server 2007 R2 Attendant.</span><span class="sxs-lookup"><span data-stu-id="09bc1-127">128 is Office Communications Server 2007 R2 Attendant.</span></span></p>
<p><span data-ttu-id="09bc1-128">256 — служба извещений конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="09bc1-128">256 is Conferencing Announcement service.</span></span></p>
<p><span data-ttu-id="09bc1-129">512 является автосекретарем конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="09bc1-129">512 is Conferencing Auto Attendant.</span></span></p>
<p><span data-ttu-id="09bc1-130">1024 — приложение группы ответа.</span><span class="sxs-lookup"><span data-stu-id="09bc1-130">1024 is Response Group application.</span></span></p>
<p><span data-ttu-id="09bc1-131">2048 находится за преноски управления голосовой связью.</span><span class="sxs-lookup"><span data-stu-id="09bc1-131">2048 is Outside Voice Control.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

