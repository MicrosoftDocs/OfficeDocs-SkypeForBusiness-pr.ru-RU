---
title: Таблица Endpoint
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
ms.assetid: 500f330d-4d7d-4e88-b1cc-fef9a9de6b5c
description: Таблица Endpoint — это вспомогательная таблица, в которой хранится информация о конечных точках, которые участвовали в сеансах, записанных в базе данных. Каждая запись в таблице представляет одну конечную точку.
ms.openlocfilehash: 9caa0571e562a84c1678208f0e70c27317deda3c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823069"
---
# <a name="endpoint-table"></a><span data-ttu-id="ca81c-104">Таблица Endpoint</span><span class="sxs-lookup"><span data-stu-id="ca81c-104">Endpoint table</span></span>
 
<span data-ttu-id="ca81c-105">Таблица Endpoint — это вспомогательная таблица, в которой хранится информация о конечных точках, которые участвовали в сеансах, записанных в базе данных.</span><span class="sxs-lookup"><span data-stu-id="ca81c-105">The Endpoint table is a supporting table that stores information about the endpoints that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="ca81c-106">Каждая запись в таблице представляет одну конечную точку.</span><span class="sxs-lookup"><span data-stu-id="ca81c-106">Each record in the table represents one endpoint.</span></span>
  
|<span data-ttu-id="ca81c-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="ca81c-107">**Column**</span></span>|<span data-ttu-id="ca81c-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="ca81c-108">**Data Type**</span></span>|<span data-ttu-id="ca81c-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="ca81c-109">**Key/Index**</span></span>|<span data-ttu-id="ca81c-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="ca81c-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ca81c-111">**EndpointKey**</span><span class="sxs-lookup"><span data-stu-id="ca81c-111">**EndpointKey**</span></span> <br/> |<span data-ttu-id="ca81c-112">int</span><span class="sxs-lookup"><span data-stu-id="ca81c-112">int</span></span>  <br/> |<span data-ttu-id="ca81c-113">Primary</span><span class="sxs-lookup"><span data-stu-id="ca81c-113">Primary</span></span>  <br/> |<span data-ttu-id="ca81c-114">Уникальный номер, идентифицирующий эту конечную точку.</span><span class="sxs-lookup"><span data-stu-id="ca81c-114">Unique number identifying this endpoint.</span></span>  <br/> |
|<span data-ttu-id="ca81c-115">**Название**</span><span class="sxs-lookup"><span data-stu-id="ca81c-115">**Name**</span></span> <br/> |<span data-ttu-id="ca81c-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="ca81c-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="ca81c-117">Уникальные</span><span class="sxs-lookup"><span data-stu-id="ca81c-117">Unique</span></span>  <br/> |<span data-ttu-id="ca81c-118">Имя конечной точки.</span><span class="sxs-lookup"><span data-stu-id="ca81c-118">Endpoint name.</span></span>  <br/> |
|<span data-ttu-id="ca81c-119">**ОС**</span><span class="sxs-lookup"><span data-stu-id="ca81c-119">**OS**</span></span> <br/> |<span data-ttu-id="ca81c-120">nvarchar(128)</span><span class="sxs-lookup"><span data-stu-id="ca81c-120">nvarchar(128)</span></span>  <br/> | <br/> |<span data-ttu-id="ca81c-121">Операционная система (ОС) конечной точки.</span><span class="sxs-lookup"><span data-stu-id="ca81c-121">Operating system (OS) of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="ca81c-122">**CPUName**</span><span class="sxs-lookup"><span data-stu-id="ca81c-122">**CPUName**</span></span> <br/> |<span data-ttu-id="ca81c-123">nvarchar(128)</span><span class="sxs-lookup"><span data-stu-id="ca81c-123">nvarchar(128)</span></span>  <br/> ||<span data-ttu-id="ca81c-124">Имя ЦП конечной точки.</span><span class="sxs-lookup"><span data-stu-id="ca81c-124">CPU name of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="ca81c-125">**CPUNumberOfCores**</span><span class="sxs-lookup"><span data-stu-id="ca81c-125">**CPUNumberOfCores**</span></span> <br/> |<span data-ttu-id="ca81c-126">smallint</span><span class="sxs-lookup"><span data-stu-id="ca81c-126">smallint</span></span>  <br/> ||<span data-ttu-id="ca81c-127">Количество ядер ЦП конечной точки.</span><span class="sxs-lookup"><span data-stu-id="ca81c-127">Number of CPU cores of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="ca81c-128">**CPUProcessorSpeed**</span><span class="sxs-lookup"><span data-stu-id="ca81c-128">**CPUProcessorSpeed**</span></span> <br/> |<span data-ttu-id="ca81c-129">int</span><span class="sxs-lookup"><span data-stu-id="ca81c-129">int</span></span>  <br/> ||<span data-ttu-id="ca81c-130">Скорость процессора ЦП конечной точки.</span><span class="sxs-lookup"><span data-stu-id="ca81c-130">CPU processor speed of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="ca81c-131">**VirtualizationFlag**</span><span class="sxs-lookup"><span data-stu-id="ca81c-131">**VirtualizationFlag**</span></span> <br/> |<span data-ttu-id="ca81c-132">tinyint</span><span class="sxs-lookup"><span data-stu-id="ca81c-132">tinyint</span></span>  <br/> || <span data-ttu-id="ca81c-133">Флаг бита, который указывает, работает ли система в виртуализированной среде:</span><span class="sxs-lookup"><span data-stu-id="ca81c-133">Bit flag that indicates if the system is running in a virtualized environment:</span></span> <br/>  <span data-ttu-id="ca81c-134">0x0000 - Нет</span><span class="sxs-lookup"><span data-stu-id="ca81c-134">0x0000 - None</span></span> <br/>  <span data-ttu-id="ca81c-135">0x0001 — HyperV</span><span class="sxs-lookup"><span data-stu-id="ca81c-135">0x0001 - HyperV</span></span> <br/>  <span data-ttu-id="ca81c-136">0x0002 VMWare</span><span class="sxs-lookup"><span data-stu-id="ca81c-136">0x0002 - VMWare</span></span> <br/>  <span data-ttu-id="ca81c-137">0x0004 виртуальный КОМПЬЮТЕР</span><span class="sxs-lookup"><span data-stu-id="ca81c-137">0x0004 - Virtual PC</span></span> <br/>  <span data-ttu-id="ca81c-138">0x0008 Xen PC</span><span class="sxs-lookup"><span data-stu-id="ca81c-138">0x0008 - Xen PC</span></span> <br/> |
   

