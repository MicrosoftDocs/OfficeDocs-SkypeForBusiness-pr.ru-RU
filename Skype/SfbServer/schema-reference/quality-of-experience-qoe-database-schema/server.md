---
title: Таблица Servers
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9af89d08-d35a-48e8-b56d-6df292f973cc
description: В таблице Server представляет собой вспомогательную таблицу. Каждая запись представляет один сервер.
ms.openlocfilehash: c0031e7181bb39895edadc40748f61626621f00e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920133"
---
# <a name="server-table"></a><span data-ttu-id="90512-104">Таблица Servers</span><span class="sxs-lookup"><span data-stu-id="90512-104">Server table</span></span>
 
<span data-ttu-id="90512-105">В таблице Server представляет собой вспомогательную таблицу.</span><span class="sxs-lookup"><span data-stu-id="90512-105">The Server table is a supporting table.</span></span> <span data-ttu-id="90512-106">Каждая запись представляет один сервер.</span><span class="sxs-lookup"><span data-stu-id="90512-106">Each record represents one server.</span></span> 
  
|<span data-ttu-id="90512-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="90512-107">**Column**</span></span>|<span data-ttu-id="90512-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="90512-108">**Data Type**</span></span>|<span data-ttu-id="90512-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="90512-109">**Key/Index**</span></span>|<span data-ttu-id="90512-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="90512-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="90512-111">**ServerKey**</span><span class="sxs-lookup"><span data-stu-id="90512-111">**ServerKey**</span></span> <br/> |<span data-ttu-id="90512-112">целое</span><span class="sxs-lookup"><span data-stu-id="90512-112">int</span></span>  <br/> |<span data-ttu-id="90512-113">Primary</span><span class="sxs-lookup"><span data-stu-id="90512-113">Primary</span></span>  <br/> |<span data-ttu-id="90512-114">Уникальный номер, идентифицирующий сервер.</span><span class="sxs-lookup"><span data-stu-id="90512-114">Unique number identifying the server.</span></span>  <br/> |
|<span data-ttu-id="90512-115">**FQDNOrIP**</span><span class="sxs-lookup"><span data-stu-id="90512-115">**FQDNOrIP**</span></span> <br/> |<span data-ttu-id="90512-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="90512-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="90512-117">Индекс</span><span class="sxs-lookup"><span data-stu-id="90512-117">index</span></span>  <br/> |<span data-ttu-id="90512-118">Строка MAC-адреса.</span><span class="sxs-lookup"><span data-stu-id="90512-118">MAC address string.</span></span>  <br/> |
|<span data-ttu-id="90512-119">**ServerType**</span><span class="sxs-lookup"><span data-stu-id="90512-119">**ServerType**</span></span> <br/> |<span data-ttu-id="90512-120">целое</span><span class="sxs-lookup"><span data-stu-id="90512-120">int</span></span>  <br/> |<span data-ttu-id="90512-121">Внешний</span><span class="sxs-lookup"><span data-stu-id="90512-121">Foreign</span></span>  <br/> |<span data-ttu-id="90512-122">1: сервер-посредник</span><span class="sxs-lookup"><span data-stu-id="90512-122">1: Mediation Server</span></span>  <br/> <span data-ttu-id="90512-123">2: A / видеоконференций 16394: A пограничного service32769: шлюз</span><span class="sxs-lookup"><span data-stu-id="90512-123">2: A/V Conferencing Server16394: A/V Edge service32769: Gateway</span></span>  <br/> |
|<span data-ttu-id="90512-124">**PoolName**</span><span class="sxs-lookup"><span data-stu-id="90512-124">**PoolName**</span></span> <br/> |<span data-ttu-id="90512-125">nvarchar(512)</span><span class="sxs-lookup"><span data-stu-id="90512-125">nvarchar(512)</span></span>  <br/> ||<span data-ttu-id="90512-126">Пул, к которой принадлежит сервер.</span><span class="sxs-lookup"><span data-stu-id="90512-126">Pool the server belongs to.</span></span> <span data-ttu-id="90512-127">Применяется только для A / V Server конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="90512-127">Only applicable for the A/V Conferencing Server.</span></span>  <br/> |
|<span data-ttu-id="90512-128">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="90512-128">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="90512-129">datetime</span><span class="sxs-lookup"><span data-stu-id="90512-129">datetime</span></span>  <br/> ||<span data-ttu-id="90512-130">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="90512-130">For internal use only.</span></span>  <br/> |
   

