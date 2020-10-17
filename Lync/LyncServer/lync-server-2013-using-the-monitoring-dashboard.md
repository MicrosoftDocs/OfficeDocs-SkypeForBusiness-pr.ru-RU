---
title: 'Lync Server 2013: использование панели мониторинга'
description: 'Lync Server 2013: использование панели мониторинга.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using the Monitoring Dashboard
ms:assetid: e00e5783-116f-481f-ad17-3af847d6769a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721905(v=OCS.15)
ms:contentKeyID: 49733839
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e8a68fa1e55b7d0b8305c53802ddabaa904fa214
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556045"
---
# <a name="using-the-monitoring-dashboard-in-lync-server-2013"></a><span data-ttu-id="ce5ca-103">Использование панели мониторинга в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ce5ca-103">Using the Monitoring Dashboard in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ce5ca-104">_**Последнее изменение темы:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="ce5ca-104">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="ce5ca-105">Панель мониторинга предоставляет администраторам краткие сведения о работоспособности и использовании системы Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ce5ca-105">The Monitoring Dashboard provides administrators with a quick overview of their Microsoft Lync Server 2013 system health and system usage.</span></span> <span data-ttu-id="ce5ca-106">Панель мониторинга предназначена для отображения объединенного представления важных системных показателей и для этого она отображает следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="ce5ca-106">The Dashboard is designed to show an aggregate view of key system metrics and to do so by displaying either:</span></span>

  - <span data-ttu-id="ce5ca-p102">Итоги за текущий день. Обратите внимание, что значения, показанные для текущего дня, представляют данные, зафиксированные с полуночи до текущего времени (на основе локального времени сервера отчетов). Это означает, что вы, как правило, будете просматривать данные за неполный день, а не за 24 часа. Например, если локальное время сервера 08:00, вы увидите данные за восемь часов, поскольку с полуночи до текущего времени (08:00) прошло восемь часов.</span><span class="sxs-lookup"><span data-stu-id="ce5ca-p102">Totals for the current day. Note that values shown for the current day represent data that has been recorded from midnight until the current time (based on the local time of the reporting server). That means that you will typically be viewing data for a partial day and not for a 24-hour period. For example, if the local time of the server is 8:00 AM, you see eight hours’ worth of data because there are eight hours between midnight and the current time of 8:00 AM.</span></span>

  - <span data-ttu-id="ce5ca-111">Итоги недели и итоговые значения тенденций за последние шесть недель.</span><span class="sxs-lookup"><span data-stu-id="ce5ca-111">Totals for the week, and trend totals for the past six weeks.</span></span>

  - <span data-ttu-id="ce5ca-112">Итоги за месяц и итоговые значения тенденций за последние шесть месяцев (только для системы).</span><span class="sxs-lookup"><span data-stu-id="ce5ca-112">Totals for the month, and trend totals for the past six months (for system usage only).</span></span>

<span data-ttu-id="ce5ca-113">Обратите внимание, что вы можете использовать командлет [Get-CsReportingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsReportingConfiguration) , чтобы получить URL-адрес, используемый для доступа к отчетам мониторинга Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="ce5ca-113">Note that you can use the [Get-CsReportingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsReportingConfiguration) cmdlet to return the URL used for accessing Lync Server 2013 Monitoring Reports:</span></span>

    Get-CsReportingConfiguration

<span data-ttu-id="ce5ca-114">По умолчанию панель мониторинга показывает данные о следующих показателях за текущую неделю (а также итоговые значения тенденций за предыдущие шесть недель):</span><span class="sxs-lookup"><span data-stu-id="ce5ca-114">By default, the Monitoring Dashboard shows data for the following metrics for the current week (and trend totals for the previous six weeks):</span></span>

<div>

## <a name="system-usage-metrics"></a><span data-ttu-id="ce5ca-115">Показатели использования системы</span><span class="sxs-lookup"><span data-stu-id="ce5ca-115">System Usage Metrics</span></span>

<span data-ttu-id="ce5ca-116">**Registration**</span><span class="sxs-lookup"><span data-stu-id="ce5ca-116">**Registration**</span></span>

  - <span data-ttu-id="ce5ca-117">Уникальных входов пользователей в систему</span><span class="sxs-lookup"><span data-stu-id="ce5ca-117">Unique user logons</span></span>

