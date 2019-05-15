---
title: Таблица AppliedBandwidthSource
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 24fb3caf-19b3-4c0a-90d7-ca5d53de32ad
description: Таблица appliedbandwidthsource представляет собой вспомогательную таблицу. Каждая запись представляет один источник.
ms.openlocfilehash: 49e4fd4b2c2543399d073d5d03e8cccad8b0038e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924852"
---
# <a name="appliedbandwidthsource-table"></a><span data-ttu-id="a9e5a-104">Таблица AppliedBandwidthSource</span><span class="sxs-lookup"><span data-stu-id="a9e5a-104">AppliedBandwidthSource table</span></span>
 
<span data-ttu-id="a9e5a-105">Таблица appliedbandwidthsource представляет собой вспомогательную таблицу.</span><span class="sxs-lookup"><span data-stu-id="a9e5a-105">The AppliedBandwidthSource table is a supporting table.</span></span> <span data-ttu-id="a9e5a-106">Каждая запись представляет один источник.</span><span class="sxs-lookup"><span data-stu-id="a9e5a-106">Each record represents one source.</span></span>
  
|<span data-ttu-id="a9e5a-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="a9e5a-107">**Column**</span></span>|<span data-ttu-id="a9e5a-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="a9e5a-108">**Data Type**</span></span>|<span data-ttu-id="a9e5a-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="a9e5a-109">**Key/Index**</span></span>|<span data-ttu-id="a9e5a-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="a9e5a-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a9e5a-111">**AppliedBandwidthSourceKey**</span><span class="sxs-lookup"><span data-stu-id="a9e5a-111">**AppliedBandwidthSourceKey**</span></span> <br/> |<span data-ttu-id="a9e5a-112">целое</span><span class="sxs-lookup"><span data-stu-id="a9e5a-112">int</span></span>  <br/> |<span data-ttu-id="a9e5a-113">Primary</span><span class="sxs-lookup"><span data-stu-id="a9e5a-113">Primary</span></span>  <br/> |<span data-ttu-id="a9e5a-114">Уникальный номер, определяющий источник.</span><span class="sxs-lookup"><span data-stu-id="a9e5a-114">Unique number identifying the source.</span></span>  <br/> |
|<span data-ttu-id="a9e5a-115">**AppliedBandwidthSource**</span><span class="sxs-lookup"><span data-stu-id="a9e5a-115">**AppliedBandwidthSource**</span></span> <br/> |<span data-ttu-id="a9e5a-116">varchar(256)</span><span class="sxs-lookup"><span data-stu-id="a9e5a-116">varchar(256)</span></span>  <br/> |<span data-ttu-id="a9e5a-117">Уникальный</span><span class="sxs-lookup"><span data-stu-id="a9e5a-117">Unique</span></span>  <br/> |<span data-ttu-id="a9e5a-118">Это источник накладываемого ограничение пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="a9e5a-118">This is the source of the bandwidth cap being imposed.</span></span> <span data-ttu-id="a9e5a-119">Этот параметр описывает где готовится к ограничение пропускной способности из (например, «Сервер политики», «ВКЛЮЧИТЬ сервер» или «Модальность»).</span><span class="sxs-lookup"><span data-stu-id="a9e5a-119">It describes where the bandwidth limit is coming from (for example, "Policy Server", "TURN Server", or "Modality").</span></span>  <br/> |
   

