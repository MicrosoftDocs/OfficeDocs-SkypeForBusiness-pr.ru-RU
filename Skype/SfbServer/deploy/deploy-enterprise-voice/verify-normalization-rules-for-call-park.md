---
title: Проверка правил нормализации для call Park в Skype для бизнеса
ms.reviewer: ''
ms.author: v-cichur
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
ms.openlocfilehash: f60f334efa8907618c0b67f61faaaa3b444e9c47
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2021
ms.locfileid: "58616985"
---
# <a name="verify-normalization-rules-for-call-park-in-skype-for-business"></a>Проверка правил нормализации для call Park в Skype для бизнеса
 
Узнайте о правилах нормализации для call Park в Skype для бизнеса Server Корпоративная голосовая связь.
  
Орбиты Call Park не должны быть нормализованы. Проверьте абонентские группы и убедитесь, что значения орбит не нормализованы. Если необходимо создать дополнительное правило нормализации, чтобы не допустить нормализации орбит, выполните процедуру в Create or [modify a dial plan in Skype для бизнеса Server,](dial-plans.md) чтобы  определить новое правило нормализации, чтобы **шаблон,** чтобы соответствовать, определяет диапазон орбиты и шаблон перевода **составляет $1**. Например, если диапазон орбиты парка вызовов составляет от 7000 до 7999, шаблон  для совпадения является **^(7\d {3} )$** и шаблон перевода **$ 1**. 
  
> [!IMPORTANT]
> Убедитесь, что правило нормализации по умолчанию в планах набора не содержит **^(\d). \*** В противном случае правило нормализации call Park никогда не будет работать.
  
## <a name="see-also"></a>См. также

[Создание или изменение набора номера в Skype для бизнеса Server](dial-plans.md)

