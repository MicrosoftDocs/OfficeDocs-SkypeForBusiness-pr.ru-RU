---
title: 'Lync Server 2013: отчет списка обзвона группы ответа'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Response Group Call List Report
ms:assetid: a2d3e08b-511b-4507-abba-8ff71aa27c8e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615443(v=OCS.15)
ms:contentKeyID: 48184954
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 94c06e2029ca1a22a0a9f73249cff3251e2fcbc2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723619"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="response-group-call-list-report-in-lync-server-2013"></a><span data-ttu-id="38c40-102">Отчет списка обзвона группы ответа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="38c40-102">Response Group Call List Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="38c40-103">_**Тема последнего изменения:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="38c40-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="38c40-104">Приложение "группа ответа" позволяет Microsoft Lync Server 2013 отвечать на звонки и направлять их на основании набранного номера и, при необходимости, на ответы вызывающего абонента на ряд вопросов.</span><span class="sxs-lookup"><span data-stu-id="38c40-104">The Response Group application provides a way for Microsoft Lync Server 2013 to answer and route phone calls based on the number that was dialed and, optionally, on the caller's responses to a series of questions.</span></span> <span data-ttu-id="38c40-105">Обычно звонки группы ответа перенаправляются не отдельным пользователям, а группе пользователей, также называемых группой агентов.</span><span class="sxs-lookup"><span data-stu-id="38c40-105">Typically, Response Group calls are not routed to an individual person but, instead, are routed to a team of people referred to as an agent group.</span></span> <span data-ttu-id="38c40-106">Например, если кто-то звонит на номер телефона для службы поддержки, Lync Server 2013 может автоматически перенаправлять этот звонок в первый доступный агент службы поддержки.</span><span class="sxs-lookup"><span data-stu-id="38c40-106">For example, if someone calls the phone number for your help desk, Lync Server 2013 can automatically route that call to the first available help desk agent.</span></span> <span data-ttu-id="38c40-107">Кроме того, Lync Server может задать ряд вопросов ("нажмите 1, если у вас возникли проблемы с оборудованием.</span><span class="sxs-lookup"><span data-stu-id="38c40-107">Alternatively, Lync Server could ask a series of questions ("Press 1 if you are having hardware problems.</span></span> <span data-ttu-id="38c40-108">Если у вас возникли проблемы с программным обеспечением, нажмите 2.</span><span class="sxs-lookup"><span data-stu-id="38c40-108">Press 2 if you are having software problems.</span></span> <span data-ttu-id="38c40-109">Если у вас возникли проблемы с сетью, нажмите клавишу 3. и перенаправить звонок на наиболее подходящий агент службы поддержки в соответствии с ответом на эти вопросы.</span><span class="sxs-lookup"><span data-stu-id="38c40-109">Press 3 if you are having network problems.") and then route the call to the most appropriate help desk agent based on the answer to those questions.</span></span>

