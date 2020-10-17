---
title: 'Lync Server 2013: сводный отчет по конференциям'
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
ms.openlocfilehash: d4390c2f3aa18820668415543496dfdcfd5aa79e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502356"
---
# <a name="conference-summary-report-in-lync-server-2013"></a><span data-ttu-id="01ea4-102">Сводный отчет по конференциям в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="01ea4-102">Conference Summary Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="01ea4-103">_**Последнее изменение темы:** 2014-09-03_</span><span class="sxs-lookup"><span data-stu-id="01ea4-103">_**Topic Last Modified:** 2014-09-03_</span></span>

<span data-ttu-id="01ea4-104">Сводный отчет о конференциях предоставляет обзорные сведения о сеансах веб-конференций.</span><span class="sxs-lookup"><span data-stu-id="01ea4-104">The Conference Summary Report provides an overall view of your online conferencing sessions.</span></span> <span data-ttu-id="01ea4-105">Как правило, Конференция состоит из более чем 2 пользователей и требует использования служб конференц-связи Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="01ea4-105">A conference typically involves more than 2 users and requires the use of Microsoft Lync Server 2013 conferencing services.</span></span> <span data-ttu-id="01ea4-106">Для сравнения, в одноранговом сеансе обычно участвуют только два пользователя, и для него не требуются службы конференц-связи Lync Server.</span><span class="sxs-lookup"><span data-stu-id="01ea4-106">By comparison, a peer-to-peer session typically involves just 2 users and does not require the use of Lync Server's conferencing services.</span></span> <span data-ttu-id="01ea4-107">Сведения об одноранговых действиях отображаются в [сводном отчете по одноранговым действиям в Lync Server 2013](lync-server-2013-peer-to-peer-activity-summary-report.md).</span><span class="sxs-lookup"><span data-stu-id="01ea4-107">Peer-to-peer activities are reported on the [Peer-to-Peer Activity Summary Report in Lync Server 2013](lync-server-2013-peer-to-peer-activity-summary-report.md).</span></span>

<span data-ttu-id="01ea4-108">Сводный отчет по конференциям содержит не только сведения о том, сколько конференций выполнялось в течение определенного периода времени (ежечасно, ежедневно, еженедельно, ежемесячно), но также показывает общее количество людей, которые потратили участие в конференциях, и общее количество уникальных организаторов конференций.</span><span class="sxs-lookup"><span data-stu-id="01ea4-108">The Conference Summary Report not only tells you how many conferences were held during a given time period (hourly, daily, weekly, monthly) but also tells you the total number of people who took part in those conferences, and the total number of unique conference organizers.</span></span>

