---
title: tblPrincipalInvites
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
ms.assetid: 548ec156-4d1a-469d-a804-62cff226e5c2
description: tblPrincipalInvites содержит приглашения для всех подготовленных пользователей для всех узлов с включенным автоматическим приглашением.
ms.openlocfilehash: 5bbccd582442001bd2122dcbacdbe3634fcfd649
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815859"
---
# <a name="tblprincipalinvites"></a><span data-ttu-id="ccec2-103">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="ccec2-103">tblPrincipalInvites</span></span>
 
<span data-ttu-id="ccec2-104">tblPrincipalInvites содержит приглашения для всех подготовленных пользователей для всех узлов с включенным автоматическим приглашением.</span><span class="sxs-lookup"><span data-stu-id="ccec2-104">tblPrincipalInvites contains invitations for all provisioned users for all nodes with auto-invite on.</span></span>
  
<span data-ttu-id="ccec2-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="ccec2-105">**Columns**</span></span>

|<span data-ttu-id="ccec2-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="ccec2-106">**Column**</span></span>|<span data-ttu-id="ccec2-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="ccec2-107">**Type**</span></span>|<span data-ttu-id="ccec2-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="ccec2-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ccec2-109">prinID</span><span class="sxs-lookup"><span data-stu-id="ccec2-109">prinID</span></span>  <br/> |<span data-ttu-id="ccec2-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="ccec2-110">int, not null</span></span>  <br/> |<span data-ttu-id="ccec2-111">Код участника</span><span class="sxs-lookup"><span data-stu-id="ccec2-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="ccec2-112">invID</span><span class="sxs-lookup"><span data-stu-id="ccec2-112">invID</span></span>  <br/> |<span data-ttu-id="ccec2-113">int, не null</span><span class="sxs-lookup"><span data-stu-id="ccec2-113">int, not null</span></span>  <br/> |<span data-ttu-id="ccec2-114">Уникальный порядковый номер (на код участника), созданный для таблицы tblLastInviteId.</span><span class="sxs-lookup"><span data-stu-id="ccec2-114">Unique sequential number (per principal ID) generated from tblLastInviteId table.</span></span>  <br/> |
|<span data-ttu-id="ccec2-115">nodeID</span><span class="sxs-lookup"><span data-stu-id="ccec2-115">nodeID</span></span>  <br/> |<span data-ttu-id="ccec2-116">int, не null</span><span class="sxs-lookup"><span data-stu-id="ccec2-116">int, not null</span></span>  <br/> |<span data-ttu-id="ccec2-117">Код узла (только комната чата).</span><span class="sxs-lookup"><span data-stu-id="ccec2-117">Node ID (chat room only).</span></span>  <br/> |
|<span data-ttu-id="ccec2-118">createdOn</span><span class="sxs-lookup"><span data-stu-id="ccec2-118">createdOn</span></span>  <br/> |<span data-ttu-id="ccec2-119">datetime, не null</span><span class="sxs-lookup"><span data-stu-id="ccec2-119">datetime, not null</span></span>  <br/> |<span data-ttu-id="ccec2-120">Время создания.</span><span class="sxs-lookup"><span data-stu-id="ccec2-120">Time of creation.</span></span>  <br/> |
   
<span data-ttu-id="ccec2-121">**Keys**</span><span class="sxs-lookup"><span data-stu-id="ccec2-121">**Keys**</span></span>

|<span data-ttu-id="ccec2-122">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="ccec2-122">**Column**</span></span>|<span data-ttu-id="ccec2-123">**Описание**</span><span class="sxs-lookup"><span data-stu-id="ccec2-123">**Description**</span></span>|
|:-----|:-----|
|\<prinID, nodeID\>  <br/> |<span data-ttu-id="ccec2-124">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="ccec2-124">Primary key.</span></span>  <br/> |
|<span data-ttu-id="ccec2-125">prinID</span><span class="sxs-lookup"><span data-stu-id="ccec2-125">prinID</span></span>  <br/> |<span data-ttu-id="ccec2-126">Внешний ключ с подстановкой в таблице tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="ccec2-126">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="ccec2-127">nodeID</span><span class="sxs-lookup"><span data-stu-id="ccec2-127">nodeID</span></span>  <br/> |<span data-ttu-id="ccec2-128">Внешний ключ с подстановкой в таблице tblNode.nodeID.</span><span class="sxs-lookup"><span data-stu-id="ccec2-128">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
   

