---
title: Просмотр использования Microsoft Teams в Power BI с помощью данных CQD
ms.author: serdars
author: SerdarSoysal
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
description: Используйте отчеты Power BI по использованию Teams для доступа к данным панели мониторинга качества звонка (CQD) Microsoft Teams для отслеживания использования Microsoft Teams в организации.
ms.openlocfilehash: bda89f3715997016e6c1bea242dcf6b8b182c6bf
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/06/2020
ms.locfileid: "46581550"
---
# <a name="view-microsoft-teams-utilization-in-power-bi-using-cqd-data"></a><span data-ttu-id="8af2f-103">Просмотр использования Microsoft Teams в Power BI с помощью данных CQD</span><span class="sxs-lookup"><span data-stu-id="8af2f-103">View Microsoft Teams utilization in Power BI using CQD data</span></span>

<span data-ttu-id="8af2f-104">В марте 2020 г. мы добавили отчет об использовании Teams в загружаемые шаблоны запросов Power BI для [CQD.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="8af2f-104">New in March 2020, we've added a Teams Utilization report to our downloadable [Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> 

<span data-ttu-id="8af2f-105">Эти новые отчеты по использованию Teams позволяют узнать, как (и в какой степени) пользователи используют Microsoft Teams, используя данные панели мониторинга качества звонка (CQD) Teams.</span><span class="sxs-lookup"><span data-stu-id="8af2f-105">This new Teams Utilization reports lets you see how (and how much) your users are using Microsoft Teams by accessing Teams Call Quality Dashboard (CQD) data.</span></span> <span data-ttu-id="8af2f-106">Эти отчеты предназначены для централизованного использования этих данных и администраторами, и руководителями предприятий.</span><span class="sxs-lookup"><span data-stu-id="8af2f-106">These reports are intended to be a centralized location that both administrators and business leaders can quickly go to for this data.</span></span>

<span data-ttu-id="8af2f-107">Отчет Power BI по использованию Teams состоит из двух основных отчетов: **["Сводка](#call-count-summary-report)** по подсчету вызовов" и **["Итоги](#audio-minutes-summary-report)** аудиосвязи в минутах".</span><span class="sxs-lookup"><span data-stu-id="8af2f-107">The Teams Utilization Power BI report consists of two primary reports: **[Call Count Summary](#call-count-summary-report)** and **[Audio Minutes Summary](#audio-minutes-summary-report)**.</span></span> <span data-ttu-id="8af2f-108">Отчеты ["Ежедневное](#daily-usage)использование", [](#user-list) "Региональные аудиоконференции", "Сведения о конференции" и "Список пользователей" вступает в силу, когда пользователь получает возможность воспользоваться подробными отчетами, которые описаны ниже. [](#regional-audio-details) [](#conference-details)</span><span class="sxs-lookup"><span data-stu-id="8af2f-108">The [Daily Usage](#daily-usage), [Regional Audio Details](#regional-audio-details), [Conference Details](#conference-details) and [User List](#user-list) reports come into play when a user takes advantage of the drill-down reports, noted in the descriptions below.</span></span>

> [!NOTE]
> <span data-ttu-id="8af2f-109">Для того чтобы обеспечить возможности фильтрации по регионам и сетям, данные о здании и подсети должны быть заполнены.</span><span class="sxs-lookup"><span data-stu-id="8af2f-109">Building and subnet data must be populated to provide regional and network filtering capabilities.</span></span>

## <a name="call-count-summary-report"></a><span data-ttu-id="8af2f-110">Сводный отчет о подсчете вызовов</span><span class="sxs-lookup"><span data-stu-id="8af2f-110">Call Count Summary Report</span></span>

<span data-ttu-id="8af2f-111">На главной странице ("Сводка по подсчету вызовов") сразу выведется количество сеансов общего доступа к звуку, видео и экрану за последние 30 и 90 дней, как отмечено в разделе.</span><span class="sxs-lookup"><span data-stu-id="8af2f-111">The main page (Call Count Summary) immediately provides the number of audio, video and screen sharing sessions over the last 30 and 90 days as noted in the section title.</span></span> <span data-ttu-id="8af2f-112">Изначально отображаемая информация отображается для всей организации и может быть отфильтрованной с помощью параметров перепада среза в левой части страницы.</span><span class="sxs-lookup"><span data-stu-id="8af2f-112">The data initially displayed is for the organization as a whole and can be filtered using the slicer dropdown options on the left side of the page.</span></span>

![Снимок экрана: отчеты об использовании Teams](media/CQD-teams-utilization-report1.png)

1. <span data-ttu-id="8af2f-114">Справа от срезов количество вызовов по типам мультимедиа разбито на внутреннее или внешнее представление за последние 30 дней.</span><span class="sxs-lookup"><span data-stu-id="8af2f-114">To the right of the slicer dropdowns, the number of calls by media type is broken down to an internal/external view over the past thirty days.</span></span> <span data-ttu-id="8af2f-115">На снимке экрана выше по видно, что происходят дополнительные вызовы из-за пределов организации, что дает смысл рассмотреть текущую глобальную среду.</span><span class="sxs-lookup"><span data-stu-id="8af2f-115">We can see through the above screenshot that there are more calls happening from outside organizational locations, which makes sense considering the current global environment.</span></span>
  <span data-ttu-id="8af2f-116">![Снимок экрана: отчеты об использовании Teams](media/CQD-teams-utilization-report2.png)</span><span class="sxs-lookup"><span data-stu-id="8af2f-116">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report2.png)</span></span>

1. <span data-ttu-id="8af2f-117">Справа от окна "Количество типов мультимедиа" есть ежемесячный подсчет вызовов по типу мультимедиа за последние 90 дней.</span><span class="sxs-lookup"><span data-stu-id="8af2f-117">To the right of the media type count box, we have the Monthly Call Count by Media Type for the last 90 days.</span></span> <span data-ttu-id="8af2f-118">На каждый столбец и тип мультимедиа можно навести курсор, чтобы отобразить количество за предыдущий или текущий месяц на текущую дату, предоставляя сведения о тенденциях использования.</span><span class="sxs-lookup"><span data-stu-id="8af2f-118">Each column and media type can be hovered over to display the count for a previous month or the current month to date, providing usage trend information.</span></span>
  <span data-ttu-id="8af2f-119">![Снимок экрана: отчеты об использовании Teams](media/CQD-teams-utilization-report3.png)</span><span class="sxs-lookup"><span data-stu-id="8af2f-119">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report3.png)</span></span>
 

1. <span data-ttu-id="8af2f-120">Средний график работает так же, как и на 90-дневном графике, но предоставляет представление ежедневного использования за последние 30 дней и позволяет пользователю щелкнуть правой кнопкой мыши и деталить детали для определенного дня.</span><span class="sxs-lookup"><span data-stu-id="8af2f-120">The middle graph functions as the 90-day graph does, however it provides a daily usage view for the past 30 days and allows a user to right click and drill down into details for a specific day.</span></span>
  <span data-ttu-id="8af2f-121">![Снимок экрана: отчеты об использовании Teams](media/CQD-teams-utilization-report4.png)</span><span class="sxs-lookup"><span data-stu-id="8af2f-121">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report4.png)</span></span>

<span data-ttu-id="8af2f-122">В нижнем левом разделе страницы вы найдете таблицу с итогами для каждого типа мультимедиа за последний год.</span><span class="sxs-lookup"><span data-stu-id="8af2f-122">On the bottom left section of the page, you'll find a table providing total values for each media type over the past year.</span></span> 
    <span data-ttu-id="8af2f-123">![Снимок экрана: снимок экрана: отчеты об использовании ](media/CQD-teams-utilization-report5.png) ![ Teams](media/CQD-teams-utilization-report6.png)</span><span class="sxs-lookup"><span data-stu-id="8af2f-123">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report5.png) ![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report6.png)</span></span>   

