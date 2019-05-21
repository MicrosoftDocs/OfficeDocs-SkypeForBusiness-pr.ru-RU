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
localization_priority: Normal
ms.assetid: 14c44736-71ba-4fc5-82c7-1df65bf6261c
description: В представлении Воипдетаилс хранятся сведения о одноранговых сеансах, где по крайней мере один пользователь является пользователем VoIP. Это представление было представлено в Microsoft Lync Server 2013.
ms.openlocfilehash: 7f5f1e3cf1540e1a12a9365753e494ff2d8a371e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295666"
---
# <a name="voipdetails-view"></a><span data-ttu-id="ba105-104">Представление Воипдетаилс</span><span class="sxs-lookup"><span data-stu-id="ba105-104">VoIPDetails view</span></span>
 
<span data-ttu-id="ba105-105">В представлении Воипдетаилс хранятся сведения о одноранговых сеансах, где по крайней мере один пользователь является пользователем VoIP.</span><span class="sxs-lookup"><span data-stu-id="ba105-105">The VoIPDetails view stores information about peer-to-peer sessions, where at least one user is a VoIP user.</span></span> <span data-ttu-id="ba105-106">Это представление было представлено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ba105-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ba105-107">В представлении Воипдетаилс содержатся все столбцы в [представлении "сессиондетаилс](sessiondetails-0.md) " в дополнение к столбцам, перечисленным ниже.</span><span class="sxs-lookup"><span data-stu-id="ba105-107">The VoIPDetails view contains all of the columns in the [SessionDetails view](sessiondetails-0.md) in addition the columns listed below.</span></span>
  
|<span data-ttu-id="ba105-108">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="ba105-108">**Column**</span></span>|<span data-ttu-id="ba105-109">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="ba105-109">**Data Type**</span></span>|<span data-ttu-id="ba105-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="ba105-110">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ba105-111">**Фромфоне**</span><span class="sxs-lookup"><span data-stu-id="ba105-111">**FromPhone**</span></span> <br/> |<span data-ttu-id="ba105-112">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="ba105-112">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="ba105-113">URI телефона пользователя, запустившего сеанс.</span><span class="sxs-lookup"><span data-stu-id="ba105-113">Phone URI of the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="ba105-114">**Тофоне**</span><span class="sxs-lookup"><span data-stu-id="ba105-114">**ToPhone**</span></span> <br/> |<span data-ttu-id="ba105-115">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="ba105-115">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="ba105-116">Универсальный код ресурса (URI) пользователя, который присоединился к сеансу.</span><span class="sxs-lookup"><span data-stu-id="ba105-116">Phone URI of the user who joined the session.</span></span>  <br/> |
|<span data-ttu-id="ba105-117">**Дисконнектедбюри**</span><span class="sxs-lookup"><span data-stu-id="ba105-117">**DisconnectedByUri**</span></span> <br/> |<span data-ttu-id="ba105-118">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="ba105-118">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="ba105-119">Универсальный код ресурса (URI) пользователя, который отключил сеанс.</span><span class="sxs-lookup"><span data-stu-id="ba105-119">URI of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="ba105-120">**Дисконнектедбюритипе**</span><span class="sxs-lookup"><span data-stu-id="ba105-120">**DisconnectedByUriType**</span></span> <br/> |<span data-ttu-id="ba105-121">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="ba105-121">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="ba105-122">Тип URI пользователя, который отключил сеанс.</span><span class="sxs-lookup"><span data-stu-id="ba105-122">Type of URI of the user who disconnected the session.</span></span> <span data-ttu-id="ba105-123">Для получения дополнительных сведений ознакомьтесь с [таблицей уритипес](uritypes.md) .</span><span class="sxs-lookup"><span data-stu-id="ba105-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
|<span data-ttu-id="ba105-124">**Дисконнектедбитенант**</span><span class="sxs-lookup"><span data-stu-id="ba105-124">**DisconnectedByTenant**</span></span> <br/> |<span data-ttu-id="ba105-125">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="ba105-125">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="ba105-126">Клиент пользователя, который отключил сеанс.</span><span class="sxs-lookup"><span data-stu-id="ba105-126">Tenant of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="ba105-127">**Дисконнектедбифоне**</span><span class="sxs-lookup"><span data-stu-id="ba105-127">**DisconnectedByPhone**</span></span> <br/> |<span data-ttu-id="ba105-128">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="ba105-128">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="ba105-129">Универсальный код ресурса (URI) пользователя, который отключил сеанс.</span><span class="sxs-lookup"><span data-stu-id="ba105-129">Phone URI of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="ba105-130">**Фроммедиатионсервер**</span><span class="sxs-lookup"><span data-stu-id="ba105-130">**FromMediationServer**</span></span> <br/> |<span data-ttu-id="ba105-131">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="ba105-131">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="ba105-132">Сервер исправлений, используемый пользователем, который запустил сеанс.</span><span class="sxs-lookup"><span data-stu-id="ba105-132">Mediation Server used by the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="ba105-133">**Томедиатионсервер**</span><span class="sxs-lookup"><span data-stu-id="ba105-133">**ToMediationServer**</span></span> <br/> |<span data-ttu-id="ba105-134">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="ba105-134">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="ba105-135">Сервер исправлений, используемый пользователем, который присоединил сеанс.</span><span class="sxs-lookup"><span data-stu-id="ba105-135">Mediation Server used by the user who joined the session.</span></span>  <br/> |
|<span data-ttu-id="ba105-136">**Фромгатевай**</span><span class="sxs-lookup"><span data-stu-id="ba105-136">**FromGateway**</span></span> <br/> |<span data-ttu-id="ba105-137">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="ba105-137">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="ba105-138">Шлюз, используемый пользователем, который запустил сеанс.</span><span class="sxs-lookup"><span data-stu-id="ba105-138">Gateway used by the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="ba105-139">**Тогатевай**</span><span class="sxs-lookup"><span data-stu-id="ba105-139">**ToGateway**</span></span> <br/> |<span data-ttu-id="ba105-140">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="ba105-140">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="ba105-141">Шлюз, используемый пользователем, который присоединился к сеансу.</span><span class="sxs-lookup"><span data-stu-id="ba105-141">Gateway used by the user who joined the session.</span></span>  <br/> |
   

