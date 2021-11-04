---
title: Проверка правил нормализации для call Park в Skype для бизнеса
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
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
ms.openlocfilehash: ca76c15d7f71afa75e9b9247eab9cd96e5baedb0
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/04/2021
ms.locfileid: "60771534"
---
# <a name="verify-normalization-rules-for-call-park-in-skype-for-business"></a>Проверка правил нормализации для call Park в Skype для бизнеса
 
Узнайте о правилах нормализации для call Park в Skype для бизнеса Server Корпоративная голосовая связь.
  
Орбиты Call Park не должны быть нормализованы. Проверьте абонентские группы и убедитесь, что значения орбит не нормализованы. Если необходимо создать дополнительное правило нормализации, чтобы не допустить нормализации орбит, выполните процедуру в Create or [modify a dial plan in Skype для бизнеса Server,](dial-plans.md) чтобы  определить новое правило нормализации, чтобы **шаблон,** чтобы соответствовать, определяет диапазон орбиты и шаблон перевода **составляет $1**. Например, если диапазон орбиты парка вызовов составляет от 7000 до 7999, шаблон  для совпадения является **^(7\d {3} )$** и шаблон перевода **$ 1**. 
  
> [!IMPORTANT]
> Убедитесь, что правило нормализации по умолчанию в планах набора не содержит **^(\d). \*** В противном случае правило нормализации call Park никогда не будет работать.
  
## <a name="see-also"></a>См. также

[Создание или изменение набора номера в Skype для бизнеса Server](dial-plans.md)

