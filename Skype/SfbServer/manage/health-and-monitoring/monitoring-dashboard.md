---
title: Использование панели мониторинга в Скайп для Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e00e5783-116f-481f-ad17-3af847d6769a
description: 'Сводка: Сведения о панели мониторинга в Скайп для Business Server.'
ms.openlocfilehash: e12c9faed684121def2e1a4b175f2f7a9fcb534e
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2018
ms.locfileid: "25375275"
---
# <a name="using-the-monitoring-dashboard-in-skype-for-business-server"></a><span data-ttu-id="fbaf2-103">Использование панели мониторинга в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="fbaf2-103">Using the Monitoring Dashboard in Skype for Business Server</span></span>
 
<span data-ttu-id="fbaf2-104">**Сводка:** Сведения о панели мониторинга в Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="fbaf2-104">**Summary:** Learn about the Monitoring Dashboard in Skype for Business Server.</span></span>
  
<span data-ttu-id="fbaf2-105">Панель мониторинга предоставляет администраторам краткий обзор их Скайп для использования системы работоспособности и системы Business Server.</span><span class="sxs-lookup"><span data-stu-id="fbaf2-105">The Monitoring Dashboard provides administrators with a quick overview of their Skype for Business Server system health and system usage.</span></span> <span data-ttu-id="fbaf2-106">Панель мониторинга предназначена для отображения сводного представления важнейших системных показателей в одном из следующих вариантов.</span><span class="sxs-lookup"><span data-stu-id="fbaf2-106">The Dashboard is designed to show an aggregate view of key system metrics and to do so by displaying either:</span></span>
  
- <span data-ttu-id="fbaf2-107">Итоги за текущий день.</span><span class="sxs-lookup"><span data-stu-id="fbaf2-107">Totals for the current day.</span></span> <span data-ttu-id="fbaf2-108">Обратите внимание, что значения, показанные для текущего дня, представляют данные, зафиксированные с полуночи до текущего времени (на основе локального времени сервера отчетов).</span><span class="sxs-lookup"><span data-stu-id="fbaf2-108">Note that values shown for the current day represent data that has been recorded from midnight until the current time (based on the local time of the reporting server).</span></span> <span data-ttu-id="fbaf2-109">Это означает, что вы, как правило, будете просматривать данные за неполный день, а не за 24 часа.</span><span class="sxs-lookup"><span data-stu-id="fbaf2-109">That means that you will typically be viewing data for a partial day and not for a 24-hour period.</span></span> <span data-ttu-id="fbaf2-110">Например если местного времени сервера — 8:00:00, вы увидите стоимость 8 часов данные из-за 8 часов между полночь и текущего времени 8:00:00.</span><span class="sxs-lookup"><span data-stu-id="fbaf2-110">For example, if the local time of the server is 8:00 AM, you see eight hours' worth of data because there are eight hours between midnight and the current time of 8:00 AM.</span></span>
    
- <span data-ttu-id="fbaf2-111">Итоги недели и итоговые значения тенденций за последние шесть недель.</span><span class="sxs-lookup"><span data-stu-id="fbaf2-111">Totals for the week, and trend totals for the past six weeks.</span></span>
    
- <span data-ttu-id="fbaf2-112">Итоги за месяц и итоговые значения тенденций за последние шесть месяцев (только для системы).</span><span class="sxs-lookup"><span data-stu-id="fbaf2-112">Totals for the month, and trend totals for the past six months (for system usage only).</span></span>
    
<span data-ttu-id="fbaf2-113">Обратите внимание на то, что можно использовать командлет [Get-CsReportingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csreportingconfiguration?view=skype-ps) возвращает URL-адрес для доступа к Скайп для отчетов мониторинга Business Server:</span><span class="sxs-lookup"><span data-stu-id="fbaf2-113">Note that you can use the [Get-CsReportingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csreportingconfiguration?view=skype-ps) cmdlet to return the URL used for accessing Skype for Business Server Monitoring Reports:</span></span>
  
```
Get-CsReportingConfiguration
```

<span data-ttu-id="fbaf2-114">По умолчанию панель мониторинга показывает данные о следующих показателях за текущую неделю (а также итоговые значения тенденций за предыдущие шесть недель):</span><span class="sxs-lookup"><span data-stu-id="fbaf2-114">By default, the Monitoring Dashboard shows data for the following metrics for the current week (and trend totals for the previous six weeks):</span></span>
  
