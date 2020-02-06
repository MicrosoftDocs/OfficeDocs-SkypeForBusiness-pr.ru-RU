---
title: tblPrincipalRole
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
description: ТблпринЦипалроле включает явные роли, назначенные узлам.
ms.openlocfilehash: 1cc606ec3825bb664d4123154e97fabb15678cfd
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813367"
---
# <a name="tblprincipalrole"></a><span data-ttu-id="6436f-103">tblPrincipalRole</span><span class="sxs-lookup"><span data-stu-id="6436f-103">tblPrincipalRole</span></span>
 
<span data-ttu-id="6436f-104">ТблпринЦипалроле включает явные роли, назначенные узлам.</span><span class="sxs-lookup"><span data-stu-id="6436f-104">tblPrincipalRole contains explicit roles assigned to nodes.</span></span>
  
<span data-ttu-id="6436f-105">**Столбцов**</span><span class="sxs-lookup"><span data-stu-id="6436f-105">**Columns**</span></span>

|<span data-ttu-id="6436f-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="6436f-106">**Column**</span></span>|<span data-ttu-id="6436f-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="6436f-107">**Type**</span></span>|<span data-ttu-id="6436f-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="6436f-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6436f-109">принроленодеид</span><span class="sxs-lookup"><span data-stu-id="6436f-109">prinRoleNodeID</span></span>  <br/> |<span data-ttu-id="6436f-110">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="6436f-110">int, not null</span></span>  <br/> |<span data-ttu-id="6436f-111">Идентификатор узла, к которому относится роль.</span><span class="sxs-lookup"><span data-stu-id="6436f-111">Node ID that the role applies to.</span></span>  <br/> |
|<span data-ttu-id="6436f-112">принролепринид</span><span class="sxs-lookup"><span data-stu-id="6436f-112">prinRolePrinID</span></span>  <br/> |<span data-ttu-id="6436f-113">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="6436f-113">int, not null</span></span>  <br/> |<span data-ttu-id="6436f-114">Идентификатор участника.</span><span class="sxs-lookup"><span data-stu-id="6436f-114">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="6436f-115">принролетипеид</span><span class="sxs-lookup"><span data-stu-id="6436f-115">prinRoleTypeID</span></span>  <br/> |<span data-ttu-id="6436f-116">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="6436f-116">int, not null</span></span>  <br/> |<span data-ttu-id="6436f-117">Идентификатор типа роли (из Тблролетипе).</span><span class="sxs-lookup"><span data-stu-id="6436f-117">Role type ID (from tblRoleType).</span></span>  <br/> |
|<span data-ttu-id="6436f-118">принролеупдатедби</span><span class="sxs-lookup"><span data-stu-id="6436f-118">prinRoleUpdatedBy</span></span>  <br/> |<span data-ttu-id="6436f-119">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="6436f-119">int, not null</span></span>  <br/> |<span data-ttu-id="6436f-120">Идентификатор участника, который последним обновил эту запись.</span><span class="sxs-lookup"><span data-stu-id="6436f-120">ID of the principal that last updated this entry.</span></span>  <br/> |
   
<span data-ttu-id="6436f-121">**Параметры**</span><span class="sxs-lookup"><span data-stu-id="6436f-121">**Keys**</span></span>

|<span data-ttu-id="6436f-122">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="6436f-122">**Column**</span></span>|<span data-ttu-id="6436f-123">**Описание**</span><span class="sxs-lookup"><span data-stu-id="6436f-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="6436f-124">\<Принроленодеид, Принролепринид, Принролетипеид\></span><span class="sxs-lookup"><span data-stu-id="6436f-124">\<prinRoleNodeID, prinRolePrinID, prinRoleTypeID\></span></span>  <br/> |<span data-ttu-id="6436f-125">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="6436f-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="6436f-126">принроленодеид</span><span class="sxs-lookup"><span data-stu-id="6436f-126">prinRoleNodeID</span></span>  <br/> |<span data-ttu-id="6436f-127">Внешний ключ с подстановкой в таблице Тблноде. Нодеид.</span><span class="sxs-lookup"><span data-stu-id="6436f-127">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
|<span data-ttu-id="6436f-128">принролепринид</span><span class="sxs-lookup"><span data-stu-id="6436f-128">prinRolePrinID</span></span>  <br/> |<span data-ttu-id="6436f-129">Внешний ключ с подстановкой в таблице ТблпринЦипал. Принид.</span><span class="sxs-lookup"><span data-stu-id="6436f-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="6436f-130">принролетипеид</span><span class="sxs-lookup"><span data-stu-id="6436f-130">prinRoleTypeID</span></span>  <br/> |<span data-ttu-id="6436f-131">Внешний ключ с подстановкой в таблице Тблролетипе. Ртипеид.</span><span class="sxs-lookup"><span data-stu-id="6436f-131">Foreign key with lookup in tblRoleType.rtypeID table.</span></span>  <br/> |
   

