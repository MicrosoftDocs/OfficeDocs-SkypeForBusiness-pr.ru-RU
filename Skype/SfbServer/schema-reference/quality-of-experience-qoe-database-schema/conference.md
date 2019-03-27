---
title: Таблица Conference
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2a2c327c-4719-42dc-a3bb-6dbc0864d9af
description: Таблица Conference представляет собой вспомогательную таблицу. Каждая запись представляет один конференции или сеанса peer-to-peer.
ms.openlocfilehash: bae144ff574f19155e11b8a2fbfd3548df356c2a
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874041"
---
# <a name="conference-table"></a><span data-ttu-id="302fc-104">Таблица Conference</span><span class="sxs-lookup"><span data-stu-id="302fc-104">Conference table</span></span>
 
<span data-ttu-id="302fc-105">Таблица Conference представляет собой вспомогательную таблицу.</span><span class="sxs-lookup"><span data-stu-id="302fc-105">The Conference table is a supporting table.</span></span> <span data-ttu-id="302fc-106">Каждая запись представляет один конференции или сеанса peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="302fc-106">Each record represents one conference or peer-to-peer session.</span></span>
  
|<span data-ttu-id="302fc-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="302fc-107">**Column**</span></span>|<span data-ttu-id="302fc-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="302fc-108">**Data Type**</span></span>|<span data-ttu-id="302fc-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="302fc-109">**Key/Index**</span></span>|<span data-ttu-id="302fc-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="302fc-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="302fc-111">**ConferenceKey**</span><span class="sxs-lookup"><span data-stu-id="302fc-111">**ConferenceKey**</span></span> <br/> |<span data-ttu-id="302fc-112">целое</span><span class="sxs-lookup"><span data-stu-id="302fc-112">int</span></span>  <br/> |<span data-ttu-id="302fc-113">Primary</span><span class="sxs-lookup"><span data-stu-id="302fc-113">Primary</span></span>  <br/> |<span data-ttu-id="302fc-114">Уникальный номер, идентифицирующий эту запись конференции.</span><span class="sxs-lookup"><span data-stu-id="302fc-114">Unique number identifying this conference record.</span></span>  <br/> |
|<span data-ttu-id="302fc-115">**ConfURI**</span><span class="sxs-lookup"><span data-stu-id="302fc-115">**ConfURI**</span></span> <br/> |<span data-ttu-id="302fc-116">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="302fc-116">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="302fc-117">Уникальный</span><span class="sxs-lookup"><span data-stu-id="302fc-117">unique</span></span>  <br/> |<span data-ttu-id="302fc-118">URI конференции, если это конференции или DialogID при этом является peer-to-peer сеанса.</span><span class="sxs-lookup"><span data-stu-id="302fc-118">Conference URI if this is a conference, or DialogID if this is a peer-to-peer session.</span></span>  <br/> |
|<span data-ttu-id="302fc-119">**Контрольная сумма**</span><span class="sxs-lookup"><span data-stu-id="302fc-119">**Checksum**</span></span> <br/> |<span data-ttu-id="302fc-120">целое</span><span class="sxs-lookup"><span data-stu-id="302fc-120">int</span></span>  <br/> |<span data-ttu-id="302fc-121">Индекс</span><span class="sxs-lookup"><span data-stu-id="302fc-121">index</span></span>  <br/> |<span data-ttu-id="302fc-122">Контрольная сумма URI конференции.</span><span class="sxs-lookup"><span data-stu-id="302fc-122">Checksum of the conference URI.</span></span> <span data-ttu-id="302fc-123">Этот параметр используется во внутренней сети.</span><span class="sxs-lookup"><span data-stu-id="302fc-123">This is used internally.</span></span>  <br/> |
|<span data-ttu-id="302fc-124">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="302fc-124">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="302fc-125">datetime</span><span class="sxs-lookup"><span data-stu-id="302fc-125">datetime</span></span>  <br/> ||<span data-ttu-id="302fc-126">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="302fc-126">For internal use only.</span></span>  <br/> |
   

