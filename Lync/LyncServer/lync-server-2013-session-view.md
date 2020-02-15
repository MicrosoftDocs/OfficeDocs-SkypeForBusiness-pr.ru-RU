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
ms.openlocfilehash: 7d20d748f9c9754efab768a702f1272bc70d889e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051301"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="session-view-in-lync-server-2013"></a>Представление сеанса в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-03_

В представлении сеанса сохраняются сведения о сеансах, для которых есть записи в базе данных. Это представление было представлено в Microsoft Lync Server 2013.


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
<th>Сведения</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>конференцедатетиме</p></td>
<td><p>datetime</p></td>
<td><p>Ссылка из таблицы линии медиаданных.</p></td>
</tr>
<tr class="even">
<td><p>конференцеури</p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI конференции, если это конференция, или DialogID, если это сеанс между одноранговыми узлами.</p></td>
</tr>
<tr class="odd">
<td><p>Correlation</p></td>
<td><p>varchar (max)</p></td>
<td><p>Идентификатор корреляции сеанса</p></td>
</tr>
<tr class="even">
<td><p>диалогкатегори</p></td>
<td><p>Битовая</p></td>
<td><p>Категория диалоговых окон; 0 — сервер Lync Server — это ветвь сервера-посредника; 1 — сервер-посредник для шлюза PSTN.</p></td>
</tr>
<tr class="odd">
<td><p>медиатионсервербипассфлаг</p></td>
<td><p>Битовая</p></td>
<td><p>Указывает, был ли обойден вызов.</p></td>
</tr>
<tr class="even">
<td><p>медиабипассварнингфлаг</p></td>
<td><p>int</p></td>
<td><p>Если это поле присутствует, оно указывает, почему вызов не может быть обойден, даже если идентификаторы обхода совпадают. Для Lync Server определено только одно значение:</p>
<p>0x0001 – неизвестный идентификатор обхода для сетевого адаптера по умолчанию</p></td>
</tr>
<tr class="odd">
<td><p>StartTime</p></td>
<td><p>datetime</p></td>
<td><p>Время начала вызова.</p></td>
</tr>
<tr class="even">
<td><p>EndTime</p></td>
<td><p>datetime</p></td>
<td><p>Время окончания вызова.</p></td>
</tr>
<tr class="odd">
<td><p>каллерпул</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Полное доменное имя пула вызывающего абонента.</p></td>
</tr>
<tr class="even">
<td><p>каллипул</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Полное доменное имя пула вызываемого абонента.</p></td>
</tr>
<tr class="odd">
<td><p>каллерпаи</p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI удостоверения PAI вызывающего абонента.</p></td>
</tr>
<tr class="even">
<td><p>каллипаи</p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI удостоверения PAI вызываемого абонента.</p></td>
</tr>
<tr class="odd">
<td><p>каллерендпоинт</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Имя конечной точки вызывающего абонента.</p></td>
</tr>
<tr class="even">
<td><p>каллиендпоинт</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Имя конечной точки абонента.</p></td>
</tr>
<tr class="odd">
<td><p>каллерусеражент</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Строка агента пользователя вызывающего абонента.</p></td>
</tr>
<tr class="even">
<td><p>каллерусераженттипе</p></td>
<td><p>smallint</p></td>
<td><p>Тип агента пользователя звонящего абонента. Дополнительные сведения см. <a href="lync-server-2013-useragent-table.md">в таблице UserAgent в Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p>каллерусераженткатегори</p></td>
<td><p>nvarchar (64)</p></td>
<td><p>Категория агента пользователя вызывающего абонента. Для получения подробных сведений ознакомьтесь со статьей <a href="lync-server-2013-useragentdef-table-qoe.md">таблица таблица useragentdef (QoE) в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p>каллиусеражент</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Строка агента пользователя вызываемого абонента.</p></td>
</tr>
<tr class="odd">
<td><p>каллиусераженттипе</p></td>
<td><p>smallint</p></td>
<td><p>Тип агента пользователя вызываемого абонента. Дополнительные сведения см. <a href="lync-server-2013-useragent-table.md">в таблице UserAgent в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p>каллиусераженткатегори</p></td>
<td><p>nvarchar (64)</p></td>
<td><p>Категория агента пользователя вызываемого абонента. Для получения подробных сведений ознакомьтесь со статьей <a href="lync-server-2013-useragentdef-table-qoe.md">таблица таблица useragentdef (QoE) в Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p>каллерури</p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI вызывающего абонента.</p></td>
</tr>
<tr class="even">
<td><p>каллиури</p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI вызываемого абонента.</p></td>
</tr>
<tr class="odd">
<td><p>каллприоирти</p></td>
<td><p>int</p></td>
<td><p>Приоритет вызова.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