<span data-ttu-id="ce5ca-118">**"Peer-to-peer" (Одноранговый сеанс);**</span><span class="sxs-lookup"><span data-stu-id="ce5ca-118">**Peer-to-peer**</span></span>

  - <span data-ttu-id="ce5ca-119">Всего сеансов</span><span class="sxs-lookup"><span data-stu-id="ce5ca-119">Total sessions</span></span>

  - <span data-ttu-id="ce5ca-120">Сеансов обмена мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="ce5ca-120">IM sessions</span></span>

  - <span data-ttu-id="ce5ca-121">Аудиосеансов</span><span class="sxs-lookup"><span data-stu-id="ce5ca-121">Audio sessions</span></span>

  - <span data-ttu-id="ce5ca-122">Видеосеансов</span><span class="sxs-lookup"><span data-stu-id="ce5ca-122">Video sessions</span></span>

  - <span data-ttu-id="ce5ca-123">Общий доступ к приложениям</span><span class="sxs-lookup"><span data-stu-id="ce5ca-123">Application sharing</span></span>

  - <span data-ttu-id="ce5ca-124">Общее количество минут аудиосеанса</span><span class="sxs-lookup"><span data-stu-id="ce5ca-124">Total audio session minutes</span></span>

  - <span data-ttu-id="ce5ca-125">Среднее количество минут аудиосеанса</span><span class="sxs-lookup"><span data-stu-id="ce5ca-125">Avg. audio session minutes</span></span>

<span data-ttu-id="ce5ca-126">**Conference**</span><span class="sxs-lookup"><span data-stu-id="ce5ca-126">**Conference**</span></span>

  - <span data-ttu-id="ce5ca-127">Всего конференций</span><span class="sxs-lookup"><span data-stu-id="ce5ca-127">Total conferences</span></span>

  - <span data-ttu-id="ce5ca-128">Конференции с обменом мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="ce5ca-128">IM conferences</span></span>

  - <span data-ttu-id="ce5ca-129">Аудио- и видеоконференции</span><span class="sxs-lookup"><span data-stu-id="ce5ca-129">A/V conferences</span></span>

  - <span data-ttu-id="ce5ca-130">Конференции с общим доступом к приложениям</span><span class="sxs-lookup"><span data-stu-id="ce5ca-130">Application sharing conferences</span></span>

  - <span data-ttu-id="ce5ca-131">Веб-конференции</span><span class="sxs-lookup"><span data-stu-id="ce5ca-131">Web conferences</span></span>

  - <span data-ttu-id="ce5ca-132">Всего организаторов</span><span class="sxs-lookup"><span data-stu-id="ce5ca-132">Total organizers</span></span>

  - <span data-ttu-id="ce5ca-133">Всего минут аудио- и видеоконференций</span><span class="sxs-lookup"><span data-stu-id="ce5ca-133">Total A/V conference minutes</span></span>

  - <span data-ttu-id="ce5ca-134">Среднее количество минут аудио- и видеоконференций</span><span class="sxs-lookup"><span data-stu-id="ce5ca-134">Avg. A/V conference minutes</span></span>

  - <span data-ttu-id="ce5ca-135">Всего конференций ТСОП</span><span class="sxs-lookup"><span data-stu-id="ce5ca-135">Total PSTN conferences</span></span>

  - <span data-ttu-id="ce5ca-136">Всего участников из ТСОП</span><span class="sxs-lookup"><span data-stu-id="ce5ca-136">Total PSTN participants</span></span>

  - <span data-ttu-id="ce5ca-137">Общее количество минут участников из ТСОП</span><span class="sxs-lookup"><span data-stu-id="ce5ca-137">Total PSTN participant minutes</span></span>

<span data-ttu-id="ce5ca-138">Помимо показателей использования системы, следующие показатели отображают итоговые значения за текущий день и предыдущие шесть дней (если выбрано **недельное представление**) или за текущую неделю и последние шесть недель, если выбрано **месячное представление**.</span><span class="sxs-lookup"><span data-stu-id="ce5ca-138">In addition to the System Usage metrics, the following metrics displays total for the current day and the previous six days (if you select **Weekly View**) or for the current week and the past six weeks if you select **Monthly View**.</span></span>

</div>

<div>

## <a name="per-user-call-diagnostics"></a><span data-ttu-id="ce5ca-139">Диагностика вызова для пользователей</span><span class="sxs-lookup"><span data-stu-id="ce5ca-139">Per-User Call Diagnostics</span></span>

