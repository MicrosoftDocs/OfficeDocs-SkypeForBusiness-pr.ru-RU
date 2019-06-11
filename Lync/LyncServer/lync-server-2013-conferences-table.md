---
title: 'Lync Server 2013: таблица Conferences'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Conferences table
ms:assetid: c3da6271-b3c6-4898-894f-10456ec794d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412964(v=OCS.15)
ms:contentKeyID: 48185340
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 17cbadaf18fa36ca55f7755b5e679e564163a207
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841485"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferences-table-in-lync-server-2013"></a>Таблица Conferences в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-09-28_

Каждая запись в этой таблице включает сведения о звонках для одной конференции.


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
<td><p>Время, в течение которого запрос на конференцию был собран агентом CDR. Используется только в качестве первичного ключа для уникальной идентификации экземпляра Конференции.</p></td>
</tr>
<tr class="even">
<td><p><strong>Сессионидсек</strong></p></td>
<td><p>целое</p></td>
<td><p>Primary</p></td>
<td><p>ИДЕНТИФИКАЦИОНный номер для идентификации сеанса. Используется в сочетании с <strong>сессионидтиме</strong> для уникальной идентификации экземпляра Конференции. *</p></td>
</tr>
<tr class="odd">
<td><p><strong>Конференцеуриид</strong></p></td>
<td><p>целое</p></td>
<td><p>Другом</p></td>
<td><p>Универсальный код ресурса (URI) Конференции. Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-conferenceuris-table.md">таблицей конференцеурис в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>Конфинстанце</strong></p></td>
<td><p>идентификатора</p></td>
<td><p> </p></td>
<td><p>Полезен для повторяющихся конференций; Каждый экземпляр повторяющейся Конференции имеет один и тот же <strong>конференцеури</strong>, но у него будет другой <strong>конфинстанце</strong>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Конференцестарттиме</strong></p></td>
<td><p>datetime</p></td>
<td><p> </p></td>
<td><p>Время начала Конференции.</p></td>
</tr>
<tr class="even">
<td><p><strong>Конференцеендтиме</strong></p></td>
<td><p>datetime</p></td>
<td><p> </p></td>
<td><p>Время начала Конференции.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Пулид</strong></p></td>
<td><p>целое</p></td>
<td><p>Другом</p></td>
<td><p>ИДЕНТИФИКАЦИОНный номер для идентификации пула, в котором собрана конференция. Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-pools-table.md">таблицей пулы в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>Организерид</strong></p></td>
<td><p>Типом</p></td>
<td><p>Другом</p></td>
<td><p>ИДЕНТИФИКАЦИОНный номер для идентификации универсального кода ресурса (URI) организатора данной Конференции. Дополнительные сведения <a href="lync-server-2013-users-table.md">можно найти в таблице Users (пользователи) в Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>Пометка</strong></p></td>
<td><p>smallint</p></td>
<td></td>
<td><p>Битовая маска, которая включает атрибуты Конференции. Возможные значения</p>
<ul>
<li><p>0X01</p></li>
<li><p>Накопител</p></li>
<li><p>Транзакции</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Обработка</strong></p></td>
<td><p>бит</p></td>
<td></td>
<td><p>Внутреннее поле, используемое службой мониторинга.</p>
<p>Это поле было введено в Microsoft Lync Server 2013.</p></td>
</tr>
</tbody>
</table>


\*Для большинства сеансов для Сессионидсек будет задано значение 1. Если два сеанса начинаются в одно и то же время, Сессионидсек для одного из них будет равен 1, а для другого — 2 и т. д.

</div>

<span> </span>

</div>

</div>

</div>

