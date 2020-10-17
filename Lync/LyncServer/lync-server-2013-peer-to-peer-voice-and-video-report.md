---
title: 'Lync Server 2013: отчет об одноранговой голосовой связи и видеосвязи'
description: 'Lync Server 2013: отчет об одноранговой голосовой связи и видеосвязи.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Peer-to-Peer Voice and Video Report
ms:assetid: e17c36b5-5a2f-4673-9696-3b2d31c2bb2f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615040(v=OCS.15)
ms:contentKeyID: 48185535
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 43041926b3d6b57508b6ee4c53ca9cb055bcb348
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557275"
---
# <a name="peer-to-peer-voice-and-video-report-in-lync-server-2013"></a><span data-ttu-id="12002-103">Отчет по одноранговой голосовой связи и видеосвязи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12002-103">Peer-to-Peer Voice and Video Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="12002-104">_**Последнее изменение темы:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="12002-104">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="12002-p101">Отчет об одноранговой голосовой связи и видеосвязи дает подробное представление о распределении голосовых звонках и видеозвонках за указанный период (например, число звонков в час или в день). Кроме того, этот отчет позволяет просматривать все выполненные голосовые звонки и видеозвонки или только те из них, которые были успешными или завершились со сбоем. Сведения о звонках в отчете упорядочены по следующим группам:</span><span class="sxs-lookup"><span data-stu-id="12002-p101">The Peer-to-Peer Voice and Video Report provides a detailed look at the distribution of voice and video calls over a specified period of time (for example, calls per hour or calls per day). The report also gives you the option of viewing all the voice and video calls that were made, or of viewing only the successful or failed calls. The reports shows call information broken down into the following groupings:</span></span>

  - <span data-ttu-id="12002-108">Число звонков на пул</span><span class="sxs-lookup"><span data-stu-id="12002-108">Calls per pool</span></span>

  - <span data-ttu-id="12002-109">Вызовы по типу вызова (например, Lync to Lync Call vs. позвонить пользователю в сети PSTN)</span><span class="sxs-lookup"><span data-stu-id="12002-109">Calls per call type (for example, a Lync to Lync call vs. a Lync call to a person on the PSTN network)</span></span>

  - <span data-ttu-id="12002-110">Звонки по типу доступа (пользователи, выполнившие вход во внутреннюю сеть, либо пользователи, выполнившие вход во внешнюю сеть)</span><span class="sxs-lookup"><span data-stu-id="12002-110">Calls per access type (users logged on to the internal network vs. users logged on to the external network)</span></span>

  - <span data-ttu-id="12002-111">Число вызовов на сервер-посредник</span><span class="sxs-lookup"><span data-stu-id="12002-111">Calls per Mediation Server</span></span>

<div>

## <a name="to-access-the-peer-to-peer-voice-and-video-report"></a><span data-ttu-id="12002-112">Доступ к отчету об одноранговой голосовой связи и видеосвязи</span><span class="sxs-lookup"><span data-stu-id="12002-112">To access the peer-to-peer voice and video report</span></span>

<span data-ttu-id="12002-113">Отчет об одноранговой голосовой связи и видеосвязи можно просмотреть, открыв сводный отчет об одноранговых операциях и щелкнув одну из следующих метрик:</span><span class="sxs-lookup"><span data-stu-id="12002-113">You can access the Peer-to-Peer Voice and Video Report only by opening the Peer-to-Peer Activity Summary Report and then clicking any of the following metrics:</span></span>

  - <span data-ttu-id="12002-114">Total peer-to-peer audio sessions (Общее число одноранговых аудиосеансов)</span><span class="sxs-lookup"><span data-stu-id="12002-114">Total peer-to-peer audio sessions</span></span>

  - <span data-ttu-id="12002-115">Total peer-to-peer audio minutes (Общее число минут одноранговой аудиосвязи)</span><span class="sxs-lookup"><span data-stu-id="12002-115">Total peer-to-peer audio minutes</span></span>

  - <span data-ttu-id="12002-116">Total peer-to-peer video sessions (Общее число одноранговых видеоосеансов)</span><span class="sxs-lookup"><span data-stu-id="12002-116">Total peer-to-peer video sessions</span></span>

  - <span data-ttu-id="12002-117">Total peer-to-peer video minutes (Общее число минут одноранговой видеосвязи)</span><span class="sxs-lookup"><span data-stu-id="12002-117">Total peer-to-peer video minutes</span></span>

