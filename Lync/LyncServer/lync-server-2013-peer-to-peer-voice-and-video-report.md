---
title: 'Lync Server 2013: отчет об одноранговой голосовой связи и видеосвязи'
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
ms.openlocfilehash: dc5d3905df971cf5ce09bfb026acc4838974ff18
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536806"
---
# <a name="peer-to-peer-voice-and-video-report-in-lync-server-2013"></a><span data-ttu-id="747fe-102">Отчет по одноранговой голосовой связи и видеосвязи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="747fe-102">Peer-to-Peer Voice and Video Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="747fe-103">_**Последнее изменение темы:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="747fe-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="747fe-p101">Отчет об одноранговой голосовой связи и видеосвязи дает подробное представление о распределении голосовых звонках и видеозвонках за указанный период (например, число звонков в час или в день). Кроме того, этот отчет позволяет просматривать все выполненные голосовые звонки и видеозвонки или только те из них, которые были успешными или завершились со сбоем. Сведения о звонках в отчете упорядочены по следующим группам:</span><span class="sxs-lookup"><span data-stu-id="747fe-p101">The Peer-to-Peer Voice and Video Report provides a detailed look at the distribution of voice and video calls over a specified period of time (for example, calls per hour or calls per day). The report also gives you the option of viewing all the voice and video calls that were made, or of viewing only the successful or failed calls. The reports shows call information broken down into the following groupings:</span></span>

  - <span data-ttu-id="747fe-107">Число звонков на пул</span><span class="sxs-lookup"><span data-stu-id="747fe-107">Calls per pool</span></span>

  - <span data-ttu-id="747fe-108">Вызовы по типу вызова (например, Lync to Lync Call vs. позвонить пользователю в сети PSTN)</span><span class="sxs-lookup"><span data-stu-id="747fe-108">Calls per call type (for example, a Lync to Lync call vs. a Lync call to a person on the PSTN network)</span></span>

  - <span data-ttu-id="747fe-109">Звонки по типу доступа (пользователи, выполнившие вход во внутреннюю сеть, либо пользователи, выполнившие вход во внешнюю сеть)</span><span class="sxs-lookup"><span data-stu-id="747fe-109">Calls per access type (users logged on to the internal network vs. users logged on to the external network)</span></span>

  - <span data-ttu-id="747fe-110">Число вызовов на сервер-посредник</span><span class="sxs-lookup"><span data-stu-id="747fe-110">Calls per Mediation Server</span></span>

<div>

## <a name="to-access-the-peer-to-peer-voice-and-video-report"></a><span data-ttu-id="747fe-111">Доступ к отчету об одноранговой голосовой связи и видеосвязи</span><span class="sxs-lookup"><span data-stu-id="747fe-111">To access the peer-to-peer voice and video report</span></span>

<span data-ttu-id="747fe-112">Отчет об одноранговой голосовой связи и видеосвязи можно просмотреть, открыв сводный отчет об одноранговых операциях и щелкнув одну из следующих метрик:</span><span class="sxs-lookup"><span data-stu-id="747fe-112">You can access the Peer-to-Peer Voice and Video Report only by opening the Peer-to-Peer Activity Summary Report and then clicking any of the following metrics:</span></span>

  - <span data-ttu-id="747fe-113">Total peer-to-peer audio sessions (Общее число одноранговых аудиосеансов)</span><span class="sxs-lookup"><span data-stu-id="747fe-113">Total peer-to-peer audio sessions</span></span>

  - <span data-ttu-id="747fe-114">Total peer-to-peer audio minutes (Общее число минут одноранговой аудиосвязи)</span><span class="sxs-lookup"><span data-stu-id="747fe-114">Total peer-to-peer audio minutes</span></span>

  - <span data-ttu-id="747fe-115">Total peer-to-peer video sessions (Общее число одноранговых видеоосеансов)</span><span class="sxs-lookup"><span data-stu-id="747fe-115">Total peer-to-peer video sessions</span></span>

  - <span data-ttu-id="747fe-116">Total peer-to-peer video minutes (Общее число минут одноранговой видеосвязи)</span><span class="sxs-lookup"><span data-stu-id="747fe-116">Total peer-to-peer video minutes</span></span>

