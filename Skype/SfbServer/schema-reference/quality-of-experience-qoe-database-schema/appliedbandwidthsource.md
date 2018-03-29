---
title: Таблица AppliedBandwidthSource
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 24fb3caf-19b3-4c0a-90d7-ca5d53de32ad
description: Таблица appliedbandwidthsource представляет собой вспомогательную таблицу. Каждая запись представляет один источник.
ms.openlocfilehash: e15df92423a3408e3cb8ae40a0788e1f165961df
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="appliedbandwidthsource-table"></a><span data-ttu-id="327a3-104">Таблица AppliedBandwidthSource</span><span class="sxs-lookup"><span data-stu-id="327a3-104">AppliedBandwidthSource table</span></span>
 
<span data-ttu-id="327a3-105">Таблица appliedbandwidthsource представляет собой вспомогательную таблицу.</span><span class="sxs-lookup"><span data-stu-id="327a3-105">The AppliedBandwidthSource table is a supporting table.</span></span> <span data-ttu-id="327a3-106">Каждая запись представляет один источник.</span><span class="sxs-lookup"><span data-stu-id="327a3-106">Each record represents one source.</span></span>
  
|<span data-ttu-id="327a3-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="327a3-107">**Column**</span></span>|<span data-ttu-id="327a3-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="327a3-108">**Data Type**</span></span>|<span data-ttu-id="327a3-109">**Ключ или индекс**</span><span class="sxs-lookup"><span data-stu-id="327a3-109">**Key/Index**</span></span>|<span data-ttu-id="327a3-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="327a3-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="327a3-111">**AppliedBandwidthSourceKey**</span><span class="sxs-lookup"><span data-stu-id="327a3-111">**AppliedBandwidthSourceKey**</span></span> <br/> |<span data-ttu-id="327a3-112">целое</span><span class="sxs-lookup"><span data-stu-id="327a3-112">int</span></span>  <br/> |<span data-ttu-id="327a3-113">Primary</span><span class="sxs-lookup"><span data-stu-id="327a3-113">Primary</span></span>  <br/> |<span data-ttu-id="327a3-114">Уникальный номер, определяющий источник.</span><span class="sxs-lookup"><span data-stu-id="327a3-114">Unique number identifying the source.</span></span>  <br/> |
|<span data-ttu-id="327a3-115">**AppliedBandwidthSource**</span><span class="sxs-lookup"><span data-stu-id="327a3-115">**AppliedBandwidthSource**</span></span> <br/> |<span data-ttu-id="327a3-116">varchar(256)</span><span class="sxs-lookup"><span data-stu-id="327a3-116">varchar(256)</span></span>  <br/> |<span data-ttu-id="327a3-117">Уникальный</span><span class="sxs-lookup"><span data-stu-id="327a3-117">Unique</span></span>  <br/> |<span data-ttu-id="327a3-118">Это источник накладываемого ограничение пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="327a3-118">This is the source of the bandwidth cap being imposed.</span></span> <span data-ttu-id="327a3-119">Этот параметр описывает где готовится к ограничение пропускной способности из (например, «Сервер политики», «ВКЛЮЧИТЬ сервер» или «Модальность»).</span><span class="sxs-lookup"><span data-stu-id="327a3-119">It describes where the bandwidth limit is coming from (for example, "Policy Server", "TURN Server", or "Modality").</span></span>  <br/> |
   

