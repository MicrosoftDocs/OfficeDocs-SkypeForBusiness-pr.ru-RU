---
title: 'Lync Server 2013: отчет об активности пользователей'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User Activity Report
ms:assetid: 3aa6fef2-ea02-4f0f-93e8-fa2e0a953d79
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558638(v=OCS.15)
ms:contentKeyID: 48183862
ms.date: 02/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 38df7f9f8c457ac68ee441a6806b87f37b10539b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140862"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="user-activity-report-in-lync-server-2013"></a><span data-ttu-id="7066d-102">Отчет об активности пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7066d-102">User Activity Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7066d-103">_**Последнее изменение темы:** 2015-02-27_</span><span class="sxs-lookup"><span data-stu-id="7066d-103">_**Topic Last Modified:** 2015-02-27_</span></span>

<span data-ttu-id="7066d-p101">Отчет об активности пользователей предоставляет подробный список одноранговых сеансов и сеансов конференц-связи, проведенных вашими пользователями за определенный период времени. В отличие от многих отчетов мониторинга отчет об активности пользователей связывает каждый звонок с отдельными пользователями. Например, одноранговые сеансы указывают универсальные коды ресурса (URI) SIP человека, который инициировал звонок (пользователь-отправитель), и человека, которому звонок был выполнен (пользователь-получатель). Если развернуть информацию по конференции вы увидите список всех участников конференции с указанием их роли.</span><span class="sxs-lookup"><span data-stu-id="7066d-p101">The User Activity Report provides a detailed list of the peer-to-peer and conferencing sessions carried out by your users in a given time period. Unlike many of the Monitoring Reports, the User Activity Report ties each call to individual users. For example, peer-to-peer sessions specify the SIP URIs of the person who initiated the call (the From user) and the person who was being called (the To user). If you expand the information for a conference, you'll see a list of all the conference participants and the role they held for that conference.</span></span>

<span data-ttu-id="7066d-p102">Отчет об активности пользователей иногда называют отчетом «службы технической поддержки». Это вызвано тем, что данный отчет часто используется сотрудниками службы технической поддержки для получения информации о сеансе для определенного пользователя. Вы можете отфильтровывать входящие и исходящие звонки для отдельного пользователя, просто введя URI SIP в поле «User URI prefix» (Префикс URI пользователя).</span><span class="sxs-lookup"><span data-stu-id="7066d-p102">The User Activity Report is sometimes referred to as the "help desk" report. That's because the report is often used by help desk personnel to retrieve session information for a specific user. You can filter for calls made to or made by an individual user simply by typing the user's SIP URI in the User URI prefix box.</span></span>

<span data-ttu-id="7066d-111">В этом случае отчет об активности пользователей возвратит сведения для любого пользователя, чей URI SIP начинается с указанной строки.</span><span class="sxs-lookup"><span data-stu-id="7066d-111">If you do this, the User Activity Report will return information for any user whose SIP URI begins with the specified string.</span></span> <span data-ttu-id="7066d-112">Например, если ввести **Ken** в поле URI, то в отчете об активности пользователей будет обнаружено **Ken**. Myer@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="7066d-112">For example, if you type **ken** in the URI box, the User Activity Report will locate **Ken**.Myer@litwareinc.com.</span></span> <span data-ttu-id="7066d-113">Тем не менее, они также будут искать следующих пользователей:</span><span class="sxs-lookup"><span data-stu-id="7066d-113">However, it will also locate these users:</span></span>

  - <span data-ttu-id="7066d-114">**кен**Azi@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="7066d-114">**ken**azi@litwareinc.com</span></span>

  - <span data-ttu-id="7066d-115">**кен**Burg@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="7066d-115">**ken**burg@litwareinc.com</span></span>

  - <span data-ttu-id="7066d-116">**Ken**. Sanchez@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="7066d-116">**Ken**.Sanchez@litwareinc.com</span></span>

  - <span data-ttu-id="7066d-117">**Кен**Nedy@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="7066d-117">**Ken**nedy@litwareinc.com</span></span>

<span data-ttu-id="7066d-118">Чтобы убедиться в том, что возвращены только сведения для Ken Myer, введите в поле поиска полный URI (Ken.Myer@litwareinc.com) или по крайней мере достаточно типа URI Ken, чтобы уникальным образом отличать его от других пользователей в Организации.</span><span class="sxs-lookup"><span data-stu-id="7066d-118">To ensure that information only for Ken Myer is returned, either type his full URI (Ken.Myer@litwareinc.com) in the search box or at least enough type of Ken’s URI to uniquely distinguish him from other users in your organization.</span></span> <span data-ttu-id="7066d-119">Например:</span><span class="sxs-lookup"><span data-stu-id="7066d-119">For example:</span></span>

