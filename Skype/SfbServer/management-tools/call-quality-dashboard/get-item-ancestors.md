---
title: Получить родительских элементов
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d39b1dbc-1514-43ec-8593-9f23b3fcae62
description: 'Сводка: сведения о операции "получение предков элементов", которая является частью службы номенклатур. Служба item входит в API репозитория для панели мониторинга качества звонков. Панель мониторинга качества звонков — это средство для Skype для бизнеса Server.'
ms.openlocfilehash: c82ae699cab0bf812f281fc2f2ad54323bcf8f7f
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992686"
---
# <a name="get-item-ancestors"></a><span data-ttu-id="7d1a0-105">Получить родительских элементов</span><span class="sxs-lookup"><span data-stu-id="7d1a0-105">Get Item Ancestors</span></span>
 
<span data-ttu-id="7d1a0-106">**Сводка:** Изучите операцию Get для предков элемента, которая является частью службы элемента.</span><span class="sxs-lookup"><span data-stu-id="7d1a0-106">**Summary:** Learn about the Get Item Ancestors operation, which is part of the Item Service.</span></span> <span data-ttu-id="7d1a0-107">Служба item входит в API репозитория для панели мониторинга качества звонков.</span><span class="sxs-lookup"><span data-stu-id="7d1a0-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="7d1a0-108">Панель мониторинга качества звонков — это средство для Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="7d1a0-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="7d1a0-109">Операция Get-предков элемента является частью службы элементов в API репозитория для панели мониторинга качества вызова.</span><span class="sxs-lookup"><span data-stu-id="7d1a0-109">The Get Item Ancestors operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-item-ancestors"></a><span data-ttu-id="7d1a0-110">Получить родительских элементов</span><span class="sxs-lookup"><span data-stu-id="7d1a0-110">Get Item Ancestors</span></span>

<span data-ttu-id="7d1a0-111">Получение предков элемента возвращает определенные предки элементов из репозитория.</span><span class="sxs-lookup"><span data-stu-id="7d1a0-111">Get Item Ancestors returns a specific items ancestors from the repository.</span></span>
  

|<span data-ttu-id="7d1a0-112">**Способов**</span><span class="sxs-lookup"><span data-stu-id="7d1a0-112">**Method**</span></span>|<span data-ttu-id="7d1a0-113">**URI запроса**</span><span class="sxs-lookup"><span data-stu-id="7d1a0-113">**Request URI**</span></span>|<span data-ttu-id="7d1a0-114">**Версия HTTP**</span><span class="sxs-lookup"><span data-stu-id="7d1a0-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="7d1a0-115">Получить</span><span class="sxs-lookup"><span data-stu-id="7d1a0-115">GET</span></span>  <br/> |<span data-ttu-id="7d1a0-116">/Коерепоситорисервице/репоситори/итеманцесторс/{итемид}\<портала\>HTTPS://</span><span class="sxs-lookup"><span data-stu-id="7d1a0-116">https://\<portal\>/QoERepositoryService/repository/itemAncestors/{itemId}</span></span>  <br/> |<span data-ttu-id="7d1a0-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="7d1a0-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="7d1a0-118">**Параметры универсального кода ресурса** (None).</span><span class="sxs-lookup"><span data-stu-id="7d1a0-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="7d1a0-119">**Заголовки запроса** — без дополнительных заголовков.</span><span class="sxs-lookup"><span data-stu-id="7d1a0-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="7d1a0-120">**Запросить текст** -None.</span><span class="sxs-lookup"><span data-stu-id="7d1a0-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="7d1a0-121">**Response (ответ** ) — ответ включает код состояния HTTP и набор заголовков ответа.</span><span class="sxs-lookup"><span data-stu-id="7d1a0-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="7d1a0-122">**Код состояния** — успешная операция возвращает код состояния 200 (ОК).</span><span class="sxs-lookup"><span data-stu-id="7d1a0-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="7d1a0-123">Если указанный идентификатор пользователя не найден, он возвращает код состояния 404 (не найден).</span><span class="sxs-lookup"><span data-stu-id="7d1a0-123">If a specified user ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="7d1a0-124">**Заголовки ответа** — без дополнительных заголовков.</span><span class="sxs-lookup"><span data-stu-id="7d1a0-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="7d1a0-125">**Тело ответа** — ниже показан пример полезных данных ответа в JSON.</span><span class="sxs-lookup"><span data-stu-id="7d1a0-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```json
[{
"item1": 1653,
"item2": 0,
"item3": "Audio Streams Monthly Trend"
},
{
"item1": 1652,
"item2": 1,
"item3": "All Audio Streams"
}]
```

 <span data-ttu-id="7d1a0-126">*Item1* — идентификатор элемента.</span><span class="sxs-lookup"><span data-stu-id="7d1a0-126">*Item1*  - ID of the item.</span></span>
  
 <span data-ttu-id="7d1a0-127">*Элем2* — глубина — расстояние от элемента.</span><span class="sxs-lookup"><span data-stu-id="7d1a0-127">*Item2*  - Depth is the distance from the Item.</span></span> <span data-ttu-id="7d1a0-128">0 — непосредственный родительский элемент.</span><span class="sxs-lookup"><span data-stu-id="7d1a0-128">0 is the immediate parent.</span></span>
  
 <span data-ttu-id="7d1a0-129">*Item3* — название элемента.</span><span class="sxs-lookup"><span data-stu-id="7d1a0-129">*Item3*  - Title of the item.</span></span>
  

