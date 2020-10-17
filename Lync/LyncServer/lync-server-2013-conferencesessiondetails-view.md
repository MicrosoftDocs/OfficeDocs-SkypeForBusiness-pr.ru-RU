---
title: 'Lync Server 2013: представление Таблица conferencesessiondetails'
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
ms.openlocfilehash: cf8023408990b7f0243aaf0e937e2d1095dff0c2
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529186"
---
# <a name="conferencesessiondetails-view-in-lync-server-2013"></a>Представление Таблица conferencesessiondetails в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-11-12_

Представление ConferenceSessionDetails хранит сведения о многосторонних сеансах. Каждая запись представляет один сеанс конференц-связи, который может быть сеансом с фокусом или сеансом с определенным сервером конференц-связи. Это представление было представлено в Microsoft Lync Server 2013.


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
<th>Сведения</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>сессионидтиме</strong></p></td>
<td><p>datetime</p></td>
<td><p>Время запроса сеанса. Используется вместе с параметром SessionIdSeq для уникального определения сеанса. Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>сессионидсек</strong></p></td>
<td><p>int</p></td>
<td><p>Идентификационный номер для идентификации сеанса. Используется совместно с параметром SessionIdTime для уникальной идентификации сеанса. Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>инвитетиме</strong></p></td>
<td><p>datetime</p></td>
<td><p>Время первого запроса INVITE. Это поле обычно заполняется данными, генерируемыми из исходного сообщения INVITE в сеансе. При отсутствии сообщения INVITE поле заполняется датой и временем первого соответствующего сообщения SIP (BYE, CANCEL, MESSAGE или INFO).</p></td>
</tr>
<tr class="even">
<td><p><strong>конференцеури</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>Идентификатор URI конференции.</p></td>
</tr>
<tr class="odd">
<td><p><strong>конференцеуритипе</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Тип идентификатора URI конференции. Дополнительные сведения см. <a href="lync-server-2013-uritypes-table.md">в таблице таблица uritypes в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>конфинстанце</strong></p></td>
<td><p>идентификатора</p></td>
<td><p>Идентификатор, который разделяет экземпляры повторяющихся конференций. Каждый повторяющийся экземпляр конференции имеет один и тот же ConferenceURI, но разное значение ConfInstance.</p></td>
</tr>
<tr class="odd">
<td><p><strong>мкуконференцеури</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>Идентификатор URI сервера конференц-связи.</p></td>
</tr>
<tr class="even">
<td><p><strong>мкуконференцеуритипе</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Тип идентификатора URI сервера конференц-связи. Дополнительные сведения см. <a href="lync-server-2013-uritypes-table.md">в таблице таблица uritypes в Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI пользователя, участвующего в сеансе.</p></td>
</tr>
<tr class="even">
<td><p><strong>усеруритипе</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Тип URI пользователя, который являлся участником сеанса. Дополнительные сведения см. <a href="lync-server-2013-uritypes-table.md">в таблице таблица uritypes в Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>усертенант</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Клиент пользователя, который являлся участником сеанса. Дополнительные сведения см. <a href="lync-server-2013-tenants-table.md">в таблице клиентов в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>усерендпоинтид</strong></p></td>
<td><p>идентификатора</p></td>
<td><p>Уникальный идентификатор пользователя, который являлся участником сеанса.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EndTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Время окончания сеанса.</p></td>
</tr>
<tr class="even">
<td><p><strong>конференцеклиентверсион</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Версия сервера конференц-связи.</p></td>
</tr>
<tr class="odd">
<td><p><strong>конференцеклиенттипе</strong></p></td>
<td><p>int</p></td>
<td><p>Тип сервера конференц-связи. Дополнительные сведения см. <a href="lync-server-2013-useragentdef-table.md">в таблице таблица useragentdef в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>конференцекатегори</strong></p></td>
<td><p>nvarchar (64)</p></td>
<td><p>Категория сервера конференц-связи.</p></td>
</tr>
<tr class="odd">
<td><p><strong>усерклиентверсион</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Версия клиента, используемая пользователем, который являлся участником сеанса.</p></td>
</tr>
<tr class="even">
<td><p><strong>усерклиенттипе</strong></p></td>
<td><p>int</p></td>
<td><p>Клиент, использованный пользователем, который являлся участником сеанса. Дополнительные сведения приведены <a href="lync-server-2013-useragentdef-table.md">в таблице таблица useragentdef в Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>усерклиенткатегори</strong></p></td>
<td><p>nvarchar (64)</p></td>
<td><p>Название категории клиента, использованной пользователем, который являлся частью сеанса.</p></td>
</tr>
<tr class="even">
<td><p><strong>онбехалфофури</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI пользователя, от чьего имени был запущен сеанс.</p></td>
</tr>
<tr class="odd">
<td><p><strong>онбехалфофуритипе</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Тип URI пользователя, от имени которого был запущен сеанс. Дополнительные сведения см. <a href="lync-server-2013-uritypes-table.md">в таблице таблица uritypes в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>онбехалфофтенант</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Клиент пользователя, от имени которого был запущен сеанс. Дополнительные сведения см. <a href="lync-server-2013-tenants-table.md">в таблице клиентов в Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>реферредбюри</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI пользователя, который указал ссылку на сеанс.</p></td>
</tr>
<tr class="even">
<td><p><strong>реферредбюритипе</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Тип URI пользователя, который указал ссылку на сеанс. Дополнительные сведения см. <a href="lync-server-2013-uritypes-table.md">в таблице таблица uritypes в Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>реферредбюритенант</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Клиент пользователя, который указал ссылку на сеанс. Дополнительные сведения см. <a href="lync-server-2013-tenants-table.md">в таблице клиентов в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>DialogId</strong></p></td>
<td><p>варстринг (775)</p></td>
<td><p>ИД диалога SIP в следующем формате:</p>
<p>:d иалог; to – Tag</p></td>
</tr>
<tr class="odd">
<td><p><strong>реплацедиалогидтиме</strong></p></td>
<td><p>datetime</p></td>
<td><p>Идентификатор диалога, который был замещен текущим сеансом. Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>реплацедиалогидсек</strong></p></td>
<td><p>int</p></td>
<td><p>Идентификационный номер для идентификации сеанса. Используется совместно с параметром ReplaceDialogIdTime для уникальной идентификации сеанса, замененного данным сеансом. Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>реплацесдиалогид</strong></p></td>
<td><p>varchar (775)</p></td>
<td><p>Идентификатор диалога SIP, который был замещен этим сеансом. Используется следующий формат:</p>
<p>диалоговое окно; from — Tag; to – Tag</p></td>
</tr>
<tr class="even">
<td><p><strong>исстартедбиконфсервер</strong></p></td>
<td><p>Битовая</p></td>
<td><p>Указывает, был ли сеанс запущен сервером конференц-связи.</p></td>
</tr>
<tr class="odd">
<td><p><strong>исендедбиконфсервер</strong></p></td>
<td><p>Битовая</p></td>
<td><p>Указывает, был ли сеанс завершен сервером конференц-связи.</p></td>
</tr>
<tr class="even">
<td><p><strong>исусеринтернал</strong></p></td>
<td><p>Битовая</p></td>
<td><p>Показывает, зашел ли пользователь в систему из внутренней сети.</p></td>
</tr>
<tr class="odd">
<td><p><strong>респонсетиме</strong></p></td>
<td><p>datetime</p></td>
<td><p>Время ответа на первое сообщение INVITE. Обычно это поле содержит данные из первоначального сообщения INVITE в сеансе. Если сообщение INVITE отсутствует, в поле записывается дата и время первого соответствующего SIP-сообщения (BYE, CANCEL, MESSAGE или INFO).</p></td>
</tr>
<tr class="even">
<td><p><strong>ResponseCode</strong></p></td>
<td><p>int</p></td>
<td><p>Код SIP-ответа на приглашение в сеанс. Это поле обычно заполняется данными, генерируемыми из исходного сообщения INVITE в сеансе. Если сообщения INVITE нет, поле заполняется датой и временем первого релевантного SIP-сообщения (BYE, CANCEL, MESSAGE или INFO).</p></td>
</tr>
<tr class="odd">
<td><p><strong>диагностиЦид</strong></p></td>
<td><p>int</p></td>
<td><p>Диагностический идентификатор, взятый из SIP-заголовков сеанса.</p></td>
</tr>
<tr class="even">
<td><p><strong>ContentType</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Тип содержимого сеанса.</p></td>
</tr>
<tr class="odd">
<td><p><strong>FrontEnd</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Полное доменное имя интерфейсного сервера, который получил данные этого сеанса.</p></td>
</tr>
<tr class="even">
<td><p><strong>Pool</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Полное доменное имя пула, захватившего данные для сеанса.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediationServer</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Сервер-посредник, использованный пользователем, который являлся участником сеанса.</p></td>
</tr>
<tr class="even">
<td><p><strong>Шлюз</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Шлюз, использованный пользователем, который являлся участником сеанса.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EdgeServer</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Полное доменное имя пограничного сервера, используемого пользователем, который являлся участником сеанса.</p></td>
</tr>
<tr class="even">
<td><p><strong>усерфлаг</strong></p></td>
<td><p>smallint</p></td>
<td><p>Указывает атрибуты пользователя, который являлся участником сеанса. Разрешены следующие определения атрибутов.</p>
<p>0x01 — интеграция с настольным телефоном</p></td>
</tr>
<tr class="odd">
<td><p><strong>каллфлаг</strong></p></td>
<td><p>smallint</p></td>
<td><p>Указывает атрибуты вызова. Разрешены следующие определения атрибутов.</p>
<p>0x01 — списанный сеанс 0</p>
<p>x02 — вызов, выполненный агентом от имени группы ответа</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

