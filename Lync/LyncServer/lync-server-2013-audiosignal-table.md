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
ms.openlocfilehash: 9d7dcf9337dceded96679411e575abc888164618
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044591"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audiosignal-table-in-lync-server-2013"></a><span data-ttu-id="2ea53-102">Таблица Таблица audiosignal в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2ea53-102">AudioSignal table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2ea53-103">_**Последнее изменение темы:** 2013-11-12_</span><span class="sxs-lookup"><span data-stu-id="2ea53-103">_**Topic Last Modified:** 2013-11-12_</span></span>

<span data-ttu-id="2ea53-104">Каждая запись представляет метрики звукового сигнала для одной конечной точки.</span><span class="sxs-lookup"><span data-stu-id="2ea53-104">Each record represents audio signal metrics for one endpoint.</span></span> <span data-ttu-id="2ea53-105">Обычно каждый вызов состоит из двух записей, один из которых является абонентом, а другой — для вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="2ea53-105">Usually, each call has two records, one is for caller, and one is for callee.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2ea53-106"><strong>Column</strong></span><span class="sxs-lookup"><span data-stu-id="2ea53-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="2ea53-107"><strong>Тип данных</strong></span><span class="sxs-lookup"><span data-stu-id="2ea53-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="2ea53-108"><strong>Ключ или индекс</strong></span><span class="sxs-lookup"><span data-stu-id="2ea53-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="2ea53-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="2ea53-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2ea53-110"><strong>конференцедатетиме</strong></span><span class="sxs-lookup"><span data-stu-id="2ea53-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="2ea53-111">datetime</span><span class="sxs-lookup"><span data-stu-id="2ea53-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="2ea53-112">Primary</span><span class="sxs-lookup"><span data-stu-id="2ea53-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="2ea53-113">Ссылка из <a href="lync-server-2013-medialine-table.md">таблицы MediaLine в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="2ea53-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ea53-114"><strong>сессионсек</strong></span><span class="sxs-lookup"><span data-stu-id="2ea53-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="2ea53-115">int</span><span class="sxs-lookup"><span data-stu-id="2ea53-115">int</span></span></p></td>
<td><p><span data-ttu-id="2ea53-116">Primary</span><span class="sxs-lookup"><span data-stu-id="2ea53-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="2ea53-117">Ссылка из <a href="lync-server-2013-medialine-table.md">таблицы MediaLine в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="2ea53-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ea53-118"><strong>медиалинелабел</strong></span><span class="sxs-lookup"><span data-stu-id="2ea53-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="2ea53-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="2ea53-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="2ea53-120">Primary</span><span class="sxs-lookup"><span data-stu-id="2ea53-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="2ea53-121">Ссылка из <a href="lync-server-2013-medialine-table.md">таблицы MediaLine в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="2ea53-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ea53-122"><strong>фромкаллер</strong></span><span class="sxs-lookup"><span data-stu-id="2ea53-122"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="2ea53-123">Битовая</span><span class="sxs-lookup"><span data-stu-id="2ea53-123">bit</span></span></p></td>
<td><p><span data-ttu-id="2ea53-124">Primary</span><span class="sxs-lookup"><span data-stu-id="2ea53-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="2ea53-125">0: данные вызываемого абонента</span><span class="sxs-lookup"><span data-stu-id="2ea53-125">0: Callee’s data</span></span></p>
<p><span data-ttu-id="2ea53-126">1: данные вызывающего абонента</span><span class="sxs-lookup"><span data-stu-id="2ea53-126">1: Caller’s data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ea53-127"><strong>сендсигналлевел</strong></span><span class="sxs-lookup"><span data-stu-id="2ea53-127"><strong>SendSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="2ea53-128">int</span><span class="sxs-lookup"><span data-stu-id="2ea53-128">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="2ea53-129">Представляет уровень звукового сигнала, поступающего после аналогового усиления контроля.</span><span class="sxs-lookup"><span data-stu-id="2ea53-129">Represents the Post-Analog Gain Control audio signal level.</span></span> <span data-ttu-id="2ea53-130">Единица измерения для этого показателя — дБмо.</span><span class="sxs-lookup"><span data-stu-id="2ea53-130">The unit for this metric is dBmo.</span></span> <span data-ttu-id="2ea53-131">Для приемлемого качества значение должно быть не менее 30 дБмо.</span><span class="sxs-lookup"><span data-stu-id="2ea53-131">For acceptable quality, it should be at least 30 dBmo.</span></span> <span data-ttu-id="2ea53-132">Этот показатель не сообщается сервером аудио- и видеоконференций и IP-телефонами.</span><span class="sxs-lookup"><span data-stu-id="2ea53-132">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ea53-133"><strong>реквсигналлевел</strong></span><span class="sxs-lookup"><span data-stu-id="2ea53-133"><strong>RecvSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="2ea53-134">int</span><span class="sxs-lookup"><span data-stu-id="2ea53-134">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="2ea53-135">Обратитесь к разделу Сендсигналлевел.</span><span class="sxs-lookup"><span data-stu-id="2ea53-135">See SendSignalLevel.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ea53-136"><strong>сендноиселевел</strong></span><span class="sxs-lookup"><span data-stu-id="2ea53-136"><strong>SendNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="2ea53-137">int</span><span class="sxs-lookup"><span data-stu-id="2ea53-137">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="2ea53-138">Представляет уровень шума управления последующей аналоговой усилением.</span><span class="sxs-lookup"><span data-stu-id="2ea53-138">Represents the Post-Analog Gain Control audio noise level.</span></span> <span data-ttu-id="2ea53-139">Единица измерения для этого показателя — дБмо.</span><span class="sxs-lookup"><span data-stu-id="2ea53-139">The unit for this metric is dBmo.</span></span> <span data-ttu-id="2ea53-140">Для приемлемого качества значение должно быть менее 35 дБмо.</span><span class="sxs-lookup"><span data-stu-id="2ea53-140">For acceptable quality, it should be less than 35 dBmo.</span></span> <span data-ttu-id="2ea53-141">Этот показатель не сообщается сервером аудио- и видеоконференций и IP-телефонами.</span><span class="sxs-lookup"><span data-stu-id="2ea53-141">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ea53-142"><strong>реквноиселевел</strong></span><span class="sxs-lookup"><span data-stu-id="2ea53-142"><strong>RecvNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="2ea53-143">int</span><span class="sxs-lookup"><span data-stu-id="2ea53-143">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="2ea53-144">Обратитесь к разделу Сендноиселевел.</span><span class="sxs-lookup"><span data-stu-id="2ea53-144">See SendNoiseLevel.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ea53-145"><strong>ечоретурн</strong></span><span class="sxs-lookup"><span data-stu-id="2ea53-145"><strong>EchoReturn</strong></span></span></p></td>
<td><p><span data-ttu-id="2ea53-146">int</span><span class="sxs-lookup"><span data-stu-id="2ea53-146">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="2ea53-147">Метрика улучшения возврата эха.</span><span class="sxs-lookup"><span data-stu-id="2ea53-147">Echo Return Loss Enhancement metric.</span></span> <span data-ttu-id="2ea53-148">Единица измерения для этого показателя — дБ.</span><span class="sxs-lookup"><span data-stu-id="2ea53-148">The unit for this metric is dB.</span></span> <span data-ttu-id="2ea53-149">Чем ниже значение, тем меньше эхосигнал.</span><span class="sxs-lookup"><span data-stu-id="2ea53-149">Lower values represent less echo.</span></span> <span data-ttu-id="2ea53-150">Этот показатель не сообщается сервером аудио- и видеоконференций и IP-телефонами.</span><span class="sxs-lookup"><span data-stu-id="2ea53-150">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ea53-151"><strong>аудиоспеакерглитчрате</strong></span><span class="sxs-lookup"><span data-stu-id="2ea53-151"><strong>AudioSpeakerGlitchRate</strong></span></span></p></td>
<td><p><span data-ttu-id="2ea53-152">int</span><span class="sxs-lookup"><span data-stu-id="2ea53-152">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="2ea53-153">Среднее число сбоев для отображения лаудспеакер в пять минут.</span><span class="sxs-lookup"><span data-stu-id="2ea53-153">Average glitches per five minutes for the loudspeaker rendering.</span></span> <span data-ttu-id="2ea53-154">Для хорошего качества должно быть не более одного сбоя в пять минут.</span><span class="sxs-lookup"><span data-stu-id="2ea53-154">For good quality, this should be less than one per five minutes.</span></span> <span data-ttu-id="2ea53-155">Этот показатель не сообщается серверами аудио- и видеоконференций, серверами-посредниками и IP-телефонами.</span><span class="sxs-lookup"><span data-stu-id="2ea53-155">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ea53-156"><strong>аудиомикглитчрате</strong></span><span class="sxs-lookup"><span data-stu-id="2ea53-156"><strong>AudioMicGlitchRate</strong></span></span></p></td>
<td><p><span data-ttu-id="2ea53-157">int</span><span class="sxs-lookup"><span data-stu-id="2ea53-157">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="2ea53-158">Среднее число сбоев для записи микрофона в течение пяти минут.</span><span class="sxs-lookup"><span data-stu-id="2ea53-158">Average glitches per five minutes for the microphone capture.</span></span> <span data-ttu-id="2ea53-159">Для хорошего качества должно быть не более одного сбоя в пять минут.</span><span class="sxs-lookup"><span data-stu-id="2ea53-159">For good quality this should be less than one per five minutes.</span></span> <span data-ttu-id="2ea53-160">Этот показатель не сообщается серверами аудио- и видеоконференций, серверами-посредниками и IP-телефонами.</span><span class="sxs-lookup"><span data-stu-id="2ea53-160">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ea53-161"><strong>аудиотиместампдрифтратемик</strong></span><span class="sxs-lookup"><span data-stu-id="2ea53-161"><strong>AudioTimestampDriftRateMic</strong></span></span></p></td>
<td><p><span data-ttu-id="2ea53-162">десятичное число (9, 2)</span><span class="sxs-lookup"><span data-stu-id="2ea53-162">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="2ea53-163">Частота расхождения сигналов для микрофона, относящихся к часам процессора.</span><span class="sxs-lookup"><span data-stu-id="2ea53-163">Microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ea53-164"><strong>аудиотиместампдрифтратеспк</strong></span><span class="sxs-lookup"><span data-stu-id="2ea53-164"><strong>AudioTimestampDriftRateSpk</strong></span></span></p></td>
<td><p><span data-ttu-id="2ea53-165">десятичное число (9, 2)</span><span class="sxs-lookup"><span data-stu-id="2ea53-165">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="2ea53-166">Частота расхождения сигналов для динамиков, относящихся к часам процессора.</span><span class="sxs-lookup"><span data-stu-id="2ea53-166">Speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ea53-167"><strong>аудиотиместамперрормикмс</strong></span><span class="sxs-lookup"><span data-stu-id="2ea53-167"><strong>AudioTimestampErrorMicMs</strong></span></span></p></td>
<td><p><span data-ttu-id="2ea53-168">десятичное число (9, 2)</span><span class="sxs-lookup"><span data-stu-id="2ea53-168">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="2ea53-169">Частота расхождения сигналов для динамиков, относящихся к часам процессора.</span><span class="sxs-lookup"><span data-stu-id="2ea53-169">Speaker device clock drift rate, relative to CPU clock.</span></span></p>
<p><span data-ttu-id="2ea53-170">Средняя ошибка метки времени для потока захвата микрофоном, в миллисекундах, в последние 20 секунд вызова.</span><span class="sxs-lookup"><span data-stu-id="2ea53-170">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ea53-171"><strong>аудиотиместамперрорспкмс</strong></span><span class="sxs-lookup"><span data-stu-id="2ea53-171"><strong>AudioTimestampErrorSpkMs</strong></span></span></p></td>
<td><p><span data-ttu-id="2ea53-172">десятичное число (9, 2)</span><span class="sxs-lookup"><span data-stu-id="2ea53-172">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="2ea53-173">Средняя ошибка метки времени потока отображения динамиков, в миллисекундах, в последние 20 секунд вызова.</span><span class="sxs-lookup"><span data-stu-id="2ea53-173">Average speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ea53-174"><strong>всентрикаусес</strong></span><span class="sxs-lookup"><span data-stu-id="2ea53-174"><strong>VsEntryCauses</strong></span></span></p></td>
<td><p><span data-ttu-id="2ea53-175">smallint</span><span class="sxs-lookup"><span data-stu-id="2ea53-175">smallint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="2ea53-176">Речевой коммутатор — это полудуплексный режим с уменьшенной возможностью прерывания.</span><span class="sxs-lookup"><span data-stu-id="2ea53-176">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="2ea53-177">Причины записи голосового переключателя:</span><span class="sxs-lookup"><span data-stu-id="2ea53-177">Causes of voice switch entry:</span></span></p>
<p><span data-ttu-id="2ea53-178">ENTER_VS_BADTS 0x01</span><span class="sxs-lookup"><span data-stu-id="2ea53-178">ENTER_VS_BADTS 0x01</span></span></p>
<p><span data-ttu-id="2ea53-179">ENTER_VS_ECHO 0x02</span><span class="sxs-lookup"><span data-stu-id="2ea53-179">ENTER_VS_ECHO 0x02</span></span></p>
<p><span data-ttu-id="2ea53-180">ENTER_VS_FORCEORCONVERGENCE 0x04</span><span class="sxs-lookup"><span data-stu-id="2ea53-180">ENTER_VS_FORCEORCONVERGENCE 0x04</span></span></p>
<p><span data-ttu-id="2ea53-181">ENTER_VS_DNLP 0x08</span><span class="sxs-lookup"><span data-stu-id="2ea53-181">ENTER_VS_DNLP 0x08</span></span></p>
<p><span data-ttu-id="2ea53-182">Причина может быть сочетанием отдельных причин.</span><span class="sxs-lookup"><span data-stu-id="2ea53-182">The cause can be a combination of those individual causes.</span></span> <span data-ttu-id="2ea53-183">В этом случае ENTER_VS_FORCEORCONVERGENCE может быть включен только в RegKey для тестового назначения.</span><span class="sxs-lookup"><span data-stu-id="2ea53-183">ENTER_VS_FORCEORCONVERGENCE can only be enabled by regkey for test purpose.</span></span></p>
<p><span data-ttu-id="2ea53-184">Тип данных для этого столбца был изменен в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2ea53-184">The data type for this column was changed in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ea53-185"><strong>ечоевенткаусес</strong></span><span class="sxs-lookup"><span data-stu-id="2ea53-185"><strong>EchoEventCauses</strong></span></span></p></td>
<td><p><span data-ttu-id="2ea53-186">tinyint</span><span class="sxs-lookup"><span data-stu-id="2ea53-186">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="2ea53-187">Причины возникновения события echo:</span><span class="sxs-lookup"><span data-stu-id="2ea53-187">Causes of an echo event:</span></span></p>
<p><span data-ttu-id="2ea53-188">ECHO_EVENT_BAD_TIMESTAMP 0x01</span><span class="sxs-lookup"><span data-stu-id="2ea53-188">ECHO_EVENT_BAD_TIMESTAMP 0x01</span></span></p>
<p><span data-ttu-id="2ea53-189">ECHO_EVENT_POSTAEC_ECHO 0x02</span><span class="sxs-lookup"><span data-stu-id="2ea53-189">ECHO_EVENT_POSTAEC_ECHO 0x02</span></span></p>
<p><span data-ttu-id="2ea53-190">ECHO_EVENT_ANLP 0x04</span><span class="sxs-lookup"><span data-stu-id="2ea53-190">ECHO_EVENT_ANLP 0x04</span></span></p>
<p><span data-ttu-id="2ea53-191">ECHO_EVENT_DNLP 0x08</span><span class="sxs-lookup"><span data-stu-id="2ea53-191">ECHO_EVENT_DNLP 0x08</span></span></p>
<p><span data-ttu-id="2ea53-192">ECHO_EVENT_MIC_CLIPPING 0x10</span><span class="sxs-lookup"><span data-stu-id="2ea53-192">ECHO_EVENT_MIC_CLIPPING 0x10</span></span></p>
<p><span data-ttu-id="2ea53-193">ECHO_EVENT_BAD_STATE 0x20</span><span class="sxs-lookup"><span data-stu-id="2ea53-193">ECHO_EVENT_BAD_STATE 0x20</span></span></p>
<p><span data-ttu-id="2ea53-194">Причина может быть сочетанием отдельных причин.</span><span class="sxs-lookup"><span data-stu-id="2ea53-194">The cause can be a combination of those individual causes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ea53-195"><strong>ечоперцентмиЦин</strong></span><span class="sxs-lookup"><span data-stu-id="2ea53-195"><strong>EchoPercentMicIn</strong></span></span></p></td>
<td><p><span data-ttu-id="2ea53-196">десятичное число (5, 2)</span><span class="sxs-lookup"><span data-stu-id="2ea53-196">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="2ea53-197">Процент времени, когда в потоке записи микрофона обнаружено эхо-сообщений.</span><span class="sxs-lookup"><span data-stu-id="2ea53-197">Percentage of time when echo was detected in the microphone capture stream.</span></span> <span data-ttu-id="2ea53-198">Как правило, низкие значения для гарнитур и телефонов, а также для телефонов динамиков или отдельных динамиков.</span><span class="sxs-lookup"><span data-stu-id="2ea53-198">Typically, values are low for headsets or handsets, and higher for speaker phones or stand-alone speakers.</span></span> <span data-ttu-id="2ea53-199">Для устройств, поддерживающих встроенную отдавление акустического эха, высокие значения указывают на наличие потерь эха.</span><span class="sxs-lookup"><span data-stu-id="2ea53-199">For devices that support on-board acoustic echo cancellation, high values indicate echo leak.</span></span> <span data-ttu-id="2ea53-200">Для других устройств эта метрика не должна использоваться для оценки качества устройства.</span><span class="sxs-lookup"><span data-stu-id="2ea53-200">For other devices, this metric should not be used to evaluate device quality.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ea53-201"><strong>ечоперцентсенд</strong></span><span class="sxs-lookup"><span data-stu-id="2ea53-201"><strong>EchoPercentSend</strong></span></span></p></td>
<td><p><span data-ttu-id="2ea53-202">десятичное число (5, 2)</span><span class="sxs-lookup"><span data-stu-id="2ea53-202">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2ea53-203">Процент времени, в течение которого обнаружено Эхо-сообщения в отправленном потоке.</span><span class="sxs-lookup"><span data-stu-id="2ea53-203">Percentage of time when echo is detected in sent stream.</span></span> <span data-ttu-id="2ea53-204">Высокое значение в отправленных потоках указывает на утечку эхосигнала.</span><span class="sxs-lookup"><span data-stu-id="2ea53-204">High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ea53-205"><strong>рксагксигналлевел</strong></span><span class="sxs-lookup"><span data-stu-id="2ea53-205"><strong>RxAGCSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="2ea53-206">int</span><span class="sxs-lookup"><span data-stu-id="2ea53-206">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="2ea53-207">Уровень полученного сигнала на сервере-посреднике от шлюза; Это относится только к серверу-посреднику.</span><span class="sxs-lookup"><span data-stu-id="2ea53-207">Received signal level on the Mediation Server from the Gateway; this applies only to the Mediation Server.</span></span> <span data-ttu-id="2ea53-208">Единица измерения — dBoV.</span><span class="sxs-lookup"><span data-stu-id="2ea53-208">The unit of this metric is dBoV.</span></span> <span data-ttu-id="2ea53-209">Приемлемый диапазон для хорошего качества — от -30 до -18 dBoV.</span><span class="sxs-lookup"><span data-stu-id="2ea53-209">For good quality, the acceptable range should be [-30 to -18] dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ea53-210"><strong>рксагкноиселевел</strong></span><span class="sxs-lookup"><span data-stu-id="2ea53-210"><strong>RxAGCNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="2ea53-211">int</span><span class="sxs-lookup"><span data-stu-id="2ea53-211">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="2ea53-212">Уровень полученного сигнала на сервере-посреднике от шлюза.</span><span class="sxs-lookup"><span data-stu-id="2ea53-212">Received signal level on the Mediation Server from the Gateway.</span></span> <span data-ttu-id="2ea53-213">Этот показатель относится только к серверу-посреднику.</span><span class="sxs-lookup"><span data-stu-id="2ea53-213">This applies only to the Mediation Server.</span></span> <span data-ttu-id="2ea53-214">Единица измерения — dBoV.</span><span class="sxs-lookup"><span data-stu-id="2ea53-214">The unit of this metric is dBoV.</span></span> <span data-ttu-id="2ea53-215">Приемлемый диапазон для хорошего качества — ниже -50 dBoV.</span><span class="sxs-lookup"><span data-stu-id="2ea53-215">For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ea53-216"><strong>рксавгагкгаин</strong></span><span class="sxs-lookup"><span data-stu-id="2ea53-216"><strong>RxAvgAGCGain</strong></span></span></p></td>
<td><p><span data-ttu-id="2ea53-217">int</span><span class="sxs-lookup"><span data-stu-id="2ea53-217">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="2ea53-218">Автоматический контроль усиления (АУДИОПОТОКУ) на стороне сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="2ea53-218">Automatic gain control (AGC) on the Mediation Server side.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ea53-219"><strong>инитиалсигналлевелрмс</strong></span><span class="sxs-lookup"><span data-stu-id="2ea53-219"><strong>InitialSignalLevelRMS</strong></span></span></p></td>
<td><p><span data-ttu-id="2ea53-220">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="2ea53-220">float</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="2ea53-221">Средняя средняя квадрат (RMS) входящего сигнала до первого 30 секунд вызова.</span><span class="sxs-lookup"><span data-stu-id="2ea53-221">The root mean square (RMS) of the incoming signal of up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ea53-222"><strong>RecvSignalLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="2ea53-222"><strong>RecvSignalLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="2ea53-223">int</span><span class="sxs-lookup"><span data-stu-id="2ea53-223">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2ea53-224">Уровень сигнала, полученный на канале 1.</span><span class="sxs-lookup"><span data-stu-id="2ea53-224">Signal level as received on channel 1.</span></span></p>
<p><span data-ttu-id="2ea53-225">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2ea53-225">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ea53-226"><strong>RecvSignalLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="2ea53-226"><strong>RecvSignalLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="2ea53-227">int</span><span class="sxs-lookup"><span data-stu-id="2ea53-227">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2ea53-228">Уровень сигнала, полученный на канале 2.</span><span class="sxs-lookup"><span data-stu-id="2ea53-228">Signal level as received on channel 2.</span></span></p>
<p><span data-ttu-id="2ea53-229">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2ea53-229">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ea53-230"><strong>RecvNoiseLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="2ea53-230"><strong>RecvNoiseLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="2ea53-231">int</span><span class="sxs-lookup"><span data-stu-id="2ea53-231">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2ea53-232">Уровень шума, полученный на канале 1.</span><span class="sxs-lookup"><span data-stu-id="2ea53-232">Noise level as received on channel 1.</span></span></p>
<p><span data-ttu-id="2ea53-233">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2ea53-233">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ea53-234"><strong>RecvNoiseLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="2ea53-234"><strong>RecvNoiseLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="2ea53-235">int</span><span class="sxs-lookup"><span data-stu-id="2ea53-235">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2ea53-236">Уровень шума, полученного по каналу 2.</span><span class="sxs-lookup"><span data-stu-id="2ea53-236">Noise level as received on channel 2.</span></span></p>
<p><span data-ttu-id="2ea53-237">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2ea53-237">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ea53-238"><strong>SendSignalLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="2ea53-238"><strong>SendSignalLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="2ea53-239">int</span><span class="sxs-lookup"><span data-stu-id="2ea53-239">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2ea53-240">Уровень сигнала, отправленный на канале 1.</span><span class="sxs-lookup"><span data-stu-id="2ea53-240">Signal level as sent on channel 1.</span></span></p>
<p><span data-ttu-id="2ea53-241">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2ea53-241">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ea53-242"><strong>SendSignalLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="2ea53-242"><strong>SendSignalLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="2ea53-243">int</span><span class="sxs-lookup"><span data-stu-id="2ea53-243">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2ea53-244">Уровень сигнала, отправленный по каналу 2.</span><span class="sxs-lookup"><span data-stu-id="2ea53-244">Signal level as sent on channel 2.</span></span></p>
<p><span data-ttu-id="2ea53-245">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2ea53-245">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ea53-246"><strong>SendNoiseLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="2ea53-246"><strong>SendNoiseLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="2ea53-247">int</span><span class="sxs-lookup"><span data-stu-id="2ea53-247">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2ea53-248">Уровень шума, отправленный на канале 1.</span><span class="sxs-lookup"><span data-stu-id="2ea53-248">Noise level as sent on channel 1.</span></span></p>
<p><span data-ttu-id="2ea53-249">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2ea53-249">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ea53-250"><strong>SendNoiseLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="2ea53-250"><strong>SendNoiseLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="2ea53-251">int</span><span class="sxs-lookup"><span data-stu-id="2ea53-251">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2ea53-252">Уровень шума, отправленный по каналу 2.</span><span class="sxs-lookup"><span data-stu-id="2ea53-252">Noise level as sent on channel 2.</span></span></p>
<p><span data-ttu-id="2ea53-253">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2ea53-253">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

