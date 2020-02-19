---
title: 'Lync Server 2013: список таблиц сервера сохраняемого чата'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: List of Persistent Chat Server tables
ms:assetid: 26c9e271-3516-4d90-b930-70fec4e359ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558628(v=OCS.15)
ms:contentKeyID: 48183659
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e6d9fe9db5ad22a0d6ad2d68d0afdbd5b0969608
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136416"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="list-of-persistent-chat-server-tables-in-lync-server-2013"></a>Список таблиц сервера сохраняемого чата в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-06_

Схема базы данных сохраняемого чата состоит из следующих таблиц.

<div>

## <a name="active-directory-sync"></a>Синхронизация Active Directory


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Table</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-tbladcookie.md">tblADCookie в Lync Server 2013</a></p></td>
<td><p>Содержит текущие файлы cookie синхронизации по протоколу LDAP. Каждая строка соответствует домену доменных служб Active Directory, который активно отслеживает изменения на сервере сохраняемого чата. В этой таблице представлены только те домены Active Directory, которые относятся к серверу сохраняемого чата.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblprincipalmemberdifference.md">tblPrincipalMemberDifference в Lync Server 2013</a></p></td>
<td><p>Содержит изменения членства в группах (добавленные и удаленные элементы), которые еще не были обработаны с помощью последующих шагов синхронизации Active Directory и являются одной из временных таблиц (вместе с таблицей Тбладупдатес), которая используется на первом этапе синхронизации Active Directory.</p>
<p>Изменения, внесенные в членство, хранятся и обрабатываются только для тех групп, которые перечислены в таблице tblPrincipal или члены которых содержатся в ней.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tbladupdates.md">Тбладупдатес в Lync Server 2013</a></p></td>
<td><p>Содержит изменения доменных служб Active Directory, которые еще не были обработаны с помощью последующих шагов синхронизации Active Directory и являются одной из временных таблиц (вместе с таблицей tblPrincipalMemberDifference), которая используется на первом шаге Active Directory Синхр.</p>
<p>Изменения в Active Directory сохраняются, обрабатываются или удаляются только для субъектов, которые уже указаны в таблице tblPrincipal.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblprincipalmembers.md">ТблпринЦипалмемберс в Lync Server 2013</a></p></td>
<td><p>Содержит сведения о членстве субъектов.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblprincipalmeta.md">tblPrincipalMeta в Lync Server 2013</a></p></td>
<td><p>Содержит субъекты, которые необходимо обновить из Active Directory.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblskippedaffiliations.md">tblSkippedAffiliations в Lync Server 2013</a></p></td>
<td><p>Содержит назначения, которые не удалось обновить по какой-либо причине, обычно из-за ошибок доступа к Active Directory.</p>
<p>Эта таблица служит только для информационных целей. Ее содержимое не используется.</p>
<p>Субъекты, назначения которых не удалось правильно обновить, сохраняются в таблице tblPrincipalMeta и могут быть обновлены еще раз.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="principals-affiliations-nodes-scopes-and-roles"></a>Субъекты, назначения, узлы, области действия и роли


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Table</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-tblprincipaltype.md">tblPrincipalType в Lync Server 2013</a></p></td>
<td><p>Содержит типы субъектов для разделения содержимого таблицы tblPrincipal на категории. Эта таблица является статической. Она настраивается при создании базы данных и больше не изменяется.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblprincipal.md">tblPrincipal в Lync Server 2013</a></p></td>
<td><p>Содержит все субъекты (пользователей, папки, группы и т. д.). Сервер сохраняемого чата обрабатывает его как плоский разнородный список. Каждый столбец соответствует типу субъекта.</p>
<p>Большая часть этих субъектов является кэшированными копиями объектов, хранящихся в Active Directory. Создание кэшированной копии в основной таблице этих объектов Active Directory обозначается как <em>Подготовка</em>.</p>
<p>Некоторые субъекты создаются более агрессивно, чем другие, и некоторые объекты Active Directory полностью игнорируются.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblprincipalaffiliations.md">ТблпринЦипалаффилиатионс в Lync Server 2013</a></p></td>
<td><p>Содержит основные принадлежности, описывающие членство в группах безопасности Active Directory, контейнерах Active Directory и т. д.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblnode.md">tblNode в Lync Server 2013</a></p></td>
<td><p>Содержит узел категории, управляемый в панели управления Lync Server.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblroletype.md">tblRoleType в Lync Server 2013</a></p></td>
<td><p>Содержит типы ролей и связанные с ними наборы разрешений. Эта таблица подстановки является статической.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblscopeprincipal.md">tblScopePrincipal в Lync Server 2013</a></p></td>
<td><p>Содержит области действия, назначенные узлам.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblprincipalrole.md">tblPrincipalRole в Lync Server 2013</a></p></td>
<td><p>Содержит роли, назначенные узлам.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblsiopwhitelist.md">tblSiopWhiteList в Lync Server 2013</a></p></td>
<td><p>Содержит зарегистрированные надстройки, которые можно связать с узлами.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblenumattribute.md">Тбленуматтрибуте в Lync Server 2013</a></p></td>
<td><p>Содержит только жестко &quot;запрограммированные атрибуты видимости&quot; и &quot;поведения&quot; , используемые в таблице tblNode.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblenumvalue.md">tblEnumValue в Lync Server 2013</a></p></td>
<td><p>Содержит значения атрибутов режима &quot;&quot; "и" для нежесткого отображения, которые используются в таблице tblNode.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="invites-chats-and-other-client-support"></a>Приглашения, чаты и другие поддерживаемые клиентом функции


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Table</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-tblprincipalinvites.md">tblPrincipalInvites в Lync Server 2013</a></p></td>
<td><p>Содержит приглашения для всех подготовленных пользователей в системе для всех узлов, для которых включено автоматическое приглашение.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblchat.md">tblChat в Lync Server 2013</a></p></td>
<td><p>Содержит все сообщения чата.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tbllastinviteid.md">tblLastInviteId в Lync Server 2013</a></p></td>
<td><p>Содержит последний созданный идентификатор приглашения (используемый в таблице tblPrincipalInvites) для каждого пользователя.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tbllastchatid.md">tblLastChatId в Lync Server 2013</a></p></td>
<td><p>Содержит последний созданный идентификатор чата (используемый в таблице tblChat) для каждого пользователя.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblpreference.md">Тблпреференце в Lync Server 2013</a></p></td>
<td><p>Содержит пользовательские настройки клиента (используется только для устаревших клиентов).</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblfiletoken.md">Тблфилетокен в Lync Server 2013</a></p></td>
<td><p>Содержит временные маркеры для передачи файлов. При каждом перезагрузке или загрузке файла служба сохраняемого чата создает маркер, который клиент использует для доступа к хранилищу файлов веб-служб.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="server-support"></a>Поддержка серверов


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Table</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-tblserveridentity.md">tblServerIdentity в Lync Server 2013</a></p></td>
<td><p>Содержит активные серверы в пуле серверов сохраняемого чата.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tbladminlock.md">tblAdminLock в Lync Server 2013</a></p></td>
<td><p>Содержит сведения о блокировке выполнения определенных команд администратором. Значение системного счетчика изменений в таблице tblSystemRevision увеличивается на единицу при каждом снятии блокировки.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblsystemrevision.md">Тблсистемревисион в Lync Server 2013</a></p></td>
<td><p>Содержит номер редакции, используемый для обеспечения  согласованности на нескольких серверах (наряду с таблицей tblAdminLock).</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblactivepeers.md">Тблактивепирс в Lync Server 2013</a></p></td>
<td><p>Содержит текущие одноранговые подключения между службами сохраняемого чата.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblconfig.md">tblConfig в Lync Server 2013</a></p></td>
<td><p>Содержит неподдерживаемую конфигурацию сервера сохраняемого чата.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

