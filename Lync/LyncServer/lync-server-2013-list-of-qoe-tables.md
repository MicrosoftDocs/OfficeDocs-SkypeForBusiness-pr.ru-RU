---
title: 'Lync Server 2013: список таблиц QoE'
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
ms.openlocfilehash: d47dc5b2623467feec340a6c918e6b43917593ee
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134955"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="list-of-qoe-tables-in-lync-server-2013"></a><span data-ttu-id="e57c0-102">Список таблиц QoE в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e57c0-102">List of QoE tables in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e57c0-103">_**Последнее изменение темы:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="e57c0-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="e57c0-104">Схема базы данных состоит из следующих таблиц.</span><span class="sxs-lookup"><span data-stu-id="e57c0-104">The database schema consists of the following tables.</span></span>

<span data-ttu-id="e57c0-105">**Вспомогательные таблицы**</span><span class="sxs-lookup"><span data-stu-id="e57c0-105">**Supporting Tables**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e57c0-106"><strong>Table</strong></span><span class="sxs-lookup"><span data-stu-id="e57c0-106"><strong>Table</strong></span></span></th>
<th><span data-ttu-id="e57c0-107"><strong>Описание</strong></span><span class="sxs-lookup"><span data-stu-id="e57c0-107"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e57c0-108"><a href="lync-server-2013-appsharingmetricsthreshold-table.md">Таблица Аппшарингметрикссрешолд в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e57c0-108"><a href="lync-server-2013-appsharingmetricsthreshold-table.md">AppSharingMetricsThreshold table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e57c0-109">Сохранение оптимальных и приемлемых значений для показателей качества взаимодействия, используемых совместно с общим доступом к приложениям.</span><span class="sxs-lookup"><span data-stu-id="e57c0-109">Stores optimal and acceptable values for the Quality of Experience metrics used with application sharing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e57c0-110"><a href="lync-server-2013-codecdescription-table.md">Таблица Кодекдескриптион в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e57c0-110"><a href="lync-server-2013-codecdescription-table.md">CodecDescription table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e57c0-111">Сопоставляет уникальные идентификаторы кодека с соответствующим кодеком.</span><span class="sxs-lookup"><span data-stu-id="e57c0-111">Maps unique codec identifiers to their corresponding codec.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e57c0-112"><a href="lync-server-2013-ipaddress-table.md">IP-адрес таблицы в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e57c0-112"><a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e57c0-113">Сопоставляет IP-адреса с уникальными идентификаторами IP-адресов, используемыми в других местах базы данных качества взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="e57c0-113">Maps IP addresses to the unique IP address identifiers used elsewhere in the Quality of Experience database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e57c0-114"><a href="lync-server-2013-networkconnectiondetail-table.md">Таблица Нетворкконнектиондетаил в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e57c0-114"><a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e57c0-115">Сопоставляет типы сетевых подключений с идентификаторами сетевых подключений, используемыми в других местах базы данных качества взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="e57c0-115">Maps network connection types to the network connection identifiers used elsewhere in the Quality of Experience database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e57c0-116"><a href="lync-server-2013-purgesettings-table-qoe.md">Таблица Таблица purgesettings (QoE) в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e57c0-116"><a href="lync-server-2013-purgesettings-table-qoe.md">PurgeSettings table (QoE) in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e57c0-117">Хранит сведения, указывающие, будут ли (и когда) устаревшие записи качества взаимодействия автоматически удаляться из базы данных QoE.</span><span class="sxs-lookup"><span data-stu-id="e57c0-117">Stores information that specifies if (and when) outdated Quality of Experience records will automatically be deleted from the QoE database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e57c0-118"><a href="lync-server-2013-traceroute-table.md">Таблица Трацерауте в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e57c0-118"><a href="lync-server-2013-traceroute-table.md">TraceRoute table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e57c0-119">Хранит сведения о маршрутизации для вызовов.</span><span class="sxs-lookup"><span data-stu-id="e57c0-119">Stores routing information for calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e57c0-120"><a href="lync-server-2013-useragentdef-table-qoe.md">Таблица Таблица useragentdef (QoE) в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e57c0-120"><a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e57c0-121">Привязка идентификаторов агента пользователя к описательным именам агента.</span><span class="sxs-lookup"><span data-stu-id="e57c0-121">Maps user agent identifiers to the agent’s descriptive names.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e57c0-122"><a href="lync-server-2013-videometricsthreshold-table.md">Таблица Таблица videometricsthreshold в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e57c0-122"><a href="lync-server-2013-videometricsthreshold-table.md">VideoMetricsThreshold table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e57c0-123">Сохранение оптимальных и приемлемых значений для показателей качества взаимодействия, используемых с видеовызовами.</span><span class="sxs-lookup"><span data-stu-id="e57c0-123">Stores optimal and acceptable values for the Quality of Experience metrics used with video calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e57c0-124"><a href="lync-server-2013-useragent-table.md">Таблица UserAgent в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e57c0-124"><a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e57c0-125">Сохраняет строки и типы агентов пользователя для протокола SIP (UA), используемые в сеансах аудио и видео.</span><span class="sxs-lookup"><span data-stu-id="e57c0-125">Stores Session Initiation Protocol (SIP) User Agent (UA) strings and UA types used in audio and video sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e57c0-126"><a href="lync-server-2013-user-table.md">Таблица user в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e57c0-126"><a href="lync-server-2013-user-table.md">User table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e57c0-127">Хранение URI пользователей, конференций и телефонов, используемых в сеансах аудио и видео.</span><span class="sxs-lookup"><span data-stu-id="e57c0-127">Stores user, conference, and phone URIs used in audio and video sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e57c0-128"><a href="lync-server-2013-endpoint-table.md">Таблица конечной точки в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e57c0-128"><a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e57c0-129">Хранит полные доменные имена конечных точек, участвующих в сеансах аудио и видео.</span><span class="sxs-lookup"><span data-stu-id="e57c0-129">Stores FQDN computer names of endpoints participating in audio and video sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e57c0-130"><a href="lync-server-2013-pool-table.md">Таблица pool в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e57c0-130"><a href="lync-server-2013-pool-table.md">Pool table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e57c0-131">Хранит имена пулов, к которым относятся данные метрики.</span><span class="sxs-lookup"><span data-stu-id="e57c0-131">Stores the names of pools to which metrics data belongs.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e57c0-132"><a href="lync-server-2013-device-table.md">Таблица Devices в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e57c0-132"><a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e57c0-133">Сохраняет устройства захвата и устройства отображения, которые используются в аудио-и видеовызовах.</span><span class="sxs-lookup"><span data-stu-id="e57c0-133">Stores capture devices and render devices which are used in an audio/video calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e57c0-134"><a href="lync-server-2013-devicedriver-table.md">Таблица Таблица devicedriver в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e57c0-134"><a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e57c0-135">Хранит драйвер устройства захвата и устройство отображения, которые используются в аудио-и видеовызовах.</span><span class="sxs-lookup"><span data-stu-id="e57c0-135">Stores driver for the capture device and the render device which are used in audio/video calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e57c0-136"><a href="lync-server-2013-conference-table.md">Таблица конференций в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e57c0-136"><a href="lync-server-2013-conference-table.md">Conference table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e57c0-137">Хранит коды URI конференций для сценариев конференц-связи или DialogID для других сценариев.</span><span class="sxs-lookup"><span data-stu-id="e57c0-137">Stores Conference URIs for conference scenarios or DialogID for other scenarios.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e57c0-138"><a href="lync-server-2013-sessioncorrelation-table.md">Таблица Таблица sessioncorrelation в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e57c0-138"><a href="lync-server-2013-sessioncorrelation-table.md">SessionCorrelation table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e57c0-139">Хранит CorrelationID для звонков по PSTN.</span><span class="sxs-lookup"><span data-stu-id="e57c0-139">Stores CorrelationID for PSTN calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e57c0-140"><a href="lync-server-2013-payloaddescription-table.md">Таблица Таблица payloaddescription в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e57c0-140"><a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e57c0-141">Сохраняет кодек, используемый в аудио-и видеовызовах.</span><span class="sxs-lookup"><span data-stu-id="e57c0-141">Stores the Codec used in audio/video calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e57c0-142"><a href="lync-server-2013-appliedbandwidthsource-table.md">Таблица Таблица appliedbandwidthsource в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e57c0-142"><a href="lync-server-2013-appliedbandwidthsource-table.md">AppliedBandwidthSource table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e57c0-143">Хранит источник пропускной способности, используемый в аудио-и видеовызовах.</span><span class="sxs-lookup"><span data-stu-id="e57c0-143">Stores the bandwidth source used in audio/video calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e57c0-144"><a href="lync-server-2013-macaddress-table.md">Таблица MacAddress в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e57c0-144"><a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e57c0-145">Хранит MAC-адрес конечных точек, участвующих в сеансах аудио и видео.</span><span class="sxs-lookup"><span data-stu-id="e57c0-145">Stores the MAC address of the endpoints participating in audio and video sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e57c0-146"><a href="lync-server-2013-dialog-table.md">Таблица диалогов в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e57c0-146"><a href="lync-server-2013-dialog-table.md">Dialog table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e57c0-147">Сохраняет идентификатор диалога для сеансов аудио и видео.</span><span class="sxs-lookup"><span data-stu-id="e57c0-147">Stores the Dialog ID of audio and video sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e57c0-148"><a href="lync-server-2013-region-table.md">Таблица Region в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e57c0-148"><a href="lync-server-2013-region-table.md">Region table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e57c0-149">Хранит область сети, определенную в параметре NC.</span><span class="sxs-lookup"><span data-stu-id="e57c0-149">Stores the network region defined in NCS setting.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e57c0-150"><a href="lync-server-2013-usersite-table.md">Таблица Таблица usersite в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e57c0-150"><a href="lync-server-2013-usersite-table.md">UserSite table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e57c0-151">Сохранение сетевого сайта, определенного в параметре NC.</span><span class="sxs-lookup"><span data-stu-id="e57c0-151">Stores the network site defined in NCS setting.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e57c0-152"><a href="lync-server-2013-subnet-table.md">Таблица Subnet в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e57c0-152"><a href="lync-server-2013-subnet-table.md">Subnet table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e57c0-153">Сохраняет подсеть, определенную в параметре NC.</span><span class="sxs-lookup"><span data-stu-id="e57c0-153">Stores the subnet defined in NCS setting.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e57c0-154"><a href="lync-server-2013-monitoredregionlink-table.md">Таблица Таблица monitoredregionlink в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e57c0-154"><a href="lync-server-2013-monitoredregionlink-table.md">MonitoredRegionLink table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e57c0-155">Хранит ссылку региона, определенную в параметре NC.</span><span class="sxs-lookup"><span data-stu-id="e57c0-155">Stores the region link defined in NCS setting.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e57c0-156"><a href="monitoredusersitelink-table.md">Таблица Таблица monitoredusersitelink</a></span><span class="sxs-lookup"><span data-stu-id="e57c0-156"><a href="monitoredusersitelink-table.md">MonitoredUserSiteLink table</a></span></span></p></td>
<td><p><span data-ttu-id="e57c0-157">Сохраняет сетевые связи сайтов, определенные в параметре NC.</span><span class="sxs-lookup"><span data-stu-id="e57c0-157">Stores the network site links defined in NCS setting.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e57c0-158"><a href="lync-server-2013-endpointsubnet-table.md">Таблица Таблица endpointsubnet в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e57c0-158"><a href="lync-server-2013-endpointsubnet-table.md">EndpointSubnet table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e57c0-159">Хранит подсеть конечной точки, участвующей в сеансе аудио и видео.</span><span class="sxs-lookup"><span data-stu-id="e57c0-159">Stores the subnet of the endpoint participating in an audio and video session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e57c0-160"><a href="lync-server-2013-server-table.md">Таблица Server в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e57c0-160"><a href="lync-server-2013-server-table.md">Server table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e57c0-161">Хранит полное доменное имя или IP-адрес сервера, через который проходит носитель.</span><span class="sxs-lookup"><span data-stu-id="e57c0-161">Stores the FQDN or IP address of the server the media goes through.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="e57c0-162">**Таблицы для данных метрик**</span><span class="sxs-lookup"><span data-stu-id="e57c0-162">**Tables for metrics data**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e57c0-163"><strong>Table</strong></span><span class="sxs-lookup"><span data-stu-id="e57c0-163"><strong>Table</strong></span></span></th>
<th><span data-ttu-id="e57c0-164"><strong>Описание</strong></span><span class="sxs-lookup"><span data-stu-id="e57c0-164"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e57c0-165"><a href="lync-server-2013-appsharingstream-table.md">Таблица Аппшарингстреам в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e57c0-165"><a href="lync-server-2013-appsharingstream-table.md">AppSharingStream table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e57c0-166">Сохранение метрик качества взаимодействия для сетевых потоков, используемых для общего доступа к приложениям.</span><span class="sxs-lookup"><span data-stu-id="e57c0-166">Stores Quality of Experience metrics for the network streams used for application sharing.</span></span> <span data-ttu-id="e57c0-167">Метрики качества взаимодействия для сетевых потоков, используемых для общего доступа к приложениям.</span><span class="sxs-lookup"><span data-stu-id="e57c0-167">Quality of Experience metrics for the network streams used for application sharing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e57c0-168"><a href="lync-server-2013-session-table.md">Таблица Sessions в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e57c0-168"><a href="lync-server-2013-session-table.md">Session table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e57c0-169">Хранит общие сведения о звуковом или аудио-или видеосеансе.</span><span class="sxs-lookup"><span data-stu-id="e57c0-169">Stores overall information about an audio or audio/video session.</span></span> <span data-ttu-id="e57c0-170">Сеанс определяется как диалоговое окно аудио-или видеоsip между двумя конечными точками.</span><span class="sxs-lookup"><span data-stu-id="e57c0-170">A session is defined as an audio or video SIP dialog between two endpoints.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e57c0-171"><a href="lync-server-2013-medialine-table.md">Таблица MediaLine в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e57c0-171"><a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e57c0-172">Хранит сведения о каждой строке мультимедиа в сеансе.</span><span class="sxs-lookup"><span data-stu-id="e57c0-172">Stores information about each media line in a session.</span></span> <span data-ttu-id="e57c0-173">Линия мультимедиа — это коллекция из одного или нескольких аудио-и видеопотоков.</span><span class="sxs-lookup"><span data-stu-id="e57c0-173">A media line is a collection of one or more audio and video streams.</span></span> <span data-ttu-id="e57c0-174">Как правило, одна линия мультимедиа будет иметь два потока: аудио или видео.</span><span class="sxs-lookup"><span data-stu-id="e57c0-174">Typically, a single media line will have two streams, either audio or video.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e57c0-175"><a href="lync-server-2013-audiostream-table.md">Таблица Таблица audiostream в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e57c0-175"><a href="lync-server-2013-audiostream-table.md">AudioStream table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e57c0-176">Сохраняет метрики качества звукового сопровождения для каждого звукового потока в линии мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="e57c0-176">Stores audio media quality metrics for each audio stream in the media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e57c0-177"><a href="lync-server-2013-audiosignal-table.md">Таблица Таблица audiosignal в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e57c0-177"><a href="lync-server-2013-audiosignal-table.md">AudioSignal table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e57c0-178">Сохраняет метрики качества звукового устройства в линии мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="e57c0-178">Stores audio media quality metrics in the media line.</span></span> <span data-ttu-id="e57c0-179">Это включает в себя метрики подавления эха и автоматические контрольные метрики (АУДИОПОТОКУ).</span><span class="sxs-lookup"><span data-stu-id="e57c0-179">This includes acoustic echo cancellation (AEC) and automatic gain control (AGC) metrics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e57c0-180"><a href="lync-server-2013-videostream-table.md">Таблица Таблица videostream в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e57c0-180"><a href="lync-server-2013-videostream-table.md">VideoStream table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e57c0-181">Хранит метрики качества мультимедиа для каждого звукового потока в линии мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="e57c0-181">Stores video media quality metrics for each audio stream in the media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e57c0-182"><a href="lync-server-2013-audioclientevent-table.md">Таблица Таблица audioclientevent в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e57c0-182"><a href="lync-server-2013-audioclientevent-table.md">AudioClientEvent table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e57c0-183">Хранит метрики качества аудио мультимедиа, собранные из клиентского события.</span><span class="sxs-lookup"><span data-stu-id="e57c0-183">Stores audio media quality metrics collected from the client event.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e57c0-184"><a href="lync-server-2013-videoclientevent-table.md">Таблица Таблица videoclientevent в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e57c0-184"><a href="lync-server-2013-videoclientevent-table.md">VideoClientEvent table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e57c0-185">Сохранение метрик качества мультимедиа, собранных из клиентского события.</span><span class="sxs-lookup"><span data-stu-id="e57c0-185">Stores video media quality metrics collected from the client event.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e57c0-186"><strong>Таблица Диагностикдата</strong></span><span class="sxs-lookup"><span data-stu-id="e57c0-186"><strong>DiagnosticData Table</strong></span></span></p></td>
<td><p><span data-ttu-id="e57c0-187">Хранение диагностических данных, предназначенных только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="e57c0-187">Stores diagnostic data which is for internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="e57c0-188">**Таблицы для сводных данных**</span><span class="sxs-lookup"><span data-stu-id="e57c0-188">**Tables for summary data**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e57c0-189"><strong>Table</strong></span><span class="sxs-lookup"><span data-stu-id="e57c0-189"><strong>Table</strong></span></span></th>
<th><span data-ttu-id="e57c0-190"><strong>Описание</strong></span><span class="sxs-lookup"><span data-stu-id="e57c0-190"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e57c0-191"><strong>Таблица Серверсуммари</strong></span><span class="sxs-lookup"><span data-stu-id="e57c0-191"><strong>ServerSummary Table</strong></span></span></p></td>
<td><p><span data-ttu-id="e57c0-192">Хранит сводные данные для серверов, эти данные используются только для отчетов о качестве взаимодействия (QoE).</span><span class="sxs-lookup"><span data-stu-id="e57c0-192">Stores summary data for the servers, these data is used for Quality of Experience (QoE) reporting only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e57c0-193"><strong>Таблица Усерсуммари</strong></span><span class="sxs-lookup"><span data-stu-id="e57c0-193"><strong>UserSummary Table</strong></span></span></p></td>
<td><p><span data-ttu-id="e57c0-194">Хранит сводные данные для пользователей, эти данные используются только для отчетов QoE.</span><span class="sxs-lookup"><span data-stu-id="e57c0-194">Stores summary data for users, these data is used for QoE reporting only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e57c0-195"><strong>Таблица Каллтипесуммари</strong></span><span class="sxs-lookup"><span data-stu-id="e57c0-195"><strong>CallTypeSummary Table</strong></span></span></p></td>
<td><p><span data-ttu-id="e57c0-196">Хранение сводных данных для типов вызовов эти данные используются только для отчетов QoE.</span><span class="sxs-lookup"><span data-stu-id="e57c0-196">Store summary data for call types, these data is used for QoE reporting only.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="e57c0-197">**Таблицы для внутреннего использования сервером мониторинга**</span><span class="sxs-lookup"><span data-stu-id="e57c0-197">**Tables for Internal Use by Monitoring Server**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e57c0-198"><strong>Table</strong></span><span class="sxs-lookup"><span data-stu-id="e57c0-198"><strong>Table</strong></span></span></th>
<th><span data-ttu-id="e57c0-199"><strong>Описание</strong></span><span class="sxs-lookup"><span data-stu-id="e57c0-199"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e57c0-200"><strong>дбконфигдатетиме</strong></span><span class="sxs-lookup"><span data-stu-id="e57c0-200"><strong>DbConfigDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e57c0-201">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="e57c0-201">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e57c0-202"><strong>дбконфигинт</strong></span><span class="sxs-lookup"><span data-stu-id="e57c0-202"><strong>DbConfigInt</strong></span></span></p></td>
<td><p><span data-ttu-id="e57c0-203">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="e57c0-203">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e57c0-204"><strong>FrontEnd Table</strong></span><span class="sxs-lookup"><span data-stu-id="e57c0-204"><strong>FrontEnd Table</strong></span></span></p></td>
<td><p><span data-ttu-id="e57c0-205">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="e57c0-205">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e57c0-206"><strong>Task Table</strong></span><span class="sxs-lookup"><span data-stu-id="e57c0-206"><strong>Task Table</strong></span></span></p></td>
<td><p><span data-ttu-id="e57c0-207">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="e57c0-207">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e57c0-208"><strong>суммаритаблеконфигуратион</strong></span><span class="sxs-lookup"><span data-stu-id="e57c0-208"><strong>SummaryTableConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="e57c0-209">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="e57c0-209">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e57c0-210"><strong>дберрормессаже</strong></span><span class="sxs-lookup"><span data-stu-id="e57c0-210"><strong>DbErrorMessage</strong></span></span></p></td>
<td><p><span data-ttu-id="e57c0-211">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="e57c0-211">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e57c0-212"><strong>метрикссрешолд</strong></span><span class="sxs-lookup"><span data-stu-id="e57c0-212"><strong>MetricsThreshold</strong></span></span></p></td>
<td><p><span data-ttu-id="e57c0-213">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="e57c0-213">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e57c0-214"><strong>дайлигхтсавингеарс</strong></span><span class="sxs-lookup"><span data-stu-id="e57c0-214"><strong>DaylightSavingYears</strong></span></span></p></td>
<td><p><span data-ttu-id="e57c0-215">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="e57c0-215">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e57c0-216"><strong>тимезонеконфигуратион</strong></span><span class="sxs-lookup"><span data-stu-id="e57c0-216"><strong>TimeZoneConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="e57c0-217">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="e57c0-217">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e57c0-218"><strong>TimeZones</strong></span><span class="sxs-lookup"><span data-stu-id="e57c0-218"><strong>TimeZones</strong></span></span></p></td>
<td><p><span data-ttu-id="e57c0-219">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="e57c0-219">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e57c0-220"><strong>Таблица CallSummary</strong></span><span class="sxs-lookup"><span data-stu-id="e57c0-220"><strong>CallSummary Table</strong></span></span></p></td>
<td><p><span data-ttu-id="e57c0-221">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="e57c0-221">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e57c0-222"><strong>Таблица Девицекаллсумари</strong></span><span class="sxs-lookup"><span data-stu-id="e57c0-222"><strong>DeviceCallSumary Table</strong></span></span></p></td>
<td><p><span data-ttu-id="e57c0-223">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="e57c0-223">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e57c0-224"><strong>Таблица Tenant</strong></span><span class="sxs-lookup"><span data-stu-id="e57c0-224"><strong>Tenant Table</strong></span></span></p></td>
<td><p><span data-ttu-id="e57c0-225">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="e57c0-225">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e57c0-226"><strong>видеокаллсуммаритабле</strong></span><span class="sxs-lookup"><span data-stu-id="e57c0-226"><strong>VideoCallSummaryTable</strong></span></span></p></td>
<td><p><span data-ttu-id="e57c0-227">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="e57c0-227">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e57c0-228"><strong>аскаллсуммаритабле</strong></span><span class="sxs-lookup"><span data-stu-id="e57c0-228"><strong>ASCallSummaryTable</strong></span></span></p></td>
<td><p><span data-ttu-id="e57c0-229">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="e57c0-229">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

