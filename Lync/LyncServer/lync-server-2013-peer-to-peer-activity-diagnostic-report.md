---
title: 'Lync Server 2013: диагностический отчет об одноранговой активности'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Peer-to-Peer Activity Diagnostic Report
ms:assetid: 025e8ab4-2e64-4a6b-8f52-caf756a5cac3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558602(v=OCS.15)
ms:contentKeyID: 48183242
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 53e47232a6345749f78f6136929209722a83621e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48524396"
---
# <a name="peer-to-peer-activity-diagnostic-report-in-lync-server-2013"></a><span data-ttu-id="69639-102">Диагностический отчет об одноранговых действиях в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="69639-102">Peer-to-Peer Activity Diagnostic Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="69639-103">_**Последнее изменение темы:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="69639-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="69639-104">Диагностический отчет об одноранговом обмене данными предоставляет сведения об успешных и неудавшихся сеансах однорангового обмена данными.</span><span class="sxs-lookup"><span data-stu-id="69639-104">The Peer-to-Peer Activity Diagnostic Report provides information about the success and failure of your peer-to-peer communication sessions.</span></span> <span data-ttu-id="69639-105">Обратите внимание, что Microsoft Lync Server 2013 различает различные типы сбоев:</span><span class="sxs-lookup"><span data-stu-id="69639-105">Note that Microsoft Lync Server 2013 distinguishes between different kinds of failure:</span></span>

  - <span data-ttu-id="69639-106">**Ожидаемый отказ**.</span><span class="sxs-lookup"><span data-stu-id="69639-106">**Expected failure**.</span></span> <span data-ttu-id="69639-107">Под ожидаемым отказом обычно понимается отказ в сугубо техническом смысле.</span><span class="sxs-lookup"><span data-stu-id="69639-107">An expected failure is typically a failure only in the most technical sense.</span></span> <span data-ttu-id="69639-108">Например, предположим, что вы звоните кому-то, но этого человека нет на месте, и он не может ответить на звонок.</span><span class="sxs-lookup"><span data-stu-id="69639-108">For example, suppose you call someone, but he or she is away from the office and is unable to answer the phone.</span></span> <span data-ttu-id="69639-109">Поскольку на звонок не был получен ответ, такая ситуация технически считается отказом.</span><span class="sxs-lookup"><span data-stu-id="69639-109">Because the call was not answered, the call is technically considered a failure.</span></span> <span data-ttu-id="69639-110">С другой стороны, ожидаемый сбой: Microsoft Lync Server 2013 не ожидает ответа на телефон, если вы не можете ответить на телефон.</span><span class="sxs-lookup"><span data-stu-id="69639-110">On the other hand, this was an expected failure: Microsoft Lync Server 2013 does not expect you to answer the phone if you're not available to answer the phone.</span></span> <span data-ttu-id="69639-111">Аналогичным образом, ожидаемый отказ произойдет в том случае, если вы попытаетесь отправить мгновенное сообщение пользователю, которого нет в сети или который работает с телефона, не поддерживающего обмен мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="69639-111">Likewise, an expected failure will occur if you attempt to send an instant message to a user who is offline, or is logged on only to a phone that does not support instant messaging.</span></span>

  - <span data-ttu-id="69639-112">**Неожиданный сбой**.</span><span class="sxs-lookup"><span data-stu-id="69639-112">**Unexpected failure**.</span></span> <span data-ttu-id="69639-113">Непредвиденная ошибка — это именно то, что подразумевается: ошибка, которая в зависимости от обстоятельств не ожидается.</span><span class="sxs-lookup"><span data-stu-id="69639-113">An unexpected error is exactly what the name implies: an error that, based on the circumstances, you would not expect to occur.</span></span> <span data-ttu-id="69639-114">Например, вы звоните кому-то, и кто-то может ответить на звонок; Однако когда Lync Server 2013 пытается направить вызов в голосовую почту, происходит сбой вызова из-за потери подключения к единой системе обмена сообщениями Exchange.</span><span class="sxs-lookup"><span data-stu-id="69639-114">For example, suppose you call someone and that person is available to answer the call; however, when Lync Server 2013 tries to route your call to voicemail the call fails because connectivity to Exchange Unified Messaging has been lost.</span></span> <span data-ttu-id="69639-115">Это непредвиденная ошибка: вы ожидаете, что звонки всегда будут маршрутизироваться в голосовую почту.</span><span class="sxs-lookup"><span data-stu-id="69639-115">That's an unexpected error: you would expect that calls could always be routed to voicemail.</span></span> <span data-ttu-id="69639-116">Как правило, неожиданные сбои — это проблемы, которые, вероятно, не могут быть ремедиеды с помощью обучения пользователей или аналогичных мер.</span><span class="sxs-lookup"><span data-stu-id="69639-116">As a general rule, unexpected failures are true failures: they are problems that likely cannot be remedied through user education or similar measures.</span></span>

