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
description: Использование отчетов Power BI для доступа к данным об использовании панели мониторинга качества вызовов Microsoft Teams (CQD) для отслеживания использования Microsoft Teams в Организации.
ms.openlocfilehash: bd1a95a683da881a78acb5d4849bba0ac55f4898
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085585"
---
# <a name="view-microsoft-teams-utilization-in-power-bi-using-cqd-data"></a><span data-ttu-id="d6c95-103">Просмотр использования Microsoft Teams в Power BI с использованием данных CQD</span><span class="sxs-lookup"><span data-stu-id="d6c95-103">View Microsoft Teams utilization in Power BI using CQD data</span></span>

<span data-ttu-id="d6c95-104">В 2020 марта мы добавили отчет об использовании Teams в [шаблоны запросов Power BI для CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span><span class="sxs-lookup"><span data-stu-id="d6c95-104">New in March 2020, we've added a Teams Utilization report to our downloadable [Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> 

<span data-ttu-id="d6c95-105">Эти новые отчеты об использовании Teams позволяют узнать, как (и сколько) ваши пользователи работают с Microsoft Teams, выполнив доступ к данным на панели мониторинга качества вызовов Teams (CQD).</span><span class="sxs-lookup"><span data-stu-id="d6c95-105">This new Teams Utilization reports lets you see how (and how much) your users are using Microsoft Teams by accessing Teams Call Quality Dashboard (CQD) data.</span></span> <span data-ttu-id="d6c95-106">Эти отчеты предназначены для централизованного хранения данных и могут быстро переходить от администраторов и руководителей предприятий.</span><span class="sxs-lookup"><span data-stu-id="d6c95-106">These reports are intended to be a centralized location that both administrators and business leaders can quickly go to for this data.</span></span>

<span data-ttu-id="d6c95-107">Отчет Power BI для работы с группами состоит из двух основных отчетов: **[Сводка по количеству звонков](#call-count-summary-report)** и **[Сводка по звуковым минутам](#audio-minutes-summary-report)**.</span><span class="sxs-lookup"><span data-stu-id="d6c95-107">The Teams Utilization Power BI report consists of two primary reports: **[Call Count Summary](#call-count-summary-report)** and **[Audio Minutes Summary](#audio-minutes-summary-report)**.</span></span> <span data-ttu-id="d6c95-108">[Ежедневное использование](#daily-usage), [сведения о региональных](#regional-audio-details)параметрах, [сведения о конференции](#conference-details) и отчеты о [списках пользователей](#user-list) воспринимаются, когда пользователь использует преимущества подробных отчетов, указанных в описании ниже.</span><span class="sxs-lookup"><span data-stu-id="d6c95-108">The [Daily Usage](#daily-usage), [Regional Audio Details](#regional-audio-details), [Conference Details](#conference-details) and [User List](#user-list) reports come into play when a user takes advantage of the drill-down reports, noted in the descriptions below.</span></span>

> [!NOTE]
> <span data-ttu-id="d6c95-109">Данные о сборке и подсети должны быть заполнены для предоставления региональных и сетевых возможностей фильтрации.</span><span class="sxs-lookup"><span data-stu-id="d6c95-109">Building and subnet data must be populated to provide regional and network filtering capabilities.</span></span>

## <a name="call-count-summary-report"></a><span data-ttu-id="d6c95-110">Сводный отчет о подсчете звонков</span><span class="sxs-lookup"><span data-stu-id="d6c95-110">Call Count Summary Report</span></span>

<span data-ttu-id="d6c95-111">Главная страница (сводка подсчета звонков) немедленно предоставляет количество сеансов обмена аудио-и видеосигналами и экрана за последние 30 и 90 дней, как указано в заголовке раздела.</span><span class="sxs-lookup"><span data-stu-id="d6c95-111">The main page (Call Count Summary) immediately provides the number of audio, video and screen sharing sessions over the last 30 and 90 days as noted in the section title.</span></span> <span data-ttu-id="d6c95-112">Изначально данные отображаются для всей Организации, и их можно отфильтровать с помощью параметров раскрывающегося списка срезов в левой части страницы.</span><span class="sxs-lookup"><span data-stu-id="d6c95-112">The data initially displayed is for the organization as a whole and can be filtered using the slicer dropdown options on the left side of the page.</span></span>

![Снимок экрана: отчеты об использовании Teams](media/CQD-teams-utilization-report1.png)

1. <span data-ttu-id="d6c95-114">Справа от раскрывающегося списка срезов число звонков по типу СМИ разбивается на внутреннее или внешнее представление за последние 30 дней.</span><span class="sxs-lookup"><span data-stu-id="d6c95-114">To the right of the slicer dropdowns, the number of calls by media type is broken down to an internal/external view over the past thirty days.</span></span> <span data-ttu-id="d6c95-115">Мы можем просмотреть снимок экрана, на котором есть больше звонков из внешних организационных расположений, которые имеют смысл при рассмотрении текущей глобальной среды.</span><span class="sxs-lookup"><span data-stu-id="d6c95-115">We can see through the above screenshot that there are more calls happening from outside organizational locations, which makes sense considering the current global environment.</span></span>
  <span data-ttu-id="d6c95-116">![Снимок экрана: отчеты об использовании Teams](media/CQD-teams-utilization-report2.png)</span><span class="sxs-lookup"><span data-stu-id="d6c95-116">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report2.png)</span></span>

1. <span data-ttu-id="d6c95-117">Справа от поля Счетчик типа мультимедиа для последних 90 дней вычислено ежемесячные звонки по типам носителей.</span><span class="sxs-lookup"><span data-stu-id="d6c95-117">To the right of the media type count box, we have the Monthly Call Count by Media Type for the last 90 days.</span></span> <span data-ttu-id="d6c95-118">Каждый столбец и тип мультимедиа можно навести на отображение количества за предыдущий месяц или с текущего месяца до текущей даты, предоставляя сведения о тенденциях использования.</span><span class="sxs-lookup"><span data-stu-id="d6c95-118">Each column and media type can be hovered over to display the count for a previous month or the current month to date, providing usage trend information.</span></span>
  <span data-ttu-id="d6c95-119">![Снимок экрана: отчеты об использовании Teams](media/CQD-teams-utilization-report3.png)</span><span class="sxs-lookup"><span data-stu-id="d6c95-119">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report3.png)</span></span>
 

