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
ms.openlocfilehash: 3496b8fe96e2bdfcbb49ec0155d66ad4eeb106fa
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044921"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="medialine-table-in-lync-server-2013"></a><span data-ttu-id="bcd00-102">Таблица MediaLine в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bcd00-102">MediaLine table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bcd00-103">_**Последнее изменение темы:** 2014-02-21_</span><span class="sxs-lookup"><span data-stu-id="bcd00-103">_**Topic Last Modified:** 2014-02-21_</span></span>

<span data-ttu-id="bcd00-104">Каждая запись представляет одну линию мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="bcd00-104">Each record represents one media line.</span></span> <span data-ttu-id="bcd00-105">(Один звуковой сеанс обычно содержит одну линию звукового носителя).</span><span class="sxs-lookup"><span data-stu-id="bcd00-105">(One audio session usually contains one audio media line.</span></span> <span data-ttu-id="bcd00-106">Один сеанс аудио-и видеоданных (A/V) обычно содержит одну линию аудио-и видеоконференций, хотя в этом сеансе могут содержаться две видеолинии, если используется устройство для конференц-связи или если используется представление галереи.</span><span class="sxs-lookup"><span data-stu-id="bcd00-106">One audio and video (A/V) session usually contains one audio media line and one video media line, although the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bcd00-107"><strong>Column</strong></span><span class="sxs-lookup"><span data-stu-id="bcd00-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="bcd00-108"><strong>Тип данных</strong></span><span class="sxs-lookup"><span data-stu-id="bcd00-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="bcd00-109"><strong>Ключ или индекс</strong></span><span class="sxs-lookup"><span data-stu-id="bcd00-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="bcd00-110"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="bcd00-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bcd00-111"><strong>конференцедатетиме</strong></span><span class="sxs-lookup"><span data-stu-id="bcd00-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="bcd00-112">datetime</span><span class="sxs-lookup"><span data-stu-id="bcd00-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="bcd00-113">Primary</span><span class="sxs-lookup"><span data-stu-id="bcd00-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="bcd00-114">Ссылка из <a href="lync-server-2013-session-table.md">таблицы Sessions в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="bcd00-114">Referenced from the <a href="lync-server-2013-session-table.md">Session table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bcd00-115"><strong>сессионсек</strong></span><span class="sxs-lookup"><span data-stu-id="bcd00-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="bcd00-116">int</span><span class="sxs-lookup"><span data-stu-id="bcd00-116">int</span></span></p></td>
<td><p><span data-ttu-id="bcd00-117">Primary</span><span class="sxs-lookup"><span data-stu-id="bcd00-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="bcd00-118">Ссылка из <a href="lync-server-2013-session-table.md">таблицы Sessions в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="bcd00-118">Referenced from the <a href="lync-server-2013-session-table.md">Session table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bcd00-119"><strong>медиалинелабел</strong></span><span class="sxs-lookup"><span data-stu-id="bcd00-119"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="bcd00-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="bcd00-120">tinyint</span></span></p></td>
<td><p><span data-ttu-id="bcd00-121">Primary</span><span class="sxs-lookup"><span data-stu-id="bcd00-121">Primary</span></span></p></td>
<td><p><span data-ttu-id="bcd00-122">0 — это основной звук, 1 — основной видеоролик, а 2 — панорамное видео, 3 — общий доступ к приложениям и рабочим столам.</span><span class="sxs-lookup"><span data-stu-id="bcd00-122">0 is main audio, 1 is main video, and 2 is panoramic video, 3 is Application/Desktop Sharing.</span></span> <span data-ttu-id="bcd00-123">Эта метка должна быть уникальной в пределах одного сеанса.</span><span class="sxs-lookup"><span data-stu-id="bcd00-123">This label must be unique within a single session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bcd00-124"><strong>коннективитице</strong></span><span class="sxs-lookup"><span data-stu-id="bcd00-124"><strong>ConnectivityIce</strong></span></span></p></td>
<td><p><span data-ttu-id="bcd00-125">tinyint</span><span class="sxs-lookup"><span data-stu-id="bcd00-125">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="bcd00-126">Этот столбец присутствует, но не используется в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bcd00-126">This column is present but not used in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="bcd00-127">Сведения о подключении, используемом для линии мультимедиа, записываются в столбцах Каллерконнективитице и Калликоннективитице.</span><span class="sxs-lookup"><span data-stu-id="bcd00-127">Information about the connectivity used for a media line is captured in the CallerConnectivityICE and CalleeConnectivityICE columns.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bcd00-128"><strong>каллерицеварнингфлагс</strong></span><span class="sxs-lookup"><span data-stu-id="bcd00-128"><strong>CallerIceWarningFlags</strong></span></span></p></td>
<td><p><span data-ttu-id="bcd00-129">int</span><span class="sxs-lookup"><span data-stu-id="bcd00-129">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="bcd00-130">Сведения о процессе интерактивной установки подключения (ICE), описанные в разделе Флаги BITS.</span><span class="sxs-lookup"><span data-stu-id="bcd00-130">Information about Interactive Connectivity Establishment (ICE) process described in bits flags.</span></span> <span data-ttu-id="bcd00-131">Дополнительные сведения можно найти в <em>спецификации протокола сервера мониторинга качества взаимодействия</em>, доступной для загрузки.</span><span class="sxs-lookup"><span data-stu-id="bcd00-131">For details, refer to the <em>Quality of Experience Monitoring Server Protocol Specification</em>, available for download.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bcd00-132"><strong>каллиицеварнингфлагс</strong></span><span class="sxs-lookup"><span data-stu-id="bcd00-132"><strong>CalleeIceWarningFlags</strong></span></span></p></td>
<td><p><span data-ttu-id="bcd00-133">int</span><span class="sxs-lookup"><span data-stu-id="bcd00-133">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="bcd00-134">То же, что и Каллерицеварнингфлагс, но на стороне вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="bcd00-134">Same as CallerIceWarningFlags, but on the callee side.</span></span> <span data-ttu-id="bcd00-135">Дополнительные сведения можно найти в <em>спецификации протокола сервера мониторинга качества взаимодействия</em>, доступной для загрузки.</span><span class="sxs-lookup"><span data-stu-id="bcd00-135">For details, refer to the <em>Quality of Experience Monitoring Server Protocol Specification</em>, available for download.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bcd00-136"><strong>Безопасность</strong></span><span class="sxs-lookup"><span data-stu-id="bcd00-136"><strong>Security</strong></span></span></p></td>
<td><p><span data-ttu-id="bcd00-137">tinyint</span><span class="sxs-lookup"><span data-stu-id="bcd00-137">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="bcd00-138">Используемый профиль безопасности.</span><span class="sxs-lookup"><span data-stu-id="bcd00-138">The security profile in use.</span></span> <span data-ttu-id="bcd00-139">0 – это NONE, 1 – SRTP, 2 – V1.</span><span class="sxs-lookup"><span data-stu-id="bcd00-139">0 is NONE, 1 is SRTP, 2 is V1.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bcd00-140"><strong>Transport</strong></span><span class="sxs-lookup"><span data-stu-id="bcd00-140"><strong>Transport</strong></span></span></p></td>
<td><p><span data-ttu-id="bcd00-141">tinyint</span><span class="sxs-lookup"><span data-stu-id="bcd00-141">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="bcd00-142">0 соответствует протоколу UDP, 1 – протоколу TCP.</span><span class="sxs-lookup"><span data-stu-id="bcd00-142">0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bcd00-143"><strong>каллерипаддр</strong></span><span class="sxs-lookup"><span data-stu-id="bcd00-143"><strong>CallerIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="bcd00-144">int</span><span class="sxs-lookup"><span data-stu-id="bcd00-144">int</span></span></p></td>
<td><p><span data-ttu-id="bcd00-145">Правительства</span><span class="sxs-lookup"><span data-stu-id="bcd00-145">Foreign</span></span></p></td>
<td><p><span data-ttu-id="bcd00-146">IP-адрес вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="bcd00-146">IP Address of the caller.</span></span> <span data-ttu-id="bcd00-147">Дополнительные сведения см. <a href="lync-server-2013-ipaddress-table.md">в таблице IPAddress в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="bcd00-147">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bcd00-148"><strong>каллерпорт</strong></span><span class="sxs-lookup"><span data-stu-id="bcd00-148"><strong>CallerPort</strong></span></span></p></td>
<td><p><span data-ttu-id="bcd00-149">int</span><span class="sxs-lookup"><span data-stu-id="bcd00-149">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="bcd00-150">Порт, используемый вызывающим абонентом.</span><span class="sxs-lookup"><span data-stu-id="bcd00-150">Port used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bcd00-151"><strong>каллерсубнет</strong></span><span class="sxs-lookup"><span data-stu-id="bcd00-151"><strong>CallerSubnet</strong></span></span></p></td>
<td><p><span data-ttu-id="bcd00-152">int</span><span class="sxs-lookup"><span data-stu-id="bcd00-152">int</span></span></p></td>
<td><p><span data-ttu-id="bcd00-153"> Правительства</span><span class="sxs-lookup"><span data-stu-id="bcd00-153"> Foreign</span></span></p></td>
<td><p><span data-ttu-id="bcd00-154">Подсеть вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="bcd00-154">The subnet of the caller.</span></span> <span data-ttu-id="bcd00-155">Дополнительные сведения см. <a href="lync-server-2013-ipaddress-table.md">в таблице IPAddress в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="bcd00-155">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bcd00-156"><strong>каллеринсиде</strong></span><span class="sxs-lookup"><span data-stu-id="bcd00-156"><strong>CallerInside</strong></span></span></p></td>
<td><p><span data-ttu-id="bcd00-157">Битовая</span><span class="sxs-lookup"><span data-stu-id="bcd00-157">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="bcd00-158">1 означает, что вызывающий абонент находится внутри корпоративной сети, 0 означает, что вызывающий абонент находится за пределами сети.</span><span class="sxs-lookup"><span data-stu-id="bcd00-158">1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bcd00-159"><strong>каллермакаддресс</strong></span><span class="sxs-lookup"><span data-stu-id="bcd00-159"><strong>CallerMacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="bcd00-160">int</span><span class="sxs-lookup"><span data-stu-id="bcd00-160">int</span></span></p></td>
<td><p><span data-ttu-id="bcd00-161">Правительства</span><span class="sxs-lookup"><span data-stu-id="bcd00-161">Foreign</span></span></p></td>
<td><p><span data-ttu-id="bcd00-162">Mac-адрес вызывающего абонента, на который ссылается <a href="lync-server-2013-macaddress-table.md">Таблица MacAddress в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="bcd00-162">Caller’s mac address, referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bcd00-163"><strong>каллеррелайипаддр</strong></span><span class="sxs-lookup"><span data-stu-id="bcd00-163"><strong>CallerRelayIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="bcd00-164">int</span><span class="sxs-lookup"><span data-stu-id="bcd00-164">int</span></span></p></td>
<td><p><span data-ttu-id="bcd00-165">Правительства</span><span class="sxs-lookup"><span data-stu-id="bcd00-165">Foreign</span></span></p></td>
<td><p><span data-ttu-id="bcd00-166">IP-адрес пограничной службы Lync Server A/V, используемой вызывающим абонентом.</span><span class="sxs-lookup"><span data-stu-id="bcd00-166">IP Address of the Lync Server A/V Edge service used by the caller.</span></span> <span data-ttu-id="bcd00-167">Дополнительные сведения см. <a href="lync-server-2013-ipaddress-table.md">в таблице IPAddress в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="bcd00-167">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bcd00-168"><strong>каллеррелайпорт</strong></span><span class="sxs-lookup"><span data-stu-id="bcd00-168"><strong>CallerRelayPort</strong></span></span></p></td>
<td><p><span data-ttu-id="bcd00-169">int</span><span class="sxs-lookup"><span data-stu-id="bcd00-169">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="bcd00-170">Порт, используемый вызывающим абонентом для пограничной службы аудио-и видеоданных.</span><span class="sxs-lookup"><span data-stu-id="bcd00-170">Port used on the A/V Edge service by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bcd00-171"><strong>каллеркаптуредев</strong></span><span class="sxs-lookup"><span data-stu-id="bcd00-171"><strong>CallerCaptureDev</strong></span></span></p></td>
<td><p><span data-ttu-id="bcd00-172">int</span><span class="sxs-lookup"><span data-stu-id="bcd00-172">int</span></span></p></td>
<td><p><span data-ttu-id="bcd00-173">Правительства</span><span class="sxs-lookup"><span data-stu-id="bcd00-173">Foreign</span></span></p></td>
<td><p><span data-ttu-id="bcd00-174">Устройство захвата, используемое вызывающим абонентом.</span><span class="sxs-lookup"><span data-stu-id="bcd00-174">Capture device used by the caller.</span></span> <span data-ttu-id="bcd00-175">Ссылка из <a href="lync-server-2013-device-table.md">таблицы устройств в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="bcd00-175">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bcd00-176"><strong>каллеррендердев</strong></span><span class="sxs-lookup"><span data-stu-id="bcd00-176"><strong>CallerRenderDev</strong></span></span></p></td>
<td><p><span data-ttu-id="bcd00-177">int</span><span class="sxs-lookup"><span data-stu-id="bcd00-177">int</span></span></p></td>
<td><p><span data-ttu-id="bcd00-178">Правительства</span><span class="sxs-lookup"><span data-stu-id="bcd00-178">Foreign</span></span></p></td>
<td><p><span data-ttu-id="bcd00-179">Устройство отображения, используемое вызывающим абонентом.</span><span class="sxs-lookup"><span data-stu-id="bcd00-179">Render device used by caller.</span></span> <span data-ttu-id="bcd00-180">Ссылка из <a href="lync-server-2013-device-table.md">таблицы устройств в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="bcd00-180">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bcd00-181"><strong>каллеркаптуредевдривер</strong></span><span class="sxs-lookup"><span data-stu-id="bcd00-181"><strong>CallerCaptureDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="bcd00-182">int</span><span class="sxs-lookup"><span data-stu-id="bcd00-182">int</span></span></p></td>
<td><p><span data-ttu-id="bcd00-183">Правительства</span><span class="sxs-lookup"><span data-stu-id="bcd00-183">Foreign</span></span></p></td>
<td><p><span data-ttu-id="bcd00-184">Драйвер устройства захвата вызывающего абонента, на который ссылается <a href="lync-server-2013-devicedriver-table.md">таблица таблица devicedriver в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="bcd00-184">Driver for the caller’s capture device, referenced from the <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bcd00-185"><strong>каллеррендердевдривер</strong></span><span class="sxs-lookup"><span data-stu-id="bcd00-185"><strong>CallerRenderDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="bcd00-186">int</span><span class="sxs-lookup"><span data-stu-id="bcd00-186">int</span></span></p></td>
<td><p><span data-ttu-id="bcd00-187">Правительства</span><span class="sxs-lookup"><span data-stu-id="bcd00-187">Foreign</span></span></p></td>
<td><p><span data-ttu-id="bcd00-188">Драйвер для устройства отрисовки вызывающего абонента, на который ссылается <a href="lync-server-2013-devicedriver-table.md">таблица таблица devicedriver в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="bcd00-188">Driver for the caller’s render device, referenced from the <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bcd00-189"><strong>каллернетворкконнектионтипе</strong></span><span class="sxs-lookup"><span data-stu-id="bcd00-189"><strong>CallerNetworkConnectionType</strong></span></span></p></td>
<td><p><span data-ttu-id="bcd00-190">tinyint</span><span class="sxs-lookup"><span data-stu-id="bcd00-190">tinyint</span></span></p></td>
<td><p><span data-ttu-id="bcd00-191">Правительства</span><span class="sxs-lookup"><span data-stu-id="bcd00-191">Foreign</span></span></p></td>
<td><p><span data-ttu-id="bcd00-192">Показывает, как вызывающий абонент подключился к сети.</span><span class="sxs-lookup"><span data-stu-id="bcd00-192">Indicates how the caller connected to the network.</span></span> <span data-ttu-id="bcd00-193">Значения берутся из <a href="lync-server-2013-networkconnectiondetail-table.md">таблицы нетворкконнектиондетаил в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="bcd00-193">Values are obtained from the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a>.</span></span> <span data-ttu-id="bcd00-194">Типичные значения: 0 для проводного подключения 1 для подключения WiFi; и 3 для подключения Ethernet.</span><span class="sxs-lookup"><span data-stu-id="bcd00-194">Typical values are 0 for a wired connection’ 1 for a WiFi connection; and 3 for an Ethernet connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bcd00-195"><strong>каллербссид</strong></span><span class="sxs-lookup"><span data-stu-id="bcd00-195"><strong>CallerBssid</strong></span></span></p></td>
<td><p><span data-ttu-id="bcd00-196">int</span><span class="sxs-lookup"><span data-stu-id="bcd00-196">int</span></span></p></td>
<td><p><span data-ttu-id="bcd00-197">Правительства</span><span class="sxs-lookup"><span data-stu-id="bcd00-197">Foreign</span></span></p></td>
<td><p><span data-ttu-id="bcd00-198">BSSID для вызывающего абонента при использовании беспроводной связи.</span><span class="sxs-lookup"><span data-stu-id="bcd00-198">Caller’s BSSID if wireless is used.</span></span> <span data-ttu-id="bcd00-199">Ссылка из <a href="lync-server-2013-macaddress-table.md">таблицы MacAddress в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="bcd00-199">Referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bcd00-200"><strong>каллервпн</strong></span><span class="sxs-lookup"><span data-stu-id="bcd00-200"><strong>CallerVPN</strong></span></span></p></td>
<td><p><span data-ttu-id="bcd00-201">Битовая</span><span class="sxs-lookup"><span data-stu-id="bcd00-201">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bcd00-202">Ссылка вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="bcd00-202">The caller's link.</span></span> <span data-ttu-id="bcd00-203">1 – подключен к виртуальной частной сети, 0 – не подключен к виртуальной частной сети.</span><span class="sxs-lookup"><span data-stu-id="bcd00-203">1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bcd00-204"><strong>каллерлинкспид</strong></span><span class="sxs-lookup"><span data-stu-id="bcd00-204"><strong>CallerLinkSpeed</strong></span></span></p></td>
<td><p><span data-ttu-id="bcd00-205">десятичное число (18, 0)</span><span class="sxs-lookup"><span data-stu-id="bcd00-205">decimal(18,0)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bcd00-206">Скорость сетевого соединения в бит/с для конечной точки вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="bcd00-206">The network link speed, in bps, for the caller's endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bcd00-207"><strong>каллиипаддр</strong></span><span class="sxs-lookup"><span data-stu-id="bcd00-207"><strong>CalleeIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="bcd00-208">int</span><span class="sxs-lookup"><span data-stu-id="bcd00-208">int</span></span></p></td>
<td><p><span data-ttu-id="bcd00-209">Правительства</span><span class="sxs-lookup"><span data-stu-id="bcd00-209">Foreign</span></span></p></td>
<td><p><span data-ttu-id="bcd00-210">IP-адрес приемника вызовов.</span><span class="sxs-lookup"><span data-stu-id="bcd00-210">IP Address of the call receiver.</span></span> <span data-ttu-id="bcd00-211">Дополнительные сведения см. <a href="lync-server-2013-ipaddress-table.md">в таблице IPAddress в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="bcd00-211">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bcd00-212"><strong>каллипорт</strong></span><span class="sxs-lookup"><span data-stu-id="bcd00-212"><strong>CalleePort</strong></span></span></p></td>
<td><p><span data-ttu-id="bcd00-213">Битовая</span><span class="sxs-lookup"><span data-stu-id="bcd00-213">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bcd00-214">Порт, используемый приемником вызовов.</span><span class="sxs-lookup"><span data-stu-id="bcd00-214">Port used by the call receiver.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bcd00-215"><strong>каллисубнет</strong></span><span class="sxs-lookup"><span data-stu-id="bcd00-215"><strong>CalleeSubnet</strong></span></span></p></td>
<td><p><span data-ttu-id="bcd00-216">int</span><span class="sxs-lookup"><span data-stu-id="bcd00-216">int</span></span></p></td>
<td><p><span data-ttu-id="bcd00-217">Правительства</span><span class="sxs-lookup"><span data-stu-id="bcd00-217">Foreign</span></span></p></td>
<td><p><span data-ttu-id="bcd00-218">Подсеть вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="bcd00-218">Subnet of callee.</span></span> <span data-ttu-id="bcd00-219">Дополнительные сведения см. <a href="lync-server-2013-ipaddress-table.md">в таблице IPAddress в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="bcd00-219">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bcd00-220"><strong>каллиинсиде</strong></span><span class="sxs-lookup"><span data-stu-id="bcd00-220"><strong>CalleeInside</strong></span></span></p></td>
<td><p><span data-ttu-id="bcd00-221">Битовая</span><span class="sxs-lookup"><span data-stu-id="bcd00-221">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="bcd00-222">1 означает, что получатель вызова находится внутри корпоративной сети, 0 означает, что приемник вызовов находится за пределами сети.</span><span class="sxs-lookup"><span data-stu-id="bcd00-222">1 means call receiver is inside the enterprise network, 0 means the call receiver is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bcd00-223"><strong>каллимакаддресс</strong></span><span class="sxs-lookup"><span data-stu-id="bcd00-223"><strong>CalleeMacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="bcd00-224">int</span><span class="sxs-lookup"><span data-stu-id="bcd00-224">int</span></span></p></td>
<td><p><span data-ttu-id="bcd00-225">Правительства</span><span class="sxs-lookup"><span data-stu-id="bcd00-225">Foreign</span></span></p></td>
<td><p><span data-ttu-id="bcd00-226">Mac-адрес вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="bcd00-226">Callee Mac address.</span></span> <span data-ttu-id="bcd00-227">Ссылка из <a href="lync-server-2013-macaddress-table.md">таблицы MacAddress в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="bcd00-227">Referenced from the <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bcd00-228"><strong>каллирелайипаддр</strong></span><span class="sxs-lookup"><span data-stu-id="bcd00-228"><strong>CalleeRelayIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="bcd00-229">int</span><span class="sxs-lookup"><span data-stu-id="bcd00-229">int</span></span></p></td>
<td><p><span data-ttu-id="bcd00-230">Правительства</span><span class="sxs-lookup"><span data-stu-id="bcd00-230">Foreign</span></span></p></td>
<td><p><span data-ttu-id="bcd00-231">IP-адрес пограничной службы аудио-и видеоданных, используемой приемником вызовов.</span><span class="sxs-lookup"><span data-stu-id="bcd00-231">IP Address of the A/V Edge service used by the call receiver.</span></span> <span data-ttu-id="bcd00-232">Дополнительные сведения см. <a href="lync-server-2013-ipaddress-table.md">в таблице IPAddress в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="bcd00-232">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bcd00-233"><strong>каллирелайпорт</strong></span><span class="sxs-lookup"><span data-stu-id="bcd00-233"><strong>CalleeRelayPort</strong></span></span></p></td>
<td><p><span data-ttu-id="bcd00-234">int</span><span class="sxs-lookup"><span data-stu-id="bcd00-234">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="bcd00-235">Порт, используемый приемником вызовов для пограничной службы аудио-и видеоданных.</span><span class="sxs-lookup"><span data-stu-id="bcd00-235">Port used on the A/V Edge Service by the call receiver.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bcd00-236"><strong>калликаптуредев</strong></span><span class="sxs-lookup"><span data-stu-id="bcd00-236"><strong>CalleeCaptureDev</strong></span></span></p></td>
<td><p><span data-ttu-id="bcd00-237">int</span><span class="sxs-lookup"><span data-stu-id="bcd00-237">int</span></span></p></td>
<td><p><span data-ttu-id="bcd00-238">правительства</span><span class="sxs-lookup"><span data-stu-id="bcd00-238">foreign</span></span></p></td>
<td><p><span data-ttu-id="bcd00-239">Устройство захвата, используемое приемником вызовов.</span><span class="sxs-lookup"><span data-stu-id="bcd00-239">Capture device used by the call receiver.</span></span> <span data-ttu-id="bcd00-240">Ссылка из <a href="lync-server-2013-device-table.md">таблицы устройств в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="bcd00-240">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bcd00-241"><strong>каллирендердев</strong></span><span class="sxs-lookup"><span data-stu-id="bcd00-241"><strong>CalleeRenderDev</strong></span></span></p></td>
<td><p><span data-ttu-id="bcd00-242">int</span><span class="sxs-lookup"><span data-stu-id="bcd00-242">int</span></span></p></td>
<td><p><span data-ttu-id="bcd00-243">Правительства</span><span class="sxs-lookup"><span data-stu-id="bcd00-243">Foreign</span></span></p></td>
<td><p><span data-ttu-id="bcd00-244">Устройство отображения, используемое приемником вызовов.</span><span class="sxs-lookup"><span data-stu-id="bcd00-244">Render device used by the call receiver.</span></span> <span data-ttu-id="bcd00-245">Ссылка из <a href="lync-server-2013-device-table.md">таблицы устройств в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="bcd00-245">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bcd00-246"><strong>калликаптуредевдривер</strong></span><span class="sxs-lookup"><span data-stu-id="bcd00-246"><strong>CalleeCaptureDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="bcd00-247">int</span><span class="sxs-lookup"><span data-stu-id="bcd00-247">int</span></span></p></td>
<td><p><span data-ttu-id="bcd00-248">Правительства</span><span class="sxs-lookup"><span data-stu-id="bcd00-248">Foreign</span></span></p></td>
<td><p><span data-ttu-id="bcd00-249">Драйвер устройства захвата приемника вызовов.</span><span class="sxs-lookup"><span data-stu-id="bcd00-249">Driver for the call receiver’s capture device.</span></span> <span data-ttu-id="bcd00-250">Ссылка из <a href="lync-server-2013-devicedriver-table.md">таблицы таблица devicedriver в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="bcd00-250">Referenced from <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bcd00-251"><strong>каллирендердевдривер</strong></span><span class="sxs-lookup"><span data-stu-id="bcd00-251"><strong>CalleeRenderDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="bcd00-252">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="bcd00-252">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="bcd00-253">Правительства</span><span class="sxs-lookup"><span data-stu-id="bcd00-253">Foreign</span></span></p></td>
<td><p><span data-ttu-id="bcd00-254">Драйвер устройства обработки для приемника вызовов.</span><span class="sxs-lookup"><span data-stu-id="bcd00-254">Driver for the call receiver’s render device.</span></span> <span data-ttu-id="bcd00-255">Ссылка из <a href="lync-server-2013-devicedriver-table.md">таблицы таблица devicedriver в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="bcd00-255">Referenced from <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bcd00-256"><strong>каллинетворкконнектионтипе</strong></span><span class="sxs-lookup"><span data-stu-id="bcd00-256"><strong>CalleeNetworkConnectionType</strong></span></span></p></td>
<td><p><span data-ttu-id="bcd00-257">tinyint</span><span class="sxs-lookup"><span data-stu-id="bcd00-257">tinyint</span></span></p></td>
<td><p><span data-ttu-id="bcd00-258">Правительства</span><span class="sxs-lookup"><span data-stu-id="bcd00-258">Foreign</span></span></p></td>
<td><p><span data-ttu-id="bcd00-259">Показывает, как вызываемый абонент подключился к сети.</span><span class="sxs-lookup"><span data-stu-id="bcd00-259">Indicates how the callee connected to the network.</span></span> <span data-ttu-id="bcd00-260">Значения берутся из <a href="lync-server-2013-networkconnectiondetail-table.md">таблицы нетворкконнектиондетаил в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="bcd00-260">Values are obtained from the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a>.</span></span> <span data-ttu-id="bcd00-261">Типичные значения: 0 для проводного подключения 1 для подключения WiFi; и 3 для подключения Ethernet.</span><span class="sxs-lookup"><span data-stu-id="bcd00-261">Typical values are 0 for a wired connection’ 1 for a WiFi connection; and 3 for an Ethernet connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bcd00-262"><strong>каллибссид</strong></span><span class="sxs-lookup"><span data-stu-id="bcd00-262"><strong>CalleeBssid</strong></span></span></p></td>
<td><p><span data-ttu-id="bcd00-263">int</span><span class="sxs-lookup"><span data-stu-id="bcd00-263">int</span></span></p></td>
<td><p><span data-ttu-id="bcd00-264">Правительства</span><span class="sxs-lookup"><span data-stu-id="bcd00-264">Foreign</span></span></p></td>
<td><p><span data-ttu-id="bcd00-265">BSSID для вызываемого абонента, если используется беспроводной доступ.</span><span class="sxs-lookup"><span data-stu-id="bcd00-265">Callee’s BSSID if wireless is used.</span></span> <span data-ttu-id="bcd00-266">Ссылка из <a href="lync-server-2013-macaddress-table.md">таблицы MacAddress в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="bcd00-266">Referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bcd00-267"><strong>калливпн</strong></span><span class="sxs-lookup"><span data-stu-id="bcd00-267"><strong>CalleeVPN</strong></span></span></p></td>
<td><p><span data-ttu-id="bcd00-268">Битовая</span><span class="sxs-lookup"><span data-stu-id="bcd00-268">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="bcd00-269">Ссылка приемника вызовов; 1 — это виртуальная частная сеть (VPN), 0 — не VPN.</span><span class="sxs-lookup"><span data-stu-id="bcd00-269">The call receiver’s link; 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bcd00-270"><strong>каллилинкспид</strong></span><span class="sxs-lookup"><span data-stu-id="bcd00-270"><strong>CalleeLinkSpeed</strong></span></span></p></td>
<td><p><span data-ttu-id="bcd00-271">десятичное число (18, 0)</span><span class="sxs-lookup"><span data-stu-id="bcd00-271">decimal(18,0)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="bcd00-272">Скорость сетевого соединения в бит/с для конечной точки приемника вызовов.</span><span class="sxs-lookup"><span data-stu-id="bcd00-272">The network link speed, in bps, for the call receiver’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bcd00-273"><strong>конверсатионалмос</strong></span><span class="sxs-lookup"><span data-stu-id="bcd00-273"><strong>ConversationalMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="bcd00-274">десятичное число (3, 2)</span><span class="sxs-lookup"><span data-stu-id="bcd00-274">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="bcd00-275">Узкополосный MOS аудиосеансов (на основе обоих аудиопотоков).</span><span class="sxs-lookup"><span data-stu-id="bcd00-275">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bcd00-276"><strong>апплиедбандвидслимит</strong></span><span class="sxs-lookup"><span data-stu-id="bcd00-276"><strong>AppliedBandwidthLimit</strong></span></span></p></td>
<td><p><span data-ttu-id="bcd00-277">int</span><span class="sxs-lookup"><span data-stu-id="bcd00-277">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bcd00-278">Это фактическая пропускная способность, примененная к потоку отправки на стороне, в которой задаются различные параметры политики (TURN, API, SDP, сервер политики и т. д.).</span><span class="sxs-lookup"><span data-stu-id="bcd00-278">This is the actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on).</span></span> <span data-ttu-id="bcd00-279">Ее не следует путать с эффективной пропускной способностью, потому что эффективная пропускная способность может быть меньше в зависимости от оценки пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="bcd00-279">This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate.</span></span> <span data-ttu-id="bcd00-280">По сути это в основном максимальная пропускная способность потока отправителя с учетом ограничений, наложенных оценкой пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="bcd00-280">This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bcd00-281"><strong>апплиедбандвидссаурцекэй</strong></span><span class="sxs-lookup"><span data-stu-id="bcd00-281"><strong>AppliedBandwidthSourceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="bcd00-282">smallint</span><span class="sxs-lookup"><span data-stu-id="bcd00-282">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bcd00-283">Источник применяемого ограничения пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="bcd00-283">This is the source of the bandwidth cap being imposed.</span></span> <span data-ttu-id="bcd00-284">В нем описывается, откуда поступает предельный объем пропускной способности ("сервер политики", "превратить сервер", "модальность" и т. д.).</span><span class="sxs-lookup"><span data-stu-id="bcd00-284">It describes where the bandwidth limit is coming from (“Policy Server”, “TURN Server”, “Modality”, and so on).</span></span> <span data-ttu-id="bcd00-285">Ссылка из <a href="lync-server-2013-appliedbandwidthsource-table.md">таблицы таблица appliedbandwidthsource в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="bcd00-285">Referenced from the <a href="lync-server-2013-appliedbandwidthsource-table.md">AppliedBandwidthSource table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bcd00-286"><strong>Caller</strong></span><span class="sxs-lookup"><span data-stu-id="bcd00-286"><strong>Caller</strong></span></span></p></td>
<td><p><span data-ttu-id="bcd00-287">Битовая</span><span class="sxs-lookup"><span data-stu-id="bcd00-287">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="bcd00-288">Указывает, были ли получены метрики от вызывающего абонента; 1 — значение "Да", NULL — нет.</span><span class="sxs-lookup"><span data-stu-id="bcd00-288">Indicates whether metrics from the caller were received; 1 is yes, a null value is no.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bcd00-289"><strong>Вызываемого абонента</strong></span><span class="sxs-lookup"><span data-stu-id="bcd00-289"><strong>Callee</strong></span></span></p></td>
<td><p><span data-ttu-id="bcd00-290">Битовая</span><span class="sxs-lookup"><span data-stu-id="bcd00-290">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="bcd00-291">Указывает, были ли получены метрики от приемника вызовов; 1 — значение "Да", NULL — нет.</span><span class="sxs-lookup"><span data-stu-id="bcd00-291">Indicates whether metrics from the call receiver were received; 1 is yes, a null value is no.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bcd00-292"><strong>мидкаллрепорт</strong></span><span class="sxs-lookup"><span data-stu-id="bcd00-292"><strong>MidCallReport</strong></span></span></p></td>
<td><p><span data-ttu-id="bcd00-293">Битовая</span><span class="sxs-lookup"><span data-stu-id="bcd00-293">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bcd00-294">Указывает, относится ли отчет к части сеанса или к полному сеансу.</span><span class="sxs-lookup"><span data-stu-id="bcd00-294">Indicates whether the report is for a portion of the session or for the complete session.</span></span></p>
<p><span data-ttu-id="bcd00-295">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bcd00-295">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bcd00-296"><strong>классифиедпуркалл</strong></span><span class="sxs-lookup"><span data-stu-id="bcd00-296"><strong>ClassifiedPoorCall</strong></span></span></p></td>
<td><p><span data-ttu-id="bcd00-297">Битовая</span><span class="sxs-lookup"><span data-stu-id="bcd00-297">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bcd00-298">Указывает, был ли вызов классифицирован как плохой вызов (значение 1) или как хороший вызов (0).</span><span class="sxs-lookup"><span data-stu-id="bcd00-298">Indicates whether a call was classified as a poor call (value of 1) or as a good call (0).</span></span></p>
<p><span data-ttu-id="bcd00-299">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bcd00-299">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bcd00-300"><strong>каллерконнективитице</strong></span><span class="sxs-lookup"><span data-stu-id="bcd00-300"><strong>CallerConnectivityICE</strong></span></span></p></td>
<td><p><span data-ttu-id="bcd00-301">tinyInt</span><span class="sxs-lookup"><span data-stu-id="bcd00-301">tinyInt</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bcd00-302">Указывает, подключен ли абонент к сети через протокол ICE (Internet Connectivity Establishment).</span><span class="sxs-lookup"><span data-stu-id="bcd00-302">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p>
<p><span data-ttu-id="bcd00-303">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bcd00-303">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bcd00-304"><strong>калликоннективитице</strong></span><span class="sxs-lookup"><span data-stu-id="bcd00-304"><strong>CalleeConnectivityICE</strong></span></span></p></td>
<td><p><span data-ttu-id="bcd00-305">tinyint</span><span class="sxs-lookup"><span data-stu-id="bcd00-305">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bcd00-306">Указывает, подключен ли абонент к сети через протокол ICE (Internet Connectivity Establishment).</span><span class="sxs-lookup"><span data-stu-id="bcd00-306">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p>
<p><span data-ttu-id="bcd00-307">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bcd00-307">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bcd00-308"><strong>каллеррефлексивелокалипаддр</strong></span><span class="sxs-lookup"><span data-stu-id="bcd00-308"><strong>CallerReflexiveLocalIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="bcd00-309">int</span><span class="sxs-lookup"><span data-stu-id="bcd00-309">int</span></span></p></td>
<td><p><span data-ttu-id="bcd00-310">Правительства</span><span class="sxs-lookup"><span data-stu-id="bcd00-310">Foreign</span></span></p></td>
<td><p><span data-ttu-id="bcd00-311">IP-адрес пользователя, который поместил вызов.</span><span class="sxs-lookup"><span data-stu-id="bcd00-311">Reflexive IP address of the user who placed the call.</span></span> <span data-ttu-id="bcd00-312">В организациях, использующих NAT (преобразование сетевых адресов), это IP-адрес прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="bcd00-312">In organizations that use NAT (network address translation), the reflexive IP address is the IP address of the proxy server.</span></span></p>
<p><span data-ttu-id="bcd00-313">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bcd00-313">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bcd00-314"><strong>каллервифидривердевицесдеск</strong></span><span class="sxs-lookup"><span data-stu-id="bcd00-314"><strong>CallerWiFiDriverDevicesDesc</strong></span></span></p></td>
<td><p><span data-ttu-id="bcd00-315">int</span><span class="sxs-lookup"><span data-stu-id="bcd00-315">int</span></span></p></td>
<td><p><span data-ttu-id="bcd00-316">Правительства</span><span class="sxs-lookup"><span data-stu-id="bcd00-316">Foreign</span></span></p></td>
<td><p><span data-ttu-id="bcd00-317">Описание устройства для драйвера Wi-Fi, используемого пользователем, который поместил звонок.</span><span class="sxs-lookup"><span data-stu-id="bcd00-317">Device description for the WiFi driver employed by the user who placed the call.</span></span></p>
<p><span data-ttu-id="bcd00-318">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bcd00-318">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bcd00-319"><strong>каллервифидриверверсион</strong></span><span class="sxs-lookup"><span data-stu-id="bcd00-319"><strong>CallerWiFiDriverVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="bcd00-320">int</span><span class="sxs-lookup"><span data-stu-id="bcd00-320">int</span></span></p></td>
<td><p><span data-ttu-id="bcd00-321">Правительства</span><span class="sxs-lookup"><span data-stu-id="bcd00-321">Foreign</span></span></p></td>
<td><p><span data-ttu-id="bcd00-322">Номер версии драйвера Wi-Fi, используемый пользователем, который поместил звонок.</span><span class="sxs-lookup"><span data-stu-id="bcd00-322">Version number for the WiFi driver employed by the user who placed the call.</span></span></p>
<p><span data-ttu-id="bcd00-323">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bcd00-323">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bcd00-324"><strong>каллерефлексивелокалипаддр</strong></span><span class="sxs-lookup"><span data-stu-id="bcd00-324"><strong>CalleReflexiveLocalIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="bcd00-325">int</span><span class="sxs-lookup"><span data-stu-id="bcd00-325">int</span></span></p></td>
<td><p><span data-ttu-id="bcd00-326">Правительства</span><span class="sxs-lookup"><span data-stu-id="bcd00-326">Foreign</span></span></p></td>
<td><p><span data-ttu-id="bcd00-327">IP-адрес пользователя, который получил вызов.</span><span class="sxs-lookup"><span data-stu-id="bcd00-327">Reflexive IP address of the user who received the call.</span></span> <span data-ttu-id="bcd00-328">В организациях, использующих NAT (преобразование сетевых адресов), это IP-адрес прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="bcd00-328">In organizations that use NAT (network address translation), the reflexive IP address is the IP address of the proxy server.</span></span></p>
<p><span data-ttu-id="bcd00-329">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bcd00-329">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bcd00-330"><strong>калливифидривердевицесдеск</strong></span><span class="sxs-lookup"><span data-stu-id="bcd00-330"><strong>CalleeWiFiDriverDevicesDesc</strong></span></span></p></td>
<td><p><span data-ttu-id="bcd00-331">int</span><span class="sxs-lookup"><span data-stu-id="bcd00-331">int</span></span></p></td>
<td><p><span data-ttu-id="bcd00-332">Правительства</span><span class="sxs-lookup"><span data-stu-id="bcd00-332">Foreign</span></span></p></td>
<td><p><span data-ttu-id="bcd00-333">Описание устройства для драйвера Wi-Fi, используемого пользователем, который получил вызов.</span><span class="sxs-lookup"><span data-stu-id="bcd00-333">Device description for the WiFi driver employed by the user who received the call.</span></span></p>
<p><span data-ttu-id="bcd00-334">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bcd00-334">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bcd00-335"><strong>калливифидриверверсион</strong></span><span class="sxs-lookup"><span data-stu-id="bcd00-335"><strong>CalleeWiFiDriverVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="bcd00-336">int</span><span class="sxs-lookup"><span data-stu-id="bcd00-336">int</span></span></p></td>
<td><p><span data-ttu-id="bcd00-337">Правительства</span><span class="sxs-lookup"><span data-stu-id="bcd00-337">Foreign</span></span></p></td>
<td><p><span data-ttu-id="bcd00-338">Номер версии драйвера Wi-Fi, используемый пользователем, получившим звонок.</span><span class="sxs-lookup"><span data-stu-id="bcd00-338">Version number for the WiFi driver employed by the user who received the call.</span></span></p>
<p><span data-ttu-id="bcd00-339">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bcd00-339">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

