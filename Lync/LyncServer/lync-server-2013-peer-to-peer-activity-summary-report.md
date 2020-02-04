---
title: 'Lync Server 2013: сводный отчет о действиях одноранговых узлов'
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
ms.openlocfilehash: d55c3d84fe48158490473c31e9782dc63e298310
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755319"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="peer-to-peer-activity-summary-report-in-lync-server-2013"></a><span data-ttu-id="56d71-102">Сводный отчет о действиях одноранговых узлов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="56d71-102">Peer-to-Peer Activity Summary Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="56d71-103">_**Тема последнего изменения:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="56d71-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="56d71-104">Сводный отчет по одноранговым действиям (Peer-to-Peer Activity Summary Report) предоставляет общий обзор одноранговых сеансов связи.</span><span class="sxs-lookup"><span data-stu-id="56d71-104">The Peer-to-Peer Activity Summary Report provides an overall view of your peer-to-peer communication sessions.</span></span> <span data-ttu-id="56d71-105">Одноранговый сеанс обычно состоит только из двух пользователей и не требует использования служб конференции Lync Server.</span><span class="sxs-lookup"><span data-stu-id="56d71-105">A peer-to-peer session typically involves just two users, and does not require the use of the Lync Server conferencing services.</span></span> <span data-ttu-id="56d71-106">По сравнению с собранием обычно используется более двух пользователей и требуется использование служб конференц-связи Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="56d71-106">By comparison, a conference typically involves more than two users and requires the use of Microsoft Lync Server 2013 conferencing services.</span></span> <span data-ttu-id="56d71-107">Обзор действий, относящихся к конференциям, дает сводный отчет по конференциям (Conference Summary Report).</span><span class="sxs-lookup"><span data-stu-id="56d71-107">Conference activity is reported on the Conference Summary Report.</span></span>

<span data-ttu-id="56d71-108">Сводный отчет по одноранговым действиям помогает, в частности, ответить на следующие вопросы.</span><span class="sxs-lookup"><span data-stu-id="56d71-108">The Peer-to-Peer Activity Summary Report helps you answer questions like the following:</span></span>

  - <span data-ttu-id="56d71-109">Сколько одноранговых мгновенных сообщений отправляют мои пользователи в обычный день?</span><span class="sxs-lookup"><span data-stu-id="56d71-109">How many peer-to-peer instant messages do my users send on a typical day?</span></span>

  - <span data-ttu-id="56d71-110">Действительно ли мои пользователи используют преимущества совместного использования приложений Lync Server и обмена файлами?</span><span class="sxs-lookup"><span data-stu-id="56d71-110">Are any of my users actually taking advantage of the Lync Server application sharing and file transfer capabilities?</span></span>

  - <span data-ttu-id="56d71-p102">Пользователи жалуются, что в определенные периоды дня сеть кажется очень медленной. Сколько минут затрачивается на одноранговые аудио- и видеосеансы в эти периоды времени?</span><span class="sxs-lookup"><span data-stu-id="56d71-p102">Users have been complaining that the network seems slow at certain times of the day. How many minutes are devoted to peer-to-peer audio and video sessions during those time periods?</span></span>

<div>

## <a name="accessing-the-peer-to-peer-activity-summary-report"></a><span data-ttu-id="56d71-113">Доступ к сводному отчету по одноранговым действиям</span><span class="sxs-lookup"><span data-stu-id="56d71-113">Accessing the Peer-to-Peer Activity Summary Report</span></span>

