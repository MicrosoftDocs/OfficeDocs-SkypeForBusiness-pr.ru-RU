---
title: 'Lync Server 2013: отчет о производительности сервера'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Server Performance Report
ms:assetid: 942bb39a-1790-498e-9d99-8f6ce2d155c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615018(v=OCS.15)
ms:contentKeyID: 48184879
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3c5a08104f33fc07d6a0ec1c3241a7f14fa1227a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822379"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-performance-report-in-lync-server-2013"></a><span data-ttu-id="c5164-102">Отчет о производительности сервера в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c5164-102">Server Performance Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c5164-103">_**Тема последнего изменения:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="c5164-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="c5164-104">Отчет о производительности сервера содержит список серверов Microsoft Lync Server 2013, в которых вы столкнулись с наибольшим количеством некачественных звонков.</span><span class="sxs-lookup"><span data-stu-id="c5164-104">The Server Performance Report provides a list of Microsoft Lync Server 2013 servers that have experienced the highest-percentage of poor calls.</span></span> <span data-ttu-id="c5164-105">В отчете сервера распределены по типам, для каждого из них дается статистика следующих видов:</span><span class="sxs-lookup"><span data-stu-id="c5164-105">The report breaks down servers by server type, reporting separate statistics for the following types:</span></span>

  - <span data-ttu-id="c5164-106">посредник</span><span class="sxs-lookup"><span data-stu-id="c5164-106">Mediation Server</span></span>

  - <span data-ttu-id="c5164-107">аудио- и видео конференций</span><span class="sxs-lookup"><span data-stu-id="c5164-107">A/V Conferencing Server</span></span>

  - <span data-ttu-id="c5164-108">Пограничный сервер аудио и видео</span><span class="sxs-lookup"><span data-stu-id="c5164-108">A/V Edge Server</span></span>

  - <span data-ttu-id="c5164-109">Шлюз (сервер-посредник)</span><span class="sxs-lookup"><span data-stu-id="c5164-109">Gateway (Mediation Server)</span></span>

  - <span data-ttu-id="c5164-110">Шлюз (в обход сервера-посредника)</span><span class="sxs-lookup"><span data-stu-id="c5164-110">Gateway (Mediation Server bypass)</span></span>

  - <span data-ttu-id="c5164-111">Видео (включая показатели видео для серверов аудио и видеоконференций и соответствующих пограничных серверов)</span><span class="sxs-lookup"><span data-stu-id="c5164-111">Video (including video metrics for A/V Conferencing servers and A/V Edge servers)</span></span>

  - <span data-ttu-id="c5164-112">Общий доступ к приложениям (включая показатели общего доступа для серверов аудио и видеоконференций и соответствующих пограничных серверов)</span><span class="sxs-lookup"><span data-stu-id="c5164-112">Application Sharing (including application sharing metrics for A/V Conferencing servers and A/V Edge servers)</span></span>

<span data-ttu-id="c5164-p102">Следует помнить, что ранжирование в данном отчете относительное. Например, предположим что вашем наименее производительном сервере бывает один плохой звонок из 1 000. Это более чем приемлемый показатель в 0,1%. Но данный сервер (при учете того, что у других серверов этот процент еще меньше) все равно будет приведет в отчет о производительности серверов.</span><span class="sxs-lookup"><span data-stu-id="c5164-p102">It’s important to note that the ranking shown in this report as relative rankings. For example, suppose your worst-performing server had one poor call among its 1,000 placed calls. That's a more-than-acceptable percentage of .1%. However, if that's the worst-performing server you have (that is, if all your other servers have a poor call percentage even lower than .1%), then that server will still appear on the Server Performance Report.</span></span>

<div>

## <a name="accessing-the-server-performance-report"></a><span data-ttu-id="c5164-117">Получение доступа к отчету о производительности серверов</span><span class="sxs-lookup"><span data-stu-id="c5164-117">Accessing the Server Performance Report</span></span>

