---
title: tblADUpdates
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ba19fa16-4d2d-4635-ac32-f93e09469546
description: Таблица tblADUpdates содержит изменения доменных служб Active Directory, которые еще не были обработаны с последующих этапах синхронизации Active Directory.
ms.openlocfilehash: 33d2ae6d2113d3f55b0fdf54439e2383ca142589
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="tbladupdates"></a><span data-ttu-id="f510d-103">tblADUpdates</span><span class="sxs-lookup"><span data-stu-id="f510d-103">tblADUpdates</span></span>
 
<span data-ttu-id="f510d-104">Таблица tblADUpdates содержит изменения доменных служб Active Directory, которые еще не были обработаны с последующих этапах синхронизации Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f510d-104">tblADUpdates contains Active Directory Domain Services changes that have not yet been processed by the later Active Directory Sync steps.</span></span>
  
<span data-ttu-id="f510d-105">**Столбцы**</span><span class="sxs-lookup"><span data-stu-id="f510d-105">**Columns**</span></span>

|<span data-ttu-id="f510d-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="f510d-106">**Column**</span></span>|<span data-ttu-id="f510d-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="f510d-107">**Type**</span></span>|<span data-ttu-id="f510d-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="f510d-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f510d-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="f510d-109">prinGuid</span></span>  <br/> |<span data-ttu-id="f510d-110">Идентификатор GUID, не может быть null</span><span class="sxs-lookup"><span data-stu-id="f510d-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="f510d-111">Глобальный Уникальный ИД измененного объекта.</span><span class="sxs-lookup"><span data-stu-id="f510d-111">Principal GUID of the object that changed.</span></span>  <br/> |
|<span data-ttu-id="f510d-112">prinADPath</span><span class="sxs-lookup"><span data-stu-id="f510d-112">prinADPath</span></span>  <br/> |<span data-ttu-id="f510d-113">nvarchar (384), отлично от null</span><span class="sxs-lookup"><span data-stu-id="f510d-113">nvarchar (384), not null</span></span>  <br/> |<span data-ttu-id="f510d-114">Различающееся имя объекта.</span><span class="sxs-lookup"><span data-stu-id="f510d-114">Distinguished name of the object.</span></span>  <br/> |
|<span data-ttu-id="f510d-115">prinAttributesChanged</span><span class="sxs-lookup"><span data-stu-id="f510d-115">prinAttributesChanged</span></span>  <br/> |<span data-ttu-id="f510d-116">bit, не может быть null</span><span class="sxs-lookup"><span data-stu-id="f510d-116">bit, not null</span></span>  <br/> |<span data-ttu-id="f510d-117">Значение true, если хотя бы один атрибут объекта изменяется.</span><span class="sxs-lookup"><span data-stu-id="f510d-117">True if at least one attribute of the object changed.</span></span>  <br/> |
|<span data-ttu-id="f510d-118">prinMembersChanged</span><span class="sxs-lookup"><span data-stu-id="f510d-118">prinMembersChanged</span></span>  <br/> |<span data-ttu-id="f510d-119">bit, не может быть null</span><span class="sxs-lookup"><span data-stu-id="f510d-119">bit, not null</span></span>  <br/> |<span data-ttu-id="f510d-120">Значение true, если изменилось членство.</span><span class="sxs-lookup"><span data-stu-id="f510d-120">True if the membership changed.</span></span>  <br/> |
|<span data-ttu-id="f510d-121">prinAffiliationsChanged</span><span class="sxs-lookup"><span data-stu-id="f510d-121">prinAffiliationsChanged</span></span>  <br/> |<span data-ttu-id="f510d-122">bit, не может быть null</span><span class="sxs-lookup"><span data-stu-id="f510d-122">bit, not null</span></span>  <br/> |<span data-ttu-id="f510d-123">Не используется.</span><span class="sxs-lookup"><span data-stu-id="f510d-123">Not used.</span></span>  <br/> |
|<span data-ttu-id="f510d-124">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="f510d-124">prinDeleted</span></span>  <br/> |<span data-ttu-id="f510d-125">bit, не может быть null</span><span class="sxs-lookup"><span data-stu-id="f510d-125">bit, not null</span></span>  <br/> |<span data-ttu-id="f510d-126">Значение true, если объект был удален.</span><span class="sxs-lookup"><span data-stu-id="f510d-126">True if the object was deleted.</span></span>  <br/> |
|<span data-ttu-id="f510d-127">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="f510d-127">lastUpdated</span></span>  <br/> |<span data-ttu-id="f510d-128">DateTime, не может быть null</span><span class="sxs-lookup"><span data-stu-id="f510d-128">datetime, not null</span></span>  <br/> |<span data-ttu-id="f510d-129">Когда строка была вставлена метка времени.</span><span class="sxs-lookup"><span data-stu-id="f510d-129">Time stamp of when the row was inserted.</span></span>  <br/> |
   

