---
title: 'Lync Server 2013: отчет об одноранговом обмене мгновенными сообщениями'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Peer-to-Peer IM Report
ms:assetid: 19ec0145-2398-437b-8989-f780c179b798
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558620(v=OCS.15)
ms:contentKeyID: 48183533
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 16098a1d549c155f9a642f7e68f056f07973217d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48524376"
---
# <a name="peer-to-peer-im-report-in-lync-server-2013"></a><span data-ttu-id="082ce-102">Отчет об одноранговом обмене мгновенными сообщениями в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="082ce-102">Peer-to-Peer IM Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="082ce-103">_**Последнее изменение темы:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="082ce-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="082ce-p101">Отчет об одноранговом обмене мгновенными сообщениями предоставляет сведения о тенденциях, связанных с сеансами однорангового обмена мгновенными сообщениями. Эти сведения разбиты по пулам и типам проверки подлинности. В отчете может отображаться либо общее число сеансов, проведенных за указанный период времени (например, день или час), либо общее число мгновенных сообщений, отправленных за этот период.</span><span class="sxs-lookup"><span data-stu-id="082ce-p101">The Peer-to-Peer IM Report provides trend information about peer-to-peer instant messaging (IM) sessions, broken down by pool and by authentication type. The report can show either the total number of sessions held during the specified time period (for example, day-by-day or hour-by-hour), or it can show the total number of instant messages sent during that time period.</span></span>

<div>

## <a name="accessing-the-peer-to-peer-im-report"></a><span data-ttu-id="082ce-106">Доступ к отчету об одноранговом обмене мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="082ce-106">Accessing the Peer-to-Peer IM Report</span></span>

<span data-ttu-id="082ce-107">Вы можете получить доступ к отчету об одноранговом обмене мгновенными сообщениями, только открыв [сводный отчет по одноранговым действиям в Lync Server 2013](lync-server-2013-peer-to-peer-activity-summary-report.md) и выбрав один из следующих показателей:</span><span class="sxs-lookup"><span data-stu-id="082ce-107">You can access the Peer-to-Peer IM Report only by opening the [Peer-to-Peer Activity Summary Report in Lync Server 2013](lync-server-2013-peer-to-peer-activity-summary-report.md) and then clicking either of the following metrics:</span></span>

  - <span data-ttu-id="082ce-108">Общее число одноранговых сеансов обмена мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="082ce-108">Total peer-to-peer IM sessions</span></span>

  - <span data-ttu-id="082ce-109">Общее число одноранговых мгновенных сообщений</span><span class="sxs-lookup"><span data-stu-id="082ce-109">Total peer-to-peer IM messages</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-im-report"></a><span data-ttu-id="082ce-110">Рекомендации по использованию отчета об одноранговом обмене мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="082ce-110">Making the Best Use of the Peer-to-Peer IM Report</span></span>

<span data-ttu-id="082ce-p102">По умолчанию в отчете об одноранговом обмене мгновенными сообщениями приводится количество сообщений за час (или за день в зависимости от параметров). Однако вы также можете просмотреть почасовое количество сеансов в день. Для этого нажмите кнопку **Показать или скрыть параметры** в правом верхнем углу окна отчетов. После этого вы можете выбрать в раскрывающемся списке **Отчет по** пункт **Число сеансов**.</span><span class="sxs-lookup"><span data-stu-id="082ce-p102">By default, the Peer-to-Peer IM Report shows you the message count per-hour (or day, depending on your settings). However, you can also choose to view the day by sessions per hour. To do that, click **Hide/Show Parameters** in the upper-right corner of the Reports window, and then click **Session Count** from the **Report by** list.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="082ce-114">Фильтры</span><span class="sxs-lookup"><span data-stu-id="082ce-114">Filters</span></span>

<span data-ttu-id="082ce-p103">Фильтры позволяют получить более конкретные наборы возвращаемых данных. В следующей таблице перечислены фильтры, которые можно использовать с отчетом об одноранговом обмене мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="082ce-p103">Filters provide a way for you to return a more finely targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the Peer-to-Peer IM Report.</span></span>

