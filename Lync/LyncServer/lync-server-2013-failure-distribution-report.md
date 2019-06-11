---
title: 'Lync Server 2013: отчет о распределении сбоев'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Failure Distribution Report
ms:assetid: 365c7beb-24d4-40f5-92e7-4978b9688916
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558635(v=OCS.15)
ms:contentKeyID: 48183849
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 06481be824f6c51975431aeea2efe27e41eadabc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834175"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failure-distribution-report-in-lync-server-2013"></a><span data-ttu-id="654f0-102">Отчет о распределении отказов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="654f0-102">Failure Distribution Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="654f0-103">_**Тема последнего изменения:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="654f0-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="654f0-104">В отчете о распределении сбоев неудачные сеансы оцениваются в следующих категориях:</span><span class="sxs-lookup"><span data-stu-id="654f0-104">The Failure Distribution Report ranks failed sessions in the following categories:</span></span>

  - <span data-ttu-id="654f0-105">Самые распространенные причины диагностики</span><span class="sxs-lookup"><span data-stu-id="654f0-105">Top diagnostic reasons</span></span>

  - <span data-ttu-id="654f0-106">Самые распространенные модальности</span><span class="sxs-lookup"><span data-stu-id="654f0-106">Top modalities</span></span>

  - <span data-ttu-id="654f0-107">Самые распространенные пулы</span><span class="sxs-lookup"><span data-stu-id="654f0-107">Top pools</span></span>

  - <span data-ttu-id="654f0-108">Самые распространенные источники</span><span class="sxs-lookup"><span data-stu-id="654f0-108">Top sources</span></span>

  - <span data-ttu-id="654f0-109">Самые распространенные компоненты</span><span class="sxs-lookup"><span data-stu-id="654f0-109">Top components</span></span>

  - <span data-ttu-id="654f0-110">Самые распространенные вызывающие пользователи</span><span class="sxs-lookup"><span data-stu-id="654f0-110">Top from users</span></span>

  - <span data-ttu-id="654f0-111">Самые распространенные вызываемые пользователи</span><span class="sxs-lookup"><span data-stu-id="654f0-111">Top to users</span></span>

  - <span data-ttu-id="654f0-112">самые распространенные вызывающие агенты пользователей.</span><span class="sxs-lookup"><span data-stu-id="654f0-112">Top from user agents</span></span>

<span data-ttu-id="654f0-p101">С помощью этих категорий вы можете точно определить, где именно возникла проблема (а в некоторых случаях и причину ее возникновения). Предположим, что вы записали 242 аудио- или видеосеанса с ошибками за день. В отчете о распределении сбоев может быть показано, что 237 неудачных сеансов состоялись в пуле Дублин. Это дает вам хорошую отправную точку для отслеживания и диагностики причин этих сбоев. Если выбрать пул Дублин в категории **Основные пулы**, вы увидите отчет о распределении сбоев только для этого пула. Затем вы можете начать анализировать, почему в пуле Дублин было так много проблем.</span><span class="sxs-lookup"><span data-stu-id="654f0-p101">You can use these categories to determine exactly where a problem is occurring and, in some cases, why the problem is occurring. For example, suppose you recorded 242 failed audio/video sessions during a given day. If you look at the Failure Distribution Report, it might show that 237 of those failed sessions took place in your Dublin pool. That gives you a good place to start when it comes to tracking down and diagnosing the causes behind those failures. If you click on the Dublin pool under the **Top pools** category, you will see a Failure Distribution Report just for that pool. You can then begin analyzing why the Dublin pool was experiencing so many difficulties.</span></span>

<div>

## <a name="viewing-the-failure-distribution-report"></a><span data-ttu-id="654f0-119">Просмотр отчета о распределении сбоев</span><span class="sxs-lookup"><span data-stu-id="654f0-119">Viewing the Failure Distribution Report</span></span>

<span data-ttu-id="654f0-120">Обратиться к отчету о распределении сбоев можно из любого из следующих отчетов, щелкнув показатель **Том ожидаемого сбоя** или **Том неожиданного сбоя**:</span><span class="sxs-lookup"><span data-stu-id="654f0-120">You can access the Failure Distribution Report from any of the following reports by clicking either the **Expected failure volume** or the **Unexpected failure volume** metric:</span></span>

  - [<span data-ttu-id="654f0-121">Отчет об ошибках верхнего уровня в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="654f0-121">Top Failures Report in Lync Server 2013</span></span>](lync-server-2013-top-failures-report.md)

  - [<span data-ttu-id="654f0-122">Диагностический отчет на Конференции в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="654f0-122">Conference Diagnostic Report in Lync Server 2013</span></span>](lync-server-2013-conference-diagnostic-report.md)

  - [<span data-ttu-id="654f0-123">Диагностический отчет о действиях одноранговой сети в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="654f0-123">Peer-to-Peer Activity Diagnostic Report in Lync Server 2013</span></span>](lync-server-2013-peer-to-peer-activity-diagnostic-report.md)

