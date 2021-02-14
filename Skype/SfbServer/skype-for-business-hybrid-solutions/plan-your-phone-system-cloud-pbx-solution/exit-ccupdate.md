---
title: Exit-CcUpdate
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
ms.assetid: 463dce1e-fb60-487d-bcf1-69e7b03ecd14
description: The Exit-CcUpdate cmdlet exits update maintenance mode on the Skype for Business Cloud Connector Edition host server.
ms.openlocfilehash: 315d6b7dccb6708901128bf8faa29a60f712e833
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41801769"
---
# <a name="exit-ccupdate"></a><span data-ttu-id="1e27a-103">Exit-CcUpdate</span><span class="sxs-lookup"><span data-stu-id="1e27a-103">Exit-CcUpdate</span></span>
 
<span data-ttu-id="1e27a-104">The Exit-CcUpdate cmdlet exits update maintenance mode on the Skype for Business Cloud Connector Edition host server.</span><span class="sxs-lookup"><span data-stu-id="1e27a-104">The Exit-CcUpdate cmdlet exits update maintenance mode on the Skype for Business Cloud Connector Edition host server.</span></span> 
  
<span data-ttu-id="1e27a-105">Этот cmdlet применяется к Skype для бизнеса Cloud Connector Edition 1.4.1, 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="1e27a-105">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span> 
  
```powershell
Exit-CcUpdate
```

## <a name="parameters"></a><span data-ttu-id="1e27a-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="1e27a-106">Parameters</span></span>

<span data-ttu-id="1e27a-107">Нет</span><span class="sxs-lookup"><span data-stu-id="1e27a-107">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="1e27a-108">Примеры</span><span class="sxs-lookup"><span data-stu-id="1e27a-108">Examples</span></span>
<span data-ttu-id="1e27a-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="1e27a-109"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="1e27a-110">Пример 1</span><span class="sxs-lookup"><span data-stu-id="1e27a-110">Example 1</span></span>

<span data-ttu-id="1e27a-111">Следующая команда помещает устройство, на котором оно выполняется, обратно в производственный режим:</span><span class="sxs-lookup"><span data-stu-id="1e27a-111">The following command puts the appliance on which it runs back into production mode:</span></span> 
  
```powershell
Exit-CcUpdate
```

## <a name="detailed-description"></a><span data-ttu-id="1e27a-112">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="1e27a-112">Detailed Description</span></span>
<span data-ttu-id="1e27a-113"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="1e27a-113"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="1e27a-114">Если у вас есть устройства, которые были поставлены в режим обслуживания, указав Enter-CcUpdate, Exit-CcUpdate снова в режиме эксплуатации.</span><span class="sxs-lookup"><span data-stu-id="1e27a-114">If you have appliances that you have put in maintenance mode by specifying the Enter-CcUpdate cmdlet, the Exit-CcUpdate cmdlet will put these back into production mode.</span></span> 
  
<span data-ttu-id="1e27a-115">Дополнительные сведения о переводить устройства в режим обслуживания см. в enter-CcUpdate.</span><span class="sxs-lookup"><span data-stu-id="1e27a-115">For more information about putting appliances in maintenance mode, see Enter-CcUpdate.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="1e27a-116">Типы входных данных</span><span class="sxs-lookup"><span data-stu-id="1e27a-116">Input Types</span></span>
<span data-ttu-id="1e27a-117"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="1e27a-117"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="1e27a-118">Нет.</span><span class="sxs-lookup"><span data-stu-id="1e27a-118">None.</span></span> <span data-ttu-id="1e27a-119">Этот Exit-CcUpdate не принимает конвейерные входные данные.</span><span class="sxs-lookup"><span data-stu-id="1e27a-119">The Exit-CcUpdate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="1e27a-120">Типы возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="1e27a-120">Return Types</span></span>
<span data-ttu-id="1e27a-121"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="1e27a-121"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="1e27a-122">Нет</span><span class="sxs-lookup"><span data-stu-id="1e27a-122">None</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="1e27a-123">См. также</span><span class="sxs-lookup"><span data-stu-id="1e27a-123">See also</span></span>
<span data-ttu-id="1e27a-124"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="1e27a-124"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="1e27a-125">Enter-CcUpdate</span><span class="sxs-lookup"><span data-stu-id="1e27a-125">Enter-CcUpdate</span></span>](enter-ccupdate.md)
  