### <a name="peer-to-peer-im-report-filters"></a><span data-ttu-id="082ce-117">Фильтры отчета об одноранговом обмене мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="082ce-117">Peer-to-Peer IM Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="082ce-118">Имя</span><span class="sxs-lookup"><span data-stu-id="082ce-118">Name</span></span></th>
<th><span data-ttu-id="082ce-119">Описание</span><span class="sxs-lookup"><span data-stu-id="082ce-119">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="082ce-120"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="082ce-120"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="082ce-p104">Начальные дата и время временного диапазона. Чтобы просмотреть данные по часам, введите начальные дату и время следующим образом:</span><span class="sxs-lookup"><span data-stu-id="082ce-p104">Start date and time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="082ce-123">7/7/2012 13:00.</span><span class="sxs-lookup"><span data-stu-id="082ce-123">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="082ce-p105">Если не указать время начала, автоматически будет выбрано время 00:00 указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</span><span class="sxs-lookup"><span data-stu-id="082ce-p105">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="082ce-126">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="082ce-126">7/7/2012</span></span></p>
<p><span data-ttu-id="082ce-127">Чтобы просмотреть данные за неделю или месяц, введите любую дату соответствующей недели или месяца (необязательно первую их дату):</span><span class="sxs-lookup"><span data-stu-id="082ce-127">To view by week or by month, enter a date that falls anywhere within the week or month (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="082ce-128">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="082ce-128">7/3/2012</span></span></p>
<p><span data-ttu-id="082ce-129">Неделя всегда начинается с воскресения и заканчивается субботой.</span><span class="sxs-lookup"><span data-stu-id="082ce-129">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="082ce-130"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="082ce-130"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="082ce-p106">Конечные дата и время временного диапазона. Чтобы просмотреть данные по часам, введите конечные дату и время следующим образом:</span><span class="sxs-lookup"><span data-stu-id="082ce-p106">End date and time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="082ce-133">7/7/2012 13:00.</span><span class="sxs-lookup"><span data-stu-id="082ce-133">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="082ce-p107">Если не указать время окончания, автоматически будет выбрано время 00:00 указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</span><span class="sxs-lookup"><span data-stu-id="082ce-p107">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="082ce-136">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="082ce-136">7/7/2012</span></span></p>
<p><span data-ttu-id="082ce-137">Для просмотра по неделям или по месяцам введите дату, выпадающую на любой день недели или месяца, который вы хотите просмотреть (это необязательно должен быть первый день недели или месяца):</span><span class="sxs-lookup"><span data-stu-id="082ce-137">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="082ce-138">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="082ce-138">7/3/2012</span></span></p>
<p><span data-ttu-id="082ce-139">Неделя всегда начинается с воскресения и заканчивается субботой.</span><span class="sxs-lookup"><span data-stu-id="082ce-139">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="082ce-140"><strong>Interval</strong></span><span class="sxs-lookup"><span data-stu-id="082ce-140"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="082ce-p108">Временной интервал. Выберите один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="082ce-p108">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="082ce-143">Ежечасно (может отображаться до 25 часов)</span><span class="sxs-lookup"><span data-stu-id="082ce-143">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="082ce-144">Ежедневно (может отображаться до 31 дня)</span><span class="sxs-lookup"><span data-stu-id="082ce-144">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="082ce-145">Еженедельно (может отображаться до 12 недель)</span><span class="sxs-lookup"><span data-stu-id="082ce-145">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="082ce-146">Ежемесячно (может отображаться до 12 месяцев)</span><span class="sxs-lookup"><span data-stu-id="082ce-146">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="082ce-p109">Если число значений между начальной и конечной датами превышает максимальное допустимое для выбранного интервала, отображается максимальное возможное число значений (с начальной даты). Например, если вы выбрали интервал "Ежедневно" с начальной датой 07.07.2012 и конечной датой 28.02.2012, будут показаны данные для периода с 07.08.2012 12:00 до 07.09.2012 12:00 (то есть для 31 дня).</span><span class="sxs-lookup"><span data-stu-id="082ce-p109">If the start and end dates exceed the maximum number of values allowed for the selected interval then only the maximum number of values (starting from the start date) are displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="082ce-149"><strong>Отчет по</strong></span><span class="sxs-lookup"><span data-stu-id="082ce-149"><strong>Report by</strong></span></span></p></td>
<td><p><span data-ttu-id="082ce-p110">Указывает значения, которые должны использоваться в отчете. Выберите один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="082ce-p110">Indicates the values to be used in the report. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="082ce-152">Число сеансов</span><span class="sxs-lookup"><span data-stu-id="082ce-152">Session count</span></span></p></li>
<li><p><span data-ttu-id="082ce-153">Число сообщений</span><span class="sxs-lookup"><span data-stu-id="082ce-153">Message count</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-im-session-by-pool"></a><span data-ttu-id="082ce-154">Показатели сеансов однорангового обмена мгновенными сообщениями по пулу</span><span class="sxs-lookup"><span data-stu-id="082ce-154">Metrics for Peer-to-Peer IM Session by Pool</span></span>

<span data-ttu-id="082ce-155">В следующей таблице показаны сведения, содержащиеся в отчете об одноранговом обмене мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="082ce-155">The following table lists the information provided in the Peer-to-Peer IM Report.</span></span>

### <a name="metrics-for-peer-to-peer-im-session-by-pool"></a><span data-ttu-id="082ce-156">Показатели сеансов однорангового обмена мгновенными сообщениями по пулу</span><span class="sxs-lookup"><span data-stu-id="082ce-156">Metrics for Peer-to-Peer IM Session by Pool</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="082ce-157">Имя</span><span class="sxs-lookup"><span data-stu-id="082ce-157">Name</span></span></th>
<th><span data-ttu-id="082ce-158">Возможность сортировки по этому показателю</span><span class="sxs-lookup"><span data-stu-id="082ce-158">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="082ce-159">Описание</span><span class="sxs-lookup"><span data-stu-id="082ce-159">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="082ce-160"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="082ce-160"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="082ce-161">Нет</span><span class="sxs-lookup"><span data-stu-id="082ce-161">No</span></span></p></td>
<td><p><span data-ttu-id="082ce-162">Имя пула регистратора или пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="082ce-162">Name of the Registrar pool or Edge Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="082ce-163"><strong>Дата/время</strong></span><span class="sxs-lookup"><span data-stu-id="082ce-163"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="082ce-164">Нет</span><span class="sxs-lookup"><span data-stu-id="082ce-164">No</span></span></p></td>
<td><p><span data-ttu-id="082ce-165">Дата и время, когда состоялся сеанс.</span><span class="sxs-lookup"><span data-stu-id="082ce-165">Date and time that the sessions took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="082ce-166"><strong>Total</strong></span><span class="sxs-lookup"><span data-stu-id="082ce-166"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="082ce-167">Нет</span><span class="sxs-lookup"><span data-stu-id="082ce-167">No</span></span></p></td>
<td><p><span data-ttu-id="082ce-168">Общее число сеансов или сообщений.</span><span class="sxs-lookup"><span data-stu-id="082ce-168">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-im-session-by-authentication-type"></a><span data-ttu-id="082ce-169">Показатели сеансов однорангового обмена мгновенными сообщениями по типу проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="082ce-169">Metrics for Peer-to-Peer IM Session by Authentication Type</span></span>

<span data-ttu-id="082ce-170">В следующей таблице показаны сведения, содержащиеся в отчете об одноранговом обмене мгновенными сообщениями для каждого типа проверки подлинности, используемого участниками однорангового сеанса.</span><span class="sxs-lookup"><span data-stu-id="082ce-170">The following table lists the information provided in the Peer-to-Peer IM Report for each type of authentication used by the participants in a peer-to-peer session.</span></span>

### <a name="metrics-for-peer-to-peer-im-session-by-authentication-type"></a><span data-ttu-id="082ce-171">Показатели сеансов однорангового обмена мгновенными сообщениями по типу проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="082ce-171">Metrics for Peer-to-Peer IM Session by Authentication Type</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="082ce-172">Имя</span><span class="sxs-lookup"><span data-stu-id="082ce-172">Name</span></span></th>
<th><span data-ttu-id="082ce-173">Возможность сортировки по этому показателю</span><span class="sxs-lookup"><span data-stu-id="082ce-173">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="082ce-174">Описание</span><span class="sxs-lookup"><span data-stu-id="082ce-174">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="082ce-175"><strong>Тип проверки подлинности</strong></span><span class="sxs-lookup"><span data-stu-id="082ce-175"><strong>Authentication type</strong></span></span></p></td>
<td><p><span data-ttu-id="082ce-176">Нет</span><span class="sxs-lookup"><span data-stu-id="082ce-176">No</span></span></p></td>
<td><p><span data-ttu-id="082ce-p111">Тип проверки подлинности, используемый участниками сеанса. Как правило, используются следующие значения:</span><span class="sxs-lookup"><span data-stu-id="082ce-p111">Type of authentication used by the session participants. Values are typically one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="082ce-179">Предприятие</span><span class="sxs-lookup"><span data-stu-id="082ce-179">Enterprise</span></span></p></li>
<li><p><span data-ttu-id="082ce-180">Интегрирован</span><span class="sxs-lookup"><span data-stu-id="082ce-180">Federated</span></span></p></li>
<li><p><span data-ttu-id="082ce-181">ИЗОБРАЖЕНИЕ</span><span class="sxs-lookup"><span data-stu-id="082ce-181">PIC</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="082ce-182"><strong>Дата/время</strong></span><span class="sxs-lookup"><span data-stu-id="082ce-182"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="082ce-183">Нет</span><span class="sxs-lookup"><span data-stu-id="082ce-183">No</span></span></p></td>
<td><p><span data-ttu-id="082ce-184">Дата и время, когда состоялся сеанс.</span><span class="sxs-lookup"><span data-stu-id="082ce-184">Date and time that the sessions took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="082ce-185"><strong>Total</strong></span><span class="sxs-lookup"><span data-stu-id="082ce-185"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="082ce-186">Нет</span><span class="sxs-lookup"><span data-stu-id="082ce-186">No</span></span></p></td>
<td><p><span data-ttu-id="082ce-187">Общее число сеансов или сообщений.</span><span class="sxs-lookup"><span data-stu-id="082ce-187">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

