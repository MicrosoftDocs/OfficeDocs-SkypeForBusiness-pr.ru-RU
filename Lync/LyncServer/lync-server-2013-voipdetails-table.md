---
title: 'Lync Server 2013: таблица таблица voipdetails'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: VoipDetails table
ms:assetid: 74ffbb71-569b-4018-be1f-4db2bbafcf36
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398566(v=OCS.15)
ms:contentKeyID: 48184522
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 26feac5b9995aa1a8444029442adcb9c935083d3
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535416"
---
# <a name="voipdetails-table-in-lync-server-2013"></a>Таблица Таблица voipdetails в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-28_

Каждая запись представляет двусторонний звонок, по крайней мере один участник которого является пользователем VoIP.


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
<td><p>Primary</p></td>
<td><p>Время запроса сеанса. В сочетании с параметром <strong>SessionIdSeq</strong> определяет сеанс уникальным образом. Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>сессионидсек</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>Идентификатор сеанса. В сочетании с параметром <strong>SessionIdTime</strong> определяет сеанс уникальным образом. Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>фромнумберид</strong></p></td>
<td><p>int</p></td>
<td><p>Правительства</p></td>
<td><p>Идентификатор <strong>PhoneId</strong> звонящего. Дополнительные сведения см. <a href="lync-server-2013-phones-table.md">в таблице phones в Lync Server 2013</a> . Если значение этого параметра, а также параметра <strong>FromGatewayId</strong> отлично от NULL, звонящий являлся пользователем ТСОП.</p></td>
</tr>
<tr class="even">
<td><p><strong>коннектеднумберид</strong></p></td>
<td><p>int</p></td>
<td><p>Правительства</p></td>
<td><p>Идентификатор <strong>PhoneId</strong> получателя звонка. Дополнительные сведения см. <a href="lync-server-2013-phones-table.md">в таблице phones в Lync Server 2013</a> . Если значение этого параметра, а также параметра <strong>ToGatewayId</strong> отлично от NULL, получатель являлся пользователем ТСОП.</p></td>
</tr>
<tr class="odd">
<td><p><strong>фроммедиатионсерверид</strong></p></td>
<td><p>int</p></td>
<td><p>Правительства</p></td>
<td><p>Сервер-посредник, с которого поступил звонок. Дополнительные сведения см. <a href="lync-server-2013-mediationservers-table.md">в таблице таблица mediationservers в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>томедиатионсерверид</strong></p></td>
<td><p>int</p></td>
<td><p>Правительства</p></td>
<td><p>Сервер-посредник, на который направляется звонок. Дополнительные сведения см. <a href="lync-server-2013-mediationservers-table.md">в таблице таблица mediationservers в Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>фромгатевайид</strong></p></td>
<td><p>int</p></td>
<td><p>Правительства</p></td>
<td><p>Шлюз, из которого поступил звонок. Более подробную информацию можно узнать <a href="lync-server-2013-gateways-table.md">в таблице шлюзы в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>тогатевайид</strong></p></td>
<td><p>int</p></td>
<td><p>Правительства</p></td>
<td><p>Шлюз, на который направляется звонок. Более подробную информацию можно узнать <a href="lync-server-2013-gateways-table.md">в таблице шлюзы в Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>дисконнектедбюриид</strong></p></td>
<td><p>int</p></td>
<td><p>Правительства</p></td>
<td><p>Универсальный код ресурса (URI) пользователя, прервавшего звонок (если имеется). Дополнительные сведения см. <a href="lync-server-2013-users-table.md">в таблице "Пользователи" в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>дисконнектедбифонеид</strong></p></td>
<td><p>int</p></td>
<td><p>Правительства</p></td>
<td><p>ИД телефона, с которого был прерван звонок. Дополнительные сведения см. <a href="lync-server-2013-phones-table.md">в таблице phones в Lync Server 2013</a> .</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

