---
title: 'Lync Server 2013: отчет о звонке'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call Detail Report
ms:assetid: 38862e35-3fec-41b9-a035-0b301942d446
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558637(v=OCS.15)
ms:contentKeyID: 48183843
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ffbfa8c3553b33f75b0f014265f93cccf46e7de6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743159"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-detail-report-in-lync-server-2013"></a><span data-ttu-id="b189b-102">Подробный отчет о звонке в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b189b-102">Call Detail Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b189b-103">_**Тема последнего изменения:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="b189b-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="b189b-104">В отчете подробных сведений о звонке подробно рассматривается отдельный звонок. отчет включает почти все показатели качества взаимодействия и статистику, собранные приложением Lync Server, разделенные на разделы отчета, такие как:</span><span class="sxs-lookup"><span data-stu-id="b189b-104">The Call Detail Report provides a detailed look at an individual call; the report includes nearly all the Quality of Experience metrics and statistics collected by Lync Server, divided into report sections such as:</span></span>

  - <span data-ttu-id="b189b-105">Call Information (Сведения о вызове)</span><span class="sxs-lookup"><span data-stu-id="b189b-105">Call Information</span></span>

  - <span data-ttu-id="b189b-106">Caller Device and Signal Metrics (Метрики сигнала и устройства вызывающего абонента)</span><span class="sxs-lookup"><span data-stu-id="b189b-106">Caller Device and Signal Metrics</span></span>

  - <span data-ttu-id="b189b-107">Callee Device and Signal Metrics (Метрики сигнала и устройства вызываемого абонента)</span><span class="sxs-lookup"><span data-stu-id="b189b-107">Callee Device and Signal metrics</span></span>

  - <span data-ttu-id="b189b-108">Caller Client Event (Событие клиента вызывающего абонента)</span><span class="sxs-lookup"><span data-stu-id="b189b-108">Caller Client Event</span></span>

  - <span data-ttu-id="b189b-109">Callee Client Event (Событие клиента вызываемого абонента)</span><span class="sxs-lookup"><span data-stu-id="b189b-109">Callee Client Event</span></span>

  - <span data-ttu-id="b189b-110">Audio Stream (Caller to Callee) (Аудиопоток (от вызывающего абонента к вызываемому))</span><span class="sxs-lookup"><span data-stu-id="b189b-110">Audio Stream (Caller to Callee)</span></span>

  - <span data-ttu-id="b189b-111">Video Stream (Caller to Callee) (Видеопоток (от вызывающего абонента к вызываемому))</span><span class="sxs-lookup"><span data-stu-id="b189b-111">Video Stream (Caller to Callee)</span></span>

  - <span data-ttu-id="b189b-112">Audio Stream (Callee to Caller) (Аудиопоток (от вызываемого абонента к вызывающему))</span><span class="sxs-lookup"><span data-stu-id="b189b-112">Audio Stream (Callee to Caller)</span></span>

  - <span data-ttu-id="b189b-113">Video Stream (Callee to Caller) (Видеопоток (от вызываемого абонента к вызывающему))</span><span class="sxs-lookup"><span data-stu-id="b189b-113">Video Stream (Callee to Caller)</span></span>

<span data-ttu-id="b189b-p101">Следует помнить, что категории и метрики, которые можно видеть в данном отчете, зависят от типа сеанса и типа конечных точек, используемых в сеансе. Например, отчет по аудиовызову не будет содержать метрики для видеопотоков, поскольку в этом вызове не было никаких видеопотоков. Аналогично, может быть отчет, в котором есть статистика вызывающего абонента, но отсутствует статистика вызываемого абонента, обычно в том случае, если вызываемый абонент использовал устройство, несовместимое с SIP. Конечные точки отвечают за статистику отчета в конце вызова; однако мобильный телефон (который ничего не знает о SIP и о статистике SIP) не в состоянии сообщить такого рода сведения. Если вызываемый абонент отвечает на вызов со своего мобильного телефона, то по завершении вызова вы не получите отчет от этого мобильного телефона.</span><span class="sxs-lookup"><span data-stu-id="b189b-p101">Keep in mind that the categories and the metrics you see on a given report depend on two things: the type of session and the type of endpoints used in the session. For example, an audio-only call will not report metrics for video streams; that's because the call didn't have a video stream. Likewise, you might have a report that lists caller statistics but not callee statistics. That's typically because the callee was not using a SIP-compliant device. Endpoints are responsible for reporting statistics at the end of a call; however, a cell phone (which knows nothing about SIP or SIP statistics) is unable to report that kind of information. If you call someone and they answer you on their cell phone, you will not get a report from that cell phone when the call ends.</span></span>

