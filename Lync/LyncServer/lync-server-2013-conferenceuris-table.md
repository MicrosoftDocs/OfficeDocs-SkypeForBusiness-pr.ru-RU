---
title: 'Lync Server 2013: таблица ConferenceUris'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: ConferenceUris table
ms:assetid: b1721d52-3c65-45ea-8997-06af8fef93fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412854(v=OCS.15)
ms:contentKeyID: 48185160
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e2b1ab44b564d649b6c8fb812077645c6dc13093
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841482"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferenceuris-table-in-lync-server-2013"></a><span data-ttu-id="d3055-102">Таблица ConferenceUris в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d3055-102">ConferenceUris table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d3055-103">_**Тема последнего изменения:** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="d3055-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="d3055-104">Таблица Конференеурис является вспомогательной таблицей, в которой хранится список различных URI конференций, участвующих в сеансах конференц-связи, записанных в базу данных.</span><span class="sxs-lookup"><span data-stu-id="d3055-104">The ConfereneUris table is a supporting table that stores a list of the various conference URIs that have participated in conference sessions recorded in the database.</span></span> <span data-ttu-id="d3055-105">Каждая запись в таблице представляет один URI конференции.</span><span class="sxs-lookup"><span data-stu-id="d3055-105">Each record in the table represents one conference URI.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d3055-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="d3055-106">Column</span></span></th>
<th><span data-ttu-id="d3055-107">Тип данных</span><span class="sxs-lookup"><span data-stu-id="d3055-107">Data Type</span></span></th>
<th><span data-ttu-id="d3055-108">Ключ/индекс</span><span class="sxs-lookup"><span data-stu-id="d3055-108">Key/Index</span></span></th>
<th><span data-ttu-id="d3055-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="d3055-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d3055-110"><strong>Некступдатетс</strong></span><span class="sxs-lookup"><span data-stu-id="d3055-110"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="d3055-111">datetime</span><span class="sxs-lookup"><span data-stu-id="d3055-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="d3055-112">Primary</span><span class="sxs-lookup"><span data-stu-id="d3055-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="d3055-113">Метка времени, используемая в качестве внутренней.</span><span class="sxs-lookup"><span data-stu-id="d3055-113">Time stamp, Internal used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d3055-114"><strong>Конференцеуриид</strong></span><span class="sxs-lookup"><span data-stu-id="d3055-114"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="d3055-115">целое</span><span class="sxs-lookup"><span data-stu-id="d3055-115">int</span></span></p></td>
<td><p><span data-ttu-id="d3055-116">Primary</span><span class="sxs-lookup"><span data-stu-id="d3055-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="d3055-117">Уникальный номер, идентифицирующий этот URI конференции.</span><span class="sxs-lookup"><span data-stu-id="d3055-117">Unique number identifying this conference URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d3055-118"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="d3055-118"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="d3055-119">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="d3055-119">nvarchar(450)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d3055-120">Универсальный код ресурса (URI) Конференции.</span><span class="sxs-lookup"><span data-stu-id="d3055-120">Conference URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d3055-121"><strong>Счет</strong></span><span class="sxs-lookup"><span data-stu-id="d3055-121"><strong>Checksum</strong></span></span></p></td>
<td><p><span data-ttu-id="d3055-122">целое</span><span class="sxs-lookup"><span data-stu-id="d3055-122">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d3055-123">Контрольная сумма для Конференцеури.</span><span class="sxs-lookup"><span data-stu-id="d3055-123">Checksum of ConferenceUri.</span></span> <span data-ttu-id="d3055-124">Используется для увеличения скорости поиска в базе данных.</span><span class="sxs-lookup"><span data-stu-id="d3055-124">Used to increases the speed of database searches.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d3055-125"><strong>Уритипеид</strong></span><span class="sxs-lookup"><span data-stu-id="d3055-125"><strong>UriTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="d3055-126">целое</span><span class="sxs-lookup"><span data-stu-id="d3055-126">int</span></span></p></td>
<td><p><span data-ttu-id="d3055-127">Другом</span><span class="sxs-lookup"><span data-stu-id="d3055-127">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d3055-128">Тип URI, например conf: чат для Конференции с помощью мгновенных сообщений или conf: аудио-видео для голосовой и видеоконференции.</span><span class="sxs-lookup"><span data-stu-id="d3055-128">URI type, such as conf:chat for IM conference, or conf:audio-video for audio/video conference.</span></span> <span data-ttu-id="d3055-129">Более подробную информацию вы увидите в <a href="lync-server-2013-uritypes-table.md">таблице уритипес в таблице Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="d3055-129">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> table for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

