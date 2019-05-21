---
title: Очистка кэша
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 08648b16-7a64-41d8-9577-5000a20fce46
description: 'Сводка: сведения об операции очистки кэша, которая входит в API данных для панели мониторинга качества звонков. Панель мониторинга качества звонков — это средство для Skype для бизнеса Server.'
ms.openlocfilehash: 38648e1a910f93a30bd6da8807321acad0330e62
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274837"
---
# <a name="clear-cache"></a><span data-ttu-id="a4373-104">Очистка кэша</span><span class="sxs-lookup"><span data-stu-id="a4373-104">Clear Cache</span></span>
 
<span data-ttu-id="a4373-105">**Сводка:** Сведения о операции очистки кэша, которая входит в API данных для панели мониторинга качества звонков.</span><span class="sxs-lookup"><span data-stu-id="a4373-105">**Summary:** Learn about the Clear Cache operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="a4373-106">Панель мониторинга качества звонков — это средство для Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="a4373-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="a4373-107">Операция очистки кэша — это часть API данных для панели мониторинга качества звонков.</span><span class="sxs-lookup"><span data-stu-id="a4373-107">The Clear Cache operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="clear-cache"></a><span data-ttu-id="a4373-108">Очистка кэша</span><span class="sxs-lookup"><span data-stu-id="a4373-108">Clear Cache</span></span>

<span data-ttu-id="a4373-109">Операция очистки кэша удаляет кэш на сервере для запросов и данных.</span><span class="sxs-lookup"><span data-stu-id="a4373-109">Clear Cache operation deletes the cache on server for queries and data.</span></span> <span data-ttu-id="a4373-110">Это приведет к сбросу кэша, и мы постараемся получать новые данные из куба QoE для новых запросов.</span><span class="sxs-lookup"><span data-stu-id="a4373-110">This will reset the cache and we will get fresh data from QoE Cube afterward for new requests.</span></span>
  

|<span data-ttu-id="a4373-111">**Способов**</span><span class="sxs-lookup"><span data-stu-id="a4373-111">**Method**</span></span>|<span data-ttu-id="a4373-112">**URI запроса**</span><span class="sxs-lookup"><span data-stu-id="a4373-112">**Request URI**</span></span>|<span data-ttu-id="a4373-113">**Версия HTTP**</span><span class="sxs-lookup"><span data-stu-id="a4373-113">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a4373-114">Поместить</span><span class="sxs-lookup"><span data-stu-id="a4373-114">POST</span></span>  <br/> |<span data-ttu-id="a4373-115">/Коедатасервице/клеаркаче\<портала\>HTTPS://</span><span class="sxs-lookup"><span data-stu-id="a4373-115">https://\<portal\>/QoEDataService/ClearCache</span></span>  <br/> |<span data-ttu-id="a4373-116">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="a4373-116">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="a4373-117">**Параметры универсального кода ресурса** (None).</span><span class="sxs-lookup"><span data-stu-id="a4373-117">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="a4373-118">**Заголовки запроса** — без дополнительных заголовков.</span><span class="sxs-lookup"><span data-stu-id="a4373-118">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="a4373-119">**Запросить текст** -None.</span><span class="sxs-lookup"><span data-stu-id="a4373-119">**Request Body** - None.</span></span>
  
 <span data-ttu-id="a4373-120">**Response (ответ** ) — ответ включает код состояния HTTP и набор заголовков ответа.</span><span class="sxs-lookup"><span data-stu-id="a4373-120">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="a4373-121">**Код состояния** — успешная операция возвращает код состояния 200 (ОК).</span><span class="sxs-lookup"><span data-stu-id="a4373-121">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="a4373-122">**Заголовки ответа** — без дополнительных заголовков.</span><span class="sxs-lookup"><span data-stu-id="a4373-122">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="a4373-123">**Текст ответа** — None (нет).</span><span class="sxs-lookup"><span data-stu-id="a4373-123">**Response Body** - None.</span></span>
  

