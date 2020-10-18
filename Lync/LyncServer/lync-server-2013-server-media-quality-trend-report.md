---
title: 'Lync Server 2013: отчет по тенденциям качества мультимедиа на серверах'
description: 'Lync Server 2013: отчет по тенденциям качества мультимедиа на сервере.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server Media Quality Trend Report
ms:assetid: 8a51fd13-1487-4632-b5ec-f7ae2abe8ed4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205071(v=OCS.15)
ms:contentKeyID: 48184760
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7ac2482b967aab230c5522c2b6a76e10ced28e7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578143"
---
# <a name="server-media-quality-trend-report-in-lync-server-2013"></a><span data-ttu-id="7c4c1-103">Отчет по тенденциям качества мультимедиа на сервере в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7c4c1-103">Server Media Quality Trend Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7c4c1-104">_**Последнее изменение темы:** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="7c4c1-104">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="7c4c1-p101">Отчет по тенденциям качества мультимедиа на серверах (Server Media Quality Trend Report) позволяет графически сравнить до 5 серверов по таким показателям качества взаимодействия, как интенсивность вызовов, процент звонков низкого качества, потеря пакетов и дрожание. Это облегчает идентификацию неэффективных серверов, недостаточно интенсивно используемых серверов и чрезмерно используемых серверов.</span><span class="sxs-lookup"><span data-stu-id="7c4c1-p101">The Server Media Quality Trend Report provides a way for you to graphically compare up to 5 servers on Quality of Experience metrics such as call volume, poor call percentage, packet loss, and jitter. This makes it easier to do such things as identify servers that are performing poorly, identify servers that are underutilized, or identify servers that are being overused.</span></span>

<div>

## <a name="accessing-the-server-media-quality-trend-report"></a><span data-ttu-id="7c4c1-107">Доступ к отчету по тенденциям качества мультимедиа на серверах</span><span class="sxs-lookup"><span data-stu-id="7c4c1-107">Accessing the Server Media Quality Trend Report</span></span>

<span data-ttu-id="7c4c1-108">Доступ к отчету по тенденциям качества мультимедиа на серверах можно получить из одного из следующих отчетов:</span><span class="sxs-lookup"><span data-stu-id="7c4c1-108">The Server Media Quality Trend Report can be accessed from either one of the following report:</span></span>

  - <span data-ttu-id="7c4c1-109">[Отчет о производительности сервера в Lync server 2013](lync-server-2013-server-performance-report.md) (щелкнув метрику тренда)</span><span class="sxs-lookup"><span data-stu-id="7c4c1-109">[Server Performance Report in Lync Server 2013](lync-server-2013-server-performance-report.md) (by clicking the Trend metric)</span></span>

  - <span data-ttu-id="7c4c1-110">[Отчет о вызове в Lync server 2013](lync-server-2013-call-detail-report.md) (щелкните метрику пограничного сервера аудио-и видеоданных.</span><span class="sxs-lookup"><span data-stu-id="7c4c1-110">[Call Detail Report in Lync Server 2013](lync-server-2013-call-detail-report.md) (by clicking the A/V edge server metric.</span></span> <span data-ttu-id="7c4c1-111">Если вызывающий абонент или вызываемый абонент является сервером, вы также можете обратиться к отчету по тенденциям качества мультимедиа сервера, щелкнув имя конечной точки.)</span><span class="sxs-lookup"><span data-stu-id="7c4c1-111">If the caller or callee is a server, you can also reach the Server Quality Media Trend Report by clicking the endpoint name.)</span></span>

</div>

<div>

## <a name="making-the-best-use-of-server-media-quality-trend-report"></a><span data-ttu-id="7c4c1-112">Оптимальное использование отчета по тенденциям качества мультимедиа на серверах</span><span class="sxs-lookup"><span data-stu-id="7c4c1-112">Making the Best Use of Server Media Quality Trend Report</span></span>

