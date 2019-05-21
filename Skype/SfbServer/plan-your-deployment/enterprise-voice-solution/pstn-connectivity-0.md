---
title: Планирование подключения к PSTN в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 280f684a-740a-443d-8ecf-574241382a42
description: Планирование подключений PSTN в корпоративной голосовой связи в Skype для бизнеса Server.
ms.openlocfilehash: f0b6aa6b43562fea91885b0d55d75fd234ab97de
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34276499"
---
# <a name="plan-for-pstn-connectivity-in-skype-for-business-server"></a>Планирование подключения к PSTN в Skype для бизнеса Server
 
Планирование подключений PSTN в корпоративной голосовой связи в Skype для бизнеса Server.
  
Решение VoIP корпоративного уровня должно предусматривать входящие и исходящие вызовы на телефонную сеть общего пользования (ТСОП) без какого-либо снижения качества обслуживания (QoS). Пользователи, которые размещаются и принимают звонки, не должны знать о базовой технологии: с точки зрения пользователя, Звонок между корпоративной инфраструктурой голосовой связи и PSTN должен казаться просто другим телефонным звонком.
  
Skype для бизнеса Server обеспечивает надежную и масштабируемую КОММУТИРУЕМую связь с помощью следующих параметров:
  
- **магистрали SIP**, соединяющие с оператором телефонной связи по сети Интернет;
    
- **прямые подключения SIP** к шлюзу ТСОП;
    
- **прямые подключения SIP** к УАТС.
    
В зависимости от размеров предприятия, охватываемой территории и существующей инфраструктуры голосовой связи можно применять один и тот же способ на всем предприятии либо два или все три способа в разных подразделениях. Сведения о каждом способе см. в следующих разделах.
  
## <a name="in-this-section"></a>Содержание

- [Магистральные линии SIP в Skype для бизнеса Server](sip-trunking.md)
    
- [Прямые подключения по протоколу SIP в Skype для бизнеса Server](direct-sip.md)
    
- [М:Н магистраль в Skype для бизнеса Server](m-n-trunk.md)
    
- [Правила трансляции в Skype для бизнеса Server](translation-rules.md)
    
- [Планирование исходящей голосовой маршрутизации в Skype для бизнеса Server](outbound-voice-routing.md)
    

