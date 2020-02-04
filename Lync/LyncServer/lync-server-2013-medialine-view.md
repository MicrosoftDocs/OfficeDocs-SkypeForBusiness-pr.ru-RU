---
title: 'Lync Server 2013: представление Медиалине'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: MediaLine view
ms:assetid: 132eca13-8913-4218-9eff-4960ced8c3dc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687972(v=OCS.15)
ms:contentKeyID: 49733560
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7aebd16d8bd2efaf8deeb6752deeb199411ab125
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763007"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="medialine-view-in-lync-server-2013"></a><span data-ttu-id="4f046-102">Медиалине представления в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4f046-102">MediaLine view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4f046-103">_**Тема последнего изменения:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="4f046-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="4f046-104">В представлении Медиалине хранятся сведения о каждой строке мультимедиа в базе данных.</span><span class="sxs-lookup"><span data-stu-id="4f046-104">The MediaLine View stores information about each media line in the database.</span></span> <span data-ttu-id="4f046-105">Один звуковой сеанс обычно состоит из одной линии звукового файла.</span><span class="sxs-lookup"><span data-stu-id="4f046-105">One audio session typically contains one audio media line.</span></span> <span data-ttu-id="4f046-106">Один из звуковых и видеофайлов (A/V) обычно состоит из одной линии звукового файла и одной линии видеоклипа; Тем не менее, в этом сеансе могут содержаться две строки видеофайла, если используется устройство конференц-связи или если используется представление коллекции.</span><span class="sxs-lookup"><span data-stu-id="4f046-106">One audio and video (A/V) session typically contains one audio media line and one video media line; however, the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span> <span data-ttu-id="4f046-107">Это представление было представлено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4f046-107">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4f046-108">Столбец</span><span class="sxs-lookup"><span data-stu-id="4f046-108">Column</span></span></th>
<th><span data-ttu-id="4f046-109">Тип данных</span><span class="sxs-lookup"><span data-stu-id="4f046-109">Data Type</span></span></th>
<th><span data-ttu-id="4f046-110">сведения</span><span class="sxs-lookup"><span data-stu-id="4f046-110">details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4f046-111">конференцедатетиме</span><span class="sxs-lookup"><span data-stu-id="4f046-111">ConferenceDateTime</span></span></p></td>
<td><p><span data-ttu-id="4f046-112">datetime</span><span class="sxs-lookup"><span data-stu-id="4f046-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="4f046-113">На которую ссылается <a href="lync-server-2013-medialine-table.md">Таблица медиалине в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="4f046-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f046-114">сессионсек</span><span class="sxs-lookup"><span data-stu-id="4f046-114">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="4f046-115">целое</span><span class="sxs-lookup"><span data-stu-id="4f046-115">int</span></span></p></td>
<td><p><span data-ttu-id="4f046-116">На которую ссылается <a href="lync-server-2013-medialine-table.md">Таблица медиалине в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="4f046-116">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f046-117">медиалинелабел</span><span class="sxs-lookup"><span data-stu-id="4f046-117">MediaLineLabel</span></span></p></td>
<td><p><span data-ttu-id="4f046-118">tinyint</span><span class="sxs-lookup"><span data-stu-id="4f046-118">tinyint</span></span></p></td>
<td><p><span data-ttu-id="4f046-119">На которую ссылается <a href="lync-server-2013-medialine-table.md">Таблица медиалине в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="4f046-119">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f046-120">каллерицеварнингфлагс</span><span class="sxs-lookup"><span data-stu-id="4f046-120">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="4f046-121">целое</span><span class="sxs-lookup"><span data-stu-id="4f046-121">int</span></span></p></td>
<td><p><span data-ttu-id="4f046-122">Сведения о процессе интерактивной установки подключения (ICE), описанные в разделе Флаги BITS для вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="4f046-122">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller.</span></span> <span data-ttu-id="4f046-123">Подробности можно найти в спецификации серверного протокола контроля качества обслуживания.</span><span class="sxs-lookup"><span data-stu-id="4f046-123">For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f046-124">каллиицеварнингфлагс</span><span class="sxs-lookup"><span data-stu-id="4f046-124">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="4f046-125">целое</span><span class="sxs-lookup"><span data-stu-id="4f046-125">int</span></span></p></td>
<td><p><span data-ttu-id="4f046-126">Сведения о процессе установки интерактивной связи (ICE), описанные в флагах BITS для вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="4f046-126">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee.</span></span> <span data-ttu-id="4f046-127">Подробности можно найти в спецификации серверного протокола контроля качества обслуживания.</span><span class="sxs-lookup"><span data-stu-id="4f046-127">For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f046-128">Безопасность</span><span class="sxs-lookup"><span data-stu-id="4f046-128">Security</span></span></p></td>
<td><p><span data-ttu-id="4f046-129">tinyint</span><span class="sxs-lookup"><span data-stu-id="4f046-129">tinyint</span></span></p></td>
<td><p><span data-ttu-id="4f046-130">Профиль безопасности используется.</span><span class="sxs-lookup"><span data-stu-id="4f046-130">Security profile in use.</span></span> <span data-ttu-id="4f046-131">0 — NONE, 1 — SRTP, 2 — v1.</span><span class="sxs-lookup"><span data-stu-id="4f046-131">0 is NONE, 1 is SRTP, 2 is V1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f046-132">Transport</span><span class="sxs-lookup"><span data-stu-id="4f046-132">Transport</span></span></p></td>
<td><p><span data-ttu-id="4f046-133">tinyint</span><span class="sxs-lookup"><span data-stu-id="4f046-133">tinyint</span></span></p></td>
<td><p><span data-ttu-id="4f046-134">Тип транспорта.</span><span class="sxs-lookup"><span data-stu-id="4f046-134">Transport type.</span></span> <span data-ttu-id="4f046-135">0 — это UDP, а 1 — TCP.</span><span class="sxs-lookup"><span data-stu-id="4f046-135">0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f046-136">каллерипаддр</span><span class="sxs-lookup"><span data-stu-id="4f046-136">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="4f046-137">var (50)</span><span class="sxs-lookup"><span data-stu-id="4f046-137">var(50)</span></span></p></td>
<td><p><span data-ttu-id="4f046-138">IP-адрес вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="4f046-138">IP address of the caller.</span></span> <span data-ttu-id="4f046-139">Это может быть либо адрес IPv4, либо IPv6.</span><span class="sxs-lookup"><span data-stu-id="4f046-139">This can be either an IPv4 or IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f046-140">каллерпорт</span><span class="sxs-lookup"><span data-stu-id="4f046-140">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="4f046-141">целое</span><span class="sxs-lookup"><span data-stu-id="4f046-141">int</span></span></p></td>
<td><p><span data-ttu-id="4f046-142">Порт, используемый вызывающим абонентом.</span><span class="sxs-lookup"><span data-stu-id="4f046-142">Port used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f046-143">каллеринсиде</span><span class="sxs-lookup"><span data-stu-id="4f046-143">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="4f046-144">бит</span><span class="sxs-lookup"><span data-stu-id="4f046-144">bit</span></span></p></td>
<td><p><span data-ttu-id="4f046-145">Указывает, находится ли вызывающий абонент в сети Организации.</span><span class="sxs-lookup"><span data-stu-id="4f046-145">Indicates whether or not the caller is inside the organization network.</span></span> <span data-ttu-id="4f046-146">1 означает, что вызывающий абонент входит в корпоративную сеть.</span><span class="sxs-lookup"><span data-stu-id="4f046-146">1 means that the caller is inside the enterprise network.</span></span> <span data-ttu-id="4f046-147">0 означает, что вызывающий абонент находится за пределами сети.</span><span class="sxs-lookup"><span data-stu-id="4f046-147">0 means that the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f046-148">каллермакаддресс</span><span class="sxs-lookup"><span data-stu-id="4f046-148">CallerMacAddress</span></span></p></td>
<td><p><span data-ttu-id="4f046-149">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="4f046-149">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4f046-150">MAC-адрес сетевого интерфейса, используемого вызывающим абонентом.</span><span class="sxs-lookup"><span data-stu-id="4f046-150">MAC address of network interface used by caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f046-151">каллеррелайипаддр</span><span class="sxs-lookup"><span data-stu-id="4f046-151">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="4f046-152">var (50)</span><span class="sxs-lookup"><span data-stu-id="4f046-152">var(50)</span></span></p></td>
<td><p><span data-ttu-id="4f046-153">IP-адрес службы EDGE (/V), используемой вызывающим абонентом.</span><span class="sxs-lookup"><span data-stu-id="4f046-153">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="4f046-154">Дополнительные сведения приведены в <a href="lync-server-2013-ipaddress-table.md">таблице IP-адрес в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="4f046-154">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f046-155">каллирелайпорт</span><span class="sxs-lookup"><span data-stu-id="4f046-155">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="4f046-156">целое</span><span class="sxs-lookup"><span data-stu-id="4f046-156">int</span></span></p></td>
<td><p><span data-ttu-id="4f046-157">Порт, используемый в службе EDGE (A/V), используемой вызывающим абонентом.</span><span class="sxs-lookup"><span data-stu-id="4f046-157">Port used on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f046-158">каллеррефлексивеипаддр</span><span class="sxs-lookup"><span data-stu-id="4f046-158">CallerReflexiveIPAddr</span></span></p></td>
<td><p><span data-ttu-id="4f046-159">var (50)</span><span class="sxs-lookup"><span data-stu-id="4f046-159">var(50)</span></span></p></td>
<td><p><span data-ttu-id="4f046-160">IP-адрес вызывающего абонента, предоставленный службой EDGE (A/V).</span><span class="sxs-lookup"><span data-stu-id="4f046-160">Caller’s IP address as reported by the A/V Edge service.</span></span> <span data-ttu-id="4f046-161">Этот адрес может отличаться от Каллерипаддр, если клиент находится за пределами NAT, например.</span><span class="sxs-lookup"><span data-stu-id="4f046-161">This address may be different that the CallerIPAddr if the client is located behind a NAT for example.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f046-162">каллеркаптуредев</span><span class="sxs-lookup"><span data-stu-id="4f046-162">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="4f046-163">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="4f046-163">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4f046-164">Имя устройства захвата вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="4f046-164">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f046-165">каллеррендердев</span><span class="sxs-lookup"><span data-stu-id="4f046-165">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="4f046-166">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="4f046-166">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4f046-167">Имя устройства отрисовки вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="4f046-167">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f046-168">каллеркаптуредевдривер</span><span class="sxs-lookup"><span data-stu-id="4f046-168">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="4f046-169">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="4f046-169">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4f046-170">Имя драйвера устройства захвата вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="4f046-170">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f046-171">каллеррендердевдривер</span><span class="sxs-lookup"><span data-stu-id="4f046-171">CallerRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="4f046-172">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="4f046-172">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4f046-173">Имя драйвера устройства отрисовки вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="4f046-173">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f046-174">каллервифидривердевицедеск</span><span class="sxs-lookup"><span data-stu-id="4f046-174">CallerWifiDriverDeviceDesc</span></span></p></td>
<td><p><span data-ttu-id="4f046-175">varchar (256</span><span class="sxs-lookup"><span data-stu-id="4f046-175">varchar(256</span></span></p></td>
<td><p><span data-ttu-id="4f046-176">Описание драйвера Wi-Fi вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="4f046-176">Caller’s Wifi driver description.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f046-177">каллервифидриверверсион</span><span class="sxs-lookup"><span data-stu-id="4f046-177">CallerWifiDriverVersion</span></span></p></td>
<td><p><span data-ttu-id="4f046-178">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="4f046-178">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4f046-179">Версия драйвера Wi-Fi вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="4f046-179">Caller’s Wifi driver version.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f046-180">каллинетворкконнектиондетаил</span><span class="sxs-lookup"><span data-stu-id="4f046-180">CalleeNetworkConnectionDetail</span></span></p></td>
<td><p><span data-ttu-id="4f046-181">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="4f046-181">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4f046-182">Сведения о сетевом подключении вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="4f046-182">Details of caller’s network connection.</span></span> <span data-ttu-id="4f046-183">Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-networkconnectiondetail-table.md">таблицей нетворкконнектиондетаил в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="4f046-183">See the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f046-184">каллербссид</span><span class="sxs-lookup"><span data-stu-id="4f046-184">CallerBssid</span></span></p></td>
<td><p><span data-ttu-id="4f046-185">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="4f046-185">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4f046-186">Основной идентификатор набора служб, используемый вызывающими абонентами WiFi-связи.</span><span class="sxs-lookup"><span data-stu-id="4f046-186">Basic Service Set Identifier used by callers WiFi connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f046-187">каллервпн</span><span class="sxs-lookup"><span data-stu-id="4f046-187">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="4f046-188">бит</span><span class="sxs-lookup"><span data-stu-id="4f046-188">bit</span></span></p></td>
<td><p><span data-ttu-id="4f046-189">Указывает, подключен ли вызывающий абонент к виртуальной частной сети.</span><span class="sxs-lookup"><span data-stu-id="4f046-189">Indicates whether the caller connected over a virtual private network.</span></span> <span data-ttu-id="4f046-190">1 — это виртуальная частная сеть (VPN), а 0 — не VPN.</span><span class="sxs-lookup"><span data-stu-id="4f046-190">1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f046-191">каллиипаддр</span><span class="sxs-lookup"><span data-stu-id="4f046-191">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="4f046-192">var (50)</span><span class="sxs-lookup"><span data-stu-id="4f046-192">var(50)</span></span></p></td>
<td><p><span data-ttu-id="4f046-193">IP-адрес вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="4f046-193">IP address of the callee.</span></span> <span data-ttu-id="4f046-194">Это может быть либо адрес IPv4, либо IPv6.</span><span class="sxs-lookup"><span data-stu-id="4f046-194">This can be either an IPv4 or IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f046-195">каллипорт</span><span class="sxs-lookup"><span data-stu-id="4f046-195">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="4f046-196">целое</span><span class="sxs-lookup"><span data-stu-id="4f046-196">int</span></span></p></td>
<td><p><span data-ttu-id="4f046-197">Порт, используемый вызываемым абонентом.</span><span class="sxs-lookup"><span data-stu-id="4f046-197">Port used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f046-198">каллиинсиде</span><span class="sxs-lookup"><span data-stu-id="4f046-198">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="4f046-199">бит</span><span class="sxs-lookup"><span data-stu-id="4f046-199">bit</span></span></p></td>
<td><p><span data-ttu-id="4f046-200">Указывает, входит ли вызывающий объект в корпоративную сеть.</span><span class="sxs-lookup"><span data-stu-id="4f046-200">Indicates whether the callee is inside the enterprise network.</span></span> <span data-ttu-id="4f046-201">1 означает, что вызываемый абонент входит в корпоративную сеть, а 0 означает, что вызываемый объект находится за пределами сети.</span><span class="sxs-lookup"><span data-stu-id="4f046-201">1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f046-202">каллимакаддресс</span><span class="sxs-lookup"><span data-stu-id="4f046-202">CalleeMacAddress</span></span></p></td>
<td><p><span data-ttu-id="4f046-203">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="4f046-203">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4f046-204">MAC-адрес сетевого интерфейса, используемого вызываемым абонентом.</span><span class="sxs-lookup"><span data-stu-id="4f046-204">MAC address of network interface used by callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f046-205">каллирелайипаддр</span><span class="sxs-lookup"><span data-stu-id="4f046-205">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="4f046-206">var (50)</span><span class="sxs-lookup"><span data-stu-id="4f046-206">var(50)</span></span></p></td>
<td><p><span data-ttu-id="4f046-207">IP-адрес службы EDGE (/V), используемой вызываемым абонентом.</span><span class="sxs-lookup"><span data-stu-id="4f046-207">IP Address of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="4f046-208">Дополнительные сведения приведены в <a href="lync-server-2013-ipaddress-table.md">таблице IP-адрес в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="4f046-208">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f046-209">каллирелайпорт</span><span class="sxs-lookup"><span data-stu-id="4f046-209">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="4f046-210">целое</span><span class="sxs-lookup"><span data-stu-id="4f046-210">int</span></span></p></td>
<td><p><span data-ttu-id="4f046-211">Порт, используемый в службе EDGE (A/V), используемой вызываемым абонентом.</span><span class="sxs-lookup"><span data-stu-id="4f046-211">Port used on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f046-212">каллирефлексивеипаддр</span><span class="sxs-lookup"><span data-stu-id="4f046-212">CalleeReflexiveIPAddr</span></span></p></td>
<td><p><span data-ttu-id="4f046-213">var (50)</span><span class="sxs-lookup"><span data-stu-id="4f046-213">var(50)</span></span></p></td>
<td><p><span data-ttu-id="4f046-214">IP-адрес вызываемого абонента, предоставленный службой Edge/V.</span><span class="sxs-lookup"><span data-stu-id="4f046-214">Callee’s IP address as reported by the A/V Edge service.</span></span> <span data-ttu-id="4f046-215">Этот адрес может отличаться от Каллиипаддр, если клиент находится за пределами NAT, например.</span><span class="sxs-lookup"><span data-stu-id="4f046-215">This address may be different that the CalleeIPAddr if the client is located behind a NAT for example.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f046-216">калликаптуредев</span><span class="sxs-lookup"><span data-stu-id="4f046-216">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="4f046-217">var (50)</span><span class="sxs-lookup"><span data-stu-id="4f046-217">var(50)</span></span></p></td>
<td><p><span data-ttu-id="4f046-218">Имя устройства захвата абонента.</span><span class="sxs-lookup"><span data-stu-id="4f046-218">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f046-219">каллирендердев</span><span class="sxs-lookup"><span data-stu-id="4f046-219">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="4f046-220">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="4f046-220">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4f046-221">Имя устройства отрисовки вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="4f046-221">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f046-222">калликаптуредевдривер</span><span class="sxs-lookup"><span data-stu-id="4f046-222">CalleeCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="4f046-223">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="4f046-223">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4f046-224">Имя драйвера устройства захвата абонента.</span><span class="sxs-lookup"><span data-stu-id="4f046-224">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f046-225">каллирендердевдривер</span><span class="sxs-lookup"><span data-stu-id="4f046-225">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="4f046-226">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="4f046-226">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4f046-227">Имя драйвера устройства обработки вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="4f046-227">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f046-228">калливифидривердевицедеск</span><span class="sxs-lookup"><span data-stu-id="4f046-228">CalleeWifiDriverDeviceDesc</span></span></p></td>
<td><p><span data-ttu-id="4f046-229">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="4f046-229">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4f046-230">Описание драйвера WiFi вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="4f046-230">Callee’s Wifi driver description.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f046-231">калливифидриверверсион</span><span class="sxs-lookup"><span data-stu-id="4f046-231">CalleeWifiDriverVersion</span></span></p></td>
<td><p><span data-ttu-id="4f046-232">varchar (256</span><span class="sxs-lookup"><span data-stu-id="4f046-232">varchar(256</span></span></p></td>
<td><p><span data-ttu-id="4f046-233">Версия драйвера Wi-Fi для вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="4f046-233">Callee’s Wifi driver version.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f046-234">каллинетворкконнектиондетаил</span><span class="sxs-lookup"><span data-stu-id="4f046-234">CalleeNetworkConnectionDetail</span></span></p></td>
<td><p><span data-ttu-id="4f046-235">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="4f046-235">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4f046-236">Сведения о сетевом подключении для вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="4f046-236">Details of callee’s network connection.</span></span> <span data-ttu-id="4f046-237">Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-networkconnectiondetail-table.md">таблицей нетворкконнектиондетаил в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="4f046-237">See the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f046-238">каллибссид</span><span class="sxs-lookup"><span data-stu-id="4f046-238">CalleeBssid</span></span></p></td>
<td><p><span data-ttu-id="4f046-239">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="4f046-239">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4f046-240">Основной идентификатор набора служб, используемый для подключений WiFi.</span><span class="sxs-lookup"><span data-stu-id="4f046-240">Basic Service Set Identifier used by callee’s WiFi connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f046-241">калливпн</span><span class="sxs-lookup"><span data-stu-id="4f046-241">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="4f046-242">бит</span><span class="sxs-lookup"><span data-stu-id="4f046-242">bit</span></span></p></td>
<td><p><span data-ttu-id="4f046-243">Указывает, подсоединен ли вызывающий объект к виртуальной частной сети.</span><span class="sxs-lookup"><span data-stu-id="4f046-243">Indicates whether the callee connected over a virtual private network.</span></span> <span data-ttu-id="4f046-244">1 — это виртуальная частная сеть (VPN), а 0 — не VPN.</span><span class="sxs-lookup"><span data-stu-id="4f046-244">1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f046-245">конверсатионалмос</span><span class="sxs-lookup"><span data-stu-id="4f046-245">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="4f046-246">десятичное число (3, 2)</span><span class="sxs-lookup"><span data-stu-id="4f046-246">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="4f046-247">Нарровбанд MOS из сеансов голосовой связи (на основе обоих звуковых потоков).</span><span class="sxs-lookup"><span data-stu-id="4f046-247">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f046-248">апплиедбандвидслимит</span><span class="sxs-lookup"><span data-stu-id="4f046-248">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="4f046-249">целое</span><span class="sxs-lookup"><span data-stu-id="4f046-249">int</span></span></p></td>
<td><p><span data-ttu-id="4f046-250">Это фактическая пропускная способность, примененная к потоку отправки на стороне, для которой заданы различные параметры политики (TURN, API, SDP, сервер политики и т. д.).</span><span class="sxs-lookup"><span data-stu-id="4f046-250">This is the actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, etc.).</span></span> <span data-ttu-id="4f046-251">Это не следует путать с эффективной пропускной способностью, так как в зависимости от оценки пропускной способности может снизиться эффективная пропускная способность.</span><span class="sxs-lookup"><span data-stu-id="4f046-251">This should not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate.</span></span> <span data-ttu-id="4f046-252">Это является, по сути, максимальной пропускной способностью потока отправки, который может занимать ограничения пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="4f046-252">This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f046-253">AppliedBandwidthSource</span><span class="sxs-lookup"><span data-stu-id="4f046-253">AppliedBandwidthSource</span></span></p></td>
<td><p><span data-ttu-id="4f046-254">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="4f046-254">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4f046-255">Источник ограничения пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="4f046-255">Source of the bandwidth cap being imposed.</span></span> <span data-ttu-id="4f046-256">Она описывает, откуда поступают ограничения пропускной способности (например, "сервер политики", "превратить сервер" или "модальность").</span><span class="sxs-lookup"><span data-stu-id="4f046-256">It describes where the bandwidth limit is coming from (for example, “Policy Server”, “TURN Server”, or “Modality”).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f046-257">Вызывающая сторона</span><span class="sxs-lookup"><span data-stu-id="4f046-257">Caller</span></span></p></td>
<td><p><span data-ttu-id="4f046-258">бит</span><span class="sxs-lookup"><span data-stu-id="4f046-258">bit</span></span></p></td>
<td><p><span data-ttu-id="4f046-259">Указывает, получены ли метрики от вызывающего абонента; 1 — Да, 0 — нет.</span><span class="sxs-lookup"><span data-stu-id="4f046-259">Indicates whether metrics from the caller were received; 1 is yes, 0 is no.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f046-260">Вызываемая сторона</span><span class="sxs-lookup"><span data-stu-id="4f046-260">Callee</span></span></p></td>
<td><p><span data-ttu-id="4f046-261">бит</span><span class="sxs-lookup"><span data-stu-id="4f046-261">bit</span></span></p></td>
<td><p><span data-ttu-id="4f046-262">Указывает, получены ли метрики от приемника вызова; 1 — Да, 0 — нет.</span><span class="sxs-lookup"><span data-stu-id="4f046-262">Indicates whether metrics from the call receiver were received; 1 is yes, 0 is no.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f046-263">мидкаллрепорт</span><span class="sxs-lookup"><span data-stu-id="4f046-263">MidCallReport</span></span></p></td>
<td><p><span data-ttu-id="4f046-264">бит</span><span class="sxs-lookup"><span data-stu-id="4f046-264">bit</span></span></p></td>
<td><p><span data-ttu-id="4f046-265">Указывает, является ли отчет частью звонка или полным звонком.</span><span class="sxs-lookup"><span data-stu-id="4f046-265">Indicates whether the report is for a portion of the call or for the complete call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f046-266">классифиедпуркалл</span><span class="sxs-lookup"><span data-stu-id="4f046-266">ClassifiedPoorCall</span></span></p></td>
<td><p><span data-ttu-id="4f046-267">бит</span><span class="sxs-lookup"><span data-stu-id="4f046-267">bit</span></span></p></td>
<td><p><span data-ttu-id="4f046-268">Указывает, был ли звонок классифицирован как некачественный звонок (1) или как хороший звонок (0).</span><span class="sxs-lookup"><span data-stu-id="4f046-268">Indicates whether a call was classified as a poor call (1) or as a good call (0).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f046-269">каллерконнективитице</span><span class="sxs-lookup"><span data-stu-id="4f046-269">CallerConnectivityICE</span></span></p></td>
<td><p><span data-ttu-id="4f046-270">tinyint</span><span class="sxs-lookup"><span data-stu-id="4f046-270">tinyint</span></span></p></td>
<td><p><span data-ttu-id="4f046-271">Указывает, подключен ли вызывающий абонент к сети с помощью протокола ICE (установление подключения к Интернету).</span><span class="sxs-lookup"><span data-stu-id="4f046-271">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f046-272">калликоннективитице</span><span class="sxs-lookup"><span data-stu-id="4f046-272">CalleeConnectivityICE</span></span></p></td>
<td><p><span data-ttu-id="4f046-273">tinyint</span><span class="sxs-lookup"><span data-stu-id="4f046-273">tinyint</span></span></p></td>
<td><p><span data-ttu-id="4f046-274">Указывает, вызывает ли пользователь подключение к сети с помощью протокола ICE (установление подключения к Интернету).</span><span class="sxs-lookup"><span data-stu-id="4f046-274">Indicates whether the user called connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

