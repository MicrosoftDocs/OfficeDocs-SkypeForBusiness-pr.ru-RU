---
title: 'Lync Server 2013: отчет о тенденциях расположения'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Location Trend Report
ms:assetid: 61e2db3c-9f10-4411-8e7e-c6950faf8533
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204941(v=OCS.15)
ms:contentKeyID: 48184280
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 26f825a33eeb90817685c1694a5c6579110ffcd6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762147"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="location-trend-report-in-lync-server-2013"></a><span data-ttu-id="b38df-102">Отчет о тенденциях расположения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b38df-102">Location Trend Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b38df-103">_**Тема последнего изменения:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="b38df-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="b38df-104">В отчете о тенденциях расположений приводятся сведения о тенденциях качества звонков для сетевых расположений.</span><span class="sxs-lookup"><span data-stu-id="b38df-104">The Location Trend Report provides call quality trend information for network locations.</span></span>

<div>

## <a name="filters"></a><span data-ttu-id="b38df-105">Фильтры</span><span class="sxs-lookup"><span data-stu-id="b38df-105">Filters</span></span>

<span data-ttu-id="b38df-p101">Фильтры позволяют получить более конкретные наборы возвращаемых данных. Например, отчет о тенденциях расположений позволяет фильтровать возвращаемые данные по таким показателям, как тип доступа (то есть внутренний или внешний доступ) или тип сетевого подключения (проводное или беспроводное). Вы также можете выбрать тип группировки данных. В этом случае звонки группируются по часам, дням или неделям.</span><span class="sxs-lookup"><span data-stu-id="b38df-p101">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Location Trend Report enables you to filter the returned data by such things as access type (that is, interval access vs. external access) or by wired/wireless network connection. You can also choose how data should be grouped. In this case, calls are grouped by hour, day, or week.</span></span>

<span data-ttu-id="b38df-110">В следующей таблице перечислены фильтры, которые вы можете использовать с отчетом о тенденциях расположений.</span><span class="sxs-lookup"><span data-stu-id="b38df-110">The following table lists the filters that you can use with the Location Trend Report.</span></span>

