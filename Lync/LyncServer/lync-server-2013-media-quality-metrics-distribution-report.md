---
title: 'Lync Server 2013: отчет по распределению метрик качества мультимедиа'
description: 'Lync Server 2013: отчет по распределению метрик качества мультимедиа.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media Quality Metrics Distribution Report
ms:assetid: d07996e6-b0a5-4ff8-9512-ab707762b4e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205262(v=OCS.15)
ms:contentKeyID: 48185409
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: def56580477dadf989268e1fc24fcec7776c00d8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548155"
---
# <a name="the-media-quality-metrics-distribution-report-in-lync-server-2013"></a><span data-ttu-id="6791b-103">Отчет по распределению метрик качества мультимедиа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6791b-103">The Media Quality Metrics Distribution Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6791b-104">_**Последнее изменение темы:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="6791b-104">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="6791b-p101">Отчет по распределению метрик качества среды позволяет просматривать диаграмму, на которой отображаются значения распространения для метрик качества работы, такие как дрожание и потеря пакетов. Предположим, пользователи сделали 10 звонков; ниже приведен отчет по этим 10 звонкам со следующими значениями времени цикла:</span><span class="sxs-lookup"><span data-stu-id="6791b-p101">The Media Quality Metrics Distribution Report enables you to see a graph that shows the distribution values for a Quality of Experience metric such as jitter or packet loss. For example, suppose your users make a total of 10 phone calls; those 10 calls report the following roundtrip times:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6791b-107">Номер звонка</span><span class="sxs-lookup"><span data-stu-id="6791b-107">Call Number</span></span></th>
<th><span data-ttu-id="6791b-108">Время цикла (мс)</span><span class="sxs-lookup"><span data-stu-id="6791b-108">Roundtrip Time (milliseconds)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6791b-109">1,1</span><span class="sxs-lookup"><span data-stu-id="6791b-109">1</span></span></p></td>
<td><p><span data-ttu-id="6791b-110">50</span><span class="sxs-lookup"><span data-stu-id="6791b-110">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6791b-111">2</span><span class="sxs-lookup"><span data-stu-id="6791b-111">2</span></span></p></td>
<td><p><span data-ttu-id="6791b-112">50</span><span class="sxs-lookup"><span data-stu-id="6791b-112">50</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6791b-113">4</span><span class="sxs-lookup"><span data-stu-id="6791b-113">3</span></span></p></td>
<td><p><span data-ttu-id="6791b-114">50</span><span class="sxs-lookup"><span data-stu-id="6791b-114">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6791b-115">4 </span><span class="sxs-lookup"><span data-stu-id="6791b-115">4</span></span></p></td>
<td><p><span data-ttu-id="6791b-116">50</span><span class="sxs-lookup"><span data-stu-id="6791b-116">50</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6791b-117">5 </span><span class="sxs-lookup"><span data-stu-id="6791b-117">5</span></span></p></td>
<td><p><span data-ttu-id="6791b-118">50</span><span class="sxs-lookup"><span data-stu-id="6791b-118">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6791b-119">6 </span><span class="sxs-lookup"><span data-stu-id="6791b-119">6</span></span></p></td>
<td><p><span data-ttu-id="6791b-120">50</span><span class="sxs-lookup"><span data-stu-id="6791b-120">50</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6791b-121">7 </span><span class="sxs-lookup"><span data-stu-id="6791b-121">7</span></span></p></td>
<td><p><span data-ttu-id="6791b-122">50</span><span class="sxs-lookup"><span data-stu-id="6791b-122">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6791b-123">8 </span><span class="sxs-lookup"><span data-stu-id="6791b-123">8</span></span></p></td>
<td><p><span data-ttu-id="6791b-124">4550</span><span class="sxs-lookup"><span data-stu-id="6791b-124">4550</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6791b-125">9 </span><span class="sxs-lookup"><span data-stu-id="6791b-125">9</span></span></p></td>
<td><p><span data-ttu-id="6791b-126">50</span><span class="sxs-lookup"><span data-stu-id="6791b-126">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6791b-127">10 </span><span class="sxs-lookup"><span data-stu-id="6791b-127">10</span></span></p></td>
<td><p><span data-ttu-id="6791b-128">50</span><span class="sxs-lookup"><span data-stu-id="6791b-128">50</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="6791b-p102">Среднее время цикла составляет 500 мс (5000, разделенные на 10). 500 мс — это очень большое время цикла; соответственно, это может говорить о значительных проблемах, связанных с перегрузкой сети (продолжительное время цикла, как правило, свидетельствует о перегруженных сетях).</span><span class="sxs-lookup"><span data-stu-id="6791b-p102">The average for those roundtrip times is 500 milliseconds (5000 divided by 10). Five hundred milliseconds is an extremely large roundtrip time; as a result, you might believe that you have a serious problem with network congestion. (Long roundtrip times are typically the result of overloaded networks.)</span></span>

