---
title: 'Lync Server 2013: таблица ConferenceUris'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ConferenceUris table
ms:assetid: b1721d52-3c65-45ea-8997-06af8fef93fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412854(v=OCS.15)
ms:contentKeyID: 48185160
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3cacbaf4e8c7c826ae2e00e9c86b44cc8387f315
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741579"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferenceuris-table-in-lync-server-2013"></a><span data-ttu-id="80e87-102">Таблица ConferenceUris в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="80e87-102">ConferenceUris table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="80e87-103">_**Тема последнего изменения:** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="80e87-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="80e87-104">Таблица Конференеурис является вспомогательной таблицей, в которой хранится список различных URI конференций, участвующих в сеансах конференц-связи, записанных в базу данных.</span><span class="sxs-lookup"><span data-stu-id="80e87-104">The ConfereneUris table is a supporting table that stores a list of the various conference URIs that have participated in conference sessions recorded in the database.</span></span> <span data-ttu-id="80e87-105">Каждая запись в таблице представляет один URI конференции.</span><span class="sxs-lookup"><span data-stu-id="80e87-105">Each record in the table represents one conference URI.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="80e87-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="80e87-106">Column</span></span></th>
<th><span data-ttu-id="80e87-107">Тип данных</span><span class="sxs-lookup"><span data-stu-id="80e87-107">Data Type</span></span></th>
<th><span data-ttu-id="80e87-108">Ключ/индекс</span><span class="sxs-lookup"><span data-stu-id="80e87-108">Key/Index</span></span></th>
<th><span data-ttu-id="80e87-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="80e87-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="80e87-110"><strong>некступдатетс</strong></span><span class="sxs-lookup"><span data-stu-id="80e87-110"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="80e87-111">datetime</span><span class="sxs-lookup"><span data-stu-id="80e87-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="80e87-112">Primary</span><span class="sxs-lookup"><span data-stu-id="80e87-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="80e87-113">Метка времени, используемая в качестве внутренней.</span><span class="sxs-lookup"><span data-stu-id="80e87-113">Time stamp, Internal used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80e87-114"><strong>конференцеуриид</strong></span><span class="sxs-lookup"><span data-stu-id="80e87-114"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="80e87-115">целое</span><span class="sxs-lookup"><span data-stu-id="80e87-115">int</span></span></p></td>
<td><p><span data-ttu-id="80e87-116">Primary</span><span class="sxs-lookup"><span data-stu-id="80e87-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="80e87-117">Уникальный номер, идентифицирующий этот URI конференции.</span><span class="sxs-lookup"><span data-stu-id="80e87-117">Unique number identifying this conference URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80e87-118"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="80e87-118"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="80e87-119">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="80e87-119">nvarchar(450)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="80e87-120">Универсальный код ресурса (URI) Конференции.</span><span class="sxs-lookup"><span data-stu-id="80e87-120">Conference URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80e87-121"><strong>Счет</strong></span><span class="sxs-lookup"><span data-stu-id="80e87-121"><strong>Checksum</strong></span></span></p></td>
<td><p><span data-ttu-id="80e87-122">целое</span><span class="sxs-lookup"><span data-stu-id="80e87-122">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="80e87-123">Контрольная сумма для Конференцеури.</span><span class="sxs-lookup"><span data-stu-id="80e87-123">Checksum of ConferenceUri.</span></span> <span data-ttu-id="80e87-124">Используется для увеличения скорости поиска в базе данных.</span><span class="sxs-lookup"><span data-stu-id="80e87-124">Used to increases the speed of database searches.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80e87-125"><strong>уритипеид</strong></span><span class="sxs-lookup"><span data-stu-id="80e87-125"><strong>UriTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="80e87-126">целое</span><span class="sxs-lookup"><span data-stu-id="80e87-126">int</span></span></p></td>
<td><p><span data-ttu-id="80e87-127">Другом</span><span class="sxs-lookup"><span data-stu-id="80e87-127">Foreign</span></span></p></td>
<td><p><span data-ttu-id="80e87-128">Тип URI, например conf: чат для Конференции с помощью мгновенных сообщений или conf: аудио-видео для голосовой и видеоконференции.</span><span class="sxs-lookup"><span data-stu-id="80e87-128">URI type, such as conf:chat for IM conference, or conf:audio-video for audio/video conference.</span></span> <span data-ttu-id="80e87-129">Более подробную информацию вы увидите в <a href="lync-server-2013-uritypes-table.md">таблице уритипес в таблице Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="80e87-129">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> table for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

