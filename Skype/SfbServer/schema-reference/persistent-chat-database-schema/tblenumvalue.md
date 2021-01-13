---
title: tblEnumValue
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
ms.assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
description: tblEnumValue — это встроенная таблица, которая содержит значения отображения и поведения атрибутов, используемых в таблице Node.
ms.openlocfilehash: a13bfbe79d1eb118f0727f390816a26d35a508d0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816029"
---
# <a name="tblenumvalue"></a><span data-ttu-id="085f3-103">tblEnumValue</span><span class="sxs-lookup"><span data-stu-id="085f3-103">tblEnumValue</span></span>
 
<span data-ttu-id="085f3-104">tblEnumValue — это встроенная таблица, которая содержит значения отображения и поведения атрибутов, используемых в таблице Node.</span><span class="sxs-lookup"><span data-stu-id="085f3-104">tblEnumValue is a hardcoded table that contains the Visibility and Behavior values of the attributes that are used in the Node table.</span></span>
  
<span data-ttu-id="085f3-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="085f3-105">**Columns**</span></span>

|<span data-ttu-id="085f3-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="085f3-106">**Column**</span></span>|<span data-ttu-id="085f3-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="085f3-107">**Type**</span></span>|<span data-ttu-id="085f3-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="085f3-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="085f3-109">valueID</span><span class="sxs-lookup"><span data-stu-id="085f3-109">valueID</span></span>  <br/> |<span data-ttu-id="085f3-110">smallint, not null</span><span class="sxs-lookup"><span data-stu-id="085f3-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="085f3-111">ИД значения.</span><span class="sxs-lookup"><span data-stu-id="085f3-111">ID of the value.</span></span>  <br/> |
|<span data-ttu-id="085f3-112">attributeID</span><span class="sxs-lookup"><span data-stu-id="085f3-112">attributeID</span></span>  <br/> |<span data-ttu-id="085f3-113">smallint, не может быть null</span><span class="sxs-lookup"><span data-stu-id="085f3-113">smallint, not null</span></span>  <br/> |<span data-ttu-id="085f3-114">ИД атрибута.</span><span class="sxs-lookup"><span data-stu-id="085f3-114">ID of the attribute.</span></span>  <br/> |
|<span data-ttu-id="085f3-115">attributeValue</span><span class="sxs-lookup"><span data-stu-id="085f3-115">attributeValue</span></span>  <br/> |<span data-ttu-id="085f3-116">nvarchar (256), not null</span><span class="sxs-lookup"><span data-stu-id="085f3-116">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="085f3-117">Имя значения.</span><span class="sxs-lookup"><span data-stu-id="085f3-117">Name of the value.</span></span>  <br/> |
   
<span data-ttu-id="085f3-118">**Keys**</span><span class="sxs-lookup"><span data-stu-id="085f3-118">**Keys**</span></span>

|<span data-ttu-id="085f3-119">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="085f3-119">**Column**</span></span>|<span data-ttu-id="085f3-120">**Описание**</span><span class="sxs-lookup"><span data-stu-id="085f3-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="085f3-121">valueID</span><span class="sxs-lookup"><span data-stu-id="085f3-121">valueID</span></span>  <br/> |<span data-ttu-id="085f3-122">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="085f3-122">Primary key.</span></span>  <br/> |
|<span data-ttu-id="085f3-123">attributeID</span><span class="sxs-lookup"><span data-stu-id="085f3-123">attributeID</span></span>  <br/> |<span data-ttu-id="085f3-124">Внешний ключ с поиском в таблице tblEnumAttribute.attributeID.</span><span class="sxs-lookup"><span data-stu-id="085f3-124">Foreign key with lookup in tblEnumAttribute.attributeID table.</span></span>  <br/> |
   
<span data-ttu-id="085f3-125">**Значения таблицы**</span><span class="sxs-lookup"><span data-stu-id="085f3-125">**Table Values**</span></span>

|<span data-ttu-id="085f3-126">**valueID**</span><span class="sxs-lookup"><span data-stu-id="085f3-126">**valueID**</span></span>|<span data-ttu-id="085f3-127">**attributeID**</span><span class="sxs-lookup"><span data-stu-id="085f3-127">**attributeID**</span></span>|<span data-ttu-id="085f3-128">**attributeValue**</span><span class="sxs-lookup"><span data-stu-id="085f3-128">**attributeValue**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="085f3-129">2 </span><span class="sxs-lookup"><span data-stu-id="085f3-129">2</span></span>  <br/> |<span data-ttu-id="085f3-130">1 </span><span class="sxs-lookup"><span data-stu-id="085f3-130">1</span></span>  <br/> |<span data-ttu-id="085f3-131">private</span><span class="sxs-lookup"><span data-stu-id="085f3-131">private</span></span>  <br/> |
|<span data-ttu-id="085f3-132">3 </span><span class="sxs-lookup"><span data-stu-id="085f3-132">3</span></span>  <br/> |<span data-ttu-id="085f3-133">1 </span><span class="sxs-lookup"><span data-stu-id="085f3-133">1</span></span>  <br/> |<span data-ttu-id="085f3-134">scope</span><span class="sxs-lookup"><span data-stu-id="085f3-134">scope</span></span>  <br/> |
|<span data-ttu-id="085f3-135">4 </span><span class="sxs-lookup"><span data-stu-id="085f3-135">4</span></span>  <br/> |<span data-ttu-id="085f3-136">2 </span><span class="sxs-lookup"><span data-stu-id="085f3-136">2</span></span>  <br/> |<span data-ttu-id="085f3-137">normal</span><span class="sxs-lookup"><span data-stu-id="085f3-137">normal</span></span>  <br/> |
|<span data-ttu-id="085f3-138">5 </span><span class="sxs-lookup"><span data-stu-id="085f3-138">5</span></span>  <br/> |<span data-ttu-id="085f3-139">2 </span><span class="sxs-lookup"><span data-stu-id="085f3-139">2</span></span>  <br/> |<span data-ttu-id="085f3-140">аудитория</span><span class="sxs-lookup"><span data-stu-id="085f3-140">auditorium</span></span>  <br/> |
|<span data-ttu-id="085f3-141">6 </span><span class="sxs-lookup"><span data-stu-id="085f3-141">6</span></span>  <br/> |<span data-ttu-id="085f3-142">1 </span><span class="sxs-lookup"><span data-stu-id="085f3-142">1</span></span>  <br/> |<span data-ttu-id="085f3-143">open</span><span class="sxs-lookup"><span data-stu-id="085f3-143">open</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="085f3-144">См. также</span><span class="sxs-lookup"><span data-stu-id="085f3-144">See also</span></span>

[<span data-ttu-id="085f3-145">tblNode</span><span class="sxs-lookup"><span data-stu-id="085f3-145">tblNode</span></span>](tblnode.md)
