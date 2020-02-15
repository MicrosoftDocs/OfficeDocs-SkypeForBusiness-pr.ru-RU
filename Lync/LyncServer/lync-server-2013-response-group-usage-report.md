---
title: 'Lync Server 2013: отчет об использовании группы ответа'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Response Group Usage Report
ms:assetid: 3248b320-a552-400a-8485-6891af4eb0f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558632(v=OCS.15)
ms:contentKeyID: 48183811
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2f0d00c24fc0b087162330fa713017782b550d16
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044121"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="response-group-usage-report-in-lync-server-2013"></a><span data-ttu-id="995aa-102">Отчет об использовании группы ответа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="995aa-102">Response Group Usage Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="995aa-103">_**Последнее изменение темы:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="995aa-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="995aa-104">Приложение группы ответа позволяет Microsoft Lync Server 2013 отвечать на звонки и направлять их на основе номера телефона, который был набран, и (необязательно) в ответах вызывающего абонента на ряд вопросов.</span><span class="sxs-lookup"><span data-stu-id="995aa-104">The Response Group application provides a way for Microsoft Lync Server 2013 to answer and route phone calls based on the number that was dialed and, optionally, on the caller's responses to a series of questions.</span></span> <span data-ttu-id="995aa-105">Как правило, звонки групп ответа не направляются отдельному человеку, но вместо этого направляются группе людей, которые называются группами агентов.</span><span class="sxs-lookup"><span data-stu-id="995aa-105">Typically, Response Group calls are not routed to an individual person but, instead, are routed to a team of people referred to as an agent group.</span></span> <span data-ttu-id="995aa-106">Например, если кто-то звонит по номеру телефона в службу поддержки, Lync Server 2013 может автоматически перенаправлять этот вызов в первый доступный агент службы поддержки.</span><span class="sxs-lookup"><span data-stu-id="995aa-106">For example, if someone calls the phone number for your help desk, Lync Server 2013 can automatically route that call to the first available help desk agent.</span></span> <span data-ttu-id="995aa-107">Кроме того, Lync Server может задать ряд вопросов ("нажмите 1, если у вас возникнут проблемы с оборудованием.</span><span class="sxs-lookup"><span data-stu-id="995aa-107">Alternatively, Lync Server could ask a series of questions ("Press 1 if you are having hardware problems.</span></span> <span data-ttu-id="995aa-108">Если у вас возникли проблемы с программным обеспечением, нажмите 2.</span><span class="sxs-lookup"><span data-stu-id="995aa-108">Press 2 if you are having software problems.</span></span> <span data-ttu-id="995aa-109">Если у вас возникли проблемы с сетью, нажмите 3. " а затем направлять вызов в наиболее подходящий агент службы поддержки на основе ответа на эти вопросы.</span><span class="sxs-lookup"><span data-stu-id="995aa-109">Press 3 if you are having network problems.") and then route the call to the most appropriate help desk agent based on the answer to those questions.</span></span>

<span data-ttu-id="995aa-110">В отчете об использовании группы ответа приводится подробная информация о числе телефонных звонков, принятых всеми вашими рабочими процессами группы ответ, далее эти звонки разбиваются на более точные категории, такие как предложенные вызовы, принятые вызовы и оставшиеся без ответа вызовы.</span><span class="sxs-lookup"><span data-stu-id="995aa-110">The Response Group Usage Report provides a detailed look at the number of phone calls received by all your Response Group workflows, then breaks those calls down into more finite categories such as Offered calls, Answered calls, and Abandoned calls.</span></span>

