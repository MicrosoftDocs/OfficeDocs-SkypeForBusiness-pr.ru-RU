---
title: 'Lync Server 2013: отчет по контролю допуска звонков'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call Admission Control Report
ms:assetid: ea4b0c9f-7f93-4b8a-b901-01e1636c44fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615043(v=OCS.15)
ms:contentKeyID: 48185933
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 46d61e01574945fe090d3fd9425133f9569bd111
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42199542"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="call-admission-control-report-in-lync-server-2013"></a><span data-ttu-id="e26e1-102">Отчет по контролю допуска звонков в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e26e1-102">Call Admission Control Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e26e1-103">_**Последнее изменение темы:** 2012-06-29_</span><span class="sxs-lookup"><span data-stu-id="e26e1-103">_**Topic Last Modified:** 2012-06-29_</span></span>

<span data-ttu-id="e26e1-104">Отчет по контролю допуска звонков (Call Admission Control Report) предоставляет сведения об одноранговых сеансах и сеансах конференц-связи, которые были проведены в рамках ограничений, установленных на месте контролем допуска звонков.</span><span class="sxs-lookup"><span data-stu-id="e26e1-104">The Call Admission Control Report provides information about peer-to-peer and conferencing sessions that were conducted under restrictions set in place by Call Admission Control.</span></span> <span data-ttu-id="e26e1-105">Контроль допуска звонков, представленный в Microsoft Lync Server 2010, позволяет администраторам разрешать или запрещать сеансы связи на основе ограничений полосы пропускания.</span><span class="sxs-lookup"><span data-stu-id="e26e1-105">Call Admission Control, introduced in Microsoft Lync Server 2010, provides a way for administrators to allow (or not allow) communication sessions based on bandwidth constraints.</span></span> <span data-ttu-id="e26e1-106">Например, администраторы могут создать политики, которые налагают ограничение на величину пропускной способности, доступный для голосовых вызовов и видеовызовов.</span><span class="sxs-lookup"><span data-stu-id="e26e1-106">For example, administrators can create policies that impose a limit on the amount of bandwidth available for voice and video calls.</span></span> <span data-ttu-id="e26e1-107">Если это ограничение пропускной способности достигается, то до завершения текущих вызовов и освобождения необходимых сетевых ресурсов перестают размещаться какие-либо новые вызовы.</span><span class="sxs-lookup"><span data-stu-id="e26e1-107">If that bandwidth limit has been reached, then no new voice or video calls can be placed until one of the current calls has ended and freed up the required network resources.</span></span>

<div>

## <a name="accessing-the-call-admission-control-report"></a><span data-ttu-id="e26e1-108">Доступ к отчету по контролю допуска звонков</span><span class="sxs-lookup"><span data-stu-id="e26e1-108">Accessing the Call Admission Control Report</span></span>

<span data-ttu-id="e26e1-p102">Отчет по контролю допуска звонков можно вызвать на домашней странице отчетов мониторинга. Из отчета по контролю допуска звонков можно перейти в следующие отчеты.</span><span class="sxs-lookup"><span data-stu-id="e26e1-p102">The Call Admission Control Report is accessed from the Monitoring Reports home page. From the Call Admission Control Report you can drill down to either of the following reports:</span></span>

  - <span data-ttu-id="e26e1-111">Отчет по деталям конференции — чтобы вызвать этот отчет, нажмите метрику Детали в сеансе конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="e26e1-111">Conference Detail Report – To access this report, click the Details metric from a conference session.</span></span>

  - <span data-ttu-id="e26e1-112">Отчет по деталям однорангового сеанса — чтобы вызвать этот отчет, нажмите метрику Детали для однорангового сеанса.</span><span class="sxs-lookup"><span data-stu-id="e26e1-112">Peer-to-Peer Session Detail Report – To access this report, click the Details metric for a peer-to-peer session.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-call-admission-control-report"></a><span data-ttu-id="e26e1-113">Оптимальное использование отчета по контролю допуска звонков</span><span class="sxs-lookup"><span data-stu-id="e26e1-113">Making the Best Use of the Call Admission Control Report</span></span>

<span data-ttu-id="e26e1-p103">Чтобы получить полный список вызовов, отклоненных из-за недостаточной пропускной способности, выберите пункт "Вызовы, отклоненные контролем допуска звонков" в раскрывающемся списке категорий вызова. Большая часть отклоненных звонков скорее всего будет иметь диагностический идентификатор 5:</span><span class="sxs-lookup"><span data-stu-id="e26e1-p103">To get a list of calls that failed because of insufficient bandwidth, select Calls rejected because of call admission control from the Call category dropdown list. Most of the returned calls will likely have a diagnostic ID of 5:</span></span>

