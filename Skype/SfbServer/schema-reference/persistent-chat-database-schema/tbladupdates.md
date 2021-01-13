---
title: tblADUpdates
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ba19fa16-4d2d-4635-ac32-f93e09469546
description: tblADUpdates содержит изменения доменных служб Active Directory, которые еще не были обработаны в последующих шагах синхронизации Active Directory.
ms.openlocfilehash: 16bb393eb57e7aaf8d3fea7001157eaabbe70c52
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821389"
---
# <a name="tbladupdates"></a><span data-ttu-id="488e6-103">tblADUpdates</span><span class="sxs-lookup"><span data-stu-id="488e6-103">tblADUpdates</span></span>
 
<span data-ttu-id="488e6-104">tblADUpdates содержит изменения доменных служб Active Directory, которые еще не были обработаны в последующих шагах синхронизации Active Directory.</span><span class="sxs-lookup"><span data-stu-id="488e6-104">tblADUpdates contains Active Directory Domain Services changes that have not yet been processed by the later Active Directory Sync steps.</span></span>
  
<span data-ttu-id="488e6-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="488e6-105">**Columns**</span></span>

|<span data-ttu-id="488e6-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="488e6-106">**Column**</span></span>|<span data-ttu-id="488e6-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="488e6-107">**Type**</span></span>|<span data-ttu-id="488e6-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="488e6-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="488e6-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="488e6-109">prinGuid</span></span>  <br/> |<span data-ttu-id="488e6-110">GUID, not null</span><span class="sxs-lookup"><span data-stu-id="488e6-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="488e6-111">Глобальный уникальный ИД измененного объекта.</span><span class="sxs-lookup"><span data-stu-id="488e6-111">Principal GUID of the object that changed.</span></span>  <br/> |
|<span data-ttu-id="488e6-112">prinADPath</span><span class="sxs-lookup"><span data-stu-id="488e6-112">prinADPath</span></span>  <br/> |<span data-ttu-id="488e6-113">nvarchar (384), not null</span><span class="sxs-lookup"><span data-stu-id="488e6-113">nvarchar (384), not null</span></span>  <br/> |<span data-ttu-id="488e6-114">Различающееся имя объекта.</span><span class="sxs-lookup"><span data-stu-id="488e6-114">Distinguished name of the object.</span></span>  <br/> |
|<span data-ttu-id="488e6-115">prinAttributesChanged</span><span class="sxs-lookup"><span data-stu-id="488e6-115">prinAttributesChanged</span></span>  <br/> |<span data-ttu-id="488e6-116">bit, not null</span><span class="sxs-lookup"><span data-stu-id="488e6-116">bit, not null</span></span>  <br/> |<span data-ttu-id="488e6-117">TRUE, если изменился хотя бы один атрибут объекта.</span><span class="sxs-lookup"><span data-stu-id="488e6-117">True if at least one attribute of the object changed.</span></span>  <br/> |
|<span data-ttu-id="488e6-118">prinMembersChanged</span><span class="sxs-lookup"><span data-stu-id="488e6-118">prinMembersChanged</span></span>  <br/> |<span data-ttu-id="488e6-119">bit, not null</span><span class="sxs-lookup"><span data-stu-id="488e6-119">bit, not null</span></span>  <br/> |<span data-ttu-id="488e6-120">TRUE, если изменилось членство.</span><span class="sxs-lookup"><span data-stu-id="488e6-120">True if the membership changed.</span></span>  <br/> |
|<span data-ttu-id="488e6-121">prinAffiliationsChanged</span><span class="sxs-lookup"><span data-stu-id="488e6-121">prinAffiliationsChanged</span></span>  <br/> |<span data-ttu-id="488e6-122">bit, not null</span><span class="sxs-lookup"><span data-stu-id="488e6-122">bit, not null</span></span>  <br/> |<span data-ttu-id="488e6-123">Не используется.</span><span class="sxs-lookup"><span data-stu-id="488e6-123">Not used.</span></span>  <br/> |
|<span data-ttu-id="488e6-124">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="488e6-124">prinDeleted</span></span>  <br/> |<span data-ttu-id="488e6-125">bit, not null</span><span class="sxs-lookup"><span data-stu-id="488e6-125">bit, not null</span></span>  <br/> |<span data-ttu-id="488e6-126">TRUE, если объект был удален.</span><span class="sxs-lookup"><span data-stu-id="488e6-126">True if the object was deleted.</span></span>  <br/> |
|<span data-ttu-id="488e6-127">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="488e6-127">lastUpdated</span></span>  <br/> |<span data-ttu-id="488e6-128">datetime, not null</span><span class="sxs-lookup"><span data-stu-id="488e6-128">datetime, not null</span></span>  <br/> |<span data-ttu-id="488e6-129">Метка времени добавления строки.</span><span class="sxs-lookup"><span data-stu-id="488e6-129">Time stamp of when the row was inserted.</span></span>  <br/> |
   

