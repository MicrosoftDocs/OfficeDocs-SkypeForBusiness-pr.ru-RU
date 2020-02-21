---
title: 'Lync Server 2013: таблица таблица videoclientevent'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: VideoClientEvent table
ms:assetid: e8ab963b-fe1d-45b3-b9bd-66a5f44c1629
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399039(v=OCS.15)
ms:contentKeyID: 48185891
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a687e503b9dfd02c296e1e96d88b93c716d7c54b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211635"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="videoclientevent-table-in-lync-server-2013"></a>Таблица Таблица videoclientevent в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-02_

Каждая запись содержит событие клиента для одной конечной точки в видеовызове. Как правило, один вызов состоит из двух записей, один для вызывающего абонента и один для вызываемого абонента.


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
<td><p><strong>конференцедатетиме</strong></p></td>
<td><p>datetime</p></td>
<td><p>Primary</p></td>
<td><p>Ссылка из <a href="lync-server-2013-medialine-table.md">таблицы MediaLine в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>сессионсек</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>Ссылка из <a href="lync-server-2013-medialine-table.md">таблицы MediaLine в Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>медиалинелабел</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Primary</p></td>
<td><p>Ссылка из <a href="lync-server-2013-medialine-table.md">таблицы MediaLine в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>фромкаллер</strong></p></td>
<td><p>Битовая</p></td>
<td><p>Primary</p></td>
<td><p>0: данные вызываемого абонента</p>
<p>1: данные вызывающего абонента</p></td>
</tr>
<tr class="odd">
<td><p><strong>нетворкбандвидсловевентратио</strong></p></td>
<td></td>
<td><p> </p></td>
<td><p>Процентное отношение сеанса событие Ловбандвидс было вызвано для состояния "плохое". Доступная полоса пропускания недостаточна для приемлемого голосового интерфейса.</p></td>
</tr>
<tr class="even">
<td><p><strong>нетворкрецеивекуалитевентратио</strong></p></td>
<td></td>
<td><p> </p></td>
<td><p>Процентное отношение сеанса событие Рецеивесендкуалити было вызвано для состояния "плохое".</p>
<p>Качество сети в терминах нарушения или потери пакетов является серьезным и влияет на качество получаемого звука.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

