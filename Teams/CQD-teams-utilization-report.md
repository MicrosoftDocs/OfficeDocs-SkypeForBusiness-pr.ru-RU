---
title: Просмотр использования Microsoft Teams в Power BI с использованием данных CQD
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: siunies
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
- Teams_ITAdmin_RemoteWorkers
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
description: Использование отчетов Power BI для отслеживания использования Microsoft Teams в Организации.
ms.openlocfilehash: 7eb39d043fafae0464ac52aa1e328c24b22d73f3
ms.sourcegitcommit: 86366b66b15870fe83cbb76e1ae7aa1ce9b3bfe1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2020
ms.locfileid: "42858764"
---
# <a name="view-microsoft-teams-utilization-in-power-bi-using-cqd-data"></a><span data-ttu-id="f991d-103">Просмотр использования Microsoft Teams в Power BI с использованием данных CQD</span><span class="sxs-lookup"><span data-stu-id="f991d-103">View Microsoft Teams utilization in Power BI using CQD data</span></span>

<span data-ttu-id="f991d-104">В 2020 марта мы добавили отчет об использовании Teams в [шаблоны запросов Power BI для CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span><span class="sxs-lookup"><span data-stu-id="f991d-104">New in March 2020, we've added a Teams Utilization report to our downloadable [Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> 

<span data-ttu-id="f991d-105">Новые отчеты об использовании Teams позволяют узнать, как (и сколько) ваши пользователи работают в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f991d-105">This new Teams Utilization reports lets you see how (and how much) your users are using Microsoft Teams.</span></span> <span data-ttu-id="f991d-106">Эти отчеты предназначены для централизованного хранения данных и могут быстро переходить от администраторов и руководителей предприятий.</span><span class="sxs-lookup"><span data-stu-id="f991d-106">These reports are intended to be a centralized location that both administrators and business leaders can quickly go to for this data.</span></span>

<span data-ttu-id="f991d-107">Отчет Power BI для работы с группами состоит из двух основных отчетов: **[Сводка по количеству звонков](#call-count-summary-report)** и **[Сводка по звуковым минутам](#audio-minutes-summary-report)**.</span><span class="sxs-lookup"><span data-stu-id="f991d-107">The Teams Utilization Power BI report consists of two primary reports: **[Call Count Summary](#call-count-summary-report)** and **[Audio Minutes Summary](#audio-minutes-summary-report)**.</span></span> <span data-ttu-id="f991d-108">Отчеты о [ежедневном использовании](#daily-usage) и [региональных звуковых данных](#regional-audio-details) проводятся, когда пользователь использует преимущества отчетов, указанных в описании ниже.</span><span class="sxs-lookup"><span data-stu-id="f991d-108">The [Daily Usage](#daily-usage) and [Regional Audio Details](#regional-audio-details) reports come into play when a user takes advantage of the drill-down reports, noted in the descriptions below.</span></span>

> [!NOTE]
> <span data-ttu-id="f991d-109">Данные о сборке и подсети должны быть заполнены для предоставления региональных и сетевых возможностей фильтрации.</span><span class="sxs-lookup"><span data-stu-id="f991d-109">Building and subnet data must be populated to provide regional and network filtering capabilities.</span></span>

## <a name="call-count-summary-report"></a><span data-ttu-id="f991d-110">Сводный отчет о подсчете звонков</span><span class="sxs-lookup"><span data-stu-id="f991d-110">Call Count Summary Report</span></span>

<span data-ttu-id="f991d-111">Главная страница (сводка подсчета звонков) немедленно предоставляет количество сеансов обмена аудио-и видеосигналами и экрана за последние 30 и 90 дней, как указано в заголовке раздела.</span><span class="sxs-lookup"><span data-stu-id="f991d-111">The main page (Call Count Summary) immediately provides the number of audio, video and screen sharing sessions over the last 30 and 90 days as noted in the section title.</span></span> <span data-ttu-id="f991d-112">Изначально данные отображаются для всей Организации, и их можно отфильтровать с помощью параметров раскрывающегося списка срезов в левой части страницы.</span><span class="sxs-lookup"><span data-stu-id="f991d-112">The data initially displayed is for the organization as a whole and can be filtered using the slicer dropdown options on the left side of the page.</span></span>

![Снимок экрана: сводный отчет о округе звонка](media/CQD-teams-utilization-report1.png)

1. <span data-ttu-id="f991d-114">Справа от раскрывающегося списка срезов число звонков по типу СМИ разбивается на внутреннее или внешнее представление за последние 30 дней.</span><span class="sxs-lookup"><span data-stu-id="f991d-114">To the right of the slicer dropdowns, the number of calls by media type is broken down to an internal/external view over the past thirty days.</span></span> <span data-ttu-id="f991d-115">Мы можем просмотреть снимок экрана, на котором есть больше звонков из внешних организационных расположений, которые имеют смысл при рассмотрении текущей глобальной среды.</span><span class="sxs-lookup"><span data-stu-id="f991d-115">We can see through the above screenshot that there are more calls happening from outside organizational locations, which makes sense considering the current global environment.</span></span>
  <span data-ttu-id="f991d-116">![Снимок экрана: сводный отчет о округе звонка](media/CQD-teams-utilization-report2.png)</span><span class="sxs-lookup"><span data-stu-id="f991d-116">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report2.png)</span></span>

1. <span data-ttu-id="f991d-117">Справа от поля Счетчик типа мультимедиа для последних 90 дней вычислено ежемесячные звонки по типам носителей.</span><span class="sxs-lookup"><span data-stu-id="f991d-117">To the right of the media type count box, we have the Monthly Call Count by Media Type for the last 90 days.</span></span> <span data-ttu-id="f991d-118">Каждый столбец и тип мультимедиа можно навести на отображение количества за предыдущий месяц или с текущего месяца до текущей даты, предоставляя сведения о тенденциях использования.</span><span class="sxs-lookup"><span data-stu-id="f991d-118">Each column and media type can be hovered over to display the count for a previous month or the current month to date, providing usage trend information.</span></span>
  <span data-ttu-id="f991d-119">![Снимок экрана: сводный отчет о округе звонка](media/CQD-teams-utilization-report3.png)</span><span class="sxs-lookup"><span data-stu-id="f991d-119">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report3.png)</span></span>

