---
title: 'Lync Server 2013: сводный отчет о конференции по КТСОП'
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
ms.openlocfilehash: f8cd36f651a84b25f7e8163a8cfc40aff5162f90
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724799"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="pstn-conference-summary-report-in-lync-server-2013"></a><span data-ttu-id="a85ed-102">Сводный отчет о конференции по PSTN в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a85ed-102">PSTN Conference Summary Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a85ed-103">_**Тема последнего изменения:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="a85ed-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="a85ed-104">В Microsoft Lync Server 2013 — конференция PSTN — это любая конференция, в которой по крайней мере один абонент звонит на звуковую часть с помощью телефонной сети PSTN (телефонная сеть с открытым коммутируемым подключением).</span><span class="sxs-lookup"><span data-stu-id="a85ed-104">In Microsoft Lync Server 2013, a PSTN conference is any conference in which at least one participant dials in to the audio portion by a using a PSTN (public switched telephone network) phone.</span></span> <span data-ttu-id="a85ed-105">(КОММУТИРУЕМый телефон – это "стационарные", "сотовый телефон" или любой другой телефон, который не использует голосовую связь по IP-адресу.) Несмотря на то, что в отчетах мониторинга используются сети PSTN-конференции, эти конференции, возможно, более часто известны как конференции с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="a85ed-105">(A PSTN phone is a "landline," a cell phone, or any other phone which does not make use of Voice over IP.) Although referred to as PSTN conferences in the Monitoring Reports, these conferences are perhaps more-commonly known as dial-in conferences.</span></span>

<span data-ttu-id="a85ed-p102">Сводный отчет по конференциям ТСОП (PSTN Conference Summary Report) предоставляет сведения обо всех конференциях ТСОП, происходивших в вашей организации (т.е. о всех конференциях, хотя бы один участник которых использовал телефонное подключение). В этом отчете содержатся сведения об общем количестве конференций ТСОП, общем количестве участников этих конференций и, что возможно самое важное, об общем количестве пользователей с телефонным подключением (метрика "Total PSTN participants" ("Общее количество участников ТСОП")).</span><span class="sxs-lookup"><span data-stu-id="a85ed-p102">The PSTN Conference Summary Report provides information about all the PSTN conferences held in your organization (that is, all the conferences that had at least one dial-in user). The report includes information about the total number of PSTN conferences, the total number of people who participated in those conferences, and, perhaps, most important, the total number of dial-in users (the Total PSTN participants metric).</span></span>

<div>

## <a name="accessing-the-pstn-conference-summary-report"></a><span data-ttu-id="a85ed-108">Доступ к сводному отчету по конференциям ТСОП</span><span class="sxs-lookup"><span data-stu-id="a85ed-108">Accessing the PSTN Conference Summary Report</span></span>

<span data-ttu-id="a85ed-p103">Сводный отчет по конференциям ТСОП можно вызвать только с домашней страницы отчетов мониторинга. Этот отчет не привязан ни к каким другим отчетам. Следует отметить, что невозможно получить подробные сведения о вызове для конференции ТСОП, в частности потому, что за предоставление этих сведений отвечают конечные точки, а телефоны ТСОП не имеют возможности отслеживать и отправлять подробные сведения о вызове.</span><span class="sxs-lookup"><span data-stu-id="a85ed-p103">The PSTN Conference Summary Report can only be accessed from the Monitoring Reports home page. This report is not linked to any other reports. Note that you cannot retrieve detailed call information for a PSTN conference, in part because individual endpoints are responsible for submitting this information. PSTN phones are not capable of tracking or submitting call detail information.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-pstn-conference-summary-report"></a><span data-ttu-id="a85ed-113">Оптимальное использование сводного отчета по конференциям ТСОП</span><span class="sxs-lookup"><span data-stu-id="a85ed-113">Making the Best Use of the PSTN Conference Summary Report</span></span>