## <a name="system-usage-metrics"></a><span data-ttu-id="fbaf2-115">Показатели использования системы</span><span class="sxs-lookup"><span data-stu-id="fbaf2-115">System Usage Metrics</span></span>

 <span data-ttu-id="fbaf2-116">**Регистрация**</span><span class="sxs-lookup"><span data-stu-id="fbaf2-116">**Registration**</span></span>
  
- <span data-ttu-id="fbaf2-117">Уникальных входов пользователей в систему</span><span class="sxs-lookup"><span data-stu-id="fbaf2-117">Unique user logons</span></span>
    
  <span data-ttu-id="fbaf2-118">**Связь между одноранговыми узлами**</span><span class="sxs-lookup"><span data-stu-id="fbaf2-118">**Peer-to-peer**</span></span>
  
- <span data-ttu-id="fbaf2-119">Общее количество сеансов</span><span class="sxs-lookup"><span data-stu-id="fbaf2-119">Total sessions</span></span>
    
- <span data-ttu-id="fbaf2-120">Сеансов обмена мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="fbaf2-120">IM sessions</span></span>
    
- <span data-ttu-id="fbaf2-121">Аудиосеансов</span><span class="sxs-lookup"><span data-stu-id="fbaf2-121">Audio sessions</span></span>
    
- <span data-ttu-id="fbaf2-122">Видеосеансов</span><span class="sxs-lookup"><span data-stu-id="fbaf2-122">Video sessions</span></span>
    
- <span data-ttu-id="fbaf2-123">Общий доступ к приложениям</span><span class="sxs-lookup"><span data-stu-id="fbaf2-123">Application sharing</span></span>
    
- <span data-ttu-id="fbaf2-124">Общее количество минут аудиосеанса</span><span class="sxs-lookup"><span data-stu-id="fbaf2-124">Total audio session minutes</span></span>
    
- <span data-ttu-id="fbaf2-125">Среднее количество минут аудиосеанса</span><span class="sxs-lookup"><span data-stu-id="fbaf2-125">Avg. audio session minutes</span></span>
    
  <span data-ttu-id="fbaf2-126">**Конференция**</span><span class="sxs-lookup"><span data-stu-id="fbaf2-126">**Conference**</span></span>
  
- <span data-ttu-id="fbaf2-127">Общее количество конференций</span><span class="sxs-lookup"><span data-stu-id="fbaf2-127">Total conferences</span></span>
    
- <span data-ttu-id="fbaf2-128">Конференции с обменом мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="fbaf2-128">IM conferences</span></span>
    
- <span data-ttu-id="fbaf2-129">Аудио- и видеоконференции</span><span class="sxs-lookup"><span data-stu-id="fbaf2-129">A/V conferences</span></span>
    
- <span data-ttu-id="fbaf2-130">Конференции с общим доступом к приложениям</span><span class="sxs-lookup"><span data-stu-id="fbaf2-130">Application sharing conferences</span></span>
    
- <span data-ttu-id="fbaf2-131">Веб-конференции</span><span class="sxs-lookup"><span data-stu-id="fbaf2-131">Web conferences</span></span>
    
- <span data-ttu-id="fbaf2-132">Всего организаторов</span><span class="sxs-lookup"><span data-stu-id="fbaf2-132">Total organizers</span></span>
    
- <span data-ttu-id="fbaf2-133">Общая продолжительность видео-/голосовых конференций минутах</span><span class="sxs-lookup"><span data-stu-id="fbaf2-133">Total A/V conference minutes</span></span>
    
- <span data-ttu-id="fbaf2-134">Среднее количество минут аудио- и видеоконференций</span><span class="sxs-lookup"><span data-stu-id="fbaf2-134">Avg. A/V conference minutes</span></span>
    
- <span data-ttu-id="fbaf2-135">Общее количество конференций по ТСОП</span><span class="sxs-lookup"><span data-stu-id="fbaf2-135">Total PSTN conferences</span></span>
    
- <span data-ttu-id="fbaf2-136">Общее количество участников конференций по ТСОП</span><span class="sxs-lookup"><span data-stu-id="fbaf2-136">Total PSTN participants</span></span>
    
- <span data-ttu-id="fbaf2-137">Общая продолжительность участия в конференции по ТСОП в минутах</span><span class="sxs-lookup"><span data-stu-id="fbaf2-137">Total PSTN participant minutes</span></span>
    
