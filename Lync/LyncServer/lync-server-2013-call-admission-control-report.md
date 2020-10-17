---
title: 'Lync Server 2013: отчет по контролю допуска звонков'
description: 'Lync Server 2013: отчет по контролю допуска звонков.'
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
ms.openlocfilehash: 8764e51603e7097095894bc1230c2a2bb1126b9c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572365"
---
# <a name="call-admission-control-report-in-lync-server-2013"></a><span data-ttu-id="0d080-103">Отчет по контролю допуска звонков в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0d080-103">Call Admission Control Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0d080-104">_**Последнее изменение темы:** 2012-06-29_</span><span class="sxs-lookup"><span data-stu-id="0d080-104">_**Topic Last Modified:** 2012-06-29_</span></span>

<span data-ttu-id="0d080-105">Отчет по контролю допуска звонков (Call Admission Control Report) предоставляет сведения об одноранговых сеансах и сеансах конференц-связи, которые были проведены в рамках ограничений, установленных на месте контролем допуска звонков.</span><span class="sxs-lookup"><span data-stu-id="0d080-105">The Call Admission Control Report provides information about peer-to-peer and conferencing sessions that were conducted under restrictions set in place by Call Admission Control.</span></span> <span data-ttu-id="0d080-106">Контроль допуска звонков, представленный в Microsoft Lync Server 2010, позволяет администраторам разрешать или запрещать сеансы связи на основе ограничений полосы пропускания.</span><span class="sxs-lookup"><span data-stu-id="0d080-106">Call Admission Control, introduced in Microsoft Lync Server 2010, provides a way for administrators to allow (or not allow) communication sessions based on bandwidth constraints.</span></span> <span data-ttu-id="0d080-107">Например, администраторы могут создать политики, которые налагают ограничение на величину пропускной способности, доступный для голосовых вызовов и видеовызовов.</span><span class="sxs-lookup"><span data-stu-id="0d080-107">For example, administrators can create policies that impose a limit on the amount of bandwidth available for voice and video calls.</span></span> <span data-ttu-id="0d080-108">Если это ограничение пропускной способности достигается, то до завершения текущих вызовов и освобождения необходимых сетевых ресурсов перестают размещаться какие-либо новые вызовы.</span><span class="sxs-lookup"><span data-stu-id="0d080-108">If that bandwidth limit has been reached, then no new voice or video calls can be placed until one of the current calls has ended and freed up the required network resources.</span></span>

<div>

## <a name="accessing-the-call-admission-control-report"></a><span data-ttu-id="0d080-109">Доступ к отчету по контролю допуска звонков</span><span class="sxs-lookup"><span data-stu-id="0d080-109">Accessing the Call Admission Control Report</span></span>

<span data-ttu-id="0d080-p102">Отчет по контролю допуска звонков можно вызвать на домашней странице отчетов мониторинга. Из отчета по контролю допуска звонков можно перейти в следующие отчеты.</span><span class="sxs-lookup"><span data-stu-id="0d080-p102">The Call Admission Control Report is accessed from the Monitoring Reports home page. From the Call Admission Control Report you can drill down to either of the following reports:</span></span>

  - <span data-ttu-id="0d080-112">Отчет по деталям конференции — чтобы вызвать этот отчет, нажмите метрику Детали в сеансе конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="0d080-112">Conference Detail Report – To access this report, click the Details metric from a conference session.</span></span>

  - <span data-ttu-id="0d080-113">Отчет по деталям однорангового сеанса — чтобы вызвать этот отчет, нажмите метрику Детали для однорангового сеанса.</span><span class="sxs-lookup"><span data-stu-id="0d080-113">Peer-to-Peer Session Detail Report – To access this report, click the Details metric for a peer-to-peer session.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-call-admission-control-report"></a><span data-ttu-id="0d080-114">Оптимальное использование отчета по контролю допуска звонков</span><span class="sxs-lookup"><span data-stu-id="0d080-114">Making the Best Use of the Call Admission Control Report</span></span>