1. <span data-ttu-id="d6c95-120">Функция середина графа, как и в случае с диаграммой с 90 днем, обеспечивает ежедневное представление использования за последние 30 дней и позволяет пользователю щелкнуть правой кнопкой мыши и подробно ознакомиться с подробными сведениями за определенный день.</span><span class="sxs-lookup"><span data-stu-id="d6c95-120">The middle graph functions as the 90-day graph does, however it provides a daily usage view for the past 30 days and allows a user to right click and drill down into details for a specific day.</span></span>
  <span data-ttu-id="d6c95-121">![Снимок экрана: отчеты об использовании Teams](media/CQD-teams-utilization-report4.png)</span><span class="sxs-lookup"><span data-stu-id="d6c95-121">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report4.png)</span></span>

<span data-ttu-id="d6c95-122">В левом нижнем углу страницы находится таблица, предоставляющая общие значения для каждого типа мультимедиа за последний год.</span><span class="sxs-lookup"><span data-stu-id="d6c95-122">On the bottom left section of the page, you'll find a table providing total values for each media type over the past year.</span></span> 
    <span data-ttu-id="d6c95-123">![Снимок экрана: снимок отчета об использовании Teams ](media/CQD-teams-utilization-report5.png) ![ : отчеты об использовании Teams](media/CQD-teams-utilization-report6.png)</span><span class="sxs-lookup"><span data-stu-id="d6c95-123">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report5.png) ![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report6.png)</span></span>   

<span data-ttu-id="d6c95-124">На линейчатой диаграмме справа от таблицы отображаются клиенты с наибольшей эффективностью использования (вызовы/потоки) за последние 30 дней.</span><span class="sxs-lookup"><span data-stu-id="d6c95-124">To the right of the table, a bar chart shows clients with the most use (calls/streams) for the past 30 days.</span></span>
   <span data-ttu-id="d6c95-125">![Снимок экрана: отчеты об использовании Teams](media/CQD-teams-utilization-report7.png)</span><span class="sxs-lookup"><span data-stu-id="d6c95-125">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report7.png)</span></span>

