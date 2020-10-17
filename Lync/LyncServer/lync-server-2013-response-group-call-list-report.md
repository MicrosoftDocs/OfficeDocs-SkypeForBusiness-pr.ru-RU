---
title: 'Lync Server 2013: отчет по списку звонков для группы ответа'
description: 'Lync Server 2013: отчет по списку звонков для группы ответа.'
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
ms.openlocfilehash: 5ffe4b62534d4849b4f0cdade9aeef8be5d69178
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560885"
---
# <a name="response-group-call-list-report-in-lync-server-2013"></a><span data-ttu-id="37609-103">Отчет по списку звонков группы ответа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="37609-103">Response Group Call List Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="37609-104">_**Последнее изменение темы:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="37609-104">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="37609-105">Приложение группы ответа позволяет Microsoft Lync Server 2013 отвечать на звонки и направлять их на основе номера телефона, который был набран, и (необязательно) в ответах вызывающего абонента на ряд вопросов.</span><span class="sxs-lookup"><span data-stu-id="37609-105">The Response Group application provides a way for Microsoft Lync Server 2013 to answer and route phone calls based on the number that was dialed and, optionally, on the caller's responses to a series of questions.</span></span> <span data-ttu-id="37609-106">Как правило, звонки групп ответа не направляются отдельному человеку, но вместо этого направляются группе людей, которые называются группами агентов.</span><span class="sxs-lookup"><span data-stu-id="37609-106">Typically, Response Group calls are not routed to an individual person but, instead, are routed to a team of people referred to as an agent group.</span></span> <span data-ttu-id="37609-107">Например, если кто-то звонит по номеру телефона в службу поддержки, Lync Server 2013 может автоматически перенаправлять этот вызов в первый доступный агент службы поддержки.</span><span class="sxs-lookup"><span data-stu-id="37609-107">For example, if someone calls the phone number for your help desk, Lync Server 2013 can automatically route that call to the first available help desk agent.</span></span> <span data-ttu-id="37609-108">Кроме того, Lync Server может задать ряд вопросов ("нажмите 1, если у вас возникнут проблемы с оборудованием.</span><span class="sxs-lookup"><span data-stu-id="37609-108">Alternatively, Lync Server could ask a series of questions ("Press 1 if you are having hardware problems.</span></span> <span data-ttu-id="37609-109">Если у вас возникли проблемы с программным обеспечением, нажмите 2.</span><span class="sxs-lookup"><span data-stu-id="37609-109">Press 2 if you are having software problems.</span></span> <span data-ttu-id="37609-110">Если у вас возникли проблемы с сетью, нажмите 3. " а затем направлять вызов в наиболее подходящий агент службы поддержки на основе ответа на эти вопросы.</span><span class="sxs-lookup"><span data-stu-id="37609-110">Press 3 if you are having network problems.") and then route the call to the most appropriate help desk agent based on the answer to those questions.</span></span>

