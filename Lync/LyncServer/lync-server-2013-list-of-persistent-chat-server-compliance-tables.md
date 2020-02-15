---
title: 'Lync Server 2013: список таблиц соответствия сервера сохраняемого чата'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: List of Persistent Chat Server compliance tables
ms:assetid: 8563446e-90cc-47cc-8a8e-4883decfe195
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215878(v=OCS.15)
ms:contentKeyID: 48706007
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fab78f554c94e11c808eeb28929d6b4511c3a695
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046132"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="list-of-persistent-chat-server-compliance-tables-in-lync-server-2013"></a>Список таблиц соответствия сервера сохраняемого чата в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-06_

Схема базы данных соответствия сохраняемого чата состоит из следующих таблиц.

<div>

## <a name="list-of-persistent-chat-server-compliance-tables"></a>Список таблиц соблюдения требований для сервера сохраняемого чата


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Table</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-tblcompliancedata.md">tblComplianceData в Lync Server 2013</a></p></td>
<td><p>Содержит события соответствия, которые еще не были обработаны настроенным адаптером.</p>
<p>В этой таблице содержатся события, связанные с сохраняемым разговором, такие как сообщения чата и загрузка файлов. (События, связанные с участниками, отслеживаются в таблице tblComplianceParticipant.)</p>
<p>(Серверы, которые обработали события, содержащиеся в этой таблице, приводятся в таблице tblComplianceFanout.)</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblcompliancefanout.md">tblComplianceFanout в Lync Server 2013</a></p></td>
<td><p>Содержит серверы, обработавшие события соответствия. Эта таблица тесно связана с таблицей tblComplianceData.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblcomplianceparticipant.md">ТблкомплианцепартиЦипант в Lync Server 2013</a></p></td>
<td><p>Содержит сведения о текущих участниках по службам чата и серверам. Он поддерживается на основе событий присоединения и соответствия частей, полученных от службы сохраняемого чата.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblcompliancestate.md">Тблкомплианцестате в Lync Server 2013</a></p></td>
<td><p>Содержит сведения о состоянии соответствия во всем пуле.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

