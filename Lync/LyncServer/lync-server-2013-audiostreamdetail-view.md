---
title: 'Lync Server 2013: представление Аудиостреамдетаил'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: AudioStreamDetail view
ms:assetid: b6a435b3-103c-41c4-96ed-33c3784534c0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721859(v=OCS.15)
ms:contentKeyID: 49733792
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 77cebcd47d735f1779396c0272877c0ec64a6189
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722589"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audiostreamdetail-view-in-lync-server-2013"></a><span data-ttu-id="dfb17-102">Аудиостреамдетаил представления в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dfb17-102">AudioStreamDetail view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dfb17-103">_**Тема последнего изменения:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="dfb17-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="dfb17-104">В представлении Аудиостреамдетаил хранятся сведения о каждом звуковом потоке в базе данных.</span><span class="sxs-lookup"><span data-stu-id="dfb17-104">The AudioStreamDetail View stores information about each audio stream in the database.</span></span> <span data-ttu-id="dfb17-105">Это представление было представлено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="dfb17-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dfb17-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="dfb17-106">Column</span></span></th>
<th><span data-ttu-id="dfb17-107">Тип данных</span><span class="sxs-lookup"><span data-stu-id="dfb17-107">Data Type</span></span></th>
<th><span data-ttu-id="dfb17-108">Подробности</span><span class="sxs-lookup"><span data-stu-id="dfb17-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dfb17-109">сессионтиме</span><span class="sxs-lookup"><span data-stu-id="dfb17-109">SessionTime</span></span></p></td>
<td><p><span data-ttu-id="dfb17-110">datetime</span><span class="sxs-lookup"><span data-stu-id="dfb17-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="dfb17-111">На которую ссылается <a href="lync-server-2013-medialine-table.md">Таблица медиалине в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="dfb17-111">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfb17-112">сессионсек</span><span class="sxs-lookup"><span data-stu-id="dfb17-112">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="dfb17-113">целое</span><span class="sxs-lookup"><span data-stu-id="dfb17-113">int</span></span></p></td>
<td><p><span data-ttu-id="dfb17-114">На которую ссылается <a href="lync-server-2013-medialine-table.md">Таблица медиалине в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="dfb17-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfb17-115">стреамид</span><span class="sxs-lookup"><span data-stu-id="dfb17-115">StreamId</span></span></p></td>
<td><p><span data-ttu-id="dfb17-116">целое</span><span class="sxs-lookup"><span data-stu-id="dfb17-116">int</span></span></p></td>
<td><p><span data-ttu-id="dfb17-117">Уникальный идентификатор в строке мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="dfb17-117">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfb17-118">StartTime</span><span class="sxs-lookup"><span data-stu-id="dfb17-118">StartTime</span></span></p></td>
<td><p><span data-ttu-id="dfb17-119">datetime</span><span class="sxs-lookup"><span data-stu-id="dfb17-119">datetime</span></span></p></td>
<td><p><span data-ttu-id="dfb17-120">Время начала сеанса.</span><span class="sxs-lookup"><span data-stu-id="dfb17-120">Start time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfb17-121">EndTime</span><span class="sxs-lookup"><span data-stu-id="dfb17-121">EndTime</span></span></p></td>
<td><p><span data-ttu-id="dfb17-122">datetime</span><span class="sxs-lookup"><span data-stu-id="dfb17-122">datetime</span></span></p></td>
<td><p><span data-ttu-id="dfb17-123">Время окончания сеанса.</span><span class="sxs-lookup"><span data-stu-id="dfb17-123">End time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfb17-124">диалогкатегори</span><span class="sxs-lookup"><span data-stu-id="dfb17-124">DialogCategory</span></span></p></td>
<td><p><span data-ttu-id="dfb17-125">бит</span><span class="sxs-lookup"><span data-stu-id="dfb17-125">bit</span></span></p></td>
<td><p><span data-ttu-id="dfb17-126">Категория диалоговых окон: 0 — сервер Lync Server — серверное средство для устранения проблем; 1 — это сервер, на котором выдается посредник для шлюза PSTN.</span><span class="sxs-lookup"><span data-stu-id="dfb17-126">Dialog category: 0 is the Lync Server to Mediation Server leg; 1 is the Mediation Server to PSTN gateway leg.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfb17-127">медиатионсервербипассфлаг</span><span class="sxs-lookup"><span data-stu-id="dfb17-127">MediationServerBypassFlag</span></span></p></td>
<td><p><span data-ttu-id="dfb17-128">бит</span><span class="sxs-lookup"><span data-stu-id="dfb17-128">bit</span></span></p></td>
<td><p><span data-ttu-id="dfb17-129">Флаг, указывающий, обходит ли звонок.</span><span class="sxs-lookup"><span data-stu-id="dfb17-129">Flag indicating if the call was bypassed or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfb17-130">медиабипассварнингфлаг</span><span class="sxs-lookup"><span data-stu-id="dfb17-130">MediaBypassWarningFlag</span></span></p></td>
<td><p><span data-ttu-id="dfb17-131">целое</span><span class="sxs-lookup"><span data-stu-id="dfb17-131">int</span></span></p></td>
<td><p><span data-ttu-id="dfb17-132">Если указано, указывает, почему звонок не обходится, даже если идентификаторы обхода не совпадают.</span><span class="sxs-lookup"><span data-stu-id="dfb17-132">If present, indicates why a call was not bypassed even if the bypass IDs matched.</span></span> <span data-ttu-id="dfb17-133">Определено только одно значение:</span><span class="sxs-lookup"><span data-stu-id="dfb17-133">Only one value is defined:</span></span></p>
<p><span data-ttu-id="dfb17-134">0x0001 — Неизвестный идентификатор обхода для сетевого адаптера по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="dfb17-134">0x0001 – Unknown bypass ID for Default network adapter.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfb17-135">каллприорити</span><span class="sxs-lookup"><span data-stu-id="dfb17-135">CallPriority</span></span></p></td>
<td><p><span data-ttu-id="dfb17-136">целое</span><span class="sxs-lookup"><span data-stu-id="dfb17-136">int</span></span></p></td>
<td><p><span data-ttu-id="dfb17-137">Приоритет звонка.</span><span class="sxs-lookup"><span data-stu-id="dfb17-137">Priority of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfb17-138">каллерпул</span><span class="sxs-lookup"><span data-stu-id="dfb17-138">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="dfb17-139">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="dfb17-139">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="dfb17-140">Полное доменное имя пула вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="dfb17-140">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfb17-141">каллипул</span><span class="sxs-lookup"><span data-stu-id="dfb17-141">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="dfb17-142">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="dfb17-142">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="dfb17-143">Полное доменное имя пула вызываемых абонентов.</span><span class="sxs-lookup"><span data-stu-id="dfb17-143">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfb17-144">Вызывающая сторона</span><span class="sxs-lookup"><span data-stu-id="dfb17-144">Caller</span></span></p></td>
<td><p><span data-ttu-id="dfb17-145">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="dfb17-145">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="dfb17-146">URI вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="dfb17-146">Caller’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfb17-147">Вызываемая сторона</span><span class="sxs-lookup"><span data-stu-id="dfb17-147">Callee</span></span></p></td>
<td><p><span data-ttu-id="dfb17-148">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="dfb17-148">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="dfb17-149">Универсальный код ресурса (URI) вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="dfb17-149">Callee’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfb17-150">каллерусеражент</span><span class="sxs-lookup"><span data-stu-id="dfb17-150">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="dfb17-151">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="dfb17-151">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="dfb17-152">Строка агента пользователя вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="dfb17-152">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfb17-153">каллерусераженттипе</span><span class="sxs-lookup"><span data-stu-id="dfb17-153">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="dfb17-154">smallint</span><span class="sxs-lookup"><span data-stu-id="dfb17-154">smallint</span></span></p></td>
<td><p><span data-ttu-id="dfb17-155">Тип агента пользователя вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="dfb17-155">Type of the caller’s user agent.</span></span> <span data-ttu-id="dfb17-156">Дополнительные сведения: <a href="lync-server-2013-useragent-table.md">Таблица UserAgent в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="dfb17-156">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfb17-157">каллерусераженткатегори</span><span class="sxs-lookup"><span data-stu-id="dfb17-157">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="dfb17-158">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="dfb17-158">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="dfb17-159">Категория агента пользователя вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="dfb17-159">Category of the caller’s user agent.</span></span> <span data-ttu-id="dfb17-160">Дополнительные сведения <a href="lync-server-2013-useragentdef-table-qoe.md">усеражентдеф в таблице "QoE" в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="dfb17-160">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfb17-161">каллиусеражент</span><span class="sxs-lookup"><span data-stu-id="dfb17-161">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="dfb17-162">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="dfb17-162">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="dfb17-163">Строка агента пользователя вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="dfb17-163">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfb17-164">каллиусераженттипе</span><span class="sxs-lookup"><span data-stu-id="dfb17-164">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="dfb17-165">smallint</span><span class="sxs-lookup"><span data-stu-id="dfb17-165">smallint</span></span></p></td>
<td><p><span data-ttu-id="dfb17-166">Тип агента пользователя, вызываемого абонентом.</span><span class="sxs-lookup"><span data-stu-id="dfb17-166">Type of callee’s user agent.</span></span> <span data-ttu-id="dfb17-167">Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-useragent-table.md">таблицей UserAgent в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="dfb17-167">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfb17-168">каллиусераженткатегори</span><span class="sxs-lookup"><span data-stu-id="dfb17-168">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="dfb17-169">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="dfb17-169">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="dfb17-170">Категория агента пользователя вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="dfb17-170">Category of callee’s user agent.</span></span> <span data-ttu-id="dfb17-171">Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-useragentdef-table-qoe.md">таблицей усеражентдеф (QoE) в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="dfb17-171">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfb17-172">каллерендпоинт</span><span class="sxs-lookup"><span data-stu-id="dfb17-172">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="dfb17-173">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="dfb17-173">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="dfb17-174">Имя конечной точки вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="dfb17-174">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfb17-175">каллиендпоинт</span><span class="sxs-lookup"><span data-stu-id="dfb17-175">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="dfb17-176">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="dfb17-176">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="dfb17-177">Имя конечной точки вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="dfb17-177">Callee’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfb17-178">каллерос</span><span class="sxs-lookup"><span data-stu-id="dfb17-178">CallerOS</span></span></p></td>
<td><p><span data-ttu-id="dfb17-179">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="dfb17-179">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="dfb17-180">Операционная система (ОС) конечной точки вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="dfb17-180">Operating system (OS) of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfb17-181">каллиос</span><span class="sxs-lookup"><span data-stu-id="dfb17-181">CalleeOS</span></span></p></td>
<td><p><span data-ttu-id="dfb17-182">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="dfb17-182">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="dfb17-183">Операционная система (ОС) конечной точки вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="dfb17-183">Operating system (OS) of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfb17-184">каллеркпунаме</span><span class="sxs-lookup"><span data-stu-id="dfb17-184">CallerCPUName</span></span></p></td>
<td><p><span data-ttu-id="dfb17-185">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="dfb17-185">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="dfb17-186">Имя ЦП конечной точки вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="dfb17-186">CPU name of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfb17-187">калликпунаме</span><span class="sxs-lookup"><span data-stu-id="dfb17-187">CalleeCPUName</span></span></p></td>
<td><p><span data-ttu-id="dfb17-188">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="dfb17-188">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="dfb17-189">Имя ЦП конечной точки вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="dfb17-189">CPU name of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfb17-190">каллеркпунумберофкорес</span><span class="sxs-lookup"><span data-stu-id="dfb17-190">CallerCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="dfb17-191">smallint</span><span class="sxs-lookup"><span data-stu-id="dfb17-191">smallint</span></span></p></td>
<td><p><span data-ttu-id="dfb17-192">Количество ядер ЦП в конечной точке вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="dfb17-192">Number of CPU cores in the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfb17-193">калликпунумберофкорес</span><span class="sxs-lookup"><span data-stu-id="dfb17-193">CalleeCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="dfb17-194">smallint</span><span class="sxs-lookup"><span data-stu-id="dfb17-194">smallint</span></span></p></td>
<td><p><span data-ttu-id="dfb17-195">Количество ядер ЦП в конечной точке вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="dfb17-195">Number of CPU cores in the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfb17-196">каллеркпупроцессорспид</span><span class="sxs-lookup"><span data-stu-id="dfb17-196">CallerCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="dfb17-197">целое</span><span class="sxs-lookup"><span data-stu-id="dfb17-197">int</span></span></p></td>
<td><p><span data-ttu-id="dfb17-198">Частота процессора конечной точки вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="dfb17-198">CPU processor speed of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfb17-199">калликпупроцессорспид</span><span class="sxs-lookup"><span data-stu-id="dfb17-199">CalleeCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="dfb17-200">целое</span><span class="sxs-lookup"><span data-stu-id="dfb17-200">int</span></span></p></td>
<td><p><span data-ttu-id="dfb17-201">Тактовая частота процессора на конечной точке вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="dfb17-201">CPU processor speed of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfb17-202">каллервиртуализатионфлаг</span><span class="sxs-lookup"><span data-stu-id="dfb17-202">CallerVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="dfb17-203">tinyint</span><span class="sxs-lookup"><span data-stu-id="dfb17-203">tinyint</span></span></p></td>
<td><p><span data-ttu-id="dfb17-204">Указывает, работает ли система вызывающего абонента в виртуализованной среде.</span><span class="sxs-lookup"><span data-stu-id="dfb17-204">Indicates whether the caller’s system is running in a virtualized environment.</span></span> <span data-ttu-id="dfb17-205">Дополнительные сведения приведены <a href="lync-server-2013-endpoint-table.md">в таблице конечная точка в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="dfb17-205">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfb17-206">калливиртуализатионфлаг</span><span class="sxs-lookup"><span data-stu-id="dfb17-206">CalleeVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="dfb17-207">tinyint</span><span class="sxs-lookup"><span data-stu-id="dfb17-207">tinyint</span></span></p></td>
<td><p><span data-ttu-id="dfb17-208">Указывает, работает ли система вызываемого абонента в виртуализованной среде.</span><span class="sxs-lookup"><span data-stu-id="dfb17-208">Indicates whether the callee’s system is running in a virtualized environment.</span></span> <span data-ttu-id="dfb17-209">Дополнительные сведения приведены <a href="lync-server-2013-endpoint-table.md">в таблице конечная точка в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="dfb17-209">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfb17-210">коррелатионкэй</span><span class="sxs-lookup"><span data-stu-id="dfb17-210">CorrelationKey</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dfb17-211">Ключ корреляции.</span><span class="sxs-lookup"><span data-stu-id="dfb17-211">Correlation key.</span></span> <span data-ttu-id="dfb17-212">На которую ссылается <a href="lync-server-2013-sessioncorrelation-table.md">Таблица сессионкоррелатион в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="dfb17-212">Referenced from the <a href="lync-server-2013-sessioncorrelation-table.md">SessionCorrelation table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfb17-213">коннективитице</span><span class="sxs-lookup"><span data-stu-id="dfb17-213">ConnectivityIce</span></span></p></td>
<td><p><span data-ttu-id="dfb17-214">tinyint</span><span class="sxs-lookup"><span data-stu-id="dfb17-214">tinyint</span></span></p></td>
<td><p><span data-ttu-id="dfb17-215">Информация о пути к носителю, например прямая или ретранслируемая.</span><span class="sxs-lookup"><span data-stu-id="dfb17-215">Information about the media path, such as direct or relayed.</span></span> <span data-ttu-id="dfb17-216">Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-medialine-table.md">таблицей медиалине в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="dfb17-216">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfb17-217">каллерицеварнингфлагс</span><span class="sxs-lookup"><span data-stu-id="dfb17-217">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="dfb17-218">целое</span><span class="sxs-lookup"><span data-stu-id="dfb17-218">int</span></span></p></td>
<td><p><span data-ttu-id="dfb17-219">Сведения о процессе интерактивной установки подключения (ICE), описанные в разделе Флаги BITS для вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="dfb17-219">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller.</span></span> <span data-ttu-id="dfb17-220">Подробности можно найти в спецификации серверного протокола контроля качества обслуживания.</span><span class="sxs-lookup"><span data-stu-id="dfb17-220">For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfb17-221">каллиицеварнингфлагс</span><span class="sxs-lookup"><span data-stu-id="dfb17-221">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="dfb17-222">целое</span><span class="sxs-lookup"><span data-stu-id="dfb17-222">int</span></span></p></td>
<td><p><span data-ttu-id="dfb17-223">Сведения о процессе установки интерактивной связи (ICE), описанные в флагах BITS для вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="dfb17-223">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee.</span></span> <span data-ttu-id="dfb17-224">Подробности можно найти в спецификации серверного протокола контроля качества обслуживания.</span><span class="sxs-lookup"><span data-stu-id="dfb17-224">For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfb17-225">Transport</span><span class="sxs-lookup"><span data-stu-id="dfb17-225">Transport</span></span></p></td>
<td><p><span data-ttu-id="dfb17-226">tinyint</span><span class="sxs-lookup"><span data-stu-id="dfb17-226">tinyint</span></span></p></td>
<td><p><span data-ttu-id="dfb17-227">Тип транспорта: 0 — UDP, 1 — TCP.</span><span class="sxs-lookup"><span data-stu-id="dfb17-227">Transport type: 0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfb17-228">каллерипаддр</span><span class="sxs-lookup"><span data-stu-id="dfb17-228">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="dfb17-229">var (50)</span><span class="sxs-lookup"><span data-stu-id="dfb17-229">var(50)</span></span></p></td>
<td><p><span data-ttu-id="dfb17-230">IP-адрес вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="dfb17-230">IP address of the caller.</span></span> <span data-ttu-id="dfb17-231">Это может быть либо IPv4, либо IPv6-адрес.</span><span class="sxs-lookup"><span data-stu-id="dfb17-231">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfb17-232">каллерпорт</span><span class="sxs-lookup"><span data-stu-id="dfb17-232">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="dfb17-233">целое</span><span class="sxs-lookup"><span data-stu-id="dfb17-233">int</span></span></p></td>
<td><p><span data-ttu-id="dfb17-234">Порт, используемый вызывающим абонентом.</span><span class="sxs-lookup"><span data-stu-id="dfb17-234">Port used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfb17-235">каллеринсиде</span><span class="sxs-lookup"><span data-stu-id="dfb17-235">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="dfb17-236">бит</span><span class="sxs-lookup"><span data-stu-id="dfb17-236">bit</span></span></p></td>
<td><p><span data-ttu-id="dfb17-237">Указывает, находится ли вызывающий объект в сети Interval: 1 означает, что вызывающий абонент входит в корпоративную сеть, а 0 означает, что вызывающий абонент находится за пределами сети.</span><span class="sxs-lookup"><span data-stu-id="dfb17-237">Indicates whether the caller is inside the interval network: 1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfb17-238">каллиипаддр</span><span class="sxs-lookup"><span data-stu-id="dfb17-238">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="dfb17-239">var (50)</span><span class="sxs-lookup"><span data-stu-id="dfb17-239">var(50)</span></span></p></td>
<td><p><span data-ttu-id="dfb17-240">IP-адрес вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="dfb17-240">IP address of the callee.</span></span> <span data-ttu-id="dfb17-241">Это может быть либо IPv4, либо IPv6-адрес.</span><span class="sxs-lookup"><span data-stu-id="dfb17-241">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfb17-242">каллипорт</span><span class="sxs-lookup"><span data-stu-id="dfb17-242">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="dfb17-243">целое</span><span class="sxs-lookup"><span data-stu-id="dfb17-243">int</span></span></p></td>
<td><p><span data-ttu-id="dfb17-244">Порт, используемый вызываемым абонентом.</span><span class="sxs-lookup"><span data-stu-id="dfb17-244">Port used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfb17-245">каллиинсиде</span><span class="sxs-lookup"><span data-stu-id="dfb17-245">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="dfb17-246">бит</span><span class="sxs-lookup"><span data-stu-id="dfb17-246">bit</span></span></p></td>
<td><p><span data-ttu-id="dfb17-247">Указывает, находится ли вызывающий объект в сети Interval: 1 означает, что вызываемый абонент входит в корпоративную сеть, а 0 означает, что вызываемый объект находится за пределами сети.</span><span class="sxs-lookup"><span data-stu-id="dfb17-247">Indicates whether the callee is inside the interval network: 1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfb17-248">каллерусерсите</span><span class="sxs-lookup"><span data-stu-id="dfb17-248">CallerUserSite</span></span></p></td>
<td><p><span data-ttu-id="dfb17-249">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="dfb17-249">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="dfb17-250">Имя сайта вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="dfb17-250">Name of the caller’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfb17-251">каллеррегион</span><span class="sxs-lookup"><span data-stu-id="dfb17-251">CallerRegion</span></span></p></td>
<td><p><span data-ttu-id="dfb17-252">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="dfb17-252">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="dfb17-253">Название страны или региона сайта вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="dfb17-253">Name of the country/region of the caller’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfb17-254">каллиусерсите</span><span class="sxs-lookup"><span data-stu-id="dfb17-254">CalleeUserSite</span></span></p></td>
<td><p><span data-ttu-id="dfb17-255">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="dfb17-255">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="dfb17-256">Имя сайта вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="dfb17-256">Name of the callee’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfb17-257">каллирегион</span><span class="sxs-lookup"><span data-stu-id="dfb17-257">CalleeRegion</span></span></p></td>
<td><p><span data-ttu-id="dfb17-258">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="dfb17-258">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="dfb17-259">Название страны или региона сайта вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="dfb17-259">Name of the country/region of the callee’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfb17-260">каллеррелайипаддр</span><span class="sxs-lookup"><span data-stu-id="dfb17-260">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="dfb17-261">var (50)</span><span class="sxs-lookup"><span data-stu-id="dfb17-261">var(50)</span></span></p></td>
<td><p><span data-ttu-id="dfb17-262">IP-адрес службы EDGE (/V), используемой вызывающим абонентом.</span><span class="sxs-lookup"><span data-stu-id="dfb17-262">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="dfb17-263">Дополнительные сведения приведены в <a href="lync-server-2013-ipaddress-table.md">таблице IP-адрес в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="dfb17-263">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfb17-264">каллеррелайпорт</span><span class="sxs-lookup"><span data-stu-id="dfb17-264">CallerRelayPort</span></span></p></td>
<td><p><span data-ttu-id="dfb17-265">целое</span><span class="sxs-lookup"><span data-stu-id="dfb17-265">int</span></span></p></td>
<td><p><span data-ttu-id="dfb17-266">Порт, используемый в службе EDGE (A/V), используемой вызывающим абонентом.</span><span class="sxs-lookup"><span data-stu-id="dfb17-266">Port used on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfb17-267">каллирелайипаддр</span><span class="sxs-lookup"><span data-stu-id="dfb17-267">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="dfb17-268">var (50)</span><span class="sxs-lookup"><span data-stu-id="dfb17-268">var(50)</span></span></p></td>
<td><p><span data-ttu-id="dfb17-269">Ключ IP-адреса для службы EDGE (/V), используемой вызываемым абонентом.</span><span class="sxs-lookup"><span data-stu-id="dfb17-269">IP Address key of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="dfb17-270">Дополнительные сведения приведены в <a href="lync-server-2013-ipaddress-table.md">таблице IP-адрес в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="dfb17-270">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfb17-271">каллирелайпорт</span><span class="sxs-lookup"><span data-stu-id="dfb17-271">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="dfb17-272">целое</span><span class="sxs-lookup"><span data-stu-id="dfb17-272">int</span></span></p></td>
<td><p><span data-ttu-id="dfb17-273">Порт, используемый в службе EDGE (A/V), используемой вызываемым абонентом.</span><span class="sxs-lookup"><span data-stu-id="dfb17-273">Port used on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfb17-274">каллеркаптуредев</span><span class="sxs-lookup"><span data-stu-id="dfb17-274">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="dfb17-275">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="dfb17-275">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="dfb17-276">Имя устройства захвата вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="dfb17-276">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfb17-277">каллеррендердев</span><span class="sxs-lookup"><span data-stu-id="dfb17-277">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="dfb17-278">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="dfb17-278">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="dfb17-279">Имя устройства отрисовки вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="dfb17-279">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfb17-280">каллеркаптуредевдривер</span><span class="sxs-lookup"><span data-stu-id="dfb17-280">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="dfb17-281">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="dfb17-281">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="dfb17-282">Имя драйвера устройства захвата вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="dfb17-282">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfb17-283">каллеррендердривер</span><span class="sxs-lookup"><span data-stu-id="dfb17-283">CallerRenderDriver</span></span></p></td>
<td><p><span data-ttu-id="dfb17-284">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="dfb17-284">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="dfb17-285">Имя драйвера устройства отрисовки вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="dfb17-285">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfb17-286">калликаптуредев</span><span class="sxs-lookup"><span data-stu-id="dfb17-286">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="dfb17-287">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="dfb17-287">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="dfb17-288">Имя устройства захвата абонента.</span><span class="sxs-lookup"><span data-stu-id="dfb17-288">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfb17-289">каллирендердев</span><span class="sxs-lookup"><span data-stu-id="dfb17-289">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="dfb17-290">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="dfb17-290">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="dfb17-291">Имя устройства отрисовки вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="dfb17-291">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfb17-292">калликаптуредевдривер</span><span class="sxs-lookup"><span data-stu-id="dfb17-292">CalleeCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="dfb17-293">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="dfb17-293">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="dfb17-294">Имя драйвера устройства захвата абонента.</span><span class="sxs-lookup"><span data-stu-id="dfb17-294">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfb17-295">каллирендердевдривер</span><span class="sxs-lookup"><span data-stu-id="dfb17-295">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="dfb17-296">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="dfb17-296">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="dfb17-297">Имя драйвера устройства обработки вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="dfb17-297">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfb17-298">каллернетворкконнектионтипе</span><span class="sxs-lookup"><span data-stu-id="dfb17-298">CallerNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="dfb17-299">tinyint</span><span class="sxs-lookup"><span data-stu-id="dfb17-299">tinyint</span></span></p></td>
<td><p><span data-ttu-id="dfb17-300">Тип сетевого подключения вызывающего абонента: 0 проводное соединение, 1 — Беспроводная связь.</span><span class="sxs-lookup"><span data-stu-id="dfb17-300">Caller’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfb17-301">каллервпн</span><span class="sxs-lookup"><span data-stu-id="dfb17-301">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="dfb17-302">бит</span><span class="sxs-lookup"><span data-stu-id="dfb17-302">bit</span></span></p></td>
<td><p><span data-ttu-id="dfb17-303">Указывает, подключен ли вызывающий абонент к виртуальной частной сети: 1 — виртуальная частная сеть (VPN), 0 — не VPN.</span><span class="sxs-lookup"><span data-stu-id="dfb17-303">Indicates whether the caller connected over a virtual private network: 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfb17-304">каллерлинкспид</span><span class="sxs-lookup"><span data-stu-id="dfb17-304">CallerLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="dfb17-305">десятичное число (18; 0)</span><span class="sxs-lookup"><span data-stu-id="dfb17-305">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="dfb17-306">Скорость сетевого соединения для конечной точки вызывающего абонента бит/с.</span><span class="sxs-lookup"><span data-stu-id="dfb17-306">Network link speed for the caller's endpoint in bps.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfb17-307">каллинетворкконнектионтипе</span><span class="sxs-lookup"><span data-stu-id="dfb17-307">CalleeNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="dfb17-308">tinyint</span><span class="sxs-lookup"><span data-stu-id="dfb17-308">tinyint</span></span></p></td>
<td><p><span data-ttu-id="dfb17-309">Тип сетевого подключения абонента: 0 – проводное, 1 — Беспроводная связь.</span><span class="sxs-lookup"><span data-stu-id="dfb17-309">Callee’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfb17-310">калливпн</span><span class="sxs-lookup"><span data-stu-id="dfb17-310">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="dfb17-311">бит</span><span class="sxs-lookup"><span data-stu-id="dfb17-311">bit</span></span></p></td>
<td><p><span data-ttu-id="dfb17-312">Указывает, подключен ли вызывающий абонент к виртуальной частной сети: 1 — виртуальная частная сеть (VPN), 0 — не VPN.</span><span class="sxs-lookup"><span data-stu-id="dfb17-312">Indicates whether the caller connected over a virtual private network: 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfb17-313">каллилинкспид</span><span class="sxs-lookup"><span data-stu-id="dfb17-313">CalleeLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="dfb17-314">десятичное число (18; 0)</span><span class="sxs-lookup"><span data-stu-id="dfb17-314">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="dfb17-315">Скорость сетевого соединения для конечной точки вызываемого абонента бит/с.</span><span class="sxs-lookup"><span data-stu-id="dfb17-315">Network link speed for the callee's endpoint in bps.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfb17-316">конверсатионалмос</span><span class="sxs-lookup"><span data-stu-id="dfb17-316">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="dfb17-317">десятичное число (3, 2)</span><span class="sxs-lookup"><span data-stu-id="dfb17-317">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="dfb17-318">Нарровбанд MOS из сеансов голосовой связи (на основе обоих звуковых потоков).</span><span class="sxs-lookup"><span data-stu-id="dfb17-318">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfb17-319">апплиедбандвидслимит</span><span class="sxs-lookup"><span data-stu-id="dfb17-319">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="dfb17-320">целое</span><span class="sxs-lookup"><span data-stu-id="dfb17-320">int</span></span></p></td>
<td><p><span data-ttu-id="dfb17-321">Реальная пропускная способность, примененная к потоку отправки данных в соответствии с различными параметрами политики (например, "повернуть", "API", SDP, сервер политики и т. д.).</span><span class="sxs-lookup"><span data-stu-id="dfb17-321">Actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on).</span></span> <span data-ttu-id="dfb17-322">Это не следует путать с эффективной пропускной способностью, так как в зависимости от оценки пропускной способности может снизиться эффективная пропускная способность.</span><span class="sxs-lookup"><span data-stu-id="dfb17-322">This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate.</span></span> <span data-ttu-id="dfb17-323">Это является, по сути, максимальной пропускной способностью потока отправки, который может занимать ограничения пропускной способности, наложенные на эту оценку.</span><span class="sxs-lookup"><span data-stu-id="dfb17-323">This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfb17-324">JitterInterArrival</span><span class="sxs-lookup"><span data-stu-id="dfb17-324">JitterInterArrival</span></span></p></td>
<td><p><span data-ttu-id="dfb17-325">целое</span><span class="sxs-lookup"><span data-stu-id="dfb17-325">int</span></span></p></td>
<td><p><span data-ttu-id="dfb17-326">Средняя колебание сети из статистики протокола управления временем в реальном времени (РТКП).</span><span class="sxs-lookup"><span data-stu-id="dfb17-326">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfb17-327">життеринтерарривалмакс</span><span class="sxs-lookup"><span data-stu-id="dfb17-327">JitterInterArrivalMax</span></span></p></td>
<td><p><span data-ttu-id="dfb17-328">целое</span><span class="sxs-lookup"><span data-stu-id="dfb17-328">int</span></span></p></td>
<td><p><span data-ttu-id="dfb17-329">Максимальная колебание сети во время звонка.</span><span class="sxs-lookup"><span data-stu-id="dfb17-329">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfb17-330">PacketLossRate</span><span class="sxs-lookup"><span data-stu-id="dfb17-330">PacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="dfb17-331">десятичное число (5; 4)</span><span class="sxs-lookup"><span data-stu-id="dfb17-331">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="dfb17-332">Средняя скорость потерь пакетов во время звонка.</span><span class="sxs-lookup"><span data-stu-id="dfb17-332">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfb17-333">паккетлоссратемакс</span><span class="sxs-lookup"><span data-stu-id="dfb17-333">PacketLossRateMax</span></span></p></td>
<td><p><span data-ttu-id="dfb17-334">десятичное число (5; 4)</span><span class="sxs-lookup"><span data-stu-id="dfb17-334">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="dfb17-335">Максимальное количество потерь пакетов, замеченное во время звонка.</span><span class="sxs-lookup"><span data-stu-id="dfb17-335">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfb17-336">бурстденсити</span><span class="sxs-lookup"><span data-stu-id="dfb17-336">BurstDensity</span></span></p></td>
<td><p><span data-ttu-id="dfb17-337">десятичное число (9; 4)</span><span class="sxs-lookup"><span data-stu-id="dfb17-337">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="dfb17-338">Средняя плотность потери пакетов во время звонка.</span><span class="sxs-lookup"><span data-stu-id="dfb17-338">Average density of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfb17-339">бурстдуратион</span><span class="sxs-lookup"><span data-stu-id="dfb17-339">BurstDuration</span></span></p></td>
<td><p><span data-ttu-id="dfb17-340">целое</span><span class="sxs-lookup"><span data-stu-id="dfb17-340">int</span></span></p></td>
<td><p><span data-ttu-id="dfb17-341">Средняя продолжительность потери пакетов в течение заданных потерь во время звонка.</span><span class="sxs-lookup"><span data-stu-id="dfb17-341">Average duration of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfb17-342">бурстгапденсити</span><span class="sxs-lookup"><span data-stu-id="dfb17-342">BurstGapDensity</span></span></p></td>
<td><p><span data-ttu-id="dfb17-343">десятичное число (9; 4)</span><span class="sxs-lookup"><span data-stu-id="dfb17-343">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="dfb17-344">Средняя плотность потери пакетов при пропуске между пакетами потери данных.</span><span class="sxs-lookup"><span data-stu-id="dfb17-344">Average density of packet loss during gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfb17-345">бурстгапдуратион</span><span class="sxs-lookup"><span data-stu-id="dfb17-345">BurstGapDuration</span></span></p></td>
<td><p><span data-ttu-id="dfb17-346">целое</span><span class="sxs-lookup"><span data-stu-id="dfb17-346">int</span></span></p></td>
<td><p><span data-ttu-id="dfb17-347">Средняя продолжительность промежутков между пакетами потери данных.</span><span class="sxs-lookup"><span data-stu-id="dfb17-347">Average duration of gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfb17-348">паккетутилизатион</span><span class="sxs-lookup"><span data-stu-id="dfb17-348">PacketUtilization</span></span></p></td>
<td><p><span data-ttu-id="dfb17-349">целое</span><span class="sxs-lookup"><span data-stu-id="dfb17-349">int</span></span></p></td>
<td><p><span data-ttu-id="dfb17-350">Число пакетов для аудиопотока.</span><span class="sxs-lookup"><span data-stu-id="dfb17-350">Packet count for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfb17-351">Самый пропускная способность</span><span class="sxs-lookup"><span data-stu-id="dfb17-351">BandwidthEst</span></span></p></td>
<td><p><span data-ttu-id="dfb17-352">целое</span><span class="sxs-lookup"><span data-stu-id="dfb17-352">int</span></span></p></td>
<td><p><span data-ttu-id="dfb17-353">Оценка пропускной способности для аудиопотока.</span><span class="sxs-lookup"><span data-stu-id="dfb17-353">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfb17-354">деградатионавг</span><span class="sxs-lookup"><span data-stu-id="dfb17-354">DegradationAvg</span></span></p></td>
<td><p><span data-ttu-id="dfb17-355">десятичное число (3, 2)</span><span class="sxs-lookup"><span data-stu-id="dfb17-355">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="dfb17-356">Сетевое MOS падение на весь звонок.</span><span class="sxs-lookup"><span data-stu-id="dfb17-356">Network MOS Degradation for the whole call.</span></span> <span data-ttu-id="dfb17-357">Диапазон от 0,0 до 5,0.</span><span class="sxs-lookup"><span data-stu-id="dfb17-357">Range is 0.0 to 5.0.</span></span> <span data-ttu-id="dfb17-358">Этот показатель показывает объем сетевого MOS уменьшился из-за колебаний и потери пакетов.</span><span class="sxs-lookup"><span data-stu-id="dfb17-358">This metric shows the amount the Network MOS was reduced because of jitter and packet loss.</span></span> <span data-ttu-id="dfb17-359">Для приемлемого качества оно должно быть менее 0,5.</span><span class="sxs-lookup"><span data-stu-id="dfb17-359">For acceptable quality it should less than 0.5.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfb17-360">деградатионмакс</span><span class="sxs-lookup"><span data-stu-id="dfb17-360">DegradationMax</span></span></p></td>
<td><p><span data-ttu-id="dfb17-361">десятичное число (3, 2)</span><span class="sxs-lookup"><span data-stu-id="dfb17-361">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="dfb17-362">Максимальная длина сетевого MOS во время звонка.</span><span class="sxs-lookup"><span data-stu-id="dfb17-362">Maximum Network MOS degradation during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfb17-363">деградатионжиттеравг</span><span class="sxs-lookup"><span data-stu-id="dfb17-363">DegradationJitterAvg</span></span></p></td>
<td><p><span data-ttu-id="dfb17-364">десятичное число (3, 2)</span><span class="sxs-lookup"><span data-stu-id="dfb17-364">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="dfb17-365">Снижение производительности сети MOS из – за колебаний.</span><span class="sxs-lookup"><span data-stu-id="dfb17-365">Network MOS degradation caused by jitter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfb17-366">деградатионпаккетлоссавг</span><span class="sxs-lookup"><span data-stu-id="dfb17-366">DegradationPacketLossAvg</span></span></p></td>
<td><p><span data-ttu-id="dfb17-367">десятичное число (3, 2)</span><span class="sxs-lookup"><span data-stu-id="dfb17-367">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="dfb17-368">Снижение производительности сети MOS из – за потери пакетов.</span><span class="sxs-lookup"><span data-stu-id="dfb17-368">Network MOS degradation caused by packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfb17-369">PayloadDescription</span><span class="sxs-lookup"><span data-stu-id="dfb17-369">PayloadDescription</span></span></p></td>
<td><p><span data-ttu-id="dfb17-370">целое</span><span class="sxs-lookup"><span data-stu-id="dfb17-370">int</span></span></p></td>
<td><p><span data-ttu-id="dfb17-371">Аудиокодек, использованный для вызова, на который ссылается <a href="lync-server-2013-payloaddescription-table.md">Таблица пайлоаддескриптион в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="dfb17-371">The audio codec used for the call, referenced from the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfb17-372">аудиосамплерате</span><span class="sxs-lookup"><span data-stu-id="dfb17-372">AudioSampleRate</span></span></p></td>
<td><p><span data-ttu-id="dfb17-373">целое</span><span class="sxs-lookup"><span data-stu-id="dfb17-373">int</span></span></p></td>
<td><p><span data-ttu-id="dfb17-374">Частота дискретизации для аудиопотока.</span><span class="sxs-lookup"><span data-stu-id="dfb17-374">Sampling rate for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfb17-375">каллерсендсигналлевел</span><span class="sxs-lookup"><span data-stu-id="dfb17-375">CallerSendSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="dfb17-376">целое</span><span class="sxs-lookup"><span data-stu-id="dfb17-376">int</span></span></p></td>
<td><p><span data-ttu-id="dfb17-377">Уровень звукового сигнала, выступающем после аналогового усиления, для звука, отправленного вызывающим абонентом.</span><span class="sxs-lookup"><span data-stu-id="dfb17-377">Post-Analog Gain Control audio signal level for the audio the caller sent.</span></span> <span data-ttu-id="dfb17-378">Единицей измерения для этой метрики является Дбмо.</span><span class="sxs-lookup"><span data-stu-id="dfb17-378">The unit for this metric is dBmo.</span></span> <span data-ttu-id="dfb17-379">Для приемлемого качества оно должно быть не менее 30 Дбмо.</span><span class="sxs-lookup"><span data-stu-id="dfb17-379">For acceptable quality, it should be at least 30 dBmo.</span></span> <span data-ttu-id="dfb17-380">Этот показатель не передается сервером Конференции и IP-телефонами по протоколу A/V.</span><span class="sxs-lookup"><span data-stu-id="dfb17-380">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfb17-381">каллерреквсигналлевел</span><span class="sxs-lookup"><span data-stu-id="dfb17-381">CallerRecvSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="dfb17-382">целое</span><span class="sxs-lookup"><span data-stu-id="dfb17-382">int</span></span></p></td>
<td><p><span data-ttu-id="dfb17-383">Уровень звукового сигнала для звука, полученного вызывающим абонентом.</span><span class="sxs-lookup"><span data-stu-id="dfb17-383">Audio signal level for the audio the caller received.</span></span> <span data-ttu-id="dfb17-384">Единицей измерения для этой метрики является Дбмо.</span><span class="sxs-lookup"><span data-stu-id="dfb17-384">The unit for this metric is dBmo.</span></span> <span data-ttu-id="dfb17-385">Для приемлемого качества оно должно быть не менее 30 Дбмо.</span><span class="sxs-lookup"><span data-stu-id="dfb17-385">For acceptable quality, it should be at least 30 dBmo.</span></span> <span data-ttu-id="dfb17-386">Этот показатель не передается сервером Конференции и IP-телефонами по протоколу A/V.</span><span class="sxs-lookup"><span data-stu-id="dfb17-386">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfb17-387">каллерсендноиселевел</span><span class="sxs-lookup"><span data-stu-id="dfb17-387">CallerSendNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="dfb17-388">целое</span><span class="sxs-lookup"><span data-stu-id="dfb17-388">int</span></span></p></td>
<td><p><span data-ttu-id="dfb17-389">После аналогового усиления контрольного шума для звука, который отправляет вызывающий абонент.</span><span class="sxs-lookup"><span data-stu-id="dfb17-389">Post-Analog Gain Control audio noise level for the audio the caller sent.</span></span> <span data-ttu-id="dfb17-390">Единицей измерения для этой метрики является Дбмо.</span><span class="sxs-lookup"><span data-stu-id="dfb17-390">The unit for this metric is dBmo.</span></span> <span data-ttu-id="dfb17-391">Для приемлемого качества оно должно быть менее 35 Дбмо.</span><span class="sxs-lookup"><span data-stu-id="dfb17-391">For acceptable quality, it should be less than 35 dBmo.</span></span> <span data-ttu-id="dfb17-392">Этот показатель не передается сервером Конференции и IP-телефонами по протоколу A/V.</span><span class="sxs-lookup"><span data-stu-id="dfb17-392">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfb17-393">каллерреквноиселевел</span><span class="sxs-lookup"><span data-stu-id="dfb17-393">CallerRecvNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="dfb17-394">целое</span><span class="sxs-lookup"><span data-stu-id="dfb17-394">int</span></span></p></td>
<td><p><span data-ttu-id="dfb17-395">Звуковой шум по контролю звукового сопровождения для звукового сигнала, полученного вызывающим абонентом.</span><span class="sxs-lookup"><span data-stu-id="dfb17-395">Post-Analog Gain Control audio noise level for the audio the caller received.</span></span> <span data-ttu-id="dfb17-396">Единицей измерения для этой метрики является Дбмо.</span><span class="sxs-lookup"><span data-stu-id="dfb17-396">The unit for this metric is dBmo.</span></span> <span data-ttu-id="dfb17-397">Для приемлемого качества оно должно быть менее 35 Дбмо.</span><span class="sxs-lookup"><span data-stu-id="dfb17-397">For acceptable quality, it should be less than 35 dBmo.</span></span> <span data-ttu-id="dfb17-398">Этот показатель не передается сервером Конференции и IP-телефонами по протоколу A/V.</span><span class="sxs-lookup"><span data-stu-id="dfb17-398">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfb17-399">каллеречоретурн</span><span class="sxs-lookup"><span data-stu-id="dfb17-399">CallerEchoReturn</span></span></p></td>
<td><p><span data-ttu-id="dfb17-400">целое</span><span class="sxs-lookup"><span data-stu-id="dfb17-400">int</span></span></p></td>
<td><p><span data-ttu-id="dfb17-401">Для вызывающего абонента возводится расширение возвращающего эха.</span><span class="sxs-lookup"><span data-stu-id="dfb17-401">Echo Return Loss Enhancement for the caller.</span></span> <span data-ttu-id="dfb17-402">Единицей измерения для этой метрики является dB.</span><span class="sxs-lookup"><span data-stu-id="dfb17-402">The unit for this metric is dB.</span></span> <span data-ttu-id="dfb17-403">Более низкие значения представляют менее эхо.</span><span class="sxs-lookup"><span data-stu-id="dfb17-403">Lower values represent less echo.</span></span> <span data-ttu-id="dfb17-404">Этот показатель не передается сервером Конференции и IP-телефонами по протоколу A/V.</span><span class="sxs-lookup"><span data-stu-id="dfb17-404">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfb17-405">каллерспеакерглитчрате</span><span class="sxs-lookup"><span data-stu-id="dfb17-405">CallerSpeakerGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="dfb17-406">целое</span><span class="sxs-lookup"><span data-stu-id="dfb17-406">int</span></span></p></td>
<td><p><span data-ttu-id="dfb17-407">Среднее число сбоев в течение пяти минут для отрисовки динамик вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="dfb17-407">Average glitches per five minutes for the caller’s loudspeaker rendering.</span></span> <span data-ttu-id="dfb17-408">Для хорошего качества это должно быть меньше, чем один за пять минут.</span><span class="sxs-lookup"><span data-stu-id="dfb17-408">For good quality, this should be less than one per five minutes.</span></span> <span data-ttu-id="dfb17-409">Не сообщается серверам конференц-связи, серверам или IP-телефонам.</span><span class="sxs-lookup"><span data-stu-id="dfb17-409">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfb17-410">каллермикглитчрате</span><span class="sxs-lookup"><span data-stu-id="dfb17-410">CallerMicGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="dfb17-411">целое</span><span class="sxs-lookup"><span data-stu-id="dfb17-411">int</span></span></p></td>
<td><p><span data-ttu-id="dfb17-412">Среднее число сбоев в течение пяти минут для захвата микрофона вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="dfb17-412">Average glitches per five minutes for the caller’s microphone capture.</span></span> <span data-ttu-id="dfb17-413">Для хорошего качества это должно быть менее чем на одну 5 минут.</span><span class="sxs-lookup"><span data-stu-id="dfb17-413">For good quality this should be less than one per five minutes.</span></span> <span data-ttu-id="dfb17-414">Не сообщается серверам конференц-связи, серверам или IP-телефонам.</span><span class="sxs-lookup"><span data-stu-id="dfb17-414">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfb17-415">каллертиместампдрифтратемик</span><span class="sxs-lookup"><span data-stu-id="dfb17-415">CallerTimestampDriftRateMic</span></span></p></td>
<td><p><span data-ttu-id="dfb17-416">десятичное число (9, 2)</span><span class="sxs-lookup"><span data-stu-id="dfb17-416">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="dfb17-417">Частота отсчета часов микрофона вызывающего устройства, относящихся к тактовой частоте процессора.</span><span class="sxs-lookup"><span data-stu-id="dfb17-417">Caller’s microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfb17-418">каллертиместампдрифтратеспк</span><span class="sxs-lookup"><span data-stu-id="dfb17-418">CallerTimestampDriftRateSpk</span></span></p></td>
<td><p><span data-ttu-id="dfb17-419">десятичное число (9, 2)</span><span class="sxs-lookup"><span data-stu-id="dfb17-419">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="dfb17-420">Частота отсчета сигналов для динамиков устройства выступающего в сторону от времени ЦП.</span><span class="sxs-lookup"><span data-stu-id="dfb17-420">Caller’s speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfb17-421">каллертиместамперрормикмс</span><span class="sxs-lookup"><span data-stu-id="dfb17-421">CallerTimestampErrorMicMs</span></span></p></td>
<td><p><span data-ttu-id="dfb17-422">десятичное число (9, 2)</span><span class="sxs-lookup"><span data-stu-id="dfb17-422">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="dfb17-423">Средняя пометка времени потока захвата микрофона в миллисекундах за последние 20 секунд звонка.</span><span class="sxs-lookup"><span data-stu-id="dfb17-423">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfb17-424">каллертиместамперрорспкмс</span><span class="sxs-lookup"><span data-stu-id="dfb17-424">CallerTimestampErrorSpkMs</span></span></p></td>
<td><p><span data-ttu-id="dfb17-425">десятичное число (9, 2)</span><span class="sxs-lookup"><span data-stu-id="dfb17-425">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="dfb17-426">Среднее значение ошибки метки времени линейного отображения динамика вызывающего абонента в миллисекундах за последние 20 секунд звонка.</span><span class="sxs-lookup"><span data-stu-id="dfb17-426">Average of the caller’s speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfb17-427">каллервсентрикаусес</span><span class="sxs-lookup"><span data-stu-id="dfb17-427">CallerVsEntryCauses</span></span></p></td>
<td><p><span data-ttu-id="dfb17-428">smallint</span><span class="sxs-lookup"><span data-stu-id="dfb17-428">smallint</span></span></p></td>
<td><p><span data-ttu-id="dfb17-429">Голосовая связь — это режим двусторонней печати с ограниченными возможностями перерывов.</span><span class="sxs-lookup"><span data-stu-id="dfb17-429">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="dfb17-430">Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-medialine-table.md">таблицей медиалине в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="dfb17-430">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfb17-431">каллеречоевенткаусес</span><span class="sxs-lookup"><span data-stu-id="dfb17-431">CallerEchoEventCauses</span></span></p></td>
<td><p><span data-ttu-id="dfb17-432">tinyint</span><span class="sxs-lookup"><span data-stu-id="dfb17-432">tinyint</span></span></p></td>
<td><p><span data-ttu-id="dfb17-433">Причины возникновения события echo для вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="dfb17-433">Causes of an echo event for the caller.</span></span> <span data-ttu-id="dfb17-434">Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-medialine-table.md">таблицей медиалине в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="dfb17-434">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfb17-435">каллеречоперцентмиЦин</span><span class="sxs-lookup"><span data-stu-id="dfb17-435">CallerEchoPercentMicIn</span></span></p></td>
<td><p><span data-ttu-id="dfb17-436">десятичное число (5; 2)</span><span class="sxs-lookup"><span data-stu-id="dfb17-436">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="dfb17-437">Процент времени, в течение которого обнаружено эхо в потоке захвата микрофона вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="dfb17-437">Percentage of time when echo is detected in the caller’s microphone capture stream.</span></span> <span data-ttu-id="dfb17-438">Если используется гарнитура, значение должно быть низким.</span><span class="sxs-lookup"><span data-stu-id="dfb17-438">If headset is used, the value should be low.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfb17-439">каллеречоперцентсенд</span><span class="sxs-lookup"><span data-stu-id="dfb17-439">CallerEchoPercentSend</span></span></p></td>
<td><p><span data-ttu-id="dfb17-440">десятичное число (5; 2)</span><span class="sxs-lookup"><span data-stu-id="dfb17-440">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="dfb17-441">Процент времени, в течение которого обнаружено эхо в потоке, отправленном вызывающим абонентом.</span><span class="sxs-lookup"><span data-stu-id="dfb17-441">Percentage of time when echo is detected in the caller’s sent stream.</span></span> <span data-ttu-id="dfb17-442">Высокий процент эха в потоках отправки указывает на наличие утечки эха.</span><span class="sxs-lookup"><span data-stu-id="dfb17-442">High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfb17-443">каллеррксагксигналлевел</span><span class="sxs-lookup"><span data-stu-id="dfb17-443">CallerRxAGCSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="dfb17-444">целое</span><span class="sxs-lookup"><span data-stu-id="dfb17-444">int</span></span></p></td>
<td><p><span data-ttu-id="dfb17-445">Уровень сигнала на сервере-источнике сообщений от шлюза к звуку вызывающего абонента; Это относится только к серверу обновлений.</span><span class="sxs-lookup"><span data-stu-id="dfb17-445">Received signal level on the Mediation Server from the Gateway for the caller’s audio; this applies only to the Mediation Server.</span></span> <span data-ttu-id="dfb17-446">Единица измерения этой метрики — Дбов.</span><span class="sxs-lookup"><span data-stu-id="dfb17-446">The unit of this metric is dBoV.</span></span> <span data-ttu-id="dfb17-447">Для хорошего качества допустимый диапазон должен составлять от-30 до-18 Дбов.</span><span class="sxs-lookup"><span data-stu-id="dfb17-447">For good quality, the acceptable range should be -30 to -18 dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfb17-448">каллеррксагкноиселевел</span><span class="sxs-lookup"><span data-stu-id="dfb17-448">CallerRxAGCNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="dfb17-449">целое</span><span class="sxs-lookup"><span data-stu-id="dfb17-449">int</span></span></p></td>
<td><p><span data-ttu-id="dfb17-450">Уровень сигнала на сервере-источнике от шлюза для звука вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="dfb17-450">Received signal level on the Mediation Server from the Gateway for the caller’s audio.</span></span> <span data-ttu-id="dfb17-451">Это относится только к серверу обновлений.</span><span class="sxs-lookup"><span data-stu-id="dfb17-451">This applies only to the Mediation Server.</span></span> <span data-ttu-id="dfb17-452">Единица измерения этой метрики — Дбов.</span><span class="sxs-lookup"><span data-stu-id="dfb17-452">The unit of this metric is dBoV.</span></span> <span data-ttu-id="dfb17-453">Для хорошего качества допустимый диапазон должен быть меньше, чем-50 Дбов.</span><span class="sxs-lookup"><span data-stu-id="dfb17-453">For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfb17-454">каллеррксагкгаин</span><span class="sxs-lookup"><span data-stu-id="dfb17-454">CallerRxAGCGain</span></span></p></td>
<td><p><span data-ttu-id="dfb17-455">целое</span><span class="sxs-lookup"><span data-stu-id="dfb17-455">int</span></span></p></td>
<td><p><span data-ttu-id="dfb17-456">Автоматический контроль усиления (АГК) на стороне сервера-посредника, примененной к звуковому каналу вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="dfb17-456">Automatic gain control (AGC) on the Mediation Server side applied to the caller’s audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfb17-457">каллеринитиалсигналлевелрмс</span><span class="sxs-lookup"><span data-stu-id="dfb17-457">CallerInitialSignalLevelRMS</span></span></p></td>
<td><p><span data-ttu-id="dfb17-458">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="dfb17-458">float</span></span></p></td>
<td><p><span data-ttu-id="dfb17-459">Среднее значение среднего квадрата входящего сигнала для вызывающего абонента до первых 30 секунд звонка.</span><span class="sxs-lookup"><span data-stu-id="dfb17-459">Root mean square (RMS) of the incoming signal to the caller for up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfb17-460">каллисендсигналлевел</span><span class="sxs-lookup"><span data-stu-id="dfb17-460">CalleeSendSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="dfb17-461">целое</span><span class="sxs-lookup"><span data-stu-id="dfb17-461">int</span></span></p></td>
<td><p><span data-ttu-id="dfb17-462">Представляет уровень звукового сигнала после аналогового усиления для звука, отправленного вызываемым абонентом.</span><span class="sxs-lookup"><span data-stu-id="dfb17-462">Represents the Post-Analog Gain Control audio signal level for the audio the callee sent.</span></span> <span data-ttu-id="dfb17-463">Единицей измерения для этой метрики является Дбмо.</span><span class="sxs-lookup"><span data-stu-id="dfb17-463">The unit for this metric is dBmo.</span></span> <span data-ttu-id="dfb17-464">Для приемлемого качества оно должно быть не менее 30 Дбмо.</span><span class="sxs-lookup"><span data-stu-id="dfb17-464">For acceptable quality, it should be at least 30 dBmo.</span></span> <span data-ttu-id="dfb17-465">Этот показатель не передается сервером Конференции и IP-телефонами по протоколу A/V.</span><span class="sxs-lookup"><span data-stu-id="dfb17-465">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfb17-466">каллиреквсигналлевел</span><span class="sxs-lookup"><span data-stu-id="dfb17-466">CalleeRecvSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="dfb17-467">целое</span><span class="sxs-lookup"><span data-stu-id="dfb17-467">int</span></span></p></td>
<td><p><span data-ttu-id="dfb17-468">Уровень звукового сигнала для звука, полученного вызываемым абонентом.</span><span class="sxs-lookup"><span data-stu-id="dfb17-468">Audio signal level for the audio the callee received.</span></span> <span data-ttu-id="dfb17-469">Единицей измерения для этой метрики является Дбмо.</span><span class="sxs-lookup"><span data-stu-id="dfb17-469">The unit for this metric is dBmo.</span></span> <span data-ttu-id="dfb17-470">Для приемлемого качества оно должно быть не менее 30 Дбмо.</span><span class="sxs-lookup"><span data-stu-id="dfb17-470">For acceptable quality, it should be at least 30 dBmo.</span></span> <span data-ttu-id="dfb17-471">Этот показатель не передается сервером Конференции и IP-телефонами по протоколу A/V.</span><span class="sxs-lookup"><span data-stu-id="dfb17-471">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfb17-472">каллисендноиселевел</span><span class="sxs-lookup"><span data-stu-id="dfb17-472">CalleeSendNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="dfb17-473">целое</span><span class="sxs-lookup"><span data-stu-id="dfb17-473">int</span></span></p></td>
<td><p><span data-ttu-id="dfb17-474">После аналогового усиления контрольного шума для звука, отправленного вызываемым абонентом.</span><span class="sxs-lookup"><span data-stu-id="dfb17-474">Post-Analog Gain Control audio noise level for the audio the callee sent.</span></span> <span data-ttu-id="dfb17-475">Единицей измерения для этой метрики является Дбмо.</span><span class="sxs-lookup"><span data-stu-id="dfb17-475">The unit for this metric is dBmo.</span></span> <span data-ttu-id="dfb17-476">Для приемлемого качества оно должно быть менее 35 Дбмо.</span><span class="sxs-lookup"><span data-stu-id="dfb17-476">For acceptable quality, it should be less than 35 dBmo.</span></span> <span data-ttu-id="dfb17-477">Этот показатель не передается сервером Конференции и IP-телефонами по протоколу A/V.</span><span class="sxs-lookup"><span data-stu-id="dfb17-477">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfb17-478">каллиреквноиселевел</span><span class="sxs-lookup"><span data-stu-id="dfb17-478">CalleeRecvNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="dfb17-479">целое</span><span class="sxs-lookup"><span data-stu-id="dfb17-479">int</span></span></p></td>
<td><p><span data-ttu-id="dfb17-480">После аналогового усиления контрольного шума для звука, полученного вызывающим абонентом, на уровне звука.</span><span class="sxs-lookup"><span data-stu-id="dfb17-480">Post-Analog Gain Control audio noise level for the audio the callee received.</span></span> <span data-ttu-id="dfb17-481">Единицей измерения для этой метрики является Дбмо.</span><span class="sxs-lookup"><span data-stu-id="dfb17-481">The unit for this metric is dBmo.</span></span> <span data-ttu-id="dfb17-482">Для приемлемого качества оно должно быть менее 35 Дбмо.</span><span class="sxs-lookup"><span data-stu-id="dfb17-482">For acceptable quality, it should be less than 35 dBmo.</span></span> <span data-ttu-id="dfb17-483">Этот показатель не передается сервером Конференции и IP-телефонами по протоколу A/V.</span><span class="sxs-lookup"><span data-stu-id="dfb17-483">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfb17-484">каллиечоретурн</span><span class="sxs-lookup"><span data-stu-id="dfb17-484">CalleeEchoReturn</span></span></p></td>
<td><p><span data-ttu-id="dfb17-485">целое</span><span class="sxs-lookup"><span data-stu-id="dfb17-485">int</span></span></p></td>
<td><p><span data-ttu-id="dfb17-486">Для вызываемого функции возвращаются улучшения с потерей эха.</span><span class="sxs-lookup"><span data-stu-id="dfb17-486">Echo Return Loss Enhancement for the callee.</span></span> <span data-ttu-id="dfb17-487">Единицей измерения для этой метрики является dB.</span><span class="sxs-lookup"><span data-stu-id="dfb17-487">The unit for this metric is dB.</span></span> <span data-ttu-id="dfb17-488">Более низкие значения представляют менее эхо.</span><span class="sxs-lookup"><span data-stu-id="dfb17-488">Lower values represent less echo.</span></span> <span data-ttu-id="dfb17-489">Этот показатель не передается сервером Конференции и IP-телефонами по протоколу A/V.</span><span class="sxs-lookup"><span data-stu-id="dfb17-489">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfb17-490">каллиспеакерглитчрате</span><span class="sxs-lookup"><span data-stu-id="dfb17-490">CalleeSpeakerGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="dfb17-491">целое</span><span class="sxs-lookup"><span data-stu-id="dfb17-491">int</span></span></p></td>
<td><p><span data-ttu-id="dfb17-492">Среднее число сбоев в течение пяти минут для отрисовки динамик вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="dfb17-492">Average glitches per five minutes for the callee’s loudspeaker rendering.</span></span> <span data-ttu-id="dfb17-493">Для хорошего качества это должно быть меньше, чем один за пять минут.</span><span class="sxs-lookup"><span data-stu-id="dfb17-493">For good quality, this should be less than one per five minutes.</span></span> <span data-ttu-id="dfb17-494">Не сообщается серверам конференц-связи, серверам или IP-телефонам.</span><span class="sxs-lookup"><span data-stu-id="dfb17-494">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfb17-495">каллимикглитчрате</span><span class="sxs-lookup"><span data-stu-id="dfb17-495">CalleeMicGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="dfb17-496">целое</span><span class="sxs-lookup"><span data-stu-id="dfb17-496">int</span></span></p></td>
<td><p><span data-ttu-id="dfb17-497">Среднее число сбоев в течение пяти минут для захвата микрофона вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="dfb17-497">Average glitches per five minutes for the callee’s microphone capture.</span></span> <span data-ttu-id="dfb17-498">Для хорошего качества это должно быть менее чем на одну 5 минут.</span><span class="sxs-lookup"><span data-stu-id="dfb17-498">For good quality this should be less than one per five minutes.</span></span> <span data-ttu-id="dfb17-499">Не сообщается серверам конференц-связи, серверам или IP-телефонам.</span><span class="sxs-lookup"><span data-stu-id="dfb17-499">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfb17-500">каллитиместампдрифтратемик</span><span class="sxs-lookup"><span data-stu-id="dfb17-500">CalleeTimestampDriftRateMic</span></span></p></td>
<td><p><span data-ttu-id="dfb17-501">десятичное число (9, 2)</span><span class="sxs-lookup"><span data-stu-id="dfb17-501">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="dfb17-502">Частота отсчета часов микрофона для вызываемого абонента в соответствии с тактовой частотой процессора.</span><span class="sxs-lookup"><span data-stu-id="dfb17-502">Callee’s microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfb17-503">каллитиместампдрифтратеспк</span><span class="sxs-lookup"><span data-stu-id="dfb17-503">CalleeTimestampDriftRateSpk</span></span></p></td>
<td><p><span data-ttu-id="dfb17-504">десятичное число (9, 2)</span><span class="sxs-lookup"><span data-stu-id="dfb17-504">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="dfb17-505">Частота отсчета звукового сигнала устройства вызываемого абонента в соответствии с тактовой частотой процессора.</span><span class="sxs-lookup"><span data-stu-id="dfb17-505">Callee’s speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfb17-506">каллитиместамперрормикмс</span><span class="sxs-lookup"><span data-stu-id="dfb17-506">CalleeTimestampErrorMicMs</span></span></p></td>
<td><p><span data-ttu-id="dfb17-507">десятичное число (9, 2)</span><span class="sxs-lookup"><span data-stu-id="dfb17-507">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="dfb17-508">Средняя пометка времени потока захвата микрофона в миллисекундах за последние 20 секунд звонка.</span><span class="sxs-lookup"><span data-stu-id="dfb17-508">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfb17-509">каллитиместамперрорспкмс</span><span class="sxs-lookup"><span data-stu-id="dfb17-509">CalleeTimestampErrorSpkMs</span></span></p></td>
<td><p><span data-ttu-id="dfb17-510">десятичное число (9, 2)</span><span class="sxs-lookup"><span data-stu-id="dfb17-510">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="dfb17-511">Среднее сообщение об ошибке пометки времени линейного отображения динамика в миллисекундах за последние 20 секунд звонка.</span><span class="sxs-lookup"><span data-stu-id="dfb17-511">Average of the callee’s speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfb17-512">калливсентрикаусес</span><span class="sxs-lookup"><span data-stu-id="dfb17-512">CalleeVsEntryCauses</span></span></p></td>
<td><p><span data-ttu-id="dfb17-513">smallint</span><span class="sxs-lookup"><span data-stu-id="dfb17-513">smallint</span></span></p></td>
<td><p><span data-ttu-id="dfb17-514">Голосовая связь — это режим двусторонней печати с ограниченными возможностями перерывов.</span><span class="sxs-lookup"><span data-stu-id="dfb17-514">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="dfb17-515">Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-medialine-table.md">таблицей медиалине в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="dfb17-515">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfb17-516">каллиечоевенткаусес</span><span class="sxs-lookup"><span data-stu-id="dfb17-516">CalleeEchoEventCauses</span></span></p></td>
<td><p><span data-ttu-id="dfb17-517">tinyint</span><span class="sxs-lookup"><span data-stu-id="dfb17-517">tinyint</span></span></p></td>
<td><p><span data-ttu-id="dfb17-518">Причины возникновения события echo для вызываемого объекта.</span><span class="sxs-lookup"><span data-stu-id="dfb17-518">Causes of an echo event for the callee.</span></span> <span data-ttu-id="dfb17-519">Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-medialine-table.md">таблицей медиалине в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="dfb17-519">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfb17-520">каллиечоперцентмиЦин</span><span class="sxs-lookup"><span data-stu-id="dfb17-520">CalleeEchoPercentMicIn</span></span></p></td>
<td><p><span data-ttu-id="dfb17-521">десятичное число (5; 2)</span><span class="sxs-lookup"><span data-stu-id="dfb17-521">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="dfb17-522">Процент времени, когда в потоке захвата микрофона вызываемого абонента будет обнаружено эхо.</span><span class="sxs-lookup"><span data-stu-id="dfb17-522">Percentage of time when echo is detected in the callee’s microphone capture stream.</span></span> <span data-ttu-id="dfb17-523">Если используется гарнитура, значение должно быть низким.</span><span class="sxs-lookup"><span data-stu-id="dfb17-523">If headset is used, the value should be low.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfb17-524">каллиечоперцентсенд</span><span class="sxs-lookup"><span data-stu-id="dfb17-524">CalleeEchoPercentSend</span></span></p></td>
<td><p><span data-ttu-id="dfb17-525">десятичное число (5; 2)</span><span class="sxs-lookup"><span data-stu-id="dfb17-525">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="dfb17-526">Процент времени, в течение которого обнаружено эхо в потоке, отправленном вызываемым абонентом.</span><span class="sxs-lookup"><span data-stu-id="dfb17-526">Percentage of time when echo is detected in the callee’s sent stream.</span></span> <span data-ttu-id="dfb17-527">Высокий процент эха в потоках отправки указывает на наличие утечки эха.</span><span class="sxs-lookup"><span data-stu-id="dfb17-527">High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfb17-528">каллирксагксигналлевел</span><span class="sxs-lookup"><span data-stu-id="dfb17-528">CalleeRxAGCSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="dfb17-529">целое</span><span class="sxs-lookup"><span data-stu-id="dfb17-529">int</span></span></p></td>
<td><p><span data-ttu-id="dfb17-530">Уровень сигнала на сервере-посреднике от шлюза для звука вызываемого абонента; Это относится только к серверу обновлений.</span><span class="sxs-lookup"><span data-stu-id="dfb17-530">Received signal level on the Mediation Server from the Gateway for the callee’s audio; this applies only to the Mediation Server.</span></span> <span data-ttu-id="dfb17-531">Единица измерения этой метрики — Дбов.</span><span class="sxs-lookup"><span data-stu-id="dfb17-531">The unit of this metric is dBoV.</span></span> <span data-ttu-id="dfb17-532">Для хорошего качества допустимый диапазон должен составлять от [-30 до-18] Дбов.</span><span class="sxs-lookup"><span data-stu-id="dfb17-532">For good quality, the acceptable range should be [-30 to -18] dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfb17-533">каллирксагкноиселевел</span><span class="sxs-lookup"><span data-stu-id="dfb17-533">CalleeRxAGCNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="dfb17-534">целое</span><span class="sxs-lookup"><span data-stu-id="dfb17-534">int</span></span></p></td>
<td><p><span data-ttu-id="dfb17-535">Уровень сигнала на сервере-посреднике от шлюза к звуковому каналу вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="dfb17-535">Received signal level on the Mediation Server from the Gateway for the callee’s audio.</span></span> <span data-ttu-id="dfb17-536">Это относится только к серверу обновлений.</span><span class="sxs-lookup"><span data-stu-id="dfb17-536">This applies only to the Mediation Server.</span></span> <span data-ttu-id="dfb17-537">Единица измерения этой метрики — Дбов.</span><span class="sxs-lookup"><span data-stu-id="dfb17-537">The unit of this metric is dBoV.</span></span> <span data-ttu-id="dfb17-538">Для хорошего качества допустимый диапазон должен быть меньше, чем-50 Дбов.</span><span class="sxs-lookup"><span data-stu-id="dfb17-538">For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfb17-539">каллирксагкгаин</span><span class="sxs-lookup"><span data-stu-id="dfb17-539">CalleeRxAGCGain</span></span></p></td>
<td><p><span data-ttu-id="dfb17-540">целое</span><span class="sxs-lookup"><span data-stu-id="dfb17-540">int</span></span></p></td>
<td><p><span data-ttu-id="dfb17-541">Функция автоматического усиления доступа (АГК) на стороне сервера-посредника, примененная к звуковому каналу вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="dfb17-541">Automatic gain control (AGC) on the Mediation Server side applied to the callee’s audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfb17-542">каллиинитиалсигналлевелрмс</span><span class="sxs-lookup"><span data-stu-id="dfb17-542">CalleeInitialSignalLevelRMS</span></span></p></td>
<td><p><span data-ttu-id="dfb17-543">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="dfb17-543">float</span></span></p></td>
<td><p><span data-ttu-id="dfb17-544">Среднее значение среднего квадрата (RMS) входящего сигнала для вызываемого абонента до первых 30 секунд звонка.</span><span class="sxs-lookup"><span data-stu-id="dfb17-544">Root mean square (RMS) of the incoming signal to the callee for up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfb17-545">ратиоконцеаледсамплесавг</span><span class="sxs-lookup"><span data-stu-id="dfb17-545">RatioConcealedSamplesAvg</span></span></p></td>
<td><p><span data-ttu-id="dfb17-546">десятичное число (5; 2)</span><span class="sxs-lookup"><span data-stu-id="dfb17-546">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="dfb17-547">Среднее отношение количества преобразованных образцов, созданных при воспроизведении звука, на обычные выборки.</span><span class="sxs-lookup"><span data-stu-id="dfb17-547">Average ratio of concealed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfb17-548">ратиостретчедсамплесавг</span><span class="sxs-lookup"><span data-stu-id="dfb17-548">RatioStretchedSamplesAvg</span></span></p></td>
<td><p><span data-ttu-id="dfb17-549">десятичное число (5; 2)</span><span class="sxs-lookup"><span data-stu-id="dfb17-549">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="dfb17-550">Среднее отношение растянутых образцов, созданных при воспроизведении звука, на обычные выборки.</span><span class="sxs-lookup"><span data-stu-id="dfb17-550">Average ratio of stretched samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfb17-551">ратиокомпресседсамплесавг</span><span class="sxs-lookup"><span data-stu-id="dfb17-551">RatioCompressedSamplesAvg</span></span></p></td>
<td><p><span data-ttu-id="dfb17-552">десятичное число (5; 2)</span><span class="sxs-lookup"><span data-stu-id="dfb17-552">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="dfb17-553">Среднее отношение количества сжатых образцов, созданных при восстановлении звука, на обычные образцы.</span><span class="sxs-lookup"><span data-stu-id="dfb17-553">Average ratio of compressed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfb17-554">RoundTrip</span><span class="sxs-lookup"><span data-stu-id="dfb17-554">RoundTrip</span></span></p></td>
<td><p><span data-ttu-id="dfb17-555">целое</span><span class="sxs-lookup"><span data-stu-id="dfb17-555">int</span></span></p></td>
<td><p><span data-ttu-id="dfb17-556">Время кругового приема из статистики РТКП.</span><span class="sxs-lookup"><span data-stu-id="dfb17-556">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfb17-557">раундтрипмакс</span><span class="sxs-lookup"><span data-stu-id="dfb17-557">RoundTripMax</span></span></p></td>
<td><p><span data-ttu-id="dfb17-558">целое</span><span class="sxs-lookup"><span data-stu-id="dfb17-558">int</span></span></p></td>
<td><p><span data-ttu-id="dfb17-559">Максимальное время кругового приема для звукового потока.</span><span class="sxs-lookup"><span data-stu-id="dfb17-559">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfb17-560">овераллавгнетворкмос</span><span class="sxs-lookup"><span data-stu-id="dfb17-560">OverallAvgNetworkMOS</span></span></p></td>
<td><p><span data-ttu-id="dfb17-561">десятичное число (3, 2)</span><span class="sxs-lookup"><span data-stu-id="dfb17-561">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="dfb17-562">Средняя сетевая MOS широкополосному для звонка.</span><span class="sxs-lookup"><span data-stu-id="dfb17-562">Average wideband Network MOS for the call.</span></span> <span data-ttu-id="dfb17-563">Эта метрика зависит от потерь пакетов, колебаний и используемого кодека.</span><span class="sxs-lookup"><span data-stu-id="dfb17-563">This metric depends on the packet loss, jitter, and codec used.</span></span> <span data-ttu-id="dfb17-564">Диапазон от 1,0 до 5,0.</span><span class="sxs-lookup"><span data-stu-id="dfb17-564">Range is 1.0 to 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfb17-565">овераллминнетворкмос</span><span class="sxs-lookup"><span data-stu-id="dfb17-565">OverallMinNetworkMOS</span></span></p></td>
<td><p><span data-ttu-id="dfb17-566">десятичное число (3, 2)</span><span class="sxs-lookup"><span data-stu-id="dfb17-566">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="dfb17-567">Минимальная широкополосному сети MOS для звонка.</span><span class="sxs-lookup"><span data-stu-id="dfb17-567">Minimum wideband Network MOS for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfb17-568">сендлистенмос</span><span class="sxs-lookup"><span data-stu-id="dfb17-568">SendListenMOS</span></span></p></td>
<td><p><span data-ttu-id="dfb17-569">десятичное число (3, 2)</span><span class="sxs-lookup"><span data-stu-id="dfb17-569">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="dfb17-570">Средняя прогнозируемая широкополосному прослушивания MOS для звукового сигнала, в том числе уровней речи, шума и характеристик устройства захвата.</span><span class="sxs-lookup"><span data-stu-id="dfb17-570">Average predicted wideband Listening MOS score for audio sent, including speech level, noise level and capture device characteristics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfb17-571">сендлистенмосмин</span><span class="sxs-lookup"><span data-stu-id="dfb17-571">SendListenMOSMin</span></span></p></td>
<td><p><span data-ttu-id="dfb17-572">десятичное число (3, 2)</span><span class="sxs-lookup"><span data-stu-id="dfb17-572">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="dfb17-573">Минимальная Сендлистенмос для звонка.</span><span class="sxs-lookup"><span data-stu-id="dfb17-573">Minimum SendListenMOS for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfb17-574">реквлистенмос</span><span class="sxs-lookup"><span data-stu-id="dfb17-574">RecvListenMOS</span></span></p></td>
<td><p><span data-ttu-id="dfb17-575">десятичное число (3, 2)</span><span class="sxs-lookup"><span data-stu-id="dfb17-575">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="dfb17-576">Средняя прогнозируемая широкополосному прослушивания MOS для звуковых сообщений, полученных из сети, включая уровень речи, уровень шума, кодек, условия сети и характеристики устройства захвата.</span><span class="sxs-lookup"><span data-stu-id="dfb17-576">Average predicted wideband Listening MOS score for audio received from the network including speech level, noise level, codec, network conditions and capture device characteristics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfb17-577">реквлистенмосмин</span><span class="sxs-lookup"><span data-stu-id="dfb17-577">RecvListenMOSMin</span></span></p></td>
<td><p><span data-ttu-id="dfb17-578">десятичное число (3, 2)</span><span class="sxs-lookup"><span data-stu-id="dfb17-578">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="dfb17-579">Минимальная Реквлистенмос для звонка.</span><span class="sxs-lookup"><span data-stu-id="dfb17-579">Minimum RecvListenMOS for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfb17-580">аудиофекусед</span><span class="sxs-lookup"><span data-stu-id="dfb17-580">AudioFECUsed</span></span></p></td>
<td><p><span data-ttu-id="dfb17-581">бит</span><span class="sxs-lookup"><span data-stu-id="dfb17-581">bit</span></span></p></td>
<td><p><span data-ttu-id="dfb17-582">Указывает, был ли использован голосовой FEC для звонка.</span><span class="sxs-lookup"><span data-stu-id="dfb17-582">Indicates whether audio FEC was used for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfb17-583">сендерискаллерпаи</span><span class="sxs-lookup"><span data-stu-id="dfb17-583">SenderIsCallerPAI</span></span></p></td>
<td><p><span data-ttu-id="dfb17-584">бит</span><span class="sxs-lookup"><span data-stu-id="dfb17-584">bit</span></span></p></td>
<td><p><span data-ttu-id="dfb17-585">Указывает направление, в котором определяются p-утвержденные сведения; 1 — направление потока на вызываемый абонентом. 0 — направление потока из вызываемого объекта вызывающему абоненту.</span><span class="sxs-lookup"><span data-stu-id="dfb17-585">Indicates direction of the p-asserted identify information; 1 means the stream direction is from the caller to the callee; 0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

