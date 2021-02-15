---
title: Получение элементов измерений
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
ms.assetid: bd89bbf7-cb98-4cd8-bbfa-0484663d14db
description: Сводка. Сведения об операции get Dimension Members. Операция Get Dimension Members является частью API данных для панели мониторинга качества вызовов. Панель мониторинга качества звонков — это инструмент для Skype для бизнеса Server.
ms.openlocfilehash: ffec3b02a3c876a003adb679a28b0e8f2edb91c2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832639"
---
# <a name="get-dimension-members"></a><span data-ttu-id="728c8-105">Получение элементов измерений</span><span class="sxs-lookup"><span data-stu-id="728c8-105">Get Dimension Members</span></span>
 
<span data-ttu-id="728c8-106">**Сводка:** Узнайте об операции "Получить члены измерения".</span><span class="sxs-lookup"><span data-stu-id="728c8-106">**Summary:** Learn about the Get Dimension Members operation.</span></span> <span data-ttu-id="728c8-107">Операция Get Dimension Members является частью API данных для панели мониторинга качества вызовов.</span><span class="sxs-lookup"><span data-stu-id="728c8-107">The Get Dimension Members operation is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="728c8-108">Панель мониторинга качества звонков — это инструмент для Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="728c8-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="728c8-109">Операция Get Dimension Members является частью API данных для панели мониторинга качества вызовов.</span><span class="sxs-lookup"><span data-stu-id="728c8-109">The Get Dimension Members operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="get-dimension-members"></a><span data-ttu-id="728c8-110">Получение элементов измерений</span><span class="sxs-lookup"><span data-stu-id="728c8-110">Get Dimension Members</span></span>

<span data-ttu-id="728c8-111">Операция "Получить члены измерения" возвращает список членов определенного измерения.</span><span class="sxs-lookup"><span data-stu-id="728c8-111">Get Dimension Members operation returns the list of members of a specific dimension.</span></span> <span data-ttu-id="728c8-112">Кроме того, это позволяет фильтровать список участников и получать подмножество, чтобы сократить затраты на передачу данных по проводной сети.</span><span class="sxs-lookup"><span data-stu-id="728c8-112">It also give the ability to filter the member list and get a subset, to reduce the wire transfer cost.</span></span>
  

|<span data-ttu-id="728c8-113">**Способ**</span><span class="sxs-lookup"><span data-stu-id="728c8-113">**Method**</span></span>|<span data-ttu-id="728c8-114">**URI запроса**</span><span class="sxs-lookup"><span data-stu-id="728c8-114">**Request URI**</span></span>|<span data-ttu-id="728c8-115">**Версия HTTP**</span><span class="sxs-lookup"><span data-stu-id="728c8-115">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="728c8-116">POST</span><span class="sxs-lookup"><span data-stu-id="728c8-116">POST</span></span>  <br/> |<span data-ttu-id="728c8-117">https:// \<portal\> /QoEDataService/DimensionMembers</span><span class="sxs-lookup"><span data-stu-id="728c8-117">https://\<portal\>/QoEDataService/DimensionMembers</span></span>  <br/> |<span data-ttu-id="728c8-118">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="728c8-118">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="728c8-119">**Параметры URI** — нет.</span><span class="sxs-lookup"><span data-stu-id="728c8-119">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="728c8-120">**Request Headers** - No additional headers.</span><span class="sxs-lookup"><span data-stu-id="728c8-120">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="728c8-121">**Тело запроса** — содержит имя измерения, для которого нужны члены.</span><span class="sxs-lookup"><span data-stu-id="728c8-121">**Request Body** - This contains the name of dimension we want the members for.</span></span> <span data-ttu-id="728c8-122">Кроме того, вы можете указать максимальное количество возвращаемого числа членов, а также указать фильтрацию, чтобы ограничить возвращаемую часть.</span><span class="sxs-lookup"><span data-stu-id="728c8-122">Also max number of members returned, beside you can specify some filtering to limit the returned members.</span></span>
  
```json
{
"ByPassCache": false,
"DataModelName": "[StartDate].[Month]",
"SearchCaption": "",
"SearchValue": "",
"PageNumber": 0,
"PageSize": 8000
}
```

 <span data-ttu-id="728c8-123">**Ответ.** Ответ включает код состояния HTTP и набор загодеров отклика.</span><span class="sxs-lookup"><span data-stu-id="728c8-123">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="728c8-124">**Код состояния** : успешная операция возвращает код состояния 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="728c8-124">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="728c8-125">**Response Headers** - No additional headers.</span><span class="sxs-lookup"><span data-stu-id="728c8-125">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="728c8-126">**Тело ответа** . Ниже приведен пример полезной нагрузки ответа в JSON в ответ на запрос "[StartDate]. Измерение [Month]".</span><span class="sxs-lookup"><span data-stu-id="728c8-126">**Response Body** - Below is a sample response payload in JSON in response to a request for "[StartDate].[Month]" dimension.</span></span>
  
> [!NOTE]
> <span data-ttu-id="728c8-127">В списке отображается только небольшая часть списка.</span><span class="sxs-lookup"><span data-stu-id="728c8-127">The list is only showing a small portion of the list.</span></span> 
  
```json
{
"MembersCount": 493,
"Members": [["[1990-01-01T00:00:00]",
"January 1990"],
["[1990-02-01T00:00:00]",
"February 1990"],
["[1990-03-01T00:00:00]",
"March 1990"],
 
    ...
    
["[2030-10-01T00:00:00]",
"October 2030"],
["[2030-11-01T00:00:00]",
"November 2030"],
["[2030-12-01T00:00:00]",
"December 2030"],
["[2031-01-01T00:00:00]",
"January 2031"]]
}
```