</div>

<div>

## <a name="to-make-the-best-use-of-the-peer-to-peer-voice-and-video-report"></a><span data-ttu-id="747fe-117">Доступ к отчету об одноранговой голосовой связи и видеосвязи</span><span class="sxs-lookup"><span data-stu-id="747fe-117">To make the best use of the peer-to-peer voice and video report</span></span>

<span data-ttu-id="747fe-p102">Существует несколько способ фильтрации отчета об одноранговой голосовой связи и видеосвязи. Однако по умолчанию эти параметры фильтрации скрыты. Чтобы просмотреть их, нажмите кнопку **Показать/скрыть параметры** в верхнем правом углу окна отчета.</span><span class="sxs-lookup"><span data-stu-id="747fe-p102">There are a number of ways you can filter the Peer-to-Peer Voice and Video Report. However, those filtering options are hidden from view by default. To view the filtering options available to you, click **Show/Hide Parameters** button in the upper-right corner of the Report window.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="747fe-121">Фильтры</span><span class="sxs-lookup"><span data-stu-id="747fe-121">Filters</span></span>

<span data-ttu-id="747fe-p103">Фильтры позволяют вам возвратить уточненный набор данных или просматривать возвращенные данные различными способами. В следующей таблице перечислены фильтры, которые вы можете использовать в отчете об одноранговой голосовой связи и видеосвязи.</span><span class="sxs-lookup"><span data-stu-id="747fe-p103">Filters provide a way for you to return a more finely targeted set of data or to view the data in different ways. The following table lists the filters that you can use with the Peer-to-Peer Voice and Video Report.</span></span>