<span data-ttu-id="37609-p102">Отчет Response Group Call List (Список звонков группы ответа) предоставляет список звонков, совершенных за указанный период времени, а также сведения о типах звонков. Отчет Response Group Usage (Использование группы ответа), который необходимо открывать до открытия отчета Response Group Call List (Список звонков группы ответа), содержит следующие типы звонков:</span><span class="sxs-lookup"><span data-stu-id="37609-p102">The Response Group Call List Report represents a collection of calls made for a specified period of time and for a specified type of call. The Response Group Usage Report (which must be opened first before you can open the Response Group Call List Report) recognizes the following call types:</span></span>

  - <span data-ttu-id="37609-p103">**Received calls** (Число полученных звонков). Общее число звонков, полученных всеми экземплярами приложения "Группа ответа".</span><span class="sxs-lookup"><span data-stu-id="37609-p103">**Received calls**. Total number of calls received by all instances of the Response Group application.</span></span>

  - <span data-ttu-id="37609-115">**Успешные звонки**.</span><span class="sxs-lookup"><span data-stu-id="37609-115">**Successful calls**.</span></span> <span data-ttu-id="37609-116">Общее количество звонков, которые были выбраны приложением группы ответа.</span><span class="sxs-lookup"><span data-stu-id="37609-116">Total number of calls that were picked up by the Response Group application.</span></span>

  - <span data-ttu-id="37609-p105">**Предложенные звонки**. Общее количество звонков, переданных агенту группы ответа.</span><span class="sxs-lookup"><span data-stu-id="37609-p105">**Offered calls**. Total number of calls that were transferred to a Response Group agent.</span></span>

  - <span data-ttu-id="37609-p106">**Отвеченные звонки**. Общее количество звонков, на которые фактически ответил агент группы ответа.</span><span class="sxs-lookup"><span data-stu-id="37609-p106">**Answered calls**. Total number of calls that were actually answered by a Response Group agent.</span></span>

  - <span data-ttu-id="37609-121">Процент отклоненных звонков.</span><span class="sxs-lookup"><span data-stu-id="37609-121">Percentage of abandoned calls.</span></span> <span data-ttu-id="37609-122">Процент звонков, которые были приняты приложением группы ответа, но на которые не ответил агент.</span><span class="sxs-lookup"><span data-stu-id="37609-122">Percentage of calls that were received by the Response Group application but were never answered by an agent.</span></span> <span data-ttu-id="37609-123">Это значение вычисляется вычитанием числа отвеченных вызовов из количества принятых вызовов и последующим делением результата на число принятых вызовов.</span><span class="sxs-lookup"><span data-stu-id="37609-123">This value is calculated by subtracting the Answered calls from the Received calls, and then dividing that value by the number of Received calls.</span></span> <span data-ttu-id="37609-124">Например, если вы получили 10 вызовов, на 7 из которых был получен ответ, 7 вычитается из 10, что дает 3 неотвеченных вызовов.</span><span class="sxs-lookup"><span data-stu-id="37609-124">For example, if you received 10 calls and 7 were answered, you would subtract 7 from 10, leaving 3 unanswered calls.</span></span> <span data-ttu-id="37609-125">Это значение затем делится на 10, что дает процент звонков, оставшихся без ответа, равный 30%.</span><span class="sxs-lookup"><span data-stu-id="37609-125">That value would then be divided by 10, giving you an abandoned call percentage of 30%.</span></span>

  - <span data-ttu-id="37609-p108">**Transferred calls** (Число переведенных звонков). Общее число звонков для приложения "Группа ответа", которые были переведены из-за превышения времени ожидания очереди или переполнения очереди.</span><span class="sxs-lookup"><span data-stu-id="37609-p108">**Transferred calls**. Total number of Response Group calls that were transferred because of a queue timeout or queue overflow.</span></span>

<div>

## <a name="accessing-the-response-group-call-list-report"></a><span data-ttu-id="37609-128">Доступ к отчету Response Group Call List (Список звонков группы ответа)</span><span class="sxs-lookup"><span data-stu-id="37609-128">Accessing the Response Group Call List Report</span></span>

<span data-ttu-id="37609-129">Чтобы получить доступ к отчету о списке звонков группы ответа, щелкните одну из указанных ниже метрик в [отчете об использовании группы ответа в Lync Server 2013](lync-server-2013-response-group-usage-report.md):</span><span class="sxs-lookup"><span data-stu-id="37609-129">The Response Group Call List Report can only be accessed by clicking one of the following metrics found on the [Response Group Usage Report in Lync Server 2013](lync-server-2013-response-group-usage-report.md):</span></span>

  - <span data-ttu-id="37609-130">Принятые вызовы</span><span class="sxs-lookup"><span data-stu-id="37609-130">Received calls</span></span>

  - <span data-ttu-id="37609-131">Успешные вызовы</span><span class="sxs-lookup"><span data-stu-id="37609-131">Successful calls</span></span>

  - <span data-ttu-id="37609-132">Предложенные вызовы</span><span class="sxs-lookup"><span data-stu-id="37609-132">Offered calls</span></span>

  - <span data-ttu-id="37609-133">Отвеченные вызовы</span><span class="sxs-lookup"><span data-stu-id="37609-133">Answered calls</span></span>

  - <span data-ttu-id="37609-134">Transferred calls (Число переведенных звонков)</span><span class="sxs-lookup"><span data-stu-id="37609-134">Transferred calls</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-response-group-call-list-report"></a><span data-ttu-id="37609-135">Рекомендации по использованию отчета Response Group Call List (Список звонков группы ответа)</span><span class="sxs-lookup"><span data-stu-id="37609-135">Making the Best Use of the Response Group Call List Report</span></span>