1. <span data-ttu-id="f991d-120">Функция середина графа, как и в случае с диаграммой с 90 днем, обеспечивает ежедневное представление использования за последние 30 дней и позволяет пользователю щелкнуть правой кнопкой мыши и подробно ознакомиться с подробными сведениями за определенный день.</span><span class="sxs-lookup"><span data-stu-id="f991d-120">The middle graph functions as the 90-day graph does, however it provides a daily usage view for the past 30 days and allows a user to right click and drill down into details for a specific day.</span></span>
  <span data-ttu-id="f991d-121">![Снимок экрана: сводный отчет о округе звонка](media/CQD-teams-utilization-report4.png)</span><span class="sxs-lookup"><span data-stu-id="f991d-121">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report4.png)</span></span>

<span data-ttu-id="f991d-122">В левом нижнем углу страницы находится таблица, предоставляющая общие значения для каждого типа мультимедиа за последний год.</span><span class="sxs-lookup"><span data-stu-id="f991d-122">On the bottom left section of the page, you'll find a table providing total values for each media type over the past year.</span></span> 
    <span data-ttu-id="f991d-123">![Снимок экрана: сводный отчет о округе звонка](media/CQD-teams-utilization-report5.png)</span><span class="sxs-lookup"><span data-stu-id="f991d-123">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report5.png)</span></span>
  
<span data-ttu-id="f991d-124">У таблицы также есть доступная детализация, на которой можно видеть региональную разбивку данных.</span><span class="sxs-lookup"><span data-stu-id="f991d-124">The table also has an available drill down where you can see a regional data breakdown.</span></span>
    <span data-ttu-id="f991d-125">![Снимок экрана: сводный отчет о округе звонка](media/CQD-teams-utilization-report6.png)</span><span class="sxs-lookup"><span data-stu-id="f991d-125">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report6.png)</span></span>

<span data-ttu-id="f991d-126">На линейчатой диаграмме справа от таблицы отображаются клиенты с наибольшей эффективностью использования (вызовы/потоки) за последние 30 дней.</span><span class="sxs-lookup"><span data-stu-id="f991d-126">To the right of the table, a bar chart shows clients with the most use (calls/streams) for the past 30 days.</span></span>
   <span data-ttu-id="f991d-127">![Снимок экрана: сводный отчет о округе звонка](media/CQD-teams-utilization-report7.png)</span><span class="sxs-lookup"><span data-stu-id="f991d-127">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report7.png)</span></span>


