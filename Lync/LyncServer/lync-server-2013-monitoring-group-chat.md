---
title: 'Lync Server 2013: отслеживание группового чата'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Monitoring group chat
ms:assetid: bddcf0be-ebf3-46bc-90c7-2576877734fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720924(v=OCS.15)
ms:contentKeyID: 63969648
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 74897191cac7559237e961b7600a3ed478d11e58
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826684"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-group-chat-in-lync-server-2013"></a>Мониторинг группового чата в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2014-08-04_

Мы настоятельно рекомендуем использовать последнюю версию [общего установщика обновлений на сервере](http://support.microsoft.com/kb/968802) , доступную в центре загрузки Майкрософт, для повышения производительности.

Предполагается, что вы используете Последнее накопительное обновление, для метрики, чтобы понять, работают ли серверы группового чата в оптимальной работоспособности, используйте следующую таблицу с нагрузочным тестированием.

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
<td><p>Три сервера группового чата в пуле группового чата, каждый из которых имеет 8 ГБ памяти и 8 процессоров.</p></td>
</tr>
<tr class="even">
<td><p>Два внешних сервера Lync Server 2013 в выпуске Enterprise Edition.</p></td>
</tr>
<tr class="odd">
<td><p>60 000 одновременные пользователи на трех серверах группового чата.</p></td>
</tr>
<tr class="even">
<td><p>каналы 25 000, размещенные по группе группового чата.</p></td>
</tr>
<tr class="odd">
<td><p>Размер канала:</p>
<ul>
<li><p>Размер мелкого канала: 30</p></li>
<li><p>Средний размер канала: 150</p></li>
<li><p>Размер большого канала: 2500</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Число каналов:</p>
<ul>
<li><p>Число малых каналов: 24 000</p></li>
<li><p>Число средних каналов 800</p></li>
<li><p>Число больших каналов 24</p></li>
<li><p>Всего каналов 24 824</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Пригласите каналы:</p>
<ul>
<li><p>Половина каналов согласитесь с каналами</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Количество каналов, к которым пользователь присоединяется:</p>
<ul>
<li><p>Мелкий: 12</p></li>
<li><p>Средний: 2</p></li>
<li><p>Крупный: 1</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Скорость соединения:</p>
<ul>
<li><p>10 всего за секунду, с 3,33 на сервер</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Скорость выхода:</p>
<ul>
<li><p>10 всего за секунду, с 3,33 на сервер</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Ставка чата:</p>
<ul>
<li><p>20 всего в секунду, 6.66/сек на сервер</p></li>
</ul></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> Указанные ниже номера счетчиков производительности, как правило, зависят от конфигурации разных аппаратных спецификаций или профилей пользователей.



</div>

### <a name="performance-counter-to-be-monitored"></a>Счетчик производительности для наблюдения

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
<td><p>Процесс (Чаннелсервице)-&gt;% Processor Time</p></td>
<td><p>Минимум: 0</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

