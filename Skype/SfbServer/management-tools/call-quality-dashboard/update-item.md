---
title: Обновление элемента
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
ms.assetid: b1c15c56-cdae-4f3e-838a-52f0940cf729
description: Сводка. Сведения об операции обновления элемента, которая входит в состав службы элементов. Служба элементов является частью API репозитория для панели мониторинга качества вызовов. Панель мониторинга качества звонков — это инструмент для Skype для бизнеса Server.
ms.openlocfilehash: 78da2fa414b4ba266f9e6aba4feac5ff73150062
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803089"
---
# <a name="update-item"></a><span data-ttu-id="1c75b-105">Обновление элемента</span><span class="sxs-lookup"><span data-stu-id="1c75b-105">Update Item</span></span>
 
<span data-ttu-id="1c75b-106">**Сводка:** Узнайте об операции обновления элемента, которая входит в состав службы элементов.</span><span class="sxs-lookup"><span data-stu-id="1c75b-106">**Summary:** Learn about the Update Item operation, which is part of the Item Service.</span></span> <span data-ttu-id="1c75b-107">Служба элементов является частью API репозитория для панели мониторинга качества вызовов.</span><span class="sxs-lookup"><span data-stu-id="1c75b-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="1c75b-108">Панель мониторинга качества звонков — это инструмент для Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="1c75b-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="1c75b-109">Операция "Обновление элемента" является частью службы элементов в API репозитория для панели мониторинга качества вызовов.</span><span class="sxs-lookup"><span data-stu-id="1c75b-109">The Update Item operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="update-item"></a><span data-ttu-id="1c75b-110">Обновление элемента</span><span class="sxs-lookup"><span data-stu-id="1c75b-110">Update Item</span></span>

<span data-ttu-id="1c75b-111">Обновление элемента обновляет определенный элемент в репозитории.</span><span class="sxs-lookup"><span data-stu-id="1c75b-111">Update Item updates a specific item in the repository.</span></span>
  

|<span data-ttu-id="1c75b-112">**Способ**</span><span class="sxs-lookup"><span data-stu-id="1c75b-112">**Method**</span></span>|<span data-ttu-id="1c75b-113">**URI запроса**</span><span class="sxs-lookup"><span data-stu-id="1c75b-113">**Request URI**</span></span>|<span data-ttu-id="1c75b-114">**Версия HTTP**</span><span class="sxs-lookup"><span data-stu-id="1c75b-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1c75b-115">PUT</span><span class="sxs-lookup"><span data-stu-id="1c75b-115">PUT</span></span>  <br/> |<span data-ttu-id="1c75b-116">https:// \<portal\> /QoERepositoryService/repository/item/{itemId}</span><span class="sxs-lookup"><span data-stu-id="1c75b-116">https://\<portal\>/QoERepositoryService/repository/item/{itemId}</span></span>  <br/> |<span data-ttu-id="1c75b-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="1c75b-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="1c75b-118">**Параметры URI** — нет.</span><span class="sxs-lookup"><span data-stu-id="1c75b-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="1c75b-119">**Request Headers** -Content-Type: application/json.</span><span class="sxs-lookup"><span data-stu-id="1c75b-119">**Request Headers** -Content-Type: application/json.</span></span>
  
 <span data-ttu-id="1c75b-120">**Тело запроса** — JSON.</span><span class="sxs-lookup"><span data-stu-id="1c75b-120">**Request Body** - JSON.</span></span>
  
<span data-ttu-id="1c75b-121">Пример полезной нагрузки запроса:</span><span class="sxs-lookup"><span data-stu-id="1c75b-121">Sample request payload:</span></span>
  
```json
{
  content : "{ 'Product' : 'New Product Name'",
  type: "application/json"
}
```

 <span data-ttu-id="1c75b-122">*content*  Данные в формате JSON, которые будут храниться в качестве нового содержимого существующего в подчиненного элемента.</span><span class="sxs-lookup"><span data-stu-id="1c75b-122">*content*  JSON formatted data to be stored as the new content of an existing sub-Item.</span></span> <span data-ttu-id="1c75b-123">С технической точки000 г. репозиторий может хранить любое содержимое любой схемы, но при этом он должен быть либо отчетом, либо запросом.</span><span class="sxs-lookup"><span data-stu-id="1c75b-123">Technically, a repository can store any content of any schema, but when used for Call Quality Dashboard, it should be either a report or a query.</span></span> <span data-ttu-id="1c75b-124">*type*  Всегда укажите "application/json" для панели мониторинга качества вызовов.</span><span class="sxs-lookup"><span data-stu-id="1c75b-124">*type*  Always specify "application/json" for Call Quality Dashboard.</span></span>
  
 <span data-ttu-id="1c75b-125">**Ответ.** Ответ включает код состояния HTTP и набор загодеров отклика.</span><span class="sxs-lookup"><span data-stu-id="1c75b-125">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="1c75b-126">**Код состояния** : успешная операция возвращает код состояния 204 (без содержимого).</span><span class="sxs-lookup"><span data-stu-id="1c75b-126">**Status Code** - A successful operation returns status code 204 (No Content).</span></span> <span data-ttu-id="1c75b-127">Если указанный код элемента не найден, возвращается код состояния 404 (не найден).</span><span class="sxs-lookup"><span data-stu-id="1c75b-127">If a specified item ID is not found, it returns status code 404 (Not Found).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="1c75b-128">Состояние "Нет содержимого" не является состоянием ошибки.</span><span class="sxs-lookup"><span data-stu-id="1c75b-128">"No Content" is not an error status.</span></span> <span data-ttu-id="1c75b-129">Это означает, что ответ не вернул ничего в теле (с другой стороны, 200 OK возвращает содержимое в теле).</span><span class="sxs-lookup"><span data-stu-id="1c75b-129">It means that a response did not return anything in the body (in contrast, 200 OK returns content in Body).</span></span> <span data-ttu-id="1c75b-130">Это означает, что элемент был успешно обновлен.</span><span class="sxs-lookup"><span data-stu-id="1c75b-130">It indicates that the Item was successfully updated.</span></span> 
  
 <span data-ttu-id="1c75b-131">**Response Headers** — None.</span><span class="sxs-lookup"><span data-stu-id="1c75b-131">**Response Headers** - None.</span></span>
  
 <span data-ttu-id="1c75b-132">**Тело ответа** — нет.</span><span class="sxs-lookup"><span data-stu-id="1c75b-132">**Response Body** - None.</span></span>
  

