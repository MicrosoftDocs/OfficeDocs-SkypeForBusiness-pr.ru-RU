---
title: 'Lync Server 2013: сводный отчет по конференциям'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Conference Summary Report
ms:assetid: 62f54812-5700-45a3-8526-8f58b0f77fbc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558656(v=OCS.15)
ms:contentKeyID: 48184299
ms.date: 09/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dde91a25d33bac5af8b1759b1fbfc90cfb9bc0ff
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841499"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conference-summary-report-in-lync-server-2013"></a><span data-ttu-id="0c99e-102">Сводный отчет о конференциях в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0c99e-102">Conference Summary Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0c99e-103">_**Тема последнего изменения:** 2014-09-03_</span><span class="sxs-lookup"><span data-stu-id="0c99e-103">_**Topic Last Modified:** 2014-09-03_</span></span>

<span data-ttu-id="0c99e-104">Сводный отчет по конференциям предоставляет обзорные сведения о сеансах веб-конференций.</span><span class="sxs-lookup"><span data-stu-id="0c99e-104">The Conference Summary Report provides an overall view of your online conferencing sessions.</span></span> <span data-ttu-id="0c99e-105">На Конференции обычно используется более 2 пользователей и требуется использование служб конференц-связи Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0c99e-105">A conference typically involves more than 2 users and requires the use of Microsoft Lync Server 2013 conferencing services.</span></span> <span data-ttu-id="0c99e-106">Для сравнения одноранговый сеанс обычно состоит только из двух пользователей и не требует использования служб конференц-связи Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0c99e-106">By comparison, a peer-to-peer session typically involves just 2 users and does not require the use of Lync Server's conferencing services.</span></span> <span data-ttu-id="0c99e-107">Сведения о одноранговых действиях выводятся в сводном отчете о действиях одноранговых групп [в Lync Server 2013](lync-server-2013-peer-to-peer-activity-summary-report.md).</span><span class="sxs-lookup"><span data-stu-id="0c99e-107">Peer-to-peer activities are reported on the [Peer-to-Peer Activity Summary Report in Lync Server 2013](lync-server-2013-peer-to-peer-activity-summary-report.md).</span></span>

<span data-ttu-id="0c99e-108">В сводном отчете о Конференции не только указывается количество конференций, сохраненных в течение определенного периода времени (ежечасно, ежедневно, еженедельно, ежемесячно), но при этом указывается общее количество пользователей, которые потратили на эти конференции, а также общее количество уникальных конференций. организаторов.</span><span class="sxs-lookup"><span data-stu-id="0c99e-108">The Conference Summary Report not only tells you how many conferences were held during a given time period (hourly, daily, weekly, monthly) but also tells you the total number of people who took part in those conferences, and the total number of unique conference organizers.</span></span>

