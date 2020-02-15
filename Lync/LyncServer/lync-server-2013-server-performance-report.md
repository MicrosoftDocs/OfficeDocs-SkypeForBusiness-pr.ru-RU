---
title: 'Lync Server 2013: отчет о производительности сервера'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server Performance Report
ms:assetid: 942bb39a-1790-498e-9d99-8f6ce2d155c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615018(v=OCS.15)
ms:contentKeyID: 48184879
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e60757721a9244a55e7ce341be6834934108858a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050701"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-performance-report-in-lync-server-2013"></a><span data-ttu-id="4c8aa-102">Отчет о производительности сервера в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4c8aa-102">Server Performance Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4c8aa-103">_**Последнее изменение темы:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="4c8aa-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="4c8aa-104">В отчете о производительности сервера представлен список серверов Microsoft Lync Server 2013, на которых вы столкнулись с наивысшим процентом неудачных вызовов.</span><span class="sxs-lookup"><span data-stu-id="4c8aa-104">The Server Performance Report provides a list of Microsoft Lync Server 2013 servers that have experienced the highest-percentage of poor calls.</span></span> <span data-ttu-id="4c8aa-105">В отчете сервера распределены по типам, для каждого из них дается статистика следующих видов:</span><span class="sxs-lookup"><span data-stu-id="4c8aa-105">The report breaks down servers by server type, reporting separate statistics for the following types:</span></span>

  - <span data-ttu-id="4c8aa-106">Mediation Server (Сервер-посредник);</span><span class="sxs-lookup"><span data-stu-id="4c8aa-106">Mediation Server</span></span>

  - <span data-ttu-id="4c8aa-107">A/V Conferencing Server (Сервер аудио- и видеоконференций);</span><span class="sxs-lookup"><span data-stu-id="4c8aa-107">A/V Conferencing Server</span></span>

  - <span data-ttu-id="4c8aa-108">A/V Edge Server (Пограничный сервер аудио- и видеоданных);</span><span class="sxs-lookup"><span data-stu-id="4c8aa-108">A/V Edge Server</span></span>

  - <span data-ttu-id="4c8aa-109">Шлюз (сервер-посредник)</span><span class="sxs-lookup"><span data-stu-id="4c8aa-109">Gateway (Mediation Server)</span></span>

  - <span data-ttu-id="4c8aa-110">Шлюз (в обход сервера-посредника)</span><span class="sxs-lookup"><span data-stu-id="4c8aa-110">Gateway (Mediation Server bypass)</span></span>

  - <span data-ttu-id="4c8aa-111">Видео (включая показатели видео для серверов аудио и видеоконференций и соответствующих пограничных серверов)</span><span class="sxs-lookup"><span data-stu-id="4c8aa-111">Video (including video metrics for A/V Conferencing servers and A/V Edge servers)</span></span>

  - <span data-ttu-id="4c8aa-112">Общий доступ к приложениям (включая показатели общего доступа для серверов аудио и видеоконференций и соответствующих пограничных серверов)</span><span class="sxs-lookup"><span data-stu-id="4c8aa-112">Application Sharing (including application sharing metrics for A/V Conferencing servers and A/V Edge servers)</span></span>

<span data-ttu-id="4c8aa-p102">Следует помнить, что ранжирование в данном отчете относительное. Например, предположим что вашем наименее производительном сервере бывает один плохой звонок из 1 000. Это более чем приемлемый показатель в 0,1%. Но данный сервер (при учете того, что у других серверов этот процент еще меньше) все равно будет приведет в отчет о производительности серверов.</span><span class="sxs-lookup"><span data-stu-id="4c8aa-p102">It’s important to note that the ranking shown in this report as relative rankings. For example, suppose your worst-performing server had one poor call among its 1,000 placed calls. That's a more-than-acceptable percentage of .1%. However, if that's the worst-performing server you have (that is, if all your other servers have a poor call percentage even lower than .1%), then that server will still appear on the Server Performance Report.</span></span>

<div>

## <a name="accessing-the-server-performance-report"></a><span data-ttu-id="4c8aa-117">Получение доступа к отчету о производительности серверов</span><span class="sxs-lookup"><span data-stu-id="4c8aa-117">Accessing the Server Performance Report</span></span>

