---
title: Таблица Мультимедиа
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 1e1b427f-59b5-4564-bde5-1002a80439ee
description: Каждая запись представляет один тип мультимедиа, используемый в одноранговом сеансе. Если бы использовалось более одного типа мультимедиа, один сеанс был бы представлен несколькими записями в таблице.
ms.openlocfilehash: ce5b5a2b312307e608367279e4e871ed03063860
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800109"
---
# <a name="media-table"></a><span data-ttu-id="e7ddf-104">Таблица Мультимедиа</span><span class="sxs-lookup"><span data-stu-id="e7ddf-104">Media table</span></span>
 
<span data-ttu-id="e7ddf-p102">Каждая запись представляет один тип мультимедиа, используемый в одноранговом сеансе. Если бы использовалось более одного типа мультимедиа, один сеанс был бы представлен несколькими записями в таблице.</span><span class="sxs-lookup"><span data-stu-id="e7ddf-p102">Each record represents one media type used in a peer-to-peer session. One session would be represented by multiple records in the table, if more than one media type is used.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e7ddf-p103">Таблицу мультимедиа не следует использовать для вычисления длительности мультимедиа для сеанса. Эта таблица содержит сведения об обмене мультимедиа во время сеанса. Обмен мультимедиа осуществляется с помощью запроса INVITE, а время отправки этого  запроса указывается с помощью параметра StartTime. Время отправки запроса необязательно соответствует времени запуска обмена мультимедиа, который начинается только после приема сеанса вызываемым. EndTime обычно обозначает время завершения этого сеанса.</span><span class="sxs-lookup"><span data-stu-id="e7ddf-p103">The Media table should not be used to calculate the media duration for a session. This table contains the signaling details of media exchange in a session. Media exchange is done by the INVITE request, and StartTime indicates the time that the INVITE was sent out. The invite time does not necessarily mean the media start time, because media starts only after the sessionee accepts the session. The EndTime usually means the end time of this session.</span></span> 
  
|<span data-ttu-id="e7ddf-111">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="e7ddf-111">**Column**</span></span>|<span data-ttu-id="e7ddf-112">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="e7ddf-112">**Data Type**</span></span>|<span data-ttu-id="e7ddf-113">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="e7ddf-113">**Key/Index**</span></span>|<span data-ttu-id="e7ddf-114">**Details**</span><span class="sxs-lookup"><span data-stu-id="e7ddf-114">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e7ddf-115">**SessionIdTime**</span><span class="sxs-lookup"><span data-stu-id="e7ddf-115">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="e7ddf-116">datetime</span><span class="sxs-lookup"><span data-stu-id="e7ddf-116">datetime</span></span>  <br/> |<span data-ttu-id="e7ddf-117">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="e7ddf-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="e7ddf-118">Время запроса сеанса.</span><span class="sxs-lookup"><span data-stu-id="e7ddf-118">Time of session request.</span></span> <span data-ttu-id="e7ddf-119">В сочетании с параметром **SessionIdSeq** определяет сеанс уникальным образом.</span><span class="sxs-lookup"><span data-stu-id="e7ddf-119">Used in conjunction with **SessionIdSeq** to uniquely identify a session.</span></span> <span data-ttu-id="e7ddf-120">Дополнительные сведения см. в таблице [Dialogs в Skype для бизнеса Server 2015.](dialogs.md)</span><span class="sxs-lookup"><span data-stu-id="e7ddf-120">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="e7ddf-121">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="e7ddf-121">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="e7ddf-122">int</span><span class="sxs-lookup"><span data-stu-id="e7ddf-122">int</span></span>  <br/> |<span data-ttu-id="e7ddf-123">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="e7ddf-123">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="e7ddf-124">Идентификатор для идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="e7ddf-124">ID number to identify the session.</span></span> <span data-ttu-id="e7ddf-125">В сочетании с параметром **SessionIdTime** определяет сеанс уникальным образом.</span><span class="sxs-lookup"><span data-stu-id="e7ddf-125">Used in conjunction with **SessionIdTime** to uniquely identify a session.</span></span> <span data-ttu-id="e7ddf-126">Дополнительные сведения см. в таблице [Dialogs в Skype для бизнеса Server 2015.](dialogs.md)</span><span class="sxs-lookup"><span data-stu-id="e7ddf-126">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="e7ddf-127">**MediaId**</span><span class="sxs-lookup"><span data-stu-id="e7ddf-127">**MediaId**</span></span> <br/> |<span data-ttu-id="e7ddf-128">tinyint</span><span class="sxs-lookup"><span data-stu-id="e7ddf-128">tinyint</span></span>  <br/> |<span data-ttu-id="e7ddf-129">Первичный, внешний</span><span class="sxs-lookup"><span data-stu-id="e7ddf-129">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="e7ddf-130">Уникальный номер, идентифицирующий этот тип мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="e7ddf-130">Unique number identifying this media type.</span></span> <span data-ttu-id="e7ddf-131">Дополнительные сведения см. в таблице [MediaList.](medialist.md)</span><span class="sxs-lookup"><span data-stu-id="e7ddf-131">See the [MediaList table](medialist.md) for more information.</span></span> <br/> |
|<span data-ttu-id="e7ddf-132">**StartTime**</span><span class="sxs-lookup"><span data-stu-id="e7ddf-132">**StartTime**</span></span> <br/> |<span data-ttu-id="e7ddf-133">datetime</span><span class="sxs-lookup"><span data-stu-id="e7ddf-133">datetime</span></span>  <br/> |<span data-ttu-id="e7ddf-134">Primary</span><span class="sxs-lookup"><span data-stu-id="e7ddf-134">Primary</span></span>  <br/> |<span data-ttu-id="e7ddf-p107">Время отправки запроса мультимедиа, а не фактическое время начала обмена мультимедиа. **StartTime** включает в себя время настройки сеанса.</span><span class="sxs-lookup"><span data-stu-id="e7ddf-p107">This is the time that a media request was sent out, not the real media start time. **StartTime** includes the session setup time. </span></span><br/> |
|<span data-ttu-id="e7ddf-137">**EndTime**</span><span class="sxs-lookup"><span data-stu-id="e7ddf-137">**EndTime**</span></span> <br/> |<span data-ttu-id="e7ddf-138">datetime</span><span class="sxs-lookup"><span data-stu-id="e7ddf-138">datetime</span></span>  <br/> ||<span data-ttu-id="e7ddf-139">Время завершения этого сеанса.</span><span class="sxs-lookup"><span data-stu-id="e7ddf-139">This is the end time of the session.</span></span>  <br/> |
   

