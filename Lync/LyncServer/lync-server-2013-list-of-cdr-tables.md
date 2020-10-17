---
title: 'Lync Server 2013: список таблиц CDR'
description: 'Lync Server 2013: список таблиц CDR.'
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
ms.openlocfilehash: 21d0f683ffeb0f5f1cbba5db4c45d248aa14e8e4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558705"
---
# <a name="list-of-cdr-tables-in-lync-server-2013"></a><span data-ttu-id="74ceb-103">Список таблиц CDR в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="74ceb-103">List of CDR tables in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="74ceb-104">_**Последнее изменение темы:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="74ceb-104">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="74ceb-105">Схема базы данных регистрации вызовов (call detail recording — CDR) состоит из следующих таблиц.</span><span class="sxs-lookup"><span data-stu-id="74ceb-105">The call detail recording (CDR) database schema consists of the following tables.</span></span>

<div>

## <a name="static-tables"></a><span data-ttu-id="74ceb-106">Статические таблицы</span><span class="sxs-lookup"><span data-stu-id="74ceb-106">Static Tables</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="74ceb-107">Table</span><span class="sxs-lookup"><span data-stu-id="74ceb-107">Table</span></span></th>
<th><span data-ttu-id="74ceb-108">Описание</span><span class="sxs-lookup"><span data-stu-id="74ceb-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="74ceb-109"><a href="lync-server-2013-callpriorities-table.md">Таблица Таблица callpriorities в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="74ceb-109"><a href="lync-server-2013-callpriorities-table.md">CallPriorities table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="74ceb-110">Сохранение списка возможных приоритетов вызовов (включая аварийные, срочные, обычные, несрочные и т. д.).</span><span class="sxs-lookup"><span data-stu-id="74ceb-110">Stores the list of possible call priorities, such as emergency, urgent, normal, non-urgent, and more.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74ceb-111"><a href="lync-server-2013-conferencejointimethresholds-table.md">Таблица Таблица conferencejointimethresholds в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="74ceb-111"><a href="lync-server-2013-conferencejointimethresholds-table.md">ConferenceJoinTimeThresholds table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="74ceb-112">Сохранение границ классификации, используемых в отчете со сводными данными по времени подсоединения к конференции.</span><span class="sxs-lookup"><span data-stu-id="74ceb-112">Stores the classification boundaries used by the Conference Join Time Summary Report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74ceb-113"><a href="lync-server-2013-deregistertype-table.md">Таблица Таблица deregistertype в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="74ceb-113"><a href="lync-server-2013-deregistertype-table.md">DeRegisterType table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="74ceb-114">Хранит список возможных причин отмены регистрации пользователей, таких как &quot; инициирование клиента, &quot; &quot; срок действия регистрации, &quot; &quot; сбой клиента &quot; и многое другое.</span><span class="sxs-lookup"><span data-stu-id="74ceb-114">Stores the list of possible user de-register reasons, such as &quot;client initiated,&quot; &quot;registration expired,&quot; &quot;client crash,&quot; and more.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74ceb-115"><a href="lync-server-2013-medialist-table.md">Таблица Таблица medialist в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="74ceb-115"><a href="lync-server-2013-medialist-table.md">MediaList table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="74ceb-116">Сохранение списка типов мультимедиа, которые могут создавать записи в базе данных (например, чат, аудио, видео и передача файлов).</span><span class="sxs-lookup"><span data-stu-id="74ceb-116">Stores the list of media types that can generate entries in the database (for example, IM, audio, video, and file transfer).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74ceb-117"><a href="lync-server-2013-purgesettings-table.md">Таблица Таблица purgesettings в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="74ceb-117"><a href="lync-server-2013-purgesettings-table.md">PurgeSettings table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="74ceb-118">Сохранение информации, определяющей, следует ли (и когда) автоматически удалять устаревшие записи о вызовах из базы данных CDR.</span><span class="sxs-lookup"><span data-stu-id="74ceb-118">Stores information that specifies if (and when) outdated call detail records will automatically be deleted from the CDR database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74ceb-119"><a href="lync-server-2013-roles-table.md">Таблица Roles в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="74ceb-119"><a href="lync-server-2013-roles-table.md">Roles table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="74ceb-120">Сохранение списка возможных ролей участников конференции (например, участник и докладчик).</span><span class="sxs-lookup"><span data-stu-id="74ceb-120">Stores the list of possible conference roles (for example, attendee and presenter).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74ceb-121"><a href="lync-server-2013-sipresponsemetadata-table.md">Таблица Сипреспонсеметадата в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="74ceb-121"><a href="lync-server-2013-sipresponsemetadata-table.md">SIPResponseMetaData table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="74ceb-122">Сохранение списка кодов ответов SIP, классификации и определения каждого из этих кодов.</span><span class="sxs-lookup"><span data-stu-id="74ceb-122">Stores a list of SIP response codes and the classification and definition of each of those codes.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="supporting-tables"></a><span data-ttu-id="74ceb-123">Вспомогательные таблицы</span><span class="sxs-lookup"><span data-stu-id="74ceb-123">Supporting Tables</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="74ceb-124">Table</span><span class="sxs-lookup"><span data-stu-id="74ceb-124">Table</span></span></th>
<th><span data-ttu-id="74ceb-125">Описание</span><span class="sxs-lookup"><span data-stu-id="74ceb-125">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="74ceb-126"><a href="lync-server-2013-clientversions-table.md">Таблица Таблица clientversions в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="74ceb-126"><a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="74ceb-127">Сохранение клиентов (включая тип клиента и номер версии) каждого клиента, участвующего в вызове, с указанием информации, собранной в этой базе данных.</span><span class="sxs-lookup"><span data-stu-id="74ceb-127">Stores the clients (both client type and version number) of each client involved in a call with information captured in this database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74ceb-128"><a href="lync-server-2013-conferenceuris-table.md">Таблица Таблица conferenceuris в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="74ceb-128"><a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="74ceb-129">Сохранение списка кодов URI конференций, которые используются в вызовах, связанных с конференцией.</span><span class="sxs-lookup"><span data-stu-id="74ceb-129">Stores a list of ConferenceURIs that are used in conference related calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74ceb-130"><a href="lync-server-2013-contenttypes-table.md">Таблица ContentTypes в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="74ceb-130"><a href="lync-server-2013-contenttypes-table.md">ContentTypes table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="74ceb-131">Сохранение списка типов содержимого SIP (Session Initiation Protocol), которые используются и в одноранговых вызовах, и в конференц-вызовах.</span><span class="sxs-lookup"><span data-stu-id="74ceb-131">Stores a list of Session Initiation Protocol (SIP) content types that are used in both peer-to-peer calls and conference calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74ceb-132"><a href="lync-server-2013-devices-table.md">Таблица Devices в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="74ceb-132"><a href="lync-server-2013-devices-table.md">Devices table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="74ceb-133">Сохранение списка устройств, включая производителя, версию оборудования и MAC-адрес.</span><span class="sxs-lookup"><span data-stu-id="74ceb-133">Stores a list of devices, including their manufacturer, hardware version, and MAC address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74ceb-134"><a href="lync-server-2013-dialogs-table.md">Таблица диалогов в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="74ceb-134"><a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="74ceb-135">Сохранение идентификаторов диалогов для каждого сеанса в базе данных.</span><span class="sxs-lookup"><span data-stu-id="74ceb-135">Stores information about the Dialog ID for each session in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74ceb-136"><a href="lync-server-2013-edgeservers-table.md">Таблица Таблица edgeservers в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="74ceb-136"><a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="74ceb-137">Сохранение списка пограничных серверов, которые используются для внешних вызовов.</span><span class="sxs-lookup"><span data-stu-id="74ceb-137">Stores a list of Edge Servers that are used for external calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74ceb-138"><a href="lync-server-2013-gateways-table.md">Таблица Gateways в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="74ceb-138"><a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="74ceb-139">Сохранение списка шлюзов, которые используются для вызовов по протоколу VoIP.</span><span class="sxs-lookup"><span data-stu-id="74ceb-139">Stores a list of Gateways that are used for Voice over Internet Protocol (VoIP) calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74ceb-140"><a href="lync-server-2013-hardwareversions-table.md">Таблица Таблица hardwareversions в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="74ceb-140"><a href="lync-server-2013-hardwareversions-table.md">HardwareVersions table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="74ceb-141">Сохранение списка аппаратных версий устройств (стационарный телефон).</span><span class="sxs-lookup"><span data-stu-id="74ceb-141">Stores a list of hardware versions of devices (desk phone).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74ceb-142"><a href="lync-server-2013-manufacturers-table.md">Таблица производителей в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="74ceb-142"><a href="lync-server-2013-manufacturers-table.md">Manufacturers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="74ceb-143">Сохранение списка производителей устройств (стационарный телефон).</span><span class="sxs-lookup"><span data-stu-id="74ceb-143">Stores a list of manufacturers of devices (desk phone).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74ceb-144"><a href="lync-server-2013-mcus-table.md">Таблица MCUs в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="74ceb-144"><a href="lync-server-2013-mcus-table.md">Mcus table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="74ceb-145">Сохранение информации о различных серверах конференц-связи (аудио-видео) и их кодов URI.</span><span class="sxs-lookup"><span data-stu-id="74ceb-145">Stores information about the various A/V Conferencing Servers and their URIs.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74ceb-146"><a href="lync-server-2013-mediationservers-table.md">Таблица Таблица mediationservers в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="74ceb-146"><a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="74ceb-147">Сохранение списка серверов-посредников, используемых для выполнения вызовов по протоколу VoIP.</span><span class="sxs-lookup"><span data-stu-id="74ceb-147">Stores a list of Mediation Servers that are used for VoIP calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74ceb-148"><a href="lync-server-2013-phones-table.md">Таблица phones в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="74ceb-148"><a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="74ceb-149">Сохранение всех номеров телефона, использованных для выполнения вызовов по протоколу VoIP, которые были архивированы или сведения о которых были зарегистрированы.</span><span class="sxs-lookup"><span data-stu-id="74ceb-149">Stores all the phone numbers used in VoIP calls that were archived or whose call details were recorded.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74ceb-150"><a href="lync-server-2013-pools-table.md">Таблица Pools в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="74ceb-150"><a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="74ceb-151">Сохранение имен пула, в котором записываются мгновенные сообщения.</span><span class="sxs-lookup"><span data-stu-id="74ceb-151">Stores the names of the pool on which IM messages are captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74ceb-152"><a href="lync-server-2013-servers-table.md">Таблица Servers в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="74ceb-152"><a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="74ceb-153">Сохранение имен серверов, участвующих в вызовах.</span><span class="sxs-lookup"><span data-stu-id="74ceb-153">Stores the name of servers involved in calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74ceb-154"><a href="lync-server-2013-tenants-table.md">Таблица клиентов в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="74ceb-154"><a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="74ceb-155">Сохранение клиентов, поддерживаемых текущим развертыванием.</span><span class="sxs-lookup"><span data-stu-id="74ceb-155">Stores the tenants supported by current deployment.</span></span> <span data-ttu-id="74ceb-156">Существует ряд встроенных клиентов для корпоративных пользователей, федеративных пользователей, пользователей с подключением к общедоступным системам обмена мгновенными сообщениями и анонимных пользователей.</span><span class="sxs-lookup"><span data-stu-id="74ceb-156">There some build-in tenants for Enterprise user, Federated User, public IM connectivity user, and Anonymous users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74ceb-157"><a href="lync-server-2013-useragentdef-table.md">Таблица Таблица useragentdef в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="74ceb-157"><a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="74ceb-158">Привязка идентификаторов агента пользователя к описательным именам агента.</span><span class="sxs-lookup"><span data-stu-id="74ceb-158">Maps user agent identifiers to the agent’s descriptive names.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74ceb-159"><a href="lync-server-2013-users-table.md">Таблица Users в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="74ceb-159"><a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="74ceb-160">Сохранение кодов URI пользователей, которые участвовали в сеансах, зарегистрированных или заархивированных в этой базе данных.</span><span class="sxs-lookup"><span data-stu-id="74ceb-160">Stores the user URIs of users who have participated in sessions recorded or archived in this database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74ceb-161"><a href="lync-server-2013-userstatistics-table.md">Таблица Усерстатистикс в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="74ceb-161"><a href="lync-server-2013-userstatistics-table.md">UserStatistics table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="74ceb-162">Сохранение сведений об использовании системы отдельным пользователем.</span><span class="sxs-lookup"><span data-stu-id="74ceb-162">Stores information about an individual user’s usage of the system.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-specific-to-conference-cdr-records"></a><span data-ttu-id="74ceb-163">Записи, относящиеся к конкретным записям CDR конференции</span><span class="sxs-lookup"><span data-stu-id="74ceb-163">Tables Specific to Conference CDR Records</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="74ceb-164">Table</span><span class="sxs-lookup"><span data-stu-id="74ceb-164">Table</span></span></th>
<th><span data-ttu-id="74ceb-165">Описание</span><span class="sxs-lookup"><span data-stu-id="74ceb-165">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="74ceb-166"><a href="lync-server-2013-conferences-table.md">Таблица конференций в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="74ceb-166"><a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="74ceb-167">Сохранение информации обо всех конференциях, которые были заархивированы или сведения о которых были зарегистрированы, включая URI конференции, время начала и окончания.</span><span class="sxs-lookup"><span data-stu-id="74ceb-167">Stores information about all conferences that were archived or whose details were recorded, including ConferenceURI, and start and end time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74ceb-168"><a href="lync-server-2013-conferencesessiondetails-table.md">Таблица Таблица conferencesessiondetails в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="74ceb-168"><a href="lync-server-2013-conferencesessiondetails-table.md">ConferenceSessionDetails table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="74ceb-169">Сохранение информации о каждом сеансе конференц-связи на основе SIP, включая время начала и окончания, идентификатор пользователя, код ответа и идентификатор диагностики для каждого сеанса.</span><span class="sxs-lookup"><span data-stu-id="74ceb-169">Stores information about every SIP-based conference session, including start and end time, user ID, response code, and diagnostic ID for each session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74ceb-170"><a href="lync-server-2013-focusjoinsandleaves-table.md">Таблица Таблица focusjoinsandleaves в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="74ceb-170"><a href="lync-server-2013-focusjoinsandleaves-table.md">FocusJoinsAndLeaves table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="74ceb-171">Сохранение сведений о присоединениях к конференциям и отключениям от них, включая роли пользователей и версии клиентов.</span><span class="sxs-lookup"><span data-stu-id="74ceb-171">Stores information about conference joins and leaves, including users’ role and client version.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74ceb-172"><a href="lync-server-2013-mcujoinsandleaves-table.md">Таблица Таблица mcujoinsandleaves в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="74ceb-172"><a href="lync-server-2013-mcujoinsandleaves-table.md">McuJoinsAndLeaves table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="74ceb-173">Сохранение информации о серверах конференц-связи (аудио-видео), задействованных в конференции, и сведений о времени подключения и отключения пользователей.</span><span class="sxs-lookup"><span data-stu-id="74ceb-173">Stores information about the A/V Conferencing Servers that are involved in a conference and the user join and leave times.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-messages-in-im-conferences"></a><span data-ttu-id="74ceb-174">Таблицы для сообщений в чат-конференциях</span><span class="sxs-lookup"><span data-stu-id="74ceb-174">Tables for Messages in IM Conferences</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="74ceb-175">Table</span><span class="sxs-lookup"><span data-stu-id="74ceb-175">Table</span></span></th>
<th><span data-ttu-id="74ceb-176">Описание</span><span class="sxs-lookup"><span data-stu-id="74ceb-176">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="74ceb-177"><a href="lync-server-2013-conferencemessagecount-table.md">Таблица Таблица conferencemessagecount в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="74ceb-177"><a href="lync-server-2013-conferencemessagecount-table.md">ConferenceMessageCount table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="74ceb-178">Сохранение количества сообщений, которые были отправлены каждым пользователем, для каждой чат-конференции.</span><span class="sxs-lookup"><span data-stu-id="74ceb-178">For each IM conference, stores the number of messages that were sent by each user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74ceb-179"><a href="lync-server-2013-imreportsummary-table.md">Таблица Имрепортсуммари в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="74ceb-179"><a href="lync-server-2013-imreportsummary-table.md">IMReportSummary table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="74ceb-180">Предоставление общего отчета по сеансам обмена мгновенными сообщениями, которые проводятся в организации.</span><span class="sxs-lookup"><span data-stu-id="74ceb-180">Provides an overall report on the instant messaging sessions held in an organization.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-peer-to-peer-sessions"></a><span data-ttu-id="74ceb-181">Таблицы для одноранговых сеансов</span><span class="sxs-lookup"><span data-stu-id="74ceb-181">Tables for Peer-to-Peer Sessions</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="74ceb-182">Table</span><span class="sxs-lookup"><span data-stu-id="74ceb-182">Table</span></span></th>
<th><span data-ttu-id="74ceb-183">Описание</span><span class="sxs-lookup"><span data-stu-id="74ceb-183">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="74ceb-184"><a href="lync-server-2013-sessiondetails-table.md">Таблица SessionDetails в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="74ceb-184"><a href="lync-server-2013-sessiondetails-table.md">SessionDetails table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="74ceb-185">Сохранение информацию о каждом одноранговом сеансе, включая время начала и окончания, идентификатор пользователя, код ответа и количество сообщений каждого пользователя.</span><span class="sxs-lookup"><span data-stu-id="74ceb-185">Stores information about every peer-to-peer session, including start and end time, user ID, response code, and message count for each user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74ceb-186"><a href="lync-server-2013-filetransfers-table.md">Таблица Таблица filetransfers в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="74ceb-186"><a href="lync-server-2013-filetransfers-table.md">FileTransfers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="74ceb-187">Сохранение информации о сеансах передачи файлов, включая имя файла и результат (принято, отклонено или отменено).</span><span class="sxs-lookup"><span data-stu-id="74ceb-187">Stores information about file transfer sessions, including file name and result (accepted, rejected, or canceled).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74ceb-188"><a href="lync-server-2013-media-table.md">Таблица мультимедиа в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="74ceb-188"><a href="lync-server-2013-media-table.md">Media table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="74ceb-189">Сохранение информации о различных типах носителей, используемых в ходе одноранговых сеансов.</span><span class="sxs-lookup"><span data-stu-id="74ceb-189">Stores information about the different media types involved in peer-to-peer sessions.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="table-for-voip-call-details"></a><span data-ttu-id="74ceb-190">Таблица для сведений о вызовах VoIP</span><span class="sxs-lookup"><span data-stu-id="74ceb-190">Table for VoIP Call Details</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="74ceb-191">Table</span><span class="sxs-lookup"><span data-stu-id="74ceb-191">Table</span></span></th>
<th><span data-ttu-id="74ceb-192">Описание</span><span class="sxs-lookup"><span data-stu-id="74ceb-192">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="74ceb-193"><a href="lync-server-2013-voipdetails-table.md">Таблица Таблица voipdetails в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="74ceb-193"><a href="lync-server-2013-voipdetails-table.md">VoipDetails table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="74ceb-194">Сохранение информации о вызове, включая идентификатор телефона VoIP, используемый шлюз и сторону, прервавшую вызов, для каждого двустороннего вызова VoIP/ТСОП.</span><span class="sxs-lookup"><span data-stu-id="74ceb-194">For each two-party VoIP/PSTN call, stores information about the call, such as the phone ID of VoIP phone, gateway used, and which party disconnected.</span></span> <span data-ttu-id="74ceb-195">Ссылка на <a href="lync-server-2013-sessiondetails-table.md">таблицу SessionDetails в Lync Server 2013</a> для времени начала и окончания вызова и кода ответа.</span><span class="sxs-lookup"><span data-stu-id="74ceb-195">Refers to the <a href="lync-server-2013-sessiondetails-table.md">SessionDetails table in Lync Server 2013</a> for call start/end times and response code.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="74ceb-196">Если один участник вызова является пользователем VoIP или при выполнении вызова задействован сервер-посредник, в этой таблице создается соответствующая запись.</span><span class="sxs-lookup"><span data-stu-id="74ceb-196">If one party on a call is a VoIP user or if a Mediation Server was involved in the call, a record will be created in this table.</span></span> <span data-ttu-id="74ceb-197">Сведения о вызовах VoIP/VoIP, не связанных с телефонной телефонной сетью общего пользования (PSTN), записываются в <A href="lync-server-2013-sessiondetails-table.md">таблицу SessionDetails в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="74ceb-197">Information about VoIP/VoIP calls not involving a public switched telephone network (PSTN) phone is captured in the <A href="lync-server-2013-sessiondetails-table.md">SessionDetails table in Lync Server 2013</A>.</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="table-for-e9-1-1-call-auditing"></a><span data-ttu-id="74ceb-198">Таблица для аудита вызовов E9-1-1</span><span class="sxs-lookup"><span data-stu-id="74ceb-198">Table for E9-1-1 Call Auditing</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="74ceb-199">Table</span><span class="sxs-lookup"><span data-stu-id="74ceb-199">Table</span></span></th>
<th><span data-ttu-id="74ceb-200">Описание</span><span class="sxs-lookup"><span data-stu-id="74ceb-200">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="74ceb-201"><a href="lync-server-2013-locations-table.md">Таблица Locations в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="74ceb-201"><a href="lync-server-2013-locations-table.md">Locations table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="74ceb-202">Сохранение информации о каждом экстренном вызове, например вызове Enhanced 9-1-1 (E9-1-1).</span><span class="sxs-lookup"><span data-stu-id="74ceb-202">For each emergency call, such as an Enhanced 9-1-1 (E9-1-1) call, stores location information about the call.</span></span> <span data-ttu-id="74ceb-203">Ссылка на <a href="lync-server-2013-sessiondetails-table.md">таблицу SessionDetails в Lync Server 2013</a> для времени начала и окончания вызова и кода ответа.</span><span class="sxs-lookup"><span data-stu-id="74ceb-203">Refers to the <a href="lync-server-2013-sessiondetails-table.md">SessionDetails table in Lync Server 2013</a> for call start/end times and response code.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="74ceb-p105">В этой таблице содержится только большой двоичный объект местоположения для вызова E9-1-1. Ссылается на таблицу SessionDetails, в которой указываются другие подробные сведения о вызове.</span><span class="sxs-lookup"><span data-stu-id="74ceb-p105">This table only contains the location blob for the E9-1-1 call. Refers to the SessionDetails table for other detailed information about the call.</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-troubleshooting"></a><span data-ttu-id="74ceb-206">Таблицы для устранения неполадок</span><span class="sxs-lookup"><span data-stu-id="74ceb-206">Tables for Troubleshooting</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="74ceb-207">Table</span><span class="sxs-lookup"><span data-stu-id="74ceb-207">Table</span></span></th>
<th><span data-ttu-id="74ceb-208">Описание</span><span class="sxs-lookup"><span data-stu-id="74ceb-208">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="74ceb-209"><a href="lync-server-2013-application-table.md">Таблица Application в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="74ceb-209"><a href="lync-server-2013-application-table.md">Application table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="74ceb-210">Хранит сведения о различных процессах в Lync Server 2013, участвующих в маршрутизации и подключениях.</span><span class="sxs-lookup"><span data-stu-id="74ceb-210">Stores information about various processes within Lync Server 2013 that are involved in routing and connections.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74ceb-211"><a href="lync-server-2013-calltype-table.md">Таблица CallType в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="74ceb-211"><a href="lync-server-2013-calltype-table.md">CallType table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="74ceb-212">Сохранение информации о типах вызовов, например «аудио», «чат», «аудио и видео» и «общий доступ к приложениям».</span><span class="sxs-lookup"><span data-stu-id="74ceb-212">Stores information about types of the call, such as, “audio”, “Instant Messaging”, “audio and video” and “application sharing”.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74ceb-213"><a href="lync-server-2013-errorcategory-table.md">Таблица ErrorCategory в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="74ceb-213"><a href="lync-server-2013-errorcategory-table.md">ErrorCategory table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="74ceb-214">Хранит понятное имя каждого диагностической классификации Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="74ceb-214">Stores the friendly name for each Microsoft Lync Server 2013 diagnostic classification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74ceb-215"><a href="lync-server-2013-errordef-table.md">Таблица Таблица errordef в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="74ceb-215"><a href="lync-server-2013-errordef-table.md">ErrorDef table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="74ceb-216">Сохранение информации о типах ошибок и их определениях.</span><span class="sxs-lookup"><span data-stu-id="74ceb-216">Stores information about types of errors and their definitions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74ceb-217"><a href="lync-server-2013-errorreport-table.md">Таблица ErrorReport в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="74ceb-217"><a href="lync-server-2013-errorreport-table.md">ErrorReport table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="74ceb-218">Сохранение информации о возникших ошибках.</span><span class="sxs-lookup"><span data-stu-id="74ceb-218">Stores information about errors that have occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74ceb-219"><a href="lync-server-2013-progressreport-table.md">Таблица Таблица progressreport в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="74ceb-219"><a href="lync-server-2013-progressreport-table.md">ProgressReport table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="74ceb-220">Хранит сведения о ходе выполнения различных действий, связанных с процессами Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="74ceb-220">Stores information about the progress reports of various steps involved in Lync Server 2013 processes.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="74ceb-221">Таблицы, приведенные в следующем списке, используются внутренними средствами Lync Server.</span><span class="sxs-lookup"><span data-stu-id="74ceb-221">The tables in the following list are used internally by Lync Server.</span></span> <span data-ttu-id="74ceb-222">Сведения о них не приведены в данном документе.</span><span class="sxs-lookup"><span data-stu-id="74ceb-222">Their details are not described in this document.</span></span>

