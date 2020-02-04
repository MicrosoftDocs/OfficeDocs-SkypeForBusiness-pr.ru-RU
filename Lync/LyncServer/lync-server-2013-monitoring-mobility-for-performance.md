---
title: 'Lync Server 2013: наблюдение за производительностью мобильных устройств'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring mobility for performance
ms:assetid: 9c831c63-9a7d-48ec-9118-f8a7e80ddd04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690033(v=OCS.15)
ms:contentKeyID: 48184908
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 53bd9c3450617d4fd1db54b52efe0b0938c84c8b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756823"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-mobility-for-performance-in-lync-server-2013"></a>Мониторинг мобильных устройств для повышения производительности в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-02-14_

Служба мобильной связи Lync Server (МККС) и веб-интерфейс единой системы обмена сообщениями (УКВА) увеличивают нагрузку на сервер переднего плана и пулы интерфейсов. Мобильные устройства, поддерживающие подключение к серверу даже в том случае, если мобильное приложение свернуто, например устройства Android и Nokia, работающие под управлением Lync 2010 Mobile, а также устройства Android и Apple, работающие под управлением Lync 2013 для мобильных устройств, выпускают больше нагрузки, чем устройства, которые прерывать соединение с сервером, когда мобильное приложение свернуто. As your mobility usage increases, you must monitor mobility performance to determine when you need to increase your capacity.

Некоторые ограничения, влияющие на производительность мобильности:

  - доступная память;

  - ограничение очереди запросов;

  - одновременные подключения;

  - длина очереди IIS.

Другие ограничения на серверах, которые могут повлиять на производительность мобильных устройств, задаются максимум двенадцать одновременных входов, проверок подлинности, продления сеансов и прекращений. В большинстве развертываний эти максимальные значения не нуждаются в изменении.

<div>

## <a name="in-this-section"></a>Содержание

  - [Наблюдение за пределами объема памяти сервера в Lync Server 2013](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)

  - [Наблюдение за работой службы Mobility Service и использованием УКВА в Lync Server 2013](lync-server-2013-monitoring-mobility-service-and-ucwa-usage.md)

  - [Настройка службы Mobility Service для высокой производительности в Lync Server 2013](lync-server-2013-configuring-mobility-service-for-high-performance.md)

  - [Мониторинг файлов журнала трассировки запросов IIS в Lync Server 2013](lync-server-2013-monitoring-iis-request-tracing-log-files.md)

  - [Счетчики производительности мобильных устройств в Lync Server 2013](lync-server-2013-mobility-performance-counters.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