<span data-ttu-id="d6c95-126">В последнем наборе диаграмм на этой странице каждый тип мультимедиа отображается по отдельности с разбивкой на Конференции и использование P2P.</span><span class="sxs-lookup"><span data-stu-id="d6c95-126">The last set of charts for this page show each media type individually, with a breakdown showing conference and P2P usage.</span></span> <span data-ttu-id="d6c95-127">На приведенных ниже диаграммах показано, что в сравнении с P2P количество используемых конференций значительно выше.</span><span class="sxs-lookup"><span data-stu-id="d6c95-127">The charts below show that there is a significantly higher number of conference usage as compared to P2P.</span></span>
  <span data-ttu-id="d6c95-128">![Снимок экрана: отчеты об использовании Teams](media/CQD-teams-utilization-report8.png)</span><span class="sxs-lookup"><span data-stu-id="d6c95-128">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report8.png)</span></span>

## <a name="audio-minutes-summary-report"></a><span data-ttu-id="d6c95-129">Сводный отчет по звуковой минуте</span><span class="sxs-lookup"><span data-stu-id="d6c95-129">Audio Minutes Summary Report</span></span>

<span data-ttu-id="d6c95-130">В отчете об использовании звуковых минут использование общего числа минут обеспечивается в нескольких различных представлениях.</span><span class="sxs-lookup"><span data-stu-id="d6c95-130">On the Audio Minutes usage report, the total minute usage is provided through a few different views.</span></span> 

<span data-ttu-id="d6c95-131">Для использования текстовых полей у нас есть ежемесячные сведения об использовании, отображаемые рядом с срезами.</span><span class="sxs-lookup"><span data-stu-id="d6c95-131">We have the thirty-day usage summary shown next to the slicers as easy to consume text boxes.</span></span> <span data-ttu-id="d6c95-132">В поле "число" отображается 30-дневный итог, в котором есть внутренние и внешние подразделения.</span><span class="sxs-lookup"><span data-stu-id="d6c95-132">The top number shows the thirty-day total, with internal and external breakdowns below that.</span></span>

![Снимок экрана: отчеты об использовании Teams](media/CQD-teams-utilization-report9.png)

<span data-ttu-id="d6c95-134">На верхней правой линейчатой диаграмме представлено yearlong представление использования звука в конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="d6c95-134">The top right bar graph provides a yearlong view of conference audio usage.</span></span> <span data-ttu-id="d6c95-135">Наведите указатель мыши на месяц, чтобы показать звуковой тезис Конференции.</span><span class="sxs-lookup"><span data-stu-id="d6c95-135">Hover over the month to show the conference audio minutes.</span></span>

<span data-ttu-id="d6c95-136">Для отображения различий между P2P и звуком конференции в нижней левой части экрана используется весь звук в прошлом году и он разбивается между двумя типами.</span><span class="sxs-lookup"><span data-stu-id="d6c95-136">To show the difference in P2P and conference audio, the bottom left chart takes all audio for the past year and breaks it up between the two types.</span></span>

![Снимок экрана: отчеты об использовании Teams](media/CQD-teams-utilization-report10.png)

<span data-ttu-id="d6c95-138">Последняя диаграмма на странице "звуковые минуты" показывает использование звуковых минут в глобальной раскрытиех карт.</span><span class="sxs-lookup"><span data-stu-id="d6c95-138">The last chart for the Audio minutes page shows audio minute usage on a global map overlay.</span></span> <span data-ttu-id="d6c95-139">Эта диаграмма будет работать только в том случае, если данные построения и подсети загружены в клиент.</span><span class="sxs-lookup"><span data-stu-id="d6c95-139">This chart will only work if building and subnet data is uploaded to the tenant.</span></span> <span data-ttu-id="d6c95-140">Наложение круговой диаграммы на карте можно прокрутить, а затем в соответствии с региональными национальным использованием звука.</span><span class="sxs-lookup"><span data-stu-id="d6c95-140">The pie chart overlay on the map can be drilled into, subsequently providing regional audio usage.</span></span>

