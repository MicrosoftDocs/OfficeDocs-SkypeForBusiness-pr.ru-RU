---
title: Start-CcLogging
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
ms.assetid: 01b62253-2aaf-43ed-9d63-804e31edc522
description: Этот Start-CcLogging создает журнал входящих и исходяющих звонков для устройства Skype для бизнеса Cloud Connector Edition.
ms.openlocfilehash: bf84b55484e7f1d4f557730408676e337063a040
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824173"
---
# <a name="start-cclogging"></a><span data-ttu-id="e95d2-103">Start-CcLogging</span><span class="sxs-lookup"><span data-stu-id="e95d2-103">Start-CcLogging</span></span>
 
<span data-ttu-id="e95d2-104">Этот Start-CcLogging создает журнал входящих и исходяющих звонков для устройства Skype для бизнеса Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="e95d2-104">The Start-CcLogging cmdlet generates the incoming and outgoing call log for a Skype for Business Cloud Connector Edition appliance.</span></span> 
  
```powershell
Start-CcLogging
```

## <a name="parameters"></a><span data-ttu-id="e95d2-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e95d2-105">Parameters</span></span>

<span data-ttu-id="e95d2-106">Нет</span><span class="sxs-lookup"><span data-stu-id="e95d2-106">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="e95d2-107">Примеры</span><span class="sxs-lookup"><span data-stu-id="e95d2-107">Examples</span></span>
<span data-ttu-id="e95d2-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="e95d2-108"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="e95d2-109">Пример 1</span><span class="sxs-lookup"><span data-stu-id="e95d2-109">Example 1</span></span>

<span data-ttu-id="e95d2-110">В следующем примере создается журнал входящих и исходяющих вызовов:</span><span class="sxs-lookup"><span data-stu-id="e95d2-110">The following example generates the incoming and outgoing call log:</span></span>
  
```powershell
Start-CcLogging
```

## <a name="detailed-description"></a><span data-ttu-id="e95d2-111">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="e95d2-111">Detailed Description</span></span>
<span data-ttu-id="e95d2-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="e95d2-112"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="e95d2-113">Этот Start-CcLogging позволяет администраторам начать ведение журнала входящих и исходяющих вызовов на устройстве Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="e95d2-113">The Start-CcLogging cmdlet provides a way for administrators to begin logging incoming and outgoing calls on a Cloud Connector appliance.</span></span> <span data-ttu-id="e95d2-114">По умолчанию ведение журнала автоматически останавливается через четыре часа.</span><span class="sxs-lookup"><span data-stu-id="e95d2-114">By default, logging will automatically stop after four hours.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="e95d2-115">Типы входных данных</span><span class="sxs-lookup"><span data-stu-id="e95d2-115">Input Types</span></span>
<span data-ttu-id="e95d2-116"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="e95d2-116"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="e95d2-117">Нет.</span><span class="sxs-lookup"><span data-stu-id="e95d2-117">None.</span></span> <span data-ttu-id="e95d2-118">Этот Start-CcLogging не принимает конвейерные входные данные.</span><span class="sxs-lookup"><span data-stu-id="e95d2-118">The Start-CcLogging cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="e95d2-119">Типы возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="e95d2-119">Return Types</span></span>
<span data-ttu-id="e95d2-120"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="e95d2-120"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="e95d2-121">Нет</span><span class="sxs-lookup"><span data-stu-id="e95d2-121">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="e95d2-122">См. также</span><span class="sxs-lookup"><span data-stu-id="e95d2-122">See also</span></span>
<span data-ttu-id="e95d2-123"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="e95d2-123"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="e95d2-124">Search-CcLog</span><span class="sxs-lookup"><span data-stu-id="e95d2-124">Search-CcLog</span></span>](search-cclog.md)
  
[<span data-ttu-id="e95d2-125">Stop-CcLogging</span><span class="sxs-lookup"><span data-stu-id="e95d2-125">Stop-CcLogging</span></span>](stop-cclogging.md)
  

