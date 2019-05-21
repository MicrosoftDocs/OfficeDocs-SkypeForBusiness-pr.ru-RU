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
localization_priority: Normal
ms.assetid: 2a2c327c-4719-42dc-a3bb-6dbc0864d9af
description: Таблица конференции — это вспомогательная таблица. Каждая запись представляет одну конференцию или одноранговый сеанс.
ms.openlocfilehash: 61e9667d235ed9ab8f3696f55e676bfc60ab69e3
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295015"
---
# <a name="conference-table"></a><span data-ttu-id="7c974-104">Таблица Conference</span><span class="sxs-lookup"><span data-stu-id="7c974-104">Conference table</span></span>
 
<span data-ttu-id="7c974-105">Таблица конференции — это вспомогательная таблица.</span><span class="sxs-lookup"><span data-stu-id="7c974-105">The Conference table is a supporting table.</span></span> <span data-ttu-id="7c974-106">Каждая запись представляет одну конференцию или одноранговый сеанс.</span><span class="sxs-lookup"><span data-stu-id="7c974-106">Each record represents one conference or peer-to-peer session.</span></span>
  
|<span data-ttu-id="7c974-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="7c974-107">**Column**</span></span>|<span data-ttu-id="7c974-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="7c974-108">**Data Type**</span></span>|<span data-ttu-id="7c974-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="7c974-109">**Key/Index**</span></span>|<span data-ttu-id="7c974-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="7c974-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7c974-111">**Конференцекэй**</span><span class="sxs-lookup"><span data-stu-id="7c974-111">**ConferenceKey**</span></span> <br/> |<span data-ttu-id="7c974-112">целое</span><span class="sxs-lookup"><span data-stu-id="7c974-112">int</span></span>  <br/> |<span data-ttu-id="7c974-113">Primary</span><span class="sxs-lookup"><span data-stu-id="7c974-113">Primary</span></span>  <br/> |<span data-ttu-id="7c974-114">Уникальный номер, идентифицирующий эту запись конференции.</span><span class="sxs-lookup"><span data-stu-id="7c974-114">Unique number identifying this conference record.</span></span>  <br/> |
|<span data-ttu-id="7c974-115">**Конфури**</span><span class="sxs-lookup"><span data-stu-id="7c974-115">**ConfURI**</span></span> <br/> |<span data-ttu-id="7c974-116">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="7c974-116">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="7c974-117">повторя</span><span class="sxs-lookup"><span data-stu-id="7c974-117">unique</span></span>  <br/> |<span data-ttu-id="7c974-118">Универсальный код ресурса (URI) для Конференции, если это конференция, или Диалогид, если это одноранговый сеанс.</span><span class="sxs-lookup"><span data-stu-id="7c974-118">Conference URI if this is a conference, or DialogID if this is a peer-to-peer session.</span></span>  <br/> |
|<span data-ttu-id="7c974-119">**Счет**</span><span class="sxs-lookup"><span data-stu-id="7c974-119">**Checksum**</span></span> <br/> |<span data-ttu-id="7c974-120">целое</span><span class="sxs-lookup"><span data-stu-id="7c974-120">int</span></span>  <br/> |<span data-ttu-id="7c974-121">индекса</span><span class="sxs-lookup"><span data-stu-id="7c974-121">index</span></span>  <br/> |<span data-ttu-id="7c974-122">Контрольная сумма URI конференции.</span><span class="sxs-lookup"><span data-stu-id="7c974-122">Checksum of the conference URI.</span></span> <span data-ttu-id="7c974-123">Используется для внутренних целей.</span><span class="sxs-lookup"><span data-stu-id="7c974-123">This is used internally.</span></span>  <br/> |
|<span data-ttu-id="7c974-124">**Некступдатетс**</span><span class="sxs-lookup"><span data-stu-id="7c974-124">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="7c974-125">datetime</span><span class="sxs-lookup"><span data-stu-id="7c974-125">datetime</span></span>  <br/> ||<span data-ttu-id="7c974-126">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="7c974-126">For internal use only.</span></span>  <br/> |
   

