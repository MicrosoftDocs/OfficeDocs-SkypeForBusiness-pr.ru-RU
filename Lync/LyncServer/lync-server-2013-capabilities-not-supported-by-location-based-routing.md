---
title: 'Lync Server 2013: функции, не поддерживаемые маршрутизацией на основе расположения'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Capabilities not supported by Location-Based Routing
ms:assetid: c3d54953-a7d6-4465-a6c3-ae411b2d8ea9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994071(v=OCS.15)
ms:contentKeyID: 51803982
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7ca2d775fc17d0919ceb31a38b242e54d37b6a55
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841682"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capabilities-not-supported-by-location-based-routing-in-lync-server-2013"></a>Функции, не поддерживаемые маршрутизацией на основе расположения в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2014-03-12_

Маршрутизация на основе местоположения не распространяется на следующие типы взаимодействий. Маршрутизация на основе местоположения не применяется, если конечные точки Lync взаимодействуют с конечными точками PSTN с помощью этих возможностей.

  - Конференции с телефонным подключением

  - Входящие и исходящие вызовы ТСОП через группу ответов

  - Парковка вызовов или преобразование вызовов ТСОП с помощью функции парковки вызовов

  - Входящие вызовы ТСОП в службу оповещений

  - Входящие вызовы ТСОП, преобразованные через групповой ответ на вызовы

Чтобы использовать правила маршрутизации, основанные на расположении, в следующем списке, необходимо включить функцию маршрутизации на основе местоположения для конференций.

  - Исходящие вызовы по ТСОП из конференций

  - Эскалации из сеансов одноранговой голосовой связи к сеансам конференций с привлечением конечных точек ТСОП

  - Передачи после консультации с привлечением конечных точек ТСОП

Чтобы включить возможность маршрутизации для конференций на основе местоположения, ознакомьтесь со сведениями [о маршрутизации на основе местоположения для конференций в Lync Server 2013](lync-server-2013-location-based-routing-for-conferencing.md).

<div>

## <a name="see-also"></a>См. также


[Планирование маршрутизации на основе местоположения в Lync Server 2013](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

