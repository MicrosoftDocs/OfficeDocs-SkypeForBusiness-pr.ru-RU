---
title: 'Lync Server 2013: сводный отчет по качеству мультимедиа'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media Quality Summary Report
ms:assetid: 8bd59ad6-3087-49c8-b692-5573fe2ffcd8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615012(v=OCS.15)
ms:contentKeyID: 48184776
ms.date: 06/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4080460083074f7ad74618034ab2e7910de5e53d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516187"
---
# <a name="media-quality-summary-report-in-lync-server-2013"></a><span data-ttu-id="6de63-102">Сводный отчет по качеству мультимедиа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6de63-102">Media Quality Summary Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6de63-103">_**Последнее изменение темы:** 2016-06-29_</span><span class="sxs-lookup"><span data-stu-id="6de63-103">_**Topic Last Modified:** 2016-06-29_</span></span>

<span data-ttu-id="6de63-104">Сводный отчет по качеству мультимедиа, возможно, является лучшим предложением для анализа качества звонков в организации: он предоставляет подробные метрики качества взаимодействия при вызовах, распределенные по следующим категориям:</span><span class="sxs-lookup"><span data-stu-id="6de63-104">The Media Quality Summary Report is perhaps your best bet for analyzing call quality in your organization: this report provides detailed Quality of Experience (QoE) call metrics broken down into the following categories:</span></span>

  - <span data-ttu-id="6de63-105">Одноранговые вызовы UC (например, Microsoft Lync 2013 to Microsoft Lync 2013 Call)</span><span class="sxs-lookup"><span data-stu-id="6de63-105">UC Peer to Peer Calls (such as a Microsoft Lync 2013 to Microsoft Lync 2013 call)</span></span>

  - <span data-ttu-id="6de63-106">UC Conference Sessions (сеансы конференций в объединенных коммуникациях);</span><span class="sxs-lookup"><span data-stu-id="6de63-106">UC Conference Sessions</span></span>

  - <span data-ttu-id="6de63-107">PSTN Conference Sessions (сеансы конференций в ТСОП);</span><span class="sxs-lookup"><span data-stu-id="6de63-107">PSTN Conference Sessions</span></span>

  - <span data-ttu-id="6de63-108">PSTN Calls: Media Bypass (вызовы в ТСОП: обход сервера-посредника);</span><span class="sxs-lookup"><span data-stu-id="6de63-108">PSTN Calls: Media Bypass</span></span>

  - <span data-ttu-id="6de63-109">PSTN Calls (Non-Bypass): UC Leg (вызовы в ТСОП (без обхода): участок объединенных коммуникаций);</span><span class="sxs-lookup"><span data-stu-id="6de63-109">PSTN Calls (Non-Bypass): UC Leg</span></span>

  - <span data-ttu-id="6de63-110">PSTN Calls (Non-Bypass): Gateway Leg (вызовы в ТСОП (без обхода): участок шлюза);</span><span class="sxs-lookup"><span data-stu-id="6de63-110">PSTN Calls (Non-Bypass): Gateway Leg</span></span>

  - <span data-ttu-id="6de63-111">другие типы вызовов.</span><span class="sxs-lookup"><span data-stu-id="6de63-111">Other Call Types</span></span>

<span data-ttu-id="6de63-112">При первом открытии отчета отображается сводка по каждой из этих категорий.</span><span class="sxs-lookup"><span data-stu-id="6de63-112">When you first open the report, you see summary information for each of these categories.</span></span> <span data-ttu-id="6de63-113">Не покидая отчет, вы можете развернуть каждую категорию, чтобы просмотреть подкатегории, такие как вызовы, выполненные из Office Communicator 2007 R2, в Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="6de63-113">Without leaving the report, you can expand each category to look at subcategories such as calls made from Office Communicator 2007 R2 to Lync 2013.</span></span> <span data-ttu-id="6de63-114">Затем можно также детализировать эти подкатегории, чтобы просмотреть сведения о каждом вызове, сделанном в этой подкатегории.</span><span class="sxs-lookup"><span data-stu-id="6de63-114">In turn, you can then drill down into these subcategories to see details about each call made within that subcategory.</span></span>

<span data-ttu-id="6de63-115">В Microsoft Lync Server 2013 сводный отчет по качеству мультимедиа дополнительно разделяет данные на три типа вызовов: голосовые звонки, видеовызовы и вызовы общего доступа к приложениям.</span><span class="sxs-lookup"><span data-stu-id="6de63-115">In Microsoft Lync Server 2013 the Media Quality Summary Report further breaks the data down into three call types: audio calls, video calls, and application sharing calls.</span></span> <span data-ttu-id="6de63-116">Для каждого типа вызова в отчете имеется свой собственный раздел и свой собственный ряд метрик вызова.</span><span class="sxs-lookup"><span data-stu-id="6de63-116">Each call type has its own section in the report, and its own custom set of call metrics.</span></span>

<span data-ttu-id="6de63-117">Кроме того, сводный отчет по качеству мультимедиа позволяет применять фильтры, чтобы сравнивать качество проводных и беспроводных вызовов, внутренних и внешних вызовов, а также вызовов с использованием VPN и вызовов без VPN.</span><span class="sxs-lookup"><span data-stu-id="6de63-117">The Media Quality Summary Report also allows you to apply filters that enable you to compare the call quality of wired calls vs. wireless calls, internal calls vs. external calls, and VPN calls vs. non-VPN calls.</span></span>

<div>

## <a name="accessing-the-media-quality-summary-report"></a><span data-ttu-id="6de63-118">Доступ к сводному отчету по качеству мультимедиа</span><span class="sxs-lookup"><span data-stu-id="6de63-118">Accessing the Media Quality Summary Report</span></span>

