---
title: Получение элементов
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 9e189a48-4944-4f93-88d7-9d56b56770a6
description: 'Сводка: сведения об операции "получение элементов", которая входит в состав службы номенклатур. Служба item входит в API репозитория для панели мониторинга качества звонков. Панель мониторинга качества звонков — это средство для Skype для бизнеса Server.'
ms.openlocfilehash: be93e16750c1a977a6bc3cfc9651e78a043ef563
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992666"
---
# <a name="get-items"></a><span data-ttu-id="4280b-105">Получение элементов</span><span class="sxs-lookup"><span data-stu-id="4280b-105">Get Items</span></span>
 
<span data-ttu-id="4280b-106">**Сводка:** Сведения об операции "получение элементов", которая входит в состав службы номенклатур.</span><span class="sxs-lookup"><span data-stu-id="4280b-106">**Summary:** Learn about the Get Items operation, which is part of the Item Service.</span></span> <span data-ttu-id="4280b-107">Служба item входит в API репозитория для панели мониторинга качества звонков.</span><span class="sxs-lookup"><span data-stu-id="4280b-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="4280b-108">Панель мониторинга качества звонков — это средство для Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="4280b-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="4280b-109">Операция "получить элементы" является частью службы элементов в API репозитория для панели мониторинга качества звонков.</span><span class="sxs-lookup"><span data-stu-id="4280b-109">The Get Items operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-items"></a><span data-ttu-id="4280b-110">Получение элементов</span><span class="sxs-lookup"><span data-stu-id="4280b-110">Get Items</span></span>

<span data-ttu-id="4280b-111">Функция Get Items возвращает все элементы в репозитории.</span><span class="sxs-lookup"><span data-stu-id="4280b-111">Get Items returns all Items in the repository.</span></span>
  
|<span data-ttu-id="4280b-112">**Способов**</span><span class="sxs-lookup"><span data-stu-id="4280b-112">**Method**</span></span>|<span data-ttu-id="4280b-113">**URI запроса**</span><span class="sxs-lookup"><span data-stu-id="4280b-113">**Request URI**</span></span>|<span data-ttu-id="4280b-114">**Версия HTTP**</span><span class="sxs-lookup"><span data-stu-id="4280b-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="4280b-115">Получить</span><span class="sxs-lookup"><span data-stu-id="4280b-115">GET</span></span>  <br/> |<span data-ttu-id="4280b-116">/Коерепоситорисервице/репоситори/итем\<портала\>HTTPS://</span><span class="sxs-lookup"><span data-stu-id="4280b-116">https://\<portal\>/QoERepositoryService/repository/item</span></span>  <br/> |<span data-ttu-id="4280b-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="4280b-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="4280b-118">**Параметры универсального кода ресурса** (None).</span><span class="sxs-lookup"><span data-stu-id="4280b-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="4280b-119">**Заголовки запроса** — без дополнительных заголовков.</span><span class="sxs-lookup"><span data-stu-id="4280b-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="4280b-120">**Запросить текст** -None.</span><span class="sxs-lookup"><span data-stu-id="4280b-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="4280b-121">**Response (ответ** ) — ответ включает код состояния HTTP и набор заголовков ответа.</span><span class="sxs-lookup"><span data-stu-id="4280b-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="4280b-122">**Код состояния** — успешная операция возвращает код состояния 200 (ОК).</span><span class="sxs-lookup"><span data-stu-id="4280b-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="4280b-123">**Заголовки ответа** — без дополнительных заголовков.</span><span class="sxs-lookup"><span data-stu-id="4280b-123">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="4280b-124">**Тело ответа** — ниже показан пример полезных данных ответа в JSON.</span><span class="sxs-lookup"><span data-stu-id="4280b-124">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4280b-125">Возвращается массив объектов элементов.</span><span class="sxs-lookup"><span data-stu-id="4280b-125">An array of Item objects is returned.</span></span> <span data-ttu-id="4280b-126">Подробнее об объекте Item можно найти в разделе Получение элемента.</span><span class="sxs-lookup"><span data-stu-id="4280b-126">For details about Item object, see Get Item.</span></span> 
  
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
