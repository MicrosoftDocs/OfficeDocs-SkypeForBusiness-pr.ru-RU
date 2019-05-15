---
title: Таблица Conference
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2a2c327c-4719-42dc-a3bb-6dbc0864d9af
description: Таблица Conference представляет собой вспомогательную таблицу. Каждая запись представляет один конференции или сеанса peer-to-peer.
ms.openlocfilehash: 0914e98aed4aea16e5301ccae454e925663454a5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920168"
---
# <a name="conference-table"></a><span data-ttu-id="ecbe1-104">Таблица Conference</span><span class="sxs-lookup"><span data-stu-id="ecbe1-104">Conference table</span></span>
 
<span data-ttu-id="ecbe1-105">Таблица Conference представляет собой вспомогательную таблицу.</span><span class="sxs-lookup"><span data-stu-id="ecbe1-105">The Conference table is a supporting table.</span></span> <span data-ttu-id="ecbe1-106">Каждая запись представляет один конференции или сеанса peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="ecbe1-106">Each record represents one conference or peer-to-peer session.</span></span>
  
|<span data-ttu-id="ecbe1-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="ecbe1-107">**Column**</span></span>|<span data-ttu-id="ecbe1-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="ecbe1-108">**Data Type**</span></span>|<span data-ttu-id="ecbe1-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="ecbe1-109">**Key/Index**</span></span>|<span data-ttu-id="ecbe1-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="ecbe1-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ecbe1-111">**ConferenceKey**</span><span class="sxs-lookup"><span data-stu-id="ecbe1-111">**ConferenceKey**</span></span> <br/> |<span data-ttu-id="ecbe1-112">целое</span><span class="sxs-lookup"><span data-stu-id="ecbe1-112">int</span></span>  <br/> |<span data-ttu-id="ecbe1-113">Primary</span><span class="sxs-lookup"><span data-stu-id="ecbe1-113">Primary</span></span>  <br/> |<span data-ttu-id="ecbe1-114">Уникальный номер, идентифицирующий эту запись конференции.</span><span class="sxs-lookup"><span data-stu-id="ecbe1-114">Unique number identifying this conference record.</span></span>  <br/> |
|<span data-ttu-id="ecbe1-115">**ConfURI**</span><span class="sxs-lookup"><span data-stu-id="ecbe1-115">**ConfURI**</span></span> <br/> |<span data-ttu-id="ecbe1-116">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="ecbe1-116">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="ecbe1-117">Уникальный</span><span class="sxs-lookup"><span data-stu-id="ecbe1-117">unique</span></span>  <br/> |<span data-ttu-id="ecbe1-118">URI конференции, если это конференции или DialogID при этом является peer-to-peer сеанса.</span><span class="sxs-lookup"><span data-stu-id="ecbe1-118">Conference URI if this is a conference, or DialogID if this is a peer-to-peer session.</span></span>  <br/> |
|<span data-ttu-id="ecbe1-119">**Контрольная сумма**</span><span class="sxs-lookup"><span data-stu-id="ecbe1-119">**Checksum**</span></span> <br/> |<span data-ttu-id="ecbe1-120">целое</span><span class="sxs-lookup"><span data-stu-id="ecbe1-120">int</span></span>  <br/> |<span data-ttu-id="ecbe1-121">Индекс</span><span class="sxs-lookup"><span data-stu-id="ecbe1-121">index</span></span>  <br/> |<span data-ttu-id="ecbe1-122">Контрольная сумма URI конференции.</span><span class="sxs-lookup"><span data-stu-id="ecbe1-122">Checksum of the conference URI.</span></span> <span data-ttu-id="ecbe1-123">Этот параметр используется во внутренней сети.</span><span class="sxs-lookup"><span data-stu-id="ecbe1-123">This is used internally.</span></span>  <br/> |
|<span data-ttu-id="ecbe1-124">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="ecbe1-124">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="ecbe1-125">datetime</span><span class="sxs-lookup"><span data-stu-id="ecbe1-125">datetime</span></span>  <br/> ||<span data-ttu-id="ecbe1-126">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="ecbe1-126">For internal use only.</span></span>  <br/> |
   

