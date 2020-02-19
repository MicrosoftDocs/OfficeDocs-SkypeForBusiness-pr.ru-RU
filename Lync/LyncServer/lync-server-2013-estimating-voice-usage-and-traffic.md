---
title: 'Lync Server 2013: Оценка использования голосовой связи и трафика'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Estimating voice usage and traffic
ms:assetid: 621b08fb-f894-4d91-ac38-e443401b098b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398439(v=OCS.15)
ms:contentKeyID: 48184332
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7723a67b4cefb75218f01dde3603a100b54d40b8
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42131402"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="estimating-voice-usage-and-traffic-for-lync-server-2013"></a>Оценка использования голосовой связи и трафика для Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-08-07_

Средство планирования Microsoft Lync Server 2013, средство планирования использует следующую метрику для оценки трафика пользователя на каждом сайте и количества портов, необходимых для поддержки этого трафика.

  - <span></span>  
    Для **легкого трафика** (один звонок через ТСОП на одного пользователя в час) — 15 пользователей на порт.

  - <span></span>  
    Для **среднего трафика** (2 звонка через ТСОП на одного пользователя в час) — 10 пользователей на порт.

  - <span></span>  
    Для **тяжелого трафика** (3 или больше звонков через ТСОП на вызовы пользователя в час) — 5 пользователей на порт.

Число портов, в свою очередь, определяет количество серверов-посредников и шлюзов, которые будут обязательными. Шлюзы ТСОП, которые развертывают большинство организаций, могут содержать от 2 до 960 портов. (Существуют и более крупные шлюзы, но они в основном используются поставщиками услуг телефонии.)

Например, организация с 10000 пользователей и средним трафиком требуется 1000 портов. Число шлюзов равно общему числу необходимых портов, что определяется общей емкостью шлюзов.

</div>

<span> </span>

</div>

</div>

</div>

