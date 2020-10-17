---
title: 'Lync Server 2013: сравнительный отчет по качеству мультимедиа'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media Quality Comparison Report
ms:assetid: c1d0b5a8-98ff-455a-b78b-a05a21cf066d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205236(v=OCS.15)
ms:contentKeyID: 48185317
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 05b157be6cc94f0b01dbefadfd89041118b944e1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500666"
---
# <a name="media-quality-comparison-report-in-lync-server-2013"></a><span data-ttu-id="5b6dc-102">Отчет по сравнению качества мультимедиа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5b6dc-102">Media Quality Comparison Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5b6dc-103">_**Последнее изменение темы:** 2014-04-22_</span><span class="sxs-lookup"><span data-stu-id="5b6dc-103">_**Topic Last Modified:** 2014-04-22_</span></span>

<span data-ttu-id="5b6dc-104">Сравнительный отчет качества мультимедиа-данных позволяет сравнить значения качества звонков для различных типов аудиозвонков (например, звонков, выполненных через беспроводные сети и звонков, выполненных через проводное соединение).</span><span class="sxs-lookup"><span data-stu-id="5b6dc-104">The Media Quality Comparison Report enables you to compare call quality values for different types of audio calls (for example, calls made over a wireless network vs. calls made across a wired connection).</span></span>

<div>

## <a name="accessing-the-media-quality-comparison-report"></a><span data-ttu-id="5b6dc-105">Доступ к сравнительному отчету качества мультимедиа-данных</span><span class="sxs-lookup"><span data-stu-id="5b6dc-105">Accessing the Media Quality Comparison Report</span></span>

<span data-ttu-id="5b6dc-106">Сравнительный отчет качества мультимедиа-данных доступен на домашней странице отчетов мониторинга.</span><span class="sxs-lookup"><span data-stu-id="5b6dc-106">The Media Quality Comparison Report is accessed from the Monitoring Reports home page.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="5b6dc-107">Фильтры</span><span class="sxs-lookup"><span data-stu-id="5b6dc-107">Filters</span></span>

<span data-ttu-id="5b6dc-p101">Фильтры предоставляют способ получения более точно настроенного набора данных или просмотра возвращенных данных различными способами. В следующей таблице перечислены фильтры, которые можно использовать в сравнительном отчете качества мультимедиа-данных.</span><span class="sxs-lookup"><span data-stu-id="5b6dc-p101">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the Media Quality Comparison Report.</span></span>

