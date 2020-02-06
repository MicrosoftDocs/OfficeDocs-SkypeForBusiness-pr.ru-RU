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
description: Командлет Start-CcLogging запускает ведение журналов входящих и исходящих звонков для устройства Skype для бизнеса Cloud Connector Edition.
ms.openlocfilehash: bf84b55484e7f1d4f557730408676e337063a040
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824173"
---
# <a name="start-cclogging"></a><span data-ttu-id="811a0-103">Start-CcLogging</span><span class="sxs-lookup"><span data-stu-id="811a0-103">Start-CcLogging</span></span>
 
<span data-ttu-id="811a0-104">Командлет Start-CcLogging запускает ведение журналов входящих и исходящих звонков для устройства Skype для бизнеса Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="811a0-104">The Start-CcLogging cmdlet generates the incoming and outgoing call log for a Skype for Business Cloud Connector Edition appliance.</span></span> 
  
```powershell
Start-CcLogging
```

## <a name="parameters"></a><span data-ttu-id="811a0-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="811a0-105">Parameters</span></span>

<span data-ttu-id="811a0-106">Нет</span><span class="sxs-lookup"><span data-stu-id="811a0-106">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="811a0-107">Примеры</span><span class="sxs-lookup"><span data-stu-id="811a0-107">Examples</span></span>
<span data-ttu-id="811a0-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="811a0-108"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="811a0-109">Пример 1</span><span class="sxs-lookup"><span data-stu-id="811a0-109">Example 1</span></span>

<span data-ttu-id="811a0-110">В следующем примере создаются журналы входящих и исходящих звонков:</span><span class="sxs-lookup"><span data-stu-id="811a0-110">The following example generates the incoming and outgoing call log:</span></span>
  
```powershell
Start-CcLogging
```

## <a name="detailed-description"></a><span data-ttu-id="811a0-111">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="811a0-111">Detailed Description</span></span>
<span data-ttu-id="811a0-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="811a0-112"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="811a0-113">Командлет Start-Кклоггинг предоставляет администраторам способ начать ведение журнала входящих и исходящих вызовов на устройстве облачного соединителя.</span><span class="sxs-lookup"><span data-stu-id="811a0-113">The Start-CcLogging cmdlet provides a way for administrators to begin logging incoming and outgoing calls on a Cloud Connector appliance.</span></span> <span data-ttu-id="811a0-114">По умолчанию ведение журналов автоматически прекращается через четыре часа.</span><span class="sxs-lookup"><span data-stu-id="811a0-114">By default, logging will automatically stop after four hours.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="811a0-115">Типы входных данных</span><span class="sxs-lookup"><span data-stu-id="811a0-115">Input Types</span></span>
<span data-ttu-id="811a0-116"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="811a0-116"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="811a0-p102">Нет. Командлет Start-CcLogging не принимает входные данные по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="811a0-p102">None. The Start-CcLogging cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="811a0-119">Типы возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="811a0-119">Return Types</span></span>
<span data-ttu-id="811a0-120"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="811a0-120"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="811a0-121">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="811a0-121">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="811a0-122">См. также</span><span class="sxs-lookup"><span data-stu-id="811a0-122">See also</span></span>
<span data-ttu-id="811a0-123"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="811a0-123"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="811a0-124">Search-CcLog</span><span class="sxs-lookup"><span data-stu-id="811a0-124">Search-CcLog</span></span>](search-cclog.md)
  
[<span data-ttu-id="811a0-125">Stop-CcLogging</span><span class="sxs-lookup"><span data-stu-id="811a0-125">Stop-CcLogging</span></span>](stop-cclogging.md)
  

