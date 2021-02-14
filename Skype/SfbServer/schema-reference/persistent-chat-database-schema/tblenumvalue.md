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
# <a name="tblenumvalue"></a><span data-ttu-id="badae-103">tblEnumValue</span><span class="sxs-lookup"><span data-stu-id="badae-103">tblEnumValue</span></span>
 
<span data-ttu-id="badae-104">tblEnumValue — это встроенная таблица, которая содержит значения отображения и поведения атрибутов, используемых в таблице Node.</span><span class="sxs-lookup"><span data-stu-id="badae-104">tblEnumValue is a hardcoded table that contains the Visibility and Behavior values of the attributes that are used in the Node table.</span></span>
  
<span data-ttu-id="badae-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="badae-105">**Columns**</span></span>

|<span data-ttu-id="badae-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="badae-106">**Column**</span></span>|<span data-ttu-id="badae-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="badae-107">**Type**</span></span>|<span data-ttu-id="badae-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="badae-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="badae-109">valueID</span><span class="sxs-lookup"><span data-stu-id="badae-109">valueID</span></span>  <br/> |<span data-ttu-id="badae-110">smallint, not null</span><span class="sxs-lookup"><span data-stu-id="badae-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="badae-111">ИД значения.</span><span class="sxs-lookup"><span data-stu-id="badae-111">ID of the value.</span></span>  <br/> |
|<span data-ttu-id="badae-112">attributeID</span><span class="sxs-lookup"><span data-stu-id="badae-112">attributeID</span></span>  <br/> |<span data-ttu-id="badae-113">smallint, не может быть null</span><span class="sxs-lookup"><span data-stu-id="badae-113">smallint, not null</span></span>  <br/> |<span data-ttu-id="badae-114">ИД атрибута.</span><span class="sxs-lookup"><span data-stu-id="badae-114">ID of the attribute.</span></span>  <br/> |
|<span data-ttu-id="badae-115">attributeValue</span><span class="sxs-lookup"><span data-stu-id="badae-115">attributeValue</span></span>  <br/> |<span data-ttu-id="badae-116">nvarchar (256), not null</span><span class="sxs-lookup"><span data-stu-id="badae-116">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="badae-117">Имя значения.</span><span class="sxs-lookup"><span data-stu-id="badae-117">Name of the value.</span></span>  <br/> |
   
<span data-ttu-id="badae-118">**Keys**</span><span class="sxs-lookup"><span data-stu-id="badae-118">**Keys**</span></span>

|<span data-ttu-id="badae-119">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="badae-119">**Column**</span></span>|<span data-ttu-id="badae-120">**Описание**</span><span class="sxs-lookup"><span data-stu-id="badae-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="badae-121">valueID</span><span class="sxs-lookup"><span data-stu-id="badae-121">valueID</span></span>  <br/> |<span data-ttu-id="badae-122">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="badae-122">Primary key.</span></span>  <br/> |
|<span data-ttu-id="badae-123">attributeID</span><span class="sxs-lookup"><span data-stu-id="badae-123">attributeID</span></span>  <br/> |<span data-ttu-id="badae-124">Внешний ключ с поиском в таблице tblEnumAttribute.attributeID.</span><span class="sxs-lookup"><span data-stu-id="badae-124">Foreign key with lookup in tblEnumAttribute.attributeID table.</span></span>  <br/> |
   
<span data-ttu-id="badae-125">**Значения таблицы**</span><span class="sxs-lookup"><span data-stu-id="badae-125">**Table Values**</span></span>

|<span data-ttu-id="badae-126">**valueID**</span><span class="sxs-lookup"><span data-stu-id="badae-126">**valueID**</span></span>|<span data-ttu-id="badae-127">**attributeID**</span><span class="sxs-lookup"><span data-stu-id="badae-127">**attributeID**</span></span>|<span data-ttu-id="badae-128">**attributeValue**</span><span class="sxs-lookup"><span data-stu-id="badae-128">**attributeValue**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="badae-129">2 </span><span class="sxs-lookup"><span data-stu-id="badae-129">2</span></span>  <br/> |<span data-ttu-id="badae-130">1 </span><span class="sxs-lookup"><span data-stu-id="badae-130">1</span></span>  <br/> |<span data-ttu-id="badae-131">private</span><span class="sxs-lookup"><span data-stu-id="badae-131">private</span></span>  <br/> |
|<span data-ttu-id="badae-132">3 </span><span class="sxs-lookup"><span data-stu-id="badae-132">3</span></span>  <br/> |<span data-ttu-id="badae-133">1 </span><span class="sxs-lookup"><span data-stu-id="badae-133">1</span></span>  <br/> |<span data-ttu-id="badae-134">scope</span><span class="sxs-lookup"><span data-stu-id="badae-134">scope</span></span>  <br/> |
|<span data-ttu-id="badae-135">4 </span><span class="sxs-lookup"><span data-stu-id="badae-135">4</span></span>  <br/> |<span data-ttu-id="badae-136">2 </span><span class="sxs-lookup"><span data-stu-id="badae-136">2</span></span>  <br/> |<span data-ttu-id="badae-137">normal</span><span class="sxs-lookup"><span data-stu-id="badae-137">normal</span></span>  <br/> |
|<span data-ttu-id="badae-138">5 </span><span class="sxs-lookup"><span data-stu-id="badae-138">5</span></span>  <br/> |<span data-ttu-id="badae-139">2 </span><span class="sxs-lookup"><span data-stu-id="badae-139">2</span></span>  <br/> |<span data-ttu-id="badae-140">аудитория</span><span class="sxs-lookup"><span data-stu-id="badae-140">auditorium</span></span>  <br/> |
|<span data-ttu-id="badae-141">6 </span><span class="sxs-lookup"><span data-stu-id="badae-141">6</span></span>  <br/> |<span data-ttu-id="badae-142">1 </span><span class="sxs-lookup"><span data-stu-id="badae-142">1</span></span>  <br/> |<span data-ttu-id="badae-143">open</span><span class="sxs-lookup"><span data-stu-id="badae-143">open</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="badae-144">См. также</span><span class="sxs-lookup"><span data-stu-id="badae-144">See also</span></span>

[<span data-ttu-id="badae-145">tblNode</span><span class="sxs-lookup"><span data-stu-id="badae-145">tblNode</span></span>](tblnode.md)