<span data-ttu-id="6de63-119">Сводный отчет по качеству мультимедиа можно вызвать на домашней странице отчетов наблюдения.</span><span class="sxs-lookup"><span data-stu-id="6de63-119">The Media Quality Summary Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="6de63-120">Вы можете перейти к [отчету по списку обзвона в Lync Server 2013](lync-server-2013-call-list-report.md) , щелкнув один из следующих показателей:</span><span class="sxs-lookup"><span data-stu-id="6de63-120">You can drill down to the [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="6de63-121">Объем звонков</span><span class="sxs-lookup"><span data-stu-id="6de63-121">Call volume</span></span>

  - <span data-ttu-id="6de63-122">Poor call percentage (Процент звонков низкого качества)</span><span class="sxs-lookup"><span data-stu-id="6de63-122">Poor call percentage</span></span>

<span data-ttu-id="6de63-123">Кроме того, можно вызвать отчет по распределению метрик качества мультимедиа, щелкнув какую-либо из метрик звонка:</span><span class="sxs-lookup"><span data-stu-id="6de63-123">In addition, you can access the Media Quality Metrics Distribution Report by clicking any of the following audio call metrics:</span></span>

  - <span data-ttu-id="6de63-124">Round trip (ms)
(Круговой путь (мс))</span><span class="sxs-lookup"><span data-stu-id="6de63-124">Round trip (ms)</span></span>

  - <span data-ttu-id="6de63-125">Degradation (MOS) (Снижение (MOS))</span><span class="sxs-lookup"><span data-stu-id="6de63-125">Degradation (MOS)</span></span>

  - <span data-ttu-id="6de63-126">Packet loss (Потеря пакетов)</span><span class="sxs-lookup"><span data-stu-id="6de63-126">Packet loss</span></span>

  - <span data-ttu-id="6de63-127">Jitter (ms) (Дрожание (мс))</span><span class="sxs-lookup"><span data-stu-id="6de63-127">Jitter (ms)</span></span>

  - <span data-ttu-id="6de63-128">Healer concealed ratio (Коэффициент скрытых сэмплов)</span><span class="sxs-lookup"><span data-stu-id="6de63-128">Healer concealed ratio</span></span>

  - <span data-ttu-id="6de63-129">Healer stretched ratio (Коэффициент растянутых сэмплов)</span><span class="sxs-lookup"><span data-stu-id="6de63-129">Healer stretched ratio</span></span>

  - <span data-ttu-id="6de63-130">Healer compressed ratio (Коэффициент сжатых сэмплов)</span><span class="sxs-lookup"><span data-stu-id="6de63-130">Healer compressed ratio</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="6de63-131">Фильтры</span><span class="sxs-lookup"><span data-stu-id="6de63-131">Filters</span></span>

<span data-ttu-id="6de63-p104">Фильтры позволяют получать более адресный набор данных или просматривать полученные данные разными способами. Например, в сводном отчете по качеству мультимедиа можно фильтровать данные по типу доступа (т.е. по внутреннему или внешнему доступу), а также по проводному или беспроводному типу подключения. Кроме того, можно выбрать способ группирования данных. В данном случае вызовы группируются по часу, дню, неделе или месяцу.</span><span class="sxs-lookup"><span data-stu-id="6de63-p104">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Media Quality Summary Report enables you to filter the returned data by such things as access type (that is, interval access vs. external access) or by wired/wireless network connection. You can also choose how data should be grouped. In this case, calls are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="6de63-136">В следующей таблице приведены фильтры, которые можно использовать в сводном отчете по качеству мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="6de63-136">The following table lists the filters that you can use with the Media Quality Summary Report.</span></span>

### <a name="media-quality-summary-report-filters"></a><span data-ttu-id="6de63-137">Фильтры сводного отчета по качеству мультимедиа</span><span class="sxs-lookup"><span data-stu-id="6de63-137">Media Quality Summary Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6de63-138">Имя</span><span class="sxs-lookup"><span data-stu-id="6de63-138">Name</span></span></th>
<th><span data-ttu-id="6de63-139">Описание</span><span class="sxs-lookup"><span data-stu-id="6de63-139">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6de63-140"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="6de63-140"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="6de63-p105">Дата и время начала диапазона. Чтобы просмотреть данные по часам, введите дату и время начала в следующем формате:</span><span class="sxs-lookup"><span data-stu-id="6de63-p105">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="6de63-143">7/7/2012 13:00.</span><span class="sxs-lookup"><span data-stu-id="6de63-143">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="6de63-p106">Если не указать время начала, автоматически будет выбрано время 00:00 указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</span><span class="sxs-lookup"><span data-stu-id="6de63-p106">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="6de63-146">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="6de63-146">7/7/2012</span></span></p>
<p><span data-ttu-id="6de63-147">Для просмотра по неделям или по месяцам введите дату, выпадающую на любой день недели или месяца, который вы хотите просмотреть (это необязательно должен быть первый день недели или месяца):</span><span class="sxs-lookup"><span data-stu-id="6de63-147">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="6de63-148">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="6de63-148">7/3/2012</span></span></p>
<p><span data-ttu-id="6de63-149">Неделя всегда начинается с воскресения и заканчивается субботой.</span><span class="sxs-lookup"><span data-stu-id="6de63-149">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6de63-150"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="6de63-150"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="6de63-p107">Дата и время окончания диапазона. Чтобы просмотреть данные по часам, введите дату и время окончания в следующем формате:</span><span class="sxs-lookup"><span data-stu-id="6de63-p107">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="6de63-153">7/7/2012 13:00.</span><span class="sxs-lookup"><span data-stu-id="6de63-153">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="6de63-p108">Если не указать время окончания, автоматически будет выбрано время 00:00 указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</span><span class="sxs-lookup"><span data-stu-id="6de63-p108">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="6de63-156">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="6de63-156">7/7/2012</span></span></p>
<p><span data-ttu-id="6de63-157">Для просмотра по неделям или по месяцам введите дату, выпадающую на любой день недели или месяца, который вы хотите просмотреть (это необязательно должен быть первый день недели или месяца):</span><span class="sxs-lookup"><span data-stu-id="6de63-157">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="6de63-158">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="6de63-158">7/3/2012</span></span></p>
<p><span data-ttu-id="6de63-159">Недели всегда продолжаются с воскресенья по субботу.</span><span class="sxs-lookup"><span data-stu-id="6de63-159">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6de63-160"><strong>Access type (Тип доступа)</strong></span><span class="sxs-lookup"><span data-stu-id="6de63-160"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="6de63-p109">Указывает, вошел ли клиент из внутренней или внешней сети при выполнении звонка. Выберите одно из значений:</span><span class="sxs-lookup"><span data-stu-id="6de63-p109">Indicates whether the client was logged on to the internal network or the external network when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="6de63-163">Ко</span><span class="sxs-lookup"><span data-stu-id="6de63-163">[All]</span></span></p></li>
<li><p><span data-ttu-id="6de63-164">Внутренний</span><span class="sxs-lookup"><span data-stu-id="6de63-164">Internal</span></span></p></li>
<li><p><span data-ttu-id="6de63-165">Внешний</span><span class="sxs-lookup"><span data-stu-id="6de63-165">External</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6de63-166"><strong>Тип сети</strong></span><span class="sxs-lookup"><span data-stu-id="6de63-166"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="6de63-p110">Указание типа сети, к которой был подключен клиент при выполнении вызова. Выберите одно из значений:</span><span class="sxs-lookup"><span data-stu-id="6de63-p110">Indicates the type of network the client was connected to when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="6de63-169">Ко</span><span class="sxs-lookup"><span data-stu-id="6de63-169">[All]</span></span></p></li>
<li><p><span data-ttu-id="6de63-170">Политик</span><span class="sxs-lookup"><span data-stu-id="6de63-170">Wired</span></span></p></li>
<li><p><span data-ttu-id="6de63-171">Инфракрас</span><span class="sxs-lookup"><span data-stu-id="6de63-171">Wireless</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6de63-172"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="6de63-172"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="6de63-p111">Указывает, использовал ли внешний клиент VPN-подключение при выполнении звонка. Выберите одно из значений:</span><span class="sxs-lookup"><span data-stu-id="6de63-p111">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="6de63-175">Ко</span><span class="sxs-lookup"><span data-stu-id="6de63-175">[All]</span></span></p></li>
<li><p><span data-ttu-id="6de63-176">VPN</span><span class="sxs-lookup"><span data-stu-id="6de63-176">VPN</span></span></p></li>
<li><p><span data-ttu-id="6de63-177">Не VPN</span><span class="sxs-lookup"><span data-stu-id="6de63-177">Non-VPN</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="6de63-178">Метрики</span><span class="sxs-lookup"><span data-stu-id="6de63-178">Metrics</span></span>

<span data-ttu-id="6de63-179">В следующей таблице приведены сведения, которые предоставляет сводный отчет по качеству мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="6de63-179">The following table lists the information provided in the Media Quality Summary Report.</span></span>

### <a name="media-quality-summary-report-metrics-audio-call-summary"></a><span data-ttu-id="6de63-180">Метрики сводного отчета по качеству мультимедиа: сводка по голосовым вызовам</span><span class="sxs-lookup"><span data-stu-id="6de63-180">Media Quality Summary Report Metrics: Audio Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6de63-181">Имя</span><span class="sxs-lookup"><span data-stu-id="6de63-181">Name</span></span></th>
<th><span data-ttu-id="6de63-182">Возможность сортировки по этому показателю</span><span class="sxs-lookup"><span data-stu-id="6de63-182">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="6de63-183">Описание</span><span class="sxs-lookup"><span data-stu-id="6de63-183">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6de63-184"><strong>Call type/Endpoint type (Тип вызова/тип конечной точки)</strong></span><span class="sxs-lookup"><span data-stu-id="6de63-184"><strong>Call type/Endpoint type</strong></span></span></p></td>
<td><p><span data-ttu-id="6de63-185">Нет</span><span class="sxs-lookup"><span data-stu-id="6de63-185">No</span></span></p></td>
<td><p><span data-ttu-id="6de63-p112">Если щелкнуть этот элемент, то отчет покажет подробные сведения о вызовах на основе этого типа. Типы вызовов:</span><span class="sxs-lookup"><span data-stu-id="6de63-p112">When you click this item, the report shows detailed information about calls based on that type. Call types include:</span></span></p>
<ul>
<li><p><span data-ttu-id="6de63-188">UC Peer-to-Peer Calls (одноранговые вызовы в объединенных коммуникациях);</span><span class="sxs-lookup"><span data-stu-id="6de63-188">UC Peer-to-Peer Calls</span></span></p></li>
<li><p><span data-ttu-id="6de63-189">UC Conference Sessions (сеансы конференций в объединенных коммуникациях);</span><span class="sxs-lookup"><span data-stu-id="6de63-189">UC Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="6de63-190">PSTN Conference Sessions (сеансы конференций в ТСОП);</span><span class="sxs-lookup"><span data-stu-id="6de63-190">PSTN Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="6de63-191">PSTN Calls: Media Bypass (вызовы в ТСОП: обход сервера-посредника);</span><span class="sxs-lookup"><span data-stu-id="6de63-191">PSTN Calls: Media Bypass</span></span></p></li>
<li><p><span data-ttu-id="6de63-192">PSTN Calls (Non-Bypass): UC Leg (вызовы в ТСОП (без обхода): участок объединенных коммуникаций);</span><span class="sxs-lookup"><span data-stu-id="6de63-192">PSTN Calls (Non-Bypass): UC Leg</span></span></p></li>
<li><p><span data-ttu-id="6de63-193">PSTN Calls (Non-Bypass): Gateway Leg (вызовы в ТСОП (без обхода): участок шлюза);</span><span class="sxs-lookup"><span data-stu-id="6de63-193">PSTN Calls (Non-Bypass): Gateway Leg</span></span></p></li>
<li><p><span data-ttu-id="6de63-194">Other Call Types (другие типы вызовов).</span><span class="sxs-lookup"><span data-stu-id="6de63-194">Other Call Types</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6de63-195"><strong>Call volume (Интенсивность вызовов)</strong></span><span class="sxs-lookup"><span data-stu-id="6de63-195"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="6de63-196">Нет</span><span class="sxs-lookup"><span data-stu-id="6de63-196">No</span></span></p></td>
<td><p><span data-ttu-id="6de63-197">Общее количество вызовов по типу вызова.</span><span class="sxs-lookup"><span data-stu-id="6de63-197">Total number of calls per call type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6de63-198"><strong>Poor call percentage (Процент звонков низкого качества)</strong></span><span class="sxs-lookup"><span data-stu-id="6de63-198"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="6de63-199">Нет</span><span class="sxs-lookup"><span data-stu-id="6de63-199">No</span></span></p></td>
<td><p><span data-ttu-id="6de63-p113">Общее количество звонков, классифицированных как звонки низкого качества. Звонок низкого качества — это любой звонок, хотя бы одна метрика которого превышает допустимое значение (например, звонок с чрезмерным дрожанием).</span><span class="sxs-lookup"><span data-stu-id="6de63-p113">Total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6de63-202"><strong>Call volume (wireless call) (Интенсивность вызовов (беспроводной вызов))</strong></span><span class="sxs-lookup"><span data-stu-id="6de63-202"><strong>Call volume (wireless call)</strong></span></span></p></td>
<td><p><span data-ttu-id="6de63-203">Нет</span><span class="sxs-lookup"><span data-stu-id="6de63-203">No</span></span></p></td>
<td><p><span data-ttu-id="6de63-204">Общее количество вызовов, использовавших беспроводное подключение.</span><span class="sxs-lookup"><span data-stu-id="6de63-204">Total number of calls that used a wireless connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6de63-205"><strong>Call volume (VPN call) (Интенсивность вызовов (через VPN))</strong></span><span class="sxs-lookup"><span data-stu-id="6de63-205"><strong>Call volume (VPN call)</strong></span></span></p></td>
<td><p><span data-ttu-id="6de63-206">Нет</span><span class="sxs-lookup"><span data-stu-id="6de63-206">No</span></span></p></td>
<td><p><span data-ttu-id="6de63-207">Общее количество вызовов, использовавших подключение через VPN.</span><span class="sxs-lookup"><span data-stu-id="6de63-207">Total number of calls that used a VPN connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6de63-208"><strong>Call volume (external call) (Интенсивность вызовов (внешние вызовы))</strong></span><span class="sxs-lookup"><span data-stu-id="6de63-208"><strong>Call volume (external call)</strong></span></span></p></td>
<td><p><span data-ttu-id="6de63-209">Нет</span><span class="sxs-lookup"><span data-stu-id="6de63-209">No</span></span></p></td>
<td><p><span data-ttu-id="6de63-210">Количество вызовов, которые использовали внешнее подключение (т.е. подключение за пределами внутренней сети).</span><span class="sxs-lookup"><span data-stu-id="6de63-210">Number of calls that used an external connection (that is, a connection outside the internal network).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6de63-211"><strong>Round trip (ms) (Круговой путь (мс))</strong></span><span class="sxs-lookup"><span data-stu-id="6de63-211"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="6de63-212">Нет</span><span class="sxs-lookup"><span data-stu-id="6de63-212">No</span></span></p></td>
<td><p><span data-ttu-id="6de63-p114">Среднее время (в миллисекундах), которое требуется пакету транспортного протокола в режиме реального времени (пакету протокола RTP) на переход к другой конечной точке и возвращение назад. Приемлемым по качеству считается круговой путь не дольше 100 миллисекунд.</span><span class="sxs-lookup"><span data-stu-id="6de63-p114">Average amount of (in milliseconds) required for a real-time transport protocol (RTP) packet to travel to another endpoint and then back. Round-trip times of 100 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="6de63-p115">Высокие значения кругового пути могут быть следствием маршрутизации международных вызовов, неправильной настройки маршрутизации или перегруженности сервера мультимедиа. Высокие значения кругового пути осложняют проведение двусторонних бесед в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="6de63-p115">High round-trip values can be caused by international call routing, a routing misconfiguration, or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6de63-217"><strong>Degradation (MOS) (Снижение (MOS))</strong></span><span class="sxs-lookup"><span data-stu-id="6de63-217"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="6de63-218">Нет</span><span class="sxs-lookup"><span data-stu-id="6de63-218">No</span></span></p></td>
<td><p><span data-ttu-id="6de63-219">Средняя величина снижения экспертной оценки разборчивости речи (MOS) во время вызова.</span><span class="sxs-lookup"><span data-stu-id="6de63-219">Average amount of mean opinion score (MOS) degradation experienced during a call.</span></span> <span data-ttu-id="6de63-220">Значение снижения может быть в диапазоне от 0.0 до 5.0.</span><span class="sxs-lookup"><span data-stu-id="6de63-220">Degradation values can range from a low of 0.0 to a high of 5.0.</span></span> <span data-ttu-id="6de63-221">Значение не выше 0.5 является приемлемым уровнем снижения.</span><span class="sxs-lookup"><span data-stu-id="6de63-221">A value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="6de63-222">Традиционно средние экспертные оценки разборчивости речи вычислялись по оценкам пользователей качества вызова по шкале от 1 до 5.</span><span class="sxs-lookup"><span data-stu-id="6de63-222">Historically, mean options scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="6de63-223">В Lync Server Lync Server использует набор алгоритмов для прогнозирования того, как пользователи будут оценены при вызове.</span><span class="sxs-lookup"><span data-stu-id="6de63-223">In Lync Server, Lync Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="6de63-p117">Высокие значения снижения могут быть вызваны перегруженностью, нехваткой пропускной способности, перегруженность или помехами в беспроводной сети, а также перегруженностью сервера мультимедиа или конечной точки. Высокие значения могут привести к искажению или потере звука.</span><span class="sxs-lookup"><span data-stu-id="6de63-p117">High degradation values can be caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server or endpoint. High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6de63-226"><strong>Packet loss (Потеря пакетов)</strong></span><span class="sxs-lookup"><span data-stu-id="6de63-226"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="6de63-227">Нет</span><span class="sxs-lookup"><span data-stu-id="6de63-227">No</span></span></p></td>
<td><p><span data-ttu-id="6de63-p118">Средний показатель потери пакетов протокола RTP. (Потеря пакетов происходит, когда пакеты протокола RTP, который используется для передачи звука и видео в Интернете, не достигают места своего назначения.) Высокие показатели потери пакетов обычно бывают следствием перегруженности, нехватки пропускной способности, перегруженности или помех в беспроводной сети, а также перегруженности сервера мультимедиа. Потеря пакетов обычно приводит к искажению или потере звука..</span><span class="sxs-lookup"><span data-stu-id="6de63-p118">Average rate of RTP packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6de63-231"><strong>Дрожание (мс)</strong></span><span class="sxs-lookup"><span data-stu-id="6de63-231"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="6de63-232">Нет</span><span class="sxs-lookup"><span data-stu-id="6de63-232">No</span></span></p></td>
<td><p><span data-ttu-id="6de63-233">Средний уровень дрожания, определенный между прибытием пакетов протокола RTP.</span><span class="sxs-lookup"><span data-stu-id="6de63-233">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="6de63-234">(Колебание — это мера &quot; вибрирования &quot; вызова.) Большие значения колебаний обычно вызваны перегрузкой или перегрузкой сервера мультимедиа, что приводит к искажению или потере звука.</span><span class="sxs-lookup"><span data-stu-id="6de63-234">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6de63-235"><strong>Healer concealed ratio (Коэффициент скрытых сэмплов)</strong></span><span class="sxs-lookup"><span data-stu-id="6de63-235"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="6de63-236">Нет</span><span class="sxs-lookup"><span data-stu-id="6de63-236">No</span></span></p></td>
<td><p><span data-ttu-id="6de63-p120">Среднее отношение скрытых звуковых сэмплов к общему количеству сэмплов. (Скрытые звуковые сэмплы — это техника, которая используется для сглаживания резких переходов, которые обычно вызываются потерей сетевых пакетов.) Высокие значения указывают на значительные уровни применения скрытия потерь, вызванных потерей пакетов или дрожанием, что может привести к искажению или потере звука.</span><span class="sxs-lookup"><span data-stu-id="6de63-p120">Average ratio of concealed audio samples to the total to the total number of samples. (A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6de63-239"><strong>Healer stretched ratio (Коэффициент растянутых сэмплов)</strong></span><span class="sxs-lookup"><span data-stu-id="6de63-239"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="6de63-240">Нет</span><span class="sxs-lookup"><span data-stu-id="6de63-240">No</span></span></p></td>
<td><p><span data-ttu-id="6de63-p121">Среднее отношение растянутых звуковых сэмплов к общему количеству сэмплов. (Растянутые звуковые сэмплы — это звук, который растягивается для поддержания качества звонка, когда обнаруживается потерянный сетевой пакет.) Высокие значения указывают на значительные уровни растягивания сэмплов, вызванного дрожанием, что может привести к искажению или потере звука.</span><span class="sxs-lookup"><span data-stu-id="6de63-p121">Average ratio of stretched audio samples to the total to the total number of samples. (Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6de63-243"><strong>Healer compressed ratio (Коэффициент сжатых сэмплов)</strong></span><span class="sxs-lookup"><span data-stu-id="6de63-243"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="6de63-244">Нет</span><span class="sxs-lookup"><span data-stu-id="6de63-244">No</span></span></p></td>
<td><p><span data-ttu-id="6de63-p122">Среднее отношение сжатых звуковых сэмплов к общему количеству сэмплов. (Сжатые звуковые сэмплы — это звук, который сжимается для поддержания качества звонка, когда обнаруживается потерянный сетевой пакет.) Высокие значения указывают на значительные уровни сжатия сэмплов, вызванного дрожанием, что может привести к искажению или потере звука.</span><span class="sxs-lookup"><span data-stu-id="6de63-p122">Average ratio of compressed audio samples to the total number of samples. (Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="media-quality-summary-report-metrics-video-call-summary"></a><span data-ttu-id="6de63-247">Метрики сводного отчета по качеству мультимедиа: сводка по видеовызовам</span><span class="sxs-lookup"><span data-stu-id="6de63-247">Media Quality Summary Report Metrics: Video Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6de63-248">Имя</span><span class="sxs-lookup"><span data-stu-id="6de63-248">Name</span></span></th>
<th><span data-ttu-id="6de63-249">Возможность сортировки по этому показателю</span><span class="sxs-lookup"><span data-stu-id="6de63-249">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="6de63-250">Описание</span><span class="sxs-lookup"><span data-stu-id="6de63-250">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6de63-251"><strong>Call type/Endpoint type (Тип вызова/тип конечной точки)</strong></span><span class="sxs-lookup"><span data-stu-id="6de63-251"><strong>Call type/Endpoint type</strong></span></span></p></td>
<td><p><span data-ttu-id="6de63-252">Нет</span><span class="sxs-lookup"><span data-stu-id="6de63-252">No</span></span></p></td>
<td><p><span data-ttu-id="6de63-p123">Если щелкнуть этот элемент, то отчет покажет подробные сведения о вызовах на основе этого типа. Типы вызовов:</span><span class="sxs-lookup"><span data-stu-id="6de63-p123">When you click this item, the report shows detailed information about calls based on that type. Call types include:</span></span></p>
<ul>
<li><p><span data-ttu-id="6de63-255">UC Peer-to-Peer Calls (одноранговые вызовы в объединенных коммуникациях);</span><span class="sxs-lookup"><span data-stu-id="6de63-255">UC Peer-to-Peer Calls</span></span></p></li>
<li><p><span data-ttu-id="6de63-256">UC Conference Sessions (сеансы конференций в объединенных коммуникациях);</span><span class="sxs-lookup"><span data-stu-id="6de63-256">UC Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="6de63-257">PSTN Conference Sessions (сеансы конференций в ТСОП);</span><span class="sxs-lookup"><span data-stu-id="6de63-257">PSTN Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="6de63-258">PSTN Calls: Media Bypass (вызовы в ТСОП: обход сервера-посредника);</span><span class="sxs-lookup"><span data-stu-id="6de63-258">PSTN Calls: Media Bypass</span></span></p></li>
<li><p><span data-ttu-id="6de63-259">PSTN Calls (Non-Bypass): UC Leg (вызовы в ТСОП (без обхода): участок объединенных коммуникаций);</span><span class="sxs-lookup"><span data-stu-id="6de63-259">PSTN Calls (Non-Bypass): UC Leg</span></span></p></li>
<li><p><span data-ttu-id="6de63-260">PSTN Calls (Non-Bypass): Gateway Leg (вызовы в ТСОП (без обхода): участок шлюза);</span><span class="sxs-lookup"><span data-stu-id="6de63-260">PSTN Calls (Non-Bypass): Gateway Leg</span></span></p></li>
<li><p><span data-ttu-id="6de63-261">Other Call Types (другие типы вызовов).</span><span class="sxs-lookup"><span data-stu-id="6de63-261">Other Call Types</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6de63-262"><strong>Call volume (Интенсивность вызовов)</strong></span><span class="sxs-lookup"><span data-stu-id="6de63-262"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="6de63-263">Нет</span><span class="sxs-lookup"><span data-stu-id="6de63-263">No</span></span></p></td>
<td><p><span data-ttu-id="6de63-264">Общее количество вызовов по типу вызова.</span><span class="sxs-lookup"><span data-stu-id="6de63-264">Total number of calls per call type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6de63-265"><strong>Poor call percentage (Процент звонков низкого качества)</strong></span><span class="sxs-lookup"><span data-stu-id="6de63-265"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="6de63-266">Нет</span><span class="sxs-lookup"><span data-stu-id="6de63-266">No</span></span></p></td>
<td><p><span data-ttu-id="6de63-p124">Общее количество звонков, классифицированных как звонки низкого качества. Звонок низкого качества — это любой звонок, хотя бы одна метрика которого превышает допустимое значение (например, звонок с чрезмерным дрожанием).</span><span class="sxs-lookup"><span data-stu-id="6de63-p124">Total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6de63-269"><strong>Call volume (wireless call) (Интенсивность вызовов (беспроводной вызов))</strong></span><span class="sxs-lookup"><span data-stu-id="6de63-269"><strong>Call volume (wireless call)</strong></span></span></p></td>
<td><p><span data-ttu-id="6de63-270">Нет</span><span class="sxs-lookup"><span data-stu-id="6de63-270">No</span></span></p></td>
<td><p><span data-ttu-id="6de63-271">Общее количество вызовов, использовавших беспроводное подключение.</span><span class="sxs-lookup"><span data-stu-id="6de63-271">Total number of calls that used a wireless connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6de63-272"><strong>Call volume (VPN call) (Интенсивность вызовов (через VPN))</strong></span><span class="sxs-lookup"><span data-stu-id="6de63-272"><strong>Call volume (VPN call)</strong></span></span></p></td>
<td><p><span data-ttu-id="6de63-273">Нет</span><span class="sxs-lookup"><span data-stu-id="6de63-273">No</span></span></p></td>
<td><p><span data-ttu-id="6de63-274">Общее количество вызовов, использовавших подключение через VPN.</span><span class="sxs-lookup"><span data-stu-id="6de63-274">Total number of calls that used a VPN connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6de63-275"><strong>Call volume (external call) (Интенсивность вызовов (внешние вызовы))</strong></span><span class="sxs-lookup"><span data-stu-id="6de63-275"><strong>Call volume (external call)</strong></span></span></p></td>
<td><p><span data-ttu-id="6de63-276">Нет</span><span class="sxs-lookup"><span data-stu-id="6de63-276">No</span></span></p></td>
<td><p><span data-ttu-id="6de63-277">Количество вызовов, которые использовали внешнее подключение (т.е. подключение за пределами внутренней сети).</span><span class="sxs-lookup"><span data-stu-id="6de63-277">Number of calls that used an external connection (that is, a connection outside the internal network).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6de63-278"><strong>Avg bit-rate (Kbits/s) (Средняя скорость потока (Кбит/с))</strong></span><span class="sxs-lookup"><span data-stu-id="6de63-278"><strong>Avg bit-rate (Kbits/s)</strong></span></span></p></td>
<td><p><span data-ttu-id="6de63-279">Нет</span><span class="sxs-lookup"><span data-stu-id="6de63-279">No</span></span></p></td>
<td><p><span data-ttu-id="6de63-280">Средняя скорость потока видео (в килобитах в секунду).</span><span class="sxs-lookup"><span data-stu-id="6de63-280">Average video bit rate (in kilobits per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6de63-281"><strong>Low bit-rate % (% при низкой скорости потока)</strong></span><span class="sxs-lookup"><span data-stu-id="6de63-281"><strong>Low bit-rate %</strong></span></span></p></td>
<td><p><span data-ttu-id="6de63-282">Нет</span><span class="sxs-lookup"><span data-stu-id="6de63-282">No</span></span></p></td>
<td><p><span data-ttu-id="6de63-283">Процент вызовов при низкой скорости потока видео.</span><span class="sxs-lookup"><span data-stu-id="6de63-283">Percentage of the call where the bit rate was low.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6de63-284"><strong>Outbound packet loss (Потеря исходящих пакетов)</strong></span><span class="sxs-lookup"><span data-stu-id="6de63-284"><strong>Outbound packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="6de63-285">Нет</span><span class="sxs-lookup"><span data-stu-id="6de63-285">No</span></span></p></td>
<td><p><span data-ttu-id="6de63-p125">Потеря исходящих пакетов транспортного протокола в режиме реального времени (пакетов протокола RTP). (Потеря пакетов происходит, когда пакеты протокола RTP, который используется для передачи звука и видео в Интернете, не достигают места своего назначения.) Высокие уровни потерь обычно бывают следствием перегруженности, нехватки пропускной способности, перегруженности или помех в беспроводной сети, а также перегруженности сервера мультимедиа. Потеря пакетов обычно приводит к искажению или потере звука..</span><span class="sxs-lookup"><span data-stu-id="6de63-p125">Real-Time Transport Protocol (RTP) packet loss for outbound packets. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6de63-289"><strong>Frozen frame % (% замороженных кадров)</strong></span><span class="sxs-lookup"><span data-stu-id="6de63-289"><strong>Frozen frame %</strong></span></span></p></td>
<td><p><span data-ttu-id="6de63-290">Нет</span><span class="sxs-lookup"><span data-stu-id="6de63-290">No</span></span></p></td>
<td><p><span data-ttu-id="6de63-p126">Процент "замороженных" кадров. В замороженном кадре видео перестает передаваться, а звуковая часть вызова продолжается.</span><span class="sxs-lookup"><span data-stu-id="6de63-p126">Percentage of “frozen” frames. In a frozen frame, the video stops advancing while the audio portion of the call continues.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6de63-293"><strong>Outbound avg frame rate (Средняя скорость исходящих кадров)</strong></span><span class="sxs-lookup"><span data-stu-id="6de63-293"><strong>Outbound avg frame rate</strong></span></span></p></td>
<td><p><span data-ttu-id="6de63-294">Нет</span><span class="sxs-lookup"><span data-stu-id="6de63-294">No</span></span></p></td>
<td><p><span data-ttu-id="6de63-295">Средняя скорость кадров для исходящих передач во время вызова.</span><span class="sxs-lookup"><span data-stu-id="6de63-295">Average frame rate for outbound transmissions during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6de63-296"><strong>Inbound avg frame rate (Средняя скорость входящих кадров)</strong></span><span class="sxs-lookup"><span data-stu-id="6de63-296"><strong>Inbound avg frame rate</strong></span></span></p></td>
<td><p><span data-ttu-id="6de63-297">Нет</span><span class="sxs-lookup"><span data-stu-id="6de63-297">No</span></span></p></td>
<td><p><span data-ttu-id="6de63-298">Средняя скорость кадров для входящих передач во время вызова.</span><span class="sxs-lookup"><span data-stu-id="6de63-298">Average frame rate for incoming transmissions during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6de63-299"><strong>Inbound low frame rate % (% вызовов при низкой скорости входящих кадров)</strong></span><span class="sxs-lookup"><span data-stu-id="6de63-299"><strong>Inbound low frame rate %</strong></span></span></p></td>
<td><p><span data-ttu-id="6de63-300">Нет</span><span class="sxs-lookup"><span data-stu-id="6de63-300">No</span></span></p></td>
<td><p><span data-ttu-id="6de63-301">Процент вызовов, когда скорость потока входящего видео была низкой.</span><span class="sxs-lookup"><span data-stu-id="6de63-301">Percentage of the call where the bit rate for incoming video was low.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6de63-302"><strong>Client health % (% работоспособности клиента)</strong></span><span class="sxs-lookup"><span data-stu-id="6de63-302"><strong>Client health %</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6de63-303">Указывает относительную работоспособность клиентского устройства во время вызова.</span><span class="sxs-lookup"><span data-stu-id="6de63-303">Indicates the relative health of the client device during the call.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="media-quality-summary-report-metrics-application-sharing-call-summary"></a><span data-ttu-id="6de63-304">Метрики сводного отчета по качеству мультимедиа: сводка по вызовам с общим доступом к приложениям</span><span class="sxs-lookup"><span data-stu-id="6de63-304">Media Quality Summary Report Metrics: Application Sharing Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6de63-305">Имя</span><span class="sxs-lookup"><span data-stu-id="6de63-305">Name</span></span></th>
<th><span data-ttu-id="6de63-306">Возможность сортировки по этому показателю</span><span class="sxs-lookup"><span data-stu-id="6de63-306">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="6de63-307">Описание</span><span class="sxs-lookup"><span data-stu-id="6de63-307">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6de63-308"><strong>Call type/Endpoint type (Тип вызова/тип конечной точки)</strong></span><span class="sxs-lookup"><span data-stu-id="6de63-308"><strong>Call type/Endpoint type</strong></span></span></p></td>
<td><p><span data-ttu-id="6de63-309">Нет</span><span class="sxs-lookup"><span data-stu-id="6de63-309">No</span></span></p></td>
<td><p><span data-ttu-id="6de63-p127">Если щелкнуть этот элемент, то отчет покажет подробные сведения о вызовах на основе этого типа. Типы вызовов:</span><span class="sxs-lookup"><span data-stu-id="6de63-p127">When you click this item, the report shows detailed information about calls based on that type. Call types include:</span></span></p>
<ul>
<li><p><span data-ttu-id="6de63-312">UC Peer-to-Peer Calls (одноранговые вызовы в объединенных коммуникациях);</span><span class="sxs-lookup"><span data-stu-id="6de63-312">UC Peer-to-Peer Calls</span></span></p></li>
<li><p><span data-ttu-id="6de63-313">UC Conference Sessions (сеансы конференций в объединенных коммуникациях);</span><span class="sxs-lookup"><span data-stu-id="6de63-313">UC Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="6de63-314">PSTN Conference Sessions (сеансы конференций в ТСОП);</span><span class="sxs-lookup"><span data-stu-id="6de63-314">PSTN Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="6de63-315">PSTN Calls: Media Bypass (вызовы в ТСОП: обход сервера-посредника);</span><span class="sxs-lookup"><span data-stu-id="6de63-315">PSTN Calls: Media Bypass</span></span></p></li>
<li><p><span data-ttu-id="6de63-316">PSTN Calls (Non-Bypass): UC Leg (вызовы в ТСОП (без обхода): участок объединенных коммуникаций);</span><span class="sxs-lookup"><span data-stu-id="6de63-316">PSTN Calls (Non-Bypass): UC Leg</span></span></p></li>
<li><p><span data-ttu-id="6de63-317">PSTN Calls (Non-Bypass): Gateway Leg (вызовы в ТСОП (без обхода): участок шлюза);</span><span class="sxs-lookup"><span data-stu-id="6de63-317">PSTN Calls (Non-Bypass): Gateway Leg</span></span></p></li>
<li><p><span data-ttu-id="6de63-318">Other Call Types (другие типы вызовов).</span><span class="sxs-lookup"><span data-stu-id="6de63-318">Other Call Types</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6de63-319"><strong>Call volume (Интенсивность вызовов)</strong></span><span class="sxs-lookup"><span data-stu-id="6de63-319"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="6de63-320">Нет</span><span class="sxs-lookup"><span data-stu-id="6de63-320">No</span></span></p></td>
<td><p><span data-ttu-id="6de63-321">Общее количество вызовов по типу вызова.</span><span class="sxs-lookup"><span data-stu-id="6de63-321">Total number of calls per call type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6de63-322"><strong>Poor call percentage (Процент звонков низкого качества)</strong></span><span class="sxs-lookup"><span data-stu-id="6de63-322"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="6de63-323">Нет</span><span class="sxs-lookup"><span data-stu-id="6de63-323">No</span></span></p></td>
<td><p><span data-ttu-id="6de63-p128">Общее количество звонков, классифицированных как звонки низкого качества. Звонок низкого качества — это любой звонок, хотя бы одна метрика которого превышает допустимое значение (например, звонок с чрезмерным дрожанием).</span><span class="sxs-lookup"><span data-stu-id="6de63-p128">Total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6de63-326"><strong>Call volume (wireless call) (Интенсивность вызовов (беспроводной вызов))</strong></span><span class="sxs-lookup"><span data-stu-id="6de63-326"><strong>Call volume (wireless call)</strong></span></span></p></td>
<td><p><span data-ttu-id="6de63-327">Нет</span><span class="sxs-lookup"><span data-stu-id="6de63-327">No</span></span></p></td>
<td><p><span data-ttu-id="6de63-328">Общее количество вызовов, использовавших беспроводное подключение.</span><span class="sxs-lookup"><span data-stu-id="6de63-328">Total number of calls that used a wireless connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6de63-329"><strong>Call volume (VPN call) (Интенсивность вызовов (через VPN))</strong></span><span class="sxs-lookup"><span data-stu-id="6de63-329"><strong>Call volume (VPN call)</strong></span></span></p></td>
<td><p><span data-ttu-id="6de63-330">Нет</span><span class="sxs-lookup"><span data-stu-id="6de63-330">No</span></span></p></td>
<td><p><span data-ttu-id="6de63-331">Общее количество вызовов, использовавших подключение через VPN.</span><span class="sxs-lookup"><span data-stu-id="6de63-331">Total number of calls that used a VPN connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6de63-332"><strong>Call volume (external call) (Интенсивность вызовов (внешние вызовы))</strong></span><span class="sxs-lookup"><span data-stu-id="6de63-332"><strong>Call volume (external call)</strong></span></span></p></td>
<td><p><span data-ttu-id="6de63-333">Нет</span><span class="sxs-lookup"><span data-stu-id="6de63-333">No</span></span></p></td>
<td><p><span data-ttu-id="6de63-334">Количество вызовов, которые использовали внешнее подключение (т.е. подключение за пределами внутренней сети).</span><span class="sxs-lookup"><span data-stu-id="6de63-334">Number of calls that used an external connection (that is, a connection outside the internal network).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6de63-335"><strong>Дрожание (мс)</strong></span><span class="sxs-lookup"><span data-stu-id="6de63-335"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="6de63-336">Нет</span><span class="sxs-lookup"><span data-stu-id="6de63-336">No</span></span></p></td>
<td><p><span data-ttu-id="6de63-337">Средний уровень дрожания, определенный между прибытием пакетов протокола RTP.</span><span class="sxs-lookup"><span data-stu-id="6de63-337">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="6de63-338">(Колебание — это мера &quot; вибрирования &quot; вызова.) Большие значения колебаний обычно вызваны перегрузкой или перегрузкой сервера мультимедиа, что приводит к искажению или потере звука.</span><span class="sxs-lookup"><span data-stu-id="6de63-338">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6de63-339"><strong>Средняя относительная задержка в одну сторону</strong></span><span class="sxs-lookup"><span data-stu-id="6de63-339"><strong>Avg. relative one way</strong></span></span></p></td>
<td><p><span data-ttu-id="6de63-340">Нет</span><span class="sxs-lookup"><span data-stu-id="6de63-340">No</span></span></p></td>
<td><p><span data-ttu-id="6de63-p130">Средняя относительная задержка в одну сторону между двумя конечными точками медиаданных. Это мера односкачковой задержки.</span><span class="sxs-lookup"><span data-stu-id="6de63-p130">Average relative one-way delay between two media endpoints. This is a single-hop latency measure.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6de63-343"><strong>Средняя задержка обработки элемента RDP</strong></span><span class="sxs-lookup"><span data-stu-id="6de63-343"><strong>Avg. RDP tile processing latency</strong></span></span></p></td>
<td><p><span data-ttu-id="6de63-344">Нет</span><span class="sxs-lookup"><span data-stu-id="6de63-344">No</span></span></p></td>
<td><p><span data-ttu-id="6de63-345">Среднее значение задержки обработки элементов RDP на сервере конференц-связи общего доступа к приложениям во время сеанса просмотра.</span><span class="sxs-lookup"><span data-stu-id="6de63-345">The average RDP tile processing latency in the AS Conferencing Server over the duration of the viewing session.</span></span> <span data-ttu-id="6de63-346">Высокое среднее значение отражает более длительную задержку при просмотре и включает задержку сети.</span><span class="sxs-lookup"><span data-stu-id="6de63-346">A high average reflects a longer delay in the viewing experience, and includes network latency.</span></span> <span data-ttu-id="6de63-347">На перегруженном сервере конференц-связи могут происходить в среднем более длительные задержки.</span><span class="sxs-lookup"><span data-stu-id="6de63-347">An overloaded conferencing server may experience higher average delays.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6de63-348"><strong>Total spoiled tile % (Итоговый % испорченных плиток)</strong></span><span class="sxs-lookup"><span data-stu-id="6de63-348"><strong>Total spoiled tile %</strong></span></span></p></td>
<td><p><span data-ttu-id="6de63-349">Нет</span><span class="sxs-lookup"><span data-stu-id="6de63-349">No</span></span></p></td>
<td><p><span data-ttu-id="6de63-350">Итоговый процент испорченных плиток протокола RDP.</span><span class="sxs-lookup"><span data-stu-id="6de63-350">Total percentage of spoiled RDP tiles.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

