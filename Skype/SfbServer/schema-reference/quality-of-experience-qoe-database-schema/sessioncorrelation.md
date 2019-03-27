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
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30884665"
---
# <a name="sessioncorrelation-table"></a><span data-ttu-id="478de-104">Таблица SessionCorrelation</span><span class="sxs-lookup"><span data-stu-id="478de-104">SessionCorrelation table</span></span>
 
<span data-ttu-id="478de-105">Таблица sessioncorrelation представляет собой вспомогательную таблицу.</span><span class="sxs-lookup"><span data-stu-id="478de-105">The SessionCorrelation table is a supporting table.</span></span> <span data-ttu-id="478de-106">Каждая запись представляет один CorrelationID, который используется для сопоставления нескольких сеансов.</span><span class="sxs-lookup"><span data-stu-id="478de-106">Each record represents one CorrelationID which is used to correlate multiple sessions.</span></span> 
  
|<span data-ttu-id="478de-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="478de-107">**Column**</span></span>|<span data-ttu-id="478de-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="478de-108">**Data Type**</span></span>|<span data-ttu-id="478de-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="478de-109">**Key/Index**</span></span>|<span data-ttu-id="478de-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="478de-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="478de-111">**Контрольная сумма**</span><span class="sxs-lookup"><span data-stu-id="478de-111">**Checksum**</span></span> <br/> |<span data-ttu-id="478de-112">целое</span><span class="sxs-lookup"><span data-stu-id="478de-112">int</span></span>  <br/> |||
|<span data-ttu-id="478de-113">**CorrelationKey**</span><span class="sxs-lookup"><span data-stu-id="478de-113">**CorrelationKey**</span></span> <br/> |<span data-ttu-id="478de-114">целое</span><span class="sxs-lookup"><span data-stu-id="478de-114">int</span></span>  <br/> |<span data-ttu-id="478de-115">Primary</span><span class="sxs-lookup"><span data-stu-id="478de-115">Primary</span></span>  <br/> |<span data-ttu-id="478de-116">Уникальный номер, идентифицирующий этот / видеоконференций.</span><span class="sxs-lookup"><span data-stu-id="478de-116">Unique number identifying this A/V Conferencing Server.</span></span>  <br/> |
|<span data-ttu-id="478de-117">**CorrelationID**</span><span class="sxs-lookup"><span data-stu-id="478de-117">**CorrelationID**</span></span> <br/> |<span data-ttu-id="478de-118">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="478de-118">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="478de-119">Уникальный</span><span class="sxs-lookup"><span data-stu-id="478de-119">Unique</span></span>  <br/> |<span data-ttu-id="478de-120">Сопоставленным сеансам будет иметь тот же идентификатор корреляции.</span><span class="sxs-lookup"><span data-stu-id="478de-120">Sessions that are correlated will have the same correlation ID.</span></span>  <br/> |
|<span data-ttu-id="478de-121">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="478de-121">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="478de-122">datetime</span><span class="sxs-lookup"><span data-stu-id="478de-122">datetime</span></span>  <br/> | <br/> |<span data-ttu-id="478de-123">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="478de-123">For internal use only.</span></span>  <br/> |
   

