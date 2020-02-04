---
title: 'Lync Server 2013: сводный отчет о звонке'
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
ms.openlocfilehash: 0228af8690fe7170fc4fd77e72f67f6cb3adc08c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743039"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-diagnostic-summary-report-in-lync-server-2013"></a><span data-ttu-id="ad392-102">Сводный отчет о звонке в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ad392-102">Call Diagnostic Summary Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ad392-103">_**Тема последнего изменения:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="ad392-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="ad392-p101">Сводный диагностический отчет по вызовам предоставляет полную сводку по неудачным одноранговым сеансам и сеансам конференц-связи. Этот отчет показывает общее количество сбоев для обоих типов сеансов, и далее разбивает сведения о сбое по следующим типам модальности сеанса:</span><span class="sxs-lookup"><span data-stu-id="ad392-p101">The Call Diagnostic Summary Report provides an overall look at failed peer-to-peer and conferencing sessions. The report shows the overall failure rate for both types of sessions, and further breaks the failure information down by session modality type:</span></span>

  - <span data-ttu-id="ad392-106">Обмен мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="ad392-106">Instant messaging</span></span>

  - <span data-ttu-id="ad392-107">Общий доступ к приложениям</span><span class="sxs-lookup"><span data-stu-id="ad392-107">Application sharing</span></span>

  - <span data-ttu-id="ad392-108">Передача файлов</span><span class="sxs-lookup"><span data-stu-id="ad392-108">File transfer</span></span>

  - <span data-ttu-id="ad392-109">Аудио</span><span class="sxs-lookup"><span data-stu-id="ad392-109">Audio</span></span>

  - <span data-ttu-id="ad392-110">Видео</span><span class="sxs-lookup"><span data-stu-id="ad392-110">Video</span></span>

<div>

## <a name="accessing-the-call-diagnostic-summary-report"></a><span data-ttu-id="ad392-111">Доступ к сводному диагностическому отчету по вызовам</span><span class="sxs-lookup"><span data-stu-id="ad392-111">Accessing the Call Diagnostic Summary Report</span></span>

<span data-ttu-id="ad392-112">The Call Diagnostic Summary Report is accessed from the Monitoring Reports Home page.</span><span class="sxs-lookup"><span data-stu-id="ad392-112">The Call Diagnostic Summary Report is accessed from the Monitoring Reports Home page.</span></span> <span data-ttu-id="ad392-113">Из сводного отчета "Диагностика звонков" вы можете получить доступ к [диагностическим отчету о действиях одноранговых групп в Lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md) , щелкнув метрику частота сбоя в разделе "одноранговый сеанс" в сводном отчете.</span><span class="sxs-lookup"><span data-stu-id="ad392-113">From the Call Diagnostic Summary Report you can access the [Peer-to-Peer Activity Diagnostic Report in Lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md) by clicking the Failure rate metric under the Peer-to-Peer Session Summary section of the report.</span></span> <span data-ttu-id="ad392-114">Вы также можете получить доступ к [диагностическим отчетам на Конференции в Lync Server 2013](lync-server-2013-conference-diagnostic-report.md) , щелкнув одну из следующих метрик конференции:</span><span class="sxs-lookup"><span data-stu-id="ad392-114">You can also access the [Conference Diagnostic Report in Lync Server 2013](lync-server-2013-conference-diagnostic-report.md) by clicking any of the following conference metrics:</span></span>

  - <span data-ttu-id="ad392-115">Общая доля сбоев сеансов</span><span class="sxs-lookup"><span data-stu-id="ad392-115">Overall session failure rate</span></span>

  - <span data-ttu-id="ad392-116">Доля сбоев центра конференций</span><span class="sxs-lookup"><span data-stu-id="ad392-116">Focus failure rate</span></span>

  - <span data-ttu-id="ad392-117">Доля сбоев MCU</span><span class="sxs-lookup"><span data-stu-id="ad392-117">MCU failure rate</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-call-diagnostic-summary-report"></a><span data-ttu-id="ad392-118">Эффективное использование сводного диагностического отчета по вызовам</span><span class="sxs-lookup"><span data-stu-id="ad392-118">Making the Best Use of the Call Diagnostic Summary Report</span></span>

