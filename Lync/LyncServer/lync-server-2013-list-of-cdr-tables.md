---
title: 'Lync Server 2013: список таблиц регистрации звонков'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: List of CDR tables
ms:assetid: 031843fd-c7ff-4534-9b02-8847aad70807
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398084(v=OCS.15)
ms:contentKeyID: 48183254
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1ac043d144e73d8e1b40ca717e278619e053fdc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833949"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="list-of-cdr-tables-in-lync-server-2013"></a><span data-ttu-id="d091d-102">Список таблиц регистрации звонков в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d091d-102">List of CDR tables in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d091d-103">_**Тема последнего изменения:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="d091d-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="d091d-104">Схема базы данных для записи сведений о звонке (CDR) состоит из следующих таблиц.</span><span class="sxs-lookup"><span data-stu-id="d091d-104">The call detail recording (CDR) database schema consists of the following tables.</span></span>

<div>

## <a name="static-tables"></a><span data-ttu-id="d091d-105">Статические таблицы</span><span class="sxs-lookup"><span data-stu-id="d091d-105">Static Tables</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d091d-106">Таблица</span><span class="sxs-lookup"><span data-stu-id="d091d-106">Table</span></span></th>
<th><span data-ttu-id="d091d-107">Описание</span><span class="sxs-lookup"><span data-stu-id="d091d-107">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d091d-108"><a href="lync-server-2013-callpriorities-table.md">Таблица SessionCorrelation в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d091d-108"><a href="lync-server-2013-callpriorities-table.md">CallPriorities table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d091d-109">Хранит список возможных приоритетов звонков, например, экстренных, срочных, обычных, несрочных и т. д.</span><span class="sxs-lookup"><span data-stu-id="d091d-109">Stores the list of possible call priorities, such as emergency, urgent, normal, non-urgent, and more.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d091d-110"><a href="lync-server-2013-conferencejointimethresholds-table.md">Таблица Конференцежоинтимесрешолдс в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d091d-110"><a href="lync-server-2013-conferencejointimethresholds-table.md">ConferenceJoinTimeThresholds table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d091d-111">Хранит границы классификации, используемые в сводном отчете "время присоединения к Конференции".</span><span class="sxs-lookup"><span data-stu-id="d091d-111">Stores the classification boundaries used by the Conference Join Time Summary Report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d091d-112"><a href="lync-server-2013-deregistertype-table.md">Таблица DeRegisterType в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d091d-112"><a href="lync-server-2013-deregistertype-table.md">DeRegisterType table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d091d-113">Хранит список возможных причин, по которым пользователь может отменить регистрацию, например &quot;инициирование клиента&quot; &quot;, истек срок регистрации&quot; &quot;, сбой клиента&quot; и многое другое.</span><span class="sxs-lookup"><span data-stu-id="d091d-113">Stores the list of possible user de-register reasons, such as &quot;client initiated,&quot; &quot;registration expired,&quot; &quot;client crash,&quot; and more.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d091d-114"><a href="lync-server-2013-medialist-table.md">Таблица MediaList в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d091d-114"><a href="lync-server-2013-medialist-table.md">MediaList table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d091d-115">Хранит список типов мультимедиа, которые могут создавать записи в базе данных (например, мгновенные сообщения, звук, видео и передачу файлов).</span><span class="sxs-lookup"><span data-stu-id="d091d-115">Stores the list of media types that can generate entries in the database (for example, IM, audio, video, and file transfer).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d091d-116"><a href="lync-server-2013-purgesettings-table.md">Таблица Пуржесеттингс в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d091d-116"><a href="lync-server-2013-purgesettings-table.md">PurgeSettings table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d091d-117">Хранит сведения о том, будут ли (и когда) устаревшие записи о вызовах автоматически удалены из базы данных CDR.</span><span class="sxs-lookup"><span data-stu-id="d091d-117">Stores information that specifies if (and when) outdated call detail records will automatically be deleted from the CDR database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d091d-118"><a href="lync-server-2013-roles-table.md">Таблица Roles в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d091d-118"><a href="lync-server-2013-roles-table.md">Roles table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d091d-119">Хранит список возможных ролей конференции (например, участника и выступающего).</span><span class="sxs-lookup"><span data-stu-id="d091d-119">Stores the list of possible conference roles (for example, attendee and presenter).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d091d-120"><a href="lync-server-2013-sipresponsemetadata-table.md">Таблица Сипреспонсеметадата в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d091d-120"><a href="lync-server-2013-sipresponsemetadata-table.md">SIPResponseMetaData table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d091d-121">Содержит список кодов ответов SIP и классификацию и определение каждого из этих кодов.</span><span class="sxs-lookup"><span data-stu-id="d091d-121">Stores a list of SIP response codes and the classification and definition of each of those codes.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="supporting-tables"></a><span data-ttu-id="d091d-122">Вспомогательные таблицы</span><span class="sxs-lookup"><span data-stu-id="d091d-122">Supporting Tables</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d091d-123">Таблица</span><span class="sxs-lookup"><span data-stu-id="d091d-123">Table</span></span></th>
<th><span data-ttu-id="d091d-124">Описание</span><span class="sxs-lookup"><span data-stu-id="d091d-124">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d091d-125"><a href="lync-server-2013-clientversions-table.md">Таблица ClientVersions в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d091d-125"><a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d091d-126">Хранит клиентов (тип клиента и номер версии) каждого клиента, участвующего в вызове, с данными, захваченными в этой базе данных.</span><span class="sxs-lookup"><span data-stu-id="d091d-126">Stores the clients (both client type and version number) of each client involved in a call with information captured in this database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d091d-127"><a href="lync-server-2013-conferenceuris-table.md">Таблица ConferenceUris в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d091d-127"><a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d091d-128">Хранит список Конференцеурис, используемых в звонках, связанных с Конференцией.</span><span class="sxs-lookup"><span data-stu-id="d091d-128">Stores a list of ConferenceURIs that are used in conference related calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d091d-129"><a href="lync-server-2013-contenttypes-table.md">Таблица ContentTypes в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d091d-129"><a href="lync-server-2013-contenttypes-table.md">ContentTypes table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d091d-130">Хранит список типов контента SIP, которые используются в одноранговых звонках и конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="d091d-130">Stores a list of Session Initiation Protocol (SIP) content types that are used in both peer-to-peer calls and conference calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d091d-131"><a href="lync-server-2013-devices-table.md">Таблица Devices в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d091d-131"><a href="lync-server-2013-devices-table.md">Devices table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d091d-132">Хранит список устройств, в том числе изготовителя, аппаратную версию и MAC-адрес.</span><span class="sxs-lookup"><span data-stu-id="d091d-132">Stores a list of devices, including their manufacturer, hardware version, and MAC address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d091d-133"><a href="lync-server-2013-dialogs-table.md">Таблица Dialogs в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d091d-133"><a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d091d-134">Хранит сведения о коде диалогового окна для каждого сеанса в базе данных.</span><span class="sxs-lookup"><span data-stu-id="d091d-134">Stores information about the Dialog ID for each session in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d091d-135"><a href="lync-server-2013-edgeservers-table.md">Таблица EdgeServers в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d091d-135"><a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d091d-136">Хранит список пограничных серверов, которые используются при внешних звонках.</span><span class="sxs-lookup"><span data-stu-id="d091d-136">Stores a list of Edge Servers that are used for external calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d091d-137"><a href="lync-server-2013-gateways-table.md">Таблица Gateways в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d091d-137"><a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d091d-138">Хранит список шлюзов, используемых для звонков по протоколу голосовой связи через Интернет (VoIP).</span><span class="sxs-lookup"><span data-stu-id="d091d-138">Stores a list of Gateways that are used for Voice over Internet Protocol (VoIP) calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d091d-139"><a href="lync-server-2013-hardwareversions-table.md">Таблица HardwareVersions в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d091d-139"><a href="lync-server-2013-hardwareversions-table.md">HardwareVersions table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d091d-140">Хранит список аппаратных версий устройств (стационарных телефонов).</span><span class="sxs-lookup"><span data-stu-id="d091d-140">Stores a list of hardware versions of devices (desk phone).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d091d-141"><a href="lync-server-2013-manufacturers-table.md">Таблица Manufacturers в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d091d-141"><a href="lync-server-2013-manufacturers-table.md">Manufacturers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d091d-142">Хранит список изготовителей устройств (стационарный телефон).</span><span class="sxs-lookup"><span data-stu-id="d091d-142">Stores a list of manufacturers of devices (desk phone).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d091d-143"><a href="lync-server-2013-mcus-table.md">Таблица Mcus в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d091d-143"><a href="lync-server-2013-mcus-table.md">Mcus table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d091d-144">В этой папке хранятся сведения о различных серверах конференций/V и их URI.</span><span class="sxs-lookup"><span data-stu-id="d091d-144">Stores information about the various A/V Conferencing Servers and their URIs.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d091d-145"><a href="lync-server-2013-mediationservers-table.md">Таблица MediationServers в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d091d-145"><a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d091d-146">Хранит список серверов-посредников, используемых для звонков по протоколу VoIP.</span><span class="sxs-lookup"><span data-stu-id="d091d-146">Stores a list of Mediation Servers that are used for VoIP calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d091d-147"><a href="lync-server-2013-phones-table.md">Таблица Phones в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d091d-147"><a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d091d-148">Хранит все телефонные номера, используемые для звонков по протоколу VoIP, которые были заархивированы или в которых были записаны сведения о звонках.</span><span class="sxs-lookup"><span data-stu-id="d091d-148">Stores all the phone numbers used in VoIP calls that were archived or whose call details were recorded.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d091d-149"><a href="lync-server-2013-pools-table.md">Таблица Pools в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d091d-149"><a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d091d-150">Хранит имена групп, в которых регистрируются МГНОВЕНные сообщения.</span><span class="sxs-lookup"><span data-stu-id="d091d-150">Stores the names of the pool on which IM messages are captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d091d-151"><a href="lync-server-2013-servers-table.md">Таблица Servers в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d091d-151"><a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d091d-152">Хранит имена серверов, участвующих в звонках.</span><span class="sxs-lookup"><span data-stu-id="d091d-152">Stores the name of servers involved in calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d091d-153"><a href="lync-server-2013-tenants-table.md">Таблица Tenants в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d091d-153"><a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d091d-154">Хранит клиентов, которые поддерживаются текущим развертыванием.</span><span class="sxs-lookup"><span data-stu-id="d091d-154">Stores the tenants supported by current deployment.</span></span> <span data-ttu-id="d091d-155">Некоторые клиентские сборки для корпоративных пользователей, федеративного пользователя, общего пользователя подключения к обмену мгновенными сообщениями и анонимные пользователи.</span><span class="sxs-lookup"><span data-stu-id="d091d-155">There some build-in tenants for Enterprise user, Federated User, public IM connectivity user, and Anonymous users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d091d-156"><a href="lync-server-2013-useragentdef-table.md">Таблица Усеражентдеф в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d091d-156"><a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d091d-157">Сопоставляет идентификаторы агента пользователя с описательными именами агента.</span><span class="sxs-lookup"><span data-stu-id="d091d-157">Maps user agent identifiers to the agent’s descriptive names.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d091d-158"><a href="lync-server-2013-users-table.md">Таблица Users в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d091d-158"><a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d091d-159">Хранит идентификаторы URI пользователей, которые участвовали в сеансах, записанных или архивированных в этой базе данных.</span><span class="sxs-lookup"><span data-stu-id="d091d-159">Stores the user URIs of users who have participated in sessions recorded or archived in this database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d091d-160"><a href="lync-server-2013-userstatistics-table.md">Таблица Усерстатистикс в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d091d-160"><a href="lync-server-2013-userstatistics-table.md">UserStatistics table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d091d-161">Хранит сведения об использовании системы конкретным пользователем.</span><span class="sxs-lookup"><span data-stu-id="d091d-161">Stores information about an individual user’s usage of the system.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-specific-to-conference-cdr-records"></a><span data-ttu-id="d091d-162">Таблицы, связанные с записями CDR конференций</span><span class="sxs-lookup"><span data-stu-id="d091d-162">Tables Specific to Conference CDR Records</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d091d-163">Таблица</span><span class="sxs-lookup"><span data-stu-id="d091d-163">Table</span></span></th>
<th><span data-ttu-id="d091d-164">Описание</span><span class="sxs-lookup"><span data-stu-id="d091d-164">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d091d-165"><a href="lync-server-2013-conferences-table.md">Таблица Conferences в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d091d-165"><a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d091d-166">Хранит сведения обо всех конференциях, которые были архивированы, а также о том, какие данные были записаны, включая Конференцеури, время начала и окончания.</span><span class="sxs-lookup"><span data-stu-id="d091d-166">Stores information about all conferences that were archived or whose details were recorded, including ConferenceURI, and start and end time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d091d-167"><a href="lync-server-2013-conferencesessiondetails-table.md">Таблица ConferenceSessionDetails в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d091d-167"><a href="lync-server-2013-conferencesessiondetails-table.md">ConferenceSessionDetails table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d091d-168">В этой папке хранятся сведения о каждом сеансе конференции на базе SIP, в том числе время начала и окончания, идентификатор пользователя, код ответа и идентификатор диагностики для каждого сеанса.</span><span class="sxs-lookup"><span data-stu-id="d091d-168">Stores information about every SIP-based conference session, including start and end time, user ID, response code, and diagnostic ID for each session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d091d-169"><a href="lync-server-2013-focusjoinsandleaves-table.md">Таблица FocusJoinsAndLeaves в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d091d-169"><a href="lync-server-2013-focusjoinsandleaves-table.md">FocusJoinsAndLeaves table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d091d-170">Хранит сведения о присоединениях и листьях конференций, в том числе о роли пользователей и клиентской версии.</span><span class="sxs-lookup"><span data-stu-id="d091d-170">Stores information about conference joins and leaves, including users’ role and client version.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d091d-171"><a href="lync-server-2013-mcujoinsandleaves-table.md">Таблица McuJoinsAndLeaves в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d091d-171"><a href="lync-server-2013-mcujoinsandleaves-table.md">McuJoinsAndLeaves table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d091d-172">Хранит сведения о серверах конференций (A/V), вовлеченных в конференцию, а также присоединения и выхода пользователей.</span><span class="sxs-lookup"><span data-stu-id="d091d-172">Stores information about the A/V Conferencing Servers that are involved in a conference and the user join and leave times.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-messages-in-im-conferences"></a><span data-ttu-id="d091d-173">Таблицы для сообщений в конференциях по обмену мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="d091d-173">Tables for Messages in IM Conferences</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d091d-174">Таблица</span><span class="sxs-lookup"><span data-stu-id="d091d-174">Table</span></span></th>
<th><span data-ttu-id="d091d-175">Описание</span><span class="sxs-lookup"><span data-stu-id="d091d-175">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d091d-176"><a href="lync-server-2013-conferencemessagecount-table.md">Таблица ConferenceMessageCount в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d091d-176"><a href="lync-server-2013-conferencemessagecount-table.md">ConferenceMessageCount table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d091d-177">Для каждой конференции с мгновенными сообщениями хранится количество сообщений, отправленных каждым пользователем.</span><span class="sxs-lookup"><span data-stu-id="d091d-177">For each IM conference, stores the number of messages that were sent by each user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d091d-178"><a href="lync-server-2013-imreportsummary-table.md">Таблица Имрепортсуммари в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d091d-178"><a href="lync-server-2013-imreportsummary-table.md">IMReportSummary table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d091d-179">Общие сведения о сеансах обмена мгновенными сообщениями, проводимых в Организации.</span><span class="sxs-lookup"><span data-stu-id="d091d-179">Provides an overall report on the instant messaging sessions held in an organization.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-peer-to-peer-sessions"></a><span data-ttu-id="d091d-180">Таблицы для одноранговых сеансов</span><span class="sxs-lookup"><span data-stu-id="d091d-180">Tables for Peer-to-Peer Sessions</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d091d-181">Таблица</span><span class="sxs-lookup"><span data-stu-id="d091d-181">Table</span></span></th>
<th><span data-ttu-id="d091d-182">Описание</span><span class="sxs-lookup"><span data-stu-id="d091d-182">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d091d-183"><a href="lync-server-2013-sessiondetails-table.md">Таблица SessionDetails в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d091d-183"><a href="lync-server-2013-sessiondetails-table.md">SessionDetails table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d091d-184">Хранит сведения обо всех одноранговых сеансах, в том числе время начала и окончания, идентификатор пользователя, код ответа и количество сообщений для каждого пользователя.</span><span class="sxs-lookup"><span data-stu-id="d091d-184">Stores information about every peer-to-peer session, including start and end time, user ID, response code, and message count for each user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d091d-185"><a href="lync-server-2013-filetransfers-table.md">Таблица FileTransfers в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d091d-185"><a href="lync-server-2013-filetransfers-table.md">FileTransfers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d091d-186">Хранит сведения о сеансах передачи файлов, включая имя файла и результат (разрешено, отклонено или отменено).</span><span class="sxs-lookup"><span data-stu-id="d091d-186">Stores information about file transfer sessions, including file name and result (accepted, rejected, or canceled).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d091d-187"><a href="lync-server-2013-media-table.md">Таблица Media в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d091d-187"><a href="lync-server-2013-media-table.md">Media table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d091d-188">Хранит сведения о различных типах носителей, участвующих в одноранговых сеансах.</span><span class="sxs-lookup"><span data-stu-id="d091d-188">Stores information about the different media types involved in peer-to-peer sessions.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="table-for-voip-call-details"></a><span data-ttu-id="d091d-189">Таблица сведений о звонке VoIP</span><span class="sxs-lookup"><span data-stu-id="d091d-189">Table for VoIP Call Details</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d091d-190">Таблица</span><span class="sxs-lookup"><span data-stu-id="d091d-190">Table</span></span></th>
<th><span data-ttu-id="d091d-191">Описание</span><span class="sxs-lookup"><span data-stu-id="d091d-191">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d091d-192"><a href="lync-server-2013-voipdetails-table.md">Таблица VoipDetails в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d091d-192"><a href="lync-server-2013-voipdetails-table.md">VoipDetails table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d091d-193">Для каждого из двух сторон VoIP/КТСОП звоните сведения о звонке, например номер телефона телефона VoIP, используемый шлюз, и какая сторона отключилась.</span><span class="sxs-lookup"><span data-stu-id="d091d-193">For each two-party VoIP/PSTN call, stores information about the call, such as the phone ID of VoIP phone, gateway used, and which party disconnected.</span></span> <span data-ttu-id="d091d-194">Ссылка на <a href="lync-server-2013-sessiondetails-table.md">таблицу сессиондетаилс в Lync Server 2013</a> для значений "начало/окончание" и "код ответа" для вызова.</span><span class="sxs-lookup"><span data-stu-id="d091d-194">Refers to the <a href="lync-server-2013-sessiondetails-table.md">SessionDetails table in Lync Server 2013</a> for call start/end times and response code.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="d091d-195">Если один из участников звонка является пользователем VoIP или на него вовлечен сервер-посредник, в этой таблице будет создана запись.</span><span class="sxs-lookup"><span data-stu-id="d091d-195">If one party on a call is a VoIP user or if a Mediation Server was involved in the call, a record will be created in this table.</span></span> <span data-ttu-id="d091d-196">Сведения о вызовах VoIP и VoIP, не посвященных коммутируемой телефонной сети общего пользования (PSTN), записываются в <A href="lync-server-2013-sessiondetails-table.md">таблицу сессиондетаилс в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="d091d-196">Information about VoIP/VoIP calls not involving a public switched telephone network (PSTN) phone is captured in the <A href="lync-server-2013-sessiondetails-table.md">SessionDetails table in Lync Server 2013</A>.</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="table-for-e9-1-1-call-auditing"></a><span data-ttu-id="d091d-197">Таблица для аудита звонков E9-1-1</span><span class="sxs-lookup"><span data-stu-id="d091d-197">Table for E9-1-1 Call Auditing</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d091d-198">Таблица</span><span class="sxs-lookup"><span data-stu-id="d091d-198">Table</span></span></th>
<th><span data-ttu-id="d091d-199">Описание</span><span class="sxs-lookup"><span data-stu-id="d091d-199">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d091d-200"><a href="lync-server-2013-locations-table.md">Таблица Locations в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d091d-200"><a href="lync-server-2013-locations-table.md">Locations table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d091d-201">Для каждого вызова экстренной помощи, например улучшенного звонка в 9-1-1 (E9-1-1), можно хранить сведения о его местонахождении.</span><span class="sxs-lookup"><span data-stu-id="d091d-201">For each emergency call, such as an Enhanced 9-1-1 (E9-1-1) call, stores location information about the call.</span></span> <span data-ttu-id="d091d-202">Ссылка на <a href="lync-server-2013-sessiondetails-table.md">таблицу сессиондетаилс в Lync Server 2013</a> для значений "начало/окончание" и "код ответа" для вызова.</span><span class="sxs-lookup"><span data-stu-id="d091d-202">Refers to the <a href="lync-server-2013-sessiondetails-table.md">SessionDetails table in Lync Server 2013</a> for call start/end times and response code.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="d091d-203">Эта таблица включает большой двоичный объект Location для вызова E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="d091d-203">This table only contains the location blob for the E9-1-1 call.</span></span> <span data-ttu-id="d091d-204">Ссылка на таблицу Сессиондетаилс для получения более подробной информации о звонке.</span><span class="sxs-lookup"><span data-stu-id="d091d-204">Refers to the SessionDetails table for other detailed information about the call.</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-troubleshooting"></a><span data-ttu-id="d091d-205">Таблицы для устранения неполадок</span><span class="sxs-lookup"><span data-stu-id="d091d-205">Tables for Troubleshooting</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d091d-206">Таблица</span><span class="sxs-lookup"><span data-stu-id="d091d-206">Table</span></span></th>
<th><span data-ttu-id="d091d-207">Описание</span><span class="sxs-lookup"><span data-stu-id="d091d-207">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d091d-208"><a href="lync-server-2013-application-table.md">Таблица Application в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d091d-208"><a href="lync-server-2013-application-table.md">Application table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d091d-209">В этой папке хранятся сведения о различных процессах в Lync Server 2013, которые используются в маршруте и соединениях.</span><span class="sxs-lookup"><span data-stu-id="d091d-209">Stores information about various processes within Lync Server 2013 that are involved in routing and connections.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d091d-210"><a href="lync-server-2013-calltype-table.md">Таблица CallType в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d091d-210"><a href="lync-server-2013-calltype-table.md">CallType table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d091d-211">Хранит сведения о типах звонка, например "звук", "мгновенные сообщения", "звук и видео" и "общий доступ к приложениям".</span><span class="sxs-lookup"><span data-stu-id="d091d-211">Stores information about types of the call, such as, “audio”, “Instant Messaging”, “audio and video” and “application sharing”.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d091d-212"><a href="lync-server-2013-errorcategory-table.md">Таблица Ерроркатегори в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d091d-212"><a href="lync-server-2013-errorcategory-table.md">ErrorCategory table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d091d-213">Хранит понятное имя для каждого диагностического классификация Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d091d-213">Stores the friendly name for each Microsoft Lync Server 2013 diagnostic classification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d091d-214"><a href="lync-server-2013-errordef-table.md">Таблица ErrorDef в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d091d-214"><a href="lync-server-2013-errordef-table.md">ErrorDef table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d091d-215">Хранит сведения о типах ошибок и их определениях.</span><span class="sxs-lookup"><span data-stu-id="d091d-215">Stores information about types of errors and their definitions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d091d-216"><a href="lync-server-2013-errorreport-table.md">Таблица ErrorReport в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d091d-216"><a href="lync-server-2013-errorreport-table.md">ErrorReport table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d091d-217">Хранит сведения о возникших ошибках.</span><span class="sxs-lookup"><span data-stu-id="d091d-217">Stores information about errors that have occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d091d-218"><a href="lync-server-2013-progressreport-table.md">Таблица ProgressReport в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d091d-218"><a href="lync-server-2013-progressreport-table.md">ProgressReport table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d091d-219">Хранит сведения о ходе выполнения различных шагов, участвующих в процессах Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d091d-219">Stores information about the progress reports of various steps involved in Lync Server 2013 processes.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="d091d-220">Таблицы, приведенные в следующем списке, используются для внутренних целей на сервере Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d091d-220">The tables in the following list are used internally by Lync Server.</span></span> <span data-ttu-id="d091d-221">Эти сведения не описаны в настоящем документе.</span><span class="sxs-lookup"><span data-stu-id="d091d-221">Their details are not described in this document.</span></span>