![Снимок экрана: отчеты об использовании Teams](media/CQD-teams-utilization-report11.png)


## <a name="drill-through-capabilities"></a><span data-ttu-id="d6c95-142">Возможности детализации</span><span class="sxs-lookup"><span data-stu-id="d6c95-142">Drill-through capabilities</span></span>

<span data-ttu-id="d6c95-143">Как отмечалось выше, пользователи могут детализировать отчеты об использовании в повседневной и региональной регионах.</span><span class="sxs-lookup"><span data-stu-id="d6c95-143">As previously noted, users can drill into the daily and regional usage reports.</span></span>

### <a name="daily-usage"></a><span data-ttu-id="d6c95-144">Ежедневное использование</span><span class="sxs-lookup"><span data-stu-id="d6c95-144">Daily Usage</span></span>

<span data-ttu-id="d6c95-145">Отчет об использовании ежедневно позволяет администратору определять периоды пикового потребления в течение дня.</span><span class="sxs-lookup"><span data-stu-id="d6c95-145">The Daily Usage report allows an administrator to identify peak consumption periods through the course of a day.</span></span> <span data-ttu-id="d6c95-146">Помимо использования, мы также можем захватить общую информацию о пользователе и тональность за этот день.</span><span class="sxs-lookup"><span data-stu-id="d6c95-146">In addition to usage, we are also able to capture overall user sentiment and feedback for that day.</span></span>

![Снимок экрана: отчеты об использовании Teams](media/CQD-teams-utilization-report12.png)

<span data-ttu-id="d6c95-148">В отчете об использовании ежедневно отображаются общие сведения о звуковых и видеофайлах, а также о видеосвязи для выбранного дня, благодаря которым добавлена возможность различать внутренние и внешние подключения.</span><span class="sxs-lookup"><span data-stu-id="d6c95-148">The Daily usage report displays the number of Audio, Video and Screen shares for the selected day with the added ability to differentiate between internal and external connectivity.</span></span> <span data-ttu-id="d6c95-149">Подразделение Конференции и одноранговой сети — это непосредственно справа от поля «Итого» модальности.</span><span class="sxs-lookup"><span data-stu-id="d6c95-149">A Conference and Peer to Peer breakdown is to the immediate right of the modality total box.</span></span> <span data-ttu-id="d6c95-150">В правом верхнем углу отчета содержится список конференций с соответствующими ИДЕНТИФИКАТОРами и участниками в течение дня.</span><span class="sxs-lookup"><span data-stu-id="d6c95-150">The top right of the report provides a list of conferences with their associated ID and participants for the day.</span></span> <span data-ttu-id="d6c95-151">Список конференций также предоставляет дополнительный уровень детализации в отчете о Конференции.</span><span class="sxs-lookup"><span data-stu-id="d6c95-151">The conference list provides an additional drill down to the Conference Details report as well.</span></span> <span data-ttu-id="d6c95-152">ЗАМЕНА РИСУНКА</span><span class="sxs-lookup"><span data-stu-id="d6c95-152">REPLACE GRAPHIC</span></span>

![Снимок экрана: отчеты об использовании Teams](media/CQD-teams-utilization-report13.png)

<span data-ttu-id="d6c95-154">Линейчатая диаграмма в центральной области позволяет пользователю определять периоды пикового расхода в течение дня.</span><span class="sxs-lookup"><span data-stu-id="d6c95-154">The bar graph in the center area allows the user to identify peak consumption periods through the course of a day.</span></span> <span data-ttu-id="d6c95-155">Пользователи могут детализировать на графике часы, представленные на диаграмме, которые будут представлять отчет о списке пользователей за час.</span><span class="sxs-lookup"><span data-stu-id="d6c95-155">Users may drill down into the hour represented on the graph which will present the User List report for the hour.</span></span>

<span data-ttu-id="d6c95-156">Справа от линейчатой диаграммы обратная связь пользователя представлена в визуальном формате.</span><span class="sxs-lookup"><span data-stu-id="d6c95-156">To the right of the bar graph, User Feedback is presented in a visual format.</span></span> <span data-ttu-id="d6c95-157">Несмотря на то, что пользователь тональность может быть ценным, он обеспечивает понимание, которое можно использовать для выявления потенциальных проблем.</span><span class="sxs-lookup"><span data-stu-id="d6c95-157">While user sentiment can be subjective, it does provide insight that can be used to identify potential issues.</span></span>

