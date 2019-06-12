---
title: 'Lync Server 2013: таблица Усерстатистикс'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: UserStatistics table
ms:assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721893(v=OCS.15)
ms:contentKeyID: 49733827
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f0f684850625f61ca72bbcc9c4bc53b56fcc6b38
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849270"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="userstatistics-table-in-lync-server-2013"></a>Таблица Усерстатистикс в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-09-28_

Таблица Усерстатистикс является вспомогательной таблицей. Каждая запись в таблице содержит сведения об использовании системы конкретным пользователем. Эта таблица введена в Microsoft Lync Server 2013.


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
<th>Ключ/индекс</th>
<th>Сведения</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Идентификатора пользователя</strong></p></td>
<td><p>целое</p></td>
<td><p>Primary</p></td>
<td><p>Уникальный номер, идентифицирующий этого пользователя.</p></td>
</tr>
<tr class="even">
<td><p><strong>Ластлогинтиме</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>Время последнего входа пользователя в систему.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Ластконфорганизедтиме</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>Последний раз, когда пользователь организует конференцию.</p></td>
</tr>
<tr class="even">
<td><p><strong>Ласткаллорганизеркаллфаилуретиме</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>Последнее время, когда пользователь попытался вызвать сбой звонка.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Ластконфорганизеркаллфаилуретиме</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>Последний раз, когда пользователь попытался вызвать сбой в организаторе конференц-связи.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

