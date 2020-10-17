---
title: 'Lync Server 2013: таблица MediaLine'
description: 'Lync Server 2013: таблица MediaLine.'
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
ms.openlocfilehash: 2acea8e14ba0608d9ebf72a48f888bfc4501fae3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572115"
---
# <a name="medialine-table-in-lync-server-2013"></a><span data-ttu-id="dcbb8-103">Таблица MediaLine в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dcbb8-103">MediaLine table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dcbb8-104">_**Последнее изменение темы:** 2014-02-21_</span><span class="sxs-lookup"><span data-stu-id="dcbb8-104">_**Topic Last Modified:** 2014-02-21_</span></span>

<span data-ttu-id="dcbb8-105">Каждая запись представляет одну линию мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="dcbb8-105">Each record represents one media line.</span></span> <span data-ttu-id="dcbb8-106">(Один звуковой сеанс обычно содержит одну линию звукового носителя).</span><span class="sxs-lookup"><span data-stu-id="dcbb8-106">(One audio session usually contains one audio media line.</span></span> <span data-ttu-id="dcbb8-107">Один сеанс аудио-и видеоданных (A/V) обычно содержит одну линию аудио-и видеоконференций, хотя в этом сеансе могут содержаться две видеолинии, если используется устройство для конференц-связи или если используется представление галереи.</span><span class="sxs-lookup"><span data-stu-id="dcbb8-107">One audio and video (A/V) session usually contains one audio media line and one video media line, although the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dcbb8-108"><strong>Column</strong></span><span class="sxs-lookup"><span data-stu-id="dcbb8-108"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="dcbb8-109"><strong>Тип данных</strong></span><span class="sxs-lookup"><span data-stu-id="dcbb8-109"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="dcbb8-110"><strong>Ключ или индекс</strong></span><span class="sxs-lookup"><span data-stu-id="dcbb8-110"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="dcbb8-111"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="dcbb8-111"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dcbb8-112"><strong>конференцедатетиме</strong></span><span class="sxs-lookup"><span data-stu-id="dcbb8-112"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="dcbb8-113">datetime</span><span class="sxs-lookup"><span data-stu-id="dcbb8-113">datetime</span></span></p></td>
<td><p><span data-ttu-id="dcbb8-114">Primary</span><span class="sxs-lookup"><span data-stu-id="dcbb8-114">Primary</span></span></p></td>
<td><p><span data-ttu-id="dcbb8-115">Ссылка из <a href="lync-server-2013-session-table.md">таблицы Sessions в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="dcbb8-115">Referenced from the <a href="lync-server-2013-session-table.md">Session table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dcbb8-116"><strong>сессионсек</strong></span><span class="sxs-lookup"><span data-stu-id="dcbb8-116"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="dcbb8-117">int</span><span class="sxs-lookup"><span data-stu-id="dcbb8-117">int</span></span></p></td>
<td><p><span data-ttu-id="dcbb8-118">Primary</span><span class="sxs-lookup"><span data-stu-id="dcbb8-118">Primary</span></span></p></td>
<td><p><span data-ttu-id="dcbb8-119">Ссылка из <a href="lync-server-2013-session-table.md">таблицы Sessions в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="dcbb8-119">Referenced from the <a href="lync-server-2013-session-table.md">Session table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dcbb8-120"><strong>медиалинелабел</strong></span><span class="sxs-lookup"><span data-stu-id="dcbb8-120"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="dcbb8-121">tinyint</span><span class="sxs-lookup"><span data-stu-id="dcbb8-121">tinyint</span></span></p></td>
<td><p><span data-ttu-id="dcbb8-122">Primary</span><span class="sxs-lookup"><span data-stu-id="dcbb8-122">Primary</span></span></p></td>
<td><p><span data-ttu-id="dcbb8-123">0 — это основной звук, 1 — основной видеоролик, а 2 — панорамное видео, 3 — общий доступ к приложениям и рабочим столам.</span><span class="sxs-lookup"><span data-stu-id="dcbb8-123">0 is main audio, 1 is main video, and 2 is panoramic video, 3 is Application/Desktop Sharing.</span></span> <span data-ttu-id="dcbb8-124">Эта метка должна быть уникальной в пределах одного сеанса.</span><span class="sxs-lookup"><span data-stu-id="dcbb8-124">This label must be unique within a single session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dcbb8-125"><strong>коннективитице</strong></span><span class="sxs-lookup"><span data-stu-id="dcbb8-125"><strong>ConnectivityIce</strong></span></span></p></td>
<td><p><span data-ttu-id="dcbb8-126">tinyint</span><span class="sxs-lookup"><span data-stu-id="dcbb8-126">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="dcbb8-127">Этот столбец присутствует, но не используется в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="dcbb8-127">This column is present but not used in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="dcbb8-128">Сведения о подключении, используемом для линии мультимедиа, записываются в столбцах Каллерконнективитице и Калликоннективитице.</span><span class="sxs-lookup"><span data-stu-id="dcbb8-128">Information about the connectivity used for a media line is captured in the CallerConnectivityICE and CalleeConnectivityICE columns.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dcbb8-129"><strong>каллерицеварнингфлагс</strong></span><span class="sxs-lookup"><span data-stu-id="dcbb8-129"><strong>CallerIceWarningFlags</strong></span></span></p></td>
<td><p><span data-ttu-id="dcbb8-130">int</span><span class="sxs-lookup"><span data-stu-id="dcbb8-130">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="dcbb8-131">Сведения о процессе интерактивной установки подключения (ICE), описанные в разделе Флаги BITS.</span><span class="sxs-lookup"><span data-stu-id="dcbb8-131">Information about Interactive Connectivity Establishment (ICE) process described in bits flags.</span></span> <span data-ttu-id="dcbb8-132">Дополнительные сведения можно найти в <em>спецификации протокола сервера мониторинга качества взаимодействия</em>, доступной для загрузки.</span><span class="sxs-lookup"><span data-stu-id="dcbb8-132">For details, refer to the <em>Quality of Experience Monitoring Server Protocol Specification</em>, available for download.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dcbb8-133"><strong>каллиицеварнингфлагс</strong></span><span class="sxs-lookup"><span data-stu-id="dcbb8-133"><strong>CalleeIceWarningFlags</strong></span></span></p></td>
<td><p><span data-ttu-id="dcbb8-134">int</span><span class="sxs-lookup"><span data-stu-id="dcbb8-134">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="dcbb8-135">То же, что и Каллерицеварнингфлагс, но на стороне вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="dcbb8-135">Same as CallerIceWarningFlags, but on the callee side.</span></span> <span data-ttu-id="dcbb8-136">Дополнительные сведения можно найти в <em>спецификации протокола сервера мониторинга качества взаимодействия</em>, доступной для загрузки.</span><span class="sxs-lookup"><span data-stu-id="dcbb8-136">For details, refer to the <em>Quality of Experience Monitoring Server Protocol Specification</em>, available for download.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dcbb8-137"><strong>Безопасность</strong></span><span class="sxs-lookup"><span data-stu-id="dcbb8-137"><strong>Security</strong></span></span></p></td>
<td><p><span data-ttu-id="dcbb8-138">tinyint</span><span class="sxs-lookup"><span data-stu-id="dcbb8-138">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="dcbb8-139">Используемый профиль безопасности.</span><span class="sxs-lookup"><span data-stu-id="dcbb8-139">The security profile in use.</span></span> <span data-ttu-id="dcbb8-140">0 – это NONE, 1 – SRTP, 2 – V1.</span><span class="sxs-lookup"><span data-stu-id="dcbb8-140">0 is NONE, 1 is SRTP, 2 is V1.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dcbb8-141"><strong>Transport</strong></span><span class="sxs-lookup"><span data-stu-id="dcbb8-141"><strong>Transport</strong></span></span></p></td>
<td><p><span data-ttu-id="dcbb8-142">tinyint</span><span class="sxs-lookup"><span data-stu-id="dcbb8-142">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="dcbb8-143">0 соответствует протоколу UDP, 1 – протоколу TCP.</span><span class="sxs-lookup"><span data-stu-id="dcbb8-143">0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dcbb8-144"><strong>каллерипаддр</strong></span><span class="sxs-lookup"><span data-stu-id="dcbb8-144"><strong>CallerIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="dcbb8-145">int</span><span class="sxs-lookup"><span data-stu-id="dcbb8-145">int</span></span></p></td>
<td><p><span data-ttu-id="dcbb8-146">Правительства</span><span class="sxs-lookup"><span data-stu-id="dcbb8-146">Foreign</span></span></p></td>
<td><p><span data-ttu-id="dcbb8-147">IP-адрес вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="dcbb8-147">IP Address of the caller.</span></span> <span data-ttu-id="dcbb8-148">Дополнительные сведения см. <a href="lync-server-2013-ipaddress-table.md">в таблице IPAddress в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="dcbb8-148">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dcbb8-149"><strong>каллерпорт</strong></span><span class="sxs-lookup"><span data-stu-id="dcbb8-149"><strong>CallerPort</strong></span></span></p></td>
<td><p><span data-ttu-id="dcbb8-150">int</span><span class="sxs-lookup"><span data-stu-id="dcbb8-150">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="dcbb8-151">Порт, используемый вызывающим абонентом.</span><span class="sxs-lookup"><span data-stu-id="dcbb8-151">Port used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dcbb8-152"><strong>каллерсубнет</strong></span><span class="sxs-lookup"><span data-stu-id="dcbb8-152"><strong>CallerSubnet</strong></span></span></p></td>
<td><p><span data-ttu-id="dcbb8-153">int</span><span class="sxs-lookup"><span data-stu-id="dcbb8-153">int</span></span></p></td>
<td><p><span data-ttu-id="dcbb8-154"> Правительства</span><span class="sxs-lookup"><span data-stu-id="dcbb8-154"> Foreign</span></span></p></td>
<td><p><span data-ttu-id="dcbb8-155">Подсеть вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="dcbb8-155">The subnet of the caller.</span></span> <span data-ttu-id="dcbb8-156">Дополнительные сведения см. <a href="lync-server-2013-ipaddress-table.md">в таблице IPAddress в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="dcbb8-156">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dcbb8-157"><strong>каллеринсиде</strong></span><span class="sxs-lookup"><span data-stu-id="dcbb8-157"><strong>CallerInside</strong></span></span></p></td>
<td><p><span data-ttu-id="dcbb8-158">Битовая</span><span class="sxs-lookup"><span data-stu-id="dcbb8-158">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="dcbb8-159">1 означает, что вызывающий абонент находится внутри корпоративной сети, 0 означает, что вызывающий абонент находится за пределами сети.</span><span class="sxs-lookup"><span data-stu-id="dcbb8-159">1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dcbb8-160"><strong>каллермакаддресс</strong></span><span class="sxs-lookup"><span data-stu-id="dcbb8-160"><strong>CallerMacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="dcbb8-161">int</span><span class="sxs-lookup"><span data-stu-id="dcbb8-161">int</span></span></p></td>
<td><p><span data-ttu-id="dcbb8-162">Правительства</span><span class="sxs-lookup"><span data-stu-id="dcbb8-162">Foreign</span></span></p></td>
<td><p><span data-ttu-id="dcbb8-163">Mac-адрес вызывающего абонента, на который ссылается <a href="lync-server-2013-macaddress-table.md">Таблица MacAddress в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="dcbb8-163">Caller’s mac address, referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dcbb8-164"><strong>каллеррелайипаддр</strong></span><span class="sxs-lookup"><span data-stu-id="dcbb8-164"><strong>CallerRelayIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="dcbb8-165">int</span><span class="sxs-lookup"><span data-stu-id="dcbb8-165">int</span></span></p></td>
<td><p><span data-ttu-id="dcbb8-166">Правительства</span><span class="sxs-lookup"><span data-stu-id="dcbb8-166">Foreign</span></span></p></td>
<td><p><span data-ttu-id="dcbb8-167">IP-адрес пограничной службы Lync Server A/V, используемой вызывающим абонентом.</span><span class="sxs-lookup"><span data-stu-id="dcbb8-167">IP Address of the Lync Server A/V Edge service used by the caller.</span></span> <span data-ttu-id="dcbb8-168">Дополнительные сведения см. <a href="lync-server-2013-ipaddress-table.md">в таблице IPAddress в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="dcbb8-168">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dcbb8-169"><strong>каллеррелайпорт</strong></span><span class="sxs-lookup"><span data-stu-id="dcbb8-169"><strong>CallerRelayPort</strong></span></span></p></td>
<td><p><span data-ttu-id="dcbb8-170">int</span><span class="sxs-lookup"><span data-stu-id="dcbb8-170">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="dcbb8-171">Порт, используемый вызывающим абонентом для пограничной службы аудио-и видеоданных.</span><span class="sxs-lookup"><span data-stu-id="dcbb8-171">Port used on the A/V Edge service by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dcbb8-172"><strong>каллеркаптуредев</strong></span><span class="sxs-lookup"><span data-stu-id="dcbb8-172"><strong>CallerCaptureDev</strong></span></span></p></td>
<td><p><span data-ttu-id="dcbb8-173">int</span><span class="sxs-lookup"><span data-stu-id="dcbb8-173">int</span></span></p></td>
<td><p><span data-ttu-id="dcbb8-174">Правительства</span><span class="sxs-lookup"><span data-stu-id="dcbb8-174">Foreign</span></span></p></td>
<td><p><span data-ttu-id="dcbb8-175">Устройство захвата, используемое вызывающим абонентом.</span><span class="sxs-lookup"><span data-stu-id="dcbb8-175">Capture device used by the caller.</span></span> <span data-ttu-id="dcbb8-176">Ссылка из <a href="lync-server-2013-device-table.md">таблицы устройств в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="dcbb8-176">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dcbb8-177"><strong>каллеррендердев</strong></span><span class="sxs-lookup"><span data-stu-id="dcbb8-177"><strong>CallerRenderDev</strong></span></span></p></td>
<td><p><span data-ttu-id="dcbb8-178">int</span><span class="sxs-lookup"><span data-stu-id="dcbb8-178">int</span></span></p></td>
<td><p><span data-ttu-id="dcbb8-179">Правительства</span><span class="sxs-lookup"><span data-stu-id="dcbb8-179">Foreign</span></span></p></td>
<td><p><span data-ttu-id="dcbb8-180">Устройство отображения, используемое вызывающим абонентом.</span><span class="sxs-lookup"><span data-stu-id="dcbb8-180">Render device used by caller.</span></span> <span data-ttu-id="dcbb8-181">Ссылка из <a href="lync-server-2013-device-table.md">таблицы устройств в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="dcbb8-181">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dcbb8-182"><strong>каллеркаптуредевдривер</strong></span><span class="sxs-lookup"><span data-stu-id="dcbb8-182"><strong>CallerCaptureDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="dcbb8-183">int</span><span class="sxs-lookup"><span data-stu-id="dcbb8-183">int</span></span></p></td>
<td><p><span data-ttu-id="dcbb8-184">Правительства</span><span class="sxs-lookup"><span data-stu-id="dcbb8-184">Foreign</span></span></p></td>
<td><p><span data-ttu-id="dcbb8-185">Драйвер устройства захвата вызывающего абонента, на который ссылается <a href="lync-server-2013-devicedriver-table.md">таблица таблица devicedriver в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="dcbb8-185">Driver for the caller’s capture device, referenced from the <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dcbb8-186"><strong>каллеррендердевдривер</strong></span><span class="sxs-lookup"><span data-stu-id="dcbb8-186"><strong>CallerRenderDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="dcbb8-187">int</span><span class="sxs-lookup"><span data-stu-id="dcbb8-187">int</span></span></p></td>
<td><p><span data-ttu-id="dcbb8-188">Правительства</span><span class="sxs-lookup"><span data-stu-id="dcbb8-188">Foreign</span></span></p></td>
<td><p><span data-ttu-id="dcbb8-189">Драйвер для устройства отрисовки вызывающего абонента, на который ссылается <a href="lync-server-2013-devicedriver-table.md">таблица таблица devicedriver в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="dcbb8-189">Driver for the caller’s render device, referenced from the <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dcbb8-190"><strong>каллернетворкконнектионтипе</strong></span><span class="sxs-lookup"><span data-stu-id="dcbb8-190"><strong>CallerNetworkConnectionType</strong></span></span></p></td>
<td><p><span data-ttu-id="dcbb8-191">tinyint</span><span class="sxs-lookup"><span data-stu-id="dcbb8-191">tinyint</span></span></p></td>
<td><p><span data-ttu-id="dcbb8-192">Правительства</span><span class="sxs-lookup"><span data-stu-id="dcbb8-192">Foreign</span></span></p></td>
<td><p><span data-ttu-id="dcbb8-193">Показывает, как вызывающий абонент подключился к сети.</span><span class="sxs-lookup"><span data-stu-id="dcbb8-193">Indicates how the caller connected to the network.</span></span> <span data-ttu-id="dcbb8-194">Значения берутся из <a href="lync-server-2013-networkconnectiondetail-table.md">таблицы нетворкконнектиондетаил в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="dcbb8-194">Values are obtained from the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a>.</span></span> <span data-ttu-id="dcbb8-195">Типичные значения: 0 для проводного подключения 1 для подключения WiFi; и 3 для подключения Ethernet.</span><span class="sxs-lookup"><span data-stu-id="dcbb8-195">Typical values are 0 for a wired connection’ 1 for a WiFi connection; and 3 for an Ethernet connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dcbb8-196"><strong>каллербссид</strong></span><span class="sxs-lookup"><span data-stu-id="dcbb8-196"><strong>CallerBssid</strong></span></span></p></td>
<td><p><span data-ttu-id="dcbb8-197">int</span><span class="sxs-lookup"><span data-stu-id="dcbb8-197">int</span></span></p></td>
<td><p><span data-ttu-id="dcbb8-198">Правительства</span><span class="sxs-lookup"><span data-stu-id="dcbb8-198">Foreign</span></span></p></td>
<td><p><span data-ttu-id="dcbb8-199">BSSID для вызывающего абонента при использовании беспроводной связи.</span><span class="sxs-lookup"><span data-stu-id="dcbb8-199">Caller’s BSSID if wireless is used.</span></span> <span data-ttu-id="dcbb8-200">Ссылка из <a href="lync-server-2013-macaddress-table.md">таблицы MacAddress в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="dcbb8-200">Referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dcbb8-201"><strong>каллервпн</strong></span><span class="sxs-lookup"><span data-stu-id="dcbb8-201"><strong>CallerVPN</strong></span></span></p></td>
<td><p><span data-ttu-id="dcbb8-202">Битовая</span><span class="sxs-lookup"><span data-stu-id="dcbb8-202">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dcbb8-203">Ссылка вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="dcbb8-203">The caller's link.</span></span> <span data-ttu-id="dcbb8-204">1 – подключен к виртуальной частной сети, 0 – не подключен к виртуальной частной сети.</span><span class="sxs-lookup"><span data-stu-id="dcbb8-204">1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dcbb8-205"><strong>каллерлинкспид</strong></span><span class="sxs-lookup"><span data-stu-id="dcbb8-205"><strong>CallerLinkSpeed</strong></span></span></p></td>
<td><p><span data-ttu-id="dcbb8-206">десятичное число (18, 0)</span><span class="sxs-lookup"><span data-stu-id="dcbb8-206">decimal(18,0)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dcbb8-207">Скорость сетевого соединения в бит/с для конечной точки вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="dcbb8-207">The network link speed, in bps, for the caller's endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dcbb8-208"><strong>каллиипаддр</strong></span><span class="sxs-lookup"><span data-stu-id="dcbb8-208"><strong>CalleeIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="dcbb8-209">int</span><span class="sxs-lookup"><span data-stu-id="dcbb8-209">int</span></span></p></td>
<td><p><span data-ttu-id="dcbb8-210">Правительства</span><span class="sxs-lookup"><span data-stu-id="dcbb8-210">Foreign</span></span></p></td>
<td><p><span data-ttu-id="dcbb8-211">IP-адрес приемника вызовов.</span><span class="sxs-lookup"><span data-stu-id="dcbb8-211">IP Address of the call receiver.</span></span> <span data-ttu-id="dcbb8-212">Дополнительные сведения см. <a href="lync-server-2013-ipaddress-table.md">в таблице IPAddress в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="dcbb8-212">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dcbb8-213"><strong>каллипорт</strong></span><span class="sxs-lookup"><span data-stu-id="dcbb8-213"><strong>CalleePort</strong></span></span></p></td>
<td><p><span data-ttu-id="dcbb8-214">Битовая</span><span class="sxs-lookup"><span data-stu-id="dcbb8-214">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dcbb8-215">Порт, используемый приемником вызовов.</span><span class="sxs-lookup"><span data-stu-id="dcbb8-215">Port used by the call receiver.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dcbb8-216"><strong>каллисубнет</strong></span><span class="sxs-lookup"><span data-stu-id="dcbb8-216"><strong>CalleeSubnet</strong></span></span></p></td>
<td><p><span data-ttu-id="dcbb8-217">int</span><span class="sxs-lookup"><span data-stu-id="dcbb8-217">int</span></span></p></td>
<td><p><span data-ttu-id="dcbb8-218">Правительства</span><span class="sxs-lookup"><span data-stu-id="dcbb8-218">Foreign</span></span></p></td>
<td><p><span data-ttu-id="dcbb8-219">Подсеть вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="dcbb8-219">Subnet of callee.</span></span> <span data-ttu-id="dcbb8-220">Дополнительные сведения см. <a href="lync-server-2013-ipaddress-table.md">в таблице IPAddress в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="dcbb8-220">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dcbb8-221"><strong>каллиинсиде</strong></span><span class="sxs-lookup"><span data-stu-id="dcbb8-221"><strong>CalleeInside</strong></span></span></p></td>
<td><p><span data-ttu-id="dcbb8-222">Битовая</span><span class="sxs-lookup"><span data-stu-id="dcbb8-222">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="dcbb8-223">1 означает, что получатель вызова находится внутри корпоративной сети, 0 означает, что приемник вызовов находится за пределами сети.</span><span class="sxs-lookup"><span data-stu-id="dcbb8-223">1 means call receiver is inside the enterprise network, 0 means the call receiver is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dcbb8-224"><strong>каллимакаддресс</strong></span><span class="sxs-lookup"><span data-stu-id="dcbb8-224"><strong>CalleeMacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="dcbb8-225">int</span><span class="sxs-lookup"><span data-stu-id="dcbb8-225">int</span></span></p></td>
<td><p><span data-ttu-id="dcbb8-226">Правительства</span><span class="sxs-lookup"><span data-stu-id="dcbb8-226">Foreign</span></span></p></td>
<td><p><span data-ttu-id="dcbb8-227">Mac-адрес вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="dcbb8-227">Callee Mac address.</span></span> <span data-ttu-id="dcbb8-228">Ссылка из <a href="lync-server-2013-macaddress-table.md">таблицы MacAddress в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="dcbb8-228">Referenced from the <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dcbb8-229"><strong>каллирелайипаддр</strong></span><span class="sxs-lookup"><span data-stu-id="dcbb8-229"><strong>CalleeRelayIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="dcbb8-230">int</span><span class="sxs-lookup"><span data-stu-id="dcbb8-230">int</span></span></p></td>
<td><p><span data-ttu-id="dcbb8-231">Правительства</span><span class="sxs-lookup"><span data-stu-id="dcbb8-231">Foreign</span></span></p></td>
<td><p><span data-ttu-id="dcbb8-232">IP-адрес пограничной службы аудио-и видеоданных, используемой приемником вызовов.</span><span class="sxs-lookup"><span data-stu-id="dcbb8-232">IP Address of the A/V Edge service used by the call receiver.</span></span> <span data-ttu-id="dcbb8-233">Дополнительные сведения см. <a href="lync-server-2013-ipaddress-table.md">в таблице IPAddress в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="dcbb8-233">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dcbb8-234"><strong>каллирелайпорт</strong></span><span class="sxs-lookup"><span data-stu-id="dcbb8-234"><strong>CalleeRelayPort</strong></span></span></p></td>
<td><p><span data-ttu-id="dcbb8-235">int</span><span class="sxs-lookup"><span data-stu-id="dcbb8-235">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="dcbb8-236">Порт, используемый приемником вызовов для пограничной службы аудио-и видеоданных.</span><span class="sxs-lookup"><span data-stu-id="dcbb8-236">Port used on the A/V Edge Service by the call receiver.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dcbb8-237"><strong>калликаптуредев</strong></span><span class="sxs-lookup"><span data-stu-id="dcbb8-237"><strong>CalleeCaptureDev</strong></span></span></p></td>
<td><p><span data-ttu-id="dcbb8-238">int</span><span class="sxs-lookup"><span data-stu-id="dcbb8-238">int</span></span></p></td>
<td><p><span data-ttu-id="dcbb8-239">правительства</span><span class="sxs-lookup"><span data-stu-id="dcbb8-239">foreign</span></span></p></td>
<td><p><span data-ttu-id="dcbb8-240">Устройство захвата, используемое приемником вызовов.</span><span class="sxs-lookup"><span data-stu-id="dcbb8-240">Capture device used by the call receiver.</span></span> <span data-ttu-id="dcbb8-241">Ссылка из <a href="lync-server-2013-device-table.md">таблицы устройств в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="dcbb8-241">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dcbb8-242"><strong>каллирендердев</strong></span><span class="sxs-lookup"><span data-stu-id="dcbb8-242"><strong>CalleeRenderDev</strong></span></span></p></td>
<td><p><span data-ttu-id="dcbb8-243">int</span><span class="sxs-lookup"><span data-stu-id="dcbb8-243">int</span></span></p></td>
<td><p><span data-ttu-id="dcbb8-244">Правительства</span><span class="sxs-lookup"><span data-stu-id="dcbb8-244">Foreign</span></span></p></td>
<td><p><span data-ttu-id="dcbb8-245">Устройство отображения, используемое приемником вызовов.</span><span class="sxs-lookup"><span data-stu-id="dcbb8-245">Render device used by the call receiver.</span></span> <span data-ttu-id="dcbb8-246">Ссылка из <a href="lync-server-2013-device-table.md">таблицы устройств в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="dcbb8-246">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dcbb8-247"><strong>калликаптуредевдривер</strong></span><span class="sxs-lookup"><span data-stu-id="dcbb8-247"><strong>CalleeCaptureDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="dcbb8-248">int</span><span class="sxs-lookup"><span data-stu-id="dcbb8-248">int</span></span></p></td>
<td><p><span data-ttu-id="dcbb8-249">Правительства</span><span class="sxs-lookup"><span data-stu-id="dcbb8-249">Foreign</span></span></p></td>
<td><p><span data-ttu-id="dcbb8-250">Драйвер устройства захвата приемника вызовов.</span><span class="sxs-lookup"><span data-stu-id="dcbb8-250">Driver for the call receiver’s capture device.</span></span> <span data-ttu-id="dcbb8-251">Ссылка из <a href="lync-server-2013-devicedriver-table.md">таблицы таблица devicedriver в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="dcbb8-251">Referenced from <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dcbb8-252"><strong>каллирендердевдривер</strong></span><span class="sxs-lookup"><span data-stu-id="dcbb8-252"><strong>CalleeRenderDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="dcbb8-253">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="dcbb8-253">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="dcbb8-254">Правительства</span><span class="sxs-lookup"><span data-stu-id="dcbb8-254">Foreign</span></span></p></td>
<td><p><span data-ttu-id="dcbb8-255">Драйвер устройства обработки для приемника вызовов.</span><span class="sxs-lookup"><span data-stu-id="dcbb8-255">Driver for the call receiver’s render device.</span></span> <span data-ttu-id="dcbb8-256">Ссылка из <a href="lync-server-2013-devicedriver-table.md">таблицы таблица devicedriver в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="dcbb8-256">Referenced from <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dcbb8-257"><strong>каллинетворкконнектионтипе</strong></span><span class="sxs-lookup"><span data-stu-id="dcbb8-257"><strong>CalleeNetworkConnectionType</strong></span></span></p></td>
<td><p><span data-ttu-id="dcbb8-258">tinyint</span><span class="sxs-lookup"><span data-stu-id="dcbb8-258">tinyint</span></span></p></td>
<td><p><span data-ttu-id="dcbb8-259">Правительства</span><span class="sxs-lookup"><span data-stu-id="dcbb8-259">Foreign</span></span></p></td>
<td><p><span data-ttu-id="dcbb8-260">Показывает, как вызываемый абонент подключился к сети.</span><span class="sxs-lookup"><span data-stu-id="dcbb8-260">Indicates how the callee connected to the network.</span></span> <span data-ttu-id="dcbb8-261">Значения берутся из <a href="lync-server-2013-networkconnectiondetail-table.md">таблицы нетворкконнектиондетаил в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="dcbb8-261">Values are obtained from the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a>.</span></span> <span data-ttu-id="dcbb8-262">Типичные значения: 0 для проводного подключения 1 для подключения WiFi; и 3 для подключения Ethernet.</span><span class="sxs-lookup"><span data-stu-id="dcbb8-262">Typical values are 0 for a wired connection’ 1 for a WiFi connection; and 3 for an Ethernet connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dcbb8-263"><strong>каллибссид</strong></span><span class="sxs-lookup"><span data-stu-id="dcbb8-263"><strong>CalleeBssid</strong></span></span></p></td>
<td><p><span data-ttu-id="dcbb8-264">int</span><span class="sxs-lookup"><span data-stu-id="dcbb8-264">int</span></span></p></td>
<td><p><span data-ttu-id="dcbb8-265">Правительства</span><span class="sxs-lookup"><span data-stu-id="dcbb8-265">Foreign</span></span></p></td>
<td><p><span data-ttu-id="dcbb8-266">BSSID для вызываемого абонента, если используется беспроводной доступ.</span><span class="sxs-lookup"><span data-stu-id="dcbb8-266">Callee’s BSSID if wireless is used.</span></span> <span data-ttu-id="dcbb8-267">Ссылка из <a href="lync-server-2013-macaddress-table.md">таблицы MacAddress в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="dcbb8-267">Referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dcbb8-268"><strong>калливпн</strong></span><span class="sxs-lookup"><span data-stu-id="dcbb8-268"><strong>CalleeVPN</strong></span></span></p></td>
<td><p><span data-ttu-id="dcbb8-269">Битовая</span><span class="sxs-lookup"><span data-stu-id="dcbb8-269">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="dcbb8-270">Ссылка приемника вызовов; 1 — это виртуальная частная сеть (VPN), 0 — не VPN.</span><span class="sxs-lookup"><span data-stu-id="dcbb8-270">The call receiver’s link; 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dcbb8-271"><strong>каллилинкспид</strong></span><span class="sxs-lookup"><span data-stu-id="dcbb8-271"><strong>CalleeLinkSpeed</strong></span></span></p></td>
<td><p><span data-ttu-id="dcbb8-272">десятичное число (18, 0)</span><span class="sxs-lookup"><span data-stu-id="dcbb8-272">decimal(18,0)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="dcbb8-273">Скорость сетевого соединения в бит/с для конечной точки приемника вызовов.</span><span class="sxs-lookup"><span data-stu-id="dcbb8-273">The network link speed, in bps, for the call receiver’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dcbb8-274"><strong>конверсатионалмос</strong></span><span class="sxs-lookup"><span data-stu-id="dcbb8-274"><strong>ConversationalMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="dcbb8-275">десятичное число (3, 2)</span><span class="sxs-lookup"><span data-stu-id="dcbb8-275">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="dcbb8-276">Узкополосный MOS аудиосеансов (на основе обоих аудиопотоков).</span><span class="sxs-lookup"><span data-stu-id="dcbb8-276">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dcbb8-277"><strong>апплиедбандвидслимит</strong></span><span class="sxs-lookup"><span data-stu-id="dcbb8-277"><strong>AppliedBandwidthLimit</strong></span></span></p></td>
<td><p><span data-ttu-id="dcbb8-278">int</span><span class="sxs-lookup"><span data-stu-id="dcbb8-278">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dcbb8-279">Это фактическая пропускная способность, примененная к потоку отправки на стороне, в которой задаются различные параметры политики (TURN, API, SDP, сервер политики и т. д.).</span><span class="sxs-lookup"><span data-stu-id="dcbb8-279">This is the actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on).</span></span> <span data-ttu-id="dcbb8-280">Ее не следует путать с эффективной пропускной способностью, потому что эффективная пропускная способность может быть меньше в зависимости от оценки пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="dcbb8-280">This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate.</span></span> <span data-ttu-id="dcbb8-281">По сути это в основном максимальная пропускная способность потока отправителя с учетом ограничений, наложенных оценкой пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="dcbb8-281">This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dcbb8-282"><strong>апплиедбандвидссаурцекэй</strong></span><span class="sxs-lookup"><span data-stu-id="dcbb8-282"><strong>AppliedBandwidthSourceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="dcbb8-283">smallint</span><span class="sxs-lookup"><span data-stu-id="dcbb8-283">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dcbb8-284">Источник применяемого ограничения пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="dcbb8-284">This is the source of the bandwidth cap being imposed.</span></span> <span data-ttu-id="dcbb8-285">В нем описывается, откуда поступает предельный объем пропускной способности ("сервер политики", "превратить сервер", "модальность" и т. д.).</span><span class="sxs-lookup"><span data-stu-id="dcbb8-285">It describes where the bandwidth limit is coming from (“Policy Server”, “TURN Server”, “Modality”, and so on).</span></span> <span data-ttu-id="dcbb8-286">Ссылка из <a href="lync-server-2013-appliedbandwidthsource-table.md">таблицы таблица appliedbandwidthsource в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="dcbb8-286">Referenced from the <a href="lync-server-2013-appliedbandwidthsource-table.md">AppliedBandwidthSource table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dcbb8-287"><strong>Caller</strong></span><span class="sxs-lookup"><span data-stu-id="dcbb8-287"><strong>Caller</strong></span></span></p></td>
<td><p><span data-ttu-id="dcbb8-288">Битовая</span><span class="sxs-lookup"><span data-stu-id="dcbb8-288">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="dcbb8-289">Указывает, были ли получены метрики от вызывающего абонента; 1 — значение "Да", NULL — нет.</span><span class="sxs-lookup"><span data-stu-id="dcbb8-289">Indicates whether metrics from the caller were received; 1 is yes, a null value is no.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dcbb8-290"><strong>Вызываемого абонента</strong></span><span class="sxs-lookup"><span data-stu-id="dcbb8-290"><strong>Callee</strong></span></span></p></td>
<td><p><span data-ttu-id="dcbb8-291">Битовая</span><span class="sxs-lookup"><span data-stu-id="dcbb8-291">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="dcbb8-292">Указывает, были ли получены метрики от приемника вызовов; 1 — значение "Да", NULL — нет.</span><span class="sxs-lookup"><span data-stu-id="dcbb8-292">Indicates whether metrics from the call receiver were received; 1 is yes, a null value is no.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dcbb8-293"><strong>мидкаллрепорт</strong></span><span class="sxs-lookup"><span data-stu-id="dcbb8-293"><strong>MidCallReport</strong></span></span></p></td>
<td><p><span data-ttu-id="dcbb8-294">Битовая</span><span class="sxs-lookup"><span data-stu-id="dcbb8-294">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dcbb8-295">Указывает, относится ли отчет к части сеанса или к полному сеансу.</span><span class="sxs-lookup"><span data-stu-id="dcbb8-295">Indicates whether the report is for a portion of the session or for the complete session.</span></span></p>
<p><span data-ttu-id="dcbb8-296">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="dcbb8-296">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dcbb8-297"><strong>классифиедпуркалл</strong></span><span class="sxs-lookup"><span data-stu-id="dcbb8-297"><strong>ClassifiedPoorCall</strong></span></span></p></td>
<td><p><span data-ttu-id="dcbb8-298">Битовая</span><span class="sxs-lookup"><span data-stu-id="dcbb8-298">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dcbb8-299">Указывает, был ли вызов классифицирован как плохой вызов (значение 1) или как хороший вызов (0).</span><span class="sxs-lookup"><span data-stu-id="dcbb8-299">Indicates whether a call was classified as a poor call (value of 1) or as a good call (0).</span></span></p>
<p><span data-ttu-id="dcbb8-300">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="dcbb8-300">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dcbb8-301"><strong>каллерконнективитице</strong></span><span class="sxs-lookup"><span data-stu-id="dcbb8-301"><strong>CallerConnectivityICE</strong></span></span></p></td>
<td><p><span data-ttu-id="dcbb8-302">tinyInt</span><span class="sxs-lookup"><span data-stu-id="dcbb8-302">tinyInt</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dcbb8-303">Указывает, подключен ли абонент к сети через протокол ICE (Internet Connectivity Establishment).</span><span class="sxs-lookup"><span data-stu-id="dcbb8-303">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p>
<p><span data-ttu-id="dcbb8-304">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="dcbb8-304">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dcbb8-305"><strong>калликоннективитице</strong></span><span class="sxs-lookup"><span data-stu-id="dcbb8-305"><strong>CalleeConnectivityICE</strong></span></span></p></td>
<td><p><span data-ttu-id="dcbb8-306">tinyint</span><span class="sxs-lookup"><span data-stu-id="dcbb8-306">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dcbb8-307">Указывает, подключен ли абонент к сети через протокол ICE (Internet Connectivity Establishment).</span><span class="sxs-lookup"><span data-stu-id="dcbb8-307">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p>
<p><span data-ttu-id="dcbb8-308">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="dcbb8-308">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dcbb8-309"><strong>каллеррефлексивелокалипаддр</strong></span><span class="sxs-lookup"><span data-stu-id="dcbb8-309"><strong>CallerReflexiveLocalIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="dcbb8-310">int</span><span class="sxs-lookup"><span data-stu-id="dcbb8-310">int</span></span></p></td>
<td><p><span data-ttu-id="dcbb8-311">Правительства</span><span class="sxs-lookup"><span data-stu-id="dcbb8-311">Foreign</span></span></p></td>
<td><p><span data-ttu-id="dcbb8-312">IP-адрес пользователя, который поместил вызов.</span><span class="sxs-lookup"><span data-stu-id="dcbb8-312">Reflexive IP address of the user who placed the call.</span></span> <span data-ttu-id="dcbb8-313">В организациях, использующих NAT (преобразование сетевых адресов), это IP-адрес прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="dcbb8-313">In organizations that use NAT (network address translation), the reflexive IP address is the IP address of the proxy server.</span></span></p>
<p><span data-ttu-id="dcbb8-314">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="dcbb8-314">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dcbb8-315"><strong>каллервифидривердевицесдеск</strong></span><span class="sxs-lookup"><span data-stu-id="dcbb8-315"><strong>CallerWiFiDriverDevicesDesc</strong></span></span></p></td>
<td><p><span data-ttu-id="dcbb8-316">int</span><span class="sxs-lookup"><span data-stu-id="dcbb8-316">int</span></span></p></td>
<td><p><span data-ttu-id="dcbb8-317">Правительства</span><span class="sxs-lookup"><span data-stu-id="dcbb8-317">Foreign</span></span></p></td>
<td><p><span data-ttu-id="dcbb8-318">Описание устройства для драйвера Wi-Fi, используемого пользователем, который поместил звонок.</span><span class="sxs-lookup"><span data-stu-id="dcbb8-318">Device description for the WiFi driver employed by the user who placed the call.</span></span></p>
<p><span data-ttu-id="dcbb8-319">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="dcbb8-319">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dcbb8-320"><strong>каллервифидриверверсион</strong></span><span class="sxs-lookup"><span data-stu-id="dcbb8-320"><strong>CallerWiFiDriverVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="dcbb8-321">int</span><span class="sxs-lookup"><span data-stu-id="dcbb8-321">int</span></span></p></td>
<td><p><span data-ttu-id="dcbb8-322">Правительства</span><span class="sxs-lookup"><span data-stu-id="dcbb8-322">Foreign</span></span></p></td>
<td><p><span data-ttu-id="dcbb8-323">Номер версии драйвера Wi-Fi, используемый пользователем, который поместил звонок.</span><span class="sxs-lookup"><span data-stu-id="dcbb8-323">Version number for the WiFi driver employed by the user who placed the call.</span></span></p>
<p><span data-ttu-id="dcbb8-324">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="dcbb8-324">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dcbb8-325"><strong>каллерефлексивелокалипаддр</strong></span><span class="sxs-lookup"><span data-stu-id="dcbb8-325"><strong>CalleReflexiveLocalIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="dcbb8-326">int</span><span class="sxs-lookup"><span data-stu-id="dcbb8-326">int</span></span></p></td>
<td><p><span data-ttu-id="dcbb8-327">Правительства</span><span class="sxs-lookup"><span data-stu-id="dcbb8-327">Foreign</span></span></p></td>
<td><p><span data-ttu-id="dcbb8-328">IP-адрес пользователя, который получил вызов.</span><span class="sxs-lookup"><span data-stu-id="dcbb8-328">Reflexive IP address of the user who received the call.</span></span> <span data-ttu-id="dcbb8-329">В организациях, использующих NAT (преобразование сетевых адресов), это IP-адрес прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="dcbb8-329">In organizations that use NAT (network address translation), the reflexive IP address is the IP address of the proxy server.</span></span></p>
<p><span data-ttu-id="dcbb8-330">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="dcbb8-330">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dcbb8-331"><strong>калливифидривердевицесдеск</strong></span><span class="sxs-lookup"><span data-stu-id="dcbb8-331"><strong>CalleeWiFiDriverDevicesDesc</strong></span></span></p></td>
<td><p><span data-ttu-id="dcbb8-332">int</span><span class="sxs-lookup"><span data-stu-id="dcbb8-332">int</span></span></p></td>
<td><p><span data-ttu-id="dcbb8-333">Правительства</span><span class="sxs-lookup"><span data-stu-id="dcbb8-333">Foreign</span></span></p></td>
<td><p><span data-ttu-id="dcbb8-334">Описание устройства для драйвера Wi-Fi, используемого пользователем, который получил вызов.</span><span class="sxs-lookup"><span data-stu-id="dcbb8-334">Device description for the WiFi driver employed by the user who received the call.</span></span></p>
<p><span data-ttu-id="dcbb8-335">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="dcbb8-335">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dcbb8-336"><strong>калливифидриверверсион</strong></span><span class="sxs-lookup"><span data-stu-id="dcbb8-336"><strong>CalleeWiFiDriverVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="dcbb8-337">int</span><span class="sxs-lookup"><span data-stu-id="dcbb8-337">int</span></span></p></td>
<td><p><span data-ttu-id="dcbb8-338">Правительства</span><span class="sxs-lookup"><span data-stu-id="dcbb8-338">Foreign</span></span></p></td>
<td><p><span data-ttu-id="dcbb8-339">Номер версии драйвера Wi-Fi, используемый пользователем, получившим звонок.</span><span class="sxs-lookup"><span data-stu-id="dcbb8-339">Version number for the WiFi driver employed by the user who received the call.</span></span></p>
<p><span data-ttu-id="dcbb8-340">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="dcbb8-340">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