</div>

<div>

## <a name="tables-for-internal-use-by-lync-server"></a><span data-ttu-id="74ceb-223">Таблицы для внутреннего использования сервером Lync Server</span><span class="sxs-lookup"><span data-stu-id="74ceb-223">Tables for Internal Use by Lync Server</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="74ceb-224">Table</span><span class="sxs-lookup"><span data-stu-id="74ceb-224">Table</span></span></th>
<th><span data-ttu-id="74ceb-225">Описание</span><span class="sxs-lookup"><span data-stu-id="74ceb-225">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="74ceb-226"><strong>дбконфигдатетиме</strong></span><span class="sxs-lookup"><span data-stu-id="74ceb-226"><strong>DbConfigDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="74ceb-227">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="74ceb-227">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74ceb-228"><strong>дбконфигинт</strong></span><span class="sxs-lookup"><span data-stu-id="74ceb-228"><strong>DbConfigInt</strong></span></span></p></td>
<td><p><span data-ttu-id="74ceb-229">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="74ceb-229">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74ceb-230"><strong>дберрормессаже</strong></span><span class="sxs-lookup"><span data-stu-id="74ceb-230"><strong>DbErrorMessage</strong></span></span></p></td>
<td><p><span data-ttu-id="74ceb-231">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="74ceb-231">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74ceb-232"><strong>FrontEnd Table</strong></span><span class="sxs-lookup"><span data-stu-id="74ceb-232"><strong>FrontEnd Table</strong></span></span></p></td>
<td><p><span data-ttu-id="74ceb-233">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="74ceb-233">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74ceb-234"><strong>MSMQProcessing Table</strong></span><span class="sxs-lookup"><span data-stu-id="74ceb-234"><strong>MSMQProcessing Table</strong></span></span></p></td>
<td><p><span data-ttu-id="74ceb-235">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="74ceb-235">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74ceb-236"><strong>суммаритаблеконфигуратион</strong></span><span class="sxs-lookup"><span data-stu-id="74ceb-236"><strong>SummaryTableConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="74ceb-237">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="74ceb-237">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74ceb-238"><strong>Syndicators Table</strong></span><span class="sxs-lookup"><span data-stu-id="74ceb-238"><strong>Syndicators Table</strong></span></span></p></td>
<td><p><span data-ttu-id="74ceb-239">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="74ceb-239">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74ceb-240"><strong>SyndicatorsTenantMap Table</strong></span><span class="sxs-lookup"><span data-stu-id="74ceb-240"><strong>SyndicatorsTenantMap Table</strong></span></span></p></td>
<td><p><span data-ttu-id="74ceb-241">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="74ceb-241">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74ceb-242"><strong>Task Table</strong></span><span class="sxs-lookup"><span data-stu-id="74ceb-242"><strong>Task Table</strong></span></span></p></td>
<td><p><span data-ttu-id="74ceb-243">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="74ceb-243">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74ceb-244"><strong>UserStatistics</strong></span><span class="sxs-lookup"><span data-stu-id="74ceb-244"><strong>UserStatistics</strong></span></span></p></td>
<td><p><span data-ttu-id="74ceb-245">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="74ceb-245">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74ceb-246"><strong>UsageSummary_UQ</strong></span><span class="sxs-lookup"><span data-stu-id="74ceb-246"><strong>UsageSummary_UQ</strong></span></span></p></td>
<td><p><span data-ttu-id="74ceb-247">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="74ceb-247">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74ceb-248"><strong>усажесуммари</strong></span><span class="sxs-lookup"><span data-stu-id="74ceb-248"><strong>UsageSummary</strong></span></span></p></td>
<td><p><span data-ttu-id="74ceb-249">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="74ceb-249">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74ceb-250"><strong>дайлигхтсавингеарс</strong></span><span class="sxs-lookup"><span data-stu-id="74ceb-250"><strong>DaylightSavingYears</strong></span></span></p></td>
<td><p><span data-ttu-id="74ceb-251">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="74ceb-251">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74ceb-252"><strong>тимезонеконфигуратион</strong></span><span class="sxs-lookup"><span data-stu-id="74ceb-252"><strong>TimeZoneConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="74ceb-253">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="74ceb-253">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74ceb-254"><strong>TimeZones</strong></span><span class="sxs-lookup"><span data-stu-id="74ceb-254"><strong>TimeZones</strong></span></span></p></td>
<td><p><span data-ttu-id="74ceb-255">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="74ceb-255">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74ceb-256"><strong>FailureSummary_UQ</strong></span><span class="sxs-lookup"><span data-stu-id="74ceb-256"><strong>FailureSummary_UQ</strong></span></span></p></td>
<td><p><span data-ttu-id="74ceb-257">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="74ceb-257">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74ceb-258"><strong>фаилуресуммари</strong></span><span class="sxs-lookup"><span data-stu-id="74ceb-258"><strong>FailureSummary</strong></span></span></p></td>
<td><p><span data-ttu-id="74ceb-259">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="74ceb-259">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74ceb-260"><strong>серверсуммари</strong></span><span class="sxs-lookup"><span data-stu-id="74ceb-260"><strong>ServerSummary</strong></span></span></p></td>
<td><p><span data-ttu-id="74ceb-261">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="74ceb-261">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74ceb-262"><strong>мсдиагметадата</strong></span><span class="sxs-lookup"><span data-stu-id="74ceb-262"><strong>MsDiagMetaData</strong></span></span></p></td>
<td><p><span data-ttu-id="74ceb-263">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="74ceb-263">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

