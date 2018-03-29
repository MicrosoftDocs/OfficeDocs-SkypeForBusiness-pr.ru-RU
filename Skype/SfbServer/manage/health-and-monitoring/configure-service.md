---
title: Настройка высокой производительности службы Mobility Service в Skype для бизнеса Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c2b8aadb-cffb-49f0-ba7a-e8541a1ff475
description: ': Сводка сведения о службе мобильности в Скайп для Business Server 2015.'
ms.openlocfilehash: 12f64ed75195bb94365686d76cdfca841e6c9c8e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="configure-mobility-service-for-high-performance-in-skype-for-business-server-2015"></a>Настройка высокой производительности службы Mobility Service в Skype для бизнеса Server 2015
 
**Сводка:** Сведения о службе мобильности в Скайп для Business Server 2015.
  
> [!IMPORTANT]
> В этом разделе относятся только к Скайп для службы Mobility 2015 Business Server (Mcx) и не применяется к Unified Communications Web API (UCWA), как в накопительные пакеты обновления для Lync Server 2013: февраля 2013 г. 
  
При установке службы мобильной связи (Mcx) на Internet Information Services (IIS) 7.5 установщика Mobility Service настраивает некоторые параметры производительности на сервере переднего плана. Мы рекомендуем использовать IIS 7.5 для мобильных устройств. Параметры влияют на максимальное число параллельных пользователей запросов и максимальное число потоков, разрешенных для службы Mobility Service.
  
Далее представлены параметры производительности:
  
### <a name="settings-for-mcx-on-iis-75"></a>Параметры для Mcx в службе IIS 7.5

1. **maxConcurrentThreadsPerCPU** имеет значение нуль (0).
    
2. **maxConcurrentRequestsPerCPU** имеет значение нуль (0).
    
3. Процессная модель ASP.NET имеет значение AutoConfig (только для IIS 7.5).
    
4. Предел очереди HTTP.sys имеет значение 1000 (по умолчанию).
    

