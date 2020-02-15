---
title: 'Lync Server 2013: сводный отчет по конференциям'
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
ms.openlocfilehash: d2c31c614298112b91874882df1e4945845b74bd
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046322"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conference-summary-subreport-in-lync-server-2013"></a><span data-ttu-id="27c0a-102">Сводный отчет по конференциям в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="27c0a-102">Conference Summary Subreport in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="27c0a-103">_**Последнее изменение темы:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="27c0a-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="27c0a-p101">Вложенный сводный отчет о конференции содержит обзор неудачных сеансов конференц-связи. Такие неудачные сеансы дополнительно делятся по типу — сеансы Focus и сеансы MCU.</span><span class="sxs-lookup"><span data-stu-id="27c0a-p101">The Conference Summary Subreport provides an overall view of failed conference sessions. These failed sessions are further broken down by session type: Focus sessions and MCU sessions.</span></span>

<div>

## <a name="filters"></a><span data-ttu-id="27c0a-106">Фильтры</span><span class="sxs-lookup"><span data-stu-id="27c0a-106">Filters</span></span>

<span data-ttu-id="27c0a-p102">Фильтры позволяют вам возвратить уточненный набор данных или просматривать возвращенные данные различными способами. В следующей таблице перечислены фильтры, которые вы можете использовать во вложенном сводном отчете о конференции.</span><span class="sxs-lookup"><span data-stu-id="27c0a-p102">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the Conference Summary Subreport.</span></span>

### <a name="conference-summary-subreport-filters"></a><span data-ttu-id="27c0a-109">Фильтры вложенного сводного отчета о конференции</span><span class="sxs-lookup"><span data-stu-id="27c0a-109">Conference Summary Subreport Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="27c0a-110">Имя</span><span class="sxs-lookup"><span data-stu-id="27c0a-110">Name</span></span></th>
<th><span data-ttu-id="27c0a-111">Описание</span><span class="sxs-lookup"><span data-stu-id="27c0a-111">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="27c0a-112"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="27c0a-112"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="27c0a-p103">Дата и время начала диапазона. Чтобы просмотреть данные по часам, введите дату и время начала в следующем формате:</span><span class="sxs-lookup"><span data-stu-id="27c0a-p103">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="27c0a-115">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="27c0a-115">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="27c0a-p104">Если не указать время начала, автоматически будет выбрано время 00:00 указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</span><span class="sxs-lookup"><span data-stu-id="27c0a-p104">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="27c0a-118">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="27c0a-118">7/7/2012</span></span></p>
<p><span data-ttu-id="27c0a-119">Для просмотра по неделям или по месяцам введите дату, выпадающую на любой день недели или месяца, который вы хотите просмотреть (это необязательно должен быть первый день недели или месяца):</span><span class="sxs-lookup"><span data-stu-id="27c0a-119">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="27c0a-120">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="27c0a-120">7/3/2012</span></span></p>
<p><span data-ttu-id="27c0a-121">Неделя всегда начинается с воскресенья и заканчивается субботой.</span><span class="sxs-lookup"><span data-stu-id="27c0a-121">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27c0a-122"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="27c0a-122"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="27c0a-p105">Дата и время окончания диапазона. Чтобы просмотреть данные по часам, введите дату и время окончания в следующем формате:</span><span class="sxs-lookup"><span data-stu-id="27c0a-p105">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="27c0a-125">7/7/2012 13:00.</span><span class="sxs-lookup"><span data-stu-id="27c0a-125">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="27c0a-p106">Если не указать время окончания, автоматически будет выбрано время 00:00 указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</span><span class="sxs-lookup"><span data-stu-id="27c0a-p106">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="27c0a-128">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="27c0a-128">7/7/2012</span></span></p>
<p><span data-ttu-id="27c0a-129">Для просмотра по неделям или по месяцам введите дату, выпадающую на любой день недели или месяца, который вы хотите просмотреть (это необязательно должен быть первый день недели или месяца):</span><span class="sxs-lookup"><span data-stu-id="27c0a-129">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="27c0a-130">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="27c0a-130">7/3/2012</span></span></p>
<p><span data-ttu-id="27c0a-131">Неделя всегда начинается с воскресения и заканчивается субботой.</span><span class="sxs-lookup"><span data-stu-id="27c0a-131">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27c0a-132"><strong>Ресурсов</strong></span><span class="sxs-lookup"><span data-stu-id="27c0a-132"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="27c0a-p107">Полное доменное имя пула Регистраторов или пограничного сервера. Вы можете выбрать отдельный пул или щелкнуть элемент <strong>[All]</strong> (Все) для просмотра данных из всех пулов. Этот раскрывающийся список заполняется автоматически на основании записей в базе данных.</span><span class="sxs-lookup"><span data-stu-id="27c0a-p107">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="27c0a-136">Метрик</span><span class="sxs-lookup"><span data-stu-id="27c0a-136">Metrics</span></span>

<span data-ttu-id="27c0a-137">В следующей таблице перечислены сведения, представленные во вложенном сводном отчете о конференции.</span><span class="sxs-lookup"><span data-stu-id="27c0a-137">The following table lists the information provided in the Conference Summary Subreport.</span></span>

