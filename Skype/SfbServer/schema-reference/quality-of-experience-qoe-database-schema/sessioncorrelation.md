---
title: Таблица SessionCorrelation
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
ms.assetid: 041705e1-7290-464f-95f8-96256cfa2e3e
description: Таблица SessionCorrelation является вспомогательной. Каждая запись представляет один CorrelationID, который используется для корреляции нескольких сеансов.
ms.openlocfilehash: 36b617517f3642a2150c72369db858eee62a4a87
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802659"
---
# <a name="sessioncorrelation-table"></a><span data-ttu-id="ef495-104">Таблица SessionCorrelation</span><span class="sxs-lookup"><span data-stu-id="ef495-104">SessionCorrelation table</span></span>
 
<span data-ttu-id="ef495-105">Таблица SessionCorrelation является вспомогательной.</span><span class="sxs-lookup"><span data-stu-id="ef495-105">The SessionCorrelation table is a supporting table.</span></span> <span data-ttu-id="ef495-106">Каждая запись представляет один CorrelationID, который используется для корреляции нескольких сеансов.</span><span class="sxs-lookup"><span data-stu-id="ef495-106">Each record represents one CorrelationID which is used to correlate multiple sessions.</span></span> 
  
|<span data-ttu-id="ef495-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="ef495-107">**Column**</span></span>|<span data-ttu-id="ef495-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="ef495-108">**Data Type**</span></span>|<span data-ttu-id="ef495-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="ef495-109">**Key/Index**</span></span>|<span data-ttu-id="ef495-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="ef495-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ef495-111">**Контрольная сумма**</span><span class="sxs-lookup"><span data-stu-id="ef495-111">**Checksum**</span></span> <br/> |<span data-ttu-id="ef495-112">int</span><span class="sxs-lookup"><span data-stu-id="ef495-112">int</span></span>  <br/> |||
|<span data-ttu-id="ef495-113">**CorrelationKey**</span><span class="sxs-lookup"><span data-stu-id="ef495-113">**CorrelationKey**</span></span> <br/> |<span data-ttu-id="ef495-114">int</span><span class="sxs-lookup"><span data-stu-id="ef495-114">int</span></span>  <br/> |<span data-ttu-id="ef495-115">Primary</span><span class="sxs-lookup"><span data-stu-id="ef495-115">Primary</span></span>  <br/> |<span data-ttu-id="ef495-116">Уникальный номер, идентифицирующий этот сервер A/V Conferencing Server.</span><span class="sxs-lookup"><span data-stu-id="ef495-116">Unique number identifying this A/V Conferencing Server.</span></span>  <br/> |
|<span data-ttu-id="ef495-117">**CorrelationID**</span><span class="sxs-lookup"><span data-stu-id="ef495-117">**CorrelationID**</span></span> <br/> |<span data-ttu-id="ef495-118">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="ef495-118">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="ef495-119">Уникальные</span><span class="sxs-lookup"><span data-stu-id="ef495-119">Unique</span></span>  <br/> |<span data-ttu-id="ef495-120">Связанные сеансы будут иметь одинаковый ид корреляции.</span><span class="sxs-lookup"><span data-stu-id="ef495-120">Sessions that are correlated will have the same correlation ID.</span></span>  <br/> |
|<span data-ttu-id="ef495-121">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="ef495-121">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="ef495-122">datetime</span><span class="sxs-lookup"><span data-stu-id="ef495-122">datetime</span></span>  <br/> | <br/> |<span data-ttu-id="ef495-123">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="ef495-123">For internal use only.</span></span>  <br/> |
   

