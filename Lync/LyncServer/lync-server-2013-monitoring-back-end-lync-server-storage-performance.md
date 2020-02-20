---
title: 'Lync Server 2013: Мониторинг производительности сервера внешнего хранилища Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring back end Lync Server 2013 storage performance
ms:assetid: 71627c70-1953-4ac2-afbe-f3ad85be0f44
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720917(v=OCS.15)
ms:contentKeyID: 63969619
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e48db772a35177571b1affe7c69674cc7fce07ac
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149358"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="monitoring-back-end-lync-server-2013-storage-performance"></a>Мониторинг производительности сервера внешней системы хранения данных Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2014-05-02_

Серверные базы данных Lync Server 2013 являются очень важной частью развертывания Lync Server 2013. Рекомендуется постоянно отслеживать базы данных и соответствующие журналы транзакций, чтобы обеспечить оптимальное выполнение серверного сервера Lync Server 2013.

В следующей таблице указаны счетчики производительности, которые необходимо отслеживать для получения сведений о производительности хранилища. Базовые значения для этих счетчиков необходимо определить первыми (когда система находится на нормальной, ожидаемой нагрузке), чтобы оценить изменения производительности при напряжении системы.

### <a name="performance-counters-to-be-monitored"></a>Наблюдаемые счетчики производительности

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Счетчик производительности</th>
<th>Базовые пороговые значения</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Транзакций в секунду (RTC)</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Транзакций в секунду (журнал RTCDyn)</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Транзакций в секунду (tempdb)</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Сбросов журнала в секунду (RTC)</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Сбросов журнала/сек (журнал RTCDyn)</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Очисток журнала в секунду (tempdb)</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Обращений к диску/сек (чтение и запись), RTC DB</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Обращений к диску/сек-журнал RTC</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Обращений к диску/сек-журнал RTCDyn DB</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Обращений к диску/сек-журнал журнал RTCDyn</p></td>
<td></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

