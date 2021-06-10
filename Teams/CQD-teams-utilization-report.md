---
title: Просмотр Microsoft Teams использования в Power BI данных CQD
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
description: Используйте отчеты Teams использование Power BI для доступа к данным панели мониторинга качества Microsoft Teams (CQD) для отслеживания Microsoft Teams использования в организации.
ms.openlocfilehash: 719f02ce7a5cd36e96ed7fd563c259c6e77764fd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095043"
---
# <a name="view-microsoft-teams-utilization-in-power-bi-using-cqd-data"></a><span data-ttu-id="612cd-103">Просмотр Microsoft Teams использования в Power BI данных CQD</span><span class="sxs-lookup"><span data-stu-id="612cd-103">View Microsoft Teams utilization in Power BI using CQD data</span></span>

<span data-ttu-id="612cd-104">В марте 2020 г. мы добавили отчет об использовании Teams в шаблоны запросов Power BI [CQD.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="612cd-104">New in March 2020, we've added a Teams Utilization report to our downloadable [Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> 

<span data-ttu-id="612cd-105">Эти новые Teams использования позволяют узнать, как (и в какой степени) пользователи используют Microsoft Teams, используя данные Teams панели мониторинга качества звонка (CQD).</span><span class="sxs-lookup"><span data-stu-id="612cd-105">This new Teams Utilization reports lets you see how (and how much) your users are using Microsoft Teams by accessing Teams Call Quality Dashboard (CQD) data.</span></span> <span data-ttu-id="612cd-106">Эти отчеты предназначены для централизованного использования этих данных как администраторами, так и руководителями предприятий.</span><span class="sxs-lookup"><span data-stu-id="612cd-106">These reports are intended to be a centralized location that both administrators and business leaders can quickly go to for this data.</span></span>

<span data-ttu-id="612cd-107">Отчет Teams использование Power BI состоит из двух основных отчетов: **[](#call-count-summary-report)** "Сводка по подсчету вызовов" и "Сводка по звуковому **[протоколу".](#audio-minutes-summary-report)**</span><span class="sxs-lookup"><span data-stu-id="612cd-107">The Teams Utilization Power BI report consists of two primary reports: **[Call Count Summary](#call-count-summary-report)** and **[Audio Minutes Summary](#audio-minutes-summary-report)**.</span></span> <span data-ttu-id="612cd-108">Отчеты [Ежедневное](#daily-usage) [использование,](#regional-audio-details)Сведения [](#user-list) о региональных аудиофайлах, Сведения о конференции и Список пользователей вступает в силу, когда пользователь получает возможность воспользоваться отчетами для детали, которые описаны в описании ниже. [](#conference-details)</span><span class="sxs-lookup"><span data-stu-id="612cd-108">The [Daily Usage](#daily-usage), [Regional Audio Details](#regional-audio-details), [Conference Details](#conference-details) and [User List](#user-list) reports come into play when a user takes advantage of the drill-down reports, noted in the descriptions below.</span></span>

> [!NOTE]
> <span data-ttu-id="612cd-109">Чтобы обеспечить возможности фильтрации по регионам и сетям, необходимо заполнить данные здания и подсети.</span><span class="sxs-lookup"><span data-stu-id="612cd-109">Building and subnet data must be populated to provide regional and network filtering capabilities.</span></span>

## <a name="call-count-summary-report"></a><span data-ttu-id="612cd-110">Сводный отчет по подсчету вызовов</span><span class="sxs-lookup"><span data-stu-id="612cd-110">Call Count Summary Report</span></span>

<span data-ttu-id="612cd-111">На главной странице (Сводка по подсчету вызовов) сразу же выведется количество сеансов общего доступа к аудио- и видеофайлам и экрану за последние 30 и 90 дней, как отмечено в разделе.</span><span class="sxs-lookup"><span data-stu-id="612cd-111">The main page (Call Count Summary) immediately provides the number of audio, video and screen sharing sessions over the last 30 and 90 days as noted in the section title.</span></span> <span data-ttu-id="612cd-112">Изначально отображаемая информация используется для всей организации и может быть отфильтрованной с помощью параметров среза в левой части страницы.</span><span class="sxs-lookup"><span data-stu-id="612cd-112">The data initially displayed is for the organization as a whole and can be filtered using the slicer dropdown options on the left side of the page.</span></span>

![Снимок экрана: Teams отчеты об использовании](media/CQD-teams-utilization-report1.png)

1. <span data-ttu-id="612cd-114">Справа от срезов количество звонков по типам мультимедиа разбито на внутреннее или внешнее представление за последние 30 дней.</span><span class="sxs-lookup"><span data-stu-id="612cd-114">To the right of the slicer dropdowns, the number of calls by media type is broken down to an internal/external view over the past thirty days.</span></span> <span data-ttu-id="612cd-115">На снимке экрана выше видно, что в организации происходит больше звонков из-за пределов организации, что имеет смысл с учетом текущей глобальной среды.</span><span class="sxs-lookup"><span data-stu-id="612cd-115">We can see through the above screenshot that there are more calls happening from outside organizational locations, which makes sense considering the current global environment.</span></span>
  <span data-ttu-id="612cd-116">![Снимок экрана: отчеты Teams использования](media/CQD-teams-utilization-report2.png)</span><span class="sxs-lookup"><span data-stu-id="612cd-116">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report2.png)</span></span>

1. <span data-ttu-id="612cd-117">Справа от окна "Количество типов мультимедиа" имеется ежемесячный подсчет звонка по типу мультимедиа за последние 90 дней.</span><span class="sxs-lookup"><span data-stu-id="612cd-117">To the right of the media type count box, we have the Monthly Call Count by Media Type for the last 90 days.</span></span> <span data-ttu-id="612cd-118">На каждый столбец и тип мультимедиа можно навести курсор, чтобы отобразить количество за предыдущий или текущий месяц с информацией о тенденциях использования.</span><span class="sxs-lookup"><span data-stu-id="612cd-118">Each column and media type can be hovered over to display the count for a previous month or the current month to date, providing usage trend information.</span></span>
  <span data-ttu-id="612cd-119">![Снимок экрана: отчеты Teams использования](media/CQD-teams-utilization-report3.png)</span><span class="sxs-lookup"><span data-stu-id="612cd-119">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report3.png)</span></span>
 

