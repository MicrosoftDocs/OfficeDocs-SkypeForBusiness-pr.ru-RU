---
title: 'Lync Server 2013: одноранговый голосовой и видео отчет'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Peer-to-Peer Voice and Video Report
ms:assetid: e17c36b5-5a2f-4673-9696-3b2d31c2bb2f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615040(v=OCS.15)
ms:contentKeyID: 48185535
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b938a5281717528143cfc077a42f51bd68f69bae
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825396"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="peer-to-peer-voice-and-video-report-in-lync-server-2013"></a><span data-ttu-id="70ce9-102">Одноранговый голосовой и Видеоотчет в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="70ce9-102">Peer-to-Peer Voice and Video Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="70ce9-103">_**Тема последнего изменения:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="70ce9-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="70ce9-p101">Отчет об одноранговой голосовой связи и видеосвязи дает подробное представление о распределении голосовых звонках и видеозвонках за указанный период (например, число звонков в час или в день). Кроме того, этот отчет позволяет просматривать все выполненные голосовые звонки и видеозвонки или только те из них, которые были успешными или завершились со сбоем. Сведения о звонках в отчете упорядочены по следующим группам:</span><span class="sxs-lookup"><span data-stu-id="70ce9-p101">The Peer-to-Peer Voice and Video Report provides a detailed look at the distribution of voice and video calls over a specified period of time (for example, calls per hour or calls per day). The report also gives you the option of viewing all the voice and video calls that were made, or of viewing only the successful or failed calls. The reports shows call information broken down into the following groupings:</span></span>

  - <span data-ttu-id="70ce9-107">Число звонков на пул</span><span class="sxs-lookup"><span data-stu-id="70ce9-107">Calls per pool</span></span>

  - <span data-ttu-id="70ce9-108">Звонки на тип звонка (например, Lync для звонков по Lync и вызов Lync для абонента в сети PSTN).</span><span class="sxs-lookup"><span data-stu-id="70ce9-108">Calls per call type (for example, a Lync to Lync call vs. a Lync call to a person on the PSTN network)</span></span>

  - <span data-ttu-id="70ce9-109">Звонки по типу доступа (пользователи, выполнившие вход во внутреннюю сеть, либо пользователи, выполнившие вход во внешнюю сеть)</span><span class="sxs-lookup"><span data-stu-id="70ce9-109">Calls per access type (users logged on to the internal network vs. users logged on to the external network)</span></span>

  - <span data-ttu-id="70ce9-110">Звонки на сервер по исправлению</span><span class="sxs-lookup"><span data-stu-id="70ce9-110">Calls per Mediation Server</span></span>

<div>

## <a name="to-access-the-peer-to-peer-voice-and-video-report"></a><span data-ttu-id="70ce9-111">Доступ к отчету об одноранговой голосовой связи и видеосвязи</span><span class="sxs-lookup"><span data-stu-id="70ce9-111">To access the peer-to-peer voice and video report</span></span>

<span data-ttu-id="70ce9-112">Отчет об одноранговой голосовой связи и видеосвязи можно просмотреть, открыв сводный отчет об одноранговых операциях и щелкнув одну из следующих метрик:</span><span class="sxs-lookup"><span data-stu-id="70ce9-112">You can access the Peer-to-Peer Voice and Video Report only by opening the Peer-to-Peer Activity Summary Report and then clicking any of the following metrics:</span></span>

  - <span data-ttu-id="70ce9-113">Общее количество одноранговых сеансов аудиосвязи</span><span class="sxs-lookup"><span data-stu-id="70ce9-113">Total peer-to-peer audio sessions</span></span>

  - <span data-ttu-id="70ce9-114">Общее число минут одноранговой аудиосвязи (Общее число минут одноранговой аудиосвязи)</span><span class="sxs-lookup"><span data-stu-id="70ce9-114">Total peer-to-peer audio minutes</span></span>

  - <span data-ttu-id="70ce9-115">Общее количество одноранговых сеансов видеосвязи</span><span class="sxs-lookup"><span data-stu-id="70ce9-115">Total peer-to-peer video sessions</span></span>

  - <span data-ttu-id="70ce9-116">Общее число минут одноранговой видеосвязи (Общее число минут одноранговой видеосвязи)</span><span class="sxs-lookup"><span data-stu-id="70ce9-116">Total peer-to-peer video minutes</span></span>

