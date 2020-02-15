---
title: 'Lync Server 2013: отчет о расположении'
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
ms.openlocfilehash: 45f7db796a4edab00918b0353e9b635f4615ba9a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046782"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="location-report-in-lync-server-2013"></a><span data-ttu-id="4e22b-102">Отчет о местоположении в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4e22b-102">Location Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4e22b-103">_**Последнее изменение темы:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="4e22b-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="4e22b-p101">Отчет о местоположениях (Location Report) предоставляет сведения о показателях качества звонков, сгруппированных по расположению в сети (по подсети). Если ваши пользователи испытывают проблемы со звонками, то данный отчет поможет выявить конкретное местоположение проблемы.</span><span class="sxs-lookup"><span data-stu-id="4e22b-p101">The Location Report provides information about call quality metrics grouped by network location (that is, by network subnet). If your users are experiencing problems with their calls, this report can help you determine if those problems are widespread or if they are largely confined to a given network segment.</span></span>

<div>

## <a name="accessing-the-location-report"></a><span data-ttu-id="4e22b-106">Получение доступа к отчету о местоположениях</span><span class="sxs-lookup"><span data-stu-id="4e22b-106">Accessing the Location Report</span></span>

<span data-ttu-id="4e22b-p102">Отчет доступен на главной странице отчетов сервера мониторинга. Отчет Call List Report можно детализировать, щелкнув один из следующих показателей:</span><span class="sxs-lookup"><span data-stu-id="4e22b-p102">The Location Report is accessed from the Monitoring Reports home page. You can drill down to the Call List Report by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="4e22b-109">Объем звонков</span><span class="sxs-lookup"><span data-stu-id="4e22b-109">Call volume</span></span>

  - <span data-ttu-id="4e22b-110">Процент плохих звонков</span><span class="sxs-lookup"><span data-stu-id="4e22b-110">Poor call percentage</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="4e22b-111">Фильтры</span><span class="sxs-lookup"><span data-stu-id="4e22b-111">Filters</span></span>

<span data-ttu-id="4e22b-112">Фильтры позволяют получать более точные и актуальные наборы данных или просматривать возвращаемые данные в разных комбинациях.</span><span class="sxs-lookup"><span data-stu-id="4e22b-112">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="4e22b-113">Например, в отчете о расположении можно выполнить фильтрацию по такому адресу, в котором был получен вызов, или от того, использовался ли вызов для беспроводного или проводного подключения.</span><span class="sxs-lookup"><span data-stu-id="4e22b-113">For example, the Location Report enables you to filter on such things as the location where a call was originated or whether the call took place on a wireless or a wired connection.</span></span> <span data-ttu-id="4e22b-114">Кроме того, можно выбрать способ группирования данных.</span><span class="sxs-lookup"><span data-stu-id="4e22b-114">You can also choose how data should be grouped.</span></span> <span data-ttu-id="4e22b-115">В данном случае вызовы группируются по часу, дню, неделе или месяцу.</span><span class="sxs-lookup"><span data-stu-id="4e22b-115">In this case, calls are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="4e22b-116">В следующей таблице перечислены фильтры, которые можно использовать с отчетом о расположении.</span><span class="sxs-lookup"><span data-stu-id="4e22b-116">The following table lists the filters that you can use with the Location Report.</span></span>