<span data-ttu-id="7066d-120">Ken.my</span><span class="sxs-lookup"><span data-stu-id="7066d-120">Ken.my</span></span>

<div>

## <a name="to-access-the-user-activity-report"></a><span data-ttu-id="7066d-121">Чтобы получить доступ к отчету о действиях пользователей, выполните следующие действия</span><span class="sxs-lookup"><span data-stu-id="7066d-121">To access the user activity report</span></span>

<span data-ttu-id="7066d-122">Доступ к отчету об активности пользователей осуществляется с домашней страницы отчетов мониторинга.</span><span class="sxs-lookup"><span data-stu-id="7066d-122">The User Activity Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="7066d-123">Вы также можете получить доступ к отчету о действиях пользователей, щелкнув метрику URI пользователя в [отчете по IP-телефонам в Lync Server 2013](lync-server-2013-ip-phone-inventory-report.md).</span><span class="sxs-lookup"><span data-stu-id="7066d-123">You can also reach the User Activity Report by clicking the User URI metric on the [IP Phone Inventory Report in Lync Server 2013](lync-server-2013-ip-phone-inventory-report.md).</span></span> <span data-ttu-id="7066d-124">Щелкнув элемент «Conference URI» (URI конференции) в отчете об активности пользователей вы откроете подробный отчет о конференции.</span><span class="sxs-lookup"><span data-stu-id="7066d-124">From within the User Activity Report, clicking the Conference URI (for a conference) takes you to the Conference Detail Report.</span></span> <span data-ttu-id="7066d-125">Аналогично, если щелкнуть метрику деталей для однорангового звонка, вы переходите к [отчету по деталям однорангового сеанса в Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md).</span><span class="sxs-lookup"><span data-stu-id="7066d-125">Similarly, clicking the Detail metric for a peer-to-peer call takes you to the [Peer-to-Peer Session Detail Report in Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md).</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-user-activity-report"></a><span data-ttu-id="7066d-126">Оптимальное использование отчета об активности пользователей</span><span class="sxs-lookup"><span data-stu-id="7066d-126">Making the best use of the user activity report</span></span>

<span data-ttu-id="7066d-127">Хотя отчет об активности пользователей содержит много полезной информации, ее бывает сложно найти.</span><span class="sxs-lookup"><span data-stu-id="7066d-127">Although there is a lot of good information in the User Activity Report, that information can sometimes be difficult to locate.</span></span> <span data-ttu-id="7066d-128">Например, все действия пользователя, выполняемые в Организации в течение определенного периода времени, включаются в отчет об активности пользователей; Это означает, что в отчете скрыта информация о том, какие пользователи фактически использовали Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7066d-128">For example, all the user activity that takes place in your organization during a specified period is included in the User Activity Report; that means that, buried, within the report is information about which users actually used Microsoft Lync Server 2013 in some way.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="7066d-129">С технической точки зрения некоторые действия пользователя могут быть незаписанными: в то время как Lync Server стремится хранить информацию обо всех телефонных звонках, что может привести к выполнению вызова без информации о том, что этот вызов записывает в базу данных.</span><span class="sxs-lookup"><span data-stu-id="7066d-129">Technically, it’s possible that some user activity might go unrecorded: while Lync Server strives to keep information about all phone calls it's possible that a call could have been made without the information about that call being written to the database.</span></span> <span data-ttu-id="7066d-130">Lync Server предназначен для предоставления очень точного, но не обязательно идеального внешнего вида использования Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7066d-130">Lync Server is designed to give an extremely accurate but not necessarily perfect look at how Lync Server 2013 is being used.</span></span> <span data-ttu-id="7066d-131">(Факт отсутствия гарантии, что 100% всех вызовов записано объясняется тем, почему мониторинг сервера Lync Server не следует использовать в качестве системы выставления счетов.)</span><span class="sxs-lookup"><span data-stu-id="7066d-131">(The fact that there is no guarantee that 100% of all calls are recorded explains why Lync Server monitoring should not be used as a billing system.)</span></span><BR><span data-ttu-id="7066d-p108">Во-вторых, отчет мониторинга может отобразить не более 1000 записей. Таким образом, в зависимости от уровня активности пользователей и обрабатываемого периода запрос может возвращать не все данные, находящиеся в базе данных.</span><span class="sxs-lookup"><span data-stu-id="7066d-p108">Second, a Monitoring Report report can only display, at most, 1,000 records. Depending on the amount of user activity you have, and depending on the time period you are working with, that means your query might not return all the data actually stored in the database.</span></span>