<span data-ttu-id="995aa-111">При работе с отчетом об использовании группы ответа важно понять разницу между типами вызовов.</span><span class="sxs-lookup"><span data-stu-id="995aa-111">The key to working with the Response Group Usage Report is to understand the difference between the reported call types:</span></span>

  - <span data-ttu-id="995aa-p102">**Полученные звонки**. Общее количество звонков, полученных всеми экземплярами приложения группы ответа.</span><span class="sxs-lookup"><span data-stu-id="995aa-p102">**Received calls**. Total number of calls received by all instances of the Response Group application.</span></span>

  - <span data-ttu-id="995aa-114">**Успешные звонки**.</span><span class="sxs-lookup"><span data-stu-id="995aa-114">**Successful calls**.</span></span> <span data-ttu-id="995aa-115">Общее количество звонков, которые были выбраны приложением группы ответа.</span><span class="sxs-lookup"><span data-stu-id="995aa-115">Total number of calls that were picked up by the Response Group application.</span></span>

  - <span data-ttu-id="995aa-p104">**Предложенные звонки**. Общее количество звонков, переданных агенту группы ответа.</span><span class="sxs-lookup"><span data-stu-id="995aa-p104">**Offered calls**. Total number of calls that were transferred to a Response Group agent.</span></span>

  - <span data-ttu-id="995aa-p105">**Отвеченные звонки**. Общее количество звонков, на которые фактически ответил агент группы ответа.</span><span class="sxs-lookup"><span data-stu-id="995aa-p105">**Answered calls**. Total number of calls that were actually answered by a Response Group agent.</span></span>

  - <span data-ttu-id="995aa-p106">**Процент отклоненных звонков**. Процент звонков, которые были приняты приложением группы ответа, но на которые не ответил агент. Это значение вычисляется вычитанием числа отвеченных вызовов из количества принятых вызовов и последующим делением результата на число принятых вызовов. Например, если вы получили 10 вызовов, на 7 из которых был получен ответ, 7 вычитается из 10, что дает 3 неотвеченных вызовов. Это значение затем делится на 10, что дает процент звонков, оставшихся без ответа, равный 30%.</span><span class="sxs-lookup"><span data-stu-id="995aa-p106">**Percentage of abandoned calls**. Percentage of calls that were received by the Response Group application but were never answered by an agent. This value is calculated by subtracting the Answered calls from the Received calls, and then dividing that value by the number of Received calls. For example, if you received 10 calls and 7 were answered, you would subtract 7 from 10, leaving 3 unanswered calls. That value would then be divided by 10, giving you an abandoned call percentage of 30%.</span></span>

  - <span data-ttu-id="995aa-p107">**Переадресованные вызовы**. Общее количество звонков, которые были переадресованы группой ответа из-за истечения времени ожидания или переполнение очереди очереди.</span><span class="sxs-lookup"><span data-stu-id="995aa-p107">**Transferred calls**. Total number of Response Group calls that were transferred because of a queue timeout or queue overflow.</span></span>

<span data-ttu-id="995aa-p108">Если вы изучаете отчет об использовании группы ответа и не можете вспомнить определение любого из этих типов вызовов, просто наведите указатель мыши на метку соответствующего типа звонка. Появится всплывающая подсказка с кратким описанием типа вызова.</span><span class="sxs-lookup"><span data-stu-id="995aa-p108">If you are looking at the Response Group Usage Report and can't remember the definition for any of these call types, simply hold your mouse over the appropriate call type label. A tooltip will appear that offers a brief description of the call type.</span></span>

<span data-ttu-id="995aa-p109">Отчет об использовании группы ответа позволяет отфильтровать данные по URI рабочего процесса (SIP-адресу, связанным с этим рабочим процессом). Однако на самом деле URI рабочих процессов не отображаются в самом отчете. Если вы хотите узнать, например, какие рабочие процессы отвечают на наибольшее число звонков или в каких рабочих процессах больше всего переадресованных вызовов, щелкните соответствующий показатель, чтобы открыть отчета по спискам вызовов группы ответа за данный период времени. В этом отчете перечислены URI рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="995aa-p109">The Response Group Usage Report allows you to filter on a workflow URI (the SIP address associated with that workflow). However, workflow URIs do not actually appear on the report itself. If you would like to know things such as which workflows are answering the most calls or which workflows are experiencing the most transferred calls, click the appropriate metric to open the Response Group Call List Report for that given time period. That reports does list the workflow URIs.</span></span>

