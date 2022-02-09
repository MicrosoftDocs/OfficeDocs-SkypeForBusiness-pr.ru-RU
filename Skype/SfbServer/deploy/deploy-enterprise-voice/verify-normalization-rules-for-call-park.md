---
title: Проверка правил нормализации для call Park в Skype для бизнеса
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: deaa170f-041e-45cb-8eab-f02931ab541e
description: Узнайте о правилах нормализации для call Park в Skype для бизнеса Server Корпоративная голосовая связь.
ms.openlocfilehash: 35ffdfd6fe7e4289ebb4fa0ecd6cef9a26256bb0
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/05/2022
ms.locfileid: "62404361"
---
# <a name="verify-normalization-rules-for-call-park-in-skype-for-business"></a>Проверка правил нормализации для call Park в Skype для бизнеса
 
Узнайте о правилах нормализации для call Park в Skype для бизнеса Server Корпоративная голосовая связь.
  
Орбиты Call Park не должны быть нормализованы. Проверьте абонентские группы и убедитесь, что значения орбит не нормализованы. Если необходимо создать дополнительное правило нормализации, чтобы не допустить нормализации орбит, выполните процедуру в Create or [modify a dial plan in Skype для бизнеса Server](dial-plans.md), чтобы определить новое правило нормализации, чтобы **шаблон**, чтобы соответствовать, определяет диапазон орбиты и шаблон перевода составляет  **$1**. Например, если диапазон орбиты парка вызовов составляет 7000 — 7999, шаблон для совпадения — **^(7\d{3})$**, а шаблон перевода  — **$1**.
  
> [!IMPORTANT]
> Убедитесь, что правило нормализации по умолчанию в планах набора не содержит **^(\d\*)**. В противном случае правило нормализации call Park никогда не будет работать.
  
## <a name="see-also"></a>См. также

[Создание или изменение набора номера в Skype для бизнеса Server](dial-plans.md)

