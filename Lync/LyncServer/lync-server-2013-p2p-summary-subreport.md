---
title: 'Lync Server 2013: сводный сводный отчет P2P'
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
ms.openlocfilehash: ee8b2b914779cf8fde4f1e3a58d827dd355d28e7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515996"
---
# <a name="p2p-summary-subreport-in-lync-server-2013"></a><span data-ttu-id="84dde-102">Сводный сводный отчет P2P в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="84dde-102">P2P Summary Subreport in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="84dde-103">_**Последнее изменение темы:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="84dde-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="84dde-104">Вложенный сводный отчет по одноранговым подключениям содержит общий обзор одноранговых сеансов связи, завершившихся с ошибками.</span><span class="sxs-lookup"><span data-stu-id="84dde-104">The P2P Summary Subreport provides an overall view of your failed peer-to-peer communication sessions.</span></span>

<div>

## <a name="filters"></a><span data-ttu-id="84dde-105">Фильтры</span><span class="sxs-lookup"><span data-stu-id="84dde-105">Filters</span></span>

<span data-ttu-id="84dde-p101">Фильтры позволяют возвращать более точный набор данных или различными способами просматривать возвращенные данные. В следующей таблице представлены фильтры, которые вы можете использовать со сводным вложенным отчетом P2P.</span><span class="sxs-lookup"><span data-stu-id="84dde-p101">Filters provide a way for you to return a more finely targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the P2P Summary Subreport.</span></span>

### <a name="p2p-summary-subreport-filters"></a><span data-ttu-id="84dde-108">Фильтры вложенного сводного отчета по одноранговым подключениям</span><span class="sxs-lookup"><span data-stu-id="84dde-108">P2P Summary Subreport Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="84dde-109">Имя</span><span class="sxs-lookup"><span data-stu-id="84dde-109">Name</span></span></th>
<th><span data-ttu-id="84dde-110">Описание</span><span class="sxs-lookup"><span data-stu-id="84dde-110">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="84dde-111"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="84dde-111"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="84dde-p102">Начальные дата и время временного диапазона. Чтобы просмотреть данные по часам, введите начальные дату и время следующим образом:</span><span class="sxs-lookup"><span data-stu-id="84dde-p102">Start date and time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="84dde-114">7/7/2012 13:00.</span><span class="sxs-lookup"><span data-stu-id="84dde-114">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="84dde-p103">Если не указать время начала, автоматически будет выбрано время 00:00 указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</span><span class="sxs-lookup"><span data-stu-id="84dde-p103">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="84dde-117">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="84dde-117">7/7/2012</span></span></p>
<p><span data-ttu-id="84dde-118">Для просмотра по неделям или по месяцам введите дату, выпадающую на любой день недели или месяца, который вы хотите просмотреть (это необязательно должен быть первый день недели или месяца):</span><span class="sxs-lookup"><span data-stu-id="84dde-118">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="84dde-119">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="84dde-119">7/3/2012</span></span></p>
<p><span data-ttu-id="84dde-120">Неделя всегда начинается с воскресения и заканчивается субботой.</span><span class="sxs-lookup"><span data-stu-id="84dde-120">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84dde-121"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="84dde-121"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="84dde-p104">Конечные дата и время временного диапазона. Чтобы просмотреть данные по часам, введите конечные дату и время следующим образом:</span><span class="sxs-lookup"><span data-stu-id="84dde-p104">End date and time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="84dde-124">7/7/2012 13:00.</span><span class="sxs-lookup"><span data-stu-id="84dde-124">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="84dde-p105">Если не указать время окончания, автоматически будет выбрано время 00:00 указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</span><span class="sxs-lookup"><span data-stu-id="84dde-p105">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="84dde-127">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="84dde-127">7/7/2012</span></span></p>
<p><span data-ttu-id="84dde-128">Для просмотра по неделям или по месяцам введите дату, выпадающую на любой день недели или месяца, который вы хотите просмотреть (это необязательно должен быть первый день недели или месяца):</span><span class="sxs-lookup"><span data-stu-id="84dde-128">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="84dde-129">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="84dde-129">7/3/2012</span></span></p>
<p><span data-ttu-id="84dde-130">Неделя всегда начинается с воскресения и заканчивается субботой.</span><span class="sxs-lookup"><span data-stu-id="84dde-130">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84dde-131"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="84dde-131"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="84dde-p106">Полное доменное имя пула Регистраторов или пограничного сервера. Вы можете выбрать отдельный пул или щелкнуть элемент <strong>[All]</strong> (Все) для просмотра данных из всех пулов. Этот раскрывающийся список заполняется автоматически на основании записей в базе данных.</span><span class="sxs-lookup"><span data-stu-id="84dde-p106">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="84dde-135">Метрики</span><span class="sxs-lookup"><span data-stu-id="84dde-135">Metrics</span></span>

