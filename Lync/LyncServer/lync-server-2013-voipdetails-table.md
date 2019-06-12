---
title: 'Lync Server 2013: таблица VoipDetails'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: VoipDetails table
ms:assetid: 74ffbb71-569b-4018-be1f-4db2bbafcf36
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398566(v=OCS.15)
ms:contentKeyID: 48184522
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7879f5dc7d5b884dfc2d3777ed4fa800978a3cff
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849073"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="voipdetails-table-in-lync-server-2013"></a>Таблица VoipDetails в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-09-28_

Каждая запись представляет вызов на стороне 1 2, в котором как минимум один пользователь является пользователем VoIP.


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
<td><p><strong>Сессионидтиме</strong></p></td>
<td><p>datetime</p></td>
<td><p>Primary</p></td>
<td><p>Время запроса сеанса. Используется в сочетании с <strong>сессионидсек</strong> для уникальной идентификации сеанса. Дополнительные сведения приведены <a href="lync-server-2013-dialogs-table.md">в таблице диалоговые окна Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>Сессионидсек</strong></p></td>
<td><p>целое</p></td>
<td><p>Primary</p></td>
<td><p>ИДЕНТИФИКАЦИОНный номер для идентификации сеанса. Используется в сочетании с <strong>сессионидтиме</strong> для уникальной идентификации сеанса. Дополнительные сведения приведены <a href="lync-server-2013-dialogs-table.md">в таблице диалоговые окна Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>Фромнумберид</strong></p></td>
<td><p>целое</p></td>
<td><p>Другом</p></td>
<td><p><strong>Фонеид</strong> вызывающего абонента. Для получения дополнительных сведений ознакомьтесь с таблицей " <a href="lync-server-2013-phones-table.md">телефоны" в Lync Server 2013</a> . Если NOT NULL и <strong>фромгатевайид</strong> не NULL, вызывающий абонент являлся пользователем КТСОП.</p></td>
</tr>
<tr class="even">
<td><p><strong>Коннектеднумберид</strong></p></td>
<td><p>целое</p></td>
<td><p>Другом</p></td>
<td><p><strong>Фонеид</strong> получателя звонка. Для получения дополнительных сведений ознакомьтесь с таблицей " <a href="lync-server-2013-phones-table.md">телефоны" в Lync Server 2013</a> . Если NOT NULL и <strong>тогатевайид</strong> не NULL, получатель звонка был пользователем КТСОП.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Фроммедиатионсерверид</strong></p></td>
<td><p>целое</p></td>
<td><p>Другом</p></td>
<td><p>Сервер, на котором поступил звонок. Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-mediationservers-table.md">таблицей медиатионсерверс в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>Томедиатионсерверид</strong></p></td>
<td><p>целое</p></td>
<td><p>Другом</p></td>
<td><p>Будет вызываем сервер для устранения проблем. Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-mediationservers-table.md">таблицей медиатионсерверс в Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>Фромгатевайид</strong></p></td>
<td><p>целое</p></td>
<td><p>Другом</p></td>
<td><p>Шлюз, из которого поступил звонок. Более подробную информацию вы увидите <a href="lync-server-2013-gateways-table.md">в таблице шлюзов в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>Тогатевайид</strong></p></td>
<td><p>целое</p></td>
<td><p>Другом</p></td>
<td><p>Шлюз, на который проходит звонок. Более подробную информацию вы увидите <a href="lync-server-2013-gateways-table.md">в таблице шлюзов в Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>Дисконнектедбюриид</strong></p></td>
<td><p>целое</p></td>
<td><p>Другом</p></td>
<td><p>Универсальный код ресурса (URI) пользователя, который отключил звонок, если пользователь имеет URI. Дополнительные сведения <a href="lync-server-2013-users-table.md">можно найти в таблице Users (пользователи) в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>Дисконнектедбифонеид</strong></p></td>
<td><p>целое</p></td>
<td><p>Другом</p></td>
<td><p>Идентификационный номер телефона, который отключил звонок, был отключен от телефона. Для получения дополнительных сведений ознакомьтесь с таблицей " <a href="lync-server-2013-phones-table.md">телефоны" в Lync Server 2013</a> .</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

