---
title: 'Lync Server 2013: представление регистрации'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Registration view
ms:assetid: 8a42bc7d-3d4f-43c1-9e15-89b2ee419ade
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688120(v=OCS.15)
ms:contentKeyID: 49733718
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cdf0e0edd69685af866905fea08144de327c446c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536586"
---
# <a name="registration-view-in-lync-server-2013"></a>Представление регистрации в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-01_

В представлении Registration хранится информация о регистрации пользователей. Это представление было представлено в Lync Server 2013.


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
<td><p><strong>регистертиме</strong></p></td>
<td><p>datetime</p></td>
<td><p>Время регистрации.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI зарегистрировавшегося пользователя.</p></td>
</tr>
<tr class="odd">
<td><p><strong>усеруритипе</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Тип URI зарегистрировавшегося пользователя. Дополнительные сведения см. <a href="lync-server-2013-uritypes-table.md">в таблице таблица uritypes в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>усертенант</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Клиент зарегистрировавшегося пользователя. Дополнительные сведения см. <a href="lync-server-2013-tenants-table.md">в таблице клиентов в Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>ендпоинтид</strong></p></td>
<td><p>идентификатора</p></td>
<td><p>Уникальный идентификатор конечной точки зарегистрировавшегося пользователя.</p></td>
</tr>
<tr class="even">
<td><p><strong>ендпоинтера</strong></p></td>
<td><p>идентификатора</p></td>
<td><p>Уникальный идентификатор для различия регистраций с одним пользователем и одной конечной точкой.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeRegisterType</strong></p></td>
<td><p>datetime</p></td>
<td><p>Время отмены регистрации.</p></td>
</tr>
<tr class="even">
<td><p><strong>дерегистерреасон</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Причина отмены регистрации.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClientVersion</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Версия клиента зарегистрировавшегося пользователя.</p></td>
</tr>
<tr class="even">
<td><p><strong>ClientType</strong></p></td>
<td><p>int</p></td>
<td><p>Версия клиента зарегистрировавшегося пользователя. Дополнительные сведения приведены <a href="lync-server-2013-useragentdef-table.md">в таблице таблица useragentdef в Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>клиенткатегори</strong></p></td>
<td><p>nvarchar (64)</p></td>
<td><p>Категория клиента зарегистрировавшегося пользователя.</p></td>
</tr>
<tr class="even">
<td><p><strong>Адреса</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>IP-адрес зарегистрировавшегося пользователя. Это может быть IPv4- или IPv6-адрес.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DialogId</strong></p></td>
<td><p>варстринг (775)</p></td>
<td><p>Код диалога SIP. Формат:</p>
<p>диалоговое окно; from — Tag; to – Tag</p></td>
</tr>
<tr class="even">
<td><p><strong>ResponseCode</strong></p></td>
<td><p>int</p></td>
<td><p>Код SIP-ответа на приглашение в сеанс. Это поле обычно заполняется данными, генерируемыми из исходного сообщения INVITE в сеансе. Если сообщения INVITE нет, поле заполняется датой и временем первого релевантного SIP-сообщения (BYE, CANCEL, MESSAGE или INFO).</p></td>
</tr>
<tr class="odd">
<td><p><strong>диагностиЦид</strong></p></td>
<td><p>int</p></td>
<td><p>Код диагностики из заголовков SIP.</p></td>
</tr>
<tr class="even">
<td><p><strong>Регистратор</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Полное доменное имя регистратора.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Pool</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Полное доменное имя пула, который получил данные этого сеанса.</p></td>
</tr>
<tr class="even">
<td><p><strong>EdgeServer</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Полное доменное имя пограничного сервера зарегистрировавшегося пользователя.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsInternal</strong></p></td>
<td><p>Битовая</p></td>
<td><p>Показывает, зашел ли пользователь в систему из внутренней сети.</p></td>
</tr>
<tr class="even">
<td><p><strong>исусерсервицеаваилабле</strong></p></td>
<td><p>Битовая</p></td>
<td><p>Указывает, была ли служба UserService доступна во время регистрации.</p></td>
</tr>
<tr class="odd">
<td><p><strong>испримарирегистрар</strong></p></td>
<td><p>Битовая</p></td>
<td><p>Указывает, осуществлялась регистрация в основном регистраторе.</p></td>
</tr>
<tr class="even">
<td><p><strong>девицемакаддресс</strong></p></td>
<td><p>типу</p></td>
<td><p>MAC-адрес зарегистрировавшегося устройства.</p></td>
</tr>
<tr class="odd">
<td><p><strong>девицемануфактурер</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Производитель зарегистрировавшегося устройства. Для получения дополнительных сведений ознакомьтесь со статьей <a href="lync-server-2013-manufacturers-table.md">Таблица производители в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>девицехардвареверсион</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Версия оборудования зарегистрировавшегося устройства. Дополнительные сведения см. <a href="lync-server-2013-hardwareversions-table.md">в таблице таблица hardwareversions в Lync Server 2013</a> .</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