<div>

## <a name="accessing-the-response-group-usage-report"></a><span data-ttu-id="995aa-133">Доступ к отчету об использовании группы ответа</span><span class="sxs-lookup"><span data-stu-id="995aa-133">Accessing the Response Group Usage Report</span></span>

<span data-ttu-id="995aa-134">Отчет об использовании группы ответа можно открыть на домашней странице отчетов мониторинга.</span><span class="sxs-lookup"><span data-stu-id="995aa-134">The Response Group Usage Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="995aa-135">Вы можете перейти к [отчету списка звонков группы ответа в Lync Server 2013](lync-server-2013-response-group-call-list-report.md) , щелкнув один из следующих показателей:</span><span class="sxs-lookup"><span data-stu-id="995aa-135">You can drill down to the [Response Group Call List Report in Lync Server 2013](lync-server-2013-response-group-call-list-report.md) by clicking any of the following metrics:</span></span>

  - <span data-ttu-id="995aa-136">Received calls (Число полученных звонков)</span><span class="sxs-lookup"><span data-stu-id="995aa-136">Received calls</span></span>

  - <span data-ttu-id="995aa-137">Successful calls (Число успешных звонков)</span><span class="sxs-lookup"><span data-stu-id="995aa-137">Successful calls</span></span>

  - <span data-ttu-id="995aa-138">Offered calls (Число предложенных звонков)</span><span class="sxs-lookup"><span data-stu-id="995aa-138">Offered calls</span></span>

  - <span data-ttu-id="995aa-139">Answered calls (Число звонков с ответом)</span><span class="sxs-lookup"><span data-stu-id="995aa-139">Answered calls</span></span>

  - <span data-ttu-id="995aa-140">Transferred calls (Число переведенных звонков)</span><span class="sxs-lookup"><span data-stu-id="995aa-140">Transferred calls</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-response-group-usage-report"></a><span data-ttu-id="995aa-141">Оптимальное применение отчета об использовании группы ответа</span><span class="sxs-lookup"><span data-stu-id="995aa-141">Making the Best Use of the Response Group Usage Report</span></span>

