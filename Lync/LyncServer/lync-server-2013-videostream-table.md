---
title: 'Lync Server 2013: таблица VideoStream'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: VideoStream table
ms:assetid: 4275ede7-5467-4a97-b8c8-a4b00917bf32
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425928(v=OCS.15)
ms:contentKeyID: 48184014
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 98e0ad3f7c18032dd903d2f8d1d41428ccc12cf9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849177"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="videostream-table-in-lync-server-2013"></a><span data-ttu-id="6597c-102">Таблица VideoStream в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6597c-102">VideoStream table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6597c-103">_**Тема последнего изменения:** 2013-12-13_</span><span class="sxs-lookup"><span data-stu-id="6597c-103">_**Topic Last Modified:** 2013-12-13_</span></span>

<span data-ttu-id="6597c-104">Каждая запись представляет один поток видео.</span><span class="sxs-lookup"><span data-stu-id="6597c-104">Each record represents one video stream.</span></span> <span data-ttu-id="6597c-105">Одна линия видеофайла обычно состоит из двух видеопотоков.</span><span class="sxs-lookup"><span data-stu-id="6597c-105">One video media line usually contains two video streams.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6597c-106"><strong>Столбец</strong></span><span class="sxs-lookup"><span data-stu-id="6597c-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="6597c-107"><strong>Тип данных</strong></span><span class="sxs-lookup"><span data-stu-id="6597c-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="6597c-108"><strong>Ключ/индекс</strong></span><span class="sxs-lookup"><span data-stu-id="6597c-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="6597c-109"><strong>Сведения</strong></span><span class="sxs-lookup"><span data-stu-id="6597c-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6597c-110"><strong>Конференцедатетиме</strong></span><span class="sxs-lookup"><span data-stu-id="6597c-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="6597c-111">datetime</span><span class="sxs-lookup"><span data-stu-id="6597c-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="6597c-112">Primary</span><span class="sxs-lookup"><span data-stu-id="6597c-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="6597c-113">На которую ссылается <a href="lync-server-2013-medialine-table.md">Таблица медиалине в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="6597c-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6597c-114"><strong>Сессионсек</strong></span><span class="sxs-lookup"><span data-stu-id="6597c-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="6597c-115">целое</span><span class="sxs-lookup"><span data-stu-id="6597c-115">int</span></span></p></td>
<td><p><span data-ttu-id="6597c-116">Primary</span><span class="sxs-lookup"><span data-stu-id="6597c-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="6597c-117">R, на который ссылается <a href="lync-server-2013-medialine-table.md">Таблица медиалине в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="6597c-117">R Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6597c-118"><strong>Медиалинелабел</strong></span><span class="sxs-lookup"><span data-stu-id="6597c-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="6597c-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="6597c-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="6597c-120">Primary</span><span class="sxs-lookup"><span data-stu-id="6597c-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="6597c-121">На которую ссылается <a href="lync-server-2013-medialine-table.md">Таблица медиалине в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="6597c-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6597c-122"><strong>Стреамид</strong></span><span class="sxs-lookup"><span data-stu-id="6597c-122"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="6597c-123">целое</span><span class="sxs-lookup"><span data-stu-id="6597c-123">int</span></span></p></td>
<td><p><span data-ttu-id="6597c-124">Primary</span><span class="sxs-lookup"><span data-stu-id="6597c-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="6597c-125">Уникальный идентификатор в строке мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="6597c-125">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6597c-126"><strong>Видеопайлоаддескриптион</strong></span><span class="sxs-lookup"><span data-stu-id="6597c-126"><strong>VideoPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="6597c-127">smallint</span><span class="sxs-lookup"><span data-stu-id="6597c-127">smallint</span></span></p></td>
<td><p><span data-ttu-id="6597c-128">Внешний, основной</span><span class="sxs-lookup"><span data-stu-id="6597c-128">Foreign, Primary</span></span></p></td>
<td><p><span data-ttu-id="6597c-129">Описание полезных данных.</span><span class="sxs-lookup"><span data-stu-id="6597c-129">Payload description.</span></span> <span data-ttu-id="6597c-130">Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-payloaddescription-table.md">таблицей пайлоаддескриптион в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="6597c-130">See the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6597c-131"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="6597c-131"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="6597c-132">целое</span><span class="sxs-lookup"><span data-stu-id="6597c-132">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="6597c-133">Средняя колебание сети из статистики протокола управления временем в реальном времени (РТКП).</span><span class="sxs-lookup"><span data-stu-id="6597c-133">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6597c-134"><strong>Життеринтерарривалмакс</strong></span><span class="sxs-lookup"><span data-stu-id="6597c-134"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="6597c-135">целое</span><span class="sxs-lookup"><span data-stu-id="6597c-135">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="6597c-136">Максимальная колебание сети во время видеосеанса.</span><span class="sxs-lookup"><span data-stu-id="6597c-136">Maximum network jitter during the video session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6597c-137"><strong>RoundTrip</strong></span><span class="sxs-lookup"><span data-stu-id="6597c-137"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="6597c-138">целое</span><span class="sxs-lookup"><span data-stu-id="6597c-138">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="6597c-139">Время кругового приема из статистики РТКП.</span><span class="sxs-lookup"><span data-stu-id="6597c-139">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6597c-140"><strong>Раундтрипмакс</strong></span><span class="sxs-lookup"><span data-stu-id="6597c-140"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="6597c-141">целое</span><span class="sxs-lookup"><span data-stu-id="6597c-141">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="6597c-142">Максимальное время кругового сеанса для видеопотока.</span><span class="sxs-lookup"><span data-stu-id="6597c-142">Maximum round trip time for the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6597c-143"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="6597c-143"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="6597c-144">десятичное число (5; 4)</span><span class="sxs-lookup"><span data-stu-id="6597c-144">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="6597c-145">Средняя скорость потерь пакетов во время звонка.</span><span class="sxs-lookup"><span data-stu-id="6597c-145">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6597c-146"><strong>Паккетлоссратемакс</strong></span><span class="sxs-lookup"><span data-stu-id="6597c-146"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="6597c-147">десятичное число (5; 4)</span><span class="sxs-lookup"><span data-stu-id="6597c-147">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="6597c-148">Максимальное количество потерь пакетов, замеченное во время звонка.</span><span class="sxs-lookup"><span data-stu-id="6597c-148">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6597c-149"><strong>Паккетутилизатион</strong></span><span class="sxs-lookup"><span data-stu-id="6597c-149"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="6597c-150">целое</span><span class="sxs-lookup"><span data-stu-id="6597c-150">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="6597c-151">Число пакетов для видеопотока (транспортный протокол в реальном времени).</span><span class="sxs-lookup"><span data-stu-id="6597c-151">Packet count for the video stream (Real Time Transport Protocol, RTP).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6597c-152"><strong>Самый пропускная способность</strong></span><span class="sxs-lookup"><span data-stu-id="6597c-152"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="6597c-153">целое</span><span class="sxs-lookup"><span data-stu-id="6597c-153">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="6597c-154">Оценка пропускной способности для видеопотока.</span><span class="sxs-lookup"><span data-stu-id="6597c-154">Bandwidth estimates for the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6597c-155"><strong>Видеоресолутион</strong></span><span class="sxs-lookup"><span data-stu-id="6597c-155"><strong>VideoResolution</strong></span></span></p></td>
<td><p><span data-ttu-id="6597c-156">char (9)</span><span class="sxs-lookup"><span data-stu-id="6597c-156">char(9)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="6597c-157">Разрешение видео в пикселях, умноженное на высоту в пикселях.</span><span class="sxs-lookup"><span data-stu-id="6597c-157">Resolution of the video in pixels width multiplied by pixels height.</span></span> <span data-ttu-id="6597c-158">Отображается в виде строки.</span><span class="sxs-lookup"><span data-stu-id="6597c-158">Reported as a string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6597c-159"><strong>Видеобитратеавг</strong></span><span class="sxs-lookup"><span data-stu-id="6597c-159"><strong>VideoBitRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="6597c-160">целое</span><span class="sxs-lookup"><span data-stu-id="6597c-160">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="6597c-161">Средняя скорость потока видео.</span><span class="sxs-lookup"><span data-stu-id="6597c-161">Average bit rate of the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6597c-162"><strong>Инбаундвидеофрамератеавг</strong></span><span class="sxs-lookup"><span data-stu-id="6597c-162"><strong>InboundVideoFrameRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="6597c-163">десятичное число (9; 4)</span><span class="sxs-lookup"><span data-stu-id="6597c-163">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="6597c-164">Полученная частота кадров видео.</span><span class="sxs-lookup"><span data-stu-id="6597c-164">The video frame rate received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6597c-165"><strong>Аутбаундвидеофрамератеавг</strong></span><span class="sxs-lookup"><span data-stu-id="6597c-165"><strong>OutboundVideoFrameRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="6597c-166">десятичное число (9; 4)</span><span class="sxs-lookup"><span data-stu-id="6597c-166">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="6597c-167">Частота отправки кадров видео.</span><span class="sxs-lookup"><span data-stu-id="6597c-167">The video frame rate sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6597c-168"><strong>Видеобитратемакс</strong></span><span class="sxs-lookup"><span data-stu-id="6597c-168"><strong>VideoBitRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="6597c-169">целое</span><span class="sxs-lookup"><span data-stu-id="6597c-169">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="6597c-170">Максимальная скорость видеосигнала во время видеосеанса.</span><span class="sxs-lookup"><span data-stu-id="6597c-170">The maximum video bit rate during the video session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6597c-171"><strong>Видеофрамелоссрате</strong></span><span class="sxs-lookup"><span data-stu-id="6597c-171"><strong>VideoFrameLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="6597c-172">десятичное число (9; 4)</span><span class="sxs-lookup"><span data-stu-id="6597c-172">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="6597c-173">Процент от общего числа потерянных кадров видео.</span><span class="sxs-lookup"><span data-stu-id="6597c-173">The percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6597c-174"><strong>Видеофек</strong></span><span class="sxs-lookup"><span data-stu-id="6597c-174"><strong>VideoFEC</strong></span></span></p></td>
<td><p><span data-ttu-id="6597c-175">бит</span><span class="sxs-lookup"><span data-stu-id="6597c-175">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="6597c-176">Недоступно.</span><span class="sxs-lookup"><span data-stu-id="6597c-176">Not available.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6597c-177"><strong>VideoLocalFrameLossPercentageAvg</strong></span><span class="sxs-lookup"><span data-stu-id="6597c-177"><strong>VideoLocalFrameLossPercentageAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="6597c-178">десятичное число (9; 4)</span><span class="sxs-lookup"><span data-stu-id="6597c-178">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6597c-179">Процент от общего числа потерянных кадров видео.</span><span class="sxs-lookup"><span data-stu-id="6597c-179">The percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6597c-180"><strong>Цифкуалитиратио</strong></span><span class="sxs-lookup"><span data-stu-id="6597c-180"><strong>CIFQualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="6597c-181">tinyint</span><span class="sxs-lookup"><span data-stu-id="6597c-181">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6597c-182">Процент звонка, находился в разрешении общего формата обмена (циф).</span><span class="sxs-lookup"><span data-stu-id="6597c-182">The percentage of the call that was at the Common Interchange Format (CIF) resolution.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6597c-183"><strong>Вгакуалитиратио</strong></span><span class="sxs-lookup"><span data-stu-id="6597c-183"><strong>VGAQualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="6597c-184">tinyint</span><span class="sxs-lookup"><span data-stu-id="6597c-184">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6597c-185">Процент звонка, находился в режиме разрешающей способности VGA.</span><span class="sxs-lookup"><span data-stu-id="6597c-185">The percentage of the call that was at VGA resolution.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6597c-186"><strong>HD720QualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="6597c-186"><strong>HD720QualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="6597c-187">tinyint</span><span class="sxs-lookup"><span data-stu-id="6597c-187">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6597c-188">Процентное соотношение вызова, которое было установлено по адресу HD720.</span><span class="sxs-lookup"><span data-stu-id="6597c-188">The percentage of the call that was at HD720 resolution.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6597c-189"><strong>Нонедропратио</strong></span><span class="sxs-lookup"><span data-stu-id="6597c-189"><strong>NoneDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="6597c-190">tinyint</span><span class="sxs-lookup"><span data-stu-id="6597c-190">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6597c-191">Процент продолжительности звонка без удаления кадров.</span><span class="sxs-lookup"><span data-stu-id="6597c-191">Percentage of call duration with no frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6597c-192"><strong>Бдропратио</strong></span><span class="sxs-lookup"><span data-stu-id="6597c-192"><strong>BDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="6597c-193">tinyint</span><span class="sxs-lookup"><span data-stu-id="6597c-193">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6597c-194">Процент продолжительности звонка с помощью функции B Frame Drop.</span><span class="sxs-lookup"><span data-stu-id="6597c-194">Percentage of call duration with B frame drop.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6597c-195"><strong>Бпдропратио</strong></span><span class="sxs-lookup"><span data-stu-id="6597c-195"><strong>BPDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="6597c-196">tinyint</span><span class="sxs-lookup"><span data-stu-id="6597c-196">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6597c-197">Процент продолжительности звонка с помощью перетаскивания рамки BP.</span><span class="sxs-lookup"><span data-stu-id="6597c-197">Percentage of call duration with BP frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6597c-198"><strong>Бпспдропратио</strong></span><span class="sxs-lookup"><span data-stu-id="6597c-198"><strong>BPSPDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="6597c-199">tinyint</span><span class="sxs-lookup"><span data-stu-id="6597c-199">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6597c-200">Процент продолжительности звонка с помощью БПСП Frame Drop.</span><span class="sxs-lookup"><span data-stu-id="6597c-200">Percentage of call duration with BPSP frame drop.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6597c-201"><strong>Бпспидропратио</strong></span><span class="sxs-lookup"><span data-stu-id="6597c-201"><strong>BPSPIDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="6597c-202">tinyint</span><span class="sxs-lookup"><span data-stu-id="6597c-202">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6597c-203">Процент продолжительности звонка с помощью БПСПИ Frame Drop.</span><span class="sxs-lookup"><span data-stu-id="6597c-203">Percentage of call duration with BPSPI frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6597c-204"><strong>443</strong></span><span class="sxs-lookup"><span data-stu-id="6597c-204"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="6597c-205">бит</span><span class="sxs-lookup"><span data-stu-id="6597c-205">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="6597c-206">Получение потоковых данных на стороне получателя.</span><span class="sxs-lookup"><span data-stu-id="6597c-206">Stream data on receiver side is received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6597c-207"><strong>Исходящее</strong></span><span class="sxs-lookup"><span data-stu-id="6597c-207"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="6597c-208">бит</span><span class="sxs-lookup"><span data-stu-id="6597c-208">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="6597c-209">Получение данных потока на стороне отправителя.</span><span class="sxs-lookup"><span data-stu-id="6597c-209">Stream data on sender side is received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6597c-210"><strong>Сендерискаллерпаи</strong></span><span class="sxs-lookup"><span data-stu-id="6597c-210"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="6597c-211">бит</span><span class="sxs-lookup"><span data-stu-id="6597c-211">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="6597c-212">1 — направление потока для вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="6597c-212">1 means the stream direction is from the caller to callee.</span></span></p>
<p><span data-ttu-id="6597c-213">0 — направление потока из вызываемого объекта вызывающему абоненту.</span><span class="sxs-lookup"><span data-stu-id="6597c-213">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6597c-214"><strong>Лоссконжестионперцент</strong></span><span class="sxs-lookup"><span data-stu-id="6597c-214"><strong>LossCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="6597c-215">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="6597c-215">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6597c-216">Указывает процент времени, в течение которого Звонок находился в состоянии перегрузки с потерей.</span><span class="sxs-lookup"><span data-stu-id="6597c-216">Indicates the percentage of the time when the call was in a loss congestion state.</span></span></p>
<p><span data-ttu-id="6597c-217">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6597c-217">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6597c-218"><strong>Делайконжестионперцент</strong></span><span class="sxs-lookup"><span data-stu-id="6597c-218"><strong>DelayCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="6597c-219">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="6597c-219">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6597c-220">Указывает процент вызова, в течение которого перегрузка была вызвана отложенным поступлением сетевых пакетов.</span><span class="sxs-lookup"><span data-stu-id="6597c-220">Indicates the percentage of the call during which congestion was caused by the delayed arrival of network packets.</span></span></p>
<p><span data-ttu-id="6597c-221">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6597c-221">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6597c-222"><strong>Контентиондетектедперцент</strong></span><span class="sxs-lookup"><span data-stu-id="6597c-222"><strong>ContentionDetectedPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="6597c-223">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="6597c-223">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6597c-224">Указывает процент времени, в течение которого Звонок конкурирует за ресурсы сети.</span><span class="sxs-lookup"><span data-stu-id="6597c-224">Indicates the percentage of the time when the call was competing for network resources.</span></span></p>
<p><span data-ttu-id="6597c-225">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6597c-225">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6597c-226"><strong>Бандвидсестмин</strong></span><span class="sxs-lookup"><span data-stu-id="6597c-226"><strong>BandwidthEstMin</strong></span></span></p></td>
<td><p><span data-ttu-id="6597c-227">целое</span><span class="sxs-lookup"><span data-stu-id="6597c-227">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6597c-228">Минимальная сумма оценки пропускной способности, измеряемая во время звонка.</span><span class="sxs-lookup"><span data-stu-id="6597c-228">Minimum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="6597c-229">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6597c-229">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6597c-230"><strong>Бандвидсестмакс</strong></span><span class="sxs-lookup"><span data-stu-id="6597c-230"><strong>BandwidthEstMax</strong></span></span></p></td>
<td><p><span data-ttu-id="6597c-231">целое</span><span class="sxs-lookup"><span data-stu-id="6597c-231">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6597c-232">Максимальная степень оценки пропускной способности, измеряемая во время звонка.</span><span class="sxs-lookup"><span data-stu-id="6597c-232">Maximum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="6597c-233">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6597c-233">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6597c-234"><strong>Бандвидсестстддев</strong></span><span class="sxs-lookup"><span data-stu-id="6597c-234"><strong>BandwidthEstStdDev</strong></span></span></p></td>
<td><p><span data-ttu-id="6597c-235">целое</span><span class="sxs-lookup"><span data-stu-id="6597c-235">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6597c-236">Стандартное отклонение оценки пропускной способности, измеряемой во время звонка.</span><span class="sxs-lookup"><span data-stu-id="6597c-236">Standard deviation of the bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="6597c-237">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6597c-237">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6597c-238"><strong>Бандвидсеставже</strong></span><span class="sxs-lookup"><span data-stu-id="6597c-238"><strong>BandwidthEstAvge</strong></span></span></p></td>
<td><p><span data-ttu-id="6597c-239">целое</span><span class="sxs-lookup"><span data-stu-id="6597c-239">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6597c-240">Средняя сумма оценки пропускной способности, измеряемая во время звонка.</span><span class="sxs-lookup"><span data-stu-id="6597c-240">Average amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="6597c-241">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6597c-241">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6597c-242"><strong>Ловбандвидсформултивиев</strong></span><span class="sxs-lookup"><span data-stu-id="6597c-242"><strong>LowBandwidthForMultiview</strong></span></span></p></td>
<td><p><span data-ttu-id="6597c-243">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="6597c-243">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6597c-244">Процент звонка, когда конечная точка определила, что сетевое подключение не поддерживало функцию просмотра видео.</span><span class="sxs-lookup"><span data-stu-id="6597c-244">Percentage of the call where the endpoint determined that the network connection could not support multiview video.</span></span></p>
<p><span data-ttu-id="6597c-245">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6597c-245">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6597c-246"><strong>Релативеоневайтотал</strong></span><span class="sxs-lookup"><span data-stu-id="6597c-246"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="6597c-247">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="6597c-247">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6597c-248">Общая сумма односторонней задержки.</span><span class="sxs-lookup"><span data-stu-id="6597c-248">Total amount of one-way latency.</span></span> <span data-ttu-id="6597c-249">Относительная односторонняя задержка измеряет задержку между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="6597c-249">Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="6597c-250">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6597c-250">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6597c-251"><strong>Релативеоневайавераже</strong></span><span class="sxs-lookup"><span data-stu-id="6597c-251"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="6597c-252">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="6597c-252">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6597c-253">Средняя величина односторонней задержки.</span><span class="sxs-lookup"><span data-stu-id="6597c-253">Average amount of one-way latency.</span></span> <span data-ttu-id="6597c-254">Относительная односторонняя задержка измеряет задержку между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="6597c-254">Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="6597c-255">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6597c-255">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6597c-256"><strong>Релативеоневаймакс</strong></span><span class="sxs-lookup"><span data-stu-id="6597c-256"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="6597c-257">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="6597c-257">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6597c-258">Максимальная сумма односторонняя задержка.</span><span class="sxs-lookup"><span data-stu-id="6597c-258">Maximum amount of one-way latency.</span></span> <span data-ttu-id="6597c-259">Относительная односторонняя задержка измеряет задержку между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="6597c-259">Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="6597c-260">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6597c-260">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6597c-261"><strong>Релативеоневайбурстоккурренцес</strong></span><span class="sxs-lookup"><span data-stu-id="6597c-261"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="6597c-262">целое</span><span class="sxs-lookup"><span data-stu-id="6597c-262">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6597c-263">Общее количество односторонних вхождений.</span><span class="sxs-lookup"><span data-stu-id="6597c-263">Total one-way burst occurrences.</span></span> <span data-ttu-id="6597c-264">Одновременная передача данных — это передача, при которой данные передаются в непредсказуемые пакеты, а не в устойчивый поток.</span><span class="sxs-lookup"><span data-stu-id="6597c-264">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="6597c-265">Этот показатель измеряет поток данных между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="6597c-265">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="6597c-266">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6597c-266">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6597c-267"><strong>Релативеоневайбурстденсити</strong></span><span class="sxs-lookup"><span data-stu-id="6597c-267"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="6597c-268">целое</span><span class="sxs-lookup"><span data-stu-id="6597c-268">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6597c-269">Общая односторонняя плотность нагрузки.</span><span class="sxs-lookup"><span data-stu-id="6597c-269">Total one-way burst density.</span></span> <span data-ttu-id="6597c-270">Одновременная передача данных — это передача, при которой данные передаются в непредсказуемые пакеты, а не в устойчивый поток.</span><span class="sxs-lookup"><span data-stu-id="6597c-270">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="6597c-271">Этот показатель измеряет поток данных между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="6597c-271">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="6597c-272">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6597c-272">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6597c-273"><strong>Релативеоневайбурстдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="6597c-273"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="6597c-274">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="6597c-274">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6597c-275">Общая продолжительность односторонней длительности.</span><span class="sxs-lookup"><span data-stu-id="6597c-275">Total one-way burst duration.</span></span> <span data-ttu-id="6597c-276">Одновременная передача данных — это передача, при которой данные передаются в непредсказуемые пакеты, а не в устойчивый поток.</span><span class="sxs-lookup"><span data-stu-id="6597c-276">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="6597c-277">Этот показатель измеряет поток данных между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="6597c-277">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="6597c-278">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6597c-278">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6597c-279"><strong>Релативеоневайгапоккурренцес</strong></span><span class="sxs-lookup"><span data-stu-id="6597c-279"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="6597c-280">целое</span><span class="sxs-lookup"><span data-stu-id="6597c-280">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6597c-281">Общее количество односторонних вхождений.</span><span class="sxs-lookup"><span data-stu-id="6597c-281">Total one-way gap occurrences.</span></span> <span data-ttu-id="6597c-282">Одновременная передача данных — это передача, при которой данные передаются в непредсказуемые пакеты, а не в устойчивый поток. зазоры указывают на задержку между этими пакетами.</span><span class="sxs-lookup"><span data-stu-id="6597c-282">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="6597c-283">Этот показатель измеряет поток данных между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="6597c-283">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="6597c-284">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6597c-284">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6597c-285"><strong>Релативеоневайгапденсити</strong></span><span class="sxs-lookup"><span data-stu-id="6597c-285"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="6597c-286">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="6597c-286">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6597c-287">Общая плотность односторонних зазоров.</span><span class="sxs-lookup"><span data-stu-id="6597c-287">Total one-way gap density.</span></span> <span data-ttu-id="6597c-288">Одновременная передача данных — это передача, при которой данные передаются в непредсказуемые пакеты, а не в устойчивый поток. зазоры указывают на задержку между этими пакетами.</span><span class="sxs-lookup"><span data-stu-id="6597c-288">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="6597c-289">Этот показатель измеряет поток данных между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="6597c-289">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="6597c-290">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6597c-290">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6597c-291"><strong>Релативеоневайгапдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="6597c-291"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="6597c-292">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="6597c-292">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6597c-293">Общая продолжительность односторонних промежутков.</span><span class="sxs-lookup"><span data-stu-id="6597c-293">Total one-way gap duration.</span></span> <span data-ttu-id="6597c-294">Одновременная передача данных — это передача, при которой данные передаются в непредсказуемые пакеты, а не в устойчивый поток. зазоры указывают на задержку между этими пакетами.</span><span class="sxs-lookup"><span data-stu-id="6597c-294">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="6597c-295">Этот показатель измеряет поток данных между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="6597c-295">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="6597c-296">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6597c-296">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6597c-297"><strong>Видеопаккетлоссрате</strong></span><span class="sxs-lookup"><span data-stu-id="6597c-297"><strong>VideoPacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="6597c-298">десятичное число (9; 4)</span><span class="sxs-lookup"><span data-stu-id="6597c-298">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6597c-299">Частота потери видеопакетов.</span><span class="sxs-lookup"><span data-stu-id="6597c-299">Rate at which video packets were lost.</span></span></p>
<p><span data-ttu-id="6597c-300">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6597c-300">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6597c-301"><strong>Видеоаллокатебвавг</strong></span><span class="sxs-lookup"><span data-stu-id="6597c-301"><strong>VideoAllocateBWAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="6597c-302">целое</span><span class="sxs-lookup"><span data-stu-id="6597c-302">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6597c-303">Средний объем пропускной способности, выделенной для видео.</span><span class="sxs-lookup"><span data-stu-id="6597c-303">Average amount of bandwidth allocated for video.</span></span></p>
<p><span data-ttu-id="6597c-304">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6597c-304">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6597c-305"><strong>Сендкодектипес</strong></span><span class="sxs-lookup"><span data-stu-id="6597c-305"><strong>SendCodecTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="6597c-306">smallint</span><span class="sxs-lookup"><span data-stu-id="6597c-306">smallint</span></span></p></td>
<td><p><span data-ttu-id="6597c-307">Другом</span><span class="sxs-lookup"><span data-stu-id="6597c-307">Foreign</span></span></p></td>
<td><p><span data-ttu-id="6597c-308">Тип видеокодеков, используемых отправителем.</span><span class="sxs-lookup"><span data-stu-id="6597c-308">Type of video codecs used by the sender.</span></span> <span data-ttu-id="6597c-309">Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-codecdescription-table.md">таблицей кодекдескриптион в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="6597c-309">See the <a href="lync-server-2013-codecdescription-table.md">CodecDescription table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="6597c-310">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6597c-310">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6597c-311"><strong>Сендресолутионвидс</strong></span><span class="sxs-lookup"><span data-stu-id="6597c-311"><strong>SendResolutionWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="6597c-312">целое</span><span class="sxs-lookup"><span data-stu-id="6597c-312">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6597c-313">Ширина разрешения, используемая отправителем.</span><span class="sxs-lookup"><span data-stu-id="6597c-313">Resolution width used by the sender.</span></span></p>
<p><span data-ttu-id="6597c-314">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6597c-314">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6597c-315"><strong>Сендресолутионхеигхт</strong></span><span class="sxs-lookup"><span data-stu-id="6597c-315"><strong>SendResolutionHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="6597c-316">целое</span><span class="sxs-lookup"><span data-stu-id="6597c-316">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6597c-317">Высота разрешения, используемая отправителем.</span><span class="sxs-lookup"><span data-stu-id="6597c-317">Resolution height used by the sender.</span></span></p>
<p><span data-ttu-id="6597c-318">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6597c-318">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6597c-319"><strong>Сендфрамератеавераже</strong></span><span class="sxs-lookup"><span data-stu-id="6597c-319"><strong>SendFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="6597c-320">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="6597c-320">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6597c-321">Средняя скорость кадров видео, используемая отправителем.</span><span class="sxs-lookup"><span data-stu-id="6597c-321">Average video frame rate transmission used by the sender.</span></span></p>
<p><span data-ttu-id="6597c-322">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6597c-322">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6597c-323"><strong>Сендбитратемаксимум</strong></span><span class="sxs-lookup"><span data-stu-id="6597c-323"><strong>SendBitRateMaximum</strong></span></span></p></td>
<td><p><span data-ttu-id="6597c-324">целое</span><span class="sxs-lookup"><span data-stu-id="6597c-324">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6597c-325">Максимальная скорость для отправителя.</span><span class="sxs-lookup"><span data-stu-id="6597c-325">Maximum bit rate for the sender.</span></span></p>
<p><span data-ttu-id="6597c-326">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6597c-326">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6597c-327"><strong>Сендбитратеавераже</strong></span><span class="sxs-lookup"><span data-stu-id="6597c-327"><strong>SendBitRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="6597c-328">целое</span><span class="sxs-lookup"><span data-stu-id="6597c-328">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6597c-329">Средняя скорость в битах для отправителя.</span><span class="sxs-lookup"><span data-stu-id="6597c-329">Average bit rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6597c-330"><strong>Сендвидеостреамсмакс</strong></span><span class="sxs-lookup"><span data-stu-id="6597c-330"><strong>SendVideoStreamsMax</strong></span></span></p></td>
<td><p><span data-ttu-id="6597c-331">целое</span><span class="sxs-lookup"><span data-stu-id="6597c-331">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6597c-332">Максимальное количество видеопотоков, используемых отправителем.</span><span class="sxs-lookup"><span data-stu-id="6597c-332">Maximum number of video streams used by the sender.</span></span></p>
<p><span data-ttu-id="6597c-333">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6597c-333">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6597c-334"><strong>Реквкодектипес</strong></span><span class="sxs-lookup"><span data-stu-id="6597c-334"><strong>RecvCodecTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="6597c-335">smallint</span><span class="sxs-lookup"><span data-stu-id="6597c-335">smallint</span></span></p></td>
<td><p><span data-ttu-id="6597c-336">Другом</span><span class="sxs-lookup"><span data-stu-id="6597c-336">Foreign</span></span></p></td>
<td><p><span data-ttu-id="6597c-337">Видео коды, используемые получателем.</span><span class="sxs-lookup"><span data-stu-id="6597c-337">Video codes used by the receiver.</span></span> <span data-ttu-id="6597c-338">Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-codecdescription-table.md">таблицей кодекдескриптион в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="6597c-338">See the <a href="lync-server-2013-codecdescription-table.md">CodecDescription table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="6597c-339">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6597c-339">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6597c-340"><strong>Реквресолутионвидс</strong></span><span class="sxs-lookup"><span data-stu-id="6597c-340"><strong>RecvResolutionWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="6597c-341">целое</span><span class="sxs-lookup"><span data-stu-id="6597c-341">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6597c-342">Ширина разрешения, используемая получателем.</span><span class="sxs-lookup"><span data-stu-id="6597c-342">Resolution width used by the receiver.</span></span></p>
<p><span data-ttu-id="6597c-343">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6597c-343">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6597c-344"><strong>Реквресолутионхеигхт</strong></span><span class="sxs-lookup"><span data-stu-id="6597c-344"><strong>RecvResolutionHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="6597c-345">целое</span><span class="sxs-lookup"><span data-stu-id="6597c-345">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6597c-346">Высота разрешения, используемая получателем.</span><span class="sxs-lookup"><span data-stu-id="6597c-346">Resolution height used by the receiver.</span></span></p>
<p><span data-ttu-id="6597c-347">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6597c-347">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6597c-348"><strong>RecvFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="6597c-348"><strong>RecvFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="6597c-349">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="6597c-349">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6597c-350">Средняя частота кадров видео, используемая получателем.</span><span class="sxs-lookup"><span data-stu-id="6597c-350">Average video frame rate used by the receiver.</span></span></p>
<p><span data-ttu-id="6597c-351">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6597c-351">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6597c-352"><strong>Реквбитратемаксимум</strong></span><span class="sxs-lookup"><span data-stu-id="6597c-352"><strong>RecvBitRateMaximum</strong></span></span></p></td>
<td><p><span data-ttu-id="6597c-353">целое</span><span class="sxs-lookup"><span data-stu-id="6597c-353">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6597c-354">Максимальная скорость потока для получателя.</span><span class="sxs-lookup"><span data-stu-id="6597c-354">Maximum bit rate for the receiver.</span></span></p>
<p><span data-ttu-id="6597c-355">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6597c-355">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6597c-356"><strong>Реквбитратеавераже</strong></span><span class="sxs-lookup"><span data-stu-id="6597c-356"><strong>RecvBitRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="6597c-357">целое</span><span class="sxs-lookup"><span data-stu-id="6597c-357">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6597c-358">Средняя скорость потока для получателя.</span><span class="sxs-lookup"><span data-stu-id="6597c-358">Average bit rate for the receiver.</span></span></p>
<p><span data-ttu-id="6597c-359">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6597c-359">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6597c-360"><strong>Рекввидеостреамсмакс</strong></span><span class="sxs-lookup"><span data-stu-id="6597c-360"><strong>RecvVideoStreamsMax</strong></span></span></p></td>
<td><p><span data-ttu-id="6597c-361">целое</span><span class="sxs-lookup"><span data-stu-id="6597c-361">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6597c-362">Максимальное количество видеопотоков для получателя.</span><span class="sxs-lookup"><span data-stu-id="6597c-362">Maximum video streams for the receiver.</span></span></p>
<p><span data-ttu-id="6597c-363">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6597c-363">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6597c-364"><strong>Рекввидеостреамсмин</strong></span><span class="sxs-lookup"><span data-stu-id="6597c-364"><strong>RecvVideoStreamsMin</strong></span></span></p></td>
<td><p><span data-ttu-id="6597c-365">целое</span><span class="sxs-lookup"><span data-stu-id="6597c-365">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6597c-366">Минимальный поток видеозаписи для получателя.</span><span class="sxs-lookup"><span data-stu-id="6597c-366">Minimum video streams for the receiver.</span></span></p>
<p><span data-ttu-id="6597c-367">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6597c-367">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6597c-368"><strong>Рекввидеостреамсмоде</strong></span><span class="sxs-lookup"><span data-stu-id="6597c-368"><strong>RecvVideoStreamsMode</strong></span></span></p></td>
<td><p><span data-ttu-id="6597c-369">целое</span><span class="sxs-lookup"><span data-stu-id="6597c-369">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6597c-370">Режим видео (например, коллекция или один поток) получателя.</span><span class="sxs-lookup"><span data-stu-id="6597c-370">Video mode (for example, gallery or single stream) for the receiver.</span></span></p>
<p><span data-ttu-id="6597c-371">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6597c-371">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6597c-372"><strong>VideoPostFECPLR</strong></span><span class="sxs-lookup"><span data-stu-id="6597c-372"><strong>VideoPostFECPLR</strong></span></span></p></td>
<td><p><span data-ttu-id="6597c-373">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="6597c-373">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6597c-374">Применена ставка потери пакетов после исправления ошибки переадресации.</span><span class="sxs-lookup"><span data-stu-id="6597c-374">Packet loss rate after forward error correction has been applied.</span></span></p>
<p><span data-ttu-id="6597c-375">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6597c-375">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6597c-376"><strong>Динамиккапабилитиперцент</strong></span><span class="sxs-lookup"><span data-stu-id="6597c-376"><strong>DynamicCapabilityPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="6597c-377">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="6597c-377">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6597c-378">Процент времени, в течение которого был активен флаг динамической доступности.</span><span class="sxs-lookup"><span data-stu-id="6597c-378">Percentage of time that the dynamic capability flag was active.</span></span></p>
<p><span data-ttu-id="6597c-379">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6597c-379">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6597c-380"><strong>Ресолутионмин</strong></span><span class="sxs-lookup"><span data-stu-id="6597c-380"><strong>ResolutionMin</strong></span></span></p></td>
<td><p><span data-ttu-id="6597c-381">char (9)</span><span class="sxs-lookup"><span data-stu-id="6597c-381">char(9)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6597c-382">Минимальное разрешение, измеряемое во время звонка.</span><span class="sxs-lookup"><span data-stu-id="6597c-382">Minimum resolution measured during the call.</span></span></p>
<p><span data-ttu-id="6597c-383">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6597c-383">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6597c-384"><strong>Ловбитратекаллперцент</strong></span><span class="sxs-lookup"><span data-stu-id="6597c-384"><strong>LowBitRateCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="6597c-385">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="6597c-385">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6597c-386">Процент звонка ниже минимального порогового значения скорости (70 килобит в секунду).</span><span class="sxs-lookup"><span data-stu-id="6597c-386">Percentage of the call below the low bit rate threshold (70 kilobits per second).</span></span></p>
<p><span data-ttu-id="6597c-387">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6597c-387">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6597c-388"><strong>LowFrameRateCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="6597c-388"><strong>LowFrameRateCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="6597c-389">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="6597c-389">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6597c-390">Процент звонка ниже нижнего порогового значения частоты кадров (количество кадров в 7,5 в секунду, входящее).</span><span class="sxs-lookup"><span data-stu-id="6597c-390">Percentage of the call below the low frame rate threshold (7.5 frames per second, inbound).</span></span></p>
<p><span data-ttu-id="6597c-391">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6597c-391">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6597c-392"><strong>LowResolutionCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="6597c-392"><strong>LowResolutionCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="6597c-393">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="6597c-393">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6597c-394">Процент звонка, который выполнялся по низким разрешению.</span><span class="sxs-lookup"><span data-stu-id="6597c-394">Percentage of the call that occurred at the lowest resolution.</span></span></p>
<p><span data-ttu-id="6597c-395">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6597c-395">This column was introduced in Microsoft Lync Server 2013.</span></span></p>
<p><span data-ttu-id="6597c-396">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6597c-396">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6597c-397"><strong>Дуратионсекондс</strong></span><span class="sxs-lookup"><span data-stu-id="6597c-397"><strong>DurationSeconds</strong></span></span></p></td>
<td><p><span data-ttu-id="6597c-398">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="6597c-398">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6597c-399">Продолжительность звонка в секундах.</span><span class="sxs-lookup"><span data-stu-id="6597c-399">Length of the call in seconds.</span></span></p>
<p><span data-ttu-id="6597c-400">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6597c-400">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6597c-401"><strong>Исаггрегатеддата</strong></span><span class="sxs-lookup"><span data-stu-id="6597c-401"><strong>IsAggregatedData</strong></span></span></p></td>
<td><p><span data-ttu-id="6597c-402">бит</span><span class="sxs-lookup"><span data-stu-id="6597c-402">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6597c-403">Указывает, были ли данные объединены из нескольких вызовов.</span><span class="sxs-lookup"><span data-stu-id="6597c-403">Indicates whether the data has been aggregated from multiple calls.</span></span></p>
<p><span data-ttu-id="6597c-404">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6597c-404">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

