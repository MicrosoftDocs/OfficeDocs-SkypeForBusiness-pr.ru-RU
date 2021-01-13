---
title: Примеры разработки CQD
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 8ca9bf7a-2d6f-48d5-a821-531009726525
description: Сводка. Обзор учебника и примеров разработки для панели мониторинга качества вызовов. Панель мониторинга качества звонков — это инструмент для Skype для бизнеса Server.
ms.openlocfilehash: 193a03662d6f771b19c57017d909cc6574a755ef
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832729"
---
# <a name="cqd-development-samples"></a><span data-ttu-id="94da7-104">Примеры разработки CQD</span><span class="sxs-lookup"><span data-stu-id="94da7-104">CQD Development Samples</span></span>

<span data-ttu-id="94da7-105">**Сводка:** Просмотрите учебник и примеры разработки для панели мониторинга качества вызовов.</span><span class="sxs-lookup"><span data-stu-id="94da7-105">**Summary:** Review a tutorial and development samples for Call Quality Dashboard.</span></span> <span data-ttu-id="94da7-106">Панель мониторинга качества звонков — это инструмент для Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="94da7-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>

<span data-ttu-id="94da7-107">В этой статье приводится учебник и примеры по разработке панели мониторинга качества вызовов (CQD).</span><span class="sxs-lookup"><span data-stu-id="94da7-107">This article provides a tutorial and samples on development for Call Quality Dashboard (CQD).</span></span>

## <a name="call-quality-dashboard-cqd-development-samples"></a><span data-ttu-id="94da7-108">Примеры разработки панели мониторинга качества вызовов (CQD)</span><span class="sxs-lookup"><span data-stu-id="94da7-108">Call Quality Dashboard (CQD) Development Samples</span></span>

<span data-ttu-id="94da7-109">Учебник. Создание настраиваемой презентации отчета с помощью API службы данных и репозитория CQD.</span><span class="sxs-lookup"><span data-stu-id="94da7-109">Tutorial: Building Customized Report Presentation using the CQD Data Service and Repository Service API's.</span></span>

### <a name="introduction-to-cqd"></a><span data-ttu-id="94da7-110">Введение в CQD</span><span class="sxs-lookup"><span data-stu-id="94da7-110">Introduction to CQD</span></span>

<span data-ttu-id="94da7-111">CQD обеспечивает быстрый и простой доступ к сводной информации о качестве звонков для локального развертывания Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="94da7-111">CQD offers quick and easy access to aggregated call quality information for on-premise Skype for Business Server deployments.</span></span> <span data-ttu-id="94da7-112">CQD состоит из трех компонентов: базы данных архива QoE, куба и портала.</span><span class="sxs-lookup"><span data-stu-id="94da7-112">CQD consists of three components: the QoE Archive database, the Cube, and the Portal.</span></span> <span data-ttu-id="94da7-113">Портал — это основной уровень представления, который можно разделить на три следующих компонента:</span><span class="sxs-lookup"><span data-stu-id="94da7-113">The Portal is the main presentation layer and can be further divided into the following three components:</span></span>

1. <span data-ttu-id="94da7-114">Data Service, which is accessible for authenticated users through the [Data API for Call Quality Dashboard (CQD) in Skype for Business Server](data-api.md).</span><span class="sxs-lookup"><span data-stu-id="94da7-114">Data Service, which is accessible for authenticated users through the [Data API for Call Quality Dashboard (CQD) in Skype for Business Server](data-api.md).</span></span>

2. <span data-ttu-id="94da7-115">Служба репозитория, доступная для пользователей, подлинность которых прошла через API репозитория для панели мониторинга качества звонков [(CQD) в Skype для бизнеса Server.](repository-api.md)</span><span class="sxs-lookup"><span data-stu-id="94da7-115">Repository Service, which is accessible for authenticated users through the [Repository API for Call Quality Dashboard (CQD) in Skype for Business Server](repository-api.md).</span></span>

3. <span data-ttu-id="94da7-116">Веб-портал, который является интерфейсом на основе HTML5, с которым пользователи CQD видят и взаимодействуют.</span><span class="sxs-lookup"><span data-stu-id="94da7-116">Web portal, which is the HTML5 based interface that CQD users see and interact with.</span></span> <span data-ttu-id="94da7-117">Эта возможность доступна для пользователей, подлинность в которые недоступна.</span><span class="sxs-lookup"><span data-stu-id="94da7-117">This is accessible for authenticated users.</span></span>

<span data-ttu-id="94da7-118">Отчеты, показанные на веб-портале, группются в "наборы отчетов".</span><span class="sxs-lookup"><span data-stu-id="94da7-118">The reports shown on the web portal are grouped into "report sets".</span></span> <span data-ttu-id="94da7-119">На рисунке показан набор отчетов с двумя отчетами.</span><span class="sxs-lookup"><span data-stu-id="94da7-119">The figure shows a report set with two reports.</span></span> <span data-ttu-id="94da7-120">В каждом отчете на приведенной ниже информационной панели показаны результаты запроса по количеству звонков низкого качества и процента звонков низкого качества в течение нескольких месяцев, при этом применяются различные фильтры.</span><span class="sxs-lookup"><span data-stu-id="94da7-120">Each report in this dashboard below shows query results on number of good calls, poor calls and poor call percentage for several months, with various filters applied.</span></span> 

![Пример отчета CQD](../../media/9e0723f7-f850-4d11-9ecd-7e8e013a8bed.png)

<span data-ttu-id="94da7-122">CQD создается в соответствии с методологией качества вызовов (CQM), поэтому набор отчетов по умолчанию разработан в соответствии с потоком исследования, введенным CQM.</span><span class="sxs-lookup"><span data-stu-id="94da7-122">CQD is created following the Call Quality Methodology (CQM), so the default set of reports is designed to align with the investigation flow introduced by CQM.</span></span> <span data-ttu-id="94da7-123">Пользователи также могут редактировать или создавать настраиваемые отчеты в своих потребностях.</span><span class="sxs-lookup"><span data-stu-id="94da7-123">Users also have the flexibility to edit or create custom reports to meet their needs.</span></span> <span data-ttu-id="94da7-124">Тем не менее, поскольку существует несколько способов визуализации данных, визуализация, предоставляемая CQD, может не полностью решить потребности каждого пользователя.</span><span class="sxs-lookup"><span data-stu-id="94da7-124">However, since there are multiple ways to visualize the data, the visualization provided by CQD may not fully address the needs of every user.</span></span> <span data-ttu-id="94da7-125">В таких случаях пользователь может использовать API данных и API репозитория для создания пользовательских страниц отчетов.</span><span class="sxs-lookup"><span data-stu-id="94da7-125">In such situations, a user can leverage the Data APIs and Repository APIs to create custom report pages.</span></span> <span data-ttu-id="94da7-126">В этом руководстве мы проймем ряд примеров.</span><span class="sxs-lookup"><span data-stu-id="94da7-126">We will go through a series of examples in this tutorial.</span></span>

