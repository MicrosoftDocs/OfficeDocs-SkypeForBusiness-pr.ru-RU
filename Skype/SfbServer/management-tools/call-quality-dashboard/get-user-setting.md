---
title: Получение параметра пользователя
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 16611a55-79fb-487a-a936-20caca829f87
description: 'Сводка: сведения о команде "получить параметры пользователя", которая входит в состав службы параметров пользователя. Служба параметров пользователя входит в API репозитория для панели мониторинга качества звонков. Панель мониторинга качества звонков — это средство для Skype для бизнеса Server.'
ms.openlocfilehash: 295e12405eb6a7ebbf45b87e3a06f3a745b90bad
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274655"
---
# <a name="get-user-setting"></a><span data-ttu-id="670d2-105">Получение параметра пользователя</span><span class="sxs-lookup"><span data-stu-id="670d2-105">Get User Setting</span></span>
 
<span data-ttu-id="670d2-106">**Сводка:** Узнайте о том, как получить параметр пользователя, который входит в состав службы параметров пользователя.</span><span class="sxs-lookup"><span data-stu-id="670d2-106">**Summary:** Learn about the Get User Setting operation, which is part of the User Settings Service.</span></span> <span data-ttu-id="670d2-107">Служба параметров пользователя входит в API репозитория для панели мониторинга качества звонков.</span><span class="sxs-lookup"><span data-stu-id="670d2-107">The User Settings Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="670d2-108">Панель мониторинга качества звонков — это средство для Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="670d2-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="670d2-109">Операция получения параметров пользователя входит в состав службы параметров пользователя в API репозитория для панели мониторинга качества звонков.</span><span class="sxs-lookup"><span data-stu-id="670d2-109">The Get User Setting operation is part of the User Settings Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-user-setting"></a><span data-ttu-id="670d2-110">Получение параметра пользователя</span><span class="sxs-lookup"><span data-stu-id="670d2-110">Get User Setting</span></span>

<span data-ttu-id="670d2-111">Параметр получить параметры пользователя возвращает один пользовательский параметр.</span><span class="sxs-lookup"><span data-stu-id="670d2-111">Get User Setting returns a single user setting.</span></span>
  

|<span data-ttu-id="670d2-112">**Способов**</span><span class="sxs-lookup"><span data-stu-id="670d2-112">**Method**</span></span>|<span data-ttu-id="670d2-113">**URI запроса**</span><span class="sxs-lookup"><span data-stu-id="670d2-113">**Request URI**</span></span>|<span data-ttu-id="670d2-114">**Версия HTTP**</span><span class="sxs-lookup"><span data-stu-id="670d2-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="670d2-115">Получить</span><span class="sxs-lookup"><span data-stu-id="670d2-115">GET</span></span>  <br/> |<span data-ttu-id="670d2-116">/Коерепоситорисервице/репоситори/Усер/{усерид}/сеттинг/{Кэй}\<портала\>HTTPS://</span><span class="sxs-lookup"><span data-stu-id="670d2-116">https://\<portal\>/QoERepositoryService/repository/user/{userId}/setting/{key}</span></span>  <br/> |<span data-ttu-id="670d2-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="670d2-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="670d2-118">**Параметры универсального кода ресурса** (None).</span><span class="sxs-lookup"><span data-stu-id="670d2-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="670d2-119">**Заголовки запроса** — без дополнительных заголовков.</span><span class="sxs-lookup"><span data-stu-id="670d2-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="670d2-120">**Запросить текст** -None.</span><span class="sxs-lookup"><span data-stu-id="670d2-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="670d2-121">**Response (ответ** ) — ответ включает код состояния HTTP и набор заголовков ответа.</span><span class="sxs-lookup"><span data-stu-id="670d2-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="670d2-122">**Код состояния** — успешная операция возвращает код состояния 200 (ОК).</span><span class="sxs-lookup"><span data-stu-id="670d2-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="670d2-123">**Заголовки ответа** — без дополнительных заголовков.</span><span class="sxs-lookup"><span data-stu-id="670d2-123">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="670d2-124">**Тело ответа** — ниже показан пример полезных данных ответа в JSON.</span><span class="sxs-lookup"><span data-stu-id="670d2-124">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```
{
"userId": 6,
"key": "ShowDescriptions",
"value": "true"
}
```

 <span data-ttu-id="670d2-125">*UserID* — идентификатор пользователя.</span><span class="sxs-lookup"><span data-stu-id="670d2-125">*userId*  - ID of the user.</span></span>
  
 <span data-ttu-id="670d2-126">\*\* клавиша со значением параметра.</span><span class="sxs-lookup"><span data-stu-id="670d2-126">*key*  - Key of the setting.</span></span>
  
 <span data-ttu-id="670d2-127">*value (значение* ) параметра.</span><span class="sxs-lookup"><span data-stu-id="670d2-127">*value*  - Value of the setting.</span></span>
  

