---
title: Получение пользователя
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
ms.assetid: 52b89a4b-a0bd-493d-bb5e-e21904eb8e48
description: 'Сводка: сведения о команде Get User, которая входит в состав службы пользователей. Служба User входит в API репозитория для панели мониторинга качества звонков. Панель мониторинга качества звонков — это средство для Skype для бизнеса Server.'
ms.openlocfilehash: e07a232b61e5ef0bb7462b3fff58d642a14496ec
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816738"
---
# <a name="get-user"></a><span data-ttu-id="1f2cf-105">Получение пользователя</span><span class="sxs-lookup"><span data-stu-id="1f2cf-105">Get User</span></span>
 
<span data-ttu-id="1f2cf-106">**Сводка:** Сведения о команде Get User, которая входит в состав службы пользователей.</span><span class="sxs-lookup"><span data-stu-id="1f2cf-106">**Summary:** Learn about the Get User operation, which is part of the User Service.</span></span> <span data-ttu-id="1f2cf-107">Служба User входит в API репозитория для панели мониторинга качества звонков.</span><span class="sxs-lookup"><span data-stu-id="1f2cf-107">The User Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="1f2cf-108">Панель мониторинга качества звонков — это средство для Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="1f2cf-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="1f2cf-109">Операция Get Users является частью службы пользователей в API репозитория для панели мониторинга качества звонков.</span><span class="sxs-lookup"><span data-stu-id="1f2cf-109">The Get Users operation is part of the User Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-user"></a><span data-ttu-id="1f2cf-110">Получение пользователя</span><span class="sxs-lookup"><span data-stu-id="1f2cf-110">Get User</span></span>

<span data-ttu-id="1f2cf-111">Функция Get User возвращает запись пользователя из репозитория.</span><span class="sxs-lookup"><span data-stu-id="1f2cf-111">Get User returns a user record from the repository.</span></span>
  
|<span data-ttu-id="1f2cf-112">**Способов**</span><span class="sxs-lookup"><span data-stu-id="1f2cf-112">**Method**</span></span>|<span data-ttu-id="1f2cf-113">**URI запроса**</span><span class="sxs-lookup"><span data-stu-id="1f2cf-113">**Request URI**</span></span>|<span data-ttu-id="1f2cf-114">**Версия HTTP**</span><span class="sxs-lookup"><span data-stu-id="1f2cf-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1f2cf-115">Получить</span><span class="sxs-lookup"><span data-stu-id="1f2cf-115">GET</span></span>  <br/> |<span data-ttu-id="1f2cf-116">/Коерепоситорисервице/репоситори/Усер/{усерид}\<портала\>HTTPS://</span><span class="sxs-lookup"><span data-stu-id="1f2cf-116">https://\<portal\>/QoERepositoryService/repository/user/{userId}</span></span>  <br/> |<span data-ttu-id="1f2cf-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="1f2cf-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="1f2cf-118">**Параметры универсального кода ресурса** (None).</span><span class="sxs-lookup"><span data-stu-id="1f2cf-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="1f2cf-119">**Заголовки запроса** — без дополнительных заголовков.</span><span class="sxs-lookup"><span data-stu-id="1f2cf-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="1f2cf-120">**Запросить текст** -None.</span><span class="sxs-lookup"><span data-stu-id="1f2cf-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="1f2cf-121">**Response (ответ** ) — ответ включает код состояния HTTP и набор заголовков ответа.</span><span class="sxs-lookup"><span data-stu-id="1f2cf-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="1f2cf-122">**Код состояния** — успешная операция возвращает код состояния 200 (ОК).</span><span class="sxs-lookup"><span data-stu-id="1f2cf-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="1f2cf-123">Если указанный идентификатор пользователя не найден, он возвращает код состояния 404 (не найден).</span><span class="sxs-lookup"><span data-stu-id="1f2cf-123">If a specified user ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="1f2cf-124">**Заголовки ответа** — без дополнительных заголовков.</span><span class="sxs-lookup"><span data-stu-id="1f2cf-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="1f2cf-125">**Тело ответа** — ниже показан пример полезных данных ответа в JSON.</span><span class="sxs-lookup"><span data-stu-id="1f2cf-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```json
{
"userId": 0,
"loginName": "system",
"defaultItemId": 1655
}
```

 <span data-ttu-id="1f2cf-126">*UserID* — идентификатор пользователя.</span><span class="sxs-lookup"><span data-stu-id="1f2cf-126">*userId*  - ID of the user.</span></span>
  
 <span data-ttu-id="1f2cf-127">*наloginname* — внешний идентификатор пользователя для обычных пользователей.</span><span class="sxs-lookup"><span data-stu-id="1f2cf-127">*loginName*  - External user identification for regular users.</span></span> <span data-ttu-id="1f2cf-128">Если для проверки подлинности пользователей используется проверка подлинности Windows, это может быть полное доменное имя пользователя.</span><span class="sxs-lookup"><span data-stu-id="1f2cf-128">If Windows Authentication is used for authenticating users, then this may be a FQDN of the user.</span></span>
  
 <span data-ttu-id="1f2cf-129">*дефаултитемид* — идентификатор элемента по умолчанию для этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="1f2cf-129">*defaultItemId*  - ID of the default Item for this user.</span></span> <span data-ttu-id="1f2cf-130">Элемент по умолчанию — самый верхний элемент, связанный с пользователем.</span><span class="sxs-lookup"><span data-stu-id="1f2cf-130">The default Item is the top-most Item that is associated to the user.</span></span> <span data-ttu-id="1f2cf-131">Все другие элементы, которыми владеет этот пользователь, можно перемещать из элемента по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="1f2cf-131">All other Items this user owns can be navigated from the default Item.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1f2cf-132">Укажите `defaultItemId` значение для получения элемента, чтобы получить сведения об элементе по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="1f2cf-132">Supply the  `defaultItemId` value to Get Item operation to retrieve the details of the default Item.</span></span>
  