<span data-ttu-id="654f0-124">В отчете распределение сбоев можно выбрать любую из указанных ниже метрик, чтобы просмотреть [отчет о списке отказов в Lync Server 2013](lync-server-2013-failure-list-report.md):</span><span class="sxs-lookup"><span data-stu-id="654f0-124">From the Failure Distribution Report, you can click any of the following metrics to view the [Failure List Report in Lync Server 2013](lync-server-2013-failure-list-report.md):</span></span>

  - <span data-ttu-id="654f0-125">Top diagnostic reasons (sessions) (Основные причины диагностики (сеансы))</span><span class="sxs-lookup"><span data-stu-id="654f0-125">Top diagnostic reasons (sessions)</span></span>

  - <span data-ttu-id="654f0-126">Top modalities (sessions) (Основные условия (сеансы))</span><span class="sxs-lookup"><span data-stu-id="654f0-126">Top modalities (sessions)</span></span>

  - <span data-ttu-id="654f0-127">Top pools (sessions) (Основные пулы (сеансы))</span><span class="sxs-lookup"><span data-stu-id="654f0-127">Top pools (sessions)</span></span>

  - <span data-ttu-id="654f0-128">Top sources (sessions) (Основные источники (сеансы))</span><span class="sxs-lookup"><span data-stu-id="654f0-128">Top sources (sessions)</span></span>

  - <span data-ttu-id="654f0-129">Top components (sessions) (Основные компоненты (сеансы))</span><span class="sxs-lookup"><span data-stu-id="654f0-129">Top components (sessions)</span></span>

  - <span data-ttu-id="654f0-130">Top from users (sessions) (Основные пользователи с ошибками исходящей связи (сеансы))</span><span class="sxs-lookup"><span data-stu-id="654f0-130">Top from users (sessions)</span></span>

  - <span data-ttu-id="654f0-131">Top to users (sessions) (Основные пользователи с ошибками входящей связи (сеансы))</span><span class="sxs-lookup"><span data-stu-id="654f0-131">Top to users (sessions)</span></span>

  - <span data-ttu-id="654f0-132">Top from user agents (sessions) (Основные агенты пользователей, используемые в сеансах, завершившихся с ошибками (сеансы))</span><span class="sxs-lookup"><span data-stu-id="654f0-132">Top from user agents (sessions)</span></span>

</div>

<div>

## <a name="using-the-failure-distribution-report"></a><span data-ttu-id="654f0-133">Использование отчета о распределении сбоев</span><span class="sxs-lookup"><span data-stu-id="654f0-133">Using the Failure Distribution Report</span></span>

<span data-ttu-id="654f0-p102">В зависимости от размера и разрешения экрана некоторые данные в отчете о распределении сбоев при просмотре на экране могут усекаться. Это особенно актуально для таких показателей, как агенты пользователя, у которых могут быть очень длинные метки. Например, агент пользователя с именем UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Lync 2013) может только частично появится на экране:</span><span class="sxs-lookup"><span data-stu-id="654f0-p102">Depending on your monitor size and screen resolution, it's possible that some of the data shown in the Failure Distribution Report might be truncated when you view it onscreen. This is especially true for metrics such as user agents, which can have very long labels. For example, a user agent with a name like "UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Lync 2013)" might only partially appear onscreen:</span></span>

<span data-ttu-id="654f0-137">UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Ly...</span><span class="sxs-lookup"><span data-stu-id="654f0-137">UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Ly...</span></span>

<span data-ttu-id="654f0-138">К счастью, всю метку можно увидеть, просто удерживая указатель мыши над усеченным значением.</span><span class="sxs-lookup"><span data-stu-id="654f0-138">Fortunately, you can see the entire label simply by holding your mouse over the truncated value.</span></span>

<span data-ttu-id="654f0-p103">Один из интересных показателей, который можно использовать для фильтрации с помощью отчета распределения сбоев – это код диагностики. Если вы видите один и тот же код в других отчетах, можно отфильтровать отчет по этому коду и получить очень подробные сведения о том, где именно и как часто этот код появлялся в ошибочном сеансе.</span><span class="sxs-lookup"><span data-stu-id="654f0-p103">One interesting metric that you can filter on by using the Failure Distribution Report is Diagnostic ID. If you see the same Diagnostic ID cropping up in other reports you can filter on that ID in the Failure Distribution Report and get a very detailed look at exactly where, and how often, that ID has been reported during a failed session.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="654f0-141">Фильтры</span><span class="sxs-lookup"><span data-stu-id="654f0-141">Filters</span></span>

<span data-ttu-id="654f0-p104">Фильтры позволяют получать более точный набор данных или просматривать данные различными способами. Например, отчет распределения сбоев позволяет фильтровать данные по таким элементам, как тип деятельности (одноранговый сеанс или сеанс конференц-связи) или код диагностики, связанный с каждым ошибочным сеансом.</span><span class="sxs-lookup"><span data-stu-id="654f0-p104">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Failed Distribution Report enables you to filter on such things as the activity type (peer-to-peer session or conferencing session) or by the diagnostic ID that accompanied each failed session.</span></span>

