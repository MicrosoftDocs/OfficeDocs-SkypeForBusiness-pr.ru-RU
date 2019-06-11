---
title: 'Lync Server 2013: отчет о тенденциях качества сервера мультимедиа'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Server Media Quality Trend Report
ms:assetid: 8a51fd13-1487-4632-b5ec-f7ae2abe8ed4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205071(v=OCS.15)
ms:contentKeyID: 48184760
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dc60cd4c0d8d00fa67a5fe77ca70e61058191baa
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34821875"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-media-quality-trend-report-in-lync-server-2013"></a><span data-ttu-id="5faf4-102">Отчет о тенденциях качества сервера мультимедиа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5faf4-102">Server Media Quality Trend Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5faf4-103">_**Тема последнего изменения:** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="5faf4-103">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="5faf4-104">Отчет о тенденциях качества передачи данных сервера обеспечивает способ сравнения с 5 серверами на предмет качества обслуживания, таких как громкость звонка, процент неудовлетворительного звонка, потеря пакетов и нарушение колебаний.</span><span class="sxs-lookup"><span data-stu-id="5faf4-104">The Server Media Quality Trend Report provides a way for you to graphically compare up to 5 servers on Quality of Experience metrics such as call volume, poor call percentage, packet loss, and jitter.</span></span> <span data-ttu-id="5faf4-105">Это облегчает идентификацию неэффективных серверов, недостаточно интенсивно используемых серверов и чрезмерно используемых серверов.</span><span class="sxs-lookup"><span data-stu-id="5faf4-105">This makes it easier to do such things as identify servers that are performing poorly, identify servers that are underutilized, or identify servers that are being overused.</span></span>

<div>

## <a name="accessing-the-server-media-quality-trend-report"></a><span data-ttu-id="5faf4-106">Доступ к отчету по тенденциям качества мультимедиа на серверах</span><span class="sxs-lookup"><span data-stu-id="5faf4-106">Accessing the Server Media Quality Trend Report</span></span>

<span data-ttu-id="5faf4-107">Доступ к отчету по тенденциям качества мультимедиа на серверах можно получить из одного из следующих отчетов:</span><span class="sxs-lookup"><span data-stu-id="5faf4-107">The Server Media Quality Trend Report can be accessed from either one of the following report:</span></span>

  - <span data-ttu-id="5faf4-108">[Отчет о производительности сервера в Lync server 2013](lync-server-2013-server-performance-report.md) (выбирая метрику тренда)</span><span class="sxs-lookup"><span data-stu-id="5faf4-108">[Server Performance Report in Lync Server 2013](lync-server-2013-server-performance-report.md) (by clicking the Trend metric)</span></span>

  - <span data-ttu-id="5faf4-109">[Подробный отчет о звонке в Lync Server 2013](lync-server-2013-call-detail-report.md) (щелкнув метрику пограничного сервера «A/V».</span><span class="sxs-lookup"><span data-stu-id="5faf4-109">[Call Detail Report in Lync Server 2013](lync-server-2013-call-detail-report.md) (by clicking the A/V edge server metric.</span></span> <span data-ttu-id="5faf4-110">Если вызывающий или вызываемый объект является сервером, вы также можете связаться с отчетом о тенденциях для качества сервера, щелкнув имя конечной точки.)</span><span class="sxs-lookup"><span data-stu-id="5faf4-110">If the caller or callee is a server, you can also reach the Server Quality Media Trend Report by clicking the endpoint name.)</span></span>

</div>

<div>

## <a name="making-the-best-use-of-server-media-quality-trend-report"></a><span data-ttu-id="5faf4-111">Оптимальное использование отчета по тенденциям качества мультимедиа на серверах</span><span class="sxs-lookup"><span data-stu-id="5faf4-111">Making the Best Use of Server Media Quality Trend Report</span></span>