</div>

  - <span data-ttu-id="7066d-134">Какие именно пользователи использовали систему в определенный период?</span><span class="sxs-lookup"><span data-stu-id="7066d-134">Which users actually used the system during this time period?</span></span>

  - <span data-ttu-id="7066d-135">Какие именно пользователи были наиболее активными в определенный период?</span><span class="sxs-lookup"><span data-stu-id="7066d-135">Which of my users were the most active during this time period?</span></span>

  - <span data-ttu-id="7066d-136">Являются ли пользователи, выполнившие наиболее количество звонков, так же и пользователями, принявшими участие в большинстве сеансов обмена мгновенными сообщениями?</span><span class="sxs-lookup"><span data-stu-id="7066d-136">Are the users who make the most phone calls also the users who participate in the most instant messaging sessions?</span></span>

<span data-ttu-id="7066d-137">Если вам нужно ответить на такие вопросы, вы можете экспортировать данные, полученные отчетами мониторинга, в электронную таблицу Excel.</span><span class="sxs-lookup"><span data-stu-id="7066d-137">If you need to answer questions like this, you can export the data retrieved by the Monitoring Reports to an Excel spreadsheet.</span></span> <span data-ttu-id="7066d-138">Затем используйте эту электронную таблицу и/или файл значений с разделителями-запятыми, чтобы проанализировать данные способами в отчете об активности пользователей.</span><span class="sxs-lookup"><span data-stu-id="7066d-138">You then use that spreadsheet and/or a comma-separated values file to analyze the data in ways that the User Activity Report.</span></span> <span data-ttu-id="7066d-139">Например, предположим, что данные отчета экспортированы в Excel, а затем — в файл значений с разделителями запятыми.</span><span class="sxs-lookup"><span data-stu-id="7066d-139">For example, suppose you have exported the report data to Excel and then to a comma-separated values file.</span></span> <span data-ttu-id="7066d-140">В этот момент вы можете импортировать данные из. CSV-файл в Windows PowerShell с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="7066d-140">At that point, you can import the data from the .CSV file to Windows PowerShell by using a command similar to this:</span></span>

    $x = Import-Csv -Path "C:\Data\User_Activity_Report.csv"

<span data-ttu-id="7066d-141">После импорта данных вы можете использовать простые команды Windows PowerShell, чтобы помочь вам ответить на ваши вопросы.</span><span class="sxs-lookup"><span data-stu-id="7066d-141">After the data has been imported you can then use simple Windows PowerShell commands to help answer your questions.</span></span> <span data-ttu-id="7066d-142">Например, эта команда возвращает список уникальных пользователей, являвшихся пользователем-отправителем хотя бы в одном сеансе:</span><span class="sxs-lookup"><span data-stu-id="7066d-142">For example, this command returns a list of unique users who served as the "From user" in at least one session:</span></span>

    $x | Group-Object "From user" | Select Name | Sort-Object Name

<span data-ttu-id="7066d-143">Другими словами:</span><span class="sxs-lookup"><span data-stu-id="7066d-143">In other words:</span></span>

    Name
    ----
    David.Ahs@litwareinc.com
    Gilead.Amosnino@litwareinc.com
    Henrik.Jensen@litwareinc.com
    Ken.Myer@litwareinc.com
    Pilar.Ackerman@litwareinc.com

