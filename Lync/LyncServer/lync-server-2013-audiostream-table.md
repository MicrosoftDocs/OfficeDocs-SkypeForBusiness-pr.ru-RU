---
title: 'Lync Server 2013: таблица AudioStream'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: AudioStream table
ms:assetid: 49ccbbc3-2f73-45fc-80a6-e612535cbc10
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425961(v=OCS.15)
ms:contentKeyID: 48184077
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f9412001652f4f323bdd3fb5722d0d7222535fd2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841902"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audiostream-table-in-lync-server-2013"></a><span data-ttu-id="4e696-102">Таблица AudioStream в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4e696-102">AudioStream table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4e696-103">_**Тема последнего изменения:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="4e696-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="4e696-104">Каждая запись представляет собой один звуковой поток.</span><span class="sxs-lookup"><span data-stu-id="4e696-104">Each record represents one audio stream.</span></span> <span data-ttu-id="4e696-105">Одна линейка звуковых файлов обычно состоит из двух звуковых потоков.</span><span class="sxs-lookup"><span data-stu-id="4e696-105">One audio media line usually contains two audio streams.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4e696-106"><strong>Столбец</strong></span><span class="sxs-lookup"><span data-stu-id="4e696-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="4e696-107"><strong>Тип данных</strong></span><span class="sxs-lookup"><span data-stu-id="4e696-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="4e696-108"><strong>Ключ/индекс</strong></span><span class="sxs-lookup"><span data-stu-id="4e696-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="4e696-109"><strong>Сведения</strong></span><span class="sxs-lookup"><span data-stu-id="4e696-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4e696-110"><strong>Конференцедатетиме</strong></span><span class="sxs-lookup"><span data-stu-id="4e696-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="4e696-111">datetime</span><span class="sxs-lookup"><span data-stu-id="4e696-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="4e696-112">Primary</span><span class="sxs-lookup"><span data-stu-id="4e696-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="4e696-113">На которую ссылается <a href="lync-server-2013-medialine-table.md">Таблица медиалине в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="4e696-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e696-114"><strong>Сессионсек</strong></span><span class="sxs-lookup"><span data-stu-id="4e696-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="4e696-115">целое</span><span class="sxs-lookup"><span data-stu-id="4e696-115">int</span></span></p></td>
<td><p><span data-ttu-id="4e696-116">Primary</span><span class="sxs-lookup"><span data-stu-id="4e696-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="4e696-117">На которую ссылается <a href="lync-server-2013-medialine-table.md">Таблица медиалине в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="4e696-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e696-118"><strong>Медиалинелабел</strong></span><span class="sxs-lookup"><span data-stu-id="4e696-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="4e696-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="4e696-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="4e696-120">Primary</span><span class="sxs-lookup"><span data-stu-id="4e696-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="4e696-121">На которую ссылается <a href="lync-server-2013-medialine-table.md">Таблица медиалине в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="4e696-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e696-122"><strong>Стреамид</strong></span><span class="sxs-lookup"><span data-stu-id="4e696-122"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="4e696-123">целое</span><span class="sxs-lookup"><span data-stu-id="4e696-123">int</span></span></p></td>
<td><p><span data-ttu-id="4e696-124">Primary</span><span class="sxs-lookup"><span data-stu-id="4e696-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="4e696-125">Уникальный идентификатор в строке мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="4e696-125">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e696-126"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="4e696-126"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="4e696-127">целое</span><span class="sxs-lookup"><span data-stu-id="4e696-127">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4e696-128">Средняя колебание сети из статистики протокола управления временем в реальном времени (РТКП).</span><span class="sxs-lookup"><span data-stu-id="4e696-128">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e696-129"><strong>Життеринтерарривалмакс</strong></span><span class="sxs-lookup"><span data-stu-id="4e696-129"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="4e696-130">целое</span><span class="sxs-lookup"><span data-stu-id="4e696-130">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4e696-131">Максимальная колебание сети во время звонка.</span><span class="sxs-lookup"><span data-stu-id="4e696-131">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e696-132"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="4e696-132"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="4e696-133">десятичное число (5; 4)</span><span class="sxs-lookup"><span data-stu-id="4e696-133">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4e696-134">Средняя скорость потерь пакетов во время звонка.</span><span class="sxs-lookup"><span data-stu-id="4e696-134">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e696-135"><strong>Паккетлоссратемакс</strong></span><span class="sxs-lookup"><span data-stu-id="4e696-135"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="4e696-136">десятичное число (5; 4)</span><span class="sxs-lookup"><span data-stu-id="4e696-136">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4e696-137">Максимальное количество потерь пакетов, замеченное во время звонка.</span><span class="sxs-lookup"><span data-stu-id="4e696-137">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e696-138"><strong>Бурстденсити</strong></span><span class="sxs-lookup"><span data-stu-id="4e696-138"><strong>BurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="4e696-139">десятичное число (9; 4)</span><span class="sxs-lookup"><span data-stu-id="4e696-139">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4e696-140">Средняя плотность потери пакетов во время звонка.</span><span class="sxs-lookup"><span data-stu-id="4e696-140">Average density of packet Loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e696-141"><strong>Бурстдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="4e696-141"><strong>BurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="4e696-142">целое</span><span class="sxs-lookup"><span data-stu-id="4e696-142">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4e696-143">Средняя продолжительность потери пакетов в течение заданных потерь во время звонка.</span><span class="sxs-lookup"><span data-stu-id="4e696-143">Average duration of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e696-144"><strong>Бурстгапденсити</strong></span><span class="sxs-lookup"><span data-stu-id="4e696-144"><strong>BurstGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="4e696-145">десятичное число (9; 4)</span><span class="sxs-lookup"><span data-stu-id="4e696-145">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4e696-146">Средняя плотность потери пакетов при пропуске между пакетами потери данных.</span><span class="sxs-lookup"><span data-stu-id="4e696-146">Average density of packet loss during gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e696-147"><strong>Бурстгапдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="4e696-147"><strong>BurstGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="4e696-148">целое</span><span class="sxs-lookup"><span data-stu-id="4e696-148">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4e696-149">Средняя продолжительность промежутков между пакетами потери данных.</span><span class="sxs-lookup"><span data-stu-id="4e696-149">Average duration of gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e696-150"><strong>Паккетутилизатион</strong></span><span class="sxs-lookup"><span data-stu-id="4e696-150"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="4e696-151">Типом</span><span class="sxs-lookup"><span data-stu-id="4e696-151">Int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4e696-152">Число пакетов для аудиопотока.</span><span class="sxs-lookup"><span data-stu-id="4e696-152">Packet count for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e696-153"><strong>Самый пропускная способность</strong></span><span class="sxs-lookup"><span data-stu-id="4e696-153"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="4e696-154">Типом</span><span class="sxs-lookup"><span data-stu-id="4e696-154">Int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4e696-155">Оценка пропускной способности для аудиопотока.</span><span class="sxs-lookup"><span data-stu-id="4e696-155">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e696-156"><strong>Деградатионавг</strong></span><span class="sxs-lookup"><span data-stu-id="4e696-156"><strong>DegradationAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="4e696-157">десятичное число (3, 2)</span><span class="sxs-lookup"><span data-stu-id="4e696-157">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4e696-158">Сетевое MOS падение на весь звонок.</span><span class="sxs-lookup"><span data-stu-id="4e696-158">Network MOS Degradation for the whole call.</span></span> <span data-ttu-id="4e696-159">Диапазон от 0,0 до 5,0.</span><span class="sxs-lookup"><span data-stu-id="4e696-159">Range is 0.0 to 5.0.</span></span> <span data-ttu-id="4e696-160">Этот показатель показывает объем сетевого MOS уменьшился из-за колебаний и потери пакетов.</span><span class="sxs-lookup"><span data-stu-id="4e696-160">This metric shows the amount the Network MOS was reduced because of jitter and packet loss.</span></span> <span data-ttu-id="4e696-161">Для приемлемого качества оно должно быть менее 0,5.</span><span class="sxs-lookup"><span data-stu-id="4e696-161">For acceptable quality it should less than 0.5.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e696-162"><strong>Деградатионмакс</strong></span><span class="sxs-lookup"><span data-stu-id="4e696-162"><strong>DegradationMax</strong></span></span></p></td>
<td><p><span data-ttu-id="4e696-163">десятичное число (3, 2)</span><span class="sxs-lookup"><span data-stu-id="4e696-163">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4e696-164">Максимальная длина сетевого MOS во время звонка.</span><span class="sxs-lookup"><span data-stu-id="4e696-164">Maximum Network MOS degradation during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e696-165"><strong>Деградатионжиттеравг</strong></span><span class="sxs-lookup"><span data-stu-id="4e696-165"><strong>DegradationJitterAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="4e696-166">десятичное число (3, 2)</span><span class="sxs-lookup"><span data-stu-id="4e696-166">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4e696-167">Снижение производительности сети MOS из – за колебаний.</span><span class="sxs-lookup"><span data-stu-id="4e696-167">Network MOS degradation caused by jitter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e696-168"><strong>Деградатионпаккетлоссавг</strong></span><span class="sxs-lookup"><span data-stu-id="4e696-168"><strong>DegradationPacketLossAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="4e696-169">десятичное число (3, 2)</span><span class="sxs-lookup"><span data-stu-id="4e696-169">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4e696-170">Снижение производительности сети MOS из – за потери пакетов.</span><span class="sxs-lookup"><span data-stu-id="4e696-170">Network MOS degradation caused by packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e696-171"><strong>Аудиопайлоаддескриптион</strong></span><span class="sxs-lookup"><span data-stu-id="4e696-171"><strong>AudioPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="4e696-172">целое</span><span class="sxs-lookup"><span data-stu-id="4e696-172">int</span></span></p></td>
<td><p><span data-ttu-id="4e696-173">Другом</span><span class="sxs-lookup"><span data-stu-id="4e696-173">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4e696-174">Аудиокодек, использованный для вызова, на который ссылается таблица Пайлоаддескриптион.</span><span class="sxs-lookup"><span data-stu-id="4e696-174">The audio Codec used for the call, referenced from PayloadDescription Table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e696-175"><strong>Аудиосамплерате</strong></span><span class="sxs-lookup"><span data-stu-id="4e696-175"><strong>AudioSampleRate</strong></span></span></p></td>
<td><p><span data-ttu-id="4e696-176">целое</span><span class="sxs-lookup"><span data-stu-id="4e696-176">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4e696-177">Частота дискретизации для аудиопотока.</span><span class="sxs-lookup"><span data-stu-id="4e696-177">Sampling rate for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e696-178"><strong>RoundTrip</strong></span><span class="sxs-lookup"><span data-stu-id="4e696-178"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="4e696-179">целое</span><span class="sxs-lookup"><span data-stu-id="4e696-179">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4e696-180">Время кругового приема из статистики РТКП.</span><span class="sxs-lookup"><span data-stu-id="4e696-180">Round trip time from RTCP statistics.</span></span> <span data-ttu-id="4e696-181">Для приемлемого качества оно должно быть меньше 100ms.</span><span class="sxs-lookup"><span data-stu-id="4e696-181">For acceptable quality this should be less than 100ms.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e696-182"><strong>Раундтрипмакс</strong></span><span class="sxs-lookup"><span data-stu-id="4e696-182"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="4e696-183">целое</span><span class="sxs-lookup"><span data-stu-id="4e696-183">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4e696-184">Максимальное время кругового приема для звукового потока.</span><span class="sxs-lookup"><span data-stu-id="4e696-184">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e696-185"><strong>Овераллавгнетворкмос</strong></span><span class="sxs-lookup"><span data-stu-id="4e696-185"><strong>OverallAvgNetworkMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="4e696-186">десятичное число (3, 2)</span><span class="sxs-lookup"><span data-stu-id="4e696-186">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4e696-187">Средняя сетевая MOS широкополосному для звонка.</span><span class="sxs-lookup"><span data-stu-id="4e696-187">Average wideband Network MOS for the call.</span></span> <span data-ttu-id="4e696-188">Эта метрика зависит от потерь пакетов, колебаний и используемого кодека.</span><span class="sxs-lookup"><span data-stu-id="4e696-188">This metric depends on the packet loss, jitter, and codec used.</span></span> <span data-ttu-id="4e696-189">Диапазон: [1,0 – 5,0].</span><span class="sxs-lookup"><span data-stu-id="4e696-189">Range is [1.0 to 5.0].</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e696-190"><strong>Овераллминнетворкмос</strong></span><span class="sxs-lookup"><span data-stu-id="4e696-190"><strong>OverallMinNetworkMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="4e696-191">десятичное число (3, 2)</span><span class="sxs-lookup"><span data-stu-id="4e696-191">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4e696-192">Минимальная широкополосному сеть MOS для звонка.</span><span class="sxs-lookup"><span data-stu-id="4e696-192">The minimum wideband Network MOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e696-193"><strong>Сендлистенмос</strong></span><span class="sxs-lookup"><span data-stu-id="4e696-193"><strong>SendListenMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="4e696-194">десятичное число (3, 2)</span><span class="sxs-lookup"><span data-stu-id="4e696-194">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4e696-195">Средний прогнозируемый широкополосному прослушивания MOS для звукового сигнала, в том числе уровней речи, уровней шума и характеристик устройства захвата.</span><span class="sxs-lookup"><span data-stu-id="4e696-195">The average predicted wideband Listening MOS score for audio sent, including speech level, noise level and capture device characteristics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e696-196"><strong>Сендлистенмосмин</strong></span><span class="sxs-lookup"><span data-stu-id="4e696-196"><strong>SendListenMOSMin</strong></span></span></p></td>
<td><p><span data-ttu-id="4e696-197">десятичное число (3, 2)</span><span class="sxs-lookup"><span data-stu-id="4e696-197">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4e696-198">Минимальная Сендлистенмос для звонка.</span><span class="sxs-lookup"><span data-stu-id="4e696-198">The minimum SendListenMOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e696-199"><strong>Реквлистенмос</strong></span><span class="sxs-lookup"><span data-stu-id="4e696-199"><strong>RecvListenMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="4e696-200">десятичное число (3, 2)</span><span class="sxs-lookup"><span data-stu-id="4e696-200">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4e696-201">Средний прогнозируемый широкополосному прослушивания MOS для звукового сигнала, получаемого из сети, включая уровень речи, уровень шума, кодек, условия сети и характеристики устройства захвата.</span><span class="sxs-lookup"><span data-stu-id="4e696-201">The average predicted wideband Listening MOS score for audio received from the network including speech level, noise level, codec, network conditions and capture device characteristics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e696-202"><strong>Реквлистенмосмин</strong></span><span class="sxs-lookup"><span data-stu-id="4e696-202"><strong>RecvListenMOSMin</strong></span></span></p></td>
<td><p><span data-ttu-id="4e696-203">десятичное число (3, 2)</span><span class="sxs-lookup"><span data-stu-id="4e696-203">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4e696-204">Минимальная Реквлистенмос для звонка.</span><span class="sxs-lookup"><span data-stu-id="4e696-204">The minimum RecvListenMOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e696-205"><strong>Аудиофекусед</strong></span><span class="sxs-lookup"><span data-stu-id="4e696-205"><strong>AudioFECUsed</strong></span></span></p></td>
<td><p><span data-ttu-id="4e696-206">бит</span><span class="sxs-lookup"><span data-stu-id="4e696-206">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4e696-207">Флаг, указывающий, использовался ли для звонка звуковой FEC.</span><span class="sxs-lookup"><span data-stu-id="4e696-207">Flag indicating if audio FEC was used for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e696-208"><strong>Ратиоконцеаледсамплесавг</strong></span><span class="sxs-lookup"><span data-stu-id="4e696-208"><strong>RatioConcealedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="4e696-209">десятичное число (5; 2)</span><span class="sxs-lookup"><span data-stu-id="4e696-209">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4e696-210">Среднее отношение количества преобразованных образцов, созданных при воспроизведении звука, на обычные выборки.</span><span class="sxs-lookup"><span data-stu-id="4e696-210">Average ratio of concealed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e696-211"><strong>Ратиостретчедсамплесавг</strong></span><span class="sxs-lookup"><span data-stu-id="4e696-211"><strong>RatioStretchedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="4e696-212">десятичное число (5; 2)</span><span class="sxs-lookup"><span data-stu-id="4e696-212">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4e696-213">Среднее отношение растянутых образцов, созданных при воспроизведении звука, на обычные выборки.</span><span class="sxs-lookup"><span data-stu-id="4e696-213">Average ratio of stretched samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e696-214"><strong>Ратиокомпресседсамплесавг</strong></span><span class="sxs-lookup"><span data-stu-id="4e696-214"><strong>RatioCompressedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="4e696-215">десятичное число (5; 2)</span><span class="sxs-lookup"><span data-stu-id="4e696-215">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4e696-216">Среднее отношение количества сжатых образцов, созданных при восстановлении звука, на обычные образцы.</span><span class="sxs-lookup"><span data-stu-id="4e696-216">Average ratio of compressed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e696-217"><strong>443</strong></span><span class="sxs-lookup"><span data-stu-id="4e696-217"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="4e696-218">бит</span><span class="sxs-lookup"><span data-stu-id="4e696-218">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4e696-219">Получение потоковых данных на стороне получателя.</span><span class="sxs-lookup"><span data-stu-id="4e696-219">Stream data on receiver side is received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e696-220"><strong>Исходящее</strong></span><span class="sxs-lookup"><span data-stu-id="4e696-220"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="4e696-221">бит</span><span class="sxs-lookup"><span data-stu-id="4e696-221">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4e696-222">Получение данных потока на стороне отправителя.</span><span class="sxs-lookup"><span data-stu-id="4e696-222">Stream data on sender side is received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e696-223"><strong>Сендерискаллерпаи</strong></span><span class="sxs-lookup"><span data-stu-id="4e696-223"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="4e696-224">бит</span><span class="sxs-lookup"><span data-stu-id="4e696-224">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4e696-225">1 — направление потока на вызываемый абонентом.</span><span class="sxs-lookup"><span data-stu-id="4e696-225">1 means the stream direction is from the caller to the callee.</span></span></p>
<p><span data-ttu-id="4e696-226">0 — направление потока из вызываемого объекта вызывающему абоненту.</span><span class="sxs-lookup"><span data-stu-id="4e696-226">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e696-227"><strong>Життеринтерарривалсд</strong></span><span class="sxs-lookup"><span data-stu-id="4e696-227"><strong>JitterInterArrivalSD</strong></span></span></p></td>
<td><p><span data-ttu-id="4e696-228">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="4e696-228">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4e696-229">Стандартное отклонение для наступления интервала ожидания.</span><span class="sxs-lookup"><span data-stu-id="4e696-229">Standard deviation for jitter arrival times.</span></span></p>
<p><span data-ttu-id="4e696-230">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4e696-230">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e696-231"><strong>Концеалратиомакс</strong></span><span class="sxs-lookup"><span data-stu-id="4e696-231"><strong>ConcealRatioMax</strong></span></span></p></td>
<td><p><span data-ttu-id="4e696-232">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="4e696-232">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4e696-233">Максимальное соотношение пакетов, которые скрываются с помощью восстанавливаемого экземпляра.</span><span class="sxs-lookup"><span data-stu-id="4e696-233">Maximum ratio of packets concealed by the healer.</span></span></p>
<p><span data-ttu-id="4e696-234">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4e696-234">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e696-235"><strong>Концеалратиосд</strong></span><span class="sxs-lookup"><span data-stu-id="4e696-235"><strong>ConcealRatioSD</strong></span></span></p></td>
<td><p><span data-ttu-id="4e696-236">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="4e696-236">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4e696-237">Стандартное отклонение для соотношения пакетов, которые скрываются с помощью восстанавливаемого экземпляра.</span><span class="sxs-lookup"><span data-stu-id="4e696-237">Standard deviation for the ratio of packets concealed by the healer.</span></span></p>
<p><span data-ttu-id="4e696-238">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4e696-238">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e696-239"><strong>Хеалерпаккетдропратио</strong></span><span class="sxs-lookup"><span data-stu-id="4e696-239"><strong>HealerPacketDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="4e696-240">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="4e696-240">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4e696-241">Доля пакетов, отброшенных с помощью восстанавливаемого экземпляра по сравнению с общим количеством полученных пакетов.</span><span class="sxs-lookup"><span data-stu-id="4e696-241">Ratio of packets dropped by the healer compared to the total number of packets received.</span></span></p>
<p><span data-ttu-id="4e696-242">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4e696-242">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e696-243"><strong>Хеалерфекпаккетуседратио</strong></span><span class="sxs-lookup"><span data-stu-id="4e696-243"><strong>HealerFECPacketUsedRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="4e696-244">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="4e696-244">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4e696-245">Отношение использованных пакетов исправлений ошибок переадресации к общему количеству полученных пакетов.</span><span class="sxs-lookup"><span data-stu-id="4e696-245">Ratio of used forward error correction packets compared to the total number of packets received.</span></span></p>
<p><span data-ttu-id="4e696-246">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4e696-246">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e696-247"><strong>Макскомпресседсамплес</strong></span><span class="sxs-lookup"><span data-stu-id="4e696-247"><strong>MaxCompressedSamples</strong></span></span></p></td>
<td><p><span data-ttu-id="4e696-248">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="4e696-248">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4e696-249">Максимальное количество звуковых пакетов, сжатых с помощью восстанавливаемого архива.</span><span class="sxs-lookup"><span data-stu-id="4e696-249">Maximum number of audio packets that were compressed by the healer.</span></span></p>
<p><span data-ttu-id="4e696-250">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4e696-250">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e696-251"><strong>Лоссконжестионперцент</strong></span><span class="sxs-lookup"><span data-stu-id="4e696-251"><strong>LossCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="4e696-252">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="4e696-252">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4e696-253">Указывает процент времени, в течение которого Звонок находился в состоянии перегрузки с потерей.</span><span class="sxs-lookup"><span data-stu-id="4e696-253">Indicates the percentage of the time when the call was in a loss congestion state.</span></span></p>
<p><span data-ttu-id="4e696-254">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4e696-254">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e696-255"><strong>Делайконжестионперцент</strong></span><span class="sxs-lookup"><span data-stu-id="4e696-255"><strong>DelayCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="4e696-256">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="4e696-256">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4e696-257">Указывает процент вызова, в течение которого перегрузка была вызвана отложенным поступлением сетевых пакетов.</span><span class="sxs-lookup"><span data-stu-id="4e696-257">Indicates the percentage of the call during which congestion was caused by the delayed arrival of network packets.</span></span></p>
<p><span data-ttu-id="4e696-258">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4e696-258">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e696-259"><strong>Контентиондетектедперцент</strong></span><span class="sxs-lookup"><span data-stu-id="4e696-259"><strong>ContentionDetectedPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="4e696-260">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="4e696-260">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4e696-261">Указывает процент времени, в течение которого Звонок конкурирует за ресурсы сети.</span><span class="sxs-lookup"><span data-stu-id="4e696-261">Indicates the percentage of the time when the call was competing for network resources.</span></span></p>
<p><span data-ttu-id="4e696-262">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4e696-262">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e696-263"><strong>Бандвидсестмин</strong></span><span class="sxs-lookup"><span data-stu-id="4e696-263"><strong>BandwidthEstMin</strong></span></span></p></td>
<td><p><span data-ttu-id="4e696-264">целое</span><span class="sxs-lookup"><span data-stu-id="4e696-264">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4e696-265">Минимальная сумма оценки пропускной способности, измеряемая во время звонка.</span><span class="sxs-lookup"><span data-stu-id="4e696-265">Minimum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="4e696-266">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4e696-266">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e696-267"><strong>Бандвидсестмакс</strong></span><span class="sxs-lookup"><span data-stu-id="4e696-267"><strong>BandwidthEstMax</strong></span></span></p></td>
<td><p><span data-ttu-id="4e696-268">целое</span><span class="sxs-lookup"><span data-stu-id="4e696-268">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4e696-269">Максимальная степень оценки пропускной способности, измеряемая во время звонка.</span><span class="sxs-lookup"><span data-stu-id="4e696-269">Maximum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="4e696-270">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4e696-270">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e696-271"><strong>Бандвидсестстддев</strong></span><span class="sxs-lookup"><span data-stu-id="4e696-271"><strong>BandwidthEstStdDev</strong></span></span></p></td>
<td><p><span data-ttu-id="4e696-272">целое</span><span class="sxs-lookup"><span data-stu-id="4e696-272">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4e696-273">Стандартное отклонение оценки пропускной способности, измеряемой во время звонка.</span><span class="sxs-lookup"><span data-stu-id="4e696-273">Standard deviation of the bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="4e696-274">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4e696-274">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e696-275"><strong>Бандвидсеставже</strong></span><span class="sxs-lookup"><span data-stu-id="4e696-275"><strong>BandwidthEstAvge</strong></span></span></p></td>
<td><p><span data-ttu-id="4e696-276">целое</span><span class="sxs-lookup"><span data-stu-id="4e696-276">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4e696-277">Средняя сумма оценки пропускной способности, измеряемая во время звонка.</span><span class="sxs-lookup"><span data-stu-id="4e696-277">Average amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="4e696-278">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4e696-278">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e696-279"><strong>Релативеоневайтотал</strong></span><span class="sxs-lookup"><span data-stu-id="4e696-279"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="4e696-280">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="4e696-280">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4e696-281">Общая сумма односторонней задержки.</span><span class="sxs-lookup"><span data-stu-id="4e696-281">Total amount of one-way latency.</span></span> <span data-ttu-id="4e696-282">Относительная односторонняя задержка измеряет задержку между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="4e696-282">Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="4e696-283">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4e696-283">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e696-284"><strong>Релативеоневайавераже</strong></span><span class="sxs-lookup"><span data-stu-id="4e696-284"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="4e696-285">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="4e696-285">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4e696-286">Средняя величина односторонней задержки.</span><span class="sxs-lookup"><span data-stu-id="4e696-286">Average amount of one-way latency.</span></span> <span data-ttu-id="4e696-287">Относительная односторонняя задержка измеряет задержку между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="4e696-287">Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="4e696-288">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4e696-288">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e696-289"><strong>Релативеоневаймакс</strong></span><span class="sxs-lookup"><span data-stu-id="4e696-289"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="4e696-290">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="4e696-290">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4e696-291">Максимальная сумма односторонняя задержка.</span><span class="sxs-lookup"><span data-stu-id="4e696-291">Maximum amount of one-way latency.</span></span> <span data-ttu-id="4e696-292">Относительная односторонняя задержка измеряет задержку между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="4e696-292">Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="4e696-293">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4e696-293">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e696-294"><strong>Релативеоневайбурстоккурренцес</strong></span><span class="sxs-lookup"><span data-stu-id="4e696-294"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="4e696-295">целое</span><span class="sxs-lookup"><span data-stu-id="4e696-295">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4e696-296">Общее количество односторонних вхождений.</span><span class="sxs-lookup"><span data-stu-id="4e696-296">Total one-way burst occurrences.</span></span> <span data-ttu-id="4e696-297">Одновременная передача данных — это передача, при которой данные передаются в непредсказуемые пакеты, а не в устойчивый поток.</span><span class="sxs-lookup"><span data-stu-id="4e696-297">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="4e696-298">Этот показатель измеряет поток данных между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="4e696-298">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="4e696-299">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4e696-299">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e696-300"><strong>Релативеоневайбурстденсити</strong></span><span class="sxs-lookup"><span data-stu-id="4e696-300"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="4e696-301">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="4e696-301">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4e696-302">Общая односторонняя плотность нагрузки.</span><span class="sxs-lookup"><span data-stu-id="4e696-302">Total one-way burst density.</span></span> <span data-ttu-id="4e696-303">Одновременная передача данных — это передача, при которой данные передаются в непредсказуемые пакеты, а не в устойчивый поток.</span><span class="sxs-lookup"><span data-stu-id="4e696-303">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="4e696-304">Этот показатель измеряет поток данных между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="4e696-304">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="4e696-305">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4e696-305">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e696-306"><strong>Релативеоневайбурстдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="4e696-306"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="4e696-307">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="4e696-307">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4e696-308">Общая продолжительность односторонней длительности.</span><span class="sxs-lookup"><span data-stu-id="4e696-308">Total one-way burst duration.</span></span> <span data-ttu-id="4e696-309">Одновременная передача данных — это передача, при которой данные передаются в непредсказуемые пакеты, а не в устойчивый поток.</span><span class="sxs-lookup"><span data-stu-id="4e696-309">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="4e696-310">Этот показатель измеряет поток данных между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="4e696-310">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="4e696-311">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4e696-311">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e696-312"><strong>Релативеоневайгапоккурренцес</strong></span><span class="sxs-lookup"><span data-stu-id="4e696-312"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="4e696-313">целое</span><span class="sxs-lookup"><span data-stu-id="4e696-313">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4e696-314">Общее количество односторонних вхождений.</span><span class="sxs-lookup"><span data-stu-id="4e696-314">Total one-way gap occurrences.</span></span> <span data-ttu-id="4e696-315">Одновременная передача данных — это передача, при которой данные передаются в непредсказуемые пакеты, а не в устойчивый поток. зазоры указывают на задержку между этими пакетами.</span><span class="sxs-lookup"><span data-stu-id="4e696-315">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="4e696-316">Этот показатель измеряет поток данных между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="4e696-316">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="4e696-317">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4e696-317">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e696-318"><strong>Релативеоневайгапденсити</strong></span><span class="sxs-lookup"><span data-stu-id="4e696-318"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="4e696-319">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="4e696-319">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4e696-320">Общая плотность односторонних зазоров.</span><span class="sxs-lookup"><span data-stu-id="4e696-320">Total one-way gap density.</span></span> <span data-ttu-id="4e696-321">Одновременная передача данных — это передача, при которой данные передаются в непредсказуемые пакеты, а не в устойчивый поток. зазоры указывают на задержку между этими пакетами.</span><span class="sxs-lookup"><span data-stu-id="4e696-321">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="4e696-322">Этот показатель измеряет поток данных между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="4e696-322">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="4e696-323">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4e696-323">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e696-324"><strong>Релативеоневайгапдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="4e696-324"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="4e696-325">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="4e696-325">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4e696-326">Общая продолжительность односторонних промежутков.</span><span class="sxs-lookup"><span data-stu-id="4e696-326">Total one-way gap duration.</span></span> <span data-ttu-id="4e696-327">Одновременная передача данных — это передача, при которой данные передаются в непредсказуемые пакеты, а не в устойчивый поток. зазоры указывают на задержку между этими пакетами.</span><span class="sxs-lookup"><span data-stu-id="4e696-327">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="4e696-328">Этот показатель измеряет поток данных между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="4e696-328">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="4e696-329">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4e696-329">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e696-330"><strong>Декодестереоперцент</strong></span><span class="sxs-lookup"><span data-stu-id="4e696-330"><strong>DecodeStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="4e696-331">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="4e696-331">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4e696-332">Процент звонка, декодированный как стерео.</span><span class="sxs-lookup"><span data-stu-id="4e696-332">Percentage of the call decoded as stereo.</span></span></p>
<p><span data-ttu-id="4e696-333">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4e696-333">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e696-334"><strong>Аекрендерстереоперцент</strong></span><span class="sxs-lookup"><span data-stu-id="4e696-334"><strong>AecRenderStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="4e696-335">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="4e696-335">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4e696-336">Процент звонка, выводимого в качестве стерео, с помощью отдавления акустического эха.</span><span class="sxs-lookup"><span data-stu-id="4e696-336">Percentage of the call rendered as stereo by the acoustic echo canceller.</span></span></p>
<p><span data-ttu-id="4e696-337">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4e696-337">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e696-338"><strong>Аудиопостфекплр</strong></span><span class="sxs-lookup"><span data-stu-id="4e696-338"><strong>AudioPostFECPLR</strong></span></span></p></td>
<td><p><span data-ttu-id="4e696-339">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="4e696-339">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4e696-340">Применена ставка потери пакетов после исправления ошибки переадресации.</span><span class="sxs-lookup"><span data-stu-id="4e696-340">Packet loss rate after forward error correction has been applied.</span></span></p>
<p><span data-ttu-id="4e696-341">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4e696-341">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e696-342"><strong>Енкодестереоперцент</strong></span><span class="sxs-lookup"><span data-stu-id="4e696-342"><strong>EncodeStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="4e696-343">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="4e696-343">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4e696-344">Процент звонка, закодированный как стерео.</span><span class="sxs-lookup"><span data-stu-id="4e696-344">Percentage of the call encoded as stereo.</span></span></p>
<p><span data-ttu-id="4e696-345">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4e696-345">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e696-346"><strong>Аеккаптурестереоперцент</strong></span><span class="sxs-lookup"><span data-stu-id="4e696-346"><strong>AecCaptureStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="4e696-347">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="4e696-347">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4e696-348">Процент звонка, захваченного как стерео, с помощью функции отмены акустического эха.</span><span class="sxs-lookup"><span data-stu-id="4e696-348">Percentage of the call captured as stereo by the acoustic echo canceller.</span></span></p>
<p><span data-ttu-id="4e696-349">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4e696-349">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

