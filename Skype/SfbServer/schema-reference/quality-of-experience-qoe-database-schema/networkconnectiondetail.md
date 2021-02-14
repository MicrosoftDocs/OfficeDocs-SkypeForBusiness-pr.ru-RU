---
title: Таблица NetworkConnectionDetail
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
ms.assetid: b48cc9a6-5232-48b5-bd20-53b68229336b
description: В таблице NetworkConnectionDetail сопоставляются типы сетевых подключений с идентификаторами сетевых подключений, используемых в базе данных качества взаимодействия. Эта таблица была представлена в Microsoft Lync Server 2013.
ms.openlocfilehash: 2e03e7935370e71a8070ed1882f61ac5480f312e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806309"
---
# <a name="networkconnectiondetail-table"></a><span data-ttu-id="f31ca-104">Таблица NetworkConnectionDetail</span><span class="sxs-lookup"><span data-stu-id="f31ca-104">NetworkConnectionDetail table</span></span>
 
<span data-ttu-id="f31ca-105">В таблице NetworkConnectionDetail сопоставляются типы сетевых подключений с идентификаторами сетевых подключений, используемых в базе данных качества взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="f31ca-105">The NetworkConnectionDetail table maps network connection types to the network connection identifiers used elsewhere in the Quality of Experience database.</span></span> <span data-ttu-id="f31ca-106">Эта таблица была представлена в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f31ca-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="f31ca-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="f31ca-107">**Column**</span></span>|<span data-ttu-id="f31ca-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="f31ca-108">**Data Type**</span></span>|<span data-ttu-id="f31ca-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="f31ca-109">**Key/Index**</span></span>|<span data-ttu-id="f31ca-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="f31ca-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f31ca-111">**NetworkConnectionDetailKey**</span><span class="sxs-lookup"><span data-stu-id="f31ca-111">**NetworkConnectionDetailKey**</span></span> <br/> |<span data-ttu-id="f31ca-112">tinyint</span><span class="sxs-lookup"><span data-stu-id="f31ca-112">tinyint</span></span>  <br/> |<span data-ttu-id="f31ca-113">Primary</span><span class="sxs-lookup"><span data-stu-id="f31ca-113">Primary</span></span>  <br/> |<span data-ttu-id="f31ca-114">Уникальный идентификатор типа сетевого подключения.</span><span class="sxs-lookup"><span data-stu-id="f31ca-114">Unique identifier for the network connection type.</span></span>  <br/> |
|<span data-ttu-id="f31ca-115">**NetworkConnectionDetail**</span><span class="sxs-lookup"><span data-stu-id="f31ca-115">**NetworkConnectionDetail**</span></span> <br/> |<span data-ttu-id="f31ca-116">varchar(256)</span><span class="sxs-lookup"><span data-stu-id="f31ca-116">varchar(256)</span></span>  <br/> |<span data-ttu-id="f31ca-117">Уникальные</span><span class="sxs-lookup"><span data-stu-id="f31ca-117">Unique</span></span>  <br/> |<span data-ttu-id="f31ca-p103">Тип сетевого подключения, который соответствует значению NetworkConnectionDetailKey. Допускаются следующие значения:</span><span class="sxs-lookup"><span data-stu-id="f31ca-p103">Network connection type that corresponds to the NetworkConnectionDetailKey. Allowed values are:</span></span>  <br/> <span data-ttu-id="f31ca-120">0 — проводное</span><span class="sxs-lookup"><span data-stu-id="f31ca-120">0 -- Wired</span></span>  <br/> <span data-ttu-id="f31ca-121">1 — беспроводное</span><span class="sxs-lookup"><span data-stu-id="f31ca-121">1 -- WiFi</span></span>  <br/> <span data-ttu-id="f31ca-122">2 — Ethernet</span><span class="sxs-lookup"><span data-stu-id="f31ca-122">2 -- Ethernet</span></span>  <br/> <span data-ttu-id="f31ca-123">3 — MobileBB</span><span class="sxs-lookup"><span data-stu-id="f31ca-123">3 -- MobileBB</span></span>  <br/> <span data-ttu-id="f31ca-124">4 — другие</span><span class="sxs-lookup"><span data-stu-id="f31ca-124">4 -- Other</span></span>  <br/> <span data-ttu-id="f31ca-125">5 — туннель</span><span class="sxs-lookup"><span data-stu-id="f31ca-125">5 -- Tunnel</span></span>  <br/> |
   

