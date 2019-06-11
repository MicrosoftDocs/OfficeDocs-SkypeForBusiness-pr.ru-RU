---
title: 'Lync Server 2013: таблица Имрепортсуммари'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: IMReportSummary table
ms:assetid: 27ff9453-53f2-4fae-b637-70a086c9df96
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204753(v=OCS.15)
ms:contentKeyID: 48183673
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c2254bafe059cc1a4bc6436580e9d604711f5fb3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834021"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="imreportsummary-table-in-lync-server-2013"></a>Таблица Имрепортсуммари в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-08-20_

Имрепортсуммаритабле предоставляет общий отчет о сеансах обмена мгновенными сообщениями, которые хранятся в Организации. Эта таблица введена в Microsoft Lync Server 2013.


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
<th>Ключ/индекс</th>
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
<td><p><strong>Тимепериод</strong></p></td>
<td><p>char (1)</p></td>
<td><p>Primary</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><strong>Пулфкдн</strong></p></td>
<td><p>nvarchar (257)</p></td>
<td><p>Primary</p></td>
<td><p>Полное доменное имя пула, на котором размещается сеанс.</p></td>
</tr>
<tr class="even">
<td><p><strong>Аустипе</strong></p></td>
<td><p>целое</p></td>
<td><p>Primary</p></td>
<td><p>Приоритет звонка (например, срочной или несрочный). Сведения о приоритетах хранятся в <a href="lync-server-2013-callpriorities-table.md">таблице каллприоритиес в Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Сессионкаунт</strong></p></td>
<td><p>bigint</p></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><strong>Мсгкаунт</strong></p></td>
<td><p>bigint</p></td>
<td></td>
<td><p>Общее количество мгновенных сообщений, пересылаемых во время сеанса.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