<span data-ttu-id="0c99e-109">Под "уникальным" организатором понимается пользователь, который запланировал по крайней мере одну конференцию.</span><span class="sxs-lookup"><span data-stu-id="0c99e-109">A "unique” organizer is anyone who schedules at least one conference.</span></span> <span data-ttu-id="0c99e-110">Например, если пользователь Pilar Ackerman запланировал одну конференцию, он считается одним уникальным организатором.</span><span class="sxs-lookup"><span data-stu-id="0c99e-110">For example, if Pilar Ackerman schedules one conference she counts as one unique organizer.</span></span> <span data-ttu-id="0c99e-111">Если пользователь Ken Myer запланировал 148 конференций, он также считается одним уникальным организатором.</span><span class="sxs-lookup"><span data-stu-id="0c99e-111">If Ken Myer schedules 148 conferences he, too counts as one unique organizer.</span></span> <span data-ttu-id="0c99e-112">Например, в приведенной ниже таблице показаны запланированные 8 Конференции, но только три уникальных организаторов (Кен мер, почтового Вронский и Дэвида АХС).</span><span class="sxs-lookup"><span data-stu-id="0c99e-112">For example, the table below shows 8 conferences scheduled, but just three unique organizers (Ken Myer, Pilar Ackerman, and David Ahs).</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0c99e-113">Организатор конференции</span><span class="sxs-lookup"><span data-stu-id="0c99e-113">Conference Organizer</span></span></th>
<th><span data-ttu-id="0c99e-114">Дата конференции</span><span class="sxs-lookup"><span data-stu-id="0c99e-114">Conference Date</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0c99e-115">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="0c99e-115">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="0c99e-116">7/7/2012 10:00 AM</span><span class="sxs-lookup"><span data-stu-id="0c99e-116">7/7/2012 10:00 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c99e-117">David Ahs</span><span class="sxs-lookup"><span data-stu-id="0c99e-117">David Ahs</span></span></p></td>
<td><p><span data-ttu-id="0c99e-118">7/7/2012 10:00 AM</span><span class="sxs-lookup"><span data-stu-id="0c99e-118">7/7/2012 10:00 AM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c99e-119">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="0c99e-119">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="0c99e-120">7/7/2012 11:00 AM</span><span class="sxs-lookup"><span data-stu-id="0c99e-120">7/7/2012 11:00 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c99e-121">Pilar Ackerman</span><span class="sxs-lookup"><span data-stu-id="0c99e-121">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="0c99e-122">7/7/2012 11:00 AM</span><span class="sxs-lookup"><span data-stu-id="0c99e-122">7/7/2012 11:00 AM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c99e-123">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="0c99e-123">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="0c99e-124">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="0c99e-124">7/7/2012 1:00 PM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c99e-125">Pilar Ackerman</span><span class="sxs-lookup"><span data-stu-id="0c99e-125">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="0c99e-126">7/7/2012 2:00 PM</span><span class="sxs-lookup"><span data-stu-id="0c99e-126">7/7/2012 2:00 PM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c99e-127">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="0c99e-127">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="0c99e-128">7/2/2012 10:00 AM</span><span class="sxs-lookup"><span data-stu-id="0c99e-128">7/2/2012 10:00 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c99e-129">Pilar Ackerman</span><span class="sxs-lookup"><span data-stu-id="0c99e-129">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="0c99e-130">7/2/2012 10:00 AM</span><span class="sxs-lookup"><span data-stu-id="0c99e-130">7/2/2012 10:00 AM</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="0c99e-131">В сводном отчете о конференциях также указывается количество конференций, в которых использовалась голосовая и видеосвязь.</span><span class="sxs-lookup"><span data-stu-id="0c99e-131">The Conference Summary Report also indicates how many conferences included audio and/or video.</span></span>

<div>

## <a name="accessing-the-conference-summary-report"></a><span data-ttu-id="0c99e-132">Доступ к сводному отчету о конференциях</span><span class="sxs-lookup"><span data-stu-id="0c99e-132">Accessing the Conference Summary Report</span></span>

<span data-ttu-id="0c99e-p103">Доступ к сводному отчету о конференциях можно получить с домашней страницы "Отчеты наблюдения". Вы можете просмотреть подробные сведения в отчете о действиях конференций, щелкнув один из следующих разделов:</span><span class="sxs-lookup"><span data-stu-id="0c99e-p103">The Conference Summary Report is accessed from the Monitoring Reports home page. You can drill down to the Conference Activity report by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="0c99e-135">Общее количество конференций</span><span class="sxs-lookup"><span data-stu-id="0c99e-135">Total conferences</span></span>

  - <span data-ttu-id="0c99e-136">Общее количество участников</span><span class="sxs-lookup"><span data-stu-id="0c99e-136">Total participants</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-conference-summary-report"></a><span data-ttu-id="0c99e-137">Рекомендации по использованию сводного отчета о конференциях</span><span class="sxs-lookup"><span data-stu-id="0c99e-137">Making the Best Use of the Conference Summary Report</span></span>

