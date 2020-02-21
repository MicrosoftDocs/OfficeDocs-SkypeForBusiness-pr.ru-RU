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
ms.openlocfilehash: 840ec938fdd6262468eb86a3b190e100c38bf32c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42217275"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="monitoring-mobility-for-performance-in-lync-server-2013"></a>Наблюдение за производительностью мобильных устройств в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-14_

Служба Mobility Server Mobility Service (MCX) и веб-API объединенных коммуникаций (UCWA) увеличивают нагрузку на серверы переднего плана и пулы переднего плана. Мобильные устройства, которые поддерживают подключение к серверу, даже если мобильное приложение свернуто, например устройства Android и Nokia, работающие под управлением Lync 2010 Mobile, а также устройства с Android и Apple, работающие под управлением Lync 2013 Mobile, накладывают большую нагрузку, чем устройства, которые разрыв подключения к серверу, когда мобильное приложение свернуто. По мере роста использования мобильных устройств необходимо следить за производительностью мобильных устройств, чтобы определить, когда нужно увеличить емкость.

Некоторые ограничения, влияющие на производительность мобильности:

  - доступная память;

  - ограничение очереди запросов;

  - одновременные подключения;

  - длина очереди IIS.

Другие ограничения на серверах, которые могут повлиять на производительность мобильных устройств, могут быть не более двенадцати, чем двенадцать одновременных входов, проверки подлинности, продления сеанса и завершения. В большинстве развертываний эти максимальные значения не нуждаются в изменении.

<div>

## <a name="in-this-section"></a>Содержание

  - [Мониторинг пределов объема памяти сервера в Lync Server 2013](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)

  - [Мониторинг службы Mobility Service и использования UCWA в Lync Server 2013](lync-server-2013-monitoring-mobility-service-and-ucwa-usage.md)

  - [Настройка службы Mobility Service для высокой производительности в Lync Server 2013](lync-server-2013-configuring-mobility-service-for-high-performance.md)

  - [Мониторинг файлов журнала трассировки запросов IIS в Lync Server 2013](lync-server-2013-monitoring-iis-request-tracing-log-files.md)

  - [Счетчики производительности мобильных устройств в Lync Server 2013](lync-server-2013-mobility-performance-counters.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