<span data-ttu-id="4c8aa-118">Доступ к отчету можно получить с главный страницы отчетов по мониторингу.</span><span class="sxs-lookup"><span data-stu-id="4c8aa-118">The Server Performance Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="4c8aa-119">Вы можете перейти к [отчету по списку обзвона в Lync Server 2013](lync-server-2013-call-list-report.md) , щелкнув один из следующих показателей:</span><span class="sxs-lookup"><span data-stu-id="4c8aa-119">You can drill down to the [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="4c8aa-120">Call volume (Интенсивность вызовов)</span><span class="sxs-lookup"><span data-stu-id="4c8aa-120">Call volume</span></span>

  - <span data-ttu-id="4c8aa-121">Poor call percentage (Процент звонков низкого качества)</span><span class="sxs-lookup"><span data-stu-id="4c8aa-121">Poor call percentage</span></span>

<span data-ttu-id="4c8aa-122">Также можно детализировать отчет о тренде качестве среды передачи данных сервера, щелкнув один из следующих показателей:</span><span class="sxs-lookup"><span data-stu-id="4c8aa-122">In addition, you can drill down to the Server Media Quality Trend Report by clicking the following metric:</span></span>

  - <span data-ttu-id="4c8aa-123">ТЕНДЕНЦИЯ</span><span class="sxs-lookup"><span data-stu-id="4c8aa-123">Trend</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-server-performance-report"></a><span data-ttu-id="4c8aa-124">Рекомендации по использовании отчета о производительности серверов</span><span class="sxs-lookup"><span data-stu-id="4c8aa-124">Making the Best Use of the Server Performance Report</span></span>

<span data-ttu-id="4c8aa-p104">В отчете есть несколько фильтров данных. Например, можно фильтровать по типу сети (звонки по проводным и беспроводным соединениям) и типу доступа (звонки из-за пределов и изнутри брандмауэра). Рекомендуется использовать данные фильтры при просмотре отчета. Например, предположим что имеется сервер-посредник с процентом плохих звонков 3.24%. Если рассмотреть процент плохих беспроводных звонков, то процент может достигать значения 20%. Это значит, что на данном сервере возникают проблемы при обслуживании беспроводных звонков, эти сведения были скрыты, так как проблем при обслуживании проводных соединений не было.</span><span class="sxs-lookup"><span data-stu-id="4c8aa-p104">The Server Performance Report provides a number of ways to filter data; for example, you can filter on network type (calls made from a wired connection vs. calls made from a wireless connection) and access type (calls made from inside the firewall vs. calls made from outside the firewall). It's a good idea when viewing the server performance report to make use of these filters. For example, suppose you have a Mediation Server that has a poor call percentage of 3.24%. If you look solely at wireless calls, that same server might have a poor call percentage approaching 20%. That means that the server was having difficulty with wireless calls, a problem that is partially obscured because the server was not having problems with wired calls.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="4c8aa-130">Фильтры</span><span class="sxs-lookup"><span data-stu-id="4c8aa-130">Filters</span></span>

<span data-ttu-id="4c8aa-p105">С помощью фильтров можно получить более точный набор данных и просмотреть полученные данные под другим углом. Например, в отчете о производительности серверов можно фильтровать данные по типу сети и серверу. Также можно выбрать способ группирования данных. В данном случае данные группируются по часам, дню, неделе и месяцу.</span><span class="sxs-lookup"><span data-stu-id="4c8aa-p105">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Server Performance Report enables you to do such things as filter the returned data by server type or by network type (that is, wired or wireless). You can also choose how data should be grouped. In this case, data is grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="4c8aa-135">В следующей таблице приведены фильтры, которые можно использовать в отчете о производительности серверов.</span><span class="sxs-lookup"><span data-stu-id="4c8aa-135">The following table lists the filters that you can use with the Server Performance Report.</span></span>

### <a name="server-performance-report-filters"></a><span data-ttu-id="4c8aa-136">Фильтры отчета о производительности серверов</span><span class="sxs-lookup"><span data-stu-id="4c8aa-136">Server Performance Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4c8aa-137">Имя</span><span class="sxs-lookup"><span data-stu-id="4c8aa-137">Name</span></span></th>
<th><span data-ttu-id="4c8aa-138">Описание</span><span class="sxs-lookup"><span data-stu-id="4c8aa-138">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4c8aa-139"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="4c8aa-139"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="4c8aa-p106">Дата и время начала диапазона. Чтобы просмотреть данные по часам, введите дату и время начала в следующем формате:</span><span class="sxs-lookup"><span data-stu-id="4c8aa-p106">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="4c8aa-142">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="4c8aa-142">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="4c8aa-p107">Если не указать время начала, автоматически будет выбрано время 00:00 указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</span><span class="sxs-lookup"><span data-stu-id="4c8aa-p107">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="4c8aa-145">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="4c8aa-145">7/7/2012</span></span></p>
<p><span data-ttu-id="4c8aa-146">Для просмотра по неделям или по месяцам введите дату, выпадающую на любой день недели или месяца, который вы хотите просмотреть (это необязательно должен быть первый день недели или месяца):</span><span class="sxs-lookup"><span data-stu-id="4c8aa-146">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="4c8aa-147">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="4c8aa-147">7/3/2012</span></span></p>
<p><span data-ttu-id="4c8aa-148">Неделя всегда начинается с воскресения и заканчивается субботой.</span><span class="sxs-lookup"><span data-stu-id="4c8aa-148">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c8aa-149"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="4c8aa-149"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="4c8aa-p108">Дата и время окончания диапазона. Чтобы просмотреть данные по часам, введите дату и время окончания в следующем формате:</span><span class="sxs-lookup"><span data-stu-id="4c8aa-p108">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="4c8aa-152">7/7/2012 13:00.</span><span class="sxs-lookup"><span data-stu-id="4c8aa-152">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="4c8aa-p109">Если не указать время окончания, автоматически будет выбрано время 00:00 указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</span><span class="sxs-lookup"><span data-stu-id="4c8aa-p109">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="4c8aa-155">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="4c8aa-155">7/7/2012</span></span></p>
<p><span data-ttu-id="4c8aa-156">Для просмотра по неделям или по месяцам введите дату, выпадающую на любой день недели или месяца, который вы хотите просмотреть (это необязательно должен быть первый день недели или месяца):</span><span class="sxs-lookup"><span data-stu-id="4c8aa-156">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="4c8aa-157">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="4c8aa-157">7/3/2012</span></span></p>
<p><span data-ttu-id="4c8aa-158">Недели всегда начинаются в воскресенье, а заканчиваются в субботу.</span><span class="sxs-lookup"><span data-stu-id="4c8aa-158">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c8aa-159"><strong>Тип сервера</strong></span><span class="sxs-lookup"><span data-stu-id="4c8aa-159"><strong>Server type</strong></span></span></p></td>
<td><p><span data-ttu-id="4c8aa-p110">Обозначает тип сервера, по которому дается сводка о производительности. Выберите один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="4c8aa-p110">Indicates the type of server whose performance should be reported. Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="4c8aa-162">Ко</span><span class="sxs-lookup"><span data-stu-id="4c8aa-162">[All]</span></span></p></li>
<li><p><span data-ttu-id="4c8aa-163">Сервер-посредник</span><span class="sxs-lookup"><span data-stu-id="4c8aa-163">Mediation Server</span></span></p></li>
<li><p><span data-ttu-id="4c8aa-164">A/V Conferencing Server (Сервер аудио- и видеоконференций);</span><span class="sxs-lookup"><span data-stu-id="4c8aa-164">A/V Conferencing Server</span></span></p></li>
<li><p><span data-ttu-id="4c8aa-165">Пограничный сервер аудио и видео</span><span class="sxs-lookup"><span data-stu-id="4c8aa-165">A/V Edge Server</span></span></p></li>
</ol></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c8aa-166"><strong>Первые N</strong></span><span class="sxs-lookup"><span data-stu-id="4c8aa-166"><strong>Top N</strong></span></span></p></td>
<td><p><span data-ttu-id="4c8aa-p111">Обозначает количество серверов (на основе их процента плохих звонков) для отображения в каждой категории. Например, если выбрать значение<strong>5</strong>, то отображается пять хуже всего справляющихся серверов. Выберите один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="4c8aa-p111">Indicates the number of servers (based on their poor call percentage) to be displayed in each category. For example, if you select <strong>5</strong> then the five poorest-performing servers are displayed. Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="4c8aa-170">Ко</span><span class="sxs-lookup"><span data-stu-id="4c8aa-170">[All]</span></span></p></li>
<li><p><span data-ttu-id="4c8aa-171">5 </span><span class="sxs-lookup"><span data-stu-id="4c8aa-171">5</span></span></p></li>
<li><p><span data-ttu-id="4c8aa-172">10 </span><span class="sxs-lookup"><span data-stu-id="4c8aa-172">10</span></span></p></li>
</ol></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c8aa-173"><strong>Тип доступа</strong></span><span class="sxs-lookup"><span data-stu-id="4c8aa-173"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="4c8aa-p112">Указывает, вошел ли клиент из внутренней или внешней сети при выполнении звонка. Выберите одно из значений:</span><span class="sxs-lookup"><span data-stu-id="4c8aa-p112">Indicates whether the client was logged on to the internal network or the external network when the call was placed. Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="4c8aa-176">Ко</span><span class="sxs-lookup"><span data-stu-id="4c8aa-176">[All]</span></span></p></li>
<li><p><span data-ttu-id="4c8aa-177">Внутренний</span><span class="sxs-lookup"><span data-stu-id="4c8aa-177">Internal</span></span></p></li>
<li><p><span data-ttu-id="4c8aa-178">External</span><span class="sxs-lookup"><span data-stu-id="4c8aa-178">External</span></span></p></li>
</ol></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c8aa-179"><strong>Тип сети</strong></span><span class="sxs-lookup"><span data-stu-id="4c8aa-179"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="4c8aa-p113">Указание типа сети, к которой был подключен клиент при выполнении вызова. Выберите одно из значений:</span><span class="sxs-lookup"><span data-stu-id="4c8aa-p113">Indicates the type of network the client was connected to when the call was placed. Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="4c8aa-182">Ко</span><span class="sxs-lookup"><span data-stu-id="4c8aa-182">[All]</span></span></p></li>
<li><p><span data-ttu-id="4c8aa-183">Политик</span><span class="sxs-lookup"><span data-stu-id="4c8aa-183">Wired</span></span></p></li>
<li><p><span data-ttu-id="4c8aa-184">Инфракрас</span><span class="sxs-lookup"><span data-stu-id="4c8aa-184">Wireless</span></span></p></li>
</ol></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c8aa-185"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="4c8aa-185"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="4c8aa-p114">Указывает, использовал ли внешний клиент VPN-подключение при выполнении звонка. Выберите одно из значений:</span><span class="sxs-lookup"><span data-stu-id="4c8aa-p114">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed. Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="4c8aa-188">Ко</span><span class="sxs-lookup"><span data-stu-id="4c8aa-188">[All]</span></span></p></li>
<li><p><span data-ttu-id="4c8aa-189">VPN</span><span class="sxs-lookup"><span data-stu-id="4c8aa-189">VPN</span></span></p></li>
<li><p><span data-ttu-id="4c8aa-190">Не VPN</span><span class="sxs-lookup"><span data-stu-id="4c8aa-190">Non-VPN</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="4c8aa-191">Метрик</span><span class="sxs-lookup"><span data-stu-id="4c8aa-191">Metrics</span></span>

<span data-ttu-id="4c8aa-192">В следующей таблице приведены сведения, предоставляемы в отчете о производительности серверов.</span><span class="sxs-lookup"><span data-stu-id="4c8aa-192">The following table lists the information provided in the Server Performance Report.</span></span>

### <a name="server-performance-report-metrics-audio-call-summary"></a><span data-ttu-id="4c8aa-193">Показатели отчета о производительности серверов: сводка по голосовым звонкам</span><span class="sxs-lookup"><span data-stu-id="4c8aa-193">Server Performance Report Metrics: Audio Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4c8aa-194">Имя</span><span class="sxs-lookup"><span data-stu-id="4c8aa-194">Name</span></span></th>
<th><span data-ttu-id="4c8aa-195">Можно проводить сортировку</span><span class="sxs-lookup"><span data-stu-id="4c8aa-195">Can Sort On</span></span></th>
<th><span data-ttu-id="4c8aa-196">Описание</span><span class="sxs-lookup"><span data-stu-id="4c8aa-196">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4c8aa-197"><strong>Server</strong></span><span class="sxs-lookup"><span data-stu-id="4c8aa-197"><strong>Server</strong></span></span></p></td>
<td><p><span data-ttu-id="4c8aa-198">Нет</span><span class="sxs-lookup"><span data-stu-id="4c8aa-198">No</span></span></p></td>
<td><p><span data-ttu-id="4c8aa-199">Название/IP-адрес сервера.</span><span class="sxs-lookup"><span data-stu-id="4c8aa-199">Name/IP address of the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c8aa-200"><strong>Объем звонков</strong></span><span class="sxs-lookup"><span data-stu-id="4c8aa-200"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="4c8aa-201">Нет</span><span class="sxs-lookup"><span data-stu-id="4c8aa-201">No</span></span></p></td>
<td><p><span data-ttu-id="4c8aa-202">Общее количество сделанных звонков.</span><span class="sxs-lookup"><span data-stu-id="4c8aa-202">Total number of calls made.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c8aa-203"><strong>Процент плохих звонков</strong></span><span class="sxs-lookup"><span data-stu-id="4c8aa-203"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="4c8aa-204">Нет</span><span class="sxs-lookup"><span data-stu-id="4c8aa-204">No</span></span></p></td>
<td><p><span data-ttu-id="4c8aa-p115">Общие количество звонков отнесенных к плохим. Плохой звонок — любой звонок, при котором хотя бы один из измеряемых показателей превысил допустимое значение (например, звонок с большими искажения сигнала).</span><span class="sxs-lookup"><span data-stu-id="4c8aa-p115">Total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c8aa-207"><strong>Круговой путь (мс)</strong></span><span class="sxs-lookup"><span data-stu-id="4c8aa-207"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="4c8aa-208">Да</span><span class="sxs-lookup"><span data-stu-id="4c8aa-208">Yes</span></span></p></td>
<td><p><span data-ttu-id="4c8aa-p116">Среднее время (в миллисекунда) требуемое для передачи пакета протокола транспорта реального времени (RTP) в другую конечную точку и обратно. Круговой путь в 100 и меньше миллисекунд считается допустимым.</span><span class="sxs-lookup"><span data-stu-id="4c8aa-p116">Average amount of (in milliseconds) required for a real-time transport protocol (RTP) packet to travel to another endpoint and then back. Round-trip times of 100 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="4c8aa-p117">Высокие значения прохождения кругового пути могут быть вызваны маршрутизацией международных звонков, неправильной настройкой маршрутизацией или перегрузкой сервера-посредника. Большое время кругового пути приводит к трудностям при обслуживании двунаправленных аудиоразговоров.</span><span class="sxs-lookup"><span data-stu-id="4c8aa-p117">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c8aa-213"><strong>Падение качества (средняя оценка)</strong></span><span class="sxs-lookup"><span data-stu-id="4c8aa-213"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="4c8aa-214">Да</span><span class="sxs-lookup"><span data-stu-id="4c8aa-214">Yes</span></span></p></td>
<td><p><span data-ttu-id="4c8aa-215">Средний объем деградации в соответствии со средней экспертной оценкой разборчивости речи (MOS), наблюдаемый в ходе вызова.</span><span class="sxs-lookup"><span data-stu-id="4c8aa-215">Average amount of mean opinion score (MOS) degradation experienced during a call.</span></span> <span data-ttu-id="4c8aa-216">Значение снижения может быть в диапазоне от 0.0 до 5.0.</span><span class="sxs-lookup"><span data-stu-id="4c8aa-216">Degradation values can range from a low of 0.0 to a high of 5.0.</span></span> <span data-ttu-id="4c8aa-217">Значение не выше 0.5 является приемлемым уровнем снижения.</span><span class="sxs-lookup"><span data-stu-id="4c8aa-217">A value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="4c8aa-218">Традиционно средние экспертные оценки разборчивости речи вычислялись по оценкам пользователей качества вызова по шкале от 1 до 5.</span><span class="sxs-lookup"><span data-stu-id="4c8aa-218">Historically, mean options scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="4c8aa-219">В Lync Server сервер мониторинга использует набор алгоритмов для прогнозирования того, как пользователи будут оценены при вызове.</span><span class="sxs-lookup"><span data-stu-id="4c8aa-219">In Lync Server, the Monitoring Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="4c8aa-p119">Высокие значения снижения могут быть вызваны перегруженностью, нехваткой пропускной способности, перегруженность или помехами в беспроводной сети, а также перегруженностью сервера мультимедиа или конечной точки. Высокие значения могут привести к искажению или потере звука.</span><span class="sxs-lookup"><span data-stu-id="4c8aa-p119">High degradation values can be caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server or endpoint. High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c8aa-222"><strong>Потеря пакетов</strong></span><span class="sxs-lookup"><span data-stu-id="4c8aa-222"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="4c8aa-223">Да</span><span class="sxs-lookup"><span data-stu-id="4c8aa-223">Yes</span></span></p></td>
<td><p><span data-ttu-id="4c8aa-p120">Среднее значение потери RTP-пакетов. (Пакет считается потерянным, если он не дошел до назначения). Большие значения потери пакетов могут быть вызваны перегрузкой сети, недостатком пропускной способности, помехами в беспроводной среде, перегрузкой на сервере-посреднике. Обычно это приводит к искажению или потере аудиосигнала.</span><span class="sxs-lookup"><span data-stu-id="4c8aa-p120">Average rate of real-time transport protocol (RTP) packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c8aa-227"><strong>Дрожание (мс)</strong></span><span class="sxs-lookup"><span data-stu-id="4c8aa-227"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="4c8aa-228">Да</span><span class="sxs-lookup"><span data-stu-id="4c8aa-228">Yes</span></span></p></td>
<td><p><span data-ttu-id="4c8aa-229">Среднее значение колебаний, зарегистрированных между прибытиями пакетов RTP.</span><span class="sxs-lookup"><span data-stu-id="4c8aa-229">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="4c8aa-230">(Колебание — это мера &quot;вибрирования&quot; вызова.) Большие значения колебаний обычно вызваны перегрузкой или перегрузкой сервера мультимедиа, что приводит к искажению или потере звука.</span><span class="sxs-lookup"><span data-stu-id="4c8aa-230">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c8aa-231"><strong>Соотношение скрытых фрагментов в процессе восстановления</strong></span><span class="sxs-lookup"><span data-stu-id="4c8aa-231"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="4c8aa-232">Да</span><span class="sxs-lookup"><span data-stu-id="4c8aa-232">Yes</span></span></p></td>
<td><p><span data-ttu-id="4c8aa-p122">Среднее отношение количества скрытых аудиофрагментов к общему количеству фрагментов. (Скрытие аудиофрагментов — это метод, используемый для сглаживания резких переходов, которые обычно вызваны пропуском сетевых пакетов.) Высокие значения указывают на высокие уровни скрытия потерь, которые были обусловлены потерей пакетов или колебаниями. Эти высокие значения приводят к искажению звука или потере аудиосигналов.</span><span class="sxs-lookup"><span data-stu-id="4c8aa-p122">Average ratio of concealed audio samples to the total to the total number of samples. (A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c8aa-235"><strong>Соотношение растянутых фрагментов в процессе восстановления</strong></span><span class="sxs-lookup"><span data-stu-id="4c8aa-235"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="4c8aa-236">Да</span><span class="sxs-lookup"><span data-stu-id="4c8aa-236">Yes</span></span></p></td>
<td><p><span data-ttu-id="4c8aa-p123">Среднее отношение количества растянутых аудиофрагментов к общему количеству фрагментов. (Растянутые аудиофрагменты — фрагменты, которые были увеличены для поддержания качества вызова при обнаружении пропуска сетевого пакета.) Высокие значения указывают на значительные уровни растягивания фрагментов, которые были обусловлены колебаниями. Эти высокие значения приводят к искажению звука или к созданию эффекта механического звучания.</span><span class="sxs-lookup"><span data-stu-id="4c8aa-p123">Average ratio of stretched audio samples to the total to the total number of samples. (Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c8aa-239"><strong>Соотношение сжатых фрагментов в процессе восстановления</strong></span><span class="sxs-lookup"><span data-stu-id="4c8aa-239"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="4c8aa-240">Да</span><span class="sxs-lookup"><span data-stu-id="4c8aa-240">Yes</span></span></p></td>
<td><p><span data-ttu-id="4c8aa-p124">Средняя степень растянутых аудиообразцов по отношению к общему числу образцов. (Сжатие аудиопакета - это методика, которая применяется для поддержания качества звонка при обнаружении потери сетевого пакета). Большие значения обозначают частое применение данной методики, вызванное большими искажениями — аудиосигнал звучит как ускоренный или искаженный.</span><span class="sxs-lookup"><span data-stu-id="4c8aa-p124">Average ratio of compressed audio samples to the total number of samples. (Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="server-performance-report-metrics-video-call-summary"></a><span data-ttu-id="4c8aa-243">Показатели отчета о производительности серверов: сводка по видеозвонкам</span><span class="sxs-lookup"><span data-stu-id="4c8aa-243">Server Performance Report Metrics: Video Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4c8aa-244">Имя</span><span class="sxs-lookup"><span data-stu-id="4c8aa-244">Name</span></span></th>
<th><span data-ttu-id="4c8aa-245">Возможность сортировки по этому показателю</span><span class="sxs-lookup"><span data-stu-id="4c8aa-245">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="4c8aa-246">Описание</span><span class="sxs-lookup"><span data-stu-id="4c8aa-246">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4c8aa-247"><strong>Call type/Endpoint type (Тип вызова/тип конечной точки)</strong></span><span class="sxs-lookup"><span data-stu-id="4c8aa-247"><strong>Call type/Endpoint type</strong></span></span></p></td>
<td><p><span data-ttu-id="4c8aa-248">Нет</span><span class="sxs-lookup"><span data-stu-id="4c8aa-248">No</span></span></p></td>
<td><p><span data-ttu-id="4c8aa-p125">Если щелкнуть этот элемент, то отчет покажет подробные сведения о вызовах на основе этого типа. Типы вызовов:</span><span class="sxs-lookup"><span data-stu-id="4c8aa-p125">When you click this item, the report shows detailed information about calls based on that type. Call types include:</span></span></p>
<ul>
<li><p><span data-ttu-id="4c8aa-251">UC Peer-to-Peer Calls (одноранговые вызовы в объединенных коммуникациях);</span><span class="sxs-lookup"><span data-stu-id="4c8aa-251">UC Peer-to-Peer Calls</span></span></p></li>
<li><p><span data-ttu-id="4c8aa-252">UC Conference Sessions (сеансы конференций в объединенных коммуникациях);</span><span class="sxs-lookup"><span data-stu-id="4c8aa-252">UC Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="4c8aa-253">PSTN Conference Sessions (сеансы конференций в ТСОП);</span><span class="sxs-lookup"><span data-stu-id="4c8aa-253">PSTN Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="4c8aa-254">PSTN Calls: Media Bypass (вызовы в ТСОП: обход сервера-посредника);</span><span class="sxs-lookup"><span data-stu-id="4c8aa-254">PSTN Calls: Media Bypass</span></span></p></li>
<li><p><span data-ttu-id="4c8aa-255">PSTN Calls (Non-Bypass): UC Leg (вызовы в ТСОП (без обхода): участок объединенных коммуникаций);</span><span class="sxs-lookup"><span data-stu-id="4c8aa-255">PSTN Calls (Non-Bypass): UC Leg</span></span></p></li>
<li><p><span data-ttu-id="4c8aa-256">PSTN Calls (Non-Bypass): Gateway Leg (вызовы в ТСОП (без обхода): участок шлюза);</span><span class="sxs-lookup"><span data-stu-id="4c8aa-256">PSTN Calls (Non-Bypass): Gateway Leg</span></span></p></li>
<li><p><span data-ttu-id="4c8aa-257">Other Call Types (другие типы вызовов).</span><span class="sxs-lookup"><span data-stu-id="4c8aa-257">Other Call Types</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c8aa-258"><strong>Call volume (Интенсивность вызовов)</strong></span><span class="sxs-lookup"><span data-stu-id="4c8aa-258"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="4c8aa-259">Нет</span><span class="sxs-lookup"><span data-stu-id="4c8aa-259">No</span></span></p></td>
<td><p><span data-ttu-id="4c8aa-260">Общее количество вызовов по типу вызова.</span><span class="sxs-lookup"><span data-stu-id="4c8aa-260">Total number of calls per call type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c8aa-261"><strong>Poor call percentage (Процент звонков низкого качества)</strong></span><span class="sxs-lookup"><span data-stu-id="4c8aa-261"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="4c8aa-262">Нет</span><span class="sxs-lookup"><span data-stu-id="4c8aa-262">No</span></span></p></td>
<td><p><span data-ttu-id="4c8aa-p126">Общее количество звонков, классифицированных как звонки низкого качества. Звонок низкого качества — это любой звонок, хотя бы одна метрика которого превышает допустимое значение (например, звонок с чрезмерным дрожанием).</span><span class="sxs-lookup"><span data-stu-id="4c8aa-p126">Total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c8aa-265"><strong>Call volume (wireless call) (Интенсивность вызовов (беспроводной вызов))</strong></span><span class="sxs-lookup"><span data-stu-id="4c8aa-265"><strong>Call volume (wireless call)</strong></span></span></p></td>
<td><p><span data-ttu-id="4c8aa-266">Нет</span><span class="sxs-lookup"><span data-stu-id="4c8aa-266">No</span></span></p></td>
<td><p><span data-ttu-id="4c8aa-267">Общее количество вызовов, использовавших беспроводное подключение.</span><span class="sxs-lookup"><span data-stu-id="4c8aa-267">Total number of calls that used a wireless connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c8aa-268"><strong>Call volume (VPN call) (Интенсивность вызовов (через VPN))</strong></span><span class="sxs-lookup"><span data-stu-id="4c8aa-268"><strong>Call volume (VPN call)</strong></span></span></p></td>
<td><p><span data-ttu-id="4c8aa-269">Нет</span><span class="sxs-lookup"><span data-stu-id="4c8aa-269">No</span></span></p></td>
<td><p><span data-ttu-id="4c8aa-270">Общее количество вызовов, использовавших подключение через VPN.</span><span class="sxs-lookup"><span data-stu-id="4c8aa-270">Total number of calls that used a VPN connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c8aa-271"><strong>Call volume (external call) (Интенсивность вызовов (внешние вызовы))</strong></span><span class="sxs-lookup"><span data-stu-id="4c8aa-271"><strong>Call volume (external call)</strong></span></span></p></td>
<td><p><span data-ttu-id="4c8aa-272">Нет</span><span class="sxs-lookup"><span data-stu-id="4c8aa-272">No</span></span></p></td>
<td><p><span data-ttu-id="4c8aa-273">Количество вызовов, которые использовали внешнее подключение (т.е. подключение за пределами внутренней сети).</span><span class="sxs-lookup"><span data-stu-id="4c8aa-273">Number of calls that used an external connection (that is, a connection outside the internal network).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c8aa-274"><strong>Avg bit-rate (Kbits/s) (Средняя скорость потока (Кбит/с))</strong></span><span class="sxs-lookup"><span data-stu-id="4c8aa-274"><strong>Avg bit-rate (Kbits/s)</strong></span></span></p></td>
<td><p><span data-ttu-id="4c8aa-275">Нет</span><span class="sxs-lookup"><span data-stu-id="4c8aa-275">No</span></span></p></td>
<td><p><span data-ttu-id="4c8aa-276">Средняя скорость потока видео (в килобитах в секунду).</span><span class="sxs-lookup"><span data-stu-id="4c8aa-276">Average video bit rate (in kilobits per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c8aa-277"><strong>Low bit-rate % (% при низкой скорости потока)</strong></span><span class="sxs-lookup"><span data-stu-id="4c8aa-277"><strong>Low bit-rate %</strong></span></span></p></td>
<td><p><span data-ttu-id="4c8aa-278">Нет</span><span class="sxs-lookup"><span data-stu-id="4c8aa-278">No</span></span></p></td>
<td><p><span data-ttu-id="4c8aa-279">Процент вызовов при низкой скорости потока видео.</span><span class="sxs-lookup"><span data-stu-id="4c8aa-279">Percentage of the call where the bit rate was low.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c8aa-280"><strong>Outbound packet loss (Потеря исходящих пакетов)</strong></span><span class="sxs-lookup"><span data-stu-id="4c8aa-280"><strong>Outbound packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="4c8aa-281">Нет</span><span class="sxs-lookup"><span data-stu-id="4c8aa-281">No</span></span></p></td>
<td><p><span data-ttu-id="4c8aa-p127">Потеря исходящих пакетов RTP. Потеря пакетов происходит, когда пакеты протокола RTP, используемого для передачи аудио и видео через Интернет, не достигают точки назначения. Причиной высокого процента потерь может быть перегрузка сети, нехватка пропускной способности, радиопомехи беспроводной связи или перегрузка сервера мультимедиа. Потеря пакетов обычно приводит к искажению или пропаданию звука.</span><span class="sxs-lookup"><span data-stu-id="4c8aa-p127">Real-Time Transport Protocol (RTP) packet loss for outbound packets. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c8aa-285"><strong>Процент остановленных кадров</strong></span><span class="sxs-lookup"><span data-stu-id="4c8aa-285"><strong>Frozen frame %</strong></span></span></p></td>
<td><p><span data-ttu-id="4c8aa-286">Нет</span><span class="sxs-lookup"><span data-stu-id="4c8aa-286">No</span></span></p></td>
<td><p><span data-ttu-id="4c8aa-p128">Процент "замороженных" кадров. В замороженном кадре видео перестает передаваться, а звуковая часть вызова продолжается.</span><span class="sxs-lookup"><span data-stu-id="4c8aa-p128">Percentage of “frozen” frames. In a frozen frame, the video stops advancing while the audio portion of the call continues.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c8aa-289"><strong>Outbound avg frame rate (Средняя скорость исходящих кадров)</strong></span><span class="sxs-lookup"><span data-stu-id="4c8aa-289"><strong>Outbound avg frame rate</strong></span></span></p></td>
<td><p><span data-ttu-id="4c8aa-290">Нет</span><span class="sxs-lookup"><span data-stu-id="4c8aa-290">No</span></span></p></td>
<td><p><span data-ttu-id="4c8aa-291">Средняя скорость кадров для исходящих передач во время вызова.</span><span class="sxs-lookup"><span data-stu-id="4c8aa-291">Average frame rate for outbound transmissions during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c8aa-292"><strong>Inbound avg frame rate (Средняя скорость входящих кадров)</strong></span><span class="sxs-lookup"><span data-stu-id="4c8aa-292"><strong>Inbound avg frame rate</strong></span></span></p></td>
<td><p><span data-ttu-id="4c8aa-293">Нет</span><span class="sxs-lookup"><span data-stu-id="4c8aa-293">No</span></span></p></td>
<td><p><span data-ttu-id="4c8aa-294">Средняя скорость кадров для входящих передач во время вызова.</span><span class="sxs-lookup"><span data-stu-id="4c8aa-294">Average frame rate for incoming transmissions during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c8aa-295"><strong>Inbound low frame rate % (% вызовов при низкой скорости входящих кадров)</strong></span><span class="sxs-lookup"><span data-stu-id="4c8aa-295"><strong>Inbound low frame rate %</strong></span></span></p></td>
<td><p><span data-ttu-id="4c8aa-296">Нет</span><span class="sxs-lookup"><span data-stu-id="4c8aa-296">No</span></span></p></td>
<td><p><span data-ttu-id="4c8aa-297">Процент вызовов, когда скорость потока входящего видео была низкой.</span><span class="sxs-lookup"><span data-stu-id="4c8aa-297">Percentage of the call where the bit rate for incoming video was low.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c8aa-298"><strong>Client health % (% работоспособности клиента)</strong></span><span class="sxs-lookup"><span data-stu-id="4c8aa-298"><strong>Client health %</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4c8aa-299">Показывает относительную работоспособность клиентского устройства во время вызова.</span><span class="sxs-lookup"><span data-stu-id="4c8aa-299">Indicates the relative health of the client device during the call.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="server-performance-report-metrics-application-sharing-call-summary"></a><span data-ttu-id="4c8aa-300">Показатели отчета о производительности серверов: сводка по сеансам общего доступа к приложениям</span><span class="sxs-lookup"><span data-stu-id="4c8aa-300">Server Performance Report Metrics: Application Sharing Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4c8aa-301">Имя</span><span class="sxs-lookup"><span data-stu-id="4c8aa-301">Name</span></span></th>
<th><span data-ttu-id="4c8aa-302">Возможность сортировки по этому показателю</span><span class="sxs-lookup"><span data-stu-id="4c8aa-302">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="4c8aa-303">Описание</span><span class="sxs-lookup"><span data-stu-id="4c8aa-303">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4c8aa-304"><strong>Call type/Endpoint type (Тип вызова/тип конечной точки)</strong></span><span class="sxs-lookup"><span data-stu-id="4c8aa-304"><strong>Call type/Endpoint type</strong></span></span></p></td>
<td><p><span data-ttu-id="4c8aa-305">Нет</span><span class="sxs-lookup"><span data-stu-id="4c8aa-305">No</span></span></p></td>
<td><p><span data-ttu-id="4c8aa-p129">Если щелкнуть этот элемент, то отчет покажет подробные сведения о вызовах на основе этого типа. Типы вызовов:</span><span class="sxs-lookup"><span data-stu-id="4c8aa-p129">When you click this item, the report shows detailed information about calls based on that type. Call types include:</span></span></p>
<ul>
<li><p><span data-ttu-id="4c8aa-308">UC Peer-to-Peer Calls (одноранговые вызовы в объединенных коммуникациях);</span><span class="sxs-lookup"><span data-stu-id="4c8aa-308">UC Peer-to-Peer Calls</span></span></p></li>
<li><p><span data-ttu-id="4c8aa-309">UC Conference Sessions (сеансы конференций в объединенных коммуникациях);</span><span class="sxs-lookup"><span data-stu-id="4c8aa-309">UC Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="4c8aa-310">PSTN Conference Sessions (сеансы конференций в ТСОП);</span><span class="sxs-lookup"><span data-stu-id="4c8aa-310">PSTN Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="4c8aa-311">PSTN Calls: Media Bypass (вызовы в ТСОП: обход сервера-посредника);</span><span class="sxs-lookup"><span data-stu-id="4c8aa-311">PSTN Calls: Media Bypass</span></span></p></li>
<li><p><span data-ttu-id="4c8aa-312">PSTN Calls (Non-Bypass): UC Leg (вызовы в ТСОП (без обхода): участок объединенных коммуникаций);</span><span class="sxs-lookup"><span data-stu-id="4c8aa-312">PSTN Calls (Non-Bypass): UC Leg</span></span></p></li>
<li><p><span data-ttu-id="4c8aa-313">PSTN Calls (Non-Bypass): Gateway Leg (вызовы в ТСОП (без обхода): участок шлюза);</span><span class="sxs-lookup"><span data-stu-id="4c8aa-313">PSTN Calls (Non-Bypass): Gateway Leg</span></span></p></li>
<li><p><span data-ttu-id="4c8aa-314">Other Call Types (другие типы вызовов).</span><span class="sxs-lookup"><span data-stu-id="4c8aa-314">Other Call Types</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c8aa-315"><strong>Call volume (Интенсивность вызовов)</strong></span><span class="sxs-lookup"><span data-stu-id="4c8aa-315"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="4c8aa-316">Нет</span><span class="sxs-lookup"><span data-stu-id="4c8aa-316">No</span></span></p></td>
<td><p><span data-ttu-id="4c8aa-317">Общее количество вызовов по типу вызова.</span><span class="sxs-lookup"><span data-stu-id="4c8aa-317">Total number of calls per call type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c8aa-318"><strong>Poor call percentage (Процент звонков низкого качества)</strong></span><span class="sxs-lookup"><span data-stu-id="4c8aa-318"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="4c8aa-319">Нет</span><span class="sxs-lookup"><span data-stu-id="4c8aa-319">No</span></span></p></td>
<td><p><span data-ttu-id="4c8aa-p130">Общее количество звонков, классифицированных как звонки низкого качества. Звонок низкого качества — это любой звонок, хотя бы одна метрика которого превышает допустимое значение (например, звонок с чрезмерным дрожанием).</span><span class="sxs-lookup"><span data-stu-id="4c8aa-p130">Total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c8aa-322"><strong>Call volume (wireless call) (Интенсивность вызовов (беспроводной вызов))</strong></span><span class="sxs-lookup"><span data-stu-id="4c8aa-322"><strong>Call volume (wireless call)</strong></span></span></p></td>
<td><p><span data-ttu-id="4c8aa-323">Нет</span><span class="sxs-lookup"><span data-stu-id="4c8aa-323">No</span></span></p></td>
<td><p><span data-ttu-id="4c8aa-324">Общее количество вызовов, использовавших беспроводное подключение.</span><span class="sxs-lookup"><span data-stu-id="4c8aa-324">Total number of calls that used a wireless connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c8aa-325"><strong>Call volume (VPN call) (Интенсивность вызовов (через VPN))</strong></span><span class="sxs-lookup"><span data-stu-id="4c8aa-325"><strong>Call volume (VPN call)</strong></span></span></p></td>
<td><p><span data-ttu-id="4c8aa-326">Нет</span><span class="sxs-lookup"><span data-stu-id="4c8aa-326">No</span></span></p></td>
<td><p><span data-ttu-id="4c8aa-327">Общее количество вызовов, использовавших подключение через VPN.</span><span class="sxs-lookup"><span data-stu-id="4c8aa-327">Total number of calls that used a VPN connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c8aa-328"><strong>Call volume (external call) (Интенсивность вызовов (внешние вызовы))</strong></span><span class="sxs-lookup"><span data-stu-id="4c8aa-328"><strong>Call volume (external call)</strong></span></span></p></td>
<td><p><span data-ttu-id="4c8aa-329">Нет</span><span class="sxs-lookup"><span data-stu-id="4c8aa-329">No</span></span></p></td>
<td><p><span data-ttu-id="4c8aa-330">Количество вызовов, которые использовали внешнее подключение (т.е. подключение за пределами внутренней сети).</span><span class="sxs-lookup"><span data-stu-id="4c8aa-330">Number of calls that used an external connection (that is, a connection outside the internal network).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c8aa-331"><strong>Дрожание (мс)</strong></span><span class="sxs-lookup"><span data-stu-id="4c8aa-331"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="4c8aa-332">Нет</span><span class="sxs-lookup"><span data-stu-id="4c8aa-332">No</span></span></p></td>
<td><p><span data-ttu-id="4c8aa-333">Средний уровень дрожания, определенный между прибытием пакетов протокола RTP.</span><span class="sxs-lookup"><span data-stu-id="4c8aa-333">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="4c8aa-334">(Колебание — это мера &quot;вибрирования&quot; вызова.) Большие значения колебаний обычно вызваны перегрузкой или перегрузкой сервера мультимедиа, что приводит к искажению или потере звука.</span><span class="sxs-lookup"><span data-stu-id="4c8aa-334">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c8aa-335"><strong>Средняя относительная задержка в одну сторону</strong></span><span class="sxs-lookup"><span data-stu-id="4c8aa-335"><strong>Avg. relative one way</strong></span></span></p></td>
<td><p><span data-ttu-id="4c8aa-336">Нет</span><span class="sxs-lookup"><span data-stu-id="4c8aa-336">No</span></span></p></td>
<td><p><span data-ttu-id="4c8aa-p132">Средняя относительная задержка в одну сторону между двумя конечными точками медиаданных. Это мера односкачковой задержки.</span><span class="sxs-lookup"><span data-stu-id="4c8aa-p132">Average relative one-way delay between two media endpoints. This is a single-hop latency measure.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c8aa-339"><strong>Средняя задержка обработки элемента RDP</strong></span><span class="sxs-lookup"><span data-stu-id="4c8aa-339"><strong>Avg. RDP tile processing latency</strong></span></span></p></td>
<td><p><span data-ttu-id="4c8aa-340">Нет</span><span class="sxs-lookup"><span data-stu-id="4c8aa-340">No</span></span></p></td>
<td><p><span data-ttu-id="4c8aa-p133">Среднее значение задержки обработки элементов RDP на сервере конференц-связи общего доступа к приложениям во время сеанса просмотра. Этот показатель не охватывает задержку передачи данных в сети. Высокое среднее значение отражает более длительную задержку при просмотре. На перегруженном сервере конференц-связи могут происходить в среднем более длительные задержки.</span><span class="sxs-lookup"><span data-stu-id="4c8aa-p133">The average RDP tile processing latency in the AS Conferencing Server over the duration of the viewing session. This metric does not cover network latency. A high average reflects a longer delay in the viewing experience. An overloaded conferencing server may experience higher average delays.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c8aa-345"><strong>Total spoiled tile % (Итоговый % испорченных плиток)</strong></span><span class="sxs-lookup"><span data-stu-id="4c8aa-345"><strong>Total spoiled tile %</strong></span></span></p></td>
<td><p><span data-ttu-id="4c8aa-346">Нет</span><span class="sxs-lookup"><span data-stu-id="4c8aa-346">No</span></span></p></td>
<td><p><span data-ttu-id="4c8aa-347">Итоговый процент испорченных плиток протокола RDP.</span><span class="sxs-lookup"><span data-stu-id="4c8aa-347">Total percentage of spoiled RDP tiles.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

