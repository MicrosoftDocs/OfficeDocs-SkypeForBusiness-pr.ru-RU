---
title: 'Lync Server 2013: таблица медиа'
description: 'Lync Server 2013: таблица медиа.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media table
ms:assetid: 1e1b427f-59b5-4564-bde5-1002a80439ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398268(v=OCS.15)
ms:contentKeyID: 48183568
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 31e30d1f91c59b8e3aa7915fc0d513618d0f709f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558035"
---
# <a name="media-table-in-lync-server-2013"></a>Таблица мультимедиа в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-28_

Каждая запись представляет один тип мультимедиа, используемый в одноранговом сеансе. Если бы использовалось более одного типа мультимедиа, один сеанс был бы представлен несколькими записями в таблице.

<div>


> [!NOTE]  
> Таблицу мультимедиа не следует использовать для вычисления длительности мультимедиа для сеанса. Эта таблица содержит сведения об обмене мультимедиа во время сеанса. Обмен мультимедиа осуществляется с помощью запроса INVITE, а время отправки этого  запроса указывается с помощью параметра StartTime. Время отправки запроса необязательно соответствует времени запуска обмена мультимедиа, который начинается только после приема сеанса вызываемым. EndTime обычно обозначает время завершения этого сеанса.



</div>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Столбец</th>
<th>Тип данных</th>
<th>Ключ или индекс</th>
<th>Сведения</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>сессионидтиме</strong></p></td>
<td><p>datetime</p></td>
<td><p>Основной, внешний</p></td>
<td><p>Время запроса сеанса. В сочетании с параметром <strong>SessionIdSeq</strong> определяет сеанс уникальным образом. Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>сессионидсек</strong></p></td>
<td><p>int</p></td>
<td><p>Основной, внешний</p></td>
<td><p>Идентификатор для идентификации сеанса. В сочетании с параметром <strong>SessionIdTime</strong> определяет сеанс уникальным образом. Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>медиаид</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Первичный, внешний</p></td>
<td><p>Уникальный номер, идентифицирующий этот тип мультимедиа. Дополнительные сведения см. <a href="lync-server-2013-medialist-table.md">в таблице таблица medialist в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>StartTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Primary</p></td>
<td><p>Время отправки запроса мультимедиа, а не фактическое время начала обмена мультимедиа. <strong>StartTime</strong> включает в себя время настройки сеанса.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EndTime</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>Время завершения этого сеанса.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