<span data-ttu-id="37609-p109">Отчет Response Group Call List (Список звонков группы ответа) позволяет просмотреть звонки, относящиеся к определенному рабочему процессу группы ответа. Для этого необходимо ввести URI рабочего процесса (SIP-адрес рабочего процесса) в поле Workflow URI (URI рабочего процесса). Разумеется, перед выполнением вышеуказанного действия необходимо отобразить поле Workflow URI (URI рабочего процесса). Чтобы открыть параметры фильтрации данных отчета Response Group Call List (Список звонков группы ответа), нажмите кнопку Show/Hide Parameters (Показать/скрыть параметры) в левом верхнем углу окна отчета.</span><span class="sxs-lookup"><span data-stu-id="37609-p109">The Response Group Call List Report allows you to limit the displayed data to calls involving a particular Response Group workflow. To do that, you need to enter the workflow URI (the workflow's SIP address) in the Workflow URI box. Before you can do that, however, you must actually be able to see the Workflow URI box. To display the filtering options for the Response Group Call List Report, click the Show/Hide Parameters button in the upper left-hand portion of the report window.</span></span>

<span data-ttu-id="37609-140">Обратите внимание, что в отчете Response Group Call List (Список звонков группы ответа) при наведении указателя мыши на показатели Response code (Код ответа) или Diagnostic ID (ИД диагностики) не отображается всплывающая подсказка.</span><span class="sxs-lookup"><span data-stu-id="37609-140">Note that the Response Group Call List does not display information about either the Response code or the Diagnostic ID if you hold the mouse over either of those metrics.</span></span> <span data-ttu-id="37609-141">Если вам нужны дополнительные сведения, вы можете отметить код ответа и/или идентификатор диагностики, а затем выполнить поиск этих значений в [отчете о самых сбоях в Lync Server 2013](lync-server-2013-top-failures-report.md).</span><span class="sxs-lookup"><span data-stu-id="37609-141">If you need more information, you might note the Response code and/or Diagnostic ID, and then search for those values in the [Top Failures Report in Lync Server 2013](lync-server-2013-top-failures-report.md).</span></span>

<span data-ttu-id="37609-142">Чтобы узнать, какие рабочие процессы получили наибольшее число звонков, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="37609-142">a question like this one: "Which individual workflow received the most calls?", you can do the following:</span></span>

1.  <span data-ttu-id="37609-p111">В отчете Response Group Usage Report (Использование группы ответа) задайте требуемый период времени и затем щелкните показатель (Число полученных звонков). Откроется отчет Response Group Call List (Список звонков группы ответа).</span><span class="sxs-lookup"><span data-stu-id="37609-p111">On the Response Group Usage Report, set the desired time period and then click the Received Calls metric. That will open the Response Group Call List Report.</span></span>

2.  <span data-ttu-id="37609-p112">Экспортируйте данные отчета Response Group Call List (Список звонков группы ответа). Например, можно экспортировать данные в формат Microsoft Excel и затем с помощью Excel преобразовать данные в файл данных с разделителями-запятыми.</span><span class="sxs-lookup"><span data-stu-id="37609-p112">Export the data shown on the Response Group Call List Report. For example, you might export the data in Microsoft Excel format, and then use Excel to convert that data to a comma-separated values file.</span></span>

3.  <span data-ttu-id="37609-147">Выполните анализ с помощью Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="37609-147">Run your analyses using Windows PowerShell.</span></span>

<span data-ttu-id="37609-148">Например, если вы сохранили данные в файл с именем C: \\ \\ List Call of Response \_ Group \_ \_ \_Report.csv, вы можете использовать следующую команду, чтобы возвратить общее число полученных вызовов для каждого рабочего процесса, указанного в отчете:</span><span class="sxs-lookup"><span data-stu-id="37609-148">For example, if you have saved the data to a file named C:\\Data\\Response\_Group\_Call\_List\_Report.csv, you can then use the following command to return the total number of received calls for each workflow listed in the report:</span></span>

    $calls = Import-Csv -Path "C:\ Data\Response_Group_Call_List_Report.csv"
    $calls | Group-Object Workflow | Select-Object Count, Name | Sort-Object Count -Descending

<span data-ttu-id="37609-149">Команда вернет сведения, похожие на следующие:</span><span class="sxs-lookup"><span data-stu-id="37609-149">That will information similar to this:</span></span>

    Count    Name
    -----    ----
      160    Redmond Help Desk
       47    Dublin Help Desk
       31    North America Customer Support
       16    EMEA Customer Support
       14    Employment Opportunities

</div>

<div>

## <a name="filters"></a><span data-ttu-id="37609-150">Фильтры</span><span class="sxs-lookup"><span data-stu-id="37609-150">Filters</span></span>

<span data-ttu-id="37609-p113">Фильтры позволяют получить более детализированный набор данных или изменить способ просмотра возвращаемых данных. В следующей таблице перечислены фильтры, которые можно использовать в отчете Response Group Call List (Список звонков группы ответа).</span><span class="sxs-lookup"><span data-stu-id="37609-p113">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the Response Group Call List Report.</span></span>

### <a name="response-group-call-list-report-filters"></a><span data-ttu-id="37609-153">Фильтры отчета Response Group Call List (Список звонков группы ответа)</span><span class="sxs-lookup"><span data-stu-id="37609-153">Response Group Call List Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="37609-154">Имя</span><span class="sxs-lookup"><span data-stu-id="37609-154">Name</span></span></th>
<th><span data-ttu-id="37609-155">Описание</span><span class="sxs-lookup"><span data-stu-id="37609-155">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="37609-156"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="37609-156"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="37609-p114">Дата и время начала диапазона. Чтобы просмотреть данные по часам, введите дату и время начала в следующем формате:</span><span class="sxs-lookup"><span data-stu-id="37609-p114">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="37609-159">7/7/2012 13:00.</span><span class="sxs-lookup"><span data-stu-id="37609-159">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="37609-p115">Если не указать время начала, автоматически будет выбрано время 00:00 указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</span><span class="sxs-lookup"><span data-stu-id="37609-p115">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="37609-162">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="37609-162">7/7/2012</span></span></p>
<p><span data-ttu-id="37609-163">Для просмотра по неделям или по месяцам введите дату, выпадающую на любой день недели или месяца, который вы хотите просмотреть (это необязательно должен быть первый день недели или месяца):</span><span class="sxs-lookup"><span data-stu-id="37609-163">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="37609-164">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="37609-164">7/3/2012</span></span></p>
<p><span data-ttu-id="37609-165">Неделя всегда начинается с воскресения и заканчивается субботой.</span><span class="sxs-lookup"><span data-stu-id="37609-165">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37609-166"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="37609-166"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="37609-p116">Дата и время окончания диапазона. Чтобы просмотреть данные по часам, введите дату и время окончания в следующем формате:</span><span class="sxs-lookup"><span data-stu-id="37609-p116">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="37609-169">7/7/2012 13:00.</span><span class="sxs-lookup"><span data-stu-id="37609-169">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="37609-p117">Если не указать время окончания, автоматически будет выбрано время 00:00 указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</span><span class="sxs-lookup"><span data-stu-id="37609-p117">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="37609-172">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="37609-172">7/7/2012</span></span></p>
<p><span data-ttu-id="37609-173">Для просмотра по неделям или по месяцам введите дату, выпадающую на любой день недели или месяца, который вы хотите просмотреть (это необязательно должен быть первый день недели или месяца):</span><span class="sxs-lookup"><span data-stu-id="37609-173">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="37609-174">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="37609-174">7/3/2012</span></span></p>
<p><span data-ttu-id="37609-175">Первым днем недели считается воскресенье, а последним — суббота.</span><span class="sxs-lookup"><span data-stu-id="37609-175">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37609-176"><strong>Workflow URI</strong> (URI рабочего процесса)</span><span class="sxs-lookup"><span data-stu-id="37609-176"><strong>Workflow URI</strong></span></span></p></td>
<td><p><span data-ttu-id="37609-p118">Позволяет ограничивать возвращаемые данные до указанного рабочего процесса группы ответа. Чтобы использовать этот фильтр, введите SIP-адрес рабочего процесса. Например:</span><span class="sxs-lookup"><span data-stu-id="37609-p118">Enables you to limit the returned data to the specified Response Group workflow. To use this filter, enter the Workflow SIP address. For example:</span></span></p>
<p><span data-ttu-id="37609-180">sip:helpdesk@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="37609-180">sip:helpdesk@litwareinc.com</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37609-181"><strong>Звонки</strong></span><span class="sxs-lookup"><span data-stu-id="37609-181"><strong>Calls</strong></span></span></p></td>
<td><p><span data-ttu-id="37609-182">Доступны следующие типы звонков:</span><span class="sxs-lookup"><span data-stu-id="37609-182">You can select one of the following call types:</span></span></p>
<ul>
<li><p><span data-ttu-id="37609-183">Received Calls (Полученные звонки)</span><span class="sxs-lookup"><span data-stu-id="37609-183">Received Calls</span></span></p></li>
<li><p><span data-ttu-id="37609-184">Successful Calls (Успешные звонки)</span><span class="sxs-lookup"><span data-stu-id="37609-184">Successful Calls</span></span></p></li>
<li><p><span data-ttu-id="37609-185">Offered Calls (Предложенные звонки)</span><span class="sxs-lookup"><span data-stu-id="37609-185">Offered Calls</span></span></p></li>
<li><p><span data-ttu-id="37609-186">Answered Calls (Звонки с ответом)</span><span class="sxs-lookup"><span data-stu-id="37609-186">Answered Calls</span></span></p></li>
<li><p><span data-ttu-id="37609-187">Transferred Calls (Переведенные звонки)</span><span class="sxs-lookup"><span data-stu-id="37609-187">Transferred Calls</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="37609-188">Метрики</span><span class="sxs-lookup"><span data-stu-id="37609-188">Metrics</span></span>

<span data-ttu-id="37609-189">В следующей таблице приведены показатели, доступные в отчете Response Group Call List Report (Список звонков группы ответа) для каждого звонка, полученного приложением "Группа ответа".</span><span class="sxs-lookup"><span data-stu-id="37609-189">The following table lists the information provided in the Response Group Call List Report for each call received by the Response Group application.</span></span>

### <a name="response-group-call-list-report-metrics"></a><span data-ttu-id="37609-190">Показатели отчета Response Group Call List (Список звонков группы ответа)</span><span class="sxs-lookup"><span data-stu-id="37609-190">Response Group Call List Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="37609-191">Имя</span><span class="sxs-lookup"><span data-stu-id="37609-191">Name</span></span></th>
<th><span data-ttu-id="37609-192">Возможность сортировки по этому показателю</span><span class="sxs-lookup"><span data-stu-id="37609-192">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="37609-193">Описание</span><span class="sxs-lookup"><span data-stu-id="37609-193">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="37609-194"><strong>Caller</strong></span><span class="sxs-lookup"><span data-stu-id="37609-194"><strong>Caller</strong></span></span></p></td>
<td><p><span data-ttu-id="37609-195">Нет</span><span class="sxs-lookup"><span data-stu-id="37609-195">No</span></span></p></td>
<td><p><span data-ttu-id="37609-196">SIP-адрес вызывающего.</span><span class="sxs-lookup"><span data-stu-id="37609-196">SIP address of the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37609-197"><strong>Рабочий процесс</strong></span><span class="sxs-lookup"><span data-stu-id="37609-197"><strong>Workflow</strong></span></span></p></td>
<td><p><span data-ttu-id="37609-198">Нет</span><span class="sxs-lookup"><span data-stu-id="37609-198">No</span></span></p></td>
<td><p><span data-ttu-id="37609-199">SIP-адрес рабочего процесса "Группа ответа".</span><span class="sxs-lookup"><span data-stu-id="37609-199">SIP address of the Response Group workflow.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37609-200"><strong>Start time</strong></span><span class="sxs-lookup"><span data-stu-id="37609-200"><strong>Start time</strong></span></span></p></td>
<td><p><span data-ttu-id="37609-201">Нет</span><span class="sxs-lookup"><span data-stu-id="37609-201">No</span></span></p></td>
<td><p><span data-ttu-id="37609-202">Дата и время начала звонка.</span><span class="sxs-lookup"><span data-stu-id="37609-202">Date and time that the call started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37609-203"><strong>End time</strong></span><span class="sxs-lookup"><span data-stu-id="37609-203"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="37609-204">Нет</span><span class="sxs-lookup"><span data-stu-id="37609-204">No</span></span></p></td>
<td><p><span data-ttu-id="37609-205">Дата и время окончания звонка.</span><span class="sxs-lookup"><span data-stu-id="37609-205">Date and time that the call ended.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37609-206"><strong>Response code</strong></span><span class="sxs-lookup"><span data-stu-id="37609-206"><strong>Response code</strong></span></span></p></td>
<td><p><span data-ttu-id="37609-207">Нет</span><span class="sxs-lookup"><span data-stu-id="37609-207">No</span></span></p></td>
<td><p><span data-ttu-id="37609-208">Код ответа SIP, отправленный при сбое сеанса.</span><span class="sxs-lookup"><span data-stu-id="37609-208">SIP response code sent when the session failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37609-209"><strong>Diagnostic ID</strong></span><span class="sxs-lookup"><span data-stu-id="37609-209"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="37609-210">Нет</span><span class="sxs-lookup"><span data-stu-id="37609-210">No</span></span></p></td>
<td><p><span data-ttu-id="37609-211">Уникальный идентификатор (в виде заголовка ms-diagnostics), добавленный к сообщению SIP, который предоставляет полезные сведения для устранения ошибок.</span><span class="sxs-lookup"><span data-stu-id="37609-211">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