<span data-ttu-id="654f0-144">В следующей таблице приведены фильтры, которые можно использовать с отчетом распределения сбоев.</span><span class="sxs-lookup"><span data-stu-id="654f0-144">The following table lists the filters that you can use with the Failure Distribution Report.</span></span>

### <a name="failure-distribution-report-filters"></a><span data-ttu-id="654f0-145">Фильтры отчета распределения сбоев</span><span class="sxs-lookup"><span data-stu-id="654f0-145">Failure Distribution Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="654f0-146">Имя</span><span class="sxs-lookup"><span data-stu-id="654f0-146">Name</span></span></th>
<th><span data-ttu-id="654f0-147">Описание</span><span class="sxs-lookup"><span data-stu-id="654f0-147">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="654f0-148"><strong>От</strong></span><span class="sxs-lookup"><span data-stu-id="654f0-148"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="654f0-p105">Начальные дата/время для временного диапазона. Чтобы просмотреть данные по часам, введите начальные дату и время следующим образом:</span><span class="sxs-lookup"><span data-stu-id="654f0-p105">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="654f0-151">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="654f0-151">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="654f0-p106">Если вы не вводите начальное время, отчет автоматически начинается с 12:00 AM указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</span><span class="sxs-lookup"><span data-stu-id="654f0-p106">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="654f0-154">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="654f0-154">7/7/2012</span></span></p>
<p><span data-ttu-id="654f0-155">Чтобы просмотреть данные за неделю или месяц, введите дату, выпадающую на любое время в рамках недели или месяца, которые вы хотите просмотреть (вам не требуется вводить первый день недели или месяца):</span><span class="sxs-lookup"><span data-stu-id="654f0-155">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="654f0-156">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="654f0-156">7/3/2012</span></span></p>
<p><span data-ttu-id="654f0-157">Недели всегда отсчитываются с воскресенья по субботу.</span><span class="sxs-lookup"><span data-stu-id="654f0-157">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="654f0-158"><strong>До</strong></span><span class="sxs-lookup"><span data-stu-id="654f0-158"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="654f0-p107">Конечные дата/время для временного диапазона. Чтобы просмотреть данные по часам, введите конечные дату и время следующим образом:</span><span class="sxs-lookup"><span data-stu-id="654f0-p107">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="654f0-161">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="654f0-161">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="654f0-p108">Если вы не вводите конечное время, отчет автоматически заканчивается в 12:00 AM указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</span><span class="sxs-lookup"><span data-stu-id="654f0-p108">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="654f0-164">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="654f0-164">7/7/2012</span></span></p>
<p><span data-ttu-id="654f0-165">Чтобы просмотреть данные за неделю или месяц, введите дату, выпадающую на любое время в рамках недели или месяца, которые вы хотите просмотреть (вам не требуется вводить первый день недели или месяца):</span><span class="sxs-lookup"><span data-stu-id="654f0-165">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="654f0-166">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="654f0-166">7/3/2012</span></span></p>
<p><span data-ttu-id="654f0-167">Недели всегда отсчитываются с воскресенья по субботу.</span><span class="sxs-lookup"><span data-stu-id="654f0-167">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="654f0-168"><strong>Пул</strong></span><span class="sxs-lookup"><span data-stu-id="654f0-168"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="654f0-p109">Полное доменное имя пула регистратора или пограничного сервера. Можно выбрать отдельный пул или нажать <strong>[Все]</strong>, чтобы просмотреть данные для всех пулов. Этот раскрывающийся список автоматически заполняется на основе записей в базе данных.</span><span class="sxs-lookup"><span data-stu-id="654f0-p109">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="654f0-172"><strong>Тип сеанса</strong></span><span class="sxs-lookup"><span data-stu-id="654f0-172"><strong>Activity type</strong></span></span></p></td>
<td><p><span data-ttu-id="654f0-p110">Тип деятельности, к которому требуется применить фильтр. Выберите один из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="654f0-p110">Type of activity to filter on. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="654f0-175">[All] (Все)</span><span class="sxs-lookup"><span data-stu-id="654f0-175">[All]</span></span></p></li>
<li><p><span data-ttu-id="654f0-176">Одноранговая</span><span class="sxs-lookup"><span data-stu-id="654f0-176">Peer-to-peer</span></span></p></li>
<li><p><span data-ttu-id="654f0-177">Конференция</span><span class="sxs-lookup"><span data-stu-id="654f0-177">Conference</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="654f0-178"><strong>Session category (Категория сеанса)</strong></span><span class="sxs-lookup"><span data-stu-id="654f0-178"><strong>Session category</strong></span></span></p></td>
<td><p><span data-ttu-id="654f0-p111">Указывает, была ли рассматриваемая активность успешна. Выберите одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="654f0-p111">Indicates whether the activity in question succeeded or failed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="654f0-181">[All] (Все)</span><span class="sxs-lookup"><span data-stu-id="654f0-181">[All]</span></span></p></li>
<li><p><span data-ttu-id="654f0-182">Success (Успешно)</span><span class="sxs-lookup"><span data-stu-id="654f0-182">Success</span></span></p></li>
<li><p><span data-ttu-id="654f0-183">Expected failure (Ожидаемый сбой)</span><span class="sxs-lookup"><span data-stu-id="654f0-183">Expected failure</span></span></p></li>
<li><p><span data-ttu-id="654f0-184">Unexpected failure (Неожиданный сбой)</span><span class="sxs-lookup"><span data-stu-id="654f0-184">Unexpected failure</span></span></p></li>
</ul>
<p><span data-ttu-id="654f0-185">&quot;Ожидаемый сбой&quot; — это сбой, который должен выполняться.</span><span class="sxs-lookup"><span data-stu-id="654f0-185">An &quot;expected failure&quot; is a failure that is expected to happen.</span></span> <span data-ttu-id="654f0-186">Например, если пользователь установил статус «Не беспокоить», то ожидаемое, что все вызовы этого пользователя завершатся неудачно.</span><span class="sxs-lookup"><span data-stu-id="654f0-186">For example, if a user has set his or her status to Do Not Disturb you would expect any call to that user to fail.</span></span> <span data-ttu-id="654f0-187">Произошла &quot;непредвиденная ошибка&quot; , возникающая в том, что может выглядеть как подсистема, которая в противном случае является работоспособной.</span><span class="sxs-lookup"><span data-stu-id="654f0-187">An &quot;unexpected failure&quot; is a failure that occurs in what would appear to be an otherwise healthy system.</span></span> <span data-ttu-id="654f0-188">Например, вызов не должен прерываться, если вызывающий абонент помещается на удержание.</span><span class="sxs-lookup"><span data-stu-id="654f0-188">For example, a call should not be terminated if the caller is placed on hold.</span></span> <span data-ttu-id="654f0-189">В этом случае это считается непредвиденным сбоем.</span><span class="sxs-lookup"><span data-stu-id="654f0-189">If that occurs, that would be flagged as an unexpected failure.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="654f0-190"><strong>Diagnostic ID (ИД диагностики)</strong></span><span class="sxs-lookup"><span data-stu-id="654f0-190"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="654f0-p113">Прикрепленный к SIP-сообщению уникальный идентификатор (в форме заголовка ms-diagnostics), который часто содержит информацию, полезную при поиске и устранении ошибок. Заголовки диагностики не являются обязательными (можно иметь сеансы SIP без таких заголовков), а идентификаторы диагностики указываются только для сеансов, в которых возникли какие-либо проблемы.</span><span class="sxs-lookup"><span data-stu-id="654f0-p113">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-diagnostic-reasons"></a><span data-ttu-id="654f0-193">Показатели для самых распространенных причин диагностики</span><span class="sxs-lookup"><span data-stu-id="654f0-193">Metrics for Top Diagnostic Reasons</span></span>

