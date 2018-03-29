---
title: Таблица VideoClientEvent
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
ms.openlocfilehash: b0c73cb3bc07a3e258f66555993698c21a978250
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="videoclientevent-table"></a><span data-ttu-id="0f56e-104">Таблица VideoClientEvent</span><span class="sxs-lookup"><span data-stu-id="0f56e-104">VideoClientEvent table</span></span>
 
<span data-ttu-id="0f56e-105">Каждая запись содержит события клиента для одной конечной точки в видеозвонок.</span><span class="sxs-lookup"><span data-stu-id="0f56e-105">Each record contains client event for one endpoint in a video call.</span></span> <span data-ttu-id="0f56e-106">Как правило один вызов имеет две записи, одно для вызывающего абонента, а другое для вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="0f56e-106">Usually, one call has two records, one for caller and one for callee.</span></span>
  
|<span data-ttu-id="0f56e-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="0f56e-107">**Column**</span></span>|<span data-ttu-id="0f56e-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="0f56e-108">**Data Type**</span></span>|<span data-ttu-id="0f56e-109">**Ключ или индекс**</span><span class="sxs-lookup"><span data-stu-id="0f56e-109">**Key/Index**</span></span>|<span data-ttu-id="0f56e-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="0f56e-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="0f56e-111">**ConferenceDateTime**</span><span class="sxs-lookup"><span data-stu-id="0f56e-111">**ConferenceDateTime**</span></span> <br/> |<span data-ttu-id="0f56e-112">datetime</span><span class="sxs-lookup"><span data-stu-id="0f56e-112">datetime</span></span>  <br/> |<span data-ttu-id="0f56e-113">Primary</span><span class="sxs-lookup"><span data-stu-id="0f56e-113">Primary</span></span>  <br/> |<span data-ttu-id="0f56e-114">Ссылка из [MediaLine table](medialine-0.md).</span><span class="sxs-lookup"><span data-stu-id="0f56e-114">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="0f56e-115">**SessionSeq**</span><span class="sxs-lookup"><span data-stu-id="0f56e-115">**SessionSeq**</span></span> <br/> |<span data-ttu-id="0f56e-116">целое</span><span class="sxs-lookup"><span data-stu-id="0f56e-116">int</span></span>  <br/> |<span data-ttu-id="0f56e-117">Primary</span><span class="sxs-lookup"><span data-stu-id="0f56e-117">Primary</span></span>  <br/> |<span data-ttu-id="0f56e-118">Ссылка из [MediaLine table](medialine-0.md).</span><span class="sxs-lookup"><span data-stu-id="0f56e-118">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="0f56e-119">**MediaLineLabel**</span><span class="sxs-lookup"><span data-stu-id="0f56e-119">**MediaLineLabel**</span></span> <br/> |<span data-ttu-id="0f56e-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="0f56e-120">tinyint</span></span>  <br/> |<span data-ttu-id="0f56e-121">Primary</span><span class="sxs-lookup"><span data-stu-id="0f56e-121">Primary</span></span>  <br/> |<span data-ttu-id="0f56e-122">Ссылка из [MediaLine table](medialine-0.md).</span><span class="sxs-lookup"><span data-stu-id="0f56e-122">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="0f56e-123">**FromCaller**</span><span class="sxs-lookup"><span data-stu-id="0f56e-123">**FromCaller**</span></span> <br/> |<span data-ttu-id="0f56e-124">бит</span><span class="sxs-lookup"><span data-stu-id="0f56e-124">bit</span></span>  <br/> |<span data-ttu-id="0f56e-125">Primary</span><span class="sxs-lookup"><span data-stu-id="0f56e-125">Primary</span></span>  <br/> |<span data-ttu-id="0f56e-126">0: данные вызываемой стороны</span><span class="sxs-lookup"><span data-stu-id="0f56e-126">0: Callee's data</span></span>  <br/> <span data-ttu-id="0f56e-127">1: данные вызывающего абонента</span><span class="sxs-lookup"><span data-stu-id="0f56e-127">1: Caller's data</span></span>  <br/> |
|<span data-ttu-id="0f56e-128">**NetworkBandwidthLowEventRatio**</span><span class="sxs-lookup"><span data-stu-id="0f56e-128">**NetworkBandwidthLowEventRatio**</span></span> <br/> || <br/> |<span data-ttu-id="0f56e-129">Процент в сеансе события LowBandwidth для состояния «Bad».</span><span class="sxs-lookup"><span data-stu-id="0f56e-129">Percentage of session the LowBandwidth event was fired for 'Bad' state.</span></span> <span data-ttu-id="0f56e-130">Пропускная способность недостаточно для обеспечения взаимодействия приемлемой голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="0f56e-130">The available bandwidth is insufficient for an acceptable voice experience.</span></span>  <br/> |
|<span data-ttu-id="0f56e-131">**NetworkReceiveQualityEventRatio**</span><span class="sxs-lookup"><span data-stu-id="0f56e-131">**NetworkReceiveQualityEventRatio**</span></span> <br/> || <br/> |<span data-ttu-id="0f56e-132">Процент в сеансе событие ReceiveSendQuality возникало для состояния «Bad».</span><span class="sxs-lookup"><span data-stu-id="0f56e-132">Percentage of session the ReceiveSendQuality event was fired for 'Bad' state.</span></span>  <br/> <span data-ttu-id="0f56e-133">Качества сети в терминах дрожания или потери пакетов, что оказывает негативное влияние на качество получаемых аудиоданных.</span><span class="sxs-lookup"><span data-stu-id="0f56e-133">Network quality in terms of jitter or packet loss is severe and impacts the quality of audio being received.</span></span>  <br/> |
   

