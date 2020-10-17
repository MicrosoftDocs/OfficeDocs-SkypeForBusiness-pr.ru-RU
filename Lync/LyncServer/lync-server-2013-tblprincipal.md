---
title: 'Lync Server 2013: tblPrincipal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipal
ms:assetid: 79a24502-b4ce-41f0-8979-8caddf535338
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558667(v=OCS.15)
ms:contentKeyID: 48184571
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5e4b0c8154429fa68bc05e757130e0b92a47e65c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523766"
---
# <a name="tblprincipal-in-lync-server-2013"></a>tblPrincipal в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-12_

Таблица tblPrincipal содержит все субъекты, включая пользователей, папки и группы.

### <a name="columns"></a>Столбцы

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Столбец</th>
<th>Тип</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>prinID</p></td>
<td><p>int, not null</p></td>
<td><p>Идентификатор субъекта.</p></td>
</tr>
<tr class="even">
<td><p>прингуид</p></td>
<td><p>GUID, не null</p></td>
<td><p>Идентификатор GUID субъекта. Он широко используется в качестве альтернативного первичного ключа, так как его смысл пересекается с пространством доменных служб Active Directory. (GUID кэшированного субъекта аналогичен GUID соответствующего объекта Active Directory.)</p></td>
</tr>
<tr class="odd">
<td><p>принури</p></td>
<td><p>nvarchar (256), не может быть null</p></td>
<td><p>Универсальный код ресурса (URI) субъекта. Схема SIP используется для пользователей, а ma-grp — практически для всех остальных субъектов.</p></td>
</tr>
<tr class="even">
<td><p>приннаме</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Общее имя. Используется только для пользователей.</p></td>
</tr>
<tr class="odd">
<td><p>приндисплайнаме</p></td>
<td><p>Nvarchar (256)</p></td>
<td><p>Отображаемое имя. Используется только для пользователей.</p></td>
</tr>
<tr class="even">
<td><p>принкомпанинаме</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Название компании. Используется только для пользователей.</p></td>
</tr>
<tr class="odd">
<td><p>принемаил</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Электронная почта. Используется только для пользователей.</p></td>
</tr>
<tr class="even">
<td><p>принадпас</p></td>
<td><p>nvarchar (384)</p></td>
<td><p>Имя домена объекта Active Directory, кэшированной версией которого является субъект. Может иметь значение Null для типов, не являющихся объектами Active Directory (например, системных пользователей).</p></td>
</tr>
<tr class="odd">
<td><p>принадусерпринЦипалнаме</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Имя участника-пользователя. Используется только для обычных типов пользователя.</p></td>
</tr>
<tr class="even">
<td><p>приндисаблед</p></td>
<td><p>smallint, не null</p></td>
<td><ul>
<li><p>0 — субъект активен.</p></li>
<li><p>1 — субъект отключен, поскольку отключены возможности SIP пользователя.</p></li>
<li><p>2 — субъект удален, поскольку удален связанный объект Active Directory.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>принтипеид</p></td>
<td><p>smallint, не может быть null</p></td>
<td><p>Тип субъекта (из таблицы tblPrincipalType).</p></td>
</tr>
<tr class="even">
<td><p>принпулид</p></td>
<td><p>Целое</p></td>
<td><p>Назначение пула Lync для субъекта.</p></td>
</tr>
<tr class="odd">
<td><p>принполициид</p></td>
<td><p>Целое</p></td>
<td><p>Значение политики сервера сохраняемого чата для пользователя, если присутствует политика типов тегов.</p></td>
</tr>
<tr class="even">
<td><p>принаддедби</p></td>
<td><p>int</p></td>
<td><p>Идентификатор субъекта создателя.</p></td>
</tr>
<tr class="odd">
<td><p>принаддедон</p></td>
<td><p>bigint, не может быть null</p></td>
<td><p>Метка времени создания.</p></td>
</tr>
<tr class="even">
<td><p>принупдатедби</p></td>
<td><p>int</p></td>
<td><p>Идентификатор субъекта, выполнившего последнее обновление.</p></td>
</tr>
<tr class="odd">
<td><p>принупдатедон</p></td>
<td><p>bigint, не может быть null</p></td>
<td><p>Метка времени последнего обновления.</p></td>
</tr>
<tr class="even">
<td><p>принверифиедон</p></td>
<td><p>datetime, не может быть null</p></td>
<td><p>Дата и время последнего обновления субъекта в результате синхронизации с Active Directory.</p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a>Keys

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Столбец</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>prinID</p></td>
<td><p>Первичный ключ.</p></td>
</tr>
<tr class="even">
<td><p>принтипеид</p></td>
<td><p>Внешний ключ с подстановкой в таблице tblPrincipalType.ptypeID.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

