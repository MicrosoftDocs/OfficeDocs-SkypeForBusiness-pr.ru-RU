---
title: 'Lync Server 2013: таблица AudioClientEvent'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: AudioClientEvent table
ms:assetid: fef73d8f-7261-4e5b-9769-82435b007979
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413086(v=OCS.15)
ms:contentKeyID: 48185967
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 489777458838d5e77df1f8c82ed6ab8b6c295832
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841904"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audioclientevent-table-in-lync-server-2013"></a><span data-ttu-id="e1b2a-102">Таблица AudioClientEvent в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e1b2a-102">AudioClientEvent table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e1b2a-103">_**Тема последнего изменения:** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="e1b2a-103">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="e1b2a-104">Каждая запись имеет событие клиента для одной конечной точки в голосовой видеозвонке.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-104">Each record contains a client event for one endpoint in an audio call.</span></span> <span data-ttu-id="e1b2a-105">Обычно один звонок состоит из двух записей: одного для вызывающего и для вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-105">Usually, one call has two records, one for caller and one for callee.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e1b2a-106"><strong>Столбец</strong></span><span class="sxs-lookup"><span data-stu-id="e1b2a-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="e1b2a-107"><strong>Тип данных</strong></span><span class="sxs-lookup"><span data-stu-id="e1b2a-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="e1b2a-108"><strong>Ключ/индекс</strong></span><span class="sxs-lookup"><span data-stu-id="e1b2a-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="e1b2a-109"><strong>Сведения</strong></span><span class="sxs-lookup"><span data-stu-id="e1b2a-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e1b2a-110"><strong>Конференцедатетиме</strong></span><span class="sxs-lookup"><span data-stu-id="e1b2a-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e1b2a-111">datetime</span><span class="sxs-lookup"><span data-stu-id="e1b2a-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="e1b2a-112">Primary</span><span class="sxs-lookup"><span data-stu-id="e1b2a-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="e1b2a-113">На которую ссылается <a href="lync-server-2013-medialine-table.md">Таблица медиалине в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e1b2a-114"><strong>Сессионсек</strong></span><span class="sxs-lookup"><span data-stu-id="e1b2a-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="e1b2a-115">целое</span><span class="sxs-lookup"><span data-stu-id="e1b2a-115">int</span></span></p></td>
<td><p><span data-ttu-id="e1b2a-116">Primary</span><span class="sxs-lookup"><span data-stu-id="e1b2a-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="e1b2a-117">На которую ссылается <a href="lync-server-2013-medialine-table.md">Таблица медиалине в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e1b2a-118"><strong>Медиалинелабел</strong></span><span class="sxs-lookup"><span data-stu-id="e1b2a-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="e1b2a-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="e1b2a-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="e1b2a-120">Primary</span><span class="sxs-lookup"><span data-stu-id="e1b2a-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="e1b2a-121">На которую ссылается <a href="lync-server-2013-medialine-table.md">Таблица медиалине в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e1b2a-122"><strong>Фромкаллер</strong></span><span class="sxs-lookup"><span data-stu-id="e1b2a-122"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="e1b2a-123">бит</span><span class="sxs-lookup"><span data-stu-id="e1b2a-123">bit</span></span></p></td>
<td><p><span data-ttu-id="e1b2a-124">Primary</span><span class="sxs-lookup"><span data-stu-id="e1b2a-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="e1b2a-125">0: данные вызывающего абонента</span><span class="sxs-lookup"><span data-stu-id="e1b2a-125">0: Callee’s data</span></span></p>
<p><span data-ttu-id="e1b2a-126">1: данные вызывающего абонента</span><span class="sxs-lookup"><span data-stu-id="e1b2a-126">1: Caller’s data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e1b2a-127"><strong>Нетворксендкуалитевентратио</strong></span><span class="sxs-lookup"><span data-stu-id="e1b2a-127"><strong>NetworkSendQualityEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="e1b2a-128">десятичное число (5; 2)</span><span class="sxs-lookup"><span data-stu-id="e1b2a-128">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e1b2a-129">Процент сеанса, когда событие Нетворксендкуалити было инициировано для состояния "Bad".</span><span class="sxs-lookup"><span data-stu-id="e1b2a-129">Percentage of session the NetworkSendQuality event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="e1b2a-130">Качество сети в условиях нарушения или потери пакетов является серьезным и повлияет на качество отправляемого звука.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-130">Network quality in terms of jitter or packet loss is severe and impacting the quality of audio being sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e1b2a-131"><strong>Нетворкрецеивекуалитевентратио</strong></span><span class="sxs-lookup"><span data-stu-id="e1b2a-131"><strong>NetworkReceiveQualityEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="e1b2a-132">десятичное число (5; 2)</span><span class="sxs-lookup"><span data-stu-id="e1b2a-132">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e1b2a-133">Процент сеанса, когда событие Рецеивесендкуалити было инициировано для состояния "Bad".</span><span class="sxs-lookup"><span data-stu-id="e1b2a-133">Percentage of session the ReceiveSendQuality event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="e1b2a-134">Качество сети в условиях нарушения или потери пакетов является серьезным и повлияет на качество получаемого звука.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-134">Network quality in terms of jitter or packet loss is severe and impacting the quality of audio being received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e1b2a-135"><strong>Нетворкделайевентратио</strong></span><span class="sxs-lookup"><span data-stu-id="e1b2a-135"><strong>NetworkDelayEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="e1b2a-136">десятичное число (5; 2)</span><span class="sxs-lookup"><span data-stu-id="e1b2a-136">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e1b2a-137">Процент сеанса. событие задержки было инициировано для состояния "Bad".</span><span class="sxs-lookup"><span data-stu-id="e1b2a-137">Percentage of session the Delay event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="e1b2a-138">Задержка сети является серьезной и повлияет на работу, предотвращая интерактивную связь</span><span class="sxs-lookup"><span data-stu-id="e1b2a-138">Network latency is severe and impacting the experience by preventing interactive communication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e1b2a-139"><strong>Нетворкбандвидсловевентратио</strong></span><span class="sxs-lookup"><span data-stu-id="e1b2a-139"><strong>NetworkBandwidthLowEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="e1b2a-140">десятичное число (5; 2)</span><span class="sxs-lookup"><span data-stu-id="e1b2a-140">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e1b2a-141">Процент сеанса, когда событие Ловбандвидс было инициировано для состояния "Bad".</span><span class="sxs-lookup"><span data-stu-id="e1b2a-141">Percentage of session the LowBandwidth event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="e1b2a-142">Доступная пропускная способность недостаточна для приемлемого голосового интерфейса.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-142">The available bandwidth is insufficient for an acceptable voice experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e1b2a-143"><strong>КпуинсуффиЦиентевентратио</strong></span><span class="sxs-lookup"><span data-stu-id="e1b2a-143"><strong>CPUInsufficientEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="e1b2a-144">десятичное число (5; 2)</span><span class="sxs-lookup"><span data-stu-id="e1b2a-144">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e1b2a-145">Процент пропускной ошибки ЦП, недостаточный для состояния "Bad".</span><span class="sxs-lookup"><span data-stu-id="e1b2a-145">Percentage of session the insufficient CPU event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="e1b2a-146">Недостаточно циклов ЦП для обработки с текущими модальностей и используемыми приложениями.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-146">There are insufficient CPU cycles for processing with the current modalities and applications in use.</span></span> <span data-ttu-id="e1b2a-147">Это приводит к искажениям канала звука.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-147">This causes distortions with the audio channel.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e1b2a-148"><strong>Девицехалфдуплексаецевентратио</strong></span><span class="sxs-lookup"><span data-stu-id="e1b2a-148"><strong>DeviceHalfDuplexAECEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="e1b2a-149">десятичное число (5; 2)</span><span class="sxs-lookup"><span data-stu-id="e1b2a-149">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e1b2a-150">Процент сеанса, когда событие Девицехалфдуплексаек было инициировано для состояния "Bad".</span><span class="sxs-lookup"><span data-stu-id="e1b2a-150">Percentage of session the DeviceHalfDuplexAEC event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="e1b2a-151">В целях предотвращения эхо-эха система вводит двухстороннюю двустороннюю печать.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-151">In order to prevent echo, the system has enter half duplex.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e1b2a-152"><strong>Девицерендернотфунктионинжевентратио</strong></span><span class="sxs-lookup"><span data-stu-id="e1b2a-152"><strong>DeviceRenderNotFunctioningEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="e1b2a-153">десятичное число (5; 2)</span><span class="sxs-lookup"><span data-stu-id="e1b2a-153">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e1b2a-154">Процент сеанса, когда событие Девицерендернотфунктионинг было инициировано для состояния "Bad".</span><span class="sxs-lookup"><span data-stu-id="e1b2a-154">Percentage of session the DeviceRenderNotFunctioning event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="e1b2a-155">Устройство рендеринга, используемое в данный момент для сеанса, работает неправильно.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-155">The render device currently being used for the session is not functioning correctly.</span></span> <span data-ttu-id="e1b2a-156">Это может привести к появлению односторонней голосовой проблемы.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-156">This can cause one-way audio issues.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e1b2a-157"><strong>Девицекаптуренотфунктионинжевентратио</strong></span><span class="sxs-lookup"><span data-stu-id="e1b2a-157"><strong>DeviceCaptureNotFunctioningEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="e1b2a-158">десятичное число (5; 2)</span><span class="sxs-lookup"><span data-stu-id="e1b2a-158">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e1b2a-159">Процент сеанса, когда событие Девицекаптуренотфунктионинг было инициировано для состояния "Bad".</span><span class="sxs-lookup"><span data-stu-id="e1b2a-159">Percentage of session the DeviceCaptureNotFunctioning event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="e1b2a-160">Устройство захвата, используемое в сеансе, не работает должным образом.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-160">The capture device currently being used for the session is not functioning correctly.</span></span> <span data-ttu-id="e1b2a-161">Это может привести к появлению односторонней голосовой проблемы.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-161">This can cause one-way audio issues.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e1b2a-162"><strong>Девицеглитчесевентратио</strong></span><span class="sxs-lookup"><span data-stu-id="e1b2a-162"><strong>DeviceGlitchesEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="e1b2a-163">десятичное число (5; 2)</span><span class="sxs-lookup"><span data-stu-id="e1b2a-163">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e1b2a-164">Процент сеанса, когда событие Девицеглитчес было инициировано для состояния "Bad".</span><span class="sxs-lookup"><span data-stu-id="e1b2a-164">Percentage of session the DeviceGlitches event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="e1b2a-165">При отрисовке звука возникают серьезные проблемы, вызывающие искажения.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-165">There are severe glitches in the rendering of audio which is causing distortions.</span></span> <span data-ttu-id="e1b2a-166">Это может быть вызвано проблемами с драйверами, отложенными вызовами процедур (DPC) (Drivers) и высокой загрузкой ЦП.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-166">These glitches can be caused by driver issues, deferred procedure calls (DPC) storm (drivers), and high CPU usage.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e1b2a-167"><strong>Девицеловснревентратио</strong></span><span class="sxs-lookup"><span data-stu-id="e1b2a-167"><strong>DeviceLowSNREventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="e1b2a-168">десятичное число (5; 2)</span><span class="sxs-lookup"><span data-stu-id="e1b2a-168">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e1b2a-169">Процент сеанса, когда событие Девицеловснр было инициировано для состояния "Bad".</span><span class="sxs-lookup"><span data-stu-id="e1b2a-169">Percentage of session the DeviceLowSNR event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="e1b2a-170">Качество захвата очень низкое, но очень шумный или пользовательский разговор слишком далеко от микрофона.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-170">The capture quality is very poor, either very noisy or user is talking too far away from the microphone.</span></span> <span data-ttu-id="e1b2a-171">Это вызовет искажения.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-171">This will cause distortions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e1b2a-172"><strong>Девицеловспичлевелевентратио</strong></span><span class="sxs-lookup"><span data-stu-id="e1b2a-172"><strong>DeviceLowSpeechLevelEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="e1b2a-173">десятичное число (5; 2)</span><span class="sxs-lookup"><span data-stu-id="e1b2a-173">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e1b2a-174">Процент сеанса, когда событие Девицеловспичлевел было инициировано для состояния "Bad".</span><span class="sxs-lookup"><span data-stu-id="e1b2a-174">Percentage of session the DeviceLowSpeechLevel event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="e1b2a-175">Слишком низкий уровень речи пользователя, система не может увеличить его.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-175">User‘s speech level is too low and the system cannot increase it any further.</span></span> <span data-ttu-id="e1b2a-176">Это может вызвать либо искажение или восприятие в качестве односторонней голосовой.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-176">This can either cause distortions or perceived as one-way audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e1b2a-177"><strong>Девицеклиппинжевентратио</strong></span><span class="sxs-lookup"><span data-stu-id="e1b2a-177"><strong>DeviceClippingEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="e1b2a-178">Десятичное число (5; 2)</span><span class="sxs-lookup"><span data-stu-id="e1b2a-178">Decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e1b2a-179">Процент сеанса, когда событие Девицеклиппинг было инициировано для состояния "Bad".</span><span class="sxs-lookup"><span data-stu-id="e1b2a-179">Percentage of session the DeviceClipping event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="e1b2a-180">При использовании близких между собой видеороликов микрофон прозвучит искажения из-за обрезки.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-180">When near-end speech clips the microphone, far-end hears distortion due to clipping.</span></span> <span data-ttu-id="e1b2a-181">Важно избегать вырезки близких микрофонов.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-181">It is important to avoid near-end microphone clipping.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e1b2a-182"><strong>Девицеечоевентратио</strong></span><span class="sxs-lookup"><span data-stu-id="e1b2a-182"><strong>DeviceEchoEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="e1b2a-183">десятичное число (5; 2)</span><span class="sxs-lookup"><span data-stu-id="e1b2a-183">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e1b2a-184">Процент сеанса, когда событие Девицеечоевент было инициировано для состояния "Bad".</span><span class="sxs-lookup"><span data-stu-id="e1b2a-184">Percentage of session the DeviceEchoEvent event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="e1b2a-185">Устройство или Настройка вызывают эхо за пределами способности системы компенсировать.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-185">Device or setup is causing echo beyond the ability of the system to compensate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e1b2a-186"><strong>Девиценеарендтоечоратиоевентратио</strong></span><span class="sxs-lookup"><span data-stu-id="e1b2a-186"><strong>DeviceNearEndToEchoRatioEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="e1b2a-187">десятичное число (5; 2)</span><span class="sxs-lookup"><span data-stu-id="e1b2a-187">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e1b2a-188">Процент сеанса, когда событие Девиценеарендтоечоратио было инициировано для состояния "Bad".</span><span class="sxs-lookup"><span data-stu-id="e1b2a-188">Percentage of session the DeviceNearEndToEchoRatio event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="e1b2a-189">Голосовая речь пользователя слишком мала по сравнению с записанным эхо-эффектом, что влияет на работу пользователей, так как оно ограничивает возможности прерывания пользователя.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-189">The user’s speech is too low compared to the echo being captured which impacts the users experience because it limits how easy it is to interrupt a user.</span></span> <span data-ttu-id="e1b2a-190">Уменьшить громкость динамика, передвиньте микрофон ближе к разговору.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-190">Reduce speaker volume, move the microphone closer to the talker.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e1b2a-191"><strong>Девицемултиплиндпоинтсевенткаунт</strong></span><span class="sxs-lookup"><span data-stu-id="e1b2a-191"><strong>DeviceMultipleEndpointsEventCount</strong></span></span></p></td>
<td><p><span data-ttu-id="e1b2a-192">целое</span><span class="sxs-lookup"><span data-stu-id="e1b2a-192">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e1b2a-193">Количество ситуаций, в которых событие Девицемултиплиндпоинтс было инициировано для состояния "Bad".</span><span class="sxs-lookup"><span data-stu-id="e1b2a-193">Number of times during session the DeviceMultipleEndpoints event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="e1b2a-194">Обнаружено несколько конечных точек звука в одном сеансе и компенсация системы была произведена с помощью уменьшения объема рендеринга.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-194">Multiple audio endpoints in the same session detected and the system has compensated by reducing render volume.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e1b2a-195"><strong>Девицеховлинжевенткаунт</strong></span><span class="sxs-lookup"><span data-stu-id="e1b2a-195"><strong>DeviceHowlingEventCount</strong></span></span></p></td>
<td><p><span data-ttu-id="e1b2a-196">целое</span><span class="sxs-lookup"><span data-stu-id="e1b2a-196">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e1b2a-197">Количество ситуаций, в которых событие Девицеховлинжевент было инициировано для состояния "Bad".</span><span class="sxs-lookup"><span data-stu-id="e1b2a-197">Number of times during session the DeviceHowlingEvent event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="e1b2a-198">Обнаружен цикл обратной связи (это связано с тем, что несколько конечных точек совместно поддерживают звуковой путь).</span><span class="sxs-lookup"><span data-stu-id="e1b2a-198">Audio feedback loop detected (caused by multiple endpoints sharing audio path).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e1b2a-199"><strong>Девицерендерзероволумивентратио</strong></span><span class="sxs-lookup"><span data-stu-id="e1b2a-199"><strong>DeviceRenderZeroVolumeEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="e1b2a-200">десятичное число (5; 2)</span><span class="sxs-lookup"><span data-stu-id="e1b2a-200">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e1b2a-201">Процент сеанса. событие Девицерендерзероволуме было инициировано в состоянии Bad.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-201">Percentage of session the DeviceRenderZeroVolume event was fired for being in the “Bad’ state.</span></span> <span data-ttu-id="e1b2a-202">Для устройства обработки было установлено нулевое значение "Громкость".</span><span class="sxs-lookup"><span data-stu-id="e1b2a-202">The render device was set to zero volume.</span></span></p>
<p><span data-ttu-id="e1b2a-203">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-203">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e1b2a-204"><strong>Девицерендермутивентратио</strong></span><span class="sxs-lookup"><span data-stu-id="e1b2a-204"><strong>DeviceRenderMuteEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="e1b2a-205">десятичное число (5; 2)</span><span class="sxs-lookup"><span data-stu-id="e1b2a-205">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e1b2a-206">Процент сеанса. событие Девицерендермуте было инициировано в состоянии Bad.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-206">Percentage of session the DeviceRenderMute event was fired for being in the “Bad’ state.</span></span> <span data-ttu-id="e1b2a-207">Устройство рендеринга отключено.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-207">The render device was muted.</span></span></p>
<p><span data-ttu-id="e1b2a-208">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-208">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

