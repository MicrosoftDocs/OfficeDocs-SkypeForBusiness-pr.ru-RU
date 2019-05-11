---
title: Представление VoIPDetails
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14c44736-71ba-4fc5-82c7-1df65bf6261c
description: Представление VoIPDetails сохранение информации о сеансах peer-to-peer, где по крайней мере один пользователь является пользователем VoIP. В этом представлении была введена в Microsoft Lync Server 2013.
ms.openlocfilehash: 6fb1dede975e59c0ae56fe9872472310c914f685
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930031"
---
# <a name="voipdetails-view"></a><span data-ttu-id="ffb38-104">Представление VoIPDetails</span><span class="sxs-lookup"><span data-stu-id="ffb38-104">VoIPDetails view</span></span>
 
<span data-ttu-id="ffb38-105">Представление VoIPDetails сохранение информации о сеансах peer-to-peer, где по крайней мере один пользователь является пользователем VoIP.</span><span class="sxs-lookup"><span data-stu-id="ffb38-105">The VoIPDetails view stores information about peer-to-peer sessions, where at least one user is a VoIP user.</span></span> <span data-ttu-id="ffb38-106">В этом представлении была введена в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ffb38-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ffb38-107">Представление VoIPDetails содержит все столбцы [SessionDetails view](sessiondetails-0.md) в дополнение к этому столбцов, перечисленных ниже.</span><span class="sxs-lookup"><span data-stu-id="ffb38-107">The VoIPDetails view contains all of the columns in the [SessionDetails view](sessiondetails-0.md) in addition the columns listed below.</span></span>
  
|<span data-ttu-id="ffb38-108">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="ffb38-108">**Column**</span></span>|<span data-ttu-id="ffb38-109">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="ffb38-109">**Data Type**</span></span>|<span data-ttu-id="ffb38-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="ffb38-110">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ffb38-111">**FromPhone**</span><span class="sxs-lookup"><span data-stu-id="ffb38-111">**FromPhone**</span></span> <br/> |<span data-ttu-id="ffb38-112">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="ffb38-112">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="ffb38-113">URI-адрес пользователя, запустившего сеанс телефона.</span><span class="sxs-lookup"><span data-stu-id="ffb38-113">Phone URI of the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="ffb38-114">**ToPhone**</span><span class="sxs-lookup"><span data-stu-id="ffb38-114">**ToPhone**</span></span> <br/> |<span data-ttu-id="ffb38-115">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="ffb38-115">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="ffb38-116">URI-адрес пользователя, который присоединился к сеансу телефона.</span><span class="sxs-lookup"><span data-stu-id="ffb38-116">Phone URI of the user who joined the session.</span></span>  <br/> |
|<span data-ttu-id="ffb38-117">**DisconnectedByUri**</span><span class="sxs-lookup"><span data-stu-id="ffb38-117">**DisconnectedByUri**</span></span> <br/> |<span data-ttu-id="ffb38-118">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="ffb38-118">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="ffb38-119">URI пользователя, отключившегося от сеанса.</span><span class="sxs-lookup"><span data-stu-id="ffb38-119">URI of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="ffb38-120">**DisconnectedByUriType**</span><span class="sxs-lookup"><span data-stu-id="ffb38-120">**DisconnectedByUriType**</span></span> <br/> |<span data-ttu-id="ffb38-121">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="ffb38-121">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="ffb38-122">Тип URI пользователя, отключившегося от сеанса.</span><span class="sxs-lookup"><span data-stu-id="ffb38-122">Type of URI of the user who disconnected the session.</span></span> <span data-ttu-id="ffb38-123">В [таблице UriTypes](uritypes.md) для получения дополнительных сведений см.</span><span class="sxs-lookup"><span data-stu-id="ffb38-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
|<span data-ttu-id="ffb38-124">**DisconnectedByTenant**</span><span class="sxs-lookup"><span data-stu-id="ffb38-124">**DisconnectedByTenant**</span></span> <br/> |<span data-ttu-id="ffb38-125">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="ffb38-125">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="ffb38-126">Клиент пользователя, отключившегося от сеанса.</span><span class="sxs-lookup"><span data-stu-id="ffb38-126">Tenant of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="ffb38-127">**DisconnectedByPhone**</span><span class="sxs-lookup"><span data-stu-id="ffb38-127">**DisconnectedByPhone**</span></span> <br/> |<span data-ttu-id="ffb38-128">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="ffb38-128">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="ffb38-129">URI-адрес пользователя, отключившегося от сеанса телефона.</span><span class="sxs-lookup"><span data-stu-id="ffb38-129">Phone URI of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="ffb38-130">**FromMediationServer**</span><span class="sxs-lookup"><span data-stu-id="ffb38-130">**FromMediationServer**</span></span> <br/> |<span data-ttu-id="ffb38-131">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="ffb38-131">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="ffb38-132">Сервер-посредник пользователя, запустившего сеанс.</span><span class="sxs-lookup"><span data-stu-id="ffb38-132">Mediation Server used by the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="ffb38-133">**ToMediationServer**</span><span class="sxs-lookup"><span data-stu-id="ffb38-133">**ToMediationServer**</span></span> <br/> |<span data-ttu-id="ffb38-134">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="ffb38-134">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="ffb38-135">Сервер-посредник пользователя, который присоединился к сеансу.</span><span class="sxs-lookup"><span data-stu-id="ffb38-135">Mediation Server used by the user who joined the session.</span></span>  <br/> |
|<span data-ttu-id="ffb38-136">**FromGateway**</span><span class="sxs-lookup"><span data-stu-id="ffb38-136">**FromGateway**</span></span> <br/> |<span data-ttu-id="ffb38-137">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="ffb38-137">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="ffb38-138">Шлюз, используемый пользователем, запустившим сеанс.</span><span class="sxs-lookup"><span data-stu-id="ffb38-138">Gateway used by the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="ffb38-139">**ToGateway**</span><span class="sxs-lookup"><span data-stu-id="ffb38-139">**ToGateway**</span></span> <br/> |<span data-ttu-id="ffb38-140">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="ffb38-140">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="ffb38-141">Шлюз, используемый пользователем, который присоединился к сеансу.</span><span class="sxs-lookup"><span data-stu-id="ffb38-141">Gateway used by the user who joined the session.</span></span>  <br/> |
   

