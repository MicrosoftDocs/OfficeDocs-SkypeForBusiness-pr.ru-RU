---
title: 'Lync Server 2013: представление Видеостреамдетаил'
description: 'Lync Server 2013: представление Видеостреамдетаил.'
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
ms.openlocfilehash: a3f420c292627d15fd0d54f2eba01c565a49a72d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567975"
---
# <a name="videostreamdetail-view-in-lync-server-2013"></a><span data-ttu-id="8532f-103">Представление Видеостреамдетаил в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8532f-103">VideoStreamDetail view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8532f-104">_**Последнее изменение темы:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="8532f-104">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="8532f-105">Представление VideoStreamDetail хранит сведения о каждом видеопотоке в базе данных.</span><span class="sxs-lookup"><span data-stu-id="8532f-105">The VideoStreamDetail View stores information about each video stream in the database.</span></span> <span data-ttu-id="8532f-106">Это представление было представлено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8532f-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8532f-107">Столбец</span><span class="sxs-lookup"><span data-stu-id="8532f-107">Column</span></span></th>
<th><span data-ttu-id="8532f-108">Тип данных</span><span class="sxs-lookup"><span data-stu-id="8532f-108">Data Type</span></span></th>
<th><span data-ttu-id="8532f-109">Описание</span><span class="sxs-lookup"><span data-stu-id="8532f-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8532f-110">сессионтиме</span><span class="sxs-lookup"><span data-stu-id="8532f-110">SessionTime</span></span></p></td>
<td><p><span data-ttu-id="8532f-111">datetime</span><span class="sxs-lookup"><span data-stu-id="8532f-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="8532f-112">Ссылка из <a href="lync-server-2013-medialine-table.md">таблицы MediaLine в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="8532f-112">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8532f-113">сессионсек</span><span class="sxs-lookup"><span data-stu-id="8532f-113">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="8532f-114">int</span><span class="sxs-lookup"><span data-stu-id="8532f-114">int</span></span></p></td>
<td><p><span data-ttu-id="8532f-115">Ссылка из <a href="lync-server-2013-medialine-table.md">таблицы MediaLine в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="8532f-115">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8532f-116">медиалинелабел</span><span class="sxs-lookup"><span data-stu-id="8532f-116">MediaLineLabel</span></span></p></td>
<td><p><span data-ttu-id="8532f-117">tinyint</span><span class="sxs-lookup"><span data-stu-id="8532f-117">tinyint</span></span></p></td>
<td><p><span data-ttu-id="8532f-118">Ссылка из <a href="lync-server-2013-medialine-table.md">таблицы MediaLine в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="8532f-118">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8532f-119">стреамид</span><span class="sxs-lookup"><span data-stu-id="8532f-119">StreamId</span></span></p></td>
<td><p><span data-ttu-id="8532f-120">int</span><span class="sxs-lookup"><span data-stu-id="8532f-120">int</span></span></p></td>
<td><p><span data-ttu-id="8532f-121">Уникальный идентификатор в линии мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="8532f-121">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8532f-122">StartTime</span><span class="sxs-lookup"><span data-stu-id="8532f-122">StartTime</span></span></p></td>
<td><p><span data-ttu-id="8532f-123">datetime</span><span class="sxs-lookup"><span data-stu-id="8532f-123">datetime</span></span></p></td>
<td><p><span data-ttu-id="8532f-124">Время начала сеанса.</span><span class="sxs-lookup"><span data-stu-id="8532f-124">Start time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8532f-125">EndTime</span><span class="sxs-lookup"><span data-stu-id="8532f-125">EndTime</span></span></p></td>
<td><p><span data-ttu-id="8532f-126">datetime</span><span class="sxs-lookup"><span data-stu-id="8532f-126">datetime</span></span></p></td>
<td><p><span data-ttu-id="8532f-127">Время окончания сеанса.</span><span class="sxs-lookup"><span data-stu-id="8532f-127">End time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8532f-128">каллприорити</span><span class="sxs-lookup"><span data-stu-id="8532f-128">CallPriority</span></span></p></td>
<td><p><span data-ttu-id="8532f-129">int</span><span class="sxs-lookup"><span data-stu-id="8532f-129">int</span></span></p></td>
<td><p><span data-ttu-id="8532f-130">Приоритет вызова.</span><span class="sxs-lookup"><span data-stu-id="8532f-130">Priority of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8532f-131">каллерпул</span><span class="sxs-lookup"><span data-stu-id="8532f-131">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="8532f-132">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="8532f-132">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8532f-133">Полное доменное имя пула вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="8532f-133">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8532f-134">каллипул</span><span class="sxs-lookup"><span data-stu-id="8532f-134">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="8532f-135">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="8532f-135">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8532f-136">Полное доменное имя пула вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="8532f-136">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8532f-137">Вызывающая сторона</span><span class="sxs-lookup"><span data-stu-id="8532f-137">Caller</span></span></p></td>
<td><p><span data-ttu-id="8532f-138">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="8532f-138">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="8532f-139">URI вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="8532f-139">Caller’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8532f-140">Вызываемого абонента</span><span class="sxs-lookup"><span data-stu-id="8532f-140">Callee</span></span></p></td>
<td><p><span data-ttu-id="8532f-141">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="8532f-141">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="8532f-142">URI вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="8532f-142">Callee’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8532f-143">каллерусеражент</span><span class="sxs-lookup"><span data-stu-id="8532f-143">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="8532f-144">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="8532f-144">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8532f-145">Строка агента пользователя вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="8532f-145">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8532f-146">каллерусераженттипе</span><span class="sxs-lookup"><span data-stu-id="8532f-146">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="8532f-147">smallint</span><span class="sxs-lookup"><span data-stu-id="8532f-147">smallint</span></span></p></td>
<td><p><span data-ttu-id="8532f-148">Тип агента пользователя звонящего абонента.</span><span class="sxs-lookup"><span data-stu-id="8532f-148">Type of caller’s user agent.</span></span> <span data-ttu-id="8532f-149">Дополнительные сведения см. <a href="lync-server-2013-useragent-table.md">в таблице UserAgent в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="8532f-149">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8532f-150">каллерусераженткатегори</span><span class="sxs-lookup"><span data-stu-id="8532f-150">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="8532f-151">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="8532f-151">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="8532f-152">Категория агента пользователя звонящего абонента.</span><span class="sxs-lookup"><span data-stu-id="8532f-152">Category of caller’s user agent.</span></span> <span data-ttu-id="8532f-153">Для получения подробных сведений ознакомьтесь со статьей <a href="lync-server-2013-useragentdef-table-qoe.md">таблица таблица useragentdef (QoE) в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="8532f-153">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8532f-154">каллиусеражент</span><span class="sxs-lookup"><span data-stu-id="8532f-154">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="8532f-155">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="8532f-155">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8532f-156">Строка агента пользователя вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="8532f-156">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8532f-157">каллиусераженттипе</span><span class="sxs-lookup"><span data-stu-id="8532f-157">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="8532f-158">smallint</span><span class="sxs-lookup"><span data-stu-id="8532f-158">smallint</span></span></p></td>
<td><p><span data-ttu-id="8532f-159">Тип агента пользователя вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="8532f-159">Type of callee’s user agent.</span></span> <span data-ttu-id="8532f-160">Сведения о том, как просмотреть <a href="lync-server-2013-useragent-table.md">таблицу UserAgent в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="8532f-160">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8532f-161">каллиусераженткатегори</span><span class="sxs-lookup"><span data-stu-id="8532f-161">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="8532f-162">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="8532f-162">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="8532f-163">Категория агента пользователя вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="8532f-163">Category of callee’s user agent.</span></span> <span data-ttu-id="8532f-164">Для получения дополнительных сведений смотрите <a href="lync-server-2013-useragentdef-table-qoe.md">таблицу таблица useragentdef (QoE) в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="8532f-164">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8532f-165">каллерендпоинт</span><span class="sxs-lookup"><span data-stu-id="8532f-165">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="8532f-166">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="8532f-166">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8532f-167">Имя конечной точки вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="8532f-167">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8532f-168">каллиендпоинт</span><span class="sxs-lookup"><span data-stu-id="8532f-168">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="8532f-169">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="8532f-169">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8532f-170">Имя конечной точки вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="8532f-170">Callee’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8532f-171">каллерос</span><span class="sxs-lookup"><span data-stu-id="8532f-171">CallerOS</span></span></p></td>
<td><p><span data-ttu-id="8532f-172">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="8532f-172">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="8532f-173">Операционная система конечной точки вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="8532f-173">Operating system (OS) of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8532f-174">каллиос</span><span class="sxs-lookup"><span data-stu-id="8532f-174">CalleeOS</span></span></p></td>
<td><p><span data-ttu-id="8532f-175">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="8532f-175">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="8532f-176">Операционная система конечной точки вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="8532f-176">Operating system (OS) of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8532f-177">каллеркпунаме</span><span class="sxs-lookup"><span data-stu-id="8532f-177">CallerCPUName</span></span></p></td>
<td><p><span data-ttu-id="8532f-178">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="8532f-178">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="8532f-179">Название ЦП конечной точки вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="8532f-179">CPU name of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8532f-180">калликпунаме</span><span class="sxs-lookup"><span data-stu-id="8532f-180">CalleeCPUName</span></span></p></td>
<td><p><span data-ttu-id="8532f-181">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="8532f-181">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="8532f-182">Название ЦП конечной точки вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="8532f-182">CPU name of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8532f-183">каллеркпунумберофкорес</span><span class="sxs-lookup"><span data-stu-id="8532f-183">CallerCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="8532f-184">smallint</span><span class="sxs-lookup"><span data-stu-id="8532f-184">smallint</span></span></p></td>
<td><p><span data-ttu-id="8532f-185">Число ядер ЦП конечной точки звонящего абонента.</span><span class="sxs-lookup"><span data-stu-id="8532f-185">Number of CPU cores of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8532f-186">калликпунумберофкорес</span><span class="sxs-lookup"><span data-stu-id="8532f-186">CalleeCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="8532f-187">smallint</span><span class="sxs-lookup"><span data-stu-id="8532f-187">smallint</span></span></p></td>
<td><p><span data-ttu-id="8532f-188">Число ядер ЦП конечной точки вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="8532f-188">Number of CPU cores of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8532f-189">каллеркпупроцессорспид</span><span class="sxs-lookup"><span data-stu-id="8532f-189">CallerCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="8532f-190">int</span><span class="sxs-lookup"><span data-stu-id="8532f-190">int</span></span></p></td>
<td><p><span data-ttu-id="8532f-191">Скорость ЦП конечной точки вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="8532f-191">CPU processor speed of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8532f-192">калликпупроцессорспид</span><span class="sxs-lookup"><span data-stu-id="8532f-192">CalleeCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="8532f-193">int</span><span class="sxs-lookup"><span data-stu-id="8532f-193">int</span></span></p></td>
<td><p><span data-ttu-id="8532f-194">Скорость ЦП конечной точки вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="8532f-194">CPU processor speed of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8532f-195">каллервиртуализатионфлаг</span><span class="sxs-lookup"><span data-stu-id="8532f-195">CallerVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="8532f-196">tinyint</span><span class="sxs-lookup"><span data-stu-id="8532f-196">tinyint</span></span></p></td>
<td><p><span data-ttu-id="8532f-197">Указывает, работает ли система вызывающего абонента в виртуализованной среде.</span><span class="sxs-lookup"><span data-stu-id="8532f-197">Indicates whether the caller’s system is running in a virtualized environment.</span></span> <span data-ttu-id="8532f-198">Более подробную информацию можно узнать <a href="lync-server-2013-endpoint-table.md">в таблице конечная точка в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="8532f-198">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8532f-199">калливиртуализатионфлаг</span><span class="sxs-lookup"><span data-stu-id="8532f-199">CalleeVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="8532f-200">tinyint</span><span class="sxs-lookup"><span data-stu-id="8532f-200">tinyint</span></span></p></td>
<td><p><span data-ttu-id="8532f-201">Указывает, работает ли система вызываемого абонента в виртуализованной среде.</span><span class="sxs-lookup"><span data-stu-id="8532f-201">Indicates whether the callee’s system is running in a virtualized environment.</span></span> <span data-ttu-id="8532f-202">Более подробную информацию можно узнать <a href="lync-server-2013-endpoint-table.md">в таблице конечная точка в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="8532f-202">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8532f-203">коннективитице</span><span class="sxs-lookup"><span data-stu-id="8532f-203">ConnectivityIce</span></span></p></td>
<td><p><span data-ttu-id="8532f-204">tinyint</span><span class="sxs-lookup"><span data-stu-id="8532f-204">tinyint</span></span></p></td>
<td><p><span data-ttu-id="8532f-205">Информация о пути к носителю, например прямой или с ретрансляцией.</span><span class="sxs-lookup"><span data-stu-id="8532f-205">Information about media path, such as direct or relayed.</span></span> <span data-ttu-id="8532f-206">Дополнительные сведения см. <a href="lync-server-2013-medialine-table.md">в таблице MediaLine в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="8532f-206">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8532f-207">каллерицеварнингфлагс</span><span class="sxs-lookup"><span data-stu-id="8532f-207">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="8532f-208">int</span><span class="sxs-lookup"><span data-stu-id="8532f-208">int</span></span></p></td>
<td><p><span data-ttu-id="8532f-p109">Сведения о технологии ICE (Interactive Connectivity Establishment), описанные в битовых флагах, для вызывающего абонента. Дополнительные сведения см. в спецификации протокола сервера мониторинга качества взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="8532f-p109">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8532f-211">каллиицеварнингфлагс</span><span class="sxs-lookup"><span data-stu-id="8532f-211">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="8532f-212">int</span><span class="sxs-lookup"><span data-stu-id="8532f-212">int</span></span></p></td>
<td><p><span data-ttu-id="8532f-p110">Сведения о технологии ICE (Interactive Connectivity Establishment), описанные в битовых флагах, для вызываемого абонента. Дополнительные сведения см. в спецификации протокола сервера мониторинга качества взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="8532f-p110">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8532f-215">Transport</span><span class="sxs-lookup"><span data-stu-id="8532f-215">Transport</span></span></p></td>
<td><p><span data-ttu-id="8532f-216">int</span><span class="sxs-lookup"><span data-stu-id="8532f-216">int</span></span></p></td>
<td><p><span data-ttu-id="8532f-217">Вид транспорта: 0 — UDP, 1 — TCP.</span><span class="sxs-lookup"><span data-stu-id="8532f-217">Transport type: 0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8532f-218">каллерипаддр</span><span class="sxs-lookup"><span data-stu-id="8532f-218">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="8532f-219">var (50)</span><span class="sxs-lookup"><span data-stu-id="8532f-219">var(50)</span></span></p></td>
<td><p><span data-ttu-id="8532f-220">IP-адрес вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="8532f-220">IP address of the caller.</span></span> <span data-ttu-id="8532f-221">Это может быть IPv4-адрес или IPv6-адрес.</span><span class="sxs-lookup"><span data-stu-id="8532f-221">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8532f-222">каллерпорт</span><span class="sxs-lookup"><span data-stu-id="8532f-222">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="8532f-223">int</span><span class="sxs-lookup"><span data-stu-id="8532f-223">int</span></span></p></td>
<td><p><span data-ttu-id="8532f-224">Порт, используемый вызывающим абонентом.</span><span class="sxs-lookup"><span data-stu-id="8532f-224">Port used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8532f-225">каллеринсиде</span><span class="sxs-lookup"><span data-stu-id="8532f-225">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="8532f-226">Битовая</span><span class="sxs-lookup"><span data-stu-id="8532f-226">bit</span></span></p></td>
<td><p><span data-ttu-id="8532f-p112">Указывает, находится ли звонящий абонент внутри сети организации: 1 означает, что абонент внутри корпоративной сети, 0 — абонент вне сети.</span><span class="sxs-lookup"><span data-stu-id="8532f-p112">Indicates whether the caller is inside the organization network. 1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8532f-229">каллиипаддр</span><span class="sxs-lookup"><span data-stu-id="8532f-229">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="8532f-230">var (50)</span><span class="sxs-lookup"><span data-stu-id="8532f-230">var(50)</span></span></p></td>
<td><p><span data-ttu-id="8532f-231">IP-адрес вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="8532f-231">IP address of the callee.</span></span> <span data-ttu-id="8532f-232">Это может быть IPv4-адрес или IPv6-адрес.</span><span class="sxs-lookup"><span data-stu-id="8532f-232">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8532f-233">каллипорт</span><span class="sxs-lookup"><span data-stu-id="8532f-233">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="8532f-234">int</span><span class="sxs-lookup"><span data-stu-id="8532f-234">int</span></span></p></td>
<td><p><span data-ttu-id="8532f-235">Порт, используемый вызываемым абонентом.</span><span class="sxs-lookup"><span data-stu-id="8532f-235">Port used by the callee.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8532f-236">каллиинсиде</span><span class="sxs-lookup"><span data-stu-id="8532f-236">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="8532f-237">Битовая</span><span class="sxs-lookup"><span data-stu-id="8532f-237">bit</span></span></p></td>
<td><p><span data-ttu-id="8532f-238">Указывает, находится ли вызываемый абонент внутри сети организации: 1 означает, что абонент внутри корпоративной сети, 0 — абонент вне сети.</span><span class="sxs-lookup"><span data-stu-id="8532f-238">Indicates whether the caller is inside the organization network.1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8532f-239">каллерусерсите</span><span class="sxs-lookup"><span data-stu-id="8532f-239">CallerUserSite</span></span></p></td>
<td><p><span data-ttu-id="8532f-240">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="8532f-240">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="8532f-241">Имя сайта вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="8532f-241">Name of the caller’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8532f-242">каллеррегион</span><span class="sxs-lookup"><span data-stu-id="8532f-242">CallerRegion</span></span></p></td>
<td><p><span data-ttu-id="8532f-243">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="8532f-243">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="8532f-244">Название страны или региона, где находится сайт вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="8532f-244">Name of the country/region of the caller’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8532f-245">каллиусерсите</span><span class="sxs-lookup"><span data-stu-id="8532f-245">CalleeUserSite</span></span></p></td>
<td><p><span data-ttu-id="8532f-246">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="8532f-246">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="8532f-247">Имя сайта вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="8532f-247">Name of the callee’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8532f-248">каллирегион</span><span class="sxs-lookup"><span data-stu-id="8532f-248">CalleeRegion</span></span></p></td>
<td><p><span data-ttu-id="8532f-249">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="8532f-249">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="8532f-250">Название страны или региона, где находится сайт вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="8532f-250">Name of the country/region of the callee’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8532f-251">каллеррелайипаддр</span><span class="sxs-lookup"><span data-stu-id="8532f-251">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="8532f-252">var (50)</span><span class="sxs-lookup"><span data-stu-id="8532f-252">var(50)</span></span></p></td>
<td><p><span data-ttu-id="8532f-253">IP-адрес пограничной службы обработки аудио- и видеоданных, используемой вызывающим абонентом.</span><span class="sxs-lookup"><span data-stu-id="8532f-253">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="8532f-254">Дополнительные сведения см. <a href="lync-server-2013-ipaddress-table.md">в таблице IPAddress в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="8532f-254">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8532f-255">каллеррелайпорт</span><span class="sxs-lookup"><span data-stu-id="8532f-255">CallerRelayPort</span></span></p></td>
<td><p><span data-ttu-id="8532f-256">int</span><span class="sxs-lookup"><span data-stu-id="8532f-256">int</span></span></p></td>
<td><p><span data-ttu-id="8532f-257">Порт пограничной службы обмена аудио-видео данными, используемой звонящим абонентом.</span><span class="sxs-lookup"><span data-stu-id="8532f-257">Port on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8532f-258">каллирелайипаддр</span><span class="sxs-lookup"><span data-stu-id="8532f-258">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="8532f-259">var (50)</span><span class="sxs-lookup"><span data-stu-id="8532f-259">var(50)</span></span></p></td>
<td><p><span data-ttu-id="8532f-260">IP-адрес пограничной службы обработки аудио- и видеоданных, используемой вызываемым абонентом.</span><span class="sxs-lookup"><span data-stu-id="8532f-260">IP Address key of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="8532f-261">Дополнительные сведения см. <a href="lync-server-2013-ipaddress-table.md">в таблице IPAddress в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="8532f-261">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8532f-262">каллирелайпорт</span><span class="sxs-lookup"><span data-stu-id="8532f-262">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="8532f-263">int</span><span class="sxs-lookup"><span data-stu-id="8532f-263">int</span></span></p></td>
<td><p><span data-ttu-id="8532f-264">Порт пограничной службы обмена аудио-видео данными, используемой вызываемым абонентом.</span><span class="sxs-lookup"><span data-stu-id="8532f-264">Port on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8532f-265">каллеркаптуредев</span><span class="sxs-lookup"><span data-stu-id="8532f-265">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="8532f-266">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="8532f-266">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8532f-267">Имя устройства захвата вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="8532f-267">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8532f-268">каллеррендердев</span><span class="sxs-lookup"><span data-stu-id="8532f-268">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="8532f-269">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="8532f-269">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8532f-270">Имя устройства обработки вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="8532f-270">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8532f-271">каллеркаптуредевдривер</span><span class="sxs-lookup"><span data-stu-id="8532f-271">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="8532f-272">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="8532f-272">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8532f-273">Имя драйвера устройства захвата звонящего абонента.</span><span class="sxs-lookup"><span data-stu-id="8532f-273">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8532f-274">каллеррендердевдривер</span><span class="sxs-lookup"><span data-stu-id="8532f-274">CallerRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="8532f-275">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="8532f-275">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8532f-276">Имя драйвера для устройства обработки вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="8532f-276">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8532f-277">калликаптуредев</span><span class="sxs-lookup"><span data-stu-id="8532f-277">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="8532f-278">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="8532f-278">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8532f-279">Имя устройства захвата вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="8532f-279">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8532f-280">каллирендердев</span><span class="sxs-lookup"><span data-stu-id="8532f-280">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="8532f-281">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="8532f-281">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8532f-282">Имя устройства обработки звука вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="8532f-282">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8532f-283">каллекаптуредевдривер</span><span class="sxs-lookup"><span data-stu-id="8532f-283">CalleCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="8532f-284">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="8532f-284">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8532f-285">Имя драйвера для устройства захвата вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="8532f-285">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8532f-286">каллирендердевдривер</span><span class="sxs-lookup"><span data-stu-id="8532f-286">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="8532f-287">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="8532f-287">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8532f-288">Имя драйвера для устройства обработки вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="8532f-288">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8532f-289">каллернетворкконнектионтипе</span><span class="sxs-lookup"><span data-stu-id="8532f-289">CallerNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="8532f-290">tinyint</span><span class="sxs-lookup"><span data-stu-id="8532f-290">tinyint</span></span></p></td>
<td><p><span data-ttu-id="8532f-291">Тип подключения к сети вызывающего абонента: 0 — проводной, 1 — беспроводной.</span><span class="sxs-lookup"><span data-stu-id="8532f-291">Caller’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8532f-292">каллервпн</span><span class="sxs-lookup"><span data-stu-id="8532f-292">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="8532f-293">Битовая</span><span class="sxs-lookup"><span data-stu-id="8532f-293">bit</span></span></p></td>
<td><p><span data-ttu-id="8532f-p116">Указывает, подключен ли звонящий абонент через виртуальную частную сеть: 1 — виртуальная частная сеть (VPN), 0 — не VPN.</span><span class="sxs-lookup"><span data-stu-id="8532f-p116">Indicates whether or not the caller connected over a virtual private network. 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8532f-296">каллерлинкспид</span><span class="sxs-lookup"><span data-stu-id="8532f-296">CallerLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="8532f-297">десятичное число (18,)</span><span class="sxs-lookup"><span data-stu-id="8532f-297">decimal(18,)</span></span></p></td>
<td><p><span data-ttu-id="8532f-298">Скорость сетевого канала для звонящего абонента в бит/с.</span><span class="sxs-lookup"><span data-stu-id="8532f-298">Network link speed for the caller's endpoint in bps.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8532f-299">каллинетворкконнектионтипе</span><span class="sxs-lookup"><span data-stu-id="8532f-299">CalleeNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="8532f-300">tinyint</span><span class="sxs-lookup"><span data-stu-id="8532f-300">tinyint</span></span></p></td>
<td><p><span data-ttu-id="8532f-301">Тип подключения к сети вызываемого абонента: 0 — проводной, 1 — беспроводной.</span><span class="sxs-lookup"><span data-stu-id="8532f-301">Callee’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8532f-302">калливпн</span><span class="sxs-lookup"><span data-stu-id="8532f-302">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="8532f-303">Битовая</span><span class="sxs-lookup"><span data-stu-id="8532f-303">bit</span></span></p></td>
<td><p><span data-ttu-id="8532f-p117">Указывает, подключен ли вызываемый абонент через виртуальную частную сеть: 1 — виртуальная частная сеть (VPN), 0 — не VPN.</span><span class="sxs-lookup"><span data-stu-id="8532f-p117">Indicates whether or not the callee connected over a virtual private network. 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8532f-306">каллилинкспид</span><span class="sxs-lookup"><span data-stu-id="8532f-306">CalleeLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="8532f-307">десятичное число (18, 0)</span><span class="sxs-lookup"><span data-stu-id="8532f-307">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="8532f-308">Скорость сетевого канала для вызываемого абонента в бит/с.</span><span class="sxs-lookup"><span data-stu-id="8532f-308">Network link speed for the callee’s endpoint (in bps).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8532f-309">конверсатионалмос</span><span class="sxs-lookup"><span data-stu-id="8532f-309">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="8532f-310">десятичное число (3, 2)</span><span class="sxs-lookup"><span data-stu-id="8532f-310">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="8532f-311">Узкополосный MOS аудиосеансов (на основе обоих аудиопотоков).</span><span class="sxs-lookup"><span data-stu-id="8532f-311">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8532f-312">апплиедбандвидслимит</span><span class="sxs-lookup"><span data-stu-id="8532f-312">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="8532f-313">int</span><span class="sxs-lookup"><span data-stu-id="8532f-313">int</span></span></p></td>
<td><p><span data-ttu-id="8532f-p118">Фактическая пропускная способность, применяемая к данному потоку отправителя с различными параметрами политики (TURN, API, SDP, сервер политик и т. д.). Ее не следует путать с эффективной пропускной способностью, потому что эффективная пропускная способность может быть меньше в зависимости от оценки пропускной способности. По сути это в основном максимальная пропускная способность потока отправителя с учетом ограничений, наложенных оценкой пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="8532f-p118">Actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on). This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate. This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8532f-317">життеринтерарривал</span><span class="sxs-lookup"><span data-stu-id="8532f-317">JitterInterArrival</span></span></p></td>
<td><p><span data-ttu-id="8532f-318">int</span><span class="sxs-lookup"><span data-stu-id="8532f-318">int</span></span></p></td>
<td><p><span data-ttu-id="8532f-319">Средний уровень дрожания в сети на основе статистики протокола RTCP.</span><span class="sxs-lookup"><span data-stu-id="8532f-319">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8532f-320">життеринтерарривалмакс</span><span class="sxs-lookup"><span data-stu-id="8532f-320">JitterInterArrivalMax</span></span></p></td>
<td><p><span data-ttu-id="8532f-321">int</span><span class="sxs-lookup"><span data-stu-id="8532f-321">int</span></span></p></td>
<td><p><span data-ttu-id="8532f-322">Максимальное "дрожание" сети во время вызова.</span><span class="sxs-lookup"><span data-stu-id="8532f-322">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8532f-323">Обработки</span><span class="sxs-lookup"><span data-stu-id="8532f-323">RoundTrip</span></span></p></td>
<td><p><span data-ttu-id="8532f-324">int</span><span class="sxs-lookup"><span data-stu-id="8532f-324">int</span></span></p></td>
<td><p><span data-ttu-id="8532f-325">Время приема-передачи на основе статистики RTCP.</span><span class="sxs-lookup"><span data-stu-id="8532f-325">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8532f-326">раундтрипмакс</span><span class="sxs-lookup"><span data-stu-id="8532f-326">RoundTripMax</span></span></p></td>
<td><p><span data-ttu-id="8532f-327">int</span><span class="sxs-lookup"><span data-stu-id="8532f-327">int</span></span></p></td>
<td><p><span data-ttu-id="8532f-328">Максимальное время кругового пути для аудиопотока.</span><span class="sxs-lookup"><span data-stu-id="8532f-328">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8532f-329">паккетлоссрате</span><span class="sxs-lookup"><span data-stu-id="8532f-329">PacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="8532f-330">десятичное число (5, 4)</span><span class="sxs-lookup"><span data-stu-id="8532f-330">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="8532f-331">Средний коэффициент потерь пакетов в течение вызова.</span><span class="sxs-lookup"><span data-stu-id="8532f-331">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8532f-332">паккетлоссратемакс</span><span class="sxs-lookup"><span data-stu-id="8532f-332">PacketLossRateMax</span></span></p></td>
<td><p><span data-ttu-id="8532f-333">десятичное число (5, 4)</span><span class="sxs-lookup"><span data-stu-id="8532f-333">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="8532f-334">Максимальная наблюдаемая частота потери пакетов во время вызова.</span><span class="sxs-lookup"><span data-stu-id="8532f-334">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8532f-335">паккетутилизатион</span><span class="sxs-lookup"><span data-stu-id="8532f-335">PacketUtilization</span></span></p></td>
<td><p><span data-ttu-id="8532f-336">int</span><span class="sxs-lookup"><span data-stu-id="8532f-336">int</span></span></p></td>
<td><p><span data-ttu-id="8532f-337">Количество пакетов для видеопотока (RTP).</span><span class="sxs-lookup"><span data-stu-id="8532f-337">Packet count for the video stream (Real Time Transport Protocol, RTP).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8532f-338">Самый полоса пропускания</span><span class="sxs-lookup"><span data-stu-id="8532f-338">BandwidthEst</span></span></p></td>
<td><p><span data-ttu-id="8532f-339">int</span><span class="sxs-lookup"><span data-stu-id="8532f-339">int</span></span></p></td>
<td><p><span data-ttu-id="8532f-340">Оценка пропускной способности для аудиопотока.</span><span class="sxs-lookup"><span data-stu-id="8532f-340">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8532f-341">PayloadDescription</span><span class="sxs-lookup"><span data-stu-id="8532f-341">PayloadDescription</span></span></p></td>
<td><p><span data-ttu-id="8532f-342">int</span><span class="sxs-lookup"><span data-stu-id="8532f-342">int</span></span></p></td>
<td><p><span data-ttu-id="8532f-343">Аудиокодек, используемый для вызова, на который ссылается <a href="lync-server-2013-payloaddescription-table.md">таблица таблица payloaddescription в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="8532f-343">Audio codec used for the call, referenced from the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8532f-344">видеоресолутион</span><span class="sxs-lookup"><span data-stu-id="8532f-344">VideoResolution</span></span></p></td>
<td><p><span data-ttu-id="8532f-345">char (9)</span><span class="sxs-lookup"><span data-stu-id="8532f-345">char(9)</span></span></p></td>
<td><p><span data-ttu-id="8532f-p119">Разрешение видео в пикселах (ширина умножается на высоту в пикселах). Указывается как строка.</span><span class="sxs-lookup"><span data-stu-id="8532f-p119">Resolution of the video in pixels width multiplied by pixels height. Reported as a string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8532f-348">видеобитратеавг</span><span class="sxs-lookup"><span data-stu-id="8532f-348">VideoBitRateAvg</span></span></p></td>
<td><p><span data-ttu-id="8532f-349">int</span><span class="sxs-lookup"><span data-stu-id="8532f-349">int</span></span></p></td>
<td><p><span data-ttu-id="8532f-350">Средняя скорость передачи видеопотока.</span><span class="sxs-lookup"><span data-stu-id="8532f-350">Average bit rate of the video stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8532f-351">инбаундвидеофрамератеавг</span><span class="sxs-lookup"><span data-stu-id="8532f-351">InboundVideoFrameRateAvg</span></span></p></td>
<td><p><span data-ttu-id="8532f-352">десятичное число (9, 4)</span><span class="sxs-lookup"><span data-stu-id="8532f-352">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="8532f-353">Частота кадров полученного видео.</span><span class="sxs-lookup"><span data-stu-id="8532f-353">Frame rate of video received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8532f-354">аутбаундвидеофрамератеавг</span><span class="sxs-lookup"><span data-stu-id="8532f-354">OutboundVideoFrameRateAvg</span></span></p></td>
<td><p><span data-ttu-id="8532f-355">десятичное число (9, 4)</span><span class="sxs-lookup"><span data-stu-id="8532f-355">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="8532f-356">Частота кадров отправленного видео.</span><span class="sxs-lookup"><span data-stu-id="8532f-356">Frame rate of video sent.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8532f-357">виидеобитратемакс</span><span class="sxs-lookup"><span data-stu-id="8532f-357">ViideoBitRateMax</span></span></p></td>
<td><p><span data-ttu-id="8532f-358">int</span><span class="sxs-lookup"><span data-stu-id="8532f-358">int</span></span></p></td>
<td><p><span data-ttu-id="8532f-359">Максимальная скорость передачи видео в ходе видеосеанса.</span><span class="sxs-lookup"><span data-stu-id="8532f-359">Maximum video bit rate during the video session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8532f-360">видеопаккетлоссрате</span><span class="sxs-lookup"><span data-stu-id="8532f-360">VideoPacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="8532f-361">десятичное число (9, 4)</span><span class="sxs-lookup"><span data-stu-id="8532f-361">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="8532f-362">Скорость потери видеопакетов.</span><span class="sxs-lookup"><span data-stu-id="8532f-362">Rate at which video packets were lost.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8532f-363">видеофрамелоссрате</span><span class="sxs-lookup"><span data-stu-id="8532f-363">VideoFrameLossRate</span></span></p></td>
<td><p><span data-ttu-id="8532f-364">десятичное число (9.4)</span><span class="sxs-lookup"><span data-stu-id="8532f-364">decimal(9.4)</span></span></p></td>
<td><p><span data-ttu-id="8532f-365">Процент от общего числа потерянных видеокадров.</span><span class="sxs-lookup"><span data-stu-id="8532f-365">Percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8532f-366">видеофек</span><span class="sxs-lookup"><span data-stu-id="8532f-366">VideoFEC</span></span></p></td>
<td><p><span data-ttu-id="8532f-367">Битовая</span><span class="sxs-lookup"><span data-stu-id="8532f-367">bit</span></span></p></td>
<td><p><span data-ttu-id="8532f-368">Не используется.</span><span class="sxs-lookup"><span data-stu-id="8532f-368">Not used.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8532f-369">видеоаллокатебвавг</span><span class="sxs-lookup"><span data-stu-id="8532f-369">VideoAllocateBWAvg</span></span></p></td>
<td><p><span data-ttu-id="8532f-370">int</span><span class="sxs-lookup"><span data-stu-id="8532f-370">int</span></span></p></td>
<td><p><span data-ttu-id="8532f-371">Средний объем выделенной полосы пропускания для видео.</span><span class="sxs-lookup"><span data-stu-id="8532f-371">Average amount of bandwidth allocated for video.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8532f-372">видеолокалфрамелоссперцентажеавг</span><span class="sxs-lookup"><span data-stu-id="8532f-372">VideoLocalFrameLossPercentageAvg</span></span></p></td>
<td><p><span data-ttu-id="8532f-373">десятичное число (9.4)</span><span class="sxs-lookup"><span data-stu-id="8532f-373">decimal(9.4)</span></span></p></td>
<td><p><span data-ttu-id="8532f-374">Процент от общего числа потерянных видеокадров.</span><span class="sxs-lookup"><span data-stu-id="8532f-374">Percentage of total video frames that were lost.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8532f-375">сендерискаллерпаи</span><span class="sxs-lookup"><span data-stu-id="8532f-375">SenderIsCallerPAI</span></span></p></td>
<td><p><span data-ttu-id="8532f-376">Битовая</span><span class="sxs-lookup"><span data-stu-id="8532f-376">bit</span></span></p></td>
<td><p><span data-ttu-id="8532f-p120">Направление потока для Р-утверждаемой идентификационной информации. 1 означает направление потока от звонящего абонента к вызываемому абоненту; 0 направление от вызываемого к звонящему абоненту.</span><span class="sxs-lookup"><span data-stu-id="8532f-p120">Stream direction for p-asserted identity information. 1 means the stream direction is from the caller to the callee; 0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

