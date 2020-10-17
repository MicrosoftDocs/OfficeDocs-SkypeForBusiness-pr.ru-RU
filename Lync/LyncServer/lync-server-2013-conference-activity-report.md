---
title: 'Lync Server 2013: отчет об активности в конференциях'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conference Activity Report
ms:assetid: 22ddb509-af16-4fc8-9b98-6f58caa6f37e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558627(v=OCS.15)
ms:contentKeyID: 48183618
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fe99c67faa5cc9d0fadd2bdabd260c9d40091303
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526046"
---
# <a name="conference-activity-report-in-lync-server-2013"></a><span data-ttu-id="8dc5c-102">Отчет об активности конференций в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8dc5c-102">Conference Activity Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8dc5c-103">_**Последнее изменение темы:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="8dc5c-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="8dc5c-104">Отчет о конференциях позволяет легко найти ответ на такие вопросы, как сколько конференций проводится каждый день и когда они проводятся.</span><span class="sxs-lookup"><span data-stu-id="8dc5c-104">The Conference Activity Report makes it easy for you to answer questions like these: how many conferences are being held each day, and when are those conferences being held?</span></span> <span data-ttu-id="8dc5c-105">Такая информация полезна не только сама по себе, но и в целях устранения неполадок.</span><span class="sxs-lookup"><span data-stu-id="8dc5c-105">Information like this is useful not only in its own right, but also as a troubleshooting tool.</span></span> <span data-ttu-id="8dc5c-106">Например, предположим, что пользователи жалуются на то, что работа сети особенно замедляется в середине дня.</span><span class="sxs-lookup"><span data-stu-id="8dc5c-106">For example, suppose users are complaining that the network seems particularly slow in the middle of the day.</span></span> <span data-ttu-id="8dc5c-107">Краткий обзор отчетов о действиях в конференциях может предложить одну из возможных причин: в течение 10:00 AM и 2:00 на любой другой раз запланировано гораздо больше конференций.</span><span class="sxs-lookup"><span data-stu-id="8dc5c-107">A quick glance at the Conference Activity reports might suggest one possible reason: far more conferences are being scheduled between the hours of 10:00 AM and 2:00 PM then at any other time.</span></span>

<span data-ttu-id="8dc5c-108">Если замедление работы сети вызывает проблемы, вы можете порекомендовать пользователям перенести некоторые конференции на менее загруженное время суток.</span><span class="sxs-lookup"><span data-stu-id="8dc5c-108">If the slow network is causing problems, you can encourage users to reschedule some of their conferences during the less-heavily trafficked times of the day.</span></span>

<div>

## <a name="accessing-the-conference-activity-report"></a><span data-ttu-id="8dc5c-109">Доступ к отчету о конференциях</span><span class="sxs-lookup"><span data-stu-id="8dc5c-109">Accessing the Conference Activity Report</span></span>

<span data-ttu-id="8dc5c-110">Доступ к отчету о конференциях можно получить из [сводного отчета по конференциям в Lync Server 2013](lync-server-2013-conference-summary-report.md) , щелкнув один из следующих показателей:</span><span class="sxs-lookup"><span data-stu-id="8dc5c-110">The Conference Activity Report is accessed from the [Conference Summary Report in Lync Server 2013](lync-server-2013-conference-summary-report.md) by clicking either one of the following metrics:</span></span>

  - <span data-ttu-id="8dc5c-111">Общее количество конференций</span><span class="sxs-lookup"><span data-stu-id="8dc5c-111">Total conferences</span></span>

  - <span data-ttu-id="8dc5c-112">Общее количество участников</span><span class="sxs-lookup"><span data-stu-id="8dc5c-112">Total participants</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-conference-activity-report"></a><span data-ttu-id="8dc5c-113">Рекомендации по использованию отчета о конференциях</span><span class="sxs-lookup"><span data-stu-id="8dc5c-113">Making the Best Use of the Conference Activity Report</span></span>