<span data-ttu-id="7c4c1-113">При выборе показателя тренда в [отчете о производительности сервера в Lync server 2013](lync-server-2013-server-performance-report.md) для определенного сервера откроется отчет по тенденциям качества мультимедиа на сервере.</span><span class="sxs-lookup"><span data-stu-id="7c4c1-113">When you click the Trend metric on the [Server Performance Report in Lync Server 2013](lync-server-2013-server-performance-report.md) for a specific server, the Server Media Quality Trend Report will open.</span></span> <span data-ttu-id="7c4c1-114">Однако вы увидите пустой отчет; сервер, выбранный в отчете по производительности сервера, не будет отображаться на экране.</span><span class="sxs-lookup"><span data-stu-id="7c4c1-114">However, you will see only a blank instance of that report; the server you selected on the Server Performance Report will not be displayed onscreen.</span></span> <span data-ttu-id="7c4c1-115">Вам придется выбрать этот сервер из раскрывающегося списка серверов.</span><span class="sxs-lookup"><span data-stu-id="7c4c1-115">Instead, you will need to select that server from the Servers dropdown.</span></span> <span data-ttu-id="7c4c1-116">Обратите внимание, что в этом списке также имеется параметр "Select All" ("Выбрать все").</span><span class="sxs-lookup"><span data-stu-id="7c4c1-116">Note, too that the Servers dropdown includes a Select All option.</span></span> <span data-ttu-id="7c4c1-117">Этот параметр не будет работать при наличии более 5 серверов; отчет по тенденциям качества мультимедиа на серверах может отображать данные не более чем для 5 серверов одновременно.</span><span class="sxs-lookup"><span data-stu-id="7c4c1-117">This option will not work if you have more than 5 servers; the Server Media Quality Trend Report can only display data for a maximum of 5 servers at a time.</span></span>

<span data-ttu-id="7c4c1-118">На графиках, отображаемых в отчете по тенденциям качества мультимедиа на сервере, точки с меткой "Громкость" и "процент звонков с плохим процентом" — гиперссылками; щелкнув точку на графике, вы откроете экземпляр отчета по [списку обзвона в Lync Server 2013, в](lync-server-2013-call-list-report.md) котором отображаются все вызовы (или неудачные звонки) за указанный период времени.</span><span class="sxs-lookup"><span data-stu-id="7c4c1-118">On the graphs displayed by the Server Media Quality Trend Report, the points labeled Call Volume and Poor Call Percentage are hotlinks; clicking a point on the graph will open an instance of the [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) showing the total calls (or poor calls) for the specified time period.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="7c4c1-119">Фильтры</span><span class="sxs-lookup"><span data-stu-id="7c4c1-119">Filters</span></span>

<span data-ttu-id="7c4c1-p104">Фильтры позволяют получать более адресный набор данных или просматривать полученные данные разными способами. В следующей таблице приведены фильтры, которые можно использовать в отчете по тенденциям качества мультимедиа на серверах.</span><span class="sxs-lookup"><span data-stu-id="7c4c1-p104">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the Server Media Quality Trend Report.</span></span>

