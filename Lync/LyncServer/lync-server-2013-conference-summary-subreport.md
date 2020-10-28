---
title: 'Lync Server 2013: сводный отчет по конференциям'
description: 'Lync Server 2013: сводный отчет по конференциям.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conference Summary Subreport
ms:assetid: 2fc1d2bf-34f5-4093-a6e2-250ec1f1b004
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204779(v=OCS.15)
ms:contentKeyID: 48183742
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0612ce1adb8a6b0fdea5e3bf70b88346f7c08044
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550695"
---
# <a name="conference-summary-subreport-in-lync-server-2013"></a><span data-ttu-id="7ff26-103">Сводный отчет по конференциям в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7ff26-103">Conference Summary Subreport in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7ff26-104">_**Последнее изменение темы:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="7ff26-104">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="7ff26-p101">Вложенный сводный отчет о конференции содержит обзор неудачных сеансов конференц-связи. Такие неудачные сеансы дополнительно делятся по типу — сеансы Focus и сеансы MCU.</span><span class="sxs-lookup"><span data-stu-id="7ff26-p101">The Conference Summary Subreport provides an overall view of failed conference sessions. These failed sessions are further broken down by session type: Focus sessions and MCU sessions.</span></span>

<div>

## <a name="filters"></a><span data-ttu-id="7ff26-107">Фильтры</span><span class="sxs-lookup"><span data-stu-id="7ff26-107">Filters</span></span>

<span data-ttu-id="7ff26-p102">Фильтры позволяют вам возвратить уточненный набор данных или просматривать возвращенные данные различными способами. В следующей таблице перечислены фильтры, которые вы можете использовать во вложенном сводном отчете о конференции.</span><span class="sxs-lookup"><span data-stu-id="7ff26-p102">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the Conference Summary Subreport.</span></span>

### <a name="conference-summary-subreport-filters"></a><span data-ttu-id="7ff26-110">Фильтры вложенного сводного отчета о конференции</span><span class="sxs-lookup"><span data-stu-id="7ff26-110">Conference Summary Subreport Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7ff26-111">Имя</span><span class="sxs-lookup"><span data-stu-id="7ff26-111">Name</span></span></th>
<th><span data-ttu-id="7ff26-112">Описание</span><span class="sxs-lookup"><span data-stu-id="7ff26-112">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7ff26-113"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="7ff26-113"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="7ff26-p103">Дата и время начала диапазона. Чтобы просмотреть данные по часам, введите дату и время начала в следующем формате:</span><span class="sxs-lookup"><span data-stu-id="7ff26-p103">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="7ff26-116">7/7/2012 13:00.</span><span class="sxs-lookup"><span data-stu-id="7ff26-116">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="7ff26-p104">Если не указать время начала, автоматически будет выбрано время 00:00 указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</span><span class="sxs-lookup"><span data-stu-id="7ff26-p104">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="7ff26-119">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="7ff26-119">7/7/2012</span></span></p>
<p><span data-ttu-id="7ff26-120">Для просмотра по неделям или по месяцам введите дату, выпадающую на любой день недели или месяца, который вы хотите просмотреть (это необязательно должен быть первый день недели или месяца):</span><span class="sxs-lookup"><span data-stu-id="7ff26-120">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="7ff26-121">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="7ff26-121">7/3/2012</span></span></p>
<p><span data-ttu-id="7ff26-122">Неделя всегда начинается с воскресения и заканчивается субботой.</span><span class="sxs-lookup"><span data-stu-id="7ff26-122">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7ff26-123"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="7ff26-123"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="7ff26-p105">Дата и время окончания диапазона. Чтобы просмотреть данные по часам, введите дату и время окончания в следующем формате:</span><span class="sxs-lookup"><span data-stu-id="7ff26-p105">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="7ff26-126">7/7/2012 13:00.</span><span class="sxs-lookup"><span data-stu-id="7ff26-126">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="7ff26-p106">Если не указать время окончания, автоматически будет выбрано время 00:00 указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</span><span class="sxs-lookup"><span data-stu-id="7ff26-p106">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="7ff26-129">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="7ff26-129">7/7/2012</span></span></p>
<p><span data-ttu-id="7ff26-130">Для просмотра по неделям или по месяцам введите дату, выпадающую на любой день недели или месяца, который вы хотите просмотреть (это необязательно должен быть первый день недели или месяца):</span><span class="sxs-lookup"><span data-stu-id="7ff26-130">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="7ff26-131">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="7ff26-131">7/3/2012</span></span></p>
<p><span data-ttu-id="7ff26-132">Неделя всегда начинается с воскресения и заканчивается субботой.</span><span class="sxs-lookup"><span data-stu-id="7ff26-132">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7ff26-133"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="7ff26-133"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="7ff26-p107">Полное доменное имя пула Регистраторов или пограничного сервера. Вы можете выбрать отдельный пул или щелкнуть элемент <strong>[All]</strong> (Все) для просмотра данных из всех пулов. Этот раскрывающийся список заполняется автоматически на основании записей в базе данных.</span><span class="sxs-lookup"><span data-stu-id="7ff26-p107">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="7ff26-137">Метрики</span><span class="sxs-lookup"><span data-stu-id="7ff26-137">Metrics</span></span>

<span data-ttu-id="7ff26-138">В следующей таблице перечислены сведения, представленные во вложенном сводном отчете о конференции.</span><span class="sxs-lookup"><span data-stu-id="7ff26-138">The following table lists the information provided in the Conference Summary Subreport.</span></span>

