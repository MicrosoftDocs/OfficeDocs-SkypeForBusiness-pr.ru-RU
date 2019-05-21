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
ms.openlocfilehash: a1e7e8525df77cd5aacafb6d41316a985fbe9694
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274704"
---
# <a name="get-items"></a><span data-ttu-id="82287-105">Получение элементов</span><span class="sxs-lookup"><span data-stu-id="82287-105">Get Items</span></span>
 
<span data-ttu-id="82287-106">**Сводка:** Сведения об операции "получение элементов", которая входит в состав службы номенклатур.</span><span class="sxs-lookup"><span data-stu-id="82287-106">**Summary:** Learn about the Get Items operation, which is part of the Item Service.</span></span> <span data-ttu-id="82287-107">Служба item входит в API репозитория для панели мониторинга качества звонков.</span><span class="sxs-lookup"><span data-stu-id="82287-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="82287-108">Панель мониторинга качества звонков — это средство для Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="82287-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="82287-109">Операция "получить элементы" является частью службы элементов в API репозитория для панели мониторинга качества звонков.</span><span class="sxs-lookup"><span data-stu-id="82287-109">The Get Items operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-items"></a><span data-ttu-id="82287-110">Получение элементов</span><span class="sxs-lookup"><span data-stu-id="82287-110">Get Items</span></span>

<span data-ttu-id="82287-111">Функция Get Items возвращает все элементы в репозитории.</span><span class="sxs-lookup"><span data-stu-id="82287-111">Get Items returns all Items in the repository.</span></span>
  
|<span data-ttu-id="82287-112">**Способов**</span><span class="sxs-lookup"><span data-stu-id="82287-112">**Method**</span></span>|<span data-ttu-id="82287-113">**URI запроса**</span><span class="sxs-lookup"><span data-stu-id="82287-113">**Request URI**</span></span>|<span data-ttu-id="82287-114">**Версия HTTP**</span><span class="sxs-lookup"><span data-stu-id="82287-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="82287-115">Получить</span><span class="sxs-lookup"><span data-stu-id="82287-115">GET</span></span>  <br/> |<span data-ttu-id="82287-116">/Коерепоситорисервице/репоситори/итем\<портала\>HTTPS://</span><span class="sxs-lookup"><span data-stu-id="82287-116">https://\<portal\>/QoERepositoryService/repository/item</span></span>  <br/> |<span data-ttu-id="82287-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="82287-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="82287-118">**Параметры универсального кода ресурса** (None).</span><span class="sxs-lookup"><span data-stu-id="82287-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="82287-119">**Заголовки запроса** — без дополнительных заголовков.</span><span class="sxs-lookup"><span data-stu-id="82287-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="82287-120">**Запросить текст** -None.</span><span class="sxs-lookup"><span data-stu-id="82287-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="82287-121">**Response (ответ** ) — ответ включает код состояния HTTP и набор заголовков ответа.</span><span class="sxs-lookup"><span data-stu-id="82287-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="82287-122">**Код состояния** — успешная операция возвращает код состояния 200 (ОК).</span><span class="sxs-lookup"><span data-stu-id="82287-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="82287-123">**Заголовки ответа** — без дополнительных заголовков.</span><span class="sxs-lookup"><span data-stu-id="82287-123">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="82287-124">**Тело ответа** — ниже показан пример полезных данных ответа в JSON.</span><span class="sxs-lookup"><span data-stu-id="82287-124">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="82287-125">Возвращается массив объектов элементов.</span><span class="sxs-lookup"><span data-stu-id="82287-125">An array of Item objects is returned.</span></span> <span data-ttu-id="82287-126">Подробнее об объекте Item можно найти в разделе Получение элемента.</span><span class="sxs-lookup"><span data-stu-id="82287-126">For details about Item object, see Get Item.</span></span> 
  
```
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
