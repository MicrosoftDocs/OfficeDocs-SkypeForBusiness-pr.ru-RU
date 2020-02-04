---
title: 'Lync Server 2013: представление сеанса'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Session view
ms:assetid: 49e33f5b-45d0-4146-a5a4-76954d895a98
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688048(v=OCS.15)
ms:contentKeyID: 49733641
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6a153899fd484da861088a8e7672a69707e46a59
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764817"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="session-view-in-lync-server-2013"></a>Представление сеанса в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-03_

В представлении сеанса хранятся сведения о сеансах с записями в базе данных. Это представление было представлено в Microsoft Lync Server 2013.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Столбец</th>
<th>Тип данных</th>
<th>Подробности</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>конференцедатетиме</p></td>
<td><p>datetime</p></td>
<td><p>На которую ссылается таблица Медиалине.</p></td>
</tr>
<tr class="even">
<td><p>конференцеури</p></td>
<td><p>nvarchar (450)</p></td>
<td><p>Универсальный код ресурса (URI) для Конференции, если это конференция, или Диалогид, если это одноранговый сеанс.</p></td>
</tr>
<tr class="odd">
<td><p>Анализ</p></td>
<td><p>varchar (max)</p></td>
<td><p>Идентификатор корреляции для сеанса.</p></td>
</tr>
<tr class="even">
<td><p>диалогкатегори</p></td>
<td><p>бит</p></td>
<td><p>Категория диалогового окна; 0 — это сервер Lync Server для устранения проблем; 1 — это сервер исправлений для шлюза PSTN Gateway.</p></td>
</tr>
<tr class="odd">
<td><p>медиатионсервербипассфлаг</p></td>
<td><p>бит</p></td>
<td><p>Указывает, был ли звонок пропущен.</p></td>
</tr>
<tr class="even">
<td><p>медиабипассварнингфлаг</p></td>
<td><p>целое</p></td>
<td><p>Это поле, если оно указано, указывает, почему звонок не обходится даже в том случае, если идентификаторы обхода не совпадают. Для Lync Server определено только одно значение:</p>
<p>0x0001 — Неизвестный идентификатор обхода для сетевого адаптера по умолчанию</p></td>
</tr>
<tr class="odd">
<td><p>StartTime</p></td>
<td><p>datetime</p></td>
<td><p>Время начала звонка.</p></td>
</tr>
<tr class="even">
<td><p>EndTime</p></td>
<td><p>datetime</p></td>
<td><p>Время окончания звонка.</p></td>
</tr>
<tr class="odd">
<td><p>каллерпул</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Полное доменное имя пула вызывающего абонента.</p></td>
</tr>
<tr class="even">
<td><p>каллипул</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Полное доменное имя пула вызываемых абонентов.</p></td>
</tr>
<tr class="odd">
<td><p>каллерпаи</p></td>
<td><p>nvarchar (450)</p></td>
<td><p>Универсальный код ресурса (URI) удостоверения вызывающего абонента.</p></td>
</tr>
<tr class="even">
<td><p>каллипаи</p></td>
<td><p>nvarchar (450)</p></td>
<td><p>КОД URI удостоверения, утвержденный вызываемым p.</p></td>
</tr>
<tr class="odd">
<td><p>каллерендпоинт</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Имя конечной точки вызывающего абонента.</p></td>
</tr>
<tr class="even">
<td><p>каллиендпоинт</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Имя конечной точки вызывающего абонента.</p></td>
</tr>
<tr class="odd">
<td><p>каллерусеражент</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Строка агента пользователя вызывающего абонента.</p></td>
</tr>
<tr class="even">
<td><p>каллерусераженттипе</p></td>
<td><p>smallint</p></td>
<td><p>Тип агента пользователя вызывающего абонента. Дополнительные сведения: <a href="lync-server-2013-useragent-table.md">Таблица UserAgent в Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p>каллерусераженткатегори</p></td>
<td><p>nvarchar (64)</p></td>
<td><p>Категория агента пользователя вызывающего абонента. Дополнительные сведения <a href="lync-server-2013-useragentdef-table-qoe.md">усеражентдеф в таблице "QoE" в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p>каллиусеражент</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Строка агента пользователя вызываемого абонента.</p></td>
</tr>
<tr class="odd">
<td><p>каллиусераженттипе</p></td>
<td><p>smallint</p></td>
<td><p>Тип агента пользователя для вызываемого абонента. Дополнительные сведения: <a href="lync-server-2013-useragent-table.md">Таблица UserAgent в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p>каллиусераженткатегори</p></td>
<td><p>nvarchar (64)</p></td>
<td><p>Категория агента пользователя для вызываемого абонента. Дополнительные сведения <a href="lync-server-2013-useragentdef-table-qoe.md">усеражентдеф в таблице "QoE" в Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p>каллерури</p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI вызывающего абонента.</p></td>
</tr>
<tr class="even">
<td><p>каллиури</p></td>
<td><p>nvarchar (450)</p></td>
<td><p>Универсальный код ресурса (URI) вызываемого абонента.</p></td>
</tr>
<tr class="odd">
<td><p>каллприоирти</p></td>
<td><p>целое</p></td>
<td><p>Приоритет звонка.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

