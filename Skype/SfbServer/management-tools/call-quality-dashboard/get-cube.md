---
title: Получение куба
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c8eeb387-dc1e-44e0-bbf9-a566f8bda551
description: 'Сводка: сведения о операции "получить куб", которая входит в API данных для панели мониторинга качества звонков. Панель мониторинга качества звонков — это средство для Skype для бизнеса Server.'
ms.openlocfilehash: 1d8327439d79e7d02182dc7195bc0052bf6c923c
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888828"
---
# <a name="get-cube"></a><span data-ttu-id="13055-104">Получение куба</span><span class="sxs-lookup"><span data-stu-id="13055-104">Get Cube</span></span>
 
<span data-ttu-id="13055-105">**Сводка:** Сведения о выполнении операции "получить куб", которая входит в API данных для панели мониторинга качества звонков.</span><span class="sxs-lookup"><span data-stu-id="13055-105">**Summary:** Learn about the Get Cube operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="13055-106">Панель мониторинга качества звонков — это средство для Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="13055-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="13055-107">Операция "получить куб" входит в API данных для панели мониторинга качества звонков.</span><span class="sxs-lookup"><span data-stu-id="13055-107">The Get Cube operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="get-cube"></a><span data-ttu-id="13055-108">Получение куба</span><span class="sxs-lookup"><span data-stu-id="13055-108">Get Cube</span></span>

<span data-ttu-id="13055-109">Операция "получить куб" возвращает список доступных размеров и измерений.</span><span class="sxs-lookup"><span data-stu-id="13055-109">Get Cube operation returns the list of available dimensions and measurements.</span></span>
  

|<span data-ttu-id="13055-110">**Способов**</span><span class="sxs-lookup"><span data-stu-id="13055-110">**Method**</span></span>|<span data-ttu-id="13055-111">**URI запроса**</span><span class="sxs-lookup"><span data-stu-id="13055-111">**Request URI**</span></span>|<span data-ttu-id="13055-112">**Версия HTTP**</span><span class="sxs-lookup"><span data-stu-id="13055-112">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="13055-113">Получить</span><span class="sxs-lookup"><span data-stu-id="13055-113">GET</span></span>  <br/> |<span data-ttu-id="13055-114">/Коедатасервице/кубеструктуре\<портала\>HTTPS://</span><span class="sxs-lookup"><span data-stu-id="13055-114">https://\<portal\>/QoEDataService/CubeStructure</span></span>  <br/> |<span data-ttu-id="13055-115">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="13055-115">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="13055-116">**Параметры универсального кода ресурса** (None).</span><span class="sxs-lookup"><span data-stu-id="13055-116">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="13055-117">**Заголовки запроса** — без дополнительных заголовков.</span><span class="sxs-lookup"><span data-stu-id="13055-117">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="13055-118">**Запросить текст** -None.</span><span class="sxs-lookup"><span data-stu-id="13055-118">**Request Body** - None.</span></span>
  
 <span data-ttu-id="13055-119">**Response (ответ** ) — ответ включает код состояния HTTP и набор заголовков ответа.</span><span class="sxs-lookup"><span data-stu-id="13055-119">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="13055-120">**Код состояния** — успешная операция возвращает код состояния 200 (ОК).</span><span class="sxs-lookup"><span data-stu-id="13055-120">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="13055-121">**Заголовки ответа** — без дополнительных заголовков.</span><span class="sxs-lookup"><span data-stu-id="13055-121">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="13055-122">**Тело ответа** — ниже показан пример полезных данных ответа в JSON.</span><span class="sxs-lookup"><span data-stu-id="13055-122">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="13055-123">В этом примере показаны первые два элемента каждой группы элементов куба.</span><span class="sxs-lookup"><span data-stu-id="13055-123">This sample is only showing first two elements of each groups of Cube elements.</span></span> 
  
```json
{
"Kpis": [{
"FriendlyName": "Poor Trend Month",
"DataModelName": "[KPIValue].Poor Trend Month",
"Description": null
},
{
"FriendlyName": "Poor Rate Trend Month",
"DataModelName": "[KPIValue].Poor Rate Trend Month",
"Description": null
}],
"Dimensions": [{
"Category": "Access Location Pair",
"Attributes": [{
"FriendlyName": "Location Pair",
"DataModelName": "[Access Location Pair].[Location Pair]",
"Description": "Description of Location Pair"
}]
},
{
"Category": "Audio Bandwidth Est",
"Attributes": [{
"FriendlyName": "Metric",
"DataModelName": "[Audio Bandwidth Est].[Metric]",
"Description": "Description of Metric"
}]
}],
"Measurements": [{
"FriendlyName": "Audio Streams Count",
"DataModelName": "[Measures].[Audio Streams Count]",
"Description": "Description of Audio Streams Count"
},
{
"FriendlyName": "Audio Good Streams JPDR Count",
"DataModelName": "[Measures].[Audio Good Streams JPDR Count]",
"Description": "Description of Audio Good Streams JPDR Count"
}]
}
```

 <span data-ttu-id="13055-124">*Ключевые показатели эффективности* — зарезервированы.</span><span class="sxs-lookup"><span data-stu-id="13055-124">*KPIs*  - Reserved.</span></span> <span data-ttu-id="13055-125">Раздел КИП в полезных данных запроса допускает операцию выполнения запроса, возвращающую значения для ключевых показателей эффективности, определенных в Кубе.</span><span class="sxs-lookup"><span data-stu-id="13055-125">The KPIs section of a request payload allows Run Query operation to return values for the KPIs defined in the cube.</span></span> <span data-ttu-id="13055-126">В Кубе QoE пока нет ключевых индикаторов производительности.</span><span class="sxs-lookup"><span data-stu-id="13055-126">No KPIs exist in the QoE Cube yet.</span></span>
  
 <span data-ttu-id="13055-127">*Dimensions* — список измерений, которые можно использовать в разделах "фильтры" и "измерения" полезных данных запроса для выполнения операции запроса.</span><span class="sxs-lookup"><span data-stu-id="13055-127">*Dimensions*  - The list of dimensions that may be used in Filters and Dimensions sections of a request payload for Run Query operation.</span></span> <span data-ttu-id="13055-128">Чтобы использовать измерение в выражении фильтра, необходимо указать элемент измерения, который можно получить с помощью операции "получить элементы измерения".</span><span class="sxs-lookup"><span data-stu-id="13055-128">To use a dimension in a filter expression, you need to specify a dimension member, which can be obtained using Get Dimension Members operation.</span></span>
  
 <span data-ttu-id="13055-129">*Измерения* — список измерений, которые можно использовать в разделе "измерения" полезных данных запроса для выполнения операции запроса.</span><span class="sxs-lookup"><span data-stu-id="13055-129">*Measurements*  - The list of measurements that may be used in Measurements section of a request payload for Run Query operation.</span></span>
  

