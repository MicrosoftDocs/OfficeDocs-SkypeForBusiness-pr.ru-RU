---
title: Таблица errordef в Скайп для Business Server 2015
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
ms.openlocfilehash: 4583e1130d257a99d075f2dec0dea80ee6b1390c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="errordef-table-in-skype-for-business-server-2015"></a><span data-ttu-id="24dd5-104">Таблица errordef в Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="24dd5-104">ErrorDef table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="24dd5-105">Таблица errordef хранит сведения о каждом типе, которая может возникнуть ошибка.</span><span class="sxs-lookup"><span data-stu-id="24dd5-105">The ErrorDef table stores information about each type of error that may occur.</span></span> <span data-ttu-id="24dd5-106">Каждая запись является одного типа ошибки.</span><span class="sxs-lookup"><span data-stu-id="24dd5-106">Each record is one type of error.</span></span>
  
|<span data-ttu-id="24dd5-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="24dd5-107">**Column**</span></span>|<span data-ttu-id="24dd5-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="24dd5-108">**Data Type**</span></span>|<span data-ttu-id="24dd5-109">**Ключ или индекс**</span><span class="sxs-lookup"><span data-stu-id="24dd5-109">**Key/Index**</span></span>|<span data-ttu-id="24dd5-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="24dd5-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="24dd5-111">**Код ошибки**</span><span class="sxs-lookup"><span data-stu-id="24dd5-111">**ErrorId**</span></span> <br/> |<span data-ttu-id="24dd5-112">целое</span><span class="sxs-lookup"><span data-stu-id="24dd5-112">int</span></span>  <br/> |<span data-ttu-id="24dd5-113">Primary</span><span class="sxs-lookup"><span data-stu-id="24dd5-113">Primary</span></span>  <br/> |<span data-ttu-id="24dd5-114">Уникальный номер, идентифицирующий тип ошибки.</span><span class="sxs-lookup"><span data-stu-id="24dd5-114">Unique ID number identifying this type of error.</span></span>  <br/> |
|<span data-ttu-id="24dd5-115">**ResponseCode**</span><span class="sxs-lookup"><span data-stu-id="24dd5-115">**ResponseCode**</span></span> <br/> |<span data-ttu-id="24dd5-116">целое</span><span class="sxs-lookup"><span data-stu-id="24dd5-116">int</span></span>  <br/> | <br/> |<span data-ttu-id="24dd5-117">Стандартный код ответа SIP, связанный с этой ошибкой.</span><span class="sxs-lookup"><span data-stu-id="24dd5-117">Standard SIP response code associated with this error.</span></span>  <br/> |
|<span data-ttu-id="24dd5-118">**MsDiagId**</span><span class="sxs-lookup"><span data-stu-id="24dd5-118">**MsDiagId**</span></span> <br/> |<span data-ttu-id="24dd5-119">целое</span><span class="sxs-lookup"><span data-stu-id="24dd5-119">int</span></span>  <br/> | <br/> |<span data-ttu-id="24dd5-120">Диагностический идентификатор Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="24dd5-120">Microsoft Diagnostic ID.</span></span>  <br/> |
|<span data-ttu-id="24dd5-121">**CallTypeId**</span><span class="sxs-lookup"><span data-stu-id="24dd5-121">**CallTypeId**</span></span> <br/> |<span data-ttu-id="24dd5-122">Int</span><span class="sxs-lookup"><span data-stu-id="24dd5-122">Int</span></span>  <br/> |<span data-ttu-id="24dd5-123">Внешний</span><span class="sxs-lookup"><span data-stu-id="24dd5-123">Foreign</span></span>  <br/> |<span data-ttu-id="24dd5-124">Тип вызова.</span><span class="sxs-lookup"><span data-stu-id="24dd5-124">Type of the call.</span></span> <span data-ttu-id="24dd5-125">[Таблица CallType в Скайп для Business Server 2015](calltype.md) для получения дополнительных сведений см.</span><span class="sxs-lookup"><span data-stu-id="24dd5-125">See the [CallType table in Skype for Business Server 2015](calltype.md) for more information.</span></span> <br/> |
|<span data-ttu-id="24dd5-126">**RequestType**</span><span class="sxs-lookup"><span data-stu-id="24dd5-126">**RequestType**</span></span> <br/> |<span data-ttu-id="24dd5-127">varbinary(33)</span><span class="sxs-lookup"><span data-stu-id="24dd5-127">varbinary(33)</span></span>  <br/> | <br/> |<span data-ttu-id="24dd5-128">Тип запроса с отказом.</span><span class="sxs-lookup"><span data-stu-id="24dd5-128">Type of request that failed.</span></span>  <br/> <span data-ttu-id="24dd5-129">Эти данные можно преобразовать в текстовый формат с помощью следующего синтаксиса:</span><span class="sxs-lookup"><span data-stu-id="24dd5-129">This data can be converted to text format by using this syntax:</span></span>  <br/>  `cast(cast(RequestType as varbinary(max)) as varchar(max))` <br/> |
|<span data-ttu-id="24dd5-130">**ContentType**</span><span class="sxs-lookup"><span data-stu-id="24dd5-130">**ContentType**</span></span> <br/> |<span data-ttu-id="24dd5-131">varbinary(257)</span><span class="sxs-lookup"><span data-stu-id="24dd5-131">varbinary(257)</span></span>  <br/> | <br/> |<span data-ttu-id="24dd5-132">Тип содержимого запроса с отказом.</span><span class="sxs-lookup"><span data-stu-id="24dd5-132">Content type of the request that failed.</span></span>  <br/> <span data-ttu-id="24dd5-133">Эти данные можно преобразовать в текстовый формат с помощью следующего синтаксиса:</span><span class="sxs-lookup"><span data-stu-id="24dd5-133">This data can be converted to text format by using this syntaxt:</span></span>  <br/>  `cast(cast(ContentType as varbinary(max)) as varchar(max))` <br/> |
   

