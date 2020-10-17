---
title: 'Lync Server 2013: таблица таблица conferenceuris'
description: 'Lync Server 2013: таблица таблица conferenceuris.'
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
ms.openlocfilehash: a142aa9ad1fe4d3ae92aa3e21aa9eee505457cbe
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566745"
---
# <a name="conferenceuris-table-in-lync-server-2013"></a><span data-ttu-id="f537e-103">Таблица Таблица conferenceuris в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f537e-103">ConferenceUris table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f537e-104">_**Последнее изменение темы:** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="f537e-104">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="f537e-p101">ConfereneUris — это вспомогательная таблица, в которой хранится список различных URI конференций, используемых в сеансах конференций, записанных в базе данных. Каждая запись в таблице представляет один URI конференции.</span><span class="sxs-lookup"><span data-stu-id="f537e-p101">The ConfereneUris table is a supporting table that stores a list of the various conference URIs that have participated in conference sessions recorded in the database. Each record in the table represents one conference URI.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f537e-107">Столбец</span><span class="sxs-lookup"><span data-stu-id="f537e-107">Column</span></span></th>
<th><span data-ttu-id="f537e-108">Тип данных</span><span class="sxs-lookup"><span data-stu-id="f537e-108">Data Type</span></span></th>
<th><span data-ttu-id="f537e-109">Ключ или индекс</span><span class="sxs-lookup"><span data-stu-id="f537e-109">Key/Index</span></span></th>
<th><span data-ttu-id="f537e-110">Сведения</span><span class="sxs-lookup"><span data-stu-id="f537e-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f537e-111"><strong>некступдатетс</strong></span><span class="sxs-lookup"><span data-stu-id="f537e-111"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="f537e-112">datetime</span><span class="sxs-lookup"><span data-stu-id="f537e-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="f537e-113">Primary</span><span class="sxs-lookup"><span data-stu-id="f537e-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="f537e-114">Метка времени; для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="f537e-114">Time stamp, Internal used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f537e-115"><strong>конференцеуриид</strong></span><span class="sxs-lookup"><span data-stu-id="f537e-115"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="f537e-116">int</span><span class="sxs-lookup"><span data-stu-id="f537e-116">int</span></span></p></td>
<td><p><span data-ttu-id="f537e-117">Primary</span><span class="sxs-lookup"><span data-stu-id="f537e-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="f537e-118">Уникальный номер, идентифицирующий этот URI конференции.</span><span class="sxs-lookup"><span data-stu-id="f537e-118">Unique number identifying this conference URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f537e-119"><strong>конференцеури</strong></span><span class="sxs-lookup"><span data-stu-id="f537e-119"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="f537e-120">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="f537e-120">nvarchar(450)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f537e-121">URI конференции.</span><span class="sxs-lookup"><span data-stu-id="f537e-121">Conference URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f537e-122"><strong>Контрольная сумма</strong></span><span class="sxs-lookup"><span data-stu-id="f537e-122"><strong>Checksum</strong></span></span></p></td>
<td><p><span data-ttu-id="f537e-123">int</span><span class="sxs-lookup"><span data-stu-id="f537e-123">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f537e-p102">Контрольная сумма ConferenceUri. Используется для повышения скорости поиска в базе данных.</span><span class="sxs-lookup"><span data-stu-id="f537e-p102">Checksum of ConferenceUri. Used to increases the speed of database searches.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f537e-126"><strong>уритипеид</strong></span><span class="sxs-lookup"><span data-stu-id="f537e-126"><strong>UriTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="f537e-127">int</span><span class="sxs-lookup"><span data-stu-id="f537e-127">int</span></span></p></td>
<td><p><span data-ttu-id="f537e-128">Правительства</span><span class="sxs-lookup"><span data-stu-id="f537e-128">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f537e-129">Тип URI, например conf:chat для конференции обмена мгновенными сообщениями или conf:audio-video для аудио- и видеоконференции.</span><span class="sxs-lookup"><span data-stu-id="f537e-129">URI type, such as conf:chat for IM conference, or conf:audio-video for audio/video conference.</span></span> <span data-ttu-id="f537e-130">Для получения дополнительных сведений ознакомьтесь со статьей <a href="lync-server-2013-uritypes-table.md">таблица таблица uritypes в таблице Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f537e-130">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> table for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

