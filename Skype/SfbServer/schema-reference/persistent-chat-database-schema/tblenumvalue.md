---
title: tblEnumValue
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
ms.openlocfilehash: 4957f87401dc93cc98d18fa5b1844e13daaefabd
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="tblenumvalue"></a><span data-ttu-id="7dd17-103">tblEnumValue</span><span class="sxs-lookup"><span data-stu-id="7dd17-103">tblEnumValue</span></span>
 
<span data-ttu-id="7dd17-104">tblEnumValue — это встроенная таблица, которая содержит значения отображения и поведения атрибутов, используемых в таблице Node.</span><span class="sxs-lookup"><span data-stu-id="7dd17-104">tblEnumValue is a hardcoded table that contains the Visibility and Behavior values of the attributes that are used in the Node table.</span></span>
  
<span data-ttu-id="7dd17-105">**Столбцы**</span><span class="sxs-lookup"><span data-stu-id="7dd17-105">**Columns**</span></span>

|<span data-ttu-id="7dd17-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="7dd17-106">**Column**</span></span>|<span data-ttu-id="7dd17-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="7dd17-107">**Type**</span></span>|<span data-ttu-id="7dd17-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="7dd17-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="7dd17-109">valueID</span><span class="sxs-lookup"><span data-stu-id="7dd17-109">valueID</span></span>  <br/> |<span data-ttu-id="7dd17-110">smallint, не может быть null</span><span class="sxs-lookup"><span data-stu-id="7dd17-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="7dd17-111">ИД значения.</span><span class="sxs-lookup"><span data-stu-id="7dd17-111">ID of the value.</span></span>  <br/> |
|<span data-ttu-id="7dd17-112">attributeID</span><span class="sxs-lookup"><span data-stu-id="7dd17-112">attributeID</span></span>  <br/> |<span data-ttu-id="7dd17-113">smallint, не может быть null</span><span class="sxs-lookup"><span data-stu-id="7dd17-113">smallint, not null</span></span>  <br/> |<span data-ttu-id="7dd17-114">Идентификатор атрибута.</span><span class="sxs-lookup"><span data-stu-id="7dd17-114">ID of the attribute.</span></span>  <br/> |
|<span data-ttu-id="7dd17-115">attributeValue</span><span class="sxs-lookup"><span data-stu-id="7dd17-115">attributeValue</span></span>  <br/> |<span data-ttu-id="7dd17-116">nvarchar (256), отлично от null</span><span class="sxs-lookup"><span data-stu-id="7dd17-116">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="7dd17-117">Имя значения.</span><span class="sxs-lookup"><span data-stu-id="7dd17-117">Name of the value.</span></span>  <br/> |
   
<span data-ttu-id="7dd17-118">**Ключи**</span><span class="sxs-lookup"><span data-stu-id="7dd17-118">**Keys**</span></span>

|<span data-ttu-id="7dd17-119">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="7dd17-119">**Column**</span></span>|<span data-ttu-id="7dd17-120">**Описание**</span><span class="sxs-lookup"><span data-stu-id="7dd17-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="7dd17-121">valueID</span><span class="sxs-lookup"><span data-stu-id="7dd17-121">valueID</span></span>  <br/> |<span data-ttu-id="7dd17-122">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="7dd17-122">Primary key.</span></span>  <br/> |
|<span data-ttu-id="7dd17-123">attributeID</span><span class="sxs-lookup"><span data-stu-id="7dd17-123">attributeID</span></span>  <br/> |<span data-ttu-id="7dd17-124">Внешний ключ с поиском в таблице tblEnumAttribute.attributeID.</span><span class="sxs-lookup"><span data-stu-id="7dd17-124">Foreign key with lookup in tblEnumAttribute.attributeID table.</span></span>  <br/> |
   
<span data-ttu-id="7dd17-125">**Значения таблицы**</span><span class="sxs-lookup"><span data-stu-id="7dd17-125">**Table Values**</span></span>

|<span data-ttu-id="7dd17-126">**valueID**</span><span class="sxs-lookup"><span data-stu-id="7dd17-126">**valueID**</span></span>|<span data-ttu-id="7dd17-127">**attributeID**</span><span class="sxs-lookup"><span data-stu-id="7dd17-127">**attributeID**</span></span>|<span data-ttu-id="7dd17-128">**attributeValue**</span><span class="sxs-lookup"><span data-stu-id="7dd17-128">**attributeValue**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="7dd17-129">2</span><span class="sxs-lookup"><span data-stu-id="7dd17-129">2</span></span>  <br/> |<span data-ttu-id="7dd17-130">1</span><span class="sxs-lookup"><span data-stu-id="7dd17-130">1</span></span>  <br/> |<span data-ttu-id="7dd17-131">закрытые</span><span class="sxs-lookup"><span data-stu-id="7dd17-131">private</span></span>  <br/> |
|<span data-ttu-id="7dd17-132">3</span><span class="sxs-lookup"><span data-stu-id="7dd17-132">3</span></span>  <br/> |<span data-ttu-id="7dd17-133">1</span><span class="sxs-lookup"><span data-stu-id="7dd17-133">1</span></span>  <br/> |<span data-ttu-id="7dd17-134">область</span><span class="sxs-lookup"><span data-stu-id="7dd17-134">scope</span></span>  <br/> |
|<span data-ttu-id="7dd17-135">4</span><span class="sxs-lookup"><span data-stu-id="7dd17-135">4</span></span>  <br/> |<span data-ttu-id="7dd17-136">2</span><span class="sxs-lookup"><span data-stu-id="7dd17-136">2</span></span>  <br/> |<span data-ttu-id="7dd17-137">Обычный</span><span class="sxs-lookup"><span data-stu-id="7dd17-137">normal</span></span>  <br/> |
|<span data-ttu-id="7dd17-138">5</span><span class="sxs-lookup"><span data-stu-id="7dd17-138">5</span></span>  <br/> |<span data-ttu-id="7dd17-139">2</span><span class="sxs-lookup"><span data-stu-id="7dd17-139">2</span></span>  <br/> |<span data-ttu-id="7dd17-140">аудитория</span><span class="sxs-lookup"><span data-stu-id="7dd17-140">auditorium</span></span>  <br/> |
|<span data-ttu-id="7dd17-141">6</span><span class="sxs-lookup"><span data-stu-id="7dd17-141">6</span></span>  <br/> |<span data-ttu-id="7dd17-142">1</span><span class="sxs-lookup"><span data-stu-id="7dd17-142">1</span></span>  <br/> |<span data-ttu-id="7dd17-143">Откройте</span><span class="sxs-lookup"><span data-stu-id="7dd17-143">open</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="7dd17-144">См. также</span><span class="sxs-lookup"><span data-stu-id="7dd17-144">See also</span></span>

#### 

[<span data-ttu-id="7dd17-145">tblNode</span><span class="sxs-lookup"><span data-stu-id="7dd17-145">tblNode</span></span>](tblnode.md)

