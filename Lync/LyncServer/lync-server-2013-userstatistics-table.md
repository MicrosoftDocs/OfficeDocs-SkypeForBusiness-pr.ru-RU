---
title: 'Lync Server 2013: таблица Усерстатистикс'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: UserStatistics table
ms:assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721893(v=OCS.15)
ms:contentKeyID: 49733827
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2758b52b44a58095203deb7e70387934f723ee97
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140692"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="userstatistics-table-in-lync-server-2013"></a>Таблица Усерстатистикс в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-28_

Таблица UserStatistics предназначена для поддержки. Каждая запись в таблице содержит информацию об использовании системы отдельными пользователями. Эта таблица была введена в Microsoft Lync Server 2013.


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
<td><p><strong>UserId</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>Уникальный номер, идентифицирующий данного пользователя.</p></td>
</tr>
<tr class="even">
<td><p><strong>ластлогинтиме</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>Время последнего входа пользователя в систему.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ластконфорганизедтиме</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>Время последней конференции, организованной пользователем.</p></td>
</tr>
<tr class="even">
<td><p><strong>ласткаллорганизеркаллфаилуретиме</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>Время последнего сбоя вызова пользователя.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ластконфорганизеркаллфаилуретиме</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>Время последнего сбоя вызова, когда организатором конференции был данный пользователь.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

