---
title: 'Lync Server 2013: отчет о списке обзвона'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Call List Report
ms:assetid: 9739f9f0-7a37-4844-91d5-f089d2011013
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615020(v=OCS.15)
ms:contentKeyID: 48184921
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: faf330a776f64534c02833a0472cfefea7f0998e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841706"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-list-report-in-lync-server-2013"></a><span data-ttu-id="525b0-102">Отчет "список обзвона" в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="525b0-102">Call List Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="525b0-103">_**Тема последнего изменения:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="525b0-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="525b0-104">Отчет по списку обзвона предоставляет параметры качества взаимодействия (QoE) для отдельных вызовов, выполненных и принятых сотрудниками организации.</span><span class="sxs-lookup"><span data-stu-id="525b0-104">The Call List Report provides Quality of Experience (QoE) metrics for individual calls made and received in your organization.</span></span> <span data-ttu-id="525b0-105">Обратите внимание, что действительные параметры, содержащиеся в отчете, зависят от способа доступа к отчету по списку обзвона.</span><span class="sxs-lookup"><span data-stu-id="525b0-105">Note that the actual metrics reported will depend on how you access the Call List report.</span></span> <span data-ttu-id="525b0-106">Например, если открыть отчет из [отчета на устройстве в Lync Server 2013, в](lync-server-2013-device-report.md)отчете об устройстве будут показаны такие метрики, как, например, метрики, указанные ниже.</span><span class="sxs-lookup"><span data-stu-id="525b0-106">For example, if you open the report from the [Device Report in Lync Server 2013](lync-server-2013-device-report.md), you'll see metrics such as the following, metrics that are also reported on the Device Report:</span></span>

  - <span data-ttu-id="525b0-107">Микрофон вызывающего абонента</span><span class="sxs-lookup"><span data-stu-id="525b0-107">Caller's microphone</span></span>

  - <span data-ttu-id="525b0-108">Динамик вызывающего абонента</span><span class="sxs-lookup"><span data-stu-id="525b0-108">Caller's speaker</span></span>

  - <span data-ttu-id="525b0-109">Микрофон вызываемого абонента</span><span class="sxs-lookup"><span data-stu-id="525b0-109">Callee's microphone</span></span>

  - <span data-ttu-id="525b0-110">Динамик вызываемого абонента</span><span class="sxs-lookup"><span data-stu-id="525b0-110">Callee's speaker</span></span>

  - <span data-ttu-id="525b0-111">Соотношение времени голосовой коммутации</span><span class="sxs-lookup"><span data-stu-id="525b0-111">Ratio of voice switch time</span></span>

<span data-ttu-id="525b0-112">Тем не менее, если открыть отчет "список обзвона" из [отчета о местоположении в Lync Server 2013](lync-server-2013-location-report.md), вы не увидите эти метрики; Вместо этого вы увидите метрики, подобные указанным ниже.</span><span class="sxs-lookup"><span data-stu-id="525b0-112">However, if you open the Call List Report from the [Location Report in Lync Server 2013](lync-server-2013-location-report.md), you won't see any of those metrics; instead, you'll see metrics like these:</span></span>

  - <span data-ttu-id="525b0-113">Круговой путь (мс)</span><span class="sxs-lookup"><span data-stu-id="525b0-113">Round trip (ms)</span></span>

  - <span data-ttu-id="525b0-114">Падение качества (средняя оценка)</span><span class="sxs-lookup"><span data-stu-id="525b0-114">Degradation (MOS)</span></span>

  - <span data-ttu-id="525b0-115">Потеря пакетов</span><span class="sxs-lookup"><span data-stu-id="525b0-115">Packet loss</span></span>

  - <span data-ttu-id="525b0-116">Дрожание (мс)</span><span class="sxs-lookup"><span data-stu-id="525b0-116">Jitter (ms)</span></span>

<span data-ttu-id="525b0-p102">Это показатели, содержащиеся в отчете о местоположении. Однако вы всегда можете щелкнуть «Подробные показатели» в отчете по списку обзвона, чтобы получить полную информацию QoE для любого вызова.</span><span class="sxs-lookup"><span data-stu-id="525b0-p102">Those are the metrics reported on the Location Report. However, from the Call List Report you can always click the Detail metric to provide complete QoE information for any call.</span></span>

