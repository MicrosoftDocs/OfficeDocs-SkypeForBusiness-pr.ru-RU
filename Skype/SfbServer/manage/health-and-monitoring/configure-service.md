---
title: Настройка службы мобильности для повышения производительности в Скайп для Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c2b8aadb-cffb-49f0-ba7a-e8541a1ff475
description: ': Сводка сведения о службе мобильности в Скайп для Business Server.'
ms.openlocfilehash: 5031d34a2fdcb1610325afbf58c5524a0ee28ca8
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "21026808"
---
# <a name="configure-mobility-service-for-high-performance-in-skype-for-business-server"></a>Настройка службы мобильности для повышения производительности в Скайп для Business Server
 
**Сводка:** Сведения о службе мобильности в Скайп для Business Server.
  
> [!IMPORTANT]
> В этом разделе относятся только к Скайп для службы Mobility Business Server (Mcx) и не применяется к Unified Communications Web API (UCWA), как в накопительные пакеты обновления для Lync Server 2013: февраля 2013 г. 
  
При установке службы мобильной связи (Mcx) на Internet Information Services (IIS) 7.5 установщика Mobility Service настраивает некоторые параметры производительности на сервере переднего плана. Мы рекомендуем использовать IIS 7.5 для мобильных устройств. Параметры влияют на максимальное число параллельных пользователей запросов и максимальное число потоков, разрешенных для службы Mobility Service.
  
Далее представлены параметры производительности:
  
### <a name="settings-for-mcx-on-iis-75"></a>Параметры для Mcx в службе IIS 7.5

1. **maxConcurrentThreadsPerCPU** имеет значение нуль (0).
    
2. **maxConcurrentRequestsPerCPU** имеет значение нуль (0).
    
3. Процессная модель ASP.NET имеет значение AutoConfig (только для IIS 7.5).
    
4. Предел очереди HTTP.sys имеет значение 1000 (по умолчанию).
    