### <a name="peer-to-peer-voice-and-video-report-filters"></a><span data-ttu-id="747fe-124">Фильтры отчета об одноранговой голосовой связи и видеосвязи</span><span class="sxs-lookup"><span data-stu-id="747fe-124">Peer-to-peer voice and video report filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="747fe-125">Имя</span><span class="sxs-lookup"><span data-stu-id="747fe-125">Name</span></span></th>
<th><span data-ttu-id="747fe-126">Описание</span><span class="sxs-lookup"><span data-stu-id="747fe-126">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="747fe-127"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="747fe-127"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="747fe-p104">Начальные дата и время временного диапазона. Чтобы просмотреть данные по часам, введите начальные дату и время следующим образом:</span><span class="sxs-lookup"><span data-stu-id="747fe-p104">Start date and time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="747fe-130">7/7/2012 13:00.</span><span class="sxs-lookup"><span data-stu-id="747fe-130">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="747fe-p105">Если не указать время начала, автоматически будет выбрано время 00:00 указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</span><span class="sxs-lookup"><span data-stu-id="747fe-p105">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="747fe-133">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="747fe-133">7/7/2012</span></span></p>
<p><span data-ttu-id="747fe-134">Для просмотра по неделям или по месяцам введите дату, выпадающую на любой день недели или месяца, который вы хотите просмотреть (это необязательно должен быть первый день недели или месяца):</span><span class="sxs-lookup"><span data-stu-id="747fe-134">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="747fe-135">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="747fe-135">7/3/2012</span></span></p>
<p><span data-ttu-id="747fe-136">Неделя всегда начинается с воскресения и заканчивается субботой.</span><span class="sxs-lookup"><span data-stu-id="747fe-136">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="747fe-137"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="747fe-137"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="747fe-p106">Дата и время окончания диапазона. Чтобы просмотреть данные по часам, введите дату и время окончания в следующем формате:</span><span class="sxs-lookup"><span data-stu-id="747fe-p106">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="747fe-140">7/7/2012 13:00.</span><span class="sxs-lookup"><span data-stu-id="747fe-140">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="747fe-p107">Если не указать время окончания, автоматически будет выбрано время 00:00 указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</span><span class="sxs-lookup"><span data-stu-id="747fe-p107">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="747fe-143">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="747fe-143">7/7/2012</span></span></p>
<p><span data-ttu-id="747fe-144">Для просмотра по неделям или по месяцам введите дату, выпадающую на любой день недели или месяца, который вы хотите просмотреть (это необязательно должен быть первый день недели или месяца):</span><span class="sxs-lookup"><span data-stu-id="747fe-144">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="747fe-145">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="747fe-145">7/3/2012</span></span></p>
<p><span data-ttu-id="747fe-146">Неделя всегда начинается с воскресения и заканчивается субботой.</span><span class="sxs-lookup"><span data-stu-id="747fe-146">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="747fe-147"><strong>Interval</strong></span><span class="sxs-lookup"><span data-stu-id="747fe-147"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="747fe-p108">Временной интервал. Выберите один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="747fe-p108">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="747fe-150">Ежечасно (может отображаться до 25 часов)</span><span class="sxs-lookup"><span data-stu-id="747fe-150">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="747fe-151">Ежедневно (может отображаться до 31 дня)</span><span class="sxs-lookup"><span data-stu-id="747fe-151">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="747fe-152">Еженедельно (может отображаться до 12 недель)</span><span class="sxs-lookup"><span data-stu-id="747fe-152">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="747fe-153">Ежемесячно (может отображаться до 12 месяцев)</span><span class="sxs-lookup"><span data-stu-id="747fe-153">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="747fe-p109">Если начальная и конечная даты превышают максимально допустимое количество значений для выбранного интервала, отображается только максимальное число значений (с отсчетом от начальной даты). Например, если вы выбрали интервал «Daily» с начальной датой 7/7/2012 и конечной датой 2/28/2012, отображаются данные по дням с 00:00 часов 8/7/2012  по 00:00 часов 9/7/2012 (то есть всего за 31 день).</span><span class="sxs-lookup"><span data-stu-id="747fe-p109">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="747fe-156"><strong>Media type</strong> (Тип мультимедиа)</span><span class="sxs-lookup"><span data-stu-id="747fe-156"><strong>Media type</strong></span></span></p></td>
<td><p><span data-ttu-id="747fe-p110">Указывает используемый в сеансе тип мультимедиа. Выберите одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="747fe-p110">Indicates the type of media used in the session. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="747fe-159">Двух</span><span class="sxs-lookup"><span data-stu-id="747fe-159">Both</span></span></p></li>
<li><p><span data-ttu-id="747fe-160">"Audio" (Аудио);</span><span class="sxs-lookup"><span data-stu-id="747fe-160">Audio</span></span></p></li>
<li><p><span data-ttu-id="747fe-161">"Video" (Видео);</span><span class="sxs-lookup"><span data-stu-id="747fe-161">Video</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="747fe-162"><strong>Call disposition</strong> (Характер звонка)</span><span class="sxs-lookup"><span data-stu-id="747fe-162"><strong>Call disposition</strong></span></span></p></td>
<td><p><span data-ttu-id="747fe-p111">Указывает, был ли сеанс успешным. Выберите одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="747fe-p111">Indicates the success or failure of the session. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="747fe-165">Ко</span><span class="sxs-lookup"><span data-stu-id="747fe-165">[All]</span></span></p></li>
<li><p><span data-ttu-id="747fe-166">Success Calls (Успешные звонки)</span><span class="sxs-lookup"><span data-stu-id="747fe-166">Success Calls</span></span></p></li>
<li><p><span data-ttu-id="747fe-167">Failed Calls (Звонки со сбоем)</span><span class="sxs-lookup"><span data-stu-id="747fe-167">Failed Calls</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="747fe-168"><strong>Report by</strong> (Отчетность)</span><span class="sxs-lookup"><span data-stu-id="747fe-168"><strong>Report by</strong></span></span></p></td>
<td><p><span data-ttu-id="747fe-p112">Указывает значения, которые должны использоваться в отчете. Выберите один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="747fe-p112">Indicates the values to be used in the report. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="747fe-171">Session count (Число сеансов)</span><span class="sxs-lookup"><span data-stu-id="747fe-171">Session count</span></span></p></li>
<li><p><span data-ttu-id="747fe-172">Call minutes (Число минут звонков)</span><span class="sxs-lookup"><span data-stu-id="747fe-172">Call minutes</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-pool"></a><span data-ttu-id="747fe-173">Метрики для операций одноранговой голосовой связи и видеосвязи по пулам</span><span class="sxs-lookup"><span data-stu-id="747fe-173">Metrics for peer-to-peer voice and video activity by Pool</span></span>

