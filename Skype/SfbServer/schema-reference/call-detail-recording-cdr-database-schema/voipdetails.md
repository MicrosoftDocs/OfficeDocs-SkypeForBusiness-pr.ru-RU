---
title: Представление VoIPDetails
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
ms.assetid: 14c44736-71ba-4fc5-82c7-1df65bf6261c
description: В представлении VoIPDetails хранится информация об одноранговых сеансах, где по крайней мере один пользователь является пользователем VoIP. Это представление впервые было введено в Microsoft Lync Server 2013.
ms.openlocfilehash: b42fecc7a0f43f86dba2439a373c7013c605a5e0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813079"
---
# <a name="voipdetails-view"></a><span data-ttu-id="a73a2-104">Представление VoIPDetails</span><span class="sxs-lookup"><span data-stu-id="a73a2-104">VoIPDetails view</span></span>
 
<span data-ttu-id="a73a2-105">В представлении VoIPDetails хранится информация об одноранговых сеансах, где по крайней мере один пользователь является пользователем VoIP.</span><span class="sxs-lookup"><span data-stu-id="a73a2-105">The VoIPDetails view stores information about peer-to-peer sessions, where at least one user is a VoIP user.</span></span> <span data-ttu-id="a73a2-106">Это представление впервые было введено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a73a2-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a73a2-107">Представление VoIPDetails содержит все столбцы в представлении [SessionDetails,](sessiondetails-0.md) а также столбцы, перечисленные ниже.</span><span class="sxs-lookup"><span data-stu-id="a73a2-107">The VoIPDetails view contains all of the columns in the [SessionDetails view](sessiondetails-0.md) in addition the columns listed below.</span></span>
  
|<span data-ttu-id="a73a2-108">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="a73a2-108">**Column**</span></span>|<span data-ttu-id="a73a2-109">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="a73a2-109">**Data Type**</span></span>|<span data-ttu-id="a73a2-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="a73a2-110">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a73a2-111">**FromPhone**</span><span class="sxs-lookup"><span data-stu-id="a73a2-111">**FromPhone**</span></span> <br/> |<span data-ttu-id="a73a2-112">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="a73a2-112">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="a73a2-113">URI телефона пользователя, занявшего сеанс.</span><span class="sxs-lookup"><span data-stu-id="a73a2-113">Phone URI of the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="a73a2-114">**ToPhone**</span><span class="sxs-lookup"><span data-stu-id="a73a2-114">**ToPhone**</span></span> <br/> |<span data-ttu-id="a73a2-115">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="a73a2-115">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="a73a2-116">URI телефона пользователя, который присоединился к сеансу.</span><span class="sxs-lookup"><span data-stu-id="a73a2-116">Phone URI of the user who joined the session.</span></span>  <br/> |
|<span data-ttu-id="a73a2-117">**DisconnectedByUri**</span><span class="sxs-lookup"><span data-stu-id="a73a2-117">**DisconnectedByUri**</span></span> <br/> |<span data-ttu-id="a73a2-118">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="a73a2-118">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="a73a2-119">URI пользователя, отключившего сеанс.</span><span class="sxs-lookup"><span data-stu-id="a73a2-119">URI of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="a73a2-120">**DisconnectedByUriType**</span><span class="sxs-lookup"><span data-stu-id="a73a2-120">**DisconnectedByUriType**</span></span> <br/> |<span data-ttu-id="a73a2-121">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="a73a2-121">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="a73a2-122">Тип URI пользователя, отключившего сеанс.</span><span class="sxs-lookup"><span data-stu-id="a73a2-122">Type of URI of the user who disconnected the session.</span></span> <span data-ttu-id="a73a2-123">Дополнительные сведения см. в таблице [UriTypes.](uritypes.md)</span><span class="sxs-lookup"><span data-stu-id="a73a2-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
|<span data-ttu-id="a73a2-124">**DisconnectedByTenant**</span><span class="sxs-lookup"><span data-stu-id="a73a2-124">**DisconnectedByTenant**</span></span> <br/> |<span data-ttu-id="a73a2-125">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="a73a2-125">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="a73a2-126">Клиент пользователя, отключившего сеанс.</span><span class="sxs-lookup"><span data-stu-id="a73a2-126">Tenant of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="a73a2-127">**DisconnectedByPhone**</span><span class="sxs-lookup"><span data-stu-id="a73a2-127">**DisconnectedByPhone**</span></span> <br/> |<span data-ttu-id="a73a2-128">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="a73a2-128">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="a73a2-129">URI телефона пользователя, отключившего сеанс.</span><span class="sxs-lookup"><span data-stu-id="a73a2-129">Phone URI of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="a73a2-130">**FromMediationServer**</span><span class="sxs-lookup"><span data-stu-id="a73a2-130">**FromMediationServer**</span></span> <br/> |<span data-ttu-id="a73a2-131">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="a73a2-131">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="a73a2-132">Сервер-посредник, используемый пользователем, который запустил сеанс.</span><span class="sxs-lookup"><span data-stu-id="a73a2-132">Mediation Server used by the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="a73a2-133">**ToMediationServer**</span><span class="sxs-lookup"><span data-stu-id="a73a2-133">**ToMediationServer**</span></span> <br/> |<span data-ttu-id="a73a2-134">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="a73a2-134">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="a73a2-135">Сервер-посредник, используемый пользователем, который присоединился к сеансу.</span><span class="sxs-lookup"><span data-stu-id="a73a2-135">Mediation Server used by the user who joined the session.</span></span>  <br/> |
|<span data-ttu-id="a73a2-136">**FromGateway**</span><span class="sxs-lookup"><span data-stu-id="a73a2-136">**FromGateway**</span></span> <br/> |<span data-ttu-id="a73a2-137">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="a73a2-137">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="a73a2-138">Шлюз, используемый пользователем, который запустил сеанс.</span><span class="sxs-lookup"><span data-stu-id="a73a2-138">Gateway used by the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="a73a2-139">**ToGateway**</span><span class="sxs-lookup"><span data-stu-id="a73a2-139">**ToGateway**</span></span> <br/> |<span data-ttu-id="a73a2-140">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="a73a2-140">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="a73a2-141">Шлюз, используемый пользователем, который присоединился к сеансу.</span><span class="sxs-lookup"><span data-stu-id="a73a2-141">Gateway used by the user who joined the session.</span></span>  <br/> |
   

