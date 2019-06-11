---
title: 'Lync Server 2013: диагностический отчет о действиях одноранговых компьютеров'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Peer-to-Peer Activity Diagnostic Report
ms:assetid: 025e8ab4-2e64-4a6b-8f52-caf756a5cac3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558602(v=OCS.15)
ms:contentKeyID: 48183242
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f435a4b0ff0ec42e8898260c3ada528963bbebb1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825410"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="peer-to-peer-activity-diagnostic-report-in-lync-server-2013"></a><span data-ttu-id="c995a-102">Диагностический отчет о действиях одноранговой сети в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c995a-102">Peer-to-Peer Activity Diagnostic Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c995a-103">_**Тема последнего изменения:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="c995a-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="c995a-104">Диагностический отчет об одноранговом обмене данными предоставляет сведения об успешных и неудавшихся сеансах однорангового обмена данными.</span><span class="sxs-lookup"><span data-stu-id="c995a-104">The Peer-to-Peer Activity Diagnostic Report provides information about the success and failure of your peer-to-peer communication sessions.</span></span> <span data-ttu-id="c995a-105">Обратите внимание, что в Microsoft Lync Server 2013 различаются различные типы сбоев.</span><span class="sxs-lookup"><span data-stu-id="c995a-105">Note that Microsoft Lync Server 2013 distinguishes between different kinds of failure:</span></span>

  - <span data-ttu-id="c995a-106">**Ожидаемый отказ**.</span><span class="sxs-lookup"><span data-stu-id="c995a-106">**Expected failure**.</span></span> <span data-ttu-id="c995a-107">Под ожидаемым отказом обычно понимается отказ в сугубо техническом смысле.</span><span class="sxs-lookup"><span data-stu-id="c995a-107">An expected failure is typically a failure only in the most technical sense.</span></span> <span data-ttu-id="c995a-108">Например, предположим, что вы звоните кому-то, но этого человека нет на месте, и он не может ответить на звонок.</span><span class="sxs-lookup"><span data-stu-id="c995a-108">For example, suppose you call someone, but he or she is away from the office and is unable to answer the phone.</span></span> <span data-ttu-id="c995a-109">Поскольку на звонок не был получен ответ, такая ситуация технически считается отказом.</span><span class="sxs-lookup"><span data-stu-id="c995a-109">Because the call was not answered, the call is technically considered a failure.</span></span> <span data-ttu-id="c995a-110">С другой стороны, это был ожидаемый сбой: Microsoft Lync Server 2013 не предполагает, что вы можете ответить на него, если вы не можете ответить на телефон.</span><span class="sxs-lookup"><span data-stu-id="c995a-110">On the other hand, this was an expected failure: Microsoft Lync Server 2013 does not expect you to answer the phone if you're not available to answer the phone.</span></span> <span data-ttu-id="c995a-111">Аналогичным образом, ожидаемый отказ произойдет в том случае, если вы попытаетесь отправить мгновенное сообщение пользователю, которого нет в сети или который работает с телефона, не поддерживающего обмен мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="c995a-111">Likewise, an expected failure will occur if you attempt to send an instant message to a user who is offline, or is logged on only to a phone that does not support instant messaging.</span></span>

  - <span data-ttu-id="c995a-112">**Произошла непредвиденная ошибка**.</span><span class="sxs-lookup"><span data-stu-id="c995a-112">**Unexpected failure**.</span></span> <span data-ttu-id="c995a-113">Неизвестная ошибка — именно то, что подразумевается в этом имени: ошибка, которая в зависимости от обстоятельств не ожидается.</span><span class="sxs-lookup"><span data-stu-id="c995a-113">An unexpected error is exactly what the name implies: an error that, based on the circumstances, you would not expect to occur.</span></span> <span data-ttu-id="c995a-114">Например, предположим, что вы звоните человеку, и этот человек доступен для ответа на звонок; Тем не менее, если Lync Server 2013 пытается направить Звонок на голосовую почту, вызов завершится сбоем, поскольку связь с единой системой обмена сообщениями Exchange была прервана.</span><span class="sxs-lookup"><span data-stu-id="c995a-114">For example, suppose you call someone and that person is available to answer the call; however, when Lync Server 2013 tries to route your call to voicemail the call fails because connectivity to Exchange Unified Messaging has been lost.</span></span> <span data-ttu-id="c995a-115">Произошла непредвиденная ошибка: вы ожидаете, что звонки всегда будут перенаправляться в голосовую почту.</span><span class="sxs-lookup"><span data-stu-id="c995a-115">That's an unexpected error: you would expect that calls could always be routed to voicemail.</span></span> <span data-ttu-id="c995a-116">Как правило, непредвиденные сбои — это ошибки, которые, возможно, не могут быть решить с помощью обучения пользователей или аналогичных мер.</span><span class="sxs-lookup"><span data-stu-id="c995a-116">As a general rule, unexpected failures are true failures: they are problems that likely cannot be remedied through user education or similar measures.</span></span>

