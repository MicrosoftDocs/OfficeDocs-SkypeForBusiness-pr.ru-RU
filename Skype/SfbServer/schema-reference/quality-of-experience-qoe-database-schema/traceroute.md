---
title: Таблица TraceRoute
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
ms.assetid: b9493cef-6ece-4f13-bf68-dbf132aab4f4
description: Таблица TraceRoute содержит сведения о маршрутизации звонков. Эта таблица была представлена в Microsoft Lync Server 2013.
ms.openlocfilehash: 7ecad93cca80a9b7cea73f64158b3c0008a1d6e7
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831329"
---
# <a name="traceroute-table"></a><span data-ttu-id="ad64a-104">Таблица TraceRoute</span><span class="sxs-lookup"><span data-stu-id="ad64a-104">TraceRoute table</span></span>
 
<span data-ttu-id="ad64a-105">Таблица TraceRoute содержит сведения о маршрутизации звонков.</span><span class="sxs-lookup"><span data-stu-id="ad64a-105">The TraceRoute table contains routing information from calls.</span></span> <span data-ttu-id="ad64a-106">Эта таблица была представлена в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ad64a-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="ad64a-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="ad64a-107">**Column**</span></span>|<span data-ttu-id="ad64a-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="ad64a-108">**Data Type**</span></span>|<span data-ttu-id="ad64a-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="ad64a-109">**Key/Index**</span></span>|<span data-ttu-id="ad64a-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="ad64a-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ad64a-111">**ConferenceDateTime**</span><span class="sxs-lookup"><span data-stu-id="ad64a-111">**ConferenceDateTime**</span></span> <br/> |<span data-ttu-id="ad64a-112">datetime</span><span class="sxs-lookup"><span data-stu-id="ad64a-112">datetime</span></span>  <br/> |<span data-ttu-id="ad64a-113">Первичный, внешний</span><span class="sxs-lookup"><span data-stu-id="ad64a-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="ad64a-114">Дата и время начала звонка.</span><span class="sxs-lookup"><span data-stu-id="ad64a-114">Date and time that the call began.</span></span>  <br/> |
|<span data-ttu-id="ad64a-115">**SessionSeq**</span><span class="sxs-lookup"><span data-stu-id="ad64a-115">**SessionSeq**</span></span> <br/> |<span data-ttu-id="ad64a-116">int</span><span class="sxs-lookup"><span data-stu-id="ad64a-116">int</span></span>  <br/> |<span data-ttu-id="ad64a-117">Первичный, внешний</span><span class="sxs-lookup"><span data-stu-id="ad64a-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="ad64a-118">Уникальный идентификатор, используемых для однозначной идентификации звонков, которые могут начаться одновременно.</span><span class="sxs-lookup"><span data-stu-id="ad64a-118">Unique identifier used to distinguish between multiple calls that might have begun on the same date and at the same time.</span></span>  <br/> |
|<span data-ttu-id="ad64a-119">**MediaLineLabel**</span><span class="sxs-lookup"><span data-stu-id="ad64a-119">**MediaLineLabel**</span></span> <br/> |<span data-ttu-id="ad64a-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="ad64a-120">tinyint</span></span>  <br/> |<span data-ttu-id="ad64a-121">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="ad64a-121">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="ad64a-p103">Представляет тип видеоканала, используемого для звонка. Допускаются следующие значения:</span><span class="sxs-lookup"><span data-stu-id="ad64a-p103">Represents the type of video line used in the call. Allowed values are:</span></span>  <br/> <span data-ttu-id="ad64a-124">0 — звук</span><span class="sxs-lookup"><span data-stu-id="ad64a-124">0 - Audio</span></span>  <br/> <span data-ttu-id="ad64a-125">1 — видео</span><span class="sxs-lookup"><span data-stu-id="ad64a-125">1 - Video</span></span>  <br/> <span data-ttu-id="ad64a-126">2 — панорамное видео</span><span class="sxs-lookup"><span data-stu-id="ad64a-126">2 - Panoramic video</span></span>  <br/> <span data-ttu-id="ad64a-127">3 . Общий доступ к приложениям и рабочим столам</span><span class="sxs-lookup"><span data-stu-id="ad64a-127">3 - Application/Desktop sharing</span></span>  <br/> |
|<span data-ttu-id="ad64a-128">**FromCaller**</span><span class="sxs-lookup"><span data-stu-id="ad64a-128">**FromCaller**</span></span> <br/> |<span data-ttu-id="ad64a-129">bit</span><span class="sxs-lookup"><span data-stu-id="ad64a-129">bit</span></span>  <br/> |<span data-ttu-id="ad64a-130">Primary</span><span class="sxs-lookup"><span data-stu-id="ad64a-130">Primary</span></span>  <br/> |<span data-ttu-id="ad64a-131">Конечная точка, выполнившая звонок.</span><span class="sxs-lookup"><span data-stu-id="ad64a-131">Endpoint that placed the call.</span></span>  <br/> |
|<span data-ttu-id="ad64a-132">**Hop**</span><span class="sxs-lookup"><span data-stu-id="ad64a-132">**Hop**</span></span> <br/> |<span data-ttu-id="ad64a-133">int</span><span class="sxs-lookup"><span data-stu-id="ad64a-133">int</span></span>  <br/> ||<span data-ttu-id="ad64a-134">Переход между сетями.</span><span class="sxs-lookup"><span data-stu-id="ad64a-134">Network hop/</span></span>  <br/> |
|<span data-ttu-id="ad64a-135">**IPAddressKey**</span><span class="sxs-lookup"><span data-stu-id="ad64a-135">**IPAddressKey**</span></span> <br/> |<span data-ttu-id="ad64a-136">int</span><span class="sxs-lookup"><span data-stu-id="ad64a-136">int</span></span>  <br/> |<span data-ttu-id="ad64a-137">Внешняя</span><span class="sxs-lookup"><span data-stu-id="ad64a-137">Foreign</span></span>  <br/> |<span data-ttu-id="ad64a-138">Уникальный идентификатор IP-адреса.</span><span class="sxs-lookup"><span data-stu-id="ad64a-138">Unique identifier for the IP address.</span></span> <span data-ttu-id="ad64a-139">Сведения об IP-адресах хранятся в [таблице IPAddress.](ipaddress.md)</span><span class="sxs-lookup"><span data-stu-id="ad64a-139">IP address information is stored in the [IPAddress table](ipaddress.md).</span></span>  <br/> |
|<span data-ttu-id="ad64a-140">**RTT**</span><span class="sxs-lookup"><span data-stu-id="ad64a-140">**RTT**</span></span> <br/> |<span data-ttu-id="ad64a-141">int</span><span class="sxs-lookup"><span data-stu-id="ad64a-141">int</span></span>  <br/> ||<span data-ttu-id="ad64a-p105">Время цикла. Это время, которое требуется на то, чтобы пакет с голосовыми данными достиг назначения и отправил обратно уведомление о том, что он был получен.</span><span class="sxs-lookup"><span data-stu-id="ad64a-p105">Roundtrip time. The roundtrip time measures the amount of time it takes for a voice packet to reach its destination and then send back notification that it was received.</span></span>  <br/> |
   