<span data-ttu-id="8dc5c-p102">По умолчанию в отчете о конференциях приводится общее количество конференций за указанный период времени (например, за день или определенный час). Однако вы также можете просмотреть общее число участников за этот период или общее число минут участия в конференциях. Для этого нажмите кнопку "Показать или скрыть параметры", чтобы отобразить параметры фильтрации, и затем выберите в раскрывающемся списке "Отчет по" один из следующих пунктов:</span><span class="sxs-lookup"><span data-stu-id="8dc5c-p102">By default the Conference Activity Report shows you the total number of conferences for the specified time period (for example, the total number of conferences per day, or the total number of conferences per hour of the day). However, you can also choose to display the total number of participants for that time period or the total number of participant minutes. To do that, click the Show/Hide Parameters button to display the filtering options, and then select one of the following from the Report by dropdown list:</span></span>

  - <span data-ttu-id="8dc5c-117">Число участников</span><span class="sxs-lookup"><span data-stu-id="8dc5c-117">Participant count</span></span>

  - <span data-ttu-id="8dc5c-118">Минут участия</span><span class="sxs-lookup"><span data-stu-id="8dc5c-118">Participant minutes</span></span>

  - <span data-ttu-id="8dc5c-119">Число конференций</span><span class="sxs-lookup"><span data-stu-id="8dc5c-119">Conference count</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="8dc5c-120">Фильтры</span><span class="sxs-lookup"><span data-stu-id="8dc5c-120">Filters</span></span>

<span data-ttu-id="8dc5c-p103">Фильтры позволяют получить более конкретные наборы возвращаемых данных. В следующей таблице перечислены фильтры, которые можно использовать с отчетом о конференциях.</span><span class="sxs-lookup"><span data-stu-id="8dc5c-p103">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the Conference Activity Report.</span></span>

### <a name="conference-activity-report-filters"></a><span data-ttu-id="8dc5c-123">Фильтры отчета о конференциях</span><span class="sxs-lookup"><span data-stu-id="8dc5c-123">Conference Activity Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8dc5c-124">Имя</span><span class="sxs-lookup"><span data-stu-id="8dc5c-124">Name</span></span></th>
<th><span data-ttu-id="8dc5c-125">Описание</span><span class="sxs-lookup"><span data-stu-id="8dc5c-125">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8dc5c-126"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="8dc5c-126"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="8dc5c-p104">Дата и время начала диапазона. Чтобы просмотреть данные по часам, введите дату и время начала в следующем формате:</span><span class="sxs-lookup"><span data-stu-id="8dc5c-p104">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="8dc5c-129">7/7/2012 13:00.</span><span class="sxs-lookup"><span data-stu-id="8dc5c-129">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="8dc5c-p105">Если не указать время начала, автоматически будет выбрано время 00:00 указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</span><span class="sxs-lookup"><span data-stu-id="8dc5c-p105">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="8dc5c-132">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="8dc5c-132">7/7/2012</span></span></p>
<p><span data-ttu-id="8dc5c-133">Для просмотра по неделям или по месяцам введите дату, выпадающую на любой день недели или месяца, который вы хотите просмотреть (это необязательно должен быть первый день недели или месяца):</span><span class="sxs-lookup"><span data-stu-id="8dc5c-133">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="8dc5c-134">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="8dc5c-134">7/3/2012</span></span></p>
<p><span data-ttu-id="8dc5c-135">Неделя всегда начинается с воскресения и заканчивается субботой.</span><span class="sxs-lookup"><span data-stu-id="8dc5c-135">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8dc5c-136"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="8dc5c-136"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="8dc5c-p106">Дата и время окончания диапазона. Чтобы просмотреть данные по часам, введите дату и время окончания в следующем формате:</span><span class="sxs-lookup"><span data-stu-id="8dc5c-p106">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="8dc5c-139">7/7/2012 13:00.</span><span class="sxs-lookup"><span data-stu-id="8dc5c-139">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="8dc5c-p107">Если не указать время окончания, автоматически будет выбрано время 00:00 указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</span><span class="sxs-lookup"><span data-stu-id="8dc5c-p107">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="8dc5c-142">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="8dc5c-142">7/7/2012</span></span></p>
<p><span data-ttu-id="8dc5c-143">Для просмотра по неделям или по месяцам введите дату, выпадающую на любой день недели или месяца, который вы хотите просмотреть (это необязательно должен быть первый день недели или месяца):</span><span class="sxs-lookup"><span data-stu-id="8dc5c-143">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="8dc5c-144">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="8dc5c-144">7/3/2012</span></span></p>
<p><span data-ttu-id="8dc5c-145">Неделя всегда начинается с воскресения и заканчивается субботой.</span><span class="sxs-lookup"><span data-stu-id="8dc5c-145">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8dc5c-146"><strong>Interval</strong></span><span class="sxs-lookup"><span data-stu-id="8dc5c-146"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="8dc5c-p108">Временной интервал. Выберите один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="8dc5c-p108">Time interval. Select any of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="8dc5c-149">Ежечасно (может отображаться до 25 часов)</span><span class="sxs-lookup"><span data-stu-id="8dc5c-149">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="8dc5c-150">Ежедневно (может отображаться до 31 дня)</span><span class="sxs-lookup"><span data-stu-id="8dc5c-150">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="8dc5c-151">Еженедельно (может отображаться до 12 недель)</span><span class="sxs-lookup"><span data-stu-id="8dc5c-151">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="8dc5c-152">Ежемесячно (может отображаться до 12 месяцев)</span><span class="sxs-lookup"><span data-stu-id="8dc5c-152">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="8dc5c-p109">Если число значений между начальной и конечной датами превышает максимальное допустимое для выбранного интервала, отображается максимальное возможное число значений (с начальной даты). Например, если вы выбрали интервал "Ежедневно" с начальной датой 07.07.2012 и конечной датой 28.02.2012, будут показаны данные для периода с 07.08.2012 24:00 до 07.09.2012 24:00 (то есть для 31 дня).</span><span class="sxs-lookup"><span data-stu-id="8dc5c-p109">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8dc5c-155"><strong>Отчет по</strong></span><span class="sxs-lookup"><span data-stu-id="8dc5c-155"><strong>Report by</strong></span></span></p></td>
<td><p><span data-ttu-id="8dc5c-p110">Указывает значения, которые должны использоваться в отчете. Выберите один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="8dc5c-p110">Indicates the values to be used in the report. You can select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="8dc5c-158">Число участников</span><span class="sxs-lookup"><span data-stu-id="8dc5c-158">Participant Count</span></span></p></li>
<li><p><span data-ttu-id="8dc5c-159">Минут участия</span><span class="sxs-lookup"><span data-stu-id="8dc5c-159">Participant Minutes</span></span></p></li>
<li><p><span data-ttu-id="8dc5c-160">Число конференций</span><span class="sxs-lookup"><span data-stu-id="8dc5c-160">Conference Count</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferences-by-pool"></a><span data-ttu-id="8dc5c-161">Показатели для конференций по пулу</span><span class="sxs-lookup"><span data-stu-id="8dc5c-161">Metrics for Conferences by Pool</span></span>

