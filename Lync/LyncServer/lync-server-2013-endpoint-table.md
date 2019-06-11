---
title: 'Lync Server 2013: таблица Endpoint'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Endpoint table
ms:assetid: 500f330d-4d7d-4e88-b1cc-fef9a9de6b5c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398327(v=OCS.15)
ms:contentKeyID: 48184098
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6cedf4d85cefd8a9fefb9f0ee4608f4a290fdc09
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834214"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="endpoint-table-in-lync-server-2013"></a>Таблица Endpoint в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-02_

Таблица конечных точек — это вспомогательная таблица, в которой хранятся сведения о конечных точках, участвующих в сеансах, записанных в базе данных. Каждая запись в таблице представляет одну конечную точку.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Столбец</strong></th>
<th><strong>Тип данных</strong></th>
<th><strong>Ключ/индекс</strong></th>
<th><strong>Сведения</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Ендпоинткэй</strong></p></td>
<td><p>целое</p></td>
<td><p>Primary</p></td>
<td><p>Уникальный номер, идентифицирующий эту конечную точку.</p></td>
</tr>
<tr class="even">
<td><p><strong>Имя</strong>.</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Повторя</p></td>
<td><p>Имя конечной точки.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OS</strong></p></td>
<td><p>nvarchar(128</p></td>
<td><p> </p></td>
<td><p>Операционная система (ОС) конечной точки.</p></td>
</tr>
<tr class="even">
<td><p><strong>Кпунаме</strong></p></td>
<td><p>nvarchar(128</p></td>
<td></td>
<td><p>Имя ЦП конечной точки.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Кпунумберофкорес</strong></p></td>
<td><p>smallint</p></td>
<td></td>
<td><p>Количество ядер ЦП конечной точки.</p></td>
</tr>
<tr class="even">
<td><p><strong>Кпупроцессорспид</strong></p></td>
<td><p>целое</p></td>
<td></td>
<td><p>Тактовая частота процессора для конечной точки.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Виртуализатионфлаг</strong></p></td>
<td><p>tinyint</p></td>
<td></td>
<td><p>Битовый флаг, указывающий на то, что система работает в виртуализованной среде.</p>
<ul>
<li><p>0x0000 — None (нет)</p></li>
<li><p>0x0001 — HyperV</p></li>
<li><p>0x0002 — VMWare</p></li>
<li><p>0x0004 — Virtual PC</p></li>
<li><p>0x0008 – ПК с Xen</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

