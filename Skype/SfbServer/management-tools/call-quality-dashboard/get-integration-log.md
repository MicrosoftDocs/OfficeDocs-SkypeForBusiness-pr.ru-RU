---
title: Получение журнала интеграции
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
ms.assetid: 8856f6bc-5460-4f35-acf2-f7662f01579b
description: Сводка. Сведения об операции "Получить журнал интеграции", которая входит в API данных для панели мониторинга качества вызовов. Панель мониторинга качества звонков — это инструмент для Skype для бизнеса Server.
ms.openlocfilehash: 69827fa9f3fd3f56843a41867b029a071799ba66
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832599"
---
# <a name="get-integration-log"></a><span data-ttu-id="486ce-104">Получение журнала интеграции</span><span class="sxs-lookup"><span data-stu-id="486ce-104">Get Integration Log</span></span>
 
<span data-ttu-id="486ce-105">**Сводка:** Сведения об операции "Получить журнал интеграции", которая входит в API данных для панели мониторинга качества вызовов.</span><span class="sxs-lookup"><span data-stu-id="486ce-105">**Summary:** Learn about the Get Integration Log operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="486ce-106">Панель мониторинга качества звонков — это инструмент для Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="486ce-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="486ce-107">Операция "Получить журнал интеграции" является частью API данных для панели мониторинга качества вызовов</span><span class="sxs-lookup"><span data-stu-id="486ce-107">The Get Integration Log operation is part of the Data API for Call Quality Dashboard</span></span>
  
## <a name="get-integration-log"></a><span data-ttu-id="486ce-108">Получение журнала интеграции</span><span class="sxs-lookup"><span data-stu-id="486ce-108">Get Integration Log</span></span>

<span data-ttu-id="486ce-109">Операция "Получить журнал интеграции" возвращает список записей журнала, описывающих действия в обработке куба QoE.</span><span class="sxs-lookup"><span data-stu-id="486ce-109">Get Integration Log operation returns a list of log entries describing the activities in QoE Cube processing.</span></span>
  
<span data-ttu-id="486ce-110">По умолчанию эта операция отключена из соображений безопасности.</span><span class="sxs-lookup"><span data-stu-id="486ce-110">This operation is disabled by default for security reasons.</span></span> <span data-ttu-id="486ce-111">При отключке возвращается пустая строка.</span><span class="sxs-lookup"><span data-stu-id="486ce-111">When disabled, it returns an empty string.</span></span> <span data-ttu-id="486ce-112">Чтобы включить эту операцию, администраторам необходимо настроить web.config для хост-веб-приложения API данных.</span><span class="sxs-lookup"><span data-stu-id="486ce-112">To enable this operation, administrators need to configure the web.config for Data API's host web application.</span></span>
  

|<span data-ttu-id="486ce-113">Метод</span><span class="sxs-lookup"><span data-stu-id="486ce-113">Method</span></span>|<span data-ttu-id="486ce-114">**URI запроса**</span><span class="sxs-lookup"><span data-stu-id="486ce-114">**Request URI**</span></span>|<span data-ttu-id="486ce-115">**Версия HTTP**</span><span class="sxs-lookup"><span data-stu-id="486ce-115">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="486ce-116">GET</span><span class="sxs-lookup"><span data-stu-id="486ce-116">GET</span></span>  <br/> |<span data-ttu-id="486ce-117">https:// \<portal\> /QoEDataService/IntegrationLog</span><span class="sxs-lookup"><span data-stu-id="486ce-117">https://\<portal\>/QoEDataService/IntegrationLog</span></span>  <br/> |<span data-ttu-id="486ce-118">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="486ce-118">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="486ce-119">**Параметры URI** — нет.</span><span class="sxs-lookup"><span data-stu-id="486ce-119">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="486ce-120">**Request Headers** - No additional headers.</span><span class="sxs-lookup"><span data-stu-id="486ce-120">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="486ce-121">**Тело запроса** — нет.</span><span class="sxs-lookup"><span data-stu-id="486ce-121">**Request Body** - None.</span></span>
  
 <span data-ttu-id="486ce-122">**Ответ.** Ответ включает код состояния HTTP и набор загодеров отклика.</span><span class="sxs-lookup"><span data-stu-id="486ce-122">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="486ce-123">**Код состояния** — успешная операция возвращает код состояния 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="486ce-123">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="486ce-124">**Response Headers** - No additional headers.</span><span class="sxs-lookup"><span data-stu-id="486ce-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="486ce-125">**Тело ответа** . Ниже приведен пример структуры записей журнала.</span><span class="sxs-lookup"><span data-stu-id="486ce-125">**Response Body** - Below is a sample structure of log entries.</span></span>
  
```json
[
{"LogCategory":"<category>","LogTime":"2015-03-18T10:28:29.10","LogDescription":"<log description>"}
]
```


