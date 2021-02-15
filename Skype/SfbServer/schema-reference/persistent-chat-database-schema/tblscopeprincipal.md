---
title: tblScopePrincipal
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
ms.assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
description: tblScopePrincipal содержит области, назначенные узлам.
ms.openlocfilehash: efda792ab6f6c6cc7b188a9dffdaa7c324b24797
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831519"
---
# <a name="tblscopeprincipal"></a><span data-ttu-id="faedc-103">tblScopePrincipal</span><span class="sxs-lookup"><span data-stu-id="faedc-103">tblScopePrincipal</span></span>
 
<span data-ttu-id="faedc-104">tblScopePrincipal содержит области, назначенные узлам.</span><span class="sxs-lookup"><span data-stu-id="faedc-104">tblScopePrincipal contains scopes assigned to nodes.</span></span>
  
<span data-ttu-id="faedc-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="faedc-105">**Columns**</span></span>

|<span data-ttu-id="faedc-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="faedc-106">**Column**</span></span>|<span data-ttu-id="faedc-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="faedc-107">**Type**</span></span>|<span data-ttu-id="faedc-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="faedc-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="faedc-109">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="faedc-109">scopeNodeID</span></span>  <br/> |<span data-ttu-id="faedc-110">int, не null</span><span class="sxs-lookup"><span data-stu-id="faedc-110">int, not null</span></span>  <br/> |<span data-ttu-id="faedc-111">Код узла, к которой применяется область.</span><span class="sxs-lookup"><span data-stu-id="faedc-111">Node ID that the scope applies to.</span></span>  <br/> |
|<span data-ttu-id="faedc-112">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="faedc-112">scopePrinID</span></span>  <br/> |<span data-ttu-id="faedc-113">int, не null</span><span class="sxs-lookup"><span data-stu-id="faedc-113">int, not null</span></span>  <br/> |<span data-ttu-id="faedc-114">Код участника</span><span class="sxs-lookup"><span data-stu-id="faedc-114">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="faedc-115">scopeIsDenied</span><span class="sxs-lookup"><span data-stu-id="faedc-115">scopeIsDenied</span></span>  <br/> |<span data-ttu-id="faedc-116">bit, не null</span><span class="sxs-lookup"><span data-stu-id="faedc-116">bit, not null</span></span>  <br/> |<span data-ttu-id="faedc-117">Значение true, если тип области — Deny; значение false, если тип области — Allow.</span><span class="sxs-lookup"><span data-stu-id="faedc-117">True if type of scope is Deny; False if Allow.</span></span>  <br/> |
|<span data-ttu-id="faedc-118">scopeUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="faedc-118">scopeUpdatedBy</span></span>  <br/> |<span data-ttu-id="faedc-119">int, не null</span><span class="sxs-lookup"><span data-stu-id="faedc-119">int, not null</span></span>  <br/> |<span data-ttu-id="faedc-120">Код участника, который последним обновил эту запись.</span><span class="sxs-lookup"><span data-stu-id="faedc-120">ID of the principal that last updated this entry.</span></span>  <br/> |
   
<span data-ttu-id="faedc-121">**Keys**</span><span class="sxs-lookup"><span data-stu-id="faedc-121">**Keys**</span></span>

|<span data-ttu-id="faedc-122">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="faedc-122">**Column**</span></span>|<span data-ttu-id="faedc-123">**Описание**</span><span class="sxs-lookup"><span data-stu-id="faedc-123">**Description**</span></span>|
|:-----|:-----|
|\<scopeNodeID, scopePrinID\>  <br/> |<span data-ttu-id="faedc-124">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="faedc-124">Primary key.</span></span>  <br/> |
|<span data-ttu-id="faedc-125">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="faedc-125">scopeNodeID</span></span>  <br/> |<span data-ttu-id="faedc-126">Внешний ключ с подстановкой в таблице tblNode.nodeID.</span><span class="sxs-lookup"><span data-stu-id="faedc-126">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
|<span data-ttu-id="faedc-127">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="faedc-127">scopePrinID</span></span>  <br/> |<span data-ttu-id="faedc-128">Внешний ключ с подстановкой в таблице tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="faedc-128">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

