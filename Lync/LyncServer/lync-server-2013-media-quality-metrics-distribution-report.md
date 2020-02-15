---
title: 'Lync Server 2013: отчет по распределению метрик качества мультимедиа'
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
ms.openlocfilehash: 38adc41aaffcccbb27d4c9105f0fecabcae3c21c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045121"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="the-media-quality-metrics-distribution-report-in-lync-server-2013"></a><span data-ttu-id="fba07-102">Отчет по распределению метрик качества мультимедиа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fba07-102">The Media Quality Metrics Distribution Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fba07-103">_**Последнее изменение темы:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="fba07-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="fba07-p101">Отчет по распределению метрик качества среды позволяет просматривать диаграмму, на которой отображаются значения распространения для метрик качества работы, такие как дрожание и потеря пакетов. Предположим, пользователи сделали 10 звонков; ниже приведен отчет по этим 10 звонкам со следующими значениями времени цикла:</span><span class="sxs-lookup"><span data-stu-id="fba07-p101">The Media Quality Metrics Distribution Report enables you to see a graph that shows the distribution values for a Quality of Experience metric such as jitter or packet loss. For example, suppose your users make a total of 10 phone calls; those 10 calls report the following roundtrip times:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fba07-106">Номер звонка</span><span class="sxs-lookup"><span data-stu-id="fba07-106">Call Number</span></span></th>
<th><span data-ttu-id="fba07-107">Время цикла (мс)</span><span class="sxs-lookup"><span data-stu-id="fba07-107">Roundtrip Time (milliseconds)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fba07-108">1 </span><span class="sxs-lookup"><span data-stu-id="fba07-108">1</span></span></p></td>
<td><p><span data-ttu-id="fba07-109">50</span><span class="sxs-lookup"><span data-stu-id="fba07-109">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fba07-110">2 </span><span class="sxs-lookup"><span data-stu-id="fba07-110">2</span></span></p></td>
<td><p><span data-ttu-id="fba07-111">50</span><span class="sxs-lookup"><span data-stu-id="fba07-111">50</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fba07-112">3 </span><span class="sxs-lookup"><span data-stu-id="fba07-112">3</span></span></p></td>
<td><p><span data-ttu-id="fba07-113">50</span><span class="sxs-lookup"><span data-stu-id="fba07-113">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fba07-114">4 </span><span class="sxs-lookup"><span data-stu-id="fba07-114">4</span></span></p></td>
<td><p><span data-ttu-id="fba07-115">50</span><span class="sxs-lookup"><span data-stu-id="fba07-115">50</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fba07-116">5 </span><span class="sxs-lookup"><span data-stu-id="fba07-116">5</span></span></p></td>
<td><p><span data-ttu-id="fba07-117">50</span><span class="sxs-lookup"><span data-stu-id="fba07-117">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fba07-118">6 </span><span class="sxs-lookup"><span data-stu-id="fba07-118">6</span></span></p></td>
<td><p><span data-ttu-id="fba07-119">50</span><span class="sxs-lookup"><span data-stu-id="fba07-119">50</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fba07-120">7 </span><span class="sxs-lookup"><span data-stu-id="fba07-120">7</span></span></p></td>
<td><p><span data-ttu-id="fba07-121">50</span><span class="sxs-lookup"><span data-stu-id="fba07-121">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fba07-122">8 </span><span class="sxs-lookup"><span data-stu-id="fba07-122">8</span></span></p></td>
<td><p><span data-ttu-id="fba07-123">4550</span><span class="sxs-lookup"><span data-stu-id="fba07-123">4550</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fba07-124">9 </span><span class="sxs-lookup"><span data-stu-id="fba07-124">9</span></span></p></td>
<td><p><span data-ttu-id="fba07-125">50</span><span class="sxs-lookup"><span data-stu-id="fba07-125">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fba07-126">10 </span><span class="sxs-lookup"><span data-stu-id="fba07-126">10</span></span></p></td>
<td><p><span data-ttu-id="fba07-127">50</span><span class="sxs-lookup"><span data-stu-id="fba07-127">50</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="fba07-p102">Среднее время цикла составляет 500 мс (5000, разделенные на 10). 500 мс — это очень большое время цикла; соответственно, это может говорить о значительных проблемах, связанных с перегрузкой сети (продолжительное время цикла, как правило, свидетельствует о перегруженных сетях).</span><span class="sxs-lookup"><span data-stu-id="fba07-p102">The average for those roundtrip times is 500 milliseconds (5000 divided by 10). Five hundred milliseconds is an extremely large roundtrip time; as a result, you might believe that you have a serious problem with network congestion. (Long roundtrip times are typically the result of overloaded networks.)</span></span>

