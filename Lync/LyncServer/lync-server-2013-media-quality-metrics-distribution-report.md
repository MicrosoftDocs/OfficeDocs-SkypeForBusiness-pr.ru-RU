---
title: 'Lync Server 2013: отчет о распределении метрик качества мультимедиа'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Media Quality Metrics Distribution Report
ms:assetid: d07996e6-b0a5-4ff8-9512-ab707762b4e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205262(v=OCS.15)
ms:contentKeyID: 48185409
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d1d814fd001f3510a7ae83e63746bdc1265932e4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827391"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="the-media-quality-metrics-distribution-report-in-lync-server-2013"></a><span data-ttu-id="c3607-102">Отчет о распределении метрик качества мультимедиа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c3607-102">The Media Quality Metrics Distribution Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c3607-103">_**Тема последнего изменения:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="c3607-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="c3607-p101">Отчет по распределению метрик качества среды позволяет просматривать диаграмму, на которой отображаются значения распространения для метрик качества работы, такие как дрожание и потеря пакетов. Предположим, пользователи сделали 10 звонков; ниже приведен отчет по этим 10 звонкам со следующими значениями времени цикла:</span><span class="sxs-lookup"><span data-stu-id="c3607-p101">The Media Quality Metrics Distribution Report enables you to see a graph that shows the distribution values for a Quality of Experience metric such as jitter or packet loss. For example, suppose your users make a total of 10 phone calls; those 10 calls report the following roundtrip times:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c3607-106">Номер звонка</span><span class="sxs-lookup"><span data-stu-id="c3607-106">Call Number</span></span></th>
<th><span data-ttu-id="c3607-107">Время обмена данными (мсек)</span><span class="sxs-lookup"><span data-stu-id="c3607-107">Roundtrip Time (milliseconds)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c3607-108">1</span><span class="sxs-lookup"><span data-stu-id="c3607-108">1</span></span></p></td>
<td><p><span data-ttu-id="c3607-109">50</span><span class="sxs-lookup"><span data-stu-id="c3607-109">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3607-110">2</span><span class="sxs-lookup"><span data-stu-id="c3607-110">2</span></span></p></td>
<td><p><span data-ttu-id="c3607-111">50</span><span class="sxs-lookup"><span data-stu-id="c3607-111">50</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3607-112">3</span><span class="sxs-lookup"><span data-stu-id="c3607-112">3</span></span></p></td>
<td><p><span data-ttu-id="c3607-113">50</span><span class="sxs-lookup"><span data-stu-id="c3607-113">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3607-114">4</span><span class="sxs-lookup"><span data-stu-id="c3607-114">4</span></span></p></td>
<td><p><span data-ttu-id="c3607-115">50</span><span class="sxs-lookup"><span data-stu-id="c3607-115">50</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3607-116">5</span><span class="sxs-lookup"><span data-stu-id="c3607-116">5</span></span></p></td>
<td><p><span data-ttu-id="c3607-117">50</span><span class="sxs-lookup"><span data-stu-id="c3607-117">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3607-118">6</span><span class="sxs-lookup"><span data-stu-id="c3607-118">6</span></span></p></td>
<td><p><span data-ttu-id="c3607-119">50</span><span class="sxs-lookup"><span data-stu-id="c3607-119">50</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3607-120">7</span><span class="sxs-lookup"><span data-stu-id="c3607-120">7</span></span></p></td>
<td><p><span data-ttu-id="c3607-121">50</span><span class="sxs-lookup"><span data-stu-id="c3607-121">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3607-122">No8</span><span class="sxs-lookup"><span data-stu-id="c3607-122">8</span></span></p></td>
<td><p><span data-ttu-id="c3607-123">4550</span><span class="sxs-lookup"><span data-stu-id="c3607-123">4550</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3607-124">@</span><span class="sxs-lookup"><span data-stu-id="c3607-124">9</span></span></p></td>
<td><p><span data-ttu-id="c3607-125">50</span><span class="sxs-lookup"><span data-stu-id="c3607-125">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3607-126">5-10</span><span class="sxs-lookup"><span data-stu-id="c3607-126">10</span></span></p></td>
<td><p><span data-ttu-id="c3607-127">50</span><span class="sxs-lookup"><span data-stu-id="c3607-127">50</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c3607-128">Среднее значение этого времени — 500 миллисекунд (5000 делится на 10).</span><span class="sxs-lookup"><span data-stu-id="c3607-128">The average for those roundtrip times is 500 milliseconds (5000 divided by 10).</span></span> <span data-ttu-id="c3607-129">500 миллисекунд — это очень большое время обмена данными; как следствие, вы можете полагать, что у вас серьезная проблема с перегрузкой сети.</span><span class="sxs-lookup"><span data-stu-id="c3607-129">Five hundred milliseconds is an extremely large roundtrip time; as a result, you might believe that you have a serious problem with network congestion.</span></span> <span data-ttu-id="c3607-130">(Обычно время обмена данными является результатом перегруженных сетей.)</span><span class="sxs-lookup"><span data-stu-id="c3607-130">(Long roundtrip times are typically the result of overloaded networks.)</span></span>

