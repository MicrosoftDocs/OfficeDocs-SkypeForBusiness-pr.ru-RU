---
title: tblScopePrincipal
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
ms.assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
description: ТблскопепринЦипал включает области, назначенные узлам.
ms.openlocfilehash: 24a38ef4acf3e0d500c7652f5ca418af585343b6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812447"
---
# <a name="tblscopeprincipal"></a><span data-ttu-id="03d4d-103">tblScopePrincipal</span><span class="sxs-lookup"><span data-stu-id="03d4d-103">tblScopePrincipal</span></span>
 
<span data-ttu-id="03d4d-104">ТблскопепринЦипал включает области, назначенные узлам.</span><span class="sxs-lookup"><span data-stu-id="03d4d-104">tblScopePrincipal contains scopes assigned to nodes.</span></span>
  
<span data-ttu-id="03d4d-105">**Столбцов**</span><span class="sxs-lookup"><span data-stu-id="03d4d-105">**Columns**</span></span>

|<span data-ttu-id="03d4d-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="03d4d-106">**Column**</span></span>|<span data-ttu-id="03d4d-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="03d4d-107">**Type**</span></span>|<span data-ttu-id="03d4d-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="03d4d-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="03d4d-109">скопенодеид</span><span class="sxs-lookup"><span data-stu-id="03d4d-109">scopeNodeID</span></span>  <br/> |<span data-ttu-id="03d4d-110">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="03d4d-110">int, not null</span></span>  <br/> |<span data-ttu-id="03d4d-111">Идентификатор узла, к которому относится область.</span><span class="sxs-lookup"><span data-stu-id="03d4d-111">Node ID that the scope applies to.</span></span>  <br/> |
|<span data-ttu-id="03d4d-112">скопепринид</span><span class="sxs-lookup"><span data-stu-id="03d4d-112">scopePrinID</span></span>  <br/> |<span data-ttu-id="03d4d-113">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="03d4d-113">int, not null</span></span>  <br/> |<span data-ttu-id="03d4d-114">Идентификатор участника.</span><span class="sxs-lookup"><span data-stu-id="03d4d-114">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="03d4d-115">скопеисдениед</span><span class="sxs-lookup"><span data-stu-id="03d4d-115">scopeIsDenied</span></span>  <br/> |<span data-ttu-id="03d4d-116">bit, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="03d4d-116">bit, not null</span></span>  <br/> |<span data-ttu-id="03d4d-117">Значение true, если тип области — Deny; Значение false, если разрешено.</span><span class="sxs-lookup"><span data-stu-id="03d4d-117">True if type of scope is Deny; False if Allow.</span></span>  <br/> |
|<span data-ttu-id="03d4d-118">скопеупдатедби</span><span class="sxs-lookup"><span data-stu-id="03d4d-118">scopeUpdatedBy</span></span>  <br/> |<span data-ttu-id="03d4d-119">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="03d4d-119">int, not null</span></span>  <br/> |<span data-ttu-id="03d4d-120">Идентификатор участника, который последним обновил эту запись.</span><span class="sxs-lookup"><span data-stu-id="03d4d-120">ID of the principal that last updated this entry.</span></span>  <br/> |
   
<span data-ttu-id="03d4d-121">**Параметры**</span><span class="sxs-lookup"><span data-stu-id="03d4d-121">**Keys**</span></span>

|<span data-ttu-id="03d4d-122">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="03d4d-122">**Column**</span></span>|<span data-ttu-id="03d4d-123">**Описание**</span><span class="sxs-lookup"><span data-stu-id="03d4d-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="03d4d-124">\<Скопенодеид, Скопепринид\></span><span class="sxs-lookup"><span data-stu-id="03d4d-124">\<scopeNodeID, scopePrinID\></span></span>  <br/> |<span data-ttu-id="03d4d-125">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="03d4d-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="03d4d-126">скопенодеид</span><span class="sxs-lookup"><span data-stu-id="03d4d-126">scopeNodeID</span></span>  <br/> |<span data-ttu-id="03d4d-127">Внешний ключ с подстановкой в таблице Тблноде. Нодеид.</span><span class="sxs-lookup"><span data-stu-id="03d4d-127">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
|<span data-ttu-id="03d4d-128">скопепринид</span><span class="sxs-lookup"><span data-stu-id="03d4d-128">scopePrinID</span></span>  <br/> |<span data-ttu-id="03d4d-129">Внешний ключ с подстановкой в таблице ТблпринЦипал. Принид.</span><span class="sxs-lookup"><span data-stu-id="03d4d-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