<span data-ttu-id="ce5ca-140">**Пользователей со сбоями вызовов**</span><span class="sxs-lookup"><span data-stu-id="ce5ca-140">**Users with call failures**</span></span>

  - <span data-ttu-id="ce5ca-141">Всего пользователей со сбоями вызовов</span><span class="sxs-lookup"><span data-stu-id="ce5ca-141">Total users with call failures</span></span>

  - <span data-ttu-id="ce5ca-142">Организаторов конференций со сбоями вызовов</span><span class="sxs-lookup"><span data-stu-id="ce5ca-142">Conference organizers with call failures</span></span>

<span data-ttu-id="ce5ca-143">**Пользователей со звонками плохого качества**</span><span class="sxs-lookup"><span data-stu-id="ce5ca-143">**Users with poor quality calls**</span></span>

  - <span data-ttu-id="ce5ca-144">Всего пользователей со звонками плохого качества</span><span class="sxs-lookup"><span data-stu-id="ce5ca-144">Total users with poor quality calls</span></span>

</div>

<div>

## <a name="call-diagnostics"></a><span data-ttu-id="ce5ca-145">Диагностика звонка</span><span class="sxs-lookup"><span data-stu-id="ce5ca-145">Call Diagnostics</span></span>

<span data-ttu-id="ce5ca-146">"Peer-to-peer" (Одноранговый сеанс);</span><span class="sxs-lookup"><span data-stu-id="ce5ca-146">Peer-to-peer</span></span>

  - <span data-ttu-id="ce5ca-147">Всего сбоев</span><span class="sxs-lookup"><span data-stu-id="ce5ca-147">Total failures</span></span>

  - <span data-ttu-id="ce5ca-148">Общий уровень сбоев</span><span class="sxs-lookup"><span data-stu-id="ce5ca-148">Overall failure rate</span></span>

  - <span data-ttu-id="ce5ca-149">Уровень сбоев обмена мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="ce5ca-149">IM failure rate</span></span>

  - <span data-ttu-id="ce5ca-150">Уровень сбоев аудио</span><span class="sxs-lookup"><span data-stu-id="ce5ca-150">Audio failure rate</span></span>

  - <span data-ttu-id="ce5ca-151">Уровень сбоев общего доступа к приложениям</span><span class="sxs-lookup"><span data-stu-id="ce5ca-151">Application sharing failure rate</span></span>

<span data-ttu-id="ce5ca-152">Conference</span><span class="sxs-lookup"><span data-stu-id="ce5ca-152">Conference</span></span>

  - <span data-ttu-id="ce5ca-153">Всего сбоев</span><span class="sxs-lookup"><span data-stu-id="ce5ca-153">Total failures</span></span>

  - <span data-ttu-id="ce5ca-154">Общий уровень сбоев</span><span class="sxs-lookup"><span data-stu-id="ce5ca-154">Overall failure rate</span></span>

  - <span data-ttu-id="ce5ca-155">Уровень сбоев обмена мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="ce5ca-155">IM failure rate</span></span>

  - <span data-ttu-id="ce5ca-156">Уровень сбоев аудио и видео</span><span class="sxs-lookup"><span data-stu-id="ce5ca-156">A/V failure rate</span></span>

  - <span data-ttu-id="ce5ca-157">Уровень сбоев общего доступа к приложениям</span><span class="sxs-lookup"><span data-stu-id="ce5ca-157">Application sharing failure rate</span></span>

<span data-ttu-id="ce5ca-158">Пять серверов с наибольшим числом неудачных сеансов</span><span class="sxs-lookup"><span data-stu-id="ce5ca-158">Top five servers by failed sessions</span></span>

</div>

<div>

## <a name="media-quality-diagnostics"></a><span data-ttu-id="ce5ca-159">Диагностика качества мультимедиа</span><span class="sxs-lookup"><span data-stu-id="ce5ca-159">Media Quality Diagnostics</span></span>

