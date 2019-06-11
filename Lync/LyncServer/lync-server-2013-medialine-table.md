---
title: 'Lync Server 2013: таблица MediaLine'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: MediaLine table
ms:assetid: 414b1d63-ae97-4c27-bac0-c9ad0f808ff0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425920(v=OCS.15)
ms:contentKeyID: 48183956
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4828f67614115eb4d6f46ab0a0a7c315e02d1924
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827440"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="medialine-table-in-lync-server-2013"></a><span data-ttu-id="277e3-102">Таблица MediaLine в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="277e3-102">MediaLine table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="277e3-103">_**Тема последнего изменения:** 2014-02-21_</span><span class="sxs-lookup"><span data-stu-id="277e3-103">_**Topic Last Modified:** 2014-02-21_</span></span>

<span data-ttu-id="277e3-104">Каждая запись представляет одну сеть мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="277e3-104">Each record represents one media line.</span></span> <span data-ttu-id="277e3-105">(Один звуковой сеанс обычно состоит из одной линии звукового файла.</span><span class="sxs-lookup"><span data-stu-id="277e3-105">(One audio session usually contains one audio media line.</span></span> <span data-ttu-id="277e3-106">Один из звуковых и видеофайлов (A/V) обычно содержит одну строку звукового файла и одну строку видеофайла, хотя в этом сеансе может быть две видеоустройства, если используется устройство конференц-связи или режим галереи.</span><span class="sxs-lookup"><span data-stu-id="277e3-106">One audio and video (A/V) session usually contains one audio media line and one video media line, although the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="277e3-107"><strong>Столбец</strong></span><span class="sxs-lookup"><span data-stu-id="277e3-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="277e3-108"><strong>Тип данных</strong></span><span class="sxs-lookup"><span data-stu-id="277e3-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="277e3-109"><strong>Ключ/индекс</strong></span><span class="sxs-lookup"><span data-stu-id="277e3-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="277e3-110"><strong>Сведения</strong></span><span class="sxs-lookup"><span data-stu-id="277e3-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="277e3-111"><strong>Конференцедатетиме</strong></span><span class="sxs-lookup"><span data-stu-id="277e3-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="277e3-112">datetime</span><span class="sxs-lookup"><span data-stu-id="277e3-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="277e3-113">Primary</span><span class="sxs-lookup"><span data-stu-id="277e3-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="277e3-114">Ссылка из <a href="lync-server-2013-session-table.md">таблицы Sessions в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="277e3-114">Referenced from the <a href="lync-server-2013-session-table.md">Session table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="277e3-115"><strong>Сессионсек</strong></span><span class="sxs-lookup"><span data-stu-id="277e3-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="277e3-116">целое</span><span class="sxs-lookup"><span data-stu-id="277e3-116">int</span></span></p></td>
<td><p><span data-ttu-id="277e3-117">Primary</span><span class="sxs-lookup"><span data-stu-id="277e3-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="277e3-118">Ссылка из <a href="lync-server-2013-session-table.md">таблицы Sessions в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="277e3-118">Referenced from the <a href="lync-server-2013-session-table.md">Session table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="277e3-119"><strong>Медиалинелабел</strong></span><span class="sxs-lookup"><span data-stu-id="277e3-119"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="277e3-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="277e3-120">tinyint</span></span></p></td>
<td><p><span data-ttu-id="277e3-121">Primary</span><span class="sxs-lookup"><span data-stu-id="277e3-121">Primary</span></span></p></td>
<td><p><span data-ttu-id="277e3-122">0 — основной звук, 1 — основной видеофайл, а 2 — панорамный видеоролик, а 3 — общий доступ к приложениям и рабочему столу.</span><span class="sxs-lookup"><span data-stu-id="277e3-122">0 is main audio, 1 is main video, and 2 is panoramic video, 3 is Application/Desktop Sharing.</span></span> <span data-ttu-id="277e3-123">Эта метка должна быть уникальной в пределах одного сеанса.</span><span class="sxs-lookup"><span data-stu-id="277e3-123">This label must be unique within a single session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="277e3-124"><strong>Коннективитице</strong></span><span class="sxs-lookup"><span data-stu-id="277e3-124"><strong>ConnectivityIce</strong></span></span></p></td>
<td><p><span data-ttu-id="277e3-125">tinyint</span><span class="sxs-lookup"><span data-stu-id="277e3-125">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="277e3-126">Этот столбец присутствует в Microsoft Lync Server 2013, но не используется.</span><span class="sxs-lookup"><span data-stu-id="277e3-126">This column is present but not used in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="277e3-127">Сведения о подключении, используемом для линии мультимедиа, записываются в столбцах Каллерконнективитице и Калликоннективитице.</span><span class="sxs-lookup"><span data-stu-id="277e3-127">Information about the connectivity used for a media line is captured in the CallerConnectivityICE and CalleeConnectivityICE columns.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="277e3-128"><strong>Каллерицеварнингфлагс</strong></span><span class="sxs-lookup"><span data-stu-id="277e3-128"><strong>CallerIceWarningFlags</strong></span></span></p></td>
<td><p><span data-ttu-id="277e3-129">целое</span><span class="sxs-lookup"><span data-stu-id="277e3-129">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="277e3-130">Сведения о процессе установки интерактивной связи (ICE), описанные в разделе Флаги BITS.</span><span class="sxs-lookup"><span data-stu-id="277e3-130">Information about Interactive Connectivity Establishment (ICE) process described in bits flags.</span></span> <span data-ttu-id="277e3-131">Подробные сведения можно найти в <em>спецификации протоколов сервера контроля качества обслуживания</em>, которую можно загрузить.</span><span class="sxs-lookup"><span data-stu-id="277e3-131">For details, refer to the <em>Quality of Experience Monitoring Server Protocol Specification</em>, available for download.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="277e3-132"><strong>Каллиицеварнингфлагс</strong></span><span class="sxs-lookup"><span data-stu-id="277e3-132"><strong>CalleeIceWarningFlags</strong></span></span></p></td>
<td><p><span data-ttu-id="277e3-133">целое</span><span class="sxs-lookup"><span data-stu-id="277e3-133">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="277e3-134">То же, что и Каллерицеварнингфлагс, но на стороне вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="277e3-134">Same as CallerIceWarningFlags, but on the callee side.</span></span> <span data-ttu-id="277e3-135">Подробные сведения можно найти в <em>спецификации протоколов сервера контроля качества обслуживания</em>, которую можно загрузить.</span><span class="sxs-lookup"><span data-stu-id="277e3-135">For details, refer to the <em>Quality of Experience Monitoring Server Protocol Specification</em>, available for download.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="277e3-136"><strong>Безопасность</strong></span><span class="sxs-lookup"><span data-stu-id="277e3-136"><strong>Security</strong></span></span></p></td>
<td><p><span data-ttu-id="277e3-137">tinyint</span><span class="sxs-lookup"><span data-stu-id="277e3-137">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="277e3-138">Используемый профиль безопасности.</span><span class="sxs-lookup"><span data-stu-id="277e3-138">The security profile in use.</span></span> <span data-ttu-id="277e3-139">0 — NONE, 1 — SRTP, 2 — v1.</span><span class="sxs-lookup"><span data-stu-id="277e3-139">0 is NONE, 1 is SRTP, 2 is V1.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="277e3-140"><strong>Transport</strong></span><span class="sxs-lookup"><span data-stu-id="277e3-140"><strong>Transport</strong></span></span></p></td>
<td><p><span data-ttu-id="277e3-141">tinyint</span><span class="sxs-lookup"><span data-stu-id="277e3-141">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="277e3-142">0 — это UDP, а 1 — TCP.</span><span class="sxs-lookup"><span data-stu-id="277e3-142">0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="277e3-143"><strong>Каллерипаддр</strong></span><span class="sxs-lookup"><span data-stu-id="277e3-143"><strong>CallerIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="277e3-144">целое</span><span class="sxs-lookup"><span data-stu-id="277e3-144">int</span></span></p></td>
<td><p><span data-ttu-id="277e3-145">Другом</span><span class="sxs-lookup"><span data-stu-id="277e3-145">Foreign</span></span></p></td>
<td><p><span data-ttu-id="277e3-146">IP-адрес вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="277e3-146">IP Address of the caller.</span></span> <span data-ttu-id="277e3-147">Дополнительные сведения приведены в <a href="lync-server-2013-ipaddress-table.md">таблице IP-адрес в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="277e3-147">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="277e3-148"><strong>Каллерпорт</strong></span><span class="sxs-lookup"><span data-stu-id="277e3-148"><strong>CallerPort</strong></span></span></p></td>
<td><p><span data-ttu-id="277e3-149">целое</span><span class="sxs-lookup"><span data-stu-id="277e3-149">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="277e3-150">Порт, используемый вызывающим абонентом.</span><span class="sxs-lookup"><span data-stu-id="277e3-150">Port used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="277e3-151"><strong>Каллерсубнет</strong></span><span class="sxs-lookup"><span data-stu-id="277e3-151"><strong>CallerSubnet</strong></span></span></p></td>
<td><p><span data-ttu-id="277e3-152">целое</span><span class="sxs-lookup"><span data-stu-id="277e3-152">int</span></span></p></td>
<td><p><span data-ttu-id="277e3-153"> Другом</span><span class="sxs-lookup"><span data-stu-id="277e3-153"> Foreign</span></span></p></td>
<td><p><span data-ttu-id="277e3-154">Подсеть вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="277e3-154">The subnet of the caller.</span></span> <span data-ttu-id="277e3-155">Дополнительные сведения приведены в <a href="lync-server-2013-ipaddress-table.md">таблице IP-адрес в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="277e3-155">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="277e3-156"><strong>Каллеринсиде</strong></span><span class="sxs-lookup"><span data-stu-id="277e3-156"><strong>CallerInside</strong></span></span></p></td>
<td><p><span data-ttu-id="277e3-157">бит</span><span class="sxs-lookup"><span data-stu-id="277e3-157">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="277e3-158">1 означает, что вызывающий абонент входит в корпоративную сеть, а 0 означает, что вызывающий абонент находится за пределами сети.</span><span class="sxs-lookup"><span data-stu-id="277e3-158">1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="277e3-159"><strong>Каллермакаддресс</strong></span><span class="sxs-lookup"><span data-stu-id="277e3-159"><strong>CallerMacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="277e3-160">целое</span><span class="sxs-lookup"><span data-stu-id="277e3-160">int</span></span></p></td>
<td><p><span data-ttu-id="277e3-161">Другом</span><span class="sxs-lookup"><span data-stu-id="277e3-161">Foreign</span></span></p></td>
<td><p><span data-ttu-id="277e3-162">Mac-адрес вызывающего абонента, на который ссылается <a href="lync-server-2013-macaddress-table.md">Таблица MacAddress в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="277e3-162">Caller’s mac address, referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="277e3-163"><strong>Каллеррелайипаддр</strong></span><span class="sxs-lookup"><span data-stu-id="277e3-163"><strong>CallerRelayIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="277e3-164">целое</span><span class="sxs-lookup"><span data-stu-id="277e3-164">int</span></span></p></td>
<td><p><span data-ttu-id="277e3-165">Другом</span><span class="sxs-lookup"><span data-stu-id="277e3-165">Foreign</span></span></p></td>
<td><p><span data-ttu-id="277e3-166">IP-адрес службы Edge сервера Lync/V, используемой вызывающим абонентом.</span><span class="sxs-lookup"><span data-stu-id="277e3-166">IP Address of the Lync Server A/V Edge service used by the caller.</span></span> <span data-ttu-id="277e3-167">Дополнительные сведения приведены в <a href="lync-server-2013-ipaddress-table.md">таблице IP-адрес в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="277e3-167">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="277e3-168"><strong>Каллеррелайпорт</strong></span><span class="sxs-lookup"><span data-stu-id="277e3-168"><strong>CallerRelayPort</strong></span></span></p></td>
<td><p><span data-ttu-id="277e3-169">целое</span><span class="sxs-lookup"><span data-stu-id="277e3-169">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="277e3-170">Порт, используемый вызывающим абонентом для службы Edge A/V.</span><span class="sxs-lookup"><span data-stu-id="277e3-170">Port used on the A/V Edge service by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="277e3-171"><strong>Каллеркаптуредев</strong></span><span class="sxs-lookup"><span data-stu-id="277e3-171"><strong>CallerCaptureDev</strong></span></span></p></td>
<td><p><span data-ttu-id="277e3-172">целое</span><span class="sxs-lookup"><span data-stu-id="277e3-172">int</span></span></p></td>
<td><p><span data-ttu-id="277e3-173">Другом</span><span class="sxs-lookup"><span data-stu-id="277e3-173">Foreign</span></span></p></td>
<td><p><span data-ttu-id="277e3-174">Устройство захвата, используемое вызывающим абонентом.</span><span class="sxs-lookup"><span data-stu-id="277e3-174">Capture device used by the caller.</span></span> <span data-ttu-id="277e3-175">Ссылка из <a href="lync-server-2013-device-table.md">таблицы устройств в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="277e3-175">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="277e3-176"><strong>Каллеррендердев</strong></span><span class="sxs-lookup"><span data-stu-id="277e3-176"><strong>CallerRenderDev</strong></span></span></p></td>
<td><p><span data-ttu-id="277e3-177">целое</span><span class="sxs-lookup"><span data-stu-id="277e3-177">int</span></span></p></td>
<td><p><span data-ttu-id="277e3-178">Другом</span><span class="sxs-lookup"><span data-stu-id="277e3-178">Foreign</span></span></p></td>
<td><p><span data-ttu-id="277e3-179">Устройство обработки, используемое вызывающим абонентом.</span><span class="sxs-lookup"><span data-stu-id="277e3-179">Render device used by caller.</span></span> <span data-ttu-id="277e3-180">Ссылка из <a href="lync-server-2013-device-table.md">таблицы устройств в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="277e3-180">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="277e3-181"><strong>Каллеркаптуредевдривер</strong></span><span class="sxs-lookup"><span data-stu-id="277e3-181"><strong>CallerCaptureDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="277e3-182">целое</span><span class="sxs-lookup"><span data-stu-id="277e3-182">int</span></span></p></td>
<td><p><span data-ttu-id="277e3-183">Другом</span><span class="sxs-lookup"><span data-stu-id="277e3-183">Foreign</span></span></p></td>
<td><p><span data-ttu-id="277e3-184">Драйвер устройства захвата вызывающего абонента, на который ссылается <a href="lync-server-2013-devicedriver-table.md">Таблица девицедривер в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="277e3-184">Driver for the caller’s capture device, referenced from the <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="277e3-185"><strong>Каллеррендердевдривер</strong></span><span class="sxs-lookup"><span data-stu-id="277e3-185"><strong>CallerRenderDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="277e3-186">целое</span><span class="sxs-lookup"><span data-stu-id="277e3-186">int</span></span></p></td>
<td><p><span data-ttu-id="277e3-187">Другом</span><span class="sxs-lookup"><span data-stu-id="277e3-187">Foreign</span></span></p></td>
<td><p><span data-ttu-id="277e3-188">Драйвер для устройства отрисовки вызывающего абонента, на который ссылается <a href="lync-server-2013-devicedriver-table.md">Таблица девицедривер в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="277e3-188">Driver for the caller’s render device, referenced from the <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="277e3-189"><strong>Каллернетворкконнектионтипе</strong></span><span class="sxs-lookup"><span data-stu-id="277e3-189"><strong>CallerNetworkConnectionType</strong></span></span></p></td>
<td><p><span data-ttu-id="277e3-190">tinyint</span><span class="sxs-lookup"><span data-stu-id="277e3-190">tinyint</span></span></p></td>
<td><p><span data-ttu-id="277e3-191">Другом</span><span class="sxs-lookup"><span data-stu-id="277e3-191">Foreign</span></span></p></td>
<td><p><span data-ttu-id="277e3-192">Показывает, как вызывающий абонент подключился к сети.</span><span class="sxs-lookup"><span data-stu-id="277e3-192">Indicates how the caller connected to the network.</span></span> <span data-ttu-id="277e3-193">Значения извлекаются из <a href="lync-server-2013-networkconnectiondetail-table.md">таблицы нетворкконнектиондетаил в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="277e3-193">Values are obtained from the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a>.</span></span> <span data-ttu-id="277e3-194">Типичные значения: 0 для проводного подключения 1 для подключения WiFi; и 3 для подключения Ethernet.</span><span class="sxs-lookup"><span data-stu-id="277e3-194">Typical values are 0 for a wired connection’ 1 for a WiFi connection; and 3 for an Ethernet connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="277e3-195"><strong>Каллербссид</strong></span><span class="sxs-lookup"><span data-stu-id="277e3-195"><strong>CallerBssid</strong></span></span></p></td>
<td><p><span data-ttu-id="277e3-196">целое</span><span class="sxs-lookup"><span data-stu-id="277e3-196">int</span></span></p></td>
<td><p><span data-ttu-id="277e3-197">Другом</span><span class="sxs-lookup"><span data-stu-id="277e3-197">Foreign</span></span></p></td>
<td><p><span data-ttu-id="277e3-198">BSSID для вызывающего абонента, если используется беспроводная связь.</span><span class="sxs-lookup"><span data-stu-id="277e3-198">Caller’s BSSID if wireless is used.</span></span> <span data-ttu-id="277e3-199">Ссылка из <a href="lync-server-2013-macaddress-table.md">таблицы MacAddress в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="277e3-199">Referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="277e3-200"><strong>Каллервпн</strong></span><span class="sxs-lookup"><span data-stu-id="277e3-200"><strong>CallerVPN</strong></span></span></p></td>
<td><p><span data-ttu-id="277e3-201">бит</span><span class="sxs-lookup"><span data-stu-id="277e3-201">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="277e3-202">Ссылка вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="277e3-202">The caller's link.</span></span> <span data-ttu-id="277e3-203">1 — это виртуальная частная сеть (VPN), а 0 — не VPN.</span><span class="sxs-lookup"><span data-stu-id="277e3-203">1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="277e3-204"><strong>Каллерлинкспид</strong></span><span class="sxs-lookup"><span data-stu-id="277e3-204"><strong>CallerLinkSpeed</strong></span></span></p></td>
<td><p><span data-ttu-id="277e3-205">десятичное число (18; 0)</span><span class="sxs-lookup"><span data-stu-id="277e3-205">decimal(18,0)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="277e3-206">Скорость сетевого соединения (в бит/с) для конечной точки вызывающего объекта.</span><span class="sxs-lookup"><span data-stu-id="277e3-206">The network link speed, in bps, for the caller's endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="277e3-207"><strong>Каллиипаддр</strong></span><span class="sxs-lookup"><span data-stu-id="277e3-207"><strong>CalleeIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="277e3-208">целое</span><span class="sxs-lookup"><span data-stu-id="277e3-208">int</span></span></p></td>
<td><p><span data-ttu-id="277e3-209">Другом</span><span class="sxs-lookup"><span data-stu-id="277e3-209">Foreign</span></span></p></td>
<td><p><span data-ttu-id="277e3-210">IP-адрес получателя звонка.</span><span class="sxs-lookup"><span data-stu-id="277e3-210">IP Address of the call receiver.</span></span> <span data-ttu-id="277e3-211">Дополнительные сведения приведены в <a href="lync-server-2013-ipaddress-table.md">таблице IP-адрес в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="277e3-211">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="277e3-212"><strong>Каллипорт</strong></span><span class="sxs-lookup"><span data-stu-id="277e3-212"><strong>CalleePort</strong></span></span></p></td>
<td><p><span data-ttu-id="277e3-213">бит</span><span class="sxs-lookup"><span data-stu-id="277e3-213">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="277e3-214">Порт, используемый получателем звонка.</span><span class="sxs-lookup"><span data-stu-id="277e3-214">Port used by the call receiver.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="277e3-215"><strong>Каллисубнет</strong></span><span class="sxs-lookup"><span data-stu-id="277e3-215"><strong>CalleeSubnet</strong></span></span></p></td>
<td><p><span data-ttu-id="277e3-216">целое</span><span class="sxs-lookup"><span data-stu-id="277e3-216">int</span></span></p></td>
<td><p><span data-ttu-id="277e3-217">Другом</span><span class="sxs-lookup"><span data-stu-id="277e3-217">Foreign</span></span></p></td>
<td><p><span data-ttu-id="277e3-218">Подсеть вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="277e3-218">Subnet of callee.</span></span> <span data-ttu-id="277e3-219">Дополнительные сведения приведены в <a href="lync-server-2013-ipaddress-table.md">таблице IP-адрес в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="277e3-219">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="277e3-220"><strong>Каллиинсиде</strong></span><span class="sxs-lookup"><span data-stu-id="277e3-220"><strong>CalleeInside</strong></span></span></p></td>
<td><p><span data-ttu-id="277e3-221">бит</span><span class="sxs-lookup"><span data-stu-id="277e3-221">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="277e3-222">1 — Получатель звонка входит в корпоративную сеть, а 0 означает, что получатель звонка находится за пределами сети.</span><span class="sxs-lookup"><span data-stu-id="277e3-222">1 means call receiver is inside the enterprise network, 0 means the call receiver is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="277e3-223"><strong>Каллимакаддресс</strong></span><span class="sxs-lookup"><span data-stu-id="277e3-223"><strong>CalleeMacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="277e3-224">целое</span><span class="sxs-lookup"><span data-stu-id="277e3-224">int</span></span></p></td>
<td><p><span data-ttu-id="277e3-225">Другом</span><span class="sxs-lookup"><span data-stu-id="277e3-225">Foreign</span></span></p></td>
<td><p><span data-ttu-id="277e3-226">Абонентский Mac-адрес.</span><span class="sxs-lookup"><span data-stu-id="277e3-226">Callee Mac address.</span></span> <span data-ttu-id="277e3-227">Ссылка на <a href="lync-server-2013-macaddress-table.md">таблицу MacAddress в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="277e3-227">Referenced from the <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="277e3-228"><strong>Каллирелайипаддр</strong></span><span class="sxs-lookup"><span data-stu-id="277e3-228"><strong>CalleeRelayIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="277e3-229">целое</span><span class="sxs-lookup"><span data-stu-id="277e3-229">int</span></span></p></td>
<td><p><span data-ttu-id="277e3-230">Другом</span><span class="sxs-lookup"><span data-stu-id="277e3-230">Foreign</span></span></p></td>
<td><p><span data-ttu-id="277e3-231">IP-адрес службы EDGE (/V), используемой приемником вызова.</span><span class="sxs-lookup"><span data-stu-id="277e3-231">IP Address of the A/V Edge service used by the call receiver.</span></span> <span data-ttu-id="277e3-232">Дополнительные сведения приведены в <a href="lync-server-2013-ipaddress-table.md">таблице IP-адрес в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="277e3-232">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="277e3-233"><strong>Каллирелайпорт</strong></span><span class="sxs-lookup"><span data-stu-id="277e3-233"><strong>CalleeRelayPort</strong></span></span></p></td>
<td><p><span data-ttu-id="277e3-234">целое</span><span class="sxs-lookup"><span data-stu-id="277e3-234">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="277e3-235">Порт, используемый приемником вызова для службы Edge/V.</span><span class="sxs-lookup"><span data-stu-id="277e3-235">Port used on the A/V Edge Service by the call receiver.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="277e3-236"><strong>Калликаптуредев</strong></span><span class="sxs-lookup"><span data-stu-id="277e3-236"><strong>CalleeCaptureDev</strong></span></span></p></td>
<td><p><span data-ttu-id="277e3-237">целое</span><span class="sxs-lookup"><span data-stu-id="277e3-237">int</span></span></p></td>
<td><p><span data-ttu-id="277e3-238">другом</span><span class="sxs-lookup"><span data-stu-id="277e3-238">foreign</span></span></p></td>
<td><p><span data-ttu-id="277e3-239">Устройство захвата, используемое получателем звонка.</span><span class="sxs-lookup"><span data-stu-id="277e3-239">Capture device used by the call receiver.</span></span> <span data-ttu-id="277e3-240">Ссылка из <a href="lync-server-2013-device-table.md">таблицы устройств в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="277e3-240">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="277e3-241"><strong>Каллирендердев</strong></span><span class="sxs-lookup"><span data-stu-id="277e3-241"><strong>CalleeRenderDev</strong></span></span></p></td>
<td><p><span data-ttu-id="277e3-242">целое</span><span class="sxs-lookup"><span data-stu-id="277e3-242">int</span></span></p></td>
<td><p><span data-ttu-id="277e3-243">Другом</span><span class="sxs-lookup"><span data-stu-id="277e3-243">Foreign</span></span></p></td>
<td><p><span data-ttu-id="277e3-244">Устройство обработки, используемое получателем звонка.</span><span class="sxs-lookup"><span data-stu-id="277e3-244">Render device used by the call receiver.</span></span> <span data-ttu-id="277e3-245">Ссылка из <a href="lync-server-2013-device-table.md">таблицы устройств в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="277e3-245">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="277e3-246"><strong>Калликаптуредевдривер</strong></span><span class="sxs-lookup"><span data-stu-id="277e3-246"><strong>CalleeCaptureDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="277e3-247">целое</span><span class="sxs-lookup"><span data-stu-id="277e3-247">int</span></span></p></td>
<td><p><span data-ttu-id="277e3-248">Другом</span><span class="sxs-lookup"><span data-stu-id="277e3-248">Foreign</span></span></p></td>
<td><p><span data-ttu-id="277e3-249">Драйвер устройства захвата приемника звонков.</span><span class="sxs-lookup"><span data-stu-id="277e3-249">Driver for the call receiver’s capture device.</span></span> <span data-ttu-id="277e3-250">Ссылка из <a href="lync-server-2013-devicedriver-table.md">таблицы девицедривер в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="277e3-250">Referenced from <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="277e3-251"><strong>Каллирендердевдривер</strong></span><span class="sxs-lookup"><span data-stu-id="277e3-251"><strong>CalleeRenderDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="277e3-252">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="277e3-252">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="277e3-253">Другом</span><span class="sxs-lookup"><span data-stu-id="277e3-253">Foreign</span></span></p></td>
<td><p><span data-ttu-id="277e3-254">Драйвер устройства отрисовки приемника звонков.</span><span class="sxs-lookup"><span data-stu-id="277e3-254">Driver for the call receiver’s render device.</span></span> <span data-ttu-id="277e3-255">Ссылка из <a href="lync-server-2013-devicedriver-table.md">таблицы девицедривер в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="277e3-255">Referenced from <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="277e3-256"><strong>Каллинетворкконнектионтипе</strong></span><span class="sxs-lookup"><span data-stu-id="277e3-256"><strong>CalleeNetworkConnectionType</strong></span></span></p></td>
<td><p><span data-ttu-id="277e3-257">tinyint</span><span class="sxs-lookup"><span data-stu-id="277e3-257">tinyint</span></span></p></td>
<td><p><span data-ttu-id="277e3-258">Другом</span><span class="sxs-lookup"><span data-stu-id="277e3-258">Foreign</span></span></p></td>
<td><p><span data-ttu-id="277e3-259">Показывает, как вызывающий абонент подключился к сети.</span><span class="sxs-lookup"><span data-stu-id="277e3-259">Indicates how the callee connected to the network.</span></span> <span data-ttu-id="277e3-260">Значения извлекаются из <a href="lync-server-2013-networkconnectiondetail-table.md">таблицы нетворкконнектиондетаил в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="277e3-260">Values are obtained from the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a>.</span></span> <span data-ttu-id="277e3-261">Типичные значения: 0 для проводного подключения 1 для подключения WiFi; и 3 для подключения Ethernet.</span><span class="sxs-lookup"><span data-stu-id="277e3-261">Typical values are 0 for a wired connection’ 1 for a WiFi connection; and 3 for an Ethernet connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="277e3-262"><strong>Каллибссид</strong></span><span class="sxs-lookup"><span data-stu-id="277e3-262"><strong>CalleeBssid</strong></span></span></p></td>
<td><p><span data-ttu-id="277e3-263">целое</span><span class="sxs-lookup"><span data-stu-id="277e3-263">int</span></span></p></td>
<td><p><span data-ttu-id="277e3-264">Другом</span><span class="sxs-lookup"><span data-stu-id="277e3-264">Foreign</span></span></p></td>
<td><p><span data-ttu-id="277e3-265">Если используется беспроводная связь, вызовите BSSID.</span><span class="sxs-lookup"><span data-stu-id="277e3-265">Callee’s BSSID if wireless is used.</span></span> <span data-ttu-id="277e3-266">Ссылка из <a href="lync-server-2013-macaddress-table.md">таблицы MacAddress в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="277e3-266">Referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="277e3-267"><strong>Калливпн</strong></span><span class="sxs-lookup"><span data-stu-id="277e3-267"><strong>CalleeVPN</strong></span></span></p></td>
<td><p><span data-ttu-id="277e3-268">бит</span><span class="sxs-lookup"><span data-stu-id="277e3-268">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="277e3-269">Ссылка на приемник звонка; 1 — это виртуальная частная сеть (VPN), а 0 — не VPN.</span><span class="sxs-lookup"><span data-stu-id="277e3-269">The call receiver’s link; 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="277e3-270"><strong>Каллилинкспид</strong></span><span class="sxs-lookup"><span data-stu-id="277e3-270"><strong>CalleeLinkSpeed</strong></span></span></p></td>
<td><p><span data-ttu-id="277e3-271">десятичное число (18; 0)</span><span class="sxs-lookup"><span data-stu-id="277e3-271">decimal(18,0)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="277e3-272">Скорость сетевого соединения (в бит/с) для конечной точки получателя звонка.</span><span class="sxs-lookup"><span data-stu-id="277e3-272">The network link speed, in bps, for the call receiver’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="277e3-273"><strong>Конверсатионалмос</strong></span><span class="sxs-lookup"><span data-stu-id="277e3-273"><strong>ConversationalMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="277e3-274">десятичное число (3, 2)</span><span class="sxs-lookup"><span data-stu-id="277e3-274">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="277e3-275">Нарровбанд MOS из сеансов голосовой связи (на основе обоих звуковых потоков).</span><span class="sxs-lookup"><span data-stu-id="277e3-275">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="277e3-276"><strong>Апплиедбандвидслимит</strong></span><span class="sxs-lookup"><span data-stu-id="277e3-276"><strong>AppliedBandwidthLimit</strong></span></span></p></td>
<td><p><span data-ttu-id="277e3-277">целое</span><span class="sxs-lookup"><span data-stu-id="277e3-277">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="277e3-278">Это фактическая пропускная способность, примененная к данному потоку отправки на стороне, для которой заданы различные параметры политики (повернуть, API, SDP, сервер политики и т. д.).</span><span class="sxs-lookup"><span data-stu-id="277e3-278">This is the actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on).</span></span> <span data-ttu-id="277e3-279">Это не следует путать с эффективной пропускной способностью, так как в зависимости от оценки пропускной способности может снизиться эффективная пропускная способность.</span><span class="sxs-lookup"><span data-stu-id="277e3-279">This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate.</span></span> <span data-ttu-id="277e3-280">Это является, по сути, максимальной пропускной способностью потока отправки, который может занимать ограничения пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="277e3-280">This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="277e3-281"><strong>Апплиедбандвидссаурцекэй</strong></span><span class="sxs-lookup"><span data-stu-id="277e3-281"><strong>AppliedBandwidthSourceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="277e3-282">smallint</span><span class="sxs-lookup"><span data-stu-id="277e3-282">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="277e3-283">Это источник установленного места для пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="277e3-283">This is the source of the bandwidth cap being imposed.</span></span> <span data-ttu-id="277e3-284">Она описывает, откуда поступают ограничения пропускной способности ("сервер политики", "превратить сервер", "модальность" и т. д.).</span><span class="sxs-lookup"><span data-stu-id="277e3-284">It describes where the bandwidth limit is coming from (“Policy Server”, “TURN Server”, “Modality”, and so on).</span></span> <span data-ttu-id="277e3-285">На которую ссылается <a href="lync-server-2013-appliedbandwidthsource-table.md">Таблица апплиедбандвидссаурце в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="277e3-285">Referenced from the <a href="lync-server-2013-appliedbandwidthsource-table.md">AppliedBandwidthSource table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="277e3-286"><strong>Вызывающая сторона</strong></span><span class="sxs-lookup"><span data-stu-id="277e3-286"><strong>Caller</strong></span></span></p></td>
<td><p><span data-ttu-id="277e3-287">бит</span><span class="sxs-lookup"><span data-stu-id="277e3-287">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="277e3-288">Указывает, получены ли метрики от вызывающего абонента; 1 — это "Да", значение null — "нет".</span><span class="sxs-lookup"><span data-stu-id="277e3-288">Indicates whether metrics from the caller were received; 1 is yes, a null value is no.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="277e3-289"><strong>Вызываемая сторона</strong></span><span class="sxs-lookup"><span data-stu-id="277e3-289"><strong>Callee</strong></span></span></p></td>
<td><p><span data-ttu-id="277e3-290">бит</span><span class="sxs-lookup"><span data-stu-id="277e3-290">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="277e3-291">Указывает, получены ли метрики от приемника вызова; 1 — это "Да", значение null — "нет".</span><span class="sxs-lookup"><span data-stu-id="277e3-291">Indicates whether metrics from the call receiver were received; 1 is yes, a null value is no.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="277e3-292"><strong>Мидкаллрепорт</strong></span><span class="sxs-lookup"><span data-stu-id="277e3-292"><strong>MidCallReport</strong></span></span></p></td>
<td><p><span data-ttu-id="277e3-293">бит</span><span class="sxs-lookup"><span data-stu-id="277e3-293">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="277e3-294">Указывает, является ли отчет частью сеанса или для полного сеанса.</span><span class="sxs-lookup"><span data-stu-id="277e3-294">Indicates whether the report is for a portion of the session or for the complete session.</span></span></p>
<p><span data-ttu-id="277e3-295">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="277e3-295">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="277e3-296"><strong>Классифиедпуркалл</strong></span><span class="sxs-lookup"><span data-stu-id="277e3-296"><strong>ClassifiedPoorCall</strong></span></span></p></td>
<td><p><span data-ttu-id="277e3-297">бит</span><span class="sxs-lookup"><span data-stu-id="277e3-297">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="277e3-298">Указывает, был ли звонок классифицирован как неудовлетворительный (значение 1) или как хороший звонок (0).</span><span class="sxs-lookup"><span data-stu-id="277e3-298">Indicates whether a call was classified as a poor call (value of 1) or as a good call (0).</span></span></p>
<p><span data-ttu-id="277e3-299">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="277e3-299">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="277e3-300"><strong>Каллерконнективитице</strong></span><span class="sxs-lookup"><span data-stu-id="277e3-300"><strong>CallerConnectivityICE</strong></span></span></p></td>
<td><p><span data-ttu-id="277e3-301">tinyInt</span><span class="sxs-lookup"><span data-stu-id="277e3-301">tinyInt</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="277e3-302">Указывает, подключен ли вызывающий абонент к сети с помощью протокола ICE (установление подключения к Интернету).</span><span class="sxs-lookup"><span data-stu-id="277e3-302">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p>
<p><span data-ttu-id="277e3-303">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="277e3-303">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="277e3-304"><strong>Калликоннективитице</strong></span><span class="sxs-lookup"><span data-stu-id="277e3-304"><strong>CalleeConnectivityICE</strong></span></span></p></td>
<td><p><span data-ttu-id="277e3-305">tinyint</span><span class="sxs-lookup"><span data-stu-id="277e3-305">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="277e3-306">Указывает, подключен ли вызывающий абонент к сети с помощью протокола ICE (установление подключения к Интернету).</span><span class="sxs-lookup"><span data-stu-id="277e3-306">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p>
<p><span data-ttu-id="277e3-307">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="277e3-307">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="277e3-308"><strong>Каллеррефлексивелокалипаддр</strong></span><span class="sxs-lookup"><span data-stu-id="277e3-308"><strong>CallerReflexiveLocalIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="277e3-309">целое</span><span class="sxs-lookup"><span data-stu-id="277e3-309">int</span></span></p></td>
<td><p><span data-ttu-id="277e3-310">Другом</span><span class="sxs-lookup"><span data-stu-id="277e3-310">Foreign</span></span></p></td>
<td><p><span data-ttu-id="277e3-311">IP-адрес пользователя, который поместил звонок.</span><span class="sxs-lookup"><span data-stu-id="277e3-311">Reflexive IP address of the user who placed the call.</span></span> <span data-ttu-id="277e3-312">В организациях, использующих NAT (преобразование сетевых адресов), можно использовать IP-адрес прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="277e3-312">In organizations that use NAT (network address translation), the reflexive IP address is the IP address of the proxy server.</span></span></p>
<p><span data-ttu-id="277e3-313">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="277e3-313">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="277e3-314"><strong>Каллервифидривердевицесдеск</strong></span><span class="sxs-lookup"><span data-stu-id="277e3-314"><strong>CallerWiFiDriverDevicesDesc</strong></span></span></p></td>
<td><p><span data-ttu-id="277e3-315">целое</span><span class="sxs-lookup"><span data-stu-id="277e3-315">int</span></span></p></td>
<td><p><span data-ttu-id="277e3-316">Другом</span><span class="sxs-lookup"><span data-stu-id="277e3-316">Foreign</span></span></p></td>
<td><p><span data-ttu-id="277e3-317">Описание устройства для драйвера Wi-Fi, задействованного пользовательским абонентом.</span><span class="sxs-lookup"><span data-stu-id="277e3-317">Device description for the WiFi driver employed by the user who placed the call.</span></span></p>
<p><span data-ttu-id="277e3-318">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="277e3-318">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="277e3-319"><strong>Каллервифидриверверсион</strong></span><span class="sxs-lookup"><span data-stu-id="277e3-319"><strong>CallerWiFiDriverVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="277e3-320">целое</span><span class="sxs-lookup"><span data-stu-id="277e3-320">int</span></span></p></td>
<td><p><span data-ttu-id="277e3-321">Другом</span><span class="sxs-lookup"><span data-stu-id="277e3-321">Foreign</span></span></p></td>
<td><p><span data-ttu-id="277e3-322">Номер версии для драйвера Wi-Fi, используемый пользователем, который присоединил звонок.</span><span class="sxs-lookup"><span data-stu-id="277e3-322">Version number for the WiFi driver employed by the user who placed the call.</span></span></p>
<p><span data-ttu-id="277e3-323">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="277e3-323">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="277e3-324"><strong>Каллерефлексивелокалипаддр</strong></span><span class="sxs-lookup"><span data-stu-id="277e3-324"><strong>CalleReflexiveLocalIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="277e3-325">целое</span><span class="sxs-lookup"><span data-stu-id="277e3-325">int</span></span></p></td>
<td><p><span data-ttu-id="277e3-326">Другом</span><span class="sxs-lookup"><span data-stu-id="277e3-326">Foreign</span></span></p></td>
<td><p><span data-ttu-id="277e3-327">IP-адрес пользователя, который получил звонок.</span><span class="sxs-lookup"><span data-stu-id="277e3-327">Reflexive IP address of the user who received the call.</span></span> <span data-ttu-id="277e3-328">В организациях, использующих NAT (преобразование сетевых адресов), можно использовать IP-адрес прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="277e3-328">In organizations that use NAT (network address translation), the reflexive IP address is the IP address of the proxy server.</span></span></p>
<p><span data-ttu-id="277e3-329">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="277e3-329">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="277e3-330"><strong>Калливифидривердевицесдеск</strong></span><span class="sxs-lookup"><span data-stu-id="277e3-330"><strong>CalleeWiFiDriverDevicesDesc</strong></span></span></p></td>
<td><p><span data-ttu-id="277e3-331">целое</span><span class="sxs-lookup"><span data-stu-id="277e3-331">int</span></span></p></td>
<td><p><span data-ttu-id="277e3-332">Другом</span><span class="sxs-lookup"><span data-stu-id="277e3-332">Foreign</span></span></p></td>
<td><p><span data-ttu-id="277e3-333">Описание устройства для драйвера Wi-Fi, применяемого пользователем, который получил звонок.</span><span class="sxs-lookup"><span data-stu-id="277e3-333">Device description for the WiFi driver employed by the user who received the call.</span></span></p>
<p><span data-ttu-id="277e3-334">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="277e3-334">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="277e3-335"><strong>Калливифидриверверсион</strong></span><span class="sxs-lookup"><span data-stu-id="277e3-335"><strong>CalleeWiFiDriverVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="277e3-336">целое</span><span class="sxs-lookup"><span data-stu-id="277e3-336">int</span></span></p></td>
<td><p><span data-ttu-id="277e3-337">Другом</span><span class="sxs-lookup"><span data-stu-id="277e3-337">Foreign</span></span></p></td>
<td><p><span data-ttu-id="277e3-338">Номер версии для драйвера Wi-Fi, используемый пользователем, который получил звонок.</span><span class="sxs-lookup"><span data-stu-id="277e3-338">Version number for the WiFi driver employed by the user who received the call.</span></span></p>
<p><span data-ttu-id="277e3-339">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="277e3-339">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

