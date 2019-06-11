---
title: 'Lync Server 2013: таблица ConferenceSessionDetails'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: ConferenceSessionDetails table
ms:assetid: 9eae6a54-69fd-4966-aa17-7ecee1297ad8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412741(v=OCS.15)
ms:contentKeyID: 48184925
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4c5aaa3ec022be18ad54cc8a24b8410c23faf799
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841495"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencesessiondetails-table-in-lync-server-2013"></a>Таблица ConferenceSessionDetails в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-09-28_

Каждая запись представляет один сеанс конференции, который может быть либо сеансом с фокусом, либо сеансом с определенным сервером конференц-связи.


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
<td><p>Датой</p></td>
<td><p>Основной, внешний</p></td>
<td><p>Время запроса сеанса; используется в сочетании с <strong>сессионидсек</strong> для уникальной идентификации сеанса конференц-связи. Дополнительные сведения приведены <a href="lync-server-2013-dialogs-table.md">в таблице диалоговые окна Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>Сессионидсек</strong></p></td>
<td><p>целое</p></td>
<td><p>Основной, внешний</p></td>
<td><p>ИДЕНТИФИКАЦИОНный номер для идентификации сеанса. Используется в сочетании с <strong>сессионидтиме</strong> для уникальной идентификации сеанса конференц-связи. Дополнительные сведения приведены <a href="lync-server-2013-dialogs-table.md">в таблице диалоговые окна Lync Server 2013</a> . *</p></td>
</tr>
<tr class="odd">
<td><p><strong>Конференцеуриид</strong></p></td>
<td><p>целое</p></td>
<td><p>Другом</p></td>
<td><p>КОД URI конференции Focus, связанный с этим сеансом. Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-conferenceuris-table.md">таблицей конференцеурис в Lync Server 2013</a> . Этот URI является универсальным кодом ресурса конференции на основе фокуса.</p></td>
</tr>
<tr class="even">
<td><p><strong>Конфинстанце</strong></p></td>
<td><p>Идентификатора</p></td>
<td></td>
<td><p>Идентификатор, отличающийся между экземплярами повторяющихся конференций. Каждый экземпляр повторяющейся Конференции имеет один и тот же Конференцеури, но другое значение Конфинстанце.</p>
<p>Это поле было введено в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Мкуконференцеуриид</strong></p></td>
<td><p>целое</p></td>
<td><p>Другом</p></td>
<td><p>URI конференции сервера конференций, связанный с этим сеансом. Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-conferenceuris-table.md">таблицей конференцеурис в Lync Server 2013</a> . Этот универсальный код ресурса (URI) Конференции на базе сервера конференций. Для сеансов опроса в фокусе этот столбец будет иметь значение null.</p></td>
</tr>
<tr class="even">
<td><p><strong>Идентификатора пользователя</strong></p></td>
<td><p>целое</p></td>
<td><p>Другом</p></td>
<td><p>ИДЕНТИФИКАТОР одного пользователя в сеансе Конференции. Дополнительные сведения <a href="lync-server-2013-users-table.md">можно найти в таблице Users (пользователи) в Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>Усерендпоинтид</strong></p></td>
<td><p>идентификатора</p></td>
<td></td>
<td><p>GUID для идентификации экземпляра конечной точки. Например, если один пользователь входит в систему на разных компьютерах с одной и той же учетной записью, каждый из них будет иметь другой идентификатор конечной точки.</p></td>
</tr>
<tr class="even">
<td><p><strong>Онбехалфофид</strong></p></td>
<td><p>целое</p></td>
<td><p>Другом</p></td>
<td><p>Идентификатор пользователя, от имени которого вызывающим абонентом является. Дополнительные сведения <a href="lync-server-2013-users-table.md">можно найти в таблице Users (пользователи) в Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>Реферредбид</strong></p></td>
<td><p>целое</p></td>
<td><p>Другом</p></td>
<td><p>Идентификационный номер пользователя, на который ссылается вызов. Дополнительные сведения <a href="lync-server-2013-users-table.md">можно найти в таблице Users (пользователи) в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>Усерклиентверсионид</strong></p></td>
<td><p>целое</p></td>
<td><p>Другом</p></td>
<td><p>Версия клиента, используемая пользователем Конференции. Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-clientversions-table.md">таблицей клиентверсионс в Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>Конфклиентверсионид</strong></p></td>
<td><p>целое</p></td>
<td><p>Другом</p></td>
<td><p>Версия клиента, используемая сервером Конференции. Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-clientversions-table.md">таблицей клиентверсионс в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>Реплацедиалогидтиме</strong></p></td>
<td><p>datetime</p></td>
<td><p>Другом</p></td>
<td><p>ИДЕНТИФИКАЦИОНный номер, определяющий диалоговое окно, которое было заменено текущим сеансом. Дополнительные сведения приведены <a href="lync-server-2013-dialogs-table.md">в таблице диалоговые окна Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>Реплацедиалогидсек</strong></p></td>
<td><p>целое</p></td>
<td><p>Другом</p></td>
<td><p>ИДЕНТИФИКАЦИОНный номер для идентификации сеанса. Используется в сочетании с <strong>реплацесдиалогидтиме</strong> для уникальной идентификации сеанса, который заменяется этим сеансом. Дополнительные сведения приведены <a href="lync-server-2013-dialogs-table.md">в таблице диалоговые окна Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>Исстартедбиконфсервер</strong></p></td>
<td><p>бит</p></td>
<td></td>
<td><p>Указывает, был ли сеанс запущен сервером конференц-связи.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Исендедбиконфсервер</strong></p></td>
<td><p>бит</p></td>
<td></td>
<td><p>Указывает, завершился ли сеанс сервером конференций.</p></td>
</tr>
<tr class="even">
<td><p><strong>Исусеринтернал</strong></p></td>
<td><p>бит</p></td>
<td></td>
<td><p>Вход пользователя из внутреннего режима или нет.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Респонсекоде</strong></p></td>
<td><p>целое</p></td>
<td></td>
<td><p>Код ответа протокола запуска сеансов (SIP) в приглашение на сеанс. Это поле обычно заполняется данными, созданными на основе исходного сообщения INVITE в сеансе. Если сообщение приглашения отсутствует, поле заполняется датой и временем первого соответствующего сообщения SIP (пока, CANCEL, MESSAGE или INFO).</p></td>
</tr>
<tr class="even">
<td><p><strong>ДиагностиЦид</strong></p></td>
<td><p>целое</p></td>
<td></td>
<td><p>Идентификатор диагностики, полученный в заголовке SIP.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Серверид</strong></p></td>
<td><p>целое</p></td>
<td><p>Другом</p></td>
<td><p>Идентификатор сервера переднего плана, используемого для этого сеанса. Более подробную информацию вы видите <a href="lync-server-2013-servers-table.md">в таблице Servers (серверы) в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>Пулид</strong></p></td>
<td><p>целое</p></td>
<td><p>Другом</p></td>
<td><p>Идентификатор пула, в котором был собран сеанс. Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-pools-table.md">таблицей пулы в Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>Медиатионсерверид</strong></p></td>
<td><p>целое</p></td>
<td><p>Другом</p></td>
<td><p>Сервер, на котором используется этот звонок. Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-mediationservers-table.md">таблицей медиатионсерверс в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>Гатевайид</strong></p></td>
<td><p>целое</p></td>
<td><p>Другом</p></td>
<td><p>Шлюз, который использует этот звонок. Более подробную информацию вы увидите <a href="lync-server-2013-gateways-table.md">в таблице шлюзов в Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>Еджесерверид</strong></p></td>
<td><p>целое</p></td>
<td><p>Другом</p></td>
<td><p>Пограничный сервер, на котором используется звонок. Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-edgeservers-table.md">таблицей еджесерверс в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>Контенттипеид</strong></p></td>
<td><p>целое</p></td>
<td><p>Другом</p></td>
<td><p>Тип контента, используемый в сеансе. Дополнительные сведения приведены <a href="lync-server-2013-contenttypes-table.md">в таблице ContentTypes в Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>Инвитетиме</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>Время первого запроса приглашения. Это поле обычно заполняется данными, созданными на основе исходного сообщения INVITE в сеансе. Если сообщение приглашения отсутствует, поле заполняется датой и временем первого соответствующего сообщения SIP (пока, CANCEL, MESSAGE или INFO).</p></td>
</tr>
<tr class="even">
<td><p><strong>Респонсетиме</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>Время первого ответа SIP. Это поле обычно заполняется данными, созданными на основе исходного сообщения INVITE в сеансе. Если сообщение приглашения отсутствует, поле заполняется датой и временем первого соответствующего сообщения SIP (пока, CANCEL, MESSAGE или INFO).</p></td>
</tr>
<tr class="odd">
<td><p><strong>Сессионендтиме</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>Время завершения сеанса.</p></td>
</tr>
<tr class="even">
<td><p><strong>Уритипеид</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Другом</p></td>
<td><p>Имеет значение типа URI MCU из <a href="lync-server-2013-uritypes-table.md">таблицы уритипес в Lync Server 2013</a>. Это поле используется для повышения производительности запроса.</p>
<p>Это поле было введено в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Усерфлаг</strong></p></td>
<td><p>smallint</p></td>
<td></td>
<td><p>Битовый набор, обозначающий атрибуты пользователя. Следующие определения атрибутов перечислены ниже.</p>
<ul>
<li><p>Интеграция с настольным телефоном 1</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Каллфлаг</strong></p></td>
<td><p>smallint</p></td>
<td></td>
<td><p>Битовый набор, обозначающий атрибуты вызова. Следующие определения атрибутов перечислены ниже.</p>
<ul>
<li><p>Сеанс с повторной попыткой 1</p></li>
</ul></td>
</tr>
</tbody>
</table>


\*Для большинства сеансов для Сессионидсек будет задано значение 1. Если несколько сеансов начинаются в одно и то же время, Сессионидсек для одного из них будет равен 1, а для другого — 2 и т. д.

</div>

<span> </span>

</div>

</div>

</div>

