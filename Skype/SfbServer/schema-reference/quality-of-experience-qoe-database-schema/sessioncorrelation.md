---
title: Таблица SessionCorrelation
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 041705e1-7290-464f-95f8-96256cfa2e3e
description: Таблица sessioncorrelation представляет собой вспомогательную таблицу. Каждая запись представляет один CorrelationID, который используется для сопоставления нескольких сеансов.
ms.openlocfilehash: 8a9c9661b10548bf3ebf402aa4654fced2ca709b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="sessioncorrelation-table"></a><span data-ttu-id="09ee5-104">Таблица SessionCorrelation</span><span class="sxs-lookup"><span data-stu-id="09ee5-104">SessionCorrelation table</span></span>
 
<span data-ttu-id="09ee5-105">Таблица sessioncorrelation представляет собой вспомогательную таблицу.</span><span class="sxs-lookup"><span data-stu-id="09ee5-105">The SessionCorrelation table is a supporting table.</span></span> <span data-ttu-id="09ee5-106">Каждая запись представляет один CorrelationID, который используется для сопоставления нескольких сеансов.</span><span class="sxs-lookup"><span data-stu-id="09ee5-106">Each record represents one CorrelationID which is used to correlate multiple sessions.</span></span> 
  
|<span data-ttu-id="09ee5-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="09ee5-107">**Column**</span></span>|<span data-ttu-id="09ee5-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="09ee5-108">**Data Type**</span></span>|<span data-ttu-id="09ee5-109">**Ключ или индекс**</span><span class="sxs-lookup"><span data-stu-id="09ee5-109">**Key/Index**</span></span>|<span data-ttu-id="09ee5-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="09ee5-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="09ee5-111">**Контрольная сумма**</span><span class="sxs-lookup"><span data-stu-id="09ee5-111">**Checksum**</span></span> <br/> |<span data-ttu-id="09ee5-112">целое</span><span class="sxs-lookup"><span data-stu-id="09ee5-112">int</span></span>  <br/> |||
|<span data-ttu-id="09ee5-113">**CorrelationKey**</span><span class="sxs-lookup"><span data-stu-id="09ee5-113">**CorrelationKey**</span></span> <br/> |<span data-ttu-id="09ee5-114">целое</span><span class="sxs-lookup"><span data-stu-id="09ee5-114">int</span></span>  <br/> |<span data-ttu-id="09ee5-115">Primary</span><span class="sxs-lookup"><span data-stu-id="09ee5-115">Primary</span></span>  <br/> |<span data-ttu-id="09ee5-116">Уникальный номер, идентифицирующий этот / видеоконференций.</span><span class="sxs-lookup"><span data-stu-id="09ee5-116">Unique number identifying this A/V Conferencing Server.</span></span>  <br/> |
|<span data-ttu-id="09ee5-117">**CorrelationID**</span><span class="sxs-lookup"><span data-stu-id="09ee5-117">**CorrelationID**</span></span> <br/> |<span data-ttu-id="09ee5-118">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="09ee5-118">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="09ee5-119">Уникальный</span><span class="sxs-lookup"><span data-stu-id="09ee5-119">Unique</span></span>  <br/> |<span data-ttu-id="09ee5-120">Сопоставленным сеансам будет иметь тот же идентификатор корреляции.</span><span class="sxs-lookup"><span data-stu-id="09ee5-120">Sessions that are correlated will have the same correlation ID.</span></span>  <br/> |
|<span data-ttu-id="09ee5-121">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="09ee5-121">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="09ee5-122">datetime</span><span class="sxs-lookup"><span data-stu-id="09ee5-122">datetime</span></span>  <br/> | <br/> |<span data-ttu-id="09ee5-123">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="09ee5-123">For internal use only.</span></span>  <br/> |
   

