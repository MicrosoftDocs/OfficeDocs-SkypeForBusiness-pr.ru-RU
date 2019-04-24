---
title: tblPrincipalInvites
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 548ec156-4d1a-469d-a804-62cff226e5c2
description: tblPrincipalInvites содержит приглашения для всех подготовленных пользователей для всех узлов с автоматическим приглашением на.
ms.openlocfilehash: fbf61265f4970b57ffa95a52c8bafa395fb3a331
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212469"
---
# <a name="tblprincipalinvites"></a><span data-ttu-id="e1b68-103">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="e1b68-103">tblPrincipalInvites</span></span>
 
<span data-ttu-id="e1b68-104">tblPrincipalInvites содержит приглашения для всех подготовленных пользователей для всех узлов с автоматическим приглашением на.</span><span class="sxs-lookup"><span data-stu-id="e1b68-104">tblPrincipalInvites contains invitations for all provisioned users for all nodes with auto-invite on.</span></span>
  
<span data-ttu-id="e1b68-105">**Столбцы**</span><span class="sxs-lookup"><span data-stu-id="e1b68-105">**Columns**</span></span>

|<span data-ttu-id="e1b68-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="e1b68-106">**Column**</span></span>|<span data-ttu-id="e1b68-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="e1b68-107">**Type**</span></span>|<span data-ttu-id="e1b68-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="e1b68-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e1b68-109">prinID</span><span class="sxs-lookup"><span data-stu-id="e1b68-109">prinID</span></span>  <br/> |<span data-ttu-id="e1b68-110">int, не null</span><span class="sxs-lookup"><span data-stu-id="e1b68-110">int, not null</span></span>  <br/> |<span data-ttu-id="e1b68-111">Идентификатор субъекта.</span><span class="sxs-lookup"><span data-stu-id="e1b68-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="e1b68-112">invID</span><span class="sxs-lookup"><span data-stu-id="e1b68-112">invID</span></span>  <br/> |<span data-ttu-id="e1b68-113">int, не null</span><span class="sxs-lookup"><span data-stu-id="e1b68-113">int, not null</span></span>  <br/> |<span data-ttu-id="e1b68-114">Уникальный порядковый номер (на код участника) созданный для таблицы tblLastInviteId.</span><span class="sxs-lookup"><span data-stu-id="e1b68-114">Unique sequential number (per principal ID) generated from tblLastInviteId table.</span></span>  <br/> |
|<span data-ttu-id="e1b68-115">nodeID</span><span class="sxs-lookup"><span data-stu-id="e1b68-115">nodeID</span></span>  <br/> |<span data-ttu-id="e1b68-116">int, не null</span><span class="sxs-lookup"><span data-stu-id="e1b68-116">int, not null</span></span>  <br/> |<span data-ttu-id="e1b68-117">КОД узла (только комната чата).</span><span class="sxs-lookup"><span data-stu-id="e1b68-117">Node ID (chat room only).</span></span>  <br/> |
|<span data-ttu-id="e1b68-118">createdOn</span><span class="sxs-lookup"><span data-stu-id="e1b68-118">createdOn</span></span>  <br/> |<span data-ttu-id="e1b68-119">DateTime, не может быть null</span><span class="sxs-lookup"><span data-stu-id="e1b68-119">datetime, not null</span></span>  <br/> |<span data-ttu-id="e1b68-120">Время создания.</span><span class="sxs-lookup"><span data-stu-id="e1b68-120">Time of creation.</span></span>  <br/> |
   
<span data-ttu-id="e1b68-121">**Ключи**</span><span class="sxs-lookup"><span data-stu-id="e1b68-121">**Keys**</span></span>

|<span data-ttu-id="e1b68-122">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="e1b68-122">**Column**</span></span>|<span data-ttu-id="e1b68-123">**Описание**</span><span class="sxs-lookup"><span data-stu-id="e1b68-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e1b68-124">\<prinID nodeID\></span><span class="sxs-lookup"><span data-stu-id="e1b68-124">\<prinID, nodeID\></span></span>  <br/> |<span data-ttu-id="e1b68-125">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="e1b68-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="e1b68-126">prinID</span><span class="sxs-lookup"><span data-stu-id="e1b68-126">prinID</span></span>  <br/> |<span data-ttu-id="e1b68-127">Внешний ключ с подстановкой в таблице tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="e1b68-127">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="e1b68-128">nodeID</span><span class="sxs-lookup"><span data-stu-id="e1b68-128">nodeID</span></span>  <br/> |<span data-ttu-id="e1b68-129">Внешний ключ с подстановкой в таблице tblNode.nodeID.</span><span class="sxs-lookup"><span data-stu-id="e1b68-129">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
   

