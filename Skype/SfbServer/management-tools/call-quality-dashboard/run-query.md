---
title: Запуск запроса
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
ms.assetid: 45a77f7e-b137-462b-9146-3a0f43d8e0c7
description: Сводка. Сведения об операции "Выполнить запрос", которая является частью API данных для панели мониторинга качества вызовов. Панель мониторинга качества звонков — это инструмент для Skype для бизнеса Server.
ms.openlocfilehash: bff24ca5a4d651ba276b4b0d795afabce3c6d0dd
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803119"
---
# <a name="run-query"></a><span data-ttu-id="6d69b-104">Запуск запроса</span><span class="sxs-lookup"><span data-stu-id="6d69b-104">Run Query</span></span>

<span data-ttu-id="6d69b-105">**Сводка:** Сведения об операции "Выполнить запрос", которая является частью API данных для панели мониторинга качества вызовов.</span><span class="sxs-lookup"><span data-stu-id="6d69b-105">**Summary:** Learn about the Run Query operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="6d69b-106">Панель мониторинга качества звонков — это инструмент для Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="6d69b-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>

<span data-ttu-id="6d69b-107">Операция "Выполнить запрос" является частью API данных для панели мониторинга качества вызовов.</span><span class="sxs-lookup"><span data-stu-id="6d69b-107">The Run Query operation is part of the Data API for Call Quality Dashboard.</span></span>

## <a name="run-query"></a><span data-ttu-id="6d69b-108">Запуск запроса</span><span class="sxs-lookup"><span data-stu-id="6d69b-108">Run Query</span></span>

<span data-ttu-id="6d69b-109">Операция "Выполнить запрос" позволяет выполнять запрос к кубу на основе указанных измерений, измерений и фильтров, а также возвращать данные.</span><span class="sxs-lookup"><span data-stu-id="6d69b-109">Run Query operation provides the ability to run a query on the cube based on specified dimensions, measurements, and filters and return back the data.</span></span>