<span data-ttu-id="b189b-120">Подробный отчет по вызову особенно полезен в том случае, когда требуется точно определить, почему в конкретном вызове наблюдались проблемы с качеством мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="b189b-120">The Call Detail Report is most useful when you are trying to determine exactly why a given call experienced media quality problems.</span></span>

<div>

## <a name="accessing-the-call-detail-report"></a><span data-ttu-id="b189b-121">Доступ к подробному отчету по вызову</span><span class="sxs-lookup"><span data-stu-id="b189b-121">Accessing the Call Detail Report</span></span>

<span data-ttu-id="b189b-122">Доступ к подробному отчету по вызову можно получить из любого из следующих отчетов.</span><span class="sxs-lookup"><span data-stu-id="b189b-122">The Call Detail Report can be accessed from any of the following reports:</span></span>

  - <span data-ttu-id="b189b-123">[Отчет о расположении в Lync Server 2013](lync-server-2013-location-report.md) (с помощью кнопки "позвонить" или "процент неудовлетворительного звонка")</span><span class="sxs-lookup"><span data-stu-id="b189b-123">The [Location Report in Lync Server 2013](lync-server-2013-location-report.md) (by clicking either the Call volume or the Poor call percentage metric)</span></span>

  - <span data-ttu-id="b189b-124">[Сводный отчет о качестве качества мультимедиа в Lync Server 2013](lync-server-2013-media-quality-summary-report.md) (с помощью которого можно выбрать громкость звонка или метрику процента снижения звонка)</span><span class="sxs-lookup"><span data-stu-id="b189b-124">The [Media Quality Summary Report in Lync Server 2013](lync-server-2013-media-quality-summary-report.md) (by clicking either the Call volume or Poor call percentage metric)</span></span>

  - <span data-ttu-id="b189b-125">[Отчет о сравнении качества мультимедиа в Lync server 2013](lync-server-2013-media-quality-comparison-report.md) (щелчок по [отчету "список обзвона" в Lync Server 2013](lync-server-2013-call-list-report.md) и выбор подробной метрики).</span><span class="sxs-lookup"><span data-stu-id="b189b-125">The [Media Quality Comparison Report in Lync Server 2013](lync-server-2013-media-quality-comparison-report.md) (by clicking the [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) and then clicking the Detail metric).</span></span>

  - <span data-ttu-id="b189b-126">[Отчет о производительности сервера в Lync server 2013](lync-server-2013-server-performance-report.md) (по щелчку на томе звонка или в процентах от плохого звонка)</span><span class="sxs-lookup"><span data-stu-id="b189b-126">The [Server Performance Report in Lync Server 2013](lync-server-2013-server-performance-report.md) (by clicking either the Call volume or Poor call percentage metric)</span></span>

  - <span data-ttu-id="b189b-127">[Отчет "список обзвона" в Lync Server 2013](lync-server-2013-call-list-report.md) (щелчок подробной метрики)</span><span class="sxs-lookup"><span data-stu-id="b189b-127">The [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) (by clicking the Detail metric)</span></span>