### <a name="media-quality-comparison-report-filters"></a><span data-ttu-id="5b6dc-110">Фильтры сравнительного отчета качества мультимедиа-данных</span><span class="sxs-lookup"><span data-stu-id="5b6dc-110">Media Quality Comparison Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5b6dc-111">Имя</span><span class="sxs-lookup"><span data-stu-id="5b6dc-111">Name</span></span></th>
<th><span data-ttu-id="5b6dc-112">Описание</span><span class="sxs-lookup"><span data-stu-id="5b6dc-112">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5b6dc-113"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="5b6dc-113"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="5b6dc-p102">Дата и время начала диапазона. Чтобы просмотреть данные по часам, введите дату и время начала в следующем формате:</span><span class="sxs-lookup"><span data-stu-id="5b6dc-p102">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="5b6dc-116">7/7/2012 13:00.</span><span class="sxs-lookup"><span data-stu-id="5b6dc-116">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="5b6dc-p103">Если не указать время начала, автоматически будет выбрано время 00:00 указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</span><span class="sxs-lookup"><span data-stu-id="5b6dc-p103">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="5b6dc-119">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="5b6dc-119">7/7/2012</span></span></p>
<p><span data-ttu-id="5b6dc-120">Для просмотра по неделям или по месяцам введите дату, выпадающую на любой день недели или месяца, который вы хотите просмотреть (это необязательно должен быть первый день недели или месяца):</span><span class="sxs-lookup"><span data-stu-id="5b6dc-120">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="5b6dc-121">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="5b6dc-121">7/3/2012</span></span></p>
<p><span data-ttu-id="5b6dc-122">Неделя всегда начинается с воскресения и заканчивается субботой.</span><span class="sxs-lookup"><span data-stu-id="5b6dc-122">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b6dc-123"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="5b6dc-123"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="5b6dc-p104">Дата и время окончания диапазона. Чтобы просмотреть данные по часам, введите дату и время окончания в следующем формате:</span><span class="sxs-lookup"><span data-stu-id="5b6dc-p104">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="5b6dc-126">7/7/2012 13:00.</span><span class="sxs-lookup"><span data-stu-id="5b6dc-126">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="5b6dc-p105">Если не указать время окончания, автоматически будет выбрано время 00:00 указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</span><span class="sxs-lookup"><span data-stu-id="5b6dc-p105">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="5b6dc-129">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="5b6dc-129">7/7/2012</span></span></p>
<p><span data-ttu-id="5b6dc-130">Для просмотра по неделям или по месяцам введите дату, выпадающую на любой день недели или месяца, который вы хотите просмотреть (это необязательно должен быть первый день недели или месяца):</span><span class="sxs-lookup"><span data-stu-id="5b6dc-130">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="5b6dc-131">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="5b6dc-131">7/3/2012</span></span></p>
<p><span data-ttu-id="5b6dc-132">Недели всегда начинаются с Воскресенья и заканчиваются в Субботу.</span><span class="sxs-lookup"><span data-stu-id="5b6dc-132">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5b6dc-133"><strong>Звонки</strong></span><span class="sxs-lookup"><span data-stu-id="5b6dc-133"><strong>Calls</strong></span></span></p></td>
<td><p><span data-ttu-id="5b6dc-p106">Тип звонка, который будет использоваться в качестве основного элемента для сравнения. Допускаются следующие значения:</span><span class="sxs-lookup"><span data-stu-id="5b6dc-p106">Type of call to be used as the main comparison item. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="5b6dc-136">Ко</span><span class="sxs-lookup"><span data-stu-id="5b6dc-136">[All]</span></span></p></li>
<li><p><span data-ttu-id="5b6dc-137">Внешний</span><span class="sxs-lookup"><span data-stu-id="5b6dc-137">External</span></span></p></li>
<li><p><span data-ttu-id="5b6dc-138">Внутренний</span><span class="sxs-lookup"><span data-stu-id="5b6dc-138">Internal</span></span></p></li>
<li><p><span data-ttu-id="5b6dc-139">VPN</span><span class="sxs-lookup"><span data-stu-id="5b6dc-139">VPN</span></span></p></li>
<li><p><span data-ttu-id="5b6dc-140">Не VPN</span><span class="sxs-lookup"><span data-stu-id="5b6dc-140">Non-VPN</span></span></p></li>
<li><p><span data-ttu-id="5b6dc-141">Политик</span><span class="sxs-lookup"><span data-stu-id="5b6dc-141">Wired</span></span></p></li>
<li><p><span data-ttu-id="5b6dc-142">Инфракрас</span><span class="sxs-lookup"><span data-stu-id="5b6dc-142">Wireless</span></span></p></li>
<li><p><span data-ttu-id="5b6dc-143">Внешние и проводные</span><span class="sxs-lookup"><span data-stu-id="5b6dc-143">External and wired</span></span></p></li>
<li><p><span data-ttu-id="5b6dc-144">Внешние и беспроводные</span><span class="sxs-lookup"><span data-stu-id="5b6dc-144">External and wireless</span></span></p></li>
<li><p><span data-ttu-id="5b6dc-145">Внешние и VPN</span><span class="sxs-lookup"><span data-stu-id="5b6dc-145">External and VPN</span></span></p></li>
<li><p><span data-ttu-id="5b6dc-146">Внешние и не VPN</span><span class="sxs-lookup"><span data-stu-id="5b6dc-146">External and non-VPN</span></span></p></li>
<li><p><span data-ttu-id="5b6dc-147">Внутренние и проводные</span><span class="sxs-lookup"><span data-stu-id="5b6dc-147">Internal and wired</span></span></p></li>
<li><p><span data-ttu-id="5b6dc-148">Внутренние и беспроводные</span><span class="sxs-lookup"><span data-stu-id="5b6dc-148">Internal and wireless</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b6dc-149"><strong>Сравнить со звонками</strong></span><span class="sxs-lookup"><span data-stu-id="5b6dc-149"><strong>Compare with calls</strong></span></span></p></td>
<td><p><span data-ttu-id="5b6dc-p107">Тип звонка, который будет использоваться в качестве второго элемента для сравнения. Допускаются следующие значения:</span><span class="sxs-lookup"><span data-stu-id="5b6dc-p107">Type of call to be used as the secondary comparison item. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="5b6dc-152">Ко</span><span class="sxs-lookup"><span data-stu-id="5b6dc-152">[All]</span></span></p></li>
<li><p><span data-ttu-id="5b6dc-153">Внешний</span><span class="sxs-lookup"><span data-stu-id="5b6dc-153">External</span></span></p></li>
<li><p><span data-ttu-id="5b6dc-154">Внутренний</span><span class="sxs-lookup"><span data-stu-id="5b6dc-154">Internal</span></span></p></li>
<li><p><span data-ttu-id="5b6dc-155">VPN</span><span class="sxs-lookup"><span data-stu-id="5b6dc-155">VPN</span></span></p></li>
<li><p><span data-ttu-id="5b6dc-156">Не VPN</span><span class="sxs-lookup"><span data-stu-id="5b6dc-156">Non-VPN</span></span></p></li>
<li><p><span data-ttu-id="5b6dc-157">Политик</span><span class="sxs-lookup"><span data-stu-id="5b6dc-157">Wired</span></span></p></li>
<li><p><span data-ttu-id="5b6dc-158">Инфракрас</span><span class="sxs-lookup"><span data-stu-id="5b6dc-158">Wireless</span></span></p></li>
<li><p><span data-ttu-id="5b6dc-159">Внешние и проводные</span><span class="sxs-lookup"><span data-stu-id="5b6dc-159">External and wired</span></span></p></li>
<li><p><span data-ttu-id="5b6dc-160">Внешние и беспроводные</span><span class="sxs-lookup"><span data-stu-id="5b6dc-160">External and wireless</span></span></p></li>
<li><p><span data-ttu-id="5b6dc-161">Внешние и VPN</span><span class="sxs-lookup"><span data-stu-id="5b6dc-161">External and VPN</span></span></p></li>
<li><p><span data-ttu-id="5b6dc-162">Внешние и не VPN</span><span class="sxs-lookup"><span data-stu-id="5b6dc-162">External and non-VPN</span></span></p></li>
<li><p><span data-ttu-id="5b6dc-163">Внутренние и проводные</span><span class="sxs-lookup"><span data-stu-id="5b6dc-163">Internal and wired</span></span></p></li>
<li><p><span data-ttu-id="5b6dc-164">Внутренние и беспроводные</span><span class="sxs-lookup"><span data-stu-id="5b6dc-164">Internal and wireless</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5b6dc-165"><strong>Interval</strong></span><span class="sxs-lookup"><span data-stu-id="5b6dc-165"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="5b6dc-p108">Временной интервал. Выберите один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="5b6dc-p108">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="5b6dc-168">Ежечасно (может отображаться до 25 часов)</span><span class="sxs-lookup"><span data-stu-id="5b6dc-168">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="5b6dc-169">Ежедневно (может отображаться до 31 дня)</span><span class="sxs-lookup"><span data-stu-id="5b6dc-169">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="5b6dc-170">Еженедельно (может отображаться максимум 12 недель)</span><span class="sxs-lookup"><span data-stu-id="5b6dc-170">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="5b6dc-p109">Если даты начала и окончания превышают максимальное допустимое число для выбранного интервала, будет отображено только максимальное число значений (начиная с даты начала). Например, если выбрать интервал "Ежедневно" с датой начала 07.07.2012 и датой окончания 28.08.2012, дата отображается для дней с 07.08.2012 00:00 по 07.09.2012 00:00 (то есть в сумме будут отображены данные для 31 дня).</span><span class="sxs-lookup"><span data-stu-id="5b6dc-p109">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="5b6dc-173">Метрики</span><span class="sxs-lookup"><span data-stu-id="5b6dc-173">Metrics</span></span>

