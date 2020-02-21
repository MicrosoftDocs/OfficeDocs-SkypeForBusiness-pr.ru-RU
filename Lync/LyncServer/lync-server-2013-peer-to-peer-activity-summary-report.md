---
title: 'Lync Server 2013: сводный отчет по одноранговым действиям'
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
ms.openlocfilehash: 03d1f47cbd38604e90354dc6f3590894071cc4c3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215755"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="peer-to-peer-activity-summary-report-in-lync-server-2013"></a><span data-ttu-id="15172-102">Сводный отчет по одноранговым действиям в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="15172-102">Peer-to-Peer Activity Summary Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="15172-103">_**Последнее изменение темы:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="15172-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="15172-104">Сводный отчет по одноранговым действиям (Peer-to-Peer Activity Summary Report) предоставляет общий обзор одноранговых сеансов связи.</span><span class="sxs-lookup"><span data-stu-id="15172-104">The Peer-to-Peer Activity Summary Report provides an overall view of your peer-to-peer communication sessions.</span></span> <span data-ttu-id="15172-105">Одноранговый сеанс обычно включает в себя всего два пользователя и не требует использования служб конференц-связи Lync Server.</span><span class="sxs-lookup"><span data-stu-id="15172-105">A peer-to-peer session typically involves just two users, and does not require the use of the Lync Server conferencing services.</span></span> <span data-ttu-id="15172-106">По сравнению с Конференцией обычно применяется более двух пользователей, и для них требуется использование служб конференц-связи Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="15172-106">By comparison, a conference typically involves more than two users and requires the use of Microsoft Lync Server 2013 conferencing services.</span></span> <span data-ttu-id="15172-107">Обзор действий, относящихся к конференциям, дает сводный отчет по конференциям (Conference Summary Report).</span><span class="sxs-lookup"><span data-stu-id="15172-107">Conference activity is reported on the Conference Summary Report.</span></span>

<span data-ttu-id="15172-108">Сводный отчет по одноранговым действиям помогает, в частности, ответить на следующие вопросы.</span><span class="sxs-lookup"><span data-stu-id="15172-108">The Peer-to-Peer Activity Summary Report helps you answer questions like the following:</span></span>

  - <span data-ttu-id="15172-109">Сколько одноранговых мгновенных сообщений отправляют мои пользователи в обычный день?</span><span class="sxs-lookup"><span data-stu-id="15172-109">How many peer-to-peer instant messages do my users send on a typical day?</span></span>

  - <span data-ttu-id="15172-110">Действительно ли мои пользователи используют преимущества общего доступа к приложениям Lync Server и возможности передачи файлов?</span><span class="sxs-lookup"><span data-stu-id="15172-110">Are any of my users actually taking advantage of the Lync Server application sharing and file transfer capabilities?</span></span>

  - <span data-ttu-id="15172-p102">Пользователи жалуются, что в определенные периоды дня сеть кажется очень медленной. Сколько минут затрачивается на одноранговые аудио- и видеосеансы в эти периоды времени?</span><span class="sxs-lookup"><span data-stu-id="15172-p102">Users have been complaining that the network seems slow at certain times of the day. How many minutes are devoted to peer-to-peer audio and video sessions during those time periods?</span></span>

<div>

## <a name="accessing-the-peer-to-peer-activity-summary-report"></a><span data-ttu-id="15172-113">Доступ к сводному отчету по одноранговым действиям</span><span class="sxs-lookup"><span data-stu-id="15172-113">Accessing the Peer-to-Peer Activity Summary Report</span></span>