<span data-ttu-id="8af2f-124">В правой части таблицы показаны клиенты, которые чаще всего используют (вызовы и потоки) за последние 30 дней.</span><span class="sxs-lookup"><span data-stu-id="8af2f-124">To the right of the table, a bar chart shows clients with the most use (calls/streams) for the past 30 days.</span></span>
   <span data-ttu-id="8af2f-125">![Снимок экрана: отчеты об использовании Teams](media/CQD-teams-utilization-report7.png)</span><span class="sxs-lookup"><span data-stu-id="8af2f-125">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report7.png)</span></span>

<span data-ttu-id="8af2f-126">В последнем наборе диаграмм для этой страницы каждый тип мультимедиа отображается по отдельности с разбивкой по конференциям и использованию P2P.</span><span class="sxs-lookup"><span data-stu-id="8af2f-126">The last set of charts for this page show each media type individually, with a breakdown showing conference and P2P usage.</span></span> <span data-ttu-id="8af2f-127">На диаграммах ниже видно, что использование конференц-залов значительно больше по сравнению с P2P.</span><span class="sxs-lookup"><span data-stu-id="8af2f-127">The charts below show that there is a significantly higher number of conference usage as compared to P2P.</span></span>
  <span data-ttu-id="8af2f-128">![Снимок экрана: отчеты об использовании Teams](media/CQD-teams-utilization-report8.png)</span><span class="sxs-lookup"><span data-stu-id="8af2f-128">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report8.png)</span></span>