<span data-ttu-id="654f0-194">В следующей таблице представлены сведения, приведенные в отчете распределения сбоев на основе самых распространенных кодов диагностики.</span><span class="sxs-lookup"><span data-stu-id="654f0-194">The following table lists the information provided in the Failure Distribution Report based on the most frequently reported diagnostic ID.</span></span>

### <a name="metrics-for-top-diagnostic-reasons"></a><span data-ttu-id="654f0-195">Показатели для самых распространенных причин диагностики</span><span class="sxs-lookup"><span data-stu-id="654f0-195">Metrics for Top Diagnostic Reasons</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="654f0-196">Имя</span><span class="sxs-lookup"><span data-stu-id="654f0-196">Name</span></span></th>
<th><span data-ttu-id="654f0-197">Поддержка сортировки</span><span class="sxs-lookup"><span data-stu-id="654f0-197">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="654f0-198">Описание</span><span class="sxs-lookup"><span data-stu-id="654f0-198">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="654f0-199"><strong>Rank (Ранг)</strong></span><span class="sxs-lookup"><span data-stu-id="654f0-199"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="654f0-200">Нет</span><span class="sxs-lookup"><span data-stu-id="654f0-200">No</span></span></p></td>
<td><p><span data-ttu-id="654f0-p114">Относительное ранжирование неудачных сеансов на основе кодов диагностики. Код диагностики – это уникальный идентификатор (в виде заголовка ms-diagnostics), прикрепленный к сообщению SIP, которое часто содержит полезные сведения для устранения ошибок.</span><span class="sxs-lookup"><span data-stu-id="654f0-p114">Relative ranking of failed sessions based on diagnostic IDs. The diagnostic ID is a unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="654f0-203"><strong>Самые распространенные причины диагностики</strong></span><span class="sxs-lookup"><span data-stu-id="654f0-203"><strong>Top diagnostic reasons</strong></span></span></p></td>
<td><p><span data-ttu-id="654f0-204">Нет</span><span class="sxs-lookup"><span data-stu-id="654f0-204">No</span></span></p></td>
<td><p><span data-ttu-id="654f0-205">Код, созданный во время сеанса.</span><span class="sxs-lookup"><span data-stu-id="654f0-205">Diagnostic ID generated in a session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="654f0-206"><strong>Сеансы</strong></span><span class="sxs-lookup"><span data-stu-id="654f0-206"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="654f0-207">Нет</span><span class="sxs-lookup"><span data-stu-id="654f0-207">No</span></span></p></td>
<td><p><span data-ttu-id="654f0-208">Общее количество неудачных сеансов, в которых был создан указанный код диагностики.</span><span class="sxs-lookup"><span data-stu-id="654f0-208">Total number of failed sessions where the specified diagnostic ID was generated.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-modalities"></a><span data-ttu-id="654f0-209">Показатели для самых распространенных модальностей</span><span class="sxs-lookup"><span data-stu-id="654f0-209">Metrics for Top Modalities</span></span>