<div>

## <a name="accessing-the-call-list-report"></a><span data-ttu-id="525b0-119">Доступ к отчету по списку обзвона</span><span class="sxs-lookup"><span data-stu-id="525b0-119">Accessing the Call List Report</span></span>

<span data-ttu-id="525b0-120">Доступ к отчету по списку обзвона можно получить из любого из следующих отчетов:</span><span class="sxs-lookup"><span data-stu-id="525b0-120">The Call List Report can be accessed from any of the following reports:</span></span>

  - <span data-ttu-id="525b0-121">[Отчет о расположении в Lync Server 2013](lync-server-2013-location-report.md) (щелчок на громкость звонка или процент неудовлетворительного звонка)</span><span class="sxs-lookup"><span data-stu-id="525b0-121">The [Location Report in Lync Server 2013](lync-server-2013-location-report.md) (by clicking the Call volume or Poor call percentage metric)</span></span>

  - <span data-ttu-id="525b0-122">[Отчет об устройстве в Lync Server 2013](lync-server-2013-device-report.md) (щелчок на громкость звонка или процент неудовлетворительного звонка)</span><span class="sxs-lookup"><span data-stu-id="525b0-122">The [Device Report in Lync Server 2013](lync-server-2013-device-report.md) (by clicking the Call volume or Poor call percentage metric)</span></span>

  - <span data-ttu-id="525b0-123">[Сводный отчет о качестве качества мультимедиа в Lync Server 2013](lync-server-2013-media-quality-summary-report.md) (щелчок на громкость звонка или процент неудовлетворительного звонка)</span><span class="sxs-lookup"><span data-stu-id="525b0-123">The [Media Quality Summary Report in Lync Server 2013](lync-server-2013-media-quality-summary-report.md) (by clicking the Call volume or Poor call percentage metric)</span></span>

  - <span data-ttu-id="525b0-124">[Отчет о производительности сервера в Lync server 2013](lync-server-2013-server-performance-report.md) (с помощью кнопки "позвонить" или "неудовлетворительный процент звонка")</span><span class="sxs-lookup"><span data-stu-id="525b0-124">The [Server Performance Report in Lync Server 2013](lync-server-2013-server-performance-report.md) (by clicking the Call volume or Poor call percentage metric)</span></span>

<span data-ttu-id="525b0-125">В отчете список обзвона вы можете получить доступ к подробным сведениям о [звонке в Lync Server 2013](lync-server-2013-call-detail-report.md) , щелкнув соответствующую детальную метрику.</span><span class="sxs-lookup"><span data-stu-id="525b0-125">From within the Call List Report you can access the [Call Detail Report in Lync Server 2013](lync-server-2013-call-detail-report.md) by clicking the Detail metric.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-call-list-report"></a><span data-ttu-id="525b0-126">Эффективное использование отчета по списку обзвона</span><span class="sxs-lookup"><span data-stu-id="525b0-126">Making the Best Use of the Call List Report</span></span>

<span data-ttu-id="525b0-127">Если вы не помните, для чего именно используются некоторые показатели отчета по списку обзвона (например, «Соотношение времени голосовой коммутации»), наведите указатель мыши на метку показателя; отобразится всплывающая подсказка, содержащая краткое описание показателя.</span><span class="sxs-lookup"><span data-stu-id="525b0-127">If you can't remember what some of the Call List Report metrics (such as Ratio voice switch time) actually measure, hold your mouse over the metric label; a tool tip will then appear giving you a brief description of the metric.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="525b0-128">Фильтры</span><span class="sxs-lookup"><span data-stu-id="525b0-128">Filters</span></span>

<span data-ttu-id="525b0-p103">Нет. Фильтрация отчета по списку обзвона невозможна.</span><span class="sxs-lookup"><span data-stu-id="525b0-p103">None. You cannot filter the Call List Report.</span></span>

</div>

<div>

## <a name="metrics"></a><span data-ttu-id="525b0-131">Показатели</span><span class="sxs-lookup"><span data-stu-id="525b0-131">Metrics</span></span>

