---
title: tblPrincipalRole
ms.reviewer: ''
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
ms.openlocfilehash: 69cfb0cb2b821064801a07510758514bb5d33128
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30890771"
---
# <a name="tblprincipalrole"></a><span data-ttu-id="a499b-103">tblPrincipalRole</span><span class="sxs-lookup"><span data-stu-id="a499b-103">tblPrincipalRole</span></span>
 
<span data-ttu-id="a499b-104">tblPrincipalRole содержит явные роли, назначенные узлам.</span><span class="sxs-lookup"><span data-stu-id="a499b-104">tblPrincipalRole contains explicit roles assigned to nodes.</span></span>
  
<span data-ttu-id="a499b-105">**Столбцы**</span><span class="sxs-lookup"><span data-stu-id="a499b-105">**Columns**</span></span>

|<span data-ttu-id="a499b-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="a499b-106">**Column**</span></span>|<span data-ttu-id="a499b-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="a499b-107">**Type**</span></span>|<span data-ttu-id="a499b-108">**Описание**.</span><span class="sxs-lookup"><span data-stu-id="a499b-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a499b-109">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="a499b-109">prinRoleNodeID</span></span>  <br/> |<span data-ttu-id="a499b-110">int, не null</span><span class="sxs-lookup"><span data-stu-id="a499b-110">int, not null</span></span>  <br/> |<span data-ttu-id="a499b-111">Идентификатор узла, к которому применяется роль.</span><span class="sxs-lookup"><span data-stu-id="a499b-111">Node ID that the role applies to.</span></span>  <br/> |
|<span data-ttu-id="a499b-112">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="a499b-112">prinRolePrinID</span></span>  <br/> |<span data-ttu-id="a499b-113">int, не null</span><span class="sxs-lookup"><span data-stu-id="a499b-113">int, not null</span></span>  <br/> |<span data-ttu-id="a499b-114">Идентификатор субъекта.</span><span class="sxs-lookup"><span data-stu-id="a499b-114">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="a499b-115">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="a499b-115">prinRoleTypeID</span></span>  <br/> |<span data-ttu-id="a499b-116">int, не null</span><span class="sxs-lookup"><span data-stu-id="a499b-116">int, not null</span></span>  <br/> |<span data-ttu-id="a499b-117">ИД типа роли (из tblRoleType).</span><span class="sxs-lookup"><span data-stu-id="a499b-117">Role type ID (from tblRoleType).</span></span>  <br/> |
|<span data-ttu-id="a499b-118">prinRoleUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="a499b-118">prinRoleUpdatedBy</span></span>  <br/> |<span data-ttu-id="a499b-119">int, не null</span><span class="sxs-lookup"><span data-stu-id="a499b-119">int, not null</span></span>  <br/> |<span data-ttu-id="a499b-120">Идентификатор субъекта, который последним обновил эту запись.</span><span class="sxs-lookup"><span data-stu-id="a499b-120">ID of the principal that last updated this entry.</span></span>  <br/> |
   
<span data-ttu-id="a499b-121">**Ключи**</span><span class="sxs-lookup"><span data-stu-id="a499b-121">**Keys**</span></span>

|<span data-ttu-id="a499b-122">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="a499b-122">**Column**</span></span>|<span data-ttu-id="a499b-123">**Описание**.</span><span class="sxs-lookup"><span data-stu-id="a499b-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a499b-124">\<prinRoleNodeID, prinRolePrinID, prinRoleTypeID\></span><span class="sxs-lookup"><span data-stu-id="a499b-124">\<prinRoleNodeID, prinRolePrinID, prinRoleTypeID\></span></span>  <br/> |<span data-ttu-id="a499b-125">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="a499b-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="a499b-126">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="a499b-126">prinRoleNodeID</span></span>  <br/> |<span data-ttu-id="a499b-127">Внешний ключ с подстановкой в таблице tblNode.nodeID.</span><span class="sxs-lookup"><span data-stu-id="a499b-127">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
|<span data-ttu-id="a499b-128">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="a499b-128">prinRolePrinID</span></span>  <br/> |<span data-ttu-id="a499b-129">Внешний ключ с подстановкой в таблице tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="a499b-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="a499b-130">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="a499b-130">prinRoleTypeID</span></span>  <br/> |<span data-ttu-id="a499b-131">Внешний ключ с поиском в таблице tblRoleType.rtypeID.</span><span class="sxs-lookup"><span data-stu-id="a499b-131">Foreign key with lookup in tblRoleType.rtypeID table.</span></span>  <br/> |
   