<span data-ttu-id="ce5ca-160">"Peer-to-peer" (Одноранговый сеанс);</span><span class="sxs-lookup"><span data-stu-id="ce5ca-160">Peer-to-peer</span></span>

  - <span data-ttu-id="ce5ca-161">Всего вызовов с плохим качеством</span><span class="sxs-lookup"><span data-stu-id="ce5ca-161">Total poor quality calls</span></span>

  - <span data-ttu-id="ce5ca-162">Процент вызовов плохого качества</span><span class="sxs-lookup"><span data-stu-id="ce5ca-162">Poor quality call percentage</span></span>

  - <span data-ttu-id="ce5ca-163">Вызовов ТСОП с плохим качеством</span><span class="sxs-lookup"><span data-stu-id="ce5ca-163">PSTN calls with poor quality</span></span>

<span data-ttu-id="ce5ca-164">Conference</span><span class="sxs-lookup"><span data-stu-id="ce5ca-164">Conference</span></span>

  - <span data-ttu-id="ce5ca-165">Всего вызовов с плохим качеством</span><span class="sxs-lookup"><span data-stu-id="ce5ca-165">Total poor quality calls</span></span>

  - <span data-ttu-id="ce5ca-166">Процент вызовов плохого качества</span><span class="sxs-lookup"><span data-stu-id="ce5ca-166">Poor quality call percentage</span></span>

  - <span data-ttu-id="ce5ca-167">Вызовов ТСОП с плохим качеством</span><span class="sxs-lookup"><span data-stu-id="ce5ca-167">PSTN calls with poor quality</span></span>

<span data-ttu-id="ce5ca-168">Худшие серверы по проценту вызовов плохого качества</span><span class="sxs-lookup"><span data-stu-id="ce5ca-168">Top worst servers by poor quality call percentage</span></span>

</div>

<div>

## <a name="working-with-the-monitoring-dashboard"></a><span data-ttu-id="ce5ca-169">Работа с панелью мониторинга</span><span class="sxs-lookup"><span data-stu-id="ce5ca-169">Working with the Monitoring Dashboard</span></span>

<span data-ttu-id="ce5ca-p103">Как упоминалось, итоговые значения по умолчанию отображаются для текущей недели, а значения тенденций отображаются за последние шесть недель. Если вы хотите увидеть итоговые значения для текущего месяца (а также значения тенденций за последние шесть месяцев), щелкните ссылку **Месячное представление** в верхнем правом углу панели мониторинга. Если вы хотите просмотреть итоговые значения по месяцам, текст ссылки измениться на **Недельное представление**. Вы можете вернуться в недельное представление, щелкнув эту ссылку.</span><span class="sxs-lookup"><span data-stu-id="ce5ca-p103">As noted, by default totals are shown for the current week and trend values are shown for the past six weeks. If you would prefer to see totals for the current month (as well as trend values for the past six months), click the **Monthly View** link in the upper right corner of the dashboard. If you decide to view monthly totals, the link text will change to **Weekly View**. You can switch back to the weekly view by clicking that link.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="ce5ca-p104">Панель мониторинга позволяет просматривать только итоговые значения за текущую неделю (или месяц) и значения тенденций за последние шесть недель (или месяцев). Эти даты и время изменить нельзя. Например, нельзя использовать эту панель мониторинга для просмотра итоговых значений отчета за период времени, который начинается девять месяцев назад.</span><span class="sxs-lookup"><span data-stu-id="ce5ca-p104">The Monitoring Dashboard restricts you to looking at totals for the current week (or month) and trend values for the past six weeks (or months). You cannot change these dates and times. For example, you cannot use the Dashboard to view report totals for the time period beginning nine months ago.</span></span>



</div>

<span data-ttu-id="ce5ca-p105">Значения в столбцах **Эта неделя**, **Этот месяц** и **Сегодня** приводят к более подробным сведениям об элементе. Помните, что имя столбца и значения в нем будут отличаться в зависимости от выбранного показателя и в зависимости от того, выбрали ли недельное или месячное представление. Например, если щелкнуть итоговые значения для показателя **Уникальных входов пользователей в систему**, вы увидите **Отчет о регистрации пользователей** за указанный период времени. Вы можете вернуться в панель мониторинга в любое время, щелкнув **Панель мониторинга**.</span><span class="sxs-lookup"><span data-stu-id="ce5ca-p105">The values shown in the **This week**, **This month**, or **Today** columns link you to more detailed information about the item. Keep in mind that the column name and the values displayed in that column will often differ depending on the metric chosen and depending on whether you have selected weekly view or monthly view. For example, if you click the totals shown for the **Unique user logons** metric you will see the **User Registration Report** for the specified time period. You can return to the Monitoring Dashboard at any time by clicking **Dashboard**.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="ce5ca-181">Вы также можете получить доступ к домашней странице отчетов сервера мониторинга, щелкнув ссылку <STRONG>отчеты</STRONG> в правом верхнем углу панели мониторинга.</span><span class="sxs-lookup"><span data-stu-id="ce5ca-181">You can also access the Monitoring Server Reports home page by clicking the <STRONG>Reports</STRONG> link in the upper right corner of the Dashboard.</span></span>



