---
title: 'Lync Server 2013: tblEnumValue'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblEnumValue
ms:assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615025(v=OCS.15)
ms:contentKeyID: 48185040
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d182a3689ae38d4117b45d6590bb2ccd08c0a8b7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42027060"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblenumvalue-in-lync-server-2013"></a>tblEnumValue в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-06-28_

tblEnumValue — это встроенная таблица, которая содержит значения отображения и поведения атрибутов, используемых в таблице Node.

### <a name="columns"></a>Columns

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
<td><p>валуеид</p></td>
<td><p>smallint, не может быть null</p></td>
<td><p>ИД значения.</p></td>
</tr>
<tr class="even">
<td><p>attributeID</p></td>
<td><p>smallint, не может быть null</p></td>
<td><p>ИД атрибута.</p></td>
</tr>
<tr class="odd">
<td><p>attributeValue</p></td>
<td><p>nvarchar (256), not null</p></td>
<td><p>Имя значения.</p></td>
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
<td><p>валуеид</p></td>
<td><p>Первичный ключ.</p></td>
</tr>
<tr class="even">
<td><p>attributeID</p></td>
<td><p>Внешний ключ с поиском в таблице tblEnumAttribute.attributeID.</p></td>
</tr>
</tbody>
</table>


### <a name="table-values"></a>Значения таблицы

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>валуеид</th>
<th>attributeID</th>
<th>attributeValue</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>2 </p></td>
<td><p>1 </p></td>
<td><p>закрытый</p></td>
</tr>
<tr class="even">
<td><p>3 </p></td>
<td><p>1 </p></td>
<td><p>scope</p></td>
</tr>
<tr class="odd">
<td><p>4 </p></td>
<td><p>2 </p></td>
<td><p>обычный</p></td>
</tr>
<tr class="even">
<td><p>5 </p></td>
<td><p>2 </p></td>
<td><p>аудитория</p></td>
</tr>
<tr class="odd">
<td><p>6 </p></td>
<td><p>1 </p></td>
<td><p>окно</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a>См. также


[tblNode в Lync Server 2013](lync-server-2013-tblnode.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