<span data-ttu-id="d6c95-158">В нижней таблице показан диапазон показателей для дня.</span><span class="sxs-lookup"><span data-stu-id="d6c95-158">The bottom table provides a range of metrics for the day.</span></span> <span data-ttu-id="d6c95-159">Слабые процентные значения и тарифы на сбои могут предоставить администратору потенциальные области улучшения.</span><span class="sxs-lookup"><span data-stu-id="d6c95-159">Poor percentages along with failure rates can provide an administrator with potential areas of improvement.</span></span> <span data-ttu-id="d6c95-160">Каждый час также можно выбрать отдельно, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="d6c95-160">Each hour can also be selected individually as shown below.</span></span>

<span data-ttu-id="d6c95-161">Эти данные можно использовать для определения регионов, в которых возникли проблемы во время пикового потребления.</span><span class="sxs-lookup"><span data-stu-id="d6c95-161">This data can be used to identify regions having problems during peak consumption times.</span></span>


<span data-ttu-id="d6c95-162">Щелкните столбец для этого дня, чтобы отобразить метрики за этот час.</span><span class="sxs-lookup"><span data-stu-id="d6c95-162">Click on the column for that day to display metrics for that hour.</span></span>
<span data-ttu-id="d6c95-163">![Снимок экрана: отчеты об использовании Teams](media/CQD-teams-utilization-report14.png)</span><span class="sxs-lookup"><span data-stu-id="d6c95-163">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report14.png)</span></span>
  
  1.  <span data-ttu-id="d6c95-164">В таблице под диаграммой отобразятся метрики за этот час.</span><span class="sxs-lookup"><span data-stu-id="d6c95-164">The table below the chart will display the metrics for that hour.</span></span> <span data-ttu-id="d6c95-165">Это можно сортировать по любому заголовку столбца; Тем не менее, мы будем заинтересованы в поиске проблемных областей.</span><span class="sxs-lookup"><span data-stu-id="d6c95-165">This can be sorted by any column header; however, we would be interested in finding problematic areas.</span></span>  
    ![Снимок экрана: отчеты об использовании Teams](media/CQD-teams-utilization-report15.png)
    
  2.  <span data-ttu-id="d6c95-167">Мы видим, что при этом в конференциях в течение этого времени область с изображением пропадает с низкой производительностью.</span><span class="sxs-lookup"><span data-stu-id="d6c95-167">We see that the IND region is experiencing poor video performance in conferences during this time frame.</span></span> <span data-ttu-id="d6c95-168">Впоследствии CQD QER Microsoft Reports можно использовать для сужения проблемного места, так как вы определили область "регион" и "время".</span><span class="sxs-lookup"><span data-stu-id="d6c95-168">Subsequently, the CQD QER Microsoft reports can be used to narrow down the problematic location as the region and time frame has been identified.</span></span>

### <a name="conference-details"></a><span data-ttu-id="d6c95-169">Сведения о Конференции</span><span class="sxs-lookup"><span data-stu-id="d6c95-169">Conference Details</span></span>

<span data-ttu-id="d6c95-170">Отчет о Конференции содержит дополнительные сведения о собраниях, в списке участников — на типы мультимедиа, используемые во время сеанса.</span><span class="sxs-lookup"><span data-stu-id="d6c95-170">The Conference Details report provides additional insight for meetings, from an attendee list, to the media types used during the session.</span></span>

<span data-ttu-id="d6c95-171">Щелкните правой кнопкой мыши Конференц-связь на диаграмме ИДЕНТИФИКАТОРов конференц-связи на странице ежедневного использования, чтобы детально просмотреть сведения о Конференции.</span><span class="sxs-lookup"><span data-stu-id="d6c95-171">Right click a conference the participant bar in the conference ID chart on the Daily usage page to drill down into the conference details.</span></span>

![Снимок экрана: отчеты об использовании Teams](media/CQD-teams-utilization-report24.png)

![Снимок экрана: отчеты об использовании Teams](media/CQD-teams-utilization-report25.png)
  

