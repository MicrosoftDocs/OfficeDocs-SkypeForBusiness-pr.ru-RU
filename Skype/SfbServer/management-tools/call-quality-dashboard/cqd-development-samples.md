---
title: Примеры разработки CQD
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
ms.openlocfilehash: 994a26af99ec141b531ed3011a42f626c0c62886
ms.sourcegitcommit: b680505c5dad435d98fbd0b235e0e7c67b9d8c9c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2018
ms.locfileid: "26035745"
---
# <a name="cqd-development-samples"></a>Примеры разработки CQD

**Сводка:** Обзор разработки и учебных примеров для панели мониторинга качества звонков. Панель мониторинга качества звонков — это средство для Скайп для Business Server.

Эта статья представляет собой учебное пособие по разработке панели мониторинга качества вызовов (CQD) с примерами.

## <a name="call-quality-dashboard-cqd-development-samples"></a>Примеры разработки панели мониторинга качества вызовов (CQD)

Учебное пособие. Построение презентаций нестандартных отчетов с помощью интерфейсов API для службы данных и службы репозитория в CQD.

### <a name="introduction-to-cqd"></a>Введение в CQD

CQD обеспечивает быстрый и удобный доступ к сводным данным о качестве вызова в локальных развертываниях Skype для бизнеса Server. CQD состоит из трех компонентов: архивной базы данных качества взаимодействия, куба и портала. Портал – это основной уровень презентации, который в свою очередь подразделяется на три следующих компонента:

1. Службы данных, доступном для прошедших проверку подлинности пользователей с помощью [Data API для вызова качества панели мониторинга (CQD) в Скайп для Business Server](data-api.md).

2. Репозиторий служба доступна для прошедших проверку подлинности пользователей с помощью [API репозитория для вызова качества панели мониторинга (CQD) в Скайп для Business Server](repository-api.md).

3. веб-портал — интерфейс на основе HTML5, доступный пользователям CQD для просмотра и взаимодействия. Пользователи должны пройти проверку подлинности.

Отчеты, отображаемые на веб-портал сгруппированы в «отчет о наборы». На рисунке показан такой набор, состоящий из двух отчетов. В каждом отчете на показанной ниже панели мониторинга отображаются результаты запроса, указывающие количество вызовов высокого качества, количество вызовов низкого качества и долю вызовов низкого качества в процентах за несколько месяцев с применением различных фильтров. 

![Образец отчета CQD](../../media/9e0723f7-f850-4d11-9ecd-7e8e013a8bed.png)

Панель CQD разработана согласно методологии оценки качества вызовов (CQM), поэтому используемый по умолчанию набор отчетов соответствует процессу анализа, предусмотренному этой методологией. Пользователи могут также редактировать эти отчеты и создавать собственные отчеты с учетом конкретных задач. Однако существуют различные способы визуализации данных, и тот способ, который применяется в CQD, может не полностью соответствовать задачам каждого пользователя. В таких ситуациях пользователь может создавать нестандартные страницы отчетов с помощью интерфейсов API для данных и репозитория. В этом учебном пособии приведен ряд примеров.

### <a name="how-the-dashboard-consumes-the-data-service"></a>Использование службы данных на панели мониторинга

