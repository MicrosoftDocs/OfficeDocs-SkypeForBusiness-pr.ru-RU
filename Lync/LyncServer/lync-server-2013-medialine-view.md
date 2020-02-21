---
title: 'Lync Server 2013: представление MediaLine'
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
ms.openlocfilehash: 21fa89b5afe53937ee515dac45053dbd84ae12ef
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42217604"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="medialine-view-in-lync-server-2013"></a><span data-ttu-id="e0906-102">Представление MediaLine в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e0906-102">MediaLine view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e0906-103">_**Последнее изменение темы:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="e0906-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="e0906-104">В представлении MediaLine хранятся сведения о каждой строке мультимедиа в базе данных.</span><span class="sxs-lookup"><span data-stu-id="e0906-104">The MediaLine View stores information about each media line in the database.</span></span> <span data-ttu-id="e0906-105">Один звуковой сеанс обычно содержит одну линию звукового носителя.</span><span class="sxs-lookup"><span data-stu-id="e0906-105">One audio session typically contains one audio media line.</span></span> <span data-ttu-id="e0906-106">Один сеанс аудио-и видеоданных (A/V) обычно содержит одну линию аудио-и видеоконференций; Однако в этом сеансе могут содержаться две видеолинии, если используется устройство конференц-связи или если используется представление галереи.</span><span class="sxs-lookup"><span data-stu-id="e0906-106">One audio and video (A/V) session typically contains one audio media line and one video media line; however, the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span> <span data-ttu-id="e0906-107">Это представление было представлено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e0906-107">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e0906-108">Столбец</span><span class="sxs-lookup"><span data-stu-id="e0906-108">Column</span></span></th>
<th><span data-ttu-id="e0906-109">Тип данных</span><span class="sxs-lookup"><span data-stu-id="e0906-109">Data Type</span></span></th>
<th><span data-ttu-id="e0906-110">подробности</span><span class="sxs-lookup"><span data-stu-id="e0906-110">details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e0906-111">конференцедатетиме</span><span class="sxs-lookup"><span data-stu-id="e0906-111">ConferenceDateTime</span></span></p></td>
<td><p><span data-ttu-id="e0906-112">datetime</span><span class="sxs-lookup"><span data-stu-id="e0906-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="e0906-113">Ссылка из <a href="lync-server-2013-medialine-table.md">таблицы MediaLine в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="e0906-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0906-114">сессионсек</span><span class="sxs-lookup"><span data-stu-id="e0906-114">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="e0906-115">int</span><span class="sxs-lookup"><span data-stu-id="e0906-115">int</span></span></p></td>
<td><p><span data-ttu-id="e0906-116">Ссылка из <a href="lync-server-2013-medialine-table.md">таблицы MediaLine в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="e0906-116">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0906-117">медиалинелабел</span><span class="sxs-lookup"><span data-stu-id="e0906-117">MediaLineLabel</span></span></p></td>
<td><p><span data-ttu-id="e0906-118">tinyint</span><span class="sxs-lookup"><span data-stu-id="e0906-118">tinyint</span></span></p></td>
<td><p><span data-ttu-id="e0906-119">Ссылка из <a href="lync-server-2013-medialine-table.md">таблицы MediaLine в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="e0906-119">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0906-120">каллерицеварнингфлагс</span><span class="sxs-lookup"><span data-stu-id="e0906-120">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="e0906-121">int</span><span class="sxs-lookup"><span data-stu-id="e0906-121">int</span></span></p></td>
<td><p><span data-ttu-id="e0906-p102">Сведения о технологии ICE (Interactive Connectivity Establishment), описанные в битовых флагах, для вызывающего абонента. Дополнительные сведения см. в спецификации протокола сервера мониторинга качества взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="e0906-p102">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0906-124">каллиицеварнингфлагс</span><span class="sxs-lookup"><span data-stu-id="e0906-124">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="e0906-125">int</span><span class="sxs-lookup"><span data-stu-id="e0906-125">int</span></span></p></td>
<td><p><span data-ttu-id="e0906-p103">Сведения о процессе установки интерактивной связи, описываемые во флажках разрядов для вызываемого абонента. Подробности см. в спецификации протокола сервера мониторинга качества взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="e0906-p103">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0906-128">Безопасность</span><span class="sxs-lookup"><span data-stu-id="e0906-128">Security</span></span></p></td>
<td><p><span data-ttu-id="e0906-129">tinyint</span><span class="sxs-lookup"><span data-stu-id="e0906-129">tinyint</span></span></p></td>
<td><p><span data-ttu-id="e0906-p104">Используемый профиль безопасности. 0 – это NONE, 1 – SRTP, 2 – V1.</span><span class="sxs-lookup"><span data-stu-id="e0906-p104">Security profile in use. 0 is NONE, 1 is SRTP, 2 is V1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0906-132">Transport</span><span class="sxs-lookup"><span data-stu-id="e0906-132">Transport</span></span></p></td>
<td><p><span data-ttu-id="e0906-133">tinyint</span><span class="sxs-lookup"><span data-stu-id="e0906-133">tinyint</span></span></p></td>
<td><p><span data-ttu-id="e0906-p105">Тип транспорта. 0 соответствует протоколу UDP, 1 – протоколу TCP.</span><span class="sxs-lookup"><span data-stu-id="e0906-p105">Transport type. 0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0906-136">каллерипаддр</span><span class="sxs-lookup"><span data-stu-id="e0906-136">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="e0906-137">var (50)</span><span class="sxs-lookup"><span data-stu-id="e0906-137">var(50)</span></span></p></td>
<td><p><span data-ttu-id="e0906-p106">IP-адрес вызывающего абонента. Это может быть адрес или по протоколу IPv4, или по протоколу IPv6.</span><span class="sxs-lookup"><span data-stu-id="e0906-p106">IP address of the caller. This can be either an IPv4 or IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0906-140">каллерпорт</span><span class="sxs-lookup"><span data-stu-id="e0906-140">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="e0906-141">int</span><span class="sxs-lookup"><span data-stu-id="e0906-141">int</span></span></p></td>
<td><p><span data-ttu-id="e0906-142">Порт, используемый вызывающим абонентом.</span><span class="sxs-lookup"><span data-stu-id="e0906-142">Port used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0906-143">каллеринсиде</span><span class="sxs-lookup"><span data-stu-id="e0906-143">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="e0906-144">Битовая</span><span class="sxs-lookup"><span data-stu-id="e0906-144">bit</span></span></p></td>
<td><p><span data-ttu-id="e0906-p107">Показывает, находится или нет вызывающий абонент внутри сети организации. 1 означает, что вызывающий абонент находится внутри сети предприятия. 0 означает, что вызывающий абонент находится вне такой сети.</span><span class="sxs-lookup"><span data-stu-id="e0906-p107">Indicates whether or not the caller is inside the organization network. 1 means that the caller is inside the enterprise network. 0 means that the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0906-148">каллермакаддресс</span><span class="sxs-lookup"><span data-stu-id="e0906-148">CallerMacAddress</span></span></p></td>
<td><p><span data-ttu-id="e0906-149">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="e0906-149">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e0906-150">MAC-адрес сетевого интерфейса, используемый вызывающим абонентом.</span><span class="sxs-lookup"><span data-stu-id="e0906-150">MAC address of network interface used by caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0906-151">каллеррелайипаддр</span><span class="sxs-lookup"><span data-stu-id="e0906-151">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="e0906-152">var (50)</span><span class="sxs-lookup"><span data-stu-id="e0906-152">var(50)</span></span></p></td>
<td><p><span data-ttu-id="e0906-153">IP-адрес пограничной службы обработки аудио- и видеоданных, используемой вызывающим абонентом.</span><span class="sxs-lookup"><span data-stu-id="e0906-153">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="e0906-154">Дополнительные сведения см. <a href="lync-server-2013-ipaddress-table.md">в таблице IPAddress в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e0906-154">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0906-155">каллирелайпорт</span><span class="sxs-lookup"><span data-stu-id="e0906-155">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="e0906-156">int</span><span class="sxs-lookup"><span data-stu-id="e0906-156">int</span></span></p></td>
<td><p><span data-ttu-id="e0906-157">Порт, задействованный пограничной службой аудио и видеоконференций, используемой вызывающим абонентом.</span><span class="sxs-lookup"><span data-stu-id="e0906-157">Port used on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0906-158">каллеррефлексивеипаддр</span><span class="sxs-lookup"><span data-stu-id="e0906-158">CallerReflexiveIPAddr</span></span></p></td>
<td><p><span data-ttu-id="e0906-159">var (50)</span><span class="sxs-lookup"><span data-stu-id="e0906-159">var(50)</span></span></p></td>
<td><p><span data-ttu-id="e0906-160">IP-адрес вызывающего абонента, который сообщается пограничной службой аудио и видео-конференций.</span><span class="sxs-lookup"><span data-stu-id="e0906-160">Caller’s IP address as reported by the A/V Edge service.</span></span> <span data-ttu-id="e0906-161">Этот адрес может отличаться от CallerIPAddr, если клиент, например, использует протокол преобразования сетевых адресов (NAT).</span><span class="sxs-lookup"><span data-stu-id="e0906-161">This address may be different that the CallerIPAddr if the client is located behind a NAT for example.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0906-162">каллеркаптуредев</span><span class="sxs-lookup"><span data-stu-id="e0906-162">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="e0906-163">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="e0906-163">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e0906-164">Имя устройства захвата вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="e0906-164">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0906-165">каллеррендердев</span><span class="sxs-lookup"><span data-stu-id="e0906-165">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="e0906-166">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="e0906-166">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e0906-167">Имя устройства обработки вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="e0906-167">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0906-168">каллеркаптуредевдривер</span><span class="sxs-lookup"><span data-stu-id="e0906-168">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="e0906-169">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="e0906-169">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e0906-170">Имя драйвера устройства захвата звонящего абонента.</span><span class="sxs-lookup"><span data-stu-id="e0906-170">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0906-171">каллеррендердевдривер</span><span class="sxs-lookup"><span data-stu-id="e0906-171">CallerRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="e0906-172">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="e0906-172">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e0906-173">Название драйвера устройства визуализации у вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="e0906-173">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0906-174">каллервифидривердевицедеск</span><span class="sxs-lookup"><span data-stu-id="e0906-174">CallerWifiDriverDeviceDesc</span></span></p></td>
<td><p><span data-ttu-id="e0906-175">varchar (256</span><span class="sxs-lookup"><span data-stu-id="e0906-175">varchar(256</span></span></p></td>
<td><p><span data-ttu-id="e0906-176">Описание драйвера беспроводной связи (Wi-Fi) у вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="e0906-176">Caller’s Wifi driver description.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0906-177">каллервифидриверверсион</span><span class="sxs-lookup"><span data-stu-id="e0906-177">CallerWifiDriverVersion</span></span></p></td>
<td><p><span data-ttu-id="e0906-178">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="e0906-178">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e0906-179">Версия драйвера беспроводной связи (Wi-Fi) у вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="e0906-179">Caller’s Wifi driver version.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0906-180">каллинетворкконнектиондетаил</span><span class="sxs-lookup"><span data-stu-id="e0906-180">CalleeNetworkConnectionDetail</span></span></p></td>
<td><p><span data-ttu-id="e0906-181">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="e0906-181">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e0906-182">Сведения о сетевом подключении вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="e0906-182">Details of caller’s network connection.</span></span> <span data-ttu-id="e0906-183">Дополнительные сведения см. <a href="lync-server-2013-networkconnectiondetail-table.md">в таблице нетворкконнектиондетаил в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e0906-183">See the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0906-184">каллербссид</span><span class="sxs-lookup"><span data-stu-id="e0906-184">CallerBssid</span></span></p></td>
<td><p><span data-ttu-id="e0906-185">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="e0906-185">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e0906-186">Идентификатор базового набора служб, используемый беспроводным (Wi-Fi) подключением вызывающих абонентов.</span><span class="sxs-lookup"><span data-stu-id="e0906-186">Basic Service Set Identifier used by callers WiFi connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0906-187">каллервпн</span><span class="sxs-lookup"><span data-stu-id="e0906-187">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="e0906-188">Битовая</span><span class="sxs-lookup"><span data-stu-id="e0906-188">bit</span></span></p></td>
<td><p><span data-ttu-id="e0906-p111">Показывает, подключен ли вызывающий абонент к виртуальной частной сети (VPN). 1 – подключен к виртуальной частной сети, 0 – не подключен к виртуальной частной сети.</span><span class="sxs-lookup"><span data-stu-id="e0906-p111">Indicates whether the caller connected over a virtual private network. 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0906-191">каллиипаддр</span><span class="sxs-lookup"><span data-stu-id="e0906-191">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="e0906-192">var (50)</span><span class="sxs-lookup"><span data-stu-id="e0906-192">var(50)</span></span></p></td>
<td><p><span data-ttu-id="e0906-193">IP-адрес вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="e0906-193">IP address of the callee.</span></span> <span data-ttu-id="e0906-194">Это может быть адрес или по протоколу IPv4, или по протоколу IPv6.</span><span class="sxs-lookup"><span data-stu-id="e0906-194">This can be either an IPv4 or IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0906-195">каллипорт</span><span class="sxs-lookup"><span data-stu-id="e0906-195">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="e0906-196">int</span><span class="sxs-lookup"><span data-stu-id="e0906-196">int</span></span></p></td>
<td><p><span data-ttu-id="e0906-197">Порт, используемый вызываемым абонентом.</span><span class="sxs-lookup"><span data-stu-id="e0906-197">Port used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0906-198">каллиинсиде</span><span class="sxs-lookup"><span data-stu-id="e0906-198">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="e0906-199">Битовая</span><span class="sxs-lookup"><span data-stu-id="e0906-199">bit</span></span></p></td>
<td><p><span data-ttu-id="e0906-p113">Показывает, находится ли вызываемый абонент внутри сети предприятия. 1 означает, что вызываемый абонент находится внутри сети предприятия, 0 означает, что вызываемый абонент находится вне сети предприятия.</span><span class="sxs-lookup"><span data-stu-id="e0906-p113">Indicates whether the callee is inside the enterprise network. 1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0906-202">каллимакаддресс</span><span class="sxs-lookup"><span data-stu-id="e0906-202">CalleeMacAddress</span></span></p></td>
<td><p><span data-ttu-id="e0906-203">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="e0906-203">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e0906-204">MAC-адрес сетевого интерфейса, используемый вызываемым абонентом.</span><span class="sxs-lookup"><span data-stu-id="e0906-204">MAC address of network interface used by callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0906-205">каллирелайипаддр</span><span class="sxs-lookup"><span data-stu-id="e0906-205">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="e0906-206">var (50)</span><span class="sxs-lookup"><span data-stu-id="e0906-206">var(50)</span></span></p></td>
<td><p><span data-ttu-id="e0906-207">IP-адрес пограничной службы аудио и видеоконференций, используемой вызываемым абонентом.</span><span class="sxs-lookup"><span data-stu-id="e0906-207">IP Address of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="e0906-208">Дополнительные сведения см. <a href="lync-server-2013-ipaddress-table.md">в таблице IPAddress в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e0906-208">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0906-209">каллирелайпорт</span><span class="sxs-lookup"><span data-stu-id="e0906-209">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="e0906-210">int</span><span class="sxs-lookup"><span data-stu-id="e0906-210">int</span></span></p></td>
<td><p><span data-ttu-id="e0906-211">Порт, задействованный пограничной службой аудио и видеоконференций, используемой вызываемым абонентом.</span><span class="sxs-lookup"><span data-stu-id="e0906-211">Port used on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0906-212">каллирефлексивеипаддр</span><span class="sxs-lookup"><span data-stu-id="e0906-212">CalleeReflexiveIPAddr</span></span></p></td>
<td><p><span data-ttu-id="e0906-213">var (50)</span><span class="sxs-lookup"><span data-stu-id="e0906-213">var(50)</span></span></p></td>
<td><p><span data-ttu-id="e0906-214">IP-адрес вызываемого абонента, который сообщается пограничной службой аудио и видеоконференций.</span><span class="sxs-lookup"><span data-stu-id="e0906-214">Callee’s IP address as reported by the A/V Edge service.</span></span> <span data-ttu-id="e0906-215">Этот адрес может отличаться от CalleeIPAddr, если клиент, например, использует протокол преобразования сетевых адресов.</span><span class="sxs-lookup"><span data-stu-id="e0906-215">This address may be different that the CalleeIPAddr if the client is located behind a NAT for example.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0906-216">калликаптуредев</span><span class="sxs-lookup"><span data-stu-id="e0906-216">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="e0906-217">var (50)</span><span class="sxs-lookup"><span data-stu-id="e0906-217">var(50)</span></span></p></td>
<td><p><span data-ttu-id="e0906-218">Название устройства захвата у вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="e0906-218">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0906-219">каллирендердев</span><span class="sxs-lookup"><span data-stu-id="e0906-219">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="e0906-220">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="e0906-220">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e0906-221">Имя устройства обработки вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="e0906-221">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0906-222">калликаптуредевдривер</span><span class="sxs-lookup"><span data-stu-id="e0906-222">CalleeCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="e0906-223">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="e0906-223">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e0906-224">Имя драйвера для устройства захвата вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="e0906-224">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0906-225">каллирендердевдривер</span><span class="sxs-lookup"><span data-stu-id="e0906-225">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="e0906-226">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="e0906-226">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e0906-227">Название драйвера устройства визуализации у вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="e0906-227">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0906-228">калливифидривердевицедеск</span><span class="sxs-lookup"><span data-stu-id="e0906-228">CalleeWifiDriverDeviceDesc</span></span></p></td>
<td><p><span data-ttu-id="e0906-229">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="e0906-229">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e0906-230">Описание драйвере беспроводной связи (Wi-Fi) у вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="e0906-230">Callee’s Wifi driver description.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0906-231">калливифидриверверсион</span><span class="sxs-lookup"><span data-stu-id="e0906-231">CalleeWifiDriverVersion</span></span></p></td>
<td><p><span data-ttu-id="e0906-232">varchar (256</span><span class="sxs-lookup"><span data-stu-id="e0906-232">varchar(256</span></span></p></td>
<td><p><span data-ttu-id="e0906-233">Версия драйвера беспроводной связи (Wi-Fi) у вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="e0906-233">Callee’s Wifi driver version.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0906-234">каллинетворкконнектиондетаил</span><span class="sxs-lookup"><span data-stu-id="e0906-234">CalleeNetworkConnectionDetail</span></span></p></td>
<td><p><span data-ttu-id="e0906-235">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="e0906-235">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e0906-236">Сведения о сетевом подключении вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="e0906-236">Details of callee’s network connection.</span></span> <span data-ttu-id="e0906-237">Дополнительные сведения см. <a href="lync-server-2013-networkconnectiondetail-table.md">в таблице нетворкконнектиондетаил в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e0906-237">See the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0906-238">каллибссид</span><span class="sxs-lookup"><span data-stu-id="e0906-238">CalleeBssid</span></span></p></td>
<td><p><span data-ttu-id="e0906-239">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="e0906-239">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e0906-240">Идентификатор базового набора служб, используемого подключением беспроводной связи (Wi-Fi) вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="e0906-240">Basic Service Set Identifier used by callee’s WiFi connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0906-241">калливпн</span><span class="sxs-lookup"><span data-stu-id="e0906-241">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="e0906-242">Битовая</span><span class="sxs-lookup"><span data-stu-id="e0906-242">bit</span></span></p></td>
<td><p><span data-ttu-id="e0906-p117">Показывает, подключен ли вызываемый абонент к виртуальной частной сети. 1 – подключен к виртуальной частной сети, 0 – не подключен к виртуальной частной сети.</span><span class="sxs-lookup"><span data-stu-id="e0906-p117">Indicates whether the callee connected over a virtual private network. 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0906-245">конверсатионалмос</span><span class="sxs-lookup"><span data-stu-id="e0906-245">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="e0906-246">десятичное число (3, 2)</span><span class="sxs-lookup"><span data-stu-id="e0906-246">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="e0906-247">Узкополосный MOS аудиосеансов (на основе обоих аудиопотоков).</span><span class="sxs-lookup"><span data-stu-id="e0906-247">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0906-248">апплиедбандвидслимит</span><span class="sxs-lookup"><span data-stu-id="e0906-248">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="e0906-249">int</span><span class="sxs-lookup"><span data-stu-id="e0906-249">int</span></span></p></td>
<td><p><span data-ttu-id="e0906-p118">Это фактическая полоса пропускания, применяемая к заданному потоку на стороне отправки при различных параметрах политики (TURN, API, SDP, Policy Server и т. д.). Её не следует путать с эффективной полосой пропускания, так как это может быть нижняя эффективная полоса пропускания, основанная на оценке ширины полосы пропускания. Это по существу максимальная полоса пропускания, которую может занимать отправляемый поток, в пределах, устанавливаемых оценкой полосы пропускания.</span><span class="sxs-lookup"><span data-stu-id="e0906-p118">This is the actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, etc.). This should not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate. This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0906-253">Таблица appliedbandwidthsource</span><span class="sxs-lookup"><span data-stu-id="e0906-253">AppliedBandwidthSource</span></span></p></td>
<td><p><span data-ttu-id="e0906-254">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="e0906-254">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e0906-p119">Источник пределов, накладываемых на пропускную способность. Им описывается, откуда берутся пределы, устанавливаемые для полосы пропускания (например, “Сервер политики”, “TURN-сервер” или “Модальность”).</span><span class="sxs-lookup"><span data-stu-id="e0906-p119">Source of the bandwidth cap being imposed. It describes where the bandwidth limit is coming from (for example, “Policy Server”, “TURN Server”, or “Modality”).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0906-257">Вызывающая сторона</span><span class="sxs-lookup"><span data-stu-id="e0906-257">Caller</span></span></p></td>
<td><p><span data-ttu-id="e0906-258">Битовая</span><span class="sxs-lookup"><span data-stu-id="e0906-258">bit</span></span></p></td>
<td><p><span data-ttu-id="e0906-259">Показывает, принималась ли система показателей от вызывающего абонента; 1 – да, 0 – нет.</span><span class="sxs-lookup"><span data-stu-id="e0906-259">Indicates whether metrics from the caller were received; 1 is yes, 0 is no.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0906-260">Вызываемого абонента</span><span class="sxs-lookup"><span data-stu-id="e0906-260">Callee</span></span></p></td>
<td><p><span data-ttu-id="e0906-261">Битовая</span><span class="sxs-lookup"><span data-stu-id="e0906-261">bit</span></span></p></td>
<td><p><span data-ttu-id="e0906-262">Показывает, принималась ли система показателей от получателя вызова; 1 – да, 0 – нет.</span><span class="sxs-lookup"><span data-stu-id="e0906-262">Indicates whether metrics from the call receiver were received; 1 is yes, 0 is no.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0906-263">мидкаллрепорт</span><span class="sxs-lookup"><span data-stu-id="e0906-263">MidCallReport</span></span></p></td>
<td><p><span data-ttu-id="e0906-264">Битовая</span><span class="sxs-lookup"><span data-stu-id="e0906-264">bit</span></span></p></td>
<td><p><span data-ttu-id="e0906-265">Показывает, подготовлен ли отчет для части вызова или для всего вызова.</span><span class="sxs-lookup"><span data-stu-id="e0906-265">Indicates whether the report is for a portion of the call or for the complete call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0906-266">классифиедпуркалл</span><span class="sxs-lookup"><span data-stu-id="e0906-266">ClassifiedPoorCall</span></span></p></td>
<td><p><span data-ttu-id="e0906-267">Битовая</span><span class="sxs-lookup"><span data-stu-id="e0906-267">bit</span></span></p></td>
<td><p><span data-ttu-id="e0906-268">Показывает, были ли вызов оценен как плохой (1) или как хороший (0).</span><span class="sxs-lookup"><span data-stu-id="e0906-268">Indicates whether a call was classified as a poor call (1) or as a good call (0).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0906-269">каллерконнективитице</span><span class="sxs-lookup"><span data-stu-id="e0906-269">CallerConnectivityICE</span></span></p></td>
<td><p><span data-ttu-id="e0906-270">tinyint</span><span class="sxs-lookup"><span data-stu-id="e0906-270">tinyint</span></span></p></td>
<td><p><span data-ttu-id="e0906-271">Указывает, подключен ли абонент к сети через протокол ICE (Internet Connectivity Establishment).</span><span class="sxs-lookup"><span data-stu-id="e0906-271">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0906-272">калликоннективитице</span><span class="sxs-lookup"><span data-stu-id="e0906-272">CalleeConnectivityICE</span></span></p></td>
<td><p><span data-ttu-id="e0906-273">tinyint</span><span class="sxs-lookup"><span data-stu-id="e0906-273">tinyint</span></span></p></td>
<td><p><span data-ttu-id="e0906-274">Показывает, был ли вызываемый абонент подключен к сети через протокол ICE (Internet Connectivity Establishment).</span><span class="sxs-lookup"><span data-stu-id="e0906-274">Indicates whether the user called connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

