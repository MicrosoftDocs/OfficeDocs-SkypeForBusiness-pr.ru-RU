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
# <a name="verify-normalization-rules-for-call-park-in-skype-for-business"></a>Проверка правил нормализации для приостановки звонка в Skype для бизнеса
 
Узнайте о правилах нормализации для приостановки звонков в Skype для бизнеса Server Enterprise.
  
Орбиты для приостановки звонка не должны быть нормализованы. Check your dial plans to be sure that your orbit numbers are not normalized. Если необходимо создать дополнительное правило нормализации, чтобы не допустить нормализации орбиты, выполните действия, описанные в разделе [Создание или изменение абонентской группы в Skype для бизнеса Server](dial-plans.md) , чтобы определить новое правило нормализации, чтобы он **соответствовал шаблону** . Определяет диапазон орбиты и **шаблон перевода** — **$1**. Например, если диапазон поворотной на расстоянии по орбите — 7000-7999, **шаблон должен соответствовать** **^ (7 \ d{3}) $** , а **шаблон перевода** — **$1**.
  
> [!IMPORTANT]
> Убедитесь в том, что правило нормализации по умолчанию в абонентских планах не содержит **^ (\d\*)**. В противном случае правило нормализации для приостановки вызова никогда не будет выполняться.
  
## <a name="see-also"></a>См. также

[Создание и изменение абонентской группы в Skype для бизнеса Server](dial-plans.md)