1. <span data-ttu-id="612cd-120">Средний график работает так же, как и 90-дневный график, но предоставляет представление ежедневного использования за последние 30 дней и позволяет пользователю щелкнуть правой кнопкой мыши и деталидировать детали для определенного дня.</span><span class="sxs-lookup"><span data-stu-id="612cd-120">The middle graph functions as the 90-day graph does, however it provides a daily usage view for the past 30 days and allows a user to right click and drill down into details for a specific day.</span></span>
  <span data-ttu-id="612cd-121">![Снимок экрана: отчеты Teams использования](media/CQD-teams-utilization-report4.png)</span><span class="sxs-lookup"><span data-stu-id="612cd-121">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report4.png)</span></span>

<span data-ttu-id="612cd-122">В левом нижнем разделе страницы вы найдете таблицу с итогами для каждого типа мультимедиа за последний год.</span><span class="sxs-lookup"><span data-stu-id="612cd-122">On the bottom left section of the page, you'll find a table providing total values for each media type over the past year.</span></span> 
    <span data-ttu-id="612cd-123">![Снимок экрана: Teams отчетов об ](media/CQD-teams-utilization-report5.png) ![ использовании: Teams по использованию](media/CQD-teams-utilization-report6.png)</span><span class="sxs-lookup"><span data-stu-id="612cd-123">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report5.png) ![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report6.png)</span></span>   

<span data-ttu-id="612cd-124">Справа от таблицы на линих диаграмме показаны клиенты с наиболее часто используемой (звонками и потоками) за последние 30 дней.</span><span class="sxs-lookup"><span data-stu-id="612cd-124">To the right of the table, a bar chart shows clients with the most use (calls/streams) for the past 30 days.</span></span>
   <span data-ttu-id="612cd-125">![Снимок экрана: отчеты Teams использования](media/CQD-teams-utilization-report7.png)</span><span class="sxs-lookup"><span data-stu-id="612cd-125">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report7.png)</span></span>

