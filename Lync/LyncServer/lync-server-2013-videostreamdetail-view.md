---
title: 'Lync Server 2013: представление Видеостреамдетаил'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: VideoStreamDetail view
ms:assetid: ec8c45e1-307d-40ec-a75e-6083306105f2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721928(v=OCS.15)
ms:contentKeyID: 49733863
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 95cc003a0e136a4a4c123355548b95c9566b4b31
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849174"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="videostreamdetail-view-in-lync-server-2013"></a><span data-ttu-id="209ae-102">Видеостреамдетаил представления в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="209ae-102">VideoStreamDetail view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="209ae-103">_**Тема последнего изменения:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="209ae-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="209ae-104">В представлении Видеостреамдетаил хранятся сведения о каждом видеопотоке в базе данных.</span><span class="sxs-lookup"><span data-stu-id="209ae-104">The VideoStreamDetail View stores information about each video stream in the database.</span></span> <span data-ttu-id="209ae-105">Это представление было представлено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="209ae-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="209ae-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="209ae-106">Column</span></span></th>
<th><span data-ttu-id="209ae-107">Тип данных</span><span class="sxs-lookup"><span data-stu-id="209ae-107">Data Type</span></span></th>
<th><span data-ttu-id="209ae-108">Описание</span><span class="sxs-lookup"><span data-stu-id="209ae-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="209ae-109">Сессионтиме</span><span class="sxs-lookup"><span data-stu-id="209ae-109">SessionTime</span></span></p></td>
<td><p><span data-ttu-id="209ae-110">datetime</span><span class="sxs-lookup"><span data-stu-id="209ae-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="209ae-111">На которую ссылается <a href="lync-server-2013-medialine-table.md">Таблица медиалине в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="209ae-111">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="209ae-112">Сессионсек</span><span class="sxs-lookup"><span data-stu-id="209ae-112">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="209ae-113">целое</span><span class="sxs-lookup"><span data-stu-id="209ae-113">int</span></span></p></td>
<td><p><span data-ttu-id="209ae-114">На которую ссылается <a href="lync-server-2013-medialine-table.md">Таблица медиалине в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="209ae-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="209ae-115">Медиалинелабел</span><span class="sxs-lookup"><span data-stu-id="209ae-115">MediaLineLabel</span></span></p></td>
<td><p><span data-ttu-id="209ae-116">tinyint</span><span class="sxs-lookup"><span data-stu-id="209ae-116">tinyint</span></span></p></td>
<td><p><span data-ttu-id="209ae-117">На которую ссылается <a href="lync-server-2013-medialine-table.md">Таблица медиалине в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="209ae-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="209ae-118">Стреамид</span><span class="sxs-lookup"><span data-stu-id="209ae-118">StreamId</span></span></p></td>
<td><p><span data-ttu-id="209ae-119">целое</span><span class="sxs-lookup"><span data-stu-id="209ae-119">int</span></span></p></td>
<td><p><span data-ttu-id="209ae-120">Уникальный идентификатор в строке мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="209ae-120">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="209ae-121">StartTime</span><span class="sxs-lookup"><span data-stu-id="209ae-121">StartTime</span></span></p></td>
<td><p><span data-ttu-id="209ae-122">datetime</span><span class="sxs-lookup"><span data-stu-id="209ae-122">datetime</span></span></p></td>
<td><p><span data-ttu-id="209ae-123">Время начала сеанса.</span><span class="sxs-lookup"><span data-stu-id="209ae-123">Start time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="209ae-124">EndTime</span><span class="sxs-lookup"><span data-stu-id="209ae-124">EndTime</span></span></p></td>
<td><p><span data-ttu-id="209ae-125">datetime</span><span class="sxs-lookup"><span data-stu-id="209ae-125">datetime</span></span></p></td>
<td><p><span data-ttu-id="209ae-126">Время окончания сеанса.</span><span class="sxs-lookup"><span data-stu-id="209ae-126">End time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="209ae-127">Каллприорити</span><span class="sxs-lookup"><span data-stu-id="209ae-127">CallPriority</span></span></p></td>
<td><p><span data-ttu-id="209ae-128">целое</span><span class="sxs-lookup"><span data-stu-id="209ae-128">int</span></span></p></td>
<td><p><span data-ttu-id="209ae-129">Приоритет звонка.</span><span class="sxs-lookup"><span data-stu-id="209ae-129">Priority of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="209ae-130">Каллерпул</span><span class="sxs-lookup"><span data-stu-id="209ae-130">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="209ae-131">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="209ae-131">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="209ae-132">Полное доменное имя пула вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="209ae-132">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="209ae-133">Каллипул</span><span class="sxs-lookup"><span data-stu-id="209ae-133">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="209ae-134">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="209ae-134">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="209ae-135">Полное доменное имя пула вызываемых абонентов.</span><span class="sxs-lookup"><span data-stu-id="209ae-135">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="209ae-136">Вызывающая сторона</span><span class="sxs-lookup"><span data-stu-id="209ae-136">Caller</span></span></p></td>
<td><p><span data-ttu-id="209ae-137">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="209ae-137">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="209ae-138">URI вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="209ae-138">Caller’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="209ae-139">Вызываемая сторона</span><span class="sxs-lookup"><span data-stu-id="209ae-139">Callee</span></span></p></td>
<td><p><span data-ttu-id="209ae-140">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="209ae-140">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="209ae-141">Универсальный код ресурса (URI) вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="209ae-141">Callee’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="209ae-142">Каллерусеражент</span><span class="sxs-lookup"><span data-stu-id="209ae-142">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="209ae-143">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="209ae-143">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="209ae-144">Строка агента пользователя вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="209ae-144">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="209ae-145">Каллерусераженттипе</span><span class="sxs-lookup"><span data-stu-id="209ae-145">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="209ae-146">smallint</span><span class="sxs-lookup"><span data-stu-id="209ae-146">smallint</span></span></p></td>
<td><p><span data-ttu-id="209ae-147">Тип агента пользователя вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="209ae-147">Type of caller’s user agent.</span></span> <span data-ttu-id="209ae-148">Дополнительные сведения: <a href="lync-server-2013-useragent-table.md">Таблица UserAgent в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="209ae-148">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="209ae-149">Каллерусераженткатегори</span><span class="sxs-lookup"><span data-stu-id="209ae-149">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="209ae-150">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="209ae-150">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="209ae-151">Категория агента пользователя вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="209ae-151">Category of caller’s user agent.</span></span> <span data-ttu-id="209ae-152">Дополнительные сведения <a href="lync-server-2013-useragentdef-table-qoe.md">усеражентдеф в таблице "QoE" в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="209ae-152">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="209ae-153">Каллиусеражент</span><span class="sxs-lookup"><span data-stu-id="209ae-153">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="209ae-154">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="209ae-154">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="209ae-155">Строка агента пользователя вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="209ae-155">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="209ae-156">Каллиусераженттипе</span><span class="sxs-lookup"><span data-stu-id="209ae-156">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="209ae-157">smallint</span><span class="sxs-lookup"><span data-stu-id="209ae-157">smallint</span></span></p></td>
<td><p><span data-ttu-id="209ae-158">Тип агента пользователя, вызываемого абонентом.</span><span class="sxs-lookup"><span data-stu-id="209ae-158">Type of callee’s user agent.</span></span> <span data-ttu-id="209ae-159">Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-useragent-table.md">таблицей UserAgent в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="209ae-159">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="209ae-160">Каллиусераженткатегори</span><span class="sxs-lookup"><span data-stu-id="209ae-160">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="209ae-161">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="209ae-161">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="209ae-162">Категория агента пользователя вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="209ae-162">Category of callee’s user agent.</span></span> <span data-ttu-id="209ae-163">Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-useragentdef-table-qoe.md">таблицей усеражентдеф (QoE) в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="209ae-163">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="209ae-164">Каллерендпоинт</span><span class="sxs-lookup"><span data-stu-id="209ae-164">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="209ae-165">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="209ae-165">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="209ae-166">Имя конечной точки вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="209ae-166">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="209ae-167">Каллиендпоинт</span><span class="sxs-lookup"><span data-stu-id="209ae-167">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="209ae-168">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="209ae-168">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="209ae-169">Имя конечной точки вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="209ae-169">Callee’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="209ae-170">Каллерос</span><span class="sxs-lookup"><span data-stu-id="209ae-170">CallerOS</span></span></p></td>
<td><p><span data-ttu-id="209ae-171">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="209ae-171">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="209ae-172">Операционная система (ОС) конечной точки вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="209ae-172">Operating system (OS) of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="209ae-173">Каллиос</span><span class="sxs-lookup"><span data-stu-id="209ae-173">CalleeOS</span></span></p></td>
<td><p><span data-ttu-id="209ae-174">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="209ae-174">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="209ae-175">Операционная система (ОС) конечной точки вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="209ae-175">Operating system (OS) of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="209ae-176">Каллеркпунаме</span><span class="sxs-lookup"><span data-stu-id="209ae-176">CallerCPUName</span></span></p></td>
<td><p><span data-ttu-id="209ae-177">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="209ae-177">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="209ae-178">Имя ЦП конечной точки вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="209ae-178">CPU name of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="209ae-179">Калликпунаме</span><span class="sxs-lookup"><span data-stu-id="209ae-179">CalleeCPUName</span></span></p></td>
<td><p><span data-ttu-id="209ae-180">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="209ae-180">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="209ae-181">Имя ЦП конечной точки вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="209ae-181">CPU name of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="209ae-182">Каллеркпунумберофкорес</span><span class="sxs-lookup"><span data-stu-id="209ae-182">CallerCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="209ae-183">smallint</span><span class="sxs-lookup"><span data-stu-id="209ae-183">smallint</span></span></p></td>
<td><p><span data-ttu-id="209ae-184">Количество ядер ЦП конечной точки вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="209ae-184">Number of CPU cores of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="209ae-185">Калликпунумберофкорес</span><span class="sxs-lookup"><span data-stu-id="209ae-185">CalleeCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="209ae-186">smallint</span><span class="sxs-lookup"><span data-stu-id="209ae-186">smallint</span></span></p></td>
<td><p><span data-ttu-id="209ae-187">Количество ядер ЦП конечной точки вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="209ae-187">Number of CPU cores of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="209ae-188">Каллеркпупроцессорспид</span><span class="sxs-lookup"><span data-stu-id="209ae-188">CallerCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="209ae-189">целое</span><span class="sxs-lookup"><span data-stu-id="209ae-189">int</span></span></p></td>
<td><p><span data-ttu-id="209ae-190">Частота процессора конечной точки вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="209ae-190">CPU processor speed of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="209ae-191">Калликпупроцессорспид</span><span class="sxs-lookup"><span data-stu-id="209ae-191">CalleeCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="209ae-192">целое</span><span class="sxs-lookup"><span data-stu-id="209ae-192">int</span></span></p></td>
<td><p><span data-ttu-id="209ae-193">Тактовая частота процессора на конечной точке вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="209ae-193">CPU processor speed of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="209ae-194">Каллервиртуализатионфлаг</span><span class="sxs-lookup"><span data-stu-id="209ae-194">CallerVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="209ae-195">tinyint</span><span class="sxs-lookup"><span data-stu-id="209ae-195">tinyint</span></span></p></td>
<td><p><span data-ttu-id="209ae-196">Указывает, работает ли система вызывающего абонента в виртуализованной среде.</span><span class="sxs-lookup"><span data-stu-id="209ae-196">Indicates whether the caller’s system is running in a virtualized environment.</span></span> <span data-ttu-id="209ae-197">Дополнительные сведения приведены <a href="lync-server-2013-endpoint-table.md">в таблице конечная точка в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="209ae-197">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="209ae-198">Калливиртуализатионфлаг</span><span class="sxs-lookup"><span data-stu-id="209ae-198">CalleeVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="209ae-199">tinyint</span><span class="sxs-lookup"><span data-stu-id="209ae-199">tinyint</span></span></p></td>
<td><p><span data-ttu-id="209ae-200">Указывает, работает ли система вызываемого абонента в виртуализованной среде.</span><span class="sxs-lookup"><span data-stu-id="209ae-200">Indicates whether the callee’s system is running in a virtualized environment.</span></span> <span data-ttu-id="209ae-201">Дополнительные сведения приведены <a href="lync-server-2013-endpoint-table.md">в таблице конечная точка в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="209ae-201">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="209ae-202">Коннективитице</span><span class="sxs-lookup"><span data-stu-id="209ae-202">ConnectivityIce</span></span></p></td>
<td><p><span data-ttu-id="209ae-203">tinyint</span><span class="sxs-lookup"><span data-stu-id="209ae-203">tinyint</span></span></p></td>
<td><p><span data-ttu-id="209ae-204">Сведения о пути к носителю, например прямая или ретранслируемая.</span><span class="sxs-lookup"><span data-stu-id="209ae-204">Information about media path, such as direct or relayed.</span></span> <span data-ttu-id="209ae-205">Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-medialine-table.md">таблицей медиалине в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="209ae-205">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="209ae-206">Каллерицеварнингфлагс</span><span class="sxs-lookup"><span data-stu-id="209ae-206">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="209ae-207">целое</span><span class="sxs-lookup"><span data-stu-id="209ae-207">int</span></span></p></td>
<td><p><span data-ttu-id="209ae-208">Сведения о процессе интерактивной установки подключения (ICE), описанные в разделе Флаги BITS для вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="209ae-208">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller.</span></span> <span data-ttu-id="209ae-209">Подробности можно найти в спецификации серверного протокола контроля качества обслуживания.</span><span class="sxs-lookup"><span data-stu-id="209ae-209">For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="209ae-210">Каллиицеварнингфлагс</span><span class="sxs-lookup"><span data-stu-id="209ae-210">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="209ae-211">целое</span><span class="sxs-lookup"><span data-stu-id="209ae-211">int</span></span></p></td>
<td><p><span data-ttu-id="209ae-212">Сведения о процессе установки интерактивной связи (ICE), описанные в флагах BITS для вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="209ae-212">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee.</span></span> <span data-ttu-id="209ae-213">Подробности можно найти в спецификации серверного протокола контроля качества обслуживания.</span><span class="sxs-lookup"><span data-stu-id="209ae-213">For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="209ae-214">Transport</span><span class="sxs-lookup"><span data-stu-id="209ae-214">Transport</span></span></p></td>
<td><p><span data-ttu-id="209ae-215">целое</span><span class="sxs-lookup"><span data-stu-id="209ae-215">int</span></span></p></td>
<td><p><span data-ttu-id="209ae-216">Тип транспорта: 0 — UDP, 1 — TCP.</span><span class="sxs-lookup"><span data-stu-id="209ae-216">Transport type: 0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="209ae-217">Каллерипаддр</span><span class="sxs-lookup"><span data-stu-id="209ae-217">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="209ae-218">var (50)</span><span class="sxs-lookup"><span data-stu-id="209ae-218">var(50)</span></span></p></td>
<td><p><span data-ttu-id="209ae-219">IP-адрес вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="209ae-219">IP address of the caller.</span></span> <span data-ttu-id="209ae-220">Это может быть либо IPv4, либо IPv6-адрес.</span><span class="sxs-lookup"><span data-stu-id="209ae-220">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="209ae-221">Каллерпорт</span><span class="sxs-lookup"><span data-stu-id="209ae-221">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="209ae-222">целое</span><span class="sxs-lookup"><span data-stu-id="209ae-222">int</span></span></p></td>
<td><p><span data-ttu-id="209ae-223">Порт, используемый вызывающим абонентом.</span><span class="sxs-lookup"><span data-stu-id="209ae-223">Port used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="209ae-224">Каллеринсиде</span><span class="sxs-lookup"><span data-stu-id="209ae-224">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="209ae-225">бит</span><span class="sxs-lookup"><span data-stu-id="209ae-225">bit</span></span></p></td>
<td><p><span data-ttu-id="209ae-226">Указывает, находится ли вызывающий абонент в сети Организации.</span><span class="sxs-lookup"><span data-stu-id="209ae-226">Indicates whether the caller is inside the organization network.</span></span> <span data-ttu-id="209ae-227">1 означает, что вызывающий абонент входит в корпоративную сеть, а 0 означает, что вызывающий абонент находится за пределами сети.</span><span class="sxs-lookup"><span data-stu-id="209ae-227">1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="209ae-228">Каллиипаддр</span><span class="sxs-lookup"><span data-stu-id="209ae-228">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="209ae-229">var (50)</span><span class="sxs-lookup"><span data-stu-id="209ae-229">var(50)</span></span></p></td>
<td><p><span data-ttu-id="209ae-230">IP-адрес вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="209ae-230">IP address of the callee.</span></span> <span data-ttu-id="209ae-231">Это может быть либо IPv4, либо IPv6-адрес.</span><span class="sxs-lookup"><span data-stu-id="209ae-231">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="209ae-232">Каллипорт</span><span class="sxs-lookup"><span data-stu-id="209ae-232">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="209ae-233">целое</span><span class="sxs-lookup"><span data-stu-id="209ae-233">int</span></span></p></td>
<td><p><span data-ttu-id="209ae-234">Порт, используемый вызываемым абонентом.</span><span class="sxs-lookup"><span data-stu-id="209ae-234">Port used by the callee.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="209ae-235">Каллиинсиде</span><span class="sxs-lookup"><span data-stu-id="209ae-235">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="209ae-236">бит</span><span class="sxs-lookup"><span data-stu-id="209ae-236">bit</span></span></p></td>
<td><p><span data-ttu-id="209ae-237">Указывает, входит ли вызывающий объект в сеть Организации. 1 означает вызываемый абонент в корпоративной сети, 0 означает, что вызываемый абонент находится за пределами сети.</span><span class="sxs-lookup"><span data-stu-id="209ae-237">Indicates whether the caller is inside the organization network.1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="209ae-238">Каллерусерсите</span><span class="sxs-lookup"><span data-stu-id="209ae-238">CallerUserSite</span></span></p></td>
<td><p><span data-ttu-id="209ae-239">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="209ae-239">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="209ae-240">Имя сайта вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="209ae-240">Name of the caller’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="209ae-241">Каллеррегион</span><span class="sxs-lookup"><span data-stu-id="209ae-241">CallerRegion</span></span></p></td>
<td><p><span data-ttu-id="209ae-242">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="209ae-242">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="209ae-243">Название страны или региона сайта вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="209ae-243">Name of the country/region of the caller’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="209ae-244">Каллиусерсите</span><span class="sxs-lookup"><span data-stu-id="209ae-244">CalleeUserSite</span></span></p></td>
<td><p><span data-ttu-id="209ae-245">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="209ae-245">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="209ae-246">Имя сайта вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="209ae-246">Name of the callee’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="209ae-247">Каллирегион</span><span class="sxs-lookup"><span data-stu-id="209ae-247">CalleeRegion</span></span></p></td>
<td><p><span data-ttu-id="209ae-248">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="209ae-248">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="209ae-249">Название страны или региона сайта вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="209ae-249">Name of the country/region of the callee’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="209ae-250">Каллеррелайипаддр</span><span class="sxs-lookup"><span data-stu-id="209ae-250">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="209ae-251">var (50)</span><span class="sxs-lookup"><span data-stu-id="209ae-251">var(50)</span></span></p></td>
<td><p><span data-ttu-id="209ae-252">IP-адрес службы EDGE (/V), используемой вызывающим абонентом.</span><span class="sxs-lookup"><span data-stu-id="209ae-252">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="209ae-253">Дополнительные сведения приведены в <a href="lync-server-2013-ipaddress-table.md">таблице IP-адрес в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="209ae-253">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="209ae-254">Каллеррелайпорт</span><span class="sxs-lookup"><span data-stu-id="209ae-254">CallerRelayPort</span></span></p></td>
<td><p><span data-ttu-id="209ae-255">целое</span><span class="sxs-lookup"><span data-stu-id="209ae-255">int</span></span></p></td>
<td><p><span data-ttu-id="209ae-256">Порт для службы EDGE (A/V), используемой вызывающим абонентом.</span><span class="sxs-lookup"><span data-stu-id="209ae-256">Port on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="209ae-257">Каллирелайипаддр</span><span class="sxs-lookup"><span data-stu-id="209ae-257">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="209ae-258">var (50)</span><span class="sxs-lookup"><span data-stu-id="209ae-258">var(50)</span></span></p></td>
<td><p><span data-ttu-id="209ae-259">Ключ IP-адреса для службы EDGE (/V), используемой вызываемым абонентом.</span><span class="sxs-lookup"><span data-stu-id="209ae-259">IP Address key of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="209ae-260">Дополнительные сведения приведены в <a href="lync-server-2013-ipaddress-table.md">таблице IP-адрес в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="209ae-260">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="209ae-261">Каллирелайпорт</span><span class="sxs-lookup"><span data-stu-id="209ae-261">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="209ae-262">целое</span><span class="sxs-lookup"><span data-stu-id="209ae-262">int</span></span></p></td>
<td><p><span data-ttu-id="209ae-263">Порт для службы EDGE (A/V), используемой вызываемым абонентом.</span><span class="sxs-lookup"><span data-stu-id="209ae-263">Port on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="209ae-264">Каллеркаптуредев</span><span class="sxs-lookup"><span data-stu-id="209ae-264">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="209ae-265">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="209ae-265">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="209ae-266">Имя устройства захвата вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="209ae-266">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="209ae-267">Каллеррендердев</span><span class="sxs-lookup"><span data-stu-id="209ae-267">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="209ae-268">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="209ae-268">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="209ae-269">Имя устройства отрисовки вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="209ae-269">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="209ae-270">Каллеркаптуредевдривер</span><span class="sxs-lookup"><span data-stu-id="209ae-270">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="209ae-271">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="209ae-271">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="209ae-272">Имя драйвера устройства захвата вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="209ae-272">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="209ae-273">Каллеррендердевдривер</span><span class="sxs-lookup"><span data-stu-id="209ae-273">CallerRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="209ae-274">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="209ae-274">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="209ae-275">Имя драйвера устройства отрисовки вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="209ae-275">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="209ae-276">Калликаптуредев</span><span class="sxs-lookup"><span data-stu-id="209ae-276">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="209ae-277">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="209ae-277">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="209ae-278">Имя устройства захвата абонента.</span><span class="sxs-lookup"><span data-stu-id="209ae-278">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="209ae-279">Каллирендердев</span><span class="sxs-lookup"><span data-stu-id="209ae-279">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="209ae-280">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="209ae-280">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="209ae-281">Имя устройства отрисовки вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="209ae-281">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="209ae-282">Каллекаптуредевдривер</span><span class="sxs-lookup"><span data-stu-id="209ae-282">CalleCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="209ae-283">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="209ae-283">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="209ae-284">Имя драйвера устройства захвата абонента.</span><span class="sxs-lookup"><span data-stu-id="209ae-284">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="209ae-285">Каллирендердевдривер</span><span class="sxs-lookup"><span data-stu-id="209ae-285">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="209ae-286">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="209ae-286">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="209ae-287">Имя драйвера устройства обработки вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="209ae-287">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="209ae-288">Каллернетворкконнектионтипе</span><span class="sxs-lookup"><span data-stu-id="209ae-288">CallerNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="209ae-289">tinyint</span><span class="sxs-lookup"><span data-stu-id="209ae-289">tinyint</span></span></p></td>
<td><p><span data-ttu-id="209ae-290">Тип сетевого подключения вызывающего абонента: 0 проводное соединение, 1 — Беспроводная связь.</span><span class="sxs-lookup"><span data-stu-id="209ae-290">Caller’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="209ae-291">Каллервпн</span><span class="sxs-lookup"><span data-stu-id="209ae-291">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="209ae-292">бит</span><span class="sxs-lookup"><span data-stu-id="209ae-292">bit</span></span></p></td>
<td><p><span data-ttu-id="209ae-293">Указывает, подключен ли вызывающий абонент к виртуальной частной сети.</span><span class="sxs-lookup"><span data-stu-id="209ae-293">Indicates whether or not the caller connected over a virtual private network.</span></span> <span data-ttu-id="209ae-294">1 — это виртуальная частная сеть (VPN), а 0 — не VPN.</span><span class="sxs-lookup"><span data-stu-id="209ae-294">1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="209ae-295">Каллерлинкспид</span><span class="sxs-lookup"><span data-stu-id="209ae-295">CallerLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="209ae-296">десятичное число (18;)</span><span class="sxs-lookup"><span data-stu-id="209ae-296">decimal(18,)</span></span></p></td>
<td><p><span data-ttu-id="209ae-297">Скорость сетевого соединения для конечной точки вызывающего абонента бит/с.</span><span class="sxs-lookup"><span data-stu-id="209ae-297">Network link speed for the caller's endpoint in bps.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="209ae-298">Каллинетворкконнектионтипе</span><span class="sxs-lookup"><span data-stu-id="209ae-298">CalleeNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="209ae-299">tinyint</span><span class="sxs-lookup"><span data-stu-id="209ae-299">tinyint</span></span></p></td>
<td><p><span data-ttu-id="209ae-300">Тип сетевого подключения абонента: 0 – проводное, 1 — Беспроводная связь.</span><span class="sxs-lookup"><span data-stu-id="209ae-300">Callee’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="209ae-301">Калливпн</span><span class="sxs-lookup"><span data-stu-id="209ae-301">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="209ae-302">бит</span><span class="sxs-lookup"><span data-stu-id="209ae-302">bit</span></span></p></td>
<td><p><span data-ttu-id="209ae-303">Указывает, подсоединен ли вызывающий абонент к виртуальной частной сети.</span><span class="sxs-lookup"><span data-stu-id="209ae-303">Indicates whether or not the callee connected over a virtual private network.</span></span> <span data-ttu-id="209ae-304">1 — это виртуальная частная сеть (VPN), а 0 — не VPN.</span><span class="sxs-lookup"><span data-stu-id="209ae-304">1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="209ae-305">Каллилинкспид</span><span class="sxs-lookup"><span data-stu-id="209ae-305">CalleeLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="209ae-306">десятичное число (18; 0)</span><span class="sxs-lookup"><span data-stu-id="209ae-306">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="209ae-307">Скорость сетевого соединения для конечной точки вызываемого абонента (бит/с).</span><span class="sxs-lookup"><span data-stu-id="209ae-307">Network link speed for the callee’s endpoint (in bps).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="209ae-308">Конверсатионалмос</span><span class="sxs-lookup"><span data-stu-id="209ae-308">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="209ae-309">десятичное число (3, 2)</span><span class="sxs-lookup"><span data-stu-id="209ae-309">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="209ae-310">Нарровбанд MOS из сеансов голосовой связи (на основе обоих звуковых потоков).</span><span class="sxs-lookup"><span data-stu-id="209ae-310">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="209ae-311">Апплиедбандвидслимит</span><span class="sxs-lookup"><span data-stu-id="209ae-311">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="209ae-312">целое</span><span class="sxs-lookup"><span data-stu-id="209ae-312">int</span></span></p></td>
<td><p><span data-ttu-id="209ae-313">Реальная пропускная способность, примененная к потоку отправки данных в соответствии с различными параметрами политики (например, "повернуть", "API", SDP, сервер политики и т. д.).</span><span class="sxs-lookup"><span data-stu-id="209ae-313">Actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on).</span></span> <span data-ttu-id="209ae-314">Это не следует путать с эффективной пропускной способностью, так как в зависимости от оценки пропускной способности может снизиться эффективная пропускная способность.</span><span class="sxs-lookup"><span data-stu-id="209ae-314">This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate.</span></span> <span data-ttu-id="209ae-315">Это является, по сути, максимальной пропускной способностью потока отправки, который может занимать ограничения пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="209ae-315">This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="209ae-316">JitterInterArrival</span><span class="sxs-lookup"><span data-stu-id="209ae-316">JitterInterArrival</span></span></p></td>
<td><p><span data-ttu-id="209ae-317">целое</span><span class="sxs-lookup"><span data-stu-id="209ae-317">int</span></span></p></td>
<td><p><span data-ttu-id="209ae-318">Средняя колебание сети из статистики протокола управления временем в реальном времени (РТКП).</span><span class="sxs-lookup"><span data-stu-id="209ae-318">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="209ae-319">Життеринтерарривалмакс</span><span class="sxs-lookup"><span data-stu-id="209ae-319">JitterInterArrivalMax</span></span></p></td>
<td><p><span data-ttu-id="209ae-320">целое</span><span class="sxs-lookup"><span data-stu-id="209ae-320">int</span></span></p></td>
<td><p><span data-ttu-id="209ae-321">Максимальная колебание сети во время звонка.</span><span class="sxs-lookup"><span data-stu-id="209ae-321">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="209ae-322">RoundTrip</span><span class="sxs-lookup"><span data-stu-id="209ae-322">RoundTrip</span></span></p></td>
<td><p><span data-ttu-id="209ae-323">целое</span><span class="sxs-lookup"><span data-stu-id="209ae-323">int</span></span></p></td>
<td><p><span data-ttu-id="209ae-324">Время кругового приема из статистики РТКП.</span><span class="sxs-lookup"><span data-stu-id="209ae-324">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="209ae-325">Раундтрипмакс</span><span class="sxs-lookup"><span data-stu-id="209ae-325">RoundTripMax</span></span></p></td>
<td><p><span data-ttu-id="209ae-326">целое</span><span class="sxs-lookup"><span data-stu-id="209ae-326">int</span></span></p></td>
<td><p><span data-ttu-id="209ae-327">Максимальное время кругового приема для звукового потока.</span><span class="sxs-lookup"><span data-stu-id="209ae-327">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="209ae-328">PacketLossRate</span><span class="sxs-lookup"><span data-stu-id="209ae-328">PacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="209ae-329">десятичное число (5; 4)</span><span class="sxs-lookup"><span data-stu-id="209ae-329">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="209ae-330">Средняя скорость потерь пакетов во время звонка.</span><span class="sxs-lookup"><span data-stu-id="209ae-330">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="209ae-331">Паккетлоссратемакс</span><span class="sxs-lookup"><span data-stu-id="209ae-331">PacketLossRateMax</span></span></p></td>
<td><p><span data-ttu-id="209ae-332">десятичное число (5; 4)</span><span class="sxs-lookup"><span data-stu-id="209ae-332">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="209ae-333">Максимальное количество потерь пакетов, замеченное во время звонка.</span><span class="sxs-lookup"><span data-stu-id="209ae-333">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="209ae-334">Паккетутилизатион</span><span class="sxs-lookup"><span data-stu-id="209ae-334">PacketUtilization</span></span></p></td>
<td><p><span data-ttu-id="209ae-335">целое</span><span class="sxs-lookup"><span data-stu-id="209ae-335">int</span></span></p></td>
<td><p><span data-ttu-id="209ae-336">Число пакетов для видеопотока (транспортный протокол в реальном времени).</span><span class="sxs-lookup"><span data-stu-id="209ae-336">Packet count for the video stream (Real Time Transport Protocol, RTP).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="209ae-337">Самый пропускная способность</span><span class="sxs-lookup"><span data-stu-id="209ae-337">BandwidthEst</span></span></p></td>
<td><p><span data-ttu-id="209ae-338">целое</span><span class="sxs-lookup"><span data-stu-id="209ae-338">int</span></span></p></td>
<td><p><span data-ttu-id="209ae-339">Оценка пропускной способности для аудиопотока.</span><span class="sxs-lookup"><span data-stu-id="209ae-339">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="209ae-340">PayloadDescription</span><span class="sxs-lookup"><span data-stu-id="209ae-340">PayloadDescription</span></span></p></td>
<td><p><span data-ttu-id="209ae-341">целое</span><span class="sxs-lookup"><span data-stu-id="209ae-341">int</span></span></p></td>
<td><p><span data-ttu-id="209ae-342">Аудиокодек, использованный для звонка, указан из <a href="lync-server-2013-payloaddescription-table.md">таблицы пайлоаддескриптион в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="209ae-342">Audio codec used for the call, referenced from the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="209ae-343">Видеоресолутион</span><span class="sxs-lookup"><span data-stu-id="209ae-343">VideoResolution</span></span></p></td>
<td><p><span data-ttu-id="209ae-344">char (9)</span><span class="sxs-lookup"><span data-stu-id="209ae-344">char(9)</span></span></p></td>
<td><p><span data-ttu-id="209ae-345">Разрешение видео в пикселях, умноженное на высоту в пикселях.</span><span class="sxs-lookup"><span data-stu-id="209ae-345">Resolution of the video in pixels width multiplied by pixels height.</span></span> <span data-ttu-id="209ae-346">Отображается в виде строки.</span><span class="sxs-lookup"><span data-stu-id="209ae-346">Reported as a string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="209ae-347">Видеобитратеавг</span><span class="sxs-lookup"><span data-stu-id="209ae-347">VideoBitRateAvg</span></span></p></td>
<td><p><span data-ttu-id="209ae-348">целое</span><span class="sxs-lookup"><span data-stu-id="209ae-348">int</span></span></p></td>
<td><p><span data-ttu-id="209ae-349">Средняя скорость потока видео.</span><span class="sxs-lookup"><span data-stu-id="209ae-349">Average bit rate of the video stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="209ae-350">Инбаундвидеофрамератеавг</span><span class="sxs-lookup"><span data-stu-id="209ae-350">InboundVideoFrameRateAvg</span></span></p></td>
<td><p><span data-ttu-id="209ae-351">десятичное число (9; 4)</span><span class="sxs-lookup"><span data-stu-id="209ae-351">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="209ae-352">Частота кадров, полученных в видеоролике.</span><span class="sxs-lookup"><span data-stu-id="209ae-352">Frame rate of video received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="209ae-353">Аутбаундвидеофрамератеавг</span><span class="sxs-lookup"><span data-stu-id="209ae-353">OutboundVideoFrameRateAvg</span></span></p></td>
<td><p><span data-ttu-id="209ae-354">десятичное число (9; 4)</span><span class="sxs-lookup"><span data-stu-id="209ae-354">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="209ae-355">Частота кадров, отправленных видео.</span><span class="sxs-lookup"><span data-stu-id="209ae-355">Frame rate of video sent.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="209ae-356">Виидеобитратемакс</span><span class="sxs-lookup"><span data-stu-id="209ae-356">ViideoBitRateMax</span></span></p></td>
<td><p><span data-ttu-id="209ae-357">целое</span><span class="sxs-lookup"><span data-stu-id="209ae-357">int</span></span></p></td>
<td><p><span data-ttu-id="209ae-358">Максимальная скорость видеосигнала во время видеосеанса.</span><span class="sxs-lookup"><span data-stu-id="209ae-358">Maximum video bit rate during the video session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="209ae-359">Видеопаккетлоссрате</span><span class="sxs-lookup"><span data-stu-id="209ae-359">VideoPacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="209ae-360">десятичное число (9; 4)</span><span class="sxs-lookup"><span data-stu-id="209ae-360">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="209ae-361">Частота потери видеопакетов.</span><span class="sxs-lookup"><span data-stu-id="209ae-361">Rate at which video packets were lost.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="209ae-362">Видеофрамелоссрате</span><span class="sxs-lookup"><span data-stu-id="209ae-362">VideoFrameLossRate</span></span></p></td>
<td><p><span data-ttu-id="209ae-363">Decimal (9.4)</span><span class="sxs-lookup"><span data-stu-id="209ae-363">decimal(9.4)</span></span></p></td>
<td><p><span data-ttu-id="209ae-364">Процент от общего числа потерянных кадров видео.</span><span class="sxs-lookup"><span data-stu-id="209ae-364">Percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="209ae-365">Видеофек</span><span class="sxs-lookup"><span data-stu-id="209ae-365">VideoFEC</span></span></p></td>
<td><p><span data-ttu-id="209ae-366">бит</span><span class="sxs-lookup"><span data-stu-id="209ae-366">bit</span></span></p></td>
<td><p><span data-ttu-id="209ae-367">Не используется.</span><span class="sxs-lookup"><span data-stu-id="209ae-367">Not used.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="209ae-368">Видеоаллокатебвавг</span><span class="sxs-lookup"><span data-stu-id="209ae-368">VideoAllocateBWAvg</span></span></p></td>
<td><p><span data-ttu-id="209ae-369">целое</span><span class="sxs-lookup"><span data-stu-id="209ae-369">int</span></span></p></td>
<td><p><span data-ttu-id="209ae-370">Средний объем пропускной способности, выделенной для видео.</span><span class="sxs-lookup"><span data-stu-id="209ae-370">Average amount of bandwidth allocated for video.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="209ae-371">VideoLocalFrameLossPercentageAvg</span><span class="sxs-lookup"><span data-stu-id="209ae-371">VideoLocalFrameLossPercentageAvg</span></span></p></td>
<td><p><span data-ttu-id="209ae-372">Decimal (9.4)</span><span class="sxs-lookup"><span data-stu-id="209ae-372">decimal(9.4)</span></span></p></td>
<td><p><span data-ttu-id="209ae-373">Процент от общего количества кадров видео, которые были утрачены.</span><span class="sxs-lookup"><span data-stu-id="209ae-373">Percentage of total video frames that were lost.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="209ae-374">Сендерискаллерпаи</span><span class="sxs-lookup"><span data-stu-id="209ae-374">SenderIsCallerPAI</span></span></p></td>
<td><p><span data-ttu-id="209ae-375">бит</span><span class="sxs-lookup"><span data-stu-id="209ae-375">bit</span></span></p></td>
<td><p><span data-ttu-id="209ae-376">Направление потока для идентификационной информации, утвержденной p.</span><span class="sxs-lookup"><span data-stu-id="209ae-376">Stream direction for p-asserted identity information.</span></span> <span data-ttu-id="209ae-377">1 — направление потока на вызываемый абонентом. 0 — направление потока из вызываемого объекта вызывающему абоненту.</span><span class="sxs-lookup"><span data-stu-id="209ae-377">1 means the stream direction is from the caller to the callee; 0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