<span data-ttu-id="995aa-142">Одно из наиболее интересных применений отчета об использовании группы ответа не так очевидно — это возможность получать информацию об использовании для одного рабочего процесса группы ответа.</span><span class="sxs-lookup"><span data-stu-id="995aa-142">One of the more interesting uses of the Response Group Usage Report might not be readily apparent: the ability to retrieve usage information for a single Response Group workflow.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="995aa-143">Рабочий процесс группы ответа — это, по сути, набор инструкций, определяющих, что делает Lync Server, когда пользователь набирает определенный номер телефона.</span><span class="sxs-lookup"><span data-stu-id="995aa-143">A Response Group workflow is basically a set of instructions that determines what Lync Server does when a user dials a particular phone number.</span></span> <span data-ttu-id="995aa-144">В связи с этим этот рабочий процесс уникально связан с номером телефона.</span><span class="sxs-lookup"><span data-stu-id="995aa-144">To that end, each workflow is uniquely associated with a phone number.</span></span> <span data-ttu-id="995aa-145">Когда кто-то звонит по этому номеру, рабочий процесс определяет, как его можно обработать.</span><span class="sxs-lookup"><span data-stu-id="995aa-145">When someone calls that number, the workflow determines how the call will be handled.</span></span> <span data-ttu-id="995aa-146">Например, рабочий процесс может вызвать переадресацию вызова на ряд вопросов IVR, с помощью которых система просит вызывающего абонента ввести дополнительную информацию ("Нажмите 1 для получения поддержки по оборудованию.</span><span class="sxs-lookup"><span data-stu-id="995aa-146">For example, the workflow might cause the call to be routed to a series of interactive voice response (IVR) questions that prompt the caller to enter additional information ("Press 1 for hardware support.</span></span> <span data-ttu-id="995aa-147">Нажмите 2 для получения поддержки по программному обеспечению").</span><span class="sxs-lookup"><span data-stu-id="995aa-147">Press 2 for software support.").</span></span> <span data-ttu-id="995aa-148">Или же рабочий процесс может поместить звонок в очередь и поместить вызывающего на удержание, пока не освободится оператор для ответа на вызов.</span><span class="sxs-lookup"><span data-stu-id="995aa-148">Alternatively, the workflow might cause the call to be placed in a queue , with the caller put on hold until an agent is available to answer the call.</span></span> <span data-ttu-id="995aa-149">Доступность агентов также определяется рабочим процессов: они используются для настройки рабочего времени (дней недели и времени суток, в течение которых агенты доступны для ответа на звонки) и выходных (дней, когда агенты недоступны для ответа на звонки).</span><span class="sxs-lookup"><span data-stu-id="995aa-149">The availability of agents to answer calls is also dictated by the workflow: workflows are used to configure both business hours (the days of the week and the times of day when agents are available to answer calls) and holidays (days when no agents are available to answer calls).</span></span> <span data-ttu-id="995aa-150">Каждый раз, когда вы набираете номер, соответствующий приложению группы ответа, вы вызываете рабочий процесс группы ответа.</span><span class="sxs-lookup"><span data-stu-id="995aa-150">Any time you dial a phone number that belongs to the Response Group application you are essentially calling a Response Group workflow.</span></span>



</div>

<span data-ttu-id="995aa-p112">Хотя URI рабочих процессов не отображаются в отчете об использовании группы ответа, вы все равно можете просмотреть статистику использования отдельного рабочего процесса, что зачастую является крайне полезным. Предположим, что вы недавно представили новую рекламную кампанию и хотите узнать, звонят ли люди, чтобы спросить о соответствующем продукте. Если вы связали рабочий процесс группы ответа с номером телефона, указанным в рекламной кампании, вы легко можете узнать, сколько людей звонят по этому номеру.</span><span class="sxs-lookup"><span data-stu-id="995aa-p112">Although workflow URIs do not appear in the Response Group Usage Report, it's still possible to view the usage statistics for a single workflow, something that is often extremely useful. For example, suppose you recently unveiled a new ad campaign and are curious to know whether people are calling in to ask about that product. If you have associated a Response Group workflow with the phone number given in the ad campaign, you can easily check to see how many people (if any) are calling that number.</span></span>

<span data-ttu-id="995aa-154">Также вы можете использовать аналогичный подход, чтобы оценить количество вызовов, которые обрабатываются внутренней службой поддержки или отделом обслуживания клиентов.</span><span class="sxs-lookup"><span data-stu-id="995aa-154">You might also use a similar approach to gauge the number of calls being handled by your internal help desk or your customer service department.</span></span>

<span data-ttu-id="995aa-155">Чтобы просмотреть статистику использования определенного рабочего процесса, введите URI рабочего процесса в поле "URI рабочего процесса".</span><span class="sxs-lookup"><span data-stu-id="995aa-155">To review usage statistics for a particular workflow, enter the workflow URI in the Workflow URI box.</span></span> <span data-ttu-id="995aa-156">Конечно, как уже отмечалось, URI рабочих процессов (SIP-адреса, связанные с рабочими процессами) не отображаются в отчете.</span><span class="sxs-lookup"><span data-stu-id="995aa-156">Of course, as noted, workflow URIs (the SIP address associated with a workflow) do not appear on the report.</span></span> <span data-ttu-id="995aa-157">Это означает, что вы должны найти другой способ определить URI рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="995aa-157">That means you need to find some other way to determine the URI of a workflow.</span></span> <span data-ttu-id="995aa-158">Один из способов сделать это — использовать Windows PowerShell и командную консоль Lync Server.</span><span class="sxs-lookup"><span data-stu-id="995aa-158">One way to do this is to use Windows PowerShell and the Lync Server Management Shell.</span></span> <span data-ttu-id="995aa-159">Например, следующая команда возвращает URI для всех процессов группы ответа:</span><span class="sxs-lookup"><span data-stu-id="995aa-159">For example, this command returns the URIs for all your Response Group workflows:</span></span>

    Get-CsRgsWorkflow | Select-Object Name, PrimaryUri