<span data-ttu-id="612cd-126">В последнем наборе диаграмм для этой страницы каждый тип мультимедиа отображается по отдельности с разбивкой по конференциям и использованию P2P.</span><span class="sxs-lookup"><span data-stu-id="612cd-126">The last set of charts for this page show each media type individually, with a breakdown showing conference and P2P usage.</span></span> <span data-ttu-id="612cd-127">На диаграммах ниже по сравнению с P2P-данными было значительно больше конференций.</span><span class="sxs-lookup"><span data-stu-id="612cd-127">The charts below show that there is a significantly higher number of conference usage as compared to P2P.</span></span>
  <span data-ttu-id="612cd-128">![Снимок экрана: отчеты Teams использования](media/CQD-teams-utilization-report8.png)</span><span class="sxs-lookup"><span data-stu-id="612cd-128">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report8.png)</span></span>

## <a name="audio-minutes-summary-report"></a><span data-ttu-id="612cd-129">Сводный отчет о минутах аудиосвязи</span><span class="sxs-lookup"><span data-stu-id="612cd-129">Audio Minutes Summary Report</span></span>

<span data-ttu-id="612cd-130">В отчете Использование аудиосвязи минут общее использование минут предоставляется в нескольких различных представлениях.</span><span class="sxs-lookup"><span data-stu-id="612cd-130">On the Audio Minutes usage report, the total minute usage is provided through a few different views.</span></span> 

<span data-ttu-id="612cd-131">Рядом с срезами отображается 30-дневная сводка по использованию текстовых полей.</span><span class="sxs-lookup"><span data-stu-id="612cd-131">We have the thirty-day usage summary shown next to the slicers as easy to consume text boxes.</span></span> <span data-ttu-id="612cd-132">Верхнее число — это итоговая 30-дневная с внутренними и внешними разбивками.</span><span class="sxs-lookup"><span data-stu-id="612cd-132">The top number shows the thirty-day total, with internal and external breakdowns below that.</span></span>

![Снимок экрана: Teams отчеты об использовании](media/CQD-teams-utilization-report9.png)

<span data-ttu-id="612cd-134">На правом верхнем графике можно просмотреть аудиоконференции на год.</span><span class="sxs-lookup"><span data-stu-id="612cd-134">The top right bar graph provides a yearlong view of conference audio usage.</span></span> <span data-ttu-id="612cd-135">Наведите курсор на месяц, чтобы показать минуты аудиоконференции.</span><span class="sxs-lookup"><span data-stu-id="612cd-135">Hover over the month to show the conference audio minutes.</span></span>

<span data-ttu-id="612cd-136">Чтобы показать разницу в P2P и аудиоконференции, на нижней левой диаграмме берется весь звук за последний год и он разбивается между двумя типами.</span><span class="sxs-lookup"><span data-stu-id="612cd-136">To show the difference in P2P and conference audio, the bottom left chart takes all audio for the past year and breaks it up between the two types.</span></span>

![Снимок экрана: Teams отчеты об использовании](media/CQD-teams-utilization-report10.png)

<span data-ttu-id="612cd-138">На последней диаграмме на странице Минуты звука показано использование минут на глобальной карте.</span><span class="sxs-lookup"><span data-stu-id="612cd-138">The last chart for the Audio minutes page shows audio minute usage on a global map overlay.</span></span> <span data-ttu-id="612cd-139">Эта диаграмма будет работать только при отправке данных о здании и подсети в клиент.</span><span class="sxs-lookup"><span data-stu-id="612cd-139">This chart will only work if building and subnet data is uploaded to the tenant.</span></span> <span data-ttu-id="612cd-140">Круговую диаграмму на карте можно обрезать, что впоследствии обеспечивает использование регионального звука.</span><span class="sxs-lookup"><span data-stu-id="612cd-140">The pie chart overlay on the map can be drilled into, subsequently providing regional audio usage.</span></span>

