---
title: 'Lync Server 2013: отчет о самых частых сбоях'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Top Failures Report
ms:assetid: 438942e2-580a-4b67-9d42-f116111fb26a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558640(v=OCS.15)
ms:contentKeyID: 48184021
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 972c9e97015f5a39ace3cf1fc68051cc0afcc988
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193642"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="top-failures-report-in-lync-server-2013"></a><span data-ttu-id="406b0-102">Отчет о самых сбоях в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="406b0-102">Top Failures Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="406b0-103">_**Последнее изменение темы:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="406b0-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="406b0-p101">Отчет по основным сбоям позволяет узнать о наиболее частых сбоях и характере их изменения с течением времени. Сбои основаны на сочетании двух следующих метрик:</span><span class="sxs-lookup"><span data-stu-id="406b0-p101">The Top Failures Report provides a look at the most-commonly reported failures and their trends over time. Failures are based on a combination of the following two metrics:</span></span>

  - <span data-ttu-id="406b0-p102">**Код диагностики**. Уникальный идентификатор (в виде заголовка ms-diagnostics), прикрепленный к сообщению SIP. Коды диагностики предоставляют информацию, полезную при устранении проблем со звонками.</span><span class="sxs-lookup"><span data-stu-id="406b0-p102">**Diagnostic ID**. Unique identifier (in the form of an ms-diagnostics header) that is attached to a SIP message. Diagnostic IDs provide information useful in troubleshooting call-related problems.</span></span>

  - <span data-ttu-id="406b0-109">**Код ответа**.</span><span class="sxs-lookup"><span data-stu-id="406b0-109">**Response code**.</span></span> <span data-ttu-id="406b0-110">Коды ответа используются в сеансах связи SIP для ответы на запросы SIP.</span><span class="sxs-lookup"><span data-stu-id="406b0-110">Response codes are used in SIP communication sessions to respond to SIP requests.</span></span> <span data-ttu-id="406b0-111">Предположим, что пользователь Ken отправляет запрос INVITE пользователю Pilar Ackerman (например, пользователь Ken Myer звонит пользователю Pilar Ackerman).</span><span class="sxs-lookup"><span data-stu-id="406b0-111">For example, suppose Ken sends the INVITE request to Pilar Ackerman (that is, suppose Ken Myer calls Pilar Ackerman).</span></span> <span data-ttu-id="406b0-112">Если Pilar отвечает, ее телефон отправляет код ответа 200 (OK), позволяя телефону Ken узнать об ответе Pilar.</span><span class="sxs-lookup"><span data-stu-id="406b0-112">If Pilar answers, her phone will send the response code 200 (OK), letting Ken's phone know that Pilar has answered.</span></span> <span data-ttu-id="406b0-113">Отчет по основным сбоям включает только коды откликов, отправленные в ответ на ошибку вызова; Lync Server не отслеживает все коды ответа, выданные в ходе вызова.</span><span class="sxs-lookup"><span data-stu-id="406b0-113">The Top Failures Report only includes response codes that were sent in response to a call failure; Lync Server does not keep track of all the response codes issued during the course of a call.</span></span>

<span data-ttu-id="406b0-114">Приводится информация не только об общем числе сеансов, в которых возник сбой, но и об общем числе пользователей, столкнувшихся с этим сбоем.</span><span class="sxs-lookup"><span data-stu-id="406b0-114">Information is reported not only for the total number of sessions where a failure occurred but also for the total number of users who were impacted by the failure.</span></span>

<div>

## <a name="accessing-the-top-failures-report"></a><span data-ttu-id="406b0-115">Доступ к отчету по основным сбоям</span><span class="sxs-lookup"><span data-stu-id="406b0-115">Accessing the Top Failures Report</span></span>