<span data-ttu-id="8dc5c-162">В следующей таблице показаны сведения, содержащиеся в отчете о конференциях для каждого пула.</span><span class="sxs-lookup"><span data-stu-id="8dc5c-162">The following table lists the information in the Conference Activity Report for each pool.</span></span>

### <a name="metrics-for-conferences-by-pool"></a><span data-ttu-id="8dc5c-163">Показатели для конференций по пулу</span><span class="sxs-lookup"><span data-stu-id="8dc5c-163">Metrics for Conferences by Pool</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8dc5c-164">Имя</span><span class="sxs-lookup"><span data-stu-id="8dc5c-164">Name</span></span></th>
<th><span data-ttu-id="8dc5c-165">Возможность сортировки по этому показателю</span><span class="sxs-lookup"><span data-stu-id="8dc5c-165">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="8dc5c-166">Описание</span><span class="sxs-lookup"><span data-stu-id="8dc5c-166">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8dc5c-167"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="8dc5c-167"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="8dc5c-168">Нет</span><span class="sxs-lookup"><span data-stu-id="8dc5c-168">No</span></span></p></td>
<td><p><span data-ttu-id="8dc5c-169">Имя пула Регистраторов или пограничного сервера, используемого в рамках конференции.</span><span class="sxs-lookup"><span data-stu-id="8dc5c-169">Name of the Registrar pool or Edge Server used in the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8dc5c-170"><strong>Дата/время</strong></span><span class="sxs-lookup"><span data-stu-id="8dc5c-170"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="8dc5c-171">Нет</span><span class="sxs-lookup"><span data-stu-id="8dc5c-171">No</span></span></p></td>
<td><p><span data-ttu-id="8dc5c-172">Дата и время проведения конференции.</span><span class="sxs-lookup"><span data-stu-id="8dc5c-172">Date and time when the conference was held.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8dc5c-173"><strong>Total</strong></span><span class="sxs-lookup"><span data-stu-id="8dc5c-173"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="8dc5c-174">Нет</span><span class="sxs-lookup"><span data-stu-id="8dc5c-174">No</span></span></p></td>
<td><p><span data-ttu-id="8dc5c-175">Общее число участников, общее число минут участия в конференциях или общее число конференций.</span><span class="sxs-lookup"><span data-stu-id="8dc5c-175">Total participant count, total participant minutes, or total conference count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferences-by-server-type"></a><span data-ttu-id="8dc5c-176">Показатели для конференций по типу сервера</span><span class="sxs-lookup"><span data-stu-id="8dc5c-176">Metrics for Conferences by Server Type</span></span>

