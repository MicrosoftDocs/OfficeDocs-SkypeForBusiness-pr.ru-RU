---
title: Таблица AppliedBandwidthSource
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
ms.assetid: 24fb3caf-19b3-4c0a-90d7-ca5d53de32ad
description: Таблица Апплиедбандвидссаурце является вспомогательной таблицей. Каждая запись представляет один источник.
ms.openlocfilehash: 875f6d105a2fef0bf710e57ec389bee4f2613c66
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41811447"
---
# <a name="appliedbandwidthsource-table"></a><span data-ttu-id="6eda7-104">Таблица AppliedBandwidthSource</span><span class="sxs-lookup"><span data-stu-id="6eda7-104">AppliedBandwidthSource table</span></span>
 
<span data-ttu-id="6eda7-105">Таблица Апплиедбандвидссаурце является вспомогательной таблицей.</span><span class="sxs-lookup"><span data-stu-id="6eda7-105">The AppliedBandwidthSource table is a supporting table.</span></span> <span data-ttu-id="6eda7-106">Каждая запись представляет один источник.</span><span class="sxs-lookup"><span data-stu-id="6eda7-106">Each record represents one source.</span></span>
  
|<span data-ttu-id="6eda7-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="6eda7-107">**Column**</span></span>|<span data-ttu-id="6eda7-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="6eda7-108">**Data Type**</span></span>|<span data-ttu-id="6eda7-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="6eda7-109">**Key/Index**</span></span>|<span data-ttu-id="6eda7-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="6eda7-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="6eda7-111">**апплиедбандвидссаурцекэй**</span><span class="sxs-lookup"><span data-stu-id="6eda7-111">**AppliedBandwidthSourceKey**</span></span> <br/> |<span data-ttu-id="6eda7-112">целое</span><span class="sxs-lookup"><span data-stu-id="6eda7-112">int</span></span>  <br/> |<span data-ttu-id="6eda7-113">Primary</span><span class="sxs-lookup"><span data-stu-id="6eda7-113">Primary</span></span>  <br/> |<span data-ttu-id="6eda7-114">Уникальный номер, идентифицирующий источник.</span><span class="sxs-lookup"><span data-stu-id="6eda7-114">Unique number identifying the source.</span></span>  <br/> |
|<span data-ttu-id="6eda7-115">**AppliedBandwidthSource**</span><span class="sxs-lookup"><span data-stu-id="6eda7-115">**AppliedBandwidthSource**</span></span> <br/> |<span data-ttu-id="6eda7-116">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="6eda7-116">varchar(256)</span></span>  <br/> |<span data-ttu-id="6eda7-117">Повторя</span><span class="sxs-lookup"><span data-stu-id="6eda7-117">Unique</span></span>  <br/> |<span data-ttu-id="6eda7-118">Это источник установленного места для пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="6eda7-118">This is the source of the bandwidth cap being imposed.</span></span> <span data-ttu-id="6eda7-119">Она описывает, откуда поступают ограничения пропускной способности (например, "сервер политики", "превратить сервер" или "модальность").</span><span class="sxs-lookup"><span data-stu-id="6eda7-119">It describes where the bandwidth limit is coming from (for example, "Policy Server", "TURN Server", or "Modality").</span></span>  <br/> |
   