<span data-ttu-id="6791b-p103">В реальной ситуации, вероятнее всего, 90 % вызовов будут иметь оптимальное значение времени цикла, тогда как один неудачный вызов сведет на нет все результаты. Если ориентироваться только на среднее время цикла, можно прийти к неверному заключению.</span><span class="sxs-lookup"><span data-stu-id="6791b-p103">In reality, of course, 90% of your calls had excellent round trip times; you merely had one bad call that skewed the overall results. If you only look at the average roundtrip time you might jump to a very wrong conclusion.</span></span>

<span data-ttu-id="6791b-p104">Отчет о распределении метрик качества среды позволяет избежать неправильных выводов, представляя визуализацию распределения определенных метрик (таких как время цикла). Эти диаграммы четко показывают, что девять вызовов были нормальными, а один — очень плохим. Очевидно, что может потребоваться дальнейшее выяснение причин сбоя этого вызова. Однако сама возможность узнать, что 9 из 10 вызовов были беспроблемными, позволяет избежать внесения существенных изменений в сеть (по крайней мере на данном этапе).</span><span class="sxs-lookup"><span data-stu-id="6791b-p104">The Media Quality Metrics Distribution Report helps you avoid jumping to wrong conclusions by showing you a graphical distribution of a specified metric (such as round trip time). These graphs can help make it clear that you had nine very good calls and one very bad call. Admittedly, you might still want to further investigate that one call; however, the fact that 9 out of the 10 calls were very good suggests that there is no reason to make any drastic changes to your network, at least not at this point in time.</span></span>

<div>

## <a name="filters"></a><span data-ttu-id="6791b-137">Фильтры</span><span class="sxs-lookup"><span data-stu-id="6791b-137">Filters</span></span>

<span data-ttu-id="6791b-p105">Фильтры позволяют получать более точные и актуальные наборы данных или просматривать возвращаемые данные в разных комбинациях. В следующей таблице перечислены фильтры, которые можно использовать в отчете по распределению метрик качества среды.</span><span class="sxs-lookup"><span data-stu-id="6791b-p105">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the Media Quality Metrics Distribution Report.</span></span>

