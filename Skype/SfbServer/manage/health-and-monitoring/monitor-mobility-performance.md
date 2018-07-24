---
title: Мобильность монитора производительности в Скайп для Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9c831c63-9a7d-48ec-9118-f8a7e80ddd04
description: 'Сводка: Сведения о Mobility Service (Mcx) и веб-объединенных коммуникаций API (UCWA) в Скайп для Business Server.'
ms.openlocfilehash: 4affcb532697f24c87d62e18fc26552639dc00e1
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "20990639"
---
# <a name="monitor-mobility-for-performance-in-skype-for-business-server"></a>Мобильность монитора производительности в Скайп для Business Server
 
**Сводка:** Сведения о службе Mobility Service (Mcx) и веб-объединенных коммуникаций API (UCWA) в Скайп для Business Server.
  
Скайп для службы Mobility Business Server (Mcx) и Unified Communications Web API (UCWA) увеличивают нагрузку на пулов переднего плана и серверов переднего плана. Мобильных устройств, которые поддерживают подключение к серверу даже в том случае, если свернутого мобильных приложений, таких как Android и Nokia устройств под управлением Lync 2010 Mobile, а также Android и Apple устройств под управлением Lync 2013 Mobile применяться дополнительную нагрузку, чем устройств, прерывания их подключения к серверу при свернутом окне мобильных приложений. С увеличением использования мобильных устройств должны отслеживать производительность мобильности, чтобы определить, когда следует увеличить емкость.

> [!NOTE]
> Поддержка MCX для устаревших мобильных клиентов больше не доступен в Скайп для Business Server 2019. Пользователям необходимо обновить до текущего клиента.
  
Некоторые ограничения, влияющие на производительность мобильности: 
  
- доступная память;
    
- ограничение очереди запросов;
    
- одновременные подключения;
    
- длина очереди IIS.
    
Кроме того, на производительность мобильности могут влиять следующие ограничения на серверах: не более 12 одновременных входов, проверок подлинности, а также возобновлений и прекращений сеансов. В большинстве развертываний эти максимальные значения не нуждаются в изменении.
  
## <a name="in-this-section"></a>Содержание

- [Монитор ограничений емкости памяти сервера в Скайп для Business Server](server-memory-capacity-limits.md)
    
- [Мониторинг использования службы Mobility Service и UCWA в Скайп для Business Server](service-and-ucwa-usage.md)
    
- [Настройка службы мобильности для повышения производительности в Скайп для Business Server](configure-service.md)
    
- [Мониторинг файлов журнала в Скайп трассировки для сервера запросов IIS](iis-request-tracing-log-files.md)
    
- [Счетчики производительности мобильности в Скайп для Business Server](performance-counters.md)
    

