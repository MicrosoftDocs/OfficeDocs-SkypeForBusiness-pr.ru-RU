---
title: 'Lync Server 2013: отчет по списку обзвона'
description: 'Lync Server 2013: отчет по списку обзвона.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call List Report
ms:assetid: 9739f9f0-7a37-4844-91d5-f089d2011013
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615020(v=OCS.15)
ms:contentKeyID: 48184921
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5b08d4c5f3011facc9cd8d4f6b2800638f3cc896
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561695"
---
# <a name="call-list-report-in-lync-server-2013"></a><span data-ttu-id="425d5-103">Отчет по списку обзвона в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="425d5-103">Call List Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="425d5-104">_**Последнее изменение темы:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="425d5-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="425d5-105">Отчет по списку обзвона предоставляет параметры качества взаимодействия (QoE) для отдельных вызовов, выполненных и принятых сотрудниками организации.</span><span class="sxs-lookup"><span data-stu-id="425d5-105">The Call List Report provides Quality of Experience (QoE) metrics for individual calls made and received in your organization.</span></span> <span data-ttu-id="425d5-106">Обратите внимание, что действительные параметры, содержащиеся в отчете, зависят от способа доступа к отчету по списку обзвона.</span><span class="sxs-lookup"><span data-stu-id="425d5-106">Note that the actual metrics reported will depend on how you access the Call List report.</span></span> <span data-ttu-id="425d5-107">Например, если вы откроете отчет из [отчета по устройствам в Lync Server 2013](lync-server-2013-device-report.md), вы увидите следующие метрики, которые также включаются в отчет по устройствам:</span><span class="sxs-lookup"><span data-stu-id="425d5-107">For example, if you open the report from the [Device Report in Lync Server 2013](lync-server-2013-device-report.md), you'll see metrics such as the following, metrics that are also reported on the Device Report:</span></span>

  - <span data-ttu-id="425d5-108">Микрофон вызывающего абонента</span><span class="sxs-lookup"><span data-stu-id="425d5-108">Caller's microphone</span></span>

  - <span data-ttu-id="425d5-109">Динамик вызывающего абонента</span><span class="sxs-lookup"><span data-stu-id="425d5-109">Caller's speaker</span></span>

  - <span data-ttu-id="425d5-110">Микрофон вызываемого абонента</span><span class="sxs-lookup"><span data-stu-id="425d5-110">Callee's microphone</span></span>

  - <span data-ttu-id="425d5-111">Динамик вызываемого абонента</span><span class="sxs-lookup"><span data-stu-id="425d5-111">Callee's speaker</span></span>

  - <span data-ttu-id="425d5-112">Соотношение времени голосовой коммутации</span><span class="sxs-lookup"><span data-stu-id="425d5-112">Ratio of voice switch time</span></span>

<span data-ttu-id="425d5-113">Тем не менее, если вы откроете отчет по списку обзвона из [отчета о местоположении в Lync Server 2013](lync-server-2013-location-report.md), эти показатели не будут отображаться; Вместо этого вы увидите следующие показатели:</span><span class="sxs-lookup"><span data-stu-id="425d5-113">However, if you open the Call List Report from the [Location Report in Lync Server 2013](lync-server-2013-location-report.md), you won't see any of those metrics; instead, you'll see metrics like these:</span></span>

  - <span data-ttu-id="425d5-114">Round trip (ms)
(Круговой путь (мс))</span><span class="sxs-lookup"><span data-stu-id="425d5-114">Round trip (ms)</span></span>

  - <span data-ttu-id="425d5-115">Degradation (MOS) (Снижение (MOS))</span><span class="sxs-lookup"><span data-stu-id="425d5-115">Degradation (MOS)</span></span>

  - <span data-ttu-id="425d5-116">Packet loss (Потеря пакетов)</span><span class="sxs-lookup"><span data-stu-id="425d5-116">Packet loss</span></span>

  - <span data-ttu-id="425d5-117">Колебание (мс)</span><span class="sxs-lookup"><span data-stu-id="425d5-117">Jitter (ms)</span></span>