### <a name="media-quality-metrics-distribution-report-filters"></a><span data-ttu-id="6791b-140">Фильтры отчета по распределению метрик качества среды</span><span class="sxs-lookup"><span data-stu-id="6791b-140">Media Quality Metrics Distribution Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6791b-141">Имя</span><span class="sxs-lookup"><span data-stu-id="6791b-141">Name</span></span></th>
<th><span data-ttu-id="6791b-142">Описание</span><span class="sxs-lookup"><span data-stu-id="6791b-142">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6791b-143"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="6791b-143"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="6791b-p106">Дата и время начала диапазона. Чтобы просмотреть данные по часам, введите дату и время начала в следующем формате:</span><span class="sxs-lookup"><span data-stu-id="6791b-p106">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="6791b-146">7/7/2012 13:00.</span><span class="sxs-lookup"><span data-stu-id="6791b-146">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="6791b-p107">Если не указать время начала, автоматически будет выбрано время 00:00 указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</span><span class="sxs-lookup"><span data-stu-id="6791b-p107">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="6791b-149">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="6791b-149">7/7/2012</span></span></p>
<p><span data-ttu-id="6791b-150">Для просмотра по неделям или по месяцам введите дату, выпадающую на любой день недели или месяца, который вы хотите просмотреть (это необязательно должен быть первый день недели или месяца):</span><span class="sxs-lookup"><span data-stu-id="6791b-150">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="6791b-151">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="6791b-151">7/3/2012</span></span></p>
<p><span data-ttu-id="6791b-152">Неделя всегда начинается с воскресения и заканчивается субботой.</span><span class="sxs-lookup"><span data-stu-id="6791b-152">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6791b-153"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="6791b-153"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="6791b-p108">Дата и время окончания диапазона. Чтобы просмотреть данные по часам, введите дату и время окончания в следующем формате:</span><span class="sxs-lookup"><span data-stu-id="6791b-p108">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="6791b-156">7/7/2012 13:00.</span><span class="sxs-lookup"><span data-stu-id="6791b-156">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="6791b-p109">Если не указать время окончания, автоматически будет выбрано время 00:00 указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</span><span class="sxs-lookup"><span data-stu-id="6791b-p109">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="6791b-159">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="6791b-159">7/7/2012</span></span></p>
<p><span data-ttu-id="6791b-160">Для просмотра по неделям или по месяцам введите дату, выпадающую на любой день недели или месяца, который вы хотите просмотреть (это необязательно должен быть первый день недели или месяца):</span><span class="sxs-lookup"><span data-stu-id="6791b-160">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="6791b-161">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="6791b-161">7/3/2012</span></span></p>
<p><span data-ttu-id="6791b-162">Неделя всегда начинается с воскресения и заканчивается субботой.</span><span class="sxs-lookup"><span data-stu-id="6791b-162">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6791b-163"><strong>Minimum in x axis</strong> (Минимальное значение на оси x)</span><span class="sxs-lookup"><span data-stu-id="6791b-163"><strong>Minimum in x axis</strong></span></span></p></td>
<td><p><span data-ttu-id="6791b-164">Минимальное значение будет отображаться на оси X диаграммы.</span><span class="sxs-lookup"><span data-stu-id="6791b-164">Lowest value to be displayed on the X axis of the graph.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6791b-165"><strong>Maximum in x axis</strong> (Максимальное значение на оси x)</span><span class="sxs-lookup"><span data-stu-id="6791b-165"><strong>Maximum in x axis</strong></span></span></p></td>
<td><p><span data-ttu-id="6791b-166">Максимальное значение будет отображаться на оси X диаграммы.</span><span class="sxs-lookup"><span data-stu-id="6791b-166">Highest value to be displayed on the X axis of the graph.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6791b-167"><strong>Тип доступа</strong></span><span class="sxs-lookup"><span data-stu-id="6791b-167"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="6791b-p110">Указывает, вошел ли клиент из внутренней или внешней сети при выполнении звонка. Выберите одно из значений:</span><span class="sxs-lookup"><span data-stu-id="6791b-p110">Indicates whether the client was logged on to the internal network or the external network when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="6791b-170">Ко</span><span class="sxs-lookup"><span data-stu-id="6791b-170">[All]</span></span></p></li>
<li><p><span data-ttu-id="6791b-171">Внутренний</span><span class="sxs-lookup"><span data-stu-id="6791b-171">Internal</span></span></p></li>
<li><p><span data-ttu-id="6791b-172">Внешний</span><span class="sxs-lookup"><span data-stu-id="6791b-172">External</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6791b-173"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="6791b-173"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="6791b-p111">Указывает, использовал ли внешний клиент VPN-подключение при выполнении звонка. Выберите одно из значений:</span><span class="sxs-lookup"><span data-stu-id="6791b-p111">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="6791b-176">Ко</span><span class="sxs-lookup"><span data-stu-id="6791b-176">[All]</span></span></p></li>
<li><p><span data-ttu-id="6791b-177">VPN</span><span class="sxs-lookup"><span data-stu-id="6791b-177">VPN</span></span></p></li>
<li><p><span data-ttu-id="6791b-178">Не VPN</span><span class="sxs-lookup"><span data-stu-id="6791b-178">Non-VPN</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6791b-179"><strong>Тип сети</strong></span><span class="sxs-lookup"><span data-stu-id="6791b-179"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="6791b-p112">Указание типа сети, к которой был подключен клиент при выполнении вызова. Выберите одно из значений:</span><span class="sxs-lookup"><span data-stu-id="6791b-p112">Indicates the type of network the client was connected to when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="6791b-182">Ко</span><span class="sxs-lookup"><span data-stu-id="6791b-182">[All]</span></span></p></li>
<li><p><span data-ttu-id="6791b-183">Политик</span><span class="sxs-lookup"><span data-stu-id="6791b-183">Wired</span></span></p></li>
<li><p><span data-ttu-id="6791b-184">Инфракрас</span><span class="sxs-lookup"><span data-stu-id="6791b-184">Wireless</span></span></p></li>
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

