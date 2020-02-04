---
title: 'Lync Server 2013: таблица MediaLine'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: MediaLine table
ms:assetid: 414b1d63-ae97-4c27-bac0-c9ad0f808ff0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425920(v=OCS.15)
ms:contentKeyID: 48183956
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7488aa258fd30c2f9b519806dc84f9d897a08656
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758757"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="medialine-table-in-lync-server-2013"></a><span data-ttu-id="68c17-102">Таблица MediaLine в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68c17-102">MediaLine table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="68c17-103">_**Тема последнего изменения:** 2014-02-21_</span><span class="sxs-lookup"><span data-stu-id="68c17-103">_**Topic Last Modified:** 2014-02-21_</span></span>

<span data-ttu-id="68c17-104">Каждая запись представляет одну сеть мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="68c17-104">Each record represents one media line.</span></span> <span data-ttu-id="68c17-105">(Один звуковой сеанс обычно состоит из одной линии звукового файла.</span><span class="sxs-lookup"><span data-stu-id="68c17-105">(One audio session usually contains one audio media line.</span></span> <span data-ttu-id="68c17-106">Один из звуковых и видеофайлов (A/V) обычно содержит одну строку звукового файла и одну строку видеофайла, хотя в этом сеансе может быть две видеоустройства, если используется устройство конференц-связи или режим галереи.</span><span class="sxs-lookup"><span data-stu-id="68c17-106">One audio and video (A/V) session usually contains one audio media line and one video media line, although the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="68c17-107"><strong>Столбец</strong></span><span class="sxs-lookup"><span data-stu-id="68c17-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="68c17-108"><strong>Тип данных</strong></span><span class="sxs-lookup"><span data-stu-id="68c17-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="68c17-109"><strong>Ключ/индекс</strong></span><span class="sxs-lookup"><span data-stu-id="68c17-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="68c17-110"><strong>Сведения</strong></span><span class="sxs-lookup"><span data-stu-id="68c17-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="68c17-111"><strong>конференцедатетиме</strong></span><span class="sxs-lookup"><span data-stu-id="68c17-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="68c17-112">datetime</span><span class="sxs-lookup"><span data-stu-id="68c17-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="68c17-113">Primary</span><span class="sxs-lookup"><span data-stu-id="68c17-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="68c17-114">Ссылка из <a href="lync-server-2013-session-table.md">таблицы Sessions в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="68c17-114">Referenced from the <a href="lync-server-2013-session-table.md">Session table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68c17-115"><strong>сессионсек</strong></span><span class="sxs-lookup"><span data-stu-id="68c17-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="68c17-116">целое</span><span class="sxs-lookup"><span data-stu-id="68c17-116">int</span></span></p></td>
<td><p><span data-ttu-id="68c17-117">Primary</span><span class="sxs-lookup"><span data-stu-id="68c17-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="68c17-118">Ссылка из <a href="lync-server-2013-session-table.md">таблицы Sessions в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="68c17-118">Referenced from the <a href="lync-server-2013-session-table.md">Session table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68c17-119"><strong>медиалинелабел</strong></span><span class="sxs-lookup"><span data-stu-id="68c17-119"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="68c17-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="68c17-120">tinyint</span></span></p></td>
<td><p><span data-ttu-id="68c17-121">Primary</span><span class="sxs-lookup"><span data-stu-id="68c17-121">Primary</span></span></p></td>
<td><p><span data-ttu-id="68c17-122">0 — основной звук, 1 — основной видеофайл, а 2 — панорамный видеоролик, а 3 — общий доступ к приложениям и рабочему столу.</span><span class="sxs-lookup"><span data-stu-id="68c17-122">0 is main audio, 1 is main video, and 2 is panoramic video, 3 is Application/Desktop Sharing.</span></span> <span data-ttu-id="68c17-123">Эта метка должна быть уникальной в пределах одного сеанса.</span><span class="sxs-lookup"><span data-stu-id="68c17-123">This label must be unique within a single session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68c17-124"><strong>коннективитице</strong></span><span class="sxs-lookup"><span data-stu-id="68c17-124"><strong>ConnectivityIce</strong></span></span></p></td>
<td><p><span data-ttu-id="68c17-125">tinyint</span><span class="sxs-lookup"><span data-stu-id="68c17-125">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="68c17-126">Этот столбец присутствует в Microsoft Lync Server 2013, но не используется.</span><span class="sxs-lookup"><span data-stu-id="68c17-126">This column is present but not used in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="68c17-127">Сведения о подключении, используемом для линии мультимедиа, записываются в столбцах Каллерконнективитице и Калликоннективитице.</span><span class="sxs-lookup"><span data-stu-id="68c17-127">Information about the connectivity used for a media line is captured in the CallerConnectivityICE and CalleeConnectivityICE columns.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68c17-128"><strong>каллерицеварнингфлагс</strong></span><span class="sxs-lookup"><span data-stu-id="68c17-128"><strong>CallerIceWarningFlags</strong></span></span></p></td>
<td><p><span data-ttu-id="68c17-129">целое</span><span class="sxs-lookup"><span data-stu-id="68c17-129">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="68c17-130">Сведения о процессе установки интерактивной связи (ICE), описанные в разделе Флаги BITS.</span><span class="sxs-lookup"><span data-stu-id="68c17-130">Information about Interactive Connectivity Establishment (ICE) process described in bits flags.</span></span> <span data-ttu-id="68c17-131">Подробные сведения можно найти в <em>спецификации протоколов сервера контроля качества обслуживания</em>, которую можно загрузить.</span><span class="sxs-lookup"><span data-stu-id="68c17-131">For details, refer to the <em>Quality of Experience Monitoring Server Protocol Specification</em>, available for download.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68c17-132"><strong>каллиицеварнингфлагс</strong></span><span class="sxs-lookup"><span data-stu-id="68c17-132"><strong>CalleeIceWarningFlags</strong></span></span></p></td>
<td><p><span data-ttu-id="68c17-133">целое</span><span class="sxs-lookup"><span data-stu-id="68c17-133">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="68c17-134">То же, что и Каллерицеварнингфлагс, но на стороне вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="68c17-134">Same as CallerIceWarningFlags, but on the callee side.</span></span> <span data-ttu-id="68c17-135">Подробные сведения можно найти в <em>спецификации протоколов сервера контроля качества обслуживания</em>, которую можно загрузить.</span><span class="sxs-lookup"><span data-stu-id="68c17-135">For details, refer to the <em>Quality of Experience Monitoring Server Protocol Specification</em>, available for download.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68c17-136"><strong>Безопасность</strong></span><span class="sxs-lookup"><span data-stu-id="68c17-136"><strong>Security</strong></span></span></p></td>
<td><p><span data-ttu-id="68c17-137">tinyint</span><span class="sxs-lookup"><span data-stu-id="68c17-137">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="68c17-138">Используемый профиль безопасности.</span><span class="sxs-lookup"><span data-stu-id="68c17-138">The security profile in use.</span></span> <span data-ttu-id="68c17-139">0 — NONE, 1 — SRTP, 2 — v1.</span><span class="sxs-lookup"><span data-stu-id="68c17-139">0 is NONE, 1 is SRTP, 2 is V1.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68c17-140"><strong>Transport</strong></span><span class="sxs-lookup"><span data-stu-id="68c17-140"><strong>Transport</strong></span></span></p></td>
<td><p><span data-ttu-id="68c17-141">tinyint</span><span class="sxs-lookup"><span data-stu-id="68c17-141">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="68c17-142">0 — это UDP, а 1 — TCP.</span><span class="sxs-lookup"><span data-stu-id="68c17-142">0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68c17-143"><strong>каллерипаддр</strong></span><span class="sxs-lookup"><span data-stu-id="68c17-143"><strong>CallerIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="68c17-144">целое</span><span class="sxs-lookup"><span data-stu-id="68c17-144">int</span></span></p></td>
<td><p><span data-ttu-id="68c17-145">Другом</span><span class="sxs-lookup"><span data-stu-id="68c17-145">Foreign</span></span></p></td>
<td><p><span data-ttu-id="68c17-146">IP-адрес вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="68c17-146">IP Address of the caller.</span></span> <span data-ttu-id="68c17-147">Дополнительные сведения приведены в <a href="lync-server-2013-ipaddress-table.md">таблице IP-адрес в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="68c17-147">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68c17-148"><strong>каллерпорт</strong></span><span class="sxs-lookup"><span data-stu-id="68c17-148"><strong>CallerPort</strong></span></span></p></td>
<td><p><span data-ttu-id="68c17-149">целое</span><span class="sxs-lookup"><span data-stu-id="68c17-149">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="68c17-150">Порт, используемый вызывающим абонентом.</span><span class="sxs-lookup"><span data-stu-id="68c17-150">Port used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68c17-151"><strong>каллерсубнет</strong></span><span class="sxs-lookup"><span data-stu-id="68c17-151"><strong>CallerSubnet</strong></span></span></p></td>
<td><p><span data-ttu-id="68c17-152">целое</span><span class="sxs-lookup"><span data-stu-id="68c17-152">int</span></span></p></td>
<td><p><span data-ttu-id="68c17-153"> Другом</span><span class="sxs-lookup"><span data-stu-id="68c17-153"> Foreign</span></span></p></td>
<td><p><span data-ttu-id="68c17-154">Подсеть вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="68c17-154">The subnet of the caller.</span></span> <span data-ttu-id="68c17-155">Дополнительные сведения приведены в <a href="lync-server-2013-ipaddress-table.md">таблице IP-адрес в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="68c17-155">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68c17-156"><strong>каллеринсиде</strong></span><span class="sxs-lookup"><span data-stu-id="68c17-156"><strong>CallerInside</strong></span></span></p></td>
<td><p><span data-ttu-id="68c17-157">бит</span><span class="sxs-lookup"><span data-stu-id="68c17-157">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="68c17-158">1 означает, что вызывающий абонент входит в корпоративную сеть, а 0 означает, что вызывающий абонент находится за пределами сети.</span><span class="sxs-lookup"><span data-stu-id="68c17-158">1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68c17-159"><strong>каллермакаддресс</strong></span><span class="sxs-lookup"><span data-stu-id="68c17-159"><strong>CallerMacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="68c17-160">целое</span><span class="sxs-lookup"><span data-stu-id="68c17-160">int</span></span></p></td>
<td><p><span data-ttu-id="68c17-161">Другом</span><span class="sxs-lookup"><span data-stu-id="68c17-161">Foreign</span></span></p></td>
<td><p><span data-ttu-id="68c17-162">Mac-адрес вызывающего абонента, на который ссылается <a href="lync-server-2013-macaddress-table.md">Таблица MacAddress в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="68c17-162">Caller’s mac address, referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68c17-163"><strong>каллеррелайипаддр</strong></span><span class="sxs-lookup"><span data-stu-id="68c17-163"><strong>CallerRelayIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="68c17-164">целое</span><span class="sxs-lookup"><span data-stu-id="68c17-164">int</span></span></p></td>
<td><p><span data-ttu-id="68c17-165">Другом</span><span class="sxs-lookup"><span data-stu-id="68c17-165">Foreign</span></span></p></td>
<td><p><span data-ttu-id="68c17-166">IP-адрес службы Edge сервера Lync/V, используемой вызывающим абонентом.</span><span class="sxs-lookup"><span data-stu-id="68c17-166">IP Address of the Lync Server A/V Edge service used by the caller.</span></span> <span data-ttu-id="68c17-167">Дополнительные сведения приведены в <a href="lync-server-2013-ipaddress-table.md">таблице IP-адрес в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="68c17-167">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68c17-168"><strong>каллеррелайпорт</strong></span><span class="sxs-lookup"><span data-stu-id="68c17-168"><strong>CallerRelayPort</strong></span></span></p></td>
<td><p><span data-ttu-id="68c17-169">целое</span><span class="sxs-lookup"><span data-stu-id="68c17-169">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="68c17-170">Порт, используемый вызывающим абонентом для службы Edge A/V.</span><span class="sxs-lookup"><span data-stu-id="68c17-170">Port used on the A/V Edge service by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68c17-171"><strong>каллеркаптуредев</strong></span><span class="sxs-lookup"><span data-stu-id="68c17-171"><strong>CallerCaptureDev</strong></span></span></p></td>
<td><p><span data-ttu-id="68c17-172">целое</span><span class="sxs-lookup"><span data-stu-id="68c17-172">int</span></span></p></td>
<td><p><span data-ttu-id="68c17-173">Другом</span><span class="sxs-lookup"><span data-stu-id="68c17-173">Foreign</span></span></p></td>
<td><p><span data-ttu-id="68c17-174">Устройство захвата, используемое вызывающим абонентом.</span><span class="sxs-lookup"><span data-stu-id="68c17-174">Capture device used by the caller.</span></span> <span data-ttu-id="68c17-175">Ссылка из <a href="lync-server-2013-device-table.md">таблицы устройств в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="68c17-175">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68c17-176"><strong>каллеррендердев</strong></span><span class="sxs-lookup"><span data-stu-id="68c17-176"><strong>CallerRenderDev</strong></span></span></p></td>
<td><p><span data-ttu-id="68c17-177">целое</span><span class="sxs-lookup"><span data-stu-id="68c17-177">int</span></span></p></td>
<td><p><span data-ttu-id="68c17-178">Другом</span><span class="sxs-lookup"><span data-stu-id="68c17-178">Foreign</span></span></p></td>
<td><p><span data-ttu-id="68c17-179">Устройство обработки, используемое вызывающим абонентом.</span><span class="sxs-lookup"><span data-stu-id="68c17-179">Render device used by caller.</span></span> <span data-ttu-id="68c17-180">Ссылка из <a href="lync-server-2013-device-table.md">таблицы устройств в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="68c17-180">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68c17-181"><strong>каллеркаптуредевдривер</strong></span><span class="sxs-lookup"><span data-stu-id="68c17-181"><strong>CallerCaptureDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="68c17-182">целое</span><span class="sxs-lookup"><span data-stu-id="68c17-182">int</span></span></p></td>
<td><p><span data-ttu-id="68c17-183">Другом</span><span class="sxs-lookup"><span data-stu-id="68c17-183">Foreign</span></span></p></td>
<td><p><span data-ttu-id="68c17-184">Драйвер устройства захвата вызывающего абонента, на который ссылается <a href="lync-server-2013-devicedriver-table.md">Таблица девицедривер в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="68c17-184">Driver for the caller’s capture device, referenced from the <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68c17-185"><strong>каллеррендердевдривер</strong></span><span class="sxs-lookup"><span data-stu-id="68c17-185"><strong>CallerRenderDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="68c17-186">целое</span><span class="sxs-lookup"><span data-stu-id="68c17-186">int</span></span></p></td>
<td><p><span data-ttu-id="68c17-187">Другом</span><span class="sxs-lookup"><span data-stu-id="68c17-187">Foreign</span></span></p></td>
<td><p><span data-ttu-id="68c17-188">Драйвер для устройства отрисовки вызывающего абонента, на который ссылается <a href="lync-server-2013-devicedriver-table.md">Таблица девицедривер в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="68c17-188">Driver for the caller’s render device, referenced from the <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68c17-189"><strong>каллернетворкконнектионтипе</strong></span><span class="sxs-lookup"><span data-stu-id="68c17-189"><strong>CallerNetworkConnectionType</strong></span></span></p></td>
<td><p><span data-ttu-id="68c17-190">tinyint</span><span class="sxs-lookup"><span data-stu-id="68c17-190">tinyint</span></span></p></td>
<td><p><span data-ttu-id="68c17-191">Другом</span><span class="sxs-lookup"><span data-stu-id="68c17-191">Foreign</span></span></p></td>
<td><p><span data-ttu-id="68c17-192">Показывает, как вызывающий абонент подключился к сети.</span><span class="sxs-lookup"><span data-stu-id="68c17-192">Indicates how the caller connected to the network.</span></span> <span data-ttu-id="68c17-193">Значения извлекаются из <a href="lync-server-2013-networkconnectiondetail-table.md">таблицы нетворкконнектиондетаил в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="68c17-193">Values are obtained from the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a>.</span></span> <span data-ttu-id="68c17-194">Типичные значения: 0 для проводного подключения 1 для подключения WiFi; и 3 для подключения Ethernet.</span><span class="sxs-lookup"><span data-stu-id="68c17-194">Typical values are 0 for a wired connection’ 1 for a WiFi connection; and 3 for an Ethernet connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68c17-195"><strong>каллербссид</strong></span><span class="sxs-lookup"><span data-stu-id="68c17-195"><strong>CallerBssid</strong></span></span></p></td>
<td><p><span data-ttu-id="68c17-196">целое</span><span class="sxs-lookup"><span data-stu-id="68c17-196">int</span></span></p></td>
<td><p><span data-ttu-id="68c17-197">Другом</span><span class="sxs-lookup"><span data-stu-id="68c17-197">Foreign</span></span></p></td>
<td><p><span data-ttu-id="68c17-198">BSSID для вызывающего абонента, если используется беспроводная связь.</span><span class="sxs-lookup"><span data-stu-id="68c17-198">Caller’s BSSID if wireless is used.</span></span> <span data-ttu-id="68c17-199">Ссылка из <a href="lync-server-2013-macaddress-table.md">таблицы MacAddress в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="68c17-199">Referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68c17-200"><strong>каллервпн</strong></span><span class="sxs-lookup"><span data-stu-id="68c17-200"><strong>CallerVPN</strong></span></span></p></td>
<td><p><span data-ttu-id="68c17-201">бит</span><span class="sxs-lookup"><span data-stu-id="68c17-201">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68c17-202">Ссылка вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="68c17-202">The caller's link.</span></span> <span data-ttu-id="68c17-203">1 — это виртуальная частная сеть (VPN), а 0 — не VPN.</span><span class="sxs-lookup"><span data-stu-id="68c17-203">1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68c17-204"><strong>каллерлинкспид</strong></span><span class="sxs-lookup"><span data-stu-id="68c17-204"><strong>CallerLinkSpeed</strong></span></span></p></td>
<td><p><span data-ttu-id="68c17-205">десятичное число (18; 0)</span><span class="sxs-lookup"><span data-stu-id="68c17-205">decimal(18,0)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68c17-206">Скорость сетевого соединения (в бит/с) для конечной точки вызывающего объекта.</span><span class="sxs-lookup"><span data-stu-id="68c17-206">The network link speed, in bps, for the caller's endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68c17-207"><strong>каллиипаддр</strong></span><span class="sxs-lookup"><span data-stu-id="68c17-207"><strong>CalleeIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="68c17-208">целое</span><span class="sxs-lookup"><span data-stu-id="68c17-208">int</span></span></p></td>
<td><p><span data-ttu-id="68c17-209">Другом</span><span class="sxs-lookup"><span data-stu-id="68c17-209">Foreign</span></span></p></td>
<td><p><span data-ttu-id="68c17-210">IP-адрес получателя звонка.</span><span class="sxs-lookup"><span data-stu-id="68c17-210">IP Address of the call receiver.</span></span> <span data-ttu-id="68c17-211">Дополнительные сведения приведены в <a href="lync-server-2013-ipaddress-table.md">таблице IP-адрес в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="68c17-211">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68c17-212"><strong>каллипорт</strong></span><span class="sxs-lookup"><span data-stu-id="68c17-212"><strong>CalleePort</strong></span></span></p></td>
<td><p><span data-ttu-id="68c17-213">бит</span><span class="sxs-lookup"><span data-stu-id="68c17-213">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68c17-214">Порт, используемый получателем звонка.</span><span class="sxs-lookup"><span data-stu-id="68c17-214">Port used by the call receiver.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68c17-215"><strong>каллисубнет</strong></span><span class="sxs-lookup"><span data-stu-id="68c17-215"><strong>CalleeSubnet</strong></span></span></p></td>
<td><p><span data-ttu-id="68c17-216">целое</span><span class="sxs-lookup"><span data-stu-id="68c17-216">int</span></span></p></td>
<td><p><span data-ttu-id="68c17-217">Другом</span><span class="sxs-lookup"><span data-stu-id="68c17-217">Foreign</span></span></p></td>
<td><p><span data-ttu-id="68c17-218">Подсеть вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="68c17-218">Subnet of callee.</span></span> <span data-ttu-id="68c17-219">Дополнительные сведения приведены в <a href="lync-server-2013-ipaddress-table.md">таблице IP-адрес в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="68c17-219">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68c17-220"><strong>каллиинсиде</strong></span><span class="sxs-lookup"><span data-stu-id="68c17-220"><strong>CalleeInside</strong></span></span></p></td>
<td><p><span data-ttu-id="68c17-221">бит</span><span class="sxs-lookup"><span data-stu-id="68c17-221">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="68c17-222">1 — Получатель звонка входит в корпоративную сеть, а 0 означает, что получатель звонка находится за пределами сети.</span><span class="sxs-lookup"><span data-stu-id="68c17-222">1 means call receiver is inside the enterprise network, 0 means the call receiver is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68c17-223"><strong>каллимакаддресс</strong></span><span class="sxs-lookup"><span data-stu-id="68c17-223"><strong>CalleeMacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="68c17-224">целое</span><span class="sxs-lookup"><span data-stu-id="68c17-224">int</span></span></p></td>
<td><p><span data-ttu-id="68c17-225">Другом</span><span class="sxs-lookup"><span data-stu-id="68c17-225">Foreign</span></span></p></td>
<td><p><span data-ttu-id="68c17-226">Абонентский Mac-адрес.</span><span class="sxs-lookup"><span data-stu-id="68c17-226">Callee Mac address.</span></span> <span data-ttu-id="68c17-227">Ссылка на <a href="lync-server-2013-macaddress-table.md">таблицу MacAddress в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="68c17-227">Referenced from the <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68c17-228"><strong>каллирелайипаддр</strong></span><span class="sxs-lookup"><span data-stu-id="68c17-228"><strong>CalleeRelayIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="68c17-229">целое</span><span class="sxs-lookup"><span data-stu-id="68c17-229">int</span></span></p></td>
<td><p><span data-ttu-id="68c17-230">Другом</span><span class="sxs-lookup"><span data-stu-id="68c17-230">Foreign</span></span></p></td>
<td><p><span data-ttu-id="68c17-231">IP-адрес службы EDGE (/V), используемой приемником вызова.</span><span class="sxs-lookup"><span data-stu-id="68c17-231">IP Address of the A/V Edge service used by the call receiver.</span></span> <span data-ttu-id="68c17-232">Дополнительные сведения приведены в <a href="lync-server-2013-ipaddress-table.md">таблице IP-адрес в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="68c17-232">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68c17-233"><strong>каллирелайпорт</strong></span><span class="sxs-lookup"><span data-stu-id="68c17-233"><strong>CalleeRelayPort</strong></span></span></p></td>
<td><p><span data-ttu-id="68c17-234">целое</span><span class="sxs-lookup"><span data-stu-id="68c17-234">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="68c17-235">Порт, используемый приемником вызова для службы Edge/V.</span><span class="sxs-lookup"><span data-stu-id="68c17-235">Port used on the A/V Edge Service by the call receiver.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68c17-236"><strong>калликаптуредев</strong></span><span class="sxs-lookup"><span data-stu-id="68c17-236"><strong>CalleeCaptureDev</strong></span></span></p></td>
<td><p><span data-ttu-id="68c17-237">целое</span><span class="sxs-lookup"><span data-stu-id="68c17-237">int</span></span></p></td>
<td><p><span data-ttu-id="68c17-238">другом</span><span class="sxs-lookup"><span data-stu-id="68c17-238">foreign</span></span></p></td>
<td><p><span data-ttu-id="68c17-239">Устройство захвата, используемое получателем звонка.</span><span class="sxs-lookup"><span data-stu-id="68c17-239">Capture device used by the call receiver.</span></span> <span data-ttu-id="68c17-240">Ссылка из <a href="lync-server-2013-device-table.md">таблицы устройств в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="68c17-240">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68c17-241"><strong>каллирендердев</strong></span><span class="sxs-lookup"><span data-stu-id="68c17-241"><strong>CalleeRenderDev</strong></span></span></p></td>
<td><p><span data-ttu-id="68c17-242">целое</span><span class="sxs-lookup"><span data-stu-id="68c17-242">int</span></span></p></td>
<td><p><span data-ttu-id="68c17-243">Другом</span><span class="sxs-lookup"><span data-stu-id="68c17-243">Foreign</span></span></p></td>
<td><p><span data-ttu-id="68c17-244">Устройство обработки, используемое получателем звонка.</span><span class="sxs-lookup"><span data-stu-id="68c17-244">Render device used by the call receiver.</span></span> <span data-ttu-id="68c17-245">Ссылка из <a href="lync-server-2013-device-table.md">таблицы устройств в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="68c17-245">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68c17-246"><strong>калликаптуредевдривер</strong></span><span class="sxs-lookup"><span data-stu-id="68c17-246"><strong>CalleeCaptureDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="68c17-247">целое</span><span class="sxs-lookup"><span data-stu-id="68c17-247">int</span></span></p></td>
<td><p><span data-ttu-id="68c17-248">Другом</span><span class="sxs-lookup"><span data-stu-id="68c17-248">Foreign</span></span></p></td>
<td><p><span data-ttu-id="68c17-249">Драйвер устройства захвата приемника звонков.</span><span class="sxs-lookup"><span data-stu-id="68c17-249">Driver for the call receiver’s capture device.</span></span> <span data-ttu-id="68c17-250">Ссылка из <a href="lync-server-2013-devicedriver-table.md">таблицы девицедривер в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="68c17-250">Referenced from <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68c17-251"><strong>каллирендердевдривер</strong></span><span class="sxs-lookup"><span data-stu-id="68c17-251"><strong>CalleeRenderDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="68c17-252">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="68c17-252">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="68c17-253">Другом</span><span class="sxs-lookup"><span data-stu-id="68c17-253">Foreign</span></span></p></td>
<td><p><span data-ttu-id="68c17-254">Драйвер устройства отрисовки приемника звонков.</span><span class="sxs-lookup"><span data-stu-id="68c17-254">Driver for the call receiver’s render device.</span></span> <span data-ttu-id="68c17-255">Ссылка из <a href="lync-server-2013-devicedriver-table.md">таблицы девицедривер в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="68c17-255">Referenced from <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68c17-256"><strong>каллинетворкконнектионтипе</strong></span><span class="sxs-lookup"><span data-stu-id="68c17-256"><strong>CalleeNetworkConnectionType</strong></span></span></p></td>
<td><p><span data-ttu-id="68c17-257">tinyint</span><span class="sxs-lookup"><span data-stu-id="68c17-257">tinyint</span></span></p></td>
<td><p><span data-ttu-id="68c17-258">Другом</span><span class="sxs-lookup"><span data-stu-id="68c17-258">Foreign</span></span></p></td>
<td><p><span data-ttu-id="68c17-259">Показывает, как вызывающий абонент подключился к сети.</span><span class="sxs-lookup"><span data-stu-id="68c17-259">Indicates how the callee connected to the network.</span></span> <span data-ttu-id="68c17-260">Значения извлекаются из <a href="lync-server-2013-networkconnectiondetail-table.md">таблицы нетворкконнектиондетаил в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="68c17-260">Values are obtained from the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a>.</span></span> <span data-ttu-id="68c17-261">Типичные значения: 0 для проводного подключения 1 для подключения WiFi; и 3 для подключения Ethernet.</span><span class="sxs-lookup"><span data-stu-id="68c17-261">Typical values are 0 for a wired connection’ 1 for a WiFi connection; and 3 for an Ethernet connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68c17-262"><strong>каллибссид</strong></span><span class="sxs-lookup"><span data-stu-id="68c17-262"><strong>CalleeBssid</strong></span></span></p></td>
<td><p><span data-ttu-id="68c17-263">целое</span><span class="sxs-lookup"><span data-stu-id="68c17-263">int</span></span></p></td>
<td><p><span data-ttu-id="68c17-264">Другом</span><span class="sxs-lookup"><span data-stu-id="68c17-264">Foreign</span></span></p></td>
<td><p><span data-ttu-id="68c17-265">Если используется беспроводная связь, вызовите BSSID.</span><span class="sxs-lookup"><span data-stu-id="68c17-265">Callee’s BSSID if wireless is used.</span></span> <span data-ttu-id="68c17-266">Ссылка из <a href="lync-server-2013-macaddress-table.md">таблицы MacAddress в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="68c17-266">Referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68c17-267"><strong>калливпн</strong></span><span class="sxs-lookup"><span data-stu-id="68c17-267"><strong>CalleeVPN</strong></span></span></p></td>
<td><p><span data-ttu-id="68c17-268">бит</span><span class="sxs-lookup"><span data-stu-id="68c17-268">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="68c17-269">Ссылка на приемник звонка; 1 — это виртуальная частная сеть (VPN), а 0 — не VPN.</span><span class="sxs-lookup"><span data-stu-id="68c17-269">The call receiver’s link; 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68c17-270"><strong>каллилинкспид</strong></span><span class="sxs-lookup"><span data-stu-id="68c17-270"><strong>CalleeLinkSpeed</strong></span></span></p></td>
<td><p><span data-ttu-id="68c17-271">десятичное число (18; 0)</span><span class="sxs-lookup"><span data-stu-id="68c17-271">decimal(18,0)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="68c17-272">Скорость сетевого соединения (в бит/с) для конечной точки получателя звонка.</span><span class="sxs-lookup"><span data-stu-id="68c17-272">The network link speed, in bps, for the call receiver’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68c17-273"><strong>конверсатионалмос</strong></span><span class="sxs-lookup"><span data-stu-id="68c17-273"><strong>ConversationalMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="68c17-274">десятичное число (3, 2)</span><span class="sxs-lookup"><span data-stu-id="68c17-274">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="68c17-275">Нарровбанд MOS из сеансов голосовой связи (на основе обоих звуковых потоков).</span><span class="sxs-lookup"><span data-stu-id="68c17-275">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68c17-276"><strong>апплиедбандвидслимит</strong></span><span class="sxs-lookup"><span data-stu-id="68c17-276"><strong>AppliedBandwidthLimit</strong></span></span></p></td>
<td><p><span data-ttu-id="68c17-277">целое</span><span class="sxs-lookup"><span data-stu-id="68c17-277">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68c17-278">Это фактическая пропускная способность, примененная к данному потоку отправки на стороне, для которой заданы различные параметры политики (повернуть, API, SDP, сервер политики и т. д.).</span><span class="sxs-lookup"><span data-stu-id="68c17-278">This is the actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on).</span></span> <span data-ttu-id="68c17-279">Это не следует путать с эффективной пропускной способностью, так как в зависимости от оценки пропускной способности может снизиться эффективная пропускная способность.</span><span class="sxs-lookup"><span data-stu-id="68c17-279">This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate.</span></span> <span data-ttu-id="68c17-280">Это является, по сути, максимальной пропускной способностью потока отправки, который может занимать ограничения пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="68c17-280">This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68c17-281"><strong>апплиедбандвидссаурцекэй</strong></span><span class="sxs-lookup"><span data-stu-id="68c17-281"><strong>AppliedBandwidthSourceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="68c17-282">smallint</span><span class="sxs-lookup"><span data-stu-id="68c17-282">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68c17-283">Это источник установленного места для пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="68c17-283">This is the source of the bandwidth cap being imposed.</span></span> <span data-ttu-id="68c17-284">Она описывает, откуда поступают ограничения пропускной способности ("сервер политики", "превратить сервер", "модальность" и т. д.).</span><span class="sxs-lookup"><span data-stu-id="68c17-284">It describes where the bandwidth limit is coming from (“Policy Server”, “TURN Server”, “Modality”, and so on).</span></span> <span data-ttu-id="68c17-285">На которую ссылается <a href="lync-server-2013-appliedbandwidthsource-table.md">Таблица апплиедбандвидссаурце в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="68c17-285">Referenced from the <a href="lync-server-2013-appliedbandwidthsource-table.md">AppliedBandwidthSource table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68c17-286"><strong>Вызывающая сторона</strong></span><span class="sxs-lookup"><span data-stu-id="68c17-286"><strong>Caller</strong></span></span></p></td>
<td><p><span data-ttu-id="68c17-287">бит</span><span class="sxs-lookup"><span data-stu-id="68c17-287">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="68c17-288">Указывает, получены ли метрики от вызывающего абонента; 1 — это "Да", значение null — "нет".</span><span class="sxs-lookup"><span data-stu-id="68c17-288">Indicates whether metrics from the caller were received; 1 is yes, a null value is no.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68c17-289"><strong>Вызываемая сторона</strong></span><span class="sxs-lookup"><span data-stu-id="68c17-289"><strong>Callee</strong></span></span></p></td>
<td><p><span data-ttu-id="68c17-290">бит</span><span class="sxs-lookup"><span data-stu-id="68c17-290">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="68c17-291">Указывает, получены ли метрики от приемника вызова; 1 — это "Да", значение null — "нет".</span><span class="sxs-lookup"><span data-stu-id="68c17-291">Indicates whether metrics from the call receiver were received; 1 is yes, a null value is no.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68c17-292"><strong>мидкаллрепорт</strong></span><span class="sxs-lookup"><span data-stu-id="68c17-292"><strong>MidCallReport</strong></span></span></p></td>
<td><p><span data-ttu-id="68c17-293">бит</span><span class="sxs-lookup"><span data-stu-id="68c17-293">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68c17-294">Указывает, является ли отчет частью сеанса или для полного сеанса.</span><span class="sxs-lookup"><span data-stu-id="68c17-294">Indicates whether the report is for a portion of the session or for the complete session.</span></span></p>
<p><span data-ttu-id="68c17-295">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="68c17-295">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68c17-296"><strong>классифиедпуркалл</strong></span><span class="sxs-lookup"><span data-stu-id="68c17-296"><strong>ClassifiedPoorCall</strong></span></span></p></td>
<td><p><span data-ttu-id="68c17-297">бит</span><span class="sxs-lookup"><span data-stu-id="68c17-297">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68c17-298">Указывает, был ли звонок классифицирован как неудовлетворительный (значение 1) или как хороший звонок (0).</span><span class="sxs-lookup"><span data-stu-id="68c17-298">Indicates whether a call was classified as a poor call (value of 1) or as a good call (0).</span></span></p>
<p><span data-ttu-id="68c17-299">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="68c17-299">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68c17-300"><strong>каллерконнективитице</strong></span><span class="sxs-lookup"><span data-stu-id="68c17-300"><strong>CallerConnectivityICE</strong></span></span></p></td>
<td><p><span data-ttu-id="68c17-301">tinyInt</span><span class="sxs-lookup"><span data-stu-id="68c17-301">tinyInt</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68c17-302">Указывает, подключен ли вызывающий абонент к сети с помощью протокола ICE (установление подключения к Интернету).</span><span class="sxs-lookup"><span data-stu-id="68c17-302">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p>
<p><span data-ttu-id="68c17-303">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="68c17-303">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68c17-304"><strong>калликоннективитице</strong></span><span class="sxs-lookup"><span data-stu-id="68c17-304"><strong>CalleeConnectivityICE</strong></span></span></p></td>
<td><p><span data-ttu-id="68c17-305">tinyint</span><span class="sxs-lookup"><span data-stu-id="68c17-305">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68c17-306">Указывает, подключен ли вызывающий абонент к сети с помощью протокола ICE (установление подключения к Интернету).</span><span class="sxs-lookup"><span data-stu-id="68c17-306">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p>
<p><span data-ttu-id="68c17-307">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="68c17-307">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68c17-308"><strong>каллеррефлексивелокалипаддр</strong></span><span class="sxs-lookup"><span data-stu-id="68c17-308"><strong>CallerReflexiveLocalIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="68c17-309">целое</span><span class="sxs-lookup"><span data-stu-id="68c17-309">int</span></span></p></td>
<td><p><span data-ttu-id="68c17-310">Другом</span><span class="sxs-lookup"><span data-stu-id="68c17-310">Foreign</span></span></p></td>
<td><p><span data-ttu-id="68c17-311">IP-адрес пользователя, который поместил звонок.</span><span class="sxs-lookup"><span data-stu-id="68c17-311">Reflexive IP address of the user who placed the call.</span></span> <span data-ttu-id="68c17-312">В организациях, использующих NAT (преобразование сетевых адресов), можно использовать IP-адрес прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="68c17-312">In organizations that use NAT (network address translation), the reflexive IP address is the IP address of the proxy server.</span></span></p>
<p><span data-ttu-id="68c17-313">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="68c17-313">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68c17-314"><strong>каллервифидривердевицесдеск</strong></span><span class="sxs-lookup"><span data-stu-id="68c17-314"><strong>CallerWiFiDriverDevicesDesc</strong></span></span></p></td>
<td><p><span data-ttu-id="68c17-315">целое</span><span class="sxs-lookup"><span data-stu-id="68c17-315">int</span></span></p></td>
<td><p><span data-ttu-id="68c17-316">Другом</span><span class="sxs-lookup"><span data-stu-id="68c17-316">Foreign</span></span></p></td>
<td><p><span data-ttu-id="68c17-317">Описание устройства для драйвера Wi-Fi, задействованного пользовательским абонентом.</span><span class="sxs-lookup"><span data-stu-id="68c17-317">Device description for the WiFi driver employed by the user who placed the call.</span></span></p>
<p><span data-ttu-id="68c17-318">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="68c17-318">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68c17-319"><strong>каллервифидриверверсион</strong></span><span class="sxs-lookup"><span data-stu-id="68c17-319"><strong>CallerWiFiDriverVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="68c17-320">целое</span><span class="sxs-lookup"><span data-stu-id="68c17-320">int</span></span></p></td>
<td><p><span data-ttu-id="68c17-321">Другом</span><span class="sxs-lookup"><span data-stu-id="68c17-321">Foreign</span></span></p></td>
<td><p><span data-ttu-id="68c17-322">Номер версии для драйвера Wi-Fi, используемый пользователем, который присоединил звонок.</span><span class="sxs-lookup"><span data-stu-id="68c17-322">Version number for the WiFi driver employed by the user who placed the call.</span></span></p>
<p><span data-ttu-id="68c17-323">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="68c17-323">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68c17-324"><strong>каллерефлексивелокалипаддр</strong></span><span class="sxs-lookup"><span data-stu-id="68c17-324"><strong>CalleReflexiveLocalIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="68c17-325">целое</span><span class="sxs-lookup"><span data-stu-id="68c17-325">int</span></span></p></td>
<td><p><span data-ttu-id="68c17-326">Другом</span><span class="sxs-lookup"><span data-stu-id="68c17-326">Foreign</span></span></p></td>
<td><p><span data-ttu-id="68c17-327">IP-адрес пользователя, который получил звонок.</span><span class="sxs-lookup"><span data-stu-id="68c17-327">Reflexive IP address of the user who received the call.</span></span> <span data-ttu-id="68c17-328">В организациях, использующих NAT (преобразование сетевых адресов), можно использовать IP-адрес прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="68c17-328">In organizations that use NAT (network address translation), the reflexive IP address is the IP address of the proxy server.</span></span></p>
<p><span data-ttu-id="68c17-329">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="68c17-329">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68c17-330"><strong>калливифидривердевицесдеск</strong></span><span class="sxs-lookup"><span data-stu-id="68c17-330"><strong>CalleeWiFiDriverDevicesDesc</strong></span></span></p></td>
<td><p><span data-ttu-id="68c17-331">целое</span><span class="sxs-lookup"><span data-stu-id="68c17-331">int</span></span></p></td>
<td><p><span data-ttu-id="68c17-332">Другом</span><span class="sxs-lookup"><span data-stu-id="68c17-332">Foreign</span></span></p></td>
<td><p><span data-ttu-id="68c17-333">Описание устройства для драйвера Wi-Fi, применяемого пользователем, который получил звонок.</span><span class="sxs-lookup"><span data-stu-id="68c17-333">Device description for the WiFi driver employed by the user who received the call.</span></span></p>
<p><span data-ttu-id="68c17-334">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="68c17-334">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68c17-335"><strong>калливифидриверверсион</strong></span><span class="sxs-lookup"><span data-stu-id="68c17-335"><strong>CalleeWiFiDriverVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="68c17-336">целое</span><span class="sxs-lookup"><span data-stu-id="68c17-336">int</span></span></p></td>
<td><p><span data-ttu-id="68c17-337">Другом</span><span class="sxs-lookup"><span data-stu-id="68c17-337">Foreign</span></span></p></td>
<td><p><span data-ttu-id="68c17-338">Номер версии для драйвера Wi-Fi, используемый пользователем, который получил звонок.</span><span class="sxs-lookup"><span data-stu-id="68c17-338">Version number for the WiFi driver employed by the user who received the call.</span></span></p>
<p><span data-ttu-id="68c17-339">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="68c17-339">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

