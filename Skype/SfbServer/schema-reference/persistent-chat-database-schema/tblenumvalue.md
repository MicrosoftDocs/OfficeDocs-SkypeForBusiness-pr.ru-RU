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
ms.openlocfilehash: 4e17e5fc167342c106e7b5354d90c7fc284785c3
ms.sourcegitcommit: b14cfca231b618ec28cf9f4efe11cb3e8aceb34b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/19/2018
ms.locfileid: "19505078"
---
# <a name="tblenumvalue"></a><span data-ttu-id="40fb3-103">tblEnumValue</span><span class="sxs-lookup"><span data-stu-id="40fb3-103">tblEnumValue</span></span>
 
<span data-ttu-id="40fb3-104">tblEnumValue — это встроенная таблица, которая содержит значения отображения и поведения атрибутов, используемых в таблице Node.</span><span class="sxs-lookup"><span data-stu-id="40fb3-104">tblEnumValue is a hardcoded table that contains the Visibility and Behavior values of the attributes that are used in the Node table.</span></span>
  
<span data-ttu-id="40fb3-105">**Столбцы**</span><span class="sxs-lookup"><span data-stu-id="40fb3-105">**Columns**</span></span>

|<span data-ttu-id="40fb3-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="40fb3-106">**Column**</span></span>|<span data-ttu-id="40fb3-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="40fb3-107">**Type**</span></span>|<span data-ttu-id="40fb3-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="40fb3-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="40fb3-109">valueID</span><span class="sxs-lookup"><span data-stu-id="40fb3-109">valueID</span></span>  <br/> |<span data-ttu-id="40fb3-110">smallint, не может быть null</span><span class="sxs-lookup"><span data-stu-id="40fb3-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="40fb3-111">ИД значения.</span><span class="sxs-lookup"><span data-stu-id="40fb3-111">ID of the value.</span></span>  <br/> |
|<span data-ttu-id="40fb3-112">attributeID</span><span class="sxs-lookup"><span data-stu-id="40fb3-112">attributeID</span></span>  <br/> |<span data-ttu-id="40fb3-113">smallint, не может быть null</span><span class="sxs-lookup"><span data-stu-id="40fb3-113">smallint, not null</span></span>  <br/> |<span data-ttu-id="40fb3-114">Идентификатор атрибута.</span><span class="sxs-lookup"><span data-stu-id="40fb3-114">ID of the attribute.</span></span>  <br/> |
|<span data-ttu-id="40fb3-115">attributeValue</span><span class="sxs-lookup"><span data-stu-id="40fb3-115">attributeValue</span></span>  <br/> |<span data-ttu-id="40fb3-116">nvarchar (256), отлично от null</span><span class="sxs-lookup"><span data-stu-id="40fb3-116">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="40fb3-117">Имя значения.</span><span class="sxs-lookup"><span data-stu-id="40fb3-117">Name of the value.</span></span>  <br/> |
   
<span data-ttu-id="40fb3-118">**Ключи**</span><span class="sxs-lookup"><span data-stu-id="40fb3-118">**Keys**</span></span>

|<span data-ttu-id="40fb3-119">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="40fb3-119">**Column**</span></span>|<span data-ttu-id="40fb3-120">**Описание**</span><span class="sxs-lookup"><span data-stu-id="40fb3-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="40fb3-121">valueID</span><span class="sxs-lookup"><span data-stu-id="40fb3-121">valueID</span></span>  <br/> |<span data-ttu-id="40fb3-122">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="40fb3-122">Primary key.</span></span>  <br/> |
|<span data-ttu-id="40fb3-123">attributeID</span><span class="sxs-lookup"><span data-stu-id="40fb3-123">attributeID</span></span>  <br/> |<span data-ttu-id="40fb3-124">Внешний ключ с поиском в таблице tblEnumAttribute.attributeID.</span><span class="sxs-lookup"><span data-stu-id="40fb3-124">Foreign key with lookup in tblEnumAttribute.attributeID table.</span></span>  <br/> |
   
<span data-ttu-id="40fb3-125">**Значения таблицы**</span><span class="sxs-lookup"><span data-stu-id="40fb3-125">**Table Values**</span></span>

|<span data-ttu-id="40fb3-126">**valueID**</span><span class="sxs-lookup"><span data-stu-id="40fb3-126">**valueID**</span></span>|<span data-ttu-id="40fb3-127">**attributeID**</span><span class="sxs-lookup"><span data-stu-id="40fb3-127">**attributeID**</span></span>|<span data-ttu-id="40fb3-128">**attributeValue**</span><span class="sxs-lookup"><span data-stu-id="40fb3-128">**attributeValue**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="40fb3-129">2</span><span class="sxs-lookup"><span data-stu-id="40fb3-129">2</span></span>  <br/> |<span data-ttu-id="40fb3-130">1</span><span class="sxs-lookup"><span data-stu-id="40fb3-130">1</span></span>  <br/> |<span data-ttu-id="40fb3-131">закрытые</span><span class="sxs-lookup"><span data-stu-id="40fb3-131">private</span></span>  <br/> |
|<span data-ttu-id="40fb3-132">3</span><span class="sxs-lookup"><span data-stu-id="40fb3-132">3</span></span>  <br/> |<span data-ttu-id="40fb3-133">1</span><span class="sxs-lookup"><span data-stu-id="40fb3-133">1</span></span>  <br/> |<span data-ttu-id="40fb3-134">область</span><span class="sxs-lookup"><span data-stu-id="40fb3-134">scope</span></span>  <br/> |
|<span data-ttu-id="40fb3-135">4</span><span class="sxs-lookup"><span data-stu-id="40fb3-135">4</span></span>  <br/> |<span data-ttu-id="40fb3-136">2</span><span class="sxs-lookup"><span data-stu-id="40fb3-136">2</span></span>  <br/> |<span data-ttu-id="40fb3-137">Обычный</span><span class="sxs-lookup"><span data-stu-id="40fb3-137">normal</span></span>  <br/> |
|<span data-ttu-id="40fb3-138">5</span><span class="sxs-lookup"><span data-stu-id="40fb3-138">5</span></span>  <br/> |<span data-ttu-id="40fb3-139">2</span><span class="sxs-lookup"><span data-stu-id="40fb3-139">2</span></span>  <br/> |<span data-ttu-id="40fb3-140">аудитория</span><span class="sxs-lookup"><span data-stu-id="40fb3-140">auditorium</span></span>  <br/> |
|<span data-ttu-id="40fb3-141">6</span><span class="sxs-lookup"><span data-stu-id="40fb3-141">6</span></span>  <br/> |<span data-ttu-id="40fb3-142">1</span><span class="sxs-lookup"><span data-stu-id="40fb3-142">1</span></span>  <br/> |<span data-ttu-id="40fb3-143">Откройте</span><span class="sxs-lookup"><span data-stu-id="40fb3-143">open</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="40fb3-144">См. также</span><span class="sxs-lookup"><span data-stu-id="40fb3-144">See also</span></span>

[<span data-ttu-id="40fb3-145">tblNode</span><span class="sxs-lookup"><span data-stu-id="40fb3-145">tblNode</span></span>](tblnode.md)