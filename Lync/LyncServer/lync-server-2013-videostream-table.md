---
title: 'Lync Server 2013: таблица VideoStream'
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
ms.openlocfilehash: 674d013faca3b43db04d2c5b4802103def83dbd8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757923"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="videostream-table-in-lync-server-2013"></a><span data-ttu-id="f0fad-102">Таблица VideoStream в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f0fad-102">VideoStream table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f0fad-103">_**Тема последнего изменения:** 2013-12-13_</span><span class="sxs-lookup"><span data-stu-id="f0fad-103">_**Topic Last Modified:** 2013-12-13_</span></span>

<span data-ttu-id="f0fad-104">Каждая запись представляет один поток видео.</span><span class="sxs-lookup"><span data-stu-id="f0fad-104">Each record represents one video stream.</span></span> <span data-ttu-id="f0fad-105">Одна линия видеофайла обычно состоит из двух видеопотоков.</span><span class="sxs-lookup"><span data-stu-id="f0fad-105">One video media line usually contains two video streams.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f0fad-106"><strong>Столбец</strong></span><span class="sxs-lookup"><span data-stu-id="f0fad-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="f0fad-107"><strong>Тип данных</strong></span><span class="sxs-lookup"><span data-stu-id="f0fad-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="f0fad-108"><strong>Ключ/индекс</strong></span><span class="sxs-lookup"><span data-stu-id="f0fad-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="f0fad-109"><strong>Сведения</strong></span><span class="sxs-lookup"><span data-stu-id="f0fad-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f0fad-110"><strong>конференцедатетиме</strong></span><span class="sxs-lookup"><span data-stu-id="f0fad-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f0fad-111">datetime</span><span class="sxs-lookup"><span data-stu-id="f0fad-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="f0fad-112">Primary</span><span class="sxs-lookup"><span data-stu-id="f0fad-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="f0fad-113">На которую ссылается <a href="lync-server-2013-medialine-table.md">Таблица медиалине в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="f0fad-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0fad-114"><strong>сессионсек</strong></span><span class="sxs-lookup"><span data-stu-id="f0fad-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="f0fad-115">целое</span><span class="sxs-lookup"><span data-stu-id="f0fad-115">int</span></span></p></td>
<td><p><span data-ttu-id="f0fad-116">Primary</span><span class="sxs-lookup"><span data-stu-id="f0fad-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="f0fad-117">R, на который ссылается <a href="lync-server-2013-medialine-table.md">Таблица медиалине в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="f0fad-117">R Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0fad-118"><strong>медиалинелабел</strong></span><span class="sxs-lookup"><span data-stu-id="f0fad-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="f0fad-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="f0fad-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="f0fad-120">Primary</span><span class="sxs-lookup"><span data-stu-id="f0fad-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="f0fad-121">На которую ссылается <a href="lync-server-2013-medialine-table.md">Таблица медиалине в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="f0fad-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0fad-122"><strong>стреамид</strong></span><span class="sxs-lookup"><span data-stu-id="f0fad-122"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="f0fad-123">целое</span><span class="sxs-lookup"><span data-stu-id="f0fad-123">int</span></span></p></td>
<td><p><span data-ttu-id="f0fad-124">Primary</span><span class="sxs-lookup"><span data-stu-id="f0fad-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="f0fad-125">Уникальный идентификатор в строке мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="f0fad-125">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0fad-126"><strong>видеопайлоаддескриптион</strong></span><span class="sxs-lookup"><span data-stu-id="f0fad-126"><strong>VideoPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="f0fad-127">smallint</span><span class="sxs-lookup"><span data-stu-id="f0fad-127">smallint</span></span></p></td>
<td><p><span data-ttu-id="f0fad-128">Внешний, основной</span><span class="sxs-lookup"><span data-stu-id="f0fad-128">Foreign, Primary</span></span></p></td>
<td><p><span data-ttu-id="f0fad-129">Описание полезных данных.</span><span class="sxs-lookup"><span data-stu-id="f0fad-129">Payload description.</span></span> <span data-ttu-id="f0fad-130">Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-payloaddescription-table.md">таблицей пайлоаддескриптион в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f0fad-130">See the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0fad-131"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="f0fad-131"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="f0fad-132">целое</span><span class="sxs-lookup"><span data-stu-id="f0fad-132">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f0fad-133">Средняя колебание сети из статистики протокола управления временем в реальном времени (РТКП).</span><span class="sxs-lookup"><span data-stu-id="f0fad-133">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0fad-134"><strong>життеринтерарривалмакс</strong></span><span class="sxs-lookup"><span data-stu-id="f0fad-134"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="f0fad-135">целое</span><span class="sxs-lookup"><span data-stu-id="f0fad-135">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f0fad-136">Максимальная колебание сети во время видеосеанса.</span><span class="sxs-lookup"><span data-stu-id="f0fad-136">Maximum network jitter during the video session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0fad-137"><strong>RoundTrip</strong></span><span class="sxs-lookup"><span data-stu-id="f0fad-137"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="f0fad-138">целое</span><span class="sxs-lookup"><span data-stu-id="f0fad-138">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f0fad-139">Время кругового приема из статистики РТКП.</span><span class="sxs-lookup"><span data-stu-id="f0fad-139">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0fad-140"><strong>раундтрипмакс</strong></span><span class="sxs-lookup"><span data-stu-id="f0fad-140"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="f0fad-141">целое</span><span class="sxs-lookup"><span data-stu-id="f0fad-141">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f0fad-142">Максимальное время кругового сеанса для видеопотока.</span><span class="sxs-lookup"><span data-stu-id="f0fad-142">Maximum round trip time for the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0fad-143"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="f0fad-143"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="f0fad-144">десятичное число (5; 4)</span><span class="sxs-lookup"><span data-stu-id="f0fad-144">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f0fad-145">Средняя скорость потерь пакетов во время звонка.</span><span class="sxs-lookup"><span data-stu-id="f0fad-145">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0fad-146"><strong>паккетлоссратемакс</strong></span><span class="sxs-lookup"><span data-stu-id="f0fad-146"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="f0fad-147">десятичное число (5; 4)</span><span class="sxs-lookup"><span data-stu-id="f0fad-147">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f0fad-148">Максимальное количество потерь пакетов, замеченное во время звонка.</span><span class="sxs-lookup"><span data-stu-id="f0fad-148">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0fad-149"><strong>паккетутилизатион</strong></span><span class="sxs-lookup"><span data-stu-id="f0fad-149"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="f0fad-150">целое</span><span class="sxs-lookup"><span data-stu-id="f0fad-150">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f0fad-151">Число пакетов для видеопотока (транспортный протокол в реальном времени).</span><span class="sxs-lookup"><span data-stu-id="f0fad-151">Packet count for the video stream (Real Time Transport Protocol, RTP).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0fad-152"><strong>Самый пропускная способность</strong></span><span class="sxs-lookup"><span data-stu-id="f0fad-152"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="f0fad-153">целое</span><span class="sxs-lookup"><span data-stu-id="f0fad-153">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f0fad-154">Оценка пропускной способности для видеопотока.</span><span class="sxs-lookup"><span data-stu-id="f0fad-154">Bandwidth estimates for the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0fad-155"><strong>видеоресолутион</strong></span><span class="sxs-lookup"><span data-stu-id="f0fad-155"><strong>VideoResolution</strong></span></span></p></td>
<td><p><span data-ttu-id="f0fad-156">char (9)</span><span class="sxs-lookup"><span data-stu-id="f0fad-156">char(9)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f0fad-157">Разрешение видео в пикселях, умноженное на высоту в пикселях.</span><span class="sxs-lookup"><span data-stu-id="f0fad-157">Resolution of the video in pixels width multiplied by pixels height.</span></span> <span data-ttu-id="f0fad-158">Отображается в виде строки.</span><span class="sxs-lookup"><span data-stu-id="f0fad-158">Reported as a string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0fad-159"><strong>видеобитратеавг</strong></span><span class="sxs-lookup"><span data-stu-id="f0fad-159"><strong>VideoBitRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="f0fad-160">целое</span><span class="sxs-lookup"><span data-stu-id="f0fad-160">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f0fad-161">Средняя скорость потока видео.</span><span class="sxs-lookup"><span data-stu-id="f0fad-161">Average bit rate of the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0fad-162"><strong>инбаундвидеофрамератеавг</strong></span><span class="sxs-lookup"><span data-stu-id="f0fad-162"><strong>InboundVideoFrameRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="f0fad-163">десятичное число (9; 4)</span><span class="sxs-lookup"><span data-stu-id="f0fad-163">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f0fad-164">Полученная частота кадров видео.</span><span class="sxs-lookup"><span data-stu-id="f0fad-164">The video frame rate received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0fad-165"><strong>аутбаундвидеофрамератеавг</strong></span><span class="sxs-lookup"><span data-stu-id="f0fad-165"><strong>OutboundVideoFrameRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="f0fad-166">десятичное число (9; 4)</span><span class="sxs-lookup"><span data-stu-id="f0fad-166">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f0fad-167">Частота отправки кадров видео.</span><span class="sxs-lookup"><span data-stu-id="f0fad-167">The video frame rate sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0fad-168"><strong>видеобитратемакс</strong></span><span class="sxs-lookup"><span data-stu-id="f0fad-168"><strong>VideoBitRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="f0fad-169">целое</span><span class="sxs-lookup"><span data-stu-id="f0fad-169">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f0fad-170">Максимальная скорость видеосигнала во время видеосеанса.</span><span class="sxs-lookup"><span data-stu-id="f0fad-170">The maximum video bit rate during the video session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0fad-171"><strong>видеофрамелоссрате</strong></span><span class="sxs-lookup"><span data-stu-id="f0fad-171"><strong>VideoFrameLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="f0fad-172">десятичное число (9; 4)</span><span class="sxs-lookup"><span data-stu-id="f0fad-172">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f0fad-173">Процент от общего числа потерянных кадров видео.</span><span class="sxs-lookup"><span data-stu-id="f0fad-173">The percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0fad-174"><strong>видеофек</strong></span><span class="sxs-lookup"><span data-stu-id="f0fad-174"><strong>VideoFEC</strong></span></span></p></td>
<td><p><span data-ttu-id="f0fad-175">бит</span><span class="sxs-lookup"><span data-stu-id="f0fad-175">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f0fad-176">Недоступно.</span><span class="sxs-lookup"><span data-stu-id="f0fad-176">Not available.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0fad-177"><strong>VideoLocalFrameLossPercentageAvg</strong></span><span class="sxs-lookup"><span data-stu-id="f0fad-177"><strong>VideoLocalFrameLossPercentageAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="f0fad-178">десятичное число (9; 4)</span><span class="sxs-lookup"><span data-stu-id="f0fad-178">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f0fad-179">Процент от общего числа потерянных кадров видео.</span><span class="sxs-lookup"><span data-stu-id="f0fad-179">The percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0fad-180"><strong>Цифкуалитиратио</strong></span><span class="sxs-lookup"><span data-stu-id="f0fad-180"><strong>CIFQualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="f0fad-181">tinyint</span><span class="sxs-lookup"><span data-stu-id="f0fad-181">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f0fad-182">Процент звонка, находился в разрешении общего формата обмена (циф).</span><span class="sxs-lookup"><span data-stu-id="f0fad-182">The percentage of the call that was at the Common Interchange Format (CIF) resolution.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0fad-183"><strong>вгакуалитиратио</strong></span><span class="sxs-lookup"><span data-stu-id="f0fad-183"><strong>VGAQualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="f0fad-184">tinyint</span><span class="sxs-lookup"><span data-stu-id="f0fad-184">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f0fad-185">Процент звонка, находился в режиме разрешающей способности VGA.</span><span class="sxs-lookup"><span data-stu-id="f0fad-185">The percentage of the call that was at VGA resolution.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0fad-186"><strong>HD720QualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="f0fad-186"><strong>HD720QualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="f0fad-187">tinyint</span><span class="sxs-lookup"><span data-stu-id="f0fad-187">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f0fad-188">Процентное соотношение вызова, которое было установлено по адресу HD720.</span><span class="sxs-lookup"><span data-stu-id="f0fad-188">The percentage of the call that was at HD720 resolution.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0fad-189"><strong>нонедропратио</strong></span><span class="sxs-lookup"><span data-stu-id="f0fad-189"><strong>NoneDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="f0fad-190">tinyint</span><span class="sxs-lookup"><span data-stu-id="f0fad-190">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f0fad-191">Процент продолжительности звонка без удаления кадров.</span><span class="sxs-lookup"><span data-stu-id="f0fad-191">Percentage of call duration with no frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0fad-192"><strong>бдропратио</strong></span><span class="sxs-lookup"><span data-stu-id="f0fad-192"><strong>BDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="f0fad-193">tinyint</span><span class="sxs-lookup"><span data-stu-id="f0fad-193">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f0fad-194">Процент продолжительности звонка с помощью функции B Frame Drop.</span><span class="sxs-lookup"><span data-stu-id="f0fad-194">Percentage of call duration with B frame drop.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0fad-195"><strong>бпдропратио</strong></span><span class="sxs-lookup"><span data-stu-id="f0fad-195"><strong>BPDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="f0fad-196">tinyint</span><span class="sxs-lookup"><span data-stu-id="f0fad-196">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f0fad-197">Процент продолжительности звонка с помощью перетаскивания рамки BP.</span><span class="sxs-lookup"><span data-stu-id="f0fad-197">Percentage of call duration with BP frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0fad-198"><strong>бпспдропратио</strong></span><span class="sxs-lookup"><span data-stu-id="f0fad-198"><strong>BPSPDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="f0fad-199">tinyint</span><span class="sxs-lookup"><span data-stu-id="f0fad-199">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f0fad-200">Процент продолжительности звонка с помощью БПСП Frame Drop.</span><span class="sxs-lookup"><span data-stu-id="f0fad-200">Percentage of call duration with BPSP frame drop.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0fad-201"><strong>бпспидропратио</strong></span><span class="sxs-lookup"><span data-stu-id="f0fad-201"><strong>BPSPIDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="f0fad-202">tinyint</span><span class="sxs-lookup"><span data-stu-id="f0fad-202">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f0fad-203">Процент продолжительности звонка с помощью БПСПИ Frame Drop.</span><span class="sxs-lookup"><span data-stu-id="f0fad-203">Percentage of call duration with BPSPI frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0fad-204"><strong>443</strong></span><span class="sxs-lookup"><span data-stu-id="f0fad-204"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="f0fad-205">бит</span><span class="sxs-lookup"><span data-stu-id="f0fad-205">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f0fad-206">Получение потоковых данных на стороне получателя.</span><span class="sxs-lookup"><span data-stu-id="f0fad-206">Stream data on receiver side is received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0fad-207"><strong>Исходящее</strong></span><span class="sxs-lookup"><span data-stu-id="f0fad-207"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="f0fad-208">бит</span><span class="sxs-lookup"><span data-stu-id="f0fad-208">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f0fad-209">Получение данных потока на стороне отправителя.</span><span class="sxs-lookup"><span data-stu-id="f0fad-209">Stream data on sender side is received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0fad-210"><strong>сендерискаллерпаи</strong></span><span class="sxs-lookup"><span data-stu-id="f0fad-210"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="f0fad-211">бит</span><span class="sxs-lookup"><span data-stu-id="f0fad-211">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f0fad-212">1 — направление потока для вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="f0fad-212">1 means the stream direction is from the caller to callee.</span></span></p>
<p><span data-ttu-id="f0fad-213">0 — направление потока из вызываемого объекта вызывающему абоненту.</span><span class="sxs-lookup"><span data-stu-id="f0fad-213">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0fad-214"><strong>лоссконжестионперцент</strong></span><span class="sxs-lookup"><span data-stu-id="f0fad-214"><strong>LossCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="f0fad-215">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="f0fad-215">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f0fad-216">Указывает процент времени, в течение которого Звонок находился в состоянии перегрузки с потерей.</span><span class="sxs-lookup"><span data-stu-id="f0fad-216">Indicates the percentage of the time when the call was in a loss congestion state.</span></span></p>
<p><span data-ttu-id="f0fad-217">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f0fad-217">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0fad-218"><strong>делайконжестионперцент</strong></span><span class="sxs-lookup"><span data-stu-id="f0fad-218"><strong>DelayCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="f0fad-219">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="f0fad-219">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f0fad-220">Указывает процент вызова, в течение которого перегрузка была вызвана отложенным поступлением сетевых пакетов.</span><span class="sxs-lookup"><span data-stu-id="f0fad-220">Indicates the percentage of the call during which congestion was caused by the delayed arrival of network packets.</span></span></p>
<p><span data-ttu-id="f0fad-221">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f0fad-221">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0fad-222"><strong>контентиондетектедперцент</strong></span><span class="sxs-lookup"><span data-stu-id="f0fad-222"><strong>ContentionDetectedPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="f0fad-223">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="f0fad-223">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f0fad-224">Указывает процент времени, в течение которого Звонок конкурирует за ресурсы сети.</span><span class="sxs-lookup"><span data-stu-id="f0fad-224">Indicates the percentage of the time when the call was competing for network resources.</span></span></p>
<p><span data-ttu-id="f0fad-225">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f0fad-225">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0fad-226"><strong>бандвидсестмин</strong></span><span class="sxs-lookup"><span data-stu-id="f0fad-226"><strong>BandwidthEstMin</strong></span></span></p></td>
<td><p><span data-ttu-id="f0fad-227">целое</span><span class="sxs-lookup"><span data-stu-id="f0fad-227">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f0fad-228">Минимальная сумма оценки пропускной способности, измеряемая во время звонка.</span><span class="sxs-lookup"><span data-stu-id="f0fad-228">Minimum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="f0fad-229">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f0fad-229">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0fad-230"><strong>бандвидсестмакс</strong></span><span class="sxs-lookup"><span data-stu-id="f0fad-230"><strong>BandwidthEstMax</strong></span></span></p></td>
<td><p><span data-ttu-id="f0fad-231">целое</span><span class="sxs-lookup"><span data-stu-id="f0fad-231">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f0fad-232">Максимальная степень оценки пропускной способности, измеряемая во время звонка.</span><span class="sxs-lookup"><span data-stu-id="f0fad-232">Maximum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="f0fad-233">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f0fad-233">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0fad-234"><strong>бандвидсестстддев</strong></span><span class="sxs-lookup"><span data-stu-id="f0fad-234"><strong>BandwidthEstStdDev</strong></span></span></p></td>
<td><p><span data-ttu-id="f0fad-235">целое</span><span class="sxs-lookup"><span data-stu-id="f0fad-235">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f0fad-236">Стандартное отклонение оценки пропускной способности, измеряемой во время звонка.</span><span class="sxs-lookup"><span data-stu-id="f0fad-236">Standard deviation of the bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="f0fad-237">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f0fad-237">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0fad-238"><strong>бандвидсеставже</strong></span><span class="sxs-lookup"><span data-stu-id="f0fad-238"><strong>BandwidthEstAvge</strong></span></span></p></td>
<td><p><span data-ttu-id="f0fad-239">целое</span><span class="sxs-lookup"><span data-stu-id="f0fad-239">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f0fad-240">Средняя сумма оценки пропускной способности, измеряемая во время звонка.</span><span class="sxs-lookup"><span data-stu-id="f0fad-240">Average amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="f0fad-241">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f0fad-241">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0fad-242"><strong>ловбандвидсформултивиев</strong></span><span class="sxs-lookup"><span data-stu-id="f0fad-242"><strong>LowBandwidthForMultiview</strong></span></span></p></td>
<td><p><span data-ttu-id="f0fad-243">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="f0fad-243">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f0fad-244">Процент звонка, когда конечная точка определила, что сетевое подключение не поддерживало функцию просмотра видео.</span><span class="sxs-lookup"><span data-stu-id="f0fad-244">Percentage of the call where the endpoint determined that the network connection could not support multiview video.</span></span></p>
<p><span data-ttu-id="f0fad-245">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f0fad-245">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0fad-246"><strong>релативеоневайтотал</strong></span><span class="sxs-lookup"><span data-stu-id="f0fad-246"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="f0fad-247">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="f0fad-247">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f0fad-248">Общая сумма односторонней задержки.</span><span class="sxs-lookup"><span data-stu-id="f0fad-248">Total amount of one-way latency.</span></span> <span data-ttu-id="f0fad-249">Относительная односторонняя задержка измеряет задержку между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="f0fad-249">Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="f0fad-250">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f0fad-250">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0fad-251"><strong>релативеоневайавераже</strong></span><span class="sxs-lookup"><span data-stu-id="f0fad-251"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="f0fad-252">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="f0fad-252">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f0fad-253">Средняя величина односторонней задержки.</span><span class="sxs-lookup"><span data-stu-id="f0fad-253">Average amount of one-way latency.</span></span> <span data-ttu-id="f0fad-254">Относительная односторонняя задержка измеряет задержку между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="f0fad-254">Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="f0fad-255">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f0fad-255">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0fad-256"><strong>релативеоневаймакс</strong></span><span class="sxs-lookup"><span data-stu-id="f0fad-256"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="f0fad-257">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="f0fad-257">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f0fad-258">Максимальная сумма односторонняя задержка.</span><span class="sxs-lookup"><span data-stu-id="f0fad-258">Maximum amount of one-way latency.</span></span> <span data-ttu-id="f0fad-259">Относительная односторонняя задержка измеряет задержку между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="f0fad-259">Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="f0fad-260">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f0fad-260">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0fad-261"><strong>релативеоневайбурстоккурренцес</strong></span><span class="sxs-lookup"><span data-stu-id="f0fad-261"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="f0fad-262">целое</span><span class="sxs-lookup"><span data-stu-id="f0fad-262">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f0fad-263">Общее количество односторонних вхождений.</span><span class="sxs-lookup"><span data-stu-id="f0fad-263">Total one-way burst occurrences.</span></span> <span data-ttu-id="f0fad-264">Одновременная передача данных — это передача, при которой данные передаются в непредсказуемые пакеты, а не в устойчивый поток.</span><span class="sxs-lookup"><span data-stu-id="f0fad-264">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="f0fad-265">Этот показатель измеряет поток данных между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="f0fad-265">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="f0fad-266">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f0fad-266">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0fad-267"><strong>релативеоневайбурстденсити</strong></span><span class="sxs-lookup"><span data-stu-id="f0fad-267"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="f0fad-268">целое</span><span class="sxs-lookup"><span data-stu-id="f0fad-268">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f0fad-269">Общая односторонняя плотность нагрузки.</span><span class="sxs-lookup"><span data-stu-id="f0fad-269">Total one-way burst density.</span></span> <span data-ttu-id="f0fad-270">Одновременная передача данных — это передача, при которой данные передаются в непредсказуемые пакеты, а не в устойчивый поток.</span><span class="sxs-lookup"><span data-stu-id="f0fad-270">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="f0fad-271">Этот показатель измеряет поток данных между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="f0fad-271">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="f0fad-272">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f0fad-272">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0fad-273"><strong>релативеоневайбурстдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="f0fad-273"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="f0fad-274">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="f0fad-274">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f0fad-275">Общая продолжительность односторонней длительности.</span><span class="sxs-lookup"><span data-stu-id="f0fad-275">Total one-way burst duration.</span></span> <span data-ttu-id="f0fad-276">Одновременная передача данных — это передача, при которой данные передаются в непредсказуемые пакеты, а не в устойчивый поток.</span><span class="sxs-lookup"><span data-stu-id="f0fad-276">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="f0fad-277">Этот показатель измеряет поток данных между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="f0fad-277">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="f0fad-278">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f0fad-278">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0fad-279"><strong>релативеоневайгапоккурренцес</strong></span><span class="sxs-lookup"><span data-stu-id="f0fad-279"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="f0fad-280">целое</span><span class="sxs-lookup"><span data-stu-id="f0fad-280">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f0fad-281">Общее количество односторонних вхождений.</span><span class="sxs-lookup"><span data-stu-id="f0fad-281">Total one-way gap occurrences.</span></span> <span data-ttu-id="f0fad-282">Одновременная передача данных — это передача, при которой данные передаются в непредсказуемые пакеты, а не в устойчивый поток. зазоры указывают на задержку между этими пакетами.</span><span class="sxs-lookup"><span data-stu-id="f0fad-282">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="f0fad-283">Этот показатель измеряет поток данных между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="f0fad-283">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="f0fad-284">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f0fad-284">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0fad-285"><strong>релативеоневайгапденсити</strong></span><span class="sxs-lookup"><span data-stu-id="f0fad-285"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="f0fad-286">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="f0fad-286">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f0fad-287">Общая плотность односторонних зазоров.</span><span class="sxs-lookup"><span data-stu-id="f0fad-287">Total one-way gap density.</span></span> <span data-ttu-id="f0fad-288">Одновременная передача данных — это передача, при которой данные передаются в непредсказуемые пакеты, а не в устойчивый поток. зазоры указывают на задержку между этими пакетами.</span><span class="sxs-lookup"><span data-stu-id="f0fad-288">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="f0fad-289">Этот показатель измеряет поток данных между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="f0fad-289">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="f0fad-290">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f0fad-290">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0fad-291"><strong>релативеоневайгапдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="f0fad-291"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="f0fad-292">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="f0fad-292">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f0fad-293">Общая продолжительность односторонних промежутков.</span><span class="sxs-lookup"><span data-stu-id="f0fad-293">Total one-way gap duration.</span></span> <span data-ttu-id="f0fad-294">Одновременная передача данных — это передача, при которой данные передаются в непредсказуемые пакеты, а не в устойчивый поток. зазоры указывают на задержку между этими пакетами.</span><span class="sxs-lookup"><span data-stu-id="f0fad-294">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="f0fad-295">Этот показатель измеряет поток данных между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="f0fad-295">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="f0fad-296">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f0fad-296">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0fad-297"><strong>видеопаккетлоссрате</strong></span><span class="sxs-lookup"><span data-stu-id="f0fad-297"><strong>VideoPacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="f0fad-298">десятичное число (9; 4)</span><span class="sxs-lookup"><span data-stu-id="f0fad-298">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f0fad-299">Частота потери видеопакетов.</span><span class="sxs-lookup"><span data-stu-id="f0fad-299">Rate at which video packets were lost.</span></span></p>
<p><span data-ttu-id="f0fad-300">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f0fad-300">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0fad-301"><strong>видеоаллокатебвавг</strong></span><span class="sxs-lookup"><span data-stu-id="f0fad-301"><strong>VideoAllocateBWAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="f0fad-302">целое</span><span class="sxs-lookup"><span data-stu-id="f0fad-302">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f0fad-303">Средний объем пропускной способности, выделенной для видео.</span><span class="sxs-lookup"><span data-stu-id="f0fad-303">Average amount of bandwidth allocated for video.</span></span></p>
<p><span data-ttu-id="f0fad-304">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f0fad-304">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0fad-305"><strong>сендкодектипес</strong></span><span class="sxs-lookup"><span data-stu-id="f0fad-305"><strong>SendCodecTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="f0fad-306">smallint</span><span class="sxs-lookup"><span data-stu-id="f0fad-306">smallint</span></span></p></td>
<td><p><span data-ttu-id="f0fad-307">Другом</span><span class="sxs-lookup"><span data-stu-id="f0fad-307">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f0fad-308">Тип видеокодеков, используемых отправителем.</span><span class="sxs-lookup"><span data-stu-id="f0fad-308">Type of video codecs used by the sender.</span></span> <span data-ttu-id="f0fad-309">Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-codecdescription-table.md">таблицей кодекдескриптион в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f0fad-309">See the <a href="lync-server-2013-codecdescription-table.md">CodecDescription table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="f0fad-310">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f0fad-310">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0fad-311"><strong>сендресолутионвидс</strong></span><span class="sxs-lookup"><span data-stu-id="f0fad-311"><strong>SendResolutionWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="f0fad-312">целое</span><span class="sxs-lookup"><span data-stu-id="f0fad-312">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f0fad-313">Ширина разрешения, используемая отправителем.</span><span class="sxs-lookup"><span data-stu-id="f0fad-313">Resolution width used by the sender.</span></span></p>
<p><span data-ttu-id="f0fad-314">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f0fad-314">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0fad-315"><strong>сендресолутионхеигхт</strong></span><span class="sxs-lookup"><span data-stu-id="f0fad-315"><strong>SendResolutionHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="f0fad-316">целое</span><span class="sxs-lookup"><span data-stu-id="f0fad-316">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f0fad-317">Высота разрешения, используемая отправителем.</span><span class="sxs-lookup"><span data-stu-id="f0fad-317">Resolution height used by the sender.</span></span></p>
<p><span data-ttu-id="f0fad-318">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f0fad-318">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0fad-319"><strong>сендфрамератеавераже</strong></span><span class="sxs-lookup"><span data-stu-id="f0fad-319"><strong>SendFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="f0fad-320">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="f0fad-320">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f0fad-321">Средняя скорость кадров видео, используемая отправителем.</span><span class="sxs-lookup"><span data-stu-id="f0fad-321">Average video frame rate transmission used by the sender.</span></span></p>
<p><span data-ttu-id="f0fad-322">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f0fad-322">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0fad-323"><strong>сендбитратемаксимум</strong></span><span class="sxs-lookup"><span data-stu-id="f0fad-323"><strong>SendBitRateMaximum</strong></span></span></p></td>
<td><p><span data-ttu-id="f0fad-324">целое</span><span class="sxs-lookup"><span data-stu-id="f0fad-324">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f0fad-325">Максимальная скорость для отправителя.</span><span class="sxs-lookup"><span data-stu-id="f0fad-325">Maximum bit rate for the sender.</span></span></p>
<p><span data-ttu-id="f0fad-326">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f0fad-326">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0fad-327"><strong>сендбитратеавераже</strong></span><span class="sxs-lookup"><span data-stu-id="f0fad-327"><strong>SendBitRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="f0fad-328">целое</span><span class="sxs-lookup"><span data-stu-id="f0fad-328">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f0fad-329">Средняя скорость в битах для отправителя.</span><span class="sxs-lookup"><span data-stu-id="f0fad-329">Average bit rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0fad-330"><strong>сендвидеостреамсмакс</strong></span><span class="sxs-lookup"><span data-stu-id="f0fad-330"><strong>SendVideoStreamsMax</strong></span></span></p></td>
<td><p><span data-ttu-id="f0fad-331">целое</span><span class="sxs-lookup"><span data-stu-id="f0fad-331">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f0fad-332">Максимальное количество видеопотоков, используемых отправителем.</span><span class="sxs-lookup"><span data-stu-id="f0fad-332">Maximum number of video streams used by the sender.</span></span></p>
<p><span data-ttu-id="f0fad-333">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f0fad-333">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0fad-334"><strong>реквкодектипес</strong></span><span class="sxs-lookup"><span data-stu-id="f0fad-334"><strong>RecvCodecTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="f0fad-335">smallint</span><span class="sxs-lookup"><span data-stu-id="f0fad-335">smallint</span></span></p></td>
<td><p><span data-ttu-id="f0fad-336">Другом</span><span class="sxs-lookup"><span data-stu-id="f0fad-336">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f0fad-337">Видео коды, используемые получателем.</span><span class="sxs-lookup"><span data-stu-id="f0fad-337">Video codes used by the receiver.</span></span> <span data-ttu-id="f0fad-338">Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-codecdescription-table.md">таблицей кодекдескриптион в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f0fad-338">See the <a href="lync-server-2013-codecdescription-table.md">CodecDescription table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="f0fad-339">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f0fad-339">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0fad-340"><strong>реквресолутионвидс</strong></span><span class="sxs-lookup"><span data-stu-id="f0fad-340"><strong>RecvResolutionWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="f0fad-341">целое</span><span class="sxs-lookup"><span data-stu-id="f0fad-341">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f0fad-342">Ширина разрешения, используемая получателем.</span><span class="sxs-lookup"><span data-stu-id="f0fad-342">Resolution width used by the receiver.</span></span></p>
<p><span data-ttu-id="f0fad-343">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f0fad-343">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0fad-344"><strong>реквресолутионхеигхт</strong></span><span class="sxs-lookup"><span data-stu-id="f0fad-344"><strong>RecvResolutionHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="f0fad-345">целое</span><span class="sxs-lookup"><span data-stu-id="f0fad-345">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f0fad-346">Высота разрешения, используемая получателем.</span><span class="sxs-lookup"><span data-stu-id="f0fad-346">Resolution height used by the receiver.</span></span></p>
<p><span data-ttu-id="f0fad-347">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f0fad-347">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0fad-348"><strong>RecvFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="f0fad-348"><strong>RecvFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="f0fad-349">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="f0fad-349">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f0fad-350">Средняя частота кадров видео, используемая получателем.</span><span class="sxs-lookup"><span data-stu-id="f0fad-350">Average video frame rate used by the receiver.</span></span></p>
<p><span data-ttu-id="f0fad-351">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f0fad-351">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0fad-352"><strong>реквбитратемаксимум</strong></span><span class="sxs-lookup"><span data-stu-id="f0fad-352"><strong>RecvBitRateMaximum</strong></span></span></p></td>
<td><p><span data-ttu-id="f0fad-353">целое</span><span class="sxs-lookup"><span data-stu-id="f0fad-353">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f0fad-354">Максимальная скорость потока для получателя.</span><span class="sxs-lookup"><span data-stu-id="f0fad-354">Maximum bit rate for the receiver.</span></span></p>
<p><span data-ttu-id="f0fad-355">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f0fad-355">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0fad-356"><strong>реквбитратеавераже</strong></span><span class="sxs-lookup"><span data-stu-id="f0fad-356"><strong>RecvBitRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="f0fad-357">целое</span><span class="sxs-lookup"><span data-stu-id="f0fad-357">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f0fad-358">Средняя скорость потока для получателя.</span><span class="sxs-lookup"><span data-stu-id="f0fad-358">Average bit rate for the receiver.</span></span></p>
<p><span data-ttu-id="f0fad-359">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f0fad-359">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0fad-360"><strong>рекввидеостреамсмакс</strong></span><span class="sxs-lookup"><span data-stu-id="f0fad-360"><strong>RecvVideoStreamsMax</strong></span></span></p></td>
<td><p><span data-ttu-id="f0fad-361">целое</span><span class="sxs-lookup"><span data-stu-id="f0fad-361">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f0fad-362">Максимальное количество видеопотоков для получателя.</span><span class="sxs-lookup"><span data-stu-id="f0fad-362">Maximum video streams for the receiver.</span></span></p>
<p><span data-ttu-id="f0fad-363">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f0fad-363">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0fad-364"><strong>рекввидеостреамсмин</strong></span><span class="sxs-lookup"><span data-stu-id="f0fad-364"><strong>RecvVideoStreamsMin</strong></span></span></p></td>
<td><p><span data-ttu-id="f0fad-365">целое</span><span class="sxs-lookup"><span data-stu-id="f0fad-365">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f0fad-366">Минимальный поток видеозаписи для получателя.</span><span class="sxs-lookup"><span data-stu-id="f0fad-366">Minimum video streams for the receiver.</span></span></p>
<p><span data-ttu-id="f0fad-367">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f0fad-367">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0fad-368"><strong>рекввидеостреамсмоде</strong></span><span class="sxs-lookup"><span data-stu-id="f0fad-368"><strong>RecvVideoStreamsMode</strong></span></span></p></td>
<td><p><span data-ttu-id="f0fad-369">целое</span><span class="sxs-lookup"><span data-stu-id="f0fad-369">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f0fad-370">Режим видео (например, коллекция или один поток) получателя.</span><span class="sxs-lookup"><span data-stu-id="f0fad-370">Video mode (for example, gallery or single stream) for the receiver.</span></span></p>
<p><span data-ttu-id="f0fad-371">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f0fad-371">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0fad-372"><strong>VideoPostFECPLR</strong></span><span class="sxs-lookup"><span data-stu-id="f0fad-372"><strong>VideoPostFECPLR</strong></span></span></p></td>
<td><p><span data-ttu-id="f0fad-373">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="f0fad-373">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f0fad-374">Применена ставка потери пакетов после исправления ошибки переадресации.</span><span class="sxs-lookup"><span data-stu-id="f0fad-374">Packet loss rate after forward error correction has been applied.</span></span></p>
<p><span data-ttu-id="f0fad-375">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f0fad-375">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0fad-376"><strong>динамиккапабилитиперцент</strong></span><span class="sxs-lookup"><span data-stu-id="f0fad-376"><strong>DynamicCapabilityPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="f0fad-377">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="f0fad-377">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f0fad-378">Процент времени, в течение которого был активен флаг динамической доступности.</span><span class="sxs-lookup"><span data-stu-id="f0fad-378">Percentage of time that the dynamic capability flag was active.</span></span></p>
<p><span data-ttu-id="f0fad-379">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f0fad-379">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0fad-380"><strong>ресолутионмин</strong></span><span class="sxs-lookup"><span data-stu-id="f0fad-380"><strong>ResolutionMin</strong></span></span></p></td>
<td><p><span data-ttu-id="f0fad-381">char (9)</span><span class="sxs-lookup"><span data-stu-id="f0fad-381">char(9)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f0fad-382">Минимальное разрешение, измеряемое во время звонка.</span><span class="sxs-lookup"><span data-stu-id="f0fad-382">Minimum resolution measured during the call.</span></span></p>
<p><span data-ttu-id="f0fad-383">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f0fad-383">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0fad-384"><strong>ловбитратекаллперцент</strong></span><span class="sxs-lookup"><span data-stu-id="f0fad-384"><strong>LowBitRateCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="f0fad-385">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="f0fad-385">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f0fad-386">Процент звонка ниже минимального порогового значения скорости (70 килобит в секунду).</span><span class="sxs-lookup"><span data-stu-id="f0fad-386">Percentage of the call below the low bit rate threshold (70 kilobits per second).</span></span></p>
<p><span data-ttu-id="f0fad-387">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f0fad-387">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0fad-388"><strong>LowFrameRateCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="f0fad-388"><strong>LowFrameRateCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="f0fad-389">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="f0fad-389">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f0fad-390">Процент звонка ниже нижнего порогового значения частоты кадров (количество кадров в 7,5 в секунду, входящее).</span><span class="sxs-lookup"><span data-stu-id="f0fad-390">Percentage of the call below the low frame rate threshold (7.5 frames per second, inbound).</span></span></p>
<p><span data-ttu-id="f0fad-391">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f0fad-391">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0fad-392"><strong>LowResolutionCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="f0fad-392"><strong>LowResolutionCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="f0fad-393">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="f0fad-393">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f0fad-394">Процент звонка, который выполнялся по низким разрешению.</span><span class="sxs-lookup"><span data-stu-id="f0fad-394">Percentage of the call that occurred at the lowest resolution.</span></span></p>
<p><span data-ttu-id="f0fad-395">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f0fad-395">This column was introduced in Microsoft Lync Server 2013.</span></span></p>
<p><span data-ttu-id="f0fad-396">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f0fad-396">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0fad-397"><strong>дуратионсекондс</strong></span><span class="sxs-lookup"><span data-stu-id="f0fad-397"><strong>DurationSeconds</strong></span></span></p></td>
<td><p><span data-ttu-id="f0fad-398">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="f0fad-398">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f0fad-399">Продолжительность звонка в секундах.</span><span class="sxs-lookup"><span data-stu-id="f0fad-399">Length of the call in seconds.</span></span></p>
<p><span data-ttu-id="f0fad-400">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f0fad-400">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0fad-401"><strong>исаггрегатеддата</strong></span><span class="sxs-lookup"><span data-stu-id="f0fad-401"><strong>IsAggregatedData</strong></span></span></p></td>
<td><p><span data-ttu-id="f0fad-402">бит</span><span class="sxs-lookup"><span data-stu-id="f0fad-402">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f0fad-403">Указывает, были ли данные объединены из нескольких вызовов.</span><span class="sxs-lookup"><span data-stu-id="f0fad-403">Indicates whether the data has been aggregated from multiple calls.</span></span></p>
<p><span data-ttu-id="f0fad-404">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f0fad-404">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

