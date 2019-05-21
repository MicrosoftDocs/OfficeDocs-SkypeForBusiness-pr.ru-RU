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
localization_priority: Normal
ms.assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
description: ТблпринЦипалроле включает явные роли, назначенные узлам.
ms.openlocfilehash: 9675713afba5753378f4d01b70489d0eee93b8bf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295239"
---
# <a name="tblprincipalrole"></a><span data-ttu-id="5726c-103">tblPrincipalRole</span><span class="sxs-lookup"><span data-stu-id="5726c-103">tblPrincipalRole</span></span>
 
<span data-ttu-id="5726c-104">ТблпринЦипалроле включает явные роли, назначенные узлам.</span><span class="sxs-lookup"><span data-stu-id="5726c-104">tblPrincipalRole contains explicit roles assigned to nodes.</span></span>
  
<span data-ttu-id="5726c-105">**Столбцов**</span><span class="sxs-lookup"><span data-stu-id="5726c-105">**Columns**</span></span>

|<span data-ttu-id="5726c-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="5726c-106">**Column**</span></span>|<span data-ttu-id="5726c-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="5726c-107">**Type**</span></span>|<span data-ttu-id="5726c-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="5726c-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="5726c-109">Принроленодеид</span><span class="sxs-lookup"><span data-stu-id="5726c-109">prinRoleNodeID</span></span>  <br/> |<span data-ttu-id="5726c-110">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="5726c-110">int, not null</span></span>  <br/> |<span data-ttu-id="5726c-111">Идентификатор узла, к которому относится роль.</span><span class="sxs-lookup"><span data-stu-id="5726c-111">Node ID that the role applies to.</span></span>  <br/> |
|<span data-ttu-id="5726c-112">Принролепринид</span><span class="sxs-lookup"><span data-stu-id="5726c-112">prinRolePrinID</span></span>  <br/> |<span data-ttu-id="5726c-113">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="5726c-113">int, not null</span></span>  <br/> |<span data-ttu-id="5726c-114">Идентификатор участника.</span><span class="sxs-lookup"><span data-stu-id="5726c-114">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="5726c-115">Принролетипеид</span><span class="sxs-lookup"><span data-stu-id="5726c-115">prinRoleTypeID</span></span>  <br/> |<span data-ttu-id="5726c-116">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="5726c-116">int, not null</span></span>  <br/> |<span data-ttu-id="5726c-117">Идентификатор типа роли (из Тблролетипе).</span><span class="sxs-lookup"><span data-stu-id="5726c-117">Role type ID (from tblRoleType).</span></span>  <br/> |
|<span data-ttu-id="5726c-118">Принролеупдатедби</span><span class="sxs-lookup"><span data-stu-id="5726c-118">prinRoleUpdatedBy</span></span>  <br/> |<span data-ttu-id="5726c-119">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="5726c-119">int, not null</span></span>  <br/> |<span data-ttu-id="5726c-120">Идентификатор участника, который последним обновил эту запись.</span><span class="sxs-lookup"><span data-stu-id="5726c-120">ID of the principal that last updated this entry.</span></span>  <br/> |
   
<span data-ttu-id="5726c-121">**Параметры**</span><span class="sxs-lookup"><span data-stu-id="5726c-121">**Keys**</span></span>

|<span data-ttu-id="5726c-122">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="5726c-122">**Column**</span></span>|<span data-ttu-id="5726c-123">**Описание**</span><span class="sxs-lookup"><span data-stu-id="5726c-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="5726c-124">\<Принроленодеид, Принролепринид, Принролетипеид\></span><span class="sxs-lookup"><span data-stu-id="5726c-124">\<prinRoleNodeID, prinRolePrinID, prinRoleTypeID\></span></span>  <br/> |<span data-ttu-id="5726c-125">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="5726c-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="5726c-126">Принроленодеид</span><span class="sxs-lookup"><span data-stu-id="5726c-126">prinRoleNodeID</span></span>  <br/> |<span data-ttu-id="5726c-127">Внешний ключ с подстановкой в таблице Тблноде. Нодеид.</span><span class="sxs-lookup"><span data-stu-id="5726c-127">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
|<span data-ttu-id="5726c-128">Принролепринид</span><span class="sxs-lookup"><span data-stu-id="5726c-128">prinRolePrinID</span></span>  <br/> |<span data-ttu-id="5726c-129">Внешний ключ с подстановкой в таблице ТблпринЦипал. Принид.</span><span class="sxs-lookup"><span data-stu-id="5726c-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="5726c-130">Принролетипеид</span><span class="sxs-lookup"><span data-stu-id="5726c-130">prinRoleTypeID</span></span>  <br/> |<span data-ttu-id="5726c-131">Внешний ключ с подстановкой в таблице Тблролетипе. Ртипеид.</span><span class="sxs-lookup"><span data-stu-id="5726c-131">Foreign key with lookup in tblRoleType.rtypeID table.</span></span>  <br/> |
   

