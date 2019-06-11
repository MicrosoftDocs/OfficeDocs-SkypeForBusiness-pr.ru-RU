---
title: 'Lync Server 2013: представление регистрации'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Registration view
ms:assetid: 8a42bc7d-3d4f-43c1-9e15-89b2ee419ade
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688120(v=OCS.15)
ms:contentKeyID: 49733718
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fe1b01b748204d3d4365b6f28ae4480d3632b35a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823828"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="registration-view-in-lync-server-2013"></a>Представление регистрации в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-01_

В представлении регистрация хранятся сведения о регистрации пользователей. Это представление было представлено в Lync Server 2013.


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
<td><p><strong>Регистертиме</strong></p></td>
<td><p>datetime</p></td>
<td><p>Время, когда была выполнена регистрация.</p></td>
</tr>
<tr class="even">
<td><p><strong>Усерури</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI пользователя, который зарегистрировался.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Усеруритипе</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Тип URI пользователя, который зарегистрировался. Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-uritypes-table.md">таблицей уритипес в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>Усертенант</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Клиент пользователя, который зарегистрировался. Дополнительные сведения приведены в <a href="lync-server-2013-tenants-table.md">таблице "клиенты" в Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>Ендпоинтид</strong></p></td>
<td><p>идентификатора</p></td>
<td><p>Уникальный идентификатор конечной точки пользователя, зарегистрированного в.</p></td>
</tr>
<tr class="even">
<td><p><strong>Ендпоинтера</strong></p></td>
<td><p>идентификатора</p></td>
<td><p>Уникальный идентификатор, который используется для различения регистраций, включающих одного и того же пользователя и ту же конечную точку.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeRegisterType</strong></p></td>
<td><p>datetime</p></td>
<td><p>Время, когда была произведена отмена регистрации.</p></td>
</tr>
<tr class="even">
<td><p><strong>Дерегистерреасон</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Причина отмены регистрации.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Клиентверсион</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Версия клиента, используемая пользователем, который зарегистрировался.</p></td>
</tr>
<tr class="even">
<td><p><strong>Клиенттипе</strong></p></td>
<td><p>целое</p></td>
<td><p>Клиент, используемый зарегистрированным пользователем. Дополнительные сведения вы увидите <a href="lync-server-2013-useragentdef-table.md">в таблице усеражентдеф в Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>Клиенткатегори</strong></p></td>
<td><p>nvarchar (64)</p></td>
<td><p>Категория клиента, используемая пользователем, который зарегистрировался.</p></td>
</tr>
<tr class="even">
<td><p><strong>Следующий</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>IP-адрес, с которым пользователь зарегистрировался. Это может быть адрес IPv4 или IPv6.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Диалогид</strong></p></td>
<td><p>варстринг (775)</p></td>
<td><p>ИДЕНТИФИКАТОР диалогового окна SIP. Формат:</p>
<p>диалоговое окно; тег "from-Tag"</p></td>
</tr>
<tr class="even">
<td><p><strong>Респонсекоде</strong></p></td>
<td><p>целое</p></td>
<td><p>Код ответа SIP на приглашение на сеанс. Это поле обычно заполняется данными, созданными на основе исходного сообщения INVITE в сеансе. Если сообщение приглашения отсутствует, поле заполняется датой и временем первого соответствующего сообщения SIP (пока, CANCEL, MESSAGE или INFO).</p></td>
</tr>
<tr class="odd">
<td><p><strong>ДиагностиЦид</strong></p></td>
<td><p>целое</p></td>
<td><p>Идентификатор диагностики, полученный в заголовке SIP.</p></td>
</tr>
<tr class="even">
<td><p><strong>регистратор</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Полное доменное имя регистратора.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Pool</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Полное доменное имя пула, который захватывает данные для сеанса.</p></td>
</tr>
<tr class="even">
<td><p><strong>Пограничный сервер</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Полное доменное имя пограничного сервера, используемое пользователем, который зарегистрировался.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Internal (внутренний)</strong></p></td>
<td><p>бит</p></td>
<td><p>Указывает, вошел ли пользователь из внутренней сети.</p></td>
</tr>
<tr class="even">
<td><p><strong>Исусерсервицеаваилабле</strong></p></td>
<td><p>бит</p></td>
<td><p>Указывает, был ли Усерсервице доступен на момент регистрации.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Испримарирегистрар</strong></p></td>
<td><p>бит</p></td>
<td><p>Указывает, была ли регистрация основным регистратором.</p></td>
</tr>
<tr class="even">
<td><p><strong>Девицемакаддресс</strong></p></td>
<td><p>bigint</p></td>
<td><p>MAC-адрес устройства зарегистрирован.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Девицемануфактурер</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Производитель зарегистрированного устройства. Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-manufacturers-table.md">таблицей изготовителей в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>Девицехардвареверсион</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Аппаратная версия зарегистрированного устройства. Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-hardwareversions-table.md">таблицей хардвареверсионс в Lync Server 2013</a> .</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