<span data-ttu-id="c995a-p104">Обратите внимание на то, что число успешных сеансов, ожидаемых отказов и неожиданных отказов может быть не равно в сумме общему числу сеансов. Например, имеются следующие значения.</span><span class="sxs-lookup"><span data-stu-id="c995a-p104">Note that the Success, Expected failure, and Unexpected failure metrics might not add up to the Total sessions metric. For example, in the preceding illustration, we have the following values:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c995a-119">Число успешных выполнений</span><span class="sxs-lookup"><span data-stu-id="c995a-119">Successes</span></span></th>
<th><span data-ttu-id="c995a-120">Число ожидаемых сбоев</span><span class="sxs-lookup"><span data-stu-id="c995a-120">Expected failures</span></span></th>
<th><span data-ttu-id="c995a-121">Число неожиданных сбоев</span><span class="sxs-lookup"><span data-stu-id="c995a-121">Unexpected failures</span></span></th>
<th><span data-ttu-id="c995a-122">Всего сеансов</span><span class="sxs-lookup"><span data-stu-id="c995a-122">Total sessions</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c995a-123">2024</span><span class="sxs-lookup"><span data-stu-id="c995a-123">2024</span></span></p></td>
<td><p><span data-ttu-id="c995a-124">469</span><span class="sxs-lookup"><span data-stu-id="c995a-124">469</span></span></p></td>
<td><p><span data-ttu-id="c995a-125">шестнадцат</span><span class="sxs-lookup"><span data-stu-id="c995a-125">16</span></span></p></td>
<td><p><span data-ttu-id="c995a-126">2521</span><span class="sxs-lookup"><span data-stu-id="c995a-126">2521</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c995a-127">Если сложить 2024 + 469 + 16, то получится 2509 сеансов, но в столбце "Всего сеансов" показано 2521 сеансов.</span><span class="sxs-lookup"><span data-stu-id="c995a-127">If you add 2024 + 469 + 16 you get a total of 2,509 sessions, yet the Total sessions column shows a total of 2,521 sessions.</span></span> <span data-ttu-id="c995a-128">"Недостающие" 12 сеансов – это сеансы, которые система не смогла определить как успешные или неудавшиеся.</span><span class="sxs-lookup"><span data-stu-id="c995a-128">The "missing" 12 sessions are sessions that the system was unable to categorize as successful or unsuccessful.</span></span> <span data-ttu-id="c995a-129">Это может случиться, если в продукте стороннего поставщика появился новый диагностический код, незнакомый с Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c995a-129">That will sometimes be the case when a third-party product introduces a new diagnostic code that is unfamiliar to Lync Server.</span></span> <span data-ttu-id="c995a-130">В этом случае звонки, совершенные с помощью этого продукта и зарегистрированные с помощью его кода диагностики, не всегда могут быть отнесены к успешным, ожидаемым отказам или неожиданным отказам.</span><span class="sxs-lookup"><span data-stu-id="c995a-130">When that happens, calls made using that product, and reporting that diagnostic code, cannot always be categorized as being a Success, an Expected failure, or an Unexpected failure.</span></span>

<div>