<span data-ttu-id="5b6dc-174">В следующей таблице приведены сведения, предоставляемые сравнительным отчетом качества мультимедиа-данных</span><span class="sxs-lookup"><span data-stu-id="5b6dc-174">The following table lists the information provided in the Media Quality Comparison Report.</span></span>

### <a name="media-quality-comparison-report-metrics"></a><span data-ttu-id="5b6dc-175">Метрики сравнительного отчета качества мультимедиа-данных</span><span class="sxs-lookup"><span data-stu-id="5b6dc-175">Media Quality Comparison Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5b6dc-176">Имя</span><span class="sxs-lookup"><span data-stu-id="5b6dc-176">Name</span></span></th>
<th><span data-ttu-id="5b6dc-177">Возможность сортировки по этому показателю</span><span class="sxs-lookup"><span data-stu-id="5b6dc-177">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="5b6dc-178">Описание</span><span class="sxs-lookup"><span data-stu-id="5b6dc-178">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5b6dc-179"><strong>Call volume (Интенсивность вызовов)</strong></span><span class="sxs-lookup"><span data-stu-id="5b6dc-179"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="5b6dc-180">Нет</span><span class="sxs-lookup"><span data-stu-id="5b6dc-180">No</span></span></p></td>
<td><p><span data-ttu-id="5b6dc-181">Общее количество вызовов.</span><span class="sxs-lookup"><span data-stu-id="5b6dc-181">Total number of calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b6dc-182"><strong>Degradation (MOS) (Снижение (MOS))</strong></span><span class="sxs-lookup"><span data-stu-id="5b6dc-182"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="5b6dc-183">Нет</span><span class="sxs-lookup"><span data-stu-id="5b6dc-183">No</span></span></p></td>
<td><p><span data-ttu-id="5b6dc-184">Среднее количество MOS (обозначающих оценку мнения), которое возникло во время вызова.</span><span class="sxs-lookup"><span data-stu-id="5b6dc-184">Average amount of MOS (mean opinion score) degradation experienced during a call.</span></span> <span data-ttu-id="5b6dc-185">Значение снижения может быть в диапазоне от 0.0 до 5.0; значение не выше 0.5 является приемлемым уровнем снижения.</span><span class="sxs-lookup"><span data-stu-id="5b6dc-185">Degradation values can range from a low of 0.0 to a high of 5.0; a value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="5b6dc-186">Исторически обозначаются оценки мнения, чтобы пользователи рассчитывали качество вызова по шкале от 1 до 5.</span><span class="sxs-lookup"><span data-stu-id="5b6dc-186">Historically, mean opinion scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="5b6dc-187">Lync Server использует набор алгоритмов для прогнозирования того, как пользователи будут оценены при вызове.</span><span class="sxs-lookup"><span data-stu-id="5b6dc-187">Lync Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="5b6dc-p111">Высокие значения снижения могут быть вызваны перегруженностью, нехваткой пропускной способности, перегруженностью или помехами в беспроводной сети, а также перегруженностью сервера мультимедиа или конечной точки. Высокие значения могут привести к искажению или потере звука.</span><span class="sxs-lookup"><span data-stu-id="5b6dc-p111">High degradation values can be caused by congestion; lack of bandwidth; wireless congestion or interference, or an overloaded media server or endpoint. High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5b6dc-190"><strong>Poor call percentage (Процент звонков низкого качества)</strong></span><span class="sxs-lookup"><span data-stu-id="5b6dc-190"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="5b6dc-191">Нет</span><span class="sxs-lookup"><span data-stu-id="5b6dc-191">No</span></span></p></td>
<td><p><span data-ttu-id="5b6dc-p112">Общее количество звонков, классифицированных как звонки низкого качества. Звонок низкого качества — это любой звонок, хотя бы одна метрика которого превышает допустимое значение (например, звонок с чрезмерным дрожанием).</span><span class="sxs-lookup"><span data-stu-id="5b6dc-p112">The total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b6dc-194"><strong>Round trip (ms) (Круговой путь (мс))</strong></span><span class="sxs-lookup"><span data-stu-id="5b6dc-194"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="5b6dc-195">Нет</span><span class="sxs-lookup"><span data-stu-id="5b6dc-195">No</span></span></p></td>
<td><p><span data-ttu-id="5b6dc-p113">Среднее время (в миллисекундах), требуемое для переноса пакета протокола RTP на другую конечную точку и затем обратно. Время кругового пути в 200 миллисекунд или меньше считается приемлемым качеством.</span><span class="sxs-lookup"><span data-stu-id="5b6dc-p113">Average amount of (in milliseconds) required for a Real-Time Transport Protocol packet to travel to another endpoint and then back. Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="5b6dc-p114">Высокие значения времени кругового пути могут быть вызваны международной маршрутизацией звонков; неправильной настройкой кругового пути; или перегрузкой сервера мультимедиа. Высокие значения времени кругового пути приводят к сложностям в двухсторонних аудиобеседах в реальном времени.</span><span class="sxs-lookup"><span data-stu-id="5b6dc-p114">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5b6dc-200"><strong>Packet loss (Потеря пакетов)</strong></span><span class="sxs-lookup"><span data-stu-id="5b6dc-200"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="5b6dc-201">Нет</span><span class="sxs-lookup"><span data-stu-id="5b6dc-201">No</span></span></p></td>
<td><p><span data-ttu-id="5b6dc-p115">Средняя норма потери пакетов транспортного протокола в режиме реального времени (пакетов протокола RTP). (Потеря пакетов происходит, когда пакеты протокола RTP, который используется для передачи звука и видео в Интернете, не достигают места своего назначения.) Высокие уровни потерь обычно бывают следствием перегруженности, нехватки пропускной способности, перегруженности или помех в беспроводной сети, а также перегруженности сервера мультимедиа. Потеря пакетов обычно приводит к искажению или потере звука..</span><span class="sxs-lookup"><span data-stu-id="5b6dc-p115">Average rate of Real-Time Transport Protocol (RTP) packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b6dc-205"><strong>Дрожание (мс)</strong></span><span class="sxs-lookup"><span data-stu-id="5b6dc-205"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="5b6dc-206">Нет</span><span class="sxs-lookup"><span data-stu-id="5b6dc-206">No</span></span></p></td>
<td><p><span data-ttu-id="5b6dc-207">Средний уровень дрожания, определенный между прибытием пакетов протокола RTP.</span><span class="sxs-lookup"><span data-stu-id="5b6dc-207">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="5b6dc-208">(Колебание — это мера &quot; вибрирования &quot; вызова.) Большие значения колебаний обычно вызваны перегрузкой или перегрузкой сервера мультимедиа, что приводит к искажению или потере звука.</span><span class="sxs-lookup"><span data-stu-id="5b6dc-208">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5b6dc-209"><strong>Healer concealed ratio (Коэффициент скрытых сэмплов)</strong></span><span class="sxs-lookup"><span data-stu-id="5b6dc-209"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="5b6dc-210">Нет</span><span class="sxs-lookup"><span data-stu-id="5b6dc-210">No</span></span></p></td>
<td><p><span data-ttu-id="5b6dc-p117">Среднее отношение скрытых звуковых сэмплов к общему количеству сэмплов. (Скрытые звуковые сэмплы — это техника, которая используется для сглаживания резких переходов, которые обычно вызываются потерей сетевых пакетов.) Высокие значения указывают на значительные уровни применения скрытия потерь, вызванных потерей пакетов или дрожанием, что может привести к искажению или потере звука.</span><span class="sxs-lookup"><span data-stu-id="5b6dc-p117">Average ratio of concealed audio samples to the total to the total number of samples. (A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b6dc-213"><strong>Healer stretched ratio (Коэффициент растянутых сэмплов)</strong></span><span class="sxs-lookup"><span data-stu-id="5b6dc-213"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="5b6dc-214">Нет</span><span class="sxs-lookup"><span data-stu-id="5b6dc-214">No</span></span></p></td>
<td><p><span data-ttu-id="5b6dc-p118">Среднее отношение растянутых звуковых сэмплов к общему количеству сэмплов. (Растянутые звуковые сэмплы — это звук, который растягивается для поддержания качества звонка, когда обнаруживается потерянный сетевой пакет.) Высокие значения указывают на значительные уровни растягивания сэмплов, вызванного дрожанием, что может привести к искажению или потере звука.</span><span class="sxs-lookup"><span data-stu-id="5b6dc-p118">Average ratio of stretched audio samples to the total to the total number of samples. (Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5b6dc-217"><strong>Healer compressed ratio (Коэффициент сжатых сэмплов)</strong></span><span class="sxs-lookup"><span data-stu-id="5b6dc-217"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="5b6dc-218">Нет</span><span class="sxs-lookup"><span data-stu-id="5b6dc-218">No</span></span></p></td>
<td><p><span data-ttu-id="5b6dc-p119">Среднее отношение сжатых звуковых сэмплов к общему количеству сэмплов. (Сжатые звуковые сэмплы — это звук, который сжимается для поддержания качества звонка, когда обнаруживается потерянный сетевой пакет.) Высокие значения указывают на значительные уровни сжатия сэмплов, вызванного дрожанием, что может привести к искажению или потере звука.</span><span class="sxs-lookup"><span data-stu-id="5b6dc-p119">Average ratio of compressed audio samples to the total number of samples. (Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

