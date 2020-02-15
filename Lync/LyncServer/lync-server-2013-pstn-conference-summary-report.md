---
title: 'Lync Server 2013: сводный отчет по конференциям PSTN'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PSTN Conference Summary Report
ms:assetid: 8e2f0862-4dfa-4c2b-bf8d-ad71419f15d2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615014(v=OCS.15)
ms:contentKeyID: 48184764
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aa902b9e4d53bf0ebbedf835296a371437860095
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043461"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="pstn-conference-summary-report-in-lync-server-2013"></a><span data-ttu-id="ddd10-102">Сводный отчет по конференциям PSTN в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ddd10-102">PSTN Conference Summary Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ddd10-103">_**Последнее изменение темы:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="ddd10-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="ddd10-104">В Microsoft Lync Server 2013 конференция PSTN — это любая конференция, в которой по крайней мере один участник набирается в звуковую часть с помощью телефонной линии PSTN (телефонная сеть общего пользования).</span><span class="sxs-lookup"><span data-stu-id="ddd10-104">In Microsoft Lync Server 2013, a PSTN conference is any conference in which at least one participant dials in to the audio portion by a using a PSTN (public switched telephone network) phone.</span></span> <span data-ttu-id="ddd10-105">(Телефон PSTN — это "стационарный", сотовый телефон или любой другой телефон, который не использует голосовые вызовы через IP.) Несмотря на то, что в отчетах мониторинга эти конференции называются конференциями PSTN, они, возможно, больше часто называются конференциями с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="ddd10-105">(A PSTN phone is a "landline," a cell phone, or any other phone which does not make use of Voice over IP.) Although referred to as PSTN conferences in the Monitoring Reports, these conferences are perhaps more-commonly known as dial-in conferences.</span></span>

<span data-ttu-id="ddd10-p102">Сводный отчет по конференциям ТСОП (PSTN Conference Summary Report) предоставляет сведения о всех конференциях ТСОП, происходивших в вашей организации (т.е. о всех конференциях, хотя бы один участник которых использовал телефонное подключение). В этом отчете содержатся сведения об общем количестве конференций ТСОП, общем количестве участников этих конференций и, что возможно самое важное, об общем количестве пользователей с телефонным подключением (метрика "Total PSTN participants" ("Общее количество участников ТСОП")).</span><span class="sxs-lookup"><span data-stu-id="ddd10-p102">The PSTN Conference Summary Report provides information about all the PSTN conferences held in your organization (that is, all the conferences that had at least one dial-in user). The report includes information about the total number of PSTN conferences, the total number of people who participated in those conferences, and, perhaps, most important, the total number of dial-in users (the Total PSTN participants metric).</span></span>

<div>

## <a name="accessing-the-pstn-conference-summary-report"></a><span data-ttu-id="ddd10-108">Доступ к сводному отчету по конференциям ТСОП</span><span class="sxs-lookup"><span data-stu-id="ddd10-108">Accessing the PSTN Conference Summary Report</span></span>

<span data-ttu-id="ddd10-p103">Сводный отчет по конференциям ТСОП можно вызвать только с домашней страницы отчетов мониторинга. Этот отчет не привязан ни к каким другим отчетам. Следует отметить, что невозможно получить подробные сведения о вызове для конференции ТСОП, в частности потому, что за предоставление этих сведений отвечают конечные точки, а телефоны ТСОП не имеют возможности отслеживать и отправлять подробные сведения о вызове.</span><span class="sxs-lookup"><span data-stu-id="ddd10-p103">The PSTN Conference Summary Report can only be accessed from the Monitoring Reports home page. This report is not linked to any other reports. Note that you cannot retrieve detailed call information for a PSTN conference, in part because individual endpoints are responsible for submitting this information. PSTN phones are not capable of tracking or submitting call detail information.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-pstn-conference-summary-report"></a><span data-ttu-id="ddd10-113">Оптимальное использование сводного отчета по конференциям ТСОП</span><span class="sxs-lookup"><span data-stu-id="ddd10-113">Making the Best Use of the PSTN Conference Summary Report</span></span>