<span data-ttu-id="5faf4-112">При щелчке метрики тренда в [отчете о производительности сервера в Lync server 2013](lync-server-2013-server-performance-report.md) для определенного сервера откроется отчет тренд качества сервера.</span><span class="sxs-lookup"><span data-stu-id="5faf4-112">When you click the Trend metric on the [Server Performance Report in Lync Server 2013](lync-server-2013-server-performance-report.md) for a specific server, the Server Media Quality Trend Report will open.</span></span> <span data-ttu-id="5faf4-113">Однако вы увидите пустой отчет; сервер, выбранный в отчете по производительности сервера, не будет отображаться на экране.</span><span class="sxs-lookup"><span data-stu-id="5faf4-113">However, you will see only a blank instance of that report; the server you selected on the Server Performance Report will not be displayed onscreen.</span></span> <span data-ttu-id="5faf4-114">Вам придется выбрать этот сервер из раскрывающегося списка серверов.</span><span class="sxs-lookup"><span data-stu-id="5faf4-114">Instead, you will need to select that server from the Servers dropdown.</span></span> <span data-ttu-id="5faf4-115">Обратите внимание, что в этом списке также имеется параметр "Select All" ("Выбрать все").</span><span class="sxs-lookup"><span data-stu-id="5faf4-115">Note, too that the Servers dropdown includes a Select All option.</span></span> <span data-ttu-id="5faf4-116">Этот параметр не будет работать при наличии более 5 серверов; отчет по тенденциям качества мультимедиа на серверах может отображать данные не более чем для 5 серверов одновременно.</span><span class="sxs-lookup"><span data-stu-id="5faf4-116">This option will not work if you have more than 5 servers; the Server Media Quality Trend Report can only display data for a maximum of 5 servers at a time.</span></span>

<span data-ttu-id="5faf4-117">На графах, показанных в отчете о тенденциях качества сервера мультимедиа, точки, помеченные как "Громкость" и неудовлетворительный процент звонка, хотлинкс; При щелчке точки на диаграмме откроется экземпляр [отчета из списка обзвона в Lync Server 2013](lync-server-2013-call-list-report.md) , в котором показаны все звонки (или неудовлетворительные звонки) за указанный период времени.</span><span class="sxs-lookup"><span data-stu-id="5faf4-117">On the graphs displayed by the Server Media Quality Trend Report, the points labeled Call Volume and Poor Call Percentage are hotlinks; clicking a point on the graph will open an instance of the [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) showing the total calls (or poor calls) for the specified time period.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="5faf4-118">Фильтры</span><span class="sxs-lookup"><span data-stu-id="5faf4-118">Filters</span></span>

<span data-ttu-id="5faf4-p104">Фильтры позволяют получать более адресный набор данных или просматривать полученные данные разными способами. В следующей таблице приведены фильтры, которые можно использовать в отчете по тенденциям качества мультимедиа на серверах.</span><span class="sxs-lookup"><span data-stu-id="5faf4-p104">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the Server Media Quality Trend Report.</span></span>

