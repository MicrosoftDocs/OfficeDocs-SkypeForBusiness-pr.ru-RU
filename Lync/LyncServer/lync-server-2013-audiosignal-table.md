---
title: 'Lync Server 2013: таблица таблица audiosignal'
description: 'Lync Server 2013: таблица таблица audiosignal.'
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
ms.openlocfilehash: 82f3b3119eaccfe56c4706cff07469bc3434461f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568765"
---
# <a name="audiosignal-table-in-lync-server-2013"></a><span data-ttu-id="36fd1-103">Таблица Таблица audiosignal в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="36fd1-103">AudioSignal table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="36fd1-104">_**Последнее изменение темы:** 2013-11-12_</span><span class="sxs-lookup"><span data-stu-id="36fd1-104">_**Topic Last Modified:** 2013-11-12_</span></span>

<span data-ttu-id="36fd1-105">Каждая запись представляет метрики звукового сигнала для одной конечной точки.</span><span class="sxs-lookup"><span data-stu-id="36fd1-105">Each record represents audio signal metrics for one endpoint.</span></span> <span data-ttu-id="36fd1-106">Обычно каждый вызов состоит из двух записей, один из которых является абонентом, а другой — для вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="36fd1-106">Usually, each call has two records, one is for caller, and one is for callee.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="36fd1-107"><strong>Column</strong></span><span class="sxs-lookup"><span data-stu-id="36fd1-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="36fd1-108"><strong>Тип данных</strong></span><span class="sxs-lookup"><span data-stu-id="36fd1-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="36fd1-109"><strong>Ключ или индекс</strong></span><span class="sxs-lookup"><span data-stu-id="36fd1-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="36fd1-110"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="36fd1-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="36fd1-111"><strong>конференцедатетиме</strong></span><span class="sxs-lookup"><span data-stu-id="36fd1-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="36fd1-112">datetime</span><span class="sxs-lookup"><span data-stu-id="36fd1-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="36fd1-113">Primary</span><span class="sxs-lookup"><span data-stu-id="36fd1-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="36fd1-114">Ссылка из <a href="lync-server-2013-medialine-table.md">таблицы MediaLine в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="36fd1-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36fd1-115"><strong>сессионсек</strong></span><span class="sxs-lookup"><span data-stu-id="36fd1-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="36fd1-116">int</span><span class="sxs-lookup"><span data-stu-id="36fd1-116">int</span></span></p></td>
<td><p><span data-ttu-id="36fd1-117">Primary</span><span class="sxs-lookup"><span data-stu-id="36fd1-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="36fd1-118">Ссылка из <a href="lync-server-2013-medialine-table.md">таблицы MediaLine в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="36fd1-118">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36fd1-119"><strong>медиалинелабел</strong></span><span class="sxs-lookup"><span data-stu-id="36fd1-119"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="36fd1-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="36fd1-120">tinyint</span></span></p></td>
<td><p><span data-ttu-id="36fd1-121">Primary</span><span class="sxs-lookup"><span data-stu-id="36fd1-121">Primary</span></span></p></td>
<td><p><span data-ttu-id="36fd1-122">Ссылка из <a href="lync-server-2013-medialine-table.md">таблицы MediaLine в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="36fd1-122">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36fd1-123"><strong>фромкаллер</strong></span><span class="sxs-lookup"><span data-stu-id="36fd1-123"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="36fd1-124">Битовая</span><span class="sxs-lookup"><span data-stu-id="36fd1-124">bit</span></span></p></td>
<td><p><span data-ttu-id="36fd1-125">Primary</span><span class="sxs-lookup"><span data-stu-id="36fd1-125">Primary</span></span></p></td>
<td><p><span data-ttu-id="36fd1-126">0: данные вызываемого абонента</span><span class="sxs-lookup"><span data-stu-id="36fd1-126">0: Callee’s data</span></span></p>
<p><span data-ttu-id="36fd1-127">1: данные вызывающего абонента</span><span class="sxs-lookup"><span data-stu-id="36fd1-127">1: Caller’s data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36fd1-128"><strong>сендсигналлевел</strong></span><span class="sxs-lookup"><span data-stu-id="36fd1-128"><strong>SendSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="36fd1-129">int</span><span class="sxs-lookup"><span data-stu-id="36fd1-129">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="36fd1-130">Представляет уровень звукового сигнала, поступающего после аналогового усиления контроля.</span><span class="sxs-lookup"><span data-stu-id="36fd1-130">Represents the Post-Analog Gain Control audio signal level.</span></span> <span data-ttu-id="36fd1-131">Единица измерения для этого показателя — дБмо.</span><span class="sxs-lookup"><span data-stu-id="36fd1-131">The unit for this metric is dBmo.</span></span> <span data-ttu-id="36fd1-132">Для приемлемого качества значение должно быть не менее 30 дБмо.</span><span class="sxs-lookup"><span data-stu-id="36fd1-132">For acceptable quality, it should be at least 30 dBmo.</span></span> <span data-ttu-id="36fd1-133">Этот показатель не сообщается сервером аудио- и видеоконференций и IP-телефонами.</span><span class="sxs-lookup"><span data-stu-id="36fd1-133">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36fd1-134"><strong>реквсигналлевел</strong></span><span class="sxs-lookup"><span data-stu-id="36fd1-134"><strong>RecvSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="36fd1-135">int</span><span class="sxs-lookup"><span data-stu-id="36fd1-135">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="36fd1-136">Обратитесь к разделу Сендсигналлевел.</span><span class="sxs-lookup"><span data-stu-id="36fd1-136">See SendSignalLevel.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36fd1-137"><strong>сендноиселевел</strong></span><span class="sxs-lookup"><span data-stu-id="36fd1-137"><strong>SendNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="36fd1-138">int</span><span class="sxs-lookup"><span data-stu-id="36fd1-138">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="36fd1-139">Представляет уровень шума управления последующей аналоговой усилением.</span><span class="sxs-lookup"><span data-stu-id="36fd1-139">Represents the Post-Analog Gain Control audio noise level.</span></span> <span data-ttu-id="36fd1-140">Единица измерения для этого показателя — дБмо.</span><span class="sxs-lookup"><span data-stu-id="36fd1-140">The unit for this metric is dBmo.</span></span> <span data-ttu-id="36fd1-141">Для приемлемого качества значение должно быть менее 35 дБмо.</span><span class="sxs-lookup"><span data-stu-id="36fd1-141">For acceptable quality, it should be less than 35 dBmo.</span></span> <span data-ttu-id="36fd1-142">Этот показатель не сообщается сервером аудио- и видеоконференций и IP-телефонами.</span><span class="sxs-lookup"><span data-stu-id="36fd1-142">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36fd1-143"><strong>реквноиселевел</strong></span><span class="sxs-lookup"><span data-stu-id="36fd1-143"><strong>RecvNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="36fd1-144">int</span><span class="sxs-lookup"><span data-stu-id="36fd1-144">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="36fd1-145">Обратитесь к разделу Сендноиселевел.</span><span class="sxs-lookup"><span data-stu-id="36fd1-145">See SendNoiseLevel.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36fd1-146"><strong>ечоретурн</strong></span><span class="sxs-lookup"><span data-stu-id="36fd1-146"><strong>EchoReturn</strong></span></span></p></td>
<td><p><span data-ttu-id="36fd1-147">int</span><span class="sxs-lookup"><span data-stu-id="36fd1-147">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="36fd1-148">Метрика улучшения возврата эха.</span><span class="sxs-lookup"><span data-stu-id="36fd1-148">Echo Return Loss Enhancement metric.</span></span> <span data-ttu-id="36fd1-149">Единица измерения для этого показателя — дБ.</span><span class="sxs-lookup"><span data-stu-id="36fd1-149">The unit for this metric is dB.</span></span> <span data-ttu-id="36fd1-150">Чем ниже значение, тем меньше эхосигнал.</span><span class="sxs-lookup"><span data-stu-id="36fd1-150">Lower values represent less echo.</span></span> <span data-ttu-id="36fd1-151">Этот показатель не сообщается сервером аудио- и видеоконференций и IP-телефонами.</span><span class="sxs-lookup"><span data-stu-id="36fd1-151">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36fd1-152"><strong>аудиоспеакерглитчрате</strong></span><span class="sxs-lookup"><span data-stu-id="36fd1-152"><strong>AudioSpeakerGlitchRate</strong></span></span></p></td>
<td><p><span data-ttu-id="36fd1-153">int</span><span class="sxs-lookup"><span data-stu-id="36fd1-153">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="36fd1-154">Среднее число сбоев для отображения лаудспеакер в пять минут.</span><span class="sxs-lookup"><span data-stu-id="36fd1-154">Average glitches per five minutes for the loudspeaker rendering.</span></span> <span data-ttu-id="36fd1-155">Для хорошего качества должно быть не более одного сбоя в пять минут.</span><span class="sxs-lookup"><span data-stu-id="36fd1-155">For good quality, this should be less than one per five minutes.</span></span> <span data-ttu-id="36fd1-156">Этот показатель не сообщается серверами аудио- и видеоконференций, серверами-посредниками и IP-телефонами.</span><span class="sxs-lookup"><span data-stu-id="36fd1-156">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36fd1-157"><strong>аудиомикглитчрате</strong></span><span class="sxs-lookup"><span data-stu-id="36fd1-157"><strong>AudioMicGlitchRate</strong></span></span></p></td>
<td><p><span data-ttu-id="36fd1-158">int</span><span class="sxs-lookup"><span data-stu-id="36fd1-158">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="36fd1-159">Среднее число сбоев для записи микрофона в течение пяти минут.</span><span class="sxs-lookup"><span data-stu-id="36fd1-159">Average glitches per five minutes for the microphone capture.</span></span> <span data-ttu-id="36fd1-160">Для хорошего качества должно быть не более одного сбоя в пять минут.</span><span class="sxs-lookup"><span data-stu-id="36fd1-160">For good quality this should be less than one per five minutes.</span></span> <span data-ttu-id="36fd1-161">Этот показатель не сообщается серверами аудио- и видеоконференций, серверами-посредниками и IP-телефонами.</span><span class="sxs-lookup"><span data-stu-id="36fd1-161">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36fd1-162"><strong>аудиотиместампдрифтратемик</strong></span><span class="sxs-lookup"><span data-stu-id="36fd1-162"><strong>AudioTimestampDriftRateMic</strong></span></span></p></td>
<td><p><span data-ttu-id="36fd1-163">десятичное число (9, 2)</span><span class="sxs-lookup"><span data-stu-id="36fd1-163">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="36fd1-164">Частота расхождения сигналов для микрофона, относящихся к часам процессора.</span><span class="sxs-lookup"><span data-stu-id="36fd1-164">Microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36fd1-165"><strong>аудиотиместампдрифтратеспк</strong></span><span class="sxs-lookup"><span data-stu-id="36fd1-165"><strong>AudioTimestampDriftRateSpk</strong></span></span></p></td>
<td><p><span data-ttu-id="36fd1-166">десятичное число (9, 2)</span><span class="sxs-lookup"><span data-stu-id="36fd1-166">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="36fd1-167">Частота расхождения сигналов для динамиков, относящихся к часам процессора.</span><span class="sxs-lookup"><span data-stu-id="36fd1-167">Speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36fd1-168"><strong>аудиотиместамперрормикмс</strong></span><span class="sxs-lookup"><span data-stu-id="36fd1-168"><strong>AudioTimestampErrorMicMs</strong></span></span></p></td>
<td><p><span data-ttu-id="36fd1-169">десятичное число (9, 2)</span><span class="sxs-lookup"><span data-stu-id="36fd1-169">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="36fd1-170">Частота расхождения сигналов для динамиков, относящихся к часам процессора.</span><span class="sxs-lookup"><span data-stu-id="36fd1-170">Speaker device clock drift rate, relative to CPU clock.</span></span></p>
<p><span data-ttu-id="36fd1-171">Средняя ошибка метки времени для потока захвата микрофоном, в миллисекундах, в последние 20 секунд вызова.</span><span class="sxs-lookup"><span data-stu-id="36fd1-171">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36fd1-172"><strong>аудиотиместамперрорспкмс</strong></span><span class="sxs-lookup"><span data-stu-id="36fd1-172"><strong>AudioTimestampErrorSpkMs</strong></span></span></p></td>
<td><p><span data-ttu-id="36fd1-173">десятичное число (9, 2)</span><span class="sxs-lookup"><span data-stu-id="36fd1-173">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="36fd1-174">Средняя ошибка метки времени потока отображения динамиков, в миллисекундах, в последние 20 секунд вызова.</span><span class="sxs-lookup"><span data-stu-id="36fd1-174">Average speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36fd1-175"><strong>всентрикаусес</strong></span><span class="sxs-lookup"><span data-stu-id="36fd1-175"><strong>VsEntryCauses</strong></span></span></p></td>
<td><p><span data-ttu-id="36fd1-176">smallint</span><span class="sxs-lookup"><span data-stu-id="36fd1-176">smallint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="36fd1-177">Речевой коммутатор — это полудуплексный режим с уменьшенной возможностью прерывания.</span><span class="sxs-lookup"><span data-stu-id="36fd1-177">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="36fd1-178">Причины записи голосового переключателя:</span><span class="sxs-lookup"><span data-stu-id="36fd1-178">Causes of voice switch entry:</span></span></p>
<p><span data-ttu-id="36fd1-179">ENTER_VS_BADTS 0x01</span><span class="sxs-lookup"><span data-stu-id="36fd1-179">ENTER_VS_BADTS 0x01</span></span></p>
<p><span data-ttu-id="36fd1-180">ENTER_VS_ECHO 0x02</span><span class="sxs-lookup"><span data-stu-id="36fd1-180">ENTER_VS_ECHO 0x02</span></span></p>
<p><span data-ttu-id="36fd1-181">ENTER_VS_FORCEORCONVERGENCE 0x04</span><span class="sxs-lookup"><span data-stu-id="36fd1-181">ENTER_VS_FORCEORCONVERGENCE 0x04</span></span></p>
<p><span data-ttu-id="36fd1-182">ENTER_VS_DNLP 0x08</span><span class="sxs-lookup"><span data-stu-id="36fd1-182">ENTER_VS_DNLP 0x08</span></span></p>
<p><span data-ttu-id="36fd1-183">Причина может быть сочетанием отдельных причин.</span><span class="sxs-lookup"><span data-stu-id="36fd1-183">The cause can be a combination of those individual causes.</span></span> <span data-ttu-id="36fd1-184">В этом случае ENTER_VS_FORCEORCONVERGENCE может быть включен только в RegKey для тестового назначения.</span><span class="sxs-lookup"><span data-stu-id="36fd1-184">ENTER_VS_FORCEORCONVERGENCE can only be enabled by regkey for test purpose.</span></span></p>
<p><span data-ttu-id="36fd1-185">Тип данных для этого столбца был изменен в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="36fd1-185">The data type for this column was changed in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36fd1-186"><strong>ечоевенткаусес</strong></span><span class="sxs-lookup"><span data-stu-id="36fd1-186"><strong>EchoEventCauses</strong></span></span></p></td>
<td><p><span data-ttu-id="36fd1-187">tinyint</span><span class="sxs-lookup"><span data-stu-id="36fd1-187">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="36fd1-188">Причины возникновения события echo:</span><span class="sxs-lookup"><span data-stu-id="36fd1-188">Causes of an echo event:</span></span></p>
<p><span data-ttu-id="36fd1-189">ECHO_EVENT_BAD_TIMESTAMP 0x01</span><span class="sxs-lookup"><span data-stu-id="36fd1-189">ECHO_EVENT_BAD_TIMESTAMP 0x01</span></span></p>
<p><span data-ttu-id="36fd1-190">ECHO_EVENT_POSTAEC_ECHO 0x02</span><span class="sxs-lookup"><span data-stu-id="36fd1-190">ECHO_EVENT_POSTAEC_ECHO 0x02</span></span></p>
<p><span data-ttu-id="36fd1-191">ECHO_EVENT_ANLP 0x04</span><span class="sxs-lookup"><span data-stu-id="36fd1-191">ECHO_EVENT_ANLP 0x04</span></span></p>
<p><span data-ttu-id="36fd1-192">ECHO_EVENT_DNLP 0x08</span><span class="sxs-lookup"><span data-stu-id="36fd1-192">ECHO_EVENT_DNLP 0x08</span></span></p>
<p><span data-ttu-id="36fd1-193">ECHO_EVENT_MIC_CLIPPING 0x10</span><span class="sxs-lookup"><span data-stu-id="36fd1-193">ECHO_EVENT_MIC_CLIPPING 0x10</span></span></p>
<p><span data-ttu-id="36fd1-194">ECHO_EVENT_BAD_STATE 0x20</span><span class="sxs-lookup"><span data-stu-id="36fd1-194">ECHO_EVENT_BAD_STATE 0x20</span></span></p>
<p><span data-ttu-id="36fd1-195">Причина может быть сочетанием отдельных причин.</span><span class="sxs-lookup"><span data-stu-id="36fd1-195">The cause can be a combination of those individual causes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36fd1-196"><strong>ечоперцентмиЦин</strong></span><span class="sxs-lookup"><span data-stu-id="36fd1-196"><strong>EchoPercentMicIn</strong></span></span></p></td>
<td><p><span data-ttu-id="36fd1-197">десятичное число (5, 2)</span><span class="sxs-lookup"><span data-stu-id="36fd1-197">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="36fd1-198">Процент времени, когда в потоке записи микрофона обнаружено эхо-сообщений.</span><span class="sxs-lookup"><span data-stu-id="36fd1-198">Percentage of time when echo was detected in the microphone capture stream.</span></span> <span data-ttu-id="36fd1-199">Как правило, низкие значения для гарнитур и телефонов, а также для телефонов динамиков или отдельных динамиков.</span><span class="sxs-lookup"><span data-stu-id="36fd1-199">Typically, values are low for headsets or handsets, and higher for speaker phones or stand-alone speakers.</span></span> <span data-ttu-id="36fd1-200">Для устройств, поддерживающих встроенную отдавление акустического эха, высокие значения указывают на наличие потерь эха.</span><span class="sxs-lookup"><span data-stu-id="36fd1-200">For devices that support on-board acoustic echo cancellation, high values indicate echo leak.</span></span> <span data-ttu-id="36fd1-201">Для других устройств эта метрика не должна использоваться для оценки качества устройства.</span><span class="sxs-lookup"><span data-stu-id="36fd1-201">For other devices, this metric should not be used to evaluate device quality.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36fd1-202"><strong>ечоперцентсенд</strong></span><span class="sxs-lookup"><span data-stu-id="36fd1-202"><strong>EchoPercentSend</strong></span></span></p></td>
<td><p><span data-ttu-id="36fd1-203">десятичное число (5, 2)</span><span class="sxs-lookup"><span data-stu-id="36fd1-203">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="36fd1-204">Процент времени, в течение которого обнаружено Эхо-сообщения в отправленном потоке.</span><span class="sxs-lookup"><span data-stu-id="36fd1-204">Percentage of time when echo is detected in sent stream.</span></span> <span data-ttu-id="36fd1-205">Высокое значение в отправленных потоках указывает на утечку эхосигнала.</span><span class="sxs-lookup"><span data-stu-id="36fd1-205">High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36fd1-206"><strong>рксагксигналлевел</strong></span><span class="sxs-lookup"><span data-stu-id="36fd1-206"><strong>RxAGCSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="36fd1-207">int</span><span class="sxs-lookup"><span data-stu-id="36fd1-207">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="36fd1-208">Уровень полученного сигнала на сервере-посреднике от шлюза; Это относится только к серверу-посреднику.</span><span class="sxs-lookup"><span data-stu-id="36fd1-208">Received signal level on the Mediation Server from the Gateway; this applies only to the Mediation Server.</span></span> <span data-ttu-id="36fd1-209">Единица измерения — dBoV.</span><span class="sxs-lookup"><span data-stu-id="36fd1-209">The unit of this metric is dBoV.</span></span> <span data-ttu-id="36fd1-210">Приемлемый диапазон для хорошего качества — от -30 до -18 dBoV.</span><span class="sxs-lookup"><span data-stu-id="36fd1-210">For good quality, the acceptable range should be [-30 to -18] dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36fd1-211"><strong>рксагкноиселевел</strong></span><span class="sxs-lookup"><span data-stu-id="36fd1-211"><strong>RxAGCNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="36fd1-212">int</span><span class="sxs-lookup"><span data-stu-id="36fd1-212">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="36fd1-213">Уровень полученного сигнала на сервере-посреднике от шлюза.</span><span class="sxs-lookup"><span data-stu-id="36fd1-213">Received signal level on the Mediation Server from the Gateway.</span></span> <span data-ttu-id="36fd1-214">Этот показатель относится только к серверу-посреднику.</span><span class="sxs-lookup"><span data-stu-id="36fd1-214">This applies only to the Mediation Server.</span></span> <span data-ttu-id="36fd1-215">Единица измерения — dBoV.</span><span class="sxs-lookup"><span data-stu-id="36fd1-215">The unit of this metric is dBoV.</span></span> <span data-ttu-id="36fd1-216">Приемлемый диапазон для хорошего качества — ниже -50 dBoV.</span><span class="sxs-lookup"><span data-stu-id="36fd1-216">For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36fd1-217"><strong>рксавгагкгаин</strong></span><span class="sxs-lookup"><span data-stu-id="36fd1-217"><strong>RxAvgAGCGain</strong></span></span></p></td>
<td><p><span data-ttu-id="36fd1-218">int</span><span class="sxs-lookup"><span data-stu-id="36fd1-218">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="36fd1-219">Автоматический контроль усиления (АУДИОПОТОКУ) на стороне сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="36fd1-219">Automatic gain control (AGC) on the Mediation Server side.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36fd1-220"><strong>инитиалсигналлевелрмс</strong></span><span class="sxs-lookup"><span data-stu-id="36fd1-220"><strong>InitialSignalLevelRMS</strong></span></span></p></td>
<td><p><span data-ttu-id="36fd1-221">float</span><span class="sxs-lookup"><span data-stu-id="36fd1-221">float</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="36fd1-222">Средняя средняя квадрат (RMS) входящего сигнала до первого 30 секунд вызова.</span><span class="sxs-lookup"><span data-stu-id="36fd1-222">The root mean square (RMS) of the incoming signal of up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36fd1-223"><strong>RecvSignalLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="36fd1-223"><strong>RecvSignalLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="36fd1-224">int</span><span class="sxs-lookup"><span data-stu-id="36fd1-224">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="36fd1-225">Уровень сигнала, полученный на канале 1.</span><span class="sxs-lookup"><span data-stu-id="36fd1-225">Signal level as received on channel 1.</span></span></p>
<p><span data-ttu-id="36fd1-226">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="36fd1-226">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36fd1-227"><strong>RecvSignalLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="36fd1-227"><strong>RecvSignalLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="36fd1-228">int</span><span class="sxs-lookup"><span data-stu-id="36fd1-228">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="36fd1-229">Уровень сигнала, полученный на канале 2.</span><span class="sxs-lookup"><span data-stu-id="36fd1-229">Signal level as received on channel 2.</span></span></p>
<p><span data-ttu-id="36fd1-230">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="36fd1-230">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36fd1-231"><strong>RecvNoiseLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="36fd1-231"><strong>RecvNoiseLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="36fd1-232">int</span><span class="sxs-lookup"><span data-stu-id="36fd1-232">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="36fd1-233">Уровень шума, полученный на канале 1.</span><span class="sxs-lookup"><span data-stu-id="36fd1-233">Noise level as received on channel 1.</span></span></p>
<p><span data-ttu-id="36fd1-234">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="36fd1-234">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36fd1-235"><strong>RecvNoiseLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="36fd1-235"><strong>RecvNoiseLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="36fd1-236">int</span><span class="sxs-lookup"><span data-stu-id="36fd1-236">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="36fd1-237">Уровень шума, полученного по каналу 2.</span><span class="sxs-lookup"><span data-stu-id="36fd1-237">Noise level as received on channel 2.</span></span></p>
<p><span data-ttu-id="36fd1-238">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="36fd1-238">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36fd1-239"><strong>SendSignalLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="36fd1-239"><strong>SendSignalLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="36fd1-240">int</span><span class="sxs-lookup"><span data-stu-id="36fd1-240">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="36fd1-241">Уровень сигнала, отправленный на канале 1.</span><span class="sxs-lookup"><span data-stu-id="36fd1-241">Signal level as sent on channel 1.</span></span></p>
<p><span data-ttu-id="36fd1-242">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="36fd1-242">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36fd1-243"><strong>SendSignalLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="36fd1-243"><strong>SendSignalLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="36fd1-244">int</span><span class="sxs-lookup"><span data-stu-id="36fd1-244">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="36fd1-245">Уровень сигнала, отправленный по каналу 2.</span><span class="sxs-lookup"><span data-stu-id="36fd1-245">Signal level as sent on channel 2.</span></span></p>
<p><span data-ttu-id="36fd1-246">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="36fd1-246">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36fd1-247"><strong>SendNoiseLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="36fd1-247"><strong>SendNoiseLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="36fd1-248">int</span><span class="sxs-lookup"><span data-stu-id="36fd1-248">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="36fd1-249">Уровень шума, отправленный на канале 1.</span><span class="sxs-lookup"><span data-stu-id="36fd1-249">Noise level as sent on channel 1.</span></span></p>
<p><span data-ttu-id="36fd1-250">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="36fd1-250">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36fd1-251"><strong>SendNoiseLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="36fd1-251"><strong>SendNoiseLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="36fd1-252">int</span><span class="sxs-lookup"><span data-stu-id="36fd1-252">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="36fd1-253">Уровень шума, отправленный по каналу 2.</span><span class="sxs-lookup"><span data-stu-id="36fd1-253">Noise level as sent on channel 2.</span></span></p>
<p><span data-ttu-id="36fd1-254">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="36fd1-254">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