<span data-ttu-id="ddd10-114">Чтобы определить процентное отношение всех конференций, включающих пользователей с телефонным подключением, Сравните значение общей метрики конференций PSTN с общей метрикой конференций, обнаруженной [в сводном отчете по конференциям в Lync Server 2013](lync-server-2013-conference-summary-report.md).</span><span class="sxs-lookup"><span data-stu-id="ddd10-114">To determine the percentage of all your conferences that include dial-in users, compare the value of the Total PSTN conferences metric with the Total conferences metric found on the [Conference Summary Report in Lync Server 2013](lync-server-2013-conference-summary-report.md).</span></span>

<span data-ttu-id="ddd10-p104">Если вы не видите столько конференций ТСОП, сколько предполагали увидеть, имейте в виду, что возможность организации конференции, разрешающей телефонное подключение пользователей, зависит от политики конференц-связи, которая назначена пользователю: если организация конференций ТСОП разрешена очень малому количеству пользователей, то, конечно, вы будете видеть очень мало конференций ТСОП. Чтобы быстро проверить, какие политики конференц-связи разрешают пользователям планировать конференции ТСОП, выполните в командной консоли Lync Server следующую команду:</span><span class="sxs-lookup"><span data-stu-id="ddd10-p104">If you don't see as many PSTN conferences as you might have expected to see, keep in mind that the ability to organize a conference that allows dial-in users depends on the conferencing policy that has been assigned to a user: if very few of your users are allowed to hold PSTN conferences you would obviously see very few PSTN conferences. You can quickly verify which of your conferencing policies (if any) allow users to schedule PSTN conferences by running the following command from within the Lync Server Management Shell:</span></span>

    Get-CsConferencingPolicy | Select-Object Identity, EnableDialInConferencing

<span data-ttu-id="ddd10-117">Вы получите результат, похожий на приведенный ниже.</span><span class="sxs-lookup"><span data-stu-id="ddd10-117">That will return data similar to this:</span></span>

    Identity                                EnableDialInConferencing
    --------                                ------------------------
    Global                                                      True
    site:Redmond                                               False
    site:Dublin                                                False
    Tag:RedmondDialInUsers                                      True
    Tag:DublinDialInUsers                                       True

<span data-ttu-id="ddd10-118">Вы получите результат, похожий на приведенный ниже.</span><span class="sxs-lookup"><span data-stu-id="ddd10-118">That will return data similar to this:</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="ddd10-119">Фильтры</span><span class="sxs-lookup"><span data-stu-id="ddd10-119">Filters</span></span>

<span data-ttu-id="ddd10-p105">Фильтры позволяют получать более адресный набор данных или просматривать полученные данные разными способами. Например, сводный отчет по конференциям ТСОП позволяет выбрать способ группирования данных. В этом случае конференции группируются по часу, дню, неделе или месяцу.</span><span class="sxs-lookup"><span data-stu-id="ddd10-p105">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the PSTN Conference Summary Report enables you to choose how data should be grouped. In this case, conferences are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="ddd10-123">В следующей таблице приведены фильтры, которые можно использовать в сводном отчете по конференциям ТСОП.</span><span class="sxs-lookup"><span data-stu-id="ddd10-123">The following table lists the filters that you can use with the PSTN Conference Summary Report.</span></span>

