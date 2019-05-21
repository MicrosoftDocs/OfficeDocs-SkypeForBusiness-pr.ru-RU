---
title: Получение элемента
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: e77bf649-d62a-4d94-80de-066ba47730cd
description: 'Сводка: сведения о операции получения элемента, которая входит в состав службы номенклатур. Служба item входит в API репозитория для панели мониторинга качества звонков. Панель мониторинга качества звонков — это средство для Skype для бизнеса Server.'
ms.openlocfilehash: bfd5015603ac73fb48c4e30635cf8ae0fb14bf13
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274718"
---
# <a name="get-item"></a><span data-ttu-id="e6096-105">Получение элемента</span><span class="sxs-lookup"><span data-stu-id="e6096-105">Get Item</span></span>
 
<span data-ttu-id="e6096-106">**Сводка:** Сведения об операции получения элемента, которая входит в состав службы номенклатур.</span><span class="sxs-lookup"><span data-stu-id="e6096-106">**Summary:** Learn about the Get Item operation, which is part of the Item Service.</span></span> <span data-ttu-id="e6096-107">Служба item входит в API репозитория для панели мониторинга качества звонков.</span><span class="sxs-lookup"><span data-stu-id="e6096-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="e6096-108">Панель мониторинга качества звонков — это средство для Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="e6096-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="e6096-109">Операция Get Item является частью службы элементов в API репозитория для панели мониторинга качества вызова.</span><span class="sxs-lookup"><span data-stu-id="e6096-109">The Get Item operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-item"></a><span data-ttu-id="e6096-110">Получение элемента</span><span class="sxs-lookup"><span data-stu-id="e6096-110">Get Item</span></span>

<span data-ttu-id="e6096-111">Функция Get Item возвращает определенный элемент в репозитории.</span><span class="sxs-lookup"><span data-stu-id="e6096-111">Get Item returns a specific item in the repository.</span></span>
  
|<span data-ttu-id="e6096-112">**Способов**</span><span class="sxs-lookup"><span data-stu-id="e6096-112">**Method**</span></span>|<span data-ttu-id="e6096-113">**URI запроса**</span><span class="sxs-lookup"><span data-stu-id="e6096-113">**Request URI**</span></span>|<span data-ttu-id="e6096-114">**Версия HTTP**</span><span class="sxs-lookup"><span data-stu-id="e6096-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e6096-115">Получить</span><span class="sxs-lookup"><span data-stu-id="e6096-115">GET</span></span>  <br/> |<span data-ttu-id="e6096-116">/Коерепоситорисервице/репоситори/итем/{итемид}\<портала\>HTTPS://</span><span class="sxs-lookup"><span data-stu-id="e6096-116">https://\<portal\>/QoERepositoryService/repository/item/{itemId}</span></span>  <br/> |<span data-ttu-id="e6096-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="e6096-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="e6096-118">**Параметры универсального кода ресурса** (None).</span><span class="sxs-lookup"><span data-stu-id="e6096-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="e6096-119">**Заголовки запроса** — без дополнительных заголовков.</span><span class="sxs-lookup"><span data-stu-id="e6096-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="e6096-120">**Запросить текст** -None.</span><span class="sxs-lookup"><span data-stu-id="e6096-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="e6096-121">**Response (ответ** ) — ответ включает код состояния HTTP и набор заголовков ответа.</span><span class="sxs-lookup"><span data-stu-id="e6096-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="e6096-122">**Код состояния** — успешная операция возвращает код состояния 200 (ОК).</span><span class="sxs-lookup"><span data-stu-id="e6096-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="e6096-123">Если указанный идентификатор элемента не найден, возвращается код состояния 404 (не найден).</span><span class="sxs-lookup"><span data-stu-id="e6096-123">If a specified item ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="e6096-124">**Заголовки ответа** — без дополнительных заголовков.</span><span class="sxs-lookup"><span data-stu-id="e6096-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="e6096-125">**Тело ответа** — ниже показан пример полезных данных ответа в JSON.</span><span class="sxs-lookup"><span data-stu-id="e6096-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```
{
"itemId": 1652,
"userId": 0,
"content": "{\"Title\":\"All Audio Streams\",...}",
"type": "application/json",
"subItemIds": [1653, 1710]
}
```

 <span data-ttu-id="e6096-126">*ItemId* — идентификатор элемента.</span><span class="sxs-lookup"><span data-stu-id="e6096-126">*itemId*  - ID of the item.</span></span>
  
 <span data-ttu-id="e6096-127">*UserID* -идентификатор пользователя, которому принадлежит этот элемент.</span><span class="sxs-lookup"><span data-stu-id="e6096-127">*userId*  - ID of the user who owns this item.</span></span>
  
 <span data-ttu-id="e6096-128">*Content* (содержимое) — содержимое, относящееся к приложению.</span><span class="sxs-lookup"><span data-stu-id="e6096-128">*content*  - The application-specific content.</span></span>
  
 <span data-ttu-id="e6096-129">*Type (тип* ) — тип содержимого.</span><span class="sxs-lookup"><span data-stu-id="e6096-129">*type*  - The type of the content.</span></span> <span data-ttu-id="e6096-130">Это поле задается приложениями.</span><span class="sxs-lookup"><span data-stu-id="e6096-130">This field is set by the applications.</span></span>
  
 <span data-ttu-id="e6096-131">*субитемидс* — идентификаторы дочерних элементов, если таковые имеются.</span><span class="sxs-lookup"><span data-stu-id="e6096-131">*subItemIds*  - The IDs of sub-Items, if any.</span></span> <span data-ttu-id="e6096-132">Это короткая схема операции "получить подэлементы" для сохранения звонка.</span><span class="sxs-lookup"><span data-stu-id="e6096-132">This is a short-circuit of Get Sub-Items operation to save a call.</span></span> <span data-ttu-id="e6096-133">Приложения могут также получать те же данные с помощью операции Get Sub-Items.</span><span class="sxs-lookup"><span data-stu-id="e6096-133">Applications can alternatively obtain the same information using Get Sub-Items operation.</span></span>
  

