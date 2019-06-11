---
title: 'Lync Server 2013: список таблиц сервера сохраняемого чата'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: List of Persistent Chat Server tables
ms:assetid: 26c9e271-3516-4d90-b930-70fec4e359ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558628(v=OCS.15)
ms:contentKeyID: 48183659
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4d5c16160d51373fe1eef5b7cbaefe728b904545
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833942"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="list-of-persistent-chat-server-tables-in-lync-server-2013"></a>Список таблиц сервера сохраняемого чата в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-06_

Схема базы данных сохраняемого чата состоит из следующих таблиц.

<div>

## <a name="active-directory-sync"></a>Синхронизация службы каталогов Active Directory


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Таблица</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-tbladcookie.md">tblADCookie в Lync Server 2013</a></p></td>
<td><p>В этой папке содержатся файлы cookie для синхронизации протокола Lightweight Directory Access. Каждая строка соответствует домену доменных служб Active Directory, в котором активный сервер чата отслеживает изменения. (В этой таблице представлены только те домены службы каталогов Active Directory, которые относятся к серверу сохраняемого чата.)</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblprincipalmemberdifference.md">tblPrincipalMemberDifference в Lync Server 2013</a></p></td>
<td><p>Содержит изменения членства в группах (добавленные и удаленные участники), которые еще не были обработаны с помощью последующих шагов синхронизации Active Directory и являются одной из временных таблиц (вместе с таблицей Тбладупдатес), которая используется на первом этапе синхронизации Active Directory.</p>
<p>Изменения в членстве сохраняются, обрабатываются или отображаются только для групп, указанных в таблице ТблпринЦипал или уже содержащихся в них участников.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tbladupdates.md">tblADUpdates в Lync Server 2013</a></p></td>
<td><p>Содержит изменения, внесенные в доменные службы Active Directory, которые еще не обрабатывались с помощью последующих шагов синхронизации Active Directory, и являются одной из временных таблиц (вместе с таблицей ТблпринЦипалмембердифференце), которая используется на первом этапе службы каталогов Active Directory. Идет.</p>
<p>Изменения, вносимые в Active Directory, сохраняются, обрабатываются или обе будут только для участников, которые уже указаны в таблице ТблпринЦипал.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblprincipalmembers.md">tblPrincipalMembers в Lync Server 2013</a></p></td>
<td><p>Сведения о членстве участников.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblprincipalmeta.md">tblPrincipalMeta в Lync Server 2013</a></p></td>
<td><p>Содержит участников, которые необходимо обновлять из службы каталогов Active Directory.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblskippedaffiliations.md">tblSkippedAffiliations в Lync Server 2013</a></p></td>
<td><p>Содержат назначения, которые не удалось обновить по некоторым причинам, обычно из-за ошибок доступа в службе каталогов Active Directory.</p>
<p>Эта таблица предназначена исключительно для информационных целей. Его содержимое не используется.</p>
<p>Участники с назначением, которые не удалось обновить надлежащим образом, хранятся в таблице ТблпринЦипалмета и получают другой шанс на обновление.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="principals-affiliations-nodes-scopes-and-roles"></a>Участники, принадлежности, узлы, области и роли


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Таблица</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-tblprincipaltype.md">tblPrincipalType в Lync Server 2013</a></p></td>
<td><p>Содержит типы принципалов для классификации содержимого в таблице ТблпринЦипал. Эта таблица является статичной. Он настроен во время создания базы данных и не меняется.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblprincipal.md">tblPrincipal в Lync Server 2013</a></p></td>
<td><p>Содержат все участники (пользователи, папки, группы и т. д.). Сервер сохраняемого чата обрабатывает его как плоский разнородный список. Различные столбцы основываются на типе каждого участника.</p>
<p>Большинство из этих участников кэшируют копии объектов, которые хранятся в Active Directory. Создание кэшированной копии в основной таблице этих объектов Active Directory называется <em>Подготовка</em>.</p>
<p>Некоторые принципалы создаются более агрессивно, чем другие, а некоторые объекты Active Directory пропускаются полностью.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblprincipalaffiliations.md">tblPrincipalAffiliations в Lync Server 2013</a></p></td>
<td><p>Содержат основные принадлежности, описывающие участие в группах безопасности Active Directory, контейнерах Active Directory и т. д.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblnode.md">tblNode в Lync Server 2013</a></p></td>
<td><p>Раздел "Категория", управляемый на панели управления Lync Server.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblroletype.md">tblRoleType в Lync Server 2013</a></p></td>
<td><p>Содержат типы ролей и связанные с ними наборы разрешений. Эта таблица подстановки является статичной.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblscopeprincipal.md">tblScopePrincipal в Lync Server 2013</a></p></td>
<td><p>Содержат области, назначенные узлам.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblprincipalrole.md">tblPrincipalRole в Lync Server 2013</a></p></td>
<td><p>Содержат роли, назначенные узлам.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblsiopwhitelist.md">tblSiopWhiteList в Lync Server 2013</a></p></td>
<td><p>Содержат зарегистрированные надстройки, которые можно связать с узлами.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblenumattribute.md">tblEnumAttribute в Lync Server 2013</a></p></td>
<td><p>Содержат только закодированные &quot;атрибуты&quot; видимости &quot;и&quot; поведения, используемые в таблице тблноде.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblenumvalue.md">tblEnumValue в Lync Server 2013</a></p></td>
<td><p>Содержат значения &quot;атрибутов поведения&quot; "и", которые используются в таблице тблноде.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="invites-chats-and-other-client-support"></a>Приглашения, разговоры и другие службы поддержки клиентов


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Таблица</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-tblprincipalinvites.md">tblPrincipalInvites в Lync Server 2013</a></p></td>
<td><p>Содержат приглашения для всех подготовленных пользователей в системе для всех узлов с включенным параметром "автоматическое приглашение".</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblchat.md">tblChat в Lync Server 2013</a></p></td>
<td><p>Содержат все сообщения чата.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tbllastinviteid.md">tblLastInviteId в Lync Server 2013</a></p></td>
<td><p>Содержащий идентификатор последнего приглашения, который был создан (и использован в таблице ТблпринЦипалинвитес) для каждого пользователя.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tbllastchatid.md">tblLastChatId в Lync Server 2013</a></p></td>
<td><p>Содержащий последний идентификатор чата, который был создан (и использован в таблице Тблчат) для каждого пользователя.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblpreference.md">tblPreference в Lync Server 2013</a></p></td>
<td><p>Содержат пользовательские настройки клиента (используется только устаревшими клиентами).</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblfiletoken.md">tblFileToken в Lync Server 2013</a></p></td>
<td><p>Содержат временные маркеры для целей передачи файлов. Каждый раз, когда файл отправляется или загружается, служба сохраняемого чата создает маркер, который используется клиентом для доступа к хранилищу файлов веб-служб.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="server-support"></a>Поддержка сервера


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Таблица</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-tblserveridentity.md">tblServerIdentity в Lync Server 2013</a></p></td>
<td><p>Включает активные серверы в пуле сервера сохраняемого чата.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tbladminlock.md">tblAdminLock в Lync Server 2013</a></p></td>
<td><p>Включает блокировку администратора для выполнения некоторых команд администратора. При каждом выпуске блокировки в таблице Тблсистемревисион увеличивается запись о редакции системы.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblsystemrevision.md">tblSystemRevision в Lync Server 2013</a></p></td>
<td><p>Включает номер редакции (вместе с таблицей Тбладминлокк) для достижения согласованности на нескольких серверах.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblactivepeers.md">tblActivePeers в Lync Server 2013</a></p></td>
<td><p>В этом поле содержатся текущие одноранговые соединения между службами сохраняемого чата.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblconfig.md">tblConfig в Lync Server 2013</a></p></td>
<td><p>Неподдерживаемая конфигурация сервера сохраняемого чата.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

