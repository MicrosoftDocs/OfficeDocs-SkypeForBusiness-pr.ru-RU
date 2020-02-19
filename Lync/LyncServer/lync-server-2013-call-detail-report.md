---
title: 'Lync Server 2013: подробный отчет по вызову'
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
ms.openlocfilehash: 49eb77ad61b96e9da793bab8054d1557c3d1a77a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134275"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="call-detail-report-in-lync-server-2013"></a><span data-ttu-id="4dc28-102">Подробный отчет о вызовах в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4dc28-102">Call Detail Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4dc28-103">_**Последнее изменение темы:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="4dc28-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="4dc28-104">Подробный отчет по вызовам предоставляет подробный обзор отдельного вызова; отчет включает почти все показатели качества взаимодействия и статистические данные, собранные в Lync Server, разделенные на разделы отчетов, такие как:</span><span class="sxs-lookup"><span data-stu-id="4dc28-104">The Call Detail Report provides a detailed look at an individual call; the report includes nearly all the Quality of Experience metrics and statistics collected by Lync Server, divided into report sections such as:</span></span>

  - <span data-ttu-id="4dc28-105">Call Information (Сведения о вызове)</span><span class="sxs-lookup"><span data-stu-id="4dc28-105">Call Information</span></span>

  - <span data-ttu-id="4dc28-106">Caller Device and Signal Metrics (Метрики сигнала и устройства вызывающего абонента)</span><span class="sxs-lookup"><span data-stu-id="4dc28-106">Caller Device and Signal Metrics</span></span>

  - <span data-ttu-id="4dc28-107">Callee Device and Signal Metrics (Метрики сигнала и устройства вызываемого абонента)</span><span class="sxs-lookup"><span data-stu-id="4dc28-107">Callee Device and Signal metrics</span></span>

  - <span data-ttu-id="4dc28-108">Caller Client Event (Событие клиента вызывающего абонента)</span><span class="sxs-lookup"><span data-stu-id="4dc28-108">Caller Client Event</span></span>

  - <span data-ttu-id="4dc28-109">Callee Client Event (Событие клиента вызываемого абонента)</span><span class="sxs-lookup"><span data-stu-id="4dc28-109">Callee Client Event</span></span>

  - <span data-ttu-id="4dc28-110">Audio Stream (Caller to Callee) (Аудиопоток (от вызывающего абонента к вызываемому))</span><span class="sxs-lookup"><span data-stu-id="4dc28-110">Audio Stream (Caller to Callee)</span></span>

  - <span data-ttu-id="4dc28-111">Video Stream (Caller to Callee) (Видеопоток (от вызывающего абонента к вызываемому))</span><span class="sxs-lookup"><span data-stu-id="4dc28-111">Video Stream (Caller to Callee)</span></span>

  - <span data-ttu-id="4dc28-112">Audio Stream (Callee to Caller) (Аудиопоток (от вызываемого абонента к вызывающему))</span><span class="sxs-lookup"><span data-stu-id="4dc28-112">Audio Stream (Callee to Caller)</span></span>

  - <span data-ttu-id="4dc28-113">Video Stream (Callee to Caller) (Видеопоток (от вызываемого абонента к вызывающему))</span><span class="sxs-lookup"><span data-stu-id="4dc28-113">Video Stream (Callee to Caller)</span></span>

<span data-ttu-id="4dc28-p101">Следует помнить, что категории и метрики, которые можно видеть в данном отчете, зависят от типа сеанса и типа конечных точек, используемых в сеансе. Например, отчет по аудиовызову не будет содержать метрики для видеопотоков, поскольку в этом вызове не было никаких видеопотоков. Аналогично, может быть отчет, в котором есть статистика вызывающего абонента, но отсутствует статистика вызываемого абонента, обычно в том случае, если вызываемый абонент использовал устройство, несовместимое с SIP. Конечные точки отвечают за статистику отчета в конце вызова; однако мобильный телефон (который ничего не знает о SIP и о статистике SIP) не в состоянии сообщить такого рода сведения. Если вызываемый абонент отвечает на вызов со своего мобильного телефона, то по завершении вызова вы не получите отчет от этого мобильного телефона.</span><span class="sxs-lookup"><span data-stu-id="4dc28-p101">Keep in mind that the categories and the metrics you see on a given report depend on two things: the type of session and the type of endpoints used in the session. For example, an audio-only call will not report metrics for video streams; that's because the call didn't have a video stream. Likewise, you might have a report that lists caller statistics but not callee statistics. That's typically because the callee was not using a SIP-compliant device. Endpoints are responsible for reporting statistics at the end of a call; however, a cell phone (which knows nothing about SIP or SIP statistics) is unable to report that kind of information. If you call someone and they answer you on their cell phone, you will not get a report from that cell phone when the call ends.</span></span>

