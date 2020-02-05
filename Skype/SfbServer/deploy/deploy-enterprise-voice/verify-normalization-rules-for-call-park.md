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
# <a name="verify-normalization-rules-for-call-park-in-skype-for-business"></a>Проверка правил нормализации для приостановки звонка в Skype для бизнеса
 
Узнайте о правилах нормализации для приостановки звонков в Skype для бизнеса Server Enterprise.
  
Орбиты для приостановки звонка не должны быть нормализованы. Check your dial plans to be sure that your orbit numbers are not normalized. Если необходимо создать дополнительное правило нормализации, чтобы не допустить нормализации орбиты, выполните действия, описанные в разделе [Создание или изменение абонентской группы в Skype для бизнеса Server](dial-plans.md) , чтобы определить новое правило нормализации, чтобы **шаблон соответствовал** диапазону орбиты и **шаблон перевода** — **$1**. Например, если диапазон поворотной на расстоянии по орбите — 7000-7999, **шаблон должен соответствовать** **^ (7 \ d{3}) $** , а **шаблон перевода** — **$1**.
  
> [!IMPORTANT]
> Убедитесь в том, что правило нормализации по умолчанию в абонентских планах не содержит **^ (\d\*)**. В противном случае правило нормализации для приостановки вызова никогда не будет выполняться.
  
## <a name="see-also"></a>См. также

[Создание и изменение абонентской группы в Skype для бизнеса Server](dial-plans.md)