<span data-ttu-id="995aa-160">Команда возвращает следующие или аналогичные данные:</span><span class="sxs-lookup"><span data-stu-id="995aa-160">That will return data similar to this:</span></span>

    Name                            PrimaryUri
    ----                            ----------
    Customer Support                sip:support@litwareinc.com
    Help Desk                       sip:helpdesk@litwareinc.com
    New Ad Campaign                 sip:newads@litwareinc.com

<span data-ttu-id="995aa-161">Эта команда возвращает сведения для одного рабочего процесса с именем New Ad Campaign:</span><span class="sxs-lookup"><span data-stu-id="995aa-161">This command returns information for a single workflow, the one with the name New Ad Campaign:</span></span>

    Get-CsRgsWorkflow -Name "New Ad Campaign" | Select-Object Name, PrimaryUri

</div>

<div>

## <a name="filters"></a><span data-ttu-id="995aa-162">Фильтры</span><span class="sxs-lookup"><span data-stu-id="995aa-162">Filters</span></span>

<span data-ttu-id="995aa-p114">Фильтры позволяют получать более точный набор данных или просматривать данные различными способами. Например, отчет об использовании группы ответа позволяет просматривать данные для всех рабочих процессов группы или данные отдельного рабочего процесса. Вы также можете выбрать, как группируются данные. В этом случае данные об использовании сгруппированы по часам, дням, неделям или месяцам.</span><span class="sxs-lookup"><span data-stu-id="995aa-p114">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Response Group Usage Report enables you to view data for all your Response Group workflows or to view data for an individual workflow. You can also choose how data should be grouped. In this case, usages are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="995aa-167">В следующей таблице приведены фильтры, которые можно использовать в отчете об использовании группы ответа.</span><span class="sxs-lookup"><span data-stu-id="995aa-167">The following table lists the filters that you can use with the Response Group Usage Report.</span></span>

