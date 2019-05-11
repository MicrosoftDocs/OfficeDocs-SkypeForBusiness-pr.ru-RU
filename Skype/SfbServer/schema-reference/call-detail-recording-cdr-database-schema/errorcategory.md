---
title: Таблица ErrorCategory в Скайп для Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0fde3b73-9a2f-44dd-b8dc-6df512303ff1
description: 'Таблица ErrorCategory содержит понятное имя для каждого Скайп для диагностики классификации Business Server 2015. По умолчанию Скайп для Business Server 2015 используются следующих категорий:'
ms.openlocfilehash: b6226396302353b815138b41b7c19f170a0d6b4d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901089"
---
# <a name="errorcategory-table-in-skype-for-business-server-2015"></a><span data-ttu-id="1623a-104">Таблица ErrorCategory в Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="1623a-104">ErrorCategory table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="1623a-105">Таблица ErrorCategory содержит понятное имя для каждого Скайп для диагностики классификации Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="1623a-105">The ErrorCategory table contains the friendly name for each Skype for Business Server 2015 diagnostic classification.</span></span> <span data-ttu-id="1623a-106">По умолчанию Скайп для Business Server 2015 используются следующих категорий:</span><span class="sxs-lookup"><span data-stu-id="1623a-106">By default, Skype for Business Server 2015 uses the following classifications:</span></span>
  
- <span data-ttu-id="1623a-107">0 — успешное завершение</span><span class="sxs-lookup"><span data-stu-id="1623a-107">0 -- Success</span></span>
    
- <span data-ttu-id="1623a-108">1 — ожидаемый сбой</span><span class="sxs-lookup"><span data-stu-id="1623a-108">1 -- Expected failure</span></span>
    
- <span data-ttu-id="1623a-109">2 — неожиданный сбой</span><span class="sxs-lookup"><span data-stu-id="1623a-109">2 - Unexpected failure</span></span>
    
<span data-ttu-id="1623a-110">Эта таблица была введена в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1623a-110">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="1623a-111">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="1623a-111">**Column**</span></span>|<span data-ttu-id="1623a-112">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="1623a-112">**Data Type**</span></span>|<span data-ttu-id="1623a-113">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="1623a-113">**Key/Index**</span></span>|<span data-ttu-id="1623a-114">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="1623a-114">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="1623a-115">**Идентификатор категории**</span><span class="sxs-lookup"><span data-stu-id="1623a-115">**CategoryId**</span></span> <br/> |<span data-ttu-id="1623a-116">tinyint</span><span class="sxs-lookup"><span data-stu-id="1623a-116">tinyint</span></span>  <br/> |<span data-ttu-id="1623a-117">Primary</span><span class="sxs-lookup"><span data-stu-id="1623a-117">Primary</span></span>  <br/> |<span data-ttu-id="1623a-118">Уникальный идентификатор для классификации.</span><span class="sxs-lookup"><span data-stu-id="1623a-118">Unique identifier for the classification.</span></span>  <br/> |
|<span data-ttu-id="1623a-119">**Имя**.</span><span class="sxs-lookup"><span data-stu-id="1623a-119">**Name**</span></span> <br/> |<span data-ttu-id="1623a-120">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="1623a-120">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="1623a-121">Значение и понятное имя, присвоенное классификации.</span><span class="sxs-lookup"><span data-stu-id="1623a-121">Value and friendly name assigned to the classification.</span></span> <span data-ttu-id="1623a-122">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="1623a-122">Allowed values are:</span></span> <br/>  <span data-ttu-id="1623a-123">0 — успешное завершение</span><span class="sxs-lookup"><span data-stu-id="1623a-123">0 -- Success</span></span> <br/>  <span data-ttu-id="1623a-124">1 — ожидаемый сбой</span><span class="sxs-lookup"><span data-stu-id="1623a-124">1 -- Expected failure</span></span> <br/>  <span data-ttu-id="1623a-125">2 — неожиданный сбой</span><span class="sxs-lookup"><span data-stu-id="1623a-125">2 - Unexpected failure</span></span> <br/> |
   

