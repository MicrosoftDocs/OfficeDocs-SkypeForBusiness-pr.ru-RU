---
title: Выполнение запроса
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 45a77f7e-b137-462b-9146-3a0f43d8e0c7
description: 'Сводка: Сведения о операцию выполнить запрос, который является частью API данных для панели мониторинга качества звонков. Панель мониторинга качества звонков — это средство для Скайп для Business Server.'
ms.openlocfilehash: ac9f042a8d5b8e016a398a0daf9595ffcb9d2fcb
ms.sourcegitcommit: b680505c5dad435d98fbd0b235e0e7c67b9d8c9c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2018
ms.locfileid: "26035703"
---
# <a name="run-query"></a><span data-ttu-id="112ab-104">Выполнение запроса</span><span class="sxs-lookup"><span data-stu-id="112ab-104">Run Query</span></span>

<span data-ttu-id="112ab-105">**Сводка:** Узнайте о операцию выполнить запрос, который является частью API данных для панели мониторинга качества звонков.</span><span class="sxs-lookup"><span data-stu-id="112ab-105">**Summary:** Learn about the Run Query operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="112ab-106">Панель мониторинга качества звонков — это средство для Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="112ab-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>

<span data-ttu-id="112ab-107">Операция выполнить запрос является частью API данных для панели мониторинга качества звонков.</span><span class="sxs-lookup"><span data-stu-id="112ab-107">The Run Query operation is part of the Data API for Call Quality Dashboard.</span></span>

## <a name="run-query"></a><span data-ttu-id="112ab-108">Выполнение запроса</span><span class="sxs-lookup"><span data-stu-id="112ab-108">Run Query</span></span>

<span data-ttu-id="112ab-109">Выполнить запрос, операция предоставляет возможность выполнения запроса в кубе, на основе указанного измерения, измерения и фильтры и возвращать данные обратно.</span><span class="sxs-lookup"><span data-stu-id="112ab-109">Run Query operation provides the ability to run a query on the cube based on specified dimensions, measurements, and filters and return back the data.</span></span>


|<span data-ttu-id="112ab-110">**Метод**</span><span class="sxs-lookup"><span data-stu-id="112ab-110">**Method**</span></span>|<span data-ttu-id="112ab-111">**URI запроса**</span><span class="sxs-lookup"><span data-stu-id="112ab-111">**Request URI**</span></span>|<span data-ttu-id="112ab-112">**Версия HTTP**</span><span class="sxs-lookup"><span data-stu-id="112ab-112">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="112ab-113">Поместить</span><span class="sxs-lookup"><span data-stu-id="112ab-113">POST</span></span>  <br/> |<span data-ttu-id="112ab-114">https://\<портала\>/QoEDataService/RunQuery</span><span class="sxs-lookup"><span data-stu-id="112ab-114">https://\<portal\>/QoEDataService/RunQuery</span></span>  <br/> |<span data-ttu-id="112ab-115">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="112ab-115">HTTP/1.1</span></span>  <br/> |

 <span data-ttu-id="112ab-116">**Параметры URI** — нет.</span><span class="sxs-lookup"><span data-stu-id="112ab-116">**URI Parameters** - None.</span></span>

 <span data-ttu-id="112ab-117">**Заголовки запроса** — без дополнительных заголовков.</span><span class="sxs-lookup"><span data-stu-id="112ab-117">**Request Headers** - No additional headers.</span></span>

 <span data-ttu-id="112ab-118">**Текст запроса** — здесь — это полезных данных запроса примера в JSON.</span><span class="sxs-lookup"><span data-stu-id="112ab-118">**Request Body** - Here is a sample request payload in JSON.</span></span> <span data-ttu-id="112ab-119">Он содержит измерений, фильтры и измерения, необходимые для запроса.</span><span class="sxs-lookup"><span data-stu-id="112ab-119">It contains dimensions, filters, and measurement required for a query.</span></span>

