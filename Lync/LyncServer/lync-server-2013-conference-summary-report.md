---
title: 'Lync Server 2013: сводный отчет по конференциям'
description: 'Lync Server 2013: сводный отчет по конференциям.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conference Summary Report
ms:assetid: 62f54812-5700-45a3-8526-8f58b0f77fbc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558656(v=OCS.15)
ms:contentKeyID: 48184299
ms.date: 09/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2d9c0b8ad7280d2c7336282c14f46e6b5d6a1aec
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550715"
---
# <a name="conference-summary-report-in-lync-server-2013"></a><span data-ttu-id="a96d3-103">Сводный отчет по конференциям в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a96d3-103">Conference Summary Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a96d3-104">_**Последнее изменение темы:** 2014-09-03_</span><span class="sxs-lookup"><span data-stu-id="a96d3-104">_**Topic Last Modified:** 2014-09-03_</span></span>

<span data-ttu-id="a96d3-105">Сводный отчет о конференциях предоставляет обзорные сведения о сеансах веб-конференций.</span><span class="sxs-lookup"><span data-stu-id="a96d3-105">The Conference Summary Report provides an overall view of your online conferencing sessions.</span></span> <span data-ttu-id="a96d3-106">Как правило, Конференция состоит из более чем 2 пользователей и требует использования служб конференц-связи Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a96d3-106">A conference typically involves more than 2 users and requires the use of Microsoft Lync Server 2013 conferencing services.</span></span> <span data-ttu-id="a96d3-107">Для сравнения, в одноранговом сеансе обычно участвуют только два пользователя, и для него не требуются службы конференц-связи Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a96d3-107">By comparison, a peer-to-peer session typically involves just 2 users and does not require the use of Lync Server's conferencing services.</span></span> <span data-ttu-id="a96d3-108">Сведения об одноранговых действиях отображаются в [сводном отчете по одноранговым действиям в Lync Server 2013](lync-server-2013-peer-to-peer-activity-summary-report.md).</span><span class="sxs-lookup"><span data-stu-id="a96d3-108">Peer-to-peer activities are reported on the [Peer-to-Peer Activity Summary Report in Lync Server 2013](lync-server-2013-peer-to-peer-activity-summary-report.md).</span></span>

<span data-ttu-id="a96d3-109">Сводный отчет по конференциям содержит не только сведения о том, сколько конференций выполнялось в течение определенного периода времени (ежечасно, ежедневно, еженедельно, ежемесячно), но также показывает общее количество людей, которые потратили участие в конференциях, и общее количество уникальных организаторов конференций.</span><span class="sxs-lookup"><span data-stu-id="a96d3-109">The Conference Summary Report not only tells you how many conferences were held during a given time period (hourly, daily, weekly, monthly) but also tells you the total number of people who took part in those conferences, and the total number of unique conference organizers.</span></span>

