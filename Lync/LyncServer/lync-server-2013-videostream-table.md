---
title: 'Lync Server 2013: таблица таблица videostream'
description: 'Lync Server 2013: таблица таблица videostream.'
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
ms.openlocfilehash: 0d741478e1f6290685181bff471f143e41ce9ca1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567995"
---
# <a name="videostream-table-in-lync-server-2013"></a><span data-ttu-id="77edb-103">Таблица Таблица videostream в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="77edb-103">VideoStream table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="77edb-104">_**Последнее изменение темы:** 2013-12-13_</span><span class="sxs-lookup"><span data-stu-id="77edb-104">_**Topic Last Modified:** 2013-12-13_</span></span>

<span data-ttu-id="77edb-105">Каждая запись представляет один видеопоток.</span><span class="sxs-lookup"><span data-stu-id="77edb-105">Each record represents one video stream.</span></span> <span data-ttu-id="77edb-106">Одна линия видеопотока обычно содержит два видеопотока.</span><span class="sxs-lookup"><span data-stu-id="77edb-106">One video media line usually contains two video streams.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="77edb-107"><strong>Column</strong></span><span class="sxs-lookup"><span data-stu-id="77edb-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="77edb-108"><strong>Тип данных</strong></span><span class="sxs-lookup"><span data-stu-id="77edb-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="77edb-109"><strong>Ключ или индекс</strong></span><span class="sxs-lookup"><span data-stu-id="77edb-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="77edb-110"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="77edb-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="77edb-111"><strong>конференцедатетиме</strong></span><span class="sxs-lookup"><span data-stu-id="77edb-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="77edb-112">datetime</span><span class="sxs-lookup"><span data-stu-id="77edb-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="77edb-113">Primary</span><span class="sxs-lookup"><span data-stu-id="77edb-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="77edb-114">Ссылка из <a href="lync-server-2013-medialine-table.md">таблицы MediaLine в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="77edb-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77edb-115"><strong>сессионсек</strong></span><span class="sxs-lookup"><span data-stu-id="77edb-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="77edb-116">int</span><span class="sxs-lookup"><span data-stu-id="77edb-116">int</span></span></p></td>
<td><p><span data-ttu-id="77edb-117">Primary</span><span class="sxs-lookup"><span data-stu-id="77edb-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="77edb-118">R, на который ссылается <a href="lync-server-2013-medialine-table.md">Таблица MediaLine в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="77edb-118">R Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77edb-119"><strong>медиалинелабел</strong></span><span class="sxs-lookup"><span data-stu-id="77edb-119"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="77edb-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="77edb-120">tinyint</span></span></p></td>
<td><p><span data-ttu-id="77edb-121">Primary</span><span class="sxs-lookup"><span data-stu-id="77edb-121">Primary</span></span></p></td>
<td><p><span data-ttu-id="77edb-122">Ссылка из <a href="lync-server-2013-medialine-table.md">таблицы MediaLine в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="77edb-122">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77edb-123"><strong>стреамид</strong></span><span class="sxs-lookup"><span data-stu-id="77edb-123"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="77edb-124">int</span><span class="sxs-lookup"><span data-stu-id="77edb-124">int</span></span></p></td>
<td><p><span data-ttu-id="77edb-125">Primary</span><span class="sxs-lookup"><span data-stu-id="77edb-125">Primary</span></span></p></td>
<td><p><span data-ttu-id="77edb-126">Уникальный идентификатор в линии мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="77edb-126">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77edb-127"><strong>видеопайлоаддескриптион</strong></span><span class="sxs-lookup"><span data-stu-id="77edb-127"><strong>VideoPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="77edb-128">smallint</span><span class="sxs-lookup"><span data-stu-id="77edb-128">smallint</span></span></p></td>
<td><p><span data-ttu-id="77edb-129">Внешний, основной</span><span class="sxs-lookup"><span data-stu-id="77edb-129">Foreign, Primary</span></span></p></td>
<td><p><span data-ttu-id="77edb-130">Описание полезных данных.</span><span class="sxs-lookup"><span data-stu-id="77edb-130">Payload description.</span></span> <span data-ttu-id="77edb-131">Дополнительные сведения см. <a href="lync-server-2013-payloaddescription-table.md">в таблице таблица payloaddescription в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="77edb-131">See the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77edb-132"><strong>життеринтерарривал</strong></span><span class="sxs-lookup"><span data-stu-id="77edb-132"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="77edb-133">int</span><span class="sxs-lookup"><span data-stu-id="77edb-133">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="77edb-134">Средний уровень дрожания в сети на основе статистики протокола RTCP.</span><span class="sxs-lookup"><span data-stu-id="77edb-134">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77edb-135"><strong>життеринтерарривалмакс</strong></span><span class="sxs-lookup"><span data-stu-id="77edb-135"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="77edb-136">int</span><span class="sxs-lookup"><span data-stu-id="77edb-136">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="77edb-137">Максимальная колебание сети во время сеанса видеосвязи.</span><span class="sxs-lookup"><span data-stu-id="77edb-137">Maximum network jitter during the video session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77edb-138"><strong>Обработки</strong></span><span class="sxs-lookup"><span data-stu-id="77edb-138"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="77edb-139">int</span><span class="sxs-lookup"><span data-stu-id="77edb-139">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="77edb-140">Время приема-передачи на основе статистики RTCP.</span><span class="sxs-lookup"><span data-stu-id="77edb-140">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77edb-141"><strong>раундтрипмакс</strong></span><span class="sxs-lookup"><span data-stu-id="77edb-141"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="77edb-142">int</span><span class="sxs-lookup"><span data-stu-id="77edb-142">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="77edb-143">Максимальное время кругового пути для видеопотока.</span><span class="sxs-lookup"><span data-stu-id="77edb-143">Maximum round trip time for the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77edb-144"><strong>паккетлоссрате</strong></span><span class="sxs-lookup"><span data-stu-id="77edb-144"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="77edb-145">десятичное число (5, 4)</span><span class="sxs-lookup"><span data-stu-id="77edb-145">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="77edb-146">Средний коэффициент потерь пакетов в течение вызова.</span><span class="sxs-lookup"><span data-stu-id="77edb-146">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77edb-147"><strong>паккетлоссратемакс</strong></span><span class="sxs-lookup"><span data-stu-id="77edb-147"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="77edb-148">десятичное число (5, 4)</span><span class="sxs-lookup"><span data-stu-id="77edb-148">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="77edb-149">Максимальная потеря пакетов, наблюдавшаяся в течение вызова.</span><span class="sxs-lookup"><span data-stu-id="77edb-149">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77edb-150"><strong>паккетутилизатион</strong></span><span class="sxs-lookup"><span data-stu-id="77edb-150"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="77edb-151">int</span><span class="sxs-lookup"><span data-stu-id="77edb-151">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="77edb-152">Количество пакетов для видеопотока (RTP).</span><span class="sxs-lookup"><span data-stu-id="77edb-152">Packet count for the video stream (Real Time Transport Protocol, RTP).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77edb-153"><strong>Самый полоса пропускания</strong></span><span class="sxs-lookup"><span data-stu-id="77edb-153"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="77edb-154">int</span><span class="sxs-lookup"><span data-stu-id="77edb-154">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="77edb-155">Оценка пропускной способности для видеопотока.</span><span class="sxs-lookup"><span data-stu-id="77edb-155">Bandwidth estimates for the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77edb-156"><strong>видеоресолутион</strong></span><span class="sxs-lookup"><span data-stu-id="77edb-156"><strong>VideoResolution</strong></span></span></p></td>
<td><p><span data-ttu-id="77edb-157">char (9)</span><span class="sxs-lookup"><span data-stu-id="77edb-157">char(9)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="77edb-p103">Разрешение видео в пикселах (ширина умножается на высоту в пикселах). Указывается как строка.</span><span class="sxs-lookup"><span data-stu-id="77edb-p103">Resolution of the video in pixels width multiplied by pixels height. Reported as a string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77edb-160"><strong>видеобитратеавг</strong></span><span class="sxs-lookup"><span data-stu-id="77edb-160"><strong>VideoBitRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="77edb-161">int</span><span class="sxs-lookup"><span data-stu-id="77edb-161">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="77edb-162">Средняя скорость передачи видеопотока.</span><span class="sxs-lookup"><span data-stu-id="77edb-162">Average bit rate of the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77edb-163"><strong>инбаундвидеофрамератеавг</strong></span><span class="sxs-lookup"><span data-stu-id="77edb-163"><strong>InboundVideoFrameRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="77edb-164">десятичное число (9, 4)</span><span class="sxs-lookup"><span data-stu-id="77edb-164">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="77edb-165">Полученная частота видеокадров.</span><span class="sxs-lookup"><span data-stu-id="77edb-165">The video frame rate received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77edb-166"><strong>аутбаундвидеофрамератеавг</strong></span><span class="sxs-lookup"><span data-stu-id="77edb-166"><strong>OutboundVideoFrameRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="77edb-167">десятичное число (9, 4)</span><span class="sxs-lookup"><span data-stu-id="77edb-167">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="77edb-168">Частота отправки видеокадров.</span><span class="sxs-lookup"><span data-stu-id="77edb-168">The video frame rate sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77edb-169"><strong>видеобитратемакс</strong></span><span class="sxs-lookup"><span data-stu-id="77edb-169"><strong>VideoBitRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="77edb-170">int</span><span class="sxs-lookup"><span data-stu-id="77edb-170">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="77edb-171">Максимальная скорость видеопотока во время видеосеанса.</span><span class="sxs-lookup"><span data-stu-id="77edb-171">The maximum video bit rate during the video session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77edb-172"><strong>видеофрамелоссрате</strong></span><span class="sxs-lookup"><span data-stu-id="77edb-172"><strong>VideoFrameLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="77edb-173">десятичное число (9, 4)</span><span class="sxs-lookup"><span data-stu-id="77edb-173">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="77edb-174">Процент от общего числа потерянных видеокадров.</span><span class="sxs-lookup"><span data-stu-id="77edb-174">The percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77edb-175"><strong>видеофек</strong></span><span class="sxs-lookup"><span data-stu-id="77edb-175"><strong>VideoFEC</strong></span></span></p></td>
<td><p><span data-ttu-id="77edb-176">Битовая</span><span class="sxs-lookup"><span data-stu-id="77edb-176">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="77edb-177">Недоступно.</span><span class="sxs-lookup"><span data-stu-id="77edb-177">Not available.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77edb-178"><strong>видеолокалфрамелоссперцентажеавг</strong></span><span class="sxs-lookup"><span data-stu-id="77edb-178"><strong>VideoLocalFrameLossPercentageAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="77edb-179">десятичное число (9, 4)</span><span class="sxs-lookup"><span data-stu-id="77edb-179">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="77edb-180">Процент от общего числа потерянных видеокадров.</span><span class="sxs-lookup"><span data-stu-id="77edb-180">The percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77edb-181"><strong>Цифкуалитиратио</strong></span><span class="sxs-lookup"><span data-stu-id="77edb-181"><strong>CIFQualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="77edb-182">tinyint</span><span class="sxs-lookup"><span data-stu-id="77edb-182">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="77edb-183">Процентное соотношение вызова, находилось в стандартном разрешении формата обмена данными (CIF).</span><span class="sxs-lookup"><span data-stu-id="77edb-183">The percentage of the call that was at the Common Interchange Format (CIF) resolution.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77edb-184"><strong>вгакуалитиратио</strong></span><span class="sxs-lookup"><span data-stu-id="77edb-184"><strong>VGAQualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="77edb-185">tinyint</span><span class="sxs-lookup"><span data-stu-id="77edb-185">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="77edb-186">Процентное соотношение вызовов, находилось при разрешении VGA.</span><span class="sxs-lookup"><span data-stu-id="77edb-186">The percentage of the call that was at VGA resolution.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77edb-187"><strong>HD720QualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="77edb-187"><strong>HD720QualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="77edb-188">tinyint</span><span class="sxs-lookup"><span data-stu-id="77edb-188">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="77edb-189">Процентное соотношение вызова, находилось по разрешению HD720.</span><span class="sxs-lookup"><span data-stu-id="77edb-189">The percentage of the call that was at HD720 resolution.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77edb-190"><strong>нонедропратио</strong></span><span class="sxs-lookup"><span data-stu-id="77edb-190"><strong>NoneDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="77edb-191">tinyint</span><span class="sxs-lookup"><span data-stu-id="77edb-191">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="77edb-192">Процент времени вызова без перетаскивания кадров.</span><span class="sxs-lookup"><span data-stu-id="77edb-192">Percentage of call duration with no frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77edb-193"><strong>бдропратио</strong></span><span class="sxs-lookup"><span data-stu-id="77edb-193"><strong>BDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="77edb-194">tinyint</span><span class="sxs-lookup"><span data-stu-id="77edb-194">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="77edb-195">Процент времени вызова с помощью параметра B Frame Drop.</span><span class="sxs-lookup"><span data-stu-id="77edb-195">Percentage of call duration with B frame drop.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77edb-196"><strong>бпдропратио</strong></span><span class="sxs-lookup"><span data-stu-id="77edb-196"><strong>BPDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="77edb-197">tinyint</span><span class="sxs-lookup"><span data-stu-id="77edb-197">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="77edb-198">Процент времени вызова с удалением кадра BP.</span><span class="sxs-lookup"><span data-stu-id="77edb-198">Percentage of call duration with BP frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77edb-199"><strong>бпспдропратио</strong></span><span class="sxs-lookup"><span data-stu-id="77edb-199"><strong>BPSPDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="77edb-200">tinyint</span><span class="sxs-lookup"><span data-stu-id="77edb-200">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="77edb-201">Процент времени вызова с БПСП Frame Drop.</span><span class="sxs-lookup"><span data-stu-id="77edb-201">Percentage of call duration with BPSP frame drop.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77edb-202"><strong>бпспидропратио</strong></span><span class="sxs-lookup"><span data-stu-id="77edb-202"><strong>BPSPIDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="77edb-203">tinyint</span><span class="sxs-lookup"><span data-stu-id="77edb-203">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="77edb-204">Процент времени вызова с БПСПИ Frame Drop.</span><span class="sxs-lookup"><span data-stu-id="77edb-204">Percentage of call duration with BPSPI frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77edb-205"><strong>Получение</strong></span><span class="sxs-lookup"><span data-stu-id="77edb-205"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="77edb-206">Битовая</span><span class="sxs-lookup"><span data-stu-id="77edb-206">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="77edb-207">Получение потоковых данных на стороне получателя.</span><span class="sxs-lookup"><span data-stu-id="77edb-207">Stream data on receiver side is received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77edb-208"><strong>Прав</strong></span><span class="sxs-lookup"><span data-stu-id="77edb-208"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="77edb-209">Битовая</span><span class="sxs-lookup"><span data-stu-id="77edb-209">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="77edb-210">Получение потоковых данных на стороне отправителя.</span><span class="sxs-lookup"><span data-stu-id="77edb-210">Stream data on sender side is received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77edb-211"><strong>сендерискаллерпаи</strong></span><span class="sxs-lookup"><span data-stu-id="77edb-211"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="77edb-212">Битовая</span><span class="sxs-lookup"><span data-stu-id="77edb-212">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="77edb-213">1 означает направление потока от вызывающего абонента вызываемому абоненту.</span><span class="sxs-lookup"><span data-stu-id="77edb-213">1 means the stream direction is from the caller to callee.</span></span></p>
<p><span data-ttu-id="77edb-214">0 означает направление потока от вызываемого абонента вызывающему абоненту.</span><span class="sxs-lookup"><span data-stu-id="77edb-214">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77edb-215"><strong>лоссконжестионперцент</strong></span><span class="sxs-lookup"><span data-stu-id="77edb-215"><strong>LossCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="77edb-216">float</span><span class="sxs-lookup"><span data-stu-id="77edb-216">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="77edb-217">Указывает процент времени, в течение которого вызов находился в состоянии перегрузки потерь.</span><span class="sxs-lookup"><span data-stu-id="77edb-217">Indicates the percentage of the time when the call was in a loss congestion state.</span></span></p>
<p><span data-ttu-id="77edb-218">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="77edb-218">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77edb-219"><strong>делайконжестионперцент</strong></span><span class="sxs-lookup"><span data-stu-id="77edb-219"><strong>DelayCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="77edb-220">float</span><span class="sxs-lookup"><span data-stu-id="77edb-220">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="77edb-221">Указывает процент вызова, в течение которого перегрузка была вызвана задержкой появления сетевых пакетов.</span><span class="sxs-lookup"><span data-stu-id="77edb-221">Indicates the percentage of the call during which congestion was caused by the delayed arrival of network packets.</span></span></p>
<p><span data-ttu-id="77edb-222">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="77edb-222">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77edb-223"><strong>контентиондетектедперцент</strong></span><span class="sxs-lookup"><span data-stu-id="77edb-223"><strong>ContentionDetectedPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="77edb-224">float</span><span class="sxs-lookup"><span data-stu-id="77edb-224">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="77edb-225">Указывает процент времени, в течение которого вызов конкурирует за ресурсы сети.</span><span class="sxs-lookup"><span data-stu-id="77edb-225">Indicates the percentage of the time when the call was competing for network resources.</span></span></p>
<p><span data-ttu-id="77edb-226">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="77edb-226">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77edb-227"><strong>бандвидсестмин</strong></span><span class="sxs-lookup"><span data-stu-id="77edb-227"><strong>BandwidthEstMin</strong></span></span></p></td>
<td><p><span data-ttu-id="77edb-228">int</span><span class="sxs-lookup"><span data-stu-id="77edb-228">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="77edb-229">Минимальная сумма оценки пропускной способности, измеренной во время вызова.</span><span class="sxs-lookup"><span data-stu-id="77edb-229">Minimum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="77edb-230">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="77edb-230">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77edb-231"><strong>бандвидсестмакс</strong></span><span class="sxs-lookup"><span data-stu-id="77edb-231"><strong>BandwidthEstMax</strong></span></span></p></td>
<td><p><span data-ttu-id="77edb-232">int</span><span class="sxs-lookup"><span data-stu-id="77edb-232">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="77edb-233">Максимальный объем оценки пропускной способности, измеренной во время вызова.</span><span class="sxs-lookup"><span data-stu-id="77edb-233">Maximum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="77edb-234">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="77edb-234">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77edb-235"><strong>бандвидсестстддев</strong></span><span class="sxs-lookup"><span data-stu-id="77edb-235"><strong>BandwidthEstStdDev</strong></span></span></p></td>
<td><p><span data-ttu-id="77edb-236">int</span><span class="sxs-lookup"><span data-stu-id="77edb-236">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="77edb-237">Стандартное отклонение оценки пропускной способности, измеренной во время вызова.</span><span class="sxs-lookup"><span data-stu-id="77edb-237">Standard deviation of the bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="77edb-238">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="77edb-238">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77edb-239"><strong>бандвидсеставже</strong></span><span class="sxs-lookup"><span data-stu-id="77edb-239"><strong>BandwidthEstAvge</strong></span></span></p></td>
<td><p><span data-ttu-id="77edb-240">int</span><span class="sxs-lookup"><span data-stu-id="77edb-240">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="77edb-241">Средняя величина оценки пропускной способности, измеренной во время вызова.</span><span class="sxs-lookup"><span data-stu-id="77edb-241">Average amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="77edb-242">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="77edb-242">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77edb-243"><strong>ловбандвидсформултивиев</strong></span><span class="sxs-lookup"><span data-stu-id="77edb-243"><strong>LowBandwidthForMultiview</strong></span></span></p></td>
<td><p><span data-ttu-id="77edb-244">float</span><span class="sxs-lookup"><span data-stu-id="77edb-244">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="77edb-245">Процент вызова, в котором конечная точка определила, что сетевое подключение не поддерживает просмотр видео.</span><span class="sxs-lookup"><span data-stu-id="77edb-245">Percentage of the call where the endpoint determined that the network connection could not support multiview video.</span></span></p>
<p><span data-ttu-id="77edb-246">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="77edb-246">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77edb-247"><strong>релативеоневайтотал</strong></span><span class="sxs-lookup"><span data-stu-id="77edb-247"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="77edb-248">float</span><span class="sxs-lookup"><span data-stu-id="77edb-248">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="77edb-p104">Общая величина односторонней задержки. Относительная односторонняя задержка измеряет задержку между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="77edb-p104">Total amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="77edb-251">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="77edb-251">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77edb-252"><strong>релативеоневайавераже</strong></span><span class="sxs-lookup"><span data-stu-id="77edb-252"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="77edb-253">float</span><span class="sxs-lookup"><span data-stu-id="77edb-253">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="77edb-p105">Средняя величина односторонней задержки. Относительная односторонняя задержка измеряет задержку между клиентом и сервером</span><span class="sxs-lookup"><span data-stu-id="77edb-p105">Average amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="77edb-256">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="77edb-256">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77edb-257"><strong>релативеоневаймакс</strong></span><span class="sxs-lookup"><span data-stu-id="77edb-257"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="77edb-258">float</span><span class="sxs-lookup"><span data-stu-id="77edb-258">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="77edb-p106">Максимальная величина односторонней задержки. Относительная односторонняя задержка измеряет задержку между клиентом и сервером</span><span class="sxs-lookup"><span data-stu-id="77edb-p106">Maximum amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="77edb-261">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="77edb-261">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77edb-262"><strong>релативеоневайбурстоккурренцес</strong></span><span class="sxs-lookup"><span data-stu-id="77edb-262"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="77edb-263">int</span><span class="sxs-lookup"><span data-stu-id="77edb-263">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="77edb-p107">Общее число повторов пакетов в одну сторону. "Пакетная" передача представляет собой передачу, при которой данные передаются посредством случайных пакетов, а не в виде устойчивого потока. С помощью этой метрики измеряется поток данных между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="77edb-p107">Total one-way burst occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="77edb-267">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="77edb-267">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77edb-268"><strong>релативеоневайбурстденсити</strong></span><span class="sxs-lookup"><span data-stu-id="77edb-268"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="77edb-269">int</span><span class="sxs-lookup"><span data-stu-id="77edb-269">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="77edb-p108">Общая плотность пакетов в одну сторону. "Пакетная" передача представляет собой передачу, при которой данные передаются посредством случайных пакетов, а не в виде устойчивого потока. С помощью этой метрики измеряется поток данных между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="77edb-p108">Total one-way burst density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="77edb-273">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="77edb-273">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77edb-274"><strong>релативеоневайбурстдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="77edb-274"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="77edb-275">float</span><span class="sxs-lookup"><span data-stu-id="77edb-275">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="77edb-p109">Общая длительность пакетов в одну сторону. "Пакетная" передача представляет собой передачу, при которой данные передаются посредством случайных пакетов, а не в виде устойчивого потока. С помощью этой метрики измеряется поток данных между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="77edb-p109">Total one-way burst duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="77edb-279">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="77edb-279">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77edb-280"><strong>релативеоневайгапоккурренцес</strong></span><span class="sxs-lookup"><span data-stu-id="77edb-280"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="77edb-281">int</span><span class="sxs-lookup"><span data-stu-id="77edb-281">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="77edb-p110">Общее число повторов разрывов в одну сторону. "Пакетная" передача представляет собой передачу, при которой данные передаются посредством случайных пакетов, а не в виде устойчивого потока; разрывы указывают задержку между этими пакетами. С помощью данной метрики измеряется поток данных между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="77edb-p110">Total one-way gap occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="77edb-285">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="77edb-285">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77edb-286"><strong>релативеоневайгапденсити</strong></span><span class="sxs-lookup"><span data-stu-id="77edb-286"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="77edb-287">float</span><span class="sxs-lookup"><span data-stu-id="77edb-287">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="77edb-p111">Общая плотность разрывов в одну сторону. "Пакетная" передача представляет собой передачу, при которой данные передаются посредством случайных пакетов, а не в виде устойчивого потока; разрывы указывают задержку между этими пакетами. С помощью данной метрики измеряется поток данных между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="77edb-p111">Total one-way gap density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="77edb-291">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="77edb-291">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77edb-292"><strong>релативеоневайгапдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="77edb-292"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="77edb-293">float</span><span class="sxs-lookup"><span data-stu-id="77edb-293">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="77edb-p112">Общая длительность разрывов в одну сторону. "Пакетная" передача представляет собой передачу, при которой данные передаются посредством случайных пакетов, а не в виде устойчивого потока; разрывы указывают задержку между этими пакетами. С помощью данной метрики измеряется поток данных между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="77edb-p112">Total one-way gap duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="77edb-297">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="77edb-297">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77edb-298"><strong>видеопаккетлоссрате</strong></span><span class="sxs-lookup"><span data-stu-id="77edb-298"><strong>VideoPacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="77edb-299">десятичное число (9, 4)</span><span class="sxs-lookup"><span data-stu-id="77edb-299">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="77edb-300">Скорость потери видеопакетов.</span><span class="sxs-lookup"><span data-stu-id="77edb-300">Rate at which video packets were lost.</span></span></p>
<p><span data-ttu-id="77edb-301">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="77edb-301">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77edb-302"><strong>видеоаллокатебвавг</strong></span><span class="sxs-lookup"><span data-stu-id="77edb-302"><strong>VideoAllocateBWAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="77edb-303">int</span><span class="sxs-lookup"><span data-stu-id="77edb-303">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="77edb-304">Средний объем выделенной полосы пропускания для видео.</span><span class="sxs-lookup"><span data-stu-id="77edb-304">Average amount of bandwidth allocated for video.</span></span></p>
<p><span data-ttu-id="77edb-305">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="77edb-305">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77edb-306"><strong>сендкодектипес</strong></span><span class="sxs-lookup"><span data-stu-id="77edb-306"><strong>SendCodecTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="77edb-307">smallint</span><span class="sxs-lookup"><span data-stu-id="77edb-307">smallint</span></span></p></td>
<td><p><span data-ttu-id="77edb-308">Правительства</span><span class="sxs-lookup"><span data-stu-id="77edb-308">Foreign</span></span></p></td>
<td><p><span data-ttu-id="77edb-309">Тип видеокодеков, используемых отправителем.</span><span class="sxs-lookup"><span data-stu-id="77edb-309">Type of video codecs used by the sender.</span></span> <span data-ttu-id="77edb-310">Дополнительные сведения см. <a href="lync-server-2013-codecdescription-table.md">в таблице кодекдескриптион в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="77edb-310">See the <a href="lync-server-2013-codecdescription-table.md">CodecDescription table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="77edb-311">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="77edb-311">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77edb-312"><strong>сендресолутионвидс</strong></span><span class="sxs-lookup"><span data-stu-id="77edb-312"><strong>SendResolutionWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="77edb-313">int</span><span class="sxs-lookup"><span data-stu-id="77edb-313">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="77edb-314">Ширина разрешения, используемая отправителем.</span><span class="sxs-lookup"><span data-stu-id="77edb-314">Resolution width used by the sender.</span></span></p>
<p><span data-ttu-id="77edb-315">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="77edb-315">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77edb-316"><strong>сендресолутионхеигхт</strong></span><span class="sxs-lookup"><span data-stu-id="77edb-316"><strong>SendResolutionHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="77edb-317">int</span><span class="sxs-lookup"><span data-stu-id="77edb-317">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="77edb-318">Высота разрешения, используемая отправителем.</span><span class="sxs-lookup"><span data-stu-id="77edb-318">Resolution height used by the sender.</span></span></p>
<p><span data-ttu-id="77edb-319">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="77edb-319">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77edb-320"><strong>сендфрамератеавераже</strong></span><span class="sxs-lookup"><span data-stu-id="77edb-320"><strong>SendFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="77edb-321">float</span><span class="sxs-lookup"><span data-stu-id="77edb-321">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="77edb-322">Средняя скорость передачи видеокадров, используемая отправителем.</span><span class="sxs-lookup"><span data-stu-id="77edb-322">Average video frame rate transmission used by the sender.</span></span></p>
<p><span data-ttu-id="77edb-323">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="77edb-323">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77edb-324"><strong>сендбитратемаксимум</strong></span><span class="sxs-lookup"><span data-stu-id="77edb-324"><strong>SendBitRateMaximum</strong></span></span></p></td>
<td><p><span data-ttu-id="77edb-325">int</span><span class="sxs-lookup"><span data-stu-id="77edb-325">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="77edb-326">Максимальная скорость передачи для отправителя.</span><span class="sxs-lookup"><span data-stu-id="77edb-326">Maximum bit rate for the sender.</span></span></p>
<p><span data-ttu-id="77edb-327">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="77edb-327">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77edb-328"><strong>сендбитратеавераже</strong></span><span class="sxs-lookup"><span data-stu-id="77edb-328"><strong>SendBitRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="77edb-329">int</span><span class="sxs-lookup"><span data-stu-id="77edb-329">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="77edb-330">Средняя скорость потока для отправителя.</span><span class="sxs-lookup"><span data-stu-id="77edb-330">Average bit rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77edb-331"><strong>сендвидеостреамсмакс</strong></span><span class="sxs-lookup"><span data-stu-id="77edb-331"><strong>SendVideoStreamsMax</strong></span></span></p></td>
<td><p><span data-ttu-id="77edb-332">int</span><span class="sxs-lookup"><span data-stu-id="77edb-332">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="77edb-333">Максимальное число видеопотоков, используемых отправителем.</span><span class="sxs-lookup"><span data-stu-id="77edb-333">Maximum number of video streams used by the sender.</span></span></p>
<p><span data-ttu-id="77edb-334">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="77edb-334">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77edb-335"><strong>реквкодектипес</strong></span><span class="sxs-lookup"><span data-stu-id="77edb-335"><strong>RecvCodecTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="77edb-336">smallint</span><span class="sxs-lookup"><span data-stu-id="77edb-336">smallint</span></span></p></td>
<td><p><span data-ttu-id="77edb-337">Правительства</span><span class="sxs-lookup"><span data-stu-id="77edb-337">Foreign</span></span></p></td>
<td><p><span data-ttu-id="77edb-338">Видеокоды, используемые получателем.</span><span class="sxs-lookup"><span data-stu-id="77edb-338">Video codes used by the receiver.</span></span> <span data-ttu-id="77edb-339">Дополнительные сведения см. <a href="lync-server-2013-codecdescription-table.md">в таблице кодекдескриптион в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="77edb-339">See the <a href="lync-server-2013-codecdescription-table.md">CodecDescription table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="77edb-340">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="77edb-340">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77edb-341"><strong>реквресолутионвидс</strong></span><span class="sxs-lookup"><span data-stu-id="77edb-341"><strong>RecvResolutionWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="77edb-342">int</span><span class="sxs-lookup"><span data-stu-id="77edb-342">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="77edb-343">Ширина разрешения, используемая получателем.</span><span class="sxs-lookup"><span data-stu-id="77edb-343">Resolution width used by the receiver.</span></span></p>
<p><span data-ttu-id="77edb-344">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="77edb-344">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77edb-345"><strong>реквресолутионхеигхт</strong></span><span class="sxs-lookup"><span data-stu-id="77edb-345"><strong>RecvResolutionHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="77edb-346">int</span><span class="sxs-lookup"><span data-stu-id="77edb-346">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="77edb-347">Высота разрешения, используемая получателем.</span><span class="sxs-lookup"><span data-stu-id="77edb-347">Resolution height used by the receiver.</span></span></p>
<p><span data-ttu-id="77edb-348">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="77edb-348">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77edb-349"><strong>реквфрамератеавераже</strong></span><span class="sxs-lookup"><span data-stu-id="77edb-349"><strong>RecvFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="77edb-350">float</span><span class="sxs-lookup"><span data-stu-id="77edb-350">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="77edb-351">Средняя частота видеокадров, используемая получателем.</span><span class="sxs-lookup"><span data-stu-id="77edb-351">Average video frame rate used by the receiver.</span></span></p>
<p><span data-ttu-id="77edb-352">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="77edb-352">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77edb-353"><strong>реквбитратемаксимум</strong></span><span class="sxs-lookup"><span data-stu-id="77edb-353"><strong>RecvBitRateMaximum</strong></span></span></p></td>
<td><p><span data-ttu-id="77edb-354">int</span><span class="sxs-lookup"><span data-stu-id="77edb-354">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="77edb-355">Максимальная скорость потока для получателя.</span><span class="sxs-lookup"><span data-stu-id="77edb-355">Maximum bit rate for the receiver.</span></span></p>
<p><span data-ttu-id="77edb-356">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="77edb-356">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77edb-357"><strong>реквбитратеавераже</strong></span><span class="sxs-lookup"><span data-stu-id="77edb-357"><strong>RecvBitRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="77edb-358">int</span><span class="sxs-lookup"><span data-stu-id="77edb-358">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="77edb-359">Средняя скорость потока для получателя.</span><span class="sxs-lookup"><span data-stu-id="77edb-359">Average bit rate for the receiver.</span></span></p>
<p><span data-ttu-id="77edb-360">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="77edb-360">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77edb-361"><strong>рекввидеостреамсмакс</strong></span><span class="sxs-lookup"><span data-stu-id="77edb-361"><strong>RecvVideoStreamsMax</strong></span></span></p></td>
<td><p><span data-ttu-id="77edb-362">int</span><span class="sxs-lookup"><span data-stu-id="77edb-362">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="77edb-363">Максимальное число видеопотоков для приемника.</span><span class="sxs-lookup"><span data-stu-id="77edb-363">Maximum video streams for the receiver.</span></span></p>
<p><span data-ttu-id="77edb-364">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="77edb-364">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77edb-365"><strong>рекввидеостреамсмин</strong></span><span class="sxs-lookup"><span data-stu-id="77edb-365"><strong>RecvVideoStreamsMin</strong></span></span></p></td>
<td><p><span data-ttu-id="77edb-366">int</span><span class="sxs-lookup"><span data-stu-id="77edb-366">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="77edb-367">Минимальное количество видеопотоков для приемника.</span><span class="sxs-lookup"><span data-stu-id="77edb-367">Minimum video streams for the receiver.</span></span></p>
<p><span data-ttu-id="77edb-368">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="77edb-368">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77edb-369"><strong>рекввидеостреамсмоде</strong></span><span class="sxs-lookup"><span data-stu-id="77edb-369"><strong>RecvVideoStreamsMode</strong></span></span></p></td>
<td><p><span data-ttu-id="77edb-370">int</span><span class="sxs-lookup"><span data-stu-id="77edb-370">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="77edb-371">Видеорежим (например, коллекция или один поток) для приемника.</span><span class="sxs-lookup"><span data-stu-id="77edb-371">Video mode (for example, gallery or single stream) for the receiver.</span></span></p>
<p><span data-ttu-id="77edb-372">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="77edb-372">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77edb-373"><strong>видеопостфекплр</strong></span><span class="sxs-lookup"><span data-stu-id="77edb-373"><strong>VideoPostFECPLR</strong></span></span></p></td>
<td><p><span data-ttu-id="77edb-374">float</span><span class="sxs-lookup"><span data-stu-id="77edb-374">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="77edb-375">Скорость потери пакетов после применения коррекции ошибок переадресации.</span><span class="sxs-lookup"><span data-stu-id="77edb-375">Packet loss rate after forward error correction has been applied.</span></span></p>
<p><span data-ttu-id="77edb-376">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="77edb-376">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77edb-377"><strong>динамиккапабилитиперцент</strong></span><span class="sxs-lookup"><span data-stu-id="77edb-377"><strong>DynamicCapabilityPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="77edb-378">float</span><span class="sxs-lookup"><span data-stu-id="77edb-378">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="77edb-379">Процент времени, в течение которого был активен флаг динамической возможности.</span><span class="sxs-lookup"><span data-stu-id="77edb-379">Percentage of time that the dynamic capability flag was active.</span></span></p>
<p><span data-ttu-id="77edb-380">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="77edb-380">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77edb-381"><strong>ресолутионмин</strong></span><span class="sxs-lookup"><span data-stu-id="77edb-381"><strong>ResolutionMin</strong></span></span></p></td>
<td><p><span data-ttu-id="77edb-382">char (9)</span><span class="sxs-lookup"><span data-stu-id="77edb-382">char(9)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="77edb-383">Минимальное разрешение, измеренное во время вызова.</span><span class="sxs-lookup"><span data-stu-id="77edb-383">Minimum resolution measured during the call.</span></span></p>
<p><span data-ttu-id="77edb-384">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="77edb-384">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77edb-385"><strong>ловбитратекаллперцент</strong></span><span class="sxs-lookup"><span data-stu-id="77edb-385"><strong>LowBitRateCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="77edb-386">float</span><span class="sxs-lookup"><span data-stu-id="77edb-386">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="77edb-387">Процент вызова ниже минимального порогового значения скорости (70 килобит в секунду).</span><span class="sxs-lookup"><span data-stu-id="77edb-387">Percentage of the call below the low bit rate threshold (70 kilobits per second).</span></span></p>
<p><span data-ttu-id="77edb-388">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="77edb-388">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77edb-389"><strong>ловфрамератекаллперцент</strong></span><span class="sxs-lookup"><span data-stu-id="77edb-389"><strong>LowFrameRateCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="77edb-390">float</span><span class="sxs-lookup"><span data-stu-id="77edb-390">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="77edb-391">Процент вызовов ниже минимального порога частоты кадров (7,5 кадров в секунду, входящий трафик).</span><span class="sxs-lookup"><span data-stu-id="77edb-391">Percentage of the call below the low frame rate threshold (7.5 frames per second, inbound).</span></span></p>
<p><span data-ttu-id="77edb-392">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="77edb-392">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77edb-393"><strong>ловресолутионкаллперцент</strong></span><span class="sxs-lookup"><span data-stu-id="77edb-393"><strong>LowResolutionCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="77edb-394">float</span><span class="sxs-lookup"><span data-stu-id="77edb-394">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="77edb-395">Процент звонков, произошедших с наименьшим разрешением.</span><span class="sxs-lookup"><span data-stu-id="77edb-395">Percentage of the call that occurred at the lowest resolution.</span></span></p>
<p><span data-ttu-id="77edb-396">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="77edb-396">This column was introduced in Microsoft Lync Server 2013.</span></span></p>
<p><span data-ttu-id="77edb-397">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="77edb-397">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77edb-398"><strong>дуратионсекондс</strong></span><span class="sxs-lookup"><span data-stu-id="77edb-398"><strong>DurationSeconds</strong></span></span></p></td>
<td><p><span data-ttu-id="77edb-399">float</span><span class="sxs-lookup"><span data-stu-id="77edb-399">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="77edb-400">Продолжительность звонка в секундах.</span><span class="sxs-lookup"><span data-stu-id="77edb-400">Length of the call in seconds.</span></span></p>
<p><span data-ttu-id="77edb-401">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="77edb-401">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77edb-402"><strong>исаггрегатеддата</strong></span><span class="sxs-lookup"><span data-stu-id="77edb-402"><strong>IsAggregatedData</strong></span></span></p></td>
<td><p><span data-ttu-id="77edb-403">Битовая</span><span class="sxs-lookup"><span data-stu-id="77edb-403">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="77edb-404">Указывает, были ли данные объединены из нескольких вызовов.</span><span class="sxs-lookup"><span data-stu-id="77edb-404">Indicates whether the data has been aggregated from multiple calls.</span></span></p>
<p><span data-ttu-id="77edb-405">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="77edb-405">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

