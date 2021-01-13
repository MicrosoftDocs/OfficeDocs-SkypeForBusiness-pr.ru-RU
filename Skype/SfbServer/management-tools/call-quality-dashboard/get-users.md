---
title: Получение пользователей
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
ms.assetid: 87d34baf-4c31-468d-b8f7-4faca0bc7a54
description: Сводка. Сведения об операции "Получить пользователей", которая входит в состав службы пользователей. Служба пользователей является частью API репозитория для панели мониторинга качества вызовов. Панель мониторинга качества звонков — это инструмент для Skype для бизнеса Server.
ms.openlocfilehash: a830663fc97d8fda727d1ebb008d97407796cc7c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832429"
---
# <a name="get-users"></a><span data-ttu-id="0bac5-105">Получение пользователей</span><span class="sxs-lookup"><span data-stu-id="0bac5-105">Get Users</span></span>
 
<span data-ttu-id="0bac5-106">**Сводка:** Узнайте об операции "Получить пользователей", которая входит в состав службы пользователей.</span><span class="sxs-lookup"><span data-stu-id="0bac5-106">**Summary:** Learn about the Get Users operation, which is part of the User Service.</span></span> <span data-ttu-id="0bac5-107">Служба пользователей является частью API репозитория для панели мониторинга качества вызовов.</span><span class="sxs-lookup"><span data-stu-id="0bac5-107">The User Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="0bac5-108">Панель мониторинга качества звонков — это инструмент для Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="0bac5-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="0bac5-109">Операция "Получить пользователей" является частью службы пользователей в API репозитория для панели мониторинга качества вызовов.</span><span class="sxs-lookup"><span data-stu-id="0bac5-109">The Get Users operation is part of the User Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-users"></a><span data-ttu-id="0bac5-110">Получение пользователей</span><span class="sxs-lookup"><span data-stu-id="0bac5-110">Get Users</span></span>

<span data-ttu-id="0bac5-111">Get Users returns a list of users in the repository.</span><span class="sxs-lookup"><span data-stu-id="0bac5-111">Get Users returns a list of users in the repository.</span></span>
  
|<span data-ttu-id="0bac5-112">**Способ**</span><span class="sxs-lookup"><span data-stu-id="0bac5-112">**Method**</span></span>|<span data-ttu-id="0bac5-113">**URI запроса**</span><span class="sxs-lookup"><span data-stu-id="0bac5-113">**Request URI**</span></span>|<span data-ttu-id="0bac5-114">**Версия HTTP**</span><span class="sxs-lookup"><span data-stu-id="0bac5-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0bac5-115">GET</span><span class="sxs-lookup"><span data-stu-id="0bac5-115">GET</span></span>  <br/> |<span data-ttu-id="0bac5-116">https:// \<portal\> /QoERepositoryService/repository/user</span><span class="sxs-lookup"><span data-stu-id="0bac5-116">https://\<portal\>/QoERepositoryService/repository/user</span></span>  <br/> |<span data-ttu-id="0bac5-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="0bac5-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="0bac5-118">**Параметры URI** — нет.</span><span class="sxs-lookup"><span data-stu-id="0bac5-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="0bac5-119">**Request Headers** - No additional headers.</span><span class="sxs-lookup"><span data-stu-id="0bac5-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="0bac5-120">**Тело запроса** — нет.</span><span class="sxs-lookup"><span data-stu-id="0bac5-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="0bac5-121">**Ответ.** Ответ включает код состояния HTTP и набор загодеров отклика.</span><span class="sxs-lookup"><span data-stu-id="0bac5-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="0bac5-122">**Код состояния** — успешная операция возвращает код состояния 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="0bac5-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="0bac5-123">**Response Headers** - No additional headers.</span><span class="sxs-lookup"><span data-stu-id="0bac5-123">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="0bac5-124">**Тело ответа.** Ниже приведен пример полезной нагрузки ответа в JSON.</span><span class="sxs-lookup"><span data-stu-id="0bac5-124">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0bac5-125">Возвращается массив объектов User.</span><span class="sxs-lookup"><span data-stu-id="0bac5-125">An array of User objects is returned.</span></span> <span data-ttu-id="0bac5-126">Подробные сведения об объекте User см. в сведениях о get User.</span><span class="sxs-lookup"><span data-stu-id="0bac5-126">For details about the User object, see Get User.</span></span> 
  
```json
[{
"userId": 0,
"loginName": "system",
"defaultItemId": 1652
},
{
"userId": 1,
"loginName": "SAMPLEDOMAIN\\testuser1",
"defaultItemId": 1652
},
{
"userId": 2,
"loginName": "SAMPLEDOMAIN\\testuser2",
"defaultItemId": 1774
}]
```


