---
title: Проверка правил нормализации для парковки вызовов в Skype для бизнеса
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: deaa170f-041e-45cb-8eab-f02931ab541e
description: Узнайте о правилах нормализации для парковки вызовов в Skype для бизнеса Server Корпоративная голосовая связь.
ms.openlocfilehash: d1bcd6817b1f59f73a8c4ef1562e90253a99bd30
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830579"
---
# <a name="verify-normalization-rules-for-call-park-in-skype-for-business"></a><span data-ttu-id="5e413-103">Проверка правил нормализации для парковки вызовов в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="5e413-103">Verify normalization rules for Call Park in Skype for Business</span></span>
 
<span data-ttu-id="5e413-104">Узнайте о правилах нормализации для парковки вызовов в Skype для бизнеса Server Корпоративная голосовая связь.</span><span class="sxs-lookup"><span data-stu-id="5e413-104">Learn about normalization rules for Call Park in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="5e413-105">Орбиты парковки вызовов не должны быть нормализованы.</span><span class="sxs-lookup"><span data-stu-id="5e413-105">Call Park orbits must not be normalized.</span></span> <span data-ttu-id="5e413-106">Проверьте абонентские группы и убедитесь, что значения орбит не нормализованы.</span><span class="sxs-lookup"><span data-stu-id="5e413-106">Check your dial plans to be sure that your orbit numbers are not normalized.</span></span> <span data-ttu-id="5e413-107">If you must create an additional normalization rule to prevent your orbits from being normalized, follow the procedure in [Create or modify a dial plan in Skype for Business Server](dial-plans.md) to define a new normalization rule, so that Pattern to **match** identifies the orbit range and **Translation pattern** is **$1**.</span><span class="sxs-lookup"><span data-stu-id="5e413-107">If you must create an additional normalization rule to prevent your orbits from being normalized, follow the procedure in [Create or modify a dial plan in Skype for Business Server](dial-plans.md) to define a new normalization rule, so that **Pattern to match** identifies the orbit range and **Translation pattern** is **$1**.</span></span> <span data-ttu-id="5e413-108">Например, если диапазон орбит парковки вызовов составляет 7000–7999, шаблон для совпадения **^(7\d {3} )$** **и** шаблон перевода **$ 1**. </span><span class="sxs-lookup"><span data-stu-id="5e413-108">For example, if your Call Park orbit range is 7000 - 7999, the **Pattern to match** is **^(7\d{3})$** and **Translation pattern** is **$1**.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="5e413-109">Убедитесь, что правило нормализации по умолчанию в ваших наборах не **содержит ^(\d \* ).**</span><span class="sxs-lookup"><span data-stu-id="5e413-109">Be sure that the default normalization rule in your dial plans does not contain **^(\d\*)**.</span></span> <span data-ttu-id="5e413-110">В противном случае правило нормализации парковки вызовов никогда не будет работать.</span><span class="sxs-lookup"><span data-stu-id="5e413-110">Otherwise, your Call Park normalization rule will never run.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5e413-111">См. также</span><span class="sxs-lookup"><span data-stu-id="5e413-111">See also</span></span>

[<span data-ttu-id="5e413-112">Создание или изменение телефонной плана в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="5e413-112">Create or modify a dial plan in Skype for Business Server</span></span>](dial-plans.md)

