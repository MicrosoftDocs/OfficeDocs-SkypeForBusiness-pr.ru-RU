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
ms.openlocfilehash: 7609747848e1943a08eff2fa77b87f0168710f81
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744259"
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
<td><p><strong>ластлогинтиме</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>Время последнего входа пользователя в систему.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ластконфорганизедтиме</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>Последний раз, когда пользователь организует конференцию.</p></td>
</tr>
<tr class="even">
<td><p><strong>ласткаллорганизеркаллфаилуретиме</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>Последнее время, когда пользователь попытался вызвать сбой звонка.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ластконфорганизеркаллфаилуретиме</strong></p></td>
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