<span data-ttu-id="747fe-174">В следующей таблице перечислены сведения, представленные в отчете об одноранговой голосовой связи и видеосвязи для каждого пула.</span><span class="sxs-lookup"><span data-stu-id="747fe-174">The following table lists the information provided in the Peer-to-Peer Voice and Video Report for each pool.</span></span>

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-pool"></a><span data-ttu-id="747fe-175">Метрики для операций одноранговой голосовой связи и видеосвязи по пулам</span><span class="sxs-lookup"><span data-stu-id="747fe-175">Metrics for peer-to-peer voice and video activity by pool</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="747fe-176">Имя</span><span class="sxs-lookup"><span data-stu-id="747fe-176">Name</span></span></th>
<th><span data-ttu-id="747fe-177">Возможность сортировки по этому показателю</span><span class="sxs-lookup"><span data-stu-id="747fe-177">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="747fe-178">Описание</span><span class="sxs-lookup"><span data-stu-id="747fe-178">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="747fe-179"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="747fe-179"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="747fe-180">Нет</span><span class="sxs-lookup"><span data-stu-id="747fe-180">No</span></span></p></td>
<td><p><span data-ttu-id="747fe-181">Имя пула регистратора или пограничного сервера, используемого для вызова.</span><span class="sxs-lookup"><span data-stu-id="747fe-181">Name of the Registrar pool or Edge Server used for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="747fe-182"><strong>Дата/время</strong></span><span class="sxs-lookup"><span data-stu-id="747fe-182"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="747fe-183">Нет</span><span class="sxs-lookup"><span data-stu-id="747fe-183">No</span></span></p></td>
<td><p><span data-ttu-id="747fe-184">Дата и период времени, когда был выполнен звонок.</span><span class="sxs-lookup"><span data-stu-id="747fe-184">Date and time period in which the call took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="747fe-185"><strong>Total</strong></span><span class="sxs-lookup"><span data-stu-id="747fe-185"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="747fe-186">Нет</span><span class="sxs-lookup"><span data-stu-id="747fe-186">No</span></span></p></td>
<td><p><span data-ttu-id="747fe-187">Общее число сеансов или сообщений.</span><span class="sxs-lookup"><span data-stu-id="747fe-187">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-call-type"></a><span data-ttu-id="747fe-188">Метрики для операций одноранговой голосовой связи и видеосвязи по типу вызова</span><span class="sxs-lookup"><span data-stu-id="747fe-188">Metrics for peer-to-peer voice and video activity by call type</span></span>

