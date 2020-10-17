---
title: 'Lync Server 2013: сводный отчет по одноранговым действиям'
description: 'Lync Server 2013: сводный отчет по одноранговым действиям.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Peer-to-Peer Activity Summary Report
ms:assetid: e829a21e-9dfa-46ba-9b5b-077c175d6586
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615041(v=OCS.15)
ms:contentKeyID: 48185884
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2f081f542a5063ed83be470d3e991c58e458b487
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557305"
---
# <a name="peer-to-peer-activity-summary-report-in-lync-server-2013"></a><span data-ttu-id="8cd6d-103">Сводный отчет по одноранговым действиям в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8cd6d-103">Peer-to-Peer Activity Summary Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8cd6d-104">_**Последнее изменение темы:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="8cd6d-104">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="8cd6d-105">Сводный отчет по одноранговым действиям (Peer-to-Peer Activity Summary Report) предоставляет общий обзор одноранговых сеансов связи.</span><span class="sxs-lookup"><span data-stu-id="8cd6d-105">The Peer-to-Peer Activity Summary Report provides an overall view of your peer-to-peer communication sessions.</span></span> <span data-ttu-id="8cd6d-106">Одноранговый сеанс обычно включает в себя всего два пользователя и не требует использования служб конференц-связи Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8cd6d-106">A peer-to-peer session typically involves just two users, and does not require the use of the Lync Server conferencing services.</span></span> <span data-ttu-id="8cd6d-107">По сравнению с Конференцией обычно применяется более двух пользователей, и для них требуется использование служб конференц-связи Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8cd6d-107">By comparison, a conference typically involves more than two users and requires the use of Microsoft Lync Server 2013 conferencing services.</span></span> <span data-ttu-id="8cd6d-108">Обзор действий, относящихся к конференциям, дает сводный отчет по конференциям (Conference Summary Report).</span><span class="sxs-lookup"><span data-stu-id="8cd6d-108">Conference activity is reported on the Conference Summary Report.</span></span>

<span data-ttu-id="8cd6d-109">Сводный отчет по одноранговым действиям помогает, в частности, ответить на следующие вопросы.</span><span class="sxs-lookup"><span data-stu-id="8cd6d-109">The Peer-to-Peer Activity Summary Report helps you answer questions like the following:</span></span>

  - <span data-ttu-id="8cd6d-110">Сколько одноранговых мгновенных сообщений отправляют мои пользователи в обычный день?</span><span class="sxs-lookup"><span data-stu-id="8cd6d-110">How many peer-to-peer instant messages do my users send on a typical day?</span></span>

  - <span data-ttu-id="8cd6d-111">Действительно ли мои пользователи используют преимущества общего доступа к приложениям Lync Server и возможности передачи файлов?</span><span class="sxs-lookup"><span data-stu-id="8cd6d-111">Are any of my users actually taking advantage of the Lync Server application sharing and file transfer capabilities?</span></span>

  - <span data-ttu-id="8cd6d-p102">Пользователи жалуются, что в определенные периоды дня сеть кажется очень медленной. Сколько минут затрачивается на одноранговые аудио- и видеосеансы в эти периоды времени?</span><span class="sxs-lookup"><span data-stu-id="8cd6d-p102">Users have been complaining that the network seems slow at certain times of the day. How many minutes are devoted to peer-to-peer audio and video sessions during those time periods?</span></span>

<div>

## <a name="accessing-the-peer-to-peer-activity-summary-report"></a><span data-ttu-id="8cd6d-114">Доступ к сводному отчету по одноранговым действиям</span><span class="sxs-lookup"><span data-stu-id="8cd6d-114">Accessing the Peer-to-Peer Activity Summary Report</span></span>

