---
title: 'Lync Server 2013: таблица таблица audiosignal'
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
ms.openlocfilehash: 2605bfbd3e1d4023c013557aea2bcf75404fb23c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533516"
---
# <a name="audiosignal-table-in-lync-server-2013"></a><span data-ttu-id="e2d54-102">Таблица Таблица audiosignal в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e2d54-102">AudioSignal table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e2d54-103">_**Последнее изменение темы:** 2013-11-12_</span><span class="sxs-lookup"><span data-stu-id="e2d54-103">_**Topic Last Modified:** 2013-11-12_</span></span>

<span data-ttu-id="e2d54-104">Каждая запись представляет метрики звукового сигнала для одной конечной точки.</span><span class="sxs-lookup"><span data-stu-id="e2d54-104">Each record represents audio signal metrics for one endpoint.</span></span> <span data-ttu-id="e2d54-105">Обычно каждый вызов состоит из двух записей, один из которых является абонентом, а другой — для вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="e2d54-105">Usually, each call has two records, one is for caller, and one is for callee.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e2d54-106"><strong>Column</strong></span><span class="sxs-lookup"><span data-stu-id="e2d54-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="e2d54-107"><strong>Тип данных</strong></span><span class="sxs-lookup"><span data-stu-id="e2d54-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="e2d54-108"><strong>Ключ или индекс</strong></span><span class="sxs-lookup"><span data-stu-id="e2d54-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="e2d54-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="e2d54-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e2d54-110"><strong>конференцедатетиме</strong></span><span class="sxs-lookup"><span data-stu-id="e2d54-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e2d54-111">datetime</span><span class="sxs-lookup"><span data-stu-id="e2d54-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="e2d54-112">Primary</span><span class="sxs-lookup"><span data-stu-id="e2d54-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="e2d54-113">Ссылка из <a href="lync-server-2013-medialine-table.md">таблицы MediaLine в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="e2d54-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2d54-114"><strong>сессионсек</strong></span><span class="sxs-lookup"><span data-stu-id="e2d54-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="e2d54-115">int</span><span class="sxs-lookup"><span data-stu-id="e2d54-115">int</span></span></p></td>
<td><p><span data-ttu-id="e2d54-116">Primary</span><span class="sxs-lookup"><span data-stu-id="e2d54-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="e2d54-117">Ссылка из <a href="lync-server-2013-medialine-table.md">таблицы MediaLine в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="e2d54-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2d54-118"><strong>медиалинелабел</strong></span><span class="sxs-lookup"><span data-stu-id="e2d54-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="e2d54-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="e2d54-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="e2d54-120">Primary</span><span class="sxs-lookup"><span data-stu-id="e2d54-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="e2d54-121">Ссылка из <a href="lync-server-2013-medialine-table.md">таблицы MediaLine в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="e2d54-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2d54-122"><strong>фромкаллер</strong></span><span class="sxs-lookup"><span data-stu-id="e2d54-122"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="e2d54-123">Битовая</span><span class="sxs-lookup"><span data-stu-id="e2d54-123">bit</span></span></p></td>
<td><p><span data-ttu-id="e2d54-124">Primary</span><span class="sxs-lookup"><span data-stu-id="e2d54-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="e2d54-125">0: данные вызываемого абонента</span><span class="sxs-lookup"><span data-stu-id="e2d54-125">0: Callee’s data</span></span></p>
<p><span data-ttu-id="e2d54-126">1: данные вызывающего абонента</span><span class="sxs-lookup"><span data-stu-id="e2d54-126">1: Caller’s data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2d54-127"><strong>сендсигналлевел</strong></span><span class="sxs-lookup"><span data-stu-id="e2d54-127"><strong>SendSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="e2d54-128">int</span><span class="sxs-lookup"><span data-stu-id="e2d54-128">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e2d54-129">Представляет уровень звукового сигнала, поступающего после аналогового усиления контроля.</span><span class="sxs-lookup"><span data-stu-id="e2d54-129">Represents the Post-Analog Gain Control audio signal level.</span></span> <span data-ttu-id="e2d54-130">Единица измерения для этого показателя — дБмо.</span><span class="sxs-lookup"><span data-stu-id="e2d54-130">The unit for this metric is dBmo.</span></span> <span data-ttu-id="e2d54-131">Для приемлемого качества значение должно быть не менее 30 дБмо.</span><span class="sxs-lookup"><span data-stu-id="e2d54-131">For acceptable quality, it should be at least 30 dBmo.</span></span> <span data-ttu-id="e2d54-132">Этот показатель не сообщается сервером аудио- и видеоконференций и IP-телефонами.</span><span class="sxs-lookup"><span data-stu-id="e2d54-132">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2d54-133"><strong>реквсигналлевел</strong></span><span class="sxs-lookup"><span data-stu-id="e2d54-133"><strong>RecvSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="e2d54-134">int</span><span class="sxs-lookup"><span data-stu-id="e2d54-134">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e2d54-135">Обратитесь к разделу Сендсигналлевел.</span><span class="sxs-lookup"><span data-stu-id="e2d54-135">See SendSignalLevel.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2d54-136"><strong>сендноиселевел</strong></span><span class="sxs-lookup"><span data-stu-id="e2d54-136"><strong>SendNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="e2d54-137">int</span><span class="sxs-lookup"><span data-stu-id="e2d54-137">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e2d54-138">Представляет уровень шума управления последующей аналоговой усилением.</span><span class="sxs-lookup"><span data-stu-id="e2d54-138">Represents the Post-Analog Gain Control audio noise level.</span></span> <span data-ttu-id="e2d54-139">Единица измерения для этого показателя — дБмо.</span><span class="sxs-lookup"><span data-stu-id="e2d54-139">The unit for this metric is dBmo.</span></span> <span data-ttu-id="e2d54-140">Для приемлемого качества значение должно быть менее 35 дБмо.</span><span class="sxs-lookup"><span data-stu-id="e2d54-140">For acceptable quality, it should be less than 35 dBmo.</span></span> <span data-ttu-id="e2d54-141">Этот показатель не сообщается сервером аудио- и видеоконференций и IP-телефонами.</span><span class="sxs-lookup"><span data-stu-id="e2d54-141">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2d54-142"><strong>реквноиселевел</strong></span><span class="sxs-lookup"><span data-stu-id="e2d54-142"><strong>RecvNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="e2d54-143">int</span><span class="sxs-lookup"><span data-stu-id="e2d54-143">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e2d54-144">Обратитесь к разделу Сендноиселевел.</span><span class="sxs-lookup"><span data-stu-id="e2d54-144">See SendNoiseLevel.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2d54-145"><strong>ечоретурн</strong></span><span class="sxs-lookup"><span data-stu-id="e2d54-145"><strong>EchoReturn</strong></span></span></p></td>
<td><p><span data-ttu-id="e2d54-146">int</span><span class="sxs-lookup"><span data-stu-id="e2d54-146">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e2d54-147">Метрика улучшения возврата эха.</span><span class="sxs-lookup"><span data-stu-id="e2d54-147">Echo Return Loss Enhancement metric.</span></span> <span data-ttu-id="e2d54-148">Единица измерения для этого показателя — дБ.</span><span class="sxs-lookup"><span data-stu-id="e2d54-148">The unit for this metric is dB.</span></span> <span data-ttu-id="e2d54-149">Чем ниже значение, тем меньше эхосигнал.</span><span class="sxs-lookup"><span data-stu-id="e2d54-149">Lower values represent less echo.</span></span> <span data-ttu-id="e2d54-150">Этот показатель не сообщается сервером аудио- и видеоконференций и IP-телефонами.</span><span class="sxs-lookup"><span data-stu-id="e2d54-150">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2d54-151"><strong>аудиоспеакерглитчрате</strong></span><span class="sxs-lookup"><span data-stu-id="e2d54-151"><strong>AudioSpeakerGlitchRate</strong></span></span></p></td>
<td><p><span data-ttu-id="e2d54-152">int</span><span class="sxs-lookup"><span data-stu-id="e2d54-152">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e2d54-153">Среднее число сбоев для отображения лаудспеакер в пять минут.</span><span class="sxs-lookup"><span data-stu-id="e2d54-153">Average glitches per five minutes for the loudspeaker rendering.</span></span> <span data-ttu-id="e2d54-154">Для хорошего качества должно быть не более одного сбоя в пять минут.</span><span class="sxs-lookup"><span data-stu-id="e2d54-154">For good quality, this should be less than one per five minutes.</span></span> <span data-ttu-id="e2d54-155">Этот показатель не сообщается серверами аудио- и видеоконференций, серверами-посредниками и IP-телефонами.</span><span class="sxs-lookup"><span data-stu-id="e2d54-155">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2d54-156"><strong>аудиомикглитчрате</strong></span><span class="sxs-lookup"><span data-stu-id="e2d54-156"><strong>AudioMicGlitchRate</strong></span></span></p></td>
<td><p><span data-ttu-id="e2d54-157">int</span><span class="sxs-lookup"><span data-stu-id="e2d54-157">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e2d54-158">Среднее число сбоев для записи микрофона в течение пяти минут.</span><span class="sxs-lookup"><span data-stu-id="e2d54-158">Average glitches per five minutes for the microphone capture.</span></span> <span data-ttu-id="e2d54-159">Для хорошего качества должно быть не более одного сбоя в пять минут.</span><span class="sxs-lookup"><span data-stu-id="e2d54-159">For good quality this should be less than one per five minutes.</span></span> <span data-ttu-id="e2d54-160">Этот показатель не сообщается серверами аудио- и видеоконференций, серверами-посредниками и IP-телефонами.</span><span class="sxs-lookup"><span data-stu-id="e2d54-160">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2d54-161"><strong>аудиотиместампдрифтратемик</strong></span><span class="sxs-lookup"><span data-stu-id="e2d54-161"><strong>AudioTimestampDriftRateMic</strong></span></span></p></td>
<td><p><span data-ttu-id="e2d54-162">десятичное число (9, 2)</span><span class="sxs-lookup"><span data-stu-id="e2d54-162">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e2d54-163">Частота расхождения сигналов для микрофона, относящихся к часам процессора.</span><span class="sxs-lookup"><span data-stu-id="e2d54-163">Microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2d54-164"><strong>аудиотиместампдрифтратеспк</strong></span><span class="sxs-lookup"><span data-stu-id="e2d54-164"><strong>AudioTimestampDriftRateSpk</strong></span></span></p></td>
<td><p><span data-ttu-id="e2d54-165">десятичное число (9, 2)</span><span class="sxs-lookup"><span data-stu-id="e2d54-165">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e2d54-166">Частота расхождения сигналов для динамиков, относящихся к часам процессора.</span><span class="sxs-lookup"><span data-stu-id="e2d54-166">Speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2d54-167"><strong>аудиотиместамперрормикмс</strong></span><span class="sxs-lookup"><span data-stu-id="e2d54-167"><strong>AudioTimestampErrorMicMs</strong></span></span></p></td>
<td><p><span data-ttu-id="e2d54-168">десятичное число (9, 2)</span><span class="sxs-lookup"><span data-stu-id="e2d54-168">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e2d54-169">Частота расхождения сигналов для динамиков, относящихся к часам процессора.</span><span class="sxs-lookup"><span data-stu-id="e2d54-169">Speaker device clock drift rate, relative to CPU clock.</span></span></p>
<p><span data-ttu-id="e2d54-170">Средняя ошибка метки времени для потока захвата микрофоном, в миллисекундах, в последние 20 секунд вызова.</span><span class="sxs-lookup"><span data-stu-id="e2d54-170">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2d54-171"><strong>аудиотиместамперрорспкмс</strong></span><span class="sxs-lookup"><span data-stu-id="e2d54-171"><strong>AudioTimestampErrorSpkMs</strong></span></span></p></td>
<td><p><span data-ttu-id="e2d54-172">десятичное число (9, 2)</span><span class="sxs-lookup"><span data-stu-id="e2d54-172">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e2d54-173">Средняя ошибка метки времени потока отображения динамиков, в миллисекундах, в последние 20 секунд вызова.</span><span class="sxs-lookup"><span data-stu-id="e2d54-173">Average speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2d54-174"><strong>всентрикаусес</strong></span><span class="sxs-lookup"><span data-stu-id="e2d54-174"><strong>VsEntryCauses</strong></span></span></p></td>
<td><p><span data-ttu-id="e2d54-175">smallint</span><span class="sxs-lookup"><span data-stu-id="e2d54-175">smallint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e2d54-176">Речевой коммутатор — это полудуплексный режим с уменьшенной возможностью прерывания.</span><span class="sxs-lookup"><span data-stu-id="e2d54-176">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="e2d54-177">Причины записи голосового переключателя:</span><span class="sxs-lookup"><span data-stu-id="e2d54-177">Causes of voice switch entry:</span></span></p>
<p><span data-ttu-id="e2d54-178">ENTER_VS_BADTS 0x01</span><span class="sxs-lookup"><span data-stu-id="e2d54-178">ENTER_VS_BADTS 0x01</span></span></p>
<p><span data-ttu-id="e2d54-179">ENTER_VS_ECHO 0x02</span><span class="sxs-lookup"><span data-stu-id="e2d54-179">ENTER_VS_ECHO 0x02</span></span></p>
<p><span data-ttu-id="e2d54-180">ENTER_VS_FORCEORCONVERGENCE 0x04</span><span class="sxs-lookup"><span data-stu-id="e2d54-180">ENTER_VS_FORCEORCONVERGENCE 0x04</span></span></p>
<p><span data-ttu-id="e2d54-181">ENTER_VS_DNLP 0x08</span><span class="sxs-lookup"><span data-stu-id="e2d54-181">ENTER_VS_DNLP 0x08</span></span></p>
<p><span data-ttu-id="e2d54-182">Причина может быть сочетанием отдельных причин.</span><span class="sxs-lookup"><span data-stu-id="e2d54-182">The cause can be a combination of those individual causes.</span></span> <span data-ttu-id="e2d54-183">В этом случае ENTER_VS_FORCEORCONVERGENCE может быть включен только в RegKey для тестового назначения.</span><span class="sxs-lookup"><span data-stu-id="e2d54-183">ENTER_VS_FORCEORCONVERGENCE can only be enabled by regkey for test purpose.</span></span></p>
<p><span data-ttu-id="e2d54-184">Тип данных для этого столбца был изменен в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e2d54-184">The data type for this column was changed in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2d54-185"><strong>ечоевенткаусес</strong></span><span class="sxs-lookup"><span data-stu-id="e2d54-185"><strong>EchoEventCauses</strong></span></span></p></td>
<td><p><span data-ttu-id="e2d54-186">tinyint</span><span class="sxs-lookup"><span data-stu-id="e2d54-186">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e2d54-187">Причины возникновения события echo:</span><span class="sxs-lookup"><span data-stu-id="e2d54-187">Causes of an echo event:</span></span></p>
<p><span data-ttu-id="e2d54-188">ECHO_EVENT_BAD_TIMESTAMP 0x01</span><span class="sxs-lookup"><span data-stu-id="e2d54-188">ECHO_EVENT_BAD_TIMESTAMP 0x01</span></span></p>
<p><span data-ttu-id="e2d54-189">ECHO_EVENT_POSTAEC_ECHO 0x02</span><span class="sxs-lookup"><span data-stu-id="e2d54-189">ECHO_EVENT_POSTAEC_ECHO 0x02</span></span></p>
<p><span data-ttu-id="e2d54-190">ECHO_EVENT_ANLP 0x04</span><span class="sxs-lookup"><span data-stu-id="e2d54-190">ECHO_EVENT_ANLP 0x04</span></span></p>
<p><span data-ttu-id="e2d54-191">ECHO_EVENT_DNLP 0x08</span><span class="sxs-lookup"><span data-stu-id="e2d54-191">ECHO_EVENT_DNLP 0x08</span></span></p>
<p><span data-ttu-id="e2d54-192">ECHO_EVENT_MIC_CLIPPING 0x10</span><span class="sxs-lookup"><span data-stu-id="e2d54-192">ECHO_EVENT_MIC_CLIPPING 0x10</span></span></p>
<p><span data-ttu-id="e2d54-193">ECHO_EVENT_BAD_STATE 0x20</span><span class="sxs-lookup"><span data-stu-id="e2d54-193">ECHO_EVENT_BAD_STATE 0x20</span></span></p>
<p><span data-ttu-id="e2d54-194">Причина может быть сочетанием отдельных причин.</span><span class="sxs-lookup"><span data-stu-id="e2d54-194">The cause can be a combination of those individual causes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2d54-195"><strong>ечоперцентмиЦин</strong></span><span class="sxs-lookup"><span data-stu-id="e2d54-195"><strong>EchoPercentMicIn</strong></span></span></p></td>
<td><p><span data-ttu-id="e2d54-196">десятичное число (5, 2)</span><span class="sxs-lookup"><span data-stu-id="e2d54-196">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e2d54-197">Процент времени, когда в потоке записи микрофона обнаружено эхо-сообщений.</span><span class="sxs-lookup"><span data-stu-id="e2d54-197">Percentage of time when echo was detected in the microphone capture stream.</span></span> <span data-ttu-id="e2d54-198">Как правило, низкие значения для гарнитур и телефонов, а также для телефонов динамиков или отдельных динамиков.</span><span class="sxs-lookup"><span data-stu-id="e2d54-198">Typically, values are low for headsets or handsets, and higher for speaker phones or stand-alone speakers.</span></span> <span data-ttu-id="e2d54-199">Для устройств, поддерживающих встроенную отдавление акустического эха, высокие значения указывают на наличие потерь эха.</span><span class="sxs-lookup"><span data-stu-id="e2d54-199">For devices that support on-board acoustic echo cancellation, high values indicate echo leak.</span></span> <span data-ttu-id="e2d54-200">Для других устройств эта метрика не должна использоваться для оценки качества устройства.</span><span class="sxs-lookup"><span data-stu-id="e2d54-200">For other devices, this metric should not be used to evaluate device quality.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2d54-201"><strong>ечоперцентсенд</strong></span><span class="sxs-lookup"><span data-stu-id="e2d54-201"><strong>EchoPercentSend</strong></span></span></p></td>
<td><p><span data-ttu-id="e2d54-202">десятичное число (5, 2)</span><span class="sxs-lookup"><span data-stu-id="e2d54-202">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e2d54-203">Процент времени, в течение которого обнаружено Эхо-сообщения в отправленном потоке.</span><span class="sxs-lookup"><span data-stu-id="e2d54-203">Percentage of time when echo is detected in sent stream.</span></span> <span data-ttu-id="e2d54-204">Высокое значение в отправленных потоках указывает на утечку эхосигнала.</span><span class="sxs-lookup"><span data-stu-id="e2d54-204">High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2d54-205"><strong>рксагксигналлевел</strong></span><span class="sxs-lookup"><span data-stu-id="e2d54-205"><strong>RxAGCSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="e2d54-206">int</span><span class="sxs-lookup"><span data-stu-id="e2d54-206">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e2d54-207">Уровень полученного сигнала на сервере-посреднике от шлюза; Это относится только к серверу-посреднику.</span><span class="sxs-lookup"><span data-stu-id="e2d54-207">Received signal level on the Mediation Server from the Gateway; this applies only to the Mediation Server.</span></span> <span data-ttu-id="e2d54-208">Единица измерения — dBoV.</span><span class="sxs-lookup"><span data-stu-id="e2d54-208">The unit of this metric is dBoV.</span></span> <span data-ttu-id="e2d54-209">Приемлемый диапазон для хорошего качества — от -30 до -18 dBoV.</span><span class="sxs-lookup"><span data-stu-id="e2d54-209">For good quality, the acceptable range should be [-30 to -18] dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2d54-210"><strong>рксагкноиселевел</strong></span><span class="sxs-lookup"><span data-stu-id="e2d54-210"><strong>RxAGCNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="e2d54-211">int</span><span class="sxs-lookup"><span data-stu-id="e2d54-211">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e2d54-212">Уровень полученного сигнала на сервере-посреднике от шлюза.</span><span class="sxs-lookup"><span data-stu-id="e2d54-212">Received signal level on the Mediation Server from the Gateway.</span></span> <span data-ttu-id="e2d54-213">Этот показатель относится только к серверу-посреднику.</span><span class="sxs-lookup"><span data-stu-id="e2d54-213">This applies only to the Mediation Server.</span></span> <span data-ttu-id="e2d54-214">Единица измерения — dBoV.</span><span class="sxs-lookup"><span data-stu-id="e2d54-214">The unit of this metric is dBoV.</span></span> <span data-ttu-id="e2d54-215">Приемлемый диапазон для хорошего качества — ниже -50 dBoV.</span><span class="sxs-lookup"><span data-stu-id="e2d54-215">For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2d54-216"><strong>рксавгагкгаин</strong></span><span class="sxs-lookup"><span data-stu-id="e2d54-216"><strong>RxAvgAGCGain</strong></span></span></p></td>
<td><p><span data-ttu-id="e2d54-217">int</span><span class="sxs-lookup"><span data-stu-id="e2d54-217">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e2d54-218">Автоматический контроль усиления (АУДИОПОТОКУ) на стороне сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="e2d54-218">Automatic gain control (AGC) on the Mediation Server side.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2d54-219"><strong>инитиалсигналлевелрмс</strong></span><span class="sxs-lookup"><span data-stu-id="e2d54-219"><strong>InitialSignalLevelRMS</strong></span></span></p></td>
<td><p><span data-ttu-id="e2d54-220">float</span><span class="sxs-lookup"><span data-stu-id="e2d54-220">float</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e2d54-221">Средняя средняя квадрат (RMS) входящего сигнала до первого 30 секунд вызова.</span><span class="sxs-lookup"><span data-stu-id="e2d54-221">The root mean square (RMS) of the incoming signal of up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2d54-222"><strong>RecvSignalLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="e2d54-222"><strong>RecvSignalLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="e2d54-223">int</span><span class="sxs-lookup"><span data-stu-id="e2d54-223">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e2d54-224">Уровень сигнала, полученный на канале 1.</span><span class="sxs-lookup"><span data-stu-id="e2d54-224">Signal level as received on channel 1.</span></span></p>
<p><span data-ttu-id="e2d54-225">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e2d54-225">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2d54-226"><strong>RecvSignalLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="e2d54-226"><strong>RecvSignalLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="e2d54-227">int</span><span class="sxs-lookup"><span data-stu-id="e2d54-227">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e2d54-228">Уровень сигнала, полученный на канале 2.</span><span class="sxs-lookup"><span data-stu-id="e2d54-228">Signal level as received on channel 2.</span></span></p>
<p><span data-ttu-id="e2d54-229">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e2d54-229">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2d54-230"><strong>RecvNoiseLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="e2d54-230"><strong>RecvNoiseLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="e2d54-231">int</span><span class="sxs-lookup"><span data-stu-id="e2d54-231">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e2d54-232">Уровень шума, полученный на канале 1.</span><span class="sxs-lookup"><span data-stu-id="e2d54-232">Noise level as received on channel 1.</span></span></p>
<p><span data-ttu-id="e2d54-233">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e2d54-233">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2d54-234"><strong>RecvNoiseLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="e2d54-234"><strong>RecvNoiseLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="e2d54-235">int</span><span class="sxs-lookup"><span data-stu-id="e2d54-235">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e2d54-236">Уровень шума, полученного по каналу 2.</span><span class="sxs-lookup"><span data-stu-id="e2d54-236">Noise level as received on channel 2.</span></span></p>
<p><span data-ttu-id="e2d54-237">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e2d54-237">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2d54-238"><strong>SendSignalLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="e2d54-238"><strong>SendSignalLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="e2d54-239">int</span><span class="sxs-lookup"><span data-stu-id="e2d54-239">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e2d54-240">Уровень сигнала, отправленный на канале 1.</span><span class="sxs-lookup"><span data-stu-id="e2d54-240">Signal level as sent on channel 1.</span></span></p>
<p><span data-ttu-id="e2d54-241">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e2d54-241">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2d54-242"><strong>SendSignalLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="e2d54-242"><strong>SendSignalLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="e2d54-243">int</span><span class="sxs-lookup"><span data-stu-id="e2d54-243">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e2d54-244">Уровень сигнала, отправленный по каналу 2.</span><span class="sxs-lookup"><span data-stu-id="e2d54-244">Signal level as sent on channel 2.</span></span></p>
<p><span data-ttu-id="e2d54-245">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e2d54-245">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2d54-246"><strong>SendNoiseLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="e2d54-246"><strong>SendNoiseLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="e2d54-247">int</span><span class="sxs-lookup"><span data-stu-id="e2d54-247">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e2d54-248">Уровень шума, отправленный на канале 1.</span><span class="sxs-lookup"><span data-stu-id="e2d54-248">Noise level as sent on channel 1.</span></span></p>
<p><span data-ttu-id="e2d54-249">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e2d54-249">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2d54-250"><strong>SendNoiseLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="e2d54-250"><strong>SendNoiseLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="e2d54-251">int</span><span class="sxs-lookup"><span data-stu-id="e2d54-251">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e2d54-252">Уровень шума, отправленный по каналу 2.</span><span class="sxs-lookup"><span data-stu-id="e2d54-252">Noise level as sent on channel 2.</span></span></p>
<p><span data-ttu-id="e2d54-253">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e2d54-253">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

