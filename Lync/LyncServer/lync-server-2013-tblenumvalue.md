---
title: 'Lync Server 2013: tblEnumValue'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblEnumValue
ms:assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615025(v=OCS.15)
ms:contentKeyID: 48185040
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1758daf16575491960415647e4c9bc4b43920d26
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849555"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblenumvalue-in-lync-server-2013"></a>tblEnumValue в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-06-28_

Тбленумвалуе — это жесткая таблица, содержащая значения видимости и поведения атрибутов, используемых в таблице node.

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
<td><p>Валуеид</p></td>
<td><p>smallint, NOT NULL</p></td>
<td><p>Идентификатор значения.</p></td>
</tr>
<tr class="even">
<td><p>attributeID</p></td>
<td><p>smallint, NOT NULL</p></td>
<td><p>Идентификатор атрибута.</p></td>
</tr>
<tr class="odd">
<td><p>attributeValue</p></td>
<td><p>nvarchar (256), NOT NULL</p></td>
<td><p>Имя значения.</p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a>Параметры

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
<td><p>Валуеид</p></td>
<td><p>Первичный ключ.</p></td>
</tr>
<tr class="even">
<td><p>attributeID</p></td>
<td><p>Внешний ключ с подстановкой в таблице Тбленуматтрибуте. attributeID.</p></td>
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
<th>Валуеид</th>
<th>attributeID</th>
<th>attributeValue</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>2</p></td>
<td><p>1</p></td>
<td><p>закрытые</p></td>
</tr>
<tr class="even">
<td><p>3</p></td>
<td><p>1</p></td>
<td><p>област</p></td>
</tr>
<tr class="odd">
<td><p>4</p></td>
<td><p>2</p></td>
<td><p>нормальный</p></td>
</tr>
<tr class="even">
<td><p>5</p></td>
<td><p>2</p></td>
<td><p>Аудиториум</p></td>
</tr>
<tr class="odd">
<td><p>6</p></td>
<td><p>1</p></td>
<td><p>запуска</p></td>
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

