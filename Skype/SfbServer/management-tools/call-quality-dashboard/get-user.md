---
title: Получение пользователя
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 52b89a4b-a0bd-493d-bb5e-e21904eb8e48
description: 'Сводка: Сведения об операции получения пользователя, входящего в состав службы пользователей. Служба пользователей является частью API репозитория для панели мониторинга качества звонков. Панель мониторинга качества звонков — это средство для Скайп для Business Server.'
ms.openlocfilehash: 2d3c5febe30af2ea4d41d94aec026c25e27f21b9
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32235725"
---
# <a name="get-user"></a><span data-ttu-id="00c94-105">Получение пользователя</span><span class="sxs-lookup"><span data-stu-id="00c94-105">Get User</span></span>
 
<span data-ttu-id="00c94-106">**Сводка:** Сведения об операции получения пользователя, входящего в состав службы пользователей.</span><span class="sxs-lookup"><span data-stu-id="00c94-106">**Summary:** Learn about the Get User operation, which is part of the User Service.</span></span> <span data-ttu-id="00c94-107">Служба пользователей является частью API репозитория для панели мониторинга качества звонков.</span><span class="sxs-lookup"><span data-stu-id="00c94-107">The User Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="00c94-108">Панель мониторинга качества звонков — это средство для Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="00c94-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="00c94-109">Операция получения пользователей является частью службы пользователей в API репозитория для панели мониторинга качества звонков.</span><span class="sxs-lookup"><span data-stu-id="00c94-109">The Get Users operation is part of the User Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-user"></a><span data-ttu-id="00c94-110">Получение пользователя</span><span class="sxs-lookup"><span data-stu-id="00c94-110">Get User</span></span>

<span data-ttu-id="00c94-111">Получите пользователя возвращает запись пользователя из репозитория.</span><span class="sxs-lookup"><span data-stu-id="00c94-111">Get User returns a user record from the repository.</span></span>
  
|<span data-ttu-id="00c94-112">**Метод**</span><span class="sxs-lookup"><span data-stu-id="00c94-112">**Method**</span></span>|<span data-ttu-id="00c94-113">**URI запроса**</span><span class="sxs-lookup"><span data-stu-id="00c94-113">**Request URI**</span></span>|<span data-ttu-id="00c94-114">**Версия HTTP**</span><span class="sxs-lookup"><span data-stu-id="00c94-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="00c94-115">Получить</span><span class="sxs-lookup"><span data-stu-id="00c94-115">GET</span></span>  <br/> |<span data-ttu-id="00c94-116">https://\<портала\>/QoERepositoryService/репозитория/пользователей / {userId}</span><span class="sxs-lookup"><span data-stu-id="00c94-116">https://\<portal\>/QoERepositoryService/repository/user/{userId}</span></span>  <br/> |<span data-ttu-id="00c94-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="00c94-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="00c94-118">**Параметры URI** — нет.</span><span class="sxs-lookup"><span data-stu-id="00c94-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="00c94-119">**Заголовки запроса** — без дополнительных заголовков.</span><span class="sxs-lookup"><span data-stu-id="00c94-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="00c94-120">**Текст запроса** — нет.</span><span class="sxs-lookup"><span data-stu-id="00c94-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="00c94-121">**Ответа** - ответ включает код состояния HTTP и набор заголовков ответов.</span><span class="sxs-lookup"><span data-stu-id="00c94-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="00c94-122">**Код состояния** - успешные операции возвращает код состояния 200 (ОК).</span><span class="sxs-lookup"><span data-stu-id="00c94-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="00c94-123">Если указанный пользователь с Идентификатором не найден, он возвращает код состояния 404 (не найден).</span><span class="sxs-lookup"><span data-stu-id="00c94-123">If a specified user ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="00c94-124">**Заголовки ответа** — без дополнительных заголовков.</span><span class="sxs-lookup"><span data-stu-id="00c94-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="00c94-125">**Тело ответа** - ниже приведен пример полезные данные ответа в формате JSON в.</span><span class="sxs-lookup"><span data-stu-id="00c94-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```
{
"userId": 0,
"loginName": "system",
"defaultItemId": 1655
}
```

 <span data-ttu-id="00c94-126">*идентификатор пользователя* — идентификатор пользователя.</span><span class="sxs-lookup"><span data-stu-id="00c94-126">*userId*  - ID of the user.</span></span>
  
 <span data-ttu-id="00c94-127">*loginName* - идентификации внешних пользователей для обычных пользователей.</span><span class="sxs-lookup"><span data-stu-id="00c94-127">*loginName*  - External user identification for regular users.</span></span> <span data-ttu-id="00c94-128">Если используется проверка подлинности Windows для проверки подлинности пользователей, это может быть полное доменное имя пользователя.</span><span class="sxs-lookup"><span data-stu-id="00c94-128">If Windows Authentication is used for authenticating users, then this may be a FQDN of the user.</span></span>
  
 <span data-ttu-id="00c94-129">*defaultItemId* - идентификатор элемента по умолчанию для этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="00c94-129">*defaultItemId*  - ID of the default Item for this user.</span></span> <span data-ttu-id="00c94-130">Значение по умолчанию элемента — элемент верхнего уровня, назначенного пользователю.</span><span class="sxs-lookup"><span data-stu-id="00c94-130">The default Item is the top-most Item that is associated to the user.</span></span> <span data-ttu-id="00c94-131">Все другие элементы, которому принадлежит этот пользователь может пройти от элемента по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="00c94-131">All other Items this user owns can be navigated from the default Item.</span></span>
  
> [!NOTE]
> <span data-ttu-id="00c94-132">Предоставить `defaultItemId` значение для операции получения элемента для получения сведений о элемента по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="00c94-132">Supply the  `defaultItemId` value to Get Item operation to retrieve the details of the default Item.</span></span>
  

