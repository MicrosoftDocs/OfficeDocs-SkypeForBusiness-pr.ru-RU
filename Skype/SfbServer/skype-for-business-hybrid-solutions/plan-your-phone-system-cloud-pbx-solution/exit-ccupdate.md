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
description: Командлет Exit-CcUpdate обновляет режим обслуживания на сервере узла Skype для бизнеса Cloud Connector Edition.
ms.openlocfilehash: 315d6b7dccb6708901128bf8faa29a60f712e833
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41801769"
---
# <a name="exit-ccupdate"></a><span data-ttu-id="68690-103">Exit-CcUpdate</span><span class="sxs-lookup"><span data-stu-id="68690-103">Exit-CcUpdate</span></span>
 
<span data-ttu-id="68690-104">Командлет Exit-CcUpdate обновляет режим обслуживания на сервере узла Skype для бизнеса Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="68690-104">The Exit-CcUpdate cmdlet exits update maintenance mode on the Skype for Business Cloud Connector Edition host server.</span></span> 
  
<span data-ttu-id="68690-105">Этот командлет применяется к версии Skype для бизнеса Cloud Connector Edition 1.4.1, 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="68690-105">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span> 
  
```powershell
Exit-CcUpdate
```

## <a name="parameters"></a><span data-ttu-id="68690-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="68690-106">Parameters</span></span>

<span data-ttu-id="68690-107">Нет</span><span class="sxs-lookup"><span data-stu-id="68690-107">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="68690-108">Примеры</span><span class="sxs-lookup"><span data-stu-id="68690-108">Examples</span></span>
<span data-ttu-id="68690-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="68690-109"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="68690-110">Пример 1</span><span class="sxs-lookup"><span data-stu-id="68690-110">Example 1</span></span>

<span data-ttu-id="68690-111">Следующая команда переводит устройство, на котором она выполняется, в рабочий режим:</span><span class="sxs-lookup"><span data-stu-id="68690-111">The following command puts the appliance on which it runs back into production mode:</span></span> 
  
```powershell
Exit-CcUpdate
```

## <a name="detailed-description"></a><span data-ttu-id="68690-112">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="68690-112">Detailed Description</span></span>
<span data-ttu-id="68690-113"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="68690-113"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="68690-114">Если вы перевели какие-либо устройства в режим обслуживания с помощью командлета Enter-CcUpdate, командлет Exit-CcUpdate позволит вернуть их в рабочий режим.</span><span class="sxs-lookup"><span data-stu-id="68690-114">If you have appliances that you have put in maintenance mode by specifying the Enter-CcUpdate cmdlet, the Exit-CcUpdate cmdlet will put these back into production mode.</span></span> 
  
<span data-ttu-id="68690-115">Дополнительные сведения о переводе устройств в режим обслуживания см. в описании командлета Enter-CcUpdate.</span><span class="sxs-lookup"><span data-stu-id="68690-115">For more information about putting appliances in maintenance mode, see Enter-CcUpdate.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="68690-116">Типы входных данных</span><span class="sxs-lookup"><span data-stu-id="68690-116">Input Types</span></span>
<span data-ttu-id="68690-117"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="68690-117"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="68690-p101">Нет. Командлет Exit-CcUpdate не принимает входные данные по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="68690-p101">None. The Exit-CcUpdate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="68690-120">Типы возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="68690-120">Return Types</span></span>
<span data-ttu-id="68690-121"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="68690-121"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="68690-122">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="68690-122">None</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="68690-123">См. также</span><span class="sxs-lookup"><span data-stu-id="68690-123">See also</span></span>
<span data-ttu-id="68690-124"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="68690-124"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="68690-125">Enter-CcUpdate</span><span class="sxs-lookup"><span data-stu-id="68690-125">Enter-CcUpdate</span></span>](enter-ccupdate.md)
  