<span data-ttu-id="fbaf2-138">Помимо показателей использования системы, отображаются следующие итоговые показатели за текущий день и предыдущие шесть дней (если выбран вариант **недельное представление**) или за текущую неделю и последние шесть недель, если выбран вариант **Месячное представление**.</span><span class="sxs-lookup"><span data-stu-id="fbaf2-138">In addition to the System Usage metrics, the following metrics displays total for the current day and the previous six days (if you select **Weekly View**) or for the current week and the past six weeks if you select **Monthly View**.</span></span>
  
## <a name="per-user-call-diagnostics"></a><span data-ttu-id="fbaf2-139">Диагностика вызова для пользователей</span><span class="sxs-lookup"><span data-stu-id="fbaf2-139">Per-User Call Diagnostics</span></span>

 <span data-ttu-id="fbaf2-140">**Пользователей со сбоями вызовов**</span><span class="sxs-lookup"><span data-stu-id="fbaf2-140">**Users with call failures**</span></span>
  
- <span data-ttu-id="fbaf2-141">Всего пользователей со сбоями вызовов</span><span class="sxs-lookup"><span data-stu-id="fbaf2-141">Total users with call failures</span></span>
    
- <span data-ttu-id="fbaf2-142">Организаторов конференций со сбоями вызовов</span><span class="sxs-lookup"><span data-stu-id="fbaf2-142">Conference organizers with call failures</span></span>
    
  <span data-ttu-id="fbaf2-143">**Пользователей со звонками плохого качества**</span><span class="sxs-lookup"><span data-stu-id="fbaf2-143">**Users with poor quality calls**</span></span>
  
- <span data-ttu-id="fbaf2-144">Всего пользователей со звонками плохого качества</span><span class="sxs-lookup"><span data-stu-id="fbaf2-144">Total users with poor quality calls</span></span>
    
## <a name="call-diagnostics"></a><span data-ttu-id="fbaf2-145">Диагностика звонка</span><span class="sxs-lookup"><span data-stu-id="fbaf2-145">Call Diagnostics</span></span>

<span data-ttu-id="fbaf2-146">Связь между одноранговыми узлами</span><span class="sxs-lookup"><span data-stu-id="fbaf2-146">Peer-to-peer</span></span>
  
- <span data-ttu-id="fbaf2-147">Всего сбоев</span><span class="sxs-lookup"><span data-stu-id="fbaf2-147">Total failures</span></span>
    
- <span data-ttu-id="fbaf2-148">Общий уровень сбоев</span><span class="sxs-lookup"><span data-stu-id="fbaf2-148">Overall failure rate</span></span>
    
- <span data-ttu-id="fbaf2-149">Уровень сбоев обмена мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="fbaf2-149">IM failure rate</span></span>
    
- <span data-ttu-id="fbaf2-150">Уровень сбоев аудио</span><span class="sxs-lookup"><span data-stu-id="fbaf2-150">Audio failure rate</span></span>
    
- <span data-ttu-id="fbaf2-151">Уровень сбоев общего доступа к приложениям</span><span class="sxs-lookup"><span data-stu-id="fbaf2-151">Application sharing failure rate</span></span>
    
<span data-ttu-id="fbaf2-152">Конференция</span><span class="sxs-lookup"><span data-stu-id="fbaf2-152">Conference</span></span>
  
- <span data-ttu-id="fbaf2-153">Всего сбоев</span><span class="sxs-lookup"><span data-stu-id="fbaf2-153">Total failures</span></span>
    
- <span data-ttu-id="fbaf2-154">Общий уровень сбоев</span><span class="sxs-lookup"><span data-stu-id="fbaf2-154">Overall failure rate</span></span>
    
- <span data-ttu-id="fbaf2-155">Уровень сбоев обмена мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="fbaf2-155">IM failure rate</span></span>
    
- <span data-ttu-id="fbaf2-156">Уровень сбоев аудио и видео</span><span class="sxs-lookup"><span data-stu-id="fbaf2-156">A/V failure rate</span></span>
    
- <span data-ttu-id="fbaf2-157">Уровень сбоев общего доступа к приложениям</span><span class="sxs-lookup"><span data-stu-id="fbaf2-157">Application sharing failure rate</span></span>
    
<span data-ttu-id="fbaf2-158">Пять серверов с наибольшим числом неудачных сеансов</span><span class="sxs-lookup"><span data-stu-id="fbaf2-158">Top five servers by failed sessions</span></span>
  
## <a name="media-quality-diagnostics"></a><span data-ttu-id="fbaf2-159">Диагностика качества мультимедиа</span><span class="sxs-lookup"><span data-stu-id="fbaf2-159">Media Quality Diagnostics</span></span>