</div>

<div>

## <a name="to-make-the-best-use-of-the-peer-to-peer-voice-and-video-report"></a><span data-ttu-id="12002-118">Доступ к отчету об одноранговой голосовой связи и видеосвязи</span><span class="sxs-lookup"><span data-stu-id="12002-118">To make the best use of the peer-to-peer voice and video report</span></span>

<span data-ttu-id="12002-p102">Существует несколько способ фильтрации отчета об одноранговой голосовой связи и видеосвязи. Однако по умолчанию эти параметры фильтрации скрыты. Чтобы просмотреть их, нажмите кнопку **Показать/скрыть параметры** в верхнем правом углу окна отчета.</span><span class="sxs-lookup"><span data-stu-id="12002-p102">There are a number of ways you can filter the Peer-to-Peer Voice and Video Report. However, those filtering options are hidden from view by default. To view the filtering options available to you, click **Show/Hide Parameters** button in the upper-right corner of the Report window.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="12002-122">Фильтры</span><span class="sxs-lookup"><span data-stu-id="12002-122">Filters</span></span>

<span data-ttu-id="12002-p103">Фильтры позволяют вам возвратить уточненный набор данных или просматривать возвращенные данные различными способами. В следующей таблице перечислены фильтры, которые вы можете использовать в отчете об одноранговой голосовой связи и видеосвязи.</span><span class="sxs-lookup"><span data-stu-id="12002-p103">Filters provide a way for you to return a more finely targeted set of data or to view the data in different ways. The following table lists the filters that you can use with the Peer-to-Peer Voice and Video Report.</span></span>

