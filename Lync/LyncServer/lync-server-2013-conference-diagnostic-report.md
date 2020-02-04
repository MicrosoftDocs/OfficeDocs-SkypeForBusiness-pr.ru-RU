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
ms.openlocfilehash: 69c63e710463a37eecbb7d20edbe5999d0fbb55f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757023"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conference-diagnostic-report-in-lync-server-2013"></a><span data-ttu-id="f9905-102">Диагностический отчет на Конференции в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f9905-102">Conference Diagnostic Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f9905-103">_**Тема последнего изменения:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="f9905-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="f9905-104">Диагностический отчет о конференц-связи содержит сведения об успешности или сбое всех сеансов конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="f9905-104">The Conference Diagnostic Report provides information about the success and failure of all conferencing sessions.</span></span> <span data-ttu-id="f9905-105">Обратите внимание, что в Microsoft Lync Server различаются различные типы сбоев.</span><span class="sxs-lookup"><span data-stu-id="f9905-105">Note that Microsoft Lync Server distinguishes between different kinds of failure:</span></span>

  - <span data-ttu-id="f9905-p102">**Ожидаемый сбой**. Ожидаемый сбой можно назвать сбоем исключительно с технической точки зрения. Например, предположим, что кто-то запускает конференцию, но вешает трубку прежде, чем другие пользователи могут присоединиться к этой конференции. С технической точки зрения это сбой ? конференция была инициализирована, но не завершена. Однако это сбой, которого можно было ожидать: если организатор отменяет конференцию до присоединения других пользователей, ожидать завершения конференции нельзя.</span><span class="sxs-lookup"><span data-stu-id="f9905-p102">**Expected failure**. An expected failure is typically a failure only in the most technical sense. For example, suppose someone starts a conference but hangs up before anyone can join. Technically that's a failure: the conference was initiated, but not completed. However, that's a failure that you would expect to happen: if the organizer cancels the conference before anyone can join then you would not expect that conference to be completed.</span></span>

  - <span data-ttu-id="f9905-p103">**Неожиданный сбой**. Неожиданный сбой полностью соответствует своему названию ? это ошибка, возникновение которой вы в данных обстоятельствах не ожидали. Например, предположим, что конференцию нельзя провести, так как не удается получить политику собраний организатора. Это неожиданная ошибка: возможность получения политики собраний организатора должна быть доступна всегда.</span><span class="sxs-lookup"><span data-stu-id="f9905-p103">**Unexpected failure**. An unexpected error is exactly what the name implies: an error that, based on the circumstances, you would not expect to occur. For example, suppose a conference could not be held because the organizer's meeting policy could not be retrieved. That's an unexpected error: after all, you should always be able to retrieve a user's meeting policy.</span></span>

<span data-ttu-id="f9905-p104">Обратите внимание на то, что метрики успешного выполнения, ожидаемого сбоя и неожиданного сбоя могут не учитываться в метрике итогового числа сеансов. Например, вы можете увидеть в отчете следующие значения:</span><span class="sxs-lookup"><span data-stu-id="f9905-p104">Note that the Success, Expected failure, and Unexpected failure metrics might not add up to the Total sessions metric. For example, you might see the following values in the Report:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f9905-117">Число успешных выполнений</span><span class="sxs-lookup"><span data-stu-id="f9905-117">Successes</span></span></th>
<th><span data-ttu-id="f9905-118">Число ожидаемых сбоев</span><span class="sxs-lookup"><span data-stu-id="f9905-118">Expected failures</span></span></th>
<th><span data-ttu-id="f9905-119">Число неожиданных сбоев</span><span class="sxs-lookup"><span data-stu-id="f9905-119">Unexpected failures</span></span></th>
<th><span data-ttu-id="f9905-120">Всего сеансов</span><span class="sxs-lookup"><span data-stu-id="f9905-120">Total sessions</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f9905-121">2024</span><span class="sxs-lookup"><span data-stu-id="f9905-121">2024</span></span></p></td>
<td><p><span data-ttu-id="f9905-122">469</span><span class="sxs-lookup"><span data-stu-id="f9905-122">469</span></span></p></td>
<td><p><span data-ttu-id="f9905-123">шестнадцат</span><span class="sxs-lookup"><span data-stu-id="f9905-123">16</span></span></p></td>
<td><p><span data-ttu-id="f9905-124">2521</span><span class="sxs-lookup"><span data-stu-id="f9905-124">2521</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="f9905-125">Если сложить 2024 + 469 + 16 получается 2509 сеансов, однако в столбце итогового числа сеансов стоит значение 2521.</span><span class="sxs-lookup"><span data-stu-id="f9905-125">If you add 2024 + 469 + 16 you get a total of 2,509 sessions and yet, the Total sessions column shows a total of 2,521 sessions.</span></span> <span data-ttu-id="f9905-126">Для 12 «отсутствующих» сеансов системе не удалось отнести сеанс к категории успешных или неуспешных.</span><span class="sxs-lookup"><span data-stu-id="f9905-126">The "missing" 12 sessions for are sessions that the system was unable to categorize as successful or unsuccessful.</span></span> <span data-ttu-id="f9905-127">Это иногда является случайом, когда сторонний продукт представляет новый диагностический код, незнакомый с сервером мониторинга.</span><span class="sxs-lookup"><span data-stu-id="f9905-127">That will sometimes be the case when a third-party product introduces a new diagnostic code that is unfamiliar to Monitoring Server.</span></span> <span data-ttu-id="f9905-128">В этом случае звонки, выполненные с использованием этого продукта и отчетность по этому диагностическому коду не всегда можно отнести к категории успешного выполнения, ожидаемого сбоя или неожиданного сбоя.</span><span class="sxs-lookup"><span data-stu-id="f9905-128">When that happens, calls made using that product, and reporting that diagnostic code, cannot always be categorized as being a Success, an Expected failure, or an Unexpected failure.</span></span>