<span data-ttu-id="8dc5c-177">В следующей таблице показаны сведения, содержащиеся в отчете о конференциях для каждого типа сервера.</span><span class="sxs-lookup"><span data-stu-id="8dc5c-177">The following table lists the information in the Conference Activity Report for each type of server.</span></span>

### <a name="metrics-for-conferences-by-server-type"></a><span data-ttu-id="8dc5c-178">Показатели для конференций по типу сервера</span><span class="sxs-lookup"><span data-stu-id="8dc5c-178">Metrics for Conferences by Server Type</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8dc5c-179">Имя</span><span class="sxs-lookup"><span data-stu-id="8dc5c-179">Name</span></span></th>
<th><span data-ttu-id="8dc5c-180">Возможность сортировки по этому показателю</span><span class="sxs-lookup"><span data-stu-id="8dc5c-180">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="8dc5c-181">Описание</span><span class="sxs-lookup"><span data-stu-id="8dc5c-181">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8dc5c-182"><strong>Тип сервера конференций</strong></span><span class="sxs-lookup"><span data-stu-id="8dc5c-182"><strong>Conferencing server type</strong></span></span></p></td>
<td><p><span data-ttu-id="8dc5c-183">Нет</span><span class="sxs-lookup"><span data-stu-id="8dc5c-183">No</span></span></p></td>
<td><p><span data-ttu-id="8dc5c-184">Тип сервера, используемого для конференции. Обычно имеет одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="8dc5c-184">Type of server used in the conference, typically one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="8dc5c-185">Сервер веб-конференций</span><span class="sxs-lookup"><span data-stu-id="8dc5c-185">Web Conferencing Server</span></span></p></li>
<li><p><span data-ttu-id="8dc5c-186">Сервер конференций с обменом мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="8dc5c-186">IM Conferencing Server</span></span></p></li>
<li><p><span data-ttu-id="8dc5c-187">Сервер конференций с телефонной связью</span><span class="sxs-lookup"><span data-stu-id="8dc5c-187">Telephony Conferencing Server</span></span></p></li>
<li><p><span data-ttu-id="8dc5c-188">Сервер аудио- и видеоконференций</span><span class="sxs-lookup"><span data-stu-id="8dc5c-188">AV Conferencing Server</span></span></p></li>
<li><p><span data-ttu-id="8dc5c-189">Совместное использование приложений</span><span class="sxs-lookup"><span data-stu-id="8dc5c-189">Application Sharing</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8dc5c-190"><strong>Дата/время</strong></span><span class="sxs-lookup"><span data-stu-id="8dc5c-190"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="8dc5c-191">Нет</span><span class="sxs-lookup"><span data-stu-id="8dc5c-191">No</span></span></p></td>
<td><p><span data-ttu-id="8dc5c-192">Дата и время проведения конференции.</span><span class="sxs-lookup"><span data-stu-id="8dc5c-192">Date and time when the conference was held.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8dc5c-193"><strong>Total</strong></span><span class="sxs-lookup"><span data-stu-id="8dc5c-193"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="8dc5c-194">Нет</span><span class="sxs-lookup"><span data-stu-id="8dc5c-194">No</span></span></p></td>
<td><p><span data-ttu-id="8dc5c-195">Общее число участников, общее число минут участия в конференциях или общее число конференций.</span><span class="sxs-lookup"><span data-stu-id="8dc5c-195">Total participant count, total participant minutes, or total conference count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

