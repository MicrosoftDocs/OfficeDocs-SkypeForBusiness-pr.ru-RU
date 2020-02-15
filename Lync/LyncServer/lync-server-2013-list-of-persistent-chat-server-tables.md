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
ms.openlocfilehash: 4327e2a72f91e17fd71cd198940ea01d10423b00
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034711"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="list-of-persistent-chat-server-tables-in-lync-server-2013"></a><span data-ttu-id="3b995-102">Список таблиц сервера сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3b995-102">List of Persistent Chat Server tables in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3b995-103">_**Последнее изменение темы:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="3b995-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="3b995-104">Схема базы данных сохраняемого чата состоит из следующих таблиц.</span><span class="sxs-lookup"><span data-stu-id="3b995-104">The Persistent Chat database schema consists of the following tables.</span></span>

<div>

## <a name="active-directory-sync"></a><span data-ttu-id="3b995-105">Синхронизация Active Directory</span><span class="sxs-lookup"><span data-stu-id="3b995-105">Active Directory Sync</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3b995-106">Table</span><span class="sxs-lookup"><span data-stu-id="3b995-106">Table</span></span></th>
<th><span data-ttu-id="3b995-107">Описание</span><span class="sxs-lookup"><span data-stu-id="3b995-107">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3b995-108"><a href="lync-server-2013-tbladcookie.md">tblADCookie в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="3b995-108"><a href="lync-server-2013-tbladcookie.md">tblADCookie in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="3b995-109">Содержит текущие файлы cookie синхронизации по протоколу LDAP.</span><span class="sxs-lookup"><span data-stu-id="3b995-109">Contains the current Lightweight Directory Access Protocol (LDAP) Sync cookies.</span></span> <span data-ttu-id="3b995-110">Каждая строка соответствует домену доменных служб Active Directory, который активно отслеживает изменения на сервере сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="3b995-110">Each row corresponds to an Active Directory Domain Services domain that Persistent Chat Server is actively monitoring for changes.</span></span> <span data-ttu-id="3b995-111">В этой таблице представлены только те домены Active Directory, которые относятся к серверу сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="3b995-111">(Only the Active Directory domains that are relevant for Persistent Chat Server are represented in this table.)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b995-112"><a href="lync-server-2013-tblprincipalmemberdifference.md">tblPrincipalMemberDifference в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="3b995-112"><a href="lync-server-2013-tblprincipalmemberdifference.md">tblPrincipalMemberDifference in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="3b995-113">Содержит изменения членства в группах (добавленные и удаленные элементы), которые еще не были обработаны с помощью последующих шагов синхронизации Active Directory и являются одной из временных таблиц (вместе с таблицей Тбладупдатес), которая используется на первом этапе синхронизации Active Directory.</span><span class="sxs-lookup"><span data-stu-id="3b995-113">Contains group membership changes (both added and removed members) that have not yet been processed by the later Active Directory Sync steps and is one of the temporary tables (along with tblADUpdates table) that is used in the first step of Active Directory Sync.</span></span></p>
<p><span data-ttu-id="3b995-114">Изменения, внесенные в членство, хранятся и обрабатываются только для тех групп, которые перечислены в таблице tblPrincipal или члены которых содержатся в ней.</span><span class="sxs-lookup"><span data-stu-id="3b995-114">Membership changes are stored, processed, or both, only for groups that are listed in the tblPrincipal table or that already have members listed there.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3b995-115"><a href="lync-server-2013-tbladupdates.md">Тбладупдатес в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="3b995-115"><a href="lync-server-2013-tbladupdates.md">tblADUpdates in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="3b995-116">Содержит изменения доменных служб Active Directory, которые еще не были обработаны с помощью последующих шагов синхронизации Active Directory и являются одной из временных таблиц (вместе с таблицей tblPrincipalMemberDifference), которая используется на первом шаге Active Directory Синхр.</span><span class="sxs-lookup"><span data-stu-id="3b995-116">Contains changes to Active Directory Domain Services that have not yet been processed by the later Active Directory Sync steps and is one of the temporary tables (along with the tblPrincipalMemberDifference table) that is used in the first step of Active Directory Sync.</span></span></p>
<p><span data-ttu-id="3b995-117">Изменения в Active Directory сохраняются, обрабатываются или удаляются только для субъектов, которые уже указаны в таблице tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="3b995-117">Changes to Active Directory are stored, processed, or both only for principals that are already listed in the tblPrincipal table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b995-118"><a href="lync-server-2013-tblprincipalmembers.md">ТблпринЦипалмемберс в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="3b995-118"><a href="lync-server-2013-tblprincipalmembers.md">tblPrincipalMembers in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="3b995-119">Содержит сведения о членстве субъектов.</span><span class="sxs-lookup"><span data-stu-id="3b995-119">Contains principal memberships.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3b995-120"><a href="lync-server-2013-tblprincipalmeta.md">tblPrincipalMeta в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="3b995-120"><a href="lync-server-2013-tblprincipalmeta.md">tblPrincipalMeta in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="3b995-121">Содержит субъекты, которые необходимо обновить из Active Directory.</span><span class="sxs-lookup"><span data-stu-id="3b995-121">Contains the principals that have to be refreshed from Active Directory.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b995-122"><a href="lync-server-2013-tblskippedaffiliations.md">tblSkippedAffiliations в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="3b995-122"><a href="lync-server-2013-tblskippedaffiliations.md">tblSkippedAffiliations in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="3b995-123">Содержит назначения, которые не удалось обновить по какой-либо причине, обычно из-за ошибок доступа к Active Directory.</span><span class="sxs-lookup"><span data-stu-id="3b995-123">Contains affiliations that could not be refreshed for some reason, usually due to Active Directory access errors.</span></span></p>
<p><span data-ttu-id="3b995-p102">Эта таблица служит только для информационных целей. Ее содержимое не используется.</span><span class="sxs-lookup"><span data-stu-id="3b995-p102">This table is for informational purposes only. Its content is not used.</span></span></p>
<p><span data-ttu-id="3b995-126">Субъекты, назначения которых не удалось правильно обновить, сохраняются в таблице tblPrincipalMeta и могут быть обновлены еще раз.</span><span class="sxs-lookup"><span data-stu-id="3b995-126">The principals with affiliations that could not be refreshed properly are kept in the tblPrincipalMeta table and are given another chance to be refreshed.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="principals-affiliations-nodes-scopes-and-roles"></a><span data-ttu-id="3b995-127">Субъекты, назначения, узлы, области действия и роли</span><span class="sxs-lookup"><span data-stu-id="3b995-127">Principals, Affiliations, Nodes, Scopes, and Roles</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3b995-128">Table</span><span class="sxs-lookup"><span data-stu-id="3b995-128">Table</span></span></th>
<th><span data-ttu-id="3b995-129">Описание</span><span class="sxs-lookup"><span data-stu-id="3b995-129">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3b995-130"><a href="lync-server-2013-tblprincipaltype.md">tblPrincipalType в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="3b995-130"><a href="lync-server-2013-tblprincipaltype.md">tblPrincipalType in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="3b995-p103">Содержит типы субъектов для разделения содержимого таблицы tblPrincipal на категории. Эта таблица является статической. Она настраивается при создании базы данных и больше не изменяется.</span><span class="sxs-lookup"><span data-stu-id="3b995-p103">Contains principal types to categorize what is in the tblPrincipal table. This table is static. It is set up during database creation and does not change.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b995-134"><a href="lync-server-2013-tblprincipal.md">tblPrincipal в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="3b995-134"><a href="lync-server-2013-tblprincipal.md">tblPrincipal in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="3b995-135">Содержит все субъекты (пользователей, папки, группы и т. д.).</span><span class="sxs-lookup"><span data-stu-id="3b995-135">Contains all principals (users, folders, groups, and so on).</span></span> <span data-ttu-id="3b995-136">Сервер сохраняемого чата обрабатывает его как плоский разнородный список.</span><span class="sxs-lookup"><span data-stu-id="3b995-136">Persistent Chat Server handles this as a flat heterogeneous list.</span></span> <span data-ttu-id="3b995-137">Каждый столбец соответствует типу субъекта.</span><span class="sxs-lookup"><span data-stu-id="3b995-137">Various columns are based on the type of each principal.</span></span></p>
<p><span data-ttu-id="3b995-138">Большая часть этих субъектов является кэшированными копиями объектов, хранящихся в Active Directory.</span><span class="sxs-lookup"><span data-stu-id="3b995-138">Most of these principals are cached copies of objects stored in Active Directory.</span></span> <span data-ttu-id="3b995-139">Создание кэшированной копии в основной таблице этих объектов Active Directory обозначается как <em>Подготовка</em>.</span><span class="sxs-lookup"><span data-stu-id="3b995-139">Creating the cached copy in the Principal table of these Active Directory objects is referred as <em>provisioning</em>.</span></span></p>
<p><span data-ttu-id="3b995-140">Некоторые субъекты создаются более агрессивно, чем другие, и некоторые объекты Active Directory полностью игнорируются.</span><span class="sxs-lookup"><span data-stu-id="3b995-140">Some principals are created more aggressively than others, and some Active Directory objects are ignored altogether.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3b995-141"><a href="lync-server-2013-tblprincipalaffiliations.md">ТблпринЦипалаффилиатионс в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="3b995-141"><a href="lync-server-2013-tblprincipalaffiliations.md">tblPrincipalAffiliations in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="3b995-142">Содержит основные принадлежности, описывающие членство в группах безопасности Active Directory, контейнерах Active Directory и т. д.</span><span class="sxs-lookup"><span data-stu-id="3b995-142">Contains principal affiliations that describe memberships in Active Directory security groups, Active Directory containers, and so on.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b995-143"><a href="lync-server-2013-tblnode.md">tblNode в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="3b995-143"><a href="lync-server-2013-tblnode.md">tblNode in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="3b995-144">Содержит узел категории, управляемый в панели управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3b995-144">Contains the category node, as managed in Lync Server Control Panel.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3b995-145"><a href="lync-server-2013-tblroletype.md">tblRoleType в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="3b995-145"><a href="lync-server-2013-tblroletype.md">tblRoleType in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="3b995-146">Содержит типы ролей и связанные с ними наборы разрешений.</span><span class="sxs-lookup"><span data-stu-id="3b995-146">Contains role types and their associated permission sets.</span></span> <span data-ttu-id="3b995-147">Эта таблица подстановки является статической.</span><span class="sxs-lookup"><span data-stu-id="3b995-147">This lookup table is static.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b995-148"><a href="lync-server-2013-tblscopeprincipal.md">tblScopePrincipal в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="3b995-148"><a href="lync-server-2013-tblscopeprincipal.md">tblScopePrincipal in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="3b995-149">Содержит области действия, назначенные узлам.</span><span class="sxs-lookup"><span data-stu-id="3b995-149">Contains scopes assigned to nodes.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3b995-150"><a href="lync-server-2013-tblprincipalrole.md">tblPrincipalRole в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="3b995-150"><a href="lync-server-2013-tblprincipalrole.md">tblPrincipalRole in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="3b995-151">Содержит роли, назначенные узлам.</span><span class="sxs-lookup"><span data-stu-id="3b995-151">Contains roles assigned to nodes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b995-152"><a href="lync-server-2013-tblsiopwhitelist.md">tblSiopWhiteList в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="3b995-152"><a href="lync-server-2013-tblsiopwhitelist.md">tblSiopWhiteList in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="3b995-153">Содержит зарегистрированные надстройки, которые можно связать с узлами.</span><span class="sxs-lookup"><span data-stu-id="3b995-153">Contains the registered Add-ins that can be associated with nodes.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3b995-154"><a href="lync-server-2013-tblenumattribute.md">Тбленуматтрибуте в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="3b995-154"><a href="lync-server-2013-tblenumattribute.md">tblEnumAttribute in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="3b995-155">Содержит только жестко &quot;запрограммированные атрибуты видимости&quot; и &quot;поведения&quot; , используемые в таблице tblNode.</span><span class="sxs-lookup"><span data-stu-id="3b995-155">Contains only the hardcoded &quot;Visibility&quot; and &quot;Behavior&quot; attributes that are used in the tblNode table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b995-156"><a href="lync-server-2013-tblenumvalue.md">tblEnumValue в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="3b995-156"><a href="lync-server-2013-tblenumvalue.md">tblEnumValue in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="3b995-157">Содержит значения атрибутов режима &quot;&quot; "и" для нежесткого отображения, которые используются в таблице tblNode.</span><span class="sxs-lookup"><span data-stu-id="3b995-157">Contains the values of the hardcoded &quot;Visibility” and “Behavior&quot; attributes that are used in the tblNode table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="invites-chats-and-other-client-support"></a><span data-ttu-id="3b995-158">Приглашения, чаты и другие поддерживаемые клиентом функции</span><span class="sxs-lookup"><span data-stu-id="3b995-158">Invites, Chats, and Other Client Support</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3b995-159">Table</span><span class="sxs-lookup"><span data-stu-id="3b995-159">Table</span></span></th>
<th><span data-ttu-id="3b995-160">Описание</span><span class="sxs-lookup"><span data-stu-id="3b995-160">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3b995-161"><a href="lync-server-2013-tblprincipalinvites.md">tblPrincipalInvites в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="3b995-161"><a href="lync-server-2013-tblprincipalinvites.md">tblPrincipalInvites in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="3b995-162">Содержит приглашения для всех подготовленных пользователей в системе для всех узлов, для которых включено автоматическое приглашение.</span><span class="sxs-lookup"><span data-stu-id="3b995-162">Contains invites for all provisioned users in the system for all nodes with Auto Invite enabled.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b995-163"><a href="lync-server-2013-tblchat.md">tblChat в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="3b995-163"><a href="lync-server-2013-tblchat.md">tblChat in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="3b995-164">Содержит все сообщения чата.</span><span class="sxs-lookup"><span data-stu-id="3b995-164">Contains all chat messages.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3b995-165"><a href="lync-server-2013-tbllastinviteid.md">tblLastInviteId в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="3b995-165"><a href="lync-server-2013-tbllastinviteid.md">tblLastInviteId in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="3b995-166">Содержит последний созданный идентификатор приглашения (используемый в таблице tblPrincipalInvites) для каждого пользователя.</span><span class="sxs-lookup"><span data-stu-id="3b995-166">Contains the last invite ID that was generated (and used in the tblPrincipalInvites table) for each user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b995-167"><a href="lync-server-2013-tbllastchatid.md">tblLastChatId в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="3b995-167"><a href="lync-server-2013-tbllastchatid.md">tblLastChatId in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="3b995-168">Содержит последний созданный идентификатор чата (используемый в таблице tblChat) для каждого пользователя.</span><span class="sxs-lookup"><span data-stu-id="3b995-168">Contains the last chat ID that was generated (and used in the tblChat table) for each user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3b995-169"><a href="lync-server-2013-tblpreference.md">Тблпреференце в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="3b995-169"><a href="lync-server-2013-tblpreference.md">tblPreference in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="3b995-170">Содержит пользовательские настройки клиента (используется только для устаревших клиентов).</span><span class="sxs-lookup"><span data-stu-id="3b995-170">Contains user client preferences (used by legacy clients only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b995-171"><a href="lync-server-2013-tblfiletoken.md">Тблфилетокен в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="3b995-171"><a href="lync-server-2013-tblfiletoken.md">tblFileToken in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="3b995-172">Содержит временные маркеры для передачи файлов.</span><span class="sxs-lookup"><span data-stu-id="3b995-172">Contains temporary tokens for file transfer purposes.</span></span> <span data-ttu-id="3b995-173">При каждом перезагрузке или загрузке файла служба сохраняемого чата создает маркер, который клиент использует для доступа к хранилищу файлов веб-служб.</span><span class="sxs-lookup"><span data-stu-id="3b995-173">Each time a file is uploaded or downloaded, the Persistent Chat service generates a token that the client uses to access the Web service file store.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="server-support"></a><span data-ttu-id="3b995-174">Поддержка серверов</span><span class="sxs-lookup"><span data-stu-id="3b995-174">Server Support</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3b995-175">Table</span><span class="sxs-lookup"><span data-stu-id="3b995-175">Table</span></span></th>
<th><span data-ttu-id="3b995-176">Описание</span><span class="sxs-lookup"><span data-stu-id="3b995-176">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3b995-177"><a href="lync-server-2013-tblserveridentity.md">tblServerIdentity в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="3b995-177"><a href="lync-server-2013-tblserveridentity.md">tblServerIdentity in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="3b995-178">Содержит активные серверы в пуле серверов сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="3b995-178">Contains the active servers in the Persistent Chat Server pool.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b995-179"><a href="lync-server-2013-tbladminlock.md">tblAdminLock в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="3b995-179"><a href="lync-server-2013-tbladminlock.md">tblAdminLock in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="3b995-p108">Содержит сведения о блокировке выполнения определенных команд администратором. Значение системного счетчика изменений в таблице tblSystemRevision увеличивается на единицу при каждом снятии блокировки.</span><span class="sxs-lookup"><span data-stu-id="3b995-p108">Contains the administrator lock to run some administrator commands. The system revision entry in the tblSystemRevision table is incremented after each release of the lock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3b995-182"><a href="lync-server-2013-tblsystemrevision.md">Тблсистемревисион в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="3b995-182"><a href="lync-server-2013-tblsystemrevision.md">tblSystemRevision in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="3b995-183">Содержит номер редакции, используемый для обеспечения  согласованности на нескольких серверах (наряду с таблицей tblAdminLock).</span><span class="sxs-lookup"><span data-stu-id="3b995-183">Contains the revision number entry used (along with the tblAdminLock table) for achieving consistency across multiple servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b995-184"><a href="lync-server-2013-tblactivepeers.md">Тблактивепирс в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="3b995-184"><a href="lync-server-2013-tblactivepeers.md">tblActivePeers in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="3b995-185">Содержит текущие одноранговые подключения между службами сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="3b995-185">Contains current peer-to-peer connections between Persistent Chat services.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3b995-186"><a href="lync-server-2013-tblconfig.md">tblConfig в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="3b995-186"><a href="lync-server-2013-tblconfig.md">tblConfig in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="3b995-187">Содержит неподдерживаемую конфигурацию сервера сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="3b995-187">Contains the Persistent Chat Server unsupported configuration.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

