---
title: 'Lync Server 2013: список таблиц соблюдения требований для сервера сохраняемого чата'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: List of Persistent Chat Server compliance tables
ms:assetid: 8563446e-90cc-47cc-8a8e-4883decfe195
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215878(v=OCS.15)
ms:contentKeyID: 48706007
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 31d3df9a0bfd5fa4b8b4acdda15ed86940c2572a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833939"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="list-of-persistent-chat-server-compliance-tables-in-lync-server-2013"></a>Список таблиц соблюдения требований для сервера сохраняемого чата в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-06_

Схема базы данных соответствия требованиям к сохраненным Чатам состоит из следующих таблиц.

<div>

## <a name="list-of-persistent-chat-server-compliance-tables"></a>Список таблиц соответствия требованиям сервера для работы с постоянной версией чата


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Таблица</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-tblcompliancedata.md">tblComplianceData в Lync Server 2013</a></p></td>
<td><p>Содержит события соответствия требованиям, которые еще не были обработаны настроенным адаптером.</p>
<p>В этой таблице содержатся сохраняемые события, связанные с чат, такие как сообщения чата и загружаемые файлы. (События участников отслеживаются таблицей ТблкомплианцепартиЦипант.)</p>
<p>(Серверы, обработавшие события в этой таблице, перечислены в таблице Тблкомплианцефанаут).</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblcompliancefanout.md">tblComplianceFanout в Lync Server 2013</a></p></td>
<td><p>Содержат серверы, которые обрабатывали событие соответствия требованиям. Эта таблица тесно связана с таблицей Тблкомплианцедата.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblcomplianceparticipant.md">tblComplianceParticipant в Lync Server 2013</a></p></td>
<td><p>Включает в себя текущих участников для каждой службы чата и для каждого сервера. Она поддерживается на основе событий присоединения и частей соответствия, полученных от службы сохраняемого чата.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblcompliancestate.md">tblComplianceState в Lync Server 2013</a></p></td>
<td><p>Сведения о состоянии соответствия требованиям всего пула.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

