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
localization_priority: Normal
ms.assetid: e8ab963b-fe1d-45b3-b9bd-66a5f44c1629
description: 'Каждая запись имеет событие клиента для одной конечной точки во время видеозвонка. Обычно один звонок состоит из двух записей: одного для вызывающего и для вызываемого абонента.'
ms.openlocfilehash: b8e93206ea30622baa82adcec5ee9a80235521c5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294557"
---
# <a name="videoclientevent-table"></a><span data-ttu-id="0dbc5-104">Таблица VideoClientEvent</span><span class="sxs-lookup"><span data-stu-id="0dbc5-104">VideoClientEvent table</span></span>
 
<span data-ttu-id="0dbc5-105">Каждая запись имеет событие клиента для одной конечной точки во время видеозвонка.</span><span class="sxs-lookup"><span data-stu-id="0dbc5-105">Each record contains client event for one endpoint in a video call.</span></span> <span data-ttu-id="0dbc5-106">Обычно один звонок состоит из двух записей: одного для вызывающего и для вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="0dbc5-106">Usually, one call has two records, one for caller and one for callee.</span></span>
  
|<span data-ttu-id="0dbc5-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="0dbc5-107">**Column**</span></span>|<span data-ttu-id="0dbc5-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="0dbc5-108">**Data Type**</span></span>|<span data-ttu-id="0dbc5-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="0dbc5-109">**Key/Index**</span></span>|<span data-ttu-id="0dbc5-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="0dbc5-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="0dbc5-111">**Конференцедатетиме**</span><span class="sxs-lookup"><span data-stu-id="0dbc5-111">**ConferenceDateTime**</span></span> <br/> |<span data-ttu-id="0dbc5-112">datetime</span><span class="sxs-lookup"><span data-stu-id="0dbc5-112">datetime</span></span>  <br/> |<span data-ttu-id="0dbc5-113">Primary</span><span class="sxs-lookup"><span data-stu-id="0dbc5-113">Primary</span></span>  <br/> |<span data-ttu-id="0dbc5-114">На которую ссылается [Таблица медиалине](medialine-0.md).</span><span class="sxs-lookup"><span data-stu-id="0dbc5-114">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="0dbc5-115">**Сессионсек**</span><span class="sxs-lookup"><span data-stu-id="0dbc5-115">**SessionSeq**</span></span> <br/> |<span data-ttu-id="0dbc5-116">целое</span><span class="sxs-lookup"><span data-stu-id="0dbc5-116">int</span></span>  <br/> |<span data-ttu-id="0dbc5-117">Primary</span><span class="sxs-lookup"><span data-stu-id="0dbc5-117">Primary</span></span>  <br/> |<span data-ttu-id="0dbc5-118">На которую ссылается [Таблица медиалине](medialine-0.md).</span><span class="sxs-lookup"><span data-stu-id="0dbc5-118">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="0dbc5-119">**Медиалинелабел**</span><span class="sxs-lookup"><span data-stu-id="0dbc5-119">**MediaLineLabel**</span></span> <br/> |<span data-ttu-id="0dbc5-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="0dbc5-120">tinyint</span></span>  <br/> |<span data-ttu-id="0dbc5-121">Primary</span><span class="sxs-lookup"><span data-stu-id="0dbc5-121">Primary</span></span>  <br/> |<span data-ttu-id="0dbc5-122">На которую ссылается [Таблица медиалине](medialine-0.md).</span><span class="sxs-lookup"><span data-stu-id="0dbc5-122">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="0dbc5-123">**Фромкаллер**</span><span class="sxs-lookup"><span data-stu-id="0dbc5-123">**FromCaller**</span></span> <br/> |<span data-ttu-id="0dbc5-124">бит</span><span class="sxs-lookup"><span data-stu-id="0dbc5-124">bit</span></span>  <br/> |<span data-ttu-id="0dbc5-125">Primary</span><span class="sxs-lookup"><span data-stu-id="0dbc5-125">Primary</span></span>  <br/> |<span data-ttu-id="0dbc5-126">0: данные вызывающего абонента</span><span class="sxs-lookup"><span data-stu-id="0dbc5-126">0: Callee's data</span></span>  <br/> <span data-ttu-id="0dbc5-127">1: данные вызывающего абонента</span><span class="sxs-lookup"><span data-stu-id="0dbc5-127">1: Caller's data</span></span>  <br/> |
|<span data-ttu-id="0dbc5-128">**Нетворкбандвидсловевентратио**</span><span class="sxs-lookup"><span data-stu-id="0dbc5-128">**NetworkBandwidthLowEventRatio**</span></span> <br/> || <br/> |<span data-ttu-id="0dbc5-129">Процент сеанса, когда событие Ловбандвидс было инициировано для состояния "Bad".</span><span class="sxs-lookup"><span data-stu-id="0dbc5-129">Percentage of session the LowBandwidth event was fired for 'Bad' state.</span></span> <span data-ttu-id="0dbc5-130">Доступная пропускная способность недостаточна для приемлемого голосового интерфейса.</span><span class="sxs-lookup"><span data-stu-id="0dbc5-130">The available bandwidth is insufficient for an acceptable voice experience.</span></span>  <br/> |
|<span data-ttu-id="0dbc5-131">**Нетворкрецеивекуалитевентратио**</span><span class="sxs-lookup"><span data-stu-id="0dbc5-131">**NetworkReceiveQualityEventRatio**</span></span> <br/> || <br/> |<span data-ttu-id="0dbc5-132">Процент сеанса, когда событие Рецеивесендкуалити было инициировано для состояния "Bad".</span><span class="sxs-lookup"><span data-stu-id="0dbc5-132">Percentage of session the ReceiveSendQuality event was fired for 'Bad' state.</span></span>  <br/> <span data-ttu-id="0dbc5-133">Качество сети в условиях нарушения или потери пакетов является существенным и влияет на качество получаемого звука.</span><span class="sxs-lookup"><span data-stu-id="0dbc5-133">Network quality in terms of jitter or packet loss is severe and impacts the quality of audio being received.</span></span>  <br/> |
   