<span data-ttu-id="0d080-p103">Чтобы получить полный список вызовов, отклоненных из-за недостаточной пропускной способности, выберите пункт "Вызовы, отклоненные контролем допуска звонков" в раскрывающемся списке категорий вызова. Большая часть отклоненных звонков скорее всего будет иметь диагностический идентификатор 5:</span><span class="sxs-lookup"><span data-stu-id="0d080-p103">To get a list of calls that failed because of insufficient bandwidth, select Calls rejected because of call admission control from the Call category dropdown list. Most of the returned calls will likely have a diagnostic ID of 5:</span></span>

<span data-ttu-id="0d080-p104">Недостаточная пропускная способность для установки сеанса. Попытка перенаправить в ТСОП.</span><span class="sxs-lookup"><span data-stu-id="0d080-p104">Insufficient bandwidth to establish session. Attempt PSTN re-route.</span></span>

<span data-ttu-id="0d080-119">Это указывает, что ограничения контроля допуска звонков запретили выполнение этого вызова в сети VoIP.</span><span class="sxs-lookup"><span data-stu-id="0d080-119">That indicates that Call Admission Control limitations were preventing the call from being made on the VoIP network.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="0d080-120">Фильтры</span><span class="sxs-lookup"><span data-stu-id="0d080-120">Filters</span></span>

<span data-ttu-id="0d080-p105">Фильтры позволяют получать более адресный набор данных или просматривать полученные данные разными способами. Например, контроль допуска звонков позволяет фильтровать вызовы по вызывающему пользователю или по вызываемому пользователю. Можно также выбрать способ группирования данных. В этом случае вызовы группируются по часу, дню, неделе или месяцу.</span><span class="sxs-lookup"><span data-stu-id="0d080-p105">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Call Admission Control Report enables you to filter calls by the user who initiated the call or by the user who was being called. You can also choose how data should be grouped. In this case, calls are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="0d080-125">В следующей таблице приведены фильтры, которые можно использовать в отчете по контролю допуска звонков.</span><span class="sxs-lookup"><span data-stu-id="0d080-125">The following table lists the filters that you can use with the Call Admission Control Report.</span></span>