<span data-ttu-id="fbaf2-160">Связь между одноранговыми узлами</span><span class="sxs-lookup"><span data-stu-id="fbaf2-160">Peer-to-peer</span></span>
  
- <span data-ttu-id="fbaf2-161">Всего вызовов с плохим качеством</span><span class="sxs-lookup"><span data-stu-id="fbaf2-161">Total poor quality calls</span></span>
    
- <span data-ttu-id="fbaf2-162">Процент вызовов плохого качества</span><span class="sxs-lookup"><span data-stu-id="fbaf2-162">Poor quality call percentage</span></span>
    
- <span data-ttu-id="fbaf2-163">Вызовов ТСОП с плохим качеством</span><span class="sxs-lookup"><span data-stu-id="fbaf2-163">PSTN calls with poor quality</span></span>
    
<span data-ttu-id="fbaf2-164">Конференция</span><span class="sxs-lookup"><span data-stu-id="fbaf2-164">Conference</span></span>
  
- <span data-ttu-id="fbaf2-165">Всего вызовов с плохим качеством</span><span class="sxs-lookup"><span data-stu-id="fbaf2-165">Total poor quality calls</span></span>
    
- <span data-ttu-id="fbaf2-166">Процент вызовов плохого качества</span><span class="sxs-lookup"><span data-stu-id="fbaf2-166">Poor quality call percentage</span></span>
    
- <span data-ttu-id="fbaf2-167">Вызовов ТСОП с плохим качеством</span><span class="sxs-lookup"><span data-stu-id="fbaf2-167">PSTN calls with poor quality</span></span>
    
<span data-ttu-id="fbaf2-168">Худшие серверы по проценту вызовов плохого качества</span><span class="sxs-lookup"><span data-stu-id="fbaf2-168">Top worst servers by poor quality call percentage</span></span>
  
## <a name="working-with-the-monitoring-dashboard"></a><span data-ttu-id="fbaf2-169">Работа с панелью мониторинга</span><span class="sxs-lookup"><span data-stu-id="fbaf2-169">Working with the Monitoring Dashboard</span></span>

<span data-ttu-id="fbaf2-p103">Как указано выше, по умолчанию итоговые значения отображаются для текущей недели, а значения, представляющие тенденции – за последние шесть недель. Если требуется просмотреть итоговые значения для текущего месяца (а также тенденции за последние шесть месяцев), щелкните ссылку **Месячное представление** в верхнем правом углу панели мониторинга. При переходе к просмотру итоговых значений за месяц текст ссылки изменяется на **Недельное представление**. Для возврата к недельному представлению следует щелкнуть эту ссылку.</span><span class="sxs-lookup"><span data-stu-id="fbaf2-p103">As noted, by default totals are shown for the current week and trend values are shown for the past six weeks. If you would prefer to see totals for the current month (as well as trend values for the past six months), click the **Monthly View** link in the upper right corner of the dashboard. If you decide to view monthly totals, the link text will change to **Weekly View**. You can switch back to the weekly view by clicking that link.</span></span>
  
> [!TIP]
> <span data-ttu-id="fbaf2-p104">Панель мониторинга позволяет просматривать только итоговые значения за текущую неделю (или месяц) и значения тенденций за последние шесть недель (или месяцев). Эти даты и время изменить нельзя. Например, нельзя использовать эту панель мониторинга для просмотра итоговых значений отчета за период времени, который начинается девять месяцев назад.</span><span class="sxs-lookup"><span data-stu-id="fbaf2-p104">The Monitoring Dashboard restricts you to looking at totals for the current week (or month) and trend values for the past six weeks (or months). You cannot change these dates and times. For example, you cannot use the Dashboard to view report totals for the time period beginning nine months ago.</span></span> 
  
<span data-ttu-id="fbaf2-p105">Значения в столбцах **Эта неделя**, **Этот месяц** и **Сегодня** содержат ссылки на подробные сведения о данном элементе. Следует учитывать, что имя столбца и отображаемые в нем значения зависят от выбранного показателя и от того, выбрано ли недельное или месячное представление. Например, при щелчке итоговых значений для показателя **Входы уникальных пользователей** отображается **Отчет о регистрации пользователей** за указанный период времени. В любой момент можно вернуться на панель мониторинга, щелкнув **Панель мониторинга**.</span><span class="sxs-lookup"><span data-stu-id="fbaf2-p105">The values shown in the **This week**, **This month**, or **Today** columns link you to more detailed information about the item. Keep in mind that the column name and the values displayed in that column will often differ depending on the metric chosen and depending on whether you have selected weekly view or monthly view. For example, if you click the totals shown for the **Unique user logons** metric you will see the **User Registration Report** for the specified time period. You can return to the Monitoring Dashboard at any time by clicking **Dashboard**.</span></span>
  
