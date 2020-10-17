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
ms.openlocfilehash: 4a9abfbc214e72cf059250910ecec4ad3bcdba33
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515786"
---
# <a name="audiostreamdetail-view-in-lync-server-2013"></a><span data-ttu-id="ba048-102">Представление Аудиостреамдетаил в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ba048-102">AudioStreamDetail view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ba048-103">_**Последнее изменение темы:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="ba048-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="ba048-104">В представлении AudioStreamDetail хранятся сведения о всех аудиопотоках в базе данных.</span><span class="sxs-lookup"><span data-stu-id="ba048-104">The AudioStreamDetail View stores information about each audio stream in the database.</span></span> <span data-ttu-id="ba048-105">Это представление было представлено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ba048-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ba048-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="ba048-106">Column</span></span></th>
<th><span data-ttu-id="ba048-107">Тип данных</span><span class="sxs-lookup"><span data-stu-id="ba048-107">Data Type</span></span></th>
<th><span data-ttu-id="ba048-108">Сведения</span><span class="sxs-lookup"><span data-stu-id="ba048-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ba048-109">сессионтиме</span><span class="sxs-lookup"><span data-stu-id="ba048-109">SessionTime</span></span></p></td>
<td><p><span data-ttu-id="ba048-110">datetime</span><span class="sxs-lookup"><span data-stu-id="ba048-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="ba048-111">Ссылка из <a href="lync-server-2013-medialine-table.md">таблицы MediaLine в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="ba048-111">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba048-112">сессионсек</span><span class="sxs-lookup"><span data-stu-id="ba048-112">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="ba048-113">int</span><span class="sxs-lookup"><span data-stu-id="ba048-113">int</span></span></p></td>
<td><p><span data-ttu-id="ba048-114">Ссылка из <a href="lync-server-2013-medialine-table.md">таблицы MediaLine в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="ba048-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba048-115">стреамид</span><span class="sxs-lookup"><span data-stu-id="ba048-115">StreamId</span></span></p></td>
<td><p><span data-ttu-id="ba048-116">int</span><span class="sxs-lookup"><span data-stu-id="ba048-116">int</span></span></p></td>
<td><p><span data-ttu-id="ba048-117">Уникальный идентификатор в линии мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="ba048-117">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba048-118">StartTime</span><span class="sxs-lookup"><span data-stu-id="ba048-118">StartTime</span></span></p></td>
<td><p><span data-ttu-id="ba048-119">datetime</span><span class="sxs-lookup"><span data-stu-id="ba048-119">datetime</span></span></p></td>
<td><p><span data-ttu-id="ba048-120">Время начала сеанса.</span><span class="sxs-lookup"><span data-stu-id="ba048-120">Start time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba048-121">EndTime</span><span class="sxs-lookup"><span data-stu-id="ba048-121">EndTime</span></span></p></td>
<td><p><span data-ttu-id="ba048-122">datetime</span><span class="sxs-lookup"><span data-stu-id="ba048-122">datetime</span></span></p></td>
<td><p><span data-ttu-id="ba048-123">Время окончания сеанса.</span><span class="sxs-lookup"><span data-stu-id="ba048-123">End time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba048-124">диалогкатегори</span><span class="sxs-lookup"><span data-stu-id="ba048-124">DialogCategory</span></span></p></td>
<td><p><span data-ttu-id="ba048-125">Битовая</span><span class="sxs-lookup"><span data-stu-id="ba048-125">bit</span></span></p></td>
<td><p><span data-ttu-id="ba048-126">Категория диалоговых окон: 0 — сервер Lync Server — это ветвь сервера-посредника; 1 — это сервер-посредник для шлюза PSTN.</span><span class="sxs-lookup"><span data-stu-id="ba048-126">Dialog category: 0 is the Lync Server to Mediation Server leg; 1 is the Mediation Server to PSTN gateway leg.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba048-127">медиатионсервербипассфлаг</span><span class="sxs-lookup"><span data-stu-id="ba048-127">MediationServerBypassFlag</span></span></p></td>
<td><p><span data-ttu-id="ba048-128">Битовая</span><span class="sxs-lookup"><span data-stu-id="ba048-128">bit</span></span></p></td>
<td><p><span data-ttu-id="ba048-129">Флаг, указывающий, выполнял ли вызов обход сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="ba048-129">Flag indicating if the call was bypassed or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba048-130">медиабипассварнингфлаг</span><span class="sxs-lookup"><span data-stu-id="ba048-130">MediaBypassWarningFlag</span></span></p></td>
<td><p><span data-ttu-id="ba048-131">int</span><span class="sxs-lookup"><span data-stu-id="ba048-131">int</span></span></p></td>
<td><p><span data-ttu-id="ba048-p102">Если это поле присутствует, оно указывает, почему вызов не выполнял обход сервера-посредника, даже если идентификаторы обхода соответствовали. Задается только одно значение:</span><span class="sxs-lookup"><span data-stu-id="ba048-p102">If present, indicates why a call was not bypassed even if the bypass IDs matched. Only one value is defined:</span></span></p>
<p><span data-ttu-id="ba048-134">0x0001 — неизвестный идентификатор обхода для сетевого адаптера по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ba048-134">0x0001 – Unknown bypass ID for Default network adapter.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba048-135">каллприорити</span><span class="sxs-lookup"><span data-stu-id="ba048-135">CallPriority</span></span></p></td>
<td><p><span data-ttu-id="ba048-136">int</span><span class="sxs-lookup"><span data-stu-id="ba048-136">int</span></span></p></td>
<td><p><span data-ttu-id="ba048-137">Приоритет вызова.</span><span class="sxs-lookup"><span data-stu-id="ba048-137">Priority of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba048-138">каллерпул</span><span class="sxs-lookup"><span data-stu-id="ba048-138">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="ba048-139">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="ba048-139">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ba048-140">Полное доменное имя пула вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="ba048-140">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba048-141">каллипул</span><span class="sxs-lookup"><span data-stu-id="ba048-141">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="ba048-142">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="ba048-142">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ba048-143">Полное доменное имя пула вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="ba048-143">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba048-144">Вызывающая сторона</span><span class="sxs-lookup"><span data-stu-id="ba048-144">Caller</span></span></p></td>
<td><p><span data-ttu-id="ba048-145">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="ba048-145">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="ba048-146">URI вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="ba048-146">Caller’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba048-147">Вызываемого абонента</span><span class="sxs-lookup"><span data-stu-id="ba048-147">Callee</span></span></p></td>
<td><p><span data-ttu-id="ba048-148">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="ba048-148">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="ba048-149">URI вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="ba048-149">Callee’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba048-150">каллерусеражент</span><span class="sxs-lookup"><span data-stu-id="ba048-150">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="ba048-151">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="ba048-151">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ba048-152">Строка агента пользователя вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="ba048-152">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba048-153">каллерусераженттипе</span><span class="sxs-lookup"><span data-stu-id="ba048-153">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="ba048-154">smallint</span><span class="sxs-lookup"><span data-stu-id="ba048-154">smallint</span></span></p></td>
<td><p><span data-ttu-id="ba048-155">Тип агента пользователя вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="ba048-155">Type of the caller’s user agent.</span></span> <span data-ttu-id="ba048-156">Дополнительные сведения см. <a href="lync-server-2013-useragent-table.md">в таблице UserAgent в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ba048-156">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba048-157">каллерусераженткатегори</span><span class="sxs-lookup"><span data-stu-id="ba048-157">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="ba048-158">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="ba048-158">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="ba048-159">Категория агента пользователя вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="ba048-159">Category of the caller’s user agent.</span></span> <span data-ttu-id="ba048-160">Для получения подробных сведений ознакомьтесь со статьей <a href="lync-server-2013-useragentdef-table-qoe.md">таблица таблица useragentdef (QoE) в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ba048-160">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba048-161">каллиусеражент</span><span class="sxs-lookup"><span data-stu-id="ba048-161">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="ba048-162">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="ba048-162">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ba048-163">Строка агента пользователя вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="ba048-163">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba048-164">каллиусераженттипе</span><span class="sxs-lookup"><span data-stu-id="ba048-164">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="ba048-165">smallint</span><span class="sxs-lookup"><span data-stu-id="ba048-165">smallint</span></span></p></td>
<td><p><span data-ttu-id="ba048-166">Тип агента пользователя вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="ba048-166">Type of callee’s user agent.</span></span> <span data-ttu-id="ba048-167">Сведения о том, как просмотреть <a href="lync-server-2013-useragent-table.md">таблицу UserAgent в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ba048-167">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba048-168">каллиусераженткатегори</span><span class="sxs-lookup"><span data-stu-id="ba048-168">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="ba048-169">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="ba048-169">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="ba048-170">Категория агента пользователя вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="ba048-170">Category of callee’s user agent.</span></span> <span data-ttu-id="ba048-171">Для получения дополнительных сведений смотрите <a href="lync-server-2013-useragentdef-table-qoe.md">таблицу таблица useragentdef (QoE) в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ba048-171">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba048-172">каллерендпоинт</span><span class="sxs-lookup"><span data-stu-id="ba048-172">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="ba048-173">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="ba048-173">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ba048-174">Имя конечной точки вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="ba048-174">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba048-175">каллиендпоинт</span><span class="sxs-lookup"><span data-stu-id="ba048-175">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="ba048-176">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="ba048-176">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ba048-177">Имя конечной точки вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="ba048-177">Callee’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba048-178">каллерос</span><span class="sxs-lookup"><span data-stu-id="ba048-178">CallerOS</span></span></p></td>
<td><p><span data-ttu-id="ba048-179">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="ba048-179">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="ba048-180">Операционная система конечной точки вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="ba048-180">Operating system (OS) of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba048-181">каллиос</span><span class="sxs-lookup"><span data-stu-id="ba048-181">CalleeOS</span></span></p></td>
<td><p><span data-ttu-id="ba048-182">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="ba048-182">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="ba048-183">Операционная система конечной точки вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="ba048-183">Operating system (OS) of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba048-184">каллеркпунаме</span><span class="sxs-lookup"><span data-stu-id="ba048-184">CallerCPUName</span></span></p></td>
<td><p><span data-ttu-id="ba048-185">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="ba048-185">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="ba048-186">Название ЦП конечной точки вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="ba048-186">CPU name of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba048-187">калликпунаме</span><span class="sxs-lookup"><span data-stu-id="ba048-187">CalleeCPUName</span></span></p></td>
<td><p><span data-ttu-id="ba048-188">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="ba048-188">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="ba048-189">Название ЦП конечной точки вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="ba048-189">CPU name of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba048-190">каллеркпунумберофкорес</span><span class="sxs-lookup"><span data-stu-id="ba048-190">CallerCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="ba048-191">smallint</span><span class="sxs-lookup"><span data-stu-id="ba048-191">smallint</span></span></p></td>
<td><p><span data-ttu-id="ba048-192">Число ядер ЦП на конечной точке вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="ba048-192">Number of CPU cores in the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba048-193">калликпунумберофкорес</span><span class="sxs-lookup"><span data-stu-id="ba048-193">CalleeCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="ba048-194">smallint</span><span class="sxs-lookup"><span data-stu-id="ba048-194">smallint</span></span></p></td>
<td><p><span data-ttu-id="ba048-195">Число ядер ЦП на конечной точке вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="ba048-195">Number of CPU cores in the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba048-196">каллеркпупроцессорспид</span><span class="sxs-lookup"><span data-stu-id="ba048-196">CallerCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="ba048-197">int</span><span class="sxs-lookup"><span data-stu-id="ba048-197">int</span></span></p></td>
<td><p><span data-ttu-id="ba048-198">Скорость ЦП конечной точки вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="ba048-198">CPU processor speed of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba048-199">калликпупроцессорспид</span><span class="sxs-lookup"><span data-stu-id="ba048-199">CalleeCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="ba048-200">int</span><span class="sxs-lookup"><span data-stu-id="ba048-200">int</span></span></p></td>
<td><p><span data-ttu-id="ba048-201">Скорость ЦП конечной точки вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="ba048-201">CPU processor speed of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba048-202">каллервиртуализатионфлаг</span><span class="sxs-lookup"><span data-stu-id="ba048-202">CallerVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="ba048-203">tinyint</span><span class="sxs-lookup"><span data-stu-id="ba048-203">tinyint</span></span></p></td>
<td><p><span data-ttu-id="ba048-204">Указывает, работает ли система вызывающего абонента в виртуализованной среде.</span><span class="sxs-lookup"><span data-stu-id="ba048-204">Indicates whether the caller’s system is running in a virtualized environment.</span></span> <span data-ttu-id="ba048-205">Более подробную информацию можно узнать <a href="lync-server-2013-endpoint-table.md">в таблице конечная точка в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ba048-205">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba048-206">калливиртуализатионфлаг</span><span class="sxs-lookup"><span data-stu-id="ba048-206">CalleeVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="ba048-207">tinyint</span><span class="sxs-lookup"><span data-stu-id="ba048-207">tinyint</span></span></p></td>
<td><p><span data-ttu-id="ba048-208">Указывает, работает ли система вызываемого абонента в виртуализованной среде.</span><span class="sxs-lookup"><span data-stu-id="ba048-208">Indicates whether the callee’s system is running in a virtualized environment.</span></span> <span data-ttu-id="ba048-209">Более подробную информацию можно узнать <a href="lync-server-2013-endpoint-table.md">в таблице конечная точка в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ba048-209">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba048-210">коррелатионкэй</span><span class="sxs-lookup"><span data-stu-id="ba048-210">CorrelationKey</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ba048-211">Ключ корреляции.</span><span class="sxs-lookup"><span data-stu-id="ba048-211">Correlation key.</span></span> <span data-ttu-id="ba048-212">Ссылка из <a href="lync-server-2013-sessioncorrelation-table.md">таблицы таблица sessioncorrelation в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="ba048-212">Referenced from the <a href="lync-server-2013-sessioncorrelation-table.md">SessionCorrelation table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba048-213">коннективитице</span><span class="sxs-lookup"><span data-stu-id="ba048-213">ConnectivityIce</span></span></p></td>
<td><p><span data-ttu-id="ba048-214">tinyint</span><span class="sxs-lookup"><span data-stu-id="ba048-214">tinyint</span></span></p></td>
<td><p><span data-ttu-id="ba048-215">Сведения о канале передачи медиаданных, например прямой или ретранслируемый.</span><span class="sxs-lookup"><span data-stu-id="ba048-215">Information about the media path, such as direct or relayed.</span></span> <span data-ttu-id="ba048-216">Дополнительные сведения см. <a href="lync-server-2013-medialine-table.md">в таблице MediaLine в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ba048-216">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba048-217">каллерицеварнингфлагс</span><span class="sxs-lookup"><span data-stu-id="ba048-217">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="ba048-218">int</span><span class="sxs-lookup"><span data-stu-id="ba048-218">int</span></span></p></td>
<td><p><span data-ttu-id="ba048-p111">Сведения о технологии ICE (Interactive Connectivity Establishment), описанные в битовых флагах, для вызывающего абонента. Дополнительные сведения см. в спецификации протокола сервера мониторинга качества взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="ba048-p111">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba048-221">каллиицеварнингфлагс</span><span class="sxs-lookup"><span data-stu-id="ba048-221">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="ba048-222">int</span><span class="sxs-lookup"><span data-stu-id="ba048-222">int</span></span></p></td>
<td><p><span data-ttu-id="ba048-p112">Сведения о технологии ICE (Interactive Connectivity Establishment), описанные в битовых флагах, для вызываемого абонента. Дополнительные сведения см. в спецификации протокола сервера мониторинга качества взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="ba048-p112">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba048-225">Transport</span><span class="sxs-lookup"><span data-stu-id="ba048-225">Transport</span></span></p></td>
<td><p><span data-ttu-id="ba048-226">tinyint</span><span class="sxs-lookup"><span data-stu-id="ba048-226">tinyint</span></span></p></td>
<td><p><span data-ttu-id="ba048-227">Тип транспорта: 0 — UDP, 1 — TCP.</span><span class="sxs-lookup"><span data-stu-id="ba048-227">Transport type: 0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba048-228">каллерипаддр</span><span class="sxs-lookup"><span data-stu-id="ba048-228">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="ba048-229">var (50)</span><span class="sxs-lookup"><span data-stu-id="ba048-229">var(50)</span></span></p></td>
<td><p><span data-ttu-id="ba048-230">IP-адрес вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="ba048-230">IP address of the caller.</span></span> <span data-ttu-id="ba048-231">Это может быть IPv4-адрес или IPv6-адрес.</span><span class="sxs-lookup"><span data-stu-id="ba048-231">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba048-232">каллерпорт</span><span class="sxs-lookup"><span data-stu-id="ba048-232">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="ba048-233">int</span><span class="sxs-lookup"><span data-stu-id="ba048-233">int</span></span></p></td>
<td><p><span data-ttu-id="ba048-234">Порт, используемый вызывающим абонентом.</span><span class="sxs-lookup"><span data-stu-id="ba048-234">Port used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba048-235">каллеринсиде</span><span class="sxs-lookup"><span data-stu-id="ba048-235">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="ba048-236">Битовая</span><span class="sxs-lookup"><span data-stu-id="ba048-236">bit</span></span></p></td>
<td><p><span data-ttu-id="ba048-237">Указывает, находится ли вызывающий абонент во внутренней сети: 1 означает, что вызывающий абонент находится внутри корпоративной сети, 0 означает, что вызывающий абонент находится вне сети.</span><span class="sxs-lookup"><span data-stu-id="ba048-237">Indicates whether the caller is inside the interval network: 1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba048-238">каллиипаддр</span><span class="sxs-lookup"><span data-stu-id="ba048-238">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="ba048-239">var (50)</span><span class="sxs-lookup"><span data-stu-id="ba048-239">var(50)</span></span></p></td>
<td><p><span data-ttu-id="ba048-240">IP-адрес вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="ba048-240">IP address of the callee.</span></span> <span data-ttu-id="ba048-241">Это может быть IPv4-адрес или IPv6-адрес.</span><span class="sxs-lookup"><span data-stu-id="ba048-241">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba048-242">каллипорт</span><span class="sxs-lookup"><span data-stu-id="ba048-242">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="ba048-243">int</span><span class="sxs-lookup"><span data-stu-id="ba048-243">int</span></span></p></td>
<td><p><span data-ttu-id="ba048-244">Порт, используемый вызываемым абонентом.</span><span class="sxs-lookup"><span data-stu-id="ba048-244">Port used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba048-245">каллиинсиде</span><span class="sxs-lookup"><span data-stu-id="ba048-245">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="ba048-246">Битовая</span><span class="sxs-lookup"><span data-stu-id="ba048-246">bit</span></span></p></td>
<td><p><span data-ttu-id="ba048-247">Указывает, находится ли вызываемый абонент во внутренней сети: 1 означает, что вызываемый абонент находится внутри корпоративной сети, 0 означает, что вызываемый абонент находится вне сети.</span><span class="sxs-lookup"><span data-stu-id="ba048-247">Indicates whether the callee is inside the interval network: 1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba048-248">каллерусерсите</span><span class="sxs-lookup"><span data-stu-id="ba048-248">CallerUserSite</span></span></p></td>
<td><p><span data-ttu-id="ba048-249">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="ba048-249">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="ba048-250">Имя сайта вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="ba048-250">Name of the caller’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba048-251">каллеррегион</span><span class="sxs-lookup"><span data-stu-id="ba048-251">CallerRegion</span></span></p></td>
<td><p><span data-ttu-id="ba048-252">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="ba048-252">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="ba048-253">Название страны или региона, где находится сайт вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="ba048-253">Name of the country/region of the caller’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba048-254">каллиусерсите</span><span class="sxs-lookup"><span data-stu-id="ba048-254">CalleeUserSite</span></span></p></td>
<td><p><span data-ttu-id="ba048-255">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="ba048-255">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="ba048-256">Имя сайта вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="ba048-256">Name of the callee’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba048-257">каллирегион</span><span class="sxs-lookup"><span data-stu-id="ba048-257">CalleeRegion</span></span></p></td>
<td><p><span data-ttu-id="ba048-258">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="ba048-258">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="ba048-259">Название страны или региона, где находится сайт вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="ba048-259">Name of the country/region of the callee’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba048-260">каллеррелайипаддр</span><span class="sxs-lookup"><span data-stu-id="ba048-260">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="ba048-261">var (50)</span><span class="sxs-lookup"><span data-stu-id="ba048-261">var(50)</span></span></p></td>
<td><p><span data-ttu-id="ba048-262">IP-адрес пограничной службы обработки аудио- и видеоданных, используемой вызывающим абонентом.</span><span class="sxs-lookup"><span data-stu-id="ba048-262">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="ba048-263">Дополнительные сведения см. <a href="lync-server-2013-ipaddress-table.md">в таблице IPAddress в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ba048-263">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba048-264">каллеррелайпорт</span><span class="sxs-lookup"><span data-stu-id="ba048-264">CallerRelayPort</span></span></p></td>
<td><p><span data-ttu-id="ba048-265">int</span><span class="sxs-lookup"><span data-stu-id="ba048-265">int</span></span></p></td>
<td><p><span data-ttu-id="ba048-266">Порт, используемый вызывающим абонентом в пограничной службе обработки аудио- и видеоданных.</span><span class="sxs-lookup"><span data-stu-id="ba048-266">Port used on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba048-267">каллирелайипаддр</span><span class="sxs-lookup"><span data-stu-id="ba048-267">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="ba048-268">var (50)</span><span class="sxs-lookup"><span data-stu-id="ba048-268">var(50)</span></span></p></td>
<td><p><span data-ttu-id="ba048-269">IP-адрес пограничной службы обработки аудио- и видеоданных, используемой вызываемым абонентом.</span><span class="sxs-lookup"><span data-stu-id="ba048-269">IP Address key of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="ba048-270">Дополнительные сведения см. <a href="lync-server-2013-ipaddress-table.md">в таблице IPAddress в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ba048-270">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba048-271">каллирелайпорт</span><span class="sxs-lookup"><span data-stu-id="ba048-271">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="ba048-272">int</span><span class="sxs-lookup"><span data-stu-id="ba048-272">int</span></span></p></td>
<td><p><span data-ttu-id="ba048-273">Порт, используемый вызываемым абонентом в пограничной службе обработки аудио- и видеоданных.</span><span class="sxs-lookup"><span data-stu-id="ba048-273">Port used on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba048-274">каллеркаптуредев</span><span class="sxs-lookup"><span data-stu-id="ba048-274">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="ba048-275">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="ba048-275">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ba048-276">Имя устройства захвата вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="ba048-276">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba048-277">каллеррендердев</span><span class="sxs-lookup"><span data-stu-id="ba048-277">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="ba048-278">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="ba048-278">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ba048-279">Имя устройства обработки вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="ba048-279">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba048-280">каллеркаптуредевдривер</span><span class="sxs-lookup"><span data-stu-id="ba048-280">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="ba048-281">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="ba048-281">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ba048-282">Имя драйвера для устройства захвата вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="ba048-282">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba048-283">каллеррендердривер</span><span class="sxs-lookup"><span data-stu-id="ba048-283">CallerRenderDriver</span></span></p></td>
<td><p><span data-ttu-id="ba048-284">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="ba048-284">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ba048-285">Имя драйвера для устройства обработки вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="ba048-285">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba048-286">калликаптуредев</span><span class="sxs-lookup"><span data-stu-id="ba048-286">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="ba048-287">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="ba048-287">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ba048-288">Имя устройства захвата вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="ba048-288">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba048-289">каллирендердев</span><span class="sxs-lookup"><span data-stu-id="ba048-289">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="ba048-290">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="ba048-290">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ba048-291">Имя устройства обработки вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="ba048-291">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba048-292">калликаптуредевдривер</span><span class="sxs-lookup"><span data-stu-id="ba048-292">CalleeCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="ba048-293">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="ba048-293">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ba048-294">Имя драйвера для устройства захвата вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="ba048-294">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba048-295">каллирендердевдривер</span><span class="sxs-lookup"><span data-stu-id="ba048-295">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="ba048-296">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="ba048-296">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ba048-297">Имя драйвера для устройства обработки вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="ba048-297">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba048-298">каллернетворкконнектионтипе</span><span class="sxs-lookup"><span data-stu-id="ba048-298">CallerNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="ba048-299">tinyint</span><span class="sxs-lookup"><span data-stu-id="ba048-299">tinyint</span></span></p></td>
<td><p><span data-ttu-id="ba048-300">Тип подключения к сети вызывающего абонента: 0 — проводной, 1 — беспроводной.</span><span class="sxs-lookup"><span data-stu-id="ba048-300">Caller’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba048-301">каллервпн</span><span class="sxs-lookup"><span data-stu-id="ba048-301">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="ba048-302">Битовая</span><span class="sxs-lookup"><span data-stu-id="ba048-302">bit</span></span></p></td>
<td><p><span data-ttu-id="ba048-303">Указывает, подключен ли вызывающий абонент через виртуальную частную сеть: 1 — да, 0 — нет.</span><span class="sxs-lookup"><span data-stu-id="ba048-303">Indicates whether the caller connected over a virtual private network: 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba048-304">каллерлинкспид</span><span class="sxs-lookup"><span data-stu-id="ba048-304">CallerLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="ba048-305">десятичное число (18, 0)</span><span class="sxs-lookup"><span data-stu-id="ba048-305">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="ba048-306">Скорость сетевого соединения в бит/с для конечной точки вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="ba048-306">Network link speed for the caller's endpoint in bps.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba048-307">каллинетворкконнектионтипе</span><span class="sxs-lookup"><span data-stu-id="ba048-307">CalleeNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="ba048-308">tinyint</span><span class="sxs-lookup"><span data-stu-id="ba048-308">tinyint</span></span></p></td>
<td><p><span data-ttu-id="ba048-309">Тип подключения к сети вызываемого абонента: 0 — проводной, 1 — беспроводной.</span><span class="sxs-lookup"><span data-stu-id="ba048-309">Callee’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba048-310">калливпн</span><span class="sxs-lookup"><span data-stu-id="ba048-310">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="ba048-311">Битовая</span><span class="sxs-lookup"><span data-stu-id="ba048-311">bit</span></span></p></td>
<td><p><span data-ttu-id="ba048-312">Указывает, подключен ли вызываемый абонент через виртуальную частную сеть: 1 — да, 0 — нет.</span><span class="sxs-lookup"><span data-stu-id="ba048-312">Indicates whether the caller connected over a virtual private network: 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba048-313">каллилинкспид</span><span class="sxs-lookup"><span data-stu-id="ba048-313">CalleeLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="ba048-314">десятичное число (18, 0)</span><span class="sxs-lookup"><span data-stu-id="ba048-314">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="ba048-315">Скорость сетевого соединения в бит/с для конечной точки вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="ba048-315">Network link speed for the callee's endpoint in bps.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba048-316">конверсатионалмос</span><span class="sxs-lookup"><span data-stu-id="ba048-316">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="ba048-317">десятичное число (3, 2)</span><span class="sxs-lookup"><span data-stu-id="ba048-317">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="ba048-318">Узкополосный MOS аудиосеансов (на основе обоих аудиопотоков).</span><span class="sxs-lookup"><span data-stu-id="ba048-318">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba048-319">апплиедбандвидслимит</span><span class="sxs-lookup"><span data-stu-id="ba048-319">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="ba048-320">int</span><span class="sxs-lookup"><span data-stu-id="ba048-320">int</span></span></p></td>
<td><p><span data-ttu-id="ba048-p117">Фактическая пропускная способность, доступная указанному потоку с учетом заданных параметров политики (TURN, API, SDP, сервер политики и т. д.). Это значение не следует путать с эффективной пропускной способностью, так как эффективная пропускная способность может оказаться ниже на основе оценки полосы пропускания. Это, по сути, максимальная пропускная способность отправляемого потока с учетом ограничений, наложенных оценкой полосы пропускания.</span><span class="sxs-lookup"><span data-stu-id="ba048-p117">Actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on). This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate. This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba048-324">життеринтерарривал</span><span class="sxs-lookup"><span data-stu-id="ba048-324">JitterInterArrival</span></span></p></td>
<td><p><span data-ttu-id="ba048-325">int</span><span class="sxs-lookup"><span data-stu-id="ba048-325">int</span></span></p></td>
<td><p><span data-ttu-id="ba048-326">Средний уровень дрожания в сети на основе статистики протокола RTCP.</span><span class="sxs-lookup"><span data-stu-id="ba048-326">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba048-327">життеринтерарривалмакс</span><span class="sxs-lookup"><span data-stu-id="ba048-327">JitterInterArrivalMax</span></span></p></td>
<td><p><span data-ttu-id="ba048-328">int</span><span class="sxs-lookup"><span data-stu-id="ba048-328">int</span></span></p></td>
<td><p><span data-ttu-id="ba048-329">Максимальный уровень дрожания в сети в течение вызова.</span><span class="sxs-lookup"><span data-stu-id="ba048-329">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba048-330">паккетлоссрате</span><span class="sxs-lookup"><span data-stu-id="ba048-330">PacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="ba048-331">десятичное число (5, 4)</span><span class="sxs-lookup"><span data-stu-id="ba048-331">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="ba048-332">Средний коэффициент потерь пакетов в течение вызова.</span><span class="sxs-lookup"><span data-stu-id="ba048-332">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba048-333">паккетлоссратемакс</span><span class="sxs-lookup"><span data-stu-id="ba048-333">PacketLossRateMax</span></span></p></td>
<td><p><span data-ttu-id="ba048-334">десятичное число (5, 4)</span><span class="sxs-lookup"><span data-stu-id="ba048-334">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="ba048-335">Максимальная потеря пакетов, наблюдавшаяся в течение вызова.</span><span class="sxs-lookup"><span data-stu-id="ba048-335">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba048-336">бурстденсити</span><span class="sxs-lookup"><span data-stu-id="ba048-336">BurstDensity</span></span></p></td>
<td><p><span data-ttu-id="ba048-337">десятичное число (9, 4)</span><span class="sxs-lookup"><span data-stu-id="ba048-337">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="ba048-338">Средняя плотность потерь пакетов во время пиков потерь в течение вызова.</span><span class="sxs-lookup"><span data-stu-id="ba048-338">Average density of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba048-339">бурстдуратион</span><span class="sxs-lookup"><span data-stu-id="ba048-339">BurstDuration</span></span></p></td>
<td><p><span data-ttu-id="ba048-340">int</span><span class="sxs-lookup"><span data-stu-id="ba048-340">int</span></span></p></td>
<td><p><span data-ttu-id="ba048-341">Средняя продолжительность потерь пакетов во время пиков потерь в течение вызова.</span><span class="sxs-lookup"><span data-stu-id="ba048-341">Average duration of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba048-342">бурстгапденсити</span><span class="sxs-lookup"><span data-stu-id="ba048-342">BurstGapDensity</span></span></p></td>
<td><p><span data-ttu-id="ba048-343">десятичное число (9, 4)</span><span class="sxs-lookup"><span data-stu-id="ba048-343">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="ba048-344">Средняя плотность потерь пакетов в промежутках между пиками потерь.</span><span class="sxs-lookup"><span data-stu-id="ba048-344">Average density of packet loss during gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba048-345">бурстгапдуратион</span><span class="sxs-lookup"><span data-stu-id="ba048-345">BurstGapDuration</span></span></p></td>
<td><p><span data-ttu-id="ba048-346">int</span><span class="sxs-lookup"><span data-stu-id="ba048-346">int</span></span></p></td>
<td><p><span data-ttu-id="ba048-347">Средняя продолжительность промежутков между пиками потерь пакетов.</span><span class="sxs-lookup"><span data-stu-id="ba048-347">Average duration of gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba048-348">паккетутилизатион</span><span class="sxs-lookup"><span data-stu-id="ba048-348">PacketUtilization</span></span></p></td>
<td><p><span data-ttu-id="ba048-349">int</span><span class="sxs-lookup"><span data-stu-id="ba048-349">int</span></span></p></td>
<td><p><span data-ttu-id="ba048-350">Количество пакетов для аудиопотока.</span><span class="sxs-lookup"><span data-stu-id="ba048-350">Packet count for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba048-351">Самый полоса пропускания</span><span class="sxs-lookup"><span data-stu-id="ba048-351">BandwidthEst</span></span></p></td>
<td><p><span data-ttu-id="ba048-352">int</span><span class="sxs-lookup"><span data-stu-id="ba048-352">int</span></span></p></td>
<td><p><span data-ttu-id="ba048-353">Оценка пропускной способности для аудиопотока.</span><span class="sxs-lookup"><span data-stu-id="ba048-353">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba048-354">деградатионавг</span><span class="sxs-lookup"><span data-stu-id="ba048-354">DegradationAvg</span></span></p></td>
<td><p><span data-ttu-id="ba048-355">десятичное число (3, 2)</span><span class="sxs-lookup"><span data-stu-id="ba048-355">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="ba048-p118">Снижение экспертной оценки качества (MOS) в сети для всего звонка в диапазоне от 0,0 до 5,0. Эта метрика показывает величину уменьшения MOS в сети, обусловленную дрожанием и потерей пакетов. Для приемлемого качества это значение должно быть меньше, чем 0,5.</span><span class="sxs-lookup"><span data-stu-id="ba048-p118">Network MOS Degradation for the whole call. Range is 0.0 to 5.0. This metric shows the amount the Network MOS was reduced because of jitter and packet loss. For acceptable quality it should less than 0.5.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba048-360">деградатионмакс</span><span class="sxs-lookup"><span data-stu-id="ba048-360">DegradationMax</span></span></p></td>
<td><p><span data-ttu-id="ba048-361">десятичное число (3, 2)</span><span class="sxs-lookup"><span data-stu-id="ba048-361">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="ba048-362">Максимальное снижение экспертной оценки качества (MOS) в сети во время звонка.</span><span class="sxs-lookup"><span data-stu-id="ba048-362">Maximum Network MOS degradation during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba048-363">деградатионжиттеравг</span><span class="sxs-lookup"><span data-stu-id="ba048-363">DegradationJitterAvg</span></span></p></td>
<td><p><span data-ttu-id="ba048-364">десятичное число (3, 2)</span><span class="sxs-lookup"><span data-stu-id="ba048-364">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="ba048-365">Снижение экспертной оценки качества (MOS) в сети, вызванное дрожанием.</span><span class="sxs-lookup"><span data-stu-id="ba048-365">Network MOS degradation caused by jitter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba048-366">деградатионпаккетлоссавг</span><span class="sxs-lookup"><span data-stu-id="ba048-366">DegradationPacketLossAvg</span></span></p></td>
<td><p><span data-ttu-id="ba048-367">десятичное число (3, 2)</span><span class="sxs-lookup"><span data-stu-id="ba048-367">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="ba048-368">Снижение экспертной оценки качества (MOS) в сети, вызванное потерей пакетов.</span><span class="sxs-lookup"><span data-stu-id="ba048-368">Network MOS degradation caused by packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba048-369">PayloadDescription</span><span class="sxs-lookup"><span data-stu-id="ba048-369">PayloadDescription</span></span></p></td>
<td><p><span data-ttu-id="ba048-370">int</span><span class="sxs-lookup"><span data-stu-id="ba048-370">int</span></span></p></td>
<td><p><span data-ttu-id="ba048-371">Аудиокодек, используемый для вызова, на который ссылается <a href="lync-server-2013-payloaddescription-table.md">таблица таблица payloaddescription в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="ba048-371">The audio codec used for the call, referenced from the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba048-372">аудиосамплерате</span><span class="sxs-lookup"><span data-stu-id="ba048-372">AudioSampleRate</span></span></p></td>
<td><p><span data-ttu-id="ba048-373">int</span><span class="sxs-lookup"><span data-stu-id="ba048-373">int</span></span></p></td>
<td><p><span data-ttu-id="ba048-374">Частота выборки для аудиопотока.</span><span class="sxs-lookup"><span data-stu-id="ba048-374">Sampling rate for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba048-375">каллерсендсигналлевел</span><span class="sxs-lookup"><span data-stu-id="ba048-375">CallerSendSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="ba048-376">int</span><span class="sxs-lookup"><span data-stu-id="ba048-376">int</span></span></p></td>
<td><p><span data-ttu-id="ba048-p119">Послеаналоговая регулировка уровня звукового сигнала для аудиопотока, отправленного вызывающим абонентом. Единица измерения для этого показателя — дБмо. Для приемлемого качества значение должно быть не менее 30 дБмо. Этот показатель не сообщается сервером аудио- и видеоконференций и IP-телефонами.</span><span class="sxs-lookup"><span data-stu-id="ba048-p119">Post-Analog Gain Control audio signal level for the audio the caller sent. The unit for this metric is dBmo. For acceptable quality, it should be at least 30 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba048-381">каллерреквсигналлевел</span><span class="sxs-lookup"><span data-stu-id="ba048-381">CallerRecvSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="ba048-382">int</span><span class="sxs-lookup"><span data-stu-id="ba048-382">int</span></span></p></td>
<td><p><span data-ttu-id="ba048-p120">Уровень звукового сигнала для аудиопотока, принятого вызывающим абонентом. Единица измерения для этого показателя — дБмо. Для приемлемого качества значение должно быть не менее 30 дБмо. Этот показатель не сообщается сервером аудио- и видеоконференций и IP-телефонами.</span><span class="sxs-lookup"><span data-stu-id="ba048-p120">Audio signal level for the audio the caller received. The unit for this metric is dBmo. For acceptable quality, it should be at least 30 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba048-387">каллерсендноиселевел</span><span class="sxs-lookup"><span data-stu-id="ba048-387">CallerSendNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="ba048-388">int</span><span class="sxs-lookup"><span data-stu-id="ba048-388">int</span></span></p></td>
<td><p><span data-ttu-id="ba048-p121">Послеаналоговая регулировка уровня акустического шума для аудиопотока, отправленного вызывающим абонентом. Единица измерения для этого показателя — дБмо. Для приемлемого качества значение должно быть менее 35 дБмо. Этот показатель не сообщается сервером аудио- и видеоконференций и IP-телефонами.</span><span class="sxs-lookup"><span data-stu-id="ba048-p121">Post-Analog Gain Control audio noise level for the audio the caller sent. The unit for this metric is dBmo. For acceptable quality, it should be less than 35 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba048-393">каллерреквноиселевел</span><span class="sxs-lookup"><span data-stu-id="ba048-393">CallerRecvNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="ba048-394">int</span><span class="sxs-lookup"><span data-stu-id="ba048-394">int</span></span></p></td>
<td><p><span data-ttu-id="ba048-p122">Послеаналоговая регулировка уровня акустического шума для аудиопотока, полученного вызывающим абонентом. Единица измерения для этого показателя — дБмо. Для приемлемого качества значение должно быть менее 35 дБмо. Этот показатель не сообщается сервером аудио- и видеоконференций и IP-телефонами.</span><span class="sxs-lookup"><span data-stu-id="ba048-p122">Post-Analog Gain Control audio noise level for the audio the caller received. The unit for this metric is dBmo. For acceptable quality, it should be less than 35 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba048-399">каллеречоретурн</span><span class="sxs-lookup"><span data-stu-id="ba048-399">CallerEchoReturn</span></span></p></td>
<td><p><span data-ttu-id="ba048-400">int</span><span class="sxs-lookup"><span data-stu-id="ba048-400">int</span></span></p></td>
<td><p><span data-ttu-id="ba048-p123">Отношение мощностей некомпенсированного и скомпенсированного эхосигнала для вызывающего абонента. Единица измерения для этого показателя — дБ. Чем ниже значение, тем меньше эхосигнал. Этот показатель не сообщается сервером аудио- и видеоконференций и IP-телефонами.</span><span class="sxs-lookup"><span data-stu-id="ba048-p123">Echo Return Loss Enhancement for the caller. The unit for this metric is dB. Lower values represent less echo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba048-405">каллерспеакерглитчрате</span><span class="sxs-lookup"><span data-stu-id="ba048-405">CallerSpeakerGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="ba048-406">int</span><span class="sxs-lookup"><span data-stu-id="ba048-406">int</span></span></p></td>
<td><p><span data-ttu-id="ba048-p124">Среднее количество временных сбоев за пять минут при воспроизведении акустическими системами вызывающего абонента. Для хорошего качества должно быть не более одного сбоя в пять минут. Этот показатель не сообщается серверами аудио- и видеоконференций, серверами-посредниками и IP-телефонами.</span><span class="sxs-lookup"><span data-stu-id="ba048-p124">Average glitches per five minutes for the caller’s loudspeaker rendering. For good quality, this should be less than one per five minutes. Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba048-410">каллермикглитчрате</span><span class="sxs-lookup"><span data-stu-id="ba048-410">CallerMicGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="ba048-411">int</span><span class="sxs-lookup"><span data-stu-id="ba048-411">int</span></span></p></td>
<td><p><span data-ttu-id="ba048-p125">Среднее количество временных сбоев за пять минут при захвате звука микрофоном вызывающего абонента. Для хорошего качества должно быть не более одного сбоя в пять минут. Этот показатель не сообщается серверами аудио- и видеоконференций, серверами-посредниками и IP-телефонами.</span><span class="sxs-lookup"><span data-stu-id="ba048-p125">Average glitches per five minutes for the caller’s microphone capture. For good quality this should be less than one per five minutes. Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba048-415">каллертиместампдрифтратемик</span><span class="sxs-lookup"><span data-stu-id="ba048-415">CallerTimestampDriftRateMic</span></span></p></td>
<td><p><span data-ttu-id="ba048-416">десятичное число (9, 2)</span><span class="sxs-lookup"><span data-stu-id="ba048-416">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="ba048-417">Скорость рассинхронизации часов микрофона вызывающего абонента относительно часов процессора.</span><span class="sxs-lookup"><span data-stu-id="ba048-417">Caller’s microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba048-418">каллертиместампдрифтратеспк</span><span class="sxs-lookup"><span data-stu-id="ba048-418">CallerTimestampDriftRateSpk</span></span></p></td>
<td><p><span data-ttu-id="ba048-419">десятичное число (9, 2)</span><span class="sxs-lookup"><span data-stu-id="ba048-419">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="ba048-420">Скорость рассинхронизации часов динамика вызывающего абонента относительно часов процессора.</span><span class="sxs-lookup"><span data-stu-id="ba048-420">Caller’s speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba048-421">каллертиместамперрормикмс</span><span class="sxs-lookup"><span data-stu-id="ba048-421">CallerTimestampErrorMicMs</span></span></p></td>
<td><p><span data-ttu-id="ba048-422">десятичное число (9, 2)</span><span class="sxs-lookup"><span data-stu-id="ba048-422">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="ba048-423">Средняя ошибка метки времени для потока захвата микрофоном, в миллисекундах, в последние 20 секунд вызова.</span><span class="sxs-lookup"><span data-stu-id="ba048-423">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba048-424">каллертиместамперрорспкмс</span><span class="sxs-lookup"><span data-stu-id="ba048-424">CallerTimestampErrorSpkMs</span></span></p></td>
<td><p><span data-ttu-id="ba048-425">десятичное число (9, 2)</span><span class="sxs-lookup"><span data-stu-id="ba048-425">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="ba048-426">Средняя ошибка метки времени для потока воспроизведения динамиком вызывающего абонента, в миллисекундах, в последние 20 секунд вызова.</span><span class="sxs-lookup"><span data-stu-id="ba048-426">Average of the caller’s speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba048-427">каллервсентрикаусес</span><span class="sxs-lookup"><span data-stu-id="ba048-427">CallerVsEntryCauses</span></span></p></td>
<td><p><span data-ttu-id="ba048-428">smallint</span><span class="sxs-lookup"><span data-stu-id="ba048-428">smallint</span></span></p></td>
<td><p><span data-ttu-id="ba048-429">Речевой коммутатор — это полудуплексный режим с уменьшенной возможностью прерывания.</span><span class="sxs-lookup"><span data-stu-id="ba048-429">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="ba048-430">Дополнительные сведения см. <a href="lync-server-2013-medialine-table.md">в таблице MediaLine в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ba048-430">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba048-431">каллеречоевенткаусес</span><span class="sxs-lookup"><span data-stu-id="ba048-431">CallerEchoEventCauses</span></span></p></td>
<td><p><span data-ttu-id="ba048-432">tinyint</span><span class="sxs-lookup"><span data-stu-id="ba048-432">tinyint</span></span></p></td>
<td><p><span data-ttu-id="ba048-433">Причины события эхосигнала для вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="ba048-433">Causes of an echo event for the caller.</span></span> <span data-ttu-id="ba048-434">Дополнительные сведения см. <a href="lync-server-2013-medialine-table.md">в таблице MediaLine в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ba048-434">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba048-435">каллеречоперцентмиЦин</span><span class="sxs-lookup"><span data-stu-id="ba048-435">CallerEchoPercentMicIn</span></span></p></td>
<td><p><span data-ttu-id="ba048-436">десятичное число (5, 2)</span><span class="sxs-lookup"><span data-stu-id="ba048-436">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="ba048-p128">Процент времени, когда в потоке захвата микрофоном вызывающего абонента обнаруживается эхосигнал. Если используется гарнитура, то значение должно быть низким.</span><span class="sxs-lookup"><span data-stu-id="ba048-p128">Percentage of time when echo is detected in the caller’s microphone capture stream. If headset is used, the value should be low.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba048-439">каллеречоперцентсенд</span><span class="sxs-lookup"><span data-stu-id="ba048-439">CallerEchoPercentSend</span></span></p></td>
<td><p><span data-ttu-id="ba048-440">десятичное число (5, 2)</span><span class="sxs-lookup"><span data-stu-id="ba048-440">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="ba048-p129">Процент времени, когда в потоке, отправленном вызывающим абонентом, обнаруживается эхосигнал. Высокое значение в отправленных потоках указывает на утечку эхосигнала.</span><span class="sxs-lookup"><span data-stu-id="ba048-p129">Percentage of time when echo is detected in the caller’s sent stream. High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba048-443">каллеррксагксигналлевел</span><span class="sxs-lookup"><span data-stu-id="ba048-443">CallerRxAGCSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="ba048-444">int</span><span class="sxs-lookup"><span data-stu-id="ba048-444">int</span></span></p></td>
<td><p><span data-ttu-id="ba048-p130">Уровень сигнала, полученный на сервере-посреднике от шлюза, для аудиопотока вызывающего абонента; этот показатель относится только к серверу-посреднику. Единица измерения — dBoV. Приемлемый диапазон для хорошего качества — от -30 до -18 dBoV.</span><span class="sxs-lookup"><span data-stu-id="ba048-p130">Received signal level on the Mediation Server from the Gateway for the caller’s audio; this applies only to the Mediation Server. The unit of this metric is dBoV. For good quality, the acceptable range should be -30 to -18 dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba048-448">каллеррксагкноиселевел</span><span class="sxs-lookup"><span data-stu-id="ba048-448">CallerRxAGCNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="ba048-449">int</span><span class="sxs-lookup"><span data-stu-id="ba048-449">int</span></span></p></td>
<td><p><span data-ttu-id="ba048-p131">Уровень акустического шума, полученный на сервере-посреднике от шлюза, для аудиопотока вызывающего абонента. Этот показатель относится только к серверу-посреднику. Единица измерения — dBoV. Приемлемый диапазон для хорошего качества — ниже -50 dBoV.</span><span class="sxs-lookup"><span data-stu-id="ba048-p131">Received signal level on the Mediation Server from the Gateway for the caller’s audio. This applies only to the Mediation Server. The unit of this metric is dBoV. For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba048-454">каллеррксагкгаин</span><span class="sxs-lookup"><span data-stu-id="ba048-454">CallerRxAGCGain</span></span></p></td>
<td><p><span data-ttu-id="ba048-455">int</span><span class="sxs-lookup"><span data-stu-id="ba048-455">int</span></span></p></td>
<td><p><span data-ttu-id="ba048-456">Автоматическая регулировка усиления на стороне сервера-посредника, применяемая к аудиопотоку вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="ba048-456">Automatic gain control (AGC) on the Mediation Server side applied to the caller’s audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba048-457">каллеринитиалсигналлевелрмс</span><span class="sxs-lookup"><span data-stu-id="ba048-457">CallerInitialSignalLevelRMS</span></span></p></td>
<td><p><span data-ttu-id="ba048-458">float</span><span class="sxs-lookup"><span data-stu-id="ba048-458">float</span></span></p></td>
<td><p><span data-ttu-id="ba048-459">Среднеквадратическое отклонение входящего сигнала вызывающего абонента до 30 первых секунд вызова.</span><span class="sxs-lookup"><span data-stu-id="ba048-459">Root mean square (RMS) of the incoming signal to the caller for up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba048-460">каллисендсигналлевел</span><span class="sxs-lookup"><span data-stu-id="ba048-460">CalleeSendSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="ba048-461">int</span><span class="sxs-lookup"><span data-stu-id="ba048-461">int</span></span></p></td>
<td><p><span data-ttu-id="ba048-p132">Послеаналоговая регулировка уровня звукового сигнала для аудиопотока, отправленного вызываемым абонентом. Единица измерения для этого показателя — дБмо. Для приемлемого качества значение должно быть не менее 30 дБмо. Этот показатель не сообщается сервером аудио- и видеоконференций и IP-телефонами.</span><span class="sxs-lookup"><span data-stu-id="ba048-p132">Represents the Post-Analog Gain Control audio signal level for the audio the callee sent. The unit for this metric is dBmo. For acceptable quality, it should be at least 30 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba048-466">каллиреквсигналлевел</span><span class="sxs-lookup"><span data-stu-id="ba048-466">CalleeRecvSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="ba048-467">int</span><span class="sxs-lookup"><span data-stu-id="ba048-467">int</span></span></p></td>
<td><p><span data-ttu-id="ba048-p133">Уровень звукового сигнала для аудиопотока, принятого вызываемым абонентом. Единица измерения для этого показателя — дБмо. Для приемлемого качества значение должно быть не менее 30 дБмо. Этот показатель не сообщается сервером аудио- и видеоконференций и IP-телефонами.</span><span class="sxs-lookup"><span data-stu-id="ba048-p133">Audio signal level for the audio the callee received. The unit for this metric is dBmo. For acceptable quality, it should be at least 30 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba048-472">каллисендноиселевел</span><span class="sxs-lookup"><span data-stu-id="ba048-472">CalleeSendNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="ba048-473">int</span><span class="sxs-lookup"><span data-stu-id="ba048-473">int</span></span></p></td>
<td><p><span data-ttu-id="ba048-p134">Послеаналоговая регулировка уровня акустического шума для аудиопотока, отправленного вызываемым абонентом. Единица измерения для этого показателя — дБмо. Для приемлемого качества значение должно быть менее 35 дБмо. Этот показатель не сообщается сервером аудио- и видеоконференций и IP-телефонами.</span><span class="sxs-lookup"><span data-stu-id="ba048-p134">Post-Analog Gain Control audio noise level for the audio the callee sent. The unit for this metric is dBmo. For acceptable quality, it should be less than 35 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba048-478">каллиреквноиселевел</span><span class="sxs-lookup"><span data-stu-id="ba048-478">CalleeRecvNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="ba048-479">int</span><span class="sxs-lookup"><span data-stu-id="ba048-479">int</span></span></p></td>
<td><p><span data-ttu-id="ba048-p135">Послеаналоговая регулировка уровня акустического шума для аудиопотока, принятого вызываемым абонентом. Единица измерения для этого показателя — дБмо. Для приемлемого качества значение должно быть менее 35 дБмо. Этот показатель не сообщается сервером аудио- и видеоконференций и IP-телефонами.</span><span class="sxs-lookup"><span data-stu-id="ba048-p135">Post-Analog Gain Control audio noise level for the audio the callee received. The unit for this metric is dBmo. For acceptable quality, it should be less than 35 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba048-484">каллиечоретурн</span><span class="sxs-lookup"><span data-stu-id="ba048-484">CalleeEchoReturn</span></span></p></td>
<td><p><span data-ttu-id="ba048-485">int</span><span class="sxs-lookup"><span data-stu-id="ba048-485">int</span></span></p></td>
<td><p><span data-ttu-id="ba048-p136">Отношение мощностей некомпенсированного и скомпенсированного эхосигнала для вызываемого абонента. Единица измерения для этого показателя — дБ. Чем ниже значение, тем меньше эхосигнал. Этот показатель не сообщается сервером аудио- и видеоконференций и IP-телефонами.</span><span class="sxs-lookup"><span data-stu-id="ba048-p136">Echo Return Loss Enhancement for the callee. The unit for this metric is dB. Lower values represent less echo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba048-490">каллиспеакерглитчрате</span><span class="sxs-lookup"><span data-stu-id="ba048-490">CalleeSpeakerGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="ba048-491">int</span><span class="sxs-lookup"><span data-stu-id="ba048-491">int</span></span></p></td>
<td><p><span data-ttu-id="ba048-p137">Среднее количество временных сбоев за пять минут при воспроизведении акустическими системами вызываемого абонента. Для хорошего качества должно быть не более одного сбоя в пять минут. Этот показатель не сообщается серверами аудио- и видеоконференций, серверами-посредниками и IP-телефонами.</span><span class="sxs-lookup"><span data-stu-id="ba048-p137">Average glitches per five minutes for the callee’s loudspeaker rendering. For good quality, this should be less than one per five minutes. Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba048-495">каллимикглитчрате</span><span class="sxs-lookup"><span data-stu-id="ba048-495">CalleeMicGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="ba048-496">int</span><span class="sxs-lookup"><span data-stu-id="ba048-496">int</span></span></p></td>
<td><p><span data-ttu-id="ba048-p138">Среднее количество временных сбоев за пять минут при захвате звука микрофоном вызываемого абонента. Для хорошего качества должно быть не более одного сбоя в пять минут. Этот показатель не сообщается серверами аудио- и видеоконференций, серверами-посредниками и IP-телефонами.</span><span class="sxs-lookup"><span data-stu-id="ba048-p138">Average glitches per five minutes for the callee’s microphone capture. For good quality this should be less than one per five minutes. Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba048-500">каллитиместампдрифтратемик</span><span class="sxs-lookup"><span data-stu-id="ba048-500">CalleeTimestampDriftRateMic</span></span></p></td>
<td><p><span data-ttu-id="ba048-501">десятичное число (9, 2)</span><span class="sxs-lookup"><span data-stu-id="ba048-501">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="ba048-502">Скорость рассинхронизации часов микрофона вызываемого абонента относительно часов процессора.</span><span class="sxs-lookup"><span data-stu-id="ba048-502">Callee’s microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba048-503">каллитиместампдрифтратеспк</span><span class="sxs-lookup"><span data-stu-id="ba048-503">CalleeTimestampDriftRateSpk</span></span></p></td>
<td><p><span data-ttu-id="ba048-504">десятичное число (9, 2)</span><span class="sxs-lookup"><span data-stu-id="ba048-504">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="ba048-505">Скорость рассинхронизации часов динамика вызываемого абонента относительно часов процессора.</span><span class="sxs-lookup"><span data-stu-id="ba048-505">Callee’s speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba048-506">каллитиместамперрормикмс</span><span class="sxs-lookup"><span data-stu-id="ba048-506">CalleeTimestampErrorMicMs</span></span></p></td>
<td><p><span data-ttu-id="ba048-507">десятичное число (9, 2)</span><span class="sxs-lookup"><span data-stu-id="ba048-507">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="ba048-508">Средняя ошибка метки времени для потока захвата микрофоном, в миллисекундах, в последние 20 секунд вызова.</span><span class="sxs-lookup"><span data-stu-id="ba048-508">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba048-509">каллитиместамперрорспкмс</span><span class="sxs-lookup"><span data-stu-id="ba048-509">CalleeTimestampErrorSpkMs</span></span></p></td>
<td><p><span data-ttu-id="ba048-510">десятичное число (9, 2)</span><span class="sxs-lookup"><span data-stu-id="ba048-510">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="ba048-511">Средняя ошибка метки времени для потока воспроизведения динамиком вызываемого абонента, в миллисекундах, в последние 20 секунд вызова.</span><span class="sxs-lookup"><span data-stu-id="ba048-511">Average of the callee’s speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba048-512">калливсентрикаусес</span><span class="sxs-lookup"><span data-stu-id="ba048-512">CalleeVsEntryCauses</span></span></p></td>
<td><p><span data-ttu-id="ba048-513">smallint</span><span class="sxs-lookup"><span data-stu-id="ba048-513">smallint</span></span></p></td>
<td><p><span data-ttu-id="ba048-514">Речевой коммутатор — это полудуплексный режим с уменьшенной возможностью прерывания.</span><span class="sxs-lookup"><span data-stu-id="ba048-514">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="ba048-515">Дополнительные сведения см. <a href="lync-server-2013-medialine-table.md">в таблице MediaLine в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ba048-515">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba048-516">каллиечоевенткаусес</span><span class="sxs-lookup"><span data-stu-id="ba048-516">CalleeEchoEventCauses</span></span></p></td>
<td><p><span data-ttu-id="ba048-517">tinyint</span><span class="sxs-lookup"><span data-stu-id="ba048-517">tinyint</span></span></p></td>
<td><p><span data-ttu-id="ba048-518">Причины события эхосигнала для вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="ba048-518">Causes of an echo event for the callee.</span></span> <span data-ttu-id="ba048-519">Дополнительные сведения см. <a href="lync-server-2013-medialine-table.md">в таблице MediaLine в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ba048-519">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba048-520">каллиечоперцентмиЦин</span><span class="sxs-lookup"><span data-stu-id="ba048-520">CalleeEchoPercentMicIn</span></span></p></td>
<td><p><span data-ttu-id="ba048-521">десятичное число (5, 2)</span><span class="sxs-lookup"><span data-stu-id="ba048-521">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="ba048-p141">Процент времени, когда в потоке захвата микрофоном вызываемого абонента обнаруживается эхосигнал. Если используется гарнитура, то значение должно быть низким.</span><span class="sxs-lookup"><span data-stu-id="ba048-p141">Percentage of time when echo is detected in the callee’s microphone capture stream. If headset is used, the value should be low.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba048-524">каллиечоперцентсенд</span><span class="sxs-lookup"><span data-stu-id="ba048-524">CalleeEchoPercentSend</span></span></p></td>
<td><p><span data-ttu-id="ba048-525">десятичное число (5, 2)</span><span class="sxs-lookup"><span data-stu-id="ba048-525">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="ba048-p142">Процент времени, когда в потоке, отправленном вызываемым абонентом, обнаруживается эхосигнал. Высокое значение в отправленных потоках указывает на утечку эхосигнала.</span><span class="sxs-lookup"><span data-stu-id="ba048-p142">Percentage of time when echo is detected in the callee’s sent stream. High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba048-528">каллирксагксигналлевел</span><span class="sxs-lookup"><span data-stu-id="ba048-528">CalleeRxAGCSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="ba048-529">int</span><span class="sxs-lookup"><span data-stu-id="ba048-529">int</span></span></p></td>
<td><p><span data-ttu-id="ba048-p143">Уровень сигнала, полученный на сервере-посреднике от шлюза, для аудиопотока вызываемого абонента; этот показатель относится только к серверу-посреднику. Единица измерения — dBoV. Приемлемый диапазон для хорошего качества — от -30 до -18 dBoV.</span><span class="sxs-lookup"><span data-stu-id="ba048-p143">Received signal level on the Mediation Server from the Gateway for the callee’s audio; this applies only to the Mediation Server. The unit of this metric is dBoV. For good quality, the acceptable range should be [-30 to -18] dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba048-533">каллирксагкноиселевел</span><span class="sxs-lookup"><span data-stu-id="ba048-533">CalleeRxAGCNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="ba048-534">int</span><span class="sxs-lookup"><span data-stu-id="ba048-534">int</span></span></p></td>
<td><p><span data-ttu-id="ba048-p144">Уровень акустического шума, полученный на сервере-посреднике от шлюза, для аудиопотока вызываемого абонента. Этот показатель относится только к серверу-посреднику. Единица измерения — dBoV. Приемлемый диапазон для хорошего качества — ниже -50 dBoV.</span><span class="sxs-lookup"><span data-stu-id="ba048-p144">Received signal level on the Mediation Server from the Gateway for the callee’s audio. This applies only to the Mediation Server. The unit of this metric is dBoV. For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba048-539">каллирксагкгаин</span><span class="sxs-lookup"><span data-stu-id="ba048-539">CalleeRxAGCGain</span></span></p></td>
<td><p><span data-ttu-id="ba048-540">int</span><span class="sxs-lookup"><span data-stu-id="ba048-540">int</span></span></p></td>
<td><p><span data-ttu-id="ba048-541">Автоматическая регулировка усиления на стороне сервера-посредника, применяемая к аудиопотоку вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="ba048-541">Automatic gain control (AGC) on the Mediation Server side applied to the callee’s audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba048-542">каллиинитиалсигналлевелрмс</span><span class="sxs-lookup"><span data-stu-id="ba048-542">CalleeInitialSignalLevelRMS</span></span></p></td>
<td><p><span data-ttu-id="ba048-543">float</span><span class="sxs-lookup"><span data-stu-id="ba048-543">float</span></span></p></td>
<td><p><span data-ttu-id="ba048-544">Среднеквадратическое отклонение входящего сигнала вызываемого абонента до 30 первых секунд вызова.</span><span class="sxs-lookup"><span data-stu-id="ba048-544">Root mean square (RMS) of the incoming signal to the callee for up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba048-545">RatioConcealedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="ba048-545">RatioConcealedSamplesAvg</span></span></p></td>
<td><p><span data-ttu-id="ba048-546">десятичное число (5, 2)</span><span class="sxs-lookup"><span data-stu-id="ba048-546">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="ba048-547">Среднее отношение числа скрытых образцов, созданных функцией восстановления звука, к обычным образцам.</span><span class="sxs-lookup"><span data-stu-id="ba048-547">Average ratio of concealed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba048-548">ратиостретчедсамплесавг</span><span class="sxs-lookup"><span data-stu-id="ba048-548">RatioStretchedSamplesAvg</span></span></p></td>
<td><p><span data-ttu-id="ba048-549">десятичное число (5, 2)</span><span class="sxs-lookup"><span data-stu-id="ba048-549">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="ba048-550">Среднее отношение числа растянутых образцов, созданных функцией восстановления звука, к обычным образцам.</span><span class="sxs-lookup"><span data-stu-id="ba048-550">Average ratio of stretched samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba048-551">ратиокомпресседсамплесавг</span><span class="sxs-lookup"><span data-stu-id="ba048-551">RatioCompressedSamplesAvg</span></span></p></td>
<td><p><span data-ttu-id="ba048-552">десятичное число (5, 2)</span><span class="sxs-lookup"><span data-stu-id="ba048-552">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="ba048-553">Среднее отношение числа сжатых образцов, созданных функцией восстановления звука, к обычным образцам.</span><span class="sxs-lookup"><span data-stu-id="ba048-553">Average ratio of compressed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba048-554">Обработки</span><span class="sxs-lookup"><span data-stu-id="ba048-554">RoundTrip</span></span></p></td>
<td><p><span data-ttu-id="ba048-555">int</span><span class="sxs-lookup"><span data-stu-id="ba048-555">int</span></span></p></td>
<td><p><span data-ttu-id="ba048-556">Время приема-передачи на основе статистики RTCP.</span><span class="sxs-lookup"><span data-stu-id="ba048-556">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba048-557">раундтрипмакс</span><span class="sxs-lookup"><span data-stu-id="ba048-557">RoundTripMax</span></span></p></td>
<td><p><span data-ttu-id="ba048-558">int</span><span class="sxs-lookup"><span data-stu-id="ba048-558">int</span></span></p></td>
<td><p><span data-ttu-id="ba048-559">Максимальное время приема-передачи для аудиопотока.</span><span class="sxs-lookup"><span data-stu-id="ba048-559">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba048-560">овераллавгнетворкмос</span><span class="sxs-lookup"><span data-stu-id="ba048-560">OverallAvgNetworkMOS</span></span></p></td>
<td><p><span data-ttu-id="ba048-561">десятичное число (3, 2)</span><span class="sxs-lookup"><span data-stu-id="ba048-561">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="ba048-p145">Средняя экспертная оценка качества (MOS) в широкополосной сети для вызова. Значение этого показателя зависит от потерь пакетов, дрожания и используемого кодека. Диапазон — от 1,0 до 5,0.</span><span class="sxs-lookup"><span data-stu-id="ba048-p145">Average wideband Network MOS for the call. This metric depends on the packet loss, jitter, and codec used. Range is 1.0 to 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba048-565">овераллминнетворкмос</span><span class="sxs-lookup"><span data-stu-id="ba048-565">OverallMinNetworkMOS</span></span></p></td>
<td><p><span data-ttu-id="ba048-566">десятичное число (3, 2)</span><span class="sxs-lookup"><span data-stu-id="ba048-566">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="ba048-567">Минимальная экспертная оценка качества (MOS) в широкополосной сети для вызова.</span><span class="sxs-lookup"><span data-stu-id="ba048-567">Minimum wideband Network MOS for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba048-568">Значение sendlistenmos</span><span class="sxs-lookup"><span data-stu-id="ba048-568">SendListenMOS</span></span></p></td>
<td><p><span data-ttu-id="ba048-569">десятичное число (3, 2)</span><span class="sxs-lookup"><span data-stu-id="ba048-569">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="ba048-570">Средняя прогнозируемая экспертная оценка качества (MOS) при широкополосном прослушивании для отправленного аудиосигнала, включая характеристики уровня чувствительности микрофона, уровня помех и устройства захвата.</span><span class="sxs-lookup"><span data-stu-id="ba048-570">Average predicted wideband Listening MOS score for audio sent, including speech level, noise level and capture device characteristics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba048-571">сендлистенмосмин</span><span class="sxs-lookup"><span data-stu-id="ba048-571">SendListenMOSMin</span></span></p></td>
<td><p><span data-ttu-id="ba048-572">десятичное число (3, 2)</span><span class="sxs-lookup"><span data-stu-id="ba048-572">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="ba048-573">Минимальное значение SendListenMOS для вызова.</span><span class="sxs-lookup"><span data-stu-id="ba048-573">Minimum SendListenMOS for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba048-574">Значение recvlistenmos</span><span class="sxs-lookup"><span data-stu-id="ba048-574">RecvListenMOS</span></span></p></td>
<td><p><span data-ttu-id="ba048-575">десятичное число (3, 2)</span><span class="sxs-lookup"><span data-stu-id="ba048-575">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="ba048-576">Средняя прогнозируемая экспертная оценка качества (MOS) для аудиосигнала, полученного из сети, включая характеристики уровня чувствительности микрофона, уровня помех и устройства захвата.</span><span class="sxs-lookup"><span data-stu-id="ba048-576">Average predicted wideband Listening MOS score for audio received from the network including speech level, noise level, codec, network conditions and capture device characteristics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba048-577">реквлистенмосмин</span><span class="sxs-lookup"><span data-stu-id="ba048-577">RecvListenMOSMin</span></span></p></td>
<td><p><span data-ttu-id="ba048-578">десятичное число (3, 2)</span><span class="sxs-lookup"><span data-stu-id="ba048-578">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="ba048-579">Минимальное значение RecvListenMOS для вызова.</span><span class="sxs-lookup"><span data-stu-id="ba048-579">Minimum RecvListenMOS for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba048-580">аудиофекусед</span><span class="sxs-lookup"><span data-stu-id="ba048-580">AudioFECUsed</span></span></p></td>
<td><p><span data-ttu-id="ba048-581">Битовая</span><span class="sxs-lookup"><span data-stu-id="ba048-581">bit</span></span></p></td>
<td><p><span data-ttu-id="ba048-582">Указывает, применялась ли для этого вызова прямая коррекция аудиосигнала.</span><span class="sxs-lookup"><span data-stu-id="ba048-582">Indicates whether audio FEC was used for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba048-583">сендерискаллерпаи</span><span class="sxs-lookup"><span data-stu-id="ba048-583">SenderIsCallerPAI</span></span></p></td>
<td><p><span data-ttu-id="ba048-584">Битовая</span><span class="sxs-lookup"><span data-stu-id="ba048-584">bit</span></span></p></td>
<td><p><span data-ttu-id="ba048-585">Указывает направление передачи данных P-Asserted-Identity: 1 указывает направление потока от вызывающего абонента к вызываемому; 0 указывает направление потока от вызываемого абонента к вызывающему.</span><span class="sxs-lookup"><span data-stu-id="ba048-585">Indicates direction of the p-asserted identify information; 1 means the stream direction is from the caller to the callee; 0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

