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
ms.openlocfilehash: e9b6cc13721ff249d9f8bd8bc0c38260c4ca7f55
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211625"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="videostreamdetail-view-in-lync-server-2013"></a><span data-ttu-id="40763-102">Представление Видеостреамдетаил в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="40763-102">VideoStreamDetail view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="40763-103">_**Последнее изменение темы:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="40763-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="40763-104">Представление VideoStreamDetail хранит сведения о каждом видеопотоке в базе данных.</span><span class="sxs-lookup"><span data-stu-id="40763-104">The VideoStreamDetail View stores information about each video stream in the database.</span></span> <span data-ttu-id="40763-105">Это представление было представлено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="40763-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="40763-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="40763-106">Column</span></span></th>
<th><span data-ttu-id="40763-107">Тип данных</span><span class="sxs-lookup"><span data-stu-id="40763-107">Data Type</span></span></th>
<th><span data-ttu-id="40763-108">Описание</span><span class="sxs-lookup"><span data-stu-id="40763-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="40763-109">сессионтиме</span><span class="sxs-lookup"><span data-stu-id="40763-109">SessionTime</span></span></p></td>
<td><p><span data-ttu-id="40763-110">datetime</span><span class="sxs-lookup"><span data-stu-id="40763-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="40763-111">Ссылка из <a href="lync-server-2013-medialine-table.md">таблицы MediaLine в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="40763-111">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40763-112">сессионсек</span><span class="sxs-lookup"><span data-stu-id="40763-112">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="40763-113">int</span><span class="sxs-lookup"><span data-stu-id="40763-113">int</span></span></p></td>
<td><p><span data-ttu-id="40763-114">Ссылка из <a href="lync-server-2013-medialine-table.md">таблицы MediaLine в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="40763-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="40763-115">медиалинелабел</span><span class="sxs-lookup"><span data-stu-id="40763-115">MediaLineLabel</span></span></p></td>
<td><p><span data-ttu-id="40763-116">tinyint</span><span class="sxs-lookup"><span data-stu-id="40763-116">tinyint</span></span></p></td>
<td><p><span data-ttu-id="40763-117">Ссылка из <a href="lync-server-2013-medialine-table.md">таблицы MediaLine в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="40763-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40763-118">стреамид</span><span class="sxs-lookup"><span data-stu-id="40763-118">StreamId</span></span></p></td>
<td><p><span data-ttu-id="40763-119">int</span><span class="sxs-lookup"><span data-stu-id="40763-119">int</span></span></p></td>
<td><p><span data-ttu-id="40763-120">Уникальный идентификатор в линии мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="40763-120">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="40763-121">StartTime</span><span class="sxs-lookup"><span data-stu-id="40763-121">StartTime</span></span></p></td>
<td><p><span data-ttu-id="40763-122">datetime</span><span class="sxs-lookup"><span data-stu-id="40763-122">datetime</span></span></p></td>
<td><p><span data-ttu-id="40763-123">Время начала сеанса.</span><span class="sxs-lookup"><span data-stu-id="40763-123">Start time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40763-124">EndTime</span><span class="sxs-lookup"><span data-stu-id="40763-124">EndTime</span></span></p></td>
<td><p><span data-ttu-id="40763-125">datetime</span><span class="sxs-lookup"><span data-stu-id="40763-125">datetime</span></span></p></td>
<td><p><span data-ttu-id="40763-126">Время окончания сеанса.</span><span class="sxs-lookup"><span data-stu-id="40763-126">End time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="40763-127">каллприорити</span><span class="sxs-lookup"><span data-stu-id="40763-127">CallPriority</span></span></p></td>
<td><p><span data-ttu-id="40763-128">int</span><span class="sxs-lookup"><span data-stu-id="40763-128">int</span></span></p></td>
<td><p><span data-ttu-id="40763-129">Приоритет вызова.</span><span class="sxs-lookup"><span data-stu-id="40763-129">Priority of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40763-130">каллерпул</span><span class="sxs-lookup"><span data-stu-id="40763-130">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="40763-131">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="40763-131">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="40763-132">Полное доменное имя пула вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="40763-132">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="40763-133">каллипул</span><span class="sxs-lookup"><span data-stu-id="40763-133">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="40763-134">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="40763-134">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="40763-135">Полное доменное имя пула вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="40763-135">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40763-136">Вызывающая сторона</span><span class="sxs-lookup"><span data-stu-id="40763-136">Caller</span></span></p></td>
<td><p><span data-ttu-id="40763-137">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="40763-137">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="40763-138">URI вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="40763-138">Caller’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="40763-139">Вызываемого абонента</span><span class="sxs-lookup"><span data-stu-id="40763-139">Callee</span></span></p></td>
<td><p><span data-ttu-id="40763-140">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="40763-140">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="40763-141">URI вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="40763-141">Callee’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40763-142">каллерусеражент</span><span class="sxs-lookup"><span data-stu-id="40763-142">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="40763-143">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="40763-143">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="40763-144">Строка агента пользователя вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="40763-144">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="40763-145">каллерусераженттипе</span><span class="sxs-lookup"><span data-stu-id="40763-145">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="40763-146">smallint</span><span class="sxs-lookup"><span data-stu-id="40763-146">smallint</span></span></p></td>
<td><p><span data-ttu-id="40763-147">Тип агента пользователя звонящего абонента.</span><span class="sxs-lookup"><span data-stu-id="40763-147">Type of caller’s user agent.</span></span> <span data-ttu-id="40763-148">Дополнительные сведения см. <a href="lync-server-2013-useragent-table.md">в таблице UserAgent в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="40763-148">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40763-149">каллерусераженткатегори</span><span class="sxs-lookup"><span data-stu-id="40763-149">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="40763-150">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="40763-150">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="40763-151">Категория агента пользователя звонящего абонента.</span><span class="sxs-lookup"><span data-stu-id="40763-151">Category of caller’s user agent.</span></span> <span data-ttu-id="40763-152">Для получения подробных сведений ознакомьтесь со статьей <a href="lync-server-2013-useragentdef-table-qoe.md">таблица таблица useragentdef (QoE) в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="40763-152">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="40763-153">каллиусеражент</span><span class="sxs-lookup"><span data-stu-id="40763-153">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="40763-154">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="40763-154">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="40763-155">Строка агента пользователя вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="40763-155">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40763-156">каллиусераженттипе</span><span class="sxs-lookup"><span data-stu-id="40763-156">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="40763-157">smallint</span><span class="sxs-lookup"><span data-stu-id="40763-157">smallint</span></span></p></td>
<td><p><span data-ttu-id="40763-158">Тип агента пользователя вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="40763-158">Type of callee’s user agent.</span></span> <span data-ttu-id="40763-159">Сведения о том, как просмотреть <a href="lync-server-2013-useragent-table.md">таблицу UserAgent в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="40763-159">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="40763-160">каллиусераженткатегори</span><span class="sxs-lookup"><span data-stu-id="40763-160">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="40763-161">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="40763-161">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="40763-162">Категория агента пользователя вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="40763-162">Category of callee’s user agent.</span></span> <span data-ttu-id="40763-163">Для получения дополнительных сведений смотрите <a href="lync-server-2013-useragentdef-table-qoe.md">таблицу таблица useragentdef (QoE) в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="40763-163">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40763-164">каллерендпоинт</span><span class="sxs-lookup"><span data-stu-id="40763-164">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="40763-165">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="40763-165">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="40763-166">Имя конечной точки вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="40763-166">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="40763-167">каллиендпоинт</span><span class="sxs-lookup"><span data-stu-id="40763-167">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="40763-168">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="40763-168">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="40763-169">Имя конечной точки вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="40763-169">Callee’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40763-170">каллерос</span><span class="sxs-lookup"><span data-stu-id="40763-170">CallerOS</span></span></p></td>
<td><p><span data-ttu-id="40763-171">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="40763-171">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="40763-172">Операционная система конечной точки вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="40763-172">Operating system (OS) of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="40763-173">каллиос</span><span class="sxs-lookup"><span data-stu-id="40763-173">CalleeOS</span></span></p></td>
<td><p><span data-ttu-id="40763-174">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="40763-174">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="40763-175">Операционная система конечной точки вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="40763-175">Operating system (OS) of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40763-176">каллеркпунаме</span><span class="sxs-lookup"><span data-stu-id="40763-176">CallerCPUName</span></span></p></td>
<td><p><span data-ttu-id="40763-177">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="40763-177">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="40763-178">Название ЦП конечной точки вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="40763-178">CPU name of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="40763-179">калликпунаме</span><span class="sxs-lookup"><span data-stu-id="40763-179">CalleeCPUName</span></span></p></td>
<td><p><span data-ttu-id="40763-180">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="40763-180">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="40763-181">Название ЦП конечной точки вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="40763-181">CPU name of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40763-182">каллеркпунумберофкорес</span><span class="sxs-lookup"><span data-stu-id="40763-182">CallerCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="40763-183">smallint</span><span class="sxs-lookup"><span data-stu-id="40763-183">smallint</span></span></p></td>
<td><p><span data-ttu-id="40763-184">Число ядер ЦП конечной точки звонящего абонента.</span><span class="sxs-lookup"><span data-stu-id="40763-184">Number of CPU cores of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="40763-185">калликпунумберофкорес</span><span class="sxs-lookup"><span data-stu-id="40763-185">CalleeCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="40763-186">smallint</span><span class="sxs-lookup"><span data-stu-id="40763-186">smallint</span></span></p></td>
<td><p><span data-ttu-id="40763-187">Число ядер ЦП конечной точки вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="40763-187">Number of CPU cores of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40763-188">каллеркпупроцессорспид</span><span class="sxs-lookup"><span data-stu-id="40763-188">CallerCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="40763-189">int</span><span class="sxs-lookup"><span data-stu-id="40763-189">int</span></span></p></td>
<td><p><span data-ttu-id="40763-190">Скорость ЦП конечной точки вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="40763-190">CPU processor speed of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="40763-191">калликпупроцессорспид</span><span class="sxs-lookup"><span data-stu-id="40763-191">CalleeCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="40763-192">int</span><span class="sxs-lookup"><span data-stu-id="40763-192">int</span></span></p></td>
<td><p><span data-ttu-id="40763-193">Скорость ЦП конечной точки вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="40763-193">CPU processor speed of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40763-194">каллервиртуализатионфлаг</span><span class="sxs-lookup"><span data-stu-id="40763-194">CallerVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="40763-195">tinyint</span><span class="sxs-lookup"><span data-stu-id="40763-195">tinyint</span></span></p></td>
<td><p><span data-ttu-id="40763-196">Указывает, работает ли система вызывающего абонента в виртуализованной среде.</span><span class="sxs-lookup"><span data-stu-id="40763-196">Indicates whether the caller’s system is running in a virtualized environment.</span></span> <span data-ttu-id="40763-197">Более подробную информацию можно узнать <a href="lync-server-2013-endpoint-table.md">в таблице конечная точка в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="40763-197">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="40763-198">калливиртуализатионфлаг</span><span class="sxs-lookup"><span data-stu-id="40763-198">CalleeVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="40763-199">tinyint</span><span class="sxs-lookup"><span data-stu-id="40763-199">tinyint</span></span></p></td>
<td><p><span data-ttu-id="40763-200">Указывает, работает ли система вызываемого абонента в виртуализованной среде.</span><span class="sxs-lookup"><span data-stu-id="40763-200">Indicates whether the callee’s system is running in a virtualized environment.</span></span> <span data-ttu-id="40763-201">Более подробную информацию можно узнать <a href="lync-server-2013-endpoint-table.md">в таблице конечная точка в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="40763-201">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40763-202">коннективитице</span><span class="sxs-lookup"><span data-stu-id="40763-202">ConnectivityIce</span></span></p></td>
<td><p><span data-ttu-id="40763-203">tinyint</span><span class="sxs-lookup"><span data-stu-id="40763-203">tinyint</span></span></p></td>
<td><p><span data-ttu-id="40763-204">Информация о пути к носителю, например прямой или с ретрансляцией.</span><span class="sxs-lookup"><span data-stu-id="40763-204">Information about media path, such as direct or relayed.</span></span> <span data-ttu-id="40763-205">Дополнительные сведения см. <a href="lync-server-2013-medialine-table.md">в таблице MediaLine в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="40763-205">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="40763-206">каллерицеварнингфлагс</span><span class="sxs-lookup"><span data-stu-id="40763-206">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="40763-207">int</span><span class="sxs-lookup"><span data-stu-id="40763-207">int</span></span></p></td>
<td><p><span data-ttu-id="40763-p109">Сведения о технологии ICE (Interactive Connectivity Establishment), описанные в битовых флагах, для вызывающего абонента. Дополнительные сведения см. в спецификации протокола сервера мониторинга качества взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="40763-p109">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40763-210">каллиицеварнингфлагс</span><span class="sxs-lookup"><span data-stu-id="40763-210">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="40763-211">int</span><span class="sxs-lookup"><span data-stu-id="40763-211">int</span></span></p></td>
<td><p><span data-ttu-id="40763-p110">Сведения о технологии ICE (Interactive Connectivity Establishment), описанные в битовых флагах, для вызываемого абонента. Дополнительные сведения см. в спецификации протокола сервера мониторинга качества взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="40763-p110">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="40763-214">Transport</span><span class="sxs-lookup"><span data-stu-id="40763-214">Transport</span></span></p></td>
<td><p><span data-ttu-id="40763-215">int</span><span class="sxs-lookup"><span data-stu-id="40763-215">int</span></span></p></td>
<td><p><span data-ttu-id="40763-216">Вид транспорта: 0 — UDP, 1 — TCP.</span><span class="sxs-lookup"><span data-stu-id="40763-216">Transport type: 0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40763-217">каллерипаддр</span><span class="sxs-lookup"><span data-stu-id="40763-217">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="40763-218">var (50)</span><span class="sxs-lookup"><span data-stu-id="40763-218">var(50)</span></span></p></td>
<td><p><span data-ttu-id="40763-219">IP-адрес вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="40763-219">IP address of the caller.</span></span> <span data-ttu-id="40763-220">Адрес может быть представлен в формате IPv4 или IPv6.</span><span class="sxs-lookup"><span data-stu-id="40763-220">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="40763-221">каллерпорт</span><span class="sxs-lookup"><span data-stu-id="40763-221">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="40763-222">int</span><span class="sxs-lookup"><span data-stu-id="40763-222">int</span></span></p></td>
<td><p><span data-ttu-id="40763-223">Порт, используемый вызывающим абонентом.</span><span class="sxs-lookup"><span data-stu-id="40763-223">Port used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40763-224">каллеринсиде</span><span class="sxs-lookup"><span data-stu-id="40763-224">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="40763-225">Битовая</span><span class="sxs-lookup"><span data-stu-id="40763-225">bit</span></span></p></td>
<td><p><span data-ttu-id="40763-p112">Указывает, находится ли звонящий абонент внутри сети организации: 1 означает, что абонент внутри корпоративной сети, 0 — абонент вне сети.</span><span class="sxs-lookup"><span data-stu-id="40763-p112">Indicates whether the caller is inside the organization network. 1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="40763-228">каллиипаддр</span><span class="sxs-lookup"><span data-stu-id="40763-228">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="40763-229">var (50)</span><span class="sxs-lookup"><span data-stu-id="40763-229">var(50)</span></span></p></td>
<td><p><span data-ttu-id="40763-230">IP-адрес вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="40763-230">IP address of the callee.</span></span> <span data-ttu-id="40763-231">Это может быть IPv4-адрес или IPv6-адрес.</span><span class="sxs-lookup"><span data-stu-id="40763-231">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40763-232">каллипорт</span><span class="sxs-lookup"><span data-stu-id="40763-232">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="40763-233">int</span><span class="sxs-lookup"><span data-stu-id="40763-233">int</span></span></p></td>
<td><p><span data-ttu-id="40763-234">Порт, используемый вызываемым абонентом.</span><span class="sxs-lookup"><span data-stu-id="40763-234">Port used by the callee.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="40763-235">каллиинсиде</span><span class="sxs-lookup"><span data-stu-id="40763-235">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="40763-236">Битовая</span><span class="sxs-lookup"><span data-stu-id="40763-236">bit</span></span></p></td>
<td><p><span data-ttu-id="40763-237">Указывает, находится ли вызываемый абонент внутри сети организации: 1 означает, что абонент внутри корпоративной сети, 0 — абонент вне сети.</span><span class="sxs-lookup"><span data-stu-id="40763-237">Indicates whether the caller is inside the organization network.1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40763-238">каллерусерсите</span><span class="sxs-lookup"><span data-stu-id="40763-238">CallerUserSite</span></span></p></td>
<td><p><span data-ttu-id="40763-239">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="40763-239">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="40763-240">Имя сайта вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="40763-240">Name of the caller’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="40763-241">каллеррегион</span><span class="sxs-lookup"><span data-stu-id="40763-241">CallerRegion</span></span></p></td>
<td><p><span data-ttu-id="40763-242">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="40763-242">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="40763-243">Название страны или региона, где находится сайт вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="40763-243">Name of the country/region of the caller’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40763-244">каллиусерсите</span><span class="sxs-lookup"><span data-stu-id="40763-244">CalleeUserSite</span></span></p></td>
<td><p><span data-ttu-id="40763-245">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="40763-245">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="40763-246">Имя сайта вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="40763-246">Name of the callee’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="40763-247">каллирегион</span><span class="sxs-lookup"><span data-stu-id="40763-247">CalleeRegion</span></span></p></td>
<td><p><span data-ttu-id="40763-248">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="40763-248">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="40763-249">Название страны или региона, где находится сайт вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="40763-249">Name of the country/region of the callee’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40763-250">каллеррелайипаддр</span><span class="sxs-lookup"><span data-stu-id="40763-250">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="40763-251">var (50)</span><span class="sxs-lookup"><span data-stu-id="40763-251">var(50)</span></span></p></td>
<td><p><span data-ttu-id="40763-252">IP-адрес пограничной службы обработки аудио- и видеоданных, используемой вызывающим абонентом.</span><span class="sxs-lookup"><span data-stu-id="40763-252">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="40763-253">Дополнительные сведения см. <a href="lync-server-2013-ipaddress-table.md">в таблице IPAddress в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="40763-253">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="40763-254">каллеррелайпорт</span><span class="sxs-lookup"><span data-stu-id="40763-254">CallerRelayPort</span></span></p></td>
<td><p><span data-ttu-id="40763-255">int</span><span class="sxs-lookup"><span data-stu-id="40763-255">int</span></span></p></td>
<td><p><span data-ttu-id="40763-256">Порт пограничной службы обмена аудио-видео данными, используемой звонящим абонентом.</span><span class="sxs-lookup"><span data-stu-id="40763-256">Port on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40763-257">каллирелайипаддр</span><span class="sxs-lookup"><span data-stu-id="40763-257">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="40763-258">var (50)</span><span class="sxs-lookup"><span data-stu-id="40763-258">var(50)</span></span></p></td>
<td><p><span data-ttu-id="40763-259">IP-адрес пограничной службы обработки аудио- и видеоданных, используемой вызываемым абонентом.</span><span class="sxs-lookup"><span data-stu-id="40763-259">IP Address key of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="40763-260">Дополнительные сведения см. <a href="lync-server-2013-ipaddress-table.md">в таблице IPAddress в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="40763-260">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="40763-261">каллирелайпорт</span><span class="sxs-lookup"><span data-stu-id="40763-261">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="40763-262">int</span><span class="sxs-lookup"><span data-stu-id="40763-262">int</span></span></p></td>
<td><p><span data-ttu-id="40763-263">Порт пограничной службы обмена аудио-видео данными, используемой вызываемым абонентом.</span><span class="sxs-lookup"><span data-stu-id="40763-263">Port on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40763-264">каллеркаптуредев</span><span class="sxs-lookup"><span data-stu-id="40763-264">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="40763-265">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="40763-265">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="40763-266">Имя устройства захвата вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="40763-266">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="40763-267">каллеррендердев</span><span class="sxs-lookup"><span data-stu-id="40763-267">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="40763-268">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="40763-268">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="40763-269">Имя устройства обработки вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="40763-269">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40763-270">каллеркаптуредевдривер</span><span class="sxs-lookup"><span data-stu-id="40763-270">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="40763-271">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="40763-271">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="40763-272">Имя драйвера устройства захвата звонящего абонента.</span><span class="sxs-lookup"><span data-stu-id="40763-272">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="40763-273">каллеррендердевдривер</span><span class="sxs-lookup"><span data-stu-id="40763-273">CallerRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="40763-274">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="40763-274">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="40763-275">Имя драйвера для устройства обработки вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="40763-275">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40763-276">калликаптуредев</span><span class="sxs-lookup"><span data-stu-id="40763-276">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="40763-277">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="40763-277">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="40763-278">Имя устройства захвата вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="40763-278">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="40763-279">каллирендердев</span><span class="sxs-lookup"><span data-stu-id="40763-279">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="40763-280">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="40763-280">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="40763-281">Имя устройства обработки звука вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="40763-281">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40763-282">каллекаптуредевдривер</span><span class="sxs-lookup"><span data-stu-id="40763-282">CalleCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="40763-283">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="40763-283">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="40763-284">Имя драйвера для устройства захвата вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="40763-284">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="40763-285">каллирендердевдривер</span><span class="sxs-lookup"><span data-stu-id="40763-285">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="40763-286">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="40763-286">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="40763-287">Имя драйвера для устройства обработки вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="40763-287">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40763-288">каллернетворкконнектионтипе</span><span class="sxs-lookup"><span data-stu-id="40763-288">CallerNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="40763-289">tinyint</span><span class="sxs-lookup"><span data-stu-id="40763-289">tinyint</span></span></p></td>
<td><p><span data-ttu-id="40763-290">Тип подключения к сети вызывающего абонента: 0 — проводной, 1 — беспроводной.</span><span class="sxs-lookup"><span data-stu-id="40763-290">Caller’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="40763-291">каллервпн</span><span class="sxs-lookup"><span data-stu-id="40763-291">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="40763-292">Битовая</span><span class="sxs-lookup"><span data-stu-id="40763-292">bit</span></span></p></td>
<td><p><span data-ttu-id="40763-p116">Указывает, подключен ли звонящий абонент через виртуальную частную сеть: 1 — виртуальная частная сеть (VPN), 0 — не VPN.</span><span class="sxs-lookup"><span data-stu-id="40763-p116">Indicates whether or not the caller connected over a virtual private network. 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40763-295">каллерлинкспид</span><span class="sxs-lookup"><span data-stu-id="40763-295">CallerLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="40763-296">десятичное число (18,)</span><span class="sxs-lookup"><span data-stu-id="40763-296">decimal(18,)</span></span></p></td>
<td><p><span data-ttu-id="40763-297">Скорость сетевого канала для звонящего абонента в бит/с.</span><span class="sxs-lookup"><span data-stu-id="40763-297">Network link speed for the caller's endpoint in bps.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="40763-298">каллинетворкконнектионтипе</span><span class="sxs-lookup"><span data-stu-id="40763-298">CalleeNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="40763-299">tinyint</span><span class="sxs-lookup"><span data-stu-id="40763-299">tinyint</span></span></p></td>
<td><p><span data-ttu-id="40763-300">Тип подключения к сети вызываемого абонента: 0 — проводной, 1 — беспроводной.</span><span class="sxs-lookup"><span data-stu-id="40763-300">Callee’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40763-301">калливпн</span><span class="sxs-lookup"><span data-stu-id="40763-301">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="40763-302">Битовая</span><span class="sxs-lookup"><span data-stu-id="40763-302">bit</span></span></p></td>
<td><p><span data-ttu-id="40763-p117">Указывает, подключен ли вызываемый абонент через виртуальную частную сеть: 1 — виртуальная частная сеть (VPN), 0 — не VPN.</span><span class="sxs-lookup"><span data-stu-id="40763-p117">Indicates whether or not the callee connected over a virtual private network. 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="40763-305">каллилинкспид</span><span class="sxs-lookup"><span data-stu-id="40763-305">CalleeLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="40763-306">десятичное число (18, 0)</span><span class="sxs-lookup"><span data-stu-id="40763-306">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="40763-307">Скорость сетевого канала для вызываемого абонента в бит/с.</span><span class="sxs-lookup"><span data-stu-id="40763-307">Network link speed for the callee’s endpoint (in bps).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40763-308">конверсатионалмос</span><span class="sxs-lookup"><span data-stu-id="40763-308">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="40763-309">десятичное число (3, 2)</span><span class="sxs-lookup"><span data-stu-id="40763-309">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="40763-310">Узкополосный MOS аудиосеансов (на основе обоих аудиопотоков).</span><span class="sxs-lookup"><span data-stu-id="40763-310">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="40763-311">апплиедбандвидслимит</span><span class="sxs-lookup"><span data-stu-id="40763-311">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="40763-312">int</span><span class="sxs-lookup"><span data-stu-id="40763-312">int</span></span></p></td>
<td><p><span data-ttu-id="40763-p118">Фактическая пропускная способность, применяемая к данному потоку отправителя с различными параметрами политики (TURN, API, SDP, сервер политик и т. д.). Ее не следует путать с эффективной пропускной способностью, потому что эффективная пропускная способность может быть меньше в зависимости от оценки пропускной способности. По сути это в основном максимальная пропускная способность потока отправителя с учетом ограничений, наложенных оценкой пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="40763-p118">Actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on). This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate. This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40763-316">життеринтерарривал</span><span class="sxs-lookup"><span data-stu-id="40763-316">JitterInterArrival</span></span></p></td>
<td><p><span data-ttu-id="40763-317">int</span><span class="sxs-lookup"><span data-stu-id="40763-317">int</span></span></p></td>
<td><p><span data-ttu-id="40763-318">Средний уровень дрожания в сети на основе статистики протокола RTCP.</span><span class="sxs-lookup"><span data-stu-id="40763-318">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="40763-319">життеринтерарривалмакс</span><span class="sxs-lookup"><span data-stu-id="40763-319">JitterInterArrivalMax</span></span></p></td>
<td><p><span data-ttu-id="40763-320">int</span><span class="sxs-lookup"><span data-stu-id="40763-320">int</span></span></p></td>
<td><p><span data-ttu-id="40763-321">Максимальное "дрожание" сети во время вызова.</span><span class="sxs-lookup"><span data-stu-id="40763-321">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40763-322">Обработки</span><span class="sxs-lookup"><span data-stu-id="40763-322">RoundTrip</span></span></p></td>
<td><p><span data-ttu-id="40763-323">int</span><span class="sxs-lookup"><span data-stu-id="40763-323">int</span></span></p></td>
<td><p><span data-ttu-id="40763-324">Время приема-передачи на основе статистики RTCP.</span><span class="sxs-lookup"><span data-stu-id="40763-324">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="40763-325">раундтрипмакс</span><span class="sxs-lookup"><span data-stu-id="40763-325">RoundTripMax</span></span></p></td>
<td><p><span data-ttu-id="40763-326">int</span><span class="sxs-lookup"><span data-stu-id="40763-326">int</span></span></p></td>
<td><p><span data-ttu-id="40763-327">Максимальное время кругового пути для аудиопотока.</span><span class="sxs-lookup"><span data-stu-id="40763-327">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40763-328">паккетлоссрате</span><span class="sxs-lookup"><span data-stu-id="40763-328">PacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="40763-329">десятичное число (5, 4)</span><span class="sxs-lookup"><span data-stu-id="40763-329">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="40763-330">Средний коэффициент потерь пакетов в течение вызова.</span><span class="sxs-lookup"><span data-stu-id="40763-330">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="40763-331">паккетлоссратемакс</span><span class="sxs-lookup"><span data-stu-id="40763-331">PacketLossRateMax</span></span></p></td>
<td><p><span data-ttu-id="40763-332">десятичное число (5, 4)</span><span class="sxs-lookup"><span data-stu-id="40763-332">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="40763-333">Максимальная наблюдаемая частота потери пакетов во время вызова.</span><span class="sxs-lookup"><span data-stu-id="40763-333">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40763-334">паккетутилизатион</span><span class="sxs-lookup"><span data-stu-id="40763-334">PacketUtilization</span></span></p></td>
<td><p><span data-ttu-id="40763-335">int</span><span class="sxs-lookup"><span data-stu-id="40763-335">int</span></span></p></td>
<td><p><span data-ttu-id="40763-336">Количество пакетов для видеопотока (RTP).</span><span class="sxs-lookup"><span data-stu-id="40763-336">Packet count for the video stream (Real Time Transport Protocol, RTP).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="40763-337">Самый полоса пропускания</span><span class="sxs-lookup"><span data-stu-id="40763-337">BandwidthEst</span></span></p></td>
<td><p><span data-ttu-id="40763-338">int</span><span class="sxs-lookup"><span data-stu-id="40763-338">int</span></span></p></td>
<td><p><span data-ttu-id="40763-339">Оценка пропускной способности для аудиопотока.</span><span class="sxs-lookup"><span data-stu-id="40763-339">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40763-340">Таблица payloaddescription</span><span class="sxs-lookup"><span data-stu-id="40763-340">PayloadDescription</span></span></p></td>
<td><p><span data-ttu-id="40763-341">int</span><span class="sxs-lookup"><span data-stu-id="40763-341">int</span></span></p></td>
<td><p><span data-ttu-id="40763-342">Аудиокодек, используемый для вызова, на который ссылается <a href="lync-server-2013-payloaddescription-table.md">таблица таблица payloaddescription в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="40763-342">Audio codec used for the call, referenced from the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="40763-343">видеоресолутион</span><span class="sxs-lookup"><span data-stu-id="40763-343">VideoResolution</span></span></p></td>
<td><p><span data-ttu-id="40763-344">char (9)</span><span class="sxs-lookup"><span data-stu-id="40763-344">char(9)</span></span></p></td>
<td><p><span data-ttu-id="40763-p119">Разрешение видео в пикселах (ширина умножается на высоту в пикселах). Указывается как строка.</span><span class="sxs-lookup"><span data-stu-id="40763-p119">Resolution of the video in pixels width multiplied by pixels height. Reported as a string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40763-347">видеобитратеавг</span><span class="sxs-lookup"><span data-stu-id="40763-347">VideoBitRateAvg</span></span></p></td>
<td><p><span data-ttu-id="40763-348">int</span><span class="sxs-lookup"><span data-stu-id="40763-348">int</span></span></p></td>
<td><p><span data-ttu-id="40763-349">Средняя скорость передачи видеопотока.</span><span class="sxs-lookup"><span data-stu-id="40763-349">Average bit rate of the video stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="40763-350">инбаундвидеофрамератеавг</span><span class="sxs-lookup"><span data-stu-id="40763-350">InboundVideoFrameRateAvg</span></span></p></td>
<td><p><span data-ttu-id="40763-351">десятичное число (9, 4)</span><span class="sxs-lookup"><span data-stu-id="40763-351">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="40763-352">Частота кадров полученного видео.</span><span class="sxs-lookup"><span data-stu-id="40763-352">Frame rate of video received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40763-353">аутбаундвидеофрамератеавг</span><span class="sxs-lookup"><span data-stu-id="40763-353">OutboundVideoFrameRateAvg</span></span></p></td>
<td><p><span data-ttu-id="40763-354">десятичное число (9, 4)</span><span class="sxs-lookup"><span data-stu-id="40763-354">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="40763-355">Частота кадров отправленного видео.</span><span class="sxs-lookup"><span data-stu-id="40763-355">Frame rate of video sent.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="40763-356">виидеобитратемакс</span><span class="sxs-lookup"><span data-stu-id="40763-356">ViideoBitRateMax</span></span></p></td>
<td><p><span data-ttu-id="40763-357">int</span><span class="sxs-lookup"><span data-stu-id="40763-357">int</span></span></p></td>
<td><p><span data-ttu-id="40763-358">Максимальная скорость передачи видео в ходе видеосеанса.</span><span class="sxs-lookup"><span data-stu-id="40763-358">Maximum video bit rate during the video session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40763-359">видеопаккетлоссрате</span><span class="sxs-lookup"><span data-stu-id="40763-359">VideoPacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="40763-360">десятичное число (9, 4)</span><span class="sxs-lookup"><span data-stu-id="40763-360">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="40763-361">Скорость потери видеопакетов.</span><span class="sxs-lookup"><span data-stu-id="40763-361">Rate at which video packets were lost.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="40763-362">видеофрамелоссрате</span><span class="sxs-lookup"><span data-stu-id="40763-362">VideoFrameLossRate</span></span></p></td>
<td><p><span data-ttu-id="40763-363">десятичное число (9.4)</span><span class="sxs-lookup"><span data-stu-id="40763-363">decimal(9.4)</span></span></p></td>
<td><p><span data-ttu-id="40763-364">Процент от общего числа потерянных видеокадров.</span><span class="sxs-lookup"><span data-stu-id="40763-364">Percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40763-365">видеофек</span><span class="sxs-lookup"><span data-stu-id="40763-365">VideoFEC</span></span></p></td>
<td><p><span data-ttu-id="40763-366">Битовая</span><span class="sxs-lookup"><span data-stu-id="40763-366">bit</span></span></p></td>
<td><p><span data-ttu-id="40763-367">Не используется.</span><span class="sxs-lookup"><span data-stu-id="40763-367">Not used.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="40763-368">видеоаллокатебвавг</span><span class="sxs-lookup"><span data-stu-id="40763-368">VideoAllocateBWAvg</span></span></p></td>
<td><p><span data-ttu-id="40763-369">int</span><span class="sxs-lookup"><span data-stu-id="40763-369">int</span></span></p></td>
<td><p><span data-ttu-id="40763-370">Средний объем выделенной полосы пропускания для видео.</span><span class="sxs-lookup"><span data-stu-id="40763-370">Average amount of bandwidth allocated for video.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40763-371">видеолокалфрамелоссперцентажеавг</span><span class="sxs-lookup"><span data-stu-id="40763-371">VideoLocalFrameLossPercentageAvg</span></span></p></td>
<td><p><span data-ttu-id="40763-372">десятичное число (9.4)</span><span class="sxs-lookup"><span data-stu-id="40763-372">decimal(9.4)</span></span></p></td>
<td><p><span data-ttu-id="40763-373">Процент от общего числа потерянных видеокадров.</span><span class="sxs-lookup"><span data-stu-id="40763-373">Percentage of total video frames that were lost.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="40763-374">сендерискаллерпаи</span><span class="sxs-lookup"><span data-stu-id="40763-374">SenderIsCallerPAI</span></span></p></td>
<td><p><span data-ttu-id="40763-375">Битовая</span><span class="sxs-lookup"><span data-stu-id="40763-375">bit</span></span></p></td>
<td><p><span data-ttu-id="40763-p120">Направление потока для Р-утверждаемой идентификационной информации. 1 означает направление потока от звонящего абонента к вызываемому абоненту; 0 направление от вызываемого к звонящему абоненту.</span><span class="sxs-lookup"><span data-stu-id="40763-p120">Stream direction for p-asserted identity information. 1 means the stream direction is from the caller to the callee; 0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