</div>

<span data-ttu-id="ce5ca-p106">В столбце **Тенденция** отображается простой линейный график, показывающий итоги за последние шесть недель (или, в зависимости от показателя и временного интервала — за последние шесть дней или шесть месяцев). Эти простые линейные графики показывают одну точку данных без метки для каждого периода времени (например, одна немаркированная точка данных для каждой из последних шести недель). Тем не менее вы можете получить фактические значения для этих графиков, удерживая указатель мыши на графике. В этом случае во всплывающей подсказке отображается максимальное и минимальное значения графика.</span><span class="sxs-lookup"><span data-stu-id="ce5ca-p106">The **Trend** column displays a simple line graph that shows totals for the past six weeks (or, depending on the metric and the time interval, the past six days or the past six months). These simple line graphs display one unlabeled data point for each time period (for example, one unlabeled data point for each of the past six weeks). However, you can retrieve actual values for these graphs by holding your mouse pointer over the graph. In that case, a tooltip shows you the maximum and minimum values in the graph.</span></span>

</div>

<div>

## <a name="exporting-data-from-the-monitoring-dashboard"></a><span data-ttu-id="ce5ca-186">Экспорт данных из панели мониторинга</span><span class="sxs-lookup"><span data-stu-id="ce5ca-186">Exporting Data from the Monitoring Dashboard</span></span>

<span data-ttu-id="ce5ca-p107">Панель мониторинга предоставляет несколько способов для экспорта текущего представления. На панели инструментов панели мониторинга можно увидеть значок, который выглядит как дискета с зеленой стрелкой. Если щелкнуть этот значок, появится раскрывающийся список, предоставляющий следующие форматы экспорта данных:</span><span class="sxs-lookup"><span data-stu-id="ce5ca-p107">The Monitoring Dashboard provides a number of ways to export the current dashboard view. On the Dashboard toolbar, you'll see an icon that looks like a floppy disk with a green arrow attached to it. If you click this icon, a dropdown list will appear giving you the following data export formats:</span></span>

  - <span data-ttu-id="ce5ca-190">XML-файл с данными отчета</span><span class="sxs-lookup"><span data-stu-id="ce5ca-190">XML file with report data</span></span>

  - <span data-ttu-id="ce5ca-191">CSV (разделители-запятые)</span><span class="sxs-lookup"><span data-stu-id="ce5ca-191">CSV (comma delimited)</span></span>

  - <span data-ttu-id="ce5ca-192">PDF</span><span class="sxs-lookup"><span data-stu-id="ce5ca-192">PDF</span></span>

  - <span data-ttu-id="ce5ca-193">MHTML (веб-архив)</span><span class="sxs-lookup"><span data-stu-id="ce5ca-193">MHTML (web archive)</span></span>

  - <span data-ttu-id="ce5ca-194">Excel</span><span class="sxs-lookup"><span data-stu-id="ce5ca-194">Excel</span></span>

  - <span data-ttu-id="ce5ca-195">Файл TIFF</span><span class="sxs-lookup"><span data-stu-id="ce5ca-195">TIFF file</span></span>

  - <span data-ttu-id="ce5ca-196">Word</span><span class="sxs-lookup"><span data-stu-id="ce5ca-196">Word</span></span>

