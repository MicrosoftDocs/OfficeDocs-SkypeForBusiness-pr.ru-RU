---
title: 'Lync Server 2013: таблица AudioStream'
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
ms.openlocfilehash: 97a8015bce118991b21b541faf588dd4d76ac784
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738349"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audiostream-table-in-lync-server-2013"></a><span data-ttu-id="337f0-102">Таблица AudioStream в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="337f0-102">AudioStream table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="337f0-103">_**Тема последнего изменения:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="337f0-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="337f0-104">Каждая запись представляет собой один звуковой поток.</span><span class="sxs-lookup"><span data-stu-id="337f0-104">Each record represents one audio stream.</span></span> <span data-ttu-id="337f0-105">Одна линейка звуковых файлов обычно состоит из двух звуковых потоков.</span><span class="sxs-lookup"><span data-stu-id="337f0-105">One audio media line usually contains two audio streams.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="337f0-106"><strong>Столбец</strong></span><span class="sxs-lookup"><span data-stu-id="337f0-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="337f0-107"><strong>Тип данных</strong></span><span class="sxs-lookup"><span data-stu-id="337f0-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="337f0-108"><strong>Ключ/индекс</strong></span><span class="sxs-lookup"><span data-stu-id="337f0-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="337f0-109"><strong>Сведения</strong></span><span class="sxs-lookup"><span data-stu-id="337f0-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="337f0-110"><strong>конференцедатетиме</strong></span><span class="sxs-lookup"><span data-stu-id="337f0-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="337f0-111">datetime</span><span class="sxs-lookup"><span data-stu-id="337f0-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="337f0-112">Primary</span><span class="sxs-lookup"><span data-stu-id="337f0-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="337f0-113">На которую ссылается <a href="lync-server-2013-medialine-table.md">Таблица медиалине в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="337f0-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="337f0-114"><strong>сессионсек</strong></span><span class="sxs-lookup"><span data-stu-id="337f0-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="337f0-115">целое</span><span class="sxs-lookup"><span data-stu-id="337f0-115">int</span></span></p></td>
<td><p><span data-ttu-id="337f0-116">Primary</span><span class="sxs-lookup"><span data-stu-id="337f0-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="337f0-117">На которую ссылается <a href="lync-server-2013-medialine-table.md">Таблица медиалине в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="337f0-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="337f0-118"><strong>медиалинелабел</strong></span><span class="sxs-lookup"><span data-stu-id="337f0-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="337f0-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="337f0-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="337f0-120">Primary</span><span class="sxs-lookup"><span data-stu-id="337f0-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="337f0-121">На которую ссылается <a href="lync-server-2013-medialine-table.md">Таблица медиалине в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="337f0-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="337f0-122"><strong>стреамид</strong></span><span class="sxs-lookup"><span data-stu-id="337f0-122"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="337f0-123">целое</span><span class="sxs-lookup"><span data-stu-id="337f0-123">int</span></span></p></td>
<td><p><span data-ttu-id="337f0-124">Primary</span><span class="sxs-lookup"><span data-stu-id="337f0-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="337f0-125">Уникальный идентификатор в строке мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="337f0-125">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="337f0-126"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="337f0-126"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="337f0-127">целое</span><span class="sxs-lookup"><span data-stu-id="337f0-127">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="337f0-128">Средняя колебание сети из статистики протокола управления временем в реальном времени (РТКП).</span><span class="sxs-lookup"><span data-stu-id="337f0-128">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="337f0-129"><strong>життеринтерарривалмакс</strong></span><span class="sxs-lookup"><span data-stu-id="337f0-129"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="337f0-130">целое</span><span class="sxs-lookup"><span data-stu-id="337f0-130">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="337f0-131">Максимальная колебание сети во время звонка.</span><span class="sxs-lookup"><span data-stu-id="337f0-131">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="337f0-132"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="337f0-132"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="337f0-133">десятичное число (5; 4)</span><span class="sxs-lookup"><span data-stu-id="337f0-133">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="337f0-134">Средняя скорость потерь пакетов во время звонка.</span><span class="sxs-lookup"><span data-stu-id="337f0-134">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="337f0-135"><strong>паккетлоссратемакс</strong></span><span class="sxs-lookup"><span data-stu-id="337f0-135"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="337f0-136">десятичное число (5; 4)</span><span class="sxs-lookup"><span data-stu-id="337f0-136">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="337f0-137">Максимальное количество потерь пакетов, замеченное во время звонка.</span><span class="sxs-lookup"><span data-stu-id="337f0-137">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="337f0-138"><strong>бурстденсити</strong></span><span class="sxs-lookup"><span data-stu-id="337f0-138"><strong>BurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="337f0-139">десятичное число (9; 4)</span><span class="sxs-lookup"><span data-stu-id="337f0-139">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="337f0-140">Средняя плотность потери пакетов во время звонка.</span><span class="sxs-lookup"><span data-stu-id="337f0-140">Average density of packet Loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="337f0-141"><strong>бурстдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="337f0-141"><strong>BurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="337f0-142">целое</span><span class="sxs-lookup"><span data-stu-id="337f0-142">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="337f0-143">Средняя продолжительность потери пакетов в течение заданных потерь во время звонка.</span><span class="sxs-lookup"><span data-stu-id="337f0-143">Average duration of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="337f0-144"><strong>бурстгапденсити</strong></span><span class="sxs-lookup"><span data-stu-id="337f0-144"><strong>BurstGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="337f0-145">десятичное число (9; 4)</span><span class="sxs-lookup"><span data-stu-id="337f0-145">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="337f0-146">Средняя плотность потери пакетов при пропуске между пакетами потери данных.</span><span class="sxs-lookup"><span data-stu-id="337f0-146">Average density of packet loss during gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="337f0-147"><strong>бурстгапдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="337f0-147"><strong>BurstGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="337f0-148">целое</span><span class="sxs-lookup"><span data-stu-id="337f0-148">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="337f0-149">Средняя продолжительность промежутков между пакетами потери данных.</span><span class="sxs-lookup"><span data-stu-id="337f0-149">Average duration of gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="337f0-150"><strong>паккетутилизатион</strong></span><span class="sxs-lookup"><span data-stu-id="337f0-150"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="337f0-151">Типом</span><span class="sxs-lookup"><span data-stu-id="337f0-151">Int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="337f0-152">Число пакетов для аудиопотока.</span><span class="sxs-lookup"><span data-stu-id="337f0-152">Packet count for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="337f0-153"><strong>Самый пропускная способность</strong></span><span class="sxs-lookup"><span data-stu-id="337f0-153"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="337f0-154">Типом</span><span class="sxs-lookup"><span data-stu-id="337f0-154">Int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="337f0-155">Оценка пропускной способности для аудиопотока.</span><span class="sxs-lookup"><span data-stu-id="337f0-155">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="337f0-156"><strong>деградатионавг</strong></span><span class="sxs-lookup"><span data-stu-id="337f0-156"><strong>DegradationAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="337f0-157">десятичное число (3, 2)</span><span class="sxs-lookup"><span data-stu-id="337f0-157">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="337f0-158">Сетевое MOS падение на весь звонок.</span><span class="sxs-lookup"><span data-stu-id="337f0-158">Network MOS Degradation for the whole call.</span></span> <span data-ttu-id="337f0-159">Диапазон от 0,0 до 5,0.</span><span class="sxs-lookup"><span data-stu-id="337f0-159">Range is 0.0 to 5.0.</span></span> <span data-ttu-id="337f0-160">Этот показатель показывает объем сетевого MOS уменьшился из-за колебаний и потери пакетов.</span><span class="sxs-lookup"><span data-stu-id="337f0-160">This metric shows the amount the Network MOS was reduced because of jitter and packet loss.</span></span> <span data-ttu-id="337f0-161">Для приемлемого качества оно должно быть менее 0,5.</span><span class="sxs-lookup"><span data-stu-id="337f0-161">For acceptable quality it should less than 0.5.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="337f0-162"><strong>деградатионмакс</strong></span><span class="sxs-lookup"><span data-stu-id="337f0-162"><strong>DegradationMax</strong></span></span></p></td>
<td><p><span data-ttu-id="337f0-163">десятичное число (3, 2)</span><span class="sxs-lookup"><span data-stu-id="337f0-163">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="337f0-164">Максимальная длина сетевого MOS во время звонка.</span><span class="sxs-lookup"><span data-stu-id="337f0-164">Maximum Network MOS degradation during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="337f0-165"><strong>деградатионжиттеравг</strong></span><span class="sxs-lookup"><span data-stu-id="337f0-165"><strong>DegradationJitterAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="337f0-166">десятичное число (3, 2)</span><span class="sxs-lookup"><span data-stu-id="337f0-166">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="337f0-167">Снижение производительности сети MOS из – за колебаний.</span><span class="sxs-lookup"><span data-stu-id="337f0-167">Network MOS degradation caused by jitter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="337f0-168"><strong>деградатионпаккетлоссавг</strong></span><span class="sxs-lookup"><span data-stu-id="337f0-168"><strong>DegradationPacketLossAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="337f0-169">десятичное число (3, 2)</span><span class="sxs-lookup"><span data-stu-id="337f0-169">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="337f0-170">Снижение производительности сети MOS из – за потери пакетов.</span><span class="sxs-lookup"><span data-stu-id="337f0-170">Network MOS degradation caused by packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="337f0-171"><strong>аудиопайлоаддескриптион</strong></span><span class="sxs-lookup"><span data-stu-id="337f0-171"><strong>AudioPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="337f0-172">целое</span><span class="sxs-lookup"><span data-stu-id="337f0-172">int</span></span></p></td>
<td><p><span data-ttu-id="337f0-173">Другом</span><span class="sxs-lookup"><span data-stu-id="337f0-173">Foreign</span></span></p></td>
<td><p><span data-ttu-id="337f0-174">Аудиокодек, использованный для вызова, на который ссылается таблица Пайлоаддескриптион.</span><span class="sxs-lookup"><span data-stu-id="337f0-174">The audio Codec used for the call, referenced from PayloadDescription Table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="337f0-175"><strong>аудиосамплерате</strong></span><span class="sxs-lookup"><span data-stu-id="337f0-175"><strong>AudioSampleRate</strong></span></span></p></td>
<td><p><span data-ttu-id="337f0-176">целое</span><span class="sxs-lookup"><span data-stu-id="337f0-176">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="337f0-177">Частота дискретизации для аудиопотока.</span><span class="sxs-lookup"><span data-stu-id="337f0-177">Sampling rate for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="337f0-178"><strong>RoundTrip</strong></span><span class="sxs-lookup"><span data-stu-id="337f0-178"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="337f0-179">целое</span><span class="sxs-lookup"><span data-stu-id="337f0-179">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="337f0-180">Время кругового приема из статистики РТКП.</span><span class="sxs-lookup"><span data-stu-id="337f0-180">Round trip time from RTCP statistics.</span></span> <span data-ttu-id="337f0-181">Для приемлемого качества оно должно быть меньше 100ms.</span><span class="sxs-lookup"><span data-stu-id="337f0-181">For acceptable quality this should be less than 100ms.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="337f0-182"><strong>раундтрипмакс</strong></span><span class="sxs-lookup"><span data-stu-id="337f0-182"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="337f0-183">целое</span><span class="sxs-lookup"><span data-stu-id="337f0-183">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="337f0-184">Максимальное время кругового приема для звукового потока.</span><span class="sxs-lookup"><span data-stu-id="337f0-184">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="337f0-185"><strong>овераллавгнетворкмос</strong></span><span class="sxs-lookup"><span data-stu-id="337f0-185"><strong>OverallAvgNetworkMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="337f0-186">десятичное число (3, 2)</span><span class="sxs-lookup"><span data-stu-id="337f0-186">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="337f0-187">Средняя сетевая MOS широкополосному для звонка.</span><span class="sxs-lookup"><span data-stu-id="337f0-187">Average wideband Network MOS for the call.</span></span> <span data-ttu-id="337f0-188">Эта метрика зависит от потерь пакетов, колебаний и используемого кодека.</span><span class="sxs-lookup"><span data-stu-id="337f0-188">This metric depends on the packet loss, jitter, and codec used.</span></span> <span data-ttu-id="337f0-189">Диапазон: [1,0 – 5,0].</span><span class="sxs-lookup"><span data-stu-id="337f0-189">Range is [1.0 to 5.0].</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="337f0-190"><strong>овераллминнетворкмос</strong></span><span class="sxs-lookup"><span data-stu-id="337f0-190"><strong>OverallMinNetworkMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="337f0-191">десятичное число (3, 2)</span><span class="sxs-lookup"><span data-stu-id="337f0-191">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="337f0-192">Минимальная широкополосному сеть MOS для звонка.</span><span class="sxs-lookup"><span data-stu-id="337f0-192">The minimum wideband Network MOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="337f0-193"><strong>сендлистенмос</strong></span><span class="sxs-lookup"><span data-stu-id="337f0-193"><strong>SendListenMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="337f0-194">десятичное число (3, 2)</span><span class="sxs-lookup"><span data-stu-id="337f0-194">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="337f0-195">Средний прогнозируемый широкополосному прослушивания MOS для звукового сигнала, в том числе уровней речи, уровней шума и характеристик устройства захвата.</span><span class="sxs-lookup"><span data-stu-id="337f0-195">The average predicted wideband Listening MOS score for audio sent, including speech level, noise level and capture device characteristics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="337f0-196"><strong>сендлистенмосмин</strong></span><span class="sxs-lookup"><span data-stu-id="337f0-196"><strong>SendListenMOSMin</strong></span></span></p></td>
<td><p><span data-ttu-id="337f0-197">десятичное число (3, 2)</span><span class="sxs-lookup"><span data-stu-id="337f0-197">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="337f0-198">Минимальная Сендлистенмос для звонка.</span><span class="sxs-lookup"><span data-stu-id="337f0-198">The minimum SendListenMOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="337f0-199"><strong>реквлистенмос</strong></span><span class="sxs-lookup"><span data-stu-id="337f0-199"><strong>RecvListenMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="337f0-200">десятичное число (3, 2)</span><span class="sxs-lookup"><span data-stu-id="337f0-200">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="337f0-201">Средний прогнозируемый широкополосному прослушивания MOS для звукового сигнала, получаемого из сети, включая уровень речи, уровень шума, кодек, условия сети и характеристики устройства захвата.</span><span class="sxs-lookup"><span data-stu-id="337f0-201">The average predicted wideband Listening MOS score for audio received from the network including speech level, noise level, codec, network conditions and capture device characteristics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="337f0-202"><strong>реквлистенмосмин</strong></span><span class="sxs-lookup"><span data-stu-id="337f0-202"><strong>RecvListenMOSMin</strong></span></span></p></td>
<td><p><span data-ttu-id="337f0-203">десятичное число (3, 2)</span><span class="sxs-lookup"><span data-stu-id="337f0-203">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="337f0-204">Минимальная Реквлистенмос для звонка.</span><span class="sxs-lookup"><span data-stu-id="337f0-204">The minimum RecvListenMOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="337f0-205"><strong>аудиофекусед</strong></span><span class="sxs-lookup"><span data-stu-id="337f0-205"><strong>AudioFECUsed</strong></span></span></p></td>
<td><p><span data-ttu-id="337f0-206">бит</span><span class="sxs-lookup"><span data-stu-id="337f0-206">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="337f0-207">Флаг, указывающий, использовался ли для звонка звуковой FEC.</span><span class="sxs-lookup"><span data-stu-id="337f0-207">Flag indicating if audio FEC was used for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="337f0-208"><strong>ратиоконцеаледсамплесавг</strong></span><span class="sxs-lookup"><span data-stu-id="337f0-208"><strong>RatioConcealedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="337f0-209">десятичное число (5; 2)</span><span class="sxs-lookup"><span data-stu-id="337f0-209">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="337f0-210">Среднее отношение количества преобразованных образцов, созданных при воспроизведении звука, на обычные выборки.</span><span class="sxs-lookup"><span data-stu-id="337f0-210">Average ratio of concealed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="337f0-211"><strong>ратиостретчедсамплесавг</strong></span><span class="sxs-lookup"><span data-stu-id="337f0-211"><strong>RatioStretchedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="337f0-212">десятичное число (5; 2)</span><span class="sxs-lookup"><span data-stu-id="337f0-212">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="337f0-213">Среднее отношение растянутых образцов, созданных при воспроизведении звука, на обычные выборки.</span><span class="sxs-lookup"><span data-stu-id="337f0-213">Average ratio of stretched samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="337f0-214"><strong>ратиокомпресседсамплесавг</strong></span><span class="sxs-lookup"><span data-stu-id="337f0-214"><strong>RatioCompressedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="337f0-215">десятичное число (5; 2)</span><span class="sxs-lookup"><span data-stu-id="337f0-215">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="337f0-216">Среднее отношение количества сжатых образцов, созданных при восстановлении звука, на обычные образцы.</span><span class="sxs-lookup"><span data-stu-id="337f0-216">Average ratio of compressed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="337f0-217"><strong>443</strong></span><span class="sxs-lookup"><span data-stu-id="337f0-217"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="337f0-218">бит</span><span class="sxs-lookup"><span data-stu-id="337f0-218">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="337f0-219">Получение потоковых данных на стороне получателя.</span><span class="sxs-lookup"><span data-stu-id="337f0-219">Stream data on receiver side is received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="337f0-220"><strong>Исходящее</strong></span><span class="sxs-lookup"><span data-stu-id="337f0-220"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="337f0-221">бит</span><span class="sxs-lookup"><span data-stu-id="337f0-221">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="337f0-222">Получение данных потока на стороне отправителя.</span><span class="sxs-lookup"><span data-stu-id="337f0-222">Stream data on sender side is received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="337f0-223"><strong>сендерискаллерпаи</strong></span><span class="sxs-lookup"><span data-stu-id="337f0-223"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="337f0-224">бит</span><span class="sxs-lookup"><span data-stu-id="337f0-224">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="337f0-225">1 — направление потока на вызываемый абонентом.</span><span class="sxs-lookup"><span data-stu-id="337f0-225">1 means the stream direction is from the caller to the callee.</span></span></p>
<p><span data-ttu-id="337f0-226">0 — направление потока из вызываемого объекта вызывающему абоненту.</span><span class="sxs-lookup"><span data-stu-id="337f0-226">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="337f0-227"><strong>життеринтерарривалсд</strong></span><span class="sxs-lookup"><span data-stu-id="337f0-227"><strong>JitterInterArrivalSD</strong></span></span></p></td>
<td><p><span data-ttu-id="337f0-228">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="337f0-228">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="337f0-229">Стандартное отклонение для наступления интервала ожидания.</span><span class="sxs-lookup"><span data-stu-id="337f0-229">Standard deviation for jitter arrival times.</span></span></p>
<p><span data-ttu-id="337f0-230">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="337f0-230">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="337f0-231"><strong>концеалратиомакс</strong></span><span class="sxs-lookup"><span data-stu-id="337f0-231"><strong>ConcealRatioMax</strong></span></span></p></td>
<td><p><span data-ttu-id="337f0-232">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="337f0-232">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="337f0-233">Максимальное соотношение пакетов, которые скрываются с помощью восстанавливаемого экземпляра.</span><span class="sxs-lookup"><span data-stu-id="337f0-233">Maximum ratio of packets concealed by the healer.</span></span></p>
<p><span data-ttu-id="337f0-234">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="337f0-234">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="337f0-235"><strong>концеалратиосд</strong></span><span class="sxs-lookup"><span data-stu-id="337f0-235"><strong>ConcealRatioSD</strong></span></span></p></td>
<td><p><span data-ttu-id="337f0-236">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="337f0-236">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="337f0-237">Стандартное отклонение для соотношения пакетов, которые скрываются с помощью восстанавливаемого экземпляра.</span><span class="sxs-lookup"><span data-stu-id="337f0-237">Standard deviation for the ratio of packets concealed by the healer.</span></span></p>
<p><span data-ttu-id="337f0-238">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="337f0-238">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="337f0-239"><strong>хеалерпаккетдропратио</strong></span><span class="sxs-lookup"><span data-stu-id="337f0-239"><strong>HealerPacketDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="337f0-240">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="337f0-240">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="337f0-241">Доля пакетов, отброшенных с помощью восстанавливаемого экземпляра по сравнению с общим количеством полученных пакетов.</span><span class="sxs-lookup"><span data-stu-id="337f0-241">Ratio of packets dropped by the healer compared to the total number of packets received.</span></span></p>
<p><span data-ttu-id="337f0-242">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="337f0-242">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="337f0-243"><strong>хеалерфекпаккетуседратио</strong></span><span class="sxs-lookup"><span data-stu-id="337f0-243"><strong>HealerFECPacketUsedRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="337f0-244">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="337f0-244">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="337f0-245">Отношение использованных пакетов исправлений ошибок переадресации к общему количеству полученных пакетов.</span><span class="sxs-lookup"><span data-stu-id="337f0-245">Ratio of used forward error correction packets compared to the total number of packets received.</span></span></p>
<p><span data-ttu-id="337f0-246">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="337f0-246">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="337f0-247"><strong>макскомпресседсамплес</strong></span><span class="sxs-lookup"><span data-stu-id="337f0-247"><strong>MaxCompressedSamples</strong></span></span></p></td>
<td><p><span data-ttu-id="337f0-248">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="337f0-248">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="337f0-249">Максимальное количество звуковых пакетов, сжатых с помощью восстанавливаемого архива.</span><span class="sxs-lookup"><span data-stu-id="337f0-249">Maximum number of audio packets that were compressed by the healer.</span></span></p>
<p><span data-ttu-id="337f0-250">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="337f0-250">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="337f0-251"><strong>лоссконжестионперцент</strong></span><span class="sxs-lookup"><span data-stu-id="337f0-251"><strong>LossCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="337f0-252">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="337f0-252">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="337f0-253">Указывает процент времени, в течение которого Звонок находился в состоянии перегрузки с потерей.</span><span class="sxs-lookup"><span data-stu-id="337f0-253">Indicates the percentage of the time when the call was in a loss congestion state.</span></span></p>
<p><span data-ttu-id="337f0-254">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="337f0-254">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="337f0-255"><strong>делайконжестионперцент</strong></span><span class="sxs-lookup"><span data-stu-id="337f0-255"><strong>DelayCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="337f0-256">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="337f0-256">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="337f0-257">Указывает процент вызова, в течение которого перегрузка была вызвана отложенным поступлением сетевых пакетов.</span><span class="sxs-lookup"><span data-stu-id="337f0-257">Indicates the percentage of the call during which congestion was caused by the delayed arrival of network packets.</span></span></p>
<p><span data-ttu-id="337f0-258">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="337f0-258">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="337f0-259"><strong>контентиондетектедперцент</strong></span><span class="sxs-lookup"><span data-stu-id="337f0-259"><strong>ContentionDetectedPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="337f0-260">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="337f0-260">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="337f0-261">Указывает процент времени, в течение которого Звонок конкурирует за ресурсы сети.</span><span class="sxs-lookup"><span data-stu-id="337f0-261">Indicates the percentage of the time when the call was competing for network resources.</span></span></p>
<p><span data-ttu-id="337f0-262">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="337f0-262">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="337f0-263"><strong>бандвидсестмин</strong></span><span class="sxs-lookup"><span data-stu-id="337f0-263"><strong>BandwidthEstMin</strong></span></span></p></td>
<td><p><span data-ttu-id="337f0-264">целое</span><span class="sxs-lookup"><span data-stu-id="337f0-264">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="337f0-265">Минимальная сумма оценки пропускной способности, измеряемая во время звонка.</span><span class="sxs-lookup"><span data-stu-id="337f0-265">Minimum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="337f0-266">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="337f0-266">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="337f0-267"><strong>бандвидсестмакс</strong></span><span class="sxs-lookup"><span data-stu-id="337f0-267"><strong>BandwidthEstMax</strong></span></span></p></td>
<td><p><span data-ttu-id="337f0-268">целое</span><span class="sxs-lookup"><span data-stu-id="337f0-268">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="337f0-269">Максимальная степень оценки пропускной способности, измеряемая во время звонка.</span><span class="sxs-lookup"><span data-stu-id="337f0-269">Maximum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="337f0-270">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="337f0-270">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="337f0-271"><strong>бандвидсестстддев</strong></span><span class="sxs-lookup"><span data-stu-id="337f0-271"><strong>BandwidthEstStdDev</strong></span></span></p></td>
<td><p><span data-ttu-id="337f0-272">целое</span><span class="sxs-lookup"><span data-stu-id="337f0-272">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="337f0-273">Стандартное отклонение оценки пропускной способности, измеряемой во время звонка.</span><span class="sxs-lookup"><span data-stu-id="337f0-273">Standard deviation of the bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="337f0-274">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="337f0-274">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="337f0-275"><strong>бандвидсеставже</strong></span><span class="sxs-lookup"><span data-stu-id="337f0-275"><strong>BandwidthEstAvge</strong></span></span></p></td>
<td><p><span data-ttu-id="337f0-276">целое</span><span class="sxs-lookup"><span data-stu-id="337f0-276">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="337f0-277">Средняя сумма оценки пропускной способности, измеряемая во время звонка.</span><span class="sxs-lookup"><span data-stu-id="337f0-277">Average amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="337f0-278">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="337f0-278">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="337f0-279"><strong>релативеоневайтотал</strong></span><span class="sxs-lookup"><span data-stu-id="337f0-279"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="337f0-280">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="337f0-280">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="337f0-281">Общая сумма односторонней задержки.</span><span class="sxs-lookup"><span data-stu-id="337f0-281">Total amount of one-way latency.</span></span> <span data-ttu-id="337f0-282">Относительная односторонняя задержка измеряет задержку между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="337f0-282">Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="337f0-283">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="337f0-283">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="337f0-284"><strong>релативеоневайавераже</strong></span><span class="sxs-lookup"><span data-stu-id="337f0-284"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="337f0-285">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="337f0-285">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="337f0-286">Средняя величина односторонней задержки.</span><span class="sxs-lookup"><span data-stu-id="337f0-286">Average amount of one-way latency.</span></span> <span data-ttu-id="337f0-287">Относительная односторонняя задержка измеряет задержку между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="337f0-287">Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="337f0-288">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="337f0-288">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="337f0-289"><strong>релативеоневаймакс</strong></span><span class="sxs-lookup"><span data-stu-id="337f0-289"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="337f0-290">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="337f0-290">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="337f0-291">Максимальная сумма односторонняя задержка.</span><span class="sxs-lookup"><span data-stu-id="337f0-291">Maximum amount of one-way latency.</span></span> <span data-ttu-id="337f0-292">Относительная односторонняя задержка измеряет задержку между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="337f0-292">Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="337f0-293">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="337f0-293">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="337f0-294"><strong>релативеоневайбурстоккурренцес</strong></span><span class="sxs-lookup"><span data-stu-id="337f0-294"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="337f0-295">целое</span><span class="sxs-lookup"><span data-stu-id="337f0-295">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="337f0-296">Общее количество односторонних вхождений.</span><span class="sxs-lookup"><span data-stu-id="337f0-296">Total one-way burst occurrences.</span></span> <span data-ttu-id="337f0-297">Одновременная передача данных — это передача, при которой данные передаются в непредсказуемые пакеты, а не в устойчивый поток.</span><span class="sxs-lookup"><span data-stu-id="337f0-297">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="337f0-298">Этот показатель измеряет поток данных между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="337f0-298">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="337f0-299">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="337f0-299">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="337f0-300"><strong>релативеоневайбурстденсити</strong></span><span class="sxs-lookup"><span data-stu-id="337f0-300"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="337f0-301">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="337f0-301">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="337f0-302">Общая односторонняя плотность нагрузки.</span><span class="sxs-lookup"><span data-stu-id="337f0-302">Total one-way burst density.</span></span> <span data-ttu-id="337f0-303">Одновременная передача данных — это передача, при которой данные передаются в непредсказуемые пакеты, а не в устойчивый поток.</span><span class="sxs-lookup"><span data-stu-id="337f0-303">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="337f0-304">Этот показатель измеряет поток данных между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="337f0-304">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="337f0-305">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="337f0-305">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="337f0-306"><strong>релативеоневайбурстдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="337f0-306"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="337f0-307">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="337f0-307">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="337f0-308">Общая продолжительность односторонней длительности.</span><span class="sxs-lookup"><span data-stu-id="337f0-308">Total one-way burst duration.</span></span> <span data-ttu-id="337f0-309">Одновременная передача данных — это передача, при которой данные передаются в непредсказуемые пакеты, а не в устойчивый поток.</span><span class="sxs-lookup"><span data-stu-id="337f0-309">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="337f0-310">Этот показатель измеряет поток данных между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="337f0-310">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="337f0-311">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="337f0-311">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="337f0-312"><strong>релативеоневайгапоккурренцес</strong></span><span class="sxs-lookup"><span data-stu-id="337f0-312"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="337f0-313">целое</span><span class="sxs-lookup"><span data-stu-id="337f0-313">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="337f0-314">Общее количество односторонних вхождений.</span><span class="sxs-lookup"><span data-stu-id="337f0-314">Total one-way gap occurrences.</span></span> <span data-ttu-id="337f0-315">Одновременная передача данных — это передача, при которой данные передаются в непредсказуемые пакеты, а не в устойчивый поток. зазоры указывают на задержку между этими пакетами.</span><span class="sxs-lookup"><span data-stu-id="337f0-315">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="337f0-316">Этот показатель измеряет поток данных между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="337f0-316">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="337f0-317">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="337f0-317">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="337f0-318"><strong>релативеоневайгапденсити</strong></span><span class="sxs-lookup"><span data-stu-id="337f0-318"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="337f0-319">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="337f0-319">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="337f0-320">Общая плотность односторонних зазоров.</span><span class="sxs-lookup"><span data-stu-id="337f0-320">Total one-way gap density.</span></span> <span data-ttu-id="337f0-321">Одновременная передача данных — это передача, при которой данные передаются в непредсказуемые пакеты, а не в устойчивый поток. зазоры указывают на задержку между этими пакетами.</span><span class="sxs-lookup"><span data-stu-id="337f0-321">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="337f0-322">Этот показатель измеряет поток данных между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="337f0-322">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="337f0-323">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="337f0-323">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="337f0-324"><strong>релативеоневайгапдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="337f0-324"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="337f0-325">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="337f0-325">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="337f0-326">Общая продолжительность односторонних промежутков.</span><span class="sxs-lookup"><span data-stu-id="337f0-326">Total one-way gap duration.</span></span> <span data-ttu-id="337f0-327">Одновременная передача данных — это передача, при которой данные передаются в непредсказуемые пакеты, а не в устойчивый поток. зазоры указывают на задержку между этими пакетами.</span><span class="sxs-lookup"><span data-stu-id="337f0-327">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="337f0-328">Этот показатель измеряет поток данных между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="337f0-328">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="337f0-329">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="337f0-329">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="337f0-330"><strong>декодестереоперцент</strong></span><span class="sxs-lookup"><span data-stu-id="337f0-330"><strong>DecodeStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="337f0-331">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="337f0-331">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="337f0-332">Процент звонка, декодированный как стерео.</span><span class="sxs-lookup"><span data-stu-id="337f0-332">Percentage of the call decoded as stereo.</span></span></p>
<p><span data-ttu-id="337f0-333">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="337f0-333">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="337f0-334"><strong>аекрендерстереоперцент</strong></span><span class="sxs-lookup"><span data-stu-id="337f0-334"><strong>AecRenderStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="337f0-335">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="337f0-335">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="337f0-336">Процент звонка, выводимого в качестве стерео, с помощью отдавления акустического эха.</span><span class="sxs-lookup"><span data-stu-id="337f0-336">Percentage of the call rendered as stereo by the acoustic echo canceller.</span></span></p>
<p><span data-ttu-id="337f0-337">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="337f0-337">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="337f0-338"><strong>аудиопостфекплр</strong></span><span class="sxs-lookup"><span data-stu-id="337f0-338"><strong>AudioPostFECPLR</strong></span></span></p></td>
<td><p><span data-ttu-id="337f0-339">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="337f0-339">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="337f0-340">Применена ставка потери пакетов после исправления ошибки переадресации.</span><span class="sxs-lookup"><span data-stu-id="337f0-340">Packet loss rate after forward error correction has been applied.</span></span></p>
<p><span data-ttu-id="337f0-341">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="337f0-341">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="337f0-342"><strong>енкодестереоперцент</strong></span><span class="sxs-lookup"><span data-stu-id="337f0-342"><strong>EncodeStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="337f0-343">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="337f0-343">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="337f0-344">Процент звонка, закодированный как стерео.</span><span class="sxs-lookup"><span data-stu-id="337f0-344">Percentage of the call encoded as stereo.</span></span></p>
<p><span data-ttu-id="337f0-345">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="337f0-345">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="337f0-346"><strong>аеккаптурестереоперцент</strong></span><span class="sxs-lookup"><span data-stu-id="337f0-346"><strong>AecCaptureStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="337f0-347">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="337f0-347">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="337f0-348">Процент звонка, захваченного как стерео, с помощью функции отмены акустического эха.</span><span class="sxs-lookup"><span data-stu-id="337f0-348">Percentage of the call captured as stereo by the acoustic echo canceller.</span></span></p>
<p><span data-ttu-id="337f0-349">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="337f0-349">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