<span data-ttu-id="69639-p104">Обратите внимание на то, что число успешных сеансов, ожидаемых отказов и непредвиденных отказов может быть не равно в сумме общему числу сеансов. Например, имеются следующие значения.</span><span class="sxs-lookup"><span data-stu-id="69639-p104">Note that the Success, Expected failure, and Unexpected failure metrics might not add up to the Total sessions metric. For example, in the preceding illustration, we have the following values:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="69639-119">Успешные операции</span><span class="sxs-lookup"><span data-stu-id="69639-119">Successes</span></span></th>
<th><span data-ttu-id="69639-120">Число ожидаемых сбоев</span><span class="sxs-lookup"><span data-stu-id="69639-120">Expected failures</span></span></th>
<th><span data-ttu-id="69639-121">Число неожиданных сбоев</span><span class="sxs-lookup"><span data-stu-id="69639-121">Unexpected failures</span></span></th>
<th><span data-ttu-id="69639-122">Всего сеансов</span><span class="sxs-lookup"><span data-stu-id="69639-122">Total sessions</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="69639-123">2024</span><span class="sxs-lookup"><span data-stu-id="69639-123">2024</span></span></p></td>
<td><p><span data-ttu-id="69639-124">469</span><span class="sxs-lookup"><span data-stu-id="69639-124">469</span></span></p></td>
<td><p><span data-ttu-id="69639-125">16 </span><span class="sxs-lookup"><span data-stu-id="69639-125">16</span></span></p></td>
<td><p><span data-ttu-id="69639-126">2521</span><span class="sxs-lookup"><span data-stu-id="69639-126">2521</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="69639-127">Если сложить 2024 + 469 + 16, то получится 2509 сеансов, но в столбце "Всего сеансов" показано 2521 сеансов.</span><span class="sxs-lookup"><span data-stu-id="69639-127">If you add 2024 + 469 + 16 you get a total of 2,509 sessions, yet the Total sessions column shows a total of 2,521 sessions.</span></span> <span data-ttu-id="69639-128">"Недостающие" 12 сеансов — это сеансы, которые система не смогла определить как успешные или неудавшиеся.</span><span class="sxs-lookup"><span data-stu-id="69639-128">The "missing" 12 sessions are sessions that the system was unable to categorize as successful or unsuccessful.</span></span> <span data-ttu-id="69639-129">Это иногда происходит, когда сторонний продукт представляет новый диагностический код, незнакомый с Lync Server.</span><span class="sxs-lookup"><span data-stu-id="69639-129">That will sometimes be the case when a third-party product introduces a new diagnostic code that is unfamiliar to Lync Server.</span></span> <span data-ttu-id="69639-130">В этом случае звонки, совершенные с помощью этого продукта и зарегистрированные с помощью его кода диагностики, не всегда могут быть отнесены к успешным, ожидаемым отказам или непредвиденным отказам.</span><span class="sxs-lookup"><span data-stu-id="69639-130">When that happens, calls made using that product, and reporting that diagnostic code, cannot always be categorized as being a Success, an Expected failure, or an Unexpected failure.</span></span>

