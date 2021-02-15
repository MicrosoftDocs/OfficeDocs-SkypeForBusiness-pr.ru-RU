---
title: Получение куба
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
ms.assetid: c8eeb387-dc1e-44e0-bbf9-a566f8bda551
description: Сводка. Сведения об операции "Получить куб", которая входит в API данных для панели мониторинга качества вызовов. Панель мониторинга качества звонков — это инструмент для Skype для бизнеса Server.
ms.openlocfilehash: a3527f21bc1751c23bba088ae06c3e6702cb8c8e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832629"
---
# <a name="get-cube"></a><span data-ttu-id="468a5-104">Получение куба</span><span class="sxs-lookup"><span data-stu-id="468a5-104">Get Cube</span></span>
 
<span data-ttu-id="468a5-105">**Сводка:** Сведения об операции "Получить куб", которая является частью API данных для панели мониторинга качества вызовов.</span><span class="sxs-lookup"><span data-stu-id="468a5-105">**Summary:** Learn about the Get Cube operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="468a5-106">Панель мониторинга качества звонков — это инструмент для Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="468a5-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="468a5-107">Операция "Получить куб" является частью API данных для панели мониторинга качества вызовов.</span><span class="sxs-lookup"><span data-stu-id="468a5-107">The Get Cube operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="get-cube"></a><span data-ttu-id="468a5-108">Получение куба</span><span class="sxs-lookup"><span data-stu-id="468a5-108">Get Cube</span></span>

<span data-ttu-id="468a5-109">Операция "Получить куб" возвращает список доступных измерений и измерений.</span><span class="sxs-lookup"><span data-stu-id="468a5-109">Get Cube operation returns the list of available dimensions and measurements.</span></span>
  

|<span data-ttu-id="468a5-110">**Способ**</span><span class="sxs-lookup"><span data-stu-id="468a5-110">**Method**</span></span>|<span data-ttu-id="468a5-111">**URI запроса**</span><span class="sxs-lookup"><span data-stu-id="468a5-111">**Request URI**</span></span>|<span data-ttu-id="468a5-112">**Версия HTTP**</span><span class="sxs-lookup"><span data-stu-id="468a5-112">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="468a5-113">GET</span><span class="sxs-lookup"><span data-stu-id="468a5-113">GET</span></span>  <br/> |<span data-ttu-id="468a5-114">https:// \<portal\> /QoEDataService/CubeStructure</span><span class="sxs-lookup"><span data-stu-id="468a5-114">https://\<portal\>/QoEDataService/CubeStructure</span></span>  <br/> |<span data-ttu-id="468a5-115">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="468a5-115">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="468a5-116">**Параметры URI** — нет.</span><span class="sxs-lookup"><span data-stu-id="468a5-116">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="468a5-117">**Request Headers** - No additional headers.</span><span class="sxs-lookup"><span data-stu-id="468a5-117">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="468a5-118">**Тело запроса** — нет.</span><span class="sxs-lookup"><span data-stu-id="468a5-118">**Request Body** - None.</span></span>
  
 <span data-ttu-id="468a5-119">**Ответ.** Ответ включает код состояния HTTP и набор загодеров отклика.</span><span class="sxs-lookup"><span data-stu-id="468a5-119">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="468a5-120">**Код состояния** : успешная операция возвращает код состояния 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="468a5-120">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="468a5-121">**Response Headers** - No additional headers.</span><span class="sxs-lookup"><span data-stu-id="468a5-121">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="468a5-122">**Тело ответа.** Ниже приведен пример полезной нагрузки ответа в JSON.</span><span class="sxs-lookup"><span data-stu-id="468a5-122">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="468a5-123">В этом примере показаны только первые два элемента каждой группы элементов Куба.</span><span class="sxs-lookup"><span data-stu-id="468a5-123">This sample is only showing first two elements of each groups of Cube elements.</span></span> 
  
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

 <span data-ttu-id="468a5-124">*KPIs*  — зарезервировано.</span><span class="sxs-lookup"><span data-stu-id="468a5-124">*KPIs*  - Reserved.</span></span> <span data-ttu-id="468a5-125">Раздел ХП полезной нагрузки запроса позволяет операции "Выполнить запрос" возвращать значения для ХП, определенных в кубе.</span><span class="sxs-lookup"><span data-stu-id="468a5-125">The KPIs section of a request payload allows Run Query operation to return values for the KPIs defined in the cube.</span></span> <span data-ttu-id="468a5-126">В кубе QoE еще нет ХП.</span><span class="sxs-lookup"><span data-stu-id="468a5-126">No KPIs exist in the QoE Cube yet.</span></span>
  
 <span data-ttu-id="468a5-127">*Измерения —*  список измерений, которые могут использоваться в разделах "Фильтры и измерения" полезной нагрузки запроса для операции "Выполнить запрос".</span><span class="sxs-lookup"><span data-stu-id="468a5-127">*Dimensions*  - The list of dimensions that may be used in Filters and Dimensions sections of a request payload for Run Query operation.</span></span> <span data-ttu-id="468a5-128">Чтобы использовать измерение в выражении фильтра, необходимо указать член измерения, который можно получить с помощью операции Get Dimension Members.</span><span class="sxs-lookup"><span data-stu-id="468a5-128">To use a dimension in a filter expression, you need to specify a dimension member, which can be obtained using Get Dimension Members operation.</span></span>
  
 <span data-ttu-id="468a5-129">*Измерения —*  список показателей, которые могут использоваться в разделе "Измерения" полезной нагрузки запроса для выполнения операции запроса.</span><span class="sxs-lookup"><span data-stu-id="468a5-129">*Measurements*  - The list of measurements that may be used in Measurements section of a request payload for Run Query operation.</span></span>
  

