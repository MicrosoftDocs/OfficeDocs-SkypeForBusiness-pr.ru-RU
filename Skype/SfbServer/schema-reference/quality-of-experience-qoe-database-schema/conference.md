---
title: Таблица Conference
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
ms.assetid: 2a2c327c-4719-42dc-a3bb-6dbc0864d9af
description: Таблица конференции — это вспомогательная таблица. Каждая запись представляет одну конференцию или одноранговый сеанс.
ms.openlocfilehash: 95e08861adaca2e76144f35037626e7b03afd962
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41810307"
---
# <a name="conference-table"></a><span data-ttu-id="13466-104">Таблица Conference</span><span class="sxs-lookup"><span data-stu-id="13466-104">Conference table</span></span>
 
<span data-ttu-id="13466-105">Таблица конференции — это вспомогательная таблица.</span><span class="sxs-lookup"><span data-stu-id="13466-105">The Conference table is a supporting table.</span></span> <span data-ttu-id="13466-106">Каждая запись представляет одну конференцию или одноранговый сеанс.</span><span class="sxs-lookup"><span data-stu-id="13466-106">Each record represents one conference or peer-to-peer session.</span></span>
  
|<span data-ttu-id="13466-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="13466-107">**Column**</span></span>|<span data-ttu-id="13466-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="13466-108">**Data Type**</span></span>|<span data-ttu-id="13466-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="13466-109">**Key/Index**</span></span>|<span data-ttu-id="13466-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="13466-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="13466-111">**конференцекэй**</span><span class="sxs-lookup"><span data-stu-id="13466-111">**ConferenceKey**</span></span> <br/> |<span data-ttu-id="13466-112">целое</span><span class="sxs-lookup"><span data-stu-id="13466-112">int</span></span>  <br/> |<span data-ttu-id="13466-113">Primary</span><span class="sxs-lookup"><span data-stu-id="13466-113">Primary</span></span>  <br/> |<span data-ttu-id="13466-114">Уникальный номер, идентифицирующий эту запись конференции.</span><span class="sxs-lookup"><span data-stu-id="13466-114">Unique number identifying this conference record.</span></span>  <br/> |
|<span data-ttu-id="13466-115">**конфури**</span><span class="sxs-lookup"><span data-stu-id="13466-115">**ConfURI**</span></span> <br/> |<span data-ttu-id="13466-116">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="13466-116">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="13466-117">повторя</span><span class="sxs-lookup"><span data-stu-id="13466-117">unique</span></span>  <br/> |<span data-ttu-id="13466-118">Универсальный код ресурса (URI) для Конференции, если это конференция, или Диалогид, если это одноранговый сеанс.</span><span class="sxs-lookup"><span data-stu-id="13466-118">Conference URI if this is a conference, or DialogID if this is a peer-to-peer session.</span></span>  <br/> |
|<span data-ttu-id="13466-119">**Счет**</span><span class="sxs-lookup"><span data-stu-id="13466-119">**Checksum**</span></span> <br/> |<span data-ttu-id="13466-120">целое</span><span class="sxs-lookup"><span data-stu-id="13466-120">int</span></span>  <br/> |<span data-ttu-id="13466-121">индекса</span><span class="sxs-lookup"><span data-stu-id="13466-121">index</span></span>  <br/> |<span data-ttu-id="13466-122">Контрольная сумма URI конференции.</span><span class="sxs-lookup"><span data-stu-id="13466-122">Checksum of the conference URI.</span></span> <span data-ttu-id="13466-123">Используется для внутренних целей.</span><span class="sxs-lookup"><span data-stu-id="13466-123">This is used internally.</span></span>  <br/> |
|<span data-ttu-id="13466-124">**некступдатетс**</span><span class="sxs-lookup"><span data-stu-id="13466-124">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="13466-125">datetime</span><span class="sxs-lookup"><span data-stu-id="13466-125">datetime</span></span>  <br/> ||<span data-ttu-id="13466-126">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="13466-126">For internal use only.</span></span>  <br/> |
   