### <a name="peer-to-peer-voice-and-video-report-filters"></a><span data-ttu-id="12002-125">Фильтры отчета об одноранговой голосовой связи и видеосвязи</span><span class="sxs-lookup"><span data-stu-id="12002-125">Peer-to-peer voice and video report filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="12002-126">Имя</span><span class="sxs-lookup"><span data-stu-id="12002-126">Name</span></span></th>
<th><span data-ttu-id="12002-127">Описание</span><span class="sxs-lookup"><span data-stu-id="12002-127">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="12002-128"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="12002-128"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="12002-p104">Начальные дата и время временного диапазона. Чтобы просмотреть данные по часам, введите начальные дату и время следующим образом:</span><span class="sxs-lookup"><span data-stu-id="12002-p104">Start date and time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="12002-131">7/7/2012 13:00.</span><span class="sxs-lookup"><span data-stu-id="12002-131">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="12002-p105">Если не указать время начала, автоматически будет выбрано время 00:00 указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</span><span class="sxs-lookup"><span data-stu-id="12002-p105">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="12002-134">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="12002-134">7/7/2012</span></span></p>
<p><span data-ttu-id="12002-135">Для просмотра по неделям или по месяцам введите дату, выпадающую на любой день недели или месяца, который вы хотите просмотреть (это необязательно должен быть первый день недели или месяца):</span><span class="sxs-lookup"><span data-stu-id="12002-135">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="12002-136">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="12002-136">7/3/2012</span></span></p>
<p><span data-ttu-id="12002-137">Неделя всегда начинается с воскресения и заканчивается субботой.</span><span class="sxs-lookup"><span data-stu-id="12002-137">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12002-138"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="12002-138"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="12002-p106">Дата и время окончания диапазона. Чтобы просмотреть данные по часам, введите дату и время окончания в следующем формате:</span><span class="sxs-lookup"><span data-stu-id="12002-p106">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="12002-141">7/7/2012 13:00.</span><span class="sxs-lookup"><span data-stu-id="12002-141">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="12002-p107">Если не указать время окончания, автоматически будет выбрано время 00:00 указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</span><span class="sxs-lookup"><span data-stu-id="12002-p107">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="12002-144">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="12002-144">7/7/2012</span></span></p>
<p><span data-ttu-id="12002-145">Для просмотра по неделям или по месяцам введите дату, выпадающую на любой день недели или месяца, который вы хотите просмотреть (это необязательно должен быть первый день недели или месяца):</span><span class="sxs-lookup"><span data-stu-id="12002-145">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="12002-146">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="12002-146">7/3/2012</span></span></p>
<p><span data-ttu-id="12002-147">Неделя всегда начинается с воскресения и заканчивается субботой.</span><span class="sxs-lookup"><span data-stu-id="12002-147">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12002-148"><strong>Interval</strong></span><span class="sxs-lookup"><span data-stu-id="12002-148"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="12002-p108">Временной интервал. Выберите один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="12002-p108">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="12002-151">Ежечасно (может отображаться до 25 часов)</span><span class="sxs-lookup"><span data-stu-id="12002-151">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="12002-152">Ежедневно (может отображаться до 31 дня)</span><span class="sxs-lookup"><span data-stu-id="12002-152">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="12002-153">Еженедельно (может отображаться до 12 недель)</span><span class="sxs-lookup"><span data-stu-id="12002-153">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="12002-154">Ежемесячно (может отображаться до 12 месяцев)</span><span class="sxs-lookup"><span data-stu-id="12002-154">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="12002-p109">Если начальная и конечная даты превышают максимально допустимое количество значений для выбранного интервала, отображается только максимальное число значений (с отсчетом от начальной даты). Например, если вы выбрали интервал «Daily» с начальной датой 7/7/2012 и конечной датой 2/28/2012, отображаются данные по дням с 00:00 часов 8/7/2012  по 00:00 часов 9/7/2012 (то есть всего за 31 день).</span><span class="sxs-lookup"><span data-stu-id="12002-p109">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12002-157"><strong>Media type</strong> (Тип мультимедиа)</span><span class="sxs-lookup"><span data-stu-id="12002-157"><strong>Media type</strong></span></span></p></td>
<td><p><span data-ttu-id="12002-p110">Указывает используемый в сеансе тип мультимедиа. Выберите одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="12002-p110">Indicates the type of media used in the session. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="12002-160">Двух</span><span class="sxs-lookup"><span data-stu-id="12002-160">Both</span></span></p></li>
<li><p><span data-ttu-id="12002-161">"Audio" (Аудио);</span><span class="sxs-lookup"><span data-stu-id="12002-161">Audio</span></span></p></li>
<li><p><span data-ttu-id="12002-162">"Video" (Видео);</span><span class="sxs-lookup"><span data-stu-id="12002-162">Video</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12002-163"><strong>Call disposition</strong> (Характер звонка)</span><span class="sxs-lookup"><span data-stu-id="12002-163"><strong>Call disposition</strong></span></span></p></td>
<td><p><span data-ttu-id="12002-p111">Указывает, был ли сеанс успешным. Выберите одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="12002-p111">Indicates the success or failure of the session. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="12002-166">Ко</span><span class="sxs-lookup"><span data-stu-id="12002-166">[All]</span></span></p></li>
<li><p><span data-ttu-id="12002-167">Success Calls (Успешные звонки)</span><span class="sxs-lookup"><span data-stu-id="12002-167">Success Calls</span></span></p></li>
<li><p><span data-ttu-id="12002-168">Failed Calls (Звонки со сбоем)</span><span class="sxs-lookup"><span data-stu-id="12002-168">Failed Calls</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12002-169"><strong>Report by</strong> (Отчетность)</span><span class="sxs-lookup"><span data-stu-id="12002-169"><strong>Report by</strong></span></span></p></td>
<td><p><span data-ttu-id="12002-p112">Указывает значения, которые должны использоваться в отчете. Выберите один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="12002-p112">Indicates the values to be used in the report. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="12002-172">Session count (Число сеансов)</span><span class="sxs-lookup"><span data-stu-id="12002-172">Session count</span></span></p></li>
<li><p><span data-ttu-id="12002-173">Call minutes (Число минут звонков)</span><span class="sxs-lookup"><span data-stu-id="12002-173">Call minutes</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-pool"></a><span data-ttu-id="12002-174">Метрики для операций одноранговой голосовой связи и видеосвязи по пулам</span><span class="sxs-lookup"><span data-stu-id="12002-174">Metrics for peer-to-peer voice and video activity by Pool</span></span>

