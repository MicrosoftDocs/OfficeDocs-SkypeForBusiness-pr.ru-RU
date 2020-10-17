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
ms.openlocfilehash: 60fa841f7f88e0da2c428ae68c5007fb79e6c69d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536326"
---
# <a name="tblprincipaltype-in-lync-server-2013"></a>tblPrincipalType в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-12_

Таблица tblPrincipalType содержит типы субъектов для разделения содержимого таблицы tblPrincipal по категориям.

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
<td><p>птипеид</p></td>
<td><p>smallint, не может быть null</p></td>
<td><p>Идентификатор типа субъекта.</p></td>
</tr>
<tr class="even">
<td><p>птипедеск</p></td>
<td><p>nvarchar (256), не может быть null</p></td>
<td><p>Описание типа.</p></td>
</tr>
<tr class="odd">
<td><p>птипеиссистемусер</p></td>
<td><p>bit, не может быть null</p></td>
<td><p>Имеет значение True, если тип соответствует субъектам, которые используются во внутренних целях.</p></td>
</tr>
<tr class="even">
<td><p>птипеисусер</p></td>
<td><p>bit, не может быть null</p></td>
<td><p>Имеет значение True, если тип соответствует пользователям.</p></td>
</tr>
</tbody>
</table>


### <a name="key"></a>Key

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


### <a name="principal-values"></a>Значения субъектов

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
<th>Role</th>
<th>Описание</th>
<th>Пользователь</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1,1</p></td>
<td><p>Любой</p></td>
<td><p>Общий субъект неизвестного типа. Не используется в таблице tblPrincipal.</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>2</p></td>
<td><p>анюсер</p></td>
<td><p>Общий субъект типа "пользователь". Не используется в таблице tblPrincipal.</p></td>
<td><p>Да</p></td>
</tr>
<tr class="odd">
<td><p>4</p></td>
<td><p>аниграуп</p></td>
<td><p>Общий субъект типа "группа". Не используется в таблице tblPrincipal.</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>4 </p></td>
<td><p>системусер</p></td>
<td><p>Субъект, используемый сервером сохраняемого чата для внутреннего использования.</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>5 </p></td>
<td><p>Пользователь</p></td>
<td><p>Обычный пользователь.</p></td>
<td><p>Да</p></td>
</tr>
<tr class="even">
<td><p>8 </p></td>
<td><p>DC</p></td>
<td><p>Контроллер домена доменных служб Active Directory.</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>9 </p></td>
<td><p>Группа</p></td>
<td><p>Группа безопасности Active Directory.</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>10 </p></td>
<td><p>Folder</p></td>
<td><p>Контейнер или подразделение Active Directory.</p></td>
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

