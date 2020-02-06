---
title: tblPrincipalInvites
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
ms.assetid: 548ec156-4d1a-469d-a804-62cff226e5c2
description: ТблпринЦипалинвитес включает приглашения для всех подготовленных пользователей для всех узлов с автоматическим приглашением.
ms.openlocfilehash: dfa41ec5715c7c5255b26fcdb32561e74c4f08df
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814187"
---
# <a name="tblprincipalinvites"></a><span data-ttu-id="8568f-103">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="8568f-103">tblPrincipalInvites</span></span>
 
<span data-ttu-id="8568f-104">ТблпринЦипалинвитес включает приглашения для всех подготовленных пользователей для всех узлов с автоматическим приглашением.</span><span class="sxs-lookup"><span data-stu-id="8568f-104">tblPrincipalInvites contains invitations for all provisioned users for all nodes with auto-invite on.</span></span>
  
<span data-ttu-id="8568f-105">**Столбцов**</span><span class="sxs-lookup"><span data-stu-id="8568f-105">**Columns**</span></span>

|<span data-ttu-id="8568f-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="8568f-106">**Column**</span></span>|<span data-ttu-id="8568f-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="8568f-107">**Type**</span></span>|<span data-ttu-id="8568f-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="8568f-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="8568f-109">принид</span><span class="sxs-lookup"><span data-stu-id="8568f-109">prinID</span></span>  <br/> |<span data-ttu-id="8568f-110">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="8568f-110">int, not null</span></span>  <br/> |<span data-ttu-id="8568f-111">Идентификатор участника.</span><span class="sxs-lookup"><span data-stu-id="8568f-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="8568f-112">инвид</span><span class="sxs-lookup"><span data-stu-id="8568f-112">invID</span></span>  <br/> |<span data-ttu-id="8568f-113">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="8568f-113">int, not null</span></span>  <br/> |<span data-ttu-id="8568f-114">Уникальный последовательный номер (для идентификатора участника), сформированный из таблицы Тблластинвитеид.</span><span class="sxs-lookup"><span data-stu-id="8568f-114">Unique sequential number (per principal ID) generated from tblLastInviteId table.</span></span>  <br/> |
|<span data-ttu-id="8568f-115">нодеид</span><span class="sxs-lookup"><span data-stu-id="8568f-115">nodeID</span></span>  <br/> |<span data-ttu-id="8568f-116">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="8568f-116">int, not null</span></span>  <br/> |<span data-ttu-id="8568f-117">Идентификатор узла (только для комнаты чата).</span><span class="sxs-lookup"><span data-stu-id="8568f-117">Node ID (chat room only).</span></span>  <br/> |
|<span data-ttu-id="8568f-118">креатедон</span><span class="sxs-lookup"><span data-stu-id="8568f-118">createdOn</span></span>  <br/> |<span data-ttu-id="8568f-119">DateTime, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="8568f-119">datetime, not null</span></span>  <br/> |<span data-ttu-id="8568f-120">Время создания.</span><span class="sxs-lookup"><span data-stu-id="8568f-120">Time of creation.</span></span>  <br/> |
   
<span data-ttu-id="8568f-121">**Параметры**</span><span class="sxs-lookup"><span data-stu-id="8568f-121">**Keys**</span></span>

|<span data-ttu-id="8568f-122">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="8568f-122">**Column**</span></span>|<span data-ttu-id="8568f-123">**Описание**</span><span class="sxs-lookup"><span data-stu-id="8568f-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8568f-124">\<Принид, Нодеид\></span><span class="sxs-lookup"><span data-stu-id="8568f-124">\<prinID, nodeID\></span></span>  <br/> |<span data-ttu-id="8568f-125">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="8568f-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="8568f-126">принид</span><span class="sxs-lookup"><span data-stu-id="8568f-126">prinID</span></span>  <br/> |<span data-ttu-id="8568f-127">Внешний ключ с подстановкой в таблице ТблпринЦипал. Принид.</span><span class="sxs-lookup"><span data-stu-id="8568f-127">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="8568f-128">нодеид</span><span class="sxs-lookup"><span data-stu-id="8568f-128">nodeID</span></span>  <br/> |<span data-ttu-id="8568f-129">Внешний ключ с подстановкой в таблице Тблноде. Нодеид.</span><span class="sxs-lookup"><span data-stu-id="8568f-129">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
   