### <a name="location-trend-report-filters"></a><span data-ttu-id="b38df-111">Фильтры отчета тенденций расположений</span><span class="sxs-lookup"><span data-stu-id="b38df-111">Location Trend Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b38df-112">Имя</span><span class="sxs-lookup"><span data-stu-id="b38df-112">Name</span></span></th>
<th><span data-ttu-id="b38df-113">Описание</span><span class="sxs-lookup"><span data-stu-id="b38df-113">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b38df-114"><strong>От</strong></span><span class="sxs-lookup"><span data-stu-id="b38df-114"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="b38df-p102">Начальные дата/время для временного диапазона. Чтобы просмотреть данные по часам, введите начальные дату и время следующим образом:</span><span class="sxs-lookup"><span data-stu-id="b38df-p102">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="b38df-117">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="b38df-117">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="b38df-p103">Если вы не вводите начальное время, отчет автоматически начинается с 12:00 AM указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</span><span class="sxs-lookup"><span data-stu-id="b38df-p103">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="b38df-120">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="b38df-120">7/7/2012</span></span></p>
<p><span data-ttu-id="b38df-121">Чтобы просмотреть данные за неделю или месяц, введите дату, выпадающую на любое время в рамках недели или месяца, которые вы хотите просмотреть (вам не требуется вводить первый день недели или месяца):</span><span class="sxs-lookup"><span data-stu-id="b38df-121">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="b38df-122">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="b38df-122">7/3/2012</span></span></p>
<p><span data-ttu-id="b38df-123">Недели всегда отсчитываются с воскресенья по субботу.</span><span class="sxs-lookup"><span data-stu-id="b38df-123">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b38df-124"><strong>До</strong></span><span class="sxs-lookup"><span data-stu-id="b38df-124"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="b38df-p104">Конечные дата/время для временного диапазона. Чтобы просмотреть данные по часам, введите конечные дату и время следующим образом:</span><span class="sxs-lookup"><span data-stu-id="b38df-p104">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="b38df-127">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="b38df-127">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="b38df-p105">Если вы не вводите конечное время, отчет автоматически заканчивается в 12:00 AM указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</span><span class="sxs-lookup"><span data-stu-id="b38df-p105">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="b38df-130">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="b38df-130">7/7/2012</span></span></p>
<p><span data-ttu-id="b38df-131">Чтобы просмотреть данные за неделю или месяц, введите дату, выпадающую на любое время в рамках недели или месяца, которые вы хотите просмотреть (вам не требуется вводить первый день недели или месяца):</span><span class="sxs-lookup"><span data-stu-id="b38df-131">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="b38df-132">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="b38df-132">7/3/2012</span></span></p>
<p><span data-ttu-id="b38df-133">Недели всегда отсчитываются с воскресенья по субботу.</span><span class="sxs-lookup"><span data-stu-id="b38df-133">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b38df-134"><strong>Интервал</strong></span><span class="sxs-lookup"><span data-stu-id="b38df-134"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="b38df-p106">Временной интервал. Выберите одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="b38df-p106">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="b38df-137">Ежечасно (можно отобразить не более 25 часов)</span><span class="sxs-lookup"><span data-stu-id="b38df-137">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="b38df-138">Ежедневно (можно отобразить не более 31 дня)</span><span class="sxs-lookup"><span data-stu-id="b38df-138">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="b38df-139">Еженедельно (можно отобразить не более 12 недель)</span><span class="sxs-lookup"><span data-stu-id="b38df-139">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="b38df-p107">Если число значений между начальной и конечной датами превышает максимальное допустимое для выбранного интервала, отображается максимальное возможное число значений (с начальной даты). Например, если вы выбрали интервал "Ежедневно" с начальной датой 01.01.2011 и конечной датой 28.02.2011, будут показаны данные для периода с 01.08.2011 24:00 до 01.09.2011 24:00 (то есть для 31 дня).</span><span class="sxs-lookup"><span data-stu-id="b38df-p107">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 1/1/2011 and an end date of 2/28/2011, data is displayed for the days 8/1/2011 12:00 AM to 9/1/2011 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b38df-142"><strong>Тип доступа</strong></span><span class="sxs-lookup"><span data-stu-id="b38df-142"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="b38df-p108">Определяет, был ли клиент зарегистрирован во внутренней сети или внешней сети при выполнении вызова. Выберите один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="b38df-p108">Indicates whether the client was logged on to the internal network or the external network when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="b38df-145">[All] (Все)</span><span class="sxs-lookup"><span data-stu-id="b38df-145">[All]</span></span></p></li>
<li><p><span data-ttu-id="b38df-146">Internal</span><span class="sxs-lookup"><span data-stu-id="b38df-146">Internal</span></span></p></li>
<li><p><span data-ttu-id="b38df-147">Внешняя</span><span class="sxs-lookup"><span data-stu-id="b38df-147">External</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b38df-148"><strong>Тип сети</strong></span><span class="sxs-lookup"><span data-stu-id="b38df-148"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="b38df-p109">Определяет тип сети, к которой был подключен клиент при выполнении вызова. Выберите один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="b38df-p109">Indicates the type of network the client was connected to when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="b38df-151">[All] (Все)</span><span class="sxs-lookup"><span data-stu-id="b38df-151">[All]</span></span></p></li>
<li><p><span data-ttu-id="b38df-152">Проводная</span><span class="sxs-lookup"><span data-stu-id="b38df-152">Wired</span></span></p></li>
<li><p><span data-ttu-id="b38df-153">Беспроводная</span><span class="sxs-lookup"><span data-stu-id="b38df-153">Wireless</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b38df-154"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="b38df-154"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="b38df-p110">Указывает, использовал ли внешний клиент подключение посредством виртуальной частной сети (VPN) при выполнении вызова. Выберите один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="b38df-p110">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="b38df-157">[All] (Все)</span><span class="sxs-lookup"><span data-stu-id="b38df-157">[All]</span></span></p></li>
<li><p><span data-ttu-id="b38df-158">VPN;</span><span class="sxs-lookup"><span data-stu-id="b38df-158">VPN</span></span></p></li>
<li><p><span data-ttu-id="b38df-159">Не VPN</span><span class="sxs-lookup"><span data-stu-id="b38df-159">Non-VPN</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