<span data-ttu-id="747fe-189">В следующей таблице перечислены сведения, представленные в отчете об одноранговой голосовой связи и видеосвязи для каждого типа выполненных звонков.</span><span class="sxs-lookup"><span data-stu-id="747fe-189">The following table lists the information provided in the Peer-to-Peer Voice and Video Report for each type of call that was made.</span></span>

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-call-type"></a><span data-ttu-id="747fe-190">Метрики для операций одноранговой голосовой связи и видеосвязи по типу вызова</span><span class="sxs-lookup"><span data-stu-id="747fe-190">Metrics for peer-to-peer voice and video activity by call type</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="747fe-191">Имя</span><span class="sxs-lookup"><span data-stu-id="747fe-191">Name</span></span></th>
<th><span data-ttu-id="747fe-192">Возможность сортировки по этому показателю</span><span class="sxs-lookup"><span data-stu-id="747fe-192">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="747fe-193">Описание</span><span class="sxs-lookup"><span data-stu-id="747fe-193">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="747fe-194"><strong>Call type</strong> (Тип звонка)</span><span class="sxs-lookup"><span data-stu-id="747fe-194"><strong>Call type</strong></span></span></p></td>
<td><p><span data-ttu-id="747fe-195">Нет</span><span class="sxs-lookup"><span data-stu-id="747fe-195">No</span></span></p></td>
<td><p><span data-ttu-id="747fe-p113">Указывает тип выполненного звонка. Доступны следующие значения:</span><span class="sxs-lookup"><span data-stu-id="747fe-p113">Indicates the type of call that was made. Values are one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="747fe-198">UC для UC</span><span class="sxs-lookup"><span data-stu-id="747fe-198">UC-to-UC</span></span></p></li>
<li><p><span data-ttu-id="747fe-199">UC для PSTN</span><span class="sxs-lookup"><span data-stu-id="747fe-199">UC-to-PSTN</span></span></p></li>
<li><p><span data-ttu-id="747fe-200">PSTN – UC</span><span class="sxs-lookup"><span data-stu-id="747fe-200">PSTN-to-UC</span></span></p></li>
<li><p><span data-ttu-id="747fe-201">PSTN – PSTN</span><span class="sxs-lookup"><span data-stu-id="747fe-201">PSTN-to-PSTN</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="747fe-202"><strong>Дата/время</strong></span><span class="sxs-lookup"><span data-stu-id="747fe-202"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="747fe-203">Нет</span><span class="sxs-lookup"><span data-stu-id="747fe-203">No</span></span></p></td>
<td><p><span data-ttu-id="747fe-204">Дата и период времени, когда был выполнен звонок.</span><span class="sxs-lookup"><span data-stu-id="747fe-204">Date and time period in which the call took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="747fe-205"><strong>Total</strong></span><span class="sxs-lookup"><span data-stu-id="747fe-205"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="747fe-206">Нет</span><span class="sxs-lookup"><span data-stu-id="747fe-206">No</span></span></p></td>
<td><p><span data-ttu-id="747fe-207">Общее число сеансов или сообщений.</span><span class="sxs-lookup"><span data-stu-id="747fe-207">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-access-type"></a><span data-ttu-id="747fe-208">Метрики для операций одноранговой голосовой связи и видеосвязи по типу доступа</span><span class="sxs-lookup"><span data-stu-id="747fe-208">Metrics for peer-to-peer voice and video activity by access type</span></span>

