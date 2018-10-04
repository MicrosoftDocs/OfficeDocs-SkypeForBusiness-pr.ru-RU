---
title: Получение параметров пользователя
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bdfe063b-e808-4f3c-884a-acbbabb9be0a
description: 'Сводка: Сведения о операцию получить параметры пользователя, который является частью службы параметров пользователя. Служба параметров пользователя входит в API репозитория для панели мониторинга качества звонков. Панель мониторинга качества звонков — это средство для Скайп для Business Server 2015.'
ms.openlocfilehash: 41bc45f63366337000ad8c263ff8e6dbcb36a3b3
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2018
ms.locfileid: "25375381"
---
# <a name="get-user-settings"></a><span data-ttu-id="69963-105">Получение параметров пользователя</span><span class="sxs-lookup"><span data-stu-id="69963-105">Get User Settings</span></span>
 
<span data-ttu-id="69963-106">**Сводка:** Узнайте о операцию получить параметры пользователя, который является частью службы параметров пользователя.</span><span class="sxs-lookup"><span data-stu-id="69963-106">**Summary:** Learn about the Get User Settings operation, which is part of the User Settings Service.</span></span> <span data-ttu-id="69963-107">Служба параметров пользователя входит в API репозитория для панели мониторинга качества звонков.</span><span class="sxs-lookup"><span data-stu-id="69963-107">The User Settings Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="69963-108">Панель мониторинга качества звонков — это средство для Скайп для Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="69963-108">Call Quality Dashboard is a tool for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="69963-109">Операция получить параметры пользователя является частью служба параметров пользователя в API репозитория для панели мониторинга качества звонков.</span><span class="sxs-lookup"><span data-stu-id="69963-109">The Get User Settings operation is part of the User Settings Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-user-settings"></a><span data-ttu-id="69963-110">Получение параметров пользователя</span><span class="sxs-lookup"><span data-stu-id="69963-110">Get User Settings</span></span>

<span data-ttu-id="69963-111">Параметры пользователя Get возвращает список параметров для указанного пользователя.</span><span class="sxs-lookup"><span data-stu-id="69963-111">Get User Settings returns a list of settings for a specified user.</span></span>
  

|<span data-ttu-id="69963-112">**Метод**</span><span class="sxs-lookup"><span data-stu-id="69963-112">**Method**</span></span>|<span data-ttu-id="69963-113">**URI запроса**</span><span class="sxs-lookup"><span data-stu-id="69963-113">**Request URI**</span></span>|<span data-ttu-id="69963-114">**Версия HTTP**</span><span class="sxs-lookup"><span data-stu-id="69963-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="69963-115">Получить</span><span class="sxs-lookup"><span data-stu-id="69963-115">GET</span></span>  <br/> |<span data-ttu-id="69963-116">https://\<портала\>/QoERepositoryService/репозитория/пользователей / {userId} аудио- и настройка</span><span class="sxs-lookup"><span data-stu-id="69963-116">https://\<portal\>/QoERepositoryService/repository/user/{userId}/setting</span></span>  <br/> |<span data-ttu-id="69963-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="69963-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="69963-118">**Параметры URI**</span><span class="sxs-lookup"><span data-stu-id="69963-118">**URI Parameters**</span></span>
  
- <span data-ttu-id="69963-119">*эффективное* - необязательно.</span><span class="sxs-lookup"><span data-stu-id="69963-119">*effective*  - Optional.</span></span> <span data-ttu-id="69963-120">Этот параметр применяется только при использовании по умолчанию идентификатор определенного пользователя.</span><span class="sxs-lookup"><span data-stu-id="69963-120">This parameter applies only when the special user ID default is used.</span></span> <span data-ttu-id="69963-121">В других случаях он будет игнорироваться.</span><span class="sxs-lookup"><span data-stu-id="69963-121">In other cases, it will be ignored.</span></span> <span data-ttu-id="69963-122">`True`Возвращает параметры действующих пользователей и `false` возвращает только что пользовательских параметров (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="69963-122">`True` returns effective user settings and `false` returns just user settings (default).</span></span>
    
  <span data-ttu-id="69963-123">**Заголовки запроса** — без дополнительных заголовков.</span><span class="sxs-lookup"><span data-stu-id="69963-123">**Request Headers** - No additional headers.</span></span>
  
  <span data-ttu-id="69963-124">**Текст запроса** — нет.</span><span class="sxs-lookup"><span data-stu-id="69963-124">**Request Body** - None.</span></span>
  
  <span data-ttu-id="69963-125">**Ответа** - ответ включает код состояния HTTP и набор заголовков ответов.</span><span class="sxs-lookup"><span data-stu-id="69963-125">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
  <span data-ttu-id="69963-126">**Код состояния** - успешные операции возвращает код состояния 200 (ОК).</span><span class="sxs-lookup"><span data-stu-id="69963-126">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
  <span data-ttu-id="69963-127">**Заголовки ответа** — без дополнительных заголовков.</span><span class="sxs-lookup"><span data-stu-id="69963-127">**Response Headers** - No additional headers.</span></span>
  
  <span data-ttu-id="69963-128">**Тело ответа** - ниже приведен пример полезные данные ответа в формате JSON в.</span><span class="sxs-lookup"><span data-stu-id="69963-128">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```
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