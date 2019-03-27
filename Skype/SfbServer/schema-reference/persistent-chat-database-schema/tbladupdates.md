---
title: tblADUpdates
ms.reviewer: ''
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
ms.openlocfilehash: 0e7bde110ad3d0495cb7ddea55e405eac21d96b4
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30899605"
---
# <a name="tbladupdates"></a><span data-ttu-id="f7dff-103">tblADUpdates</span><span class="sxs-lookup"><span data-stu-id="f7dff-103">tblADUpdates</span></span>
 
<span data-ttu-id="f7dff-104">Таблица tblADUpdates содержит изменения доменных служб Active Directory, которые еще не были обработаны с последующих этапах синхронизации Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f7dff-104">tblADUpdates contains Active Directory Domain Services changes that have not yet been processed by the later Active Directory Sync steps.</span></span>
  
<span data-ttu-id="f7dff-105">**Столбцы**</span><span class="sxs-lookup"><span data-stu-id="f7dff-105">**Columns**</span></span>

|<span data-ttu-id="f7dff-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="f7dff-106">**Column**</span></span>|<span data-ttu-id="f7dff-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="f7dff-107">**Type**</span></span>|<span data-ttu-id="f7dff-108">**Описание**.</span><span class="sxs-lookup"><span data-stu-id="f7dff-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f7dff-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="f7dff-109">prinGuid</span></span>  <br/> |<span data-ttu-id="f7dff-110">Идентификатор GUID, не может быть null</span><span class="sxs-lookup"><span data-stu-id="f7dff-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="f7dff-111">Глобальный Уникальный ИД измененного объекта.</span><span class="sxs-lookup"><span data-stu-id="f7dff-111">Principal GUID of the object that changed.</span></span>  <br/> |
|<span data-ttu-id="f7dff-112">prinADPath</span><span class="sxs-lookup"><span data-stu-id="f7dff-112">prinADPath</span></span>  <br/> |<span data-ttu-id="f7dff-113">nvarchar (384), отлично от null</span><span class="sxs-lookup"><span data-stu-id="f7dff-113">nvarchar (384), not null</span></span>  <br/> |<span data-ttu-id="f7dff-114">Различающееся имя объекта.</span><span class="sxs-lookup"><span data-stu-id="f7dff-114">Distinguished name of the object.</span></span>  <br/> |
|<span data-ttu-id="f7dff-115">prinAttributesChanged</span><span class="sxs-lookup"><span data-stu-id="f7dff-115">prinAttributesChanged</span></span>  <br/> |<span data-ttu-id="f7dff-116">bit, не может быть null</span><span class="sxs-lookup"><span data-stu-id="f7dff-116">bit, not null</span></span>  <br/> |<span data-ttu-id="f7dff-117">Значение true, если хотя бы один атрибут объекта изменяется.</span><span class="sxs-lookup"><span data-stu-id="f7dff-117">True if at least one attribute of the object changed.</span></span>  <br/> |
|<span data-ttu-id="f7dff-118">prinMembersChanged</span><span class="sxs-lookup"><span data-stu-id="f7dff-118">prinMembersChanged</span></span>  <br/> |<span data-ttu-id="f7dff-119">bit, не может быть null</span><span class="sxs-lookup"><span data-stu-id="f7dff-119">bit, not null</span></span>  <br/> |<span data-ttu-id="f7dff-120">Значение true, если изменилось членство.</span><span class="sxs-lookup"><span data-stu-id="f7dff-120">True if the membership changed.</span></span>  <br/> |
|<span data-ttu-id="f7dff-121">prinAffiliationsChanged</span><span class="sxs-lookup"><span data-stu-id="f7dff-121">prinAffiliationsChanged</span></span>  <br/> |<span data-ttu-id="f7dff-122">bit, не может быть null</span><span class="sxs-lookup"><span data-stu-id="f7dff-122">bit, not null</span></span>  <br/> |<span data-ttu-id="f7dff-123">Не используется.</span><span class="sxs-lookup"><span data-stu-id="f7dff-123">Not used.</span></span>  <br/> |
|<span data-ttu-id="f7dff-124">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="f7dff-124">prinDeleted</span></span>  <br/> |<span data-ttu-id="f7dff-125">bit, не может быть null</span><span class="sxs-lookup"><span data-stu-id="f7dff-125">bit, not null</span></span>  <br/> |<span data-ttu-id="f7dff-126">Значение true, если объект был удален.</span><span class="sxs-lookup"><span data-stu-id="f7dff-126">True if the object was deleted.</span></span>  <br/> |
|<span data-ttu-id="f7dff-127">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="f7dff-127">lastUpdated</span></span>  <br/> |<span data-ttu-id="f7dff-128">DateTime, не может быть null</span><span class="sxs-lookup"><span data-stu-id="f7dff-128">datetime, not null</span></span>  <br/> |<span data-ttu-id="f7dff-129">Когда строка была вставлена метка времени.</span><span class="sxs-lookup"><span data-stu-id="f7dff-129">Time stamp of when the row was inserted.</span></span>  <br/> |
   