<span data-ttu-id="fba07-p103">В реальной ситуации, вероятнее всего, 90 % вызовов будут иметь оптимальное значение времени цикла, тогда как один неудачный вызов сведет на нет все результаты. Если ориентироваться только на среднее время цикла, можно прийти к неверному заключению.</span><span class="sxs-lookup"><span data-stu-id="fba07-p103">In reality, of course, 90% of your calls had excellent round trip times; you merely had one bad call that skewed the overall results. If you only look at the average roundtrip time you might jump to a very wrong conclusion.</span></span>

<span data-ttu-id="fba07-p104">Отчет о распределении метрик качества среды позволяет избежать неправильных выводов, представляя визуализацию распределения определенных метрик (таких как время цикла). Эти диаграммы четко показывают, что девять вызовов были нормальными, а один — очень плохим. Очевидно, что может потребоваться дальнейшее выяснение причин сбоя этого вызова. Однако сама возможность узнать, что 9 из 10 вызовов были беспроблемными, позволяет избежать внесения существенных изменений в сеть (по крайней мере на данном этапе).</span><span class="sxs-lookup"><span data-stu-id="fba07-p104">The Media Quality Metrics Distribution Report helps you avoid jumping to wrong conclusions by showing you a graphical distribution of a specified metric (such as round trip time). These graphs can help make it clear that you had nine very good calls and one very bad call. Admittedly, you might still want to further investigate that one call; however, the fact that 9 out of the 10 calls were very good suggests that there is no reason to make any drastic changes to your network, at least not at this point in time.</span></span>

<div>

## <a name="filters"></a><span data-ttu-id="fba07-136">Фильтры</span><span class="sxs-lookup"><span data-stu-id="fba07-136">Filters</span></span>

<span data-ttu-id="fba07-p105">Фильтры позволяют получать более точные и актуальные наборы данных или просматривать возвращаемые данные в разных комбинациях. В следующей таблице перечислены фильтры, которые можно использовать в отчете по распределению метрик качества среды.</span><span class="sxs-lookup"><span data-stu-id="fba07-p105">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the Media Quality Metrics Distribution Report.</span></span>

