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
description: The Stop-CcLogging stops generating the incoming and outgoing call log for a Skype for Business Cloud Connector Edition appliance.
ms.openlocfilehash: 8a012e9b1a94c3698cc61da4326eb0ccbb27bca2
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824163"
---
# <a name="stop-cclogging"></a><span data-ttu-id="ad300-103">Stop-CcLogging</span><span class="sxs-lookup"><span data-stu-id="ad300-103">Stop-CcLogging</span></span>
 
<span data-ttu-id="ad300-104">The Stop-CcLogging stops generating the incoming and outgoing call log for a Skype for Business Cloud Connector Edition appliance.</span><span class="sxs-lookup"><span data-stu-id="ad300-104">The Stop-CcLogging cmdlet stops generating the incoming and outgoing call log for a Skype for Business Cloud Connector Edition appliance.</span></span>
  
```powershell
Stop-CcLogging [-RemoveCache]
```

## <a name="examples"></a><span data-ttu-id="ad300-105">Примеры</span><span class="sxs-lookup"><span data-stu-id="ad300-105">Examples</span></span>
<span data-ttu-id="ad300-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="ad300-106"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="ad300-107">Пример 1</span><span class="sxs-lookup"><span data-stu-id="ad300-107">Example 1</span></span>

<span data-ttu-id="ad300-108">В следующем примере прекращается создание журнала входящих и исходяющих вызовов:</span><span class="sxs-lookup"><span data-stu-id="ad300-108">The following example stops generating the incoming and outgoing call log:</span></span> 
  
```powershell
Stop-CcLogging
```

### <a name="example-2"></a><span data-ttu-id="ad300-109">Пример 2</span><span class="sxs-lookup"><span data-stu-id="ad300-109">Example 2</span></span>

<span data-ttu-id="ad300-110">В следующем примере прекращается создание журнала входящих и исходяющих вызовов, а также очищаются файлы кэша:</span><span class="sxs-lookup"><span data-stu-id="ad300-110">The next example stops generating the incoming and outgoing call log and cleans up the cache files:</span></span>
  
```powershell
Stop-CcLogging -RemoveCache
```

## <a name="detailed-description"></a><span data-ttu-id="ad300-111">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="ad300-111">Detailed Description</span></span>
<span data-ttu-id="ad300-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="ad300-112"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="ad300-113">Этот Stop-CcLogging останавливает ведение журнала входящих и исходяющих вызовов на устройстве.</span><span class="sxs-lookup"><span data-stu-id="ad300-113">The Stop-CcLogging cmdlet stops logging of incoming and outgoing calls on an appliance.</span></span> <span data-ttu-id="ad300-114">По умолчанию ведение журнала автоматически останавливается через четыре часа.</span><span class="sxs-lookup"><span data-stu-id="ad300-114">By default, logging will automatically stop after four hours.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="ad300-115">Параметры</span><span class="sxs-lookup"><span data-stu-id="ad300-115">Parameters</span></span>
<span data-ttu-id="ad300-116"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="ad300-116"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="ad300-117">**Параметр**</span><span class="sxs-lookup"><span data-stu-id="ad300-117">**Parameter**</span></span>|<span data-ttu-id="ad300-118">**Required**</span><span class="sxs-lookup"><span data-stu-id="ad300-118">**Required**</span></span>|<span data-ttu-id="ad300-119">**Тип**</span><span class="sxs-lookup"><span data-stu-id="ad300-119">**Type**</span></span>|<span data-ttu-id="ad300-120">**Описание**</span><span class="sxs-lookup"><span data-stu-id="ad300-120">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="ad300-121">RemoveCache</span><span class="sxs-lookup"><span data-stu-id="ad300-121">RemoveCache</span></span> <br/> | <span data-ttu-id="ad300-122">Необязательный</span><span class="sxs-lookup"><span data-stu-id="ad300-122">Optional</span></span> <br/> | <span data-ttu-id="ad300-123">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="ad300-123">System.Management.Automation.SwitchParameter</span></span> <br/> |<span data-ttu-id="ad300-124">Удаляет файлы кэша журналов.</span><span class="sxs-lookup"><span data-stu-id="ad300-124">Removes the logging cache files.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="ad300-125">Типы входных данных</span><span class="sxs-lookup"><span data-stu-id="ad300-125">Input Types</span></span>
<span data-ttu-id="ad300-126"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="ad300-126"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="ad300-127">Нет.</span><span class="sxs-lookup"><span data-stu-id="ad300-127">None.</span></span> <span data-ttu-id="ad300-128">Этот Stop-CcLogging не принимает конвейерные входные данные.</span><span class="sxs-lookup"><span data-stu-id="ad300-128">The Stop-CcLogging cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="ad300-129">Типы возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="ad300-129">Return Types</span></span>
<span data-ttu-id="ad300-130"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="ad300-130"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="ad300-131">Нет</span><span class="sxs-lookup"><span data-stu-id="ad300-131">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ad300-132">См. также</span><span class="sxs-lookup"><span data-stu-id="ad300-132">See also</span></span>
<span data-ttu-id="ad300-133"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="ad300-133"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="ad300-134">Search-CcLog</span><span class="sxs-lookup"><span data-stu-id="ad300-134">Search-CcLog</span></span>](search-cclog.md)
  
[<span data-ttu-id="ad300-135">Start-CcLogging</span><span class="sxs-lookup"><span data-stu-id="ad300-135">Start-CcLogging</span></span>](start-cclogging.md)
  

