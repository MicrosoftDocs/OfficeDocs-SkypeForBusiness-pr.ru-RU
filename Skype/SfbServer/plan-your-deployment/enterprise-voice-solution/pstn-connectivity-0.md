---
title: Планирование подключения к ТСОП в Скайп Business Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 280f684a-740a-443d-8ecf-574241382a42
description: Планирование подключения к ТСОП в корпоративной голосовой связи в Скайп Business Server.
ms.openlocfilehash: d98955795ef5172065027a1fab9030091ee11b11
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30878037"
---
# <a name="plan-for-pstn-connectivity-in-skype-for-business-server"></a>Планирование подключения к ТСОП в Скайп Business Server
 
Планирование подключения к ТСОП в корпоративной голосовой связи в Скайп Business Server.
  
Решение VoIP корпоративного уровня должно предусматривать входящие и исходящие вызовы на телефонную сеть общего пользования (ТСОП) без какого-либо снижения качества обслуживания (QoS). Пользователи, выполнять и принимать вызовы его не следует принять во внимание базовую технологию: с точки зрения пользователя инфраструктурой корпоративной голосовой связи и наоборот PSTN должны показаться любой другой телефонный звонок.
  
Скайп для Business Server обеспечивает надежное, масштабируемое подключение к ТСОП с помощью следующих параметров:
  
- **магистрали SIP**, соединяющие с оператором телефонной связи по сети Интернет;
    
- **прямые подключения SIP** к шлюзу ТСОП;
    
- **прямые подключения SIP** к УАТС.
    
В зависимости от размеров предприятия, охватываемой территории и существующей инфраструктуры голосовой связи можно применять один и тот же способ на всем предприятии либо два или все три способа в разных подразделениях. Сведения о каждом способе см. в следующих разделах.
  
## <a name="in-this-section"></a>Содержание

- [SIP-магистрали в Скайп для Business Server](sip-trunking.md)
    
- [Прямые SIP-подключения в Скайп для Business Server](direct-sip.md)
    
- [Магистраль m: n в Скайп для Business Server](m-n-trunk.md)
    
- [Правила преобразования в Скайп для Business Server](translation-rules.md)
    
- [Планирование маршрутизации исходящей голосовой почты в Скайп для Business Server](outbound-voice-routing.md)
    