![Снимок экрана: Teams отчеты об использовании](media/CQD-teams-utilization-report11.png)


## <a name="drill-through-capabilities"></a><span data-ttu-id="612cd-142">Возможности drill-through</span><span class="sxs-lookup"><span data-stu-id="612cd-142">Drill-through capabilities</span></span>

<span data-ttu-id="612cd-143">Как уже было отмечено, пользователи могут использовать отчеты о ежедневном и региональном использовании.</span><span class="sxs-lookup"><span data-stu-id="612cd-143">As previously noted, users can drill into the daily and regional usage reports.</span></span>

### <a name="daily-usage"></a><span data-ttu-id="612cd-144">Ежедневное использование</span><span class="sxs-lookup"><span data-stu-id="612cd-144">Daily Usage</span></span>

<span data-ttu-id="612cd-145">Отчет о ежедневном использовании позволяет администратору определять пиковые периоды потребления в течение суток.</span><span class="sxs-lookup"><span data-stu-id="612cd-145">The Daily Usage report allows an administrator to identify peak consumption periods through the course of a day.</span></span> <span data-ttu-id="612cd-146">В дополнение к использованию, мы также можем получить общее мнение пользователей и отзывы за этот день.</span><span class="sxs-lookup"><span data-stu-id="612cd-146">In addition to usage, we are also able to capture overall user sentiment and feedback for that day.</span></span>

![Снимок экрана: Teams отчеты об использовании](media/CQD-teams-utilization-report12.png)

<span data-ttu-id="612cd-148">В отчете Ежедневное использование отображается количество звуковых, видео- и экранных ресурсов для выбранного дня с добавленной возможностью различать внутреннее и внешнее подключение.</span><span class="sxs-lookup"><span data-stu-id="612cd-148">The Daily usage report displays the number of Audio, Video and Screen shares for the selected day with the added ability to differentiate between internal and external connectivity.</span></span> <span data-ttu-id="612cd-149">Разбивка по конференциям и одноранговой разбивке находится справа от итога модали.</span><span class="sxs-lookup"><span data-stu-id="612cd-149">A Conference and Peer to Peer breakdown is to the immediate right of the modality total box.</span></span> <span data-ttu-id="612cd-150">В правой верхней части отчета справа от нее содержится список конференций с их связанными ИД и участниками на день.</span><span class="sxs-lookup"><span data-stu-id="612cd-150">The top right of the report provides a list of conferences with their associated ID and participants for the day.</span></span> <span data-ttu-id="612cd-151">Список конференций также содержит дополнительные сведения о конференции.</span><span class="sxs-lookup"><span data-stu-id="612cd-151">The conference list provides an additional drill down to the Conference Details report as well.</span></span> <span data-ttu-id="612cd-152">РИСУНОК "ЗАМЕНИТЬ"</span><span class="sxs-lookup"><span data-stu-id="612cd-152">REPLACE GRAPHIC</span></span>

![Снимок экрана: Teams отчеты об использовании](media/CQD-teams-utilization-report13.png)

<span data-ttu-id="612cd-154">График в центральной области позволяет пользователю определять пиковые периоды потребления в течение суток.</span><span class="sxs-lookup"><span data-stu-id="612cd-154">The bar graph in the center area allows the user to identify peak consumption periods through the course of a day.</span></span> <span data-ttu-id="612cd-155">Пользователи могут просуммировать час, представленный на графике, в котором будет представлен отчет о списке пользователей за час.</span><span class="sxs-lookup"><span data-stu-id="612cd-155">Users may drill down into the hour represented on the graph which will present the User List report for the hour.</span></span>

<span data-ttu-id="612cd-156">Справа от гограммы отзывы пользователей представлены в визуальном формате.</span><span class="sxs-lookup"><span data-stu-id="612cd-156">To the right of the bar graph, User Feedback is presented in a visual format.</span></span> <span data-ttu-id="612cd-157">Хотя такие идеи могут быть неохожна, они предоставляют информацию, которая может использоваться для выявления потенциальных проблем.</span><span class="sxs-lookup"><span data-stu-id="612cd-157">While user sentiment can be subjective, it does provide insight that can be used to identify potential issues.</span></span>