### <a name="location-report-filters"></a><span data-ttu-id="4e22b-117">Фильтры отчета о расположениях</span><span class="sxs-lookup"><span data-stu-id="4e22b-117">Location Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4e22b-118">Имя</span><span class="sxs-lookup"><span data-stu-id="4e22b-118">Name</span></span></th>
<th><span data-ttu-id="4e22b-119">Описание</span><span class="sxs-lookup"><span data-stu-id="4e22b-119">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4e22b-120"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="4e22b-120"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="4e22b-p104">Дата и время начала диапазона. Чтобы просмотреть данные по часам, введите дату и время начала в следующем формате:</span><span class="sxs-lookup"><span data-stu-id="4e22b-p104">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="4e22b-123">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="4e22b-123">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="4e22b-p105">Если не указать время начала, автоматически будет выбрано время 00:00 указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</span><span class="sxs-lookup"><span data-stu-id="4e22b-p105">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="4e22b-126">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="4e22b-126">7/7/2012</span></span></p>
<p><span data-ttu-id="4e22b-127">Для просмотра по неделям или по месяцам введите дату, выпадающую на любой день недели или месяца, который вы хотите просмотреть (это необязательно должен быть первый день недели или месяца):</span><span class="sxs-lookup"><span data-stu-id="4e22b-127">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="4e22b-128">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="4e22b-128">7/3/2012</span></span></p>
<p><span data-ttu-id="4e22b-129">Неделя всегда начинается с воскресения и заканчивается субботой.</span><span class="sxs-lookup"><span data-stu-id="4e22b-129">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e22b-130"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="4e22b-130"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="4e22b-p106">Дата и время окончания диапазона. Чтобы просмотреть данные по часам, введите дату и время окончания в следующем формате:</span><span class="sxs-lookup"><span data-stu-id="4e22b-p106">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="4e22b-133">7/7/2012 13:00.</span><span class="sxs-lookup"><span data-stu-id="4e22b-133">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="4e22b-p107">Если не указать время окончания, автоматически будет выбрано время 00:00 указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</span><span class="sxs-lookup"><span data-stu-id="4e22b-p107">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="4e22b-136">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="4e22b-136">7/7/2012</span></span></p>
<p><span data-ttu-id="4e22b-137">Для просмотра по неделям или по месяцам введите дату, выпадающую на любой день недели или месяца, который вы хотите просмотреть (это необязательно должен быть первый день недели или месяца):</span><span class="sxs-lookup"><span data-stu-id="4e22b-137">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="4e22b-138">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="4e22b-138">7/3/2012</span></span></p>
<p><span data-ttu-id="4e22b-139">Неделя всегда начинается с воскресения и заканчивается субботой.</span><span class="sxs-lookup"><span data-stu-id="4e22b-139">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e22b-140"><strong>Местоположение вызывающего абонента</strong></span><span class="sxs-lookup"><span data-stu-id="4e22b-140"><strong>Caller location</strong></span></span></p></td>
<td><p><span data-ttu-id="4e22b-141">IP-подсеть пользователя, который поместил вызов.</span><span class="sxs-lookup"><span data-stu-id="4e22b-141">IP subnet of the user who placed the call.</span></span> <span data-ttu-id="4e22b-142">Вы можете выбрать только <strong>[все]</strong> , чтобы указать все подсети.</span><span class="sxs-lookup"><span data-stu-id="4e22b-142">You can only select <strong>[All]</strong> to indicate all subnets.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e22b-143"><strong>Местоположение вызываемого абонента</strong></span><span class="sxs-lookup"><span data-stu-id="4e22b-143"><strong>Callee location</strong></span></span></p></td>
<td><p><span data-ttu-id="4e22b-144">IP-подсеть пользователя, который получил вызов.</span><span class="sxs-lookup"><span data-stu-id="4e22b-144">IP subnet of the user who received the call.</span></span> <span data-ttu-id="4e22b-145">Вы можете выбрать только <strong>[все]</strong> , чтобы указать все подсети.</span><span class="sxs-lookup"><span data-stu-id="4e22b-145">You can only select <strong>[All]</strong> to indicate all subnets.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e22b-146"><strong>Тип сети</strong></span><span class="sxs-lookup"><span data-stu-id="4e22b-146"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="4e22b-p110">Указание типа сети, к которой был подключен клиент при выполнении вызова. Выберите одно из значений:</span><span class="sxs-lookup"><span data-stu-id="4e22b-p110">Indicates the type of network the client was connected to when the call was placed. Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="4e22b-149">Ко</span><span class="sxs-lookup"><span data-stu-id="4e22b-149">[All]</span></span></p></li>
<li><p><span data-ttu-id="4e22b-150">Политик</span><span class="sxs-lookup"><span data-stu-id="4e22b-150">Wired</span></span></p></li>
<li><p><span data-ttu-id="4e22b-151">Инфракрас</span><span class="sxs-lookup"><span data-stu-id="4e22b-151">Wireless</span></span></p></li>
</ol></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e22b-152"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="4e22b-152"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="4e22b-p111">Указывает, использовал ли внешний клиент VPN-подключение при выполнении звонка. Выберите одно из значений:</span><span class="sxs-lookup"><span data-stu-id="4e22b-p111">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed. Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="4e22b-155">Ко</span><span class="sxs-lookup"><span data-stu-id="4e22b-155">[All]</span></span></p></li>
<li><p><span data-ttu-id="4e22b-156">VPN</span><span class="sxs-lookup"><span data-stu-id="4e22b-156">VPN</span></span></p></li>
<li><p><span data-ttu-id="4e22b-157">Не VPN</span><span class="sxs-lookup"><span data-stu-id="4e22b-157">Non-VPN</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="4e22b-158">Метрик</span><span class="sxs-lookup"><span data-stu-id="4e22b-158">Metrics</span></span>