<span data-ttu-id="747fe-209">В следующей таблице перечислены сведения, представленные в отчете об одноранговой голосовой связи и видеосвязи для каждого типа сетевого доступа.</span><span class="sxs-lookup"><span data-stu-id="747fe-209">The following table lists the information provided in the Peer-to-Peer Voice and Video Report for each network access type.</span></span>

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-access-type"></a><span data-ttu-id="747fe-210">Метрики для операций одноранговой голосовой связи и видеосвязи по типу доступа</span><span class="sxs-lookup"><span data-stu-id="747fe-210">Metrics for peer-to-peer voice and video activity by access type</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="747fe-211">Имя</span><span class="sxs-lookup"><span data-stu-id="747fe-211">Name</span></span></th>
<th><span data-ttu-id="747fe-212">Возможность сортировки по этому показателю</span><span class="sxs-lookup"><span data-stu-id="747fe-212">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="747fe-213">Описание</span><span class="sxs-lookup"><span data-stu-id="747fe-213">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="747fe-214"><strong>Activity type</strong> (Тип активности)</span><span class="sxs-lookup"><span data-stu-id="747fe-214"><strong>Activity type</strong></span></span></p></td>
<td><p><span data-ttu-id="747fe-215">Нет</span><span class="sxs-lookup"><span data-stu-id="747fe-215">No</span></span></p></td>
<td><p><span data-ttu-id="747fe-p114">Указывает, выполняли ли клиенты вход во внутреннюю или во внешнюю сеть при совершении звонка. Обычно доступны следующие значения:</span><span class="sxs-lookup"><span data-stu-id="747fe-p114">Indicates whether the clients were logged on to the internal network or the external network when the call was placed. Values are typically one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="747fe-218">Внутренний</span><span class="sxs-lookup"><span data-stu-id="747fe-218">Internal</span></span></p></li>
<li><p><span data-ttu-id="747fe-219">Внешний</span><span class="sxs-lookup"><span data-stu-id="747fe-219">External</span></span></p></li>
<li><p><span data-ttu-id="747fe-220">Mixed</span><span class="sxs-lookup"><span data-stu-id="747fe-220">Mixed</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="747fe-221"><strong>Дата/время</strong></span><span class="sxs-lookup"><span data-stu-id="747fe-221"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="747fe-222">Нет</span><span class="sxs-lookup"><span data-stu-id="747fe-222">No</span></span></p></td>
<td><p><span data-ttu-id="747fe-223">Дата и период времени, когда был выполнен звонок.</span><span class="sxs-lookup"><span data-stu-id="747fe-223">Date and time period in which the call took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="747fe-224"><strong>Total</strong></span><span class="sxs-lookup"><span data-stu-id="747fe-224"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="747fe-225">Нет</span><span class="sxs-lookup"><span data-stu-id="747fe-225">No</span></span></p></td>
<td><p><span data-ttu-id="747fe-226">Общее число сеансов или сообщений.</span><span class="sxs-lookup"><span data-stu-id="747fe-226">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-mediation-server"></a><span data-ttu-id="747fe-227">Метрики для операций одноранговой голосовой связи и видеосвязи по серверу-посреднику</span><span class="sxs-lookup"><span data-stu-id="747fe-227">Metrics for peer-to-peer voice and video activity by mediation server</span></span>

<span data-ttu-id="747fe-228">В следующей таблице перечислены сведения, представленные в отчете об одноранговой голосовой связи и видеосвязи для каждого сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="747fe-228">The following table lists the information provided in the Peer-to-Peer Voice and Video Report for each Mediation Server.</span></span>

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-mediation-server"></a><span data-ttu-id="747fe-229">Метрики для операций одноранговой голосовой связи и видеосвязи по серверу-посреднику</span><span class="sxs-lookup"><span data-stu-id="747fe-229">Metrics for peer-to-peer voice and video activity by mediation server</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="747fe-230">Имя</span><span class="sxs-lookup"><span data-stu-id="747fe-230">Name</span></span></th>
<th><span data-ttu-id="747fe-231">Возможность сортировки по этому показателю</span><span class="sxs-lookup"><span data-stu-id="747fe-231">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="747fe-232">Описание</span><span class="sxs-lookup"><span data-stu-id="747fe-232">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="747fe-233"><strong>Mediation Server</strong> (Сервер-посредник)</span><span class="sxs-lookup"><span data-stu-id="747fe-233"><strong>Mediation Server</strong></span></span></p></td>
<td><p><span data-ttu-id="747fe-234">Нет</span><span class="sxs-lookup"><span data-stu-id="747fe-234">No</span></span></p></td>
<td><p><span data-ttu-id="747fe-235">Имя сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="747fe-235">Name of the Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="747fe-236"><strong>Дата/время</strong></span><span class="sxs-lookup"><span data-stu-id="747fe-236"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="747fe-237">Нет</span><span class="sxs-lookup"><span data-stu-id="747fe-237">No</span></span></p></td>
<td><p><span data-ttu-id="747fe-238">Дата и период времени, когда был выполнен звонок.</span><span class="sxs-lookup"><span data-stu-id="747fe-238">Date and time period in which the call took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="747fe-239"><strong>Total</strong></span><span class="sxs-lookup"><span data-stu-id="747fe-239"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="747fe-240">Нет</span><span class="sxs-lookup"><span data-stu-id="747fe-240">No</span></span></p></td>
<td><p><span data-ttu-id="747fe-241">Общее число сеансов или сообщений.</span><span class="sxs-lookup"><span data-stu-id="747fe-241">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

