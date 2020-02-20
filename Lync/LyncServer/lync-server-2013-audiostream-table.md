---
title: 'Lync Server 2013: таблица таблица audiostream'
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
ms.openlocfilehash: 0f169a00a9eff262d0229daf6e52110d64cf7a34
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145478"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="audiostream-table-in-lync-server-2013"></a><span data-ttu-id="84e2c-102">Таблица Таблица audiostream в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="84e2c-102">AudioStream table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="84e2c-103">_**Последнее изменение темы:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="84e2c-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="84e2c-104">Каждая запись представляет один аудиопоток.</span><span class="sxs-lookup"><span data-stu-id="84e2c-104">Each record represents one audio stream.</span></span> <span data-ttu-id="84e2c-105">Одна линия аудио мультимедиа обычно содержит два звуковых потока.</span><span class="sxs-lookup"><span data-stu-id="84e2c-105">One audio media line usually contains two audio streams.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="84e2c-106"><strong>Column</strong></span><span class="sxs-lookup"><span data-stu-id="84e2c-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="84e2c-107"><strong>Тип данных</strong></span><span class="sxs-lookup"><span data-stu-id="84e2c-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="84e2c-108"><strong>Ключ или индекс</strong></span><span class="sxs-lookup"><span data-stu-id="84e2c-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="84e2c-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="84e2c-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="84e2c-110"><strong>конференцедатетиме</strong></span><span class="sxs-lookup"><span data-stu-id="84e2c-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="84e2c-111">datetime</span><span class="sxs-lookup"><span data-stu-id="84e2c-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="84e2c-112">Primary</span><span class="sxs-lookup"><span data-stu-id="84e2c-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="84e2c-113">Ссылка из <a href="lync-server-2013-medialine-table.md">таблицы MediaLine в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="84e2c-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84e2c-114"><strong>сессионсек</strong></span><span class="sxs-lookup"><span data-stu-id="84e2c-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="84e2c-115">int</span><span class="sxs-lookup"><span data-stu-id="84e2c-115">int</span></span></p></td>
<td><p><span data-ttu-id="84e2c-116">Primary</span><span class="sxs-lookup"><span data-stu-id="84e2c-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="84e2c-117">Ссылка из <a href="lync-server-2013-medialine-table.md">таблицы MediaLine в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="84e2c-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84e2c-118"><strong>медиалинелабел</strong></span><span class="sxs-lookup"><span data-stu-id="84e2c-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="84e2c-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="84e2c-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="84e2c-120">Primary</span><span class="sxs-lookup"><span data-stu-id="84e2c-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="84e2c-121">Ссылка из <a href="lync-server-2013-medialine-table.md">таблицы MediaLine в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="84e2c-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84e2c-122"><strong>стреамид</strong></span><span class="sxs-lookup"><span data-stu-id="84e2c-122"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="84e2c-123">int</span><span class="sxs-lookup"><span data-stu-id="84e2c-123">int</span></span></p></td>
<td><p><span data-ttu-id="84e2c-124">Primary</span><span class="sxs-lookup"><span data-stu-id="84e2c-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="84e2c-125">Уникальный идентификатор в линии мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="84e2c-125">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84e2c-126"><strong>життеринтерарривал</strong></span><span class="sxs-lookup"><span data-stu-id="84e2c-126"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="84e2c-127">int</span><span class="sxs-lookup"><span data-stu-id="84e2c-127">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="84e2c-128">Средний уровень дрожания в сети на основе статистики протокола RTCP.</span><span class="sxs-lookup"><span data-stu-id="84e2c-128">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84e2c-129"><strong>життеринтерарривалмакс</strong></span><span class="sxs-lookup"><span data-stu-id="84e2c-129"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="84e2c-130">int</span><span class="sxs-lookup"><span data-stu-id="84e2c-130">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="84e2c-131">Максимальный уровень дрожания в сети в течение вызова.</span><span class="sxs-lookup"><span data-stu-id="84e2c-131">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84e2c-132"><strong>паккетлоссрате</strong></span><span class="sxs-lookup"><span data-stu-id="84e2c-132"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="84e2c-133">десятичное число (5, 4)</span><span class="sxs-lookup"><span data-stu-id="84e2c-133">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="84e2c-134">Средний коэффициент потерь пакетов в течение вызова.</span><span class="sxs-lookup"><span data-stu-id="84e2c-134">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84e2c-135"><strong>паккетлоссратемакс</strong></span><span class="sxs-lookup"><span data-stu-id="84e2c-135"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="84e2c-136">десятичное число (5, 4)</span><span class="sxs-lookup"><span data-stu-id="84e2c-136">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="84e2c-137">Максимальная потеря пакетов, наблюдавшаяся в течение вызова.</span><span class="sxs-lookup"><span data-stu-id="84e2c-137">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84e2c-138"><strong>бурстденсити</strong></span><span class="sxs-lookup"><span data-stu-id="84e2c-138"><strong>BurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="84e2c-139">десятичное число (9, 4)</span><span class="sxs-lookup"><span data-stu-id="84e2c-139">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="84e2c-140">Средняя плотность потери пакетов во время пакетов потерь во время вызова.</span><span class="sxs-lookup"><span data-stu-id="84e2c-140">Average density of packet Loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84e2c-141"><strong>бурстдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="84e2c-141"><strong>BurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="84e2c-142">int</span><span class="sxs-lookup"><span data-stu-id="84e2c-142">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="84e2c-143">Средняя продолжительность потерь пакетов во время пиков потерь в течение вызова.</span><span class="sxs-lookup"><span data-stu-id="84e2c-143">Average duration of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84e2c-144"><strong>бурстгапденсити</strong></span><span class="sxs-lookup"><span data-stu-id="84e2c-144"><strong>BurstGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="84e2c-145">десятичное число (9, 4)</span><span class="sxs-lookup"><span data-stu-id="84e2c-145">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="84e2c-146">Средняя плотность потерь пакетов в промежутках между пиками потерь.</span><span class="sxs-lookup"><span data-stu-id="84e2c-146">Average density of packet loss during gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84e2c-147"><strong>бурстгапдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="84e2c-147"><strong>BurstGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="84e2c-148">int</span><span class="sxs-lookup"><span data-stu-id="84e2c-148">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="84e2c-149">Средняя продолжительность промежутков между пиками потерь пакетов.</span><span class="sxs-lookup"><span data-stu-id="84e2c-149">Average duration of gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84e2c-150"><strong>паккетутилизатион</strong></span><span class="sxs-lookup"><span data-stu-id="84e2c-150"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="84e2c-151">Целое</span><span class="sxs-lookup"><span data-stu-id="84e2c-151">Int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="84e2c-152">Количество пакетов для аудиопотока.</span><span class="sxs-lookup"><span data-stu-id="84e2c-152">Packet count for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84e2c-153"><strong>Самый полоса пропускания</strong></span><span class="sxs-lookup"><span data-stu-id="84e2c-153"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="84e2c-154">Целое</span><span class="sxs-lookup"><span data-stu-id="84e2c-154">Int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="84e2c-155">Оценка пропускной способности для аудиопотока.</span><span class="sxs-lookup"><span data-stu-id="84e2c-155">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84e2c-156"><strong>деградатионавг</strong></span><span class="sxs-lookup"><span data-stu-id="84e2c-156"><strong>DegradationAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="84e2c-157">десятичное число (3, 2)</span><span class="sxs-lookup"><span data-stu-id="84e2c-157">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="84e2c-p102">Снижение экспертной оценки качества (MOS) в сети для всего звонка в диапазоне от 0,0 до 5,0. Эта метрика показывает величину уменьшения MOS в сети, обусловленную дрожанием и потерей пакетов. Для приемлемого качества это значение должно быть меньше, чем 0,5.</span><span class="sxs-lookup"><span data-stu-id="84e2c-p102">Network MOS Degradation for the whole call. Range is 0.0 to 5.0. This metric shows the amount the Network MOS was reduced because of jitter and packet loss. For acceptable quality it should less than 0.5.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84e2c-162"><strong>деградатионмакс</strong></span><span class="sxs-lookup"><span data-stu-id="84e2c-162"><strong>DegradationMax</strong></span></span></p></td>
<td><p><span data-ttu-id="84e2c-163">десятичное число (3, 2)</span><span class="sxs-lookup"><span data-stu-id="84e2c-163">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="84e2c-164">Максимальное снижение экспертной оценки качества (MOS) в сети во время звонка.</span><span class="sxs-lookup"><span data-stu-id="84e2c-164">Maximum Network MOS degradation during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84e2c-165"><strong>деградатионжиттеравг</strong></span><span class="sxs-lookup"><span data-stu-id="84e2c-165"><strong>DegradationJitterAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="84e2c-166">десятичное число (3, 2)</span><span class="sxs-lookup"><span data-stu-id="84e2c-166">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="84e2c-167">Снижение экспертной оценки качества (MOS) в сети, вызванное дрожанием.</span><span class="sxs-lookup"><span data-stu-id="84e2c-167">Network MOS degradation caused by jitter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84e2c-168"><strong>деградатионпаккетлоссавг</strong></span><span class="sxs-lookup"><span data-stu-id="84e2c-168"><strong>DegradationPacketLossAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="84e2c-169">десятичное число (3, 2)</span><span class="sxs-lookup"><span data-stu-id="84e2c-169">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="84e2c-170">Снижение экспертной оценки качества (MOS) в сети, вызванное потерей пакетов.</span><span class="sxs-lookup"><span data-stu-id="84e2c-170">Network MOS degradation caused by packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84e2c-171"><strong>аудиопайлоаддескриптион</strong></span><span class="sxs-lookup"><span data-stu-id="84e2c-171"><strong>AudioPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="84e2c-172">int</span><span class="sxs-lookup"><span data-stu-id="84e2c-172">int</span></span></p></td>
<td><p><span data-ttu-id="84e2c-173">Правительства</span><span class="sxs-lookup"><span data-stu-id="84e2c-173">Foreign</span></span></p></td>
<td><p><span data-ttu-id="84e2c-174">Аудиокодек, используемый для вызова, на который ссылается таблица таблица payloaddescription.</span><span class="sxs-lookup"><span data-stu-id="84e2c-174">The audio Codec used for the call, referenced from PayloadDescription Table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84e2c-175"><strong>аудиосамплерате</strong></span><span class="sxs-lookup"><span data-stu-id="84e2c-175"><strong>AudioSampleRate</strong></span></span></p></td>
<td><p><span data-ttu-id="84e2c-176">int</span><span class="sxs-lookup"><span data-stu-id="84e2c-176">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="84e2c-177">Частота выборки для аудиопотока.</span><span class="sxs-lookup"><span data-stu-id="84e2c-177">Sampling rate for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84e2c-178"><strong>Обработки</strong></span><span class="sxs-lookup"><span data-stu-id="84e2c-178"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="84e2c-179">int</span><span class="sxs-lookup"><span data-stu-id="84e2c-179">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="84e2c-180">Время приема-передачи на основе статистики RTCP.</span><span class="sxs-lookup"><span data-stu-id="84e2c-180">Round trip time from RTCP statistics.</span></span> <span data-ttu-id="84e2c-181">Для приемлемого качества это должно быть меньше 100 мс.</span><span class="sxs-lookup"><span data-stu-id="84e2c-181">For acceptable quality this should be less than 100ms.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84e2c-182"><strong>раундтрипмакс</strong></span><span class="sxs-lookup"><span data-stu-id="84e2c-182"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="84e2c-183">int</span><span class="sxs-lookup"><span data-stu-id="84e2c-183">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="84e2c-184">Максимальное время приема-передачи для аудиопотока.</span><span class="sxs-lookup"><span data-stu-id="84e2c-184">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84e2c-185"><strong>овераллавгнетворкмос</strong></span><span class="sxs-lookup"><span data-stu-id="84e2c-185"><strong>OverallAvgNetworkMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="84e2c-186">десятичное число (3, 2)</span><span class="sxs-lookup"><span data-stu-id="84e2c-186">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="84e2c-187">Средняя экспертная оценка качества (MOS) в широкополосной сети для вызова.</span><span class="sxs-lookup"><span data-stu-id="84e2c-187">Average wideband Network MOS for the call.</span></span> <span data-ttu-id="84e2c-188">Значение этого показателя зависит от потерь пакетов, дрожания и используемого кодека.</span><span class="sxs-lookup"><span data-stu-id="84e2c-188">This metric depends on the packet loss, jitter, and codec used.</span></span> <span data-ttu-id="84e2c-189">Диапазон — [1,0 – 5,0].</span><span class="sxs-lookup"><span data-stu-id="84e2c-189">Range is [1.0 to 5.0].</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84e2c-190"><strong>овераллминнетворкмос</strong></span><span class="sxs-lookup"><span data-stu-id="84e2c-190"><strong>OverallMinNetworkMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="84e2c-191">десятичное число (3, 2)</span><span class="sxs-lookup"><span data-stu-id="84e2c-191">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="84e2c-192">Минимум экспертная Network MOS для вызова.</span><span class="sxs-lookup"><span data-stu-id="84e2c-192">The minimum wideband Network MOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84e2c-193"><strong>Значение sendlistenmos</strong></span><span class="sxs-lookup"><span data-stu-id="84e2c-193"><strong>SendListenMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="84e2c-194">десятичное число (3, 2)</span><span class="sxs-lookup"><span data-stu-id="84e2c-194">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="84e2c-195">Средний прогнозируемый экспертная прослушивающий рейтинг MOS для звукового сигнала, в том числе уровень речи, уровень шума и характеристики устройства захвата.</span><span class="sxs-lookup"><span data-stu-id="84e2c-195">The average predicted wideband Listening MOS score for audio sent, including speech level, noise level and capture device characteristics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84e2c-196"><strong>сендлистенмосмин</strong></span><span class="sxs-lookup"><span data-stu-id="84e2c-196"><strong>SendListenMOSMin</strong></span></span></p></td>
<td><p><span data-ttu-id="84e2c-197">десятичное число (3, 2)</span><span class="sxs-lookup"><span data-stu-id="84e2c-197">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="84e2c-198">Минимальное значение sendlistenmos для вызова.</span><span class="sxs-lookup"><span data-stu-id="84e2c-198">The minimum SendListenMOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84e2c-199"><strong>Значение recvlistenmos</strong></span><span class="sxs-lookup"><span data-stu-id="84e2c-199"><strong>RecvListenMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="84e2c-200">десятичное число (3, 2)</span><span class="sxs-lookup"><span data-stu-id="84e2c-200">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="84e2c-201">Средний прогнозируемый экспертная прослушивания MOS для звука, получаемого из сети, включая уровень речи, уровень шума, кодек, условия сети и характеристики устройства захвата.</span><span class="sxs-lookup"><span data-stu-id="84e2c-201">The average predicted wideband Listening MOS score for audio received from the network including speech level, noise level, codec, network conditions and capture device characteristics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84e2c-202"><strong>реквлистенмосмин</strong></span><span class="sxs-lookup"><span data-stu-id="84e2c-202"><strong>RecvListenMOSMin</strong></span></span></p></td>
<td><p><span data-ttu-id="84e2c-203">десятичное число (3, 2)</span><span class="sxs-lookup"><span data-stu-id="84e2c-203">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="84e2c-204">Минимальное значение recvlistenmos для вызова.</span><span class="sxs-lookup"><span data-stu-id="84e2c-204">The minimum RecvListenMOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84e2c-205"><strong>аудиофекусед</strong></span><span class="sxs-lookup"><span data-stu-id="84e2c-205"><strong>AudioFECUsed</strong></span></span></p></td>
<td><p><span data-ttu-id="84e2c-206">Битовая</span><span class="sxs-lookup"><span data-stu-id="84e2c-206">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="84e2c-207">Флаг, указывающий, использовался ли для вызова звуковая FEC.</span><span class="sxs-lookup"><span data-stu-id="84e2c-207">Flag indicating if audio FEC was used for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84e2c-208"><strong>RatioConcealedSamplesAvg</strong></span><span class="sxs-lookup"><span data-stu-id="84e2c-208"><strong>RatioConcealedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="84e2c-209">десятичное число (5, 2)</span><span class="sxs-lookup"><span data-stu-id="84e2c-209">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="84e2c-210">Среднее отношение числа скрытых образцов, созданных функцией восстановления звука, к обычным образцам.</span><span class="sxs-lookup"><span data-stu-id="84e2c-210">Average ratio of concealed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84e2c-211"><strong>ратиостретчедсамплесавг</strong></span><span class="sxs-lookup"><span data-stu-id="84e2c-211"><strong>RatioStretchedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="84e2c-212">десятичное число (5, 2)</span><span class="sxs-lookup"><span data-stu-id="84e2c-212">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="84e2c-213">Среднее отношение числа растянутых образцов, созданных функцией восстановления звука, к обычным образцам.</span><span class="sxs-lookup"><span data-stu-id="84e2c-213">Average ratio of stretched samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84e2c-214"><strong>ратиокомпресседсамплесавг</strong></span><span class="sxs-lookup"><span data-stu-id="84e2c-214"><strong>RatioCompressedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="84e2c-215">десятичное число (5, 2)</span><span class="sxs-lookup"><span data-stu-id="84e2c-215">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="84e2c-216">Среднее отношение числа сжатых образцов, созданных функцией восстановления звука, к обычным образцам.</span><span class="sxs-lookup"><span data-stu-id="84e2c-216">Average ratio of compressed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84e2c-217"><strong>Получение</strong></span><span class="sxs-lookup"><span data-stu-id="84e2c-217"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="84e2c-218">Битовая</span><span class="sxs-lookup"><span data-stu-id="84e2c-218">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="84e2c-219">Получение потоковых данных на стороне получателя.</span><span class="sxs-lookup"><span data-stu-id="84e2c-219">Stream data on receiver side is received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84e2c-220"><strong>Прав</strong></span><span class="sxs-lookup"><span data-stu-id="84e2c-220"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="84e2c-221">Битовая</span><span class="sxs-lookup"><span data-stu-id="84e2c-221">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="84e2c-222">Получение потоковых данных на стороне отправителя.</span><span class="sxs-lookup"><span data-stu-id="84e2c-222">Stream data on sender side is received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84e2c-223"><strong>сендерискаллерпаи</strong></span><span class="sxs-lookup"><span data-stu-id="84e2c-223"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="84e2c-224">Битовая</span><span class="sxs-lookup"><span data-stu-id="84e2c-224">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="84e2c-225">1 означает направление потока от вызывающего абонента к вызываемому абоненту.</span><span class="sxs-lookup"><span data-stu-id="84e2c-225">1 means the stream direction is from the caller to the callee.</span></span></p>
<p><span data-ttu-id="84e2c-226">0 означает направление потока от вызываемого абонента вызывающему абоненту.</span><span class="sxs-lookup"><span data-stu-id="84e2c-226">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84e2c-227"><strong>життеринтерарривалсд</strong></span><span class="sxs-lookup"><span data-stu-id="84e2c-227"><strong>JitterInterArrivalSD</strong></span></span></p></td>
<td><p><span data-ttu-id="84e2c-228">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="84e2c-228">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="84e2c-229">Стандартное отклонение для времени прибытия при колебании.</span><span class="sxs-lookup"><span data-stu-id="84e2c-229">Standard deviation for jitter arrival times.</span></span></p>
<p><span data-ttu-id="84e2c-230">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="84e2c-230">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84e2c-231"><strong>концеалратиомакс</strong></span><span class="sxs-lookup"><span data-stu-id="84e2c-231"><strong>ConcealRatioMax</strong></span></span></p></td>
<td><p><span data-ttu-id="84e2c-232">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="84e2c-232">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="84e2c-233">Максимальное соотношение пакетов, скрытые средством для воспроизведения.</span><span class="sxs-lookup"><span data-stu-id="84e2c-233">Maximum ratio of packets concealed by the healer.</span></span></p>
<p><span data-ttu-id="84e2c-234">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="84e2c-234">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84e2c-235"><strong>концеалратиосд</strong></span><span class="sxs-lookup"><span data-stu-id="84e2c-235"><strong>ConcealRatioSD</strong></span></span></p></td>
<td><p><span data-ttu-id="84e2c-236">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="84e2c-236">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="84e2c-237">Стандартное отклонение для соотношения пакетов, которые скрываются средством "выбор".</span><span class="sxs-lookup"><span data-stu-id="84e2c-237">Standard deviation for the ratio of packets concealed by the healer.</span></span></p>
<p><span data-ttu-id="84e2c-238">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="84e2c-238">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84e2c-239"><strong>хеалерпаккетдропратио</strong></span><span class="sxs-lookup"><span data-stu-id="84e2c-239"><strong>HealerPacketDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="84e2c-240">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="84e2c-240">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="84e2c-241">Доля пакетов, отброшенных средством сброса по сравнению с общим количеством полученных пакетов.</span><span class="sxs-lookup"><span data-stu-id="84e2c-241">Ratio of packets dropped by the healer compared to the total number of packets received.</span></span></p>
<p><span data-ttu-id="84e2c-242">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="84e2c-242">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84e2c-243"><strong>хеалерфекпаккетуседратио</strong></span><span class="sxs-lookup"><span data-stu-id="84e2c-243"><strong>HealerFECPacketUsedRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="84e2c-244">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="84e2c-244">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="84e2c-245">Доля использованных пакетов коррекции ошибок переадресации по сравнению с общим количеством полученных пакетов.</span><span class="sxs-lookup"><span data-stu-id="84e2c-245">Ratio of used forward error correction packets compared to the total number of packets received.</span></span></p>
<p><span data-ttu-id="84e2c-246">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="84e2c-246">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84e2c-247"><strong>макскомпресседсамплес</strong></span><span class="sxs-lookup"><span data-stu-id="84e2c-247"><strong>MaxCompressedSamples</strong></span></span></p></td>
<td><p><span data-ttu-id="84e2c-248">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="84e2c-248">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="84e2c-249">Максимальное число пакетов звукозаписи, сжатых средством завершения.</span><span class="sxs-lookup"><span data-stu-id="84e2c-249">Maximum number of audio packets that were compressed by the healer.</span></span></p>
<p><span data-ttu-id="84e2c-250">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="84e2c-250">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84e2c-251"><strong>лоссконжестионперцент</strong></span><span class="sxs-lookup"><span data-stu-id="84e2c-251"><strong>LossCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="84e2c-252">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="84e2c-252">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="84e2c-253">Указывает процент времени, в течение которого вызов находился в состоянии перегрузки потерь.</span><span class="sxs-lookup"><span data-stu-id="84e2c-253">Indicates the percentage of the time when the call was in a loss congestion state.</span></span></p>
<p><span data-ttu-id="84e2c-254">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="84e2c-254">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84e2c-255"><strong>делайконжестионперцент</strong></span><span class="sxs-lookup"><span data-stu-id="84e2c-255"><strong>DelayCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="84e2c-256">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="84e2c-256">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="84e2c-257">Указывает процент вызова, в течение которого перегрузка была вызвана задержкой появления сетевых пакетов.</span><span class="sxs-lookup"><span data-stu-id="84e2c-257">Indicates the percentage of the call during which congestion was caused by the delayed arrival of network packets.</span></span></p>
<p><span data-ttu-id="84e2c-258">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="84e2c-258">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84e2c-259"><strong>контентиондетектедперцент</strong></span><span class="sxs-lookup"><span data-stu-id="84e2c-259"><strong>ContentionDetectedPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="84e2c-260">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="84e2c-260">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="84e2c-261">Указывает процент времени, в течение которого вызов конкурирует за ресурсы сети.</span><span class="sxs-lookup"><span data-stu-id="84e2c-261">Indicates the percentage of the time when the call was competing for network resources.</span></span></p>
<p><span data-ttu-id="84e2c-262">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="84e2c-262">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84e2c-263"><strong>бандвидсестмин</strong></span><span class="sxs-lookup"><span data-stu-id="84e2c-263"><strong>BandwidthEstMin</strong></span></span></p></td>
<td><p><span data-ttu-id="84e2c-264">int</span><span class="sxs-lookup"><span data-stu-id="84e2c-264">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="84e2c-265">Минимальная сумма оценки пропускной способности, измеренной во время вызова.</span><span class="sxs-lookup"><span data-stu-id="84e2c-265">Minimum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="84e2c-266">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="84e2c-266">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84e2c-267"><strong>бандвидсестмакс</strong></span><span class="sxs-lookup"><span data-stu-id="84e2c-267"><strong>BandwidthEstMax</strong></span></span></p></td>
<td><p><span data-ttu-id="84e2c-268">int</span><span class="sxs-lookup"><span data-stu-id="84e2c-268">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="84e2c-269">Максимальный объем оценки пропускной способности, измеренной во время вызова.</span><span class="sxs-lookup"><span data-stu-id="84e2c-269">Maximum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="84e2c-270">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="84e2c-270">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84e2c-271"><strong>бандвидсестстддев</strong></span><span class="sxs-lookup"><span data-stu-id="84e2c-271"><strong>BandwidthEstStdDev</strong></span></span></p></td>
<td><p><span data-ttu-id="84e2c-272">int</span><span class="sxs-lookup"><span data-stu-id="84e2c-272">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="84e2c-273">Стандартное отклонение оценки пропускной способности, измеренной во время вызова.</span><span class="sxs-lookup"><span data-stu-id="84e2c-273">Standard deviation of the bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="84e2c-274">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="84e2c-274">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84e2c-275"><strong>бандвидсеставже</strong></span><span class="sxs-lookup"><span data-stu-id="84e2c-275"><strong>BandwidthEstAvge</strong></span></span></p></td>
<td><p><span data-ttu-id="84e2c-276">int</span><span class="sxs-lookup"><span data-stu-id="84e2c-276">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="84e2c-277">Средняя величина оценки пропускной способности, измеренной во время вызова.</span><span class="sxs-lookup"><span data-stu-id="84e2c-277">Average amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="84e2c-278">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="84e2c-278">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84e2c-279"><strong>релативеоневайтотал</strong></span><span class="sxs-lookup"><span data-stu-id="84e2c-279"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="84e2c-280">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="84e2c-280">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="84e2c-p105">Общая величина односторонней задержки. Относительная односторонняя задержка измеряет задержку между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="84e2c-p105">Total amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="84e2c-283">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="84e2c-283">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84e2c-284"><strong>релативеоневайавераже</strong></span><span class="sxs-lookup"><span data-stu-id="84e2c-284"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="84e2c-285">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="84e2c-285">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="84e2c-p106">Средняя величина односторонней задержки. Относительная односторонняя задержка измеряет задержку между клиентом и сервером</span><span class="sxs-lookup"><span data-stu-id="84e2c-p106">Average amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="84e2c-288">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="84e2c-288">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84e2c-289"><strong>релативеоневаймакс</strong></span><span class="sxs-lookup"><span data-stu-id="84e2c-289"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="84e2c-290">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="84e2c-290">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="84e2c-p107">Максимальная величина односторонней задержки. Относительная односторонняя задержка измеряет задержку между клиентом и сервером</span><span class="sxs-lookup"><span data-stu-id="84e2c-p107">Maximum amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="84e2c-293">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="84e2c-293">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84e2c-294"><strong>релативеоневайбурстоккурренцес</strong></span><span class="sxs-lookup"><span data-stu-id="84e2c-294"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="84e2c-295">int</span><span class="sxs-lookup"><span data-stu-id="84e2c-295">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="84e2c-p108">Общее число повторов пакетов в одну сторону. "Пакетная" передача представляет собой передачу, при которой данные передаются посредством случайных пакетов, а не в виде устойчивого потока. С помощью этой метрики измеряется поток данных между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="84e2c-p108">Total one-way burst occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="84e2c-299">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="84e2c-299">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84e2c-300"><strong>релативеоневайбурстденсити</strong></span><span class="sxs-lookup"><span data-stu-id="84e2c-300"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="84e2c-301">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="84e2c-301">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="84e2c-p109">Общая плотность пакетов в одну сторону. "Пакетная" передача представляет собой передачу, при которой данные передаются посредством случайных пакетов, а не в виде устойчивого потока. С помощью этой метрики измеряется поток данных между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="84e2c-p109">Total one-way burst density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="84e2c-305">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="84e2c-305">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84e2c-306"><strong>релативеоневайбурстдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="84e2c-306"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="84e2c-307">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="84e2c-307">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="84e2c-p110">Общая длительность пакетов в одну сторону. "Пакетная" передача представляет собой передачу, при которой данные передаются посредством случайных пакетов, а не в виде устойчивого потока. С помощью этой метрики измеряется поток данных между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="84e2c-p110">Total one-way burst duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="84e2c-311">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="84e2c-311">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84e2c-312"><strong>релативеоневайгапоккурренцес</strong></span><span class="sxs-lookup"><span data-stu-id="84e2c-312"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="84e2c-313">int</span><span class="sxs-lookup"><span data-stu-id="84e2c-313">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="84e2c-p111">Общее число повторов разрывов в одну сторону. "Пакетная" передача представляет собой передачу, при которой данные передаются посредством случайных пакетов, а не в виде устойчивого потока; разрывы указывают задержку между этими пакетами. С помощью данной метрики измеряется поток данных между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="84e2c-p111">Total one-way gap occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="84e2c-317">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="84e2c-317">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84e2c-318"><strong>релативеоневайгапденсити</strong></span><span class="sxs-lookup"><span data-stu-id="84e2c-318"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="84e2c-319">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="84e2c-319">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="84e2c-p112">Общая плотность разрывов в одну сторону. "Пакетная" передача представляет собой передачу, при которой данные передаются посредством случайных пакетов, а не в виде устойчивого потока; разрывы указывают задержку между этими пакетами. С помощью данной метрики измеряется поток данных между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="84e2c-p112">Total one-way gap density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="84e2c-323">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="84e2c-323">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84e2c-324"><strong>релативеоневайгапдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="84e2c-324"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="84e2c-325">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="84e2c-325">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="84e2c-p113">Общая длительность разрывов в одну сторону. "Пакетная" передача представляет собой передачу, при которой данные передаются посредством случайных пакетов, а не в виде устойчивого потока; разрывы указывают задержку между этими пакетами. С помощью данной метрики измеряется поток данных между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="84e2c-p113">Total one-way gap duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="84e2c-329">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="84e2c-329">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84e2c-330"><strong>декодестереоперцент</strong></span><span class="sxs-lookup"><span data-stu-id="84e2c-330"><strong>DecodeStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="84e2c-331">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="84e2c-331">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="84e2c-332">Процент вызовов, декодированный как стерео.</span><span class="sxs-lookup"><span data-stu-id="84e2c-332">Percentage of the call decoded as stereo.</span></span></p>
<p><span data-ttu-id="84e2c-333">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="84e2c-333">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84e2c-334"><strong>аекрендерстереоперцент</strong></span><span class="sxs-lookup"><span data-stu-id="84e2c-334"><strong>AecRenderStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="84e2c-335">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="84e2c-335">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="84e2c-336">Процентное соотношение вызова, отображаемое в качестве стерео, средством подавления акустического эха.</span><span class="sxs-lookup"><span data-stu-id="84e2c-336">Percentage of the call rendered as stereo by the acoustic echo canceller.</span></span></p>
<p><span data-ttu-id="84e2c-337">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="84e2c-337">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84e2c-338"><strong>аудиопостфекплр</strong></span><span class="sxs-lookup"><span data-stu-id="84e2c-338"><strong>AudioPostFECPLR</strong></span></span></p></td>
<td><p><span data-ttu-id="84e2c-339">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="84e2c-339">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="84e2c-340">Скорость потери пакетов после применения коррекции ошибок переадресации.</span><span class="sxs-lookup"><span data-stu-id="84e2c-340">Packet loss rate after forward error correction has been applied.</span></span></p>
<p><span data-ttu-id="84e2c-341">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="84e2c-341">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84e2c-342"><strong>енкодестереоперцент</strong></span><span class="sxs-lookup"><span data-stu-id="84e2c-342"><strong>EncodeStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="84e2c-343">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="84e2c-343">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="84e2c-344">Процент вызовов, закодированный как стерео.</span><span class="sxs-lookup"><span data-stu-id="84e2c-344">Percentage of the call encoded as stereo.</span></span></p>
<p><span data-ttu-id="84e2c-345">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="84e2c-345">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84e2c-346"><strong>аеккаптурестереоперцент</strong></span><span class="sxs-lookup"><span data-stu-id="84e2c-346"><strong>AecCaptureStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="84e2c-347">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="84e2c-347">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="84e2c-348">Процентное соотношение вызовов, записанное в качестве стереосистемы, с помощью функции отмены акустического эха.</span><span class="sxs-lookup"><span data-stu-id="84e2c-348">Percentage of the call captured as stereo by the acoustic echo canceller.</span></span></p>
<p><span data-ttu-id="84e2c-349">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="84e2c-349">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