</div>

<div>

## <a name="tables-for-internal-use-by-lync-server"></a><span data-ttu-id="d091d-222">Таблицы для внутреннего использования в Lync Server</span><span class="sxs-lookup"><span data-stu-id="d091d-222">Tables for Internal Use by Lync Server</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d091d-223">Таблица</span><span class="sxs-lookup"><span data-stu-id="d091d-223">Table</span></span></th>
<th><span data-ttu-id="d091d-224">Описание</span><span class="sxs-lookup"><span data-stu-id="d091d-224">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d091d-225"><strong>Дбконфигдатетиме</strong></span><span class="sxs-lookup"><span data-stu-id="d091d-225"><strong>DbConfigDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="d091d-226">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="d091d-226">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d091d-227"><strong>Дбконфигинт</strong></span><span class="sxs-lookup"><span data-stu-id="d091d-227"><strong>DbConfigInt</strong></span></span></p></td>
<td><p><span data-ttu-id="d091d-228">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="d091d-228">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d091d-229"><strong>Дберрормессаже</strong></span><span class="sxs-lookup"><span data-stu-id="d091d-229"><strong>DbErrorMessage</strong></span></span></p></td>
<td><p><span data-ttu-id="d091d-230">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="d091d-230">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d091d-231"><strong>Интерфейсная таблица</strong></span><span class="sxs-lookup"><span data-stu-id="d091d-231"><strong>FrontEnd Table</strong></span></span></p></td>
<td><p><span data-ttu-id="d091d-232">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="d091d-232">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d091d-233"><strong>Таблица Мсмкпроцессинг</strong></span><span class="sxs-lookup"><span data-stu-id="d091d-233"><strong>MSMQProcessing Table</strong></span></span></p></td>
<td><p><span data-ttu-id="d091d-234">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="d091d-234">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d091d-235"><strong>Суммаритаблеконфигуратион</strong></span><span class="sxs-lookup"><span data-stu-id="d091d-235"><strong>SummaryTableConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="d091d-236">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="d091d-236">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d091d-237"><strong>Таблица "синдикации"</strong></span><span class="sxs-lookup"><span data-stu-id="d091d-237"><strong>Syndicators Table</strong></span></span></p></td>
<td><p><span data-ttu-id="d091d-238">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="d091d-238">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d091d-239"><strong>Таблица Синдикаторстенантмап</strong></span><span class="sxs-lookup"><span data-stu-id="d091d-239"><strong>SyndicatorsTenantMap Table</strong></span></span></p></td>
<td><p><span data-ttu-id="d091d-240">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="d091d-240">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d091d-241"><strong>Таблица задач</strong></span><span class="sxs-lookup"><span data-stu-id="d091d-241"><strong>Task Table</strong></span></span></p></td>
<td><p><span data-ttu-id="d091d-242">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="d091d-242">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d091d-243"><strong>UserStatistics</strong></span><span class="sxs-lookup"><span data-stu-id="d091d-243"><strong>UserStatistics</strong></span></span></p></td>
<td><p><span data-ttu-id="d091d-244">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="d091d-244">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d091d-245"><strong>Усажесуммари_ук</strong></span><span class="sxs-lookup"><span data-stu-id="d091d-245"><strong>UsageSummary_UQ</strong></span></span></p></td>
<td><p><span data-ttu-id="d091d-246">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="d091d-246">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d091d-247"><strong>Усажесуммари</strong></span><span class="sxs-lookup"><span data-stu-id="d091d-247"><strong>UsageSummary</strong></span></span></p></td>
<td><p><span data-ttu-id="d091d-248">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="d091d-248">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d091d-249"><strong>Дайлигхтсавингеарс</strong></span><span class="sxs-lookup"><span data-stu-id="d091d-249"><strong>DaylightSavingYears</strong></span></span></p></td>
<td><p><span data-ttu-id="d091d-250">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="d091d-250">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d091d-251"><strong>Тимезонеконфигуратион</strong></span><span class="sxs-lookup"><span data-stu-id="d091d-251"><strong>TimeZoneConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="d091d-252">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="d091d-252">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d091d-253"><strong>Часовых поясов</strong></span><span class="sxs-lookup"><span data-stu-id="d091d-253"><strong>TimeZones</strong></span></span></p></td>
<td><p><span data-ttu-id="d091d-254">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="d091d-254">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d091d-255"><strong>Фаилуресуммари_ук</strong></span><span class="sxs-lookup"><span data-stu-id="d091d-255"><strong>FailureSummary_UQ</strong></span></span></p></td>
<td><p><span data-ttu-id="d091d-256">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="d091d-256">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d091d-257"><strong>Фаилуресуммари</strong></span><span class="sxs-lookup"><span data-stu-id="d091d-257"><strong>FailureSummary</strong></span></span></p></td>
<td><p><span data-ttu-id="d091d-258">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="d091d-258">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d091d-259"><strong>Серверсуммари</strong></span><span class="sxs-lookup"><span data-stu-id="d091d-259"><strong>ServerSummary</strong></span></span></p></td>
<td><p><span data-ttu-id="d091d-260">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="d091d-260">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d091d-261"><strong>Мсдиагметадата</strong></span><span class="sxs-lookup"><span data-stu-id="d091d-261"><strong>MsDiagMetaData</strong></span></span></p></td>
<td><p><span data-ttu-id="d091d-262">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="d091d-262">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

