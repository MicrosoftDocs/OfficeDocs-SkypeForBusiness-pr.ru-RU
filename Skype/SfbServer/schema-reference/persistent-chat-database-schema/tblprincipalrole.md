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
# <a name="tblprincipalrole"></a><span data-ttu-id="f1f2b-103">tblPrincipalRole</span><span class="sxs-lookup"><span data-stu-id="f1f2b-103">tblPrincipalRole</span></span>
 
<span data-ttu-id="f1f2b-104">tblPrincipalRole содержит явные роли, назначенные узлам.</span><span class="sxs-lookup"><span data-stu-id="f1f2b-104">tblPrincipalRole contains explicit roles assigned to nodes.</span></span>
  
<span data-ttu-id="f1f2b-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="f1f2b-105">**Columns**</span></span>

|<span data-ttu-id="f1f2b-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="f1f2b-106">**Column**</span></span>|<span data-ttu-id="f1f2b-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="f1f2b-107">**Type**</span></span>|<span data-ttu-id="f1f2b-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="f1f2b-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f1f2b-109">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="f1f2b-109">prinRoleNodeID</span></span>  <br/> |<span data-ttu-id="f1f2b-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="f1f2b-110">int, not null</span></span>  <br/> |<span data-ttu-id="f1f2b-111">ИД узла, к которому применяется роль.</span><span class="sxs-lookup"><span data-stu-id="f1f2b-111">Node ID that the role applies to.</span></span>  <br/> |
|<span data-ttu-id="f1f2b-112">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="f1f2b-112">prinRolePrinID</span></span>  <br/> |<span data-ttu-id="f1f2b-113">int, not null</span><span class="sxs-lookup"><span data-stu-id="f1f2b-113">int, not null</span></span>  <br/> |<span data-ttu-id="f1f2b-114">ИД субъекта.</span><span class="sxs-lookup"><span data-stu-id="f1f2b-114">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="f1f2b-115">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="f1f2b-115">prinRoleTypeID</span></span>  <br/> |<span data-ttu-id="f1f2b-116">int, not null</span><span class="sxs-lookup"><span data-stu-id="f1f2b-116">int, not null</span></span>  <br/> |<span data-ttu-id="f1f2b-117">ИД типа роли (из tblRoleType).</span><span class="sxs-lookup"><span data-stu-id="f1f2b-117">Role type ID (from tblRoleType).</span></span>  <br/> |
|<span data-ttu-id="f1f2b-118">prinRoleUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="f1f2b-118">prinRoleUpdatedBy</span></span>  <br/> |<span data-ttu-id="f1f2b-119">int, not null</span><span class="sxs-lookup"><span data-stu-id="f1f2b-119">int, not null</span></span>  <br/> |<span data-ttu-id="f1f2b-120">Код участника, который последним обновил эту запись.</span><span class="sxs-lookup"><span data-stu-id="f1f2b-120">ID of the principal that last updated this entry.</span></span>  <br/> |
   
<span data-ttu-id="f1f2b-121">**Keys**</span><span class="sxs-lookup"><span data-stu-id="f1f2b-121">**Keys**</span></span>

|<span data-ttu-id="f1f2b-122">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="f1f2b-122">**Column**</span></span>|<span data-ttu-id="f1f2b-123">**Описание**</span><span class="sxs-lookup"><span data-stu-id="f1f2b-123">**Description**</span></span>|
|:-----|:-----|
|\<prinRoleNodeID, prinRolePrinID, prinRoleTypeID\>  <br/> |<span data-ttu-id="f1f2b-124">Основной ключ.</span><span class="sxs-lookup"><span data-stu-id="f1f2b-124">Primary key.</span></span>  <br/> |
|<span data-ttu-id="f1f2b-125">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="f1f2b-125">prinRoleNodeID</span></span>  <br/> |<span data-ttu-id="f1f2b-126">Внешний ключ с поиском в таблице tblNode.nodeID.</span><span class="sxs-lookup"><span data-stu-id="f1f2b-126">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
|<span data-ttu-id="f1f2b-127">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="f1f2b-127">prinRolePrinID</span></span>  <br/> |<span data-ttu-id="f1f2b-128">Внешний ключ с поиском в таблице tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="f1f2b-128">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="f1f2b-129">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="f1f2b-129">prinRoleTypeID</span></span>  <br/> |<span data-ttu-id="f1f2b-130">Внешний ключ с поиском в таблице tblRoleType.rtypeID.</span><span class="sxs-lookup"><span data-stu-id="f1f2b-130">Foreign key with lookup in tblRoleType.rtypeID table.</span></span>  <br/> |
   

