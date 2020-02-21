---
title: 'Lync Server 2013: диагностический отчет по конференциям'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conference Diagnostic Report
ms:assetid: e9edc23c-8ce8-4ab8-8786-9d22e1e51e14
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615042(v=OCS.15)
ms:contentKeyID: 48185901
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eb475db2d1a12dcfc2b95dbf4711191767b18236
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191972"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conference-diagnostic-report-in-lync-server-2013"></a><span data-ttu-id="d5759-102">Диагностический отчет по конференциям в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d5759-102">Conference Diagnostic Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d5759-103">_**Последнее изменение темы:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="d5759-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="d5759-p101">Диагностический отчет по конференциям содержит сведения об успешности или сбое всех сеансов конференц-связи. Обратите внимание на то, что Microsoft Lync Server различает несколько видов сбоев:</span><span class="sxs-lookup"><span data-stu-id="d5759-p101">The Conference Diagnostic Report provides information about the success and failure of all conferencing sessions. Note that Microsoft Lync Server distinguishes between different kinds of failure:</span></span>

  - <span data-ttu-id="d5759-p102">**Ожидаемый сбой**. Ожидаемый сбой можно назвать сбоем исключительно с технической точки зрения. Например, предположим, что кто-то запускает конференцию, но вешает трубку прежде, чем другие пользователи могут присоединиться к этой конференции. С технической точки зрения это сбой ? конференция была инициализирована, но не завершена. Однако это сбой, которого можно было ожидать: если организатор отменяет конференцию до присоединения других пользователей, ожидать завершения конференции нельзя.</span><span class="sxs-lookup"><span data-stu-id="d5759-p102">**Expected failure**. An expected failure is typically a failure only in the most technical sense. For example, suppose someone starts a conference but hangs up before anyone can join. Technically that's a failure: the conference was initiated, but not completed. However, that's a failure that you would expect to happen: if the organizer cancels the conference before anyone can join then you would not expect that conference to be completed.</span></span>

  - <span data-ttu-id="d5759-p103">**Неожиданный сбой**. Неожиданный сбой полностью соответствует своему названию ? это ошибка, возникновение которой вы в данных обстоятельствах не ожидали. Например, предположим, что конференцию нельзя провести, так как не удается получить политику собраний организатора. Это неожиданная ошибка: возможность получения политики собраний организатора должна быть доступна всегда.</span><span class="sxs-lookup"><span data-stu-id="d5759-p103">**Unexpected failure**. An unexpected error is exactly what the name implies: an error that, based on the circumstances, you would not expect to occur. For example, suppose a conference could not be held because the organizer's meeting policy could not be retrieved. That's an unexpected error: after all, you should always be able to retrieve a user's meeting policy.</span></span>

<span data-ttu-id="d5759-p104">Обратите внимание на то, что метрики успешного выполнения, ожидаемого сбоя и неожиданного сбоя могут не учитываться в метрике итогового числа сеансов. Например, вы можете увидеть в отчете следующие значения:</span><span class="sxs-lookup"><span data-stu-id="d5759-p104">Note that the Success, Expected failure, and Unexpected failure metrics might not add up to the Total sessions metric. For example, you might see the following values in the Report:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d5759-117">Успешные операции</span><span class="sxs-lookup"><span data-stu-id="d5759-117">Successes</span></span></th>
<th><span data-ttu-id="d5759-118">Число ожидаемых сбоев</span><span class="sxs-lookup"><span data-stu-id="d5759-118">Expected failures</span></span></th>
<th><span data-ttu-id="d5759-119">Число неожиданных сбоев</span><span class="sxs-lookup"><span data-stu-id="d5759-119">Unexpected failures</span></span></th>
<th><span data-ttu-id="d5759-120">Всего сеансов</span><span class="sxs-lookup"><span data-stu-id="d5759-120">Total sessions</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d5759-121">2024</span><span class="sxs-lookup"><span data-stu-id="d5759-121">2024</span></span></p></td>
<td><p><span data-ttu-id="d5759-122">469</span><span class="sxs-lookup"><span data-stu-id="d5759-122">469</span></span></p></td>
<td><p><span data-ttu-id="d5759-123">16 </span><span class="sxs-lookup"><span data-stu-id="d5759-123">16</span></span></p></td>
<td><p><span data-ttu-id="d5759-124">2521</span><span class="sxs-lookup"><span data-stu-id="d5759-124">2521</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="d5759-125">Если сложить 2024 + 469 + 16 получается 2509 сеансов, однако в столбце итогового числа сеансов стоит значение 2521.</span><span class="sxs-lookup"><span data-stu-id="d5759-125">If you add 2024 + 469 + 16 you get a total of 2,509 sessions and yet, the Total sessions column shows a total of 2,521 sessions.</span></span> <span data-ttu-id="d5759-126">Для 12 «отсутствующих» сеансов системе не удалось отнести сеанс к категории успешных или неуспешных.</span><span class="sxs-lookup"><span data-stu-id="d5759-126">The "missing" 12 sessions for are sessions that the system was unable to categorize as successful or unsuccessful.</span></span> <span data-ttu-id="d5759-127">Это иногда происходит, когда сторонний продукт представляет новый диагностический код, незнакомый с сервером мониторинга.</span><span class="sxs-lookup"><span data-stu-id="d5759-127">That will sometimes be the case when a third-party product introduces a new diagnostic code that is unfamiliar to Monitoring Server.</span></span> <span data-ttu-id="d5759-128">В этом случае звонки, выполненные с использованием этого продукта и отчетность по этому диагностическому коду не всегда можно отнести к категории успешного выполнения, ожидаемого сбоя или неожиданного сбоя.</span><span class="sxs-lookup"><span data-stu-id="d5759-128">When that happens, calls made using that product, and reporting that diagnostic code, cannot always be categorized as being a Success, an Expected failure, or an Unexpected failure.</span></span>