### <a name="call-admission-control-report-filters"></a><span data-ttu-id="0d080-126">Фильтры отчета по контролю допуска звонков</span><span class="sxs-lookup"><span data-stu-id="0d080-126">Call Admission Control Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0d080-127">Имя</span><span class="sxs-lookup"><span data-stu-id="0d080-127">Name</span></span></th>
<th><span data-ttu-id="0d080-128">Описание</span><span class="sxs-lookup"><span data-stu-id="0d080-128">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0d080-129"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="0d080-129"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="0d080-p106">Дата и время начала диапазона времени. Чтобы просматривать данные по часам, введите дату и время начала:</span><span class="sxs-lookup"><span data-stu-id="0d080-p106">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="0d080-132">17.07.12 13:00</span><span class="sxs-lookup"><span data-stu-id="0d080-132">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="0d080-p107">Если вы не вводите начальное время, отчет автоматически начинается с 24:00 указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</span><span class="sxs-lookup"><span data-stu-id="0d080-p107">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="0d080-135">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="0d080-135">7/17/12012</span></span></p>
<p><span data-ttu-id="0d080-136">Чтобы просматривать данные по неделям или месяцам, введите дату, попадающую в интересующую неделю или месяц (не обязательно указывать первый день недели или месяца):</span><span class="sxs-lookup"><span data-stu-id="0d080-136">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="0d080-137">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="0d080-137">7/13/2012</span></span></p>
<p><span data-ttu-id="0d080-138">Недели всегда продолжаются с воскресенья по субботу.</span><span class="sxs-lookup"><span data-stu-id="0d080-138">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d080-139"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="0d080-139"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="0d080-p108">Дата и время конца диапазона времени. Чтобы просматривать данные по часам, введите дату и время окончания:</span><span class="sxs-lookup"><span data-stu-id="0d080-p108">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="0d080-142">17.07.12 13:00</span><span class="sxs-lookup"><span data-stu-id="0d080-142">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="0d080-p109">Если вы не вводите конечное время, отчет автоматически заканчивается в 24:00 указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</span><span class="sxs-lookup"><span data-stu-id="0d080-p109">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="0d080-145">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="0d080-145">7/17/12012</span></span></p>
<p><span data-ttu-id="0d080-146">Чтобы просматривать данные по неделям или месяцам, введите дату, попадающую в интересующую неделю или месяц (не обязательно указывать первый день недели или месяца):</span><span class="sxs-lookup"><span data-stu-id="0d080-146">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="0d080-147">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="0d080-147">7/13/2012</span></span></p>
<p><span data-ttu-id="0d080-148">Недели всегда продолжаются с воскресенья по субботу.</span><span class="sxs-lookup"><span data-stu-id="0d080-148">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0d080-149"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="0d080-149"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="0d080-p110">Полное доменное имя пула регистратора или пограничного сервера. Можно выбрать отдельный пул или нажать <strong>[Все]</strong>, чтобы просмотреть данные для всех пулов. Этот раскрывающийся список автоматически заполняется на основе записей в базе данных.</span><span class="sxs-lookup"><span data-stu-id="0d080-p110">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d080-153"><strong>Тип действия</strong></span><span class="sxs-lookup"><span data-stu-id="0d080-153"><strong>Activity type</strong></span></span></p></td>
<td><p><span data-ttu-id="0d080-p111">Тип действия. Выберите одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="0d080-p111">Type of activity. Select one of the following activities:</span></span></p>
<ul>
<li><p><span data-ttu-id="0d080-156">Ко</span><span class="sxs-lookup"><span data-stu-id="0d080-156">[All]</span></span></p></li>
<li><p><span data-ttu-id="0d080-157">Одноранговая сеть</span><span class="sxs-lookup"><span data-stu-id="0d080-157">Peer-to-Peer</span></span></p></li>
<li><p><span data-ttu-id="0d080-158">Conference</span><span class="sxs-lookup"><span data-stu-id="0d080-158">Conference</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0d080-159"><strong>Категория вызова</strong></span><span class="sxs-lookup"><span data-stu-id="0d080-159"><strong>Call category</strong></span></span></p></td>
<td><p><span data-ttu-id="0d080-p112">Указывает причину, которую контроль допуска звонков использовал для вызова. Выберите один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="0d080-p112">Indicates the reason that CAC was used for the call. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="0d080-162">Ко</span><span class="sxs-lookup"><span data-stu-id="0d080-162">[All]</span></span></p></li>
<li><p><span data-ttu-id="0d080-163">Вызов отклонен контролем допуска звонков</span><span class="sxs-lookup"><span data-stu-id="0d080-163">Call rejected because of call admission control</span></span></p></li>
<li><p><span data-ttu-id="0d080-164">Вызовы перенаправлены через ТСОП вследствие контроля допуска звонков</span><span class="sxs-lookup"><span data-stu-id="0d080-164">Calls rerouted through PSTN because of call admission control</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="0d080-165">Метрики для одноранговых сеансов</span><span class="sxs-lookup"><span data-stu-id="0d080-165">Metrics for Peer-to-Peer Sessions</span></span>

<span data-ttu-id="0d080-166">В следующей таблице приведены сведения, предоставляемые отчетом по контролю допуска звонков для одноранговых сеансов (т.е. сеансов, в которых только два участника).</span><span class="sxs-lookup"><span data-stu-id="0d080-166">The following table lists the information provided in the Call Admission Control Report for peer-to-peer sessions (that is, sessions involving just two participants).</span></span>

