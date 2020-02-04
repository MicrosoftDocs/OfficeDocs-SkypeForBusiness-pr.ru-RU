---
title: 'Lync Server 2013: tblPrincipalType'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipalType
ms:assetid: 32e1c1d6-80f4-4624-bf4e-b4c77d3982fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558633(v=OCS.15)
ms:contentKeyID: 48183787
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6731d0bcda6e4e66b1b498a5f1bf91023627b1f0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764089"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipaltype-in-lync-server-2013"></a>tblPrincipalType в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-09-12_

ТблпринЦипалтипе содержит основные типы для классификации содержимого в таблице ТблпринЦипал.

### <a name="columns"></a>Столбцов

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
<td><p>птипеид</p></td>
<td><p>smallint, NOT NULL</p></td>
<td><p>Идентификатор типа участника.</p></td>
</tr>
<tr class="even">
<td><p>птипедеск</p></td>
<td><p>nvarchar (256), NOT NULL</p></td>
<td><p>Описание типа.</p></td>
</tr>
<tr class="odd">
<td><p>птипеиссистемусер</p></td>
<td><p>bit, NOT NULL</p></td>
<td><p>Значение true, если тип соответствует участникам, которые используются для внутренних целей.</p></td>
</tr>
<tr class="even">
<td><p>птипеисусер</p></td>
<td><p>bit, NOT NULL</p></td>
<td><p>Значение true, если тип является пользовательским типом.</p></td>
</tr>
</tbody>
</table>


### <a name="key"></a>Ключ

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
<td><p>птипеид</p></td>
<td><p>Первичный ключ.</p></td>
</tr>
</tbody>
</table>


### <a name="principal-values"></a>Основные значения

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>ID</th>
<th>Должность</th>
<th>Описание</th>
<th>Пользователь</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1</p></td>
<td><p>Любой</p></td>
<td><p>Универсальный принципал без известного типа. Не используется в таблице ТблпринЦипал.</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>2</p></td>
<td><p>анюсер</p></td>
<td><p>Универсальный принципал для типа пользователя. Не используется в таблице ТблпринЦипал.</p></td>
<td><p>Да</p></td>
</tr>
<tr class="odd">
<td><p>3</p></td>
<td><p>аниграуп</p></td>
<td><p>Универсальный принципал с семантикой группы. Не используется в таблице ТблпринЦипал.</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>4</p></td>
<td><p>системусер</p></td>
<td><p>Основной сервер, который используется для внутренних целей с помощью сохраняемого сервера чата.</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>5</p></td>
<td><p>Пользователь</p></td>
<td><p>Обычный пользователь.</p></td>
<td><p>Да</p></td>
</tr>
<tr class="even">
<td><p>No8</p></td>
<td><p>NУДАЛЕННЫЙ</p></td>
<td><p>Контроллер домена доменных служб Active Directory.</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>@</p></td>
<td><p>Сгруппирован</p></td>
<td><p>Группа безопасности Active Directory.</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>5-10</p></td>
<td><p>Нее</p></td>
<td><p>Контейнер Active Directory или подразделение.</p></td>
<td></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a>См. также


[tblPrincipal в Lync Server 2013](lync-server-2013-tblprincipal.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

