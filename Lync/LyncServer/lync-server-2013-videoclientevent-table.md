---
title: 'Lync Server 2013: таблица VideoClientEvent'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: VideoClientEvent table
ms:assetid: e8ab963b-fe1d-45b3-b9bd-66a5f44c1629
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399039(v=OCS.15)
ms:contentKeyID: 48185891
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 79b428a639cee6fb0df04cc969b529c5bbbfb2c9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849178"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="videoclientevent-table-in-lync-server-2013"></a>Таблица VideoClientEvent в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-02_

Каждая запись имеет событие клиента для одной конечной точки во время видеозвонка. Обычно один звонок состоит из двух записей: одного для вызывающего и для вызываемого абонента.


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
<td><p><strong>Конференцедатетиме</strong></p></td>
<td><p>datetime</p></td>
<td><p>Primary</p></td>
<td><p>На которую ссылается <a href="lync-server-2013-medialine-table.md">Таблица медиалине в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>Сессионсек</strong></p></td>
<td><p>целое</p></td>
<td><p>Primary</p></td>
<td><p>На которую ссылается <a href="lync-server-2013-medialine-table.md">Таблица медиалине в Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Медиалинелабел</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Primary</p></td>
<td><p>На которую ссылается <a href="lync-server-2013-medialine-table.md">Таблица медиалине в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>Фромкаллер</strong></p></td>
<td><p>бит</p></td>
<td><p>Primary</p></td>
<td><p>0: данные вызывающего абонента</p>
<p>1: данные вызывающего абонента</p></td>
</tr>
<tr class="odd">
<td><p><strong>Нетворкбандвидсловевентратио</strong></p></td>
<td></td>
<td><p> </p></td>
<td><p>Процент сеанса, когда событие Ловбандвидс было инициировано для состояния "Bad". Доступная пропускная способность недостаточна для приемлемого голосового интерфейса.</p></td>
</tr>
<tr class="even">
<td><p><strong>Нетворкрецеивекуалитевентратио</strong></p></td>
<td></td>
<td><p> </p></td>
<td><p>Процент сеанса, когда событие Рецеивесендкуалити было инициировано для состояния "Bad".</p>
<p>Качество сети в условиях нарушения или потери пакетов является существенным и влияет на качество получаемого звука.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

