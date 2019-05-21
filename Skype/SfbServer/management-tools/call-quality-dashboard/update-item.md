---
title: Обновление элемента
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b1c15c56-cdae-4f3e-838a-52f0940cf729
description: 'Сводка: сведения об операции обновления элемента, которая входит в состав службы номенклатур. Служба item входит в API репозитория для панели мониторинга качества звонков. Панель мониторинга качества звонков — это средство для Skype для бизнеса Server.'
ms.openlocfilehash: aa46be0babf5998fcf2fabea797cb7a769914f8e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274536"
---
# <a name="update-item"></a><span data-ttu-id="f7595-105">Обновление элемента</span><span class="sxs-lookup"><span data-stu-id="f7595-105">Update Item</span></span>
 
<span data-ttu-id="f7595-106">**Сводка:** Сведения об операции обновления элемента, которая входит в состав службы номенклатур.</span><span class="sxs-lookup"><span data-stu-id="f7595-106">**Summary:** Learn about the Update Item operation, which is part of the Item Service.</span></span> <span data-ttu-id="f7595-107">Служба item входит в API репозитория для панели мониторинга качества звонков.</span><span class="sxs-lookup"><span data-stu-id="f7595-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="f7595-108">Панель мониторинга качества звонков — это средство для Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="f7595-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="f7595-109">Операция обновления элемента является частью службы элементов в API репозитория для панели мониторинга качества вызова.</span><span class="sxs-lookup"><span data-stu-id="f7595-109">The Update Item operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="update-item"></a><span data-ttu-id="f7595-110">Обновление элемента</span><span class="sxs-lookup"><span data-stu-id="f7595-110">Update Item</span></span>

<span data-ttu-id="f7595-111">Обновление элемента обновляет определенный элемент в репозитории.</span><span class="sxs-lookup"><span data-stu-id="f7595-111">Update Item updates a specific item in the repository.</span></span>
  

|<span data-ttu-id="f7595-112">**Способов**</span><span class="sxs-lookup"><span data-stu-id="f7595-112">**Method**</span></span>|<span data-ttu-id="f7595-113">**URI запроса**</span><span class="sxs-lookup"><span data-stu-id="f7595-113">**Request URI**</span></span>|<span data-ttu-id="f7595-114">**Версия HTTP**</span><span class="sxs-lookup"><span data-stu-id="f7595-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f7595-115">Установка</span><span class="sxs-lookup"><span data-stu-id="f7595-115">PUT</span></span>  <br/> |<span data-ttu-id="f7595-116">/Коерепоситорисервице/репоситори/итем/{итемид}\<портала\>HTTPS://</span><span class="sxs-lookup"><span data-stu-id="f7595-116">https://\<portal\>/QoERepositoryService/repository/item/{itemId}</span></span>  <br/> |<span data-ttu-id="f7595-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="f7595-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="f7595-118">**Параметры универсального кода ресурса** (None).</span><span class="sxs-lookup"><span data-stu-id="f7595-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="f7595-119">**Заголовки запроса** — тип содержимого: Application/JSON.</span><span class="sxs-lookup"><span data-stu-id="f7595-119">**Request Headers** -Content-Type: application/json.</span></span>
  
 <span data-ttu-id="f7595-120">**Текст запроса** — JSON.</span><span class="sxs-lookup"><span data-stu-id="f7595-120">**Request Body** - JSON.</span></span>
  
<span data-ttu-id="f7595-121">Пример полезных данных запроса:</span><span class="sxs-lookup"><span data-stu-id="f7595-121">Sample request payload:</span></span>
  
```
{
  content : "{ 'Product' : 'New Product Name'",
  type: "application/json"
}
```

 <span data-ttu-id="f7595-122">*Content (содержимое* )  Данные в формате JSON, сохраняемые в виде нового содержимого существующего подэлемента.</span><span class="sxs-lookup"><span data-stu-id="f7595-122">*content*  JSON formatted data to be stored as the new content of an existing sub-Item.</span></span> <span data-ttu-id="f7595-123">Технически, в репозитории может храниться любое содержимое любой схемы, но при использовании для панели мониторинга качества звонков требуется либо отчет, либо запрос.</span><span class="sxs-lookup"><span data-stu-id="f7595-123">Technically, a repository can store any content of any schema, but when used for Call Quality Dashboard, it should be either a report or a query.</span></span> <span data-ttu-id="f7595-124">*Type (тип* )  Всегда указывайте "Application/JSON" для панели мониторинга качества звонков.</span><span class="sxs-lookup"><span data-stu-id="f7595-124">*type*  Always specify "application/json" for Call Quality Dashboard.</span></span>
  
 <span data-ttu-id="f7595-125">**Response (ответ** ) — ответ включает код состояния HTTP и набор заголовков ответа.</span><span class="sxs-lookup"><span data-stu-id="f7595-125">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="f7595-126">**Код состояния** — успешная операция возвращает код состояния 204 (нет контента).</span><span class="sxs-lookup"><span data-stu-id="f7595-126">**Status Code** - A successful operation returns status code 204 (No Content).</span></span> <span data-ttu-id="f7595-127">Если указанный идентификатор элемента не найден, возвращается код состояния 404 (не найден).</span><span class="sxs-lookup"><span data-stu-id="f7595-127">If a specified item ID is not found, it returns status code 404 (Not Found).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="f7595-128">"Отсутствие содержимого" не является состоянием ошибки.</span><span class="sxs-lookup"><span data-stu-id="f7595-128">"No Content" is not an error status.</span></span> <span data-ttu-id="f7595-129">Это означает, что ответ не возвращал ничего в тексте (в отличие от 200 ОК возвращает содержимое в теле).</span><span class="sxs-lookup"><span data-stu-id="f7595-129">It means that a response did not return anything in the body (in contrast, 200 OK returns content in Body).</span></span> <span data-ttu-id="f7595-130">Оно указывает на то, что элемент успешно обновлен.</span><span class="sxs-lookup"><span data-stu-id="f7595-130">It indicates that the Item was successfully updated.</span></span> 
  
 <span data-ttu-id="f7595-131">**Заголовки ответа** — нет.</span><span class="sxs-lookup"><span data-stu-id="f7595-131">**Response Headers** - None.</span></span>
  
 <span data-ttu-id="f7595-132">**Текст ответа** — None (нет).</span><span class="sxs-lookup"><span data-stu-id="f7595-132">**Response Body** - None.</span></span>
  

