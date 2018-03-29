---
title: tblPrincipalMeta
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
ms.openlocfilehash: cfbff018167a3cde68061c3e04eb65d2742e51e9
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="tblprincipalmeta"></a><span data-ttu-id="39e4b-103">tblPrincipalMeta</span><span class="sxs-lookup"><span data-stu-id="39e4b-103">tblPrincipalMeta</span></span>
 
<span data-ttu-id="39e4b-104">tblPrincipalMeta содержит список субъектов, которых необходимо обновить из доменных служб Active Directory.</span><span class="sxs-lookup"><span data-stu-id="39e4b-104">tblPrincipalMeta contains the principals that have to be refreshed from Active Directory Domain Services.</span></span>
  
<span data-ttu-id="39e4b-105">**Столбцы**</span><span class="sxs-lookup"><span data-stu-id="39e4b-105">**Columns**</span></span>

|<span data-ttu-id="39e4b-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="39e4b-106">**Column**</span></span>|<span data-ttu-id="39e4b-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="39e4b-107">**Type**</span></span>|<span data-ttu-id="39e4b-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="39e4b-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="39e4b-109">prinID</span><span class="sxs-lookup"><span data-stu-id="39e4b-109">prinID</span></span>  <br/> |<span data-ttu-id="39e4b-110">int, не null</span><span class="sxs-lookup"><span data-stu-id="39e4b-110">int, not null</span></span>  <br/> |<span data-ttu-id="39e4b-111">Идентификатор субъекта.</span><span class="sxs-lookup"><span data-stu-id="39e4b-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="39e4b-112">prinAffiliationsDirty</span><span class="sxs-lookup"><span data-stu-id="39e4b-112">prinAffiliationsDirty</span></span>  <br/> |<span data-ttu-id="39e4b-113">bit, не может быть null</span><span class="sxs-lookup"><span data-stu-id="39e4b-113">bit, not null</span></span>  <br/> |<span data-ttu-id="39e4b-114">Значение true, если назначения субъектов требуется обновить.</span><span class="sxs-lookup"><span data-stu-id="39e4b-114">True if principal affiliations have to be refreshed.</span></span>  <br/> |
|<span data-ttu-id="39e4b-115">prinAttributesDirty</span><span class="sxs-lookup"><span data-stu-id="39e4b-115">prinAttributesDirty</span></span>  <br/> |<span data-ttu-id="39e4b-116">bit, не может быть null</span><span class="sxs-lookup"><span data-stu-id="39e4b-116">bit, not null</span></span>  <br/> |<span data-ttu-id="39e4b-117">Значение true, если атрибуты которых необходимо обновить.</span><span class="sxs-lookup"><span data-stu-id="39e4b-117">True if principal attributes have to be refreshed.</span></span>  <br/> |
|<span data-ttu-id="39e4b-118">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="39e4b-118">prinDeleted</span></span>  <br/> |<span data-ttu-id="39e4b-119">bit, не может быть null</span><span class="sxs-lookup"><span data-stu-id="39e4b-119">bit, not null</span></span>  <br/> |<span data-ttu-id="39e4b-120">Значение true, если субъект был удален.</span><span class="sxs-lookup"><span data-stu-id="39e4b-120">True if the principal has been deleted.</span></span>  <br/> |
|<span data-ttu-id="39e4b-121">tryCount</span><span class="sxs-lookup"><span data-stu-id="39e4b-121">tryCount</span></span>  <br/> |<span data-ttu-id="39e4b-122">целое</span><span class="sxs-lookup"><span data-stu-id="39e4b-122">int</span></span>  <br/> |<span data-ttu-id="39e4b-123">Число попыток обновления субъекта из Доменных службах Active Directory, предпринятых на данный момент.</span><span class="sxs-lookup"><span data-stu-id="39e4b-123">Number of attempts to refresh the principal from AD DS that have happened so far.</span></span>  <br/> |
|<span data-ttu-id="39e4b-124">lastTry</span><span class="sxs-lookup"><span data-stu-id="39e4b-124">lastTry</span></span>  <br/> |<span data-ttu-id="39e4b-125">datetime</span><span class="sxs-lookup"><span data-stu-id="39e4b-125">datetime</span></span>  <br/> |<span data-ttu-id="39e4b-126">Метка времени последней попытки обновления субъекта.</span><span class="sxs-lookup"><span data-stu-id="39e4b-126">Time stamp from the latest attempt to refresh the principal.</span></span> <span data-ttu-id="39e4b-127">Может иметь значение null, если обновление не предпринята попытка еще.</span><span class="sxs-lookup"><span data-stu-id="39e4b-127">Can be null if no refresh has been attempted yet.</span></span>  <br/> |
|<span data-ttu-id="39e4b-128">nextTry</span><span class="sxs-lookup"><span data-stu-id="39e4b-128">nextTry</span></span>  <br/> |<span data-ttu-id="39e4b-129">datetime</span><span class="sxs-lookup"><span data-stu-id="39e4b-129">datetime</span></span>  <br/> |<span data-ttu-id="39e4b-130">Метка времени для следующего запланированного обновления.</span><span class="sxs-lookup"><span data-stu-id="39e4b-130">Time stamp for the next scheduled refresh.</span></span> <span data-ttu-id="39e4b-131">Может иметь значение null, если дальнейшие обновления по расписанию.</span><span class="sxs-lookup"><span data-stu-id="39e4b-131">Can be null if no further refresh has been scheduled.</span></span>  <br/> |
   
<span data-ttu-id="39e4b-132">**Ключи**</span><span class="sxs-lookup"><span data-stu-id="39e4b-132">**Keys**</span></span>

|<span data-ttu-id="39e4b-133">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="39e4b-133">**Column**</span></span>|<span data-ttu-id="39e4b-134">**Описание**</span><span class="sxs-lookup"><span data-stu-id="39e4b-134">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="39e4b-135">prinID</span><span class="sxs-lookup"><span data-stu-id="39e4b-135">prinID</span></span>  <br/> |<span data-ttu-id="39e4b-136">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="39e4b-136">Primary key.</span></span>  <br/> |
|<span data-ttu-id="39e4b-137">prinID</span><span class="sxs-lookup"><span data-stu-id="39e4b-137">prinID</span></span>  <br/> |<span data-ttu-id="39e4b-138">Внешний ключ с подстановкой в таблице tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="39e4b-138">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

