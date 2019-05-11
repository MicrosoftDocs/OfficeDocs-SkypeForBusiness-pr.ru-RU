---
title: tblADUpdates
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ba19fa16-4d2d-4635-ac32-f93e09469546
description: Таблица tblADUpdates содержит изменения доменных служб Active Directory, которые еще не были обработаны с последующих этапах синхронизации Active Directory.
ms.openlocfilehash: 4ed1abe2d5926c8b34ddccb28133ecc34ddaa03a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929863"
---
# <a name="tbladupdates"></a><span data-ttu-id="5b082-103">tblADUpdates</span><span class="sxs-lookup"><span data-stu-id="5b082-103">tblADUpdates</span></span>
 
<span data-ttu-id="5b082-104">Таблица tblADUpdates содержит изменения доменных служб Active Directory, которые еще не были обработаны с последующих этапах синхронизации Active Directory.</span><span class="sxs-lookup"><span data-stu-id="5b082-104">tblADUpdates contains Active Directory Domain Services changes that have not yet been processed by the later Active Directory Sync steps.</span></span>
  
<span data-ttu-id="5b082-105">**Столбцы**</span><span class="sxs-lookup"><span data-stu-id="5b082-105">**Columns**</span></span>

|<span data-ttu-id="5b082-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="5b082-106">**Column**</span></span>|<span data-ttu-id="5b082-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="5b082-107">**Type**</span></span>|<span data-ttu-id="5b082-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="5b082-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="5b082-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="5b082-109">prinGuid</span></span>  <br/> |<span data-ttu-id="5b082-110">Идентификатор GUID, не может быть null</span><span class="sxs-lookup"><span data-stu-id="5b082-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="5b082-111">Глобальный Уникальный ИД измененного объекта.</span><span class="sxs-lookup"><span data-stu-id="5b082-111">Principal GUID of the object that changed.</span></span>  <br/> |
|<span data-ttu-id="5b082-112">prinADPath</span><span class="sxs-lookup"><span data-stu-id="5b082-112">prinADPath</span></span>  <br/> |<span data-ttu-id="5b082-113">nvarchar (384), отлично от null</span><span class="sxs-lookup"><span data-stu-id="5b082-113">nvarchar (384), not null</span></span>  <br/> |<span data-ttu-id="5b082-114">Различающееся имя объекта.</span><span class="sxs-lookup"><span data-stu-id="5b082-114">Distinguished name of the object.</span></span>  <br/> |
|<span data-ttu-id="5b082-115">prinAttributesChanged</span><span class="sxs-lookup"><span data-stu-id="5b082-115">prinAttributesChanged</span></span>  <br/> |<span data-ttu-id="5b082-116">bit, не может быть null</span><span class="sxs-lookup"><span data-stu-id="5b082-116">bit, not null</span></span>  <br/> |<span data-ttu-id="5b082-117">Значение true, если хотя бы один атрибут объекта изменяется.</span><span class="sxs-lookup"><span data-stu-id="5b082-117">True if at least one attribute of the object changed.</span></span>  <br/> |
|<span data-ttu-id="5b082-118">prinMembersChanged</span><span class="sxs-lookup"><span data-stu-id="5b082-118">prinMembersChanged</span></span>  <br/> |<span data-ttu-id="5b082-119">bit, не может быть null</span><span class="sxs-lookup"><span data-stu-id="5b082-119">bit, not null</span></span>  <br/> |<span data-ttu-id="5b082-120">Значение true, если изменилось членство.</span><span class="sxs-lookup"><span data-stu-id="5b082-120">True if the membership changed.</span></span>  <br/> |
|<span data-ttu-id="5b082-121">prinAffiliationsChanged</span><span class="sxs-lookup"><span data-stu-id="5b082-121">prinAffiliationsChanged</span></span>  <br/> |<span data-ttu-id="5b082-122">bit, не может быть null</span><span class="sxs-lookup"><span data-stu-id="5b082-122">bit, not null</span></span>  <br/> |<span data-ttu-id="5b082-123">Не используется.</span><span class="sxs-lookup"><span data-stu-id="5b082-123">Not used.</span></span>  <br/> |
|<span data-ttu-id="5b082-124">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="5b082-124">prinDeleted</span></span>  <br/> |<span data-ttu-id="5b082-125">bit, не может быть null</span><span class="sxs-lookup"><span data-stu-id="5b082-125">bit, not null</span></span>  <br/> |<span data-ttu-id="5b082-126">Значение true, если объект был удален.</span><span class="sxs-lookup"><span data-stu-id="5b082-126">True if the object was deleted.</span></span>  <br/> |
|<span data-ttu-id="5b082-127">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="5b082-127">lastUpdated</span></span>  <br/> |<span data-ttu-id="5b082-128">DateTime, не может быть null</span><span class="sxs-lookup"><span data-stu-id="5b082-128">datetime, not null</span></span>  <br/> |<span data-ttu-id="5b082-129">Когда строка была вставлена метка времени.</span><span class="sxs-lookup"><span data-stu-id="5b082-129">Time stamp of when the row was inserted.</span></span>  <br/> |
   

