---
title: 'Lync Server 2013: таблица AudioClientEvent'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: AudioClientEvent table
ms:assetid: fef73d8f-7261-4e5b-9769-82435b007979
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413086(v=OCS.15)
ms:contentKeyID: 48185967
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 44d5146b334af83618ca2dd6261a18e72708f4f5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722629"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audioclientevent-table-in-lync-server-2013"></a><span data-ttu-id="5a3e0-102">Таблица AudioClientEvent в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5a3e0-102">AudioClientEvent table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5a3e0-103">_**Тема последнего изменения:** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="5a3e0-103">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="5a3e0-104">Каждая запись имеет событие клиента для одной конечной точки в голосовой видеозвонке.</span><span class="sxs-lookup"><span data-stu-id="5a3e0-104">Each record contains a client event for one endpoint in an audio call.</span></span> <span data-ttu-id="5a3e0-105">Обычно один звонок состоит из двух записей: одного для вызывающего и для вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="5a3e0-105">Usually, one call has two records, one for caller and one for callee.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5a3e0-106"><strong>Столбец</strong></span><span class="sxs-lookup"><span data-stu-id="5a3e0-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="5a3e0-107"><strong>Тип данных</strong></span><span class="sxs-lookup"><span data-stu-id="5a3e0-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="5a3e0-108"><strong>Ключ/индекс</strong></span><span class="sxs-lookup"><span data-stu-id="5a3e0-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="5a3e0-109"><strong>Сведения</strong></span><span class="sxs-lookup"><span data-stu-id="5a3e0-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5a3e0-110"><strong>конференцедатетиме</strong></span><span class="sxs-lookup"><span data-stu-id="5a3e0-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="5a3e0-111">datetime</span><span class="sxs-lookup"><span data-stu-id="5a3e0-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="5a3e0-112">Primary</span><span class="sxs-lookup"><span data-stu-id="5a3e0-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="5a3e0-113">На которую ссылается <a href="lync-server-2013-medialine-table.md">Таблица медиалине в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="5a3e0-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5a3e0-114"><strong>сессионсек</strong></span><span class="sxs-lookup"><span data-stu-id="5a3e0-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="5a3e0-115">целое</span><span class="sxs-lookup"><span data-stu-id="5a3e0-115">int</span></span></p></td>
<td><p><span data-ttu-id="5a3e0-116">Primary</span><span class="sxs-lookup"><span data-stu-id="5a3e0-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="5a3e0-117">На которую ссылается <a href="lync-server-2013-medialine-table.md">Таблица медиалине в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="5a3e0-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5a3e0-118"><strong>медиалинелабел</strong></span><span class="sxs-lookup"><span data-stu-id="5a3e0-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="5a3e0-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="5a3e0-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="5a3e0-120">Primary</span><span class="sxs-lookup"><span data-stu-id="5a3e0-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="5a3e0-121">На которую ссылается <a href="lync-server-2013-medialine-table.md">Таблица медиалине в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="5a3e0-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5a3e0-122"><strong>фромкаллер</strong></span><span class="sxs-lookup"><span data-stu-id="5a3e0-122"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="5a3e0-123">бит</span><span class="sxs-lookup"><span data-stu-id="5a3e0-123">bit</span></span></p></td>
<td><p><span data-ttu-id="5a3e0-124">Primary</span><span class="sxs-lookup"><span data-stu-id="5a3e0-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="5a3e0-125">0: данные вызывающего абонента</span><span class="sxs-lookup"><span data-stu-id="5a3e0-125">0: Callee’s data</span></span></p>
<p><span data-ttu-id="5a3e0-126">1: данные вызывающего абонента</span><span class="sxs-lookup"><span data-stu-id="5a3e0-126">1: Caller’s data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5a3e0-127"><strong>нетворксендкуалитевентратио</strong></span><span class="sxs-lookup"><span data-stu-id="5a3e0-127"><strong>NetworkSendQualityEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="5a3e0-128">десятичное число (5; 2)</span><span class="sxs-lookup"><span data-stu-id="5a3e0-128">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5a3e0-129">Процент сеанса, когда событие Нетворксендкуалити было инициировано для состояния "Bad".</span><span class="sxs-lookup"><span data-stu-id="5a3e0-129">Percentage of session the NetworkSendQuality event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="5a3e0-130">Качество сети в условиях нарушения или потери пакетов является серьезным и повлияет на качество отправляемого звука.</span><span class="sxs-lookup"><span data-stu-id="5a3e0-130">Network quality in terms of jitter or packet loss is severe and impacting the quality of audio being sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5a3e0-131"><strong>нетворкрецеивекуалитевентратио</strong></span><span class="sxs-lookup"><span data-stu-id="5a3e0-131"><strong>NetworkReceiveQualityEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="5a3e0-132">десятичное число (5; 2)</span><span class="sxs-lookup"><span data-stu-id="5a3e0-132">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5a3e0-133">Процент сеанса, когда событие Рецеивесендкуалити было инициировано для состояния "Bad".</span><span class="sxs-lookup"><span data-stu-id="5a3e0-133">Percentage of session the ReceiveSendQuality event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="5a3e0-134">Качество сети в условиях нарушения или потери пакетов является серьезным и повлияет на качество получаемого звука.</span><span class="sxs-lookup"><span data-stu-id="5a3e0-134">Network quality in terms of jitter or packet loss is severe and impacting the quality of audio being received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5a3e0-135"><strong>нетворкделайевентратио</strong></span><span class="sxs-lookup"><span data-stu-id="5a3e0-135"><strong>NetworkDelayEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="5a3e0-136">десятичное число (5; 2)</span><span class="sxs-lookup"><span data-stu-id="5a3e0-136">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5a3e0-137">Процент сеанса. событие задержки было инициировано для состояния "Bad".</span><span class="sxs-lookup"><span data-stu-id="5a3e0-137">Percentage of session the Delay event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="5a3e0-138">Задержка сети является серьезной и повлияет на работу, предотвращая интерактивную связь</span><span class="sxs-lookup"><span data-stu-id="5a3e0-138">Network latency is severe and impacting the experience by preventing interactive communication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5a3e0-139"><strong>нетворкбандвидсловевентратио</strong></span><span class="sxs-lookup"><span data-stu-id="5a3e0-139"><strong>NetworkBandwidthLowEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="5a3e0-140">десятичное число (5; 2)</span><span class="sxs-lookup"><span data-stu-id="5a3e0-140">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5a3e0-141">Процент сеанса, когда событие Ловбандвидс было инициировано для состояния "Bad".</span><span class="sxs-lookup"><span data-stu-id="5a3e0-141">Percentage of session the LowBandwidth event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="5a3e0-142">Доступная пропускная способность недостаточна для приемлемого голосового интерфейса.</span><span class="sxs-lookup"><span data-stu-id="5a3e0-142">The available bandwidth is insufficient for an acceptable voice experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5a3e0-143"><strong>кпуинсуффиЦиентевентратио</strong></span><span class="sxs-lookup"><span data-stu-id="5a3e0-143"><strong>CPUInsufficientEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="5a3e0-144">десятичное число (5; 2)</span><span class="sxs-lookup"><span data-stu-id="5a3e0-144">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5a3e0-145">Процент пропускной ошибки ЦП, недостаточный для состояния "Bad".</span><span class="sxs-lookup"><span data-stu-id="5a3e0-145">Percentage of session the insufficient CPU event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="5a3e0-146">Недостаточно циклов ЦП для обработки с текущими модальностей и используемыми приложениями.</span><span class="sxs-lookup"><span data-stu-id="5a3e0-146">There are insufficient CPU cycles for processing with the current modalities and applications in use.</span></span> <span data-ttu-id="5a3e0-147">Это приводит к искажениям канала звука.</span><span class="sxs-lookup"><span data-stu-id="5a3e0-147">This causes distortions with the audio channel.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5a3e0-148"><strong>девицехалфдуплексаецевентратио</strong></span><span class="sxs-lookup"><span data-stu-id="5a3e0-148"><strong>DeviceHalfDuplexAECEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="5a3e0-149">десятичное число (5; 2)</span><span class="sxs-lookup"><span data-stu-id="5a3e0-149">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5a3e0-150">Процент сеанса, когда событие Девицехалфдуплексаек было инициировано для состояния "Bad".</span><span class="sxs-lookup"><span data-stu-id="5a3e0-150">Percentage of session the DeviceHalfDuplexAEC event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="5a3e0-151">В целях предотвращения эхо-эха система вводит двухстороннюю двустороннюю печать.</span><span class="sxs-lookup"><span data-stu-id="5a3e0-151">In order to prevent echo, the system has enter half duplex.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5a3e0-152"><strong>девицерендернотфунктионинжевентратио</strong></span><span class="sxs-lookup"><span data-stu-id="5a3e0-152"><strong>DeviceRenderNotFunctioningEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="5a3e0-153">десятичное число (5; 2)</span><span class="sxs-lookup"><span data-stu-id="5a3e0-153">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5a3e0-154">Процент сеанса, когда событие Девицерендернотфунктионинг было инициировано для состояния "Bad".</span><span class="sxs-lookup"><span data-stu-id="5a3e0-154">Percentage of session the DeviceRenderNotFunctioning event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="5a3e0-155">Устройство рендеринга, используемое в данный момент для сеанса, работает неправильно.</span><span class="sxs-lookup"><span data-stu-id="5a3e0-155">The render device currently being used for the session is not functioning correctly.</span></span> <span data-ttu-id="5a3e0-156">Это может привести к появлению односторонней голосовой проблемы.</span><span class="sxs-lookup"><span data-stu-id="5a3e0-156">This can cause one-way audio issues.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5a3e0-157"><strong>девицекаптуренотфунктионинжевентратио</strong></span><span class="sxs-lookup"><span data-stu-id="5a3e0-157"><strong>DeviceCaptureNotFunctioningEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="5a3e0-158">десятичное число (5; 2)</span><span class="sxs-lookup"><span data-stu-id="5a3e0-158">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5a3e0-159">Процент сеанса, когда событие Девицекаптуренотфунктионинг было инициировано для состояния "Bad".</span><span class="sxs-lookup"><span data-stu-id="5a3e0-159">Percentage of session the DeviceCaptureNotFunctioning event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="5a3e0-160">Устройство захвата, используемое в сеансе, не работает должным образом.</span><span class="sxs-lookup"><span data-stu-id="5a3e0-160">The capture device currently being used for the session is not functioning correctly.</span></span> <span data-ttu-id="5a3e0-161">Это может привести к появлению односторонней голосовой проблемы.</span><span class="sxs-lookup"><span data-stu-id="5a3e0-161">This can cause one-way audio issues.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5a3e0-162"><strong>девицеглитчесевентратио</strong></span><span class="sxs-lookup"><span data-stu-id="5a3e0-162"><strong>DeviceGlitchesEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="5a3e0-163">десятичное число (5; 2)</span><span class="sxs-lookup"><span data-stu-id="5a3e0-163">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5a3e0-164">Процент сеанса, когда событие Девицеглитчес было инициировано для состояния "Bad".</span><span class="sxs-lookup"><span data-stu-id="5a3e0-164">Percentage of session the DeviceGlitches event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="5a3e0-165">При отрисовке звука возникают серьезные проблемы, вызывающие искажения.</span><span class="sxs-lookup"><span data-stu-id="5a3e0-165">There are severe glitches in the rendering of audio which is causing distortions.</span></span> <span data-ttu-id="5a3e0-166">Это может быть вызвано проблемами с драйверами, отложенными вызовами процедур (DPC) (Drivers) и высокой загрузкой ЦП.</span><span class="sxs-lookup"><span data-stu-id="5a3e0-166">These glitches can be caused by driver issues, deferred procedure calls (DPC) storm (drivers), and high CPU usage.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5a3e0-167"><strong>девицеловснревентратио</strong></span><span class="sxs-lookup"><span data-stu-id="5a3e0-167"><strong>DeviceLowSNREventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="5a3e0-168">десятичное число (5; 2)</span><span class="sxs-lookup"><span data-stu-id="5a3e0-168">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5a3e0-169">Процент сеанса, когда событие Девицеловснр было инициировано для состояния "Bad".</span><span class="sxs-lookup"><span data-stu-id="5a3e0-169">Percentage of session the DeviceLowSNR event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="5a3e0-170">Качество захвата очень низкое, но очень шумный или пользовательский разговор слишком далеко от микрофона.</span><span class="sxs-lookup"><span data-stu-id="5a3e0-170">The capture quality is very poor, either very noisy or user is talking too far away from the microphone.</span></span> <span data-ttu-id="5a3e0-171">Это вызовет искажения.</span><span class="sxs-lookup"><span data-stu-id="5a3e0-171">This will cause distortions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5a3e0-172"><strong>девицеловспичлевелевентратио</strong></span><span class="sxs-lookup"><span data-stu-id="5a3e0-172"><strong>DeviceLowSpeechLevelEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="5a3e0-173">десятичное число (5; 2)</span><span class="sxs-lookup"><span data-stu-id="5a3e0-173">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5a3e0-174">Процент сеанса, когда событие Девицеловспичлевел было инициировано для состояния "Bad".</span><span class="sxs-lookup"><span data-stu-id="5a3e0-174">Percentage of session the DeviceLowSpeechLevel event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="5a3e0-175">Слишком низкий уровень речи пользователя, система не может увеличить его.</span><span class="sxs-lookup"><span data-stu-id="5a3e0-175">User‘s speech level is too low and the system cannot increase it any further.</span></span> <span data-ttu-id="5a3e0-176">Это может вызвать либо искажение или восприятие в качестве односторонней голосовой.</span><span class="sxs-lookup"><span data-stu-id="5a3e0-176">This can either cause distortions or perceived as one-way audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5a3e0-177"><strong>девицеклиппинжевентратио</strong></span><span class="sxs-lookup"><span data-stu-id="5a3e0-177"><strong>DeviceClippingEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="5a3e0-178">Десятичное число (5; 2)</span><span class="sxs-lookup"><span data-stu-id="5a3e0-178">Decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5a3e0-179">Процент сеанса, когда событие Девицеклиппинг было инициировано для состояния "Bad".</span><span class="sxs-lookup"><span data-stu-id="5a3e0-179">Percentage of session the DeviceClipping event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="5a3e0-180">При использовании близких между собой видеороликов микрофон прозвучит искажения из-за обрезки.</span><span class="sxs-lookup"><span data-stu-id="5a3e0-180">When near-end speech clips the microphone, far-end hears distortion due to clipping.</span></span> <span data-ttu-id="5a3e0-181">Важно избегать вырезки близких микрофонов.</span><span class="sxs-lookup"><span data-stu-id="5a3e0-181">It is important to avoid near-end microphone clipping.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5a3e0-182"><strong>девицеечоевентратио</strong></span><span class="sxs-lookup"><span data-stu-id="5a3e0-182"><strong>DeviceEchoEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="5a3e0-183">десятичное число (5; 2)</span><span class="sxs-lookup"><span data-stu-id="5a3e0-183">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5a3e0-184">Процент сеанса, когда событие Девицеечоевент было инициировано для состояния "Bad".</span><span class="sxs-lookup"><span data-stu-id="5a3e0-184">Percentage of session the DeviceEchoEvent event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="5a3e0-185">Устройство или Настройка вызывают эхо за пределами способности системы компенсировать.</span><span class="sxs-lookup"><span data-stu-id="5a3e0-185">Device or setup is causing echo beyond the ability of the system to compensate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5a3e0-186"><strong>девиценеарендтоечоратиоевентратио</strong></span><span class="sxs-lookup"><span data-stu-id="5a3e0-186"><strong>DeviceNearEndToEchoRatioEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="5a3e0-187">десятичное число (5; 2)</span><span class="sxs-lookup"><span data-stu-id="5a3e0-187">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5a3e0-188">Процент сеанса, когда событие Девиценеарендтоечоратио было инициировано для состояния "Bad".</span><span class="sxs-lookup"><span data-stu-id="5a3e0-188">Percentage of session the DeviceNearEndToEchoRatio event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="5a3e0-189">Голосовая речь пользователя слишком мала по сравнению с записанным эхо-эффектом, что влияет на работу пользователей, так как оно ограничивает возможности прерывания пользователя.</span><span class="sxs-lookup"><span data-stu-id="5a3e0-189">The user’s speech is too low compared to the echo being captured which impacts the users experience because it limits how easy it is to interrupt a user.</span></span> <span data-ttu-id="5a3e0-190">Уменьшить громкость динамика, передвиньте микрофон ближе к разговору.</span><span class="sxs-lookup"><span data-stu-id="5a3e0-190">Reduce speaker volume, move the microphone closer to the talker.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5a3e0-191"><strong>девицемултиплиндпоинтсевенткаунт</strong></span><span class="sxs-lookup"><span data-stu-id="5a3e0-191"><strong>DeviceMultipleEndpointsEventCount</strong></span></span></p></td>
<td><p><span data-ttu-id="5a3e0-192">целое</span><span class="sxs-lookup"><span data-stu-id="5a3e0-192">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5a3e0-193">Количество ситуаций, в которых событие Девицемултиплиндпоинтс было инициировано для состояния "Bad".</span><span class="sxs-lookup"><span data-stu-id="5a3e0-193">Number of times during session the DeviceMultipleEndpoints event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="5a3e0-194">Обнаружено несколько конечных точек звука в одном сеансе и компенсация системы была произведена с помощью уменьшения объема рендеринга.</span><span class="sxs-lookup"><span data-stu-id="5a3e0-194">Multiple audio endpoints in the same session detected and the system has compensated by reducing render volume.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5a3e0-195"><strong>девицеховлинжевенткаунт</strong></span><span class="sxs-lookup"><span data-stu-id="5a3e0-195"><strong>DeviceHowlingEventCount</strong></span></span></p></td>
<td><p><span data-ttu-id="5a3e0-196">целое</span><span class="sxs-lookup"><span data-stu-id="5a3e0-196">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5a3e0-197">Количество ситуаций, в которых событие Девицеховлинжевент было инициировано для состояния "Bad".</span><span class="sxs-lookup"><span data-stu-id="5a3e0-197">Number of times during session the DeviceHowlingEvent event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="5a3e0-198">Обнаружен цикл обратной связи (это связано с тем, что несколько конечных точек совместно поддерживают звуковой путь).</span><span class="sxs-lookup"><span data-stu-id="5a3e0-198">Audio feedback loop detected (caused by multiple endpoints sharing audio path).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5a3e0-199"><strong>девицерендерзероволумивентратио</strong></span><span class="sxs-lookup"><span data-stu-id="5a3e0-199"><strong>DeviceRenderZeroVolumeEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="5a3e0-200">десятичное число (5; 2)</span><span class="sxs-lookup"><span data-stu-id="5a3e0-200">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5a3e0-201">Процент сеанса. событие Девицерендерзероволуме было инициировано в состоянии Bad.</span><span class="sxs-lookup"><span data-stu-id="5a3e0-201">Percentage of session the DeviceRenderZeroVolume event was fired for being in the “Bad’ state.</span></span> <span data-ttu-id="5a3e0-202">Для устройства обработки было установлено нулевое значение "Громкость".</span><span class="sxs-lookup"><span data-stu-id="5a3e0-202">The render device was set to zero volume.</span></span></p>
<p><span data-ttu-id="5a3e0-203">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5a3e0-203">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5a3e0-204"><strong>девицерендермутивентратио</strong></span><span class="sxs-lookup"><span data-stu-id="5a3e0-204"><strong>DeviceRenderMuteEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="5a3e0-205">десятичное число (5; 2)</span><span class="sxs-lookup"><span data-stu-id="5a3e0-205">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5a3e0-206">Процент сеанса. событие Девицерендермуте было инициировано в состоянии Bad.</span><span class="sxs-lookup"><span data-stu-id="5a3e0-206">Percentage of session the DeviceRenderMute event was fired for being in the “Bad’ state.</span></span> <span data-ttu-id="5a3e0-207">Устройство рендеринга отключено.</span><span class="sxs-lookup"><span data-stu-id="5a3e0-207">The render device was muted.</span></span></p>
<p><span data-ttu-id="5a3e0-208">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5a3e0-208">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