<span data-ttu-id="612cd-158">В нижней таблице содержится диапазон метрик на день.</span><span class="sxs-lookup"><span data-stu-id="612cd-158">The bottom table provides a range of metrics for the day.</span></span> <span data-ttu-id="612cd-159">Неудовлетворительные процентные показатели и коэффициенты сбоев могут помочь администратору в улучшении.</span><span class="sxs-lookup"><span data-stu-id="612cd-159">Poor percentages along with failure rates can provide an administrator with potential areas of improvement.</span></span> <span data-ttu-id="612cd-160">Каждый час также можно выбрать по отдельности, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="612cd-160">Each hour can also be selected individually as shown below.</span></span>

<span data-ttu-id="612cd-161">Эти данные можно использовать для определения регионов, в которые возникают проблемы во время пикового потребления.</span><span class="sxs-lookup"><span data-stu-id="612cd-161">This data can be used to identify regions having problems during peak consumption times.</span></span>


<span data-ttu-id="612cd-162">Щелкните столбец для этого дня, чтобы отобразить показатели за этот час.</span><span class="sxs-lookup"><span data-stu-id="612cd-162">Click on the column for that day to display metrics for that hour.</span></span>
<span data-ttu-id="612cd-163">![Снимок экрана: отчеты Teams использования](media/CQD-teams-utilization-report14.png)</span><span class="sxs-lookup"><span data-stu-id="612cd-163">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report14.png)</span></span>
  
  1.  <span data-ttu-id="612cd-164">В таблице под диаграммой будут показаны показатели за этот час.</span><span class="sxs-lookup"><span data-stu-id="612cd-164">The table below the chart will display the metrics for that hour.</span></span> <span data-ttu-id="612cd-165">Его можно отсортировать по любому заглавию столбца. однако мы хотели бы найти проблемные области.</span><span class="sxs-lookup"><span data-stu-id="612cd-165">This can be sorted by any column header; however, we would be interested in finding problematic areas.</span></span>  
    ![Снимок экрана: Teams отчеты об использовании](media/CQD-teams-utilization-report15.png)
    
  2.  <span data-ttu-id="612cd-167">Мы видим, что в регионе IND наблюдается низкая производительность видео в конференциях в течение этого времени.</span><span class="sxs-lookup"><span data-stu-id="612cd-167">We see that the IND region is experiencing poor video performance in conferences during this time frame.</span></span> <span data-ttu-id="612cd-168">Впоследствии отчеты Корпорации Майкрософт QQD QER можно использовать для сужение проблемного расположения по мере определения региона и задаваемой период времени.</span><span class="sxs-lookup"><span data-stu-id="612cd-168">Subsequently, the CQD QER Microsoft reports can be used to narrow down the problematic location as the region and time frame has been identified.</span></span>

### <a name="conference-details"></a><span data-ttu-id="612cd-169">Сведения о конференции</span><span class="sxs-lookup"><span data-stu-id="612cd-169">Conference Details</span></span>

<span data-ttu-id="612cd-170">Отчет "Сведения о конференции" содержит дополнительные сведения о собраниях ( от списка участников до типов мультимедиа, используемых во время сеанса).</span><span class="sxs-lookup"><span data-stu-id="612cd-170">The Conference Details report provides additional insight for meetings, from an attendee list, to the media types used during the session.</span></span>

<span data-ttu-id="612cd-171">Щелкните правой кнопкой мыши конференцию в диаграмме "Код конференции" на странице Ежедневное использование, чтобы деталижать сведения о конференции.</span><span class="sxs-lookup"><span data-stu-id="612cd-171">Right click a conference the participant bar in the conference ID chart on the Daily usage page to drill down into the conference details.</span></span>

![Снимок экрана: Teams отчеты об использовании](media/CQD-teams-utilization-report24.png)

