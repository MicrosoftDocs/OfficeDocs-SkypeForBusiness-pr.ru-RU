---
title: Таблица Server
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
ms.assetid: 9af89d08-d35a-48e8-b56d-6df292f973cc
description: Таблица Server является таблицей поддержки. Каждая запись в этой таблице представляет один сервер.
ms.openlocfilehash: 7f26ed9053c65acb8cfd2e586edbd77fdfa7472b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802709"
---
# <a name="server-table"></a><span data-ttu-id="5bb7b-104">Таблица Server</span><span class="sxs-lookup"><span data-stu-id="5bb7b-104">Server table</span></span>
 
<span data-ttu-id="5bb7b-p102">Таблица Server является таблицей поддержки. Каждая запись в этой таблице представляет один сервер.</span><span class="sxs-lookup"><span data-stu-id="5bb7b-p102">The Server table is a supporting table. Each record represents one server.</span></span> 
  
|<span data-ttu-id="5bb7b-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="5bb7b-107">**Column**</span></span>|<span data-ttu-id="5bb7b-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="5bb7b-108">**Data Type**</span></span>|<span data-ttu-id="5bb7b-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="5bb7b-109">**Key/Index**</span></span>|<span data-ttu-id="5bb7b-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="5bb7b-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="5bb7b-111">**ServerKey**</span><span class="sxs-lookup"><span data-stu-id="5bb7b-111">**ServerKey**</span></span> <br/> |<span data-ttu-id="5bb7b-112">int</span><span class="sxs-lookup"><span data-stu-id="5bb7b-112">int</span></span>  <br/> |<span data-ttu-id="5bb7b-113">Primary</span><span class="sxs-lookup"><span data-stu-id="5bb7b-113">Primary</span></span>  <br/> |<span data-ttu-id="5bb7b-114">Уникальный номер, идентифицирующий сервер.</span><span class="sxs-lookup"><span data-stu-id="5bb7b-114">Unique number identifying the server.</span></span>  <br/> |
|<span data-ttu-id="5bb7b-115">**FQDNOrIP**</span><span class="sxs-lookup"><span data-stu-id="5bb7b-115">**FQDNOrIP**</span></span> <br/> |<span data-ttu-id="5bb7b-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="5bb7b-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="5bb7b-117">index</span><span class="sxs-lookup"><span data-stu-id="5bb7b-117">index</span></span>  <br/> |<span data-ttu-id="5bb7b-118">Строка MAC-адреса.</span><span class="sxs-lookup"><span data-stu-id="5bb7b-118">MAC address string.</span></span>  <br/> |
|<span data-ttu-id="5bb7b-119">**ServerType**</span><span class="sxs-lookup"><span data-stu-id="5bb7b-119">**ServerType**</span></span> <br/> |<span data-ttu-id="5bb7b-120">int</span><span class="sxs-lookup"><span data-stu-id="5bb7b-120">int</span></span>  <br/> |<span data-ttu-id="5bb7b-121">Внешняя</span><span class="sxs-lookup"><span data-stu-id="5bb7b-121">Foreign</span></span>  <br/> |<span data-ttu-id="5bb7b-122">1: сервер-посредник</span><span class="sxs-lookup"><span data-stu-id="5bb7b-122">1: Mediation Server</span></span>  <br/> <span data-ttu-id="5bb7b-123">2: сервер аудио- и видеоконференций 16394: пограничная служба аудио- и видеосвязи 32769: шлюз</span><span class="sxs-lookup"><span data-stu-id="5bb7b-123">2: A/V Conferencing Server16394: A/V Edge service32769: Gateway</span></span>  <br/> |
|<span data-ttu-id="5bb7b-124">**PoolName**</span><span class="sxs-lookup"><span data-stu-id="5bb7b-124">**PoolName**</span></span> <br/> |<span data-ttu-id="5bb7b-125">nvarchar(512)</span><span class="sxs-lookup"><span data-stu-id="5bb7b-125">nvarchar(512)</span></span>  <br/> ||<span data-ttu-id="5bb7b-p103">Пул, которому принадлежит сервер. Применяется только для серверов аудио- и видеоконференций.</span><span class="sxs-lookup"><span data-stu-id="5bb7b-p103">Pool the server belongs to. Only applicable for the A/V Conferencing Server.</span></span>  <br/> |
|<span data-ttu-id="5bb7b-128">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="5bb7b-128">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="5bb7b-129">datetime</span><span class="sxs-lookup"><span data-stu-id="5bb7b-129">datetime</span></span>  <br/> ||<span data-ttu-id="5bb7b-130">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="5bb7b-130">For internal use only.</span></span>  <br/> |
   

