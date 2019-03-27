---
title: Таблица errordef в Скайп для Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6acf3b86-da61-4923-9812-300db6f66dec
description: Таблица errordef хранит сведения о каждом типе, которая может возникнуть ошибка. Каждая запись является одного типа ошибки.
ms.openlocfilehash: cec601dad24dda522477bfcd7b1e80d0efc45799
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30899069"
---
# <a name="errordef-table-in-skype-for-business-server-2015"></a><span data-ttu-id="38708-104">Таблица errordef в Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="38708-104">ErrorDef table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="38708-105">Таблица errordef хранит сведения о каждом типе, которая может возникнуть ошибка.</span><span class="sxs-lookup"><span data-stu-id="38708-105">The ErrorDef table stores information about each type of error that may occur.</span></span> <span data-ttu-id="38708-106">Каждая запись является одного типа ошибки.</span><span class="sxs-lookup"><span data-stu-id="38708-106">Each record is one type of error.</span></span>
  
|<span data-ttu-id="38708-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="38708-107">**Column**</span></span>|<span data-ttu-id="38708-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="38708-108">**Data Type**</span></span>|<span data-ttu-id="38708-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="38708-109">**Key/Index**</span></span>|<span data-ttu-id="38708-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="38708-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="38708-111">**Код ошибки**</span><span class="sxs-lookup"><span data-stu-id="38708-111">**ErrorId**</span></span> <br/> |<span data-ttu-id="38708-112">целое</span><span class="sxs-lookup"><span data-stu-id="38708-112">int</span></span>  <br/> |<span data-ttu-id="38708-113">Primary</span><span class="sxs-lookup"><span data-stu-id="38708-113">Primary</span></span>  <br/> |<span data-ttu-id="38708-114">Уникальный номер, идентифицирующий тип ошибки.</span><span class="sxs-lookup"><span data-stu-id="38708-114">Unique ID number identifying this type of error.</span></span>  <br/> |
|<span data-ttu-id="38708-115">**ResponseCode**</span><span class="sxs-lookup"><span data-stu-id="38708-115">**ResponseCode**</span></span> <br/> |<span data-ttu-id="38708-116">целое</span><span class="sxs-lookup"><span data-stu-id="38708-116">int</span></span>  <br/> | <br/> |<span data-ttu-id="38708-117">Стандартный код ответа SIP, связанный с этой ошибкой.</span><span class="sxs-lookup"><span data-stu-id="38708-117">Standard SIP response code associated with this error.</span></span>  <br/> |
|<span data-ttu-id="38708-118">**MsDiagId**</span><span class="sxs-lookup"><span data-stu-id="38708-118">**MsDiagId**</span></span> <br/> |<span data-ttu-id="38708-119">целое</span><span class="sxs-lookup"><span data-stu-id="38708-119">int</span></span>  <br/> | <br/> |<span data-ttu-id="38708-120">Диагностический идентификатор Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="38708-120">Microsoft Diagnostic ID.</span></span>  <br/> |
|<span data-ttu-id="38708-121">**CallTypeId**</span><span class="sxs-lookup"><span data-stu-id="38708-121">**CallTypeId**</span></span> <br/> |<span data-ttu-id="38708-122">Int</span><span class="sxs-lookup"><span data-stu-id="38708-122">Int</span></span>  <br/> |<span data-ttu-id="38708-123">Внешний</span><span class="sxs-lookup"><span data-stu-id="38708-123">Foreign</span></span>  <br/> |<span data-ttu-id="38708-124">Тип вызова.</span><span class="sxs-lookup"><span data-stu-id="38708-124">Type of the call.</span></span> <span data-ttu-id="38708-125">[Таблица CallType в Скайп для Business Server 2015](calltype.md) для получения дополнительных сведений см.</span><span class="sxs-lookup"><span data-stu-id="38708-125">See the [CallType table in Skype for Business Server 2015](calltype.md) for more information.</span></span> <br/> |
|<span data-ttu-id="38708-126">**RequestType**</span><span class="sxs-lookup"><span data-stu-id="38708-126">**RequestType**</span></span> <br/> |<span data-ttu-id="38708-127">varbinary(33)</span><span class="sxs-lookup"><span data-stu-id="38708-127">varbinary(33)</span></span>  <br/> | <br/> |<span data-ttu-id="38708-128">Тип запроса с отказом.</span><span class="sxs-lookup"><span data-stu-id="38708-128">Type of request that failed.</span></span>  <br/> <span data-ttu-id="38708-129">Эти данные можно преобразовать в текстовый формат с помощью следующего синтаксиса:</span><span class="sxs-lookup"><span data-stu-id="38708-129">This data can be converted to text format by using this syntax:</span></span>  <br/>  `cast(cast(RequestType as varbinary(max)) as varchar(max))` <br/> |
|<span data-ttu-id="38708-130">**ContentType**</span><span class="sxs-lookup"><span data-stu-id="38708-130">**ContentType**</span></span> <br/> |<span data-ttu-id="38708-131">varbinary(257)</span><span class="sxs-lookup"><span data-stu-id="38708-131">varbinary(257)</span></span>  <br/> | <br/> |<span data-ttu-id="38708-132">Тип содержимого запроса с отказом.</span><span class="sxs-lookup"><span data-stu-id="38708-132">Content type of the request that failed.</span></span>  <br/> <span data-ttu-id="38708-133">Эти данные можно преобразовать в текстовый формат с помощью следующего синтаксиса:</span><span class="sxs-lookup"><span data-stu-id="38708-133">This data can be converted to text format by using this syntaxt:</span></span>  <br/>  `cast(cast(ContentType as varbinary(max)) as varchar(max))` <br/> |
   