![Снимок экрана: Teams отчеты об использовании](media/CQD-teams-utilization-report25.png)
  

<span data-ttu-id="612cd-174">Мы можем видеть участников конференции, а также всю информацию в зависимости от потери пакетов и дрожания для устранения возможных неполадок в нижней таблице.</span><span class="sxs-lookup"><span data-stu-id="612cd-174">We can see the participants in the conference as well as all the pertinent information down to packet loss and jitter to assist with potential troubleshooting efforts in the bottom table.</span></span>

![Снимок экрана: Teams отчеты об использовании](media/CQD-teams-utilization-report26.png)


### <a name="regional-audio-details"></a><span data-ttu-id="612cd-176">Сведения о региональных аудиофайлах</span><span class="sxs-lookup"><span data-stu-id="612cd-176">Regional Audio Details</span></span>

<span data-ttu-id="612cd-177">Подробные сведения о региональных аудиозаписях специально показывают использование минут на звук для выбранного региона.</span><span class="sxs-lookup"><span data-stu-id="612cd-177">The Regional Audio Details drill down specifically shows the audio minute usage for the selected region.</span></span> <span data-ttu-id="612cd-178">Пользователи с доступом к CQD могут видеть тенденции использования P2P-и аудиоконференции в выбранном регионе.</span><span class="sxs-lookup"><span data-stu-id="612cd-178">Users with access to CQD can see usage trends for both P2P and conference audio within the selected region.</span></span>

1.  <span data-ttu-id="612cd-179">На странице Сводка по подсчету вызовов пролили в таблицу по определенному региону.</span><span class="sxs-lookup"><span data-stu-id="612cd-179">On the Call Count Summary page, drill-through to as specific region through the table.</span></span>
  <span data-ttu-id="612cd-180">![Снимок экрана: отчеты Teams использования](media/CQD-teams-utilization-report16.png)</span><span class="sxs-lookup"><span data-stu-id="612cd-180">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report16.png)</span></span>

2.  <span data-ttu-id="612cd-181">Вы можете выбрать строку с областью, для которую необходимы дополнительные сведения.</span><span class="sxs-lookup"><span data-stu-id="612cd-181">Select the row with the region additional information is needed for.</span></span>
  <span data-ttu-id="612cd-182">![Снимок экрана: отчеты Teams использования](media/CQD-teams-utilization-report17.png)</span><span class="sxs-lookup"><span data-stu-id="612cd-182">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report17.png)</span></span>

3.  <span data-ttu-id="612cd-183">Тенденции изменения данных показывают значительное количество минут, используемых во внутренней сети, при этом использование P2P-2P значительно ухудшено.</span><span class="sxs-lookup"><span data-stu-id="612cd-183">The data trends show a significant number of minutes being used on the internal network, with conferencing far surpassing P2P use.</span></span>
  <span data-ttu-id="612cd-184">![Снимок экрана: отчеты Teams использования](media/CQD-teams-utilization-report18.png)</span><span class="sxs-lookup"><span data-stu-id="612cd-184">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report18.png)</span></span>

<span data-ttu-id="612cd-185">Региональные тенденции аудиосвязи можно использовать для демонстрации влияния внешних факторов на пользователей в мире.</span><span class="sxs-lookup"><span data-stu-id="612cd-185">The regional audio trend can be used to show how users are impacted by external influences in the world.</span></span> <span data-ttu-id="612cd-186">В частности, в настоящее время мы ожидаем, что внешний уровень использования регионов EMEA и APAC увеличится, и людям будет предложено работать удаленно.</span><span class="sxs-lookup"><span data-stu-id="612cd-186">Specifically, right now, we would expect to see the external usage for the EMEA and APAC regions to increase with people being asked to work remotely.</span></span>


### <a name="user-list"></a><span data-ttu-id="612cd-187">Список пользователей</span><span class="sxs-lookup"><span data-stu-id="612cd-187">User List</span></span>

