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
# <a name="server-table"></a><span data-ttu-id="bcfbc-104">Таблица Server</span><span class="sxs-lookup"><span data-stu-id="bcfbc-104">Server table</span></span>
 
<span data-ttu-id="bcfbc-p102">Таблица Server является таблицей поддержки. Каждая запись в этой таблице представляет один сервер.</span><span class="sxs-lookup"><span data-stu-id="bcfbc-p102">The Server table is a supporting table. Each record represents one server.</span></span> 
  
|<span data-ttu-id="bcfbc-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="bcfbc-107">**Column**</span></span>|<span data-ttu-id="bcfbc-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="bcfbc-108">**Data Type**</span></span>|<span data-ttu-id="bcfbc-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="bcfbc-109">**Key/Index**</span></span>|<span data-ttu-id="bcfbc-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="bcfbc-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="bcfbc-111">**ServerKey**</span><span class="sxs-lookup"><span data-stu-id="bcfbc-111">**ServerKey**</span></span> <br/> |<span data-ttu-id="bcfbc-112">int</span><span class="sxs-lookup"><span data-stu-id="bcfbc-112">int</span></span>  <br/> |<span data-ttu-id="bcfbc-113">Primary</span><span class="sxs-lookup"><span data-stu-id="bcfbc-113">Primary</span></span>  <br/> |<span data-ttu-id="bcfbc-114">Уникальный номер, идентифицирующий сервер.</span><span class="sxs-lookup"><span data-stu-id="bcfbc-114">Unique number identifying the server.</span></span>  <br/> |
|<span data-ttu-id="bcfbc-115">**FQDNOrIP**</span><span class="sxs-lookup"><span data-stu-id="bcfbc-115">**FQDNOrIP**</span></span> <br/> |<span data-ttu-id="bcfbc-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="bcfbc-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="bcfbc-117">index</span><span class="sxs-lookup"><span data-stu-id="bcfbc-117">index</span></span>  <br/> |<span data-ttu-id="bcfbc-118">Строка MAC-адреса.</span><span class="sxs-lookup"><span data-stu-id="bcfbc-118">MAC address string.</span></span>  <br/> |
|<span data-ttu-id="bcfbc-119">**ServerType**</span><span class="sxs-lookup"><span data-stu-id="bcfbc-119">**ServerType**</span></span> <br/> |<span data-ttu-id="bcfbc-120">int</span><span class="sxs-lookup"><span data-stu-id="bcfbc-120">int</span></span>  <br/> |<span data-ttu-id="bcfbc-121">Внешняя</span><span class="sxs-lookup"><span data-stu-id="bcfbc-121">Foreign</span></span>  <br/> |<span data-ttu-id="bcfbc-122">1: сервер-посредник</span><span class="sxs-lookup"><span data-stu-id="bcfbc-122">1: Mediation Server</span></span>  <br/> <span data-ttu-id="bcfbc-123">2: сервер аудио- и видеоконференций 16394: пограничная служба аудио- и видеосвязи 32769: шлюз</span><span class="sxs-lookup"><span data-stu-id="bcfbc-123">2: A/V Conferencing Server16394: A/V Edge service32769: Gateway</span></span>  <br/> |
|<span data-ttu-id="bcfbc-124">**PoolName**</span><span class="sxs-lookup"><span data-stu-id="bcfbc-124">**PoolName**</span></span> <br/> |<span data-ttu-id="bcfbc-125">nvarchar(512)</span><span class="sxs-lookup"><span data-stu-id="bcfbc-125">nvarchar(512)</span></span>  <br/> ||<span data-ttu-id="bcfbc-p103">Пул, которому принадлежит сервер. Применяется только для серверов аудио- и видеоконференций.</span><span class="sxs-lookup"><span data-stu-id="bcfbc-p103">Pool the server belongs to. Only applicable for the A/V Conferencing Server.</span></span>  <br/> |
|<span data-ttu-id="bcfbc-128">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="bcfbc-128">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="bcfbc-129">datetime</span><span class="sxs-lookup"><span data-stu-id="bcfbc-129">datetime</span></span>  <br/> ||<span data-ttu-id="bcfbc-130">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="bcfbc-130">For internal use only.</span></span>  <br/> |
   