### <a name="media-quality-metrics-distribution-report-filters"></a><span data-ttu-id="fba07-139">Фильтры отчета по распределению метрик качества среды</span><span class="sxs-lookup"><span data-stu-id="fba07-139">Media Quality Metrics Distribution Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fba07-140">Имя</span><span class="sxs-lookup"><span data-stu-id="fba07-140">Name</span></span></th>
<th><span data-ttu-id="fba07-141">Описание</span><span class="sxs-lookup"><span data-stu-id="fba07-141">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fba07-142"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="fba07-142"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="fba07-p106">Дата и время начала диапазона. Чтобы просмотреть данные по часам, введите дату и время начала в следующем формате:</span><span class="sxs-lookup"><span data-stu-id="fba07-p106">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="fba07-145">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="fba07-145">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="fba07-p107">Если не указать время начала, автоматически будет выбрано время 00:00 указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</span><span class="sxs-lookup"><span data-stu-id="fba07-p107">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="fba07-148">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="fba07-148">7/7/2012</span></span></p>
<p><span data-ttu-id="fba07-149">Для просмотра по неделям или по месяцам введите дату, выпадающую на любой день недели или месяца, который вы хотите просмотреть (это необязательно должен быть первый день недели или месяца):</span><span class="sxs-lookup"><span data-stu-id="fba07-149">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="fba07-150">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="fba07-150">7/3/2012</span></span></p>
<p><span data-ttu-id="fba07-151">Неделя всегда начинается с воскресенья и заканчивается субботой.</span><span class="sxs-lookup"><span data-stu-id="fba07-151">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fba07-152"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="fba07-152"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="fba07-p108">Дата и время окончания диапазона. Чтобы просмотреть данные по часам, введите дату и время окончания в следующем формате:</span><span class="sxs-lookup"><span data-stu-id="fba07-p108">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="fba07-155">7/7/2012 13:00.</span><span class="sxs-lookup"><span data-stu-id="fba07-155">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="fba07-p109">Если не указать время окончания, автоматически будет выбрано время 00:00 указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</span><span class="sxs-lookup"><span data-stu-id="fba07-p109">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="fba07-158">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="fba07-158">7/7/2012</span></span></p>
<p><span data-ttu-id="fba07-159">Для просмотра по неделям или по месяцам введите дату, выпадающую на любой день недели или месяца, который вы хотите просмотреть (это необязательно должен быть первый день недели или месяца):</span><span class="sxs-lookup"><span data-stu-id="fba07-159">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="fba07-160">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="fba07-160">7/3/2012</span></span></p>
<p><span data-ttu-id="fba07-161">Неделя всегда начинается с воскресения и заканчивается субботой.</span><span class="sxs-lookup"><span data-stu-id="fba07-161">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fba07-162"><strong>Minimum in x axis</strong> (Минимальное значение на оси x)</span><span class="sxs-lookup"><span data-stu-id="fba07-162"><strong>Minimum in x axis</strong></span></span></p></td>
<td><p><span data-ttu-id="fba07-163">Минимальное значение будет отображаться на оси X диаграммы.</span><span class="sxs-lookup"><span data-stu-id="fba07-163">Lowest value to be displayed on the X axis of the graph.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fba07-164"><strong>Maximum in x axis</strong> (Максимальное значение на оси x)</span><span class="sxs-lookup"><span data-stu-id="fba07-164"><strong>Maximum in x axis</strong></span></span></p></td>
<td><p><span data-ttu-id="fba07-165">Максимальное значение будет отображаться на оси X диаграммы.</span><span class="sxs-lookup"><span data-stu-id="fba07-165">Highest value to be displayed on the X axis of the graph.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fba07-166"><strong>Тип доступа</strong></span><span class="sxs-lookup"><span data-stu-id="fba07-166"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="fba07-p110">Указывает, вошел ли клиент из внутренней или внешней сети при выполнении звонка. Выберите одно из значений:</span><span class="sxs-lookup"><span data-stu-id="fba07-p110">Indicates whether the client was logged on to the internal network or the external network when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="fba07-169">Ко</span><span class="sxs-lookup"><span data-stu-id="fba07-169">[All]</span></span></p></li>
<li><p><span data-ttu-id="fba07-170">Внутренний</span><span class="sxs-lookup"><span data-stu-id="fba07-170">Internal</span></span></p></li>
<li><p><span data-ttu-id="fba07-171">External</span><span class="sxs-lookup"><span data-stu-id="fba07-171">External</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fba07-172"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="fba07-172"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="fba07-p111">Указывает, использовал ли внешний клиент VPN-подключение при выполнении звонка. Выберите одно из значений:</span><span class="sxs-lookup"><span data-stu-id="fba07-p111">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="fba07-175">Ко</span><span class="sxs-lookup"><span data-stu-id="fba07-175">[All]</span></span></p></li>
<li><p><span data-ttu-id="fba07-176">VPN</span><span class="sxs-lookup"><span data-stu-id="fba07-176">VPN</span></span></p></li>
<li><p><span data-ttu-id="fba07-177">Не VPN</span><span class="sxs-lookup"><span data-stu-id="fba07-177">Non-VPN</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fba07-178"><strong>Тип сети</strong></span><span class="sxs-lookup"><span data-stu-id="fba07-178"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="fba07-p112">Указание типа сети, к которой был подключен клиент при выполнении вызова. Выберите одно из значений:</span><span class="sxs-lookup"><span data-stu-id="fba07-p112">Indicates the type of network the client was connected to when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="fba07-181">Ко</span><span class="sxs-lookup"><span data-stu-id="fba07-181">[All]</span></span></p></li>
<li><p><span data-ttu-id="fba07-182">Политик</span><span class="sxs-lookup"><span data-stu-id="fba07-182">Wired</span></span></p></li>
<li><p><span data-ttu-id="fba07-183">Инфракрас</span><span class="sxs-lookup"><span data-stu-id="fba07-183">Wireless</span></span></p></li>
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