<span data-ttu-id="56d71-114">Сводный отчет по одноранговым действиям можно вызвать на домашней странице отчетов мониторинга.</span><span class="sxs-lookup"><span data-stu-id="56d71-114">You access the Peer-to-Peer Activity Summary Report from the Monitoring Reports home page.</span></span> <span data-ttu-id="56d71-115">Вы открываете [отчет о одноранговых сообщениях в Lync Server 2013](lync-server-2013-peer-to-peer-im-report.md) , щелкая один из указанных ниже метрик.</span><span class="sxs-lookup"><span data-stu-id="56d71-115">You open the [Peer-to-Peer IM Report in Lync Server 2013](lync-server-2013-peer-to-peer-im-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="56d71-116">Общее количество одноранговых сеансов обмена мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="56d71-116">Total peer-to-peer IM sessions</span></span>

  - <span data-ttu-id="56d71-117">Общее количество одноранговых мгновенных сообщений</span><span class="sxs-lookup"><span data-stu-id="56d71-117">Total peer-to-peer IM messages</span></span>

<span data-ttu-id="56d71-118">Аналогично, можно открыть отчет по одноранговой голосовой и видеосвязи (Peer-to-Peer Voice and Video Report), щелкнув какую-либо из следующих метрик:</span><span class="sxs-lookup"><span data-stu-id="56d71-118">Likewise, you can open the Peer-to-Peer Voice and Video Report by clicking any of these metrics:</span></span>

  - <span data-ttu-id="56d71-119">Общее количество одноранговых сеансов аудиосвязи</span><span class="sxs-lookup"><span data-stu-id="56d71-119">Total peer-to-peer audio sessions</span></span>

  - <span data-ttu-id="56d71-120">Общее время в одноранговых сеансах аудиосвязи в минутах</span><span class="sxs-lookup"><span data-stu-id="56d71-120">Total peer-to-peer audio session minutes</span></span>

  - <span data-ttu-id="56d71-121">Общее количество одноранговых сеансов аудиосвязи</span><span class="sxs-lookup"><span data-stu-id="56d71-121">Total peer-to-peer audio sessions</span></span>

  - <span data-ttu-id="56d71-122">Общее время в одноранговых сеансах аудиосвязи в минутах</span><span class="sxs-lookup"><span data-stu-id="56d71-122">Total peer-to-peer audio session minutes</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-activity-summary-report"></a><span data-ttu-id="56d71-123">Оптимальное использование сводного отчета по одноранговым действиям</span><span class="sxs-lookup"><span data-stu-id="56d71-123">Making the Best Use of the Peer-to-Peer Activity Summary Report</span></span>

<span data-ttu-id="56d71-p104">Внизу сводного отчета по одноранговым действиям можно найти итоговые значения для таких метрик, как "Общее количество одноранговых сеансов обмена мгновенными сообщениями" и "Общее количество одноранговых мгновенных сообщений". Это позволяет получить краткую сводку по всем сведениям, которые можно найти в основном тексте отчета.</span><span class="sxs-lookup"><span data-stu-id="56d71-p104">At the bottom of the Peer-to-Peer Activity Summary Report you'll find totals for metrics such as Total peer-to-peer IM sessions and Total peer-to-peer IM messages. This provides a quick summary of the detailed information found in the body of the report.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="56d71-126">Фильтры</span><span class="sxs-lookup"><span data-stu-id="56d71-126">Filters</span></span>

<span data-ttu-id="56d71-p105">Фильтры позволяют получать более адресный набор данных или просматривать полученные данные разными способами. Например, сводный отчет по одноранговым действиям позволяет выбрать способ группирования данных. В данном случае действия группируются по часу, дню, неделе или месяцу.</span><span class="sxs-lookup"><span data-stu-id="56d71-p105">Filters provide a way for you to return a more finely targeted set of data or to view the returned data in different ways. For example, the Peer-to-Peer Activity Summary Report enables you to choose how data should be grouped. In this case, activity grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="56d71-130">В следующей таблице приведены фильтры, которые можно использовать в сводном отчете по одноранговым действиям.</span><span class="sxs-lookup"><span data-stu-id="56d71-130">The following table lists the filters that you can use with the Peer-to-Peer Activity Summary Report.</span></span>

### <a name="peer-to-peer-activity-summary-report-filters"></a><span data-ttu-id="56d71-131">Фильтры сводного отчета по одноранговым действиям</span><span class="sxs-lookup"><span data-stu-id="56d71-131">Peer-to-Peer Activity Summary Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="56d71-132">Имя</span><span class="sxs-lookup"><span data-stu-id="56d71-132">Name</span></span></th>
<th><span data-ttu-id="56d71-133">Описание</span><span class="sxs-lookup"><span data-stu-id="56d71-133">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="56d71-134"><strong>От</strong></span><span class="sxs-lookup"><span data-stu-id="56d71-134"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="56d71-p106">Начальная дата и начальное время для диапазона времени. Чтобы просмотреть данные по часам, введите начальную дату и начальное время в следующем формате:</span><span class="sxs-lookup"><span data-stu-id="56d71-p106">Start date and time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="56d71-137">7/17/12012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="56d71-137">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="56d71-p107">Если вы не вводите начальное время, отчет автоматически начинается с 12:00 AM указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</span><span class="sxs-lookup"><span data-stu-id="56d71-p107">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="56d71-140">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="56d71-140">7/17/12012</span></span></p>
<p><span data-ttu-id="56d71-141">Чтобы просмотреть данные за неделю или месяц, введите дату, выпадающую на любое время в рамках недели или месяца, которые вы хотите просмотреть (вам не требуется вводить первый день недели или месяца):</span><span class="sxs-lookup"><span data-stu-id="56d71-141">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="56d71-142">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="56d71-142">7/13/2012</span></span></p>
<p><span data-ttu-id="56d71-143">Недели всегда отсчитываются с воскресенья по субботу.</span><span class="sxs-lookup"><span data-stu-id="56d71-143">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="56d71-144"><strong>До</strong></span><span class="sxs-lookup"><span data-stu-id="56d71-144"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="56d71-p108">Конечная дата и конечное время для диапазона времени. Чтобы просмотреть данные по часам, введите конечную дату и конечное время в следующем формате:</span><span class="sxs-lookup"><span data-stu-id="56d71-p108">End date and time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="56d71-147">7/17/12012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="56d71-147">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="56d71-p109">Если вы не вводите конечное время, отчет автоматически заканчивается в 12:00 AM указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</span><span class="sxs-lookup"><span data-stu-id="56d71-p109">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="56d71-150">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="56d71-150">7/17/12012</span></span></p>
<p><span data-ttu-id="56d71-151">Чтобы просмотреть данные за неделю или месяц, введите дату, выпадающую на любое время в рамках недели или месяца, которые вы хотите просмотреть (вам не требуется вводить первый день недели или месяца):</span><span class="sxs-lookup"><span data-stu-id="56d71-151">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="56d71-152">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="56d71-152">7/13/2012</span></span></p>
<p><span data-ttu-id="56d71-153">Недели всегда отсчитываются с воскресенья по субботу.</span><span class="sxs-lookup"><span data-stu-id="56d71-153">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="56d71-154"><strong>Интервал</strong></span><span class="sxs-lookup"><span data-stu-id="56d71-154"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="56d71-p110">Временной интервал. Выберите одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="56d71-p110">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="56d71-157">Ежечасно (можно отобразить не более 25 часов)</span><span class="sxs-lookup"><span data-stu-id="56d71-157">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="56d71-158">Ежедневно (можно отобразить не более 31 дня)</span><span class="sxs-lookup"><span data-stu-id="56d71-158">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="56d71-159">Еженедельно (можно отобразить не более 12 недель)</span><span class="sxs-lookup"><span data-stu-id="56d71-159">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="56d71-160">Ежемесячно (можно отобразить не более 12 месяцев)</span><span class="sxs-lookup"><span data-stu-id="56d71-160">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="56d71-161">Если количество значений между начальной и конечной датами превышает максимально допустимое для выбранного интервала, отображается максимальное возможное количество значений (от начальной даты и далее).</span><span class="sxs-lookup"><span data-stu-id="56d71-161">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed.</span></span> <span data-ttu-id="56d71-162">Например, если выбрать ежедневный интервал с датой начала 7/17/12012 и датой окончания 2/28/2012, данные будут выводиться для дней 8/7/12012 12:00 – 9/7/12012 12:00 AM (то есть, всего за 31 дня).</span><span class="sxs-lookup"><span data-stu-id="56d71-162">For example, if you select the Daily interval with a start date of 7/17/12012 and an end date of 2/28/2012, data is displayed for the days 8/7/12012 12:00 AM to 9/7/12012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="56d71-163">Показатели</span><span class="sxs-lookup"><span data-stu-id="56d71-163">Metrics</span></span>

<span data-ttu-id="56d71-164">В следующей таблице перечислены сведения, указанные в сводном отчете о действиях одноранговых узлов.</span><span class="sxs-lookup"><span data-stu-id="56d71-164">The following table lists the information provided in the Peer-to-Peer Activity Summary Report.</span></span>

### <a name="peer-to-peer-activity-summary-report-metrics"></a><span data-ttu-id="56d71-165">Метрики сводного отчета о действиях одноранговых групп</span><span class="sxs-lookup"><span data-stu-id="56d71-165">Peer-to-Peer Activity Summary Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="56d71-166">Имя</span><span class="sxs-lookup"><span data-stu-id="56d71-166">Name</span></span></th>
<th><span data-ttu-id="56d71-167">Поддержка сортировки</span><span class="sxs-lookup"><span data-stu-id="56d71-167">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="56d71-168">Описание</span><span class="sxs-lookup"><span data-stu-id="56d71-168">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="56d71-169"><strong>Ежечасно</strong></span><span class="sxs-lookup"><span data-stu-id="56d71-169"><strong>Hourly</strong></span></span></p>
<p><span data-ttu-id="56d71-170"><strong>Ежедневно</strong></span><span class="sxs-lookup"><span data-stu-id="56d71-170"><strong>Daily</strong></span></span></p>
<p><span data-ttu-id="56d71-171"><strong>Еженедельно</strong></span><span class="sxs-lookup"><span data-stu-id="56d71-171"><strong>Weekly</strong></span></span></p>
<p><span data-ttu-id="56d71-172"><strong>Ежемесячно</strong></span><span class="sxs-lookup"><span data-stu-id="56d71-172"><strong>Monthly</strong></span></span></p></td>
<td><p><span data-ttu-id="56d71-173">Нет</span><span class="sxs-lookup"><span data-stu-id="56d71-173">No</span></span></p></td>
<td><p><span data-ttu-id="56d71-174">Указывает на временной интервал, выбранный на панели фильтров.</span><span class="sxs-lookup"><span data-stu-id="56d71-174">Indicates the time interval that you selected on the filter toolbar.</span></span> <span data-ttu-id="56d71-175">Вы можете щелкнуть временной интервал, чтобы просмотреть подробные сведения для него, если они доступны.</span><span class="sxs-lookup"><span data-stu-id="56d71-175">Where applicable, you can click a given time interval to view detailed information for that interval.</span></span> <span data-ttu-id="56d71-176">Например, если вы используете ежедневный интервал и нажимайте 7/17/12012, появится Почасовая подразделение действия регистрации пользователя для этой даты.</span><span class="sxs-lookup"><span data-stu-id="56d71-176">For example, if you are using the Daily interval and you click 7/17/12012, you see an hourly breakdown of user registration activity for that date.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="56d71-177"><strong>Общее количество одноранговых сеансов</strong></span><span class="sxs-lookup"><span data-stu-id="56d71-177"><strong>Total peer-to-peer sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="56d71-178">Нет</span><span class="sxs-lookup"><span data-stu-id="56d71-178">No</span></span></p></td>
<td><p><span data-ttu-id="56d71-179">Общее количество одноранговых сеансов, проведенных вне зависимости от типа сеанса.</span><span class="sxs-lookup"><span data-stu-id="56d71-179">Total number of peer-to-peer sessions conducted, regardless of session type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="56d71-180"><strong>Общее количество одноранговых сеансов обмена мгновенными сообщениями</strong></span><span class="sxs-lookup"><span data-stu-id="56d71-180"><strong>Total peer-to-peer IM sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="56d71-181">Нет</span><span class="sxs-lookup"><span data-stu-id="56d71-181">No</span></span></p></td>
<td><p><span data-ttu-id="56d71-182">Общее количество одноранговых сеансов обмена мгновенными сообщениями (IM).</span><span class="sxs-lookup"><span data-stu-id="56d71-182">Total number of peer-to-peer instant messaging (IM) sessions.</span></span> <span data-ttu-id="56d71-183">При щелчке по этому элементу в отчете отображается одноранговый отчет о мгновенных сообщениях за выбранный период времени.</span><span class="sxs-lookup"><span data-stu-id="56d71-183">When you click this item, the report shows you the Peer-to-Peer IM Report for the selected time period.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="56d71-184"><strong>Общее количество одноранговых мгновенных сообщений</strong></span><span class="sxs-lookup"><span data-stu-id="56d71-184"><strong>Total peer-to-peer IM messages</strong></span></span></p></td>
<td><p><span data-ttu-id="56d71-185">Нет</span><span class="sxs-lookup"><span data-stu-id="56d71-185">No</span></span></p></td>
<td><p><span data-ttu-id="56d71-186">Общее количество мгновенных сообщений, отправленных в одноранговых сеансах.</span><span class="sxs-lookup"><span data-stu-id="56d71-186">Total number of instant messages sent in peer-to-peer sessions.</span></span> <span data-ttu-id="56d71-187">При щелчке по этому элементу в отчете отображается одноранговый отчет о мгновенных сообщениях за выбранный период времени.</span><span class="sxs-lookup"><span data-stu-id="56d71-187">When you click this item, the report shows you the Peer-to-Peer IM Report for the selected time period.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="56d71-188"><strong>Общее количество одноранговых сеансов аудиосвязи</strong></span><span class="sxs-lookup"><span data-stu-id="56d71-188"><strong>Total peer-to-peer audio sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="56d71-189">Нет</span><span class="sxs-lookup"><span data-stu-id="56d71-189">No</span></span></p></td>
<td><p><span data-ttu-id="56d71-190">Общее количество одноранговых голосовых вызовов.</span><span class="sxs-lookup"><span data-stu-id="56d71-190">Total number of peer-to-peer audio calls.</span></span> <span data-ttu-id="56d71-191">Если щелкнуть это поле, в отчете будет показана одноранговый голосовой и Видеоотчет по выбранному периоду времени.</span><span class="sxs-lookup"><span data-stu-id="56d71-191">When you click this field, the report shows you the Peer-to-Peer Voice and Video Report for the selected time period.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="56d71-192"><strong>Общее количество одноранговых сеансов аудиосвязи (мин)</strong></span><span class="sxs-lookup"><span data-stu-id="56d71-192"><strong>Total peer-to-peer audio session minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="56d71-193">Нет</span><span class="sxs-lookup"><span data-stu-id="56d71-193">No</span></span></p></td>
<td><p><span data-ttu-id="56d71-194">Общее количество времени, затраченного на одноранговые сеансы звука.</span><span class="sxs-lookup"><span data-stu-id="56d71-194">Total amount of time spent in peer-to-peer audio sessions.</span></span> <span data-ttu-id="56d71-195">Когда вы щелкните этот элемент, в отчете будет отображено одноранговый голосовой и Видеоотчет в выбранный период времени.</span><span class="sxs-lookup"><span data-stu-id="56d71-195">When you click this item, the report shows you the Peer-to-Peer Voice and Video Report for the selected time period.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="56d71-196"><strong>Среднее число минут для одноранговых сеансов связи</strong></span><span class="sxs-lookup"><span data-stu-id="56d71-196"><strong>Average peer-to-peer audio session minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="56d71-197">Нет</span><span class="sxs-lookup"><span data-stu-id="56d71-197">No</span></span></p></td>
<td><p><span data-ttu-id="56d71-198">Среднее количество времени, затраченного на одноранговые сеансы звука.</span><span class="sxs-lookup"><span data-stu-id="56d71-198">Average amount of time spent in peer-to-peer audio sessions.</span></span> <span data-ttu-id="56d71-199">Вычисляется путем деления общего количества времени для сеанса звука на общее число сеансов голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="56d71-199">Calculated by dividing the total audio session time by the total number of audio sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="56d71-200"><strong>Общее количество одноранговых сеансов видеосвязи</strong></span><span class="sxs-lookup"><span data-stu-id="56d71-200"><strong>Total peer-to-peer video sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="56d71-201">Нет</span><span class="sxs-lookup"><span data-stu-id="56d71-201">No</span></span></p></td>
<td><p><span data-ttu-id="56d71-202">Общее количество одноранговых видеозвонков.</span><span class="sxs-lookup"><span data-stu-id="56d71-202">Total number of peer-to-peer video calls.</span></span> <span data-ttu-id="56d71-203">Обратите внимание, что видеосеансы также учитываются в качестве сеансов голосовой связи: каждый видеосеанс подсчитывается как один видеосеанс и один звуковой сеанс.</span><span class="sxs-lookup"><span data-stu-id="56d71-203">Note that video sessions are also counted as audio sessions: each video session is counted as one video session and one audio session.</span></span> <span data-ttu-id="56d71-204">Когда вы щелкните этот элемент, в отчете будет отображено одноранговый голосовой и Видеоотчет в выбранный период времени.</span><span class="sxs-lookup"><span data-stu-id="56d71-204">When you click this item, the report shows you the Peer-to-Peer Voice and Video Report for the selected time period.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="56d71-205"><strong>Общее количество одноранговых сеансов видеосвязи (мин)</strong></span><span class="sxs-lookup"><span data-stu-id="56d71-205"><strong>Total peer-to-peer video session minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="56d71-206">Нет</span><span class="sxs-lookup"><span data-stu-id="56d71-206">No</span></span></p></td>
<td><p><span data-ttu-id="56d71-207">Общее количество времени, затраченного на одноранговые видеосеансы.</span><span class="sxs-lookup"><span data-stu-id="56d71-207">Total amount of time spent in peer-to-peer video sessions.</span></span> <span data-ttu-id="56d71-208">Когда вы щелкните этот элемент, в отчете будет отображено одноранговый голосовой и Видеоотчет в выбранный период времени.</span><span class="sxs-lookup"><span data-stu-id="56d71-208">When you click this item, the report shows you the Peer-to-Peer Voice and Video Report for the selected time period.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="56d71-209"><strong>Среднее количество минут одноранговых видеосеансов</strong></span><span class="sxs-lookup"><span data-stu-id="56d71-209"><strong>Average peer-to-peer video session minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="56d71-210">Нет</span><span class="sxs-lookup"><span data-stu-id="56d71-210">No</span></span></p></td>
<td><p><span data-ttu-id="56d71-211">Среднее количество времени, затраченного на одноранговые видеосеансы.</span><span class="sxs-lookup"><span data-stu-id="56d71-211">Average amount of time spent in peer-to-peer video sessions.</span></span> <span data-ttu-id="56d71-212">Вычисляется путем деления общего количества времени видеосеанса на общее количество видеосеансов.</span><span class="sxs-lookup"><span data-stu-id="56d71-212">Calculated by dividing the total video session time by the total number of video sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="56d71-213"><strong>Общее количество одноранговых сеансов передачи файлов</strong></span><span class="sxs-lookup"><span data-stu-id="56d71-213"><strong>Total peer-to-peer file transfer sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="56d71-214">Нет</span><span class="sxs-lookup"><span data-stu-id="56d71-214">No</span></span></p></td>
<td><p><span data-ttu-id="56d71-215">Общее количество одноранговых сеансов, в которых включена передача файлов.</span><span class="sxs-lookup"><span data-stu-id="56d71-215">Total number of peer-to-peer sessions that included file transfers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="56d71-216"><strong>Общее количество одноранговых сеансов общего доступа к приложениям</strong></span><span class="sxs-lookup"><span data-stu-id="56d71-216"><strong>Total peer-to-peer application sharing sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="56d71-217">Нет</span><span class="sxs-lookup"><span data-stu-id="56d71-217">No</span></span></p></td>
<td><p><span data-ttu-id="56d71-218">Общее количество одноранговых сеансов, в которых включен общий доступ к приложениям.</span><span class="sxs-lookup"><span data-stu-id="56d71-218">Total number of peer-to-peer sessions that included application sharing.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

