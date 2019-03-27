---
title: Stop-CcLogging
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fee9eda7-ad15-40d2-b9fe-21c5462d3309
description: Командлет Stop-CcLogging прекращает ведение журналов входящих и исходящих звонков для устройства Skype для бизнеса Cloud Connector Edition.
ms.openlocfilehash: eaccde49421cd22e32b23b89d8b5ea42dd073912
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30879625"
---
# <a name="stop-cclogging"></a><span data-ttu-id="a08e7-103">Stop-CcLogging</span><span class="sxs-lookup"><span data-stu-id="a08e7-103">Stop-CcLogging</span></span>
 
<span data-ttu-id="a08e7-104">Командлет Stop-CcLogging прекращает ведение журналов входящих и исходящих звонков для устройства Skype для бизнеса Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="a08e7-104">The Stop-CcLogging cmdlet stops generating the incoming and outgoing call log for a Skype for Business Cloud Connector Edition appliance.</span></span>
  
```
Stop-CcLogging [-RemoveCache]
```

## <a name="examples"></a><span data-ttu-id="a08e7-105">Примеры</span><span class="sxs-lookup"><span data-stu-id="a08e7-105">Examples</span></span>
<span data-ttu-id="a08e7-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="a08e7-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="a08e7-107">Пример 1</span><span class="sxs-lookup"><span data-stu-id="a08e7-107">Example 1</span></span>

<span data-ttu-id="a08e7-108">В следующем примере прекращается ведение журналов входящих и исходящих звонков:</span><span class="sxs-lookup"><span data-stu-id="a08e7-108">The following example stops generating the incoming and outgoing call log:</span></span> 
  
```
Stop-CcLogging
```

### <a name="example-2"></a><span data-ttu-id="a08e7-109">Пример 2</span><span class="sxs-lookup"><span data-stu-id="a08e7-109">Example 2</span></span>

<span data-ttu-id="a08e7-110">В следующем примере прекращается ведение журналов входящих и исходящих звонков, а также удаляются файлы кэша:</span><span class="sxs-lookup"><span data-stu-id="a08e7-110">The next example stops generating the incoming and outgoing call log and cleans up the cache files:</span></span>
  
```
Stop-CcLogging -RemoveCache
```

## <a name="detailed-description"></a><span data-ttu-id="a08e7-111">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="a08e7-111">Detailed Description</span></span>
<span data-ttu-id="a08e7-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="a08e7-112"></span></span>

<span data-ttu-id="a08e7-113">Командлет Stop-CcLogging прекращает ведение журналов входящих и исходящих звонков для устройства.</span><span class="sxs-lookup"><span data-stu-id="a08e7-113">The Stop-CcLogging cmdlet stops logging of incoming and outgoing calls on an appliance.</span></span> <span data-ttu-id="a08e7-114">По умолчанию ведение журналов автоматически прекращается через четыре часа.</span><span class="sxs-lookup"><span data-stu-id="a08e7-114">By default, logging will automatically stop after four hours.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="a08e7-115">Параметры</span><span class="sxs-lookup"><span data-stu-id="a08e7-115">Parameters</span></span>
<span data-ttu-id="a08e7-116"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="a08e7-116"></span></span>

|<span data-ttu-id="a08e7-117">**Параметр**</span><span class="sxs-lookup"><span data-stu-id="a08e7-117">**Parameter**</span></span>|<span data-ttu-id="a08e7-118">**Обязательно**</span><span class="sxs-lookup"><span data-stu-id="a08e7-118">**Required**</span></span>|<span data-ttu-id="a08e7-119">**Тип**</span><span class="sxs-lookup"><span data-stu-id="a08e7-119">**Type**</span></span>|<span data-ttu-id="a08e7-120">**Описание**.</span><span class="sxs-lookup"><span data-stu-id="a08e7-120">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="a08e7-121">RemoveCache</span><span class="sxs-lookup"><span data-stu-id="a08e7-121">RemoveCache</span></span> <br/> | <span data-ttu-id="a08e7-122">Необязательно</span><span class="sxs-lookup"><span data-stu-id="a08e7-122">Optional</span></span> <br/> | <span data-ttu-id="a08e7-123">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="a08e7-123">System.Management.Automation.SwitchParameter</span></span> <br/> |<span data-ttu-id="a08e7-124">Удаляет файлы кэша журналов.</span><span class="sxs-lookup"><span data-stu-id="a08e7-124">Removes the logging cache files.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="a08e7-125">Типы входных данных</span><span class="sxs-lookup"><span data-stu-id="a08e7-125">Input Types</span></span>
<span data-ttu-id="a08e7-126"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="a08e7-126"></span></span>

<span data-ttu-id="a08e7-p102">Нет. Командлет Stop-CcLogging не принимает входные данные по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="a08e7-p102">None. The Stop-CcLogging cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="a08e7-129">Типы возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="a08e7-129">Return Types</span></span>
<span data-ttu-id="a08e7-130"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="a08e7-130"></span></span>

<span data-ttu-id="a08e7-131">Нет</span><span class="sxs-lookup"><span data-stu-id="a08e7-131">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a08e7-132">См. также</span><span class="sxs-lookup"><span data-stu-id="a08e7-132">See also</span></span>
<span data-ttu-id="a08e7-133"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="a08e7-133"></span></span>

[<span data-ttu-id="a08e7-134">Search-CcLog</span><span class="sxs-lookup"><span data-stu-id="a08e7-134">Search-CcLog</span></span>](search-cclog.md)
  
[<span data-ttu-id="a08e7-135">Start-CcLogging</span><span class="sxs-lookup"><span data-stu-id="a08e7-135">Start-CcLogging</span></span>](start-cclogging.md)
  

