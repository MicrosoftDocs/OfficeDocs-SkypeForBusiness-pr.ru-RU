---
title: 'Lync Server 2013: мониторинг группового чата'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring group chat
ms:assetid: bddcf0be-ebf3-46bc-90c7-2576877734fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720924(v=OCS.15)
ms:contentKeyID: 63969648
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cb82eedd9d9578aeb4120136c1896267cde35392
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051141"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-group-chat-in-lync-server-2013"></a>Отслеживание чата группового чата в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2014-08-04_

Мы настоятельно рекомендуем запускать самый последний [накопительный пакет обновления на сервере](http://support.microsoft.com/kb/968802) , доступный в центре загрузки Майкрософт, чтобы повысить производительность.

Если вы используете Последнее накопительное обновление, воспользуйтесь следующей таблицей нагрузочного тестирования для получения метрик, чтобы определить, работают ли серверы группового чата в оптимальной работоспособности.

### <a name="test-environment-and-user-model"></a>Тестовая среда и пользовательская модель

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th> </th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Три сервера группового чата в пуле группового чата, каждая из которых имеет 8 ГБ памяти и 8 процессоров.</p></td>
</tr>
<tr class="even">
<td><p>Два интерфейсных сервера Lync Server 2013 в Enterprise Edition.</p></td>
</tr>
<tr class="odd">
<td><p>60 000 одновременно работающих пользователей на трех серверах группового чата.</p></td>
</tr>
<tr class="even">
<td><p>25 000 каналы, размещенные по пулу группового чата.</p></td>
</tr>
<tr class="odd">
<td><p>Размер канала:</p>
<ul>
<li><p>Малый размер канала: 30</p></li>
<li><p>Средний размер канала: 150</p></li>
<li><p>Большой размер канала: 2500</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Число каналов:</p>
<ul>
<li><p>Число маленьких каналов: 24 000</p></li>
<li><p>Число средних каналов 800</p></li>
<li><p>Число больших каналов 24</p></li>
<li><p>Общее число каналов 24 824</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Каналы приглашений:</p>
<ul>
<li><p>Половина каналов были приглашены каналы</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Число каналов, к которым присоединяется пользователь:</p>
<ul>
<li><p>Малый размер: 12</p></li>
<li><p>Средний: 2</p></li>
<li><p>Крупный: 1</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Скорость соединения:</p>
<ul>
<li><p>10, каждую секунду, в секунду на один сервер</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Скорость выхода:</p>
<ul>
<li><p>10, каждую секунду, в секунду на один сервер</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Частота чата:</p>
<ul>
<li><p>20 всего в секунду, 6.66/сек на сервер</p></li>
</ul></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> Следующие номера счетчиков производительности, скорее всего, будут отличаться при использовании различных спецификаций оборудования или профилей пользователей.



</div>

### <a name="performance-counter-to-be-monitored"></a>Отслеживаемый счетчик производительности

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Счетчик производительности</th>
<th>Пороговые значения</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Процесс (Чаннелсервице)-&gt;% загруженности процессора</p></td>
<td><p>Минимум: 0</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

