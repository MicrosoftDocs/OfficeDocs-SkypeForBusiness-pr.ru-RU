---
title: 'Lync Server 2013: сводный отчет по диагностике звонков'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call Diagnostic Summary Report
ms:assetid: 9091de56-13e6-440e-9353-f57c10c906fe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615016(v=OCS.15)
ms:contentKeyID: 48184789
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0ebd3da761fe9923f05c2ddd5dfced852b4b27e6
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134245"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="call-diagnostic-summary-report-in-lync-server-2013"></a><span data-ttu-id="fa7e4-102">Сводный отчет по диагностике звонков в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fa7e4-102">Call Diagnostic Summary Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fa7e4-103">_**Последнее изменение темы:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="fa7e4-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="fa7e4-p101">Сводный диагностический отчет по вызовам предоставляет полную сводку по неудачным одноранговым сеансам и сеансам конференц-связи. Этот отчет показывает общее количество сбоев для обоих типов сеансов, и далее разбивает сведения о сбое по следующим типам модальности сеанса:</span><span class="sxs-lookup"><span data-stu-id="fa7e4-p101">The Call Diagnostic Summary Report provides an overall look at failed peer-to-peer and conferencing sessions. The report shows the overall failure rate for both types of sessions, and further breaks the failure information down by session modality type:</span></span>

  - <span data-ttu-id="fa7e4-106">Обмен мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="fa7e4-106">Instant messaging</span></span>

  - <span data-ttu-id="fa7e4-107">Общий доступ к приложениям</span><span class="sxs-lookup"><span data-stu-id="fa7e4-107">Application sharing</span></span>

  - <span data-ttu-id="fa7e4-108">Передача файлов</span><span class="sxs-lookup"><span data-stu-id="fa7e4-108">File transfer</span></span>

  - <span data-ttu-id="fa7e4-109">"Audio" (Аудио);</span><span class="sxs-lookup"><span data-stu-id="fa7e4-109">Audio</span></span>

  - <span data-ttu-id="fa7e4-110">"Video" (Видео);</span><span class="sxs-lookup"><span data-stu-id="fa7e4-110">Video</span></span>

<div>

## <a name="accessing-the-call-diagnostic-summary-report"></a><span data-ttu-id="fa7e4-111">Доступ к сводному диагностическому отчету по вызовам</span><span class="sxs-lookup"><span data-stu-id="fa7e4-111">Accessing the Call Diagnostic Summary Report</span></span>

<span data-ttu-id="fa7e4-112">Доступ к сводному диагностическому отчету по вызовам можно получить на домашней странице отчетов мониторинга.</span><span class="sxs-lookup"><span data-stu-id="fa7e4-112">The Call Diagnostic Summary Report is accessed from the Monitoring Reports Home page.</span></span> <span data-ttu-id="fa7e4-113">В сводном отчете диагностики звонков можно получить доступ к [диагностическим отчету по одноранговым действиям в Lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md) , щелкнув метрику частота сбоев в разделе "Сводка по одноранговому сеансу" отчета.</span><span class="sxs-lookup"><span data-stu-id="fa7e4-113">From the Call Diagnostic Summary Report you can access the [Peer-to-Peer Activity Diagnostic Report in Lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md) by clicking the Failure rate metric under the Peer-to-Peer Session Summary section of the report.</span></span> <span data-ttu-id="fa7e4-114">Вы также можете получить доступ к [диагностическим отчетам конференций в Lync Server 2013](lync-server-2013-conference-diagnostic-report.md) , щелкнув любую из следующих метрик конференции:</span><span class="sxs-lookup"><span data-stu-id="fa7e4-114">You can also access the [Conference Diagnostic Report in Lync Server 2013](lync-server-2013-conference-diagnostic-report.md) by clicking any of the following conference metrics:</span></span>

  - <span data-ttu-id="fa7e4-115">Overall session failure rate (Общее количество неудачных сеансов)</span><span class="sxs-lookup"><span data-stu-id="fa7e4-115">Overall session failure rate</span></span>

  - <span data-ttu-id="fa7e4-116">Focus failure rate (Неудачные сеансы с центром)</span><span class="sxs-lookup"><span data-stu-id="fa7e4-116">Focus failure rate</span></span>

  - <span data-ttu-id="fa7e4-117">MCU failure rate (Неудачные сеансы с MCU)</span><span class="sxs-lookup"><span data-stu-id="fa7e4-117">MCU failure rate</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-call-diagnostic-summary-report"></a><span data-ttu-id="fa7e4-118">Эффективное использование сводного диагностического отчета по вызовам</span><span class="sxs-lookup"><span data-stu-id="fa7e4-118">Making the Best Use of the Call Diagnostic Summary Report</span></span>