<span data-ttu-id="4dc28-120">Подробный отчет по вызову особенно полезен в том случае, когда требуется точно определить, почему в конкретном вызове наблюдались проблемы с качеством мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="4dc28-120">The Call Detail Report is most useful when you are trying to determine exactly why a given call experienced media quality problems.</span></span>

<div>

## <a name="accessing-the-call-detail-report"></a><span data-ttu-id="4dc28-121">Доступ к подробному отчету по вызову</span><span class="sxs-lookup"><span data-stu-id="4dc28-121">Accessing the Call Detail Report</span></span>

<span data-ttu-id="4dc28-122">Доступ к подробному отчету по вызову можно получить из любого из следующих отчетов.</span><span class="sxs-lookup"><span data-stu-id="4dc28-122">The Call Detail Report can be accessed from any of the following reports:</span></span>

  - <span data-ttu-id="4dc28-123">[Отчет о местоположении в Lync Server 2013](lync-server-2013-location-report.md) (щелкните метрику громкости вызова или процента звонков низкого качества)</span><span class="sxs-lookup"><span data-stu-id="4dc28-123">The [Location Report in Lync Server 2013](lync-server-2013-location-report.md) (by clicking either the Call volume or the Poor call percentage metric)</span></span>

  - <span data-ttu-id="4dc28-124">[Сводный отчет по качеству мультимедиа в Lync Server 2013](lync-server-2013-media-quality-summary-report.md) (щелкните метрику громкости вызова или процента звонков низкого качества)</span><span class="sxs-lookup"><span data-stu-id="4dc28-124">The [Media Quality Summary Report in Lync Server 2013](lync-server-2013-media-quality-summary-report.md) (by clicking either the Call volume or Poor call percentage metric)</span></span>

  - <span data-ttu-id="4dc28-125">[Отчет по сравнению качества мультимедиа в Lync server 2013](lync-server-2013-media-quality-comparison-report.md) (щелкнув [отчет по списку обзвона в Lync Server 2013](lync-server-2013-call-list-report.md) , а затем щелкнув метрику Detail).</span><span class="sxs-lookup"><span data-stu-id="4dc28-125">The [Media Quality Comparison Report in Lync Server 2013](lync-server-2013-media-quality-comparison-report.md) (by clicking the [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) and then clicking the Detail metric).</span></span>

  - <span data-ttu-id="4dc28-126">[Отчет о производительности сервера в Lync server 2013](lync-server-2013-server-performance-report.md) (щелкните метрику громкости вызова или процента звонков низкого качества)</span><span class="sxs-lookup"><span data-stu-id="4dc28-126">The [Server Performance Report in Lync Server 2013](lync-server-2013-server-performance-report.md) (by clicking either the Call volume or Poor call percentage metric)</span></span>

  - <span data-ttu-id="4dc28-127">[Отчет по списку обзвона в Lync Server 2013](lync-server-2013-call-list-report.md) (щелкните метрику "подробные показатели")</span><span class="sxs-lookup"><span data-stu-id="4dc28-127">The [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) (by clicking the Detail metric)</span></span>

