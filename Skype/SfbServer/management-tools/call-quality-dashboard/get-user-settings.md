---
title: Получение параметров пользователя
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bdfe063b-e808-4f3c-884a-acbbabb9be0a
description: 'Сводка: сведения о команде "получить параметры пользователя", которая входит в состав службы параметров пользователя. Служба параметров пользователя входит в API репозитория для панели мониторинга качества звонков. Панель мониторинга качества звонков — это средство для Skype для бизнеса Server.'
ms.openlocfilehash: 42934496b8b65132a67d4012d81d7b8997859726
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992636"
---
# <a name="get-user-settings"></a><span data-ttu-id="fa9ca-105">Получение параметров пользователя</span><span class="sxs-lookup"><span data-stu-id="fa9ca-105">Get User Settings</span></span>
 
<span data-ttu-id="fa9ca-106">**Сводка:** Сведения о выполнении операции получения параметров пользователя, которая входит в состав службы параметров пользователя.</span><span class="sxs-lookup"><span data-stu-id="fa9ca-106">**Summary:** Learn about the Get User Settings operation, which is part of the User Settings Service.</span></span> <span data-ttu-id="fa9ca-107">Служба параметров пользователя входит в API репозитория для панели мониторинга качества звонков.</span><span class="sxs-lookup"><span data-stu-id="fa9ca-107">The User Settings Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="fa9ca-108">Панель мониторинга качества звонков — это средство для Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="fa9ca-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="fa9ca-109">Операция "получить параметры пользователя" входит в состав службы параметров пользователя в API репозитория для панели мониторинга качества звонков.</span><span class="sxs-lookup"><span data-stu-id="fa9ca-109">The Get User Settings operation is part of the User Settings Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-user-settings"></a><span data-ttu-id="fa9ca-110">Получение параметров пользователя</span><span class="sxs-lookup"><span data-stu-id="fa9ca-110">Get User Settings</span></span>

<span data-ttu-id="fa9ca-111">Получить параметры пользователя возвращает список параметров для указанного пользователя.</span><span class="sxs-lookup"><span data-stu-id="fa9ca-111">Get User Settings returns a list of settings for a specified user.</span></span>
  

|<span data-ttu-id="fa9ca-112">**Способов**</span><span class="sxs-lookup"><span data-stu-id="fa9ca-112">**Method**</span></span>|<span data-ttu-id="fa9ca-113">**URI запроса**</span><span class="sxs-lookup"><span data-stu-id="fa9ca-113">**Request URI**</span></span>|<span data-ttu-id="fa9ca-114">**Версия HTTP**</span><span class="sxs-lookup"><span data-stu-id="fa9ca-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="fa9ca-115">Получить</span><span class="sxs-lookup"><span data-stu-id="fa9ca-115">GET</span></span>  <br/> |<span data-ttu-id="fa9ca-116">/Коерепоситорисервице/репоситори/Усер/{усерид}/сеттинг\<портала\>HTTPS://</span><span class="sxs-lookup"><span data-stu-id="fa9ca-116">https://\<portal\>/QoERepositoryService/repository/user/{userId}/setting</span></span>  <br/> |<span data-ttu-id="fa9ca-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="fa9ca-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="fa9ca-118">**Параметры URI**</span><span class="sxs-lookup"><span data-stu-id="fa9ca-118">**URI Parameters**</span></span>
  
- <span data-ttu-id="fa9ca-119">*эффективная* — необязательный.</span><span class="sxs-lookup"><span data-stu-id="fa9ca-119">*effective*  - Optional.</span></span> <span data-ttu-id="fa9ca-120">Этот параметр применяется только в том случае, если используется специальный идентификатор пользователя по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="fa9ca-120">This parameter applies only when the special user ID default is used.</span></span> <span data-ttu-id="fa9ca-121">В других случаях оно будет игнорироваться.</span><span class="sxs-lookup"><span data-stu-id="fa9ca-121">In other cases, it will be ignored.</span></span> <span data-ttu-id="fa9ca-122">`True`Возвращает действующие пользовательские параметры и `false` возвращает только пользовательские параметры (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="fa9ca-122">`True` returns effective user settings and `false` returns just user settings (default).</span></span>
    
  <span data-ttu-id="fa9ca-123">**Заголовки запроса** — без дополнительных заголовков.</span><span class="sxs-lookup"><span data-stu-id="fa9ca-123">**Request Headers** - No additional headers.</span></span>
  
  <span data-ttu-id="fa9ca-124">**Запросить текст** -None.</span><span class="sxs-lookup"><span data-stu-id="fa9ca-124">**Request Body** - None.</span></span>
  
  <span data-ttu-id="fa9ca-125">**Response (ответ** ) — ответ включает код состояния HTTP и набор заголовков ответа.</span><span class="sxs-lookup"><span data-stu-id="fa9ca-125">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
  <span data-ttu-id="fa9ca-126">**Код состояния** — успешная операция возвращает код состояния 200 (ОК).</span><span class="sxs-lookup"><span data-stu-id="fa9ca-126">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
  <span data-ttu-id="fa9ca-127">**Заголовки ответа** — без дополнительных заголовков.</span><span class="sxs-lookup"><span data-stu-id="fa9ca-127">**Response Headers** - No additional headers.</span></span>
  
  <span data-ttu-id="fa9ca-128">**Тело ответа** — ниже показан пример полезных данных ответа в JSON.</span><span class="sxs-lookup"><span data-stu-id="fa9ca-128">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
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