<span data-ttu-id="7066d-144">Эта команда выводит список уникальных пользователей (на основании общего числа сеансов, в которых они приняли участие:</span><span class="sxs-lookup"><span data-stu-id="7066d-144">This command lists the unique users (based on the total number of sessions that they participated in:</span></span>

    $x | Group-Object "From user" | Select Count, Name | Sort-Object Count -Descending

<span data-ttu-id="7066d-145">При этом возвращаются данные, аналогичные следующим:</span><span class="sxs-lookup"><span data-stu-id="7066d-145">That returns data similar to this:</span></span>

    Count    Name
    -----    ----
      523    Ken.Myer@litwareinc.com
       63    David.Ahs@litwareinc.com
       29    Pilar.Ackerman@litwareinc.com
       17    Gilead.Amosnino@litwareinc.com
       10    Henrik.Jensen@litwareinc.com

<span data-ttu-id="7066d-146">Эта команда ограничивает область поиска только сеансами, имевшими звуковую модальность:</span><span class="sxs-lookup"><span data-stu-id="7066d-146">This command limits the reported sessions to those that included audio as a modality:</span></span>

    $x | Where-Object {$_.Modalities -match "audio"} | Group-Object "From user" | Select Count, Name | Sort-Object Count -Descending

<span data-ttu-id="7066d-147">При наведении указателя на любой идентификатор диагностики в отчете отображается подсказка с описанием этого идентификатора.</span><span class="sxs-lookup"><span data-stu-id="7066d-147">If you hold your mouse over any Diagnostic ID shown on the report, a tooltip will appear describing that ID.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="7066d-148">Фильтры</span><span class="sxs-lookup"><span data-stu-id="7066d-148">Filters</span></span>

<span data-ttu-id="7066d-p111">Фильтры позволяют вам возвратить уточненный набор данных или просматривать возвращенные данные различными способами. Например, отчет об активности пользователей позволяет вам фильтровать возвращенные данные, например, по типу активности (одноранговые сеансы или сеансы конференц-связи) или по SIP-адресу пользователя (позволяя вам просматривать активность одного пользователя). Вы также можете определить группировку данных. В данном случае сведения об использовании группируются по часу, дню, неделе или месяцу.</span><span class="sxs-lookup"><span data-stu-id="7066d-p111">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the User Activity Report enables you to filter the returned data based on such things as activity type (that is, peer-to-peer sessions or conferencing sessions) or by the user's SIP address (allowing you to view the activities for one user). You can also choose how data should be grouped. In this case, usages are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="7066d-153">В следующей таблице перечислены фильтры, которые вы можете использовать в отчете об активности пользователей.</span><span class="sxs-lookup"><span data-stu-id="7066d-153">The following table lists the filters that you can use with the User Activity Report.</span></span>

### <a name="user-activity-report-filters"></a><span data-ttu-id="7066d-154">Фильтры отчета активности пользователя</span><span class="sxs-lookup"><span data-stu-id="7066d-154">User activity report filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7066d-155">Имя</span><span class="sxs-lookup"><span data-stu-id="7066d-155">Name</span></span></th>
<th><span data-ttu-id="7066d-156">Описание</span><span class="sxs-lookup"><span data-stu-id="7066d-156">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7066d-157"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="7066d-157"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="7066d-p112">Дата и время начала диапазона времени. Чтобы просматривать данные по часам, введите дату и время начала:</span><span class="sxs-lookup"><span data-stu-id="7066d-p112">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="7066d-160">17.07.12 13:00</span><span class="sxs-lookup"><span data-stu-id="7066d-160">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="7066d-p113">Если вы не вводите начальное время, отчет автоматически начинается с 24:00 указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</span><span class="sxs-lookup"><span data-stu-id="7066d-p113">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="7066d-163">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="7066d-163">7/17/12012</span></span></p>
<p><span data-ttu-id="7066d-164">Чтобы просматривать данные по неделям или месяцам, введите дату, попадающую в интересующую неделю или месяц (не обязательно указывать первый день недели или месяца):</span><span class="sxs-lookup"><span data-stu-id="7066d-164">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="7066d-165">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="7066d-165">7/13/2012</span></span></p>
<p><span data-ttu-id="7066d-166">Недели всегда продолжаются с воскресенья по субботу.</span><span class="sxs-lookup"><span data-stu-id="7066d-166">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7066d-167"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="7066d-167"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="7066d-p114">Дата и время конца диапазона времени. Чтобы просматривать данные по часам, введите дату и время окончания:</span><span class="sxs-lookup"><span data-stu-id="7066d-p114">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="7066d-170">17.07.12 13:00</span><span class="sxs-lookup"><span data-stu-id="7066d-170">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="7066d-p115">Если вы не вводите конечное время, отчет автоматически заканчивается в 24:00 указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</span><span class="sxs-lookup"><span data-stu-id="7066d-p115">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="7066d-173">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="7066d-173">7/17/12012</span></span></p>
<p><span data-ttu-id="7066d-174">Чтобы просматривать данные по неделям или месяцам, введите дату, попадающую в интересующую неделю или месяц (не обязательно указывать первый день недели или месяца):</span><span class="sxs-lookup"><span data-stu-id="7066d-174">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="7066d-175">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="7066d-175">7/13/2012</span></span></p>
<p><span data-ttu-id="7066d-176">Недели всегда отсчитываются с воскресенья по субботу.</span><span class="sxs-lookup"><span data-stu-id="7066d-176">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7066d-177"><strong>Activity type (Тип действия)</strong></span><span class="sxs-lookup"><span data-stu-id="7066d-177"><strong>Activity type</strong></span></span></p></td>
<td><p><span data-ttu-id="7066d-p116">Тип действия. Выберите одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="7066d-p116">Type of activity. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="7066d-180">Ко</span><span class="sxs-lookup"><span data-stu-id="7066d-180">[All]</span></span></p></li>
<li><p><span data-ttu-id="7066d-181">"Peer-to-peer" (Одноранговый сеанс);</span><span class="sxs-lookup"><span data-stu-id="7066d-181">Peer-to-peer</span></span></p></li>
<li><p><span data-ttu-id="7066d-182">Встречи</span><span class="sxs-lookup"><span data-stu-id="7066d-182">Conference</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7066d-183"><strong>Модальности</strong></span><span class="sxs-lookup"><span data-stu-id="7066d-183"><strong>Modality</strong></span></span></p></td>
<td><p><span data-ttu-id="7066d-184">Модальность, доступная в зависимости от выбранного типа действия, зависит от выбранного типа.</span><span class="sxs-lookup"><span data-stu-id="7066d-184">The Modality available to you varies depending on the select Activity Type.</span></span> <span data-ttu-id="7066d-185">Если тип действия — Peer-to-Peer, можно выбрать обмен мгновенными сообщениями; Передача файлов; Общий доступ к приложениям; Фактур или видео в качестве модальности.</span><span class="sxs-lookup"><span data-stu-id="7066d-185">If the Activity Type is Peer-to-Peer, you can select IM; File Transfer; Application Sharing; Voice; or Video as the modality.</span></span></p>
<p><span data-ttu-id="7066d-186">Если тип действия — конференц-связи, можно выбрать конференц-связи с телефонным СООБЩЕНИЕм; Веб-конференция; Общий доступ к приложениям; Конференция голосовых и видеоконференций; или на телефонную конференцию.</span><span class="sxs-lookup"><span data-stu-id="7066d-186">If the Activity Type is Conference, you can select IM Phone conference; Web conference; Application Sharing; Voice/Video conference; or Telephony conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7066d-187"><strong>Session category</strong> (Категория сеанса)</span><span class="sxs-lookup"><span data-stu-id="7066d-187"><strong>Session category</strong></span></span></p></td>
<td><p><span data-ttu-id="7066d-p118">Указывает, была ли рассматриваемая активность успешна. Выберите одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="7066d-p118">Indicates whether the activity in question succeeded or failed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="7066d-190">Ко</span><span class="sxs-lookup"><span data-stu-id="7066d-190">[All]</span></span></p></li>
<li><p><span data-ttu-id="7066d-191">Success</span><span class="sxs-lookup"><span data-stu-id="7066d-191">Success</span></span></p></li>
<li><p><span data-ttu-id="7066d-192">Expected failure (Ожидаемый сбой)</span><span class="sxs-lookup"><span data-stu-id="7066d-192">Expected failure</span></span></p></li>
<li><p><span data-ttu-id="7066d-193">Непредвиденный сбой</span><span class="sxs-lookup"><span data-stu-id="7066d-193">Unexpected failure</span></span></p></li>
</ul>
<p><span data-ttu-id="7066d-194">&quot;Ожидаемый сбой&quot; — это сбой, который должен произойти; Например, если пользователь настроил состояние "не беспокоить", вы не можете ожидать, что любой из вызовов этого пользователя не будет выполнен.</span><span class="sxs-lookup"><span data-stu-id="7066d-194">An &quot;expected failure&quot; is a failure that is expected to happen; for example, if a user has set his or her status to Do Not Disturb you would expect any call to that user to fail.</span></span> <span data-ttu-id="7066d-195">&quot;Непредвиденный сбой&quot; — это проблема, которая может показаться неработоспособной системой.</span><span class="sxs-lookup"><span data-stu-id="7066d-195">An &quot;unexpected failure&quot; is a failure that occurs in what would appear to be an otherwise healthy system.</span></span> <span data-ttu-id="7066d-196">Например, вызов не должен прерываться, если вызывающий абонент помещается на удержание.</span><span class="sxs-lookup"><span data-stu-id="7066d-196">For example, a call should not be terminated if the caller is placed on hold.</span></span> <span data-ttu-id="7066d-197">В этом случае это считается непредвиденным сбоем.</span><span class="sxs-lookup"><span data-stu-id="7066d-197">If that occurs, that would be flagged as an unexpected failure.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7066d-198"><strong>User URI prefix</strong> (Префикс URI пользователя)</span><span class="sxs-lookup"><span data-stu-id="7066d-198"><strong>User URI prefix</strong></span></span></p></td>
<td><p><span data-ttu-id="7066d-p120">Адрес SIP пользователя. Чтобы просмотреть только записи для пользователя Ken Myer, вам необходимо ввести SIP-адрес этого пользователя. Например:</span><span class="sxs-lookup"><span data-stu-id="7066d-p120">SIP address for the user. To view records only for the user Ken Myer you need to enter Ken Myer's SIP address. For example:</span></span></p>
<p><span data-ttu-id="7066d-202">sip:kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="7066d-202">sip:kenmyer@litwareinc.com</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="7066d-203">Метрики для одноранговых сеансов</span><span class="sxs-lookup"><span data-stu-id="7066d-203">Metrics for peer-to-peer sessions</span></span>

<span data-ttu-id="7066d-204">В следующей таблице приведены сведения из отчета об активности пользователей для одноранговых сеансов (то есть сеансов, включающих всего двух участников).</span><span class="sxs-lookup"><span data-stu-id="7066d-204">The following table lists the information provided in the User Activity Report for peer-to-peer sessions (that is, sessions involving just two participants).</span></span>

### <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="7066d-205">Метрики для одноранговых сеансов</span><span class="sxs-lookup"><span data-stu-id="7066d-205">Metrics for peer-to-peer sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7066d-206">Имя</span><span class="sxs-lookup"><span data-stu-id="7066d-206">Name</span></span></th>
<th><span data-ttu-id="7066d-207">Возможность сортировки по этому показателю</span><span class="sxs-lookup"><span data-stu-id="7066d-207">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="7066d-208">Описание</span><span class="sxs-lookup"><span data-stu-id="7066d-208">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7066d-209"><strong>Detail</strong></span><span class="sxs-lookup"><span data-stu-id="7066d-209"><strong>Detail</strong></span></span></p></td>
<td><p><span data-ttu-id="7066d-210">Нет</span><span class="sxs-lookup"><span data-stu-id="7066d-210">No</span></span></p></td>
<td><p><span data-ttu-id="7066d-211">При щелчке данного элемента отчет отображает для выбранного сеанса подробный отчет об одноранговом сеансе.</span><span class="sxs-lookup"><span data-stu-id="7066d-211">When you click this item, the report shows you the Peer-to-Peer Session Detail Report for the selected session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7066d-212"><strong>From user</strong> (Пользователь-отправитель)</span><span class="sxs-lookup"><span data-stu-id="7066d-212"><strong>From user</strong></span></span></p></td>
<td><p><span data-ttu-id="7066d-213">Да</span><span class="sxs-lookup"><span data-stu-id="7066d-213">Yes</span></span></p></td>
<td><p><span data-ttu-id="7066d-214">SIP-адрес пользователя, который инициировал данный одноранговый сеанс.</span><span class="sxs-lookup"><span data-stu-id="7066d-214">SIP address of the user who initiated the peer-to-peer session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7066d-215"><strong>To user</strong> (Пользователь-получатель)</span><span class="sxs-lookup"><span data-stu-id="7066d-215"><strong>To user</strong></span></span></p></td>
<td><p><span data-ttu-id="7066d-216">Да</span><span class="sxs-lookup"><span data-stu-id="7066d-216">Yes</span></span></p></td>
<td><p><span data-ttu-id="7066d-217">SIP-адрес пользователя, который присоединился к данному одноранговому сеансу.</span><span class="sxs-lookup"><span data-stu-id="7066d-217">SIP address of the user who joined the peer-to-peer session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7066d-218"><strong>Модальности</strong></span><span class="sxs-lookup"><span data-stu-id="7066d-218"><strong>Modalities</strong></span></span></p></td>
<td><p><span data-ttu-id="7066d-219">Да</span><span class="sxs-lookup"><span data-stu-id="7066d-219">Yes</span></span></p></td>
<td><p><span data-ttu-id="7066d-p121">Тип коммуникации, использованный в сеансе. Например, мгновенные сообщения, звук или передача файлов.</span><span class="sxs-lookup"><span data-stu-id="7066d-p121">Type of communication used in the session. For example, IM, audio, or file transfer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7066d-222"><strong>Invite time</strong> (Время приглашения)</span><span class="sxs-lookup"><span data-stu-id="7066d-222"><strong>Invite time</strong></span></span></p></td>
<td><p><span data-ttu-id="7066d-223">Да</span><span class="sxs-lookup"><span data-stu-id="7066d-223">Yes</span></span></p></td>
<td><p><span data-ttu-id="7066d-224">Дата и время отправки начального приглашения присоединиться к одноранговому сеансу.</span><span class="sxs-lookup"><span data-stu-id="7066d-224">Date and time the initial invitation to join the peer-to-peer session was sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7066d-225"><strong>Response time</strong> (Время ответа)</span><span class="sxs-lookup"><span data-stu-id="7066d-225"><strong>Response time</strong></span></span></p></td>
<td><p><span data-ttu-id="7066d-226">Да</span><span class="sxs-lookup"><span data-stu-id="7066d-226">Yes</span></span></p></td>
<td><p><span data-ttu-id="7066d-227">Дата и время, &quot;когда&quot; пользователь принял приглашение на сеанс.</span><span class="sxs-lookup"><span data-stu-id="7066d-227">Date and time that the &quot;To&quot; user accepted the session invitation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7066d-228"><strong>End time</strong> (Время окончания)</span><span class="sxs-lookup"><span data-stu-id="7066d-228"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="7066d-229">Да</span><span class="sxs-lookup"><span data-stu-id="7066d-229">Yes</span></span></p></td>
<td><p><span data-ttu-id="7066d-230">Дата и время окончания однорангового сеанса.</span><span class="sxs-lookup"><span data-stu-id="7066d-230">Date and time the peer-to-peer session ended.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7066d-231"><strong>Diagnostic ID</strong> (Идентификатор диагностики)</span><span class="sxs-lookup"><span data-stu-id="7066d-231"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="7066d-232">Да</span><span class="sxs-lookup"><span data-stu-id="7066d-232">Yes</span></span></p></td>
<td><p><span data-ttu-id="7066d-p122">Уникальный идентификатор (в форме заголовка ms-diagnostics), присоединенный к сообщению SIP, который часто содержит сведения, помогающий устранять ошибки. Диагностические заголовки являются необязательными (можно иметь сеансы SIP, не включающие эти заголовки), и диагностические идентификаторы сообщаются только для тех сеансов, которые испытывали какие-либо проблемы.</span><span class="sxs-lookup"><span data-stu-id="7066d-p122">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="7066d-235">Метрики для сеансов конференц-связи</span><span class="sxs-lookup"><span data-stu-id="7066d-235">Metrics for conferencing sessions</span></span>

<span data-ttu-id="7066d-236">В следующей таблице приведены сведения из отчета об активности пользователей для сеансов конференц-связи (то есть сеансов, включающих трех и более участников).</span><span class="sxs-lookup"><span data-stu-id="7066d-236">The following table lists the information provided in the User Activity Report for conferencing sessions (that is, sessions involving three or more participants).</span></span>

### <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="7066d-237">Метрики для сеансов конференц-связи</span><span class="sxs-lookup"><span data-stu-id="7066d-237">Metrics for conferencing sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7066d-238">Имя</span><span class="sxs-lookup"><span data-stu-id="7066d-238">Name</span></span></th>
<th><span data-ttu-id="7066d-239">Возможность сортировки по этому показателю</span><span class="sxs-lookup"><span data-stu-id="7066d-239">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="7066d-240">Описание</span><span class="sxs-lookup"><span data-stu-id="7066d-240">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7066d-241"><strong>Conference URI</strong> (URI конференции)</span><span class="sxs-lookup"><span data-stu-id="7066d-241"><strong>Conference URI</strong></span></span></p></td>
<td><p><span data-ttu-id="7066d-242">Да</span><span class="sxs-lookup"><span data-stu-id="7066d-242">Yes</span></span></p></td>
<td><p><span data-ttu-id="7066d-243">Уникальный идентификатор конференции.</span><span class="sxs-lookup"><span data-stu-id="7066d-243">Unique conference identifier.</span></span> <span data-ttu-id="7066d-244">При щелчке данного элемента отчет отображает для выбранного сеанса подробный отчет о конференции.</span><span class="sxs-lookup"><span data-stu-id="7066d-244">When you click this item, the report shows you the Conference Detail Report for the selected session.</span></span> <span data-ttu-id="7066d-245">При развертывании этого элемента отчет отображает информацию об участниках конференции.</span><span class="sxs-lookup"><span data-stu-id="7066d-245">When you expand this item, the report shows you information about the conference participants.</span></span> <span data-ttu-id="7066d-246">Дополнительные сведения приведены в разделе &quot;метрики для участников&quot; Конференции далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="7066d-246">For details, see the &quot;Metrics for Conference Participants&quot; section later in this topic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7066d-247"><strong>Organizer</strong></span><span class="sxs-lookup"><span data-stu-id="7066d-247"><strong>Organizer</strong></span></span></p></td>
<td><p><span data-ttu-id="7066d-248">Да</span><span class="sxs-lookup"><span data-stu-id="7066d-248">Yes</span></span></p></td>
<td><p><span data-ttu-id="7066d-249">SIP-адрес пользователя, организовавшего конференцию.</span><span class="sxs-lookup"><span data-stu-id="7066d-249">SIP address of the user who organized the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7066d-250"><strong>Ресурсов</strong></span><span class="sxs-lookup"><span data-stu-id="7066d-250"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="7066d-251">Да</span><span class="sxs-lookup"><span data-stu-id="7066d-251">Yes</span></span></p></td>
<td><p><span data-ttu-id="7066d-252">Имя используемого в конференции пограничного сервера (при его наличии).</span><span class="sxs-lookup"><span data-stu-id="7066d-252">Name of the Edge Server (if any) used in the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7066d-253"><strong>Start time</strong> (Время начала)</span><span class="sxs-lookup"><span data-stu-id="7066d-253"><strong>Start time</strong></span></span></p></td>
<td><p><span data-ttu-id="7066d-254">Да</span><span class="sxs-lookup"><span data-stu-id="7066d-254">Yes</span></span></p></td>
<td><p><span data-ttu-id="7066d-255">Дата и время начала конференции.</span><span class="sxs-lookup"><span data-stu-id="7066d-255">Date and time that the conference began.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7066d-256"><strong>End time</strong> (Время окончания)</span><span class="sxs-lookup"><span data-stu-id="7066d-256"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="7066d-257">Да</span><span class="sxs-lookup"><span data-stu-id="7066d-257">Yes</span></span></p></td>
<td><p><span data-ttu-id="7066d-258">Дата и время завершения конференции.</span><span class="sxs-lookup"><span data-stu-id="7066d-258">Date and time that the conference ended.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conference-participants"></a><span data-ttu-id="7066d-259">Метрики для участников конференции</span><span class="sxs-lookup"><span data-stu-id="7066d-259">Metrics for conference participants</span></span>

<span data-ttu-id="7066d-260">В следующей таблице приведены сведения из отчета об активности пользователей для каждого из участников конференции.</span><span class="sxs-lookup"><span data-stu-id="7066d-260">The following table lists the information provided in the User Activity Report provides for each participant in a conference.</span></span>

### <a name="metrics-for-conference-participants"></a><span data-ttu-id="7066d-261">Метрики для участников конференции</span><span class="sxs-lookup"><span data-stu-id="7066d-261">Metrics for conference participants</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7066d-262">Имя</span><span class="sxs-lookup"><span data-stu-id="7066d-262">Name</span></span></th>
<th><span data-ttu-id="7066d-263">Возможность сортировки по этому показателю</span><span class="sxs-lookup"><span data-stu-id="7066d-263">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="7066d-264">Описание</span><span class="sxs-lookup"><span data-stu-id="7066d-264">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7066d-265"><strong>Роль</strong></span><span class="sxs-lookup"><span data-stu-id="7066d-265"><strong>Role</strong></span></span></p></td>
<td><p><span data-ttu-id="7066d-266">Нет</span><span class="sxs-lookup"><span data-stu-id="7066d-266">No</span></span></p></td>
<td><p><span data-ttu-id="7066d-267">Роль (например, выступающий) пользователя на конференции.</span><span class="sxs-lookup"><span data-stu-id="7066d-267">Conference role (for example, Presenter) for the user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7066d-268"><strong>Участник</strong></span><span class="sxs-lookup"><span data-stu-id="7066d-268"><strong>Participant</strong></span></span></p></td>
<td><p><span data-ttu-id="7066d-269">Нет</span><span class="sxs-lookup"><span data-stu-id="7066d-269">No</span></span></p></td>
<td><p><span data-ttu-id="7066d-270">Адрес SIP пользователя.</span><span class="sxs-lookup"><span data-stu-id="7066d-270">SIP address of the user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7066d-271"><strong>Подключение</strong></span><span class="sxs-lookup"><span data-stu-id="7066d-271"><strong>Connectivity</strong></span></span></p></td>
<td><p><span data-ttu-id="7066d-272">Нет</span><span class="sxs-lookup"><span data-stu-id="7066d-272">No</span></span></p></td>
<td><p><span data-ttu-id="7066d-273">Тип подключения к сети.</span><span class="sxs-lookup"><span data-stu-id="7066d-273">Network connection type.</span></span> <span data-ttu-id="7066d-274">Например, &quot;из внутреннего&quot; для внутреннего или &quot;от PSTN&quot; для пользователей с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="7066d-274">For example &quot;From Internal&quot; for internal connection or &quot;From PSTN&quot; for dial-in users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7066d-275"><strong>Join time</strong> (Время присоединения)</span><span class="sxs-lookup"><span data-stu-id="7066d-275"><strong>Join time</strong></span></span></p></td>
<td><p><span data-ttu-id="7066d-276">Нет</span><span class="sxs-lookup"><span data-stu-id="7066d-276">No</span></span></p></td>
<td><p><span data-ttu-id="7066d-277">Дата и время присоединения пользователя к конференции.</span><span class="sxs-lookup"><span data-stu-id="7066d-277">Date and time that the user joined the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7066d-278"><strong>Leave time</strong> (Время ухода)</span><span class="sxs-lookup"><span data-stu-id="7066d-278"><strong>Leave time</strong></span></span></p></td>
<td><p><span data-ttu-id="7066d-279">Нет</span><span class="sxs-lookup"><span data-stu-id="7066d-279">No</span></span></p></td>
<td><p><span data-ttu-id="7066d-280">Дата и время покидания пользователем конференции.</span><span class="sxs-lookup"><span data-stu-id="7066d-280">Date and time that the user left the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7066d-281"><strong>Diagnostic ID</strong> (Идентификатор диагностики)</span><span class="sxs-lookup"><span data-stu-id="7066d-281"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="7066d-282">Нет</span><span class="sxs-lookup"><span data-stu-id="7066d-282">No</span></span></p></td>
<td><p><span data-ttu-id="7066d-p125">Уникальный идентификатор (в форме заголовка ms-diagnostics), присоединенный к сообщению SIP, который часто содержит сведения, помогающий устранять ошибки. Диагностические заголовки являются необязательными (можно иметь сеансы SIP, не включающие эти заголовки), и диагностические идентификаторы сообщаются только для тех сеансов, которые испытывали какие-либо проблемы.</span><span class="sxs-lookup"><span data-stu-id="7066d-p125">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

