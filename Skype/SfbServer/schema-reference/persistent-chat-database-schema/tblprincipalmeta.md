---
title: tblPrincipalMeta
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
ms.assetid: 808490d4-7d6d-47a2-b8af-b5940d47073b
description: tblPrincipalMeta содержит имена, которые необходимо обновить из доменных служб Active Directory.
ms.openlocfilehash: e10b56a8a3a1c25f73cd1a07f4fdcde18c6f1215
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831549"
---
# <a name="tblprincipalmeta"></a><span data-ttu-id="e44a0-103">tblPrincipalMeta</span><span class="sxs-lookup"><span data-stu-id="e44a0-103">tblPrincipalMeta</span></span>
 
<span data-ttu-id="e44a0-104">tblPrincipalMeta содержит имена, которые необходимо обновить из доменных служб Active Directory.</span><span class="sxs-lookup"><span data-stu-id="e44a0-104">tblPrincipalMeta contains the principals that have to be refreshed from Active Directory Domain Services.</span></span>
  
<span data-ttu-id="e44a0-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="e44a0-105">**Columns**</span></span>

|<span data-ttu-id="e44a0-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="e44a0-106">**Column**</span></span>|<span data-ttu-id="e44a0-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="e44a0-107">**Type**</span></span>|<span data-ttu-id="e44a0-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="e44a0-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e44a0-109">prinID</span><span class="sxs-lookup"><span data-stu-id="e44a0-109">prinID</span></span>  <br/> |<span data-ttu-id="e44a0-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="e44a0-110">int, not null</span></span>  <br/> |<span data-ttu-id="e44a0-111">ИД субъекта.</span><span class="sxs-lookup"><span data-stu-id="e44a0-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="e44a0-112">prinAffiliationsDirty</span><span class="sxs-lookup"><span data-stu-id="e44a0-112">prinAffiliationsDirty</span></span>  <br/> |<span data-ttu-id="e44a0-113">bit, не равно null</span><span class="sxs-lookup"><span data-stu-id="e44a0-113">bit, not null</span></span>  <br/> |<span data-ttu-id="e44a0-114">Значение true, если назначения субъектов требуется обновить.</span><span class="sxs-lookup"><span data-stu-id="e44a0-114">True if principal affiliations have to be refreshed.</span></span>  <br/> |
|<span data-ttu-id="e44a0-115">prinAttributesDirty</span><span class="sxs-lookup"><span data-stu-id="e44a0-115">prinAttributesDirty</span></span>  <br/> |<span data-ttu-id="e44a0-116">bit, не равно null</span><span class="sxs-lookup"><span data-stu-id="e44a0-116">bit, not null</span></span>  <br/> |<span data-ttu-id="e44a0-117">Значение true, если атрибуты субъектов требуется обновить.</span><span class="sxs-lookup"><span data-stu-id="e44a0-117">True if principal attributes have to be refreshed.</span></span>  <br/> |
|<span data-ttu-id="e44a0-118">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="e44a0-118">prinDeleted</span></span>  <br/> |<span data-ttu-id="e44a0-119">bit, не равно null</span><span class="sxs-lookup"><span data-stu-id="e44a0-119">bit, not null</span></span>  <br/> |<span data-ttu-id="e44a0-120">Значение true, если субъект был удален.</span><span class="sxs-lookup"><span data-stu-id="e44a0-120">True if the principal has been deleted.</span></span>  <br/> |
|<span data-ttu-id="e44a0-121">tryCount</span><span class="sxs-lookup"><span data-stu-id="e44a0-121">tryCount</span></span>  <br/> |<span data-ttu-id="e44a0-122">int</span><span class="sxs-lookup"><span data-stu-id="e44a0-122">int</span></span>  <br/> |<span data-ttu-id="e44a0-123">Число попыток обновления субъекта из доменных служб Active Directory, предпринятых на данный момент.</span><span class="sxs-lookup"><span data-stu-id="e44a0-123">Number of attempts to refresh the principal from AD DS that have happened so far.</span></span>  <br/> |
|<span data-ttu-id="e44a0-124">lastTry</span><span class="sxs-lookup"><span data-stu-id="e44a0-124">lastTry</span></span>  <br/> |<span data-ttu-id="e44a0-125">datetime</span><span class="sxs-lookup"><span data-stu-id="e44a0-125">datetime</span></span>  <br/> |<span data-ttu-id="e44a0-p101">Метка времени для последней попытки обновления субъекта. Может иметь значение null, если попытки обновления еще не предпринимались.</span><span class="sxs-lookup"><span data-stu-id="e44a0-p101">Time stamp from the latest attempt to refresh the principal. Can be null if no refresh has been attempted yet.</span></span>  <br/> |
|<span data-ttu-id="e44a0-128">nextTry</span><span class="sxs-lookup"><span data-stu-id="e44a0-128">nextTry</span></span>  <br/> |<span data-ttu-id="e44a0-129">datetime</span><span class="sxs-lookup"><span data-stu-id="e44a0-129">datetime</span></span>  <br/> |<span data-ttu-id="e44a0-p102">Метка времени для следующего запланированного обновления. Может иметь значение null, если дальнейшее обновление не запланировано.</span><span class="sxs-lookup"><span data-stu-id="e44a0-p102">Time stamp for the next scheduled refresh. Can be null if no further refresh has been scheduled.</span></span>  <br/> |
   
<span data-ttu-id="e44a0-132">**Keys**</span><span class="sxs-lookup"><span data-stu-id="e44a0-132">**Keys**</span></span>

|<span data-ttu-id="e44a0-133">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="e44a0-133">**Column**</span></span>|<span data-ttu-id="e44a0-134">**Описание**</span><span class="sxs-lookup"><span data-stu-id="e44a0-134">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e44a0-135">prinID</span><span class="sxs-lookup"><span data-stu-id="e44a0-135">prinID</span></span>  <br/> |<span data-ttu-id="e44a0-136">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="e44a0-136">Primary key.</span></span>  <br/> |
|<span data-ttu-id="e44a0-137">prinID</span><span class="sxs-lookup"><span data-stu-id="e44a0-137">prinID</span></span>  <br/> |<span data-ttu-id="e44a0-138">Внешний ключ с поиском в таблице tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="e44a0-138">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

