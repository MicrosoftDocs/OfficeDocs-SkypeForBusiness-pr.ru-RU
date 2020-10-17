---
title: 'Lync Server 2013: сводный сводный отчет P2P'
description: 'Lync Server 2013: сводный сводный отчет P2P.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: P2P Summary Subreport
ms:assetid: fc36185a-3cc5-4167-8c93-8a755fa75ac7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205416(v=OCS.15)
ms:contentKeyID: 48185950
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eda51e76c4ed7b62535a2a2e4ab52982aa6381f3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557385"
---
# <a name="p2p-summary-subreport-in-lync-server-2013"></a><span data-ttu-id="e470c-103">Сводный сводный отчет P2P в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e470c-103">P2P Summary Subreport in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e470c-104">_**Последнее изменение темы:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="e470c-104">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="e470c-105">Вложенный сводный отчет по одноранговым подключениям содержит общий обзор одноранговых сеансов связи, завершившихся с ошибками.</span><span class="sxs-lookup"><span data-stu-id="e470c-105">The P2P Summary Subreport provides an overall view of your failed peer-to-peer communication sessions.</span></span>

<div>

## <a name="filters"></a><span data-ttu-id="e470c-106">Фильтры</span><span class="sxs-lookup"><span data-stu-id="e470c-106">Filters</span></span>

<span data-ttu-id="e470c-p101">Фильтры позволяют возвращать более точный набор данных или различными способами просматривать возвращенные данные. В следующей таблице представлены фильтры, которые вы можете использовать со сводным вложенным отчетом P2P.</span><span class="sxs-lookup"><span data-stu-id="e470c-p101">Filters provide a way for you to return a more finely targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the P2P Summary Subreport.</span></span>

### <a name="p2p-summary-subreport-filters"></a><span data-ttu-id="e470c-109">Фильтры вложенного сводного отчета по одноранговым подключениям</span><span class="sxs-lookup"><span data-stu-id="e470c-109">P2P Summary Subreport Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e470c-110">Имя</span><span class="sxs-lookup"><span data-stu-id="e470c-110">Name</span></span></th>
<th><span data-ttu-id="e470c-111">Описание</span><span class="sxs-lookup"><span data-stu-id="e470c-111">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e470c-112"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="e470c-112"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="e470c-p102">Начальные дата и время временного диапазона. Чтобы просмотреть данные по часам, введите начальные дату и время следующим образом:</span><span class="sxs-lookup"><span data-stu-id="e470c-p102">Start date and time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="e470c-115">7/7/2012 13:00.</span><span class="sxs-lookup"><span data-stu-id="e470c-115">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="e470c-p103">Если не указать время начала, автоматически будет выбрано время 00:00 указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</span><span class="sxs-lookup"><span data-stu-id="e470c-p103">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="e470c-118">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="e470c-118">7/7/2012</span></span></p>
<p><span data-ttu-id="e470c-119">Для просмотра по неделям или по месяцам введите дату, выпадающую на любой день недели или месяца, который вы хотите просмотреть (это необязательно должен быть первый день недели или месяца):</span><span class="sxs-lookup"><span data-stu-id="e470c-119">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="e470c-120">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="e470c-120">7/3/2012</span></span></p>
<p><span data-ttu-id="e470c-121">Неделя всегда начинается с воскресения и заканчивается субботой.</span><span class="sxs-lookup"><span data-stu-id="e470c-121">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e470c-122"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="e470c-122"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="e470c-p104">Конечные дата и время временного диапазона. Чтобы просмотреть данные по часам, введите конечные дату и время следующим образом:</span><span class="sxs-lookup"><span data-stu-id="e470c-p104">End date and time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="e470c-125">7/7/2012 13:00.</span><span class="sxs-lookup"><span data-stu-id="e470c-125">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="e470c-p105">Если не указать время окончания, автоматически будет выбрано время 00:00 указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</span><span class="sxs-lookup"><span data-stu-id="e470c-p105">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="e470c-128">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="e470c-128">7/7/2012</span></span></p>
<p><span data-ttu-id="e470c-129">Для просмотра по неделям или по месяцам введите дату, выпадающую на любой день недели или месяца, который вы хотите просмотреть (это необязательно должен быть первый день недели или месяца):</span><span class="sxs-lookup"><span data-stu-id="e470c-129">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="e470c-130">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="e470c-130">7/3/2012</span></span></p>
<p><span data-ttu-id="e470c-131">Неделя всегда начинается с воскресения и заканчивается субботой.</span><span class="sxs-lookup"><span data-stu-id="e470c-131">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e470c-132"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="e470c-132"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="e470c-p106">Полное доменное имя пула Регистраторов или пограничного сервера. Вы можете выбрать отдельный пул или щелкнуть элемент <strong>[All]</strong> (Все) для просмотра данных из всех пулов. Этот раскрывающийся список заполняется автоматически на основании записей в базе данных.</span><span class="sxs-lookup"><span data-stu-id="e470c-p106">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="e470c-136">Метрики</span><span class="sxs-lookup"><span data-stu-id="e470c-136">Metrics</span></span>

