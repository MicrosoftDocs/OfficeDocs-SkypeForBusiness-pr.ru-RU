---
title: 'Lync Server 2013: отчет о соотношении качества мультимедиа'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Media Quality Comparison Report
ms:assetid: c1d0b5a8-98ff-455a-b78b-a05a21cf066d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205236(v=OCS.15)
ms:contentKeyID: 48185317
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a6697e02d7b821ebd3dc3cabc3a95c8d00960a08
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827447"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-quality-comparison-report-in-lync-server-2013"></a><span data-ttu-id="aff81-102">Отчет о сравнении качества мультимедиа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aff81-102">Media Quality Comparison Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aff81-103">_**Тема последнего изменения:** 2014-04-22_</span><span class="sxs-lookup"><span data-stu-id="aff81-103">_**Topic Last Modified:** 2014-04-22_</span></span>

<span data-ttu-id="aff81-104">Сравнительный отчет качества мультимедиа-данных позволяет сравнить значения качества звонков для различных типов аудиозвонков (например, звонков, выполненных через беспроводные сети и звонков, выполненных через проводное соединение).</span><span class="sxs-lookup"><span data-stu-id="aff81-104">The Media Quality Comparison Report enables you to compare call quality values for different types of audio calls (for example, calls made over a wireless network vs. calls made across a wired connection).</span></span>

<div>

## <a name="accessing-the-media-quality-comparison-report"></a><span data-ttu-id="aff81-105">Доступ к сравнительному отчету качества мультимедиа-данных</span><span class="sxs-lookup"><span data-stu-id="aff81-105">Accessing the Media Quality Comparison Report</span></span>

<span data-ttu-id="aff81-106">Сравнительный отчет качества мультимедиа-данных доступен на домашней странице отчетов мониторинга.</span><span class="sxs-lookup"><span data-stu-id="aff81-106">The Media Quality Comparison Report is accessed from the Monitoring Reports home page.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="aff81-107">Фильтры</span><span class="sxs-lookup"><span data-stu-id="aff81-107">Filters</span></span>

<span data-ttu-id="aff81-p101">Фильтры предоставляют способ получения более точно настроенного набора данных или просмотра возвращенных данных различными способами. В следующей таблице перечислены фильтры, которые можно использовать в сравнительном отчете качества мультимедиа-данных.</span><span class="sxs-lookup"><span data-stu-id="aff81-p101">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the Media Quality Comparison Report.</span></span>

