---
title: Примеры разработки CQD
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 8ca9bf7a-2d6f-48d5-a821-531009726525
description: 'Сводка: Обзор разработки и учебных примеров для панели мониторинга качества звонков. Панель мониторинга качества звонков — это средство для Скайп для Business Server.'
ms.openlocfilehash: eb2e195a9eaac54b01af6d0da498fda6fafe374c
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32232864"
---
# <a name="cqd-development-samples"></a><span data-ttu-id="cfa2b-104">Примеры разработки CQD</span><span class="sxs-lookup"><span data-stu-id="cfa2b-104">CQD Development Samples</span></span>

<span data-ttu-id="cfa2b-105">**Сводка:** Обзор разработки и учебных примеров для панели мониторинга качества звонков.</span><span class="sxs-lookup"><span data-stu-id="cfa2b-105">**Summary:** Review a tutorial and development samples for Call Quality Dashboard.</span></span> <span data-ttu-id="cfa2b-106">Панель мониторинга качества звонков — это средство для Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="cfa2b-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>

<span data-ttu-id="cfa2b-107">Эта статья представляет собой учебное пособие по разработке панели мониторинга качества вызовов (CQD) с примерами.</span><span class="sxs-lookup"><span data-stu-id="cfa2b-107">This article provides a tutorial and samples on development for Call Quality Dashboard (CQD).</span></span>

## <a name="call-quality-dashboard-cqd-development-samples"></a><span data-ttu-id="cfa2b-108">Примеры разработки панели мониторинга качества вызовов (CQD)</span><span class="sxs-lookup"><span data-stu-id="cfa2b-108">Call Quality Dashboard (CQD) Development Samples</span></span>

<span data-ttu-id="cfa2b-109">Учебное пособие. Построение презентаций нестандартных отчетов с помощью интерфейсов API для службы данных и службы репозитория в CQD.</span><span class="sxs-lookup"><span data-stu-id="cfa2b-109">Tutorial: Building Customized Report Presentation using the CQD Data Service and Repository Service API's.</span></span>

### <a name="introduction-to-cqd"></a><span data-ttu-id="cfa2b-110">Введение в CQD</span><span class="sxs-lookup"><span data-stu-id="cfa2b-110">Introduction to CQD</span></span>

<span data-ttu-id="cfa2b-111">CQD обеспечивает быстрый и удобный доступ к сводным данным о качестве вызова в локальных развертываниях Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="cfa2b-111">CQD offers quick and easy access to aggregated call quality information for on-premise Skype for Business Server deployments.</span></span> <span data-ttu-id="cfa2b-112">CQD состоит из трех компонентов: архивной базы данных качества взаимодействия, куба и портала.</span><span class="sxs-lookup"><span data-stu-id="cfa2b-112">CQD consists of three components: the QoE Archive database, the Cube, and the Portal.</span></span> <span data-ttu-id="cfa2b-113">Портал – это основной уровень презентации, который в свою очередь подразделяется на три следующих компонента:</span><span class="sxs-lookup"><span data-stu-id="cfa2b-113">The Portal is the main presentation layer and can be further divided into the following three components:</span></span>

1. <span data-ttu-id="cfa2b-114">Службы данных, доступном для прошедших проверку подлинности пользователей с помощью [Data API для вызова качества панели мониторинга (CQD) в Скайп для Business Server](data-api.md).</span><span class="sxs-lookup"><span data-stu-id="cfa2b-114">Data Service, which is accessible for authenticated users through the [Data API for Call Quality Dashboard (CQD) in Skype for Business Server](data-api.md).</span></span>

2. <span data-ttu-id="cfa2b-115">Репозиторий служба доступна для прошедших проверку подлинности пользователей с помощью [API репозитория для вызова качества панели мониторинга (CQD) в Скайп для Business Server](repository-api.md).</span><span class="sxs-lookup"><span data-stu-id="cfa2b-115">Repository Service, which is accessible for authenticated users through the [Repository API for Call Quality Dashboard (CQD) in Skype for Business Server](repository-api.md).</span></span>

3. <span data-ttu-id="cfa2b-116">веб-портал — интерфейс на основе HTML5, доступный пользователям CQD для просмотра и взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="cfa2b-116">Web portal, which is the HTML5 based interface that CQD users see and interact with.</span></span> <span data-ttu-id="cfa2b-117">Пользователи должны пройти проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="cfa2b-117">This is accessible for authenticated users.</span></span>

