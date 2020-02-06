---
title: Получение пользователей
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
ms.assetid: 87d34baf-4c31-468d-b8f7-4faca0bc7a54
description: 'Сводка: сведения о команде Get Users, которая входит в состав службы пользователей. Служба User входит в API репозитория для панели мониторинга качества звонков. Панель мониторинга качества звонков — это средство для Skype для бизнеса Server.'
ms.openlocfilehash: 81d261a49798ef49d4a1d693681b4497652cf395
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816728"
---
# <a name="get-users"></a><span data-ttu-id="678a3-105">Получение пользователей</span><span class="sxs-lookup"><span data-stu-id="678a3-105">Get Users</span></span>
 
<span data-ttu-id="678a3-106">**Сводка:** Сведения о выполнении операции Get Users, которая входит в состав службы "Пользователи".</span><span class="sxs-lookup"><span data-stu-id="678a3-106">**Summary:** Learn about the Get Users operation, which is part of the User Service.</span></span> <span data-ttu-id="678a3-107">Служба User входит в API репозитория для панели мониторинга качества звонков.</span><span class="sxs-lookup"><span data-stu-id="678a3-107">The User Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="678a3-108">Панель мониторинга качества звонков — это средство для Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="678a3-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="678a3-109">Операция Get Users является частью службы пользователей в API репозитория для панели мониторинга качества звонков.</span><span class="sxs-lookup"><span data-stu-id="678a3-109">The Get Users operation is part of the User Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-users"></a><span data-ttu-id="678a3-110">Получение пользователей</span><span class="sxs-lookup"><span data-stu-id="678a3-110">Get Users</span></span>

<span data-ttu-id="678a3-111">Функция Get Users возвращает список пользователей в репозитории.</span><span class="sxs-lookup"><span data-stu-id="678a3-111">Get Users returns a list of users in the repository.</span></span>
  
|<span data-ttu-id="678a3-112">**Способов**</span><span class="sxs-lookup"><span data-stu-id="678a3-112">**Method**</span></span>|<span data-ttu-id="678a3-113">**URI запроса**</span><span class="sxs-lookup"><span data-stu-id="678a3-113">**Request URI**</span></span>|<span data-ttu-id="678a3-114">**Версия HTTP**</span><span class="sxs-lookup"><span data-stu-id="678a3-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="678a3-115">Получить</span><span class="sxs-lookup"><span data-stu-id="678a3-115">GET</span></span>  <br/> |<span data-ttu-id="678a3-116">/Коерепоситорисервице/репоситори/Усер\<портала\>HTTPS://</span><span class="sxs-lookup"><span data-stu-id="678a3-116">https://\<portal\>/QoERepositoryService/repository/user</span></span>  <br/> |<span data-ttu-id="678a3-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="678a3-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="678a3-118">**Параметры универсального кода ресурса** (None).</span><span class="sxs-lookup"><span data-stu-id="678a3-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="678a3-119">**Заголовки запроса** — без дополнительных заголовков.</span><span class="sxs-lookup"><span data-stu-id="678a3-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="678a3-120">**Запросить текст** -None.</span><span class="sxs-lookup"><span data-stu-id="678a3-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="678a3-121">**Response (ответ** ) — ответ включает код состояния HTTP и набор заголовков ответа.</span><span class="sxs-lookup"><span data-stu-id="678a3-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="678a3-122">**Код состояния** — успешная операция возвращает код состояния 200 (ОК).</span><span class="sxs-lookup"><span data-stu-id="678a3-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="678a3-123">**Заголовки ответа** — без дополнительных заголовков.</span><span class="sxs-lookup"><span data-stu-id="678a3-123">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="678a3-124">**Тело ответа** — ниже показан пример полезных данных ответа в JSON.</span><span class="sxs-lookup"><span data-stu-id="678a3-124">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="678a3-125">Возвращается массив объектов пользователя.</span><span class="sxs-lookup"><span data-stu-id="678a3-125">An array of User objects is returned.</span></span> <span data-ttu-id="678a3-126">Сведения об объекте User можно найти в статьях получение пользователя.</span><span class="sxs-lookup"><span data-stu-id="678a3-126">For details about the User object, see Get User.</span></span> 
  
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