<div>

## <a name="accessing-the-conference-diagnostic-report"></a><span data-ttu-id="f9905-129">Доступ к диагностическому отчету по конференциям</span><span class="sxs-lookup"><span data-stu-id="f9905-129">Accessing the Conference Diagnostic Report</span></span>

<span data-ttu-id="f9905-130">Доступ к диагностическому отчету по конференциям осуществляется с домашней страницы отчетов мониторинга.</span><span class="sxs-lookup"><span data-stu-id="f9905-130">The Conference Diagnostic Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="f9905-131">Вы можете получить доступ к [отчету о распределении отказов в Lync Server 2013](lync-server-2013-failure-distribution-report.md) , выбрав один из указанных ниже метрик.</span><span class="sxs-lookup"><span data-stu-id="f9905-131">You can access the [Failure Distribution Report in Lync Server 2013](lync-server-2013-failure-distribution-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="f9905-132">Unexpected failure volume (Объем неожиданных сбоев)</span><span class="sxs-lookup"><span data-stu-id="f9905-132">Unexpected failure volume</span></span>

  - <span data-ttu-id="f9905-133">Expected failure volume (Ожидаемый сбой, объем)</span><span class="sxs-lookup"><span data-stu-id="f9905-133">Expected failure volume</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-conference-diagnostic-report"></a><span data-ttu-id="f9905-134">Эффективное использование диагностического отчета по конференциям</span><span class="sxs-lookup"><span data-stu-id="f9905-134">Making the Best Use of the Conference Diagnostic Report</span></span>

<span data-ttu-id="f9905-135">В отчете диагностика Конференции есть ряд диаграмм.</span><span class="sxs-lookup"><span data-stu-id="f9905-135">The Conference Diagnostic Report includes a series of graphs.</span></span> <span data-ttu-id="f9905-136">Каждый столбец, показанный на диаграмме, действительно является гиперссылкой.</span><span class="sxs-lookup"><span data-stu-id="f9905-136">Each of the columns shown in the graph is actually a hyperlink.</span></span> <span data-ttu-id="f9905-137">Если щелкнуть столбец, в Lync Server 2013 в течение этого периода времени и типа конференции будет детально рассмотрен [отчет о распределении отказов](lync-server-2013-failure-distribution-report.md) .</span><span class="sxs-lookup"><span data-stu-id="f9905-137">If you click a column, you'll drill down to the [Failure Distribution Report in Lync Server 2013](lync-server-2013-failure-distribution-report.md) for that time period and that conference type.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="f9905-138">Фильтры</span><span class="sxs-lookup"><span data-stu-id="f9905-138">Filters</span></span>

<span data-ttu-id="f9905-p108">Фильтры позволяют вам возвратить уточненный набор данных или просматривать возвращенные данные различными способами. Например, диагностический отчет по конференциям позволяет вам выполнять фильтрацию по таким условиям, как тип проводимой конференции (например, конференция Focus) или используемый для конференции пограничный сервер. Вы также можете определить группировку данных. В данном случае конференции группируются по часу, дню, неделе или месяцу.</span><span class="sxs-lookup"><span data-stu-id="f9905-p108">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Conference Diagnostic Report enables you to filter on such things as the type of conference being conducted (for example, a Focus-based conference) or by the Edge Server used in the conference. You can also choose how data should be grouped. In this case, conferences are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="f9905-143">В следующей таблице перечислены фильтры, которые вы можете использовать в диагностическом отчете по конференциям.</span><span class="sxs-lookup"><span data-stu-id="f9905-143">The following table lists the filters that you can use with the Conference Diagnostic Report.</span></span>

### <a name="conference-diagnostic-report-filters"></a><span data-ttu-id="f9905-144">Фильтры диагностического отчета по конференциям</span><span class="sxs-lookup"><span data-stu-id="f9905-144">Conference Diagnostic Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f9905-145">Имя</span><span class="sxs-lookup"><span data-stu-id="f9905-145">Name</span></span></th>
<th><span data-ttu-id="f9905-146">Описание</span><span class="sxs-lookup"><span data-stu-id="f9905-146">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f9905-147"><strong>От</strong></span><span class="sxs-lookup"><span data-stu-id="f9905-147"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="f9905-p109">Начальные дата/время для временного диапазона. Чтобы просмотреть данные по часам, введите начальные дату и время следующим образом:</span><span class="sxs-lookup"><span data-stu-id="f9905-p109">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="f9905-150">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="f9905-150">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="f9905-p110">Если вы не вводите начальное время, отчет автоматически начинается с 12:00 AM указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</span><span class="sxs-lookup"><span data-stu-id="f9905-p110">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="f9905-153">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="f9905-153">7/7/2012</span></span></p>
<p><span data-ttu-id="f9905-154">Чтобы просмотреть данные за неделю или месяц, введите дату, выпадающую на любое время в рамках недели или месяца, которые вы хотите просмотреть (вам не требуется вводить первый день недели или месяца):</span><span class="sxs-lookup"><span data-stu-id="f9905-154">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="f9905-155">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="f9905-155">7/3/2012</span></span></p>
<p><span data-ttu-id="f9905-156">Недели всегда отсчитываются с воскресенья по субботу.</span><span class="sxs-lookup"><span data-stu-id="f9905-156">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9905-157"><strong>До</strong></span><span class="sxs-lookup"><span data-stu-id="f9905-157"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="f9905-p111">Конечные дата/время для временного диапазона. Чтобы просмотреть данные по часам, введите конечные дату и время следующим образом:</span><span class="sxs-lookup"><span data-stu-id="f9905-p111">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="f9905-160">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="f9905-160">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="f9905-p112">Если вы не вводите конечное время, отчет автоматически заканчивается в 12:00 AM указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</span><span class="sxs-lookup"><span data-stu-id="f9905-p112">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="f9905-163">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="f9905-163">7/7/2012</span></span></p>
<p><span data-ttu-id="f9905-164">Чтобы просмотреть данные за неделю или месяц, введите дату, выпадающую на любое время в рамках недели или месяца, которые вы хотите просмотреть (вам не требуется вводить первый день недели или месяца):</span><span class="sxs-lookup"><span data-stu-id="f9905-164">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="f9905-165">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="f9905-165">7/3/2012</span></span></p>
<p><span data-ttu-id="f9905-166">Недели всегда отсчитываются с воскресенья по субботу.</span><span class="sxs-lookup"><span data-stu-id="f9905-166">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f9905-167"><strong>Интервал</strong></span><span class="sxs-lookup"><span data-stu-id="f9905-167"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="f9905-p113">Временной интервал. Выберите одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="f9905-p113">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="f9905-170">Ежечасно (можно отобразить не более 25 часов)</span><span class="sxs-lookup"><span data-stu-id="f9905-170">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="f9905-171">Ежедневно (можно отобразить не более 31 дня)</span><span class="sxs-lookup"><span data-stu-id="f9905-171">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="f9905-172">Еженедельно (можно отобразить не более 12 недель)</span><span class="sxs-lookup"><span data-stu-id="f9905-172">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="f9905-173">Ежемесячно (можно отобразить не более 12 месяцев)</span><span class="sxs-lookup"><span data-stu-id="f9905-173">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="f9905-174">Если количество значений между начальной и конечной датами превышает максимально допустимое для выбранного интервала, отображается максимальное возможное количество значений (от начальной даты и далее).</span><span class="sxs-lookup"><span data-stu-id="f9905-174">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed.</span></span> <span data-ttu-id="f9905-175">Например, если выбрать ежедневный интервал с датой начала 7/7/2012 и датой окончания 2/28/2012, данные будут выводиться для дней 8/7/2012 12:00 – 9/7/2012 12:00 AM (то есть, всего за 31 дня).</span><span class="sxs-lookup"><span data-stu-id="f9905-175">For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9905-176"><strong>Пул</strong></span><span class="sxs-lookup"><span data-stu-id="f9905-176"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="f9905-p115">Полное доменное имя пула регистратора или пограничного сервера. Можно выбрать отдельный пул или нажать <strong>[Все]</strong>, чтобы просмотреть данные для всех пулов. Этот раскрывающийся список автоматически заполняется на основе записей в базе данных.</span><span class="sxs-lookup"><span data-stu-id="f9905-p115">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f9905-180"><strong>Сеансы конференц-связи</strong></span><span class="sxs-lookup"><span data-stu-id="f9905-180"><strong>Conference sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="f9905-p116">Указывает тип сеанса конференц-связи. Выберите одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="f9905-p116">Indicates the type of conferencing session. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="f9905-183">[All] (Все)</span><span class="sxs-lookup"><span data-stu-id="f9905-183">[All]</span></span></p></li>
<li><p><span data-ttu-id="f9905-184">Сеансы центра конференций</span><span class="sxs-lookup"><span data-stu-id="f9905-184">Focus sessions</span></span></p></li>
<li><p><span data-ttu-id="f9905-185">All MCU sessions (Все сеансы MCU)</span><span class="sxs-lookup"><span data-stu-id="f9905-185">All MCU sessions</span></span></p></li>
<li><p><span data-ttu-id="f9905-186">IM conferencing (Конференции с обменом мгновенными сообщениями)</span><span class="sxs-lookup"><span data-stu-id="f9905-186">IM conferencing</span></span></p></li>
<li><p><span data-ttu-id="f9905-187">Общий доступ к приложениям</span><span class="sxs-lookup"><span data-stu-id="f9905-187">Application sharing</span></span></p></li>
<li><p><span data-ttu-id="f9905-188">A/V conferencing (Аудио- и видеоконференции)</span><span class="sxs-lookup"><span data-stu-id="f9905-188">A/V conferencing</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="f9905-189">Показатели</span><span class="sxs-lookup"><span data-stu-id="f9905-189">Metrics</span></span>

<span data-ttu-id="f9905-190">В следующей таблице перечислены сведения, представленные в диагностическом отчете по конференциям.</span><span class="sxs-lookup"><span data-stu-id="f9905-190">The following table lists the information provided in the Conference Diagnostic Report for each type of conferencing session.</span></span>

### <a name="conference-diagnostic-report-metrics"></a><span data-ttu-id="f9905-191">Метрики диагностического отчета по конференциям</span><span class="sxs-lookup"><span data-stu-id="f9905-191">Conference Diagnostic Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f9905-192">Имя</span><span class="sxs-lookup"><span data-stu-id="f9905-192">Name</span></span></th>
<th><span data-ttu-id="f9905-193">Поддержка сортировки</span><span class="sxs-lookup"><span data-stu-id="f9905-193">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="f9905-194">Описание</span><span class="sxs-lookup"><span data-stu-id="f9905-194">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f9905-195"><strong>Success volume (Объем успешной связи)</strong></span><span class="sxs-lookup"><span data-stu-id="f9905-195"><strong>Success volume</strong></span></span></p></td>
<td><p><span data-ttu-id="f9905-196">Нет</span><span class="sxs-lookup"><span data-stu-id="f9905-196">No</span></span></p></td>
<td><p><span data-ttu-id="f9905-197">Общее число успешных конференций.</span><span class="sxs-lookup"><span data-stu-id="f9905-197">Total number of successful conferences.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9905-198"><strong>Доля успешной связи</strong></span><span class="sxs-lookup"><span data-stu-id="f9905-198"><strong>Success percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="f9905-199">Нет</span><span class="sxs-lookup"><span data-stu-id="f9905-199">No</span></span></p></td>
<td><p><span data-ttu-id="f9905-p117">Процентное отношение конференций, которые были завершены со значительными проблемами. Значение вычисляется путем деления значения «Success volume» (Успех, процент) на значение «Total sessions» (Всего сеансов).</span><span class="sxs-lookup"><span data-stu-id="f9905-p117">Percentage of conferences that completed with significant problems. Calculated by dividing the Success volume by the Total sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f9905-202"><strong>Unexpected failure volume (Объем неожиданных сбоев)</strong></span><span class="sxs-lookup"><span data-stu-id="f9905-202"><strong>Expected failure volume</strong></span></span></p></td>
<td><p><span data-ttu-id="f9905-203">Нет</span><span class="sxs-lookup"><span data-stu-id="f9905-203">No</span></span></p></td>
<td><p><span data-ttu-id="f9905-204">Общее количество конференций, в &quot;которых произошла&quot; ожидаемая ошибка.</span><span class="sxs-lookup"><span data-stu-id="f9905-204">Total number of conferences where an &quot;expected failure&quot; occurred.</span></span></p>
<p><span data-ttu-id="f9905-p118">Ожидаемый сбой ? это сбой, возникновение которого ожидаемо. Например, если пользователь задал для себя состояние «Не беспокоить», можно ожидать, что любой звонок этому пользователю будет неудачным.</span><span class="sxs-lookup"><span data-stu-id="f9905-p118">An expected failure is a failure that is expected to happen. For example, if a user has set his or her status to Do Not Disturb you would expect any call to that user to fail.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9905-207"><strong>Expected failure percentage (Доля ожидаемых сбоев)</strong></span><span class="sxs-lookup"><span data-stu-id="f9905-207"><strong>Expected failure percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="f9905-208">Нет</span><span class="sxs-lookup"><span data-stu-id="f9905-208">No</span></span></p></td>
<td><p><span data-ttu-id="f9905-p119">Процентное отношение конференций, для которых возник ожидаемый сбой. Значение вычисляется путем деления значения «Expected failure volume» (Ожидаемый сбой, объем) на значение «Total sessions» (Всего сеансов).</span><span class="sxs-lookup"><span data-stu-id="f9905-p119">Percentage of conferences that experienced an expected error. Calculated by dividing the Expected failure volume by the Total sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f9905-211"><strong>Unexpected failure volume (Объем неожиданных сбоев)</strong></span><span class="sxs-lookup"><span data-stu-id="f9905-211"><strong>Unexpected failure volume</strong></span></span></p></td>
<td><p><span data-ttu-id="f9905-212">Нет</span><span class="sxs-lookup"><span data-stu-id="f9905-212">No</span></span></p></td>
<td><p><span data-ttu-id="f9905-213">Общее количество конференций, в &quot;которых произошла&quot; непредвиденная ошибка.</span><span class="sxs-lookup"><span data-stu-id="f9905-213">Total number of conferences where an &quot;unexpected failure&quot; occurred.</span></span></p>
<p><span data-ttu-id="f9905-p120">Неожиданный сбой ? это событие, которое в других условиях считалось бы нормальной работой системы. Например, звонок не следует завершать, если звонящий переведен в режим удержания. Если такое произошло, данное событие будет обозначено как неожиданный сбой.</span><span class="sxs-lookup"><span data-stu-id="f9905-p120">An unexpected failure is a failure that occurs in what would appear to be an otherwise healthy system. For example, a call should not be terminated if the caller is placed on hold. If that occurs, that would be flagged as an unexpected failure.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9905-217"><strong>Unexpected failure percentage (Доля неожиданных сбоев)</strong></span><span class="sxs-lookup"><span data-stu-id="f9905-217"><strong>Unexpected failure percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="f9905-218">Нет</span><span class="sxs-lookup"><span data-stu-id="f9905-218">No</span></span></p></td>
<td><p><span data-ttu-id="f9905-p121">Процентное отношение конференций, для которых возник неожиданный сбой. Значение вычисляется путем деления значения «Unexpected failure volume» (Неожиданный сбой, объем) на значение «Total sessions» (Всего сеансов).</span><span class="sxs-lookup"><span data-stu-id="f9905-p121">Percentage of conferences that experienced an unexpected error. Calculated by dividing the Unexpected failure volume by the Total sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f9905-221"><strong>Всего сеансов</strong></span><span class="sxs-lookup"><span data-stu-id="f9905-221"><strong>Total sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="f9905-222">Нет</span><span class="sxs-lookup"><span data-stu-id="f9905-222">No</span></span></p></td>
<td><p><span data-ttu-id="f9905-223">Общее число конференций, включая успешные конференции, неуспешные (как с ожидаемыми, так и с неожиданными сбоями) конференции и конференции, не отнесенные ни к одной из категорий.</span><span class="sxs-lookup"><span data-stu-id="f9905-223">Total number of conferences, including successful conferences, failed conferences (both expected failures and unexpected failures), and uncategorized conferences.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