<span data-ttu-id="12002-175">В следующей таблице перечислены сведения, представленные в отчете об одноранговой голосовой связи и видеосвязи для каждого пула.</span><span class="sxs-lookup"><span data-stu-id="12002-175">The following table lists the information provided in the Peer-to-Peer Voice and Video Report for each pool.</span></span>

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-pool"></a><span data-ttu-id="12002-176">Метрики для операций одноранговой голосовой связи и видеосвязи по пулам</span><span class="sxs-lookup"><span data-stu-id="12002-176">Metrics for peer-to-peer voice and video activity by pool</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="12002-177">Имя</span><span class="sxs-lookup"><span data-stu-id="12002-177">Name</span></span></th>
<th><span data-ttu-id="12002-178">Возможность сортировки по этому показателю</span><span class="sxs-lookup"><span data-stu-id="12002-178">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="12002-179">Описание</span><span class="sxs-lookup"><span data-stu-id="12002-179">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="12002-180"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="12002-180"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="12002-181">Нет</span><span class="sxs-lookup"><span data-stu-id="12002-181">No</span></span></p></td>
<td><p><span data-ttu-id="12002-182">Имя пула регистратора или пограничного сервера, используемого для вызова.</span><span class="sxs-lookup"><span data-stu-id="12002-182">Name of the Registrar pool or Edge Server used for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12002-183"><strong>Дата/время</strong></span><span class="sxs-lookup"><span data-stu-id="12002-183"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="12002-184">Нет</span><span class="sxs-lookup"><span data-stu-id="12002-184">No</span></span></p></td>
<td><p><span data-ttu-id="12002-185">Дата и период времени, когда был выполнен звонок.</span><span class="sxs-lookup"><span data-stu-id="12002-185">Date and time period in which the call took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12002-186"><strong>Total</strong></span><span class="sxs-lookup"><span data-stu-id="12002-186"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="12002-187">Нет</span><span class="sxs-lookup"><span data-stu-id="12002-187">No</span></span></p></td>
<td><p><span data-ttu-id="12002-188">Общее число сеансов или сообщений.</span><span class="sxs-lookup"><span data-stu-id="12002-188">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-call-type"></a><span data-ttu-id="12002-189">Метрики для операций одноранговой голосовой связи и видеосвязи по типу вызова</span><span class="sxs-lookup"><span data-stu-id="12002-189">Metrics for peer-to-peer voice and video activity by call type</span></span>

