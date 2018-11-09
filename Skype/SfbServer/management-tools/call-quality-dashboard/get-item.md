---
title: Получение элемента
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: e77bf649-d62a-4d94-80de-066ba47730cd
description: 'Сводка: Сведения о операцию получения элемента, который является частью службы элемента. Служба элемент является частью API репозитория для панели мониторинга качества звонков. Панель мониторинга качества звонков — это средство для Скайп для Business Server.'
ms.openlocfilehash: 12b52bdd51e8ba59f1aa90e2a366b3e11fb54805
ms.sourcegitcommit: b680505c5dad435d98fbd0b235e0e7c67b9d8c9c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2018
ms.locfileid: "26035585"
---
# <a name="get-item"></a><span data-ttu-id="a50e1-105">Получение элемента</span><span class="sxs-lookup"><span data-stu-id="a50e1-105">Get Item</span></span>
 
<span data-ttu-id="a50e1-106">**Сводка:** Узнайте о операцию получения элемента, который является частью службы элемента.</span><span class="sxs-lookup"><span data-stu-id="a50e1-106">**Summary:** Learn about the Get Item operation, which is part of the Item Service.</span></span> <span data-ttu-id="a50e1-107">Служба элемент является частью API репозитория для панели мониторинга качества звонков.</span><span class="sxs-lookup"><span data-stu-id="a50e1-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="a50e1-108">Панель мониторинга качества звонков — это средство для Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="a50e1-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="a50e1-109">Операции получения элемента является частью службы элемента в API репозитория для панели мониторинга качества звонков.</span><span class="sxs-lookup"><span data-stu-id="a50e1-109">The Get Item operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-item"></a><span data-ttu-id="a50e1-110">Получение элемента</span><span class="sxs-lookup"><span data-stu-id="a50e1-110">Get Item</span></span>

<span data-ttu-id="a50e1-111">Получение элемента возвращает конкретный элемент в репозитории.</span><span class="sxs-lookup"><span data-stu-id="a50e1-111">Get Item returns a specific item in the repository.</span></span>
  
|<span data-ttu-id="a50e1-112">**Метод**</span><span class="sxs-lookup"><span data-stu-id="a50e1-112">**Method**</span></span>|<span data-ttu-id="a50e1-113">**URI запроса**</span><span class="sxs-lookup"><span data-stu-id="a50e1-113">**Request URI**</span></span>|<span data-ttu-id="a50e1-114">**Версия HTTP**</span><span class="sxs-lookup"><span data-stu-id="a50e1-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a50e1-115">Получить</span><span class="sxs-lookup"><span data-stu-id="a50e1-115">GET</span></span>  <br/> |<span data-ttu-id="a50e1-116">https://\<портала\>/QoERepositoryService/репозитория/элемент / {itemId}</span><span class="sxs-lookup"><span data-stu-id="a50e1-116">https://\<portal\>/QoERepositoryService/repository/item/{itemId}</span></span>  <br/> |<span data-ttu-id="a50e1-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="a50e1-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="a50e1-118">**Параметры URI** — нет.</span><span class="sxs-lookup"><span data-stu-id="a50e1-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="a50e1-119">**Заголовки запроса** — без дополнительных заголовков.</span><span class="sxs-lookup"><span data-stu-id="a50e1-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="a50e1-120">**Текст запроса** — нет.</span><span class="sxs-lookup"><span data-stu-id="a50e1-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="a50e1-121">**Ответа** - ответ включает код состояния HTTP и набор заголовков ответов.</span><span class="sxs-lookup"><span data-stu-id="a50e1-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="a50e1-122">**Код состояния** - успешные операции возвращает код состояния 200 (ОК).</span><span class="sxs-lookup"><span data-stu-id="a50e1-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="a50e1-123">Если элемент с указанным Идентификатором не найден, возвращает код состояния 404 (не найден).</span><span class="sxs-lookup"><span data-stu-id="a50e1-123">If a specified item ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="a50e1-124">**Заголовки ответа** — без дополнительных заголовков.</span><span class="sxs-lookup"><span data-stu-id="a50e1-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="a50e1-125">**Тело ответа** - ниже приведен пример полезные данные ответа в формате JSON в.</span><span class="sxs-lookup"><span data-stu-id="a50e1-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```
{
"itemId": 1652,
"userId": 0,
"content": "{\"Title\":\"All Audio Streams\",...}",
"type": "application/json",
"subItemIds": [1653, 1710]
}
```

 <span data-ttu-id="a50e1-126">*идентификатор элемента* - идентификатор элемента.</span><span class="sxs-lookup"><span data-stu-id="a50e1-126">*itemId*  - ID of the item.</span></span>
  
 <span data-ttu-id="a50e1-127">*идентификатор пользователя* — идентификатор пользователя, которому принадлежит этот элемент.</span><span class="sxs-lookup"><span data-stu-id="a50e1-127">*userId*  - ID of the user who owns this item.</span></span>
  
 <span data-ttu-id="a50e1-128">*контент* - содержимого конкретного приложения.</span><span class="sxs-lookup"><span data-stu-id="a50e1-128">*content*  - The application-specific content.</span></span>
  
 <span data-ttu-id="a50e1-129">*Тип* — тип контента.</span><span class="sxs-lookup"><span data-stu-id="a50e1-129">*type*  - The type of the content.</span></span> <span data-ttu-id="a50e1-130">В этом поле задается с помощью приложений.</span><span class="sxs-lookup"><span data-stu-id="a50e1-130">This field is set by the applications.</span></span>
  
 <span data-ttu-id="a50e1-131">*subItemIds* - идентификаторы вложенные элементы, при их наличии.</span><span class="sxs-lookup"><span data-stu-id="a50e1-131">*subItemIds*  - The IDs of sub-Items, if any.</span></span> <span data-ttu-id="a50e1-132">Это short-circuit операции получение дочерних элементов для сохранения звонка.</span><span class="sxs-lookup"><span data-stu-id="a50e1-132">This is a short-circuit of Get Sub-Items operation to save a call.</span></span> <span data-ttu-id="a50e1-133">Приложения также могут получать те же данные, с помощью операции получение дочерних элементов.</span><span class="sxs-lookup"><span data-stu-id="a50e1-133">Applications can alternatively obtain the same information using Get Sub-Items operation.</span></span>
  

