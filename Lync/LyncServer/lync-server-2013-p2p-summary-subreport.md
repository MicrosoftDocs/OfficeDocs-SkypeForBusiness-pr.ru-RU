---
title: 'Сводный отчет о Lync Server 2013: P2P'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: P2P Summary Subreport
ms:assetid: fc36185a-3cc5-4167-8c93-8a755fa75ac7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205416(v=OCS.15)
ms:contentKeyID: 48185950
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7199d9571adfb90b6f848f8f46474fd14813bc76
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825382"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="p2p-summary-subreport-in-lync-server-2013"></a><span data-ttu-id="cb44a-102">Сводный отчет P2P в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cb44a-102">P2P Summary Subreport in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cb44a-103">_**Тема последнего изменения:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="cb44a-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="cb44a-104">Вложенный сводный отчет по одноранговым подключениям содержит общий обзор одноранговых сеансов связи, завершившихся с ошибками.</span><span class="sxs-lookup"><span data-stu-id="cb44a-104">The P2P Summary Subreport provides an overall view of your failed peer-to-peer communication sessions.</span></span>

<div>

## <a name="filters"></a><span data-ttu-id="cb44a-105">Фильтры</span><span class="sxs-lookup"><span data-stu-id="cb44a-105">Filters</span></span>

<span data-ttu-id="cb44a-p101">Фильтры позволяют возвращать более точный набор данных или различными способами просматривать возвращенные данные. В следующей таблице представлены фильтры, которые вы можете использовать со сводным вложенным отчетом P2P.</span><span class="sxs-lookup"><span data-stu-id="cb44a-p101">Filters provide a way for you to return a more finely targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the P2P Summary Subreport.</span></span>

### <a name="p2p-summary-subreport-filters"></a><span data-ttu-id="cb44a-108">Фильтры вложенного сводного отчета по одноранговым подключениям</span><span class="sxs-lookup"><span data-stu-id="cb44a-108">P2P Summary Subreport Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cb44a-109">Имя</span><span class="sxs-lookup"><span data-stu-id="cb44a-109">Name</span></span></th>
<th><span data-ttu-id="cb44a-110">Описание</span><span class="sxs-lookup"><span data-stu-id="cb44a-110">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cb44a-111"><strong>От</strong></span><span class="sxs-lookup"><span data-stu-id="cb44a-111"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="cb44a-p102">Начальная дата и начальное время для диапазона времени. Чтобы просмотреть данные по часам, введите начальную дату и начальное время в следующем формате:</span><span class="sxs-lookup"><span data-stu-id="cb44a-p102">Start date and time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="cb44a-114">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="cb44a-114">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="cb44a-p103">Если вы не вводите начальное время, отчет автоматически начинается с 12:00 AM указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</span><span class="sxs-lookup"><span data-stu-id="cb44a-p103">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="cb44a-117">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="cb44a-117">7/7/2012</span></span></p>
<p><span data-ttu-id="cb44a-118">Чтобы просмотреть данные за неделю или месяц, введите дату, выпадающую на любое время в рамках недели или месяца, которые вы хотите просмотреть (вам не требуется вводить первый день недели или месяца):</span><span class="sxs-lookup"><span data-stu-id="cb44a-118">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="cb44a-119">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="cb44a-119">7/3/2012</span></span></p>
<p><span data-ttu-id="cb44a-120">Недели всегда отсчитываются с воскресенья по субботу.</span><span class="sxs-lookup"><span data-stu-id="cb44a-120">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cb44a-121"><strong>До</strong></span><span class="sxs-lookup"><span data-stu-id="cb44a-121"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="cb44a-p104">Конечная дата и конечное время для диапазона времени. Чтобы просмотреть данные по часам, введите конечную дату и конечное время в следующем формате:</span><span class="sxs-lookup"><span data-stu-id="cb44a-p104">End date and time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="cb44a-124">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="cb44a-124">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="cb44a-p105">Если вы не вводите конечное время, отчет автоматически заканчивается в 12:00 AM указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</span><span class="sxs-lookup"><span data-stu-id="cb44a-p105">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="cb44a-127">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="cb44a-127">7/7/2012</span></span></p>
<p><span data-ttu-id="cb44a-128">Чтобы просмотреть данные за неделю или месяц, введите дату, выпадающую на любое время в рамках недели или месяца, которые вы хотите просмотреть (вам не требуется вводить первый день недели или месяца):</span><span class="sxs-lookup"><span data-stu-id="cb44a-128">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="cb44a-129">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="cb44a-129">7/3/2012</span></span></p>
<p><span data-ttu-id="cb44a-130">Недели всегда отсчитываются с воскресенья по субботу.</span><span class="sxs-lookup"><span data-stu-id="cb44a-130">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cb44a-131"><strong>Пул</strong></span><span class="sxs-lookup"><span data-stu-id="cb44a-131"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="cb44a-p106">Полное доменное имя пула регистратора или пограничного сервера. Можно выбрать отдельный пул или нажать <strong>[Все]</strong>, чтобы просмотреть данные для всех пулов. Этот раскрывающийся список автоматически заполняется на основе записей в базе данных.</span><span class="sxs-lookup"><span data-stu-id="cb44a-p106">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="cb44a-135">Показатели</span><span class="sxs-lookup"><span data-stu-id="cb44a-135">Metrics</span></span>