<span data-ttu-id="12002-190">В следующей таблице перечислены сведения, представленные в отчете об одноранговой голосовой связи и видеосвязи для каждого типа выполненных звонков.</span><span class="sxs-lookup"><span data-stu-id="12002-190">The following table lists the information provided in the Peer-to-Peer Voice and Video Report for each type of call that was made.</span></span>

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-call-type"></a><span data-ttu-id="12002-191">Метрики для операций одноранговой голосовой связи и видеосвязи по типу вызова</span><span class="sxs-lookup"><span data-stu-id="12002-191">Metrics for peer-to-peer voice and video activity by call type</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="12002-192">Имя</span><span class="sxs-lookup"><span data-stu-id="12002-192">Name</span></span></th>
<th><span data-ttu-id="12002-193">Возможность сортировки по этому показателю</span><span class="sxs-lookup"><span data-stu-id="12002-193">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="12002-194">Описание</span><span class="sxs-lookup"><span data-stu-id="12002-194">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="12002-195"><strong>Call type</strong> (Тип звонка)</span><span class="sxs-lookup"><span data-stu-id="12002-195"><strong>Call type</strong></span></span></p></td>
<td><p><span data-ttu-id="12002-196">Нет</span><span class="sxs-lookup"><span data-stu-id="12002-196">No</span></span></p></td>
<td><p><span data-ttu-id="12002-p113">Указывает тип выполненного звонка. Доступны следующие значения:</span><span class="sxs-lookup"><span data-stu-id="12002-p113">Indicates the type of call that was made. Values are one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="12002-199">UC для UC</span><span class="sxs-lookup"><span data-stu-id="12002-199">UC-to-UC</span></span></p></li>
<li><p><span data-ttu-id="12002-200">UC для PSTN</span><span class="sxs-lookup"><span data-stu-id="12002-200">UC-to-PSTN</span></span></p></li>
<li><p><span data-ttu-id="12002-201">PSTN – UC</span><span class="sxs-lookup"><span data-stu-id="12002-201">PSTN-to-UC</span></span></p></li>
<li><p><span data-ttu-id="12002-202">PSTN – PSTN</span><span class="sxs-lookup"><span data-stu-id="12002-202">PSTN-to-PSTN</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12002-203"><strong>Дата/время</strong></span><span class="sxs-lookup"><span data-stu-id="12002-203"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="12002-204">Нет</span><span class="sxs-lookup"><span data-stu-id="12002-204">No</span></span></p></td>
<td><p><span data-ttu-id="12002-205">Дата и период времени, когда был выполнен звонок.</span><span class="sxs-lookup"><span data-stu-id="12002-205">Date and time period in which the call took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12002-206"><strong>Total</strong></span><span class="sxs-lookup"><span data-stu-id="12002-206"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="12002-207">Нет</span><span class="sxs-lookup"><span data-stu-id="12002-207">No</span></span></p></td>
<td><p><span data-ttu-id="12002-208">Общее число сеансов или сообщений.</span><span class="sxs-lookup"><span data-stu-id="12002-208">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-access-type"></a><span data-ttu-id="12002-209">Метрики для операций одноранговой голосовой связи и видеосвязи по типу доступа</span><span class="sxs-lookup"><span data-stu-id="12002-209">Metrics for peer-to-peer voice and video activity by access type</span></span>

