---
title: 'Lync Server 2013: таблица Видеометрикссрешолд'
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
ms.openlocfilehash: 93dc2fd539ccc24717939ccfa2ca93032fd9f25b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741989"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="videometricsthreshold-table-in-lync-server-2013"></a>Таблица Видеометрикссрешолд в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-02_

Таблица Видеометрикссрешолд имеет оптимальные и приемлемые значения для показателей качества взаимодействия, используемых с видеозвонками.


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
<td><p><strong>CallType</strong></p></td>
<td><p>целое</p></td>
<td><p>Primary</p></td>
<td><p>Тип размещенного звонка.</p></td>
</tr>
<tr class="even">
<td><p><strong>видеопостфекплроптимал</strong></p></td>
<td><p>десятичное число (5; 2)</p></td>
<td></td>
<td><p>Значение по умолчанию — 0,05.</p></td>
</tr>
<tr class="odd">
<td><p><strong>видеопостфекплракцептабле</strong></p></td>
<td><p>десятичное число (5; 2)</p></td>
<td></td>
<td><p>Значение по умолчанию — 0,10.</p></td>
</tr>
<tr class="even">
<td><p><strong>видеолокалфрамелостперцентажеаверажеоптимал</strong></p></td>
<td><p>десятичное число (5; 2)</p></td>
<td></td>
<td><p>Значение по умолчанию — 5,0.</p></td>
</tr>
<tr class="odd">
<td><p><strong>видеолокалфрамелостперцентажеаверажеакцептабле</strong></p></td>
<td><p>десятичное число (5; 2)</p></td>
<td></td>
<td><p>Значение по умолчанию — 10,0.</p></td>
</tr>
<tr class="even">
<td><p><strong>реквфрамератеаверажеоптимал</strong></p></td>
<td><p>десятичное число (9; 4)</p></td>
<td></td>
<td><p>Значение по умолчанию — 12,0000.</p></td>
</tr>
<tr class="odd">
<td><p><strong>реквфрамератеаверажеакцептабле</strong></p></td>
<td><p>десятичное число (9; 4)</p></td>
<td></td>
<td><p>Значение по умолчанию — 7,0000.</p></td>
</tr>
<tr class="even">
<td><p><strong>ловфрамератекаллперцентоптимал</strong></p></td>
<td><p>десятичное число (5; 2)</p></td>
<td></td>
<td><p>Значение по умолчанию — 5,0.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ловфрамератекаллперцентакцептабле</strong></p></td>
<td><p>десятичное число (5; 2)</p></td>
<td></td>
<td><p>Значение по умолчанию — 10.0/</p></td>
</tr>
<tr class="even">
<td><p><strong>ловресолутионкаллперцентоптимал</strong></p></td>
<td><p>десятичное число (5; 2)</p></td>
<td></td>
<td><p>Значение по умолчанию — 5,0.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ловресолутионкаллперцентакцептабле</strong></p></td>
<td><p>десятичное число (5; 2)</p></td>
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
<td><p>число с плавающей точкой</p></td>
<td></td>
<td><p>Значение по умолчанию — 0,10.</p></td>
</tr>
<tr class="even">
<td><p><strong>видеофрамератеавгоптимал</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td></td>
<td><p>Значением по умолчанию является 12.</p></td>
</tr>
<tr class="odd">
<td><p><strong>видеофрамератеавгакцептабле</strong></p></td>
<td><p>число с плавающей точкой</p></td>
<td></td>
<td><p>Значением по умолчанию является 7.</p></td>
</tr>
<tr class="even">
<td><p><strong>динамиккапабилитиперцентоптимал</strong></p></td>
<td><p>десятичное число (5; 2)</p></td>
<td></td>
<td><p>Значение по умолчанию — 5,00.</p></td>
</tr>
<tr class="odd">
<td><p><strong>динамиккапабилитиперцентакцептабле</strong></p></td>
<td><p>десятичное число (5; 2)</p></td>
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

