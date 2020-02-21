---
title: 'Lync Server 2013: отчет о времени присоединения к Конференции'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conference Join Time Report
ms:assetid: e64dc89a-25e4-4cb8-bcb1-51712e69ba5a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205344(v=OCS.15)
ms:contentKeyID: 48185686
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 76388655fc8ed893e09b192ae24c7807b46f9f6c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42199382"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conference-join-time-report-in-lync-server-2013"></a><span data-ttu-id="a0c1d-102">Отчет о времени присоединения к Конференции в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a0c1d-102">Conference Join Time Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a0c1d-103">_**Последнее изменение темы:** 2014-04-23_</span><span class="sxs-lookup"><span data-stu-id="a0c1d-103">_**Topic Last Modified:** 2014-04-23_</span></span>

<span data-ttu-id="a0c1d-p101">Сводный отчет о времени присоединения к конференции позволяет вам определить, сколько времени требуется пользователям для присоединения к конференции. В этом отчете указывается среднее время присоединения (в миллисекундах), а также приводятся сведения о том, сколько пользователей смогло присоединиться к конференции за 2 секунды или быстрее, скольким пользователям потребовалось для этого от 2 до 5 секунд и так далее.</span><span class="sxs-lookup"><span data-stu-id="a0c1d-p101">The Conference Join Time Summary enables you to determine how long it takes your users to join a conference. The report shows the average join time (in milliseconds), and also provides a breakdown that lets you know how many users were able to join a conference in 2 seconds or less, how many users required between 2 and 5 seconds to join the conference, and so on.</span></span>

<div>

## <a name="accessing-the-conference-join-time-report"></a><span data-ttu-id="a0c1d-106">Доступ к отчету о времени присоединения к конференции</span><span class="sxs-lookup"><span data-stu-id="a0c1d-106">Accessing the Conference Join Time Report</span></span>

<span data-ttu-id="a0c1d-107">Доступ к отчету о времени присоединения к конференции осуществляется с домашней страницы отчетов мониторинга.</span><span class="sxs-lookup"><span data-stu-id="a0c1d-107">The Conference Join Time Report is accessed from the Monitoring Reports home page.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="a0c1d-108">Фильтры</span><span class="sxs-lookup"><span data-stu-id="a0c1d-108">Filters</span></span>

<span data-ttu-id="a0c1d-p102">Фильтры позволяют вам возвратить уточненный набор данных или просматривать возвращенные данные различными способами. В следующей таблице перечислены фильтры, которые вы можете использовать в отчете о времени присоединения к конференции.</span><span class="sxs-lookup"><span data-stu-id="a0c1d-p102">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the Conference Join Time Report.</span></span>

