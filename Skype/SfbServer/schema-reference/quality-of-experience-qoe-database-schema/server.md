---
title: Таблица Servers
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9af89d08-d35a-48e8-b56d-6df292f973cc
description: Серверная таблица является вспомогательной таблицей. Каждая запись представляет один сервер.
ms.openlocfilehash: e57bb96fd715d67a5b6676a2399dc520f08bac96
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41806137"
---
# <a name="server-table"></a><span data-ttu-id="38e6d-104">Таблица Servers</span><span class="sxs-lookup"><span data-stu-id="38e6d-104">Server table</span></span>
 
<span data-ttu-id="38e6d-105">Серверная таблица является вспомогательной таблицей.</span><span class="sxs-lookup"><span data-stu-id="38e6d-105">The Server table is a supporting table.</span></span> <span data-ttu-id="38e6d-106">Каждая запись представляет один сервер.</span><span class="sxs-lookup"><span data-stu-id="38e6d-106">Each record represents one server.</span></span> 
  
|<span data-ttu-id="38e6d-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="38e6d-107">**Column**</span></span>|<span data-ttu-id="38e6d-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="38e6d-108">**Data Type**</span></span>|<span data-ttu-id="38e6d-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="38e6d-109">**Key/Index**</span></span>|<span data-ttu-id="38e6d-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="38e6d-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="38e6d-111">**серверкэй**</span><span class="sxs-lookup"><span data-stu-id="38e6d-111">**ServerKey**</span></span> <br/> |<span data-ttu-id="38e6d-112">целое</span><span class="sxs-lookup"><span data-stu-id="38e6d-112">int</span></span>  <br/> |<span data-ttu-id="38e6d-113">Primary</span><span class="sxs-lookup"><span data-stu-id="38e6d-113">Primary</span></span>  <br/> |<span data-ttu-id="38e6d-114">Уникальный номер, идентифицирующий сервер.</span><span class="sxs-lookup"><span data-stu-id="38e6d-114">Unique number identifying the server.</span></span>  <br/> |
|<span data-ttu-id="38e6d-115">**фкднорип**</span><span class="sxs-lookup"><span data-stu-id="38e6d-115">**FQDNOrIP**</span></span> <br/> |<span data-ttu-id="38e6d-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="38e6d-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="38e6d-117">индекса</span><span class="sxs-lookup"><span data-stu-id="38e6d-117">index</span></span>  <br/> |<span data-ttu-id="38e6d-118">Строка MAC-адреса.</span><span class="sxs-lookup"><span data-stu-id="38e6d-118">MAC address string.</span></span>  <br/> |
|<span data-ttu-id="38e6d-119">**ServerType**</span><span class="sxs-lookup"><span data-stu-id="38e6d-119">**ServerType**</span></span> <br/> |<span data-ttu-id="38e6d-120">целое</span><span class="sxs-lookup"><span data-stu-id="38e6d-120">int</span></span>  <br/> |<span data-ttu-id="38e6d-121">Другом</span><span class="sxs-lookup"><span data-stu-id="38e6d-121">Foreign</span></span>  <br/> |<span data-ttu-id="38e6d-122">1: сервер исправлений</span><span class="sxs-lookup"><span data-stu-id="38e6d-122">1: Mediation Server</span></span>  <br/> <span data-ttu-id="38e6d-123">2: Server16394 конференции/V-service32769: шлюз</span><span class="sxs-lookup"><span data-stu-id="38e6d-123">2: A/V Conferencing Server16394: A/V Edge service32769: Gateway</span></span>  <br/> |
|<span data-ttu-id="38e6d-124">**пулнаме**</span><span class="sxs-lookup"><span data-stu-id="38e6d-124">**PoolName**</span></span> <br/> |<span data-ttu-id="38e6d-125">nvarchar (512)</span><span class="sxs-lookup"><span data-stu-id="38e6d-125">nvarchar(512)</span></span>  <br/> ||<span data-ttu-id="38e6d-126">Группа, к которой принадлежит сервер.</span><span class="sxs-lookup"><span data-stu-id="38e6d-126">Pool the server belongs to.</span></span> <span data-ttu-id="38e6d-127">Применимо только для сервера конференц-связи A/V.</span><span class="sxs-lookup"><span data-stu-id="38e6d-127">Only applicable for the A/V Conferencing Server.</span></span>  <br/> |
|<span data-ttu-id="38e6d-128">**некступдатетс**</span><span class="sxs-lookup"><span data-stu-id="38e6d-128">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="38e6d-129">datetime</span><span class="sxs-lookup"><span data-stu-id="38e6d-129">datetime</span></span>  <br/> ||<span data-ttu-id="38e6d-130">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="38e6d-130">For internal use only.</span></span>  <br/> |
   