### <a name="response-group-usage-report-filters"></a><span data-ttu-id="995aa-168">Фильтры отчета об использовании группы ответа</span><span class="sxs-lookup"><span data-stu-id="995aa-168">Response Group Usage Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="995aa-169">Имя</span><span class="sxs-lookup"><span data-stu-id="995aa-169">Name</span></span></th>
<th><span data-ttu-id="995aa-170">Описание</span><span class="sxs-lookup"><span data-stu-id="995aa-170">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="995aa-171"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="995aa-171"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="995aa-p115">Дата и время начала диапазона. Чтобы просмотреть данные по часам, введите дату и время начала в следующем формате:</span><span class="sxs-lookup"><span data-stu-id="995aa-p115">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="995aa-174">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="995aa-174">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="995aa-p116">Если не указать время начала, автоматически будет выбрано время 00:00 указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</span><span class="sxs-lookup"><span data-stu-id="995aa-p116">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="995aa-177">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="995aa-177">7/7/2012</span></span></p>
<p><span data-ttu-id="995aa-178">Для просмотра по неделям или по месяцам введите дату, выпадающую на любой день недели или месяца, который вы хотите просмотреть (это необязательно должен быть первый день недели или месяца):</span><span class="sxs-lookup"><span data-stu-id="995aa-178">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="995aa-179">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="995aa-179">7/3/2012</span></span></p>
<p><span data-ttu-id="995aa-180">Недели всегда начинаются с Воскресенья и заканчиваются в Субботу.</span><span class="sxs-lookup"><span data-stu-id="995aa-180">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="995aa-181"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="995aa-181"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="995aa-p117">Дата и время окончания диапазона. Чтобы просмотреть данные по часам, введите дату и время окончания в следующем формате:</span><span class="sxs-lookup"><span data-stu-id="995aa-p117">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="995aa-184">7/7/2012 13:00.</span><span class="sxs-lookup"><span data-stu-id="995aa-184">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="995aa-p118">Если не указать время окончания, автоматически будет выбрано время 00:00 указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</span><span class="sxs-lookup"><span data-stu-id="995aa-p118">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="995aa-187">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="995aa-187">7/7/2012</span></span></p>
<p><span data-ttu-id="995aa-188">Для просмотра по неделям или по месяцам введите дату, выпадающую на любой день недели или месяца, который вы хотите просмотреть (это необязательно должен быть первый день недели или месяца):</span><span class="sxs-lookup"><span data-stu-id="995aa-188">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="995aa-189">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="995aa-189">7/3/2012</span></span></p>
<p><span data-ttu-id="995aa-190">Неделя всегда начинается с воскресения и заканчивается субботой.</span><span class="sxs-lookup"><span data-stu-id="995aa-190">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="995aa-191"><strong>Interval</strong></span><span class="sxs-lookup"><span data-stu-id="995aa-191"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="995aa-p119">Временной интервал. Выберите один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="995aa-p119">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="995aa-194">Ежечасно (может отображаться до 25 часов)</span><span class="sxs-lookup"><span data-stu-id="995aa-194">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="995aa-195">Ежедневно (может отображаться до 31 дня)</span><span class="sxs-lookup"><span data-stu-id="995aa-195">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="995aa-196">Еженедельно (может отображаться до 12 недель)</span><span class="sxs-lookup"><span data-stu-id="995aa-196">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="995aa-197">Ежемесячно (может отображаться до 12 месяцев)</span><span class="sxs-lookup"><span data-stu-id="995aa-197">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="995aa-p120">Если даты начала и окончания превышают максимальное допустимые значения для выбранного интервала, отображается только максимальное число значений (от даты начала). Например, если выбран интервал "Ежедневно" с датой начала 07.07.2012 и датой окончания 28.02.2012, данные отображаются с 24:00 07.08.2012 до 24:00 07.09.2012 (то есть в общей сложности отображаются данные для 31 дня).</span><span class="sxs-lookup"><span data-stu-id="995aa-p120">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="995aa-200"><strong>URI рабочего процесса</strong></span><span class="sxs-lookup"><span data-stu-id="995aa-200"><strong>Workflow URI</strong></span></span></p></td>
<td><p><span data-ttu-id="995aa-p121">Позволяет ограничивать возвращаемые данные до указанного рабочего процесса группы ответа. Чтобы использовать этот фильтр, введите SIP-адрес рабочего процесса. Например:</span><span class="sxs-lookup"><span data-stu-id="995aa-p121">Enables you to limit the returned data to the specified Response Group workflow. To use this filter, enter the Workflow SIP address. For example:</span></span></p>
<p><span data-ttu-id="995aa-204">sip:helpdesk@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="995aa-204">sip:helpdesk@litwareinc.com</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="995aa-205">Метрик</span><span class="sxs-lookup"><span data-stu-id="995aa-205">Metrics</span></span>

<span data-ttu-id="995aa-206">В следующей таблице представлены сведения, приведенные в отчете об использовании группы ответа.</span><span class="sxs-lookup"><span data-stu-id="995aa-206">The following table lists the information provided in the Response Group Usage Report.</span></span>

