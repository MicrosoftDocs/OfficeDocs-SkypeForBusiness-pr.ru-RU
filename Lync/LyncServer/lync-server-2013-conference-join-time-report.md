---
title: 'Lync Server 2013: отчет о времени присоединения к Конференции'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Conference Join Time Report
ms:assetid: e64dc89a-25e4-4cb8-bcb1-51712e69ba5a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205344(v=OCS.15)
ms:contentKeyID: 48185686
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fac854b9e296d744473593562f32430c6e21fc87
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841493"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conference-join-time-report-in-lync-server-2013"></a><span data-ttu-id="9833f-102">Отчет о времени присоединения к Конференции в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9833f-102">Conference Join Time Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9833f-103">_**Тема последнего изменения:** 2014-04-23_</span><span class="sxs-lookup"><span data-stu-id="9833f-103">_**Topic Last Modified:** 2014-04-23_</span></span>

<span data-ttu-id="9833f-p101">Сводный отчет о времени присоединения к конференции позволяет вам определить, сколько времени требуется пользователям для присоединения к конференции. В этом отчете указывается среднее время присоединения (в миллисекундах), а также приводятся сведения о том, сколько пользователей смогло присоединиться к конференции за 2 секунды или быстрее, скольким пользователям потребовалось для этого от 2 до 5 секунд и так далее.</span><span class="sxs-lookup"><span data-stu-id="9833f-p101">The Conference Join Time Summary enables you to determine how long it takes your users to join a conference. The report shows the average join time (in milliseconds), and also provides a breakdown that lets you know how many users were able to join a conference in 2 seconds or less, how many users required between 2 and 5 seconds to join the conference, and so on.</span></span>

<div>

## <a name="accessing-the-conference-join-time-report"></a><span data-ttu-id="9833f-106">Доступ к отчету о времени присоединения к конференции</span><span class="sxs-lookup"><span data-stu-id="9833f-106">Accessing the Conference Join Time Report</span></span>

<span data-ttu-id="9833f-107">Доступ к отчету о времени присоединения к конференции осуществляется с домашней страницы отчетов мониторинга.</span><span class="sxs-lookup"><span data-stu-id="9833f-107">The Conference Join Time Report is accessed from the Monitoring Reports home page.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="9833f-108">Фильтры</span><span class="sxs-lookup"><span data-stu-id="9833f-108">Filters</span></span>

<span data-ttu-id="9833f-p102">Фильтры позволяют вам возвратить уточненный набор данных или просматривать возвращенные данные различными способами. В следующей таблице перечислены фильтры, которые вы можете использовать в отчете о времени присоединения к конференции.</span><span class="sxs-lookup"><span data-stu-id="9833f-p102">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the Conference Join Time Report.</span></span>