<span data-ttu-id="0c99e-138">Суммарные значения для большинства показателей, используемых в сводном отчете о конференциях, приведены в нижней части отчета.</span><span class="sxs-lookup"><span data-stu-id="0c99e-138">Total values for most of the metrics used on the Conference Summary Report can be found at the bottom of the report; scroll down to see values such as the total number of conferences held during the specified time period, and the total number of people who participated in those conferences.</span></span> <span data-ttu-id="0c99e-139">Прокрутите отчет вниз, чтобы просмотреть общее число конференций, проведенных в течение определенного периода, и общее число их участников.</span><span class="sxs-lookup"><span data-stu-id="0c99e-139">One metric that is not totaled at the bottom of the report is Total unique conference organizers.</span></span> <span data-ttu-id="0c99e-140">Однако среди суммарных значений нет общего числа уникальных организаторов.</span><span class="sxs-lookup"><span data-stu-id="0c99e-140">Why not?</span></span> <span data-ttu-id="0c99e-141">Объясняется это просто.</span><span class="sxs-lookup"><span data-stu-id="0c99e-141">Here’s one reason.</span></span> <span data-ttu-id="0c99e-142">Предположим, что вы просматриваете данные за месяц.</span><span class="sxs-lookup"><span data-stu-id="0c99e-142">Suppose you are looking at a month's worth of data.</span></span> <span data-ttu-id="0c99e-143">В первый день было 34 уникальных организатора конференций, а во второй день – 27 организаторов.</span><span class="sxs-lookup"><span data-stu-id="0c99e-143">On day 1 you had 34 unique conference organizers; on day 2 you had 27 unique conference organizers.</span></span> <span data-ttu-id="0c99e-144">Означает ли это, что общее число уникальных организаторов в течение этих двух дней равно 61?</span><span class="sxs-lookup"><span data-stu-id="0c99e-144">Does that mean you had 61 unique conference organizers for those two days?</span></span> <span data-ttu-id="0c99e-145">Не обязательно.</span><span class="sxs-lookup"><span data-stu-id="0c99e-145">Not necessarily.</span></span> <span data-ttu-id="0c99e-146">В действительности все 27 пользователей, организовавших конференции во второй день, могут входить в число 34 пользователей, организовавших конференции в первый день.</span><span class="sxs-lookup"><span data-stu-id="0c99e-146">After all, all 27 people who organized conferences on day 2 might be among the 34 people who organized conferences on day 1.</span></span> <span data-ttu-id="0c99e-147">Например, в этом простом отчете Обратите внимание на то, что Кен мер и почтового Вронский запланированные конференции как в 7/7/2012, так и в 7/2/2012:</span><span class="sxs-lookup"><span data-stu-id="0c99e-147">For example, in this simple report, note that Ken Myer and Pilar Ackerman scheduled conferences both on 7/7/2012 and on 7/2/2012:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0c99e-148">Организатор конференции</span><span class="sxs-lookup"><span data-stu-id="0c99e-148">Conference Organizer</span></span></th>
<th><span data-ttu-id="0c99e-149">Дата конференции</span><span class="sxs-lookup"><span data-stu-id="0c99e-149">Conference Date</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0c99e-150">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="0c99e-150">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="0c99e-151">7/7/2012 10:00 AM</span><span class="sxs-lookup"><span data-stu-id="0c99e-151">7/7/2012 10:00 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c99e-152">David Ahs</span><span class="sxs-lookup"><span data-stu-id="0c99e-152">David Ahs</span></span></p></td>
<td><p><span data-ttu-id="0c99e-153">7/7/2012 10:00 AM</span><span class="sxs-lookup"><span data-stu-id="0c99e-153">7/7/2012 10:00 AM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c99e-154">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="0c99e-154">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="0c99e-155">7/7/2012 11:00 AM</span><span class="sxs-lookup"><span data-stu-id="0c99e-155">7/7/2012 11:00 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c99e-156">Pilar Ackerman</span><span class="sxs-lookup"><span data-stu-id="0c99e-156">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="0c99e-157">7/7/2012 11:00 AM</span><span class="sxs-lookup"><span data-stu-id="0c99e-157">7/7/2012 11:00 AM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c99e-158">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="0c99e-158">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="0c99e-159">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="0c99e-159">7/7/2012 1:00 PM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c99e-160">Pilar Ackerman</span><span class="sxs-lookup"><span data-stu-id="0c99e-160">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="0c99e-161">7/7/2012 2:00 PM</span><span class="sxs-lookup"><span data-stu-id="0c99e-161">7/7/2012 2:00 PM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c99e-162">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="0c99e-162">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="0c99e-163">7/2/2012 10:00 AM</span><span class="sxs-lookup"><span data-stu-id="0c99e-163">7/2/2012 10:00 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c99e-164">Pilar Ackerman</span><span class="sxs-lookup"><span data-stu-id="0c99e-164">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="0c99e-165">7/2/2012 10:00 AM</span><span class="sxs-lookup"><span data-stu-id="0c99e-165">7/2/2012 10:00 AM</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="0c99e-166">Чтобы получить более точное представление об общем количестве уникальных организаторов конференций, измените временной интервал. Например, просмотрите данные по месяцам, а не по дням.</span><span class="sxs-lookup"><span data-stu-id="0c99e-166">To get a better idea of the total number of unique users who organized conferences, change your time interval; for example, look at the data by month instead of by day.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="0c99e-167">Фильтры</span><span class="sxs-lookup"><span data-stu-id="0c99e-167">Filters</span></span>

