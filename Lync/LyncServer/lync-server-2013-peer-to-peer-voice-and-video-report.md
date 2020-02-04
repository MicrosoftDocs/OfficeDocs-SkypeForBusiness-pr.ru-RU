---
title: 'Lync Server 2013: одноранговый голосовой и видео отчет'
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
ms.openlocfilehash: 68cddb8296a94ff5d5b084895024d7379a42022c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755289"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="peer-to-peer-voice-and-video-report-in-lync-server-2013"></a><span data-ttu-id="dfaa4-102">Одноранговый голосовой и Видеоотчет в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dfaa4-102">Peer-to-Peer Voice and Video Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dfaa4-103">_**Тема последнего изменения:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="dfaa4-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="dfaa4-p101">Отчет об одноранговой голосовой связи и видеосвязи дает подробное представление о распределении голосовых звонках и видеозвонках за указанный период (например, число звонков в час или в день). Кроме того, этот отчет позволяет просматривать все выполненные голосовые звонки и видеозвонки или только те из них, которые были успешными или завершились со сбоем. Сведения о звонках в отчете упорядочены по следующим группам:</span><span class="sxs-lookup"><span data-stu-id="dfaa4-p101">The Peer-to-Peer Voice and Video Report provides a detailed look at the distribution of voice and video calls over a specified period of time (for example, calls per hour or calls per day). The report also gives you the option of viewing all the voice and video calls that were made, or of viewing only the successful or failed calls. The reports shows call information broken down into the following groupings:</span></span>

  - <span data-ttu-id="dfaa4-107">Число звонков на пул</span><span class="sxs-lookup"><span data-stu-id="dfaa4-107">Calls per pool</span></span>

  - <span data-ttu-id="dfaa4-108">Звонки на тип звонка (например, Lync для звонков по Lync и вызов Lync для абонента в сети PSTN).</span><span class="sxs-lookup"><span data-stu-id="dfaa4-108">Calls per call type (for example, a Lync to Lync call vs. a Lync call to a person on the PSTN network)</span></span>

  - <span data-ttu-id="dfaa4-109">Звонки по типу доступа (пользователи, выполнившие вход во внутреннюю сеть, либо пользователи, выполнившие вход во внешнюю сеть)</span><span class="sxs-lookup"><span data-stu-id="dfaa4-109">Calls per access type (users logged on to the internal network vs. users logged on to the external network)</span></span>

  - <span data-ttu-id="dfaa4-110">Звонки на сервер по исправлению</span><span class="sxs-lookup"><span data-stu-id="dfaa4-110">Calls per Mediation Server</span></span>

<div>

## <a name="to-access-the-peer-to-peer-voice-and-video-report"></a><span data-ttu-id="dfaa4-111">Доступ к отчету об одноранговой голосовой связи и видеосвязи</span><span class="sxs-lookup"><span data-stu-id="dfaa4-111">To access the peer-to-peer voice and video report</span></span>

<span data-ttu-id="dfaa4-112">Отчет об одноранговой голосовой связи и видеосвязи можно просмотреть, открыв сводный отчет об одноранговых операциях и щелкнув одну из следующих метрик:</span><span class="sxs-lookup"><span data-stu-id="dfaa4-112">You can access the Peer-to-Peer Voice and Video Report only by opening the Peer-to-Peer Activity Summary Report and then clicking any of the following metrics:</span></span>

  - <span data-ttu-id="dfaa4-113">Общее количество одноранговых сеансов аудиосвязи</span><span class="sxs-lookup"><span data-stu-id="dfaa4-113">Total peer-to-peer audio sessions</span></span>

  - <span data-ttu-id="dfaa4-114">Общее число минут одноранговой аудиосвязи (Общее число минут одноранговой аудиосвязи)</span><span class="sxs-lookup"><span data-stu-id="dfaa4-114">Total peer-to-peer audio minutes</span></span>

  - <span data-ttu-id="dfaa4-115">Общее количество одноранговых сеансов видеосвязи</span><span class="sxs-lookup"><span data-stu-id="dfaa4-115">Total peer-to-peer video sessions</span></span>

  - <span data-ttu-id="dfaa4-116">Общее число минут одноранговой видеосвязи (Общее число минут одноранговой видеосвязи)</span><span class="sxs-lookup"><span data-stu-id="dfaa4-116">Total peer-to-peer video minutes</span></span>