<span data-ttu-id="d6c95-174">Мы можем видеть участников конференции, а также всю необходимую информацию в отношении потери и колебаний пакетов, чтобы помочь в использовании потенциальных операций по устранению неполадок в нижней части таблицы.</span><span class="sxs-lookup"><span data-stu-id="d6c95-174">We can see the participants in the conference as well as all the pertinent information down to packet loss and jitter to assist with potential troubleshooting efforts in the bottom table.</span></span>

![Снимок экрана: отчеты об использовании Teams](media/CQD-teams-utilization-report26.png)


### <a name="regional-audio-details"></a><span data-ttu-id="d6c95-176">Региональные параметры звука</span><span class="sxs-lookup"><span data-stu-id="d6c95-176">Regional Audio Details</span></span>

<span data-ttu-id="d6c95-177">В разделе сведения о региональных звуках в конкретном разделе показано использование звуковых минут для выбранного региона.</span><span class="sxs-lookup"><span data-stu-id="d6c95-177">The Regional Audio Details drill down specifically shows the audio minute usage for the selected region.</span></span> <span data-ttu-id="d6c95-178">Пользователи, у которых есть доступ к CQD, могут просматривать тенденции использования как для P2P, так и для звука конференции в выбранной области.</span><span class="sxs-lookup"><span data-stu-id="d6c95-178">Users with access to CQD can see usage trends for both P2P and conference audio within the selected region.</span></span>

1.  <span data-ttu-id="d6c95-179">На странице "Сводка количества звонков" перейдите в раздел "определенный регион по таблице".</span><span class="sxs-lookup"><span data-stu-id="d6c95-179">On the Call Count Summary page, drill-through to as specific region through the table.</span></span>
  <span data-ttu-id="d6c95-180">![Снимок экрана: отчеты об использовании Teams](media/CQD-teams-utilization-report16.png)</span><span class="sxs-lookup"><span data-stu-id="d6c95-180">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report16.png)</span></span>

2.  <span data-ttu-id="d6c95-181">Выберите строку, для которой требуются дополнительные сведения о регионе.</span><span class="sxs-lookup"><span data-stu-id="d6c95-181">Select the row with the region additional information is needed for.</span></span>
  <span data-ttu-id="d6c95-182">![Снимок экрана: отчеты об использовании Teams](media/CQD-teams-utilization-report17.png)</span><span class="sxs-lookup"><span data-stu-id="d6c95-182">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report17.png)</span></span>

3.  <span data-ttu-id="d6c95-183">В тенденциях данных показано значительное количество минут, которые используются во внутренней сети, и конференц-связь значительно преходила за использование P2P.</span><span class="sxs-lookup"><span data-stu-id="d6c95-183">The data trends show a significant number of minutes being used on the internal network, with conferencing far surpassing P2P use.</span></span>
  <span data-ttu-id="d6c95-184">![Снимок экрана: отчеты об использовании Teams](media/CQD-teams-utilization-report18.png)</span><span class="sxs-lookup"><span data-stu-id="d6c95-184">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report18.png)</span></span>

<span data-ttu-id="d6c95-185">Региональная тенденция для звука может быть использована для того, чтобы показать влияние пользователей на внешний эффект в мире.</span><span class="sxs-lookup"><span data-stu-id="d6c95-185">The regional audio trend can be used to show how users are impacted by external influences in the world.</span></span> <span data-ttu-id="d6c95-186">В частности, мы бы хотели видеть внешнее использование в регионах EMEA и APAC, чтобы больше узнать о том, что пользователи должны работать удаленно.</span><span class="sxs-lookup"><span data-stu-id="d6c95-186">Specifically, right now, we would expect to see the external usage for the EMEA and APAC regions to increase with people being asked to work remotely.</span></span>


### <a name="user-list"></a><span data-ttu-id="d6c95-187">Список пользователей</span><span class="sxs-lookup"><span data-stu-id="d6c95-187">User List</span></span>