## <a name="audio-minutes-summary-report"></a><span data-ttu-id="8af2f-129">Сводный отчет о минутах аудиосвязи</span><span class="sxs-lookup"><span data-stu-id="8af2f-129">Audio Minutes Summary Report</span></span>

<span data-ttu-id="8af2f-130">В отчете об использовании минут аудиосвязи общая сумма минут представлена в нескольких различных представлениях.</span><span class="sxs-lookup"><span data-stu-id="8af2f-130">On the Audio Minutes usage report, the total minute usage is provided through a few different views.</span></span> 

<span data-ttu-id="8af2f-131">Рядом с срезами отображается 30-дневная сводка по использованию текстовых полей.</span><span class="sxs-lookup"><span data-stu-id="8af2f-131">We have the thirty-day usage summary shown next to the slicers as easy to consume text boxes.</span></span> <span data-ttu-id="8af2f-132">На верхнем числе — итог за 30 дней с внутренней и внешней разбивкой.</span><span class="sxs-lookup"><span data-stu-id="8af2f-132">The top number shows the thirty-day total, with internal and external breakdowns below that.</span></span>

![Снимок экрана: отчеты об использовании Teams](media/CQD-teams-utilization-report9.png)

<span data-ttu-id="8af2f-134">Верхний правый график предоставляет ежегодное представление использования аудиоконференции.</span><span class="sxs-lookup"><span data-stu-id="8af2f-134">The top right bar graph provides a yearlong view of conference audio usage.</span></span> <span data-ttu-id="8af2f-135">Наведите курсор на месяц, чтобы показать минуты аудиоконференции.</span><span class="sxs-lookup"><span data-stu-id="8af2f-135">Hover over the month to show the conference audio minutes.</span></span>

<span data-ttu-id="8af2f-136">Чтобы показать разницу в звуке на P2P и конференции, на нижней левой диаграмме берется весь звук за последний год и он раздвеывается между двумя типами.</span><span class="sxs-lookup"><span data-stu-id="8af2f-136">To show the difference in P2P and conference audio, the bottom left chart takes all audio for the past year and breaks it up between the two types.</span></span>

![Снимок экрана: отчеты об использовании Teams](media/CQD-teams-utilization-report10.png)

<span data-ttu-id="8af2f-138">Последняя диаграмма на странице "Минуты звука" отображает использование минут звука на глобальной карте.</span><span class="sxs-lookup"><span data-stu-id="8af2f-138">The last chart for the Audio minutes page shows audio minute usage on a global map overlay.</span></span> <span data-ttu-id="8af2f-139">Эта диаграмма будет работать только в том случае, если данные о здании и подсети загружены в клиент.</span><span class="sxs-lookup"><span data-stu-id="8af2f-139">This chart will only work if building and subnet data is uploaded to the tenant.</span></span> <span data-ttu-id="8af2f-140">Круговая диаграмма, наложение диаграммы на карте, может быть разуверчена, что впоследствии обеспечивает использование региональной аудиосвязи.</span><span class="sxs-lookup"><span data-stu-id="8af2f-140">The pie chart overlay on the map can be drilled into, subsequently providing regional audio usage.</span></span>

