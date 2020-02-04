---
title: 'Lync Server 2013: представление Видеостреамдетаил'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: VideoStreamDetail view
ms:assetid: ec8c45e1-307d-40ec-a75e-6083306105f2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721928(v=OCS.15)
ms:contentKeyID: 49733863
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dfa754fbcc24377b07bab3b13473adb1c5e953ea
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741979"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="videostreamdetail-view-in-lync-server-2013"></a><span data-ttu-id="fab33-102">Видеостреамдетаил представления в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fab33-102">VideoStreamDetail view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fab33-103">_**Тема последнего изменения:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="fab33-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="fab33-104">В представлении Видеостреамдетаил хранятся сведения о каждом видеопотоке в базе данных.</span><span class="sxs-lookup"><span data-stu-id="fab33-104">The VideoStreamDetail View stores information about each video stream in the database.</span></span> <span data-ttu-id="fab33-105">Это представление было представлено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fab33-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fab33-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="fab33-106">Column</span></span></th>
<th><span data-ttu-id="fab33-107">Тип данных</span><span class="sxs-lookup"><span data-stu-id="fab33-107">Data Type</span></span></th>
<th><span data-ttu-id="fab33-108">Описание</span><span class="sxs-lookup"><span data-stu-id="fab33-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fab33-109">сессионтиме</span><span class="sxs-lookup"><span data-stu-id="fab33-109">SessionTime</span></span></p></td>
<td><p><span data-ttu-id="fab33-110">datetime</span><span class="sxs-lookup"><span data-stu-id="fab33-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="fab33-111">На которую ссылается <a href="lync-server-2013-medialine-table.md">Таблица медиалине в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="fab33-111">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fab33-112">сессионсек</span><span class="sxs-lookup"><span data-stu-id="fab33-112">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="fab33-113">целое</span><span class="sxs-lookup"><span data-stu-id="fab33-113">int</span></span></p></td>
<td><p><span data-ttu-id="fab33-114">На которую ссылается <a href="lync-server-2013-medialine-table.md">Таблица медиалине в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="fab33-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fab33-115">медиалинелабел</span><span class="sxs-lookup"><span data-stu-id="fab33-115">MediaLineLabel</span></span></p></td>
<td><p><span data-ttu-id="fab33-116">tinyint</span><span class="sxs-lookup"><span data-stu-id="fab33-116">tinyint</span></span></p></td>
<td><p><span data-ttu-id="fab33-117">На которую ссылается <a href="lync-server-2013-medialine-table.md">Таблица медиалине в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="fab33-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fab33-118">стреамид</span><span class="sxs-lookup"><span data-stu-id="fab33-118">StreamId</span></span></p></td>
<td><p><span data-ttu-id="fab33-119">целое</span><span class="sxs-lookup"><span data-stu-id="fab33-119">int</span></span></p></td>
<td><p><span data-ttu-id="fab33-120">Уникальный идентификатор в строке мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="fab33-120">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fab33-121">StartTime</span><span class="sxs-lookup"><span data-stu-id="fab33-121">StartTime</span></span></p></td>
<td><p><span data-ttu-id="fab33-122">datetime</span><span class="sxs-lookup"><span data-stu-id="fab33-122">datetime</span></span></p></td>
<td><p><span data-ttu-id="fab33-123">Время начала сеанса.</span><span class="sxs-lookup"><span data-stu-id="fab33-123">Start time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fab33-124">EndTime</span><span class="sxs-lookup"><span data-stu-id="fab33-124">EndTime</span></span></p></td>
<td><p><span data-ttu-id="fab33-125">datetime</span><span class="sxs-lookup"><span data-stu-id="fab33-125">datetime</span></span></p></td>
<td><p><span data-ttu-id="fab33-126">Время окончания сеанса.</span><span class="sxs-lookup"><span data-stu-id="fab33-126">End time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fab33-127">каллприорити</span><span class="sxs-lookup"><span data-stu-id="fab33-127">CallPriority</span></span></p></td>
<td><p><span data-ttu-id="fab33-128">целое</span><span class="sxs-lookup"><span data-stu-id="fab33-128">int</span></span></p></td>
<td><p><span data-ttu-id="fab33-129">Приоритет звонка.</span><span class="sxs-lookup"><span data-stu-id="fab33-129">Priority of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fab33-130">каллерпул</span><span class="sxs-lookup"><span data-stu-id="fab33-130">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="fab33-131">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="fab33-131">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fab33-132">Полное доменное имя пула вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="fab33-132">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fab33-133">каллипул</span><span class="sxs-lookup"><span data-stu-id="fab33-133">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="fab33-134">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="fab33-134">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fab33-135">Полное доменное имя пула вызываемых абонентов.</span><span class="sxs-lookup"><span data-stu-id="fab33-135">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fab33-136">Вызывающая сторона</span><span class="sxs-lookup"><span data-stu-id="fab33-136">Caller</span></span></p></td>
<td><p><span data-ttu-id="fab33-137">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="fab33-137">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="fab33-138">URI вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="fab33-138">Caller’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fab33-139">Вызываемая сторона</span><span class="sxs-lookup"><span data-stu-id="fab33-139">Callee</span></span></p></td>
<td><p><span data-ttu-id="fab33-140">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="fab33-140">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="fab33-141">Универсальный код ресурса (URI) вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="fab33-141">Callee’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fab33-142">каллерусеражент</span><span class="sxs-lookup"><span data-stu-id="fab33-142">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="fab33-143">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="fab33-143">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fab33-144">Строка агента пользователя вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="fab33-144">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fab33-145">каллерусераженттипе</span><span class="sxs-lookup"><span data-stu-id="fab33-145">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="fab33-146">smallint</span><span class="sxs-lookup"><span data-stu-id="fab33-146">smallint</span></span></p></td>
<td><p><span data-ttu-id="fab33-147">Тип агента пользователя вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="fab33-147">Type of caller’s user agent.</span></span> <span data-ttu-id="fab33-148">Дополнительные сведения: <a href="lync-server-2013-useragent-table.md">Таблица UserAgent в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="fab33-148">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fab33-149">каллерусераженткатегори</span><span class="sxs-lookup"><span data-stu-id="fab33-149">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="fab33-150">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="fab33-150">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="fab33-151">Категория агента пользователя вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="fab33-151">Category of caller’s user agent.</span></span> <span data-ttu-id="fab33-152">Дополнительные сведения <a href="lync-server-2013-useragentdef-table-qoe.md">усеражентдеф в таблице "QoE" в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="fab33-152">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fab33-153">каллиусеражент</span><span class="sxs-lookup"><span data-stu-id="fab33-153">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="fab33-154">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="fab33-154">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fab33-155">Строка агента пользователя вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="fab33-155">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fab33-156">каллиусераженттипе</span><span class="sxs-lookup"><span data-stu-id="fab33-156">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="fab33-157">smallint</span><span class="sxs-lookup"><span data-stu-id="fab33-157">smallint</span></span></p></td>
<td><p><span data-ttu-id="fab33-158">Тип агента пользователя, вызываемого абонентом.</span><span class="sxs-lookup"><span data-stu-id="fab33-158">Type of callee’s user agent.</span></span> <span data-ttu-id="fab33-159">Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-useragent-table.md">таблицей UserAgent в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="fab33-159">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fab33-160">каллиусераженткатегори</span><span class="sxs-lookup"><span data-stu-id="fab33-160">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="fab33-161">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="fab33-161">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="fab33-162">Категория агента пользователя вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="fab33-162">Category of callee’s user agent.</span></span> <span data-ttu-id="fab33-163">Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-useragentdef-table-qoe.md">таблицей усеражентдеф (QoE) в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="fab33-163">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fab33-164">каллерендпоинт</span><span class="sxs-lookup"><span data-stu-id="fab33-164">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="fab33-165">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="fab33-165">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fab33-166">Имя конечной точки вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="fab33-166">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fab33-167">каллиендпоинт</span><span class="sxs-lookup"><span data-stu-id="fab33-167">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="fab33-168">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="fab33-168">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fab33-169">Имя конечной точки вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="fab33-169">Callee’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fab33-170">каллерос</span><span class="sxs-lookup"><span data-stu-id="fab33-170">CallerOS</span></span></p></td>
<td><p><span data-ttu-id="fab33-171">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="fab33-171">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="fab33-172">Операционная система (ОС) конечной точки вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="fab33-172">Operating system (OS) of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fab33-173">каллиос</span><span class="sxs-lookup"><span data-stu-id="fab33-173">CalleeOS</span></span></p></td>
<td><p><span data-ttu-id="fab33-174">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="fab33-174">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="fab33-175">Операционная система (ОС) конечной точки вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="fab33-175">Operating system (OS) of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fab33-176">каллеркпунаме</span><span class="sxs-lookup"><span data-stu-id="fab33-176">CallerCPUName</span></span></p></td>
<td><p><span data-ttu-id="fab33-177">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="fab33-177">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="fab33-178">Имя ЦП конечной точки вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="fab33-178">CPU name of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fab33-179">калликпунаме</span><span class="sxs-lookup"><span data-stu-id="fab33-179">CalleeCPUName</span></span></p></td>
<td><p><span data-ttu-id="fab33-180">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="fab33-180">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="fab33-181">Имя ЦП конечной точки вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="fab33-181">CPU name of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fab33-182">каллеркпунумберофкорес</span><span class="sxs-lookup"><span data-stu-id="fab33-182">CallerCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="fab33-183">smallint</span><span class="sxs-lookup"><span data-stu-id="fab33-183">smallint</span></span></p></td>
<td><p><span data-ttu-id="fab33-184">Количество ядер ЦП конечной точки вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="fab33-184">Number of CPU cores of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fab33-185">калликпунумберофкорес</span><span class="sxs-lookup"><span data-stu-id="fab33-185">CalleeCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="fab33-186">smallint</span><span class="sxs-lookup"><span data-stu-id="fab33-186">smallint</span></span></p></td>
<td><p><span data-ttu-id="fab33-187">Количество ядер ЦП конечной точки вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="fab33-187">Number of CPU cores of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fab33-188">каллеркпупроцессорспид</span><span class="sxs-lookup"><span data-stu-id="fab33-188">CallerCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="fab33-189">целое</span><span class="sxs-lookup"><span data-stu-id="fab33-189">int</span></span></p></td>
<td><p><span data-ttu-id="fab33-190">Частота процессора конечной точки вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="fab33-190">CPU processor speed of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fab33-191">калликпупроцессорспид</span><span class="sxs-lookup"><span data-stu-id="fab33-191">CalleeCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="fab33-192">целое</span><span class="sxs-lookup"><span data-stu-id="fab33-192">int</span></span></p></td>
<td><p><span data-ttu-id="fab33-193">Тактовая частота процессора на конечной точке вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="fab33-193">CPU processor speed of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fab33-194">каллервиртуализатионфлаг</span><span class="sxs-lookup"><span data-stu-id="fab33-194">CallerVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="fab33-195">tinyint</span><span class="sxs-lookup"><span data-stu-id="fab33-195">tinyint</span></span></p></td>
<td><p><span data-ttu-id="fab33-196">Указывает, работает ли система вызывающего абонента в виртуализованной среде.</span><span class="sxs-lookup"><span data-stu-id="fab33-196">Indicates whether the caller’s system is running in a virtualized environment.</span></span> <span data-ttu-id="fab33-197">Дополнительные сведения приведены <a href="lync-server-2013-endpoint-table.md">в таблице конечная точка в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="fab33-197">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fab33-198">калливиртуализатионфлаг</span><span class="sxs-lookup"><span data-stu-id="fab33-198">CalleeVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="fab33-199">tinyint</span><span class="sxs-lookup"><span data-stu-id="fab33-199">tinyint</span></span></p></td>
<td><p><span data-ttu-id="fab33-200">Указывает, работает ли система вызываемого абонента в виртуализованной среде.</span><span class="sxs-lookup"><span data-stu-id="fab33-200">Indicates whether the callee’s system is running in a virtualized environment.</span></span> <span data-ttu-id="fab33-201">Дополнительные сведения приведены <a href="lync-server-2013-endpoint-table.md">в таблице конечная точка в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="fab33-201">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fab33-202">коннективитице</span><span class="sxs-lookup"><span data-stu-id="fab33-202">ConnectivityIce</span></span></p></td>
<td><p><span data-ttu-id="fab33-203">tinyint</span><span class="sxs-lookup"><span data-stu-id="fab33-203">tinyint</span></span></p></td>
<td><p><span data-ttu-id="fab33-204">Сведения о пути к носителю, например прямая или ретранслируемая.</span><span class="sxs-lookup"><span data-stu-id="fab33-204">Information about media path, such as direct or relayed.</span></span> <span data-ttu-id="fab33-205">Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-medialine-table.md">таблицей медиалине в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="fab33-205">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fab33-206">каллерицеварнингфлагс</span><span class="sxs-lookup"><span data-stu-id="fab33-206">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="fab33-207">целое</span><span class="sxs-lookup"><span data-stu-id="fab33-207">int</span></span></p></td>
<td><p><span data-ttu-id="fab33-208">Сведения о процессе интерактивной установки подключения (ICE), описанные в разделе Флаги BITS для вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="fab33-208">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller.</span></span> <span data-ttu-id="fab33-209">Подробности можно найти в спецификации серверного протокола контроля качества обслуживания.</span><span class="sxs-lookup"><span data-stu-id="fab33-209">For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fab33-210">каллиицеварнингфлагс</span><span class="sxs-lookup"><span data-stu-id="fab33-210">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="fab33-211">целое</span><span class="sxs-lookup"><span data-stu-id="fab33-211">int</span></span></p></td>
<td><p><span data-ttu-id="fab33-212">Сведения о процессе установки интерактивной связи (ICE), описанные в флагах BITS для вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="fab33-212">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee.</span></span> <span data-ttu-id="fab33-213">Подробности можно найти в спецификации серверного протокола контроля качества обслуживания.</span><span class="sxs-lookup"><span data-stu-id="fab33-213">For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fab33-214">Transport</span><span class="sxs-lookup"><span data-stu-id="fab33-214">Transport</span></span></p></td>
<td><p><span data-ttu-id="fab33-215">целое</span><span class="sxs-lookup"><span data-stu-id="fab33-215">int</span></span></p></td>
<td><p><span data-ttu-id="fab33-216">Тип транспорта: 0 — UDP, 1 — TCP.</span><span class="sxs-lookup"><span data-stu-id="fab33-216">Transport type: 0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fab33-217">каллерипаддр</span><span class="sxs-lookup"><span data-stu-id="fab33-217">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="fab33-218">var (50)</span><span class="sxs-lookup"><span data-stu-id="fab33-218">var(50)</span></span></p></td>
<td><p><span data-ttu-id="fab33-219">IP-адрес вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="fab33-219">IP address of the caller.</span></span> <span data-ttu-id="fab33-220">Это может быть либо IPv4, либо IPv6-адрес.</span><span class="sxs-lookup"><span data-stu-id="fab33-220">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fab33-221">каллерпорт</span><span class="sxs-lookup"><span data-stu-id="fab33-221">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="fab33-222">целое</span><span class="sxs-lookup"><span data-stu-id="fab33-222">int</span></span></p></td>
<td><p><span data-ttu-id="fab33-223">Порт, используемый вызывающим абонентом.</span><span class="sxs-lookup"><span data-stu-id="fab33-223">Port used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fab33-224">каллеринсиде</span><span class="sxs-lookup"><span data-stu-id="fab33-224">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="fab33-225">бит</span><span class="sxs-lookup"><span data-stu-id="fab33-225">bit</span></span></p></td>
<td><p><span data-ttu-id="fab33-226">Указывает, находится ли вызывающий абонент в сети Организации.</span><span class="sxs-lookup"><span data-stu-id="fab33-226">Indicates whether the caller is inside the organization network.</span></span> <span data-ttu-id="fab33-227">1 означает, что вызывающий абонент входит в корпоративную сеть, а 0 означает, что вызывающий абонент находится за пределами сети.</span><span class="sxs-lookup"><span data-stu-id="fab33-227">1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fab33-228">каллиипаддр</span><span class="sxs-lookup"><span data-stu-id="fab33-228">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="fab33-229">var (50)</span><span class="sxs-lookup"><span data-stu-id="fab33-229">var(50)</span></span></p></td>
<td><p><span data-ttu-id="fab33-230">IP-адрес вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="fab33-230">IP address of the callee.</span></span> <span data-ttu-id="fab33-231">Это может быть либо IPv4, либо IPv6-адрес.</span><span class="sxs-lookup"><span data-stu-id="fab33-231">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fab33-232">каллипорт</span><span class="sxs-lookup"><span data-stu-id="fab33-232">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="fab33-233">целое</span><span class="sxs-lookup"><span data-stu-id="fab33-233">int</span></span></p></td>
<td><p><span data-ttu-id="fab33-234">Порт, используемый вызываемым абонентом.</span><span class="sxs-lookup"><span data-stu-id="fab33-234">Port used by the callee.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fab33-235">каллиинсиде</span><span class="sxs-lookup"><span data-stu-id="fab33-235">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="fab33-236">бит</span><span class="sxs-lookup"><span data-stu-id="fab33-236">bit</span></span></p></td>
<td><p><span data-ttu-id="fab33-237">Указывает, входит ли вызывающий объект в сеть Организации. 1 означает вызываемый абонент в корпоративной сети, 0 означает, что вызываемый абонент находится за пределами сети.</span><span class="sxs-lookup"><span data-stu-id="fab33-237">Indicates whether the caller is inside the organization network.1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fab33-238">каллерусерсите</span><span class="sxs-lookup"><span data-stu-id="fab33-238">CallerUserSite</span></span></p></td>
<td><p><span data-ttu-id="fab33-239">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="fab33-239">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="fab33-240">Имя сайта вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="fab33-240">Name of the caller’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fab33-241">каллеррегион</span><span class="sxs-lookup"><span data-stu-id="fab33-241">CallerRegion</span></span></p></td>
<td><p><span data-ttu-id="fab33-242">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="fab33-242">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="fab33-243">Название страны или региона сайта вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="fab33-243">Name of the country/region of the caller’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fab33-244">каллиусерсите</span><span class="sxs-lookup"><span data-stu-id="fab33-244">CalleeUserSite</span></span></p></td>
<td><p><span data-ttu-id="fab33-245">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="fab33-245">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="fab33-246">Имя сайта вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="fab33-246">Name of the callee’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fab33-247">каллирегион</span><span class="sxs-lookup"><span data-stu-id="fab33-247">CalleeRegion</span></span></p></td>
<td><p><span data-ttu-id="fab33-248">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="fab33-248">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="fab33-249">Название страны или региона сайта вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="fab33-249">Name of the country/region of the callee’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fab33-250">каллеррелайипаддр</span><span class="sxs-lookup"><span data-stu-id="fab33-250">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="fab33-251">var (50)</span><span class="sxs-lookup"><span data-stu-id="fab33-251">var(50)</span></span></p></td>
<td><p><span data-ttu-id="fab33-252">IP-адрес службы EDGE (/V), используемой вызывающим абонентом.</span><span class="sxs-lookup"><span data-stu-id="fab33-252">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="fab33-253">Дополнительные сведения приведены в <a href="lync-server-2013-ipaddress-table.md">таблице IP-адрес в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="fab33-253">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fab33-254">каллеррелайпорт</span><span class="sxs-lookup"><span data-stu-id="fab33-254">CallerRelayPort</span></span></p></td>
<td><p><span data-ttu-id="fab33-255">целое</span><span class="sxs-lookup"><span data-stu-id="fab33-255">int</span></span></p></td>
<td><p><span data-ttu-id="fab33-256">Порт для службы EDGE (A/V), используемой вызывающим абонентом.</span><span class="sxs-lookup"><span data-stu-id="fab33-256">Port on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fab33-257">каллирелайипаддр</span><span class="sxs-lookup"><span data-stu-id="fab33-257">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="fab33-258">var (50)</span><span class="sxs-lookup"><span data-stu-id="fab33-258">var(50)</span></span></p></td>
<td><p><span data-ttu-id="fab33-259">Ключ IP-адреса для службы EDGE (/V), используемой вызываемым абонентом.</span><span class="sxs-lookup"><span data-stu-id="fab33-259">IP Address key of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="fab33-260">Дополнительные сведения приведены в <a href="lync-server-2013-ipaddress-table.md">таблице IP-адрес в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="fab33-260">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fab33-261">каллирелайпорт</span><span class="sxs-lookup"><span data-stu-id="fab33-261">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="fab33-262">целое</span><span class="sxs-lookup"><span data-stu-id="fab33-262">int</span></span></p></td>
<td><p><span data-ttu-id="fab33-263">Порт для службы EDGE (A/V), используемой вызываемым абонентом.</span><span class="sxs-lookup"><span data-stu-id="fab33-263">Port on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fab33-264">каллеркаптуредев</span><span class="sxs-lookup"><span data-stu-id="fab33-264">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="fab33-265">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="fab33-265">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fab33-266">Имя устройства захвата вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="fab33-266">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fab33-267">каллеррендердев</span><span class="sxs-lookup"><span data-stu-id="fab33-267">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="fab33-268">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="fab33-268">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fab33-269">Имя устройства отрисовки вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="fab33-269">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fab33-270">каллеркаптуредевдривер</span><span class="sxs-lookup"><span data-stu-id="fab33-270">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="fab33-271">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="fab33-271">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fab33-272">Имя драйвера устройства захвата вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="fab33-272">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fab33-273">каллеррендердевдривер</span><span class="sxs-lookup"><span data-stu-id="fab33-273">CallerRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="fab33-274">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="fab33-274">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fab33-275">Имя драйвера устройства отрисовки вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="fab33-275">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fab33-276">калликаптуредев</span><span class="sxs-lookup"><span data-stu-id="fab33-276">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="fab33-277">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="fab33-277">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fab33-278">Имя устройства захвата абонента.</span><span class="sxs-lookup"><span data-stu-id="fab33-278">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fab33-279">каллирендердев</span><span class="sxs-lookup"><span data-stu-id="fab33-279">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="fab33-280">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="fab33-280">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fab33-281">Имя устройства отрисовки вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="fab33-281">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fab33-282">каллекаптуредевдривер</span><span class="sxs-lookup"><span data-stu-id="fab33-282">CalleCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="fab33-283">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="fab33-283">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fab33-284">Имя драйвера устройства захвата абонента.</span><span class="sxs-lookup"><span data-stu-id="fab33-284">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fab33-285">каллирендердевдривер</span><span class="sxs-lookup"><span data-stu-id="fab33-285">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="fab33-286">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="fab33-286">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fab33-287">Имя драйвера устройства обработки вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="fab33-287">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fab33-288">каллернетворкконнектионтипе</span><span class="sxs-lookup"><span data-stu-id="fab33-288">CallerNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="fab33-289">tinyint</span><span class="sxs-lookup"><span data-stu-id="fab33-289">tinyint</span></span></p></td>
<td><p><span data-ttu-id="fab33-290">Тип сетевого подключения вызывающего абонента: 0 проводное соединение, 1 — Беспроводная связь.</span><span class="sxs-lookup"><span data-stu-id="fab33-290">Caller’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fab33-291">каллервпн</span><span class="sxs-lookup"><span data-stu-id="fab33-291">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="fab33-292">бит</span><span class="sxs-lookup"><span data-stu-id="fab33-292">bit</span></span></p></td>
<td><p><span data-ttu-id="fab33-293">Указывает, подключен ли вызывающий абонент к виртуальной частной сети.</span><span class="sxs-lookup"><span data-stu-id="fab33-293">Indicates whether or not the caller connected over a virtual private network.</span></span> <span data-ttu-id="fab33-294">1 — это виртуальная частная сеть (VPN), а 0 — не VPN.</span><span class="sxs-lookup"><span data-stu-id="fab33-294">1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fab33-295">каллерлинкспид</span><span class="sxs-lookup"><span data-stu-id="fab33-295">CallerLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="fab33-296">десятичное число (18;)</span><span class="sxs-lookup"><span data-stu-id="fab33-296">decimal(18,)</span></span></p></td>
<td><p><span data-ttu-id="fab33-297">Скорость сетевого соединения для конечной точки вызывающего абонента бит/с.</span><span class="sxs-lookup"><span data-stu-id="fab33-297">Network link speed for the caller's endpoint in bps.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fab33-298">каллинетворкконнектионтипе</span><span class="sxs-lookup"><span data-stu-id="fab33-298">CalleeNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="fab33-299">tinyint</span><span class="sxs-lookup"><span data-stu-id="fab33-299">tinyint</span></span></p></td>
<td><p><span data-ttu-id="fab33-300">Тип сетевого подключения абонента: 0 – проводное, 1 — Беспроводная связь.</span><span class="sxs-lookup"><span data-stu-id="fab33-300">Callee’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fab33-301">калливпн</span><span class="sxs-lookup"><span data-stu-id="fab33-301">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="fab33-302">бит</span><span class="sxs-lookup"><span data-stu-id="fab33-302">bit</span></span></p></td>
<td><p><span data-ttu-id="fab33-303">Указывает, подсоединен ли вызывающий абонент к виртуальной частной сети.</span><span class="sxs-lookup"><span data-stu-id="fab33-303">Indicates whether or not the callee connected over a virtual private network.</span></span> <span data-ttu-id="fab33-304">1 — это виртуальная частная сеть (VPN), а 0 — не VPN.</span><span class="sxs-lookup"><span data-stu-id="fab33-304">1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fab33-305">каллилинкспид</span><span class="sxs-lookup"><span data-stu-id="fab33-305">CalleeLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="fab33-306">десятичное число (18; 0)</span><span class="sxs-lookup"><span data-stu-id="fab33-306">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="fab33-307">Скорость сетевого соединения для конечной точки вызываемого абонента (бит/с).</span><span class="sxs-lookup"><span data-stu-id="fab33-307">Network link speed for the callee’s endpoint (in bps).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fab33-308">конверсатионалмос</span><span class="sxs-lookup"><span data-stu-id="fab33-308">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="fab33-309">десятичное число (3, 2)</span><span class="sxs-lookup"><span data-stu-id="fab33-309">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="fab33-310">Нарровбанд MOS из сеансов голосовой связи (на основе обоих звуковых потоков).</span><span class="sxs-lookup"><span data-stu-id="fab33-310">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fab33-311">апплиедбандвидслимит</span><span class="sxs-lookup"><span data-stu-id="fab33-311">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="fab33-312">целое</span><span class="sxs-lookup"><span data-stu-id="fab33-312">int</span></span></p></td>
<td><p><span data-ttu-id="fab33-313">Реальная пропускная способность, примененная к потоку отправки данных в соответствии с различными параметрами политики (например, "повернуть", "API", SDP, сервер политики и т. д.).</span><span class="sxs-lookup"><span data-stu-id="fab33-313">Actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on).</span></span> <span data-ttu-id="fab33-314">Это не следует путать с эффективной пропускной способностью, так как в зависимости от оценки пропускной способности может снизиться эффективная пропускная способность.</span><span class="sxs-lookup"><span data-stu-id="fab33-314">This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate.</span></span> <span data-ttu-id="fab33-315">Это является, по сути, максимальной пропускной способностью потока отправки, который может занимать ограничения пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="fab33-315">This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fab33-316">JitterInterArrival</span><span class="sxs-lookup"><span data-stu-id="fab33-316">JitterInterArrival</span></span></p></td>
<td><p><span data-ttu-id="fab33-317">целое</span><span class="sxs-lookup"><span data-stu-id="fab33-317">int</span></span></p></td>
<td><p><span data-ttu-id="fab33-318">Средняя колебание сети из статистики протокола управления временем в реальном времени (РТКП).</span><span class="sxs-lookup"><span data-stu-id="fab33-318">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fab33-319">життеринтерарривалмакс</span><span class="sxs-lookup"><span data-stu-id="fab33-319">JitterInterArrivalMax</span></span></p></td>
<td><p><span data-ttu-id="fab33-320">целое</span><span class="sxs-lookup"><span data-stu-id="fab33-320">int</span></span></p></td>
<td><p><span data-ttu-id="fab33-321">Максимальная колебание сети во время звонка.</span><span class="sxs-lookup"><span data-stu-id="fab33-321">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fab33-322">RoundTrip</span><span class="sxs-lookup"><span data-stu-id="fab33-322">RoundTrip</span></span></p></td>
<td><p><span data-ttu-id="fab33-323">целое</span><span class="sxs-lookup"><span data-stu-id="fab33-323">int</span></span></p></td>
<td><p><span data-ttu-id="fab33-324">Время кругового приема из статистики РТКП.</span><span class="sxs-lookup"><span data-stu-id="fab33-324">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fab33-325">раундтрипмакс</span><span class="sxs-lookup"><span data-stu-id="fab33-325">RoundTripMax</span></span></p></td>
<td><p><span data-ttu-id="fab33-326">целое</span><span class="sxs-lookup"><span data-stu-id="fab33-326">int</span></span></p></td>
<td><p><span data-ttu-id="fab33-327">Максимальное время кругового приема для звукового потока.</span><span class="sxs-lookup"><span data-stu-id="fab33-327">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fab33-328">PacketLossRate</span><span class="sxs-lookup"><span data-stu-id="fab33-328">PacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="fab33-329">десятичное число (5; 4)</span><span class="sxs-lookup"><span data-stu-id="fab33-329">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="fab33-330">Средняя скорость потерь пакетов во время звонка.</span><span class="sxs-lookup"><span data-stu-id="fab33-330">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fab33-331">паккетлоссратемакс</span><span class="sxs-lookup"><span data-stu-id="fab33-331">PacketLossRateMax</span></span></p></td>
<td><p><span data-ttu-id="fab33-332">десятичное число (5; 4)</span><span class="sxs-lookup"><span data-stu-id="fab33-332">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="fab33-333">Максимальное количество потерь пакетов, замеченное во время звонка.</span><span class="sxs-lookup"><span data-stu-id="fab33-333">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fab33-334">паккетутилизатион</span><span class="sxs-lookup"><span data-stu-id="fab33-334">PacketUtilization</span></span></p></td>
<td><p><span data-ttu-id="fab33-335">целое</span><span class="sxs-lookup"><span data-stu-id="fab33-335">int</span></span></p></td>
<td><p><span data-ttu-id="fab33-336">Число пакетов для видеопотока (транспортный протокол в реальном времени).</span><span class="sxs-lookup"><span data-stu-id="fab33-336">Packet count for the video stream (Real Time Transport Protocol, RTP).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fab33-337">Самый пропускная способность</span><span class="sxs-lookup"><span data-stu-id="fab33-337">BandwidthEst</span></span></p></td>
<td><p><span data-ttu-id="fab33-338">целое</span><span class="sxs-lookup"><span data-stu-id="fab33-338">int</span></span></p></td>
<td><p><span data-ttu-id="fab33-339">Оценка пропускной способности для аудиопотока.</span><span class="sxs-lookup"><span data-stu-id="fab33-339">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fab33-340">PayloadDescription</span><span class="sxs-lookup"><span data-stu-id="fab33-340">PayloadDescription</span></span></p></td>
<td><p><span data-ttu-id="fab33-341">целое</span><span class="sxs-lookup"><span data-stu-id="fab33-341">int</span></span></p></td>
<td><p><span data-ttu-id="fab33-342">Аудиокодек, использованный для звонка, указан из <a href="lync-server-2013-payloaddescription-table.md">таблицы пайлоаддескриптион в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="fab33-342">Audio codec used for the call, referenced from the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fab33-343">видеоресолутион</span><span class="sxs-lookup"><span data-stu-id="fab33-343">VideoResolution</span></span></p></td>
<td><p><span data-ttu-id="fab33-344">char (9)</span><span class="sxs-lookup"><span data-stu-id="fab33-344">char(9)</span></span></p></td>
<td><p><span data-ttu-id="fab33-345">Разрешение видео в пикселях, умноженное на высоту в пикселях.</span><span class="sxs-lookup"><span data-stu-id="fab33-345">Resolution of the video in pixels width multiplied by pixels height.</span></span> <span data-ttu-id="fab33-346">Отображается в виде строки.</span><span class="sxs-lookup"><span data-stu-id="fab33-346">Reported as a string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fab33-347">видеобитратеавг</span><span class="sxs-lookup"><span data-stu-id="fab33-347">VideoBitRateAvg</span></span></p></td>
<td><p><span data-ttu-id="fab33-348">целое</span><span class="sxs-lookup"><span data-stu-id="fab33-348">int</span></span></p></td>
<td><p><span data-ttu-id="fab33-349">Средняя скорость потока видео.</span><span class="sxs-lookup"><span data-stu-id="fab33-349">Average bit rate of the video stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fab33-350">инбаундвидеофрамератеавг</span><span class="sxs-lookup"><span data-stu-id="fab33-350">InboundVideoFrameRateAvg</span></span></p></td>
<td><p><span data-ttu-id="fab33-351">десятичное число (9; 4)</span><span class="sxs-lookup"><span data-stu-id="fab33-351">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="fab33-352">Частота кадров, полученных в видеоролике.</span><span class="sxs-lookup"><span data-stu-id="fab33-352">Frame rate of video received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fab33-353">аутбаундвидеофрамератеавг</span><span class="sxs-lookup"><span data-stu-id="fab33-353">OutboundVideoFrameRateAvg</span></span></p></td>
<td><p><span data-ttu-id="fab33-354">десятичное число (9; 4)</span><span class="sxs-lookup"><span data-stu-id="fab33-354">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="fab33-355">Частота кадров, отправленных видео.</span><span class="sxs-lookup"><span data-stu-id="fab33-355">Frame rate of video sent.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fab33-356">виидеобитратемакс</span><span class="sxs-lookup"><span data-stu-id="fab33-356">ViideoBitRateMax</span></span></p></td>
<td><p><span data-ttu-id="fab33-357">целое</span><span class="sxs-lookup"><span data-stu-id="fab33-357">int</span></span></p></td>
<td><p><span data-ttu-id="fab33-358">Максимальная скорость видеосигнала во время видеосеанса.</span><span class="sxs-lookup"><span data-stu-id="fab33-358">Maximum video bit rate during the video session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fab33-359">видеопаккетлоссрате</span><span class="sxs-lookup"><span data-stu-id="fab33-359">VideoPacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="fab33-360">десятичное число (9; 4)</span><span class="sxs-lookup"><span data-stu-id="fab33-360">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="fab33-361">Частота потери видеопакетов.</span><span class="sxs-lookup"><span data-stu-id="fab33-361">Rate at which video packets were lost.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fab33-362">видеофрамелоссрате</span><span class="sxs-lookup"><span data-stu-id="fab33-362">VideoFrameLossRate</span></span></p></td>
<td><p><span data-ttu-id="fab33-363">Decimal (9.4)</span><span class="sxs-lookup"><span data-stu-id="fab33-363">decimal(9.4)</span></span></p></td>
<td><p><span data-ttu-id="fab33-364">Процент от общего числа потерянных кадров видео.</span><span class="sxs-lookup"><span data-stu-id="fab33-364">Percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fab33-365">видеофек</span><span class="sxs-lookup"><span data-stu-id="fab33-365">VideoFEC</span></span></p></td>
<td><p><span data-ttu-id="fab33-366">бит</span><span class="sxs-lookup"><span data-stu-id="fab33-366">bit</span></span></p></td>
<td><p><span data-ttu-id="fab33-367">Не используется.</span><span class="sxs-lookup"><span data-stu-id="fab33-367">Not used.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fab33-368">видеоаллокатебвавг</span><span class="sxs-lookup"><span data-stu-id="fab33-368">VideoAllocateBWAvg</span></span></p></td>
<td><p><span data-ttu-id="fab33-369">целое</span><span class="sxs-lookup"><span data-stu-id="fab33-369">int</span></span></p></td>
<td><p><span data-ttu-id="fab33-370">Средний объем пропускной способности, выделенной для видео.</span><span class="sxs-lookup"><span data-stu-id="fab33-370">Average amount of bandwidth allocated for video.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fab33-371">VideoLocalFrameLossPercentageAvg</span><span class="sxs-lookup"><span data-stu-id="fab33-371">VideoLocalFrameLossPercentageAvg</span></span></p></td>
<td><p><span data-ttu-id="fab33-372">Decimal (9.4)</span><span class="sxs-lookup"><span data-stu-id="fab33-372">decimal(9.4)</span></span></p></td>
<td><p><span data-ttu-id="fab33-373">Процент от общего количества кадров видео, которые были утрачены.</span><span class="sxs-lookup"><span data-stu-id="fab33-373">Percentage of total video frames that were lost.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fab33-374">сендерискаллерпаи</span><span class="sxs-lookup"><span data-stu-id="fab33-374">SenderIsCallerPAI</span></span></p></td>
<td><p><span data-ttu-id="fab33-375">бит</span><span class="sxs-lookup"><span data-stu-id="fab33-375">bit</span></span></p></td>
<td><p><span data-ttu-id="fab33-376">Направление потока для идентификационной информации, утвержденной p.</span><span class="sxs-lookup"><span data-stu-id="fab33-376">Stream direction for p-asserted identity information.</span></span> <span data-ttu-id="fab33-377">1 — направление потока на вызываемый абонентом. 0 — направление потока из вызываемого объекта вызывающему абоненту.</span><span class="sxs-lookup"><span data-stu-id="fab33-377">1 means the stream direction is from the caller to the callee; 0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

