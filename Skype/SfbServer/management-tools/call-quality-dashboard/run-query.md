---
title: Выполнение запроса
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 45a77f7e-b137-462b-9146-3a0f43d8e0c7
description: 'Сводка: сведения о выполнении операции запроса, которая входит в API данных для панели мониторинга качества звонков. Панель мониторинга качества звонков — это средство для Skype для бизнеса Server.'
ms.openlocfilehash: 8d31ea4c597ea3353fdd5da3e863938aababe819
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991404"
---
# <a name="run-query"></a><span data-ttu-id="0ff24-104">Выполнение запроса</span><span class="sxs-lookup"><span data-stu-id="0ff24-104">Run Query</span></span>

<span data-ttu-id="0ff24-105">**Сводка:** Сведения о выполнении операции запроса, которая входит в API данных для панели мониторинга качества звонков.</span><span class="sxs-lookup"><span data-stu-id="0ff24-105">**Summary:** Learn about the Run Query operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="0ff24-106">Панель мониторинга качества звонков — это средство для Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="0ff24-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>

<span data-ttu-id="0ff24-107">Операция выполнения запроса входит в API данных для панели мониторинга качества звонков.</span><span class="sxs-lookup"><span data-stu-id="0ff24-107">The Run Query operation is part of the Data API for Call Quality Dashboard.</span></span>

## <a name="run-query"></a><span data-ttu-id="0ff24-108">Выполнение запроса</span><span class="sxs-lookup"><span data-stu-id="0ff24-108">Run Query</span></span>

<span data-ttu-id="0ff24-109">Операция выполнения запроса предоставляет возможность выполнения запроса для куба на основе указанных размеров, измерений и фильтров, а также возврата данных.</span><span class="sxs-lookup"><span data-stu-id="0ff24-109">Run Query operation provides the ability to run a query on the cube based on specified dimensions, measurements, and filters and return back the data.</span></span>


|<span data-ttu-id="0ff24-110">**Способов**</span><span class="sxs-lookup"><span data-stu-id="0ff24-110">**Method**</span></span>|<span data-ttu-id="0ff24-111">**URI запроса**</span><span class="sxs-lookup"><span data-stu-id="0ff24-111">**Request URI**</span></span>|<span data-ttu-id="0ff24-112">**Версия HTTP**</span><span class="sxs-lookup"><span data-stu-id="0ff24-112">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0ff24-113">Поместить</span><span class="sxs-lookup"><span data-stu-id="0ff24-113">POST</span></span>  <br/> |<span data-ttu-id="0ff24-114">/Коедатасервице/рункуери\<портала\>HTTPS://</span><span class="sxs-lookup"><span data-stu-id="0ff24-114">https://\<portal\>/QoEDataService/RunQuery</span></span>  <br/> |<span data-ttu-id="0ff24-115">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="0ff24-115">HTTP/1.1</span></span>  <br/> |

 <span data-ttu-id="0ff24-116">**Параметры универсального кода ресурса** (None).</span><span class="sxs-lookup"><span data-stu-id="0ff24-116">**URI Parameters** - None.</span></span>

 <span data-ttu-id="0ff24-117">**Заголовки запроса** — без дополнительных заголовков.</span><span class="sxs-lookup"><span data-stu-id="0ff24-117">**Request Headers** - No additional headers.</span></span>

 <span data-ttu-id="0ff24-118">**Тело запроса** — образец полезных данных запроса в JSON.</span><span class="sxs-lookup"><span data-stu-id="0ff24-118">**Request Body** - Here is a sample request payload in JSON.</span></span> <span data-ttu-id="0ff24-119">Она включает измерения, фильтры и измерения, необходимые для запроса.</span><span class="sxs-lookup"><span data-stu-id="0ff24-119">It contains dimensions, filters, and measurement required for a query.</span></span>

