---
title: Получить параметры пользователя
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 16611a55-79fb-487a-a936-20caca829f87
description: 'Сводка: Сведения о операцию получить пользовательский параметр, который является частью службы параметров пользователя. Служба параметров пользователя входит в API репозитория для панели мониторинга качества звонков. Панель мониторинга качества звонков — это средство для Скайп для Business Server.'
ms.openlocfilehash: 286939271bdc99790f125beabb68735dd4c5f758
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/15/2018
ms.locfileid: "26530715"
---
# <a name="get-user-setting"></a><span data-ttu-id="345a4-105">Получить параметры пользователя</span><span class="sxs-lookup"><span data-stu-id="345a4-105">Get User Setting</span></span>
 
<span data-ttu-id="345a4-106">**Сводка:** Узнайте о операцию получить пользовательский параметр, который является частью службы параметров пользователя.</span><span class="sxs-lookup"><span data-stu-id="345a4-106">**Summary:** Learn about the Get User Setting operation, which is part of the User Settings Service.</span></span> <span data-ttu-id="345a4-107">Служба параметров пользователя входит в API репозитория для панели мониторинга качества звонков.</span><span class="sxs-lookup"><span data-stu-id="345a4-107">The User Settings Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="345a4-108">Панель мониторинга качества звонков — это средство для Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="345a4-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="345a4-109">Операция получения параметр пользователя является частью служба параметров пользователя в API репозитория для панели мониторинга качества звонков.</span><span class="sxs-lookup"><span data-stu-id="345a4-109">The Get User Setting operation is part of the User Settings Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-user-setting"></a><span data-ttu-id="345a4-110">Получить параметры пользователя</span><span class="sxs-lookup"><span data-stu-id="345a4-110">Get User Setting</span></span>

<span data-ttu-id="345a4-111">Получите возвращает параметр пользователя параметр с одним пользователем.</span><span class="sxs-lookup"><span data-stu-id="345a4-111">Get User Setting returns a single user setting.</span></span>
  

|<span data-ttu-id="345a4-112">**Метод**</span><span class="sxs-lookup"><span data-stu-id="345a4-112">**Method**</span></span>|<span data-ttu-id="345a4-113">**URI запроса**</span><span class="sxs-lookup"><span data-stu-id="345a4-113">**Request URI**</span></span>|<span data-ttu-id="345a4-114">**Версия HTTP**</span><span class="sxs-lookup"><span data-stu-id="345a4-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="345a4-115">Получить</span><span class="sxs-lookup"><span data-stu-id="345a4-115">GET</span></span>  <br/> |<span data-ttu-id="345a4-116">https://\<портала\>/QoERepositoryService/репозитория/пользователей / {userId} /setting/ {раздела}</span><span class="sxs-lookup"><span data-stu-id="345a4-116">https://\<portal\>/QoERepositoryService/repository/user/{userId}/setting/{key}</span></span>  <br/> |<span data-ttu-id="345a4-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="345a4-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="345a4-118">**Параметры URI** — нет.</span><span class="sxs-lookup"><span data-stu-id="345a4-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="345a4-119">**Заголовки запроса** — без дополнительных заголовков.</span><span class="sxs-lookup"><span data-stu-id="345a4-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="345a4-120">**Текст запроса** — нет.</span><span class="sxs-lookup"><span data-stu-id="345a4-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="345a4-121">**Ответа** - ответ включает код состояния HTTP и набор заголовков ответов.</span><span class="sxs-lookup"><span data-stu-id="345a4-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="345a4-122">**Код состояния** - успешные операции возвращает код состояния 200 (ОК).</span><span class="sxs-lookup"><span data-stu-id="345a4-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="345a4-123">**Заголовки ответа** — без дополнительных заголовков.</span><span class="sxs-lookup"><span data-stu-id="345a4-123">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="345a4-124">**Тело ответа** - ниже приведен пример полезные данные ответа в формате JSON в.</span><span class="sxs-lookup"><span data-stu-id="345a4-124">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```
{
"userId": 6,
"key": "ShowDescriptions",
"value": "true"
}
```

 <span data-ttu-id="345a4-125">*идентификатор пользователя* — идентификатор пользователя.</span><span class="sxs-lookup"><span data-stu-id="345a4-125">*userId*  - ID of the user.</span></span>
  
 <span data-ttu-id="345a4-126">*ключ* - ключ параметра.</span><span class="sxs-lookup"><span data-stu-id="345a4-126">*key*  - Key of the setting.</span></span>
  
 <span data-ttu-id="345a4-127">*значение* — значение параметра.</span><span class="sxs-lookup"><span data-stu-id="345a4-127">*value*  - Value of the setting.</span></span>
  

