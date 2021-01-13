---
title: tblPrincipalRole
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
ms.assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
description: tblPrincipalRole содержит явные роли, назначенные узлам.
ms.openlocfilehash: 13c9c25db9ba1dbe281947468bbd834e80417899
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831559"
---
# <a name="tblprincipalrole"></a><span data-ttu-id="280c9-103">tblPrincipalRole</span><span class="sxs-lookup"><span data-stu-id="280c9-103">tblPrincipalRole</span></span>
 
<span data-ttu-id="280c9-104">tblPrincipalRole содержит явные роли, назначенные узлам.</span><span class="sxs-lookup"><span data-stu-id="280c9-104">tblPrincipalRole contains explicit roles assigned to nodes.</span></span>
  
<span data-ttu-id="280c9-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="280c9-105">**Columns**</span></span>

|<span data-ttu-id="280c9-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="280c9-106">**Column**</span></span>|<span data-ttu-id="280c9-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="280c9-107">**Type**</span></span>|<span data-ttu-id="280c9-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="280c9-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="280c9-109">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="280c9-109">prinRoleNodeID</span></span>  <br/> |<span data-ttu-id="280c9-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="280c9-110">int, not null</span></span>  <br/> |<span data-ttu-id="280c9-111">ИД узла, к которому применяется роль.</span><span class="sxs-lookup"><span data-stu-id="280c9-111">Node ID that the role applies to.</span></span>  <br/> |
|<span data-ttu-id="280c9-112">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="280c9-112">prinRolePrinID</span></span>  <br/> |<span data-ttu-id="280c9-113">int, not null</span><span class="sxs-lookup"><span data-stu-id="280c9-113">int, not null</span></span>  <br/> |<span data-ttu-id="280c9-114">ИД субъекта.</span><span class="sxs-lookup"><span data-stu-id="280c9-114">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="280c9-115">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="280c9-115">prinRoleTypeID</span></span>  <br/> |<span data-ttu-id="280c9-116">int, not null</span><span class="sxs-lookup"><span data-stu-id="280c9-116">int, not null</span></span>  <br/> |<span data-ttu-id="280c9-117">ИД типа роли (из tblRoleType).</span><span class="sxs-lookup"><span data-stu-id="280c9-117">Role type ID (from tblRoleType).</span></span>  <br/> |
|<span data-ttu-id="280c9-118">prinRoleUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="280c9-118">prinRoleUpdatedBy</span></span>  <br/> |<span data-ttu-id="280c9-119">int, not null</span><span class="sxs-lookup"><span data-stu-id="280c9-119">int, not null</span></span>  <br/> |<span data-ttu-id="280c9-120">Код участника, который последним обновил эту запись.</span><span class="sxs-lookup"><span data-stu-id="280c9-120">ID of the principal that last updated this entry.</span></span>  <br/> |
   
<span data-ttu-id="280c9-121">**Keys**</span><span class="sxs-lookup"><span data-stu-id="280c9-121">**Keys**</span></span>

|<span data-ttu-id="280c9-122">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="280c9-122">**Column**</span></span>|<span data-ttu-id="280c9-123">**Описание**</span><span class="sxs-lookup"><span data-stu-id="280c9-123">**Description**</span></span>|
|:-----|:-----|
|\<prinRoleNodeID, prinRolePrinID, prinRoleTypeID\>  <br/> |<span data-ttu-id="280c9-124">Основной ключ.</span><span class="sxs-lookup"><span data-stu-id="280c9-124">Primary key.</span></span>  <br/> |
|<span data-ttu-id="280c9-125">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="280c9-125">prinRoleNodeID</span></span>  <br/> |<span data-ttu-id="280c9-126">Внешний ключ с поиском в таблице tblNode.nodeID.</span><span class="sxs-lookup"><span data-stu-id="280c9-126">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
|<span data-ttu-id="280c9-127">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="280c9-127">prinRolePrinID</span></span>  <br/> |<span data-ttu-id="280c9-128">Внешний ключ с поиском в таблице tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="280c9-128">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="280c9-129">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="280c9-129">prinRoleTypeID</span></span>  <br/> |<span data-ttu-id="280c9-130">Внешний ключ с поиском в таблице tblRoleType.rtypeID.</span><span class="sxs-lookup"><span data-stu-id="280c9-130">Foreign key with lookup in tblRoleType.rtypeID table.</span></span>  <br/> |
   

