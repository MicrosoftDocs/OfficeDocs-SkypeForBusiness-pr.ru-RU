---
title: Получить родительских элементов
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
ms.assetid: d39b1dbc-1514-43ec-8593-9f23b3fcae62
description: Сводка. Сведения об операции "Получить предков элемента", которая входит в состав службы элементов. Служба элементов является частью API репозитория для панели мониторинга качества вызовов. Панель мониторинга качества звонков — это инструмент для Skype для бизнеса Server.
ms.openlocfilehash: 59fcd10f620b32151346e8732e67ae6151a258ff
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832579"
---
# <a name="get-item-ancestors"></a><span data-ttu-id="6a9b0-105">Получить родительских элементов</span><span class="sxs-lookup"><span data-stu-id="6a9b0-105">Get Item Ancestors</span></span>
 
<span data-ttu-id="6a9b0-106">**Сводка:** Узнайте об операции "Получить предки элемента", которая входит в состав службы элементов.</span><span class="sxs-lookup"><span data-stu-id="6a9b0-106">**Summary:** Learn about the Get Item Ancestors operation, which is part of the Item Service.</span></span> <span data-ttu-id="6a9b0-107">Служба элементов является частью API репозитория для панели мониторинга качества вызовов.</span><span class="sxs-lookup"><span data-stu-id="6a9b0-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="6a9b0-108">Панель мониторинга качества звонков — это инструмент для Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="6a9b0-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="6a9b0-109">Операция "Получить предков элемента" является частью службы элементов в API репозитория для панели мониторинга качества вызовов.</span><span class="sxs-lookup"><span data-stu-id="6a9b0-109">The Get Item Ancestors operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-item-ancestors"></a><span data-ttu-id="6a9b0-110">Получить родительских элементов</span><span class="sxs-lookup"><span data-stu-id="6a9b0-110">Get Item Ancestors</span></span>

<span data-ttu-id="6a9b0-111">Get Item Ancestors returns a specific items ancestors from the repository.</span><span class="sxs-lookup"><span data-stu-id="6a9b0-111">Get Item Ancestors returns a specific items ancestors from the repository.</span></span>
  

|<span data-ttu-id="6a9b0-112">**Способ**</span><span class="sxs-lookup"><span data-stu-id="6a9b0-112">**Method**</span></span>|<span data-ttu-id="6a9b0-113">**URI запроса**</span><span class="sxs-lookup"><span data-stu-id="6a9b0-113">**Request URI**</span></span>|<span data-ttu-id="6a9b0-114">**Версия HTTP**</span><span class="sxs-lookup"><span data-stu-id="6a9b0-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6a9b0-115">GET</span><span class="sxs-lookup"><span data-stu-id="6a9b0-115">GET</span></span>  <br/> |<span data-ttu-id="6a9b0-116">https:// \<portal\> /QoERepositoryService/repository/itemAncestors/{itemId}</span><span class="sxs-lookup"><span data-stu-id="6a9b0-116">https://\<portal\>/QoERepositoryService/repository/itemAncestors/{itemId}</span></span>  <br/> |<span data-ttu-id="6a9b0-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="6a9b0-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="6a9b0-118">**Параметры URI** — нет.</span><span class="sxs-lookup"><span data-stu-id="6a9b0-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="6a9b0-119">**Request Headers** - No additional headers.</span><span class="sxs-lookup"><span data-stu-id="6a9b0-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="6a9b0-120">**Тело запроса** — нет.</span><span class="sxs-lookup"><span data-stu-id="6a9b0-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="6a9b0-121">**Ответ.** Ответ включает код состояния HTTP и набор загодеров отклика.</span><span class="sxs-lookup"><span data-stu-id="6a9b0-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="6a9b0-122">**Код состояния** : успешная операция возвращает код состояния 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="6a9b0-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="6a9b0-123">Если указанный код пользователя не найден, возвращается код состояния 404 (не найден).</span><span class="sxs-lookup"><span data-stu-id="6a9b0-123">If a specified user ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="6a9b0-124">**Response Headers** - No additional headers.</span><span class="sxs-lookup"><span data-stu-id="6a9b0-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="6a9b0-125">**Тело ответа.** Ниже приведен пример полезной нагрузки ответа в JSON.</span><span class="sxs-lookup"><span data-stu-id="6a9b0-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
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

 <span data-ttu-id="6a9b0-126">*Item1*  — ИД элемента.</span><span class="sxs-lookup"><span data-stu-id="6a9b0-126">*Item1*  - ID of the item.</span></span>
  
 <span data-ttu-id="6a9b0-127">*Item2*  — глубина — это расстояние от элемента.</span><span class="sxs-lookup"><span data-stu-id="6a9b0-127">*Item2*  - Depth is the distance from the Item.</span></span> <span data-ttu-id="6a9b0-128">0 — непосредственный родительский.</span><span class="sxs-lookup"><span data-stu-id="6a9b0-128">0 is the immediate parent.</span></span>
  
 <span data-ttu-id="6a9b0-129">*Item3*  — заголовок элемента.</span><span class="sxs-lookup"><span data-stu-id="6a9b0-129">*Item3*  - Title of the item.</span></span>
  

