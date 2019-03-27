---
title: Получение вложенных элементов
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 0542eba9-3dda-40de-bba8-095d22825e4e
description: 'Сводка: Сведения о операцию получение дочерних элементов, который является частью службы элемента. Служба элемент является частью API репозитория для панели мониторинга качества звонков. Панель мониторинга качества звонков — это средство для Скайп для Business Server.'
ms.openlocfilehash: 41287978338bce49d8d8c30d1d6b91b9b2498acc
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30889009"
---
# <a name="get-sub-items"></a><span data-ttu-id="5a1dd-105">Получение вложенных элементов</span><span class="sxs-lookup"><span data-stu-id="5a1dd-105">Get Sub-Items</span></span>
 
<span data-ttu-id="5a1dd-106">**Сводка:** Узнайте о операцию получение дочерних элементов, который является частью службы элемента.</span><span class="sxs-lookup"><span data-stu-id="5a1dd-106">**Summary:** Learn about the Get Sub-Items operation, which is part of the Item Service.</span></span> <span data-ttu-id="5a1dd-107">Служба элемент является частью API репозитория для панели мониторинга качества звонков.</span><span class="sxs-lookup"><span data-stu-id="5a1dd-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="5a1dd-108">Панель мониторинга качества звонков — это средство для Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="5a1dd-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="5a1dd-109">Получение дочерних элементов операции является частью службы элемента в API репозитория для панели мониторинга качества звонков.</span><span class="sxs-lookup"><span data-stu-id="5a1dd-109">The Get Sub-Items operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-sub-items"></a><span data-ttu-id="5a1dd-110">Получение вложенных элементов</span><span class="sxs-lookup"><span data-stu-id="5a1dd-110">Get Sub-Items</span></span>

<span data-ttu-id="5a1dd-111">Получите вложенные элементы возвращает конкретный элемент вложенные элементы.</span><span class="sxs-lookup"><span data-stu-id="5a1dd-111">Get Sub-Items returns a specific Item's sub-items.</span></span>
  

|<span data-ttu-id="5a1dd-112">**Метод**</span><span class="sxs-lookup"><span data-stu-id="5a1dd-112">**Method**</span></span>|<span data-ttu-id="5a1dd-113">**URI запроса**</span><span class="sxs-lookup"><span data-stu-id="5a1dd-113">**Request URI**</span></span>|<span data-ttu-id="5a1dd-114">**Версия HTTP**</span><span class="sxs-lookup"><span data-stu-id="5a1dd-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="5a1dd-115">Получить</span><span class="sxs-lookup"><span data-stu-id="5a1dd-115">GET</span></span>  <br/> |<span data-ttu-id="5a1dd-116">https://\<портала\>/QoERepositoryService/репозитория/элемент / {itemId} / subitem</span><span class="sxs-lookup"><span data-stu-id="5a1dd-116">https://\<portal\>/QoERepositoryService/repository/item/{itemId}/subitem</span></span>  <br/> |<span data-ttu-id="5a1dd-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="5a1dd-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="5a1dd-118">**Параметры URI** — нет.</span><span class="sxs-lookup"><span data-stu-id="5a1dd-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="5a1dd-119">**Заголовки запроса** — без дополнительных заголовков.</span><span class="sxs-lookup"><span data-stu-id="5a1dd-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="5a1dd-120">**Текст запроса** — нет.</span><span class="sxs-lookup"><span data-stu-id="5a1dd-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="5a1dd-121">**Ответа** - ответ включает код состояния HTTP и набор заголовков ответов.</span><span class="sxs-lookup"><span data-stu-id="5a1dd-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="5a1dd-122">**Код состояния** - успешные операции возвращает код состояния 200 (ОК).</span><span class="sxs-lookup"><span data-stu-id="5a1dd-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="5a1dd-123">Если указанный пользователь с Идентификатором не найден, он возвращает код состояния 404 (не найден).</span><span class="sxs-lookup"><span data-stu-id="5a1dd-123">If a specified user ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="5a1dd-124">**Заголовки ответа** — без дополнительных заголовков.</span><span class="sxs-lookup"><span data-stu-id="5a1dd-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="5a1dd-125">**Тело ответа** - ниже приведен пример полезные данные ответа в формате JSON в.</span><span class="sxs-lookup"><span data-stu-id="5a1dd-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5a1dd-126">Возвращает массив объектов элемента.</span><span class="sxs-lookup"><span data-stu-id="5a1dd-126">An array of Item object is returned.</span></span> 
  
```
[{
"itemId": 1653,
"userId": 0,
"type": "application/json"
},
{
"itemId": 1710,
"userId": 0,
"type": "json"
}]
```

<span data-ttu-id="5a1dd-127">Объект Item, возвращенные операцией вложенные элементы содержит только следующие три поля.</span><span class="sxs-lookup"><span data-stu-id="5a1dd-127">The Item object returned by Sub-Items operation only contains the following three fields.</span></span> 
  
 <span data-ttu-id="5a1dd-128">*идентификатор элемента* - идентификатор элемента.</span><span class="sxs-lookup"><span data-stu-id="5a1dd-128">*itemId*  - ID of the item.</span></span>
  
 <span data-ttu-id="5a1dd-129">*идентификатор пользователя* — идентификатор пользователя, которому принадлежит этот элемент.</span><span class="sxs-lookup"><span data-stu-id="5a1dd-129">*userId*  - ID of the User who owns this Item.</span></span>
  
 <span data-ttu-id="5a1dd-130">*Тип* — тип контента.</span><span class="sxs-lookup"><span data-stu-id="5a1dd-130">*type*  - The type of the content.</span></span> <span data-ttu-id="5a1dd-131">В этом поле задается с помощью приложений.</span><span class="sxs-lookup"><span data-stu-id="5a1dd-131">This field is set by the applications.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="5a1dd-132">`Content`и `subItems` не включены в ответ для сокращения объема данных, передаваемых по сети.</span><span class="sxs-lookup"><span data-stu-id="5a1dd-132">`Content` and `subItems` fields are not included in the response to reduce the amount of data transmitted over the network.</span></span>
  

