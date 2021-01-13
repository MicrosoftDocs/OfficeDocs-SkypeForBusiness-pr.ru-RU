---
title: Получение параметра пользователя
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
ms.assetid: 16611a55-79fb-487a-a936-20caca829f87
description: Сводка. Сведения об операции "Получить параметр пользователя", которая входит в состав службы параметров пользователей. Служба параметров пользователя является частью API репозитория для панели мониторинга качества вызовов. Панель мониторинга качества звонков — это инструмент для Skype для бизнеса Server.
ms.openlocfilehash: 82632f5de7ae215d6f34d9f0b39e500fb713a1be
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832489"
---
# <a name="get-user-setting"></a><span data-ttu-id="71696-105">Получение параметра пользователя</span><span class="sxs-lookup"><span data-stu-id="71696-105">Get User Setting</span></span>
 
<span data-ttu-id="71696-106">**Сводка:** Learn about the Get User Setting operation, which is part of the User Settings Service.</span><span class="sxs-lookup"><span data-stu-id="71696-106">**Summary:** Learn about the Get User Setting operation, which is part of the User Settings Service.</span></span> <span data-ttu-id="71696-107">Служба параметров пользователя является частью API репозитория для панели мониторинга качества вызовов.</span><span class="sxs-lookup"><span data-stu-id="71696-107">The User Settings Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="71696-108">Панель мониторинга качества звонков — это инструмент для Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="71696-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="71696-109">Операция "Получить параметр пользователя" является частью службы пользовательских параметров в API репозитория для панели мониторинга качества вызовов.</span><span class="sxs-lookup"><span data-stu-id="71696-109">The Get User Setting operation is part of the User Settings Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-user-setting"></a><span data-ttu-id="71696-110">Получение параметра пользователя</span><span class="sxs-lookup"><span data-stu-id="71696-110">Get User Setting</span></span>

<span data-ttu-id="71696-111">При этом возвращается один параметр пользователя.</span><span class="sxs-lookup"><span data-stu-id="71696-111">Get User Setting returns a single user setting.</span></span>
  

|<span data-ttu-id="71696-112">**Способ**</span><span class="sxs-lookup"><span data-stu-id="71696-112">**Method**</span></span>|<span data-ttu-id="71696-113">**URI запроса**</span><span class="sxs-lookup"><span data-stu-id="71696-113">**Request URI**</span></span>|<span data-ttu-id="71696-114">**Версия HTTP**</span><span class="sxs-lookup"><span data-stu-id="71696-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="71696-115">GET</span><span class="sxs-lookup"><span data-stu-id="71696-115">GET</span></span>  <br/> |<span data-ttu-id="71696-116">https:// \<portal\> /QoERepositoryService/repository/user/{userId}/setting/{key}</span><span class="sxs-lookup"><span data-stu-id="71696-116">https://\<portal\>/QoERepositoryService/repository/user/{userId}/setting/{key}</span></span>  <br/> |<span data-ttu-id="71696-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="71696-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="71696-118">**Параметры URI** — нет.</span><span class="sxs-lookup"><span data-stu-id="71696-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="71696-119">**Request Headers** - No additional headers.</span><span class="sxs-lookup"><span data-stu-id="71696-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="71696-120">**Тело запроса** — нет.</span><span class="sxs-lookup"><span data-stu-id="71696-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="71696-121">**Ответ.** Ответ включает код состояния HTTP и набор загодеров отклика.</span><span class="sxs-lookup"><span data-stu-id="71696-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="71696-122">**Код состояния** : успешная операция возвращает код состояния 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="71696-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="71696-123">**Response Headers** - No additional headers.</span><span class="sxs-lookup"><span data-stu-id="71696-123">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="71696-124">**Тело ответа.** Ниже приведен пример полезной нагрузки ответа в JSON.</span><span class="sxs-lookup"><span data-stu-id="71696-124">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```json
{
"userId": 6,
"key": "ShowDescriptions",
"value": "true"
}
```

 <span data-ttu-id="71696-125">*userId*  — ИД пользователя.</span><span class="sxs-lookup"><span data-stu-id="71696-125">*userId*  - ID of the user.</span></span>
  
 <span data-ttu-id="71696-126">*key*  — ключ параметра.</span><span class="sxs-lookup"><span data-stu-id="71696-126">*key*  - Key of the setting.</span></span>
  
 <span data-ttu-id="71696-127">*value*  — значение параметра.</span><span class="sxs-lookup"><span data-stu-id="71696-127">*value*  - Value of the setting.</span></span>
  