```json
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

 <span data-ttu-id="0ff24-120">*Filters* — список применяемых фильтров, в результате которого результирующий набор данных будет показывать только подмножество данных, которые будут представлять собой.</span><span class="sxs-lookup"><span data-stu-id="0ff24-120">*Filters*  - A list of filter expressions to be applied such that the resulting data set will reflect only the subset of the data that are of interest.</span></span>

 <span data-ttu-id="0ff24-121">*Измерения* — список измерений, которые будут использоваться для статистической обработки данных.</span><span class="sxs-lookup"><span data-stu-id="0ff24-121">*Dimensions*  - A list of dimensions that will be used for aggregating the data.</span></span> <span data-ttu-id="0ff24-122">Требуется хотя бы одно измерение, но для получения дополнительных уровней вложенных агрегатов может быть указано несколько измерений.</span><span class="sxs-lookup"><span data-stu-id="0ff24-122">At least one dimension is required but multiple dimensions may be specified to obtain additional level of sub-aggregations.</span></span>

 <span data-ttu-id="0ff24-123">*Измерения* — список измерений, также называемых фактами, которые представляют собой необходимые метрики, которые должны быть агрегированы на основе указанных вами измерений.</span><span class="sxs-lookup"><span data-stu-id="0ff24-123">*Measurements*  - A list of measurements, also known as facts, that are the desired metrics to be aggregated based on the dimensions you specified.</span></span>

 <span data-ttu-id="0ff24-124">*Тенденция* — дополнительные инструкции по настройке результирующих данных.</span><span class="sxs-lookup"><span data-stu-id="0ff24-124">*Trend*  - Additional control instructions to customize the result data.</span></span>

 <span data-ttu-id="0ff24-125">**Response (ответ** ) — ответ включает код состояния HTTP и набор заголовков ответа.</span><span class="sxs-lookup"><span data-stu-id="0ff24-125">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>

 <span data-ttu-id="0ff24-126">**Код состояния** — успешная операция возвращает код состояния 200 (ОК).</span><span class="sxs-lookup"><span data-stu-id="0ff24-126">**Status Code** - A successful operation returns status code 200 (OK).</span></span>

 <span data-ttu-id="0ff24-127">**Заголовки ответа** — без дополнительных заголовков.</span><span class="sxs-lookup"><span data-stu-id="0ff24-127">**Response Headers** - No additional headers.</span></span>

 <span data-ttu-id="0ff24-128">**Тело ответа** — ниже показан пример полезных данных ответа в JSON.</span><span class="sxs-lookup"><span data-stu-id="0ff24-128">**Response Body** - Below is a sample response payload in JSON.</span></span> <span data-ttu-id="0ff24-129">Она содержит таблицу данных, содержащую данные, также содержит метаданные, которые показывают время выполнения запроса и сведения о том, находятся ли данные из кэша.</span><span class="sxs-lookup"><span data-stu-id="0ff24-129">It contains a data table which contains the data, also it will contain a meta data, which shows query execution time and whether or not the data is from the cache.</span></span>

```json
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

 <span data-ttu-id="0ff24-130">*Время выполнения* — общее время, затраченное сервером на возврат данных.</span><span class="sxs-lookup"><span data-stu-id="0ff24-130">*Execution Time*  - The total time it took for the server to return the data.</span></span> <span data-ttu-id="0ff24-131">Это может вызвать или не включать кэширование.</span><span class="sxs-lookup"><span data-stu-id="0ff24-131">This may or may not involve cache.</span></span>

 <span data-ttu-id="0ff24-132">*Результат данных* — результат запроса.</span><span class="sxs-lookup"><span data-stu-id="0ff24-132">*Data Result*  - The result of the query.</span></span> <span data-ttu-id="0ff24-133">Это двухмерный массив, который содержит все перестановки членов измерений и каждый элемент, содержащий имена членов измерения, а также агрегированные значения указанных измерений.</span><span class="sxs-lookup"><span data-stu-id="0ff24-133">It is a two-dimensional array containing all permutations of the dimensions' members, and each element containing the dimensions' member names as well as the aggregated values of the specified Measurements.</span></span>

 <span data-ttu-id="0ff24-134">*Результаты из кэша* — для диагностики.</span><span class="sxs-lookup"><span data-stu-id="0ff24-134">*Result is From Cache*  - For diagnostics.</span></span> <span data-ttu-id="0ff24-135">Указывает, получен ли результат из кэша или из куба QoE.</span><span class="sxs-lookup"><span data-stu-id="0ff24-135">Indicates whether the result came from the cache or from the QoE Cube.</span></span>