<span data-ttu-id="4e22b-159">В следующей таблице перечислены сведения, представленные в отчете о расположении.</span><span class="sxs-lookup"><span data-stu-id="4e22b-159">The following table lists the information provided in the Location Report.</span></span>

### <a name="location-report-metrics"></a><span data-ttu-id="4e22b-160">Метрики отчета о расположении</span><span class="sxs-lookup"><span data-stu-id="4e22b-160">Location Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4e22b-161">Имя</span><span class="sxs-lookup"><span data-stu-id="4e22b-161">Name</span></span></th>
<th><span data-ttu-id="4e22b-162">Возможность сортировки по этому показателю</span><span class="sxs-lookup"><span data-stu-id="4e22b-162">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="4e22b-163">Описание</span><span class="sxs-lookup"><span data-stu-id="4e22b-163">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4e22b-164"><strong>Подсеть вызывающего абонента</strong></span><span class="sxs-lookup"><span data-stu-id="4e22b-164"><strong>Caller subnet</strong></span></span></p></td>
<td><p><span data-ttu-id="4e22b-165">Нет</span><span class="sxs-lookup"><span data-stu-id="4e22b-165">No</span></span></p></td>
<td><p><span data-ttu-id="4e22b-166">IP-подсеть пользователя, который поместил вызов.</span><span class="sxs-lookup"><span data-stu-id="4e22b-166">IP subnet of the user who placed the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e22b-167"><strong>Подсеть вызываемого абонента</strong></span><span class="sxs-lookup"><span data-stu-id="4e22b-167"><strong>Callee subnet</strong></span></span></p></td>
<td><p><span data-ttu-id="4e22b-168">Нет</span><span class="sxs-lookup"><span data-stu-id="4e22b-168">No</span></span></p></td>
<td><p><span data-ttu-id="4e22b-169">IP-подсеть пользователя, который получил вызов.</span><span class="sxs-lookup"><span data-stu-id="4e22b-169">IP subnet of the user who received the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e22b-170"><strong>Громкость вызова</strong></span><span class="sxs-lookup"><span data-stu-id="4e22b-170"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="4e22b-171">Да</span><span class="sxs-lookup"><span data-stu-id="4e22b-171">Yes</span></span></p></td>
<td><p><span data-ttu-id="4e22b-172">Общее количество выполненных вызовов.</span><span class="sxs-lookup"><span data-stu-id="4e22b-172">Total number of calls placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e22b-173"><strong>Процент звонков низкого качества</strong></span><span class="sxs-lookup"><span data-stu-id="4e22b-173"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="4e22b-174">Да</span><span class="sxs-lookup"><span data-stu-id="4e22b-174">Yes</span></span></p></td>
<td><p><span data-ttu-id="4e22b-175">Процент звонков, классифицированных как некачественные звонки.</span><span class="sxs-lookup"><span data-stu-id="4e22b-175">Percentage of calls classified as poor calls.</span></span> <span data-ttu-id="4e22b-176">Звонок низкого качества — это любой звонок, хотя бы одна метрика которого превышает допустимое значение (например, звонок с чрезмерным дрожанием).</span><span class="sxs-lookup"><span data-stu-id="4e22b-176">A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e22b-177"><strong>Время кругового пути (мс)</strong></span><span class="sxs-lookup"><span data-stu-id="4e22b-177"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="4e22b-178">Да</span><span class="sxs-lookup"><span data-stu-id="4e22b-178">Yes</span></span></p></td>
<td><p><span data-ttu-id="4e22b-p113">Среднее время (в миллисекундах), необходимое для перемещения пакета Real-Time Transport Protocol в другую конечную точку и его возврата. Приемлемым считается время двусторонней передачи, равное 200 мс (или менее).</span><span class="sxs-lookup"><span data-stu-id="4e22b-p113">Average amount of (in milliseconds) required for a real-time transport protocol (RTP) packet to travel to another endpoint and then back. Round-trip times of 100 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="4e22b-p114">Высокие значения кругового пути могут быть следствием маршрутизации международных вызовов, неправильной настройки маршрутизации или перегруженности сервера мультимедиа. Высокие значения кругового пути осложняют проведение двусторонних бесед в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="4e22b-p114">High round-trip values can be caused by international call routing, a routing misconfiguration, or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e22b-183"><strong>Деградация (MOS)</strong></span><span class="sxs-lookup"><span data-stu-id="4e22b-183"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="4e22b-184">Да</span><span class="sxs-lookup"><span data-stu-id="4e22b-184">Yes</span></span></p></td>
<td><p><span data-ttu-id="4e22b-185">Средний объем деградации в соответствии со средней экспертной оценкой разборчивости речи (MOS), наблюдаемый в ходе вызова.</span><span class="sxs-lookup"><span data-stu-id="4e22b-185">Average amount of mean opinion score (MOS) degradation experienced during a call.</span></span> <span data-ttu-id="4e22b-186">Значение снижения может быть в диапазоне от 0.0 до 5.0.</span><span class="sxs-lookup"><span data-stu-id="4e22b-186">Degradation values can range from a low of 0.0 to a high of 5.0.</span></span> <span data-ttu-id="4e22b-187">Значение не выше 0.5 является приемлемым уровнем снижения.</span><span class="sxs-lookup"><span data-stu-id="4e22b-187">A value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="4e22b-188">Традиционно средние экспертные оценки разборчивости речи вычислялись по оценкам пользователей качества вызова по шкале от 1 до 5.</span><span class="sxs-lookup"><span data-stu-id="4e22b-188">Historically, mean options scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="4e22b-189">В Lync Server Lync Server использует набор алгоритмов для прогнозирования того, как пользователи будут оценены при вызове.</span><span class="sxs-lookup"><span data-stu-id="4e22b-189">In Lync Server, Lync Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="4e22b-p116">Высокие значения снижения могут быть вызваны перегруженностью, нехваткой пропускной способности, перегруженность или помехами в беспроводной сети, а также перегруженностью сервера мультимедиа или конечной точки. Высокие значения могут привести к искажению или потере звука.</span><span class="sxs-lookup"><span data-stu-id="4e22b-p116">High degradation values can be caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server or endpoint. High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e22b-192"><strong>Потеря пакетов</strong></span><span class="sxs-lookup"><span data-stu-id="4e22b-192"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="4e22b-193">Да</span><span class="sxs-lookup"><span data-stu-id="4e22b-193">Yes</span></span></p></td>
<td><p><span data-ttu-id="4e22b-p117">Средний показатель потери пакетов RTP. (Потеря пакетов происходит, когда пакеты RTP (протокол, используемый для передачи видео- и аудиокомпонентов через Интернет) не достигают места назначения.) Высокие значения потери, как правило, обусловлены перегрузкой, недостаточной пропускной способностью, помехами или перегрузкой беспроводной сети либо перегрузкой сервера-посредника. Потеря пакетов обычно приводит к искажению или потере звук.</span><span class="sxs-lookup"><span data-stu-id="4e22b-p117">Average rate of RTP packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e22b-197"><strong>Колебани</strong></span><span class="sxs-lookup"><span data-stu-id="4e22b-197"><strong>Jitter</strong></span></span></p></td>
<td><p><span data-ttu-id="4e22b-198">Да</span><span class="sxs-lookup"><span data-stu-id="4e22b-198">Yes</span></span></p></td>
<td><p><span data-ttu-id="4e22b-199">Среднее значение колебаний, зарегистрированных между прибытиями пакетов RTP.</span><span class="sxs-lookup"><span data-stu-id="4e22b-199">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="4e22b-200">(Колебание — это мера &quot;вибрирования&quot; вызова.) Большие значения колебаний обычно вызваны перегрузкой или перегрузкой сервера мультимедиа, что приводит к искажению или потере звука.</span><span class="sxs-lookup"><span data-stu-id="4e22b-200">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e22b-201"><strong>Соотношение скрытых фрагментов в процессе восстановления</strong></span><span class="sxs-lookup"><span data-stu-id="4e22b-201"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="4e22b-202">Да</span><span class="sxs-lookup"><span data-stu-id="4e22b-202">Yes</span></span></p></td>
<td><p><span data-ttu-id="4e22b-p119">Среднее отношение количества скрытых аудиофрагментов к общему количеству фрагментов. (Скрытие аудиофрагментов — это метод, используемый для сглаживания резких переходов, которые обычно вызваны пропуском сетевых пакетов.) Высокие значения указывают на высокие уровни скрытия потерь, которые были обусловлены потерей пакетов или колебаниями. Эти высокие значения приводят к искажению звука или потере аудиосигналов.</span><span class="sxs-lookup"><span data-stu-id="4e22b-p119">Average ratio of concealed audio samples to the total to the total number of samples. (A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e22b-205"><strong>Соотношение растянутых фрагментов в процессе восстановления</strong></span><span class="sxs-lookup"><span data-stu-id="4e22b-205"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="4e22b-206">Да</span><span class="sxs-lookup"><span data-stu-id="4e22b-206">Yes</span></span></p></td>
<td><p><span data-ttu-id="4e22b-p120">Среднее отношение количества растянутых аудиофрагментов к общему количеству фрагментов. (Растянутые аудиофрагменты — фрагменты, которые были увеличены для поддержания качества вызова при обнаружении пропуска сетевого пакета.) Высокие значения указывают на значительные уровни растягивания фрагментов, которые были обусловлены колебаниями. Эти высокие значения приводят к искажению звука или к созданию эффекта механического звучания.</span><span class="sxs-lookup"><span data-stu-id="4e22b-p120">Average ratio of stretched audio samples to the total to the total number of samples. (Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e22b-209"><strong>Соотношение сжатых фрагментов в процессе восстановления</strong></span><span class="sxs-lookup"><span data-stu-id="4e22b-209"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="4e22b-210">Да</span><span class="sxs-lookup"><span data-stu-id="4e22b-210">Yes</span></span></p></td>
<td><p><span data-ttu-id="4e22b-p121">Среднее отношение сжатых звуковых сэмплов к общему количеству сэмплов. (Сжатые звуковые сэмплы — это звук, который сжимается для поддержания качества звонка, когда обнаруживается потерянный сетевой пакет.) Высокие значения указывают на значительные уровни сжатия сэмплов, вызванного дрожанием, что может привести к искажению или потере звука.</span><span class="sxs-lookup"><span data-stu-id="4e22b-p121">Average ratio of compressed audio samples to the total number of samples. (Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

