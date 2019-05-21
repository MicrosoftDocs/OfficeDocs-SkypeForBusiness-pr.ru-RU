---
title: Настройка службы Mobility Service для высокой производительности в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c2b8aadb-cffb-49f0-ba7a-e8541a1ff475
description: 'Сводка: сведения о службе Mobility Service в Skype для бизнеса Server.'
ms.openlocfilehash: 35e04fa080964495ccd9abed28c0688dd7be45a9
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34305845"
---
# <a name="configure-mobility-service-for-high-performance-in-skype-for-business-server"></a>Настройка службы Mobility Service для высокой производительности в Skype для бизнеса Server
 
**Сводка:** Узнайте о службе Mobility Service в Skype для бизнеса Server.
  
> [!IMPORTANT]
> Этот раздел относится только к службе Mobility Service в Skype для бизнеса Server (МККС) и не применяется к веб-API единой системы обмена сообщениями (УКВА), как доставляется в накопительные обновления для Lync Server 2013: Февраль 2013. 
  
При установке службы Mobility Service (МККС) в службах IIS 7,5 программа установки службы Mobility Service настраивает некоторые параметры быстродействия на сервере переднего плана. We recommend that you use IIS 7.5 for mobility. The settings affect the maximum number of concurrent user requests and the maximum number of threads that are allowed for the Mobility Service.
  
Далее представлены параметры производительности:
  
### <a name="settings-for-mcx-on-iis-75"></a>Параметры для Mcx в службе IIS 7.5

1. **maxConcurrentThreadsPerCPU** имеет значение нуля (0).
    
2. **maxConcurrentRequestsPerCPU** имеет значение нуля (0).
    
3. Процессная модель ASP.NET имеет значение AutoConfig (только для IIS 7.5).
    
4. Предел очереди HTTP.sys имеет значение 1000 (по умолчанию).
    