<span data-ttu-id="12002-210">В следующей таблице перечислены сведения, представленные в отчете об одноранговой голосовой связи и видеосвязи для каждого типа сетевого доступа.</span><span class="sxs-lookup"><span data-stu-id="12002-210">The following table lists the information provided in the Peer-to-Peer Voice and Video Report for each network access type.</span></span>

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-access-type"></a><span data-ttu-id="12002-211">Метрики для операций одноранговой голосовой связи и видеосвязи по типу доступа</span><span class="sxs-lookup"><span data-stu-id="12002-211">Metrics for peer-to-peer voice and video activity by access type</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="12002-212">Имя</span><span class="sxs-lookup"><span data-stu-id="12002-212">Name</span></span></th>
<th><span data-ttu-id="12002-213">Возможность сортировки по этому показателю</span><span class="sxs-lookup"><span data-stu-id="12002-213">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="12002-214">Описание</span><span class="sxs-lookup"><span data-stu-id="12002-214">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="12002-215"><strong>Activity type</strong> (Тип активности)</span><span class="sxs-lookup"><span data-stu-id="12002-215"><strong>Activity type</strong></span></span></p></td>
<td><p><span data-ttu-id="12002-216">Нет</span><span class="sxs-lookup"><span data-stu-id="12002-216">No</span></span></p></td>
<td><p><span data-ttu-id="12002-p114">Указывает, выполняли ли клиенты вход во внутреннюю или во внешнюю сеть при совершении звонка. Обычно доступны следующие значения:</span><span class="sxs-lookup"><span data-stu-id="12002-p114">Indicates whether the clients were logged on to the internal network or the external network when the call was placed. Values are typically one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="12002-219">Внутренний</span><span class="sxs-lookup"><span data-stu-id="12002-219">Internal</span></span></p></li>
<li><p><span data-ttu-id="12002-220">Внешний</span><span class="sxs-lookup"><span data-stu-id="12002-220">External</span></span></p></li>
<li><p><span data-ttu-id="12002-221">Mixed</span><span class="sxs-lookup"><span data-stu-id="12002-221">Mixed</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12002-222"><strong>Дата/время</strong></span><span class="sxs-lookup"><span data-stu-id="12002-222"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="12002-223">Нет</span><span class="sxs-lookup"><span data-stu-id="12002-223">No</span></span></p></td>
<td><p><span data-ttu-id="12002-224">Дата и период времени, когда был выполнен звонок.</span><span class="sxs-lookup"><span data-stu-id="12002-224">Date and time period in which the call took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12002-225"><strong>Total</strong></span><span class="sxs-lookup"><span data-stu-id="12002-225"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="12002-226">Нет</span><span class="sxs-lookup"><span data-stu-id="12002-226">No</span></span></p></td>
<td><p><span data-ttu-id="12002-227">Общее число сеансов или сообщений.</span><span class="sxs-lookup"><span data-stu-id="12002-227">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-mediation-server"></a><span data-ttu-id="12002-228">Метрики для операций одноранговой голосовой связи и видеосвязи по серверу-посреднику</span><span class="sxs-lookup"><span data-stu-id="12002-228">Metrics for peer-to-peer voice and video activity by mediation server</span></span>

<span data-ttu-id="12002-229">В следующей таблице перечислены сведения, представленные в отчете об одноранговой голосовой связи и видеосвязи для каждого сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="12002-229">The following table lists the information provided in the Peer-to-Peer Voice and Video Report for each Mediation Server.</span></span>

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-mediation-server"></a><span data-ttu-id="12002-230">Метрики для операций одноранговой голосовой связи и видеосвязи по серверу-посреднику</span><span class="sxs-lookup"><span data-stu-id="12002-230">Metrics for peer-to-peer voice and video activity by mediation server</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="12002-231">Имя</span><span class="sxs-lookup"><span data-stu-id="12002-231">Name</span></span></th>
<th><span data-ttu-id="12002-232">Возможность сортировки по этому показателю</span><span class="sxs-lookup"><span data-stu-id="12002-232">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="12002-233">Описание</span><span class="sxs-lookup"><span data-stu-id="12002-233">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="12002-234"><strong>Mediation Server</strong> (Сервер-посредник)</span><span class="sxs-lookup"><span data-stu-id="12002-234"><strong>Mediation Server</strong></span></span></p></td>
<td><p><span data-ttu-id="12002-235">Нет</span><span class="sxs-lookup"><span data-stu-id="12002-235">No</span></span></p></td>
<td><p><span data-ttu-id="12002-236">Имя сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="12002-236">Name of the Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12002-237"><strong>Дата/время</strong></span><span class="sxs-lookup"><span data-stu-id="12002-237"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="12002-238">Нет</span><span class="sxs-lookup"><span data-stu-id="12002-238">No</span></span></p></td>
<td><p><span data-ttu-id="12002-239">Дата и период времени, когда был выполнен звонок.</span><span class="sxs-lookup"><span data-stu-id="12002-239">Date and time period in which the call took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12002-240"><strong>Total</strong></span><span class="sxs-lookup"><span data-stu-id="12002-240"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="12002-241">Нет</span><span class="sxs-lookup"><span data-stu-id="12002-241">No</span></span></p></td>
<td><p><span data-ttu-id="12002-242">Общее число сеансов или сообщений.</span><span class="sxs-lookup"><span data-stu-id="12002-242">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