### <a name="media-quality-comparison-report-filters"></a><span data-ttu-id="aff81-110">Фильтры сравнительного отчета качества мультимедиа-данных</span><span class="sxs-lookup"><span data-stu-id="aff81-110">Media Quality Comparison Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="aff81-111">Имя</span><span class="sxs-lookup"><span data-stu-id="aff81-111">Name</span></span></th>
<th><span data-ttu-id="aff81-112">Описание</span><span class="sxs-lookup"><span data-stu-id="aff81-112">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="aff81-113"><strong>От</strong></span><span class="sxs-lookup"><span data-stu-id="aff81-113"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="aff81-p102">Начальные дата/время для временного диапазона. Чтобы просмотреть данные по часам, введите начальные дату и время следующим образом:</span><span class="sxs-lookup"><span data-stu-id="aff81-p102">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="aff81-116">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="aff81-116">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="aff81-p103">Если вы не вводите начальное время, отчет автоматически начинается с 12:00 AM указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</span><span class="sxs-lookup"><span data-stu-id="aff81-p103">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="aff81-119">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="aff81-119">7/7/2012</span></span></p>
<p><span data-ttu-id="aff81-120">Чтобы просмотреть данные за неделю или месяц, введите дату, выпадающую на любое время в рамках недели или месяца, которые вы хотите просмотреть (вам не требуется вводить первый день недели или месяца):</span><span class="sxs-lookup"><span data-stu-id="aff81-120">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="aff81-121">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="aff81-121">7/3/2012</span></span></p>
<p><span data-ttu-id="aff81-122">Недели всегда отсчитываются с воскресенья по субботу.</span><span class="sxs-lookup"><span data-stu-id="aff81-122">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aff81-123"><strong>До</strong></span><span class="sxs-lookup"><span data-stu-id="aff81-123"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="aff81-p104">Конечные дата/время для временного диапазона. Чтобы просмотреть данные по часам, введите конечные дату и время следующим образом:</span><span class="sxs-lookup"><span data-stu-id="aff81-p104">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="aff81-126">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="aff81-126">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="aff81-p105">Если вы не вводите конечное время, отчет автоматически заканчивается в 12:00 AM указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</span><span class="sxs-lookup"><span data-stu-id="aff81-p105">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="aff81-129">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="aff81-129">7/7/2012</span></span></p>
<p><span data-ttu-id="aff81-130">Чтобы просмотреть данные за неделю или месяц, введите дату, выпадающую на любое время в рамках недели или месяца, которые вы хотите просмотреть (вам не требуется вводить первый день недели или месяца):</span><span class="sxs-lookup"><span data-stu-id="aff81-130">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="aff81-131">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="aff81-131">7/3/2012</span></span></p>
<p><span data-ttu-id="aff81-132">Недели всегда отсчитываются с воскресенья по субботу.</span><span class="sxs-lookup"><span data-stu-id="aff81-132">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aff81-133"><strong>Звонки</strong></span><span class="sxs-lookup"><span data-stu-id="aff81-133"><strong>Calls</strong></span></span></p></td>
<td><p><span data-ttu-id="aff81-p106">Тип звонка, который будет использоваться в качестве основного элемента для сравнения. Допускаются следующие значения:</span><span class="sxs-lookup"><span data-stu-id="aff81-p106">Type of call to be used as the main comparison item. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="aff81-136">[All] (Все)</span><span class="sxs-lookup"><span data-stu-id="aff81-136">[All]</span></span></p></li>
<li><p><span data-ttu-id="aff81-137">Внешний</span><span class="sxs-lookup"><span data-stu-id="aff81-137">External</span></span></p></li>
<li><p><span data-ttu-id="aff81-138">Internal</span><span class="sxs-lookup"><span data-stu-id="aff81-138">Internal</span></span></p></li>
<li><p><span data-ttu-id="aff81-139">VPN</span><span class="sxs-lookup"><span data-stu-id="aff81-139">VPN</span></span></p></li>
<li><p><span data-ttu-id="aff81-140">Не VPN</span><span class="sxs-lookup"><span data-stu-id="aff81-140">Non-VPN</span></span></p></li>
<li><p><span data-ttu-id="aff81-141">Проводная</span><span class="sxs-lookup"><span data-stu-id="aff81-141">Wired</span></span></p></li>
<li><p><span data-ttu-id="aff81-142">Беспроводная</span><span class="sxs-lookup"><span data-stu-id="aff81-142">Wireless</span></span></p></li>
<li><p><span data-ttu-id="aff81-143">Внешние и проводные</span><span class="sxs-lookup"><span data-stu-id="aff81-143">External and wired</span></span></p></li>
<li><p><span data-ttu-id="aff81-144">Внешние и беспроводные</span><span class="sxs-lookup"><span data-stu-id="aff81-144">External and wireless</span></span></p></li>
<li><p><span data-ttu-id="aff81-145">Внешние и VPN</span><span class="sxs-lookup"><span data-stu-id="aff81-145">External and VPN</span></span></p></li>
<li><p><span data-ttu-id="aff81-146">Внешние и не VPN</span><span class="sxs-lookup"><span data-stu-id="aff81-146">External and non-VPN</span></span></p></li>
<li><p><span data-ttu-id="aff81-147">Внутренние и проводные</span><span class="sxs-lookup"><span data-stu-id="aff81-147">Internal and wired</span></span></p></li>
<li><p><span data-ttu-id="aff81-148">Внутренние и беспроводные</span><span class="sxs-lookup"><span data-stu-id="aff81-148">Internal and wireless</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aff81-149"><strong>Сравнить со звонками</strong></span><span class="sxs-lookup"><span data-stu-id="aff81-149"><strong>Compare with calls</strong></span></span></p></td>
<td><p><span data-ttu-id="aff81-p107">Тип звонка, который будет использоваться в качестве второго элемента для сравнения. Допускаются следующие значения:</span><span class="sxs-lookup"><span data-stu-id="aff81-p107">Type of call to be used as the secondary comparison item. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="aff81-152">[All] (Все)</span><span class="sxs-lookup"><span data-stu-id="aff81-152">[All]</span></span></p></li>
<li><p><span data-ttu-id="aff81-153">Внешний</span><span class="sxs-lookup"><span data-stu-id="aff81-153">External</span></span></p></li>
<li><p><span data-ttu-id="aff81-154">Internal</span><span class="sxs-lookup"><span data-stu-id="aff81-154">Internal</span></span></p></li>
<li><p><span data-ttu-id="aff81-155">VPN</span><span class="sxs-lookup"><span data-stu-id="aff81-155">VPN</span></span></p></li>
<li><p><span data-ttu-id="aff81-156">Не VPN</span><span class="sxs-lookup"><span data-stu-id="aff81-156">Non-VPN</span></span></p></li>
<li><p><span data-ttu-id="aff81-157">Проводная</span><span class="sxs-lookup"><span data-stu-id="aff81-157">Wired</span></span></p></li>
<li><p><span data-ttu-id="aff81-158">Беспроводная</span><span class="sxs-lookup"><span data-stu-id="aff81-158">Wireless</span></span></p></li>
<li><p><span data-ttu-id="aff81-159">Внешние и проводные</span><span class="sxs-lookup"><span data-stu-id="aff81-159">External and wired</span></span></p></li>
<li><p><span data-ttu-id="aff81-160">Внешние и беспроводные</span><span class="sxs-lookup"><span data-stu-id="aff81-160">External and wireless</span></span></p></li>
<li><p><span data-ttu-id="aff81-161">Внешние и VPN</span><span class="sxs-lookup"><span data-stu-id="aff81-161">External and VPN</span></span></p></li>
<li><p><span data-ttu-id="aff81-162">Внешние и не VPN</span><span class="sxs-lookup"><span data-stu-id="aff81-162">External and non-VPN</span></span></p></li>
<li><p><span data-ttu-id="aff81-163">Внутренние и проводные</span><span class="sxs-lookup"><span data-stu-id="aff81-163">Internal and wired</span></span></p></li>
<li><p><span data-ttu-id="aff81-164">Внутренние и беспроводные</span><span class="sxs-lookup"><span data-stu-id="aff81-164">Internal and wireless</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aff81-165"><strong>Интервал</strong></span><span class="sxs-lookup"><span data-stu-id="aff81-165"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="aff81-p108">Временной интервал. Выберите одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="aff81-p108">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="aff81-168">Ежечасно (можно отобразить не более 25 часов)</span><span class="sxs-lookup"><span data-stu-id="aff81-168">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="aff81-169">Ежедневно (можно отобразить не более 31 дня)</span><span class="sxs-lookup"><span data-stu-id="aff81-169">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="aff81-170">Еженедельно (можно отобразить не более 12 недель)</span><span class="sxs-lookup"><span data-stu-id="aff81-170">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="aff81-171">Если число значений между начальной и конечной датами превышает максимальное допустимое для выбранного интервала, отображается максимальное возможное число значений (с начальной даты).</span><span class="sxs-lookup"><span data-stu-id="aff81-171">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed.</span></span> <span data-ttu-id="aff81-172">Например, если выбрать ежедневный интервал с датой начала 7/7/2012 и датой окончания 2/28/2012, данные будут выводиться для дней 8/7/2012 12:00 – 9/7/2012 12:00 AM (то есть, всего за 31 дня).</span><span class="sxs-lookup"><span data-stu-id="aff81-172">For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="aff81-173">Показатели</span><span class="sxs-lookup"><span data-stu-id="aff81-173">Metrics</span></span>

