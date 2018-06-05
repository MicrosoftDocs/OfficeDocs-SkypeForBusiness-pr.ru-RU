---
title: Получение журнала интеграции
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 8856f6bc-5460-4f35-acf2-f7662f01579b
description: 'Сводка: Сведения о операции получения интеграции журнала, которая является частью API данных для панели мониторинга качества звонков. Панель мониторинга качества звонков — это средство для Скайп для Business Server 2015.'
ms.openlocfilehash: a71d01780222d673c8455176ac82fc51683b441e
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569074"
---
# <a name="get-integration-log"></a><span data-ttu-id="1ec2d-104">Получение журнала интеграции</span><span class="sxs-lookup"><span data-stu-id="1ec2d-104">Get Integration Log</span></span>
 
<span data-ttu-id="1ec2d-105">**Сводка:** Узнайте о операции получения интеграции журнала, которая является частью API данных для панели мониторинга качества звонков.</span><span class="sxs-lookup"><span data-stu-id="1ec2d-105">**Summary:** Learn about the Get Integration Log operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="1ec2d-106">Панель мониторинга качества звонков — это средство для Скайп для Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="1ec2d-106">Call Quality Dashboard is a tool for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="1ec2d-107">Операция получения журнала интеграции является частью API данных для панели мониторинга качества звонков</span><span class="sxs-lookup"><span data-stu-id="1ec2d-107">The Get Integration Log operation is part of the Data API for Call Quality Dashboard</span></span>
  
## <a name="get-integration-log"></a><span data-ttu-id="1ec2d-108">Получение журнала интеграции</span><span class="sxs-lookup"><span data-stu-id="1ec2d-108">Get Integration Log</span></span>

<span data-ttu-id="1ec2d-109">Получение журнала интеграции операция возвращает список записей журнала, описывающий действия в кубе качества взаимодействия обработки.</span><span class="sxs-lookup"><span data-stu-id="1ec2d-109">Get Integration Log operation returns a list of log entries describing the activities in QoE Cube processing.</span></span>
  
<span data-ttu-id="1ec2d-110">Эта операция отключена по умолчанию в целях безопасности.</span><span class="sxs-lookup"><span data-stu-id="1ec2d-110">This operation is disabled by default for security reasons.</span></span> <span data-ttu-id="1ec2d-111">При отключении возвращает пустую строку.</span><span class="sxs-lookup"><span data-stu-id="1ec2d-111">When disabled, it returns an empty string.</span></span> <span data-ttu-id="1ec2d-112">Чтобы включить эту операцию, администраторы должны настроить файл web.config для данных API размещения веб-приложения.</span><span class="sxs-lookup"><span data-stu-id="1ec2d-112">To enable this operation, administrators need to configure the web.config for Data API's host web application.</span></span>
  

|<span data-ttu-id="1ec2d-113">Метод</span><span class="sxs-lookup"><span data-stu-id="1ec2d-113">Method</span></span>|<span data-ttu-id="1ec2d-114">**URI запроса**</span><span class="sxs-lookup"><span data-stu-id="1ec2d-114">**Request URI**</span></span>|<span data-ttu-id="1ec2d-115">**Версия HTTP**</span><span class="sxs-lookup"><span data-stu-id="1ec2d-115">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1ec2d-116">Получить</span><span class="sxs-lookup"><span data-stu-id="1ec2d-116">GET</span></span>  <br/> |<span data-ttu-id="1ec2d-117">https://\<портала\>/QoEDataService/IntegrationLog</span><span class="sxs-lookup"><span data-stu-id="1ec2d-117">https://\<portal\>/QoEDataService/IntegrationLog</span></span>  <br/> |<span data-ttu-id="1ec2d-118">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="1ec2d-118">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="1ec2d-119">**Параметры URI** — нет.</span><span class="sxs-lookup"><span data-stu-id="1ec2d-119">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="1ec2d-120">**Заголовки запроса** — без дополнительных заголовков.</span><span class="sxs-lookup"><span data-stu-id="1ec2d-120">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="1ec2d-121">**Текст запроса** — нет.</span><span class="sxs-lookup"><span data-stu-id="1ec2d-121">**Request Body** - None.</span></span>
  
 <span data-ttu-id="1ec2d-122">**Ответа** - ответ включает код состояния HTTP и набор заголовков ответов.</span><span class="sxs-lookup"><span data-stu-id="1ec2d-122">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="1ec2d-123">**Код состояния** - успешные операции возвращает код состояния 200 (ОК).</span><span class="sxs-lookup"><span data-stu-id="1ec2d-123">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="1ec2d-124">**Заголовки ответа** — без дополнительных заголовков.</span><span class="sxs-lookup"><span data-stu-id="1ec2d-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="1ec2d-125">**Тело ответа** - ниже приведен образец структуры записей журнала.</span><span class="sxs-lookup"><span data-stu-id="1ec2d-125">**Response Body** - Below is a sample structure of log entries.</span></span>
  
```
[
{"LogCategory":"<category>","LogTime":"2015-03-18T10:28:29.10","LogDescription":"<log description>"}
]
```


