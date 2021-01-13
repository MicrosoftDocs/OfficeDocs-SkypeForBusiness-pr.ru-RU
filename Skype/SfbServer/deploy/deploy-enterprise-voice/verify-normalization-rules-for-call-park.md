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
# <a name="verify-normalization-rules-for-call-park-in-skype-for-business"></a>Проверка правил нормализации для парковки вызовов в Skype для бизнеса
 
Узнайте о правилах нормализации для парковки вызовов в Skype для бизнеса Server Корпоративная голосовая связь.
  
Орбиты парковки вызовов не должны быть нормализованы. Проверьте абонентские группы и убедитесь, что значения орбит не нормализованы. If you must create an additional normalization rule to prevent your orbits from being normalized, follow the procedure in [Create or modify a dial plan in Skype for Business Server](dial-plans.md) to define a new normalization rule, so that Pattern to **match** identifies the orbit range and **Translation pattern** is **$1**. Например, если диапазон орбит парковки вызовов составляет 7000–7999, шаблон для совпадения **^(7\d {3} )$** **и** шаблон перевода **$ 1**. 
  
> [!IMPORTANT]
> Убедитесь, что правило нормализации по умолчанию в ваших наборах не **содержит ^(\d \* ).** В противном случае правило нормализации парковки вызовов никогда не будет работать.
  
## <a name="see-also"></a>См. также

[Создание или изменение телефонной плана в Skype для бизнеса Server](dial-plans.md)