### <a name="pstn-conference-summary-report-filters"></a><span data-ttu-id="ddd10-124">Фильтры сводного отчета по конференциям ТСОП</span><span class="sxs-lookup"><span data-stu-id="ddd10-124">PSTN Conference Summary Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ddd10-125">Имя</span><span class="sxs-lookup"><span data-stu-id="ddd10-125">Name</span></span></th>
<th><span data-ttu-id="ddd10-126">Описание</span><span class="sxs-lookup"><span data-stu-id="ddd10-126">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ddd10-127"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="ddd10-127"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="ddd10-p106">Дата и время начала диапазона. Чтобы просмотреть данные по часам, введите дату и время начала в следующем формате:</span><span class="sxs-lookup"><span data-stu-id="ddd10-p106">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="ddd10-130">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="ddd10-130">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="ddd10-p107">Если не указать время начала, автоматически будет выбрано время 00:00 указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</span><span class="sxs-lookup"><span data-stu-id="ddd10-p107">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="ddd10-133">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="ddd10-133">7/7/2012</span></span></p>
<p><span data-ttu-id="ddd10-134">Для просмотра по неделям или по месяцам введите дату, выпадающую на любой день недели или месяца, который вы хотите просмотреть (это необязательно должен быть первый день недели или месяца):</span><span class="sxs-lookup"><span data-stu-id="ddd10-134">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="ddd10-135">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="ddd10-135">7/3/2012</span></span></p>
<p><span data-ttu-id="ddd10-136">Недели всегда начинаются с Воскресенья и заканчиваются в Субботу.</span><span class="sxs-lookup"><span data-stu-id="ddd10-136">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ddd10-137"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="ddd10-137"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="ddd10-p108">Дата и время окончания диапазона. Чтобы просмотреть данные по часам, введите дату и время окончания в следующем формате:</span><span class="sxs-lookup"><span data-stu-id="ddd10-p108">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="ddd10-140">7/7/2012 13:00.</span><span class="sxs-lookup"><span data-stu-id="ddd10-140">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="ddd10-p109">Если не указать время окончания, автоматически будет выбрано время 00:00 указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</span><span class="sxs-lookup"><span data-stu-id="ddd10-p109">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="ddd10-143">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="ddd10-143">7/7/2012</span></span></p>
<p><span data-ttu-id="ddd10-144">Для просмотра по неделям или по месяцам введите дату, выпадающую на любой день недели или месяца, который вы хотите просмотреть (это необязательно должен быть первый день недели или месяца):</span><span class="sxs-lookup"><span data-stu-id="ddd10-144">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="ddd10-145">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="ddd10-145">7/3/2012</span></span></p>
<p><span data-ttu-id="ddd10-146">Неделя всегда начинается с воскресения и заканчивается субботой.</span><span class="sxs-lookup"><span data-stu-id="ddd10-146">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ddd10-147"><strong>Interval</strong></span><span class="sxs-lookup"><span data-stu-id="ddd10-147"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="ddd10-p110">Временной интервал. Выберите один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="ddd10-p110">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="ddd10-150">Ежечасно (может отображаться до 25 часов)</span><span class="sxs-lookup"><span data-stu-id="ddd10-150">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="ddd10-151">Ежедневно (может отображаться до 31 дня)</span><span class="sxs-lookup"><span data-stu-id="ddd10-151">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="ddd10-152">Еженедельно (может отображаться до 12 недель)</span><span class="sxs-lookup"><span data-stu-id="ddd10-152">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="ddd10-153">Ежемесячно (может отображаться до 12 месяцев)</span><span class="sxs-lookup"><span data-stu-id="ddd10-153">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="ddd10-p111">Если указаны такие даты начала и конца, что превышается максимально разрешенное количество значений для выбранного интервала, то отображается только максимально допустимое количество значений (начиная с даты начала). Например, если выбран ежедневный интервал с датой начала 07.07.12 и датой конца 28.02.12, то отображаются данные для дней от 07.08.12 24:00 до 07.09.12 24:00 (т. е. данные для 31 дня).</span><span class="sxs-lookup"><span data-stu-id="ddd10-p111">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="ddd10-156">Метрик</span><span class="sxs-lookup"><span data-stu-id="ddd10-156">Metrics</span></span>