<span data-ttu-id="f991d-128">В последнем наборе диаграмм на этой странице каждый тип мультимедиа отображается по отдельности с разбивкой на Конференции и использование P2P.</span><span class="sxs-lookup"><span data-stu-id="f991d-128">The last set of charts for this page show each media type individually, with a breakdown showing conference and P2P usage.</span></span> <span data-ttu-id="f991d-129">На приведенных ниже диаграммах показано, что в сравнении с P2P количество используемых конференций значительно выше.</span><span class="sxs-lookup"><span data-stu-id="f991d-129">The charts below show that there is a significantly higher number of conference usage as compared to P2P.</span></span>
  <span data-ttu-id="f991d-130">![Снимок экрана: сводный отчет о округе звонка](media/CQD-teams-utilization-report8.png)</span><span class="sxs-lookup"><span data-stu-id="f991d-130">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report8.png)</span></span>

## <a name="audio-minutes-summary-report"></a><span data-ttu-id="f991d-131">Сводный отчет по звуковой минуте</span><span class="sxs-lookup"><span data-stu-id="f991d-131">Audio Minutes Summary Report</span></span>

<span data-ttu-id="f991d-132">В отчете об использовании звуковых минут использование общего числа минут обеспечивается в нескольких различных представлениях.</span><span class="sxs-lookup"><span data-stu-id="f991d-132">On the Audio Minutes usage report, the total minute usage is provided through a few different views.</span></span> 

<span data-ttu-id="f991d-133">Для использования текстовых полей у нас есть ежемесячные сведения об использовании, отображаемые рядом с срезами.</span><span class="sxs-lookup"><span data-stu-id="f991d-133">We have the thirty-day usage summary shown next to the slicers as easy to consume text boxes.</span></span> <span data-ttu-id="f991d-134">В поле "число" отображается 30-дневный итог, в котором есть внутренние и внешние подразделения.</span><span class="sxs-lookup"><span data-stu-id="f991d-134">The top number shows the thirty-day total, with internal and external breakdowns below that.</span></span>

![Снимок экрана: сводный отчет о округе звонка](media/CQD-teams-utilization-report9.png)

<span data-ttu-id="f991d-136">На верхней правой линейчатой диаграмме представлено еарлонг представление использования звука в конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="f991d-136">The top right bar graph provides a yearlong view of conference audio usage.</span></span> <span data-ttu-id="f991d-137">Наведите указатель мыши на месяц, чтобы показать звуковой тезис Конференции.</span><span class="sxs-lookup"><span data-stu-id="f991d-137">Hover over the month to show the conference audio minutes.</span></span>

<span data-ttu-id="f991d-138">Для отображения различий между P2P и звуком конференции в нижней левой части экрана используется весь звук в прошлом году и он разбивается между двумя типами.</span><span class="sxs-lookup"><span data-stu-id="f991d-138">To show the difference in P2P and conference audio, the bottom left chart takes all audio for the past year and breaks it up between the two types.</span></span>

<span data-ttu-id="f991d-139">![Снимок экрана: сводный отчет](media/CQD-teams-utilization-report10.png) о округе звонка последняя диаграмма на странице "звуковые минуты" показывает использование звуковых минут в глобальной наложения на глобальную карту.</span><span class="sxs-lookup"><span data-stu-id="f991d-139">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report10.png) The last chart for the Audio minutes page shows audio minute usage on a global map overlay.</span></span> <span data-ttu-id="f991d-140">Эта диаграмма будет работать только в том случае, если данные построения и подсети загружены в клиент.</span><span class="sxs-lookup"><span data-stu-id="f991d-140">This chart will only work if building and subnet data is uploaded to the tenant.</span></span> <span data-ttu-id="f991d-141">Наложение круговой диаграммы на карте можно прокрутить, а затем в соответствии с региональными национальным использованием звука.</span><span class="sxs-lookup"><span data-stu-id="f991d-141">The pie chart overlay on the map can be drilled into, subsequently providing regional audio usage.</span></span>

![Снимок экрана: сводный отчет о округе звонка](media/CQD-teams-utilization-report11.png)