<span data-ttu-id="a96d3-p102">Под "уникальным" организатором понимается пользователь, который запланировал по крайней мере одну конференцию. Например, если пользователь Алексей Иванов запланировал одну конференцию, он считается одним уникальным организатором. Если пользователь Виталий Максимов запланировал 148 конференций, он также считается одним уникальным организатором. Например, в таблице ниже показано 8 запланированных конференций, но только три уникальных организатора (Виталий Максимов, Алексей Иванов и Анна Васильева).</span><span class="sxs-lookup"><span data-stu-id="a96d3-p102">A "unique” organizer is anyone who schedules at least one conference. For example, if Pilar Ackerman schedules one conference she counts as one unique organizer. If Ken Myer schedules 148 conferences he, too counts as one unique organizer. For example, the table below shows 8 conferences scheduled, but just three unique organizers (Ken Myer, Pilar Ackerman, and David Ahs).</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a96d3-114">Организатор конференции</span><span class="sxs-lookup"><span data-stu-id="a96d3-114">Conference Organizer</span></span></th>
<th><span data-ttu-id="a96d3-115">Дата конференции</span><span class="sxs-lookup"><span data-stu-id="a96d3-115">Conference Date</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a96d3-116">Виталий Максимов</span><span class="sxs-lookup"><span data-stu-id="a96d3-116">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="a96d3-117">07.07.2012 10:00</span><span class="sxs-lookup"><span data-stu-id="a96d3-117">7/7/2012 10:00 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a96d3-118">Анна Васильева</span><span class="sxs-lookup"><span data-stu-id="a96d3-118">David Ahs</span></span></p></td>
<td><p><span data-ttu-id="a96d3-119">07.07.2012 10:00</span><span class="sxs-lookup"><span data-stu-id="a96d3-119">7/7/2012 10:00 AM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a96d3-120">Виталий Максимов</span><span class="sxs-lookup"><span data-stu-id="a96d3-120">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="a96d3-121">07.07.2012 11:00</span><span class="sxs-lookup"><span data-stu-id="a96d3-121">7/7/2012 11:00 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a96d3-122">Алексей Иванов</span><span class="sxs-lookup"><span data-stu-id="a96d3-122">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="a96d3-123">07.07.2012 11:00</span><span class="sxs-lookup"><span data-stu-id="a96d3-123">7/7/2012 11:00 AM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a96d3-124">Виталий Максимов</span><span class="sxs-lookup"><span data-stu-id="a96d3-124">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="a96d3-125">07.07.2012 13:00</span><span class="sxs-lookup"><span data-stu-id="a96d3-125">7/7/2012 1:00 PM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a96d3-126">Алексей Иванов</span><span class="sxs-lookup"><span data-stu-id="a96d3-126">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="a96d3-127">07.07.2012 14:00</span><span class="sxs-lookup"><span data-stu-id="a96d3-127">7/7/2012 2:00 PM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a96d3-128">Виталий Максимов</span><span class="sxs-lookup"><span data-stu-id="a96d3-128">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="a96d3-129">02.07.2012 10:00</span><span class="sxs-lookup"><span data-stu-id="a96d3-129">7/2/2012 10:00 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a96d3-130">Алексей Иванов</span><span class="sxs-lookup"><span data-stu-id="a96d3-130">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="a96d3-131">02.07.2012 10:00</span><span class="sxs-lookup"><span data-stu-id="a96d3-131">7/2/2012 10:00 AM</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a96d3-132">В сводном отчете о конференциях также указывается количество конференций, в которых использовалась голосовая и видеосвязь.</span><span class="sxs-lookup"><span data-stu-id="a96d3-132">The Conference Summary Report also indicates how many conferences included audio and/or video.</span></span>

<div>

## <a name="accessing-the-conference-summary-report"></a><span data-ttu-id="a96d3-133">Доступ к сводному отчету о конференциях</span><span class="sxs-lookup"><span data-stu-id="a96d3-133">Accessing the Conference Summary Report</span></span>

<span data-ttu-id="a96d3-p103">Доступ к сводному отчету о конференциях можно получить с домашней страницы "Отчеты наблюдения". Вы можете просмотреть подробные сведения в отчете о действиях конференций, щелкнув один из следующих разделов:</span><span class="sxs-lookup"><span data-stu-id="a96d3-p103">The Conference Summary Report is accessed from the Monitoring Reports home page. You can drill down to the Conference Activity report by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="a96d3-136">Общее количество конференций</span><span class="sxs-lookup"><span data-stu-id="a96d3-136">Total conferences</span></span>

  - <span data-ttu-id="a96d3-137">Общее количество участников</span><span class="sxs-lookup"><span data-stu-id="a96d3-137">Total participants</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-conference-summary-report"></a><span data-ttu-id="a96d3-138">Рекомендации по использованию сводного отчета о конференциях</span><span class="sxs-lookup"><span data-stu-id="a96d3-138">Making the Best Use of the Conference Summary Report</span></span>

