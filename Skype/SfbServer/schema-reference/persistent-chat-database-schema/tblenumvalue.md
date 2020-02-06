---
title: tblEnumValue
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
description: Тбленумвалуе — это жесткая таблица, содержащая значения видимости и поведения атрибутов, используемых в таблице node.
ms.openlocfilehash: accb9cb4801984bd4b3839cd44e5b7feb8d06baa
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814607"
---
# <a name="tblenumvalue"></a><span data-ttu-id="021a1-103">tblEnumValue</span><span class="sxs-lookup"><span data-stu-id="021a1-103">tblEnumValue</span></span>
 
<span data-ttu-id="021a1-104">Тбленумвалуе — это жесткая таблица, содержащая значения видимости и поведения атрибутов, используемых в таблице node.</span><span class="sxs-lookup"><span data-stu-id="021a1-104">tblEnumValue is a hardcoded table that contains the Visibility and Behavior values of the attributes that are used in the Node table.</span></span>
  
<span data-ttu-id="021a1-105">**Столбцов**</span><span class="sxs-lookup"><span data-stu-id="021a1-105">**Columns**</span></span>

|<span data-ttu-id="021a1-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="021a1-106">**Column**</span></span>|<span data-ttu-id="021a1-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="021a1-107">**Type**</span></span>|<span data-ttu-id="021a1-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="021a1-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="021a1-109">валуеид</span><span class="sxs-lookup"><span data-stu-id="021a1-109">valueID</span></span>  <br/> |<span data-ttu-id="021a1-110">smallint, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="021a1-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="021a1-111">Идентификатор значения.</span><span class="sxs-lookup"><span data-stu-id="021a1-111">ID of the value.</span></span>  <br/> |
|<span data-ttu-id="021a1-112">attributeID</span><span class="sxs-lookup"><span data-stu-id="021a1-112">attributeID</span></span>  <br/> |<span data-ttu-id="021a1-113">smallint, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="021a1-113">smallint, not null</span></span>  <br/> |<span data-ttu-id="021a1-114">Идентификатор атрибута.</span><span class="sxs-lookup"><span data-stu-id="021a1-114">ID of the attribute.</span></span>  <br/> |
|<span data-ttu-id="021a1-115">attributeValue</span><span class="sxs-lookup"><span data-stu-id="021a1-115">attributeValue</span></span>  <br/> |<span data-ttu-id="021a1-116">nvarchar (256), NOT NULL</span><span class="sxs-lookup"><span data-stu-id="021a1-116">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="021a1-117">Имя значения.</span><span class="sxs-lookup"><span data-stu-id="021a1-117">Name of the value.</span></span>  <br/> |
   
<span data-ttu-id="021a1-118">**Параметры**</span><span class="sxs-lookup"><span data-stu-id="021a1-118">**Keys**</span></span>

|<span data-ttu-id="021a1-119">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="021a1-119">**Column**</span></span>|<span data-ttu-id="021a1-120">**Описание**</span><span class="sxs-lookup"><span data-stu-id="021a1-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="021a1-121">валуеид</span><span class="sxs-lookup"><span data-stu-id="021a1-121">valueID</span></span>  <br/> |<span data-ttu-id="021a1-122">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="021a1-122">Primary key.</span></span>  <br/> |
|<span data-ttu-id="021a1-123">attributeID</span><span class="sxs-lookup"><span data-stu-id="021a1-123">attributeID</span></span>  <br/> |<span data-ttu-id="021a1-124">Внешний ключ с подстановкой в таблице Тбленуматтрибуте. attributeID.</span><span class="sxs-lookup"><span data-stu-id="021a1-124">Foreign key with lookup in tblEnumAttribute.attributeID table.</span></span>  <br/> |
   
<span data-ttu-id="021a1-125">**Значения таблицы**</span><span class="sxs-lookup"><span data-stu-id="021a1-125">**Table Values**</span></span>

|<span data-ttu-id="021a1-126">**валуеид**</span><span class="sxs-lookup"><span data-stu-id="021a1-126">**valueID**</span></span>|<span data-ttu-id="021a1-127">**attributeID**</span><span class="sxs-lookup"><span data-stu-id="021a1-127">**attributeID**</span></span>|<span data-ttu-id="021a1-128">**attributeValue**</span><span class="sxs-lookup"><span data-stu-id="021a1-128">**attributeValue**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="021a1-129">2</span><span class="sxs-lookup"><span data-stu-id="021a1-129">2</span></span>  <br/> |<span data-ttu-id="021a1-130">1</span><span class="sxs-lookup"><span data-stu-id="021a1-130">1</span></span>  <br/> |<span data-ttu-id="021a1-131">закрытые</span><span class="sxs-lookup"><span data-stu-id="021a1-131">private</span></span>  <br/> |
|<span data-ttu-id="021a1-132">3</span><span class="sxs-lookup"><span data-stu-id="021a1-132">3</span></span>  <br/> |<span data-ttu-id="021a1-133">1</span><span class="sxs-lookup"><span data-stu-id="021a1-133">1</span></span>  <br/> |<span data-ttu-id="021a1-134">област</span><span class="sxs-lookup"><span data-stu-id="021a1-134">scope</span></span>  <br/> |
|<span data-ttu-id="021a1-135">4</span><span class="sxs-lookup"><span data-stu-id="021a1-135">4</span></span>  <br/> |<span data-ttu-id="021a1-136">2</span><span class="sxs-lookup"><span data-stu-id="021a1-136">2</span></span>  <br/> |<span data-ttu-id="021a1-137">нормальный</span><span class="sxs-lookup"><span data-stu-id="021a1-137">normal</span></span>  <br/> |
|<span data-ttu-id="021a1-138">5</span><span class="sxs-lookup"><span data-stu-id="021a1-138">5</span></span>  <br/> |<span data-ttu-id="021a1-139">2</span><span class="sxs-lookup"><span data-stu-id="021a1-139">2</span></span>  <br/> |<span data-ttu-id="021a1-140">аудиториум</span><span class="sxs-lookup"><span data-stu-id="021a1-140">auditorium</span></span>  <br/> |
|<span data-ttu-id="021a1-141">6</span><span class="sxs-lookup"><span data-stu-id="021a1-141">6</span></span>  <br/> |<span data-ttu-id="021a1-142">1</span><span class="sxs-lookup"><span data-stu-id="021a1-142">1</span></span>  <br/> |<span data-ttu-id="021a1-143">запуска</span><span class="sxs-lookup"><span data-stu-id="021a1-143">open</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="021a1-144">См. также</span><span class="sxs-lookup"><span data-stu-id="021a1-144">See also</span></span>

[<span data-ttu-id="021a1-145">tblNode</span><span class="sxs-lookup"><span data-stu-id="021a1-145">tblNode</span></span>](tblnode.md)
