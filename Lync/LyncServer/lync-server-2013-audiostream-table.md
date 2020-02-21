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
ms.openlocfilehash: e2da0884915f44246e316f80cb9fd35fb7aecaad
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195772"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="audiostream-table-in-lync-server-2013"></a><span data-ttu-id="8ad94-102">Таблица Таблица audiostream в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8ad94-102">AudioStream table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8ad94-103">_**Последнее изменение темы:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="8ad94-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="8ad94-104">Каждая запись представляет один аудиопоток.</span><span class="sxs-lookup"><span data-stu-id="8ad94-104">Each record represents one audio stream.</span></span> <span data-ttu-id="8ad94-105">Одна линия аудио мультимедиа обычно содержит два звуковых потока.</span><span class="sxs-lookup"><span data-stu-id="8ad94-105">One audio media line usually contains two audio streams.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8ad94-106"><strong>Column</strong></span><span class="sxs-lookup"><span data-stu-id="8ad94-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="8ad94-107"><strong>Тип данных</strong></span><span class="sxs-lookup"><span data-stu-id="8ad94-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="8ad94-108"><strong>Ключ или индекс</strong></span><span class="sxs-lookup"><span data-stu-id="8ad94-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="8ad94-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="8ad94-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8ad94-110"><strong>конференцедатетиме</strong></span><span class="sxs-lookup"><span data-stu-id="8ad94-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="8ad94-111">datetime</span><span class="sxs-lookup"><span data-stu-id="8ad94-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="8ad94-112">Primary</span><span class="sxs-lookup"><span data-stu-id="8ad94-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="8ad94-113">Ссылка из <a href="lync-server-2013-medialine-table.md">таблицы MediaLine в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="8ad94-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ad94-114"><strong>сессионсек</strong></span><span class="sxs-lookup"><span data-stu-id="8ad94-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="8ad94-115">int</span><span class="sxs-lookup"><span data-stu-id="8ad94-115">int</span></span></p></td>
<td><p><span data-ttu-id="8ad94-116">Primary</span><span class="sxs-lookup"><span data-stu-id="8ad94-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="8ad94-117">Ссылка из <a href="lync-server-2013-medialine-table.md">таблицы MediaLine в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="8ad94-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ad94-118"><strong>медиалинелабел</strong></span><span class="sxs-lookup"><span data-stu-id="8ad94-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="8ad94-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="8ad94-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="8ad94-120">Primary</span><span class="sxs-lookup"><span data-stu-id="8ad94-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="8ad94-121">Ссылка из <a href="lync-server-2013-medialine-table.md">таблицы MediaLine в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="8ad94-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ad94-122"><strong>стреамид</strong></span><span class="sxs-lookup"><span data-stu-id="8ad94-122"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="8ad94-123">int</span><span class="sxs-lookup"><span data-stu-id="8ad94-123">int</span></span></p></td>
<td><p><span data-ttu-id="8ad94-124">Primary</span><span class="sxs-lookup"><span data-stu-id="8ad94-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="8ad94-125">Уникальный идентификатор в линии мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="8ad94-125">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ad94-126"><strong>життеринтерарривал</strong></span><span class="sxs-lookup"><span data-stu-id="8ad94-126"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="8ad94-127">int</span><span class="sxs-lookup"><span data-stu-id="8ad94-127">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8ad94-128">Средний уровень дрожания в сети на основе статистики протокола RTCP.</span><span class="sxs-lookup"><span data-stu-id="8ad94-128">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ad94-129"><strong>життеринтерарривалмакс</strong></span><span class="sxs-lookup"><span data-stu-id="8ad94-129"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="8ad94-130">int</span><span class="sxs-lookup"><span data-stu-id="8ad94-130">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8ad94-131">Максимальный уровень дрожания в сети в течение вызова.</span><span class="sxs-lookup"><span data-stu-id="8ad94-131">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ad94-132"><strong>паккетлоссрате</strong></span><span class="sxs-lookup"><span data-stu-id="8ad94-132"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="8ad94-133">десятичное число (5, 4)</span><span class="sxs-lookup"><span data-stu-id="8ad94-133">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8ad94-134">Средний коэффициент потерь пакетов в течение вызова.</span><span class="sxs-lookup"><span data-stu-id="8ad94-134">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ad94-135"><strong>паккетлоссратемакс</strong></span><span class="sxs-lookup"><span data-stu-id="8ad94-135"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="8ad94-136">десятичное число (5, 4)</span><span class="sxs-lookup"><span data-stu-id="8ad94-136">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8ad94-137">Максимальная потеря пакетов, наблюдавшаяся в течение вызова.</span><span class="sxs-lookup"><span data-stu-id="8ad94-137">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ad94-138"><strong>бурстденсити</strong></span><span class="sxs-lookup"><span data-stu-id="8ad94-138"><strong>BurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="8ad94-139">десятичное число (9, 4)</span><span class="sxs-lookup"><span data-stu-id="8ad94-139">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8ad94-140">Средняя плотность потери пакетов во время пакетов потерь во время вызова.</span><span class="sxs-lookup"><span data-stu-id="8ad94-140">Average density of packet Loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ad94-141"><strong>бурстдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="8ad94-141"><strong>BurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="8ad94-142">int</span><span class="sxs-lookup"><span data-stu-id="8ad94-142">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8ad94-143">Средняя продолжительность потерь пакетов во время пиков потерь в течение вызова.</span><span class="sxs-lookup"><span data-stu-id="8ad94-143">Average duration of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ad94-144"><strong>бурстгапденсити</strong></span><span class="sxs-lookup"><span data-stu-id="8ad94-144"><strong>BurstGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="8ad94-145">десятичное число (9, 4)</span><span class="sxs-lookup"><span data-stu-id="8ad94-145">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8ad94-146">Средняя плотность потерь пакетов в промежутках между пиками потерь.</span><span class="sxs-lookup"><span data-stu-id="8ad94-146">Average density of packet loss during gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ad94-147"><strong>бурстгапдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="8ad94-147"><strong>BurstGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="8ad94-148">int</span><span class="sxs-lookup"><span data-stu-id="8ad94-148">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8ad94-149">Средняя продолжительность промежутков между пиками потерь пакетов.</span><span class="sxs-lookup"><span data-stu-id="8ad94-149">Average duration of gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ad94-150"><strong>паккетутилизатион</strong></span><span class="sxs-lookup"><span data-stu-id="8ad94-150"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="8ad94-151">Целое</span><span class="sxs-lookup"><span data-stu-id="8ad94-151">Int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8ad94-152">Количество пакетов для аудиопотока.</span><span class="sxs-lookup"><span data-stu-id="8ad94-152">Packet count for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ad94-153"><strong>Самый полоса пропускания</strong></span><span class="sxs-lookup"><span data-stu-id="8ad94-153"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="8ad94-154">Целое</span><span class="sxs-lookup"><span data-stu-id="8ad94-154">Int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8ad94-155">Оценка пропускной способности для аудиопотока.</span><span class="sxs-lookup"><span data-stu-id="8ad94-155">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ad94-156"><strong>деградатионавг</strong></span><span class="sxs-lookup"><span data-stu-id="8ad94-156"><strong>DegradationAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="8ad94-157">десятичное число (3, 2)</span><span class="sxs-lookup"><span data-stu-id="8ad94-157">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8ad94-p102">Снижение экспертной оценки качества (MOS) в сети для всего звонка в диапазоне от 0,0 до 5,0. Эта метрика показывает величину уменьшения MOS в сети, обусловленную дрожанием и потерей пакетов. Для приемлемого качества это значение должно быть меньше, чем 0,5.</span><span class="sxs-lookup"><span data-stu-id="8ad94-p102">Network MOS Degradation for the whole call. Range is 0.0 to 5.0. This metric shows the amount the Network MOS was reduced because of jitter and packet loss. For acceptable quality it should less than 0.5.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ad94-162"><strong>деградатионмакс</strong></span><span class="sxs-lookup"><span data-stu-id="8ad94-162"><strong>DegradationMax</strong></span></span></p></td>
<td><p><span data-ttu-id="8ad94-163">десятичное число (3, 2)</span><span class="sxs-lookup"><span data-stu-id="8ad94-163">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8ad94-164">Максимальное снижение экспертной оценки качества (MOS) в сети во время звонка.</span><span class="sxs-lookup"><span data-stu-id="8ad94-164">Maximum Network MOS degradation during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ad94-165"><strong>деградатионжиттеравг</strong></span><span class="sxs-lookup"><span data-stu-id="8ad94-165"><strong>DegradationJitterAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="8ad94-166">десятичное число (3, 2)</span><span class="sxs-lookup"><span data-stu-id="8ad94-166">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8ad94-167">Снижение экспертной оценки качества (MOS) в сети, вызванное дрожанием.</span><span class="sxs-lookup"><span data-stu-id="8ad94-167">Network MOS degradation caused by jitter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ad94-168"><strong>деградатионпаккетлоссавг</strong></span><span class="sxs-lookup"><span data-stu-id="8ad94-168"><strong>DegradationPacketLossAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="8ad94-169">десятичное число (3, 2)</span><span class="sxs-lookup"><span data-stu-id="8ad94-169">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8ad94-170">Снижение экспертной оценки качества (MOS) в сети, вызванное потерей пакетов.</span><span class="sxs-lookup"><span data-stu-id="8ad94-170">Network MOS degradation caused by packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ad94-171"><strong>аудиопайлоаддескриптион</strong></span><span class="sxs-lookup"><span data-stu-id="8ad94-171"><strong>AudioPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="8ad94-172">int</span><span class="sxs-lookup"><span data-stu-id="8ad94-172">int</span></span></p></td>
<td><p><span data-ttu-id="8ad94-173">Правительства</span><span class="sxs-lookup"><span data-stu-id="8ad94-173">Foreign</span></span></p></td>
<td><p><span data-ttu-id="8ad94-174">Аудиокодек, используемый для вызова, на который ссылается таблица таблица payloaddescription.</span><span class="sxs-lookup"><span data-stu-id="8ad94-174">The audio Codec used for the call, referenced from PayloadDescription Table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ad94-175"><strong>аудиосамплерате</strong></span><span class="sxs-lookup"><span data-stu-id="8ad94-175"><strong>AudioSampleRate</strong></span></span></p></td>
<td><p><span data-ttu-id="8ad94-176">int</span><span class="sxs-lookup"><span data-stu-id="8ad94-176">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8ad94-177">Частота выборки для аудиопотока.</span><span class="sxs-lookup"><span data-stu-id="8ad94-177">Sampling rate for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ad94-178"><strong>Обработки</strong></span><span class="sxs-lookup"><span data-stu-id="8ad94-178"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="8ad94-179">int</span><span class="sxs-lookup"><span data-stu-id="8ad94-179">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8ad94-180">Время приема-передачи на основе статистики RTCP.</span><span class="sxs-lookup"><span data-stu-id="8ad94-180">Round trip time from RTCP statistics.</span></span> <span data-ttu-id="8ad94-181">Для приемлемого качества это должно быть меньше 100 мс.</span><span class="sxs-lookup"><span data-stu-id="8ad94-181">For acceptable quality this should be less than 100ms.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ad94-182"><strong>раундтрипмакс</strong></span><span class="sxs-lookup"><span data-stu-id="8ad94-182"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="8ad94-183">int</span><span class="sxs-lookup"><span data-stu-id="8ad94-183">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8ad94-184">Максимальное время приема-передачи для аудиопотока.</span><span class="sxs-lookup"><span data-stu-id="8ad94-184">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ad94-185"><strong>овераллавгнетворкмос</strong></span><span class="sxs-lookup"><span data-stu-id="8ad94-185"><strong>OverallAvgNetworkMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="8ad94-186">десятичное число (3, 2)</span><span class="sxs-lookup"><span data-stu-id="8ad94-186">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8ad94-187">Средняя экспертная оценка качества (MOS) в широкополосной сети для вызова.</span><span class="sxs-lookup"><span data-stu-id="8ad94-187">Average wideband Network MOS for the call.</span></span> <span data-ttu-id="8ad94-188">Значение этого показателя зависит от потерь пакетов, дрожания и используемого кодека.</span><span class="sxs-lookup"><span data-stu-id="8ad94-188">This metric depends on the packet loss, jitter, and codec used.</span></span> <span data-ttu-id="8ad94-189">Диапазон — [1,0 – 5,0].</span><span class="sxs-lookup"><span data-stu-id="8ad94-189">Range is [1.0 to 5.0].</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ad94-190"><strong>овераллминнетворкмос</strong></span><span class="sxs-lookup"><span data-stu-id="8ad94-190"><strong>OverallMinNetworkMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="8ad94-191">десятичное число (3, 2)</span><span class="sxs-lookup"><span data-stu-id="8ad94-191">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8ad94-192">Минимум экспертная Network MOS для вызова.</span><span class="sxs-lookup"><span data-stu-id="8ad94-192">The minimum wideband Network MOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ad94-193"><strong>Значение sendlistenmos</strong></span><span class="sxs-lookup"><span data-stu-id="8ad94-193"><strong>SendListenMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="8ad94-194">десятичное число (3, 2)</span><span class="sxs-lookup"><span data-stu-id="8ad94-194">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8ad94-195">Средний прогнозируемый экспертная прослушивающий рейтинг MOS для звукового сигнала, в том числе уровень речи, уровень шума и характеристики устройства захвата.</span><span class="sxs-lookup"><span data-stu-id="8ad94-195">The average predicted wideband Listening MOS score for audio sent, including speech level, noise level and capture device characteristics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ad94-196"><strong>сендлистенмосмин</strong></span><span class="sxs-lookup"><span data-stu-id="8ad94-196"><strong>SendListenMOSMin</strong></span></span></p></td>
<td><p><span data-ttu-id="8ad94-197">десятичное число (3, 2)</span><span class="sxs-lookup"><span data-stu-id="8ad94-197">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8ad94-198">Минимальное значение sendlistenmos для вызова.</span><span class="sxs-lookup"><span data-stu-id="8ad94-198">The minimum SendListenMOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ad94-199"><strong>Значение recvlistenmos</strong></span><span class="sxs-lookup"><span data-stu-id="8ad94-199"><strong>RecvListenMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="8ad94-200">десятичное число (3, 2)</span><span class="sxs-lookup"><span data-stu-id="8ad94-200">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8ad94-201">Средний прогнозируемый экспертная прослушивания MOS для звука, получаемого из сети, включая уровень речи, уровень шума, кодек, условия сети и характеристики устройства захвата.</span><span class="sxs-lookup"><span data-stu-id="8ad94-201">The average predicted wideband Listening MOS score for audio received from the network including speech level, noise level, codec, network conditions and capture device characteristics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ad94-202"><strong>реквлистенмосмин</strong></span><span class="sxs-lookup"><span data-stu-id="8ad94-202"><strong>RecvListenMOSMin</strong></span></span></p></td>
<td><p><span data-ttu-id="8ad94-203">десятичное число (3, 2)</span><span class="sxs-lookup"><span data-stu-id="8ad94-203">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8ad94-204">Минимальное значение recvlistenmos для вызова.</span><span class="sxs-lookup"><span data-stu-id="8ad94-204">The minimum RecvListenMOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ad94-205"><strong>аудиофекусед</strong></span><span class="sxs-lookup"><span data-stu-id="8ad94-205"><strong>AudioFECUsed</strong></span></span></p></td>
<td><p><span data-ttu-id="8ad94-206">Битовая</span><span class="sxs-lookup"><span data-stu-id="8ad94-206">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8ad94-207">Флаг, указывающий, использовался ли для вызова звуковая FEC.</span><span class="sxs-lookup"><span data-stu-id="8ad94-207">Flag indicating if audio FEC was used for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ad94-208"><strong>RatioConcealedSamplesAvg</strong></span><span class="sxs-lookup"><span data-stu-id="8ad94-208"><strong>RatioConcealedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="8ad94-209">десятичное число (5, 2)</span><span class="sxs-lookup"><span data-stu-id="8ad94-209">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8ad94-210">Среднее отношение числа скрытых образцов, созданных функцией восстановления звука, к обычным образцам.</span><span class="sxs-lookup"><span data-stu-id="8ad94-210">Average ratio of concealed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ad94-211"><strong>ратиостретчедсамплесавг</strong></span><span class="sxs-lookup"><span data-stu-id="8ad94-211"><strong>RatioStretchedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="8ad94-212">десятичное число (5, 2)</span><span class="sxs-lookup"><span data-stu-id="8ad94-212">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8ad94-213">Среднее отношение числа растянутых образцов, созданных функцией восстановления звука, к обычным образцам.</span><span class="sxs-lookup"><span data-stu-id="8ad94-213">Average ratio of stretched samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ad94-214"><strong>ратиокомпресседсамплесавг</strong></span><span class="sxs-lookup"><span data-stu-id="8ad94-214"><strong>RatioCompressedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="8ad94-215">десятичное число (5, 2)</span><span class="sxs-lookup"><span data-stu-id="8ad94-215">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8ad94-216">Среднее отношение числа сжатых образцов, созданных функцией восстановления звука, к обычным образцам.</span><span class="sxs-lookup"><span data-stu-id="8ad94-216">Average ratio of compressed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ad94-217"><strong>Получение</strong></span><span class="sxs-lookup"><span data-stu-id="8ad94-217"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="8ad94-218">Битовая</span><span class="sxs-lookup"><span data-stu-id="8ad94-218">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8ad94-219">Получение потоковых данных на стороне получателя.</span><span class="sxs-lookup"><span data-stu-id="8ad94-219">Stream data on receiver side is received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ad94-220"><strong>Прав</strong></span><span class="sxs-lookup"><span data-stu-id="8ad94-220"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="8ad94-221">Битовая</span><span class="sxs-lookup"><span data-stu-id="8ad94-221">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8ad94-222">Получение потоковых данных на стороне отправителя.</span><span class="sxs-lookup"><span data-stu-id="8ad94-222">Stream data on sender side is received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ad94-223"><strong>сендерискаллерпаи</strong></span><span class="sxs-lookup"><span data-stu-id="8ad94-223"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="8ad94-224">Битовая</span><span class="sxs-lookup"><span data-stu-id="8ad94-224">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8ad94-225">1 означает направление потока от вызывающего абонента к вызываемому абоненту.</span><span class="sxs-lookup"><span data-stu-id="8ad94-225">1 means the stream direction is from the caller to the callee.</span></span></p>
<p><span data-ttu-id="8ad94-226">0 означает направление потока от вызываемого абонента вызывающему абоненту.</span><span class="sxs-lookup"><span data-stu-id="8ad94-226">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ad94-227"><strong>життеринтерарривалсд</strong></span><span class="sxs-lookup"><span data-stu-id="8ad94-227"><strong>JitterInterArrivalSD</strong></span></span></p></td>
<td><p><span data-ttu-id="8ad94-228">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="8ad94-228">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8ad94-229">Стандартное отклонение для времени прибытия при колебании.</span><span class="sxs-lookup"><span data-stu-id="8ad94-229">Standard deviation for jitter arrival times.</span></span></p>
<p><span data-ttu-id="8ad94-230">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8ad94-230">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ad94-231"><strong>концеалратиомакс</strong></span><span class="sxs-lookup"><span data-stu-id="8ad94-231"><strong>ConcealRatioMax</strong></span></span></p></td>
<td><p><span data-ttu-id="8ad94-232">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="8ad94-232">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8ad94-233">Максимальное соотношение пакетов, скрытые средством для воспроизведения.</span><span class="sxs-lookup"><span data-stu-id="8ad94-233">Maximum ratio of packets concealed by the healer.</span></span></p>
<p><span data-ttu-id="8ad94-234">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8ad94-234">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ad94-235"><strong>концеалратиосд</strong></span><span class="sxs-lookup"><span data-stu-id="8ad94-235"><strong>ConcealRatioSD</strong></span></span></p></td>
<td><p><span data-ttu-id="8ad94-236">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="8ad94-236">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8ad94-237">Стандартное отклонение для соотношения пакетов, которые скрываются средством "выбор".</span><span class="sxs-lookup"><span data-stu-id="8ad94-237">Standard deviation for the ratio of packets concealed by the healer.</span></span></p>
<p><span data-ttu-id="8ad94-238">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8ad94-238">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ad94-239"><strong>хеалерпаккетдропратио</strong></span><span class="sxs-lookup"><span data-stu-id="8ad94-239"><strong>HealerPacketDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="8ad94-240">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="8ad94-240">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8ad94-241">Доля пакетов, отброшенных средством сброса по сравнению с общим количеством полученных пакетов.</span><span class="sxs-lookup"><span data-stu-id="8ad94-241">Ratio of packets dropped by the healer compared to the total number of packets received.</span></span></p>
<p><span data-ttu-id="8ad94-242">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8ad94-242">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ad94-243"><strong>хеалерфекпаккетуседратио</strong></span><span class="sxs-lookup"><span data-stu-id="8ad94-243"><strong>HealerFECPacketUsedRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="8ad94-244">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="8ad94-244">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8ad94-245">Доля использованных пакетов коррекции ошибок переадресации по сравнению с общим количеством полученных пакетов.</span><span class="sxs-lookup"><span data-stu-id="8ad94-245">Ratio of used forward error correction packets compared to the total number of packets received.</span></span></p>
<p><span data-ttu-id="8ad94-246">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8ad94-246">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ad94-247"><strong>макскомпресседсамплес</strong></span><span class="sxs-lookup"><span data-stu-id="8ad94-247"><strong>MaxCompressedSamples</strong></span></span></p></td>
<td><p><span data-ttu-id="8ad94-248">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="8ad94-248">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8ad94-249">Максимальное число пакетов звукозаписи, сжатых средством завершения.</span><span class="sxs-lookup"><span data-stu-id="8ad94-249">Maximum number of audio packets that were compressed by the healer.</span></span></p>
<p><span data-ttu-id="8ad94-250">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8ad94-250">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ad94-251"><strong>лоссконжестионперцент</strong></span><span class="sxs-lookup"><span data-stu-id="8ad94-251"><strong>LossCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="8ad94-252">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="8ad94-252">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8ad94-253">Указывает процент времени, в течение которого вызов находился в состоянии перегрузки потерь.</span><span class="sxs-lookup"><span data-stu-id="8ad94-253">Indicates the percentage of the time when the call was in a loss congestion state.</span></span></p>
<p><span data-ttu-id="8ad94-254">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8ad94-254">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ad94-255"><strong>делайконжестионперцент</strong></span><span class="sxs-lookup"><span data-stu-id="8ad94-255"><strong>DelayCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="8ad94-256">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="8ad94-256">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8ad94-257">Указывает процент вызова, в течение которого перегрузка была вызвана задержкой появления сетевых пакетов.</span><span class="sxs-lookup"><span data-stu-id="8ad94-257">Indicates the percentage of the call during which congestion was caused by the delayed arrival of network packets.</span></span></p>
<p><span data-ttu-id="8ad94-258">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8ad94-258">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ad94-259"><strong>контентиондетектедперцент</strong></span><span class="sxs-lookup"><span data-stu-id="8ad94-259"><strong>ContentionDetectedPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="8ad94-260">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="8ad94-260">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8ad94-261">Указывает процент времени, в течение которого вызов конкурирует за ресурсы сети.</span><span class="sxs-lookup"><span data-stu-id="8ad94-261">Indicates the percentage of the time when the call was competing for network resources.</span></span></p>
<p><span data-ttu-id="8ad94-262">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8ad94-262">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ad94-263"><strong>бандвидсестмин</strong></span><span class="sxs-lookup"><span data-stu-id="8ad94-263"><strong>BandwidthEstMin</strong></span></span></p></td>
<td><p><span data-ttu-id="8ad94-264">int</span><span class="sxs-lookup"><span data-stu-id="8ad94-264">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8ad94-265">Минимальная сумма оценки пропускной способности, измеренной во время вызова.</span><span class="sxs-lookup"><span data-stu-id="8ad94-265">Minimum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="8ad94-266">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8ad94-266">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ad94-267"><strong>бандвидсестмакс</strong></span><span class="sxs-lookup"><span data-stu-id="8ad94-267"><strong>BandwidthEstMax</strong></span></span></p></td>
<td><p><span data-ttu-id="8ad94-268">int</span><span class="sxs-lookup"><span data-stu-id="8ad94-268">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8ad94-269">Максимальный объем оценки пропускной способности, измеренной во время вызова.</span><span class="sxs-lookup"><span data-stu-id="8ad94-269">Maximum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="8ad94-270">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8ad94-270">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ad94-271"><strong>бандвидсестстддев</strong></span><span class="sxs-lookup"><span data-stu-id="8ad94-271"><strong>BandwidthEstStdDev</strong></span></span></p></td>
<td><p><span data-ttu-id="8ad94-272">int</span><span class="sxs-lookup"><span data-stu-id="8ad94-272">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8ad94-273">Стандартное отклонение оценки пропускной способности, измеренной во время вызова.</span><span class="sxs-lookup"><span data-stu-id="8ad94-273">Standard deviation of the bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="8ad94-274">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8ad94-274">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ad94-275"><strong>бандвидсеставже</strong></span><span class="sxs-lookup"><span data-stu-id="8ad94-275"><strong>BandwidthEstAvge</strong></span></span></p></td>
<td><p><span data-ttu-id="8ad94-276">int</span><span class="sxs-lookup"><span data-stu-id="8ad94-276">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8ad94-277">Средняя величина оценки пропускной способности, измеренной во время вызова.</span><span class="sxs-lookup"><span data-stu-id="8ad94-277">Average amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="8ad94-278">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8ad94-278">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ad94-279"><strong>релативеоневайтотал</strong></span><span class="sxs-lookup"><span data-stu-id="8ad94-279"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="8ad94-280">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="8ad94-280">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8ad94-p105">Общая величина односторонней задержки. Относительная односторонняя задержка измеряет задержку между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="8ad94-p105">Total amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="8ad94-283">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8ad94-283">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ad94-284"><strong>релативеоневайавераже</strong></span><span class="sxs-lookup"><span data-stu-id="8ad94-284"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="8ad94-285">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="8ad94-285">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8ad94-p106">Средняя величина односторонней задержки. Относительная односторонняя задержка измеряет задержку между клиентом и сервером</span><span class="sxs-lookup"><span data-stu-id="8ad94-p106">Average amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="8ad94-288">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8ad94-288">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ad94-289"><strong>релативеоневаймакс</strong></span><span class="sxs-lookup"><span data-stu-id="8ad94-289"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="8ad94-290">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="8ad94-290">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8ad94-p107">Максимальная величина односторонней задержки. Относительная односторонняя задержка измеряет задержку между клиентом и сервером</span><span class="sxs-lookup"><span data-stu-id="8ad94-p107">Maximum amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="8ad94-293">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8ad94-293">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ad94-294"><strong>релативеоневайбурстоккурренцес</strong></span><span class="sxs-lookup"><span data-stu-id="8ad94-294"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="8ad94-295">int</span><span class="sxs-lookup"><span data-stu-id="8ad94-295">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8ad94-p108">Общее число повторов пакетов в одну сторону. "Пакетная" передача представляет собой передачу, при которой данные передаются посредством случайных пакетов, а не в виде устойчивого потока. С помощью этой метрики измеряется поток данных между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="8ad94-p108">Total one-way burst occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="8ad94-299">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8ad94-299">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ad94-300"><strong>релативеоневайбурстденсити</strong></span><span class="sxs-lookup"><span data-stu-id="8ad94-300"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="8ad94-301">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="8ad94-301">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8ad94-p109">Общая плотность пакетов в одну сторону. "Пакетная" передача представляет собой передачу, при которой данные передаются посредством случайных пакетов, а не в виде устойчивого потока. С помощью этой метрики измеряется поток данных между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="8ad94-p109">Total one-way burst density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="8ad94-305">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8ad94-305">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ad94-306"><strong>релативеоневайбурстдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="8ad94-306"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="8ad94-307">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="8ad94-307">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8ad94-p110">Общая длительность пакетов в одну сторону. "Пакетная" передача представляет собой передачу, при которой данные передаются посредством случайных пакетов, а не в виде устойчивого потока. С помощью этой метрики измеряется поток данных между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="8ad94-p110">Total one-way burst duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="8ad94-311">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8ad94-311">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ad94-312"><strong>релативеоневайгапоккурренцес</strong></span><span class="sxs-lookup"><span data-stu-id="8ad94-312"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="8ad94-313">int</span><span class="sxs-lookup"><span data-stu-id="8ad94-313">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8ad94-p111">Общее число повторов разрывов в одну сторону. "Пакетная" передача представляет собой передачу, при которой данные передаются посредством случайных пакетов, а не в виде устойчивого потока; разрывы указывают задержку между этими пакетами. С помощью данной метрики измеряется поток данных между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="8ad94-p111">Total one-way gap occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="8ad94-317">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8ad94-317">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ad94-318"><strong>релативеоневайгапденсити</strong></span><span class="sxs-lookup"><span data-stu-id="8ad94-318"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="8ad94-319">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="8ad94-319">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8ad94-p112">Общая плотность разрывов в одну сторону. "Пакетная" передача представляет собой передачу, при которой данные передаются посредством случайных пакетов, а не в виде устойчивого потока; разрывы указывают задержку между этими пакетами. С помощью данной метрики измеряется поток данных между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="8ad94-p112">Total one-way gap density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="8ad94-323">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8ad94-323">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ad94-324"><strong>релативеоневайгапдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="8ad94-324"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="8ad94-325">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="8ad94-325">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8ad94-p113">Общая длительность разрывов в одну сторону. "Пакетная" передача представляет собой передачу, при которой данные передаются посредством случайных пакетов, а не в виде устойчивого потока; разрывы указывают задержку между этими пакетами. С помощью данной метрики измеряется поток данных между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="8ad94-p113">Total one-way gap duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="8ad94-329">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8ad94-329">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ad94-330"><strong>декодестереоперцент</strong></span><span class="sxs-lookup"><span data-stu-id="8ad94-330"><strong>DecodeStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="8ad94-331">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="8ad94-331">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8ad94-332">Процент вызовов, декодированный как стерео.</span><span class="sxs-lookup"><span data-stu-id="8ad94-332">Percentage of the call decoded as stereo.</span></span></p>
<p><span data-ttu-id="8ad94-333">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8ad94-333">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ad94-334"><strong>аекрендерстереоперцент</strong></span><span class="sxs-lookup"><span data-stu-id="8ad94-334"><strong>AecRenderStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="8ad94-335">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="8ad94-335">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8ad94-336">Процентное соотношение вызова, отображаемое в качестве стерео, средством подавления акустического эха.</span><span class="sxs-lookup"><span data-stu-id="8ad94-336">Percentage of the call rendered as stereo by the acoustic echo canceller.</span></span></p>
<p><span data-ttu-id="8ad94-337">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8ad94-337">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ad94-338"><strong>аудиопостфекплр</strong></span><span class="sxs-lookup"><span data-stu-id="8ad94-338"><strong>AudioPostFECPLR</strong></span></span></p></td>
<td><p><span data-ttu-id="8ad94-339">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="8ad94-339">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8ad94-340">Скорость потери пакетов после применения коррекции ошибок переадресации.</span><span class="sxs-lookup"><span data-stu-id="8ad94-340">Packet loss rate after forward error correction has been applied.</span></span></p>
<p><span data-ttu-id="8ad94-341">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8ad94-341">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ad94-342"><strong>енкодестереоперцент</strong></span><span class="sxs-lookup"><span data-stu-id="8ad94-342"><strong>EncodeStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="8ad94-343">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="8ad94-343">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8ad94-344">Процент вызовов, закодированный как стерео.</span><span class="sxs-lookup"><span data-stu-id="8ad94-344">Percentage of the call encoded as stereo.</span></span></p>
<p><span data-ttu-id="8ad94-345">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8ad94-345">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ad94-346"><strong>аеккаптурестереоперцент</strong></span><span class="sxs-lookup"><span data-stu-id="8ad94-346"><strong>AecCaptureStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="8ad94-347">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="8ad94-347">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8ad94-348">Процентное соотношение вызовов, записанное в качестве стереосистемы, с помощью функции отмены акустического эха.</span><span class="sxs-lookup"><span data-stu-id="8ad94-348">Percentage of the call captured as stereo by the acoustic echo canceller.</span></span></p>
<p><span data-ttu-id="8ad94-349">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8ad94-349">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