<span data-ttu-id="01ea4-p102">Под "уникальным" организатором понимается пользователь, который запланировал по крайней мере одну конференцию. Например, если пользователь Алексей Иванов запланировал одну конференцию, он считается одним уникальным организатором. Если пользователь Виталий Максимов запланировал 148 конференций, он также считается одним уникальным организатором. Например, в таблице ниже показано 8 запланированных конференций, но только три уникальных организатора (Виталий Максимов, Алексей Иванов и Анна Васильева).</span><span class="sxs-lookup"><span data-stu-id="01ea4-p102">A "unique” organizer is anyone who schedules at least one conference. For example, if Pilar Ackerman schedules one conference she counts as one unique organizer. If Ken Myer schedules 148 conferences he, too counts as one unique organizer. For example, the table below shows 8 conferences scheduled, but just three unique organizers (Ken Myer, Pilar Ackerman, and David Ahs).</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="01ea4-113">Организатор конференции</span><span class="sxs-lookup"><span data-stu-id="01ea4-113">Conference Organizer</span></span></th>
<th><span data-ttu-id="01ea4-114">Дата конференции</span><span class="sxs-lookup"><span data-stu-id="01ea4-114">Conference Date</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="01ea4-115">Виталий Максимов</span><span class="sxs-lookup"><span data-stu-id="01ea4-115">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="01ea4-116">07.07.2012 10:00</span><span class="sxs-lookup"><span data-stu-id="01ea4-116">7/7/2012 10:00 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="01ea4-117">Анна Васильева</span><span class="sxs-lookup"><span data-stu-id="01ea4-117">David Ahs</span></span></p></td>
<td><p><span data-ttu-id="01ea4-118">07.07.2012 10:00</span><span class="sxs-lookup"><span data-stu-id="01ea4-118">7/7/2012 10:00 AM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="01ea4-119">Виталий Максимов</span><span class="sxs-lookup"><span data-stu-id="01ea4-119">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="01ea4-120">07.07.2012 11:00</span><span class="sxs-lookup"><span data-stu-id="01ea4-120">7/7/2012 11:00 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="01ea4-121">Алексей Иванов</span><span class="sxs-lookup"><span data-stu-id="01ea4-121">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="01ea4-122">07.07.2012 11:00</span><span class="sxs-lookup"><span data-stu-id="01ea4-122">7/7/2012 11:00 AM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="01ea4-123">Виталий Максимов</span><span class="sxs-lookup"><span data-stu-id="01ea4-123">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="01ea4-124">07.07.2012 13:00</span><span class="sxs-lookup"><span data-stu-id="01ea4-124">7/7/2012 1:00 PM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="01ea4-125">Алексей Иванов</span><span class="sxs-lookup"><span data-stu-id="01ea4-125">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="01ea4-126">07.07.2012 14:00</span><span class="sxs-lookup"><span data-stu-id="01ea4-126">7/7/2012 2:00 PM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="01ea4-127">Виталий Максимов</span><span class="sxs-lookup"><span data-stu-id="01ea4-127">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="01ea4-128">02.07.2012 10:00</span><span class="sxs-lookup"><span data-stu-id="01ea4-128">7/2/2012 10:00 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="01ea4-129">Алексей Иванов</span><span class="sxs-lookup"><span data-stu-id="01ea4-129">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="01ea4-130">02.07.2012 10:00</span><span class="sxs-lookup"><span data-stu-id="01ea4-130">7/2/2012 10:00 AM</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="01ea4-131">В сводном отчете о конференциях также указывается количество конференций, в которых использовалась голосовая и видеосвязь.</span><span class="sxs-lookup"><span data-stu-id="01ea4-131">The Conference Summary Report also indicates how many conferences included audio and/or video.</span></span>

<div>

## <a name="accessing-the-conference-summary-report"></a><span data-ttu-id="01ea4-132">Доступ к сводному отчету о конференциях</span><span class="sxs-lookup"><span data-stu-id="01ea4-132">Accessing the Conference Summary Report</span></span>

<span data-ttu-id="01ea4-p103">Доступ к сводному отчету о конференциях можно получить с домашней страницы "Отчеты наблюдения". Вы можете просмотреть подробные сведения в отчете о действиях конференций, щелкнув один из следующих разделов:</span><span class="sxs-lookup"><span data-stu-id="01ea4-p103">The Conference Summary Report is accessed from the Monitoring Reports home page. You can drill down to the Conference Activity report by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="01ea4-135">Общее количество конференций</span><span class="sxs-lookup"><span data-stu-id="01ea4-135">Total conferences</span></span>

  - <span data-ttu-id="01ea4-136">Общее количество участников</span><span class="sxs-lookup"><span data-stu-id="01ea4-136">Total participants</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-conference-summary-report"></a><span data-ttu-id="01ea4-137">Рекомендации по использованию сводного отчета о конференциях</span><span class="sxs-lookup"><span data-stu-id="01ea4-137">Making the Best Use of the Conference Summary Report</span></span>

