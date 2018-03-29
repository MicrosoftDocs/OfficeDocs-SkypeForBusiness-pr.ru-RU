---
title: Таблица Endpoint
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 500f330d-4d7d-4e88-b1cc-fef9a9de6b5c
description: В таблице конечная точка представляет собой вспомогательную таблицу, в которой хранятся сведения о конечных точках, которые участвовали в сеансах, записанные в базе данных. Каждая запись в таблице представляет одной конечной точки.
ms.openlocfilehash: 64eb55a0c1bebe7f2ce992351ce21db2fdc575d7
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="endpoint-table"></a><span data-ttu-id="56f12-104">Таблица Endpoint</span><span class="sxs-lookup"><span data-stu-id="56f12-104">Endpoint table</span></span>
 
<span data-ttu-id="56f12-105">В таблице конечная точка представляет собой вспомогательную таблицу, в которой хранятся сведения о конечных точках, которые участвовали в сеансах, записанные в базе данных.</span><span class="sxs-lookup"><span data-stu-id="56f12-105">The Endpoint table is a supporting table that stores information about the endpoints that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="56f12-106">Каждая запись в таблице представляет одной конечной точки.</span><span class="sxs-lookup"><span data-stu-id="56f12-106">Each record in the table represents one endpoint.</span></span>
  
|<span data-ttu-id="56f12-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="56f12-107">**Column**</span></span>|<span data-ttu-id="56f12-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="56f12-108">**Data Type**</span></span>|<span data-ttu-id="56f12-109">**Ключ или индекс**</span><span class="sxs-lookup"><span data-stu-id="56f12-109">**Key/Index**</span></span>|<span data-ttu-id="56f12-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="56f12-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="56f12-111">**EndpointKey**</span><span class="sxs-lookup"><span data-stu-id="56f12-111">**EndpointKey**</span></span> <br/> |<span data-ttu-id="56f12-112">целое</span><span class="sxs-lookup"><span data-stu-id="56f12-112">int</span></span>  <br/> |<span data-ttu-id="56f12-113">Primary</span><span class="sxs-lookup"><span data-stu-id="56f12-113">Primary</span></span>  <br/> |<span data-ttu-id="56f12-114">Уникальный номер, идентифицирующий эту конечную точку.</span><span class="sxs-lookup"><span data-stu-id="56f12-114">Unique number identifying this endpoint.</span></span>  <br/> |
|<span data-ttu-id="56f12-115">**Имя**.</span><span class="sxs-lookup"><span data-stu-id="56f12-115">**Name**</span></span> <br/> |<span data-ttu-id="56f12-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="56f12-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="56f12-117">Уникальный</span><span class="sxs-lookup"><span data-stu-id="56f12-117">Unique</span></span>  <br/> |<span data-ttu-id="56f12-118">Имя конечной точки.</span><span class="sxs-lookup"><span data-stu-id="56f12-118">Endpoint name.</span></span>  <br/> |
|<span data-ttu-id="56f12-119">**ОПЕРАЦИОННАЯ СИСТЕМА**</span><span class="sxs-lookup"><span data-stu-id="56f12-119">**OS**</span></span> <br/> |<span data-ttu-id="56f12-120">nvarchar(128)</span><span class="sxs-lookup"><span data-stu-id="56f12-120">nvarchar(128)</span></span>  <br/> | <br/> |<span data-ttu-id="56f12-121">Операционная система конечной точки.</span><span class="sxs-lookup"><span data-stu-id="56f12-121">Operating system (OS) of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="56f12-122">**CPUName**</span><span class="sxs-lookup"><span data-stu-id="56f12-122">**CPUName**</span></span> <br/> |<span data-ttu-id="56f12-123">nvarchar(128)</span><span class="sxs-lookup"><span data-stu-id="56f12-123">nvarchar(128)</span></span>  <br/> ||<span data-ttu-id="56f12-124">Имя ЦП конечной точки.</span><span class="sxs-lookup"><span data-stu-id="56f12-124">CPU name of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="56f12-125">**CPUNumberOfCores**</span><span class="sxs-lookup"><span data-stu-id="56f12-125">**CPUNumberOfCores**</span></span> <br/> |<span data-ttu-id="56f12-126">smallint</span><span class="sxs-lookup"><span data-stu-id="56f12-126">smallint</span></span>  <br/> ||<span data-ttu-id="56f12-127">Число ядер ЦП конечной точки.</span><span class="sxs-lookup"><span data-stu-id="56f12-127">Number of CPU cores of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="56f12-128">**CPUProcessorSpeed**</span><span class="sxs-lookup"><span data-stu-id="56f12-128">**CPUProcessorSpeed**</span></span> <br/> |<span data-ttu-id="56f12-129">целое</span><span class="sxs-lookup"><span data-stu-id="56f12-129">int</span></span>  <br/> ||<span data-ttu-id="56f12-130">Скорость ЦП конечной точки.</span><span class="sxs-lookup"><span data-stu-id="56f12-130">CPU processor speed of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="56f12-131">**VirtualizationFlag**</span><span class="sxs-lookup"><span data-stu-id="56f12-131">**VirtualizationFlag**</span></span> <br/> |<span data-ttu-id="56f12-132">tinyint</span><span class="sxs-lookup"><span data-stu-id="56f12-132">tinyint</span></span>  <br/> || <span data-ttu-id="56f12-133">Битовый флаг, указывающий, если в системе запущена в виртуализованной среде:</span><span class="sxs-lookup"><span data-stu-id="56f12-133">Bit flag that indicates if the system is running in a virtualized environment:</span></span> <br/>  <span data-ttu-id="56f12-134">0x0000 - нет</span><span class="sxs-lookup"><span data-stu-id="56f12-134">0x0000 - None</span></span> <br/>  <span data-ttu-id="56f12-135">0x0001 - HyperV</span><span class="sxs-lookup"><span data-stu-id="56f12-135">0x0001 - HyperV</span></span> <br/>  <span data-ttu-id="56f12-136">0x0002 - VMWare</span><span class="sxs-lookup"><span data-stu-id="56f12-136">0x0002 - VMWare</span></span> <br/>  <span data-ttu-id="56f12-137">0x0004 - virtual PC</span><span class="sxs-lookup"><span data-stu-id="56f12-137">0x0004 - Virtual PC</span></span> <br/>  <span data-ttu-id="56f12-138">0x0008 - Xen ПК</span><span class="sxs-lookup"><span data-stu-id="56f12-138">0x0008 - Xen PC</span></span> <br/> |
   

