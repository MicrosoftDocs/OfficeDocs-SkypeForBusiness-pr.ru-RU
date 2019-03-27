---
title: Настройка службы мобильности для повышения производительности в Скайп для Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c2b8aadb-cffb-49f0-ba7a-e8541a1ff475
description: ': Сводка сведения о службе мобильности в Скайп для Business Server.'
ms.openlocfilehash: 3e3f0df7550a64236335108453f0c35d902a1713
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30876410"
---
# <a name="configure-mobility-service-for-high-performance-in-skype-for-business-server"></a>Настройка службы мобильности для повышения производительности в Скайп для Business Server
 
**Сводка:** Сведения о службе мобильности в Скайп для Business Server.
  
> [!IMPORTANT]
> В этом разделе относятся только к Скайп для службы Mobility Business Server (Mcx) и не применяется к Unified Communications Web API (UCWA), как в накопительные пакеты обновления для Lync Server 2013: февраля 2013 г. 
  
При установке службы мобильной связи (Mcx) на Internet Information Services (IIS) 7.5 установщика Mobility Service настраивает некоторые параметры производительности на сервере переднего плана. We recommend that you use IIS 7.5 for mobility. The settings affect the maximum number of concurrent user requests and the maximum number of threads that are allowed for the Mobility Service.
  
Далее представлены параметры производительности:
  
### <a name="settings-for-mcx-on-iis-75"></a>Параметры для Mcx в службе IIS 7.5

1. **maxConcurrentThreadsPerCPU** имеет значение нуля (0).
    
2. **maxConcurrentRequestsPerCPU** имеет значение нуля (0).
    
3. Процессная модель ASP.NET имеет значение AutoConfig (только для IIS 7.5).
    
4. Предел очереди HTTP.sys имеет значение 1000 (по умолчанию).
    