<span data-ttu-id="425d5-p102">Это показатели, содержащиеся в отчете о местоположении. Однако вы всегда можете щелкнуть «Подробные показатели» в отчете по списку обзвона, чтобы получить полную информацию QoE для любого вызова.</span><span class="sxs-lookup"><span data-stu-id="425d5-p102">Those are the metrics reported on the Location Report. However, from the Call List Report you can always click the Detail metric to provide complete QoE information for any call.</span></span>

<div>

## <a name="accessing-the-call-list-report"></a><span data-ttu-id="425d5-120">Доступ к отчету по списку обзвона</span><span class="sxs-lookup"><span data-stu-id="425d5-120">Accessing the Call List Report</span></span>

<span data-ttu-id="425d5-121">Доступ к отчету по списку обзвона можно получить из любого из следующих отчетов:</span><span class="sxs-lookup"><span data-stu-id="425d5-121">The Call List Report can be accessed from any of the following reports:</span></span>

  - <span data-ttu-id="425d5-122">[Отчет о местоположении в Lync Server 2013](lync-server-2013-location-report.md) (щелкните метрику громкости вызова или процента звонков низкого качества)</span><span class="sxs-lookup"><span data-stu-id="425d5-122">The [Location Report in Lync Server 2013](lync-server-2013-location-report.md) (by clicking the Call volume or Poor call percentage metric)</span></span>

  - <span data-ttu-id="425d5-123">[Отчет по устройствам в Lync Server 2013](lync-server-2013-device-report.md) (щелкните метрику громкости вызова или процента звонков низкого качества)</span><span class="sxs-lookup"><span data-stu-id="425d5-123">The [Device Report in Lync Server 2013](lync-server-2013-device-report.md) (by clicking the Call volume or Poor call percentage metric)</span></span>

  - <span data-ttu-id="425d5-124">[Сводный отчет по качеству мультимедиа в Lync Server 2013](lync-server-2013-media-quality-summary-report.md) (щелкнув метрику громкости вызова или процента звонков низкого качества)</span><span class="sxs-lookup"><span data-stu-id="425d5-124">The [Media Quality Summary Report in Lync Server 2013](lync-server-2013-media-quality-summary-report.md) (by clicking the Call volume or Poor call percentage metric)</span></span>

  - <span data-ttu-id="425d5-125">[Отчет о производительности сервера в Lync server 2013](lync-server-2013-server-performance-report.md) (щелкнув метрику громкости вызова или процента звонков низкого качества)</span><span class="sxs-lookup"><span data-stu-id="425d5-125">The [Server Performance Report in Lync Server 2013](lync-server-2013-server-performance-report.md) (by clicking the Call volume or Poor call percentage metric)</span></span>

<span data-ttu-id="425d5-126">В отчете по списку обзвона можно получить доступ к [подробному отчету по вызову в Lync Server 2013](lync-server-2013-call-detail-report.md) , щелкнув метрику Detail.</span><span class="sxs-lookup"><span data-stu-id="425d5-126">From within the Call List Report you can access the [Call Detail Report in Lync Server 2013](lync-server-2013-call-detail-report.md) by clicking the Detail metric.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-call-list-report"></a><span data-ttu-id="425d5-127">Эффективное использование отчета по списку обзвона</span><span class="sxs-lookup"><span data-stu-id="425d5-127">Making the Best Use of the Call List Report</span></span>

<span data-ttu-id="425d5-128">Если вы не помните, для чего именно используются некоторые показатели отчета по списку обзвона (например, «Соотношение времени голосовой коммутации»), наведите указатель мыши на метку показателя; отобразится всплывающая подсказка, содержащая краткое описание показателя.</span><span class="sxs-lookup"><span data-stu-id="425d5-128">If you can't remember what some of the Call List Report metrics (such as Ratio voice switch time) actually measure, hold your mouse over the metric label; a tool tip will then appear giving you a brief description of the metric.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="425d5-129">Фильтры</span><span class="sxs-lookup"><span data-stu-id="425d5-129">Filters</span></span>

<span data-ttu-id="425d5-p103">Нет. Фильтрация отчета по списку обзвона невозможна.</span><span class="sxs-lookup"><span data-stu-id="425d5-p103">None. You cannot filter the Call List Report.</span></span>

</div>

<div>

## <a name="metrics"></a><span data-ttu-id="425d5-132">Метрики</span><span class="sxs-lookup"><span data-stu-id="425d5-132">Metrics</span></span>

