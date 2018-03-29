---
title: Выход CcUpdate
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
ms.openlocfilehash: f7b913fd6aaa77a18df66fd86a36d5d4838f69d4
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="exit-ccupdate"></a><span data-ttu-id="c0a01-103">Выход CcUpdate</span><span class="sxs-lookup"><span data-stu-id="c0a01-103">Exit-CcUpdate</span></span>
 
<span data-ttu-id="c0a01-104">Командлет Exit-CcUpdate обновляет режим обслуживания на сервере узла Skype для бизнеса Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="c0a01-104">The Exit-CcUpdate cmdlet exits update maintenance mode on the Skype for Business Cloud Connector Edition host server.</span></span> 
  
<span data-ttu-id="c0a01-105">Этот командлет применяется к версии Skype для бизнеса Cloud Connector Edition 1.4.1, 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="c0a01-105">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span> 
  
```
Exit-CcUpdate
```

## <a name="parameters"></a><span data-ttu-id="c0a01-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="c0a01-106">Parameters</span></span>

<span data-ttu-id="c0a01-107">Нет</span><span class="sxs-lookup"><span data-stu-id="c0a01-107">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="c0a01-108">Примеры</span><span class="sxs-lookup"><span data-stu-id="c0a01-108">Examples</span></span>
<span data-ttu-id="c0a01-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="c0a01-109"></span></span>

### <a name="example-1"></a><span data-ttu-id="c0a01-110">Пример 1</span><span class="sxs-lookup"><span data-stu-id="c0a01-110">Example 1</span></span>

<span data-ttu-id="c0a01-111">Следующая команда переводит устройство, на котором она выполняется, в рабочий режим:</span><span class="sxs-lookup"><span data-stu-id="c0a01-111">The following command puts the appliance on which it runs back into production mode:</span></span> 
  
```
Exit-CcUpdate
```

## <a name="detailed-description"></a><span data-ttu-id="c0a01-112">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="c0a01-112">Detailed Description</span></span>
<span data-ttu-id="c0a01-113"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="c0a01-113"></span></span>

<span data-ttu-id="c0a01-114">Если вы перевели какие-либо устройства в режим обслуживания с помощью командлета Enter-CcUpdate, командлет Exit-CcUpdate позволит вернуть их в рабочий режим.</span><span class="sxs-lookup"><span data-stu-id="c0a01-114">If you have appliances that you have put in maintenance mode by specifying the Enter-CcUpdate cmdlet, the Exit-CcUpdate cmdlet will put these back into production mode.</span></span> 
  
<span data-ttu-id="c0a01-115">Дополнительные сведения о переводе устройств в режим обслуживания см. в описании командлета Enter-CcUpdate.</span><span class="sxs-lookup"><span data-stu-id="c0a01-115">For more information about putting appliances in maintenance mode, see Enter-CcUpdate.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="c0a01-116">Типы входных данных</span><span class="sxs-lookup"><span data-stu-id="c0a01-116">Input Types</span></span>
<span data-ttu-id="c0a01-117"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="c0a01-117"></span></span>

<span data-ttu-id="c0a01-p101">Нет. Командлет Exit-CcUpdate не принимает входные данные по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="c0a01-p101">None. The Exit-CcUpdate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="c0a01-120">Типы возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="c0a01-120">Return Types</span></span>
<span data-ttu-id="c0a01-121"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="c0a01-121"></span></span>

<span data-ttu-id="c0a01-122">Нет</span><span class="sxs-lookup"><span data-stu-id="c0a01-122">None</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="c0a01-123">См. также</span><span class="sxs-lookup"><span data-stu-id="c0a01-123">See also</span></span>
<span data-ttu-id="c0a01-124"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="c0a01-124"></span></span>

[<span data-ttu-id="c0a01-125">Введите CcUpdate</span><span class="sxs-lookup"><span data-stu-id="c0a01-125">Enter-CcUpdate</span></span>](enter-ccupdate.md)
  

