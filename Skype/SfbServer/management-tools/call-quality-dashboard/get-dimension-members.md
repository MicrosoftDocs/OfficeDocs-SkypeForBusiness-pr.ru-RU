---
title: Получение элементов измерений
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bd89bbf7-cb98-4cd8-bbfa-0484663d14db
description: 'Сводка: сведения о операции "получить элементы измерения". Операция Get Dimension Members является частью API данных для панели мониторинга качества звонков. Панель мониторинга качества звонков — это средство для Skype для бизнеса Server.'
ms.openlocfilehash: c457e7f3b42aaeb11c35180bc4c1ae6ee42b914e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274753"
---
# <a name="get-dimension-members"></a><span data-ttu-id="4180f-105">Получение элементов измерений</span><span class="sxs-lookup"><span data-stu-id="4180f-105">Get Dimension Members</span></span>
 
<span data-ttu-id="4180f-106">**Сводка:** Сведения о выполнении операции "получить элементы измерения".</span><span class="sxs-lookup"><span data-stu-id="4180f-106">**Summary:** Learn about the Get Dimension Members operation.</span></span> <span data-ttu-id="4180f-107">Операция Get Dimension Members является частью API данных для панели мониторинга качества звонков.</span><span class="sxs-lookup"><span data-stu-id="4180f-107">The Get Dimension Members operation is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="4180f-108">Панель мониторинга качества звонков — это средство для Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="4180f-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="4180f-109">Операция Get Dimension Members является частью API данных для панели мониторинга качества звонков.</span><span class="sxs-lookup"><span data-stu-id="4180f-109">The Get Dimension Members operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="get-dimension-members"></a><span data-ttu-id="4180f-110">Получение элементов измерений</span><span class="sxs-lookup"><span data-stu-id="4180f-110">Get Dimension Members</span></span>

<span data-ttu-id="4180f-111">Функция "получить элементы измерения" возвращает список элементов определенного измерения.</span><span class="sxs-lookup"><span data-stu-id="4180f-111">Get Dimension Members operation returns the list of members of a specific dimension.</span></span> <span data-ttu-id="4180f-112">Кроме того, она дает возможность отфильтровать список участников и получить подмножество, чтобы снизить стоимость передачи данных в сети.</span><span class="sxs-lookup"><span data-stu-id="4180f-112">It also give the ability to filter the member list and get a subset, to reduce the wire transfer cost.</span></span>
  

|<span data-ttu-id="4180f-113">**Способов**</span><span class="sxs-lookup"><span data-stu-id="4180f-113">**Method**</span></span>|<span data-ttu-id="4180f-114">**URI запроса**</span><span class="sxs-lookup"><span data-stu-id="4180f-114">**Request URI**</span></span>|<span data-ttu-id="4180f-115">**Версия HTTP**</span><span class="sxs-lookup"><span data-stu-id="4180f-115">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="4180f-116">Поместить</span><span class="sxs-lookup"><span data-stu-id="4180f-116">POST</span></span>  <br/> |<span data-ttu-id="4180f-117">/Коедатасервице/дименсионмемберс\<портала\>HTTPS://</span><span class="sxs-lookup"><span data-stu-id="4180f-117">https://\<portal\>/QoEDataService/DimensionMembers</span></span>  <br/> |<span data-ttu-id="4180f-118">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="4180f-118">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="4180f-119">**Параметры универсального кода ресурса** (None).</span><span class="sxs-lookup"><span data-stu-id="4180f-119">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="4180f-120">**Заголовки запроса** — без дополнительных заголовков.</span><span class="sxs-lookup"><span data-stu-id="4180f-120">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="4180f-121">**Текст Request** — в нем содержится название измерения, для которого нужно добавить участников.</span><span class="sxs-lookup"><span data-stu-id="4180f-121">**Request Body** - This contains the name of dimension we want the members for.</span></span> <span data-ttu-id="4180f-122">Кроме того, при возвращении предельного числа участников вы можете задать некоторые фильтры, чтобы ограничить возвращаемые элементы.</span><span class="sxs-lookup"><span data-stu-id="4180f-122">Also max number of members returned, beside you can specify some filtering to limit the returned members.</span></span>
  
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

 <span data-ttu-id="4180f-123">**Response (ответ** ) — ответ включает код состояния HTTP и набор заголовков ответа.</span><span class="sxs-lookup"><span data-stu-id="4180f-123">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="4180f-124">**Код состояния** — успешная операция возвращает код состояния 200 (ОК).</span><span class="sxs-lookup"><span data-stu-id="4180f-124">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="4180f-125">**Заголовки ответа** — без дополнительных заголовков.</span><span class="sxs-lookup"><span data-stu-id="4180f-125">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="4180f-126">**Тело ответа** — ниже показан пример полезных данных ответа в JSON в ответ на запрос "[StartDate]. Измерение [месяц] ".</span><span class="sxs-lookup"><span data-stu-id="4180f-126">**Response Body** - Below is a sample response payload in JSON in response to a request for "[StartDate].[Month]" dimension.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4180f-127">Список отображается только в небольшой части списка.</span><span class="sxs-lookup"><span data-stu-id="4180f-127">The list is only showing a small portion of the list.</span></span> 
  
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
