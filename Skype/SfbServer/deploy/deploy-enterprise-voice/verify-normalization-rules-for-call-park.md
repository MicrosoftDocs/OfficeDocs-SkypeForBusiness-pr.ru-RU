---
title: Проверка правил нормализации для приостановки звонка в Skype для бизнеса
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: deaa170f-041e-45cb-8eab-f02931ab541e
description: Узнайте о правилах нормализации для приостановки звонков в Skype для бизнеса Server Enterprise.
ms.openlocfilehash: 36e9a91ff1269caffb8eab5be9a2c681d3244b31
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34300939"
---
# <a name="verify-normalization-rules-for-call-park-in-skype-for-business"></a><span data-ttu-id="55c7f-103">Проверка правил нормализации для приостановки звонка в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="55c7f-103">Verify normalization rules for Call Park in Skype for Business</span></span>
 
<span data-ttu-id="55c7f-104">Узнайте о правилах нормализации для приостановки звонков в Skype для бизнеса Server Enterprise.</span><span class="sxs-lookup"><span data-stu-id="55c7f-104">Learn about normalization rules for Call Park in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="55c7f-105">Орбиты для приостановки звонка не должны быть нормализованы.</span><span class="sxs-lookup"><span data-stu-id="55c7f-105">Call Park orbits must not be normalized.</span></span> <span data-ttu-id="55c7f-106">Check your dial plans to be sure that your orbit numbers are not normalized.</span><span class="sxs-lookup"><span data-stu-id="55c7f-106">Check your dial plans to be sure that your orbit numbers are not normalized.</span></span> <span data-ttu-id="55c7f-107">Если необходимо создать дополнительное правило нормализации, чтобы не допустить нормализации орбиты, выполните действия, описанные в разделе [Создание или изменение абонентской группы в Skype для бизнеса Server](dial-plans.md) , чтобы определить новое правило нормализации, чтобы он **соответствовал шаблону** . Определяет диапазон орбиты и **шаблон перевода** — **$1**.</span><span class="sxs-lookup"><span data-stu-id="55c7f-107">If you must create an additional normalization rule to prevent your orbits from being normalized, follow the procedure in [Create or modify a dial plan in Skype for Business Server](dial-plans.md) to define a new normalization rule, so that **Pattern to match** identifies the orbit range and **Translation pattern** is **$1**.</span></span> <span data-ttu-id="55c7f-108">Например, если диапазон поворотной на расстоянии по орбите — 7000-7999, **шаблон должен соответствовать** **^ (7 \ d{3}) $** , а **шаблон перевода** — **$1**.</span><span class="sxs-lookup"><span data-stu-id="55c7f-108">For example, if your Call Park orbit range is 7000 - 7999, the **Pattern to match** is **^(7\d{3})$** and **Translation pattern** is **$1**.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="55c7f-109">Убедитесь в том, что правило нормализации по умолчанию в абонентских планах не содержит **^ (\d\*)**.</span><span class="sxs-lookup"><span data-stu-id="55c7f-109">Be sure that the default normalization rule in your dial plans does not contain **^(\d\*)**.</span></span> <span data-ttu-id="55c7f-110">В противном случае правило нормализации для приостановки вызова никогда не будет выполняться.</span><span class="sxs-lookup"><span data-stu-id="55c7f-110">Otherwise, your Call Park normalization rule will never run.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="55c7f-111">См. также</span><span class="sxs-lookup"><span data-stu-id="55c7f-111">See also</span></span>

[<span data-ttu-id="55c7f-112">Создание и изменение абонентской группы в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="55c7f-112">Create or modify a dial plan in Skype for Business Server</span></span>](dial-plans.md)

