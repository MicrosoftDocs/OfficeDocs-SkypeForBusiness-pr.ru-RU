---
title: Получение вложенных элементов
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 0542eba9-3dda-40de-bba8-095d22825e4e
description: 'Сводка: сведения о операции "получить подэлементы", которая входит в состав службы номенклатур. Служба item входит в API репозитория для панели мониторинга качества звонков. Панель мониторинга качества звонков — это средство для Skype для бизнеса Server.'
ms.openlocfilehash: 523a6050065680550685337dabfec72c87f30bf7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816768"
---
# <a name="get-sub-items"></a><span data-ttu-id="cd386-105">Получение вложенных элементов</span><span class="sxs-lookup"><span data-stu-id="cd386-105">Get Sub-Items</span></span>
 
<span data-ttu-id="cd386-106">**Сводка:** Сведения о операции "получить подэлементы", которая входит в состав службы номенклатур.</span><span class="sxs-lookup"><span data-stu-id="cd386-106">**Summary:** Learn about the Get Sub-Items operation, which is part of the Item Service.</span></span> <span data-ttu-id="cd386-107">Служба item входит в API репозитория для панели мониторинга качества звонков.</span><span class="sxs-lookup"><span data-stu-id="cd386-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="cd386-108">Панель мониторинга качества звонков — это средство для Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="cd386-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="cd386-109">Операция Get Sub-Items является частью службы элементов в API репозитория для панели мониторинга качества звонков.</span><span class="sxs-lookup"><span data-stu-id="cd386-109">The Get Sub-Items operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-sub-items"></a><span data-ttu-id="cd386-110">Получение вложенных элементов</span><span class="sxs-lookup"><span data-stu-id="cd386-110">Get Sub-Items</span></span>

<span data-ttu-id="cd386-111">Функция "получить вложенные элементы" Возвращает вложенные элементы определенного элемента.</span><span class="sxs-lookup"><span data-stu-id="cd386-111">Get Sub-Items returns a specific Item's sub-items.</span></span>
  

|<span data-ttu-id="cd386-112">**Способов**</span><span class="sxs-lookup"><span data-stu-id="cd386-112">**Method**</span></span>|<span data-ttu-id="cd386-113">**URI запроса**</span><span class="sxs-lookup"><span data-stu-id="cd386-113">**Request URI**</span></span>|<span data-ttu-id="cd386-114">**Версия HTTP**</span><span class="sxs-lookup"><span data-stu-id="cd386-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="cd386-115">Получить</span><span class="sxs-lookup"><span data-stu-id="cd386-115">GET</span></span>  <br/> |<span data-ttu-id="cd386-116">/Коерепоситорисервице/репоситори/итем/{итемид}/субитем\<портала\>HTTPS://</span><span class="sxs-lookup"><span data-stu-id="cd386-116">https://\<portal\>/QoERepositoryService/repository/item/{itemId}/subitem</span></span>  <br/> |<span data-ttu-id="cd386-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="cd386-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="cd386-118">**Параметры универсального кода ресурса** (None).</span><span class="sxs-lookup"><span data-stu-id="cd386-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="cd386-119">**Заголовки запроса** — без дополнительных заголовков.</span><span class="sxs-lookup"><span data-stu-id="cd386-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="cd386-120">**Запросить текст** -None.</span><span class="sxs-lookup"><span data-stu-id="cd386-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="cd386-121">**Response (ответ** ) — ответ включает код состояния HTTP и набор заголовков ответа.</span><span class="sxs-lookup"><span data-stu-id="cd386-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="cd386-122">**Код состояния** — успешная операция возвращает код состояния 200 (ОК).</span><span class="sxs-lookup"><span data-stu-id="cd386-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="cd386-123">Если указанный идентификатор пользователя не найден, он возвращает код состояния 404 (не найден).</span><span class="sxs-lookup"><span data-stu-id="cd386-123">If a specified user ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="cd386-124">**Заголовки ответа** — без дополнительных заголовков.</span><span class="sxs-lookup"><span data-stu-id="cd386-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="cd386-125">**Тело ответа** — ниже показан пример полезных данных ответа в JSON.</span><span class="sxs-lookup"><span data-stu-id="cd386-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="cd386-126">Возвращается массив объектов Item.</span><span class="sxs-lookup"><span data-stu-id="cd386-126">An array of Item object is returned.</span></span> 
  
```json
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

<span data-ttu-id="cd386-127">Объект Item, возвращаемый операцией дочернего элемента, состоит только из трех указанных ниже полей.</span><span class="sxs-lookup"><span data-stu-id="cd386-127">The Item object returned by Sub-Items operation only contains the following three fields.</span></span> 
  
 <span data-ttu-id="cd386-128">*ItemId* — идентификатор элемента.</span><span class="sxs-lookup"><span data-stu-id="cd386-128">*itemId*  - ID of the item.</span></span>
  
 <span data-ttu-id="cd386-129">*UserID* -идентификатор пользователя, которому принадлежит этот элемент.</span><span class="sxs-lookup"><span data-stu-id="cd386-129">*userId*  - ID of the User who owns this Item.</span></span>
  
 <span data-ttu-id="cd386-130">*Type (тип* ) — тип содержимого.</span><span class="sxs-lookup"><span data-stu-id="cd386-130">*type*  - The type of the content.</span></span> <span data-ttu-id="cd386-131">Это поле задается приложениями.</span><span class="sxs-lookup"><span data-stu-id="cd386-131">This field is set by the applications.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="cd386-132">`Content`и `subItems` поля не включаются в ответ, чтобы уменьшить объем данных, передаваемых по сети.</span><span class="sxs-lookup"><span data-stu-id="cd386-132">`Content` and `subItems` fields are not included in the response to reduce the amount of data transmitted over the network.</span></span>
  

