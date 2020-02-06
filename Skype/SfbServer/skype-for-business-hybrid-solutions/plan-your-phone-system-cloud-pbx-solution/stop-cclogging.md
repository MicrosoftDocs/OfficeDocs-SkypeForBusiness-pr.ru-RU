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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: fee9eda7-ad15-40d2-b9fe-21c5462d3309
description: Командлет Stop-CcLogging прекращает ведение журналов входящих и исходящих звонков для устройства Skype для бизнеса Cloud Connector Edition.
ms.openlocfilehash: 8a012e9b1a94c3698cc61da4326eb0ccbb27bca2
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824163"
---
# <a name="stop-cclogging"></a><span data-ttu-id="4569e-103">Stop-CcLogging</span><span class="sxs-lookup"><span data-stu-id="4569e-103">Stop-CcLogging</span></span>
 
<span data-ttu-id="4569e-104">Командлет Stop-CcLogging прекращает ведение журналов входящих и исходящих звонков для устройства Skype для бизнеса Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="4569e-104">The Stop-CcLogging cmdlet stops generating the incoming and outgoing call log for a Skype for Business Cloud Connector Edition appliance.</span></span>
  
```powershell
Stop-CcLogging [-RemoveCache]
```

## <a name="examples"></a><span data-ttu-id="4569e-105">Примеры</span><span class="sxs-lookup"><span data-stu-id="4569e-105">Examples</span></span>
<span data-ttu-id="4569e-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="4569e-106"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="4569e-107">Пример 1</span><span class="sxs-lookup"><span data-stu-id="4569e-107">Example 1</span></span>

<span data-ttu-id="4569e-108">В следующем примере прекращается ведение журналов входящих и исходящих звонков:</span><span class="sxs-lookup"><span data-stu-id="4569e-108">The following example stops generating the incoming and outgoing call log:</span></span> 
  
```powershell
Stop-CcLogging
```

### <a name="example-2"></a><span data-ttu-id="4569e-109">Пример 2</span><span class="sxs-lookup"><span data-stu-id="4569e-109">Example 2</span></span>

<span data-ttu-id="4569e-110">В следующем примере прекращается ведение журналов входящих и исходящих звонков, а также удаляются файлы кэша:</span><span class="sxs-lookup"><span data-stu-id="4569e-110">The next example stops generating the incoming and outgoing call log and cleans up the cache files:</span></span>
  
```powershell
Stop-CcLogging -RemoveCache
```

## <a name="detailed-description"></a><span data-ttu-id="4569e-111">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="4569e-111">Detailed Description</span></span>
<span data-ttu-id="4569e-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="4569e-112"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="4569e-113">Командлет Stop-CcLogging прекращает ведение журналов входящих и исходящих звонков для устройства.</span><span class="sxs-lookup"><span data-stu-id="4569e-113">The Stop-CcLogging cmdlet stops logging of incoming and outgoing calls on an appliance.</span></span> <span data-ttu-id="4569e-114">По умолчанию ведение журналов автоматически прекращается через четыре часа.</span><span class="sxs-lookup"><span data-stu-id="4569e-114">By default, logging will automatically stop after four hours.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="4569e-115">Параметры</span><span class="sxs-lookup"><span data-stu-id="4569e-115">Parameters</span></span>
<span data-ttu-id="4569e-116"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="4569e-116"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="4569e-117">**Параметр**</span><span class="sxs-lookup"><span data-stu-id="4569e-117">**Parameter**</span></span>|<span data-ttu-id="4569e-118">**Обязательный**</span><span class="sxs-lookup"><span data-stu-id="4569e-118">**Required**</span></span>|<span data-ttu-id="4569e-119">**Тип**</span><span class="sxs-lookup"><span data-stu-id="4569e-119">**Type**</span></span>|<span data-ttu-id="4569e-120">**Описание**</span><span class="sxs-lookup"><span data-stu-id="4569e-120">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="4569e-121">RemoveCache</span><span class="sxs-lookup"><span data-stu-id="4569e-121">RemoveCache</span></span> <br/> | <span data-ttu-id="4569e-122">Необязательно</span><span class="sxs-lookup"><span data-stu-id="4569e-122">Optional</span></span> <br/> | <span data-ttu-id="4569e-123">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="4569e-123">System.Management.Automation.SwitchParameter</span></span> <br/> |<span data-ttu-id="4569e-124">Удаляет файлы кэша журналов.</span><span class="sxs-lookup"><span data-stu-id="4569e-124">Removes the logging cache files.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="4569e-125">Типы входных данных</span><span class="sxs-lookup"><span data-stu-id="4569e-125">Input Types</span></span>
<span data-ttu-id="4569e-126"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="4569e-126"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="4569e-p102">Нет. Командлет Stop-CcLogging не принимает входные данные по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="4569e-p102">None. The Stop-CcLogging cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="4569e-129">Типы возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="4569e-129">Return Types</span></span>
<span data-ttu-id="4569e-130"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="4569e-130"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="4569e-131">Нет</span><span class="sxs-lookup"><span data-stu-id="4569e-131">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="4569e-132">См. также</span><span class="sxs-lookup"><span data-stu-id="4569e-132">See also</span></span>
<span data-ttu-id="4569e-133"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="4569e-133"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="4569e-134">Search-CcLog</span><span class="sxs-lookup"><span data-stu-id="4569e-134">Search-CcLog</span></span>](search-cclog.md)
  
[<span data-ttu-id="4569e-135">Start-CcLogging</span><span class="sxs-lookup"><span data-stu-id="4569e-135">Start-CcLogging</span></span>](start-cclogging.md)
  

