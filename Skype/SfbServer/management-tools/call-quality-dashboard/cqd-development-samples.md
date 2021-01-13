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
# <a name="cqd-development-samples"></a>Примеры разработки CQD

**Сводка:** Просмотрите учебник и примеры разработки для панели мониторинга качества вызовов. Панель мониторинга качества звонков — это инструмент для Skype для бизнеса Server.

В этой статье приводится учебник и примеры по разработке панели мониторинга качества вызовов (CQD).

## <a name="call-quality-dashboard-cqd-development-samples"></a>Примеры разработки панели мониторинга качества вызовов (CQD)

Учебник. Создание настраиваемой презентации отчета с помощью API службы данных и репозитория CQD.

### <a name="introduction-to-cqd"></a>Введение в CQD

CQD обеспечивает быстрый и простой доступ к сводной информации о качестве звонков для локального развертывания Skype для бизнеса Server. CQD состоит из трех компонентов: базы данных архива QoE, куба и портала. Портал — это основной уровень представления, который можно разделить на три следующих компонента:

1. Data Service, which is accessible for authenticated users through the [Data API for Call Quality Dashboard (CQD) in Skype for Business Server](data-api.md).

2. Служба репозитория, доступная для пользователей, подлинность которых прошла через API репозитория для панели мониторинга качества звонков [(CQD) в Skype для бизнеса Server.](repository-api.md)

3. Веб-портал, который является интерфейсом на основе HTML5, с которым пользователи CQD видят и взаимодействуют. Эта возможность доступна для пользователей, подлинность в которые недоступна.

Отчеты, показанные на веб-портале, группются в "наборы отчетов". На рисунке показан набор отчетов с двумя отчетами. В каждом отчете на приведенной ниже информационной панели показаны результаты запроса по количеству звонков низкого качества и процента звонков низкого качества в течение нескольких месяцев, при этом применяются различные фильтры. 

![Пример отчета CQD](../../media/9e0723f7-f850-4d11-9ecd-7e8e013a8bed.png)

CQD создается в соответствии с методологией качества вызовов (CQM), поэтому набор отчетов по умолчанию разработан в соответствии с потоком исследования, введенным CQM. Пользователи также могут редактировать или создавать настраиваемые отчеты в своих потребностях. Тем не менее, поскольку существует несколько способов визуализации данных, визуализация, предоставляемая CQD, может не полностью решить потребности каждого пользователя. В таких случаях пользователь может использовать API данных и API репозитория для создания пользовательских страниц отчетов. В этом руководстве мы проймем ряд примеров.

### <a name="how-the-dashboard-consumes-the-data-service"></a>Как панель мониторинга будет использовать службу данных

