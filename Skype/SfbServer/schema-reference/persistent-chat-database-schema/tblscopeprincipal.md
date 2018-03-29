---
title: tblScopePrincipal
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
description: tblScopePrincipal содержит области, назначенные узлам.
ms.openlocfilehash: ba2927598cdff07368cb017866ec41bfa7540f48
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="tblscopeprincipal"></a><span data-ttu-id="6f095-103">tblScopePrincipal</span><span class="sxs-lookup"><span data-stu-id="6f095-103">tblScopePrincipal</span></span>
 
<span data-ttu-id="6f095-104">tblScopePrincipal содержит области, назначенные узлам.</span><span class="sxs-lookup"><span data-stu-id="6f095-104">tblScopePrincipal contains scopes assigned to nodes.</span></span>
  
<span data-ttu-id="6f095-105">**Столбцы**</span><span class="sxs-lookup"><span data-stu-id="6f095-105">**Columns**</span></span>

|<span data-ttu-id="6f095-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="6f095-106">**Column**</span></span>|<span data-ttu-id="6f095-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="6f095-107">**Type**</span></span>|<span data-ttu-id="6f095-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="6f095-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6f095-109">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="6f095-109">scopeNodeID</span></span>  <br/> |<span data-ttu-id="6f095-110">int, не null</span><span class="sxs-lookup"><span data-stu-id="6f095-110">int, not null</span></span>  <br/> |<span data-ttu-id="6f095-111">Идентификатор узла, к которому применяется область.</span><span class="sxs-lookup"><span data-stu-id="6f095-111">Node ID that the scope applies to.</span></span>  <br/> |
|<span data-ttu-id="6f095-112">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="6f095-112">scopePrinID</span></span>  <br/> |<span data-ttu-id="6f095-113">int, не null</span><span class="sxs-lookup"><span data-stu-id="6f095-113">int, not null</span></span>  <br/> |<span data-ttu-id="6f095-114">Идентификатор субъекта.</span><span class="sxs-lookup"><span data-stu-id="6f095-114">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="6f095-115">scopeIsDenied</span><span class="sxs-lookup"><span data-stu-id="6f095-115">scopeIsDenied</span></span>  <br/> |<span data-ttu-id="6f095-116">bit, не может быть null</span><span class="sxs-lookup"><span data-stu-id="6f095-116">bit, not null</span></span>  <br/> |<span data-ttu-id="6f095-117">Значение true, если тип области — Deny; Значение false, если разрешение.</span><span class="sxs-lookup"><span data-stu-id="6f095-117">True if type of scope is Deny; False if Allow.</span></span>  <br/> |
|<span data-ttu-id="6f095-118">scopeUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="6f095-118">scopeUpdatedBy</span></span>  <br/> |<span data-ttu-id="6f095-119">int, не null</span><span class="sxs-lookup"><span data-stu-id="6f095-119">int, not null</span></span>  <br/> |<span data-ttu-id="6f095-120">Идентификатор субъекта, который последним обновил эту запись.</span><span class="sxs-lookup"><span data-stu-id="6f095-120">ID of the principal that last updated this entry.</span></span>  <br/> |
   
<span data-ttu-id="6f095-121">**Ключи**</span><span class="sxs-lookup"><span data-stu-id="6f095-121">**Keys**</span></span>

|<span data-ttu-id="6f095-122">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="6f095-122">**Column**</span></span>|<span data-ttu-id="6f095-123">**Описание**</span><span class="sxs-lookup"><span data-stu-id="6f095-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="6f095-124">\<scopeNodeID scopePrinID\></span><span class="sxs-lookup"><span data-stu-id="6f095-124">\<scopeNodeID, scopePrinID\></span></span>  <br/> |<span data-ttu-id="6f095-125">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="6f095-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="6f095-126">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="6f095-126">scopeNodeID</span></span>  <br/> |<span data-ttu-id="6f095-127">Внешний ключ с подстановкой в таблице tblNode.nodeID.</span><span class="sxs-lookup"><span data-stu-id="6f095-127">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
|<span data-ttu-id="6f095-128">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="6f095-128">scopePrinID</span></span>  <br/> |<span data-ttu-id="6f095-129">Внешний ключ с подстановкой в таблице tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="6f095-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

