---
title: Получение элемента
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
ms.assetid: e77bf649-d62a-4d94-80de-066ba47730cd
description: Сводка. Сведения об операции "Получить элемент", которая входит в состав службы элементов. Служба элементов является частью API репозитория для панели мониторинга качества вызовов. Панель мониторинга качества звонков — это инструмент для Skype для бизнеса Server.
ms.openlocfilehash: 896540c4572fb3991356ce055f01690ed702c6f2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832569"
---
# <a name="get-item"></a><span data-ttu-id="6fb2b-105">Получение элемента</span><span class="sxs-lookup"><span data-stu-id="6fb2b-105">Get Item</span></span>
 
<span data-ttu-id="6fb2b-106">**Сводка:** Узнайте об операции "Получить элемент", которая входит в состав службы элементов.</span><span class="sxs-lookup"><span data-stu-id="6fb2b-106">**Summary:** Learn about the Get Item operation, which is part of the Item Service.</span></span> <span data-ttu-id="6fb2b-107">Служба элементов является частью API репозитория для панели мониторинга качества вызовов.</span><span class="sxs-lookup"><span data-stu-id="6fb2b-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="6fb2b-108">Панель мониторинга качества звонков — это инструмент для Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="6fb2b-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="6fb2b-109">Операция "Получить элемент" является частью службы элементов в API репозитория для панели мониторинга качества вызовов.</span><span class="sxs-lookup"><span data-stu-id="6fb2b-109">The Get Item operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-item"></a><span data-ttu-id="6fb2b-110">Получение элемента</span><span class="sxs-lookup"><span data-stu-id="6fb2b-110">Get Item</span></span>

<span data-ttu-id="6fb2b-111">Get Item возвращает определенный элемент в репозитории.</span><span class="sxs-lookup"><span data-stu-id="6fb2b-111">Get Item returns a specific item in the repository.</span></span>
  
|<span data-ttu-id="6fb2b-112">**Способ**</span><span class="sxs-lookup"><span data-stu-id="6fb2b-112">**Method**</span></span>|<span data-ttu-id="6fb2b-113">**URI запроса**</span><span class="sxs-lookup"><span data-stu-id="6fb2b-113">**Request URI**</span></span>|<span data-ttu-id="6fb2b-114">**Версия HTTP**</span><span class="sxs-lookup"><span data-stu-id="6fb2b-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6fb2b-115">GET</span><span class="sxs-lookup"><span data-stu-id="6fb2b-115">GET</span></span>  <br/> |<span data-ttu-id="6fb2b-116">https:// \<portal\> /QoERepositoryService/repository/item/{itemId}</span><span class="sxs-lookup"><span data-stu-id="6fb2b-116">https://\<portal\>/QoERepositoryService/repository/item/{itemId}</span></span>  <br/> |<span data-ttu-id="6fb2b-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="6fb2b-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="6fb2b-118">**Параметры URI** — нет.</span><span class="sxs-lookup"><span data-stu-id="6fb2b-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="6fb2b-119">**Request Headers** - No additional headers.</span><span class="sxs-lookup"><span data-stu-id="6fb2b-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="6fb2b-120">**Тело запроса** — нет.</span><span class="sxs-lookup"><span data-stu-id="6fb2b-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="6fb2b-121">**Ответ.** Ответ включает код состояния HTTP и набор загодеров отклика.</span><span class="sxs-lookup"><span data-stu-id="6fb2b-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="6fb2b-122">**Код состояния** — успешная операция возвращает код состояния 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="6fb2b-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="6fb2b-123">Если указанный код элемента не найден, возвращается код состояния 404 (не найден).</span><span class="sxs-lookup"><span data-stu-id="6fb2b-123">If a specified item ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="6fb2b-124">**Response Headers** - No additional headers.</span><span class="sxs-lookup"><span data-stu-id="6fb2b-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="6fb2b-125">**Тело ответа.** Ниже приведен пример полезной нагрузки ответа в JSON.</span><span class="sxs-lookup"><span data-stu-id="6fb2b-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```json
{
"itemId": 1652,
"userId": 0,
"content": "{\"Title\":\"All Audio Streams\",...}",
"type": "application/json",
"subItemIds": [1653, 1710]
}
```

 <span data-ttu-id="6fb2b-126">*itemId*  — ИД элемента.</span><span class="sxs-lookup"><span data-stu-id="6fb2b-126">*itemId*  - ID of the item.</span></span>
  
 <span data-ttu-id="6fb2b-127">*userId*  — ИД пользователя, которому принадлежит этот элемент.</span><span class="sxs-lookup"><span data-stu-id="6fb2b-127">*userId*  - ID of the user who owns this item.</span></span>
  
 <span data-ttu-id="6fb2b-128">*content*  — содержимое для конкретного приложения.</span><span class="sxs-lookup"><span data-stu-id="6fb2b-128">*content*  - The application-specific content.</span></span>
  
 <span data-ttu-id="6fb2b-129">*type*  — тип контента.</span><span class="sxs-lookup"><span data-stu-id="6fb2b-129">*type*  - The type of the content.</span></span> <span data-ttu-id="6fb2b-130">Это поле устанавливается приложениями.</span><span class="sxs-lookup"><span data-stu-id="6fb2b-130">This field is set by the applications.</span></span>
  
 <span data-ttu-id="6fb2b-131">*subItemIds*  — ИД в субподрядных элементов, если они есть.</span><span class="sxs-lookup"><span data-stu-id="6fb2b-131">*subItemIds*  - The IDs of sub-Items, if any.</span></span> <span data-ttu-id="6fb2b-132">Это кратковременная операция Get Sub-Items для сохранения вызова.</span><span class="sxs-lookup"><span data-stu-id="6fb2b-132">This is a short-circuit of Get Sub-Items operation to save a call.</span></span> <span data-ttu-id="6fb2b-133">Приложения также могут получить те же сведения с помощью операции Get Sub-Items.</span><span class="sxs-lookup"><span data-stu-id="6fb2b-133">Applications can alternatively obtain the same information using Get Sub-Items operation.</span></span>
  

