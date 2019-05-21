---
title: Таблица Еррордеф в Skype для бизнеса Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6acf3b86-da61-4923-9812-300db6f66dec
description: В таблице Еррордеф хранятся сведения о каждом типе ошибки, которые могут возникать. Каждая запись имеет один тип ошибки.
ms.openlocfilehash: c6157bb62df47b8fcb1cd158605c5a357e623adf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296282"
---
# <a name="errordef-table-in-skype-for-business-server-2015"></a><span data-ttu-id="24617-104">Таблица Еррордеф в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="24617-104">ErrorDef table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="24617-105">В таблице Еррордеф хранятся сведения о каждом типе ошибки, которые могут возникать.</span><span class="sxs-lookup"><span data-stu-id="24617-105">The ErrorDef table stores information about each type of error that may occur.</span></span> <span data-ttu-id="24617-106">Каждая запись имеет один тип ошибки.</span><span class="sxs-lookup"><span data-stu-id="24617-106">Each record is one type of error.</span></span>
  
|<span data-ttu-id="24617-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="24617-107">**Column**</span></span>|<span data-ttu-id="24617-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="24617-108">**Data Type**</span></span>|<span data-ttu-id="24617-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="24617-109">**Key/Index**</span></span>|<span data-ttu-id="24617-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="24617-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="24617-111">**Еррорид**</span><span class="sxs-lookup"><span data-stu-id="24617-111">**ErrorId**</span></span> <br/> |<span data-ttu-id="24617-112">целое</span><span class="sxs-lookup"><span data-stu-id="24617-112">int</span></span>  <br/> |<span data-ttu-id="24617-113">Primary</span><span class="sxs-lookup"><span data-stu-id="24617-113">Primary</span></span>  <br/> |<span data-ttu-id="24617-114">Уникальный ИДЕНТИФИКАЦИОНный номер, показывающий этот тип ошибки.</span><span class="sxs-lookup"><span data-stu-id="24617-114">Unique ID number identifying this type of error.</span></span>  <br/> |
|<span data-ttu-id="24617-115">**Респонсекоде**</span><span class="sxs-lookup"><span data-stu-id="24617-115">**ResponseCode**</span></span> <br/> |<span data-ttu-id="24617-116">целое</span><span class="sxs-lookup"><span data-stu-id="24617-116">int</span></span>  <br/> | <br/> |<span data-ttu-id="24617-117">Стандартный код ответа SIP, связанный с этой ошибкой.</span><span class="sxs-lookup"><span data-stu-id="24617-117">Standard SIP response code associated with this error.</span></span>  <br/> |
|<span data-ttu-id="24617-118">**Мсдиагид**</span><span class="sxs-lookup"><span data-stu-id="24617-118">**MsDiagId**</span></span> <br/> |<span data-ttu-id="24617-119">целое</span><span class="sxs-lookup"><span data-stu-id="24617-119">int</span></span>  <br/> | <br/> |<span data-ttu-id="24617-120">Идентификатор диагностики (Майкрософт).</span><span class="sxs-lookup"><span data-stu-id="24617-120">Microsoft Diagnostic ID.</span></span>  <br/> |
|<span data-ttu-id="24617-121">**Каллтипеид**</span><span class="sxs-lookup"><span data-stu-id="24617-121">**CallTypeId**</span></span> <br/> |<span data-ttu-id="24617-122">Типом</span><span class="sxs-lookup"><span data-stu-id="24617-122">Int</span></span>  <br/> |<span data-ttu-id="24617-123">Другом</span><span class="sxs-lookup"><span data-stu-id="24617-123">Foreign</span></span>  <br/> |<span data-ttu-id="24617-124">Тип звонка.</span><span class="sxs-lookup"><span data-stu-id="24617-124">Type of the call.</span></span> <span data-ttu-id="24617-125">Для получения дополнительных сведений ознакомьтесь с [таблицей каллтипе в Skype для бизнеса Server 2015](calltype.md) .</span><span class="sxs-lookup"><span data-stu-id="24617-125">See the [CallType table in Skype for Business Server 2015](calltype.md) for more information.</span></span> <br/> |
|<span data-ttu-id="24617-126">**RequestType**</span><span class="sxs-lookup"><span data-stu-id="24617-126">**RequestType**</span></span> <br/> |<span data-ttu-id="24617-127">varbinary (33)</span><span class="sxs-lookup"><span data-stu-id="24617-127">varbinary(33)</span></span>  <br/> | <br/> |<span data-ttu-id="24617-128">Тип запроса, который завершился сбоем.</span><span class="sxs-lookup"><span data-stu-id="24617-128">Type of request that failed.</span></span>  <br/> <span data-ttu-id="24617-129">Эти данные можно преобразовать в текстовый формат, используя следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="24617-129">This data can be converted to text format by using this syntax:</span></span>  <br/>  `cast(cast(RequestType as varbinary(max)) as varchar(max))` <br/> |
|<span data-ttu-id="24617-130">**Контента**</span><span class="sxs-lookup"><span data-stu-id="24617-130">**ContentType**</span></span> <br/> |<span data-ttu-id="24617-131">varbinary (257)</span><span class="sxs-lookup"><span data-stu-id="24617-131">varbinary(257)</span></span>  <br/> | <br/> |<span data-ttu-id="24617-132">Тип контента запроса, который завершился сбоем.</span><span class="sxs-lookup"><span data-stu-id="24617-132">Content type of the request that failed.</span></span>  <br/> <span data-ttu-id="24617-133">Эти данные можно преобразовать в текстовый формат с помощью синтаксиса:</span><span class="sxs-lookup"><span data-stu-id="24617-133">This data can be converted to text format by using this syntaxt:</span></span>  <br/>  `cast(cast(ContentType as varbinary(max)) as varchar(max))` <br/> |
   

