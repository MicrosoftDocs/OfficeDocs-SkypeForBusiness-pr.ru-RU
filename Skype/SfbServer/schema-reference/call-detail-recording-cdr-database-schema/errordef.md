---
title: Таблица ErrorDef в Skype для бизнеса Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6acf3b86-da61-4923-9812-300db6f66dec
description: В таблице ErrorDef хранится информация о каждом типе ошибки, которая может возникнуть. Каждая запись является одним типом ошибки.
ms.openlocfilehash: 50d7b76e1fc7edb53fbe0b299673b7281a394463
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821729"
---
# <a name="errordef-table-in-skype-for-business-server-2015"></a><span data-ttu-id="46f11-104">Таблица ErrorDef в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="46f11-104">ErrorDef table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="46f11-105">В таблице ErrorDef хранится информация о каждом типе ошибки, которая может возникнуть.</span><span class="sxs-lookup"><span data-stu-id="46f11-105">The ErrorDef table stores information about each type of error that may occur.</span></span> <span data-ttu-id="46f11-106">Каждая запись является одним типом ошибки.</span><span class="sxs-lookup"><span data-stu-id="46f11-106">Each record is one type of error.</span></span>
  
|<span data-ttu-id="46f11-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="46f11-107">**Column**</span></span>|<span data-ttu-id="46f11-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="46f11-108">**Data Type**</span></span>|<span data-ttu-id="46f11-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="46f11-109">**Key/Index**</span></span>|<span data-ttu-id="46f11-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="46f11-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="46f11-111">**ErrorId**</span><span class="sxs-lookup"><span data-stu-id="46f11-111">**ErrorId**</span></span> <br/> |<span data-ttu-id="46f11-112">int</span><span class="sxs-lookup"><span data-stu-id="46f11-112">int</span></span>  <br/> |<span data-ttu-id="46f11-113">Primary</span><span class="sxs-lookup"><span data-stu-id="46f11-113">Primary</span></span>  <br/> |<span data-ttu-id="46f11-114">Уникальный номер ИД, определяющий этот тип ошибки.</span><span class="sxs-lookup"><span data-stu-id="46f11-114">Unique ID number identifying this type of error.</span></span>  <br/> |
|<span data-ttu-id="46f11-115">**ResponseCode**</span><span class="sxs-lookup"><span data-stu-id="46f11-115">**ResponseCode**</span></span> <br/> |<span data-ttu-id="46f11-116">int</span><span class="sxs-lookup"><span data-stu-id="46f11-116">int</span></span>  <br/> | <br/> |<span data-ttu-id="46f11-117">Стандартный код ответа SIP, связанный с этой ошибкой.</span><span class="sxs-lookup"><span data-stu-id="46f11-117">Standard SIP response code associated with this error.</span></span>  <br/> |
|<span data-ttu-id="46f11-118">**MsDiagId**</span><span class="sxs-lookup"><span data-stu-id="46f11-118">**MsDiagId**</span></span> <br/> |<span data-ttu-id="46f11-119">int</span><span class="sxs-lookup"><span data-stu-id="46f11-119">int</span></span>  <br/> | <br/> |<span data-ttu-id="46f11-120">ИД диагностики Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="46f11-120">Microsoft Diagnostic ID.</span></span>  <br/> |
|<span data-ttu-id="46f11-121">**CallTypeId**</span><span class="sxs-lookup"><span data-stu-id="46f11-121">**CallTypeId**</span></span> <br/> |<span data-ttu-id="46f11-122">Целое</span><span class="sxs-lookup"><span data-stu-id="46f11-122">Int</span></span>  <br/> |<span data-ttu-id="46f11-123">Внешняя</span><span class="sxs-lookup"><span data-stu-id="46f11-123">Foreign</span></span>  <br/> |<span data-ttu-id="46f11-124">Тип вызова.</span><span class="sxs-lookup"><span data-stu-id="46f11-124">Type of the call.</span></span> <span data-ttu-id="46f11-125">Дополнительные сведения см. в таблице [CallType в Skype для бизнеса Server 2015.](calltype.md)</span><span class="sxs-lookup"><span data-stu-id="46f11-125">See the [CallType table in Skype for Business Server 2015](calltype.md) for more information.</span></span> <br/> |
|<span data-ttu-id="46f11-126">**RequestType**</span><span class="sxs-lookup"><span data-stu-id="46f11-126">**RequestType**</span></span> <br/> |<span data-ttu-id="46f11-127">varbinary(33)</span><span class="sxs-lookup"><span data-stu-id="46f11-127">varbinary(33)</span></span>  <br/> | <br/> |<span data-ttu-id="46f11-128">Тип запроса с отказом.</span><span class="sxs-lookup"><span data-stu-id="46f11-128">Type of request that failed.</span></span>  <br/> <span data-ttu-id="46f11-129">Эти данные можно преобразовать в текстовый формат, используя следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="46f11-129">This data can be converted to text format by using this syntax:</span></span>  <br/>  `cast(cast(RequestType as varbinary(max)) as varchar(max))` <br/> |
|<span data-ttu-id="46f11-130">**ContentType**</span><span class="sxs-lookup"><span data-stu-id="46f11-130">**ContentType**</span></span> <br/> |<span data-ttu-id="46f11-131">varbinary(257)</span><span class="sxs-lookup"><span data-stu-id="46f11-131">varbinary(257)</span></span>  <br/> | <br/> |<span data-ttu-id="46f11-132">Тип содержимого запроса с отказом.</span><span class="sxs-lookup"><span data-stu-id="46f11-132">Content type of the request that failed.</span></span>  <br/> <span data-ttu-id="46f11-133">Эти данные можно преобразовать в текстовый формат с помощью этого синтаксиса:</span><span class="sxs-lookup"><span data-stu-id="46f11-133">This data can be converted to text format by using this syntaxt:</span></span>  <br/>  `cast(cast(ContentType as varbinary(max)) as varchar(max))` <br/> |
   