</div>

<div>

## <a name="to-make-the-best-use-of-the-peer-to-peer-voice-and-video-report"></a><span data-ttu-id="70ce9-117">Доступ к отчету об одноранговой голосовой связи и видеосвязи</span><span class="sxs-lookup"><span data-stu-id="70ce9-117">To make the best use of the peer-to-peer voice and video report</span></span>

<span data-ttu-id="70ce9-p102">Существует несколько способ фильтрации отчета об одноранговой голосовой связи и видеосвязи. Однако по умолчанию эти параметры фильтрации скрыты. Чтобы просмотреть их, нажмите кнопку **Показать/скрыть параметры** в верхнем правом углу окна отчета.</span><span class="sxs-lookup"><span data-stu-id="70ce9-p102">There are a number of ways you can filter the Peer-to-Peer Voice and Video Report. However, those filtering options are hidden from view by default. To view the filtering options available to you, click **Show/Hide Parameters** button in the upper-right corner of the Report window.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="70ce9-121">Фильтры</span><span class="sxs-lookup"><span data-stu-id="70ce9-121">Filters</span></span>

<span data-ttu-id="70ce9-p103">Фильтры позволяют вам возвратить уточненный набор данных или просматривать возвращенные данные различными способами. В следующей таблице перечислены фильтры, которые вы можете использовать в отчете об одноранговой голосовой связи и видеосвязи.</span><span class="sxs-lookup"><span data-stu-id="70ce9-p103">Filters provide a way for you to return a more finely targeted set of data or to view the data in different ways. The following table lists the filters that you can use with the Peer-to-Peer Voice and Video Report.</span></span>