<span data-ttu-id="0c99e-p105">Фильтры позволяют получить более конкретные наборы возвращаемых данных. Например, сводный отчет о конференциях позволяет выбрать способ группировки данных. Конференции можно группировать по часу, дню, неделе или месяцу.</span><span class="sxs-lookup"><span data-stu-id="0c99e-p105">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Conference Summary Report enables you to choose how data should be grouped. In this case, conferences grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="0c99e-171">В следующей таблице перечислены фильтры, которые вы можете использовать со сводным отчетом о конференциях.</span><span class="sxs-lookup"><span data-stu-id="0c99e-171">The following table lists the filters that you can use with the Conference Summary Report.</span></span>

### <a name="conference-summary-report-filters"></a><span data-ttu-id="0c99e-172">Фильтры сводного отчета о конференциях</span><span class="sxs-lookup"><span data-stu-id="0c99e-172">Conference Summary Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0c99e-173">Имя</span><span class="sxs-lookup"><span data-stu-id="0c99e-173">Name</span></span></th>
<th><span data-ttu-id="0c99e-174">Описание</span><span class="sxs-lookup"><span data-stu-id="0c99e-174">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0c99e-175"><strong>От</strong></span><span class="sxs-lookup"><span data-stu-id="0c99e-175"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="0c99e-p106">Начальные дата/время для временного диапазона. Чтобы просмотреть данные по часам, введите начальные дату и время следующим образом:</span><span class="sxs-lookup"><span data-stu-id="0c99e-p106">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="0c99e-178">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="0c99e-178">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="0c99e-p107">Если вы не вводите начальное время, отчет автоматически начинается с 12:00 AM указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</span><span class="sxs-lookup"><span data-stu-id="0c99e-p107">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="0c99e-181">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="0c99e-181">7/7/2012</span></span></p>
<p><span data-ttu-id="0c99e-182">Чтобы просмотреть данные за неделю или месяц, введите дату, выпадающую на любое время в рамках недели или месяца, которые вы хотите просмотреть (вам не требуется вводить первый день недели или месяца):</span><span class="sxs-lookup"><span data-stu-id="0c99e-182">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="0c99e-183">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="0c99e-183">7/3/2012</span></span></p>
<p><span data-ttu-id="0c99e-184">Недели всегда отсчитываются с воскресенья по субботу.</span><span class="sxs-lookup"><span data-stu-id="0c99e-184">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c99e-185"><strong>До</strong></span><span class="sxs-lookup"><span data-stu-id="0c99e-185"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="0c99e-p108">Конечные дата/время для временного диапазона. Чтобы просмотреть данные по часам, введите конечные дату и время следующим образом:</span><span class="sxs-lookup"><span data-stu-id="0c99e-p108">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="0c99e-188">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="0c99e-188">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="0c99e-p109">Если вы не вводите конечное время, отчет автоматически заканчивается в 12:00 AM указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</span><span class="sxs-lookup"><span data-stu-id="0c99e-p109">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="0c99e-191">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="0c99e-191">7/7/2012</span></span></p>
<p><span data-ttu-id="0c99e-192">Чтобы просмотреть данные за неделю или месяц, введите дату, выпадающую на любое время в рамках недели или месяца, которые вы хотите просмотреть (вам не требуется вводить первый день недели или месяца):</span><span class="sxs-lookup"><span data-stu-id="0c99e-192">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="0c99e-193">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="0c99e-193">7/3/2012</span></span></p>
<p><span data-ttu-id="0c99e-194">Недели всегда отсчитываются с воскресенья по субботу.</span><span class="sxs-lookup"><span data-stu-id="0c99e-194">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c99e-195"><strong>Интервал</strong></span><span class="sxs-lookup"><span data-stu-id="0c99e-195"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="0c99e-p110">Временной интервал. Выберите одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="0c99e-p110">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="0c99e-198">Ежечасно (можно отобразить не более 25 часов)</span><span class="sxs-lookup"><span data-stu-id="0c99e-198">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="0c99e-199">Ежедневно (можно отобразить не более 31 дня)</span><span class="sxs-lookup"><span data-stu-id="0c99e-199">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="0c99e-200">Еженедельно (можно отобразить не более 12 недель)</span><span class="sxs-lookup"><span data-stu-id="0c99e-200">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="0c99e-201">Ежемесячно (можно отобразить не более 12 месяцев)</span><span class="sxs-lookup"><span data-stu-id="0c99e-201">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="0c99e-202">Если число значений между начальной и конечной датами превышает максимальное допустимое для выбранного интервала, отображается максимальное возможное число значений (с начальной даты).</span><span class="sxs-lookup"><span data-stu-id="0c99e-202">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) are displayed.</span></span> <span data-ttu-id="0c99e-203">Например, если выбрать ежедневный интервал с датой начала 7/7/2012 и датой окончания 2/28/2012, данные будут выводиться для дней 8/7/2012 12:00 – 9/7/2012 12:00 AM (то есть, всего за 31 дня).</span><span class="sxs-lookup"><span data-stu-id="0c99e-203">For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="0c99e-204">Показатели</span><span class="sxs-lookup"><span data-stu-id="0c99e-204">Metrics</span></span>