<span data-ttu-id="fa7e4-119">Сводный отчет по диагностике звонков содержит графики, которые сравнивают показатели сбоев для различных модальности, используемых в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fa7e4-119">The Call Diagnostic Summary Report includes graphs that compare failure rates for the various modalities used in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="fa7e4-120">Столбцы на этих графиках фактически гиперссылками; Например, если щелкнуть столбец обмен мгновенными сообщениями для одноранговых сеансов, вы узнаете, как перейти к экземпляру [диагностического отчета по одноранговым действиям в Lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md), который предоставляет дополнительные сведения о всех сеансах обмена мгновенными сообщениями, включенных в сводный отчет по диагностике звонков.</span><span class="sxs-lookup"><span data-stu-id="fa7e4-120">The columns in these graphs are actually hotlinks; for example, if you click the Instant messaging column for peer-to-peer sessions, you'll drill down to an instance of the [Peer-to-Peer Activity Diagnostic Report in Lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md), a report that provides additional details about all the instant messaging sessions included in the Call Diagnostic Summary Report.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="fa7e4-121">Фильтры</span><span class="sxs-lookup"><span data-stu-id="fa7e4-121">Filters</span></span>

<span data-ttu-id="fa7e4-p104">Фильтры позволяют получать более адресный набор данных или просматривать полученные данные разными способами. Например, в сводном диагностическом отчете по вызовам можно выполнять фильтрацию по пулу регистратора или по пограничному серверу, использовавшемуся в сеансе. Можно также выбрать способ группирования данных. В этом случае вызовы группируются по часу, дню, неделе или месяцу.</span><span class="sxs-lookup"><span data-stu-id="fa7e4-p104">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Call Diagnostic Summary Report enables you to filter on such things as the Registrar pool or Edge Server used in the session. You can also choose how data should be grouped. In this case, calls are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="fa7e4-126">В следующей таблице перечислены фильтры, которые можно использовать в сводном диагностическом отчете по вызовам.</span><span class="sxs-lookup"><span data-stu-id="fa7e4-126">The following table lists the filters that you can use with the Call Diagnostic Summary Report.</span></span>

### <a name="call-diagnostic-summary-report-filters"></a><span data-ttu-id="fa7e4-127">Фильтры сводного диагностического отчета по вызовам</span><span class="sxs-lookup"><span data-stu-id="fa7e4-127">Call Diagnostic Summary Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fa7e4-128">Имя</span><span class="sxs-lookup"><span data-stu-id="fa7e4-128">Name</span></span></th>
<th><span data-ttu-id="fa7e4-129">Описание</span><span class="sxs-lookup"><span data-stu-id="fa7e4-129">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fa7e4-130"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="fa7e4-130"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7e4-p105">Дата и время начала диапазона. Чтобы просмотреть данные по часам, введите дату и время начала в следующем формате:</span><span class="sxs-lookup"><span data-stu-id="fa7e4-p105">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="fa7e4-133">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="fa7e4-133">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="fa7e4-p106">Если не указать время начала, автоматически будет выбрано время 00:00 указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</span><span class="sxs-lookup"><span data-stu-id="fa7e4-p106">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="fa7e4-136">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="fa7e4-136">7/7/2012</span></span></p>
<p><span data-ttu-id="fa7e4-137">Для просмотра по неделям или по месяцам введите дату, выпадающую на любой день недели или месяца, который вы хотите просмотреть (это необязательно должен быть первый день недели или месяца):</span><span class="sxs-lookup"><span data-stu-id="fa7e4-137">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="fa7e4-138">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="fa7e4-138">7/3/2012</span></span></p>
<p><span data-ttu-id="fa7e4-139">Недели всегда начинаются с Воскресенья и заканчиваются в Субботу.</span><span class="sxs-lookup"><span data-stu-id="fa7e4-139">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa7e4-140"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="fa7e4-140"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7e4-p107">Дата и время окончания диапазона. Чтобы просмотреть данные по часам, введите дату и время окончания в следующем формате:</span><span class="sxs-lookup"><span data-stu-id="fa7e4-p107">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="fa7e4-143">7/7/2012 13:00.</span><span class="sxs-lookup"><span data-stu-id="fa7e4-143">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="fa7e4-p108">Если не указать время окончания, автоматически будет выбрано время 00:00 указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</span><span class="sxs-lookup"><span data-stu-id="fa7e4-p108">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="fa7e4-146">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="fa7e4-146">7/7/2012</span></span></p>
<p><span data-ttu-id="fa7e4-147">Для просмотра по неделям или по месяцам введите дату, выпадающую на любой день недели или месяца, который вы хотите просмотреть (это необязательно должен быть первый день недели или месяца):</span><span class="sxs-lookup"><span data-stu-id="fa7e4-147">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="fa7e4-148">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="fa7e4-148">7/3/2012</span></span></p>
<p><span data-ttu-id="fa7e4-149">Неделя всегда начинается с воскресения и заканчивается субботой.</span><span class="sxs-lookup"><span data-stu-id="fa7e4-149">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa7e4-150"><strong>Interval</strong></span><span class="sxs-lookup"><span data-stu-id="fa7e4-150"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7e4-p109">Временной интервал. Выберите один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="fa7e4-p109">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="fa7e4-153">Ежечасно (может отображаться до 25 часов)</span><span class="sxs-lookup"><span data-stu-id="fa7e4-153">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="fa7e4-154">Ежедневно (может отображаться до 31 дня)</span><span class="sxs-lookup"><span data-stu-id="fa7e4-154">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="fa7e4-155">Еженедельно (может отображаться до 12 недель)</span><span class="sxs-lookup"><span data-stu-id="fa7e4-155">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="fa7e4-156">Ежемесячно (может отображаться до 12 месяцев)</span><span class="sxs-lookup"><span data-stu-id="fa7e4-156">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="fa7e4-p110">Если начальная и конечная даты превышают максимально допустимое количество значений для выбранного интервала, отображается только максимальное число значений (с отсчетом от начальной даты). Например, если вы выбрали интервал «Daily» с начальной датой 7/7/2012 и конечной датой 2/28/2012, отображаются данные по дням с 00:00 часов 8/7/2012  по 00:00 часов 9/7/2012 (то есть всего за 31 день).</span><span class="sxs-lookup"><span data-stu-id="fa7e4-p110">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa7e4-159"><strong>Ресурсов</strong></span><span class="sxs-lookup"><span data-stu-id="fa7e4-159"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7e4-p111">Полное доменное имя пула регистратора или пограничного сервера. Можно выбрать отдельный пул или нажать <strong>[All] ([Все])</strong>, чтобы просмотреть данные для всех пулов. Этот раскрывающийся список автоматически заполняется на основе записей в базе данных.</span><span class="sxs-lookup"><span data-stu-id="fa7e4-p111">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="fa7e4-163">Метрики для одноранговых сеансов</span><span class="sxs-lookup"><span data-stu-id="fa7e4-163">Metrics for Peer-to-Peer Sessions</span></span>