<span data-ttu-id="01ea4-p104">Суммарные значения для большинства показателей, используемых в сводном отчете о конференциях, приведены в нижней части отчета. Прокрутите отчет вниз, чтобы просмотреть общее число конференций, проведенных в течение определенного периода, и общее число их участников. Однако среди суммарных значений нет общего числа уникальных организаторов. Объясняется это просто. Предположим, что вы просматриваете данные за месяц. В первый день было 34 уникальных организатора конференций, а во второй день — 27 организаторов. Означает ли это, что общее число уникальных организаторов в течение этих двух дней равно 61? Не обязательно. В действительности все 27 пользователей, организовавших конференции во второй день, могут входить в число 34 пользователей, организовавших конференции в первый день. Например, обратите внимание на то, что в этом простом отчете Виталий Максимов и Алексей Иванов планировали конференции как 07.07.2012, так и 02.07.2012:</span><span class="sxs-lookup"><span data-stu-id="01ea4-p104">Total values for most of the metrics used on the Conference Summary Report can be found at the bottom of the report; scroll down to see values such as the total number of conferences held during the specified time period, and the total number of people who participated in those conferences. One metric that is not totaled at the bottom of the report is Total unique conference organizers. Why not? Here’s one reason. Suppose you are looking at a month's worth of data. On day 1 you had 34 unique conference organizers; on day 2 you had 27 unique conference organizers. Does that mean you had 61 unique conference organizers for those two days? Not necessarily. After all, all 27 people who organized conferences on day 2 might be among the 34 people who organized conferences on day 1. For example, in this simple report, note that Ken Myer and Pilar Ackerman scheduled conferences both on 7/7/2012 and on 7/2/2012:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="01ea4-148">Организатор конференции</span><span class="sxs-lookup"><span data-stu-id="01ea4-148">Conference Organizer</span></span></th>
<th><span data-ttu-id="01ea4-149">Дата конференции</span><span class="sxs-lookup"><span data-stu-id="01ea4-149">Conference Date</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="01ea4-150">Виталий Максимов</span><span class="sxs-lookup"><span data-stu-id="01ea4-150">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="01ea4-151">07.07.2012 10:00</span><span class="sxs-lookup"><span data-stu-id="01ea4-151">7/7/2012 10:00 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="01ea4-152">Анна Васильева</span><span class="sxs-lookup"><span data-stu-id="01ea4-152">David Ahs</span></span></p></td>
<td><p><span data-ttu-id="01ea4-153">07.07.2012 10:00</span><span class="sxs-lookup"><span data-stu-id="01ea4-153">7/7/2012 10:00 AM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="01ea4-154">Виталий Максимов</span><span class="sxs-lookup"><span data-stu-id="01ea4-154">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="01ea4-155">07.07.2012 11:00</span><span class="sxs-lookup"><span data-stu-id="01ea4-155">7/7/2012 11:00 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="01ea4-156">Алексей Иванов</span><span class="sxs-lookup"><span data-stu-id="01ea4-156">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="01ea4-157">07.07.2012 11:00</span><span class="sxs-lookup"><span data-stu-id="01ea4-157">7/7/2012 11:00 AM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="01ea4-158">Виталий Максимов</span><span class="sxs-lookup"><span data-stu-id="01ea4-158">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="01ea4-159">07.07.2012 13:00</span><span class="sxs-lookup"><span data-stu-id="01ea4-159">7/7/2012 1:00 PM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="01ea4-160">Алексей Иванов</span><span class="sxs-lookup"><span data-stu-id="01ea4-160">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="01ea4-161">07.07.2012 14:00</span><span class="sxs-lookup"><span data-stu-id="01ea4-161">7/7/2012 2:00 PM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="01ea4-162">Виталий Максимов</span><span class="sxs-lookup"><span data-stu-id="01ea4-162">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="01ea4-163">02.07.2012 10:00</span><span class="sxs-lookup"><span data-stu-id="01ea4-163">7/2/2012 10:00 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="01ea4-164">Алексей Иванов</span><span class="sxs-lookup"><span data-stu-id="01ea4-164">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="01ea4-165">02.07.2012 10:00</span><span class="sxs-lookup"><span data-stu-id="01ea4-165">7/2/2012 10:00 AM</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="01ea4-166">Чтобы получить более точное представление об общем количестве уникальных организаторов конференций, измените временной интервал. Например, просмотрите данные по месяцам, а не по дням.</span><span class="sxs-lookup"><span data-stu-id="01ea4-166">To get a better idea of the total number of unique users who organized conferences, change your time interval; for example, look at the data by month instead of by day.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="01ea4-167">Фильтры</span><span class="sxs-lookup"><span data-stu-id="01ea4-167">Filters</span></span>

<span data-ttu-id="01ea4-p105">Фильтры позволяют получить более конкретные наборы возвращаемых данных. Например, сводный отчет о конференциях позволяет выбрать способ группировки данных. Конференции можно группировать по часу, дню, неделе или месяцу.</span><span class="sxs-lookup"><span data-stu-id="01ea4-p105">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Conference Summary Report enables you to choose how data should be grouped. In this case, conferences grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="01ea4-171">В следующей таблице перечислены фильтры, которые вы можете использовать со сводным отчетом о конференциях.</span><span class="sxs-lookup"><span data-stu-id="01ea4-171">The following table lists the filters that you can use with the Conference Summary Report.</span></span>