## <a name="drill-through-capabilities"></a><span data-ttu-id="f991d-143">Возможности детализации</span><span class="sxs-lookup"><span data-stu-id="f991d-143">Drill-through capabilities</span></span>

<span data-ttu-id="f991d-144">Как отмечалось выше, пользователи могут детализировать отчеты об использовании в повседневной и региональной регионах.</span><span class="sxs-lookup"><span data-stu-id="f991d-144">As previously noted, users can drill into the daily and regional usage reports.</span></span>

### <a name="daily-usage"></a><span data-ttu-id="f991d-145">Ежедневное использование</span><span class="sxs-lookup"><span data-stu-id="f991d-145">Daily Usage</span></span>

<span data-ttu-id="f991d-146">Отчет об использовании ежедневно позволяет администратору определять периоды пикового потребления в течение дня.</span><span class="sxs-lookup"><span data-stu-id="f991d-146">The Daily Usage report allows an administrator to identify peak consumption periods through the course of a day.</span></span> <span data-ttu-id="f991d-147">Помимо использования, мы также можем захватить общую информацию о пользователе и тональность за этот день.</span><span class="sxs-lookup"><span data-stu-id="f991d-147">In addition to usage, we are also able to capture overall user sentiment and feedback for that day.</span></span>

![Снимок экрана: сводный отчет о округе звонка](media/CQD-teams-utilization-report12.png)

<span data-ttu-id="f991d-149">Эти данные можно использовать для определения регионов, в которых возникли проблемы во время пикового потребления.</span><span class="sxs-lookup"><span data-stu-id="f991d-149">This data can be used to identify regions having problems during peak consumption times.</span></span>

1.  <span data-ttu-id="f991d-150">На странице Сводка количества звонков — детализация на определенную дату.</span><span class="sxs-lookup"><span data-stu-id="f991d-150">On the Call Count Summary page, drill-through on a specific date.</span></span> <span data-ttu-id="f991d-151">Ознакомьтесь с почасовыми тенденциями этого дня, чтобы найти пиковый коэффициент использования.</span><span class="sxs-lookup"><span data-stu-id="f991d-151">Look at the hourly trend that day to find the peak utilization.</span></span>
  <span data-ttu-id="f991d-152">![Снимок экрана: сводный отчет о округе звонка](media/CQD-teams-utilization-report13.png)</span><span class="sxs-lookup"><span data-stu-id="f991d-152">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report13.png)</span></span>

2.  <span data-ttu-id="f991d-153">Щелкните столбец для этого дня, чтобы отобразить метрики за этот час.</span><span class="sxs-lookup"><span data-stu-id="f991d-153">Click on the column for that day to display metrics for that hour.</span></span>
  <span data-ttu-id="f991d-154">![Снимок экрана: сводный отчет о округе звонка](media/CQD-teams-utilization-report14.png)</span><span class="sxs-lookup"><span data-stu-id="f991d-154">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report14.png)</span></span>
    
    1.  <span data-ttu-id="f991d-155">В таблице под диаграммой отобразятся метрики за этот час.</span><span class="sxs-lookup"><span data-stu-id="f991d-155">The table below the chart will display the metrics for that hour.</span></span> <span data-ttu-id="f991d-156">Это можно сортировать по любому заголовку столбца; Тем не менее, мы будем заинтересованы в поиске проблемных областей.</span><span class="sxs-lookup"><span data-stu-id="f991d-156">This can be sorted by any column header; however, we would be interested in finding problematic areas.</span></span>  
        ![Снимок экрана: сводный отчет о округе звонка](media/CQD-teams-utilization-report15.png)
    
    2.  <span data-ttu-id="f991d-158">Мы видим, что при этом в конференциях в течение этого времени область с изображением пропадает с низкой производительностью.</span><span class="sxs-lookup"><span data-stu-id="f991d-158">We see that the IND region is experiencing poor video performance in conferences during this time frame.</span></span> <span data-ttu-id="f991d-159">Впоследствии CQD Кер Microsoft Reports можно использовать для сужения проблемного места, так как вы определили область "регион" и "время".</span><span class="sxs-lookup"><span data-stu-id="f991d-159">Subsequently, the CQD QER Microsoft reports can be used to narrow down the problematic location as the region and time frame has been identified.</span></span>

