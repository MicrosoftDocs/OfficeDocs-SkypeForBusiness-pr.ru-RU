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
ms.openlocfilehash: 360223733f003c30d63ef0145fa04c51503d510d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154651"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delegation-in-lync-server-2013"></a>Делегирование в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-03-09_

Возможности делегирования в Lync зависят от маршрутизации на основе расположения следующим образом:

  - Когда представитель, включенный для маршрутизации на основе расположения, помещает вызов от имени руководителя, политика голосовой связи представителя используется для авторизации звонка, а политика маршрутизации голосовых вызовов на сайте представителя будет использоваться для маршрутизации вызова.

  - Для входящих звонков по PSTN в директоре применяются те же правила, что и для переадресации звонков или одновременного звонка, как описано в разделах "передача и переадресация вызовов и одновременный Звонок".

  - Когда делегат задает конечную точку PSTN в качестве одновременного абонента, для входящего вызова руководителя будет использоваться политика маршрутизации голосовой связи для сайта, связанного с входящей магистралью, для маршрутизации вызова в конечную точку PSTN представителя.

  - Для делегирования рекомендуется, чтобы руководитель и связанные с ним делегаты были размещены на одном сетевом сайте.

<div>

## <a name="see-also"></a>См. также


[Сценарии маршрутизации на основе расположения в Lync Server 2013](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