<span data-ttu-id="e26e1-p104">Недостаточная пропускная способность для установки сеанса. Попытка перенаправить в ТСОП.</span><span class="sxs-lookup"><span data-stu-id="e26e1-p104">Insufficient bandwidth to establish session. Attempt PSTN re-route.</span></span>

<span data-ttu-id="e26e1-118">Это указывает, что ограничения контроля допуска звонков запретили выполнение этого вызова в сети VoIP.</span><span class="sxs-lookup"><span data-stu-id="e26e1-118">That indicates that Call Admission Control limitations were preventing the call from being made on the VoIP network.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="e26e1-119">Фильтры</span><span class="sxs-lookup"><span data-stu-id="e26e1-119">Filters</span></span>

<span data-ttu-id="e26e1-p105">Фильтры позволяют получать более адресный набор данных или просматривать полученные данные разными способами. Например, контроль допуска звонков позволяет фильтровать вызовы по вызывающему пользователю или по вызываемому пользователю. Можно также выбрать способ группирования данных. В этом случае вызовы группируются по часу, дню, неделе или месяцу.</span><span class="sxs-lookup"><span data-stu-id="e26e1-p105">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Call Admission Control Report enables you to filter calls by the user who initiated the call or by the user who was being called. You can also choose how data should be grouped. In this case, calls are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="e26e1-124">В следующей таблице приведены фильтры, которые можно использовать в отчете по контролю допуска звонков.</span><span class="sxs-lookup"><span data-stu-id="e26e1-124">The following table lists the filters that you can use with the Call Admission Control Report.</span></span>

