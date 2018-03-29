---
title: tblPrincipalRole
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
description: tblPrincipalRole содержит явные роли, назначенные узлам.
ms.openlocfilehash: 0e6c7f60f372bc14542567ccaa1b1b1a837c6c6d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="tblprincipalrole"></a><span data-ttu-id="f6c08-103">tblPrincipalRole</span><span class="sxs-lookup"><span data-stu-id="f6c08-103">tblPrincipalRole</span></span>
 
<span data-ttu-id="f6c08-104">tblPrincipalRole содержит явные роли, назначенные узлам.</span><span class="sxs-lookup"><span data-stu-id="f6c08-104">tblPrincipalRole contains explicit roles assigned to nodes.</span></span>
  
<span data-ttu-id="f6c08-105">**Столбцы**</span><span class="sxs-lookup"><span data-stu-id="f6c08-105">**Columns**</span></span>

|<span data-ttu-id="f6c08-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="f6c08-106">**Column**</span></span>|<span data-ttu-id="f6c08-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="f6c08-107">**Type**</span></span>|<span data-ttu-id="f6c08-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="f6c08-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f6c08-109">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="f6c08-109">prinRoleNodeID</span></span>  <br/> |<span data-ttu-id="f6c08-110">int, не null</span><span class="sxs-lookup"><span data-stu-id="f6c08-110">int, not null</span></span>  <br/> |<span data-ttu-id="f6c08-111">Идентификатор узла, к которому применяется роль.</span><span class="sxs-lookup"><span data-stu-id="f6c08-111">Node ID that the role applies to.</span></span>  <br/> |
|<span data-ttu-id="f6c08-112">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="f6c08-112">prinRolePrinID</span></span>  <br/> |<span data-ttu-id="f6c08-113">int, не null</span><span class="sxs-lookup"><span data-stu-id="f6c08-113">int, not null</span></span>  <br/> |<span data-ttu-id="f6c08-114">Идентификатор субъекта.</span><span class="sxs-lookup"><span data-stu-id="f6c08-114">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="f6c08-115">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="f6c08-115">prinRoleTypeID</span></span>  <br/> |<span data-ttu-id="f6c08-116">int, не null</span><span class="sxs-lookup"><span data-stu-id="f6c08-116">int, not null</span></span>  <br/> |<span data-ttu-id="f6c08-117">ИД типа роли (из tblRoleType).</span><span class="sxs-lookup"><span data-stu-id="f6c08-117">Role type ID (from tblRoleType).</span></span>  <br/> |
|<span data-ttu-id="f6c08-118">prinRoleUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="f6c08-118">prinRoleUpdatedBy</span></span>  <br/> |<span data-ttu-id="f6c08-119">int, не null</span><span class="sxs-lookup"><span data-stu-id="f6c08-119">int, not null</span></span>  <br/> |<span data-ttu-id="f6c08-120">Идентификатор субъекта, который последним обновил эту запись.</span><span class="sxs-lookup"><span data-stu-id="f6c08-120">ID of the principal that last updated this entry.</span></span>  <br/> |
   
<span data-ttu-id="f6c08-121">**Ключи**</span><span class="sxs-lookup"><span data-stu-id="f6c08-121">**Keys**</span></span>

|<span data-ttu-id="f6c08-122">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="f6c08-122">**Column**</span></span>|<span data-ttu-id="f6c08-123">**Описание**</span><span class="sxs-lookup"><span data-stu-id="f6c08-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f6c08-124">\<prinRoleNodeID, prinRolePrinID, prinRoleTypeID\></span><span class="sxs-lookup"><span data-stu-id="f6c08-124">\<prinRoleNodeID, prinRolePrinID, prinRoleTypeID\></span></span>  <br/> |<span data-ttu-id="f6c08-125">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="f6c08-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="f6c08-126">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="f6c08-126">prinRoleNodeID</span></span>  <br/> |<span data-ttu-id="f6c08-127">Внешний ключ с подстановкой в таблице tblNode.nodeID.</span><span class="sxs-lookup"><span data-stu-id="f6c08-127">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
|<span data-ttu-id="f6c08-128">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="f6c08-128">prinRolePrinID</span></span>  <br/> |<span data-ttu-id="f6c08-129">Внешний ключ с подстановкой в таблице tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="f6c08-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="f6c08-130">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="f6c08-130">prinRoleTypeID</span></span>  <br/> |<span data-ttu-id="f6c08-131">Внешний ключ с поиском в таблице tblRoleType.rtypeID.</span><span class="sxs-lookup"><span data-stu-id="f6c08-131">Foreign key with lookup in tblRoleType.rtypeID table.</span></span>  <br/> |
   

