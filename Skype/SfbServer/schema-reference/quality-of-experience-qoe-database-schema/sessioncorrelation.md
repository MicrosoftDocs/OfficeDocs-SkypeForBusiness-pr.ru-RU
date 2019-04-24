---
title: Таблица SessionCorrelation
ms.reviewer: ''
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
ms.openlocfilehash: 8c41ab5c52c6b4d06a3c3953e8d969488680e8d3
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212118"
---
# <a name="sessioncorrelation-table"></a><span data-ttu-id="4b8b2-104">Таблица SessionCorrelation</span><span class="sxs-lookup"><span data-stu-id="4b8b2-104">SessionCorrelation table</span></span>
 
<span data-ttu-id="4b8b2-105">Таблица sessioncorrelation представляет собой вспомогательную таблицу.</span><span class="sxs-lookup"><span data-stu-id="4b8b2-105">The SessionCorrelation table is a supporting table.</span></span> <span data-ttu-id="4b8b2-106">Каждая запись представляет один CorrelationID, который используется для сопоставления нескольких сеансов.</span><span class="sxs-lookup"><span data-stu-id="4b8b2-106">Each record represents one CorrelationID which is used to correlate multiple sessions.</span></span> 
  
|<span data-ttu-id="4b8b2-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="4b8b2-107">**Column**</span></span>|<span data-ttu-id="4b8b2-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="4b8b2-108">**Data Type**</span></span>|<span data-ttu-id="4b8b2-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="4b8b2-109">**Key/Index**</span></span>|<span data-ttu-id="4b8b2-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="4b8b2-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4b8b2-111">**Контрольная сумма**</span><span class="sxs-lookup"><span data-stu-id="4b8b2-111">**Checksum**</span></span> <br/> |<span data-ttu-id="4b8b2-112">целое</span><span class="sxs-lookup"><span data-stu-id="4b8b2-112">int</span></span>  <br/> |||
|<span data-ttu-id="4b8b2-113">**CorrelationKey**</span><span class="sxs-lookup"><span data-stu-id="4b8b2-113">**CorrelationKey**</span></span> <br/> |<span data-ttu-id="4b8b2-114">целое</span><span class="sxs-lookup"><span data-stu-id="4b8b2-114">int</span></span>  <br/> |<span data-ttu-id="4b8b2-115">Primary</span><span class="sxs-lookup"><span data-stu-id="4b8b2-115">Primary</span></span>  <br/> |<span data-ttu-id="4b8b2-116">Уникальный номер, идентифицирующий этот / видеоконференций.</span><span class="sxs-lookup"><span data-stu-id="4b8b2-116">Unique number identifying this A/V Conferencing Server.</span></span>  <br/> |
|<span data-ttu-id="4b8b2-117">**CorrelationID**</span><span class="sxs-lookup"><span data-stu-id="4b8b2-117">**CorrelationID**</span></span> <br/> |<span data-ttu-id="4b8b2-118">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="4b8b2-118">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="4b8b2-119">Уникальный</span><span class="sxs-lookup"><span data-stu-id="4b8b2-119">Unique</span></span>  <br/> |<span data-ttu-id="4b8b2-120">Сопоставленным сеансам будет иметь тот же идентификатор корреляции.</span><span class="sxs-lookup"><span data-stu-id="4b8b2-120">Sessions that are correlated will have the same correlation ID.</span></span>  <br/> |
|<span data-ttu-id="4b8b2-121">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="4b8b2-121">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="4b8b2-122">datetime</span><span class="sxs-lookup"><span data-stu-id="4b8b2-122">datetime</span></span>  <br/> | <br/> |<span data-ttu-id="4b8b2-123">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="4b8b2-123">For internal use only.</span></span>  <br/> |
   