<span data-ttu-id="ad392-119">Сводный отчет о звонке содержит графики, которые сравнивают тарифы на ошибки для различных модальностей, используемых в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ad392-119">The Call Diagnostic Summary Report includes graphs that compare failure rates for the various modalities used in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="ad392-120">Столбцы на этих графах фактически хотлинкс; Например, если щелкнуть столбец "мгновенные сообщения" для одноранговых сеансов, вы узнаете, как перейти к экземпляру [диагностического отчета о действиях одноранговых участников в Lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md), который содержит дополнительные сведения о всех сеансах обмена мгновенными сообщениями, включенных в сводный отчет о звонке.</span><span class="sxs-lookup"><span data-stu-id="ad392-120">The columns in these graphs are actually hotlinks; for example, if you click the Instant messaging column for peer-to-peer sessions, you'll drill down to an instance of the [Peer-to-Peer Activity Diagnostic Report in Lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md), a report that provides additional details about all the instant messaging sessions included in the Call Diagnostic Summary Report.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="ad392-121">Фильтры</span><span class="sxs-lookup"><span data-stu-id="ad392-121">Filters</span></span>

<span data-ttu-id="ad392-p104">Фильтры позволяют получать более адресный набор данных или просматривать полученные данные разными способами. Например, в сводном диагностическом отчете по вызовам можно выполнять фильтрацию по пулу регистратора или по пограничному серверу, использовавшемуся в сеансе. Можно также выбрать способ группирования данных. В этом случае вызовы группируются по часу, дню, неделе или месяцу.</span><span class="sxs-lookup"><span data-stu-id="ad392-p104">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Call Diagnostic Summary Report enables you to filter on such things as the Registrar pool or Edge Server used in the session. You can also choose how data should be grouped. In this case, calls are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="ad392-126">В следующей таблице перечислены фильтры, которые можно использовать в сводном диагностическом отчете по вызовам.</span><span class="sxs-lookup"><span data-stu-id="ad392-126">The following table lists the filters that you can use with the Call Diagnostic Summary Report.</span></span>

### <a name="call-diagnostic-summary-report-filters"></a><span data-ttu-id="ad392-127">Фильтры сводного диагностического отчета по вызовам</span><span class="sxs-lookup"><span data-stu-id="ad392-127">Call Diagnostic Summary Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ad392-128">Имя</span><span class="sxs-lookup"><span data-stu-id="ad392-128">Name</span></span></th>
<th><span data-ttu-id="ad392-129">Описание</span><span class="sxs-lookup"><span data-stu-id="ad392-129">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ad392-130"><strong>От</strong></span><span class="sxs-lookup"><span data-stu-id="ad392-130"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="ad392-p105">Начальные дата/время для временного диапазона. Чтобы просмотреть данные по часам, введите начальные дату и время следующим образом:</span><span class="sxs-lookup"><span data-stu-id="ad392-p105">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="ad392-133">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="ad392-133">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="ad392-p106">Если вы не вводите начальное время, отчет автоматически начинается с 12:00 AM указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</span><span class="sxs-lookup"><span data-stu-id="ad392-p106">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="ad392-136">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="ad392-136">7/7/2012</span></span></p>
<p><span data-ttu-id="ad392-137">Чтобы просмотреть данные за неделю или месяц, введите дату, выпадающую на любое время в рамках недели или месяца, которые вы хотите просмотреть (вам не требуется вводить первый день недели или месяца):</span><span class="sxs-lookup"><span data-stu-id="ad392-137">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="ad392-138">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="ad392-138">7/3/2012</span></span></p>
<p><span data-ttu-id="ad392-139">Недели всегда отсчитываются с воскресенья по субботу.</span><span class="sxs-lookup"><span data-stu-id="ad392-139">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad392-140"><strong>До</strong></span><span class="sxs-lookup"><span data-stu-id="ad392-140"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="ad392-p107">Конечные дата/время для временного диапазона. Чтобы просмотреть данные по часам, введите конечные дату и время следующим образом:</span><span class="sxs-lookup"><span data-stu-id="ad392-p107">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="ad392-143">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="ad392-143">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="ad392-p108">Если вы не вводите конечное время, отчет автоматически заканчивается в 12:00 AM указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</span><span class="sxs-lookup"><span data-stu-id="ad392-p108">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="ad392-146">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="ad392-146">7/7/2012</span></span></p>
<p><span data-ttu-id="ad392-147">Чтобы просмотреть данные за неделю или месяц, введите дату, выпадающую на любое время в рамках недели или месяца, которые вы хотите просмотреть (вам не требуется вводить первый день недели или месяца):</span><span class="sxs-lookup"><span data-stu-id="ad392-147">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="ad392-148">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="ad392-148">7/3/2012</span></span></p>
<p><span data-ttu-id="ad392-149">Недели всегда отсчитываются с воскресенья по субботу.</span><span class="sxs-lookup"><span data-stu-id="ad392-149">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad392-150"><strong>Интервал</strong></span><span class="sxs-lookup"><span data-stu-id="ad392-150"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="ad392-p109">Временной интервал. Выберите одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="ad392-p109">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="ad392-153">Ежечасно (можно отобразить не более 25 часов)</span><span class="sxs-lookup"><span data-stu-id="ad392-153">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="ad392-154">Ежедневно (можно отобразить не более 31 дня)</span><span class="sxs-lookup"><span data-stu-id="ad392-154">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="ad392-155">Еженедельно (можно отобразить не более 12 недель)</span><span class="sxs-lookup"><span data-stu-id="ad392-155">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="ad392-156">Ежемесячно (можно отобразить не более 12 месяцев)</span><span class="sxs-lookup"><span data-stu-id="ad392-156">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="ad392-157">Если количество значений между начальной и конечной датами превышает максимально допустимое для выбранного интервала, отображается максимальное возможное количество значений (от начальной даты и далее).</span><span class="sxs-lookup"><span data-stu-id="ad392-157">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed.</span></span> <span data-ttu-id="ad392-158">Например, если выбрать ежедневный интервал с датой начала 7/7/2012 и датой окончания 2/28/2012, данные будут выводиться для дней 8/7/2012 12:00 – 9/7/2012 12:00 AM (то есть, всего за 31 дня).</span><span class="sxs-lookup"><span data-stu-id="ad392-158">For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad392-159"><strong>Пул</strong></span><span class="sxs-lookup"><span data-stu-id="ad392-159"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="ad392-p111">Полное доменное имя пула регистратора или пограничного сервера. Можно выбрать отдельный пул или нажать <strong>[Все]</strong>, чтобы просмотреть данные для всех пулов. Этот раскрывающийся список автоматически заполняется на основе записей в базе данных.</span><span class="sxs-lookup"><span data-stu-id="ad392-p111">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="ad392-163">Метрики для одноранговых сеансов</span><span class="sxs-lookup"><span data-stu-id="ad392-163">Metrics for Peer-to-Peer Sessions</span></span>

