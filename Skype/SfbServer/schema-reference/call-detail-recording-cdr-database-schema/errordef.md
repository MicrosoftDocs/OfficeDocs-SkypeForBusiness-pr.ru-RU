---
title: Таблица errordef в Скайп для Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6acf3b86-da61-4923-9812-300db6f66dec
description: Таблица errordef хранит сведения о каждом типе, которая может возникнуть ошибка. Каждая запись является одного типа ошибки.
ms.openlocfilehash: f1edd4595cdd360c0da1e3cd76f5ed4b63ddf46d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901168"
---
# <a name="errordef-table-in-skype-for-business-server-2015"></a><span data-ttu-id="899f6-104">Таблица errordef в Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="899f6-104">ErrorDef table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="899f6-105">Таблица errordef хранит сведения о каждом типе, которая может возникнуть ошибка.</span><span class="sxs-lookup"><span data-stu-id="899f6-105">The ErrorDef table stores information about each type of error that may occur.</span></span> <span data-ttu-id="899f6-106">Каждая запись является одного типа ошибки.</span><span class="sxs-lookup"><span data-stu-id="899f6-106">Each record is one type of error.</span></span>
  
|<span data-ttu-id="899f6-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="899f6-107">**Column**</span></span>|<span data-ttu-id="899f6-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="899f6-108">**Data Type**</span></span>|<span data-ttu-id="899f6-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="899f6-109">**Key/Index**</span></span>|<span data-ttu-id="899f6-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="899f6-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="899f6-111">**Код ошибки**</span><span class="sxs-lookup"><span data-stu-id="899f6-111">**ErrorId**</span></span> <br/> |<span data-ttu-id="899f6-112">целое</span><span class="sxs-lookup"><span data-stu-id="899f6-112">int</span></span>  <br/> |<span data-ttu-id="899f6-113">Primary</span><span class="sxs-lookup"><span data-stu-id="899f6-113">Primary</span></span>  <br/> |<span data-ttu-id="899f6-114">Уникальный номер, идентифицирующий тип ошибки.</span><span class="sxs-lookup"><span data-stu-id="899f6-114">Unique ID number identifying this type of error.</span></span>  <br/> |
|<span data-ttu-id="899f6-115">**ResponseCode**</span><span class="sxs-lookup"><span data-stu-id="899f6-115">**ResponseCode**</span></span> <br/> |<span data-ttu-id="899f6-116">целое</span><span class="sxs-lookup"><span data-stu-id="899f6-116">int</span></span>  <br/> | <br/> |<span data-ttu-id="899f6-117">Стандартный код ответа SIP, связанный с этой ошибкой.</span><span class="sxs-lookup"><span data-stu-id="899f6-117">Standard SIP response code associated with this error.</span></span>  <br/> |
|<span data-ttu-id="899f6-118">**MsDiagId**</span><span class="sxs-lookup"><span data-stu-id="899f6-118">**MsDiagId**</span></span> <br/> |<span data-ttu-id="899f6-119">целое</span><span class="sxs-lookup"><span data-stu-id="899f6-119">int</span></span>  <br/> | <br/> |<span data-ttu-id="899f6-120">Диагностический идентификатор Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="899f6-120">Microsoft Diagnostic ID.</span></span>  <br/> |
|<span data-ttu-id="899f6-121">**CallTypeId**</span><span class="sxs-lookup"><span data-stu-id="899f6-121">**CallTypeId**</span></span> <br/> |<span data-ttu-id="899f6-122">Int</span><span class="sxs-lookup"><span data-stu-id="899f6-122">Int</span></span>  <br/> |<span data-ttu-id="899f6-123">Внешний</span><span class="sxs-lookup"><span data-stu-id="899f6-123">Foreign</span></span>  <br/> |<span data-ttu-id="899f6-124">Тип вызова.</span><span class="sxs-lookup"><span data-stu-id="899f6-124">Type of the call.</span></span> <span data-ttu-id="899f6-125">[Таблица CallType в Скайп для Business Server 2015](calltype.md) для получения дополнительных сведений см.</span><span class="sxs-lookup"><span data-stu-id="899f6-125">See the [CallType table in Skype for Business Server 2015](calltype.md) for more information.</span></span> <br/> |
|<span data-ttu-id="899f6-126">**RequestType**</span><span class="sxs-lookup"><span data-stu-id="899f6-126">**RequestType**</span></span> <br/> |<span data-ttu-id="899f6-127">varbinary(33)</span><span class="sxs-lookup"><span data-stu-id="899f6-127">varbinary(33)</span></span>  <br/> | <br/> |<span data-ttu-id="899f6-128">Тип запроса с отказом.</span><span class="sxs-lookup"><span data-stu-id="899f6-128">Type of request that failed.</span></span>  <br/> <span data-ttu-id="899f6-129">Эти данные можно преобразовать в текстовый формат с помощью следующего синтаксиса:</span><span class="sxs-lookup"><span data-stu-id="899f6-129">This data can be converted to text format by using this syntax:</span></span>  <br/>  `cast(cast(RequestType as varbinary(max)) as varchar(max))` <br/> |
|<span data-ttu-id="899f6-130">**ContentType**</span><span class="sxs-lookup"><span data-stu-id="899f6-130">**ContentType**</span></span> <br/> |<span data-ttu-id="899f6-131">varbinary(257)</span><span class="sxs-lookup"><span data-stu-id="899f6-131">varbinary(257)</span></span>  <br/> | <br/> |<span data-ttu-id="899f6-132">Тип содержимого запроса с отказом.</span><span class="sxs-lookup"><span data-stu-id="899f6-132">Content type of the request that failed.</span></span>  <br/> <span data-ttu-id="899f6-133">Эти данные можно преобразовать в текстовый формат с помощью следующего синтаксиса:</span><span class="sxs-lookup"><span data-stu-id="899f6-133">This data can be converted to text format by using this syntaxt:</span></span>  <br/>  `cast(cast(ContentType as varbinary(max)) as varchar(max))` <br/> |
   

