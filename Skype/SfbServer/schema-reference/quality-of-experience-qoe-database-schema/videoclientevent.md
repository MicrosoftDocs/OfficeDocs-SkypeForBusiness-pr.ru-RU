---
title: Таблица VideoClientEvent
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e8ab963b-fe1d-45b3-b9bd-66a5f44c1629
description: 'Каждая запись содержит событие клиента для одной конечной точки в видеосвязи. Обычно один вызов имеет две записи: одну для вызываемой стороны и одну для вызываемой.'
ms.openlocfilehash: bb4a9feca562bed7bdb0080e7f9181003952f5d4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821399"
---
# <a name="videoclientevent-table"></a><span data-ttu-id="d919c-104">Таблица VideoClientEvent</span><span class="sxs-lookup"><span data-stu-id="d919c-104">VideoClientEvent table</span></span>
 
<span data-ttu-id="d919c-105">Каждая запись содержит событие клиента для одной конечной точки в видеосвязи.</span><span class="sxs-lookup"><span data-stu-id="d919c-105">Each record contains client event for one endpoint in a video call.</span></span> <span data-ttu-id="d919c-106">Обычно один вызов имеет две записи: одну для вызываемой стороны и одну для вызываемой.</span><span class="sxs-lookup"><span data-stu-id="d919c-106">Usually, one call has two records, one for caller and one for callee.</span></span>
  
|<span data-ttu-id="d919c-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="d919c-107">**Column**</span></span>|<span data-ttu-id="d919c-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="d919c-108">**Data Type**</span></span>|<span data-ttu-id="d919c-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="d919c-109">**Key/Index**</span></span>|<span data-ttu-id="d919c-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="d919c-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d919c-111">**ConferenceDateTime**</span><span class="sxs-lookup"><span data-stu-id="d919c-111">**ConferenceDateTime**</span></span> <br/> |<span data-ttu-id="d919c-112">datetime</span><span class="sxs-lookup"><span data-stu-id="d919c-112">datetime</span></span>  <br/> |<span data-ttu-id="d919c-113">Primary</span><span class="sxs-lookup"><span data-stu-id="d919c-113">Primary</span></span>  <br/> |<span data-ttu-id="d919c-114">Ссылка из [таблицы MediaLine.](medialine-0.md)</span><span class="sxs-lookup"><span data-stu-id="d919c-114">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="d919c-115">**SessionSeq**</span><span class="sxs-lookup"><span data-stu-id="d919c-115">**SessionSeq**</span></span> <br/> |<span data-ttu-id="d919c-116">int</span><span class="sxs-lookup"><span data-stu-id="d919c-116">int</span></span>  <br/> |<span data-ttu-id="d919c-117">Primary</span><span class="sxs-lookup"><span data-stu-id="d919c-117">Primary</span></span>  <br/> |<span data-ttu-id="d919c-118">Ссылка из [таблицы MediaLine.](medialine-0.md)</span><span class="sxs-lookup"><span data-stu-id="d919c-118">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="d919c-119">**MediaLineLabel**</span><span class="sxs-lookup"><span data-stu-id="d919c-119">**MediaLineLabel**</span></span> <br/> |<span data-ttu-id="d919c-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="d919c-120">tinyint</span></span>  <br/> |<span data-ttu-id="d919c-121">Primary</span><span class="sxs-lookup"><span data-stu-id="d919c-121">Primary</span></span>  <br/> |<span data-ttu-id="d919c-122">Ссылка из [таблицы MediaLine.](medialine-0.md)</span><span class="sxs-lookup"><span data-stu-id="d919c-122">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="d919c-123">**FromCaller**</span><span class="sxs-lookup"><span data-stu-id="d919c-123">**FromCaller**</span></span> <br/> |<span data-ttu-id="d919c-124">bit</span><span class="sxs-lookup"><span data-stu-id="d919c-124">bit</span></span>  <br/> |<span data-ttu-id="d919c-125">Primary</span><span class="sxs-lookup"><span data-stu-id="d919c-125">Primary</span></span>  <br/> |<span data-ttu-id="d919c-126">0: данные вызываемой</span><span class="sxs-lookup"><span data-stu-id="d919c-126">0: Callee's data</span></span>  <br/> <span data-ttu-id="d919c-127">1: данные вызываемой</span><span class="sxs-lookup"><span data-stu-id="d919c-127">1: Caller's data</span></span>  <br/> |
|<span data-ttu-id="d919c-128">**NetworkBandwidthLowEventRatio**</span><span class="sxs-lookup"><span data-stu-id="d919c-128">**NetworkBandwidthLowEventRatio**</span></span> <br/> || <br/> |<span data-ttu-id="d919c-129">Процент сеанса, когда событие LowBandwidth было и выпущено для состояния "Bad".</span><span class="sxs-lookup"><span data-stu-id="d919c-129">Percentage of session the LowBandwidth event was fired for 'Bad' state.</span></span> <span data-ttu-id="d919c-130">Доступной пропускной способности недостаточно для приемлемого звучания.</span><span class="sxs-lookup"><span data-stu-id="d919c-130">The available bandwidth is insufficient for an acceptable voice experience.</span></span>  <br/> |
|<span data-ttu-id="d919c-131">**NetworkReceiveQualityEventRatio**</span><span class="sxs-lookup"><span data-stu-id="d919c-131">**NetworkReceiveQualityEventRatio**</span></span> <br/> || <br/> |<span data-ttu-id="d919c-132">Процент сеанса, когда событие ReceiveSendQuality было и выпущено для состояния "Bad".</span><span class="sxs-lookup"><span data-stu-id="d919c-132">Percentage of session the ReceiveSendQuality event was fired for 'Bad' state.</span></span>  <br/> <span data-ttu-id="d919c-133">Качество сети в условиях дрожания или потери пакетов является серьезным и влияет на качество звука, который получается.</span><span class="sxs-lookup"><span data-stu-id="d919c-133">Network quality in terms of jitter or packet loss is severe and impacts the quality of audio being received.</span></span>  <br/> |
   

