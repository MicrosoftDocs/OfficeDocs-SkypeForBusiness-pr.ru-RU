---
title: tblADUpdates
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
ms.assetid: ba19fa16-4d2d-4635-ac32-f93e09469546
description: Тбладупдатес содержит изменения доменных служб Active Directory, которые еще не были обработаны с помощью последующих шагов синхронизации Active Directory.
ms.openlocfilehash: 6d50e065bd10e11383f606b2a4dfed0d5584cd1e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814687"
---
# <a name="tbladupdates"></a><span data-ttu-id="6b78b-103">tblADUpdates</span><span class="sxs-lookup"><span data-stu-id="6b78b-103">tblADUpdates</span></span>
 
<span data-ttu-id="6b78b-104">Тбладупдатес содержит изменения доменных служб Active Directory, которые еще не были обработаны с помощью последующих шагов синхронизации Active Directory.</span><span class="sxs-lookup"><span data-stu-id="6b78b-104">tblADUpdates contains Active Directory Domain Services changes that have not yet been processed by the later Active Directory Sync steps.</span></span>
  
<span data-ttu-id="6b78b-105">**Столбцов**</span><span class="sxs-lookup"><span data-stu-id="6b78b-105">**Columns**</span></span>

|<span data-ttu-id="6b78b-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="6b78b-106">**Column**</span></span>|<span data-ttu-id="6b78b-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="6b78b-107">**Type**</span></span>|<span data-ttu-id="6b78b-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="6b78b-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6b78b-109">прингуид</span><span class="sxs-lookup"><span data-stu-id="6b78b-109">prinGuid</span></span>  <br/> |<span data-ttu-id="6b78b-110">GUID, а не NULL</span><span class="sxs-lookup"><span data-stu-id="6b78b-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="6b78b-111">Идентификатор GUID участника измененного объекта.</span><span class="sxs-lookup"><span data-stu-id="6b78b-111">Principal GUID of the object that changed.</span></span>  <br/> |
|<span data-ttu-id="6b78b-112">принадпас</span><span class="sxs-lookup"><span data-stu-id="6b78b-112">prinADPath</span></span>  <br/> |<span data-ttu-id="6b78b-113">nvarchar (384), NOT NULL</span><span class="sxs-lookup"><span data-stu-id="6b78b-113">nvarchar (384), not null</span></span>  <br/> |<span data-ttu-id="6b78b-114">Отличительное имя объекта.</span><span class="sxs-lookup"><span data-stu-id="6b78b-114">Distinguished name of the object.</span></span>  <br/> |
|<span data-ttu-id="6b78b-115">принаттрибутесчанжед</span><span class="sxs-lookup"><span data-stu-id="6b78b-115">prinAttributesChanged</span></span>  <br/> |<span data-ttu-id="6b78b-116">bit, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="6b78b-116">bit, not null</span></span>  <br/> |<span data-ttu-id="6b78b-117">Значение true, если по крайней мере один из атрибутов объекта изменился.</span><span class="sxs-lookup"><span data-stu-id="6b78b-117">True if at least one attribute of the object changed.</span></span>  <br/> |
|<span data-ttu-id="6b78b-118">принмемберсчанжед</span><span class="sxs-lookup"><span data-stu-id="6b78b-118">prinMembersChanged</span></span>  <br/> |<span data-ttu-id="6b78b-119">bit, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="6b78b-119">bit, not null</span></span>  <br/> |<span data-ttu-id="6b78b-120">Значение true, если изменилось членство.</span><span class="sxs-lookup"><span data-stu-id="6b78b-120">True if the membership changed.</span></span>  <br/> |
|<span data-ttu-id="6b78b-121">принаффилиатионсчанжед</span><span class="sxs-lookup"><span data-stu-id="6b78b-121">prinAffiliationsChanged</span></span>  <br/> |<span data-ttu-id="6b78b-122">bit, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="6b78b-122">bit, not null</span></span>  <br/> |<span data-ttu-id="6b78b-123">Не используется.</span><span class="sxs-lookup"><span data-stu-id="6b78b-123">Not used.</span></span>  <br/> |
|<span data-ttu-id="6b78b-124">принделетед</span><span class="sxs-lookup"><span data-stu-id="6b78b-124">prinDeleted</span></span>  <br/> |<span data-ttu-id="6b78b-125">bit, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="6b78b-125">bit, not null</span></span>  <br/> |<span data-ttu-id="6b78b-126">Значение true, если объект был удален.</span><span class="sxs-lookup"><span data-stu-id="6b78b-126">True if the object was deleted.</span></span>  <br/> |
|<span data-ttu-id="6b78b-127">ластупдатед</span><span class="sxs-lookup"><span data-stu-id="6b78b-127">lastUpdated</span></span>  <br/> |<span data-ttu-id="6b78b-128">DateTime, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="6b78b-128">datetime, not null</span></span>  <br/> |<span data-ttu-id="6b78b-129">Метка времени вставки строки.</span><span class="sxs-lookup"><span data-stu-id="6b78b-129">Time stamp of when the row was inserted.</span></span>  <br/> |
   