<span data-ttu-id="cfa2b-118">Отчеты, отображаемые на веб-портал сгруппированы в «отчет о наборы».</span><span class="sxs-lookup"><span data-stu-id="cfa2b-118">The reports shown on the web portal are grouped into "report sets".</span></span> <span data-ttu-id="cfa2b-119">На рисунке показан такой набор, состоящий из двух отчетов.</span><span class="sxs-lookup"><span data-stu-id="cfa2b-119">The figure shows a report set with two reports.</span></span> <span data-ttu-id="cfa2b-120">В каждом отчете на показанной ниже панели мониторинга отображаются результаты запроса, указывающие количество вызовов высокого качества, количество вызовов низкого качества и долю вызовов низкого качества в процентах за несколько месяцев с применением различных фильтров.</span><span class="sxs-lookup"><span data-stu-id="cfa2b-120">Each report in this dashboard below shows query results on number of good calls, poor calls and poor call percentage for several months, with various filters applied.</span></span> 

![Образец отчета CQD](../../media/9e0723f7-f850-4d11-9ecd-7e8e013a8bed.png)

<span data-ttu-id="cfa2b-p106">Панель CQD разработана согласно методологии оценки качества вызовов (CQM), поэтому используемый по умолчанию набор отчетов соответствует процессу анализа, предусмотренному этой методологией. Пользователи могут также редактировать эти отчеты и создавать собственные отчеты с учетом конкретных задач. Однако существуют различные способы визуализации данных, и тот способ, который применяется в CQD, может не полностью соответствовать задачам каждого пользователя. В таких ситуациях пользователь может создавать нестандартные страницы отчетов с помощью интерфейсов API для данных и репозитория. В этом учебном пособии приведен ряд примеров.</span><span class="sxs-lookup"><span data-stu-id="cfa2b-p106">CQD is created following the Call Quality Methodology (CQM), so the default set of reports is designed to align with the investigation flow introduced by CQM. Users also have the flexibility to edit or create custom reports to meet their needs. However, since there are multiple ways to visualize the data, the visualization provided by CQD may not fully address the needs of every user. In such situations, a user can leverage the Data APIs and Repository APIs to create custom report pages. We will go through a series of examples in this tutorial.</span></span>

### <a name="how-the-dashboard-consumes-the-data-service"></a><span data-ttu-id="cfa2b-127">Использование службы данных на панели мониторинга</span><span class="sxs-lookup"><span data-stu-id="cfa2b-127">How the dashboard consumes the data service</span></span>

