---
title: Получение дочерних элементов
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 0542eba9-3dda-40de-bba8-095d22825e4e
description: 'Сводка: Сведения о операцию получение дочерних элементов, который является частью службы элемента. Служба элемент является частью API репозитория для панели мониторинга качества звонков. Панель мониторинга качества звонков — это средство для Скайп для Business Server 2015.'
ms.openlocfilehash: f125a10ac9d3f608216ea23d17f614d0bff88af7
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/13/2018
ms.locfileid: "26295941"
---
# <a name="get-sub-items"></a><span data-ttu-id="ecb31-105">Получение дочерних элементов</span><span class="sxs-lookup"><span data-stu-id="ecb31-105">Get Sub-Items</span></span>
 
<span data-ttu-id="ecb31-106">**Сводка:** Узнайте о операцию получение дочерних элементов, который является частью службы элемента.</span><span class="sxs-lookup"><span data-stu-id="ecb31-106">**Summary:** Learn about the Get Sub-Items operation, which is part of the Item Service.</span></span> <span data-ttu-id="ecb31-107">Служба элемент является частью API репозитория для панели мониторинга качества звонков.</span><span class="sxs-lookup"><span data-stu-id="ecb31-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="ecb31-108">Панель мониторинга качества звонков — это средство для Скайп для Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="ecb31-108">Call Quality Dashboard is a tool for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="ecb31-109">Получение дочерних элементов операции является частью службы элемента в API репозитория для панели мониторинга качества звонков.</span><span class="sxs-lookup"><span data-stu-id="ecb31-109">The Get Sub-Items operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-sub-items"></a><span data-ttu-id="ecb31-110">Получение дочерних элементов</span><span class="sxs-lookup"><span data-stu-id="ecb31-110">Get Sub-Items</span></span>

<span data-ttu-id="ecb31-111">Получите вложенные элементы возвращает конкретный элемент вложенные элементы.</span><span class="sxs-lookup"><span data-stu-id="ecb31-111">Get Sub-Items returns a specific Item's sub-items.</span></span>
  

|<span data-ttu-id="ecb31-112">**Метод**</span><span class="sxs-lookup"><span data-stu-id="ecb31-112">**Method**</span></span>|<span data-ttu-id="ecb31-113">**URI запроса**</span><span class="sxs-lookup"><span data-stu-id="ecb31-113">**Request URI**</span></span>|<span data-ttu-id="ecb31-114">**Версия HTTP**</span><span class="sxs-lookup"><span data-stu-id="ecb31-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ecb31-115">Получить</span><span class="sxs-lookup"><span data-stu-id="ecb31-115">GET</span></span>  <br/> |<span data-ttu-id="ecb31-116">https://\<портала\>/QoERepositoryService/репозитория/элемент / {itemId} / subitem</span><span class="sxs-lookup"><span data-stu-id="ecb31-116">https://\<portal\>/QoERepositoryService/repository/item/{itemId}/subitem</span></span>  <br/> |<span data-ttu-id="ecb31-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="ecb31-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="ecb31-118">**Параметры URI** — нет.</span><span class="sxs-lookup"><span data-stu-id="ecb31-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="ecb31-119">**Заголовки запроса** — без дополнительных заголовков.</span><span class="sxs-lookup"><span data-stu-id="ecb31-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="ecb31-120">**Текст запроса** — нет.</span><span class="sxs-lookup"><span data-stu-id="ecb31-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="ecb31-121">**Ответа** - ответ включает код состояния HTTP и набор заголовков ответов.</span><span class="sxs-lookup"><span data-stu-id="ecb31-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="ecb31-122">**Код состояния** - успешные операции возвращает код состояния 200 (ОК).</span><span class="sxs-lookup"><span data-stu-id="ecb31-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="ecb31-123">Если указанный пользователь с Идентификатором не найден, он возвращает код состояния 404 (не найден).</span><span class="sxs-lookup"><span data-stu-id="ecb31-123">If a specified user ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="ecb31-124">**Заголовки ответа** — без дополнительных заголовков.</span><span class="sxs-lookup"><span data-stu-id="ecb31-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="ecb31-125">**Тело ответа** - ниже приведен пример полезные данные ответа в формате JSON в.</span><span class="sxs-lookup"><span data-stu-id="ecb31-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ecb31-126">Возвращает массив объектов элемента.</span><span class="sxs-lookup"><span data-stu-id="ecb31-126">An array of Item object is returned.</span></span> 
  
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

<span data-ttu-id="ecb31-127">Объект Item, возвращенные операцией вложенные элементы содержит только следующие три поля.</span><span class="sxs-lookup"><span data-stu-id="ecb31-127">The Item object returned by Sub-Items operation only contains the following three fields.</span></span> 
  
 <span data-ttu-id="ecb31-128">*идентификатор элемента* - идентификатор элемента.</span><span class="sxs-lookup"><span data-stu-id="ecb31-128">*itemId*  - ID of the item.</span></span>
  
 <span data-ttu-id="ecb31-129">*идентификатор пользователя* — идентификатор пользователя, которому принадлежит этот элемент.</span><span class="sxs-lookup"><span data-stu-id="ecb31-129">*userId*  - ID of the User who owns this Item.</span></span>
  
 <span data-ttu-id="ecb31-130">*Тип* — тип контента.</span><span class="sxs-lookup"><span data-stu-id="ecb31-130">*type*  - The type of the content.</span></span> <span data-ttu-id="ecb31-131">В этом поле задается с помощью приложений.</span><span class="sxs-lookup"><span data-stu-id="ecb31-131">This field is set by the applications.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="ecb31-132">`Content`и `subItems` не включены в ответ для сокращения объема данных, передаваемых по сети.</span><span class="sxs-lookup"><span data-stu-id="ecb31-132">`Content` and `subItems` fields are not included in the response to reduce the amount of data transmitted over the network.</span></span>
  