<span data-ttu-id="a85ed-114">Чтобы определить процентную долю всех ваших конференций, включающих пользователей с телефонным подключением, Сравните значение из общей метрики конференций по КТСОП с общей метрикой конференций [в сводном отчете о конференции в Lync Server 2013](lync-server-2013-conference-summary-report.md).</span><span class="sxs-lookup"><span data-stu-id="a85ed-114">To determine the percentage of all your conferences that include dial-in users, compare the value of the Total PSTN conferences metric with the Total conferences metric found on the [Conference Summary Report in Lync Server 2013](lync-server-2013-conference-summary-report.md).</span></span>

<span data-ttu-id="a85ed-115">If you don't see as many PSTN conferences as you might have expected to see, keep in mind that the ability to organize a conference that allows dial-in users depends on the conferencing policy that has been assigned to a user: if very few of your users are allowed to hold PSTN conferences you would obviously see very few PSTN conferences.</span><span class="sxs-lookup"><span data-stu-id="a85ed-115">If you don't see as many PSTN conferences as you might have expected to see, keep in mind that the ability to organize a conference that allows dial-in users depends on the conferencing policy that has been assigned to a user: if very few of your users are allowed to hold PSTN conferences you would obviously see very few PSTN conferences.</span></span> <span data-ttu-id="a85ed-116">Вы можете быстро проверить, какие из политик конференц-связи (если они есть) разрешают пользователям планировать конференции PSTN, выполнив следующую команду в командной консоли Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a85ed-116">You can quickly verify which of your conferencing policies (if any) allow users to schedule PSTN conferences by running the following command from within the Lync Server Management Shell:</span></span>

    Get-CsConferencingPolicy | Select-Object Identity, EnableDialInConferencing

<span data-ttu-id="a85ed-117">Эти команды возвращают сведения, схожие со следующими:</span><span class="sxs-lookup"><span data-stu-id="a85ed-117">That will return data similar to this:</span></span>

    Identity                                EnableDialInConferencing
    --------                                ------------------------
    Global                                                      True
    site:Redmond                                               False
    site:Dublin                                                False
    Tag:RedmondDialInUsers                                      True
    Tag:DublinDialInUsers                                       True

<span data-ttu-id="a85ed-118">Эти команды возвращают сведения, схожие со следующими:</span><span class="sxs-lookup"><span data-stu-id="a85ed-118">That will return data similar to this:</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="a85ed-119">Фильтры</span><span class="sxs-lookup"><span data-stu-id="a85ed-119">Filters</span></span>

<span data-ttu-id="a85ed-120">Фильтры предоставляют способ возврата более точного набора данных в соответствии с заданными критериями или просмотра возвращенных данных другими способами.</span><span class="sxs-lookup"><span data-stu-id="a85ed-120">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="a85ed-121">Например, сводный отчет по конференциям ТСОП позволяет выбрать способ группирования данных.</span><span class="sxs-lookup"><span data-stu-id="a85ed-121">For example, the PSTN Conference Summary Report enables you to choose how data should be grouped.</span></span> <span data-ttu-id="a85ed-122">В этом случае конференции группируются по часу, дню, неделе или месяцу.</span><span class="sxs-lookup"><span data-stu-id="a85ed-122">In this case, conferences are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="a85ed-123">В следующей таблице приведены фильтры, которые можно использовать в сводном отчете по конференциям ТСОП.</span><span class="sxs-lookup"><span data-stu-id="a85ed-123">The following table lists the filters that you can use with the PSTN Conference Summary Report.</span></span>