<span data-ttu-id="cfa2b-128">При переходе на домашнюю страницу CQD (например http://localhost/cqd), задайте отчета и соответствующих отчетов для проверка подлинности и авторизация пользователя извлекается из службы репозитория.</span><span class="sxs-lookup"><span data-stu-id="cfa2b-128">When navigating to the CQD homepage (e.g. http://localhost/cqd), the report set and corresponding reports for an authenticated and authorized user will be retrieved from the Repository Service.</span></span> <span data-ttu-id="cfa2b-129">Полный URL-адрес будет создан из идентификатора набора отчетов и месяц года (идентификатор набора отчетов — целое число после / #/ в разделе URL-адрес и по умолчанию текущего месяца года добавляется в конце идентификатора набора отчетов после косой черты).</span><span class="sxs-lookup"><span data-stu-id="cfa2b-129">A full URL will be constructed from the report-set ID and the year-month (report-set ID is the integer number after '/#/' section in URL, and by default the current year-month is appended at the end of the report-set ID after the slash).</span></span> <span data-ttu-id="cfa2b-130">Определения отчетов хранятся в формате JSON и после извлечения из службы репозитория вводятся в службу данных.</span><span class="sxs-lookup"><span data-stu-id="cfa2b-130">The report definitions are stored in JSON format and when retrieved from the Repository Service, will then be used as input to the Data Service.</span></span> <span data-ttu-id="cfa2b-131">В службе данных на основе введенных данных формируются запросы с многомерными выражениями (MDX), которые затем выполняются применительно к кубу для извлечения данных по каждому отчету.</span><span class="sxs-lookup"><span data-stu-id="cfa2b-131">The Data Service generates Multi-Dimension expressions (MDX) queries based on the input and then run these MDX queries against the Cube to retrieve data for each report.</span></span> 

### <a name="building-customized-reports"></a><span data-ttu-id="cfa2b-132">Составление нестандартных отчетов</span><span class="sxs-lookup"><span data-stu-id="cfa2b-132">Building customized reports</span></span>

<span data-ttu-id="cfa2b-p108">В CQD предусмотрены широкие возможности настройки отчетов, однако в некоторых ситуациях пользователям необходимы сводные данные по нескольким отчетам, созданным в CQD. Например, может потребоваться отчет, где в табличной форме показана доля вызовов низкого качества для всех возможных вариантов вызовов по проводной связи (пример результата такого отчета показан на рисунке):</span><span class="sxs-lookup"><span data-stu-id="cfa2b-p108">CQD already has a lot of flexibility in customizing reports, but there could be situations where users may want to aggregate data across multiple reports created in CQD. For example, there could be a need to create a report that shows the poor call percentages of all possible combinations of wired calls in a table (a result like the figure):</span></span>

![Таблица CQD](../../media/ef19d535-5da6-44a9-91f6-1ed3f30b96f1.png)

<span data-ttu-id="cfa2b-p109">Если пользователь работает на портале, предусмотренном в CQD, для извлечения и записи доли вызовов низкого качества из разных отчетов он должен перемещаться между отчетами; при сборе большого количества точек данных этот процесс может быть трудоемким. С помощью интерфейсов API для данных пользователи могут запрограммировать эту операцию; в этом случае данные извлекаются из службы данных (например, посредством вызовов AJAX).</span><span class="sxs-lookup"><span data-stu-id="cfa2b-p109">Using the Portal provided by CQD, a user would have to navigate to multiple reports to extract and record the poor call % for each one, which can be laborious if there are many data points that need to be collected. The Data APIs provide users with a programmatic way to accomplish this, by retrieving data from the Data Service (e.g. via AJAX calls).</span></span> 

 <span data-ttu-id="cfa2b-138">**Пример 1. Образец простого отчета**</span><span class="sxs-lookup"><span data-stu-id="cfa2b-138">**Example 1: Simple report sample**</span></span>

<span data-ttu-id="cfa2b-p110">Сначала рассмотрим простой пример. Предположим, что требуется отобразить на странице HTML количество потоков звуковых данных высокого и низкого качества за февраль 2015 года, как показано на рисунке:</span><span class="sxs-lookup"><span data-stu-id="cfa2b-p110">Let us take a simple example first. If we want to show the Audio Good Stream and the Audio Bad stream count of February 2015 on an HTML page like the figure:</span></span>

![Пример отчета CQD](../../media/f0e4e61f-1fa5-4d69-b192-f19e9612bf1c.png)

<span data-ttu-id="cfa2b-p111">Для этого необходимо отправить в службу данных вызов с надлежащими параметрами и вывести результаты запроса в таблице HTML. Ниже приведен образец кода JavaScript.</span><span class="sxs-lookup"><span data-stu-id="cfa2b-p111">What we need is to send a call to the Data Service with the proper parameters, and show the query results in an HTML table. The following is a sample of the JavaScript code:</span></span>

```        
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

<span data-ttu-id="cfa2b-144">Этот пример можно разбить на три этапа.</span><span class="sxs-lookup"><span data-stu-id="cfa2b-144">This example can be further deconstructed into three steps:</span></span>

1. <span data-ttu-id="cfa2b-145">Построение запросов (в примере, это значение задается в переменной «запрос»).</span><span class="sxs-lookup"><span data-stu-id="cfa2b-145">Construct the query (in the example this is defined in the variable 'query').</span></span> <span data-ttu-id="cfa2b-146">Запрос определяется как объект JSON, включающий в себя следующие данные.</span><span class="sxs-lookup"><span data-stu-id="cfa2b-146">The query is defined as a JSON object, which includes the following data:</span></span>

   <span data-ttu-id="cfa2b-147">a)</span><span class="sxs-lookup"><span data-stu-id="cfa2b-147">a.</span></span> <span data-ttu-id="cfa2b-148">Измерения (не обязательно).</span><span class="sxs-lookup"><span data-stu-id="cfa2b-148">Zero or more dimensions.</span></span> <span data-ttu-id="cfa2b-149">Каждое измерение обозначается параметром DataModelName.</span><span class="sxs-lookup"><span data-stu-id="cfa2b-149">Each dimension is indicated by a DataModelName.</span></span>

   <span data-ttu-id="cfa2b-150">б)</span><span class="sxs-lookup"><span data-stu-id="cfa2b-150">b.</span></span> <span data-ttu-id="cfa2b-151">Фильтры (не обязательно).</span><span class="sxs-lookup"><span data-stu-id="cfa2b-151">Zero or more filters.</span></span> <span data-ttu-id="cfa2b-152">Для каждого фильтра задаются следующие составляющие:</span><span class="sxs-lookup"><span data-stu-id="cfa2b-152">Each filter has:</span></span>

   - <span data-ttu-id="cfa2b-153">DataModelName (измерение, для которого будет задан фильтр);</span><span class="sxs-lookup"><span data-stu-id="cfa2b-153">DataModelName (the dimension that will have the filter set).</span></span>

   - <span data-ttu-id="cfa2b-154">значение (для сравнения с применением операнда);</span><span class="sxs-lookup"><span data-stu-id="cfa2b-154">Value (the value that will be compared by the operand).</span></span>

   - <span data-ttu-id="cfa2b-155">Операнд (тип сравнения, 0 означает «Равно»).</span><span class="sxs-lookup"><span data-stu-id="cfa2b-155">Operand (comparison type, 0 means "Equal").</span></span>

     <span data-ttu-id="cfa2b-156">в.</span><span class="sxs-lookup"><span data-stu-id="cfa2b-156">c.</span></span> <span data-ttu-id="cfa2b-157">Хотя бы один показатель.</span><span class="sxs-lookup"><span data-stu-id="cfa2b-157">One or more measurements.</span></span>

2. <span data-ttu-id="cfa2b-158">Отправка запроса в службу данных посредством вызова AJAX.</span><span class="sxs-lookup"><span data-stu-id="cfa2b-158">Send the query to Data Service via AJAX call.</span></span> <span data-ttu-id="cfa2b-159">Необходимо указать следующие параметры запроса.</span><span class="sxs-lookup"><span data-stu-id="cfa2b-159">The following request parameters need to be provided:</span></span>

   <span data-ttu-id="cfa2b-160">a)</span><span class="sxs-lookup"><span data-stu-id="cfa2b-160">a.</span></span> <span data-ttu-id="cfa2b-161">url (в качестве URL-адреса следует указать http://[имя_сервера]/QoEDataService/RunQuery).</span><span class="sxs-lookup"><span data-stu-id="cfa2b-161">url (which should be http://[ServerName]/QoEDataService/RunQuery).</span></span>

   <span data-ttu-id="cfa2b-162">б)</span><span class="sxs-lookup"><span data-stu-id="cfa2b-162">b.</span></span> <span data-ttu-id="cfa2b-163">данные (это строковое представление объекта JSON, определенный в переменной «запрос»).</span><span class="sxs-lookup"><span data-stu-id="cfa2b-163">data (this is the string representation of the JSON object defined in the 'query' variable).</span></span> <span data-ttu-id="cfa2b-164">Служба данных возвращает результаты запроса в виде параметра функции обратного вызова для успешного выполнения.</span><span class="sxs-lookup"><span data-stu-id="cfa2b-164">Data Service will return the query results as a parameter of the call back function for success.</span></span>

   <span data-ttu-id="cfa2b-165">в.</span><span class="sxs-lookup"><span data-stu-id="cfa2b-165">c.</span></span> <span data-ttu-id="cfa2b-166">Введите (для QoEDataService, RunQuery принимает только «ПУБЛИКАЦИЯ» запросы).</span><span class="sxs-lookup"><span data-stu-id="cfa2b-166">type (for QoEDataService, RunQuery only accepts 'POST' requests).</span></span>

   <span data-ttu-id="cfa2b-167">г.</span><span class="sxs-lookup"><span data-stu-id="cfa2b-167">d.</span></span> <span data-ttu-id="cfa2b-168">async (признак, указывающий, должен ли вызов AJAX быть синхронным или асинхронным).</span><span class="sxs-lookup"><span data-stu-id="cfa2b-168">async (a flag indicating whether the AJAX call should be synchronous or asynchronous).</span></span>

   <span data-ttu-id="cfa2b-169">e.</span><span class="sxs-lookup"><span data-stu-id="cfa2b-169">e.</span></span> <span data-ttu-id="cfa2b-170">contentType (должен быть «application/json»).</span><span class="sxs-lookup"><span data-stu-id="cfa2b-170">contentType (should be "application/json").</span></span>

   <span data-ttu-id="cfa2b-171">f.</span><span class="sxs-lookup"><span data-stu-id="cfa2b-171">f.</span></span> <span data-ttu-id="cfa2b-172">success (функция обратного вызова в случае успешного завершения вызова AJAX).</span><span class="sxs-lookup"><span data-stu-id="cfa2b-172">success (call-back function for when the AJAX call finishes successfully).</span></span>

   <span data-ttu-id="cfa2b-173">g.</span><span class="sxs-lookup"><span data-stu-id="cfa2b-173">g.</span></span> <span data-ttu-id="cfa2b-174">error (функция обработки ошибок в случае сбоя вызова AJAX).</span><span class="sxs-lookup"><span data-stu-id="cfa2b-174">error (error handling function for when AJAX call fails).</span></span>

3. <span data-ttu-id="cfa2b-175">Внедрение данных в элементы div в коде HTML (в данном примере кода для этого после успешного выполнения запроса AJAX осуществляется анонимный вызов функции).</span><span class="sxs-lookup"><span data-stu-id="cfa2b-175">Put data into div elements in the HTML (in the example in the code, this is done via the anonymous function call after the AJAX request is completed successfully).</span></span>

<span data-ttu-id="cfa2b-p124">При внедрении кода JavaScript в страницу HTML на этой странице отображается отчет, подобный показанному на рисунке. Ниже код HTML показан полностью:</span><span class="sxs-lookup"><span data-stu-id="cfa2b-p124">Enclosing the JavaScript code into an HTML page, and the page will show a report like the one shown in the figure. The full html is as follows:</span></span>

```
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

<span data-ttu-id="cfa2b-p125">Такой отчет по-прежнему очень прост. Пользователь может настроить его, добавляя дополнительные показатели, измерения или фильтры. Например, если требуется отобразить долю вызовов низкого качества в AppSharing, необходимо добавить новый показатель, связанный с AppSharing. Для отображения всех вызовов TCP в сравнении с вызовами UDP следует добавить новое измерение, относящееся к типу транспортного протокола. Для отображения количества вызовов низкого качества в конкретном здании следует добавить новый фильтр, позволяющий выбрать входящие и исходящие вызовы в этом здании.</span><span class="sxs-lookup"><span data-stu-id="cfa2b-p125">So far, the report is still very simple. The user can add more measurements, dimensions, or filters to customize the report. For example, if you want to show AppSharing poor call percentage, then a new measurement regarding AppSharing needs to be added. If you want to show all TCP calls v.s. UDP calls, a new dimension regarding transportation type should be added. If you want to show the number of poor calls within a specific building, then a new filter should be added to select the calls to and from that building.</span></span>

 <span data-ttu-id="cfa2b-184">**Пример 2. Образец определения отчета**</span><span class="sxs-lookup"><span data-stu-id="cfa2b-184">**Example 2: Report definition sample**</span></span>

<span data-ttu-id="cfa2b-p126">Некоторые пользователи могут не знать, как составляется полный список показателей/измерений/фильтров и соответствующих значений при формировании запроса. В этом случае можно перейти на портал, сформировать отчет в редакторе отчетов, найти строку JSON в определении отчета и скопировать ее в пользовательский отчет.</span><span class="sxs-lookup"><span data-stu-id="cfa2b-p126">It might be difficult for someone to figure out how to write the full list of measurements/dimensions/filters and their corresponding values when constructing a query. In this case, you can go to the Portal, build a report using the report editor, and view the JSON string of the report definition, and then copy the definition into a custom report.</span></span> 

<span data-ttu-id="cfa2b-p127">В этом примере будет создана веб-страница, подобная показанной на рисунке; если пользователь введет на этой веб-странице идентификатор любого существующего набора отчетов (или отчета), на ней отобразится определение этого набора отчетов или отчета. После этого пользователь может включить строку JSON для каждого отчета в код, аналогичный рассмотренному в примере 1, и составить любой требуемый отчет.</span><span class="sxs-lookup"><span data-stu-id="cfa2b-p127">In this example, we will create a web page like the one shown in the figure where a user can enter the ID of any existing report set (or report) and show the definition of the report set or report on the web page. The user can then plug the JSON string of each report into code similar to the one shown in Example 1 and construct any customized report the user desires.</span></span> 

![Пример CQD](../../media/01c45c23-c4d2-47b8-819f-0888cf71260f.png)

<span data-ttu-id="cfa2b-p128">При создании средства просмотра определений отчетов потребуется отправить вызовы в службу репозитория для извлечения определения каждого требуемого набора отчетов, представленного в виде строки JSON. Интерфейс API репозитория возвращает определение набора отчетов по заданному определению набора отчетов.</span><span class="sxs-lookup"><span data-stu-id="cfa2b-p128">To create the report definition viewer tool, we need to send calls to Repository Service to retrieve the JSON string representations of the definitions of every report-set we want. The Repository API will return report-set definition based on a given report set ID.</span></span> 

<span data-ttu-id="cfa2b-192">В качестве примера рассмотрим приведенный ниже код.</span><span class="sxs-lookup"><span data-stu-id="cfa2b-192">A quick example is as follows, the code contains a block that is a simple example to send a query to the Repository service to get the contents of a repository item based on its identifier.</span></span> <span data-ttu-id="cfa2b-193">Он содержит блок, который служит простым образцом отправки в службу репозитория запроса на получение содержимого элемента из репозитория по идентификатору этого элемента.</span><span class="sxs-lookup"><span data-stu-id="cfa2b-193">And the next portion of code (processReportSetData method) is sending AJAX calls to get the definition of each report within that report set.</span></span> <span data-ttu-id="cfa2b-194">Следующий фрагмент кода (метод processReportSetData) обеспечивает отправку вызовов AJAX для получения определения каждого отчета из данного набора.</span><span class="sxs-lookup"><span data-stu-id="cfa2b-194">Since the ID in the CQD web portal is the ID of a report set, the AJAX call will return a report set item.</span></span> <span data-ttu-id="cfa2b-195">Более подробные сведения в API репозитория и в частности, GetItems, можно найти в списке [Получение элементов](get-items.md).</span><span class="sxs-lookup"><span data-stu-id="cfa2b-195">More detail on the Repository API and specifically, GetItems, can be found in the [Get Items](get-items.md).</span></span> 

```
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

<span data-ttu-id="cfa2b-196">Результатом приведенного выше кода является веб-страница, подобная показанной на рисунке (без определения отчета при первом посещении).</span><span class="sxs-lookup"><span data-stu-id="cfa2b-196">The above will result in a web page like the one in the figure (without the report definition upon initial visit).</span></span> <span data-ttu-id="cfa2b-197">Получите идентификатор набора отчетов из портала CQD (после / #/ вход в портал CQD URL-адрес (например:</span><span class="sxs-lookup"><span data-stu-id="cfa2b-197">Get the report set ID from CQD portal (it is after '/#/' sign in CQD portal URL (E.g.</span></span> <span data-ttu-id="cfa2b-198">на первом рисунке отчета идентификатора набора является 3024) и поместите этот идентификатор набора отчета в раздел входных данных веб-страницы.</span><span class="sxs-lookup"><span data-stu-id="cfa2b-198">in the first figure the report set ID is 3024), and put this report set ID into the input section of this web page.</span></span> <span data-ttu-id="cfa2b-199">Нажмите кнопку «Загрузить» и просмотреть полное определение (показатели, измерения списки фильтров) набор отчетов.</span><span class="sxs-lookup"><span data-stu-id="cfa2b-199">Press the "load" button and see the full definition (measurements, dimensions, filters lists) of the report set.</span></span>

<span data-ttu-id="cfa2b-200">Таким образом, чтобы быстро получить полное определение набора/report отчет.</span><span class="sxs-lookup"><span data-stu-id="cfa2b-200">In summary, in order to quickly get the full definition of a report/report set.</span></span> <span data-ttu-id="cfa2b-201">Для этого требуется выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="cfa2b-201">The steps are:</span></span>

1. <span data-ttu-id="cfa2b-202">Перейдите к порталу и использовать редактор запросов для настройки report (щелкните «Изменить» над отчет для редактирования, добавление, удаление показатели, измерения/фильтры, а затем сохранить отчет).</span><span class="sxs-lookup"><span data-stu-id="cfa2b-202">Go to the Portal and use the query editor to customize a report (click the "Edit" button above a report to edit, add, remove measurements/dimensions/filters, and then save the report).</span></span>

2. <span data-ttu-id="cfa2b-203">Получите идентификатор набора отчетов из URL-адреса (целое число после / #/ входа в URL-адрес).</span><span class="sxs-lookup"><span data-stu-id="cfa2b-203">Get the report set ID from URL (the integer after '/#/' sign in URL).</span></span>

3. <span data-ttu-id="cfa2b-204">Вызовите веб-страницу определения отчета, созданную в примере 2, введите идентификатора набора отчетов и извлеките полное определение этого набора (которое будет применяться в вызовах интерфейса API для данных).</span><span class="sxs-lookup"><span data-stu-id="cfa2b-204">Launch this Report Definition web page created in Example 2, and enter the report set ID and retrieve the full definition of a report set (to use in Data API calls).</span></span>

   <span data-ttu-id="cfa2b-205">**Пример 3. Образец системы показателей**</span><span class="sxs-lookup"><span data-stu-id="cfa2b-205">**Example 3: Scorecard sample**</span></span>

<span data-ttu-id="cfa2b-p132">Перейдем к более сложной задаче. Требуется создать веб-страницу, подобную показанной на рисунке. Поскольку при этом увеличивается объем обрабатываемых данных, следует обновить код из примера 1 (с помощью сформированной в примере 2 веб-страницы, позволяющей извлекать полное определение любого отчета).</span><span class="sxs-lookup"><span data-stu-id="cfa2b-p132">Time for a more complicated task. What if we want to create a web page like the figure? We need to update Example 1, (with the help of the web page generated in Example 2 to retrieve the full definition of any report) so that we can handle larger amount of data.</span></span>

<span data-ttu-id="cfa2b-p133">В данном случае требуется обновить список показателей и измерений. Для добавления/изменения показателя и/или размерности следует выполнить инструкции из примера 2 и извлечь полное определение отчета, в том числе полные списки показателей и измерений. Включите полное определение отчета в образец кода.</span><span class="sxs-lookup"><span data-stu-id="cfa2b-p133">In this case, we need to update the measurement and dimension list. The way to figure out how to add/edit a measurement and/or a dimension is to follow the instructions in Example 2, and retrieve the full report definition, including the full measurement and dimension lists. Plug the full report definition into the sample code.</span></span> 

<span data-ttu-id="cfa2b-212">Ниже приведена пошаговая процедура получения показанной на рисунке страницы системы показателей на основе кода из примера 1.</span><span class="sxs-lookup"><span data-stu-id="cfa2b-212">Here are the detailed steps to get to the scorecard page in the figure from the sample provided in Example 1:</span></span>

1. <span data-ttu-id="cfa2b-213">Обновление измерений в переменной «запрос» из `[Measures].[Audio Good Streams JPDR Count]` и `[Measures].[Audio Poor Streams JPDR Count]` для `[Measures].[AudioPoorJPDRPercentage]`.</span><span class="sxs-lookup"><span data-stu-id="cfa2b-213">Update Measurements in the 'query' variable from  `[Measures].[Audio Good Streams JPDR Count]` and `[Measures].[Audio Poor Streams JPDR Count]` to `[Measures].[AudioPoorJPDRPercentage]`.</span></span> 

2. <span data-ttu-id="cfa2b-214">Обновите фильтры.</span><span class="sxs-lookup"><span data-stu-id="cfa2b-214">Update the filters.</span></span> <span data-ttu-id="cfa2b-215">Данные JSON для фильтров в примере 1 имеет один фильтр, которая задается в измерении `[StartDate].[Month]`.</span><span class="sxs-lookup"><span data-stu-id="cfa2b-215">The JSON data for Filters in Example 1 has one filter, which is set on the dimension  `[StartDate].[Month]`.</span></span> <span data-ttu-id="cfa2b-216">Поскольку фильтры являются массивом JSON, к списку фильтров можно добавлять дополнительные измерения.</span><span class="sxs-lookup"><span data-stu-id="cfa2b-216">Since Filters is a JSON array, additional dimensions can be added to the list of filters.</span></span> <span data-ttu-id="cfa2b-217">Например чтобы получить клиентов сервера внутри проводной вызовы для «currentMonth», у нас есть следующие фильтры:</span><span class="sxs-lookup"><span data-stu-id="cfa2b-217">For example, to get the server-client inside wired calls for the "currentMonth", we should have the following filters:</span></span>

   ```
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

   <span data-ttu-id="cfa2b-218">Здесь измерение `[Scenarios].[ScenarioPair]` задано значение равно `[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]`.</span><span class="sxs-lookup"><span data-stu-id="cfa2b-218">Here the dimension  `[Scenarios].[ScenarioPair]` is set to equal `[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]`.</span></span> <span data-ttu-id="cfa2b-219">`[Scenario.][ScenarioPair]` — Это специальные измерение, созданное для упрощения создания отчета.</span><span class="sxs-lookup"><span data-stu-id="cfa2b-219">The  `[Scenario.][ScenarioPair]` is a special dimension created to simplify report creation.</span></span> <span data-ttu-id="cfa2b-220">Она имеет шесть значения, соответствующие `[FirstIsServer], [SecondIsServer], [FirstInside], [SecondIsServer], [FirstConnectionType], [SecondConnectionType]`.</span><span class="sxs-lookup"><span data-stu-id="cfa2b-220">It has six values corresponding to `[FirstIsServer], [SecondIsServer], [FirstInside], [SecondIsServer], [FirstConnectionType], [SecondConnectionType]`.</span></span> <span data-ttu-id="cfa2b-221">Таким образом, для определения не требуется сочетание шести фильтров: достаточно одного фильтра.</span><span class="sxs-lookup"><span data-stu-id="cfa2b-221">So instead of using a combination of 6 filters to define a scenario, we only need to use 1 filter.</span></span> <span data-ttu-id="cfa2b-222">В нашем примере значение `[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]` преобразование в сценарий где: сначала — это сервер, во-вторых не является сервером, сначала находится внутри, во-вторых находится внутри, проводное первый тип подключения, а второй тип подключения — проводной, которая является точное определение " Сервер Client-Inside проводной сети».</span><span class="sxs-lookup"><span data-stu-id="cfa2b-222">In our example, the value  `[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]` translates to the scenario where: first is server, second is not server, first is inside, second is inside, first connection type is wired, and second connection type is wired, which is the exact definition of "Server-Client-Inside Wired".</span></span>

3. <span data-ttu-id="cfa2b-p136">Создайте по одному фильтру для каждого сценария. В системе показателей на рисунке каждая строка представляет отдельный сценарий, для которого задается отдельный фильтр (измерения и показатели являются общими для всех сценариев).</span><span class="sxs-lookup"><span data-stu-id="cfa2b-p136">Create one filter set per scenario. Each row in the scorecard, in the figure, represents a different scenario, which will be a different filter (while the dimensions and measurements stay the same).</span></span> 

4. <span data-ttu-id="cfa2b-p137">Выполните синтаксический разбор результатов вызовов AJAX и поместите их в правильное положение в таблице. Поскольку эта операция выполняется преимущественно средствами HTML и JavaScript, ее детали здесь опущены. Соответствующий код приведен в приложении A.</span><span class="sxs-lookup"><span data-stu-id="cfa2b-p137">Parse the results from the AJAX calls and place them in the correct position of the table. Since this is mostly HTML and JavaScript manipulation, we will not go into the details here. Instead, the code is provided in Appendix A.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="cfa2b-228">При включении общего доступа к междоменных ресурсов (CORS) пользователи могут возникнуть ошибки, как «отсутствует «Доступ элемент управления-разрешить-происхождения» заголовок присутствует запрошенный ресурс.</span><span class="sxs-lookup"><span data-stu-id="cfa2b-228">If Cross-Origin Resource Sharing (CORS) is enabled, users may encounter errors like "No 'Access-Control-Allow-Origin' header is present on the requested resource.</span></span> <span data-ttu-id="cfa2b-229">Происхождение «null» таким образом не разрешен доступ».</span><span class="sxs-lookup"><span data-stu-id="cfa2b-229">Origin 'null' is therefore not allowed access".</span></span> <span data-ttu-id="cfa2b-230">Чтобы решить эту проблему, поместите HTML-файл в папке, где установлены портала (по умолчанию, оно должно быть `%SystemDrive%\Program Files\Skype for Business 2015 CQD\CQD)`.</span><span class="sxs-lookup"><span data-stu-id="cfa2b-230">To resolve the issue, place the HTML file under the folder where the Portal is installed (by default, it should be `%SystemDrive%\Program Files\Skype for Business 2015 CQD\CQD)`.</span></span> <span data-ttu-id="cfa2b-231">Получить доступ к HTML-код через любой браузер с URL-адрес `http://<servername>/cqd/<html_file_name>`.</span><span class="sxs-lookup"><span data-stu-id="cfa2b-231">Then access the html through any browser with the URL  `http://<servername>/cqd/<html_file_name>`.</span></span> <span data-ttu-id="cfa2b-232">(— Это URL-адрес по умолчанию для локальной панели мониторинга CQD `http://<servername>/cqd.`)</span><span class="sxs-lookup"><span data-stu-id="cfa2b-232">(The default URL for local CQD dashboard is  `http://<servername>/cqd.`)</span></span> 

### <a name="appendix-a"></a><span data-ttu-id="cfa2b-233">Приложение A</span><span class="sxs-lookup"><span data-stu-id="cfa2b-233">Appendix A</span></span>

<span data-ttu-id="cfa2b-234">Код HTML для примера 3 (образец системы показателей):</span><span class="sxs-lookup"><span data-stu-id="cfa2b-234">HTML code for Example 3 (Scorecard sample):</span></span>

```
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