При переходе на домашнюю страницу CQD (например http://localhost/cqd), задайте отчета и соответствующих отчетов для проверка подлинности и авторизация пользователя извлекается из службы репозитория. Полный URL-адрес будет создан из идентификатора набора отчетов и месяц года (идентификатор набора отчетов — целое число после / #/ в разделе URL-адрес и по умолчанию текущего месяца года добавляется в конце идентификатора набора отчетов после косой черты). Определения отчетов хранятся в формате JSON и после извлечения из службы репозитория вводятся в службу данных. В службе данных на основе введенных данных формируются запросы с многомерными выражениями (MDX), которые затем выполняются применительно к кубу для извлечения данных по каждому отчету. 

### <a name="building-customized-reports"></a>Составление нестандартных отчетов

В CQD предусмотрены широкие возможности настройки отчетов, однако в некоторых ситуациях пользователям необходимы сводные данные по нескольким отчетам, созданным в CQD. Например, может потребоваться отчет, где в табличной форме показана доля вызовов низкого качества для всех возможных вариантов вызовов по проводной связи (пример результата такого отчета показан на рисунке):

![Таблица CQD](../../media/ef19d535-5da6-44a9-91f6-1ed3f30b96f1.png)

Если пользователь работает на портале, предусмотренном в CQD, для извлечения и записи доли вызовов низкого качества из разных отчетов он должен перемещаться между отчетами; при сборе большого количества точек данных этот процесс может быть трудоемким. С помощью интерфейсов API для данных пользователи могут запрограммировать эту операцию; в этом случае данные извлекаются из службы данных (например, посредством вызовов AJAX). 

 **Пример 1. Образец простого отчета**

Сначала рассмотрим простой пример. Предположим, что требуется отобразить на странице HTML количество потоков звуковых данных высокого и низкого качества за февраль 2015 года, как показано на рисунке:

![Пример отчета CQD](../../media/f0e4e61f-1fa5-4d69-b192-f19e9612bf1c.png)

Для этого необходимо отправить в службу данных вызов с надлежащими параметрами и вывести результаты запроса в таблице HTML. Ниже приведен образец кода JavaScript.

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

Этот пример можно разбить на три этапа.

1. Построение запросов (в примере, это значение задается в переменной «запрос»). Запрос определяется как объект JSON, включающий в себя следующие данные.

   а. Измерения (не обязательно). Каждое измерение обозначается параметром DataModelName.

   б. Фильтры (не обязательно). Для каждого фильтра задаются следующие составляющие:

   - DataModelName (измерение, для которого будет задан фильтр);

   - значение (для сравнения с применением операнда);

   - Операнд (тип сравнения, 0 означает «Равно»).

     в. Хотя бы один показатель.

2. Отправка запроса в службу данных посредством вызова AJAX. Необходимо указать следующие параметры запроса.

   а. url (в качестве URL-адреса следует указать http://[имя_сервера]/QoEDataService/RunQuery).

   б. данные (это строковое представление объекта JSON, определенный в переменной «запрос»). Служба данных возвращает результаты запроса в виде параметра функции обратного вызова для успешного выполнения.

   в. Введите (для QoEDataService, RunQuery принимает только «ПУБЛИКАЦИЯ» запросы).

   г. async (признак, указывающий, должен ли вызов AJAX быть синхронным или асинхронным).

   e. contentType (должен быть «application/json»).

   f. success (функция обратного вызова в случае успешного завершения вызова AJAX).

   g. error (функция обработки ошибок в случае сбоя вызова AJAX).

3. Внедрение данных в элементы div в коде HTML (в данном примере кода для этого после успешного выполнения запроса AJAX осуществляется анонимный вызов функции).

При внедрении кода JavaScript в страницу HTML на этой странице отображается отчет, подобный показанному на рисунке. Ниже код HTML показан полностью:

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

Такой отчет по-прежнему очень прост. Пользователь может настроить его, добавляя дополнительные показатели, измерения или фильтры. Например, если требуется отобразить долю вызовов низкого качества в AppSharing, необходимо добавить новый показатель, связанный с AppSharing. Для отображения всех вызовов TCP в сравнении с вызовами UDP следует добавить новое измерение, относящееся к типу транспортного протокола. Для отображения количества вызовов низкого качества в конкретном здании следует добавить новый фильтр, позволяющий выбрать входящие и исходящие вызовы в этом здании.

 **Пример 2. Образец определения отчета**

Некоторые пользователи могут не знать, как составляется полный список показателей/измерений/фильтров и соответствующих значений при формировании запроса. В этом случае можно перейти на портал, сформировать отчет в редакторе отчетов, найти строку JSON в определении отчета и скопировать ее в пользовательский отчет. 

В этом примере будет создана веб-страница, подобная показанной на рисунке; если пользователь введет на этой веб-странице идентификатор любого существующего набора отчетов (или отчета), на ней отобразится определение этого набора отчетов или отчета. После этого пользователь может включить строку JSON для каждого отчета в код, аналогичный рассмотренному в примере 1, и составить любой требуемый отчет. 

![Пример CQD](../../media/01c45c23-c4d2-47b8-819f-0888cf71260f.png)

При создании средства просмотра определений отчетов потребуется отправить вызовы в службу репозитория для извлечения определения каждого требуемого набора отчетов, представленного в виде строки JSON. Интерфейс API репозитория возвращает определение набора отчетов по заданному определению набора отчетов. 

В качестве примера рассмотрим приведенный ниже код. Он содержит блок, который служит простым образцом отправки в службу репозитория запроса на получение содержимого элемента из репозитория по идентификатору этого элемента. Следующий фрагмент кода (метод processReportSetData) обеспечивает отправку вызовов AJAX для получения определения каждого отчета из данного набора. Более подробные сведения в API репозитория и в частности, GetItems, можно найти в списке [Получение элементов](get-items.md). 

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

Результатом приведенного выше кода является веб-страница, подобная показанной на рисунке (без определения отчета при первом посещении). Получите идентификатор набора отчетов из портала CQD (после / #/ вход в портал CQD URL-адрес (например: на первом рисунке отчета идентификатора набора является 3024) и поместите этот идентификатор набора отчета в раздел входных данных веб-страницы. Нажмите кнопку «Загрузить» и просмотреть полное определение (показатели, измерения списки фильтров) набор отчетов.

Таким образом, чтобы быстро получить полное определение набора/report отчет. Для этого требуется выполнить следующие действия:

1. Перейдите к порталу и использовать редактор запросов для настройки report (щелкните «Изменить» над отчет для редактирования, добавление, удаление показатели, измерения/фильтры, а затем сохранить отчет).

2. Получите идентификатор набора отчетов из URL-адреса (целое число после / #/ входа в URL-адрес).

3. Вызовите веб-страницу определения отчета, созданную в примере 2, введите идентификатора набора отчетов и извлеките полное определение этого набора (которое будет применяться в вызовах интерфейса API для данных).

   **Пример 3. Образец системы показателей**

Перейдем к более сложной задаче. Требуется создать веб-страницу, подобную показанной на рисунке. Поскольку при этом увеличивается объем обрабатываемых данных, следует обновить код из примера 1 (с помощью сформированной в примере 2 веб-страницы, позволяющей извлекать полное определение любого отчета).

В данном случае требуется обновить список показателей и измерений. Для добавления/изменения показателя и/или размерности следует выполнить инструкции из примера 2 и извлечь полное определение отчета, в том числе полные списки показателей и измерений. Включите полное определение отчета в образец кода. 

Ниже приведена пошаговая процедура получения показанной на рисунке страницы системы показателей на основе кода из примера 1.

1. Обновление измерений в переменной «запрос» из `[Measures].[Audio Good Streams JPDR Count]` и `[Measures].[Audio Poor Streams JPDR Count]` для `[Measures].[AudioPoorJPDRPercentage]`. 

2. Обновите фильтры. Данные JSON для фильтров в примере 1 имеет один фильтр, которая задается в измерении `[StartDate].[Month]`. Поскольку фильтры являются массивом JSON, к списку фильтров можно добавлять дополнительные измерения. Например чтобы получить клиентов сервера внутри проводной вызовы для «currentMonth», у нас есть следующие фильтры:

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

   Здесь измерение `[Scenarios].[ScenarioPair]` задано значение равно `[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]`. `[Scenario.][ScenarioPair]` — Это специальные измерение, созданное для упрощения создания отчета. Оно имеет шесть значений, соответствующих параметрам `[FirstIsServer], [SecondIsServer], [FirstInside], [SecondIsServer], [FirstConnectionType], [SecondConnectionType]`. Таким образом, для определения не требуется сочетание шести фильтров: достаточно одного фильтра. В нашем примере значение `[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]` преобразование в сценарий где: сначала — это сервер, во-вторых не является сервером, сначала находится внутри, во-вторых находится внутри, проводное первый тип подключения, а второй тип подключения — проводной, которая является точное определение " Сервер Client-Inside проводной сети».

3. Создайте по одному фильтру для каждого сценария. В системе показателей на рисунке каждая строка представляет отдельный сценарий, для которого задается отдельный фильтр (измерения и показатели являются общими для всех сценариев). 

4. Выполните синтаксический разбор результатов вызовов AJAX и поместите их в правильное положение в таблице. Поскольку эта операция выполняется преимущественно средствами HTML и JavaScript, ее детали здесь опущены. Соответствующий код приведен в приложении A.

    > [!NOTE]
    >  При включении общего доступа к междоменных ресурсов (CORS) пользователи могут возникнуть ошибки, как «отсутствует «Доступ элемент управления-разрешить-происхождения» заголовок присутствует запрошенный ресурс. Происхождение «null» таким образом не разрешен доступ». Чтобы решить эту проблему, поместите HTML-файл в папке, где установлены портала (по умолчанию, оно должно быть `%SystemDrive%\Program Files\Skype for Business 2015 CQD\CQD)`. Получить доступ к HTML-код через любой браузер с URL-адрес `http://<servername>/cqd/<html_file_name>`. (— Это URL-адрес по умолчанию для локальной панели мониторинга CQD `http://<servername>/cqd.`) 

### <a name="appendix-a"></a>Приложение A

Код HTML для примера 3 (образец системы показателей):

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