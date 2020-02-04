---
title: 'Lync Server 2013: технические рекомендации для маршрутизации на основе расположения'
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
ms.openlocfilehash: 978590484cbb6bd3c23fac26422c186847662e49
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764049"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-considerations-for-location-based-routing-in-lync-server-2013"></a>Технические рекомендации для маршрутизации на основе расположения в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-03-09_

При планировании маршрутизации на основе местоположения следует принимать во влияния указанные ниже сценарии.

<div>

## <a name="disaster-recovery"></a>Аварийное восстановление

При отработке отказа из основного пула в пул резервного копирования, а также при восстановлении нормальных операций для основного пула, маршрутизация на основе местоположения всегда будет принудительно применяться во время аварийной ситуации и процедуры восстановления.

</div>

<div>

## <a name="survivable-branch-appliance"></a>для обеспечения связи в филиалах

Настройка маршрутизации на основе местоположения влияет на планирование развертывания шлюзов, связанных с бесперебойными устройствами филиалов. Шлюз, связанный с вашим СБА, должен находиться на том же сетевом сайте, что и работающее устройство филиала. в противном случае, если настроена маршрутизация на основе местоположения, пользователи, работающие на устройстве с бесперебойной подразделением, не смогут выполнять исходящие вызовы. При подключении через глобальную сеть между бесперебойно используемым устройством филиала и центральным сайтом ограничения на маршрутизацию на основе местоположения остаются принудительными.

</div>

<div>

## <a name="see-also"></a>См. также


[Планирование маршрутизации на основе местоположения в Lync Server 2013](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

