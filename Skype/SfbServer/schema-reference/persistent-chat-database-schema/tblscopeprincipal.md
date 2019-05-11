---
title: tblScopePrincipal
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
description: tblScopePrincipal содержит области, назначенные узлам.
ms.openlocfilehash: f682c8a2235ef30cda365bc5950cbfb123840595
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924929"
---
# <a name="tblscopeprincipal"></a><span data-ttu-id="07861-103">tblScopePrincipal</span><span class="sxs-lookup"><span data-stu-id="07861-103">tblScopePrincipal</span></span>
 
<span data-ttu-id="07861-104">tblScopePrincipal содержит области, назначенные узлам.</span><span class="sxs-lookup"><span data-stu-id="07861-104">tblScopePrincipal contains scopes assigned to nodes.</span></span>
  
<span data-ttu-id="07861-105">**Столбцы**</span><span class="sxs-lookup"><span data-stu-id="07861-105">**Columns**</span></span>

|<span data-ttu-id="07861-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="07861-106">**Column**</span></span>|<span data-ttu-id="07861-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="07861-107">**Type**</span></span>|<span data-ttu-id="07861-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="07861-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="07861-109">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="07861-109">scopeNodeID</span></span>  <br/> |<span data-ttu-id="07861-110">int, не null</span><span class="sxs-lookup"><span data-stu-id="07861-110">int, not null</span></span>  <br/> |<span data-ttu-id="07861-111">Идентификатор узла, к которому применяется область.</span><span class="sxs-lookup"><span data-stu-id="07861-111">Node ID that the scope applies to.</span></span>  <br/> |
|<span data-ttu-id="07861-112">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="07861-112">scopePrinID</span></span>  <br/> |<span data-ttu-id="07861-113">int, не null</span><span class="sxs-lookup"><span data-stu-id="07861-113">int, not null</span></span>  <br/> |<span data-ttu-id="07861-114">Идентификатор субъекта.</span><span class="sxs-lookup"><span data-stu-id="07861-114">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="07861-115">scopeIsDenied</span><span class="sxs-lookup"><span data-stu-id="07861-115">scopeIsDenied</span></span>  <br/> |<span data-ttu-id="07861-116">bit, не может быть null</span><span class="sxs-lookup"><span data-stu-id="07861-116">bit, not null</span></span>  <br/> |<span data-ttu-id="07861-117">Значение true, если тип области — Deny; Значение false, если разрешение.</span><span class="sxs-lookup"><span data-stu-id="07861-117">True if type of scope is Deny; False if Allow.</span></span>  <br/> |
|<span data-ttu-id="07861-118">scopeUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="07861-118">scopeUpdatedBy</span></span>  <br/> |<span data-ttu-id="07861-119">int, не null</span><span class="sxs-lookup"><span data-stu-id="07861-119">int, not null</span></span>  <br/> |<span data-ttu-id="07861-120">Идентификатор субъекта, который последним обновил эту запись.</span><span class="sxs-lookup"><span data-stu-id="07861-120">ID of the principal that last updated this entry.</span></span>  <br/> |
   
<span data-ttu-id="07861-121">**Ключи**</span><span class="sxs-lookup"><span data-stu-id="07861-121">**Keys**</span></span>

|<span data-ttu-id="07861-122">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="07861-122">**Column**</span></span>|<span data-ttu-id="07861-123">**Описание**</span><span class="sxs-lookup"><span data-stu-id="07861-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="07861-124">\<scopeNodeID scopePrinID\></span><span class="sxs-lookup"><span data-stu-id="07861-124">\<scopeNodeID, scopePrinID\></span></span>  <br/> |<span data-ttu-id="07861-125">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="07861-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="07861-126">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="07861-126">scopeNodeID</span></span>  <br/> |<span data-ttu-id="07861-127">Внешний ключ с подстановкой в таблице tblNode.nodeID.</span><span class="sxs-lookup"><span data-stu-id="07861-127">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
|<span data-ttu-id="07861-128">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="07861-128">scopePrinID</span></span>  <br/> |<span data-ttu-id="07861-129">Внешний ключ с подстановкой в таблице tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="07861-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

