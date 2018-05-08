---
title: Планирование связи с ТСОП в Skype для бизнеса Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 280f684a-740a-443d-8ecf-574241382a42
description: Планирование подключения к ТСОП в корпоративной голосовой связи в Скайп Business Server.
ms.openlocfilehash: 228391049988c2eb886c0cb4e7caccce6f55ff3b
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="plan-for-pstn-connectivity-in-skype-for-business-server-2015"></a>Планирование связи с ТСОП в Skype для бизнеса Server 2015
 
Планирование подключения к ТСОП в корпоративной голосовой связи в Скайп Business Server.
  
Решение VoIP корпоративного класса должно обеспечивать вызовы в телефонную сеть общего пользования (ТСОП) и из нее без ухудшения качества обслуживания (QoS). Пользователи, выполнять и принимать вызовы его не следует принять во внимание базовую технологию: с точки зрения пользователя инфраструктурой корпоративной голосовой связи и наоборот PSTN должны показаться любой другой телефонный звонок.
  
Скайп для Business Server обеспечивает надежное, масштабируемое подключение к ТСОП с помощью следующих параметров:
  
- **магистрали SIP**, соединяющие с оператором телефонной связи по сети Интернет;
    
- **прямые подключения SIP** к шлюзу ТСОП;
    
- **прямые подключения SIP** к УАТС.
    
В зависимости от размеров предприятия, охватываемой территории и существующей инфраструктуры голосовой связи можно применять один и тот же способ на всем предприятии либо два или все три способа в разных подразделениях. Сведения о каждом способе см. в следующих разделах.
  
## <a name="in-this-section"></a>Содержание

- [SIP-магистрали в Скайп для Business Server 2015](sip-trunking.md)
    
- [Прямые SIP-подключения в Скайп для Business Server 2015](direct-sip.md)
    
- [Магистраль m: n в Скайп для Business Server 2015](m-n-trunk.md)
    
- [Правила преобразования в Скайп для Business Server 2015](translation-rules.md)
    
- [Планирование маршрутизации исходящей голосовой почты в Скайп для Business Server 2015](outbound-voice-routing.md)
    