<span data-ttu-id="525b0-132">В следующей таблице представлен список данных, которые приводятся в отчете по списку обзвона для каждого вызова.</span><span class="sxs-lookup"><span data-stu-id="525b0-132">The following table lists the information provided in the Call List Report for each call.</span></span>

### <a name="call-list-report-metrics"></a><span data-ttu-id="525b0-133">Показатели в отчете по списку обзвона</span><span class="sxs-lookup"><span data-stu-id="525b0-133">Call List Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="525b0-134">Имя</span><span class="sxs-lookup"><span data-stu-id="525b0-134">Name</span></span></th>
<th><span data-ttu-id="525b0-135">Поддержка сортировки</span><span class="sxs-lookup"><span data-stu-id="525b0-135">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="525b0-136">Описание</span><span class="sxs-lookup"><span data-stu-id="525b0-136">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="525b0-137"><strong>Сведения</strong></span><span class="sxs-lookup"><span data-stu-id="525b0-137"><strong>Details</strong></span></span></p></td>
<td><p><span data-ttu-id="525b0-138">Нет</span><span class="sxs-lookup"><span data-stu-id="525b0-138">No</span></span></p></td>
<td><p><span data-ttu-id="525b0-139">Если щелкнуть этот элемент, в отчете отображается дополнительная информация о вызове.</span><span class="sxs-lookup"><span data-stu-id="525b0-139">When you click this item, the report shows additional information on the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="525b0-140"><strong>Вызывающая сторона</strong></span><span class="sxs-lookup"><span data-stu-id="525b0-140"><strong>Caller</strong></span></span></p></td>
<td><p><span data-ttu-id="525b0-141">Да</span><span class="sxs-lookup"><span data-stu-id="525b0-141">Yes</span></span></p></td>
<td><p><span data-ttu-id="525b0-142">SIP-адрес пользователя, инициировавшего вызов.</span><span class="sxs-lookup"><span data-stu-id="525b0-142">SIP address of the person who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="525b0-143"><strong>Вызываемая сторона</strong></span><span class="sxs-lookup"><span data-stu-id="525b0-143"><strong>Callee</strong></span></span></p></td>
<td><p><span data-ttu-id="525b0-144">Да</span><span class="sxs-lookup"><span data-stu-id="525b0-144">Yes</span></span></p></td>
<td><p><span data-ttu-id="525b0-145">SIP-адрес пользователя, который принял вызов.</span><span class="sxs-lookup"><span data-stu-id="525b0-145">SIP address of the person who was called.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="525b0-146"><strong>Время начала</strong></span><span class="sxs-lookup"><span data-stu-id="525b0-146"><strong>Start time</strong></span></span></p></td>
<td><p><span data-ttu-id="525b0-147">Да</span><span class="sxs-lookup"><span data-stu-id="525b0-147">Yes</span></span></p></td>
<td><p><span data-ttu-id="525b0-148">Дата и время начала звонка.</span><span class="sxs-lookup"><span data-stu-id="525b0-148">Date and time that the call started.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="525b0-149"><strong>Время окончания</strong></span><span class="sxs-lookup"><span data-stu-id="525b0-149"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="525b0-150">Да</span><span class="sxs-lookup"><span data-stu-id="525b0-150">Yes</span></span></p></td>
<td><p><span data-ttu-id="525b0-151">Дата и время окончания звонка.</span><span class="sxs-lookup"><span data-stu-id="525b0-151">Date and time that the call ended.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="525b0-152"><strong>Агент вызывающего пользователя</strong></span><span class="sxs-lookup"><span data-stu-id="525b0-152"><strong>Caller user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="525b0-153">Да</span><span class="sxs-lookup"><span data-stu-id="525b0-153">Yes</span></span></p></td>
<td><p><span data-ttu-id="525b0-154">Программное обеспечение, используемое конечной точкой пользователя, который инициировал вызов.</span><span class="sxs-lookup"><span data-stu-id="525b0-154">Software used by the endpoint of the person who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="525b0-155"><strong>Агент вызываемого пользователя</strong></span><span class="sxs-lookup"><span data-stu-id="525b0-155"><strong>Callee user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="525b0-156">Да</span><span class="sxs-lookup"><span data-stu-id="525b0-156">Yes</span></span></p></td>
<td><p><span data-ttu-id="525b0-157">Программное обеспечение, используемое конечной точкой пользователя, который принял вызов.</span><span class="sxs-lookup"><span data-stu-id="525b0-157">Software used by the endpoint of the person who was called.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="525b0-158"><strong>Круговой путь (мс)</strong></span><span class="sxs-lookup"><span data-stu-id="525b0-158"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="525b0-159">Да</span><span class="sxs-lookup"><span data-stu-id="525b0-159">Yes</span></span></p></td>
<td><p><span data-ttu-id="525b0-p104">Среднее время (в миллисекунда) требуемое для передачи пакета протокола транспорта реального времени (RTP) в другую конечную точку и обратно. Круговой путь в 100 и меньше миллисекунд считается допустимым.</span><span class="sxs-lookup"><span data-stu-id="525b0-p104">Average amount of (in milliseconds) required for a real-time transport protocol (RTP) packet to travel to another endpoint and then back. Round-trip times of 100 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="525b0-p105">Высокие значения прохождения кругового пути могут быть вызваны маршрутизацией международных звонков, неправильной настройкой маршрутизацией или перегрузкой сервера-посредника. Большое время кругового пути приводит к трудностям при обслуживании двунаправленных аудиоразговоров.</span><span class="sxs-lookup"><span data-stu-id="525b0-p105">High round-trip values can be caused by international call routing, a routing misconfiguration, or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="525b0-164"><strong>Падение качества (средняя оценка)</strong></span><span class="sxs-lookup"><span data-stu-id="525b0-164"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="525b0-165">Да</span><span class="sxs-lookup"><span data-stu-id="525b0-165">Yes</span></span></p></td>
<td><p><span data-ttu-id="525b0-166">Средняя экспертная оценка падения качества связи во время звонка.</span><span class="sxs-lookup"><span data-stu-id="525b0-166">Average amount of mean opinion score (MOS) degradation experienced during a call.</span></span> <span data-ttu-id="525b0-167">Значения лежат в диапазоне от 0,0 до 5,0.</span><span class="sxs-lookup"><span data-stu-id="525b0-167">Degradation values can range from a low of 0.0 to a high of 5.0.</span></span> <span data-ttu-id="525b0-168">Значение 0,5 или меньшее обозначает допустимое падение качества.</span><span class="sxs-lookup"><span data-stu-id="525b0-168">A value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="525b0-169">Изначально средние оценки рассчитывались на основе оценок, даваемых звонкам пользователями по шкале от 1 до 5.</span><span class="sxs-lookup"><span data-stu-id="525b0-169">Historically, mean options scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="525b0-170">В Lync Server Lync Server использует набор алгоритмов для прогнозирования того, как пользователи будут оценены при звонке.</span><span class="sxs-lookup"><span data-stu-id="525b0-170">In Lync Server, Lync Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="525b0-p107">Большие оценки падения качества могут быть вызваны перегрузкой сети, недостатком пропускной способности, помехами в беспроводной среде, перегрузкой на сервере-посреднике или конечной точке. Падение качества приводит к искажению или потере аудиосигнала.</span><span class="sxs-lookup"><span data-stu-id="525b0-p107">High degradation values can be caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server or endpoint. High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="525b0-173"><strong>Потеря пакетов</strong></span><span class="sxs-lookup"><span data-stu-id="525b0-173"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="525b0-174">Да</span><span class="sxs-lookup"><span data-stu-id="525b0-174">Yes</span></span></p></td>
<td><p><span data-ttu-id="525b0-p108">Среднее значение потери RTP-пакетов. (Пакет считается потерянным, если он не дошел до назначения). Большие значения потери пакетов могут быть вызваны перегрузкой сети, недостатком пропускной способности, помехами в беспроводной среде, перегрузкой на сервере-посреднике. Обычно это приводит к искажению или потере аудиосигнала.</span><span class="sxs-lookup"><span data-stu-id="525b0-p108">Average rate of RTP packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="525b0-178"><strong>Искажение</strong></span><span class="sxs-lookup"><span data-stu-id="525b0-178"><strong>Jitter</strong></span></span></p></td>
<td><p><span data-ttu-id="525b0-179">Да</span><span class="sxs-lookup"><span data-stu-id="525b0-179">Yes</span></span></p></td>
<td><p><span data-ttu-id="525b0-180">Среднее значение колебаний, зарегистрированных между прибытиями пакетов RTP.</span><span class="sxs-lookup"><span data-stu-id="525b0-180">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="525b0-181">(Колебание — это мера &quot;шакинесс&quot; звонка). Обычно значения с высокой степенью колебаний заключаются в результате перегруженности или перегруженного сервера мультимедиа, что приводит к искажению или потере звука.</span><span class="sxs-lookup"><span data-stu-id="525b0-181">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="525b0-182"><strong>Степень маскированных аудиообразцов</strong></span><span class="sxs-lookup"><span data-stu-id="525b0-182"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="525b0-183">Да</span><span class="sxs-lookup"><span data-stu-id="525b0-183">Yes</span></span></p></td>
<td><p><span data-ttu-id="525b0-p110">Средняя степень маскированных аудиообразцов по отношению к общему числу образцов. (Маскирование аудио - это методика, которая применяется для сглаживания оборванной передачи, которая обычно происходит при потери сетевых пакетов). Большие значения обозначают частое применение данной методики, вызванной из-за потери пакетов или искажений сигнала.</span><span class="sxs-lookup"><span data-stu-id="525b0-p110">Average ratio of concealed audio samples to the total to the total number of samples. (A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="525b0-186"><strong>Степень растянутых образцов</strong></span><span class="sxs-lookup"><span data-stu-id="525b0-186"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="525b0-187">Да</span><span class="sxs-lookup"><span data-stu-id="525b0-187">Yes</span></span></p></td>
<td><p><span data-ttu-id="525b0-p111">Средняя степень растянутых аудиообразцов по отношению к общему числу образцов. (Растягивание аудиопакета - это методика, которая применяется для поддержания качества звонка при обнаружении потери сетевого пакета). Большие значения обозначают частое применение данной методики, вызванное большими искажениями – аудиосигнал звучит как роботизированный.</span><span class="sxs-lookup"><span data-stu-id="525b0-p111">Average ratio of stretched audio samples to the total to the total number of samples. (Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="525b0-190"><strong>Степень сжатых аудиообразцов</strong></span><span class="sxs-lookup"><span data-stu-id="525b0-190"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="525b0-191">Да</span><span class="sxs-lookup"><span data-stu-id="525b0-191">Yes</span></span></p></td>
<td><p><span data-ttu-id="525b0-p112">Средняя степень растянутых аудиообразцов по отношению к общему числу образцов. (Сжатие аудиопакета - это методика, которая применяется для поддержания качества звонка при обнаружении потери сетевого пакета). Большие значения обозначают частое применение данной методики, вызванное большими искажениями – аудиосигнал звучит как ускоренный или искаженный.</span><span class="sxs-lookup"><span data-stu-id="525b0-p112">Average ratio of compressed audio samples to the total number of samples. (Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="525b0-194"><strong>Подключение</strong></span><span class="sxs-lookup"><span data-stu-id="525b0-194"><strong>Connectivity</strong></span></span></p></td>
<td><p><span data-ttu-id="525b0-195">Да</span><span class="sxs-lookup"><span data-stu-id="525b0-195">Yes</span></span></p></td>
<td><p><span data-ttu-id="525b0-p113">Типа канала беспроводной связи. Как правило, используется один из следующих каналов:</span><span class="sxs-lookup"><span data-stu-id="525b0-p113">Type of wireless communication link. Typically, this is one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="525b0-198">Ретрансляция</span><span class="sxs-lookup"><span data-stu-id="525b0-198">Relay</span></span></p></li>
<li><p><span data-ttu-id="525b0-199">Прямое подключение</span><span class="sxs-lookup"><span data-stu-id="525b0-199">Direct</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