### <a name="conference-join-time-report-filters"></a><span data-ttu-id="9833f-111">Фильтры отчета о времени присоединения к конференции</span><span class="sxs-lookup"><span data-stu-id="9833f-111">Conference Join Time Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9833f-112">Имя</span><span class="sxs-lookup"><span data-stu-id="9833f-112">Name</span></span></th>
<th><span data-ttu-id="9833f-113">Описание</span><span class="sxs-lookup"><span data-stu-id="9833f-113">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9833f-114"><strong>От</strong></span><span class="sxs-lookup"><span data-stu-id="9833f-114"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="9833f-p103">Начальные дата/время для временного диапазона. Чтобы просмотреть данные по часам, введите начальные дату и время следующим образом:</span><span class="sxs-lookup"><span data-stu-id="9833f-p103">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="9833f-117">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="9833f-117">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="9833f-p104">Если вы не вводите начальное время, отчет автоматически начинается с 12:00 AM указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</span><span class="sxs-lookup"><span data-stu-id="9833f-p104">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="9833f-120">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="9833f-120">7/7/2012</span></span></p>
<p><span data-ttu-id="9833f-121">Чтобы просмотреть данные за неделю или месяц, введите дату, выпадающую на любое время в рамках недели или месяца, которые вы хотите просмотреть (вам не требуется вводить первый день недели или месяца):</span><span class="sxs-lookup"><span data-stu-id="9833f-121">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="9833f-122">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="9833f-122">7/3/2012</span></span></p>
<p><span data-ttu-id="9833f-123">Недели всегда отсчитываются с воскресенья по субботу.</span><span class="sxs-lookup"><span data-stu-id="9833f-123">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9833f-124"><strong>До</strong></span><span class="sxs-lookup"><span data-stu-id="9833f-124"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="9833f-p105">Конечные дата/время для временного диапазона. Чтобы просмотреть данные по часам, введите конечные дату и время следующим образом:</span><span class="sxs-lookup"><span data-stu-id="9833f-p105">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="9833f-127">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="9833f-127">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="9833f-p106">Если вы не вводите конечное время, отчет автоматически заканчивается в 12:00 AM указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</span><span class="sxs-lookup"><span data-stu-id="9833f-p106">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="9833f-130">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="9833f-130">7/7/2012</span></span></p>
<p><span data-ttu-id="9833f-131">Чтобы просмотреть данные за неделю или месяц, введите дату, выпадающую на любое время в рамках недели или месяца, которые вы хотите просмотреть (вам не требуется вводить первый день недели или месяца):</span><span class="sxs-lookup"><span data-stu-id="9833f-131">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="9833f-132">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="9833f-132">7/3/2012</span></span></p>
<p><span data-ttu-id="9833f-133">Недели всегда отсчитываются с воскресенья по субботу.</span><span class="sxs-lookup"><span data-stu-id="9833f-133">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9833f-134"><strong>Интервал</strong></span><span class="sxs-lookup"><span data-stu-id="9833f-134"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="9833f-p107">Временной интервал. Выберите одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="9833f-p107">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="9833f-137">Ежечасно (можно отобразить не более 25 часов)</span><span class="sxs-lookup"><span data-stu-id="9833f-137">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="9833f-138">Ежедневно (можно отобразить не более 31 дня)</span><span class="sxs-lookup"><span data-stu-id="9833f-138">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="9833f-139">Еженедельно (можно отобразить не более 12 недель)</span><span class="sxs-lookup"><span data-stu-id="9833f-139">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="9833f-140">Ежемесячно (можно отобразить не более 12 месяцев)</span><span class="sxs-lookup"><span data-stu-id="9833f-140">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="9833f-141">Если количество значений между начальной и конечной датами превышает максимально допустимое для выбранного интервала, отображается максимальное возможное количество значений (от начальной даты и далее).</span><span class="sxs-lookup"><span data-stu-id="9833f-141">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed.</span></span> <span data-ttu-id="9833f-142">Например, если выбрать ежедневный интервал с датой начала 7/7/2012 и датой окончания 2/28/2012, данные будут выводиться для дней 8/7/2012 12:00 – 9/7/2012 12:00 AM (то есть, всего за 31 дня).</span><span class="sxs-lookup"><span data-stu-id="9833f-142">For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9833f-143"><strong>Пул</strong></span><span class="sxs-lookup"><span data-stu-id="9833f-143"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="9833f-p109">Полное доменное имя пула регистратора или пограничного сервера. Можно выбрать отдельный пул или нажать <strong>[Все]</strong>, чтобы просмотреть данные для всех пулов. Этот раскрывающийся список автоматически заполняется на основе записей в базе данных.</span><span class="sxs-lookup"><span data-stu-id="9833f-p109">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9833f-147"><strong>Сеансы конференц-связи</strong></span><span class="sxs-lookup"><span data-stu-id="9833f-147"><strong>Conference sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="9833f-p110">Тип сеанса. Допускаются следующие значения:</span><span class="sxs-lookup"><span data-stu-id="9833f-p110">Type of session. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="9833f-150">[All] (Все)</span><span class="sxs-lookup"><span data-stu-id="9833f-150">[All]</span></span></p></li>
<li><p><span data-ttu-id="9833f-151">Сеансы центра конференций (центр конференций определяет централизованную политику, служит диспетчером состояний для сетевых собраний и обеспечивает согласование всех аспектов голосовой конференции)</span><span class="sxs-lookup"><span data-stu-id="9833f-151">Focus sessions (the Focus is the central policy and state manager for online meetings and coordinates all aspects of A conference</span></span></p></li>
<li><p><span data-ttu-id="9833f-152">Общий доступ к приложениям</span><span class="sxs-lookup"><span data-stu-id="9833f-152">Application sharing</span></span></p></li>
<li><p><span data-ttu-id="9833f-153">A/V conferencing (Аудио- и видеоконференции)</span><span class="sxs-lookup"><span data-stu-id="9833f-153">A/V conferencing</span></span></p></li>
</ul>
<p><span data-ttu-id="9833f-p111">Если вы выбираете значение [All] (Все), в верхней части отчета отображается общее время присоединения к конференции. Обратите внимание на то, что приводятся итоговые значения только для конференций, запланированных с помощью Microsoft Exchange или Microsoft Outlook.</span><span class="sxs-lookup"><span data-stu-id="9833f-p111">If you select [All], the total conference join time will be displayed at the top of the report. Note that these totals are only for conferences which were scheduled by using Microsoft Exchange or Microsoft Outlook.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="9833f-156">Показатели</span><span class="sxs-lookup"><span data-stu-id="9833f-156">Metrics</span></span>

<span data-ttu-id="9833f-157">В следующей таблице перечислены сведения, представленные в отчете о времени присоединения к конференции.</span><span class="sxs-lookup"><span data-stu-id="9833f-157">The following table lists the information provided in the Conference Join Time Report.</span></span>

### <a name="conference-join-time-report-metrics"></a><span data-ttu-id="9833f-158">Метрики отчета о времени присоединения к конференции</span><span class="sxs-lookup"><span data-stu-id="9833f-158">Conference Join Time Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9833f-159">Имя</span><span class="sxs-lookup"><span data-stu-id="9833f-159">Name</span></span></th>
<th><span data-ttu-id="9833f-160">Поддержка сортировки</span><span class="sxs-lookup"><span data-stu-id="9833f-160">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="9833f-161">Описание</span><span class="sxs-lookup"><span data-stu-id="9833f-161">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9833f-162"><strong>Дата</strong></span><span class="sxs-lookup"><span data-stu-id="9833f-162"><strong>Date</strong></span></span></p>
<p><span data-ttu-id="9833f-163">Фактическое название этой метрики зависит от выбранного интервала.</span><span class="sxs-lookup"><span data-stu-id="9833f-163">The actual title for this metric will vary depending on the Interval that was selected.</span></span></p></td>
<td><p><span data-ttu-id="9833f-164">Нет</span><span class="sxs-lookup"><span data-stu-id="9833f-164">No</span></span></p></td>
<td><p><span data-ttu-id="9833f-165">Дата и время проведения конференции.</span><span class="sxs-lookup"><span data-stu-id="9833f-165">Date and time that the conference took place.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9833f-166"><strong>Всего сеансов</strong></span><span class="sxs-lookup"><span data-stu-id="9833f-166"><strong>Total sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="9833f-167">Нет</span><span class="sxs-lookup"><span data-stu-id="9833f-167">No</span></span></p></td>
<td><p><span data-ttu-id="9833f-168">Общее число сеансов, включая успешные и завершившиеся сбоем (как ожидаемые, так и непредвиденные сбои) и сеансы без категорий.</span><span class="sxs-lookup"><span data-stu-id="9833f-168">Total number of sessions, including successful sessions, failed sessions (both expected failures and unexpected failures), and uncategorized sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9833f-169"><strong>Среднее (мс)</strong></span><span class="sxs-lookup"><span data-stu-id="9833f-169"><strong>Average (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="9833f-170">Нет</span><span class="sxs-lookup"><span data-stu-id="9833f-170">No</span></span></p></td>
<td><p><span data-ttu-id="9833f-171">Среднее время (в миллисекундах), затрачиваемое участниками на присоединение к конференции.</span><span class="sxs-lookup"><span data-stu-id="9833f-171">Average amount of time (in milliseconds) that it took participants to join the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9833f-172"><strong>Сеансы &lt; 2 секунды, том</strong></span><span class="sxs-lookup"><span data-stu-id="9833f-172"><strong>Sessions &lt; 2 seconds, Volume</strong></span></span></p></td>
<td><p><span data-ttu-id="9833f-173">Нет</span><span class="sxs-lookup"><span data-stu-id="9833f-173">No</span></span></p></td>
<td><p><span data-ttu-id="9833f-174">Число участников, которые а присоединиться к конференции менее чем за 2 секунды.</span><span class="sxs-lookup"><span data-stu-id="9833f-174">Number of participants who were able to join the conference in less than 2 seconds.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9833f-175"><strong>Сеансы &lt; 2 секунды, проценты</strong></span><span class="sxs-lookup"><span data-stu-id="9833f-175"><strong>Sessions &lt; 2 seconds, Percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="9833f-176">Нет</span><span class="sxs-lookup"><span data-stu-id="9833f-176">No</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9833f-177"><strong>Сеансы от 2 до 5 с, объем</strong></span><span class="sxs-lookup"><span data-stu-id="9833f-177"><strong>Sessions 2-5 seconds, Volume</strong></span></span></p></td>
<td><p><span data-ttu-id="9833f-178">Нет</span><span class="sxs-lookup"><span data-stu-id="9833f-178">No</span></span></p></td>
<td><p><span data-ttu-id="9833f-179">Число участников, у которых присоединение к конференции заняло от 2 до 5 секунд.</span><span class="sxs-lookup"><span data-stu-id="9833f-179">Number of participants who took between 2 seconds and 5 seconds to join the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9833f-180"><strong>Сеансы от 2 до 5 с, доля</strong></span><span class="sxs-lookup"><span data-stu-id="9833f-180"><strong>Sessions 2-5 seconds, Percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="9833f-181">Нет</span><span class="sxs-lookup"><span data-stu-id="9833f-181">No</span></span></p></td>
<td><p><span data-ttu-id="9833f-182">Процент от общего числа участников, у которых присоединение к конференции заняло от 2 до 5 секунд.</span><span class="sxs-lookup"><span data-stu-id="9833f-182">Percentage of the total call participants who took between 2 seconds and 5 seconds to join the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9833f-183"><strong>Сеансы от 5 до 10 с, объем</strong></span><span class="sxs-lookup"><span data-stu-id="9833f-183"><strong>Sessions 5-10 seconds, Volume</strong></span></span></p></td>
<td><p><span data-ttu-id="9833f-184">Нет</span><span class="sxs-lookup"><span data-stu-id="9833f-184">No</span></span></p></td>
<td><p><span data-ttu-id="9833f-185">Число участников, у которых присоединение к конференции заняло от 5 до 10 секунд.</span><span class="sxs-lookup"><span data-stu-id="9833f-185">Number of participants who took between 5 seconds and 10 seconds to join the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9833f-186"><strong>Сеансы от 5 до 10 с, доля</strong></span><span class="sxs-lookup"><span data-stu-id="9833f-186"><strong>Sessions 5-10 seconds, Percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="9833f-187">Нет</span><span class="sxs-lookup"><span data-stu-id="9833f-187">No</span></span></p></td>
<td><p><span data-ttu-id="9833f-188">Процент от общего числа участников, у которых присоединение к конференции заняло от 5 до 10 секунд.</span><span class="sxs-lookup"><span data-stu-id="9833f-188">Percentage of the total call participants who took between 5 seconds and 10 seconds to join the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9833f-189"><strong>Сеансы &gt; на 10 секунд, том</strong></span><span class="sxs-lookup"><span data-stu-id="9833f-189"><strong>Sessions &gt; 10 seconds, Volume</strong></span></span></p></td>
<td><p><span data-ttu-id="9833f-190">Нет</span><span class="sxs-lookup"><span data-stu-id="9833f-190">No</span></span></p></td>
<td><p><span data-ttu-id="9833f-191">Число участников, у которых присоединение к конференции заняло более 10 секунд.</span><span class="sxs-lookup"><span data-stu-id="9833f-191">Number of participants who required more than 10 seconds to join the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9833f-192"><strong>Сеансы &gt; с 10 секундами, процент</strong></span><span class="sxs-lookup"><span data-stu-id="9833f-192"><strong>Sessions &gt; 10 seconds, Percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="9833f-193">Нет</span><span class="sxs-lookup"><span data-stu-id="9833f-193">No</span></span></p></td>
<td><p><span data-ttu-id="9833f-194">Процент от общего числа участников, у которых присоединение к конференции заняло более 10 секунд.</span><span class="sxs-lookup"><span data-stu-id="9833f-194">Percentage of the total call participants who required more than 10 seconds to join the conference.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