<span data-ttu-id="fa7e4-164">В следующей таблице приведены сведения, предоставляемые отчетом по контролю допуска звонков для одноранговых сеансов (т.е. сеансов, в которых только два участника).</span><span class="sxs-lookup"><span data-stu-id="fa7e4-164">The following table lists the information provided in the Call Diagnostic Summary Report for peer-to-peer sessions (that is, sessions involving just two participants).</span></span>

### <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="fa7e4-165">Метрики для одноранговых сеансов</span><span class="sxs-lookup"><span data-stu-id="fa7e4-165">Metrics for Peer-to-Peer Sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fa7e4-166">Имя</span><span class="sxs-lookup"><span data-stu-id="fa7e4-166">Name</span></span></th>
<th><span data-ttu-id="fa7e4-167">Возможность сортировки по этому показателю</span><span class="sxs-lookup"><span data-stu-id="fa7e4-167">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="fa7e4-168">Описание</span><span class="sxs-lookup"><span data-stu-id="fa7e4-168">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fa7e4-169"><strong> Всего сеансов </strong></span><span class="sxs-lookup"><span data-stu-id="fa7e4-169"><strong>Total sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7e4-170">Нет</span><span class="sxs-lookup"><span data-stu-id="fa7e4-170">No</span></span></p></td>
<td><p><span data-ttu-id="fa7e4-171">Общее количество проведенных одноранговых сеансов.</span><span class="sxs-lookup"><span data-stu-id="fa7e4-171">Total number of peer-to-peer sessions conducted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa7e4-172"><strong>Failure rate (Количество неудачных сеансов)</strong></span><span class="sxs-lookup"><span data-stu-id="fa7e4-172"><strong>Failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7e4-173">Нет</span><span class="sxs-lookup"><span data-stu-id="fa7e4-173">No</span></span></p></td>
<td><p><span data-ttu-id="fa7e4-p112">Процент неудачных одноранговых сеансов. Если щелкнуть этот элемент, то появится диагностический отчет по одноранговым действиям, отображающий более подробные сведения о неудачных одноранговых сеансах.</span><span class="sxs-lookup"><span data-stu-id="fa7e4-p112">Percentage of peer-to-peer sessions that failed. When you click this item, the report shows the Peer-to-Peer Activity Diagnostic report, which displays more detailed information about the failed peer-to-peer sessions.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="fa7e4-176">Метрики для сеансов конференц-связи</span><span class="sxs-lookup"><span data-stu-id="fa7e4-176">Metrics for Conferencing Sessions</span></span>

