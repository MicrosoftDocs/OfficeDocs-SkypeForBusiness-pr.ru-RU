---
title: 'Lync Server 2013: Настройка службы Mobility Service для высокой производительности'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Mobility Service for high performance
ms:assetid: c2b8aadb-cffb-49f0-ba7a-e8541a1ff475
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690042(v=OCS.15)
ms:contentKeyID: 48185332
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d587444dfd1fbe4fae8898438a51bc9cfb2b5ff
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526956"
---
# <a name="configuring-mobility-service-for-high-performance-in-lync-server-2013"></a>Настройка службы Mobility Service для высокой производительности в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-17_

<div>


> [!IMPORTANT]  
> Этот раздел относится только к службе Mobility Service 2013 для Lync Server и не относится к веб-API объединенных коммуникаций (UCWA), как доставляется в накопительные пакеты обновления для Lync Server 2013: Февраль 2013.



</div>

При установке службы Mobility Service (MCX) в службах IIS 7,5 программа установки службы Mobility Service настраивает некоторые параметры производительности на сервере переднего плана. Мы рекомендуем использовать IIS 7.5 для Mobility Service. Параметры влияют на максимальное число одновременных запросов пользователей и максимальное число потоков, которые разрешены для Mobility Service.

Ниже приведены параметры производительности.

<div>

## <a name="settings-for-mcx-on-iis-75"></a>Параметры MCX в службах IIS 7,5

1.  **maxConcurrentThreadsPerCPU** имеет значение нуль (0).

2.  **maxConcurrentRequestsPerCPU** имеет значение нуль (0).

3.  Процессная модель ASP.NET имеет значение AutoConfig (только для IIS 7.5).

4.  Предел очереди HTTP.sys имеет значение 1000 (по умолчанию).

</div>

</div>

<span> </span>

</div>

</div>

</div>