</div>

<div>

## <a name="to-make-the-best-use-of-the-peer-to-peer-voice-and-video-report"></a><span data-ttu-id="dfaa4-117">Доступ к отчету об одноранговой голосовой связи и видеосвязи</span><span class="sxs-lookup"><span data-stu-id="dfaa4-117">To make the best use of the peer-to-peer voice and video report</span></span>

<span data-ttu-id="dfaa4-p102">Существует несколько способ фильтрации отчета об одноранговой голосовой связи и видеосвязи. Однако по умолчанию эти параметры фильтрации скрыты. Чтобы просмотреть их, нажмите кнопку **Показать/скрыть параметры** в верхнем правом углу окна отчета.</span><span class="sxs-lookup"><span data-stu-id="dfaa4-p102">There are a number of ways you can filter the Peer-to-Peer Voice and Video Report. However, those filtering options are hidden from view by default. To view the filtering options available to you, click **Show/Hide Parameters** button in the upper-right corner of the Report window.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="dfaa4-121">Фильтры</span><span class="sxs-lookup"><span data-stu-id="dfaa4-121">Filters</span></span>

<span data-ttu-id="dfaa4-p103">Фильтры позволяют вам возвратить уточненный набор данных или просматривать возвращенные данные различными способами. В следующей таблице перечислены фильтры, которые вы можете использовать в отчете об одноранговой голосовой связи и видеосвязи.</span><span class="sxs-lookup"><span data-stu-id="dfaa4-p103">Filters provide a way for you to return a more finely targeted set of data or to view the data in different ways. The following table lists the filters that you can use with the Peer-to-Peer Voice and Video Report.</span></span>

