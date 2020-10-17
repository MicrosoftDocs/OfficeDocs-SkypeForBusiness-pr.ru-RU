---
title: 'Lync Server 2013: таблица таблица audioclientevent'
description: 'Lync Server 2013: таблица таблица audioclientevent.'
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
ms.openlocfilehash: 2200cd9567bdd10ac4ad8f5c269062c2f5614dcb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568785"
---
# <a name="audioclientevent-table-in-lync-server-2013"></a><span data-ttu-id="eed9c-103">Таблица Таблица audioclientevent в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eed9c-103">AudioClientEvent table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eed9c-104">_**Последнее изменение темы:** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="eed9c-104">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="eed9c-105">Каждая запись содержит клиентское событие для одной конечной точки в голосовой вызове.</span><span class="sxs-lookup"><span data-stu-id="eed9c-105">Each record contains a client event for one endpoint in an audio call.</span></span> <span data-ttu-id="eed9c-106">Как правило, один вызов состоит из двух записей, один для вызывающего абонента и один для вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="eed9c-106">Usually, one call has two records, one for caller and one for callee.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="eed9c-107"><strong>Column</strong></span><span class="sxs-lookup"><span data-stu-id="eed9c-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="eed9c-108"><strong>Тип данных</strong></span><span class="sxs-lookup"><span data-stu-id="eed9c-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="eed9c-109"><strong>Ключ или индекс</strong></span><span class="sxs-lookup"><span data-stu-id="eed9c-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="eed9c-110"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="eed9c-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="eed9c-111"><strong>конференцедатетиме</strong></span><span class="sxs-lookup"><span data-stu-id="eed9c-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="eed9c-112">datetime</span><span class="sxs-lookup"><span data-stu-id="eed9c-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="eed9c-113">Primary</span><span class="sxs-lookup"><span data-stu-id="eed9c-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="eed9c-114">Ссылка из <a href="lync-server-2013-medialine-table.md">таблицы MediaLine в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="eed9c-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eed9c-115"><strong>сессионсек</strong></span><span class="sxs-lookup"><span data-stu-id="eed9c-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="eed9c-116">int</span><span class="sxs-lookup"><span data-stu-id="eed9c-116">int</span></span></p></td>
<td><p><span data-ttu-id="eed9c-117">Primary</span><span class="sxs-lookup"><span data-stu-id="eed9c-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="eed9c-118">Ссылка из <a href="lync-server-2013-medialine-table.md">таблицы MediaLine в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="eed9c-118">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eed9c-119"><strong>медиалинелабел</strong></span><span class="sxs-lookup"><span data-stu-id="eed9c-119"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="eed9c-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="eed9c-120">tinyint</span></span></p></td>
<td><p><span data-ttu-id="eed9c-121">Primary</span><span class="sxs-lookup"><span data-stu-id="eed9c-121">Primary</span></span></p></td>
<td><p><span data-ttu-id="eed9c-122">Ссылка из <a href="lync-server-2013-medialine-table.md">таблицы MediaLine в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="eed9c-122">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eed9c-123"><strong>фромкаллер</strong></span><span class="sxs-lookup"><span data-stu-id="eed9c-123"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="eed9c-124">Битовая</span><span class="sxs-lookup"><span data-stu-id="eed9c-124">bit</span></span></p></td>
<td><p><span data-ttu-id="eed9c-125">Primary</span><span class="sxs-lookup"><span data-stu-id="eed9c-125">Primary</span></span></p></td>
<td><p><span data-ttu-id="eed9c-126">0: данные вызываемого абонента</span><span class="sxs-lookup"><span data-stu-id="eed9c-126">0: Callee’s data</span></span></p>
<p><span data-ttu-id="eed9c-127">1: данные вызывающего абонента</span><span class="sxs-lookup"><span data-stu-id="eed9c-127">1: Caller’s data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eed9c-128"><strong>нетворксендкуалитевентратио</strong></span><span class="sxs-lookup"><span data-stu-id="eed9c-128"><strong>NetworkSendQualityEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="eed9c-129">десятичное число (5, 2)</span><span class="sxs-lookup"><span data-stu-id="eed9c-129">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="eed9c-130">Процентное отношение сеанса событие Нетворксендкуалити было вызвано для состояния "плохое".</span><span class="sxs-lookup"><span data-stu-id="eed9c-130">Percentage of session the NetworkSendQuality event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="eed9c-131">Качество сети в терминах нарушения или потери пакетов серьезно и влияет на качество отправляемого звука.</span><span class="sxs-lookup"><span data-stu-id="eed9c-131">Network quality in terms of jitter or packet loss is severe and impacting the quality of audio being sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eed9c-132"><strong>нетворкрецеивекуалитевентратио</strong></span><span class="sxs-lookup"><span data-stu-id="eed9c-132"><strong>NetworkReceiveQualityEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="eed9c-133">десятичное число (5, 2)</span><span class="sxs-lookup"><span data-stu-id="eed9c-133">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="eed9c-134">Процентное отношение сеанса событие Рецеивесендкуалити было вызвано для состояния "плохое".</span><span class="sxs-lookup"><span data-stu-id="eed9c-134">Percentage of session the ReceiveSendQuality event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="eed9c-135">Качество сети в терминах нарушения или потери пакетов серьезно и влияет на качество получаемого звука.</span><span class="sxs-lookup"><span data-stu-id="eed9c-135">Network quality in terms of jitter or packet loss is severe and impacting the quality of audio being received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eed9c-136"><strong>нетворкделайевентратио</strong></span><span class="sxs-lookup"><span data-stu-id="eed9c-136"><strong>NetworkDelayEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="eed9c-137">десятичное число (5, 2)</span><span class="sxs-lookup"><span data-stu-id="eed9c-137">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="eed9c-138">Процентное соотношение между сеансами событие Delay было вызвано для состояния "плохое".</span><span class="sxs-lookup"><span data-stu-id="eed9c-138">Percentage of session the Delay event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="eed9c-139">Задержка в сети серьезна и повлияет на работу, предотвращая интерактивную связь</span><span class="sxs-lookup"><span data-stu-id="eed9c-139">Network latency is severe and impacting the experience by preventing interactive communication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eed9c-140"><strong>нетворкбандвидсловевентратио</strong></span><span class="sxs-lookup"><span data-stu-id="eed9c-140"><strong>NetworkBandwidthLowEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="eed9c-141">десятичное число (5, 2)</span><span class="sxs-lookup"><span data-stu-id="eed9c-141">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="eed9c-142">Процентное отношение сеанса событие Ловбандвидс было вызвано для состояния "плохое".</span><span class="sxs-lookup"><span data-stu-id="eed9c-142">Percentage of session the LowBandwidth event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="eed9c-143">Доступная полоса пропускания недостаточна для приемлемого голосового интерфейса.</span><span class="sxs-lookup"><span data-stu-id="eed9c-143">The available bandwidth is insufficient for an acceptable voice experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eed9c-144"><strong>кпуинсуффиЦиентевентратио</strong></span><span class="sxs-lookup"><span data-stu-id="eed9c-144"><strong>CPUInsufficientEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="eed9c-145">десятичное число (5, 2)</span><span class="sxs-lookup"><span data-stu-id="eed9c-145">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="eed9c-146">Процентное соотношение от сеанса, которое было вызвано недостаточным событием ЦП для состояния "Bad".</span><span class="sxs-lookup"><span data-stu-id="eed9c-146">Percentage of session the insufficient CPU event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="eed9c-147">Недостаточно циклов ЦП для обработки с текущими модальности и используемыми приложениями.</span><span class="sxs-lookup"><span data-stu-id="eed9c-147">There are insufficient CPU cycles for processing with the current modalities and applications in use.</span></span> <span data-ttu-id="eed9c-148">Это приводит к искажениям звукового канала.</span><span class="sxs-lookup"><span data-stu-id="eed9c-148">This causes distortions with the audio channel.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eed9c-149"><strong>девицехалфдуплексаецевентратио</strong></span><span class="sxs-lookup"><span data-stu-id="eed9c-149"><strong>DeviceHalfDuplexAECEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="eed9c-150">десятичное число (5, 2)</span><span class="sxs-lookup"><span data-stu-id="eed9c-150">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="eed9c-151">Процентное отношение сеанса событие Девицехалфдуплексаек было вызвано для состояния "плохое".</span><span class="sxs-lookup"><span data-stu-id="eed9c-151">Percentage of session the DeviceHalfDuplexAEC event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="eed9c-152">Чтобы предотвратить эхо, в системе введена половина дуплекса.</span><span class="sxs-lookup"><span data-stu-id="eed9c-152">In order to prevent echo, the system has enter half duplex.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eed9c-153"><strong>девицерендернотфунктионинжевентратио</strong></span><span class="sxs-lookup"><span data-stu-id="eed9c-153"><strong>DeviceRenderNotFunctioningEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="eed9c-154">десятичное число (5, 2)</span><span class="sxs-lookup"><span data-stu-id="eed9c-154">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="eed9c-155">Процентное отношение сеанса событие Девицерендернотфунктионинг было вызвано для состояния "плохое".</span><span class="sxs-lookup"><span data-stu-id="eed9c-155">Percentage of session the DeviceRenderNotFunctioning event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="eed9c-156">Устройство обработки, используемое в данный момент для сеанса, работает неправильно.</span><span class="sxs-lookup"><span data-stu-id="eed9c-156">The render device currently being used for the session is not functioning correctly.</span></span> <span data-ttu-id="eed9c-157">Это может привести к необратимым проблемам с аудио.</span><span class="sxs-lookup"><span data-stu-id="eed9c-157">This can cause one-way audio issues.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eed9c-158"><strong>девицекаптуренотфунктионинжевентратио</strong></span><span class="sxs-lookup"><span data-stu-id="eed9c-158"><strong>DeviceCaptureNotFunctioningEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="eed9c-159">десятичное число (5, 2)</span><span class="sxs-lookup"><span data-stu-id="eed9c-159">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="eed9c-160">Процентное отношение сеанса событие Девицекаптуренотфунктионинг было вызвано для состояния "плохое".</span><span class="sxs-lookup"><span data-stu-id="eed9c-160">Percentage of session the DeviceCaptureNotFunctioning event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="eed9c-161">Устройство записи, используемое в данный момент для сеанса, работает неправильно.</span><span class="sxs-lookup"><span data-stu-id="eed9c-161">The capture device currently being used for the session is not functioning correctly.</span></span> <span data-ttu-id="eed9c-162">Это может привести к необратимым проблемам с аудио.</span><span class="sxs-lookup"><span data-stu-id="eed9c-162">This can cause one-way audio issues.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eed9c-163"><strong>девицеглитчесевентратио</strong></span><span class="sxs-lookup"><span data-stu-id="eed9c-163"><strong>DeviceGlitchesEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="eed9c-164">десятичное число (5, 2)</span><span class="sxs-lookup"><span data-stu-id="eed9c-164">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="eed9c-165">Процентное отношение сеанса событие Девицеглитчес было вызвано для состояния "плохое".</span><span class="sxs-lookup"><span data-stu-id="eed9c-165">Percentage of session the DeviceGlitches event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="eed9c-166">При отображении звука возникают серьезные проблемы, приводящие к искажениям.</span><span class="sxs-lookup"><span data-stu-id="eed9c-166">There are severe glitches in the rendering of audio which is causing distortions.</span></span> <span data-ttu-id="eed9c-167">Эти проблемы могут быть вызваны проблемами с драйверами, отложенными вызовами процедур (DPC) и высокой загрузкой ЦП.</span><span class="sxs-lookup"><span data-stu-id="eed9c-167">These glitches can be caused by driver issues, deferred procedure calls (DPC) storm (drivers), and high CPU usage.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eed9c-168"><strong>девицеловснревентратио</strong></span><span class="sxs-lookup"><span data-stu-id="eed9c-168"><strong>DeviceLowSNREventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="eed9c-169">десятичное число (5, 2)</span><span class="sxs-lookup"><span data-stu-id="eed9c-169">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="eed9c-170">Процентное отношение сеанса событие Девицеловснр было вызвано для состояния "плохое".</span><span class="sxs-lookup"><span data-stu-id="eed9c-170">Percentage of session the DeviceLowSNR event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="eed9c-171">Качество захвата очень низкое, либо очень шумный, либо пользователь работает слишком далеко от микрофона.</span><span class="sxs-lookup"><span data-stu-id="eed9c-171">The capture quality is very poor, either very noisy or user is talking too far away from the microphone.</span></span> <span data-ttu-id="eed9c-172">Это приведет к искажениям.</span><span class="sxs-lookup"><span data-stu-id="eed9c-172">This will cause distortions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eed9c-173"><strong>девицеловспичлевелевентратио</strong></span><span class="sxs-lookup"><span data-stu-id="eed9c-173"><strong>DeviceLowSpeechLevelEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="eed9c-174">десятичное число (5, 2)</span><span class="sxs-lookup"><span data-stu-id="eed9c-174">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="eed9c-175">Процентное отношение сеанса событие Девицеловспичлевел было вызвано для состояния "плохое".</span><span class="sxs-lookup"><span data-stu-id="eed9c-175">Percentage of session the DeviceLowSpeechLevel event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="eed9c-176">Слишком маленький уровень речи пользователя, система не может увеличить его.</span><span class="sxs-lookup"><span data-stu-id="eed9c-176">User‘s speech level is too low and the system cannot increase it any further.</span></span> <span data-ttu-id="eed9c-177">Это может привести к искажениям или восприятию одностороннего звука.</span><span class="sxs-lookup"><span data-stu-id="eed9c-177">This can either cause distortions or perceived as one-way audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eed9c-178"><strong>девицеклиппинжевентратио</strong></span><span class="sxs-lookup"><span data-stu-id="eed9c-178"><strong>DeviceClippingEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="eed9c-179">Десятичное число (5, 2)</span><span class="sxs-lookup"><span data-stu-id="eed9c-179">Decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="eed9c-180">Процентное отношение сеанса событие Девицеклиппинг было вызвано для состояния "плохое".</span><span class="sxs-lookup"><span data-stu-id="eed9c-180">Percentage of session the DeviceClipping event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="eed9c-181">При использовании Ближнего голосовых видеороликов Микрофоны прослушивают искажения из-за обрезки.</span><span class="sxs-lookup"><span data-stu-id="eed9c-181">When near-end speech clips the microphone, far-end hears distortion due to clipping.</span></span> <span data-ttu-id="eed9c-182">Важно избегать использования Ближнего отсечения от микрофона.</span><span class="sxs-lookup"><span data-stu-id="eed9c-182">It is important to avoid near-end microphone clipping.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eed9c-183"><strong>девицеечоевентратио</strong></span><span class="sxs-lookup"><span data-stu-id="eed9c-183"><strong>DeviceEchoEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="eed9c-184">десятичное число (5, 2)</span><span class="sxs-lookup"><span data-stu-id="eed9c-184">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="eed9c-185">Процентное отношение сеанса событие возникновения события deviceechoevent было вызвано для состояния "плохое".</span><span class="sxs-lookup"><span data-stu-id="eed9c-185">Percentage of session the DeviceEchoEvent event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="eed9c-186">Устройство или программа установки вызывает эхо за пределами возможности системы для компенсации.</span><span class="sxs-lookup"><span data-stu-id="eed9c-186">Device or setup is causing echo beyond the ability of the system to compensate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eed9c-187"><strong>девиценеарендтоечоратиоевентратио</strong></span><span class="sxs-lookup"><span data-stu-id="eed9c-187"><strong>DeviceNearEndToEchoRatioEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="eed9c-188">десятичное число (5, 2)</span><span class="sxs-lookup"><span data-stu-id="eed9c-188">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="eed9c-189">Процентное отношение сеанса событие Девиценеарендтоечоратио было вызвано для состояния "плохое".</span><span class="sxs-lookup"><span data-stu-id="eed9c-189">Percentage of session the DeviceNearEndToEchoRatio event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="eed9c-190">Голосовая речь пользователя слишком мала по сравнению с записанным эхо-значением, которое влияет на взаимодействие с пользователями, так как оно позволяет ограничить способ прерывания пользователя.</span><span class="sxs-lookup"><span data-stu-id="eed9c-190">The user’s speech is too low compared to the echo being captured which impacts the users experience because it limits how easy it is to interrupt a user.</span></span> <span data-ttu-id="eed9c-191">Уменьшите громкость динамика, наведите микрофон ближе к рассказано.</span><span class="sxs-lookup"><span data-stu-id="eed9c-191">Reduce speaker volume, move the microphone closer to the talker.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eed9c-192"><strong>девицемултиплиндпоинтсевенткаунт</strong></span><span class="sxs-lookup"><span data-stu-id="eed9c-192"><strong>DeviceMultipleEndpointsEventCount</strong></span></span></p></td>
<td><p><span data-ttu-id="eed9c-193">int</span><span class="sxs-lookup"><span data-stu-id="eed9c-193">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eed9c-194">Количество раз, когда сеанс был вызван событием Девицемултиплиндпоинтс для состояния "плохое".</span><span class="sxs-lookup"><span data-stu-id="eed9c-194">Number of times during session the DeviceMultipleEndpoints event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="eed9c-195">Обнаружено несколько конечных точек звука в одном сеансе, и система компенсируется с помощью уменьшения объема отображения.</span><span class="sxs-lookup"><span data-stu-id="eed9c-195">Multiple audio endpoints in the same session detected and the system has compensated by reducing render volume.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eed9c-196"><strong>девицеховлинжевенткаунт</strong></span><span class="sxs-lookup"><span data-stu-id="eed9c-196"><strong>DeviceHowlingEventCount</strong></span></span></p></td>
<td><p><span data-ttu-id="eed9c-197">int</span><span class="sxs-lookup"><span data-stu-id="eed9c-197">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="eed9c-198">Количество раз, когда сеанс был вызван событием Девицеховлинжевент для состояния "плохое".</span><span class="sxs-lookup"><span data-stu-id="eed9c-198">Number of times during session the DeviceHowlingEvent event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="eed9c-199">Обнаружен цикл обратной связи со звуком (с указанием нескольких конечных точек для общего доступа к файлам).</span><span class="sxs-lookup"><span data-stu-id="eed9c-199">Audio feedback loop detected (caused by multiple endpoints sharing audio path).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eed9c-200"><strong>девицерендерзероволумивентратио</strong></span><span class="sxs-lookup"><span data-stu-id="eed9c-200"><strong>DeviceRenderZeroVolumeEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="eed9c-201">десятичное число (5, 2)</span><span class="sxs-lookup"><span data-stu-id="eed9c-201">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eed9c-202">Процент сеанса, в котором было вызвано событие Девицерендерзероволуме, в состоянии "плохое".</span><span class="sxs-lookup"><span data-stu-id="eed9c-202">Percentage of session the DeviceRenderZeroVolume event was fired for being in the “Bad’ state.</span></span> <span data-ttu-id="eed9c-203">Для устройства отрисовки задано нулевое значение громкости.</span><span class="sxs-lookup"><span data-stu-id="eed9c-203">The render device was set to zero volume.</span></span></p>
<p><span data-ttu-id="eed9c-204">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="eed9c-204">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eed9c-205"><strong>девицерендермутивентратио</strong></span><span class="sxs-lookup"><span data-stu-id="eed9c-205"><strong>DeviceRenderMuteEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="eed9c-206">десятичное число (5, 2)</span><span class="sxs-lookup"><span data-stu-id="eed9c-206">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eed9c-207">Процент сеанса, в котором было вызвано событие Девицерендермуте, в состоянии "плохое".</span><span class="sxs-lookup"><span data-stu-id="eed9c-207">Percentage of session the DeviceRenderMute event was fired for being in the “Bad’ state.</span></span> <span data-ttu-id="eed9c-208">Устройство отображения отключено.</span><span class="sxs-lookup"><span data-stu-id="eed9c-208">The render device was muted.</span></span></p>
<p><span data-ttu-id="eed9c-209">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="eed9c-209">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