<span data-ttu-id="84dde-136">Следующая таблица содержит сведения, приведенные во вложенном сводном отчете по одноранговым подключениям.</span><span class="sxs-lookup"><span data-stu-id="84dde-136">The following table lists the information provided in the P2P Summary Subreport.</span></span>

### <a name="p2p-summary-subreport-metrics"></a><span data-ttu-id="84dde-137">Метрики вложенного сводного отчета по одноранговым подключениям</span><span class="sxs-lookup"><span data-stu-id="84dde-137">P2P Summary Subreport Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="84dde-138">Имя</span><span class="sxs-lookup"><span data-stu-id="84dde-138">Name</span></span></th>
<th><span data-ttu-id="84dde-139">Возможность сортировки по этому показателю</span><span class="sxs-lookup"><span data-stu-id="84dde-139">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="84dde-140">Описание</span><span class="sxs-lookup"><span data-stu-id="84dde-140">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="84dde-141"><strong> Всего сеансов </strong></span><span class="sxs-lookup"><span data-stu-id="84dde-141"><strong>Total sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="84dde-142">Нет</span><span class="sxs-lookup"><span data-stu-id="84dde-142">No</span></span></p></td>
<td><p><span data-ttu-id="84dde-143">Общее число сеансов, включая успешные и завершившиеся сбоем (как ожидаемые, так и непредвиденные сбои) и сеансы без категорий.</span><span class="sxs-lookup"><span data-stu-id="84dde-143">Total number of sessions, including successful sessions, failed sessions (both expected failures and unexpected failures), and uncategorized sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84dde-144"><strong>Процент сбоев</strong></span><span class="sxs-lookup"><span data-stu-id="84dde-144"><strong>Failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="84dde-145">Нет</span><span class="sxs-lookup"><span data-stu-id="84dde-145">No</span></span></p></td>
<td><p><span data-ttu-id="84dde-146">Доля одноранговых сеансов, завершившихся сбоем.</span><span class="sxs-lookup"><span data-stu-id="84dde-146">Percentage of peer-to-peer sessions that failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84dde-147"><strong>Sessions by Modality</strong> (Сеансы по модальности)</span><span class="sxs-lookup"><span data-stu-id="84dde-147"><strong>Sessions by Modality</strong></span></span></p></td>
<td><p><span data-ttu-id="84dde-148">Нет</span><span class="sxs-lookup"><span data-stu-id="84dde-148">No</span></span></p></td>
<td><p><span data-ttu-id="84dde-149">Общее число сеансов, сгруппированных по модальности (например, обмен мгновенными сообщениями).</span><span class="sxs-lookup"><span data-stu-id="84dde-149">Total number of sessions grouped by modality (for example, instant messaging).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84dde-150"><strong>Failure rate by modality</strong> (Процент сбоев по модальности)</span><span class="sxs-lookup"><span data-stu-id="84dde-150"><strong>Failure rate by modality</strong></span></span></p></td>
<td><p><span data-ttu-id="84dde-151">Нет</span><span class="sxs-lookup"><span data-stu-id="84dde-151">No</span></span></p></td>
<td><p><span data-ttu-id="84dde-152">Общее число неудачных сеансов, сгруппированных по модальности (например, обмен мгновенными сообщениями).</span><span class="sxs-lookup"><span data-stu-id="84dde-152">Total number of failed sessions grouped by modality (for example, instant messaging).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

