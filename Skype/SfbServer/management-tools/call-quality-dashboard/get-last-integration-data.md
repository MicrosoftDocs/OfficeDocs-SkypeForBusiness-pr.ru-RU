---
title: Получение последних данных интеграции
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: e7967dd9-0d6a-4a80-8b59-b8fc2e5615f8
description: 'Сводка: Сведения о операции получения последнего интеграции данных, которая является частью API данных для панели мониторинга качества звонков. Панель мониторинга качества звонков — это средство для Скайп для Business Server.'
ms.openlocfilehash: 22a7382bfd861b3cade606cd087e17c007fb947b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930688"
---
# <a name="get-last-integration-data"></a><span data-ttu-id="38d03-104">Получение последних данных интеграции</span><span class="sxs-lookup"><span data-stu-id="38d03-104">Get Last Integration Data</span></span>
 
<span data-ttu-id="38d03-105">**Сводка:** Узнайте о операции получения последнего интеграции данных, которая является частью API данных для панели мониторинга качества звонков.</span><span class="sxs-lookup"><span data-stu-id="38d03-105">**Summary:** Learn about the Get Last Integration Data operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="38d03-106">Панель мониторинга качества звонков — это средство для Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="38d03-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="38d03-107">Операция получения последнего интеграции данных является частью API данных для панели мониторинга качества звонков.</span><span class="sxs-lookup"><span data-stu-id="38d03-107">The Get Last Integration Data operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="get-last-integration-data"></a><span data-ttu-id="38d03-108">Получение последних данных интеграции</span><span class="sxs-lookup"><span data-stu-id="38d03-108">Get Last Integration Data</span></span>

<span data-ttu-id="38d03-109">Операции получения последнего интеграции данных возвращает список последних 5 успеха/сбой системы архивации и обработки куба.</span><span class="sxs-lookup"><span data-stu-id="38d03-109">Get Last Integration Data operation returns the list of last 5 success/failure of archiving and cube processing.</span></span>
  
<span data-ttu-id="38d03-110">По умолчанию эта функция отключена и его необходимо включить, настроив Data API.</span><span class="sxs-lookup"><span data-stu-id="38d03-110">This feature is disabled by default and it needs to be enabled by configuring the Data API.</span></span>
  

|<span data-ttu-id="38d03-111">**Метод**</span><span class="sxs-lookup"><span data-stu-id="38d03-111">**Method**</span></span>|<span data-ttu-id="38d03-112">**URI запроса**</span><span class="sxs-lookup"><span data-stu-id="38d03-112">**Request URI**</span></span>|<span data-ttu-id="38d03-113">**Версия HTTP**</span><span class="sxs-lookup"><span data-stu-id="38d03-113">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="38d03-114">Получить</span><span class="sxs-lookup"><span data-stu-id="38d03-114">GET</span></span>  <br/> |<span data-ttu-id="38d03-115">https://\<портала\>/QoEDataService/IntegrationLog/Status</span><span class="sxs-lookup"><span data-stu-id="38d03-115">https://\<portal\>/QoEDataService/IntegrationLog/Status</span></span>  <br/> |<span data-ttu-id="38d03-116">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="38d03-116">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="38d03-117">**Параметры URI** — нет.</span><span class="sxs-lookup"><span data-stu-id="38d03-117">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="38d03-118">**Заголовки запроса** — без дополнительных заголовков.</span><span class="sxs-lookup"><span data-stu-id="38d03-118">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="38d03-119">**Текст запроса** — нет.</span><span class="sxs-lookup"><span data-stu-id="38d03-119">**Request Body** - None.</span></span>
  
 <span data-ttu-id="38d03-120">**Ответа** - ответ включает код состояния HTTP и набор заголовков ответов.</span><span class="sxs-lookup"><span data-stu-id="38d03-120">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="38d03-121">**Код состояния** - успешные операции возвращает код состояния 200 (ОК).</span><span class="sxs-lookup"><span data-stu-id="38d03-121">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="38d03-122">**Заголовки ответа** — без дополнительных заголовков.</span><span class="sxs-lookup"><span data-stu-id="38d03-122">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="38d03-123">**Тело ответа** - ниже приведена в состоянии пример журнала.</span><span class="sxs-lookup"><span data-stu-id="38d03-123">**Response Body** - Below is a sample log status.</span></span>
  
```
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