<span data-ttu-id="e470c-137">Следующая таблица содержит сведения, приведенные во вложенном сводном отчете по одноранговым подключениям.</span><span class="sxs-lookup"><span data-stu-id="e470c-137">The following table lists the information provided in the P2P Summary Subreport.</span></span>

### <a name="p2p-summary-subreport-metrics"></a><span data-ttu-id="e470c-138">Метрики вложенного сводного отчета по одноранговым подключениям</span><span class="sxs-lookup"><span data-stu-id="e470c-138">P2P Summary Subreport Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e470c-139">Имя</span><span class="sxs-lookup"><span data-stu-id="e470c-139">Name</span></span></th>
<th><span data-ttu-id="e470c-140">Возможность сортировки по этому показателю</span><span class="sxs-lookup"><span data-stu-id="e470c-140">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="e470c-141">Описание</span><span class="sxs-lookup"><span data-stu-id="e470c-141">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e470c-142"><strong> Всего сеансов </strong></span><span class="sxs-lookup"><span data-stu-id="e470c-142"><strong>Total sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="e470c-143">Нет</span><span class="sxs-lookup"><span data-stu-id="e470c-143">No</span></span></p></td>
<td><p><span data-ttu-id="e470c-144">Общее число сеансов, включая успешные и завершившиеся сбоем (как ожидаемые, так и непредвиденные сбои) и сеансы без категорий.</span><span class="sxs-lookup"><span data-stu-id="e470c-144">Total number of sessions, including successful sessions, failed sessions (both expected failures and unexpected failures), and uncategorized sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e470c-145"><strong>Процент сбоев</strong></span><span class="sxs-lookup"><span data-stu-id="e470c-145"><strong>Failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="e470c-146">Нет</span><span class="sxs-lookup"><span data-stu-id="e470c-146">No</span></span></p></td>
<td><p><span data-ttu-id="e470c-147">Доля одноранговых сеансов, завершившихся сбоем.</span><span class="sxs-lookup"><span data-stu-id="e470c-147">Percentage of peer-to-peer sessions that failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e470c-148"><strong>Sessions by Modality</strong> (Сеансы по модальности)</span><span class="sxs-lookup"><span data-stu-id="e470c-148"><strong>Sessions by Modality</strong></span></span></p></td>
<td><p><span data-ttu-id="e470c-149">Нет</span><span class="sxs-lookup"><span data-stu-id="e470c-149">No</span></span></p></td>
<td><p><span data-ttu-id="e470c-150">Общее число сеансов, сгруппированных по модальности (например, обмен мгновенными сообщениями).</span><span class="sxs-lookup"><span data-stu-id="e470c-150">Total number of sessions grouped by modality (for example, instant messaging).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e470c-151"><strong>Failure rate by modality</strong> (Процент сбоев по модальности)</span><span class="sxs-lookup"><span data-stu-id="e470c-151"><strong>Failure rate by modality</strong></span></span></p></td>
<td><p><span data-ttu-id="e470c-152">Нет</span><span class="sxs-lookup"><span data-stu-id="e470c-152">No</span></span></p></td>
<td><p><span data-ttu-id="e470c-153">Общее число неудачных сеансов, сгруппированных по модальности (например, обмен мгновенными сообщениями).</span><span class="sxs-lookup"><span data-stu-id="e470c-153">Total number of failed sessions grouped by modality (for example, instant messaging).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

