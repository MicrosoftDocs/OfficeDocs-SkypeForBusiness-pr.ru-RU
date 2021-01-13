---
title: Получение вложенных элементов
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
ms.assetid: 0542eba9-3dda-40de-bba8-095d22825e4e
description: Сводка. Сведения об операции get Sub-Items, которая входит в состав службы элементов. Служба элементов является частью API репозитория для панели мониторинга качества вызовов. Панель мониторинга качества звонков — это инструмент для Skype для бизнеса Server.
ms.openlocfilehash: defb0b898c5101513cbb4f6da4382a8bb43bce6e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832509"
---
# <a name="get-sub-items"></a><span data-ttu-id="0685e-105">Получение вложенных элементов</span><span class="sxs-lookup"><span data-stu-id="0685e-105">Get Sub-Items</span></span>
 
<span data-ttu-id="0685e-106">**Сводка:** Узнайте об операции Get Sub-Items, которая входит в состав службы элементов.</span><span class="sxs-lookup"><span data-stu-id="0685e-106">**Summary:** Learn about the Get Sub-Items operation, which is part of the Item Service.</span></span> <span data-ttu-id="0685e-107">Служба элементов является частью API репозитория для панели мониторинга качества вызовов.</span><span class="sxs-lookup"><span data-stu-id="0685e-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="0685e-108">Панель мониторинга качества звонков — это инструмент для Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="0685e-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="0685e-109">Операция Get Sub-Items является частью службы элементов в API репозитория для панели мониторинга качества вызовов.</span><span class="sxs-lookup"><span data-stu-id="0685e-109">The Get Sub-Items operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-sub-items"></a><span data-ttu-id="0685e-110">Получение вложенных элементов</span><span class="sxs-lookup"><span data-stu-id="0685e-110">Get Sub-Items</span></span>

<span data-ttu-id="0685e-111">При Sub-Items возвращается подустанавли определенного элемента.</span><span class="sxs-lookup"><span data-stu-id="0685e-111">Get Sub-Items returns a specific Item's sub-items.</span></span>
  

|<span data-ttu-id="0685e-112">**Способ**</span><span class="sxs-lookup"><span data-stu-id="0685e-112">**Method**</span></span>|<span data-ttu-id="0685e-113">**URI запроса**</span><span class="sxs-lookup"><span data-stu-id="0685e-113">**Request URI**</span></span>|<span data-ttu-id="0685e-114">**Версия HTTP**</span><span class="sxs-lookup"><span data-stu-id="0685e-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0685e-115">GET</span><span class="sxs-lookup"><span data-stu-id="0685e-115">GET</span></span>  <br/> |<span data-ttu-id="0685e-116">https:// \<portal\> /QoERepositoryService/repository/item/{itemId}/subitem</span><span class="sxs-lookup"><span data-stu-id="0685e-116">https://\<portal\>/QoERepositoryService/repository/item/{itemId}/subitem</span></span>  <br/> |<span data-ttu-id="0685e-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="0685e-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="0685e-118">**Параметры URI** — нет.</span><span class="sxs-lookup"><span data-stu-id="0685e-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="0685e-119">**Request Headers** - No additional headers.</span><span class="sxs-lookup"><span data-stu-id="0685e-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="0685e-120">**Тело запроса** — нет.</span><span class="sxs-lookup"><span data-stu-id="0685e-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="0685e-121">**Ответ.** Ответ включает код состояния HTTP и набор загодеров отклика.</span><span class="sxs-lookup"><span data-stu-id="0685e-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="0685e-122">**Код состояния** — успешная операция возвращает код состояния 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="0685e-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="0685e-123">Если указанный код пользователя не найден, возвращается код состояния 404 (не найден).</span><span class="sxs-lookup"><span data-stu-id="0685e-123">If a specified user ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="0685e-124">**Response Headers** - No additional headers.</span><span class="sxs-lookup"><span data-stu-id="0685e-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="0685e-125">**Тело ответа.** Ниже приведен пример полезной нагрузки ответа в JSON.</span><span class="sxs-lookup"><span data-stu-id="0685e-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0685e-126">Возвращается массив объекта Item.</span><span class="sxs-lookup"><span data-stu-id="0685e-126">An array of Item object is returned.</span></span> 
  
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

<span data-ttu-id="0685e-127">Объект Item, возвращенный Sub-Items, содержит только следующие три поля.</span><span class="sxs-lookup"><span data-stu-id="0685e-127">The Item object returned by Sub-Items operation only contains the following three fields.</span></span> 
  
 <span data-ttu-id="0685e-128">*itemId*  — ИД элемента.</span><span class="sxs-lookup"><span data-stu-id="0685e-128">*itemId*  - ID of the item.</span></span>
  
 <span data-ttu-id="0685e-129">*userId*  — ИД пользователя, которому принадлежит этот элемент.</span><span class="sxs-lookup"><span data-stu-id="0685e-129">*userId*  - ID of the User who owns this Item.</span></span>
  
 <span data-ttu-id="0685e-130">*type*  — тип контента.</span><span class="sxs-lookup"><span data-stu-id="0685e-130">*type*  - The type of the content.</span></span> <span data-ttu-id="0685e-131">Это поле устанавливается приложениями.</span><span class="sxs-lookup"><span data-stu-id="0685e-131">This field is set by the applications.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="0685e-132">`Content` поля не включаются в ответ, чтобы уменьшить объем данных, передаваемых `subItems` по сети.</span><span class="sxs-lookup"><span data-stu-id="0685e-132">`Content` and `subItems` fields are not included in the response to reduce the amount of data transmitted over the network.</span></span>
  