### <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="0d080-167">Метрики для одноранговых сеансов</span><span class="sxs-lookup"><span data-stu-id="0d080-167">Metrics for Peer-to-Peer Sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0d080-168">Имя</span><span class="sxs-lookup"><span data-stu-id="0d080-168">Name</span></span></th>
<th><span data-ttu-id="0d080-169">Возможность сортировки по этому показателю</span><span class="sxs-lookup"><span data-stu-id="0d080-169">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="0d080-170">Описание</span><span class="sxs-lookup"><span data-stu-id="0d080-170">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0d080-171"><strong>Detail</strong></span><span class="sxs-lookup"><span data-stu-id="0d080-171"><strong>Detail</strong></span></span></p></td>
<td><p><span data-ttu-id="0d080-172">Нет</span><span class="sxs-lookup"><span data-stu-id="0d080-172">No</span></span></p></td>
<td><p><span data-ttu-id="0d080-173">При нажатии этой метрики появится отчет по деталям однорангового сеанса для указанного сеанса.</span><span class="sxs-lookup"><span data-stu-id="0d080-173">When you click this item, the report shows you a Peer-to-Peer Session Detail Report for the specified session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d080-174"><strong>FПользователь-инициатор</strong></span><span class="sxs-lookup"><span data-stu-id="0d080-174"><strong>From user</strong></span></span></p></td>
<td><p><span data-ttu-id="0d080-175">Да</span><span class="sxs-lookup"><span data-stu-id="0d080-175">Yes</span></span></p></td>
<td><p><span data-ttu-id="0d080-176">SIP-адрес пользователя, начавшего сеанс.</span><span class="sxs-lookup"><span data-stu-id="0d080-176">SIP address of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0d080-177"><strong>Пользователь-получатель</strong></span><span class="sxs-lookup"><span data-stu-id="0d080-177"><strong>To user</strong></span></span></p></td>
<td><p><span data-ttu-id="0d080-178">Да</span><span class="sxs-lookup"><span data-stu-id="0d080-178">Yes</span></span></p></td>
<td><p><span data-ttu-id="0d080-179">SIP-адрес пользователя, приглашенного принять участие в сеансе.</span><span class="sxs-lookup"><span data-stu-id="0d080-179">SIP address of the user who was invited to join the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d080-180"><strong>Модальности</strong></span><span class="sxs-lookup"><span data-stu-id="0d080-180"><strong>Modalities</strong></span></span></p></td>
<td><p><span data-ttu-id="0d080-181">Да</span><span class="sxs-lookup"><span data-stu-id="0d080-181">Yes</span></span></p></td>
<td><p><span data-ttu-id="0d080-182">Модальности взаимодействия (например звук и видео), использовавшиеся во время сеанса.</span><span class="sxs-lookup"><span data-stu-id="0d080-182">Communication modalities (such as audio and video) that were used during the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0d080-183"><strong>Время приглашения</strong></span><span class="sxs-lookup"><span data-stu-id="0d080-183"><strong>Invite time</strong></span></span></p></td>
<td><p><span data-ttu-id="0d080-184">Да</span><span class="sxs-lookup"><span data-stu-id="0d080-184">Yes</span></span></p></td>
<td><p><span data-ttu-id="0d080-185">Дата и время отправки пользователем-инициатором исходного приглашения принять участие в сеансе.</span><span class="sxs-lookup"><span data-stu-id="0d080-185">Date and time the initial session invitation was sent to the From user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d080-186"><strong>Время ответа</strong></span><span class="sxs-lookup"><span data-stu-id="0d080-186"><strong>Response time</strong></span></span></p></td>
<td><p><span data-ttu-id="0d080-187">Да</span><span class="sxs-lookup"><span data-stu-id="0d080-187">Yes</span></span></p></td>
<td><p><span data-ttu-id="0d080-188">Дата и время, когда было получено принятие приглашения.</span><span class="sxs-lookup"><span data-stu-id="0d080-188">Date and time that the invitation acceptance was received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0d080-189"><strong>Время окончания</strong></span><span class="sxs-lookup"><span data-stu-id="0d080-189"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="0d080-190">Да</span><span class="sxs-lookup"><span data-stu-id="0d080-190">Yes</span></span></p></td>
<td><p><span data-ttu-id="0d080-191">Дата и время окончания сеанса.</span><span class="sxs-lookup"><span data-stu-id="0d080-191">Date and time that the session ended.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d080-192"><strong>ИД диагностики</strong></span><span class="sxs-lookup"><span data-stu-id="0d080-192"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="0d080-193">Да</span><span class="sxs-lookup"><span data-stu-id="0d080-193">Yes</span></span></p></td>
<td><p><span data-ttu-id="0d080-p113">Уникальный идентификатор (в форме заголовка ms-diagnostics), присоединенный к сообщению SIP, который часто содержит сведения, помогающий устранять ошибки. Диагностические заголовки являются необязательными (можно иметь сеансы SIP, не включающие эти заголовки), и диагностические идентификаторы сообщаются только для тех сеансов, которые испытывали какие-либо проблемы.</span><span class="sxs-lookup"><span data-stu-id="0d080-p113">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="0d080-196">Метрики для сеансов конференц-связи</span><span class="sxs-lookup"><span data-stu-id="0d080-196">Metrics for Conferencing Sessions</span></span>

