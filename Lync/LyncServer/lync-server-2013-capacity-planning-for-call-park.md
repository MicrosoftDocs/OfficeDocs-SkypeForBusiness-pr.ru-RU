---
title: 'Lync Server 2013: планирование емкости для парковки вызовов'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Capacity planning for Call Park
ms:assetid: 75520310-760a-4b1b-bcc1-4d724d13f87a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg416493(v=OCS.15)
ms:contentKeyID: 48184529
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5fe55e09c67e62676202def9e3def3454d7cbd33
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841677"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-call-park-in-lync-server-2013"></a>Планирование емкости для парковки вызовов в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-09-13_

<div id="sectionSection0" class="section">

В приведенной ниже таблице описана пользовательская модель парковки звонков, которую можно использовать в качестве основы для планирования производственных мощностей.

<div>


> [!IMPORTANT]  
> Имейте в виду, что при планировании производительности аварийного восстановления каждый пул из сопряженного пула может обрабатывать рабочие нагрузки для служб приостановки звонков в обоих пулах.



</div>

### <a name="call-park-user-model"></a>Пользовательская модель парковки вызовов

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Показатель</th>
<th>На пул переднего плана (с 8 серверами переднего плана)</th>
<th>Для каждого сервера Standard Edition</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Скорость парковки</p></td>
<td><p>8 вызов в минуту</p></td>
<td><p>1 вызов в минуту</p></td>
</tr>
<tr class="even">
<td><p>Скорость извлечения приостановленных вызовов</p></td>
<td><p>8 вызов в минуту</p></td>
<td><p>1 вызов в минуту</p></td>
</tr>
<tr class="odd">
<td><p>Среднее время парковки</p></td>
<td><p>60 с</p></td>
<td><p>60 с</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