### <a name="conference-join-time-report-filters"></a><span data-ttu-id="a0c1d-111">Фильтры отчета о времени присоединения к конференции</span><span class="sxs-lookup"><span data-stu-id="a0c1d-111">Conference Join Time Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a0c1d-112">Имя</span><span class="sxs-lookup"><span data-stu-id="a0c1d-112">Name</span></span></th>
<th><span data-ttu-id="a0c1d-113">Описание</span><span class="sxs-lookup"><span data-stu-id="a0c1d-113">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a0c1d-114"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="a0c1d-114"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="a0c1d-p103">Дата и время начала диапазона. Чтобы просмотреть данные по часам, введите дату и время начала в следующем формате:</span><span class="sxs-lookup"><span data-stu-id="a0c1d-p103">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="a0c1d-117">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="a0c1d-117">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="a0c1d-p104">Если не указать время начала, автоматически будет выбрано время 00:00 указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</span><span class="sxs-lookup"><span data-stu-id="a0c1d-p104">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="a0c1d-120">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="a0c1d-120">7/7/2012</span></span></p>
<p><span data-ttu-id="a0c1d-121">Для просмотра по неделям или по месяцам введите дату, выпадающую на любой день недели или месяца, который вы хотите просмотреть (это необязательно должен быть первый день недели или месяца):</span><span class="sxs-lookup"><span data-stu-id="a0c1d-121">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="a0c1d-122">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="a0c1d-122">7/3/2012</span></span></p>
<p><span data-ttu-id="a0c1d-123">Недели всегда начинаются с Воскресенья и заканчиваются в Субботу.</span><span class="sxs-lookup"><span data-stu-id="a0c1d-123">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0c1d-124"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="a0c1d-124"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="a0c1d-p105">Дата и время окончания диапазона. Чтобы просмотреть данные по часам, введите дату и время окончания в следующем формате:</span><span class="sxs-lookup"><span data-stu-id="a0c1d-p105">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="a0c1d-127">7/7/2012 13:00.</span><span class="sxs-lookup"><span data-stu-id="a0c1d-127">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="a0c1d-p106">Если не указать время окончания, автоматически будет выбрано время 00:00 указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</span><span class="sxs-lookup"><span data-stu-id="a0c1d-p106">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="a0c1d-130">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="a0c1d-130">7/7/2012</span></span></p>
<p><span data-ttu-id="a0c1d-131">Для просмотра по неделям или по месяцам введите дату, выпадающую на любой день недели или месяца, который вы хотите просмотреть (это необязательно должен быть первый день недели или месяца):</span><span class="sxs-lookup"><span data-stu-id="a0c1d-131">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="a0c1d-132">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="a0c1d-132">7/3/2012</span></span></p>
<p><span data-ttu-id="a0c1d-133">Неделя всегда начинается с воскресения и заканчивается субботой.</span><span class="sxs-lookup"><span data-stu-id="a0c1d-133">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0c1d-134"><strong>Interval</strong></span><span class="sxs-lookup"><span data-stu-id="a0c1d-134"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="a0c1d-p107">Временной интервал. Выберите один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="a0c1d-p107">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="a0c1d-137">Ежечасно (может отображаться до 25 часов)</span><span class="sxs-lookup"><span data-stu-id="a0c1d-137">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="a0c1d-138">Ежедневно (может отображаться до 31 дня)</span><span class="sxs-lookup"><span data-stu-id="a0c1d-138">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="a0c1d-139">Еженедельно (может отображаться до 12 недель)</span><span class="sxs-lookup"><span data-stu-id="a0c1d-139">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="a0c1d-140">Ежемесячно (может отображаться до 12 месяцев)</span><span class="sxs-lookup"><span data-stu-id="a0c1d-140">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="a0c1d-p108">Если начальная и конечная даты превышают максимально допустимое количество значений для выбранного интервала, отображается только максимальное число значений (с отсчетом от начальной даты). Например, если вы выбрали интервал «Daily» с начальной датой 7/7/2012 и конечной датой 2/28/2012, отображаются данные по дням с 00:00 часов 8/7/2012  по 00:00 часов 9/7/2012 (то есть всего за 31 день).</span><span class="sxs-lookup"><span data-stu-id="a0c1d-p108">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0c1d-143"><strong>Ресурсов</strong></span><span class="sxs-lookup"><span data-stu-id="a0c1d-143"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="a0c1d-p109">Полное доменное имя пула регистратора или пограничного сервера. Можно выбрать отдельный пул или щелкнуть <strong>[Все]</strong>, чтобы просмотреть данные для всех пулов. Этот раскрывающийся список заполняется автоматически на основе записей в базе данных.</span><span class="sxs-lookup"><span data-stu-id="a0c1d-p109">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0c1d-147"><strong>Conference sessions</strong> (Сеансы конференций)</span><span class="sxs-lookup"><span data-stu-id="a0c1d-147"><strong>Conference sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="a0c1d-p110">Тип сеанса. Допускаются следующие значения:</span><span class="sxs-lookup"><span data-stu-id="a0c1d-p110">Type of session. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="a0c1d-150">Ко</span><span class="sxs-lookup"><span data-stu-id="a0c1d-150">[All]</span></span></p></li>
<li><p><span data-ttu-id="a0c1d-151">Сеансы фокусировки (фокус — это центральная политика и диспетчер состояний для собраний по сети и координирует все аспекты Конференции).</span><span class="sxs-lookup"><span data-stu-id="a0c1d-151">Focus sessions (the Focus is the central policy and state manager for online meetings and coordinates all aspects of A conference</span></span></p></li>
<li><p><span data-ttu-id="a0c1d-152">Application sharing (Общий доступ к приложениям)</span><span class="sxs-lookup"><span data-stu-id="a0c1d-152">Application sharing</span></span></p></li>
<li><p><span data-ttu-id="a0c1d-153">A/V conferencing (Аудио- и видеоконференции)</span><span class="sxs-lookup"><span data-stu-id="a0c1d-153">A/V conferencing</span></span></p></li>
</ul>
<p><span data-ttu-id="a0c1d-p111">Если вы выбираете значение [All] (Все), в верхней части отчета отображается общее время присоединения к конференции. Обратите внимание на то, что приводятся итоговые значения только для конференций, запланированных с помощью Microsoft Exchange или Microsoft Outlook.</span><span class="sxs-lookup"><span data-stu-id="a0c1d-p111">If you select [All], the total conference join time will be displayed at the top of the report. Note that these totals are only for conferences which were scheduled by using Microsoft Exchange or Microsoft Outlook.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="a0c1d-156">Метрик</span><span class="sxs-lookup"><span data-stu-id="a0c1d-156">Metrics</span></span>

<span data-ttu-id="a0c1d-157">В следующей таблице перечислены сведения, представленные в отчете о времени присоединения к конференции.</span><span class="sxs-lookup"><span data-stu-id="a0c1d-157">The following table lists the information provided in the Conference Join Time Report.</span></span>

### <a name="conference-join-time-report-metrics"></a><span data-ttu-id="a0c1d-158">Метрики отчета о времени присоединения к конференции</span><span class="sxs-lookup"><span data-stu-id="a0c1d-158">Conference Join Time Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a0c1d-159">Имя</span><span class="sxs-lookup"><span data-stu-id="a0c1d-159">Name</span></span></th>
<th><span data-ttu-id="a0c1d-160">Возможность сортировки по этому показателю</span><span class="sxs-lookup"><span data-stu-id="a0c1d-160">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="a0c1d-161">Описание</span><span class="sxs-lookup"><span data-stu-id="a0c1d-161">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a0c1d-162"><strong>Date</strong></span><span class="sxs-lookup"><span data-stu-id="a0c1d-162"><strong>Date</strong></span></span></p>
<p><span data-ttu-id="a0c1d-163">Фактическое название этой метрики зависит от выбранного интервала.</span><span class="sxs-lookup"><span data-stu-id="a0c1d-163">The actual title for this metric will vary depending on the Interval that was selected.</span></span></p></td>
<td><p><span data-ttu-id="a0c1d-164">Нет</span><span class="sxs-lookup"><span data-stu-id="a0c1d-164">No</span></span></p></td>
<td><p><span data-ttu-id="a0c1d-165">Дата и время проведения конференции.</span><span class="sxs-lookup"><span data-stu-id="a0c1d-165">Date and time that the conference took place.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0c1d-166"><strong> Всего сеансов </strong></span><span class="sxs-lookup"><span data-stu-id="a0c1d-166"><strong>Total sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="a0c1d-167">Нет</span><span class="sxs-lookup"><span data-stu-id="a0c1d-167">No</span></span></p></td>
<td><p><span data-ttu-id="a0c1d-168">Общее число сеансов, включая успешные и завершившиеся сбоем (как ожидаемые, так и непредвиденные сбои) и сеансы без категорий.</span><span class="sxs-lookup"><span data-stu-id="a0c1d-168">Total number of sessions, including successful sessions, failed sessions (both expected failures and unexpected failures), and uncategorized sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0c1d-169"><strong>Average (ms)</strong> (Среднее время, мс)</span><span class="sxs-lookup"><span data-stu-id="a0c1d-169"><strong>Average (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="a0c1d-170">Нет</span><span class="sxs-lookup"><span data-stu-id="a0c1d-170">No</span></span></p></td>
<td><p><span data-ttu-id="a0c1d-171">Среднее время (в миллисекундах), затрачиваемое участниками на присоединение к конференции.</span><span class="sxs-lookup"><span data-stu-id="a0c1d-171">Average amount of time (in milliseconds) that it took participants to join the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0c1d-172"><strong>Сеансы &lt; 2 с, объем</strong></span><span class="sxs-lookup"><span data-stu-id="a0c1d-172"><strong>Sessions &lt; 2 seconds, Volume</strong></span></span></p></td>
<td><p><span data-ttu-id="a0c1d-173">Нет</span><span class="sxs-lookup"><span data-stu-id="a0c1d-173">No</span></span></p></td>
<td><p><span data-ttu-id="a0c1d-174">Число участников, которые а присоединиться к конференции менее чем за 2 секунды.</span><span class="sxs-lookup"><span data-stu-id="a0c1d-174">Number of participants who were able to join the conference in less than 2 seconds.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0c1d-175"><strong>Сеансы &lt; 2 секунды, процент</strong></span><span class="sxs-lookup"><span data-stu-id="a0c1d-175"><strong>Sessions &lt; 2 seconds, Percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="a0c1d-176">Нет</span><span class="sxs-lookup"><span data-stu-id="a0c1d-176">No</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0c1d-177"><strong>Sessions 2-5 seconds, Volume</strong> (Сеансы 5\endash 10 секунд, объем)</span><span class="sxs-lookup"><span data-stu-id="a0c1d-177"><strong>Sessions 2-5 seconds, Volume</strong></span></span></p></td>
<td><p><span data-ttu-id="a0c1d-178">Нет</span><span class="sxs-lookup"><span data-stu-id="a0c1d-178">No</span></span></p></td>
<td><p><span data-ttu-id="a0c1d-179">Число участников, у которых присоединение к конференции заняло от 5 до 10 секунд.</span><span class="sxs-lookup"><span data-stu-id="a0c1d-179">Number of participants who took between 2 seconds and 5 seconds to join the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0c1d-180"><strong>Sessions 2-5 seconds, Percentage</strong> (Сеансы 5\endash 10 секунд, процент)</span><span class="sxs-lookup"><span data-stu-id="a0c1d-180"><strong>Sessions 2-5 seconds, Percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="a0c1d-181">Нет</span><span class="sxs-lookup"><span data-stu-id="a0c1d-181">No</span></span></p></td>
<td><p><span data-ttu-id="a0c1d-182">Процент от общего числа участников, у которых присоединение к конференции заняло от 2 до 5 секунд.</span><span class="sxs-lookup"><span data-stu-id="a0c1d-182">Percentage of the total call participants who took between 2 seconds and 5 seconds to join the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0c1d-183"><strong>Sessions 5-10 seconds, Volume</strong> (Сеансы 5\endash 10 секунд, объем)</span><span class="sxs-lookup"><span data-stu-id="a0c1d-183"><strong>Sessions 5-10 seconds, Volume</strong></span></span></p></td>
<td><p><span data-ttu-id="a0c1d-184">Нет</span><span class="sxs-lookup"><span data-stu-id="a0c1d-184">No</span></span></p></td>
<td><p><span data-ttu-id="a0c1d-185">Число участников, у которых присоединение к конференции заняло от 5 до 10 секунд.</span><span class="sxs-lookup"><span data-stu-id="a0c1d-185">Number of participants who took between 5 seconds and 10 seconds to join the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0c1d-186"><strong>Sessions 5-10 seconds, Percentage</strong> (Сеансы 5\endash 10 секунд, процент)</span><span class="sxs-lookup"><span data-stu-id="a0c1d-186"><strong>Sessions 5-10 seconds, Percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="a0c1d-187">Нет</span><span class="sxs-lookup"><span data-stu-id="a0c1d-187">No</span></span></p></td>
<td><p><span data-ttu-id="a0c1d-188">Процент от общего числа участников, у которых присоединение к конференции заняло от 5 до 10 секунд.</span><span class="sxs-lookup"><span data-stu-id="a0c1d-188">Percentage of the total call participants who took between 5 seconds and 10 seconds to join the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0c1d-189"><strong>Сеансы &gt; 10 с, объем</strong></span><span class="sxs-lookup"><span data-stu-id="a0c1d-189"><strong>Sessions &gt; 10 seconds, Volume</strong></span></span></p></td>
<td><p><span data-ttu-id="a0c1d-190">Нет</span><span class="sxs-lookup"><span data-stu-id="a0c1d-190">No</span></span></p></td>
<td><p><span data-ttu-id="a0c1d-191">Число участников, у которых присоединение к конференции заняло более 10 секунд.</span><span class="sxs-lookup"><span data-stu-id="a0c1d-191">Number of participants who required more than 10 seconds to join the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0c1d-192"><strong>Сеансы &gt; 10 секунд, процент</strong></span><span class="sxs-lookup"><span data-stu-id="a0c1d-192"><strong>Sessions &gt; 10 seconds, Percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="a0c1d-193">Нет</span><span class="sxs-lookup"><span data-stu-id="a0c1d-193">No</span></span></p></td>
<td><p><span data-ttu-id="a0c1d-194">Процент от общего числа участников, у которых присоединение к конференции заняло более 10 секунд.</span><span class="sxs-lookup"><span data-stu-id="a0c1d-194">Percentage of the total call participants who required more than 10 seconds to join the conference.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