<span data-ttu-id="c3607-131">В реальной ситуации, вероятнее всего, 90 % вызовов будут иметь оптимальное значение времени цикла, тогда как один неудачный вызов сведет на нет все результаты.</span><span class="sxs-lookup"><span data-stu-id="c3607-131">In reality, of course, 90% of your calls had excellent round trip times; you merely had one bad call that skewed the overall results.</span></span> <span data-ttu-id="c3607-132">Если вы просмотрии среднее время обмена данными, вы можете перейти к очень неверному завершению.</span><span class="sxs-lookup"><span data-stu-id="c3607-132">If you only look at the average roundtrip time you might jump to a very wrong conclusion.</span></span>

<span data-ttu-id="c3607-p104">Отчет о распределении метрик качества среды позволяет избежать неправильных выводов, представляя визуализацию распределения определенных метрик (таких как время цикла). Эти диаграммы четко показывают, что девять вызовов были нормальными, а один — очень плохим. Очевидно, что может потребоваться дальнейшее выяснение причин сбоя этого вызова. Однако сама возможность узнать, что 9 из 10 вызовов были беспроблемными, позволяет избежать внесения существенных изменений в сеть (по крайней мере на данном этапе).</span><span class="sxs-lookup"><span data-stu-id="c3607-p104">The Media Quality Metrics Distribution Report helps you avoid jumping to wrong conclusions by showing you a graphical distribution of a specified metric (such as round trip time). These graphs can help make it clear that you had nine very good calls and one very bad call. Admittedly, you might still want to further investigate that one call; however, the fact that 9 out of the 10 calls were very good suggests that there is no reason to make any drastic changes to your network, at least not at this point in time.</span></span>

<div>

## <a name="filters"></a><span data-ttu-id="c3607-136">Фильтры</span><span class="sxs-lookup"><span data-stu-id="c3607-136">Filters</span></span>

<span data-ttu-id="c3607-p105">Фильтры позволяют получать более точные и актуальные наборы данных или просматривать возвращаемые данные в разных комбинациях. В следующей таблице перечислены фильтры, которые можно использовать в отчете по распределению метрик качества среды.</span><span class="sxs-lookup"><span data-stu-id="c3607-p105">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the Media Quality Metrics Distribution Report.</span></span>