### <a name="conference-summary-report-filters"></a><span data-ttu-id="01ea4-172">Фильтры сводного отчета о конференциях</span><span class="sxs-lookup"><span data-stu-id="01ea4-172">Conference Summary Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="01ea4-173">Имя</span><span class="sxs-lookup"><span data-stu-id="01ea4-173">Name</span></span></th>
<th><span data-ttu-id="01ea4-174">Описание</span><span class="sxs-lookup"><span data-stu-id="01ea4-174">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="01ea4-175"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="01ea4-175"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="01ea4-p106">Дата и время начала диапазона. Чтобы просмотреть данные по часам, введите дату и время начала в следующем формате:</span><span class="sxs-lookup"><span data-stu-id="01ea4-p106">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="01ea4-178">7/7/2012 13:00.</span><span class="sxs-lookup"><span data-stu-id="01ea4-178">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="01ea4-p107">Если не указать время начала, автоматически будет выбрано время 00:00 указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</span><span class="sxs-lookup"><span data-stu-id="01ea4-p107">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="01ea4-181">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="01ea4-181">7/7/2012</span></span></p>
<p><span data-ttu-id="01ea4-182">Для просмотра по неделям или по месяцам введите дату, выпадающую на любой день недели или месяца, который вы хотите просмотреть (это необязательно должен быть первый день недели или месяца):</span><span class="sxs-lookup"><span data-stu-id="01ea4-182">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="01ea4-183">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="01ea4-183">7/3/2012</span></span></p>
<p><span data-ttu-id="01ea4-184">Неделя всегда начинается с воскресения и заканчивается субботой.</span><span class="sxs-lookup"><span data-stu-id="01ea4-184">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="01ea4-185"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="01ea4-185"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="01ea4-p108">Дата и время окончания диапазона. Чтобы просмотреть данные по часам, введите дату и время окончания в следующем формате:</span><span class="sxs-lookup"><span data-stu-id="01ea4-p108">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="01ea4-188">7/7/2012 13:00.</span><span class="sxs-lookup"><span data-stu-id="01ea4-188">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="01ea4-p109">Если не указать время окончания, автоматически будет выбрано время 00:00 указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</span><span class="sxs-lookup"><span data-stu-id="01ea4-p109">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="01ea4-191">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="01ea4-191">7/7/2012</span></span></p>
<p><span data-ttu-id="01ea4-192">Для просмотра по неделям или по месяцам введите дату, выпадающую на любой день недели или месяца, который вы хотите просмотреть (это необязательно должен быть первый день недели или месяца):</span><span class="sxs-lookup"><span data-stu-id="01ea4-192">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="01ea4-193">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="01ea4-193">7/3/2012</span></span></p>
<p><span data-ttu-id="01ea4-194">Неделя всегда начинается с воскресения и заканчивается субботой.</span><span class="sxs-lookup"><span data-stu-id="01ea4-194">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="01ea4-195"><strong>Interval</strong></span><span class="sxs-lookup"><span data-stu-id="01ea4-195"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="01ea4-p110">Временной интервал. Выберите один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="01ea4-p110">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="01ea4-198">Ежечасно (может отображаться до 25 часов)</span><span class="sxs-lookup"><span data-stu-id="01ea4-198">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="01ea4-199">Ежедневно (может отображаться до 31 дня)</span><span class="sxs-lookup"><span data-stu-id="01ea4-199">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="01ea4-200">Еженедельно (может отображаться до 12 недель)</span><span class="sxs-lookup"><span data-stu-id="01ea4-200">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="01ea4-201">Ежемесячно (может отображаться до 12 месяцев)</span><span class="sxs-lookup"><span data-stu-id="01ea4-201">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="01ea4-p111">Если число значений между начальной и конечной датами превышает максимальное допустимое для выбранного интервала, отображается максимальное возможное число значений (с начальной даты). Например, если вы выбрали интервал "Ежедневно" с начальной датой 07.07.2012 и конечной датой 28.02.2012, будут показаны данные для периода с 07.08.2012 24:00 до 07.09.2012 24:00 (то есть для 31 дня).</span><span class="sxs-lookup"><span data-stu-id="01ea4-p111">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) are displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="01ea4-204">Метрики</span><span class="sxs-lookup"><span data-stu-id="01ea4-204">Metrics</span></span>

<span data-ttu-id="01ea4-205">В следующей таблице показаны данные, которые приводятся в сводном отчете о конференциях.</span><span class="sxs-lookup"><span data-stu-id="01ea4-205">The following table the information provided by the Conferences Summary Report.</span></span>

