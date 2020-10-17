---
title: 'Lync Server 2013: одновременный Звонок'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Simultaneous ringing
ms:assetid: df02f919-4d50-4832-9300-6c51f8b4fc56
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994079(v=OCS.15)
ms:contentKeyID: 51803990
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 358a0dd6dab96b67b26c211c9f28dbc6c0842804
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48519796"
---
# <a name="simultaneous-ringing-in-lync-server-2013"></a>Одновременные звонки в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-03-09_

Если у вызываемой абонента включен Одновременный звонок, Location-Based маршрутизация анализирует расположение вызывающей стороны и конечных точек вызываемых сторон, чтобы определить, следует ли маршрутизировать вызов.

В следующей таблице показано, что пользователь настроен с одновременным вызовом, а Одновременный звонок является пользователем на том же сетевом сайте, на другом сетевом сайте или на неизвестном сетевом сайте.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Входящий звонок PSTN для</th>
<th>Размещается на том же сетевом сайте, что и вызываемый</th>
<th>Размещается на другом сетевом сайте, чем вызываемый</th>
<th>Находится на неизвестном сетевом сайте или не включена для маршрутизации Location-Based</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Пользователь Lync</p></td>
<td><p>Одновременный звонок разрешен</p></td>
<td><p>Одновременный звонок не разрешен</p></td>
<td><p>Одновременный звонок не разрешен</p></td>
</tr>
</tbody>
</table>

  
В следующей таблице показан вызов из пользователя Lync (то есть вызывающего абонента Lync) на том же сетевом сайте, на другом сетевом сайте или на неизвестном сетевом сайте. Вызываемая сторона имеет конечную точку PSTN (например, мобильного телефона), настроенную в качестве одновременного абонента. В этом сценарии Location-Based маршрутизация определяет, будет ли вызов перенаправляться в одновременный приемник (например, мобильного телефона) вызываемого абонента.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Цель одновременных звонков</th>
<th>Размещается на том же сетевом сайте, что и вызываемый</th>
<th>Размещается на другом сетевом сайте, чем вызываемый</th>
<th>Находится на неизвестном сетевом сайте или не включена для маршрутизации Location-Based</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Конечная точка PSTN</p></td>
<td><p>Одновременный звонок разрешен через политику маршрутизации голосовых вызовов сайта вызывающего абонента</p></td>
<td><p>Одновременный звонок разрешен через политику маршрутизации голосовых вызовов сайта вызывающего абонента</p></td>
<td><p>Одновременный звонок разрешен через политику голосовой связи вызывающего абонента для магистрали, для которых не включена маршрутизация Location-Based</p></td>
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