### <a name="media-quality-metrics-distribution-report-filters"></a><span data-ttu-id="c3607-139">Фильтры отчета по распределению метрик качества среды</span><span class="sxs-lookup"><span data-stu-id="c3607-139">Media Quality Metrics Distribution Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c3607-140">Имя</span><span class="sxs-lookup"><span data-stu-id="c3607-140">Name</span></span></th>
<th><span data-ttu-id="c3607-141">Описание</span><span class="sxs-lookup"><span data-stu-id="c3607-141">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c3607-142"><strong>От</strong></span><span class="sxs-lookup"><span data-stu-id="c3607-142"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="c3607-p106">Начальные дата/время для временного диапазона. Чтобы просмотреть данные по часам, введите начальные дату и время следующим образом:</span><span class="sxs-lookup"><span data-stu-id="c3607-p106">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="c3607-145">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="c3607-145">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="c3607-p107">Если вы не вводите начальное время, отчет автоматически начинается с 12:00 AM указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</span><span class="sxs-lookup"><span data-stu-id="c3607-p107">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="c3607-148">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="c3607-148">7/7/2012</span></span></p>
<p><span data-ttu-id="c3607-149">Чтобы просмотреть данные за неделю или месяц, введите дату, выпадающую на любое время в рамках недели или месяца, которые вы хотите просмотреть (вам не требуется вводить первый день недели или месяца):</span><span class="sxs-lookup"><span data-stu-id="c3607-149">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="c3607-150">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="c3607-150">7/3/2012</span></span></p>
<p><span data-ttu-id="c3607-151">Недели всегда отсчитываются с воскресенья по субботу.</span><span class="sxs-lookup"><span data-stu-id="c3607-151">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3607-152"><strong>До</strong></span><span class="sxs-lookup"><span data-stu-id="c3607-152"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="c3607-p108">Конечные дата/время для временного диапазона. Чтобы просмотреть данные по часам, введите конечные дату и время следующим образом:</span><span class="sxs-lookup"><span data-stu-id="c3607-p108">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="c3607-155">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="c3607-155">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="c3607-p109">Если вы не вводите конечное время, отчет автоматически заканчивается в 12:00 AM указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</span><span class="sxs-lookup"><span data-stu-id="c3607-p109">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="c3607-158">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="c3607-158">7/7/2012</span></span></p>
<p><span data-ttu-id="c3607-159">Чтобы просмотреть данные за неделю или месяц, введите дату, выпадающую на любое время в рамках недели или месяца, которые вы хотите просмотреть (вам не требуется вводить первый день недели или месяца):</span><span class="sxs-lookup"><span data-stu-id="c3607-159">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="c3607-160">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="c3607-160">7/3/2012</span></span></p>
<p><span data-ttu-id="c3607-161">Недели всегда отсчитываются с воскресенья по субботу.</span><span class="sxs-lookup"><span data-stu-id="c3607-161">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3607-162"><strong>Минимальное значение на оси x</strong></span><span class="sxs-lookup"><span data-stu-id="c3607-162"><strong>Minimum in x axis</strong></span></span></p></td>
<td><p><span data-ttu-id="c3607-163">Минимальное значение будет отображаться на оси X диаграммы.</span><span class="sxs-lookup"><span data-stu-id="c3607-163">Lowest value to be displayed on the X axis of the graph.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3607-164"><strong>Максимальное значение на оси x</strong></span><span class="sxs-lookup"><span data-stu-id="c3607-164"><strong>Maximum in x axis</strong></span></span></p></td>
<td><p><span data-ttu-id="c3607-165">Максимальное значение будет отображаться на оси X диаграммы.</span><span class="sxs-lookup"><span data-stu-id="c3607-165">Highest value to be displayed on the X axis of the graph.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3607-166"><strong>Тип доступа</strong></span><span class="sxs-lookup"><span data-stu-id="c3607-166"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="c3607-p110">Определяет, был ли клиент зарегистрирован во внутренней сети или внешней сети при выполнении вызова. Выберите один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="c3607-p110">Indicates whether the client was logged on to the internal network or the external network when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="c3607-169">[All] (Все)</span><span class="sxs-lookup"><span data-stu-id="c3607-169">[All]</span></span></p></li>
<li><p><span data-ttu-id="c3607-170">Internal</span><span class="sxs-lookup"><span data-stu-id="c3607-170">Internal</span></span></p></li>
<li><p><span data-ttu-id="c3607-171">Внешний</span><span class="sxs-lookup"><span data-stu-id="c3607-171">External</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3607-172"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="c3607-172"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="c3607-p111">Указывает, использовал ли внешний клиент подключение посредством виртуальной частной сети (VPN) при выполнении вызова. Выберите один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="c3607-p111">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="c3607-175">[All] (Все)</span><span class="sxs-lookup"><span data-stu-id="c3607-175">[All]</span></span></p></li>
<li><p><span data-ttu-id="c3607-176">VPN;</span><span class="sxs-lookup"><span data-stu-id="c3607-176">VPN</span></span></p></li>
<li><p><span data-ttu-id="c3607-177">Не VPN</span><span class="sxs-lookup"><span data-stu-id="c3607-177">Non-VPN</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3607-178"><strong>Тип сети</strong></span><span class="sxs-lookup"><span data-stu-id="c3607-178"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="c3607-p112">Определяет тип сети, к которой был подключен клиент при выполнении вызова. Выберите один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="c3607-p112">Indicates the type of network the client was connected to when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="c3607-181">[All] (Все)</span><span class="sxs-lookup"><span data-stu-id="c3607-181">[All]</span></span></p></li>
<li><p><span data-ttu-id="c3607-182">Проводная</span><span class="sxs-lookup"><span data-stu-id="c3607-182">Wired</span></span></p></li>
<li><p><span data-ttu-id="c3607-183">Беспроводная</span><span class="sxs-lookup"><span data-stu-id="c3607-183">Wireless</span></span></p></li>
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

