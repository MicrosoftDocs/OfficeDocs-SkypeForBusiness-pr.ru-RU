---
title: Таблица VideoClientEvent
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e8ab963b-fe1d-45b3-b9bd-66a5f44c1629
description: 'Каждая запись имеет событие клиента для одной конечной точки во время видеозвонка. Обычно один звонок состоит из двух записей: одного для вызывающего и для вызываемого абонента.'
ms.openlocfilehash: 9acd7277fd6bc32074487be1db9874ef6a5c91aa
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41804997"
---
# <a name="videoclientevent-table"></a><span data-ttu-id="5dda1-104">Таблица VideoClientEvent</span><span class="sxs-lookup"><span data-stu-id="5dda1-104">VideoClientEvent table</span></span>
 
<span data-ttu-id="5dda1-105">Каждая запись имеет событие клиента для одной конечной точки во время видеозвонка.</span><span class="sxs-lookup"><span data-stu-id="5dda1-105">Each record contains client event for one endpoint in a video call.</span></span> <span data-ttu-id="5dda1-106">Обычно один звонок состоит из двух записей: одного для вызывающего и для вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="5dda1-106">Usually, one call has two records, one for caller and one for callee.</span></span>
  
|<span data-ttu-id="5dda1-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="5dda1-107">**Column**</span></span>|<span data-ttu-id="5dda1-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="5dda1-108">**Data Type**</span></span>|<span data-ttu-id="5dda1-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="5dda1-109">**Key/Index**</span></span>|<span data-ttu-id="5dda1-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="5dda1-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="5dda1-111">**конференцедатетиме**</span><span class="sxs-lookup"><span data-stu-id="5dda1-111">**ConferenceDateTime**</span></span> <br/> |<span data-ttu-id="5dda1-112">datetime</span><span class="sxs-lookup"><span data-stu-id="5dda1-112">datetime</span></span>  <br/> |<span data-ttu-id="5dda1-113">Primary</span><span class="sxs-lookup"><span data-stu-id="5dda1-113">Primary</span></span>  <br/> |<span data-ttu-id="5dda1-114">На которую ссылается [Таблица медиалине](medialine-0.md).</span><span class="sxs-lookup"><span data-stu-id="5dda1-114">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="5dda1-115">**сессионсек**</span><span class="sxs-lookup"><span data-stu-id="5dda1-115">**SessionSeq**</span></span> <br/> |<span data-ttu-id="5dda1-116">целое</span><span class="sxs-lookup"><span data-stu-id="5dda1-116">int</span></span>  <br/> |<span data-ttu-id="5dda1-117">Primary</span><span class="sxs-lookup"><span data-stu-id="5dda1-117">Primary</span></span>  <br/> |<span data-ttu-id="5dda1-118">На которую ссылается [Таблица медиалине](medialine-0.md).</span><span class="sxs-lookup"><span data-stu-id="5dda1-118">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="5dda1-119">**медиалинелабел**</span><span class="sxs-lookup"><span data-stu-id="5dda1-119">**MediaLineLabel**</span></span> <br/> |<span data-ttu-id="5dda1-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="5dda1-120">tinyint</span></span>  <br/> |<span data-ttu-id="5dda1-121">Primary</span><span class="sxs-lookup"><span data-stu-id="5dda1-121">Primary</span></span>  <br/> |<span data-ttu-id="5dda1-122">На которую ссылается [Таблица медиалине](medialine-0.md).</span><span class="sxs-lookup"><span data-stu-id="5dda1-122">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="5dda1-123">**фромкаллер**</span><span class="sxs-lookup"><span data-stu-id="5dda1-123">**FromCaller**</span></span> <br/> |<span data-ttu-id="5dda1-124">бит</span><span class="sxs-lookup"><span data-stu-id="5dda1-124">bit</span></span>  <br/> |<span data-ttu-id="5dda1-125">Primary</span><span class="sxs-lookup"><span data-stu-id="5dda1-125">Primary</span></span>  <br/> |<span data-ttu-id="5dda1-126">0: данные вызывающего абонента</span><span class="sxs-lookup"><span data-stu-id="5dda1-126">0: Callee's data</span></span>  <br/> <span data-ttu-id="5dda1-127">1: данные вызывающего абонента</span><span class="sxs-lookup"><span data-stu-id="5dda1-127">1: Caller's data</span></span>  <br/> |
|<span data-ttu-id="5dda1-128">**нетворкбандвидсловевентратио**</span><span class="sxs-lookup"><span data-stu-id="5dda1-128">**NetworkBandwidthLowEventRatio**</span></span> <br/> || <br/> |<span data-ttu-id="5dda1-129">Процент сеанса, когда событие Ловбандвидс было инициировано для состояния "Bad".</span><span class="sxs-lookup"><span data-stu-id="5dda1-129">Percentage of session the LowBandwidth event was fired for 'Bad' state.</span></span> <span data-ttu-id="5dda1-130">Доступная пропускная способность недостаточна для приемлемого голосового интерфейса.</span><span class="sxs-lookup"><span data-stu-id="5dda1-130">The available bandwidth is insufficient for an acceptable voice experience.</span></span>  <br/> |
|<span data-ttu-id="5dda1-131">**нетворкрецеивекуалитевентратио**</span><span class="sxs-lookup"><span data-stu-id="5dda1-131">**NetworkReceiveQualityEventRatio**</span></span> <br/> || <br/> |<span data-ttu-id="5dda1-132">Процент сеанса, когда событие Рецеивесендкуалити было инициировано для состояния "Bad".</span><span class="sxs-lookup"><span data-stu-id="5dda1-132">Percentage of session the ReceiveSendQuality event was fired for 'Bad' state.</span></span>  <br/> <span data-ttu-id="5dda1-133">Качество сети в условиях нарушения или потери пакетов является существенным и влияет на качество получаемого звука.</span><span class="sxs-lookup"><span data-stu-id="5dda1-133">Network quality in terms of jitter or packet loss is severe and impacts the quality of audio being received.</span></span>  <br/> |
   

