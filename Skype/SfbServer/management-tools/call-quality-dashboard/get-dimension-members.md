---
title: Получение элементов измерений
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bd89bbf7-cb98-4cd8-bbfa-0484663d14db
description: 'Сводка: Сведения о выполняемой операции получения элементов измерения. Получение элементов измерения операции является частью API данных для панели мониторинга качества звонков. Панель мониторинга качества звонков — это средство для Скайп для Business Server.'
ms.openlocfilehash: 482fe92a95c6754695e983ed9ff0ec69ed7a442b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33926095"
---
# <a name="get-dimension-members"></a><span data-ttu-id="e983d-105">Получение элементов измерений</span><span class="sxs-lookup"><span data-stu-id="e983d-105">Get Dimension Members</span></span>
 
<span data-ttu-id="e983d-106">**Сводка:** Сведения о выполняемой операции получения элементов измерения.</span><span class="sxs-lookup"><span data-stu-id="e983d-106">**Summary:** Learn about the Get Dimension Members operation.</span></span> <span data-ttu-id="e983d-107">Получение элементов измерения операции является частью API данных для панели мониторинга качества звонков.</span><span class="sxs-lookup"><span data-stu-id="e983d-107">The Get Dimension Members operation is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="e983d-108">Панель мониторинга качества звонков — это средство для Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="e983d-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="e983d-109">Получение элементов измерения операции является частью API данных для панели мониторинга качества звонков.</span><span class="sxs-lookup"><span data-stu-id="e983d-109">The Get Dimension Members operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="get-dimension-members"></a><span data-ttu-id="e983d-110">Получение элементов измерений</span><span class="sxs-lookup"><span data-stu-id="e983d-110">Get Dimension Members</span></span>

<span data-ttu-id="e983d-111">Элементы измерения операции Get возвращает список элементов конкретного измерения.</span><span class="sxs-lookup"><span data-stu-id="e983d-111">Get Dimension Members operation returns the list of members of a specific dimension.</span></span> <span data-ttu-id="e983d-112">Также дают возможность фильтрации элементов списка и получение подмножества, сократить расходы на перемещение проводов.</span><span class="sxs-lookup"><span data-stu-id="e983d-112">It also give the ability to filter the member list and get a subset, to reduce the wire transfer cost.</span></span>
  

|<span data-ttu-id="e983d-113">**Метод**</span><span class="sxs-lookup"><span data-stu-id="e983d-113">**Method**</span></span>|<span data-ttu-id="e983d-114">**URI запроса**</span><span class="sxs-lookup"><span data-stu-id="e983d-114">**Request URI**</span></span>|<span data-ttu-id="e983d-115">**Версия HTTP**</span><span class="sxs-lookup"><span data-stu-id="e983d-115">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e983d-116">Поместить</span><span class="sxs-lookup"><span data-stu-id="e983d-116">POST</span></span>  <br/> |<span data-ttu-id="e983d-117">https://\<портала\>/QoEDataService/DimensionMembers</span><span class="sxs-lookup"><span data-stu-id="e983d-117">https://\<portal\>/QoEDataService/DimensionMembers</span></span>  <br/> |<span data-ttu-id="e983d-118">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="e983d-118">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="e983d-119">**Параметры URI** — нет.</span><span class="sxs-lookup"><span data-stu-id="e983d-119">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="e983d-120">**Заголовки запроса** — без дополнительных заголовков.</span><span class="sxs-lookup"><span data-stu-id="e983d-120">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="e983d-121">**Текст запроса** — содержит имя мы хотели элементы для измерения.</span><span class="sxs-lookup"><span data-stu-id="e983d-121">**Request Body** - This contains the name of dimension we want the members for.</span></span> <span data-ttu-id="e983d-122">Также возвращает максимальное число элементов, рядом с полем можно указать некоторые фильтрации для ограничения возвращаемых членов.</span><span class="sxs-lookup"><span data-stu-id="e983d-122">Also max number of members returned, beside you can specify some filtering to limit the returned members.</span></span>
  
```
{
"ByPassCache": false,
"DataModelName": "[StartDate].[Month]",
"SearchCaption": "",
"SearchValue": "",
"PageNumber": 0,
"PageSize": 8000
}
```

 <span data-ttu-id="e983d-123">**Ответа** - ответ включает код состояния HTTP и набор заголовков ответов.</span><span class="sxs-lookup"><span data-stu-id="e983d-123">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="e983d-124">**Код состояния** - успешные операции возвращает код состояния 200 (ОК).</span><span class="sxs-lookup"><span data-stu-id="e983d-124">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="e983d-125">**Заголовки ответа** — без дополнительных заголовков.</span><span class="sxs-lookup"><span data-stu-id="e983d-125">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="e983d-126">**Тело ответа** - ниже приведен пример ответа полезной нагрузки в JSON в ответ на запрос «[StartDate]. [Месяц]» измерения.</span><span class="sxs-lookup"><span data-stu-id="e983d-126">**Response Body** - Below is a sample response payload in JSON in response to a request for "[StartDate].[Month]" dimension.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e983d-127">Список отображается только небольшую часть списка.</span><span class="sxs-lookup"><span data-stu-id="e983d-127">The list is only showing a small portion of the list.</span></span> 
  
```
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
