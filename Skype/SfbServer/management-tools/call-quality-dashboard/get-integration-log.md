---
title: Получение журнала интеграции
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 8856f6bc-5460-4f35-acf2-f7662f01579b
description: 'Сводка: сведения о операции получения журнала интеграции, которая входит в API данных для панели мониторинга качества звонков. Панель мониторинга качества звонков — это средство для Skype для бизнеса Server.'
ms.openlocfilehash: 9caa909e80a0bab5257af16fe77e9d154947a56e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816818"
---
# <a name="get-integration-log"></a><span data-ttu-id="cb21a-104">Получение журнала интеграции</span><span class="sxs-lookup"><span data-stu-id="cb21a-104">Get Integration Log</span></span>
 
<span data-ttu-id="cb21a-105">**Сводка:** Узнайте о том, как получить журнал интеграции, являющийся частью API данных для панели мониторинга качества звонков.</span><span class="sxs-lookup"><span data-stu-id="cb21a-105">**Summary:** Learn about the Get Integration Log operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="cb21a-106">Панель мониторинга качества звонков — это средство для Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="cb21a-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="cb21a-107">Операция "получить журнал интеграции" входит в API данных для панели мониторинга качества звонков</span><span class="sxs-lookup"><span data-stu-id="cb21a-107">The Get Integration Log operation is part of the Data API for Call Quality Dashboard</span></span>
  
## <a name="get-integration-log"></a><span data-ttu-id="cb21a-108">Получение журнала интеграции</span><span class="sxs-lookup"><span data-stu-id="cb21a-108">Get Integration Log</span></span>

<span data-ttu-id="cb21a-109">Операция Get Integration log возвращает список записей журнала, описывающих действия в обработке куба QoE.</span><span class="sxs-lookup"><span data-stu-id="cb21a-109">Get Integration Log operation returns a list of log entries describing the activities in QoE Cube processing.</span></span>
  
<span data-ttu-id="cb21a-110">По соображениям безопасности эта операция отключена по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="cb21a-110">This operation is disabled by default for security reasons.</span></span> <span data-ttu-id="cb21a-111">При отключении функция возвращает пустую строку.</span><span class="sxs-lookup"><span data-stu-id="cb21a-111">When disabled, it returns an empty string.</span></span> <span data-ttu-id="cb21a-112">Для включения этой операции администраторам необходимо настроить ведущее веб-приложение API для данных Web. config.</span><span class="sxs-lookup"><span data-stu-id="cb21a-112">To enable this operation, administrators need to configure the web.config for Data API's host web application.</span></span>
  

|<span data-ttu-id="cb21a-113">Способов</span><span class="sxs-lookup"><span data-stu-id="cb21a-113">Method</span></span>|<span data-ttu-id="cb21a-114">**URI запроса**</span><span class="sxs-lookup"><span data-stu-id="cb21a-114">**Request URI**</span></span>|<span data-ttu-id="cb21a-115">**Версия HTTP**</span><span class="sxs-lookup"><span data-stu-id="cb21a-115">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="cb21a-116">Получить</span><span class="sxs-lookup"><span data-stu-id="cb21a-116">GET</span></span>  <br/> |<span data-ttu-id="cb21a-117">/Коедатасервице/интегратионлог\<портала\>HTTPS://</span><span class="sxs-lookup"><span data-stu-id="cb21a-117">https://\<portal\>/QoEDataService/IntegrationLog</span></span>  <br/> |<span data-ttu-id="cb21a-118">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="cb21a-118">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="cb21a-119">**Параметры универсального кода ресурса** (None).</span><span class="sxs-lookup"><span data-stu-id="cb21a-119">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="cb21a-120">**Заголовки запроса** — без дополнительных заголовков.</span><span class="sxs-lookup"><span data-stu-id="cb21a-120">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="cb21a-121">**Запросить текст** -None.</span><span class="sxs-lookup"><span data-stu-id="cb21a-121">**Request Body** - None.</span></span>
  
 <span data-ttu-id="cb21a-122">**Response (ответ** ) — ответ включает код состояния HTTP и набор заголовков ответа.</span><span class="sxs-lookup"><span data-stu-id="cb21a-122">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="cb21a-123">**Код состояния** — успешная операция возвращает код состояния 200 (ОК).</span><span class="sxs-lookup"><span data-stu-id="cb21a-123">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="cb21a-124">**Заголовки ответа** — без дополнительных заголовков.</span><span class="sxs-lookup"><span data-stu-id="cb21a-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="cb21a-125">**Текст ответа** — ниже показан пример структуры записей журнала.</span><span class="sxs-lookup"><span data-stu-id="cb21a-125">**Response Body** - Below is a sample structure of log entries.</span></span>
  
```
[
{"LogCategory":"<category>","LogTime":"2015-03-18T10:28:29.10","LogDescription":"<log description>"}
]
```


