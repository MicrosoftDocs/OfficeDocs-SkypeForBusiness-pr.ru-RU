---
title: Таблица Endpoint
ms.reviewer: ''
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
ms.openlocfilehash: f9c304408006ef9caf5521b8f0bbe28c2d917abe
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212244"
---
# <a name="endpoint-table"></a><span data-ttu-id="95b94-104">Таблица Endpoint</span><span class="sxs-lookup"><span data-stu-id="95b94-104">Endpoint table</span></span>
 
<span data-ttu-id="95b94-105">В таблице конечная точка представляет собой вспомогательную таблицу, в которой хранятся сведения о конечных точках, которые участвовали в сеансах, записанные в базе данных.</span><span class="sxs-lookup"><span data-stu-id="95b94-105">The Endpoint table is a supporting table that stores information about the endpoints that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="95b94-106">Каждая запись в таблице представляет одной конечной точки.</span><span class="sxs-lookup"><span data-stu-id="95b94-106">Each record in the table represents one endpoint.</span></span>
  
|<span data-ttu-id="95b94-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="95b94-107">**Column**</span></span>|<span data-ttu-id="95b94-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="95b94-108">**Data Type**</span></span>|<span data-ttu-id="95b94-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="95b94-109">**Key/Index**</span></span>|<span data-ttu-id="95b94-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="95b94-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="95b94-111">**EndpointKey**</span><span class="sxs-lookup"><span data-stu-id="95b94-111">**EndpointKey**</span></span> <br/> |<span data-ttu-id="95b94-112">целое</span><span class="sxs-lookup"><span data-stu-id="95b94-112">int</span></span>  <br/> |<span data-ttu-id="95b94-113">Primary</span><span class="sxs-lookup"><span data-stu-id="95b94-113">Primary</span></span>  <br/> |<span data-ttu-id="95b94-114">Уникальный номер, идентифицирующий эту конечную точку.</span><span class="sxs-lookup"><span data-stu-id="95b94-114">Unique number identifying this endpoint.</span></span>  <br/> |
|<span data-ttu-id="95b94-115">**Имя**.</span><span class="sxs-lookup"><span data-stu-id="95b94-115">**Name**</span></span> <br/> |<span data-ttu-id="95b94-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="95b94-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="95b94-117">Уникальный</span><span class="sxs-lookup"><span data-stu-id="95b94-117">Unique</span></span>  <br/> |<span data-ttu-id="95b94-118">Имя конечной точки.</span><span class="sxs-lookup"><span data-stu-id="95b94-118">Endpoint name.</span></span>  <br/> |
|<span data-ttu-id="95b94-119">**OS**</span><span class="sxs-lookup"><span data-stu-id="95b94-119">**OS**</span></span> <br/> |<span data-ttu-id="95b94-120">nvarchar(128)</span><span class="sxs-lookup"><span data-stu-id="95b94-120">nvarchar(128)</span></span>  <br/> | <br/> |<span data-ttu-id="95b94-121">Операционная система конечной точки.</span><span class="sxs-lookup"><span data-stu-id="95b94-121">Operating system (OS) of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="95b94-122">**CPUName**</span><span class="sxs-lookup"><span data-stu-id="95b94-122">**CPUName**</span></span> <br/> |<span data-ttu-id="95b94-123">nvarchar(128)</span><span class="sxs-lookup"><span data-stu-id="95b94-123">nvarchar(128)</span></span>  <br/> ||<span data-ttu-id="95b94-124">Имя ЦП конечной точки.</span><span class="sxs-lookup"><span data-stu-id="95b94-124">CPU name of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="95b94-125">**CPUNumberOfCores**</span><span class="sxs-lookup"><span data-stu-id="95b94-125">**CPUNumberOfCores**</span></span> <br/> |<span data-ttu-id="95b94-126">smallint</span><span class="sxs-lookup"><span data-stu-id="95b94-126">smallint</span></span>  <br/> ||<span data-ttu-id="95b94-127">Число ядер ЦП конечной точки.</span><span class="sxs-lookup"><span data-stu-id="95b94-127">Number of CPU cores of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="95b94-128">**CPUProcessorSpeed**</span><span class="sxs-lookup"><span data-stu-id="95b94-128">**CPUProcessorSpeed**</span></span> <br/> |<span data-ttu-id="95b94-129">целое</span><span class="sxs-lookup"><span data-stu-id="95b94-129">int</span></span>  <br/> ||<span data-ttu-id="95b94-130">Скорость ЦП конечной точки.</span><span class="sxs-lookup"><span data-stu-id="95b94-130">CPU processor speed of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="95b94-131">**VirtualizationFlag**</span><span class="sxs-lookup"><span data-stu-id="95b94-131">**VirtualizationFlag**</span></span> <br/> |<span data-ttu-id="95b94-132">tinyint</span><span class="sxs-lookup"><span data-stu-id="95b94-132">tinyint</span></span>  <br/> || <span data-ttu-id="95b94-133">Битовый флаг, указывающий, если в системе запущена в виртуализованной среде:</span><span class="sxs-lookup"><span data-stu-id="95b94-133">Bit flag that indicates if the system is running in a virtualized environment:</span></span> <br/>  <span data-ttu-id="95b94-134">0x0000 - нет</span><span class="sxs-lookup"><span data-stu-id="95b94-134">0x0000 - None</span></span> <br/>  <span data-ttu-id="95b94-135">0x0001 - HyperV</span><span class="sxs-lookup"><span data-stu-id="95b94-135">0x0001 - HyperV</span></span> <br/>  <span data-ttu-id="95b94-136">0x0002 - VMWare</span><span class="sxs-lookup"><span data-stu-id="95b94-136">0x0002 - VMWare</span></span> <br/>  <span data-ttu-id="95b94-137">0x0004 - virtual PC</span><span class="sxs-lookup"><span data-stu-id="95b94-137">0x0004 - Virtual PC</span></span> <br/>  <span data-ttu-id="95b94-138">0x0008 - Xen ПК</span><span class="sxs-lookup"><span data-stu-id="95b94-138">0x0008 - Xen PC</span></span> <br/> |
   