<span data-ttu-id="8cd6d-115">Сводный отчет по одноранговым действиям можно вызвать на домашней странице отчетов мониторинга.</span><span class="sxs-lookup"><span data-stu-id="8cd6d-115">You access the Peer-to-Peer Activity Summary Report from the Monitoring Reports home page.</span></span> <span data-ttu-id="8cd6d-116">Вы открываете [отчет об одноранговом обмене мгновенными сообщениями в Lync Server 2013](lync-server-2013-peer-to-peer-im-report.md) , щелкнув один из следующих показателей:</span><span class="sxs-lookup"><span data-stu-id="8cd6d-116">You open the [Peer-to-Peer IM Report in Lync Server 2013](lync-server-2013-peer-to-peer-im-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="8cd6d-117">Общее число одноранговых сеансов обмена мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="8cd6d-117">Total peer-to-peer IM sessions</span></span>

  - <span data-ttu-id="8cd6d-118">Общее количество одноранговых мгновенных сообщений</span><span class="sxs-lookup"><span data-stu-id="8cd6d-118">Total peer-to-peer IM messages</span></span>

<span data-ttu-id="8cd6d-119">Аналогично, можно открыть отчет по одноранговой голосовой и видеосвязи (Peer-to-Peer Voice and Video Report), щелкнув какую-либо из следующих метрик:</span><span class="sxs-lookup"><span data-stu-id="8cd6d-119">Likewise, you can open the Peer-to-Peer Voice and Video Report by clicking any of these metrics:</span></span>

  - <span data-ttu-id="8cd6d-120">Общее количество одноранговых сеансов аудиосвязи</span><span class="sxs-lookup"><span data-stu-id="8cd6d-120">Total peer-to-peer audio sessions</span></span>

  - <span data-ttu-id="8cd6d-121">Общее время в одноранговых сеансах аудиосвязи в минутах</span><span class="sxs-lookup"><span data-stu-id="8cd6d-121">Total peer-to-peer audio session minutes</span></span>

  - <span data-ttu-id="8cd6d-122">Общее количество одноранговых сеансов аудиосвязи</span><span class="sxs-lookup"><span data-stu-id="8cd6d-122">Total peer-to-peer audio sessions</span></span>

  - <span data-ttu-id="8cd6d-123">Общее время в одноранговых сеансах аудиосвязи в минутах</span><span class="sxs-lookup"><span data-stu-id="8cd6d-123">Total peer-to-peer audio session minutes</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-activity-summary-report"></a><span data-ttu-id="8cd6d-124">Оптимальное использование сводного отчета по одноранговым действиям</span><span class="sxs-lookup"><span data-stu-id="8cd6d-124">Making the Best Use of the Peer-to-Peer Activity Summary Report</span></span>

<span data-ttu-id="8cd6d-p104">Внизу сводного отчета по одноранговым действиям можно найти итоговые значения для таких метрик, как "Общее количество одноранговых сеансов обмена мгновенными сообщениями" и "Общее количество одноранговых мгновенных сообщений". Это позволяет получить краткую сводку по всем сведениям, которые можно найти в основном тексте отчета.</span><span class="sxs-lookup"><span data-stu-id="8cd6d-p104">At the bottom of the Peer-to-Peer Activity Summary Report you'll find totals for metrics such as Total peer-to-peer IM sessions and Total peer-to-peer IM messages. This provides a quick summary of the detailed information found in the body of the report.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="8cd6d-127">Фильтры</span><span class="sxs-lookup"><span data-stu-id="8cd6d-127">Filters</span></span>

<span data-ttu-id="8cd6d-p105">Фильтры позволяют получать более адресный набор данных или просматривать полученные данные разными способами. Например, сводный отчет по одноранговым действиям позволяет выбрать способ группирования данных. В данном случае действия группируются по часу, дню, неделе или месяцу.</span><span class="sxs-lookup"><span data-stu-id="8cd6d-p105">Filters provide a way for you to return a more finely targeted set of data or to view the returned data in different ways. For example, the Peer-to-Peer Activity Summary Report enables you to choose how data should be grouped. In this case, activity grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="8cd6d-131">В следующей таблице приведены фильтры, которые можно использовать в сводном отчете по одноранговым действиям.</span><span class="sxs-lookup"><span data-stu-id="8cd6d-131">The following table lists the filters that you can use with the Peer-to-Peer Activity Summary Report.</span></span>

### <a name="peer-to-peer-activity-summary-report-filters"></a><span data-ttu-id="8cd6d-132">Фильтры сводного отчета по одноранговым действиям</span><span class="sxs-lookup"><span data-stu-id="8cd6d-132">Peer-to-Peer Activity Summary Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8cd6d-133">Имя</span><span class="sxs-lookup"><span data-stu-id="8cd6d-133">Name</span></span></th>
<th><span data-ttu-id="8cd6d-134">Описание</span><span class="sxs-lookup"><span data-stu-id="8cd6d-134">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8cd6d-135"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="8cd6d-135"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="8cd6d-p106">Дата и время начала диапазона времени. Чтобы просматривать данные по часам, введите дату и время начала:</span><span class="sxs-lookup"><span data-stu-id="8cd6d-p106">Start date and time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="8cd6d-138">7/17/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="8cd6d-138">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="8cd6d-p107">Если вы не вводите начальное время, отчет автоматически начинается с 24:00 указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</span><span class="sxs-lookup"><span data-stu-id="8cd6d-p107">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="8cd6d-141">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="8cd6d-141">7/17/12012</span></span></p>
<p><span data-ttu-id="8cd6d-142">Чтобы просматривать данные по неделям или месяцам, введите дату, попадающую в интересующую неделю или месяц (не обязательно указывать первый день недели или месяца):</span><span class="sxs-lookup"><span data-stu-id="8cd6d-142">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="8cd6d-143">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="8cd6d-143">7/13/2012</span></span></p>
<p><span data-ttu-id="8cd6d-144">Недели всегда продолжаются с воскресенья по субботу.</span><span class="sxs-lookup"><span data-stu-id="8cd6d-144">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8cd6d-145"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="8cd6d-145"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="8cd6d-p108">Дата и время конца диапазона времени. Чтобы просматривать данные по часам, введите дату и время окончания:</span><span class="sxs-lookup"><span data-stu-id="8cd6d-p108">End date and time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="8cd6d-148">7/17/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="8cd6d-148">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="8cd6d-p109">Если вы не вводите конечное время, отчет автоматически заканчивается в 24:00 указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</span><span class="sxs-lookup"><span data-stu-id="8cd6d-p109">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="8cd6d-151">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="8cd6d-151">7/17/12012</span></span></p>
<p><span data-ttu-id="8cd6d-152">Чтобы просматривать данные по неделям или месяцам, введите дату, попадающую в интересующую неделю или месяц (не обязательно указывать первый день недели или месяца):</span><span class="sxs-lookup"><span data-stu-id="8cd6d-152">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="8cd6d-153">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="8cd6d-153">7/13/2012</span></span></p>
<p><span data-ttu-id="8cd6d-154">Недели всегда продолжаются с воскресенья по субботу.</span><span class="sxs-lookup"><span data-stu-id="8cd6d-154">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8cd6d-155"><strong>Interval</strong></span><span class="sxs-lookup"><span data-stu-id="8cd6d-155"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="8cd6d-p110">Временной интервал. Выберите один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="8cd6d-p110">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="8cd6d-158">Ежечасно (может отображаться до 25 часов)</span><span class="sxs-lookup"><span data-stu-id="8cd6d-158">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="8cd6d-159">Ежедневно (может отображаться до 31 дня)</span><span class="sxs-lookup"><span data-stu-id="8cd6d-159">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="8cd6d-160">Еженедельно (может отображаться до 12 недель)</span><span class="sxs-lookup"><span data-stu-id="8cd6d-160">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="8cd6d-161">Ежемесячно — может отображаться не более 12 месяцев.</span><span class="sxs-lookup"><span data-stu-id="8cd6d-161">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="8cd6d-p111">Если указаны такие даты начала и конца, что превышается максимально разрешенное количество значений для выбранного интервала, то отображается только максимально допустимое количество значений (начиная с даты начала). Например, если выбран ежедневный интервал с датой начала 7/17/2012 и датой конца 2/28/2012, то отображаются данные для дней от  8/7/2012 12:00 до 9/7/2012 12:00 (т.е. данные для 31 дня).</span><span class="sxs-lookup"><span data-stu-id="8cd6d-p111">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 7/17/12012 and an end date of 2/28/2012, data is displayed for the days 8/7/12012 12:00 AM to 9/7/12012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="8cd6d-164">Метрики</span><span class="sxs-lookup"><span data-stu-id="8cd6d-164">Metrics</span></span>

<span data-ttu-id="8cd6d-165">В следующей таблице приведены виды сведений, предоставляемые в сводном отчете по одноранговым действиям.</span><span class="sxs-lookup"><span data-stu-id="8cd6d-165">The following table lists the information provided in the Peer-to-Peer Activity Summary Report.</span></span>

### <a name="peer-to-peer-activity-summary-report-metrics"></a><span data-ttu-id="8cd6d-166">Метрики сводного отчета по одноранговым действиям</span><span class="sxs-lookup"><span data-stu-id="8cd6d-166">Peer-to-Peer Activity Summary Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8cd6d-167">Имя</span><span class="sxs-lookup"><span data-stu-id="8cd6d-167">Name</span></span></th>
<th><span data-ttu-id="8cd6d-168">Возможность сортировки по этому показателю</span><span class="sxs-lookup"><span data-stu-id="8cd6d-168">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="8cd6d-169">Описание</span><span class="sxs-lookup"><span data-stu-id="8cd6d-169">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8cd6d-170"><strong>Каждый час</strong></span><span class="sxs-lookup"><span data-stu-id="8cd6d-170"><strong>Hourly</strong></span></span></p>
<p><span data-ttu-id="8cd6d-171"><strong>Ежедневное</strong></span><span class="sxs-lookup"><span data-stu-id="8cd6d-171"><strong>Daily</strong></span></span></p>
<p><span data-ttu-id="8cd6d-172"><strong>Еженедельное</strong></span><span class="sxs-lookup"><span data-stu-id="8cd6d-172"><strong>Weekly</strong></span></span></p>
<p><span data-ttu-id="8cd6d-173"><strong>Monthly</strong></span><span class="sxs-lookup"><span data-stu-id="8cd6d-173"><strong>Monthly</strong></span></span></p></td>
<td><p><span data-ttu-id="8cd6d-174">Нет</span><span class="sxs-lookup"><span data-stu-id="8cd6d-174">No</span></span></p></td>
<td><p><span data-ttu-id="8cd6d-p112">Указывает интервал времени, выбранный в панели инструментов фильтров. В применимых случаях можно щелкнуть конкретный интервал времени, чтобы просмотреть подробные сведения для этого интервала. Например, если вы используете ежедневный интервал и щелкнете дату 7/17/2012, то получите почасовую разбивку действий по регистрации пользователей на эту дату.</span><span class="sxs-lookup"><span data-stu-id="8cd6d-p112">Indicates the time interval that you selected on the filter toolbar. Where applicable, you can click a given time interval to view detailed information for that interval. For example, if you are using the Daily interval and you click 7/17/12012, you see an hourly breakdown of user registration activity for that date.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8cd6d-178"><strong>Общее количество одноранговых сеансов</strong></span><span class="sxs-lookup"><span data-stu-id="8cd6d-178"><strong>Total peer-to-peer sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="8cd6d-179">Нет</span><span class="sxs-lookup"><span data-stu-id="8cd6d-179">No</span></span></p></td>
<td><p><span data-ttu-id="8cd6d-180">Общее количество проведенных одноранговых сеансов, независимо от типа сеанса.</span><span class="sxs-lookup"><span data-stu-id="8cd6d-180">Total number of peer-to-peer sessions conducted, regardless of session type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8cd6d-181"><strong>Общее количество одноранговых сеансов обмена мгновенными сообщениями</strong></span><span class="sxs-lookup"><span data-stu-id="8cd6d-181"><strong>Total peer-to-peer IM sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="8cd6d-182">Нет</span><span class="sxs-lookup"><span data-stu-id="8cd6d-182">No</span></span></p></td>
<td><p><span data-ttu-id="8cd6d-p113">Общее количество одноранговых сеансов обмена мгновенными сообщениями. Если щелкнуть этот элемент, будет отображен отчет по одноранговым мгновенным сообщениям за выбранный период времени.</span><span class="sxs-lookup"><span data-stu-id="8cd6d-p113">Total number of peer-to-peer instant messaging (IM) sessions. When you click this item, the report shows you the Peer-to-Peer IM Report for the selected time period.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8cd6d-185"><strong>Общее количество одноранговых мгновенных сообщений</strong></span><span class="sxs-lookup"><span data-stu-id="8cd6d-185"><strong>Total peer-to-peer IM messages</strong></span></span></p></td>
<td><p><span data-ttu-id="8cd6d-186">Нет</span><span class="sxs-lookup"><span data-stu-id="8cd6d-186">No</span></span></p></td>
<td><p><span data-ttu-id="8cd6d-p114">Общее количество мгновенных сообщений, отправленных в одноранговых сеансах. Если щелкнуть этот элемент, будет отображен отчет по одноранговым мгновенным сообщениям за выбранный период времени.</span><span class="sxs-lookup"><span data-stu-id="8cd6d-p114">Total number of instant messages sent in peer-to-peer sessions. When you click this item, the report shows you the Peer-to-Peer IM Report for the selected time period.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8cd6d-189"><strong>Общее количество одноранговых сеансов аудиосвязи</strong></span><span class="sxs-lookup"><span data-stu-id="8cd6d-189"><strong>Total peer-to-peer audio sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="8cd6d-190">Нет</span><span class="sxs-lookup"><span data-stu-id="8cd6d-190">No</span></span></p></td>
<td><p><span data-ttu-id="8cd6d-p115">Общее количество одноранговых аудиовызовов. Если щелкнуть это поле, то будет отображен отчет по одноранговой голосовой и видеосвязи за выбранный период времени.</span><span class="sxs-lookup"><span data-stu-id="8cd6d-p115">Total number of peer-to-peer audio calls. When you click this field, the report shows you the Peer-to-Peer Voice and Video Report for the selected time period.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8cd6d-193"><strong>Общее время в одноранговых сеансах аудиосвязи в минутах</strong></span><span class="sxs-lookup"><span data-stu-id="8cd6d-193"><strong>Total peer-to-peer audio session minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="8cd6d-194">Нет</span><span class="sxs-lookup"><span data-stu-id="8cd6d-194">No</span></span></p></td>
<td><p><span data-ttu-id="8cd6d-195">Общее количество времени, затраченного на одноранговые сеансы аудиосвязи.</span><span class="sxs-lookup"><span data-stu-id="8cd6d-195">Total amount of time spent in peer-to-peer audio sessions.</span></span> <span data-ttu-id="8cd6d-196">Если щелкнуть этот элемент, будет отображен отчет по одноранговой голосовой и видеосвязи за выбранный период времени.</span><span class="sxs-lookup"><span data-stu-id="8cd6d-196">When you click this item, the report shows you the Peer-to-Peer Voice and Video Report for the selected time period.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8cd6d-197"><strong>Среднее время в одноранговом сеансе аудиосвязи в минутах</strong></span><span class="sxs-lookup"><span data-stu-id="8cd6d-197"><strong>Average peer-to-peer audio session minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="8cd6d-198">Нет</span><span class="sxs-lookup"><span data-stu-id="8cd6d-198">No</span></span></p></td>
<td><p><span data-ttu-id="8cd6d-p117">Среднее количество времени, затрачиваемое в одноранговом сеансе аудиосвязи. Вычисляется путем деления общего времени в сеансах аудиосвязи на общее количество сеансов аудиосвязи.</span><span class="sxs-lookup"><span data-stu-id="8cd6d-p117">Average amount of time spent in peer-to-peer audio sessions. Calculated by dividing the total audio session time by the total number of audio sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8cd6d-201"><strong>Общее количество одноранговых сеансов видеосвязи</strong></span><span class="sxs-lookup"><span data-stu-id="8cd6d-201"><strong>Total peer-to-peer video sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="8cd6d-202">Нет</span><span class="sxs-lookup"><span data-stu-id="8cd6d-202">No</span></span></p></td>
<td><p><span data-ttu-id="8cd6d-p118">Общее количество одноранговых видеовызовов. Обратите внимание, что эти сеансы видеосвязи также учитываются и как сеансы аудиосвязи: каждый сеанс видеосвязи учитывается как один сеанс видеосвязи и один сеанс аудиосвязи. Если щелкнуть этот элемент, будет отображен отчет по одноранговой голосовой и видеосвязи за выбранный период времени.</span><span class="sxs-lookup"><span data-stu-id="8cd6d-p118">Total number of peer-to-peer video calls. Note that video sessions are also counted as audio sessions: each video session is counted as one video session and one audio session. When you click this item, the report shows you the Peer-to-Peer Voice and Video Report for the selected time period.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8cd6d-206"><strong>Общее время в одноранговых сеансах видеосвязи в минутах</strong></span><span class="sxs-lookup"><span data-stu-id="8cd6d-206"><strong>Total peer-to-peer video session minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="8cd6d-207">Нет</span><span class="sxs-lookup"><span data-stu-id="8cd6d-207">No</span></span></p></td>
<td><p><span data-ttu-id="8cd6d-p119">Общее количество времени, затраченного на одноранговые сеансы видеосвязи. Если щелкнуть этот элемент, будет отображен отчет по одноранговой голосовой и видеосвязи за выбранный период времени.</span><span class="sxs-lookup"><span data-stu-id="8cd6d-p119">Total amount of time spent in peer-to-peer video sessions. When you click this item, the report shows you the Peer-to-Peer Voice and Video Report for the selected time period.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8cd6d-210"><strong>Среднее время в одноранговом сеансе видеосвязи в минутах</strong></span><span class="sxs-lookup"><span data-stu-id="8cd6d-210"><strong>Average peer-to-peer video session minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="8cd6d-211">Нет</span><span class="sxs-lookup"><span data-stu-id="8cd6d-211">No</span></span></p></td>
<td><p><span data-ttu-id="8cd6d-p120">Среднее количество времени, затрачиваемое в одноранговом сеансе видеосвязи. Вычисляется путем деления общего времени в сеансах видеосвязи на общее количество сеансов видеосвязи.</span><span class="sxs-lookup"><span data-stu-id="8cd6d-p120">Average amount of time spent in peer-to-peer video sessions. Calculated by dividing the total video session time by the total number of video sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8cd6d-214"><strong>Общее количество сеансов передачи файлов</strong></span><span class="sxs-lookup"><span data-stu-id="8cd6d-214"><strong>Total peer-to-peer file transfer sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="8cd6d-215">Нет</span><span class="sxs-lookup"><span data-stu-id="8cd6d-215">No</span></span></p></td>
<td><p><span data-ttu-id="8cd6d-216">Общее количество одноранговых сеансов, включающих передачу файлов.</span><span class="sxs-lookup"><span data-stu-id="8cd6d-216">Total number of peer-to-peer sessions that included file transfers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8cd6d-217"><strong>Общее количество одноранговых сеансов общего доступа к приложениям</strong></span><span class="sxs-lookup"><span data-stu-id="8cd6d-217"><strong>Total peer-to-peer application sharing sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="8cd6d-218">Нет</span><span class="sxs-lookup"><span data-stu-id="8cd6d-218">No</span></span></p></td>
<td><p><span data-ttu-id="8cd6d-219">Общее количество одноранговых сеансов, включающих общий доступ к приложениям.</span><span class="sxs-lookup"><span data-stu-id="8cd6d-219">Total number of peer-to-peer sessions that included application sharing.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

