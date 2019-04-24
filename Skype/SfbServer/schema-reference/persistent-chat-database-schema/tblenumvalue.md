---
title: tblEnumValue
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
description: tblEnumValue — это встроенная таблица, которая содержит значения отображения и поведения атрибутов, используемых в таблице Node.
ms.openlocfilehash: 579b2747ea753b8a701d11dd806178427cbb27b3
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212882"
---
# <a name="tblenumvalue"></a><span data-ttu-id="d6909-103">tblEnumValue</span><span class="sxs-lookup"><span data-stu-id="d6909-103">tblEnumValue</span></span>
 
<span data-ttu-id="d6909-104">tblEnumValue — это встроенная таблица, которая содержит значения отображения и поведения атрибутов, используемых в таблице Node.</span><span class="sxs-lookup"><span data-stu-id="d6909-104">tblEnumValue is a hardcoded table that contains the Visibility and Behavior values of the attributes that are used in the Node table.</span></span>
  
<span data-ttu-id="d6909-105">**Столбцы**</span><span class="sxs-lookup"><span data-stu-id="d6909-105">**Columns**</span></span>

|<span data-ttu-id="d6909-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="d6909-106">**Column**</span></span>|<span data-ttu-id="d6909-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="d6909-107">**Type**</span></span>|<span data-ttu-id="d6909-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="d6909-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d6909-109">valueID</span><span class="sxs-lookup"><span data-stu-id="d6909-109">valueID</span></span>  <br/> |<span data-ttu-id="d6909-110">smallint, не может быть null</span><span class="sxs-lookup"><span data-stu-id="d6909-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="d6909-111">ИД значения.</span><span class="sxs-lookup"><span data-stu-id="d6909-111">ID of the value.</span></span>  <br/> |
|<span data-ttu-id="d6909-112">attributeID</span><span class="sxs-lookup"><span data-stu-id="d6909-112">attributeID</span></span>  <br/> |<span data-ttu-id="d6909-113">smallint, не может быть null</span><span class="sxs-lookup"><span data-stu-id="d6909-113">smallint, not null</span></span>  <br/> |<span data-ttu-id="d6909-114">Идентификатор атрибута.</span><span class="sxs-lookup"><span data-stu-id="d6909-114">ID of the attribute.</span></span>  <br/> |
|<span data-ttu-id="d6909-115">attributeValue</span><span class="sxs-lookup"><span data-stu-id="d6909-115">attributeValue</span></span>  <br/> |<span data-ttu-id="d6909-116">nvarchar (256), отлично от null</span><span class="sxs-lookup"><span data-stu-id="d6909-116">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="d6909-117">Имя значения.</span><span class="sxs-lookup"><span data-stu-id="d6909-117">Name of the value.</span></span>  <br/> |
   
<span data-ttu-id="d6909-118">**Ключи**</span><span class="sxs-lookup"><span data-stu-id="d6909-118">**Keys**</span></span>

|<span data-ttu-id="d6909-119">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="d6909-119">**Column**</span></span>|<span data-ttu-id="d6909-120">**Описание**</span><span class="sxs-lookup"><span data-stu-id="d6909-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d6909-121">valueID</span><span class="sxs-lookup"><span data-stu-id="d6909-121">valueID</span></span>  <br/> |<span data-ttu-id="d6909-122">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="d6909-122">Primary key.</span></span>  <br/> |
|<span data-ttu-id="d6909-123">attributeID</span><span class="sxs-lookup"><span data-stu-id="d6909-123">attributeID</span></span>  <br/> |<span data-ttu-id="d6909-124">Внешний ключ с поиском в таблице tblEnumAttribute.attributeID.</span><span class="sxs-lookup"><span data-stu-id="d6909-124">Foreign key with lookup in tblEnumAttribute.attributeID table.</span></span>  <br/> |
   
<span data-ttu-id="d6909-125">**Значения таблицы**</span><span class="sxs-lookup"><span data-stu-id="d6909-125">**Table Values**</span></span>

|<span data-ttu-id="d6909-126">**valueID**</span><span class="sxs-lookup"><span data-stu-id="d6909-126">**valueID**</span></span>|<span data-ttu-id="d6909-127">**attributeID**</span><span class="sxs-lookup"><span data-stu-id="d6909-127">**attributeID**</span></span>|<span data-ttu-id="d6909-128">**attributeValue**</span><span class="sxs-lookup"><span data-stu-id="d6909-128">**attributeValue**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d6909-129">2</span><span class="sxs-lookup"><span data-stu-id="d6909-129">2</span></span>  <br/> |<span data-ttu-id="d6909-130">1</span><span class="sxs-lookup"><span data-stu-id="d6909-130">1</span></span>  <br/> |<span data-ttu-id="d6909-131">закрытые</span><span class="sxs-lookup"><span data-stu-id="d6909-131">private</span></span>  <br/> |
|<span data-ttu-id="d6909-132">3</span><span class="sxs-lookup"><span data-stu-id="d6909-132">3</span></span>  <br/> |<span data-ttu-id="d6909-133">1</span><span class="sxs-lookup"><span data-stu-id="d6909-133">1</span></span>  <br/> |<span data-ttu-id="d6909-134">область</span><span class="sxs-lookup"><span data-stu-id="d6909-134">scope</span></span>  <br/> |
|<span data-ttu-id="d6909-135">4</span><span class="sxs-lookup"><span data-stu-id="d6909-135">4</span></span>  <br/> |<span data-ttu-id="d6909-136">2</span><span class="sxs-lookup"><span data-stu-id="d6909-136">2</span></span>  <br/> |<span data-ttu-id="d6909-137">Обычный</span><span class="sxs-lookup"><span data-stu-id="d6909-137">normal</span></span>  <br/> |
|<span data-ttu-id="d6909-138">5</span><span class="sxs-lookup"><span data-stu-id="d6909-138">5</span></span>  <br/> |<span data-ttu-id="d6909-139">2</span><span class="sxs-lookup"><span data-stu-id="d6909-139">2</span></span>  <br/> |<span data-ttu-id="d6909-140">аудитория</span><span class="sxs-lookup"><span data-stu-id="d6909-140">auditorium</span></span>  <br/> |
|<span data-ttu-id="d6909-141">6</span><span class="sxs-lookup"><span data-stu-id="d6909-141">6</span></span>  <br/> |<span data-ttu-id="d6909-142">1</span><span class="sxs-lookup"><span data-stu-id="d6909-142">1</span></span>  <br/> |<span data-ttu-id="d6909-143">Откройте</span><span class="sxs-lookup"><span data-stu-id="d6909-143">open</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="d6909-144">См. также</span><span class="sxs-lookup"><span data-stu-id="d6909-144">See also</span></span>

[<span data-ttu-id="d6909-145">tblNode</span><span class="sxs-lookup"><span data-stu-id="d6909-145">tblNode</span></span>](tblnode.md)
