---
title: Представление Воипдетаилс
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
ms.assetid: 14c44736-71ba-4fc5-82c7-1df65bf6261c
description: В представлении Воипдетаилс хранятся сведения о одноранговых сеансах, где по крайней мере один пользователь является пользователем VoIP. Это представление было представлено в Microsoft Lync Server 2013.
ms.openlocfilehash: 4d3aec4c58c2cb11f21ec6403f7532bcde46b05e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814777"
---
# <a name="voipdetails-view"></a><span data-ttu-id="d81cf-104">Представление Воипдетаилс</span><span class="sxs-lookup"><span data-stu-id="d81cf-104">VoIPDetails view</span></span>
 
<span data-ttu-id="d81cf-105">В представлении Воипдетаилс хранятся сведения о одноранговых сеансах, где по крайней мере один пользователь является пользователем VoIP.</span><span class="sxs-lookup"><span data-stu-id="d81cf-105">The VoIPDetails view stores information about peer-to-peer sessions, where at least one user is a VoIP user.</span></span> <span data-ttu-id="d81cf-106">Это представление было представлено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d81cf-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d81cf-107">В представлении Воипдетаилс содержатся все столбцы в [представлении "сессиондетаилс](sessiondetails-0.md) " в дополнение к столбцам, перечисленным ниже.</span><span class="sxs-lookup"><span data-stu-id="d81cf-107">The VoIPDetails view contains all of the columns in the [SessionDetails view](sessiondetails-0.md) in addition the columns listed below.</span></span>
  
|<span data-ttu-id="d81cf-108">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="d81cf-108">**Column**</span></span>|<span data-ttu-id="d81cf-109">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="d81cf-109">**Data Type**</span></span>|<span data-ttu-id="d81cf-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="d81cf-110">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d81cf-111">**фромфоне**</span><span class="sxs-lookup"><span data-stu-id="d81cf-111">**FromPhone**</span></span> <br/> |<span data-ttu-id="d81cf-112">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="d81cf-112">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="d81cf-113">URI телефона пользователя, запустившего сеанс.</span><span class="sxs-lookup"><span data-stu-id="d81cf-113">Phone URI of the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="d81cf-114">**тофоне**</span><span class="sxs-lookup"><span data-stu-id="d81cf-114">**ToPhone**</span></span> <br/> |<span data-ttu-id="d81cf-115">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="d81cf-115">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="d81cf-116">Универсальный код ресурса (URI) пользователя, который присоединился к сеансу.</span><span class="sxs-lookup"><span data-stu-id="d81cf-116">Phone URI of the user who joined the session.</span></span>  <br/> |
|<span data-ttu-id="d81cf-117">**дисконнектедбюри**</span><span class="sxs-lookup"><span data-stu-id="d81cf-117">**DisconnectedByUri**</span></span> <br/> |<span data-ttu-id="d81cf-118">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="d81cf-118">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="d81cf-119">Универсальный код ресурса (URI) пользователя, который отключил сеанс.</span><span class="sxs-lookup"><span data-stu-id="d81cf-119">URI of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="d81cf-120">**дисконнектедбюритипе**</span><span class="sxs-lookup"><span data-stu-id="d81cf-120">**DisconnectedByUriType**</span></span> <br/> |<span data-ttu-id="d81cf-121">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="d81cf-121">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="d81cf-122">Тип URI пользователя, который отключил сеанс.</span><span class="sxs-lookup"><span data-stu-id="d81cf-122">Type of URI of the user who disconnected the session.</span></span> <span data-ttu-id="d81cf-123">Для получения дополнительных сведений ознакомьтесь с [таблицей уритипес](uritypes.md) .</span><span class="sxs-lookup"><span data-stu-id="d81cf-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
|<span data-ttu-id="d81cf-124">**дисконнектедбитенант**</span><span class="sxs-lookup"><span data-stu-id="d81cf-124">**DisconnectedByTenant**</span></span> <br/> |<span data-ttu-id="d81cf-125">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="d81cf-125">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="d81cf-126">Клиент пользователя, который отключил сеанс.</span><span class="sxs-lookup"><span data-stu-id="d81cf-126">Tenant of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="d81cf-127">**дисконнектедбифоне**</span><span class="sxs-lookup"><span data-stu-id="d81cf-127">**DisconnectedByPhone**</span></span> <br/> |<span data-ttu-id="d81cf-128">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="d81cf-128">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="d81cf-129">Универсальный код ресурса (URI) пользователя, который отключил сеанс.</span><span class="sxs-lookup"><span data-stu-id="d81cf-129">Phone URI of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="d81cf-130">**фроммедиатионсервер**</span><span class="sxs-lookup"><span data-stu-id="d81cf-130">**FromMediationServer**</span></span> <br/> |<span data-ttu-id="d81cf-131">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="d81cf-131">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="d81cf-132">Сервер исправлений, используемый пользователем, который запустил сеанс.</span><span class="sxs-lookup"><span data-stu-id="d81cf-132">Mediation Server used by the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="d81cf-133">**томедиатионсервер**</span><span class="sxs-lookup"><span data-stu-id="d81cf-133">**ToMediationServer**</span></span> <br/> |<span data-ttu-id="d81cf-134">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="d81cf-134">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="d81cf-135">Сервер исправлений, используемый пользователем, который присоединил сеанс.</span><span class="sxs-lookup"><span data-stu-id="d81cf-135">Mediation Server used by the user who joined the session.</span></span>  <br/> |
|<span data-ttu-id="d81cf-136">**фромгатевай**</span><span class="sxs-lookup"><span data-stu-id="d81cf-136">**FromGateway**</span></span> <br/> |<span data-ttu-id="d81cf-137">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="d81cf-137">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="d81cf-138">Шлюз, используемый пользователем, который запустил сеанс.</span><span class="sxs-lookup"><span data-stu-id="d81cf-138">Gateway used by the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="d81cf-139">**тогатевай**</span><span class="sxs-lookup"><span data-stu-id="d81cf-139">**ToGateway**</span></span> <br/> |<span data-ttu-id="d81cf-140">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="d81cf-140">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="d81cf-141">Шлюз, используемый пользователем, который присоединился к сеансу.</span><span class="sxs-lookup"><span data-stu-id="d81cf-141">Gateway used by the user who joined the session.</span></span>  <br/> |
   

