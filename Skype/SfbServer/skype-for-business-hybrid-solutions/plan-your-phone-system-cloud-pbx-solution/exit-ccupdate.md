---
title: Exit-CcUpdate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 463dce1e-fb60-487d-bcf1-69e7b03ecd14
description: Командлет Exit-CcUpdate обновляет режим обслуживания на сервере узла Skype для бизнеса Cloud Connector Edition.
ms.openlocfilehash: 7ac36e9cbab8e479a4ec7b070b773b3585370e8f
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30926541"
---
# <a name="exit-ccupdate"></a><span data-ttu-id="5e140-103">Exit-CcUpdate</span><span class="sxs-lookup"><span data-stu-id="5e140-103">Exit-CcUpdate</span></span>
 
<span data-ttu-id="5e140-104">Командлет Exit-CcUpdate обновляет режим обслуживания на сервере узла Skype для бизнеса Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="5e140-104">The Exit-CcUpdate cmdlet exits update maintenance mode on the Skype for Business Cloud Connector Edition host server.</span></span> 
  
<span data-ttu-id="5e140-105">Этот командлет применяется к версии Skype для бизнеса Cloud Connector Edition 1.4.1, 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="5e140-105">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span> 
  
```
Exit-CcUpdate
```

## <a name="parameters"></a><span data-ttu-id="5e140-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="5e140-106">Parameters</span></span>

<span data-ttu-id="5e140-107">Нет</span><span class="sxs-lookup"><span data-stu-id="5e140-107">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="5e140-108">Примеры</span><span class="sxs-lookup"><span data-stu-id="5e140-108">Examples</span></span>
<span data-ttu-id="5e140-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="5e140-109"></span></span>

### <a name="example-1"></a><span data-ttu-id="5e140-110">Пример 1</span><span class="sxs-lookup"><span data-stu-id="5e140-110">Example 1</span></span>

<span data-ttu-id="5e140-111">Следующая команда переводит устройство, на котором она выполняется, в рабочий режим:</span><span class="sxs-lookup"><span data-stu-id="5e140-111">The following command puts the appliance on which it runs back into production mode:</span></span> 
  
```
Exit-CcUpdate
```

## <a name="detailed-description"></a><span data-ttu-id="5e140-112">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="5e140-112">Detailed Description</span></span>
<span data-ttu-id="5e140-113"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="5e140-113"></span></span>

<span data-ttu-id="5e140-114">Если вы перевели какие-либо устройства в режим обслуживания с помощью командлета Enter-CcUpdate, командлет Exit-CcUpdate позволит вернуть их в рабочий режим.</span><span class="sxs-lookup"><span data-stu-id="5e140-114">If you have appliances that you have put in maintenance mode by specifying the Enter-CcUpdate cmdlet, the Exit-CcUpdate cmdlet will put these back into production mode.</span></span> 
  
<span data-ttu-id="5e140-115">Дополнительные сведения о переводе устройств в режим обслуживания см. в описании командлета Enter-CcUpdate.</span><span class="sxs-lookup"><span data-stu-id="5e140-115">For more information about putting appliances in maintenance mode, see Enter-CcUpdate.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="5e140-116">Типы входных данных</span><span class="sxs-lookup"><span data-stu-id="5e140-116">Input Types</span></span>
<span data-ttu-id="5e140-117"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="5e140-117"></span></span>

<span data-ttu-id="5e140-p101">Нет. Командлет Exit-CcUpdate не принимает входные данные по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="5e140-p101">None. The Exit-CcUpdate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="5e140-120">Типы возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="5e140-120">Return Types</span></span>
<span data-ttu-id="5e140-121"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="5e140-121"></span></span>

<span data-ttu-id="5e140-122">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="5e140-122">None</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="5e140-123">См. также</span><span class="sxs-lookup"><span data-stu-id="5e140-123">See also</span></span>
<span data-ttu-id="5e140-124"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="5e140-124"></span></span>

[<span data-ttu-id="5e140-125">Enter-CcUpdate</span><span class="sxs-lookup"><span data-stu-id="5e140-125">Enter-CcUpdate</span></span>](enter-ccupdate.md)
  

