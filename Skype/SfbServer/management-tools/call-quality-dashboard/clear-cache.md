---
title: Очистка кэша
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
ms.assetid: 08648b16-7a64-41d8-9577-5000a20fce46
description: Сводка. Сведения об операции очистки кэша, которая входит в API данных для панели мониторинга качества вызовов. Панель мониторинга качества звонков — это инструмент для Skype для бизнеса Server.
ms.openlocfilehash: c9b966bb1e35a5a6255cd75ea6c685daaf220a09
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806419"
---
# <a name="clear-cache"></a><span data-ttu-id="6d12a-104">Очистка кэша</span><span class="sxs-lookup"><span data-stu-id="6d12a-104">Clear Cache</span></span>
 
<span data-ttu-id="6d12a-105">**Сводка:** Сведения об операции "Очистить кэш", которая входит в API данных для панели мониторинга качества вызовов.</span><span class="sxs-lookup"><span data-stu-id="6d12a-105">**Summary:** Learn about the Clear Cache operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="6d12a-106">Панель мониторинга качества звонков — это инструмент для Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="6d12a-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="6d12a-107">Операция "Очистить кэш" является частью API данных для панели мониторинга качества вызовов.</span><span class="sxs-lookup"><span data-stu-id="6d12a-107">The Clear Cache operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="clear-cache"></a><span data-ttu-id="6d12a-108">Очистка кэша</span><span class="sxs-lookup"><span data-stu-id="6d12a-108">Clear Cache</span></span>

<span data-ttu-id="6d12a-109">Операция очистки кэша удаляет кэш на сервере для запросов и данных.</span><span class="sxs-lookup"><span data-stu-id="6d12a-109">Clear Cache operation deletes the cache on server for queries and data.</span></span> <span data-ttu-id="6d12a-110">После этого будет сброшен кэш, и мы будем получать новые данные из куба QoE для новых запросов.</span><span class="sxs-lookup"><span data-stu-id="6d12a-110">This will reset the cache and we will get fresh data from QoE Cube afterward for new requests.</span></span>
  

|<span data-ttu-id="6d12a-111">**Способ**</span><span class="sxs-lookup"><span data-stu-id="6d12a-111">**Method**</span></span>|<span data-ttu-id="6d12a-112">**URI запроса**</span><span class="sxs-lookup"><span data-stu-id="6d12a-112">**Request URI**</span></span>|<span data-ttu-id="6d12a-113">**Версия HTTP**</span><span class="sxs-lookup"><span data-stu-id="6d12a-113">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6d12a-114">POST</span><span class="sxs-lookup"><span data-stu-id="6d12a-114">POST</span></span>  <br/> |<span data-ttu-id="6d12a-115">https:// \<portal\> /QoEDataService/ClearCache</span><span class="sxs-lookup"><span data-stu-id="6d12a-115">https://\<portal\>/QoEDataService/ClearCache</span></span>  <br/> |<span data-ttu-id="6d12a-116">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="6d12a-116">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="6d12a-117">**Параметры URI** — нет.</span><span class="sxs-lookup"><span data-stu-id="6d12a-117">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="6d12a-118">**Request Headers** - No additional headers.</span><span class="sxs-lookup"><span data-stu-id="6d12a-118">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="6d12a-119">**Тело запроса** — нет.</span><span class="sxs-lookup"><span data-stu-id="6d12a-119">**Request Body** - None.</span></span>
  
 <span data-ttu-id="6d12a-120">**Ответ.** Ответ включает код состояния HTTP и набор загодеров отклика.</span><span class="sxs-lookup"><span data-stu-id="6d12a-120">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="6d12a-121">**Код состояния** — успешная операция возвращает код состояния 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="6d12a-121">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="6d12a-122">**Response Headers** - No additional headers.</span><span class="sxs-lookup"><span data-stu-id="6d12a-122">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="6d12a-123">**Тело ответа** — нет.</span><span class="sxs-lookup"><span data-stu-id="6d12a-123">**Response Body** - None.</span></span>
  