<span data-ttu-id="4dc28-128">В отчете о вызовах Вы можете получить доступ к [отчету по устройствам в Lync Server 2013](lync-server-2013-device-report.md) , щелкнув один из следующих показателей:</span><span class="sxs-lookup"><span data-stu-id="4dc28-128">From within the Call Detail Report you can access the [Device Report in Lync Server 2013](lync-server-2013-device-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="4dc28-129">Устройства захвата</span><span class="sxs-lookup"><span data-stu-id="4dc28-129">Capture device</span></span>

  - <span data-ttu-id="4dc28-130">Устройство обработки</span><span class="sxs-lookup"><span data-stu-id="4dc28-130">Render device</span></span>

<span data-ttu-id="4dc28-131">Можно также получить доступ к отчету по тенденциям качества мультимедиа на серверах, нажав метрику пограничного сервера аудио- и видеосвязи.</span><span class="sxs-lookup"><span data-stu-id="4dc28-131">You can also access the Server Media Quality Trend Report by clicking the A/V edge server metric.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-call-detail-report"></a><span data-ttu-id="4dc28-132">Эффективное использование подробного отчета по вызову</span><span class="sxs-lookup"><span data-stu-id="4dc28-132">Making the Best Use of the Call Detail Report</span></span>

<span data-ttu-id="4dc28-p102">Обычно в подробном отчете по вызову содержится более 250 разных метрик, включая такие, как уход отметки времени микрофона, низкое отношение "сигнал-шум", ближний конец ко времени эхо-задержки. Если вы не можете запомнить, что эти метрики измеряют в действительности, попробуйте задержать указатель мыши на метке метрики; часто при этом появляется всплывающая подсказка, которая описывает эту метрику.</span><span class="sxs-lookup"><span data-stu-id="4dc28-p102">The Call Detail Report typically includes over 250 different metrics, including such items as Microphone timestamp drift, Low SNR time, and Near end to echo time. If you can't remember what all of these metrics actually measure, try holding your mouse over the metric label; often-times, a tooltip will appear describing that metric.</span></span>

<span data-ttu-id="4dc28-p103">Если возникают проблемы с поиском нужной метрики, введите часть метки метрики в поле поиска и нажмите кнопку "Найти". Например, если не удается найти метрику низкого отношения "сигнал-шум" (Low SNR time), введите "SNR" в поле поиска и нажмите кнопку "Найти".</span><span class="sxs-lookup"><span data-stu-id="4dc28-p103">If you have problems locating a metric, type part of the metric label in the search box and then click Find. For example, if you can't find the Low SNR time metric, type SNR in the search box and then click Find.</span></span>

<span data-ttu-id="4dc28-137">Обратите внимание, что в отчете отслеживаются только сведения о вызове.</span><span class="sxs-lookup"><span data-stu-id="4dc28-137">Note that the report only tracks information about a call.</span></span> <span data-ttu-id="4dc28-138">Сам вызов не записывается.</span><span class="sxs-lookup"><span data-stu-id="4dc28-138">The call itself is not recorded.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="4dc28-139">Фильтры</span><span class="sxs-lookup"><span data-stu-id="4dc28-139">Filters</span></span>

<span data-ttu-id="4dc28-p105">Нет. Фильтрация подробного отчета по вызову невозможна.</span><span class="sxs-lookup"><span data-stu-id="4dc28-p105">None. You cannot filter the Call Detail Report.</span></span>

</div>

<div>

## <a name="metrics"></a><span data-ttu-id="4dc28-142">Метрик</span><span class="sxs-lookup"><span data-stu-id="4dc28-142">Metrics</span></span>

<span data-ttu-id="4dc28-143">В следующей таблице представлен список данных, которые предоставляются в подробном отчете по вызову для каждого вызова.</span><span class="sxs-lookup"><span data-stu-id="4dc28-143">The following table lists the information provided in the Call Detail Report for each call.</span></span>

### <a name="call-detail-report-metrics"></a><span data-ttu-id="4dc28-144">Метрики подробного отчета по вызову</span><span class="sxs-lookup"><span data-stu-id="4dc28-144">Call Detail Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4dc28-145">Имя</span><span class="sxs-lookup"><span data-stu-id="4dc28-145">Name</span></span></th>
<th><span data-ttu-id="4dc28-146">Возможность сортировки по этому показателю</span><span class="sxs-lookup"><span data-stu-id="4dc28-146">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="4dc28-147">Описание</span><span class="sxs-lookup"><span data-stu-id="4dc28-147">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4dc28-148"><strong>Caller PAI</strong> (PAI вызывающего абонента)</span><span class="sxs-lookup"><span data-stu-id="4dc28-148"><strong>Caller PAI</strong></span></span></p></td>
<td><p><span data-ttu-id="4dc28-149">Нет</span><span class="sxs-lookup"><span data-stu-id="4dc28-149">No</span></span></p></td>
<td><p><span data-ttu-id="4dc28-p106">Параметр P-Asserted-Identity пользователя, который инициировал вызов. Параметр P-Asserted-Identity используется для передачи подтвержденного удостоверения пользователя в рамках надежной сети.</span><span class="sxs-lookup"><span data-stu-id="4dc28-p106">P-Asserted-Identity of the user who initiated the call. The P-Asserted-Identity is used to convey the proven identity of a user within a trusted network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4dc28-152"><strong>Caller URI</strong> (URI вызывающего абонента)</span><span class="sxs-lookup"><span data-stu-id="4dc28-152"><strong>Caller URI</strong></span></span></p></td>
<td><p><span data-ttu-id="4dc28-153">Нет</span><span class="sxs-lookup"><span data-stu-id="4dc28-153">No</span></span></p></td>
<td><p><span data-ttu-id="4dc28-154">SIP-адрес пользователя, инициировавшего вызов.</span><span class="sxs-lookup"><span data-stu-id="4dc28-154">SIP address of the user who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4dc28-155"><strong>Caller endpoint</strong> (Конечная точка вызывающего абонента)</span><span class="sxs-lookup"><span data-stu-id="4dc28-155"><strong>Caller endpoint</strong></span></span></p></td>
<td><p><span data-ttu-id="4dc28-156">Нет</span><span class="sxs-lookup"><span data-stu-id="4dc28-156">No</span></span></p></td>
<td><p><span data-ttu-id="4dc28-157">Устройство, использовавшееся для выполнения вызова.</span><span class="sxs-lookup"><span data-stu-id="4dc28-157">Device used to make the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4dc28-158"><strong>Caller user agent</strong> (Агент вызывающего пользователя)</span><span class="sxs-lookup"><span data-stu-id="4dc28-158"><strong>Caller user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="4dc28-159">Нет</span><span class="sxs-lookup"><span data-stu-id="4dc28-159">No</span></span></p></td>
<td><p><span data-ttu-id="4dc28-160">Программное обеспечение, использовавшееся в устройстве, выполнившем вызов.</span><span class="sxs-lookup"><span data-stu-id="4dc28-160">Software used on the device that made the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4dc28-161"><strong>Call start</strong> (Начало вызова)</span><span class="sxs-lookup"><span data-stu-id="4dc28-161"><strong>Call start</strong></span></span></p></td>
<td><p><span data-ttu-id="4dc28-162">Нет</span><span class="sxs-lookup"><span data-stu-id="4dc28-162">No</span></span></p></td>
<td><p><span data-ttu-id="4dc28-163">Дата и время первоначального размещения вызова.</span><span class="sxs-lookup"><span data-stu-id="4dc28-163">Date and time that the call was initially placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4dc28-164"><strong>Mediation Server bypass call</strong> (Вызов с обходом сервера-посредника)</span><span class="sxs-lookup"><span data-stu-id="4dc28-164"><strong>Mediation Server bypass call</strong></span></span></p></td>
<td><p><span data-ttu-id="4dc28-165">Нет</span><span class="sxs-lookup"><span data-stu-id="4dc28-165">No</span></span></p></td>
<td><p><span data-ttu-id="4dc28-166">Указывает, подключался ли вызов к голосовому шлюзу ТСОП или к соответствующей IP-УАТС без прохода через сервер-посредник.</span><span class="sxs-lookup"><span data-stu-id="4dc28-166">Indicates whether the call connected to a PSTN voice gateway or qualified IP-PBX without passing through the Mediation Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4dc28-167"><strong>Caller OS</strong> (ОС вызывающего абонента)</span><span class="sxs-lookup"><span data-stu-id="4dc28-167"><strong>Caller OS</strong></span></span></p></td>
<td><p><span data-ttu-id="4dc28-168">Нет</span><span class="sxs-lookup"><span data-stu-id="4dc28-168">No</span></span></p></td>
<td><p><span data-ttu-id="4dc28-169">Операционная система компьютера вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="4dc28-169">Operating system of the caller's computer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4dc28-170"><strong>Caller CPU</strong> (ЦП вызывающего абонента)</span><span class="sxs-lookup"><span data-stu-id="4dc28-170"><strong>Caller CPU</strong></span></span></p></td>
<td><p><span data-ttu-id="4dc28-171">Нет</span><span class="sxs-lookup"><span data-stu-id="4dc28-171">No</span></span></p></td>
<td><p><span data-ttu-id="4dc28-172">Центральный процессор, установленный на компьютере пользователя, который инициировал вызов.</span><span class="sxs-lookup"><span data-stu-id="4dc28-172">CPU installed in the computer of the user who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4dc28-173"><strong>Caller CPU core number</strong> (Количество ядер ЦП вызывающего абонента)</span><span class="sxs-lookup"><span data-stu-id="4dc28-173"><strong>Caller CPU core number</strong></span></span></p></td>
<td><p><span data-ttu-id="4dc28-174">Нет</span><span class="sxs-lookup"><span data-stu-id="4dc28-174">No</span></span></p></td>
<td><p><span data-ttu-id="4dc28-175">Количество процессоров в компьютере пользователя, инициировавшего вызов.</span><span class="sxs-lookup"><span data-stu-id="4dc28-175">Processor number in the computer used by the person who initiated the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4dc28-176"><strong>Caller CPU speed</strong> (Частота ЦП вызывающего абонента)</span><span class="sxs-lookup"><span data-stu-id="4dc28-176"><strong>Caller CPU speed</strong></span></span></p></td>
<td><p><span data-ttu-id="4dc28-177">Нет</span><span class="sxs-lookup"><span data-stu-id="4dc28-177">No</span></span></p></td>
<td><p><span data-ttu-id="4dc28-178">Тактовая частота центрального процессора компьютера пользователя, инициировавшего вызов.</span><span class="sxs-lookup"><span data-stu-id="4dc28-178">Clock speed of the CPU of the computer used by the person who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4dc28-179"><strong>Caller CPU virtualization</strong> (Виртуализация ЦП вызывающего абонента)</span><span class="sxs-lookup"><span data-stu-id="4dc28-179"><strong>Caller CPU virtualization</strong></span></span></p></td>
<td><p><span data-ttu-id="4dc28-180">Нет</span><span class="sxs-lookup"><span data-stu-id="4dc28-180">No</span></span></p></td>
<td><p><span data-ttu-id="4dc28-181">Виртуализация, использовавшаяся на компьютере пользователя, инициировавшего вызов (если виртуализация использовалась).</span><span class="sxs-lookup"><span data-stu-id="4dc28-181">Virtualization (if any) used on the computer used by the person who initiated the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4dc28-182"><strong>Callee PAI</strong> (PAI вызываемого абонента)</span><span class="sxs-lookup"><span data-stu-id="4dc28-182"><strong>Callee PAI</strong></span></span></p></td>
<td><p><span data-ttu-id="4dc28-183">Нет</span><span class="sxs-lookup"><span data-stu-id="4dc28-183">No</span></span></p></td>
<td><p><span data-ttu-id="4dc28-p107">Параметр P-Asserted-Identity пользователя, который получил вызов. Параметр P-Asserted-Identity используется для передачи подтвержденного удостоверения пользователя в рамках надежной сети.</span><span class="sxs-lookup"><span data-stu-id="4dc28-p107">P-Asserted-Identity of the user who was invited to join the call. The P-Asserted-Identity is used to convey the proven identity of a user within a trusted network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4dc28-186"><strong>Callee URI</strong> (URI вызываемого абонента)</span><span class="sxs-lookup"><span data-stu-id="4dc28-186"><strong>Callee URI</strong></span></span></p></td>
<td><p><span data-ttu-id="4dc28-187">Нет</span><span class="sxs-lookup"><span data-stu-id="4dc28-187">No</span></span></p></td>
<td><p><span data-ttu-id="4dc28-188">SIP-адрес пользователя, который принял вызов.</span><span class="sxs-lookup"><span data-stu-id="4dc28-188">SIP address of the user who was called.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4dc28-189"><strong>Callee endpoint</strong> (Конечная точка вызываемого абонента)</span><span class="sxs-lookup"><span data-stu-id="4dc28-189"><strong>Callee endpoint</strong></span></span></p></td>
<td><p><span data-ttu-id="4dc28-190">Нет</span><span class="sxs-lookup"><span data-stu-id="4dc28-190">No</span></span></p></td>
<td><p><span data-ttu-id="4dc28-191">Устройство, использовавшееся для принятия вызова.</span><span class="sxs-lookup"><span data-stu-id="4dc28-191">Device used to receive the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4dc28-192"><strong>Callee user agent</strong> (Агент вызываемого пользователя)</span><span class="sxs-lookup"><span data-stu-id="4dc28-192"><strong>Callee user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="4dc28-193">Нет</span><span class="sxs-lookup"><span data-stu-id="4dc28-193">No</span></span></p></td>
<td><p><span data-ttu-id="4dc28-194">Программное обеспечение, использовавшееся в устройстве, принявшем вызов.</span><span class="sxs-lookup"><span data-stu-id="4dc28-194">Software used on the device that received the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4dc28-195"><strong>Duration</strong></span><span class="sxs-lookup"><span data-stu-id="4dc28-195"><strong>Duration</strong></span></span></p></td>
<td><p><span data-ttu-id="4dc28-196">Нет</span><span class="sxs-lookup"><span data-stu-id="4dc28-196">No</span></span></p></td>
<td><p><span data-ttu-id="4dc28-197">Продолжительность (время) вызова.</span><span class="sxs-lookup"><span data-stu-id="4dc28-197">Length of time for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4dc28-198"><strong>Media bypass warning flag</strong> (Флаг предупреждения об обходе сервера-посредника)</span><span class="sxs-lookup"><span data-stu-id="4dc28-198"><strong>Media bypass warning flag</strong></span></span></p></td>
<td><p><span data-ttu-id="4dc28-199">Нет</span><span class="sxs-lookup"><span data-stu-id="4dc28-199">No</span></span></p></td>
<td><p><span data-ttu-id="4dc28-200">Предупреждение, которое выдается при обходе сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="4dc28-200">Warning issued when the Mediation Server was bypassed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4dc28-201"><strong>Callee OS</strong> (ОС вызываемого абонента)</span><span class="sxs-lookup"><span data-stu-id="4dc28-201"><strong>Callee OS</strong></span></span></p></td>
<td><p><span data-ttu-id="4dc28-202">Нет</span><span class="sxs-lookup"><span data-stu-id="4dc28-202">No</span></span></p></td>
<td><p><span data-ttu-id="4dc28-203">Операционная система компьютера вызванного пользователя.</span><span class="sxs-lookup"><span data-stu-id="4dc28-203">Operating system of the computer for the user who was called.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4dc28-204"><strong>Callee CPU</strong> (ЦП вызываемого абонента)</span><span class="sxs-lookup"><span data-stu-id="4dc28-204"><strong>Callee CPU</strong></span></span></p></td>
<td><p><span data-ttu-id="4dc28-205">Нет</span><span class="sxs-lookup"><span data-stu-id="4dc28-205">No</span></span></p></td>
<td><p><span data-ttu-id="4dc28-206">Центральный процессор, установленный на компьютере вызванного пользователя.</span><span class="sxs-lookup"><span data-stu-id="4dc28-206">CPU installed in the computer of the user who was called.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4dc28-207"><strong>Callee core number</strong> (Количество ядер ЦП вызываемого абонента)</span><span class="sxs-lookup"><span data-stu-id="4dc28-207"><strong>Callee core number</strong></span></span></p></td>
<td><p><span data-ttu-id="4dc28-208">Нет</span><span class="sxs-lookup"><span data-stu-id="4dc28-208">No</span></span></p></td>
<td><p><span data-ttu-id="4dc28-209">Количество процессоров в компьютере вызванного пользователя.</span><span class="sxs-lookup"><span data-stu-id="4dc28-209">Processor number in the computer used by the person who was called.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4dc28-210"><strong>Callee CPU speed</strong> (Частота ЦП вызываемого абонента)</span><span class="sxs-lookup"><span data-stu-id="4dc28-210"><strong>Callee CPU speed</strong></span></span></p></td>
<td><p><span data-ttu-id="4dc28-211">Нет</span><span class="sxs-lookup"><span data-stu-id="4dc28-211">No</span></span></p></td>
<td><p><span data-ttu-id="4dc28-212">Тактовая частота центрального процессора компьютера вызванного пользователя.</span><span class="sxs-lookup"><span data-stu-id="4dc28-212">Clock speed of the CPU of the computer used by the person who was called.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4dc28-213"><strong>Callee CPU virtualization</strong> (Виртуализация ЦП вызываемого абонента)</span><span class="sxs-lookup"><span data-stu-id="4dc28-213"><strong>Callee CPU virtualization</strong></span></span></p></td>
<td><p><span data-ttu-id="4dc28-214">Нет</span><span class="sxs-lookup"><span data-stu-id="4dc28-214">No</span></span></p></td>
<td><p><span data-ttu-id="4dc28-215">Виртуализация, использовавшаяся на компьютере вызванного пользователя (если виртуализация использовалась).</span><span class="sxs-lookup"><span data-stu-id="4dc28-215">Virtualization (if any) used on the computer used by the person who was called.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

