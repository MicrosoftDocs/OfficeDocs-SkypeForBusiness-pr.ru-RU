---
title: Проверка правил нормализации для приостановки звонка в Skype для бизнеса
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Узнайте о правилах нормализации для приостановки звонков в Skype для бизнеса Server Enterprise.
ms.openlocfilehash: 769d9f9becccf4df24a33a11e8814350cfb091e8
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41766892"
---
# <a name="verify-normalization-rules-for-call-park-in-skype-for-business"></a><span data-ttu-id="d54b7-103">Проверка правил нормализации для приостановки звонка в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="d54b7-103">Verify normalization rules for Call Park in Skype for Business</span></span>
 
<span data-ttu-id="d54b7-104">Узнайте о правилах нормализации для приостановки звонков в Skype для бизнеса Server Enterprise.</span><span class="sxs-lookup"><span data-stu-id="d54b7-104">Learn about normalization rules for Call Park in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="d54b7-105">Орбиты для приостановки звонка не должны быть нормализованы.</span><span class="sxs-lookup"><span data-stu-id="d54b7-105">Call Park orbits must not be normalized.</span></span> <span data-ttu-id="d54b7-106">Check your dial plans to be sure that your orbit numbers are not normalized.</span><span class="sxs-lookup"><span data-stu-id="d54b7-106">Check your dial plans to be sure that your orbit numbers are not normalized.</span></span> <span data-ttu-id="d54b7-107">Если необходимо создать дополнительное правило нормализации, чтобы не допустить нормализации орбиты, выполните действия, описанные в разделе [Создание или изменение абонентской группы в Skype для бизнеса Server](dial-plans.md) , чтобы определить новое правило нормализации, чтобы **шаблон соответствовал** диапазону орбиты и **шаблон перевода** — **$1**.</span><span class="sxs-lookup"><span data-stu-id="d54b7-107">If you must create an additional normalization rule to prevent your orbits from being normalized, follow the procedure in [Create or modify a dial plan in Skype for Business Server](dial-plans.md) to define a new normalization rule, so that **Pattern to match** identifies the orbit range and **Translation pattern** is **$1**.</span></span> <span data-ttu-id="d54b7-108">Например, если диапазон поворотной на расстоянии по орбите — 7000-7999, **шаблон должен соответствовать** **^ (7 \ d{3}) $** , а **шаблон перевода** — **$1**.</span><span class="sxs-lookup"><span data-stu-id="d54b7-108">For example, if your Call Park orbit range is 7000 - 7999, the **Pattern to match** is **^(7\d{3})$** and **Translation pattern** is **$1**.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="d54b7-109">Убедитесь в том, что правило нормализации по умолчанию в абонентских планах не содержит **^ (\d\*)**.</span><span class="sxs-lookup"><span data-stu-id="d54b7-109">Be sure that the default normalization rule in your dial plans does not contain **^(\d\*)**.</span></span> <span data-ttu-id="d54b7-110">В противном случае правило нормализации для приостановки вызова никогда не будет выполняться.</span><span class="sxs-lookup"><span data-stu-id="d54b7-110">Otherwise, your Call Park normalization rule will never run.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d54b7-111">См. также</span><span class="sxs-lookup"><span data-stu-id="d54b7-111">See also</span></span>

[<span data-ttu-id="d54b7-112">Создание и изменение абонентской группы в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="d54b7-112">Create or modify a dial plan in Skype for Business Server</span></span>](dial-plans.md)