<span data-ttu-id="0c99e-205">В следующей таблице показаны данные, которые приводятся в сводном отчете о конференциях.</span><span class="sxs-lookup"><span data-stu-id="0c99e-205">The following table the information provided by the Conferences Summary Report.</span></span>

### <a name="conference-summary-report-metrics"></a><span data-ttu-id="0c99e-206">Показатели сводного отчета о конференциях</span><span class="sxs-lookup"><span data-stu-id="0c99e-206">Conference Summary Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0c99e-207">Имя</span><span class="sxs-lookup"><span data-stu-id="0c99e-207">Name</span></span></th>
<th><span data-ttu-id="0c99e-208">Поддержка сортировки</span><span class="sxs-lookup"><span data-stu-id="0c99e-208">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="0c99e-209">Описание</span><span class="sxs-lookup"><span data-stu-id="0c99e-209">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0c99e-210"><strong>Ежечасно</strong></span><span class="sxs-lookup"><span data-stu-id="0c99e-210"><strong>Hourly</strong></span></span></p>
<p><span data-ttu-id="0c99e-211"><strong>Ежедневно</strong></span><span class="sxs-lookup"><span data-stu-id="0c99e-211"><strong>Daily</strong></span></span></p>
<p><span data-ttu-id="0c99e-212"><strong>Еженедельно</strong></span><span class="sxs-lookup"><span data-stu-id="0c99e-212"><strong>Weekly</strong></span></span></p>
<p><span data-ttu-id="0c99e-213"><strong>Ежемесячно</strong></span><span class="sxs-lookup"><span data-stu-id="0c99e-213"><strong>Monthly</strong></span></span></p></td>
<td><p><span data-ttu-id="0c99e-214">Нет</span><span class="sxs-lookup"><span data-stu-id="0c99e-214">No</span></span></p></td>
<td><p><span data-ttu-id="0c99e-215">Указывает на временной интервал, выбранный на панели фильтров.</span><span class="sxs-lookup"><span data-stu-id="0c99e-215">Indicates the time interval that you selected on the filter toolbar.</span></span> <span data-ttu-id="0c99e-216">Вы можете щелкнуть временной интервал, чтобы просмотреть подробные сведения для него, если они доступны.</span><span class="sxs-lookup"><span data-stu-id="0c99e-216">Where applicable, you can click a given time interval to view detailed information for that interval.</span></span> <span data-ttu-id="0c99e-217">Например, если вы используете ежедневный интервал и нажимайте 7/7/2012, появится Почасовая подразделение действия регистрации пользователя для этой даты.</span><span class="sxs-lookup"><span data-stu-id="0c99e-217">For example, if you are using the Daily interval and you click 7/7/2012, you see an hourly breakdown of user registration activity for that date.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c99e-218"><strong>Всего конференций</strong></span><span class="sxs-lookup"><span data-stu-id="0c99e-218"><strong>Total conferences</strong></span></span></p></td>
<td><p><span data-ttu-id="0c99e-219">Нет</span><span class="sxs-lookup"><span data-stu-id="0c99e-219">No</span></span></p></td>
<td><p><span data-ttu-id="0c99e-p113">Общее число проведенных конференций (вне зависимости от их типа). При щелчке по этому элементу выводится отчет о действиях конференций за выбранный период.</span><span class="sxs-lookup"><span data-stu-id="0c99e-p113">Total number of conferences (regardless of conference type) that were held. When you click this item, the report shows you the Conference Activity Report for the selected time period.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c99e-222"><strong>Общее количество участников</strong></span><span class="sxs-lookup"><span data-stu-id="0c99e-222"><strong>Total participants</strong></span></span></p></td>
<td><p><span data-ttu-id="0c99e-223">Нет</span><span class="sxs-lookup"><span data-stu-id="0c99e-223">No</span></span></p></td>
<td><p><span data-ttu-id="0c99e-p114">Общее число пользователей, принявших участие в конференциях. При щелчке по этому элементу выводится отчет о действиях конференций за выбранный период.</span><span class="sxs-lookup"><span data-stu-id="0c99e-p114">Total number of people who took part in the conferences. When you click this item, the report shows you the Conference Activity Report for the selected time period.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c99e-226"><strong>Среднее число участников конференции</strong></span><span class="sxs-lookup"><span data-stu-id="0c99e-226"><strong>Average participants per conference</strong></span></span></p></td>
<td><p><span data-ttu-id="0c99e-227">Нет</span><span class="sxs-lookup"><span data-stu-id="0c99e-227">No</span></span></p></td>
<td><p><span data-ttu-id="0c99e-p115">Среднее число пользователей, принявших участие в отдельной конференции. Определяется путем деления общего числа конференций на общее число участников.</span><span class="sxs-lookup"><span data-stu-id="0c99e-p115">Average number of people who took part in a given conference. Determined by dividing the total conferences by the total participants.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c99e-230"><strong>Общее количество аудио- и видеоконференций</strong></span><span class="sxs-lookup"><span data-stu-id="0c99e-230"><strong>Total A/V conferences</strong></span></span></p></td>
<td><p><span data-ttu-id="0c99e-231">Нет</span><span class="sxs-lookup"><span data-stu-id="0c99e-231">No</span></span></p></td>
<td><p><span data-ttu-id="0c99e-232">Общее число конференций, в которых использовалась голосовая и видеосвязь.</span><span class="sxs-lookup"><span data-stu-id="0c99e-232">Total number of conferences that included audio or video.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c99e-233"><strong>Общее время аудио- и видеоконференций (в минутах)</strong></span><span class="sxs-lookup"><span data-stu-id="0c99e-233"><strong>Total A/V conference minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="0c99e-234">Нет</span><span class="sxs-lookup"><span data-stu-id="0c99e-234">No</span></span></p></td>
<td><p><span data-ttu-id="0c99e-235">Общее количество минут аудио- и видеоконференций.</span><span class="sxs-lookup"><span data-stu-id="0c99e-235">Total number of minutes devoted to audio/video conferencing.</span></span></p>
<p><span data-ttu-id="0c99e-236">В разделе Общее метрика конференции "на/V" собраны все типы аудио-и видеоконференций, в том числе — Конференции с интерфейсом/V. Конференции для обмена мгновенными сообщениями; Конференции о совместном использовании приложений; Конференции с данными; и PSTN.</span><span class="sxs-lookup"><span data-stu-id="0c99e-236">The Total A/V conference minutes metric summarizes all the audio/visual conference types, including: A/V conferences; IM conferences; app sharing conferences; data conferences; and PSTN conferences.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c99e-237"><strong>Общее время участия в аудио- или видеоконференции (в минутах)</strong></span><span class="sxs-lookup"><span data-stu-id="0c99e-237"><strong>Total A/V conference participant minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="0c99e-238">Нет</span><span class="sxs-lookup"><span data-stu-id="0c99e-238">No</span></span></p></td>
<td><p><span data-ttu-id="0c99e-p116">Общее количество минут участия пользователей в аудио- и видеоконференциях. Например, предположим, что один пользователь участвует в аудио- или видеоконференции 5 минут, а второй пользователь – 3 минуты. В сумме это дает 8 минут участия: 5 плюс 3.</span><span class="sxs-lookup"><span data-stu-id="0c99e-p116">Total number of participant minutes devoted to audio/video conferencing. For example, suppose one user spends 5 minutes in an audio/video conference and a second user spends 3 minutes in that same conference. That makes a total of 8 participant minutes: 5 minutes plus 3 minutes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c99e-242"><strong>Среднее количество минут аудио- или видеоконференции</strong></span><span class="sxs-lookup"><span data-stu-id="0c99e-242"><strong>Average A/V conference minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="0c99e-243">Нет</span><span class="sxs-lookup"><span data-stu-id="0c99e-243">No</span></span></p></td>
<td><p><span data-ttu-id="0c99e-244">Средняя длительность аудио- или видеоконференции в минутах.</span><span class="sxs-lookup"><span data-stu-id="0c99e-244">Average number of minutes per audio/video conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c99e-245"><strong>Общее количество организаторов конференций</strong></span><span class="sxs-lookup"><span data-stu-id="0c99e-245"><strong>Total number of unique organizers of conferences</strong></span></span></p></td>
<td><p><span data-ttu-id="0c99e-246">Нет</span><span class="sxs-lookup"><span data-stu-id="0c99e-246">No</span></span></p></td>
<td><p><span data-ttu-id="0c99e-p117">Общее число пользователей, организовавших по крайней мере одну конференцию. Пользователь, организовавший несколько конференции, считается одним уникальным организатором, так же как и организовавший одну конференцию.</span><span class="sxs-lookup"><span data-stu-id="0c99e-p117">Total number of users who organized at least one conference. Users who organized more than one conference are counted as one unique organizer, just like users who only organized a single conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c99e-249"><strong>Общее количество сообщений в конференциях</strong></span><span class="sxs-lookup"><span data-stu-id="0c99e-249"><strong>Total conference messages</strong></span></span></p></td>
<td><p><span data-ttu-id="0c99e-250">Нет</span><span class="sxs-lookup"><span data-stu-id="0c99e-250">No</span></span></p></td>
<td><p><span data-ttu-id="0c99e-251">Общее число мгновенных сообщений, отправленных в рамках конференций.</span><span class="sxs-lookup"><span data-stu-id="0c99e-251">Total number of instant messages sent during the conferences.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