![Снимок экрана: отчеты об использовании Teams](media/CQD-teams-utilization-report11.png)


## <a name="drill-through-capabilities"></a><span data-ttu-id="8af2f-142">Возможности drill-through</span><span class="sxs-lookup"><span data-stu-id="8af2f-142">Drill-through capabilities</span></span>

<span data-ttu-id="8af2f-143">Как было отмечено ранее, пользователи могут использовать отчеты о ежедневном и региональном использовании.</span><span class="sxs-lookup"><span data-stu-id="8af2f-143">As previously noted, users can drill into the daily and regional usage reports.</span></span>

### <a name="daily-usage"></a><span data-ttu-id="8af2f-144">Ежедневное использование</span><span class="sxs-lookup"><span data-stu-id="8af2f-144">Daily Usage</span></span>

<span data-ttu-id="8af2f-145">Отчет о ежедневном использовании позволяет администратору определить пиковые периоды потребления в течение дня.</span><span class="sxs-lookup"><span data-stu-id="8af2f-145">The Daily Usage report allows an administrator to identify peak consumption periods through the course of a day.</span></span> <span data-ttu-id="8af2f-146">Кроме использования, мы также можем фиксировать общее тональность пользователей и отзывы за этот день.</span><span class="sxs-lookup"><span data-stu-id="8af2f-146">In addition to usage, we are also able to capture overall user sentiment and feedback for that day.</span></span>

![Снимок экрана: отчеты об использовании Teams](media/CQD-teams-utilization-report12.png)

<span data-ttu-id="8af2f-148">В отчете о ежедневном использовании отображается количество звуковых, видеофайлов и экранных ресурсов за выбранный день с добавленной возможностью отличить внутреннее и внешнее подключение.</span><span class="sxs-lookup"><span data-stu-id="8af2f-148">The Daily usage report displays the number of Audio, Video and Screen shares for the selected day with the added ability to differentiate between internal and external connectivity.</span></span> <span data-ttu-id="8af2f-149">Разбивка между одноранговой конференцией и одноранговой разбивкой находится справа от итога модалисти.</span><span class="sxs-lookup"><span data-stu-id="8af2f-149">A Conference and Peer to Peer breakdown is to the immediate right of the modality total box.</span></span> <span data-ttu-id="8af2f-150">В правой верхней части отчета содержится список конференций, связанных с их ИД и участниками на день.</span><span class="sxs-lookup"><span data-stu-id="8af2f-150">The top right of the report provides a list of conferences with their associated ID and participants for the day.</span></span> <span data-ttu-id="8af2f-151">Кроме того, в списке конференций содержится дополнительный детали;</span><span class="sxs-lookup"><span data-stu-id="8af2f-151">The conference list provides an additional drill down to the Conference Details report as well.</span></span> <span data-ttu-id="8af2f-152">РИСУНОК "ЗАМЕНИТЬ"</span><span class="sxs-lookup"><span data-stu-id="8af2f-152">REPLACE GRAPHIC</span></span>

![Снимок экрана: отчеты об использовании Teams](media/CQD-teams-utilization-report13.png)

<span data-ttu-id="8af2f-154">Гограмма в центральной области позволяет пользователям определять пиковые периоды потребления в течение дня.</span><span class="sxs-lookup"><span data-stu-id="8af2f-154">The bar graph in the center area allows the user to identify peak consumption periods through the course of a day.</span></span> <span data-ttu-id="8af2f-155">Пользователи могут просуммировать данные в час, представленный на графике, чтобы представить отчет о списке пользователей за час.</span><span class="sxs-lookup"><span data-stu-id="8af2f-155">Users may drill down into the hour represented on the graph which will present the User List report for the hour.</span></span>

<span data-ttu-id="8af2f-156">Справа от гограммы отзывы пользователей представлены в визуальном формате.</span><span class="sxs-lookup"><span data-stu-id="8af2f-156">To the right of the bar graph, User Feedback is presented in a visual format.</span></span> <span data-ttu-id="8af2f-157">Хотя это может быть неохожим, оно дает представление, которое можно использовать для выявления потенциальных проблем.</span><span class="sxs-lookup"><span data-stu-id="8af2f-157">While user sentiment can be subjective, it does provide insight that can be used to identify potential issues.</span></span>