### <a name="peer-to-peer-voice-and-video-report-filters"></a><span data-ttu-id="70ce9-124">Фильтры отчета об одноранговой голосовой связи и видеосвязи</span><span class="sxs-lookup"><span data-stu-id="70ce9-124">Peer-to-peer voice and video report filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="70ce9-125">Имя</span><span class="sxs-lookup"><span data-stu-id="70ce9-125">Name</span></span></th>
<th><span data-ttu-id="70ce9-126">Описание</span><span class="sxs-lookup"><span data-stu-id="70ce9-126">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="70ce9-127"><strong>От</strong></span><span class="sxs-lookup"><span data-stu-id="70ce9-127"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="70ce9-p104">Начальная дата и начальное время для диапазона времени. Чтобы просмотреть данные по часам, введите начальную дату и начальное время в следующем формате:</span><span class="sxs-lookup"><span data-stu-id="70ce9-p104">Start date and time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="70ce9-130">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="70ce9-130">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="70ce9-p105">Если вы не вводите начальное время, отчет автоматически начинается с 12:00 AM указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</span><span class="sxs-lookup"><span data-stu-id="70ce9-p105">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="70ce9-133">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="70ce9-133">7/7/2012</span></span></p>
<p><span data-ttu-id="70ce9-134">Чтобы просмотреть данные за неделю или месяц, введите дату, выпадающую на любое время в рамках недели или месяца, которые вы хотите просмотреть (вам не требуется вводить первый день недели или месяца):</span><span class="sxs-lookup"><span data-stu-id="70ce9-134">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="70ce9-135">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="70ce9-135">7/3/2012</span></span></p>
<p><span data-ttu-id="70ce9-136">Недели всегда отсчитываются с воскресенья по субботу.</span><span class="sxs-lookup"><span data-stu-id="70ce9-136">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70ce9-137"><strong>До</strong></span><span class="sxs-lookup"><span data-stu-id="70ce9-137"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="70ce9-p106">Конечные дата/время для временного диапазона. Чтобы просмотреть данные по часам, введите конечные дату и время следующим образом:</span><span class="sxs-lookup"><span data-stu-id="70ce9-p106">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="70ce9-140">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="70ce9-140">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="70ce9-p107">Если вы не вводите конечное время, отчет автоматически заканчивается в 12:00 AM указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</span><span class="sxs-lookup"><span data-stu-id="70ce9-p107">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="70ce9-143">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="70ce9-143">7/7/2012</span></span></p>
<p><span data-ttu-id="70ce9-144">Чтобы просмотреть данные за неделю или месяц, введите дату, выпадающую на любое время в рамках недели или месяца, которые вы хотите просмотреть (вам не требуется вводить первый день недели или месяца):</span><span class="sxs-lookup"><span data-stu-id="70ce9-144">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="70ce9-145">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="70ce9-145">7/3/2012</span></span></p>
<p><span data-ttu-id="70ce9-146">Недели всегда отсчитываются с воскресенья по субботу.</span><span class="sxs-lookup"><span data-stu-id="70ce9-146">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70ce9-147"><strong>Интервал</strong></span><span class="sxs-lookup"><span data-stu-id="70ce9-147"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="70ce9-p108">Временной интервал. Выберите одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="70ce9-p108">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="70ce9-150">Ежечасно (можно отобразить не более 25 часов)</span><span class="sxs-lookup"><span data-stu-id="70ce9-150">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="70ce9-151">Ежедневно (можно отобразить не более 31 дня)</span><span class="sxs-lookup"><span data-stu-id="70ce9-151">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="70ce9-152">Еженедельно (можно отобразить не более 12 недель)</span><span class="sxs-lookup"><span data-stu-id="70ce9-152">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="70ce9-153">Ежемесячно (можно отобразить не более 12 месяцев)</span><span class="sxs-lookup"><span data-stu-id="70ce9-153">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="70ce9-154">Если количество значений между начальной и конечной датами превышает максимально допустимое для выбранного интервала, отображается максимальное возможное количество значений (от начальной даты и далее).</span><span class="sxs-lookup"><span data-stu-id="70ce9-154">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed.</span></span> <span data-ttu-id="70ce9-155">Например, если выбрать ежедневный интервал с датой начала 7/7/2012 и датой окончания 2/28/2012, данные будут выводиться для дней 8/7/2012 12:00 – 9/7/2012 12:00 AM (то есть, всего за 31 дня).</span><span class="sxs-lookup"><span data-stu-id="70ce9-155">For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70ce9-156"><strong>Тип мультимедиа</strong></span><span class="sxs-lookup"><span data-stu-id="70ce9-156"><strong>Media type</strong></span></span></p></td>
<td><p><span data-ttu-id="70ce9-p110">Указывает используемый в сеансе тип мультимедиа. Выберите одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="70ce9-p110">Indicates the type of media used in the session. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="70ce9-159">Both</span><span class="sxs-lookup"><span data-stu-id="70ce9-159">Both</span></span></p></li>
<li><p><span data-ttu-id="70ce9-160">Аудио</span><span class="sxs-lookup"><span data-stu-id="70ce9-160">Audio</span></span></p></li>
<li><p><span data-ttu-id="70ce9-161">Видео</span><span class="sxs-lookup"><span data-stu-id="70ce9-161">Video</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70ce9-162"><strong>Расположение звонка</strong></span><span class="sxs-lookup"><span data-stu-id="70ce9-162"><strong>Call disposition</strong></span></span></p></td>
<td><p><span data-ttu-id="70ce9-p111">Указывает, был ли сеанс успешным. Выберите одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="70ce9-p111">Indicates the success or failure of the session. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="70ce9-165">[All] (Все)</span><span class="sxs-lookup"><span data-stu-id="70ce9-165">[All]</span></span></p></li>
<li><p><span data-ttu-id="70ce9-166">Success Calls (Успешные звонки)</span><span class="sxs-lookup"><span data-stu-id="70ce9-166">Success Calls</span></span></p></li>
<li><p><span data-ttu-id="70ce9-167">Failed Calls (Звонки со сбоем)</span><span class="sxs-lookup"><span data-stu-id="70ce9-167">Failed Calls</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70ce9-168"><strong>Report by (Отчетность)</strong></span><span class="sxs-lookup"><span data-stu-id="70ce9-168"><strong>Report by</strong></span></span></p></td>
<td><p><span data-ttu-id="70ce9-p112">Указывает значения для использования в отчете. Выберите одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="70ce9-p112">Indicates the values to be used in the report. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="70ce9-171">Session count (Число сеансов)</span><span class="sxs-lookup"><span data-stu-id="70ce9-171">Session count</span></span></p></li>
<li><p><span data-ttu-id="70ce9-172">Call minutes (Число минут звонков)</span><span class="sxs-lookup"><span data-stu-id="70ce9-172">Call minutes</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-pool"></a><span data-ttu-id="70ce9-173">Метрики для операций одноранговой голосовой связи и видеосвязи по пулам</span><span class="sxs-lookup"><span data-stu-id="70ce9-173">Metrics for peer-to-peer voice and video activity by Pool</span></span>

