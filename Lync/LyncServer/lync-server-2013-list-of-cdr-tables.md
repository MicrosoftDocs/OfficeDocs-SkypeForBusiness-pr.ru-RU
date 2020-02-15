---
title: 'Lync Server 2013: список таблиц CDR'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: List of CDR tables
ms:assetid: 031843fd-c7ff-4534-9b02-8847aad70807
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398084(v=OCS.15)
ms:contentKeyID: 48183254
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6f7f6fed1fad8cf706b86ef0cb141ab04fb39382
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048550"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="list-of-cdr-tables-in-lync-server-2013"></a><span data-ttu-id="93242-102">Список таблиц CDR в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="93242-102">List of CDR tables in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="93242-103">_**Последнее изменение темы:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="93242-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="93242-104">Схема базы данных регистрации вызовов (call detail recording — CDR) состоит из следующих таблиц.</span><span class="sxs-lookup"><span data-stu-id="93242-104">The call detail recording (CDR) database schema consists of the following tables.</span></span>

<div>

## <a name="static-tables"></a><span data-ttu-id="93242-105">Статические таблицы</span><span class="sxs-lookup"><span data-stu-id="93242-105">Static Tables</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="93242-106">Table</span><span class="sxs-lookup"><span data-stu-id="93242-106">Table</span></span></th>
<th><span data-ttu-id="93242-107">Описание</span><span class="sxs-lookup"><span data-stu-id="93242-107">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="93242-108"><a href="lync-server-2013-callpriorities-table.md">Таблица Таблица callpriorities в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="93242-108"><a href="lync-server-2013-callpriorities-table.md">CallPriorities table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="93242-109">Сохранение списка возможных приоритетов вызовов (включая аварийные, срочные, обычные, несрочные и т. д.).</span><span class="sxs-lookup"><span data-stu-id="93242-109">Stores the list of possible call priorities, such as emergency, urgent, normal, non-urgent, and more.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93242-110"><a href="lync-server-2013-conferencejointimethresholds-table.md">Таблица Таблица conferencejointimethresholds в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="93242-110"><a href="lync-server-2013-conferencejointimethresholds-table.md">ConferenceJoinTimeThresholds table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="93242-111">Сохранение границ классификации, используемых в отчете со сводными данными по времени подсоединения к конференции.</span><span class="sxs-lookup"><span data-stu-id="93242-111">Stores the classification boundaries used by the Conference Join Time Summary Report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93242-112"><a href="lync-server-2013-deregistertype-table.md">Таблица Таблица deregistertype в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="93242-112"><a href="lync-server-2013-deregistertype-table.md">DeRegisterType table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="93242-113">Хранит список возможных причин отмены регистрации пользователей, таких как &quot;инициирование клиента,&quot; &quot;срок действия регистрации,&quot; &quot;сбой клиента&quot; и многое другое.</span><span class="sxs-lookup"><span data-stu-id="93242-113">Stores the list of possible user de-register reasons, such as &quot;client initiated,&quot; &quot;registration expired,&quot; &quot;client crash,&quot; and more.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93242-114"><a href="lync-server-2013-medialist-table.md">Таблица Таблица medialist в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="93242-114"><a href="lync-server-2013-medialist-table.md">MediaList table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="93242-115">Сохранение списка типов мультимедиа, которые могут создавать записи в базе данных (например, чат, аудио, видео и передача файлов).</span><span class="sxs-lookup"><span data-stu-id="93242-115">Stores the list of media types that can generate entries in the database (for example, IM, audio, video, and file transfer).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93242-116"><a href="lync-server-2013-purgesettings-table.md">Таблица Таблица purgesettings в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="93242-116"><a href="lync-server-2013-purgesettings-table.md">PurgeSettings table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="93242-117">Сохранение информации, определяющей, следует ли (и когда) автоматически удалять устаревшие записи о вызовах из базы данных CDR.</span><span class="sxs-lookup"><span data-stu-id="93242-117">Stores information that specifies if (and when) outdated call detail records will automatically be deleted from the CDR database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93242-118"><a href="lync-server-2013-roles-table.md">Таблица Roles в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="93242-118"><a href="lync-server-2013-roles-table.md">Roles table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="93242-119">Сохранение списка возможных ролей участников конференции (например, участник и докладчик).</span><span class="sxs-lookup"><span data-stu-id="93242-119">Stores the list of possible conference roles (for example, attendee and presenter).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93242-120"><a href="lync-server-2013-sipresponsemetadata-table.md">Таблица Сипреспонсеметадата в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="93242-120"><a href="lync-server-2013-sipresponsemetadata-table.md">SIPResponseMetaData table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="93242-121">Сохранение списка кодов ответов SIP, классификации и определения каждого из этих кодов.</span><span class="sxs-lookup"><span data-stu-id="93242-121">Stores a list of SIP response codes and the classification and definition of each of those codes.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="supporting-tables"></a><span data-ttu-id="93242-122">Вспомогательные таблицы</span><span class="sxs-lookup"><span data-stu-id="93242-122">Supporting Tables</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="93242-123">Table</span><span class="sxs-lookup"><span data-stu-id="93242-123">Table</span></span></th>
<th><span data-ttu-id="93242-124">Описание</span><span class="sxs-lookup"><span data-stu-id="93242-124">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="93242-125"><a href="lync-server-2013-clientversions-table.md">Таблица Таблица clientversions в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="93242-125"><a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="93242-126">Сохранение клиентов (включая тип клиента и номер версии) каждого клиента, участвующего в вызове, с указанием информации, собранной в этой базе данных.</span><span class="sxs-lookup"><span data-stu-id="93242-126">Stores the clients (both client type and version number) of each client involved in a call with information captured in this database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93242-127"><a href="lync-server-2013-conferenceuris-table.md">Таблица Таблица conferenceuris в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="93242-127"><a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="93242-128">Сохранение списка кодов URI конференций, которые используются в вызовах, связанных с конференцией.</span><span class="sxs-lookup"><span data-stu-id="93242-128">Stores a list of ConferenceURIs that are used in conference related calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93242-129"><a href="lync-server-2013-contenttypes-table.md">Таблица ContentTypes в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="93242-129"><a href="lync-server-2013-contenttypes-table.md">ContentTypes table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="93242-130">Сохранение списка типов содержимого SIP (Session Initiation Protocol), которые используются и в одноранговых вызовах, и в конференц-вызовах.</span><span class="sxs-lookup"><span data-stu-id="93242-130">Stores a list of Session Initiation Protocol (SIP) content types that are used in both peer-to-peer calls and conference calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93242-131"><a href="lync-server-2013-devices-table.md">Таблица Devices в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="93242-131"><a href="lync-server-2013-devices-table.md">Devices table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="93242-132">Сохранение списка устройств, включая производителя, версию оборудования и MAC-адрес.</span><span class="sxs-lookup"><span data-stu-id="93242-132">Stores a list of devices, including their manufacturer, hardware version, and MAC address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93242-133"><a href="lync-server-2013-dialogs-table.md">Таблица диалогов в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="93242-133"><a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="93242-134">Сохранение идентификаторов диалогов для каждого сеанса в базе данных.</span><span class="sxs-lookup"><span data-stu-id="93242-134">Stores information about the Dialog ID for each session in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93242-135"><a href="lync-server-2013-edgeservers-table.md">Таблица Таблица edgeservers в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="93242-135"><a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="93242-136">Сохранение списка пограничных серверов, которые используются для внешних вызовов.</span><span class="sxs-lookup"><span data-stu-id="93242-136">Stores a list of Edge Servers that are used for external calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93242-137"><a href="lync-server-2013-gateways-table.md">Таблица Gateways в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="93242-137"><a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="93242-138">Сохранение списка шлюзов, которые используются для вызовов по протоколу VoIP.</span><span class="sxs-lookup"><span data-stu-id="93242-138">Stores a list of Gateways that are used for Voice over Internet Protocol (VoIP) calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93242-139"><a href="lync-server-2013-hardwareversions-table.md">Таблица Таблица hardwareversions в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="93242-139"><a href="lync-server-2013-hardwareversions-table.md">HardwareVersions table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="93242-140">Сохранение списка аппаратных версий устройств (стационарный телефон).</span><span class="sxs-lookup"><span data-stu-id="93242-140">Stores a list of hardware versions of devices (desk phone).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93242-141"><a href="lync-server-2013-manufacturers-table.md">Таблица производителей в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="93242-141"><a href="lync-server-2013-manufacturers-table.md">Manufacturers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="93242-142">Сохранение списка производителей устройств (стационарный телефон).</span><span class="sxs-lookup"><span data-stu-id="93242-142">Stores a list of manufacturers of devices (desk phone).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93242-143"><a href="lync-server-2013-mcus-table.md">Таблица MCUs в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="93242-143"><a href="lync-server-2013-mcus-table.md">Mcus table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="93242-144">Сохранение информации о различных серверах конференц-связи (аудио-видео) и их кодов URI.</span><span class="sxs-lookup"><span data-stu-id="93242-144">Stores information about the various A/V Conferencing Servers and their URIs.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93242-145"><a href="lync-server-2013-mediationservers-table.md">Таблица Таблица mediationservers в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="93242-145"><a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="93242-146">Сохранение списка серверов-посредников, используемых для выполнения вызовов по протоколу VoIP.</span><span class="sxs-lookup"><span data-stu-id="93242-146">Stores a list of Mediation Servers that are used for VoIP calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93242-147"><a href="lync-server-2013-phones-table.md">Таблица phones в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="93242-147"><a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="93242-148">Сохранение всех номеров телефона, использованных для выполнения вызовов по протоколу VoIP, которые были архивированы или сведения о которых были зарегистрированы.</span><span class="sxs-lookup"><span data-stu-id="93242-148">Stores all the phone numbers used in VoIP calls that were archived or whose call details were recorded.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93242-149"><a href="lync-server-2013-pools-table.md">Таблица Pools в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="93242-149"><a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="93242-150">Сохранение имен пула, в котором записываются мгновенные сообщения.</span><span class="sxs-lookup"><span data-stu-id="93242-150">Stores the names of the pool on which IM messages are captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93242-151"><a href="lync-server-2013-servers-table.md">Таблица Servers в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="93242-151"><a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="93242-152">Сохранение имен серверов, участвующих в вызовах.</span><span class="sxs-lookup"><span data-stu-id="93242-152">Stores the name of servers involved in calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93242-153"><a href="lync-server-2013-tenants-table.md">Таблица клиентов в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="93242-153"><a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="93242-154">Сохранение клиентов, поддерживаемых текущим развертыванием.</span><span class="sxs-lookup"><span data-stu-id="93242-154">Stores the tenants supported by current deployment.</span></span> <span data-ttu-id="93242-155">Существует ряд встроенных клиентов для корпоративных пользователей, федеративных пользователей, пользователей с подключением к общедоступным системам обмена мгновенными сообщениями и анонимных пользователей.</span><span class="sxs-lookup"><span data-stu-id="93242-155">There some build-in tenants for Enterprise user, Federated User, public IM connectivity user, and Anonymous users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93242-156"><a href="lync-server-2013-useragentdef-table.md">Таблица Таблица useragentdef в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="93242-156"><a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="93242-157">Привязка идентификаторов агента пользователя к описательным именам агента.</span><span class="sxs-lookup"><span data-stu-id="93242-157">Maps user agent identifiers to the agent’s descriptive names.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93242-158"><a href="lync-server-2013-users-table.md">Таблица Users в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="93242-158"><a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="93242-159">Сохранение кодов URI пользователей, которые участвовали в сеансах, зарегистрированных или заархивированных в этой базе данных.</span><span class="sxs-lookup"><span data-stu-id="93242-159">Stores the user URIs of users who have participated in sessions recorded or archived in this database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93242-160"><a href="lync-server-2013-userstatistics-table.md">Таблица Усерстатистикс в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="93242-160"><a href="lync-server-2013-userstatistics-table.md">UserStatistics table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="93242-161">Сохранение сведений об использовании системы отдельным пользователем.</span><span class="sxs-lookup"><span data-stu-id="93242-161">Stores information about an individual user’s usage of the system.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-specific-to-conference-cdr-records"></a><span data-ttu-id="93242-162">Записи, относящиеся к конкретным записям CDR конференции</span><span class="sxs-lookup"><span data-stu-id="93242-162">Tables Specific to Conference CDR Records</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="93242-163">Table</span><span class="sxs-lookup"><span data-stu-id="93242-163">Table</span></span></th>
<th><span data-ttu-id="93242-164">Описание</span><span class="sxs-lookup"><span data-stu-id="93242-164">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="93242-165"><a href="lync-server-2013-conferences-table.md">Таблица конференций в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="93242-165"><a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="93242-166">Сохранение информации обо всех конференциях, которые были заархивированы или сведения о которых были зарегистрированы, включая URI конференции, время начала и окончания.</span><span class="sxs-lookup"><span data-stu-id="93242-166">Stores information about all conferences that were archived or whose details were recorded, including ConferenceURI, and start and end time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93242-167"><a href="lync-server-2013-conferencesessiondetails-table.md">Таблица Таблица conferencesessiondetails в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="93242-167"><a href="lync-server-2013-conferencesessiondetails-table.md">ConferenceSessionDetails table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="93242-168">Сохранение информации о каждом сеансе конференц-связи на основе SIP, включая время начала и окончания, идентификатор пользователя, код ответа и идентификатор диагностики для каждого сеанса.</span><span class="sxs-lookup"><span data-stu-id="93242-168">Stores information about every SIP-based conference session, including start and end time, user ID, response code, and diagnostic ID for each session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93242-169"><a href="lync-server-2013-focusjoinsandleaves-table.md">Таблица Таблица focusjoinsandleaves в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="93242-169"><a href="lync-server-2013-focusjoinsandleaves-table.md">FocusJoinsAndLeaves table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="93242-170">Сохранение сведений о присоединениях к конференциям и отключениям от них, включая роли пользователей и версии клиентов.</span><span class="sxs-lookup"><span data-stu-id="93242-170">Stores information about conference joins and leaves, including users’ role and client version.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93242-171"><a href="lync-server-2013-mcujoinsandleaves-table.md">Таблица Таблица mcujoinsandleaves в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="93242-171"><a href="lync-server-2013-mcujoinsandleaves-table.md">McuJoinsAndLeaves table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="93242-172">Сохранение информации о серверах конференц-связи (аудио-видео), задействованных в конференции, и сведений о времени подключения и отключения пользователей.</span><span class="sxs-lookup"><span data-stu-id="93242-172">Stores information about the A/V Conferencing Servers that are involved in a conference and the user join and leave times.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-messages-in-im-conferences"></a><span data-ttu-id="93242-173">Таблицы для сообщений в чат-конференциях</span><span class="sxs-lookup"><span data-stu-id="93242-173">Tables for Messages in IM Conferences</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="93242-174">Table</span><span class="sxs-lookup"><span data-stu-id="93242-174">Table</span></span></th>
<th><span data-ttu-id="93242-175">Описание</span><span class="sxs-lookup"><span data-stu-id="93242-175">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="93242-176"><a href="lync-server-2013-conferencemessagecount-table.md">Таблица Таблица conferencemessagecount в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="93242-176"><a href="lync-server-2013-conferencemessagecount-table.md">ConferenceMessageCount table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="93242-177">Сохранение количества сообщений, которые были отправлены каждым пользователем, для каждой чат-конференции.</span><span class="sxs-lookup"><span data-stu-id="93242-177">For each IM conference, stores the number of messages that were sent by each user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93242-178"><a href="lync-server-2013-imreportsummary-table.md">Таблица Имрепортсуммари в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="93242-178"><a href="lync-server-2013-imreportsummary-table.md">IMReportSummary table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="93242-179">Предоставление общего отчета по сеансам обмена мгновенными сообщениями, которые проводятся в организации.</span><span class="sxs-lookup"><span data-stu-id="93242-179">Provides an overall report on the instant messaging sessions held in an organization.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-peer-to-peer-sessions"></a><span data-ttu-id="93242-180">Таблицы для одноранговых сеансов</span><span class="sxs-lookup"><span data-stu-id="93242-180">Tables for Peer-to-Peer Sessions</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="93242-181">Table</span><span class="sxs-lookup"><span data-stu-id="93242-181">Table</span></span></th>
<th><span data-ttu-id="93242-182">Описание</span><span class="sxs-lookup"><span data-stu-id="93242-182">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="93242-183"><a href="lync-server-2013-sessiondetails-table.md">Таблица SessionDetails в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="93242-183"><a href="lync-server-2013-sessiondetails-table.md">SessionDetails table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="93242-184">Сохранение информацию о каждом одноранговом сеансе, включая время начала и окончания, идентификатор пользователя, код ответа и количество сообщений каждого пользователя.</span><span class="sxs-lookup"><span data-stu-id="93242-184">Stores information about every peer-to-peer session, including start and end time, user ID, response code, and message count for each user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93242-185"><a href="lync-server-2013-filetransfers-table.md">Таблица Таблица filetransfers в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="93242-185"><a href="lync-server-2013-filetransfers-table.md">FileTransfers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="93242-186">Сохранение информации о сеансах передачи файлов, включая имя файла и результат (принято, отклонено или отменено).</span><span class="sxs-lookup"><span data-stu-id="93242-186">Stores information about file transfer sessions, including file name and result (accepted, rejected, or canceled).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93242-187"><a href="lync-server-2013-media-table.md">Таблица мультимедиа в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="93242-187"><a href="lync-server-2013-media-table.md">Media table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="93242-188">Сохранение информации о различных типах носителей, используемых в ходе одноранговых сеансов.</span><span class="sxs-lookup"><span data-stu-id="93242-188">Stores information about the different media types involved in peer-to-peer sessions.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="table-for-voip-call-details"></a><span data-ttu-id="93242-189">Таблица для сведений о вызовах VoIP</span><span class="sxs-lookup"><span data-stu-id="93242-189">Table for VoIP Call Details</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="93242-190">Table</span><span class="sxs-lookup"><span data-stu-id="93242-190">Table</span></span></th>
<th><span data-ttu-id="93242-191">Описание</span><span class="sxs-lookup"><span data-stu-id="93242-191">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="93242-192"><a href="lync-server-2013-voipdetails-table.md">Таблица Таблица voipdetails в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="93242-192"><a href="lync-server-2013-voipdetails-table.md">VoipDetails table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="93242-193">Сохранение информации о вызове, включая идентификатор телефона VoIP, используемый шлюз и сторону, прервавшую вызов, для каждого двустороннего вызова VoIP/ТСОП.</span><span class="sxs-lookup"><span data-stu-id="93242-193">For each two-party VoIP/PSTN call, stores information about the call, such as the phone ID of VoIP phone, gateway used, and which party disconnected.</span></span> <span data-ttu-id="93242-194">Ссылка на <a href="lync-server-2013-sessiondetails-table.md">таблицу SessionDetails в Lync Server 2013</a> для времени начала и окончания вызова и кода ответа.</span><span class="sxs-lookup"><span data-stu-id="93242-194">Refers to the <a href="lync-server-2013-sessiondetails-table.md">SessionDetails table in Lync Server 2013</a> for call start/end times and response code.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="93242-195">Если один участник вызова является пользователем VoIP или при выполнении вызова задействован сервер-посредник, в этой таблице создается соответствующая запись.</span><span class="sxs-lookup"><span data-stu-id="93242-195">If one party on a call is a VoIP user or if a Mediation Server was involved in the call, a record will be created in this table.</span></span> <span data-ttu-id="93242-196">Сведения о вызовах VoIP/VoIP, не связанных с телефонной телефонной сетью общего пользования (PSTN), записываются в <A href="lync-server-2013-sessiondetails-table.md">таблицу SessionDetails в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="93242-196">Information about VoIP/VoIP calls not involving a public switched telephone network (PSTN) phone is captured in the <A href="lync-server-2013-sessiondetails-table.md">SessionDetails table in Lync Server 2013</A>.</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="table-for-e9-1-1-call-auditing"></a><span data-ttu-id="93242-197">Таблица для аудита вызовов E9-1-1</span><span class="sxs-lookup"><span data-stu-id="93242-197">Table for E9-1-1 Call Auditing</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="93242-198">Table</span><span class="sxs-lookup"><span data-stu-id="93242-198">Table</span></span></th>
<th><span data-ttu-id="93242-199">Описание</span><span class="sxs-lookup"><span data-stu-id="93242-199">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="93242-200"><a href="lync-server-2013-locations-table.md">Таблица Locations в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="93242-200"><a href="lync-server-2013-locations-table.md">Locations table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="93242-201">Сохранение информации о каждом экстренном вызове, например вызове Enhanced 9-1-1 (E9-1-1).</span><span class="sxs-lookup"><span data-stu-id="93242-201">For each emergency call, such as an Enhanced 9-1-1 (E9-1-1) call, stores location information about the call.</span></span> <span data-ttu-id="93242-202">Ссылка на <a href="lync-server-2013-sessiondetails-table.md">таблицу SessionDetails в Lync Server 2013</a> для времени начала и окончания вызова и кода ответа.</span><span class="sxs-lookup"><span data-stu-id="93242-202">Refers to the <a href="lync-server-2013-sessiondetails-table.md">SessionDetails table in Lync Server 2013</a> for call start/end times and response code.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="93242-p105">В этой таблице содержится только большой двоичный объект местоположения для вызова E9-1-1. Ссылается на таблицу SessionDetails, в которой указываются другие подробные сведения о вызове.</span><span class="sxs-lookup"><span data-stu-id="93242-p105">This table only contains the location blob for the E9-1-1 call. Refers to the SessionDetails table for other detailed information about the call.</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-troubleshooting"></a><span data-ttu-id="93242-205">Таблицы для устранения неполадок</span><span class="sxs-lookup"><span data-stu-id="93242-205">Tables for Troubleshooting</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="93242-206">Table</span><span class="sxs-lookup"><span data-stu-id="93242-206">Table</span></span></th>
<th><span data-ttu-id="93242-207">Описание</span><span class="sxs-lookup"><span data-stu-id="93242-207">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="93242-208"><a href="lync-server-2013-application-table.md">Таблица Application в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="93242-208"><a href="lync-server-2013-application-table.md">Application table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="93242-209">Хранит сведения о различных процессах в Lync Server 2013, участвующих в маршрутизации и подключениях.</span><span class="sxs-lookup"><span data-stu-id="93242-209">Stores information about various processes within Lync Server 2013 that are involved in routing and connections.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93242-210"><a href="lync-server-2013-calltype-table.md">Таблица CallType в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="93242-210"><a href="lync-server-2013-calltype-table.md">CallType table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="93242-211">Сохранение информации о типах вызовов, например «аудио», «чат», «аудио и видео» и «общий доступ к приложениям».</span><span class="sxs-lookup"><span data-stu-id="93242-211">Stores information about types of the call, such as, “audio”, “Instant Messaging”, “audio and video” and “application sharing”.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93242-212"><a href="lync-server-2013-errorcategory-table.md">Таблица ErrorCategory в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="93242-212"><a href="lync-server-2013-errorcategory-table.md">ErrorCategory table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="93242-213">Хранит понятное имя каждого диагностической классификации Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="93242-213">Stores the friendly name for each Microsoft Lync Server 2013 diagnostic classification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93242-214"><a href="lync-server-2013-errordef-table.md">Таблица Таблица errordef в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="93242-214"><a href="lync-server-2013-errordef-table.md">ErrorDef table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="93242-215">Сохранение информации о типах ошибок и их определениях.</span><span class="sxs-lookup"><span data-stu-id="93242-215">Stores information about types of errors and their definitions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93242-216"><a href="lync-server-2013-errorreport-table.md">Таблица ErrorReport в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="93242-216"><a href="lync-server-2013-errorreport-table.md">ErrorReport table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="93242-217">Сохранение информации о возникших ошибках.</span><span class="sxs-lookup"><span data-stu-id="93242-217">Stores information about errors that have occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93242-218"><a href="lync-server-2013-progressreport-table.md">Таблица Таблица progressreport в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="93242-218"><a href="lync-server-2013-progressreport-table.md">ProgressReport table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="93242-219">Хранит сведения о ходе выполнения различных действий, связанных с процессами Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="93242-219">Stores information about the progress reports of various steps involved in Lync Server 2013 processes.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="93242-220">Таблицы, приведенные в следующем списке, используются внутренними средствами Lync Server.</span><span class="sxs-lookup"><span data-stu-id="93242-220">The tables in the following list are used internally by Lync Server.</span></span> <span data-ttu-id="93242-221">Сведения о них не приведены в данном документе.</span><span class="sxs-lookup"><span data-stu-id="93242-221">Their details are not described in this document.</span></span>

