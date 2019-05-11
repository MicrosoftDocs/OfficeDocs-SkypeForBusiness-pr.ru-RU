---
title: tblPrincipalRole
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
description: tblPrincipalRole содержит явные роли, назначенные узлам.
ms.openlocfilehash: 7c144f2f531af58c7c5693b28b224a2ee4456783
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33904183"
---
# <a name="tblprincipalrole"></a><span data-ttu-id="0aead-103">tblPrincipalRole</span><span class="sxs-lookup"><span data-stu-id="0aead-103">tblPrincipalRole</span></span>
 
<span data-ttu-id="0aead-104">tblPrincipalRole содержит явные роли, назначенные узлам.</span><span class="sxs-lookup"><span data-stu-id="0aead-104">tblPrincipalRole contains explicit roles assigned to nodes.</span></span>
  
<span data-ttu-id="0aead-105">**Столбцы**</span><span class="sxs-lookup"><span data-stu-id="0aead-105">**Columns**</span></span>

|<span data-ttu-id="0aead-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="0aead-106">**Column**</span></span>|<span data-ttu-id="0aead-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="0aead-107">**Type**</span></span>|<span data-ttu-id="0aead-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="0aead-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0aead-109">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="0aead-109">prinRoleNodeID</span></span>  <br/> |<span data-ttu-id="0aead-110">int, не null</span><span class="sxs-lookup"><span data-stu-id="0aead-110">int, not null</span></span>  <br/> |<span data-ttu-id="0aead-111">Идентификатор узла, к которому применяется роль.</span><span class="sxs-lookup"><span data-stu-id="0aead-111">Node ID that the role applies to.</span></span>  <br/> |
|<span data-ttu-id="0aead-112">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="0aead-112">prinRolePrinID</span></span>  <br/> |<span data-ttu-id="0aead-113">int, не null</span><span class="sxs-lookup"><span data-stu-id="0aead-113">int, not null</span></span>  <br/> |<span data-ttu-id="0aead-114">Идентификатор субъекта.</span><span class="sxs-lookup"><span data-stu-id="0aead-114">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="0aead-115">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="0aead-115">prinRoleTypeID</span></span>  <br/> |<span data-ttu-id="0aead-116">int, не null</span><span class="sxs-lookup"><span data-stu-id="0aead-116">int, not null</span></span>  <br/> |<span data-ttu-id="0aead-117">ИД типа роли (из tblRoleType).</span><span class="sxs-lookup"><span data-stu-id="0aead-117">Role type ID (from tblRoleType).</span></span>  <br/> |
|<span data-ttu-id="0aead-118">prinRoleUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="0aead-118">prinRoleUpdatedBy</span></span>  <br/> |<span data-ttu-id="0aead-119">int, не null</span><span class="sxs-lookup"><span data-stu-id="0aead-119">int, not null</span></span>  <br/> |<span data-ttu-id="0aead-120">Идентификатор субъекта, который последним обновил эту запись.</span><span class="sxs-lookup"><span data-stu-id="0aead-120">ID of the principal that last updated this entry.</span></span>  <br/> |
   
<span data-ttu-id="0aead-121">**Ключи**</span><span class="sxs-lookup"><span data-stu-id="0aead-121">**Keys**</span></span>

|<span data-ttu-id="0aead-122">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="0aead-122">**Column**</span></span>|<span data-ttu-id="0aead-123">**Описание**</span><span class="sxs-lookup"><span data-stu-id="0aead-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="0aead-124">\<prinRoleNodeID, prinRolePrinID, prinRoleTypeID\></span><span class="sxs-lookup"><span data-stu-id="0aead-124">\<prinRoleNodeID, prinRolePrinID, prinRoleTypeID\></span></span>  <br/> |<span data-ttu-id="0aead-125">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="0aead-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="0aead-126">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="0aead-126">prinRoleNodeID</span></span>  <br/> |<span data-ttu-id="0aead-127">Внешний ключ с подстановкой в таблице tblNode.nodeID.</span><span class="sxs-lookup"><span data-stu-id="0aead-127">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
|<span data-ttu-id="0aead-128">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="0aead-128">prinRolePrinID</span></span>  <br/> |<span data-ttu-id="0aead-129">Внешний ключ с подстановкой в таблице tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="0aead-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="0aead-130">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="0aead-130">prinRoleTypeID</span></span>  <br/> |<span data-ttu-id="0aead-131">Внешний ключ с поиском в таблице tblRoleType.rtypeID.</span><span class="sxs-lookup"><span data-stu-id="0aead-131">Foreign key with lookup in tblRoleType.rtypeID table.</span></span>  <br/> |
   

