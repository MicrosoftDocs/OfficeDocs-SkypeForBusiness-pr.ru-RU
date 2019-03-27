---
title: Таблица VideoClientEvent
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8ab963b-fe1d-45b3-b9bd-66a5f44c1629
description: Каждая запись содержит события клиента для одной конечной точки в видеозвонок. Как правило один вызов имеет две записи, одно для вызывающего абонента, а другое для вызываемого абонента.
ms.openlocfilehash: 314e4df9313a3d111d71b6eaa06565edcbb765d1
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30891241"
---
# <a name="videoclientevent-table"></a><span data-ttu-id="fd224-104">Таблица VideoClientEvent</span><span class="sxs-lookup"><span data-stu-id="fd224-104">VideoClientEvent table</span></span>
 
<span data-ttu-id="fd224-105">Каждая запись содержит события клиента для одной конечной точки в видеозвонок.</span><span class="sxs-lookup"><span data-stu-id="fd224-105">Each record contains client event for one endpoint in a video call.</span></span> <span data-ttu-id="fd224-106">Как правило один вызов имеет две записи, одно для вызывающего абонента, а другое для вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="fd224-106">Usually, one call has two records, one for caller and one for callee.</span></span>
  
|<span data-ttu-id="fd224-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="fd224-107">**Column**</span></span>|<span data-ttu-id="fd224-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="fd224-108">**Data Type**</span></span>|<span data-ttu-id="fd224-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="fd224-109">**Key/Index**</span></span>|<span data-ttu-id="fd224-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="fd224-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="fd224-111">**ConferenceDateTime**</span><span class="sxs-lookup"><span data-stu-id="fd224-111">**ConferenceDateTime**</span></span> <br/> |<span data-ttu-id="fd224-112">datetime</span><span class="sxs-lookup"><span data-stu-id="fd224-112">datetime</span></span>  <br/> |<span data-ttu-id="fd224-113">Primary</span><span class="sxs-lookup"><span data-stu-id="fd224-113">Primary</span></span>  <br/> |<span data-ttu-id="fd224-114">Ссылка из [MediaLine table](medialine-0.md).</span><span class="sxs-lookup"><span data-stu-id="fd224-114">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="fd224-115">**SessionSeq**</span><span class="sxs-lookup"><span data-stu-id="fd224-115">**SessionSeq**</span></span> <br/> |<span data-ttu-id="fd224-116">целое</span><span class="sxs-lookup"><span data-stu-id="fd224-116">int</span></span>  <br/> |<span data-ttu-id="fd224-117">Primary</span><span class="sxs-lookup"><span data-stu-id="fd224-117">Primary</span></span>  <br/> |<span data-ttu-id="fd224-118">Ссылка из [MediaLine table](medialine-0.md).</span><span class="sxs-lookup"><span data-stu-id="fd224-118">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="fd224-119">**MediaLineLabel**</span><span class="sxs-lookup"><span data-stu-id="fd224-119">**MediaLineLabel**</span></span> <br/> |<span data-ttu-id="fd224-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="fd224-120">tinyint</span></span>  <br/> |<span data-ttu-id="fd224-121">Primary</span><span class="sxs-lookup"><span data-stu-id="fd224-121">Primary</span></span>  <br/> |<span data-ttu-id="fd224-122">Ссылка из [MediaLine table](medialine-0.md).</span><span class="sxs-lookup"><span data-stu-id="fd224-122">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="fd224-123">**FromCaller**</span><span class="sxs-lookup"><span data-stu-id="fd224-123">**FromCaller**</span></span> <br/> |<span data-ttu-id="fd224-124">бит</span><span class="sxs-lookup"><span data-stu-id="fd224-124">bit</span></span>  <br/> |<span data-ttu-id="fd224-125">Primary</span><span class="sxs-lookup"><span data-stu-id="fd224-125">Primary</span></span>  <br/> |<span data-ttu-id="fd224-126">0: данные вызываемой стороны</span><span class="sxs-lookup"><span data-stu-id="fd224-126">0: Callee's data</span></span>  <br/> <span data-ttu-id="fd224-127">1: данные вызывающего абонента</span><span class="sxs-lookup"><span data-stu-id="fd224-127">1: Caller's data</span></span>  <br/> |
|<span data-ttu-id="fd224-128">**NetworkBandwidthLowEventRatio**</span><span class="sxs-lookup"><span data-stu-id="fd224-128">**NetworkBandwidthLowEventRatio**</span></span> <br/> || <br/> |<span data-ttu-id="fd224-129">Процент в сеансе события LowBandwidth для состояния «Bad».</span><span class="sxs-lookup"><span data-stu-id="fd224-129">Percentage of session the LowBandwidth event was fired for 'Bad' state.</span></span> <span data-ttu-id="fd224-130">Пропускная способность недостаточно для обеспечения взаимодействия приемлемой голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="fd224-130">The available bandwidth is insufficient for an acceptable voice experience.</span></span>  <br/> |
|<span data-ttu-id="fd224-131">**NetworkReceiveQualityEventRatio**</span><span class="sxs-lookup"><span data-stu-id="fd224-131">**NetworkReceiveQualityEventRatio**</span></span> <br/> || <br/> |<span data-ttu-id="fd224-132">Процент в сеансе событие ReceiveSendQuality возникало для состояния «Bad».</span><span class="sxs-lookup"><span data-stu-id="fd224-132">Percentage of session the ReceiveSendQuality event was fired for 'Bad' state.</span></span>  <br/> <span data-ttu-id="fd224-133">Качества сети в терминах дрожания или потери пакетов, что оказывает негативное влияние на качество получаемых аудиоданных.</span><span class="sxs-lookup"><span data-stu-id="fd224-133">Network quality in terms of jitter or packet loss is severe and impacts the quality of audio being received.</span></span>  <br/> |
   

