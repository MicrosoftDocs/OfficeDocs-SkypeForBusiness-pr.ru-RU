---
title: 'Lync Server 2013: передача звонков и переадресация звонков'
description: 'Lync Server 2013: Передача вызовов и переадресация вызовов.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call transfers and call forwarding
ms:assetid: 978610ec-63c7-4cf6-ad7a-9ef91559bf12
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994051(v=OCS.15)
ms:contentKeyID: 51803962
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d9359cb64b386d022eab33e4523dfaccf784075b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565255"
---
# <a name="call-transfers-and-call-forwarding-in-lync-server-2013"></a>Передача звонков и переадресация вызовов в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-03-09_

Когда применяется конечная точка PSTN, Location-Based маршрутизация анализирует расположение конечной точки Калле и конечную точку, в которую передается или передается вызов (то есть, цель передачи/перенаправления). Маршрутизация Location-Based определяет, следует ли передавать или пересылать вызов в зависимости от расположения обеих конечных точек.

В следующей таблице показан сценарий пользователя Lync в вызове с конечной точкой PSTN, а пользователь Lync передает вызов другому пользователю Lync. В зависимости от расположения сетевого сайта конечной точки участника, Location-Based маршрутизация влияет на маршрутизацию передачи или переадресации вызовов.

### <a name="initiating-call-transfer-or-forward"></a>Инициация передачи или пересылки звонка

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Пользователь, инициирующий передачу или переадресацию звонка</th>
<th>Целевая конечная точка находится на том же сетевом сайте, что и пользователь, инициирующий передачу или переадресацию</th>
<th>Целевая конечная точка находится на другом сетевом сайте, что и пользователь, инициирующий передачу или переадресацию вызовов</th>
<th>Целевая конечная точка находится в неизвестном сетевом сайте или на сетевом сайте не включена маршрутизация Location-Based</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Пользователь Lync</p></td>
<td><p>Переадресация звонков или передача разрешена</p></td>
<td><p>Переадресация вызовов и передача запрещены</p></td>
<td><p>Переадресация вызовов и передача запрещены</p></td>
</tr>
</tbody>
</table>

  

Например: пользователь Lync в вызове с конечной точкой PSTN передает вызов другому пользователю Lync, который находится на том же сетевом сайте. В этом случае передача вызовов разрешена.

В следующей таблице показан сценарий пользователя Lync в вызове с другим пользователем Lync, а один из пользователей передает вызов конечной точке PSTN. В зависимости от расположения пользователя, на который передается вызов, в таблице подробно описывается, как Location-Based маршрутизация влияет на вызов.

### <a name="call-transfer-or-forward-to-pstn-endpoint"></a>Передача звонка или переадресация на конечную точку PSTN

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Целевая конечная точка передачи вызовов и переадресации</th>
<th>Пользователи Lync на одном сетевом сайте</th>
<th>Пользователи Lync в различных сетевых сайтах</th>
<th>Один или оба пользователя Lync на неизвестном сетевом сайте или сетевом сайте не включены для маршрутизации Location-Based</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Конечная точка PSTN</p></td>
<td><p>Переадресация звонков или передача данных разрешена политикой маршрутизации голосовой связи на сайте перенесенного пользователя</p></td>
<td><p>Переадресация звонков или передача данных разрешена политикой маршрутизации голосовой связи на сайте перенесенного пользователя</p></td>
<td><p>Переадресация звонков или передача, разрешенные переданными политикой голосовой связи пользователя, только через магистрали, для которых не включена маршрутизация Location-Based</p></td>
</tr>
</tbody>
</table>

  
Например: пользователь Lync в вызове с другим пользователем Lync, который находится на том же сетевом сайте, передает вызов конечной точке PSTN, а передача вызовов разрешена.

<div>

## <a name="see-also"></a>См. также


[Сценарии для маршрутизации Location-Based в Lync Server 2013](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

