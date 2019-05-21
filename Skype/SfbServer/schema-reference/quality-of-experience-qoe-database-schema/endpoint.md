---
title: Таблица Endpoint
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 500f330d-4d7d-4e88-b1cc-fef9a9de6b5c
description: Таблица конечных точек — это вспомогательная таблица, в которой хранятся сведения о конечных точках, участвующих в сеансах, записанных в базе данных. Каждая запись в таблице представляет одну конечную точку.
ms.openlocfilehash: 7d582d382784d04d4495de972aa20673862284f4
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294994"
---
# <a name="endpoint-table"></a><span data-ttu-id="91c26-104">Таблица Endpoint</span><span class="sxs-lookup"><span data-stu-id="91c26-104">Endpoint table</span></span>
 
<span data-ttu-id="91c26-105">Таблица конечных точек — это вспомогательная таблица, в которой хранятся сведения о конечных точках, участвующих в сеансах, записанных в базе данных.</span><span class="sxs-lookup"><span data-stu-id="91c26-105">The Endpoint table is a supporting table that stores information about the endpoints that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="91c26-106">Каждая запись в таблице представляет одну конечную точку.</span><span class="sxs-lookup"><span data-stu-id="91c26-106">Each record in the table represents one endpoint.</span></span>
  
|<span data-ttu-id="91c26-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="91c26-107">**Column**</span></span>|<span data-ttu-id="91c26-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="91c26-108">**Data Type**</span></span>|<span data-ttu-id="91c26-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="91c26-109">**Key/Index**</span></span>|<span data-ttu-id="91c26-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="91c26-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="91c26-111">**Ендпоинткэй**</span><span class="sxs-lookup"><span data-stu-id="91c26-111">**EndpointKey**</span></span> <br/> |<span data-ttu-id="91c26-112">целое</span><span class="sxs-lookup"><span data-stu-id="91c26-112">int</span></span>  <br/> |<span data-ttu-id="91c26-113">Primary</span><span class="sxs-lookup"><span data-stu-id="91c26-113">Primary</span></span>  <br/> |<span data-ttu-id="91c26-114">Уникальный номер, идентифицирующий эту конечную точку.</span><span class="sxs-lookup"><span data-stu-id="91c26-114">Unique number identifying this endpoint.</span></span>  <br/> |
|<span data-ttu-id="91c26-115">**Имя**.</span><span class="sxs-lookup"><span data-stu-id="91c26-115">**Name**</span></span> <br/> |<span data-ttu-id="91c26-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="91c26-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="91c26-117">Повторя</span><span class="sxs-lookup"><span data-stu-id="91c26-117">Unique</span></span>  <br/> |<span data-ttu-id="91c26-118">Имя конечной точки.</span><span class="sxs-lookup"><span data-stu-id="91c26-118">Endpoint name.</span></span>  <br/> |
|<span data-ttu-id="91c26-119">**OS**</span><span class="sxs-lookup"><span data-stu-id="91c26-119">**OS**</span></span> <br/> |<span data-ttu-id="91c26-120">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="91c26-120">nvarchar(128)</span></span>  <br/> | <br/> |<span data-ttu-id="91c26-121">Операционная система (ОС) конечной точки.</span><span class="sxs-lookup"><span data-stu-id="91c26-121">Operating system (OS) of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="91c26-122">**Кпунаме**</span><span class="sxs-lookup"><span data-stu-id="91c26-122">**CPUName**</span></span> <br/> |<span data-ttu-id="91c26-123">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="91c26-123">nvarchar(128)</span></span>  <br/> ||<span data-ttu-id="91c26-124">Имя ЦП конечной точки.</span><span class="sxs-lookup"><span data-stu-id="91c26-124">CPU name of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="91c26-125">**Кпунумберофкорес**</span><span class="sxs-lookup"><span data-stu-id="91c26-125">**CPUNumberOfCores**</span></span> <br/> |<span data-ttu-id="91c26-126">smallint</span><span class="sxs-lookup"><span data-stu-id="91c26-126">smallint</span></span>  <br/> ||<span data-ttu-id="91c26-127">Количество ядер ЦП конечной точки.</span><span class="sxs-lookup"><span data-stu-id="91c26-127">Number of CPU cores of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="91c26-128">**Кпупроцессорспид**</span><span class="sxs-lookup"><span data-stu-id="91c26-128">**CPUProcessorSpeed**</span></span> <br/> |<span data-ttu-id="91c26-129">целое</span><span class="sxs-lookup"><span data-stu-id="91c26-129">int</span></span>  <br/> ||<span data-ttu-id="91c26-130">Тактовая частота процессора для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="91c26-130">CPU processor speed of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="91c26-131">**Виртуализатионфлаг**</span><span class="sxs-lookup"><span data-stu-id="91c26-131">**VirtualizationFlag**</span></span> <br/> |<span data-ttu-id="91c26-132">tinyint</span><span class="sxs-lookup"><span data-stu-id="91c26-132">tinyint</span></span>  <br/> || <span data-ttu-id="91c26-133">Битовый флаг, указывающий на то, что система работает в виртуализованной среде.</span><span class="sxs-lookup"><span data-stu-id="91c26-133">Bit flag that indicates if the system is running in a virtualized environment:</span></span> <br/>  <span data-ttu-id="91c26-134">0x0000 — None</span><span class="sxs-lookup"><span data-stu-id="91c26-134">0x0000 - None</span></span> <br/>  <span data-ttu-id="91c26-135">0x0001-HyperV</span><span class="sxs-lookup"><span data-stu-id="91c26-135">0x0001 - HyperV</span></span> <br/>  <span data-ttu-id="91c26-136">0x0002 — VMWare</span><span class="sxs-lookup"><span data-stu-id="91c26-136">0x0002 - VMWare</span></span> <br/>  <span data-ttu-id="91c26-137">0x0004 — виртуальный ПК</span><span class="sxs-lookup"><span data-stu-id="91c26-137">0x0004 - Virtual PC</span></span> <br/>  <span data-ttu-id="91c26-138">0x0008 — компьютер Xen</span><span class="sxs-lookup"><span data-stu-id="91c26-138">0x0008 - Xen PC</span></span> <br/> |
   