<span data-ttu-id="38c40-p102">Отчет Response Group Call List (Список звонков группы ответа) предоставляет список звонков, совершенных за указанный период времени, а также сведения о типах звонков. Отчет Response Group Usage (Использование группы ответа), который необходимо открывать до открытия отчета Response Group Call List (Список звонков группы ответа), содержит следующие типы звонков:</span><span class="sxs-lookup"><span data-stu-id="38c40-p102">The Response Group Call List Report represents a collection of calls made for a specified period of time and for a specified type of call. The Response Group Usage Report (which must be opened first before you can open the Response Group Call List Report) recognizes the following call types:</span></span>

  - <span data-ttu-id="38c40-p103">**Полученные звонки**. Общее число звонков, полученных всеми экземплярами приложения «Группа ответа».</span><span class="sxs-lookup"><span data-stu-id="38c40-p103">**Received calls**. Total number of calls received by all instances of the Response Group application.</span></span>

  - <span data-ttu-id="38c40-p104">**Успешные звонки**. Общее число звонков, которые были приняты приложением "Группа ответа".</span><span class="sxs-lookup"><span data-stu-id="38c40-p104">**Successful calls**. Total number of calls that were picked up by the Response Group application.</span></span>

  - <span data-ttu-id="38c40-p105">**Предложенные звонки**. Общее число звонков, которые были переведены агенту группы ответа.</span><span class="sxs-lookup"><span data-stu-id="38c40-p105">**Offered calls**. Total number of calls that were transferred to a Response Group agent.</span></span>

  - <span data-ttu-id="38c40-p106">**Отвеченные звонки**. Общее число звонков, на которые ответил агент группы ответа.</span><span class="sxs-lookup"><span data-stu-id="38c40-p106">**Answered calls**. Total number of calls that were actually answered by a Response Group agent.</span></span>

  - <span data-ttu-id="38c40-120">Процент отклоненных звонков.</span><span class="sxs-lookup"><span data-stu-id="38c40-120">Percentage of abandoned calls.</span></span> <span data-ttu-id="38c40-121">Процент звонков, которые были приняты приложением группы ответа, но на которые не ответил агент.</span><span class="sxs-lookup"><span data-stu-id="38c40-121">Percentage of calls that were received by the Response Group application but were never answered by an agent.</span></span> <span data-ttu-id="38c40-122">Это значение вычисляется вычитанием числа отвеченных вызовов из количества принятых вызовов и последующим делением результата на число принятых вызовов.</span><span class="sxs-lookup"><span data-stu-id="38c40-122">This value is calculated by subtracting the Answered calls from the Received calls, and then dividing that value by the number of Received calls.</span></span> <span data-ttu-id="38c40-123">Например, если вы получили 10 вызовов, на 7 из которых был получен ответ, 7 вычитается из 10, что дает 3 неотвеченных вызовов.</span><span class="sxs-lookup"><span data-stu-id="38c40-123">For example, if you received 10 calls and 7 were answered, you would subtract 7 from 10, leaving 3 unanswered calls.</span></span> <span data-ttu-id="38c40-124">Это значение затем делится на 10, что дает процент звонков, оставшихся без ответа, равный 30%.</span><span class="sxs-lookup"><span data-stu-id="38c40-124">That value would then be divided by 10, giving you an abandoned call percentage of 30%.</span></span>

  - <span data-ttu-id="38c40-p108">**Переключенные звонки**. Общее число звонков для приложения «Группа ответа», которые были переведены из-за превышения времени ожидания очереди или переполнения очереди.</span><span class="sxs-lookup"><span data-stu-id="38c40-p108">**Transferred calls**. Total number of Response Group calls that were transferred because of a queue timeout or queue overflow.</span></span>

<div>

## <a name="accessing-the-response-group-call-list-report"></a><span data-ttu-id="38c40-127">Доступ к отчету Response Group Call List (Список звонков группы ответа)</span><span class="sxs-lookup"><span data-stu-id="38c40-127">Accessing the Response Group Call List Report</span></span>

<span data-ttu-id="38c40-128">Чтобы получить доступ к отчету списка обзвона в группе ответа, выберите один из указанных ниже метрик в [отчете использование группы ответов в Lync Server 2013](lync-server-2013-response-group-usage-report.md):</span><span class="sxs-lookup"><span data-stu-id="38c40-128">The Response Group Call List Report can only be accessed by clicking one of the following metrics found on the [Response Group Usage Report in Lync Server 2013](lync-server-2013-response-group-usage-report.md):</span></span>

  - <span data-ttu-id="38c40-129">Полученные звонки</span><span class="sxs-lookup"><span data-stu-id="38c40-129">Received calls</span></span>

  - <span data-ttu-id="38c40-130">Успешные звонки</span><span class="sxs-lookup"><span data-stu-id="38c40-130">Successful calls</span></span>

  - <span data-ttu-id="38c40-131">Предложенные звонки</span><span class="sxs-lookup"><span data-stu-id="38c40-131">Offered calls</span></span>

  - <span data-ttu-id="38c40-132">Отвеченные звонки</span><span class="sxs-lookup"><span data-stu-id="38c40-132">Answered calls</span></span>

  - <span data-ttu-id="38c40-133">Переключенные звонки</span><span class="sxs-lookup"><span data-stu-id="38c40-133">Transferred calls</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-response-group-call-list-report"></a><span data-ttu-id="38c40-134">Рекомендации по использованию отчета Response Group Call List (Список звонков группы ответа)</span><span class="sxs-lookup"><span data-stu-id="38c40-134">Making the Best Use of the Response Group Call List Report</span></span>