<span data-ttu-id="8af2f-158">В нижней таблице содержится диапазон метрик для дня.</span><span class="sxs-lookup"><span data-stu-id="8af2f-158">The bottom table provides a range of metrics for the day.</span></span> <span data-ttu-id="8af2f-159">Неудовлетворительные процентные показатели и коэффициенты сбоев могут предоставить администратору возможности улучшения.</span><span class="sxs-lookup"><span data-stu-id="8af2f-159">Poor percentages along with failure rates can provide an administrator with potential areas of improvement.</span></span> <span data-ttu-id="8af2f-160">Каждый час также можно выбрать по отдельности, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="8af2f-160">Each hour can also be selected individually as shown below.</span></span>

<span data-ttu-id="8af2f-161">Эти данные можно использовать для определения регионов, в которые возникают проблемы во время пикового потребление.</span><span class="sxs-lookup"><span data-stu-id="8af2f-161">This data can be used to identify regions having problems during peak consumption times.</span></span>


<span data-ttu-id="8af2f-162">Щелкните столбец для этого дня, чтобы отобразить показатели за этот час.</span><span class="sxs-lookup"><span data-stu-id="8af2f-162">Click on the column for that day to display metrics for that hour.</span></span>
<span data-ttu-id="8af2f-163">![Снимок экрана: отчеты об использовании Teams](media/CQD-teams-utilization-report14.png)</span><span class="sxs-lookup"><span data-stu-id="8af2f-163">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report14.png)</span></span>
  
  1.  <span data-ttu-id="8af2f-164">В таблице под диаграммой отобразятся показатели за этот час.</span><span class="sxs-lookup"><span data-stu-id="8af2f-164">The table below the chart will display the metrics for that hour.</span></span> <span data-ttu-id="8af2f-165">Его можно отсортировать по любому заглавию столбца. однако мы хотели бы заинтересовались поиском проблемных областей.</span><span class="sxs-lookup"><span data-stu-id="8af2f-165">This can be sorted by any column header; however, we would be interested in finding problematic areas.</span></span>  
    ![Снимок экрана: отчеты об использовании Teams](media/CQD-teams-utilization-report15.png)
    
  2.  <span data-ttu-id="8af2f-167">Мы видим, что в регионе IND в этот период времени наблюдается низкая производительность видео во время конференций.</span><span class="sxs-lookup"><span data-stu-id="8af2f-167">We see that the IND region is experiencing poor video performance in conferences during this time frame.</span></span> <span data-ttu-id="8af2f-168">Впоследствии можно использовать отчеты Корпорации Майкрософт для QER для CQD, чтобы сузить проблемное расположение по мере определения региона и замера времени.</span><span class="sxs-lookup"><span data-stu-id="8af2f-168">Subsequently, the CQD QER Microsoft reports can be used to narrow down the problematic location as the region and time frame has been identified.</span></span>

### <a name="conference-details"></a><span data-ttu-id="8af2f-169">Сведения о конференции</span><span class="sxs-lookup"><span data-stu-id="8af2f-169">Conference Details</span></span>

<span data-ttu-id="8af2f-170">Отчет "Сведения о конференции" содержит дополнительные сведения о собраниях (от списка участников) до типов мультимедиа, используемых в ходе сеанса.</span><span class="sxs-lookup"><span data-stu-id="8af2f-170">The Conference Details report provides additional insight for meetings, from an attendee list, to the media types used during the session.</span></span>

<span data-ttu-id="8af2f-171">Щелкните правой кнопкой мыши диаграмму участников в диаграмме "Код конференции" на странице ежедневного использования, чтобы получить подробные сведения о конференции.</span><span class="sxs-lookup"><span data-stu-id="8af2f-171">Right click a conference the participant bar in the conference ID chart on the Daily usage page to drill down into the conference details.</span></span>

![Снимок экрана: отчеты об использовании Teams](media/CQD-teams-utilization-report24.png)

![Снимок экрана: отчеты об использовании Teams](media/CQD-teams-utilization-report25.png)
  