### <a name="peer-to-peer-voice-and-video-report-filters"></a><span data-ttu-id="dfaa4-124">Фильтры отчета об одноранговой голосовой связи и видеосвязи</span><span class="sxs-lookup"><span data-stu-id="dfaa4-124">Peer-to-peer voice and video report filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dfaa4-125">Имя</span><span class="sxs-lookup"><span data-stu-id="dfaa4-125">Name</span></span></th>
<th><span data-ttu-id="dfaa4-126">Описание</span><span class="sxs-lookup"><span data-stu-id="dfaa4-126">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dfaa4-127"><strong>От</strong></span><span class="sxs-lookup"><span data-stu-id="dfaa4-127"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="dfaa4-p104">Начальная дата и начальное время для диапазона времени. Чтобы просмотреть данные по часам, введите начальную дату и начальное время в следующем формате:</span><span class="sxs-lookup"><span data-stu-id="dfaa4-p104">Start date and time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="dfaa4-130">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="dfaa4-130">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="dfaa4-p105">Если вы не вводите начальное время, отчет автоматически начинается с 12:00 AM указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</span><span class="sxs-lookup"><span data-stu-id="dfaa4-p105">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="dfaa4-133">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="dfaa4-133">7/7/2012</span></span></p>
<p><span data-ttu-id="dfaa4-134">Чтобы просмотреть данные за неделю или месяц, введите дату, выпадающую на любое время в рамках недели или месяца, которые вы хотите просмотреть (вам не требуется вводить первый день недели или месяца):</span><span class="sxs-lookup"><span data-stu-id="dfaa4-134">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="dfaa4-135">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="dfaa4-135">7/3/2012</span></span></p>
<p><span data-ttu-id="dfaa4-136">Недели всегда отсчитываются с воскресенья по субботу.</span><span class="sxs-lookup"><span data-stu-id="dfaa4-136">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfaa4-137"><strong>До</strong></span><span class="sxs-lookup"><span data-stu-id="dfaa4-137"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="dfaa4-p106">Конечные дата/время для временного диапазона. Чтобы просмотреть данные по часам, введите конечные дату и время следующим образом:</span><span class="sxs-lookup"><span data-stu-id="dfaa4-p106">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="dfaa4-140">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="dfaa4-140">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="dfaa4-p107">Если вы не вводите конечное время, отчет автоматически заканчивается в 12:00 AM указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</span><span class="sxs-lookup"><span data-stu-id="dfaa4-p107">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="dfaa4-143">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="dfaa4-143">7/7/2012</span></span></p>
<p><span data-ttu-id="dfaa4-144">Чтобы просмотреть данные за неделю или месяц, введите дату, выпадающую на любое время в рамках недели или месяца, которые вы хотите просмотреть (вам не требуется вводить первый день недели или месяца):</span><span class="sxs-lookup"><span data-stu-id="dfaa4-144">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="dfaa4-145">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="dfaa4-145">7/3/2012</span></span></p>
<p><span data-ttu-id="dfaa4-146">Недели всегда отсчитываются с воскресенья по субботу.</span><span class="sxs-lookup"><span data-stu-id="dfaa4-146">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfaa4-147"><strong>Интервал</strong></span><span class="sxs-lookup"><span data-stu-id="dfaa4-147"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="dfaa4-p108">Временной интервал. Выберите одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="dfaa4-p108">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="dfaa4-150">Ежечасно (можно отобразить не более 25 часов)</span><span class="sxs-lookup"><span data-stu-id="dfaa4-150">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="dfaa4-151">Ежедневно (можно отобразить не более 31 дня)</span><span class="sxs-lookup"><span data-stu-id="dfaa4-151">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="dfaa4-152">Еженедельно (можно отобразить не более 12 недель)</span><span class="sxs-lookup"><span data-stu-id="dfaa4-152">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="dfaa4-153">Ежемесячно (можно отобразить не более 12 месяцев)</span><span class="sxs-lookup"><span data-stu-id="dfaa4-153">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="dfaa4-154">Если количество значений между начальной и конечной датами превышает максимально допустимое для выбранного интервала, отображается максимальное возможное количество значений (от начальной даты и далее).</span><span class="sxs-lookup"><span data-stu-id="dfaa4-154">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed.</span></span> <span data-ttu-id="dfaa4-155">Например, если выбрать ежедневный интервал с датой начала 7/7/2012 и датой окончания 2/28/2012, данные будут выводиться для дней 8/7/2012 12:00 – 9/7/2012 12:00 AM (то есть, всего за 31 дня).</span><span class="sxs-lookup"><span data-stu-id="dfaa4-155">For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfaa4-156"><strong>Тип мультимедиа</strong></span><span class="sxs-lookup"><span data-stu-id="dfaa4-156"><strong>Media type</strong></span></span></p></td>
<td><p><span data-ttu-id="dfaa4-p110">Указывает используемый в сеансе тип мультимедиа. Выберите одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="dfaa4-p110">Indicates the type of media used in the session. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="dfaa4-159">Both</span><span class="sxs-lookup"><span data-stu-id="dfaa4-159">Both</span></span></p></li>
<li><p><span data-ttu-id="dfaa4-160">Аудио</span><span class="sxs-lookup"><span data-stu-id="dfaa4-160">Audio</span></span></p></li>
<li><p><span data-ttu-id="dfaa4-161">Видео</span><span class="sxs-lookup"><span data-stu-id="dfaa4-161">Video</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfaa4-162"><strong>Расположение звонка</strong></span><span class="sxs-lookup"><span data-stu-id="dfaa4-162"><strong>Call disposition</strong></span></span></p></td>
<td><p><span data-ttu-id="dfaa4-p111">Указывает, был ли сеанс успешным. Выберите одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="dfaa4-p111">Indicates the success or failure of the session. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="dfaa4-165">[All] (Все)</span><span class="sxs-lookup"><span data-stu-id="dfaa4-165">[All]</span></span></p></li>
<li><p><span data-ttu-id="dfaa4-166">Success Calls (Успешные звонки)</span><span class="sxs-lookup"><span data-stu-id="dfaa4-166">Success Calls</span></span></p></li>
<li><p><span data-ttu-id="dfaa4-167">Failed Calls (Звонки со сбоем)</span><span class="sxs-lookup"><span data-stu-id="dfaa4-167">Failed Calls</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfaa4-168"><strong>Report by (Отчетность)</strong></span><span class="sxs-lookup"><span data-stu-id="dfaa4-168"><strong>Report by</strong></span></span></p></td>
<td><p><span data-ttu-id="dfaa4-p112">Указывает значения для использования в отчете. Выберите одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="dfaa4-p112">Indicates the values to be used in the report. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="dfaa4-171">Session count (Число сеансов)</span><span class="sxs-lookup"><span data-stu-id="dfaa4-171">Session count</span></span></p></li>
<li><p><span data-ttu-id="dfaa4-172">Call minutes (Число минут звонков)</span><span class="sxs-lookup"><span data-stu-id="dfaa4-172">Call minutes</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-pool"></a><span data-ttu-id="dfaa4-173">Метрики для операций одноранговой голосовой связи и видеосвязи по пулам</span><span class="sxs-lookup"><span data-stu-id="dfaa4-173">Metrics for peer-to-peer voice and video activity by Pool</span></span>

