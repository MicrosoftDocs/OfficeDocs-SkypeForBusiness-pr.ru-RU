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
localization_priority: Normal
ms.assetid: 0fde3b73-9a2f-44dd-b8dc-6df512303ff1
description: 'В таблице Ерроркатегори содержится понятное имя для каждой классификации диагностики Skype для Business Server 2015. По умолчанию в Skype для бизнеса Server 2015 используются следующие классификации:'
ms.openlocfilehash: bafeb75ee9e6ae0f96b08e26909828f1b36f7e7b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296289"
---
# <a name="errorcategory-table-in-skype-for-business-server-2015"></a><span data-ttu-id="5d753-104">Таблица Ерроркатегори в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="5d753-104">ErrorCategory table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="5d753-105">В таблице Ерроркатегори содержится понятное имя для каждой классификации диагностики Skype для Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="5d753-105">The ErrorCategory table contains the friendly name for each Skype for Business Server 2015 diagnostic classification.</span></span> <span data-ttu-id="5d753-106">По умолчанию в Skype для бизнеса Server 2015 используются следующие классификации:</span><span class="sxs-lookup"><span data-stu-id="5d753-106">By default, Skype for Business Server 2015 uses the following classifications:</span></span>
  
- <span data-ttu-id="5d753-107">0 — успех</span><span class="sxs-lookup"><span data-stu-id="5d753-107">0 -- Success</span></span>
    
- <span data-ttu-id="5d753-108">1 — ожидаемый сбой</span><span class="sxs-lookup"><span data-stu-id="5d753-108">1 -- Expected failure</span></span>
    
- <span data-ttu-id="5d753-109">2 — непредвиденный сбой</span><span class="sxs-lookup"><span data-stu-id="5d753-109">2 - Unexpected failure</span></span>
    
<span data-ttu-id="5d753-110">Эта таблица введена в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5d753-110">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="5d753-111">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="5d753-111">**Column**</span></span>|<span data-ttu-id="5d753-112">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="5d753-112">**Data Type**</span></span>|<span data-ttu-id="5d753-113">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="5d753-113">**Key/Index**</span></span>|<span data-ttu-id="5d753-114">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="5d753-114">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="5d753-115">**КодТипа**</span><span class="sxs-lookup"><span data-stu-id="5d753-115">**CategoryId**</span></span> <br/> |<span data-ttu-id="5d753-116">tinyint</span><span class="sxs-lookup"><span data-stu-id="5d753-116">tinyint</span></span>  <br/> |<span data-ttu-id="5d753-117">Primary</span><span class="sxs-lookup"><span data-stu-id="5d753-117">Primary</span></span>  <br/> |<span data-ttu-id="5d753-118">Уникальный идентификатор для классификации.</span><span class="sxs-lookup"><span data-stu-id="5d753-118">Unique identifier for the classification.</span></span>  <br/> |
|<span data-ttu-id="5d753-119">**Имя**.</span><span class="sxs-lookup"><span data-stu-id="5d753-119">**Name**</span></span> <br/> |<span data-ttu-id="5d753-120">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="5d753-120">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="5d753-121">Значение и понятное имя, присвоенное классификации.</span><span class="sxs-lookup"><span data-stu-id="5d753-121">Value and friendly name assigned to the classification.</span></span> <span data-ttu-id="5d753-122">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="5d753-122">Allowed values are:</span></span> <br/>  <span data-ttu-id="5d753-123">0 — успех</span><span class="sxs-lookup"><span data-stu-id="5d753-123">0 -- Success</span></span> <br/>  <span data-ttu-id="5d753-124">1 — ожидаемый сбой</span><span class="sxs-lookup"><span data-stu-id="5d753-124">1 -- Expected failure</span></span> <br/>  <span data-ttu-id="5d753-125">2 — непредвиденный сбой</span><span class="sxs-lookup"><span data-stu-id="5d753-125">2 - Unexpected failure</span></span> <br/> |
   