<span data-ttu-id="406b0-116">Доступ к отчету по основным сбоям можно получить с домашней страницы отчетов по мониторингу.</span><span class="sxs-lookup"><span data-stu-id="406b0-116">The Top Failures Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="406b0-117">Щелкнув метрику зарегистрированных сеансов, вы перейдете к [отчету распределения сбоев в Lync Server 2013](lync-server-2013-failure-distribution-report.md).</span><span class="sxs-lookup"><span data-stu-id="406b0-117">Clicking the Reported sessions metric will take you to the [Failure Distribution Report in Lync Server 2013](lync-server-2013-failure-distribution-report.md).</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-top-failures-report"></a><span data-ttu-id="406b0-118">Рекомендации по использованию отчета по основным сбоям</span><span class="sxs-lookup"><span data-stu-id="406b0-118">Making the Best Use of the Top Failures Report</span></span>

<span data-ttu-id="406b0-p105">Отчет по основным сбоям имеет одну необычную особенность: он позволяет одновременно выполнять фильтрацию по 5 кодам диагностики. (Обычно одновременно вы можете выполнять фильтрацию только по одному из них, например по SIP-адресу пользователя.) Чтобы выполнить фильтрацию по нескольким кодам диагностики, просто введите каждый код в поле "Diagnostic IDs" (Коды диагностики), отделяя его запятой. (При необходимости вы можете ставить после каждой запятой пробел.) Например:</span><span class="sxs-lookup"><span data-stu-id="406b0-p105">The Top Failures Report is unusual in one regard: it allows you to filter on as many as 5 diagnostic IDs at once. (Typically you can only filter on one item – such as one user SIP address – at a time.) To filter on multiple diagnostic IDs, simply enter each ID in the Diagnostic IDs box, separating the IDs by using commas. (If you want to, you can leave a blank space after each comma.) For example:</span></span>

<span data-ttu-id="406b0-122">1011, 2412, 1033, 52116, 1008</span><span class="sxs-lookup"><span data-stu-id="406b0-122">1011, 2412, 1033, 52116, 1008</span></span>

<span data-ttu-id="406b0-123">Сделайте это, и будут отображаться только неудачные звонки, в которых возник один из данных кодов диагностики.</span><span class="sxs-lookup"><span data-stu-id="406b0-123">Do that, and only failed calls that reported at least one of those five diagnostic IDs will be displayed.</span></span>

<span data-ttu-id="406b0-p106">Если навести указатель на код диагностики, отображается подсказка с описание его значения. Например, если навести указатель на код ответа 486, отображается следующее сообщение:</span><span class="sxs-lookup"><span data-stu-id="406b0-p106">If you hold your mouse over a Response code you'll see a tooltip that tells you what the Response code in question means. For example, if you hold the mouse over the Response code 486 you'll see this message:</span></span>

<span data-ttu-id="406b0-126">Busy Here (Занято).</span><span class="sxs-lookup"><span data-stu-id="406b0-126">Busy Here.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="406b0-127">Фильтры</span><span class="sxs-lookup"><span data-stu-id="406b0-127">Filters</span></span>

<span data-ttu-id="406b0-p107">Фильтры позволяют получать более адресный набор данных или просматривать полученные данные разными способами. Например, в отчете по основным сбоям можно фильтровать возвращенные данные по типу действия (одноранговый сеанс или сеанс конференц-связи) или по коду ответа SIP, выданному для неудачного сеанса. Кроме того, можно выбрать способ группирования данных. В данном случае вызовы использования по часу, дню, неделе или месяцу.</span><span class="sxs-lookup"><span data-stu-id="406b0-p107">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Top Failures Report enables you to filter the returned data based on such things as the activity type (peer-to-peer session or conferencing session) or by the SIP response code that accompanied the failed session. You can also choose how data should be grouped. In this case, usages are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="406b0-132">В следующей таблице приведены фильтры, которые можно использовать с отчетом по основным сбоям.</span><span class="sxs-lookup"><span data-stu-id="406b0-132">The following table lists the filters that you can use with the Top Failures Report.</span></span>

