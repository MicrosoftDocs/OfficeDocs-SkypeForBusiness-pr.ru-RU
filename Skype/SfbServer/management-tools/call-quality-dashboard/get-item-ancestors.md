---
title: Получить родительских элементов
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d39b1dbc-1514-43ec-8593-9f23b3fcae62
description: 'Сводка: Сведения о операцию получения предков элемента, который является частью службы элемента. Служба элемент является частью API репозитория для панели мониторинга качества звонков. Панель мониторинга качества звонков — это средство для Скайп для Business Server.'
ms.openlocfilehash: 7afeecb81d1933b0a308b174e49f6d8ff45a93dd
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30873114"
---
# <a name="get-item-ancestors"></a><span data-ttu-id="36140-105">Получить родительских элементов</span><span class="sxs-lookup"><span data-stu-id="36140-105">Get Item Ancestors</span></span>
 
<span data-ttu-id="36140-106">**Сводка:** Узнайте о операцию получения предков элемента, который является частью службы элемента.</span><span class="sxs-lookup"><span data-stu-id="36140-106">**Summary:** Learn about the Get Item Ancestors operation, which is part of the Item Service.</span></span> <span data-ttu-id="36140-107">Служба элемент является частью API репозитория для панели мониторинга качества звонков.</span><span class="sxs-lookup"><span data-stu-id="36140-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="36140-108">Панель мониторинга качества звонков — это средство для Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="36140-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="36140-109">Операция получения предков элемента является частью службы элемента в API репозитория для панели мониторинга качества звонков.</span><span class="sxs-lookup"><span data-stu-id="36140-109">The Get Item Ancestors operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-item-ancestors"></a><span data-ttu-id="36140-110">Получить родительских элементов</span><span class="sxs-lookup"><span data-stu-id="36140-110">Get Item Ancestors</span></span>

<span data-ttu-id="36140-111">Получите предков элемента возвращает предков определенные элементы из репозитория.</span><span class="sxs-lookup"><span data-stu-id="36140-111">Get Item Ancestors returns a specific items ancestors from the repository.</span></span>
  

|<span data-ttu-id="36140-112">**Метод**</span><span class="sxs-lookup"><span data-stu-id="36140-112">**Method**</span></span>|<span data-ttu-id="36140-113">**URI запроса**</span><span class="sxs-lookup"><span data-stu-id="36140-113">**Request URI**</span></span>|<span data-ttu-id="36140-114">**Версия HTTP**</span><span class="sxs-lookup"><span data-stu-id="36140-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="36140-115">Получить</span><span class="sxs-lookup"><span data-stu-id="36140-115">GET</span></span>  <br/> |<span data-ttu-id="36140-116">https://\<портала\>/QoERepositoryService/репозитория/itemAncestors / {itemId}</span><span class="sxs-lookup"><span data-stu-id="36140-116">https://\<portal\>/QoERepositoryService/repository/itemAncestors/{itemId}</span></span>  <br/> |<span data-ttu-id="36140-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="36140-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="36140-118">**Параметры URI** — нет.</span><span class="sxs-lookup"><span data-stu-id="36140-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="36140-119">**Заголовки запроса** — без дополнительных заголовков.</span><span class="sxs-lookup"><span data-stu-id="36140-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="36140-120">**Текст запроса** — нет.</span><span class="sxs-lookup"><span data-stu-id="36140-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="36140-121">**Ответа** - ответ включает код состояния HTTP и набор заголовков ответов.</span><span class="sxs-lookup"><span data-stu-id="36140-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="36140-122">**Код состояния** - успешные операции возвращает код состояния 200 (ОК).</span><span class="sxs-lookup"><span data-stu-id="36140-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="36140-123">Если указанный пользователь с Идентификатором не найден, он возвращает код состояния 404 (не найден).</span><span class="sxs-lookup"><span data-stu-id="36140-123">If a specified user ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="36140-124">**Заголовки ответа** — без дополнительных заголовков.</span><span class="sxs-lookup"><span data-stu-id="36140-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="36140-125">**Тело ответа** - ниже приведен пример полезные данные ответа в формате JSON в.</span><span class="sxs-lookup"><span data-stu-id="36140-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```
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

 <span data-ttu-id="36140-126">*Item1* - идентификатор элемента.</span><span class="sxs-lookup"><span data-stu-id="36140-126">*Item1*  - ID of the item.</span></span>
  
 <span data-ttu-id="36140-127">*Item2* - глубина — это расстояние от элемента.</span><span class="sxs-lookup"><span data-stu-id="36140-127">*Item2*  - Depth is the distance from the Item.</span></span> <span data-ttu-id="36140-128">0 — это непосредственный родительский.</span><span class="sxs-lookup"><span data-stu-id="36140-128">0 is the immediate parent.</span></span>
  
 <span data-ttu-id="36140-129">*Item3* — название элемента.</span><span class="sxs-lookup"><span data-stu-id="36140-129">*Item3*  - Title of the item.</span></span>
  