<span data-ttu-id="0d080-197">В следующей таблице приведены сведения, которые предоставляются в отчете по контролю допуска звонков для сеансов конференц-связи (т.е. сеансов, в которых не менее трех участников).</span><span class="sxs-lookup"><span data-stu-id="0d080-197">The following table lists the information provided in the Call Admission Control Report for conferencing sessions (that is, sessions involving three or more participants).</span></span>

### <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="0d080-198">Метрики для сеансов конференц-связи</span><span class="sxs-lookup"><span data-stu-id="0d080-198">Metrics for Conferencing Sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0d080-199">Имя</span><span class="sxs-lookup"><span data-stu-id="0d080-199">Name</span></span></th>
<th><span data-ttu-id="0d080-200">Возможность сортировки по этому показателю</span><span class="sxs-lookup"><span data-stu-id="0d080-200">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="0d080-201">Описание</span><span class="sxs-lookup"><span data-stu-id="0d080-201">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0d080-202"><strong>Conference URI</strong> (URI конференции)</span><span class="sxs-lookup"><span data-stu-id="0d080-202"><strong>Conference URI</strong></span></span></p></td>
<td><p><span data-ttu-id="0d080-203">Да</span><span class="sxs-lookup"><span data-stu-id="0d080-203">Yes</span></span></p></td>
<td><p><span data-ttu-id="0d080-p114">Уникальный идентификатор конференции. Если нажать этот элемент, будут отображены отдельные участники конференции.</span><span class="sxs-lookup"><span data-stu-id="0d080-p114">Unique identifier for the conference. When you click this item, the report shows the individual conference participants.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d080-206"><strong>Organizer</strong></span><span class="sxs-lookup"><span data-stu-id="0d080-206"><strong>Organizer</strong></span></span></p></td>
<td><p><span data-ttu-id="0d080-207">Да</span><span class="sxs-lookup"><span data-stu-id="0d080-207">Yes</span></span></p></td>
<td><p><span data-ttu-id="0d080-208">SIP-адрес пользователя, организовавшего конференцию.</span><span class="sxs-lookup"><span data-stu-id="0d080-208">SIP address of the user who organized the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0d080-209"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="0d080-209"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="0d080-210">Да</span><span class="sxs-lookup"><span data-stu-id="0d080-210">Yes</span></span></p></td>
<td><p><span data-ttu-id="0d080-211">пограничный сервер, использовавшийся в конференции.</span><span class="sxs-lookup"><span data-stu-id="0d080-211">Edge Server used in the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d080-212"><strong>Время начала</strong></span><span class="sxs-lookup"><span data-stu-id="0d080-212"><strong>Start time</strong></span></span></p></td>
<td><p><span data-ttu-id="0d080-213">Да</span><span class="sxs-lookup"><span data-stu-id="0d080-213">Yes</span></span></p></td>
<td><p><span data-ttu-id="0d080-214">Дата и время начала конференции.</span><span class="sxs-lookup"><span data-stu-id="0d080-214">Date and time that the conference started.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0d080-215"><strong>Время окончания</strong></span><span class="sxs-lookup"><span data-stu-id="0d080-215"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="0d080-216">Да</span><span class="sxs-lookup"><span data-stu-id="0d080-216">Yes</span></span></p></td>
<td><p><span data-ttu-id="0d080-217">Дата и время окончания конференции.</span><span class="sxs-lookup"><span data-stu-id="0d080-217">Date and time that the conference ended.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-individual-conference-participants"></a><span data-ttu-id="0d080-218">Метрики для отдельных участников конференции</span><span class="sxs-lookup"><span data-stu-id="0d080-218">Metrics for Individual Conference Participants</span></span>

<span data-ttu-id="0d080-219">В следующей таблице приведены сведения, которые предоставляются в отчете по контролю допуска звонков для отдельных участников конференции.</span><span class="sxs-lookup"><span data-stu-id="0d080-219">The following table lists the information provided in the Call Admission Control Report for individual conference participants.</span></span>