### <a name="call-admission-control-report-filters"></a><span data-ttu-id="e26e1-125">Фильтры отчета по контролю допуска звонков</span><span class="sxs-lookup"><span data-stu-id="e26e1-125">Call Admission Control Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e26e1-126">Имя</span><span class="sxs-lookup"><span data-stu-id="e26e1-126">Name</span></span></th>
<th><span data-ttu-id="e26e1-127">Описание</span><span class="sxs-lookup"><span data-stu-id="e26e1-127">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e26e1-128"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="e26e1-128"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="e26e1-p106">Дата и время начала диапазона времени. Чтобы просматривать данные по часам, введите дату и время начала:</span><span class="sxs-lookup"><span data-stu-id="e26e1-p106">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="e26e1-131">17.07.12 13:00</span><span class="sxs-lookup"><span data-stu-id="e26e1-131">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="e26e1-p107">Если вы не вводите начальное время, отчет автоматически начинается с 24:00 указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</span><span class="sxs-lookup"><span data-stu-id="e26e1-p107">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="e26e1-134">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="e26e1-134">7/17/12012</span></span></p>
<p><span data-ttu-id="e26e1-135">Чтобы просматривать данные по неделям или месяцам, введите дату, попадающую в интересующую неделю или месяц (не обязательно указывать первый день недели или месяца):</span><span class="sxs-lookup"><span data-stu-id="e26e1-135">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="e26e1-136">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="e26e1-136">7/13/2012</span></span></p>
<p><span data-ttu-id="e26e1-137">Неделя всегда начинается с воскресенья и заканчивается субботой.</span><span class="sxs-lookup"><span data-stu-id="e26e1-137">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e26e1-138"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="e26e1-138"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="e26e1-p108">Дата и время конца диапазона времени. Чтобы просматривать данные по часам, введите дату и время окончания:</span><span class="sxs-lookup"><span data-stu-id="e26e1-p108">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="e26e1-141">17.07.12 13:00</span><span class="sxs-lookup"><span data-stu-id="e26e1-141">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="e26e1-p109">Если вы не вводите конечное время, отчет автоматически заканчивается в 24:00 указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</span><span class="sxs-lookup"><span data-stu-id="e26e1-p109">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="e26e1-144">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="e26e1-144">7/17/12012</span></span></p>
<p><span data-ttu-id="e26e1-145">Чтобы просматривать данные по неделям или месяцам, введите дату, попадающую в интересующую неделю или месяц (не обязательно указывать первый день недели или месяца):</span><span class="sxs-lookup"><span data-stu-id="e26e1-145">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="e26e1-146">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="e26e1-146">7/13/2012</span></span></p>
<p><span data-ttu-id="e26e1-147">Недели всегда продолжаются с воскресенья по субботу.</span><span class="sxs-lookup"><span data-stu-id="e26e1-147">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e26e1-148"><strong>Ресурсов</strong></span><span class="sxs-lookup"><span data-stu-id="e26e1-148"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="e26e1-p110">Полное доменное имя пула регистратора или пограничного сервера. Можно выбрать отдельный пул или нажать <strong>[Все]</strong>, чтобы просмотреть данные для всех пулов. Этот раскрывающийся список автоматически заполняется на основе записей в базе данных.</span><span class="sxs-lookup"><span data-stu-id="e26e1-p110">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e26e1-152"><strong>Тип действия</strong></span><span class="sxs-lookup"><span data-stu-id="e26e1-152"><strong>Activity type</strong></span></span></p></td>
<td><p><span data-ttu-id="e26e1-p111">Тип действия. Выберите одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="e26e1-p111">Type of activity. Select one of the following activities:</span></span></p>
<ul>
<li><p><span data-ttu-id="e26e1-155">Ко</span><span class="sxs-lookup"><span data-stu-id="e26e1-155">[All]</span></span></p></li>
<li><p><span data-ttu-id="e26e1-156">Одноранговая сеть</span><span class="sxs-lookup"><span data-stu-id="e26e1-156">Peer-to-Peer</span></span></p></li>
<li><p><span data-ttu-id="e26e1-157">Встречи</span><span class="sxs-lookup"><span data-stu-id="e26e1-157">Conference</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e26e1-158"><strong>Категория вызова</strong></span><span class="sxs-lookup"><span data-stu-id="e26e1-158"><strong>Call category</strong></span></span></p></td>
<td><p><span data-ttu-id="e26e1-p112">Указывает причину, которую контроль допуска звонков использовал для вызова. Выберите один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="e26e1-p112">Indicates the reason that CAC was used for the call. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="e26e1-161">Ко</span><span class="sxs-lookup"><span data-stu-id="e26e1-161">[All]</span></span></p></li>
<li><p><span data-ttu-id="e26e1-162">Вызов отклонен контролем допуска звонков</span><span class="sxs-lookup"><span data-stu-id="e26e1-162">Call rejected because of call admission control</span></span></p></li>
<li><p><span data-ttu-id="e26e1-163">Вызовы перенаправлены через ТСОП вследствие контроля допуска звонков</span><span class="sxs-lookup"><span data-stu-id="e26e1-163">Calls rerouted through PSTN because of call admission control</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="e26e1-164">Метрики для одноранговых сеансов</span><span class="sxs-lookup"><span data-stu-id="e26e1-164">Metrics for Peer-to-Peer Sessions</span></span>

<span data-ttu-id="e26e1-165">В следующей таблице приведены сведения, предоставляемые отчетом по контролю допуска звонков для одноранговых сеансов (т.е. сеансов, в которых только два участника).</span><span class="sxs-lookup"><span data-stu-id="e26e1-165">The following table lists the information provided in the Call Admission Control Report for peer-to-peer sessions (that is, sessions involving just two participants).</span></span>