### <a name="how-the-dashboard-consumes-the-data-service"></a><span data-ttu-id="94da7-127">Как панель мониторинга будет использовать службу данных</span><span class="sxs-lookup"><span data-stu-id="94da7-127">How the dashboard consumes the data service</span></span>

<span data-ttu-id="94da7-128">При переходе к домашней странице CQD (например, набор отчетов и соответствующие отчеты для пользователя, подлинность и авторизованного пользователя будут извлечены из службы репозитория. http://localhost/cqd)</span><span class="sxs-lookup"><span data-stu-id="94da7-128">When navigating to the CQD homepage (e.g. http://localhost/cqd), the report set and corresponding reports for an authenticated and authorized user will be retrieved from the Repository Service.</span></span> <span data-ttu-id="94da7-129">Полный URL-адрес будет создан из ИД набора отчетов и года-месяца (ид набора отчетов — это целый номер после раздела "/#/" в URL-адресе, а по умолчанию текущий год-месяц после косой черты будет в конце набора отчетов).</span><span class="sxs-lookup"><span data-stu-id="94da7-129">A full URL will be constructed from the report-set ID and the year-month (report-set ID is the integer number after '/#/' section in URL, and by default the current year-month is appended at the end of the report-set ID after the slash).</span></span> <span data-ttu-id="94da7-130">Определения отчетов хранятся в формате JSON и при извлечении из службы репозитория будут использоваться в качестве входных данных для службы данных.</span><span class="sxs-lookup"><span data-stu-id="94da7-130">The report definitions are stored in JSON format and when retrieved from the Repository Service, will then be used as input to the Data Service.</span></span> <span data-ttu-id="94da7-131">Служба данных создает запросы многомерных выражений (MDX) на основе входных данных и затем вызывает эти запросы многомерных выражений к кубу, чтобы получить данные для каждого отчета.</span><span class="sxs-lookup"><span data-stu-id="94da7-131">The Data Service generates Multi-Dimension expressions (MDX) queries based on the input and then run these MDX queries against the Cube to retrieve data for each report.</span></span> 

### <a name="building-customized-reports"></a><span data-ttu-id="94da7-132">Создание настраиваемых отчетов</span><span class="sxs-lookup"><span data-stu-id="94da7-132">Building customized reports</span></span>

<span data-ttu-id="94da7-133">В CQD уже есть большая гибкость в настройке отчетов, но могут возникнуть ситуации, в которых пользователям может потребоваться агрегировать данные в нескольких отчетах, созданных в CQD.</span><span class="sxs-lookup"><span data-stu-id="94da7-133">CQD already has a lot of flexibility in customizing reports, but there could be situations where users may want to aggregate data across multiple reports created in CQD.</span></span> <span data-ttu-id="94da7-134">Например, может понадобиться создать отчет, который показывает процент звонков низкого качества для всех возможных комбинаций проводных звонков в таблице (результат, например, на рисунке):</span><span class="sxs-lookup"><span data-stu-id="94da7-134">For example, there could be a need to create a report that shows the poor call percentages of all possible combinations of wired calls in a table (a result like the figure):</span></span>

![Таблица CQD](../../media/ef19d535-5da6-44a9-91f6-1ed3f30b96f1.png)

<span data-ttu-id="94da7-136">С помощью портала, предоставленного CQD, пользователю потребуется перейти к нескольким отчетам, чтобы извлечь и записать процент вызовов низкого качества для каждого из них, что может быть трудоемким, если требуется собрать большое количество точек данных.</span><span class="sxs-lookup"><span data-stu-id="94da7-136">Using the Portal provided by CQD, a user would have to navigate to multiple reports to extract and record the poor call % for each one, which can be laborious if there are many data points that need to be collected.</span></span> <span data-ttu-id="94da7-137">API данных предоставляют пользователям программный способ получить данные из службы данных (например, с помощью вызовов AJAX).</span><span class="sxs-lookup"><span data-stu-id="94da7-137">The Data APIs provide users with a programmatic way to accomplish this, by retrieving data from the Data Service (e.g. via AJAX calls).</span></span> 

 <span data-ttu-id="94da7-138">**Пример 1. Пример простого отчета**</span><span class="sxs-lookup"><span data-stu-id="94da7-138">**Example 1: Simple report sample**</span></span>

<span data-ttu-id="94da7-139">Сначала рассмотрим простой пример.</span><span class="sxs-lookup"><span data-stu-id="94da7-139">Let us take a simple example first.</span></span> <span data-ttu-id="94da7-140">Если мы хотим показать количество потоков Audio Good Stream и Audio Bad за февраль 2015 г. на HTML-странице, например на рисунке:</span><span class="sxs-lookup"><span data-stu-id="94da7-140">If we want to show the Audio Good Stream and the Audio Bad stream count of February 2015 on an HTML page like the figure:</span></span>

![Пример отчета CQD](../../media/f0e4e61f-1fa5-4d69-b192-f19e9612bf1c.png)

<span data-ttu-id="94da7-142">Нам нужно отправить вызов в службу данных с правильными параметрами и показать результаты запроса в HTML-таблице.</span><span class="sxs-lookup"><span data-stu-id="94da7-142">What we need is to send a call to the Data Service with the proper parameters, and show the query results in an HTML table.</span></span> <span data-ttu-id="94da7-143">Ниже приводится пример кода JavaScript.</span><span class="sxs-lookup"><span data-stu-id="94da7-143">The following is a sample of the JavaScript code:</span></span>

```javascript        
$($.fn.freeFormReport = function (queries, urlApi, presentation) {
            var query = {
                Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                Filters: [{
                    DataModelName: '[StartDate].[Month]',
                    Value: '[2015-02-01T00:00:00]',
                    Operand: 0
                }],
                Measurements:
                    [{ DataModelName: '[Measures].[Audio Good Streams JPDR Count]' },
                     { DataModelName: '[Measures].[Audio Poor Streams JPDR Count]' },]
            };            

            $.ajax({
                url: 'http://localhost/QoEDataService/RunQuery',
                data: JSON.stringify(query),
                type: 'POST',
                async: true,
                contentType: 'application/json;charset=utf-8',
                success: function (data) {
                    //This is the jQuery syntax for document.GetElementById()
                    $('#AudioGoodStreamsJPDRCount').html(data.DataResult[0][1]);
                    $('#AudioPoorStreamsJPDRCount').html(data.DataResult[0][2]);
                }
                error: function (error) {
                    alert('Error getting data, check that the data service is running and that the URL is correct.');
           }
            });
        });
```

<span data-ttu-id="94da7-144">Этот пример можно далее разрезать на три этапа:</span><span class="sxs-lookup"><span data-stu-id="94da7-144">This example can be further deconstructed into three steps:</span></span>

1. <span data-ttu-id="94da7-145">Создание запроса (в примере он определен в переменной "query").</span><span class="sxs-lookup"><span data-stu-id="94da7-145">Construct the query (in the example this is defined in the variable 'query').</span></span> <span data-ttu-id="94da7-146">Запрос определяется как объект JSON, который включает следующие данные:</span><span class="sxs-lookup"><span data-stu-id="94da7-146">The query is defined as a JSON object, which includes the following data:</span></span>

   <span data-ttu-id="94da7-147">а.</span><span class="sxs-lookup"><span data-stu-id="94da7-147">a.</span></span> <span data-ttu-id="94da7-148">Ноль или больше измерений.</span><span class="sxs-lookup"><span data-stu-id="94da7-148">Zero or more dimensions.</span></span> <span data-ttu-id="94da7-149">Каждое измерение указывается dataModelName.</span><span class="sxs-lookup"><span data-stu-id="94da7-149">Each dimension is indicated by a DataModelName.</span></span>

   <span data-ttu-id="94da7-150">б.</span><span class="sxs-lookup"><span data-stu-id="94da7-150">b.</span></span> <span data-ttu-id="94da7-151">Ноль или больше фильтров.</span><span class="sxs-lookup"><span data-stu-id="94da7-151">Zero or more filters.</span></span> <span data-ttu-id="94da7-152">Каждый фильтр имеет:</span><span class="sxs-lookup"><span data-stu-id="94da7-152">Each filter has:</span></span>

   - <span data-ttu-id="94da7-153">DataModelName (измерение, которое будет иметь набор фильтров).</span><span class="sxs-lookup"><span data-stu-id="94da7-153">DataModelName (the dimension that will have the filter set).</span></span>

   - <span data-ttu-id="94da7-154">Значение (значение, которое будет сравниваться операндом).</span><span class="sxs-lookup"><span data-stu-id="94da7-154">Value (the value that will be compared by the operand).</span></span>

   - <span data-ttu-id="94da7-155">Операнд (тип сравнения, 0 означает "Равно").</span><span class="sxs-lookup"><span data-stu-id="94da7-155">Operand (comparison type, 0 means "Equal").</span></span>

     <span data-ttu-id="94da7-156">c.</span><span class="sxs-lookup"><span data-stu-id="94da7-156">c.</span></span> <span data-ttu-id="94da7-157">Один или несколько показателей.</span><span class="sxs-lookup"><span data-stu-id="94da7-157">One or more measurements.</span></span>

2. <span data-ttu-id="94da7-158">Отправьте запрос в службу данных с помощью вызова AJAX.</span><span class="sxs-lookup"><span data-stu-id="94da7-158">Send the query to Data Service via AJAX call.</span></span> <span data-ttu-id="94da7-159">Должны быть предоставлены следующие параметры запроса:</span><span class="sxs-lookup"><span data-stu-id="94da7-159">The following request parameters need to be provided:</span></span>

   <span data-ttu-id="94da7-160">а.</span><span class="sxs-lookup"><span data-stu-id="94da7-160">a.</span></span> <span data-ttu-id="94da7-161">url(который должен быть http://[Имя сервера]/QoEDataService/RunQuery).</span><span class="sxs-lookup"><span data-stu-id="94da7-161">url (which should be http://[ServerName]/QoEDataService/RunQuery).</span></span>

   <span data-ttu-id="94da7-162">б.</span><span class="sxs-lookup"><span data-stu-id="94da7-162">b.</span></span> <span data-ttu-id="94da7-163">data (это строка представления объекта JSON, определенного в переменной "query").</span><span class="sxs-lookup"><span data-stu-id="94da7-163">data (this is the string representation of the JSON object defined in the 'query' variable).</span></span> <span data-ttu-id="94da7-164">Служба данных возвращает результаты запроса в качестве параметра функции обратного вызова для успешного выполнения.</span><span class="sxs-lookup"><span data-stu-id="94da7-164">Data Service will return the query results as a parameter of the call back function for success.</span></span>

   <span data-ttu-id="94da7-165">c.</span><span class="sxs-lookup"><span data-stu-id="94da7-165">c.</span></span> <span data-ttu-id="94da7-166">type (для QoEDataService RunQuery принимает только запросы POST).</span><span class="sxs-lookup"><span data-stu-id="94da7-166">type (for QoEDataService, RunQuery only accepts 'POST' requests).</span></span>

   <span data-ttu-id="94da7-167">г.</span><span class="sxs-lookup"><span data-stu-id="94da7-167">d.</span></span> <span data-ttu-id="94da7-168">асинхронный (флаг, указывающий, должен ли вызов AJAX быть синхронным или асинхронным).</span><span class="sxs-lookup"><span data-stu-id="94da7-168">async (a flag indicating whether the AJAX call should be synchronous or asynchronous).</span></span>

   <span data-ttu-id="94da7-169">д.</span><span class="sxs-lookup"><span data-stu-id="94da7-169">e.</span></span> <span data-ttu-id="94da7-170">contentType (должно быть "application/json").</span><span class="sxs-lookup"><span data-stu-id="94da7-170">contentType (should be "application/json").</span></span>

   <span data-ttu-id="94da7-171">е.</span><span class="sxs-lookup"><span data-stu-id="94da7-171">f.</span></span> <span data-ttu-id="94da7-172">успешно (функция обратного вызова для успешного завершения вызова AJAX).</span><span class="sxs-lookup"><span data-stu-id="94da7-172">success (call-back function for when the AJAX call finishes successfully).</span></span>

   <span data-ttu-id="94da7-173">ж.</span><span class="sxs-lookup"><span data-stu-id="94da7-173">g.</span></span> <span data-ttu-id="94da7-174">ошибка (функция обработки ошибок при сбойе вызова AJAX).</span><span class="sxs-lookup"><span data-stu-id="94da7-174">error (error handling function for when AJAX call fails).</span></span>

3. <span data-ttu-id="94da7-175">Поместите данные в элементы div в HTML (в примере в коде это делается с помощью анонимного вызова функции после успешного завершения запроса AJAX).</span><span class="sxs-lookup"><span data-stu-id="94da7-175">Put data into div elements in the HTML (in the example in the code, this is done via the anonymous function call after the AJAX request is completed successfully).</span></span>

<span data-ttu-id="94da7-176">Заключив код JavaScript в HTML-страницу, на странице будет показан отчет, похожий на показанный на рисунке.</span><span class="sxs-lookup"><span data-stu-id="94da7-176">Enclosing the JavaScript code into an HTML page, and the page will show a report like the one shown in the figure.</span></span> <span data-ttu-id="94da7-177">Полный html-код:</span><span class="sxs-lookup"><span data-stu-id="94da7-177">The full html is as follows:</span></span>

```javascript
<!DOCTYPE html>
<html xmlns="http://www.w3.org/1999/xhtml">
<head>
</head>
<body>
    <script src="OpenSourceSoftware/Scripts/jquery-2.1.1.js"></script>

    <script>
        $($.fn.freeFormReport = function (queries, urlApi, presentation) {

            var query = {
                Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                Filters: [{
                    DataModelName: '[StartDate].[Month]',
                    Value: '[2015-02-01T00:00:00]',
                    Operand: 0
                }],
                Measurements:
                    [{ DataModelName: '[Measures].[Audio Good Streams JPDR Count]' },
                     { DataModelName: '[Measures].[Audio Poor Streams JPDR Count]' },]
            };            

            $.ajax({
                url: 'http://localhost/QoEDataService/RunQuery',
                data: JSON.stringify(query),
                type: 'POST',
                async: true,
                contentType: 'application/json;charset=utf-8',
                success: function (data) {
                    //This is the jQuery syntax for document.GetElementById()
                    $('#AudioGoodStreamsJPDRCount').html(data.DataResult[0][1]);
                    $('#AudioPoorStreamsJPDRCount').html(data.DataResult[0][2]);
                }
                error: function (error) {
                    alert('Error getting data, check that the data service is running and that the URL is correct.');
           }

            });
        });
    </script>
    <table border="1">
        <tr>
            <td></td>
            <td><div>Audio Good Streams JPDR Count</div></td>
            <td><div>Audio Poor Streams JPDR Count</div></td>
        </tr>
        <tr>
            <td>February</td>
            <td><div id="AudioGoodStreamsJPDRCount"></div></td>
            <td><div id="AudioPoorStreamsJPDRCount"></div></td>
        </tr>
    </table>
</body>
</html>
```

<span data-ttu-id="94da7-178">Пока что отчет по-прежнему очень прост.</span><span class="sxs-lookup"><span data-stu-id="94da7-178">So far, the report is still very simple.</span></span> <span data-ttu-id="94da7-179">Пользователь может добавить дополнительные измерения, измерения или фильтры для настройки отчета.</span><span class="sxs-lookup"><span data-stu-id="94da7-179">The user can add more measurements, dimensions, or filters to customize the report.</span></span> <span data-ttu-id="94da7-180">Например, если вы хотите показать процент вызовов AppSharing низкого качества, необходимо добавить новое измерение, касающееся AppSharing.</span><span class="sxs-lookup"><span data-stu-id="94da7-180">For example, if you want to show AppSharing poor call percentage, then a new measurement regarding AppSharing needs to be added.</span></span> <span data-ttu-id="94da7-181">Если вы хотите показать все вызовы TCP v.s.</span><span class="sxs-lookup"><span data-stu-id="94da7-181">If you want to show all TCP calls v.s.</span></span> <span data-ttu-id="94da7-182">Вызовы UDP, следует добавить новое измерение, касающееся типа транспорта.</span><span class="sxs-lookup"><span data-stu-id="94da7-182">UDP calls, a new dimension regarding transportation type should be added.</span></span> <span data-ttu-id="94da7-183">Если вы хотите показать количество звонков низкого качества в определенном здании, необходимо добавить новый фильтр для выбора вызовов в это здание и из него.</span><span class="sxs-lookup"><span data-stu-id="94da7-183">If you want to show the number of poor calls within a specific building, then a new filter should be added to select the calls to and from that building.</span></span>

 <span data-ttu-id="94da7-184">**Пример 2. Пример определения отчета**</span><span class="sxs-lookup"><span data-stu-id="94da7-184">**Example 2: Report definition sample**</span></span>

<span data-ttu-id="94da7-185">При составлении запроса может быть сложно понять, как записать полный список измерений, измерений/фильтров и соответствующих им значений.</span><span class="sxs-lookup"><span data-stu-id="94da7-185">It might be difficult for someone to figure out how to write the full list of measurements/dimensions/filters and their corresponding values when constructing a query.</span></span> <span data-ttu-id="94da7-186">В этом случае можно перейти на портал, создать отчет с помощью редактора отчетов и просмотреть строку JSON определения отчета, а затем скопировать определение в настраиваемый отчет.</span><span class="sxs-lookup"><span data-stu-id="94da7-186">In this case, you can go to the Portal, build a report using the report editor, and view the JSON string of the report definition, and then copy the definition into a custom report.</span></span> 

<span data-ttu-id="94da7-187">В этом примере мы создадим веб-страницу, похожую на показанную на рисунке, где пользователь может ввести ИД любого существующего набора отчетов (или отчета) и показать определение набора отчетов или отчета на веб-странице.</span><span class="sxs-lookup"><span data-stu-id="94da7-187">In this example, we will create a web page like the one shown in the figure where a user can enter the ID of any existing report set (or report) and show the definition of the report set or report on the web page.</span></span> <span data-ttu-id="94da7-188">Затем пользователь может подключить строку JSON каждого отчета к коду, аналогичному показанного в примере 1, и создать любой настраиваемый отчет, который будет желаем пользователю.</span><span class="sxs-lookup"><span data-stu-id="94da7-188">The user can then plug the JSON string of each report into code similar to the one shown in Example 1 and construct any customized report the user desires.</span></span> 

![Пример CQD](../../media/01c45c23-c4d2-47b8-819f-0888cf71260f.png)

<span data-ttu-id="94da7-190">Чтобы создать средство просмотра определений отчетов, необходимо отправить вызовы в службу репозитория, чтобы получить строковые представления определений каждого набора отчетов, который нам нужен, в строке JSON.</span><span class="sxs-lookup"><span data-stu-id="94da7-190">To create the report definition viewer tool, we need to send calls to Repository Service to retrieve the JSON string representations of the definitions of every report-set we want.</span></span> <span data-ttu-id="94da7-191">API репозитория возвращает определение набора отчетов на основе заданного ИД набора отчетов.</span><span class="sxs-lookup"><span data-stu-id="94da7-191">The Repository API will return report-set definition based on a given report set ID.</span></span> 

<span data-ttu-id="94da7-192">Краткий пример: код содержит блок, который является простым примером отправки запроса в службу репозитория для получения содержимого элемента репозитория на основе его идентификатора.</span><span class="sxs-lookup"><span data-stu-id="94da7-192">A quick example is as follows, the code contains a block that is a simple example to send a query to the Repository service to get the contents of a repository item based on its identifier.</span></span> <span data-ttu-id="94da7-193">А следующая часть кода (метод processReportSetData) отправляет вызовы AJAX для получения определения каждого отчета в этом наборе отчетов.</span><span class="sxs-lookup"><span data-stu-id="94da7-193">And the next portion of code (processReportSetData method) is sending AJAX calls to get the definition of each report within that report set.</span></span> <span data-ttu-id="94da7-194">Так как ИД на веб-портале CQD является ИД набора отчетов, вызов AJAX возвращает элемент набора отчетов.</span><span class="sxs-lookup"><span data-stu-id="94da7-194">Since the ID in the CQD web portal is the ID of a report set, the AJAX call will return a report set item.</span></span> <span data-ttu-id="94da7-195">Подробнее об API репозитория и, в частности, GetItems, можно найти в меню ["Получить элементы".](get-items.md)</span><span class="sxs-lookup"><span data-stu-id="94da7-195">More detail on the Repository API and specifically, GetItems, can be found in the [Get Items](get-items.md).</span></span> 

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="utf-8" />
    <meta http-equiv='cache-control' content='no-cache'>
    <meta http-equiv='expires' content='0'>
    <meta http-equiv='pragma' content='no-cache'>
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta http-equiv="x-content-type-options" content="nosniff">
    <title>CQD Report definition viewer</title>
</head>
<body>    
    <div style="font-size:32pt">CQD Report definition viewer</div>
        <p>ReportSet Id: <input id="reportSetId" /></p>
        <button onclick='loadReportSet()'>Load</button>
        <div id="Report"></div>
    <!-- Third party Libraries -->
    <script src="OpenSourceSoftware/Scripts/jquery-2.1.1.js"></script>

    <script>
        var urlRepositoryApi = 'http://localhost/QoERepositoryService/repository/item/';

        var loadReportSet = function ()
        {
            var reportSetId = document.getElementById('reportSetId').value;

            $.ajax({
                url: urlRepositoryApi + reportSetId,
                data: '',
                type: 'GET',
                async: false,
                contentType: 'application/json;charset=utf-8',
                success: function (data) {
                    var reportSetDiv = document.getElementById('Report');
                    reportSetDiv.innerHTML = '';
                    processReportSetData(reportSetDiv, data);
                },
                error: function (error) {
                    alert('Error getting Report, check that the qoe data service is running and url is correct.');
                }
            });
        };

        var processReportSetData = function (divReportSet, reportSetDef) {
             //show the report set definition like Title, Description, etc
            showReportSetDefinition(divReportSet, reportSetDef);

            //for each Report in the Reportset, get the Report definition from the Repository Service
            for (var i = 0; i < reportSetDef.subItemIds.length; i++)
            {
                //the reportId is in the subItemIds array.  This is not shown in the CQD UI at all
                var reportId = reportSetDef.subItemIds[i];

                var divReport = document.createElement('div');
                divReport.style.margin = '12px';                
                divReportSet.appendChild(divReport);

                //retrieve the report definition with the reportId
                $.ajax({
                    url: urlRepositoryApi + reportId,
                    data: '',
                    type: 'GET',
                    async: false,
                    contentType: 'application/json;charset=utf-8',
                    success: function (reportData) {
                        processReportData(divReport, reportData, reportId);
                    },
                    error: function (error) {
                        alert('Error getting Report ' + reportId.toString() + ', check that the qoe data service is running and url is correct.');
                    }
                });
            }
        };

        //helper function to render the ReportSet definition
        var showReportSetDefinition = function (divReportSet, reportSetDef) {
            var div = document.createElement('div');
            ReportSetDefinition = reportSetDef.content;
            txt = document.createTextNode(ReportSetDefinition);
            div.style.margin = '12px';
            div.appendChild(txt);
            divReportSet.appendChild(div);
        };

        //show the report definition
        var processReportData = function (divReport, reportData, itemId) {
            if (divReport != undefined &amp;&amp; reportData.content != undefined) {
                var Report = JSON.parse(reportData.content);

                var divReportId = document.createElement('div');
                var subItemId = reportData.subItemIds.length > 0 ? reportData.subItemIds[0].toString() : 'none';
                divReportId.innerHTML = 'ItemId: ' + itemId.toString() + ' (' + Report.Title + ') [subItemId:' + subItemId + ']';
                divReport.appendChild(divReportId);

                var divReportDef = document.createElement('div');
                txt = document.createTextNode(JSON.stringify(Report));
                divReportDef.style.margin = '12px';
                divReportDef.appendChild(txt);                            
                divReport.appendChild(divReportDef);
            }
        };
    </script>
</body>
</html>
```

<span data-ttu-id="94da7-196">В результате вышеуказанная веб-страница будет выглядеть так же, как на рисунке (без определения отчета при первоначальном посещении).</span><span class="sxs-lookup"><span data-stu-id="94da7-196">The above will result in a web page like the one in the figure (without the report definition upon initial visit).</span></span> <span data-ttu-id="94da7-197">Получите ИД набора отчетов с портала CQD (это после знака "/#/" в URL-адресе портала CQD (например,</span><span class="sxs-lookup"><span data-stu-id="94da7-197">Get the report set ID from CQD portal (it is after '/#/' sign in CQD portal URL (E.g.</span></span> <span data-ttu-id="94da7-198">На первом рисунке ид набора отчетов — 3024, и этот ид набора отчетов помещался во входной раздел этой веб-страницы.</span><span class="sxs-lookup"><span data-stu-id="94da7-198">in the first figure the report set ID is 3024), and put this report set ID into the input section of this web page.</span></span> <span data-ttu-id="94da7-199">Нажмите кнопку "загрузить" и посмотрите полное определение (измерения, измерения, списки фильтров) набора отчетов.</span><span class="sxs-lookup"><span data-stu-id="94da7-199">Press the "load" button and see the full definition (measurements, dimensions, filters lists) of the report set.</span></span>

<span data-ttu-id="94da7-200">Таким образом, чтобы быстро получить полное определение набора отчетов и отчетов.</span><span class="sxs-lookup"><span data-stu-id="94da7-200">In summary, in order to quickly get the full definition of a report/report set.</span></span> <span data-ttu-id="94da7-201">Ниже описана последовательность действий.</span><span class="sxs-lookup"><span data-stu-id="94da7-201">The steps are:</span></span>

1. <span data-ttu-id="94da7-202">Перейдите на портал и используйте редактор запросов для настройки отчета (нажмите кнопку "Изменить" над отчетом, чтобы изменить, добавить, удалить измерения, измерения/фильтры, а затем сохранить отчет).</span><span class="sxs-lookup"><span data-stu-id="94da7-202">Go to the Portal and use the query editor to customize a report (click the "Edit" button above a report to edit, add, remove measurements/dimensions/filters, and then save the report).</span></span>

2. <span data-ttu-id="94da7-203">Получите по URL-адресу ИД набора отчетов (это будет вся после URL-адреса для знака "/#/").</span><span class="sxs-lookup"><span data-stu-id="94da7-203">Get the report set ID from URL (the integer after '/#/' sign in URL).</span></span>

3. <span data-ttu-id="94da7-204">Запустите эту веб-страницу определения отчета, созданную в примере 2, и введите ИД набора отчетов и извлекает полное определение набора отчетов (для использования в вызовах API данных).</span><span class="sxs-lookup"><span data-stu-id="94da7-204">Launch this Report Definition web page created in Example 2, and enter the report set ID and retrieve the full definition of a report set (to use in Data API calls).</span></span>

   <span data-ttu-id="94da7-205">**Пример 3. Пример системы показателей**</span><span class="sxs-lookup"><span data-stu-id="94da7-205">**Example 3: Scorecard sample**</span></span>

<span data-ttu-id="94da7-206">Время для более сложной задачи.</span><span class="sxs-lookup"><span data-stu-id="94da7-206">Time for a more complicated task.</span></span> <span data-ttu-id="94da7-207">Что делать, если мы хотим создать веб-страницу, похожую на рисунок?</span><span class="sxs-lookup"><span data-stu-id="94da7-207">What if we want to create a web page like the figure?</span></span> <span data-ttu-id="94da7-208">Нам необходимо обновить пример 1 (с помощью веб-страницы, сгенерированной в примере 2, чтобы получить полное определение любого отчета), чтобы можно было обрабатывать больший объем данных.</span><span class="sxs-lookup"><span data-stu-id="94da7-208">We need to update Example 1, (with the help of the web page generated in Example 2 to retrieve the full definition of any report) so that we can handle larger amount of data.</span></span>

<span data-ttu-id="94da7-209">В этом случае нам необходимо обновить список измерений и показателей.</span><span class="sxs-lookup"><span data-stu-id="94da7-209">In this case, we need to update the measurement and dimension list.</span></span> <span data-ttu-id="94da7-210">Чтобы узнать, как добавить или изменить измерение, выполните инструкции в примере 2 и извлекаете полное определение отчета, включая полные списки измерений и измерений.</span><span class="sxs-lookup"><span data-stu-id="94da7-210">The way to figure out how to add/edit a measurement and/or a dimension is to follow the instructions in Example 2, and retrieve the full report definition, including the full measurement and dimension lists.</span></span> <span data-ttu-id="94da7-211">Подключите полное определение отчета к примеру кода.</span><span class="sxs-lookup"><span data-stu-id="94da7-211">Plug the full report definition into the sample code.</span></span> 

<span data-ttu-id="94da7-212">Ниже описаны подробные инструкции для получения страницы системы показателей на рисунке из примера, представленного в примере 1:</span><span class="sxs-lookup"><span data-stu-id="94da7-212">Here are the detailed steps to get to the scorecard page in the figure from the sample provided in Example 1:</span></span>

1. <span data-ttu-id="94da7-213">Обновление показателей в переменной "query" от  `[Measures].[Audio Good Streams JPDR Count]` и `[Measures].[Audio Poor Streams JPDR Count]` до `[Measures].[AudioPoorJPDRPercentage]` .</span><span class="sxs-lookup"><span data-stu-id="94da7-213">Update Measurements in the 'query' variable from  `[Measures].[Audio Good Streams JPDR Count]` and `[Measures].[Audio Poor Streams JPDR Count]` to `[Measures].[AudioPoorJPDRPercentage]`.</span></span> 

2. <span data-ttu-id="94da7-214">Обновим фильтры.</span><span class="sxs-lookup"><span data-stu-id="94da7-214">Update the filters.</span></span> <span data-ttu-id="94da7-215">Данные JSON для фильтров в примере 1 имеет один фильтр, который устанавливается в  `[StartDate].[Month]` измерении.</span><span class="sxs-lookup"><span data-stu-id="94da7-215">The JSON data for Filters in Example 1 has one filter, which is set on the dimension  `[StartDate].[Month]`.</span></span> <span data-ttu-id="94da7-216">Так как фильтры — это массив JSON, в список фильтров можно добавить дополнительные измерения.</span><span class="sxs-lookup"><span data-stu-id="94da7-216">Since Filters is a JSON array, additional dimensions can be added to the list of filters.</span></span> <span data-ttu-id="94da7-217">Например, чтобы получить сервер-клиент внутри проводных вызовов для "currentMonth", у нас должны быть следующие фильтры:</span><span class="sxs-lookup"><span data-stu-id="94da7-217">For example, to get the server-client inside wired calls for the "currentMonth", we should have the following filters:</span></span>

   ```javascript
   Filters: [
     { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
    {
        "DataModelName": "[Scenarios].[ScenarioPair]",
         "Caption": " Server-Inside-wired,Client-Inside-wired",
         "Value": "[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]",
         "Operand": 0,
         "UnionGroup": ""
     },

     { DataModelName: '[StreamType].[StreamType]', Caption: "Valid", Value: "[False]", Operand: 0, UnionGroup: "" }
   ],
   ```

   <span data-ttu-id="94da7-218">Здесь измерение  `[Scenarios].[ScenarioPair]` равно `[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]` .</span><span class="sxs-lookup"><span data-stu-id="94da7-218">Here the dimension  `[Scenarios].[ScenarioPair]` is set to equal `[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]`.</span></span> <span data-ttu-id="94da7-219">Это  `[Scenario.][ScenarioPair]` специальное измерение, созданное для упрощения создания отчетов.</span><span class="sxs-lookup"><span data-stu-id="94da7-219">The  `[Scenario.][ScenarioPair]` is a special dimension created to simplify report creation.</span></span> <span data-ttu-id="94da7-220">Он имеет шесть значений, соответствующих `[FirstIsServer], [SecondIsServer], [FirstInside], [SecondIsServer], [FirstConnectionType], [SecondConnectionType]` .</span><span class="sxs-lookup"><span data-stu-id="94da7-220">It has six values corresponding to `[FirstIsServer], [SecondIsServer], [FirstInside], [SecondIsServer], [FirstConnectionType], [SecondConnectionType]`.</span></span> <span data-ttu-id="94da7-221">Поэтому вместо использования сочетания 6 фильтров для определения сценария необходимо использовать только один фильтр.</span><span class="sxs-lookup"><span data-stu-id="94da7-221">So instead of using a combination of 6 filters to define a scenario, we only need to use 1 filter.</span></span> <span data-ttu-id="94da7-222">В нашем примере значение преобразуется в сценарий, где: первый — сервер, второй — не сервер, второй — внутри, первый тип подключения проводной, второй тип подключения проводной, то есть точное определение  `[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]` "Server-Client-Inside Wired".</span><span class="sxs-lookup"><span data-stu-id="94da7-222">In our example, the value  `[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]` translates to the scenario where: first is server, second is not server, first is inside, second is inside, first connection type is wired, and second connection type is wired, which is the exact definition of "Server-Client-Inside Wired".</span></span>

3. <span data-ttu-id="94da7-223">Создайте один набор фильтров для каждого сценария.</span><span class="sxs-lookup"><span data-stu-id="94da7-223">Create one filter set per scenario.</span></span> <span data-ttu-id="94da7-224">Каждая строка системы показателей, представленная на рисунке, представляет разные сценарии, которые будут представлять собой разные фильтры (в то время как измерения и показатели остаются одинаковыми).</span><span class="sxs-lookup"><span data-stu-id="94da7-224">Each row in the scorecard, in the figure, represents a different scenario, which will be a different filter (while the dimensions and measurements stay the same).</span></span> 

4. <span data-ttu-id="94da7-225">Анализ результатов вызовов AJAX и поместите их в правильное положение таблицы.</span><span class="sxs-lookup"><span data-stu-id="94da7-225">Parse the results from the AJAX calls and place them in the correct position of the table.</span></span> <span data-ttu-id="94da7-226">Так как это в основном манипуляции с HTML и JavaScript, здесь мы не будем подробно перейти к этим сведениям.</span><span class="sxs-lookup"><span data-stu-id="94da7-226">Since this is mostly HTML and JavaScript manipulation, we will not go into the details here.</span></span> <span data-ttu-id="94da7-227">Вместо этого код предоставляется в приложении А.</span><span class="sxs-lookup"><span data-stu-id="94da7-227">Instead, the code is provided in Appendix A.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="94da7-228">Если включен общий доступ к ресурсам между источниками (CORS), у пользователей могут возникнуть такие ошибки, как "Нет загона "Access-Control-Allow-Origin" в запрашиваемом ресурсе.</span><span class="sxs-lookup"><span data-stu-id="94da7-228">If Cross-Origin Resource Sharing (CORS) is enabled, users may encounter errors like "No 'Access-Control-Allow-Origin' header is present on the requested resource.</span></span> <span data-ttu-id="94da7-229">Поэтому источнику "null" не разрешен доступ".</span><span class="sxs-lookup"><span data-stu-id="94da7-229">Origin 'null' is therefore not allowed access".</span></span> <span data-ttu-id="94da7-230">Чтобы устранить проблему, поместите HTML-файл в папку, в которой установлен портал (по умолчанию он должен быть `%SystemDrive%\Program Files\Skype for Business 2015 CQD\CQD)` .</span><span class="sxs-lookup"><span data-stu-id="94da7-230">To resolve the issue, place the HTML file under the folder where the Portal is installed (by default, it should be `%SystemDrive%\Program Files\Skype for Business 2015 CQD\CQD)`.</span></span> <span data-ttu-id="94da7-231">Затем доступ к HTML-коду можно получить через любой браузер с URL-адресом. `http://<servername>/cqd/<html_file_name>`</span><span class="sxs-lookup"><span data-stu-id="94da7-231">Then access the html through any browser with the URL  `http://<servername>/cqd/<html_file_name>`.</span></span> <span data-ttu-id="94da7-232">(URL-адрес по умолчанию для локальной панели мониторинга CQD:  `http://<servername>/cqd.` )</span><span class="sxs-lookup"><span data-stu-id="94da7-232">(The default URL for local CQD dashboard is  `http://<servername>/cqd.`)</span></span> 

### <a name="appendix-a"></a><span data-ttu-id="94da7-233">Приложение A</span><span class="sxs-lookup"><span data-stu-id="94da7-233">Appendix A</span></span>

<span data-ttu-id="94da7-234">HTML-код для примера 3 (пример системы показателей):</span><span class="sxs-lookup"><span data-stu-id="94da7-234">HTML code for Example 3 (Scorecard sample):</span></span>

```html
<!DOCTYPE html>
<html xmlns="http://www.w3.org/1999/xhtml">
<head>
    <meta charset="utf-8" />
    <meta http-equiv='cache-control' content='no-cache'>
    <meta http-equiv='expires' content='0'>
    <meta http-equiv='pragma' content='no-cache'>
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <title>Scoreboard Sample</title>

    <style>
        .row {
            margin-right: -15px;
            margin-left: -15px;
            display: table-row;
        }
        .col-md-3 {
            width: 25%;
            display: table-cell;
        }
        .col-md-2 {
            width: 16.66666667%;
            display: table-cell;
        }
        .col-md-1 {
            width: 8.33333333%;
            display: table-cell;
        }

    </style>
</head>
<body>    

    <!-- Third party Libraries -->
    <script src="OpenSourceSoftware/Scripts/jquery-2.1.1.js"></script>

    <table id="ScoreCardTable" style="margin:100px">
        <tr>
            <td width="250px" style="text-align: center; font-size: 24px; font-family: 'Segoe UI'; font-weight: lighter; color: white; background-color: #505050">
                <div style="margin:10px">Scoreboard Sample</div>
            </td>
            <td width="1200px">
                <div style="margin:10px;background-color:#D9D9D9" >
                    <div class="row" id="Header" style="font-size:24px;font-family:'Segoe UI';font-weight:lighter;color:white;background-color:#505050">
                        <div class="col-md-3">Poor Call %</div>
                        <div class="col-md-1">Month1</div>
                        <div class="col-md-1">Month2</div>
                        <div class="col-md-1">Month3</div>
                        <div class="col-md-1">Month4</div>
                        <div class="col-md-1">Month5</div>
                        <div class="col-md-1">Month6</div>
                    </div>                    
                    <div class="row"><div class="col-md-3" style="font-weight:bold">Wired</div></div>
                    <div class="row" id="SS"><div class="col-md-3">Server-Server</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row" id="SWI"><div class="col-md-3">Server-Client (inside)</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row" id="SWO"><div class="col-md-3">Server-Client (outside)</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row" id="WWI"><div class="col-md-3">Client-Client (inside)</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row" id="WIWO"><div class="col-md-3">Client-Client (outside)</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row"><div class="col-md-3" style="font-weight:bold">Wireless</div></div>
                    <div class="row" id="SWFI"><div class="col-md-3">Server-Client (inside)</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row" id="SWFO"><div class="col-md-3">Server-Client (outside)</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row" id="WFIWFI"><div class="col-md-3">Client-Client (inside)</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row" id="WFOWFO"><div class="col-md-3">Client-Client (outside)</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row"><div class="col-md-3" style="font-weight:bold">Mobile/Broadband</div></div>
                    <div class="row" id="SMP"><div class="col-md-3">Server-MobilePhone</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row" id="SMBB"><div class="col-md-3">Server-MobileBroadBand</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row"><div class="col-md-3" style="font-weight:bold">Lync Web App</div></div>
                    <div class="row" id="SLWA"><div class="col-md-3">Server-Client (inside &amp; outside)</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                </div>
            </td>
        </tr>
        <tr>
            <td><br /></td>
        </tr>
    </table>

    <script>

        $(function () {
            var month_names_short = ['NAM', 'Jan', 'Feb', 'Mar', 'Apr', 'May', 'Jun', 'Jul', 'Aug', 'Sep', 'Oct', 'Nov', 'Dec'];
            var currentMonth = '2015-3';

            //update the header with the month names
            var row = document.getElementById('Header');
            var numMonthsToShow = 6;
            for (var m = numMonthsToShow-1; m >= 0; m--) {
                var dateSplit = currentMonth.split('-');
                var monthInt = parseInt(dateSplit[1]);
                var yearInt = parseInt(dateSplit[0]);
                monthInt = monthInt - m;
                if (monthInt < 1)
                {
                    monthInt += 12;
                    yearInt--;
                }
                row.children[numMonthsToShow-m].innerHTML = month_names_short[monthInt];
            }

            var queries = [
            {
                Label: "Server-Server",
                ID: "SS",
                Query:
                {
                  Dimensions: [{ DataModelName: '[StartDate].[Month]'}],
                  Filters: [
                      {
                          "DataModelName": "[Scenarios].[ScenarioPair]",
                          "Caption": " Server-Inside-wired,Server-Inside-wired",
                          "Value": "[1]&amp;[1]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]",
                          "Operand": 0,
                          "UnionGroup": ""
                      },
                      { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
                      { DataModelName: '[StreamType].[StreamType]', Caption: "Valid", Value: "[False]", Operand: 0, UnionGroup: ""}
                  ],
                  Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]'}],
                  Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                 }
            },
            {
                Label: "Server-Client (inside)",
                ID: "SWI",
                Query:
                {
                  Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                  Filters: [
                      {
                          "DataModelName": "[Scenarios].[ScenarioPair]",
                          "Caption": " Server-Inside-wired,Client-Inside-wired",
                          "Value": "[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]",
                          "Operand": 0,
                          "UnionGroup": ""
                      },
                      { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
                      { DataModelName: '[StreamType].[StreamType]', Caption: "Valid", Value: "[False]", Operand: 0, UnionGroup: "" }
                  ],
                  Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                  Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                }
            },
            {
                Label: "Server-Client (outside)",
                ID: "SWO",
                Query:
                {
                  Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                  Filters: [
                      {
                          "DataModelName": "[Scenarios].[ScenarioPair]",
                          "Caption": " Server-Inside-wired,Client-Outside-wired",
                          "Value": "[1]&amp;[0]&amp;[1]&amp;[0]&amp;[Wired]&amp;[Wired]",
                          "Operand": 0,
                          "UnionGroup": ""
                      },
                      { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
                      { DataModelName: '[StreamType].[StreamType]', Caption: "Valid", Value: "[False]", Operand: 0, UnionGroup: "" }
                  ],
                  Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                  Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                 }
            },
            {
                Label: "Client-Client (inside)",
                ID: "WWI",
                Query:
                {
                    Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                    Filters: [
                        {
                            "DataModelName": "[Scenarios].[ScenarioPair]",
                            "Caption": " Client-Inside-wired,Client-Inside-wired",
                            "Value": "[0]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]",
                            "Operand": 0,
                            "UnionGroup": ""
                        },
                        { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
                        { DataModelName: '[StreamType].[StreamType]', Caption: "Valid", Value: "[False]", Operand: 0, UnionGroup: "" }
                    ],
                    Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                    Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                }
            }
            ,
            {
                Label: "Client-Client (outside)",
                ID: "WIWO",
                Query:
                {
                    Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                    Filters: [
                        {
                          "DataModelName": "[Scenarios].[ScenarioPair]",
                          "Caption": "Client-Outside-Wired,Client-Outside-Wired",
                          "Value": "[0]&amp;[0]&amp;[0]&amp;[0]&amp;[Wired]&amp;[Wired]",
                          "Operand": 0,
                          "UnionGroup": ""
                        },
                        { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
                        { DataModelName: '[StreamType].[StreamType]', Caption: "Valid", Value: "[False]", Operand: 0, UnionGroup: "" }
                    ],
                    Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                    Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                }
            },
            {
                Label: "Server-Client (inside)",
                ID: "SWFI",
                Query:
                {
                    Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                    Filters: [
                        {
                            "DataModelName": "[Scenarios].[ScenarioPair]",
                            "Caption": " Server-Inside-wired,Client-Inside-wifi",
                            "Value": "[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wifi]",
                            "Operand": 0,
                            "UnionGroup": ""
                        },
                        { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
                        { DataModelName: '[StreamType].[StreamType]', Caption: "Valid", Value: "[False]", Operand: 0, UnionGroup: "" }
                    ],
                    Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                    Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                }
            },
            {
                Label: "Server-Client (outside)",
                ID: "SWFO",
                Query:
                {
                    Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                    Filters: [
                         {
                             "DataModelName": "[Scenarios].[ScenarioPair]",
                             "Caption": " Server-Inside-wired,Client-Outside-wifi",
                             "Value": "[1]&amp;[0]&amp;[1]&amp;[0]&amp;[Wired]&amp;[Wifi]",
                             "Operand": 0,
                             "UnionGroup": ""
                         },
                        { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
                        { DataModelName: '[StreamType].[StreamType]', Caption: "Valid", Value: "[False]", Operand: 0, UnionGroup: "" }
                    ],
                    Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                    Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                }
            },
            {
                Label: "Client-Client (inside)",
                ID: "WFIWFI",
                Query:
                {
                    Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                    Filters: [
                        {
                            "DataModelName": "[Scenarios].[ScenarioPair]",
                            "Caption": " Client-Inside-Wifi,Client-Inside-Wifi",
                            "Value": "[0]&amp;[0]&amp;[1]&amp;[1]&amp;[Wifi]&amp;[Wifi]",
                            "Operand": 0,
                            "UnionGroup": ""
                        },
                        { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
                        { DataModelName: '[StreamType].[StreamType]', Caption: "Valid", Value: "[False]", Operand: 0, UnionGroup: "" }
                    ],
                    Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                    Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                }
            },
            {
                Label: "Client-Client (outside)",
                ID: "WFOWFO",
                Query:
                {
                    Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                    Filters: [
                        {
                          "DataModelName": "[Scenarios].[ScenarioPair]",
                          "Caption": "Client-Outside-Wifi,Client-Outside-Wifi",
                          "Value": "[0]&amp;[0]&amp;[0]&amp;[0]&amp;[Wifi]&amp;[Wifi]",
                          "Operand": 0,
                          "UnionGroup": ""
                        },
                        { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
                        { DataModelName: '[StreamType].[StreamType]', Caption: "Valid", Value: "[False]", Operand: 0, UnionGroup: "" }
                    ],
                    Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                    Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                }
            },
            {
                Label: "Server-MobilePhone",
                ID: "SMP",
                Query:
                {
                    Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                    Filters: [
                        {"DataModelName": "[First Is Server].[Agent]","Caption": "Server","Value": "[1]","Operand": 0,"UnionGroup": ""},
                        {"DataModelName": "[Second User Agent].[User Agent Type]","Caption": "AndroidLync | iPhoneLync | WPLync","Value": "[AndroidLync],[iPhoneLync],[WPLync]","Operand": 0,"UnionGroup": ""},
                        { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
                    ],
                    Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                    Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                }
            },
            {
                Label: "Server-MobileBroadBand",
                ID: "SMBB",
                Query:
                {
                    Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                    Filters: [
                        {"DataModelName": "[Second Network Connection Type].[Network Connection Detail]","Caption": "MobileBB","Value": "[MobileBB]","Operand": 0,"UnionGroup": ""},
                        {"DataModelName": "[First Is Server].[Agent]","Caption": "Server","Value": "[1]","Operand": 0,"UnionGroup": ""},
                        {"DataModelName": "[Second Is Server].[Agent]","Caption": "Client ","Value": "[0]","Operand": 0,"UnionGroup": ""},
                        { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 }                       
                    ],
                    Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                    Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                }
            },
            {
                Label: "Server-LWA",
                ID: "SLWA",
                Query:
                {
                    Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                    Filters: [
                        {"DataModelName": "[First Is Server].[Agent]","Caption": "Server","Value": "[1]","Operand": 0,"UnionGroup": ""},
                        {"DataModelName": "[Second User Agent].[User Agent Type]","Caption": "LWA","Value": "[LWA]","Operand": 0,"UnionGroup": ""},
                        { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 }                       
                    ],
                    Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                    Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                }
            }

            ];

            //get the overall corpnet data
            for (var i = 0; i < queries.length; i++) {
                $.ajax({

                    url: 'http://localhost/QoEDataService/RunQuery',
                    data: JSON.stringify(queries[i].Query),
                    type: 'POST',
                    async: false,
                    withCredentials: true,
                    contentType: 'application/json;charset=utf-8',
                    success: function (data) {

                        //find the table row corresponding to the name of this query
                        var row = document.getElementById(queries[i].ID);

                        //update the values for each month
                        for (var m = 0; m < data.DataResult.length; m++)
                        {
                            row.children[m + 1].innerHTML = data.DataResult[m][1].toFixed(2).toString();
                        }

                    },
                    error: function (error) {
                        var row = document.getElementById(queries[i].ID);
                        row.children[1].innerHTML = 'error';
                    }
                });
            }
        });
    </script>
</body>
</html>
```
