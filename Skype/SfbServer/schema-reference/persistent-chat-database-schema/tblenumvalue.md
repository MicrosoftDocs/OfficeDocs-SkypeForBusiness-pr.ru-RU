---
title: tblEnumValue
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
description: tblEnumValue — это встроенная таблица, которая содержит значения отображения и поведения атрибутов, используемых в таблице Node.
ms.openlocfilehash: 00ee5a7a7538fa620e438ead5e986f859ef25a6c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929870"
---
# <a name="tblenumvalue"></a><span data-ttu-id="f201a-103">tblEnumValue</span><span class="sxs-lookup"><span data-stu-id="f201a-103">tblEnumValue</span></span>
 
<span data-ttu-id="f201a-104">tblEnumValue — это встроенная таблица, которая содержит значения отображения и поведения атрибутов, используемых в таблице Node.</span><span class="sxs-lookup"><span data-stu-id="f201a-104">tblEnumValue is a hardcoded table that contains the Visibility and Behavior values of the attributes that are used in the Node table.</span></span>
  
<span data-ttu-id="f201a-105">**Столбцы**</span><span class="sxs-lookup"><span data-stu-id="f201a-105">**Columns**</span></span>

|<span data-ttu-id="f201a-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="f201a-106">**Column**</span></span>|<span data-ttu-id="f201a-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="f201a-107">**Type**</span></span>|<span data-ttu-id="f201a-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="f201a-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f201a-109">valueID</span><span class="sxs-lookup"><span data-stu-id="f201a-109">valueID</span></span>  <br/> |<span data-ttu-id="f201a-110">smallint, не может быть null</span><span class="sxs-lookup"><span data-stu-id="f201a-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="f201a-111">ИД значения.</span><span class="sxs-lookup"><span data-stu-id="f201a-111">ID of the value.</span></span>  <br/> |
|<span data-ttu-id="f201a-112">attributeID</span><span class="sxs-lookup"><span data-stu-id="f201a-112">attributeID</span></span>  <br/> |<span data-ttu-id="f201a-113">smallint, не может быть null</span><span class="sxs-lookup"><span data-stu-id="f201a-113">smallint, not null</span></span>  <br/> |<span data-ttu-id="f201a-114">Идентификатор атрибута.</span><span class="sxs-lookup"><span data-stu-id="f201a-114">ID of the attribute.</span></span>  <br/> |
|<span data-ttu-id="f201a-115">attributeValue</span><span class="sxs-lookup"><span data-stu-id="f201a-115">attributeValue</span></span>  <br/> |<span data-ttu-id="f201a-116">nvarchar (256), отлично от null</span><span class="sxs-lookup"><span data-stu-id="f201a-116">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="f201a-117">Имя значения.</span><span class="sxs-lookup"><span data-stu-id="f201a-117">Name of the value.</span></span>  <br/> |
   
<span data-ttu-id="f201a-118">**Ключи**</span><span class="sxs-lookup"><span data-stu-id="f201a-118">**Keys**</span></span>

|<span data-ttu-id="f201a-119">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="f201a-119">**Column**</span></span>|<span data-ttu-id="f201a-120">**Описание**</span><span class="sxs-lookup"><span data-stu-id="f201a-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f201a-121">valueID</span><span class="sxs-lookup"><span data-stu-id="f201a-121">valueID</span></span>  <br/> |<span data-ttu-id="f201a-122">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="f201a-122">Primary key.</span></span>  <br/> |
|<span data-ttu-id="f201a-123">attributeID</span><span class="sxs-lookup"><span data-stu-id="f201a-123">attributeID</span></span>  <br/> |<span data-ttu-id="f201a-124">Внешний ключ с поиском в таблице tblEnumAttribute.attributeID.</span><span class="sxs-lookup"><span data-stu-id="f201a-124">Foreign key with lookup in tblEnumAttribute.attributeID table.</span></span>  <br/> |
   
<span data-ttu-id="f201a-125">**Значения таблицы**</span><span class="sxs-lookup"><span data-stu-id="f201a-125">**Table Values**</span></span>

|<span data-ttu-id="f201a-126">**valueID**</span><span class="sxs-lookup"><span data-stu-id="f201a-126">**valueID**</span></span>|<span data-ttu-id="f201a-127">**attributeID**</span><span class="sxs-lookup"><span data-stu-id="f201a-127">**attributeID**</span></span>|<span data-ttu-id="f201a-128">**attributeValue**</span><span class="sxs-lookup"><span data-stu-id="f201a-128">**attributeValue**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f201a-129">2</span><span class="sxs-lookup"><span data-stu-id="f201a-129">2</span></span>  <br/> |<span data-ttu-id="f201a-130">1</span><span class="sxs-lookup"><span data-stu-id="f201a-130">1</span></span>  <br/> |<span data-ttu-id="f201a-131">закрытые</span><span class="sxs-lookup"><span data-stu-id="f201a-131">private</span></span>  <br/> |
|<span data-ttu-id="f201a-132">3</span><span class="sxs-lookup"><span data-stu-id="f201a-132">3</span></span>  <br/> |<span data-ttu-id="f201a-133">1</span><span class="sxs-lookup"><span data-stu-id="f201a-133">1</span></span>  <br/> |<span data-ttu-id="f201a-134">область</span><span class="sxs-lookup"><span data-stu-id="f201a-134">scope</span></span>  <br/> |
|<span data-ttu-id="f201a-135">4</span><span class="sxs-lookup"><span data-stu-id="f201a-135">4</span></span>  <br/> |<span data-ttu-id="f201a-136">2</span><span class="sxs-lookup"><span data-stu-id="f201a-136">2</span></span>  <br/> |<span data-ttu-id="f201a-137">Обычный</span><span class="sxs-lookup"><span data-stu-id="f201a-137">normal</span></span>  <br/> |
|<span data-ttu-id="f201a-138">5</span><span class="sxs-lookup"><span data-stu-id="f201a-138">5</span></span>  <br/> |<span data-ttu-id="f201a-139">2</span><span class="sxs-lookup"><span data-stu-id="f201a-139">2</span></span>  <br/> |<span data-ttu-id="f201a-140">аудитория</span><span class="sxs-lookup"><span data-stu-id="f201a-140">auditorium</span></span>  <br/> |
|<span data-ttu-id="f201a-141">6</span><span class="sxs-lookup"><span data-stu-id="f201a-141">6</span></span>  <br/> |<span data-ttu-id="f201a-142">1</span><span class="sxs-lookup"><span data-stu-id="f201a-142">1</span></span>  <br/> |<span data-ttu-id="f201a-143">Откройте</span><span class="sxs-lookup"><span data-stu-id="f201a-143">open</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="f201a-144">См. также</span><span class="sxs-lookup"><span data-stu-id="f201a-144">See also</span></span>

[<span data-ttu-id="f201a-145">tblNode</span><span class="sxs-lookup"><span data-stu-id="f201a-145">tblNode</span></span>](tblnode.md)
