---
title: 'Lync Server 2013: отчет о распределении сбоев'
description: 'Lync Server 2013: отчет о распределении сбоев.'
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
ms.openlocfilehash: f5a87f779f87d6b7002fa108f1969c33739eed9b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564735"
---
# <a name="failure-distribution-report-in-lync-server-2013"></a><span data-ttu-id="ba926-103">Отчет о распределении сбоев в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ba926-103">Failure Distribution Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ba926-104">_**Последнее изменение темы:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="ba926-104">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="ba926-105">В отчете о распределении сбоев неудачные сеансы оцениваются в следующих категориях:</span><span class="sxs-lookup"><span data-stu-id="ba926-105">The Failure Distribution Report ranks failed sessions in the following categories:</span></span>

  - <span data-ttu-id="ba926-106">самые распространенные причины диагностики;</span><span class="sxs-lookup"><span data-stu-id="ba926-106">Top diagnostic reasons</span></span>

  - <span data-ttu-id="ba926-107">самые распространенные модальности;</span><span class="sxs-lookup"><span data-stu-id="ba926-107">Top modalities</span></span>

  - <span data-ttu-id="ba926-108">самые распространенные пулы;</span><span class="sxs-lookup"><span data-stu-id="ba926-108">Top pools</span></span>

  - <span data-ttu-id="ba926-109">самые распространенные источники;</span><span class="sxs-lookup"><span data-stu-id="ba926-109">Top sources</span></span>

  - <span data-ttu-id="ba926-110">самые распространенные компоненты;</span><span class="sxs-lookup"><span data-stu-id="ba926-110">Top components</span></span>

  - <span data-ttu-id="ba926-111">самые распространенные вызывающие пользователи;</span><span class="sxs-lookup"><span data-stu-id="ba926-111">Top from users</span></span>

  - <span data-ttu-id="ba926-112">самые распространенные вызываемые пользователи;</span><span class="sxs-lookup"><span data-stu-id="ba926-112">Top to users</span></span>

  - <span data-ttu-id="ba926-113">самые распространенные вызывающие агенты пользователей.</span><span class="sxs-lookup"><span data-stu-id="ba926-113">Top from user agents</span></span>

<span data-ttu-id="ba926-p101">С помощью этих категорий вы можете точно определить, где именно возникла проблема (а в некоторых случаях и причину ее возникновения). Предположим, что вы записали 242 аудио- или видеосеанса с ошибками за день. В отчете о распределении сбоев может быть показано, что 237 неудачных сеансов состоялись в пуле Дублин. Это дает вам хорошую отправную точку для отслеживания и диагностики причин этих сбоев. Если выбрать пул Дублин в категории **Основные пулы**, вы увидите отчет о распределении сбоев только для этого пула. Затем вы можете начать анализировать, почему в пуле Дублин было так много проблем.</span><span class="sxs-lookup"><span data-stu-id="ba926-p101">You can use these categories to determine exactly where a problem is occurring and, in some cases, why the problem is occurring. For example, suppose you recorded 242 failed audio/video sessions during a given day. If you look at the Failure Distribution Report, it might show that 237 of those failed sessions took place in your Dublin pool. That gives you a good place to start when it comes to tracking down and diagnosing the causes behind those failures. If you click on the Dublin pool under the **Top pools** category, you will see a Failure Distribution Report just for that pool. You can then begin analyzing why the Dublin pool was experiencing so many difficulties.</span></span>

<div>

## <a name="viewing-the-failure-distribution-report"></a><span data-ttu-id="ba926-120">Просмотр отчета о распределении сбоев</span><span class="sxs-lookup"><span data-stu-id="ba926-120">Viewing the Failure Distribution Report</span></span>