<span data-ttu-id="cb44a-136">Следующая таблица содержит сведения, приведенные во вложенном сводном отчете по одноранговым подключениям.</span><span class="sxs-lookup"><span data-stu-id="cb44a-136">The following table lists the information provided in the P2P Summary Subreport.</span></span>

### <a name="p2p-summary-subreport-metrics"></a><span data-ttu-id="cb44a-137">Метрики вложенного сводного отчета по одноранговым подключениям</span><span class="sxs-lookup"><span data-stu-id="cb44a-137">P2P Summary Subreport Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cb44a-138">Имя</span><span class="sxs-lookup"><span data-stu-id="cb44a-138">Name</span></span></th>
<th><span data-ttu-id="cb44a-139">Поддержка сортировки</span><span class="sxs-lookup"><span data-stu-id="cb44a-139">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="cb44a-140">Описание</span><span class="sxs-lookup"><span data-stu-id="cb44a-140">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cb44a-141"><strong>Всего сеансов</strong></span><span class="sxs-lookup"><span data-stu-id="cb44a-141"><strong>Total sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="cb44a-142">Нет</span><span class="sxs-lookup"><span data-stu-id="cb44a-142">No</span></span></p></td>
<td><p><span data-ttu-id="cb44a-143">Общее число сеансов, включая успешные и завершившиеся сбоем (как ожидаемые, так и непредвиденные сбои) и сеансы без категорий.</span><span class="sxs-lookup"><span data-stu-id="cb44a-143">Total number of sessions, including successful sessions, failed sessions (both expected failures and unexpected failures), and uncategorized sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cb44a-144"><strong>Доля сбоев</strong></span><span class="sxs-lookup"><span data-stu-id="cb44a-144"><strong>Failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="cb44a-145">Нет</span><span class="sxs-lookup"><span data-stu-id="cb44a-145">No</span></span></p></td>
<td><p><span data-ttu-id="cb44a-146">Процент неудачных одноранговых сеансов.</span><span class="sxs-lookup"><span data-stu-id="cb44a-146">Percentage of peer-to-peer sessions that failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cb44a-147"><strong>Сеансы по модальности</strong></span><span class="sxs-lookup"><span data-stu-id="cb44a-147"><strong>Sessions by Modality</strong></span></span></p></td>
<td><p><span data-ttu-id="cb44a-148">Нет</span><span class="sxs-lookup"><span data-stu-id="cb44a-148">No</span></span></p></td>
<td><p><span data-ttu-id="cb44a-149">Общее число сеансов, сгруппированных по модальности (например, обмен мгновенными сообщениями).</span><span class="sxs-lookup"><span data-stu-id="cb44a-149">Total number of sessions grouped by modality (for example, instant messaging).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cb44a-150"><strong>Доля сбоев по модальности</strong></span><span class="sxs-lookup"><span data-stu-id="cb44a-150"><strong>Failure rate by modality</strong></span></span></p></td>
<td><p><span data-ttu-id="cb44a-151">Нет</span><span class="sxs-lookup"><span data-stu-id="cb44a-151">No</span></span></p></td>
<td><p><span data-ttu-id="cb44a-152">Общее число неудачных сеансов, сгруппированных по модальности (например, обмен мгновенными сообщениями).</span><span class="sxs-lookup"><span data-stu-id="cb44a-152">Total number of failed sessions grouped by modality (for example, instant messaging).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

