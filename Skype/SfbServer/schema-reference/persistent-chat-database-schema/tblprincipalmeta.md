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
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212434"
---
# <a name="tblprincipalmeta"></a><span data-ttu-id="fa466-103">tblPrincipalMeta</span><span class="sxs-lookup"><span data-stu-id="fa466-103">tblPrincipalMeta</span></span>
 
<span data-ttu-id="fa466-104">tblPrincipalMeta содержит список субъектов, которых необходимо обновить из доменных служб Active Directory.</span><span class="sxs-lookup"><span data-stu-id="fa466-104">tblPrincipalMeta contains the principals that have to be refreshed from Active Directory Domain Services.</span></span>
  
<span data-ttu-id="fa466-105">**Столбцы**</span><span class="sxs-lookup"><span data-stu-id="fa466-105">**Columns**</span></span>

|<span data-ttu-id="fa466-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="fa466-106">**Column**</span></span>|<span data-ttu-id="fa466-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="fa466-107">**Type**</span></span>|<span data-ttu-id="fa466-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="fa466-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="fa466-109">prinID</span><span class="sxs-lookup"><span data-stu-id="fa466-109">prinID</span></span>  <br/> |<span data-ttu-id="fa466-110">int, не null</span><span class="sxs-lookup"><span data-stu-id="fa466-110">int, not null</span></span>  <br/> |<span data-ttu-id="fa466-111">Идентификатор субъекта.</span><span class="sxs-lookup"><span data-stu-id="fa466-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="fa466-112">prinAffiliationsDirty</span><span class="sxs-lookup"><span data-stu-id="fa466-112">prinAffiliationsDirty</span></span>  <br/> |<span data-ttu-id="fa466-113">bit, не может быть null</span><span class="sxs-lookup"><span data-stu-id="fa466-113">bit, not null</span></span>  <br/> |<span data-ttu-id="fa466-114">Значение true, если назначения субъектов требуется обновить.</span><span class="sxs-lookup"><span data-stu-id="fa466-114">True if principal affiliations have to be refreshed.</span></span>  <br/> |
|<span data-ttu-id="fa466-115">prinAttributesDirty</span><span class="sxs-lookup"><span data-stu-id="fa466-115">prinAttributesDirty</span></span>  <br/> |<span data-ttu-id="fa466-116">bit, не может быть null</span><span class="sxs-lookup"><span data-stu-id="fa466-116">bit, not null</span></span>  <br/> |<span data-ttu-id="fa466-117">Значение true, если атрибуты которых необходимо обновить.</span><span class="sxs-lookup"><span data-stu-id="fa466-117">True if principal attributes have to be refreshed.</span></span>  <br/> |
|<span data-ttu-id="fa466-118">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="fa466-118">prinDeleted</span></span>  <br/> |<span data-ttu-id="fa466-119">bit, не может быть null</span><span class="sxs-lookup"><span data-stu-id="fa466-119">bit, not null</span></span>  <br/> |<span data-ttu-id="fa466-120">Значение true, если субъект был удален.</span><span class="sxs-lookup"><span data-stu-id="fa466-120">True if the principal has been deleted.</span></span>  <br/> |
|<span data-ttu-id="fa466-121">tryCount</span><span class="sxs-lookup"><span data-stu-id="fa466-121">tryCount</span></span>  <br/> |<span data-ttu-id="fa466-122">целое</span><span class="sxs-lookup"><span data-stu-id="fa466-122">int</span></span>  <br/> |<span data-ttu-id="fa466-123">Число попыток обновления субъекта из Доменных службах Active Directory, предпринятых на данный момент.</span><span class="sxs-lookup"><span data-stu-id="fa466-123">Number of attempts to refresh the principal from AD DS that have happened so far.</span></span>  <br/> |
|<span data-ttu-id="fa466-124">lastTry</span><span class="sxs-lookup"><span data-stu-id="fa466-124">lastTry</span></span>  <br/> |<span data-ttu-id="fa466-125">datetime</span><span class="sxs-lookup"><span data-stu-id="fa466-125">datetime</span></span>  <br/> |<span data-ttu-id="fa466-126">Метка времени последней попытки обновления субъекта.</span><span class="sxs-lookup"><span data-stu-id="fa466-126">Time stamp from the latest attempt to refresh the principal.</span></span> <span data-ttu-id="fa466-127">Может иметь значение null, если обновление не предпринята попытка еще.</span><span class="sxs-lookup"><span data-stu-id="fa466-127">Can be null if no refresh has been attempted yet.</span></span>  <br/> |
|<span data-ttu-id="fa466-128">nextTry</span><span class="sxs-lookup"><span data-stu-id="fa466-128">nextTry</span></span>  <br/> |<span data-ttu-id="fa466-129">datetime</span><span class="sxs-lookup"><span data-stu-id="fa466-129">datetime</span></span>  <br/> |<span data-ttu-id="fa466-130">Метка времени для следующего запланированного обновления.</span><span class="sxs-lookup"><span data-stu-id="fa466-130">Time stamp for the next scheduled refresh.</span></span> <span data-ttu-id="fa466-131">Может иметь значение null, если дальнейшие обновления по расписанию.</span><span class="sxs-lookup"><span data-stu-id="fa466-131">Can be null if no further refresh has been scheduled.</span></span>  <br/> |
   
<span data-ttu-id="fa466-132">**Ключи**</span><span class="sxs-lookup"><span data-stu-id="fa466-132">**Keys**</span></span>

|<span data-ttu-id="fa466-133">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="fa466-133">**Column**</span></span>|<span data-ttu-id="fa466-134">**Описание**</span><span class="sxs-lookup"><span data-stu-id="fa466-134">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="fa466-135">prinID</span><span class="sxs-lookup"><span data-stu-id="fa466-135">prinID</span></span>  <br/> |<span data-ttu-id="fa466-136">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="fa466-136">Primary key.</span></span>  <br/> |
|<span data-ttu-id="fa466-137">prinID</span><span class="sxs-lookup"><span data-stu-id="fa466-137">prinID</span></span>  <br/> |<span data-ttu-id="fa466-138">Внешний ключ с подстановкой в таблице tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="fa466-138">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