<span data-ttu-id="654f0-210">В следующей таблице содержатся сведения, приведенные в отчете распределения сбоев на основе модальностей сеансов, в которых произошло больше всего ошибок.</span><span class="sxs-lookup"><span data-stu-id="654f0-210">The following table lists the information provided in the Failure Distribution Report based on the session modalities that experienced the most failures.</span></span>

### <a name="metrics-for-top-modalities"></a><span data-ttu-id="654f0-211">Показатели для самых распространенных модальностей</span><span class="sxs-lookup"><span data-stu-id="654f0-211">Metrics for Top Modalities</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="654f0-212">Имя</span><span class="sxs-lookup"><span data-stu-id="654f0-212">Name</span></span></th>
<th><span data-ttu-id="654f0-213">Поддержка сортировки</span><span class="sxs-lookup"><span data-stu-id="654f0-213">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="654f0-214">Описание</span><span class="sxs-lookup"><span data-stu-id="654f0-214">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="654f0-215"><strong>Rank (Ранг)</strong></span><span class="sxs-lookup"><span data-stu-id="654f0-215"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="654f0-216">Нет</span><span class="sxs-lookup"><span data-stu-id="654f0-216">No</span></span></p></td>
<td><p><span data-ttu-id="654f0-217">Относительное ранжирование неудачных сеансов на основе типа сеанса (например, аудио- или видеоконференция или одноранговый сеанс передачи файлов).</span><span class="sxs-lookup"><span data-stu-id="654f0-217">Relative ranking based of failed session based on session type (for example, an audio/video conference or a peer-to-peer file transfer session).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="654f0-218"><strong>Самые распространенные модальности</strong></span><span class="sxs-lookup"><span data-stu-id="654f0-218"><strong>Top modalities</strong></span></span></p></td>
<td><p><span data-ttu-id="654f0-219">Нет</span><span class="sxs-lookup"><span data-stu-id="654f0-219">No</span></span></p></td>
<td><p><span data-ttu-id="654f0-220">Тип сеанса.</span><span class="sxs-lookup"><span data-stu-id="654f0-220">Session type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="654f0-221"><strong>Сеансы</strong></span><span class="sxs-lookup"><span data-stu-id="654f0-221"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="654f0-222">Нет</span><span class="sxs-lookup"><span data-stu-id="654f0-222">No</span></span></p></td>
<td><p><span data-ttu-id="654f0-223">Общее количество неудачных сеансов с указанной модальностью.</span><span class="sxs-lookup"><span data-stu-id="654f0-223">Total number of failed sessions involving the specified modality.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-pools"></a><span data-ttu-id="654f0-224">Показатели для самых распространенных пулов</span><span class="sxs-lookup"><span data-stu-id="654f0-224">Metrics for Top Pools</span></span>

<span data-ttu-id="654f0-225">В следующей таблице содержатся сведения, приведенные в отчете распределения сбоев на основе пулов, в которых произошло больше всего ошибок.</span><span class="sxs-lookup"><span data-stu-id="654f0-225">The following table lists the information provided in the Failure Distribution Report based on the pools that experienced the most failures.</span></span>

