---
title: 'Lync Server 2013: список таблиц сервера сохраняемого чата'
description: 'Lync Server 2013: список таблиц сервера сохраняемого чата.'
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
ms.openlocfilehash: 838e6d8f83b137923075851b29df4c602a487391
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550055"
---
# <a name="list-of-persistent-chat-server-tables-in-lync-server-2013"></a><span data-ttu-id="fdf19-103">Список таблиц сервера сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fdf19-103">List of Persistent Chat Server tables in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fdf19-104">_**Последнее изменение темы:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="fdf19-104">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="fdf19-105">Схема базы данных сохраняемого чата состоит из следующих таблиц.</span><span class="sxs-lookup"><span data-stu-id="fdf19-105">The Persistent Chat database schema consists of the following tables.</span></span>

<div>

## <a name="active-directory-sync"></a><span data-ttu-id="fdf19-106">Синхронизация Active Directory</span><span class="sxs-lookup"><span data-stu-id="fdf19-106">Active Directory Sync</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fdf19-107">Table</span><span class="sxs-lookup"><span data-stu-id="fdf19-107">Table</span></span></th>
<th><span data-ttu-id="fdf19-108">Описание</span><span class="sxs-lookup"><span data-stu-id="fdf19-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fdf19-109"><a href="lync-server-2013-tbladcookie.md">tblADCookie в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="fdf19-109"><a href="lync-server-2013-tbladcookie.md">tblADCookie in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="fdf19-110">Содержит текущие файлы cookie синхронизации по протоколу LDAP.</span><span class="sxs-lookup"><span data-stu-id="fdf19-110">Contains the current Lightweight Directory Access Protocol (LDAP) Sync cookies.</span></span> <span data-ttu-id="fdf19-111">Каждая строка соответствует домену доменных служб Active Directory, который активно отслеживает изменения на сервере сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="fdf19-111">Each row corresponds to an Active Directory Domain Services domain that Persistent Chat Server is actively monitoring for changes.</span></span> <span data-ttu-id="fdf19-112">В этой таблице представлены только те домены Active Directory, которые относятся к серверу сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="fdf19-112">(Only the Active Directory domains that are relevant for Persistent Chat Server are represented in this table.)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdf19-113"><a href="lync-server-2013-tblprincipalmemberdifference.md">tblPrincipalMemberDifference в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="fdf19-113"><a href="lync-server-2013-tblprincipalmemberdifference.md">tblPrincipalMemberDifference in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="fdf19-114">Содержит изменения членства в группах (добавленные и удаленные элементы), которые еще не были обработаны с помощью последующих шагов синхронизации Active Directory и являются одной из временных таблиц (вместе с таблицей Тбладупдатес), которая используется на первом этапе синхронизации Active Directory.</span><span class="sxs-lookup"><span data-stu-id="fdf19-114">Contains group membership changes (both added and removed members) that have not yet been processed by the later Active Directory Sync steps and is one of the temporary tables (along with tblADUpdates table) that is used in the first step of Active Directory Sync.</span></span></p>
<p><span data-ttu-id="fdf19-115">Изменения, внесенные в членство, хранятся и обрабатываются только для тех групп, которые перечислены в таблице tblPrincipal или члены которых содержатся в ней.</span><span class="sxs-lookup"><span data-stu-id="fdf19-115">Membership changes are stored, processed, or both, only for groups that are listed in the tblPrincipal table or that already have members listed there.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdf19-116"><a href="lync-server-2013-tbladupdates.md">Тбладупдатес в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="fdf19-116"><a href="lync-server-2013-tbladupdates.md">tblADUpdates in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="fdf19-117">Содержит изменения доменных служб Active Directory, которые еще не были обработаны с помощью последующих шагов синхронизации Active Directory и являются одной из временных таблиц (вместе с таблицей tblPrincipalMemberDifference), которая используется на первом этапе синхронизации Active Directory.</span><span class="sxs-lookup"><span data-stu-id="fdf19-117">Contains changes to Active Directory Domain Services that have not yet been processed by the later Active Directory Sync steps and is one of the temporary tables (along with the tblPrincipalMemberDifference table) that is used in the first step of Active Directory Sync.</span></span></p>
<p><span data-ttu-id="fdf19-118">Изменения в Active Directory сохраняются, обрабатываются или удаляются только для субъектов, которые уже указаны в таблице tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="fdf19-118">Changes to Active Directory are stored, processed, or both only for principals that are already listed in the tblPrincipal table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdf19-119"><a href="lync-server-2013-tblprincipalmembers.md">ТблпринЦипалмемберс в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="fdf19-119"><a href="lync-server-2013-tblprincipalmembers.md">tblPrincipalMembers in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="fdf19-120">Содержит сведения о членстве субъектов.</span><span class="sxs-lookup"><span data-stu-id="fdf19-120">Contains principal memberships.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdf19-121"><a href="lync-server-2013-tblprincipalmeta.md">tblPrincipalMeta в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="fdf19-121"><a href="lync-server-2013-tblprincipalmeta.md">tblPrincipalMeta in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="fdf19-122">Содержит субъекты, которые необходимо обновить из Active Directory.</span><span class="sxs-lookup"><span data-stu-id="fdf19-122">Contains the principals that have to be refreshed from Active Directory.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdf19-123"><a href="lync-server-2013-tblskippedaffiliations.md">tblSkippedAffiliations в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="fdf19-123"><a href="lync-server-2013-tblskippedaffiliations.md">tblSkippedAffiliations in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="fdf19-124">Содержит назначения, которые не удалось обновить по какой-либо причине, обычно из-за ошибок доступа к Active Directory.</span><span class="sxs-lookup"><span data-stu-id="fdf19-124">Contains affiliations that could not be refreshed for some reason, usually due to Active Directory access errors.</span></span></p>
<p><span data-ttu-id="fdf19-p102">Эта таблица служит только для информационных целей. Ее содержимое не используется.</span><span class="sxs-lookup"><span data-stu-id="fdf19-p102">This table is for informational purposes only. Its content is not used.</span></span></p>
<p><span data-ttu-id="fdf19-127">Субъекты, назначения которых не удалось правильно обновить, сохраняются в таблице tblPrincipalMeta и могут быть обновлены еще раз.</span><span class="sxs-lookup"><span data-stu-id="fdf19-127">The principals with affiliations that could not be refreshed properly are kept in the tblPrincipalMeta table and are given another chance to be refreshed.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="principals-affiliations-nodes-scopes-and-roles"></a><span data-ttu-id="fdf19-128">Субъекты, назначения, узлы, области действия и роли</span><span class="sxs-lookup"><span data-stu-id="fdf19-128">Principals, Affiliations, Nodes, Scopes, and Roles</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fdf19-129">Table</span><span class="sxs-lookup"><span data-stu-id="fdf19-129">Table</span></span></th>
<th><span data-ttu-id="fdf19-130">Описание</span><span class="sxs-lookup"><span data-stu-id="fdf19-130">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fdf19-131"><a href="lync-server-2013-tblprincipaltype.md">tblPrincipalType в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="fdf19-131"><a href="lync-server-2013-tblprincipaltype.md">tblPrincipalType in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="fdf19-p103">Содержит типы субъектов для разделения содержимого таблицы tblPrincipal на категории. Эта таблица является статической. Она настраивается при создании базы данных и больше не изменяется.</span><span class="sxs-lookup"><span data-stu-id="fdf19-p103">Contains principal types to categorize what is in the tblPrincipal table. This table is static. It is set up during database creation and does not change.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdf19-135"><a href="lync-server-2013-tblprincipal.md">tblPrincipal в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="fdf19-135"><a href="lync-server-2013-tblprincipal.md">tblPrincipal in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="fdf19-136">Содержит все субъекты (пользователей, папки, группы и т. д.).</span><span class="sxs-lookup"><span data-stu-id="fdf19-136">Contains all principals (users, folders, groups, and so on).</span></span> <span data-ttu-id="fdf19-137">Сервер сохраняемого чата обрабатывает его как плоский разнородный список.</span><span class="sxs-lookup"><span data-stu-id="fdf19-137">Persistent Chat Server handles this as a flat heterogeneous list.</span></span> <span data-ttu-id="fdf19-138">Каждый столбец соответствует типу субъекта.</span><span class="sxs-lookup"><span data-stu-id="fdf19-138">Various columns are based on the type of each principal.</span></span></p>
<p><span data-ttu-id="fdf19-139">Большая часть этих субъектов является кэшированными копиями объектов, хранящихся в Active Directory.</span><span class="sxs-lookup"><span data-stu-id="fdf19-139">Most of these principals are cached copies of objects stored in Active Directory.</span></span> <span data-ttu-id="fdf19-140">Создание кэшированной копии в основной таблице этих объектов Active Directory обозначается как <em>Подготовка</em>.</span><span class="sxs-lookup"><span data-stu-id="fdf19-140">Creating the cached copy in the Principal table of these Active Directory objects is referred as <em>provisioning</em>.</span></span></p>
<p><span data-ttu-id="fdf19-141">Некоторые субъекты создаются более агрессивно, чем другие, и некоторые объекты Active Directory полностью игнорируются.</span><span class="sxs-lookup"><span data-stu-id="fdf19-141">Some principals are created more aggressively than others, and some Active Directory objects are ignored altogether.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdf19-142"><a href="lync-server-2013-tblprincipalaffiliations.md">ТблпринЦипалаффилиатионс в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="fdf19-142"><a href="lync-server-2013-tblprincipalaffiliations.md">tblPrincipalAffiliations in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="fdf19-143">Содержит основные принадлежности, описывающие членство в группах безопасности Active Directory, контейнерах Active Directory и т. д.</span><span class="sxs-lookup"><span data-stu-id="fdf19-143">Contains principal affiliations that describe memberships in Active Directory security groups, Active Directory containers, and so on.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdf19-144"><a href="lync-server-2013-tblnode.md">tblNode в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="fdf19-144"><a href="lync-server-2013-tblnode.md">tblNode in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="fdf19-145">Содержит узел категории, управляемый в панели управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fdf19-145">Contains the category node, as managed in Lync Server Control Panel.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdf19-146"><a href="lync-server-2013-tblroletype.md">tblRoleType в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="fdf19-146"><a href="lync-server-2013-tblroletype.md">tblRoleType in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="fdf19-147">Содержит типы ролей и связанные с ними наборы разрешений.</span><span class="sxs-lookup"><span data-stu-id="fdf19-147">Contains role types and their associated permission sets.</span></span> <span data-ttu-id="fdf19-148">Эта таблица подстановки является статической.</span><span class="sxs-lookup"><span data-stu-id="fdf19-148">This lookup table is static.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdf19-149"><a href="lync-server-2013-tblscopeprincipal.md">tblScopePrincipal в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="fdf19-149"><a href="lync-server-2013-tblscopeprincipal.md">tblScopePrincipal in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="fdf19-150">Содержит области действия, назначенные узлам.</span><span class="sxs-lookup"><span data-stu-id="fdf19-150">Contains scopes assigned to nodes.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdf19-151"><a href="lync-server-2013-tblprincipalrole.md">tblPrincipalRole в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="fdf19-151"><a href="lync-server-2013-tblprincipalrole.md">tblPrincipalRole in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="fdf19-152">Содержит роли, назначенные узлам.</span><span class="sxs-lookup"><span data-stu-id="fdf19-152">Contains roles assigned to nodes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdf19-153"><a href="lync-server-2013-tblsiopwhitelist.md">tblSiopWhiteList в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="fdf19-153"><a href="lync-server-2013-tblsiopwhitelist.md">tblSiopWhiteList in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="fdf19-154">Содержит зарегистрированные надстройки, которые можно связать с узлами.</span><span class="sxs-lookup"><span data-stu-id="fdf19-154">Contains the registered Add-ins that can be associated with nodes.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdf19-155"><a href="lync-server-2013-tblenumattribute.md">Тбленуматтрибуте в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="fdf19-155"><a href="lync-server-2013-tblenumattribute.md">tblEnumAttribute in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="fdf19-156">Содержит только жестко запрограммированные &quot; &quot; атрибуты видимости и &quot; поведения &quot; , используемые в таблице tblNode.</span><span class="sxs-lookup"><span data-stu-id="fdf19-156">Contains only the hardcoded &quot;Visibility&quot; and &quot;Behavior&quot; attributes that are used in the tblNode table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdf19-157"><a href="lync-server-2013-tblenumvalue.md">tblEnumValue в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="fdf19-157"><a href="lync-server-2013-tblenumvalue.md">tblEnumValue in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="fdf19-158">Содержит значения &quot; атрибутов режима "и" для нежесткого отображения &quot; , которые используются в таблице tblNode.</span><span class="sxs-lookup"><span data-stu-id="fdf19-158">Contains the values of the hardcoded &quot;Visibility” and “Behavior&quot; attributes that are used in the tblNode table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="invites-chats-and-other-client-support"></a><span data-ttu-id="fdf19-159">Приглашения, чаты и другие поддерживаемые клиентом функции</span><span class="sxs-lookup"><span data-stu-id="fdf19-159">Invites, Chats, and Other Client Support</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fdf19-160">Table</span><span class="sxs-lookup"><span data-stu-id="fdf19-160">Table</span></span></th>
<th><span data-ttu-id="fdf19-161">Описание</span><span class="sxs-lookup"><span data-stu-id="fdf19-161">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fdf19-162"><a href="lync-server-2013-tblprincipalinvites.md">tblPrincipalInvites в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="fdf19-162"><a href="lync-server-2013-tblprincipalinvites.md">tblPrincipalInvites in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="fdf19-163">Содержит приглашения для всех подготовленных пользователей в системе для всех узлов, для которых включено автоматическое приглашение.</span><span class="sxs-lookup"><span data-stu-id="fdf19-163">Contains invites for all provisioned users in the system for all nodes with Auto Invite enabled.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdf19-164"><a href="lync-server-2013-tblchat.md">tblChat в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="fdf19-164"><a href="lync-server-2013-tblchat.md">tblChat in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="fdf19-165">Содержит все сообщения чата.</span><span class="sxs-lookup"><span data-stu-id="fdf19-165">Contains all chat messages.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdf19-166"><a href="lync-server-2013-tbllastinviteid.md">tblLastInviteId в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="fdf19-166"><a href="lync-server-2013-tbllastinviteid.md">tblLastInviteId in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="fdf19-167">Содержит последний созданный идентификатор приглашения (используемый в таблице tblPrincipalInvites) для каждого пользователя.</span><span class="sxs-lookup"><span data-stu-id="fdf19-167">Contains the last invite ID that was generated (and used in the tblPrincipalInvites table) for each user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdf19-168"><a href="lync-server-2013-tbllastchatid.md">tblLastChatId в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="fdf19-168"><a href="lync-server-2013-tbllastchatid.md">tblLastChatId in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="fdf19-169">Содержит последний созданный идентификатор чата (используемый в таблице tblChat) для каждого пользователя.</span><span class="sxs-lookup"><span data-stu-id="fdf19-169">Contains the last chat ID that was generated (and used in the tblChat table) for each user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdf19-170"><a href="lync-server-2013-tblpreference.md">Тблпреференце в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="fdf19-170"><a href="lync-server-2013-tblpreference.md">tblPreference in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="fdf19-171">Содержит пользовательские настройки клиента (используется только для устаревших клиентов).</span><span class="sxs-lookup"><span data-stu-id="fdf19-171">Contains user client preferences (used by legacy clients only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdf19-172"><a href="lync-server-2013-tblfiletoken.md">Тблфилетокен в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="fdf19-172"><a href="lync-server-2013-tblfiletoken.md">tblFileToken in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="fdf19-173">Содержит временные маркеры для передачи файлов.</span><span class="sxs-lookup"><span data-stu-id="fdf19-173">Contains temporary tokens for file transfer purposes.</span></span> <span data-ttu-id="fdf19-174">При каждом перезагрузке или загрузке файла служба сохраняемого чата создает маркер, который клиент использует для доступа к хранилищу файлов веб-служб.</span><span class="sxs-lookup"><span data-stu-id="fdf19-174">Each time a file is uploaded or downloaded, the Persistent Chat service generates a token that the client uses to access the Web service file store.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="server-support"></a><span data-ttu-id="fdf19-175">Поддержка серверов</span><span class="sxs-lookup"><span data-stu-id="fdf19-175">Server Support</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fdf19-176">Table</span><span class="sxs-lookup"><span data-stu-id="fdf19-176">Table</span></span></th>
<th><span data-ttu-id="fdf19-177">Описание</span><span class="sxs-lookup"><span data-stu-id="fdf19-177">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fdf19-178"><a href="lync-server-2013-tblserveridentity.md">tblServerIdentity в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="fdf19-178"><a href="lync-server-2013-tblserveridentity.md">tblServerIdentity in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="fdf19-179">Содержит активные серверы в пуле серверов сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="fdf19-179">Contains the active servers in the Persistent Chat Server pool.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdf19-180"><a href="lync-server-2013-tbladminlock.md">tblAdminLock в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="fdf19-180"><a href="lync-server-2013-tbladminlock.md">tblAdminLock in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="fdf19-p108">Содержит сведения о блокировке выполнения определенных команд администратором. Значение системного счетчика изменений в таблице tblSystemRevision увеличивается на единицу при каждом снятии блокировки.</span><span class="sxs-lookup"><span data-stu-id="fdf19-p108">Contains the administrator lock to run some administrator commands. The system revision entry in the tblSystemRevision table is incremented after each release of the lock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdf19-183"><a href="lync-server-2013-tblsystemrevision.md">Тблсистемревисион в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="fdf19-183"><a href="lync-server-2013-tblsystemrevision.md">tblSystemRevision in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="fdf19-184">Содержит номер редакции, используемый для обеспечения  согласованности на нескольких серверах (наряду с таблицей tblAdminLock).</span><span class="sxs-lookup"><span data-stu-id="fdf19-184">Contains the revision number entry used (along with the tblAdminLock table) for achieving consistency across multiple servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdf19-185"><a href="lync-server-2013-tblactivepeers.md">Тблактивепирс в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="fdf19-185"><a href="lync-server-2013-tblactivepeers.md">tblActivePeers in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="fdf19-186">Содержит текущие одноранговые подключения между службами сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="fdf19-186">Contains current peer-to-peer connections between Persistent Chat services.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdf19-187"><a href="lync-server-2013-tblconfig.md">tblConfig в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="fdf19-187"><a href="lync-server-2013-tblconfig.md">tblConfig in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="fdf19-188">Содержит неподдерживаемую конфигурацию сервера сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="fdf19-188">Contains the Persistent Chat Server unsupported configuration.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

