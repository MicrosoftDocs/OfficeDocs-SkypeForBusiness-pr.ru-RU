---
title: 'Lync Server 2013: таблица таблица conferenceuris'
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
ms.openlocfilehash: e9142be1b2d46a7d7634394970d07dfa450a22e1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529176"
---
# <a name="conferenceuris-table-in-lync-server-2013"></a><span data-ttu-id="b5678-102">Таблица Таблица conferenceuris в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b5678-102">ConferenceUris table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b5678-103">_**Последнее изменение темы:** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="b5678-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="b5678-p101">ConfereneUris — это вспомогательная таблица, в которой хранится список различных URI конференций, используемых в сеансах конференций, записанных в базе данных. Каждая запись в таблице представляет один URI конференции.</span><span class="sxs-lookup"><span data-stu-id="b5678-p101">The ConfereneUris table is a supporting table that stores a list of the various conference URIs that have participated in conference sessions recorded in the database. Each record in the table represents one conference URI.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b5678-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="b5678-106">Column</span></span></th>
<th><span data-ttu-id="b5678-107">Тип данных</span><span class="sxs-lookup"><span data-stu-id="b5678-107">Data Type</span></span></th>
<th><span data-ttu-id="b5678-108">Ключ или индекс</span><span class="sxs-lookup"><span data-stu-id="b5678-108">Key/Index</span></span></th>
<th><span data-ttu-id="b5678-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="b5678-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b5678-110"><strong>некступдатетс</strong></span><span class="sxs-lookup"><span data-stu-id="b5678-110"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="b5678-111">datetime</span><span class="sxs-lookup"><span data-stu-id="b5678-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="b5678-112">Primary</span><span class="sxs-lookup"><span data-stu-id="b5678-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="b5678-113">Метка времени; для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="b5678-113">Time stamp, Internal used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5678-114"><strong>конференцеуриид</strong></span><span class="sxs-lookup"><span data-stu-id="b5678-114"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="b5678-115">int</span><span class="sxs-lookup"><span data-stu-id="b5678-115">int</span></span></p></td>
<td><p><span data-ttu-id="b5678-116">Primary</span><span class="sxs-lookup"><span data-stu-id="b5678-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="b5678-117">Уникальный номер, идентифицирующий этот URI конференции.</span><span class="sxs-lookup"><span data-stu-id="b5678-117">Unique number identifying this conference URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5678-118"><strong>конференцеури</strong></span><span class="sxs-lookup"><span data-stu-id="b5678-118"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="b5678-119">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="b5678-119">nvarchar(450)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b5678-120">URI конференции.</span><span class="sxs-lookup"><span data-stu-id="b5678-120">Conference URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5678-121"><strong>Контрольная сумма</strong></span><span class="sxs-lookup"><span data-stu-id="b5678-121"><strong>Checksum</strong></span></span></p></td>
<td><p><span data-ttu-id="b5678-122">int</span><span class="sxs-lookup"><span data-stu-id="b5678-122">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b5678-p102">Контрольная сумма ConferenceUri. Используется для повышения скорости поиска в базе данных.</span><span class="sxs-lookup"><span data-stu-id="b5678-p102">Checksum of ConferenceUri. Used to increases the speed of database searches.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5678-125"><strong>уритипеид</strong></span><span class="sxs-lookup"><span data-stu-id="b5678-125"><strong>UriTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="b5678-126">int</span><span class="sxs-lookup"><span data-stu-id="b5678-126">int</span></span></p></td>
<td><p><span data-ttu-id="b5678-127">Правительства</span><span class="sxs-lookup"><span data-stu-id="b5678-127">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b5678-128">Тип URI, например conf:chat для конференции обмена мгновенными сообщениями или conf:audio-video для аудио- и видеоконференции.</span><span class="sxs-lookup"><span data-stu-id="b5678-128">URI type, such as conf:chat for IM conference, or conf:audio-video for audio/video conference.</span></span> <span data-ttu-id="b5678-129">Для получения дополнительных сведений ознакомьтесь со статьей <a href="lync-server-2013-uritypes-table.md">таблица таблица uritypes в таблице Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b5678-129">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> table for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

