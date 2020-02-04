---
title: 'Сервер Lync Server 2013: отчет о расположении'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Location Report
ms:assetid: cb2f1551-1e21-4f13-a39d-91f5f9010ccf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615035(v=OCS.15)
ms:contentKeyID: 48185641
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4bb42f32313acd3609b21180ddaef90c53c27564
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762157"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="location-report-in-lync-server-2013"></a><span data-ttu-id="3addd-102">Отчет о расположении в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3addd-102">Location Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3addd-103">_**Тема последнего изменения:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="3addd-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="3addd-p101">Отчет о местоположениях (Location Report) предоставляет сведения о показателях качества звонков, сгруппированных по расположению в сети (по подсети). Если ваши пользователи испытывают проблемы со звонками, то данный отчет поможет выявить конкретное местоположение проблемы.</span><span class="sxs-lookup"><span data-stu-id="3addd-p101">The Location Report provides information about call quality metrics grouped by network location (that is, by network subnet). If your users are experiencing problems with their calls, this report can help you determine if those problems are widespread or if they are largely confined to a given network segment.</span></span>

<div>

## <a name="accessing-the-location-report"></a><span data-ttu-id="3addd-106">Получение доступа к отчету о местоположениях</span><span class="sxs-lookup"><span data-stu-id="3addd-106">Accessing the Location Report</span></span>

<span data-ttu-id="3addd-p102">Отчет доступен на главной странице отчетов сервера мониторинга. Отчет Call List Report можно детализировать, щелкнув один из следующих показателей:</span><span class="sxs-lookup"><span data-stu-id="3addd-p102">The Location Report is accessed from the Monitoring Reports home page. You can drill down to the Call List Report by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="3addd-109">Громкость вызова</span><span class="sxs-lookup"><span data-stu-id="3addd-109">Call volume</span></span>

  - <span data-ttu-id="3addd-110">Процент звонков низкого качества</span><span class="sxs-lookup"><span data-stu-id="3addd-110">Poor call percentage</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="3addd-111">Фильтры</span><span class="sxs-lookup"><span data-stu-id="3addd-111">Filters</span></span>

<span data-ttu-id="3addd-112">Фильтры предоставляют способ возврата более точного набора данных в соответствии с заданными критериями или просмотра возвращенных данных другими способами.</span><span class="sxs-lookup"><span data-stu-id="3addd-112">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="3addd-113">Например, в отчете можно фильтровать данные по месту произведения звонка и типу используемой сети.</span><span class="sxs-lookup"><span data-stu-id="3addd-113">For example, the Location Report enables you to filter on such things as the location where a call was originated or whether the call took place on a wireless or a wired connection.</span></span> <span data-ttu-id="3addd-114">Также можно выбрать способ группирования данных.</span><span class="sxs-lookup"><span data-stu-id="3addd-114">You can also choose how data should be grouped.</span></span> <span data-ttu-id="3addd-115">В данном случае данные группируются по часам, дню, неделе и месяцу.</span><span class="sxs-lookup"><span data-stu-id="3addd-115">In this case, calls are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="3addd-116">В следующей таблице приведены фильтры, доступные для использования с отчетом.</span><span class="sxs-lookup"><span data-stu-id="3addd-116">The following table lists the filters that you can use with the Location Report.</span></span>

