---
title: Планирование подключения к STN в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 280f684a-740a-443d-8ecf-574241382a42
description: Планирование подключения к STN в Корпоративная голосовая связь Skype для бизнеса Server.
ms.openlocfilehash: 492f4e2cc71644cb1e9957f407a549cce5dbc31d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813569"
---
# <a name="plan-for-pstn-connectivity-in-skype-for-business-server"></a>Планирование подключения к STN в Skype для бизнеса Server
 
Планирование подключения к STN в Корпоративная голосовая связь Skype для бизнеса Server.
  
Решение VoIP корпоративного уровня должно обеспечивать вызовы в телефонную сеть общего пользования (ТСОП) и обратно без ухудшения качества обслуживания (QoS). Пользователи, которые звонят и получают звонки, не должны знать об этой технологии: с точки зрения пользователя вызов между инфраструктурой Корпоративная голосовая связь и STN должен выглядеть как другой телефонный звонок.
  
Skype для бизнеса Server обеспечивает надежное масштабируемое подключение к STN с помощью следующих параметров:
  
- **SIP-магистрали** для поставщика услуг Интернет-телефонии (ITSP);
    
- **прямые SIP-подключения** для шлюза ТСОП;
    
- **прямые SIP-подключения** для УАТС.
    
В зависимости от размера, географического покрытия и существующей инфраструктуры системы голосовой связи предприятия могут использовать один, два или даже все три этих варианта в различных местоположениях. Подробные сведения об этих параметрах см. в следующих разделах.
  
## <a name="in-this-section"></a>В этом разделе:

- [Транкинг SIP в Skype для бизнеса Server](sip-trunking.md)
    
- [Прямые подключения SIP в Skype для бизнеса Server](direct-sip.md)
    
- [Магистраль M:N в Skype для бизнеса Server](m-n-trunk.md)
    
- [Правила трансляции в Skype для бизнеса Server](translation-rules.md)
    
- [Планирование маршрутной исходящие голосовой почты в Skype для бизнеса Server](outbound-voice-routing.md)
    

