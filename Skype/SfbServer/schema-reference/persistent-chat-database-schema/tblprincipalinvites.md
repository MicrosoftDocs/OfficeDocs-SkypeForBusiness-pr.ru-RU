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
localization_priority: Normal
ms.assetid: 548ec156-4d1a-469d-a804-62cff226e5c2
description: ТблпринЦипалинвитес включает приглашения для всех подготовленных пользователей для всех узлов с автоматическим приглашением.
ms.openlocfilehash: 21344cfc34ce046a1dffdf7cd3ee9557da20a7ef
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295295"
---
# <a name="tblprincipalinvites"></a><span data-ttu-id="1d63b-103">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="1d63b-103">tblPrincipalInvites</span></span>
 
<span data-ttu-id="1d63b-104">ТблпринЦипалинвитес включает приглашения для всех подготовленных пользователей для всех узлов с автоматическим приглашением.</span><span class="sxs-lookup"><span data-stu-id="1d63b-104">tblPrincipalInvites contains invitations for all provisioned users for all nodes with auto-invite on.</span></span>
  
<span data-ttu-id="1d63b-105">**Столбцов**</span><span class="sxs-lookup"><span data-stu-id="1d63b-105">**Columns**</span></span>

|<span data-ttu-id="1d63b-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="1d63b-106">**Column**</span></span>|<span data-ttu-id="1d63b-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="1d63b-107">**Type**</span></span>|<span data-ttu-id="1d63b-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="1d63b-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1d63b-109">Принид</span><span class="sxs-lookup"><span data-stu-id="1d63b-109">prinID</span></span>  <br/> |<span data-ttu-id="1d63b-110">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="1d63b-110">int, not null</span></span>  <br/> |<span data-ttu-id="1d63b-111">Идентификатор участника.</span><span class="sxs-lookup"><span data-stu-id="1d63b-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="1d63b-112">ИНВИД</span><span class="sxs-lookup"><span data-stu-id="1d63b-112">invID</span></span>  <br/> |<span data-ttu-id="1d63b-113">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="1d63b-113">int, not null</span></span>  <br/> |<span data-ttu-id="1d63b-114">Уникальный последовательный номер (для идентификатора участника), сформированный из таблицы Тблластинвитеид.</span><span class="sxs-lookup"><span data-stu-id="1d63b-114">Unique sequential number (per principal ID) generated from tblLastInviteId table.</span></span>  <br/> |
|<span data-ttu-id="1d63b-115">Нодеид</span><span class="sxs-lookup"><span data-stu-id="1d63b-115">nodeID</span></span>  <br/> |<span data-ttu-id="1d63b-116">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="1d63b-116">int, not null</span></span>  <br/> |<span data-ttu-id="1d63b-117">Идентификатор узла (только для комнаты чата).</span><span class="sxs-lookup"><span data-stu-id="1d63b-117">Node ID (chat room only).</span></span>  <br/> |
|<span data-ttu-id="1d63b-118">Креатедон</span><span class="sxs-lookup"><span data-stu-id="1d63b-118">createdOn</span></span>  <br/> |<span data-ttu-id="1d63b-119">DateTime, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="1d63b-119">datetime, not null</span></span>  <br/> |<span data-ttu-id="1d63b-120">Время создания.</span><span class="sxs-lookup"><span data-stu-id="1d63b-120">Time of creation.</span></span>  <br/> |
   
<span data-ttu-id="1d63b-121">**Параметры**</span><span class="sxs-lookup"><span data-stu-id="1d63b-121">**Keys**</span></span>

|<span data-ttu-id="1d63b-122">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="1d63b-122">**Column**</span></span>|<span data-ttu-id="1d63b-123">**Описание**</span><span class="sxs-lookup"><span data-stu-id="1d63b-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1d63b-124">\<Принид, Нодеид\></span><span class="sxs-lookup"><span data-stu-id="1d63b-124">\<prinID, nodeID\></span></span>  <br/> |<span data-ttu-id="1d63b-125">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="1d63b-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="1d63b-126">Принид</span><span class="sxs-lookup"><span data-stu-id="1d63b-126">prinID</span></span>  <br/> |<span data-ttu-id="1d63b-127">Внешний ключ с подстановкой в таблице ТблпринЦипал. Принид.</span><span class="sxs-lookup"><span data-stu-id="1d63b-127">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="1d63b-128">Нодеид</span><span class="sxs-lookup"><span data-stu-id="1d63b-128">nodeID</span></span>  <br/> |<span data-ttu-id="1d63b-129">Внешний ключ с подстановкой в таблице Тблноде. Нодеид.</span><span class="sxs-lookup"><span data-stu-id="1d63b-129">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
   

