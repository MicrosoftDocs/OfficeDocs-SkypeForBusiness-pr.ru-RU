---
title: Таблица Servers
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9af89d08-d35a-48e8-b56d-6df292f973cc
description: В таблице Server представляет собой вспомогательную таблицу. Каждая запись представляет один сервер.
ms.openlocfilehash: be48b90cc727ebfd0320b38ac0d89a302dab6b07
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="server-table"></a><span data-ttu-id="caf21-104">Таблица Servers</span><span class="sxs-lookup"><span data-stu-id="caf21-104">Server table</span></span>
 
<span data-ttu-id="caf21-105">В таблице Server представляет собой вспомогательную таблицу.</span><span class="sxs-lookup"><span data-stu-id="caf21-105">The Server table is a supporting table.</span></span> <span data-ttu-id="caf21-106">Каждая запись представляет один сервер.</span><span class="sxs-lookup"><span data-stu-id="caf21-106">Each record represents one server.</span></span> 
  
|<span data-ttu-id="caf21-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="caf21-107">**Column**</span></span>|<span data-ttu-id="caf21-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="caf21-108">**Data Type**</span></span>|<span data-ttu-id="caf21-109">**Ключ или индекс**</span><span class="sxs-lookup"><span data-stu-id="caf21-109">**Key/Index**</span></span>|<span data-ttu-id="caf21-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="caf21-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="caf21-111">**ServerKey**</span><span class="sxs-lookup"><span data-stu-id="caf21-111">**ServerKey**</span></span> <br/> |<span data-ttu-id="caf21-112">целое</span><span class="sxs-lookup"><span data-stu-id="caf21-112">int</span></span>  <br/> |<span data-ttu-id="caf21-113">Primary</span><span class="sxs-lookup"><span data-stu-id="caf21-113">Primary</span></span>  <br/> |<span data-ttu-id="caf21-114">Уникальный номер, идентифицирующий сервер.</span><span class="sxs-lookup"><span data-stu-id="caf21-114">Unique number identifying the server.</span></span>  <br/> |
|<span data-ttu-id="caf21-115">**FQDNOrIP**</span><span class="sxs-lookup"><span data-stu-id="caf21-115">**FQDNOrIP**</span></span> <br/> |<span data-ttu-id="caf21-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="caf21-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="caf21-117">Индекс</span><span class="sxs-lookup"><span data-stu-id="caf21-117">index</span></span>  <br/> |<span data-ttu-id="caf21-118">Строка MAC-адреса.</span><span class="sxs-lookup"><span data-stu-id="caf21-118">MAC address string.</span></span>  <br/> |
|<span data-ttu-id="caf21-119">**ServerType**</span><span class="sxs-lookup"><span data-stu-id="caf21-119">**ServerType**</span></span> <br/> |<span data-ttu-id="caf21-120">целое</span><span class="sxs-lookup"><span data-stu-id="caf21-120">int</span></span>  <br/> |<span data-ttu-id="caf21-121">Внешний</span><span class="sxs-lookup"><span data-stu-id="caf21-121">Foreign</span></span>  <br/> |<span data-ttu-id="caf21-122">1: сервер-посредник</span><span class="sxs-lookup"><span data-stu-id="caf21-122">1: Mediation Server</span></span>  <br/> <span data-ttu-id="caf21-123">2: A / видеоконференций 16394: A пограничного service32769: шлюз</span><span class="sxs-lookup"><span data-stu-id="caf21-123">2: A/V Conferencing Server16394: A/V Edge service32769: Gateway</span></span>  <br/> |
|<span data-ttu-id="caf21-124">**PoolName**</span><span class="sxs-lookup"><span data-stu-id="caf21-124">**PoolName**</span></span> <br/> |<span data-ttu-id="caf21-125">nvarchar(512)</span><span class="sxs-lookup"><span data-stu-id="caf21-125">nvarchar(512)</span></span>  <br/> ||<span data-ttu-id="caf21-126">Пул, к которой принадлежит сервер.</span><span class="sxs-lookup"><span data-stu-id="caf21-126">Pool the server belongs to.</span></span> <span data-ttu-id="caf21-127">Применяется только для A / V Server конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="caf21-127">Only applicable for the A/V Conferencing Server.</span></span>  <br/> |
|<span data-ttu-id="caf21-128">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="caf21-128">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="caf21-129">datetime</span><span class="sxs-lookup"><span data-stu-id="caf21-129">datetime</span></span>  <br/> ||<span data-ttu-id="caf21-130">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="caf21-130">For internal use only.</span></span>  <br/> |
   

