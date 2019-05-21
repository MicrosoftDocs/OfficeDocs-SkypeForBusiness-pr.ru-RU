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
localization_priority: Normal
ms.assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
description: ТблскопепринЦипал включает области, назначенные узлам.
ms.openlocfilehash: 2fd8e434710c7bcd266c427fa492e23adacedb22
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295197"
---
# <a name="tblscopeprincipal"></a><span data-ttu-id="79507-103">tblScopePrincipal</span><span class="sxs-lookup"><span data-stu-id="79507-103">tblScopePrincipal</span></span>
 
<span data-ttu-id="79507-104">ТблскопепринЦипал включает области, назначенные узлам.</span><span class="sxs-lookup"><span data-stu-id="79507-104">tblScopePrincipal contains scopes assigned to nodes.</span></span>
  
<span data-ttu-id="79507-105">**Столбцов**</span><span class="sxs-lookup"><span data-stu-id="79507-105">**Columns**</span></span>

|<span data-ttu-id="79507-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="79507-106">**Column**</span></span>|<span data-ttu-id="79507-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="79507-107">**Type**</span></span>|<span data-ttu-id="79507-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="79507-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="79507-109">Скопенодеид</span><span class="sxs-lookup"><span data-stu-id="79507-109">scopeNodeID</span></span>  <br/> |<span data-ttu-id="79507-110">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="79507-110">int, not null</span></span>  <br/> |<span data-ttu-id="79507-111">Идентификатор узла, к которому относится область.</span><span class="sxs-lookup"><span data-stu-id="79507-111">Node ID that the scope applies to.</span></span>  <br/> |
|<span data-ttu-id="79507-112">Скопепринид</span><span class="sxs-lookup"><span data-stu-id="79507-112">scopePrinID</span></span>  <br/> |<span data-ttu-id="79507-113">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="79507-113">int, not null</span></span>  <br/> |<span data-ttu-id="79507-114">Идентификатор участника.</span><span class="sxs-lookup"><span data-stu-id="79507-114">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="79507-115">Скопеисдениед</span><span class="sxs-lookup"><span data-stu-id="79507-115">scopeIsDenied</span></span>  <br/> |<span data-ttu-id="79507-116">bit, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="79507-116">bit, not null</span></span>  <br/> |<span data-ttu-id="79507-117">Значение true, если тип области — Deny; Значение false, если разрешено.</span><span class="sxs-lookup"><span data-stu-id="79507-117">True if type of scope is Deny; False if Allow.</span></span>  <br/> |
|<span data-ttu-id="79507-118">Скопеупдатедби</span><span class="sxs-lookup"><span data-stu-id="79507-118">scopeUpdatedBy</span></span>  <br/> |<span data-ttu-id="79507-119">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="79507-119">int, not null</span></span>  <br/> |<span data-ttu-id="79507-120">Идентификатор участника, который последним обновил эту запись.</span><span class="sxs-lookup"><span data-stu-id="79507-120">ID of the principal that last updated this entry.</span></span>  <br/> |
   
<span data-ttu-id="79507-121">**Параметры**</span><span class="sxs-lookup"><span data-stu-id="79507-121">**Keys**</span></span>

|<span data-ttu-id="79507-122">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="79507-122">**Column**</span></span>|<span data-ttu-id="79507-123">**Описание**</span><span class="sxs-lookup"><span data-stu-id="79507-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="79507-124">\<Скопенодеид, Скопепринид\></span><span class="sxs-lookup"><span data-stu-id="79507-124">\<scopeNodeID, scopePrinID\></span></span>  <br/> |<span data-ttu-id="79507-125">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="79507-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="79507-126">Скопенодеид</span><span class="sxs-lookup"><span data-stu-id="79507-126">scopeNodeID</span></span>  <br/> |<span data-ttu-id="79507-127">Внешний ключ с подстановкой в таблице Тблноде. Нодеид.</span><span class="sxs-lookup"><span data-stu-id="79507-127">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
|<span data-ttu-id="79507-128">Скопепринид</span><span class="sxs-lookup"><span data-stu-id="79507-128">scopePrinID</span></span>  <br/> |<span data-ttu-id="79507-129">Внешний ключ с подстановкой в таблице ТблпринЦипал. Принид.</span><span class="sxs-lookup"><span data-stu-id="79507-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

