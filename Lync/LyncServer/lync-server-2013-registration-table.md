---
title: 'Lync Server 2013: таблица Registration'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Registration table
ms:assetid: 05ff9dd3-1aaa-4af0-bd69-8789fb8eaeb3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398114(v=OCS.15)
ms:contentKeyID: 48183298
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dfee81d83fb58b2fbeccff68a672da47e6770bd6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823800"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="registration-table-in-lync-server-2013"></a>Таблица Registration в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-09-28_

Каждая запись представляет одно событие регистрации пользователя.


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
<td><p>Основной, внешний</p></td>
<td><p>Время запроса сеанса. Используется в сочетании с <strong>сессионидсек</strong> для уникальной идентификации сеанса. Дополнительные сведения приведены <a href="lync-server-2013-dialogs-table.md">в таблице диалоговые окна Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>Сессионидсек</strong></p></td>
<td><p>целое</p></td>
<td><p>Основной, внешний</p></td>
<td><p>ИДЕНТИФИКАЦИОНный номер для идентификации сеанса. Используется в сочетании с <strong>сессионидтиме</strong> для уникальной идентификации сеанса. Дополнительные сведения приведены <a href="lync-server-2013-dialogs-table.md">в таблице диалоговые окна Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>Идентификатора пользователя</strong></p></td>
<td><p>целое</p></td>
<td><p>Другом</p></td>
<td><p>Идентификатор пользователя. Дополнительные сведения <a href="lync-server-2013-users-table.md">можно найти в таблице Users (пользователи) в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>Ендпоинтид</strong></p></td>
<td><p>идентификатора</p></td>
<td></td>
<td><p>GUID для идентификации конечной точки регистрации. Обычно событие Register на том же компьютере того же пользователя будет иметь тот же идентификатор конечной точки. У разных компьютеров другой идентификатор конечной точки.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Ендпоинтера</strong></p></td>
<td><p>Идентификатора</p></td>
<td></td>
<td><p>Идентификатор, который используется для различения регистраций, включающих одного и того же пользователя и ту же конечную точку.</p>
<p>Это поле было введено в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>Клиентверсионид</strong></p></td>
<td><p>целое</p></td>
<td><p>Другом</p></td>
<td><p>Клиентская версия текущего пользователя. Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-clientversions-table.md">таблицей клиентверсионс в Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>Регистрарид</strong></p></td>
<td><p>целое</p></td>
<td><p>Другом</p></td>
<td><p>Идентификатор сервера регистратора, используемого для регистрации. Более подробную информацию вы видите <a href="lync-server-2013-servers-table.md">в таблице Servers (серверы) в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>Пулид</strong></p></td>
<td><p>целое</p></td>
<td><p>Другом</p></td>
<td><p>Идентификатор пула, в котором был собран сеанс. Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-pools-table.md">таблицей пулы в Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>Еджесерверид</strong></p></td>
<td><p>целое</p></td>
<td><p>Другом</p></td>
<td><p>Пограничный сервер, на котором проходит регистрация. Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-edgeservers-table.md">таблицей еджесерверс в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>Internal (внутренний)</strong></p></td>
<td><p>Разрядная версия</p></td>
<td></td>
<td><p>Вход пользователя из внутреннего режима или нет.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Исусерсервицеаваилабле</strong></p></td>
<td><p>бит</p></td>
<td></td>
<td><p>Доступен ли Усерсервице или нет.</p></td>
</tr>
<tr class="even">
<td><p><strong>Испримарирегистрар</strong></p></td>
<td><p>бит</p></td>
<td></td>
<td><p>Регистрация для основного регистратора или нет.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Испримарирегистрарцентрал</strong></p></td>
<td><p>бит</p></td>
<td></td>
<td><p>Указывает, зарегистрирован ли пользователь в работающем устройстве филиала.</p>
<p>Это поле было введено в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>Регистертиме</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>Время регистрации.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Дерегистертиме</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>Время отмены регистрации.</p></td>
</tr>
<tr class="even">
<td><p><strong>Респонсекоде</strong></p></td>
<td><p>целое</p></td>
<td></td>
<td><p>Код ответа на запрос на регистрацию.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ДиагностиЦид</strong></p></td>
<td><p>целое</p></td>
<td></td>
<td><p>Идентификатор диагностики запроса на регистрацию. Это означает, что тип данных диагностики.</p></td>
</tr>
<tr class="even">
<td><p><strong>Устройства</strong></p></td>
<td><p>целое</p></td>
<td><p>Другом</p></td>
<td><p>Устройство, от которого поступил запрос на регистрацию. Более подробную информацию вы видите в <a href="lync-server-2013-devices-table.md">таблице "устройства" в Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>Дерегистертипеид</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Другом</p></td>
<td><p>Причина отмены регистрации, например "пользователь инициировал", "регистрация просрочена", "клиент не проходит" и многое другое. Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-deregistertype-table.md">таблицей дерегистертипе в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>IPAddress</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td></td>
<td><p>IP-адрес конечной точки, зарегистрированной пользователем. Это может быть адрес IPv4 или IPv6.</p>
<p>Это поле было введено в Microsoft Lync Server 2013.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

