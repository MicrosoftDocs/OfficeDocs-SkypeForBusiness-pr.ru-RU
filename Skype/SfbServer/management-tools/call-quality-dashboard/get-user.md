---
title: Получение пользователя
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
ms.assetid: 52b89a4b-a0bd-493d-bb5e-e21904eb8e48
description: Сводка. Сведения об операции "Получить пользователя", которая входит в состав службы пользователей. Служба пользователей является частью API репозитория для панели мониторинга качества вызовов. Панель мониторинга качества звонков — это инструмент для Skype для бизнеса Server.
ms.openlocfilehash: dd2bb5e46ddbe3e65faf441a11e39cbc5429e473
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832419"
---
# <a name="get-user"></a><span data-ttu-id="9e3cd-105">Получение пользователя</span><span class="sxs-lookup"><span data-stu-id="9e3cd-105">Get User</span></span>
 
<span data-ttu-id="9e3cd-106">**Сводка:** Узнайте об операции "Получить пользователя", которая входит в состав службы пользователей.</span><span class="sxs-lookup"><span data-stu-id="9e3cd-106">**Summary:** Learn about the Get User operation, which is part of the User Service.</span></span> <span data-ttu-id="9e3cd-107">Служба пользователей является частью API репозитория для панели мониторинга качества вызовов.</span><span class="sxs-lookup"><span data-stu-id="9e3cd-107">The User Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="9e3cd-108">Панель мониторинга качества звонков — это инструмент для Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="9e3cd-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="9e3cd-109">Операция "Получить пользователей" является частью службы пользователей в API репозитория для панели мониторинга качества вызовов.</span><span class="sxs-lookup"><span data-stu-id="9e3cd-109">The Get Users operation is part of the User Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-user"></a><span data-ttu-id="9e3cd-110">Получение пользователя</span><span class="sxs-lookup"><span data-stu-id="9e3cd-110">Get User</span></span>

<span data-ttu-id="9e3cd-111">Get User returns a user record from the repository.</span><span class="sxs-lookup"><span data-stu-id="9e3cd-111">Get User returns a user record from the repository.</span></span>
  
|<span data-ttu-id="9e3cd-112">**Способ**</span><span class="sxs-lookup"><span data-stu-id="9e3cd-112">**Method**</span></span>|<span data-ttu-id="9e3cd-113">**URI запроса**</span><span class="sxs-lookup"><span data-stu-id="9e3cd-113">**Request URI**</span></span>|<span data-ttu-id="9e3cd-114">**Версия HTTP**</span><span class="sxs-lookup"><span data-stu-id="9e3cd-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="9e3cd-115">GET</span><span class="sxs-lookup"><span data-stu-id="9e3cd-115">GET</span></span>  <br/> |<span data-ttu-id="9e3cd-116">https:// \<portal\> /QoERepositoryService/repository/user/{userId}</span><span class="sxs-lookup"><span data-stu-id="9e3cd-116">https://\<portal\>/QoERepositoryService/repository/user/{userId}</span></span>  <br/> |<span data-ttu-id="9e3cd-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="9e3cd-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="9e3cd-118">**Параметры URI** — нет.</span><span class="sxs-lookup"><span data-stu-id="9e3cd-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="9e3cd-119">**Request Headers** - No additional headers.</span><span class="sxs-lookup"><span data-stu-id="9e3cd-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="9e3cd-120">**Тело запроса** — нет.</span><span class="sxs-lookup"><span data-stu-id="9e3cd-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="9e3cd-121">**Ответ.** Ответ включает код состояния HTTP и набор загодеров отклика.</span><span class="sxs-lookup"><span data-stu-id="9e3cd-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="9e3cd-122">**Код состояния** : успешная операция возвращает код состояния 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="9e3cd-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="9e3cd-123">Если указанный код пользователя не найден, возвращается код состояния 404 (не найден).</span><span class="sxs-lookup"><span data-stu-id="9e3cd-123">If a specified user ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="9e3cd-124">**Response Headers** - No additional headers.</span><span class="sxs-lookup"><span data-stu-id="9e3cd-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="9e3cd-125">**Тело ответа.** Ниже приведен пример полезной нагрузки ответа в JSON.</span><span class="sxs-lookup"><span data-stu-id="9e3cd-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```json
{
"userId": 0,
"loginName": "system",
"defaultItemId": 1655
}
```

 <span data-ttu-id="9e3cd-126">*userId*  — ИД пользователя.</span><span class="sxs-lookup"><span data-stu-id="9e3cd-126">*userId*  - ID of the user.</span></span>
  
 <span data-ttu-id="9e3cd-127">*loginName*  — идентификация внешних пользователей для обычных пользователей.</span><span class="sxs-lookup"><span data-stu-id="9e3cd-127">*loginName*  - External user identification for regular users.</span></span> <span data-ttu-id="9e3cd-128">Если для проверки подлинности пользователей используется проверка подлинности Windows, это может быть FQDN пользователя.</span><span class="sxs-lookup"><span data-stu-id="9e3cd-128">If Windows Authentication is used for authenticating users, then this may be a FQDN of the user.</span></span>
  
 <span data-ttu-id="9e3cd-129">*defaultItemId*  — ИД элемента по умолчанию для этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="9e3cd-129">*defaultItemId*  - ID of the default Item for this user.</span></span> <span data-ttu-id="9e3cd-130">Элемент по умолчанию — это самый верхний элемент, связанный с пользователем.</span><span class="sxs-lookup"><span data-stu-id="9e3cd-130">The default Item is the top-most Item that is associated to the user.</span></span> <span data-ttu-id="9e3cd-131">Все остальные элементы, которые принадлежат этому пользователю, можно перемещать из элемента по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="9e3cd-131">All other Items this user owns can be navigated from the default Item.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9e3cd-132">`defaultItemId`Укавите значение операции "Получить элемент", чтобы получить сведения об элементе по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="9e3cd-132">Supply the  `defaultItemId` value to Get Item operation to retrieve the details of the default Item.</span></span>
  

