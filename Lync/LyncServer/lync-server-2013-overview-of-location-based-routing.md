---
title: 'Lync Server 2013: Обзор маршрутизации Location-Based'
description: 'Lync Server 2013: Обзор маршрутизации Location-Based.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Location-Based Routing
ms:assetid: 4aa494bd-0d66-4335-b9e8-f758d44a7202
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994032(v=OCS.15)
ms:contentKeyID: 51803941
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0b1e026791a8562629231b91b58d7e7eff569ffa
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562815"
---
# <a name="overview-of-location-based-routing-in-lync-server-2013"></a>Обзор маршрутизации Location-Based в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-21_

В Location-Based маршрутизации представлен новый набор правил, которые изменяют маршрутизацию местных и международных звонков PSTN, чтобы предотвратить нерекомендуемый обход. Маршрутизация Location-Based обеспечивает гибкость для применения этих правил к определенным регионам, определенным шлюзам или только к определенному набору пользователей.

В приведенных ниже сценариях показаны основные типы ограничений, которые Location-Based маршрутизации могут принудительно применять:

  - Звонки исходящих вызовов — Location-Based маршрутизация позволяет принудительно исходить исходящие вызовы с шлюза PSTN, расположенного в том же регионе, что и вызывающий абонент, чтобы предотвратить обход бесплатных звонков с помощью шлюза PSTN, находящегося в другом регионе в качестве абонента.

  - Входные звонки — Location-Based маршрутизация может препятствовать входящим звонкам PSTN на кольца конечных точек Lync, если маршрутизация шлюза PSTN не находится в том же регионе, что и Вызываемый пользователь Lync.

  - Unknown regions — Location-Based маршрутизация запрещает входящие и исходящие вызовы PSTN между пользователями, находящимися в неопределенном расположении (например, удаленные пользователи, подключающиеся из Интернета или находящиеся в неизвестных регионах).

  - Международные регионы — маршрутизация Location-Based обеспечивает маршрутизацию исходящих вызовов через международные шлюзы PSTN, если не удается найти локальный шлюз для расположения пользователя.

<div>

## <a name="see-also"></a>См. также


[Планирование маршрутизации Location-Based в Lync Server 2013](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