### <a name="pstn-conference-summary-report-filters"></a><span data-ttu-id="a85ed-124">Фильтры сводного отчета по конференциям ТСОП</span><span class="sxs-lookup"><span data-stu-id="a85ed-124">PSTN Conference Summary Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a85ed-125">Имя</span><span class="sxs-lookup"><span data-stu-id="a85ed-125">Name</span></span></th>
<th><span data-ttu-id="a85ed-126">Описание</span><span class="sxs-lookup"><span data-stu-id="a85ed-126">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a85ed-127"><strong>От</strong></span><span class="sxs-lookup"><span data-stu-id="a85ed-127"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="a85ed-p106">Начальные дата/время для временного диапазона. Чтобы просмотреть данные по часам, введите начальные дату и время следующим образом:</span><span class="sxs-lookup"><span data-stu-id="a85ed-p106">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="a85ed-130">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="a85ed-130">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="a85ed-p107">Если вы не вводите начальное время, отчет автоматически начинается с 12:00 AM указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</span><span class="sxs-lookup"><span data-stu-id="a85ed-p107">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="a85ed-133">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="a85ed-133">7/7/2012</span></span></p>
<p><span data-ttu-id="a85ed-134">Чтобы просмотреть данные за неделю или месяц, введите дату, выпадающую на любое время в рамках недели или месяца, которые вы хотите просмотреть (вам не требуется вводить первый день недели или месяца):</span><span class="sxs-lookup"><span data-stu-id="a85ed-134">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="a85ed-135">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="a85ed-135">7/3/2012</span></span></p>
<p><span data-ttu-id="a85ed-136">Недели всегда отсчитываются с воскресенья по субботу.</span><span class="sxs-lookup"><span data-stu-id="a85ed-136">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a85ed-137"><strong>До</strong></span><span class="sxs-lookup"><span data-stu-id="a85ed-137"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="a85ed-p108">Конечные дата/время для временного диапазона. Чтобы просмотреть данные по часам, введите конечные дату и время следующим образом:</span><span class="sxs-lookup"><span data-stu-id="a85ed-p108">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="a85ed-140">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="a85ed-140">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="a85ed-p109">Если вы не вводите конечное время, отчет автоматически заканчивается в 12:00 AM указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</span><span class="sxs-lookup"><span data-stu-id="a85ed-p109">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="a85ed-143">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="a85ed-143">7/7/2012</span></span></p>
<p><span data-ttu-id="a85ed-144">Чтобы просмотреть данные за неделю или месяц, введите дату, выпадающую на любое время в рамках недели или месяца, которые вы хотите просмотреть (вам не требуется вводить первый день недели или месяца):</span><span class="sxs-lookup"><span data-stu-id="a85ed-144">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="a85ed-145">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="a85ed-145">7/3/2012</span></span></p>
<p><span data-ttu-id="a85ed-146">Недели всегда отсчитываются с воскресенья по субботу.</span><span class="sxs-lookup"><span data-stu-id="a85ed-146">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a85ed-147"><strong>Интервал</strong></span><span class="sxs-lookup"><span data-stu-id="a85ed-147"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="a85ed-p110">Временной интервал. Выберите одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="a85ed-p110">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="a85ed-150">Ежечасно (можно отобразить не более 25 часов)</span><span class="sxs-lookup"><span data-stu-id="a85ed-150">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="a85ed-151">Ежедневно (можно отобразить не более 31 дня)</span><span class="sxs-lookup"><span data-stu-id="a85ed-151">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="a85ed-152">Еженедельно (можно отобразить не более 12 недель)</span><span class="sxs-lookup"><span data-stu-id="a85ed-152">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="a85ed-153">Ежемесячно (можно отобразить не более 12 месяцев)</span><span class="sxs-lookup"><span data-stu-id="a85ed-153">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="a85ed-154">Если количество значений между начальной и конечной датами превышает максимально допустимое для выбранного интервала, отображается максимальное возможное количество значений (от начальной даты и далее).</span><span class="sxs-lookup"><span data-stu-id="a85ed-154">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed.</span></span> <span data-ttu-id="a85ed-155">Например, если выбрать ежедневный интервал с датой начала 7/7/2012 и датой окончания 2/28/2012, данные будут выводиться для дней 8/7/2012 12:00 – 9/7/2012 12:00 AM (то есть, всего за 31 дня).</span><span class="sxs-lookup"><span data-stu-id="a85ed-155">For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="a85ed-156">Показатели</span><span class="sxs-lookup"><span data-stu-id="a85ed-156">Metrics</span></span>

