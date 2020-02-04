---
title: 'Lync Server 2013: список таблиц качества взаимодействия'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: List of QoE tables
ms:assetid: 176194d7-d184-4e23-94bb-cb62b4db47f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398236(v=OCS.15)
ms:contentKeyID: 48183512
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c3161415b65c8e85ace7968ab29d86c0d0c5387a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765397"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="list-of-qoe-tables-in-lync-server-2013"></a><span data-ttu-id="24013-102">Список таблиц качества взаимодействия в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="24013-102">List of QoE tables in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="24013-103">_**Тема последнего изменения:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="24013-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="24013-104">Схема базы данных состоит из следующих таблиц.</span><span class="sxs-lookup"><span data-stu-id="24013-104">The database schema consists of the following tables.</span></span>

<span data-ttu-id="24013-105">**Вспомогательные таблицы**</span><span class="sxs-lookup"><span data-stu-id="24013-105">**Supporting Tables**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="24013-106"><strong>Таблица</strong></span><span class="sxs-lookup"><span data-stu-id="24013-106"><strong>Table</strong></span></span></th>
<th><span data-ttu-id="24013-107"><strong>Описание</strong></span><span class="sxs-lookup"><span data-stu-id="24013-107"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="24013-108"><a href="lync-server-2013-appsharingmetricsthreshold-table.md">Таблица Аппшарингметрикссрешолд в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="24013-108"><a href="lync-server-2013-appsharingmetricsthreshold-table.md">AppSharingMetricsThreshold table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="24013-109">Хранение оптимальных и приемлемых значений для показателей качества взаимодействия, используемых совместно с приложением.</span><span class="sxs-lookup"><span data-stu-id="24013-109">Stores optimal and acceptable values for the Quality of Experience metrics used with application sharing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24013-110"><a href="lync-server-2013-codecdescription-table.md">Таблица Кодекдескриптион в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="24013-110"><a href="lync-server-2013-codecdescription-table.md">CodecDescription table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="24013-111">Сопоставляет уникальные идентификаторы кодека с соответствующими кодеками.</span><span class="sxs-lookup"><span data-stu-id="24013-111">Maps unique codec identifiers to their corresponding codec.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24013-112"><a href="lync-server-2013-ipaddress-table.md">Таблица IP-адреса в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="24013-112"><a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="24013-113">Сопоставляет IP-адреса с уникальными идентификаторами IP-адресов, которые используются в базе данных качества обслуживания.</span><span class="sxs-lookup"><span data-stu-id="24013-113">Maps IP addresses to the unique IP address identifiers used elsewhere in the Quality of Experience database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24013-114"><a href="lync-server-2013-networkconnectiondetail-table.md">Таблица Нетворкконнектиондетаил в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="24013-114"><a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="24013-115">Сопоставляет типы сетевых подключений с идентификаторами сетевых подключений, используемыми в базе данных качества обслуживания.</span><span class="sxs-lookup"><span data-stu-id="24013-115">Maps network connection types to the network connection identifiers used elsewhere in the Quality of Experience database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24013-116"><a href="lync-server-2013-purgesettings-table-qoe.md">Пуржесеттингс Table (QoE) в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="24013-116"><a href="lync-server-2013-purgesettings-table-qoe.md">PurgeSettings table (QoE) in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="24013-117">Хранит сведения о том, что (и когда) устаревшие записи качества обслуживания будут автоматически удалены из базы данных QoE.</span><span class="sxs-lookup"><span data-stu-id="24013-117">Stores information that specifies if (and when) outdated Quality of Experience records will automatically be deleted from the QoE database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24013-118"><a href="lync-server-2013-traceroute-table.md">Таблица использованием Traceroute в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="24013-118"><a href="lync-server-2013-traceroute-table.md">TraceRoute table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="24013-119">Хранит сведения о маршрутизации для звонков.</span><span class="sxs-lookup"><span data-stu-id="24013-119">Stores routing information for calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24013-120"><a href="lync-server-2013-useragentdef-table-qoe.md">Усеражентдеф Table (QoE) в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="24013-120"><a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="24013-121">Сопоставляет идентификаторы агента пользователя с описательными именами агента.</span><span class="sxs-lookup"><span data-stu-id="24013-121">Maps user agent identifiers to the agent’s descriptive names.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24013-122"><a href="lync-server-2013-videometricsthreshold-table.md">Таблица Видеометрикссрешолд в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="24013-122"><a href="lync-server-2013-videometricsthreshold-table.md">VideoMetricsThreshold table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="24013-123">Хранение оптимальных и приемлемых значений для показателей качества взаимодействия, используемых с видеозвонками.</span><span class="sxs-lookup"><span data-stu-id="24013-123">Stores optimal and acceptable values for the Quality of Experience metrics used with video calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24013-124"><a href="lync-server-2013-useragent-table.md">Таблица UserAgent в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="24013-124"><a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="24013-125">В сеансах голосовой и видеосвязи для протоколов SIP (UA) User Agent (агент запуска сеанса) хранятся строки и типы UA.</span><span class="sxs-lookup"><span data-stu-id="24013-125">Stores Session Initiation Protocol (SIP) User Agent (UA) strings and UA types used in audio and video sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24013-126"><a href="lync-server-2013-user-table.md">Таблица User в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="24013-126"><a href="lync-server-2013-user-table.md">User table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="24013-127">Хранит URI пользователей, конференций и телефонных номеров, используемых в сеансах голосовой связи и видео.</span><span class="sxs-lookup"><span data-stu-id="24013-127">Stores user, conference, and phone URIs used in audio and video sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24013-128"><a href="lync-server-2013-endpoint-table.md">Таблица Endpoint в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="24013-128"><a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="24013-129">Хранит полные доменные имена конечных точек, участвующих в звуковых и видеосеансах.</span><span class="sxs-lookup"><span data-stu-id="24013-129">Stores FQDN computer names of endpoints participating in audio and video sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24013-130"><a href="lync-server-2013-pool-table.md">Таблица Pool в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="24013-130"><a href="lync-server-2013-pool-table.md">Pool table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="24013-131">Хранит имена пулов, которым принадлежат данные метрик.</span><span class="sxs-lookup"><span data-stu-id="24013-131">Stores the names of pools to which metrics data belongs.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24013-132"><a href="lync-server-2013-device-table.md">Таблица Device в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="24013-132"><a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="24013-133">Хранит устройства захвата и устройства рендеринга, используемые в голосовых и видеозвонках.</span><span class="sxs-lookup"><span data-stu-id="24013-133">Stores capture devices and render devices which are used in an audio/video calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24013-134"><a href="lync-server-2013-devicedriver-table.md">Таблица DeviceDriver в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="24013-134"><a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="24013-135">Хранит драйвер устройства захвата и устройство рендеринга, которое используется в голосовых и видеозвонках.</span><span class="sxs-lookup"><span data-stu-id="24013-135">Stores driver for the capture device and the render device which are used in audio/video calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24013-136"><a href="lync-server-2013-conference-table.md">Таблица Conference в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="24013-136"><a href="lync-server-2013-conference-table.md">Conference table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="24013-137">Хранит коды URI конференций для сценариев конференции или Диалогид для других сценариев.</span><span class="sxs-lookup"><span data-stu-id="24013-137">Stores Conference URIs for conference scenarios or DialogID for other scenarios.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24013-138"><a href="lync-server-2013-sessioncorrelation-table.md">Таблица SessionCorrelation в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="24013-138"><a href="lync-server-2013-sessioncorrelation-table.md">SessionCorrelation table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="24013-139">Содержит сведения о корреляции для КОММУТИРУЕМых звонков.</span><span class="sxs-lookup"><span data-stu-id="24013-139">Stores CorrelationID for PSTN calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24013-140"><a href="lync-server-2013-payloaddescription-table.md">Таблица PayloadDescription в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="24013-140"><a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="24013-141">Хранит кодек, используемый в голосовых и видеозвонках.</span><span class="sxs-lookup"><span data-stu-id="24013-141">Stores the Codec used in audio/video calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24013-142"><a href="lync-server-2013-appliedbandwidthsource-table.md">Таблица AppliedBandwidthSource в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="24013-142"><a href="lync-server-2013-appliedbandwidthsource-table.md">AppliedBandwidthSource table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="24013-143">Сохранение источника пропускной способности, используемой в голосовых и видеозвонках.</span><span class="sxs-lookup"><span data-stu-id="24013-143">Stores the bandwidth source used in audio/video calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24013-144"><a href="lync-server-2013-macaddress-table.md">Таблица MacAddress в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="24013-144"><a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="24013-145">Хранит MAC-адрес конечных точек, участвующих в сеансах аудио и видео.</span><span class="sxs-lookup"><span data-stu-id="24013-145">Stores the MAC address of the endpoints participating in audio and video sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24013-146"><a href="lync-server-2013-dialog-table.md">Таблица Dialog в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="24013-146"><a href="lync-server-2013-dialog-table.md">Dialog table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="24013-147">Хранит идентификатор диалога для звуковых и видеосеансов.</span><span class="sxs-lookup"><span data-stu-id="24013-147">Stores the Dialog ID of audio and video sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24013-148"><a href="lync-server-2013-region-table.md">Таблица Region в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="24013-148"><a href="lync-server-2013-region-table.md">Region table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="24013-149">Хранит сетевой регион, определенный в параметрах NC.</span><span class="sxs-lookup"><span data-stu-id="24013-149">Stores the network region defined in NCS setting.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24013-150"><a href="lync-server-2013-usersite-table.md">Таблица UserSite в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="24013-150"><a href="lync-server-2013-usersite-table.md">UserSite table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="24013-151">Сохранение сетевого сайта, определенного в параметрах NC.</span><span class="sxs-lookup"><span data-stu-id="24013-151">Stores the network site defined in NCS setting.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24013-152"><a href="lync-server-2013-subnet-table.md">Таблица Subnet в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="24013-152"><a href="lync-server-2013-subnet-table.md">Subnet table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="24013-153">Хранит подсеть, определенную в параметрах NC.</span><span class="sxs-lookup"><span data-stu-id="24013-153">Stores the subnet defined in NCS setting.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24013-154"><a href="lync-server-2013-monitoredregionlink-table.md">Таблица MonitoredRegionLink в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="24013-154"><a href="lync-server-2013-monitoredregionlink-table.md">MonitoredRegionLink table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="24013-155">Хранит ссылку на регион, определенную в параметрах NC.</span><span class="sxs-lookup"><span data-stu-id="24013-155">Stores the region link defined in NCS setting.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24013-156"><a href="monitoredusersitelink-table.md">Таблица MonitoredUserSiteLink</a></span><span class="sxs-lookup"><span data-stu-id="24013-156"><a href="monitoredusersitelink-table.md">MonitoredUserSiteLink table</a></span></span></p></td>
<td><p><span data-ttu-id="24013-157">Хранит ссылки на сайты сети, определенные в параметрах NC.</span><span class="sxs-lookup"><span data-stu-id="24013-157">Stores the network site links defined in NCS setting.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24013-158"><a href="lync-server-2013-endpointsubnet-table.md">Таблица EndpointSubnet в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="24013-158"><a href="lync-server-2013-endpointsubnet-table.md">EndpointSubnet table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="24013-159">Хранит подсеть конечной точки, участвующей в звуковых и видеосеансах.</span><span class="sxs-lookup"><span data-stu-id="24013-159">Stores the subnet of the endpoint participating in an audio and video session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24013-160"><a href="lync-server-2013-server-table.md">Таблица Server в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="24013-160"><a href="lync-server-2013-server-table.md">Server table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="24013-161">Хранит полное доменное имя или IP-адрес сервера, через который восходит носитель.</span><span class="sxs-lookup"><span data-stu-id="24013-161">Stores the FQDN or IP address of the server the media goes through.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="24013-162">**Таблицы для данных метрик**</span><span class="sxs-lookup"><span data-stu-id="24013-162">**Tables for metrics data**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="24013-163"><strong>Таблица</strong></span><span class="sxs-lookup"><span data-stu-id="24013-163"><strong>Table</strong></span></span></th>
<th><span data-ttu-id="24013-164"><strong>Описание</strong></span><span class="sxs-lookup"><span data-stu-id="24013-164"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="24013-165"><a href="lync-server-2013-appsharingstream-table.md">Таблица Аппшарингстреам в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="24013-165"><a href="lync-server-2013-appsharingstream-table.md">AppSharingStream table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="24013-166">Хранение метрик качества для сетевых потоков, используемых для совместного использования приложений.</span><span class="sxs-lookup"><span data-stu-id="24013-166">Stores Quality of Experience metrics for the network streams used for application sharing.</span></span> <span data-ttu-id="24013-167">Показатели качества взаимодействия для сетевых потоков, используемых для совместного использования приложений.</span><span class="sxs-lookup"><span data-stu-id="24013-167">Quality of Experience metrics for the network streams used for application sharing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24013-168"><a href="lync-server-2013-session-table.md">Таблица Session в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="24013-168"><a href="lync-server-2013-session-table.md">Session table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="24013-169">Хранит общие сведения о звуковых и видеофайлах, а также о звуковых и видеосеансах.</span><span class="sxs-lookup"><span data-stu-id="24013-169">Stores overall information about an audio or audio/video session.</span></span> <span data-ttu-id="24013-170">Сеанс определяется как звуковое или видеодиалоговое окно SIP между двумя конечными точками.</span><span class="sxs-lookup"><span data-stu-id="24013-170">A session is defined as an audio or video SIP dialog between two endpoints.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24013-171"><a href="lync-server-2013-medialine-table.md">Таблица MediaLine в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="24013-171"><a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="24013-172">Хранит сведения о каждой строке мультимедиа в сеансе.</span><span class="sxs-lookup"><span data-stu-id="24013-172">Stores information about each media line in a session.</span></span> <span data-ttu-id="24013-173">Линия мультимедиа — это коллекция из одного или нескольких звуковых и видеопотоков.</span><span class="sxs-lookup"><span data-stu-id="24013-173">A media line is a collection of one or more audio and video streams.</span></span> <span data-ttu-id="24013-174">Обычно в одной линии есть два потока: аудио-или видеофайлы.</span><span class="sxs-lookup"><span data-stu-id="24013-174">Typically, a single media line will have two streams, either audio or video.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24013-175"><a href="lync-server-2013-audiostream-table.md">Таблица AudioStream в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="24013-175"><a href="lync-server-2013-audiostream-table.md">AudioStream table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="24013-176">Хранит метрики качества звукового файла в линии мультимедиа для каждого звукового потока.</span><span class="sxs-lookup"><span data-stu-id="24013-176">Stores audio media quality metrics for each audio stream in the media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24013-177"><a href="lync-server-2013-audiosignal-table.md">Таблица AudioSignal в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="24013-177"><a href="lync-server-2013-audiosignal-table.md">AudioSignal table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="24013-178">Сохраняет метрики качества звукового файла в линии мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="24013-178">Stores audio media quality metrics in the media line.</span></span> <span data-ttu-id="24013-179">Это включает в себя метрики для подавления эха (AEC) и автоматических показателей контроля усиления (АГК).</span><span class="sxs-lookup"><span data-stu-id="24013-179">This includes acoustic echo cancellation (AEC) and automatic gain control (AGC) metrics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24013-180"><a href="lync-server-2013-videostream-table.md">Таблица VideoStream в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="24013-180"><a href="lync-server-2013-videostream-table.md">VideoStream table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="24013-181">Хранит метрики качества видео для каждого звукового потока в строке мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="24013-181">Stores video media quality metrics for each audio stream in the media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24013-182"><a href="lync-server-2013-audioclientevent-table.md">Таблица AudioClientEvent в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="24013-182"><a href="lync-server-2013-audioclientevent-table.md">AudioClientEvent table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="24013-183">Сохраняет показатели качества звуковых файлов мультимедиа, полученные из клиентского события.</span><span class="sxs-lookup"><span data-stu-id="24013-183">Stores audio media quality metrics collected from the client event.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24013-184"><a href="lync-server-2013-videoclientevent-table.md">Таблица VideoClientEvent в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="24013-184"><a href="lync-server-2013-videoclientevent-table.md">VideoClientEvent table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="24013-185">Хранит метрики качества видео, собранные из клиентского события.</span><span class="sxs-lookup"><span data-stu-id="24013-185">Stores video media quality metrics collected from the client event.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24013-186"><strong>Таблица Диагностикдата</strong></span><span class="sxs-lookup"><span data-stu-id="24013-186"><strong>DiagnosticData Table</strong></span></span></p></td>
<td><p><span data-ttu-id="24013-187">Хранит диагностические данные, предназначенные только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="24013-187">Stores diagnostic data which is for internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="24013-188">**Таблицы для сводных данных**</span><span class="sxs-lookup"><span data-stu-id="24013-188">**Tables for summary data**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="24013-189"><strong>Таблица</strong></span><span class="sxs-lookup"><span data-stu-id="24013-189"><strong>Table</strong></span></span></th>
<th><span data-ttu-id="24013-190"><strong>Описание</strong></span><span class="sxs-lookup"><span data-stu-id="24013-190"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="24013-191"><strong>Таблица Серверсуммари</strong></span><span class="sxs-lookup"><span data-stu-id="24013-191"><strong>ServerSummary Table</strong></span></span></p></td>
<td><p><span data-ttu-id="24013-192">Хранит сводные данные для серверов, эти данные используются только для отчетов о качестве опыта (QoE).</span><span class="sxs-lookup"><span data-stu-id="24013-192">Stores summary data for the servers, these data is used for Quality of Experience (QoE) reporting only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24013-193"><strong>Таблица Усерсуммари</strong></span><span class="sxs-lookup"><span data-stu-id="24013-193"><strong>UserSummary Table</strong></span></span></p></td>
<td><p><span data-ttu-id="24013-194">Хранит сводные данные для пользователей, эти данные используются только для отчетов QoE.</span><span class="sxs-lookup"><span data-stu-id="24013-194">Stores summary data for users, these data is used for QoE reporting only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24013-195"><strong>Таблица Каллтипесуммари</strong></span><span class="sxs-lookup"><span data-stu-id="24013-195"><strong>CallTypeSummary Table</strong></span></span></p></td>
<td><p><span data-ttu-id="24013-196">Хранить сводные данные для типов звонков эти данные используются только для отчетов QoE.</span><span class="sxs-lookup"><span data-stu-id="24013-196">Store summary data for call types, these data is used for QoE reporting only.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="24013-197">**Таблицы для внутреннего использования сервером мониторинга**</span><span class="sxs-lookup"><span data-stu-id="24013-197">**Tables for Internal Use by Monitoring Server**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="24013-198"><strong>Таблица</strong></span><span class="sxs-lookup"><span data-stu-id="24013-198"><strong>Table</strong></span></span></th>
<th><span data-ttu-id="24013-199"><strong>Описание</strong></span><span class="sxs-lookup"><span data-stu-id="24013-199"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="24013-200"><strong>дбконфигдатетиме</strong></span><span class="sxs-lookup"><span data-stu-id="24013-200"><strong>DbConfigDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="24013-201">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="24013-201">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24013-202"><strong>дбконфигинт</strong></span><span class="sxs-lookup"><span data-stu-id="24013-202"><strong>DbConfigInt</strong></span></span></p></td>
<td><p><span data-ttu-id="24013-203">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="24013-203">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24013-204"><strong>Интерфейсная таблица</strong></span><span class="sxs-lookup"><span data-stu-id="24013-204"><strong>FrontEnd Table</strong></span></span></p></td>
<td><p><span data-ttu-id="24013-205">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="24013-205">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24013-206"><strong>Таблица задач</strong></span><span class="sxs-lookup"><span data-stu-id="24013-206"><strong>Task Table</strong></span></span></p></td>
<td><p><span data-ttu-id="24013-207">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="24013-207">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24013-208"><strong>суммаритаблеконфигуратион</strong></span><span class="sxs-lookup"><span data-stu-id="24013-208"><strong>SummaryTableConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="24013-209">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="24013-209">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24013-210"><strong>дберрормессаже</strong></span><span class="sxs-lookup"><span data-stu-id="24013-210"><strong>DbErrorMessage</strong></span></span></p></td>
<td><p><span data-ttu-id="24013-211">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="24013-211">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24013-212"><strong>метрикссрешолд</strong></span><span class="sxs-lookup"><span data-stu-id="24013-212"><strong>MetricsThreshold</strong></span></span></p></td>
<td><p><span data-ttu-id="24013-213">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="24013-213">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24013-214"><strong>дайлигхтсавингеарс</strong></span><span class="sxs-lookup"><span data-stu-id="24013-214"><strong>DaylightSavingYears</strong></span></span></p></td>
<td><p><span data-ttu-id="24013-215">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="24013-215">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24013-216"><strong>тимезонеконфигуратион</strong></span><span class="sxs-lookup"><span data-stu-id="24013-216"><strong>TimeZoneConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="24013-217">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="24013-217">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24013-218"><strong>Часовых поясов</strong></span><span class="sxs-lookup"><span data-stu-id="24013-218"><strong>TimeZones</strong></span></span></p></td>
<td><p><span data-ttu-id="24013-219">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="24013-219">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24013-220"><strong>Таблица Каллсуммари</strong></span><span class="sxs-lookup"><span data-stu-id="24013-220"><strong>CallSummary Table</strong></span></span></p></td>
<td><p><span data-ttu-id="24013-221">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="24013-221">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24013-222"><strong>Таблица Девицекаллсумари</strong></span><span class="sxs-lookup"><span data-stu-id="24013-222"><strong>DeviceCallSumary Table</strong></span></span></p></td>
<td><p><span data-ttu-id="24013-223">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="24013-223">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24013-224"><strong>Таблица "клиент"</strong></span><span class="sxs-lookup"><span data-stu-id="24013-224"><strong>Tenant Table</strong></span></span></p></td>
<td><p><span data-ttu-id="24013-225">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="24013-225">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24013-226"><strong>видеокаллсуммаритабле</strong></span><span class="sxs-lookup"><span data-stu-id="24013-226"><strong>VideoCallSummaryTable</strong></span></span></p></td>
<td><p><span data-ttu-id="24013-227">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="24013-227">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24013-228"><strong>аскаллсуммаритабле</strong></span><span class="sxs-lookup"><span data-stu-id="24013-228"><strong>ASCallSummaryTable</strong></span></span></p></td>
<td><p><span data-ttu-id="24013-229">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="24013-229">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

