---
title: 'Lync Server 2013: отчет о распределении сбоев'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failure Distribution Report
ms:assetid: 365c7beb-24d4-40f5-92e7-4978b9688916
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558635(v=OCS.15)
ms:contentKeyID: 48183849
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c1531b7b103e3df6f2d165a4fd6fcd3abf100132
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42179626"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="failure-distribution-report-in-lync-server-2013"></a><span data-ttu-id="0114d-102">Отчет о распределении сбоев в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0114d-102">Failure Distribution Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0114d-103">_**Последнее изменение темы:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="0114d-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="0114d-104">В отчете о распределении сбоев неудачные сеансы оцениваются в следующих категориях:</span><span class="sxs-lookup"><span data-stu-id="0114d-104">The Failure Distribution Report ranks failed sessions in the following categories:</span></span>

  - <span data-ttu-id="0114d-105">самые распространенные причины диагностики;</span><span class="sxs-lookup"><span data-stu-id="0114d-105">Top diagnostic reasons</span></span>

  - <span data-ttu-id="0114d-106">самые распространенные модальности;</span><span class="sxs-lookup"><span data-stu-id="0114d-106">Top modalities</span></span>

  - <span data-ttu-id="0114d-107">самые распространенные пулы;</span><span class="sxs-lookup"><span data-stu-id="0114d-107">Top pools</span></span>

  - <span data-ttu-id="0114d-108">самые распространенные источники;</span><span class="sxs-lookup"><span data-stu-id="0114d-108">Top sources</span></span>

  - <span data-ttu-id="0114d-109">самые распространенные компоненты;</span><span class="sxs-lookup"><span data-stu-id="0114d-109">Top components</span></span>

  - <span data-ttu-id="0114d-110">самые распространенные вызывающие пользователи;</span><span class="sxs-lookup"><span data-stu-id="0114d-110">Top from users</span></span>

  - <span data-ttu-id="0114d-111">самые распространенные вызываемые пользователи;</span><span class="sxs-lookup"><span data-stu-id="0114d-111">Top to users</span></span>

  - <span data-ttu-id="0114d-112">самые распространенные вызывающие агенты пользователей.</span><span class="sxs-lookup"><span data-stu-id="0114d-112">Top from user agents</span></span>

<span data-ttu-id="0114d-p101">С помощью этих категорий вы можете точно определить, где именно возникла проблема (а в некоторых случаях и причину ее возникновения). Предположим, что вы записали 242 аудио- или видеосеанса с ошибками за день. В отчете о распределении сбоев может быть показано, что 237 неудачных сеансов состоялись в пуле Дублин. Это дает вам хорошую отправную точку для отслеживания и диагностики причин этих сбоев. Если выбрать пул Дублин в категории **Основные пулы**, вы увидите отчет о распределении сбоев только для этого пула. Затем вы можете начать анализировать, почему в пуле Дублин было так много проблем.</span><span class="sxs-lookup"><span data-stu-id="0114d-p101">You can use these categories to determine exactly where a problem is occurring and, in some cases, why the problem is occurring. For example, suppose you recorded 242 failed audio/video sessions during a given day. If you look at the Failure Distribution Report, it might show that 237 of those failed sessions took place in your Dublin pool. That gives you a good place to start when it comes to tracking down and diagnosing the causes behind those failures. If you click on the Dublin pool under the **Top pools** category, you will see a Failure Distribution Report just for that pool. You can then begin analyzing why the Dublin pool was experiencing so many difficulties.</span></span>

<div>

## <a name="viewing-the-failure-distribution-report"></a><span data-ttu-id="0114d-119">Просмотр отчета о распределении сбоев</span><span class="sxs-lookup"><span data-stu-id="0114d-119">Viewing the Failure Distribution Report</span></span>