### <a name="top-failures-report-filters"></a><span data-ttu-id="406b0-133">Фильтры отчета по основным сбоям</span><span class="sxs-lookup"><span data-stu-id="406b0-133">Top Failures Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="406b0-134">Имя</span><span class="sxs-lookup"><span data-stu-id="406b0-134">Name</span></span></th>
<th><span data-ttu-id="406b0-135">Описание</span><span class="sxs-lookup"><span data-stu-id="406b0-135">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="406b0-136"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="406b0-136"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="406b0-p108">Дата и время начала диапазона. Чтобы просмотреть данные по часам, введите дату и время начала в следующем формате:</span><span class="sxs-lookup"><span data-stu-id="406b0-p108">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="406b0-139">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="406b0-139">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="406b0-p109">Если не указать время начала, автоматически будет выбрано время 00:00 указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</span><span class="sxs-lookup"><span data-stu-id="406b0-p109">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="406b0-142">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="406b0-142">7/7/2012</span></span></p>
<p><span data-ttu-id="406b0-143">Для просмотра по неделям или по месяцам введите дату, выпадающую на любой день недели или месяца, который вы хотите просмотреть (это необязательно должен быть первый день недели или месяца):</span><span class="sxs-lookup"><span data-stu-id="406b0-143">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="406b0-144">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="406b0-144">7/3/2012</span></span></p>
<p><span data-ttu-id="406b0-145">Неделя всегда начинается с воскресения и заканчивается субботой.</span><span class="sxs-lookup"><span data-stu-id="406b0-145">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="406b0-146"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="406b0-146"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="406b0-p110">Дата и время окончания диапазона. Чтобы просмотреть данные по часам, введите дату и время окончания в следующем формате:</span><span class="sxs-lookup"><span data-stu-id="406b0-p110">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="406b0-149">7/7/2012 13:00.</span><span class="sxs-lookup"><span data-stu-id="406b0-149">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="406b0-p111">Если не указать время окончания, автоматически будет выбрано время 00:00 указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</span><span class="sxs-lookup"><span data-stu-id="406b0-p111">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="406b0-152">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="406b0-152">7/7/2012</span></span></p>
<p><span data-ttu-id="406b0-153">Для просмотра по неделям или по месяцам введите дату, выпадающую на любой день недели или месяца, который вы хотите просмотреть (это необязательно должен быть первый день недели или месяца):</span><span class="sxs-lookup"><span data-stu-id="406b0-153">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="406b0-154">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="406b0-154">7/3/2012</span></span></p>
<p><span data-ttu-id="406b0-155">Неделя всегда начинается в воскресенье и заканчивается в субботу.</span><span class="sxs-lookup"><span data-stu-id="406b0-155">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="406b0-156"><strong>Activity type (Тип действия)</strong></span><span class="sxs-lookup"><span data-stu-id="406b0-156"><strong>Activity type</strong></span></span></p></td>
<td><p><span data-ttu-id="406b0-p112">Тип действия. Выберите одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="406b0-p112">Type of activity. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="406b0-159">Ко</span><span class="sxs-lookup"><span data-stu-id="406b0-159">[All]</span></span></p></li>
<li><p><span data-ttu-id="406b0-160">"Peer-to-peer" (Одноранговый сеанс);</span><span class="sxs-lookup"><span data-stu-id="406b0-160">Peer-to-peer</span></span></p></li>
<li><p><span data-ttu-id="406b0-161">Встречи</span><span class="sxs-lookup"><span data-stu-id="406b0-161">Conference</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="406b0-162"><strong>Модальности</strong></span><span class="sxs-lookup"><span data-stu-id="406b0-162"><strong>Modality</strong></span></span></p></td>
<td><p><span data-ttu-id="406b0-163">В настоящее время доступен только параметр <strong>[All]</strong> (Все).</span><span class="sxs-lookup"><span data-stu-id="406b0-163">At this time the only option available is <strong>[All]</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="406b0-164"><strong>Ресурсов</strong></span><span class="sxs-lookup"><span data-stu-id="406b0-164"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="406b0-p113">Полное доменное имя пула регистратора или пограничного сервера. Можно выбрать отдельный пул или нажать <strong>[All] ([Все])</strong>, чтобы просмотреть данные для всех пулов. Этот раскрывающийся список автоматически заполняется на основе записей в базе данных.</span><span class="sxs-lookup"><span data-stu-id="406b0-p113">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="406b0-168"><strong>Категория</strong></span><span class="sxs-lookup"><span data-stu-id="406b0-168"><strong>Category</strong></span></span></p></td>
<td><p><span data-ttu-id="406b0-p114">Тип возникшего сбоя. Выберите одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="406b0-p114">Type of failure experienced. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="406b0-171">Как ожидаемый сбой, так и непредвиденный сбой</span><span class="sxs-lookup"><span data-stu-id="406b0-171">Both expected and unexpected failure</span></span></p></li>
<li><p><span data-ttu-id="406b0-172">Непредвиденный сбой</span><span class="sxs-lookup"><span data-stu-id="406b0-172">Unexpected failure</span></span></p></li>
</ul>
<p><span data-ttu-id="406b0-173">&quot;Ожидаемый сбой&quot; — это сбой, который должен произойти.</span><span class="sxs-lookup"><span data-stu-id="406b0-173">An &quot;expected failure&quot; is a failure that is expected to happen.</span></span> <span data-ttu-id="406b0-174">Например, если пользователь установил статус "Не беспокоить", то ожидаемое, что все вызовы этого пользователя завершатся неудачно.</span><span class="sxs-lookup"><span data-stu-id="406b0-174">For example, if a user has set his or her status to Do Not Disturb you would expect any call to that user to fail.</span></span> <span data-ttu-id="406b0-175">&quot;Непредвиденный сбой&quot; — это проблема, которая может показаться неработоспособной системой.</span><span class="sxs-lookup"><span data-stu-id="406b0-175">An &quot;unexpected failure&quot; is a failure that occurs in what would appear to be an otherwise healthy system.</span></span> <span data-ttu-id="406b0-176">Например, вызов не должен прерываться, если вызывающий абонент помещается на удержание.</span><span class="sxs-lookup"><span data-stu-id="406b0-176">For example, a call should not be terminated if the caller is placed on hold.</span></span> <span data-ttu-id="406b0-177">В этом случае это считается непредвиденным сбоем.</span><span class="sxs-lookup"><span data-stu-id="406b0-177">If that occurs, that would be flagged as an unexpected failure.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="406b0-178"><strong>Response code</strong> (Код ответа)</span><span class="sxs-lookup"><span data-stu-id="406b0-178"><strong>Response code</strong></span></span></p></td>
<td><p><span data-ttu-id="406b0-p116">Код ответа SIP, отправленный при сбое конференции. Введите полный код ответа, например:</span><span class="sxs-lookup"><span data-stu-id="406b0-p116">SIP response code sent when the conference failed. Enter the entire response code For example:</span></span></p>
<p><span data-ttu-id="406b0-181">400</span><span class="sxs-lookup"><span data-stu-id="406b0-181">400</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="406b0-182"><strong>Diagnostic ID</strong> (ИД диагностики)</span><span class="sxs-lookup"><span data-stu-id="406b0-182"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="406b0-p117">Уникальный идентификатор (в форме заголовка ms-diagnostics), присоединенный к сообщению SIP, который часто содержит сведения, помогающий устранять ошибки. Диагностические заголовки являются необязательными (можно иметь сеансы SIP, не включающие эти заголовки), и диагностические идентификаторы сообщаются только для тех сеансов, которые испытывали какие-либо проблемы.</span><span class="sxs-lookup"><span data-stu-id="406b0-p117">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="406b0-185">Метрик</span><span class="sxs-lookup"><span data-stu-id="406b0-185">Metrics</span></span>

