---
title: 'Lync Server 2013: входящие звонки'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Incoming calls
ms:assetid: 65b9c1b4-6af7-4527-8c33-22c4442bd209
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994038(v=OCS.15)
ms:contentKeyID: 51803948
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 05147e469ce120663992e5ae7b8a3ee59acaf78c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526616"
---
# <a name="incoming-calls-in-lync-server-2013"></a>Входящие звонки в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-03-09_

Маршрутизация входящих вызовов пользователей, включенных для маршрутизации Location-Based, зависит от расположения конечной точки пользователя. Маршрутизация входящих вызовов изменяется следующим образом. Если у пользователя есть входящий вызов конечной точки, расположенной на сетевом сайте с поддержкой маршрутизации Location-Based, а конечная точка расположена на том же сетевом сайте, что и шлюз PSTN, вызов будет перенаправлен. Если у пользователя есть входящий вызов конечной точки, расположенной на сетевом сайте с поддержкой маршрутизации Location-Based, а конечная точка расположена на другом сетевом сайте, отличном от шлюза PSTN, вызов не будет маршрутизироваться. Если у пользователя нет конечных точек, расположенных на том же сетевом сайте, что и шлюз PSTN, из которого исходит входящий вызов, входящий вызов будет перенаправлен прямо на голосовую почту пользователя, и уведомление о пропущенном звонке будет отправлено вызываемому абоненту.

Параметры переадресации звонков для пользователя, включенного для маршрутизации Location-Based, будут по-прежнему применяться, однако переадресованные звонки будут подвергаться Location-Based ограничениям маршрутизации пользователя.

В следующей таблице показано, как маршрутизация Location-Based влияет на маршрутизацию входящих вызовов в зависимости от расположения конечной точки вызываемого абонента. Сетевой сайт шлюза PSTN включен для маршрутизации Location-Based, а маршрутизация Location-Based разрешается только для маршрутизации вызовов PSTN в конечные точки того же сетевого сайта.

### <a name="callee-receiving-an-inbound-call-from-the-pstn"></a>Вызываемый абонент получает входящий звонок от PSTN

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Конечная точка вызываемого абонента расположена на том же сетевом сайте, что и шлюз PSTN</th>
<th>Конечная точка вызываемого абонента не расположена на том же сетевом сайте, что и шлюз PSTN</th>
<th>Конечная точка вызываемого абонента расположена на неизвестном сетевом сайте или не включена для маршрутизации Location-Based</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Маршрутизация входящего звонка по PSTN</p></td>
<td><p>Входящий вызов перенаправляется в конечные точки вызываемого абонента</p></td>
<td><p>Входящий звонок не перенаправляется в конечные точки вызываемого абонента</p></td>
<td><p>Входящий звонок не перенаправляется в конечные точки вызываемого абонента</p></td>
</tr>
</tbody>
</table>

  

<div>

## <a name="see-also"></a>См. также


[Сценарии для маршрутизации Location-Based в Lync Server 2013](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