<span data-ttu-id="70ce9-174">В следующей таблице перечислены сведения, представленные в отчете об одноранговой голосовой связи и видеосвязи для каждого пула.</span><span class="sxs-lookup"><span data-stu-id="70ce9-174">The following table lists the information provided in the Peer-to-Peer Voice and Video Report for each pool.</span></span>

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-pool"></a><span data-ttu-id="70ce9-175">Метрики для операций одноранговой голосовой связи и видеосвязи по пулам</span><span class="sxs-lookup"><span data-stu-id="70ce9-175">Metrics for peer-to-peer voice and video activity by pool</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="70ce9-176">Имя</span><span class="sxs-lookup"><span data-stu-id="70ce9-176">Name</span></span></th>
<th><span data-ttu-id="70ce9-177">Поддержка сортировки</span><span class="sxs-lookup"><span data-stu-id="70ce9-177">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="70ce9-178">Описание</span><span class="sxs-lookup"><span data-stu-id="70ce9-178">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="70ce9-179"><strong>Пул</strong></span><span class="sxs-lookup"><span data-stu-id="70ce9-179"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="70ce9-180">Нет</span><span class="sxs-lookup"><span data-stu-id="70ce9-180">No</span></span></p></td>
<td><p><span data-ttu-id="70ce9-181">Имя пула регистраторов или пограничного сервера, используемого для звонка.</span><span class="sxs-lookup"><span data-stu-id="70ce9-181">Name of the Registrar pool or Edge Server used for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70ce9-182"><strong>Дата/время</strong></span><span class="sxs-lookup"><span data-stu-id="70ce9-182"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="70ce9-183">Нет</span><span class="sxs-lookup"><span data-stu-id="70ce9-183">No</span></span></p></td>
<td><p><span data-ttu-id="70ce9-184">Дата и период времени, когда был выполнен звонок.</span><span class="sxs-lookup"><span data-stu-id="70ce9-184">Date and time period in which the call took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70ce9-185"><strong>Всего</strong></span><span class="sxs-lookup"><span data-stu-id="70ce9-185"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="70ce9-186">Нет</span><span class="sxs-lookup"><span data-stu-id="70ce9-186">No</span></span></p></td>
<td><p><span data-ttu-id="70ce9-187">Общее число сеансов или сообщений.</span><span class="sxs-lookup"><span data-stu-id="70ce9-187">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-call-type"></a><span data-ttu-id="70ce9-188">Метрики для операций одноранговой голосовой связи и видеосвязи по типу вызова</span><span class="sxs-lookup"><span data-stu-id="70ce9-188">Metrics for peer-to-peer voice and video activity by call type</span></span>