<span data-ttu-id="406b0-186">Следующая таблица содержит сведения, приведенные в отчете по основным сбоям.</span><span class="sxs-lookup"><span data-stu-id="406b0-186">The following table lists the information provided in the Top Failures Report.</span></span>

### <a name="top-failures-report-metrics"></a><span data-ttu-id="406b0-187">Метрики отчета по основным сбоям</span><span class="sxs-lookup"><span data-stu-id="406b0-187">Top Failures Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="406b0-188">Имя</span><span class="sxs-lookup"><span data-stu-id="406b0-188">Name</span></span></th>
<th><span data-ttu-id="406b0-189">Возможность сортировки по этому показателю</span><span class="sxs-lookup"><span data-stu-id="406b0-189">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="406b0-190">Описание</span><span class="sxs-lookup"><span data-stu-id="406b0-190">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="406b0-191"><strong>Rank</strong></span><span class="sxs-lookup"><span data-stu-id="406b0-191"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="406b0-192">Да</span><span class="sxs-lookup"><span data-stu-id="406b0-192">Yes</span></span></p></td>
<td><p><span data-ttu-id="406b0-193">Относительный ранг, основанный на количестве включенных в отчет сеансов.</span><span class="sxs-lookup"><span data-stu-id="406b0-193">Relative rank based on the number of reported sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="406b0-194"><strong>Reported sessions</strong> (Отчетные сеансы)</span><span class="sxs-lookup"><span data-stu-id="406b0-194"><strong>Reported sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="406b0-195">Да</span><span class="sxs-lookup"><span data-stu-id="406b0-195">Yes</span></span></p></td>
<td><p><span data-ttu-id="406b0-196">Общее число неудачных сеансов на основе кода диагностики и кода ответа SIP.</span><span class="sxs-lookup"><span data-stu-id="406b0-196">Total number of failed sessions based on diagnostic ID and SIP response code.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="406b0-197"><strong>Users impacted</strong> (Затронутые пользователи)</span><span class="sxs-lookup"><span data-stu-id="406b0-197"><strong>Users impacted</strong></span></span></p></td>
<td><p><span data-ttu-id="406b0-198">Да</span><span class="sxs-lookup"><span data-stu-id="406b0-198">Yes</span></span></p></td>
<td><p><span data-ttu-id="406b0-199">Общее число пользователей, столкнувшихся с неудачным сеансом.</span><span class="sxs-lookup"><span data-stu-id="406b0-199">Total number of users affected by the failed session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="406b0-200"><strong>Failure information</strong> (Информация о сбое)</span><span class="sxs-lookup"><span data-stu-id="406b0-200"><strong>Failure information</strong></span></span></p></td>
<td><p><span data-ttu-id="406b0-201">Нет</span><span class="sxs-lookup"><span data-stu-id="406b0-201">No</span></span></p></td>
<td><p><span data-ttu-id="406b0-202">Подробные сведения о сбое, включая код диагностики, код ответа SIP и описание причины сбоя сеанса.</span><span class="sxs-lookup"><span data-stu-id="406b0-202">Detailed information about the failure, including diagnostic ID, SIP response code, and description of why the session failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="406b0-203"><strong>Trend in the past</strong> (Прошлая тенденция)</span><span class="sxs-lookup"><span data-stu-id="406b0-203"><strong>Trend in the past</strong></span></span></p></td>
<td><p><span data-ttu-id="406b0-204">Нет</span><span class="sxs-lookup"><span data-stu-id="406b0-204">No</span></span></p></td>
<td><p><span data-ttu-id="406b0-205">График, показывающий зависимость неудачных сеансов от времени.</span><span class="sxs-lookup"><span data-stu-id="406b0-205">Graphs failed sessions over time.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