<span data-ttu-id="ce5ca-197">Для экспорта текущего представления панели мониторинга (и его значений) щелкните нужный параметр экспорта.</span><span class="sxs-lookup"><span data-stu-id="ce5ca-197">To export the current dashboard view (and its values), click the desired export option.</span></span> <span data-ttu-id="ce5ca-198">Lync Server 2013 создает отчет в указанном формате, а затем предоставляет возможность открыть этот отчет или сохранить его.</span><span class="sxs-lookup"><span data-stu-id="ce5ca-198">Lync Server 2013 generates a report in the specified format and then give you the option of opening that report or saving it.</span></span> <span data-ttu-id="ce5ca-199">Обратите внимание, что по умолчанию Lync Server заголовков панели мониторинга отчетов и сохраняет ее в папке **"загрузки"** .</span><span class="sxs-lookup"><span data-stu-id="ce5ca-199">Note that, by default, Lync Server titles the report **Monitoring Dashboard** and saves it to your Downloads folder.</span></span> <span data-ttu-id="ce5ca-200">Чтобы указать другое имя отчета или сохранить его в другой папке, щелкните стрелку рядом с кнопкой **Сохранить** и нажмите кнопку**Сохранить как**.</span><span class="sxs-lookup"><span data-stu-id="ce5ca-200">To give the report a different name or to store it in a different folder, click the arrow next to the **Save** button and then click **Save As**.</span></span> <span data-ttu-id="ce5ca-201">Если имя **Панель мониторинга** и папка "Загрузки" вас устраивают, можно просто нажать кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="ce5ca-201">If you are fine with name **Monitoring Dashboard** and with having the report saved in the Downloads folder you can just click the **Save** button.</span></span>

<span data-ttu-id="ce5ca-p109">Возможно, что при попытке экспорта данных панели мониторинга появится диалоговое окно **Предупреждение безопасности** с сообщением "Текущие настройки не позволяют загрузить этот файл". В этом случае выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="ce5ca-p109">It's possible that, when you try to export dashboard data, a **Security Alert** dialog box will appear along with the message "Your current settings do not allow this file to be downloaded." If that occurs, do the following:</span></span>

  - <span data-ttu-id="ce5ca-204">В Internet Explorer выберите **Свойства обозревателя**.</span><span class="sxs-lookup"><span data-stu-id="ce5ca-204">In Internet Explorer, select **Internet Options**.</span></span>

  - <span data-ttu-id="ce5ca-205">В диалоговом окне \*\* Свойства обозревателя \*\* на вкладке \*\*Безопасность \*\* щелкните **Надежных сайты**, а затем выберите **Сайты**.</span><span class="sxs-lookup"><span data-stu-id="ce5ca-205">In the **Internet Options** dialog box, on the **Security** tab, click **Trusted sites** and then click **Sites**.</span></span>

  - <span data-ttu-id="ce5ca-206">В диалоговом окне **Надежные сайты** нажмите кнопку **Добавить** , чтобы добавить Lync Server 2013, на котором запущены отчеты Lync Server 2013, в коллекции надежных веб-сайтов.</span><span class="sxs-lookup"><span data-stu-id="ce5ca-206">In the **Trusted sites** dialog box, click **Add** to add the Lync Server 2013 that is running Lync Server 2013 Reports to the collections of trusted websites.</span></span>

  - <span data-ttu-id="ce5ca-207">Нажмите кнопку **Закрыть**, а затем кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="ce5ca-207">Click **Close** and then click **OK**.</span></span>

<span data-ttu-id="ce5ca-p110">Затем вам понадобится обновить панель мониторинга, чтобы изменения вступили в силу. Для этого нажмите клавишу F5 или щелкните значок **Обновить** на панели инструментов. (Значок **Обновить** — это круг с двумя зелеными стрелками.)</span><span class="sxs-lookup"><span data-stu-id="ce5ca-p110">You will then need to refresh the Monitoring Dashboard before the changes take effect. To do that, either press F5 or click the **Refresh** icon in the Dashboard toolbar. (The **Refresh** icon is a circle with a pair of green arrows in it.)</span></span>

<span data-ttu-id="ce5ca-p111">Вы также можете создать таблицу Excel с динамическими потоками данных, которая содержит ссылки на последние данные панели мониторинга. Чтобы создать файл динамического потока данных, щелкните значок **Экспортировать в поток данных** на панели мониторинга.</span><span class="sxs-lookup"><span data-stu-id="ce5ca-p111">You can also create an Excel spreadsheet that includes live data feeds, which includes links to the latest Monitoring Dashboard data. To create a live data feed file, click the orange **Export to Data Feed** icon in the toolbar.</span></span>

<span data-ttu-id="ce5ca-213">Если вы хотите напечатать текущую панель мониторинга, щелкните значок принтера на панели инструментов.</span><span class="sxs-lookup"><span data-stu-id="ce5ca-213">If you would prefer to print the current Dashboard then click the printer icon in the toolbar.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