### <a name="location-report-filters"></a><span data-ttu-id="3addd-117">Фильтры отчета о местоположениях</span><span class="sxs-lookup"><span data-stu-id="3addd-117">Location Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3addd-118">Имя</span><span class="sxs-lookup"><span data-stu-id="3addd-118">Name</span></span></th>
<th><span data-ttu-id="3addd-119">Описание</span><span class="sxs-lookup"><span data-stu-id="3addd-119">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3addd-120"><strong>От</strong></span><span class="sxs-lookup"><span data-stu-id="3addd-120"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="3addd-p104">Начальные дата/время для временного диапазона. Чтобы просмотреть данные по часам, введите начальные дату и время следующим образом:</span><span class="sxs-lookup"><span data-stu-id="3addd-p104">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="3addd-123">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="3addd-123">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="3addd-p105">Если вы не вводите начальное время, отчет автоматически начинается с 12:00 AM указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</span><span class="sxs-lookup"><span data-stu-id="3addd-p105">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="3addd-126">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="3addd-126">7/7/2012</span></span></p>
<p><span data-ttu-id="3addd-127">Чтобы просмотреть данные за неделю или месяц, введите дату, выпадающую на любое время в рамках недели или месяца, которые вы хотите просмотреть (вам не требуется вводить первый день недели или месяца):</span><span class="sxs-lookup"><span data-stu-id="3addd-127">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="3addd-128">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="3addd-128">7/3/2012</span></span></p>
<p><span data-ttu-id="3addd-129">Недели всегда отсчитываются с воскресенья по субботу.</span><span class="sxs-lookup"><span data-stu-id="3addd-129">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3addd-130"><strong>До</strong></span><span class="sxs-lookup"><span data-stu-id="3addd-130"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="3addd-p106">Конечные дата/время для временного диапазона. Чтобы просмотреть данные по часам, введите конечные дату и время следующим образом:</span><span class="sxs-lookup"><span data-stu-id="3addd-p106">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="3addd-133">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="3addd-133">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="3addd-p107">Если вы не вводите конечное время, отчет автоматически заканчивается в 12:00 AM указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</span><span class="sxs-lookup"><span data-stu-id="3addd-p107">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="3addd-136">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="3addd-136">7/7/2012</span></span></p>
<p><span data-ttu-id="3addd-137">Чтобы просмотреть данные за неделю или месяц, введите дату, выпадающую на любое время в рамках недели или месяца, которые вы хотите просмотреть (вам не требуется вводить первый день недели или месяца):</span><span class="sxs-lookup"><span data-stu-id="3addd-137">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="3addd-138">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="3addd-138">7/3/2012</span></span></p>
<p><span data-ttu-id="3addd-139">Недели всегда отсчитываются с воскресенья по субботу.</span><span class="sxs-lookup"><span data-stu-id="3addd-139">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3addd-140"><strong>Местоположение звонящего</strong></span><span class="sxs-lookup"><span data-stu-id="3addd-140"><strong>Caller location</strong></span></span></p></td>
<td><p><span data-ttu-id="3addd-p108">IP-подсеть пользователя, выполнявшего звонок. Можно выбрать только значение <strong>[Все]</strong> для указания всех подсетей.</span><span class="sxs-lookup"><span data-stu-id="3addd-p108">IP subnet of the user who placed the call. You can only select <strong>[All]</strong> to indicate all subnets.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3addd-143"><strong>Местоположение принимающего звонок</strong></span><span class="sxs-lookup"><span data-stu-id="3addd-143"><strong>Callee location</strong></span></span></p></td>
<td><p><span data-ttu-id="3addd-p109">IP-подсеть пользователя, выполнявшего звонок. Можно выбрать только значение <strong>[Все]</strong> для указания всех подсетей.</span><span class="sxs-lookup"><span data-stu-id="3addd-p109">IP subnet of the user who received the call. You can only select <strong>[All]</strong> to indicate all subnets.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3addd-146"><strong>Тип сети</strong></span><span class="sxs-lookup"><span data-stu-id="3addd-146"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="3addd-p110">Определяет тип сети, к которой был подключен клиент при выполнении вызова. Выберите один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="3addd-p110">Indicates the type of network the client was connected to when the call was placed. Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="3addd-149">[All] (Все)</span><span class="sxs-lookup"><span data-stu-id="3addd-149">[All]</span></span></p></li>
<li><p><span data-ttu-id="3addd-150">Проводная</span><span class="sxs-lookup"><span data-stu-id="3addd-150">Wired</span></span></p></li>
<li><p><span data-ttu-id="3addd-151">Беспроводная</span><span class="sxs-lookup"><span data-stu-id="3addd-151">Wireless</span></span></p></li>
</ol></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3addd-152"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="3addd-152"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="3addd-p111">Указывает, использовал ли внешний клиент подключение посредством виртуальной частной сети (VPN) при выполнении вызова. Выберите один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="3addd-p111">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed. Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="3addd-155">[All] (Все)</span><span class="sxs-lookup"><span data-stu-id="3addd-155">[All]</span></span></p></li>
<li><p><span data-ttu-id="3addd-156">VPN;</span><span class="sxs-lookup"><span data-stu-id="3addd-156">VPN</span></span></p></li>
<li><p><span data-ttu-id="3addd-157">Не VPN</span><span class="sxs-lookup"><span data-stu-id="3addd-157">Non-VPN</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="3addd-158">Показатели</span><span class="sxs-lookup"><span data-stu-id="3addd-158">Metrics</span></span>

<span data-ttu-id="3addd-159">В следующей таблице перечислены сведения, предоставляемые в отчете о местоположениях.</span><span class="sxs-lookup"><span data-stu-id="3addd-159">The following table lists the information provided in the Location Report.</span></span>

