---
title: Получение вложенных элементов
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 0542eba9-3dda-40de-bba8-095d22825e4e
description: 'Сводка: сведения о операции "получить подэлементы", которая входит в состав службы номенклатур. Служба item входит в API репозитория для панели мониторинга качества звонков. Панель мониторинга качества звонков — это средство для Skype для бизнеса Server.'
ms.openlocfilehash: 75fc4fcd331925c224d8dfb72c681d25e3485eb6
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992656"
---
# <a name="get-sub-items"></a><span data-ttu-id="cb50e-105">Получение вложенных элементов</span><span class="sxs-lookup"><span data-stu-id="cb50e-105">Get Sub-Items</span></span>
 
<span data-ttu-id="cb50e-106">**Сводка:** Сведения о операции "получить подэлементы", которая входит в состав службы номенклатур.</span><span class="sxs-lookup"><span data-stu-id="cb50e-106">**Summary:** Learn about the Get Sub-Items operation, which is part of the Item Service.</span></span> <span data-ttu-id="cb50e-107">Служба item входит в API репозитория для панели мониторинга качества звонков.</span><span class="sxs-lookup"><span data-stu-id="cb50e-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="cb50e-108">Панель мониторинга качества звонков — это средство для Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="cb50e-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="cb50e-109">Операция Get Sub-Items является частью службы элементов в API репозитория для панели мониторинга качества звонков.</span><span class="sxs-lookup"><span data-stu-id="cb50e-109">The Get Sub-Items operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-sub-items"></a><span data-ttu-id="cb50e-110">Получение вложенных элементов</span><span class="sxs-lookup"><span data-stu-id="cb50e-110">Get Sub-Items</span></span>

<span data-ttu-id="cb50e-111">Функция "получить вложенные элементы" Возвращает вложенные элементы определенного элемента.</span><span class="sxs-lookup"><span data-stu-id="cb50e-111">Get Sub-Items returns a specific Item's sub-items.</span></span>
  

|<span data-ttu-id="cb50e-112">**Способов**</span><span class="sxs-lookup"><span data-stu-id="cb50e-112">**Method**</span></span>|<span data-ttu-id="cb50e-113">**URI запроса**</span><span class="sxs-lookup"><span data-stu-id="cb50e-113">**Request URI**</span></span>|<span data-ttu-id="cb50e-114">**Версия HTTP**</span><span class="sxs-lookup"><span data-stu-id="cb50e-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="cb50e-115">Получить</span><span class="sxs-lookup"><span data-stu-id="cb50e-115">GET</span></span>  <br/> |<span data-ttu-id="cb50e-116">/Коерепоситорисервице/репоситори/итем/{итемид}/субитем\<портала\>HTTPS://</span><span class="sxs-lookup"><span data-stu-id="cb50e-116">https://\<portal\>/QoERepositoryService/repository/item/{itemId}/subitem</span></span>  <br/> |<span data-ttu-id="cb50e-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="cb50e-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="cb50e-118">**Параметры универсального кода ресурса** (None).</span><span class="sxs-lookup"><span data-stu-id="cb50e-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="cb50e-119">**Заголовки запроса** — без дополнительных заголовков.</span><span class="sxs-lookup"><span data-stu-id="cb50e-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="cb50e-120">**Запросить текст** -None.</span><span class="sxs-lookup"><span data-stu-id="cb50e-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="cb50e-121">**Response (ответ** ) — ответ включает код состояния HTTP и набор заголовков ответа.</span><span class="sxs-lookup"><span data-stu-id="cb50e-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="cb50e-122">**Код состояния** — успешная операция возвращает код состояния 200 (ОК).</span><span class="sxs-lookup"><span data-stu-id="cb50e-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="cb50e-123">Если указанный идентификатор пользователя не найден, он возвращает код состояния 404 (не найден).</span><span class="sxs-lookup"><span data-stu-id="cb50e-123">If a specified user ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="cb50e-124">**Заголовки ответа** — без дополнительных заголовков.</span><span class="sxs-lookup"><span data-stu-id="cb50e-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="cb50e-125">**Тело ответа** — ниже показан пример полезных данных ответа в JSON.</span><span class="sxs-lookup"><span data-stu-id="cb50e-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="cb50e-126">Возвращается массив объектов Item.</span><span class="sxs-lookup"><span data-stu-id="cb50e-126">An array of Item object is returned.</span></span> 
  
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

<span data-ttu-id="cb50e-127">Объект Item, возвращаемый операцией дочернего элемента, состоит только из трех указанных ниже полей.</span><span class="sxs-lookup"><span data-stu-id="cb50e-127">The Item object returned by Sub-Items operation only contains the following three fields.</span></span> 
  
 <span data-ttu-id="cb50e-128">*ItemId* — идентификатор элемента.</span><span class="sxs-lookup"><span data-stu-id="cb50e-128">*itemId*  - ID of the item.</span></span>
  
 <span data-ttu-id="cb50e-129">*UserID* -идентификатор пользователя, которому принадлежит этот элемент.</span><span class="sxs-lookup"><span data-stu-id="cb50e-129">*userId*  - ID of the User who owns this Item.</span></span>
  
 <span data-ttu-id="cb50e-130">*Type (тип* ) — тип содержимого.</span><span class="sxs-lookup"><span data-stu-id="cb50e-130">*type*  - The type of the content.</span></span> <span data-ttu-id="cb50e-131">Это поле задается приложениями.</span><span class="sxs-lookup"><span data-stu-id="cb50e-131">This field is set by the applications.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="cb50e-132">`Content`и `subItems` поля не включаются в ответ, чтобы уменьшить объем данных, передаваемых по сети.</span><span class="sxs-lookup"><span data-stu-id="cb50e-132">`Content` and `subItems` fields are not included in the response to reduce the amount of data transmitted over the network.</span></span>
  

