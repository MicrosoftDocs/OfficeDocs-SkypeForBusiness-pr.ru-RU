---
title: Таблица Endpoint
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 500f330d-4d7d-4e88-b1cc-fef9a9de6b5c
description: В таблице конечная точка представляет собой вспомогательную таблицу, в которой хранятся сведения о конечных точках, которые участвовали в сеансах, записанные в базе данных. Каждая запись в таблице представляет одной конечной точки.
ms.openlocfilehash: 4917b0817d8fcedbc3a20b2c41d3ed62ce468c5c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920112"
---
# <a name="endpoint-table"></a><span data-ttu-id="3a500-104">Таблица Endpoint</span><span class="sxs-lookup"><span data-stu-id="3a500-104">Endpoint table</span></span>
 
<span data-ttu-id="3a500-105">В таблице конечная точка представляет собой вспомогательную таблицу, в которой хранятся сведения о конечных точках, которые участвовали в сеансах, записанные в базе данных.</span><span class="sxs-lookup"><span data-stu-id="3a500-105">The Endpoint table is a supporting table that stores information about the endpoints that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="3a500-106">Каждая запись в таблице представляет одной конечной точки.</span><span class="sxs-lookup"><span data-stu-id="3a500-106">Each record in the table represents one endpoint.</span></span>
  
|<span data-ttu-id="3a500-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="3a500-107">**Column**</span></span>|<span data-ttu-id="3a500-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="3a500-108">**Data Type**</span></span>|<span data-ttu-id="3a500-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="3a500-109">**Key/Index**</span></span>|<span data-ttu-id="3a500-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="3a500-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="3a500-111">**EndpointKey**</span><span class="sxs-lookup"><span data-stu-id="3a500-111">**EndpointKey**</span></span> <br/> |<span data-ttu-id="3a500-112">целое</span><span class="sxs-lookup"><span data-stu-id="3a500-112">int</span></span>  <br/> |<span data-ttu-id="3a500-113">Primary</span><span class="sxs-lookup"><span data-stu-id="3a500-113">Primary</span></span>  <br/> |<span data-ttu-id="3a500-114">Уникальный номер, идентифицирующий эту конечную точку.</span><span class="sxs-lookup"><span data-stu-id="3a500-114">Unique number identifying this endpoint.</span></span>  <br/> |
|<span data-ttu-id="3a500-115">**Имя**.</span><span class="sxs-lookup"><span data-stu-id="3a500-115">**Name**</span></span> <br/> |<span data-ttu-id="3a500-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="3a500-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="3a500-117">Уникальный</span><span class="sxs-lookup"><span data-stu-id="3a500-117">Unique</span></span>  <br/> |<span data-ttu-id="3a500-118">Имя конечной точки.</span><span class="sxs-lookup"><span data-stu-id="3a500-118">Endpoint name.</span></span>  <br/> |
|<span data-ttu-id="3a500-119">**OS**</span><span class="sxs-lookup"><span data-stu-id="3a500-119">**OS**</span></span> <br/> |<span data-ttu-id="3a500-120">nvarchar(128)</span><span class="sxs-lookup"><span data-stu-id="3a500-120">nvarchar(128)</span></span>  <br/> | <br/> |<span data-ttu-id="3a500-121">Операционная система конечной точки.</span><span class="sxs-lookup"><span data-stu-id="3a500-121">Operating system (OS) of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="3a500-122">**CPUName**</span><span class="sxs-lookup"><span data-stu-id="3a500-122">**CPUName**</span></span> <br/> |<span data-ttu-id="3a500-123">nvarchar(128)</span><span class="sxs-lookup"><span data-stu-id="3a500-123">nvarchar(128)</span></span>  <br/> ||<span data-ttu-id="3a500-124">Имя ЦП конечной точки.</span><span class="sxs-lookup"><span data-stu-id="3a500-124">CPU name of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="3a500-125">**CPUNumberOfCores**</span><span class="sxs-lookup"><span data-stu-id="3a500-125">**CPUNumberOfCores**</span></span> <br/> |<span data-ttu-id="3a500-126">smallint</span><span class="sxs-lookup"><span data-stu-id="3a500-126">smallint</span></span>  <br/> ||<span data-ttu-id="3a500-127">Число ядер ЦП конечной точки.</span><span class="sxs-lookup"><span data-stu-id="3a500-127">Number of CPU cores of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="3a500-128">**CPUProcessorSpeed**</span><span class="sxs-lookup"><span data-stu-id="3a500-128">**CPUProcessorSpeed**</span></span> <br/> |<span data-ttu-id="3a500-129">целое</span><span class="sxs-lookup"><span data-stu-id="3a500-129">int</span></span>  <br/> ||<span data-ttu-id="3a500-130">Скорость ЦП конечной точки.</span><span class="sxs-lookup"><span data-stu-id="3a500-130">CPU processor speed of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="3a500-131">**VirtualizationFlag**</span><span class="sxs-lookup"><span data-stu-id="3a500-131">**VirtualizationFlag**</span></span> <br/> |<span data-ttu-id="3a500-132">tinyint</span><span class="sxs-lookup"><span data-stu-id="3a500-132">tinyint</span></span>  <br/> || <span data-ttu-id="3a500-133">Битовый флаг, указывающий, если в системе запущена в виртуализованной среде:</span><span class="sxs-lookup"><span data-stu-id="3a500-133">Bit flag that indicates if the system is running in a virtualized environment:</span></span> <br/>  <span data-ttu-id="3a500-134">0x0000 - нет</span><span class="sxs-lookup"><span data-stu-id="3a500-134">0x0000 - None</span></span> <br/>  <span data-ttu-id="3a500-135">0x0001 - HyperV</span><span class="sxs-lookup"><span data-stu-id="3a500-135">0x0001 - HyperV</span></span> <br/>  <span data-ttu-id="3a500-136">0x0002 - VMWare</span><span class="sxs-lookup"><span data-stu-id="3a500-136">0x0002 - VMWare</span></span> <br/>  <span data-ttu-id="3a500-137">0x0004 - virtual PC</span><span class="sxs-lookup"><span data-stu-id="3a500-137">0x0004 - Virtual PC</span></span> <br/>  <span data-ttu-id="3a500-138">0x0008 - Xen ПК</span><span class="sxs-lookup"><span data-stu-id="3a500-138">0x0008 - Xen PC</span></span> <br/> |
   