<span data-ttu-id="8af2f-174">Мы видим участников конференции, а также всю относящемся к ней информацию (в том числе потери пакетов и дрожание), что помогает устранить неполадки в нижней таблице.</span><span class="sxs-lookup"><span data-stu-id="8af2f-174">We can see the participants in the conference as well as all the pertinent information down to packet loss and jitter to assist with potential troubleshooting efforts in the bottom table.</span></span>

![Снимок экрана: отчеты об использовании Teams](media/CQD-teams-utilization-report26.png)


### <a name="regional-audio-details"></a><span data-ttu-id="8af2f-176">Сведения о региональных аудиофайлах</span><span class="sxs-lookup"><span data-stu-id="8af2f-176">Regional Audio Details</span></span>

<span data-ttu-id="8af2f-177">Подробные сведения о региональных аудиофайлах, в частности, показывают минуты звука для выбранного региона.</span><span class="sxs-lookup"><span data-stu-id="8af2f-177">The Regional Audio Details drill down specifically shows the audio minute usage for the selected region.</span></span> <span data-ttu-id="8af2f-178">Пользователи с доступом к CQD могут видеть тенденции использования как для P2P-, так и для аудиоконференции в выбранном регионе.</span><span class="sxs-lookup"><span data-stu-id="8af2f-178">Users with access to CQD can see usage trends for both P2P and conference audio within the selected region.</span></span>

1.  <span data-ttu-id="8af2f-179">На странице "Сводка по подсчету вызовов" прообщайте сведения о конкретном регионе таблицы.</span><span class="sxs-lookup"><span data-stu-id="8af2f-179">On the Call Count Summary page, drill-through to as specific region through the table.</span></span>
  <span data-ttu-id="8af2f-180">![Снимок экрана: отчеты об использовании Teams](media/CQD-teams-utilization-report16.png)</span><span class="sxs-lookup"><span data-stu-id="8af2f-180">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report16.png)</span></span>

2.  <span data-ttu-id="8af2f-181">Вы выберите строку с областью, для которую необходимы дополнительные сведения.</span><span class="sxs-lookup"><span data-stu-id="8af2f-181">Select the row with the region additional information is needed for.</span></span>
  <span data-ttu-id="8af2f-182">![Снимок экрана: отчеты об использовании Teams](media/CQD-teams-utilization-report17.png)</span><span class="sxs-lookup"><span data-stu-id="8af2f-182">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report17.png)</span></span>

3.  <span data-ttu-id="8af2f-183">Тенденции изменения данных показывают значительное количество минут, используемых во внутренней сети, при этом использование 2P-2P-2010 значительно превышает число минут.</span><span class="sxs-lookup"><span data-stu-id="8af2f-183">The data trends show a significant number of minutes being used on the internal network, with conferencing far surpassing P2P use.</span></span>
  <span data-ttu-id="8af2f-184">![Снимок экрана: отчеты об использовании Teams](media/CQD-teams-utilization-report18.png)</span><span class="sxs-lookup"><span data-stu-id="8af2f-184">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report18.png)</span></span>

<span data-ttu-id="8af2f-185">Региональные тенденции звука можно использовать для демонстрации влияния внешних факторов на пользователей в мире.</span><span class="sxs-lookup"><span data-stu-id="8af2f-185">The regional audio trend can be used to show how users are impacted by external influences in the world.</span></span> <span data-ttu-id="8af2f-186">В частности, в настоящее время мы ожидаем, что внешний уровень использования регионов EMEA и APAC увеличится, и людям будет предложено поработать удаленно.</span><span class="sxs-lookup"><span data-stu-id="8af2f-186">Specifically, right now, we would expect to see the external usage for the EMEA and APAC regions to increase with people being asked to work remotely.</span></span>


### <a name="user-list"></a><span data-ttu-id="8af2f-187">Список пользователей</span><span class="sxs-lookup"><span data-stu-id="8af2f-187">User List</span></span>

