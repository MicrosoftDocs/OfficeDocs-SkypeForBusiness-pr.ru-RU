---
title: Мониторинг производительности для мобильных устройств в Skype для бизнеса Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9c831c63-9a7d-48ec-9118-f8a7e80ddd04
description: 'Сводка: Сведения о Mobility Service (Mcx) и веб-API (UCWA) объединенных коммуникаций в Скайп для Business Server 2015.'
ms.openlocfilehash: 1981bff8398f3fab9206f9dab748c545268f7edf
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="monitor-mobility-for-performance-in-skype-for-business-server-2015"></a>Мониторинг производительности для мобильных устройств в Skype для бизнеса Server 2015
 
**Сводка:** Описание службы Mobility Service (Mcx) и веб-API (UCWA) объединенных коммуникаций в Скайп для Business Server 2015.
  
Скайп для службы Mobility Business Server (Mcx) и Unified Communications Web API (UCWA) увеличивают нагрузку на пулов переднего плана и серверов переднего плана. Мобильных устройств, которые поддерживают подключение к серверу даже в том случае, если свернутого мобильных приложений, таких как Android и Nokia устройств под управлением Lync 2010 Mobile, а также Android и Apple устройств под управлением Lync 2013 Mobile применяться дополнительную нагрузку, чем устройств, прерывания их подключения к серверу при свернутом окне мобильных приложений. С увеличением использования мобильных устройств должны отслеживать производительность мобильности, чтобы определить, когда следует увеличить емкость.
  
Некоторые ограничения, влияющие на производительность мобильности: 
  
- доступная память;
    
- ограничение очереди запросов;
    
- одновременные подключения;
    
- длина очереди IIS.
    
Кроме того, на производительность мобильности могут влиять следующие ограничения на серверах: не более 12 одновременных входов, проверок подлинности, а также возобновлений и прекращений сеансов. В большинстве развертываний эти максимальные значения не нуждаются в изменении.
  
## <a name="in-this-section"></a>Содержание

- [Монитор ограничений емкости памяти сервера в Скайп для Business Server 2015](server-memory-capacity-limits.md)
    
- [Мониторинг использования службы Mobility Service и UCWA в Скайп для Business Server 2015](service-and-ucwa-usage.md)
    
- [Настройка службы мобильности для повышения производительности в Скайп для Business Server 2015](configure-service.md)
    
- [Мониторинга IIS запросить файлы журнала трассировки в Скайп для Business Server 2015](iis-request-tracing-log-files.md)
    
- [Счетчики производительности мобильности в Скайп для Business Server 2015](performance-counters.md)
    