<span data-ttu-id="ad392-164">В следующей таблице приведены сведения, предоставляемые отчетом по контролю допуска звонков для одноранговых сеансов (т.е. сеансов, в которых только два участника).</span><span class="sxs-lookup"><span data-stu-id="ad392-164">The following table lists the information provided in the Call Diagnostic Summary Report for peer-to-peer sessions (that is, sessions involving just two participants).</span></span>

### <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="ad392-165">Метрики для одноранговых сеансов</span><span class="sxs-lookup"><span data-stu-id="ad392-165">Metrics for Peer-to-Peer Sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ad392-166">Имя</span><span class="sxs-lookup"><span data-stu-id="ad392-166">Name</span></span></th>
<th><span data-ttu-id="ad392-167">Поддержка сортировки</span><span class="sxs-lookup"><span data-stu-id="ad392-167">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="ad392-168">Описание</span><span class="sxs-lookup"><span data-stu-id="ad392-168">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ad392-169"><strong>Всего сеансов</strong></span><span class="sxs-lookup"><span data-stu-id="ad392-169"><strong>Total sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="ad392-170">Нет</span><span class="sxs-lookup"><span data-stu-id="ad392-170">No</span></span></p></td>
<td><p><span data-ttu-id="ad392-171">Общее количество проведенных одноранговых сеансов.</span><span class="sxs-lookup"><span data-stu-id="ad392-171">Total number of peer-to-peer sessions conducted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad392-172"><strong>Процент сбоев</strong></span><span class="sxs-lookup"><span data-stu-id="ad392-172"><strong>Failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="ad392-173">Нет</span><span class="sxs-lookup"><span data-stu-id="ad392-173">No</span></span></p></td>
<td><p><span data-ttu-id="ad392-p112">Процент неудачных одноранговых сеансов. Если щелкнуть этот элемент, то появится диагностический отчет по одноранговым действиям, отображающий более подробные сведения о неудачных одноранговых сеансах.</span><span class="sxs-lookup"><span data-stu-id="ad392-p112">Percentage of peer-to-peer sessions that failed. When you click this item, the report shows the Peer-to-Peer Activity Diagnostic report, which displays more detailed information about the failed peer-to-peer sessions.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="ad392-176">Метрики для сеансов конференц-связи</span><span class="sxs-lookup"><span data-stu-id="ad392-176">Metrics for Conferencing Sessions</span></span>