### <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="e26e1-166">Метрики для одноранговых сеансов</span><span class="sxs-lookup"><span data-stu-id="e26e1-166">Metrics for Peer-to-Peer Sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e26e1-167">Имя</span><span class="sxs-lookup"><span data-stu-id="e26e1-167">Name</span></span></th>
<th><span data-ttu-id="e26e1-168">Возможность сортировки по этому показателю</span><span class="sxs-lookup"><span data-stu-id="e26e1-168">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="e26e1-169">Описание</span><span class="sxs-lookup"><span data-stu-id="e26e1-169">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e26e1-170"><strong>Detail</strong></span><span class="sxs-lookup"><span data-stu-id="e26e1-170"><strong>Detail</strong></span></span></p></td>
<td><p><span data-ttu-id="e26e1-171">Нет</span><span class="sxs-lookup"><span data-stu-id="e26e1-171">No</span></span></p></td>
<td><p><span data-ttu-id="e26e1-172">При нажатии этой метрики появится отчет по деталям однорангового сеанса для указанного сеанса.</span><span class="sxs-lookup"><span data-stu-id="e26e1-172">When you click this item, the report shows you a Peer-to-Peer Session Detail Report for the specified session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e26e1-173"><strong>FПользователь-инициатор</strong></span><span class="sxs-lookup"><span data-stu-id="e26e1-173"><strong>From user</strong></span></span></p></td>
<td><p><span data-ttu-id="e26e1-174">Да</span><span class="sxs-lookup"><span data-stu-id="e26e1-174">Yes</span></span></p></td>
<td><p><span data-ttu-id="e26e1-175">SIP-адрес пользователя, начавшего сеанс.</span><span class="sxs-lookup"><span data-stu-id="e26e1-175">SIP address of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e26e1-176"><strong>Пользователь-получатель</strong></span><span class="sxs-lookup"><span data-stu-id="e26e1-176"><strong>To user</strong></span></span></p></td>
<td><p><span data-ttu-id="e26e1-177">Да</span><span class="sxs-lookup"><span data-stu-id="e26e1-177">Yes</span></span></p></td>
<td><p><span data-ttu-id="e26e1-178">SIP-адрес пользователя, приглашенного принять участие в сеансе.</span><span class="sxs-lookup"><span data-stu-id="e26e1-178">SIP address of the user who was invited to join the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e26e1-179"><strong>Модальности</strong></span><span class="sxs-lookup"><span data-stu-id="e26e1-179"><strong>Modalities</strong></span></span></p></td>
<td><p><span data-ttu-id="e26e1-180">Да</span><span class="sxs-lookup"><span data-stu-id="e26e1-180">Yes</span></span></p></td>
<td><p><span data-ttu-id="e26e1-181">Модальности взаимодействия (например звук и видео), использовавшиеся во время сеанса.</span><span class="sxs-lookup"><span data-stu-id="e26e1-181">Communication modalities (such as audio and video) that were used during the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e26e1-182"><strong>Время приглашения</strong></span><span class="sxs-lookup"><span data-stu-id="e26e1-182"><strong>Invite time</strong></span></span></p></td>
<td><p><span data-ttu-id="e26e1-183">Да</span><span class="sxs-lookup"><span data-stu-id="e26e1-183">Yes</span></span></p></td>
<td><p><span data-ttu-id="e26e1-184">Дата и время отправки пользователем-инициатором исходного приглашения принять участие в сеансе.</span><span class="sxs-lookup"><span data-stu-id="e26e1-184">Date and time the initial session invitation was sent to the From user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e26e1-185"><strong>Время ответа</strong></span><span class="sxs-lookup"><span data-stu-id="e26e1-185"><strong>Response time</strong></span></span></p></td>
<td><p><span data-ttu-id="e26e1-186">Да</span><span class="sxs-lookup"><span data-stu-id="e26e1-186">Yes</span></span></p></td>
<td><p><span data-ttu-id="e26e1-187">Дата и время, когда было получено принятие приглашения.</span><span class="sxs-lookup"><span data-stu-id="e26e1-187">Date and time that the invitation acceptance was received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e26e1-188"><strong>End time</strong> (Время окончания)</span><span class="sxs-lookup"><span data-stu-id="e26e1-188"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="e26e1-189">Да</span><span class="sxs-lookup"><span data-stu-id="e26e1-189">Yes</span></span></p></td>
<td><p><span data-ttu-id="e26e1-190">Дата и время окончания сеанса.</span><span class="sxs-lookup"><span data-stu-id="e26e1-190">Date and time that the session ended.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e26e1-191"><strong>ИД диагностики</strong></span><span class="sxs-lookup"><span data-stu-id="e26e1-191"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="e26e1-192">Да</span><span class="sxs-lookup"><span data-stu-id="e26e1-192">Yes</span></span></p></td>
<td><p><span data-ttu-id="e26e1-p113">Уникальный идентификатор (в форме заголовка ms-diagnostics), присоединенный к сообщению SIP, который часто содержит сведения, помогающий устранять ошибки. Диагностические заголовки являются необязательными (можно иметь сеансы SIP, не включающие эти заголовки), и диагностические идентификаторы сообщаются только для тех сеансов, которые испытывали какие-либо проблемы.</span><span class="sxs-lookup"><span data-stu-id="e26e1-p113">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="e26e1-195">Метрики для сеансов конференц-связи</span><span class="sxs-lookup"><span data-stu-id="e26e1-195">Metrics for Conferencing Sessions</span></span>