<span data-ttu-id="ddd10-157">В следующей таблице приведены сведения, которые предоставляются в сводном отчете по конференциям ТСОП.</span><span class="sxs-lookup"><span data-stu-id="ddd10-157">The following table lists the information in the PSTN Conference Summary Report.</span></span>

### <a name="pstn-conference-summary-report-metrics"></a><span data-ttu-id="ddd10-158">Метрики сводного отчета по конференциям ТСОП</span><span class="sxs-lookup"><span data-stu-id="ddd10-158">PSTN Conference Summary Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ddd10-159">Имя</span><span class="sxs-lookup"><span data-stu-id="ddd10-159">Name</span></span></th>
<th><span data-ttu-id="ddd10-160">Возможность сортировки по этому показателю</span><span class="sxs-lookup"><span data-stu-id="ddd10-160">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="ddd10-161">Описание</span><span class="sxs-lookup"><span data-stu-id="ddd10-161">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ddd10-162"><strong>Каждый час</strong></span><span class="sxs-lookup"><span data-stu-id="ddd10-162"><strong>Hourly</strong></span></span></p>
<p><span data-ttu-id="ddd10-163"><strong>Daily (Ежедневный)</strong></span><span class="sxs-lookup"><span data-stu-id="ddd10-163"><strong>Daily</strong></span></span></p>
<p><span data-ttu-id="ddd10-164"><strong>Weekly (Еженедельный)</strong></span><span class="sxs-lookup"><span data-stu-id="ddd10-164"><strong>Weekly</strong></span></span></p>
<p><span data-ttu-id="ddd10-165"><strong>Monthly Channel</strong></span><span class="sxs-lookup"><span data-stu-id="ddd10-165"><strong>Monthly</strong></span></span></p></td>
<td><p><span data-ttu-id="ddd10-166">Нет</span><span class="sxs-lookup"><span data-stu-id="ddd10-166">No</span></span></p></td>
<td><p><span data-ttu-id="ddd10-p112">Указывает выбранный интервал времени. В применимых случаях можно щелкнуть конкретный интервал времени, чтобы просмотреть подробные сведения для этого интервала. Например, если вы используете ежедневный интервал и щелкнете дату 7/7/2012, то получите почасовую разбивку действий по регистрации пользователей на эту дату.</span><span class="sxs-lookup"><span data-stu-id="ddd10-p112">Indicates the selected time interval. Where applicable, you can click a given time interval to view detailed information for that interval. For example, if you are using the Daily interval and you click 7/7/2012, you see an hourly breakdown of user registration activity for that date.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ddd10-170"><strong>Total PSTN conferences (Общее количество конференций ТСОП)</strong></span><span class="sxs-lookup"><span data-stu-id="ddd10-170"><strong>Total PSTN conferences</strong></span></span></p></td>
<td><p><span data-ttu-id="ddd10-171">Нет</span><span class="sxs-lookup"><span data-stu-id="ddd10-171">No</span></span></p></td>
<td><p><span data-ttu-id="ddd10-172">Общее количество конференций, в которых разрешен телефонный доступ.</span><span class="sxs-lookup"><span data-stu-id="ddd10-172">Total number conferences that allowed dial-in access.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ddd10-173"><strong>Total participants (Общее количество участников)</strong></span><span class="sxs-lookup"><span data-stu-id="ddd10-173"><strong>Total participants</strong></span></span></p></td>
<td><p><span data-ttu-id="ddd10-174">Нет</span><span class="sxs-lookup"><span data-stu-id="ddd10-174">No</span></span></p></td>
<td><p><span data-ttu-id="ddd10-175">Общее количество людей, принявших участие в конференциях с разрешенным телефонными доступом.</span><span class="sxs-lookup"><span data-stu-id="ddd10-175">Total number of people who participated in conferences that allowed dial-in access.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ddd10-176"><strong>Total A/V conference minutes (Общее время в аудио- и видеоконференциях в минутах)</strong></span><span class="sxs-lookup"><span data-stu-id="ddd10-176"><strong>Total A/V conference minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="ddd10-177">Нет</span><span class="sxs-lookup"><span data-stu-id="ddd10-177">No</span></span></p></td>
<td><p><span data-ttu-id="ddd10-178">Общее время аудио- и видеоконференций.</span><span class="sxs-lookup"><span data-stu-id="ddd10-178">Total amount of audio/visual conference time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ddd10-179"><strong>Total A/V conference participant minutes (Общее время в аудио- или видеоконференции в минутах)</strong></span><span class="sxs-lookup"><span data-stu-id="ddd10-179"><strong>Total A/V conference participant minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="ddd10-180">Нет</span><span class="sxs-lookup"><span data-stu-id="ddd10-180">No</span></span></p></td>
<td><p><span data-ttu-id="ddd10-p113">Общее время, затраченное участниками в аудио- или видеоконференции. Например, если один участник потратил пять, а другой — три минуты в одной и той же аудио- или видеоконференции, то общее время участия в аудио- или видеоконференции составит восемь минут.</span><span class="sxs-lookup"><span data-stu-id="ddd10-p113">Total amount of audio/visual participant time. For example, if one participant spent five minutes in an A/V conference and another participant spent three minutes in the same conference, the total A/V conference participant time would be eight minutes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ddd10-183"><strong>Total PSTN participants (Общее количество участников ТСОП)</strong></span><span class="sxs-lookup"><span data-stu-id="ddd10-183"><strong>Total PSTN participants</strong></span></span></p></td>
<td><p><span data-ttu-id="ddd10-184">Нет</span><span class="sxs-lookup"><span data-stu-id="ddd10-184">No</span></span></p></td>
<td><p><span data-ttu-id="ddd10-185">Общее количество пользователей, подключившихся по телефону к конференциям, в которых разрешен телефонный доступ.</span><span class="sxs-lookup"><span data-stu-id="ddd10-185">Total number of users who dialed in to conferences that allowed dial-in access.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ddd10-186"><strong>Total PSTN participant minutes (Общее время участников ТСОП в минутах)</strong></span><span class="sxs-lookup"><span data-stu-id="ddd10-186"><strong>Total PSTN participant minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="ddd10-187">Нет</span><span class="sxs-lookup"><span data-stu-id="ddd10-187">No</span></span></p></td>
<td><p><span data-ttu-id="ddd10-p114">Общее время, затраченное на конференцию участниками с телефонным подключением. Например, если один участник с телефонным подключением провел пять минут, а другой — три минуты в одной и той же конференции, то общее время участников ТСОП составит восемь минут.</span><span class="sxs-lookup"><span data-stu-id="ddd10-p114">Total amount of conference time spent by dial-in users. For example, if one dial-in participant spent five minutes in a conference and another participant spent three minutes in the same conference, the total PSTN participant time would be eight minutes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ddd10-190"><strong>Unique conference organizers (Общее количество уникальных организаторов конференций)</strong></span><span class="sxs-lookup"><span data-stu-id="ddd10-190"><strong>Unique conference organizers</strong></span></span></p></td>
<td><p><span data-ttu-id="ddd10-191">Нет</span><span class="sxs-lookup"><span data-stu-id="ddd10-191">No</span></span></p></td>
<td><p><span data-ttu-id="ddd10-p115">Общее количество пользователей, организовавших хотя бы одну конференцию с разрешенным телефонным доступом. Пользователь, организовавший несколько таких конференций, учитывается как один уникальный организатор, как те, кто организовал только одну конференцию.</span><span class="sxs-lookup"><span data-stu-id="ddd10-p115">Total number of users who organized at least one conference that allowed dial-in access. Users who organized more than one conference are counted as one unique organizer, just like users who only organized a single conference.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