<div>

## <a name="accessing-the-peer-to-peer-activity-diagnostic-report"></a><span data-ttu-id="69639-131">Доступ к диагностическому отчету об одноранговом обмене данными</span><span class="sxs-lookup"><span data-stu-id="69639-131">Accessing the Peer-to-Peer Activity Diagnostic Report</span></span>

<span data-ttu-id="69639-132">Доступ к диагностическому отчету об одноранговом обмене данными можно получить с домашней страницы "Отчеты наблюдения".</span><span class="sxs-lookup"><span data-stu-id="69639-132">The Peer-to-Peer Diagnostic Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="69639-133">Вы можете получить доступ к [отчету распределения сбоев в Lync Server 2013](lync-server-2013-failure-distribution-report.md) , щелкнув один из следующих показателей:</span><span class="sxs-lookup"><span data-stu-id="69639-133">You can access the [Failure Distribution Report in Lync Server 2013](lync-server-2013-failure-distribution-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="69639-134">Unexpected failure volume (Неожиданный сбой, объем)</span><span class="sxs-lookup"><span data-stu-id="69639-134">Unexpected failure volume</span></span>

  - <span data-ttu-id="69639-135">Количество ожидаемых отказов</span><span class="sxs-lookup"><span data-stu-id="69639-135">Expected failure volume</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-activity-diagnostic-report"></a><span data-ttu-id="69639-136">Рекомендации по использованию диагностического отчета об одноранговом обмене данными</span><span class="sxs-lookup"><span data-stu-id="69639-136">Making the Best Use of the Peer-to-Peer Activity Diagnostic Report</span></span>

<span data-ttu-id="69639-p107">Имеется ряд способов фильтрации диагностического отчета об одноранговом обмене данными, но по умолчанию соответствующие параметры скрыты. Чтобы просмотреть доступные параметры фильтрации, нажмите кнопку "Показать или скрыть параметры" в правом верхнем углу окна отчета. Параметры фильтрации станут доступны для использования.</span><span class="sxs-lookup"><span data-stu-id="69639-p107">There are a number of ways you can filter the Peer-to-Peer Activity Diagnostic Report but, by default, those filtering options are hidden from view. To view the filtering options available to you, click the Show/Hide Parameters button in the upper right-hand corner of the report window. Once you do that the filtering options will be available for use.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="69639-140">Фильтры</span><span class="sxs-lookup"><span data-stu-id="69639-140">Filters</span></span>

<span data-ttu-id="69639-p108">Фильтры позволяют получить более конкретные наборы возвращаемых данных. Например, диагностический отчет об одноранговом обмене данными позволяет фильтровать данные по таким признакам, как модальность сеанса (например, обмен мгновенными сообщениями, передача файлов или общий доступ к приложениям). Вы также можете выбрать тип группировки данных. В этом случае звонки группируются по часам, дням или неделям.</span><span class="sxs-lookup"><span data-stu-id="69639-p108">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Peer-to-Peer Activity Diagnostic Report enables you to filter on such things as the session modality (for example, instant messaging, file transfer, or application sharing). You can also choose how data should be grouped. In this case, calls are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="69639-145">В следующем списке перечислены фильтры, которые можно использовать с диагностическим отчетом об одноранговом обмене данными.</span><span class="sxs-lookup"><span data-stu-id="69639-145">The following table lists the filters that you can use with the Peer-to-Peer Activity Diagnostic Report.</span></span>

### <a name="peer-to-peer-activity-diagnostic-report-filters"></a><span data-ttu-id="69639-146">Фильтры диагностического отчета об одноранговом обмене данными</span><span class="sxs-lookup"><span data-stu-id="69639-146">Peer-to-Peer Activity Diagnostic Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="69639-147">Имя</span><span class="sxs-lookup"><span data-stu-id="69639-147">Name</span></span></th>
<th><span data-ttu-id="69639-148">Описание</span><span class="sxs-lookup"><span data-stu-id="69639-148">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="69639-149"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="69639-149"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="69639-p109">Дата и время начала диапазона. Чтобы просмотреть данные по часам, введите дату и время начала в следующем формате:</span><span class="sxs-lookup"><span data-stu-id="69639-p109">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="69639-152">7/7/2012 13:00.</span><span class="sxs-lookup"><span data-stu-id="69639-152">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="69639-p110">Если не указать время начала, автоматически будет выбрано время 00:00 указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</span><span class="sxs-lookup"><span data-stu-id="69639-p110">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="69639-155">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="69639-155">7/7/2012</span></span></p>
<p><span data-ttu-id="69639-156">Для просмотра по неделям или по месяцам введите дату, выпадающую на любой день недели или месяца, который вы хотите просмотреть (это необязательно должен быть первый день недели или месяца):</span><span class="sxs-lookup"><span data-stu-id="69639-156">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="69639-157">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="69639-157">7/3/2012</span></span></p>
<p><span data-ttu-id="69639-158">Неделя всегда начинается с воскресения и заканчивается субботой.</span><span class="sxs-lookup"><span data-stu-id="69639-158">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69639-159"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="69639-159"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="69639-p111">Дата и время окончания диапазона. Чтобы просмотреть данные по часам, введите дату и время окончания в следующем формате:</span><span class="sxs-lookup"><span data-stu-id="69639-p111">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="69639-162">7/7/2012 13:00.</span><span class="sxs-lookup"><span data-stu-id="69639-162">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="69639-p112">Если не указать время окончания, автоматически будет выбрано время 00:00 указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</span><span class="sxs-lookup"><span data-stu-id="69639-p112">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="69639-165">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="69639-165">7/7/2012</span></span></p>
<p><span data-ttu-id="69639-166">Для просмотра по неделям или по месяцам введите дату, выпадающую на любой день недели или месяца, который вы хотите просмотреть (это необязательно должен быть первый день недели или месяца):</span><span class="sxs-lookup"><span data-stu-id="69639-166">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="69639-167">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="69639-167">7/3/2012</span></span></p>
<p><span data-ttu-id="69639-168">Неделя всегда начинается с воскресения и заканчивается субботой.</span><span class="sxs-lookup"><span data-stu-id="69639-168">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69639-169"><strong>Interval</strong></span><span class="sxs-lookup"><span data-stu-id="69639-169"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="69639-p113">Временной интервал. Выберите один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="69639-p113">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="69639-172">Ежечасно (может отображаться до 25 часов)</span><span class="sxs-lookup"><span data-stu-id="69639-172">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="69639-173">Ежедневно (может отображаться до 31 дня)</span><span class="sxs-lookup"><span data-stu-id="69639-173">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="69639-174">Еженедельно (может отображаться до 12 недель)</span><span class="sxs-lookup"><span data-stu-id="69639-174">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="69639-175">Ежемесячно (может отображаться до 12 месяцев)</span><span class="sxs-lookup"><span data-stu-id="69639-175">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="69639-p114">Если начальная и конечная даты превышают максимально допустимое количество значений для выбранного интервала, отображается только максимальное число значений (с отсчетом от начальной даты). Например, если вы выбрали интервал «Daily» с начальной датой 7/7/2012 и конечной датой 2/28/2012, отображаются данные по дням с 00:00 часов 8/7/2012  по 00:00 часов 9/7/2012 (то есть всего за 31 день).</span><span class="sxs-lookup"><span data-stu-id="69639-p114">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69639-178"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="69639-178"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="69639-p115">Полное доменное имя пула регистратора или пограничного сервера. Вы можете выбрать отдельный пул или щелкнуть <strong>[Все]</strong>, чтобы просмотреть данные по всем пулам. Этот раскрывающийся список заполняется автоматически в соответствии с записями в базе данных.</span><span class="sxs-lookup"><span data-stu-id="69639-p115">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69639-182"><strong>Модальности</strong></span><span class="sxs-lookup"><span data-stu-id="69639-182"><strong>Modality</strong></span></span></p></td>
<td><p><span data-ttu-id="69639-p116">Указывает на тип взаимодействия. Выберите один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="69639-p116">Indicates the type of communication activity that took place. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="69639-185">Ко</span><span class="sxs-lookup"><span data-stu-id="69639-185">[All]</span></span></p></li>
<li><p><span data-ttu-id="69639-186">Обмен мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="69639-186">Instant messaging</span></span></p></li>
<li><p><span data-ttu-id="69639-187">Передача файлов</span><span class="sxs-lookup"><span data-stu-id="69639-187">File transfer</span></span></p></li>
<li><p><span data-ttu-id="69639-188">Совместное использование приложений</span><span class="sxs-lookup"><span data-stu-id="69639-188">Application sharing</span></span></p></li>
<li><p><span data-ttu-id="69639-189">"Audio" (Аудио);</span><span class="sxs-lookup"><span data-stu-id="69639-189">Audio</span></span></p></li>
<li><p><span data-ttu-id="69639-190">"Video" (Видео);</span><span class="sxs-lookup"><span data-stu-id="69639-190">Video</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-per-modality"></a><span data-ttu-id="69639-191">Показатели (для каждой модальности)</span><span class="sxs-lookup"><span data-stu-id="69639-191">Metrics (per modality)</span></span>

<span data-ttu-id="69639-192">В следующей таблице показаны сведения, содержащиеся в диагностическом отчете об одноранговом обмене данными для каждой модальности.</span><span class="sxs-lookup"><span data-stu-id="69639-192">The following table lists the information provided in the Peer-to-Peer Activity Diagnostic Report for each modality.</span></span>

### <a name="metrics-per-modality"></a><span data-ttu-id="69639-193">Показатели (для каждой модальности)</span><span class="sxs-lookup"><span data-stu-id="69639-193">Metrics (per modality)</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="69639-194">Имя</span><span class="sxs-lookup"><span data-stu-id="69639-194">Name</span></span></th>
<th><span data-ttu-id="69639-195">Возможность сортировки по этому показателю</span><span class="sxs-lookup"><span data-stu-id="69639-195">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="69639-196">Описание</span><span class="sxs-lookup"><span data-stu-id="69639-196">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="69639-197"><strong>Success volume</strong> (Успех, объем)</span><span class="sxs-lookup"><span data-stu-id="69639-197"><strong>Success volume</strong></span></span></p></td>
<td><p><span data-ttu-id="69639-198">Нет</span><span class="sxs-lookup"><span data-stu-id="69639-198">No</span></span></p></td>
<td><p><span data-ttu-id="69639-199">Общее количество успешных одноранговых сеансов.</span><span class="sxs-lookup"><span data-stu-id="69639-199">Total number of successful peer-to-peer sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69639-200"><strong>Процент успешных сеансов</strong></span><span class="sxs-lookup"><span data-stu-id="69639-200"><strong>Success percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="69639-201">Нет</span><span class="sxs-lookup"><span data-stu-id="69639-201">No</span></span></p></td>
<td><p><span data-ttu-id="69639-p117">Процент одноранговых сеансов, которые завершились без серьезных проблем. Вычисляется путем деления количества успешных сеансов на общее их количество.</span><span class="sxs-lookup"><span data-stu-id="69639-p117">Percentage of peer-to-peer sessions that completed with significant problems. Calculated by dividing the Success volume by the Total sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69639-204"><strong>Количество ожидаемых отказов</strong></span><span class="sxs-lookup"><span data-stu-id="69639-204"><strong>Expected failure volume</strong></span></span></p></td>
<td><p><span data-ttu-id="69639-205">Нет</span><span class="sxs-lookup"><span data-stu-id="69639-205">No</span></span></p></td>
<td><p><span data-ttu-id="69639-206">Общее количество сеансов, в которых &quot; возник ожидаемый сбой &quot; .</span><span class="sxs-lookup"><span data-stu-id="69639-206">Total number of sessions where an &quot;expected failure&quot; occurred.</span></span></p>
<p><span data-ttu-id="69639-p118">Ожидаемый сбой ? это сбой, возникновение которого ожидаемо. Например, если пользователь задал для себя состояние «Не беспокоить», можно ожидать, что любой звонок этому пользователю будет неудачным.</span><span class="sxs-lookup"><span data-stu-id="69639-p118">An expected failure is a failure that is expected to happen. For example, if a user has set his or her status to Do Not Disturb you would expect any call to that user to fail.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69639-209"><strong>Expected failure percentage</strong> (Ожидаемый сбой, процент)</span><span class="sxs-lookup"><span data-stu-id="69639-209"><strong>Expected failure percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="69639-210">Нет</span><span class="sxs-lookup"><span data-stu-id="69639-210">No</span></span></p></td>
<td><p><span data-ttu-id="69639-p119">Процент одноранговых сеансов, в рамках которых произошли ожидаемые отказы. Вычисляется путем деления количества ожидаемых отказов на общее количество сеансов.</span><span class="sxs-lookup"><span data-stu-id="69639-p119">Percentage of peer-to-peer sessions that experienced an expected error. Calculated by dividing the Expected failure volume by the Total sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69639-213"><strong>Количество непредвиденных отказов</strong></span><span class="sxs-lookup"><span data-stu-id="69639-213"><strong>Unexpected failure volume</strong></span></span></p></td>
<td><p><span data-ttu-id="69639-214">Нет</span><span class="sxs-lookup"><span data-stu-id="69639-214">No</span></span></p></td>
<td><p><span data-ttu-id="69639-215">Общее количество сеансов, в которых &quot; произошла непредвиденная ошибка &quot; .</span><span class="sxs-lookup"><span data-stu-id="69639-215">Total number of sessions where an &quot;unexpected failure&quot; occurred.</span></span></p>
<p><span data-ttu-id="69639-p120">Неожиданный сбой ? это событие, которое в других условиях считалось бы нормальной работой системы. Например, звонок не следует завершать, если звонящий переведен в режим удержания. Если такое произошло, данное событие будет обозначено как неожиданный сбой.</span><span class="sxs-lookup"><span data-stu-id="69639-p120">An unexpected failure is a failure that occurs in what would appear to be an otherwise healthy system. For example, a call should not be terminated if the caller is placed on hold. If that occurs, that would be flagged as an unexpected failure.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69639-219"><strong>Unexpected failure percentage</strong> (Неожиданный сбой, процент)</span><span class="sxs-lookup"><span data-stu-id="69639-219"><strong>Unexpected failure percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="69639-220">Нет</span><span class="sxs-lookup"><span data-stu-id="69639-220">No</span></span></p></td>
<td><p><span data-ttu-id="69639-p121">Процент одноранговых сеансов, в рамках которых произошли непредвиденные отказы. Вычисляется путем деления количества непредвиденных отказов на общее количество сеансов.</span><span class="sxs-lookup"><span data-stu-id="69639-p121">Percentage of peer-to-peer sessions that experienced an unexpected error. Calculated by dividing the Unexpected failure volume by the Total sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69639-223"><strong>Всего сеансов</strong></span><span class="sxs-lookup"><span data-stu-id="69639-223"><strong>Total sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="69639-224">Нет</span><span class="sxs-lookup"><span data-stu-id="69639-224">No</span></span></p></td>
<td><p><span data-ttu-id="69639-225">Общее число сеансов, включая успешные сеансы, неудавшиеся сеансы (вследствие как ожидаемых, так и непредвиденных отказов) и сеансы, не отнесенные к определенной категории.</span><span class="sxs-lookup"><span data-stu-id="69639-225">Total number of sessions, including successful sessions, failed sessions (both expected failures and unexpected failures), and uncategorized sessions.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