<span data-ttu-id="70ce9-189">В следующей таблице перечислены сведения, представленные в отчете об одноранговой голосовой связи и видеосвязи для каждого типа выполненных звонков.</span><span class="sxs-lookup"><span data-stu-id="70ce9-189">The following table lists the information provided in the Peer-to-Peer Voice and Video Report for each type of call that was made.</span></span>

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-call-type"></a><span data-ttu-id="70ce9-190">Метрики для операций одноранговой голосовой связи и видеосвязи по типу вызова</span><span class="sxs-lookup"><span data-stu-id="70ce9-190">Metrics for peer-to-peer voice and video activity by call type</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="70ce9-191">Имя</span><span class="sxs-lookup"><span data-stu-id="70ce9-191">Name</span></span></th>
<th><span data-ttu-id="70ce9-192">Поддержка сортировки</span><span class="sxs-lookup"><span data-stu-id="70ce9-192">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="70ce9-193">Описание</span><span class="sxs-lookup"><span data-stu-id="70ce9-193">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="70ce9-194"><strong>Тип вызова</strong></span><span class="sxs-lookup"><span data-stu-id="70ce9-194"><strong>Call type</strong></span></span></p></td>
<td><p><span data-ttu-id="70ce9-195">Нет</span><span class="sxs-lookup"><span data-stu-id="70ce9-195">No</span></span></p></td>
<td><p><span data-ttu-id="70ce9-p113">Указывает тип выполненного звонка. Доступны следующие значения:</span><span class="sxs-lookup"><span data-stu-id="70ce9-p113">Indicates the type of call that was made. Values are one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="70ce9-198">UC-to-UC (Из объединенных коммуникаций в объединенные коммуникации)</span><span class="sxs-lookup"><span data-stu-id="70ce9-198">UC-to-UC</span></span></p></li>
<li><p><span data-ttu-id="70ce9-199">UC-to-PSTN (Из объединенных коммуникаций в ТСОП)</span><span class="sxs-lookup"><span data-stu-id="70ce9-199">UC-to-PSTN</span></span></p></li>
<li><p><span data-ttu-id="70ce9-200">PSTN-to-UC (Из ТСОП в объединенные коммуникации)</span><span class="sxs-lookup"><span data-stu-id="70ce9-200">PSTN-to-UC</span></span></p></li>
<li><p><span data-ttu-id="70ce9-201">PSTN-to-PSTN (Из ТСОП в ТСОП)</span><span class="sxs-lookup"><span data-stu-id="70ce9-201">PSTN-to-PSTN</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70ce9-202"><strong>Дата/время</strong></span><span class="sxs-lookup"><span data-stu-id="70ce9-202"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="70ce9-203">Нет</span><span class="sxs-lookup"><span data-stu-id="70ce9-203">No</span></span></p></td>
<td><p><span data-ttu-id="70ce9-204">Дата и период времени, когда был выполнен звонок.</span><span class="sxs-lookup"><span data-stu-id="70ce9-204">Date and time period in which the call took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70ce9-205"><strong>Всего</strong></span><span class="sxs-lookup"><span data-stu-id="70ce9-205"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="70ce9-206">Нет</span><span class="sxs-lookup"><span data-stu-id="70ce9-206">No</span></span></p></td>
<td><p><span data-ttu-id="70ce9-207">Общее число сеансов или сообщений.</span><span class="sxs-lookup"><span data-stu-id="70ce9-207">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-access-type"></a><span data-ttu-id="70ce9-208">Метрики для операций одноранговой голосовой связи и видеосвязи по типу доступа</span><span class="sxs-lookup"><span data-stu-id="70ce9-208">Metrics for peer-to-peer voice and video activity by access type</span></span>