### <a name="regional-audio-details"></a><span data-ttu-id="f991d-160">Региональные параметры звука</span><span class="sxs-lookup"><span data-stu-id="f991d-160">Regional Audio Details</span></span>

<span data-ttu-id="f991d-161">В разделе сведения о региональных звуках в конкретном разделе показано использование звуковых минут для выбранного региона.</span><span class="sxs-lookup"><span data-stu-id="f991d-161">The Regional Audio Details drill down specifically shows the audio minute usage for the selected region.</span></span> <span data-ttu-id="f991d-162">Пользователи, у которых есть доступ к CQD, могут просматривать тенденции использования как для P2P, так и для звука конференции в выбранной области.</span><span class="sxs-lookup"><span data-stu-id="f991d-162">Users with access to CQD can see usage trends for both P2P and conference audio within the selected region.</span></span>

1.  <span data-ttu-id="f991d-163">На странице "Сводка количества звонков" перейдите в раздел "определенный регион по таблице".</span><span class="sxs-lookup"><span data-stu-id="f991d-163">On the Call Count Summary page, drill-through to as specific region through the table.</span></span>
  <span data-ttu-id="f991d-164">![Снимок экрана: сводный отчет о округе звонка](media/CQD-teams-utilization-report16.png)</span><span class="sxs-lookup"><span data-stu-id="f991d-164">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report16.png)</span></span>

2.  <span data-ttu-id="f991d-165">Выберите строку, для которой требуются дополнительные сведения о регионе.</span><span class="sxs-lookup"><span data-stu-id="f991d-165">Select the row with the region additional information is needed for.</span></span>
  <span data-ttu-id="f991d-166">![Снимок экрана: сводный отчет о округе звонка](media/CQD-teams-utilization-report17.png)</span><span class="sxs-lookup"><span data-stu-id="f991d-166">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report17.png)</span></span>

3.  <span data-ttu-id="f991d-167">В тенденциях данных показано значительное количество минут, которые используются во внутренней сети, и конференц-связь значительно преходила за использование P2P.</span><span class="sxs-lookup"><span data-stu-id="f991d-167">The data trends show a significant number of minutes being used on the internal network, with conferencing far surpassing P2P use.</span></span>
  <span data-ttu-id="f991d-168">![Снимок экрана: сводный отчет о округе звонка](media/CQD-teams-utilization-report18.png)</span><span class="sxs-lookup"><span data-stu-id="f991d-168">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report18.png)</span></span>

<span data-ttu-id="f991d-169">Региональная тенденция для звука может быть использована для того, чтобы показать влияние пользователей на внешний эффект в мире.</span><span class="sxs-lookup"><span data-stu-id="f991d-169">The regional audio trend can be used to show how users are impacted by external influences in the world.</span></span> <span data-ttu-id="f991d-170">В частности, мы бы хотели видеть внешнее использование в регионах EMEA и APAC, чтобы больше узнать о том, что пользователи должны работать удаленно.</span><span class="sxs-lookup"><span data-stu-id="f991d-170">Specifically, right now, we would expect to see the external usage for the EMEA and APAC regions to increase with people being asked to work remotely.</span></span>



## <a name="related-topics"></a><span data-ttu-id="f991d-171">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="f991d-171">Related topics</span></span>

[<span data-ttu-id="f991d-172">Измерения и меры на панели мониторинга качества звонков</span><span class="sxs-lookup"><span data-stu-id="f991d-172">Dimensions and measures available in Call Quality Dashboard</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="f991d-173">Классификация потоков на панели мониторинга качества звонков</span><span class="sxs-lookup"><span data-stu-id="f991d-173">Stream Classification in Call Quality Dashboard</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="f991d-174">Настройка средства аналитики звонков в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="f991d-174">Set up Skype for Business Call Analytics</span></span>](set-up-call-analytics.md)

[<span data-ttu-id="f991d-175">Использование аналитики звонков для устранения проблем с качеством звонка</span><span class="sxs-lookup"><span data-stu-id="f991d-175">Use Call Analytics to troubleshoot poor call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[<span data-ttu-id="f991d-176">Аналитика звонков и панель мониторинга качества звонков</span><span class="sxs-lookup"><span data-stu-id="f991d-176">Call Analytics and Call Quality Dashboard</span></span>](difference-between-call-analytics-and-call-quality-dashboard.md)
 