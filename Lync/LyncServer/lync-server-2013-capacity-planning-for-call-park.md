---
title: 'Lync Server 2013: планирование мощности для парковки вызовов'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capacity planning for Call Park
ms:assetid: 75520310-760a-4b1b-bcc1-4d724d13f87a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg416493(v=OCS.15)
ms:contentKeyID: 48184529
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 079d1517afa72eeff607920d86b093ac01d673de
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512836"
---
# <a name="capacity-planning-for-call-park-in-lync-server-2013"></a>Планирование емкости для парковки вызовов в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-13_

<div id="sectionSection0" class="section">

В следующей таблице описывается пользовательская модель парковки вызовов, которую можно использовать в качестве основы для требований по планированию мощности.

<div>


> [!IMPORTANT]  
> Имейте в виду, что при планировании мощности аварийного восстановления каждый пул в связанном пуле должен иметь возможность обрабатывать рабочие нагрузки для служб парковки вызовов в обоих пулах.



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
<th>Метрика</th>
<th>На интерфейсный пул (с 8 серверами переднего плана)</th>
<th>Для каждого сервера Standard Edition</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Скорость парковки</p></td>
<td><p>8 вызовов в минуту</p></td>
<td><p>1 вызов в минуту</p></td>
</tr>
<tr class="even">
<td><p>Скорость извлечения паркованных вызовов</p></td>
<td><p>8 вызовов в минуту</p></td>
<td><p>1 вызов в минуту</p></td>
</tr>
<tr class="odd">
<td><p>Среднее время парковки</p></td>
<td><p>60 секунд</p></td>
<td><p>60 секунд</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

