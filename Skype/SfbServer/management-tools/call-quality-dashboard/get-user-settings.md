---
title: Получение параметров пользователя
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
ms.assetid: bdfe063b-e808-4f3c-884a-acbbabb9be0a
description: Сводка. Сведения об операции "Получить параметры пользователя", которая входит в состав службы параметров пользователей. Служба параметров пользователя является частью API репозитория для панели мониторинга качества вызовов. Панель мониторинга качества звонков — это инструмент для Skype для бизнеса Server.
ms.openlocfilehash: e2ebf39ba5a7de5d36a8b1ea0441808b6e71f97b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832479"
---
# <a name="get-user-settings"></a><span data-ttu-id="36103-105">Получение параметров пользователя</span><span class="sxs-lookup"><span data-stu-id="36103-105">Get User Settings</span></span>
 
<span data-ttu-id="36103-106">**Сводка:** Узнайте об операции "Получить параметры пользователя", которая входит в состав службы параметров пользователей.</span><span class="sxs-lookup"><span data-stu-id="36103-106">**Summary:** Learn about the Get User Settings operation, which is part of the User Settings Service.</span></span> <span data-ttu-id="36103-107">Служба параметров пользователя является частью API репозитория для панели мониторинга качества вызовов.</span><span class="sxs-lookup"><span data-stu-id="36103-107">The User Settings Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="36103-108">Панель мониторинга качества звонков — это инструмент для Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="36103-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="36103-109">Операция "Получить параметры пользователя" является частью службы параметров пользователя в API репозитория для панели мониторинга качества вызовов.</span><span class="sxs-lookup"><span data-stu-id="36103-109">The Get User Settings operation is part of the User Settings Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-user-settings"></a><span data-ttu-id="36103-110">Получение параметров пользователя</span><span class="sxs-lookup"><span data-stu-id="36103-110">Get User Settings</span></span>

<span data-ttu-id="36103-111">При этом возвращается список параметров для указанного пользователя.</span><span class="sxs-lookup"><span data-stu-id="36103-111">Get User Settings returns a list of settings for a specified user.</span></span>
  

|<span data-ttu-id="36103-112">**Способ**</span><span class="sxs-lookup"><span data-stu-id="36103-112">**Method**</span></span>|<span data-ttu-id="36103-113">**URI запроса**</span><span class="sxs-lookup"><span data-stu-id="36103-113">**Request URI**</span></span>|<span data-ttu-id="36103-114">**Версия HTTP**</span><span class="sxs-lookup"><span data-stu-id="36103-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="36103-115">GET</span><span class="sxs-lookup"><span data-stu-id="36103-115">GET</span></span>  <br/> |<span data-ttu-id="36103-116">https:// \<portal\> /QoERepositoryService/repository/user/{userId}/setting</span><span class="sxs-lookup"><span data-stu-id="36103-116">https://\<portal\>/QoERepositoryService/repository/user/{userId}/setting</span></span>  <br/> |<span data-ttu-id="36103-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="36103-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="36103-118">**Параметры URI**</span><span class="sxs-lookup"><span data-stu-id="36103-118">**URI Parameters**</span></span>
  
- <span data-ttu-id="36103-119">*effective*  — необязательный.</span><span class="sxs-lookup"><span data-stu-id="36103-119">*effective*  - Optional.</span></span> <span data-ttu-id="36103-120">Этот параметр применяется, только если используется специальный ИД пользователя по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="36103-120">This parameter applies only when the special user ID default is used.</span></span> <span data-ttu-id="36103-121">В других случаях он будет игнорироваться.</span><span class="sxs-lookup"><span data-stu-id="36103-121">In other cases, it will be ignored.</span></span> <span data-ttu-id="36103-122">`True` возвращает эффективные параметры пользователя и `false` возвращает только параметры пользователя (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="36103-122">`True` returns effective user settings and `false` returns just user settings (default).</span></span>
    
  <span data-ttu-id="36103-123">**Request Headers** - No additional headers.</span><span class="sxs-lookup"><span data-stu-id="36103-123">**Request Headers** - No additional headers.</span></span>
  
  <span data-ttu-id="36103-124">**Тело запроса** — нет.</span><span class="sxs-lookup"><span data-stu-id="36103-124">**Request Body** - None.</span></span>
  
  <span data-ttu-id="36103-125">**Ответ.** Ответ включает код состояния HTTP и набор загодеров отклика.</span><span class="sxs-lookup"><span data-stu-id="36103-125">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
  <span data-ttu-id="36103-126">**Код состояния** : успешная операция возвращает код состояния 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="36103-126">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
  <span data-ttu-id="36103-127">**Response Headers** - No additional headers.</span><span class="sxs-lookup"><span data-stu-id="36103-127">**Response Headers** - No additional headers.</span></span>
  
  <span data-ttu-id="36103-128">**Тело ответа.** Ниже приведен пример полезной нагрузки ответа в JSON.</span><span class="sxs-lookup"><span data-stu-id="36103-128">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```json
[{
"userId": 6,
"key": "ShowDescriptions",
"value": "true"
},
{
"userId": 6,
"key": "ShowTimeStamps",
"value": "true"
}]
```