### <a name="location-report-metrics"></a><span data-ttu-id="3addd-160">Показатели отчета о местоположениях</span><span class="sxs-lookup"><span data-stu-id="3addd-160">Location Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3addd-161">Имя</span><span class="sxs-lookup"><span data-stu-id="3addd-161">Name</span></span></th>
<th><span data-ttu-id="3addd-162">Поддержка сортировки</span><span class="sxs-lookup"><span data-stu-id="3addd-162">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="3addd-163">Описание</span><span class="sxs-lookup"><span data-stu-id="3addd-163">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3addd-164"><strong>Подсеть звонившего</strong></span><span class="sxs-lookup"><span data-stu-id="3addd-164"><strong>Caller subnet</strong></span></span></p></td>
<td><p><span data-ttu-id="3addd-165">Нет</span><span class="sxs-lookup"><span data-stu-id="3addd-165">No</span></span></p></td>
<td><p><span data-ttu-id="3addd-166">IP-подсеть звонившего пользователя.</span><span class="sxs-lookup"><span data-stu-id="3addd-166">IP subnet of the user who placed the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3addd-167"><strong>Подсеть принявшего звонок</strong></span><span class="sxs-lookup"><span data-stu-id="3addd-167"><strong>Callee subnet</strong></span></span></p></td>
<td><p><span data-ttu-id="3addd-168">Нет</span><span class="sxs-lookup"><span data-stu-id="3addd-168">No</span></span></p></td>
<td><p><span data-ttu-id="3addd-169">IP-подсеть пользователя, принявшего звонок.</span><span class="sxs-lookup"><span data-stu-id="3addd-169">IP subnet of the user who received the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3addd-170"><strong>Громкость вызова</strong></span><span class="sxs-lookup"><span data-stu-id="3addd-170"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="3addd-171">Да</span><span class="sxs-lookup"><span data-stu-id="3addd-171">Yes</span></span></p></td>
<td><p><span data-ttu-id="3addd-172">Общее количество выполненных вызовов.</span><span class="sxs-lookup"><span data-stu-id="3addd-172">Total number of calls placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3addd-173"><strong>Процент звонков низкого качества</strong></span><span class="sxs-lookup"><span data-stu-id="3addd-173"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="3addd-174">Да</span><span class="sxs-lookup"><span data-stu-id="3addd-174">Yes</span></span></p></td>
<td><p><span data-ttu-id="3addd-p112">Общие количество звонков, отнесенных к плохим. Плохой звонок – любой звонок, при котором хотя бы один из измеряемых показателей превысил допустимое значение (например, звонок с большими искажения сигнала).</span><span class="sxs-lookup"><span data-stu-id="3addd-p112">Percentage of calls classified as poor calls. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3addd-177"><strong>Круговой путь (мс)</strong></span><span class="sxs-lookup"><span data-stu-id="3addd-177"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="3addd-178">Да</span><span class="sxs-lookup"><span data-stu-id="3addd-178">Yes</span></span></p></td>
<td><p><span data-ttu-id="3addd-p113">Среднее время (в миллисекунда) требуемое для передачи пакета протокола транспорта реального времени (RTP) в другую конечную точку и обратно. Круговой путь в 100 и меньше миллисекунд считается допустимым.</span><span class="sxs-lookup"><span data-stu-id="3addd-p113">Average amount of (in milliseconds) required for a real-time transport protocol (RTP) packet to travel to another endpoint and then back. Round-trip times of 100 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="3addd-p114">Высокие значения прохождения кругового пути могут быть вызваны маршрутизацией международных звонков, неправильной настройкой маршрутизацией или перегрузкой сервера-посредника. Большое время кругового пути приводит к трудностям при обслуживании двунаправленных аудиоразговоров.</span><span class="sxs-lookup"><span data-stu-id="3addd-p114">High round-trip values can be caused by international call routing, a routing misconfiguration, or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3addd-183"><strong>Падение качества (средняя оценка)</strong></span><span class="sxs-lookup"><span data-stu-id="3addd-183"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="3addd-184">Да</span><span class="sxs-lookup"><span data-stu-id="3addd-184">Yes</span></span></p></td>
<td><p><span data-ttu-id="3addd-185">Средняя экспертная оценка падения качества связи во время звонка.</span><span class="sxs-lookup"><span data-stu-id="3addd-185">Average amount of mean opinion score (MOS) degradation experienced during a call.</span></span> <span data-ttu-id="3addd-186">Значения лежат в диапазоне от 0,0 до 5,0.</span><span class="sxs-lookup"><span data-stu-id="3addd-186">Degradation values can range from a low of 0.0 to a high of 5.0.</span></span> <span data-ttu-id="3addd-187">Значение 0,5 или меньшее обозначает допустимое падение качества.</span><span class="sxs-lookup"><span data-stu-id="3addd-187">A value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="3addd-188">Изначально средние оценки рассчитывались на основе оценок, даваемых звонкам пользователями по шкале от 1 до 5.</span><span class="sxs-lookup"><span data-stu-id="3addd-188">Historically, mean options scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="3addd-189">В Lync Server Lync Server использует набор алгоритмов для прогнозирования того, как пользователи будут оценены при звонке.</span><span class="sxs-lookup"><span data-stu-id="3addd-189">In Lync Server, Lync Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="3addd-p116">Большие оценки падения качества могут быть вызваны перегрузкой сети, недостатком пропускной способности, помехами в беспроводной среде, перегрузкой на сервере-посреднике или конечной точке. Падение качества приводит к искажению или потере аудиосигнала.</span><span class="sxs-lookup"><span data-stu-id="3addd-p116">High degradation values can be caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server or endpoint. High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3addd-192"><strong>Потеря пакетов</strong></span><span class="sxs-lookup"><span data-stu-id="3addd-192"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="3addd-193">Да</span><span class="sxs-lookup"><span data-stu-id="3addd-193">Yes</span></span></p></td>
<td><p><span data-ttu-id="3addd-p117">Среднее значение потери RTP-пакетов. (Пакет считается потерянным, если он не дошел до назначения). Большие значения потери пакетов могут быть вызваны перегрузкой сети, недостатком пропускной способности, помехами в беспроводной среде, перегрузкой на сервере-посреднике. Обычно это приводит к искажению или потере аудиосигнала.</span><span class="sxs-lookup"><span data-stu-id="3addd-p117">Average rate of RTP packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3addd-197"><strong>Искажение</strong></span><span class="sxs-lookup"><span data-stu-id="3addd-197"><strong>Jitter</strong></span></span></p></td>
<td><p><span data-ttu-id="3addd-198">Да</span><span class="sxs-lookup"><span data-stu-id="3addd-198">Yes</span></span></p></td>
<td><p><span data-ttu-id="3addd-199">Среднее значение колебаний, зарегистрированных между прибытиями пакетов RTP.</span><span class="sxs-lookup"><span data-stu-id="3addd-199">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="3addd-200">(Колебание — это мера &quot;шакинесс&quot; звонка). Обычно значения с высокой степенью колебаний заключаются в результате перегруженности или перегруженного сервера мультимедиа, что приводит к искажению или потере звука.</span><span class="sxs-lookup"><span data-stu-id="3addd-200">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3addd-201"><strong>Степень маскированных аудиообразцов</strong></span><span class="sxs-lookup"><span data-stu-id="3addd-201"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="3addd-202">Да</span><span class="sxs-lookup"><span data-stu-id="3addd-202">Yes</span></span></p></td>
<td><p><span data-ttu-id="3addd-p119">Средняя степень маскированных аудиообразцов по отношению к общему числу образцов. (Маскирование аудио - это методика, которая применяется для сглаживания оборванной передачи, которая обычно происходит при потери сетевых пакетов). Большие значения обозначают частое применение данной методики, вызванной из-за потери пакетов или искажений сигнала.</span><span class="sxs-lookup"><span data-stu-id="3addd-p119">Average ratio of concealed audio samples to the total to the total number of samples. (A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3addd-205"><strong>Степень растянутых образцов</strong></span><span class="sxs-lookup"><span data-stu-id="3addd-205"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="3addd-206">Да</span><span class="sxs-lookup"><span data-stu-id="3addd-206">Yes</span></span></p></td>
<td><p><span data-ttu-id="3addd-p120">Средняя степень растянутых аудиообразцов по отношению к общему числу образцов. (Растягивание аудиопакета - это методика, которая применяется для поддержания качества звонка при обнаружении потери сетевого пакета). Большие значения обозначают частое применение данной методики, вызванное большими искажениями – аудиосигнал звучит как роботизированный.</span><span class="sxs-lookup"><span data-stu-id="3addd-p120">Average ratio of stretched audio samples to the total to the total number of samples. (Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3addd-209"><strong>Степень сжатых аудиообразцов</strong></span><span class="sxs-lookup"><span data-stu-id="3addd-209"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="3addd-210">Да</span><span class="sxs-lookup"><span data-stu-id="3addd-210">Yes</span></span></p></td>
<td><p><span data-ttu-id="3addd-p121">Средняя степень растянутых аудиообразцов по отношению к общему числу образцов. (Сжатие аудиопакета - это методика, которая применяется для поддержания качества звонка при обнаружении потери сетевого пакета). Большие значения обозначают частое применение данной методики, вызванное большими искажениями – аудиосигнал звучит как ускоренный или искаженный.</span><span class="sxs-lookup"><span data-stu-id="3addd-p121">Average ratio of compressed audio samples to the total number of samples. (Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

