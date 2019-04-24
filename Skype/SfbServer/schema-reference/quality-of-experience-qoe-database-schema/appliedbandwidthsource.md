---
title: Таблица AppliedBandwidthSource
ms.reviewer: ''
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
ms.openlocfilehash: 2fed25b6ca2218cb8b7300507b5c8258b2c29798
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212357"
---
# <a name="appliedbandwidthsource-table"></a><span data-ttu-id="04cf6-104">Таблица AppliedBandwidthSource</span><span class="sxs-lookup"><span data-stu-id="04cf6-104">AppliedBandwidthSource table</span></span>
 
<span data-ttu-id="04cf6-105">Таблица appliedbandwidthsource представляет собой вспомогательную таблицу.</span><span class="sxs-lookup"><span data-stu-id="04cf6-105">The AppliedBandwidthSource table is a supporting table.</span></span> <span data-ttu-id="04cf6-106">Каждая запись представляет один источник.</span><span class="sxs-lookup"><span data-stu-id="04cf6-106">Each record represents one source.</span></span>
  
|<span data-ttu-id="04cf6-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="04cf6-107">**Column**</span></span>|<span data-ttu-id="04cf6-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="04cf6-108">**Data Type**</span></span>|<span data-ttu-id="04cf6-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="04cf6-109">**Key/Index**</span></span>|<span data-ttu-id="04cf6-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="04cf6-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="04cf6-111">**AppliedBandwidthSourceKey**</span><span class="sxs-lookup"><span data-stu-id="04cf6-111">**AppliedBandwidthSourceKey**</span></span> <br/> |<span data-ttu-id="04cf6-112">целое</span><span class="sxs-lookup"><span data-stu-id="04cf6-112">int</span></span>  <br/> |<span data-ttu-id="04cf6-113">Primary</span><span class="sxs-lookup"><span data-stu-id="04cf6-113">Primary</span></span>  <br/> |<span data-ttu-id="04cf6-114">Уникальный номер, определяющий источник.</span><span class="sxs-lookup"><span data-stu-id="04cf6-114">Unique number identifying the source.</span></span>  <br/> |
|<span data-ttu-id="04cf6-115">**AppliedBandwidthSource**</span><span class="sxs-lookup"><span data-stu-id="04cf6-115">**AppliedBandwidthSource**</span></span> <br/> |<span data-ttu-id="04cf6-116">varchar(256)</span><span class="sxs-lookup"><span data-stu-id="04cf6-116">varchar(256)</span></span>  <br/> |<span data-ttu-id="04cf6-117">Уникальный</span><span class="sxs-lookup"><span data-stu-id="04cf6-117">Unique</span></span>  <br/> |<span data-ttu-id="04cf6-118">Это источник накладываемого ограничение пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="04cf6-118">This is the source of the bandwidth cap being imposed.</span></span> <span data-ttu-id="04cf6-119">Этот параметр описывает где готовится к ограничение пропускной способности из (например, «Сервер политики», «ВКЛЮЧИТЬ сервер» или «Модальность»).</span><span class="sxs-lookup"><span data-stu-id="04cf6-119">It describes where the bandwidth limit is coming from (for example, "Policy Server", "TURN Server", or "Modality").</span></span>  <br/> |
   