<span data-ttu-id="ad392-177">В следующей таблице приведены сведения, которые предоставляются в диагностическом отчете по вызовам для сеансов конференц-связи (т.е. сеансов, в которых не менее трех участников).</span><span class="sxs-lookup"><span data-stu-id="ad392-177">The following table lists the information provided in the Call Diagnostic Report for conferencing sessions (that is, sessions involving three or more participants).</span></span>

### <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="ad392-178">Метрики для сеансов конференц-связи</span><span class="sxs-lookup"><span data-stu-id="ad392-178">Metrics for Conferencing Sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ad392-179">Имя</span><span class="sxs-lookup"><span data-stu-id="ad392-179">Name</span></span></th>
<th><span data-ttu-id="ad392-180">Поддержка сортировки</span><span class="sxs-lookup"><span data-stu-id="ad392-180">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="ad392-181">Описание</span><span class="sxs-lookup"><span data-stu-id="ad392-181">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ad392-182"><strong>Всего конференций</strong></span><span class="sxs-lookup"><span data-stu-id="ad392-182"><strong>Total conferences</strong></span></span></p></td>
<td><p><span data-ttu-id="ad392-183">Нет</span><span class="sxs-lookup"><span data-stu-id="ad392-183">No</span></span></p></td>
<td><p><span data-ttu-id="ad392-184">Общее количество проведенных конференций.</span><span class="sxs-lookup"><span data-stu-id="ad392-184">Total number of conferences conducted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad392-185"><strong>Общее количество сеансов конференц-связи</strong></span><span class="sxs-lookup"><span data-stu-id="ad392-185"><strong>Total conference sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="ad392-186">Нет</span><span class="sxs-lookup"><span data-stu-id="ad392-186">No</span></span></p></td>
<td><p><span data-ttu-id="ad392-187">Общее количество проведенных сеансов конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="ad392-187">Total number of conferencing sessions conducted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad392-188"><strong>Общее количество неудачных сеансов</strong></span><span class="sxs-lookup"><span data-stu-id="ad392-188"><strong>Overall session failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="ad392-189">Нет</span><span class="sxs-lookup"><span data-stu-id="ad392-189">No</span></span></p></td>
<td><p><span data-ttu-id="ad392-190">Процент неудачных сеансов конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="ad392-190">Percentage of the total conferencing sessions that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad392-191"><strong>Сеансы центра конференций</strong></span><span class="sxs-lookup"><span data-stu-id="ad392-191"><strong>Focus sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="ad392-192">Нет</span><span class="sxs-lookup"><span data-stu-id="ad392-192">No</span></span></p></td>
<td><p><span data-ttu-id="ad392-193">Общее количество неудачных сеансов конференц-связи с центром.</span><span class="sxs-lookup"><span data-stu-id="ad392-193">Total number of Focus-based conferencing sessions that failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad392-194"><strong>Неудачные сеансы с центром</strong></span><span class="sxs-lookup"><span data-stu-id="ad392-194"><strong>Focus failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="ad392-195">Нет</span><span class="sxs-lookup"><span data-stu-id="ad392-195">No</span></span></p></td>
<td><p><span data-ttu-id="ad392-196">Процент неудачных сеансов конференц-связи с центром.</span><span class="sxs-lookup"><span data-stu-id="ad392-196">Percentage of the Focus-based conferencing sessions that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad392-197"><strong>Сеансы MCU</strong></span><span class="sxs-lookup"><span data-stu-id="ad392-197"><strong>MCU sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="ad392-198">Нет</span><span class="sxs-lookup"><span data-stu-id="ad392-198">No</span></span></p></td>
<td><p><span data-ttu-id="ad392-199">Общее количество неудачных сеансов конференц-связи для конференций на основе сервера (ранее называвшегося узлом управления многосторонней связью или MCU).</span><span class="sxs-lookup"><span data-stu-id="ad392-199">Total number of conferencing server-based (formerly known as Multipoint Control Unit or MCU) conferences that failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad392-200"><strong>Неудачные сеансы с MCU</strong></span><span class="sxs-lookup"><span data-stu-id="ad392-200"><strong>MCU failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="ad392-201">Нет</span><span class="sxs-lookup"><span data-stu-id="ad392-201">No</span></span></p></td>
<td><p><span data-ttu-id="ad392-202">Процент неудачных сеансов конференц-связи для конференций на основе сервера (ранее называвшегося узлом управления многосторонней связью или MCU).</span><span class="sxs-lookup"><span data-stu-id="ad392-202">Percentage of the conferencing server-based (formerly known as Multipoint Control Unit or MCU) conferences that failed.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

