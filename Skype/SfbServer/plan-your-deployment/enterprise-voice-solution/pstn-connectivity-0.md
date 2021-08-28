---
title: Планирование подключения к PSTN в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 280f684a-740a-443d-8ecf-574241382a42
description: Планирование подключения к PSTN в Корпоративная голосовая связь в Skype для бизнеса Server.
ms.openlocfilehash: 803b613e3b78465f1dd8d9d04fd552b8bee553d1
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2021
ms.locfileid: "58593543"
---
# <a name="plan-for-pstn-connectivity-in-skype-for-business-server"></a>Планирование подключения к PSTN в Skype для бизнеса Server
 
Планирование подключения к PSTN в Корпоративная голосовая связь в Skype для бизнеса Server.
  
Решение VoIP корпоративного уровня должно обеспечивать вызовы в телефонную сеть общего пользования (ТСОП) и обратно без ухудшения качества обслуживания (QoS). Пользователи, которые находят и получают вызовы, не должны знать об этой технологии: с точки зрения пользователя вызов между инфраструктурой Корпоративная голосовая связь и службой PSTN должен казаться очередным телефонным вызовом.
  
Skype для бизнеса Server обеспечивает надежное масштабируемое подключение к PSTN с помощью следующих параметров:
  
- **SIP-магистрали** для поставщика услуг Интернет-телефонии (ITSP);
    
- **прямые SIP-подключения** для шлюза ТСОП;
    
- **прямые SIP-подключения** для УАТС.
    
В зависимости от размера, географического покрытия и существующей инфраструктуры системы голосовой связи предприятия могут использовать один, два или даже все три этих варианта в различных местоположениях. Подробные сведения об этих параметрах см. в следующих разделах.
  
## <a name="in-this-section"></a>В этой статье

- [Магистраль SIP в Skype для бизнеса Server](sip-trunking.md)
    
- [Прямые подключения SIP в Skype для бизнеса Server](direct-sip.md)
    
- [Магистраль M:N в Skype для бизнеса Server](m-n-trunk.md)
    
- [Правила перевода в Skype для бизнеса Server](translation-rules.md)
    
- [Планирование маршрутивки исходящие голосовой почты в Skype для бизнеса Server](outbound-voice-routing.md)
    

