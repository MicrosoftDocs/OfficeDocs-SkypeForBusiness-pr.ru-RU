---
title: 'Lync Server 2013: представление "Конференции"'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Conferences view
ms:assetid: c0e5c4db-c135-401f-9296-e9a49f6499a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721871(v=OCS.15)
ms:contentKeyID: 49733803
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 710aadb2770e9389d9e4becf206d68b8e8d815ee
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841486"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferences-view-in-lync-server-2013"></a>Представление "Конференции" в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-01_

В представлении "Конференции" хранятся сведения о конференциях. Это представление было представлено в Microsoft Lync Server 2013.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Столбец</th>
<th>Тип данных</th>
<th>Подробности</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Сессионидтиме</strong></p></td>
<td><p>datetime</p></td>
<td><p>Время запроса сеанса. Используется в сочетании с Сессионидсек для уникальной идентификации сеанса. Дополнительные сведения приведены <a href="lync-server-2013-dialogs-table.md">в таблице диалоговые окна Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>Сессионидсек</strong></p></td>
<td><p>целое</p></td>
<td><p>ИДЕНТИФИКАЦИОНный номер для идентификации сеанса. Используется в сочетании с Сессионидтиме для уникальной идентификации сеанса. Дополнительные сведения приведены <a href="lync-server-2013-dialogs-table.md">в таблице диалоговые окна Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>Универсальный код ресурса (URI) для Конференции.</p></td>
</tr>
<tr class="even">
<td><p><strong>Конференцеуритипе</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Тип URI конференции. Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-uritypes-table.md">таблицей уритипес в Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>Конфинстанце</strong></p></td>
<td><p>идентификатора</p></td>
<td><p>Используется для повторяющихся конференций. Каждый экземпляр повторяющейся Конференции имеет один и тот же Конференцеури, но другой Конфинстанце.</p></td>
</tr>
<tr class="even">
<td><p><strong>Конференцестарттиме</strong></p></td>
<td><p>datetime</p></td>
<td><p>Время начала Конференции.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Конференцеендтиме</strong></p></td>
<td><p>datetime</p></td>
<td><p>Время окончания Конференции.</p></td>
</tr>
<tr class="even">
<td><p><strong>Организерури</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>Универсальный код ресурса (URI) пользователя, который организовал конференцию.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Организертипе</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Тип URI пользователя, который организовал конференцию. Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-uritypes-table.md">таблицей уритипес в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>Организертенант</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Клиент пользователя, который организовал конференцию. Дополнительные сведения приведены в <a href="lync-server-2013-tenants-table.md">таблице "клиенты" в Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>Pool</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Полное доменное имя пула, на котором размещается конференция.</p></td>
</tr>
<tr class="even">
<td><p><strong>Пометка</strong></p></td>
<td><p>smallint</p></td>
<td><p>Битовая маска, которая включает атрибуты Конференции. Возможные значения</p>
<p>0X01 — искусственная транзакция</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

