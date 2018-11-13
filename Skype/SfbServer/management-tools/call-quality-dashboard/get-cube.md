---
title: Получение куба
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c8eeb387-dc1e-44e0-bbf9-a566f8bda551
description: 'Сводка: Сведения о операцию получения куб, который является частью API данных для панели мониторинга качества звонков. Панель мониторинга качества звонков — это средство для Скайп для Business Server 2015.'
ms.openlocfilehash: 9c31650a5dc5471e0d5ad2dcdbf2214b16d91c56
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/13/2018
ms.locfileid: "26294438"
---
# <a name="get-cube"></a><span data-ttu-id="61070-104">Получение куба</span><span class="sxs-lookup"><span data-stu-id="61070-104">Get Cube</span></span>
 
<span data-ttu-id="61070-105">**Сводка:** Узнайте о операцию получения куб, который является частью API данных для панели мониторинга качества звонков.</span><span class="sxs-lookup"><span data-stu-id="61070-105">**Summary:** Learn about the Get Cube operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="61070-106">Панель мониторинга качества звонков — это средство для Скайп для Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="61070-106">Call Quality Dashboard is a tool for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="61070-107">Операция получения куба является частью API данных для панели мониторинга качества звонков.</span><span class="sxs-lookup"><span data-stu-id="61070-107">The Get Cube operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="get-cube"></a><span data-ttu-id="61070-108">Получение куба</span><span class="sxs-lookup"><span data-stu-id="61070-108">Get Cube</span></span>

<span data-ttu-id="61070-109">Операция куба Get возвращает список доступных измерений и измерения.</span><span class="sxs-lookup"><span data-stu-id="61070-109">Get Cube operation returns the list of available dimensions and measurements.</span></span>
  

|<span data-ttu-id="61070-110">**Метод**</span><span class="sxs-lookup"><span data-stu-id="61070-110">**Method**</span></span>|<span data-ttu-id="61070-111">**URI запроса**</span><span class="sxs-lookup"><span data-stu-id="61070-111">**Request URI**</span></span>|<span data-ttu-id="61070-112">**Версия HTTP**</span><span class="sxs-lookup"><span data-stu-id="61070-112">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="61070-113">Получить</span><span class="sxs-lookup"><span data-stu-id="61070-113">GET</span></span>  <br/> |<span data-ttu-id="61070-114">https://\<портала\>/QoEDataService/CubeStructure</span><span class="sxs-lookup"><span data-stu-id="61070-114">https://\<portal\>/QoEDataService/CubeStructure</span></span>  <br/> |<span data-ttu-id="61070-115">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="61070-115">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="61070-116">**Параметры URI** — нет.</span><span class="sxs-lookup"><span data-stu-id="61070-116">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="61070-117">**Заголовки запроса** — без дополнительных заголовков.</span><span class="sxs-lookup"><span data-stu-id="61070-117">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="61070-118">**Текст запроса** — нет.</span><span class="sxs-lookup"><span data-stu-id="61070-118">**Request Body** - None.</span></span>
  
 <span data-ttu-id="61070-119">**Ответа** - ответ включает код состояния HTTP и набор заголовков ответов.</span><span class="sxs-lookup"><span data-stu-id="61070-119">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="61070-120">**Код состояния** - успешные операции возвращает код состояния 200 (ОК).</span><span class="sxs-lookup"><span data-stu-id="61070-120">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="61070-121">**Заголовки ответа** — без дополнительных заголовков.</span><span class="sxs-lookup"><span data-stu-id="61070-121">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="61070-122">**Тело ответа** - ниже приведен пример полезные данные ответа в формате JSON в.</span><span class="sxs-lookup"><span data-stu-id="61070-122">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="61070-123">В этом примере показано только первые два элемента каждой группы элементов куба.</span><span class="sxs-lookup"><span data-stu-id="61070-123">This sample is only showing first two elements of each groups of Cube elements.</span></span> 
  
```
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

 <span data-ttu-id="61070-124">*Ключевые показатели эффективности* — зарезервировано.</span><span class="sxs-lookup"><span data-stu-id="61070-124">*KPIs*  - Reserved.</span></span> <span data-ttu-id="61070-125">Ключевые показатели эффективности части полезных данных запроса позволяет выполнить запрос операции для возврата значения для ключевых индикаторов производительности, определенных в кубе.</span><span class="sxs-lookup"><span data-stu-id="61070-125">The KPIs section of a request payload allows Run Query operation to return values for the KPIs defined in the cube.</span></span> <span data-ttu-id="61070-126">Не ключевые показатели эффективности еще не существует в кубе качества взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="61070-126">No KPIs exist in the QoE Cube yet.</span></span>
  
 <span data-ttu-id="61070-127">*Измерения* - список измерений, которые могут быть использованы в разделах фильтры и размеры полезных данных запроса для операции выполнить запрос.</span><span class="sxs-lookup"><span data-stu-id="61070-127">*Dimensions*  - The list of dimensions that may be used in Filters and Dimensions sections of a request payload for Run Query operation.</span></span> <span data-ttu-id="61070-128">Чтобы использовать измерения в выражение фильтра, необходимо указать элемент измерения, который можно получить с помощью операции получения элементов измерения.</span><span class="sxs-lookup"><span data-stu-id="61070-128">To use a dimension in a filter expression, you need to specify a dimension member, which can be obtained using Get Dimension Members operation.</span></span>
  
 <span data-ttu-id="61070-129">*Измерения* — список измерений, которые могут быть использованы в разделе измерения полезных данных запроса для операции выполнить запрос.</span><span class="sxs-lookup"><span data-stu-id="61070-129">*Measurements*  - The list of measurements that may be used in Measurements section of a request payload for Run Query operation.</span></span>
  