### <a name="server-media-quality-trend-report-filters"></a><span data-ttu-id="7c4c1-122">Фильтры отчета по тенденциям качества мультимедиа на серверах</span><span class="sxs-lookup"><span data-stu-id="7c4c1-122">Server Media Quality Trend Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7c4c1-123">Имя</span><span class="sxs-lookup"><span data-stu-id="7c4c1-123">Name</span></span></th>
<th><span data-ttu-id="7c4c1-124">Описание</span><span class="sxs-lookup"><span data-stu-id="7c4c1-124">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7c4c1-125"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="7c4c1-125"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="7c4c1-p105">Дата и время начала диапазона. Чтобы просмотреть данные по часам, введите дату и время начала в следующем формате:</span><span class="sxs-lookup"><span data-stu-id="7c4c1-p105">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="7c4c1-128">7/7/2012 13:00.</span><span class="sxs-lookup"><span data-stu-id="7c4c1-128">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="7c4c1-p106">Если не указать время начала, автоматически будет выбрано время 00:00 указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</span><span class="sxs-lookup"><span data-stu-id="7c4c1-p106">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="7c4c1-131">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="7c4c1-131">7/7/2012</span></span></p>
<p><span data-ttu-id="7c4c1-132">Для просмотра по неделям или по месяцам введите дату, выпадающую на любой день недели или месяца, который вы хотите просмотреть (это необязательно должен быть первый день недели или месяца):</span><span class="sxs-lookup"><span data-stu-id="7c4c1-132">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="7c4c1-133">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="7c4c1-133">7/3/2012</span></span></p>
<p><span data-ttu-id="7c4c1-134">Неделя всегда начинается с воскресения и заканчивается субботой.</span><span class="sxs-lookup"><span data-stu-id="7c4c1-134">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c4c1-135"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="7c4c1-135"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="7c4c1-p107">Дата и время окончания диапазона. Чтобы просмотреть данные по часам, введите дату и время окончания в следующем формате:</span><span class="sxs-lookup"><span data-stu-id="7c4c1-p107">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="7c4c1-138">7/7/2012 13:00.</span><span class="sxs-lookup"><span data-stu-id="7c4c1-138">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="7c4c1-p108">Если не указать время окончания, автоматически будет выбрано время 00:00 указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</span><span class="sxs-lookup"><span data-stu-id="7c4c1-p108">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="7c4c1-141">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="7c4c1-141">7/7/2012</span></span></p>
<p><span data-ttu-id="7c4c1-142">Для просмотра по неделям или по месяцам введите дату, выпадающую на любой день недели или месяца, который вы хотите просмотреть (это необязательно должен быть первый день недели или месяца):</span><span class="sxs-lookup"><span data-stu-id="7c4c1-142">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="7c4c1-143">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="7c4c1-143">7/3/2012</span></span></p>
<p><span data-ttu-id="7c4c1-144">Неделя всегда начинается с воскресения и заканчивается субботой.</span><span class="sxs-lookup"><span data-stu-id="7c4c1-144">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c4c1-145"><strong>Interval</strong></span><span class="sxs-lookup"><span data-stu-id="7c4c1-145"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="7c4c1-p109">Временной интервал. Выберите один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="7c4c1-p109">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="7c4c1-148">Ежечасно (может отображаться до 25 часов)</span><span class="sxs-lookup"><span data-stu-id="7c4c1-148">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="7c4c1-149">Ежедневно (может отображаться до 31 дня)</span><span class="sxs-lookup"><span data-stu-id="7c4c1-149">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="7c4c1-150">Weekly (Еженедельно) — может отображаться не более 12 недель.</span><span class="sxs-lookup"><span data-stu-id="7c4c1-150">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="7c4c1-p110">Если указаны такие даты начала и конца, что превышается максимально разрешенное количество значений для выбранного интервала, то отображается только максимально допустимое количество значений (начиная с даты начала). Например, если выбран ежедневный интервал с датой начала 07.07.12 и датой конца 28.02.12, то отображаются данные для дней от 07.08.12 24:00 до 07.09.12 24:00 (т. е. данные для 31 дня).</span><span class="sxs-lookup"><span data-stu-id="7c4c1-p110">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 8/7/2012 and an end date of 9/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c4c1-153"><strong>Server type (Тип сервера)</strong></span><span class="sxs-lookup"><span data-stu-id="7c4c1-153"><strong>Server type</strong></span></span></p></td>
<td><p><span data-ttu-id="7c4c1-p111">Тип сервера, участвующего в вызове. Допускаются следующие значения:</span><span class="sxs-lookup"><span data-stu-id="7c4c1-p111">Type of server involved in the call. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="7c4c1-156">Mediation Server (Сервер-посредник);</span><span class="sxs-lookup"><span data-stu-id="7c4c1-156">Mediation Server</span></span></p></li>
<li><p><span data-ttu-id="7c4c1-157">A/V Conferencing Server (Сервер аудио- и видеоконференций);</span><span class="sxs-lookup"><span data-stu-id="7c4c1-157">A/V Conferencing Server</span></span></p></li>
<li><p><span data-ttu-id="7c4c1-158">A/V Edge Server (Пограничный сервер аудио- и видеоданных);</span><span class="sxs-lookup"><span data-stu-id="7c4c1-158">A/V Edge Server</span></span></p></li>
<li><p><span data-ttu-id="7c4c1-159">Gateway (Mediation Server) (Шлюз (сервер-посредник));</span><span class="sxs-lookup"><span data-stu-id="7c4c1-159">Gateway (Mediation Server)</span></span></p></li>
<li><p><span data-ttu-id="7c4c1-160">Gateway (Mediation Server Bypass) (Шлюз (обход сервера-посредника));</span><span class="sxs-lookup"><span data-stu-id="7c4c1-160">Gateway (Mediation Server Bypass)</span></span></p></li>
<li><p><span data-ttu-id="7c4c1-161">AS Conferencing Server (Сервер конференций AS).</span><span class="sxs-lookup"><span data-stu-id="7c4c1-161">AS Conferencing Server</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c4c1-162"><strong>Servers</strong></span><span class="sxs-lookup"><span data-stu-id="7c4c1-162"><strong>Servers</strong></span></span></p></td>
<td><p><span data-ttu-id="7c4c1-p112">Имя сервера, участвующего в сеансе; этот раскрывающийся список заполняется автоматически в зависимости от значения фильтра "Server type" ("Тип сервера"). При составлении отчета вы можете выбрать вплоть до 5 разных серверов.</span><span class="sxs-lookup"><span data-stu-id="7c4c1-p112">Name of the server involved in the session; this dropdown list is automatically populated for you based on the value of the Server type filter. You can select up to 5 different servers when compiling a report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c4c1-165"><strong>Access type (Тип доступа)</strong></span><span class="sxs-lookup"><span data-stu-id="7c4c1-165"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="7c4c1-p113">Указывает, вошел ли участник во внутреннюю сеть, или подключался из внешней сети. Допускаются следующие значения:</span><span class="sxs-lookup"><span data-stu-id="7c4c1-p113">Indicates whether the participant was logged on to the internal network or from the external network. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="7c4c1-168">Ко</span><span class="sxs-lookup"><span data-stu-id="7c4c1-168">[All]</span></span></p></li>
<li><p><span data-ttu-id="7c4c1-169">Внутренний</span><span class="sxs-lookup"><span data-stu-id="7c4c1-169">Internal</span></span></p></li>
<li><p><span data-ttu-id="7c4c1-170">Внешний</span><span class="sxs-lookup"><span data-stu-id="7c4c1-170">External</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c4c1-171"><strong>Network type (Тип сети))</strong></span><span class="sxs-lookup"><span data-stu-id="7c4c1-171"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="7c4c1-p114">Указывает тип сети, к которой подключался участник. Допускаются следующие значения:</span><span class="sxs-lookup"><span data-stu-id="7c4c1-p114">Indicates the type of network the participant was connected to. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="7c4c1-174">Ко</span><span class="sxs-lookup"><span data-stu-id="7c4c1-174">[All]</span></span></p></li>
<li><p><span data-ttu-id="7c4c1-175">Политик</span><span class="sxs-lookup"><span data-stu-id="7c4c1-175">Wired</span></span></p></li>
<li><p><span data-ttu-id="7c4c1-176">Инфракрас</span><span class="sxs-lookup"><span data-stu-id="7c4c1-176">Wireless</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c4c1-177"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="7c4c1-177"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="7c4c1-p115">Указывает, использовал ли внешний участник подключение через виртуальную частную сеть (VPN) во время сеанса. Допускаются следующие значения:</span><span class="sxs-lookup"><span data-stu-id="7c4c1-p115">Indicates whether an external participant was using a virtual private network (VPN) connection during the session. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="7c4c1-180">Ко</span><span class="sxs-lookup"><span data-stu-id="7c4c1-180">[All]</span></span></p></li>
<li><p><span data-ttu-id="7c4c1-181">VPN</span><span class="sxs-lookup"><span data-stu-id="7c4c1-181">VPN</span></span></p></li>
<li><p><span data-ttu-id="7c4c1-182">Не VPN</span><span class="sxs-lookup"><span data-stu-id="7c4c1-182">Non-VPN</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="7c4c1-183">Метрики</span><span class="sxs-lookup"><span data-stu-id="7c4c1-183">Metrics</span></span>