<span data-ttu-id="dfaa4-174">В следующей таблице перечислены сведения, представленные в отчете об одноранговой голосовой связи и видеосвязи для каждого пула.</span><span class="sxs-lookup"><span data-stu-id="dfaa4-174">The following table lists the information provided in the Peer-to-Peer Voice and Video Report for each pool.</span></span>

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-pool"></a><span data-ttu-id="dfaa4-175">Метрики для операций одноранговой голосовой связи и видеосвязи по пулам</span><span class="sxs-lookup"><span data-stu-id="dfaa4-175">Metrics for peer-to-peer voice and video activity by pool</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dfaa4-176">Имя</span><span class="sxs-lookup"><span data-stu-id="dfaa4-176">Name</span></span></th>
<th><span data-ttu-id="dfaa4-177">Поддержка сортировки</span><span class="sxs-lookup"><span data-stu-id="dfaa4-177">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="dfaa4-178">Описание</span><span class="sxs-lookup"><span data-stu-id="dfaa4-178">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dfaa4-179"><strong>Пул</strong></span><span class="sxs-lookup"><span data-stu-id="dfaa4-179"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="dfaa4-180">Нет</span><span class="sxs-lookup"><span data-stu-id="dfaa4-180">No</span></span></p></td>
<td><p><span data-ttu-id="dfaa4-181">Имя пула регистраторов или пограничного сервера, используемого для звонка.</span><span class="sxs-lookup"><span data-stu-id="dfaa4-181">Name of the Registrar pool or Edge Server used for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfaa4-182"><strong>Дата/время</strong></span><span class="sxs-lookup"><span data-stu-id="dfaa4-182"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="dfaa4-183">Нет</span><span class="sxs-lookup"><span data-stu-id="dfaa4-183">No</span></span></p></td>
<td><p><span data-ttu-id="dfaa4-184">Дата и период времени, когда был выполнен звонок.</span><span class="sxs-lookup"><span data-stu-id="dfaa4-184">Date and time period in which the call took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfaa4-185"><strong>Всего</strong></span><span class="sxs-lookup"><span data-stu-id="dfaa4-185"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="dfaa4-186">Нет</span><span class="sxs-lookup"><span data-stu-id="dfaa4-186">No</span></span></p></td>
<td><p><span data-ttu-id="dfaa4-187">Общее число сеансов или сообщений.</span><span class="sxs-lookup"><span data-stu-id="dfaa4-187">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-call-type"></a><span data-ttu-id="dfaa4-188">Метрики для операций одноранговой голосовой связи и видеосвязи по типу вызова</span><span class="sxs-lookup"><span data-stu-id="dfaa4-188">Metrics for peer-to-peer voice and video activity by call type</span></span>

