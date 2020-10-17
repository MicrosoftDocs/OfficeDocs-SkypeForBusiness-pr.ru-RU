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
ms.openlocfilehash: 331b2afbfa4b6c4147ffab3765af4e9e5031c190
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502876"
---
# <a name="audiostream-table-in-lync-server-2013"></a><span data-ttu-id="47bdc-102">Таблица Таблица audiostream в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="47bdc-102">AudioStream table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="47bdc-103">_**Последнее изменение темы:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="47bdc-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="47bdc-104">Каждая запись представляет один аудиопоток.</span><span class="sxs-lookup"><span data-stu-id="47bdc-104">Each record represents one audio stream.</span></span> <span data-ttu-id="47bdc-105">Одна линия аудио мультимедиа обычно содержит два звуковых потока.</span><span class="sxs-lookup"><span data-stu-id="47bdc-105">One audio media line usually contains two audio streams.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="47bdc-106"><strong>Column</strong></span><span class="sxs-lookup"><span data-stu-id="47bdc-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="47bdc-107"><strong>Тип данных</strong></span><span class="sxs-lookup"><span data-stu-id="47bdc-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="47bdc-108"><strong>Ключ или индекс</strong></span><span class="sxs-lookup"><span data-stu-id="47bdc-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="47bdc-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="47bdc-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="47bdc-110"><strong>конференцедатетиме</strong></span><span class="sxs-lookup"><span data-stu-id="47bdc-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="47bdc-111">datetime</span><span class="sxs-lookup"><span data-stu-id="47bdc-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="47bdc-112">Primary</span><span class="sxs-lookup"><span data-stu-id="47bdc-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="47bdc-113">Ссылка из <a href="lync-server-2013-medialine-table.md">таблицы MediaLine в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="47bdc-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47bdc-114"><strong>сессионсек</strong></span><span class="sxs-lookup"><span data-stu-id="47bdc-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="47bdc-115">int</span><span class="sxs-lookup"><span data-stu-id="47bdc-115">int</span></span></p></td>
<td><p><span data-ttu-id="47bdc-116">Primary</span><span class="sxs-lookup"><span data-stu-id="47bdc-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="47bdc-117">Ссылка из <a href="lync-server-2013-medialine-table.md">таблицы MediaLine в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="47bdc-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47bdc-118"><strong>медиалинелабел</strong></span><span class="sxs-lookup"><span data-stu-id="47bdc-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="47bdc-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="47bdc-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="47bdc-120">Primary</span><span class="sxs-lookup"><span data-stu-id="47bdc-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="47bdc-121">Ссылка из <a href="lync-server-2013-medialine-table.md">таблицы MediaLine в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="47bdc-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47bdc-122"><strong>стреамид</strong></span><span class="sxs-lookup"><span data-stu-id="47bdc-122"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="47bdc-123">int</span><span class="sxs-lookup"><span data-stu-id="47bdc-123">int</span></span></p></td>
<td><p><span data-ttu-id="47bdc-124">Primary</span><span class="sxs-lookup"><span data-stu-id="47bdc-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="47bdc-125">Уникальный идентификатор в линии мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="47bdc-125">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47bdc-126"><strong>життеринтерарривал</strong></span><span class="sxs-lookup"><span data-stu-id="47bdc-126"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="47bdc-127">int</span><span class="sxs-lookup"><span data-stu-id="47bdc-127">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="47bdc-128">Средний уровень дрожания в сети на основе статистики протокола RTCP.</span><span class="sxs-lookup"><span data-stu-id="47bdc-128">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47bdc-129"><strong>життеринтерарривалмакс</strong></span><span class="sxs-lookup"><span data-stu-id="47bdc-129"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="47bdc-130">int</span><span class="sxs-lookup"><span data-stu-id="47bdc-130">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="47bdc-131">Максимальный уровень дрожания в сети в течение вызова.</span><span class="sxs-lookup"><span data-stu-id="47bdc-131">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47bdc-132"><strong>паккетлоссрате</strong></span><span class="sxs-lookup"><span data-stu-id="47bdc-132"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="47bdc-133">десятичное число (5, 4)</span><span class="sxs-lookup"><span data-stu-id="47bdc-133">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="47bdc-134">Средний коэффициент потерь пакетов в течение вызова.</span><span class="sxs-lookup"><span data-stu-id="47bdc-134">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47bdc-135"><strong>паккетлоссратемакс</strong></span><span class="sxs-lookup"><span data-stu-id="47bdc-135"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="47bdc-136">десятичное число (5, 4)</span><span class="sxs-lookup"><span data-stu-id="47bdc-136">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="47bdc-137">Максимальная потеря пакетов, наблюдавшаяся в течение вызова.</span><span class="sxs-lookup"><span data-stu-id="47bdc-137">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47bdc-138"><strong>бурстденсити</strong></span><span class="sxs-lookup"><span data-stu-id="47bdc-138"><strong>BurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="47bdc-139">десятичное число (9, 4)</span><span class="sxs-lookup"><span data-stu-id="47bdc-139">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="47bdc-140">Средняя плотность потери пакетов во время пакетов потерь во время вызова.</span><span class="sxs-lookup"><span data-stu-id="47bdc-140">Average density of packet Loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47bdc-141"><strong>бурстдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="47bdc-141"><strong>BurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="47bdc-142">int</span><span class="sxs-lookup"><span data-stu-id="47bdc-142">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="47bdc-143">Средняя продолжительность потерь пакетов во время пиков потерь в течение вызова.</span><span class="sxs-lookup"><span data-stu-id="47bdc-143">Average duration of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47bdc-144"><strong>бурстгапденсити</strong></span><span class="sxs-lookup"><span data-stu-id="47bdc-144"><strong>BurstGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="47bdc-145">десятичное число (9, 4)</span><span class="sxs-lookup"><span data-stu-id="47bdc-145">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="47bdc-146">Средняя плотность потерь пакетов в промежутках между пиками потерь.</span><span class="sxs-lookup"><span data-stu-id="47bdc-146">Average density of packet loss during gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47bdc-147"><strong>бурстгапдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="47bdc-147"><strong>BurstGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="47bdc-148">int</span><span class="sxs-lookup"><span data-stu-id="47bdc-148">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="47bdc-149">Средняя продолжительность промежутков между пиками потерь пакетов.</span><span class="sxs-lookup"><span data-stu-id="47bdc-149">Average duration of gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47bdc-150"><strong>паккетутилизатион</strong></span><span class="sxs-lookup"><span data-stu-id="47bdc-150"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="47bdc-151">Целое</span><span class="sxs-lookup"><span data-stu-id="47bdc-151">Int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="47bdc-152">Количество пакетов для аудиопотока.</span><span class="sxs-lookup"><span data-stu-id="47bdc-152">Packet count for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47bdc-153"><strong>Самый полоса пропускания</strong></span><span class="sxs-lookup"><span data-stu-id="47bdc-153"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="47bdc-154">Целое</span><span class="sxs-lookup"><span data-stu-id="47bdc-154">Int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="47bdc-155">Оценка пропускной способности для аудиопотока.</span><span class="sxs-lookup"><span data-stu-id="47bdc-155">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47bdc-156"><strong>деградатионавг</strong></span><span class="sxs-lookup"><span data-stu-id="47bdc-156"><strong>DegradationAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="47bdc-157">десятичное число (3, 2)</span><span class="sxs-lookup"><span data-stu-id="47bdc-157">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="47bdc-p102">Снижение экспертной оценки качества (MOS) в сети для всего звонка в диапазоне от 0,0 до 5,0. Эта метрика показывает величину уменьшения MOS в сети, обусловленную дрожанием и потерей пакетов. Для приемлемого качества это значение должно быть меньше, чем 0,5.</span><span class="sxs-lookup"><span data-stu-id="47bdc-p102">Network MOS Degradation for the whole call. Range is 0.0 to 5.0. This metric shows the amount the Network MOS was reduced because of jitter and packet loss. For acceptable quality it should less than 0.5.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47bdc-162"><strong>деградатионмакс</strong></span><span class="sxs-lookup"><span data-stu-id="47bdc-162"><strong>DegradationMax</strong></span></span></p></td>
<td><p><span data-ttu-id="47bdc-163">десятичное число (3, 2)</span><span class="sxs-lookup"><span data-stu-id="47bdc-163">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="47bdc-164">Максимальное снижение экспертной оценки качества (MOS) в сети во время звонка.</span><span class="sxs-lookup"><span data-stu-id="47bdc-164">Maximum Network MOS degradation during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47bdc-165"><strong>деградатионжиттеравг</strong></span><span class="sxs-lookup"><span data-stu-id="47bdc-165"><strong>DegradationJitterAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="47bdc-166">десятичное число (3, 2)</span><span class="sxs-lookup"><span data-stu-id="47bdc-166">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="47bdc-167">Снижение экспертной оценки качества (MOS) в сети, вызванное дрожанием.</span><span class="sxs-lookup"><span data-stu-id="47bdc-167">Network MOS degradation caused by jitter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47bdc-168"><strong>деградатионпаккетлоссавг</strong></span><span class="sxs-lookup"><span data-stu-id="47bdc-168"><strong>DegradationPacketLossAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="47bdc-169">десятичное число (3, 2)</span><span class="sxs-lookup"><span data-stu-id="47bdc-169">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="47bdc-170">Снижение экспертной оценки качества (MOS) в сети, вызванное потерей пакетов.</span><span class="sxs-lookup"><span data-stu-id="47bdc-170">Network MOS degradation caused by packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47bdc-171"><strong>аудиопайлоаддескриптион</strong></span><span class="sxs-lookup"><span data-stu-id="47bdc-171"><strong>AudioPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="47bdc-172">int</span><span class="sxs-lookup"><span data-stu-id="47bdc-172">int</span></span></p></td>
<td><p><span data-ttu-id="47bdc-173">Правительства</span><span class="sxs-lookup"><span data-stu-id="47bdc-173">Foreign</span></span></p></td>
<td><p><span data-ttu-id="47bdc-174">Аудиокодек, используемый для вызова, на который ссылается таблица таблица payloaddescription.</span><span class="sxs-lookup"><span data-stu-id="47bdc-174">The audio Codec used for the call, referenced from PayloadDescription Table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47bdc-175"><strong>аудиосамплерате</strong></span><span class="sxs-lookup"><span data-stu-id="47bdc-175"><strong>AudioSampleRate</strong></span></span></p></td>
<td><p><span data-ttu-id="47bdc-176">int</span><span class="sxs-lookup"><span data-stu-id="47bdc-176">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="47bdc-177">Частота выборки для аудиопотока.</span><span class="sxs-lookup"><span data-stu-id="47bdc-177">Sampling rate for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47bdc-178"><strong>Обработки</strong></span><span class="sxs-lookup"><span data-stu-id="47bdc-178"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="47bdc-179">int</span><span class="sxs-lookup"><span data-stu-id="47bdc-179">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="47bdc-180">Время приема-передачи на основе статистики RTCP.</span><span class="sxs-lookup"><span data-stu-id="47bdc-180">Round trip time from RTCP statistics.</span></span> <span data-ttu-id="47bdc-181">Для приемлемого качества это должно быть меньше 100 мс.</span><span class="sxs-lookup"><span data-stu-id="47bdc-181">For acceptable quality this should be less than 100ms.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47bdc-182"><strong>раундтрипмакс</strong></span><span class="sxs-lookup"><span data-stu-id="47bdc-182"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="47bdc-183">int</span><span class="sxs-lookup"><span data-stu-id="47bdc-183">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="47bdc-184">Максимальное время приема-передачи для аудиопотока.</span><span class="sxs-lookup"><span data-stu-id="47bdc-184">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47bdc-185"><strong>овераллавгнетворкмос</strong></span><span class="sxs-lookup"><span data-stu-id="47bdc-185"><strong>OverallAvgNetworkMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="47bdc-186">десятичное число (3, 2)</span><span class="sxs-lookup"><span data-stu-id="47bdc-186">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="47bdc-187">Средняя экспертная оценка качества (MOS) в широкополосной сети для вызова.</span><span class="sxs-lookup"><span data-stu-id="47bdc-187">Average wideband Network MOS for the call.</span></span> <span data-ttu-id="47bdc-188">Значение этого показателя зависит от потерь пакетов, дрожания и используемого кодека.</span><span class="sxs-lookup"><span data-stu-id="47bdc-188">This metric depends on the packet loss, jitter, and codec used.</span></span> <span data-ttu-id="47bdc-189">Диапазон — [1,0 – 5,0].</span><span class="sxs-lookup"><span data-stu-id="47bdc-189">Range is [1.0 to 5.0].</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47bdc-190"><strong>овераллминнетворкмос</strong></span><span class="sxs-lookup"><span data-stu-id="47bdc-190"><strong>OverallMinNetworkMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="47bdc-191">десятичное число (3, 2)</span><span class="sxs-lookup"><span data-stu-id="47bdc-191">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="47bdc-192">Минимум экспертная Network MOS для вызова.</span><span class="sxs-lookup"><span data-stu-id="47bdc-192">The minimum wideband Network MOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47bdc-193"><strong>Значение sendlistenmos</strong></span><span class="sxs-lookup"><span data-stu-id="47bdc-193"><strong>SendListenMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="47bdc-194">десятичное число (3, 2)</span><span class="sxs-lookup"><span data-stu-id="47bdc-194">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="47bdc-195">Средний прогнозируемый экспертная прослушивающий рейтинг MOS для звукового сигнала, в том числе уровень речи, уровень шума и характеристики устройства захвата.</span><span class="sxs-lookup"><span data-stu-id="47bdc-195">The average predicted wideband Listening MOS score for audio sent, including speech level, noise level and capture device characteristics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47bdc-196"><strong>сендлистенмосмин</strong></span><span class="sxs-lookup"><span data-stu-id="47bdc-196"><strong>SendListenMOSMin</strong></span></span></p></td>
<td><p><span data-ttu-id="47bdc-197">десятичное число (3, 2)</span><span class="sxs-lookup"><span data-stu-id="47bdc-197">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="47bdc-198">Минимальное значение sendlistenmos для вызова.</span><span class="sxs-lookup"><span data-stu-id="47bdc-198">The minimum SendListenMOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47bdc-199"><strong>Значение recvlistenmos</strong></span><span class="sxs-lookup"><span data-stu-id="47bdc-199"><strong>RecvListenMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="47bdc-200">десятичное число (3, 2)</span><span class="sxs-lookup"><span data-stu-id="47bdc-200">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="47bdc-201">Средний прогнозируемый экспертная прослушивания MOS для звука, получаемого из сети, включая уровень речи, уровень шума, кодек, условия сети и характеристики устройства захвата.</span><span class="sxs-lookup"><span data-stu-id="47bdc-201">The average predicted wideband Listening MOS score for audio received from the network including speech level, noise level, codec, network conditions and capture device characteristics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47bdc-202"><strong>реквлистенмосмин</strong></span><span class="sxs-lookup"><span data-stu-id="47bdc-202"><strong>RecvListenMOSMin</strong></span></span></p></td>
<td><p><span data-ttu-id="47bdc-203">десятичное число (3, 2)</span><span class="sxs-lookup"><span data-stu-id="47bdc-203">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="47bdc-204">Минимальное значение recvlistenmos для вызова.</span><span class="sxs-lookup"><span data-stu-id="47bdc-204">The minimum RecvListenMOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47bdc-205"><strong>аудиофекусед</strong></span><span class="sxs-lookup"><span data-stu-id="47bdc-205"><strong>AudioFECUsed</strong></span></span></p></td>
<td><p><span data-ttu-id="47bdc-206">Битовая</span><span class="sxs-lookup"><span data-stu-id="47bdc-206">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="47bdc-207">Флаг, указывающий, использовался ли для вызова звуковая FEC.</span><span class="sxs-lookup"><span data-stu-id="47bdc-207">Flag indicating if audio FEC was used for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47bdc-208"><strong>RatioConcealedSamplesAvg</strong></span><span class="sxs-lookup"><span data-stu-id="47bdc-208"><strong>RatioConcealedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="47bdc-209">десятичное число (5, 2)</span><span class="sxs-lookup"><span data-stu-id="47bdc-209">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="47bdc-210">Среднее отношение числа скрытых образцов, созданных функцией восстановления звука, к обычным образцам.</span><span class="sxs-lookup"><span data-stu-id="47bdc-210">Average ratio of concealed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47bdc-211"><strong>ратиостретчедсамплесавг</strong></span><span class="sxs-lookup"><span data-stu-id="47bdc-211"><strong>RatioStretchedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="47bdc-212">десятичное число (5, 2)</span><span class="sxs-lookup"><span data-stu-id="47bdc-212">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="47bdc-213">Среднее отношение числа растянутых образцов, созданных функцией восстановления звука, к обычным образцам.</span><span class="sxs-lookup"><span data-stu-id="47bdc-213">Average ratio of stretched samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47bdc-214"><strong>ратиокомпресседсамплесавг</strong></span><span class="sxs-lookup"><span data-stu-id="47bdc-214"><strong>RatioCompressedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="47bdc-215">десятичное число (5, 2)</span><span class="sxs-lookup"><span data-stu-id="47bdc-215">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="47bdc-216">Среднее отношение числа сжатых образцов, созданных функцией восстановления звука, к обычным образцам.</span><span class="sxs-lookup"><span data-stu-id="47bdc-216">Average ratio of compressed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47bdc-217"><strong>Получение</strong></span><span class="sxs-lookup"><span data-stu-id="47bdc-217"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="47bdc-218">Битовая</span><span class="sxs-lookup"><span data-stu-id="47bdc-218">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="47bdc-219">Получение потоковых данных на стороне получателя.</span><span class="sxs-lookup"><span data-stu-id="47bdc-219">Stream data on receiver side is received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47bdc-220"><strong>Прав</strong></span><span class="sxs-lookup"><span data-stu-id="47bdc-220"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="47bdc-221">Битовая</span><span class="sxs-lookup"><span data-stu-id="47bdc-221">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="47bdc-222">Получение потоковых данных на стороне отправителя.</span><span class="sxs-lookup"><span data-stu-id="47bdc-222">Stream data on sender side is received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47bdc-223"><strong>сендерискаллерпаи</strong></span><span class="sxs-lookup"><span data-stu-id="47bdc-223"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="47bdc-224">Битовая</span><span class="sxs-lookup"><span data-stu-id="47bdc-224">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="47bdc-225">1 означает направление потока от вызывающего абонента к вызываемому абоненту.</span><span class="sxs-lookup"><span data-stu-id="47bdc-225">1 means the stream direction is from the caller to the callee.</span></span></p>
<p><span data-ttu-id="47bdc-226">0 означает направление потока от вызываемого абонента вызывающему абоненту.</span><span class="sxs-lookup"><span data-stu-id="47bdc-226">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47bdc-227"><strong>життеринтерарривалсд</strong></span><span class="sxs-lookup"><span data-stu-id="47bdc-227"><strong>JitterInterArrivalSD</strong></span></span></p></td>
<td><p><span data-ttu-id="47bdc-228">float</span><span class="sxs-lookup"><span data-stu-id="47bdc-228">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="47bdc-229">Стандартное отклонение для времени прибытия при колебании.</span><span class="sxs-lookup"><span data-stu-id="47bdc-229">Standard deviation for jitter arrival times.</span></span></p>
<p><span data-ttu-id="47bdc-230">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="47bdc-230">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47bdc-231"><strong>концеалратиомакс</strong></span><span class="sxs-lookup"><span data-stu-id="47bdc-231"><strong>ConcealRatioMax</strong></span></span></p></td>
<td><p><span data-ttu-id="47bdc-232">float</span><span class="sxs-lookup"><span data-stu-id="47bdc-232">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="47bdc-233">Максимальное соотношение пакетов, скрытые средством для воспроизведения.</span><span class="sxs-lookup"><span data-stu-id="47bdc-233">Maximum ratio of packets concealed by the healer.</span></span></p>
<p><span data-ttu-id="47bdc-234">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="47bdc-234">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47bdc-235"><strong>концеалратиосд</strong></span><span class="sxs-lookup"><span data-stu-id="47bdc-235"><strong>ConcealRatioSD</strong></span></span></p></td>
<td><p><span data-ttu-id="47bdc-236">float</span><span class="sxs-lookup"><span data-stu-id="47bdc-236">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="47bdc-237">Стандартное отклонение для соотношения пакетов, которые скрываются средством "выбор".</span><span class="sxs-lookup"><span data-stu-id="47bdc-237">Standard deviation for the ratio of packets concealed by the healer.</span></span></p>
<p><span data-ttu-id="47bdc-238">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="47bdc-238">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47bdc-239"><strong>хеалерпаккетдропратио</strong></span><span class="sxs-lookup"><span data-stu-id="47bdc-239"><strong>HealerPacketDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="47bdc-240">float</span><span class="sxs-lookup"><span data-stu-id="47bdc-240">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="47bdc-241">Доля пакетов, отброшенных средством сброса по сравнению с общим количеством полученных пакетов.</span><span class="sxs-lookup"><span data-stu-id="47bdc-241">Ratio of packets dropped by the healer compared to the total number of packets received.</span></span></p>
<p><span data-ttu-id="47bdc-242">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="47bdc-242">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47bdc-243"><strong>хеалерфекпаккетуседратио</strong></span><span class="sxs-lookup"><span data-stu-id="47bdc-243"><strong>HealerFECPacketUsedRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="47bdc-244">float</span><span class="sxs-lookup"><span data-stu-id="47bdc-244">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="47bdc-245">Доля использованных пакетов коррекции ошибок переадресации по сравнению с общим количеством полученных пакетов.</span><span class="sxs-lookup"><span data-stu-id="47bdc-245">Ratio of used forward error correction packets compared to the total number of packets received.</span></span></p>
<p><span data-ttu-id="47bdc-246">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="47bdc-246">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47bdc-247"><strong>макскомпресседсамплес</strong></span><span class="sxs-lookup"><span data-stu-id="47bdc-247"><strong>MaxCompressedSamples</strong></span></span></p></td>
<td><p><span data-ttu-id="47bdc-248">float</span><span class="sxs-lookup"><span data-stu-id="47bdc-248">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="47bdc-249">Максимальное число пакетов звукозаписи, сжатых средством завершения.</span><span class="sxs-lookup"><span data-stu-id="47bdc-249">Maximum number of audio packets that were compressed by the healer.</span></span></p>
<p><span data-ttu-id="47bdc-250">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="47bdc-250">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47bdc-251"><strong>лоссконжестионперцент</strong></span><span class="sxs-lookup"><span data-stu-id="47bdc-251"><strong>LossCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="47bdc-252">float</span><span class="sxs-lookup"><span data-stu-id="47bdc-252">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="47bdc-253">Указывает процент времени, в течение которого вызов находился в состоянии перегрузки потерь.</span><span class="sxs-lookup"><span data-stu-id="47bdc-253">Indicates the percentage of the time when the call was in a loss congestion state.</span></span></p>
<p><span data-ttu-id="47bdc-254">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="47bdc-254">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47bdc-255"><strong>делайконжестионперцент</strong></span><span class="sxs-lookup"><span data-stu-id="47bdc-255"><strong>DelayCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="47bdc-256">float</span><span class="sxs-lookup"><span data-stu-id="47bdc-256">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="47bdc-257">Указывает процент вызова, в течение которого перегрузка была вызвана задержкой появления сетевых пакетов.</span><span class="sxs-lookup"><span data-stu-id="47bdc-257">Indicates the percentage of the call during which congestion was caused by the delayed arrival of network packets.</span></span></p>
<p><span data-ttu-id="47bdc-258">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="47bdc-258">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47bdc-259"><strong>контентиондетектедперцент</strong></span><span class="sxs-lookup"><span data-stu-id="47bdc-259"><strong>ContentionDetectedPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="47bdc-260">float</span><span class="sxs-lookup"><span data-stu-id="47bdc-260">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="47bdc-261">Указывает процент времени, в течение которого вызов конкурирует за ресурсы сети.</span><span class="sxs-lookup"><span data-stu-id="47bdc-261">Indicates the percentage of the time when the call was competing for network resources.</span></span></p>
<p><span data-ttu-id="47bdc-262">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="47bdc-262">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47bdc-263"><strong>бандвидсестмин</strong></span><span class="sxs-lookup"><span data-stu-id="47bdc-263"><strong>BandwidthEstMin</strong></span></span></p></td>
<td><p><span data-ttu-id="47bdc-264">int</span><span class="sxs-lookup"><span data-stu-id="47bdc-264">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="47bdc-265">Минимальная сумма оценки пропускной способности, измеренной во время вызова.</span><span class="sxs-lookup"><span data-stu-id="47bdc-265">Minimum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="47bdc-266">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="47bdc-266">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47bdc-267"><strong>бандвидсестмакс</strong></span><span class="sxs-lookup"><span data-stu-id="47bdc-267"><strong>BandwidthEstMax</strong></span></span></p></td>
<td><p><span data-ttu-id="47bdc-268">int</span><span class="sxs-lookup"><span data-stu-id="47bdc-268">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="47bdc-269">Максимальный объем оценки пропускной способности, измеренной во время вызова.</span><span class="sxs-lookup"><span data-stu-id="47bdc-269">Maximum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="47bdc-270">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="47bdc-270">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47bdc-271"><strong>бандвидсестстддев</strong></span><span class="sxs-lookup"><span data-stu-id="47bdc-271"><strong>BandwidthEstStdDev</strong></span></span></p></td>
<td><p><span data-ttu-id="47bdc-272">int</span><span class="sxs-lookup"><span data-stu-id="47bdc-272">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="47bdc-273">Стандартное отклонение оценки пропускной способности, измеренной во время вызова.</span><span class="sxs-lookup"><span data-stu-id="47bdc-273">Standard deviation of the bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="47bdc-274">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="47bdc-274">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47bdc-275"><strong>бандвидсеставже</strong></span><span class="sxs-lookup"><span data-stu-id="47bdc-275"><strong>BandwidthEstAvge</strong></span></span></p></td>
<td><p><span data-ttu-id="47bdc-276">int</span><span class="sxs-lookup"><span data-stu-id="47bdc-276">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="47bdc-277">Средняя величина оценки пропускной способности, измеренной во время вызова.</span><span class="sxs-lookup"><span data-stu-id="47bdc-277">Average amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="47bdc-278">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="47bdc-278">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47bdc-279"><strong>релативеоневайтотал</strong></span><span class="sxs-lookup"><span data-stu-id="47bdc-279"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="47bdc-280">float</span><span class="sxs-lookup"><span data-stu-id="47bdc-280">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="47bdc-p105">Общая величина односторонней задержки. Относительная односторонняя задержка измеряет задержку между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="47bdc-p105">Total amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="47bdc-283">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="47bdc-283">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47bdc-284"><strong>релативеоневайавераже</strong></span><span class="sxs-lookup"><span data-stu-id="47bdc-284"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="47bdc-285">float</span><span class="sxs-lookup"><span data-stu-id="47bdc-285">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="47bdc-p106">Средняя величина односторонней задержки. Относительная односторонняя задержка измеряет задержку между клиентом и сервером</span><span class="sxs-lookup"><span data-stu-id="47bdc-p106">Average amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="47bdc-288">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="47bdc-288">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47bdc-289"><strong>релативеоневаймакс</strong></span><span class="sxs-lookup"><span data-stu-id="47bdc-289"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="47bdc-290">float</span><span class="sxs-lookup"><span data-stu-id="47bdc-290">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="47bdc-p107">Максимальная величина односторонней задержки. Относительная односторонняя задержка измеряет задержку между клиентом и сервером</span><span class="sxs-lookup"><span data-stu-id="47bdc-p107">Maximum amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="47bdc-293">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="47bdc-293">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47bdc-294"><strong>релативеоневайбурстоккурренцес</strong></span><span class="sxs-lookup"><span data-stu-id="47bdc-294"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="47bdc-295">int</span><span class="sxs-lookup"><span data-stu-id="47bdc-295">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="47bdc-p108">Общее число повторов пакетов в одну сторону. "Пакетная" передача представляет собой передачу, при которой данные передаются посредством случайных пакетов, а не в виде устойчивого потока. С помощью этой метрики измеряется поток данных между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="47bdc-p108">Total one-way burst occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="47bdc-299">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="47bdc-299">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47bdc-300"><strong>релативеоневайбурстденсити</strong></span><span class="sxs-lookup"><span data-stu-id="47bdc-300"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="47bdc-301">float</span><span class="sxs-lookup"><span data-stu-id="47bdc-301">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="47bdc-p109">Общая плотность пакетов в одну сторону. "Пакетная" передача представляет собой передачу, при которой данные передаются посредством случайных пакетов, а не в виде устойчивого потока. С помощью этой метрики измеряется поток данных между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="47bdc-p109">Total one-way burst density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="47bdc-305">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="47bdc-305">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47bdc-306"><strong>релативеоневайбурстдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="47bdc-306"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="47bdc-307">float</span><span class="sxs-lookup"><span data-stu-id="47bdc-307">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="47bdc-p110">Общая длительность пакетов в одну сторону. "Пакетная" передача представляет собой передачу, при которой данные передаются посредством случайных пакетов, а не в виде устойчивого потока. С помощью этой метрики измеряется поток данных между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="47bdc-p110">Total one-way burst duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="47bdc-311">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="47bdc-311">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47bdc-312"><strong>релативеоневайгапоккурренцес</strong></span><span class="sxs-lookup"><span data-stu-id="47bdc-312"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="47bdc-313">int</span><span class="sxs-lookup"><span data-stu-id="47bdc-313">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="47bdc-p111">Общее число повторов разрывов в одну сторону. "Пакетная" передача представляет собой передачу, при которой данные передаются посредством случайных пакетов, а не в виде устойчивого потока; разрывы указывают задержку между этими пакетами. С помощью данной метрики измеряется поток данных между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="47bdc-p111">Total one-way gap occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="47bdc-317">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="47bdc-317">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47bdc-318"><strong>релативеоневайгапденсити</strong></span><span class="sxs-lookup"><span data-stu-id="47bdc-318"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="47bdc-319">float</span><span class="sxs-lookup"><span data-stu-id="47bdc-319">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="47bdc-p112">Общая плотность разрывов в одну сторону. "Пакетная" передача представляет собой передачу, при которой данные передаются посредством случайных пакетов, а не в виде устойчивого потока; разрывы указывают задержку между этими пакетами. С помощью данной метрики измеряется поток данных между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="47bdc-p112">Total one-way gap density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="47bdc-323">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="47bdc-323">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47bdc-324"><strong>релативеоневайгапдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="47bdc-324"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="47bdc-325">float</span><span class="sxs-lookup"><span data-stu-id="47bdc-325">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="47bdc-p113">Общая длительность разрывов в одну сторону. "Пакетная" передача представляет собой передачу, при которой данные передаются посредством случайных пакетов, а не в виде устойчивого потока; разрывы указывают задержку между этими пакетами. С помощью данной метрики измеряется поток данных между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="47bdc-p113">Total one-way gap duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="47bdc-329">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="47bdc-329">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47bdc-330"><strong>декодестереоперцент</strong></span><span class="sxs-lookup"><span data-stu-id="47bdc-330"><strong>DecodeStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="47bdc-331">float</span><span class="sxs-lookup"><span data-stu-id="47bdc-331">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="47bdc-332">Процент вызовов, декодированный как стерео.</span><span class="sxs-lookup"><span data-stu-id="47bdc-332">Percentage of the call decoded as stereo.</span></span></p>
<p><span data-ttu-id="47bdc-333">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="47bdc-333">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47bdc-334"><strong>аекрендерстереоперцент</strong></span><span class="sxs-lookup"><span data-stu-id="47bdc-334"><strong>AecRenderStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="47bdc-335">float</span><span class="sxs-lookup"><span data-stu-id="47bdc-335">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="47bdc-336">Процентное соотношение вызова, отображаемое в качестве стерео, средством подавления акустического эха.</span><span class="sxs-lookup"><span data-stu-id="47bdc-336">Percentage of the call rendered as stereo by the acoustic echo canceller.</span></span></p>
<p><span data-ttu-id="47bdc-337">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="47bdc-337">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47bdc-338"><strong>аудиопостфекплр</strong></span><span class="sxs-lookup"><span data-stu-id="47bdc-338"><strong>AudioPostFECPLR</strong></span></span></p></td>
<td><p><span data-ttu-id="47bdc-339">float</span><span class="sxs-lookup"><span data-stu-id="47bdc-339">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="47bdc-340">Скорость потери пакетов после применения коррекции ошибок переадресации.</span><span class="sxs-lookup"><span data-stu-id="47bdc-340">Packet loss rate after forward error correction has been applied.</span></span></p>
<p><span data-ttu-id="47bdc-341">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="47bdc-341">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47bdc-342"><strong>енкодестереоперцент</strong></span><span class="sxs-lookup"><span data-stu-id="47bdc-342"><strong>EncodeStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="47bdc-343">float</span><span class="sxs-lookup"><span data-stu-id="47bdc-343">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="47bdc-344">Процент вызовов, закодированный как стерео.</span><span class="sxs-lookup"><span data-stu-id="47bdc-344">Percentage of the call encoded as stereo.</span></span></p>
<p><span data-ttu-id="47bdc-345">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="47bdc-345">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47bdc-346"><strong>аеккаптурестереоперцент</strong></span><span class="sxs-lookup"><span data-stu-id="47bdc-346"><strong>AecCaptureStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="47bdc-347">float</span><span class="sxs-lookup"><span data-stu-id="47bdc-347">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="47bdc-348">Процентное соотношение вызовов, записанное в качестве стереосистемы, с помощью функции отмены акустического эха.</span><span class="sxs-lookup"><span data-stu-id="47bdc-348">Percentage of the call captured as stereo by the acoustic echo canceller.</span></span></p>
<p><span data-ttu-id="47bdc-349">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="47bdc-349">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

