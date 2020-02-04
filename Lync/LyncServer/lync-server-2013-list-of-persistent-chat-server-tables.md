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
ms.openlocfilehash: 4902f0710752dd38c146b01bddcc44e135735201
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765407"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="list-of-persistent-chat-server-tables-in-lync-server-2013"></a><span data-ttu-id="98617-102">Список таблиц сервера сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="98617-102">List of Persistent Chat Server tables in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="98617-103">_**Тема последнего изменения:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="98617-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="98617-104">Схема базы данных сохраняемого чата состоит из следующих таблиц.</span><span class="sxs-lookup"><span data-stu-id="98617-104">The Persistent Chat database schema consists of the following tables.</span></span>

<div>

## <a name="active-directory-sync"></a><span data-ttu-id="98617-105">Синхронизация службы каталогов Active Directory</span><span class="sxs-lookup"><span data-stu-id="98617-105">Active Directory Sync</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="98617-106">Таблица</span><span class="sxs-lookup"><span data-stu-id="98617-106">Table</span></span></th>
<th><span data-ttu-id="98617-107">Описание</span><span class="sxs-lookup"><span data-stu-id="98617-107">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="98617-108"><a href="lync-server-2013-tbladcookie.md">tblADCookie в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="98617-108"><a href="lync-server-2013-tbladcookie.md">tblADCookie in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="98617-109">В этой папке содержатся файлы cookie для синхронизации протокола Lightweight Directory Access.</span><span class="sxs-lookup"><span data-stu-id="98617-109">Contains the current Lightweight Directory Access Protocol (LDAP) Sync cookies.</span></span> <span data-ttu-id="98617-110">Каждая строка соответствует домену доменных служб Active Directory, в котором активный сервер чата отслеживает изменения.</span><span class="sxs-lookup"><span data-stu-id="98617-110">Each row corresponds to an Active Directory Domain Services domain that Persistent Chat Server is actively monitoring for changes.</span></span> <span data-ttu-id="98617-111">(В этой таблице представлены только те домены службы каталогов Active Directory, которые относятся к серверу сохраняемого чата.)</span><span class="sxs-lookup"><span data-stu-id="98617-111">(Only the Active Directory domains that are relevant for Persistent Chat Server are represented in this table.)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98617-112"><a href="lync-server-2013-tblprincipalmemberdifference.md">tblPrincipalMemberDifference в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="98617-112"><a href="lync-server-2013-tblprincipalmemberdifference.md">tblPrincipalMemberDifference in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="98617-113">Содержит изменения членства в группах (добавленные и удаленные участники), которые еще не были обработаны с помощью последующих шагов синхронизации Active Directory и являются одной из временных таблиц (вместе с таблицей Тбладупдатес), которая используется на первом этапе синхронизации Active Directory.</span><span class="sxs-lookup"><span data-stu-id="98617-113">Contains group membership changes (both added and removed members) that have not yet been processed by the later Active Directory Sync steps and is one of the temporary tables (along with tblADUpdates table) that is used in the first step of Active Directory Sync.</span></span></p>
<p><span data-ttu-id="98617-114">Изменения в членстве сохраняются, обрабатываются или отображаются только для групп, указанных в таблице ТблпринЦипал или уже содержащихся в них участников.</span><span class="sxs-lookup"><span data-stu-id="98617-114">Membership changes are stored, processed, or both, only for groups that are listed in the tblPrincipal table or that already have members listed there.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="98617-115"><a href="lync-server-2013-tbladupdates.md">tblADUpdates в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="98617-115"><a href="lync-server-2013-tbladupdates.md">tblADUpdates in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="98617-116">Содержит изменения, внесенные в доменные службы Active Directory, которые еще не обрабатывались с помощью последующих шагов синхронизации Active Directory, и являются одной из временных таблиц (вместе с таблицей ТблпринЦипалмембердифференце), которая используется на первом этапе службы каталогов Active Directory. Идет.</span><span class="sxs-lookup"><span data-stu-id="98617-116">Contains changes to Active Directory Domain Services that have not yet been processed by the later Active Directory Sync steps and is one of the temporary tables (along with the tblPrincipalMemberDifference table) that is used in the first step of Active Directory Sync.</span></span></p>
<p><span data-ttu-id="98617-117">Изменения, вносимые в Active Directory, сохраняются, обрабатываются или обе будут только для участников, которые уже указаны в таблице ТблпринЦипал.</span><span class="sxs-lookup"><span data-stu-id="98617-117">Changes to Active Directory are stored, processed, or both only for principals that are already listed in the tblPrincipal table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98617-118"><a href="lync-server-2013-tblprincipalmembers.md">tblPrincipalMembers в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="98617-118"><a href="lync-server-2013-tblprincipalmembers.md">tblPrincipalMembers in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="98617-119">Сведения о членстве участников.</span><span class="sxs-lookup"><span data-stu-id="98617-119">Contains principal memberships.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="98617-120"><a href="lync-server-2013-tblprincipalmeta.md">tblPrincipalMeta в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="98617-120"><a href="lync-server-2013-tblprincipalmeta.md">tblPrincipalMeta in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="98617-121">Содержит участников, которые необходимо обновлять из службы каталогов Active Directory.</span><span class="sxs-lookup"><span data-stu-id="98617-121">Contains the principals that have to be refreshed from Active Directory.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98617-122"><a href="lync-server-2013-tblskippedaffiliations.md">tblSkippedAffiliations в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="98617-122"><a href="lync-server-2013-tblskippedaffiliations.md">tblSkippedAffiliations in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="98617-123">Содержат назначения, которые не удалось обновить по некоторым причинам, обычно из-за ошибок доступа в службе каталогов Active Directory.</span><span class="sxs-lookup"><span data-stu-id="98617-123">Contains affiliations that could not be refreshed for some reason, usually due to Active Directory access errors.</span></span></p>
<p><span data-ttu-id="98617-124">Эта таблица предназначена исключительно для информационных целей.</span><span class="sxs-lookup"><span data-stu-id="98617-124">This table is for informational purposes only.</span></span> <span data-ttu-id="98617-125">Его содержимое не используется.</span><span class="sxs-lookup"><span data-stu-id="98617-125">Its content is not used.</span></span></p>
<p><span data-ttu-id="98617-126">Участники с назначением, которые не удалось обновить надлежащим образом, хранятся в таблице ТблпринЦипалмета и получают другой шанс на обновление.</span><span class="sxs-lookup"><span data-stu-id="98617-126">The principals with affiliations that could not be refreshed properly are kept in the tblPrincipalMeta table and are given another chance to be refreshed.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="principals-affiliations-nodes-scopes-and-roles"></a><span data-ttu-id="98617-127">Участники, принадлежности, узлы, области и роли</span><span class="sxs-lookup"><span data-stu-id="98617-127">Principals, Affiliations, Nodes, Scopes, and Roles</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="98617-128">Таблица</span><span class="sxs-lookup"><span data-stu-id="98617-128">Table</span></span></th>
<th><span data-ttu-id="98617-129">Описание</span><span class="sxs-lookup"><span data-stu-id="98617-129">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="98617-130"><a href="lync-server-2013-tblprincipaltype.md">tblPrincipalType в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="98617-130"><a href="lync-server-2013-tblprincipaltype.md">tblPrincipalType in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="98617-131">Содержит типы принципалов для классификации содержимого в таблице ТблпринЦипал.</span><span class="sxs-lookup"><span data-stu-id="98617-131">Contains principal types to categorize what is in the tblPrincipal table.</span></span> <span data-ttu-id="98617-132">Эта таблица является статичной.</span><span class="sxs-lookup"><span data-stu-id="98617-132">This table is static.</span></span> <span data-ttu-id="98617-133">Он настроен во время создания базы данных и не меняется.</span><span class="sxs-lookup"><span data-stu-id="98617-133">It is set up during database creation and does not change.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98617-134"><a href="lync-server-2013-tblprincipal.md">tblPrincipal в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="98617-134"><a href="lync-server-2013-tblprincipal.md">tblPrincipal in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="98617-135">Содержат все участники (пользователи, папки, группы и т. д.).</span><span class="sxs-lookup"><span data-stu-id="98617-135">Contains all principals (users, folders, groups, and so on).</span></span> <span data-ttu-id="98617-136">Сервер сохраняемого чата обрабатывает его как плоский разнородный список.</span><span class="sxs-lookup"><span data-stu-id="98617-136">Persistent Chat Server handles this as a flat heterogeneous list.</span></span> <span data-ttu-id="98617-137">Различные столбцы основываются на типе каждого участника.</span><span class="sxs-lookup"><span data-stu-id="98617-137">Various columns are based on the type of each principal.</span></span></p>
<p><span data-ttu-id="98617-138">Большинство из этих участников кэшируют копии объектов, которые хранятся в Active Directory.</span><span class="sxs-lookup"><span data-stu-id="98617-138">Most of these principals are cached copies of objects stored in Active Directory.</span></span> <span data-ttu-id="98617-139">Создание кэшированной копии в основной таблице этих объектов Active Directory называется <em>Подготовка</em>.</span><span class="sxs-lookup"><span data-stu-id="98617-139">Creating the cached copy in the Principal table of these Active Directory objects is referred as <em>provisioning</em>.</span></span></p>
<p><span data-ttu-id="98617-140">Некоторые принципалы создаются более агрессивно, чем другие, а некоторые объекты Active Directory пропускаются полностью.</span><span class="sxs-lookup"><span data-stu-id="98617-140">Some principals are created more aggressively than others, and some Active Directory objects are ignored altogether.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="98617-141"><a href="lync-server-2013-tblprincipalaffiliations.md">tblPrincipalAffiliations в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="98617-141"><a href="lync-server-2013-tblprincipalaffiliations.md">tblPrincipalAffiliations in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="98617-142">Содержат основные принадлежности, описывающие участие в группах безопасности Active Directory, контейнерах Active Directory и т. д.</span><span class="sxs-lookup"><span data-stu-id="98617-142">Contains principal affiliations that describe memberships in Active Directory security groups, Active Directory containers, and so on.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98617-143"><a href="lync-server-2013-tblnode.md">tblNode в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="98617-143"><a href="lync-server-2013-tblnode.md">tblNode in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="98617-144">Раздел "Категория", управляемый на панели управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="98617-144">Contains the category node, as managed in Lync Server Control Panel.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="98617-145"><a href="lync-server-2013-tblroletype.md">tblRoleType в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="98617-145"><a href="lync-server-2013-tblroletype.md">tblRoleType in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="98617-146">Содержат типы ролей и связанные с ними наборы разрешений.</span><span class="sxs-lookup"><span data-stu-id="98617-146">Contains role types and their associated permission sets.</span></span> <span data-ttu-id="98617-147">Эта таблица подстановки является статичной.</span><span class="sxs-lookup"><span data-stu-id="98617-147">This lookup table is static.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98617-148"><a href="lync-server-2013-tblscopeprincipal.md">tblScopePrincipal в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="98617-148"><a href="lync-server-2013-tblscopeprincipal.md">tblScopePrincipal in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="98617-149">Содержат области, назначенные узлам.</span><span class="sxs-lookup"><span data-stu-id="98617-149">Contains scopes assigned to nodes.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="98617-150"><a href="lync-server-2013-tblprincipalrole.md">tblPrincipalRole в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="98617-150"><a href="lync-server-2013-tblprincipalrole.md">tblPrincipalRole in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="98617-151">Содержат роли, назначенные узлам.</span><span class="sxs-lookup"><span data-stu-id="98617-151">Contains roles assigned to nodes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98617-152"><a href="lync-server-2013-tblsiopwhitelist.md">tblSiopWhiteList в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="98617-152"><a href="lync-server-2013-tblsiopwhitelist.md">tblSiopWhiteList in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="98617-153">Содержат зарегистрированные надстройки, которые можно связать с узлами.</span><span class="sxs-lookup"><span data-stu-id="98617-153">Contains the registered Add-ins that can be associated with nodes.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="98617-154"><a href="lync-server-2013-tblenumattribute.md">tblEnumAttribute в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="98617-154"><a href="lync-server-2013-tblenumattribute.md">tblEnumAttribute in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="98617-155">Содержат только закодированные &quot;атрибуты&quot; видимости &quot;и&quot; поведения, используемые в таблице тблноде.</span><span class="sxs-lookup"><span data-stu-id="98617-155">Contains only the hardcoded &quot;Visibility&quot; and &quot;Behavior&quot; attributes that are used in the tblNode table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98617-156"><a href="lync-server-2013-tblenumvalue.md">tblEnumValue в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="98617-156"><a href="lync-server-2013-tblenumvalue.md">tblEnumValue in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="98617-157">Содержат значения &quot;атрибутов поведения&quot; "и", которые используются в таблице тблноде.</span><span class="sxs-lookup"><span data-stu-id="98617-157">Contains the values of the hardcoded &quot;Visibility” and “Behavior&quot; attributes that are used in the tblNode table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="invites-chats-and-other-client-support"></a><span data-ttu-id="98617-158">Приглашения, разговоры и другие службы поддержки клиентов</span><span class="sxs-lookup"><span data-stu-id="98617-158">Invites, Chats, and Other Client Support</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="98617-159">Таблица</span><span class="sxs-lookup"><span data-stu-id="98617-159">Table</span></span></th>
<th><span data-ttu-id="98617-160">Описание</span><span class="sxs-lookup"><span data-stu-id="98617-160">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="98617-161"><a href="lync-server-2013-tblprincipalinvites.md">tblPrincipalInvites в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="98617-161"><a href="lync-server-2013-tblprincipalinvites.md">tblPrincipalInvites in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="98617-162">Содержат приглашения для всех подготовленных пользователей в системе для всех узлов с включенным параметром "автоматическое приглашение".</span><span class="sxs-lookup"><span data-stu-id="98617-162">Contains invites for all provisioned users in the system for all nodes with Auto Invite enabled.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98617-163"><a href="lync-server-2013-tblchat.md">tblChat в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="98617-163"><a href="lync-server-2013-tblchat.md">tblChat in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="98617-164">Содержат все сообщения чата.</span><span class="sxs-lookup"><span data-stu-id="98617-164">Contains all chat messages.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="98617-165"><a href="lync-server-2013-tbllastinviteid.md">tblLastInviteId в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="98617-165"><a href="lync-server-2013-tbllastinviteid.md">tblLastInviteId in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="98617-166">Содержащий идентификатор последнего приглашения, который был создан (и использован в таблице ТблпринЦипалинвитес) для каждого пользователя.</span><span class="sxs-lookup"><span data-stu-id="98617-166">Contains the last invite ID that was generated (and used in the tblPrincipalInvites table) for each user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98617-167"><a href="lync-server-2013-tbllastchatid.md">tblLastChatId в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="98617-167"><a href="lync-server-2013-tbllastchatid.md">tblLastChatId in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="98617-168">Содержащий последний идентификатор чата, который был создан (и использован в таблице Тблчат) для каждого пользователя.</span><span class="sxs-lookup"><span data-stu-id="98617-168">Contains the last chat ID that was generated (and used in the tblChat table) for each user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="98617-169"><a href="lync-server-2013-tblpreference.md">tblPreference в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="98617-169"><a href="lync-server-2013-tblpreference.md">tblPreference in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="98617-170">Содержат пользовательские настройки клиента (используется только устаревшими клиентами).</span><span class="sxs-lookup"><span data-stu-id="98617-170">Contains user client preferences (used by legacy clients only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98617-171"><a href="lync-server-2013-tblfiletoken.md">tblFileToken в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="98617-171"><a href="lync-server-2013-tblfiletoken.md">tblFileToken in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="98617-172">Содержат временные маркеры для целей передачи файлов.</span><span class="sxs-lookup"><span data-stu-id="98617-172">Contains temporary tokens for file transfer purposes.</span></span> <span data-ttu-id="98617-173">Каждый раз, когда файл отправляется или загружается, служба сохраняемого чата создает маркер, который используется клиентом для доступа к хранилищу файлов веб-служб.</span><span class="sxs-lookup"><span data-stu-id="98617-173">Each time a file is uploaded or downloaded, the Persistent Chat service generates a token that the client uses to access the Web service file store.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="server-support"></a><span data-ttu-id="98617-174">Поддержка сервера</span><span class="sxs-lookup"><span data-stu-id="98617-174">Server Support</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="98617-175">Таблица</span><span class="sxs-lookup"><span data-stu-id="98617-175">Table</span></span></th>
<th><span data-ttu-id="98617-176">Описание</span><span class="sxs-lookup"><span data-stu-id="98617-176">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="98617-177"><a href="lync-server-2013-tblserveridentity.md">tblServerIdentity в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="98617-177"><a href="lync-server-2013-tblserveridentity.md">tblServerIdentity in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="98617-178">Включает активные серверы в пуле сервера сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="98617-178">Contains the active servers in the Persistent Chat Server pool.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98617-179"><a href="lync-server-2013-tbladminlock.md">tblAdminLock в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="98617-179"><a href="lync-server-2013-tbladminlock.md">tblAdminLock in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="98617-180">Включает блокировку администратора для выполнения некоторых команд администратора.</span><span class="sxs-lookup"><span data-stu-id="98617-180">Contains the administrator lock to run some administrator commands.</span></span> <span data-ttu-id="98617-181">При каждом выпуске блокировки в таблице Тблсистемревисион увеличивается запись о редакции системы.</span><span class="sxs-lookup"><span data-stu-id="98617-181">The system revision entry in the tblSystemRevision table is incremented after each release of the lock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="98617-182"><a href="lync-server-2013-tblsystemrevision.md">tblSystemRevision в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="98617-182"><a href="lync-server-2013-tblsystemrevision.md">tblSystemRevision in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="98617-183">Включает номер редакции (вместе с таблицей Тбладминлокк) для достижения согласованности на нескольких серверах.</span><span class="sxs-lookup"><span data-stu-id="98617-183">Contains the revision number entry used (along with the tblAdminLock table) for achieving consistency across multiple servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98617-184"><a href="lync-server-2013-tblactivepeers.md">tblActivePeers в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="98617-184"><a href="lync-server-2013-tblactivepeers.md">tblActivePeers in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="98617-185">В этом поле содержатся текущие одноранговые соединения между службами сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="98617-185">Contains current peer-to-peer connections between Persistent Chat services.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="98617-186"><a href="lync-server-2013-tblconfig.md">tblConfig в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="98617-186"><a href="lync-server-2013-tblconfig.md">tblConfig in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="98617-187">Неподдерживаемая конфигурация сервера сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="98617-187">Contains the Persistent Chat Server unsupported configuration.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