## <a name="accessing-the-peer-to-peer-activity-diagnostic-report"></a><span data-ttu-id="c995a-131">Доступ к диагностическому отчету об одноранговом обмене данными</span><span class="sxs-lookup"><span data-stu-id="c995a-131">Accessing the Peer-to-Peer Activity Diagnostic Report</span></span>

<span data-ttu-id="c995a-132">Доступ к диагностическому отчету об одноранговом обмене данными можно получить с домашней страницы "Отчеты наблюдения".</span><span class="sxs-lookup"><span data-stu-id="c995a-132">The Peer-to-Peer Diagnostic Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="c995a-133">Вы можете получить доступ к [отчету о распределении отказов в Lync Server 2013](lync-server-2013-failure-distribution-report.md) , выбрав один из указанных ниже метрик.</span><span class="sxs-lookup"><span data-stu-id="c995a-133">You can access the [Failure Distribution Report in Lync Server 2013](lync-server-2013-failure-distribution-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="c995a-134">Unexpected failure volume (Объем неожиданных сбоев)</span><span class="sxs-lookup"><span data-stu-id="c995a-134">Unexpected failure volume</span></span>

  - <span data-ttu-id="c995a-135">Expected failure volume (Ожидаемый сбой, объем)</span><span class="sxs-lookup"><span data-stu-id="c995a-135">Expected failure volume</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-activity-diagnostic-report"></a><span data-ttu-id="c995a-136">Рекомендации по использованию диагностического отчета об одноранговом обмене данными</span><span class="sxs-lookup"><span data-stu-id="c995a-136">Making the Best Use of the Peer-to-Peer Activity Diagnostic Report</span></span>

<span data-ttu-id="c995a-p107">Имеется ряд способов фильтрации диагностического отчета об одноранговом обмене данными, но по умолчанию соответствующие параметры скрыты. Чтобы просмотреть доступные параметры фильтрации, нажмите кнопку "Показать или скрыть параметры" в правом верхнем углу окна отчета. Параметры фильтрации станут доступны для использования.</span><span class="sxs-lookup"><span data-stu-id="c995a-p107">There are a number of ways you can filter the Peer-to-Peer Activity Diagnostic Report but, by default, those filtering options are hidden from view. To view the filtering options available to you, click the Show/Hide Parameters button in the upper right-hand corner of the report window. Once you do that the filtering options will be available for use.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="c995a-140">Фильтры</span><span class="sxs-lookup"><span data-stu-id="c995a-140">Filters</span></span>

<span data-ttu-id="c995a-p108">Фильтры позволяют получить более конкретные наборы возвращаемых данных. Например, диагностический отчет об одноранговом обмене данными позволяет фильтровать данные по таким признакам, как модальность сеанса (например, обмен мгновенными сообщениями, передача файлов или общий доступ к приложениям). Вы также можете выбрать тип группировки данных. В этом случае звонки группируются по часам, дням или неделям.</span><span class="sxs-lookup"><span data-stu-id="c995a-p108">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Peer-to-Peer Activity Diagnostic Report enables you to filter on such things as the session modality (for example, instant messaging, file transfer, or application sharing). You can also choose how data should be grouped. In this case, calls are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="c995a-145">В следующем списке перечислены фильтры, которые можно использовать с диагностическим отчетом об одноранговом обмене данными.</span><span class="sxs-lookup"><span data-stu-id="c995a-145">The following table lists the filters that you can use with the Peer-to-Peer Activity Diagnostic Report.</span></span>

### <a name="peer-to-peer-activity-diagnostic-report-filters"></a><span data-ttu-id="c995a-146">Фильтры диагностического отчета об одноранговом обмене данными</span><span class="sxs-lookup"><span data-stu-id="c995a-146">Peer-to-Peer Activity Diagnostic Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c995a-147">Имя</span><span class="sxs-lookup"><span data-stu-id="c995a-147">Name</span></span></th>
<th><span data-ttu-id="c995a-148">Описание</span><span class="sxs-lookup"><span data-stu-id="c995a-148">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c995a-149"><strong>От</strong></span><span class="sxs-lookup"><span data-stu-id="c995a-149"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="c995a-p109">Начальные дата/время для временного диапазона. Чтобы просмотреть данные по часам, введите начальные дату и время следующим образом:</span><span class="sxs-lookup"><span data-stu-id="c995a-p109">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="c995a-152">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="c995a-152">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="c995a-p110">Если вы не вводите начальное время, отчет автоматически начинается с 12:00 AM указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</span><span class="sxs-lookup"><span data-stu-id="c995a-p110">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="c995a-155">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="c995a-155">7/7/2012</span></span></p>
<p><span data-ttu-id="c995a-156">Чтобы просмотреть данные за неделю или месяц, введите дату, выпадающую на любое время в рамках недели или месяца, которые вы хотите просмотреть (вам не требуется вводить первый день недели или месяца):</span><span class="sxs-lookup"><span data-stu-id="c995a-156">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="c995a-157">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="c995a-157">7/3/2012</span></span></p>
<p><span data-ttu-id="c995a-158">Недели всегда отсчитываются с воскресенья по субботу.</span><span class="sxs-lookup"><span data-stu-id="c995a-158">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c995a-159"><strong>До</strong></span><span class="sxs-lookup"><span data-stu-id="c995a-159"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="c995a-p111">Конечные дата/время для временного диапазона. Чтобы просмотреть данные по часам, введите конечные дату и время следующим образом:</span><span class="sxs-lookup"><span data-stu-id="c995a-p111">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="c995a-162">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="c995a-162">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="c995a-p112">Если вы не вводите конечное время, отчет автоматически заканчивается в 12:00 AM указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</span><span class="sxs-lookup"><span data-stu-id="c995a-p112">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="c995a-165">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="c995a-165">7/7/2012</span></span></p>
<p><span data-ttu-id="c995a-166">Чтобы просмотреть данные за неделю или месяц, введите дату, выпадающую на любое время в рамках недели или месяца, которые вы хотите просмотреть (вам не требуется вводить первый день недели или месяца):</span><span class="sxs-lookup"><span data-stu-id="c995a-166">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="c995a-167">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="c995a-167">7/3/2012</span></span></p>
<p><span data-ttu-id="c995a-168">Недели всегда отсчитываются с воскресенья по субботу.</span><span class="sxs-lookup"><span data-stu-id="c995a-168">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c995a-169"><strong>Интервал</strong></span><span class="sxs-lookup"><span data-stu-id="c995a-169"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="c995a-p113">Временной интервал. Выберите одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="c995a-p113">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="c995a-172">Ежечасно (можно отобразить не более 25 часов)</span><span class="sxs-lookup"><span data-stu-id="c995a-172">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="c995a-173">Ежедневно (можно отобразить не более 31 дня)</span><span class="sxs-lookup"><span data-stu-id="c995a-173">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="c995a-174">Еженедельно (можно отобразить не более 12 недель)</span><span class="sxs-lookup"><span data-stu-id="c995a-174">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="c995a-175">Ежемесячно (можно отобразить не более 12 месяцев)</span><span class="sxs-lookup"><span data-stu-id="c995a-175">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="c995a-176">Если количество значений между начальной и конечной датами превышает максимально допустимое для выбранного интервала, отображается максимальное возможное количество значений (от начальной даты и далее).</span><span class="sxs-lookup"><span data-stu-id="c995a-176">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed.</span></span> <span data-ttu-id="c995a-177">Например, если выбрать ежедневный интервал с датой начала 7/7/2012 и датой окончания 2/28/2012, данные будут выводиться для дней 8/7/2012 12:00 – 9/7/2012 12:00 AM (то есть, всего за 31 дня).</span><span class="sxs-lookup"><span data-stu-id="c995a-177">For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c995a-178"><strong>Пул</strong></span><span class="sxs-lookup"><span data-stu-id="c995a-178"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="c995a-p115">Полное доменное имя пула регистратора или пограничного сервера. Можно выбрать отдельный пул или нажать <strong>[Все]</strong>, чтобы просмотреть данные для всех пулов. Этот раскрывающийся список автоматически заполняется на основе записей в базе данных.</span><span class="sxs-lookup"><span data-stu-id="c995a-p115">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c995a-182"><strong>Модальность</strong></span><span class="sxs-lookup"><span data-stu-id="c995a-182"><strong>Modality</strong></span></span></p></td>
<td><p><span data-ttu-id="c995a-p116">Указывает на тип взаимодействия. Выберите один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="c995a-p116">Indicates the type of communication activity that took place. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="c995a-185">[Все]</span><span class="sxs-lookup"><span data-stu-id="c995a-185">[All]</span></span></p></li>
<li><p><span data-ttu-id="c995a-186">Обмен мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="c995a-186">Instant messaging</span></span></p></li>
<li><p><span data-ttu-id="c995a-187">Передача файлов</span><span class="sxs-lookup"><span data-stu-id="c995a-187">File transfer</span></span></p></li>
<li><p><span data-ttu-id="c995a-188">Общий доступ к приложениям</span><span class="sxs-lookup"><span data-stu-id="c995a-188">Application sharing</span></span></p></li>
<li><p><span data-ttu-id="c995a-189">Аудио</span><span class="sxs-lookup"><span data-stu-id="c995a-189">Audio</span></span></p></li>
<li><p><span data-ttu-id="c995a-190">Видео</span><span class="sxs-lookup"><span data-stu-id="c995a-190">Video</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-per-modality"></a><span data-ttu-id="c995a-191">Показатели (для каждой модальности)</span><span class="sxs-lookup"><span data-stu-id="c995a-191">Metrics (per modality)</span></span>

<span data-ttu-id="c995a-192">В следующей таблице показаны сведения, содержащиеся в диагностическом отчете об одноранговом обмене данными для каждой модальности.</span><span class="sxs-lookup"><span data-stu-id="c995a-192">The following table lists the information provided in the Peer-to-Peer Activity Diagnostic Report for each modality.</span></span>

### <a name="metrics-per-modality"></a><span data-ttu-id="c995a-193">Показатели (для каждой модальности)</span><span class="sxs-lookup"><span data-stu-id="c995a-193">Metrics (per modality)</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c995a-194">Имя</span><span class="sxs-lookup"><span data-stu-id="c995a-194">Name</span></span></th>
<th><span data-ttu-id="c995a-195">Поддержка сортировки</span><span class="sxs-lookup"><span data-stu-id="c995a-195">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="c995a-196">Описание</span><span class="sxs-lookup"><span data-stu-id="c995a-196">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c995a-197"><strong>Success volume (Объем успешной связи)</strong></span><span class="sxs-lookup"><span data-stu-id="c995a-197"><strong>Success volume</strong></span></span></p></td>
<td><p><span data-ttu-id="c995a-198">Нет</span><span class="sxs-lookup"><span data-stu-id="c995a-198">No</span></span></p></td>
<td><p><span data-ttu-id="c995a-199">Общее количество успешных одноранговых сеансов.</span><span class="sxs-lookup"><span data-stu-id="c995a-199">Total number of successful peer-to-peer sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c995a-200"><strong>Успех, процент</strong></span><span class="sxs-lookup"><span data-stu-id="c995a-200"><strong>Success percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="c995a-201">Нет</span><span class="sxs-lookup"><span data-stu-id="c995a-201">No</span></span></p></td>
<td><p><span data-ttu-id="c995a-p117">Процент одноранговых сеансов, которые завершились без серьезных проблем. Вычисляется путем деления количества успешных сеансов на общее их количество.</span><span class="sxs-lookup"><span data-stu-id="c995a-p117">Percentage of peer-to-peer sessions that completed with significant problems. Calculated by dividing the Success volume by the Total sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c995a-204"><strong>Ожидаемый отказ, объем</strong></span><span class="sxs-lookup"><span data-stu-id="c995a-204"><strong>Expected failure volume</strong></span></span></p></td>
<td><p><span data-ttu-id="c995a-205">Нет</span><span class="sxs-lookup"><span data-stu-id="c995a-205">No</span></span></p></td>
<td><p><span data-ttu-id="c995a-206">Общее количество сеансов, в &quot;которых произошла&quot; ожидаемая ошибка.</span><span class="sxs-lookup"><span data-stu-id="c995a-206">Total number of sessions where an &quot;expected failure&quot; occurred.</span></span></p>
<p><span data-ttu-id="c995a-p118">Ожидаемый сбой ? это сбой, возникновение которого ожидаемо. Например, если пользователь задал для себя состояние «Не беспокоить», можно ожидать, что любой звонок этому пользователю будет неудачным.</span><span class="sxs-lookup"><span data-stu-id="c995a-p118">An expected failure is a failure that is expected to happen. For example, if a user has set his or her status to Do Not Disturb you would expect any call to that user to fail.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c995a-209"><strong>Expected failure percentage (Доля ожидаемых сбоев)</strong></span><span class="sxs-lookup"><span data-stu-id="c995a-209"><strong>Expected failure percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="c995a-210">Нет</span><span class="sxs-lookup"><span data-stu-id="c995a-210">No</span></span></p></td>
<td><p><span data-ttu-id="c995a-p119">Процент одноранговых сеансов, в рамках которых произошли ожидаемые отказы. Вычисляется путем деления количества ожидаемых отказов на общее количество сеансов.</span><span class="sxs-lookup"><span data-stu-id="c995a-p119">Percentage of peer-to-peer sessions that experienced an expected error. Calculated by dividing the Expected failure volume by the Total sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c995a-213"><strong>Неожиданный отказ, объем</strong></span><span class="sxs-lookup"><span data-stu-id="c995a-213"><strong>Unexpected failure volume</strong></span></span></p></td>
<td><p><span data-ttu-id="c995a-214">Нет</span><span class="sxs-lookup"><span data-stu-id="c995a-214">No</span></span></p></td>
<td><p><span data-ttu-id="c995a-215">Общее количество сеансов, в &quot;которых произошла&quot; непредвиденная ошибка.</span><span class="sxs-lookup"><span data-stu-id="c995a-215">Total number of sessions where an &quot;unexpected failure&quot; occurred.</span></span></p>
<p><span data-ttu-id="c995a-p120">Неожиданный сбой ? это событие, которое в других условиях считалось бы нормальной работой системы. Например, звонок не следует завершать, если звонящий переведен в режим удержания. Если такое произошло, данное событие будет обозначено как неожиданный сбой.</span><span class="sxs-lookup"><span data-stu-id="c995a-p120">An unexpected failure is a failure that occurs in what would appear to be an otherwise healthy system. For example, a call should not be terminated if the caller is placed on hold. If that occurs, that would be flagged as an unexpected failure.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c995a-219"><strong>Unexpected failure percentage (Доля неожиданных сбоев)</strong></span><span class="sxs-lookup"><span data-stu-id="c995a-219"><strong>Unexpected failure percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="c995a-220">Нет</span><span class="sxs-lookup"><span data-stu-id="c995a-220">No</span></span></p></td>
<td><p><span data-ttu-id="c995a-p121">Процент одноранговых сеансов, в рамках которых произошли неожиданные отказы. Вычисляется путем деления количества неожиданных отказов на общее количество сеансов.</span><span class="sxs-lookup"><span data-stu-id="c995a-p121">Percentage of peer-to-peer sessions that experienced an unexpected error. Calculated by dividing the Unexpected failure volume by the Total sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c995a-223"><strong>Всего сеансов</strong></span><span class="sxs-lookup"><span data-stu-id="c995a-223"><strong>Total sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="c995a-224">Нет</span><span class="sxs-lookup"><span data-stu-id="c995a-224">No</span></span></p></td>
<td><p><span data-ttu-id="c995a-225">Общее число сеансов, включая успешные и завершившиеся сбоем (как ожидаемые, так и неожиданные сбои) и сеансы без категорий.</span><span class="sxs-lookup"><span data-stu-id="c995a-225">Total number of sessions, including successful sessions, failed sessions (both expected failures and unexpected failures), and uncategorized sessions.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

