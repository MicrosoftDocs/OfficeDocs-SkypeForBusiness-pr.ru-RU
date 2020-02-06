---
title: Таблица Ерроркатегори в Skype для бизнеса Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 0fde3b73-9a2f-44dd-b8dc-6df512303ff1
description: 'В таблице Ерроркатегори содержится понятное имя для каждой классификации диагностики Skype для Business Server 2015. По умолчанию в Skype для бизнеса Server 2015 используются следующие классификации:'
ms.openlocfilehash: f3ad3f86a382b900d53c5e86140a46d7f32ca1c1
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815257"
---
# <a name="errorcategory-table-in-skype-for-business-server-2015"></a><span data-ttu-id="9d386-104">Таблица Ерроркатегори в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="9d386-104">ErrorCategory table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="9d386-105">В таблице Ерроркатегори содержится понятное имя для каждой классификации диагностики Skype для Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="9d386-105">The ErrorCategory table contains the friendly name for each Skype for Business Server 2015 diagnostic classification.</span></span> <span data-ttu-id="9d386-106">По умолчанию в Skype для бизнеса Server 2015 используются следующие классификации:</span><span class="sxs-lookup"><span data-stu-id="9d386-106">By default, Skype for Business Server 2015 uses the following classifications:</span></span>
  
- <span data-ttu-id="9d386-107">0 — успех</span><span class="sxs-lookup"><span data-stu-id="9d386-107">0 -- Success</span></span>
    
- <span data-ttu-id="9d386-108">1 — ожидаемый сбой</span><span class="sxs-lookup"><span data-stu-id="9d386-108">1 -- Expected failure</span></span>
    
- <span data-ttu-id="9d386-109">2 — непредвиденный сбой</span><span class="sxs-lookup"><span data-stu-id="9d386-109">2 - Unexpected failure</span></span>
    
<span data-ttu-id="9d386-110">Эта таблица введена в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9d386-110">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="9d386-111">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="9d386-111">**Column**</span></span>|<span data-ttu-id="9d386-112">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="9d386-112">**Data Type**</span></span>|<span data-ttu-id="9d386-113">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="9d386-113">**Key/Index**</span></span>|<span data-ttu-id="9d386-114">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="9d386-114">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9d386-115">**КодТипа**</span><span class="sxs-lookup"><span data-stu-id="9d386-115">**CategoryId**</span></span> <br/> |<span data-ttu-id="9d386-116">tinyint</span><span class="sxs-lookup"><span data-stu-id="9d386-116">tinyint</span></span>  <br/> |<span data-ttu-id="9d386-117">Primary</span><span class="sxs-lookup"><span data-stu-id="9d386-117">Primary</span></span>  <br/> |<span data-ttu-id="9d386-118">Уникальный идентификатор для классификации.</span><span class="sxs-lookup"><span data-stu-id="9d386-118">Unique identifier for the classification.</span></span>  <br/> |
|<span data-ttu-id="9d386-119">**Имя**</span><span class="sxs-lookup"><span data-stu-id="9d386-119">**Name**</span></span> <br/> |<span data-ttu-id="9d386-120">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="9d386-120">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="9d386-121">Значение и понятное имя, присвоенное классификации.</span><span class="sxs-lookup"><span data-stu-id="9d386-121">Value and friendly name assigned to the classification.</span></span> <span data-ttu-id="9d386-122">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="9d386-122">Allowed values are:</span></span> <br/>  <span data-ttu-id="9d386-123">0 — успех</span><span class="sxs-lookup"><span data-stu-id="9d386-123">0 -- Success</span></span> <br/>  <span data-ttu-id="9d386-124">1 — ожидаемый сбой</span><span class="sxs-lookup"><span data-stu-id="9d386-124">1 -- Expected failure</span></span> <br/>  <span data-ttu-id="9d386-125">2 — непредвиденный сбой</span><span class="sxs-lookup"><span data-stu-id="9d386-125">2 - Unexpected failure</span></span> <br/> |
   

