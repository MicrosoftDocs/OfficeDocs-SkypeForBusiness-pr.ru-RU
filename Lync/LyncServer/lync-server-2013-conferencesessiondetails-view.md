---
title: 'Lync Server 2013: представление Конференцесессиондетаилс'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ConferenceSessionDetails view
ms:assetid: 5858c84d-baed-421d-ad1d-3726e150e256
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688066(v=OCS.15)
ms:contentKeyID: 49733660
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 46356099c3eee20794a4198720597dc4395b563f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756393"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencesessiondetails-view-in-lync-server-2013"></a>Конференцесессиондетаилс представления в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-11-12_

В представлении Конференцесессиондетаилс хранятся сведения о многокомпонентных сеансах. Каждая запись представляет один сеанс конференции, который может быть либо сеансом с фокусом, либо сеансом с определенным сервером конференц-связи. Это представление было представлено в Microsoft Lync Server 2013.


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
<td><p><strong>сессионидтиме</strong></p></td>
<td><p>datetime</p></td>
<td><p>Время запроса сеанса. Используется в сочетании с Сессионидсек для уникальной идентификации сеанса. Дополнительные сведения приведены <a href="lync-server-2013-dialogs-table.md">в таблице диалоговые окна Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>сессионидсек</strong></p></td>
<td><p>целое</p></td>
<td><p>ИДЕНТИФИКАЦИОНный номер для идентификации сеанса. Используется в сочетании с Сессионидтиме для уникальной идентификации сеанса. Дополнительные сведения приведены <a href="lync-server-2013-dialogs-table.md">в таблице диалоговые окна Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>инвитетиме</strong></p></td>
<td><p>datetime</p></td>
<td><p>Время первого запроса приглашения. Это поле обычно заполняется данными, созданными на основе исходного сообщения INVITE в сеансе. Если сообщение приглашения отсутствует, поле заполняется датой и временем первого соответствующего сообщения SIP (пока, CANCEL, MESSAGE или INFO).</p></td>
</tr>
<tr class="even">
<td><p><strong>ConferenceUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>Универсальный код ресурса (URI) Конференции.</p></td>
</tr>
<tr class="odd">
<td><p><strong>конференцеуритипе</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Тип URI конференции. Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-uritypes-table.md">таблицей уритипес в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>конфинстанце</strong></p></td>
<td><p>идентификатора</p></td>
<td><p>Идентификатор, отличающийся между экземплярами повторяющихся конференций. Каждый экземпляр повторяющейся Конференции имеет один и тот же Конференцеури, но другое значение Конфинстанце.</p></td>
</tr>
<tr class="odd">
<td><p><strong>мкуконференцеури</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>Универсальный код ресурса (URI) сервера конференц-связи.</p></td>
</tr>
<tr class="even">
<td><p><strong>мкуконференцеуритипе</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Тип URI сервера конференц-связи. Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-uritypes-table.md">таблицей уритипес в Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>усерури</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>Универсальный код ресурса (URI) пользователя, участвующего в сеансе.</p></td>
</tr>
<tr class="even">
<td><p><strong>усеруритипе</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Тип URI пользователя, который является частью сеанса. Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-uritypes-table.md">таблицей уритипес в Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>усертенант</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Клиент пользователя, который является частью сеанса. Дополнительные сведения приведены в <a href="lync-server-2013-tenants-table.md">таблице "клиенты" в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>усерендпоинтид</strong></p></td>
<td><p>идентификатора</p></td>
<td><p>Уникальный идентификатор пользователя, который является частью сеанса.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EndTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Время окончания сеанса.</p></td>
</tr>
<tr class="even">
<td><p><strong>конференцеклиентверсион</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Версия сервера конференций.</p></td>
</tr>
<tr class="odd">
<td><p><strong>конференцеклиенттипе</strong></p></td>
<td><p>целое</p></td>
<td><p>Тип сервера конференций. Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-useragentdef-table.md">таблицей усеражентдеф в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>конференцекатегори</strong></p></td>
<td><p>nvarchar (64)</p></td>
<td><p>Категория "сервер конференции".</p></td>
</tr>
<tr class="odd">
<td><p><strong>усерклиентверсион</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Версия клиента, используемая пользователем, который принимал участие в сеансе.</p></td>
</tr>
<tr class="even">
<td><p><strong>усерклиенттипе</strong></p></td>
<td><p>целое</p></td>
<td><p>Клиент, используемый пользователем, который участвовал в сеансе. Дополнительные сведения вы увидите <a href="lync-server-2013-useragentdef-table.md">в таблице усеражентдеф в Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>усерклиенткатегори</strong></p></td>
<td><p>nvarchar (64)</p></td>
<td><p>Имя категории клиента, используемой пользователем, который является частью сеанса.</p></td>
</tr>
<tr class="even">
<td><p><strong>онбехалфофури</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>Универсальный код ресурса (URI) пользователя, от имени которого был запущен сеанс.</p></td>
</tr>
<tr class="odd">
<td><p><strong>онбехалфофуритипе</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Тип универсального кода ресурса (URI) пользователя, от имени которого был запущен сеанс. Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-uritypes-table.md">таблицей уритипес в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>онбехалфофтенант</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Клиент пользователя, от имени которого был запущен сеанс. Дополнительные сведения приведены в <a href="lync-server-2013-tenants-table.md">таблице "клиенты" в Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>реферредбюри</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI пользователя, который ссылался на сеанс.</p></td>
</tr>
<tr class="even">
<td><p><strong>реферредбюритипе</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Тип URI пользователя, который ссылался на сеанс. Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-uritypes-table.md">таблицей уритипес в Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>реферредбюритенант</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Клиент пользователя, который ссылался на сеанс. Дополнительные сведения приведены в <a href="lync-server-2013-tenants-table.md">таблице "клиенты" в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>диалогид</strong></p></td>
<td><p>варстринг (775)</p></td>
<td><p>ИДЕНТИФИКАТОР диалогового окна SIP. Формат</p>
<p>:d иалог; to-Tag</p></td>
</tr>
<tr class="odd">
<td><p><strong>реплацедиалогидтиме</strong></p></td>
<td><p>datetime</p></td>
<td><p>ИДЕНТИФИКАЦИОНный номер, определяющий диалоговое окно, которое было заменено текущим сеансом. Дополнительные сведения приведены <a href="lync-server-2013-dialogs-table.md">в таблице диалоговые окна Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>реплацедиалогидсек</strong></p></td>
<td><p>целое</p></td>
<td><p>ИДЕНТИФИКАЦИОНный номер для идентификации сеанса. Используется в сочетании с Реплацедиалогидтиме для уникальной идентификации сеанса, который заменяется этим сеансом. Дополнительные сведения приведены <a href="lync-server-2013-dialogs-table.md">в таблице диалоговые окна Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>реплацесдиалогид</strong></p></td>
<td><p>varchar (775)</p></td>
<td><p>ИДЕНТИФИКАТОР диалогового окна SIP, в котором будет заменяться сеанс. Формат:</p>
<p>диалоговое окно; тег "from-Tag"</p></td>
</tr>
<tr class="even">
<td><p><strong>исстартедбиконфсервер</strong></p></td>
<td><p>бит</p></td>
<td><p>Указывает, был ли запущен сервер конференц-связи.</p></td>
</tr>
<tr class="odd">
<td><p><strong>исендедбиконфсервер</strong></p></td>
<td><p>бит</p></td>
<td><p>Указывает, завершен ли сеанс на сервере конференций.</p></td>
</tr>
<tr class="even">
<td><p><strong>исусеринтернал</strong></p></td>
<td><p>бит</p></td>
<td><p>Указывает, вошел ли пользователь из внутренней сети.</p></td>
</tr>
<tr class="odd">
<td><p><strong>респонсетиме</strong></p></td>
<td><p>datetime</p></td>
<td><p>Время ответа на первое сообщение приглашения. Это поле обычно заполняется данными, созданными на основе исходного сообщения INVITE в сеансе. Если сообщение приглашения отсутствует, поле заполняется датой и временем первого соответствующего сообщения SIP (пока, CANCEL, MESSAGE или INFO).</p></td>
</tr>
<tr class="even">
<td><p><strong>респонсекоде</strong></p></td>
<td><p>целое</p></td>
<td><p>Код ответа SIP на приглашение на сеанс. Это поле обычно заполняется данными, созданными на основе исходного сообщения INVITE в сеансе. Если сообщение приглашения отсутствует, поле заполняется датой и временем первого соответствующего сообщения SIP (пока, CANCEL, MESSAGE или INFO).</p></td>
</tr>
<tr class="odd">
<td><p><strong>диагностиЦид</strong></p></td>
<td><p>целое</p></td>
<td><p>Идентификатор диагностики, полученный от заголовков SIP сеанса.</p></td>
</tr>
<tr class="even">
<td><p><strong>Контента</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Тип контента для сеанса.</p></td>
</tr>
<tr class="odd">
<td><p><strong>FrontEnd</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Полное доменное имя сервера переднего плана, который захватил данные для сеанса.</p></td>
</tr>
<tr class="even">
<td><p><strong>Pool</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Полное доменное имя пула, который захватывает данные для сеанса.</p></td>
</tr>
<tr class="odd">
<td><p><strong>медиатионсервер</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Сервер исправлений, используемый пользователем, который принимал участие в сеансе.</p></td>
</tr>
<tr class="even">
<td><p><strong>Шлюз</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Шлюз, используемый пользователем, который участвовал в сеансе.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Пограничный сервер</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Полное доменное имя пограничного сервера, используемое пользователем, который принимал участие в сеансе.</p></td>
</tr>
<tr class="even">
<td><p><strong>усерфлаг</strong></p></td>
<td><p>smallint</p></td>
<td><p>Указывает атрибуты пользователя, который принимал участие в сеансе. Допустимы следующие определения атрибутов:</p>
<p>0x01 — интеграция с настольным телефоном</p></td>
</tr>
<tr class="odd">
<td><p><strong>каллфлаг</strong></p></td>
<td><p>smallint</p></td>
<td><p>Указывает атрибуты вызова. Допустимы следующие определения атрибутов:</p>
<p>0x01 — повторное попыток Session0</p>
<p>x02 — вызов, сделанный агентом от имени группы ответа</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

