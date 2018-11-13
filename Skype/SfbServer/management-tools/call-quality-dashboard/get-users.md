---
title: Получить пользователей
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 87d34baf-4c31-468d-b8f7-4faca0bc7a54
description: 'Сводка: Сведения о операции получения пользователей, которая является частью службы пользователей. Служба пользователей является частью API репозитория для панели мониторинга качества звонков. Панель мониторинга качества звонков — это средство для Скайп для Business Server 2015.'
ms.openlocfilehash: 6d853e614047c037b0581acaf4935124615ed1e9
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/13/2018
ms.locfileid: "26294060"
---
# <a name="get-users"></a><span data-ttu-id="34998-105">Получить пользователей</span><span class="sxs-lookup"><span data-stu-id="34998-105">Get Users</span></span>
 
<span data-ttu-id="34998-106">**Сводка:** Узнайте о операции получения пользователей, которая является частью службы пользователей.</span><span class="sxs-lookup"><span data-stu-id="34998-106">**Summary:** Learn about the Get Users operation, which is part of the User Service.</span></span> <span data-ttu-id="34998-107">Служба пользователей является частью API репозитория для панели мониторинга качества звонков.</span><span class="sxs-lookup"><span data-stu-id="34998-107">The User Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="34998-108">Панель мониторинга качества звонков — это средство для Скайп для Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="34998-108">Call Quality Dashboard is a tool for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="34998-109">Операция получения пользователей является частью службы пользователей в API репозитория для панели мониторинга качества звонков.</span><span class="sxs-lookup"><span data-stu-id="34998-109">The Get Users operation is part of the User Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-users"></a><span data-ttu-id="34998-110">Получить пользователей</span><span class="sxs-lookup"><span data-stu-id="34998-110">Get Users</span></span>

<span data-ttu-id="34998-111">Получите пользователей возвращает список пользователей в репозитории.</span><span class="sxs-lookup"><span data-stu-id="34998-111">Get Users returns a list of users in the repository.</span></span>
  
|<span data-ttu-id="34998-112">**Метод**</span><span class="sxs-lookup"><span data-stu-id="34998-112">**Method**</span></span>|<span data-ttu-id="34998-113">**URI запроса**</span><span class="sxs-lookup"><span data-stu-id="34998-113">**Request URI**</span></span>|<span data-ttu-id="34998-114">**Версия HTTP**</span><span class="sxs-lookup"><span data-stu-id="34998-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="34998-115">Получить</span><span class="sxs-lookup"><span data-stu-id="34998-115">GET</span></span>  <br/> |<span data-ttu-id="34998-116">https://\<портала\>/QoERepositoryService/repository/user</span><span class="sxs-lookup"><span data-stu-id="34998-116">https://\<portal\>/QoERepositoryService/repository/user</span></span>  <br/> |<span data-ttu-id="34998-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="34998-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="34998-118">**Параметры URI** — нет.</span><span class="sxs-lookup"><span data-stu-id="34998-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="34998-119">**Заголовки запроса** — без дополнительных заголовков.</span><span class="sxs-lookup"><span data-stu-id="34998-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="34998-120">**Текст запроса** — нет.</span><span class="sxs-lookup"><span data-stu-id="34998-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="34998-121">**Ответа** - ответ включает код состояния HTTP и набор заголовков ответов.</span><span class="sxs-lookup"><span data-stu-id="34998-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="34998-122">**Код состояния** - успешные операции возвращает код состояния 200 (ОК).</span><span class="sxs-lookup"><span data-stu-id="34998-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="34998-123">**Заголовки ответа** — без дополнительных заголовков.</span><span class="sxs-lookup"><span data-stu-id="34998-123">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="34998-124">**Тело ответа** - ниже приведен пример полезные данные ответа в формате JSON в.</span><span class="sxs-lookup"><span data-stu-id="34998-124">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="34998-125">Возвращает массив объектов-пользователей.</span><span class="sxs-lookup"><span data-stu-id="34998-125">An array of User objects is returned.</span></span> <span data-ttu-id="34998-126">Для получения дополнительных сведений об объекте пользователя видеть получить пользователя.</span><span class="sxs-lookup"><span data-stu-id="34998-126">For details about the User object, see Get User.</span></span> 
  
```
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


