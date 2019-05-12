---
title: tblPrincipalInvites
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 548ec156-4d1a-469d-a804-62cff226e5c2
description: tblPrincipalInvites содержит приглашения для всех подготовленных пользователей для всех узлов с автоматическим приглашением на.
ms.openlocfilehash: 5008158dcb1c62c766162595d9bffe1875d56514
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924425"
---
# <a name="tblprincipalinvites"></a><span data-ttu-id="d6599-103">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="d6599-103">tblPrincipalInvites</span></span>
 
<span data-ttu-id="d6599-104">tblPrincipalInvites содержит приглашения для всех подготовленных пользователей для всех узлов с автоматическим приглашением на.</span><span class="sxs-lookup"><span data-stu-id="d6599-104">tblPrincipalInvites contains invitations for all provisioned users for all nodes with auto-invite on.</span></span>
  
<span data-ttu-id="d6599-105">**Столбцы**</span><span class="sxs-lookup"><span data-stu-id="d6599-105">**Columns**</span></span>

|<span data-ttu-id="d6599-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="d6599-106">**Column**</span></span>|<span data-ttu-id="d6599-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="d6599-107">**Type**</span></span>|<span data-ttu-id="d6599-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="d6599-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d6599-109">prinID</span><span class="sxs-lookup"><span data-stu-id="d6599-109">prinID</span></span>  <br/> |<span data-ttu-id="d6599-110">int, не null</span><span class="sxs-lookup"><span data-stu-id="d6599-110">int, not null</span></span>  <br/> |<span data-ttu-id="d6599-111">Идентификатор субъекта.</span><span class="sxs-lookup"><span data-stu-id="d6599-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="d6599-112">invID</span><span class="sxs-lookup"><span data-stu-id="d6599-112">invID</span></span>  <br/> |<span data-ttu-id="d6599-113">int, не null</span><span class="sxs-lookup"><span data-stu-id="d6599-113">int, not null</span></span>  <br/> |<span data-ttu-id="d6599-114">Уникальный порядковый номер (на код участника) созданный для таблицы tblLastInviteId.</span><span class="sxs-lookup"><span data-stu-id="d6599-114">Unique sequential number (per principal ID) generated from tblLastInviteId table.</span></span>  <br/> |
|<span data-ttu-id="d6599-115">nodeID</span><span class="sxs-lookup"><span data-stu-id="d6599-115">nodeID</span></span>  <br/> |<span data-ttu-id="d6599-116">int, не null</span><span class="sxs-lookup"><span data-stu-id="d6599-116">int, not null</span></span>  <br/> |<span data-ttu-id="d6599-117">КОД узла (только комната чата).</span><span class="sxs-lookup"><span data-stu-id="d6599-117">Node ID (chat room only).</span></span>  <br/> |
|<span data-ttu-id="d6599-118">createdOn</span><span class="sxs-lookup"><span data-stu-id="d6599-118">createdOn</span></span>  <br/> |<span data-ttu-id="d6599-119">DateTime, не может быть null</span><span class="sxs-lookup"><span data-stu-id="d6599-119">datetime, not null</span></span>  <br/> |<span data-ttu-id="d6599-120">Время создания.</span><span class="sxs-lookup"><span data-stu-id="d6599-120">Time of creation.</span></span>  <br/> |
   
<span data-ttu-id="d6599-121">**Ключи**</span><span class="sxs-lookup"><span data-stu-id="d6599-121">**Keys**</span></span>

|<span data-ttu-id="d6599-122">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="d6599-122">**Column**</span></span>|<span data-ttu-id="d6599-123">**Описание**</span><span class="sxs-lookup"><span data-stu-id="d6599-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d6599-124">\<prinID nodeID\></span><span class="sxs-lookup"><span data-stu-id="d6599-124">\<prinID, nodeID\></span></span>  <br/> |<span data-ttu-id="d6599-125">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="d6599-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="d6599-126">prinID</span><span class="sxs-lookup"><span data-stu-id="d6599-126">prinID</span></span>  <br/> |<span data-ttu-id="d6599-127">Внешний ключ с подстановкой в таблице tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="d6599-127">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="d6599-128">nodeID</span><span class="sxs-lookup"><span data-stu-id="d6599-128">nodeID</span></span>  <br/> |<span data-ttu-id="d6599-129">Внешний ключ с подстановкой в таблице tblNode.nodeID.</span><span class="sxs-lookup"><span data-stu-id="d6599-129">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
   

