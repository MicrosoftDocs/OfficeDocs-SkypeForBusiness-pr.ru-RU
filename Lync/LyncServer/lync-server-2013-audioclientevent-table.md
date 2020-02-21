---
title: 'Lync Server 2013: таблица таблица audioclientevent'
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
ms.openlocfilehash: d93a9cd9276ba2bdaacf892ca0ab3f4240458503
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42203465"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="audioclientevent-table-in-lync-server-2013"></a><span data-ttu-id="0d7cc-102">Таблица Таблица audioclientevent в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0d7cc-102">AudioClientEvent table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0d7cc-103">_**Последнее изменение темы:** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="0d7cc-103">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="0d7cc-104">Каждая запись содержит клиентское событие для одной конечной точки в голосовой вызове.</span><span class="sxs-lookup"><span data-stu-id="0d7cc-104">Each record contains a client event for one endpoint in an audio call.</span></span> <span data-ttu-id="0d7cc-105">Как правило, один вызов состоит из двух записей, один для вызывающего абонента и один для вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="0d7cc-105">Usually, one call has two records, one for caller and one for callee.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0d7cc-106"><strong>Column</strong></span><span class="sxs-lookup"><span data-stu-id="0d7cc-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="0d7cc-107"><strong>Тип данных</strong></span><span class="sxs-lookup"><span data-stu-id="0d7cc-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="0d7cc-108"><strong>Ключ или индекс</strong></span><span class="sxs-lookup"><span data-stu-id="0d7cc-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="0d7cc-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="0d7cc-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0d7cc-110"><strong>конференцедатетиме</strong></span><span class="sxs-lookup"><span data-stu-id="0d7cc-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="0d7cc-111">datetime</span><span class="sxs-lookup"><span data-stu-id="0d7cc-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="0d7cc-112">Primary</span><span class="sxs-lookup"><span data-stu-id="0d7cc-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="0d7cc-113">Ссылка из <a href="lync-server-2013-medialine-table.md">таблицы MediaLine в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="0d7cc-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d7cc-114"><strong>сессионсек</strong></span><span class="sxs-lookup"><span data-stu-id="0d7cc-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="0d7cc-115">int</span><span class="sxs-lookup"><span data-stu-id="0d7cc-115">int</span></span></p></td>
<td><p><span data-ttu-id="0d7cc-116">Primary</span><span class="sxs-lookup"><span data-stu-id="0d7cc-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="0d7cc-117">Ссылка из <a href="lync-server-2013-medialine-table.md">таблицы MediaLine в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="0d7cc-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0d7cc-118"><strong>медиалинелабел</strong></span><span class="sxs-lookup"><span data-stu-id="0d7cc-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="0d7cc-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="0d7cc-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="0d7cc-120">Primary</span><span class="sxs-lookup"><span data-stu-id="0d7cc-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="0d7cc-121">Ссылка из <a href="lync-server-2013-medialine-table.md">таблицы MediaLine в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="0d7cc-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d7cc-122"><strong>фромкаллер</strong></span><span class="sxs-lookup"><span data-stu-id="0d7cc-122"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="0d7cc-123">Битовая</span><span class="sxs-lookup"><span data-stu-id="0d7cc-123">bit</span></span></p></td>
<td><p><span data-ttu-id="0d7cc-124">Primary</span><span class="sxs-lookup"><span data-stu-id="0d7cc-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="0d7cc-125">0: данные вызываемого абонента</span><span class="sxs-lookup"><span data-stu-id="0d7cc-125">0: Callee’s data</span></span></p>
<p><span data-ttu-id="0d7cc-126">1: данные вызывающего абонента</span><span class="sxs-lookup"><span data-stu-id="0d7cc-126">1: Caller’s data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0d7cc-127"><strong>нетворксендкуалитевентратио</strong></span><span class="sxs-lookup"><span data-stu-id="0d7cc-127"><strong>NetworkSendQualityEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="0d7cc-128">десятичное число (5, 2)</span><span class="sxs-lookup"><span data-stu-id="0d7cc-128">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0d7cc-129">Процентное отношение сеанса событие Нетворксендкуалити было вызвано для состояния "плохое".</span><span class="sxs-lookup"><span data-stu-id="0d7cc-129">Percentage of session the NetworkSendQuality event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="0d7cc-130">Качество сети в терминах нарушения или потери пакетов серьезно и влияет на качество отправляемого звука.</span><span class="sxs-lookup"><span data-stu-id="0d7cc-130">Network quality in terms of jitter or packet loss is severe and impacting the quality of audio being sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d7cc-131"><strong>нетворкрецеивекуалитевентратио</strong></span><span class="sxs-lookup"><span data-stu-id="0d7cc-131"><strong>NetworkReceiveQualityEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="0d7cc-132">десятичное число (5, 2)</span><span class="sxs-lookup"><span data-stu-id="0d7cc-132">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0d7cc-133">Процентное отношение сеанса событие Рецеивесендкуалити было вызвано для состояния "плохое".</span><span class="sxs-lookup"><span data-stu-id="0d7cc-133">Percentage of session the ReceiveSendQuality event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="0d7cc-134">Качество сети в терминах нарушения или потери пакетов серьезно и влияет на качество получаемого звука.</span><span class="sxs-lookup"><span data-stu-id="0d7cc-134">Network quality in terms of jitter or packet loss is severe and impacting the quality of audio being received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0d7cc-135"><strong>нетворкделайевентратио</strong></span><span class="sxs-lookup"><span data-stu-id="0d7cc-135"><strong>NetworkDelayEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="0d7cc-136">десятичное число (5, 2)</span><span class="sxs-lookup"><span data-stu-id="0d7cc-136">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0d7cc-137">Процентное соотношение между сеансами событие Delay было вызвано для состояния "плохое".</span><span class="sxs-lookup"><span data-stu-id="0d7cc-137">Percentage of session the Delay event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="0d7cc-138">Задержка в сети серьезна и повлияет на работу, предотвращая интерактивную связь</span><span class="sxs-lookup"><span data-stu-id="0d7cc-138">Network latency is severe and impacting the experience by preventing interactive communication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d7cc-139"><strong>нетворкбандвидсловевентратио</strong></span><span class="sxs-lookup"><span data-stu-id="0d7cc-139"><strong>NetworkBandwidthLowEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="0d7cc-140">десятичное число (5, 2)</span><span class="sxs-lookup"><span data-stu-id="0d7cc-140">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0d7cc-141">Процентное отношение сеанса событие Ловбандвидс было вызвано для состояния "плохое".</span><span class="sxs-lookup"><span data-stu-id="0d7cc-141">Percentage of session the LowBandwidth event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="0d7cc-142">Доступная полоса пропускания недостаточна для приемлемого голосового интерфейса.</span><span class="sxs-lookup"><span data-stu-id="0d7cc-142">The available bandwidth is insufficient for an acceptable voice experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0d7cc-143"><strong>кпуинсуффиЦиентевентратио</strong></span><span class="sxs-lookup"><span data-stu-id="0d7cc-143"><strong>CPUInsufficientEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="0d7cc-144">десятичное число (5, 2)</span><span class="sxs-lookup"><span data-stu-id="0d7cc-144">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0d7cc-145">Процентное соотношение от сеанса, которое было вызвано недостаточным событием ЦП для состояния "Bad".</span><span class="sxs-lookup"><span data-stu-id="0d7cc-145">Percentage of session the insufficient CPU event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="0d7cc-146">Недостаточно циклов ЦП для обработки с текущими модальности и используемыми приложениями.</span><span class="sxs-lookup"><span data-stu-id="0d7cc-146">There are insufficient CPU cycles for processing with the current modalities and applications in use.</span></span> <span data-ttu-id="0d7cc-147">Это приводит к искажениям звукового канала.</span><span class="sxs-lookup"><span data-stu-id="0d7cc-147">This causes distortions with the audio channel.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d7cc-148"><strong>девицехалфдуплексаецевентратио</strong></span><span class="sxs-lookup"><span data-stu-id="0d7cc-148"><strong>DeviceHalfDuplexAECEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="0d7cc-149">десятичное число (5, 2)</span><span class="sxs-lookup"><span data-stu-id="0d7cc-149">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0d7cc-150">Процентное отношение сеанса событие Девицехалфдуплексаек было вызвано для состояния "плохое".</span><span class="sxs-lookup"><span data-stu-id="0d7cc-150">Percentage of session the DeviceHalfDuplexAEC event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="0d7cc-151">Чтобы предотвратить эхо, в системе введена половина дуплекса.</span><span class="sxs-lookup"><span data-stu-id="0d7cc-151">In order to prevent echo, the system has enter half duplex.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0d7cc-152"><strong>девицерендернотфунктионинжевентратио</strong></span><span class="sxs-lookup"><span data-stu-id="0d7cc-152"><strong>DeviceRenderNotFunctioningEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="0d7cc-153">десятичное число (5, 2)</span><span class="sxs-lookup"><span data-stu-id="0d7cc-153">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0d7cc-154">Процентное отношение сеанса событие Девицерендернотфунктионинг было вызвано для состояния "плохое".</span><span class="sxs-lookup"><span data-stu-id="0d7cc-154">Percentage of session the DeviceRenderNotFunctioning event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="0d7cc-155">Устройство обработки, используемое в данный момент для сеанса, работает неправильно.</span><span class="sxs-lookup"><span data-stu-id="0d7cc-155">The render device currently being used for the session is not functioning correctly.</span></span> <span data-ttu-id="0d7cc-156">Это может привести к необратимым проблемам с аудио.</span><span class="sxs-lookup"><span data-stu-id="0d7cc-156">This can cause one-way audio issues.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d7cc-157"><strong>девицекаптуренотфунктионинжевентратио</strong></span><span class="sxs-lookup"><span data-stu-id="0d7cc-157"><strong>DeviceCaptureNotFunctioningEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="0d7cc-158">десятичное число (5, 2)</span><span class="sxs-lookup"><span data-stu-id="0d7cc-158">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0d7cc-159">Процентное отношение сеанса событие Девицекаптуренотфунктионинг было вызвано для состояния "плохое".</span><span class="sxs-lookup"><span data-stu-id="0d7cc-159">Percentage of session the DeviceCaptureNotFunctioning event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="0d7cc-160">Устройство записи, используемое в данный момент для сеанса, работает неправильно.</span><span class="sxs-lookup"><span data-stu-id="0d7cc-160">The capture device currently being used for the session is not functioning correctly.</span></span> <span data-ttu-id="0d7cc-161">Это может привести к необратимым проблемам с аудио.</span><span class="sxs-lookup"><span data-stu-id="0d7cc-161">This can cause one-way audio issues.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0d7cc-162"><strong>девицеглитчесевентратио</strong></span><span class="sxs-lookup"><span data-stu-id="0d7cc-162"><strong>DeviceGlitchesEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="0d7cc-163">десятичное число (5, 2)</span><span class="sxs-lookup"><span data-stu-id="0d7cc-163">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0d7cc-164">Процентное отношение сеанса событие Девицеглитчес было вызвано для состояния "плохое".</span><span class="sxs-lookup"><span data-stu-id="0d7cc-164">Percentage of session the DeviceGlitches event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="0d7cc-165">При отображении звука возникают серьезные проблемы, приводящие к искажениям.</span><span class="sxs-lookup"><span data-stu-id="0d7cc-165">There are severe glitches in the rendering of audio which is causing distortions.</span></span> <span data-ttu-id="0d7cc-166">Эти проблемы могут быть вызваны проблемами с драйверами, отложенными вызовами процедур (DPC) и высокой загрузкой ЦП.</span><span class="sxs-lookup"><span data-stu-id="0d7cc-166">These glitches can be caused by driver issues, deferred procedure calls (DPC) storm (drivers), and high CPU usage.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d7cc-167"><strong>девицеловснревентратио</strong></span><span class="sxs-lookup"><span data-stu-id="0d7cc-167"><strong>DeviceLowSNREventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="0d7cc-168">десятичное число (5, 2)</span><span class="sxs-lookup"><span data-stu-id="0d7cc-168">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0d7cc-169">Процентное отношение сеанса событие Девицеловснр было вызвано для состояния "плохое".</span><span class="sxs-lookup"><span data-stu-id="0d7cc-169">Percentage of session the DeviceLowSNR event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="0d7cc-170">Качество захвата очень низкое, либо очень шумный, либо пользователь работает слишком далеко от микрофона.</span><span class="sxs-lookup"><span data-stu-id="0d7cc-170">The capture quality is very poor, either very noisy or user is talking too far away from the microphone.</span></span> <span data-ttu-id="0d7cc-171">Это приведет к искажениям.</span><span class="sxs-lookup"><span data-stu-id="0d7cc-171">This will cause distortions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0d7cc-172"><strong>девицеловспичлевелевентратио</strong></span><span class="sxs-lookup"><span data-stu-id="0d7cc-172"><strong>DeviceLowSpeechLevelEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="0d7cc-173">десятичное число (5, 2)</span><span class="sxs-lookup"><span data-stu-id="0d7cc-173">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0d7cc-174">Процентное отношение сеанса событие Девицеловспичлевел было вызвано для состояния "плохое".</span><span class="sxs-lookup"><span data-stu-id="0d7cc-174">Percentage of session the DeviceLowSpeechLevel event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="0d7cc-175">Слишком маленький уровень речи пользователя, система не может увеличить его.</span><span class="sxs-lookup"><span data-stu-id="0d7cc-175">User‘s speech level is too low and the system cannot increase it any further.</span></span> <span data-ttu-id="0d7cc-176">Это может привести к искажениям или восприятию одностороннего звука.</span><span class="sxs-lookup"><span data-stu-id="0d7cc-176">This can either cause distortions or perceived as one-way audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d7cc-177"><strong>девицеклиппинжевентратио</strong></span><span class="sxs-lookup"><span data-stu-id="0d7cc-177"><strong>DeviceClippingEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="0d7cc-178">Десятичное число (5, 2)</span><span class="sxs-lookup"><span data-stu-id="0d7cc-178">Decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0d7cc-179">Процентное отношение сеанса событие Девицеклиппинг было вызвано для состояния "плохое".</span><span class="sxs-lookup"><span data-stu-id="0d7cc-179">Percentage of session the DeviceClipping event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="0d7cc-180">При использовании Ближнего голосовых видеороликов Микрофоны прослушивают искажения из-за обрезки.</span><span class="sxs-lookup"><span data-stu-id="0d7cc-180">When near-end speech clips the microphone, far-end hears distortion due to clipping.</span></span> <span data-ttu-id="0d7cc-181">Важно избегать использования Ближнего отсечения от микрофона.</span><span class="sxs-lookup"><span data-stu-id="0d7cc-181">It is important to avoid near-end microphone clipping.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0d7cc-182"><strong>девицеечоевентратио</strong></span><span class="sxs-lookup"><span data-stu-id="0d7cc-182"><strong>DeviceEchoEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="0d7cc-183">десятичное число (5, 2)</span><span class="sxs-lookup"><span data-stu-id="0d7cc-183">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0d7cc-184">Процентное отношение сеанса событие возникновения события deviceechoevent было вызвано для состояния "плохое".</span><span class="sxs-lookup"><span data-stu-id="0d7cc-184">Percentage of session the DeviceEchoEvent event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="0d7cc-185">Устройство или программа установки вызывает эхо за пределами возможности системы для компенсации.</span><span class="sxs-lookup"><span data-stu-id="0d7cc-185">Device or setup is causing echo beyond the ability of the system to compensate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d7cc-186"><strong>девиценеарендтоечоратиоевентратио</strong></span><span class="sxs-lookup"><span data-stu-id="0d7cc-186"><strong>DeviceNearEndToEchoRatioEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="0d7cc-187">десятичное число (5, 2)</span><span class="sxs-lookup"><span data-stu-id="0d7cc-187">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0d7cc-188">Процентное отношение сеанса событие Девиценеарендтоечоратио было вызвано для состояния "плохое".</span><span class="sxs-lookup"><span data-stu-id="0d7cc-188">Percentage of session the DeviceNearEndToEchoRatio event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="0d7cc-189">Голосовая речь пользователя слишком мала по сравнению с записанным эхо-значением, которое влияет на взаимодействие с пользователями, так как оно позволяет ограничить способ прерывания пользователя.</span><span class="sxs-lookup"><span data-stu-id="0d7cc-189">The user’s speech is too low compared to the echo being captured which impacts the users experience because it limits how easy it is to interrupt a user.</span></span> <span data-ttu-id="0d7cc-190">Уменьшите громкость динамика, наведите микрофон ближе к рассказано.</span><span class="sxs-lookup"><span data-stu-id="0d7cc-190">Reduce speaker volume, move the microphone closer to the talker.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0d7cc-191"><strong>девицемултиплиндпоинтсевенткаунт</strong></span><span class="sxs-lookup"><span data-stu-id="0d7cc-191"><strong>DeviceMultipleEndpointsEventCount</strong></span></span></p></td>
<td><p><span data-ttu-id="0d7cc-192">int</span><span class="sxs-lookup"><span data-stu-id="0d7cc-192">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0d7cc-193">Количество раз, когда сеанс был вызван событием Девицемултиплиндпоинтс для состояния "плохое".</span><span class="sxs-lookup"><span data-stu-id="0d7cc-193">Number of times during session the DeviceMultipleEndpoints event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="0d7cc-194">Обнаружено несколько конечных точек звука в одном сеансе, и система компенсируется с помощью уменьшения объема отображения.</span><span class="sxs-lookup"><span data-stu-id="0d7cc-194">Multiple audio endpoints in the same session detected and the system has compensated by reducing render volume.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d7cc-195"><strong>девицеховлинжевенткаунт</strong></span><span class="sxs-lookup"><span data-stu-id="0d7cc-195"><strong>DeviceHowlingEventCount</strong></span></span></p></td>
<td><p><span data-ttu-id="0d7cc-196">int</span><span class="sxs-lookup"><span data-stu-id="0d7cc-196">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0d7cc-197">Количество раз, когда сеанс был вызван событием Девицеховлинжевент для состояния "плохое".</span><span class="sxs-lookup"><span data-stu-id="0d7cc-197">Number of times during session the DeviceHowlingEvent event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="0d7cc-198">Обнаружен цикл обратной связи со звуком (с указанием нескольких конечных точек для общего доступа к файлам).</span><span class="sxs-lookup"><span data-stu-id="0d7cc-198">Audio feedback loop detected (caused by multiple endpoints sharing audio path).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0d7cc-199"><strong>девицерендерзероволумивентратио</strong></span><span class="sxs-lookup"><span data-stu-id="0d7cc-199"><strong>DeviceRenderZeroVolumeEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="0d7cc-200">десятичное число (5, 2)</span><span class="sxs-lookup"><span data-stu-id="0d7cc-200">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0d7cc-201">Процент сеанса, в котором было вызвано событие Девицерендерзероволуме, в состоянии "плохое".</span><span class="sxs-lookup"><span data-stu-id="0d7cc-201">Percentage of session the DeviceRenderZeroVolume event was fired for being in the “Bad’ state.</span></span> <span data-ttu-id="0d7cc-202">Для устройства отрисовки задано нулевое значение громкости.</span><span class="sxs-lookup"><span data-stu-id="0d7cc-202">The render device was set to zero volume.</span></span></p>
<p><span data-ttu-id="0d7cc-203">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0d7cc-203">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d7cc-204"><strong>девицерендермутивентратио</strong></span><span class="sxs-lookup"><span data-stu-id="0d7cc-204"><strong>DeviceRenderMuteEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="0d7cc-205">десятичное число (5, 2)</span><span class="sxs-lookup"><span data-stu-id="0d7cc-205">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0d7cc-206">Процент сеанса, в котором было вызвано событие Девицерендермуте, в состоянии "плохое".</span><span class="sxs-lookup"><span data-stu-id="0d7cc-206">Percentage of session the DeviceRenderMute event was fired for being in the “Bad’ state.</span></span> <span data-ttu-id="0d7cc-207">Устройство отображения отключено.</span><span class="sxs-lookup"><span data-stu-id="0d7cc-207">The render device was muted.</span></span></p>
<p><span data-ttu-id="0d7cc-208">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0d7cc-208">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

