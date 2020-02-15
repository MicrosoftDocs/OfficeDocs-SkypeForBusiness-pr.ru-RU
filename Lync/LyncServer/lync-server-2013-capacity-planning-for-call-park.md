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
ms.openlocfilehash: f1192ef9b5b30c722a4f62973cf4992da3ca7300
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044181"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-call-park-in-lync-server-2013"></a>Планирование емкости для парковки вызовов в Lync Server 2013

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
<th>Метр</th>
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

