---
title: 'Lync Server 2013: делегирование'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delegation
ms:assetid: 89e76e5c-3cfb-4504-8d0d-7509c8ba9815
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994045(v=OCS.15)
ms:contentKeyID: 51803956
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8da9568ae4cd613dcba0760fb4a8b20295fbb68d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739809"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delegation-in-lync-server-2013"></a>Делегирование в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-03-09_

Возможности делегирования в Lync зависят от маршрутизации на основе местоположения следующими способами:

  - Если представитель, включенный для маршрутизации на основе местоположения, помещает звонок от имени руководителя, то для проверки подлинности звонка, а также для направления звонка будет использоваться политика маршрутизации голосовой связи для представителя.

  - Что касается исходящих звонков ТСОП диспетчеру, действуют те же правила, регламентирующие переадресацию звонков и порядок обработки одновременных звонков, что и в соответствующих разделах.

  - Когда делегат устанавливает конечную точку ТСОП в качестве точки назначения одновременных звонков для входящих звонков в адрес диспетчера, для маршрутизации звонка на конечную точку ТСОП делегата используется политика маршрутизации голосовых звонков сетевого сайта, связанного с входящей магистралью.

  - Для целей делегирования, как правило, рекомендуется, чтобы диспетчер и связанные с ним делегаты находились на одном сетевом сайте.

<div>

## <a name="see-also"></a>См. также


[Сценарии маршрутизации на основе местоположения в Lync Server 2013](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

