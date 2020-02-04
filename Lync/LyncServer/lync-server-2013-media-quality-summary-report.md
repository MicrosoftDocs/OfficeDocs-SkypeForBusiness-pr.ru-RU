---
title: 'Lync Server 2013: сводный отчет о качестве качества мультимедиа'
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
ms.openlocfilehash: 6980168a2d509bc32b9aa48f30167bca8721fef2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41766090"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-quality-summary-report-in-lync-server-2013"></a><span data-ttu-id="607f6-102">Сводный отчет о качестве качества мультимедиа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="607f6-102">Media Quality Summary Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="607f6-103">_**Тема последнего изменения:** 2016-06-29_</span><span class="sxs-lookup"><span data-stu-id="607f6-103">_**Topic Last Modified:** 2016-06-29_</span></span>

<span data-ttu-id="607f6-104">Сводный отчет по качеству мультимедиа, возможно, является лучшим предложением для анализа качества звонков в организации: он предоставляет подробные метрики качества взаимодействия при вызовах, распределенные по следующим категориям:</span><span class="sxs-lookup"><span data-stu-id="607f6-104">The Media Quality Summary Report is perhaps your best bet for analyzing call quality in your organization: this report provides detailed Quality of Experience (QoE) call metrics broken down into the following categories:</span></span>

  - <span data-ttu-id="607f6-105">Одноранговые вызовы Объединенных коммуникаций (например, Microsoft Lync 2013 to Microsoft Lync 2013)</span><span class="sxs-lookup"><span data-stu-id="607f6-105">UC Peer to Peer Calls (such as a Microsoft Lync 2013 to Microsoft Lync 2013 call)</span></span>

  - <span data-ttu-id="607f6-106">Сеансы конференц-связи по объединенным коммуникациям</span><span class="sxs-lookup"><span data-stu-id="607f6-106">UC Conference Sessions</span></span>

  - <span data-ttu-id="607f6-107">Сеансы конференц-связи по ТСОП</span><span class="sxs-lookup"><span data-stu-id="607f6-107">PSTN Conference Sessions</span></span>

  - <span data-ttu-id="607f6-108">Звонки по ТСОП: обходной канал передачи медиаданных</span><span class="sxs-lookup"><span data-stu-id="607f6-108">PSTN Calls: Media Bypass</span></span>

  - <span data-ttu-id="607f6-109">Звонки по ТСОП (без обхода): ветвь объединенных коммуникаций</span><span class="sxs-lookup"><span data-stu-id="607f6-109">PSTN Calls (Non-Bypass): UC Leg</span></span>

  - <span data-ttu-id="607f6-110">Звонки по ТСОП (без обхода): ветвь шлюза</span><span class="sxs-lookup"><span data-stu-id="607f6-110">PSTN Calls (Non-Bypass): Gateway Leg</span></span>

  - <span data-ttu-id="607f6-111">Другие типы звонков</span><span class="sxs-lookup"><span data-stu-id="607f6-111">Other Call Types</span></span>

<span data-ttu-id="607f6-112">При первом открытии отчета отображается сводка по каждой из этих категорий.</span><span class="sxs-lookup"><span data-stu-id="607f6-112">When you first open the report, you see summary information for each of these categories.</span></span> <span data-ttu-id="607f6-113">Не выходя из отчета, вы можете развернуть каждую категорию, чтобы просмотреть подкатегории, такие как звонки из Office Communicator 2007 R2 в Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="607f6-113">Without leaving the report, you can expand each category to look at subcategories such as calls made from Office Communicator 2007 R2 to Lync 2013.</span></span> <span data-ttu-id="607f6-114">Затем можно также детализировать эти подкатегории, чтобы просмотреть сведения о каждом вызове, сделанном в этой подкатегории.</span><span class="sxs-lookup"><span data-stu-id="607f6-114">In turn, you can then drill down into these subcategories to see details about each call made within that subcategory.</span></span>

<span data-ttu-id="607f6-115">В Microsoft Lync Server 2013 в отчете "Обзор качества мультимедиа" дополнительно разбиваются данные на три типа звонков: голосовые звонки, видеозвонки и обмен звонками между приложениями.</span><span class="sxs-lookup"><span data-stu-id="607f6-115">In Microsoft Lync Server 2013 the Media Quality Summary Report further breaks the data down into three call types: audio calls, video calls, and application sharing calls.</span></span> <span data-ttu-id="607f6-116">Для каждого типа вызова в отчете имеется свой собственный раздел и свой собственный ряд метрик вызова.</span><span class="sxs-lookup"><span data-stu-id="607f6-116">Each call type has its own section in the report, and its own custom set of call metrics.</span></span>

<span data-ttu-id="607f6-117">Кроме того, сводный отчет по качеству мультимедиа позволяет применять фильтры, чтобы сравнивать качество проводных и беспроводных вызовов, внутренних и внешних вызовов, а также вызовов с использованием VPN и вызовов без VPN.</span><span class="sxs-lookup"><span data-stu-id="607f6-117">The Media Quality Summary Report also allows you to apply filters that enable you to compare the call quality of wired calls vs. wireless calls, internal calls vs. external calls, and VPN calls vs. non-VPN calls.</span></span>

<div>

## <a name="accessing-the-media-quality-summary-report"></a><span data-ttu-id="607f6-118">Доступ к сводному отчету по качеству мультимедиа</span><span class="sxs-lookup"><span data-stu-id="607f6-118">Accessing the Media Quality Summary Report</span></span>

