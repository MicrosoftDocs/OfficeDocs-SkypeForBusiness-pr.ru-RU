---
title: Получение последних данных интеграции
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
ms.assetid: e7967dd9-0d6a-4a80-8b59-b8fc2e5615f8
description: Сводка. Сведения об операции "Получить последние данные интеграции", которая является частью API данных для панели мониторинга качества вызовов. Панель мониторинга качества звонков — это инструмент для Skype для бизнеса Server.
ms.openlocfilehash: c40041e41e04d2bdc62a9eb9fa1eb699697a5b3d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832519"
---
# <a name="get-last-integration-data"></a><span data-ttu-id="0b1e1-104">Получение последних данных интеграции</span><span class="sxs-lookup"><span data-stu-id="0b1e1-104">Get Last Integration Data</span></span>
 
<span data-ttu-id="0b1e1-105">**Сводка:** Сведения об операции "Получить данные последней интеграции", которая входит в API данных для панели мониторинга качества вызовов.</span><span class="sxs-lookup"><span data-stu-id="0b1e1-105">**Summary:** Learn about the Get Last Integration Data operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="0b1e1-106">Панель мониторинга качества звонков — это инструмент для Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="0b1e1-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="0b1e1-107">Операция "Получить последние данные интеграции" является частью API данных для панели мониторинга качества вызовов.</span><span class="sxs-lookup"><span data-stu-id="0b1e1-107">The Get Last Integration Data operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="get-last-integration-data"></a><span data-ttu-id="0b1e1-108">Получение последних данных интеграции</span><span class="sxs-lookup"><span data-stu-id="0b1e1-108">Get Last Integration Data</span></span>

<span data-ttu-id="0b1e1-109">Операция "Получить данные последней интеграции" возвращает список последних 5 успешных или неудачных операций архивации и обработки куба.</span><span class="sxs-lookup"><span data-stu-id="0b1e1-109">Get Last Integration Data operation returns the list of last 5 success/failure of archiving and cube processing.</span></span>
  
<span data-ttu-id="0b1e1-110">Эта функция отключена по умолчанию, и ее необходимо включить, настроив API данных.</span><span class="sxs-lookup"><span data-stu-id="0b1e1-110">This feature is disabled by default and it needs to be enabled by configuring the Data API.</span></span>
  

|<span data-ttu-id="0b1e1-111">**Способ**</span><span class="sxs-lookup"><span data-stu-id="0b1e1-111">**Method**</span></span>|<span data-ttu-id="0b1e1-112">**URI запроса**</span><span class="sxs-lookup"><span data-stu-id="0b1e1-112">**Request URI**</span></span>|<span data-ttu-id="0b1e1-113">**Версия HTTP**</span><span class="sxs-lookup"><span data-stu-id="0b1e1-113">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0b1e1-114">GET</span><span class="sxs-lookup"><span data-stu-id="0b1e1-114">GET</span></span>  <br/> |<span data-ttu-id="0b1e1-115">https:// \<portal\> /QoEDataService/IntegrationLog/Status</span><span class="sxs-lookup"><span data-stu-id="0b1e1-115">https://\<portal\>/QoEDataService/IntegrationLog/Status</span></span>  <br/> |<span data-ttu-id="0b1e1-116">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="0b1e1-116">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="0b1e1-117">**Параметры URI** — нет.</span><span class="sxs-lookup"><span data-stu-id="0b1e1-117">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="0b1e1-118">**Request Headers** - No additional headers.</span><span class="sxs-lookup"><span data-stu-id="0b1e1-118">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="0b1e1-119">**Тело запроса** — нет.</span><span class="sxs-lookup"><span data-stu-id="0b1e1-119">**Request Body** - None.</span></span>
  
 <span data-ttu-id="0b1e1-120">**Ответ.** Ответ включает код состояния HTTP и набор загодеров отклика.</span><span class="sxs-lookup"><span data-stu-id="0b1e1-120">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="0b1e1-121">**Код состояния** : успешная операция возвращает код состояния 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="0b1e1-121">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="0b1e1-122">**Response Headers** - No additional headers.</span><span class="sxs-lookup"><span data-stu-id="0b1e1-122">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="0b1e1-123">**Тело ответа** — ниже приведен пример состояния журнала.</span><span class="sxs-lookup"><span data-stu-id="0b1e1-123">**Response Body** - Below is a sample log status.</span></span>
  
```json
{
"LastSuccessIntegrations": ["01/18/2015 10:30:13",
"01/18/2015 10:28:29",
"01/17/2015 15:15:17",
"01/17/2015 15:00:17",
"01/17/2015 14:45:13"],
"LastSuccessCubeProcessings": ["01/17/2015 15:16:40",
"01/17/2015 15:01:41",
"01/17/2015 14:47:19",
"01/17/2015 14:31:40",
"01/17/2015 14:17:01"],
"LastFailedIntegrations":  ,
"LastFailedCubeProcessings": ["01/18/2015 10:30:58",
"01/18/2015 10:29:28",
"01/17/2015 10:02:20",
"01/15/2015 20:01:56",
"01/15/2015 19:45:50"],
"LastDataIntegrationStart": null,
"LastCubeProcessingStart": "01/18/2015 10:30:16"
}
```
