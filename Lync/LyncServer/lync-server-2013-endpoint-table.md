---
title: 'Lync Server 2013: таблица Endpoint'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Endpoint table
ms:assetid: 500f330d-4d7d-4e88-b1cc-fef9a9de6b5c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398327(v=OCS.15)
ms:contentKeyID: 48184098
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 201e2ae3b44f59f0edb128f58af6c18e18e51931
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042236"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="endpoint-table-in-lync-server-2013"></a>Таблица конечной точки в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-02_

Таблица Endpoint — это вспомогательная таблица, в которой хранятся сведения о конечных точках, которые участвовали в сеансах, записанных в базе данных. Каждая запись в таблице представляет одну конечную точку.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Column</strong></th>
<th><strong>Тип данных</strong></th>
<th><strong>Ключ или индекс</strong></th>
<th><strong>Details</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>ендпоинткэй</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>Уникальный номер, идентифицирующий эту конечную точку.</p></td>
</tr>
<tr class="even">
<td><p><strong>Название</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Уникальные</p></td>
<td><p>Имя конечной точки.</p></td>
</tr>
<tr class="odd">
<td><p><strong>СОВМЕСТИМ</strong></p></td>
<td><p>nvarchar(128</p></td>
<td><p> </p></td>
<td><p>Операционная система (ОС) конечной точки.</p></td>
</tr>
<tr class="even">
<td><p><strong>кпунаме</strong></p></td>
<td><p>nvarchar(128</p></td>
<td></td>
<td><p>Имя ЦП конечной точки.</p></td>
</tr>
<tr class="odd">
<td><p><strong>кпунумберофкорес</strong></p></td>
<td><p>smallint</p></td>
<td></td>
<td><p>Количество ядер ЦП конечной точки.</p></td>
</tr>
<tr class="even">
<td><p><strong>кпупроцессорспид</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Скорость ЦП конечной точки.</p></td>
</tr>
<tr class="odd">
<td><p><strong>виртуализатионфлаг</strong></p></td>
<td><p>tinyint</p></td>
<td></td>
<td><p>Битовый флаг, указывающий, работает ли система в виртуализированной среде:</p>
<ul>
<li><p>0x0000 — нет</p></li>
<li><p>0x0001 — HyperV</p></li>
<li><p>0x0002 — VMWare</p></li>
<li><p>0x0004 — Virtual PC</p></li>
<li><p>0x0008 — компьютер Xen</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