### <a name="response-group-usage-report-metrics"></a><span data-ttu-id="995aa-207">Показатели отчета об использовании группы ответа</span><span class="sxs-lookup"><span data-stu-id="995aa-207">Response Group Usage Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="995aa-208">Имя</span><span class="sxs-lookup"><span data-stu-id="995aa-208">Name</span></span></th>
<th><span data-ttu-id="995aa-209">Возможность сортировки по этому показателю</span><span class="sxs-lookup"><span data-stu-id="995aa-209">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="995aa-210">Описание</span><span class="sxs-lookup"><span data-stu-id="995aa-210">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="995aa-211"><strong>Каждый час</strong></span><span class="sxs-lookup"><span data-stu-id="995aa-211"><strong>Hourly</strong></span></span></p>
<p><span data-ttu-id="995aa-212"><strong>Daily (Ежедневный)</strong></span><span class="sxs-lookup"><span data-stu-id="995aa-212"><strong>Daily</strong></span></span></p>
<p><span data-ttu-id="995aa-213"><strong>Weekly (Еженедельный)</strong></span><span class="sxs-lookup"><span data-stu-id="995aa-213"><strong>Weekly</strong></span></span></p>
<p><span data-ttu-id="995aa-214"><strong>Monthly Channel</strong></span><span class="sxs-lookup"><span data-stu-id="995aa-214"><strong>Monthly</strong></span></span></p></td>
<td><p><span data-ttu-id="995aa-215">Нет</span><span class="sxs-lookup"><span data-stu-id="995aa-215">No</span></span></p></td>
<td><p><span data-ttu-id="995aa-p122">Указывает выбранный интервал времени. Если это возможно, вы можете щелкнуть заданный интервала для просмотра подробных сведений для этого интервала. Например, если вы используете интервал "Ежедневно" и выбираете 07.07.2012, вы увидите почасовую детализацию активности регистрации пользователей для этой даты.</span><span class="sxs-lookup"><span data-stu-id="995aa-p122">Indicates the selected time interval. Where applicable, you can click a given time interval to view detailed information for that interval. For example, if you are using the Daily interval and you click 7/7/2012, you see an hourly breakdown of user registration activity for that date.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="995aa-219"><strong>Принятые вызовы</strong></span><span class="sxs-lookup"><span data-stu-id="995aa-219"><strong>Received calls</strong></span></span></p></td>
<td><p><span data-ttu-id="995aa-220">Нет</span><span class="sxs-lookup"><span data-stu-id="995aa-220">No</span></span></p></td>
<td><p><span data-ttu-id="995aa-p123">Общее количество звонков, полученных всеми экземплярами приложения группы ответа. Если щелкнуть этот элемент, в отчете будет показан отчет по списку вызовов группы ответа за выбранный период времени.</span><span class="sxs-lookup"><span data-stu-id="995aa-p123">Total number of calls received by all instances of the Response Group application. When you click this item, the report shows you the Response Group Call List report for the selected time period.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="995aa-223"><strong>Успешные вызовы</strong></span><span class="sxs-lookup"><span data-stu-id="995aa-223"><strong>Successful calls</strong></span></span></p></td>
<td><p><span data-ttu-id="995aa-224">Нет</span><span class="sxs-lookup"><span data-stu-id="995aa-224">No</span></span></p></td>
<td><p><span data-ttu-id="995aa-p124">Общее количество звонков, полученных приложением группы ответа. Если щелкнуть этот элемент, в отчете будет показан отчет по списку вызовов группы ответа за выбранный период времени.</span><span class="sxs-lookup"><span data-stu-id="995aa-p124">Total number of calls that were picked up the Response Group application. When you click this item, the report shows you the Response Group Call List report for the selected time period.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="995aa-227"><strong>Предложенные вызовы</strong></span><span class="sxs-lookup"><span data-stu-id="995aa-227"><strong>Offered calls</strong></span></span></p></td>
<td><p><span data-ttu-id="995aa-228">Нет</span><span class="sxs-lookup"><span data-stu-id="995aa-228">No</span></span></p></td>
<td><p><span data-ttu-id="995aa-p125">Общее количество звонков, переадресованных агенту группы ответа. Если щелкнуть этот элемент, в отчете будет показан отчет по списку вызовов группы ответа за выбранный период времени.</span><span class="sxs-lookup"><span data-stu-id="995aa-p125">Total number of calls that were transferred to a Response Group agent. When you click this item, the report shows you the Response Group Call List report for the selected time period.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="995aa-231"><strong>Отвеченные вызовы</strong></span><span class="sxs-lookup"><span data-stu-id="995aa-231"><strong>Answered calls</strong></span></span></p></td>
<td><p><span data-ttu-id="995aa-232">Нет</span><span class="sxs-lookup"><span data-stu-id="995aa-232">No</span></span></p></td>
<td><p><span data-ttu-id="995aa-p126">Общее количество звонков, на которые фактически ответил агент группы ответа. Если щелкнуть этот элемент, в отчете будет показан отчет по списку вызовов группы ответа за выбранный период времени.</span><span class="sxs-lookup"><span data-stu-id="995aa-p126">Total number of calls that were actually answered by a Response Group agent. When you click this item, the report shows you the Response Group Call List report for the selected time period.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="995aa-235"><strong>Процент звонков, оставшихся без ответа</strong></span><span class="sxs-lookup"><span data-stu-id="995aa-235"><strong>Percentage of abandoned calls</strong></span></span></p></td>
<td><p><span data-ttu-id="995aa-236">Нет</span><span class="sxs-lookup"><span data-stu-id="995aa-236">No</span></span></p></td>
<td><p><span data-ttu-id="995aa-p127">Общее количество вызовов, которые были получены приложением группы ответа, но но на которые не ответил агент. Это значение вычисляется вычитанием числа отвеченных вызовов из количества принятых вызовов и последующим делением результата на число принятых вызовов. Например, если вы получили 10 вызовов, на 7 из которых был получен ответ, 7 вычитается из 10, что дает 3 неотвеченных вызовов. Это значение затем делится на 10, что дает процент звонков, оставшихся без ответа, равный 30%.</span><span class="sxs-lookup"><span data-stu-id="995aa-p127">Total number of calls that were received by the Response Group application but were never answered by an agent. This is calculated by subtracting the Answered calls from the Received calls, and then dividing that value by the number of received calls. For example, if you have 10 received calls and seven were answered, you would subtract seven from 10, leaving three unanswered calls. That value would then be divided by 10, giving you an abandoned call percentage of 30%.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="995aa-241"><strong> Среднее число вызовов агента в минутах</strong></span><span class="sxs-lookup"><span data-stu-id="995aa-241"><strong>Average call minutes by agent</strong></span></span></p></td>
<td><p><span data-ttu-id="995aa-242">Нет</span><span class="sxs-lookup"><span data-stu-id="995aa-242">No</span></span></p></td>
<td><p><span data-ttu-id="995aa-243">Среднее количество времени, затраченного на ответ агентом группы вызова.</span><span class="sxs-lookup"><span data-stu-id="995aa-243">Average amount of time a Response Group agent spent on a call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="995aa-244"><strong>Переадресованные вызовы</strong></span><span class="sxs-lookup"><span data-stu-id="995aa-244"><strong>Transferred calls</strong></span></span></p></td>
<td><p><span data-ttu-id="995aa-245">Нет</span><span class="sxs-lookup"><span data-stu-id="995aa-245">No</span></span></p></td>
<td><p><span data-ttu-id="995aa-p128">Общее количество звонков, которые были переадресованы группой ответа из-за истечения времени ожидания или переполнение очереди очереди. Если щелкнуть этот элемент, в отчете будет показан отчет по списку вызовов группы ответа за выбранный период времени.</span><span class="sxs-lookup"><span data-stu-id="995aa-p128">Total number of Response Group calls that were transferred because of a queue timeout or queue overflow. When you click this item, the report shows you the Response Group Call List report for the selected time period.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