<span data-ttu-id="15172-114">Сводный отчет по одноранговым действиям можно вызвать на домашней странице отчетов мониторинга.</span><span class="sxs-lookup"><span data-stu-id="15172-114">You access the Peer-to-Peer Activity Summary Report from the Monitoring Reports home page.</span></span> <span data-ttu-id="15172-115">Вы открываете [отчет об одноранговом обмене мгновенными сообщениями в Lync Server 2013](lync-server-2013-peer-to-peer-im-report.md) , щелкнув один из следующих показателей:</span><span class="sxs-lookup"><span data-stu-id="15172-115">You open the [Peer-to-Peer IM Report in Lync Server 2013](lync-server-2013-peer-to-peer-im-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="15172-116">Общее число одноранговых сеансов обмена мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="15172-116">Total peer-to-peer IM sessions</span></span>

  - <span data-ttu-id="15172-117">Общее число одноранговых мгновенных сообщений</span><span class="sxs-lookup"><span data-stu-id="15172-117">Total peer-to-peer IM messages</span></span>

<span data-ttu-id="15172-118">Аналогично, можно открыть отчет по одноранговой голосовой и видеосвязи (Peer-to-Peer Voice and Video Report), щелкнув какую-либо из следующих метрик:</span><span class="sxs-lookup"><span data-stu-id="15172-118">Likewise, you can open the Peer-to-Peer Voice and Video Report by clicking any of these metrics:</span></span>

  - <span data-ttu-id="15172-119">Общее количество одноранговых сеансов аудиосвязи</span><span class="sxs-lookup"><span data-stu-id="15172-119">Total peer-to-peer audio sessions</span></span>

  - <span data-ttu-id="15172-120">Общее время в одноранговых сеансах аудиосвязи в минутах</span><span class="sxs-lookup"><span data-stu-id="15172-120">Total peer-to-peer audio session minutes</span></span>

  - <span data-ttu-id="15172-121">Общее количество одноранговых сеансов аудиосвязи</span><span class="sxs-lookup"><span data-stu-id="15172-121">Total peer-to-peer audio sessions</span></span>

  - <span data-ttu-id="15172-122">Общее время в одноранговых сеансах аудиосвязи в минутах</span><span class="sxs-lookup"><span data-stu-id="15172-122">Total peer-to-peer audio session minutes</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-activity-summary-report"></a><span data-ttu-id="15172-123">Оптимальное использование сводного отчета по одноранговым действиям</span><span class="sxs-lookup"><span data-stu-id="15172-123">Making the Best Use of the Peer-to-Peer Activity Summary Report</span></span>

<span data-ttu-id="15172-p104">Внизу сводного отчета по одноранговым действиям можно найти итоговые значения для таких метрик, как "Общее количество одноранговых сеансов обмена мгновенными сообщениями" и "Общее количество одноранговых мгновенных сообщений". Это позволяет получить краткую сводку по всем сведениям, которые можно найти в основном тексте отчета.</span><span class="sxs-lookup"><span data-stu-id="15172-p104">At the bottom of the Peer-to-Peer Activity Summary Report you'll find totals for metrics such as Total peer-to-peer IM sessions and Total peer-to-peer IM messages. This provides a quick summary of the detailed information found in the body of the report.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="15172-126">Фильтры</span><span class="sxs-lookup"><span data-stu-id="15172-126">Filters</span></span>

<span data-ttu-id="15172-p105">Фильтры позволяют получать более адресный набор данных или просматривать полученные данные разными способами. Например, сводный отчет по одноранговым действиям позволяет выбрать способ группирования данных. В данном случае действия группируются по часу, дню, неделе или месяцу.</span><span class="sxs-lookup"><span data-stu-id="15172-p105">Filters provide a way for you to return a more finely targeted set of data or to view the returned data in different ways. For example, the Peer-to-Peer Activity Summary Report enables you to choose how data should be grouped. In this case, activity grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="15172-130">В следующей таблице приведены фильтры, которые можно использовать в сводном отчете по одноранговым действиям.</span><span class="sxs-lookup"><span data-stu-id="15172-130">The following table lists the filters that you can use with the Peer-to-Peer Activity Summary Report.</span></span>

### <a name="peer-to-peer-activity-summary-report-filters"></a><span data-ttu-id="15172-131">Фильтры сводного отчета по одноранговым действиям</span><span class="sxs-lookup"><span data-stu-id="15172-131">Peer-to-Peer Activity Summary Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="15172-132">Имя</span><span class="sxs-lookup"><span data-stu-id="15172-132">Name</span></span></th>
<th><span data-ttu-id="15172-133">Описание</span><span class="sxs-lookup"><span data-stu-id="15172-133">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="15172-134"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="15172-134"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="15172-p106">Дата и время начала диапазона времени. Чтобы просматривать данные по часам, введите дату и время начала:</span><span class="sxs-lookup"><span data-stu-id="15172-p106">Start date and time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="15172-137">17.07.12 13:00</span><span class="sxs-lookup"><span data-stu-id="15172-137">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="15172-p107">Если вы не вводите начальное время, отчет автоматически начинается с 24:00 указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</span><span class="sxs-lookup"><span data-stu-id="15172-p107">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="15172-140">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="15172-140">7/17/12012</span></span></p>
<p><span data-ttu-id="15172-141">Чтобы просматривать данные по неделям или месяцам, введите дату, попадающую в интересующую неделю или месяц (не обязательно указывать первый день недели или месяца):</span><span class="sxs-lookup"><span data-stu-id="15172-141">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="15172-142">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="15172-142">7/13/2012</span></span></p>
<p><span data-ttu-id="15172-143">Недели всегда отсчитываются с воскресенья по субботу.</span><span class="sxs-lookup"><span data-stu-id="15172-143">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15172-144"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="15172-144"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="15172-p108">Дата и время конца диапазона времени. Чтобы просматривать данные по часам, введите дату и время окончания:</span><span class="sxs-lookup"><span data-stu-id="15172-p108">End date and time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="15172-147">7/17/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="15172-147">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="15172-p109">Если вы не вводите конечное время, отчет автоматически заканчивается в 24:00 указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</span><span class="sxs-lookup"><span data-stu-id="15172-p109">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="15172-150">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="15172-150">7/17/12012</span></span></p>
<p><span data-ttu-id="15172-151">Чтобы просматривать данные по неделям или месяцам, введите дату, попадающую в интересующую неделю или месяц (не обязательно указывать первый день недели или месяца):</span><span class="sxs-lookup"><span data-stu-id="15172-151">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="15172-152">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="15172-152">7/13/2012</span></span></p>
<p><span data-ttu-id="15172-153">Недели всегда продолжаются с воскресенья по субботу.</span><span class="sxs-lookup"><span data-stu-id="15172-153">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15172-154"><strong>Interval</strong></span><span class="sxs-lookup"><span data-stu-id="15172-154"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="15172-p110">Временной интервал. Выберите один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="15172-p110">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="15172-157">Ежечасно (может отображаться до 25 часов)</span><span class="sxs-lookup"><span data-stu-id="15172-157">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="15172-158">Ежедневно (может отображаться до 31 дня)</span><span class="sxs-lookup"><span data-stu-id="15172-158">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="15172-159">Еженедельно (может отображаться до 12 недель)</span><span class="sxs-lookup"><span data-stu-id="15172-159">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="15172-160">Ежемесячно — может отображаться не более 12 месяцев.</span><span class="sxs-lookup"><span data-stu-id="15172-160">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="15172-p111">Если указаны такие даты начала и конца, что превышается максимально разрешенное количество значений для выбранного интервала, то отображается только максимально допустимое количество значений (начиная с даты начала). Например, если выбран ежедневный интервал с датой начала 7/17/2012 и датой конца 2/28/2012, то отображаются данные для дней от  8/7/2012 12:00 до 9/7/2012 12:00 (т.е. данные для 31 дня).</span><span class="sxs-lookup"><span data-stu-id="15172-p111">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 7/17/12012 and an end date of 2/28/2012, data is displayed for the days 8/7/12012 12:00 AM to 9/7/12012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="15172-163">Метрик</span><span class="sxs-lookup"><span data-stu-id="15172-163">Metrics</span></span>

<span data-ttu-id="15172-164">В следующей таблице приведены виды сведений, предоставляемые в сводном отчете по одноранговым действиям.</span><span class="sxs-lookup"><span data-stu-id="15172-164">The following table lists the information provided in the Peer-to-Peer Activity Summary Report.</span></span>

### <a name="peer-to-peer-activity-summary-report-metrics"></a><span data-ttu-id="15172-165">Метрики сводного отчета по одноранговым действиям</span><span class="sxs-lookup"><span data-stu-id="15172-165">Peer-to-Peer Activity Summary Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="15172-166">Имя</span><span class="sxs-lookup"><span data-stu-id="15172-166">Name</span></span></th>
<th><span data-ttu-id="15172-167">Возможность сортировки по этому показателю</span><span class="sxs-lookup"><span data-stu-id="15172-167">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="15172-168">Описание</span><span class="sxs-lookup"><span data-stu-id="15172-168">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="15172-169"><strong>Каждый час</strong></span><span class="sxs-lookup"><span data-stu-id="15172-169"><strong>Hourly</strong></span></span></p>
<p><span data-ttu-id="15172-170"><strong>Daily (Ежедневный)</strong></span><span class="sxs-lookup"><span data-stu-id="15172-170"><strong>Daily</strong></span></span></p>
<p><span data-ttu-id="15172-171"><strong>Weekly (Еженедельный)</strong></span><span class="sxs-lookup"><span data-stu-id="15172-171"><strong>Weekly</strong></span></span></p>
<p><span data-ttu-id="15172-172"><strong>Monthly Channel</strong></span><span class="sxs-lookup"><span data-stu-id="15172-172"><strong>Monthly</strong></span></span></p></td>
<td><p><span data-ttu-id="15172-173">Нет</span><span class="sxs-lookup"><span data-stu-id="15172-173">No</span></span></p></td>
<td><p><span data-ttu-id="15172-p112">Указывает интервал времени, выбранный в панели инструментов фильтров. В применимых случаях можно щелкнуть конкретный интервал времени, чтобы просмотреть подробные сведения для этого интервала. Например, если вы используете ежедневный интервал и щелкнете дату 7/17/2012, то получите почасовую разбивку действий по регистрации пользователей на эту дату.</span><span class="sxs-lookup"><span data-stu-id="15172-p112">Indicates the time interval that you selected on the filter toolbar. Where applicable, you can click a given time interval to view detailed information for that interval. For example, if you are using the Daily interval and you click 7/17/12012, you see an hourly breakdown of user registration activity for that date.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15172-177"><strong>Общее количество одноранговых сеансов</strong></span><span class="sxs-lookup"><span data-stu-id="15172-177"><strong>Total peer-to-peer sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="15172-178">Нет</span><span class="sxs-lookup"><span data-stu-id="15172-178">No</span></span></p></td>
<td><p><span data-ttu-id="15172-179">Общее количество проведенных одноранговых сеансов, независимо от типа сеанса.</span><span class="sxs-lookup"><span data-stu-id="15172-179">Total number of peer-to-peer sessions conducted, regardless of session type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15172-180"><strong>Общее количество одноранговых сеансов обмена мгновенными сообщениями</strong></span><span class="sxs-lookup"><span data-stu-id="15172-180"><strong>Total peer-to-peer IM sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="15172-181">Нет</span><span class="sxs-lookup"><span data-stu-id="15172-181">No</span></span></p></td>
<td><p><span data-ttu-id="15172-p113">Общее количество одноранговых сеансов обмена мгновенными сообщениями. Если щелкнуть этот элемент, будет отображен отчет по одноранговым мгновенным сообщениям за выбранный период времени.</span><span class="sxs-lookup"><span data-stu-id="15172-p113">Total number of peer-to-peer instant messaging (IM) sessions. When you click this item, the report shows you the Peer-to-Peer IM Report for the selected time period.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15172-184"><strong>Общее количество одноранговых мгновенных сообщений</strong></span><span class="sxs-lookup"><span data-stu-id="15172-184"><strong>Total peer-to-peer IM messages</strong></span></span></p></td>
<td><p><span data-ttu-id="15172-185">Нет</span><span class="sxs-lookup"><span data-stu-id="15172-185">No</span></span></p></td>
<td><p><span data-ttu-id="15172-p114">Общее количество мгновенных сообщений, отправленных в одноранговых сеансах. Если щелкнуть этот элемент, будет отображен отчет по одноранговым мгновенным сообщениям за выбранный период времени.</span><span class="sxs-lookup"><span data-stu-id="15172-p114">Total number of instant messages sent in peer-to-peer sessions. When you click this item, the report shows you the Peer-to-Peer IM Report for the selected time period.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15172-188"><strong>Общее количество одноранговых сеансов аудиосвязи</strong></span><span class="sxs-lookup"><span data-stu-id="15172-188"><strong>Total peer-to-peer audio sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="15172-189">Нет</span><span class="sxs-lookup"><span data-stu-id="15172-189">No</span></span></p></td>
<td><p><span data-ttu-id="15172-p115">Общее количество одноранговых аудиовызовов. Если щелкнуть это поле, то будет отображен отчет по одноранговой голосовой и видеосвязи за выбранный период времени.</span><span class="sxs-lookup"><span data-stu-id="15172-p115">Total number of peer-to-peer audio calls. When you click this field, the report shows you the Peer-to-Peer Voice and Video Report for the selected time period.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15172-192"><strong>Общее время в одноранговых сеансах аудиосвязи в минутах</strong></span><span class="sxs-lookup"><span data-stu-id="15172-192"><strong>Total peer-to-peer audio session minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="15172-193">Нет</span><span class="sxs-lookup"><span data-stu-id="15172-193">No</span></span></p></td>
<td><p><span data-ttu-id="15172-194">Общее количество времени, затраченного на одноранговые сеансы аудиосвязи.</span><span class="sxs-lookup"><span data-stu-id="15172-194">Total amount of time spent in peer-to-peer audio sessions.</span></span> <span data-ttu-id="15172-195">Если щелкнуть этот элемент, будет отображен отчет по одноранговой голосовой и видеосвязи за выбранный период времени.</span><span class="sxs-lookup"><span data-stu-id="15172-195">When you click this item, the report shows you the Peer-to-Peer Voice and Video Report for the selected time period.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15172-196"><strong>Среднее время в одноранговом сеансе аудиосвязи в минутах</strong></span><span class="sxs-lookup"><span data-stu-id="15172-196"><strong>Average peer-to-peer audio session minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="15172-197">Нет</span><span class="sxs-lookup"><span data-stu-id="15172-197">No</span></span></p></td>
<td><p><span data-ttu-id="15172-p117">Среднее количество времени, затрачиваемое в одноранговом сеансе аудиосвязи. Вычисляется путем деления общего времени в сеансах аудиосвязи на общее количество сеансов аудиосвязи.</span><span class="sxs-lookup"><span data-stu-id="15172-p117">Average amount of time spent in peer-to-peer audio sessions. Calculated by dividing the total audio session time by the total number of audio sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15172-200"><strong>Общее количество одноранговых сеансов видеосвязи</strong></span><span class="sxs-lookup"><span data-stu-id="15172-200"><strong>Total peer-to-peer video sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="15172-201">Нет</span><span class="sxs-lookup"><span data-stu-id="15172-201">No</span></span></p></td>
<td><p><span data-ttu-id="15172-p118">Общее количество одноранговых видеовызовов. Обратите внимание, что эти сеансы видеосвязи также учитываются и как сеансы аудиосвязи: каждый сеанс видеосвязи учитывается как один сеанс видеосвязи и один сеанс аудиосвязи. Если щелкнуть этот элемент, будет отображен отчет по одноранговой голосовой и видеосвязи за выбранный период времени.</span><span class="sxs-lookup"><span data-stu-id="15172-p118">Total number of peer-to-peer video calls. Note that video sessions are also counted as audio sessions: each video session is counted as one video session and one audio session. When you click this item, the report shows you the Peer-to-Peer Voice and Video Report for the selected time period.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15172-205"><strong>Общее время в одноранговых сеансах видеосвязи в минутах</strong></span><span class="sxs-lookup"><span data-stu-id="15172-205"><strong>Total peer-to-peer video session minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="15172-206">Нет</span><span class="sxs-lookup"><span data-stu-id="15172-206">No</span></span></p></td>
<td><p><span data-ttu-id="15172-p119">Общее количество времени, затраченного на одноранговые сеансы видеосвязи. Если щелкнуть этот элемент, будет отображен отчет по одноранговой голосовой и видеосвязи за выбранный период времени.</span><span class="sxs-lookup"><span data-stu-id="15172-p119">Total amount of time spent in peer-to-peer video sessions. When you click this item, the report shows you the Peer-to-Peer Voice and Video Report for the selected time period.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15172-209"><strong>Среднее время в одноранговом сеансе видеосвязи в минутах</strong></span><span class="sxs-lookup"><span data-stu-id="15172-209"><strong>Average peer-to-peer video session minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="15172-210">Нет</span><span class="sxs-lookup"><span data-stu-id="15172-210">No</span></span></p></td>
<td><p><span data-ttu-id="15172-p120">Среднее количество времени, затрачиваемое в одноранговом сеансе видеосвязи. Вычисляется путем деления общего времени в сеансах видеосвязи на общее количество сеансов видеосвязи.</span><span class="sxs-lookup"><span data-stu-id="15172-p120">Average amount of time spent in peer-to-peer video sessions. Calculated by dividing the total video session time by the total number of video sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15172-213"><strong>Общее количество сеансов передачи файлов</strong></span><span class="sxs-lookup"><span data-stu-id="15172-213"><strong>Total peer-to-peer file transfer sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="15172-214">Нет</span><span class="sxs-lookup"><span data-stu-id="15172-214">No</span></span></p></td>
<td><p><span data-ttu-id="15172-215">Общее количество одноранговых сеансов, включающих передачу файлов.</span><span class="sxs-lookup"><span data-stu-id="15172-215">Total number of peer-to-peer sessions that included file transfers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15172-216"><strong>Общее количество одноранговых сеансов общего доступа к приложениям</strong></span><span class="sxs-lookup"><span data-stu-id="15172-216"><strong>Total peer-to-peer application sharing sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="15172-217">Нет</span><span class="sxs-lookup"><span data-stu-id="15172-217">No</span></span></p></td>
<td><p><span data-ttu-id="15172-218">Общее количество одноранговых сеансов, включающих общий доступ к приложениям.</span><span class="sxs-lookup"><span data-stu-id="15172-218">Total number of peer-to-peer sessions that included application sharing.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

