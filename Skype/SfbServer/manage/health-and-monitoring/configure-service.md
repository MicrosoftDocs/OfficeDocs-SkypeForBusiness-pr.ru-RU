---
title: Настройка службы Mobility Service для высокой производительности в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c2b8aadb-cffb-49f0-ba7a-e8541a1ff475
description: Сводка. Сведения о службе Mobility Service в Skype для бизнеса Server.
ms.openlocfilehash: 83d8d6dc7a32b05a58c738deddc8c92e43bd5557
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817039"
---
# <a name="configure-mobility-service-for-high-performance-in-skype-for-business-server"></a>Настройка службы Mobility Service для высокой производительности в Skype для бизнеса Server
 
**Сводка:** Узнайте о службе Mobility Service в Skype для бизнеса Server.
  
> [!IMPORTANT]
> Этот раздел относится только к Skype для бизнеса Server Mobility Service (Mcx) и не относится к веб-API объединенных коммуникаций (UCWA), как пошаговые обновления для Lync Server 2013: февраль 2013 г. 
  
При установке службы Mobility Service (Mcx) в службах IIS 7.5 установщик Службы Mobility Service настраивает некоторые параметры производительности на сервере переднего сервера. Мы рекомендуем использовать IIS 7.5 для Mobility Service. Параметры влияют на максимальное число одновременных запросов пользователей и максимальное число потоков, которые разрешены для Mobility Service.
  
Ниже параметров производительности.
  
### <a name="settings-for-mcx-on-iis-75"></a>Параметры для Mcx в IIS 7.5

1. **maxConcurrentThreadsPerCPU** имеет значение нуль (0).
    
2. **maxConcurrentRequestsPerCPU** имеет значение нуль (0).
    
3. Процессная модель ASP.NET имеет значение AutoConfig (только для IIS 7.5).
    
4. Предел очереди HTTP.sys имеет значение 1000 (по умолчанию).
    

