---
title: 'Lync Server 2013: таблица таблица videometricsthreshold'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: VideoMetricsThreshold table
ms:assetid: 2e2f4711-35ba-48c6-b15b-5aba61c4eb75
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204778(v=OCS.15)
ms:contentKeyID: 48183736
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9ffd2c289917c5ccf0ec3a484284fecca3323810
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007258"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="videometricsthreshold-table-in-lync-server-2013"></a>Таблица Таблица videometricsthreshold в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-02_

Таблица VideoMetricsThreshold содержит оптимальные и допустимые значения метрик качества взаимодействия, используемых для видеозвонков.


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
<td><p><strong>CallType</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>Тип размещенного вызова.</p></td>
</tr>
<tr class="even">
<td><p><strong>видеопостфекплроптимал</strong></p></td>
<td><p>десятичное число (5, 2)</p></td>
<td></td>
<td><p>Значение по умолчанию — 0,05.</p></td>
</tr>
<tr class="odd">
<td><p><strong>видеопостфекплракцептабле</strong></p></td>
<td><p>десятичное число (5, 2)</p></td>
<td></td>
<td><p>Значение по умолчанию — 0,10.</p></td>
</tr>
<tr class="even">
<td><p><strong>видеолокалфрамелостперцентажеаверажеоптимал</strong></p></td>
<td><p>десятичное число (5, 2)</p></td>
<td></td>
<td><p>Значение по умолчанию — 5,0.</p></td>
</tr>
<tr class="odd">
<td><p><strong>видеолокалфрамелостперцентажеаверажеакцептабле</strong></p></td>
<td><p>десятичное число (5, 2)</p></td>
<td></td>
<td><p>Значение по умолчанию — 10,0.</p></td>
</tr>
<tr class="even">
<td><p><strong>реквфрамератеаверажеоптимал</strong></p></td>
<td><p>десятичное число (9, 4)</p></td>
<td></td>
<td><p>Значение по умолчанию — 12,0000.</p></td>
</tr>
<tr class="odd">
<td><p><strong>реквфрамератеаверажеакцептабле</strong></p></td>
<td><p>десятичное число (9, 4)</p></td>
<td></td>
<td><p>Значение по умолчанию — 7,0000.</p></td>
</tr>
<tr class="even">
<td><p><strong>ловфрамератекаллперцентоптимал</strong></p></td>
<td><p>десятичное число (5, 2)</p></td>
<td></td>
<td><p>Значение по умолчанию — 5,0.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ловфрамератекаллперцентакцептабле</strong></p></td>
<td><p>десятичное число (5, 2)</p></td>
<td></td>
<td><p>Значение по умолчанию — 10,0.</p></td>
</tr>
<tr class="even">
<td><p><strong>ловресолутионкаллперцентоптимал</strong></p></td>
<td><p>десятичное число (5, 2)</p></td>
<td></td>
<td><p>Значение по умолчанию — 5,0.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ловресолутионкаллперцентакцептабле</strong></p></td>
<td><p>десятичное число (5, 2)</p></td>
<td></td>
<td><p>Значение по умолчанию — 10,0.</p></td>
</tr>
<tr class="even">
<td><p><strong>видеопаккетлоссратеоптимал</strong></p></td>
<td><p>фоат</p></td>
<td></td>
<td><p>Значение по умолчанию — 0,05.</p></td>
</tr>
<tr class="odd">
<td><p><strong>видеопаккетлоссратеакцептабле</strong></p></td>
<td><p>с плавающей запятой</p></td>
<td></td>
<td><p>Значение по умолчанию — 0,10.</p></td>
</tr>
<tr class="even">
<td><p><strong>видеофрамератеавгоптимал</strong></p></td>
<td><p>с плавающей запятой</p></td>
<td></td>
<td><p>Значение по умолчанию — 12.</p></td>
</tr>
<tr class="odd">
<td><p><strong>видеофрамератеавгакцептабле</strong></p></td>
<td><p>с плавающей запятой</p></td>
<td></td>
<td><p>Значение по умолчанию — 7.</p></td>
</tr>
<tr class="even">
<td><p><strong>динамиккапабилитиперцентоптимал</strong></p></td>
<td><p>десятичное число (5, 2)</p></td>
<td></td>
<td><p>Значение по умолчанию — 5,00.</p></td>
</tr>
<tr class="odd">
<td><p><strong>динамиккапабилитиперцентакцептабле</strong></p></td>
<td><p>десятичное число (5, 2)</p></td>
<td></td>
<td><p>Значение по умолчанию — 10,00.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

