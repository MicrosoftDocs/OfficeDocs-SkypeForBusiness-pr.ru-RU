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
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30876692"
---
# <a name="tblprincipalinvites"></a><span data-ttu-id="006cb-103">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="006cb-103">tblPrincipalInvites</span></span>
 
<span data-ttu-id="006cb-104">tblPrincipalInvites содержит приглашения для всех подготовленных пользователей для всех узлов с автоматическим приглашением на.</span><span class="sxs-lookup"><span data-stu-id="006cb-104">tblPrincipalInvites contains invitations for all provisioned users for all nodes with auto-invite on.</span></span>
  
<span data-ttu-id="006cb-105">**Столбцы**</span><span class="sxs-lookup"><span data-stu-id="006cb-105">**Columns**</span></span>

|<span data-ttu-id="006cb-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="006cb-106">**Column**</span></span>|<span data-ttu-id="006cb-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="006cb-107">**Type**</span></span>|<span data-ttu-id="006cb-108">**Описание**.</span><span class="sxs-lookup"><span data-stu-id="006cb-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="006cb-109">prinID</span><span class="sxs-lookup"><span data-stu-id="006cb-109">prinID</span></span>  <br/> |<span data-ttu-id="006cb-110">int, не null</span><span class="sxs-lookup"><span data-stu-id="006cb-110">int, not null</span></span>  <br/> |<span data-ttu-id="006cb-111">Идентификатор субъекта.</span><span class="sxs-lookup"><span data-stu-id="006cb-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="006cb-112">invID</span><span class="sxs-lookup"><span data-stu-id="006cb-112">invID</span></span>  <br/> |<span data-ttu-id="006cb-113">int, не null</span><span class="sxs-lookup"><span data-stu-id="006cb-113">int, not null</span></span>  <br/> |<span data-ttu-id="006cb-114">Уникальный порядковый номер (на код участника) созданный для таблицы tblLastInviteId.</span><span class="sxs-lookup"><span data-stu-id="006cb-114">Unique sequential number (per principal ID) generated from tblLastInviteId table.</span></span>  <br/> |
|<span data-ttu-id="006cb-115">nodeID</span><span class="sxs-lookup"><span data-stu-id="006cb-115">nodeID</span></span>  <br/> |<span data-ttu-id="006cb-116">int, не null</span><span class="sxs-lookup"><span data-stu-id="006cb-116">int, not null</span></span>  <br/> |<span data-ttu-id="006cb-117">КОД узла (только комната чата).</span><span class="sxs-lookup"><span data-stu-id="006cb-117">Node ID (chat room only).</span></span>  <br/> |
|<span data-ttu-id="006cb-118">createdOn</span><span class="sxs-lookup"><span data-stu-id="006cb-118">createdOn</span></span>  <br/> |<span data-ttu-id="006cb-119">DateTime, не может быть null</span><span class="sxs-lookup"><span data-stu-id="006cb-119">datetime, not null</span></span>  <br/> |<span data-ttu-id="006cb-120">Время создания.</span><span class="sxs-lookup"><span data-stu-id="006cb-120">Time of creation.</span></span>  <br/> |
   
<span data-ttu-id="006cb-121">**Ключи**</span><span class="sxs-lookup"><span data-stu-id="006cb-121">**Keys**</span></span>

|<span data-ttu-id="006cb-122">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="006cb-122">**Column**</span></span>|<span data-ttu-id="006cb-123">**Описание**.</span><span class="sxs-lookup"><span data-stu-id="006cb-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="006cb-124">\<prinID nodeID\></span><span class="sxs-lookup"><span data-stu-id="006cb-124">\<prinID, nodeID\></span></span>  <br/> |<span data-ttu-id="006cb-125">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="006cb-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="006cb-126">prinID</span><span class="sxs-lookup"><span data-stu-id="006cb-126">prinID</span></span>  <br/> |<span data-ttu-id="006cb-127">Внешний ключ с подстановкой в таблице tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="006cb-127">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="006cb-128">nodeID</span><span class="sxs-lookup"><span data-stu-id="006cb-128">nodeID</span></span>  <br/> |<span data-ttu-id="006cb-129">Внешний ключ с подстановкой в таблице tblNode.nodeID.</span><span class="sxs-lookup"><span data-stu-id="006cb-129">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
   