<span data-ttu-id="d6c95-188">Детализация списка пользователей — это ожидаемая информация, определенная пользователем за определенный час, выбранный пользователем, просматривающим отчет.</span><span class="sxs-lookup"><span data-stu-id="d6c95-188">The User List drill down provides, as one might expect, user specific information for a specific hour selected by the person viewing the report.</span></span> <span data-ttu-id="d6c95-189">Отчет о списке пользователей можно получить, выполняя детализацию на диаграмме "почасовые тенденции" в отчете "Ежедневный анализ".</span><span class="sxs-lookup"><span data-stu-id="d6c95-189">The User List report is accessible through a drill down in the Hourly Trends graph on the Daily Usage report.</span></span> <span data-ttu-id="d6c95-190">Щелкните правой кнопкой мыши часы, необходимые для получения дополнительных сведений, и выберите Детализация и список пользователей, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="d6c95-190">Right click on the hour additional information is needed for and select Drill through and User List, as shown below.</span></span>

![Снимок экрана: отчеты об использовании Teams](media/CQD-teams-utilization-report19.png)

<span data-ttu-id="d6c95-192">В отчете список пользователей отображается внутреннее и внешнее подключение через кольцевую диаграмму в центре верхнего края страницы.</span><span class="sxs-lookup"><span data-stu-id="d6c95-192">The User List report shows internal/external connectivity through the doughnut chart in the top center of the page.</span></span> <span data-ttu-id="d6c95-193">Мы можем видеть, что в приведенном ниже изображении есть большое количество участников, находящихся за пределами корпоративной сети.</span><span class="sxs-lookup"><span data-stu-id="d6c95-193">We can see that there is a large amount of participation from Outside the corporate network in the below image.</span></span>

<span data-ttu-id="d6c95-194">В правом верхнем углу графика показано количество звонков, выполненных каждым пользователем в течение часа.</span><span class="sxs-lookup"><span data-stu-id="d6c95-194">The top right of the graph shows the number of calls made by each user within that hour.</span></span>

![Снимок экрана: отчеты об использовании Teams](media/CQD-teams-utilization-report20.png)

<span data-ttu-id="d6c95-196">В нижней таблице приведены подробные сведения о сеансах, в которых участвовали пользователи в течение этого часа.</span><span class="sxs-lookup"><span data-stu-id="d6c95-196">The bottom table provides detailed information for the sessions each user participated in during that hour.</span></span> <span data-ttu-id="d6c95-197">Столбец "тип сбоя" полезен при определении того, что вызвало удаление звонка.</span><span class="sxs-lookup"><span data-stu-id="d6c95-197">The Failure Type column is useful in determining what caused a call to drop.</span></span> <span data-ttu-id="d6c95-198">Столбцы «захват» и «рендеринг» полезны для определения причины, по которой во время звонка возникло низкое качество.</span><span class="sxs-lookup"><span data-stu-id="d6c95-198">The Capture and Render Device columns are useful in identifying why a call was reported having poor quality.</span></span>


## <a name="related-topics"></a><span data-ttu-id="d6c95-199">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="d6c95-199">Related topics</span></span>

[<span data-ttu-id="d6c95-200">Измерения и меры на панели мониторинга качества звонков</span><span class="sxs-lookup"><span data-stu-id="d6c95-200">Dimensions and measures available in Call Quality Dashboard</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="d6c95-201">Классификация потоков на панели мониторинга качества звонков</span><span class="sxs-lookup"><span data-stu-id="d6c95-201">Stream Classification in Call Quality Dashboard</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="d6c95-202">Настройка средства аналитики звонков в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="d6c95-202">Set up Skype for Business Call Analytics</span></span>](set-up-call-analytics.md)

[<span data-ttu-id="d6c95-203">Использование аналитики звонков для устранения проблем с качеством звонка</span><span class="sxs-lookup"><span data-stu-id="d6c95-203">Use Call Analytics to troubleshoot poor call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[<span data-ttu-id="d6c95-204">Аналитика звонков и панель мониторинга качества звонков</span><span class="sxs-lookup"><span data-stu-id="d6c95-204">Call Analytics and Call Quality Dashboard</span></span>](difference-between-call-analytics-and-call-quality-dashboard.md)

[<span data-ttu-id="d6c95-205">Устранение неполадок Teams</span><span class="sxs-lookup"><span data-stu-id="d6c95-205">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)
 