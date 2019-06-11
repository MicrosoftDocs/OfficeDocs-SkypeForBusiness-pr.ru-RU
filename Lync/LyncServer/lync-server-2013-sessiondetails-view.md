---
title: 'Lync Server 2013: представление Сессиондетаилс'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: SessionDetails view
ms:assetid: ea328c6f-cf22-48dd-8f7f-f1666c9148c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721924(v=OCS.15)
ms:contentKeyID: 49733859
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4bd3902fd35679366e905c04e99ff1e72b2ece86
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822092"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sessiondetails-view-in-lync-server-2013"></a>Сессиондетаилс представления в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-01_

В представлении Сессиондетаилс хранятся сведения о одноранговых сеансах, которые могут быть телефонным звонком VoIP-VoIP, сеансом обмена мгновенными сообщениями с двумя субъектами или сеансом другого типа. Это представление было представлено в Microsoft Lync Server 2013.


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
<td><p>Время запроса сеанса. Используется в сочетании с Сессионидсек для уникальной идентификации сеанса. Дополнительные сведения приведены <a href="lync-server-2013-dialogs-table.md">в таблице диалоговые окна в таблице Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>Сессионидсек</strong></p></td>
<td><p>целое</p></td>
<td><p>ИДЕНТИФИКАЦИОНный номер для идентификации сеанса. Используется в сочетании с Сессионидтиме для уникальной идентификации сеанса. Дополнительные сведения приведены <a href="lync-server-2013-dialogs-table.md">в таблице диалоговые окна Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>Инвитетиме</strong></p></td>
<td><p>datetime</p></td>
<td><p>Время первого запроса приглашения. Это поле обычно заполняется данными, созданными на основе исходного сообщения INVITE в сеансе. Если сообщение приглашения отсутствует, поле заполняется датой и временем первого соответствующего сообщения SIP (пока, CANCEL, MESSAGE или INFO). Это поле обычно заполняется данными, созданными на основе исходного сообщения INVITE в сеансе. Если сообщение приглашения отсутствует, поле заполняется датой и временем первого соответствующего сообщения SIP (пока, CANCEL, MESSAGE или INFO).</p></td>
</tr>
<tr class="even">
<td><p><strong>Фромури</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI пользователя, запустившего сеанс.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Таури</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>Универсальный код ресурса (URI) пользователя, который присоединился к сеансу.</p></td>
</tr>
<tr class="even">
<td><p><strong>Фромуритипе</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Тип URI пользователя, запустившего сеанс. Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-uritypes-table.md">таблицей уритипес в Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>Тауритипе</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Тип URI пользователя, который присоединился к сеансу. Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-uritypes-table.md">таблицей уритипес в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>Фромтенант</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>Клиент пользователя, который запустил сеанс. Дополнительные сведения приведены в <a href="lync-server-2013-tenants-table.md">таблице "клиенты" в Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>Тотенант</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Клиент пользователя, который присоединил сеанс. Дополнительные сведения приведены в <a href="lync-server-2013-tenants-table.md">таблице "клиенты" в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>Фромендпоинтид</strong></p></td>
<td><p>идентификатора</p></td>
<td><p>Уникальный идентификатор конечной точки пользователя, который запустил сеанс.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Тоендпоинтид</strong></p></td>
<td><p>идентификатора</p></td>
<td><p>Уникальный идентификатор конечной точки пользователя, который присоединился к сеансу.</p></td>
</tr>
<tr class="even">
<td><p><strong>EndTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Время окончания сеанса.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Фроммессажекаунт</strong></p></td>
<td><p>целое</p></td>
<td><p>Количество сообщений, отправленных пользователем, который запустил сеанс.</p></td>
</tr>
<tr class="even">
<td><p><strong>Томессажекаунт</strong></p></td>
<td><p>целое</p></td>
<td><p>Количество сообщений, отправленных пользователем, который присоединился к сеансу.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Фромклиентверсион</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Версия клиента, используемая пользователем, который запустил сеанс.</p></td>
</tr>
<tr class="even">
<td><p><strong>Фромклиенттипе</strong></p></td>
<td><p>целое</p></td>
<td><p>Клиент, используемый пользователем, который запустил сеанс. Дополнительные сведения вы увидите <a href="lync-server-2013-useragentdef-table.md">в таблице усеражентдеф в Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>Фромклиенткатегори</strong></p></td>
<td><p>nvarchar (64)</p></td>
<td><p>Имя категории клиента, используемой пользователем, который запустил сеанс.</p></td>
</tr>
<tr class="even">
<td><p><strong>Токлиентверсион</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Версия клиента, используемая пользователем, который присоединился к сеансу</p></td>
</tr>
<tr class="odd">
<td><p><strong>Токлиенттипе</strong></p></td>
<td><p>целое</p></td>
<td><p>Клиент, используемый пользователем, который присоединился к сеансу. Дополнительные сведения вы увидите <a href="lync-server-2013-useragentdef-table.md">в таблице усеражентдеф в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>Токлиенткатегори</strong></p></td>
<td><p>nvarchar (64)</p></td>
<td><p>Имя категории клиента, используемой пользователем, который присоединился к сеансу.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Таржетури</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>Универсальный код ресурса (URI) целевого пользователя сеанса.</p></td>
</tr>
<tr class="even">
<td><p><strong>Таржетуритипе</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>Тип универсального кода ресурса (URI) целевого пользователя для сеанса. Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-uritypes-table.md">таблицей уритипес в Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>Онбехалфофури</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>Универсальный код ресурса (URI) пользователя, от имени которого был запущен сеанс.</p></td>
</tr>
<tr class="even">
<td><p><strong>Онннбехалфофуритипе</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Тип универсального кода ресурса (URI) пользователя, от имени которого был запущен сеанс. Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-uritypes-table.md">таблицей уритипес в Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>Онбехалфофтенант</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Клиент пользователя, от имени которого был запущен сеанс. Дополнительные сведения приведены в <a href="lync-server-2013-tenants-table.md">таблице "клиенты" в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>Реферредбюри</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI пользователя, который ссылался на сеанс.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Реферредбюритипе</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Тип URI пользователя, который ссылался на сеанс. Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-uritypes-table.md">таблицей уритипес в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>Реферредбитенант</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Клиент пользователя, который ссылался на сеанс. Дополнительные сведения приведены в <a href="lync-server-2013-tenants-table.md">таблице "клиенты" в Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>Диалогид</strong></p></td>
<td><p>varchar (775)</p></td>
<td><p>ИДЕНТИФИКАТОР диалогового окна SIP. Формат:</p>
<p>диалоговое окно; тег "from-Tag"</p></td>
</tr>
<tr class="even">
<td><p><strong>Корреляци</strong></p></td>
<td><p>идентификатора</p></td>
<td><p>GUID, используемый для корреляции нескольких сеансов.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Реплацедиалогидтиме</strong></p></td>
<td><p>datetime</p></td>
<td><p>Время, когда диалоговое окно было заменено сеансом. Используется в сочетании с Реплацедиалогидсек для уникальной идентификации диалогового окна, которое заменяется сеансом. Дополнительные сведения приведены <a href="lync-server-2013-dialogs-table.md">в таблице диалоговые окна Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>Реплацедиалогидсек</strong></p></td>
<td><p>целое</p></td>
<td><p>ИДЕНТИФИКАЦИОНный номер для идентификации сеанса. Используется в сочетании с Реплацедиалогидтиме для уникальной идентификации диалогового окна, которое заменяется сеансом. Дополнительные сведения приведены <a href="lync-server-2013-dialogs-table.md">в таблице диалоговые окна Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>Реплацесдиалогид</strong></p></td>
<td><p>varchar (775)</p></td>
<td><p>ИДЕНТИФИКАТОР диалогового окна SIP, в котором будет заменяться сеанс. Формат:</p>
<p>диалоговое окно; тег "from-Tag"</p></td>
</tr>
<tr class="even">
<td><p><strong>Респонсетиме</strong></p></td>
<td><p>datetime</p></td>
<td><p>Время ответа на первое сообщение приглашения. Это поле обычно заполняется данными, созданными на основе исходного сообщения INVITE в сеансе. Если сообщение приглашения отсутствует, поле заполняется датой и временем первого соответствующего сообщения SIP (пока, CANCEL, MESSAGE или INFO).</p></td>
</tr>
<tr class="odd">
<td><p><strong>Респонсекоде</strong></p></td>
<td><p>целое</p></td>
<td><p>Код ответа SIP на приглашение на сеанс. Это поле обычно заполняется данными, созданными на основе исходного сообщения INVITE в сеансе. Если сообщение приглашения отсутствует, поле заполняется датой и временем первого соответствующего сообщения SIP (пока, CANCEL, MESSAGE или INFO).</p></td>
</tr>
<tr class="even">
<td><p><strong>ДиагностиЦид</strong></p></td>
<td><p>целое</p></td>
<td><p>Идентификатор диагностики, полученный из заголовков SIP.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Контента</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Тип контента для сеанса.</p></td>
</tr>
<tr class="even">
<td><p><strong>FrontEnd</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Полное доменное имя сервера переднего плана, который захватил данные для сеанса.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Pool</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Полное доменное имя пула, который захватывает данные для сеанса.</p></td>
</tr>
<tr class="even">
<td><p><strong>Фромеджесервер</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Полное доменное имя пограничного сервера, используемое пользователем, который запустил сеанс.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Тоеджесервер</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Полное доменное имя пограничного сервера, используемое пользователем, который запустил сеанс</p></td>
</tr>
<tr class="even">
<td><p><strong>Исфроминтернал</strong></p></td>
<td><p>бит</p></td>
<td><p>Указывает, вошел ли пользователь, запустивший сеанс, с помощью внутренней сети.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Истоинтернал</strong></p></td>
<td><p>бит</p></td>
<td><p>Указывает, вошел ли пользователь, который присоединился к сеансу, из внутренней сети.</p></td>
</tr>
<tr class="even">
<td><p><strong>Каллприорити</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Приоритет звонка для сеанса.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Фромусерфлаг</strong></p></td>
<td><p>smallint</p></td>
<td><p>Указывает атрибуты пользователя, который запустил сеанс. Допустимы следующие определения атрибутов:</p>
<p>0x01 — интеграция с настольным телефоном</p></td>
</tr>
<tr class="even">
<td><p><strong>Таусерфлаг</strong></p></td>
<td><p>smallint</p></td>
<td><p>Указывает атрибуты пользователя, который запустил сеанс. Допустимы следующие определения атрибутов:</p>
<p>0x01 — интеграция с настольным телефоном</p></td>
</tr>
<tr class="odd">
<td><p><strong>Каллфлаг</strong></p></td>
<td><p>smallint</p></td>
<td><p>Указывает атрибуты вызова. Допустимы следующие определения атрибутов:</p>
<p>0x01 — сеанс повторной попытки</p>
<p>0x02 — вызов, сделанный агентом от имени группы ответа</p></td>
</tr>
<tr class="even">
<td><p><strong>Расположение</strong></p></td>
<td><p>varchar (max)</p></td>
<td><p>Место вызова экстренной помощи.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

