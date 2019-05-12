---
title: Обновление элемента
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b1c15c56-cdae-4f3e-838a-52f0940cf729
description: 'Сводка: Сведения об операции обновление элемента, который является частью службы элемента. Служба элемент является частью API репозитория для панели мониторинга качества звонков. Панель мониторинга качества звонков — это средство для Скайп для Business Server.'
ms.openlocfilehash: 6ccdcd401b8f65193fd7e7f93b94c25b8540d1c0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33915033"
---
# <a name="update-item"></a><span data-ttu-id="86b3e-105">Обновление элемента</span><span class="sxs-lookup"><span data-stu-id="86b3e-105">Update Item</span></span>
 
<span data-ttu-id="86b3e-106">**Сводка:** Сведения об операции обновление элемента, который является частью службы элемента.</span><span class="sxs-lookup"><span data-stu-id="86b3e-106">**Summary:** Learn about the Update Item operation, which is part of the Item Service.</span></span> <span data-ttu-id="86b3e-107">Служба элемент является частью API репозитория для панели мониторинга качества звонков.</span><span class="sxs-lookup"><span data-stu-id="86b3e-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="86b3e-108">Панель мониторинга качества звонков — это средство для Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="86b3e-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="86b3e-109">Обновление элемента операция является частью службы элемента в API репозитория для панели мониторинга качества звонков.</span><span class="sxs-lookup"><span data-stu-id="86b3e-109">The Update Item operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="update-item"></a><span data-ttu-id="86b3e-110">Обновление элемента</span><span class="sxs-lookup"><span data-stu-id="86b3e-110">Update Item</span></span>

<span data-ttu-id="86b3e-111">Обновление элемента обновляет определенного элемента в репозитории.</span><span class="sxs-lookup"><span data-stu-id="86b3e-111">Update Item updates a specific item in the repository.</span></span>
  

|<span data-ttu-id="86b3e-112">**Метод**</span><span class="sxs-lookup"><span data-stu-id="86b3e-112">**Method**</span></span>|<span data-ttu-id="86b3e-113">**URI запроса**</span><span class="sxs-lookup"><span data-stu-id="86b3e-113">**Request URI**</span></span>|<span data-ttu-id="86b3e-114">**Версия HTTP**</span><span class="sxs-lookup"><span data-stu-id="86b3e-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="86b3e-115">РАЗМЕЩЕНИЕ</span><span class="sxs-lookup"><span data-stu-id="86b3e-115">PUT</span></span>  <br/> |<span data-ttu-id="86b3e-116">https://\<портала\>/QoERepositoryService/репозитория/элемент / {itemId}</span><span class="sxs-lookup"><span data-stu-id="86b3e-116">https://\<portal\>/QoERepositoryService/repository/item/{itemId}</span></span>  <br/> |<span data-ttu-id="86b3e-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="86b3e-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="86b3e-118">**Параметры URI** — нет.</span><span class="sxs-lookup"><span data-stu-id="86b3e-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="86b3e-119">**Заголовки Request** -контента-тип: приложение/json.</span><span class="sxs-lookup"><span data-stu-id="86b3e-119">**Request Headers** -Content-Type: application/json.</span></span>
  
 <span data-ttu-id="86b3e-120">**Текст запроса** - JSON.</span><span class="sxs-lookup"><span data-stu-id="86b3e-120">**Request Body** - JSON.</span></span>
  
<span data-ttu-id="86b3e-121">Пример полезных данных запроса:</span><span class="sxs-lookup"><span data-stu-id="86b3e-121">Sample request payload:</span></span>
  
```
{
  content : "{ 'Product' : 'New Product Name'",
  type: "application/json"
}
```

 <span data-ttu-id="86b3e-122">*контент*  Данных, хранимых в новое содержимое существующий дочерний элемент в формате JSON.</span><span class="sxs-lookup"><span data-stu-id="86b3e-122">*content*  JSON formatted data to be stored as the new content of an existing sub-Item.</span></span> <span data-ttu-id="86b3e-123">Технически репозиторию можно хранить любое содержимое любого схемы, но при использовании для панели мониторинга качества звонков, следует отчета или запроса.</span><span class="sxs-lookup"><span data-stu-id="86b3e-123">Technically, a repository can store any content of any schema, but when used for Call Quality Dashboard, it should be either a report or a query.</span></span> <span data-ttu-id="86b3e-124">*Тип*  Всегда укажите «application/json» для вызова панели мониторинга качества.</span><span class="sxs-lookup"><span data-stu-id="86b3e-124">*type*  Always specify "application/json" for Call Quality Dashboard.</span></span>
  
 <span data-ttu-id="86b3e-125">**Ответа** - ответ включает код состояния HTTP и набор заголовков ответов.</span><span class="sxs-lookup"><span data-stu-id="86b3e-125">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="86b3e-126">**Код состояния** - успешные операции возвращает код состояния 204 (нет содержимого).</span><span class="sxs-lookup"><span data-stu-id="86b3e-126">**Status Code** - A successful operation returns status code 204 (No Content).</span></span> <span data-ttu-id="86b3e-127">Если элемент с указанным Идентификатором не найден, возвращает код состояния 404 (не найден).</span><span class="sxs-lookup"><span data-stu-id="86b3e-127">If a specified item ID is not found, it returns status code 404 (Not Found).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="86b3e-128">«Нет содержимого» не является состояние ошибки.</span><span class="sxs-lookup"><span data-stu-id="86b3e-128">"No Content" is not an error status.</span></span> <span data-ttu-id="86b3e-129">Это означает, что ответ не вернула все действия в тексте запроса (в отличие от, 200 OK возвращает содержимое в тексте).</span><span class="sxs-lookup"><span data-stu-id="86b3e-129">It means that a response did not return anything in the body (in contrast, 200 OK returns content in Body).</span></span> <span data-ttu-id="86b3e-130">Указывает, что элемент был успешно обновлены.</span><span class="sxs-lookup"><span data-stu-id="86b3e-130">It indicates that the Item was successfully updated.</span></span> 
  
 <span data-ttu-id="86b3e-131">**Заголовки ответа** — нет.</span><span class="sxs-lookup"><span data-stu-id="86b3e-131">**Response Headers** - None.</span></span>
  
 <span data-ttu-id="86b3e-132">**Тело ответа** — нет.</span><span class="sxs-lookup"><span data-stu-id="86b3e-132">**Response Body** - None.</span></span>
  

