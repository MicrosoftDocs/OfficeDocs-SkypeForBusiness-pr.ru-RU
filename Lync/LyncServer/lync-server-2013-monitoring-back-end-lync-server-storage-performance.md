---
title: 'Lync Server 2013: Мониторинг производительности сервера Lync Server Storage'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Monitoring back end Lync Server 2013 storage performance
ms:assetid: 71627c70-1953-4ac2-afbe-f3ad85be0f44
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720917(v=OCS.15)
ms:contentKeyID: 63969619
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b4c63956cebc7f532f92b6e0729bdfe811d0fdfb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826761"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-back-end-lync-server-2013-storage-performance"></a>Мониторинг производительности сервера Lync Server 2013 в серверной части

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2014-05-02_

Серверные базы данных Lync Server 2013 являются важной частью развертывания Lync Server 2013. Мы рекомендуем постоянно отслеживать базы данных и соответствующие журналы транзакций, чтобы обеспечить оптимальное выполнение серверной части Lync Server 2013.

В приведенной ниже таблице указаны счетчики производительности, которые необходимо отслеживать для получения сведений о производительности хранилища. Базовые значения для этих счетчиков должны определяться первыми (когда система находится в обычном режиме, ожидаемая загрузка) для понимания изменений производительности при напряжении системы.

### <a name="performance-counters-to-be-monitored"></a>Наблюдаемые счетчики производительности

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Счетчик производительности</th>
<th>Пороговые значения базового плана</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Транзакций в секунду (RTC)</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Транзакций в секунду (рткдин)</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Транзакций в секунду (база данных tempdb)</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Сбросов журнала в секунду (RTC)</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Сбросов журнала в секунду (рткдин)</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Сбросов журнала в секунду (tempdb)</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Обращений к диску/сек (чтение и запись) — запись данных RTC.</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Обмен данными с диском/сек-журнал событий реального времени</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Обращений к диску в секунду — рткдин DB</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Обращений к диску/сек-журнал рткдин</p></td>
<td></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