<span data-ttu-id="a96d3-p104">Суммарные значения для большинства показателей, используемых в сводном отчете о конференциях, приведены в нижней части отчета. Прокрутите отчет вниз, чтобы просмотреть общее число конференций, проведенных в течение определенного периода, и общее число их участников. Однако среди суммарных значений нет общего числа уникальных организаторов. Объясняется это просто. Предположим, что вы просматриваете данные за месяц. В первый день было 34 уникальных организатора конференций, а во второй день — 27 организаторов. Означает ли это, что общее число уникальных организаторов в течение этих двух дней равно 61? Не обязательно. В действительности все 27 пользователей, организовавших конференции во второй день, могут входить в число 34 пользователей, организовавших конференции в первый день. Например, обратите внимание на то, что в этом простом отчете Виталий Максимов и Алексей Иванов планировали конференции как 07.07.2012, так и 02.07.2012:</span><span class="sxs-lookup"><span data-stu-id="a96d3-p104">Total values for most of the metrics used on the Conference Summary Report can be found at the bottom of the report; scroll down to see values such as the total number of conferences held during the specified time period, and the total number of people who participated in those conferences. One metric that is not totaled at the bottom of the report is Total unique conference organizers. Why not? Here’s one reason. Suppose you are looking at a month's worth of data. On day 1 you had 34 unique conference organizers; on day 2 you had 27 unique conference organizers. Does that mean you had 61 unique conference organizers for those two days? Not necessarily. After all, all 27 people who organized conferences on day 2 might be among the 34 people who organized conferences on day 1. For example, in this simple report, note that Ken Myer and Pilar Ackerman scheduled conferences both on 7/7/2012 and on 7/2/2012:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a96d3-149">Организатор конференции</span><span class="sxs-lookup"><span data-stu-id="a96d3-149">Conference Organizer</span></span></th>
<th><span data-ttu-id="a96d3-150">Дата конференции</span><span class="sxs-lookup"><span data-stu-id="a96d3-150">Conference Date</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a96d3-151">Виталий Максимов</span><span class="sxs-lookup"><span data-stu-id="a96d3-151">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="a96d3-152">07.07.2012 10:00</span><span class="sxs-lookup"><span data-stu-id="a96d3-152">7/7/2012 10:00 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a96d3-153">Анна Васильева</span><span class="sxs-lookup"><span data-stu-id="a96d3-153">David Ahs</span></span></p></td>
<td><p><span data-ttu-id="a96d3-154">07.07.2012 10:00</span><span class="sxs-lookup"><span data-stu-id="a96d3-154">7/7/2012 10:00 AM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a96d3-155">Виталий Максимов</span><span class="sxs-lookup"><span data-stu-id="a96d3-155">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="a96d3-156">07.07.2012 11:00</span><span class="sxs-lookup"><span data-stu-id="a96d3-156">7/7/2012 11:00 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a96d3-157">Алексей Иванов</span><span class="sxs-lookup"><span data-stu-id="a96d3-157">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="a96d3-158">07.07.2012 11:00</span><span class="sxs-lookup"><span data-stu-id="a96d3-158">7/7/2012 11:00 AM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a96d3-159">Виталий Максимов</span><span class="sxs-lookup"><span data-stu-id="a96d3-159">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="a96d3-160">07.07.2012 13:00</span><span class="sxs-lookup"><span data-stu-id="a96d3-160">7/7/2012 1:00 PM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a96d3-161">Алексей Иванов</span><span class="sxs-lookup"><span data-stu-id="a96d3-161">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="a96d3-162">07.07.2012 14:00</span><span class="sxs-lookup"><span data-stu-id="a96d3-162">7/7/2012 2:00 PM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a96d3-163">Виталий Максимов</span><span class="sxs-lookup"><span data-stu-id="a96d3-163">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="a96d3-164">02.07.2012 10:00</span><span class="sxs-lookup"><span data-stu-id="a96d3-164">7/2/2012 10:00 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a96d3-165">Алексей Иванов</span><span class="sxs-lookup"><span data-stu-id="a96d3-165">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="a96d3-166">02.07.2012 10:00</span><span class="sxs-lookup"><span data-stu-id="a96d3-166">7/2/2012 10:00 AM</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a96d3-167">Чтобы получить более точное представление об общем количестве уникальных организаторов конференций, измените временной интервал. Например, просмотрите данные по месяцам, а не по дням.</span><span class="sxs-lookup"><span data-stu-id="a96d3-167">To get a better idea of the total number of unique users who organized conferences, change your time interval; for example, look at the data by month instead of by day.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="a96d3-168">Фильтры</span><span class="sxs-lookup"><span data-stu-id="a96d3-168">Filters</span></span>

<span data-ttu-id="a96d3-p105">Фильтры позволяют получить более конкретные наборы возвращаемых данных. Например, сводный отчет о конференциях позволяет выбрать способ группировки данных. Конференции можно группировать по часу, дню, неделе или месяцу.</span><span class="sxs-lookup"><span data-stu-id="a96d3-p105">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Conference Summary Report enables you to choose how data should be grouped. In this case, conferences grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="a96d3-172">В следующей таблице перечислены фильтры, которые вы можете использовать со сводным отчетом о конференциях.</span><span class="sxs-lookup"><span data-stu-id="a96d3-172">The following table lists the filters that you can use with the Conference Summary Report.</span></span>