<span data-ttu-id="38c40-p109">Отчет Response Group Call List (Список звонков группы ответа) позволяет просмотреть звонки, относящиеся к определенному рабочему процессу группы ответа. Для этого необходимо ввести URI рабочего процесса (SIP-адрес рабочего процесса) в поле Workflow URI (URI рабочего процесса). Разумеется, перед выполнением вышеуказанного действия необходимо отобразить поле Workflow URI (URI рабочего процесса). Чтобы открыть параметры фильтрации данных отчета Response Group Call List (Список звонков группы ответа), нажмите кнопку Show/Hide Parameters (Показать/скрыть параметры) в левом верхнем углу окна отчета.</span><span class="sxs-lookup"><span data-stu-id="38c40-p109">The Response Group Call List Report allows you to limit the displayed data to calls involving a particular Response Group workflow. To do that, you need to enter the workflow URI (the workflow's SIP address) in the Workflow URI box. Before you can do that, however, you must actually be able to see the Workflow URI box. To display the filtering options for the Response Group Call List Report, click the Show/Hide Parameters button in the upper left-hand portion of the report window.</span></span>

<span data-ttu-id="38c40-139">Обратите внимание, что в отчете список звонков группы ответа при наведении указателя мыши на показатели код ответа или ИД диагностики не отображается всплывающая подсказка.</span><span class="sxs-lookup"><span data-stu-id="38c40-139">Note that the Response Group Call List does not display information about either the Response code or the Diagnostic ID if you hold the mouse over either of those metrics.</span></span> <span data-ttu-id="38c40-140">Если вам нужны дополнительные сведения, вы можете заметить код ответа и (или) идентификатор для диагностики, а затем искать эти значения в [отчете об ошибках верхнего уровня в Lync Server 2013](lync-server-2013-top-failures-report.md).</span><span class="sxs-lookup"><span data-stu-id="38c40-140">If you need more information, you might note the Response code and/or Diagnostic ID, and then search for those values in the [Top Failures Report in Lync Server 2013](lync-server-2013-top-failures-report.md).</span></span>

<span data-ttu-id="38c40-141">Чтобы узнать, какие рабочие процессы получили наибольшее число звонков, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="38c40-141">a question like this one: "Which individual workflow received the most calls?", you can do the following:</span></span>

1.  <span data-ttu-id="38c40-p111">В отчете Response Group Usage Report (Использование группы ответа) задайте требуемый период времени и затем щелкните показатель (Число полученных звонков). Откроется отчет Response Group Call List (Список звонков группы ответа).</span><span class="sxs-lookup"><span data-stu-id="38c40-p111">On the Response Group Usage Report, set the desired time period and then click the Received Calls metric. That will open the Response Group Call List Report.</span></span>

2.  <span data-ttu-id="38c40-p112">Экспортируйте данные отчета Response Group Call List (Список звонков группы ответа). Например, можно экспортировать данные в формат Microsoft Excel и затем с помощью Excel преобразовать данные в файл данных с разделителями-запятыми.</span><span class="sxs-lookup"><span data-stu-id="38c40-p112">Export the data shown on the Response Group Call List Report. For example, you might export the data in Microsoft Excel format, and then use Excel to convert that data to a comma-separated values file.</span></span>

3.  <span data-ttu-id="38c40-146">Выполните анализ с помощью Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="38c40-146">Run your analyses using Windows PowerShell.</span></span>

<span data-ttu-id="38c40-147">Например, если вы сохранили данные в файл с названием C:\\список обзвона для\_\_\\\_групповых\_звонков Data List. csv, вы можете использовать следующую команду, чтобы вернуть общее количество полученных звонков для каждого рабочего процесса, указанного в отчете.</span><span class="sxs-lookup"><span data-stu-id="38c40-147">For example, if you have saved the data to a file named C:\\Data\\Response\_Group\_Call\_List\_Report.csv, you can then use the following command to return the total number of received calls for each workflow listed in the report:</span></span>

    $calls = Import-Csv -Path "C:\ Data\Response_Group_Call_List_Report.csv"
    $calls | Group-Object Workflow | Select-Object Count, Name | Sort-Object Count -Descending

<span data-ttu-id="38c40-148">Команда вернет сведения, похожие на следующие:</span><span class="sxs-lookup"><span data-stu-id="38c40-148">That will information similar to this:</span></span>

    Count    Name
    -----    ----
      160    Redmond Help Desk
       47    Dublin Help Desk
       31    North America Customer Support
       16    EMEA Customer Support
       14    Employment Opportunities

</div>

<div>

## <a name="filters"></a><span data-ttu-id="38c40-149">Фильтры</span><span class="sxs-lookup"><span data-stu-id="38c40-149">Filters</span></span>

<span data-ttu-id="38c40-p113">Фильтры позволяют получить более детализированный набор данных или изменить способ просмотра возвращаемых данных. В следующей таблице перечислены фильтры, которые можно использовать в отчете Response Group Call List (Список звонков группы ответа).</span><span class="sxs-lookup"><span data-stu-id="38c40-p113">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the Response Group Call List Report.</span></span>

### <a name="response-group-call-list-report-filters"></a><span data-ttu-id="38c40-152">Фильтры отчета Response Group Call List (Список звонков группы ответа)</span><span class="sxs-lookup"><span data-stu-id="38c40-152">Response Group Call List Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="38c40-153">Имя</span><span class="sxs-lookup"><span data-stu-id="38c40-153">Name</span></span></th>
<th><span data-ttu-id="38c40-154">Описание</span><span class="sxs-lookup"><span data-stu-id="38c40-154">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="38c40-155"><strong>От</strong></span><span class="sxs-lookup"><span data-stu-id="38c40-155"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="38c40-p114">Начальные дата/время для временного диапазона. Чтобы просмотреть данные по часам, введите начальные дату и время следующим образом:</span><span class="sxs-lookup"><span data-stu-id="38c40-p114">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="38c40-158">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="38c40-158">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="38c40-p115">Если вы не вводите начальное время, отчет автоматически начинается с 12:00 AM указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</span><span class="sxs-lookup"><span data-stu-id="38c40-p115">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="38c40-161">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="38c40-161">7/7/2012</span></span></p>
<p><span data-ttu-id="38c40-162">Чтобы просмотреть данные за неделю или месяц, введите дату, выпадающую на любое время в рамках недели или месяца, которые вы хотите просмотреть (вам не требуется вводить первый день недели или месяца):</span><span class="sxs-lookup"><span data-stu-id="38c40-162">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="38c40-163">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="38c40-163">7/3/2012</span></span></p>
<p><span data-ttu-id="38c40-164">Недели всегда отсчитываются с воскресенья по субботу.</span><span class="sxs-lookup"><span data-stu-id="38c40-164">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38c40-165"><strong>До</strong></span><span class="sxs-lookup"><span data-stu-id="38c40-165"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="38c40-p116">Конечные дата/время для временного диапазона. Чтобы просмотреть данные по часам, введите конечные дату и время следующим образом:</span><span class="sxs-lookup"><span data-stu-id="38c40-p116">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="38c40-168">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="38c40-168">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="38c40-p117">Если вы не вводите конечное время, отчет автоматически заканчивается в 12:00 AM указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</span><span class="sxs-lookup"><span data-stu-id="38c40-p117">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="38c40-171">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="38c40-171">7/7/2012</span></span></p>
<p><span data-ttu-id="38c40-172">Чтобы просмотреть данные за неделю или месяц, введите дату, выпадающую на любое время в рамках недели или месяца, которые вы хотите просмотреть (вам не требуется вводить первый день недели или месяца):</span><span class="sxs-lookup"><span data-stu-id="38c40-172">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="38c40-173">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="38c40-173">7/3/2012</span></span></p>
<p><span data-ttu-id="38c40-174">Недели всегда отсчитываются с воскресенья по субботу.</span><span class="sxs-lookup"><span data-stu-id="38c40-174">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38c40-175"><strong>URI рабочего процесса</strong></span><span class="sxs-lookup"><span data-stu-id="38c40-175"><strong>Workflow URI</strong></span></span></p></td>
<td><p><span data-ttu-id="38c40-p118">Позволяет получать данные для указанного рабочего процесса группы ответа. Чтобы использовать этот фильтр, введите SIP-адрес рабочего процесса. Пример:</span><span class="sxs-lookup"><span data-stu-id="38c40-p118">Enables you to limit the returned data to the specified Response Group workflow. To use this filter, enter the Workflow SIP address. For example:</span></span></p>
<p><span data-ttu-id="38c40-179">sip:helpdesk@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="38c40-179">sip:helpdesk@litwareinc.com</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38c40-180"><strong>Звонки</strong></span><span class="sxs-lookup"><span data-stu-id="38c40-180"><strong>Calls</strong></span></span></p></td>
<td><p><span data-ttu-id="38c40-181">Доступны следующие типы звонков:</span><span class="sxs-lookup"><span data-stu-id="38c40-181">You can select one of the following call types:</span></span></p>
<ul>
<li><p><span data-ttu-id="38c40-182">Received Calls (Полученные звонки)</span><span class="sxs-lookup"><span data-stu-id="38c40-182">Received Calls</span></span></p></li>
<li><p><span data-ttu-id="38c40-183">Successful Calls (Успешные звонки)</span><span class="sxs-lookup"><span data-stu-id="38c40-183">Successful Calls</span></span></p></li>
<li><p><span data-ttu-id="38c40-184">Offered Calls (Предложенные звонки)</span><span class="sxs-lookup"><span data-stu-id="38c40-184">Offered Calls</span></span></p></li>
<li><p><span data-ttu-id="38c40-185">Answered Calls (Звонки с ответом)</span><span class="sxs-lookup"><span data-stu-id="38c40-185">Answered Calls</span></span></p></li>
<li><p><span data-ttu-id="38c40-186">Transferred Calls (Переведенные звонки)</span><span class="sxs-lookup"><span data-stu-id="38c40-186">Transferred Calls</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="38c40-187">Показатели</span><span class="sxs-lookup"><span data-stu-id="38c40-187">Metrics</span></span>

<span data-ttu-id="38c40-188">В следующей таблице приведены показатели, доступные в отчете Response Group Call List Report (Список звонков группы ответа) для каждого звонка, полученного приложением "Группа ответа".</span><span class="sxs-lookup"><span data-stu-id="38c40-188">The following table lists the information provided in the Response Group Call List Report for each call received by the Response Group application.</span></span>

### <a name="response-group-call-list-report-metrics"></a><span data-ttu-id="38c40-189">Показатели отчета Response Group Call List (Список звонков группы ответа)</span><span class="sxs-lookup"><span data-stu-id="38c40-189">Response Group Call List Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="38c40-190">Имя</span><span class="sxs-lookup"><span data-stu-id="38c40-190">Name</span></span></th>
<th><span data-ttu-id="38c40-191">Поддержка сортировки</span><span class="sxs-lookup"><span data-stu-id="38c40-191">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="38c40-192">Описание</span><span class="sxs-lookup"><span data-stu-id="38c40-192">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="38c40-193"><strong>Вызывающая сторона</strong></span><span class="sxs-lookup"><span data-stu-id="38c40-193"><strong>Caller</strong></span></span></p></td>
<td><p><span data-ttu-id="38c40-194">Нет</span><span class="sxs-lookup"><span data-stu-id="38c40-194">No</span></span></p></td>
<td><p><span data-ttu-id="38c40-195">SIP-адрес вызывающего.</span><span class="sxs-lookup"><span data-stu-id="38c40-195">SIP address of the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38c40-196"><strong>Workflow</strong></span><span class="sxs-lookup"><span data-stu-id="38c40-196"><strong>Workflow</strong></span></span></p></td>
<td><p><span data-ttu-id="38c40-197">Нет</span><span class="sxs-lookup"><span data-stu-id="38c40-197">No</span></span></p></td>
<td><p><span data-ttu-id="38c40-198">SIP-адрес рабочего процесса "Группа ответа".</span><span class="sxs-lookup"><span data-stu-id="38c40-198">SIP address of the Response Group workflow.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38c40-199"><strong>Время начала</strong></span><span class="sxs-lookup"><span data-stu-id="38c40-199"><strong>Start time</strong></span></span></p></td>
<td><p><span data-ttu-id="38c40-200">Нет</span><span class="sxs-lookup"><span data-stu-id="38c40-200">No</span></span></p></td>
<td><p><span data-ttu-id="38c40-201">Дата и время начала звонка.</span><span class="sxs-lookup"><span data-stu-id="38c40-201">Date and time that the call started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38c40-202"><strong>Время окончания</strong></span><span class="sxs-lookup"><span data-stu-id="38c40-202"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="38c40-203">Нет</span><span class="sxs-lookup"><span data-stu-id="38c40-203">No</span></span></p></td>
<td><p><span data-ttu-id="38c40-204">Дата и время окончания звонка.</span><span class="sxs-lookup"><span data-stu-id="38c40-204">Date and time that the call ended.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38c40-205"><strong>Код ответа</strong></span><span class="sxs-lookup"><span data-stu-id="38c40-205"><strong>Response code</strong></span></span></p></td>
<td><p><span data-ttu-id="38c40-206">Нет</span><span class="sxs-lookup"><span data-stu-id="38c40-206">No</span></span></p></td>
<td><p><span data-ttu-id="38c40-207">Код ответа SIP, отправленный при сбое сеанса.</span><span class="sxs-lookup"><span data-stu-id="38c40-207">SIP response code sent when the session failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38c40-208"><strong>ИД диагностики</strong></span><span class="sxs-lookup"><span data-stu-id="38c40-208"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="38c40-209">Нет</span><span class="sxs-lookup"><span data-stu-id="38c40-209">No</span></span></p></td>
<td><p><span data-ttu-id="38c40-210">Прикрепленный к SIP-сообщению уникальный идентификатор (в форме заголовка ms-diagnostics), который часто содержит информацию, полезную при поиске и устранении ошибок.</span><span class="sxs-lookup"><span data-stu-id="38c40-210">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