### <a name="metrics-for-top-pools"></a><span data-ttu-id="654f0-226">Показатели для самых распространенных пулов</span><span class="sxs-lookup"><span data-stu-id="654f0-226">Metrics for Top Pools</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="654f0-227">Имя</span><span class="sxs-lookup"><span data-stu-id="654f0-227">Name</span></span></th>
<th><span data-ttu-id="654f0-228">Поддержка сортировки</span><span class="sxs-lookup"><span data-stu-id="654f0-228">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="654f0-229">Описание</span><span class="sxs-lookup"><span data-stu-id="654f0-229">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="654f0-230"><strong>Rank (Ранг)</strong></span><span class="sxs-lookup"><span data-stu-id="654f0-230"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="654f0-231">Нет</span><span class="sxs-lookup"><span data-stu-id="654f0-231">No</span></span></p></td>
<td><p><span data-ttu-id="654f0-232">Относительная ранжирование неудачных сеансов на основе регистратора или пограничного сервера, на котором выполнялся сеанс.</span><span class="sxs-lookup"><span data-stu-id="654f0-232">Relative ranking of failed sessions based on the Registrar pool or Edge Server where the session was conducted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="654f0-233"><strong>Самые распространенные пулы</strong></span><span class="sxs-lookup"><span data-stu-id="654f0-233"><strong>Top pools</strong></span></span></p></td>
<td><p><span data-ttu-id="654f0-234">Нет</span><span class="sxs-lookup"><span data-stu-id="654f0-234">No</span></span></p></td>
<td><p><span data-ttu-id="654f0-235">Имя пула регистраторов или пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="654f0-235">Name of the Registrar pool or Edge Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="654f0-236"><strong>Сеансы</strong></span><span class="sxs-lookup"><span data-stu-id="654f0-236"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="654f0-237">Нет</span><span class="sxs-lookup"><span data-stu-id="654f0-237">No</span></span></p></td>
<td><p><span data-ttu-id="654f0-238">Общее количество неудачных сеансов на каждом из групп регистраторов или пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="654f0-238">Total number of failed sessions per Registrar pool or Edge Server.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-sources"></a><span data-ttu-id="654f0-239">Показатели для самых распространенных источников</span><span class="sxs-lookup"><span data-stu-id="654f0-239">Metrics for Top Sources</span></span>

<span data-ttu-id="654f0-240">В следующей таблице содержатся сведения, приведенные в отчете распределения сбоев на основе компьютеров, в которых произошло больше всего ошибок.</span><span class="sxs-lookup"><span data-stu-id="654f0-240">The following table lists the information provided in the Failure Distribution Report based on the computers that experienced the most failures.</span></span>

### <a name="metrics-for-top-sources"></a><span data-ttu-id="654f0-241">Показатели для самых распространенных источников</span><span class="sxs-lookup"><span data-stu-id="654f0-241">Metrics for Top Sources</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="654f0-242">Имя</span><span class="sxs-lookup"><span data-stu-id="654f0-242">Name</span></span></th>
<th><span data-ttu-id="654f0-243">Поддержка сортировки</span><span class="sxs-lookup"><span data-stu-id="654f0-243">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="654f0-244">Описание</span><span class="sxs-lookup"><span data-stu-id="654f0-244">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="654f0-245"><strong>Rank (Ранг)</strong></span><span class="sxs-lookup"><span data-stu-id="654f0-245"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="654f0-246">Нет</span><span class="sxs-lookup"><span data-stu-id="654f0-246">No</span></span></p></td>
<td><p><span data-ttu-id="654f0-247">Относительное ранжирование неудачных сеансов на компьютер.</span><span class="sxs-lookup"><span data-stu-id="654f0-247">Relative ranking failed sessions per computer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="654f0-248"><strong>Самые распространенные источники</strong></span><span class="sxs-lookup"><span data-stu-id="654f0-248"><strong>Top sources</strong></span></span></p></td>
<td><p><span data-ttu-id="654f0-249">Нет</span><span class="sxs-lookup"><span data-stu-id="654f0-249">No</span></span></p></td>
<td><p><span data-ttu-id="654f0-250">Имя компьютера, используемого в неудачном сеансе.</span><span class="sxs-lookup"><span data-stu-id="654f0-250">Name of the computer involved in the failed session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="654f0-251"><strong>Сеансы</strong></span><span class="sxs-lookup"><span data-stu-id="654f0-251"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="654f0-252">Нет</span><span class="sxs-lookup"><span data-stu-id="654f0-252">No</span></span></p></td>
<td><p><span data-ttu-id="654f0-253">Общее количество неудачных сеансов на компьютер.</span><span class="sxs-lookup"><span data-stu-id="654f0-253">Total number of failed sessions per computer.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-components"></a><span data-ttu-id="654f0-254">Показатели для самых распространенных компонентов</span><span class="sxs-lookup"><span data-stu-id="654f0-254">Metrics for Top Components</span></span>

<span data-ttu-id="654f0-255">В таблице ниже приведены сведения, которые содержатся в отчете о распределении неисправностей, основанном на компонентах Microsoft Lync Server 2010, в которых произошел сбой.</span><span class="sxs-lookup"><span data-stu-id="654f0-255">The following table lists the information provided in the Failure Distribution Report based on the Microsoft Lync Server 2010 components that experienced the most failures.</span></span>

