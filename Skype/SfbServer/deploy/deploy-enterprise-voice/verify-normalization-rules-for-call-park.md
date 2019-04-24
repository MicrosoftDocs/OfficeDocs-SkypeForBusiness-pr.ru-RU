---
title: Проверка правил нормализации для парковки вызовов в Скайп для бизнеса
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: deaa170f-041e-45cb-8eab-f02931ab541e
description: Описание правила нормализации для парковки вызовов в Скайп Business Server корпоративной голосовой связи.
ms.openlocfilehash: 794d64efcefbc4b36fac84e6356df46df76dc5a2
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32222557"
---
# <a name="verify-normalization-rules-for-call-park-in-skype-for-business"></a><span data-ttu-id="d1bb4-103">Проверка правил нормализации для парковки вызовов в Скайп для бизнеса</span><span class="sxs-lookup"><span data-stu-id="d1bb4-103">Verify normalization rules for Call Park in Skype for Business</span></span>
 
<span data-ttu-id="d1bb4-104">Описание правила нормализации для парковки вызовов в Скайп Business Server корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="d1bb4-104">Learn about normalization rules for Call Park in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="d1bb4-105">Орбиты парковки вызовов, не должны быть упорядочены.</span><span class="sxs-lookup"><span data-stu-id="d1bb4-105">Call Park orbits must not be normalized.</span></span> <span data-ttu-id="d1bb4-106">Check your dial plans to be sure that your orbit numbers are not normalized.</span><span class="sxs-lookup"><span data-stu-id="d1bb4-106">Check your dial plans to be sure that your orbit numbers are not normalized.</span></span> <span data-ttu-id="d1bb4-107">Если необходимо создать дополнительное правило нормализации для предотвращения нормализации вашей орбиты, выполните процедуру, описанную в [Создание и изменение абонентской группы в Скайп для Business Server](dial-plans.md) для определения нового правила нормализации, поэтому этот **шаблон для поиска соответствия** Определяет диапазон орбиты и **перевода шаблон** является **$1**.</span><span class="sxs-lookup"><span data-stu-id="d1bb4-107">If you must create an additional normalization rule to prevent your orbits from being normalized, follow the procedure in [Create or modify a dial plan in Skype for Business Server](dial-plans.md) to define a new normalization rule, so that **Pattern to match** identifies the orbit range and **Translation pattern** is **$1**.</span></span> <span data-ttu-id="d1bb4-108">Например, если диапазон орбиты парковки вызовов находится 7000-7999 **шаблон для поиска соответствия** будет **^(7\d{3})$** и **перевода шаблон** является **$1**.</span><span class="sxs-lookup"><span data-stu-id="d1bb4-108">For example, if your Call Park orbit range is 7000 - 7999, the **Pattern to match** is **^(7\d{3})$** and **Translation pattern** is **$1**.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="d1bb4-109">Убедитесь, что по умолчанию правило нормализации в абонентской не содержит **^(\d\*)**.</span><span class="sxs-lookup"><span data-stu-id="d1bb4-109">Be sure that the default normalization rule in your dial plans does not contain **^(\d\*)**.</span></span> <span data-ttu-id="d1bb4-110">В противном случае правила нормализации парковки вызовов никогда не будет работать.</span><span class="sxs-lookup"><span data-stu-id="d1bb4-110">Otherwise, your Call Park normalization rule will never run.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d1bb4-111">См. также</span><span class="sxs-lookup"><span data-stu-id="d1bb4-111">See also</span></span>

[<span data-ttu-id="d1bb4-112">Создание или изменение абонентской группы в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="d1bb4-112">Create or modify a dial plan in Skype for Business Server</span></span>](dial-plans.md)