> [!TIP]
> <span data-ttu-id="fbaf2-181">Можно также получить доступ к домашней страницы отчетов мониторинга сервера, щелкнув ссылку **отчеты** в верхнем правом углу панели мониторинга.</span><span class="sxs-lookup"><span data-stu-id="fbaf2-181">You can also access the Monitoring Server Reports home page by clicking the **Reports** link in the upper right corner of the Dashboard.</span></span>
  
<span data-ttu-id="fbaf2-p106">В столбце **Тенденция** отображается простой график, показывающий итоги за последние шесть недель (или, в зависимости от показателя и временного интервала, за последние шесть дней или шесть месяцев). На этих графиках показана одна точку данных без метки для каждого периода времени (например, для каждой из последних шести недель). Однако из графика можно извлечь фактические значения, удерживая на нем указатель мыши. При этом отображается всплывающая подсказка, где указаны максимальное и минимальное значения на графике.</span><span class="sxs-lookup"><span data-stu-id="fbaf2-p106">The **Trend** column displays a simple line graph that shows totals for the past six weeks (or, depending on the metric and the time interval, the past six days or the past six months). These simple line graphs display one unlabeled data point for each time period (for example, one unlabeled data point for each of the past six weeks). However, you can retrieve actual values for these graphs by holding your mouse pointer over the graph. In that case, a tool tip shows you the maximum and minimum values in the graph.</span></span>
  
## <a name="exporting-data-from-the-monitoring-dashboard"></a><span data-ttu-id="fbaf2-186">Экспорт данных из панели мониторинга</span><span class="sxs-lookup"><span data-stu-id="fbaf2-186">Exporting Data from the Monitoring Dashboard</span></span>

<span data-ttu-id="fbaf2-p107">Панель мониторинга предоставляет несколько способов для экспорта текущего представления. На панели инструментов панели мониторинга можно увидеть значок, который выглядит как дискета с зеленой стрелкой. Если щелкнуть этот значок, появится раскрывающийся список, предоставляющий следующие форматы экспорта данных:</span><span class="sxs-lookup"><span data-stu-id="fbaf2-p107">The Monitoring Dashboard provides a number of ways to export the current dashboard view. On the Dashboard toolbar, you'll see an icon that looks like a floppy disk with a green arrow attached to it. If you click this icon, a dropdown list will appear giving you the following data export formats:</span></span>
  
- <span data-ttu-id="fbaf2-190">XML-файл с данными отчета</span><span class="sxs-lookup"><span data-stu-id="fbaf2-190">XML file with report data</span></span>
    
- <span data-ttu-id="fbaf2-191">CSV (разделители-запятые)</span><span class="sxs-lookup"><span data-stu-id="fbaf2-191">CSV (comma delimited)</span></span>
    
- <span data-ttu-id="fbaf2-192">PDF</span><span class="sxs-lookup"><span data-stu-id="fbaf2-192">PDF</span></span>
    
- <span data-ttu-id="fbaf2-193">MHTML (веб-архив)</span><span class="sxs-lookup"><span data-stu-id="fbaf2-193">MHTML (web archive)</span></span>
    
- <span data-ttu-id="fbaf2-194">Excel</span><span class="sxs-lookup"><span data-stu-id="fbaf2-194">Excel</span></span>
    
- <span data-ttu-id="fbaf2-195">TIFF-файл</span><span class="sxs-lookup"><span data-stu-id="fbaf2-195">TIFF file</span></span>
    
- <span data-ttu-id="fbaf2-196">Word</span><span class="sxs-lookup"><span data-stu-id="fbaf2-196">Word</span></span>
    