<span data-ttu-id="7c4c1-184">В следующей таблице приведены виды сведений, предоставляемые в отчете по тенденциям качества мультимедиа на серверах.</span><span class="sxs-lookup"><span data-stu-id="7c4c1-184">The following table lists the information provided in the Server Media Quality Trend Report.</span></span>

### <a name="server-media-quality-trend-report-metrics"></a><span data-ttu-id="7c4c1-185">Метрики отчета по тенденциям качества мультимедиа на серверах</span><span class="sxs-lookup"><span data-stu-id="7c4c1-185">Server Media Quality Trend Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7c4c1-186">Имя</span><span class="sxs-lookup"><span data-stu-id="7c4c1-186">Name</span></span></th>
<th><span data-ttu-id="7c4c1-187">Возможность сортировки по этому показателю</span><span class="sxs-lookup"><span data-stu-id="7c4c1-187">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="7c4c1-188">Описание</span><span class="sxs-lookup"><span data-stu-id="7c4c1-188">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7c4c1-189"><strong>Call volume (Интенсивность вызовов)</strong></span><span class="sxs-lookup"><span data-stu-id="7c4c1-189"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="7c4c1-190">Нет</span><span class="sxs-lookup"><span data-stu-id="7c4c1-190">No</span></span></p></td>
<td><p><span data-ttu-id="7c4c1-191">Общее количество вызовов.</span><span class="sxs-lookup"><span data-stu-id="7c4c1-191">Total number of calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c4c1-192"><strong>Degradation (MOS) (Снижение (MOS))</strong></span><span class="sxs-lookup"><span data-stu-id="7c4c1-192"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="7c4c1-193">Нет</span><span class="sxs-lookup"><span data-stu-id="7c4c1-193">No</span></span></p></td>
<td><p><span data-ttu-id="7c4c1-194">Средняя величина снижения экспертной оценки разборчивости речи (MOS) во время вызова.</span><span class="sxs-lookup"><span data-stu-id="7c4c1-194">Average amount of MOS (mean option score) degradation experienced during a call.</span></span> <span data-ttu-id="7c4c1-195">Значение снижения может быть в диапазоне от 0.0 до 5.0; значение не выше 0.5 является приемлемым уровнем снижения.</span><span class="sxs-lookup"><span data-stu-id="7c4c1-195">Degradation values can range from a low of 0.0 to a high of 5.0; a value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="7c4c1-196">Традиционно средние экспертные оценки разборчивости речи вычислялись по оценкам пользователей качества вызова по шкале от 1 до 5.</span><span class="sxs-lookup"><span data-stu-id="7c4c1-196">Historically, mean options scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="7c4c1-197">Lync Server использует набор алгоритмов для прогнозирования того, как пользователи будут оценены при вызове.</span><span class="sxs-lookup"><span data-stu-id="7c4c1-197">Lync Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="7c4c1-p117">Высокие значения снижения могут быть вызваны перегруженностью, нехваткой пропускной способности, перегруженностью или помехами в беспроводной сети, а также перегруженностью сервера мультимедиа или конечной точки. Высокие значения могут привести к искажению или потере звука.</span><span class="sxs-lookup"><span data-stu-id="7c4c1-p117">High degradation values can be caused by congestion; lack of bandwidth; wireless congestion or interference, or an overloaded media server or endpoint. High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c4c1-200"><strong>Poor call percentage (Процент звонков низкого качества)</strong></span><span class="sxs-lookup"><span data-stu-id="7c4c1-200"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="7c4c1-201">Нет</span><span class="sxs-lookup"><span data-stu-id="7c4c1-201">No</span></span></p></td>
<td><p><span data-ttu-id="7c4c1-p118">Общее количество звонков, классифицированных как звонки низкого качества. Звонок низкого качества — это любой звонок, хотя бы одна метрика которого превышает допустимое значение (например, звонок с чрезмерным дрожанием).</span><span class="sxs-lookup"><span data-stu-id="7c4c1-p118">The total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c4c1-204"><strong>Round trip (ms) (Круговой путь (мс))</strong></span><span class="sxs-lookup"><span data-stu-id="7c4c1-204"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="7c4c1-205">Нет</span><span class="sxs-lookup"><span data-stu-id="7c4c1-205">No</span></span></p></td>
<td><p><span data-ttu-id="7c4c1-p119">Среднее время (в миллисекундах), которое требуется пакету транспортного протокола в режиме реального времени (пакету протокола RTP) на переход к другой конечной точке и возвращение назад. Приемлемым по качеству считается круговой путь не дольше 200 миллисекунд.</span><span class="sxs-lookup"><span data-stu-id="7c4c1-p119">Average amount of time (in milliseconds) required for a Real-Time Transport Protocol packet to travel to one endpoint and then back. Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="7c4c1-p120">Высокие значения кругового пути могут быть следствием маршрутизации международных вызовов, неправильной настройки маршрутизации или перегруженности сервера мультимедиа. Высокие значения кругового пути осложняют проведение двусторонних бесед в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="7c4c1-p120">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c4c1-210"><strong>Packet loss (Потеря пакетов)</strong></span><span class="sxs-lookup"><span data-stu-id="7c4c1-210"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="7c4c1-211">Нет</span><span class="sxs-lookup"><span data-stu-id="7c4c1-211">No</span></span></p></td>
<td><p><span data-ttu-id="7c4c1-p121">Средняя норма потери пакетов транспортного протокола в режиме реального времени (пакетов протокола RTP). (Потеря пакетов происходит, когда пакеты протокола RTP, который используется для передачи звука и видео в Интернете, не достигают места своего назначения.) Высокие уровни потерь обычно бывают следствием перегруженности, нехватки пропускной способности, перегруженности или помех в беспроводной сети, а также перегруженности сервера мультимедиа. Потеря пакетов обычно приводит к искажению или потере звука..</span><span class="sxs-lookup"><span data-stu-id="7c4c1-p121">Average rate of Real-Time Transport Protocol (RTP) packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c4c1-215"><strong>Дрожание (мс)</strong></span><span class="sxs-lookup"><span data-stu-id="7c4c1-215"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="7c4c1-216">Нет</span><span class="sxs-lookup"><span data-stu-id="7c4c1-216">No</span></span></p></td>
<td><p><span data-ttu-id="7c4c1-217">Средний уровень дрожания, определенный между прибытием пакетов протокола RTP.</span><span class="sxs-lookup"><span data-stu-id="7c4c1-217">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="7c4c1-218">(Колебание — это мера &quot; вибрирования &quot; вызова.) Большие значения колебаний обычно вызваны перегрузкой или перегрузкой сервера мультимедиа, что приводит к искажению или потере звука.</span><span class="sxs-lookup"><span data-stu-id="7c4c1-218">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c4c1-219"><strong>Healer concealed ratio (Коэффициент скрытых сэмплов)</strong></span><span class="sxs-lookup"><span data-stu-id="7c4c1-219"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="7c4c1-220">Нет</span><span class="sxs-lookup"><span data-stu-id="7c4c1-220">No</span></span></p></td>
<td><p><span data-ttu-id="7c4c1-p123">Среднее отношение скрытых звуковых сэмплов к общему количеству сэмплов. (Скрытые звуковые сэмплы — это техника, которая используется для сглаживания резких переходов, которые обычно вызываются потерей сетевых пакетов.) Высокие значения указывают на значительные уровни применения скрытия потерь, вызванных потерей пакетов или дрожанием, что может привести к искажению или потере звука.</span><span class="sxs-lookup"><span data-stu-id="7c4c1-p123">Average ratio of concealed audio samples to the total to the total number of samples. (A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c4c1-223"><strong>Healer stretched ratio (Коэффициент растянутых сэмплов)</strong></span><span class="sxs-lookup"><span data-stu-id="7c4c1-223"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="7c4c1-224">Нет</span><span class="sxs-lookup"><span data-stu-id="7c4c1-224">No</span></span></p></td>
<td><p><span data-ttu-id="7c4c1-p124">Среднее отношение растянутых звуковых сэмплов к общему количеству сэмплов. (Растянутые звуковые сэмплы — это звук, который растягивается для поддержания качества звонка, когда обнаруживается потерянный сетевой пакет.) Высокие значения указывают на значительные уровни растягивания сэмплов, вызванного дрожанием, что может привести к искажению или потере звука.</span><span class="sxs-lookup"><span data-stu-id="7c4c1-p124">Average ratio of stretched audio samples to the total to the total number of samples. (Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c4c1-227"><strong>Healer compressed ratio (Коэффициент сжатых сэмплов)</strong></span><span class="sxs-lookup"><span data-stu-id="7c4c1-227"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="7c4c1-228">Нет</span><span class="sxs-lookup"><span data-stu-id="7c4c1-228">No</span></span></p></td>
<td><p><span data-ttu-id="7c4c1-p125">Среднее отношение сжатых звуковых сэмплов к общему количеству сэмплов. (Сжатые звуковые сэмплы — это звук, который сжимается для поддержания качества звонка, когда обнаруживается потерянный сетевой пакет.) Высокие значения указывают на значительные уровни сжатия сэмплов, вызванного дрожанием, что может привести к искажению или потере звука.</span><span class="sxs-lookup"><span data-stu-id="7c4c1-p125">Average ratio of compressed audio samples to the total number of samples. (Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

