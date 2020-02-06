---
title: Настройка службы Mobility Service для высокой производительности в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c2b8aadb-cffb-49f0-ba7a-e8541a1ff475
description: 'Сводка: сведения о службе Mobility Service в Skype для бизнеса Server.'
ms.openlocfilehash: d50aab5ced14753a7665c6560220d1dfdca1061d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818059"
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
    

