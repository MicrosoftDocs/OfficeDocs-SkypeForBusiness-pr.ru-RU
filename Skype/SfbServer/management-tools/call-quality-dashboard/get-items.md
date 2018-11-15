---
title: Получение элементов
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 9e189a48-4944-4f93-88d7-9d56b56770a6
description: 'Сводка: Сведения об операции Получение элементов, который является частью службы элемента. Служба элемент является частью API репозитория для панели мониторинга качества звонков. Панель мониторинга качества звонков — это средство для Скайп для Business Server.'
ms.openlocfilehash: d3b0812232b25b412a23dba3a7270eda5a01077b
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/15/2018
ms.locfileid: "26531387"
---
# <a name="get-items"></a><span data-ttu-id="a01e3-105">Получение элементов</span><span class="sxs-lookup"><span data-stu-id="a01e3-105">Get Items</span></span>
 
<span data-ttu-id="a01e3-106">**Сводка:** Сведения об операции Получение элементов, который является частью службы элемента.</span><span class="sxs-lookup"><span data-stu-id="a01e3-106">**Summary:** Learn about the Get Items operation, which is part of the Item Service.</span></span> <span data-ttu-id="a01e3-107">Служба элемент является частью API репозитория для панели мониторинга качества звонков.</span><span class="sxs-lookup"><span data-stu-id="a01e3-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="a01e3-108">Панель мониторинга качества звонков — это средство для Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="a01e3-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="a01e3-109">Получение элементов операции является частью службы элемента в API репозитория для панели мониторинга качества звонков.</span><span class="sxs-lookup"><span data-stu-id="a01e3-109">The Get Items operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-items"></a><span data-ttu-id="a01e3-110">Получение элементов</span><span class="sxs-lookup"><span data-stu-id="a01e3-110">Get Items</span></span>

<span data-ttu-id="a01e3-111">Получение элементов возвращает все элементы в репозитории.</span><span class="sxs-lookup"><span data-stu-id="a01e3-111">Get Items returns all Items in the repository.</span></span>
  
|<span data-ttu-id="a01e3-112">**Метод**</span><span class="sxs-lookup"><span data-stu-id="a01e3-112">**Method**</span></span>|<span data-ttu-id="a01e3-113">**URI запроса**</span><span class="sxs-lookup"><span data-stu-id="a01e3-113">**Request URI**</span></span>|<span data-ttu-id="a01e3-114">**Версия HTTP**</span><span class="sxs-lookup"><span data-stu-id="a01e3-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a01e3-115">Получить</span><span class="sxs-lookup"><span data-stu-id="a01e3-115">GET</span></span>  <br/> |<span data-ttu-id="a01e3-116">https://\<портала\>/QoERepositoryService/repository/item</span><span class="sxs-lookup"><span data-stu-id="a01e3-116">https://\<portal\>/QoERepositoryService/repository/item</span></span>  <br/> |<span data-ttu-id="a01e3-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="a01e3-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="a01e3-118">**Параметры URI** — нет.</span><span class="sxs-lookup"><span data-stu-id="a01e3-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="a01e3-119">**Заголовки запроса** — без дополнительных заголовков.</span><span class="sxs-lookup"><span data-stu-id="a01e3-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="a01e3-120">**Текст запроса** — нет.</span><span class="sxs-lookup"><span data-stu-id="a01e3-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="a01e3-121">**Ответа** - ответ включает код состояния HTTP и набор заголовков ответов.</span><span class="sxs-lookup"><span data-stu-id="a01e3-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="a01e3-122">**Код состояния** - успешные операции возвращает код состояния 200 (ОК).</span><span class="sxs-lookup"><span data-stu-id="a01e3-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="a01e3-123">**Заголовки ответа** — без дополнительных заголовков.</span><span class="sxs-lookup"><span data-stu-id="a01e3-123">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="a01e3-124">**Тело ответа** - ниже приведен пример полезные данные ответа в формате JSON в.</span><span class="sxs-lookup"><span data-stu-id="a01e3-124">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a01e3-125">Возвращает массив объектов элементов.</span><span class="sxs-lookup"><span data-stu-id="a01e3-125">An array of Item objects is returned.</span></span> <span data-ttu-id="a01e3-126">Для получения дополнительных сведений об объекте элемента видите Получение элемента.</span><span class="sxs-lookup"><span data-stu-id="a01e3-126">For details about Item object, see Get Item.</span></span> 
  
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