<span data-ttu-id="70ce9-209">В следующей таблице перечислены сведения, представленные в отчете об одноранговой голосовой связи и видеосвязи для каждого типа сетевого доступа.</span><span class="sxs-lookup"><span data-stu-id="70ce9-209">The following table lists the information provided in the Peer-to-Peer Voice and Video Report for each network access type.</span></span>

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-access-type"></a><span data-ttu-id="70ce9-210">Метрики для операций одноранговой голосовой связи и видеосвязи по типу доступа</span><span class="sxs-lookup"><span data-stu-id="70ce9-210">Metrics for peer-to-peer voice and video activity by access type</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="70ce9-211">Имя</span><span class="sxs-lookup"><span data-stu-id="70ce9-211">Name</span></span></th>
<th><span data-ttu-id="70ce9-212">Поддержка сортировки</span><span class="sxs-lookup"><span data-stu-id="70ce9-212">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="70ce9-213">Описание</span><span class="sxs-lookup"><span data-stu-id="70ce9-213">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="70ce9-214"><strong>Тип сеанса</strong></span><span class="sxs-lookup"><span data-stu-id="70ce9-214"><strong>Activity type</strong></span></span></p></td>
<td><p><span data-ttu-id="70ce9-215">Нет</span><span class="sxs-lookup"><span data-stu-id="70ce9-215">No</span></span></p></td>
<td><p><span data-ttu-id="70ce9-p114">Указывает, выполняли ли клиенты вход во внутреннюю или во внешнюю сеть при совершении звонка. Обычно доступны следующие значения:</span><span class="sxs-lookup"><span data-stu-id="70ce9-p114">Indicates whether the clients were logged on to the internal network or the external network when the call was placed. Values are typically one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="70ce9-218">Internal</span><span class="sxs-lookup"><span data-stu-id="70ce9-218">Internal</span></span></p></li>
<li><p><span data-ttu-id="70ce9-219">Внешняя</span><span class="sxs-lookup"><span data-stu-id="70ce9-219">External</span></span></p></li>
<li><p><span data-ttu-id="70ce9-220">Mixed (Обе)</span><span class="sxs-lookup"><span data-stu-id="70ce9-220">Mixed</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70ce9-221"><strong>Дата/время</strong></span><span class="sxs-lookup"><span data-stu-id="70ce9-221"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="70ce9-222">Нет</span><span class="sxs-lookup"><span data-stu-id="70ce9-222">No</span></span></p></td>
<td><p><span data-ttu-id="70ce9-223">Дата и период времени, когда был выполнен звонок.</span><span class="sxs-lookup"><span data-stu-id="70ce9-223">Date and time period in which the call took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70ce9-224"><strong>Всего</strong></span><span class="sxs-lookup"><span data-stu-id="70ce9-224"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="70ce9-225">Нет</span><span class="sxs-lookup"><span data-stu-id="70ce9-225">No</span></span></p></td>
<td><p><span data-ttu-id="70ce9-226">Общее число сеансов или сообщений.</span><span class="sxs-lookup"><span data-stu-id="70ce9-226">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-mediation-server"></a><span data-ttu-id="70ce9-227">Метрики для операций одноранговой голосовой связи и видеосвязи по серверу-посреднику</span><span class="sxs-lookup"><span data-stu-id="70ce9-227">Metrics for peer-to-peer voice and video activity by mediation server</span></span>

<span data-ttu-id="70ce9-228">В таблице ниже приведены сведения, которые содержатся в видеоотчетах одноранговых и видеофайлов для каждого сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="70ce9-228">The following table lists the information provided in the Peer-to-Peer Voice and Video Report for each Mediation Server.</span></span>

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-mediation-server"></a><span data-ttu-id="70ce9-229">Метрики для операций одноранговой голосовой связи и видеосвязи по серверу-посреднику</span><span class="sxs-lookup"><span data-stu-id="70ce9-229">Metrics for peer-to-peer voice and video activity by mediation server</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="70ce9-230">Имя</span><span class="sxs-lookup"><span data-stu-id="70ce9-230">Name</span></span></th>
<th><span data-ttu-id="70ce9-231">Поддержка сортировки</span><span class="sxs-lookup"><span data-stu-id="70ce9-231">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="70ce9-232">Описание</span><span class="sxs-lookup"><span data-stu-id="70ce9-232">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="70ce9-233"><strong>посредник</strong></span><span class="sxs-lookup"><span data-stu-id="70ce9-233"><strong>Mediation Server</strong></span></span></p></td>
<td><p><span data-ttu-id="70ce9-234">Нет</span><span class="sxs-lookup"><span data-stu-id="70ce9-234">No</span></span></p></td>
<td><p><span data-ttu-id="70ce9-235">Имя сервера обновлений.</span><span class="sxs-lookup"><span data-stu-id="70ce9-235">Name of the Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70ce9-236"><strong>Дата/время</strong></span><span class="sxs-lookup"><span data-stu-id="70ce9-236"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="70ce9-237">Нет</span><span class="sxs-lookup"><span data-stu-id="70ce9-237">No</span></span></p></td>
<td><p><span data-ttu-id="70ce9-238">Дата и период времени, когда был выполнен звонок.</span><span class="sxs-lookup"><span data-stu-id="70ce9-238">Date and time period in which the call took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70ce9-239"><strong>Всего</strong></span><span class="sxs-lookup"><span data-stu-id="70ce9-239"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="70ce9-240">Нет</span><span class="sxs-lookup"><span data-stu-id="70ce9-240">No</span></span></p></td>
<td><p><span data-ttu-id="70ce9-241">Общее число сеансов или сообщений.</span><span class="sxs-lookup"><span data-stu-id="70ce9-241">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