### <a name="conference-summary-report-filters"></a><span data-ttu-id="a96d3-173">Фильтры сводного отчета о конференциях</span><span class="sxs-lookup"><span data-stu-id="a96d3-173">Conference Summary Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a96d3-174">Имя</span><span class="sxs-lookup"><span data-stu-id="a96d3-174">Name</span></span></th>
<th><span data-ttu-id="a96d3-175">Описание</span><span class="sxs-lookup"><span data-stu-id="a96d3-175">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a96d3-176"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="a96d3-176"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="a96d3-p106">Дата и время начала диапазона. Чтобы просмотреть данные по часам, введите дату и время начала в следующем формате:</span><span class="sxs-lookup"><span data-stu-id="a96d3-p106">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="a96d3-179">7/7/2012 13:00.</span><span class="sxs-lookup"><span data-stu-id="a96d3-179">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="a96d3-p107">Если не указать время начала, автоматически будет выбрано время 00:00 указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</span><span class="sxs-lookup"><span data-stu-id="a96d3-p107">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="a96d3-182">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="a96d3-182">7/7/2012</span></span></p>
<p><span data-ttu-id="a96d3-183">Для просмотра по неделям или по месяцам введите дату, выпадающую на любой день недели или месяца, который вы хотите просмотреть (это необязательно должен быть первый день недели или месяца):</span><span class="sxs-lookup"><span data-stu-id="a96d3-183">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="a96d3-184">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="a96d3-184">7/3/2012</span></span></p>
<p><span data-ttu-id="a96d3-185">Неделя всегда начинается с воскресения и заканчивается субботой.</span><span class="sxs-lookup"><span data-stu-id="a96d3-185">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a96d3-186"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="a96d3-186"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="a96d3-p108">Дата и время окончания диапазона. Чтобы просмотреть данные по часам, введите дату и время окончания в следующем формате:</span><span class="sxs-lookup"><span data-stu-id="a96d3-p108">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="a96d3-189">7/7/2012 13:00.</span><span class="sxs-lookup"><span data-stu-id="a96d3-189">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="a96d3-p109">Если не указать время окончания, автоматически будет выбрано время 00:00 указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</span><span class="sxs-lookup"><span data-stu-id="a96d3-p109">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="a96d3-192">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="a96d3-192">7/7/2012</span></span></p>
<p><span data-ttu-id="a96d3-193">Для просмотра по неделям или по месяцам введите дату, выпадающую на любой день недели или месяца, который вы хотите просмотреть (это необязательно должен быть первый день недели или месяца):</span><span class="sxs-lookup"><span data-stu-id="a96d3-193">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="a96d3-194">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="a96d3-194">7/3/2012</span></span></p>
<p><span data-ttu-id="a96d3-195">Неделя всегда начинается с воскресения и заканчивается субботой.</span><span class="sxs-lookup"><span data-stu-id="a96d3-195">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a96d3-196"><strong>Interval</strong></span><span class="sxs-lookup"><span data-stu-id="a96d3-196"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="a96d3-p110">Временной интервал. Выберите один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="a96d3-p110">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="a96d3-199">Ежечасно (может отображаться до 25 часов)</span><span class="sxs-lookup"><span data-stu-id="a96d3-199">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="a96d3-200">Ежедневно (может отображаться до 31 дня)</span><span class="sxs-lookup"><span data-stu-id="a96d3-200">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="a96d3-201">Еженедельно (может отображаться до 12 недель)</span><span class="sxs-lookup"><span data-stu-id="a96d3-201">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="a96d3-202">Ежемесячно (может отображаться до 12 месяцев)</span><span class="sxs-lookup"><span data-stu-id="a96d3-202">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="a96d3-p111">Если число значений между начальной и конечной датами превышает максимальное допустимое для выбранного интервала, отображается максимальное возможное число значений (с начальной даты). Например, если вы выбрали интервал "Ежедневно" с начальной датой 07.07.2012 и конечной датой 28.02.2012, будут показаны данные для периода с 07.08.2012 24:00 до 07.09.2012 24:00 (то есть для 31 дня).</span><span class="sxs-lookup"><span data-stu-id="a96d3-p111">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) are displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="a96d3-205">Метрики</span><span class="sxs-lookup"><span data-stu-id="a96d3-205">Metrics</span></span>

<span data-ttu-id="a96d3-206">В следующей таблице показаны данные, которые приводятся в сводном отчете о конференциях.</span><span class="sxs-lookup"><span data-stu-id="a96d3-206">The following table the information provided by the Conferences Summary Report.</span></span>

