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
localization_priority: Normal
ms.assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
description: Тбленумвалуе — это жесткая таблица, содержащая значения видимости и поведения атрибутов, используемых в таблице node.
ms.openlocfilehash: bf1ddf75fc7b7fd78c85f47626b465a4d74e5ca2
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295428"
---
# <a name="tblenumvalue"></a><span data-ttu-id="1bb41-103">tblEnumValue</span><span class="sxs-lookup"><span data-stu-id="1bb41-103">tblEnumValue</span></span>
 
<span data-ttu-id="1bb41-104">Тбленумвалуе — это жесткая таблица, содержащая значения видимости и поведения атрибутов, используемых в таблице node.</span><span class="sxs-lookup"><span data-stu-id="1bb41-104">tblEnumValue is a hardcoded table that contains the Visibility and Behavior values of the attributes that are used in the Node table.</span></span>
  
<span data-ttu-id="1bb41-105">**Столбцов**</span><span class="sxs-lookup"><span data-stu-id="1bb41-105">**Columns**</span></span>

|<span data-ttu-id="1bb41-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="1bb41-106">**Column**</span></span>|<span data-ttu-id="1bb41-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="1bb41-107">**Type**</span></span>|<span data-ttu-id="1bb41-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="1bb41-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1bb41-109">Валуеид</span><span class="sxs-lookup"><span data-stu-id="1bb41-109">valueID</span></span>  <br/> |<span data-ttu-id="1bb41-110">smallint, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="1bb41-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="1bb41-111">Идентификатор значения.</span><span class="sxs-lookup"><span data-stu-id="1bb41-111">ID of the value.</span></span>  <br/> |
|<span data-ttu-id="1bb41-112">attributeID</span><span class="sxs-lookup"><span data-stu-id="1bb41-112">attributeID</span></span>  <br/> |<span data-ttu-id="1bb41-113">smallint, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="1bb41-113">smallint, not null</span></span>  <br/> |<span data-ttu-id="1bb41-114">Идентификатор атрибута.</span><span class="sxs-lookup"><span data-stu-id="1bb41-114">ID of the attribute.</span></span>  <br/> |
|<span data-ttu-id="1bb41-115">attributeValue</span><span class="sxs-lookup"><span data-stu-id="1bb41-115">attributeValue</span></span>  <br/> |<span data-ttu-id="1bb41-116">nvarchar (256), NOT NULL</span><span class="sxs-lookup"><span data-stu-id="1bb41-116">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="1bb41-117">Имя значения.</span><span class="sxs-lookup"><span data-stu-id="1bb41-117">Name of the value.</span></span>  <br/> |
   
<span data-ttu-id="1bb41-118">**Параметры**</span><span class="sxs-lookup"><span data-stu-id="1bb41-118">**Keys**</span></span>

|<span data-ttu-id="1bb41-119">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="1bb41-119">**Column**</span></span>|<span data-ttu-id="1bb41-120">**Описание**</span><span class="sxs-lookup"><span data-stu-id="1bb41-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1bb41-121">Валуеид</span><span class="sxs-lookup"><span data-stu-id="1bb41-121">valueID</span></span>  <br/> |<span data-ttu-id="1bb41-122">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="1bb41-122">Primary key.</span></span>  <br/> |
|<span data-ttu-id="1bb41-123">attributeID</span><span class="sxs-lookup"><span data-stu-id="1bb41-123">attributeID</span></span>  <br/> |<span data-ttu-id="1bb41-124">Внешний ключ с подстановкой в таблице Тбленуматтрибуте. attributeID.</span><span class="sxs-lookup"><span data-stu-id="1bb41-124">Foreign key with lookup in tblEnumAttribute.attributeID table.</span></span>  <br/> |
   
<span data-ttu-id="1bb41-125">**Значения таблицы**</span><span class="sxs-lookup"><span data-stu-id="1bb41-125">**Table Values**</span></span>

|<span data-ttu-id="1bb41-126">**Валуеид**</span><span class="sxs-lookup"><span data-stu-id="1bb41-126">**valueID**</span></span>|<span data-ttu-id="1bb41-127">**attributeID**</span><span class="sxs-lookup"><span data-stu-id="1bb41-127">**attributeID**</span></span>|<span data-ttu-id="1bb41-128">**attributeValue**</span><span class="sxs-lookup"><span data-stu-id="1bb41-128">**attributeValue**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1bb41-129">2</span><span class="sxs-lookup"><span data-stu-id="1bb41-129">2</span></span>  <br/> |<span data-ttu-id="1bb41-130">1</span><span class="sxs-lookup"><span data-stu-id="1bb41-130">1</span></span>  <br/> |<span data-ttu-id="1bb41-131">закрытые</span><span class="sxs-lookup"><span data-stu-id="1bb41-131">private</span></span>  <br/> |
|<span data-ttu-id="1bb41-132">3</span><span class="sxs-lookup"><span data-stu-id="1bb41-132">3</span></span>  <br/> |<span data-ttu-id="1bb41-133">1</span><span class="sxs-lookup"><span data-stu-id="1bb41-133">1</span></span>  <br/> |<span data-ttu-id="1bb41-134">област</span><span class="sxs-lookup"><span data-stu-id="1bb41-134">scope</span></span>  <br/> |
|<span data-ttu-id="1bb41-135">4</span><span class="sxs-lookup"><span data-stu-id="1bb41-135">4</span></span>  <br/> |<span data-ttu-id="1bb41-136">2</span><span class="sxs-lookup"><span data-stu-id="1bb41-136">2</span></span>  <br/> |<span data-ttu-id="1bb41-137">нормальный</span><span class="sxs-lookup"><span data-stu-id="1bb41-137">normal</span></span>  <br/> |
|<span data-ttu-id="1bb41-138">5</span><span class="sxs-lookup"><span data-stu-id="1bb41-138">5</span></span>  <br/> |<span data-ttu-id="1bb41-139">2</span><span class="sxs-lookup"><span data-stu-id="1bb41-139">2</span></span>  <br/> |<span data-ttu-id="1bb41-140">Аудиториум</span><span class="sxs-lookup"><span data-stu-id="1bb41-140">auditorium</span></span>  <br/> |
|<span data-ttu-id="1bb41-141">6</span><span class="sxs-lookup"><span data-stu-id="1bb41-141">6</span></span>  <br/> |<span data-ttu-id="1bb41-142">1</span><span class="sxs-lookup"><span data-stu-id="1bb41-142">1</span></span>  <br/> |<span data-ttu-id="1bb41-143">запуска</span><span class="sxs-lookup"><span data-stu-id="1bb41-143">open</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="1bb41-144">См. также</span><span class="sxs-lookup"><span data-stu-id="1bb41-144">See also</span></span>

[<span data-ttu-id="1bb41-145">tblNode</span><span class="sxs-lookup"><span data-stu-id="1bb41-145">tblNode</span></span>](tblnode.md)
