---
title: tblPrincipalMeta
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 808490d4-7d6d-47a2-b8af-b5940d47073b
description: tblPrincipalMeta содержит список субъектов, которых необходимо обновить из доменных служб Active Directory.
ms.openlocfilehash: 049a273f7134ecb945e62da39469bcaf0defbffb
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30889609"
---
# <a name="tblprincipalmeta"></a><span data-ttu-id="04803-103">tblPrincipalMeta</span><span class="sxs-lookup"><span data-stu-id="04803-103">tblPrincipalMeta</span></span>
 
<span data-ttu-id="04803-104">tblPrincipalMeta содержит список субъектов, которых необходимо обновить из доменных служб Active Directory.</span><span class="sxs-lookup"><span data-stu-id="04803-104">tblPrincipalMeta contains the principals that have to be refreshed from Active Directory Domain Services.</span></span>
  
<span data-ttu-id="04803-105">**Столбцы**</span><span class="sxs-lookup"><span data-stu-id="04803-105">**Columns**</span></span>

|<span data-ttu-id="04803-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="04803-106">**Column**</span></span>|<span data-ttu-id="04803-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="04803-107">**Type**</span></span>|<span data-ttu-id="04803-108">**Описание**.</span><span class="sxs-lookup"><span data-stu-id="04803-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="04803-109">prinID</span><span class="sxs-lookup"><span data-stu-id="04803-109">prinID</span></span>  <br/> |<span data-ttu-id="04803-110">int, не null</span><span class="sxs-lookup"><span data-stu-id="04803-110">int, not null</span></span>  <br/> |<span data-ttu-id="04803-111">Идентификатор субъекта.</span><span class="sxs-lookup"><span data-stu-id="04803-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="04803-112">prinAffiliationsDirty</span><span class="sxs-lookup"><span data-stu-id="04803-112">prinAffiliationsDirty</span></span>  <br/> |<span data-ttu-id="04803-113">bit, не может быть null</span><span class="sxs-lookup"><span data-stu-id="04803-113">bit, not null</span></span>  <br/> |<span data-ttu-id="04803-114">Значение true, если назначения субъектов требуется обновить.</span><span class="sxs-lookup"><span data-stu-id="04803-114">True if principal affiliations have to be refreshed.</span></span>  <br/> |
|<span data-ttu-id="04803-115">prinAttributesDirty</span><span class="sxs-lookup"><span data-stu-id="04803-115">prinAttributesDirty</span></span>  <br/> |<span data-ttu-id="04803-116">bit, не может быть null</span><span class="sxs-lookup"><span data-stu-id="04803-116">bit, not null</span></span>  <br/> |<span data-ttu-id="04803-117">Значение true, если атрибуты которых необходимо обновить.</span><span class="sxs-lookup"><span data-stu-id="04803-117">True if principal attributes have to be refreshed.</span></span>  <br/> |
|<span data-ttu-id="04803-118">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="04803-118">prinDeleted</span></span>  <br/> |<span data-ttu-id="04803-119">bit, не может быть null</span><span class="sxs-lookup"><span data-stu-id="04803-119">bit, not null</span></span>  <br/> |<span data-ttu-id="04803-120">Значение true, если субъект был удален.</span><span class="sxs-lookup"><span data-stu-id="04803-120">True if the principal has been deleted.</span></span>  <br/> |
|<span data-ttu-id="04803-121">tryCount</span><span class="sxs-lookup"><span data-stu-id="04803-121">tryCount</span></span>  <br/> |<span data-ttu-id="04803-122">целое</span><span class="sxs-lookup"><span data-stu-id="04803-122">int</span></span>  <br/> |<span data-ttu-id="04803-123">Число попыток обновления субъекта из Доменных службах Active Directory, предпринятых на данный момент.</span><span class="sxs-lookup"><span data-stu-id="04803-123">Number of attempts to refresh the principal from AD DS that have happened so far.</span></span>  <br/> |
|<span data-ttu-id="04803-124">lastTry</span><span class="sxs-lookup"><span data-stu-id="04803-124">lastTry</span></span>  <br/> |<span data-ttu-id="04803-125">datetime</span><span class="sxs-lookup"><span data-stu-id="04803-125">datetime</span></span>  <br/> |<span data-ttu-id="04803-126">Метка времени последней попытки обновления субъекта.</span><span class="sxs-lookup"><span data-stu-id="04803-126">Time stamp from the latest attempt to refresh the principal.</span></span> <span data-ttu-id="04803-127">Может иметь значение null, если обновление не предпринята попытка еще.</span><span class="sxs-lookup"><span data-stu-id="04803-127">Can be null if no refresh has been attempted yet.</span></span>  <br/> |
|<span data-ttu-id="04803-128">nextTry</span><span class="sxs-lookup"><span data-stu-id="04803-128">nextTry</span></span>  <br/> |<span data-ttu-id="04803-129">datetime</span><span class="sxs-lookup"><span data-stu-id="04803-129">datetime</span></span>  <br/> |<span data-ttu-id="04803-130">Метка времени для следующего запланированного обновления.</span><span class="sxs-lookup"><span data-stu-id="04803-130">Time stamp for the next scheduled refresh.</span></span> <span data-ttu-id="04803-131">Может иметь значение null, если дальнейшие обновления по расписанию.</span><span class="sxs-lookup"><span data-stu-id="04803-131">Can be null if no further refresh has been scheduled.</span></span>  <br/> |
   
<span data-ttu-id="04803-132">**Ключи**</span><span class="sxs-lookup"><span data-stu-id="04803-132">**Keys**</span></span>

|<span data-ttu-id="04803-133">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="04803-133">**Column**</span></span>|<span data-ttu-id="04803-134">**Описание**.</span><span class="sxs-lookup"><span data-stu-id="04803-134">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="04803-135">prinID</span><span class="sxs-lookup"><span data-stu-id="04803-135">prinID</span></span>  <br/> |<span data-ttu-id="04803-136">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="04803-136">Primary key.</span></span>  <br/> |
|<span data-ttu-id="04803-137">prinID</span><span class="sxs-lookup"><span data-stu-id="04803-137">prinID</span></span>  <br/> |<span data-ttu-id="04803-138">Внешний ключ с подстановкой в таблице tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="04803-138">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

