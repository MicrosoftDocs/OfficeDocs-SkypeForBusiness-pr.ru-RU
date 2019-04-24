---
title: tblScopePrincipal
ms.reviewer: ''
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
ms.openlocfilehash: e93b92280605dfe01f288435c7cb42b724c22064
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212399"
---
# <a name="tblscopeprincipal"></a><span data-ttu-id="f9a7f-103">tblScopePrincipal</span><span class="sxs-lookup"><span data-stu-id="f9a7f-103">tblScopePrincipal</span></span>
 
<span data-ttu-id="f9a7f-104">tblScopePrincipal содержит области, назначенные узлам.</span><span class="sxs-lookup"><span data-stu-id="f9a7f-104">tblScopePrincipal contains scopes assigned to nodes.</span></span>
  
<span data-ttu-id="f9a7f-105">**Столбцы**</span><span class="sxs-lookup"><span data-stu-id="f9a7f-105">**Columns**</span></span>

|<span data-ttu-id="f9a7f-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="f9a7f-106">**Column**</span></span>|<span data-ttu-id="f9a7f-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="f9a7f-107">**Type**</span></span>|<span data-ttu-id="f9a7f-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="f9a7f-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f9a7f-109">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="f9a7f-109">scopeNodeID</span></span>  <br/> |<span data-ttu-id="f9a7f-110">int, не null</span><span class="sxs-lookup"><span data-stu-id="f9a7f-110">int, not null</span></span>  <br/> |<span data-ttu-id="f9a7f-111">Идентификатор узла, к которому применяется область.</span><span class="sxs-lookup"><span data-stu-id="f9a7f-111">Node ID that the scope applies to.</span></span>  <br/> |
|<span data-ttu-id="f9a7f-112">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="f9a7f-112">scopePrinID</span></span>  <br/> |<span data-ttu-id="f9a7f-113">int, не null</span><span class="sxs-lookup"><span data-stu-id="f9a7f-113">int, not null</span></span>  <br/> |<span data-ttu-id="f9a7f-114">Идентификатор субъекта.</span><span class="sxs-lookup"><span data-stu-id="f9a7f-114">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="f9a7f-115">scopeIsDenied</span><span class="sxs-lookup"><span data-stu-id="f9a7f-115">scopeIsDenied</span></span>  <br/> |<span data-ttu-id="f9a7f-116">bit, не может быть null</span><span class="sxs-lookup"><span data-stu-id="f9a7f-116">bit, not null</span></span>  <br/> |<span data-ttu-id="f9a7f-117">Значение true, если тип области — Deny; Значение false, если разрешение.</span><span class="sxs-lookup"><span data-stu-id="f9a7f-117">True if type of scope is Deny; False if Allow.</span></span>  <br/> |
|<span data-ttu-id="f9a7f-118">scopeUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="f9a7f-118">scopeUpdatedBy</span></span>  <br/> |<span data-ttu-id="f9a7f-119">int, не null</span><span class="sxs-lookup"><span data-stu-id="f9a7f-119">int, not null</span></span>  <br/> |<span data-ttu-id="f9a7f-120">Идентификатор субъекта, который последним обновил эту запись.</span><span class="sxs-lookup"><span data-stu-id="f9a7f-120">ID of the principal that last updated this entry.</span></span>  <br/> |
   
<span data-ttu-id="f9a7f-121">**Ключи**</span><span class="sxs-lookup"><span data-stu-id="f9a7f-121">**Keys**</span></span>

|<span data-ttu-id="f9a7f-122">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="f9a7f-122">**Column**</span></span>|<span data-ttu-id="f9a7f-123">**Описание**</span><span class="sxs-lookup"><span data-stu-id="f9a7f-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f9a7f-124">\<scopeNodeID scopePrinID\></span><span class="sxs-lookup"><span data-stu-id="f9a7f-124">\<scopeNodeID, scopePrinID\></span></span>  <br/> |<span data-ttu-id="f9a7f-125">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="f9a7f-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="f9a7f-126">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="f9a7f-126">scopeNodeID</span></span>  <br/> |<span data-ttu-id="f9a7f-127">Внешний ключ с подстановкой в таблице tblNode.nodeID.</span><span class="sxs-lookup"><span data-stu-id="f9a7f-127">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
|<span data-ttu-id="f9a7f-128">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="f9a7f-128">scopePrinID</span></span>  <br/> |<span data-ttu-id="f9a7f-129">Внешний ключ с подстановкой в таблице tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="f9a7f-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