<span data-ttu-id="ba926-121">Обратиться к отчету о распределении сбоев можно из любого из следующих отчетов, щелкнув показатель **Том ожидаемого сбоя** или **Том неожиданного сбоя**:</span><span class="sxs-lookup"><span data-stu-id="ba926-121">You can access the Failure Distribution Report from any of the following reports by clicking either the **Expected failure volume** or the **Unexpected failure volume** metric:</span></span>

  - [<span data-ttu-id="ba926-122">Отчет о самых сбоях в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ba926-122">Top Failures Report in Lync Server 2013</span></span>](lync-server-2013-top-failures-report.md)

  - [<span data-ttu-id="ba926-123">Диагностический отчет по конференциям в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ba926-123">Conference Diagnostic Report in Lync Server 2013</span></span>](lync-server-2013-conference-diagnostic-report.md)

  - [<span data-ttu-id="ba926-124">Диагностический отчет об одноранговых действиях в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ba926-124">Peer-to-Peer Activity Diagnostic Report in Lync Server 2013</span></span>](lync-server-2013-peer-to-peer-activity-diagnostic-report.md)

<span data-ttu-id="ba926-125">В отчете распределения сбоев можно щелкнуть любой из следующих метрик, чтобы просмотреть [отчет по списку отказов в Lync Server 2013](lync-server-2013-failure-list-report.md):</span><span class="sxs-lookup"><span data-stu-id="ba926-125">From the Failure Distribution Report, you can click any of the following metrics to view the [Failure List Report in Lync Server 2013](lync-server-2013-failure-list-report.md):</span></span>

  - <span data-ttu-id="ba926-126">Top diagnostic reasons (sessions) (Основные причины диагностики (сеансы))</span><span class="sxs-lookup"><span data-stu-id="ba926-126">Top diagnostic reasons (sessions)</span></span>

  - <span data-ttu-id="ba926-127">Top modalities (sessions) (Основные условия (сеансы))</span><span class="sxs-lookup"><span data-stu-id="ba926-127">Top modalities (sessions)</span></span>

  - <span data-ttu-id="ba926-128">Top pools (sessions) (Основные пулы (сеансы))</span><span class="sxs-lookup"><span data-stu-id="ba926-128">Top pools (sessions)</span></span>

  - <span data-ttu-id="ba926-129">Top sources (sessions) (Основные источники (сеансы))</span><span class="sxs-lookup"><span data-stu-id="ba926-129">Top sources (sessions)</span></span>

  - <span data-ttu-id="ba926-130">Top components (sessions) (Основные компоненты (сеансы))</span><span class="sxs-lookup"><span data-stu-id="ba926-130">Top components (sessions)</span></span>

  - <span data-ttu-id="ba926-131">Top from users (sessions) (Основные пользователи с ошибками исходящей связи (сеансы))</span><span class="sxs-lookup"><span data-stu-id="ba926-131">Top from users (sessions)</span></span>

  - <span data-ttu-id="ba926-132">Top to users (sessions) (Основные пользователи с ошибками входящей связи (сеансы))</span><span class="sxs-lookup"><span data-stu-id="ba926-132">Top to users (sessions)</span></span>

  - <span data-ttu-id="ba926-133">самые распространенные вызывающие агенты пользователей (сеансы).</span><span class="sxs-lookup"><span data-stu-id="ba926-133">Top from user agents (sessions)</span></span>

</div>

<div>

## <a name="using-the-failure-distribution-report"></a><span data-ttu-id="ba926-134">Использование отчета о распределении сбоев</span><span class="sxs-lookup"><span data-stu-id="ba926-134">Using the Failure Distribution Report</span></span>

<span data-ttu-id="ba926-p102">В зависимости от размера и разрешения экрана некоторые данные в отчете о распределении сбоев при просмотре на экране могут усекаться. Это особенно актуально для таких показателей, как агенты пользователя, у которых могут быть очень длинные метки. Например, агент пользователя с именем UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Lync 2013) может только частично появится на экране:</span><span class="sxs-lookup"><span data-stu-id="ba926-p102">Depending on your monitor size and screen resolution, it's possible that some of the data shown in the Failure Distribution Report might be truncated when you view it onscreen. This is especially true for metrics such as user agents, which can have very long labels. For example, a user agent with a name like "UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Lync 2013)" might only partially appear onscreen:</span></span>

<span data-ttu-id="ba926-138">UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Ly...</span><span class="sxs-lookup"><span data-stu-id="ba926-138">UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Ly...</span></span>

<span data-ttu-id="ba926-139">К счастью, всю метку можно увидеть, просто удерживая указатель мыши над усеченным значением.</span><span class="sxs-lookup"><span data-stu-id="ba926-139">Fortunately, you can see the entire label simply by holding your mouse over the truncated value.</span></span>

<span data-ttu-id="ba926-p103">Один из интересных показателей, который можно использовать для фильтрации с помощью отчета распределения сбоев — это код диагностики. Если вы видите один и тот же код в других отчетах, можно отфильтровать отчет по этому коду и получить очень подробные сведения о том, где именно и как часто этот код появлялся в ошибочном сеансе.</span><span class="sxs-lookup"><span data-stu-id="ba926-p103">One interesting metric that you can filter on by using the Failure Distribution Report is Diagnostic ID. If you see the same Diagnostic ID cropping up in other reports you can filter on that ID in the Failure Distribution Report and get a very detailed look at exactly where, and how often, that ID has been reported during a failed session.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="ba926-142">Фильтры</span><span class="sxs-lookup"><span data-stu-id="ba926-142">Filters</span></span>

<span data-ttu-id="ba926-p104">Фильтры позволяют получать более точный набор данных или просматривать данные различными способами. Например, отчет распределения сбоев позволяет фильтровать данные по таким элементам, как тип деятельности (одноранговый сеанс или сеанс конференц-связи) или код диагностики, связанный с каждым ошибочным сеансом.</span><span class="sxs-lookup"><span data-stu-id="ba926-p104">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Failed Distribution Report enables you to filter on such things as the activity type (peer-to-peer session or conferencing session) or by the diagnostic ID that accompanied each failed session.</span></span>

<span data-ttu-id="ba926-145">В следующей таблице приведены фильтры, которые можно использовать с отчетом распределения сбоев.</span><span class="sxs-lookup"><span data-stu-id="ba926-145">The following table lists the filters that you can use with the Failure Distribution Report.</span></span>

### <a name="failure-distribution-report-filters"></a><span data-ttu-id="ba926-146">Фильтры отчета распределения сбоев</span><span class="sxs-lookup"><span data-stu-id="ba926-146">Failure Distribution Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ba926-147">Имя</span><span class="sxs-lookup"><span data-stu-id="ba926-147">Name</span></span></th>
<th><span data-ttu-id="ba926-148">Описание</span><span class="sxs-lookup"><span data-stu-id="ba926-148">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ba926-149"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="ba926-149"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="ba926-p105">Дата и время начала диапазона. Чтобы просмотреть данные по часам, введите дату и время начала в следующем формате:</span><span class="sxs-lookup"><span data-stu-id="ba926-p105">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="ba926-152">7/7/2012 13:00.</span><span class="sxs-lookup"><span data-stu-id="ba926-152">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="ba926-p106">Если не указать время начала, автоматически будет выбрано время 00:00 указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</span><span class="sxs-lookup"><span data-stu-id="ba926-p106">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="ba926-155">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="ba926-155">7/7/2012</span></span></p>
<p><span data-ttu-id="ba926-156">Для просмотра по неделям или по месяцам введите дату, выпадающую на любой день недели или месяца, который вы хотите просмотреть (это необязательно должен быть первый день недели или месяца):</span><span class="sxs-lookup"><span data-stu-id="ba926-156">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="ba926-157">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="ba926-157">7/3/2012</span></span></p>
<p><span data-ttu-id="ba926-158">Неделя всегда начинается с воскресения и заканчивается субботой.</span><span class="sxs-lookup"><span data-stu-id="ba926-158">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba926-159"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="ba926-159"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="ba926-p107">Дата и время окончания диапазона. Чтобы просмотреть данные по часам, введите дату и время окончания в следующем формате:</span><span class="sxs-lookup"><span data-stu-id="ba926-p107">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="ba926-162">7/7/2012 13:00.</span><span class="sxs-lookup"><span data-stu-id="ba926-162">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="ba926-p108">Если не указать время окончания, автоматически будет выбрано время 00:00 указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</span><span class="sxs-lookup"><span data-stu-id="ba926-p108">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="ba926-165">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="ba926-165">7/7/2012</span></span></p>
<p><span data-ttu-id="ba926-166">Для просмотра по неделям или по месяцам введите дату, выпадающую на любой день недели или месяца, который вы хотите просмотреть (это необязательно должен быть первый день недели или месяца):</span><span class="sxs-lookup"><span data-stu-id="ba926-166">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="ba926-167">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="ba926-167">7/3/2012</span></span></p>
<p><span data-ttu-id="ba926-168">Неделя всегда начинается с воскресения и заканчивается субботой.</span><span class="sxs-lookup"><span data-stu-id="ba926-168">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba926-169"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="ba926-169"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="ba926-p109">Полное доменное имя пула регистратора или пограничного сервера. Можно выбрать отдельный пул или нажать <strong>[Все]</strong>, чтобы просмотреть данные для всех пулов. Этот раскрывающийся список автоматически заполняется на основе записей в базе данных.</span><span class="sxs-lookup"><span data-stu-id="ba926-p109">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba926-173"><strong>Тип деятельности</strong></span><span class="sxs-lookup"><span data-stu-id="ba926-173"><strong>Activity type</strong></span></span></p></td>
<td><p><span data-ttu-id="ba926-p110">Тип деятельности, к которому требуется применить фильтр. Выберите один из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="ba926-p110">Type of activity to filter on. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="ba926-176">Ко</span><span class="sxs-lookup"><span data-stu-id="ba926-176">[All]</span></span></p></li>
<li><p><span data-ttu-id="ba926-177">"Peer-to-peer" (Одноранговый сеанс);</span><span class="sxs-lookup"><span data-stu-id="ba926-177">Peer-to-peer</span></span></p></li>
<li><p><span data-ttu-id="ba926-178">Conference</span><span class="sxs-lookup"><span data-stu-id="ba926-178">Conference</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba926-179"><strong>Категория сеанса</strong></span><span class="sxs-lookup"><span data-stu-id="ba926-179"><strong>Session category</strong></span></span></p></td>
<td><p><span data-ttu-id="ba926-p111">Указывает, была ли рассматриваемая активность успешна. Выберите одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="ba926-p111">Indicates whether the activity in question succeeded or failed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="ba926-182">Ко</span><span class="sxs-lookup"><span data-stu-id="ba926-182">[All]</span></span></p></li>
<li><p><span data-ttu-id="ba926-183">Успешно</span><span class="sxs-lookup"><span data-stu-id="ba926-183">Success</span></span></p></li>
<li><p><span data-ttu-id="ba926-184">Expected failure (Ожидаемый сбой)</span><span class="sxs-lookup"><span data-stu-id="ba926-184">Expected failure</span></span></p></li>
<li><p><span data-ttu-id="ba926-185">Непредвиденный сбой</span><span class="sxs-lookup"><span data-stu-id="ba926-185">Unexpected failure</span></span></p></li>
</ul>
<p><span data-ttu-id="ba926-186">&quot;Ожидаемый сбой &quot; — это сбой, который должен произойти.</span><span class="sxs-lookup"><span data-stu-id="ba926-186">An &quot;expected failure&quot; is a failure that is expected to happen.</span></span> <span data-ttu-id="ba926-187">Например, если пользователь установил статус "Не беспокоить", то ожидаемое, что все вызовы этого пользователя завершатся неудачно.</span><span class="sxs-lookup"><span data-stu-id="ba926-187">For example, if a user has set his or her status to Do Not Disturb you would expect any call to that user to fail.</span></span> <span data-ttu-id="ba926-188">&quot;Непредвиденный сбой &quot; — это проблема, которая может показаться неработоспособной системой.</span><span class="sxs-lookup"><span data-stu-id="ba926-188">An &quot;unexpected failure&quot; is a failure that occurs in what would appear to be an otherwise healthy system.</span></span> <span data-ttu-id="ba926-189">Например, вызов не должен прерываться, если вызывающий абонент помещается на удержание.</span><span class="sxs-lookup"><span data-stu-id="ba926-189">For example, a call should not be terminated if the caller is placed on hold.</span></span> <span data-ttu-id="ba926-190">В этом случае это считается непредвиденным сбоем.</span><span class="sxs-lookup"><span data-stu-id="ba926-190">If that occurs, that would be flagged as an unexpected failure.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba926-191"><strong>Код диагностики</strong></span><span class="sxs-lookup"><span data-stu-id="ba926-191"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="ba926-p113">Уникальный идентификатор (в виде заголовка ms-diagnostics), прикрепленный к сообщению SIP, которое часто содержит полезные сведения для устранения ошибок. Заголовки диагностики являются необязательными (можно использовать SIP-сеансы без этих заголовков), а коды диагностики указываются только для сеансов, в которых были обнаружены определенные проблемы.</span><span class="sxs-lookup"><span data-stu-id="ba926-p113">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-diagnostic-reasons"></a><span data-ttu-id="ba926-194">Показатели для самых распространенных причин диагностики</span><span class="sxs-lookup"><span data-stu-id="ba926-194">Metrics for Top Diagnostic Reasons</span></span>

<span data-ttu-id="ba926-195">В следующей таблице представлены сведения, приведенные в отчете распределения сбоев на основе самых распространенных кодов диагностики.</span><span class="sxs-lookup"><span data-stu-id="ba926-195">The following table lists the information provided in the Failure Distribution Report based on the most frequently reported diagnostic ID.</span></span>

### <a name="metrics-for-top-diagnostic-reasons"></a><span data-ttu-id="ba926-196">Показатели для самых распространенных причин диагностики</span><span class="sxs-lookup"><span data-stu-id="ba926-196">Metrics for Top Diagnostic Reasons</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ba926-197">Имя</span><span class="sxs-lookup"><span data-stu-id="ba926-197">Name</span></span></th>
<th><span data-ttu-id="ba926-198">Возможность сортировки по этому показателю</span><span class="sxs-lookup"><span data-stu-id="ba926-198">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="ba926-199">Описание</span><span class="sxs-lookup"><span data-stu-id="ba926-199">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ba926-200"><strong>Rank</strong></span><span class="sxs-lookup"><span data-stu-id="ba926-200"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="ba926-201">Нет</span><span class="sxs-lookup"><span data-stu-id="ba926-201">No</span></span></p></td>
<td><p><span data-ttu-id="ba926-p114">Относительное ранжирование неудачных сеансов на основе кодов диагностики. Код диагностики — это уникальный идентификатор (в виде заголовка ms-diagnostics), прикрепленный к сообщению SIP, которое часто содержит полезные сведения для устранения ошибок.</span><span class="sxs-lookup"><span data-stu-id="ba926-p114">Relative ranking of failed sessions based on diagnostic IDs. The diagnostic ID is a unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba926-204"><strong>Самые распространенные причины диагностики</strong></span><span class="sxs-lookup"><span data-stu-id="ba926-204"><strong>Top diagnostic reasons</strong></span></span></p></td>
<td><p><span data-ttu-id="ba926-205">Нет</span><span class="sxs-lookup"><span data-stu-id="ba926-205">No</span></span></p></td>
<td><p><span data-ttu-id="ba926-206">Код, созданный во время сеанса.</span><span class="sxs-lookup"><span data-stu-id="ba926-206">Diagnostic ID generated in a session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba926-207"><strong>Сеансы</strong></span><span class="sxs-lookup"><span data-stu-id="ba926-207"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="ba926-208">Нет</span><span class="sxs-lookup"><span data-stu-id="ba926-208">No</span></span></p></td>
<td><p><span data-ttu-id="ba926-209">Общее количество неудачных сеансов, в которых был создан указанный код диагностики.</span><span class="sxs-lookup"><span data-stu-id="ba926-209">Total number of failed sessions where the specified diagnostic ID was generated.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-modalities"></a><span data-ttu-id="ba926-210">Показатели для самых распространенных модальностей</span><span class="sxs-lookup"><span data-stu-id="ba926-210">Metrics for Top Modalities</span></span>

<span data-ttu-id="ba926-211">В следующей таблице содержатся сведения, приведенные в отчете распределения сбоев на основе модальностей сеансов, в которых произошло больше всего ошибок.</span><span class="sxs-lookup"><span data-stu-id="ba926-211">The following table lists the information provided in the Failure Distribution Report based on the session modalities that experienced the most failures.</span></span>

### <a name="metrics-for-top-modalities"></a><span data-ttu-id="ba926-212">Показатели для самых распространенных модальностей</span><span class="sxs-lookup"><span data-stu-id="ba926-212">Metrics for Top Modalities</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ba926-213">Имя</span><span class="sxs-lookup"><span data-stu-id="ba926-213">Name</span></span></th>
<th><span data-ttu-id="ba926-214">Возможность сортировки по этому показателю</span><span class="sxs-lookup"><span data-stu-id="ba926-214">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="ba926-215">Описание</span><span class="sxs-lookup"><span data-stu-id="ba926-215">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ba926-216"><strong>Rank</strong></span><span class="sxs-lookup"><span data-stu-id="ba926-216"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="ba926-217">Нет</span><span class="sxs-lookup"><span data-stu-id="ba926-217">No</span></span></p></td>
<td><p><span data-ttu-id="ba926-218">Относительное ранжирование неудачных сеансов на основе типа сеанса (например, аудио- или видеоконференция или одноранговый сеанс передачи файлов).</span><span class="sxs-lookup"><span data-stu-id="ba926-218">Relative ranking based of failed session based on session type (for example, an audio/video conference or a peer-to-peer file transfer session).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba926-219"><strong>Самые распространенные модальности</strong></span><span class="sxs-lookup"><span data-stu-id="ba926-219"><strong>Top modalities</strong></span></span></p></td>
<td><p><span data-ttu-id="ba926-220">Нет</span><span class="sxs-lookup"><span data-stu-id="ba926-220">No</span></span></p></td>
<td><p><span data-ttu-id="ba926-221">Тип сеанса.</span><span class="sxs-lookup"><span data-stu-id="ba926-221">Session type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba926-222"><strong>Сеансы</strong></span><span class="sxs-lookup"><span data-stu-id="ba926-222"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="ba926-223">Нет</span><span class="sxs-lookup"><span data-stu-id="ba926-223">No</span></span></p></td>
<td><p><span data-ttu-id="ba926-224">Общее количество неудачных сеансов с указанной модальностью.</span><span class="sxs-lookup"><span data-stu-id="ba926-224">Total number of failed sessions involving the specified modality.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-pools"></a><span data-ttu-id="ba926-225">Показатели для самых распространенных пулов</span><span class="sxs-lookup"><span data-stu-id="ba926-225">Metrics for Top Pools</span></span>

<span data-ttu-id="ba926-226">В следующей таблице содержатся сведения, приведенные в отчете распределения сбоев на основе пулов, в которых произошло больше всего ошибок.</span><span class="sxs-lookup"><span data-stu-id="ba926-226">The following table lists the information provided in the Failure Distribution Report based on the pools that experienced the most failures.</span></span>

### <a name="metrics-for-top-pools"></a><span data-ttu-id="ba926-227">Показатели для самых распространенных пулов</span><span class="sxs-lookup"><span data-stu-id="ba926-227">Metrics for Top Pools</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ba926-228">Имя</span><span class="sxs-lookup"><span data-stu-id="ba926-228">Name</span></span></th>
<th><span data-ttu-id="ba926-229">Возможность сортировки по этому показателю</span><span class="sxs-lookup"><span data-stu-id="ba926-229">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="ba926-230">Описание</span><span class="sxs-lookup"><span data-stu-id="ba926-230">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ba926-231"><strong>Rank</strong></span><span class="sxs-lookup"><span data-stu-id="ba926-231"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="ba926-232">Нет</span><span class="sxs-lookup"><span data-stu-id="ba926-232">No</span></span></p></td>
<td><p><span data-ttu-id="ba926-233">Относительное ранжирование неудачных сеансов на основе пула регистратора или пограничного сервера, на котором выполнялся сеанс.</span><span class="sxs-lookup"><span data-stu-id="ba926-233">Relative ranking of failed sessions based on the Registrar pool or Edge Server where the session was conducted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba926-234"><strong>Самые распространенные пулы</strong></span><span class="sxs-lookup"><span data-stu-id="ba926-234"><strong>Top pools</strong></span></span></p></td>
<td><p><span data-ttu-id="ba926-235">Нет</span><span class="sxs-lookup"><span data-stu-id="ba926-235">No</span></span></p></td>
<td><p><span data-ttu-id="ba926-236">Имя пула регистратора или пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="ba926-236">Name of the Registrar pool or Edge Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba926-237"><strong>Сеансы</strong></span><span class="sxs-lookup"><span data-stu-id="ba926-237"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="ba926-238">Нет</span><span class="sxs-lookup"><span data-stu-id="ba926-238">No</span></span></p></td>
<td><p><span data-ttu-id="ba926-239">Общее количество неудачных сеансов на пул регистратора или пограничный сервер.</span><span class="sxs-lookup"><span data-stu-id="ba926-239">Total number of failed sessions per Registrar pool or Edge Server.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-sources"></a><span data-ttu-id="ba926-240">Показатели для самых распространенных источников</span><span class="sxs-lookup"><span data-stu-id="ba926-240">Metrics for Top Sources</span></span>

<span data-ttu-id="ba926-241">В следующей таблице содержатся сведения, приведенные в отчете распределения сбоев на основе компьютеров, в которых произошло больше всего ошибок.</span><span class="sxs-lookup"><span data-stu-id="ba926-241">The following table lists the information provided in the Failure Distribution Report based on the computers that experienced the most failures.</span></span>

### <a name="metrics-for-top-sources"></a><span data-ttu-id="ba926-242">Показатели для самых распространенных источников</span><span class="sxs-lookup"><span data-stu-id="ba926-242">Metrics for Top Sources</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ba926-243">Имя</span><span class="sxs-lookup"><span data-stu-id="ba926-243">Name</span></span></th>
<th><span data-ttu-id="ba926-244">Возможность сортировки по этому показателю</span><span class="sxs-lookup"><span data-stu-id="ba926-244">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="ba926-245">Описание</span><span class="sxs-lookup"><span data-stu-id="ba926-245">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ba926-246"><strong>Rank</strong></span><span class="sxs-lookup"><span data-stu-id="ba926-246"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="ba926-247">Нет</span><span class="sxs-lookup"><span data-stu-id="ba926-247">No</span></span></p></td>
<td><p><span data-ttu-id="ba926-248">Относительное ранжирование неудачных сеансов на компьютер.</span><span class="sxs-lookup"><span data-stu-id="ba926-248">Relative ranking failed sessions per computer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba926-249"><strong>Самые распространенные источники</strong></span><span class="sxs-lookup"><span data-stu-id="ba926-249"><strong>Top sources</strong></span></span></p></td>
<td><p><span data-ttu-id="ba926-250">Нет</span><span class="sxs-lookup"><span data-stu-id="ba926-250">No</span></span></p></td>
<td><p><span data-ttu-id="ba926-251">Имя компьютера, используемого в неудачном сеансе.</span><span class="sxs-lookup"><span data-stu-id="ba926-251">Name of the computer involved in the failed session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba926-252"><strong>Сеансы</strong></span><span class="sxs-lookup"><span data-stu-id="ba926-252"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="ba926-253">Нет</span><span class="sxs-lookup"><span data-stu-id="ba926-253">No</span></span></p></td>
<td><p><span data-ttu-id="ba926-254">Общее количество неудачных сеансов на компьютер.</span><span class="sxs-lookup"><span data-stu-id="ba926-254">Total number of failed sessions per computer.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-components"></a><span data-ttu-id="ba926-255">Показатели для самых распространенных компонентов</span><span class="sxs-lookup"><span data-stu-id="ba926-255">Metrics for Top Components</span></span>

<span data-ttu-id="ba926-256">В следующей таблице приведены сведения, приведенные в отчете распределения сбоев на основе компонентов Microsoft Lync Server 2010, которые столкнулись с большинством сбоев.</span><span class="sxs-lookup"><span data-stu-id="ba926-256">The following table lists the information provided in the Failure Distribution Report based on the Microsoft Lync Server 2010 components that experienced the most failures.</span></span>

### <a name="metrics-for-top-components"></a><span data-ttu-id="ba926-257">Показатели для самых распространенных компонентов</span><span class="sxs-lookup"><span data-stu-id="ba926-257">Metrics for Top Components</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ba926-258">Имя</span><span class="sxs-lookup"><span data-stu-id="ba926-258">Name</span></span></th>
<th><span data-ttu-id="ba926-259">Возможность сортировки по этому показателю</span><span class="sxs-lookup"><span data-stu-id="ba926-259">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="ba926-260">Описание</span><span class="sxs-lookup"><span data-stu-id="ba926-260">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ba926-261"><strong>Rank</strong></span><span class="sxs-lookup"><span data-stu-id="ba926-261"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="ba926-262">Нет</span><span class="sxs-lookup"><span data-stu-id="ba926-262">No</span></span></p></td>
<td><p><span data-ttu-id="ba926-263">Относительное ранжирование неудачных сеансов на основе компонента Lync Server 2010 (например, ExumRouting, GroupChat или MediationServer).</span><span class="sxs-lookup"><span data-stu-id="ba926-263">Relative ranking of failed sessions based on Lync Server 2010 component (for example, ExumRouting, GroupChat, or MediationServer).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba926-264"><strong>Самые распространенные компоненты</strong></span><span class="sxs-lookup"><span data-stu-id="ba926-264"><strong>Top components</strong></span></span></p></td>
<td><p><span data-ttu-id="ba926-265">Нет</span><span class="sxs-lookup"><span data-stu-id="ba926-265">No</span></span></p></td>
<td><p><span data-ttu-id="ba926-266">Имя компонента, используемого в неудачном сеансе.</span><span class="sxs-lookup"><span data-stu-id="ba926-266">Name of the component involved in the failed session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba926-267"><strong>Сеансы</strong></span><span class="sxs-lookup"><span data-stu-id="ba926-267"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="ba926-268">Нет</span><span class="sxs-lookup"><span data-stu-id="ba926-268">No</span></span></p></td>
<td><p><span data-ttu-id="ba926-269">Общее количество неудачных сеансов на компонент.</span><span class="sxs-lookup"><span data-stu-id="ba926-269">Total number of failed sessions per component.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-from-users"></a><span data-ttu-id="ba926-270">Показатели для самых распространенных вызывающих пользователей</span><span class="sxs-lookup"><span data-stu-id="ba926-270">Metrics for Top From Users</span></span>

<span data-ttu-id="ba926-271">В следующей таблице представлены сведения, приведенные в отчета распределения сбоев на основе числа пользователей, у которых возникло больше всего ошибок, когда они пытались звонить кому-нибудь еще (которых также называют "вызывающими" пользователями).</span><span class="sxs-lookup"><span data-stu-id="ba926-271">The following table lists the information provided in the Failure Distribution Report based on users who experienced the most failures when they tried to call someone else (known as "From" users).</span></span>

### <a name="metrics-for-top-from-users"></a><span data-ttu-id="ba926-272">Показатели для самых распространенных вызывающих пользователей</span><span class="sxs-lookup"><span data-stu-id="ba926-272">Metrics for Top From Users</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ba926-273">Имя</span><span class="sxs-lookup"><span data-stu-id="ba926-273">Name</span></span></th>
<th><span data-ttu-id="ba926-274">Возможность сортировки по этому показателю</span><span class="sxs-lookup"><span data-stu-id="ba926-274">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="ba926-275">Описание</span><span class="sxs-lookup"><span data-stu-id="ba926-275">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ba926-276"><strong>Rank</strong></span><span class="sxs-lookup"><span data-stu-id="ba926-276"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="ba926-277">Нет</span><span class="sxs-lookup"><span data-stu-id="ba926-277">No</span></span></p></td>
<td><p><span data-ttu-id="ba926-278">Относительно ранжирование неудачных сеансов на основе пользователя, который был приглашен для присоединения к сеансу.</span><span class="sxs-lookup"><span data-stu-id="ba926-278">Relative ranking of failed sessions based on the user who was invited to join the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba926-279"><strong>Самые распространенные вызывающие пользователи</strong></span><span class="sxs-lookup"><span data-stu-id="ba926-279"><strong>Top from users</strong></span></span></p></td>
<td><p><span data-ttu-id="ba926-280">Нет</span><span class="sxs-lookup"><span data-stu-id="ba926-280">No</span></span></p></td>
<td><p><span data-ttu-id="ba926-281">SIP-адрес пользователя, приглашенного в сеанс.</span><span class="sxs-lookup"><span data-stu-id="ba926-281">SIP address of the user invited to join the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba926-282"><strong>Сеансы</strong></span><span class="sxs-lookup"><span data-stu-id="ba926-282"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="ba926-283">Нет</span><span class="sxs-lookup"><span data-stu-id="ba926-283">No</span></span></p></td>
<td><p><span data-ttu-id="ba926-284">Общее количество неудачных сеансов на пользователя.</span><span class="sxs-lookup"><span data-stu-id="ba926-284">Total number of failed sessions per user.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-to-users"></a><span data-ttu-id="ba926-285">Показатели для самых распространенных вызываемых пользователей</span><span class="sxs-lookup"><span data-stu-id="ba926-285">Metrics for Top To Users</span></span>

<span data-ttu-id="ba926-286">В следующей таблице представлены сведения, приведенные в отчета распределения сбоев на основе пользователей, у которых возникло больше всего ошибок, когда кто-то другой пытался позвонить им (их также называют "вызываемыми" пользователями).</span><span class="sxs-lookup"><span data-stu-id="ba926-286">The following table lists the information provided in the Failure Distribution Report based on the users who experienced the most failures when another user tried to call them (known as "To" users).</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ba926-287">Имя</span><span class="sxs-lookup"><span data-stu-id="ba926-287">Name</span></span></th>
<th><span data-ttu-id="ba926-288">Возможность сортировки по этому показателю</span><span class="sxs-lookup"><span data-stu-id="ba926-288">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="ba926-289">Описание</span><span class="sxs-lookup"><span data-stu-id="ba926-289">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ba926-290"><strong>Rank</strong></span><span class="sxs-lookup"><span data-stu-id="ba926-290"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="ba926-291">Нет</span><span class="sxs-lookup"><span data-stu-id="ba926-291">No</span></span></p></td>
<td><p><span data-ttu-id="ba926-292">Относительно ранжирование неудачных сеансов на основе пользователя, инициировавшего сеанс.</span><span class="sxs-lookup"><span data-stu-id="ba926-292">Relative ranking of failed sessions based on the user who initiated the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba926-293"><strong>Самые распространенные вызываемые пользователи</strong></span><span class="sxs-lookup"><span data-stu-id="ba926-293"><strong>Top to users</strong></span></span></p></td>
<td><p><span data-ttu-id="ba926-294">Нет</span><span class="sxs-lookup"><span data-stu-id="ba926-294">No</span></span></p></td>
<td><p><span data-ttu-id="ba926-295">SIP-адрес пользователя, который инициировал сеанс.</span><span class="sxs-lookup"><span data-stu-id="ba926-295">SIP address of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba926-296"><strong>Сеансы</strong></span><span class="sxs-lookup"><span data-stu-id="ba926-296"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="ba926-297">Нет</span><span class="sxs-lookup"><span data-stu-id="ba926-297">No</span></span></p></td>
<td><p><span data-ttu-id="ba926-298">Общее количество неудачных сеансов на пользователя.</span><span class="sxs-lookup"><span data-stu-id="ba926-298">Total number of failed sessions per user.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-user-agents"></a><span data-ttu-id="ba926-299">Показатели для самых распространенных агентов пользователей</span><span class="sxs-lookup"><span data-stu-id="ba926-299">Metrics for Top User Agents</span></span>

<span data-ttu-id="ba926-300">В следующей таблице содержатся сведения, приведенные в отчете распределения сбоев на основе программного обеспечения конечных точек, в которых произошло больше всего ошибок.</span><span class="sxs-lookup"><span data-stu-id="ba926-300">The following table lists the information provided in the Failure Distribution Report based on the endpoint software that experienced the most failures.</span></span>

### <a name="metrics-for-top-user-agents"></a><span data-ttu-id="ba926-301">Показатели для самых распространенных агентов пользователей</span><span class="sxs-lookup"><span data-stu-id="ba926-301">Metrics for Top User Agents</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ba926-302">Имя</span><span class="sxs-lookup"><span data-stu-id="ba926-302">Name</span></span></th>
<th><span data-ttu-id="ba926-303">Возможность сортировки по этому показателю</span><span class="sxs-lookup"><span data-stu-id="ba926-303">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="ba926-304">Описание</span><span class="sxs-lookup"><span data-stu-id="ba926-304">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ba926-305"><strong>Rank</strong></span><span class="sxs-lookup"><span data-stu-id="ba926-305"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="ba926-306">Нет</span><span class="sxs-lookup"><span data-stu-id="ba926-306">No</span></span></p></td>
<td><p><span data-ttu-id="ba926-p115">Относительное ранжирование неудачных сеансов на основе агента пользователя (программного обеспечения), применяемого в сеансе. Например: RTCC/4.0.0.0 Входящее перенаправление/4.0.0.0.</span><span class="sxs-lookup"><span data-stu-id="ba926-p115">Relative ranking of failed sessions based on the user agent (software) involved in the session. For example: RTCC/4.0.0.0 Inbound Routing/4.0.0.0.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba926-309"><strong>Самые распространенные агенты пользователей</strong></span><span class="sxs-lookup"><span data-stu-id="ba926-309"><strong>Top user agents</strong></span></span></p></td>
<td><p><span data-ttu-id="ba926-310">Нет</span><span class="sxs-lookup"><span data-stu-id="ba926-310">No</span></span></p></td>
<td><p><span data-ttu-id="ba926-311">Имя агента пользователя, применяемого в неудачном сеансе.</span><span class="sxs-lookup"><span data-stu-id="ba926-311">Name of the user agent involved in the failed session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba926-312"><strong>Сеансы</strong></span><span class="sxs-lookup"><span data-stu-id="ba926-312"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="ba926-313">Нет</span><span class="sxs-lookup"><span data-stu-id="ba926-313">No</span></span></p></td>
<td><p><span data-ttu-id="ba926-314">Общее количество неудачных сеансов на агента пользователя.</span><span class="sxs-lookup"><span data-stu-id="ba926-314">Total number of failed sessions per user agent.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