```
{
"Filters": [{
"DataModelName": "[StartDate].[Month]",
"Caption": "July 2013",
"Value": "[2015-03-01T00:00:00]",
"Operand": 0,
"UnionGroup": ""
}],
"Dimensions": [{
"DataModelName": "[StartDate].[Month]"
}],
"Measurements": [{
"DataModelName": "[Measures].[Audio Good Streams Count]"
},
{
"DataModelName": "[Measures].[Audio UnClassified Streams Count]"
},
{
"DataModelName": "[Measures].[Audio Poor Streams Count]"
},
{
"DataModelName": "[Measures].[AudioPoorPercentage]"
}],
"Trend": {
"EnableTrend": true,
"SpanCount": 7,
"TrendDate": "2015-3",
"Type": 0
}
}
```

 <span data-ttu-id="112ab-120">*Фильтры* - список выражений фильтра для применения таким образом, результирующий набор данных, будет содержать только подмножества данных, которые могут представлять интерес.</span><span class="sxs-lookup"><span data-stu-id="112ab-120">*Filters*  - A list of filter expressions to be applied such that the resulting data set will reflect only the subset of the data that are of interest.</span></span>

 <span data-ttu-id="112ab-121">*Измерения* - список измерений, которые будут использоваться для группирования данных.</span><span class="sxs-lookup"><span data-stu-id="112ab-121">*Dimensions*  - A list of dimensions that will be used for aggregating the data.</span></span> <span data-ttu-id="112ab-122">Требуется по крайней мере одно измерение, но несколько измерений может быть указано для получения дополнительных уровней вложенных статистические выражения.</span><span class="sxs-lookup"><span data-stu-id="112ab-122">At least one dimension is required but multiple dimensions may be specified to obtain additional level of sub-aggregations.</span></span>

 <span data-ttu-id="112ab-123">*Измерения* — список единиц измерения, также известной как фактов, что желаемую метрики суммировать на основе измерений, указанному.</span><span class="sxs-lookup"><span data-stu-id="112ab-123">*Measurements*  - A list of measurements, also known as facts, that are the desired metrics to be aggregated based on the dimensions you specified.</span></span>

 <span data-ttu-id="112ab-124">*ТЕНДЕНЦИЯ* - дополнительный элемент управления инструкции для настройки данных результатов.</span><span class="sxs-lookup"><span data-stu-id="112ab-124">*Trend*  - Additional control instructions to customize the result data.</span></span>

 <span data-ttu-id="112ab-125">**Ответа** - ответ включает код состояния HTTP и набор заголовков ответов.</span><span class="sxs-lookup"><span data-stu-id="112ab-125">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>

 <span data-ttu-id="112ab-126">**Код состояния** - успешные операции возвращает код состояния 200 (ОК).</span><span class="sxs-lookup"><span data-stu-id="112ab-126">**Status Code** - A successful operation returns status code 200 (OK).</span></span>

 <span data-ttu-id="112ab-127">**Заголовки ответа** — без дополнительных заголовков.</span><span class="sxs-lookup"><span data-stu-id="112ab-127">**Response Headers** - No additional headers.</span></span>

 <span data-ttu-id="112ab-128">**Тело ответа** - ниже приведен пример полезные данные ответа в формате JSON в.</span><span class="sxs-lookup"><span data-stu-id="112ab-128">**Response Body** - Below is a sample response payload in JSON.</span></span> <span data-ttu-id="112ab-129">Он содержит таблицу данных, который содержит данные, также будет содержать метаданные, который показывает время выполнения запроса и ли данные из кэша.</span><span class="sxs-lookup"><span data-stu-id="112ab-129">It contains a data table which contains the data, also it will contain a meta data, which shows query execution time and whether or not the data is from the cache.</span></span>

```
{
"ExecutionTime": "00:00:00.2102630",
"DataResult": [["September 2014",
        1792,
        34,
        78,
        4.171],
        ["October 2014",
        37017,
        1731,
        3305,
        8.197],
        ["November 2014",
        79184,
        3033,
        5556,
        6.557],
        ["December 2014",
        122253,
        4050,
        5444,
        4.263],
        ["January 2015",
        31246,
        1069,
        1342,
        4.118]],
"ResultIsFromCache": false,
"ErrorType": 0
}
```

 <span data-ttu-id="112ab-130">*Время выполнения* — общее время, которое потребовалось для возвращения данных с сервера.</span><span class="sxs-lookup"><span data-stu-id="112ab-130">*Execution Time*  - The total time it took for the server to return the data.</span></span> <span data-ttu-id="112ab-131">Это может и не может включать в себя кэша.</span><span class="sxs-lookup"><span data-stu-id="112ab-131">This may or may not involve cache.</span></span>

 <span data-ttu-id="112ab-132">*Данные результатов* - результатов запроса.</span><span class="sxs-lookup"><span data-stu-id="112ab-132">*Data Result*  - The result of the query.</span></span> <span data-ttu-id="112ab-133">Это двухмерный массив, содержащий все перестановок элементов измерений и каждый элемент, содержащий имена элементов измерений, а также статистические значения указанного измерения.</span><span class="sxs-lookup"><span data-stu-id="112ab-133">It is a two-dimensional array containing all permutations of the dimensions' members, and each element containing the dimensions' member names as well as the aggregated values of the specified Measurements.</span></span>

 <span data-ttu-id="112ab-134">*Результатом является из кэша* - для диагностики.</span><span class="sxs-lookup"><span data-stu-id="112ab-134">*Result is From Cache*  - For diagnostics.</span></span> <span data-ttu-id="112ab-135">Указывает, будет ли результат поступил из кэша или из куба качества взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="112ab-135">Indicates whether the result came from the cache or from the QoE Cube.</span></span>