<span data-ttu-id="8af2f-188">Как и предполагалось, данные о пользователях за определенный час, выбранный пользователем для просмотра отчета, можно просмотреть в списке пользователей.</span><span class="sxs-lookup"><span data-stu-id="8af2f-188">The User List drill down provides, as one might expect, user specific information for a specific hour selected by the person viewing the report.</span></span> <span data-ttu-id="8af2f-189">Отчет "Список пользователей" доступен с помощью drill down (Почасовая диаграмма тенденций) в отчете "Ежедневное использование".</span><span class="sxs-lookup"><span data-stu-id="8af2f-189">The User List report is accessible through a drill down in the Hourly Trends graph on the Daily Usage report.</span></span> <span data-ttu-id="8af2f-190">Щелкните правой кнопкой мыши нужные дополнительные сведения о часах и выберите "Развернуть" и "Список пользователей", как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="8af2f-190">Right click on the hour additional information is needed for and select Drill through and User List, as shown below.</span></span>

![Снимок экрана: отчеты об использовании Teams](media/CQD-teams-utilization-report19.png)

<span data-ttu-id="8af2f-192">В отчете "Список пользователей" показаны внутренние и внешние подключения через кольцевую диаграмму в центре верхней части страницы.</span><span class="sxs-lookup"><span data-stu-id="8af2f-192">The User List report shows internal/external connectivity through the doughnut chart in the top center of the page.</span></span> <span data-ttu-id="8af2f-193">На приведенной ниже картинке видно, что за пределами корпоративной сети участие большое количество участников.</span><span class="sxs-lookup"><span data-stu-id="8af2f-193">We can see that there is a large amount of participation from Outside the corporate network in the below image.</span></span>

<span data-ttu-id="8af2f-194">Справа вверху на графике показано количество звонков, сделанных каждым пользователем в течение часа.</span><span class="sxs-lookup"><span data-stu-id="8af2f-194">The top right of the graph shows the number of calls made by each user within that hour.</span></span>

![Снимок экрана: отчеты об использовании Teams](media/CQD-teams-utilization-report20.png)

<span data-ttu-id="8af2f-196">В нижней таблице содержится подробная информация о сеансах, в которых участвовал каждый пользователь в течение этого часа.</span><span class="sxs-lookup"><span data-stu-id="8af2f-196">The bottom table provides detailed information for the sessions each user participated in during that hour.</span></span> <span data-ttu-id="8af2f-197">Столбец "Тип сбоя" удобен для определения причин, которые вызывались звоном.</span><span class="sxs-lookup"><span data-stu-id="8af2f-197">The Failure Type column is useful in determining what caused a call to drop.</span></span> <span data-ttu-id="8af2f-198">Столбцы "Захват" и "Отрисовка устройства" полезны для определения причин неудовлетворительнго качества звонка.</span><span class="sxs-lookup"><span data-stu-id="8af2f-198">The Capture and Render Device columns are useful in identifying why a call was reported having poor quality.</span></span>


## <a name="related-topics"></a><span data-ttu-id="8af2f-199">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="8af2f-199">Related topics</span></span>

[<span data-ttu-id="8af2f-200">Измерения и меры на панели мониторинга качества звонков</span><span class="sxs-lookup"><span data-stu-id="8af2f-200">Dimensions and measures available in Call Quality Dashboard</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="8af2f-201">Классификация потоков на панели мониторинга качества звонков</span><span class="sxs-lookup"><span data-stu-id="8af2f-201">Stream Classification in Call Quality Dashboard</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="8af2f-202">Настройка средства аналитики звонков в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="8af2f-202">Set up Skype for Business Call Analytics</span></span>](set-up-call-analytics.md)

[<span data-ttu-id="8af2f-203">Использование аналитики звонков для устранения проблем с качеством звонка</span><span class="sxs-lookup"><span data-stu-id="8af2f-203">Use Call Analytics to troubleshoot poor call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[<span data-ttu-id="8af2f-204">Аналитика звонков и панель мониторинга качества звонков</span><span class="sxs-lookup"><span data-stu-id="8af2f-204">Call Analytics and Call Quality Dashboard</span></span>](difference-between-call-analytics-and-call-quality-dashboard.md)

[<span data-ttu-id="8af2f-205">Устранение неполадок Teams</span><span class="sxs-lookup"><span data-stu-id="8af2f-205">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)
 