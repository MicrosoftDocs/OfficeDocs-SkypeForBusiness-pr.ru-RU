---
title: Очистить кэш
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 08648b16-7a64-41d8-9577-5000a20fce46
description: 'Сводка: Сведения об операции очистить кэш, который является частью API данных для панели мониторинга качества звонков. Панель мониторинга качества звонков — это средство для Скайп для Business Server.'
ms.openlocfilehash: 745fdff57843c42ebf55c1caee011d4b7f4ed250
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/15/2018
ms.locfileid: "26531290"
---
# <a name="clear-cache"></a><span data-ttu-id="f344a-104">Очистить кэш</span><span class="sxs-lookup"><span data-stu-id="f344a-104">Clear Cache</span></span>
 
<span data-ttu-id="f344a-105">**Сводка:** Сведения об операции очистить кэш, который является частью API данных для панели мониторинга качества звонков.</span><span class="sxs-lookup"><span data-stu-id="f344a-105">**Summary:** Learn about the Clear Cache operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="f344a-106">Панель мониторинга качества звонков — это средство для Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="f344a-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="f344a-107">Очистить кэш операция является частью API данных для панели мониторинга качества звонков.</span><span class="sxs-lookup"><span data-stu-id="f344a-107">The Clear Cache operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="clear-cache"></a><span data-ttu-id="f344a-108">Очистить кэш</span><span class="sxs-lookup"><span data-stu-id="f344a-108">Clear Cache</span></span>

<span data-ttu-id="f344a-109">Операция очистки кэша удаляет кэш на сервере для запросов и данных.</span><span class="sxs-lookup"><span data-stu-id="f344a-109">Clear Cache operation deletes the cache on server for queries and data.</span></span> <span data-ttu-id="f344a-110">Эта команда сбросит кэша и мы получите новые данные из куба качества взаимодействия впоследствии для новых запросов.</span><span class="sxs-lookup"><span data-stu-id="f344a-110">This will reset the cache and we will get fresh data from QoE Cube afterward for new requests.</span></span>
  

|<span data-ttu-id="f344a-111">**Метод**</span><span class="sxs-lookup"><span data-stu-id="f344a-111">**Method**</span></span>|<span data-ttu-id="f344a-112">**URI запроса**</span><span class="sxs-lookup"><span data-stu-id="f344a-112">**Request URI**</span></span>|<span data-ttu-id="f344a-113">**Версия HTTP**</span><span class="sxs-lookup"><span data-stu-id="f344a-113">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f344a-114">Поместить</span><span class="sxs-lookup"><span data-stu-id="f344a-114">POST</span></span>  <br/> |<span data-ttu-id="f344a-115">https://\<портала\>/QoEDataService/ClearCache</span><span class="sxs-lookup"><span data-stu-id="f344a-115">https://\<portal\>/QoEDataService/ClearCache</span></span>  <br/> |<span data-ttu-id="f344a-116">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="f344a-116">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="f344a-117">**Параметры URI** — нет.</span><span class="sxs-lookup"><span data-stu-id="f344a-117">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="f344a-118">**Заголовки запроса** — без дополнительных заголовков.</span><span class="sxs-lookup"><span data-stu-id="f344a-118">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="f344a-119">**Текст запроса** — нет.</span><span class="sxs-lookup"><span data-stu-id="f344a-119">**Request Body** - None.</span></span>
  
 <span data-ttu-id="f344a-120">**Ответа** - ответ включает код состояния HTTP и набор заголовков ответов.</span><span class="sxs-lookup"><span data-stu-id="f344a-120">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="f344a-121">**Код состояния** - успешные операции возвращает код состояния 200 (ОК).</span><span class="sxs-lookup"><span data-stu-id="f344a-121">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="f344a-122">**Заголовки ответа** — без дополнительных заголовков.</span><span class="sxs-lookup"><span data-stu-id="f344a-122">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="f344a-123">**Тело ответа** — нет.</span><span class="sxs-lookup"><span data-stu-id="f344a-123">**Response Body** - None.</span></span>
  