<span data-ttu-id="dfaa4-189">В следующей таблице перечислены сведения, представленные в отчете об одноранговой голосовой связи и видеосвязи для каждого типа выполненных звонков.</span><span class="sxs-lookup"><span data-stu-id="dfaa4-189">The following table lists the information provided in the Peer-to-Peer Voice and Video Report for each type of call that was made.</span></span>

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-call-type"></a><span data-ttu-id="dfaa4-190">Метрики для операций одноранговой голосовой связи и видеосвязи по типу вызова</span><span class="sxs-lookup"><span data-stu-id="dfaa4-190">Metrics for peer-to-peer voice and video activity by call type</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dfaa4-191">Имя</span><span class="sxs-lookup"><span data-stu-id="dfaa4-191">Name</span></span></th>
<th><span data-ttu-id="dfaa4-192">Поддержка сортировки</span><span class="sxs-lookup"><span data-stu-id="dfaa4-192">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="dfaa4-193">Описание</span><span class="sxs-lookup"><span data-stu-id="dfaa4-193">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dfaa4-194"><strong>Тип вызова</strong></span><span class="sxs-lookup"><span data-stu-id="dfaa4-194"><strong>Call type</strong></span></span></p></td>
<td><p><span data-ttu-id="dfaa4-195">Нет</span><span class="sxs-lookup"><span data-stu-id="dfaa4-195">No</span></span></p></td>
<td><p><span data-ttu-id="dfaa4-p113">Указывает тип выполненного звонка. Доступны следующие значения:</span><span class="sxs-lookup"><span data-stu-id="dfaa4-p113">Indicates the type of call that was made. Values are one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="dfaa4-198">UC-to-UC (Из объединенных коммуникаций в объединенные коммуникации)</span><span class="sxs-lookup"><span data-stu-id="dfaa4-198">UC-to-UC</span></span></p></li>
<li><p><span data-ttu-id="dfaa4-199">UC-to-PSTN (Из объединенных коммуникаций в ТСОП)</span><span class="sxs-lookup"><span data-stu-id="dfaa4-199">UC-to-PSTN</span></span></p></li>
<li><p><span data-ttu-id="dfaa4-200">PSTN-to-UC (Из ТСОП в объединенные коммуникации)</span><span class="sxs-lookup"><span data-stu-id="dfaa4-200">PSTN-to-UC</span></span></p></li>
<li><p><span data-ttu-id="dfaa4-201">PSTN-to-PSTN (Из ТСОП в ТСОП)</span><span class="sxs-lookup"><span data-stu-id="dfaa4-201">PSTN-to-PSTN</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfaa4-202"><strong>Дата/время</strong></span><span class="sxs-lookup"><span data-stu-id="dfaa4-202"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="dfaa4-203">Нет</span><span class="sxs-lookup"><span data-stu-id="dfaa4-203">No</span></span></p></td>
<td><p><span data-ttu-id="dfaa4-204">Дата и период времени, когда был выполнен звонок.</span><span class="sxs-lookup"><span data-stu-id="dfaa4-204">Date and time period in which the call took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfaa4-205"><strong>Всего</strong></span><span class="sxs-lookup"><span data-stu-id="dfaa4-205"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="dfaa4-206">Нет</span><span class="sxs-lookup"><span data-stu-id="dfaa4-206">No</span></span></p></td>
<td><p><span data-ttu-id="dfaa4-207">Общее число сеансов или сообщений.</span><span class="sxs-lookup"><span data-stu-id="dfaa4-207">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-access-type"></a><span data-ttu-id="dfaa4-208">Метрики для операций одноранговой голосовой связи и видеосвязи по типу доступа</span><span class="sxs-lookup"><span data-stu-id="dfaa4-208">Metrics for peer-to-peer voice and video activity by access type</span></span>