<span data-ttu-id="a85ed-157">В следующей таблице приведены сведения, которые предоставляются в сводном отчете по конференциям ТСОП.</span><span class="sxs-lookup"><span data-stu-id="a85ed-157">The following table lists the information in the PSTN Conference Summary Report.</span></span>

### <a name="pstn-conference-summary-report-metrics"></a><span data-ttu-id="a85ed-158">Метрики сводного отчета по конференциям ТСОП</span><span class="sxs-lookup"><span data-stu-id="a85ed-158">PSTN Conference Summary Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a85ed-159">Имя</span><span class="sxs-lookup"><span data-stu-id="a85ed-159">Name</span></span></th>
<th><span data-ttu-id="a85ed-160">Поддержка сортировки</span><span class="sxs-lookup"><span data-stu-id="a85ed-160">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="a85ed-161">Описание</span><span class="sxs-lookup"><span data-stu-id="a85ed-161">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a85ed-162"><strong>Ежечасно</strong></span><span class="sxs-lookup"><span data-stu-id="a85ed-162"><strong>Hourly</strong></span></span></p>
<p><span data-ttu-id="a85ed-163"><strong>Ежедневно</strong></span><span class="sxs-lookup"><span data-stu-id="a85ed-163"><strong>Daily</strong></span></span></p>
<p><span data-ttu-id="a85ed-164"><strong>Еженедельно</strong></span><span class="sxs-lookup"><span data-stu-id="a85ed-164"><strong>Weekly</strong></span></span></p>
<p><span data-ttu-id="a85ed-165"><strong>Ежемесячно</strong></span><span class="sxs-lookup"><span data-stu-id="a85ed-165"><strong>Monthly</strong></span></span></p></td>
<td><p><span data-ttu-id="a85ed-166">Нет</span><span class="sxs-lookup"><span data-stu-id="a85ed-166">No</span></span></p></td>
<td><p><span data-ttu-id="a85ed-167">Указывает выбранный интервал времени.</span><span class="sxs-lookup"><span data-stu-id="a85ed-167">Indicates the selected time interval.</span></span> <span data-ttu-id="a85ed-168">В применимых случаях можно щелкнуть конкретный интервал времени, чтобы просмотреть подробные сведения для этого интервала.</span><span class="sxs-lookup"><span data-stu-id="a85ed-168">Where applicable, you can click a given time interval to view detailed information for that interval.</span></span> <span data-ttu-id="a85ed-169">Например, если вы используете ежедневный интервал и нажимайте 7/7/2012, появится Почасовая подразделение действия регистрации пользователя для этой даты.</span><span class="sxs-lookup"><span data-stu-id="a85ed-169">For example, if you are using the Daily interval and you click 7/7/2012, you see an hourly breakdown of user registration activity for that date.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a85ed-170"><strong>Общее количество конференций ТСОП</strong></span><span class="sxs-lookup"><span data-stu-id="a85ed-170"><strong>Total PSTN conferences</strong></span></span></p></td>
<td><p><span data-ttu-id="a85ed-171">Нет</span><span class="sxs-lookup"><span data-stu-id="a85ed-171">No</span></span></p></td>
<td><p><span data-ttu-id="a85ed-172">Общее количество конференций, в которых разрешен телефонный доступ.</span><span class="sxs-lookup"><span data-stu-id="a85ed-172">Total number conferences that allowed dial-in access.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a85ed-173"><strong>Общее количество участников</strong></span><span class="sxs-lookup"><span data-stu-id="a85ed-173"><strong>Total participants</strong></span></span></p></td>
<td><p><span data-ttu-id="a85ed-174">Нет</span><span class="sxs-lookup"><span data-stu-id="a85ed-174">No</span></span></p></td>
<td><p><span data-ttu-id="a85ed-175">Общее количество людей, принявших участие в конференциях с разрешенным телефонным доступом.</span><span class="sxs-lookup"><span data-stu-id="a85ed-175">Total number of people who participated in conferences that allowed dial-in access.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a85ed-176"><strong>Общее время аудио- и видеоконференций (в минутах)</strong></span><span class="sxs-lookup"><span data-stu-id="a85ed-176"><strong>Total A/V conference minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="a85ed-177">Нет</span><span class="sxs-lookup"><span data-stu-id="a85ed-177">No</span></span></p></td>
<td><p><span data-ttu-id="a85ed-178">Общее время аудио- и видеоконференций.</span><span class="sxs-lookup"><span data-stu-id="a85ed-178">Total amount of audio/visual conference time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a85ed-179"><strong>Общее время участия в аудио- или видеоконференции (в минутах)</strong></span><span class="sxs-lookup"><span data-stu-id="a85ed-179"><strong>Total A/V conference participant minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="a85ed-180">Нет</span><span class="sxs-lookup"><span data-stu-id="a85ed-180">No</span></span></p></td>
<td><p><span data-ttu-id="a85ed-p113">Общее время, затраченное участниками в аудио- или видеоконференции. Например, если один участник потратил пять, а другой – три минуты в одной и той же аудио- или видеоконференции, то общее время участия в аудио- или видеоконференции составит восемь минут.</span><span class="sxs-lookup"><span data-stu-id="a85ed-p113">Total amount of audio/visual participant time. For example, if one participant spent five minutes in an A/V conference and another participant spent three minutes in the same conference, the total A/V conference participant time would be eight minutes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a85ed-183"><strong>Общее количество участников ТСОП</strong></span><span class="sxs-lookup"><span data-stu-id="a85ed-183"><strong>Total PSTN participants</strong></span></span></p></td>
<td><p><span data-ttu-id="a85ed-184">Нет</span><span class="sxs-lookup"><span data-stu-id="a85ed-184">No</span></span></p></td>
<td><p><span data-ttu-id="a85ed-185">Общее количество пользователей, подключившихся по телефону к конференциям, в которых разрешен телефонный доступ.</span><span class="sxs-lookup"><span data-stu-id="a85ed-185">Total number of users who dialed in to conferences that allowed dial-in access.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a85ed-186"><strong>Общее время участников ТСОП в минутах</strong></span><span class="sxs-lookup"><span data-stu-id="a85ed-186"><strong>Total PSTN participant minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="a85ed-187">Нет</span><span class="sxs-lookup"><span data-stu-id="a85ed-187">No</span></span></p></td>
<td><p><span data-ttu-id="a85ed-p114">Общее время, затраченное на конференцию участниками с телефонным подключением. Например, если один участник с телефонным подключением провел пять минут, а другой – три минуты в одной и той же конференции, то общее время участников ТСОП составит восемь минут.</span><span class="sxs-lookup"><span data-stu-id="a85ed-p114">Total amount of conference time spent by dial-in users. For example, if one dial-in participant spent five minutes in a conference and another participant spent three minutes in the same conference, the total PSTN participant time would be eight minutes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a85ed-190"><strong>Общее количество уникальных организаторов конференций</strong></span><span class="sxs-lookup"><span data-stu-id="a85ed-190"><strong>Unique conference organizers</strong></span></span></p></td>
<td><p><span data-ttu-id="a85ed-191">Нет</span><span class="sxs-lookup"><span data-stu-id="a85ed-191">No</span></span></p></td>
<td><p><span data-ttu-id="a85ed-p115">Общее количество пользователей, организовавших хотя бы одну конференцию с разрешенным телефонным доступом. Пользователь, организовавший несколько таких конференций, учитывается как один уникальный организатор, как те, кто организовал только одну конференцию.</span><span class="sxs-lookup"><span data-stu-id="a85ed-p115">Total number of users who organized at least one conference that allowed dial-in access. Users who organized more than one conference are counted as one unique organizer, just like users who only organized a single conference.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