### <a name="conference-summary-report-metrics"></a><span data-ttu-id="01ea4-206">Показатели сводного отчета о конференциях</span><span class="sxs-lookup"><span data-stu-id="01ea4-206">Conference Summary Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="01ea4-207">Имя</span><span class="sxs-lookup"><span data-stu-id="01ea4-207">Name</span></span></th>
<th><span data-ttu-id="01ea4-208">Возможность сортировки по этому показателю</span><span class="sxs-lookup"><span data-stu-id="01ea4-208">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="01ea4-209">Описание</span><span class="sxs-lookup"><span data-stu-id="01ea4-209">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="01ea4-210"><strong>Каждый час</strong></span><span class="sxs-lookup"><span data-stu-id="01ea4-210"><strong>Hourly</strong></span></span></p>
<p><span data-ttu-id="01ea4-211"><strong>Ежедневное</strong></span><span class="sxs-lookup"><span data-stu-id="01ea4-211"><strong>Daily</strong></span></span></p>
<p><span data-ttu-id="01ea4-212"><strong>Еженедельное</strong></span><span class="sxs-lookup"><span data-stu-id="01ea4-212"><strong>Weekly</strong></span></span></p>
<p><span data-ttu-id="01ea4-213"><strong>Monthly</strong></span><span class="sxs-lookup"><span data-stu-id="01ea4-213"><strong>Monthly</strong></span></span></p></td>
<td><p><span data-ttu-id="01ea4-214">Нет</span><span class="sxs-lookup"><span data-stu-id="01ea4-214">No</span></span></p></td>
<td><p><span data-ttu-id="01ea4-p112">Указывает на временной интервал, выбранной на панели фильтров. Вы можете щелкнуть временной интервал, чтобы просмотреть подробные сведения для него, если они доступны. Например, если используется интервал "Ежедневно", то при щелчке по дате 07.07.2012 вы увидите почасовые сведения о регистрации пользователей за эту дату.</span><span class="sxs-lookup"><span data-stu-id="01ea4-p112">Indicates the time interval that you selected on the filter toolbar. Where applicable, you can click a given time interval to view detailed information for that interval. For example, if you are using the Daily interval and you click 7/7/2012, you see an hourly breakdown of user registration activity for that date.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="01ea4-218"><strong>Общее количество конференций</strong></span><span class="sxs-lookup"><span data-stu-id="01ea4-218"><strong>Total conferences</strong></span></span></p></td>
<td><p><span data-ttu-id="01ea4-219">Нет</span><span class="sxs-lookup"><span data-stu-id="01ea4-219">No</span></span></p></td>
<td><p><span data-ttu-id="01ea4-p113">Общее число проведенных конференций (вне зависимости от их типа). При щелчке по этому элементу выводится отчет о действиях конференций за выбранный период.</span><span class="sxs-lookup"><span data-stu-id="01ea4-p113">Total number of conferences (regardless of conference type) that were held. When you click this item, the report shows you the Conference Activity Report for the selected time period.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="01ea4-222"><strong>Общее количество участников</strong></span><span class="sxs-lookup"><span data-stu-id="01ea4-222"><strong>Total participants</strong></span></span></p></td>
<td><p><span data-ttu-id="01ea4-223">Нет</span><span class="sxs-lookup"><span data-stu-id="01ea4-223">No</span></span></p></td>
<td><p><span data-ttu-id="01ea4-p114">Общее число пользователей, принявших участие в конференциях. При щелчке по этому элементу выводится отчет о действиях конференций за выбранный период.</span><span class="sxs-lookup"><span data-stu-id="01ea4-p114">Total number of people who took part in the conferences. When you click this item, the report shows you the Conference Activity Report for the selected time period.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="01ea4-226"><strong>Среднее число участников конференции</strong></span><span class="sxs-lookup"><span data-stu-id="01ea4-226"><strong>Average participants per conference</strong></span></span></p></td>
<td><p><span data-ttu-id="01ea4-227">Нет</span><span class="sxs-lookup"><span data-stu-id="01ea4-227">No</span></span></p></td>
<td><p><span data-ttu-id="01ea4-p115">Среднее число пользователей, принявших участие в отдельной конференции. Определяется путем деления общего числа конференций на общее число участников.</span><span class="sxs-lookup"><span data-stu-id="01ea4-p115">Average number of people who took part in a given conference. Determined by dividing the total conferences by the total participants.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="01ea4-230"><strong>Общее количество аудио- и видеоконференций</strong></span><span class="sxs-lookup"><span data-stu-id="01ea4-230"><strong>Total A/V conferences</strong></span></span></p></td>
<td><p><span data-ttu-id="01ea4-231">Нет</span><span class="sxs-lookup"><span data-stu-id="01ea4-231">No</span></span></p></td>
<td><p><span data-ttu-id="01ea4-232">Общее число конференций, в которых использовалась голосовая и видеосвязь.</span><span class="sxs-lookup"><span data-stu-id="01ea4-232">Total number of conferences that included audio or video.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="01ea4-233"><strong>Общее количество минут аудио- и видеоконференций</strong></span><span class="sxs-lookup"><span data-stu-id="01ea4-233"><strong>Total A/V conference minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="01ea4-234">Нет</span><span class="sxs-lookup"><span data-stu-id="01ea4-234">No</span></span></p></td>
<td><p><span data-ttu-id="01ea4-235">Общее количество минут аудио- и видеоконференций.</span><span class="sxs-lookup"><span data-stu-id="01ea4-235">Total number of minutes devoted to audio/video conferencing.</span></span></p>
<p><span data-ttu-id="01ea4-236">В разделе Общее количество минут в Конференции A/V собраны все типы аудио-и видеоконференций, в том числе аудио-и видеоконференций. Конференции для обмена мгновенными сообщениями; Конференции для совместного использования приложений; Конференции с данными; и PSTN Конференции.</span><span class="sxs-lookup"><span data-stu-id="01ea4-236">The Total A/V conference minutes metric summarizes all the audio/visual conference types, including: A/V conferences; IM conferences; app sharing conferences; data conferences; and PSTN conferences.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="01ea4-237"><strong>Total A/V conference participant minutes (Общее время в аудио- или видеоконференции в минутах)</strong></span><span class="sxs-lookup"><span data-stu-id="01ea4-237"><strong>Total A/V conference participant minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="01ea4-238">Нет</span><span class="sxs-lookup"><span data-stu-id="01ea4-238">No</span></span></p></td>
<td><p><span data-ttu-id="01ea4-p116">Общее количество минут участия пользователей в аудио- и видеоконференциях. Например, предположим, что один пользователь участвует в аудио- или видеоконференции 5 минут, а второй пользователь — 3 минуты. В сумме это дает 8 минут участия: 5 плюс 3.</span><span class="sxs-lookup"><span data-stu-id="01ea4-p116">Total number of participant minutes devoted to audio/video conferencing. For example, suppose one user spends 5 minutes in an audio/video conference and a second user spends 3 minutes in that same conference. That makes a total of 8 participant minutes: 5 minutes plus 3 minutes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="01ea4-242"><strong>Среднее количество минут аудио- или видеоконференции</strong></span><span class="sxs-lookup"><span data-stu-id="01ea4-242"><strong>Average A/V conference minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="01ea4-243">Нет</span><span class="sxs-lookup"><span data-stu-id="01ea4-243">No</span></span></p></td>
<td><p><span data-ttu-id="01ea4-244">Средняя длительность аудио- или видеоконференции в минутах.</span><span class="sxs-lookup"><span data-stu-id="01ea4-244">Average number of minutes per audio/video conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="01ea4-245"><strong>Общее количество организаторов конференций</strong></span><span class="sxs-lookup"><span data-stu-id="01ea4-245"><strong>Total number of unique organizers of conferences</strong></span></span></p></td>
<td><p><span data-ttu-id="01ea4-246">Нет</span><span class="sxs-lookup"><span data-stu-id="01ea4-246">No</span></span></p></td>
<td><p><span data-ttu-id="01ea4-p117">Общее число пользователей, организовавших по крайней мере одну конференцию. Пользователь, организовавший несколько конференции, считается одним уникальным организатором, так же как и организовавший одну конференцию.</span><span class="sxs-lookup"><span data-stu-id="01ea4-p117">Total number of users who organized at least one conference. Users who organized more than one conference are counted as one unique organizer, just like users who only organized a single conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="01ea4-249"><strong>Общее количество сообщений в конференциях</strong></span><span class="sxs-lookup"><span data-stu-id="01ea4-249"><strong>Total conference messages</strong></span></span></p></td>
<td><p><span data-ttu-id="01ea4-250">Нет</span><span class="sxs-lookup"><span data-stu-id="01ea4-250">No</span></span></p></td>
<td><p><span data-ttu-id="01ea4-251">Общее число мгновенных сообщений, отправленных в рамках конференций.</span><span class="sxs-lookup"><span data-stu-id="01ea4-251">Total number of instant messages sent during the conferences.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

