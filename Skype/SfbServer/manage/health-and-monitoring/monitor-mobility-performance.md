---
title: Мониторинг производительности в Skype для бизнеса Server
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
ms.assetid: 9c831c63-9a7d-48ec-9118-f8a7e80ddd04
description: 'Сводка: сведения о службе Mobility Service (МККС) и веб-интерфейсе API единой системы обмена сообщениями (УКВА) в Skype для бизнеса Server.'
ms.openlocfilehash: 4d604c46704881a055385336f8b1ff32862d929a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817838"
---
# <a name="monitor-mobility-for-performance-in-skype-for-business-server"></a>Мониторинг производительности в Skype для бизнеса Server
 
**Сводка:** Узнайте о службе Mobility Service (МККС) и веб-API единой системы обмена сообщениями (УКВА) в Skype для бизнеса Server.
  
Служба Mobility Service в Skype для бизнеса Server (МККС) и веб-интерфейс единой системы обмена сообщениями (УКВА) увеличивают нагрузку на сервер переднего плана и пулы интерфейсов. Мобильные устройства, поддерживающие подключение к серверу даже в том случае, если мобильное приложение свернуто, например устройства Android и Nokia, работающие под управлением Lync 2010 Mobile, а также устройства Android и Apple, работающие под управлением Lync 2013 для мобильных устройств, выпускают больше нагрузки, чем устройства, которые прерывать соединение с сервером, когда мобильное приложение свернуто. As your mobility usage increases, you must monitor mobility performance to determine when you need to increase your capacity.

> [!NOTE]
> Поддержка МККС (служба Mobility Service) для устаревших мобильных клиентов больше не доступна в Skype для бизнеса Server 2019. На всех текущих мобильных клиентах Skype для бизнеса уже используется веб-API единой системы обмена сообщениями (УКВА) для поддержки мгновенных сообщений, присутствия и контактов. Пользователи с устаревшими клиентами, использующими МККС, должны обновиться до текущего клиента.
  
Некоторые ограничения, влияющие на производительность мобильности: 
  
- доступная память;
    
- ограничение очереди запросов;
    
- одновременные подключения;
    
- длина очереди IIS.
    
Кроме того, на производительность мобильности могут влиять следующие ограничения на серверах: не более 12 одновременных входов, проверок подлинности, а также возобновлений и прекращений сеансов. В большинстве развертываний эти максимальные значения не нуждаются в изменении.
  
## <a name="in-this-section"></a>В этом разделе

- [Наблюдение за ограничениями объема памяти сервера в Skype для бизнеса Server](server-memory-capacity-limits.md)
    
- [Мониторинг службы Mobility Service и использование УКВА в Skype для бизнеса Server](service-and-ucwa-usage.md)
    
- [Настройка службы Mobility Service для высокой производительности в Skype для бизнеса Server](configure-service.md)
    
- [Мониторинг файлов журнала трассировки запросов IIS в Skype для бизнеса Server](iis-request-tracing-log-files.md)
    
- [Счетчики производительности мобильных устройств в Skype для бизнеса Server](performance-counters.md)
    

