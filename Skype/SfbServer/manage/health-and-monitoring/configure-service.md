---
title: Настройка службы мобильности для высокой производительности в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: c2b8aadb-cffb-49f0-ba7a-e8541a1ff475
description: Сводка. Сведения о службе мобильности в Skype для бизнеса Server.
ms.openlocfilehash: da2685faae6bf44fee212132dba6a0f7e0fe2e76
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2021
ms.locfileid: "58621035"
---
# <a name="configure-mobility-service-for-high-performance-in-skype-for-business-server"></a>Настройка службы мобильности для высокой производительности в Skype для бизнеса Server
 
**Сводка:** Узнайте о службе мобильности в Skype для бизнеса Server.
  
> [!IMPORTANT]
> Этот раздел применяется только к службе мобильности Skype для бизнеса Server (Mcx) и не применяется к веб-API единой связи (UCWA), как это было подано в накопительных обновлениях для Lync Server 2013: февраль 2013 г. 
  
При установке службы мобильности (Mcx) на службы IIS (IIS) 7.5 установщик службы мобильности настраивает некоторые параметры производительности на переднем сервере. Мы рекомендуем использовать IIS 7.5 для Mobility Service. Параметры влияют на максимальное число одновременных запросов пользователей и максимальное число потоков, которые разрешены для Mobility Service.
  
Ниже параметров производительности:
  
### <a name="settings-for-mcx-on-iis-75"></a>Параметры mcx на IIS 7.5

1. **maxConcurrentThreadsPerCPU** имеет значение нуль (0).
    
2. **maxConcurrentRequestsPerCPU** имеет значение нуль (0).
    
3. Процессная модель ASP.NET имеет значение AutoConfig (только для IIS 7.5).
    
4. Предел очереди HTTP.sys имеет значение 1000 (по умолчанию).
    

