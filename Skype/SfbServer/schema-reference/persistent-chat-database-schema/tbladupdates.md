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
localization_priority: Normal
ms.assetid: ba19fa16-4d2d-4635-ac32-f93e09469546
description: Тбладупдатес содержит изменения доменных служб Active Directory, которые еще не были обработаны с помощью последующих шагов синхронизации Active Directory.
ms.openlocfilehash: 3e7788db170539f888923a4600392e19022bbb0e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295561"
---
# <a name="tbladupdates"></a><span data-ttu-id="279ac-103">tblADUpdates</span><span class="sxs-lookup"><span data-stu-id="279ac-103">tblADUpdates</span></span>
 
<span data-ttu-id="279ac-104">Тбладупдатес содержит изменения доменных служб Active Directory, которые еще не были обработаны с помощью последующих шагов синхронизации Active Directory.</span><span class="sxs-lookup"><span data-stu-id="279ac-104">tblADUpdates contains Active Directory Domain Services changes that have not yet been processed by the later Active Directory Sync steps.</span></span>
  
<span data-ttu-id="279ac-105">**Столбцов**</span><span class="sxs-lookup"><span data-stu-id="279ac-105">**Columns**</span></span>

|<span data-ttu-id="279ac-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="279ac-106">**Column**</span></span>|<span data-ttu-id="279ac-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="279ac-107">**Type**</span></span>|<span data-ttu-id="279ac-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="279ac-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="279ac-109">Прингуид</span><span class="sxs-lookup"><span data-stu-id="279ac-109">prinGuid</span></span>  <br/> |<span data-ttu-id="279ac-110">GUID, а не NULL</span><span class="sxs-lookup"><span data-stu-id="279ac-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="279ac-111">Идентификатор GUID участника измененного объекта.</span><span class="sxs-lookup"><span data-stu-id="279ac-111">Principal GUID of the object that changed.</span></span>  <br/> |
|<span data-ttu-id="279ac-112">Принадпас</span><span class="sxs-lookup"><span data-stu-id="279ac-112">prinADPath</span></span>  <br/> |<span data-ttu-id="279ac-113">nvarchar (384), NOT NULL</span><span class="sxs-lookup"><span data-stu-id="279ac-113">nvarchar (384), not null</span></span>  <br/> |<span data-ttu-id="279ac-114">Отличительное имя объекта.</span><span class="sxs-lookup"><span data-stu-id="279ac-114">Distinguished name of the object.</span></span>  <br/> |
|<span data-ttu-id="279ac-115">Принаттрибутесчанжед</span><span class="sxs-lookup"><span data-stu-id="279ac-115">prinAttributesChanged</span></span>  <br/> |<span data-ttu-id="279ac-116">bit, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="279ac-116">bit, not null</span></span>  <br/> |<span data-ttu-id="279ac-117">Значение true, если по крайней мере один из атрибутов объекта изменился.</span><span class="sxs-lookup"><span data-stu-id="279ac-117">True if at least one attribute of the object changed.</span></span>  <br/> |
|<span data-ttu-id="279ac-118">Принмемберсчанжед</span><span class="sxs-lookup"><span data-stu-id="279ac-118">prinMembersChanged</span></span>  <br/> |<span data-ttu-id="279ac-119">bit, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="279ac-119">bit, not null</span></span>  <br/> |<span data-ttu-id="279ac-120">Значение true, если изменилось членство.</span><span class="sxs-lookup"><span data-stu-id="279ac-120">True if the membership changed.</span></span>  <br/> |
|<span data-ttu-id="279ac-121">Принаффилиатионсчанжед</span><span class="sxs-lookup"><span data-stu-id="279ac-121">prinAffiliationsChanged</span></span>  <br/> |<span data-ttu-id="279ac-122">bit, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="279ac-122">bit, not null</span></span>  <br/> |<span data-ttu-id="279ac-123">Не используется.</span><span class="sxs-lookup"><span data-stu-id="279ac-123">Not used.</span></span>  <br/> |
|<span data-ttu-id="279ac-124">Принделетед</span><span class="sxs-lookup"><span data-stu-id="279ac-124">prinDeleted</span></span>  <br/> |<span data-ttu-id="279ac-125">bit, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="279ac-125">bit, not null</span></span>  <br/> |<span data-ttu-id="279ac-126">Значение true, если объект был удален.</span><span class="sxs-lookup"><span data-stu-id="279ac-126">True if the object was deleted.</span></span>  <br/> |
|<span data-ttu-id="279ac-127">Ластупдатед</span><span class="sxs-lookup"><span data-stu-id="279ac-127">lastUpdated</span></span>  <br/> |<span data-ttu-id="279ac-128">DateTime, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="279ac-128">datetime, not null</span></span>  <br/> |<span data-ttu-id="279ac-129">Метка времени вставки строки.</span><span class="sxs-lookup"><span data-stu-id="279ac-129">Time stamp of when the row was inserted.</span></span>  <br/> |
   

