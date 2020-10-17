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
ms.openlocfilehash: 3d419800842fed080efe4005e7282a25c91f29df
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518526"
---
# <a name="videostreamdetail-view-in-lync-server-2013"></a><span data-ttu-id="f5257-102">Представление Видеостреамдетаил в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f5257-102">VideoStreamDetail view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f5257-103">_**Последнее изменение темы:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="f5257-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="f5257-104">Представление VideoStreamDetail хранит сведения о каждом видеопотоке в базе данных.</span><span class="sxs-lookup"><span data-stu-id="f5257-104">The VideoStreamDetail View stores information about each video stream in the database.</span></span> <span data-ttu-id="f5257-105">Это представление было представлено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f5257-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f5257-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="f5257-106">Column</span></span></th>
<th><span data-ttu-id="f5257-107">Тип данных</span><span class="sxs-lookup"><span data-stu-id="f5257-107">Data Type</span></span></th>
<th><span data-ttu-id="f5257-108">Описание</span><span class="sxs-lookup"><span data-stu-id="f5257-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f5257-109">сессионтиме</span><span class="sxs-lookup"><span data-stu-id="f5257-109">SessionTime</span></span></p></td>
<td><p><span data-ttu-id="f5257-110">datetime</span><span class="sxs-lookup"><span data-stu-id="f5257-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="f5257-111">Ссылка из <a href="lync-server-2013-medialine-table.md">таблицы MediaLine в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="f5257-111">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5257-112">сессионсек</span><span class="sxs-lookup"><span data-stu-id="f5257-112">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="f5257-113">int</span><span class="sxs-lookup"><span data-stu-id="f5257-113">int</span></span></p></td>
<td><p><span data-ttu-id="f5257-114">Ссылка из <a href="lync-server-2013-medialine-table.md">таблицы MediaLine в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="f5257-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5257-115">медиалинелабел</span><span class="sxs-lookup"><span data-stu-id="f5257-115">MediaLineLabel</span></span></p></td>
<td><p><span data-ttu-id="f5257-116">tinyint</span><span class="sxs-lookup"><span data-stu-id="f5257-116">tinyint</span></span></p></td>
<td><p><span data-ttu-id="f5257-117">Ссылка из <a href="lync-server-2013-medialine-table.md">таблицы MediaLine в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="f5257-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5257-118">стреамид</span><span class="sxs-lookup"><span data-stu-id="f5257-118">StreamId</span></span></p></td>
<td><p><span data-ttu-id="f5257-119">int</span><span class="sxs-lookup"><span data-stu-id="f5257-119">int</span></span></p></td>
<td><p><span data-ttu-id="f5257-120">Уникальный идентификатор в линии мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="f5257-120">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5257-121">StartTime</span><span class="sxs-lookup"><span data-stu-id="f5257-121">StartTime</span></span></p></td>
<td><p><span data-ttu-id="f5257-122">datetime</span><span class="sxs-lookup"><span data-stu-id="f5257-122">datetime</span></span></p></td>
<td><p><span data-ttu-id="f5257-123">Время начала сеанса.</span><span class="sxs-lookup"><span data-stu-id="f5257-123">Start time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5257-124">EndTime</span><span class="sxs-lookup"><span data-stu-id="f5257-124">EndTime</span></span></p></td>
<td><p><span data-ttu-id="f5257-125">datetime</span><span class="sxs-lookup"><span data-stu-id="f5257-125">datetime</span></span></p></td>
<td><p><span data-ttu-id="f5257-126">Время окончания сеанса.</span><span class="sxs-lookup"><span data-stu-id="f5257-126">End time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5257-127">каллприорити</span><span class="sxs-lookup"><span data-stu-id="f5257-127">CallPriority</span></span></p></td>
<td><p><span data-ttu-id="f5257-128">int</span><span class="sxs-lookup"><span data-stu-id="f5257-128">int</span></span></p></td>
<td><p><span data-ttu-id="f5257-129">Приоритет вызова.</span><span class="sxs-lookup"><span data-stu-id="f5257-129">Priority of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5257-130">каллерпул</span><span class="sxs-lookup"><span data-stu-id="f5257-130">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="f5257-131">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="f5257-131">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f5257-132">Полное доменное имя пула вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="f5257-132">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5257-133">каллипул</span><span class="sxs-lookup"><span data-stu-id="f5257-133">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="f5257-134">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="f5257-134">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f5257-135">Полное доменное имя пула вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="f5257-135">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5257-136">Вызывающая сторона</span><span class="sxs-lookup"><span data-stu-id="f5257-136">Caller</span></span></p></td>
<td><p><span data-ttu-id="f5257-137">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="f5257-137">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="f5257-138">URI вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="f5257-138">Caller’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5257-139">Вызываемого абонента</span><span class="sxs-lookup"><span data-stu-id="f5257-139">Callee</span></span></p></td>
<td><p><span data-ttu-id="f5257-140">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="f5257-140">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="f5257-141">URI вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="f5257-141">Callee’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5257-142">каллерусеражент</span><span class="sxs-lookup"><span data-stu-id="f5257-142">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="f5257-143">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="f5257-143">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f5257-144">Строка агента пользователя вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="f5257-144">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5257-145">каллерусераженттипе</span><span class="sxs-lookup"><span data-stu-id="f5257-145">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="f5257-146">smallint</span><span class="sxs-lookup"><span data-stu-id="f5257-146">smallint</span></span></p></td>
<td><p><span data-ttu-id="f5257-147">Тип агента пользователя звонящего абонента.</span><span class="sxs-lookup"><span data-stu-id="f5257-147">Type of caller’s user agent.</span></span> <span data-ttu-id="f5257-148">Дополнительные сведения см. <a href="lync-server-2013-useragent-table.md">в таблице UserAgent в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f5257-148">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5257-149">каллерусераженткатегори</span><span class="sxs-lookup"><span data-stu-id="f5257-149">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="f5257-150">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="f5257-150">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="f5257-151">Категория агента пользователя звонящего абонента.</span><span class="sxs-lookup"><span data-stu-id="f5257-151">Category of caller’s user agent.</span></span> <span data-ttu-id="f5257-152">Для получения подробных сведений ознакомьтесь со статьей <a href="lync-server-2013-useragentdef-table-qoe.md">таблица таблица useragentdef (QoE) в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f5257-152">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5257-153">каллиусеражент</span><span class="sxs-lookup"><span data-stu-id="f5257-153">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="f5257-154">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="f5257-154">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f5257-155">Строка агента пользователя вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="f5257-155">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5257-156">каллиусераженттипе</span><span class="sxs-lookup"><span data-stu-id="f5257-156">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="f5257-157">smallint</span><span class="sxs-lookup"><span data-stu-id="f5257-157">smallint</span></span></p></td>
<td><p><span data-ttu-id="f5257-158">Тип агента пользователя вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="f5257-158">Type of callee’s user agent.</span></span> <span data-ttu-id="f5257-159">Сведения о том, как просмотреть <a href="lync-server-2013-useragent-table.md">таблицу UserAgent в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f5257-159">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5257-160">каллиусераженткатегори</span><span class="sxs-lookup"><span data-stu-id="f5257-160">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="f5257-161">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="f5257-161">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="f5257-162">Категория агента пользователя вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="f5257-162">Category of callee’s user agent.</span></span> <span data-ttu-id="f5257-163">Для получения дополнительных сведений смотрите <a href="lync-server-2013-useragentdef-table-qoe.md">таблицу таблица useragentdef (QoE) в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f5257-163">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5257-164">каллерендпоинт</span><span class="sxs-lookup"><span data-stu-id="f5257-164">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="f5257-165">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="f5257-165">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f5257-166">Имя конечной точки вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="f5257-166">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5257-167">каллиендпоинт</span><span class="sxs-lookup"><span data-stu-id="f5257-167">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="f5257-168">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="f5257-168">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f5257-169">Имя конечной точки вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="f5257-169">Callee’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5257-170">каллерос</span><span class="sxs-lookup"><span data-stu-id="f5257-170">CallerOS</span></span></p></td>
<td><p><span data-ttu-id="f5257-171">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="f5257-171">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="f5257-172">Операционная система конечной точки вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="f5257-172">Operating system (OS) of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5257-173">каллиос</span><span class="sxs-lookup"><span data-stu-id="f5257-173">CalleeOS</span></span></p></td>
<td><p><span data-ttu-id="f5257-174">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="f5257-174">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="f5257-175">Операционная система конечной точки вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="f5257-175">Operating system (OS) of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5257-176">каллеркпунаме</span><span class="sxs-lookup"><span data-stu-id="f5257-176">CallerCPUName</span></span></p></td>
<td><p><span data-ttu-id="f5257-177">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="f5257-177">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="f5257-178">Название ЦП конечной точки вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="f5257-178">CPU name of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5257-179">калликпунаме</span><span class="sxs-lookup"><span data-stu-id="f5257-179">CalleeCPUName</span></span></p></td>
<td><p><span data-ttu-id="f5257-180">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="f5257-180">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="f5257-181">Название ЦП конечной точки вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="f5257-181">CPU name of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5257-182">каллеркпунумберофкорес</span><span class="sxs-lookup"><span data-stu-id="f5257-182">CallerCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="f5257-183">smallint</span><span class="sxs-lookup"><span data-stu-id="f5257-183">smallint</span></span></p></td>
<td><p><span data-ttu-id="f5257-184">Число ядер ЦП конечной точки звонящего абонента.</span><span class="sxs-lookup"><span data-stu-id="f5257-184">Number of CPU cores of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5257-185">калликпунумберофкорес</span><span class="sxs-lookup"><span data-stu-id="f5257-185">CalleeCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="f5257-186">smallint</span><span class="sxs-lookup"><span data-stu-id="f5257-186">smallint</span></span></p></td>
<td><p><span data-ttu-id="f5257-187">Число ядер ЦП конечной точки вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="f5257-187">Number of CPU cores of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5257-188">каллеркпупроцессорспид</span><span class="sxs-lookup"><span data-stu-id="f5257-188">CallerCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="f5257-189">int</span><span class="sxs-lookup"><span data-stu-id="f5257-189">int</span></span></p></td>
<td><p><span data-ttu-id="f5257-190">Скорость ЦП конечной точки вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="f5257-190">CPU processor speed of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5257-191">калликпупроцессорспид</span><span class="sxs-lookup"><span data-stu-id="f5257-191">CalleeCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="f5257-192">int</span><span class="sxs-lookup"><span data-stu-id="f5257-192">int</span></span></p></td>
<td><p><span data-ttu-id="f5257-193">Скорость ЦП конечной точки вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="f5257-193">CPU processor speed of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5257-194">каллервиртуализатионфлаг</span><span class="sxs-lookup"><span data-stu-id="f5257-194">CallerVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="f5257-195">tinyint</span><span class="sxs-lookup"><span data-stu-id="f5257-195">tinyint</span></span></p></td>
<td><p><span data-ttu-id="f5257-196">Указывает, работает ли система вызывающего абонента в виртуализованной среде.</span><span class="sxs-lookup"><span data-stu-id="f5257-196">Indicates whether the caller’s system is running in a virtualized environment.</span></span> <span data-ttu-id="f5257-197">Более подробную информацию можно узнать <a href="lync-server-2013-endpoint-table.md">в таблице конечная точка в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f5257-197">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5257-198">калливиртуализатионфлаг</span><span class="sxs-lookup"><span data-stu-id="f5257-198">CalleeVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="f5257-199">tinyint</span><span class="sxs-lookup"><span data-stu-id="f5257-199">tinyint</span></span></p></td>
<td><p><span data-ttu-id="f5257-200">Указывает, работает ли система вызываемого абонента в виртуализованной среде.</span><span class="sxs-lookup"><span data-stu-id="f5257-200">Indicates whether the callee’s system is running in a virtualized environment.</span></span> <span data-ttu-id="f5257-201">Более подробную информацию можно узнать <a href="lync-server-2013-endpoint-table.md">в таблице конечная точка в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f5257-201">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5257-202">коннективитице</span><span class="sxs-lookup"><span data-stu-id="f5257-202">ConnectivityIce</span></span></p></td>
<td><p><span data-ttu-id="f5257-203">tinyint</span><span class="sxs-lookup"><span data-stu-id="f5257-203">tinyint</span></span></p></td>
<td><p><span data-ttu-id="f5257-204">Информация о пути к носителю, например прямой или с ретрансляцией.</span><span class="sxs-lookup"><span data-stu-id="f5257-204">Information about media path, such as direct or relayed.</span></span> <span data-ttu-id="f5257-205">Дополнительные сведения см. <a href="lync-server-2013-medialine-table.md">в таблице MediaLine в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f5257-205">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5257-206">каллерицеварнингфлагс</span><span class="sxs-lookup"><span data-stu-id="f5257-206">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="f5257-207">int</span><span class="sxs-lookup"><span data-stu-id="f5257-207">int</span></span></p></td>
<td><p><span data-ttu-id="f5257-p109">Сведения о технологии ICE (Interactive Connectivity Establishment), описанные в битовых флагах, для вызывающего абонента. Дополнительные сведения см. в спецификации протокола сервера мониторинга качества взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="f5257-p109">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5257-210">каллиицеварнингфлагс</span><span class="sxs-lookup"><span data-stu-id="f5257-210">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="f5257-211">int</span><span class="sxs-lookup"><span data-stu-id="f5257-211">int</span></span></p></td>
<td><p><span data-ttu-id="f5257-p110">Сведения о технологии ICE (Interactive Connectivity Establishment), описанные в битовых флагах, для вызываемого абонента. Дополнительные сведения см. в спецификации протокола сервера мониторинга качества взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="f5257-p110">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5257-214">Transport</span><span class="sxs-lookup"><span data-stu-id="f5257-214">Transport</span></span></p></td>
<td><p><span data-ttu-id="f5257-215">int</span><span class="sxs-lookup"><span data-stu-id="f5257-215">int</span></span></p></td>
<td><p><span data-ttu-id="f5257-216">Вид транспорта: 0 — UDP, 1 — TCP.</span><span class="sxs-lookup"><span data-stu-id="f5257-216">Transport type: 0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5257-217">каллерипаддр</span><span class="sxs-lookup"><span data-stu-id="f5257-217">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="f5257-218">var (50)</span><span class="sxs-lookup"><span data-stu-id="f5257-218">var(50)</span></span></p></td>
<td><p><span data-ttu-id="f5257-219">IP-адрес вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="f5257-219">IP address of the caller.</span></span> <span data-ttu-id="f5257-220">Это может быть IPv4-адрес или IPv6-адрес.</span><span class="sxs-lookup"><span data-stu-id="f5257-220">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5257-221">каллерпорт</span><span class="sxs-lookup"><span data-stu-id="f5257-221">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="f5257-222">int</span><span class="sxs-lookup"><span data-stu-id="f5257-222">int</span></span></p></td>
<td><p><span data-ttu-id="f5257-223">Порт, используемый вызывающим абонентом.</span><span class="sxs-lookup"><span data-stu-id="f5257-223">Port used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5257-224">каллеринсиде</span><span class="sxs-lookup"><span data-stu-id="f5257-224">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="f5257-225">Битовая</span><span class="sxs-lookup"><span data-stu-id="f5257-225">bit</span></span></p></td>
<td><p><span data-ttu-id="f5257-p112">Указывает, находится ли звонящий абонент внутри сети организации: 1 означает, что абонент внутри корпоративной сети, 0 — абонент вне сети.</span><span class="sxs-lookup"><span data-stu-id="f5257-p112">Indicates whether the caller is inside the organization network. 1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5257-228">каллиипаддр</span><span class="sxs-lookup"><span data-stu-id="f5257-228">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="f5257-229">var (50)</span><span class="sxs-lookup"><span data-stu-id="f5257-229">var(50)</span></span></p></td>
<td><p><span data-ttu-id="f5257-230">IP-адрес вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="f5257-230">IP address of the callee.</span></span> <span data-ttu-id="f5257-231">Это может быть IPv4-адрес или IPv6-адрес.</span><span class="sxs-lookup"><span data-stu-id="f5257-231">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5257-232">каллипорт</span><span class="sxs-lookup"><span data-stu-id="f5257-232">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="f5257-233">int</span><span class="sxs-lookup"><span data-stu-id="f5257-233">int</span></span></p></td>
<td><p><span data-ttu-id="f5257-234">Порт, используемый вызываемым абонентом.</span><span class="sxs-lookup"><span data-stu-id="f5257-234">Port used by the callee.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5257-235">каллиинсиде</span><span class="sxs-lookup"><span data-stu-id="f5257-235">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="f5257-236">Битовая</span><span class="sxs-lookup"><span data-stu-id="f5257-236">bit</span></span></p></td>
<td><p><span data-ttu-id="f5257-237">Указывает, находится ли вызываемый абонент внутри сети организации: 1 означает, что абонент внутри корпоративной сети, 0 — абонент вне сети.</span><span class="sxs-lookup"><span data-stu-id="f5257-237">Indicates whether the caller is inside the organization network.1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5257-238">каллерусерсите</span><span class="sxs-lookup"><span data-stu-id="f5257-238">CallerUserSite</span></span></p></td>
<td><p><span data-ttu-id="f5257-239">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="f5257-239">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="f5257-240">Имя сайта вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="f5257-240">Name of the caller’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5257-241">каллеррегион</span><span class="sxs-lookup"><span data-stu-id="f5257-241">CallerRegion</span></span></p></td>
<td><p><span data-ttu-id="f5257-242">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="f5257-242">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="f5257-243">Название страны или региона, где находится сайт вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="f5257-243">Name of the country/region of the caller’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5257-244">каллиусерсите</span><span class="sxs-lookup"><span data-stu-id="f5257-244">CalleeUserSite</span></span></p></td>
<td><p><span data-ttu-id="f5257-245">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="f5257-245">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="f5257-246">Имя сайта вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="f5257-246">Name of the callee’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5257-247">каллирегион</span><span class="sxs-lookup"><span data-stu-id="f5257-247">CalleeRegion</span></span></p></td>
<td><p><span data-ttu-id="f5257-248">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="f5257-248">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="f5257-249">Название страны или региона, где находится сайт вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="f5257-249">Name of the country/region of the callee’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5257-250">каллеррелайипаддр</span><span class="sxs-lookup"><span data-stu-id="f5257-250">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="f5257-251">var (50)</span><span class="sxs-lookup"><span data-stu-id="f5257-251">var(50)</span></span></p></td>
<td><p><span data-ttu-id="f5257-252">IP-адрес пограничной службы обработки аудио- и видеоданных, используемой вызывающим абонентом.</span><span class="sxs-lookup"><span data-stu-id="f5257-252">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="f5257-253">Дополнительные сведения см. <a href="lync-server-2013-ipaddress-table.md">в таблице IPAddress в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f5257-253">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5257-254">каллеррелайпорт</span><span class="sxs-lookup"><span data-stu-id="f5257-254">CallerRelayPort</span></span></p></td>
<td><p><span data-ttu-id="f5257-255">int</span><span class="sxs-lookup"><span data-stu-id="f5257-255">int</span></span></p></td>
<td><p><span data-ttu-id="f5257-256">Порт пограничной службы обмена аудио-видео данными, используемой звонящим абонентом.</span><span class="sxs-lookup"><span data-stu-id="f5257-256">Port on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5257-257">каллирелайипаддр</span><span class="sxs-lookup"><span data-stu-id="f5257-257">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="f5257-258">var (50)</span><span class="sxs-lookup"><span data-stu-id="f5257-258">var(50)</span></span></p></td>
<td><p><span data-ttu-id="f5257-259">IP-адрес пограничной службы обработки аудио- и видеоданных, используемой вызываемым абонентом.</span><span class="sxs-lookup"><span data-stu-id="f5257-259">IP Address key of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="f5257-260">Дополнительные сведения см. <a href="lync-server-2013-ipaddress-table.md">в таблице IPAddress в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f5257-260">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5257-261">каллирелайпорт</span><span class="sxs-lookup"><span data-stu-id="f5257-261">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="f5257-262">int</span><span class="sxs-lookup"><span data-stu-id="f5257-262">int</span></span></p></td>
<td><p><span data-ttu-id="f5257-263">Порт пограничной службы обмена аудио-видео данными, используемой вызываемым абонентом.</span><span class="sxs-lookup"><span data-stu-id="f5257-263">Port on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5257-264">каллеркаптуредев</span><span class="sxs-lookup"><span data-stu-id="f5257-264">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="f5257-265">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="f5257-265">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f5257-266">Имя устройства захвата вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="f5257-266">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5257-267">каллеррендердев</span><span class="sxs-lookup"><span data-stu-id="f5257-267">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="f5257-268">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="f5257-268">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f5257-269">Имя устройства обработки вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="f5257-269">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5257-270">каллеркаптуредевдривер</span><span class="sxs-lookup"><span data-stu-id="f5257-270">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="f5257-271">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="f5257-271">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f5257-272">Имя драйвера устройства захвата звонящего абонента.</span><span class="sxs-lookup"><span data-stu-id="f5257-272">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5257-273">каллеррендердевдривер</span><span class="sxs-lookup"><span data-stu-id="f5257-273">CallerRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="f5257-274">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="f5257-274">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f5257-275">Имя драйвера для устройства обработки вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="f5257-275">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5257-276">калликаптуредев</span><span class="sxs-lookup"><span data-stu-id="f5257-276">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="f5257-277">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="f5257-277">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f5257-278">Имя устройства захвата вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="f5257-278">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5257-279">каллирендердев</span><span class="sxs-lookup"><span data-stu-id="f5257-279">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="f5257-280">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="f5257-280">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f5257-281">Имя устройства обработки звука вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="f5257-281">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5257-282">каллекаптуредевдривер</span><span class="sxs-lookup"><span data-stu-id="f5257-282">CalleCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="f5257-283">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="f5257-283">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f5257-284">Имя драйвера для устройства захвата вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="f5257-284">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5257-285">каллирендердевдривер</span><span class="sxs-lookup"><span data-stu-id="f5257-285">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="f5257-286">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="f5257-286">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f5257-287">Имя драйвера для устройства обработки вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="f5257-287">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5257-288">каллернетворкконнектионтипе</span><span class="sxs-lookup"><span data-stu-id="f5257-288">CallerNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="f5257-289">tinyint</span><span class="sxs-lookup"><span data-stu-id="f5257-289">tinyint</span></span></p></td>
<td><p><span data-ttu-id="f5257-290">Тип подключения к сети вызывающего абонента: 0 — проводной, 1 — беспроводной.</span><span class="sxs-lookup"><span data-stu-id="f5257-290">Caller’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5257-291">каллервпн</span><span class="sxs-lookup"><span data-stu-id="f5257-291">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="f5257-292">Битовая</span><span class="sxs-lookup"><span data-stu-id="f5257-292">bit</span></span></p></td>
<td><p><span data-ttu-id="f5257-p116">Указывает, подключен ли звонящий абонент через виртуальную частную сеть: 1 — виртуальная частная сеть (VPN), 0 — не VPN.</span><span class="sxs-lookup"><span data-stu-id="f5257-p116">Indicates whether or not the caller connected over a virtual private network. 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5257-295">каллерлинкспид</span><span class="sxs-lookup"><span data-stu-id="f5257-295">CallerLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="f5257-296">десятичное число (18,)</span><span class="sxs-lookup"><span data-stu-id="f5257-296">decimal(18,)</span></span></p></td>
<td><p><span data-ttu-id="f5257-297">Скорость сетевого канала для звонящего абонента в бит/с.</span><span class="sxs-lookup"><span data-stu-id="f5257-297">Network link speed for the caller's endpoint in bps.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5257-298">каллинетворкконнектионтипе</span><span class="sxs-lookup"><span data-stu-id="f5257-298">CalleeNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="f5257-299">tinyint</span><span class="sxs-lookup"><span data-stu-id="f5257-299">tinyint</span></span></p></td>
<td><p><span data-ttu-id="f5257-300">Тип подключения к сети вызываемого абонента: 0 — проводной, 1 — беспроводной.</span><span class="sxs-lookup"><span data-stu-id="f5257-300">Callee’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5257-301">калливпн</span><span class="sxs-lookup"><span data-stu-id="f5257-301">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="f5257-302">Битовая</span><span class="sxs-lookup"><span data-stu-id="f5257-302">bit</span></span></p></td>
<td><p><span data-ttu-id="f5257-p117">Указывает, подключен ли вызываемый абонент через виртуальную частную сеть: 1 — виртуальная частная сеть (VPN), 0 — не VPN.</span><span class="sxs-lookup"><span data-stu-id="f5257-p117">Indicates whether or not the callee connected over a virtual private network. 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5257-305">каллилинкспид</span><span class="sxs-lookup"><span data-stu-id="f5257-305">CalleeLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="f5257-306">десятичное число (18, 0)</span><span class="sxs-lookup"><span data-stu-id="f5257-306">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="f5257-307">Скорость сетевого канала для вызываемого абонента в бит/с.</span><span class="sxs-lookup"><span data-stu-id="f5257-307">Network link speed for the callee’s endpoint (in bps).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5257-308">конверсатионалмос</span><span class="sxs-lookup"><span data-stu-id="f5257-308">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="f5257-309">десятичное число (3, 2)</span><span class="sxs-lookup"><span data-stu-id="f5257-309">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="f5257-310">Узкополосный MOS аудиосеансов (на основе обоих аудиопотоков).</span><span class="sxs-lookup"><span data-stu-id="f5257-310">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5257-311">апплиедбандвидслимит</span><span class="sxs-lookup"><span data-stu-id="f5257-311">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="f5257-312">int</span><span class="sxs-lookup"><span data-stu-id="f5257-312">int</span></span></p></td>
<td><p><span data-ttu-id="f5257-p118">Фактическая пропускная способность, применяемая к данному потоку отправителя с различными параметрами политики (TURN, API, SDP, сервер политик и т. д.). Ее не следует путать с эффективной пропускной способностью, потому что эффективная пропускная способность может быть меньше в зависимости от оценки пропускной способности. По сути это в основном максимальная пропускная способность потока отправителя с учетом ограничений, наложенных оценкой пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="f5257-p118">Actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on). This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate. This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5257-316">життеринтерарривал</span><span class="sxs-lookup"><span data-stu-id="f5257-316">JitterInterArrival</span></span></p></td>
<td><p><span data-ttu-id="f5257-317">int</span><span class="sxs-lookup"><span data-stu-id="f5257-317">int</span></span></p></td>
<td><p><span data-ttu-id="f5257-318">Средний уровень дрожания в сети на основе статистики протокола RTCP.</span><span class="sxs-lookup"><span data-stu-id="f5257-318">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5257-319">життеринтерарривалмакс</span><span class="sxs-lookup"><span data-stu-id="f5257-319">JitterInterArrivalMax</span></span></p></td>
<td><p><span data-ttu-id="f5257-320">int</span><span class="sxs-lookup"><span data-stu-id="f5257-320">int</span></span></p></td>
<td><p><span data-ttu-id="f5257-321">Максимальное "дрожание" сети во время вызова.</span><span class="sxs-lookup"><span data-stu-id="f5257-321">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5257-322">Обработки</span><span class="sxs-lookup"><span data-stu-id="f5257-322">RoundTrip</span></span></p></td>
<td><p><span data-ttu-id="f5257-323">int</span><span class="sxs-lookup"><span data-stu-id="f5257-323">int</span></span></p></td>
<td><p><span data-ttu-id="f5257-324">Время приема-передачи на основе статистики RTCP.</span><span class="sxs-lookup"><span data-stu-id="f5257-324">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5257-325">раундтрипмакс</span><span class="sxs-lookup"><span data-stu-id="f5257-325">RoundTripMax</span></span></p></td>
<td><p><span data-ttu-id="f5257-326">int</span><span class="sxs-lookup"><span data-stu-id="f5257-326">int</span></span></p></td>
<td><p><span data-ttu-id="f5257-327">Максимальное время кругового пути для аудиопотока.</span><span class="sxs-lookup"><span data-stu-id="f5257-327">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5257-328">паккетлоссрате</span><span class="sxs-lookup"><span data-stu-id="f5257-328">PacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="f5257-329">десятичное число (5, 4)</span><span class="sxs-lookup"><span data-stu-id="f5257-329">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="f5257-330">Средний коэффициент потерь пакетов в течение вызова.</span><span class="sxs-lookup"><span data-stu-id="f5257-330">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5257-331">паккетлоссратемакс</span><span class="sxs-lookup"><span data-stu-id="f5257-331">PacketLossRateMax</span></span></p></td>
<td><p><span data-ttu-id="f5257-332">десятичное число (5, 4)</span><span class="sxs-lookup"><span data-stu-id="f5257-332">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="f5257-333">Максимальная наблюдаемая частота потери пакетов во время вызова.</span><span class="sxs-lookup"><span data-stu-id="f5257-333">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5257-334">паккетутилизатион</span><span class="sxs-lookup"><span data-stu-id="f5257-334">PacketUtilization</span></span></p></td>
<td><p><span data-ttu-id="f5257-335">int</span><span class="sxs-lookup"><span data-stu-id="f5257-335">int</span></span></p></td>
<td><p><span data-ttu-id="f5257-336">Количество пакетов для видеопотока (RTP).</span><span class="sxs-lookup"><span data-stu-id="f5257-336">Packet count for the video stream (Real Time Transport Protocol, RTP).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5257-337">Самый полоса пропускания</span><span class="sxs-lookup"><span data-stu-id="f5257-337">BandwidthEst</span></span></p></td>
<td><p><span data-ttu-id="f5257-338">int</span><span class="sxs-lookup"><span data-stu-id="f5257-338">int</span></span></p></td>
<td><p><span data-ttu-id="f5257-339">Оценка пропускной способности для аудиопотока.</span><span class="sxs-lookup"><span data-stu-id="f5257-339">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5257-340">PayloadDescription</span><span class="sxs-lookup"><span data-stu-id="f5257-340">PayloadDescription</span></span></p></td>
<td><p><span data-ttu-id="f5257-341">int</span><span class="sxs-lookup"><span data-stu-id="f5257-341">int</span></span></p></td>
<td><p><span data-ttu-id="f5257-342">Аудиокодек, используемый для вызова, на который ссылается <a href="lync-server-2013-payloaddescription-table.md">таблица таблица payloaddescription в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="f5257-342">Audio codec used for the call, referenced from the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5257-343">видеоресолутион</span><span class="sxs-lookup"><span data-stu-id="f5257-343">VideoResolution</span></span></p></td>
<td><p><span data-ttu-id="f5257-344">char (9)</span><span class="sxs-lookup"><span data-stu-id="f5257-344">char(9)</span></span></p></td>
<td><p><span data-ttu-id="f5257-p119">Разрешение видео в пикселах (ширина умножается на высоту в пикселах). Указывается как строка.</span><span class="sxs-lookup"><span data-stu-id="f5257-p119">Resolution of the video in pixels width multiplied by pixels height. Reported as a string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5257-347">видеобитратеавг</span><span class="sxs-lookup"><span data-stu-id="f5257-347">VideoBitRateAvg</span></span></p></td>
<td><p><span data-ttu-id="f5257-348">int</span><span class="sxs-lookup"><span data-stu-id="f5257-348">int</span></span></p></td>
<td><p><span data-ttu-id="f5257-349">Средняя скорость передачи видеопотока.</span><span class="sxs-lookup"><span data-stu-id="f5257-349">Average bit rate of the video stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5257-350">инбаундвидеофрамератеавг</span><span class="sxs-lookup"><span data-stu-id="f5257-350">InboundVideoFrameRateAvg</span></span></p></td>
<td><p><span data-ttu-id="f5257-351">десятичное число (9, 4)</span><span class="sxs-lookup"><span data-stu-id="f5257-351">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="f5257-352">Частота кадров полученного видео.</span><span class="sxs-lookup"><span data-stu-id="f5257-352">Frame rate of video received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5257-353">аутбаундвидеофрамератеавг</span><span class="sxs-lookup"><span data-stu-id="f5257-353">OutboundVideoFrameRateAvg</span></span></p></td>
<td><p><span data-ttu-id="f5257-354">десятичное число (9, 4)</span><span class="sxs-lookup"><span data-stu-id="f5257-354">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="f5257-355">Частота кадров отправленного видео.</span><span class="sxs-lookup"><span data-stu-id="f5257-355">Frame rate of video sent.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5257-356">виидеобитратемакс</span><span class="sxs-lookup"><span data-stu-id="f5257-356">ViideoBitRateMax</span></span></p></td>
<td><p><span data-ttu-id="f5257-357">int</span><span class="sxs-lookup"><span data-stu-id="f5257-357">int</span></span></p></td>
<td><p><span data-ttu-id="f5257-358">Максимальная скорость передачи видео в ходе видеосеанса.</span><span class="sxs-lookup"><span data-stu-id="f5257-358">Maximum video bit rate during the video session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5257-359">видеопаккетлоссрате</span><span class="sxs-lookup"><span data-stu-id="f5257-359">VideoPacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="f5257-360">десятичное число (9, 4)</span><span class="sxs-lookup"><span data-stu-id="f5257-360">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="f5257-361">Скорость потери видеопакетов.</span><span class="sxs-lookup"><span data-stu-id="f5257-361">Rate at which video packets were lost.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5257-362">видеофрамелоссрате</span><span class="sxs-lookup"><span data-stu-id="f5257-362">VideoFrameLossRate</span></span></p></td>
<td><p><span data-ttu-id="f5257-363">десятичное число (9.4)</span><span class="sxs-lookup"><span data-stu-id="f5257-363">decimal(9.4)</span></span></p></td>
<td><p><span data-ttu-id="f5257-364">Процент от общего числа потерянных видеокадров.</span><span class="sxs-lookup"><span data-stu-id="f5257-364">Percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5257-365">видеофек</span><span class="sxs-lookup"><span data-stu-id="f5257-365">VideoFEC</span></span></p></td>
<td><p><span data-ttu-id="f5257-366">Битовая</span><span class="sxs-lookup"><span data-stu-id="f5257-366">bit</span></span></p></td>
<td><p><span data-ttu-id="f5257-367">Не используется.</span><span class="sxs-lookup"><span data-stu-id="f5257-367">Not used.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5257-368">видеоаллокатебвавг</span><span class="sxs-lookup"><span data-stu-id="f5257-368">VideoAllocateBWAvg</span></span></p></td>
<td><p><span data-ttu-id="f5257-369">int</span><span class="sxs-lookup"><span data-stu-id="f5257-369">int</span></span></p></td>
<td><p><span data-ttu-id="f5257-370">Средний объем выделенной полосы пропускания для видео.</span><span class="sxs-lookup"><span data-stu-id="f5257-370">Average amount of bandwidth allocated for video.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5257-371">видеолокалфрамелоссперцентажеавг</span><span class="sxs-lookup"><span data-stu-id="f5257-371">VideoLocalFrameLossPercentageAvg</span></span></p></td>
<td><p><span data-ttu-id="f5257-372">десятичное число (9.4)</span><span class="sxs-lookup"><span data-stu-id="f5257-372">decimal(9.4)</span></span></p></td>
<td><p><span data-ttu-id="f5257-373">Процент от общего числа потерянных видеокадров.</span><span class="sxs-lookup"><span data-stu-id="f5257-373">Percentage of total video frames that were lost.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5257-374">сендерискаллерпаи</span><span class="sxs-lookup"><span data-stu-id="f5257-374">SenderIsCallerPAI</span></span></p></td>
<td><p><span data-ttu-id="f5257-375">Битовая</span><span class="sxs-lookup"><span data-stu-id="f5257-375">bit</span></span></p></td>
<td><p><span data-ttu-id="f5257-p120">Направление потока для Р-утверждаемой идентификационной информации. 1 означает направление потока от звонящего абонента к вызываемому абоненту; 0 направление от вызываемого к звонящему абоненту.</span><span class="sxs-lookup"><span data-stu-id="f5257-p120">Stream direction for p-asserted identity information. 1 means the stream direction is from the caller to the callee; 0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

