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
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213111"
---
# <a name="errordef-table-in-skype-for-business-server-2015"></a><span data-ttu-id="3f3a8-104">Таблица errordef в Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="3f3a8-104">ErrorDef table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="3f3a8-105">Таблица errordef хранит сведения о каждом типе, которая может возникнуть ошибка.</span><span class="sxs-lookup"><span data-stu-id="3f3a8-105">The ErrorDef table stores information about each type of error that may occur.</span></span> <span data-ttu-id="3f3a8-106">Каждая запись является одного типа ошибки.</span><span class="sxs-lookup"><span data-stu-id="3f3a8-106">Each record is one type of error.</span></span>
  
|<span data-ttu-id="3f3a8-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="3f3a8-107">**Column**</span></span>|<span data-ttu-id="3f3a8-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="3f3a8-108">**Data Type**</span></span>|<span data-ttu-id="3f3a8-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="3f3a8-109">**Key/Index**</span></span>|<span data-ttu-id="3f3a8-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="3f3a8-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="3f3a8-111">**Код ошибки**</span><span class="sxs-lookup"><span data-stu-id="3f3a8-111">**ErrorId**</span></span> <br/> |<span data-ttu-id="3f3a8-112">целое</span><span class="sxs-lookup"><span data-stu-id="3f3a8-112">int</span></span>  <br/> |<span data-ttu-id="3f3a8-113">Primary</span><span class="sxs-lookup"><span data-stu-id="3f3a8-113">Primary</span></span>  <br/> |<span data-ttu-id="3f3a8-114">Уникальный номер, идентифицирующий тип ошибки.</span><span class="sxs-lookup"><span data-stu-id="3f3a8-114">Unique ID number identifying this type of error.</span></span>  <br/> |
|<span data-ttu-id="3f3a8-115">**ResponseCode**</span><span class="sxs-lookup"><span data-stu-id="3f3a8-115">**ResponseCode**</span></span> <br/> |<span data-ttu-id="3f3a8-116">целое</span><span class="sxs-lookup"><span data-stu-id="3f3a8-116">int</span></span>  <br/> | <br/> |<span data-ttu-id="3f3a8-117">Стандартный код ответа SIP, связанный с этой ошибкой.</span><span class="sxs-lookup"><span data-stu-id="3f3a8-117">Standard SIP response code associated with this error.</span></span>  <br/> |
|<span data-ttu-id="3f3a8-118">**MsDiagId**</span><span class="sxs-lookup"><span data-stu-id="3f3a8-118">**MsDiagId**</span></span> <br/> |<span data-ttu-id="3f3a8-119">целое</span><span class="sxs-lookup"><span data-stu-id="3f3a8-119">int</span></span>  <br/> | <br/> |<span data-ttu-id="3f3a8-120">Диагностический идентификатор Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="3f3a8-120">Microsoft Diagnostic ID.</span></span>  <br/> |
|<span data-ttu-id="3f3a8-121">**CallTypeId**</span><span class="sxs-lookup"><span data-stu-id="3f3a8-121">**CallTypeId**</span></span> <br/> |<span data-ttu-id="3f3a8-122">Int</span><span class="sxs-lookup"><span data-stu-id="3f3a8-122">Int</span></span>  <br/> |<span data-ttu-id="3f3a8-123">Внешний</span><span class="sxs-lookup"><span data-stu-id="3f3a8-123">Foreign</span></span>  <br/> |<span data-ttu-id="3f3a8-124">Тип вызова.</span><span class="sxs-lookup"><span data-stu-id="3f3a8-124">Type of the call.</span></span> <span data-ttu-id="3f3a8-125">[Таблица CallType в Скайп для Business Server 2015](calltype.md) для получения дополнительных сведений см.</span><span class="sxs-lookup"><span data-stu-id="3f3a8-125">See the [CallType table in Skype for Business Server 2015](calltype.md) for more information.</span></span> <br/> |
|<span data-ttu-id="3f3a8-126">**RequestType**</span><span class="sxs-lookup"><span data-stu-id="3f3a8-126">**RequestType**</span></span> <br/> |<span data-ttu-id="3f3a8-127">varbinary(33)</span><span class="sxs-lookup"><span data-stu-id="3f3a8-127">varbinary(33)</span></span>  <br/> | <br/> |<span data-ttu-id="3f3a8-128">Тип запроса с отказом.</span><span class="sxs-lookup"><span data-stu-id="3f3a8-128">Type of request that failed.</span></span>  <br/> <span data-ttu-id="3f3a8-129">Эти данные можно преобразовать в текстовый формат с помощью следующего синтаксиса:</span><span class="sxs-lookup"><span data-stu-id="3f3a8-129">This data can be converted to text format by using this syntax:</span></span>  <br/>  `cast(cast(RequestType as varbinary(max)) as varchar(max))` <br/> |
|<span data-ttu-id="3f3a8-130">**ContentType**</span><span class="sxs-lookup"><span data-stu-id="3f3a8-130">**ContentType**</span></span> <br/> |<span data-ttu-id="3f3a8-131">varbinary(257)</span><span class="sxs-lookup"><span data-stu-id="3f3a8-131">varbinary(257)</span></span>  <br/> | <br/> |<span data-ttu-id="3f3a8-132">Тип содержимого запроса с отказом.</span><span class="sxs-lookup"><span data-stu-id="3f3a8-132">Content type of the request that failed.</span></span>  <br/> <span data-ttu-id="3f3a8-133">Эти данные можно преобразовать в текстовый формат с помощью следующего синтаксиса:</span><span class="sxs-lookup"><span data-stu-id="3f3a8-133">This data can be converted to text format by using this syntaxt:</span></span>  <br/>  `cast(cast(ContentType as varbinary(max)) as varchar(max))` <br/> |
   

