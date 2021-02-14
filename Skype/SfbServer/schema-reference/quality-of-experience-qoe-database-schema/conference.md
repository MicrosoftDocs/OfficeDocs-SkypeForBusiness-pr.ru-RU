---
title: Таблица Conference
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
ms.assetid: 2a2c327c-4719-42dc-a3bb-6dbc0864d9af
description: Таблица Conference является вспомогательной. Каждая запись представляет одну конференцию или одноранговый сеанс.
ms.openlocfilehash: 3840ad9bb4f9b0ff0aea5068c73d307d5bd0cf5e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802789"
---
# <a name="conference-table"></a><span data-ttu-id="882dc-104">Таблица Conference</span><span class="sxs-lookup"><span data-stu-id="882dc-104">Conference table</span></span>
 
<span data-ttu-id="882dc-p102">Таблица Conference является вспомогательной. Каждая запись представляет одну конференцию или одноранговый сеанс.</span><span class="sxs-lookup"><span data-stu-id="882dc-p102">The Conference table is a supporting table. Each record represents one conference or peer-to-peer session.</span></span>
  
|<span data-ttu-id="882dc-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="882dc-107">**Column**</span></span>|<span data-ttu-id="882dc-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="882dc-108">**Data Type**</span></span>|<span data-ttu-id="882dc-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="882dc-109">**Key/Index**</span></span>|<span data-ttu-id="882dc-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="882dc-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="882dc-111">**ConferenceKey**</span><span class="sxs-lookup"><span data-stu-id="882dc-111">**ConferenceKey**</span></span> <br/> |<span data-ttu-id="882dc-112">int</span><span class="sxs-lookup"><span data-stu-id="882dc-112">int</span></span>  <br/> |<span data-ttu-id="882dc-113">Primary</span><span class="sxs-lookup"><span data-stu-id="882dc-113">Primary</span></span>  <br/> |<span data-ttu-id="882dc-114">Уникальный номер, идентифицирующий эту запись конференции.</span><span class="sxs-lookup"><span data-stu-id="882dc-114">Unique number identifying this conference record.</span></span>  <br/> |
|<span data-ttu-id="882dc-115">**ConfURI**</span><span class="sxs-lookup"><span data-stu-id="882dc-115">**ConfURI**</span></span> <br/> |<span data-ttu-id="882dc-116">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="882dc-116">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="882dc-117">unique</span><span class="sxs-lookup"><span data-stu-id="882dc-117">unique</span></span>  <br/> |<span data-ttu-id="882dc-118">URI для конференции или DialogID для однорангового сеанса.</span><span class="sxs-lookup"><span data-stu-id="882dc-118">Conference URI if this is a conference, or DialogID if this is a peer-to-peer session.</span></span>  <br/> |
|<span data-ttu-id="882dc-119">**Контрольная сумма**</span><span class="sxs-lookup"><span data-stu-id="882dc-119">**Checksum**</span></span> <br/> |<span data-ttu-id="882dc-120">int</span><span class="sxs-lookup"><span data-stu-id="882dc-120">int</span></span>  <br/> |<span data-ttu-id="882dc-121">index</span><span class="sxs-lookup"><span data-stu-id="882dc-121">index</span></span>  <br/> |<span data-ttu-id="882dc-p103">Контрольная сумма URI конференции, предназначена для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="882dc-p103">Checksum of the conference URI. This is used internally.</span></span>  <br/> |
|<span data-ttu-id="882dc-124">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="882dc-124">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="882dc-125">datetime</span><span class="sxs-lookup"><span data-stu-id="882dc-125">datetime</span></span>  <br/> ||<span data-ttu-id="882dc-126">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="882dc-126">For internal use only.</span></span>  <br/> |
   