<span data-ttu-id="0114d-120">Обратиться к отчету о распределении сбоев можно из любого из следующих отчетов, щелкнув показатель **Том ожидаемого сбоя** или **Том неожиданного сбоя**:</span><span class="sxs-lookup"><span data-stu-id="0114d-120">You can access the Failure Distribution Report from any of the following reports by clicking either the **Expected failure volume** or the **Unexpected failure volume** metric:</span></span>

  - [<span data-ttu-id="0114d-121">Отчет о самых сбоях в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0114d-121">Top Failures Report in Lync Server 2013</span></span>](lync-server-2013-top-failures-report.md)

  - [<span data-ttu-id="0114d-122">Диагностический отчет по конференциям в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0114d-122">Conference Diagnostic Report in Lync Server 2013</span></span>](lync-server-2013-conference-diagnostic-report.md)

  - [<span data-ttu-id="0114d-123">Диагностический отчет об одноранговых действиях в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0114d-123">Peer-to-Peer Activity Diagnostic Report in Lync Server 2013</span></span>](lync-server-2013-peer-to-peer-activity-diagnostic-report.md)

<span data-ttu-id="0114d-124">В отчете распределения сбоев можно щелкнуть любой из следующих метрик, чтобы просмотреть [отчет по списку отказов в Lync Server 2013](lync-server-2013-failure-list-report.md):</span><span class="sxs-lookup"><span data-stu-id="0114d-124">From the Failure Distribution Report, you can click any of the following metrics to view the [Failure List Report in Lync Server 2013](lync-server-2013-failure-list-report.md):</span></span>

  - <span data-ttu-id="0114d-125">Top diagnostic reasons (sessions) (Основные причины диагностики (сеансы))</span><span class="sxs-lookup"><span data-stu-id="0114d-125">Top diagnostic reasons (sessions)</span></span>

  - <span data-ttu-id="0114d-126">Top modalities (sessions) (Основные условия (сеансы))</span><span class="sxs-lookup"><span data-stu-id="0114d-126">Top modalities (sessions)</span></span>

  - <span data-ttu-id="0114d-127">Top pools (sessions) (Основные пулы (сеансы))</span><span class="sxs-lookup"><span data-stu-id="0114d-127">Top pools (sessions)</span></span>

  - <span data-ttu-id="0114d-128">Top sources (sessions) (Основные источники (сеансы))</span><span class="sxs-lookup"><span data-stu-id="0114d-128">Top sources (sessions)</span></span>

  - <span data-ttu-id="0114d-129">Top components (sessions) (Основные компоненты (сеансы))</span><span class="sxs-lookup"><span data-stu-id="0114d-129">Top components (sessions)</span></span>

  - <span data-ttu-id="0114d-130">Top from users (sessions) (Основные пользователи с ошибками исходящей связи (сеансы))</span><span class="sxs-lookup"><span data-stu-id="0114d-130">Top from users (sessions)</span></span>

  - <span data-ttu-id="0114d-131">Top to users (sessions) (Основные пользователи с ошибками входящей связи (сеансы))</span><span class="sxs-lookup"><span data-stu-id="0114d-131">Top to users (sessions)</span></span>

  - <span data-ttu-id="0114d-132">самые распространенные вызывающие агенты пользователей (сеансы).</span><span class="sxs-lookup"><span data-stu-id="0114d-132">Top from user agents (sessions)</span></span>

</div>

<div>

## <a name="using-the-failure-distribution-report"></a><span data-ttu-id="0114d-133">Использование отчета о распределении сбоев</span><span class="sxs-lookup"><span data-stu-id="0114d-133">Using the Failure Distribution Report</span></span>

<span data-ttu-id="0114d-p102">В зависимости от размера и разрешения экрана некоторые данные в отчете о распределении сбоев при просмотре на экране могут усекаться. Это особенно актуально для таких показателей, как агенты пользователя, у которых могут быть очень длинные метки. Например, агент пользователя с именем UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Lync 2013) может только частично появится на экране:</span><span class="sxs-lookup"><span data-stu-id="0114d-p102">Depending on your monitor size and screen resolution, it's possible that some of the data shown in the Failure Distribution Report might be truncated when you view it onscreen. This is especially true for metrics such as user agents, which can have very long labels. For example, a user agent with a name like "UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Lync 2013)" might only partially appear onscreen:</span></span>

<span data-ttu-id="0114d-137">UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Ly...</span><span class="sxs-lookup"><span data-stu-id="0114d-137">UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Ly...</span></span>

<span data-ttu-id="0114d-138">К счастью, всю метку можно увидеть, просто удерживая указатель мыши над усеченным значением.</span><span class="sxs-lookup"><span data-stu-id="0114d-138">Fortunately, you can see the entire label simply by holding your mouse over the truncated value.</span></span>

<span data-ttu-id="0114d-p103">Один из интересных показателей, который можно использовать для фильтрации с помощью отчета распределения сбоев — это код диагностики. Если вы видите один и тот же код в других отчетах, можно отфильтровать отчет по этому коду и получить очень подробные сведения о том, где именно и как часто этот код появлялся в ошибочном сеансе.</span><span class="sxs-lookup"><span data-stu-id="0114d-p103">One interesting metric that you can filter on by using the Failure Distribution Report is Diagnostic ID. If you see the same Diagnostic ID cropping up in other reports you can filter on that ID in the Failure Distribution Report and get a very detailed look at exactly where, and how often, that ID has been reported during a failed session.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="0114d-141">Фильтры</span><span class="sxs-lookup"><span data-stu-id="0114d-141">Filters</span></span>

<span data-ttu-id="0114d-p104">Фильтры позволяют получать более точный набор данных или просматривать данные различными способами. Например, отчет распределения сбоев позволяет фильтровать данные по таким элементам, как тип деятельности (одноранговый сеанс или сеанс конференц-связи) или код диагностики, связанный с каждым ошибочным сеансом.</span><span class="sxs-lookup"><span data-stu-id="0114d-p104">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Failed Distribution Report enables you to filter on such things as the activity type (peer-to-peer session or conferencing session) or by the diagnostic ID that accompanied each failed session.</span></span>

<span data-ttu-id="0114d-144">В следующей таблице приведены фильтры, которые можно использовать с отчетом распределения сбоев.</span><span class="sxs-lookup"><span data-stu-id="0114d-144">The following table lists the filters that you can use with the Failure Distribution Report.</span></span>

### <a name="failure-distribution-report-filters"></a><span data-ttu-id="0114d-145">Фильтры отчета распределения сбоев</span><span class="sxs-lookup"><span data-stu-id="0114d-145">Failure Distribution Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0114d-146">Имя</span><span class="sxs-lookup"><span data-stu-id="0114d-146">Name</span></span></th>
<th><span data-ttu-id="0114d-147">Описание</span><span class="sxs-lookup"><span data-stu-id="0114d-147">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0114d-148"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="0114d-148"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="0114d-p105">Дата и время начала диапазона. Чтобы просмотреть данные по часам, введите дату и время начала в следующем формате:</span><span class="sxs-lookup"><span data-stu-id="0114d-p105">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="0114d-151">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="0114d-151">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="0114d-p106">Если не указать время начала, автоматически будет выбрано время 00:00 указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</span><span class="sxs-lookup"><span data-stu-id="0114d-p106">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="0114d-154">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="0114d-154">7/7/2012</span></span></p>
<p><span data-ttu-id="0114d-155">Для просмотра по неделям или по месяцам введите дату, выпадающую на любой день недели или месяца, который вы хотите просмотреть (это необязательно должен быть первый день недели или месяца):</span><span class="sxs-lookup"><span data-stu-id="0114d-155">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="0114d-156">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="0114d-156">7/3/2012</span></span></p>
<p><span data-ttu-id="0114d-157">Неделя всегда начинается с воскресенья и заканчивается субботой.</span><span class="sxs-lookup"><span data-stu-id="0114d-157">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0114d-158"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="0114d-158"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="0114d-p107">Дата и время окончания диапазона. Чтобы просмотреть данные по часам, введите дату и время окончания в следующем формате:</span><span class="sxs-lookup"><span data-stu-id="0114d-p107">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="0114d-161">7/7/2012 13:00.</span><span class="sxs-lookup"><span data-stu-id="0114d-161">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="0114d-p108">Если не указать время окончания, автоматически будет выбрано время 00:00 указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</span><span class="sxs-lookup"><span data-stu-id="0114d-p108">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="0114d-164">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="0114d-164">7/7/2012</span></span></p>
<p><span data-ttu-id="0114d-165">Для просмотра по неделям или по месяцам введите дату, выпадающую на любой день недели или месяца, который вы хотите просмотреть (это необязательно должен быть первый день недели или месяца):</span><span class="sxs-lookup"><span data-stu-id="0114d-165">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="0114d-166">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="0114d-166">7/3/2012</span></span></p>
<p><span data-ttu-id="0114d-167">Неделя всегда начинается с воскресения и заканчивается субботой.</span><span class="sxs-lookup"><span data-stu-id="0114d-167">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0114d-168"><strong>Ресурсов</strong></span><span class="sxs-lookup"><span data-stu-id="0114d-168"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="0114d-p109">Полное доменное имя пула регистратора или пограничного сервера. Можно выбрать отдельный пул или нажать <strong>[Все]</strong>, чтобы просмотреть данные для всех пулов. Этот раскрывающийся список автоматически заполняется на основе записей в базе данных.</span><span class="sxs-lookup"><span data-stu-id="0114d-p109">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0114d-172"><strong>Тип деятельности</strong></span><span class="sxs-lookup"><span data-stu-id="0114d-172"><strong>Activity type</strong></span></span></p></td>
<td><p><span data-ttu-id="0114d-p110">Тип деятельности, к которому требуется применить фильтр. Выберите один из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="0114d-p110">Type of activity to filter on. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="0114d-175">Ко</span><span class="sxs-lookup"><span data-stu-id="0114d-175">[All]</span></span></p></li>
<li><p><span data-ttu-id="0114d-176">"Peer-to-peer" (Одноранговый сеанс);</span><span class="sxs-lookup"><span data-stu-id="0114d-176">Peer-to-peer</span></span></p></li>
<li><p><span data-ttu-id="0114d-177">Встречи</span><span class="sxs-lookup"><span data-stu-id="0114d-177">Conference</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0114d-178"><strong>Категория сеанса</strong></span><span class="sxs-lookup"><span data-stu-id="0114d-178"><strong>Session category</strong></span></span></p></td>
<td><p><span data-ttu-id="0114d-p111">Указывает, была ли рассматриваемая активность успешна. Выберите одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="0114d-p111">Indicates whether the activity in question succeeded or failed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="0114d-181">Ко</span><span class="sxs-lookup"><span data-stu-id="0114d-181">[All]</span></span></p></li>
<li><p><span data-ttu-id="0114d-182">Success</span><span class="sxs-lookup"><span data-stu-id="0114d-182">Success</span></span></p></li>
<li><p><span data-ttu-id="0114d-183">Expected failure (Ожидаемый сбой)</span><span class="sxs-lookup"><span data-stu-id="0114d-183">Expected failure</span></span></p></li>
<li><p><span data-ttu-id="0114d-184">Непредвиденный сбой</span><span class="sxs-lookup"><span data-stu-id="0114d-184">Unexpected failure</span></span></p></li>
</ul>
<p><span data-ttu-id="0114d-185">&quot;Ожидаемый сбой&quot; — это сбой, который должен произойти.</span><span class="sxs-lookup"><span data-stu-id="0114d-185">An &quot;expected failure&quot; is a failure that is expected to happen.</span></span> <span data-ttu-id="0114d-186">Например, если пользователь установил статус "Не беспокоить", то ожидаемое, что все вызовы этого пользователя завершатся неудачно.</span><span class="sxs-lookup"><span data-stu-id="0114d-186">For example, if a user has set his or her status to Do Not Disturb you would expect any call to that user to fail.</span></span> <span data-ttu-id="0114d-187">&quot;Непредвиденный сбой&quot; — это проблема, которая может показаться неработоспособной системой.</span><span class="sxs-lookup"><span data-stu-id="0114d-187">An &quot;unexpected failure&quot; is a failure that occurs in what would appear to be an otherwise healthy system.</span></span> <span data-ttu-id="0114d-188">Например, вызов не должен прерываться, если вызывающий абонент помещается на удержание.</span><span class="sxs-lookup"><span data-stu-id="0114d-188">For example, a call should not be terminated if the caller is placed on hold.</span></span> <span data-ttu-id="0114d-189">В этом случае это считается непредвиденным сбоем.</span><span class="sxs-lookup"><span data-stu-id="0114d-189">If that occurs, that would be flagged as an unexpected failure.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0114d-190"><strong>Код диагностики</strong></span><span class="sxs-lookup"><span data-stu-id="0114d-190"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="0114d-p113">Уникальный идентификатор (в виде заголовка ms-diagnostics), прикрепленный к сообщению SIP, которое часто содержит полезные сведения для устранения ошибок. Заголовки диагностики являются необязательными (можно использовать SIP-сеансы без этих заголовков), а коды диагностики указываются только для сеансов, в которых были обнаружены определенные проблемы.</span><span class="sxs-lookup"><span data-stu-id="0114d-p113">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-diagnostic-reasons"></a><span data-ttu-id="0114d-193">Показатели для самых распространенных причин диагностики</span><span class="sxs-lookup"><span data-stu-id="0114d-193">Metrics for Top Diagnostic Reasons</span></span>

<span data-ttu-id="0114d-194">В следующей таблице представлены сведения, приведенные в отчете распределения сбоев на основе самых распространенных кодов диагностики.</span><span class="sxs-lookup"><span data-stu-id="0114d-194">The following table lists the information provided in the Failure Distribution Report based on the most frequently reported diagnostic ID.</span></span>

### <a name="metrics-for-top-diagnostic-reasons"></a><span data-ttu-id="0114d-195">Показатели для самых распространенных причин диагностики</span><span class="sxs-lookup"><span data-stu-id="0114d-195">Metrics for Top Diagnostic Reasons</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0114d-196">Имя</span><span class="sxs-lookup"><span data-stu-id="0114d-196">Name</span></span></th>
<th><span data-ttu-id="0114d-197">Возможность сортировки по этому показателю</span><span class="sxs-lookup"><span data-stu-id="0114d-197">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="0114d-198">Описание</span><span class="sxs-lookup"><span data-stu-id="0114d-198">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0114d-199"><strong>Rank</strong></span><span class="sxs-lookup"><span data-stu-id="0114d-199"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="0114d-200">Нет</span><span class="sxs-lookup"><span data-stu-id="0114d-200">No</span></span></p></td>
<td><p><span data-ttu-id="0114d-p114">Относительное ранжирование неудачных сеансов на основе кодов диагностики. Код диагностики — это уникальный идентификатор (в виде заголовка ms-diagnostics), прикрепленный к сообщению SIP, которое часто содержит полезные сведения для устранения ошибок.</span><span class="sxs-lookup"><span data-stu-id="0114d-p114">Relative ranking of failed sessions based on diagnostic IDs. The diagnostic ID is a unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0114d-203"><strong>Самые распространенные причины диагностики</strong></span><span class="sxs-lookup"><span data-stu-id="0114d-203"><strong>Top diagnostic reasons</strong></span></span></p></td>
<td><p><span data-ttu-id="0114d-204">Нет</span><span class="sxs-lookup"><span data-stu-id="0114d-204">No</span></span></p></td>
<td><p><span data-ttu-id="0114d-205">Код, созданный во время сеанса.</span><span class="sxs-lookup"><span data-stu-id="0114d-205">Diagnostic ID generated in a session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0114d-206"><strong>Сеансы</strong></span><span class="sxs-lookup"><span data-stu-id="0114d-206"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="0114d-207">Нет</span><span class="sxs-lookup"><span data-stu-id="0114d-207">No</span></span></p></td>
<td><p><span data-ttu-id="0114d-208">Общее количество неудачных сеансов, в которых был создан указанный код диагностики.</span><span class="sxs-lookup"><span data-stu-id="0114d-208">Total number of failed sessions where the specified diagnostic ID was generated.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-modalities"></a><span data-ttu-id="0114d-209">Показатели для самых распространенных модальностей</span><span class="sxs-lookup"><span data-stu-id="0114d-209">Metrics for Top Modalities</span></span>

<span data-ttu-id="0114d-210">В следующей таблице содержатся сведения, приведенные в отчете распределения сбоев на основе модальностей сеансов, в которых произошло больше всего ошибок.</span><span class="sxs-lookup"><span data-stu-id="0114d-210">The following table lists the information provided in the Failure Distribution Report based on the session modalities that experienced the most failures.</span></span>

### <a name="metrics-for-top-modalities"></a><span data-ttu-id="0114d-211">Показатели для самых распространенных модальностей</span><span class="sxs-lookup"><span data-stu-id="0114d-211">Metrics for Top Modalities</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0114d-212">Имя</span><span class="sxs-lookup"><span data-stu-id="0114d-212">Name</span></span></th>
<th><span data-ttu-id="0114d-213">Возможность сортировки по этому показателю</span><span class="sxs-lookup"><span data-stu-id="0114d-213">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="0114d-214">Описание</span><span class="sxs-lookup"><span data-stu-id="0114d-214">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0114d-215"><strong>Rank</strong></span><span class="sxs-lookup"><span data-stu-id="0114d-215"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="0114d-216">Нет</span><span class="sxs-lookup"><span data-stu-id="0114d-216">No</span></span></p></td>
<td><p><span data-ttu-id="0114d-217">Относительное ранжирование неудачных сеансов на основе типа сеанса (например, аудио- или видеоконференция или одноранговый сеанс передачи файлов).</span><span class="sxs-lookup"><span data-stu-id="0114d-217">Relative ranking based of failed session based on session type (for example, an audio/video conference or a peer-to-peer file transfer session).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0114d-218"><strong>Самые распространенные модальности</strong></span><span class="sxs-lookup"><span data-stu-id="0114d-218"><strong>Top modalities</strong></span></span></p></td>
<td><p><span data-ttu-id="0114d-219">Нет</span><span class="sxs-lookup"><span data-stu-id="0114d-219">No</span></span></p></td>
<td><p><span data-ttu-id="0114d-220">Тип сеанса.</span><span class="sxs-lookup"><span data-stu-id="0114d-220">Session type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0114d-221"><strong>Сеансы</strong></span><span class="sxs-lookup"><span data-stu-id="0114d-221"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="0114d-222">Нет</span><span class="sxs-lookup"><span data-stu-id="0114d-222">No</span></span></p></td>
<td><p><span data-ttu-id="0114d-223">Общее количество неудачных сеансов с указанной модальностью.</span><span class="sxs-lookup"><span data-stu-id="0114d-223">Total number of failed sessions involving the specified modality.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-pools"></a><span data-ttu-id="0114d-224">Показатели для самых распространенных пулов</span><span class="sxs-lookup"><span data-stu-id="0114d-224">Metrics for Top Pools</span></span>

<span data-ttu-id="0114d-225">В следующей таблице содержатся сведения, приведенные в отчете распределения сбоев на основе пулов, в которых произошло больше всего ошибок.</span><span class="sxs-lookup"><span data-stu-id="0114d-225">The following table lists the information provided in the Failure Distribution Report based on the pools that experienced the most failures.</span></span>

### <a name="metrics-for-top-pools"></a><span data-ttu-id="0114d-226">Показатели для самых распространенных пулов</span><span class="sxs-lookup"><span data-stu-id="0114d-226">Metrics for Top Pools</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0114d-227">Имя</span><span class="sxs-lookup"><span data-stu-id="0114d-227">Name</span></span></th>
<th><span data-ttu-id="0114d-228">Возможность сортировки по этому показателю</span><span class="sxs-lookup"><span data-stu-id="0114d-228">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="0114d-229">Описание</span><span class="sxs-lookup"><span data-stu-id="0114d-229">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0114d-230"><strong>Rank</strong></span><span class="sxs-lookup"><span data-stu-id="0114d-230"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="0114d-231">Нет</span><span class="sxs-lookup"><span data-stu-id="0114d-231">No</span></span></p></td>
<td><p><span data-ttu-id="0114d-232">Относительное ранжирование неудачных сеансов на основе пула регистратора или пограничного сервера, на котором выполнялся сеанс.</span><span class="sxs-lookup"><span data-stu-id="0114d-232">Relative ranking of failed sessions based on the Registrar pool or Edge Server where the session was conducted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0114d-233"><strong>Самые распространенные пулы</strong></span><span class="sxs-lookup"><span data-stu-id="0114d-233"><strong>Top pools</strong></span></span></p></td>
<td><p><span data-ttu-id="0114d-234">Нет</span><span class="sxs-lookup"><span data-stu-id="0114d-234">No</span></span></p></td>
<td><p><span data-ttu-id="0114d-235">Имя пула регистратора или пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="0114d-235">Name of the Registrar pool or Edge Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0114d-236"><strong>Сеансы</strong></span><span class="sxs-lookup"><span data-stu-id="0114d-236"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="0114d-237">Нет</span><span class="sxs-lookup"><span data-stu-id="0114d-237">No</span></span></p></td>
<td><p><span data-ttu-id="0114d-238">Общее количество неудачных сеансов на пул регистратора или пограничный сервер.</span><span class="sxs-lookup"><span data-stu-id="0114d-238">Total number of failed sessions per Registrar pool or Edge Server.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-sources"></a><span data-ttu-id="0114d-239">Показатели для самых распространенных источников</span><span class="sxs-lookup"><span data-stu-id="0114d-239">Metrics for Top Sources</span></span>

<span data-ttu-id="0114d-240">В следующей таблице содержатся сведения, приведенные в отчете распределения сбоев на основе компьютеров, в которых произошло больше всего ошибок.</span><span class="sxs-lookup"><span data-stu-id="0114d-240">The following table lists the information provided in the Failure Distribution Report based on the computers that experienced the most failures.</span></span>

### <a name="metrics-for-top-sources"></a><span data-ttu-id="0114d-241">Показатели для самых распространенных источников</span><span class="sxs-lookup"><span data-stu-id="0114d-241">Metrics for Top Sources</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0114d-242">Имя</span><span class="sxs-lookup"><span data-stu-id="0114d-242">Name</span></span></th>
<th><span data-ttu-id="0114d-243">Возможность сортировки по этому показателю</span><span class="sxs-lookup"><span data-stu-id="0114d-243">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="0114d-244">Описание</span><span class="sxs-lookup"><span data-stu-id="0114d-244">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0114d-245"><strong>Rank</strong></span><span class="sxs-lookup"><span data-stu-id="0114d-245"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="0114d-246">Нет</span><span class="sxs-lookup"><span data-stu-id="0114d-246">No</span></span></p></td>
<td><p><span data-ttu-id="0114d-247">Относительное ранжирование неудачных сеансов на компьютер.</span><span class="sxs-lookup"><span data-stu-id="0114d-247">Relative ranking failed sessions per computer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0114d-248"><strong>Самые распространенные источники</strong></span><span class="sxs-lookup"><span data-stu-id="0114d-248"><strong>Top sources</strong></span></span></p></td>
<td><p><span data-ttu-id="0114d-249">Нет</span><span class="sxs-lookup"><span data-stu-id="0114d-249">No</span></span></p></td>
<td><p><span data-ttu-id="0114d-250">Имя компьютера, используемого в неудачном сеансе.</span><span class="sxs-lookup"><span data-stu-id="0114d-250">Name of the computer involved in the failed session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0114d-251"><strong>Сеансы</strong></span><span class="sxs-lookup"><span data-stu-id="0114d-251"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="0114d-252">Нет</span><span class="sxs-lookup"><span data-stu-id="0114d-252">No</span></span></p></td>
<td><p><span data-ttu-id="0114d-253">Общее количество неудачных сеансов на компьютер.</span><span class="sxs-lookup"><span data-stu-id="0114d-253">Total number of failed sessions per computer.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-components"></a><span data-ttu-id="0114d-254">Показатели для самых распространенных компонентов</span><span class="sxs-lookup"><span data-stu-id="0114d-254">Metrics for Top Components</span></span>

<span data-ttu-id="0114d-255">В следующей таблице приведены сведения, приведенные в отчете распределения сбоев на основе компонентов Microsoft Lync Server 2010, которые столкнулись с большинством сбоев.</span><span class="sxs-lookup"><span data-stu-id="0114d-255">The following table lists the information provided in the Failure Distribution Report based on the Microsoft Lync Server 2010 components that experienced the most failures.</span></span>

### <a name="metrics-for-top-components"></a><span data-ttu-id="0114d-256">Показатели для самых распространенных компонентов</span><span class="sxs-lookup"><span data-stu-id="0114d-256">Metrics for Top Components</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0114d-257">Имя</span><span class="sxs-lookup"><span data-stu-id="0114d-257">Name</span></span></th>
<th><span data-ttu-id="0114d-258">Возможность сортировки по этому показателю</span><span class="sxs-lookup"><span data-stu-id="0114d-258">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="0114d-259">Описание</span><span class="sxs-lookup"><span data-stu-id="0114d-259">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0114d-260"><strong>Rank</strong></span><span class="sxs-lookup"><span data-stu-id="0114d-260"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="0114d-261">Нет</span><span class="sxs-lookup"><span data-stu-id="0114d-261">No</span></span></p></td>
<td><p><span data-ttu-id="0114d-262">Относительное ранжирование неудачных сеансов на основе компонента Lync Server 2010 (например, ExumRouting, GroupChat или MediationServer).</span><span class="sxs-lookup"><span data-stu-id="0114d-262">Relative ranking of failed sessions based on Lync Server 2010 component (for example, ExumRouting, GroupChat, or MediationServer).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0114d-263"><strong>Самые распространенные компоненты</strong></span><span class="sxs-lookup"><span data-stu-id="0114d-263"><strong>Top components</strong></span></span></p></td>
<td><p><span data-ttu-id="0114d-264">Нет</span><span class="sxs-lookup"><span data-stu-id="0114d-264">No</span></span></p></td>
<td><p><span data-ttu-id="0114d-265">Имя компонента, используемого в неудачном сеансе.</span><span class="sxs-lookup"><span data-stu-id="0114d-265">Name of the component involved in the failed session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0114d-266"><strong>Сеансы</strong></span><span class="sxs-lookup"><span data-stu-id="0114d-266"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="0114d-267">Нет</span><span class="sxs-lookup"><span data-stu-id="0114d-267">No</span></span></p></td>
<td><p><span data-ttu-id="0114d-268">Общее количество неудачных сеансов на компонент.</span><span class="sxs-lookup"><span data-stu-id="0114d-268">Total number of failed sessions per component.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-from-users"></a><span data-ttu-id="0114d-269">Показатели для самых распространенных вызывающих пользователей</span><span class="sxs-lookup"><span data-stu-id="0114d-269">Metrics for Top From Users</span></span>

<span data-ttu-id="0114d-270">В следующей таблице представлены сведения, приведенные в отчета распределения сбоев на основе числа пользователей, у которых возникло больше всего ошибок, когда они пытались звонить кому-нибудь еще (которых также называют "вызывающими" пользователями).</span><span class="sxs-lookup"><span data-stu-id="0114d-270">The following table lists the information provided in the Failure Distribution Report based on users who experienced the most failures when they tried to call someone else (known as "From" users).</span></span>

### <a name="metrics-for-top-from-users"></a><span data-ttu-id="0114d-271">Показатели для самых распространенных вызывающих пользователей</span><span class="sxs-lookup"><span data-stu-id="0114d-271">Metrics for Top From Users</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0114d-272">Имя</span><span class="sxs-lookup"><span data-stu-id="0114d-272">Name</span></span></th>
<th><span data-ttu-id="0114d-273">Возможность сортировки по этому показателю</span><span class="sxs-lookup"><span data-stu-id="0114d-273">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="0114d-274">Описание</span><span class="sxs-lookup"><span data-stu-id="0114d-274">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0114d-275"><strong>Rank</strong></span><span class="sxs-lookup"><span data-stu-id="0114d-275"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="0114d-276">Нет</span><span class="sxs-lookup"><span data-stu-id="0114d-276">No</span></span></p></td>
<td><p><span data-ttu-id="0114d-277">Относительно ранжирование неудачных сеансов на основе пользователя, который был приглашен для присоединения к сеансу.</span><span class="sxs-lookup"><span data-stu-id="0114d-277">Relative ranking of failed sessions based on the user who was invited to join the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0114d-278"><strong>Самые распространенные вызывающие пользователи</strong></span><span class="sxs-lookup"><span data-stu-id="0114d-278"><strong>Top from users</strong></span></span></p></td>
<td><p><span data-ttu-id="0114d-279">Нет</span><span class="sxs-lookup"><span data-stu-id="0114d-279">No</span></span></p></td>
<td><p><span data-ttu-id="0114d-280">SIP-адрес пользователя, приглашенного в сеанс.</span><span class="sxs-lookup"><span data-stu-id="0114d-280">SIP address of the user invited to join the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0114d-281"><strong>Сеансы</strong></span><span class="sxs-lookup"><span data-stu-id="0114d-281"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="0114d-282">Нет</span><span class="sxs-lookup"><span data-stu-id="0114d-282">No</span></span></p></td>
<td><p><span data-ttu-id="0114d-283">Общее количество неудачных сеансов на пользователя.</span><span class="sxs-lookup"><span data-stu-id="0114d-283">Total number of failed sessions per user.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-to-users"></a><span data-ttu-id="0114d-284">Показатели для самых распространенных вызываемых пользователей</span><span class="sxs-lookup"><span data-stu-id="0114d-284">Metrics for Top To Users</span></span>

<span data-ttu-id="0114d-285">В следующей таблице представлены сведения, приведенные в отчета распределения сбоев на основе пользователей, у которых возникло больше всего ошибок, когда кто-то другой пытался позвонить им (их также называют "вызываемыми" пользователями).</span><span class="sxs-lookup"><span data-stu-id="0114d-285">The following table lists the information provided in the Failure Distribution Report based on the users who experienced the most failures when another user tried to call them (known as "To" users).</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0114d-286">Имя</span><span class="sxs-lookup"><span data-stu-id="0114d-286">Name</span></span></th>
<th><span data-ttu-id="0114d-287">Возможность сортировки по этому показателю</span><span class="sxs-lookup"><span data-stu-id="0114d-287">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="0114d-288">Описание</span><span class="sxs-lookup"><span data-stu-id="0114d-288">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0114d-289"><strong>Rank</strong></span><span class="sxs-lookup"><span data-stu-id="0114d-289"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="0114d-290">Нет</span><span class="sxs-lookup"><span data-stu-id="0114d-290">No</span></span></p></td>
<td><p><span data-ttu-id="0114d-291">Относительно ранжирование неудачных сеансов на основе пользователя, инициировавшего сеанс.</span><span class="sxs-lookup"><span data-stu-id="0114d-291">Relative ranking of failed sessions based on the user who initiated the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0114d-292"><strong>Самые распространенные вызываемые пользователи</strong></span><span class="sxs-lookup"><span data-stu-id="0114d-292"><strong>Top to users</strong></span></span></p></td>
<td><p><span data-ttu-id="0114d-293">Нет</span><span class="sxs-lookup"><span data-stu-id="0114d-293">No</span></span></p></td>
<td><p><span data-ttu-id="0114d-294">SIP-адрес пользователя, который инициировал сеанс.</span><span class="sxs-lookup"><span data-stu-id="0114d-294">SIP address of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0114d-295"><strong>Сеансы</strong></span><span class="sxs-lookup"><span data-stu-id="0114d-295"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="0114d-296">Нет</span><span class="sxs-lookup"><span data-stu-id="0114d-296">No</span></span></p></td>
<td><p><span data-ttu-id="0114d-297">Общее количество неудачных сеансов на пользователя.</span><span class="sxs-lookup"><span data-stu-id="0114d-297">Total number of failed sessions per user.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-user-agents"></a><span data-ttu-id="0114d-298">Показатели для самых распространенных агентов пользователей</span><span class="sxs-lookup"><span data-stu-id="0114d-298">Metrics for Top User Agents</span></span>

<span data-ttu-id="0114d-299">В следующей таблице содержатся сведения, приведенные в отчете распределения сбоев на основе программного обеспечения конечных точек, в которых произошло больше всего ошибок.</span><span class="sxs-lookup"><span data-stu-id="0114d-299">The following table lists the information provided in the Failure Distribution Report based on the endpoint software that experienced the most failures.</span></span>

### <a name="metrics-for-top-user-agents"></a><span data-ttu-id="0114d-300">Показатели для самых распространенных агентов пользователей</span><span class="sxs-lookup"><span data-stu-id="0114d-300">Metrics for Top User Agents</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0114d-301">Имя</span><span class="sxs-lookup"><span data-stu-id="0114d-301">Name</span></span></th>
<th><span data-ttu-id="0114d-302">Возможность сортировки по этому показателю</span><span class="sxs-lookup"><span data-stu-id="0114d-302">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="0114d-303">Описание</span><span class="sxs-lookup"><span data-stu-id="0114d-303">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0114d-304"><strong>Rank</strong></span><span class="sxs-lookup"><span data-stu-id="0114d-304"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="0114d-305">Нет</span><span class="sxs-lookup"><span data-stu-id="0114d-305">No</span></span></p></td>
<td><p><span data-ttu-id="0114d-p115">Относительное ранжирование неудачных сеансов на основе агента пользователя (программного обеспечения), применяемого в сеансе. Например: RTCC/4.0.0.0 Входящее перенаправление/4.0.0.0.</span><span class="sxs-lookup"><span data-stu-id="0114d-p115">Relative ranking of failed sessions based on the user agent (software) involved in the session. For example: RTCC/4.0.0.0 Inbound Routing/4.0.0.0.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0114d-308"><strong>Самые распространенные агенты пользователей</strong></span><span class="sxs-lookup"><span data-stu-id="0114d-308"><strong>Top user agents</strong></span></span></p></td>
<td><p><span data-ttu-id="0114d-309">Нет</span><span class="sxs-lookup"><span data-stu-id="0114d-309">No</span></span></p></td>
<td><p><span data-ttu-id="0114d-310">Имя агента пользователя, применяемого в неудачном сеансе.</span><span class="sxs-lookup"><span data-stu-id="0114d-310">Name of the user agent involved in the failed session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0114d-311"><strong>Сеансы</strong></span><span class="sxs-lookup"><span data-stu-id="0114d-311"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="0114d-312">Нет</span><span class="sxs-lookup"><span data-stu-id="0114d-312">No</span></span></p></td>
<td><p><span data-ttu-id="0114d-313">Общее количество неудачных сеансов на агента пользователя.</span><span class="sxs-lookup"><span data-stu-id="0114d-313">Total number of failed sessions per user agent.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

