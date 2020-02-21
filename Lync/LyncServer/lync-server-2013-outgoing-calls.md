---
title: 'Lync Server 2013: исходящие вызовы'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Outgoing calls
ms:assetid: 885ffe6f-cd51-4f21-8d4f-a1ff8d818858
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994049(v=OCS.15)
ms:contentKeyID: 51803960
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7aa72bb1da56862765279f25f73070863d218067
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42216390"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="outgoing-calls-in-lync-server-2013"></a>Исходящие вызовы в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-03-09_

Маршрутизация исходящих вызовов пользователей, для которых включена маршрутизация на основе расположения, зависит от расположения в сети конечной точки пользователя. В следующей таблице показано, как маршрутизация на основе расположения влияет на маршрутизацию исходящих вызовов в зависимости от расположения конечной точки вызывающего абонента.

### <a name="caller-placing-an-outbound-call-to-the-pstn"></a>Вызывающий абонент, исходящий звонок по протоколу PSTN

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Конечная точка пользователя, расположенная на сетевом сайте, для которого включена маршрутизация на основе расположения</th>
<th>Конечная точка пользователя находится на неизвестном сетевом сайте или не включена для маршрутизации на основе расположения</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Авторизация исходящих вызовов</p></td>
<td><p>Вызов авторизован на основе политики голосовой связи пользователя</p></td>
<td><p>Вызов авторизован на основе политики голосовой связи пользователя</p></td>
</tr>
<tr class="even">
<td><p>Маршрутизация исходящего звонка</p></td>
<td><p>Вызов перенаправляется в соответствии с политикой маршрутизации голосовой связи на сетевом сайте.</p></td>
<td><p>Вызов перенаправляется в соответствии с политикой голосовой связи пользователя и только через магистрали, для которых не включена маршрутизация на основе расположения (при наличии).</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a>См. также


[Сценарии маршрутизации на основе расположения в Lync Server 2013](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

