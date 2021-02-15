---
title: Получение элементов
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
ms.assetid: 9e189a48-4944-4f93-88d7-9d56b56770a6
description: Сводка. Сведения об операции "Получить элементы", которая входит в состав службы элементов. Служба элементов является частью API репозитория для панели мониторинга качества вызовов. Панель мониторинга качества звонков — это инструмент для Skype для бизнеса Server.
ms.openlocfilehash: 7da3ba77e782abe44896a7c1eb51a458d9a7e0b8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832539"
---
# <a name="get-items"></a><span data-ttu-id="1d491-105">Получение элементов</span><span class="sxs-lookup"><span data-stu-id="1d491-105">Get Items</span></span>
 
<span data-ttu-id="1d491-106">**Сводка:** Узнайте об операции "Получить элементы", которая входит в состав службы элементов.</span><span class="sxs-lookup"><span data-stu-id="1d491-106">**Summary:** Learn about the Get Items operation, which is part of the Item Service.</span></span> <span data-ttu-id="1d491-107">Служба элементов является частью API репозитория для панели мониторинга качества вызовов.</span><span class="sxs-lookup"><span data-stu-id="1d491-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="1d491-108">Панель мониторинга качества звонков — это инструмент для Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="1d491-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="1d491-109">Операция "Получить элементы" является частью службы элементов в API репозитория для панели мониторинга качества вызовов.</span><span class="sxs-lookup"><span data-stu-id="1d491-109">The Get Items operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-items"></a><span data-ttu-id="1d491-110">Получение элементов</span><span class="sxs-lookup"><span data-stu-id="1d491-110">Get Items</span></span>

<span data-ttu-id="1d491-111">При этом возвращаются все элементы в репозитории.</span><span class="sxs-lookup"><span data-stu-id="1d491-111">Get Items returns all Items in the repository.</span></span>
  
|<span data-ttu-id="1d491-112">**Способ**</span><span class="sxs-lookup"><span data-stu-id="1d491-112">**Method**</span></span>|<span data-ttu-id="1d491-113">**URI запроса**</span><span class="sxs-lookup"><span data-stu-id="1d491-113">**Request URI**</span></span>|<span data-ttu-id="1d491-114">**Версия HTTP**</span><span class="sxs-lookup"><span data-stu-id="1d491-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1d491-115">GET</span><span class="sxs-lookup"><span data-stu-id="1d491-115">GET</span></span>  <br/> |<span data-ttu-id="1d491-116">https:// \<portal\> /QoERepositoryService/repository/item</span><span class="sxs-lookup"><span data-stu-id="1d491-116">https://\<portal\>/QoERepositoryService/repository/item</span></span>  <br/> |<span data-ttu-id="1d491-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="1d491-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="1d491-118">**Параметры URI** — нет.</span><span class="sxs-lookup"><span data-stu-id="1d491-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="1d491-119">**Request Headers** - No additional headers.</span><span class="sxs-lookup"><span data-stu-id="1d491-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="1d491-120">**Тело запроса** — нет.</span><span class="sxs-lookup"><span data-stu-id="1d491-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="1d491-121">**Ответ.** Ответ включает код состояния HTTP и набор загодеров отклика.</span><span class="sxs-lookup"><span data-stu-id="1d491-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="1d491-122">**Код состояния** : успешная операция возвращает код состояния 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="1d491-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="1d491-123">**Response Headers** - No additional headers.</span><span class="sxs-lookup"><span data-stu-id="1d491-123">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="1d491-124">**Тело ответа.** Ниже приведен пример полезной нагрузки ответа в JSON.</span><span class="sxs-lookup"><span data-stu-id="1d491-124">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1d491-125">Возвращается массив объектов Item.</span><span class="sxs-lookup"><span data-stu-id="1d491-125">An array of Item objects is returned.</span></span> <span data-ttu-id="1d491-126">Подробные сведения об объекте Item см. в статье "Получить элемент".</span><span class="sxs-lookup"><span data-stu-id="1d491-126">For details about Item object, see Get Item.</span></span> 
  
```json
[{
"itemId": 1652,
"userId": 0,
"type": "application/json"
},
{
"itemId": 1653,
"userId": 0,
"type": "application/json"
},
{
"itemId": 1654,
"userId": 0,
"type": "application/json"
}]
```
