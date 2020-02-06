---
title: Таблица использованием Traceroute
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
ms.assetid: b9493cef-6ece-4f13-bf68-dbf132aab4f4
description: В таблице использованием Traceroute содержатся сведения о маршрутизации из звонков. Эта таблица введена в Microsoft Lync Server 2013.
ms.openlocfilehash: e257bf6d89d04cd0f4784e62e7ac2876b6ede7e5
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805117"
---
# <a name="traceroute-table"></a><span data-ttu-id="13127-104">Таблица использованием Traceroute</span><span class="sxs-lookup"><span data-stu-id="13127-104">TraceRoute table</span></span>
 
<span data-ttu-id="13127-105">В таблице использованием Traceroute содержатся сведения о маршрутизации из звонков.</span><span class="sxs-lookup"><span data-stu-id="13127-105">The TraceRoute table contains routing information from calls.</span></span> <span data-ttu-id="13127-106">Эта таблица введена в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="13127-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="13127-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="13127-107">**Column**</span></span>|<span data-ttu-id="13127-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="13127-108">**Data Type**</span></span>|<span data-ttu-id="13127-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="13127-109">**Key/Index**</span></span>|<span data-ttu-id="13127-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="13127-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="13127-111">**конференцедатетиме**</span><span class="sxs-lookup"><span data-stu-id="13127-111">**ConferenceDateTime**</span></span> <br/> |<span data-ttu-id="13127-112">datetime</span><span class="sxs-lookup"><span data-stu-id="13127-112">datetime</span></span>  <br/> |<span data-ttu-id="13127-113">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="13127-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="13127-114">Дата и время начала звонка.</span><span class="sxs-lookup"><span data-stu-id="13127-114">Date and time that the call began.</span></span>  <br/> |
|<span data-ttu-id="13127-115">**сессионсек**</span><span class="sxs-lookup"><span data-stu-id="13127-115">**SessionSeq**</span></span> <br/> |<span data-ttu-id="13127-116">целое</span><span class="sxs-lookup"><span data-stu-id="13127-116">int</span></span>  <br/> |<span data-ttu-id="13127-117">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="13127-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="13127-118">Уникальный идентификатор, который используется для различения нескольких звонков, которые могли приступили к одной и той же дате и в то же время.</span><span class="sxs-lookup"><span data-stu-id="13127-118">Unique identifier used to distinguish between multiple calls that might have begun on the same date and at the same time.</span></span>  <br/> |
|<span data-ttu-id="13127-119">**медиалинелабел**</span><span class="sxs-lookup"><span data-stu-id="13127-119">**MediaLineLabel**</span></span> <br/> |<span data-ttu-id="13127-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="13127-120">tinyint</span></span>  <br/> |<span data-ttu-id="13127-121">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="13127-121">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="13127-122">Представляет тип видеостроки, используемой в звонке.</span><span class="sxs-lookup"><span data-stu-id="13127-122">Represents the type of video line used in the call.</span></span> <span data-ttu-id="13127-123">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="13127-123">Allowed values are:</span></span>  <br/> <span data-ttu-id="13127-124">0 – звук</span><span class="sxs-lookup"><span data-stu-id="13127-124">0 - Audio</span></span>  <br/> <span data-ttu-id="13127-125">1-видео</span><span class="sxs-lookup"><span data-stu-id="13127-125">1 - Video</span></span>  <br/> <span data-ttu-id="13127-126">2-панорамное видео</span><span class="sxs-lookup"><span data-stu-id="13127-126">2 - Panoramic video</span></span>  <br/> <span data-ttu-id="13127-127">3 — общий доступ к приложениям и рабочим столам</span><span class="sxs-lookup"><span data-stu-id="13127-127">3 - Application/Desktop sharing</span></span>  <br/> |
|<span data-ttu-id="13127-128">**фромкаллер**</span><span class="sxs-lookup"><span data-stu-id="13127-128">**FromCaller**</span></span> <br/> |<span data-ttu-id="13127-129">бит</span><span class="sxs-lookup"><span data-stu-id="13127-129">bit</span></span>  <br/> |<span data-ttu-id="13127-130">Primary</span><span class="sxs-lookup"><span data-stu-id="13127-130">Primary</span></span>  <br/> |<span data-ttu-id="13127-131">Конечная точка, в которой был помещен звонок.</span><span class="sxs-lookup"><span data-stu-id="13127-131">Endpoint that placed the call.</span></span>  <br/> |
|<span data-ttu-id="13127-132">**Участк**</span><span class="sxs-lookup"><span data-stu-id="13127-132">**Hop**</span></span> <br/> |<span data-ttu-id="13127-133">целое</span><span class="sxs-lookup"><span data-stu-id="13127-133">int</span></span>  <br/> ||<span data-ttu-id="13127-134">Транзитный сетевой переход/</span><span class="sxs-lookup"><span data-stu-id="13127-134">Network hop/</span></span>  <br/> |
|<span data-ttu-id="13127-135">**ипаддресскэй**</span><span class="sxs-lookup"><span data-stu-id="13127-135">**IPAddressKey**</span></span> <br/> |<span data-ttu-id="13127-136">целое</span><span class="sxs-lookup"><span data-stu-id="13127-136">int</span></span>  <br/> |<span data-ttu-id="13127-137">Другом</span><span class="sxs-lookup"><span data-stu-id="13127-137">Foreign</span></span>  <br/> |<span data-ttu-id="13127-138">Уникальный идентификатор IP-адреса.</span><span class="sxs-lookup"><span data-stu-id="13127-138">Unique identifier for the IP address.</span></span> <span data-ttu-id="13127-139">Сведения об IP-адресе хранятся в [таблице IPAddress](ipaddress.md).</span><span class="sxs-lookup"><span data-stu-id="13127-139">IP address information is stored in the [IPAddress table](ipaddress.md).</span></span>  <br/> |
|<span data-ttu-id="13127-140">**ПЕРЕДАЧИ**</span><span class="sxs-lookup"><span data-stu-id="13127-140">**RTT**</span></span> <br/> |<span data-ttu-id="13127-141">целое</span><span class="sxs-lookup"><span data-stu-id="13127-141">int</span></span>  <br/> ||<span data-ttu-id="13127-142">Время обмена данными.</span><span class="sxs-lookup"><span data-stu-id="13127-142">Roundtrip time.</span></span> <span data-ttu-id="13127-143">Время для обмена данными измеряет время, затрачиваемое на передачу голосового пакета получателю, а затем отправляет уведомление о том, что оно получено.</span><span class="sxs-lookup"><span data-stu-id="13127-143">The roundtrip time measures the amount of time it takes for a voice packet to reach its destination and then send back notification that it was received.</span></span>  <br/> |
   