При переходе к домашней странице CQD (например, набор отчетов и соответствующие отчеты для пользователя, подлинность и авторизованного пользователя будут извлечены из службы репозитория. http://localhost/cqd) Полный URL-адрес будет создан из ИД набора отчетов и года-месяца (ид набора отчетов — это целый номер после раздела "/#/" в URL-адресе, а по умолчанию текущий год-месяц после косой черты будет в конце набора отчетов). Определения отчетов хранятся в формате JSON и при извлечении из службы репозитория будут использоваться в качестве входных данных для службы данных. Служба данных создает запросы многомерных выражений (MDX) на основе входных данных и затем вызывает эти запросы многомерных выражений к кубу, чтобы получить данные для каждого отчета. 

### <a name="building-customized-reports"></a>Создание настраиваемых отчетов

В CQD уже есть большая гибкость в настройке отчетов, но могут возникнуть ситуации, в которых пользователям может потребоваться агрегировать данные в нескольких отчетах, созданных в CQD. Например, может понадобиться создать отчет, который показывает процент звонков низкого качества для всех возможных комбинаций проводных звонков в таблице (результат, например, на рисунке):

![Таблица CQD](../../media/ef19d535-5da6-44a9-91f6-1ed3f30b96f1.png)

С помощью портала, предоставленного CQD, пользователю потребуется перейти к нескольким отчетам, чтобы извлечь и записать процент вызовов низкого качества для каждого из них, что может быть трудоемким, если требуется собрать большое количество точек данных. API данных предоставляют пользователям программный способ получить данные из службы данных (например, с помощью вызовов AJAX). 

 **Пример 1. Пример простого отчета**

Сначала рассмотрим простой пример. Если мы хотим показать количество потоков Audio Good Stream и Audio Bad за февраль 2015 г. на HTML-странице, например на рисунке:

![Пример отчета CQD](../../media/f0e4e61f-1fa5-4d69-b192-f19e9612bf1c.png)

Нам нужно отправить вызов в службу данных с правильными параметрами и показать результаты запроса в HTML-таблице. Ниже приводится пример кода JavaScript.

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

Этот пример можно далее разрезать на три этапа:

1. Создание запроса (в примере он определен в переменной "query"). Запрос определяется как объект JSON, который включает следующие данные:

   а. Ноль или больше измерений. Каждое измерение указывается dataModelName.

   б. Ноль или больше фильтров. Каждый фильтр имеет:

   - DataModelName (измерение, которое будет иметь набор фильтров).

   - Значение (значение, которое будет сравниваться операндом).

   - Операнд (тип сравнения, 0 означает "Равно").

     c. Один или несколько показателей.

2. Отправьте запрос в службу данных с помощью вызова AJAX. Должны быть предоставлены следующие параметры запроса:

   а. url(который должен быть http://[Имя сервера]/QoEDataService/RunQuery).

   б. data (это строка представления объекта JSON, определенного в переменной "query"). Служба данных возвращает результаты запроса в качестве параметра функции обратного вызова для успешного выполнения.

   c. type (для QoEDataService RunQuery принимает только запросы POST).

   г. асинхронный (флаг, указывающий, должен ли вызов AJAX быть синхронным или асинхронным).

   д. contentType (должно быть "application/json").

   е. успешно (функция обратного вызова для успешного завершения вызова AJAX).

   ж. ошибка (функция обработки ошибок при сбойе вызова AJAX).

3. Поместите данные в элементы div в HTML (в примере в коде это делается с помощью анонимного вызова функции после успешного завершения запроса AJAX).

Заключив код JavaScript в HTML-страницу, на странице будет показан отчет, похожий на показанный на рисунке. Полный html-код:

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

Пока что отчет по-прежнему очень прост. Пользователь может добавить дополнительные измерения, измерения или фильтры для настройки отчета. Например, если вы хотите показать процент вызовов AppSharing низкого качества, необходимо добавить новое измерение, касающееся AppSharing. Если вы хотите показать все вызовы TCP v.s. Вызовы UDP, следует добавить новое измерение, касающееся типа транспорта. Если вы хотите показать количество звонков низкого качества в определенном здании, необходимо добавить новый фильтр для выбора вызовов в это здание и из него.

 **Пример 2. Пример определения отчета**

При составлении запроса может быть сложно понять, как записать полный список измерений, измерений/фильтров и соответствующих им значений. В этом случае можно перейти на портал, создать отчет с помощью редактора отчетов и просмотреть строку JSON определения отчета, а затем скопировать определение в настраиваемый отчет. 

В этом примере мы создадим веб-страницу, похожую на показанную на рисунке, где пользователь может ввести ИД любого существующего набора отчетов (или отчета) и показать определение набора отчетов или отчета на веб-странице. Затем пользователь может подключить строку JSON каждого отчета к коду, аналогичному показанного в примере 1, и создать любой настраиваемый отчет, который будет желаем пользователю. 

![Пример CQD](../../media/01c45c23-c4d2-47b8-819f-0888cf71260f.png)

Чтобы создать средство просмотра определений отчетов, необходимо отправить вызовы в службу репозитория, чтобы получить строковые представления определений каждого набора отчетов, который нам нужен, в строке JSON. API репозитория возвращает определение набора отчетов на основе заданного ИД набора отчетов. 

Краткий пример: код содержит блок, который является простым примером отправки запроса в службу репозитория для получения содержимого элемента репозитория на основе его идентификатора. А следующая часть кода (метод processReportSetData) отправляет вызовы AJAX для получения определения каждого отчета в этом наборе отчетов. Так как ИД на веб-портале CQD является ИД набора отчетов, вызов AJAX возвращает элемент набора отчетов. Подробнее об API репозитория и, в частности, GetItems, можно найти в меню ["Получить элементы".](get-items.md) 

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

В результате вышеуказанная веб-страница будет выглядеть так же, как на рисунке (без определения отчета при первоначальном посещении). Получите ИД набора отчетов с портала CQD (это после знака "/#/" в URL-адресе портала CQD (например, На первом рисунке ид набора отчетов — 3024, и этот ид набора отчетов помещался во входной раздел этой веб-страницы. Нажмите кнопку "загрузить" и посмотрите полное определение (измерения, измерения, списки фильтров) набора отчетов.

Таким образом, чтобы быстро получить полное определение набора отчетов и отчетов. Ниже описана последовательность действий.

1. Перейдите на портал и используйте редактор запросов для настройки отчета (нажмите кнопку "Изменить" над отчетом, чтобы изменить, добавить, удалить измерения, измерения/фильтры, а затем сохранить отчет).

2. Получите по URL-адресу ИД набора отчетов (это будет вся после URL-адреса для знака "/#/").

3. Запустите эту веб-страницу определения отчета, созданную в примере 2, и введите ИД набора отчетов и извлекает полное определение набора отчетов (для использования в вызовах API данных).

   **Пример 3. Пример системы показателей**

Время для более сложной задачи. Что делать, если мы хотим создать веб-страницу, похожую на рисунок? Нам необходимо обновить пример 1 (с помощью веб-страницы, сгенерированной в примере 2, чтобы получить полное определение любого отчета), чтобы можно было обрабатывать больший объем данных.

В этом случае нам необходимо обновить список измерений и показателей. Чтобы узнать, как добавить или изменить измерение, выполните инструкции в примере 2 и извлекаете полное определение отчета, включая полные списки измерений и измерений. Подключите полное определение отчета к примеру кода. 

Ниже описаны подробные инструкции для получения страницы системы показателей на рисунке из примера, представленного в примере 1:

1. Обновление показателей в переменной "query" от  `[Measures].[Audio Good Streams JPDR Count]` и `[Measures].[Audio Poor Streams JPDR Count]` до `[Measures].[AudioPoorJPDRPercentage]` . 

2. Обновим фильтры. Данные JSON для фильтров в примере 1 имеет один фильтр, который устанавливается в  `[StartDate].[Month]` измерении. Так как фильтры — это массив JSON, в список фильтров можно добавить дополнительные измерения. Например, чтобы получить сервер-клиент внутри проводных вызовов для "currentMonth", у нас должны быть следующие фильтры:

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

   Здесь измерение  `[Scenarios].[ScenarioPair]` равно `[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]` . Это  `[Scenario.][ScenarioPair]` специальное измерение, созданное для упрощения создания отчетов. Он имеет шесть значений, соответствующих `[FirstIsServer], [SecondIsServer], [FirstInside], [SecondIsServer], [FirstConnectionType], [SecondConnectionType]` . Поэтому вместо использования сочетания 6 фильтров для определения сценария необходимо использовать только один фильтр. В нашем примере значение преобразуется в сценарий, где: первый — сервер, второй — не сервер, второй — внутри, первый тип подключения проводной, второй тип подключения проводной, то есть точное определение  `[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]` "Server-Client-Inside Wired".

3. Создайте один набор фильтров для каждого сценария. Каждая строка системы показателей, представленная на рисунке, представляет разные сценарии, которые будут представлять собой разные фильтры (в то время как измерения и показатели остаются одинаковыми). 

4. Анализ результатов вызовов AJAX и поместите их в правильное положение таблицы. Так как это в основном манипуляции с HTML и JavaScript, здесь мы не будем подробно перейти к этим сведениям. Вместо этого код предоставляется в приложении А.

    > [!NOTE]
    >  Если включен общий доступ к ресурсам между источниками (CORS), у пользователей могут возникнуть такие ошибки, как "Нет загона "Access-Control-Allow-Origin" в запрашиваемом ресурсе. Поэтому источнику "null" не разрешен доступ". Чтобы устранить проблему, поместите HTML-файл в папку, в которой установлен портал (по умолчанию он должен быть `%SystemDrive%\Program Files\Skype for Business 2015 CQD\CQD)` . Затем доступ к HTML-коду можно получить через любой браузер с URL-адресом. `http://<servername>/cqd/<html_file_name>` (URL-адрес по умолчанию для локальной панели мониторинга CQD:  `http://<servername>/cqd.` ) 

### <a name="appendix-a"></a>Приложение A

HTML-код для примера 3 (пример системы показателей):

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
