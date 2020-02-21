---
title: 'Lync Server 2013: таблица таблица videostream'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: VideoStream table
ms:assetid: 4275ede7-5467-4a97-b8c8-a4b00917bf32
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425928(v=OCS.15)
ms:contentKeyID: 48184014
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a313419ca4072fe4d1841ba66a9cb603671e6c56
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211653"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="videostream-table-in-lync-server-2013"></a><span data-ttu-id="9b3e4-102">Таблица Таблица videostream в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9b3e4-102">VideoStream table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9b3e4-103">_**Последнее изменение темы:** 2013-12-13_</span><span class="sxs-lookup"><span data-stu-id="9b3e4-103">_**Topic Last Modified:** 2013-12-13_</span></span>

<span data-ttu-id="9b3e4-104">Каждая запись представляет один видеопоток.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-104">Each record represents one video stream.</span></span> <span data-ttu-id="9b3e4-105">Одна линия видеопотока обычно содержит два видеопотока.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-105">One video media line usually contains two video streams.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9b3e4-106"><strong>Column</strong></span><span class="sxs-lookup"><span data-stu-id="9b3e4-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="9b3e4-107"><strong>Тип данных</strong></span><span class="sxs-lookup"><span data-stu-id="9b3e4-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="9b3e4-108"><strong>Ключ или индекс</strong></span><span class="sxs-lookup"><span data-stu-id="9b3e4-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="9b3e4-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="9b3e4-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9b3e4-110"><strong>конференцедатетиме</strong></span><span class="sxs-lookup"><span data-stu-id="9b3e4-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="9b3e4-111">datetime</span><span class="sxs-lookup"><span data-stu-id="9b3e4-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="9b3e4-112">Primary</span><span class="sxs-lookup"><span data-stu-id="9b3e4-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="9b3e4-113">Ссылка из <a href="lync-server-2013-medialine-table.md">таблицы MediaLine в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9b3e4-114"><strong>сессионсек</strong></span><span class="sxs-lookup"><span data-stu-id="9b3e4-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="9b3e4-115">int</span><span class="sxs-lookup"><span data-stu-id="9b3e4-115">int</span></span></p></td>
<td><p><span data-ttu-id="9b3e4-116">Primary</span><span class="sxs-lookup"><span data-stu-id="9b3e4-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="9b3e4-117">R, на который ссылается <a href="lync-server-2013-medialine-table.md">Таблица MediaLine в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-117">R Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9b3e4-118"><strong>медиалинелабел</strong></span><span class="sxs-lookup"><span data-stu-id="9b3e4-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="9b3e4-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="9b3e4-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="9b3e4-120">Primary</span><span class="sxs-lookup"><span data-stu-id="9b3e4-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="9b3e4-121">Ссылка из <a href="lync-server-2013-medialine-table.md">таблицы MediaLine в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9b3e4-122"><strong>стреамид</strong></span><span class="sxs-lookup"><span data-stu-id="9b3e4-122"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="9b3e4-123">int</span><span class="sxs-lookup"><span data-stu-id="9b3e4-123">int</span></span></p></td>
<td><p><span data-ttu-id="9b3e4-124">Primary</span><span class="sxs-lookup"><span data-stu-id="9b3e4-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="9b3e4-125">Уникальный идентификатор в линии мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-125">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9b3e4-126"><strong>видеопайлоаддескриптион</strong></span><span class="sxs-lookup"><span data-stu-id="9b3e4-126"><strong>VideoPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="9b3e4-127">smallint</span><span class="sxs-lookup"><span data-stu-id="9b3e4-127">smallint</span></span></p></td>
<td><p><span data-ttu-id="9b3e4-128">Внешний, основной</span><span class="sxs-lookup"><span data-stu-id="9b3e4-128">Foreign, Primary</span></span></p></td>
<td><p><span data-ttu-id="9b3e4-129">Описание полезных данных.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-129">Payload description.</span></span> <span data-ttu-id="9b3e4-130">Дополнительные сведения см. <a href="lync-server-2013-payloaddescription-table.md">в таблице таблица payloaddescription в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="9b3e4-130">See the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9b3e4-131"><strong>життеринтерарривал</strong></span><span class="sxs-lookup"><span data-stu-id="9b3e4-131"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="9b3e4-132">int</span><span class="sxs-lookup"><span data-stu-id="9b3e4-132">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9b3e4-133">Средний уровень дрожания в сети на основе статистики протокола RTCP.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-133">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9b3e4-134"><strong>життеринтерарривалмакс</strong></span><span class="sxs-lookup"><span data-stu-id="9b3e4-134"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="9b3e4-135">int</span><span class="sxs-lookup"><span data-stu-id="9b3e4-135">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9b3e4-136">Максимальная колебание сети во время сеанса видеосвязи.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-136">Maximum network jitter during the video session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9b3e4-137"><strong>Обработки</strong></span><span class="sxs-lookup"><span data-stu-id="9b3e4-137"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="9b3e4-138">int</span><span class="sxs-lookup"><span data-stu-id="9b3e4-138">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9b3e4-139">Время приема-передачи на основе статистики RTCP.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-139">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9b3e4-140"><strong>раундтрипмакс</strong></span><span class="sxs-lookup"><span data-stu-id="9b3e4-140"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="9b3e4-141">int</span><span class="sxs-lookup"><span data-stu-id="9b3e4-141">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9b3e4-142">Максимальное время кругового пути для видеопотока.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-142">Maximum round trip time for the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9b3e4-143"><strong>паккетлоссрате</strong></span><span class="sxs-lookup"><span data-stu-id="9b3e4-143"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="9b3e4-144">десятичное число (5, 4)</span><span class="sxs-lookup"><span data-stu-id="9b3e4-144">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9b3e4-145">Средний коэффициент потерь пакетов в течение вызова.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-145">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9b3e4-146"><strong>паккетлоссратемакс</strong></span><span class="sxs-lookup"><span data-stu-id="9b3e4-146"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="9b3e4-147">десятичное число (5, 4)</span><span class="sxs-lookup"><span data-stu-id="9b3e4-147">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9b3e4-148">Максимальная потеря пакетов, наблюдавшаяся в течение вызова.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-148">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9b3e4-149"><strong>паккетутилизатион</strong></span><span class="sxs-lookup"><span data-stu-id="9b3e4-149"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="9b3e4-150">int</span><span class="sxs-lookup"><span data-stu-id="9b3e4-150">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9b3e4-151">Количество пакетов для видеопотока (RTP).</span><span class="sxs-lookup"><span data-stu-id="9b3e4-151">Packet count for the video stream (Real Time Transport Protocol, RTP).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9b3e4-152"><strong>Самый полоса пропускания</strong></span><span class="sxs-lookup"><span data-stu-id="9b3e4-152"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="9b3e4-153">int</span><span class="sxs-lookup"><span data-stu-id="9b3e4-153">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9b3e4-154">Оценка пропускной способности для видеопотока.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-154">Bandwidth estimates for the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9b3e4-155"><strong>видеоресолутион</strong></span><span class="sxs-lookup"><span data-stu-id="9b3e4-155"><strong>VideoResolution</strong></span></span></p></td>
<td><p><span data-ttu-id="9b3e4-156">char (9)</span><span class="sxs-lookup"><span data-stu-id="9b3e4-156">char(9)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9b3e4-p103">Разрешение видео в пикселах (ширина умножается на высоту в пикселах). Указывается как строка.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-p103">Resolution of the video in pixels width multiplied by pixels height. Reported as a string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9b3e4-159"><strong>видеобитратеавг</strong></span><span class="sxs-lookup"><span data-stu-id="9b3e4-159"><strong>VideoBitRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="9b3e4-160">int</span><span class="sxs-lookup"><span data-stu-id="9b3e4-160">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9b3e4-161">Средняя скорость передачи видеопотока.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-161">Average bit rate of the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9b3e4-162"><strong>инбаундвидеофрамератеавг</strong></span><span class="sxs-lookup"><span data-stu-id="9b3e4-162"><strong>InboundVideoFrameRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="9b3e4-163">десятичное число (9, 4)</span><span class="sxs-lookup"><span data-stu-id="9b3e4-163">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9b3e4-164">Полученная частота видеокадров.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-164">The video frame rate received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9b3e4-165"><strong>аутбаундвидеофрамератеавг</strong></span><span class="sxs-lookup"><span data-stu-id="9b3e4-165"><strong>OutboundVideoFrameRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="9b3e4-166">десятичное число (9, 4)</span><span class="sxs-lookup"><span data-stu-id="9b3e4-166">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9b3e4-167">Частота отправки видеокадров.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-167">The video frame rate sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9b3e4-168"><strong>видеобитратемакс</strong></span><span class="sxs-lookup"><span data-stu-id="9b3e4-168"><strong>VideoBitRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="9b3e4-169">int</span><span class="sxs-lookup"><span data-stu-id="9b3e4-169">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9b3e4-170">Максимальная скорость видеопотока во время видеосеанса.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-170">The maximum video bit rate during the video session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9b3e4-171"><strong>видеофрамелоссрате</strong></span><span class="sxs-lookup"><span data-stu-id="9b3e4-171"><strong>VideoFrameLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="9b3e4-172">десятичное число (9, 4)</span><span class="sxs-lookup"><span data-stu-id="9b3e4-172">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9b3e4-173">Процент от общего числа потерянных видеокадров.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-173">The percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9b3e4-174"><strong>видеофек</strong></span><span class="sxs-lookup"><span data-stu-id="9b3e4-174"><strong>VideoFEC</strong></span></span></p></td>
<td><p><span data-ttu-id="9b3e4-175">Битовая</span><span class="sxs-lookup"><span data-stu-id="9b3e4-175">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9b3e4-176">Недоступно.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-176">Not available.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9b3e4-177"><strong>видеолокалфрамелоссперцентажеавг</strong></span><span class="sxs-lookup"><span data-stu-id="9b3e4-177"><strong>VideoLocalFrameLossPercentageAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="9b3e4-178">десятичное число (9, 4)</span><span class="sxs-lookup"><span data-stu-id="9b3e4-178">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9b3e4-179">Процент от общего числа потерянных видеокадров.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-179">The percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9b3e4-180"><strong>Цифкуалитиратио</strong></span><span class="sxs-lookup"><span data-stu-id="9b3e4-180"><strong>CIFQualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="9b3e4-181">tinyint</span><span class="sxs-lookup"><span data-stu-id="9b3e4-181">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9b3e4-182">Процентное соотношение вызова, находилось в стандартном разрешении формата обмена данными (CIF).</span><span class="sxs-lookup"><span data-stu-id="9b3e4-182">The percentage of the call that was at the Common Interchange Format (CIF) resolution.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9b3e4-183"><strong>вгакуалитиратио</strong></span><span class="sxs-lookup"><span data-stu-id="9b3e4-183"><strong>VGAQualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="9b3e4-184">tinyint</span><span class="sxs-lookup"><span data-stu-id="9b3e4-184">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9b3e4-185">Процентное соотношение вызовов, находилось при разрешении VGA.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-185">The percentage of the call that was at VGA resolution.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9b3e4-186"><strong>HD720QualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="9b3e4-186"><strong>HD720QualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="9b3e4-187">tinyint</span><span class="sxs-lookup"><span data-stu-id="9b3e4-187">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9b3e4-188">Процентное соотношение вызова, находилось по разрешению HD720.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-188">The percentage of the call that was at HD720 resolution.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9b3e4-189"><strong>нонедропратио</strong></span><span class="sxs-lookup"><span data-stu-id="9b3e4-189"><strong>NoneDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="9b3e4-190">tinyint</span><span class="sxs-lookup"><span data-stu-id="9b3e4-190">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9b3e4-191">Процент времени вызова без перетаскивания кадров.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-191">Percentage of call duration with no frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9b3e4-192"><strong>бдропратио</strong></span><span class="sxs-lookup"><span data-stu-id="9b3e4-192"><strong>BDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="9b3e4-193">tinyint</span><span class="sxs-lookup"><span data-stu-id="9b3e4-193">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9b3e4-194">Процент времени вызова с помощью параметра B Frame Drop.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-194">Percentage of call duration with B frame drop.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9b3e4-195"><strong>бпдропратио</strong></span><span class="sxs-lookup"><span data-stu-id="9b3e4-195"><strong>BPDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="9b3e4-196">tinyint</span><span class="sxs-lookup"><span data-stu-id="9b3e4-196">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9b3e4-197">Процент времени вызова с удалением кадра BP.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-197">Percentage of call duration with BP frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9b3e4-198"><strong>бпспдропратио</strong></span><span class="sxs-lookup"><span data-stu-id="9b3e4-198"><strong>BPSPDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="9b3e4-199">tinyint</span><span class="sxs-lookup"><span data-stu-id="9b3e4-199">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9b3e4-200">Процент времени вызова с БПСП Frame Drop.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-200">Percentage of call duration with BPSP frame drop.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9b3e4-201"><strong>бпспидропратио</strong></span><span class="sxs-lookup"><span data-stu-id="9b3e4-201"><strong>BPSPIDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="9b3e4-202">tinyint</span><span class="sxs-lookup"><span data-stu-id="9b3e4-202">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9b3e4-203">Процент времени вызова с БПСПИ Frame Drop.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-203">Percentage of call duration with BPSPI frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9b3e4-204"><strong>Получение</strong></span><span class="sxs-lookup"><span data-stu-id="9b3e4-204"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="9b3e4-205">Битовая</span><span class="sxs-lookup"><span data-stu-id="9b3e4-205">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9b3e4-206">Получение потоковых данных на стороне получателя.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-206">Stream data on receiver side is received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9b3e4-207"><strong>Прав</strong></span><span class="sxs-lookup"><span data-stu-id="9b3e4-207"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="9b3e4-208">Битовая</span><span class="sxs-lookup"><span data-stu-id="9b3e4-208">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9b3e4-209">Получение потоковых данных на стороне отправителя.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-209">Stream data on sender side is received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9b3e4-210"><strong>сендерискаллерпаи</strong></span><span class="sxs-lookup"><span data-stu-id="9b3e4-210"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="9b3e4-211">Битовая</span><span class="sxs-lookup"><span data-stu-id="9b3e4-211">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9b3e4-212">1 означает направление потока от вызывающего абонента вызываемому абоненту.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-212">1 means the stream direction is from the caller to callee.</span></span></p>
<p><span data-ttu-id="9b3e4-213">0 означает направление потока от вызываемого абонента вызывающему абоненту.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-213">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9b3e4-214"><strong>лоссконжестионперцент</strong></span><span class="sxs-lookup"><span data-stu-id="9b3e4-214"><strong>LossCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="9b3e4-215">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="9b3e4-215">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9b3e4-216">Указывает процент времени, в течение которого вызов находился в состоянии перегрузки потерь.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-216">Indicates the percentage of the time when the call was in a loss congestion state.</span></span></p>
<p><span data-ttu-id="9b3e4-217">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-217">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9b3e4-218"><strong>делайконжестионперцент</strong></span><span class="sxs-lookup"><span data-stu-id="9b3e4-218"><strong>DelayCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="9b3e4-219">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="9b3e4-219">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9b3e4-220">Указывает процент вызова, в течение которого перегрузка была вызвана задержкой появления сетевых пакетов.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-220">Indicates the percentage of the call during which congestion was caused by the delayed arrival of network packets.</span></span></p>
<p><span data-ttu-id="9b3e4-221">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-221">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9b3e4-222"><strong>контентиондетектедперцент</strong></span><span class="sxs-lookup"><span data-stu-id="9b3e4-222"><strong>ContentionDetectedPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="9b3e4-223">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="9b3e4-223">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9b3e4-224">Указывает процент времени, в течение которого вызов конкурирует за ресурсы сети.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-224">Indicates the percentage of the time when the call was competing for network resources.</span></span></p>
<p><span data-ttu-id="9b3e4-225">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-225">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9b3e4-226"><strong>бандвидсестмин</strong></span><span class="sxs-lookup"><span data-stu-id="9b3e4-226"><strong>BandwidthEstMin</strong></span></span></p></td>
<td><p><span data-ttu-id="9b3e4-227">int</span><span class="sxs-lookup"><span data-stu-id="9b3e4-227">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9b3e4-228">Минимальная сумма оценки пропускной способности, измеренной во время вызова.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-228">Minimum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="9b3e4-229">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-229">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9b3e4-230"><strong>бандвидсестмакс</strong></span><span class="sxs-lookup"><span data-stu-id="9b3e4-230"><strong>BandwidthEstMax</strong></span></span></p></td>
<td><p><span data-ttu-id="9b3e4-231">int</span><span class="sxs-lookup"><span data-stu-id="9b3e4-231">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9b3e4-232">Максимальный объем оценки пропускной способности, измеренной во время вызова.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-232">Maximum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="9b3e4-233">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-233">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9b3e4-234"><strong>бандвидсестстддев</strong></span><span class="sxs-lookup"><span data-stu-id="9b3e4-234"><strong>BandwidthEstStdDev</strong></span></span></p></td>
<td><p><span data-ttu-id="9b3e4-235">int</span><span class="sxs-lookup"><span data-stu-id="9b3e4-235">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9b3e4-236">Стандартное отклонение оценки пропускной способности, измеренной во время вызова.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-236">Standard deviation of the bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="9b3e4-237">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-237">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9b3e4-238"><strong>бандвидсеставже</strong></span><span class="sxs-lookup"><span data-stu-id="9b3e4-238"><strong>BandwidthEstAvge</strong></span></span></p></td>
<td><p><span data-ttu-id="9b3e4-239">int</span><span class="sxs-lookup"><span data-stu-id="9b3e4-239">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9b3e4-240">Средняя величина оценки пропускной способности, измеренной во время вызова.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-240">Average amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="9b3e4-241">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-241">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9b3e4-242"><strong>ловбандвидсформултивиев</strong></span><span class="sxs-lookup"><span data-stu-id="9b3e4-242"><strong>LowBandwidthForMultiview</strong></span></span></p></td>
<td><p><span data-ttu-id="9b3e4-243">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="9b3e4-243">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9b3e4-244">Процент вызова, в котором конечная точка определила, что сетевое подключение не поддерживает просмотр видео.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-244">Percentage of the call where the endpoint determined that the network connection could not support multiview video.</span></span></p>
<p><span data-ttu-id="9b3e4-245">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-245">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9b3e4-246"><strong>релативеоневайтотал</strong></span><span class="sxs-lookup"><span data-stu-id="9b3e4-246"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="9b3e4-247">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="9b3e4-247">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9b3e4-p104">Общая величина односторонней задержки. Относительная односторонняя задержка измеряет задержку между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-p104">Total amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="9b3e4-250">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-250">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9b3e4-251"><strong>релативеоневайавераже</strong></span><span class="sxs-lookup"><span data-stu-id="9b3e4-251"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="9b3e4-252">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="9b3e4-252">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9b3e4-p105">Средняя величина односторонней задержки. Относительная односторонняя задержка измеряет задержку между клиентом и сервером</span><span class="sxs-lookup"><span data-stu-id="9b3e4-p105">Average amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="9b3e4-255">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-255">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9b3e4-256"><strong>релативеоневаймакс</strong></span><span class="sxs-lookup"><span data-stu-id="9b3e4-256"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="9b3e4-257">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="9b3e4-257">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9b3e4-p106">Максимальная величина односторонней задержки. Относительная односторонняя задержка измеряет задержку между клиентом и сервером</span><span class="sxs-lookup"><span data-stu-id="9b3e4-p106">Maximum amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="9b3e4-260">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-260">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9b3e4-261"><strong>релативеоневайбурстоккурренцес</strong></span><span class="sxs-lookup"><span data-stu-id="9b3e4-261"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="9b3e4-262">int</span><span class="sxs-lookup"><span data-stu-id="9b3e4-262">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9b3e4-p107">Общее число повторов пакетов в одну сторону. "Пакетная" передача представляет собой передачу, при которой данные передаются посредством случайных пакетов, а не в виде устойчивого потока. С помощью этой метрики измеряется поток данных между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-p107">Total one-way burst occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="9b3e4-266">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-266">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9b3e4-267"><strong>релативеоневайбурстденсити</strong></span><span class="sxs-lookup"><span data-stu-id="9b3e4-267"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="9b3e4-268">int</span><span class="sxs-lookup"><span data-stu-id="9b3e4-268">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9b3e4-p108">Общая плотность пакетов в одну сторону. "Пакетная" передача представляет собой передачу, при которой данные передаются посредством случайных пакетов, а не в виде устойчивого потока. С помощью этой метрики измеряется поток данных между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-p108">Total one-way burst density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="9b3e4-272">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-272">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9b3e4-273"><strong>релативеоневайбурстдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="9b3e4-273"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="9b3e4-274">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="9b3e4-274">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9b3e4-p109">Общая длительность пакетов в одну сторону. "Пакетная" передача представляет собой передачу, при которой данные передаются посредством случайных пакетов, а не в виде устойчивого потока. С помощью этой метрики измеряется поток данных между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-p109">Total one-way burst duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="9b3e4-278">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-278">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9b3e4-279"><strong>релативеоневайгапоккурренцес</strong></span><span class="sxs-lookup"><span data-stu-id="9b3e4-279"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="9b3e4-280">int</span><span class="sxs-lookup"><span data-stu-id="9b3e4-280">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9b3e4-p110">Общее число повторов разрывов в одну сторону. "Пакетная" передача представляет собой передачу, при которой данные передаются посредством случайных пакетов, а не в виде устойчивого потока; разрывы указывают задержку между этими пакетами. С помощью данной метрики измеряется поток данных между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-p110">Total one-way gap occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="9b3e4-284">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-284">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9b3e4-285"><strong>релативеоневайгапденсити</strong></span><span class="sxs-lookup"><span data-stu-id="9b3e4-285"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="9b3e4-286">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="9b3e4-286">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9b3e4-p111">Общая плотность разрывов в одну сторону. "Пакетная" передача представляет собой передачу, при которой данные передаются посредством случайных пакетов, а не в виде устойчивого потока; разрывы указывают задержку между этими пакетами. С помощью данной метрики измеряется поток данных между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-p111">Total one-way gap density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="9b3e4-290">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-290">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9b3e4-291"><strong>релативеоневайгапдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="9b3e4-291"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="9b3e4-292">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="9b3e4-292">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9b3e4-p112">Общая длительность разрывов в одну сторону. "Пакетная" передача представляет собой передачу, при которой данные передаются посредством случайных пакетов, а не в виде устойчивого потока; разрывы указывают задержку между этими пакетами. С помощью данной метрики измеряется поток данных между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-p112">Total one-way gap duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="9b3e4-296">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-296">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9b3e4-297"><strong>видеопаккетлоссрате</strong></span><span class="sxs-lookup"><span data-stu-id="9b3e4-297"><strong>VideoPacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="9b3e4-298">десятичное число (9, 4)</span><span class="sxs-lookup"><span data-stu-id="9b3e4-298">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9b3e4-299">Скорость потери видеопакетов.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-299">Rate at which video packets were lost.</span></span></p>
<p><span data-ttu-id="9b3e4-300">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-300">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9b3e4-301"><strong>видеоаллокатебвавг</strong></span><span class="sxs-lookup"><span data-stu-id="9b3e4-301"><strong>VideoAllocateBWAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="9b3e4-302">int</span><span class="sxs-lookup"><span data-stu-id="9b3e4-302">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9b3e4-303">Средний объем выделенной полосы пропускания для видео.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-303">Average amount of bandwidth allocated for video.</span></span></p>
<p><span data-ttu-id="9b3e4-304">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-304">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9b3e4-305"><strong>сендкодектипес</strong></span><span class="sxs-lookup"><span data-stu-id="9b3e4-305"><strong>SendCodecTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="9b3e4-306">smallint</span><span class="sxs-lookup"><span data-stu-id="9b3e4-306">smallint</span></span></p></td>
<td><p><span data-ttu-id="9b3e4-307">Правительства</span><span class="sxs-lookup"><span data-stu-id="9b3e4-307">Foreign</span></span></p></td>
<td><p><span data-ttu-id="9b3e4-308">Тип видеокодеков, используемых отправителем.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-308">Type of video codecs used by the sender.</span></span> <span data-ttu-id="9b3e4-309">Дополнительные сведения см. <a href="lync-server-2013-codecdescription-table.md">в таблице кодекдескриптион в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="9b3e4-309">See the <a href="lync-server-2013-codecdescription-table.md">CodecDescription table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="9b3e4-310">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-310">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9b3e4-311"><strong>сендресолутионвидс</strong></span><span class="sxs-lookup"><span data-stu-id="9b3e4-311"><strong>SendResolutionWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="9b3e4-312">int</span><span class="sxs-lookup"><span data-stu-id="9b3e4-312">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9b3e4-313">Ширина разрешения, используемая отправителем.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-313">Resolution width used by the sender.</span></span></p>
<p><span data-ttu-id="9b3e4-314">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-314">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9b3e4-315"><strong>сендресолутионхеигхт</strong></span><span class="sxs-lookup"><span data-stu-id="9b3e4-315"><strong>SendResolutionHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="9b3e4-316">int</span><span class="sxs-lookup"><span data-stu-id="9b3e4-316">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9b3e4-317">Высота разрешения, используемая отправителем.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-317">Resolution height used by the sender.</span></span></p>
<p><span data-ttu-id="9b3e4-318">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-318">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9b3e4-319"><strong>сендфрамератеавераже</strong></span><span class="sxs-lookup"><span data-stu-id="9b3e4-319"><strong>SendFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="9b3e4-320">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="9b3e4-320">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9b3e4-321">Средняя скорость передачи видеокадров, используемая отправителем.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-321">Average video frame rate transmission used by the sender.</span></span></p>
<p><span data-ttu-id="9b3e4-322">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-322">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9b3e4-323"><strong>сендбитратемаксимум</strong></span><span class="sxs-lookup"><span data-stu-id="9b3e4-323"><strong>SendBitRateMaximum</strong></span></span></p></td>
<td><p><span data-ttu-id="9b3e4-324">int</span><span class="sxs-lookup"><span data-stu-id="9b3e4-324">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9b3e4-325">Максимальная скорость передачи для отправителя.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-325">Maximum bit rate for the sender.</span></span></p>
<p><span data-ttu-id="9b3e4-326">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-326">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9b3e4-327"><strong>сендбитратеавераже</strong></span><span class="sxs-lookup"><span data-stu-id="9b3e4-327"><strong>SendBitRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="9b3e4-328">int</span><span class="sxs-lookup"><span data-stu-id="9b3e4-328">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9b3e4-329">Средняя скорость потока для отправителя.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-329">Average bit rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9b3e4-330"><strong>сендвидеостреамсмакс</strong></span><span class="sxs-lookup"><span data-stu-id="9b3e4-330"><strong>SendVideoStreamsMax</strong></span></span></p></td>
<td><p><span data-ttu-id="9b3e4-331">int</span><span class="sxs-lookup"><span data-stu-id="9b3e4-331">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9b3e4-332">Максимальное число видеопотоков, используемых отправителем.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-332">Maximum number of video streams used by the sender.</span></span></p>
<p><span data-ttu-id="9b3e4-333">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-333">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9b3e4-334"><strong>реквкодектипес</strong></span><span class="sxs-lookup"><span data-stu-id="9b3e4-334"><strong>RecvCodecTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="9b3e4-335">smallint</span><span class="sxs-lookup"><span data-stu-id="9b3e4-335">smallint</span></span></p></td>
<td><p><span data-ttu-id="9b3e4-336">Правительства</span><span class="sxs-lookup"><span data-stu-id="9b3e4-336">Foreign</span></span></p></td>
<td><p><span data-ttu-id="9b3e4-337">Видеокоды, используемые получателем.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-337">Video codes used by the receiver.</span></span> <span data-ttu-id="9b3e4-338">Дополнительные сведения см. <a href="lync-server-2013-codecdescription-table.md">в таблице кодекдескриптион в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="9b3e4-338">See the <a href="lync-server-2013-codecdescription-table.md">CodecDescription table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="9b3e4-339">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-339">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9b3e4-340"><strong>реквресолутионвидс</strong></span><span class="sxs-lookup"><span data-stu-id="9b3e4-340"><strong>RecvResolutionWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="9b3e4-341">int</span><span class="sxs-lookup"><span data-stu-id="9b3e4-341">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9b3e4-342">Ширина разрешения, используемая получателем.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-342">Resolution width used by the receiver.</span></span></p>
<p><span data-ttu-id="9b3e4-343">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-343">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9b3e4-344"><strong>реквресолутионхеигхт</strong></span><span class="sxs-lookup"><span data-stu-id="9b3e4-344"><strong>RecvResolutionHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="9b3e4-345">int</span><span class="sxs-lookup"><span data-stu-id="9b3e4-345">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9b3e4-346">Высота разрешения, используемая получателем.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-346">Resolution height used by the receiver.</span></span></p>
<p><span data-ttu-id="9b3e4-347">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-347">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9b3e4-348"><strong>реквфрамератеавераже</strong></span><span class="sxs-lookup"><span data-stu-id="9b3e4-348"><strong>RecvFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="9b3e4-349">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="9b3e4-349">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9b3e4-350">Средняя частота видеокадров, используемая получателем.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-350">Average video frame rate used by the receiver.</span></span></p>
<p><span data-ttu-id="9b3e4-351">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-351">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9b3e4-352"><strong>реквбитратемаксимум</strong></span><span class="sxs-lookup"><span data-stu-id="9b3e4-352"><strong>RecvBitRateMaximum</strong></span></span></p></td>
<td><p><span data-ttu-id="9b3e4-353">int</span><span class="sxs-lookup"><span data-stu-id="9b3e4-353">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9b3e4-354">Максимальная скорость потока для получателя.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-354">Maximum bit rate for the receiver.</span></span></p>
<p><span data-ttu-id="9b3e4-355">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-355">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9b3e4-356"><strong>реквбитратеавераже</strong></span><span class="sxs-lookup"><span data-stu-id="9b3e4-356"><strong>RecvBitRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="9b3e4-357">int</span><span class="sxs-lookup"><span data-stu-id="9b3e4-357">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9b3e4-358">Средняя скорость потока для получателя.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-358">Average bit rate for the receiver.</span></span></p>
<p><span data-ttu-id="9b3e4-359">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-359">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9b3e4-360"><strong>рекввидеостреамсмакс</strong></span><span class="sxs-lookup"><span data-stu-id="9b3e4-360"><strong>RecvVideoStreamsMax</strong></span></span></p></td>
<td><p><span data-ttu-id="9b3e4-361">int</span><span class="sxs-lookup"><span data-stu-id="9b3e4-361">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9b3e4-362">Максимальное число видеопотоков для приемника.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-362">Maximum video streams for the receiver.</span></span></p>
<p><span data-ttu-id="9b3e4-363">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-363">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9b3e4-364"><strong>рекввидеостреамсмин</strong></span><span class="sxs-lookup"><span data-stu-id="9b3e4-364"><strong>RecvVideoStreamsMin</strong></span></span></p></td>
<td><p><span data-ttu-id="9b3e4-365">int</span><span class="sxs-lookup"><span data-stu-id="9b3e4-365">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9b3e4-366">Минимальное количество видеопотоков для приемника.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-366">Minimum video streams for the receiver.</span></span></p>
<p><span data-ttu-id="9b3e4-367">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-367">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9b3e4-368"><strong>рекввидеостреамсмоде</strong></span><span class="sxs-lookup"><span data-stu-id="9b3e4-368"><strong>RecvVideoStreamsMode</strong></span></span></p></td>
<td><p><span data-ttu-id="9b3e4-369">int</span><span class="sxs-lookup"><span data-stu-id="9b3e4-369">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9b3e4-370">Видеорежим (например, коллекция или один поток) для приемника.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-370">Video mode (for example, gallery or single stream) for the receiver.</span></span></p>
<p><span data-ttu-id="9b3e4-371">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-371">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9b3e4-372"><strong>видеопостфекплр</strong></span><span class="sxs-lookup"><span data-stu-id="9b3e4-372"><strong>VideoPostFECPLR</strong></span></span></p></td>
<td><p><span data-ttu-id="9b3e4-373">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="9b3e4-373">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9b3e4-374">Скорость потери пакетов после применения коррекции ошибок переадресации.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-374">Packet loss rate after forward error correction has been applied.</span></span></p>
<p><span data-ttu-id="9b3e4-375">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-375">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9b3e4-376"><strong>динамиккапабилитиперцент</strong></span><span class="sxs-lookup"><span data-stu-id="9b3e4-376"><strong>DynamicCapabilityPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="9b3e4-377">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="9b3e4-377">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9b3e4-378">Процент времени, в течение которого был активен флаг динамической возможности.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-378">Percentage of time that the dynamic capability flag was active.</span></span></p>
<p><span data-ttu-id="9b3e4-379">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-379">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9b3e4-380"><strong>ресолутионмин</strong></span><span class="sxs-lookup"><span data-stu-id="9b3e4-380"><strong>ResolutionMin</strong></span></span></p></td>
<td><p><span data-ttu-id="9b3e4-381">char (9)</span><span class="sxs-lookup"><span data-stu-id="9b3e4-381">char(9)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9b3e4-382">Минимальное разрешение, измеренное во время вызова.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-382">Minimum resolution measured during the call.</span></span></p>
<p><span data-ttu-id="9b3e4-383">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-383">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9b3e4-384"><strong>ловбитратекаллперцент</strong></span><span class="sxs-lookup"><span data-stu-id="9b3e4-384"><strong>LowBitRateCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="9b3e4-385">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="9b3e4-385">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9b3e4-386">Процент вызова ниже минимального порогового значения скорости (70 килобит в секунду).</span><span class="sxs-lookup"><span data-stu-id="9b3e4-386">Percentage of the call below the low bit rate threshold (70 kilobits per second).</span></span></p>
<p><span data-ttu-id="9b3e4-387">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-387">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9b3e4-388"><strong>ловфрамератекаллперцент</strong></span><span class="sxs-lookup"><span data-stu-id="9b3e4-388"><strong>LowFrameRateCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="9b3e4-389">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="9b3e4-389">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9b3e4-390">Процент вызовов ниже минимального порога частоты кадров (7,5 кадров в секунду, входящий трафик).</span><span class="sxs-lookup"><span data-stu-id="9b3e4-390">Percentage of the call below the low frame rate threshold (7.5 frames per second, inbound).</span></span></p>
<p><span data-ttu-id="9b3e4-391">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-391">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9b3e4-392"><strong>ловресолутионкаллперцент</strong></span><span class="sxs-lookup"><span data-stu-id="9b3e4-392"><strong>LowResolutionCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="9b3e4-393">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="9b3e4-393">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9b3e4-394">Процент звонков, произошедших с наименьшим разрешением.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-394">Percentage of the call that occurred at the lowest resolution.</span></span></p>
<p><span data-ttu-id="9b3e4-395">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-395">This column was introduced in Microsoft Lync Server 2013.</span></span></p>
<p><span data-ttu-id="9b3e4-396">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-396">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9b3e4-397"><strong>дуратионсекондс</strong></span><span class="sxs-lookup"><span data-stu-id="9b3e4-397"><strong>DurationSeconds</strong></span></span></p></td>
<td><p><span data-ttu-id="9b3e4-398">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="9b3e4-398">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9b3e4-399">Продолжительность звонка в секундах.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-399">Length of the call in seconds.</span></span></p>
<p><span data-ttu-id="9b3e4-400">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-400">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9b3e4-401"><strong>исаггрегатеддата</strong></span><span class="sxs-lookup"><span data-stu-id="9b3e4-401"><strong>IsAggregatedData</strong></span></span></p></td>
<td><p><span data-ttu-id="9b3e4-402">Битовая</span><span class="sxs-lookup"><span data-stu-id="9b3e4-402">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9b3e4-403">Указывает, были ли данные объединены из нескольких вызовов.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-403">Indicates whether the data has been aggregated from multiple calls.</span></span></p>
<p><span data-ttu-id="9b3e4-404">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-404">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

