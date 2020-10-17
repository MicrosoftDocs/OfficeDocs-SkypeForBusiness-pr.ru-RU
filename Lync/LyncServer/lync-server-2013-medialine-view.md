---
title: 'Lync Server 2013: представление MediaLine'
description: 'Lync Server 2013: представление MediaLine.'
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
ms.openlocfilehash: 4c61fcc15b46958622e6cddd66427255a6def154
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568685"
---
# <a name="medialine-view-in-lync-server-2013"></a><span data-ttu-id="e0549-103">Представление MediaLine в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e0549-103">MediaLine view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e0549-104">_**Последнее изменение темы:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="e0549-104">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="e0549-105">В представлении MediaLine хранятся сведения о каждой строке мультимедиа в базе данных.</span><span class="sxs-lookup"><span data-stu-id="e0549-105">The MediaLine View stores information about each media line in the database.</span></span> <span data-ttu-id="e0549-106">Один звуковой сеанс обычно содержит одну линию звукового носителя.</span><span class="sxs-lookup"><span data-stu-id="e0549-106">One audio session typically contains one audio media line.</span></span> <span data-ttu-id="e0549-107">Один сеанс аудио-и видеоданных (A/V) обычно содержит одну линию аудио-и видеоконференций; Однако в этом сеансе могут содержаться две видеолинии, если используется устройство конференц-связи или если используется представление галереи.</span><span class="sxs-lookup"><span data-stu-id="e0549-107">One audio and video (A/V) session typically contains one audio media line and one video media line; however, the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span> <span data-ttu-id="e0549-108">Это представление было представлено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e0549-108">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e0549-109">Столбец</span><span class="sxs-lookup"><span data-stu-id="e0549-109">Column</span></span></th>
<th><span data-ttu-id="e0549-110">Тип данных</span><span class="sxs-lookup"><span data-stu-id="e0549-110">Data Type</span></span></th>
<th><span data-ttu-id="e0549-111">details</span><span class="sxs-lookup"><span data-stu-id="e0549-111">details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e0549-112">конференцедатетиме</span><span class="sxs-lookup"><span data-stu-id="e0549-112">ConferenceDateTime</span></span></p></td>
<td><p><span data-ttu-id="e0549-113">datetime</span><span class="sxs-lookup"><span data-stu-id="e0549-113">datetime</span></span></p></td>
<td><p><span data-ttu-id="e0549-114">Ссылка из <a href="lync-server-2013-medialine-table.md">таблицы MediaLine в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="e0549-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0549-115">сессионсек</span><span class="sxs-lookup"><span data-stu-id="e0549-115">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="e0549-116">int</span><span class="sxs-lookup"><span data-stu-id="e0549-116">int</span></span></p></td>
<td><p><span data-ttu-id="e0549-117">Ссылка из <a href="lync-server-2013-medialine-table.md">таблицы MediaLine в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="e0549-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0549-118">медиалинелабел</span><span class="sxs-lookup"><span data-stu-id="e0549-118">MediaLineLabel</span></span></p></td>
<td><p><span data-ttu-id="e0549-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="e0549-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="e0549-120">Ссылка из <a href="lync-server-2013-medialine-table.md">таблицы MediaLine в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="e0549-120">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0549-121">каллерицеварнингфлагс</span><span class="sxs-lookup"><span data-stu-id="e0549-121">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="e0549-122">int</span><span class="sxs-lookup"><span data-stu-id="e0549-122">int</span></span></p></td>
<td><p><span data-ttu-id="e0549-p102">Сведения о технологии ICE (Interactive Connectivity Establishment), описанные в битовых флагах, для вызывающего абонента. Дополнительные сведения см. в спецификации протокола сервера мониторинга качества взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="e0549-p102">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0549-125">каллиицеварнингфлагс</span><span class="sxs-lookup"><span data-stu-id="e0549-125">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="e0549-126">int</span><span class="sxs-lookup"><span data-stu-id="e0549-126">int</span></span></p></td>
<td><p><span data-ttu-id="e0549-p103">Сведения о процессе установки интерактивной связи, описываемые во флажках разрядов для вызываемого абонента. Подробности см. в спецификации протокола сервера мониторинга качества взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="e0549-p103">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0549-129">Безопасность</span><span class="sxs-lookup"><span data-stu-id="e0549-129">Security</span></span></p></td>
<td><p><span data-ttu-id="e0549-130">tinyint</span><span class="sxs-lookup"><span data-stu-id="e0549-130">tinyint</span></span></p></td>
<td><p><span data-ttu-id="e0549-p104">Используемый профиль безопасности. 0 – это NONE, 1 – SRTP, 2 – V1.</span><span class="sxs-lookup"><span data-stu-id="e0549-p104">Security profile in use. 0 is NONE, 1 is SRTP, 2 is V1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0549-133">Transport</span><span class="sxs-lookup"><span data-stu-id="e0549-133">Transport</span></span></p></td>
<td><p><span data-ttu-id="e0549-134">tinyint</span><span class="sxs-lookup"><span data-stu-id="e0549-134">tinyint</span></span></p></td>
<td><p><span data-ttu-id="e0549-p105">Тип транспорта. 0 соответствует протоколу UDP, 1 – протоколу TCP.</span><span class="sxs-lookup"><span data-stu-id="e0549-p105">Transport type. 0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0549-137">каллерипаддр</span><span class="sxs-lookup"><span data-stu-id="e0549-137">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="e0549-138">var (50)</span><span class="sxs-lookup"><span data-stu-id="e0549-138">var(50)</span></span></p></td>
<td><p><span data-ttu-id="e0549-p106">IP-адрес вызывающего абонента. Это может быть адрес или по протоколу IPv4, или по протоколу IPv6.</span><span class="sxs-lookup"><span data-stu-id="e0549-p106">IP address of the caller. This can be either an IPv4 or IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0549-141">каллерпорт</span><span class="sxs-lookup"><span data-stu-id="e0549-141">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="e0549-142">int</span><span class="sxs-lookup"><span data-stu-id="e0549-142">int</span></span></p></td>
<td><p><span data-ttu-id="e0549-143">Порт, используемый вызывающим абонентом.</span><span class="sxs-lookup"><span data-stu-id="e0549-143">Port used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0549-144">каллеринсиде</span><span class="sxs-lookup"><span data-stu-id="e0549-144">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="e0549-145">Битовая</span><span class="sxs-lookup"><span data-stu-id="e0549-145">bit</span></span></p></td>
<td><p><span data-ttu-id="e0549-p107">Показывает, находится или нет вызывающий абонент внутри сети организации. 1 означает, что вызывающий абонент находится внутри сети предприятия. 0 означает, что вызывающий абонент находится вне такой сети.</span><span class="sxs-lookup"><span data-stu-id="e0549-p107">Indicates whether or not the caller is inside the organization network. 1 means that the caller is inside the enterprise network. 0 means that the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0549-149">каллермакаддресс</span><span class="sxs-lookup"><span data-stu-id="e0549-149">CallerMacAddress</span></span></p></td>
<td><p><span data-ttu-id="e0549-150">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="e0549-150">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e0549-151">MAC-адрес сетевого интерфейса, используемый вызывающим абонентом.</span><span class="sxs-lookup"><span data-stu-id="e0549-151">MAC address of network interface used by caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0549-152">каллеррелайипаддр</span><span class="sxs-lookup"><span data-stu-id="e0549-152">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="e0549-153">var (50)</span><span class="sxs-lookup"><span data-stu-id="e0549-153">var(50)</span></span></p></td>
<td><p><span data-ttu-id="e0549-154">IP-адрес пограничной службы обработки аудио- и видеоданных, используемой вызывающим абонентом.</span><span class="sxs-lookup"><span data-stu-id="e0549-154">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="e0549-155">Дополнительные сведения см. <a href="lync-server-2013-ipaddress-table.md">в таблице IPAddress в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e0549-155">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0549-156">каллирелайпорт</span><span class="sxs-lookup"><span data-stu-id="e0549-156">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="e0549-157">int</span><span class="sxs-lookup"><span data-stu-id="e0549-157">int</span></span></p></td>
<td><p><span data-ttu-id="e0549-158">Порт, задействованный пограничной службой аудио и видеоконференций, используемой вызывающим абонентом.</span><span class="sxs-lookup"><span data-stu-id="e0549-158">Port used on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0549-159">каллеррефлексивеипаддр</span><span class="sxs-lookup"><span data-stu-id="e0549-159">CallerReflexiveIPAddr</span></span></p></td>
<td><p><span data-ttu-id="e0549-160">var (50)</span><span class="sxs-lookup"><span data-stu-id="e0549-160">var(50)</span></span></p></td>
<td><p><span data-ttu-id="e0549-161">IP-адрес вызывающего абонента, который сообщается пограничной службой аудио и видео-конференций.</span><span class="sxs-lookup"><span data-stu-id="e0549-161">Caller’s IP address as reported by the A/V Edge service.</span></span> <span data-ttu-id="e0549-162">Этот адрес может отличаться от CallerIPAddr, если клиент, например, использует протокол преобразования сетевых адресов (NAT).</span><span class="sxs-lookup"><span data-stu-id="e0549-162">This address may be different that the CallerIPAddr if the client is located behind a NAT for example.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0549-163">каллеркаптуредев</span><span class="sxs-lookup"><span data-stu-id="e0549-163">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="e0549-164">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="e0549-164">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e0549-165">Имя устройства захвата вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="e0549-165">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0549-166">каллеррендердев</span><span class="sxs-lookup"><span data-stu-id="e0549-166">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="e0549-167">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="e0549-167">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e0549-168">Имя устройства обработки вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="e0549-168">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0549-169">каллеркаптуредевдривер</span><span class="sxs-lookup"><span data-stu-id="e0549-169">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="e0549-170">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="e0549-170">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e0549-171">Имя драйвера устройства захвата звонящего абонента.</span><span class="sxs-lookup"><span data-stu-id="e0549-171">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0549-172">каллеррендердевдривер</span><span class="sxs-lookup"><span data-stu-id="e0549-172">CallerRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="e0549-173">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="e0549-173">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e0549-174">Название драйвера устройства визуализации у вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="e0549-174">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0549-175">каллервифидривердевицедеск</span><span class="sxs-lookup"><span data-stu-id="e0549-175">CallerWifiDriverDeviceDesc</span></span></p></td>
<td><p><span data-ttu-id="e0549-176">varchar (256</span><span class="sxs-lookup"><span data-stu-id="e0549-176">varchar(256</span></span></p></td>
<td><p><span data-ttu-id="e0549-177">Описание драйвера беспроводной связи (Wi-Fi) у вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="e0549-177">Caller’s Wifi driver description.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0549-178">каллервифидриверверсион</span><span class="sxs-lookup"><span data-stu-id="e0549-178">CallerWifiDriverVersion</span></span></p></td>
<td><p><span data-ttu-id="e0549-179">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="e0549-179">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e0549-180">Версия драйвера беспроводной связи (Wi-Fi) у вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="e0549-180">Caller’s Wifi driver version.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0549-181">каллинетворкконнектиондетаил</span><span class="sxs-lookup"><span data-stu-id="e0549-181">CalleeNetworkConnectionDetail</span></span></p></td>
<td><p><span data-ttu-id="e0549-182">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="e0549-182">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e0549-183">Сведения о сетевом подключении вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="e0549-183">Details of caller’s network connection.</span></span> <span data-ttu-id="e0549-184">Дополнительные сведения см. <a href="lync-server-2013-networkconnectiondetail-table.md">в таблице нетворкконнектиондетаил в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e0549-184">See the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0549-185">каллербссид</span><span class="sxs-lookup"><span data-stu-id="e0549-185">CallerBssid</span></span></p></td>
<td><p><span data-ttu-id="e0549-186">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="e0549-186">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e0549-187">Идентификатор базового набора служб, используемый беспроводным (Wi-Fi) подключением вызывающих абонентов.</span><span class="sxs-lookup"><span data-stu-id="e0549-187">Basic Service Set Identifier used by callers WiFi connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0549-188">каллервпн</span><span class="sxs-lookup"><span data-stu-id="e0549-188">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="e0549-189">Битовая</span><span class="sxs-lookup"><span data-stu-id="e0549-189">bit</span></span></p></td>
<td><p><span data-ttu-id="e0549-p111">Показывает, подключен ли вызывающий абонент к виртуальной частной сети (VPN). 1 – подключен к виртуальной частной сети, 0 – не подключен к виртуальной частной сети.</span><span class="sxs-lookup"><span data-stu-id="e0549-p111">Indicates whether the caller connected over a virtual private network. 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0549-192">каллиипаддр</span><span class="sxs-lookup"><span data-stu-id="e0549-192">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="e0549-193">var (50)</span><span class="sxs-lookup"><span data-stu-id="e0549-193">var(50)</span></span></p></td>
<td><p><span data-ttu-id="e0549-194">IP-адрес вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="e0549-194">IP address of the callee.</span></span> <span data-ttu-id="e0549-195">Это может быть адрес или по протоколу IPv4, или по протоколу IPv6.</span><span class="sxs-lookup"><span data-stu-id="e0549-195">This can be either an IPv4 or IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0549-196">каллипорт</span><span class="sxs-lookup"><span data-stu-id="e0549-196">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="e0549-197">int</span><span class="sxs-lookup"><span data-stu-id="e0549-197">int</span></span></p></td>
<td><p><span data-ttu-id="e0549-198">Порт, используемый вызываемым абонентом.</span><span class="sxs-lookup"><span data-stu-id="e0549-198">Port used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0549-199">каллиинсиде</span><span class="sxs-lookup"><span data-stu-id="e0549-199">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="e0549-200">Битовая</span><span class="sxs-lookup"><span data-stu-id="e0549-200">bit</span></span></p></td>
<td><p><span data-ttu-id="e0549-p113">Показывает, находится ли вызываемый абонент внутри сети предприятия. 1 означает, что вызываемый абонент находится внутри сети предприятия, 0 означает, что вызываемый абонент находится вне сети предприятия.</span><span class="sxs-lookup"><span data-stu-id="e0549-p113">Indicates whether the callee is inside the enterprise network. 1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0549-203">каллимакаддресс</span><span class="sxs-lookup"><span data-stu-id="e0549-203">CalleeMacAddress</span></span></p></td>
<td><p><span data-ttu-id="e0549-204">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="e0549-204">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e0549-205">MAC-адрес сетевого интерфейса, используемый вызываемым абонентом.</span><span class="sxs-lookup"><span data-stu-id="e0549-205">MAC address of network interface used by callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0549-206">каллирелайипаддр</span><span class="sxs-lookup"><span data-stu-id="e0549-206">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="e0549-207">var (50)</span><span class="sxs-lookup"><span data-stu-id="e0549-207">var(50)</span></span></p></td>
<td><p><span data-ttu-id="e0549-208">IP-адрес пограничной службы аудио и видеоконференций, используемой вызываемым абонентом.</span><span class="sxs-lookup"><span data-stu-id="e0549-208">IP Address of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="e0549-209">Дополнительные сведения см. <a href="lync-server-2013-ipaddress-table.md">в таблице IPAddress в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e0549-209">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0549-210">каллирелайпорт</span><span class="sxs-lookup"><span data-stu-id="e0549-210">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="e0549-211">int</span><span class="sxs-lookup"><span data-stu-id="e0549-211">int</span></span></p></td>
<td><p><span data-ttu-id="e0549-212">Порт, задействованный пограничной службой аудио и видеоконференций, используемой вызываемым абонентом.</span><span class="sxs-lookup"><span data-stu-id="e0549-212">Port used on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0549-213">каллирефлексивеипаддр</span><span class="sxs-lookup"><span data-stu-id="e0549-213">CalleeReflexiveIPAddr</span></span></p></td>
<td><p><span data-ttu-id="e0549-214">var (50)</span><span class="sxs-lookup"><span data-stu-id="e0549-214">var(50)</span></span></p></td>
<td><p><span data-ttu-id="e0549-215">IP-адрес вызываемого абонента, который сообщается пограничной службой аудио и видеоконференций.</span><span class="sxs-lookup"><span data-stu-id="e0549-215">Callee’s IP address as reported by the A/V Edge service.</span></span> <span data-ttu-id="e0549-216">Этот адрес может отличаться от CalleeIPAddr, если клиент, например, использует протокол преобразования сетевых адресов.</span><span class="sxs-lookup"><span data-stu-id="e0549-216">This address may be different that the CalleeIPAddr if the client is located behind a NAT for example.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0549-217">калликаптуредев</span><span class="sxs-lookup"><span data-stu-id="e0549-217">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="e0549-218">var (50)</span><span class="sxs-lookup"><span data-stu-id="e0549-218">var(50)</span></span></p></td>
<td><p><span data-ttu-id="e0549-219">Название устройства захвата у вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="e0549-219">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0549-220">каллирендердев</span><span class="sxs-lookup"><span data-stu-id="e0549-220">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="e0549-221">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="e0549-221">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e0549-222">Имя устройства обработки вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="e0549-222">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0549-223">калликаптуредевдривер</span><span class="sxs-lookup"><span data-stu-id="e0549-223">CalleeCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="e0549-224">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="e0549-224">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e0549-225">Имя драйвера для устройства захвата вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="e0549-225">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0549-226">каллирендердевдривер</span><span class="sxs-lookup"><span data-stu-id="e0549-226">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="e0549-227">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="e0549-227">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e0549-228">Название драйвера устройства визуализации у вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="e0549-228">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0549-229">калливифидривердевицедеск</span><span class="sxs-lookup"><span data-stu-id="e0549-229">CalleeWifiDriverDeviceDesc</span></span></p></td>
<td><p><span data-ttu-id="e0549-230">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="e0549-230">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e0549-231">Описание драйвере беспроводной связи (Wi-Fi) у вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="e0549-231">Callee’s Wifi driver description.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0549-232">калливифидриверверсион</span><span class="sxs-lookup"><span data-stu-id="e0549-232">CalleeWifiDriverVersion</span></span></p></td>
<td><p><span data-ttu-id="e0549-233">varchar (256</span><span class="sxs-lookup"><span data-stu-id="e0549-233">varchar(256</span></span></p></td>
<td><p><span data-ttu-id="e0549-234">Версия драйвера беспроводной связи (Wi-Fi) у вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="e0549-234">Callee’s Wifi driver version.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0549-235">каллинетворкконнектиондетаил</span><span class="sxs-lookup"><span data-stu-id="e0549-235">CalleeNetworkConnectionDetail</span></span></p></td>
<td><p><span data-ttu-id="e0549-236">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="e0549-236">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e0549-237">Сведения о сетевом подключении вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="e0549-237">Details of callee’s network connection.</span></span> <span data-ttu-id="e0549-238">Дополнительные сведения см. <a href="lync-server-2013-networkconnectiondetail-table.md">в таблице нетворкконнектиондетаил в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e0549-238">See the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0549-239">каллибссид</span><span class="sxs-lookup"><span data-stu-id="e0549-239">CalleeBssid</span></span></p></td>
<td><p><span data-ttu-id="e0549-240">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="e0549-240">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e0549-241">Идентификатор базового набора служб, используемого подключением беспроводной связи (Wi-Fi) вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="e0549-241">Basic Service Set Identifier used by callee’s WiFi connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0549-242">калливпн</span><span class="sxs-lookup"><span data-stu-id="e0549-242">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="e0549-243">Битовая</span><span class="sxs-lookup"><span data-stu-id="e0549-243">bit</span></span></p></td>
<td><p><span data-ttu-id="e0549-p117">Показывает, подключен ли вызываемый абонент к виртуальной частной сети. 1 – подключен к виртуальной частной сети, 0 – не подключен к виртуальной частной сети.</span><span class="sxs-lookup"><span data-stu-id="e0549-p117">Indicates whether the callee connected over a virtual private network. 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0549-246">конверсатионалмос</span><span class="sxs-lookup"><span data-stu-id="e0549-246">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="e0549-247">десятичное число (3, 2)</span><span class="sxs-lookup"><span data-stu-id="e0549-247">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="e0549-248">Узкополосный MOS аудиосеансов (на основе обоих аудиопотоков).</span><span class="sxs-lookup"><span data-stu-id="e0549-248">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0549-249">апплиедбандвидслимит</span><span class="sxs-lookup"><span data-stu-id="e0549-249">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="e0549-250">int</span><span class="sxs-lookup"><span data-stu-id="e0549-250">int</span></span></p></td>
<td><p><span data-ttu-id="e0549-p118">Это фактическая полоса пропускания, применяемая к заданному потоку на стороне отправки при различных параметрах политики (TURN, API, SDP, Policy Server и т. д.). Её не следует путать с эффективной полосой пропускания, так как это может быть нижняя эффективная полоса пропускания, основанная на оценке ширины полосы пропускания. Это по существу максимальная полоса пропускания, которую может занимать отправляемый поток, в пределах, устанавливаемых оценкой полосы пропускания.</span><span class="sxs-lookup"><span data-stu-id="e0549-p118">This is the actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, etc.). This should not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate. This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0549-254">AppliedBandwidthSource</span><span class="sxs-lookup"><span data-stu-id="e0549-254">AppliedBandwidthSource</span></span></p></td>
<td><p><span data-ttu-id="e0549-255">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="e0549-255">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e0549-p119">Источник пределов, накладываемых на пропускную способность. Им описывается, откуда берутся пределы, устанавливаемые для полосы пропускания (например, “Сервер политики”, “TURN-сервер” или “Модальность”).</span><span class="sxs-lookup"><span data-stu-id="e0549-p119">Source of the bandwidth cap being imposed. It describes where the bandwidth limit is coming from (for example, “Policy Server”, “TURN Server”, or “Modality”).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0549-258">Вызывающая сторона</span><span class="sxs-lookup"><span data-stu-id="e0549-258">Caller</span></span></p></td>
<td><p><span data-ttu-id="e0549-259">Битовая</span><span class="sxs-lookup"><span data-stu-id="e0549-259">bit</span></span></p></td>
<td><p><span data-ttu-id="e0549-260">Показывает, принималась ли система показателей от вызывающего абонента; 1 – да, 0 – нет.</span><span class="sxs-lookup"><span data-stu-id="e0549-260">Indicates whether metrics from the caller were received; 1 is yes, 0 is no.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0549-261">Вызываемого абонента</span><span class="sxs-lookup"><span data-stu-id="e0549-261">Callee</span></span></p></td>
<td><p><span data-ttu-id="e0549-262">Битовая</span><span class="sxs-lookup"><span data-stu-id="e0549-262">bit</span></span></p></td>
<td><p><span data-ttu-id="e0549-263">Показывает, принималась ли система показателей от получателя вызова; 1 – да, 0 – нет.</span><span class="sxs-lookup"><span data-stu-id="e0549-263">Indicates whether metrics from the call receiver were received; 1 is yes, 0 is no.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0549-264">мидкаллрепорт</span><span class="sxs-lookup"><span data-stu-id="e0549-264">MidCallReport</span></span></p></td>
<td><p><span data-ttu-id="e0549-265">Битовая</span><span class="sxs-lookup"><span data-stu-id="e0549-265">bit</span></span></p></td>
<td><p><span data-ttu-id="e0549-266">Показывает, подготовлен ли отчет для части вызова или для всего вызова.</span><span class="sxs-lookup"><span data-stu-id="e0549-266">Indicates whether the report is for a portion of the call or for the complete call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0549-267">классифиедпуркалл</span><span class="sxs-lookup"><span data-stu-id="e0549-267">ClassifiedPoorCall</span></span></p></td>
<td><p><span data-ttu-id="e0549-268">Битовая</span><span class="sxs-lookup"><span data-stu-id="e0549-268">bit</span></span></p></td>
<td><p><span data-ttu-id="e0549-269">Показывает, были ли вызов оценен как плохой (1) или как хороший (0).</span><span class="sxs-lookup"><span data-stu-id="e0549-269">Indicates whether a call was classified as a poor call (1) or as a good call (0).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0549-270">каллерконнективитице</span><span class="sxs-lookup"><span data-stu-id="e0549-270">CallerConnectivityICE</span></span></p></td>
<td><p><span data-ttu-id="e0549-271">tinyint</span><span class="sxs-lookup"><span data-stu-id="e0549-271">tinyint</span></span></p></td>
<td><p><span data-ttu-id="e0549-272">Указывает, подключен ли абонент к сети через протокол ICE (Internet Connectivity Establishment).</span><span class="sxs-lookup"><span data-stu-id="e0549-272">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0549-273">калликоннективитице</span><span class="sxs-lookup"><span data-stu-id="e0549-273">CalleeConnectivityICE</span></span></p></td>
<td><p><span data-ttu-id="e0549-274">tinyint</span><span class="sxs-lookup"><span data-stu-id="e0549-274">tinyint</span></span></p></td>
<td><p><span data-ttu-id="e0549-275">Показывает, был ли вызываемый абонент подключен к сети через протокол ICE (Internet Connectivity Establishment).</span><span class="sxs-lookup"><span data-stu-id="e0549-275">Indicates whether the user called connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