<span data-ttu-id="e26e1-196">В следующей таблице приведены сведения, которые предоставляются в отчете по контролю допуска звонков для сеансов конференц-связи (т.е. сеансов, в которых не менее трех участников).</span><span class="sxs-lookup"><span data-stu-id="e26e1-196">The following table lists the information provided in the Call Admission Control Report for conferencing sessions (that is, sessions involving three or more participants).</span></span>

### <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="e26e1-197">Метрики для сеансов конференц-связи</span><span class="sxs-lookup"><span data-stu-id="e26e1-197">Metrics for Conferencing Sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e26e1-198">Имя</span><span class="sxs-lookup"><span data-stu-id="e26e1-198">Name</span></span></th>
<th><span data-ttu-id="e26e1-199">Возможность сортировки по этому показателю</span><span class="sxs-lookup"><span data-stu-id="e26e1-199">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="e26e1-200">Описание</span><span class="sxs-lookup"><span data-stu-id="e26e1-200">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e26e1-201"><strong>Conference URI</strong> (URI конференции)</span><span class="sxs-lookup"><span data-stu-id="e26e1-201"><strong>Conference URI</strong></span></span></p></td>
<td><p><span data-ttu-id="e26e1-202">Да</span><span class="sxs-lookup"><span data-stu-id="e26e1-202">Yes</span></span></p></td>
<td><p><span data-ttu-id="e26e1-p114">Уникальный идентификатор конференции. Если нажать этот элемент, будут отображены отдельные участники конференции.</span><span class="sxs-lookup"><span data-stu-id="e26e1-p114">Unique identifier for the conference. When you click this item, the report shows the individual conference participants.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e26e1-205"><strong>Organizer</strong></span><span class="sxs-lookup"><span data-stu-id="e26e1-205"><strong>Organizer</strong></span></span></p></td>
<td><p><span data-ttu-id="e26e1-206">Да</span><span class="sxs-lookup"><span data-stu-id="e26e1-206">Yes</span></span></p></td>
<td><p><span data-ttu-id="e26e1-207">SIP-адрес пользователя, организовавшего конференцию.</span><span class="sxs-lookup"><span data-stu-id="e26e1-207">SIP address of the user who organized the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e26e1-208"><strong>Ресурсов</strong></span><span class="sxs-lookup"><span data-stu-id="e26e1-208"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="e26e1-209">Да</span><span class="sxs-lookup"><span data-stu-id="e26e1-209">Yes</span></span></p></td>
<td><p><span data-ttu-id="e26e1-210">пограничный сервер, использовавшийся в конференции.</span><span class="sxs-lookup"><span data-stu-id="e26e1-210">Edge Server used in the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e26e1-211"><strong>Время начала</strong></span><span class="sxs-lookup"><span data-stu-id="e26e1-211"><strong>Start time</strong></span></span></p></td>
<td><p><span data-ttu-id="e26e1-212">Да</span><span class="sxs-lookup"><span data-stu-id="e26e1-212">Yes</span></span></p></td>
<td><p><span data-ttu-id="e26e1-213">Дата и время начала конференции.</span><span class="sxs-lookup"><span data-stu-id="e26e1-213">Date and time that the conference started.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e26e1-214"><strong>Время окончания</strong></span><span class="sxs-lookup"><span data-stu-id="e26e1-214"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="e26e1-215">Да</span><span class="sxs-lookup"><span data-stu-id="e26e1-215">Yes</span></span></p></td>
<td><p><span data-ttu-id="e26e1-216">Дата и время окончания конференции.</span><span class="sxs-lookup"><span data-stu-id="e26e1-216">Date and time that the conference ended.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-individual-conference-participants"></a><span data-ttu-id="e26e1-217">Метрики для отдельных участников конференции</span><span class="sxs-lookup"><span data-stu-id="e26e1-217">Metrics for Individual Conference Participants</span></span>

<span data-ttu-id="e26e1-218">В следующей таблице приведены сведения, которые предоставляются в отчете по контролю допуска звонков для отдельных участников конференции.</span><span class="sxs-lookup"><span data-stu-id="e26e1-218">The following table lists the information provided in the Call Admission Control Report for individual conference participants.</span></span>

