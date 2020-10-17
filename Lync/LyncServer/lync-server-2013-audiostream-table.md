---
title: 'Lync Server 2013: таблица таблица audiostream'
description: 'Lync Server 2013: таблица таблица audiostream.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: AudioStream table
ms:assetid: 49ccbbc3-2f73-45fc-80a6-e612535cbc10
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425961(v=OCS.15)
ms:contentKeyID: 48184077
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8af2e622e14c54fa4f9a6313e1b0dae8f2483132
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552345"
---
# <a name="audiostream-table-in-lync-server-2013"></a><span data-ttu-id="6f3e6-103">Таблица Таблица audiostream в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6f3e6-103">AudioStream table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6f3e6-104">_**Последнее изменение темы:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="6f3e6-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="6f3e6-105">Каждая запись представляет один аудиопоток.</span><span class="sxs-lookup"><span data-stu-id="6f3e6-105">Each record represents one audio stream.</span></span> <span data-ttu-id="6f3e6-106">Одна линия аудио мультимедиа обычно содержит два звуковых потока.</span><span class="sxs-lookup"><span data-stu-id="6f3e6-106">One audio media line usually contains two audio streams.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6f3e6-107"><strong>Column</strong></span><span class="sxs-lookup"><span data-stu-id="6f3e6-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="6f3e6-108"><strong>Тип данных</strong></span><span class="sxs-lookup"><span data-stu-id="6f3e6-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="6f3e6-109"><strong>Ключ или индекс</strong></span><span class="sxs-lookup"><span data-stu-id="6f3e6-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="6f3e6-110"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="6f3e6-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6f3e6-111"><strong>конференцедатетиме</strong></span><span class="sxs-lookup"><span data-stu-id="6f3e6-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="6f3e6-112">datetime</span><span class="sxs-lookup"><span data-stu-id="6f3e6-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="6f3e6-113">Primary</span><span class="sxs-lookup"><span data-stu-id="6f3e6-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="6f3e6-114">Ссылка из <a href="lync-server-2013-medialine-table.md">таблицы MediaLine в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="6f3e6-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f3e6-115"><strong>сессионсек</strong></span><span class="sxs-lookup"><span data-stu-id="6f3e6-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="6f3e6-116">int</span><span class="sxs-lookup"><span data-stu-id="6f3e6-116">int</span></span></p></td>
<td><p><span data-ttu-id="6f3e6-117">Primary</span><span class="sxs-lookup"><span data-stu-id="6f3e6-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="6f3e6-118">Ссылка из <a href="lync-server-2013-medialine-table.md">таблицы MediaLine в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="6f3e6-118">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6f3e6-119"><strong>медиалинелабел</strong></span><span class="sxs-lookup"><span data-stu-id="6f3e6-119"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="6f3e6-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="6f3e6-120">tinyint</span></span></p></td>
<td><p><span data-ttu-id="6f3e6-121">Primary</span><span class="sxs-lookup"><span data-stu-id="6f3e6-121">Primary</span></span></p></td>
<td><p><span data-ttu-id="6f3e6-122">Ссылка из <a href="lync-server-2013-medialine-table.md">таблицы MediaLine в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="6f3e6-122">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f3e6-123"><strong>стреамид</strong></span><span class="sxs-lookup"><span data-stu-id="6f3e6-123"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="6f3e6-124">int</span><span class="sxs-lookup"><span data-stu-id="6f3e6-124">int</span></span></p></td>
<td><p><span data-ttu-id="6f3e6-125">Primary</span><span class="sxs-lookup"><span data-stu-id="6f3e6-125">Primary</span></span></p></td>
<td><p><span data-ttu-id="6f3e6-126">Уникальный идентификатор в линии мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="6f3e6-126">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6f3e6-127"><strong>життеринтерарривал</strong></span><span class="sxs-lookup"><span data-stu-id="6f3e6-127"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="6f3e6-128">int</span><span class="sxs-lookup"><span data-stu-id="6f3e6-128">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="6f3e6-129">Средний уровень дрожания в сети на основе статистики протокола RTCP.</span><span class="sxs-lookup"><span data-stu-id="6f3e6-129">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f3e6-130"><strong>життеринтерарривалмакс</strong></span><span class="sxs-lookup"><span data-stu-id="6f3e6-130"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="6f3e6-131">int</span><span class="sxs-lookup"><span data-stu-id="6f3e6-131">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="6f3e6-132">Максимальный уровень дрожания в сети в течение вызова.</span><span class="sxs-lookup"><span data-stu-id="6f3e6-132">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6f3e6-133"><strong>паккетлоссрате</strong></span><span class="sxs-lookup"><span data-stu-id="6f3e6-133"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="6f3e6-134">десятичное число (5, 4)</span><span class="sxs-lookup"><span data-stu-id="6f3e6-134">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="6f3e6-135">Средний коэффициент потерь пакетов в течение вызова.</span><span class="sxs-lookup"><span data-stu-id="6f3e6-135">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f3e6-136"><strong>паккетлоссратемакс</strong></span><span class="sxs-lookup"><span data-stu-id="6f3e6-136"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="6f3e6-137">десятичное число (5, 4)</span><span class="sxs-lookup"><span data-stu-id="6f3e6-137">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="6f3e6-138">Максимальная потеря пакетов, наблюдавшаяся в течение вызова.</span><span class="sxs-lookup"><span data-stu-id="6f3e6-138">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6f3e6-139"><strong>бурстденсити</strong></span><span class="sxs-lookup"><span data-stu-id="6f3e6-139"><strong>BurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="6f3e6-140">десятичное число (9, 4)</span><span class="sxs-lookup"><span data-stu-id="6f3e6-140">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="6f3e6-141">Средняя плотность потери пакетов во время пакетов потерь во время вызова.</span><span class="sxs-lookup"><span data-stu-id="6f3e6-141">Average density of packet Loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f3e6-142"><strong>бурстдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="6f3e6-142"><strong>BurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="6f3e6-143">int</span><span class="sxs-lookup"><span data-stu-id="6f3e6-143">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="6f3e6-144">Средняя продолжительность потерь пакетов во время пиков потерь в течение вызова.</span><span class="sxs-lookup"><span data-stu-id="6f3e6-144">Average duration of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6f3e6-145"><strong>бурстгапденсити</strong></span><span class="sxs-lookup"><span data-stu-id="6f3e6-145"><strong>BurstGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="6f3e6-146">десятичное число (9, 4)</span><span class="sxs-lookup"><span data-stu-id="6f3e6-146">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="6f3e6-147">Средняя плотность потерь пакетов в промежутках между пиками потерь.</span><span class="sxs-lookup"><span data-stu-id="6f3e6-147">Average density of packet loss during gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f3e6-148"><strong>бурстгапдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="6f3e6-148"><strong>BurstGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="6f3e6-149">int</span><span class="sxs-lookup"><span data-stu-id="6f3e6-149">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="6f3e6-150">Средняя продолжительность промежутков между пиками потерь пакетов.</span><span class="sxs-lookup"><span data-stu-id="6f3e6-150">Average duration of gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6f3e6-151"><strong>паккетутилизатион</strong></span><span class="sxs-lookup"><span data-stu-id="6f3e6-151"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="6f3e6-152">Целое</span><span class="sxs-lookup"><span data-stu-id="6f3e6-152">Int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="6f3e6-153">Количество пакетов для аудиопотока.</span><span class="sxs-lookup"><span data-stu-id="6f3e6-153">Packet count for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f3e6-154"><strong>Самый полоса пропускания</strong></span><span class="sxs-lookup"><span data-stu-id="6f3e6-154"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="6f3e6-155">Целое</span><span class="sxs-lookup"><span data-stu-id="6f3e6-155">Int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="6f3e6-156">Оценка пропускной способности для аудиопотока.</span><span class="sxs-lookup"><span data-stu-id="6f3e6-156">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6f3e6-157"><strong>деградатионавг</strong></span><span class="sxs-lookup"><span data-stu-id="6f3e6-157"><strong>DegradationAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="6f3e6-158">десятичное число (3, 2)</span><span class="sxs-lookup"><span data-stu-id="6f3e6-158">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="6f3e6-p102">Снижение экспертной оценки качества (MOS) в сети для всего звонка в диапазоне от 0,0 до 5,0. Эта метрика показывает величину уменьшения MOS в сети, обусловленную дрожанием и потерей пакетов. Для приемлемого качества это значение должно быть меньше, чем 0,5.</span><span class="sxs-lookup"><span data-stu-id="6f3e6-p102">Network MOS Degradation for the whole call. Range is 0.0 to 5.0. This metric shows the amount the Network MOS was reduced because of jitter and packet loss. For acceptable quality it should less than 0.5.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f3e6-163"><strong>деградатионмакс</strong></span><span class="sxs-lookup"><span data-stu-id="6f3e6-163"><strong>DegradationMax</strong></span></span></p></td>
<td><p><span data-ttu-id="6f3e6-164">десятичное число (3, 2)</span><span class="sxs-lookup"><span data-stu-id="6f3e6-164">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="6f3e6-165">Максимальное снижение экспертной оценки качества (MOS) в сети во время звонка.</span><span class="sxs-lookup"><span data-stu-id="6f3e6-165">Maximum Network MOS degradation during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6f3e6-166"><strong>деградатионжиттеравг</strong></span><span class="sxs-lookup"><span data-stu-id="6f3e6-166"><strong>DegradationJitterAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="6f3e6-167">десятичное число (3, 2)</span><span class="sxs-lookup"><span data-stu-id="6f3e6-167">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="6f3e6-168">Снижение экспертной оценки качества (MOS) в сети, вызванное дрожанием.</span><span class="sxs-lookup"><span data-stu-id="6f3e6-168">Network MOS degradation caused by jitter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f3e6-169"><strong>деградатионпаккетлоссавг</strong></span><span class="sxs-lookup"><span data-stu-id="6f3e6-169"><strong>DegradationPacketLossAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="6f3e6-170">десятичное число (3, 2)</span><span class="sxs-lookup"><span data-stu-id="6f3e6-170">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="6f3e6-171">Снижение экспертной оценки качества (MOS) в сети, вызванное потерей пакетов.</span><span class="sxs-lookup"><span data-stu-id="6f3e6-171">Network MOS degradation caused by packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6f3e6-172"><strong>аудиопайлоаддескриптион</strong></span><span class="sxs-lookup"><span data-stu-id="6f3e6-172"><strong>AudioPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="6f3e6-173">int</span><span class="sxs-lookup"><span data-stu-id="6f3e6-173">int</span></span></p></td>
<td><p><span data-ttu-id="6f3e6-174">Правительства</span><span class="sxs-lookup"><span data-stu-id="6f3e6-174">Foreign</span></span></p></td>
<td><p><span data-ttu-id="6f3e6-175">Аудиокодек, используемый для вызова, на который ссылается таблица таблица payloaddescription.</span><span class="sxs-lookup"><span data-stu-id="6f3e6-175">The audio Codec used for the call, referenced from PayloadDescription Table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f3e6-176"><strong>аудиосамплерате</strong></span><span class="sxs-lookup"><span data-stu-id="6f3e6-176"><strong>AudioSampleRate</strong></span></span></p></td>
<td><p><span data-ttu-id="6f3e6-177">int</span><span class="sxs-lookup"><span data-stu-id="6f3e6-177">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="6f3e6-178">Частота выборки для аудиопотока.</span><span class="sxs-lookup"><span data-stu-id="6f3e6-178">Sampling rate for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6f3e6-179"><strong>Обработки</strong></span><span class="sxs-lookup"><span data-stu-id="6f3e6-179"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="6f3e6-180">int</span><span class="sxs-lookup"><span data-stu-id="6f3e6-180">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="6f3e6-181">Время приема-передачи на основе статистики RTCP.</span><span class="sxs-lookup"><span data-stu-id="6f3e6-181">Round trip time from RTCP statistics.</span></span> <span data-ttu-id="6f3e6-182">Для приемлемого качества это должно быть меньше 100 мс.</span><span class="sxs-lookup"><span data-stu-id="6f3e6-182">For acceptable quality this should be less than 100ms.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f3e6-183"><strong>раундтрипмакс</strong></span><span class="sxs-lookup"><span data-stu-id="6f3e6-183"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="6f3e6-184">int</span><span class="sxs-lookup"><span data-stu-id="6f3e6-184">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="6f3e6-185">Максимальное время приема-передачи для аудиопотока.</span><span class="sxs-lookup"><span data-stu-id="6f3e6-185">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6f3e6-186"><strong>овераллавгнетворкмос</strong></span><span class="sxs-lookup"><span data-stu-id="6f3e6-186"><strong>OverallAvgNetworkMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="6f3e6-187">десятичное число (3, 2)</span><span class="sxs-lookup"><span data-stu-id="6f3e6-187">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="6f3e6-188">Средняя экспертная оценка качества (MOS) в широкополосной сети для вызова.</span><span class="sxs-lookup"><span data-stu-id="6f3e6-188">Average wideband Network MOS for the call.</span></span> <span data-ttu-id="6f3e6-189">Значение этого показателя зависит от потерь пакетов, дрожания и используемого кодека.</span><span class="sxs-lookup"><span data-stu-id="6f3e6-189">This metric depends on the packet loss, jitter, and codec used.</span></span> <span data-ttu-id="6f3e6-190">Диапазон — [1,0 – 5,0].</span><span class="sxs-lookup"><span data-stu-id="6f3e6-190">Range is [1.0 to 5.0].</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f3e6-191"><strong>овераллминнетворкмос</strong></span><span class="sxs-lookup"><span data-stu-id="6f3e6-191"><strong>OverallMinNetworkMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="6f3e6-192">десятичное число (3, 2)</span><span class="sxs-lookup"><span data-stu-id="6f3e6-192">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="6f3e6-193">Минимум экспертная Network MOS для вызова.</span><span class="sxs-lookup"><span data-stu-id="6f3e6-193">The minimum wideband Network MOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6f3e6-194"><strong>Значение sendlistenmos</strong></span><span class="sxs-lookup"><span data-stu-id="6f3e6-194"><strong>SendListenMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="6f3e6-195">десятичное число (3, 2)</span><span class="sxs-lookup"><span data-stu-id="6f3e6-195">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="6f3e6-196">Средний прогнозируемый экспертная прослушивающий рейтинг MOS для звукового сигнала, в том числе уровень речи, уровень шума и характеристики устройства захвата.</span><span class="sxs-lookup"><span data-stu-id="6f3e6-196">The average predicted wideband Listening MOS score for audio sent, including speech level, noise level and capture device characteristics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f3e6-197"><strong>сендлистенмосмин</strong></span><span class="sxs-lookup"><span data-stu-id="6f3e6-197"><strong>SendListenMOSMin</strong></span></span></p></td>
<td><p><span data-ttu-id="6f3e6-198">десятичное число (3, 2)</span><span class="sxs-lookup"><span data-stu-id="6f3e6-198">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="6f3e6-199">Минимальное значение sendlistenmos для вызова.</span><span class="sxs-lookup"><span data-stu-id="6f3e6-199">The minimum SendListenMOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6f3e6-200"><strong>Значение recvlistenmos</strong></span><span class="sxs-lookup"><span data-stu-id="6f3e6-200"><strong>RecvListenMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="6f3e6-201">десятичное число (3, 2)</span><span class="sxs-lookup"><span data-stu-id="6f3e6-201">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="6f3e6-202">Средний прогнозируемый экспертная прослушивания MOS для звука, получаемого из сети, включая уровень речи, уровень шума, кодек, условия сети и характеристики устройства захвата.</span><span class="sxs-lookup"><span data-stu-id="6f3e6-202">The average predicted wideband Listening MOS score for audio received from the network including speech level, noise level, codec, network conditions and capture device characteristics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f3e6-203"><strong>реквлистенмосмин</strong></span><span class="sxs-lookup"><span data-stu-id="6f3e6-203"><strong>RecvListenMOSMin</strong></span></span></p></td>
<td><p><span data-ttu-id="6f3e6-204">десятичное число (3, 2)</span><span class="sxs-lookup"><span data-stu-id="6f3e6-204">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="6f3e6-205">Минимальное значение recvlistenmos для вызова.</span><span class="sxs-lookup"><span data-stu-id="6f3e6-205">The minimum RecvListenMOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6f3e6-206"><strong>аудиофекусед</strong></span><span class="sxs-lookup"><span data-stu-id="6f3e6-206"><strong>AudioFECUsed</strong></span></span></p></td>
<td><p><span data-ttu-id="6f3e6-207">Битовая</span><span class="sxs-lookup"><span data-stu-id="6f3e6-207">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6f3e6-208">Флаг, указывающий, использовался ли для вызова звуковая FEC.</span><span class="sxs-lookup"><span data-stu-id="6f3e6-208">Flag indicating if audio FEC was used for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f3e6-209"><strong>RatioConcealedSamplesAvg</strong></span><span class="sxs-lookup"><span data-stu-id="6f3e6-209"><strong>RatioConcealedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="6f3e6-210">десятичное число (5, 2)</span><span class="sxs-lookup"><span data-stu-id="6f3e6-210">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6f3e6-211">Среднее отношение числа скрытых образцов, созданных функцией восстановления звука, к обычным образцам.</span><span class="sxs-lookup"><span data-stu-id="6f3e6-211">Average ratio of concealed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6f3e6-212"><strong>ратиостретчедсамплесавг</strong></span><span class="sxs-lookup"><span data-stu-id="6f3e6-212"><strong>RatioStretchedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="6f3e6-213">десятичное число (5, 2)</span><span class="sxs-lookup"><span data-stu-id="6f3e6-213">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6f3e6-214">Среднее отношение числа растянутых образцов, созданных функцией восстановления звука, к обычным образцам.</span><span class="sxs-lookup"><span data-stu-id="6f3e6-214">Average ratio of stretched samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f3e6-215"><strong>ратиокомпресседсамплесавг</strong></span><span class="sxs-lookup"><span data-stu-id="6f3e6-215"><strong>RatioCompressedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="6f3e6-216">десятичное число (5, 2)</span><span class="sxs-lookup"><span data-stu-id="6f3e6-216">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6f3e6-217">Среднее отношение числа сжатых образцов, созданных функцией восстановления звука, к обычным образцам.</span><span class="sxs-lookup"><span data-stu-id="6f3e6-217">Average ratio of compressed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6f3e6-218"><strong>Получение</strong></span><span class="sxs-lookup"><span data-stu-id="6f3e6-218"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="6f3e6-219">Битовая</span><span class="sxs-lookup"><span data-stu-id="6f3e6-219">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="6f3e6-220">Получение потоковых данных на стороне получателя.</span><span class="sxs-lookup"><span data-stu-id="6f3e6-220">Stream data on receiver side is received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f3e6-221"><strong>Прав</strong></span><span class="sxs-lookup"><span data-stu-id="6f3e6-221"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="6f3e6-222">Битовая</span><span class="sxs-lookup"><span data-stu-id="6f3e6-222">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="6f3e6-223">Получение потоковых данных на стороне отправителя.</span><span class="sxs-lookup"><span data-stu-id="6f3e6-223">Stream data on sender side is received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6f3e6-224"><strong>сендерискаллерпаи</strong></span><span class="sxs-lookup"><span data-stu-id="6f3e6-224"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="6f3e6-225">Битовая</span><span class="sxs-lookup"><span data-stu-id="6f3e6-225">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="6f3e6-226">1 означает направление потока от вызывающего абонента к вызываемому абоненту.</span><span class="sxs-lookup"><span data-stu-id="6f3e6-226">1 means the stream direction is from the caller to the callee.</span></span></p>
<p><span data-ttu-id="6f3e6-227">0 означает направление потока от вызываемого абонента вызывающему абоненту.</span><span class="sxs-lookup"><span data-stu-id="6f3e6-227">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f3e6-228"><strong>життеринтерарривалсд</strong></span><span class="sxs-lookup"><span data-stu-id="6f3e6-228"><strong>JitterInterArrivalSD</strong></span></span></p></td>
<td><p><span data-ttu-id="6f3e6-229">float</span><span class="sxs-lookup"><span data-stu-id="6f3e6-229">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6f3e6-230">Стандартное отклонение для времени прибытия при колебании.</span><span class="sxs-lookup"><span data-stu-id="6f3e6-230">Standard deviation for jitter arrival times.</span></span></p>
<p><span data-ttu-id="6f3e6-231">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6f3e6-231">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6f3e6-232"><strong>концеалратиомакс</strong></span><span class="sxs-lookup"><span data-stu-id="6f3e6-232"><strong>ConcealRatioMax</strong></span></span></p></td>
<td><p><span data-ttu-id="6f3e6-233">float</span><span class="sxs-lookup"><span data-stu-id="6f3e6-233">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6f3e6-234">Максимальное соотношение пакетов, скрытые средством для воспроизведения.</span><span class="sxs-lookup"><span data-stu-id="6f3e6-234">Maximum ratio of packets concealed by the healer.</span></span></p>
<p><span data-ttu-id="6f3e6-235">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6f3e6-235">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f3e6-236"><strong>концеалратиосд</strong></span><span class="sxs-lookup"><span data-stu-id="6f3e6-236"><strong>ConcealRatioSD</strong></span></span></p></td>
<td><p><span data-ttu-id="6f3e6-237">float</span><span class="sxs-lookup"><span data-stu-id="6f3e6-237">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6f3e6-238">Стандартное отклонение для соотношения пакетов, которые скрываются средством "выбор".</span><span class="sxs-lookup"><span data-stu-id="6f3e6-238">Standard deviation for the ratio of packets concealed by the healer.</span></span></p>
<p><span data-ttu-id="6f3e6-239">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6f3e6-239">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6f3e6-240"><strong>хеалерпаккетдропратио</strong></span><span class="sxs-lookup"><span data-stu-id="6f3e6-240"><strong>HealerPacketDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="6f3e6-241">float</span><span class="sxs-lookup"><span data-stu-id="6f3e6-241">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6f3e6-242">Доля пакетов, отброшенных средством сброса по сравнению с общим количеством полученных пакетов.</span><span class="sxs-lookup"><span data-stu-id="6f3e6-242">Ratio of packets dropped by the healer compared to the total number of packets received.</span></span></p>
<p><span data-ttu-id="6f3e6-243">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6f3e6-243">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f3e6-244"><strong>хеалерфекпаккетуседратио</strong></span><span class="sxs-lookup"><span data-stu-id="6f3e6-244"><strong>HealerFECPacketUsedRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="6f3e6-245">float</span><span class="sxs-lookup"><span data-stu-id="6f3e6-245">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6f3e6-246">Доля использованных пакетов коррекции ошибок переадресации по сравнению с общим количеством полученных пакетов.</span><span class="sxs-lookup"><span data-stu-id="6f3e6-246">Ratio of used forward error correction packets compared to the total number of packets received.</span></span></p>
<p><span data-ttu-id="6f3e6-247">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6f3e6-247">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6f3e6-248"><strong>макскомпресседсамплес</strong></span><span class="sxs-lookup"><span data-stu-id="6f3e6-248"><strong>MaxCompressedSamples</strong></span></span></p></td>
<td><p><span data-ttu-id="6f3e6-249">float</span><span class="sxs-lookup"><span data-stu-id="6f3e6-249">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6f3e6-250">Максимальное число пакетов звукозаписи, сжатых средством завершения.</span><span class="sxs-lookup"><span data-stu-id="6f3e6-250">Maximum number of audio packets that were compressed by the healer.</span></span></p>
<p><span data-ttu-id="6f3e6-251">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6f3e6-251">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f3e6-252"><strong>лоссконжестионперцент</strong></span><span class="sxs-lookup"><span data-stu-id="6f3e6-252"><strong>LossCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="6f3e6-253">float</span><span class="sxs-lookup"><span data-stu-id="6f3e6-253">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6f3e6-254">Указывает процент времени, в течение которого вызов находился в состоянии перегрузки потерь.</span><span class="sxs-lookup"><span data-stu-id="6f3e6-254">Indicates the percentage of the time when the call was in a loss congestion state.</span></span></p>
<p><span data-ttu-id="6f3e6-255">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6f3e6-255">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6f3e6-256"><strong>делайконжестионперцент</strong></span><span class="sxs-lookup"><span data-stu-id="6f3e6-256"><strong>DelayCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="6f3e6-257">float</span><span class="sxs-lookup"><span data-stu-id="6f3e6-257">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6f3e6-258">Указывает процент вызова, в течение которого перегрузка была вызвана задержкой появления сетевых пакетов.</span><span class="sxs-lookup"><span data-stu-id="6f3e6-258">Indicates the percentage of the call during which congestion was caused by the delayed arrival of network packets.</span></span></p>
<p><span data-ttu-id="6f3e6-259">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6f3e6-259">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f3e6-260"><strong>контентиондетектедперцент</strong></span><span class="sxs-lookup"><span data-stu-id="6f3e6-260"><strong>ContentionDetectedPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="6f3e6-261">float</span><span class="sxs-lookup"><span data-stu-id="6f3e6-261">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6f3e6-262">Указывает процент времени, в течение которого вызов конкурирует за ресурсы сети.</span><span class="sxs-lookup"><span data-stu-id="6f3e6-262">Indicates the percentage of the time when the call was competing for network resources.</span></span></p>
<p><span data-ttu-id="6f3e6-263">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6f3e6-263">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6f3e6-264"><strong>бандвидсестмин</strong></span><span class="sxs-lookup"><span data-stu-id="6f3e6-264"><strong>BandwidthEstMin</strong></span></span></p></td>
<td><p><span data-ttu-id="6f3e6-265">int</span><span class="sxs-lookup"><span data-stu-id="6f3e6-265">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6f3e6-266">Минимальная сумма оценки пропускной способности, измеренной во время вызова.</span><span class="sxs-lookup"><span data-stu-id="6f3e6-266">Minimum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="6f3e6-267">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6f3e6-267">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f3e6-268"><strong>бандвидсестмакс</strong></span><span class="sxs-lookup"><span data-stu-id="6f3e6-268"><strong>BandwidthEstMax</strong></span></span></p></td>
<td><p><span data-ttu-id="6f3e6-269">int</span><span class="sxs-lookup"><span data-stu-id="6f3e6-269">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6f3e6-270">Максимальный объем оценки пропускной способности, измеренной во время вызова.</span><span class="sxs-lookup"><span data-stu-id="6f3e6-270">Maximum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="6f3e6-271">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6f3e6-271">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6f3e6-272"><strong>бандвидсестстддев</strong></span><span class="sxs-lookup"><span data-stu-id="6f3e6-272"><strong>BandwidthEstStdDev</strong></span></span></p></td>
<td><p><span data-ttu-id="6f3e6-273">int</span><span class="sxs-lookup"><span data-stu-id="6f3e6-273">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6f3e6-274">Стандартное отклонение оценки пропускной способности, измеренной во время вызова.</span><span class="sxs-lookup"><span data-stu-id="6f3e6-274">Standard deviation of the bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="6f3e6-275">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6f3e6-275">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f3e6-276"><strong>бандвидсеставже</strong></span><span class="sxs-lookup"><span data-stu-id="6f3e6-276"><strong>BandwidthEstAvge</strong></span></span></p></td>
<td><p><span data-ttu-id="6f3e6-277">int</span><span class="sxs-lookup"><span data-stu-id="6f3e6-277">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6f3e6-278">Средняя величина оценки пропускной способности, измеренной во время вызова.</span><span class="sxs-lookup"><span data-stu-id="6f3e6-278">Average amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="6f3e6-279">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6f3e6-279">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6f3e6-280"><strong>релативеоневайтотал</strong></span><span class="sxs-lookup"><span data-stu-id="6f3e6-280"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="6f3e6-281">float</span><span class="sxs-lookup"><span data-stu-id="6f3e6-281">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6f3e6-p105">Общая величина односторонней задержки. Относительная односторонняя задержка измеряет задержку между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="6f3e6-p105">Total amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="6f3e6-284">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6f3e6-284">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f3e6-285"><strong>релативеоневайавераже</strong></span><span class="sxs-lookup"><span data-stu-id="6f3e6-285"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="6f3e6-286">float</span><span class="sxs-lookup"><span data-stu-id="6f3e6-286">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6f3e6-p106">Средняя величина односторонней задержки. Относительная односторонняя задержка измеряет задержку между клиентом и сервером</span><span class="sxs-lookup"><span data-stu-id="6f3e6-p106">Average amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="6f3e6-289">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6f3e6-289">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6f3e6-290"><strong>релативеоневаймакс</strong></span><span class="sxs-lookup"><span data-stu-id="6f3e6-290"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="6f3e6-291">float</span><span class="sxs-lookup"><span data-stu-id="6f3e6-291">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6f3e6-p107">Максимальная величина односторонней задержки. Относительная односторонняя задержка измеряет задержку между клиентом и сервером</span><span class="sxs-lookup"><span data-stu-id="6f3e6-p107">Maximum amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="6f3e6-294">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6f3e6-294">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f3e6-295"><strong>релативеоневайбурстоккурренцес</strong></span><span class="sxs-lookup"><span data-stu-id="6f3e6-295"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="6f3e6-296">int</span><span class="sxs-lookup"><span data-stu-id="6f3e6-296">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6f3e6-p108">Общее число повторов пакетов в одну сторону. "Пакетная" передача представляет собой передачу, при которой данные передаются посредством случайных пакетов, а не в виде устойчивого потока. С помощью этой метрики измеряется поток данных между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="6f3e6-p108">Total one-way burst occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="6f3e6-300">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6f3e6-300">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6f3e6-301"><strong>релативеоневайбурстденсити</strong></span><span class="sxs-lookup"><span data-stu-id="6f3e6-301"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="6f3e6-302">float</span><span class="sxs-lookup"><span data-stu-id="6f3e6-302">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6f3e6-p109">Общая плотность пакетов в одну сторону. "Пакетная" передача представляет собой передачу, при которой данные передаются посредством случайных пакетов, а не в виде устойчивого потока. С помощью этой метрики измеряется поток данных между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="6f3e6-p109">Total one-way burst density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="6f3e6-306">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6f3e6-306">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f3e6-307"><strong>релативеоневайбурстдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="6f3e6-307"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="6f3e6-308">float</span><span class="sxs-lookup"><span data-stu-id="6f3e6-308">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6f3e6-p110">Общая длительность пакетов в одну сторону. "Пакетная" передача представляет собой передачу, при которой данные передаются посредством случайных пакетов, а не в виде устойчивого потока. С помощью этой метрики измеряется поток данных между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="6f3e6-p110">Total one-way burst duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="6f3e6-312">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6f3e6-312">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6f3e6-313"><strong>релативеоневайгапоккурренцес</strong></span><span class="sxs-lookup"><span data-stu-id="6f3e6-313"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="6f3e6-314">int</span><span class="sxs-lookup"><span data-stu-id="6f3e6-314">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6f3e6-p111">Общее число повторов разрывов в одну сторону. "Пакетная" передача представляет собой передачу, при которой данные передаются посредством случайных пакетов, а не в виде устойчивого потока; разрывы указывают задержку между этими пакетами. С помощью данной метрики измеряется поток данных между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="6f3e6-p111">Total one-way gap occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="6f3e6-318">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6f3e6-318">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f3e6-319"><strong>релативеоневайгапденсити</strong></span><span class="sxs-lookup"><span data-stu-id="6f3e6-319"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="6f3e6-320">float</span><span class="sxs-lookup"><span data-stu-id="6f3e6-320">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6f3e6-p112">Общая плотность разрывов в одну сторону. "Пакетная" передача представляет собой передачу, при которой данные передаются посредством случайных пакетов, а не в виде устойчивого потока; разрывы указывают задержку между этими пакетами. С помощью данной метрики измеряется поток данных между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="6f3e6-p112">Total one-way gap density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="6f3e6-324">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6f3e6-324">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6f3e6-325"><strong>релативеоневайгапдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="6f3e6-325"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="6f3e6-326">float</span><span class="sxs-lookup"><span data-stu-id="6f3e6-326">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6f3e6-p113">Общая длительность разрывов в одну сторону. "Пакетная" передача представляет собой передачу, при которой данные передаются посредством случайных пакетов, а не в виде устойчивого потока; разрывы указывают задержку между этими пакетами. С помощью данной метрики измеряется поток данных между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="6f3e6-p113">Total one-way gap duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="6f3e6-330">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6f3e6-330">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f3e6-331"><strong>декодестереоперцент</strong></span><span class="sxs-lookup"><span data-stu-id="6f3e6-331"><strong>DecodeStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="6f3e6-332">float</span><span class="sxs-lookup"><span data-stu-id="6f3e6-332">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6f3e6-333">Процент вызовов, декодированный как стерео.</span><span class="sxs-lookup"><span data-stu-id="6f3e6-333">Percentage of the call decoded as stereo.</span></span></p>
<p><span data-ttu-id="6f3e6-334">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6f3e6-334">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6f3e6-335"><strong>аекрендерстереоперцент</strong></span><span class="sxs-lookup"><span data-stu-id="6f3e6-335"><strong>AecRenderStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="6f3e6-336">float</span><span class="sxs-lookup"><span data-stu-id="6f3e6-336">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6f3e6-337">Процентное соотношение вызова, отображаемое в качестве стерео, средством подавления акустического эха.</span><span class="sxs-lookup"><span data-stu-id="6f3e6-337">Percentage of the call rendered as stereo by the acoustic echo canceller.</span></span></p>
<p><span data-ttu-id="6f3e6-338">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6f3e6-338">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f3e6-339"><strong>аудиопостфекплр</strong></span><span class="sxs-lookup"><span data-stu-id="6f3e6-339"><strong>AudioPostFECPLR</strong></span></span></p></td>
<td><p><span data-ttu-id="6f3e6-340">float</span><span class="sxs-lookup"><span data-stu-id="6f3e6-340">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6f3e6-341">Скорость потери пакетов после применения коррекции ошибок переадресации.</span><span class="sxs-lookup"><span data-stu-id="6f3e6-341">Packet loss rate after forward error correction has been applied.</span></span></p>
<p><span data-ttu-id="6f3e6-342">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6f3e6-342">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6f3e6-343"><strong>енкодестереоперцент</strong></span><span class="sxs-lookup"><span data-stu-id="6f3e6-343"><strong>EncodeStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="6f3e6-344">float</span><span class="sxs-lookup"><span data-stu-id="6f3e6-344">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6f3e6-345">Процент вызовов, закодированный как стерео.</span><span class="sxs-lookup"><span data-stu-id="6f3e6-345">Percentage of the call encoded as stereo.</span></span></p>
<p><span data-ttu-id="6f3e6-346">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6f3e6-346">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f3e6-347"><strong>аеккаптурестереоперцент</strong></span><span class="sxs-lookup"><span data-stu-id="6f3e6-347"><strong>AecCaptureStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="6f3e6-348">float</span><span class="sxs-lookup"><span data-stu-id="6f3e6-348">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6f3e6-349">Процентное соотношение вызовов, записанное в качестве стереосистемы, с помощью функции отмены акустического эха.</span><span class="sxs-lookup"><span data-stu-id="6f3e6-349">Percentage of the call captured as stereo by the acoustic echo canceller.</span></span></p>
<p><span data-ttu-id="6f3e6-350">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6f3e6-350">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

