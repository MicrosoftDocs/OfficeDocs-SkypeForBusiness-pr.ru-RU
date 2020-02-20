---
title: 'Lync Server 2013: технические рекомендации по маршрутизации на основе расположения'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical considerations for Location-Based Routing
ms:assetid: 2e2a9199-7c6f-48d3-9adb-3873fc4f8c4e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994027(v=OCS.15)
ms:contentKeyID: 51803936
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e672e35771ec3cc4ecbd3655af350231f1583b52
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141895"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="technical-considerations-for-location-based-routing-in-lync-server-2013"></a>Технические рекомендации по маршрутизации на основе расположения в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-03-09_

При планировании маршрутизации на основе расположения следует учитывать влияние следующих сценариев.

<div>

## <a name="disaster-recovery"></a>Аварийное восстановление

При отработке отказа из основного пула в резервный пул, а также при восстановлении нормальных операций в основном пуле, маршрутизация на основе местоположения всегда применяется во время аварийного восстановления и процедуры восстановления.

</div>

<div>

## <a name="survivable-branch-appliance"></a>Устройство для обеспечения связи в филиалах

Настройка маршрутизации на основе расположения влияет на планирование того, где разворачиваются шлюзы, связанные с устройствами для обеспечения связи в филиалах. Шлюз, связанный с SBA, должен находиться на том же сетевом сайте, что и устройство для обеспечения связи в филиалах. в противном случае пользователи, размещенные на устройстве для обеспечения связи в филиалах, не смогут совершать исходящие вызовы, если настроена маршрутизация на основе расположения. При соединении WAN между устройством для обеспечения связи в филиалах и центральным сайтом ограничения на маршрутизацию на основе расположения остаются принудительными.

</div>

<div>

## <a name="see-also"></a>См. также


[Планирование маршрутизации на основе расположения в Lync Server 2013](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

