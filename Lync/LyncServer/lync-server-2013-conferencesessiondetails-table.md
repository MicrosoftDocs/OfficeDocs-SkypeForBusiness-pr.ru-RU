---
title: 'Lync Server 2013: таблица таблица conferencesessiondetails'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ConferenceSessionDetails table
ms:assetid: 9eae6a54-69fd-4966-aa17-7ecee1297ad8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412741(v=OCS.15)
ms:contentKeyID: 48184925
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f7f0907b6c92d3ca5ed1adf7f1a991242d6ddeb1
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140572"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conferencesessiondetails-table-in-lync-server-2013"></a>Таблица Таблица conferencesessiondetails в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-28_

Каждая запись представляет один сеанс конференц-связи, который может быть либо сеансом с центром конференций, либо сеансом с конкретным сервером конференций.


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
<td><p>Отличным</p></td>
<td><p>Первичный, внешний</p></td>
<td><p>Время запроса сеанса; используется вместе с <strong>SessionIdSeq</strong> для уникальной идентификации сеанса конференц-связи. Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>сессионидсек</strong></p></td>
<td><p>int</p></td>
<td><p>Основной, внешний</p></td>
<td><p>Идентификатор сеанса. Используется совместно с <strong>сессионидтиме</strong> для уникальной идентификации сеанса конференц-связи. Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> . *</p></td>
</tr>
<tr class="odd">
<td><p><strong>конференцеуриид</strong></p></td>
<td><p>int</p></td>
<td><p>Правительства</p></td>
<td><p>URI конференции с центром конференций, связанной с этим сеансом. Дополнительные сведения см. <a href="lync-server-2013-conferenceuris-table.md">в таблице таблица conferenceuris в Lync Server 2013</a> . Это URI конференции на основе центра конференций.</p></td>
</tr>
<tr class="even">
<td><p><strong>конфинстанце</strong></p></td>
<td><p>Идентификатора</p></td>
<td></td>
<td><p>Идентификатор, который различается для экземпляров повторяющихся конференций. Каждый повторяющийся экземпляр конференции имеет один и тот же ConferenceURI, но разное значение ConfInstance.</p>
<p>Это поле было введено в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>мкуконференцеуриид</strong></p></td>
<td><p>int</p></td>
<td><p>Правительства</p></td>
<td><p>URI конференции с сервером конференций, относящейся к этому сеансу. Дополнительные сведения см. <a href="lync-server-2013-conferenceuris-table.md">в таблице таблица conferenceuris в Lync Server 2013</a> . Это URI конференции на основе сервера конференций. Для сеансов конференц-связи с центром конференций этот столбец будет пустым.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserId</strong></p></td>
<td><p>int</p></td>
<td><p>Правительства</p></td>
<td><p>Идентификатор одного пользователя в этом сеансе конференц-связи. Дополнительные сведения см. <a href="lync-server-2013-users-table.md">в таблице "Пользователи" в Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>усерендпоинтид</strong></p></td>
<td><p>идентификатора</p></td>
<td></td>
<td><p>GUID для идентификации экземпляра конечной точки. Например, если один пользователь входит на разные компьютеры с одной и той же учетной записью, то все эти компьютеры будут иметь разные идентификаторы конечной точки.</p></td>
</tr>
<tr class="even">
<td><p><strong>онбехалфофид</strong></p></td>
<td><p>int</p></td>
<td><p>Правительства</p></td>
<td><p>Определяет идентификатор пользователя, которого представляет вызывающий абонент. Дополнительные сведения см. <a href="lync-server-2013-users-table.md">в таблице "Пользователи" в Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>реферредбид</strong></p></td>
<td><p>int</p></td>
<td><p>Правительства</p></td>
<td><p>Идентификатор пользователя, который ссылается на вызов. Дополнительные сведения см. <a href="lync-server-2013-users-table.md">в таблице "Пользователи" в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>усерклиентверсионид</strong></p></td>
<td><p>int</p></td>
<td><p>Правительства</p></td>
<td><p>Версия клиента, используемого пользователем конференц-связи. Дополнительные сведения см. <a href="lync-server-2013-clientversions-table.md">в таблице таблица clientversions в Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>конфклиентверсионид</strong></p></td>
<td><p>int</p></td>
<td><p>Правительства</p></td>
<td><p>Версия клиента, используемого сервером конференций. Дополнительные сведения см. <a href="lync-server-2013-clientversions-table.md">в таблице таблица clientversions в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>реплацедиалогидтиме</strong></p></td>
<td><p>datetime</p></td>
<td><p>Правительства</p></td>
<td><p>Идентификационный номер для определения диалога, замененного текущим сеансом. Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>реплацедиалогидсек</strong></p></td>
<td><p>int</p></td>
<td><p>Правительства</p></td>
<td><p>Идентификатор для идентификации сеанса. Используется в сочетании с <strong>ReplacesDialogIdTime</strong> для уникальной идентификации сеанса. Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>исстартедбиконфсервер</strong></p></td>
<td><p>Битовая</p></td>
<td></td>
<td><p>Показывает, был ли сеанс начат сервером конференций.</p></td>
</tr>
<tr class="odd">
<td><p><strong>исендедбиконфсервер</strong></p></td>
<td><p>Битовая</p></td>
<td></td>
<td><p>Показывает, был ли сеанс завершен сервером конференций.</p></td>
</tr>
<tr class="even">
<td><p><strong>исусеринтернал</strong></p></td>
<td><p>Битовая</p></td>
<td></td>
<td><p>Вошел ли пользователь из внутренней сети.</p></td>
</tr>
<tr class="odd">
<td><p><strong>респонсекоде</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Код SIP-ответа на приглашение в сеанс. Это поле обычно заполняется данными, генерируемыми из исходного сообщения INVITE в сеансе. Если сообщения INVITE нет, поле заполняется датой и временем первого релевантного SIP-сообщения (BYE, CANCEL, MESSAGE или INFO).</p></td>
</tr>
<tr class="even">
<td><p><strong>диагностиЦид</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Диагностический идентификатор, захваченный из заголовка SIP.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ServerId</strong></p></td>
<td><p>int</p></td>
<td><p>Правительства</p></td>
<td><p>Идентификатор сервера переднего плана, используемого для этого сеанса. Дополнительные сведения см. <a href="lync-server-2013-servers-table.md">в таблице Servers в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>пулид</strong></p></td>
<td><p>int</p></td>
<td><p>Правительства</p></td>
<td><p>Идентификатор пула, в котором был записан сеанс. Дополнительные сведения см. <a href="lync-server-2013-pools-table.md">в таблице Pools в Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>медиатионсерверид</strong></p></td>
<td><p>int</p></td>
<td><p>Правительства</p></td>
<td><p>Сервер-посредник, который использовался вызовом. Дополнительные сведения см. <a href="lync-server-2013-mediationservers-table.md">в таблице таблица mediationservers в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>гатевайид</strong></p></td>
<td><p>int</p></td>
<td><p>Правительства</p></td>
<td><p>Шлюз, который использовался вызовом. Более подробную информацию можно узнать <a href="lync-server-2013-gateways-table.md">в таблице шлюзы в Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>еджесерверид</strong></p></td>
<td><p>int</p></td>
<td><p>Правительства</p></td>
<td><p>Пограничный сервер, который использовался вызовом. Дополнительные сведения см. <a href="lync-server-2013-edgeservers-table.md">в таблице таблица edgeservers в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>ContentTypeId</strong></p></td>
<td><p>int</p></td>
<td><p>Правительства</p></td>
<td><p>Тип контента, используемый в сеансе. Для получения дополнительных сведений см <a href="lync-server-2013-contenttypes-table.md">таблицу ContentTypes в Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>инвитетиме</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>Время первого запроса INVITE. Это поле обычно заполняется данными, генерируемыми из исходного сообщения INVITE в сеансе. Если сообщения INVITE нет, поле заполняется датой и временем первого релевантного SIP-сообщения (BYE, CANCEL, MESSAGE или INFO).</p></td>
</tr>
<tr class="even">
<td><p><strong>респонсетиме</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>Время первого ответа SIP. Это поле обычно заполняется данными, генерируемыми из исходного сообщения INVITE в сеансе. Если сообщения INVITE нет, поле заполняется датой и временем первого релевантного SIP-сообщения (BYE, CANCEL, MESSAGE или INFO).</p></td>
</tr>
<tr class="odd">
<td><p><strong>сессионендтиме</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>Время окончания сеанса.</p></td>
</tr>
<tr class="even">
<td><p><strong>уритипеид</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Правительства</p></td>
<td><p>Содержит значение типа универсального кода ресурса (URI) MCU из <a href="lync-server-2013-uritypes-table.md">таблицы таблица uritypes в Lync Server 2013</a>. Это поле используется для повышения производительности запроса.</p>
<p>Это поле было введено в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>усерфлаг</strong></p></td>
<td><p>smallint</p></td>
<td></td>
<td><p>Набор битов, указывающий атрибуты пользователя. Перечисляются следующие определения атрибутов:</p>
<ul>
<li><p>интеграция со стационарным телефоном — 1</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>каллфлаг</strong></p></td>
<td><p>smallint</p></td>
<td></td>
<td><p>Набор битов, указывающий атрибуты вызова. Перечисляются следующие определения атрибутов:</p>
<ul>
<li><p>повторный сеанс — 1</p></li>
</ul></td>
</tr>
</tbody>
</table>


\*Для большинства сеансов Сессионидсек будет иметь значение 1. Если несколько сеансов начинаются в одно и то же время, для одного из них SessionIdSeq будет иметь значение 1, для другого — 2 и т. д.

</div>

<span> </span>

</div>

</div>

</div>