### <a name="conference-summary-report-metrics"></a><span data-ttu-id="a96d3-207">Показатели сводного отчета о конференциях</span><span class="sxs-lookup"><span data-stu-id="a96d3-207">Conference Summary Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a96d3-208">Имя</span><span class="sxs-lookup"><span data-stu-id="a96d3-208">Name</span></span></th>
<th><span data-ttu-id="a96d3-209">Возможность сортировки по этому показателю</span><span class="sxs-lookup"><span data-stu-id="a96d3-209">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="a96d3-210">Описание</span><span class="sxs-lookup"><span data-stu-id="a96d3-210">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a96d3-211"><strong>Каждый час</strong></span><span class="sxs-lookup"><span data-stu-id="a96d3-211"><strong>Hourly</strong></span></span></p>
<p><span data-ttu-id="a96d3-212"><strong>Ежедневное</strong></span><span class="sxs-lookup"><span data-stu-id="a96d3-212"><strong>Daily</strong></span></span></p>
<p><span data-ttu-id="a96d3-213"><strong>Еженедельное</strong></span><span class="sxs-lookup"><span data-stu-id="a96d3-213"><strong>Weekly</strong></span></span></p>
<p><span data-ttu-id="a96d3-214"><strong>Monthly</strong></span><span class="sxs-lookup"><span data-stu-id="a96d3-214"><strong>Monthly</strong></span></span></p></td>
<td><p><span data-ttu-id="a96d3-215">Нет</span><span class="sxs-lookup"><span data-stu-id="a96d3-215">No</span></span></p></td>
<td><p><span data-ttu-id="a96d3-p112">Указывает на временной интервал, выбранной на панели фильтров. Вы можете щелкнуть временной интервал, чтобы просмотреть подробные сведения для него, если они доступны. Например, если используется интервал "Ежедневно", то при щелчке по дате 07.07.2012 вы увидите почасовые сведения о регистрации пользователей за эту дату.</span><span class="sxs-lookup"><span data-stu-id="a96d3-p112">Indicates the time interval that you selected on the filter toolbar. Where applicable, you can click a given time interval to view detailed information for that interval. For example, if you are using the Daily interval and you click 7/7/2012, you see an hourly breakdown of user registration activity for that date.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a96d3-219"><strong>Общее количество конференций</strong></span><span class="sxs-lookup"><span data-stu-id="a96d3-219"><strong>Total conferences</strong></span></span></p></td>
<td><p><span data-ttu-id="a96d3-220">Нет</span><span class="sxs-lookup"><span data-stu-id="a96d3-220">No</span></span></p></td>
<td><p><span data-ttu-id="a96d3-p113">Общее число проведенных конференций (вне зависимости от их типа). При щелчке по этому элементу выводится отчет о действиях конференций за выбранный период.</span><span class="sxs-lookup"><span data-stu-id="a96d3-p113">Total number of conferences (regardless of conference type) that were held. When you click this item, the report shows you the Conference Activity Report for the selected time period.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a96d3-223"><strong>Общее количество участников</strong></span><span class="sxs-lookup"><span data-stu-id="a96d3-223"><strong>Total participants</strong></span></span></p></td>
<td><p><span data-ttu-id="a96d3-224">Нет</span><span class="sxs-lookup"><span data-stu-id="a96d3-224">No</span></span></p></td>
<td><p><span data-ttu-id="a96d3-p114">Общее число пользователей, принявших участие в конференциях. При щелчке по этому элементу выводится отчет о действиях конференций за выбранный период.</span><span class="sxs-lookup"><span data-stu-id="a96d3-p114">Total number of people who took part in the conferences. When you click this item, the report shows you the Conference Activity Report for the selected time period.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a96d3-227"><strong>Среднее число участников конференции</strong></span><span class="sxs-lookup"><span data-stu-id="a96d3-227"><strong>Average participants per conference</strong></span></span></p></td>
<td><p><span data-ttu-id="a96d3-228">Нет</span><span class="sxs-lookup"><span data-stu-id="a96d3-228">No</span></span></p></td>
<td><p><span data-ttu-id="a96d3-p115">Среднее число пользователей, принявших участие в отдельной конференции. Определяется путем деления общего числа конференций на общее число участников.</span><span class="sxs-lookup"><span data-stu-id="a96d3-p115">Average number of people who took part in a given conference. Determined by dividing the total conferences by the total participants.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a96d3-231"><strong>Общее количество аудио- и видеоконференций</strong></span><span class="sxs-lookup"><span data-stu-id="a96d3-231"><strong>Total A/V conferences</strong></span></span></p></td>
<td><p><span data-ttu-id="a96d3-232">Нет</span><span class="sxs-lookup"><span data-stu-id="a96d3-232">No</span></span></p></td>
<td><p><span data-ttu-id="a96d3-233">Общее число конференций, в которых использовалась голосовая и видеосвязь.</span><span class="sxs-lookup"><span data-stu-id="a96d3-233">Total number of conferences that included audio or video.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a96d3-234"><strong>Общее количество минут аудио- и видеоконференций</strong></span><span class="sxs-lookup"><span data-stu-id="a96d3-234"><strong>Total A/V conference minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="a96d3-235">Нет</span><span class="sxs-lookup"><span data-stu-id="a96d3-235">No</span></span></p></td>
<td><p><span data-ttu-id="a96d3-236">Общее количество минут аудио- и видеоконференций.</span><span class="sxs-lookup"><span data-stu-id="a96d3-236">Total number of minutes devoted to audio/video conferencing.</span></span></p>
<p><span data-ttu-id="a96d3-237">В разделе Общее количество минут в Конференции A/V собраны все типы аудио-и видеоконференций, в том числе аудио-и видеоконференций. Конференции для обмена мгновенными сообщениями; Конференции для совместного использования приложений; Конференции с данными; и PSTN Конференции.</span><span class="sxs-lookup"><span data-stu-id="a96d3-237">The Total A/V conference minutes metric summarizes all the audio/visual conference types, including: A/V conferences; IM conferences; app sharing conferences; data conferences; and PSTN conferences.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a96d3-238"><strong>Total A/V conference participant minutes (Общее время в аудио- или видеоконференции в минутах)</strong></span><span class="sxs-lookup"><span data-stu-id="a96d3-238"><strong>Total A/V conference participant minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="a96d3-239">Нет</span><span class="sxs-lookup"><span data-stu-id="a96d3-239">No</span></span></p></td>
<td><p><span data-ttu-id="a96d3-p116">Общее количество минут участия пользователей в аудио- и видеоконференциях. Например, предположим, что один пользователь участвует в аудио- или видеоконференции 5 минут, а второй пользователь — 3 минуты. В сумме это дает 8 минут участия: 5 плюс 3.</span><span class="sxs-lookup"><span data-stu-id="a96d3-p116">Total number of participant minutes devoted to audio/video conferencing. For example, suppose one user spends 5 minutes in an audio/video conference and a second user spends 3 minutes in that same conference. That makes a total of 8 participant minutes: 5 minutes plus 3 minutes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a96d3-243"><strong>Среднее количество минут аудио- или видеоконференции</strong></span><span class="sxs-lookup"><span data-stu-id="a96d3-243"><strong>Average A/V conference minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="a96d3-244">Нет</span><span class="sxs-lookup"><span data-stu-id="a96d3-244">No</span></span></p></td>
<td><p><span data-ttu-id="a96d3-245">Средняя длительность аудио- или видеоконференции в минутах.</span><span class="sxs-lookup"><span data-stu-id="a96d3-245">Average number of minutes per audio/video conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a96d3-246"><strong>Общее количество организаторов конференций</strong></span><span class="sxs-lookup"><span data-stu-id="a96d3-246"><strong>Total number of unique organizers of conferences</strong></span></span></p></td>
<td><p><span data-ttu-id="a96d3-247">Нет</span><span class="sxs-lookup"><span data-stu-id="a96d3-247">No</span></span></p></td>
<td><p><span data-ttu-id="a96d3-p117">Общее число пользователей, организовавших по крайней мере одну конференцию. Пользователь, организовавший несколько конференции, считается одним уникальным организатором, так же как и организовавший одну конференцию.</span><span class="sxs-lookup"><span data-stu-id="a96d3-p117">Total number of users who organized at least one conference. Users who organized more than one conference are counted as one unique organizer, just like users who only organized a single conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a96d3-250"><strong>Общее количество сообщений в конференциях</strong></span><span class="sxs-lookup"><span data-stu-id="a96d3-250"><strong>Total conference messages</strong></span></span></p></td>
<td><p><span data-ttu-id="a96d3-251">Нет</span><span class="sxs-lookup"><span data-stu-id="a96d3-251">No</span></span></p></td>
<td><p><span data-ttu-id="a96d3-252">Общее число мгновенных сообщений, отправленных в рамках конференций.</span><span class="sxs-lookup"><span data-stu-id="a96d3-252">Total number of instant messages sent during the conferences.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

