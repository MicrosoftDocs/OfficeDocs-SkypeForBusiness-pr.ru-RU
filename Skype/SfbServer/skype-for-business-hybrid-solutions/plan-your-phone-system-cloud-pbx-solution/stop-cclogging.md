---
title: Stop-CcLogging
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fee9eda7-ad15-40d2-b9fe-21c5462d3309
description: Командлет Stop-CcLogging прекращает ведение журналов входящих и исходящих звонков для устройства Skype для бизнеса Cloud Connector Edition.
ms.openlocfilehash: dcc62e8ec772912a8275f5321a6c91e28dde8c25
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286938"
---
# <a name="stop-cclogging"></a><span data-ttu-id="eb1e2-103">Stop-CcLogging</span><span class="sxs-lookup"><span data-stu-id="eb1e2-103">Stop-CcLogging</span></span>
 
<span data-ttu-id="eb1e2-104">Командлет Stop-CcLogging прекращает ведение журналов входящих и исходящих звонков для устройства Skype для бизнеса Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="eb1e2-104">The Stop-CcLogging cmdlet stops generating the incoming and outgoing call log for a Skype for Business Cloud Connector Edition appliance.</span></span>
  
```
Stop-CcLogging [-RemoveCache]
```

## <a name="examples"></a><span data-ttu-id="eb1e2-105">Примеры</span><span class="sxs-lookup"><span data-stu-id="eb1e2-105">Examples</span></span>
<span data-ttu-id="eb1e2-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="eb1e2-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="eb1e2-107">Пример 1</span><span class="sxs-lookup"><span data-stu-id="eb1e2-107">Example 1</span></span>

<span data-ttu-id="eb1e2-108">В следующем примере прекращается ведение журналов входящих и исходящих звонков:</span><span class="sxs-lookup"><span data-stu-id="eb1e2-108">The following example stops generating the incoming and outgoing call log:</span></span> 
  
```
Stop-CcLogging
```

### <a name="example-2"></a><span data-ttu-id="eb1e2-109">Пример 2</span><span class="sxs-lookup"><span data-stu-id="eb1e2-109">Example 2</span></span>

<span data-ttu-id="eb1e2-110">В следующем примере прекращается ведение журналов входящих и исходящих звонков, а также удаляются файлы кэша:</span><span class="sxs-lookup"><span data-stu-id="eb1e2-110">The next example stops generating the incoming and outgoing call log and cleans up the cache files:</span></span>
  
```
Stop-CcLogging -RemoveCache
```

## <a name="detailed-description"></a><span data-ttu-id="eb1e2-111">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="eb1e2-111">Detailed Description</span></span>
<span data-ttu-id="eb1e2-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="eb1e2-112"></span></span>

<span data-ttu-id="eb1e2-113">Командлет Stop-CcLogging прекращает ведение журналов входящих и исходящих звонков для устройства.</span><span class="sxs-lookup"><span data-stu-id="eb1e2-113">The Stop-CcLogging cmdlet stops logging of incoming and outgoing calls on an appliance.</span></span> <span data-ttu-id="eb1e2-114">По умолчанию ведение журналов автоматически прекращается через четыре часа.</span><span class="sxs-lookup"><span data-stu-id="eb1e2-114">By default, logging will automatically stop after four hours.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="eb1e2-115">Параметры</span><span class="sxs-lookup"><span data-stu-id="eb1e2-115">Parameters</span></span>
<span data-ttu-id="eb1e2-116"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="eb1e2-116"></span></span>

|<span data-ttu-id="eb1e2-117">**Параметр**</span><span class="sxs-lookup"><span data-stu-id="eb1e2-117">**Parameter**</span></span>|<span data-ttu-id="eb1e2-118">**Обязательно**</span><span class="sxs-lookup"><span data-stu-id="eb1e2-118">**Required**</span></span>|<span data-ttu-id="eb1e2-119">**Тип**</span><span class="sxs-lookup"><span data-stu-id="eb1e2-119">**Type**</span></span>|<span data-ttu-id="eb1e2-120">**Описание**</span><span class="sxs-lookup"><span data-stu-id="eb1e2-120">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="eb1e2-121">RemoveCache</span><span class="sxs-lookup"><span data-stu-id="eb1e2-121">RemoveCache</span></span> <br/> | <span data-ttu-id="eb1e2-122">Необязательно</span><span class="sxs-lookup"><span data-stu-id="eb1e2-122">Optional</span></span> <br/> | <span data-ttu-id="eb1e2-123">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="eb1e2-123">System.Management.Automation.SwitchParameter</span></span> <br/> |<span data-ttu-id="eb1e2-124">Удаляет файлы кэша журналов.</span><span class="sxs-lookup"><span data-stu-id="eb1e2-124">Removes the logging cache files.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="eb1e2-125">Типы входных данных</span><span class="sxs-lookup"><span data-stu-id="eb1e2-125">Input Types</span></span>
<span data-ttu-id="eb1e2-126"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="eb1e2-126"></span></span>

<span data-ttu-id="eb1e2-p102">Нет. Командлет Stop-CcLogging не принимает входные данные по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="eb1e2-p102">None. The Stop-CcLogging cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="eb1e2-129">Типы возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="eb1e2-129">Return Types</span></span>
<span data-ttu-id="eb1e2-130"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="eb1e2-130"></span></span>

<span data-ttu-id="eb1e2-131">Нет</span><span class="sxs-lookup"><span data-stu-id="eb1e2-131">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="eb1e2-132">См. также</span><span class="sxs-lookup"><span data-stu-id="eb1e2-132">See also</span></span>
<span data-ttu-id="eb1e2-133"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="eb1e2-133"></span></span>

[<span data-ttu-id="eb1e2-134">Search-CcLog</span><span class="sxs-lookup"><span data-stu-id="eb1e2-134">Search-CcLog</span></span>](search-cclog.md)
  
[<span data-ttu-id="eb1e2-135">Start-CcLogging</span><span class="sxs-lookup"><span data-stu-id="eb1e2-135">Start-CcLogging</span></span>](start-cclogging.md)
  