### <a name="server-media-quality-trend-report-filters"></a><span data-ttu-id="5faf4-121">Фильтры отчета по тенденциям качества мультимедиа на серверах</span><span class="sxs-lookup"><span data-stu-id="5faf4-121">Server Media Quality Trend Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5faf4-122">Имя</span><span class="sxs-lookup"><span data-stu-id="5faf4-122">Name</span></span></th>
<th><span data-ttu-id="5faf4-123">Описание</span><span class="sxs-lookup"><span data-stu-id="5faf4-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5faf4-124"><strong>От</strong></span><span class="sxs-lookup"><span data-stu-id="5faf4-124"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="5faf4-p105">Начальные дата/время для временного диапазона. Чтобы просмотреть данные по часам, введите начальные дату и время следующим образом:</span><span class="sxs-lookup"><span data-stu-id="5faf4-p105">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="5faf4-127">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="5faf4-127">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="5faf4-p106">Если вы не вводите начальное время, отчет автоматически начинается с 12:00 AM указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</span><span class="sxs-lookup"><span data-stu-id="5faf4-p106">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="5faf4-130">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="5faf4-130">7/7/2012</span></span></p>
<p><span data-ttu-id="5faf4-131">Чтобы просмотреть данные за неделю или месяц, введите дату, выпадающую на любое время в рамках недели или месяца, которые вы хотите просмотреть (вам не требуется вводить первый день недели или месяца):</span><span class="sxs-lookup"><span data-stu-id="5faf4-131">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="5faf4-132">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="5faf4-132">7/3/2012</span></span></p>
<p><span data-ttu-id="5faf4-133">Недели всегда отсчитываются с воскресенья по субботу.</span><span class="sxs-lookup"><span data-stu-id="5faf4-133">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5faf4-134"><strong>До</strong></span><span class="sxs-lookup"><span data-stu-id="5faf4-134"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="5faf4-p107">Конечные дата/время для временного диапазона. Чтобы просмотреть данные по часам, введите конечные дату и время следующим образом:</span><span class="sxs-lookup"><span data-stu-id="5faf4-p107">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="5faf4-137">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="5faf4-137">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="5faf4-p108">Если вы не вводите конечное время, отчет автоматически заканчивается в 12:00 AM указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</span><span class="sxs-lookup"><span data-stu-id="5faf4-p108">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="5faf4-140">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="5faf4-140">7/7/2012</span></span></p>
<p><span data-ttu-id="5faf4-141">Чтобы просмотреть данные за неделю или месяц, введите дату, выпадающую на любое время в рамках недели или месяца, которые вы хотите просмотреть (вам не требуется вводить первый день недели или месяца):</span><span class="sxs-lookup"><span data-stu-id="5faf4-141">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="5faf4-142">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="5faf4-142">7/3/2012</span></span></p>
<p><span data-ttu-id="5faf4-143">Недели всегда отсчитываются с воскресенья по субботу.</span><span class="sxs-lookup"><span data-stu-id="5faf4-143">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5faf4-144"><strong>Интервал</strong></span><span class="sxs-lookup"><span data-stu-id="5faf4-144"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="5faf4-p109">Временной интервал. Выберите одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="5faf4-p109">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="5faf4-147">Ежечасно (можно отобразить не более 25 часов)</span><span class="sxs-lookup"><span data-stu-id="5faf4-147">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="5faf4-148">Ежедневно (можно отобразить не более 31 дня)</span><span class="sxs-lookup"><span data-stu-id="5faf4-148">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="5faf4-149">Еженедельно (можно отобразить не более 12 недель)</span><span class="sxs-lookup"><span data-stu-id="5faf4-149">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="5faf4-150">Если число значений между начальной и конечной датами превышает максимальное допустимое для выбранного интервала, отображается максимальное возможное число значений (с начальной даты).</span><span class="sxs-lookup"><span data-stu-id="5faf4-150">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed.</span></span> <span data-ttu-id="5faf4-151">Например, если выбрать ежедневный интервал с датой начала 8/7/2012 и датой окончания 9/28/2012, данные будут выводиться для дней 8/7/2012 12:00 – 9/7/2012 12:00 AM (то есть, всего за 31 дня).</span><span class="sxs-lookup"><span data-stu-id="5faf4-151">For example, if you select the Daily interval with a start date of 8/7/2012 and an end date of 9/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5faf4-152"><strong>Тип сервера</strong></span><span class="sxs-lookup"><span data-stu-id="5faf4-152"><strong>Server type</strong></span></span></p></td>
<td><p><span data-ttu-id="5faf4-p111">Тип сервера, участвующего в вызове. Допускаются следующие значения:</span><span class="sxs-lookup"><span data-stu-id="5faf4-p111">Type of server involved in the call. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="5faf4-155">посредник</span><span class="sxs-lookup"><span data-stu-id="5faf4-155">Mediation Server</span></span></p></li>
<li><p><span data-ttu-id="5faf4-156">аудио- и видео конференций</span><span class="sxs-lookup"><span data-stu-id="5faf4-156">A/V Conferencing Server</span></span></p></li>
<li><p><span data-ttu-id="5faf4-157">Пограничный сервер аудио и видео</span><span class="sxs-lookup"><span data-stu-id="5faf4-157">A/V Edge Server</span></span></p></li>
<li><p><span data-ttu-id="5faf4-158">Шлюз (сервер-посредник)</span><span class="sxs-lookup"><span data-stu-id="5faf4-158">Gateway (Mediation Server)</span></span></p></li>
<li><p><span data-ttu-id="5faf4-159">Gateway (Mediation Server Bypass) (Шлюз (обход сервера-посредника));</span><span class="sxs-lookup"><span data-stu-id="5faf4-159">Gateway (Mediation Server Bypass)</span></span></p></li>
<li><p><span data-ttu-id="5faf4-160">AS Conferencing Server (Сервер конференций AS).</span><span class="sxs-lookup"><span data-stu-id="5faf4-160">AS Conferencing Server</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5faf4-161"><strong>Servers (Серверы)</strong></span><span class="sxs-lookup"><span data-stu-id="5faf4-161"><strong>Servers</strong></span></span></p></td>
<td><p><span data-ttu-id="5faf4-p112">Имя сервера, участвующего в сеансе; этот раскрывающийся список заполняется автоматически в зависимости от значения фильтра "Server type" ("Тип сервера"). При составлении отчета вы можете выбрать вплоть до 5 разных серверов.</span><span class="sxs-lookup"><span data-stu-id="5faf4-p112">Name of the server involved in the session; this dropdown list is automatically populated for you based on the value of the Server type filter. You can select up to 5 different servers when compiling a report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5faf4-164"><strong>Тип доступа</strong></span><span class="sxs-lookup"><span data-stu-id="5faf4-164"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="5faf4-p113">Указывает, вошел ли участник во внутреннюю сеть, или подключался из внешней сети. Допускаются следующие значения:</span><span class="sxs-lookup"><span data-stu-id="5faf4-p113">Indicates whether the participant was logged on to the internal network or from the external network. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="5faf4-167">[All] (Все)</span><span class="sxs-lookup"><span data-stu-id="5faf4-167">[All]</span></span></p></li>
<li><p><span data-ttu-id="5faf4-168">Internal</span><span class="sxs-lookup"><span data-stu-id="5faf4-168">Internal</span></span></p></li>
<li><p><span data-ttu-id="5faf4-169">Внешняя</span><span class="sxs-lookup"><span data-stu-id="5faf4-169">External</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5faf4-170"><strong>Тип сети</strong></span><span class="sxs-lookup"><span data-stu-id="5faf4-170"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="5faf4-p114">Указывает тип сети, к которой подключался участник. Допускаются следующие значения:</span><span class="sxs-lookup"><span data-stu-id="5faf4-p114">Indicates the type of network the participant was connected to. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="5faf4-173">[All] (Все)</span><span class="sxs-lookup"><span data-stu-id="5faf4-173">[All]</span></span></p></li>
<li><p><span data-ttu-id="5faf4-174">Проводная</span><span class="sxs-lookup"><span data-stu-id="5faf4-174">Wired</span></span></p></li>
<li><p><span data-ttu-id="5faf4-175">Беспроводная</span><span class="sxs-lookup"><span data-stu-id="5faf4-175">Wireless</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5faf4-176"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="5faf4-176"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="5faf4-p115">Указывает, использовал ли внешний участник подключение через виртуальную частную сеть (VPN) во время сеанса. Допускаются следующие значения:</span><span class="sxs-lookup"><span data-stu-id="5faf4-p115">Indicates whether an external participant was using a virtual private network (VPN) connection during the session. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="5faf4-179">[All] (Все)</span><span class="sxs-lookup"><span data-stu-id="5faf4-179">[All]</span></span></p></li>
<li><p><span data-ttu-id="5faf4-180">VPN</span><span class="sxs-lookup"><span data-stu-id="5faf4-180">VPN</span></span></p></li>
<li><p><span data-ttu-id="5faf4-181">Не VPN</span><span class="sxs-lookup"><span data-stu-id="5faf4-181">Non-VPN</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="5faf4-182">Показатели</span><span class="sxs-lookup"><span data-stu-id="5faf4-182">Metrics</span></span>