<span data-ttu-id="fa7e4-177">В следующей таблице приведены сведения, которые предоставляются в диагностическом отчете по вызовам для сеансов конференц-связи (т.е. сеансов, в которых не менее трех участников).</span><span class="sxs-lookup"><span data-stu-id="fa7e4-177">The following table lists the information provided in the Call Diagnostic Report for conferencing sessions (that is, sessions involving three or more participants).</span></span>

### <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="fa7e4-178">Метрики для сеансов конференц-связи</span><span class="sxs-lookup"><span data-stu-id="fa7e4-178">Metrics for Conferencing Sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fa7e4-179">Имя</span><span class="sxs-lookup"><span data-stu-id="fa7e4-179">Name</span></span></th>
<th><span data-ttu-id="fa7e4-180">Возможность сортировки по этому показателю</span><span class="sxs-lookup"><span data-stu-id="fa7e4-180">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="fa7e4-181">Описание</span><span class="sxs-lookup"><span data-stu-id="fa7e4-181">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fa7e4-182"><strong>Total conferences</strong> (Всего конференций)</span><span class="sxs-lookup"><span data-stu-id="fa7e4-182"><strong>Total conferences</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7e4-183">Нет</span><span class="sxs-lookup"><span data-stu-id="fa7e4-183">No</span></span></p></td>
<td><p><span data-ttu-id="fa7e4-184">Общее количество проведенных конференций.</span><span class="sxs-lookup"><span data-stu-id="fa7e4-184">Total number of conferences conducted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa7e4-185"><strong>Общее количество сеансов конференц-связи</strong></span><span class="sxs-lookup"><span data-stu-id="fa7e4-185"><strong>Total conference sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7e4-186">Нет</span><span class="sxs-lookup"><span data-stu-id="fa7e4-186">No</span></span></p></td>
<td><p><span data-ttu-id="fa7e4-187">Общее количество проведенных сеансов конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="fa7e4-187">Total number of conferencing sessions conducted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa7e4-188"><strong>Overall session failure rate (Общее количество неудачных сеансов)</strong></span><span class="sxs-lookup"><span data-stu-id="fa7e4-188"><strong>Overall session failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7e4-189">Нет</span><span class="sxs-lookup"><span data-stu-id="fa7e4-189">No</span></span></p></td>
<td><p><span data-ttu-id="fa7e4-190">Процент неудачных сеансов конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="fa7e4-190">Percentage of the total conferencing sessions that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa7e4-191"><strong>Focus sessions (Сеансы с центром)</strong></span><span class="sxs-lookup"><span data-stu-id="fa7e4-191"><strong>Focus sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7e4-192">Нет</span><span class="sxs-lookup"><span data-stu-id="fa7e4-192">No</span></span></p></td>
<td><p><span data-ttu-id="fa7e4-193">Общее количество неудачных сеансов конференц-связи с центром.</span><span class="sxs-lookup"><span data-stu-id="fa7e4-193">Total number of Focus-based conferencing sessions that failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa7e4-194"><strong>Focus failure rate (Неудачные сеансы с центром)</strong></span><span class="sxs-lookup"><span data-stu-id="fa7e4-194"><strong>Focus failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7e4-195">Нет</span><span class="sxs-lookup"><span data-stu-id="fa7e4-195">No</span></span></p></td>
<td><p><span data-ttu-id="fa7e4-196">Процент неудачных сеансов конференц-связи с центром.</span><span class="sxs-lookup"><span data-stu-id="fa7e4-196">Percentage of the Focus-based conferencing sessions that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa7e4-197"><strong>MCU sessions (Сеансы с MCU)</strong></span><span class="sxs-lookup"><span data-stu-id="fa7e4-197"><strong>MCU sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7e4-198">Нет</span><span class="sxs-lookup"><span data-stu-id="fa7e4-198">No</span></span></p></td>
<td><p><span data-ttu-id="fa7e4-199">Общее количество неудачных сеансов конференц-связи для конференций на основе сервера (ранее называвшегося узлом управления многосторонней связью или MCU).</span><span class="sxs-lookup"><span data-stu-id="fa7e4-199">Total number of conferencing server-based (formerly known as Multipoint Control Unit or MCU) conferences that failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa7e4-200"><strong>MCU failure rate (Неудачные сеансы с MCU)</strong></span><span class="sxs-lookup"><span data-stu-id="fa7e4-200"><strong>MCU failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7e4-201">Нет</span><span class="sxs-lookup"><span data-stu-id="fa7e4-201">No</span></span></p></td>
<td><p><span data-ttu-id="fa7e4-202">Процент неудачных сеансов конференц-связи для конференций на основе сервера (ранее называвшегося узлом управления многосторонней связью или MCU).</span><span class="sxs-lookup"><span data-stu-id="fa7e4-202">Percentage of the conferencing server-based (formerly known as Multipoint Control Unit or MCU) conferences that failed.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