<div>

## <a name="accessing-the-conference-diagnostic-report"></a><span data-ttu-id="d5759-129">Доступ к диагностическому отчету по конференциям</span><span class="sxs-lookup"><span data-stu-id="d5759-129">Accessing the Conference Diagnostic Report</span></span>

<span data-ttu-id="d5759-130">Доступ к  диагностическому отчету по конференциям осуществляется с домашней страницы отчетов мониторинга.</span><span class="sxs-lookup"><span data-stu-id="d5759-130">The Conference Diagnostic Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="d5759-131">Вы можете получить доступ к [отчету распределения сбоев в Lync Server 2013](lync-server-2013-failure-distribution-report.md) , щелкнув один из следующих показателей:</span><span class="sxs-lookup"><span data-stu-id="d5759-131">You can access the [Failure Distribution Report in Lync Server 2013](lync-server-2013-failure-distribution-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="d5759-132">Unexpected failure volume (Неожиданный сбой, объем)</span><span class="sxs-lookup"><span data-stu-id="d5759-132">Unexpected failure volume</span></span>

  - <span data-ttu-id="d5759-133">Expected failure volume (Ожидаемый сбой, объем)</span><span class="sxs-lookup"><span data-stu-id="d5759-133">Expected failure volume</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-conference-diagnostic-report"></a><span data-ttu-id="d5759-134">Эффективное использование диагностического отчета по конференциям</span><span class="sxs-lookup"><span data-stu-id="d5759-134">Making the Best Use of the Conference Diagnostic Report</span></span>

<span data-ttu-id="d5759-135">Диагностический отчет по Конференции содержит ряд графиков.</span><span class="sxs-lookup"><span data-stu-id="d5759-135">The Conference Diagnostic Report includes a series of graphs.</span></span> <span data-ttu-id="d5759-136">Все столбцы, показанные на графике, фактически являются гиперссылкой.</span><span class="sxs-lookup"><span data-stu-id="d5759-136">Each of the columns shown in the graph is actually a hyperlink.</span></span> <span data-ttu-id="d5759-137">Если щелкнуть столбец, вы получите подробные сведения [об отчете о распределении сбоев в Lync Server 2013](lync-server-2013-failure-distribution-report.md) для этого периода времени и типа конференции.</span><span class="sxs-lookup"><span data-stu-id="d5759-137">If you click a column, you'll drill down to the [Failure Distribution Report in Lync Server 2013](lync-server-2013-failure-distribution-report.md) for that time period and that conference type.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="d5759-138">Фильтры</span><span class="sxs-lookup"><span data-stu-id="d5759-138">Filters</span></span>

<span data-ttu-id="d5759-p108">Фильтры позволяют вам возвратить уточненный набор данных или просматривать возвращенные данные различными способами. Например, диагностический отчет по конференциям позволяет вам выполнять фильтрацию по таким условиям, как тип проводимой конференции (например, конференция Focus) или используемый для конференции пограничный сервер. Вы также можете определить группировку данных. В данном случае конференции группируются по часу, дню, неделе или месяцу.</span><span class="sxs-lookup"><span data-stu-id="d5759-p108">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Conference Diagnostic Report enables you to filter on such things as the type of conference being conducted (for example, a Focus-based conference) or by the Edge Server used in the conference. You can also choose how data should be grouped. In this case, conferences are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="d5759-143">В следующей таблице перечислены фильтры, которые вы можете использовать в диагностическом отчете по конференциям.</span><span class="sxs-lookup"><span data-stu-id="d5759-143">The following table lists the filters that you can use with the Conference Diagnostic Report.</span></span>

### <a name="conference-diagnostic-report-filters"></a><span data-ttu-id="d5759-144">Фильтры диагностического отчета по конференциям</span><span class="sxs-lookup"><span data-stu-id="d5759-144">Conference Diagnostic Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d5759-145">Имя</span><span class="sxs-lookup"><span data-stu-id="d5759-145">Name</span></span></th>
<th><span data-ttu-id="d5759-146">Описание</span><span class="sxs-lookup"><span data-stu-id="d5759-146">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d5759-147"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="d5759-147"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="d5759-p109">Дата и время начала диапазона. Чтобы просмотреть данные по часам, введите дату и время начала в следующем формате:</span><span class="sxs-lookup"><span data-stu-id="d5759-p109">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="d5759-150">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="d5759-150">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="d5759-p110">Если не указать время начала, автоматически будет выбрано время 00:00 указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</span><span class="sxs-lookup"><span data-stu-id="d5759-p110">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="d5759-153">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="d5759-153">7/7/2012</span></span></p>
<p><span data-ttu-id="d5759-154">Для просмотра по неделям или по месяцам введите дату, выпадающую на любой день недели или месяца, который вы хотите просмотреть (это необязательно должен быть первый день недели или месяца):</span><span class="sxs-lookup"><span data-stu-id="d5759-154">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="d5759-155">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="d5759-155">7/3/2012</span></span></p>
<p><span data-ttu-id="d5759-156">Недели всегда начинаются с Воскресенья и заканчиваются в Субботу.</span><span class="sxs-lookup"><span data-stu-id="d5759-156">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d5759-157"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="d5759-157"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="d5759-p111">Дата и время окончания диапазона. Чтобы просмотреть данные по часам, введите дату и время окончания в следующем формате:</span><span class="sxs-lookup"><span data-stu-id="d5759-p111">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="d5759-160">7/7/2012 13:00.</span><span class="sxs-lookup"><span data-stu-id="d5759-160">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="d5759-p112">Если не указать время окончания, автоматически будет выбрано время 00:00 указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</span><span class="sxs-lookup"><span data-stu-id="d5759-p112">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="d5759-163">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="d5759-163">7/7/2012</span></span></p>
<p><span data-ttu-id="d5759-164">Для просмотра по неделям или по месяцам введите дату, выпадающую на любой день недели или месяца, который вы хотите просмотреть (это необязательно должен быть первый день недели или месяца):</span><span class="sxs-lookup"><span data-stu-id="d5759-164">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="d5759-165">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="d5759-165">7/3/2012</span></span></p>
<p><span data-ttu-id="d5759-166">Неделя всегда начинается с воскресения и заканчивается субботой.</span><span class="sxs-lookup"><span data-stu-id="d5759-166">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d5759-167"><strong>Interval</strong></span><span class="sxs-lookup"><span data-stu-id="d5759-167"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="d5759-p113">Временной интервал. Выберите один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="d5759-p113">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="d5759-170">Ежечасно (может отображаться до 25 часов)</span><span class="sxs-lookup"><span data-stu-id="d5759-170">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="d5759-171">Ежедневно (может отображаться до 31 дня)</span><span class="sxs-lookup"><span data-stu-id="d5759-171">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="d5759-172">Еженедельно (может отображаться до 12 недель)</span><span class="sxs-lookup"><span data-stu-id="d5759-172">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="d5759-173">Ежемесячно (может отображаться до 12 месяцев)</span><span class="sxs-lookup"><span data-stu-id="d5759-173">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="d5759-p114">Если начальная и конечная даты превышают максимально допустимое количество значений для выбранного интервала, отображается только максимальное число значений (с отсчетом от начальной даты). Например, если вы выбрали интервал «Daily» с начальной датой 7/7/2012 и конечной датой 2/28/2012, отображаются данные по дням с 00:00 часов 8/7/2012  по 00:00 часов 9/7/2012 (то есть всего за 31 день).</span><span class="sxs-lookup"><span data-stu-id="d5759-p114">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d5759-176"><strong>Ресурсов</strong></span><span class="sxs-lookup"><span data-stu-id="d5759-176"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="d5759-p115">Полное доменное имя пула регистратора или пограничного сервера. Можно выбрать отдельный пул или щелкнуть <strong>[Все]</strong>, чтобы просмотреть данные для всех пулов. Этот раскрывающийся список заполняется автоматически на основе записей в базе данных.</span><span class="sxs-lookup"><span data-stu-id="d5759-p115">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d5759-180"><strong>Conference sessions</strong> (Сеансы конференций)</span><span class="sxs-lookup"><span data-stu-id="d5759-180"><strong>Conference sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="d5759-p116">Указывает тип сеанса конференц-связи. Выберите одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="d5759-p116">Indicates the type of conferencing session. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="d5759-183">Ко</span><span class="sxs-lookup"><span data-stu-id="d5759-183">[All]</span></span></p></li>
<li><p><span data-ttu-id="d5759-184">Focus sessions (Сеансы Focus)</span><span class="sxs-lookup"><span data-stu-id="d5759-184">Focus sessions</span></span></p></li>
<li><p><span data-ttu-id="d5759-185">All MCU sessions (Все сеансы MCU)</span><span class="sxs-lookup"><span data-stu-id="d5759-185">All MCU sessions</span></span></p></li>
<li><p><span data-ttu-id="d5759-186">IM conferencing (Конференции с обменом мгновенными сообщениями)</span><span class="sxs-lookup"><span data-stu-id="d5759-186">IM conferencing</span></span></p></li>
<li><p><span data-ttu-id="d5759-187">Application sharing (Общий доступ к приложениям)</span><span class="sxs-lookup"><span data-stu-id="d5759-187">Application sharing</span></span></p></li>
<li><p><span data-ttu-id="d5759-188">A/V conferencing (Аудио- и видеоконференции)</span><span class="sxs-lookup"><span data-stu-id="d5759-188">A/V conferencing</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="d5759-189">Метрик</span><span class="sxs-lookup"><span data-stu-id="d5759-189">Metrics</span></span>

<span data-ttu-id="d5759-190">В следующей таблице перечислены сведения, представленные в диагностическом отчете по конференциям.</span><span class="sxs-lookup"><span data-stu-id="d5759-190">The following table lists the information provided in the Conference Diagnostic Report for each type of conferencing session.</span></span>

### <a name="conference-diagnostic-report-metrics"></a><span data-ttu-id="d5759-191">Метрики диагностического отчета по конференциям</span><span class="sxs-lookup"><span data-stu-id="d5759-191">Conference Diagnostic Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d5759-192">Имя</span><span class="sxs-lookup"><span data-stu-id="d5759-192">Name</span></span></th>
<th><span data-ttu-id="d5759-193">Возможность сортировки по этому показателю</span><span class="sxs-lookup"><span data-stu-id="d5759-193">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="d5759-194">Описание</span><span class="sxs-lookup"><span data-stu-id="d5759-194">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d5759-195"><strong>Success volume</strong> (Успех, объем)</span><span class="sxs-lookup"><span data-stu-id="d5759-195"><strong>Success volume</strong></span></span></p></td>
<td><p><span data-ttu-id="d5759-196">Нет</span><span class="sxs-lookup"><span data-stu-id="d5759-196">No</span></span></p></td>
<td><p><span data-ttu-id="d5759-197">Общее число успешных конференций.</span><span class="sxs-lookup"><span data-stu-id="d5759-197">Total number of successful conferences.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d5759-198"><strong>Success percentage</strong> (Успех, процент)</span><span class="sxs-lookup"><span data-stu-id="d5759-198"><strong>Success percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="d5759-199">Нет</span><span class="sxs-lookup"><span data-stu-id="d5759-199">No</span></span></p></td>
<td><p><span data-ttu-id="d5759-p117">Процентное отношение конференций, которые были завершены со значительными проблемами. Значение вычисляется путем деления значения «Success volume» (Успех, процент) на значение «Total sessions» (Всего сеансов).</span><span class="sxs-lookup"><span data-stu-id="d5759-p117">Percentage of conferences that completed with significant problems. Calculated by dividing the Success volume by the Total sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d5759-202"><strong>Expected failure volume</strong> (Ожидаемый сбой, объем)</span><span class="sxs-lookup"><span data-stu-id="d5759-202"><strong>Expected failure volume</strong></span></span></p></td>
<td><p><span data-ttu-id="d5759-203">Нет</span><span class="sxs-lookup"><span data-stu-id="d5759-203">No</span></span></p></td>
<td><p><span data-ttu-id="d5759-204">Общее количество конференций, в &quot;которых возник ожидаемый сбой.&quot;</span><span class="sxs-lookup"><span data-stu-id="d5759-204">Total number of conferences where an &quot;expected failure&quot; occurred.</span></span></p>
<p><span data-ttu-id="d5759-p118">Ожидаемый сбой ? это сбой, возникновение которого ожидаемо. Например, если пользователь задал для себя состояние «Не беспокоить», можно ожидать, что любой звонок этому пользователю будет неудачным.</span><span class="sxs-lookup"><span data-stu-id="d5759-p118">An expected failure is a failure that is expected to happen. For example, if a user has set his or her status to Do Not Disturb you would expect any call to that user to fail.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d5759-207"><strong>Expected failure percentage</strong> (Ожидаемый сбой, процент)</span><span class="sxs-lookup"><span data-stu-id="d5759-207"><strong>Expected failure percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="d5759-208">Нет</span><span class="sxs-lookup"><span data-stu-id="d5759-208">No</span></span></p></td>
<td><p><span data-ttu-id="d5759-p119">Процентное отношение конференций, для которых возник ожидаемый сбой. Значение вычисляется путем деления значения «Expected failure volume» (Ожидаемый сбой, объем) на значение «Total sessions» (Всего сеансов).</span><span class="sxs-lookup"><span data-stu-id="d5759-p119">Percentage of conferences that experienced an expected error. Calculated by dividing the Expected failure volume by the Total sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d5759-211"><strong>Unexpected failure volume</strong> (Неожиданный сбой, объем)</span><span class="sxs-lookup"><span data-stu-id="d5759-211"><strong>Unexpected failure volume</strong></span></span></p></td>
<td><p><span data-ttu-id="d5759-212">Нет</span><span class="sxs-lookup"><span data-stu-id="d5759-212">No</span></span></p></td>
<td><p><span data-ttu-id="d5759-213">Общее количество конференций, в &quot;которых произошла&quot; непредвиденная ошибка.</span><span class="sxs-lookup"><span data-stu-id="d5759-213">Total number of conferences where an &quot;unexpected failure&quot; occurred.</span></span></p>
<p><span data-ttu-id="d5759-p120">Неожиданный сбой ? это событие, которое в других условиях считалось бы нормальной работой системы. Например, звонок не следует завершать, если звонящий переведен в режим удержания. Если такое произошло, данное событие будет обозначено как неожиданный сбой.</span><span class="sxs-lookup"><span data-stu-id="d5759-p120">An unexpected failure is a failure that occurs in what would appear to be an otherwise healthy system. For example, a call should not be terminated if the caller is placed on hold. If that occurs, that would be flagged as an unexpected failure.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d5759-217"><strong>Unexpected failure percentage</strong> (Неожиданный сбой, процент)</span><span class="sxs-lookup"><span data-stu-id="d5759-217"><strong>Unexpected failure percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="d5759-218">Нет</span><span class="sxs-lookup"><span data-stu-id="d5759-218">No</span></span></p></td>
<td><p><span data-ttu-id="d5759-p121">Процентное отношение конференций, для которых возник неожиданный сбой. Значение вычисляется путем деления значения «Unexpected failure volume» (Неожиданный сбой, объем) на значение «Total sessions» (Всего сеансов).</span><span class="sxs-lookup"><span data-stu-id="d5759-p121">Percentage of conferences that experienced an unexpected error. Calculated by dividing the Unexpected failure volume by the Total sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d5759-221"><strong> Всего сеансов </strong></span><span class="sxs-lookup"><span data-stu-id="d5759-221"><strong>Total sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="d5759-222">Нет</span><span class="sxs-lookup"><span data-stu-id="d5759-222">No</span></span></p></td>
<td><p><span data-ttu-id="d5759-223">Общее число конференций, включая успешные конференции, неуспешные (как с ожидаемыми, так и с неожиданными сбоями) конференции и конференции, не отнесенные ни к одной из категорий.</span><span class="sxs-lookup"><span data-stu-id="d5759-223">Total number of conferences, including successful conferences, failed conferences (both expected failures and unexpected failures), and uncategorized conferences.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