### <a name="conference-summary-subreport-metrics"></a><span data-ttu-id="7ff26-139">Метрики вложенного сводного отчета о конференции</span><span class="sxs-lookup"><span data-stu-id="7ff26-139">Conference Summary Subreport Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7ff26-140">Имя</span><span class="sxs-lookup"><span data-stu-id="7ff26-140">Name</span></span></th>
<th><span data-ttu-id="7ff26-141">Возможность сортировки по этому показателю</span><span class="sxs-lookup"><span data-stu-id="7ff26-141">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="7ff26-142">Описание</span><span class="sxs-lookup"><span data-stu-id="7ff26-142">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7ff26-143"><strong>Total conferences</strong> (Всего конференций)</span><span class="sxs-lookup"><span data-stu-id="7ff26-143"><strong>Total conferences</strong></span></span></p></td>
<td><p><span data-ttu-id="7ff26-144">Нет</span><span class="sxs-lookup"><span data-stu-id="7ff26-144">No</span></span></p></td>
<td><p><span data-ttu-id="7ff26-145">Общее количество проведенных конференций.</span><span class="sxs-lookup"><span data-stu-id="7ff26-145">Total number of conferences held.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7ff26-146"><strong>Total conference sessions</strong> (Всего сеансов конференций)</span><span class="sxs-lookup"><span data-stu-id="7ff26-146"><strong>Total conference sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="7ff26-147">Нет</span><span class="sxs-lookup"><span data-stu-id="7ff26-147">No</span></span></p></td>
<td><p><span data-ttu-id="7ff26-p108">Общее количество сеансов конференций. Отдельная конференция может иметь несколько сеансов; например, конференция может включать в себя как сеанс Focus, так и сеанс MCU.</span><span class="sxs-lookup"><span data-stu-id="7ff26-p108">Total number of conference sessions. A single conference can have multiple sessions; for example, a conference might include both a Focus session and an MCU session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7ff26-150"><strong>Overall session failure rate</strong> (Общий уровень сбоев сеансов)</span><span class="sxs-lookup"><span data-stu-id="7ff26-150"><strong>Overall session failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="7ff26-151">Нет</span><span class="sxs-lookup"><span data-stu-id="7ff26-151">No</span></span></p></td>
<td><p><span data-ttu-id="7ff26-152">Процентное отношение всех конференций, завершившихся со сбоем.</span><span class="sxs-lookup"><span data-stu-id="7ff26-152">Percentage of all conferences that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7ff26-153"><strong>Focus sessions</strong> (Сеансы Focus)</span><span class="sxs-lookup"><span data-stu-id="7ff26-153"><strong>Focus sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="7ff26-154">Нет</span><span class="sxs-lookup"><span data-stu-id="7ff26-154">No</span></span></p></td>
<td><p><span data-ttu-id="7ff26-155">Общее количество сеансов Focus.</span><span class="sxs-lookup"><span data-stu-id="7ff26-155">Total number of Focus sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7ff26-156"><strong>Focus failure rate</strong> (Уровень сбоев Focus)</span><span class="sxs-lookup"><span data-stu-id="7ff26-156"><strong>Focus failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="7ff26-157">Нет</span><span class="sxs-lookup"><span data-stu-id="7ff26-157">No</span></span></p></td>
<td><p><span data-ttu-id="7ff26-158">Процентное отношение сеансов Focus, завершившихся со сбоем.</span><span class="sxs-lookup"><span data-stu-id="7ff26-158">Percentage of Focus sessions that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7ff26-159">MCU sessions (Сеансы с MCU)</span><span class="sxs-lookup"><span data-stu-id="7ff26-159">MCU sessions</span></span></p></td>
<td><p><span data-ttu-id="7ff26-160">Нет</span><span class="sxs-lookup"><span data-stu-id="7ff26-160">No</span></span></p></td>
<td><p><span data-ttu-id="7ff26-161">Общее количество сеансов MCU.</span><span class="sxs-lookup"><span data-stu-id="7ff26-161">Total number of MCU sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7ff26-162"><strong>MCU failure rate</strong> (Уровень сбоев MCU)</span><span class="sxs-lookup"><span data-stu-id="7ff26-162"><strong>MCU failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="7ff26-163">Нет</span><span class="sxs-lookup"><span data-stu-id="7ff26-163">No</span></span></p></td>
<td><p><span data-ttu-id="7ff26-164">Процентное отношение сеансов MCU, завершившихся со сбоем.</span><span class="sxs-lookup"><span data-stu-id="7ff26-164">Percentage of MCU sessions that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7ff26-165"><strong>MCU sessions by modality</strong> (Сеансы MCU по модальности)</span><span class="sxs-lookup"><span data-stu-id="7ff26-165"><strong>MCU sessions by modality</strong></span></span></p></td>
<td><p><span data-ttu-id="7ff26-166">Нет</span><span class="sxs-lookup"><span data-stu-id="7ff26-166">No</span></span></p></td>
<td><p><span data-ttu-id="7ff26-167">Общее количество сеансов MCU, сгруппированных по модальности (например, конференции с обменом мгновенными сообщениями).</span><span class="sxs-lookup"><span data-stu-id="7ff26-167">Total number of MCU sessions, grouped by modality (for example, IM conferencing).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7ff26-168"><strong>Failure rate by modality</strong> (Уровень сбоев по модальности)</span><span class="sxs-lookup"><span data-stu-id="7ff26-168"><strong>Failure rate by modality</strong></span></span></p></td>
<td><p><span data-ttu-id="7ff26-169">Нет</span><span class="sxs-lookup"><span data-stu-id="7ff26-169">No</span></span></p></td>
<td><p><span data-ttu-id="7ff26-170">Процентное отношение неудачных сеансов MCU, сгруппированных по модальности (например, конференции с обменом мгновенными сообщениями).</span><span class="sxs-lookup"><span data-stu-id="7ff26-170">Percentage of MCU sessions that failed, grouped by modality (for example, IM conferencing).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