### <a name="metrics-for-top-components"></a><span data-ttu-id="654f0-256">Показатели для самых распространенных компонентов</span><span class="sxs-lookup"><span data-stu-id="654f0-256">Metrics for Top Components</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="654f0-257">Имя</span><span class="sxs-lookup"><span data-stu-id="654f0-257">Name</span></span></th>
<th><span data-ttu-id="654f0-258">Поддержка сортировки</span><span class="sxs-lookup"><span data-stu-id="654f0-258">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="654f0-259">Описание</span><span class="sxs-lookup"><span data-stu-id="654f0-259">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="654f0-260"><strong>Rank (Ранг)</strong></span><span class="sxs-lookup"><span data-stu-id="654f0-260"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="654f0-261">Нет</span><span class="sxs-lookup"><span data-stu-id="654f0-261">No</span></span></p></td>
<td><p><span data-ttu-id="654f0-262">Относительная ранжирование неудачных сеансов на основе компонента Lync Server 2010 (например, Ексумраутинг, Граупчат или Медиатионсервер).</span><span class="sxs-lookup"><span data-stu-id="654f0-262">Relative ranking of failed sessions based on Lync Server 2010 component (for example, ExumRouting, GroupChat, or MediationServer).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="654f0-263"><strong>Самые распространенные компоненты</strong></span><span class="sxs-lookup"><span data-stu-id="654f0-263"><strong>Top components</strong></span></span></p></td>
<td><p><span data-ttu-id="654f0-264">Нет</span><span class="sxs-lookup"><span data-stu-id="654f0-264">No</span></span></p></td>
<td><p><span data-ttu-id="654f0-265">Имя компонента, используемого в неудачном сеансе.</span><span class="sxs-lookup"><span data-stu-id="654f0-265">Name of the component involved in the failed session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="654f0-266"><strong>Сеансы</strong></span><span class="sxs-lookup"><span data-stu-id="654f0-266"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="654f0-267">Нет</span><span class="sxs-lookup"><span data-stu-id="654f0-267">No</span></span></p></td>
<td><p><span data-ttu-id="654f0-268">Общее количество неудачных сеансов на компонент.</span><span class="sxs-lookup"><span data-stu-id="654f0-268">Total number of failed sessions per component.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-from-users"></a><span data-ttu-id="654f0-269">Показатели для самых распространенных вызывающих пользователей</span><span class="sxs-lookup"><span data-stu-id="654f0-269">Metrics for Top From Users</span></span>

<span data-ttu-id="654f0-270">В следующей таблице представлены сведения, приведенные в отчете распределения сбоев на основе числа пользователей, у которых возникло больше всего ошибок, когда они пытались звонить кому-нибудь еще (которых также называют "вызывающими" пользователями).</span><span class="sxs-lookup"><span data-stu-id="654f0-270">The following table lists the information provided in the Failure Distribution Report based on users who experienced the most failures when they tried to call someone else (known as "From" users).</span></span>

### <a name="metrics-for-top-from-users"></a><span data-ttu-id="654f0-271">Показатели для самых распространенных вызывающих пользователей</span><span class="sxs-lookup"><span data-stu-id="654f0-271">Metrics for Top From Users</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="654f0-272">Имя</span><span class="sxs-lookup"><span data-stu-id="654f0-272">Name</span></span></th>
<th><span data-ttu-id="654f0-273">Поддержка сортировки</span><span class="sxs-lookup"><span data-stu-id="654f0-273">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="654f0-274">Описание</span><span class="sxs-lookup"><span data-stu-id="654f0-274">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="654f0-275"><strong>Rank (Ранг)</strong></span><span class="sxs-lookup"><span data-stu-id="654f0-275"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="654f0-276">Нет</span><span class="sxs-lookup"><span data-stu-id="654f0-276">No</span></span></p></td>
<td><p><span data-ttu-id="654f0-277">Относительно ранжирование неудачных сеансов на основе пользователя, который был приглашен для присоединения к сеансу.</span><span class="sxs-lookup"><span data-stu-id="654f0-277">Relative ranking of failed sessions based on the user who was invited to join the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="654f0-278"><strong>Самые распространенные вызывающие пользователи</strong></span><span class="sxs-lookup"><span data-stu-id="654f0-278"><strong>Top from users</strong></span></span></p></td>
<td><p><span data-ttu-id="654f0-279">Нет</span><span class="sxs-lookup"><span data-stu-id="654f0-279">No</span></span></p></td>
<td><p><span data-ttu-id="654f0-280">SIP-адрес пользователя, приглашенного в сеанс.</span><span class="sxs-lookup"><span data-stu-id="654f0-280">SIP address of the user invited to join the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="654f0-281"><strong>Сеансы</strong></span><span class="sxs-lookup"><span data-stu-id="654f0-281"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="654f0-282">Нет</span><span class="sxs-lookup"><span data-stu-id="654f0-282">No</span></span></p></td>
<td><p><span data-ttu-id="654f0-283">Общее количество неудачных сеансов на пользователя.</span><span class="sxs-lookup"><span data-stu-id="654f0-283">Total number of failed sessions per user.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-to-users"></a><span data-ttu-id="654f0-284">Показатели для самых распространенных вызываемых пользователей</span><span class="sxs-lookup"><span data-stu-id="654f0-284">Metrics for Top To Users</span></span>