<span data-ttu-id="5faf4-183">В следующей таблице приведены виды сведений, предоставляемые в отчете по тенденциям качества мультимедиа на серверах.</span><span class="sxs-lookup"><span data-stu-id="5faf4-183">The following table lists the information provided in the Server Media Quality Trend Report.</span></span>

### <a name="server-media-quality-trend-report-metrics"></a><span data-ttu-id="5faf4-184">Метрики отчета по тенденциям качества мультимедиа на серверах</span><span class="sxs-lookup"><span data-stu-id="5faf4-184">Server Media Quality Trend Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5faf4-185">Имя</span><span class="sxs-lookup"><span data-stu-id="5faf4-185">Name</span></span></th>
<th><span data-ttu-id="5faf4-186">Поддержка сортировки</span><span class="sxs-lookup"><span data-stu-id="5faf4-186">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="5faf4-187">Описание</span><span class="sxs-lookup"><span data-stu-id="5faf4-187">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5faf4-188"><strong>Громкость вызова</strong></span><span class="sxs-lookup"><span data-stu-id="5faf4-188"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="5faf4-189">Нет</span><span class="sxs-lookup"><span data-stu-id="5faf4-189">No</span></span></p></td>
<td><p><span data-ttu-id="5faf4-190">Полное число звонков.</span><span class="sxs-lookup"><span data-stu-id="5faf4-190">Total number of calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5faf4-191"><strong>Падение качества (средняя оценка)</strong></span><span class="sxs-lookup"><span data-stu-id="5faf4-191"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="5faf4-192">Нет</span><span class="sxs-lookup"><span data-stu-id="5faf4-192">No</span></span></p></td>
<td><p><span data-ttu-id="5faf4-193">Среднее значение числа MOS (средней экспертной оценки разборчивости речи), показывающей ухудшение качества связи во время звонка.</span><span class="sxs-lookup"><span data-stu-id="5faf4-193">Average amount of MOS (mean option score) degradation experienced during a call.</span></span> <span data-ttu-id="5faf4-194">Значения ухудшения качества могут находиться в диапазоне от 0,0 до 5,0; значение 0,5 или ниже соответствует приемлемому ухудшению.</span><span class="sxs-lookup"><span data-stu-id="5faf4-194">Degradation values can range from a low of 0.0 to a high of 5.0; a value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="5faf4-195">Исторически средние экспертные оценки разборчивости речи вычислялись при помощи пользователей, которые оценивали качество звонка по шкале от 1 до 5.</span><span class="sxs-lookup"><span data-stu-id="5faf4-195">Historically, mean options scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="5faf4-196">Lync Server использует набор алгоритмов для прогнозирования того, как пользователи будут оценены при звонке.</span><span class="sxs-lookup"><span data-stu-id="5faf4-196">Lync Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="5faf4-p117">Высокие значения ухудшения могут быть вызваны перегрузкой; недостаточной пропускной способностью; перегрузкой беспроводной сети или интерференцией; перегрузкой сервера мультимедиа или конечной точки. Сильное ухудшение приводит к повреждению или потере аудиосигнала.</span><span class="sxs-lookup"><span data-stu-id="5faf4-p117">High degradation values can be caused by congestion; lack of bandwidth; wireless congestion or interference, or an overloaded media server or endpoint. High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5faf4-199"><strong>Процент звонков низкого качества</strong></span><span class="sxs-lookup"><span data-stu-id="5faf4-199"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="5faf4-200">Нет</span><span class="sxs-lookup"><span data-stu-id="5faf4-200">No</span></span></p></td>
<td><p><span data-ttu-id="5faf4-p118">Полное число звонков, классифицированных как неудовлетворительные. Неудовлетворительный звонок — это любой звонок, в котором хотя бы одна измеренная метрика превысила допустимое значение (например, звонок, подверженный слишком сильному дрожанию).</span><span class="sxs-lookup"><span data-stu-id="5faf4-p118">The total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5faf4-203"><strong>Круговой путь (мс)</strong></span><span class="sxs-lookup"><span data-stu-id="5faf4-203"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="5faf4-204">Нет</span><span class="sxs-lookup"><span data-stu-id="5faf4-204">No</span></span></p></td>
<td><p><span data-ttu-id="5faf4-p119">Среднее время (в миллисекундах), которое требуется пакету транспортного протокола в режиме реального времени (пакету протокола RTP) на переход к другой конечной точке и возвращение назад. Приемлемым по качеству считается круговой путь не дольше 200 миллисекунд.</span><span class="sxs-lookup"><span data-stu-id="5faf4-p119">Average amount of time (in milliseconds) required for a Real-Time Transport Protocol packet to travel to one endpoint and then back. Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="5faf4-p120">Высокие значения времени двусторонней передачи могут быть обусловлены международной маршрутизацией вызовов, неправильной конфигурацией маршрутизации или перегрузкой сервера-посредника. Длительное время двусторонней передачи приводит к возникновению проблем при двусторонних аудиоразговорах в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="5faf4-p120">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5faf4-209"><strong>Потеря пакетов</strong></span><span class="sxs-lookup"><span data-stu-id="5faf4-209"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="5faf4-210">Нет</span><span class="sxs-lookup"><span data-stu-id="5faf4-210">No</span></span></p></td>
<td><p><span data-ttu-id="5faf4-p121">Средняя частота потери пакетов RTP. (Потеря пакетов происходит, когда пакеты RTP (Real-Time Transport Protocol — протокол, используемый для передачи аудио- и видеопакетов через Интернет) не достигают места назначения.) Высокие показатели потерь обычно вызваны перегрузкой, недостаточной полосой пропускания, помехами или перегрузкой беспроводной сети, а также перегрузкой сервера-посредника. Потеря пакетов обычно приводит к искажению звука или потере аудиосигналов.</span><span class="sxs-lookup"><span data-stu-id="5faf4-p121">Average rate of Real-Time Transport Protocol (RTP) packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5faf4-214"><strong>Дрожание (мс)</strong></span><span class="sxs-lookup"><span data-stu-id="5faf4-214"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="5faf4-215">Нет</span><span class="sxs-lookup"><span data-stu-id="5faf4-215">No</span></span></p></td>
<td><p><span data-ttu-id="5faf4-216">Среднее значение колебаний, зарегистрированных между прибытиями пакетов RTP.</span><span class="sxs-lookup"><span data-stu-id="5faf4-216">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="5faf4-217">(Колебание — это мера &quot;шакинесс&quot; звонка). Обычно значения с высокой степенью колебаний заключаются в результате перегруженности или перегруженного сервера мультимедиа, что приводит к искажению или потере звука.</span><span class="sxs-lookup"><span data-stu-id="5faf4-217">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5faf4-218"><strong>Степень маскированных аудиообразцов</strong></span><span class="sxs-lookup"><span data-stu-id="5faf4-218"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="5faf4-219">Нет</span><span class="sxs-lookup"><span data-stu-id="5faf4-219">No</span></span></p></td>
<td><p><span data-ttu-id="5faf4-p123">Средняя степень маскированных аудиообразцов по отношению к общему числу образцов. (Маскирование аудио - это методика, которая применяется для сглаживания оборванной передачи, которая обычно происходит при потери сетевых пакетов). Большие значения обозначают частое применение данной методики, вызванной из-за потери пакетов или искажений сигнала.</span><span class="sxs-lookup"><span data-stu-id="5faf4-p123">Average ratio of concealed audio samples to the total to the total number of samples. (A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5faf4-222"><strong>Степень растянутых образцов</strong></span><span class="sxs-lookup"><span data-stu-id="5faf4-222"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="5faf4-223">Нет</span><span class="sxs-lookup"><span data-stu-id="5faf4-223">No</span></span></p></td>
<td><p><span data-ttu-id="5faf4-p124">Средняя степень растянутых аудиообразцов по отношению к общему числу образцов. (Растягивание аудиопакета - это методика, которая применяется для поддержания качества звонка при обнаружении потери сетевого пакета). Большие значения обозначают частое применение данной методики, вызванное большими искажениями – аудиосигнал звучит как роботизированный.</span><span class="sxs-lookup"><span data-stu-id="5faf4-p124">Average ratio of stretched audio samples to the total to the total number of samples. (Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5faf4-226"><strong>Степень сжатых аудиообразцов</strong></span><span class="sxs-lookup"><span data-stu-id="5faf4-226"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="5faf4-227">Нет</span><span class="sxs-lookup"><span data-stu-id="5faf4-227">No</span></span></p></td>
<td><p><span data-ttu-id="5faf4-p125">Средняя степень растянутых аудиообразцов по отношению к общему числу образцов. (Сжатие аудиопакета - это методика, которая применяется для поддержания качества звонка при обнаружении потери сетевого пакета). Большие значения обозначают частое применение данной методики, вызванное большими искажениями – аудиосигнал звучит как ускоренный или искаженный.</span><span class="sxs-lookup"><span data-stu-id="5faf4-p125">Average ratio of compressed audio samples to the total number of samples. (Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