<span data-ttu-id="612cd-188">В списке пользователей можно просмотреть сведения о пользователях за определенный час, выбранные пользователем, просматривая отчет.</span><span class="sxs-lookup"><span data-stu-id="612cd-188">The User List drill down provides, as one might expect, user specific information for a specific hour selected by the person viewing the report.</span></span> <span data-ttu-id="612cd-189">Отчет Список пользователей доступен с помощью drill down (Почасовая диаграмма тенденций) в отчете Ежедневное использование.</span><span class="sxs-lookup"><span data-stu-id="612cd-189">The User List report is accessible through a drill down in the Hourly Trends graph on the Daily Usage report.</span></span> <span data-ttu-id="612cd-190">Щелкните правой кнопкой мыши час, когда потребуется дополнительная информация, и выберите развернуть и список пользователей, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="612cd-190">Right click on the hour additional information is needed for and select Drill through and User List, as shown below.</span></span>

![Снимок экрана: Teams отчеты об использовании](media/CQD-teams-utilization-report19.png)

<span data-ttu-id="612cd-192">В отчете Список пользователей показано внутреннее и внешнее подключение через кольцевую диаграмму в центре верхней части страницы.</span><span class="sxs-lookup"><span data-stu-id="612cd-192">The User List report shows internal/external connectivity through the doughnut chart in the top center of the page.</span></span> <span data-ttu-id="612cd-193">На приведенной ниже картинке видно, что за пределами корпоративной сети имеется большое количество участников.</span><span class="sxs-lookup"><span data-stu-id="612cd-193">We can see that there is a large amount of participation from Outside the corporate network in the below image.</span></span>

<span data-ttu-id="612cd-194">В правом верхнем верхнем конце графика показано количество звонков, сделанных каждым пользователем в течение часа.</span><span class="sxs-lookup"><span data-stu-id="612cd-194">The top right of the graph shows the number of calls made by each user within that hour.</span></span>

![Снимок экрана: Teams отчеты об использовании](media/CQD-teams-utilization-report20.png)

<span data-ttu-id="612cd-196">В нижней таблице содержится подробная информация о сеансах, в которых участвовал каждый пользователь в течение этого часа.</span><span class="sxs-lookup"><span data-stu-id="612cd-196">The bottom table provides detailed information for the sessions each user participated in during that hour.</span></span> <span data-ttu-id="612cd-197">Столбец Тип сбоя удобен для определения причин перепада звонка.</span><span class="sxs-lookup"><span data-stu-id="612cd-197">The Failure Type column is useful in determining what caused a call to drop.</span></span> <span data-ttu-id="612cd-198">Столбцы "Захват" и "Отрисовка устройства" удобна для определения причин неудовлетворительнго качества звонка.</span><span class="sxs-lookup"><span data-stu-id="612cd-198">The Capture and Render Device columns are useful in identifying why a call was reported having poor quality.</span></span>


## <a name="related-topics"></a><span data-ttu-id="612cd-199">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="612cd-199">Related topics</span></span>

[<span data-ttu-id="612cd-200">Измерения и меры на панели мониторинга качества звонков</span><span class="sxs-lookup"><span data-stu-id="612cd-200">Dimensions and measures available in Call Quality Dashboard</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="612cd-201">Классификация потоков на панели мониторинга качества звонков</span><span class="sxs-lookup"><span data-stu-id="612cd-201">Stream Classification in Call Quality Dashboard</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="612cd-202">Настройка средства аналитики звонков в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="612cd-202">Set up Skype for Business Call Analytics</span></span>](set-up-call-analytics.md)

[<span data-ttu-id="612cd-203">Использование аналитики звонков для устранения проблем с качеством звонка</span><span class="sxs-lookup"><span data-stu-id="612cd-203">Use Call Analytics to troubleshoot poor call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[<span data-ttu-id="612cd-204">Аналитика звонков и панель мониторинга качества звонков</span><span class="sxs-lookup"><span data-stu-id="612cd-204">Call Analytics and Call Quality Dashboard</span></span>](./monitor-call-quality-qos.md)

[<span data-ttu-id="612cd-205">Устранение неполадок Teams</span><span class="sxs-lookup"><span data-stu-id="612cd-205">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)
