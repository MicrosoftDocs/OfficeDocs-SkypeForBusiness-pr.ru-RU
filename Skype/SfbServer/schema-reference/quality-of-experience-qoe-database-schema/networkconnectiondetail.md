---
title: Таблица NetworkConnectionDetail
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b48cc9a6-5232-48b5-bd20-53b68229336b
description: Таблица NetworkConnectionDetail сопоставляет типы сетевых подключений с идентификаторами используемыми в базе данных качества взаимодействия. Эта таблица была введена в Microsoft Lync Server 2013.
ms.openlocfilehash: cc1eb91d3c633ed9455a0476b613430dfa8e3d6b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="networkconnectiondetail-table"></a><span data-ttu-id="d901f-104">Таблица NetworkConnectionDetail</span><span class="sxs-lookup"><span data-stu-id="d901f-104">NetworkConnectionDetail table</span></span>
 
<span data-ttu-id="d901f-105">Таблица NetworkConnectionDetail сопоставляет типы сетевых подключений с идентификаторами используемыми в базе данных качества взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="d901f-105">The NetworkConnectionDetail table maps network connection types to the network connection identifiers used elsewhere in the Quality of Experience database.</span></span> <span data-ttu-id="d901f-106">Эта таблица была введена в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d901f-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="d901f-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="d901f-107">**Column**</span></span>|<span data-ttu-id="d901f-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="d901f-108">**Data Type**</span></span>|<span data-ttu-id="d901f-109">**Ключ или индекс**</span><span class="sxs-lookup"><span data-stu-id="d901f-109">**Key/Index**</span></span>|<span data-ttu-id="d901f-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="d901f-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d901f-111">**NetworkConnectionDetailKey**</span><span class="sxs-lookup"><span data-stu-id="d901f-111">**NetworkConnectionDetailKey**</span></span> <br/> |<span data-ttu-id="d901f-112">tinyint</span><span class="sxs-lookup"><span data-stu-id="d901f-112">tinyint</span></span>  <br/> |<span data-ttu-id="d901f-113">Primary</span><span class="sxs-lookup"><span data-stu-id="d901f-113">Primary</span></span>  <br/> |<span data-ttu-id="d901f-114">Уникальный идентификатор типа сетевого подключения.</span><span class="sxs-lookup"><span data-stu-id="d901f-114">Unique identifier for the network connection type.</span></span>  <br/> |
|<span data-ttu-id="d901f-115">**NetworkConnectionDetail**</span><span class="sxs-lookup"><span data-stu-id="d901f-115">**NetworkConnectionDetail**</span></span> <br/> |<span data-ttu-id="d901f-116">varchar(256)</span><span class="sxs-lookup"><span data-stu-id="d901f-116">varchar(256)</span></span>  <br/> |<span data-ttu-id="d901f-117">Уникальный</span><span class="sxs-lookup"><span data-stu-id="d901f-117">Unique</span></span>  <br/> |<span data-ttu-id="d901f-118">Тип сетевого подключения, соответствующий NetworkConnectionDetailKey.</span><span class="sxs-lookup"><span data-stu-id="d901f-118">Network connection type that corresponds to the NetworkConnectionDetailKey.</span></span> <span data-ttu-id="d901f-119">Доступны значения:</span><span class="sxs-lookup"><span data-stu-id="d901f-119">Allowed values are:</span></span>  <br/> <span data-ttu-id="d901f-120">0 — проводной сети</span><span class="sxs-lookup"><span data-stu-id="d901f-120">0 -- Wired</span></span>  <br/> <span data-ttu-id="d901f-121">1 — WiFi</span><span class="sxs-lookup"><span data-stu-id="d901f-121">1 -- WiFi</span></span>  <br/> <span data-ttu-id="d901f-122">2 — Ethernet</span><span class="sxs-lookup"><span data-stu-id="d901f-122">2 -- Ethernet</span></span>  <br/> <span data-ttu-id="d901f-123">3 - MobileBB</span><span class="sxs-lookup"><span data-stu-id="d901f-123">3 -- MobileBB</span></span>  <br/> <span data-ttu-id="d901f-124">4 — другие</span><span class="sxs-lookup"><span data-stu-id="d901f-124">4 -- Other</span></span>  <br/> <span data-ttu-id="d901f-125">5 — туннель</span><span class="sxs-lookup"><span data-stu-id="d901f-125">5 -- Tunnel</span></span>  <br/> |
   