<span data-ttu-id="dfaa4-209">В следующей таблице перечислены сведения, представленные в отчете об одноранговой голосовой связи и видеосвязи для каждого типа сетевого доступа.</span><span class="sxs-lookup"><span data-stu-id="dfaa4-209">The following table lists the information provided in the Peer-to-Peer Voice and Video Report for each network access type.</span></span>

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-access-type"></a><span data-ttu-id="dfaa4-210">Метрики для операций одноранговой голосовой связи и видеосвязи по типу доступа</span><span class="sxs-lookup"><span data-stu-id="dfaa4-210">Metrics for peer-to-peer voice and video activity by access type</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dfaa4-211">Имя</span><span class="sxs-lookup"><span data-stu-id="dfaa4-211">Name</span></span></th>
<th><span data-ttu-id="dfaa4-212">Поддержка сортировки</span><span class="sxs-lookup"><span data-stu-id="dfaa4-212">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="dfaa4-213">Описание</span><span class="sxs-lookup"><span data-stu-id="dfaa4-213">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dfaa4-214"><strong>Тип сеанса</strong></span><span class="sxs-lookup"><span data-stu-id="dfaa4-214"><strong>Activity type</strong></span></span></p></td>
<td><p><span data-ttu-id="dfaa4-215">Нет</span><span class="sxs-lookup"><span data-stu-id="dfaa4-215">No</span></span></p></td>
<td><p><span data-ttu-id="dfaa4-p114">Указывает, выполняли ли клиенты вход во внутреннюю или во внешнюю сеть при совершении звонка. Обычно доступны следующие значения:</span><span class="sxs-lookup"><span data-stu-id="dfaa4-p114">Indicates whether the clients were logged on to the internal network or the external network when the call was placed. Values are typically one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="dfaa4-218">Internal</span><span class="sxs-lookup"><span data-stu-id="dfaa4-218">Internal</span></span></p></li>
<li><p><span data-ttu-id="dfaa4-219">Внешняя</span><span class="sxs-lookup"><span data-stu-id="dfaa4-219">External</span></span></p></li>
<li><p><span data-ttu-id="dfaa4-220">Mixed (Обе)</span><span class="sxs-lookup"><span data-stu-id="dfaa4-220">Mixed</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfaa4-221"><strong>Дата/время</strong></span><span class="sxs-lookup"><span data-stu-id="dfaa4-221"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="dfaa4-222">Нет</span><span class="sxs-lookup"><span data-stu-id="dfaa4-222">No</span></span></p></td>
<td><p><span data-ttu-id="dfaa4-223">Дата и период времени, когда был выполнен звонок.</span><span class="sxs-lookup"><span data-stu-id="dfaa4-223">Date and time period in which the call took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfaa4-224"><strong>Всего</strong></span><span class="sxs-lookup"><span data-stu-id="dfaa4-224"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="dfaa4-225">Нет</span><span class="sxs-lookup"><span data-stu-id="dfaa4-225">No</span></span></p></td>
<td><p><span data-ttu-id="dfaa4-226">Общее число сеансов или сообщений.</span><span class="sxs-lookup"><span data-stu-id="dfaa4-226">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-mediation-server"></a><span data-ttu-id="dfaa4-227">Метрики для операций одноранговой голосовой связи и видеосвязи по серверу-посреднику</span><span class="sxs-lookup"><span data-stu-id="dfaa4-227">Metrics for peer-to-peer voice and video activity by mediation server</span></span>

<span data-ttu-id="dfaa4-228">В таблице ниже приведены сведения, которые содержатся в видеоотчетах одноранговых и видеофайлов для каждого сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="dfaa4-228">The following table lists the information provided in the Peer-to-Peer Voice and Video Report for each Mediation Server.</span></span>

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-mediation-server"></a><span data-ttu-id="dfaa4-229">Метрики для операций одноранговой голосовой связи и видеосвязи по серверу-посреднику</span><span class="sxs-lookup"><span data-stu-id="dfaa4-229">Metrics for peer-to-peer voice and video activity by mediation server</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dfaa4-230">Имя</span><span class="sxs-lookup"><span data-stu-id="dfaa4-230">Name</span></span></th>
<th><span data-ttu-id="dfaa4-231">Поддержка сортировки</span><span class="sxs-lookup"><span data-stu-id="dfaa4-231">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="dfaa4-232">Описание</span><span class="sxs-lookup"><span data-stu-id="dfaa4-232">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dfaa4-233"><strong>посредник</strong></span><span class="sxs-lookup"><span data-stu-id="dfaa4-233"><strong>Mediation Server</strong></span></span></p></td>
<td><p><span data-ttu-id="dfaa4-234">Нет</span><span class="sxs-lookup"><span data-stu-id="dfaa4-234">No</span></span></p></td>
<td><p><span data-ttu-id="dfaa4-235">Имя сервера обновлений.</span><span class="sxs-lookup"><span data-stu-id="dfaa4-235">Name of the Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfaa4-236"><strong>Дата/время</strong></span><span class="sxs-lookup"><span data-stu-id="dfaa4-236"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="dfaa4-237">Нет</span><span class="sxs-lookup"><span data-stu-id="dfaa4-237">No</span></span></p></td>
<td><p><span data-ttu-id="dfaa4-238">Дата и период времени, когда был выполнен звонок.</span><span class="sxs-lookup"><span data-stu-id="dfaa4-238">Date and time period in which the call took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfaa4-239"><strong>Всего</strong></span><span class="sxs-lookup"><span data-stu-id="dfaa4-239"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="dfaa4-240">Нет</span><span class="sxs-lookup"><span data-stu-id="dfaa4-240">No</span></span></p></td>
<td><p><span data-ttu-id="dfaa4-241">Общее число сеансов или сообщений.</span><span class="sxs-lookup"><span data-stu-id="dfaa4-241">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