<span data-ttu-id="607f6-119">Сводный отчет по качеству мультимедиа можно вызвать на домашней странице отчетов наблюдения.</span><span class="sxs-lookup"><span data-stu-id="607f6-119">The Media Quality Summary Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="607f6-120">Вы можете перейти к [отчету список обзвона в Lync Server 2013](lync-server-2013-call-list-report.md) , щелкнув один из следующих метрик:</span><span class="sxs-lookup"><span data-stu-id="607f6-120">You can drill down to the [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="607f6-121">Громкость вызова</span><span class="sxs-lookup"><span data-stu-id="607f6-121">Call volume</span></span>

  - <span data-ttu-id="607f6-122">Процент звонков низкого качества</span><span class="sxs-lookup"><span data-stu-id="607f6-122">Poor call percentage</span></span>

<span data-ttu-id="607f6-123">Кроме того, можно вызвать отчет по распределению метрик качества мультимедиа, щелкнув какую-либо из метрик звонка:</span><span class="sxs-lookup"><span data-stu-id="607f6-123">In addition, you can access the Media Quality Metrics Distribution Report by clicking any of the following audio call metrics:</span></span>

  - <span data-ttu-id="607f6-124">Круговой путь (мс)</span><span class="sxs-lookup"><span data-stu-id="607f6-124">Round trip (ms)</span></span>

  - <span data-ttu-id="607f6-125">Падение качества (средняя оценка)</span><span class="sxs-lookup"><span data-stu-id="607f6-125">Degradation (MOS)</span></span>

  - <span data-ttu-id="607f6-126">Потеря пакетов</span><span class="sxs-lookup"><span data-stu-id="607f6-126">Packet loss</span></span>

  - <span data-ttu-id="607f6-127">Колебание (мс)</span><span class="sxs-lookup"><span data-stu-id="607f6-127">Jitter (ms)</span></span>

  - <span data-ttu-id="607f6-128">Степень маскированных аудиообразцов</span><span class="sxs-lookup"><span data-stu-id="607f6-128">Healer concealed ratio</span></span>

  - <span data-ttu-id="607f6-129">Степень растянутых образцов</span><span class="sxs-lookup"><span data-stu-id="607f6-129">Healer stretched ratio</span></span>

  - <span data-ttu-id="607f6-130">Степень сжатых аудиообразцов</span><span class="sxs-lookup"><span data-stu-id="607f6-130">Healer compressed ratio</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="607f6-131">Фильтры</span><span class="sxs-lookup"><span data-stu-id="607f6-131">Filters</span></span>

<span data-ttu-id="607f6-p104">Фильтры позволяют получать более адресный набор данных или просматривать полученные данные разными способами. Например, в сводном отчете по качеству мультимедиа можно фильтровать данные по типу доступа (т.е. по внутреннему или внешнему доступу), а также по проводному или беспроводному типу подключения. Кроме того, можно выбрать способ группирования данных. В данном случае вызовы группируются по часу, дню, неделе или месяцу.</span><span class="sxs-lookup"><span data-stu-id="607f6-p104">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Media Quality Summary Report enables you to filter the returned data by such things as access type (that is, interval access vs. external access) or by wired/wireless network connection. You can also choose how data should be grouped. In this case, calls are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="607f6-136">В следующей таблице приведены фильтры, которые можно использовать в сводном отчете по качеству мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="607f6-136">The following table lists the filters that you can use with the Media Quality Summary Report.</span></span>

### <a name="media-quality-summary-report-filters"></a><span data-ttu-id="607f6-137">Фильтры сводного отчета по качеству мультимедиа</span><span class="sxs-lookup"><span data-stu-id="607f6-137">Media Quality Summary Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="607f6-138">Имя</span><span class="sxs-lookup"><span data-stu-id="607f6-138">Name</span></span></th>
<th><span data-ttu-id="607f6-139">Описание</span><span class="sxs-lookup"><span data-stu-id="607f6-139">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="607f6-140"><strong>От</strong></span><span class="sxs-lookup"><span data-stu-id="607f6-140"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="607f6-p105">Начальные дата/время для временного диапазона. Чтобы просмотреть данные по часам, введите начальные дату и время следующим образом:</span><span class="sxs-lookup"><span data-stu-id="607f6-p105">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="607f6-143">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="607f6-143">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="607f6-p106">Если вы не вводите начальное время, отчет автоматически начинается с 12:00 AM указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</span><span class="sxs-lookup"><span data-stu-id="607f6-p106">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="607f6-146">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="607f6-146">7/7/2012</span></span></p>
<p><span data-ttu-id="607f6-147">Чтобы просмотреть данные за неделю или месяц, введите дату, выпадающую на любое время в рамках недели или месяца, которые вы хотите просмотреть (вам не требуется вводить первый день недели или месяца):</span><span class="sxs-lookup"><span data-stu-id="607f6-147">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="607f6-148">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="607f6-148">7/3/2012</span></span></p>
<p><span data-ttu-id="607f6-149">Недели всегда отсчитываются с воскресенья по субботу.</span><span class="sxs-lookup"><span data-stu-id="607f6-149">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="607f6-150"><strong>До</strong></span><span class="sxs-lookup"><span data-stu-id="607f6-150"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="607f6-p107">Конечные дата/время для временного диапазона. Чтобы просмотреть данные по часам, введите конечные дату и время следующим образом:</span><span class="sxs-lookup"><span data-stu-id="607f6-p107">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="607f6-153">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="607f6-153">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="607f6-p108">Если вы не вводите конечное время, отчет автоматически заканчивается в 12:00 AM указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</span><span class="sxs-lookup"><span data-stu-id="607f6-p108">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="607f6-156">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="607f6-156">7/7/2012</span></span></p>
<p><span data-ttu-id="607f6-157">Чтобы просмотреть данные за неделю или месяц, введите дату, выпадающую на любое время в рамках недели или месяца, которые вы хотите просмотреть (вам не требуется вводить первый день недели или месяца):</span><span class="sxs-lookup"><span data-stu-id="607f6-157">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="607f6-158">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="607f6-158">7/3/2012</span></span></p>
<p><span data-ttu-id="607f6-159">Недели всегда отсчитываются с воскресенья по субботу.</span><span class="sxs-lookup"><span data-stu-id="607f6-159">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="607f6-160"><strong>Тип доступа</strong></span><span class="sxs-lookup"><span data-stu-id="607f6-160"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="607f6-p109">Определяет, был ли клиент зарегистрирован во внутренней сети или внешней сети при выполнении вызова. Выберите один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="607f6-p109">Indicates whether the client was logged on to the internal network or the external network when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="607f6-163">[All] (Все)</span><span class="sxs-lookup"><span data-stu-id="607f6-163">[All]</span></span></p></li>
<li><p><span data-ttu-id="607f6-164">Internal</span><span class="sxs-lookup"><span data-stu-id="607f6-164">Internal</span></span></p></li>
<li><p><span data-ttu-id="607f6-165">Внешняя</span><span class="sxs-lookup"><span data-stu-id="607f6-165">External</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="607f6-166"><strong>Тип сети</strong></span><span class="sxs-lookup"><span data-stu-id="607f6-166"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="607f6-p110">Определяет тип сети, к которой был подключен клиент при выполнении вызова. Выберите один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="607f6-p110">Indicates the type of network the client was connected to when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="607f6-169">[All] (Все)</span><span class="sxs-lookup"><span data-stu-id="607f6-169">[All]</span></span></p></li>
<li><p><span data-ttu-id="607f6-170">Проводная</span><span class="sxs-lookup"><span data-stu-id="607f6-170">Wired</span></span></p></li>
<li><p><span data-ttu-id="607f6-171">Беспроводная</span><span class="sxs-lookup"><span data-stu-id="607f6-171">Wireless</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="607f6-172"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="607f6-172"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="607f6-p111">Указывает, использовал ли внешний клиент подключение посредством виртуальной частной сети (VPN) при выполнении вызова. Выберите один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="607f6-p111">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="607f6-175">[All] (Все)</span><span class="sxs-lookup"><span data-stu-id="607f6-175">[All]</span></span></p></li>
<li><p><span data-ttu-id="607f6-176">VPN;</span><span class="sxs-lookup"><span data-stu-id="607f6-176">VPN</span></span></p></li>
<li><p><span data-ttu-id="607f6-177">Не VPN</span><span class="sxs-lookup"><span data-stu-id="607f6-177">Non-VPN</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="607f6-178">Показатели</span><span class="sxs-lookup"><span data-stu-id="607f6-178">Metrics</span></span>

<span data-ttu-id="607f6-179">В следующей таблице приведены сведения, которые предоставляют сводный отчет по качеству мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="607f6-179">The following table lists the information provided in the Media Quality Summary Report.</span></span>

### <a name="media-quality-summary-report-metrics-audio-call-summary"></a><span data-ttu-id="607f6-180">Метрики сводного отчета по качеству мультимедиа: сводка по голосовым вызовам</span><span class="sxs-lookup"><span data-stu-id="607f6-180">Media Quality Summary Report Metrics: Audio Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="607f6-181">Имя</span><span class="sxs-lookup"><span data-stu-id="607f6-181">Name</span></span></th>
<th><span data-ttu-id="607f6-182">Поддержка сортировки</span><span class="sxs-lookup"><span data-stu-id="607f6-182">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="607f6-183">Описание</span><span class="sxs-lookup"><span data-stu-id="607f6-183">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="607f6-184"><strong>Тип звонка и конечной точки</strong></span><span class="sxs-lookup"><span data-stu-id="607f6-184"><strong>Call type/Endpoint type</strong></span></span></p></td>
<td><p><span data-ttu-id="607f6-185">Нет</span><span class="sxs-lookup"><span data-stu-id="607f6-185">No</span></span></p></td>
<td><p><span data-ttu-id="607f6-p112">При щелчке этого элемента отчет предоставляет подробные сведения о звонках, основанных на этом типе. Типы звонков:</span><span class="sxs-lookup"><span data-stu-id="607f6-p112">When you click this item, the report shows detailed information about calls based on that type. Call types include:</span></span></p>
<ul>
<li><p><span data-ttu-id="607f6-188">Одноранговые звонки по объединенным коммуникациям</span><span class="sxs-lookup"><span data-stu-id="607f6-188">UC Peer-to-Peer Calls</span></span></p></li>
<li><p><span data-ttu-id="607f6-189">Сеансы конференц-связи по объединенным коммуникациям</span><span class="sxs-lookup"><span data-stu-id="607f6-189">UC Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="607f6-190">Сеансы конференц-связи по ТСОП</span><span class="sxs-lookup"><span data-stu-id="607f6-190">PSTN Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="607f6-191">Звонки по ТСОП: обходной канал передачи медиаданных</span><span class="sxs-lookup"><span data-stu-id="607f6-191">PSTN Calls: Media Bypass</span></span></p></li>
<li><p><span data-ttu-id="607f6-192">Звонки по ТСОП (без обхода): ветвь объединенных коммуникаций</span><span class="sxs-lookup"><span data-stu-id="607f6-192">PSTN Calls (Non-Bypass): UC Leg</span></span></p></li>
<li><p><span data-ttu-id="607f6-193">Звонки по ТСОП (без обхода): ветвь шлюза</span><span class="sxs-lookup"><span data-stu-id="607f6-193">PSTN Calls (Non-Bypass): Gateway Leg</span></span></p></li>
<li><p><span data-ttu-id="607f6-194">Другие типы звонков</span><span class="sxs-lookup"><span data-stu-id="607f6-194">Other Call Types</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="607f6-195"><strong>Громкость вызова</strong></span><span class="sxs-lookup"><span data-stu-id="607f6-195"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="607f6-196">Нет</span><span class="sxs-lookup"><span data-stu-id="607f6-196">No</span></span></p></td>
<td><p><span data-ttu-id="607f6-197">Общее количество звонков на тип звонка.</span><span class="sxs-lookup"><span data-stu-id="607f6-197">Total number of calls per call type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="607f6-198"><strong>Процент звонков низкого качества</strong></span><span class="sxs-lookup"><span data-stu-id="607f6-198"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="607f6-199">Нет</span><span class="sxs-lookup"><span data-stu-id="607f6-199">No</span></span></p></td>
<td><p><span data-ttu-id="607f6-p113">Общее количество звонков, классифицированных как звонки низкого качества. Звонок низкого качества – это любой звонок, хотя бы одна метрика которого превышает допустимое значение (например, звонок с чрезмерным дрожанием).</span><span class="sxs-lookup"><span data-stu-id="607f6-p113">Total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="607f6-202"><strong>Объем звонков (звонок по беспроводной сети)</strong></span><span class="sxs-lookup"><span data-stu-id="607f6-202"><strong>Call volume (wireless call)</strong></span></span></p></td>
<td><p><span data-ttu-id="607f6-203">Нет</span><span class="sxs-lookup"><span data-stu-id="607f6-203">No</span></span></p></td>
<td><p><span data-ttu-id="607f6-204">Общее количество звонков, при которых используется беспроводное подключение.</span><span class="sxs-lookup"><span data-stu-id="607f6-204">Total number of calls that used a wireless connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="607f6-205"><strong>Объем звонков (звонок по сети VPN)</strong></span><span class="sxs-lookup"><span data-stu-id="607f6-205"><strong>Call volume (VPN call)</strong></span></span></p></td>
<td><p><span data-ttu-id="607f6-206">Нет</span><span class="sxs-lookup"><span data-stu-id="607f6-206">No</span></span></p></td>
<td><p><span data-ttu-id="607f6-207">Общее количество звонков, при которых используется подключение по сети VPN.</span><span class="sxs-lookup"><span data-stu-id="607f6-207">Total number of calls that used a VPN connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="607f6-208"><strong>Объем звонков (внешний звонок)</strong></span><span class="sxs-lookup"><span data-stu-id="607f6-208"><strong>Call volume (external call)</strong></span></span></p></td>
<td><p><span data-ttu-id="607f6-209">Нет</span><span class="sxs-lookup"><span data-stu-id="607f6-209">No</span></span></p></td>
<td><p><span data-ttu-id="607f6-210">Количество звонков, при которых используется внешнее подключение (то есть подключение за пределами внутренней сети).</span><span class="sxs-lookup"><span data-stu-id="607f6-210">Number of calls that used an external connection (that is, a connection outside the internal network).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="607f6-211"><strong>Круговой путь (мс)</strong></span><span class="sxs-lookup"><span data-stu-id="607f6-211"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="607f6-212">Нет</span><span class="sxs-lookup"><span data-stu-id="607f6-212">No</span></span></p></td>
<td><p><span data-ttu-id="607f6-p114">Среднее время (в миллисекундах) требуемое для передачи пакета протокола транспорта реального времени (RTP) в другую конечную точку и обратно. Круговой путь в 100 и меньше миллисекунд считается допустимым.</span><span class="sxs-lookup"><span data-stu-id="607f6-p114">Average amount of (in milliseconds) required for a real-time transport protocol (RTP) packet to travel to another endpoint and then back. Round-trip times of 100 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="607f6-p115">Высокие значения прохождения кругового пути могут быть вызваны маршрутизацией международных звонков, неправильной настройкой маршрутизацией или перегрузкой сервера-посредника. Большое время кругового пути приводит к трудностям при обслуживании двунаправленных аудиоразговоров.</span><span class="sxs-lookup"><span data-stu-id="607f6-p115">High round-trip values can be caused by international call routing, a routing misconfiguration, or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="607f6-217"><strong>Падение качества (средняя оценка)</strong></span><span class="sxs-lookup"><span data-stu-id="607f6-217"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="607f6-218">Нет</span><span class="sxs-lookup"><span data-stu-id="607f6-218">No</span></span></p></td>
<td><p><span data-ttu-id="607f6-219">Средняя экспертная оценка падения качества связи во время звонка.</span><span class="sxs-lookup"><span data-stu-id="607f6-219">Average amount of mean opinion score (MOS) degradation experienced during a call.</span></span> <span data-ttu-id="607f6-220">Значения лежат в диапазоне от 0,0 до 5,0.</span><span class="sxs-lookup"><span data-stu-id="607f6-220">Degradation values can range from a low of 0.0 to a high of 5.0.</span></span> <span data-ttu-id="607f6-221">Значение 0,5 или меньшее обозначает допустимое падение качества.</span><span class="sxs-lookup"><span data-stu-id="607f6-221">A value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="607f6-222">Изначально средние оценки рассчитывались на основе оценок, даваемых звонкам пользователями по шкале от 1 до 5.</span><span class="sxs-lookup"><span data-stu-id="607f6-222">Historically, mean options scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="607f6-223">В Lync Server Lync Server использует набор алгоритмов для прогнозирования того, как пользователи будут оценены при звонке.</span><span class="sxs-lookup"><span data-stu-id="607f6-223">In Lync Server, Lync Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="607f6-p117">Большие оценки падения качества могут быть вызваны перегрузкой сети, недостатком пропускной способности, помехами в беспроводной среде, перегрузкой на сервере-посреднике или конечной точке. Падение качества приводит к искажению или потере аудиосигнала.</span><span class="sxs-lookup"><span data-stu-id="607f6-p117">High degradation values can be caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server or endpoint. High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="607f6-226"><strong>Потеря пакетов</strong></span><span class="sxs-lookup"><span data-stu-id="607f6-226"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="607f6-227">Нет</span><span class="sxs-lookup"><span data-stu-id="607f6-227">No</span></span></p></td>
<td><p><span data-ttu-id="607f6-p118">Среднее значение потери RTP-пакетов. (Пакет считается потерянным, если он не дошел до назначения). Большие значения потери пакетов могут быть вызваны перегрузкой сети, недостатком пропускной способности, помехами в беспроводной среде, перегрузкой на сервере-посреднике. Обычно это приводит к искажению или потере аудиосигнала.</span><span class="sxs-lookup"><span data-stu-id="607f6-p118">Average rate of RTP packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="607f6-231"><strong>Колебание (мс)</strong></span><span class="sxs-lookup"><span data-stu-id="607f6-231"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="607f6-232">Нет</span><span class="sxs-lookup"><span data-stu-id="607f6-232">No</span></span></p></td>
<td><p><span data-ttu-id="607f6-233">Среднее значение колебаний, зарегистрированных между прибытиями пакетов RTP.</span><span class="sxs-lookup"><span data-stu-id="607f6-233">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="607f6-234">(Колебание — это мера &quot;шакинесс&quot; звонка). Обычно значения с высокой степенью колебаний заключаются в результате перегруженности или перегруженного сервера мультимедиа, что приводит к искажению или потере звука.</span><span class="sxs-lookup"><span data-stu-id="607f6-234">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="607f6-235"><strong>Степень маскированных аудиообразцов</strong></span><span class="sxs-lookup"><span data-stu-id="607f6-235"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="607f6-236">Нет</span><span class="sxs-lookup"><span data-stu-id="607f6-236">No</span></span></p></td>
<td><p><span data-ttu-id="607f6-p120">Средняя степень маскированных аудиообразцов по отношению к общему числу образцов. (Маскирование аудио - это методика, которая применяется для сглаживания оборванной передачи, которая обычно происходит при потери сетевых пакетов). Большие значения обозначают частое применение данной методики, вызванной из-за потери пакетов или искажений сигнала.</span><span class="sxs-lookup"><span data-stu-id="607f6-p120">Average ratio of concealed audio samples to the total to the total number of samples. (A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="607f6-239"><strong>Степень растянутых образцов</strong></span><span class="sxs-lookup"><span data-stu-id="607f6-239"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="607f6-240">Нет</span><span class="sxs-lookup"><span data-stu-id="607f6-240">No</span></span></p></td>
<td><p><span data-ttu-id="607f6-p121">Средняя степень растянутых аудиообразцов по отношению к общему числу образцов. (Растягивание аудиопакета - это методика, которая применяется для поддержания качества звонка при обнаружении потери сетевого пакета). Большие значения обозначают частое применение данной методики, вызванное большими искажениями – аудиосигнал звучит как роботизированный.</span><span class="sxs-lookup"><span data-stu-id="607f6-p121">Average ratio of stretched audio samples to the total to the total number of samples. (Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="607f6-243"><strong>Степень сжатых аудиообразцов</strong></span><span class="sxs-lookup"><span data-stu-id="607f6-243"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="607f6-244">Нет</span><span class="sxs-lookup"><span data-stu-id="607f6-244">No</span></span></p></td>
<td><p><span data-ttu-id="607f6-p122">Средняя степень растянутых аудиообразцов по отношению к общему числу образцов. (Сжатие аудиопакета - это методика, которая применяется для поддержания качества звонка при обнаружении потери сетевого пакета). Большие значения обозначают частое применение данной методики, вызванное большими искажениями – аудиосигнал звучит как ускоренный или искаженный.</span><span class="sxs-lookup"><span data-stu-id="607f6-p122">Average ratio of compressed audio samples to the total number of samples. (Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="media-quality-summary-report-metrics-video-call-summary"></a><span data-ttu-id="607f6-247">Метрики сводного отчета по качеству мультимедиа: сводка по видеовызовам</span><span class="sxs-lookup"><span data-stu-id="607f6-247">Media Quality Summary Report Metrics: Video Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="607f6-248">Имя</span><span class="sxs-lookup"><span data-stu-id="607f6-248">Name</span></span></th>
<th><span data-ttu-id="607f6-249">Поддержка сортировки</span><span class="sxs-lookup"><span data-stu-id="607f6-249">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="607f6-250">Описание</span><span class="sxs-lookup"><span data-stu-id="607f6-250">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="607f6-251"><strong>Тип звонка и конечной точки</strong></span><span class="sxs-lookup"><span data-stu-id="607f6-251"><strong>Call type/Endpoint type</strong></span></span></p></td>
<td><p><span data-ttu-id="607f6-252">Нет</span><span class="sxs-lookup"><span data-stu-id="607f6-252">No</span></span></p></td>
<td><p><span data-ttu-id="607f6-p123">При щелчке этого элемента отчет предоставляет подробные сведения о звонках, основанных на этом типе. Типы звонков:</span><span class="sxs-lookup"><span data-stu-id="607f6-p123">When you click this item, the report shows detailed information about calls based on that type. Call types include:</span></span></p>
<ul>
<li><p><span data-ttu-id="607f6-255">Одноранговые звонки по объединенным коммуникациям</span><span class="sxs-lookup"><span data-stu-id="607f6-255">UC Peer-to-Peer Calls</span></span></p></li>
<li><p><span data-ttu-id="607f6-256">Сеансы конференц-связи по объединенным коммуникациям</span><span class="sxs-lookup"><span data-stu-id="607f6-256">UC Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="607f6-257">Сеансы конференц-связи по ТСОП</span><span class="sxs-lookup"><span data-stu-id="607f6-257">PSTN Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="607f6-258">Звонки по ТСОП: обходной канал передачи медиаданных</span><span class="sxs-lookup"><span data-stu-id="607f6-258">PSTN Calls: Media Bypass</span></span></p></li>
<li><p><span data-ttu-id="607f6-259">Звонки по ТСОП (без обхода): ветвь объединенных коммуникаций</span><span class="sxs-lookup"><span data-stu-id="607f6-259">PSTN Calls (Non-Bypass): UC Leg</span></span></p></li>
<li><p><span data-ttu-id="607f6-260">Звонки по ТСОП (без обхода): ветвь шлюза</span><span class="sxs-lookup"><span data-stu-id="607f6-260">PSTN Calls (Non-Bypass): Gateway Leg</span></span></p></li>
<li><p><span data-ttu-id="607f6-261">Другие типы звонков</span><span class="sxs-lookup"><span data-stu-id="607f6-261">Other Call Types</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="607f6-262"><strong>Громкость вызова</strong></span><span class="sxs-lookup"><span data-stu-id="607f6-262"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="607f6-263">Нет</span><span class="sxs-lookup"><span data-stu-id="607f6-263">No</span></span></p></td>
<td><p><span data-ttu-id="607f6-264">Общее количество звонков на тип звонка.</span><span class="sxs-lookup"><span data-stu-id="607f6-264">Total number of calls per call type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="607f6-265"><strong>Процент звонков низкого качества</strong></span><span class="sxs-lookup"><span data-stu-id="607f6-265"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="607f6-266">Нет</span><span class="sxs-lookup"><span data-stu-id="607f6-266">No</span></span></p></td>
<td><p><span data-ttu-id="607f6-p124">Общее количество звонков, классифицированных как звонки низкого качества. Звонок низкого качества – это любой звонок, хотя бы одна метрика которого превышает допустимое значение (например, звонок с чрезмерным дрожанием).</span><span class="sxs-lookup"><span data-stu-id="607f6-p124">Total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="607f6-269"><strong>Объем звонков (звонок по беспроводной сети)</strong></span><span class="sxs-lookup"><span data-stu-id="607f6-269"><strong>Call volume (wireless call)</strong></span></span></p></td>
<td><p><span data-ttu-id="607f6-270">Нет</span><span class="sxs-lookup"><span data-stu-id="607f6-270">No</span></span></p></td>
<td><p><span data-ttu-id="607f6-271">Общее количество звонков, при которых используется беспроводное подключение.</span><span class="sxs-lookup"><span data-stu-id="607f6-271">Total number of calls that used a wireless connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="607f6-272"><strong>Объем звонков (звонок по сети VPN)</strong></span><span class="sxs-lookup"><span data-stu-id="607f6-272"><strong>Call volume (VPN call)</strong></span></span></p></td>
<td><p><span data-ttu-id="607f6-273">Нет</span><span class="sxs-lookup"><span data-stu-id="607f6-273">No</span></span></p></td>
<td><p><span data-ttu-id="607f6-274">Общее количество звонков, при которых используется подключение по сети VPN.</span><span class="sxs-lookup"><span data-stu-id="607f6-274">Total number of calls that used a VPN connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="607f6-275"><strong>Объем звонков (внешний звонок)</strong></span><span class="sxs-lookup"><span data-stu-id="607f6-275"><strong>Call volume (external call)</strong></span></span></p></td>
<td><p><span data-ttu-id="607f6-276">Нет</span><span class="sxs-lookup"><span data-stu-id="607f6-276">No</span></span></p></td>
<td><p><span data-ttu-id="607f6-277">Количество звонков, при которых используется внешнее подключение (то есть подключение за пределами внутренней сети).</span><span class="sxs-lookup"><span data-stu-id="607f6-277">Number of calls that used an external connection (that is, a connection outside the internal network).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="607f6-278"><strong>Средняя скорость потока (кбит/с)</strong></span><span class="sxs-lookup"><span data-stu-id="607f6-278"><strong>Avg bit-rate (Kbits/s)</strong></span></span></p></td>
<td><p><span data-ttu-id="607f6-279">Нет</span><span class="sxs-lookup"><span data-stu-id="607f6-279">No</span></span></p></td>
<td><p><span data-ttu-id="607f6-280">Средняя скорость видеопотока (кбит/с).</span><span class="sxs-lookup"><span data-stu-id="607f6-280">Average video bit rate (in kilobits per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="607f6-281"><strong>Процент низкой скорости потока</strong></span><span class="sxs-lookup"><span data-stu-id="607f6-281"><strong>Low bit-rate %</strong></span></span></p></td>
<td><p><span data-ttu-id="607f6-282">Нет</span><span class="sxs-lookup"><span data-stu-id="607f6-282">No</span></span></p></td>
<td><p><span data-ttu-id="607f6-283">Процент звонков с низкой скоростью потока.</span><span class="sxs-lookup"><span data-stu-id="607f6-283">Percentage of the call where the bit rate was low.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="607f6-284"><strong>Потеря исходящих пакетов</strong></span><span class="sxs-lookup"><span data-stu-id="607f6-284"><strong>Outbound packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="607f6-285">Нет</span><span class="sxs-lookup"><span data-stu-id="607f6-285">No</span></span></p></td>
<td><p><span data-ttu-id="607f6-p125">Потеря исходящих пакетов транспортного протокола в режиме реального времени (пакетов протокола RTP). (Потеря пакетов происходит, когда пакеты протокола RTP, который используется для передачи звука и видео в Интернете, не достигают места своего назначения.) Высокие уровни потерь обычно бывают следствием перегруженности, нехватки пропускной способности, перегруженности или помех в беспроводной сети, а также перегруженности сервера мультимедиа. Потеря пакетов обычно приводит к искажению или потере звука.</span><span class="sxs-lookup"><span data-stu-id="607f6-p125">Real-Time Transport Protocol (RTP) packet loss for outbound packets. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="607f6-289"><strong>Процент остановленных кадров</strong></span><span class="sxs-lookup"><span data-stu-id="607f6-289"><strong>Frozen frame %</strong></span></span></p></td>
<td><p><span data-ttu-id="607f6-290">Нет</span><span class="sxs-lookup"><span data-stu-id="607f6-290">No</span></span></p></td>
<td><p><span data-ttu-id="607f6-p126">Процент "остановленных" кадров. При остановке кадров видео не воспроизводится, а звук продолжает воспроизводиться.</span><span class="sxs-lookup"><span data-stu-id="607f6-p126">Percentage of “frozen” frames. In a frozen frame, the video stops advancing while the audio portion of the call continues.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="607f6-293"><strong>Средняя частота кадров исходящего сигнала</strong></span><span class="sxs-lookup"><span data-stu-id="607f6-293"><strong>Outbound avg frame rate</strong></span></span></p></td>
<td><p><span data-ttu-id="607f6-294">Нет</span><span class="sxs-lookup"><span data-stu-id="607f6-294">No</span></span></p></td>
<td><p><span data-ttu-id="607f6-295">Средняя частота кадров исходящей передачи во время вызова.</span><span class="sxs-lookup"><span data-stu-id="607f6-295">Average frame rate for outbound transmissions during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="607f6-296"><strong>Средняя частота входящих кадров (%)</strong></span><span class="sxs-lookup"><span data-stu-id="607f6-296"><strong>Inbound avg frame rate</strong></span></span></p></td>
<td><p><span data-ttu-id="607f6-297">Нет</span><span class="sxs-lookup"><span data-stu-id="607f6-297">No</span></span></p></td>
<td><p><span data-ttu-id="607f6-298">Средняя частота кадров входящей передачи во время вызова.</span><span class="sxs-lookup"><span data-stu-id="607f6-298">Average frame rate for incoming transmissions during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="607f6-299"><strong>Низкая частота входящих кадров (%)</strong></span><span class="sxs-lookup"><span data-stu-id="607f6-299"><strong>Inbound low frame rate %</strong></span></span></p></td>
<td><p><span data-ttu-id="607f6-300">Нет</span><span class="sxs-lookup"><span data-stu-id="607f6-300">No</span></span></p></td>
<td><p><span data-ttu-id="607f6-301">Процент звонков с низкой скоростью входящего видеопотока.</span><span class="sxs-lookup"><span data-stu-id="607f6-301">Percentage of the call where the bit rate for incoming video was low.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="607f6-302"><strong>Работоспособность клиента (%)</strong></span><span class="sxs-lookup"><span data-stu-id="607f6-302"><strong>Client health %</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="607f6-303">Показывает относительную работоспособность клиентского устройства во время вызова.</span><span class="sxs-lookup"><span data-stu-id="607f6-303">Indicates the relative health of the client device during the call.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="media-quality-summary-report-metrics-application-sharing-call-summary"></a><span data-ttu-id="607f6-304">Метрики сводного отчета по качеству мультимедиа: сводка по вызовам с общим доступом к приложениям</span><span class="sxs-lookup"><span data-stu-id="607f6-304">Media Quality Summary Report Metrics: Application Sharing Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="607f6-305">Имя</span><span class="sxs-lookup"><span data-stu-id="607f6-305">Name</span></span></th>
<th><span data-ttu-id="607f6-306">Поддержка сортировки</span><span class="sxs-lookup"><span data-stu-id="607f6-306">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="607f6-307">Описание</span><span class="sxs-lookup"><span data-stu-id="607f6-307">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="607f6-308"><strong>Тип звонка и конечной точки</strong></span><span class="sxs-lookup"><span data-stu-id="607f6-308"><strong>Call type/Endpoint type</strong></span></span></p></td>
<td><p><span data-ttu-id="607f6-309">Нет</span><span class="sxs-lookup"><span data-stu-id="607f6-309">No</span></span></p></td>
<td><p><span data-ttu-id="607f6-p127">При щелчке этого элемента отчет предоставляет подробные сведения о звонках, основанных на этом типе. Типы звонков:</span><span class="sxs-lookup"><span data-stu-id="607f6-p127">When you click this item, the report shows detailed information about calls based on that type. Call types include:</span></span></p>
<ul>
<li><p><span data-ttu-id="607f6-312">Одноранговые звонки по объединенным коммуникациям</span><span class="sxs-lookup"><span data-stu-id="607f6-312">UC Peer-to-Peer Calls</span></span></p></li>
<li><p><span data-ttu-id="607f6-313">Сеансы конференц-связи по объединенным коммуникациям</span><span class="sxs-lookup"><span data-stu-id="607f6-313">UC Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="607f6-314">Сеансы конференц-связи по ТСОП</span><span class="sxs-lookup"><span data-stu-id="607f6-314">PSTN Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="607f6-315">Звонки по ТСОП: обходной канал передачи медиаданных</span><span class="sxs-lookup"><span data-stu-id="607f6-315">PSTN Calls: Media Bypass</span></span></p></li>
<li><p><span data-ttu-id="607f6-316">Звонки по ТСОП (без обхода): ветвь объединенных коммуникаций</span><span class="sxs-lookup"><span data-stu-id="607f6-316">PSTN Calls (Non-Bypass): UC Leg</span></span></p></li>
<li><p><span data-ttu-id="607f6-317">Звонки по ТСОП (без обхода): ветвь шлюза</span><span class="sxs-lookup"><span data-stu-id="607f6-317">PSTN Calls (Non-Bypass): Gateway Leg</span></span></p></li>
<li><p><span data-ttu-id="607f6-318">Другие типы звонков</span><span class="sxs-lookup"><span data-stu-id="607f6-318">Other Call Types</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="607f6-319"><strong>Громкость вызова</strong></span><span class="sxs-lookup"><span data-stu-id="607f6-319"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="607f6-320">Нет</span><span class="sxs-lookup"><span data-stu-id="607f6-320">No</span></span></p></td>
<td><p><span data-ttu-id="607f6-321">Общее количество звонков на тип звонка.</span><span class="sxs-lookup"><span data-stu-id="607f6-321">Total number of calls per call type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="607f6-322"><strong>Процент звонков низкого качества</strong></span><span class="sxs-lookup"><span data-stu-id="607f6-322"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="607f6-323">Нет</span><span class="sxs-lookup"><span data-stu-id="607f6-323">No</span></span></p></td>
<td><p><span data-ttu-id="607f6-p128">Общее количество звонков, классифицированных как звонки низкого качества. Звонок низкого качества – это любой звонок, хотя бы одна метрика которого превышает допустимое значение (например, звонок с чрезмерным дрожанием).</span><span class="sxs-lookup"><span data-stu-id="607f6-p128">Total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="607f6-326"><strong>Объем звонков (звонок по беспроводной сети)</strong></span><span class="sxs-lookup"><span data-stu-id="607f6-326"><strong>Call volume (wireless call)</strong></span></span></p></td>
<td><p><span data-ttu-id="607f6-327">Нет</span><span class="sxs-lookup"><span data-stu-id="607f6-327">No</span></span></p></td>
<td><p><span data-ttu-id="607f6-328">Общее количество звонков, при которых используется беспроводное подключение.</span><span class="sxs-lookup"><span data-stu-id="607f6-328">Total number of calls that used a wireless connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="607f6-329"><strong>Объем звонков (звонок по сети VPN)</strong></span><span class="sxs-lookup"><span data-stu-id="607f6-329"><strong>Call volume (VPN call)</strong></span></span></p></td>
<td><p><span data-ttu-id="607f6-330">Нет</span><span class="sxs-lookup"><span data-stu-id="607f6-330">No</span></span></p></td>
<td><p><span data-ttu-id="607f6-331">Общее количество звонков, при которых используется подключение по сети VPN.</span><span class="sxs-lookup"><span data-stu-id="607f6-331">Total number of calls that used a VPN connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="607f6-332"><strong>Объем звонков (внешний звонок)</strong></span><span class="sxs-lookup"><span data-stu-id="607f6-332"><strong>Call volume (external call)</strong></span></span></p></td>
<td><p><span data-ttu-id="607f6-333">Нет</span><span class="sxs-lookup"><span data-stu-id="607f6-333">No</span></span></p></td>
<td><p><span data-ttu-id="607f6-334">Количество звонков, при которых используется внешнее подключение (то есть подключение за пределами внутренней сети).</span><span class="sxs-lookup"><span data-stu-id="607f6-334">Number of calls that used an external connection (that is, a connection outside the internal network).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="607f6-335"><strong>Дрожание (мс)</strong></span><span class="sxs-lookup"><span data-stu-id="607f6-335"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="607f6-336">Нет</span><span class="sxs-lookup"><span data-stu-id="607f6-336">No</span></span></p></td>
<td><p><span data-ttu-id="607f6-337">Среднее значение колебаний, зарегистрированных между прибытиями пакетов RTP.</span><span class="sxs-lookup"><span data-stu-id="607f6-337">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="607f6-338">(Колебание — это мера &quot;шакинесс&quot; звонка). Обычно значения с высокой степенью колебаний заключаются в результате перегруженности или перегруженного сервера мультимедиа, что приводит к искажению или потере звука.</span><span class="sxs-lookup"><span data-stu-id="607f6-338">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="607f6-339"><strong>Средняя относительная задержка в одну сторону</strong></span><span class="sxs-lookup"><span data-stu-id="607f6-339"><strong>Avg. relative one way</strong></span></span></p></td>
<td><p><span data-ttu-id="607f6-340">Нет</span><span class="sxs-lookup"><span data-stu-id="607f6-340">No</span></span></p></td>
<td><p><span data-ttu-id="607f6-p130">Средняя относительная задержка в одну сторону между двумя конечными точками медиаданных. Это мера односкачковой задержки.</span><span class="sxs-lookup"><span data-stu-id="607f6-p130">Average relative one-way delay between two media endpoints. This is a single-hop latency measure.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="607f6-343"><strong>Средняя задержка обработки элемента RDP</strong></span><span class="sxs-lookup"><span data-stu-id="607f6-343"><strong>Avg. RDP tile processing latency</strong></span></span></p></td>
<td><p><span data-ttu-id="607f6-344">Нет</span><span class="sxs-lookup"><span data-stu-id="607f6-344">No</span></span></p></td>
<td><p><span data-ttu-id="607f6-p131">Среднее значение задержки обработки элементов RDP на сервере конференц-связи общего доступа к приложениям во время сеанса просмотра. Высокое среднее значение отражает более длительную задержку при просмотре и включает задержку сети. На перегруженном сервере конференц-связи могут происходить в среднем более длительные задержки.</span><span class="sxs-lookup"><span data-stu-id="607f6-p131">The average RDP tile processing latency in the AS Conferencing Server over the duration of the viewing session. A high average reflects a longer delay in the viewing experience, and includes network latency. An overloaded conferencing server may experience higher average delays.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="607f6-348"><strong>Процент испорченных элементов</strong></span><span class="sxs-lookup"><span data-stu-id="607f6-348"><strong>Total spoiled tile %</strong></span></span></p></td>
<td><p><span data-ttu-id="607f6-349">Нет</span><span class="sxs-lookup"><span data-stu-id="607f6-349">No</span></span></p></td>
<td><p><span data-ttu-id="607f6-350">Итоговый процент испорченных элементов RDP.</span><span class="sxs-lookup"><span data-stu-id="607f6-350">Total percentage of spoiled RDP tiles.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

