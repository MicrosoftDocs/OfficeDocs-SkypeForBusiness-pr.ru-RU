---
title: 'Lync Server 2013: таблица регистрации'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Registration table
ms:assetid: 05ff9dd3-1aaa-4af0-bd69-8789fb8eaeb3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398114(v=OCS.15)
ms:contentKeyID: 48183298
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d56f08db69fab4dfbf8da0c09d5d693bccf76bf2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152181"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="registration-table-in-lync-server-2013"></a>Таблица регистрации в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-28_

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
<th>Ключ или индекс</th>
<th>Сведения</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>сессионидтиме</strong></p></td>
<td><p>datetime</p></td>
<td><p>Основной, внешний</p></td>
<td><p>Время запроса сеанса. В сочетании с параметром <strong>SessionIdSeq</strong> определяет сеанс уникальным образом. Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>сессионидсек</strong></p></td>
<td><p>int</p></td>
<td><p>Первичный, внешний</p></td>
<td><p>Идентификатор для идентификации сеанса. В сочетании с параметром <strong>SessionIdTime</strong> определяет сеанс уникальным образом. Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserId</strong></p></td>
<td><p>int</p></td>
<td><p>Правительства</p></td>
<td><p>Идентификатор пользователя. Дополнительные сведения см. <a href="lync-server-2013-users-table.md">в таблице "Пользователи" в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>ендпоинтид</strong></p></td>
<td><p>идентификатора</p></td>
<td></td>
<td><p>GUID для идентификации конечной точки регистрации. Обычно события регистрации с одного и того же компьютера и одного и того же пользователя будут иметь одинаковый идентификатор конечной точки. Разные компьютеры имеют разные идентификаторы конечной точки.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ендпоинтера</strong></p></td>
<td><p>Идентификатора</p></td>
<td></td>
<td><p>Идентификатор, используемый, чтобы отличать друг от друга регистрации, в которых участвует один и тот же пользователь и одна и та же конечная точка.</p>
<p>Это поле было введено в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>клиентверсионид</strong></p></td>
<td><p>int</p></td>
<td><p>Правительства</p></td>
<td><p>Версия клиента текущего пользователя. Дополнительные сведения см. <a href="lync-server-2013-clientversions-table.md">в таблице таблица clientversions в Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>регистрарид</strong></p></td>
<td><p>int</p></td>
<td><p>Правительства</p></td>
<td><p>Идентификатор сервера регистратора, использовавшегося для регистрации. Дополнительные сведения см. <a href="lync-server-2013-servers-table.md">в таблице Servers в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>пулид</strong></p></td>
<td><p>int</p></td>
<td><p>Правительства</p></td>
<td><p>Идентификатор пула, в котором был записан сеанс. Дополнительные сведения см. <a href="lync-server-2013-pools-table.md">в таблице Pools в Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>еджесерверид</strong></p></td>
<td><p>int</p></td>
<td><p>Правительства</p></td>
<td><p>Пограничный сервер, через который проходила регистрация. Дополнительные сведения см. <a href="lync-server-2013-edgeservers-table.md">в таблице таблица edgeservers в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>IsInternal</strong></p></td>
<td><p>Битовая</p></td>
<td></td>
<td><p>Вошел ли пользователь из внутренней сети или нет.</p></td>
</tr>
<tr class="odd">
<td><p><strong>исусерсервицеаваилабле</strong></p></td>
<td><p>Битовая</p></td>
<td></td>
<td><p>Доступна ли служба UserService.</p></td>
</tr>
<tr class="even">
<td><p><strong>испримарирегистрар</strong></p></td>
<td><p>Битовая</p></td>
<td></td>
<td><p>Является ли регистратор основным.</p></td>
</tr>
<tr class="odd">
<td><p><strong>испримарирегистрарцентрал</strong></p></td>
<td><p>Битовая</p></td>
<td></td>
<td><p>Указывает, регистрировался ли пользователь с помощью устройства для обеспечения связи в филиалах.</p>
<p>Это поле было введено в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>регистертиме</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>Время регистрации.</p></td>
</tr>
<tr class="odd">
<td><p><strong>дерегистертиме</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>Время отмены регистрации.</p></td>
</tr>
<tr class="even">
<td><p><strong>респонсекоде</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Код ответа запроса регистрации.</p></td>
</tr>
<tr class="odd">
<td><p><strong>диагностиЦид</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Диагностический идентификатор запроса регистрации. Указывает тип диагностической информации.</p></td>
</tr>
<tr class="even">
<td><p><strong>Устройства</strong></p></td>
<td><p>int</p></td>
<td><p>Правительства</p></td>
<td><p>Устройство, с которого поступил запрос регистрации. Дополнительные сведения см. <a href="lync-server-2013-devices-table.md">в таблице Devices (устройства) в Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>дерегистертипеид</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Правительства</p></td>
<td><p>Причина отмены регистрации, такая как "user initiated" ("инициатива пользователя"), "registration expired" ("истек срок действия регистрации"), "client fail" ("сбой клиента") и др. Дополнительные сведения см. <a href="lync-server-2013-deregistertype-table.md">в таблице таблица deregistertype в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>Адреса</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td></td>
<td><p>IP-адрес конечной точки зарегистрировавшегося пользователя. Это может быть IPv4-адрес или IPv6-адрес.</p>
<p>Это поле было введено в Microsoft Lync Server 2013.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