</div>

<div>

## <a name="tables-for-internal-use-by-lync-server"></a><span data-ttu-id="93242-222">Таблицы для внутреннего использования сервером Lync Server</span><span class="sxs-lookup"><span data-stu-id="93242-222">Tables for Internal Use by Lync Server</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="93242-223">Table</span><span class="sxs-lookup"><span data-stu-id="93242-223">Table</span></span></th>
<th><span data-ttu-id="93242-224">Описание</span><span class="sxs-lookup"><span data-stu-id="93242-224">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="93242-225"><strong>дбконфигдатетиме</strong></span><span class="sxs-lookup"><span data-stu-id="93242-225"><strong>DbConfigDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="93242-226">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="93242-226">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93242-227"><strong>дбконфигинт</strong></span><span class="sxs-lookup"><span data-stu-id="93242-227"><strong>DbConfigInt</strong></span></span></p></td>
<td><p><span data-ttu-id="93242-228">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="93242-228">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93242-229"><strong>дберрормессаже</strong></span><span class="sxs-lookup"><span data-stu-id="93242-229"><strong>DbErrorMessage</strong></span></span></p></td>
<td><p><span data-ttu-id="93242-230">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="93242-230">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93242-231"><strong>FrontEnd Table</strong></span><span class="sxs-lookup"><span data-stu-id="93242-231"><strong>FrontEnd Table</strong></span></span></p></td>
<td><p><span data-ttu-id="93242-232">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="93242-232">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93242-233"><strong>MSMQProcessing Table</strong></span><span class="sxs-lookup"><span data-stu-id="93242-233"><strong>MSMQProcessing Table</strong></span></span></p></td>
<td><p><span data-ttu-id="93242-234">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="93242-234">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93242-235"><strong>суммаритаблеконфигуратион</strong></span><span class="sxs-lookup"><span data-stu-id="93242-235"><strong>SummaryTableConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="93242-236">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="93242-236">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93242-237"><strong>Syndicators Table</strong></span><span class="sxs-lookup"><span data-stu-id="93242-237"><strong>Syndicators Table</strong></span></span></p></td>
<td><p><span data-ttu-id="93242-238">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="93242-238">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93242-239"><strong>SyndicatorsTenantMap Table</strong></span><span class="sxs-lookup"><span data-stu-id="93242-239"><strong>SyndicatorsTenantMap Table</strong></span></span></p></td>
<td><p><span data-ttu-id="93242-240">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="93242-240">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93242-241"><strong>Task Table</strong></span><span class="sxs-lookup"><span data-stu-id="93242-241"><strong>Task Table</strong></span></span></p></td>
<td><p><span data-ttu-id="93242-242">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="93242-242">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93242-243"><strong>усерстатистикс</strong></span><span class="sxs-lookup"><span data-stu-id="93242-243"><strong>UserStatistics</strong></span></span></p></td>
<td><p><span data-ttu-id="93242-244">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="93242-244">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93242-245"><strong>UsageSummary_UQ</strong></span><span class="sxs-lookup"><span data-stu-id="93242-245"><strong>UsageSummary_UQ</strong></span></span></p></td>
<td><p><span data-ttu-id="93242-246">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="93242-246">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93242-247"><strong>усажесуммари</strong></span><span class="sxs-lookup"><span data-stu-id="93242-247"><strong>UsageSummary</strong></span></span></p></td>
<td><p><span data-ttu-id="93242-248">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="93242-248">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93242-249"><strong>дайлигхтсавингеарс</strong></span><span class="sxs-lookup"><span data-stu-id="93242-249"><strong>DaylightSavingYears</strong></span></span></p></td>
<td><p><span data-ttu-id="93242-250">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="93242-250">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93242-251"><strong>тимезонеконфигуратион</strong></span><span class="sxs-lookup"><span data-stu-id="93242-251"><strong>TimeZoneConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="93242-252">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="93242-252">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93242-253"><strong>TimeZones</strong></span><span class="sxs-lookup"><span data-stu-id="93242-253"><strong>TimeZones</strong></span></span></p></td>
<td><p><span data-ttu-id="93242-254">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="93242-254">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93242-255"><strong>FailureSummary_UQ</strong></span><span class="sxs-lookup"><span data-stu-id="93242-255"><strong>FailureSummary_UQ</strong></span></span></p></td>
<td><p><span data-ttu-id="93242-256">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="93242-256">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93242-257"><strong>фаилуресуммари</strong></span><span class="sxs-lookup"><span data-stu-id="93242-257"><strong>FailureSummary</strong></span></span></p></td>
<td><p><span data-ttu-id="93242-258">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="93242-258">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93242-259"><strong>серверсуммари</strong></span><span class="sxs-lookup"><span data-stu-id="93242-259"><strong>ServerSummary</strong></span></span></p></td>
<td><p><span data-ttu-id="93242-260">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="93242-260">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93242-261"><strong>мсдиагметадата</strong></span><span class="sxs-lookup"><span data-stu-id="93242-261"><strong>MsDiagMetaData</strong></span></span></p></td>
<td><p><span data-ttu-id="93242-262">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="93242-262">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

