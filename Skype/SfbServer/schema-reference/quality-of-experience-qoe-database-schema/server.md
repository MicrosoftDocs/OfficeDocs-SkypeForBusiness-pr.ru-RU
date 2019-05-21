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
localization_priority: Normal
ms.assetid: 9af89d08-d35a-48e8-b56d-6df292f973cc
description: Серверная таблица является вспомогательной таблицей. Каждая запись представляет один сервер.
ms.openlocfilehash: 93ba62c262b95b46b76cd445be04a0bc53c5a960
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294714"
---
# <a name="server-table"></a><span data-ttu-id="6ec4c-104">Таблица Servers</span><span class="sxs-lookup"><span data-stu-id="6ec4c-104">Server table</span></span>
 
<span data-ttu-id="6ec4c-105">Серверная таблица является вспомогательной таблицей.</span><span class="sxs-lookup"><span data-stu-id="6ec4c-105">The Server table is a supporting table.</span></span> <span data-ttu-id="6ec4c-106">Каждая запись представляет один сервер.</span><span class="sxs-lookup"><span data-stu-id="6ec4c-106">Each record represents one server.</span></span> 
  
|<span data-ttu-id="6ec4c-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="6ec4c-107">**Column**</span></span>|<span data-ttu-id="6ec4c-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="6ec4c-108">**Data Type**</span></span>|<span data-ttu-id="6ec4c-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="6ec4c-109">**Key/Index**</span></span>|<span data-ttu-id="6ec4c-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="6ec4c-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="6ec4c-111">**Серверкэй**</span><span class="sxs-lookup"><span data-stu-id="6ec4c-111">**ServerKey**</span></span> <br/> |<span data-ttu-id="6ec4c-112">целое</span><span class="sxs-lookup"><span data-stu-id="6ec4c-112">int</span></span>  <br/> |<span data-ttu-id="6ec4c-113">Primary</span><span class="sxs-lookup"><span data-stu-id="6ec4c-113">Primary</span></span>  <br/> |<span data-ttu-id="6ec4c-114">Уникальный номер, идентифицирующий сервер.</span><span class="sxs-lookup"><span data-stu-id="6ec4c-114">Unique number identifying the server.</span></span>  <br/> |
|<span data-ttu-id="6ec4c-115">**Фкднорип**</span><span class="sxs-lookup"><span data-stu-id="6ec4c-115">**FQDNOrIP**</span></span> <br/> |<span data-ttu-id="6ec4c-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="6ec4c-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="6ec4c-117">индекса</span><span class="sxs-lookup"><span data-stu-id="6ec4c-117">index</span></span>  <br/> |<span data-ttu-id="6ec4c-118">Строка MAC-адреса.</span><span class="sxs-lookup"><span data-stu-id="6ec4c-118">MAC address string.</span></span>  <br/> |
|<span data-ttu-id="6ec4c-119">**ServerType**</span><span class="sxs-lookup"><span data-stu-id="6ec4c-119">**ServerType**</span></span> <br/> |<span data-ttu-id="6ec4c-120">целое</span><span class="sxs-lookup"><span data-stu-id="6ec4c-120">int</span></span>  <br/> |<span data-ttu-id="6ec4c-121">Другом</span><span class="sxs-lookup"><span data-stu-id="6ec4c-121">Foreign</span></span>  <br/> |<span data-ttu-id="6ec4c-122">1: сервер исправлений</span><span class="sxs-lookup"><span data-stu-id="6ec4c-122">1: Mediation Server</span></span>  <br/> <span data-ttu-id="6ec4c-123">2: Server16394 конференции/V-service32769: шлюз</span><span class="sxs-lookup"><span data-stu-id="6ec4c-123">2: A/V Conferencing Server16394: A/V Edge service32769: Gateway</span></span>  <br/> |
|<span data-ttu-id="6ec4c-124">**Пулнаме**</span><span class="sxs-lookup"><span data-stu-id="6ec4c-124">**PoolName**</span></span> <br/> |<span data-ttu-id="6ec4c-125">nvarchar (512)</span><span class="sxs-lookup"><span data-stu-id="6ec4c-125">nvarchar(512)</span></span>  <br/> ||<span data-ttu-id="6ec4c-126">Группа, к которой принадлежит сервер.</span><span class="sxs-lookup"><span data-stu-id="6ec4c-126">Pool the server belongs to.</span></span> <span data-ttu-id="6ec4c-127">Применимо только для сервера конференц-связи A/V.</span><span class="sxs-lookup"><span data-stu-id="6ec4c-127">Only applicable for the A/V Conferencing Server.</span></span>  <br/> |
|<span data-ttu-id="6ec4c-128">**Некступдатетс**</span><span class="sxs-lookup"><span data-stu-id="6ec4c-128">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="6ec4c-129">datetime</span><span class="sxs-lookup"><span data-stu-id="6ec4c-129">datetime</span></span>  <br/> ||<span data-ttu-id="6ec4c-130">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="6ec4c-130">For internal use only.</span></span>  <br/> |
   

