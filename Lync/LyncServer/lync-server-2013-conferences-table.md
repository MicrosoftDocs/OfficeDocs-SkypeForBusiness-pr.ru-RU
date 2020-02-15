---
title: 'Lync Server 2013: таблица конференций'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conferences table
ms:assetid: c3da6271-b3c6-4898-894f-10456ec794d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412964(v=OCS.15)
ms:contentKeyID: 48185340
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 218879c8e2c64178fc140d46199529f86ec7dc31
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049060"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferences-table-in-lync-server-2013"></a>Таблица конференций в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-28_

Каждая запись в этой таблице содержит сведения о вызовах для одной конференции.


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
<td><p>Время, в течение которого запрос на конференцию был захвачен агентом CDR. Используется только в качестве первичного ключа для уникальной идентификации экземпляра Конференции.</p></td>
</tr>
<tr class="even">
<td><p><strong>сессионидсек</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>Идентификатор сеанса. Используется совместно с <strong>сессионидтиме</strong> для уникальной идентификации экземпляра Конференции. *</p></td>
</tr>
<tr class="odd">
<td><p><strong>конференцеуриид</strong></p></td>
<td><p>int</p></td>
<td><p>Правительства</p></td>
<td><p>URI конференции. Дополнительные сведения см. <a href="lync-server-2013-conferenceuris-table.md">в таблице таблица conferenceuris в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>конфинстанце</strong></p></td>
<td><p>идентификатора</p></td>
<td><p> </p></td>
<td><p>Полезен для повторяющихся конференций; Каждый экземпляр повторяющейся Конференции имеет один и тот же <strong>конференцеури</strong>, но у него будет другой <strong>конфинстанце</strong>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>конференцестарттиме</strong></p></td>
<td><p>datetime</p></td>
<td><p> </p></td>
<td><p>Время начала Конференции.</p></td>
</tr>
<tr class="even">
<td><p><strong>конференцеендтиме</strong></p></td>
<td><p>datetime</p></td>
<td><p> </p></td>
<td><p>Время начала Конференции.</p></td>
</tr>
<tr class="odd">
<td><p><strong>пулид</strong></p></td>
<td><p>int</p></td>
<td><p>Правительства</p></td>
<td><p>ИДЕНТИФИКАЦИОНный номер для идентификации пула, в котором была собрана конференция. Дополнительные сведения см. <a href="lync-server-2013-pools-table.md">в таблице Pools в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>организерид</strong></p></td>
<td><p>Целое</p></td>
<td><p>Правительства</p></td>
<td><p>ИДЕНТИФИКАЦИОНный номер для идентификации универсального кода ресурса (URI) организатора этой Конференции. Дополнительные сведения см. <a href="lync-server-2013-users-table.md">в таблице "Пользователи" в Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>Флаг</strong></p></td>
<td><p>smallint</p></td>
<td></td>
<td><p>Битовая маска, содержащая атрибуты Конференции. Возможные значения:</p>
<ul>
<li><p>0X01</p></li>
<li><p>Виртуальный</p></li>
<li><p>Транзакция</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Обработать</strong></p></td>
<td><p>Битовая</p></td>
<td></td>
<td><p>Внутреннее поле, используемое службой мониторинга.</p>
<p>Это поле было введено в Microsoft Lync Server 2013.</p></td>
</tr>
</tbody>
</table>


\*Для большинства сеансов Сессионидсек будет иметь значение 1. Если два сеанса начинаются в одно и то же время, то Сессионидсек для одного из них будет иметь значение 1, а другое — 2 и т. д.

</div>

<span> </span>

</div>

</div>

</div>

