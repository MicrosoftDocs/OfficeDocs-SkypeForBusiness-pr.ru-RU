---
title: Таблица ErrorCategory в Skype для бизнеса Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 0fde3b73-9a2f-44dd-b8dc-6df512303ff1
description: 'Таблица ErrorCategory содержит удобное имя для каждой диагностической классификации Skype для бизнеса Server 2015. По умолчанию Skype для бизнеса Server 2015 использует следующие классификации:'
ms.openlocfilehash: ca3719f6d284cf715be1a87b1c7a5dc04ae84b04
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813149"
---
# <a name="errorcategory-table-in-skype-for-business-server-2015"></a><span data-ttu-id="35af6-104">Таблица ErrorCategory в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="35af6-104">ErrorCategory table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="35af6-105">Таблица ErrorCategory содержит удобное имя для каждой диагностической классификации Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="35af6-105">The ErrorCategory table contains the friendly name for each Skype for Business Server 2015 diagnostic classification.</span></span> <span data-ttu-id="35af6-106">По умолчанию Skype для бизнеса Server 2015 использует следующие классификации:</span><span class="sxs-lookup"><span data-stu-id="35af6-106">By default, Skype for Business Server 2015 uses the following classifications:</span></span>
  
- <span data-ttu-id="35af6-107">0 — успешно</span><span class="sxs-lookup"><span data-stu-id="35af6-107">0 -- Success</span></span>
    
- <span data-ttu-id="35af6-108">1 — ожидаемый сбой</span><span class="sxs-lookup"><span data-stu-id="35af6-108">1 -- Expected failure</span></span>
    
- <span data-ttu-id="35af6-109">2 — неожиданный сбой</span><span class="sxs-lookup"><span data-stu-id="35af6-109">2 - Unexpected failure</span></span>
    
<span data-ttu-id="35af6-110">Эта таблица была представлена в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="35af6-110">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="35af6-111">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="35af6-111">**Column**</span></span>|<span data-ttu-id="35af6-112">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="35af6-112">**Data Type**</span></span>|<span data-ttu-id="35af6-113">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="35af6-113">**Key/Index**</span></span>|<span data-ttu-id="35af6-114">**Details**</span><span class="sxs-lookup"><span data-stu-id="35af6-114">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="35af6-115">**CategoryId**</span><span class="sxs-lookup"><span data-stu-id="35af6-115">**CategoryId**</span></span> <br/> |<span data-ttu-id="35af6-116">tinyint</span><span class="sxs-lookup"><span data-stu-id="35af6-116">tinyint</span></span>  <br/> |<span data-ttu-id="35af6-117">Primary</span><span class="sxs-lookup"><span data-stu-id="35af6-117">Primary</span></span>  <br/> |<span data-ttu-id="35af6-118">Уникальный идентификатор для классификации.</span><span class="sxs-lookup"><span data-stu-id="35af6-118">Unique identifier for the classification.</span></span>  <br/> |
|<span data-ttu-id="35af6-119">**Название**</span><span class="sxs-lookup"><span data-stu-id="35af6-119">**Name**</span></span> <br/> |<span data-ttu-id="35af6-120">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="35af6-120">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="35af6-p103">Значение и понятное имя, назначенные классификации. Допускаются следующие значения:</span><span class="sxs-lookup"><span data-stu-id="35af6-p103">Value and friendly name assigned to the classification. Allowed values are:</span></span> <br/>  <span data-ttu-id="35af6-123">0 — успешно</span><span class="sxs-lookup"><span data-stu-id="35af6-123">0 -- Success</span></span> <br/>  <span data-ttu-id="35af6-124">1 — ожидаемый сбой</span><span class="sxs-lookup"><span data-stu-id="35af6-124">1 -- Expected failure</span></span> <br/>  <span data-ttu-id="35af6-125">2 — неожиданный сбой</span><span class="sxs-lookup"><span data-stu-id="35af6-125">2 - Unexpected failure</span></span> <br/> |
   