<span data-ttu-id="fbaf2-197">Для экспорта текущего представления панели мониторинга (и вместе со значениями) щелкните требуемый вариант экспорта.</span><span class="sxs-lookup"><span data-stu-id="fbaf2-197">To export the current dashboard view (and its values), click the desired export option.</span></span> <span data-ttu-id="fbaf2-198">Скайп для Business Server создает отчет в указанном формате и предоставить возможность отчет об открытии и сохранении его.</span><span class="sxs-lookup"><span data-stu-id="fbaf2-198">Skype for Business Server generates a report in the specified format and then give you the option of opening that report or saving it.</span></span> <span data-ttu-id="fbaf2-199">Обратите внимание, что по умолчанию Скайп для Business Server названия отчета **Панель мониторинга** и сохраняет его в папку файлы для загрузки.</span><span class="sxs-lookup"><span data-stu-id="fbaf2-199">Note that, by default, Skype for Business Server titles the report **Monitoring Dashboard** and saves it to your Downloads folder.</span></span> <span data-ttu-id="fbaf2-200">Для присвоения отчету другого имени или его сохранения в другой папке щелкните стрелку рядом с кнопкой **Сохранить** и затем выберите **Сохранить как**.</span><span class="sxs-lookup"><span data-stu-id="fbaf2-200">To give the report a different name or to store it in a different folder, click the arrow next to the **Save** button and then click **Save As**.</span></span> <span data-ttu-id="fbaf2-201">Для сохранения отчета под именем **Панель мониторинга** в папке «Загрузки» достаточно нажать кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="fbaf2-201">If you are fine with name **Monitoring Dashboard** and with having the report saved in the Downloads folder you can just click the **Save** button.</span></span>
  
<span data-ttu-id="fbaf2-p109">При попытке экспорта данных панели мониторинга может появиться диалоговое окно **Предупреждение системы безопасности** с сообщением «Ваши параметры безопасности не разрешают загрузку этого файла». В этом случае выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="fbaf2-p109">It's possible that, when you try to export dashboard data, a **Security Alert** dialog box will appear along with the message "Your current settings do not allow this file to be downloaded." If that occurs, do the following:</span></span>
  
- <span data-ttu-id="fbaf2-204">В Internet Explorer выберите **Свойства обозревателя**.</span><span class="sxs-lookup"><span data-stu-id="fbaf2-204">In Internet Explorer, select **Internet Options**.</span></span>
    
- <span data-ttu-id="fbaf2-205">В диалоговом окне **Свойства обозревателя** на вкладке **Безопасность** щелкните **Надежные сайты**, затем **Сайты**.</span><span class="sxs-lookup"><span data-stu-id="fbaf2-205">In the **Internet Options** dialog box, on the **Security** tab, click **Trusted sites** and then click **Sites**.</span></span>
    
- <span data-ttu-id="fbaf2-206">В диалоговом окне **Надежные узлы** нажмите кнопку **Добавить** для добавления Скайп для Business Server, на котором работает Скайп для бизнес-сервера отчетов в коллекции надежных веб-сайтов.</span><span class="sxs-lookup"><span data-stu-id="fbaf2-206">In the **Trusted sites** dialog box, click **Add** to add the Skype for Business Server that is running Skype for Business Server Reports to the collections of trusted websites.</span></span>
    
- <span data-ttu-id="fbaf2-207">Нажмите кнопку **Закрыть**, затем **ОК**.</span><span class="sxs-lookup"><span data-stu-id="fbaf2-207">Click **Close** and then click **OK**.</span></span>
    
<span data-ttu-id="fbaf2-p110">После этого для применения изменений потребуется обновить панель мониторинга. Для этого нажмите клавишу F5 или щелкните значок **Обновить** на панели инструментов. (Значок **Обновить** представляет собой окружность с двумя зелеными стрелками.)</span><span class="sxs-lookup"><span data-stu-id="fbaf2-p110">You will then need to refresh the Monitoring Dashboard before the changes take effect. To do that, either press F5 or click the **Refresh** icon in the Dashboard toolbar. (The **Refresh** icon is a circle with a pair of green arrows in it.)</span></span>
  
<span data-ttu-id="fbaf2-p111">Можно также создать электронную таблицу Excel с динамическими потоками данных, содержащую ссылки на последние данные панели мониторинга. Для создания файла динамического потока данных щелкните оранжевый значок **Экспортировать в поток данных** на панели инструментов.</span><span class="sxs-lookup"><span data-stu-id="fbaf2-p111">You can also create an Excel spreadsheet that includes live data feeds, which includes links to the latest Monitoring Dashboard data. To create a live data feed file, click the orange **Export to Data Feed** icon in the toolbar.</span></span>
  
<span data-ttu-id="fbaf2-213">Если вы хотите напечатать текущую панель мониторинга, щелкните значок принтера на панели инструментов.</span><span class="sxs-lookup"><span data-stu-id="fbaf2-213">If you would prefer to print the current Dashboard then click the printer icon in the toolbar.</span></span>
  