<span data-ttu-id="aff81-174">В следующей таблице приведены сведения, предоставляемые сравнительным отчетом качества мультимедиа-данных</span><span class="sxs-lookup"><span data-stu-id="aff81-174">The following table lists the information provided in the Media Quality Comparison Report.</span></span>

### <a name="media-quality-comparison-report-metrics"></a><span data-ttu-id="aff81-175">Метрики сравнительного отчета качества мультимедиа-данных</span><span class="sxs-lookup"><span data-stu-id="aff81-175">Media Quality Comparison Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="aff81-176">Имя</span><span class="sxs-lookup"><span data-stu-id="aff81-176">Name</span></span></th>
<th><span data-ttu-id="aff81-177">Поддержка сортировки</span><span class="sxs-lookup"><span data-stu-id="aff81-177">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="aff81-178">Описание</span><span class="sxs-lookup"><span data-stu-id="aff81-178">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="aff81-179"><strong>Громкость вызова</strong></span><span class="sxs-lookup"><span data-stu-id="aff81-179"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="aff81-180">Нет</span><span class="sxs-lookup"><span data-stu-id="aff81-180">No</span></span></p></td>
<td><p><span data-ttu-id="aff81-181">Полное число звонков.</span><span class="sxs-lookup"><span data-stu-id="aff81-181">Total number of calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aff81-182"><strong>Падение качества (средняя оценка)</strong></span><span class="sxs-lookup"><span data-stu-id="aff81-182"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="aff81-183">Нет</span><span class="sxs-lookup"><span data-stu-id="aff81-183">No</span></span></p></td>
<td><p><span data-ttu-id="aff81-184">Среднее значение числа MOS (средней экспертной оценки разборчивости речи), показывающей ухудшение качества связи во время звонка.</span><span class="sxs-lookup"><span data-stu-id="aff81-184">Average amount of MOS (mean opinion score) degradation experienced during a call.</span></span> <span data-ttu-id="aff81-185">Значения ухудшения качества могут находиться в диапазоне от 0,0 до 5,0; значение 0,5 или ниже соответствует приемлемому ухудшению.</span><span class="sxs-lookup"><span data-stu-id="aff81-185">Degradation values can range from a low of 0.0 to a high of 5.0; a value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="aff81-186">Исторически средние экспертные оценки разборчивости речи вычислялись при помощи пользователей, которые оценивали качество звонка по шкале от 1 до 5.</span><span class="sxs-lookup"><span data-stu-id="aff81-186">Historically, mean opinion scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="aff81-187">Lync Server использует набор алгоритмов для прогнозирования того, как пользователи будут оценены при звонке.</span><span class="sxs-lookup"><span data-stu-id="aff81-187">Lync Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="aff81-p111">Высокие значения ухудшения могут быть вызваны перегрузкой; недостаточной пропускной способностью; перегрузкой беспроводной сети или интерференцией; перегрузкой сервера мультимедиа или конечной точки. Сильное ухудшение приводит к повреждению или потере аудиосигнала.</span><span class="sxs-lookup"><span data-stu-id="aff81-p111">High degradation values can be caused by congestion; lack of bandwidth; wireless congestion or interference, or an overloaded media server or endpoint. High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aff81-190"><strong>Процент звонков низкого качества</strong></span><span class="sxs-lookup"><span data-stu-id="aff81-190"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="aff81-191">Нет</span><span class="sxs-lookup"><span data-stu-id="aff81-191">No</span></span></p></td>
<td><p><span data-ttu-id="aff81-p112">Полное число звонков, классифицированных как неудовлетворительные. Неудовлетворительный звонок — это любой звонок, в котором хотя бы одна измеренная метрика превысила допустимое значение (например, звонок, подверженный слишком сильному дрожанию).</span><span class="sxs-lookup"><span data-stu-id="aff81-p112">The total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aff81-194"><strong>Круговой путь (мс)</strong></span><span class="sxs-lookup"><span data-stu-id="aff81-194"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="aff81-195">Нет</span><span class="sxs-lookup"><span data-stu-id="aff81-195">No</span></span></p></td>
<td><p><span data-ttu-id="aff81-p113">Среднее время (в миллисекундах), необходимое для перемещения пакета Real-Time Transport Protocol в другую конечную точку и его возврата. Приемлемым считается время двусторонней передачи, равное 200 мс (или менее).</span><span class="sxs-lookup"><span data-stu-id="aff81-p113">Average amount of (in milliseconds) required for a Real-Time Transport Protocol packet to travel to another endpoint and then back. Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="aff81-p114">Высокие значения времени двусторонней передачи могут быть обусловлены международной маршрутизацией вызовов, неправильной конфигурацией маршрутизации или перегрузкой сервера-посредника. Длительное время двусторонней передачи приводит к возникновению проблем при двусторонних аудиоразговорах в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="aff81-p114">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aff81-200"><strong>Потеря пакетов</strong></span><span class="sxs-lookup"><span data-stu-id="aff81-200"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="aff81-201">Нет</span><span class="sxs-lookup"><span data-stu-id="aff81-201">No</span></span></p></td>
<td><p><span data-ttu-id="aff81-p115">Средняя частота потери пакетов RTP. (Потеря пакетов происходит, когда пакеты RTP (Real-Time Transport Protocol — протокол, используемый для передачи аудио- и видеопакетов через Интернет) не достигают места назначения.) Высокие показатели потерь обычно вызваны перегрузкой, недостаточной полосой пропускания, помехами или перегрузкой беспроводной сети, а также перегрузкой сервера-посредника. Потеря пакетов обычно приводит к искажению звука или потере аудиосигналов.</span><span class="sxs-lookup"><span data-stu-id="aff81-p115">Average rate of Real-Time Transport Protocol (RTP) packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aff81-205"><strong>Дрожание (мс)</strong></span><span class="sxs-lookup"><span data-stu-id="aff81-205"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="aff81-206">Нет</span><span class="sxs-lookup"><span data-stu-id="aff81-206">No</span></span></p></td>
<td><p><span data-ttu-id="aff81-207">Среднее значение колебаний, зарегистрированных между прибытиями пакетов RTP.</span><span class="sxs-lookup"><span data-stu-id="aff81-207">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="aff81-208">(Колебание — это мера &quot;шакинесс&quot; звонка). Обычно значения с высокой степенью колебаний заключаются в результате перегруженности или перегруженного сервера мультимедиа, что приводит к искажению или потере звука.</span><span class="sxs-lookup"><span data-stu-id="aff81-208">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aff81-209"><strong>Степень маскированных аудиообразцов</strong></span><span class="sxs-lookup"><span data-stu-id="aff81-209"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="aff81-210">Нет</span><span class="sxs-lookup"><span data-stu-id="aff81-210">No</span></span></p></td>
<td><p><span data-ttu-id="aff81-p117">Средняя степень маскированных аудиообразцов по отношению к общему числу образцов. (Маскирование аудио - это методика, которая применяется для сглаживания оборванной передачи, которая обычно происходит при потери сетевых пакетов). Большие значения обозначают частое применение данной методики, вызванной из-за потери пакетов или искажений сигнала.</span><span class="sxs-lookup"><span data-stu-id="aff81-p117">Average ratio of concealed audio samples to the total to the total number of samples. (A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aff81-213"><strong>Степень растянутых образцов</strong></span><span class="sxs-lookup"><span data-stu-id="aff81-213"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="aff81-214">Нет</span><span class="sxs-lookup"><span data-stu-id="aff81-214">No</span></span></p></td>
<td><p><span data-ttu-id="aff81-p118">Средняя степень растянутых аудиообразцов по отношению к общему числу образцов. (Растягивание аудиопакета - это методика, которая применяется для поддержания качества звонка при обнаружении потери сетевого пакета). Большие значения обозначают частое применение данной методики, вызванное большими искажениями – аудиосигнал звучит как роботизированный.</span><span class="sxs-lookup"><span data-stu-id="aff81-p118">Average ratio of stretched audio samples to the total to the total number of samples. (Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aff81-217"><strong>Степень сжатых аудиообразцов</strong></span><span class="sxs-lookup"><span data-stu-id="aff81-217"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="aff81-218">Нет</span><span class="sxs-lookup"><span data-stu-id="aff81-218">No</span></span></p></td>
<td><p><span data-ttu-id="aff81-p119">Средняя степень растянутых аудиообразцов по отношению к общему числу образцов. (Сжатие аудиопакета - это методика, которая применяется для поддержания качества звонка при обнаружении потери сетевого пакета). Большие значения обозначают частое применение данной методики, вызванное большими искажениями – аудиосигнал звучит как ускоренный или искаженный.</span><span class="sxs-lookup"><span data-stu-id="aff81-p119">Average ratio of compressed audio samples to the total number of samples. (Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

