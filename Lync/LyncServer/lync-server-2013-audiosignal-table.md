---
title: 'Lync Server 2013: таблица AudioSignal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: AudioSignal table
ms:assetid: 0013c8c6-cdf9-4d70-bc2a-cddd1560f66b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398064(v=OCS.15)
ms:contentKeyID: 48183217
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e6605a25191906660bbad11908f754a81360c893
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841903"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audiosignal-table-in-lync-server-2013"></a><span data-ttu-id="6af7d-102">Таблица AudioSignal в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6af7d-102">AudioSignal table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6af7d-103">_**Тема последнего изменения:** 2013-11-12_</span><span class="sxs-lookup"><span data-stu-id="6af7d-103">_**Topic Last Modified:** 2013-11-12_</span></span>

<span data-ttu-id="6af7d-104">Каждая запись представляет метрики звукового сигнала для одной конечной точки.</span><span class="sxs-lookup"><span data-stu-id="6af7d-104">Each record represents audio signal metrics for one endpoint.</span></span> <span data-ttu-id="6af7d-105">Обычно каждый звонок состоит из двух записей: одной из них, а другая — для вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="6af7d-105">Usually, each call has two records, one is for caller, and one is for callee.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6af7d-106"><strong>Столбец</strong></span><span class="sxs-lookup"><span data-stu-id="6af7d-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="6af7d-107"><strong>Тип данных</strong></span><span class="sxs-lookup"><span data-stu-id="6af7d-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="6af7d-108"><strong>Ключ/индекс</strong></span><span class="sxs-lookup"><span data-stu-id="6af7d-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="6af7d-109"><strong>Сведения</strong></span><span class="sxs-lookup"><span data-stu-id="6af7d-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6af7d-110"><strong>Конференцедатетиме</strong></span><span class="sxs-lookup"><span data-stu-id="6af7d-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="6af7d-111">datetime</span><span class="sxs-lookup"><span data-stu-id="6af7d-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="6af7d-112">Primary</span><span class="sxs-lookup"><span data-stu-id="6af7d-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="6af7d-113">На которую ссылается <a href="lync-server-2013-medialine-table.md">Таблица медиалине в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="6af7d-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6af7d-114"><strong>Сессионсек</strong></span><span class="sxs-lookup"><span data-stu-id="6af7d-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="6af7d-115">целое</span><span class="sxs-lookup"><span data-stu-id="6af7d-115">int</span></span></p></td>
<td><p><span data-ttu-id="6af7d-116">Primary</span><span class="sxs-lookup"><span data-stu-id="6af7d-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="6af7d-117">На которую ссылается <a href="lync-server-2013-medialine-table.md">Таблица медиалине в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="6af7d-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6af7d-118"><strong>Медиалинелабел</strong></span><span class="sxs-lookup"><span data-stu-id="6af7d-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="6af7d-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="6af7d-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="6af7d-120">Primary</span><span class="sxs-lookup"><span data-stu-id="6af7d-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="6af7d-121">На которую ссылается <a href="lync-server-2013-medialine-table.md">Таблица медиалине в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="6af7d-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6af7d-122"><strong>Фромкаллер</strong></span><span class="sxs-lookup"><span data-stu-id="6af7d-122"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="6af7d-123">бит</span><span class="sxs-lookup"><span data-stu-id="6af7d-123">bit</span></span></p></td>
<td><p><span data-ttu-id="6af7d-124">Primary</span><span class="sxs-lookup"><span data-stu-id="6af7d-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="6af7d-125">0: данные вызывающего абонента</span><span class="sxs-lookup"><span data-stu-id="6af7d-125">0: Callee’s data</span></span></p>
<p><span data-ttu-id="6af7d-126">1: данные вызывающего абонента</span><span class="sxs-lookup"><span data-stu-id="6af7d-126">1: Caller’s data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6af7d-127"><strong>Сендсигналлевел</strong></span><span class="sxs-lookup"><span data-stu-id="6af7d-127"><strong>SendSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="6af7d-128">целое</span><span class="sxs-lookup"><span data-stu-id="6af7d-128">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="6af7d-129">Обозначает уровень звукового сигнала после аналогового усиления контроля.</span><span class="sxs-lookup"><span data-stu-id="6af7d-129">Represents the Post-Analog Gain Control audio signal level.</span></span> <span data-ttu-id="6af7d-130">Единицей измерения для этой метрики является Дбмо.</span><span class="sxs-lookup"><span data-stu-id="6af7d-130">The unit for this metric is dBmo.</span></span> <span data-ttu-id="6af7d-131">Для приемлемого качества оно должно быть не менее 30 Дбмо.</span><span class="sxs-lookup"><span data-stu-id="6af7d-131">For acceptable quality, it should be at least 30 dBmo.</span></span> <span data-ttu-id="6af7d-132">Этот показатель не передается сервером Конференции и IP-телефонами по протоколу A/V.</span><span class="sxs-lookup"><span data-stu-id="6af7d-132">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6af7d-133"><strong>Реквсигналлевел</strong></span><span class="sxs-lookup"><span data-stu-id="6af7d-133"><strong>RecvSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="6af7d-134">целое</span><span class="sxs-lookup"><span data-stu-id="6af7d-134">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="6af7d-135">Смотрите Сендсигналлевел.</span><span class="sxs-lookup"><span data-stu-id="6af7d-135">See SendSignalLevel.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6af7d-136"><strong>Сендноиселевел</strong></span><span class="sxs-lookup"><span data-stu-id="6af7d-136"><strong>SendNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="6af7d-137">целое</span><span class="sxs-lookup"><span data-stu-id="6af7d-137">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="6af7d-138">Обозначает уровень звукового шума, поступающего после аналогового усиления.</span><span class="sxs-lookup"><span data-stu-id="6af7d-138">Represents the Post-Analog Gain Control audio noise level.</span></span> <span data-ttu-id="6af7d-139">Единицей измерения для этой метрики является Дбмо.</span><span class="sxs-lookup"><span data-stu-id="6af7d-139">The unit for this metric is dBmo.</span></span> <span data-ttu-id="6af7d-140">Для приемлемого качества оно должно быть менее 35 Дбмо.</span><span class="sxs-lookup"><span data-stu-id="6af7d-140">For acceptable quality, it should be less than 35 dBmo.</span></span> <span data-ttu-id="6af7d-141">Этот показатель не передается сервером Конференции и IP-телефонами по протоколу A/V.</span><span class="sxs-lookup"><span data-stu-id="6af7d-141">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6af7d-142"><strong>Реквноиселевел</strong></span><span class="sxs-lookup"><span data-stu-id="6af7d-142"><strong>RecvNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="6af7d-143">целое</span><span class="sxs-lookup"><span data-stu-id="6af7d-143">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="6af7d-144">Смотрите Сендноиселевел.</span><span class="sxs-lookup"><span data-stu-id="6af7d-144">See SendNoiseLevel.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6af7d-145"><strong>Ечоретурн</strong></span><span class="sxs-lookup"><span data-stu-id="6af7d-145"><strong>EchoReturn</strong></span></span></p></td>
<td><p><span data-ttu-id="6af7d-146">целое</span><span class="sxs-lookup"><span data-stu-id="6af7d-146">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="6af7d-147">Показатель возвращающего потери при возврате эха.</span><span class="sxs-lookup"><span data-stu-id="6af7d-147">Echo Return Loss Enhancement metric.</span></span> <span data-ttu-id="6af7d-148">Единицей измерения для этой метрики является dB.</span><span class="sxs-lookup"><span data-stu-id="6af7d-148">The unit for this metric is dB.</span></span> <span data-ttu-id="6af7d-149">Более низкие значения представляют менее эхо.</span><span class="sxs-lookup"><span data-stu-id="6af7d-149">Lower values represent less echo.</span></span> <span data-ttu-id="6af7d-150">Этот показатель не передается сервером Конференции и IP-телефонами по протоколу A/V.</span><span class="sxs-lookup"><span data-stu-id="6af7d-150">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6af7d-151"><strong>Аудиоспеакерглитчрате</strong></span><span class="sxs-lookup"><span data-stu-id="6af7d-151"><strong>AudioSpeakerGlitchRate</strong></span></span></p></td>
<td><p><span data-ttu-id="6af7d-152">целое</span><span class="sxs-lookup"><span data-stu-id="6af7d-152">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="6af7d-153">Среднее число сбоев в течение пяти минут для отрисовки динамик.</span><span class="sxs-lookup"><span data-stu-id="6af7d-153">Average glitches per five minutes for the loudspeaker rendering.</span></span> <span data-ttu-id="6af7d-154">Для хорошего качества это должно быть меньше, чем один за пять минут.</span><span class="sxs-lookup"><span data-stu-id="6af7d-154">For good quality, this should be less than one per five minutes.</span></span> <span data-ttu-id="6af7d-155">Не сообщается серверам конференц-связи, серверам или IP-телефонам.</span><span class="sxs-lookup"><span data-stu-id="6af7d-155">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6af7d-156"><strong>Аудиомикглитчрате</strong></span><span class="sxs-lookup"><span data-stu-id="6af7d-156"><strong>AudioMicGlitchRate</strong></span></span></p></td>
<td><p><span data-ttu-id="6af7d-157">целое</span><span class="sxs-lookup"><span data-stu-id="6af7d-157">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="6af7d-158">Среднее число сбоев в течение пяти минут для захвата микрофона.</span><span class="sxs-lookup"><span data-stu-id="6af7d-158">Average glitches per five minutes for the microphone capture.</span></span> <span data-ttu-id="6af7d-159">Для хорошего качества это должно быть менее чем на одну 5 минут.</span><span class="sxs-lookup"><span data-stu-id="6af7d-159">For good quality this should be less than one per five minutes.</span></span> <span data-ttu-id="6af7d-160">Не сообщается серверам конференц-связи, серверам или IP-телефонам.</span><span class="sxs-lookup"><span data-stu-id="6af7d-160">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6af7d-161"><strong>Аудиотиместампдрифтратемик</strong></span><span class="sxs-lookup"><span data-stu-id="6af7d-161"><strong>AudioTimestampDriftRateMic</strong></span></span></p></td>
<td><p><span data-ttu-id="6af7d-162">десятичное число (9, 2)</span><span class="sxs-lookup"><span data-stu-id="6af7d-162">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="6af7d-163">Частота расхождения синхронизирующих сигналов для микрофона, относящихся к тактовой частоте процессора.</span><span class="sxs-lookup"><span data-stu-id="6af7d-163">Microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6af7d-164"><strong>Аудиотиместампдрифтратеспк</strong></span><span class="sxs-lookup"><span data-stu-id="6af7d-164"><strong>AudioTimestampDriftRateSpk</strong></span></span></p></td>
<td><p><span data-ttu-id="6af7d-165">десятичное число (9, 2)</span><span class="sxs-lookup"><span data-stu-id="6af7d-165">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="6af7d-166">Частота расхождения синхронизирующих импульсов устройства для динамиков относительно часов процессора.</span><span class="sxs-lookup"><span data-stu-id="6af7d-166">Speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6af7d-167"><strong>Аудиотиместамперрормикмс</strong></span><span class="sxs-lookup"><span data-stu-id="6af7d-167"><strong>AudioTimestampErrorMicMs</strong></span></span></p></td>
<td><p><span data-ttu-id="6af7d-168">десятичное число (9, 2)</span><span class="sxs-lookup"><span data-stu-id="6af7d-168">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="6af7d-169">Частота расхождения синхронизирующих импульсов устройства для динамиков относительно часов процессора.</span><span class="sxs-lookup"><span data-stu-id="6af7d-169">Speaker device clock drift rate, relative to CPU clock.</span></span></p>
<p><span data-ttu-id="6af7d-170">Средняя пометка времени потока захвата микрофона в миллисекундах за последние 20 секунд звонка.</span><span class="sxs-lookup"><span data-stu-id="6af7d-170">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6af7d-171"><strong>Аудиотиместамперрорспкмс</strong></span><span class="sxs-lookup"><span data-stu-id="6af7d-171"><strong>AudioTimestampErrorSpkMs</strong></span></span></p></td>
<td><p><span data-ttu-id="6af7d-172">десятичное число (9, 2)</span><span class="sxs-lookup"><span data-stu-id="6af7d-172">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="6af7d-173">Средняя отметка времени линейного потока обработки динамиков в миллисекундах за последние 20 секунд вызова.</span><span class="sxs-lookup"><span data-stu-id="6af7d-173">Average speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6af7d-174"><strong>Всентрикаусес</strong></span><span class="sxs-lookup"><span data-stu-id="6af7d-174"><strong>VsEntryCauses</strong></span></span></p></td>
<td><p><span data-ttu-id="6af7d-175">smallint</span><span class="sxs-lookup"><span data-stu-id="6af7d-175">smallint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="6af7d-176">Голосовая связь — это режим двусторонней печати с ограниченными возможностями перерывов.</span><span class="sxs-lookup"><span data-stu-id="6af7d-176">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="6af7d-177">Причины для записи голосового переключателя:</span><span class="sxs-lookup"><span data-stu-id="6af7d-177">Causes of voice switch entry:</span></span></p>
<p><span data-ttu-id="6af7d-178">ЕНТЕР_ВС_БАДТС 0x01</span><span class="sxs-lookup"><span data-stu-id="6af7d-178">ENTER_VS_BADTS 0x01</span></span></p>
<p><span data-ttu-id="6af7d-179">ЕНТЕР_ВС_ЕЧО 0x02</span><span class="sxs-lookup"><span data-stu-id="6af7d-179">ENTER_VS_ECHO 0x02</span></span></p>
<p><span data-ttu-id="6af7d-180">ЕНТЕР_ВС_ФОРЦЕОРКОНВЕРЖЕНЦЕ 0x04</span><span class="sxs-lookup"><span data-stu-id="6af7d-180">ENTER_VS_FORCEORCONVERGENCE 0x04</span></span></p>
<p><span data-ttu-id="6af7d-181">ЕНТЕР_ВС_ДНЛП 0x08</span><span class="sxs-lookup"><span data-stu-id="6af7d-181">ENTER_VS_DNLP 0x08</span></span></p>
<p><span data-ttu-id="6af7d-182">Причина может быть сочетанием отдельных причин.</span><span class="sxs-lookup"><span data-stu-id="6af7d-182">The cause can be a combination of those individual causes.</span></span> <span data-ttu-id="6af7d-183">ЕНТЕР_ВС_ФОРЦЕОРКОНВЕРЖЕНЦЕ может быть включена только в RegKey для целей тестирования.</span><span class="sxs-lookup"><span data-stu-id="6af7d-183">ENTER_VS_FORCEORCONVERGENCE can only be enabled by regkey for test purpose.</span></span></p>
<p><span data-ttu-id="6af7d-184">Тип данных этого столбца изменен в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6af7d-184">The data type for this column was changed in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6af7d-185"><strong>Ечоевенткаусес</strong></span><span class="sxs-lookup"><span data-stu-id="6af7d-185"><strong>EchoEventCauses</strong></span></span></p></td>
<td><p><span data-ttu-id="6af7d-186">tinyint</span><span class="sxs-lookup"><span data-stu-id="6af7d-186">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="6af7d-187">Причины возникновения события echo:</span><span class="sxs-lookup"><span data-stu-id="6af7d-187">Causes of an echo event:</span></span></p>
<p><span data-ttu-id="6af7d-188">ЕЧО_ЕВЕНТ_БАД_ТИМЕСТАМП 0x01</span><span class="sxs-lookup"><span data-stu-id="6af7d-188">ECHO_EVENT_BAD_TIMESTAMP 0x01</span></span></p>
<p><span data-ttu-id="6af7d-189">ЕЧО_ЕВЕНТ_ПОСТАЕК_ЕЧО 0x02</span><span class="sxs-lookup"><span data-stu-id="6af7d-189">ECHO_EVENT_POSTAEC_ECHO 0x02</span></span></p>
<p><span data-ttu-id="6af7d-190">ЕЧО_ЕВЕНТ_АНЛП 0x04</span><span class="sxs-lookup"><span data-stu-id="6af7d-190">ECHO_EVENT_ANLP 0x04</span></span></p>
<p><span data-ttu-id="6af7d-191">ЕЧО_ЕВЕНТ_ДНЛП 0x08</span><span class="sxs-lookup"><span data-stu-id="6af7d-191">ECHO_EVENT_DNLP 0x08</span></span></p>
<p><span data-ttu-id="6af7d-192">ЕЧО_ЕВЕНТ_МИК_КЛИППИНГ 0x10</span><span class="sxs-lookup"><span data-stu-id="6af7d-192">ECHO_EVENT_MIC_CLIPPING 0x10</span></span></p>
<p><span data-ttu-id="6af7d-193">ЕЧО_ЕВЕНТ_БАД_СТАТЕ 0x20</span><span class="sxs-lookup"><span data-stu-id="6af7d-193">ECHO_EVENT_BAD_STATE 0x20</span></span></p>
<p><span data-ttu-id="6af7d-194">Причина может быть сочетанием отдельных причин.</span><span class="sxs-lookup"><span data-stu-id="6af7d-194">The cause can be a combination of those individual causes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6af7d-195"><strong>ЕчоперцентмиЦин</strong></span><span class="sxs-lookup"><span data-stu-id="6af7d-195"><strong>EchoPercentMicIn</strong></span></span></p></td>
<td><p><span data-ttu-id="6af7d-196">десятичное число (5; 2)</span><span class="sxs-lookup"><span data-stu-id="6af7d-196">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="6af7d-p109">Процент времени, когда в потоке захвата микрофоном обнаруживался эхосигнал. Обычно низкие значения отображаются для гарнитур или телефонных трубок, а высокие значения – для телефонных или автономных динамиков. Для устройств, которые поддерживают встроенную возможность подавления акустического эхосигнала, высокие значения указывают утечку эхосигнала. Для других устройств эти единицы измерения не должны использоваться для оценки качества устройства.</span><span class="sxs-lookup"><span data-stu-id="6af7d-p109">Percentage of time when echo was detected in the microphone capture stream. Typically, values are low for headsets or handsets, and higher for speaker phones or stand-alone speakers. For devices that support on-board acoustic echo cancellation, high values indicate echo leak. For other devices, this metric should not be used to evaluate device quality.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6af7d-201"><strong>Ечоперцентсенд</strong></span><span class="sxs-lookup"><span data-stu-id="6af7d-201"><strong>EchoPercentSend</strong></span></span></p></td>
<td><p><span data-ttu-id="6af7d-202">десятичное число (5; 2)</span><span class="sxs-lookup"><span data-stu-id="6af7d-202">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6af7d-203">Процент времени, в течение которого обнаружено Эхо-сообщение в отправленном потоке.</span><span class="sxs-lookup"><span data-stu-id="6af7d-203">Percentage of time when echo is detected in sent stream.</span></span> <span data-ttu-id="6af7d-204">Высокий процент эха в потоках отправки указывает на наличие утечки эха.</span><span class="sxs-lookup"><span data-stu-id="6af7d-204">High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6af7d-205"><strong>Рксагксигналлевел</strong></span><span class="sxs-lookup"><span data-stu-id="6af7d-205"><strong>RxAGCSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="6af7d-206">целое</span><span class="sxs-lookup"><span data-stu-id="6af7d-206">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="6af7d-207">Уровень сигнала на сервере обновлений от шлюза; Это относится только к серверу обновлений.</span><span class="sxs-lookup"><span data-stu-id="6af7d-207">Received signal level on the Mediation Server from the Gateway; this applies only to the Mediation Server.</span></span> <span data-ttu-id="6af7d-208">Единица измерения этой метрики — Дбов.</span><span class="sxs-lookup"><span data-stu-id="6af7d-208">The unit of this metric is dBoV.</span></span> <span data-ttu-id="6af7d-209">Для хорошего качества допустимый диапазон должен составлять от [-30 до-18] Дбов.</span><span class="sxs-lookup"><span data-stu-id="6af7d-209">For good quality, the acceptable range should be [-30 to -18] dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6af7d-210"><strong>Рксагкноиселевел</strong></span><span class="sxs-lookup"><span data-stu-id="6af7d-210"><strong>RxAGCNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="6af7d-211">целое</span><span class="sxs-lookup"><span data-stu-id="6af7d-211">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="6af7d-212">Уровень сигнала на сервере обновлений от шлюза.</span><span class="sxs-lookup"><span data-stu-id="6af7d-212">Received signal level on the Mediation Server from the Gateway.</span></span> <span data-ttu-id="6af7d-213">Это относится только к серверу обновлений.</span><span class="sxs-lookup"><span data-stu-id="6af7d-213">This applies only to the Mediation Server.</span></span> <span data-ttu-id="6af7d-214">Единица измерения этой метрики — Дбов.</span><span class="sxs-lookup"><span data-stu-id="6af7d-214">The unit of this metric is dBoV.</span></span> <span data-ttu-id="6af7d-215">Для хорошего качества допустимый диапазон должен быть меньше, чем-50 Дбов.</span><span class="sxs-lookup"><span data-stu-id="6af7d-215">For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6af7d-216"><strong>Рксавгагкгаин</strong></span><span class="sxs-lookup"><span data-stu-id="6af7d-216"><strong>RxAvgAGCGain</strong></span></span></p></td>
<td><p><span data-ttu-id="6af7d-217">целое</span><span class="sxs-lookup"><span data-stu-id="6af7d-217">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="6af7d-218">Автоматический контроль усиления (АГК) на стороне сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="6af7d-218">Automatic gain control (AGC) on the Mediation Server side.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6af7d-219"><strong>Инитиалсигналлевелрмс</strong></span><span class="sxs-lookup"><span data-stu-id="6af7d-219"><strong>InitialSignalLevelRMS</strong></span></span></p></td>
<td><p><span data-ttu-id="6af7d-220">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="6af7d-220">float</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="6af7d-221">Среднее значение среднего квадрата для входящего сигнала, которое составляет до первых 30 секунд звонка.</span><span class="sxs-lookup"><span data-stu-id="6af7d-221">The root mean square (RMS) of the incoming signal of up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6af7d-222"><strong>RecvSignalLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="6af7d-222"><strong>RecvSignalLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="6af7d-223">целое</span><span class="sxs-lookup"><span data-stu-id="6af7d-223">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6af7d-224">Уровень сигнала, полученный на канале 1.</span><span class="sxs-lookup"><span data-stu-id="6af7d-224">Signal level as received on channel 1.</span></span></p>
<p><span data-ttu-id="6af7d-225">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6af7d-225">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6af7d-226"><strong>RecvSignalLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="6af7d-226"><strong>RecvSignalLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="6af7d-227">целое</span><span class="sxs-lookup"><span data-stu-id="6af7d-227">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6af7d-228">Уровень сигнала, полученный на канале 2.</span><span class="sxs-lookup"><span data-stu-id="6af7d-228">Signal level as received on channel 2.</span></span></p>
<p><span data-ttu-id="6af7d-229">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6af7d-229">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6af7d-230"><strong>RecvNoiseLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="6af7d-230"><strong>RecvNoiseLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="6af7d-231">целое</span><span class="sxs-lookup"><span data-stu-id="6af7d-231">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6af7d-232">Уровень шума, полученный на канале 1.</span><span class="sxs-lookup"><span data-stu-id="6af7d-232">Noise level as received on channel 1.</span></span></p>
<p><span data-ttu-id="6af7d-233">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6af7d-233">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6af7d-234"><strong>RecvNoiseLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="6af7d-234"><strong>RecvNoiseLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="6af7d-235">целое</span><span class="sxs-lookup"><span data-stu-id="6af7d-235">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6af7d-236">Уровень шума, полученный на канале 2.</span><span class="sxs-lookup"><span data-stu-id="6af7d-236">Noise level as received on channel 2.</span></span></p>
<p><span data-ttu-id="6af7d-237">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6af7d-237">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6af7d-238"><strong>SendSignalLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="6af7d-238"><strong>SendSignalLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="6af7d-239">целое</span><span class="sxs-lookup"><span data-stu-id="6af7d-239">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6af7d-240">Уровень сигнала, отправленный на канале 1.</span><span class="sxs-lookup"><span data-stu-id="6af7d-240">Signal level as sent on channel 1.</span></span></p>
<p><span data-ttu-id="6af7d-241">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6af7d-241">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6af7d-242"><strong>SendSignalLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="6af7d-242"><strong>SendSignalLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="6af7d-243">целое</span><span class="sxs-lookup"><span data-stu-id="6af7d-243">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6af7d-244">Уровень сигнала, отправленный на канале 2.</span><span class="sxs-lookup"><span data-stu-id="6af7d-244">Signal level as sent on channel 2.</span></span></p>
<p><span data-ttu-id="6af7d-245">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6af7d-245">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6af7d-246"><strong>SendNoiseLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="6af7d-246"><strong>SendNoiseLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="6af7d-247">целое</span><span class="sxs-lookup"><span data-stu-id="6af7d-247">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6af7d-248">Уровень шума, отправленный на канале 1.</span><span class="sxs-lookup"><span data-stu-id="6af7d-248">Noise level as sent on channel 1.</span></span></p>
<p><span data-ttu-id="6af7d-249">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6af7d-249">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6af7d-250"><strong>SendNoiseLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="6af7d-250"><strong>SendNoiseLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="6af7d-251">целое</span><span class="sxs-lookup"><span data-stu-id="6af7d-251">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6af7d-252">Уровень шума, отправленный на канале 2.</span><span class="sxs-lookup"><span data-stu-id="6af7d-252">Noise level as sent on channel 2.</span></span></p>
<p><span data-ttu-id="6af7d-253">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6af7d-253">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