<span data-ttu-id="c5164-118">Доступ к отчету можно получить с главный страницы отчетов по мониторингу.</span><span class="sxs-lookup"><span data-stu-id="c5164-118">The Server Performance Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="c5164-119">Вы можете перейти к отчету [список обзвона в Lync Server 2013](lync-server-2013-call-list-report.md) , щелкнув один из следующих метрик:</span><span class="sxs-lookup"><span data-stu-id="c5164-119">You can drill down to the [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="c5164-120">Громкость вызова</span><span class="sxs-lookup"><span data-stu-id="c5164-120">Call volume</span></span>

  - <span data-ttu-id="c5164-121">Процент звонков низкого качества</span><span class="sxs-lookup"><span data-stu-id="c5164-121">Poor call percentage</span></span>

<span data-ttu-id="c5164-122">Также можно детализировать отчет о тренде качестве среды передачи данных сервера, щелкнув один из следующих показателей:</span><span class="sxs-lookup"><span data-stu-id="c5164-122">In addition, you can drill down to the Server Media Quality Trend Report by clicking the following metric:</span></span>

  - <span data-ttu-id="c5164-123">Тренд</span><span class="sxs-lookup"><span data-stu-id="c5164-123">Trend</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-server-performance-report"></a><span data-ttu-id="c5164-124">Оптимальное использование отчета о производительности сервера</span><span class="sxs-lookup"><span data-stu-id="c5164-124">Making the Best Use of the Server Performance Report</span></span>

<span data-ttu-id="c5164-p104">В отчете есть несколько фильтров данных. Например, можно фильтровать по типу сети (звонки по проводным и беспроводным соединениям) и типу доступа (звонки из-за пределов и изнутри брандмауэра). Рекомендуется использовать данные фильтры при просмотре отчета. Например, предположим что имеется сервер-посредник с процентом плохих звонков 3.24%. Если рассмотреть процент плохих беспроводных звонков, то процент может достигать значения 20%. Это значит, что на данном сервере возникают проблемы при обслуживании беспроводных звонков, эти сведения были скрыты, так как проблем при обслуживании проводных соединений не было.</span><span class="sxs-lookup"><span data-stu-id="c5164-p104">The Server Performance Report provides a number of ways to filter data; for example, you can filter on network type (calls made from a wired connection vs. calls made from a wireless connection) and access type (calls made from inside the firewall vs. calls made from outside the firewall). It's a good idea when viewing the server performance report to make use of these filters. For example, suppose you have a Mediation Server that has a poor call percentage of 3.24%. If you look solely at wireless calls, that same server might have a poor call percentage approaching 20%. That means that the server was having difficulty with wireless calls, a problem that is partially obscured because the server was not having problems with wired calls.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="c5164-130">Фильтры</span><span class="sxs-lookup"><span data-stu-id="c5164-130">Filters</span></span>

<span data-ttu-id="c5164-p105">С помощью фильтров можно получить более точный набор данных и просмотреть полученные данные под другим углом. Например, в отчете о производительности серверов можно фильтровать данные по типу сети и серверу. Также можно выбрать способ группирования данных. В данном случае данные группируются по часам, дню, неделе и месяцу.</span><span class="sxs-lookup"><span data-stu-id="c5164-p105">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Server Performance Report enables you to do such things as filter the returned data by server type or by network type (that is, wired or wireless). You can also choose how data should be grouped. In this case, data is grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="c5164-135">В следующей таблице приведены фильтры, которые можно использовать в отчете о производительности серверов.</span><span class="sxs-lookup"><span data-stu-id="c5164-135">The following table lists the filters that you can use with the Server Performance Report.</span></span>

### <a name="server-performance-report-filters"></a><span data-ttu-id="c5164-136">Фильтры отчета о производительности серверов</span><span class="sxs-lookup"><span data-stu-id="c5164-136">Server Performance Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c5164-137">Имя</span><span class="sxs-lookup"><span data-stu-id="c5164-137">Name</span></span></th>
<th><span data-ttu-id="c5164-138">Описание</span><span class="sxs-lookup"><span data-stu-id="c5164-138">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c5164-139"><strong>От</strong></span><span class="sxs-lookup"><span data-stu-id="c5164-139"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="c5164-p106">Начальные дата/время для временного диапазона. Чтобы просмотреть данные по часам, введите начальные дату и время следующим образом:</span><span class="sxs-lookup"><span data-stu-id="c5164-p106">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="c5164-142">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="c5164-142">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="c5164-p107">Если вы не вводите начальное время, отчет автоматически начинается с 12:00 AM указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</span><span class="sxs-lookup"><span data-stu-id="c5164-p107">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="c5164-145">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="c5164-145">7/7/2012</span></span></p>
<p><span data-ttu-id="c5164-146">Чтобы просмотреть данные за неделю или месяц, введите дату, выпадающую на любое время в рамках недели или месяца, которые вы хотите просмотреть (вам не требуется вводить первый день недели или месяца):</span><span class="sxs-lookup"><span data-stu-id="c5164-146">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="c5164-147">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="c5164-147">7/3/2012</span></span></p>
<p><span data-ttu-id="c5164-148">Недели всегда отсчитываются с воскресенья по субботу.</span><span class="sxs-lookup"><span data-stu-id="c5164-148">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5164-149"><strong>До</strong></span><span class="sxs-lookup"><span data-stu-id="c5164-149"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="c5164-p108">Конечные дата/время для временного диапазона. Чтобы просмотреть данные по часам, введите конечные дату и время следующим образом:</span><span class="sxs-lookup"><span data-stu-id="c5164-p108">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="c5164-152">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="c5164-152">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="c5164-p109">Если вы не вводите конечное время, отчет автоматически заканчивается в 12:00 AM указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</span><span class="sxs-lookup"><span data-stu-id="c5164-p109">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="c5164-155">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="c5164-155">7/7/2012</span></span></p>
<p><span data-ttu-id="c5164-156">Чтобы просмотреть данные за неделю или месяц, введите дату, выпадающую на любое время в рамках недели или месяца, которые вы хотите просмотреть (вам не требуется вводить первый день недели или месяца):</span><span class="sxs-lookup"><span data-stu-id="c5164-156">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="c5164-157">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="c5164-157">7/3/2012</span></span></p>
<p><span data-ttu-id="c5164-158">Недели всегда отсчитываются с воскресенья по субботу.</span><span class="sxs-lookup"><span data-stu-id="c5164-158">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5164-159"><strong>Тип сервера</strong></span><span class="sxs-lookup"><span data-stu-id="c5164-159"><strong>Server type</strong></span></span></p></td>
<td><p><span data-ttu-id="c5164-p110">Обозначает тип сервера, по которому дается сводка о производительности. Выберите один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="c5164-p110">Indicates the type of server whose performance should be reported. Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="c5164-162">[All] (Все)</span><span class="sxs-lookup"><span data-stu-id="c5164-162">[All]</span></span></p></li>
<li><p><span data-ttu-id="c5164-163">посредник</span><span class="sxs-lookup"><span data-stu-id="c5164-163">Mediation Server</span></span></p></li>
<li><p><span data-ttu-id="c5164-164">аудио- и видео конференций</span><span class="sxs-lookup"><span data-stu-id="c5164-164">A/V Conferencing Server</span></span></p></li>
<li><p><span data-ttu-id="c5164-165">Пограничный сервер аудио и видео</span><span class="sxs-lookup"><span data-stu-id="c5164-165">A/V Edge Server</span></span></p></li>
</ol></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5164-166"><strong>Первые N</strong></span><span class="sxs-lookup"><span data-stu-id="c5164-166"><strong>Top N</strong></span></span></p></td>
<td><p><span data-ttu-id="c5164-p111">Обозначает количество серверов (на основе их процента плохих звонков) для отображения в каждой категории. Например, если выбрать значение <strong>5</strong>, то отображается пять хуже всего справляющихся серверов. Выберите один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="c5164-p111">Indicates the number of servers (based on their poor call percentage) to be displayed in each category. For example, if you select <strong>5</strong> then the five poorest-performing servers are displayed. Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="c5164-170">[All] (Все)</span><span class="sxs-lookup"><span data-stu-id="c5164-170">[All]</span></span></p></li>
<li><p><span data-ttu-id="c5164-171">5</span><span class="sxs-lookup"><span data-stu-id="c5164-171">5</span></span></p></li>
<li><p><span data-ttu-id="c5164-172">5-10</span><span class="sxs-lookup"><span data-stu-id="c5164-172">10</span></span></p></li>
</ol></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5164-173"><strong>Тип доступа</strong></span><span class="sxs-lookup"><span data-stu-id="c5164-173"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="c5164-p112">Определяет, был ли клиент зарегистрирован во внутренней сети или внешней сети при выполнении вызова. Выберите один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="c5164-p112">Indicates whether the client was logged on to the internal network or the external network when the call was placed. Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="c5164-176">[All] (Все)</span><span class="sxs-lookup"><span data-stu-id="c5164-176">[All]</span></span></p></li>
<li><p><span data-ttu-id="c5164-177">Internal</span><span class="sxs-lookup"><span data-stu-id="c5164-177">Internal</span></span></p></li>
<li><p><span data-ttu-id="c5164-178">Внешняя</span><span class="sxs-lookup"><span data-stu-id="c5164-178">External</span></span></p></li>
</ol></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5164-179"><strong>Тип сети</strong></span><span class="sxs-lookup"><span data-stu-id="c5164-179"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="c5164-p113">Определяет тип сети, к которой был подключен клиент при выполнении вызова. Выберите один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="c5164-p113">Indicates the type of network the client was connected to when the call was placed. Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="c5164-182">[All] (Все)</span><span class="sxs-lookup"><span data-stu-id="c5164-182">[All]</span></span></p></li>
<li><p><span data-ttu-id="c5164-183">Проводная</span><span class="sxs-lookup"><span data-stu-id="c5164-183">Wired</span></span></p></li>
<li><p><span data-ttu-id="c5164-184">Беспроводная</span><span class="sxs-lookup"><span data-stu-id="c5164-184">Wireless</span></span></p></li>
</ol></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5164-185"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="c5164-185"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="c5164-p114">Указывает, использовал ли внешний клиент подключение посредством виртуальной частной сети (VPN) при выполнении вызова. Выберите один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="c5164-p114">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed. Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="c5164-188">[All] (Все)</span><span class="sxs-lookup"><span data-stu-id="c5164-188">[All]</span></span></p></li>
<li><p><span data-ttu-id="c5164-189">VPN;</span><span class="sxs-lookup"><span data-stu-id="c5164-189">VPN</span></span></p></li>
<li><p><span data-ttu-id="c5164-190">Не VPN</span><span class="sxs-lookup"><span data-stu-id="c5164-190">Non-VPN</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="c5164-191">Показатели</span><span class="sxs-lookup"><span data-stu-id="c5164-191">Metrics</span></span>

<span data-ttu-id="c5164-192">В следующей таблице приведены сведения, предоставляемы в отчете о производительности серверов.</span><span class="sxs-lookup"><span data-stu-id="c5164-192">The following table lists the information provided in the Server Performance Report.</span></span>

### <a name="server-performance-report-metrics-audio-call-summary"></a><span data-ttu-id="c5164-193">Показатели отчета о производительности серверов: сводка по голосовым звонкам</span><span class="sxs-lookup"><span data-stu-id="c5164-193">Server Performance Report Metrics: Audio Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c5164-194">Имя</span><span class="sxs-lookup"><span data-stu-id="c5164-194">Name</span></span></th>
<th><span data-ttu-id="c5164-195">Можно проводить сортировку</span><span class="sxs-lookup"><span data-stu-id="c5164-195">Can Sort On</span></span></th>
<th><span data-ttu-id="c5164-196">Описание</span><span class="sxs-lookup"><span data-stu-id="c5164-196">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c5164-197"><strong>Сервер</strong></span><span class="sxs-lookup"><span data-stu-id="c5164-197"><strong>Server</strong></span></span></p></td>
<td><p><span data-ttu-id="c5164-198">Нет</span><span class="sxs-lookup"><span data-stu-id="c5164-198">No</span></span></p></td>
<td><p><span data-ttu-id="c5164-199">Название/IP-адрес сервера.</span><span class="sxs-lookup"><span data-stu-id="c5164-199">Name/IP address of the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5164-200"><strong>Громкость вызова</strong></span><span class="sxs-lookup"><span data-stu-id="c5164-200"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="c5164-201">Нет</span><span class="sxs-lookup"><span data-stu-id="c5164-201">No</span></span></p></td>
<td><p><span data-ttu-id="c5164-202">Общее количество сделанных звонков.</span><span class="sxs-lookup"><span data-stu-id="c5164-202">Total number of calls made.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5164-203"><strong>Процент звонков низкого качества</strong></span><span class="sxs-lookup"><span data-stu-id="c5164-203"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="c5164-204">Нет</span><span class="sxs-lookup"><span data-stu-id="c5164-204">No</span></span></p></td>
<td><p><span data-ttu-id="c5164-p115">Общее количество звонков, классифицированных как звонки низкого качества. Звонок низкого качества – это любой звонок, хотя бы одна метрика которого превышает допустимое значение (например, звонок с чрезмерным дрожанием).</span><span class="sxs-lookup"><span data-stu-id="c5164-p115">Total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5164-207"><strong>Круговой путь (мс)</strong></span><span class="sxs-lookup"><span data-stu-id="c5164-207"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="c5164-208">Да</span><span class="sxs-lookup"><span data-stu-id="c5164-208">Yes</span></span></p></td>
<td><p><span data-ttu-id="c5164-p116">Среднее время (в миллисекунда) требуемое для передачи пакета протокола транспорта реального времени (RTP) в другую конечную точку и обратно. Круговой путь в 100 и меньше миллисекунд считается допустимым.</span><span class="sxs-lookup"><span data-stu-id="c5164-p116">Average amount of (in milliseconds) required for a real-time transport protocol (RTP) packet to travel to another endpoint and then back. Round-trip times of 100 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="c5164-p117">Высокие значения времени двусторонней передачи могут быть обусловлены международной маршрутизацией вызовов, неправильной конфигурацией маршрутизации или перегрузкой сервера-посредника. Длительное время двусторонней передачи приводит к возникновению проблем при двусторонних аудиоразговорах в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="c5164-p117">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5164-213"><strong>Падение качества (средняя оценка)</strong></span><span class="sxs-lookup"><span data-stu-id="c5164-213"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="c5164-214">Да</span><span class="sxs-lookup"><span data-stu-id="c5164-214">Yes</span></span></p></td>
<td><p><span data-ttu-id="c5164-215">Средняя экспертная оценка падения качества связи во время звонка.</span><span class="sxs-lookup"><span data-stu-id="c5164-215">Average amount of mean opinion score (MOS) degradation experienced during a call.</span></span> <span data-ttu-id="c5164-216">Значения лежат в диапазоне от 0,0 до 5,0.</span><span class="sxs-lookup"><span data-stu-id="c5164-216">Degradation values can range from a low of 0.0 to a high of 5.0.</span></span> <span data-ttu-id="c5164-217">Значение 0,5 или меньшее обозначает допустимое падение качества.</span><span class="sxs-lookup"><span data-stu-id="c5164-217">A value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="c5164-218">Изначально средние оценки рассчитывались на основе оценок, даваемых звонкам пользователями по шкале от 1 до 5.</span><span class="sxs-lookup"><span data-stu-id="c5164-218">Historically, mean options scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="c5164-219">В Lync Server сервер мониторинга использует набор алгоритмов для прогнозирования того, как пользователи будут оценены при звонке.</span><span class="sxs-lookup"><span data-stu-id="c5164-219">In Lync Server, the Monitoring Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="c5164-p119">Большие оценки падения качества могут быть вызваны перегрузкой сети, недостатком пропускной способности, помехами в беспроводной среде, перегрузкой на сервере-посреднике или конечной точке. Падение качества приводит к искажению или потере аудиосигнала.</span><span class="sxs-lookup"><span data-stu-id="c5164-p119">High degradation values can be caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server or endpoint. High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5164-222"><strong>Потеря пакетов</strong></span><span class="sxs-lookup"><span data-stu-id="c5164-222"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="c5164-223">Да</span><span class="sxs-lookup"><span data-stu-id="c5164-223">Yes</span></span></p></td>
<td><p><span data-ttu-id="c5164-p120">Среднее значение потери RTP-пакетов. (Пакет считается потерянным, если он не дошел до назначения). Большие значения потери пакетов могут быть вызваны перегрузкой сети, недостатком пропускной способности, помехами в беспроводной среде, перегрузкой на сервере-посреднике. Обычно это приводит к искажению или потере аудиосигнала.</span><span class="sxs-lookup"><span data-stu-id="c5164-p120">Average rate of real-time transport protocol (RTP) packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5164-227"><strong>Дрожание (мс)</strong></span><span class="sxs-lookup"><span data-stu-id="c5164-227"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="c5164-228">Да</span><span class="sxs-lookup"><span data-stu-id="c5164-228">Yes</span></span></p></td>
<td><p><span data-ttu-id="c5164-229">Среднее значение колебаний, зарегистрированных между прибытиями пакетов RTP.</span><span class="sxs-lookup"><span data-stu-id="c5164-229">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="c5164-230">(Колебание — это мера &quot;шакинесс&quot; звонка). Обычно значения с высокой степенью колебаний заключаются в результате перегруженности или перегруженного сервера мультимедиа, что приводит к искажению или потере звука.</span><span class="sxs-lookup"><span data-stu-id="c5164-230">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5164-231"><strong>Степень маскированных аудиообразцов</strong></span><span class="sxs-lookup"><span data-stu-id="c5164-231"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="c5164-232">Да</span><span class="sxs-lookup"><span data-stu-id="c5164-232">Yes</span></span></p></td>
<td><p><span data-ttu-id="c5164-p122">Средняя степень маскированных аудиообразцов по отношению к общему числу образцов. (Маскирование аудио - это методика, которая применяется для сглаживания оборванной передачи, которая обычно происходит при потери сетевых пакетов). Большие значения обозначают частое применение данной методики, вызванной из-за потери пакетов или искажений сигнала.</span><span class="sxs-lookup"><span data-stu-id="c5164-p122">Average ratio of concealed audio samples to the total to the total number of samples. (A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5164-235"><strong>Степень растянутых образцов</strong></span><span class="sxs-lookup"><span data-stu-id="c5164-235"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="c5164-236">Да</span><span class="sxs-lookup"><span data-stu-id="c5164-236">Yes</span></span></p></td>
<td><p><span data-ttu-id="c5164-p123">Средняя степень растянутых аудиообразцов по отношению к общему числу образцов. (Растягивание аудиопакета - это методика, которая применяется для поддержания качества звонка при обнаружении потери сетевого пакета). Большие значения обозначают частое применение данной методики, вызванное большими искажениями – аудиосигнал звучит как роботизированный.</span><span class="sxs-lookup"><span data-stu-id="c5164-p123">Average ratio of stretched audio samples to the total to the total number of samples. (Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5164-239"><strong>Степень сжатых аудиообразцов</strong></span><span class="sxs-lookup"><span data-stu-id="c5164-239"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="c5164-240">Да</span><span class="sxs-lookup"><span data-stu-id="c5164-240">Yes</span></span></p></td>
<td><p><span data-ttu-id="c5164-p124">Средняя степень растянутых аудиообразцов по отношению к общему числу образцов. (Сжатие аудиопакета - это методика, которая применяется для поддержания качества звонка при обнаружении потери сетевого пакета). Большие значения обозначают частое применение данной методики, вызванное большими искажениями – аудиосигнал звучит как ускоренный или искаженный.</span><span class="sxs-lookup"><span data-stu-id="c5164-p124">Average ratio of compressed audio samples to the total number of samples. (Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="server-performance-report-metrics-video-call-summary"></a><span data-ttu-id="c5164-243">Показатели отчета о производительности серверов: сводка по видеозвонкам</span><span class="sxs-lookup"><span data-stu-id="c5164-243">Server Performance Report Metrics: Video Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c5164-244">Имя</span><span class="sxs-lookup"><span data-stu-id="c5164-244">Name</span></span></th>
<th><span data-ttu-id="c5164-245">Поддержка сортировки</span><span class="sxs-lookup"><span data-stu-id="c5164-245">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="c5164-246">Описание</span><span class="sxs-lookup"><span data-stu-id="c5164-246">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c5164-247"><strong>Тип звонка и конечной точки</strong></span><span class="sxs-lookup"><span data-stu-id="c5164-247"><strong>Call type/Endpoint type</strong></span></span></p></td>
<td><p><span data-ttu-id="c5164-248">Нет</span><span class="sxs-lookup"><span data-stu-id="c5164-248">No</span></span></p></td>
<td><p><span data-ttu-id="c5164-p125">При щелчке этого элемента отчет предоставляет подробные сведения о звонках, основанных на этом типе. Типы звонков:</span><span class="sxs-lookup"><span data-stu-id="c5164-p125">When you click this item, the report shows detailed information about calls based on that type. Call types include:</span></span></p>
<ul>
<li><p><span data-ttu-id="c5164-251">Одноранговые звонки по объединенным коммуникациям</span><span class="sxs-lookup"><span data-stu-id="c5164-251">UC Peer-to-Peer Calls</span></span></p></li>
<li><p><span data-ttu-id="c5164-252">Сеансы конференц-связи по объединенным коммуникациям</span><span class="sxs-lookup"><span data-stu-id="c5164-252">UC Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="c5164-253">Сеансы конференц-связи по ТСОП</span><span class="sxs-lookup"><span data-stu-id="c5164-253">PSTN Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="c5164-254">Звонки по ТСОП: обходной канал передачи медиаданных</span><span class="sxs-lookup"><span data-stu-id="c5164-254">PSTN Calls: Media Bypass</span></span></p></li>
<li><p><span data-ttu-id="c5164-255">Звонки по ТСОП (без обхода): ветвь объединенных коммуникаций</span><span class="sxs-lookup"><span data-stu-id="c5164-255">PSTN Calls (Non-Bypass): UC Leg</span></span></p></li>
<li><p><span data-ttu-id="c5164-256">Звонки по ТСОП (без обхода): ветвь шлюза</span><span class="sxs-lookup"><span data-stu-id="c5164-256">PSTN Calls (Non-Bypass): Gateway Leg</span></span></p></li>
<li><p><span data-ttu-id="c5164-257">Другие типы звонков</span><span class="sxs-lookup"><span data-stu-id="c5164-257">Other Call Types</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5164-258"><strong>Громкость вызова</strong></span><span class="sxs-lookup"><span data-stu-id="c5164-258"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="c5164-259">Нет</span><span class="sxs-lookup"><span data-stu-id="c5164-259">No</span></span></p></td>
<td><p><span data-ttu-id="c5164-260">Общее количество звонков на тип звонка.</span><span class="sxs-lookup"><span data-stu-id="c5164-260">Total number of calls per call type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5164-261"><strong>Процент звонков низкого качества</strong></span><span class="sxs-lookup"><span data-stu-id="c5164-261"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="c5164-262">Нет</span><span class="sxs-lookup"><span data-stu-id="c5164-262">No</span></span></p></td>
<td><p><span data-ttu-id="c5164-p126">Общее количество звонков, классифицированных как звонки низкого качества. Звонок низкого качества – это любой звонок, хотя бы одна метрика которого превышает допустимое значение (например, звонок с чрезмерным дрожанием).</span><span class="sxs-lookup"><span data-stu-id="c5164-p126">Total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5164-265"><strong>Объем звонков (звонок по беспроводной сети)</strong></span><span class="sxs-lookup"><span data-stu-id="c5164-265"><strong>Call volume (wireless call)</strong></span></span></p></td>
<td><p><span data-ttu-id="c5164-266">Нет</span><span class="sxs-lookup"><span data-stu-id="c5164-266">No</span></span></p></td>
<td><p><span data-ttu-id="c5164-267">Общее количество звонков, при которых используется беспроводное подключение.</span><span class="sxs-lookup"><span data-stu-id="c5164-267">Total number of calls that used a wireless connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5164-268"><strong>Объем звонков (звонок по сети VPN)</strong></span><span class="sxs-lookup"><span data-stu-id="c5164-268"><strong>Call volume (VPN call)</strong></span></span></p></td>
<td><p><span data-ttu-id="c5164-269">Нет</span><span class="sxs-lookup"><span data-stu-id="c5164-269">No</span></span></p></td>
<td><p><span data-ttu-id="c5164-270">Общее количество звонков, при которых используется подключение по сети VPN.</span><span class="sxs-lookup"><span data-stu-id="c5164-270">Total number of calls that used a VPN connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5164-271"><strong>Объем звонков (внешний звонок)</strong></span><span class="sxs-lookup"><span data-stu-id="c5164-271"><strong>Call volume (external call)</strong></span></span></p></td>
<td><p><span data-ttu-id="c5164-272">Нет</span><span class="sxs-lookup"><span data-stu-id="c5164-272">No</span></span></p></td>
<td><p><span data-ttu-id="c5164-273">Количество звонков, при которых используется внешнее подключение (то есть подключение за пределами внутренней сети).</span><span class="sxs-lookup"><span data-stu-id="c5164-273">Number of calls that used an external connection (that is, a connection outside the internal network).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5164-274"><strong>Средняя скорость потока (кбит/с)</strong></span><span class="sxs-lookup"><span data-stu-id="c5164-274"><strong>Avg bit-rate (Kbits/s)</strong></span></span></p></td>
<td><p><span data-ttu-id="c5164-275">Нет</span><span class="sxs-lookup"><span data-stu-id="c5164-275">No</span></span></p></td>
<td><p><span data-ttu-id="c5164-276">Средняя скорость видеопотока (кбит/с).</span><span class="sxs-lookup"><span data-stu-id="c5164-276">Average video bit rate (in kilobits per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5164-277"><strong>Процент низкой скорости потока</strong></span><span class="sxs-lookup"><span data-stu-id="c5164-277"><strong>Low bit-rate %</strong></span></span></p></td>
<td><p><span data-ttu-id="c5164-278">Нет</span><span class="sxs-lookup"><span data-stu-id="c5164-278">No</span></span></p></td>
<td><p><span data-ttu-id="c5164-279">Процент звонков с низкой скоростью потока.</span><span class="sxs-lookup"><span data-stu-id="c5164-279">Percentage of the call where the bit rate was low.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5164-280"><strong>Потеря исходящих пакетов</strong></span><span class="sxs-lookup"><span data-stu-id="c5164-280"><strong>Outbound packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="c5164-281">Нет</span><span class="sxs-lookup"><span data-stu-id="c5164-281">No</span></span></p></td>
<td><p><span data-ttu-id="c5164-p127">Потеря исходящих пакетов RTP. Потеря пакетов происходит, когда пакеты протокола RTP, используемого для передачи аудио и видео через Интернет, не достигают точки назначения. Причиной высокого процента потерь может быть перегрузка сети, нехватка пропускной способности, радиопомехи беспроводной связи или перегрузка сервера мультимедиа. Потеря пакетов обычно приводит к искажению или пропаданию звука.</span><span class="sxs-lookup"><span data-stu-id="c5164-p127">Real-Time Transport Protocol (RTP) packet loss for outbound packets. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5164-285"><strong>Процент остановленных кадров</strong></span><span class="sxs-lookup"><span data-stu-id="c5164-285"><strong>Frozen frame %</strong></span></span></p></td>
<td><p><span data-ttu-id="c5164-286">Нет</span><span class="sxs-lookup"><span data-stu-id="c5164-286">No</span></span></p></td>
<td><p><span data-ttu-id="c5164-p128">Процент "остановленных" кадров. При остановке кадров видео не воспроизводится, а звук продолжает воспроизводиться.</span><span class="sxs-lookup"><span data-stu-id="c5164-p128">Percentage of “frozen” frames. In a frozen frame, the video stops advancing while the audio portion of the call continues.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5164-289"><strong>Средняя частота кадров исходящего сигнала</strong></span><span class="sxs-lookup"><span data-stu-id="c5164-289"><strong>Outbound avg frame rate</strong></span></span></p></td>
<td><p><span data-ttu-id="c5164-290">Нет</span><span class="sxs-lookup"><span data-stu-id="c5164-290">No</span></span></p></td>
<td><p><span data-ttu-id="c5164-291">Средняя частота кадров исходящей передачи во время вызова.</span><span class="sxs-lookup"><span data-stu-id="c5164-291">Average frame rate for outbound transmissions during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5164-292"><strong>Средняя частота входящих кадров (%)</strong></span><span class="sxs-lookup"><span data-stu-id="c5164-292"><strong>Inbound avg frame rate</strong></span></span></p></td>
<td><p><span data-ttu-id="c5164-293">Нет</span><span class="sxs-lookup"><span data-stu-id="c5164-293">No</span></span></p></td>
<td><p><span data-ttu-id="c5164-294">Средняя частота кадров входящей передачи во время вызова.</span><span class="sxs-lookup"><span data-stu-id="c5164-294">Average frame rate for incoming transmissions during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5164-295"><strong>Низкая частота входящих кадров (%)</strong></span><span class="sxs-lookup"><span data-stu-id="c5164-295"><strong>Inbound low frame rate %</strong></span></span></p></td>
<td><p><span data-ttu-id="c5164-296">Нет</span><span class="sxs-lookup"><span data-stu-id="c5164-296">No</span></span></p></td>
<td><p><span data-ttu-id="c5164-297">Процент звонков с низкой скоростью входящего видеопотока.</span><span class="sxs-lookup"><span data-stu-id="c5164-297">Percentage of the call where the bit rate for incoming video was low.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5164-298"><strong>Работоспособность клиента (%)</strong></span><span class="sxs-lookup"><span data-stu-id="c5164-298"><strong>Client health %</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c5164-299">Показывает относительную работоспособность клиентского устройства во время вызова.</span><span class="sxs-lookup"><span data-stu-id="c5164-299">Indicates the relative health of the client device during the call.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="server-performance-report-metrics-application-sharing-call-summary"></a><span data-ttu-id="c5164-300">Показатели отчета о производительности серверов: сводка по сеансам общего доступа к приложениям</span><span class="sxs-lookup"><span data-stu-id="c5164-300">Server Performance Report Metrics: Application Sharing Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c5164-301">Имя</span><span class="sxs-lookup"><span data-stu-id="c5164-301">Name</span></span></th>
<th><span data-ttu-id="c5164-302">Поддержка сортировки</span><span class="sxs-lookup"><span data-stu-id="c5164-302">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="c5164-303">Описание</span><span class="sxs-lookup"><span data-stu-id="c5164-303">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c5164-304"><strong>Тип звонка и конечной точки</strong></span><span class="sxs-lookup"><span data-stu-id="c5164-304"><strong>Call type/Endpoint type</strong></span></span></p></td>
<td><p><span data-ttu-id="c5164-305">Нет</span><span class="sxs-lookup"><span data-stu-id="c5164-305">No</span></span></p></td>
<td><p><span data-ttu-id="c5164-p129">При щелчке этого элемента отчет предоставляет подробные сведения о звонках, основанных на этом типе. Типы звонков:</span><span class="sxs-lookup"><span data-stu-id="c5164-p129">When you click this item, the report shows detailed information about calls based on that type. Call types include:</span></span></p>
<ul>
<li><p><span data-ttu-id="c5164-308">Одноранговые звонки по объединенным коммуникациям</span><span class="sxs-lookup"><span data-stu-id="c5164-308">UC Peer-to-Peer Calls</span></span></p></li>
<li><p><span data-ttu-id="c5164-309">Сеансы конференц-связи по объединенным коммуникациям</span><span class="sxs-lookup"><span data-stu-id="c5164-309">UC Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="c5164-310">Сеансы конференц-связи по ТСОП</span><span class="sxs-lookup"><span data-stu-id="c5164-310">PSTN Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="c5164-311">Звонки по ТСОП: обходной канал передачи медиаданных</span><span class="sxs-lookup"><span data-stu-id="c5164-311">PSTN Calls: Media Bypass</span></span></p></li>
<li><p><span data-ttu-id="c5164-312">Звонки по ТСОП (без обхода): ветвь объединенных коммуникаций</span><span class="sxs-lookup"><span data-stu-id="c5164-312">PSTN Calls (Non-Bypass): UC Leg</span></span></p></li>
<li><p><span data-ttu-id="c5164-313">Звонки по ТСОП (без обхода): ветвь шлюза</span><span class="sxs-lookup"><span data-stu-id="c5164-313">PSTN Calls (Non-Bypass): Gateway Leg</span></span></p></li>
<li><p><span data-ttu-id="c5164-314">Другие типы звонков</span><span class="sxs-lookup"><span data-stu-id="c5164-314">Other Call Types</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5164-315"><strong>Громкость вызова</strong></span><span class="sxs-lookup"><span data-stu-id="c5164-315"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="c5164-316">Нет</span><span class="sxs-lookup"><span data-stu-id="c5164-316">No</span></span></p></td>
<td><p><span data-ttu-id="c5164-317">Общее количество звонков на тип звонка.</span><span class="sxs-lookup"><span data-stu-id="c5164-317">Total number of calls per call type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5164-318"><strong>Процент звонков низкого качества</strong></span><span class="sxs-lookup"><span data-stu-id="c5164-318"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="c5164-319">Нет</span><span class="sxs-lookup"><span data-stu-id="c5164-319">No</span></span></p></td>
<td><p><span data-ttu-id="c5164-p130">Общее количество звонков, классифицированных как звонки низкого качества. Звонок низкого качества – это любой звонок, хотя бы одна метрика которого превышает допустимое значение (например, звонок с чрезмерным дрожанием).</span><span class="sxs-lookup"><span data-stu-id="c5164-p130">Total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5164-322"><strong>Объем звонков (звонок по беспроводной сети)</strong></span><span class="sxs-lookup"><span data-stu-id="c5164-322"><strong>Call volume (wireless call)</strong></span></span></p></td>
<td><p><span data-ttu-id="c5164-323">Нет</span><span class="sxs-lookup"><span data-stu-id="c5164-323">No</span></span></p></td>
<td><p><span data-ttu-id="c5164-324">Общее количество звонков, при которых используется беспроводное подключение.</span><span class="sxs-lookup"><span data-stu-id="c5164-324">Total number of calls that used a wireless connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5164-325"><strong>Объем звонков (звонок по сети VPN)</strong></span><span class="sxs-lookup"><span data-stu-id="c5164-325"><strong>Call volume (VPN call)</strong></span></span></p></td>
<td><p><span data-ttu-id="c5164-326">Нет</span><span class="sxs-lookup"><span data-stu-id="c5164-326">No</span></span></p></td>
<td><p><span data-ttu-id="c5164-327">Общее количество звонков, при которых используется подключение по сети VPN.</span><span class="sxs-lookup"><span data-stu-id="c5164-327">Total number of calls that used a VPN connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5164-328"><strong>Объем звонков (внешний звонок)</strong></span><span class="sxs-lookup"><span data-stu-id="c5164-328"><strong>Call volume (external call)</strong></span></span></p></td>
<td><p><span data-ttu-id="c5164-329">Нет</span><span class="sxs-lookup"><span data-stu-id="c5164-329">No</span></span></p></td>
<td><p><span data-ttu-id="c5164-330">Количество звонков, при которых используется внешнее подключение (то есть подключение за пределами внутренней сети).</span><span class="sxs-lookup"><span data-stu-id="c5164-330">Number of calls that used an external connection (that is, a connection outside the internal network).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5164-331"><strong>Дрожание (мс)</strong></span><span class="sxs-lookup"><span data-stu-id="c5164-331"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="c5164-332">Нет</span><span class="sxs-lookup"><span data-stu-id="c5164-332">No</span></span></p></td>
<td><p><span data-ttu-id="c5164-333">Среднее значение колебаний, зарегистрированных между прибытиями пакетов RTP.</span><span class="sxs-lookup"><span data-stu-id="c5164-333">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="c5164-334">(Колебание — это мера &quot;шакинесс&quot; звонка). Обычно значения с высокой степенью колебаний заключаются в результате перегруженности или перегруженного сервера мультимедиа, что приводит к искажению или потере звука.</span><span class="sxs-lookup"><span data-stu-id="c5164-334">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5164-335"><strong>Средняя относительная задержка в одну сторону</strong></span><span class="sxs-lookup"><span data-stu-id="c5164-335"><strong>Avg. relative one way</strong></span></span></p></td>
<td><p><span data-ttu-id="c5164-336">Нет</span><span class="sxs-lookup"><span data-stu-id="c5164-336">No</span></span></p></td>
<td><p><span data-ttu-id="c5164-p132">Средняя относительная задержка в одну сторону между двумя конечными точками медиаданных. Это мера односкачковой задержки.</span><span class="sxs-lookup"><span data-stu-id="c5164-p132">Average relative one-way delay between two media endpoints. This is a single-hop latency measure.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5164-339"><strong>Средняя задержка обработки элемента RDP</strong></span><span class="sxs-lookup"><span data-stu-id="c5164-339"><strong>Avg. RDP tile processing latency</strong></span></span></p></td>
<td><p><span data-ttu-id="c5164-340">Нет</span><span class="sxs-lookup"><span data-stu-id="c5164-340">No</span></span></p></td>
<td><p><span data-ttu-id="c5164-p133">Среднее значение задержки обработки элементов RDP на сервере конференц-связи общего доступа к приложениям во время сеанса просмотра. Этот показатель не охватывает задержку передачи данных в сети. Высокое среднее значение отражает более длительную задержку при просмотре. На перегруженном сервере конференц-связи могут происходить в среднем более длительные задержки.</span><span class="sxs-lookup"><span data-stu-id="c5164-p133">The average RDP tile processing latency in the AS Conferencing Server over the duration of the viewing session. This metric does not cover network latency. A high average reflects a longer delay in the viewing experience. An overloaded conferencing server may experience higher average delays.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5164-345"><strong>Процент испорченных элементов</strong></span><span class="sxs-lookup"><span data-stu-id="c5164-345"><strong>Total spoiled tile %</strong></span></span></p></td>
<td><p><span data-ttu-id="c5164-346">Нет</span><span class="sxs-lookup"><span data-stu-id="c5164-346">No</span></span></p></td>
<td><p><span data-ttu-id="c5164-347">Итоговый процент испорченных элементов RDP.</span><span class="sxs-lookup"><span data-stu-id="c5164-347">Total percentage of spoiled RDP tiles.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