### <a name="metrics-for-individual-conference-participants"></a><span data-ttu-id="0d080-220">Метрики для отдельных участников конференции</span><span class="sxs-lookup"><span data-stu-id="0d080-220">Metrics for Individual Conference Participants</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0d080-221">Имя</span><span class="sxs-lookup"><span data-stu-id="0d080-221">Name</span></span></th>
<th><span data-ttu-id="0d080-222">Возможность сортировки по этому показателю</span><span class="sxs-lookup"><span data-stu-id="0d080-222">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="0d080-223">Описание</span><span class="sxs-lookup"><span data-stu-id="0d080-223">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0d080-224"><strong>Role</strong></span><span class="sxs-lookup"><span data-stu-id="0d080-224"><strong>Role</strong></span></span></p></td>
<td><p><span data-ttu-id="0d080-225">Нет</span><span class="sxs-lookup"><span data-stu-id="0d080-225">No</span></span></p></td>
<td><p><span data-ttu-id="0d080-226">Роль (например, докладчик), которую играл участник конференции.</span><span class="sxs-lookup"><span data-stu-id="0d080-226">Role (for example, Presenter) played by the conference participant.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d080-227"><strong>Участник</strong></span><span class="sxs-lookup"><span data-stu-id="0d080-227"><strong>Participant</strong></span></span></p></td>
<td><p><span data-ttu-id="0d080-228">Нет</span><span class="sxs-lookup"><span data-stu-id="0d080-228">No</span></span></p></td>
<td><p><span data-ttu-id="0d080-229">SIP-адрес участника конференции.</span><span class="sxs-lookup"><span data-stu-id="0d080-229">SIP address of the conference participant.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0d080-230"><strong>Подключение</strong></span><span class="sxs-lookup"><span data-stu-id="0d080-230"><strong>Connectivity</strong></span></span></p></td>
<td><p><span data-ttu-id="0d080-231">Нет</span><span class="sxs-lookup"><span data-stu-id="0d080-231">No</span></span></p></td>
<td><p><span data-ttu-id="0d080-232">Подключение участника к сети, обычно из внутренней сети или из внешней сети.</span><span class="sxs-lookup"><span data-stu-id="0d080-232">Network connectivity (typically From Internal or From External) for the participant.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d080-233"><strong>Модальности</strong></span><span class="sxs-lookup"><span data-stu-id="0d080-233"><strong>Modality</strong></span></span></p></td>
<td><p><span data-ttu-id="0d080-234">Нет</span><span class="sxs-lookup"><span data-stu-id="0d080-234">No</span></span></p></td>
<td><p><span data-ttu-id="0d080-235">Тип конференции (например, аудио- и видеоконференция).</span><span class="sxs-lookup"><span data-stu-id="0d080-235">Conference type (for example, A/V conferencing).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0d080-236"><strong>Время присоединения</strong></span><span class="sxs-lookup"><span data-stu-id="0d080-236"><strong>Join time</strong></span></span></p></td>
<td><p><span data-ttu-id="0d080-237">Нет</span><span class="sxs-lookup"><span data-stu-id="0d080-237">No</span></span></p></td>
<td><p><span data-ttu-id="0d080-238">Дата и время присоединения участника к конференции.</span><span class="sxs-lookup"><span data-stu-id="0d080-238">Date and time that the participant joined the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d080-239"><strong>Leave time</strong> (Время ухода)</span><span class="sxs-lookup"><span data-stu-id="0d080-239"><strong>Leave time</strong></span></span></p></td>
<td><p><span data-ttu-id="0d080-240">Нет</span><span class="sxs-lookup"><span data-stu-id="0d080-240">No</span></span></p></td>
<td><p><span data-ttu-id="0d080-241">Дата и время, когда участник покинул конференцию.</span><span class="sxs-lookup"><span data-stu-id="0d080-241">Date and time that the participant left the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0d080-242"><strong>ИД диагностики</strong></span><span class="sxs-lookup"><span data-stu-id="0d080-242"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="0d080-243">Нет</span><span class="sxs-lookup"><span data-stu-id="0d080-243">No</span></span></p></td>
<td><p><span data-ttu-id="0d080-p115">Уникальный идентификатор (в форме заголовка ms-diagnostics), присоединенный к сообщению SIP, который часто содержит сведения, помогающий устранять ошибки. Диагностические заголовки являются необязательными (можно иметь сеансы SIP, не включающие эти заголовки), и диагностические идентификаторы сообщаются только для тех сеансов, которые испытывали какие-либо проблемы.</span><span class="sxs-lookup"><span data-stu-id="0d080-p115">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

