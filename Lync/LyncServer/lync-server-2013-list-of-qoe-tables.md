---
title: 'Lync Server 2013: список таблиц QoE'
description: 'Lync Server 2013: список таблиц QoE.'
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
ms.openlocfilehash: 871babf246f616d306a03f84f9134605dd595999
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550045"
---
# <a name="list-of-qoe-tables-in-lync-server-2013"></a><span data-ttu-id="a42d5-103">Список таблиц QoE в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a42d5-103">List of QoE tables in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a42d5-104">_**Последнее изменение темы:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="a42d5-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="a42d5-105">Схема базы данных состоит из следующих таблиц.</span><span class="sxs-lookup"><span data-stu-id="a42d5-105">The database schema consists of the following tables.</span></span>

<span data-ttu-id="a42d5-106">**Вспомогательные таблицы**</span><span class="sxs-lookup"><span data-stu-id="a42d5-106">**Supporting Tables**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a42d5-107"><strong>Table</strong></span><span class="sxs-lookup"><span data-stu-id="a42d5-107"><strong>Table</strong></span></span></th>
<th><span data-ttu-id="a42d5-108"><strong>Описание</strong></span><span class="sxs-lookup"><span data-stu-id="a42d5-108"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a42d5-109"><a href="lync-server-2013-appsharingmetricsthreshold-table.md">Таблица Аппшарингметрикссрешолд в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a42d5-109"><a href="lync-server-2013-appsharingmetricsthreshold-table.md">AppSharingMetricsThreshold table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a42d5-110">Сохранение оптимальных и приемлемых значений для показателей качества взаимодействия, используемых совместно с общим доступом к приложениям.</span><span class="sxs-lookup"><span data-stu-id="a42d5-110">Stores optimal and acceptable values for the Quality of Experience metrics used with application sharing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a42d5-111"><a href="lync-server-2013-codecdescription-table.md">Таблица Кодекдескриптион в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a42d5-111"><a href="lync-server-2013-codecdescription-table.md">CodecDescription table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a42d5-112">Сопоставляет уникальные идентификаторы кодека с соответствующим кодеком.</span><span class="sxs-lookup"><span data-stu-id="a42d5-112">Maps unique codec identifiers to their corresponding codec.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a42d5-113"><a href="lync-server-2013-ipaddress-table.md">IP-адрес таблицы в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a42d5-113"><a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a42d5-114">Сопоставляет IP-адреса с уникальными идентификаторами IP-адресов, используемыми в других местах базы данных качества взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="a42d5-114">Maps IP addresses to the unique IP address identifiers used elsewhere in the Quality of Experience database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a42d5-115"><a href="lync-server-2013-networkconnectiondetail-table.md">Таблица Нетворкконнектиондетаил в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a42d5-115"><a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a42d5-116">Сопоставляет типы сетевых подключений с идентификаторами сетевых подключений, используемыми в других местах базы данных качества взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="a42d5-116">Maps network connection types to the network connection identifiers used elsewhere in the Quality of Experience database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a42d5-117"><a href="lync-server-2013-purgesettings-table-qoe.md">Таблица Таблица purgesettings (QoE) в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a42d5-117"><a href="lync-server-2013-purgesettings-table-qoe.md">PurgeSettings table (QoE) in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a42d5-118">Хранит сведения, указывающие, будут ли (и когда) устаревшие записи качества взаимодействия автоматически удаляться из базы данных QoE.</span><span class="sxs-lookup"><span data-stu-id="a42d5-118">Stores information that specifies if (and when) outdated Quality of Experience records will automatically be deleted from the QoE database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a42d5-119"><a href="lync-server-2013-traceroute-table.md">Таблица Трацерауте в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a42d5-119"><a href="lync-server-2013-traceroute-table.md">TraceRoute table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a42d5-120">Хранит сведения о маршрутизации для вызовов.</span><span class="sxs-lookup"><span data-stu-id="a42d5-120">Stores routing information for calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a42d5-121"><a href="lync-server-2013-useragentdef-table-qoe.md">Таблица Таблица useragentdef (QoE) в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a42d5-121"><a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a42d5-122">Привязка идентификаторов агента пользователя к описательным именам агента.</span><span class="sxs-lookup"><span data-stu-id="a42d5-122">Maps user agent identifiers to the agent’s descriptive names.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a42d5-123"><a href="lync-server-2013-videometricsthreshold-table.md">Таблица Таблица videometricsthreshold в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a42d5-123"><a href="lync-server-2013-videometricsthreshold-table.md">VideoMetricsThreshold table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a42d5-124">Сохранение оптимальных и приемлемых значений для показателей качества взаимодействия, используемых с видеовызовами.</span><span class="sxs-lookup"><span data-stu-id="a42d5-124">Stores optimal and acceptable values for the Quality of Experience metrics used with video calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a42d5-125"><a href="lync-server-2013-useragent-table.md">Таблица UserAgent в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a42d5-125"><a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a42d5-126">Сохраняет строки и типы агентов пользователя для протокола SIP (UA), используемые в сеансах аудио и видео.</span><span class="sxs-lookup"><span data-stu-id="a42d5-126">Stores Session Initiation Protocol (SIP) User Agent (UA) strings and UA types used in audio and video sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a42d5-127"><a href="lync-server-2013-user-table.md">Таблица user в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a42d5-127"><a href="lync-server-2013-user-table.md">User table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a42d5-128">Хранение URI пользователей, конференций и телефонов, используемых в сеансах аудио и видео.</span><span class="sxs-lookup"><span data-stu-id="a42d5-128">Stores user, conference, and phone URIs used in audio and video sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a42d5-129"><a href="lync-server-2013-endpoint-table.md">Таблица конечной точки в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a42d5-129"><a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a42d5-130">Хранит полные доменные имена конечных точек, участвующих в сеансах аудио и видео.</span><span class="sxs-lookup"><span data-stu-id="a42d5-130">Stores FQDN computer names of endpoints participating in audio and video sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a42d5-131"><a href="lync-server-2013-pool-table.md">Таблица pool в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a42d5-131"><a href="lync-server-2013-pool-table.md">Pool table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a42d5-132">Хранит имена пулов, к которым относятся данные метрики.</span><span class="sxs-lookup"><span data-stu-id="a42d5-132">Stores the names of pools to which metrics data belongs.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a42d5-133"><a href="lync-server-2013-device-table.md">Таблица Devices в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a42d5-133"><a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a42d5-134">Сохраняет устройства захвата и устройства отображения, которые используются в аудио-и видеовызовах.</span><span class="sxs-lookup"><span data-stu-id="a42d5-134">Stores capture devices and render devices which are used in an audio/video calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a42d5-135"><a href="lync-server-2013-devicedriver-table.md">Таблица Таблица devicedriver в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a42d5-135"><a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a42d5-136">Хранит драйвер устройства захвата и устройство отображения, которые используются в аудио-и видеовызовах.</span><span class="sxs-lookup"><span data-stu-id="a42d5-136">Stores driver for the capture device and the render device which are used in audio/video calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a42d5-137"><a href="lync-server-2013-conference-table.md">Таблица конференций в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a42d5-137"><a href="lync-server-2013-conference-table.md">Conference table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a42d5-138">Хранит коды URI конференций для сценариев конференц-связи или DialogID для других сценариев.</span><span class="sxs-lookup"><span data-stu-id="a42d5-138">Stores Conference URIs for conference scenarios or DialogID for other scenarios.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a42d5-139"><a href="lync-server-2013-sessioncorrelation-table.md">Таблица Таблица sessioncorrelation в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a42d5-139"><a href="lync-server-2013-sessioncorrelation-table.md">SessionCorrelation table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a42d5-140">Хранит CorrelationID для звонков по PSTN.</span><span class="sxs-lookup"><span data-stu-id="a42d5-140">Stores CorrelationID for PSTN calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a42d5-141"><a href="lync-server-2013-payloaddescription-table.md">Таблица Таблица payloaddescription в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a42d5-141"><a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a42d5-142">Сохраняет кодек, используемый в аудио-и видеовызовах.</span><span class="sxs-lookup"><span data-stu-id="a42d5-142">Stores the Codec used in audio/video calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a42d5-143"><a href="lync-server-2013-appliedbandwidthsource-table.md">Таблица Таблица appliedbandwidthsource в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a42d5-143"><a href="lync-server-2013-appliedbandwidthsource-table.md">AppliedBandwidthSource table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a42d5-144">Хранит источник пропускной способности, используемый в аудио-и видеовызовах.</span><span class="sxs-lookup"><span data-stu-id="a42d5-144">Stores the bandwidth source used in audio/video calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a42d5-145"><a href="lync-server-2013-macaddress-table.md">Таблица MacAddress в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a42d5-145"><a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a42d5-146">Хранит MAC-адрес конечных точек, участвующих в сеансах аудио и видео.</span><span class="sxs-lookup"><span data-stu-id="a42d5-146">Stores the MAC address of the endpoints participating in audio and video sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a42d5-147"><a href="lync-server-2013-dialog-table.md">Таблица диалогов в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a42d5-147"><a href="lync-server-2013-dialog-table.md">Dialog table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a42d5-148">Сохраняет идентификатор диалога для сеансов аудио и видео.</span><span class="sxs-lookup"><span data-stu-id="a42d5-148">Stores the Dialog ID of audio and video sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a42d5-149"><a href="lync-server-2013-region-table.md">Таблица Region в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a42d5-149"><a href="lync-server-2013-region-table.md">Region table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a42d5-150">Хранит область сети, определенную в параметре NC.</span><span class="sxs-lookup"><span data-stu-id="a42d5-150">Stores the network region defined in NCS setting.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a42d5-151"><a href="lync-server-2013-usersite-table.md">Таблица Таблица usersite в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a42d5-151"><a href="lync-server-2013-usersite-table.md">UserSite table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a42d5-152">Сохранение сетевого сайта, определенного в параметре NC.</span><span class="sxs-lookup"><span data-stu-id="a42d5-152">Stores the network site defined in NCS setting.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a42d5-153"><a href="lync-server-2013-subnet-table.md">Таблица Subnet в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a42d5-153"><a href="lync-server-2013-subnet-table.md">Subnet table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a42d5-154">Сохраняет подсеть, определенную в параметре NC.</span><span class="sxs-lookup"><span data-stu-id="a42d5-154">Stores the subnet defined in NCS setting.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a42d5-155"><a href="lync-server-2013-monitoredregionlink-table.md">Таблица Таблица monitoredregionlink в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a42d5-155"><a href="lync-server-2013-monitoredregionlink-table.md">MonitoredRegionLink table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a42d5-156">Хранит ссылку региона, определенную в параметре NC.</span><span class="sxs-lookup"><span data-stu-id="a42d5-156">Stores the region link defined in NCS setting.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a42d5-157"><a href="monitoredusersitelink-table.md">Таблица Таблица monitoredusersitelink</a></span><span class="sxs-lookup"><span data-stu-id="a42d5-157"><a href="monitoredusersitelink-table.md">MonitoredUserSiteLink table</a></span></span></p></td>
<td><p><span data-ttu-id="a42d5-158">Сохраняет сетевые связи сайтов, определенные в параметре NC.</span><span class="sxs-lookup"><span data-stu-id="a42d5-158">Stores the network site links defined in NCS setting.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a42d5-159"><a href="lync-server-2013-endpointsubnet-table.md">Таблица Таблица endpointsubnet в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a42d5-159"><a href="lync-server-2013-endpointsubnet-table.md">EndpointSubnet table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a42d5-160">Хранит подсеть конечной точки, участвующей в сеансе аудио и видео.</span><span class="sxs-lookup"><span data-stu-id="a42d5-160">Stores the subnet of the endpoint participating in an audio and video session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a42d5-161"><a href="lync-server-2013-server-table.md">Таблица Server в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a42d5-161"><a href="lync-server-2013-server-table.md">Server table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a42d5-162">Хранит полное доменное имя или IP-адрес сервера, через который проходит носитель.</span><span class="sxs-lookup"><span data-stu-id="a42d5-162">Stores the FQDN or IP address of the server the media goes through.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a42d5-163">**Таблицы для данных метрик**</span><span class="sxs-lookup"><span data-stu-id="a42d5-163">**Tables for metrics data**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a42d5-164"><strong>Table</strong></span><span class="sxs-lookup"><span data-stu-id="a42d5-164"><strong>Table</strong></span></span></th>
<th><span data-ttu-id="a42d5-165"><strong>Описание</strong></span><span class="sxs-lookup"><span data-stu-id="a42d5-165"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a42d5-166"><a href="lync-server-2013-appsharingstream-table.md">Таблица Аппшарингстреам в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a42d5-166"><a href="lync-server-2013-appsharingstream-table.md">AppSharingStream table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a42d5-167">Сохранение метрик качества взаимодействия для сетевых потоков, используемых для общего доступа к приложениям.</span><span class="sxs-lookup"><span data-stu-id="a42d5-167">Stores Quality of Experience metrics for the network streams used for application sharing.</span></span> <span data-ttu-id="a42d5-168">Метрики качества взаимодействия для сетевых потоков, используемых для общего доступа к приложениям.</span><span class="sxs-lookup"><span data-stu-id="a42d5-168">Quality of Experience metrics for the network streams used for application sharing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a42d5-169"><a href="lync-server-2013-session-table.md">Таблица Sessions в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a42d5-169"><a href="lync-server-2013-session-table.md">Session table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a42d5-170">Хранит общие сведения о звуковом или аудио-или видеосеансе.</span><span class="sxs-lookup"><span data-stu-id="a42d5-170">Stores overall information about an audio or audio/video session.</span></span> <span data-ttu-id="a42d5-171">Сеанс определяется как диалоговое окно аудио-или видеоsip между двумя конечными точками.</span><span class="sxs-lookup"><span data-stu-id="a42d5-171">A session is defined as an audio or video SIP dialog between two endpoints.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a42d5-172"><a href="lync-server-2013-medialine-table.md">Таблица MediaLine в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a42d5-172"><a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a42d5-173">Хранит сведения о каждой строке мультимедиа в сеансе.</span><span class="sxs-lookup"><span data-stu-id="a42d5-173">Stores information about each media line in a session.</span></span> <span data-ttu-id="a42d5-174">Линия мультимедиа — это коллекция из одного или нескольких аудио-и видеопотоков.</span><span class="sxs-lookup"><span data-stu-id="a42d5-174">A media line is a collection of one or more audio and video streams.</span></span> <span data-ttu-id="a42d5-175">Как правило, одна линия мультимедиа будет иметь два потока: аудио или видео.</span><span class="sxs-lookup"><span data-stu-id="a42d5-175">Typically, a single media line will have two streams, either audio or video.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a42d5-176"><a href="lync-server-2013-audiostream-table.md">Таблица Таблица audiostream в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a42d5-176"><a href="lync-server-2013-audiostream-table.md">AudioStream table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a42d5-177">Сохраняет метрики качества звукового сопровождения для каждого звукового потока в линии мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="a42d5-177">Stores audio media quality metrics for each audio stream in the media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a42d5-178"><a href="lync-server-2013-audiosignal-table.md">Таблица Таблица audiosignal в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a42d5-178"><a href="lync-server-2013-audiosignal-table.md">AudioSignal table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a42d5-179">Сохраняет метрики качества звукового устройства в линии мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="a42d5-179">Stores audio media quality metrics in the media line.</span></span> <span data-ttu-id="a42d5-180">Это включает в себя метрики подавления эха и автоматические контрольные метрики (АУДИОПОТОКУ).</span><span class="sxs-lookup"><span data-stu-id="a42d5-180">This includes acoustic echo cancellation (AEC) and automatic gain control (AGC) metrics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a42d5-181"><a href="lync-server-2013-videostream-table.md">Таблица Таблица videostream в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a42d5-181"><a href="lync-server-2013-videostream-table.md">VideoStream table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a42d5-182">Хранит метрики качества мультимедиа для каждого звукового потока в линии мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="a42d5-182">Stores video media quality metrics for each audio stream in the media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a42d5-183"><a href="lync-server-2013-audioclientevent-table.md">Таблица Таблица audioclientevent в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a42d5-183"><a href="lync-server-2013-audioclientevent-table.md">AudioClientEvent table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a42d5-184">Хранит метрики качества аудио мультимедиа, собранные из клиентского события.</span><span class="sxs-lookup"><span data-stu-id="a42d5-184">Stores audio media quality metrics collected from the client event.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a42d5-185"><a href="lync-server-2013-videoclientevent-table.md">Таблица Таблица videoclientevent в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a42d5-185"><a href="lync-server-2013-videoclientevent-table.md">VideoClientEvent table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a42d5-186">Сохранение метрик качества мультимедиа, собранных из клиентского события.</span><span class="sxs-lookup"><span data-stu-id="a42d5-186">Stores video media quality metrics collected from the client event.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a42d5-187"><strong>Таблица Диагностикдата</strong></span><span class="sxs-lookup"><span data-stu-id="a42d5-187"><strong>DiagnosticData Table</strong></span></span></p></td>
<td><p><span data-ttu-id="a42d5-188">Хранение диагностических данных, предназначенных только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="a42d5-188">Stores diagnostic data which is for internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a42d5-189">**Таблицы для сводных данных**</span><span class="sxs-lookup"><span data-stu-id="a42d5-189">**Tables for summary data**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a42d5-190"><strong>Table</strong></span><span class="sxs-lookup"><span data-stu-id="a42d5-190"><strong>Table</strong></span></span></th>
<th><span data-ttu-id="a42d5-191"><strong>Описание</strong></span><span class="sxs-lookup"><span data-stu-id="a42d5-191"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a42d5-192"><strong>Таблица Серверсуммари</strong></span><span class="sxs-lookup"><span data-stu-id="a42d5-192"><strong>ServerSummary Table</strong></span></span></p></td>
<td><p><span data-ttu-id="a42d5-193">Хранит сводные данные для серверов, эти данные используются только для отчетов о качестве взаимодействия (QoE).</span><span class="sxs-lookup"><span data-stu-id="a42d5-193">Stores summary data for the servers, these data is used for Quality of Experience (QoE) reporting only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a42d5-194"><strong>Таблица Усерсуммари</strong></span><span class="sxs-lookup"><span data-stu-id="a42d5-194"><strong>UserSummary Table</strong></span></span></p></td>
<td><p><span data-ttu-id="a42d5-195">Хранит сводные данные для пользователей, эти данные используются только для отчетов QoE.</span><span class="sxs-lookup"><span data-stu-id="a42d5-195">Stores summary data for users, these data is used for QoE reporting only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a42d5-196"><strong>Таблица Каллтипесуммари</strong></span><span class="sxs-lookup"><span data-stu-id="a42d5-196"><strong>CallTypeSummary Table</strong></span></span></p></td>
<td><p><span data-ttu-id="a42d5-197">Хранение сводных данных для типов вызовов эти данные используются только для отчетов QoE.</span><span class="sxs-lookup"><span data-stu-id="a42d5-197">Store summary data for call types, these data is used for QoE reporting only.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a42d5-198">**Таблицы для внутреннего использования сервером мониторинга**</span><span class="sxs-lookup"><span data-stu-id="a42d5-198">**Tables for Internal Use by Monitoring Server**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a42d5-199"><strong>Table</strong></span><span class="sxs-lookup"><span data-stu-id="a42d5-199"><strong>Table</strong></span></span></th>
<th><span data-ttu-id="a42d5-200"><strong>Описание</strong></span><span class="sxs-lookup"><span data-stu-id="a42d5-200"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a42d5-201"><strong>дбконфигдатетиме</strong></span><span class="sxs-lookup"><span data-stu-id="a42d5-201"><strong>DbConfigDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a42d5-202">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="a42d5-202">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a42d5-203"><strong>дбконфигинт</strong></span><span class="sxs-lookup"><span data-stu-id="a42d5-203"><strong>DbConfigInt</strong></span></span></p></td>
<td><p><span data-ttu-id="a42d5-204">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="a42d5-204">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a42d5-205"><strong>FrontEnd Table</strong></span><span class="sxs-lookup"><span data-stu-id="a42d5-205"><strong>FrontEnd Table</strong></span></span></p></td>
<td><p><span data-ttu-id="a42d5-206">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="a42d5-206">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a42d5-207"><strong>Task Table</strong></span><span class="sxs-lookup"><span data-stu-id="a42d5-207"><strong>Task Table</strong></span></span></p></td>
<td><p><span data-ttu-id="a42d5-208">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="a42d5-208">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a42d5-209"><strong>суммаритаблеконфигуратион</strong></span><span class="sxs-lookup"><span data-stu-id="a42d5-209"><strong>SummaryTableConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="a42d5-210">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="a42d5-210">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a42d5-211"><strong>дберрормессаже</strong></span><span class="sxs-lookup"><span data-stu-id="a42d5-211"><strong>DbErrorMessage</strong></span></span></p></td>
<td><p><span data-ttu-id="a42d5-212">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="a42d5-212">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a42d5-213"><strong>метрикссрешолд</strong></span><span class="sxs-lookup"><span data-stu-id="a42d5-213"><strong>MetricsThreshold</strong></span></span></p></td>
<td><p><span data-ttu-id="a42d5-214">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="a42d5-214">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a42d5-215"><strong>дайлигхтсавингеарс</strong></span><span class="sxs-lookup"><span data-stu-id="a42d5-215"><strong>DaylightSavingYears</strong></span></span></p></td>
<td><p><span data-ttu-id="a42d5-216">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="a42d5-216">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a42d5-217"><strong>тимезонеконфигуратион</strong></span><span class="sxs-lookup"><span data-stu-id="a42d5-217"><strong>TimeZoneConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="a42d5-218">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="a42d5-218">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a42d5-219"><strong>TimeZones</strong></span><span class="sxs-lookup"><span data-stu-id="a42d5-219"><strong>TimeZones</strong></span></span></p></td>
<td><p><span data-ttu-id="a42d5-220">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="a42d5-220">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a42d5-221"><strong>Таблица CallSummary</strong></span><span class="sxs-lookup"><span data-stu-id="a42d5-221"><strong>CallSummary Table</strong></span></span></p></td>
<td><p><span data-ttu-id="a42d5-222">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="a42d5-222">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a42d5-223"><strong>Таблица Девицекаллсумари</strong></span><span class="sxs-lookup"><span data-stu-id="a42d5-223"><strong>DeviceCallSumary Table</strong></span></span></p></td>
<td><p><span data-ttu-id="a42d5-224">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="a42d5-224">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a42d5-225"><strong>Таблица Tenant</strong></span><span class="sxs-lookup"><span data-stu-id="a42d5-225"><strong>Tenant Table</strong></span></span></p></td>
<td><p><span data-ttu-id="a42d5-226">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="a42d5-226">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a42d5-227"><strong>видеокаллсуммаритабле</strong></span><span class="sxs-lookup"><span data-stu-id="a42d5-227"><strong>VideoCallSummaryTable</strong></span></span></p></td>
<td><p><span data-ttu-id="a42d5-228">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="a42d5-228">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a42d5-229"><strong>аскаллсуммаритабле</strong></span><span class="sxs-lookup"><span data-stu-id="a42d5-229"><strong>ASCallSummaryTable</strong></span></span></p></td>
<td><p><span data-ttu-id="a42d5-230">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="a42d5-230">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

