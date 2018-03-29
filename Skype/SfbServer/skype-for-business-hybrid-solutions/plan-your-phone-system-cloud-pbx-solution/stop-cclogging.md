---
title: STOP-CcLogging
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fee9eda7-ad15-40d2-b9fe-21c5462d3309
description: Командлет Stop-CcLogging останавливает создание журнала входящих и исходящих вызовов для Скайп для соединителя Cloud Business Edition устройства.
ms.openlocfilehash: abecc5acc6a454b2965fbf79caadb23f2256e4cd
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="stop-cclogging"></a><span data-ttu-id="bf730-103">STOP-CcLogging</span><span class="sxs-lookup"><span data-stu-id="bf730-103">Stop-CcLogging</span></span>
 
<span data-ttu-id="bf730-104">Командлет Stop-CcLogging останавливает создание журнала входящих и исходящих вызовов для Скайп для соединителя Cloud Business Edition устройства.</span><span class="sxs-lookup"><span data-stu-id="bf730-104">The Stop-CcLogging cmdlet stops generating the incoming and outgoing call log for a Skype for Business Cloud Connector Edition appliance.</span></span>
  
```
Stop-CcLogging [-RemoveCache]
```

## <a name="examples"></a><span data-ttu-id="bf730-105">Примеры</span><span class="sxs-lookup"><span data-stu-id="bf730-105">Examples</span></span>
<span data-ttu-id="bf730-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="bf730-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="bf730-107">Пример 1</span><span class="sxs-lookup"><span data-stu-id="bf730-107">Example 1</span></span>

<span data-ttu-id="bf730-108">В следующем примере прекращается ведение журналов входящих и исходящих звонков:</span><span class="sxs-lookup"><span data-stu-id="bf730-108">The following example stops generating the incoming and outgoing call log:</span></span> 
  
```
Stop-CcLogging
```

### <a name="example-2"></a><span data-ttu-id="bf730-109">Пример 2</span><span class="sxs-lookup"><span data-stu-id="bf730-109">Example 2</span></span>

<span data-ttu-id="bf730-110">В следующем примере прекращается ведение журналов входящих и исходящих звонков, а также удаляются файлы кэша:</span><span class="sxs-lookup"><span data-stu-id="bf730-110">The next example stops generating the incoming and outgoing call log and cleans up the cache files:</span></span>
  
```
Stop-CcLogging -RemoveCache
```

## <a name="detailed-description"></a><span data-ttu-id="bf730-111">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="bf730-111">Detailed Description</span></span>
<span data-ttu-id="bf730-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="bf730-112"></span></span>

<span data-ttu-id="bf730-p101">Командлет Stop-CcLogging прекращает ведение журналов входящих и исходящих звонков для устройства. По умолчанию ведение журналов автоматически прекращается через четыре часа.</span><span class="sxs-lookup"><span data-stu-id="bf730-p101">The Stop-CcLogging cmdlet stops logging of incoming and outgoing calls on an appliance. By default, logging will automatically stop after four hours.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="bf730-115">Параметры</span><span class="sxs-lookup"><span data-stu-id="bf730-115">Parameters</span></span>
<span data-ttu-id="bf730-116"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="bf730-116"></span></span>

|<span data-ttu-id="bf730-117">**Параметр**</span><span class="sxs-lookup"><span data-stu-id="bf730-117">**Parameter**</span></span>|<span data-ttu-id="bf730-118">**Обязательно**</span><span class="sxs-lookup"><span data-stu-id="bf730-118">**Required**</span></span>|<span data-ttu-id="bf730-119">**Тип**</span><span class="sxs-lookup"><span data-stu-id="bf730-119">**Type**</span></span>|<span data-ttu-id="bf730-120">**Описание**</span><span class="sxs-lookup"><span data-stu-id="bf730-120">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="bf730-121">RemoveCache</span><span class="sxs-lookup"><span data-stu-id="bf730-121">RemoveCache</span></span> <br/> | <span data-ttu-id="bf730-122">Необязательно</span><span class="sxs-lookup"><span data-stu-id="bf730-122">Optional</span></span> <br/> | <span data-ttu-id="bf730-123">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="bf730-123">System.Management.Automation.SwitchParameter</span></span> <br/> |<span data-ttu-id="bf730-124">Удаляет файлы кэша журналов.</span><span class="sxs-lookup"><span data-stu-id="bf730-124">Removes the logging cache files.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="bf730-125">Типы входных данных</span><span class="sxs-lookup"><span data-stu-id="bf730-125">Input Types</span></span>
<span data-ttu-id="bf730-126"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="bf730-126"></span></span>

<span data-ttu-id="bf730-p102">Нет. Командлет Stop-CcLogging не принимает входные данные по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="bf730-p102">None. The Stop-CcLogging cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="bf730-129">Типы возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="bf730-129">Return Types</span></span>
<span data-ttu-id="bf730-130"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="bf730-130"></span></span>

<span data-ttu-id="bf730-131">Нет</span><span class="sxs-lookup"><span data-stu-id="bf730-131">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="bf730-132">См. также</span><span class="sxs-lookup"><span data-stu-id="bf730-132">See also</span></span>
<span data-ttu-id="bf730-133"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="bf730-133"></span></span>

[<span data-ttu-id="bf730-134">CcLog поиска</span><span class="sxs-lookup"><span data-stu-id="bf730-134">Search-CcLog</span></span>](search-cclog.md)
  
[<span data-ttu-id="bf730-135">Start-CcLogging</span><span class="sxs-lookup"><span data-stu-id="bf730-135">Start-CcLogging</span></span>](start-cclogging.md)
  