<span data-ttu-id="425d5-133">В следующей таблице представлен список данных, которые приводятся в отчете по списку обзвона для каждого вызова.</span><span class="sxs-lookup"><span data-stu-id="425d5-133">The following table lists the information provided in the Call List Report for each call.</span></span>

### <a name="call-list-report-metrics"></a><span data-ttu-id="425d5-134">Показатели в отчете по списку обзвона</span><span class="sxs-lookup"><span data-stu-id="425d5-134">Call List Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="425d5-135">Имя</span><span class="sxs-lookup"><span data-stu-id="425d5-135">Name</span></span></th>
<th><span data-ttu-id="425d5-136">Возможность сортировки по этому показателю</span><span class="sxs-lookup"><span data-stu-id="425d5-136">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="425d5-137">Описание</span><span class="sxs-lookup"><span data-stu-id="425d5-137">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="425d5-138"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="425d5-138"><strong>Details</strong></span></span></p></td>
<td><p><span data-ttu-id="425d5-139">Нет</span><span class="sxs-lookup"><span data-stu-id="425d5-139">No</span></span></p></td>
<td><p><span data-ttu-id="425d5-140">Если щелкнуть этот элемент, в отчете отображается дополнительная информация о вызове.</span><span class="sxs-lookup"><span data-stu-id="425d5-140">When you click this item, the report shows additional information on the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="425d5-141"><strong>Caller</strong></span><span class="sxs-lookup"><span data-stu-id="425d5-141"><strong>Caller</strong></span></span></p></td>
<td><p><span data-ttu-id="425d5-142">Да</span><span class="sxs-lookup"><span data-stu-id="425d5-142">Yes</span></span></p></td>
<td><p><span data-ttu-id="425d5-143">SIP-адрес пользователя, инициировавшего вызов.</span><span class="sxs-lookup"><span data-stu-id="425d5-143">SIP address of the person who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="425d5-144"><strong>Вызываемого абонента</strong></span><span class="sxs-lookup"><span data-stu-id="425d5-144"><strong>Callee</strong></span></span></p></td>
<td><p><span data-ttu-id="425d5-145">Да</span><span class="sxs-lookup"><span data-stu-id="425d5-145">Yes</span></span></p></td>
<td><p><span data-ttu-id="425d5-146">SIP-адрес пользователя, который принял вызов.</span><span class="sxs-lookup"><span data-stu-id="425d5-146">SIP address of the person who was called.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="425d5-147"><strong>Время начала</strong></span><span class="sxs-lookup"><span data-stu-id="425d5-147"><strong>Start time</strong></span></span></p></td>
<td><p><span data-ttu-id="425d5-148">Да</span><span class="sxs-lookup"><span data-stu-id="425d5-148">Yes</span></span></p></td>
<td><p><span data-ttu-id="425d5-149">Дата и время начала вызова.</span><span class="sxs-lookup"><span data-stu-id="425d5-149">Date and time that the call started.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="425d5-150"><strong>Время окончания</strong></span><span class="sxs-lookup"><span data-stu-id="425d5-150"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="425d5-151">Да</span><span class="sxs-lookup"><span data-stu-id="425d5-151">Yes</span></span></p></td>
<td><p><span data-ttu-id="425d5-152">Дата и время завершения вызова.</span><span class="sxs-lookup"><span data-stu-id="425d5-152">Date and time that the call ended.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="425d5-153"><strong>Агент вызывающего пользователя</strong></span><span class="sxs-lookup"><span data-stu-id="425d5-153"><strong>Caller user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="425d5-154">Да</span><span class="sxs-lookup"><span data-stu-id="425d5-154">Yes</span></span></p></td>
<td><p><span data-ttu-id="425d5-155">Программное обеспечение, используемое конечной точкой пользователя, который инициировал вызов.</span><span class="sxs-lookup"><span data-stu-id="425d5-155">Software used by the endpoint of the person who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="425d5-156"><strong>Агент вызываемого пользователя</strong></span><span class="sxs-lookup"><span data-stu-id="425d5-156"><strong>Callee user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="425d5-157">Да</span><span class="sxs-lookup"><span data-stu-id="425d5-157">Yes</span></span></p></td>
<td><p><span data-ttu-id="425d5-158">Программное обеспечение, используемое конечной точкой пользователя, который принял вызов.</span><span class="sxs-lookup"><span data-stu-id="425d5-158">Software used by the endpoint of the person who was called.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="425d5-159"><strong>Время кругового пути (мс)</strong></span><span class="sxs-lookup"><span data-stu-id="425d5-159"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="425d5-160">Да</span><span class="sxs-lookup"><span data-stu-id="425d5-160">Yes</span></span></p></td>
<td><p><span data-ttu-id="425d5-p104">Среднее время (в миллисекундах), необходимое для перемещения пакета Real-Time Transport Protocol в другую конечную точку и его возврата. Приемлемым считается время двусторонней передачи, равное 200 мс (или менее).</span><span class="sxs-lookup"><span data-stu-id="425d5-p104">Average amount of (in milliseconds) required for a real-time transport protocol (RTP) packet to travel to another endpoint and then back. Round-trip times of 100 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="425d5-p105">Высокие значения кругового пути могут быть следствием маршрутизации международных вызовов, неправильной настройки маршрутизации или перегруженности сервера мультимедиа. Высокие значения кругового пути осложняют проведение двусторонних бесед в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="425d5-p105">High round-trip values can be caused by international call routing, a routing misconfiguration, or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="425d5-165"><strong>Деградация (MOS)</strong></span><span class="sxs-lookup"><span data-stu-id="425d5-165"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="425d5-166">Да</span><span class="sxs-lookup"><span data-stu-id="425d5-166">Yes</span></span></p></td>
<td><p><span data-ttu-id="425d5-167">Средний объем деградации в соответствии со средней экспертной оценкой разборчивости речи (MOS), наблюдаемый в ходе вызова.</span><span class="sxs-lookup"><span data-stu-id="425d5-167">Average amount of mean opinion score (MOS) degradation experienced during a call.</span></span> <span data-ttu-id="425d5-168">Значение снижения может быть в диапазоне от 0.0 до 5.0.</span><span class="sxs-lookup"><span data-stu-id="425d5-168">Degradation values can range from a low of 0.0 to a high of 5.0.</span></span> <span data-ttu-id="425d5-169">Значение не выше 0.5 является приемлемым уровнем снижения.</span><span class="sxs-lookup"><span data-stu-id="425d5-169">A value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="425d5-170">Традиционно средние экспертные оценки разборчивости речи вычислялись по оценкам пользователей качества вызова по шкале от 1 до 5.</span><span class="sxs-lookup"><span data-stu-id="425d5-170">Historically, mean options scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="425d5-171">В Lync Server Lync Server использует набор алгоритмов для прогнозирования того, как пользователи будут оценены при вызове.</span><span class="sxs-lookup"><span data-stu-id="425d5-171">In Lync Server, Lync Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="425d5-p107">Высокие значения снижения могут быть вызваны перегруженностью, нехваткой пропускной способности, перегруженность или помехами в беспроводной сети, а также перегруженностью сервера мультимедиа или конечной точки. Высокие значения могут привести к искажению или потере звука.</span><span class="sxs-lookup"><span data-stu-id="425d5-p107">High degradation values can be caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server or endpoint. High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="425d5-174"><strong>Потеря пакетов</strong></span><span class="sxs-lookup"><span data-stu-id="425d5-174"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="425d5-175">Да</span><span class="sxs-lookup"><span data-stu-id="425d5-175">Yes</span></span></p></td>
<td><p><span data-ttu-id="425d5-p108">Средний показатель потери пакетов RTP. (Потеря пакетов происходит, когда пакеты RTP (протокол, используемый для передачи видео- и аудиокомпонентов через Интернет) не достигают места назначения.) Высокие значения потери, как правило, обусловлены перегрузкой, недостаточной пропускной способностью, помехами или перегрузкой беспроводной сети либо перегрузкой сервера-посредника. Потеря пакетов обычно приводит к искажению или потере звук.</span><span class="sxs-lookup"><span data-stu-id="425d5-p108">Average rate of RTP packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="425d5-179"><strong>Колебани</strong></span><span class="sxs-lookup"><span data-stu-id="425d5-179"><strong>Jitter</strong></span></span></p></td>
<td><p><span data-ttu-id="425d5-180">Да</span><span class="sxs-lookup"><span data-stu-id="425d5-180">Yes</span></span></p></td>
<td><p><span data-ttu-id="425d5-181">Среднее значение колебаний, зарегистрированных между прибытиями пакетов RTP.</span><span class="sxs-lookup"><span data-stu-id="425d5-181">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="425d5-182">(Колебание — это мера &quot; вибрирования &quot; вызова.) Большие значения колебаний обычно вызваны перегрузкой или перегрузкой сервера мультимедиа, что приводит к искажению или потере звука.</span><span class="sxs-lookup"><span data-stu-id="425d5-182">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="425d5-183"><strong>Соотношение скрытых фрагментов в процессе восстановления</strong></span><span class="sxs-lookup"><span data-stu-id="425d5-183"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="425d5-184">Да</span><span class="sxs-lookup"><span data-stu-id="425d5-184">Yes</span></span></p></td>
<td><p><span data-ttu-id="425d5-p110">Среднее отношение количества скрытых аудиофрагментов к общему количеству фрагментов. (Скрытие аудиофрагментов — это метод, используемый для сглаживания резких переходов, которые обычно вызваны пропуском сетевых пакетов.) Высокие значения указывают на высокие уровни скрытия потерь, которые были обусловлены потерей пакетов или колебаниями. Эти высокие значения приводят к искажению звука или потере аудиосигналов.</span><span class="sxs-lookup"><span data-stu-id="425d5-p110">Average ratio of concealed audio samples to the total to the total number of samples. (A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="425d5-187"><strong>Соотношение растянутых фрагментов в процессе восстановления</strong></span><span class="sxs-lookup"><span data-stu-id="425d5-187"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="425d5-188">Да</span><span class="sxs-lookup"><span data-stu-id="425d5-188">Yes</span></span></p></td>
<td><p><span data-ttu-id="425d5-p111">Среднее отношение количества растянутых аудиофрагментов к общему количеству фрагментов. (Растянутые аудиофрагменты — фрагменты, которые были увеличены для поддержания качества вызова при обнаружении пропуска сетевого пакета.) Высокие значения указывают на значительные уровни растягивания фрагментов, которые были обусловлены колебаниями. Эти высокие значения приводят к искажению звука или к созданию эффекта механического звучания.</span><span class="sxs-lookup"><span data-stu-id="425d5-p111">Average ratio of stretched audio samples to the total to the total number of samples. (Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="425d5-191"><strong>Соотношение сжатых фрагментов в процессе восстановления</strong></span><span class="sxs-lookup"><span data-stu-id="425d5-191"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="425d5-192">Да</span><span class="sxs-lookup"><span data-stu-id="425d5-192">Yes</span></span></p></td>
<td><p><span data-ttu-id="425d5-p112">Среднее отношение количества сжатых аудиофрагментов к общему количеству фрагментов. (Сжатые аудиофрагменты — фрагменты, которые были сжаты для поддержания качества вызова при обнаружении пропуска сетевого пакета.) Высокие значения указывают на значительные уровни сжатия фрагментов, которые были обусловлены колебаниями. Эти высокие значения приводят к искажению звука или к созданию эффекта ускоренного звучания.</span><span class="sxs-lookup"><span data-stu-id="425d5-p112">Average ratio of compressed audio samples to the total number of samples. (Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="425d5-195"><strong>Подключение</strong></span><span class="sxs-lookup"><span data-stu-id="425d5-195"><strong>Connectivity</strong></span></span></p></td>
<td><p><span data-ttu-id="425d5-196">Да</span><span class="sxs-lookup"><span data-stu-id="425d5-196">Yes</span></span></p></td>
<td><p><span data-ttu-id="425d5-p113">Типа канала беспроводной связи. Как правило, используется один из следующих каналов:</span><span class="sxs-lookup"><span data-stu-id="425d5-p113">Type of wireless communication link. Typically, this is one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="425d5-199">Протокол</span><span class="sxs-lookup"><span data-stu-id="425d5-199">Relay</span></span></p></li>
<li><p><span data-ttu-id="425d5-200">Правителе</span><span class="sxs-lookup"><span data-stu-id="425d5-200">Direct</span></span></p></li>
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

