---
title: Таблица AppliedBandwidthSource
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
ms.assetid: 24fb3caf-19b3-4c0a-90d7-ca5d53de32ad
description: Таблица AppliedBandwidthSource является вспомогательной. Каждая запись представляет один источник.
ms.openlocfilehash: bf7e1be3b98bcd56fea16dbd7aa7171b056a7f3c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831409"
---
# <a name="appliedbandwidthsource-table"></a><span data-ttu-id="765bc-104">Таблица AppliedBandwidthSource</span><span class="sxs-lookup"><span data-stu-id="765bc-104">AppliedBandwidthSource table</span></span>
 
<span data-ttu-id="765bc-p102">Таблица AppliedBandwidthSource является вспомогательной. Каждая запись представляет один источник.</span><span class="sxs-lookup"><span data-stu-id="765bc-p102">The AppliedBandwidthSource table is a supporting table. Each record represents one source.</span></span>
  
|<span data-ttu-id="765bc-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="765bc-107">**Column**</span></span>|<span data-ttu-id="765bc-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="765bc-108">**Data Type**</span></span>|<span data-ttu-id="765bc-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="765bc-109">**Key/Index**</span></span>|<span data-ttu-id="765bc-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="765bc-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="765bc-111">**AppliedBandwidthSourceKey**</span><span class="sxs-lookup"><span data-stu-id="765bc-111">**AppliedBandwidthSourceKey**</span></span> <br/> |<span data-ttu-id="765bc-112">int</span><span class="sxs-lookup"><span data-stu-id="765bc-112">int</span></span>  <br/> |<span data-ttu-id="765bc-113">Primary</span><span class="sxs-lookup"><span data-stu-id="765bc-113">Primary</span></span>  <br/> |<span data-ttu-id="765bc-114">Уникальный номер, определяющий источник.</span><span class="sxs-lookup"><span data-stu-id="765bc-114">Unique number identifying the source.</span></span>  <br/> |
|<span data-ttu-id="765bc-115">**AppliedBandwidthSource**</span><span class="sxs-lookup"><span data-stu-id="765bc-115">**AppliedBandwidthSource**</span></span> <br/> |<span data-ttu-id="765bc-116">varchar(256)</span><span class="sxs-lookup"><span data-stu-id="765bc-116">varchar(256)</span></span>  <br/> |<span data-ttu-id="765bc-117">Уникальные</span><span class="sxs-lookup"><span data-stu-id="765bc-117">Unique</span></span>  <br/> |<span data-ttu-id="765bc-118">Источник применяемого ограничения пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="765bc-118">This is the source of the bandwidth cap being imposed.</span></span> <span data-ttu-id="765bc-119">В нем описывается источник ограничения пропускной способности (например, "Сервер политики", "TURN Server" или "Модальность").</span><span class="sxs-lookup"><span data-stu-id="765bc-119">It describes where the bandwidth limit is coming from (for example, "Policy Server", "TURN Server", or "Modality").</span></span>  <br/> |
   

