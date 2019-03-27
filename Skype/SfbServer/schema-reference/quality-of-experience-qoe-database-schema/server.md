---
title: Таблица Servers
ms.reviewer: ''
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
ms.openlocfilehash: 877743f5d589cd4fea34039786b33bd410069bb3
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874310"
---
# <a name="server-table"></a><span data-ttu-id="d5475-104">Таблица Servers</span><span class="sxs-lookup"><span data-stu-id="d5475-104">Server table</span></span>
 
<span data-ttu-id="d5475-105">В таблице Server представляет собой вспомогательную таблицу.</span><span class="sxs-lookup"><span data-stu-id="d5475-105">The Server table is a supporting table.</span></span> <span data-ttu-id="d5475-106">Каждая запись представляет один сервер.</span><span class="sxs-lookup"><span data-stu-id="d5475-106">Each record represents one server.</span></span> 
  
|<span data-ttu-id="d5475-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="d5475-107">**Column**</span></span>|<span data-ttu-id="d5475-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="d5475-108">**Data Type**</span></span>|<span data-ttu-id="d5475-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="d5475-109">**Key/Index**</span></span>|<span data-ttu-id="d5475-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="d5475-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d5475-111">**ServerKey**</span><span class="sxs-lookup"><span data-stu-id="d5475-111">**ServerKey**</span></span> <br/> |<span data-ttu-id="d5475-112">целое</span><span class="sxs-lookup"><span data-stu-id="d5475-112">int</span></span>  <br/> |<span data-ttu-id="d5475-113">Primary</span><span class="sxs-lookup"><span data-stu-id="d5475-113">Primary</span></span>  <br/> |<span data-ttu-id="d5475-114">Уникальный номер, идентифицирующий сервер.</span><span class="sxs-lookup"><span data-stu-id="d5475-114">Unique number identifying the server.</span></span>  <br/> |
|<span data-ttu-id="d5475-115">**FQDNOrIP**</span><span class="sxs-lookup"><span data-stu-id="d5475-115">**FQDNOrIP**</span></span> <br/> |<span data-ttu-id="d5475-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="d5475-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="d5475-117">Индекс</span><span class="sxs-lookup"><span data-stu-id="d5475-117">index</span></span>  <br/> |<span data-ttu-id="d5475-118">Строка MAC-адреса.</span><span class="sxs-lookup"><span data-stu-id="d5475-118">MAC address string.</span></span>  <br/> |
|<span data-ttu-id="d5475-119">**ServerType**</span><span class="sxs-lookup"><span data-stu-id="d5475-119">**ServerType**</span></span> <br/> |<span data-ttu-id="d5475-120">целое</span><span class="sxs-lookup"><span data-stu-id="d5475-120">int</span></span>  <br/> |<span data-ttu-id="d5475-121">Внешний</span><span class="sxs-lookup"><span data-stu-id="d5475-121">Foreign</span></span>  <br/> |<span data-ttu-id="d5475-122">1: сервер-посредник</span><span class="sxs-lookup"><span data-stu-id="d5475-122">1: Mediation Server</span></span>  <br/> <span data-ttu-id="d5475-123">2: A / видеоконференций 16394: A пограничного service32769: шлюз</span><span class="sxs-lookup"><span data-stu-id="d5475-123">2: A/V Conferencing Server16394: A/V Edge service32769: Gateway</span></span>  <br/> |
|<span data-ttu-id="d5475-124">**PoolName**</span><span class="sxs-lookup"><span data-stu-id="d5475-124">**PoolName**</span></span> <br/> |<span data-ttu-id="d5475-125">nvarchar(512)</span><span class="sxs-lookup"><span data-stu-id="d5475-125">nvarchar(512)</span></span>  <br/> ||<span data-ttu-id="d5475-126">Пул, к которой принадлежит сервер.</span><span class="sxs-lookup"><span data-stu-id="d5475-126">Pool the server belongs to.</span></span> <span data-ttu-id="d5475-127">Применяется только для A / V Server конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="d5475-127">Only applicable for the A/V Conferencing Server.</span></span>  <br/> |
|<span data-ttu-id="d5475-128">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="d5475-128">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="d5475-129">datetime</span><span class="sxs-lookup"><span data-stu-id="d5475-129">datetime</span></span>  <br/> ||<span data-ttu-id="d5475-130">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="d5475-130">For internal use only.</span></span>  <br/> |
   

