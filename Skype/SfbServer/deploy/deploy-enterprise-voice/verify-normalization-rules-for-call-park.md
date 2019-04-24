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
# <a name="verify-normalization-rules-for-call-park-in-skype-for-business"></a>Проверка правил нормализации для парковки вызовов в Скайп для бизнеса
 
Описание правила нормализации для парковки вызовов в Скайп Business Server корпоративной голосовой связи.
  
Орбиты парковки вызовов, не должны быть упорядочены. Check your dial plans to be sure that your orbit numbers are not normalized. Если необходимо создать дополнительное правило нормализации для предотвращения нормализации вашей орбиты, выполните процедуру, описанную в [Создание и изменение абонентской группы в Скайп для Business Server](dial-plans.md) для определения нового правила нормализации, поэтому этот **шаблон для поиска соответствия** Определяет диапазон орбиты и **перевода шаблон** является **$1**. Например, если диапазон орбиты парковки вызовов находится 7000-7999 **шаблон для поиска соответствия** будет **^(7\d{3})$** и **перевода шаблон** является **$1**.
  
> [!IMPORTANT]
> Убедитесь, что по умолчанию правило нормализации в абонентской не содержит **^(\d\*)**. В противном случае правила нормализации парковки вызовов никогда не будет работать.
  
## <a name="see-also"></a>См. также

[Создание или изменение абонентской группы в Скайп для Business Server](dial-plans.md)