### <a name="conference-summary-subreport-metrics"></a><span data-ttu-id="27c0a-138">Метрики вложенного сводного отчета о конференции</span><span class="sxs-lookup"><span data-stu-id="27c0a-138">Conference Summary Subreport Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="27c0a-139">Имя</span><span class="sxs-lookup"><span data-stu-id="27c0a-139">Name</span></span></th>
<th><span data-ttu-id="27c0a-140">Возможность сортировки по этому показателю</span><span class="sxs-lookup"><span data-stu-id="27c0a-140">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="27c0a-141">Описание</span><span class="sxs-lookup"><span data-stu-id="27c0a-141">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="27c0a-142"><strong>Total conferences</strong> (Всего конференций)</span><span class="sxs-lookup"><span data-stu-id="27c0a-142"><strong>Total conferences</strong></span></span></p></td>
<td><p><span data-ttu-id="27c0a-143">Нет</span><span class="sxs-lookup"><span data-stu-id="27c0a-143">No</span></span></p></td>
<td><p><span data-ttu-id="27c0a-144">Общее количество проведенных конференций.</span><span class="sxs-lookup"><span data-stu-id="27c0a-144">Total number of conferences held.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27c0a-145"><strong>Total conference sessions</strong> (Всего сеансов конференций)</span><span class="sxs-lookup"><span data-stu-id="27c0a-145"><strong>Total conference sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="27c0a-146">Нет</span><span class="sxs-lookup"><span data-stu-id="27c0a-146">No</span></span></p></td>
<td><p><span data-ttu-id="27c0a-p108">Общее количество сеансов конференций. Отдельная конференция может иметь несколько сеансов; например, конференция может включать в себя как сеанс Focus, так и сеанс MCU.</span><span class="sxs-lookup"><span data-stu-id="27c0a-p108">Total number of conference sessions. A single conference can have multiple sessions; for example, a conference might include both a Focus session and an MCU session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27c0a-149"><strong>Overall session failure rate</strong> (Общий уровень сбоев сеансов)</span><span class="sxs-lookup"><span data-stu-id="27c0a-149"><strong>Overall session failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="27c0a-150">Нет</span><span class="sxs-lookup"><span data-stu-id="27c0a-150">No</span></span></p></td>
<td><p><span data-ttu-id="27c0a-151">Процентное отношение всех конференций, завершившихся со сбоем.</span><span class="sxs-lookup"><span data-stu-id="27c0a-151">Percentage of all conferences that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27c0a-152"><strong>Focus sessions</strong> (Сеансы Focus)</span><span class="sxs-lookup"><span data-stu-id="27c0a-152"><strong>Focus sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="27c0a-153">Нет</span><span class="sxs-lookup"><span data-stu-id="27c0a-153">No</span></span></p></td>
<td><p><span data-ttu-id="27c0a-154">Общее количество сеансов Focus.</span><span class="sxs-lookup"><span data-stu-id="27c0a-154">Total number of Focus sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27c0a-155"><strong>Focus failure rate</strong> (Уровень сбоев Focus)</span><span class="sxs-lookup"><span data-stu-id="27c0a-155"><strong>Focus failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="27c0a-156">Нет</span><span class="sxs-lookup"><span data-stu-id="27c0a-156">No</span></span></p></td>
<td><p><span data-ttu-id="27c0a-157">Процентное отношение сеансов Focus, завершившихся со сбоем.</span><span class="sxs-lookup"><span data-stu-id="27c0a-157">Percentage of Focus sessions that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27c0a-158">MCU sessions (Сеансы с MCU)</span><span class="sxs-lookup"><span data-stu-id="27c0a-158">MCU sessions</span></span></p></td>
<td><p><span data-ttu-id="27c0a-159">Нет</span><span class="sxs-lookup"><span data-stu-id="27c0a-159">No</span></span></p></td>
<td><p><span data-ttu-id="27c0a-160">Общее количество сеансов MCU.</span><span class="sxs-lookup"><span data-stu-id="27c0a-160">Total number of MCU sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27c0a-161"><strong>MCU failure rate</strong> (Уровень сбоев MCU)</span><span class="sxs-lookup"><span data-stu-id="27c0a-161"><strong>MCU failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="27c0a-162">Нет</span><span class="sxs-lookup"><span data-stu-id="27c0a-162">No</span></span></p></td>
<td><p><span data-ttu-id="27c0a-163">Процентное отношение сеансов MCU, завершившихся со сбоем.</span><span class="sxs-lookup"><span data-stu-id="27c0a-163">Percentage of MCU sessions that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27c0a-164"><strong>MCU sessions by modality</strong> (Сеансы MCU по модальности)</span><span class="sxs-lookup"><span data-stu-id="27c0a-164"><strong>MCU sessions by modality</strong></span></span></p></td>
<td><p><span data-ttu-id="27c0a-165">Нет</span><span class="sxs-lookup"><span data-stu-id="27c0a-165">No</span></span></p></td>
<td><p><span data-ttu-id="27c0a-166">Общее количество сеансов MCU, сгруппированных по модальности (например, конференции с обменом мгновенными сообщениями).</span><span class="sxs-lookup"><span data-stu-id="27c0a-166">Total number of MCU sessions, grouped by modality (for example, IM conferencing).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27c0a-167"><strong>Failure rate by modality</strong> (Уровень сбоев по модальности)</span><span class="sxs-lookup"><span data-stu-id="27c0a-167"><strong>Failure rate by modality</strong></span></span></p></td>
<td><p><span data-ttu-id="27c0a-168">Нет</span><span class="sxs-lookup"><span data-stu-id="27c0a-168">No</span></span></p></td>
<td><p><span data-ttu-id="27c0a-169">Процентное отношение неудачных сеансов MCU, сгруппированных по модальности (например, конференции с обменом мгновенными сообщениями).</span><span class="sxs-lookup"><span data-stu-id="27c0a-169">Percentage of MCU sessions that failed, grouped by modality (for example, IM conferencing).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