|<span data-ttu-id="6d69b-110">**Способ**</span><span class="sxs-lookup"><span data-stu-id="6d69b-110">**Method**</span></span>|<span data-ttu-id="6d69b-111">**URI запроса**</span><span class="sxs-lookup"><span data-stu-id="6d69b-111">**Request URI**</span></span>|<span data-ttu-id="6d69b-112">**Версия HTTP**</span><span class="sxs-lookup"><span data-stu-id="6d69b-112">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6d69b-113">POST</span><span class="sxs-lookup"><span data-stu-id="6d69b-113">POST</span></span>  <br/> |<span data-ttu-id="6d69b-114">https:// \<portal\> /QoEDataService/RunQuery</span><span class="sxs-lookup"><span data-stu-id="6d69b-114">https://\<portal\>/QoEDataService/RunQuery</span></span>  <br/> |<span data-ttu-id="6d69b-115">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="6d69b-115">HTTP/1.1</span></span>  <br/> |

 <span data-ttu-id="6d69b-116">**Параметры URI** — нет.</span><span class="sxs-lookup"><span data-stu-id="6d69b-116">**URI Parameters** - None.</span></span>

 <span data-ttu-id="6d69b-117">**Request Headers** - No additional headers.</span><span class="sxs-lookup"><span data-stu-id="6d69b-117">**Request Headers** - No additional headers.</span></span>

 <span data-ttu-id="6d69b-118">**Тело запроса—** вот пример полезной нагрузки запроса в JSON.</span><span class="sxs-lookup"><span data-stu-id="6d69b-118">**Request Body** - Here is a sample request payload in JSON.</span></span> <span data-ttu-id="6d69b-119">Он содержит измерения, фильтры и измерения, необходимые для запроса.</span><span class="sxs-lookup"><span data-stu-id="6d69b-119">It contains dimensions, filters, and measurement required for a query.</span></span>

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

 <span data-ttu-id="6d69b-120">*Фильтры*  — список выражений фильтра, которые необходимо применить таким образом, чтобы полученный набор данных отображал только подмножество интересующих вас данных.</span><span class="sxs-lookup"><span data-stu-id="6d69b-120">*Filters*  - A list of filter expressions to be applied such that the resulting data set will reflect only the subset of the data that are of interest.</span></span>

 <span data-ttu-id="6d69b-121">*Измерения —*  список измерений, которые будут использоваться для агрегации данных.</span><span class="sxs-lookup"><span data-stu-id="6d69b-121">*Dimensions*  - A list of dimensions that will be used for aggregating the data.</span></span> <span data-ttu-id="6d69b-122">Требуется по крайней мере одно измерение, но для получения дополнительного уровня под агрегации может быть задано несколько измерений.</span><span class="sxs-lookup"><span data-stu-id="6d69b-122">At least one dimension is required but multiple dimensions may be specified to obtain additional level of sub-aggregations.</span></span>

 <span data-ttu-id="6d69b-123">*Измерения —*  список измерений, также известных как факты, которые являются нужными метриками, которые необходимо агрегировать на основе указанных измерений.</span><span class="sxs-lookup"><span data-stu-id="6d69b-123">*Measurements*  - A list of measurements, also known as facts, that are the desired metrics to be aggregated based on the dimensions you specified.</span></span>

 <span data-ttu-id="6d69b-124">*Trend*  — дополнительные инструкции по контролю для настройки данных результатов.</span><span class="sxs-lookup"><span data-stu-id="6d69b-124">*Trend*  - Additional control instructions to customize the result data.</span></span>

 <span data-ttu-id="6d69b-125">**Ответ.** Ответ включает код состояния HTTP и набор загодеров отклика.</span><span class="sxs-lookup"><span data-stu-id="6d69b-125">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>

 <span data-ttu-id="6d69b-126">**Код состояния** — успешная операция возвращает код состояния 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="6d69b-126">**Status Code** - A successful operation returns status code 200 (OK).</span></span>

 <span data-ttu-id="6d69b-127">**Response Headers** - No additional headers.</span><span class="sxs-lookup"><span data-stu-id="6d69b-127">**Response Headers** - No additional headers.</span></span>

 <span data-ttu-id="6d69b-128">**Тело ответа.** Ниже приведен пример полезной нагрузки ответа в JSON.</span><span class="sxs-lookup"><span data-stu-id="6d69b-128">**Response Body** - Below is a sample response payload in JSON.</span></span> <span data-ttu-id="6d69b-129">Она содержит таблицу данных, которая содержит данные, а также метаданные, в которой показано время выполнения запроса и указывает, являются ли данные из кэша.</span><span class="sxs-lookup"><span data-stu-id="6d69b-129">It contains a data table which contains the data, also it will contain a meta data, which shows query execution time and whether or not the data is from the cache.</span></span>

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

 <span data-ttu-id="6d69b-130">*Время выполнения*  — общее время, необходимое серверу для возврата данных.</span><span class="sxs-lookup"><span data-stu-id="6d69b-130">*Execution Time*  - The total time it took for the server to return the data.</span></span> <span data-ttu-id="6d69b-131">Это может включать или не включать кэш.</span><span class="sxs-lookup"><span data-stu-id="6d69b-131">This may or may not involve cache.</span></span>

 <span data-ttu-id="6d69b-132">*Результат данных*  — результат запроса.</span><span class="sxs-lookup"><span data-stu-id="6d69b-132">*Data Result*  - The result of the query.</span></span> <span data-ttu-id="6d69b-133">Это двумерный массив, содержащий все перенастройки элементов измерений и каждый элемент, содержащий имена членов измерений, а также агрегированные значения указанных измерений.</span><span class="sxs-lookup"><span data-stu-id="6d69b-133">It is a two-dimensional array containing all permutations of the dimensions' members, and each element containing the dimensions' member names as well as the aggregated values of the specified Measurements.</span></span>

 <span data-ttu-id="6d69b-134">*Результат : из кэша*  — для диагностики.</span><span class="sxs-lookup"><span data-stu-id="6d69b-134">*Result is From Cache*  - For diagnostics.</span></span> <span data-ttu-id="6d69b-135">Указывает, поступил ли результат из кэша или куба QoE.</span><span class="sxs-lookup"><span data-stu-id="6d69b-135">Indicates whether the result came from the cache or from the QoE Cube.</span></span>
