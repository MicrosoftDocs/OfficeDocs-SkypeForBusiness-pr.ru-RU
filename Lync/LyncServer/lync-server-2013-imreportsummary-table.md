---
title: 'Lync Server 2013: таблица Имрепортсуммари'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IMReportSummary table
ms:assetid: 27ff9453-53f2-4fae-b637-70a086c9df96
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204753(v=OCS.15)
ms:contentKeyID: 48183673
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5e750da3fd42a726012f089291d3e2c770e52b44
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526636"
---
# <a name="imreportsummary-table-in-lync-server-2013"></a>Таблица Имрепортсуммари в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-08-20_

В таблице IMReportSummaryTable приводится общий отчет о сеансах обмена мгновенными сообщениями, которые проводятся в организации. Эта таблица была введена в Microsoft Lync Server 2013.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Столбец</th>
<th>Тип данных</th>
<th>Ключ или индекс</th>
<th>Сведения</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>StartTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Primary</p></td>
<td><p>Дата и время начала сеанса обмена мгновенными сообщениями.</p></td>
</tr>
<tr class="even">
<td><p><strong>Время</strong></p></td>
<td><p>char (1)</p></td>
<td><p>Primary</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><strong>PoolFQDN</strong></p></td>
<td><p>nvarchar (257)</p></td>
<td><p>Primary</p></td>
<td><p>Полное доменное имя пула, в котором размещается сеанс.</p></td>
</tr>
<tr class="even">
<td><p><strong>аустипе</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>Приоритет звонка (например, срочный или несрочный). Сведения о приоритетах хранятся в <a href="lync-server-2013-callpriorities-table.md">таблице таблица callpriorities в Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>сессионкаунт</strong></p></td>
<td><p>типу</p></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><strong>мсгкаунт</strong></p></td>
<td><p>типу</p></td>
<td></td>
<td><p>Общее число мгновенных сообщений, отправленных в рамках сеанса.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