### <a name="metrics-for-individual-conference-participants"></a><span data-ttu-id="e26e1-219">Метрики для отдельных участников конференции</span><span class="sxs-lookup"><span data-stu-id="e26e1-219">Metrics for Individual Conference Participants</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e26e1-220">Имя</span><span class="sxs-lookup"><span data-stu-id="e26e1-220">Name</span></span></th>
<th><span data-ttu-id="e26e1-221">Возможность сортировки по этому показателю</span><span class="sxs-lookup"><span data-stu-id="e26e1-221">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="e26e1-222">Описание</span><span class="sxs-lookup"><span data-stu-id="e26e1-222">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e26e1-223"><strong>Роль</strong></span><span class="sxs-lookup"><span data-stu-id="e26e1-223"><strong>Role</strong></span></span></p></td>
<td><p><span data-ttu-id="e26e1-224">Нет</span><span class="sxs-lookup"><span data-stu-id="e26e1-224">No</span></span></p></td>
<td><p><span data-ttu-id="e26e1-225">Роль (например, докладчик), которую играл участник конференции.</span><span class="sxs-lookup"><span data-stu-id="e26e1-225">Role (for example, Presenter) played by the conference participant.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e26e1-226"><strong>Участник</strong></span><span class="sxs-lookup"><span data-stu-id="e26e1-226"><strong>Participant</strong></span></span></p></td>
<td><p><span data-ttu-id="e26e1-227">Нет</span><span class="sxs-lookup"><span data-stu-id="e26e1-227">No</span></span></p></td>
<td><p><span data-ttu-id="e26e1-228">SIP-адрес участника конференции.</span><span class="sxs-lookup"><span data-stu-id="e26e1-228">SIP address of the conference participant.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e26e1-229"><strong>Подключение</strong></span><span class="sxs-lookup"><span data-stu-id="e26e1-229"><strong>Connectivity</strong></span></span></p></td>
<td><p><span data-ttu-id="e26e1-230">Нет</span><span class="sxs-lookup"><span data-stu-id="e26e1-230">No</span></span></p></td>
<td><p><span data-ttu-id="e26e1-231">Подключение участника к сети, обычно из внутренней сети или из внешней сети.</span><span class="sxs-lookup"><span data-stu-id="e26e1-231">Network connectivity (typically From Internal or From External) for the participant.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e26e1-232"><strong>Модальности</strong></span><span class="sxs-lookup"><span data-stu-id="e26e1-232"><strong>Modality</strong></span></span></p></td>
<td><p><span data-ttu-id="e26e1-233">Нет</span><span class="sxs-lookup"><span data-stu-id="e26e1-233">No</span></span></p></td>
<td><p><span data-ttu-id="e26e1-234">Тип конференции (например, аудио- и видеоконференция).</span><span class="sxs-lookup"><span data-stu-id="e26e1-234">Conference type (for example, A/V conferencing).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e26e1-235"><strong>Время присоединения</strong></span><span class="sxs-lookup"><span data-stu-id="e26e1-235"><strong>Join time</strong></span></span></p></td>
<td><p><span data-ttu-id="e26e1-236">Нет</span><span class="sxs-lookup"><span data-stu-id="e26e1-236">No</span></span></p></td>
<td><p><span data-ttu-id="e26e1-237">Дата и время присоединения участника к конференции.</span><span class="sxs-lookup"><span data-stu-id="e26e1-237">Date and time that the participant joined the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e26e1-238"><strong>Leave time</strong> (Время ухода)</span><span class="sxs-lookup"><span data-stu-id="e26e1-238"><strong>Leave time</strong></span></span></p></td>
<td><p><span data-ttu-id="e26e1-239">Нет</span><span class="sxs-lookup"><span data-stu-id="e26e1-239">No</span></span></p></td>
<td><p><span data-ttu-id="e26e1-240">Дата и время, когда участник покинул конференцию.</span><span class="sxs-lookup"><span data-stu-id="e26e1-240">Date and time that the participant left the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e26e1-241"><strong>ИД диагностики</strong></span><span class="sxs-lookup"><span data-stu-id="e26e1-241"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="e26e1-242">Нет</span><span class="sxs-lookup"><span data-stu-id="e26e1-242">No</span></span></p></td>
<td><p><span data-ttu-id="e26e1-p115">Уникальный идентификатор (в форме заголовка ms-diagnostics), присоединенный к сообщению SIP, который часто содержит сведения, помогающий устранять ошибки. Диагностические заголовки являются необязательными (можно иметь сеансы SIP, не включающие эти заголовки), и диагностические идентификаторы сообщаются только для тех сеансов, которые испытывали какие-либо проблемы.</span><span class="sxs-lookup"><span data-stu-id="e26e1-p115">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

