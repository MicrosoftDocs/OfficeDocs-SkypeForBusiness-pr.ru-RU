---
title: 'Lync Server 2013: таблица AudioSignal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: AudioSignal table
ms:assetid: 0013c8c6-cdf9-4d70-bc2a-cddd1560f66b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398064(v=OCS.15)
ms:contentKeyID: 48183217
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 950c8457f80c69af5875064fff55c5ac7df61b24
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739579"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audiosignal-table-in-lync-server-2013"></a><span data-ttu-id="d89f7-102">Таблица AudioSignal в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d89f7-102">AudioSignal table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d89f7-103">_**Тема последнего изменения:** 2013-11-12_</span><span class="sxs-lookup"><span data-stu-id="d89f7-103">_**Topic Last Modified:** 2013-11-12_</span></span>

<span data-ttu-id="d89f7-104">Каждая запись представляет метрики звукового сигнала для одной конечной точки.</span><span class="sxs-lookup"><span data-stu-id="d89f7-104">Each record represents audio signal metrics for one endpoint.</span></span> <span data-ttu-id="d89f7-105">Обычно каждый звонок состоит из двух записей: одной из них, а другая — для вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="d89f7-105">Usually, each call has two records, one is for caller, and one is for callee.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d89f7-106"><strong>Столбец</strong></span><span class="sxs-lookup"><span data-stu-id="d89f7-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="d89f7-107"><strong>Тип данных</strong></span><span class="sxs-lookup"><span data-stu-id="d89f7-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="d89f7-108"><strong>Ключ/индекс</strong></span><span class="sxs-lookup"><span data-stu-id="d89f7-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="d89f7-109"><strong>Сведения</strong></span><span class="sxs-lookup"><span data-stu-id="d89f7-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d89f7-110"><strong>конференцедатетиме</strong></span><span class="sxs-lookup"><span data-stu-id="d89f7-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="d89f7-111">datetime</span><span class="sxs-lookup"><span data-stu-id="d89f7-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="d89f7-112">Primary</span><span class="sxs-lookup"><span data-stu-id="d89f7-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="d89f7-113">На которую ссылается <a href="lync-server-2013-medialine-table.md">Таблица медиалине в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="d89f7-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d89f7-114"><strong>сессионсек</strong></span><span class="sxs-lookup"><span data-stu-id="d89f7-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="d89f7-115">целое</span><span class="sxs-lookup"><span data-stu-id="d89f7-115">int</span></span></p></td>
<td><p><span data-ttu-id="d89f7-116">Primary</span><span class="sxs-lookup"><span data-stu-id="d89f7-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="d89f7-117">На которую ссылается <a href="lync-server-2013-medialine-table.md">Таблица медиалине в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="d89f7-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d89f7-118"><strong>медиалинелабел</strong></span><span class="sxs-lookup"><span data-stu-id="d89f7-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="d89f7-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="d89f7-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="d89f7-120">Primary</span><span class="sxs-lookup"><span data-stu-id="d89f7-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="d89f7-121">На которую ссылается <a href="lync-server-2013-medialine-table.md">Таблица медиалине в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="d89f7-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d89f7-122"><strong>фромкаллер</strong></span><span class="sxs-lookup"><span data-stu-id="d89f7-122"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="d89f7-123">бит</span><span class="sxs-lookup"><span data-stu-id="d89f7-123">bit</span></span></p></td>
<td><p><span data-ttu-id="d89f7-124">Primary</span><span class="sxs-lookup"><span data-stu-id="d89f7-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="d89f7-125">0: данные вызывающего абонента</span><span class="sxs-lookup"><span data-stu-id="d89f7-125">0: Callee’s data</span></span></p>
<p><span data-ttu-id="d89f7-126">1: данные вызывающего абонента</span><span class="sxs-lookup"><span data-stu-id="d89f7-126">1: Caller’s data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d89f7-127"><strong>сендсигналлевел</strong></span><span class="sxs-lookup"><span data-stu-id="d89f7-127"><strong>SendSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="d89f7-128">целое</span><span class="sxs-lookup"><span data-stu-id="d89f7-128">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d89f7-129">Обозначает уровень звукового сигнала после аналогового усиления контроля.</span><span class="sxs-lookup"><span data-stu-id="d89f7-129">Represents the Post-Analog Gain Control audio signal level.</span></span> <span data-ttu-id="d89f7-130">Единицей измерения для этой метрики является Дбмо.</span><span class="sxs-lookup"><span data-stu-id="d89f7-130">The unit for this metric is dBmo.</span></span> <span data-ttu-id="d89f7-131">Для приемлемого качества оно должно быть не менее 30 Дбмо.</span><span class="sxs-lookup"><span data-stu-id="d89f7-131">For acceptable quality, it should be at least 30 dBmo.</span></span> <span data-ttu-id="d89f7-132">Этот показатель не передается сервером Конференции и IP-телефонами по протоколу A/V.</span><span class="sxs-lookup"><span data-stu-id="d89f7-132">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d89f7-133"><strong>реквсигналлевел</strong></span><span class="sxs-lookup"><span data-stu-id="d89f7-133"><strong>RecvSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="d89f7-134">целое</span><span class="sxs-lookup"><span data-stu-id="d89f7-134">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d89f7-135">Смотрите Сендсигналлевел.</span><span class="sxs-lookup"><span data-stu-id="d89f7-135">See SendSignalLevel.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d89f7-136"><strong>сендноиселевел</strong></span><span class="sxs-lookup"><span data-stu-id="d89f7-136"><strong>SendNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="d89f7-137">целое</span><span class="sxs-lookup"><span data-stu-id="d89f7-137">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d89f7-138">Обозначает уровень звукового шума, поступающего после аналогового усиления.</span><span class="sxs-lookup"><span data-stu-id="d89f7-138">Represents the Post-Analog Gain Control audio noise level.</span></span> <span data-ttu-id="d89f7-139">Единицей измерения для этой метрики является Дбмо.</span><span class="sxs-lookup"><span data-stu-id="d89f7-139">The unit for this metric is dBmo.</span></span> <span data-ttu-id="d89f7-140">Для приемлемого качества оно должно быть менее 35 Дбмо.</span><span class="sxs-lookup"><span data-stu-id="d89f7-140">For acceptable quality, it should be less than 35 dBmo.</span></span> <span data-ttu-id="d89f7-141">Этот показатель не передается сервером Конференции и IP-телефонами по протоколу A/V.</span><span class="sxs-lookup"><span data-stu-id="d89f7-141">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d89f7-142"><strong>реквноиселевел</strong></span><span class="sxs-lookup"><span data-stu-id="d89f7-142"><strong>RecvNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="d89f7-143">целое</span><span class="sxs-lookup"><span data-stu-id="d89f7-143">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d89f7-144">Смотрите Сендноиселевел.</span><span class="sxs-lookup"><span data-stu-id="d89f7-144">See SendNoiseLevel.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d89f7-145"><strong>ечоретурн</strong></span><span class="sxs-lookup"><span data-stu-id="d89f7-145"><strong>EchoReturn</strong></span></span></p></td>
<td><p><span data-ttu-id="d89f7-146">целое</span><span class="sxs-lookup"><span data-stu-id="d89f7-146">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d89f7-147">Показатель возвращающего потери при возврате эха.</span><span class="sxs-lookup"><span data-stu-id="d89f7-147">Echo Return Loss Enhancement metric.</span></span> <span data-ttu-id="d89f7-148">Единицей измерения для этой метрики является dB.</span><span class="sxs-lookup"><span data-stu-id="d89f7-148">The unit for this metric is dB.</span></span> <span data-ttu-id="d89f7-149">Более низкие значения представляют менее эхо.</span><span class="sxs-lookup"><span data-stu-id="d89f7-149">Lower values represent less echo.</span></span> <span data-ttu-id="d89f7-150">Этот показатель не передается сервером Конференции и IP-телефонами по протоколу A/V.</span><span class="sxs-lookup"><span data-stu-id="d89f7-150">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d89f7-151"><strong>аудиоспеакерглитчрате</strong></span><span class="sxs-lookup"><span data-stu-id="d89f7-151"><strong>AudioSpeakerGlitchRate</strong></span></span></p></td>
<td><p><span data-ttu-id="d89f7-152">целое</span><span class="sxs-lookup"><span data-stu-id="d89f7-152">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d89f7-153">Среднее число сбоев в течение пяти минут для отрисовки динамик.</span><span class="sxs-lookup"><span data-stu-id="d89f7-153">Average glitches per five minutes for the loudspeaker rendering.</span></span> <span data-ttu-id="d89f7-154">Для хорошего качества это должно быть меньше, чем один за пять минут.</span><span class="sxs-lookup"><span data-stu-id="d89f7-154">For good quality, this should be less than one per five minutes.</span></span> <span data-ttu-id="d89f7-155">Не сообщается серверам конференц-связи, серверам или IP-телефонам.</span><span class="sxs-lookup"><span data-stu-id="d89f7-155">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d89f7-156"><strong>аудиомикглитчрате</strong></span><span class="sxs-lookup"><span data-stu-id="d89f7-156"><strong>AudioMicGlitchRate</strong></span></span></p></td>
<td><p><span data-ttu-id="d89f7-157">целое</span><span class="sxs-lookup"><span data-stu-id="d89f7-157">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d89f7-158">Среднее число сбоев в течение пяти минут для захвата микрофона.</span><span class="sxs-lookup"><span data-stu-id="d89f7-158">Average glitches per five minutes for the microphone capture.</span></span> <span data-ttu-id="d89f7-159">Для хорошего качества это должно быть менее чем на одну 5 минут.</span><span class="sxs-lookup"><span data-stu-id="d89f7-159">For good quality this should be less than one per five minutes.</span></span> <span data-ttu-id="d89f7-160">Не сообщается серверам конференц-связи, серверам или IP-телефонам.</span><span class="sxs-lookup"><span data-stu-id="d89f7-160">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d89f7-161"><strong>аудиотиместампдрифтратемик</strong></span><span class="sxs-lookup"><span data-stu-id="d89f7-161"><strong>AudioTimestampDriftRateMic</strong></span></span></p></td>
<td><p><span data-ttu-id="d89f7-162">десятичное число (9, 2)</span><span class="sxs-lookup"><span data-stu-id="d89f7-162">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d89f7-163">Частота расхождения синхронизирующих сигналов для микрофона, относящихся к тактовой частоте процессора.</span><span class="sxs-lookup"><span data-stu-id="d89f7-163">Microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d89f7-164"><strong>аудиотиместампдрифтратеспк</strong></span><span class="sxs-lookup"><span data-stu-id="d89f7-164"><strong>AudioTimestampDriftRateSpk</strong></span></span></p></td>
<td><p><span data-ttu-id="d89f7-165">десятичное число (9, 2)</span><span class="sxs-lookup"><span data-stu-id="d89f7-165">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d89f7-166">Частота расхождения синхронизирующих импульсов устройства для динамиков относительно часов процессора.</span><span class="sxs-lookup"><span data-stu-id="d89f7-166">Speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d89f7-167"><strong>аудиотиместамперрормикмс</strong></span><span class="sxs-lookup"><span data-stu-id="d89f7-167"><strong>AudioTimestampErrorMicMs</strong></span></span></p></td>
<td><p><span data-ttu-id="d89f7-168">десятичное число (9, 2)</span><span class="sxs-lookup"><span data-stu-id="d89f7-168">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d89f7-169">Частота расхождения синхронизирующих импульсов устройства для динамиков относительно часов процессора.</span><span class="sxs-lookup"><span data-stu-id="d89f7-169">Speaker device clock drift rate, relative to CPU clock.</span></span></p>
<p><span data-ttu-id="d89f7-170">Средняя пометка времени потока захвата микрофона в миллисекундах за последние 20 секунд звонка.</span><span class="sxs-lookup"><span data-stu-id="d89f7-170">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d89f7-171"><strong>аудиотиместамперрорспкмс</strong></span><span class="sxs-lookup"><span data-stu-id="d89f7-171"><strong>AudioTimestampErrorSpkMs</strong></span></span></p></td>
<td><p><span data-ttu-id="d89f7-172">десятичное число (9, 2)</span><span class="sxs-lookup"><span data-stu-id="d89f7-172">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d89f7-173">Средняя отметка времени линейного потока обработки динамиков в миллисекундах за последние 20 секунд вызова.</span><span class="sxs-lookup"><span data-stu-id="d89f7-173">Average speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d89f7-174"><strong>всентрикаусес</strong></span><span class="sxs-lookup"><span data-stu-id="d89f7-174"><strong>VsEntryCauses</strong></span></span></p></td>
<td><p><span data-ttu-id="d89f7-175">smallint</span><span class="sxs-lookup"><span data-stu-id="d89f7-175">smallint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d89f7-176">Голосовая связь — это режим двусторонней печати с ограниченными возможностями перерывов.</span><span class="sxs-lookup"><span data-stu-id="d89f7-176">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="d89f7-177">Причины для записи голосового переключателя:</span><span class="sxs-lookup"><span data-stu-id="d89f7-177">Causes of voice switch entry:</span></span></p>
<p><span data-ttu-id="d89f7-178">ENTER_VS_BADTS 0x01</span><span class="sxs-lookup"><span data-stu-id="d89f7-178">ENTER_VS_BADTS 0x01</span></span></p>
<p><span data-ttu-id="d89f7-179">ENTER_VS_ECHO 0x02</span><span class="sxs-lookup"><span data-stu-id="d89f7-179">ENTER_VS_ECHO 0x02</span></span></p>
<p><span data-ttu-id="d89f7-180">ENTER_VS_FORCEORCONVERGENCE 0x04</span><span class="sxs-lookup"><span data-stu-id="d89f7-180">ENTER_VS_FORCEORCONVERGENCE 0x04</span></span></p>
<p><span data-ttu-id="d89f7-181">ENTER_VS_DNLP 0x08</span><span class="sxs-lookup"><span data-stu-id="d89f7-181">ENTER_VS_DNLP 0x08</span></span></p>
<p><span data-ttu-id="d89f7-182">Причина может быть сочетанием отдельных причин.</span><span class="sxs-lookup"><span data-stu-id="d89f7-182">The cause can be a combination of those individual causes.</span></span> <span data-ttu-id="d89f7-183">ENTER_VS_FORCEORCONVERGENCE может быть включена только в RegKey для целей тестирования.</span><span class="sxs-lookup"><span data-stu-id="d89f7-183">ENTER_VS_FORCEORCONVERGENCE can only be enabled by regkey for test purpose.</span></span></p>
<p><span data-ttu-id="d89f7-184">Тип данных этого столбца изменен в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d89f7-184">The data type for this column was changed in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d89f7-185"><strong>ечоевенткаусес</strong></span><span class="sxs-lookup"><span data-stu-id="d89f7-185"><strong>EchoEventCauses</strong></span></span></p></td>
<td><p><span data-ttu-id="d89f7-186">tinyint</span><span class="sxs-lookup"><span data-stu-id="d89f7-186">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d89f7-187">Причины возникновения события echo:</span><span class="sxs-lookup"><span data-stu-id="d89f7-187">Causes of an echo event:</span></span></p>
<p><span data-ttu-id="d89f7-188">ECHO_EVENT_BAD_TIMESTAMP 0x01</span><span class="sxs-lookup"><span data-stu-id="d89f7-188">ECHO_EVENT_BAD_TIMESTAMP 0x01</span></span></p>
<p><span data-ttu-id="d89f7-189">ECHO_EVENT_POSTAEC_ECHO 0x02</span><span class="sxs-lookup"><span data-stu-id="d89f7-189">ECHO_EVENT_POSTAEC_ECHO 0x02</span></span></p>
<p><span data-ttu-id="d89f7-190">ECHO_EVENT_ANLP 0x04</span><span class="sxs-lookup"><span data-stu-id="d89f7-190">ECHO_EVENT_ANLP 0x04</span></span></p>
<p><span data-ttu-id="d89f7-191">ECHO_EVENT_DNLP 0x08</span><span class="sxs-lookup"><span data-stu-id="d89f7-191">ECHO_EVENT_DNLP 0x08</span></span></p>
<p><span data-ttu-id="d89f7-192">ECHO_EVENT_MIC_CLIPPING 0x10</span><span class="sxs-lookup"><span data-stu-id="d89f7-192">ECHO_EVENT_MIC_CLIPPING 0x10</span></span></p>
<p><span data-ttu-id="d89f7-193">ECHO_EVENT_BAD_STATE 0x20</span><span class="sxs-lookup"><span data-stu-id="d89f7-193">ECHO_EVENT_BAD_STATE 0x20</span></span></p>
<p><span data-ttu-id="d89f7-194">Причина может быть сочетанием отдельных причин.</span><span class="sxs-lookup"><span data-stu-id="d89f7-194">The cause can be a combination of those individual causes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d89f7-195"><strong>ечоперцентмиЦин</strong></span><span class="sxs-lookup"><span data-stu-id="d89f7-195"><strong>EchoPercentMicIn</strong></span></span></p></td>
<td><p><span data-ttu-id="d89f7-196">десятичное число (5; 2)</span><span class="sxs-lookup"><span data-stu-id="d89f7-196">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d89f7-p109">Процент времени, когда в потоке захвата микрофоном обнаруживался эхосигнал. Обычно низкие значения отображаются для гарнитур или телефонных трубок, а высокие значения – для телефонных или автономных динамиков. Для устройств, которые поддерживают встроенную возможность подавления акустического эхосигнала, высокие значения указывают утечку эхосигнала. Для других устройств эти единицы измерения не должны использоваться для оценки качества устройства.</span><span class="sxs-lookup"><span data-stu-id="d89f7-p109">Percentage of time when echo was detected in the microphone capture stream. Typically, values are low for headsets or handsets, and higher for speaker phones or stand-alone speakers. For devices that support on-board acoustic echo cancellation, high values indicate echo leak. For other devices, this metric should not be used to evaluate device quality.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d89f7-201"><strong>ечоперцентсенд</strong></span><span class="sxs-lookup"><span data-stu-id="d89f7-201"><strong>EchoPercentSend</strong></span></span></p></td>
<td><p><span data-ttu-id="d89f7-202">десятичное число (5; 2)</span><span class="sxs-lookup"><span data-stu-id="d89f7-202">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d89f7-203">Процент времени, в течение которого обнаружено Эхо-сообщение в отправленном потоке.</span><span class="sxs-lookup"><span data-stu-id="d89f7-203">Percentage of time when echo is detected in sent stream.</span></span> <span data-ttu-id="d89f7-204">Высокий процент эха в потоках отправки указывает на наличие утечки эха.</span><span class="sxs-lookup"><span data-stu-id="d89f7-204">High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d89f7-205"><strong>рксагксигналлевел</strong></span><span class="sxs-lookup"><span data-stu-id="d89f7-205"><strong>RxAGCSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="d89f7-206">целое</span><span class="sxs-lookup"><span data-stu-id="d89f7-206">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d89f7-207">Уровень сигнала на сервере обновлений от шлюза; Это относится только к серверу обновлений.</span><span class="sxs-lookup"><span data-stu-id="d89f7-207">Received signal level on the Mediation Server from the Gateway; this applies only to the Mediation Server.</span></span> <span data-ttu-id="d89f7-208">Единица измерения этой метрики — Дбов.</span><span class="sxs-lookup"><span data-stu-id="d89f7-208">The unit of this metric is dBoV.</span></span> <span data-ttu-id="d89f7-209">Для хорошего качества допустимый диапазон должен составлять от [-30 до-18] Дбов.</span><span class="sxs-lookup"><span data-stu-id="d89f7-209">For good quality, the acceptable range should be [-30 to -18] dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d89f7-210"><strong>рксагкноиселевел</strong></span><span class="sxs-lookup"><span data-stu-id="d89f7-210"><strong>RxAGCNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="d89f7-211">целое</span><span class="sxs-lookup"><span data-stu-id="d89f7-211">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d89f7-212">Уровень сигнала на сервере обновлений от шлюза.</span><span class="sxs-lookup"><span data-stu-id="d89f7-212">Received signal level on the Mediation Server from the Gateway.</span></span> <span data-ttu-id="d89f7-213">Это относится только к серверу обновлений.</span><span class="sxs-lookup"><span data-stu-id="d89f7-213">This applies only to the Mediation Server.</span></span> <span data-ttu-id="d89f7-214">Единица измерения этой метрики — Дбов.</span><span class="sxs-lookup"><span data-stu-id="d89f7-214">The unit of this metric is dBoV.</span></span> <span data-ttu-id="d89f7-215">Для хорошего качества допустимый диапазон должен быть меньше, чем-50 Дбов.</span><span class="sxs-lookup"><span data-stu-id="d89f7-215">For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d89f7-216"><strong>рксавгагкгаин</strong></span><span class="sxs-lookup"><span data-stu-id="d89f7-216"><strong>RxAvgAGCGain</strong></span></span></p></td>
<td><p><span data-ttu-id="d89f7-217">целое</span><span class="sxs-lookup"><span data-stu-id="d89f7-217">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d89f7-218">Автоматический контроль усиления (АГК) на стороне сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="d89f7-218">Automatic gain control (AGC) on the Mediation Server side.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d89f7-219"><strong>инитиалсигналлевелрмс</strong></span><span class="sxs-lookup"><span data-stu-id="d89f7-219"><strong>InitialSignalLevelRMS</strong></span></span></p></td>
<td><p><span data-ttu-id="d89f7-220">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="d89f7-220">float</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d89f7-221">Среднее значение среднего квадрата для входящего сигнала, которое составляет до первых 30 секунд звонка.</span><span class="sxs-lookup"><span data-stu-id="d89f7-221">The root mean square (RMS) of the incoming signal of up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d89f7-222"><strong>RecvSignalLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="d89f7-222"><strong>RecvSignalLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="d89f7-223">целое</span><span class="sxs-lookup"><span data-stu-id="d89f7-223">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d89f7-224">Уровень сигнала, полученный на канале 1.</span><span class="sxs-lookup"><span data-stu-id="d89f7-224">Signal level as received on channel 1.</span></span></p>
<p><span data-ttu-id="d89f7-225">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d89f7-225">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d89f7-226"><strong>RecvSignalLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="d89f7-226"><strong>RecvSignalLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="d89f7-227">целое</span><span class="sxs-lookup"><span data-stu-id="d89f7-227">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d89f7-228">Уровень сигнала, полученный на канале 2.</span><span class="sxs-lookup"><span data-stu-id="d89f7-228">Signal level as received on channel 2.</span></span></p>
<p><span data-ttu-id="d89f7-229">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d89f7-229">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d89f7-230"><strong>RecvNoiseLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="d89f7-230"><strong>RecvNoiseLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="d89f7-231">целое</span><span class="sxs-lookup"><span data-stu-id="d89f7-231">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d89f7-232">Уровень шума, полученный на канале 1.</span><span class="sxs-lookup"><span data-stu-id="d89f7-232">Noise level as received on channel 1.</span></span></p>
<p><span data-ttu-id="d89f7-233">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d89f7-233">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d89f7-234"><strong>RecvNoiseLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="d89f7-234"><strong>RecvNoiseLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="d89f7-235">целое</span><span class="sxs-lookup"><span data-stu-id="d89f7-235">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d89f7-236">Уровень шума, полученный на канале 2.</span><span class="sxs-lookup"><span data-stu-id="d89f7-236">Noise level as received on channel 2.</span></span></p>
<p><span data-ttu-id="d89f7-237">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d89f7-237">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d89f7-238"><strong>SendSignalLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="d89f7-238"><strong>SendSignalLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="d89f7-239">целое</span><span class="sxs-lookup"><span data-stu-id="d89f7-239">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d89f7-240">Уровень сигнала, отправленный на канале 1.</span><span class="sxs-lookup"><span data-stu-id="d89f7-240">Signal level as sent on channel 1.</span></span></p>
<p><span data-ttu-id="d89f7-241">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d89f7-241">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d89f7-242"><strong>SendSignalLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="d89f7-242"><strong>SendSignalLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="d89f7-243">целое</span><span class="sxs-lookup"><span data-stu-id="d89f7-243">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d89f7-244">Уровень сигнала, отправленный на канале 2.</span><span class="sxs-lookup"><span data-stu-id="d89f7-244">Signal level as sent on channel 2.</span></span></p>
<p><span data-ttu-id="d89f7-245">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d89f7-245">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d89f7-246"><strong>SendNoiseLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="d89f7-246"><strong>SendNoiseLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="d89f7-247">целое</span><span class="sxs-lookup"><span data-stu-id="d89f7-247">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d89f7-248">Уровень шума, отправленный на канале 1.</span><span class="sxs-lookup"><span data-stu-id="d89f7-248">Noise level as sent on channel 1.</span></span></p>
<p><span data-ttu-id="d89f7-249">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d89f7-249">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d89f7-250"><strong>SendNoiseLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="d89f7-250"><strong>SendNoiseLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="d89f7-251">целое</span><span class="sxs-lookup"><span data-stu-id="d89f7-251">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d89f7-252">Уровень шума, отправленный на канале 2.</span><span class="sxs-lookup"><span data-stu-id="d89f7-252">Noise level as sent on channel 2.</span></span></p>
<p><span data-ttu-id="d89f7-253">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d89f7-253">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