<span data-ttu-id="b189b-128">В отчете сведения о звонке вы можете получить доступ к [отчету об устройстве в Lync Server 2013](lync-server-2013-device-report.md) , выбрав один из указанных ниже метрик.</span><span class="sxs-lookup"><span data-stu-id="b189b-128">From within the Call Detail Report you can access the [Device Report in Lync Server 2013](lync-server-2013-device-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="b189b-129">Устройства захвата</span><span class="sxs-lookup"><span data-stu-id="b189b-129">Capture device</span></span>

  - <span data-ttu-id="b189b-130">Устройства обработки</span><span class="sxs-lookup"><span data-stu-id="b189b-130">Render device</span></span>

<span data-ttu-id="b189b-131">Можно также получить доступ к отчету по тенденциям качества мультимедиа на серверах, нажав метрику пограничного сервера аудио- и видеосвязи.</span><span class="sxs-lookup"><span data-stu-id="b189b-131">You can also access the Server Media Quality Trend Report by clicking the A/V edge server metric.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-call-detail-report"></a><span data-ttu-id="b189b-132">Эффективное использование подробного отчета по вызову</span><span class="sxs-lookup"><span data-stu-id="b189b-132">Making the Best Use of the Call Detail Report</span></span>

<span data-ttu-id="b189b-p102">Обычно в подробном отчете по вызову содержится более 250 разных метрик, включая такие, как уход отметки времени микрофона, низкое отношение "сигнал-шум", ближний конец ко времени эхо-задержки. Если вы не можете запомнить, что эти метрики измеряют в действительности, попробуйте задержать указатель мыши на метке метрики; часто при этом появляется всплывающая подсказка, которая описывает эту метрику.</span><span class="sxs-lookup"><span data-stu-id="b189b-p102">The Call Detail Report typically includes over 250 different metrics, including such items as Microphone timestamp drift, Low SNR time, and Near end to echo time. If you can't remember what all of these metrics actually measure, try holding your mouse over the metric label; often-times, a tooltip will appear describing that metric.</span></span>

<span data-ttu-id="b189b-135">Если у вас возникли проблемы при поиске метрики, введите часть метки метрики в поле поиска и нажмите кнопку найти.</span><span class="sxs-lookup"><span data-stu-id="b189b-135">If you have problems locating a metric, type part of the metric label in the search box and then click Find.</span></span> <span data-ttu-id="b189b-136">Например, если не удается найти метрику SNR Time, введите в поле поиска SNR и нажмите кнопку найти.</span><span class="sxs-lookup"><span data-stu-id="b189b-136">For example, if you can't find the Low SNR time metric, type SNR in the search box and then click Find.</span></span>

<span data-ttu-id="b189b-p104">Обратите внимание, что в этом отчете отслеживается информация только о вызове. Сам вызов не записывается.</span><span class="sxs-lookup"><span data-stu-id="b189b-p104">Note that the report only tracks information about a call. The call itself is not recorded.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="b189b-139">Фильтры</span><span class="sxs-lookup"><span data-stu-id="b189b-139">Filters</span></span>

<span data-ttu-id="b189b-p105">Нет. Фильтрация подробного отчета по вызову невозможна.</span><span class="sxs-lookup"><span data-stu-id="b189b-p105">None. You cannot filter the Call Detail Report.</span></span>

</div>

<div>

## <a name="metrics"></a><span data-ttu-id="b189b-142">Показатели</span><span class="sxs-lookup"><span data-stu-id="b189b-142">Metrics</span></span>

<span data-ttu-id="b189b-143">В следующей таблице представлен список данных, которые предоставляются в подробном отчете по вызову для каждого вызова.</span><span class="sxs-lookup"><span data-stu-id="b189b-143">The following table lists the information provided in the Call Detail Report for each call.</span></span>

### <a name="call-detail-report-metrics"></a><span data-ttu-id="b189b-144">Метрики подробного отчета по вызову</span><span class="sxs-lookup"><span data-stu-id="b189b-144">Call Detail Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b189b-145">Имя</span><span class="sxs-lookup"><span data-stu-id="b189b-145">Name</span></span></th>
<th><span data-ttu-id="b189b-146">Поддержка сортировки</span><span class="sxs-lookup"><span data-stu-id="b189b-146">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="b189b-147">Описание</span><span class="sxs-lookup"><span data-stu-id="b189b-147">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b189b-148"><strong>Caller PAI (PAI вызывающего абонента)</strong></span><span class="sxs-lookup"><span data-stu-id="b189b-148"><strong>Caller PAI</strong></span></span></p></td>
<td><p><span data-ttu-id="b189b-149">Нет</span><span class="sxs-lookup"><span data-stu-id="b189b-149">No</span></span></p></td>
<td><p><span data-ttu-id="b189b-p106">Параметр P-Asserted-Identity пользователя, который инициировал вызов. Параметр P-Asserted-Identity используется для передачи подтвержденного удостоверения пользователя в рамках надежной сети.</span><span class="sxs-lookup"><span data-stu-id="b189b-p106">P-Asserted-Identity of the user who initiated the call. The P-Asserted-Identity is used to convey the proven identity of a user within a trusted network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b189b-152"><strong>Caller URI (URI вызывающего абонента)</strong></span><span class="sxs-lookup"><span data-stu-id="b189b-152"><strong>Caller URI</strong></span></span></p></td>
<td><p><span data-ttu-id="b189b-153">Нет</span><span class="sxs-lookup"><span data-stu-id="b189b-153">No</span></span></p></td>
<td><p><span data-ttu-id="b189b-154">SIP-адрес пользователя, инициировавшего вызов.</span><span class="sxs-lookup"><span data-stu-id="b189b-154">SIP address of the user who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b189b-155"><strong>Caller endpoint (Конечная точка вызывающего абонента)</strong></span><span class="sxs-lookup"><span data-stu-id="b189b-155"><strong>Caller endpoint</strong></span></span></p></td>
<td><p><span data-ttu-id="b189b-156">Нет</span><span class="sxs-lookup"><span data-stu-id="b189b-156">No</span></span></p></td>
<td><p><span data-ttu-id="b189b-157">Устройство, использовавшееся для выполнения вызова.</span><span class="sxs-lookup"><span data-stu-id="b189b-157">Device used to make the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b189b-158"><strong>Caller user agent (Агент вызывающего пользователя)</strong></span><span class="sxs-lookup"><span data-stu-id="b189b-158"><strong>Caller user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="b189b-159">Нет</span><span class="sxs-lookup"><span data-stu-id="b189b-159">No</span></span></p></td>
<td><p><span data-ttu-id="b189b-160">Программное обеспечение, использовавшееся в устройстве, выполнившем вызов.</span><span class="sxs-lookup"><span data-stu-id="b189b-160">Software used on the device that made the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b189b-161"><strong>Call start (Начало вызова)</strong></span><span class="sxs-lookup"><span data-stu-id="b189b-161"><strong>Call start</strong></span></span></p></td>
<td><p><span data-ttu-id="b189b-162">Нет</span><span class="sxs-lookup"><span data-stu-id="b189b-162">No</span></span></p></td>
<td><p><span data-ttu-id="b189b-163">Дата и время первоначального размещения вызова.</span><span class="sxs-lookup"><span data-stu-id="b189b-163">Date and time that the call was initially placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b189b-164"><strong>Mediation Server bypass call (Вызов с обходом сервера-посредника)</strong></span><span class="sxs-lookup"><span data-stu-id="b189b-164"><strong>Mediation Server bypass call</strong></span></span></p></td>
<td><p><span data-ttu-id="b189b-165">Нет</span><span class="sxs-lookup"><span data-stu-id="b189b-165">No</span></span></p></td>
<td><p><span data-ttu-id="b189b-166">Указывает, подключался ли вызов к голосовому шлюзу ТСОП или к соответствующей IP-УАТС без прохода через сервер-посредник.</span><span class="sxs-lookup"><span data-stu-id="b189b-166">Indicates whether the call connected to a PSTN voice gateway or qualified IP-PBX without passing through the Mediation Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b189b-167"><strong>Caller OS (ОС вызывающего абонента)</strong></span><span class="sxs-lookup"><span data-stu-id="b189b-167"><strong>Caller OS</strong></span></span></p></td>
<td><p><span data-ttu-id="b189b-168">Нет</span><span class="sxs-lookup"><span data-stu-id="b189b-168">No</span></span></p></td>
<td><p><span data-ttu-id="b189b-169">Операционная система компьютера вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="b189b-169">Operating system of the caller's computer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b189b-170"><strong>Caller CPU (ЦП вызывающего абонента)</strong></span><span class="sxs-lookup"><span data-stu-id="b189b-170"><strong>Caller CPU</strong></span></span></p></td>
<td><p><span data-ttu-id="b189b-171">Нет</span><span class="sxs-lookup"><span data-stu-id="b189b-171">No</span></span></p></td>
<td><p><span data-ttu-id="b189b-172">Центральный процессор, установленный на компьютере пользователя, который инициировал вызов.</span><span class="sxs-lookup"><span data-stu-id="b189b-172">CPU installed in the computer of the user who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b189b-173"><strong>Caller CPU core number (Количество ядер ЦП вызывающего абонента)</strong></span><span class="sxs-lookup"><span data-stu-id="b189b-173"><strong>Caller CPU core number</strong></span></span></p></td>
<td><p><span data-ttu-id="b189b-174">Нет</span><span class="sxs-lookup"><span data-stu-id="b189b-174">No</span></span></p></td>
<td><p><span data-ttu-id="b189b-175">Количество процессоров в компьютере пользователя, инициировавшего вызов.</span><span class="sxs-lookup"><span data-stu-id="b189b-175">Processor number in the computer used by the person who initiated the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b189b-176"><strong>Caller CPU speed (Частота ЦП вызывающего абонента)</strong></span><span class="sxs-lookup"><span data-stu-id="b189b-176"><strong>Caller CPU speed</strong></span></span></p></td>
<td><p><span data-ttu-id="b189b-177">Нет</span><span class="sxs-lookup"><span data-stu-id="b189b-177">No</span></span></p></td>
<td><p><span data-ttu-id="b189b-178">Тактовая частота центрального процессора компьютера пользователя, инициировавшего вызов.</span><span class="sxs-lookup"><span data-stu-id="b189b-178">Clock speed of the CPU of the computer used by the person who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b189b-179"><strong>Caller CPU virtualization (Виртуализация ЦП вызывающего абонента)</strong></span><span class="sxs-lookup"><span data-stu-id="b189b-179"><strong>Caller CPU virtualization</strong></span></span></p></td>
<td><p><span data-ttu-id="b189b-180">Нет</span><span class="sxs-lookup"><span data-stu-id="b189b-180">No</span></span></p></td>
<td><p><span data-ttu-id="b189b-181">Виртуализация, использовавшаяся на компьютере пользователя, инициировавшего вызов (если виртуализация использовалась).</span><span class="sxs-lookup"><span data-stu-id="b189b-181">Virtualization (if any) used on the computer used by the person who initiated the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b189b-182"><strong>Callee PAI (PAI вызываемого абонента)</strong></span><span class="sxs-lookup"><span data-stu-id="b189b-182"><strong>Callee PAI</strong></span></span></p></td>
<td><p><span data-ttu-id="b189b-183">Нет</span><span class="sxs-lookup"><span data-stu-id="b189b-183">No</span></span></p></td>
<td><p><span data-ttu-id="b189b-p107">Параметр P-Asserted-Identity пользователя, который получил вызов. Параметр P-Asserted-Identity используется для передачи подтвержденного удостоверения пользователя в рамках надежной сети.</span><span class="sxs-lookup"><span data-stu-id="b189b-p107">P-Asserted-Identity of the user who was invited to join the call. The P-Asserted-Identity is used to convey the proven identity of a user within a trusted network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b189b-186"><strong>Callee URI (URI вызываемого абонента)</strong></span><span class="sxs-lookup"><span data-stu-id="b189b-186"><strong>Callee URI</strong></span></span></p></td>
<td><p><span data-ttu-id="b189b-187">Нет</span><span class="sxs-lookup"><span data-stu-id="b189b-187">No</span></span></p></td>
<td><p><span data-ttu-id="b189b-188">SIP-адрес пользователя, который принял вызов.</span><span class="sxs-lookup"><span data-stu-id="b189b-188">SIP address of the user who was called.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b189b-189"><strong>Callee endpoint (Конечная точка вызываемого абонента)</strong></span><span class="sxs-lookup"><span data-stu-id="b189b-189"><strong>Callee endpoint</strong></span></span></p></td>
<td><p><span data-ttu-id="b189b-190">Нет</span><span class="sxs-lookup"><span data-stu-id="b189b-190">No</span></span></p></td>
<td><p><span data-ttu-id="b189b-191">Устройство, использовавшееся для принятия вызова.</span><span class="sxs-lookup"><span data-stu-id="b189b-191">Device used to receive the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b189b-192"><strong>Callee user agent (Агент вызываемого пользователя)</strong></span><span class="sxs-lookup"><span data-stu-id="b189b-192"><strong>Callee user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="b189b-193">Нет</span><span class="sxs-lookup"><span data-stu-id="b189b-193">No</span></span></p></td>
<td><p><span data-ttu-id="b189b-194">Программное обеспечение, использовавшееся в устройстве, принявшем вызов.</span><span class="sxs-lookup"><span data-stu-id="b189b-194">Software used on the device that received the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b189b-195"><strong>Duration (Длительность)</strong></span><span class="sxs-lookup"><span data-stu-id="b189b-195"><strong>Duration</strong></span></span></p></td>
<td><p><span data-ttu-id="b189b-196">Нет</span><span class="sxs-lookup"><span data-stu-id="b189b-196">No</span></span></p></td>
<td><p><span data-ttu-id="b189b-197">Продолжительность (время) вызова.</span><span class="sxs-lookup"><span data-stu-id="b189b-197">Length of time for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b189b-198"><strong>Media bypass warning flag (Флаг предупреждения об обходе сервера-посредника)</strong></span><span class="sxs-lookup"><span data-stu-id="b189b-198"><strong>Media bypass warning flag</strong></span></span></p></td>
<td><p><span data-ttu-id="b189b-199">Нет</span><span class="sxs-lookup"><span data-stu-id="b189b-199">No</span></span></p></td>
<td><p><span data-ttu-id="b189b-200">Предупреждение, которое выдается при обходе сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="b189b-200">Warning issued when the Mediation Server was bypassed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b189b-201"><strong>Callee OS (ОС вызываемого абонента)</strong></span><span class="sxs-lookup"><span data-stu-id="b189b-201"><strong>Callee OS</strong></span></span></p></td>
<td><p><span data-ttu-id="b189b-202">Нет</span><span class="sxs-lookup"><span data-stu-id="b189b-202">No</span></span></p></td>
<td><p><span data-ttu-id="b189b-203">Операционная система компьютера вызванного пользователя.</span><span class="sxs-lookup"><span data-stu-id="b189b-203">Operating system of the computer for the user who was called.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b189b-204"><strong>Callee CPU (ЦП вызываемого абонента)</strong></span><span class="sxs-lookup"><span data-stu-id="b189b-204"><strong>Callee CPU</strong></span></span></p></td>
<td><p><span data-ttu-id="b189b-205">Нет</span><span class="sxs-lookup"><span data-stu-id="b189b-205">No</span></span></p></td>
<td><p><span data-ttu-id="b189b-206">Центральный процессор, установленный на компьютере вызванного пользователя.</span><span class="sxs-lookup"><span data-stu-id="b189b-206">CPU installed in the computer of the user who was called.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b189b-207"><strong>Callee core number (Количество ядер ЦП вызываемого абонента)</strong></span><span class="sxs-lookup"><span data-stu-id="b189b-207"><strong>Callee core number</strong></span></span></p></td>
<td><p><span data-ttu-id="b189b-208">Нет</span><span class="sxs-lookup"><span data-stu-id="b189b-208">No</span></span></p></td>
<td><p><span data-ttu-id="b189b-209">Количество процессоров в компьютере вызванного пользователя.</span><span class="sxs-lookup"><span data-stu-id="b189b-209">Processor number in the computer used by the person who was called.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b189b-210"><strong>Callee CPU speed (Частота ЦП вызываемого абонента)</strong></span><span class="sxs-lookup"><span data-stu-id="b189b-210"><strong>Callee CPU speed</strong></span></span></p></td>
<td><p><span data-ttu-id="b189b-211">Нет</span><span class="sxs-lookup"><span data-stu-id="b189b-211">No</span></span></p></td>
<td><p><span data-ttu-id="b189b-212">Тактовая частота центрального процессора компьютера вызванного пользователя.</span><span class="sxs-lookup"><span data-stu-id="b189b-212">Clock speed of the CPU of the computer used by the person who was called.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b189b-213"><strong>Callee CPU virtualization (Виртуализация ЦП вызываемого абонента)</strong></span><span class="sxs-lookup"><span data-stu-id="b189b-213"><strong>Callee CPU virtualization</strong></span></span></p></td>
<td><p><span data-ttu-id="b189b-214">Нет</span><span class="sxs-lookup"><span data-stu-id="b189b-214">No</span></span></p></td>
<td><p><span data-ttu-id="b189b-215">Виртуализация, использовавшаяся на компьютере вызванного пользователя (если виртуализация использовалась).</span><span class="sxs-lookup"><span data-stu-id="b189b-215">Virtualization (if any) used on the computer used by the person who was called.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