<span data-ttu-id="654f0-285">В следующей таблице представлены сведения, приведенные в отчете распределения сбоев на основе пользователей, у которых возникло больше всего ошибок, когда кто-то другой пытался позвонить им (их также называют "вызываемыми" пользователями).</span><span class="sxs-lookup"><span data-stu-id="654f0-285">The following table lists the information provided in the Failure Distribution Report based on the users who experienced the most failures when another user tried to call them (known as "To" users).</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="654f0-286">Имя</span><span class="sxs-lookup"><span data-stu-id="654f0-286">Name</span></span></th>
<th><span data-ttu-id="654f0-287">Поддержка сортировки</span><span class="sxs-lookup"><span data-stu-id="654f0-287">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="654f0-288">Описание</span><span class="sxs-lookup"><span data-stu-id="654f0-288">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="654f0-289"><strong>Rank (Ранг)</strong></span><span class="sxs-lookup"><span data-stu-id="654f0-289"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="654f0-290">Нет</span><span class="sxs-lookup"><span data-stu-id="654f0-290">No</span></span></p></td>
<td><p><span data-ttu-id="654f0-291">Относительно ранжирование неудачных сеансов на основе пользователя, инициировавшего сеанс.</span><span class="sxs-lookup"><span data-stu-id="654f0-291">Relative ranking of failed sessions based on the user who initiated the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="654f0-292"><strong>Самые распространенные вызываемые пользователи</strong></span><span class="sxs-lookup"><span data-stu-id="654f0-292"><strong>Top to users</strong></span></span></p></td>
<td><p><span data-ttu-id="654f0-293">Нет</span><span class="sxs-lookup"><span data-stu-id="654f0-293">No</span></span></p></td>
<td><p><span data-ttu-id="654f0-294">SIP-адрес пользователя, инициировавшего сеанс.</span><span class="sxs-lookup"><span data-stu-id="654f0-294">SIP address of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="654f0-295"><strong>Сеансы</strong></span><span class="sxs-lookup"><span data-stu-id="654f0-295"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="654f0-296">Нет</span><span class="sxs-lookup"><span data-stu-id="654f0-296">No</span></span></p></td>
<td><p><span data-ttu-id="654f0-297">Общее количество неудачных сеансов на пользователя.</span><span class="sxs-lookup"><span data-stu-id="654f0-297">Total number of failed sessions per user.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-user-agents"></a><span data-ttu-id="654f0-298">Показатели для самых распространенных агентов пользователей</span><span class="sxs-lookup"><span data-stu-id="654f0-298">Metrics for Top User Agents</span></span>

<span data-ttu-id="654f0-299">В следующей таблице содержатся сведения, приведенные в отчете распределения сбоев на основе программного обеспечения конечных точек, в которых произошло больше всего ошибок.</span><span class="sxs-lookup"><span data-stu-id="654f0-299">The following table lists the information provided in the Failure Distribution Report based on the endpoint software that experienced the most failures.</span></span>

### <a name="metrics-for-top-user-agents"></a><span data-ttu-id="654f0-300">Показатели для самых распространенных агентов пользователей</span><span class="sxs-lookup"><span data-stu-id="654f0-300">Metrics for Top User Agents</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="654f0-301">Имя</span><span class="sxs-lookup"><span data-stu-id="654f0-301">Name</span></span></th>
<th><span data-ttu-id="654f0-302">Поддержка сортировки</span><span class="sxs-lookup"><span data-stu-id="654f0-302">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="654f0-303">Описание</span><span class="sxs-lookup"><span data-stu-id="654f0-303">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="654f0-304"><strong>Rank (Ранг)</strong></span><span class="sxs-lookup"><span data-stu-id="654f0-304"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="654f0-305">Нет</span><span class="sxs-lookup"><span data-stu-id="654f0-305">No</span></span></p></td>
<td><p><span data-ttu-id="654f0-p115">Относительное ранжирование неудачных сеансов на основе агента пользователя (программного обеспечения), применяемого в сеансе. Например: RTCC/4.0.0.0 Входящее перенаправление/4.0.0.0.</span><span class="sxs-lookup"><span data-stu-id="654f0-p115">Relative ranking of failed sessions based on the user agent (software) involved in the session. For example: RTCC/4.0.0.0 Inbound Routing/4.0.0.0.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="654f0-308"><strong>Самые распространенные агенты пользователей</strong></span><span class="sxs-lookup"><span data-stu-id="654f0-308"><strong>Top user agents</strong></span></span></p></td>
<td><p><span data-ttu-id="654f0-309">Нет</span><span class="sxs-lookup"><span data-stu-id="654f0-309">No</span></span></p></td>
<td><p><span data-ttu-id="654f0-310">Имя агента пользователя, применяемого в неудачном сеансе.</span><span class="sxs-lookup"><span data-stu-id="654f0-310">Name of the user agent involved in the failed session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="654f0-311"><strong>Сеансы</strong></span><span class="sxs-lookup"><span data-stu-id="654f0-311"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="654f0-312">Нет</span><span class="sxs-lookup"><span data-stu-id="654f0-312">No</span></span></p></td>
<td><p><span data-ttu-id="654f0-313">Общее количество неудачных сеансов на агента пользователя.</span><span class="sxs-lookup"><span data-stu-id="654f0-313">Total number of failed sessions per user agent.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

