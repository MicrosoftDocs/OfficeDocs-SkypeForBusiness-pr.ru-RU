---
title: 'Lync Server 2013: представление Аудиостреамдетаил'
description: 'Lync Server 2013: представление Аудиостреамдетаил.'
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
ms.openlocfilehash: 92c4c9bbb4f126e242e28d835222f6ba2af89d8b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573055"
---
# <a name="audiostreamdetail-view-in-lync-server-2013"></a><span data-ttu-id="61f36-103">Представление Аудиостреамдетаил в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61f36-103">AudioStreamDetail view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="61f36-104">_**Последнее изменение темы:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="61f36-104">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="61f36-105">В представлении AudioStreamDetail хранятся сведения о всех аудиопотоках в базе данных.</span><span class="sxs-lookup"><span data-stu-id="61f36-105">The AudioStreamDetail View stores information about each audio stream in the database.</span></span> <span data-ttu-id="61f36-106">Это представление было представлено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="61f36-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="61f36-107">Столбец</span><span class="sxs-lookup"><span data-stu-id="61f36-107">Column</span></span></th>
<th><span data-ttu-id="61f36-108">Тип данных</span><span class="sxs-lookup"><span data-stu-id="61f36-108">Data Type</span></span></th>
<th><span data-ttu-id="61f36-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="61f36-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="61f36-110">сессионтиме</span><span class="sxs-lookup"><span data-stu-id="61f36-110">SessionTime</span></span></p></td>
<td><p><span data-ttu-id="61f36-111">datetime</span><span class="sxs-lookup"><span data-stu-id="61f36-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="61f36-112">Ссылка из <a href="lync-server-2013-medialine-table.md">таблицы MediaLine в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="61f36-112">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61f36-113">сессионсек</span><span class="sxs-lookup"><span data-stu-id="61f36-113">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="61f36-114">int</span><span class="sxs-lookup"><span data-stu-id="61f36-114">int</span></span></p></td>
<td><p><span data-ttu-id="61f36-115">Ссылка из <a href="lync-server-2013-medialine-table.md">таблицы MediaLine в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="61f36-115">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61f36-116">стреамид</span><span class="sxs-lookup"><span data-stu-id="61f36-116">StreamId</span></span></p></td>
<td><p><span data-ttu-id="61f36-117">int</span><span class="sxs-lookup"><span data-stu-id="61f36-117">int</span></span></p></td>
<td><p><span data-ttu-id="61f36-118">Уникальный идентификатор в линии мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="61f36-118">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61f36-119">StartTime</span><span class="sxs-lookup"><span data-stu-id="61f36-119">StartTime</span></span></p></td>
<td><p><span data-ttu-id="61f36-120">datetime</span><span class="sxs-lookup"><span data-stu-id="61f36-120">datetime</span></span></p></td>
<td><p><span data-ttu-id="61f36-121">Время начала сеанса.</span><span class="sxs-lookup"><span data-stu-id="61f36-121">Start time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61f36-122">EndTime</span><span class="sxs-lookup"><span data-stu-id="61f36-122">EndTime</span></span></p></td>
<td><p><span data-ttu-id="61f36-123">datetime</span><span class="sxs-lookup"><span data-stu-id="61f36-123">datetime</span></span></p></td>
<td><p><span data-ttu-id="61f36-124">Время окончания сеанса.</span><span class="sxs-lookup"><span data-stu-id="61f36-124">End time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61f36-125">диалогкатегори</span><span class="sxs-lookup"><span data-stu-id="61f36-125">DialogCategory</span></span></p></td>
<td><p><span data-ttu-id="61f36-126">Битовая</span><span class="sxs-lookup"><span data-stu-id="61f36-126">bit</span></span></p></td>
<td><p><span data-ttu-id="61f36-127">Категория диалоговых окон: 0 — сервер Lync Server — это ветвь сервера-посредника; 1 — это сервер-посредник для шлюза PSTN.</span><span class="sxs-lookup"><span data-stu-id="61f36-127">Dialog category: 0 is the Lync Server to Mediation Server leg; 1 is the Mediation Server to PSTN gateway leg.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61f36-128">медиатионсервербипассфлаг</span><span class="sxs-lookup"><span data-stu-id="61f36-128">MediationServerBypassFlag</span></span></p></td>
<td><p><span data-ttu-id="61f36-129">Битовая</span><span class="sxs-lookup"><span data-stu-id="61f36-129">bit</span></span></p></td>
<td><p><span data-ttu-id="61f36-130">Флаг, указывающий, выполнял ли вызов обход сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="61f36-130">Flag indicating if the call was bypassed or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61f36-131">медиабипассварнингфлаг</span><span class="sxs-lookup"><span data-stu-id="61f36-131">MediaBypassWarningFlag</span></span></p></td>
<td><p><span data-ttu-id="61f36-132">int</span><span class="sxs-lookup"><span data-stu-id="61f36-132">int</span></span></p></td>
<td><p><span data-ttu-id="61f36-p102">Если это поле присутствует, оно указывает, почему вызов не выполнял обход сервера-посредника, даже если идентификаторы обхода соответствовали. Задается только одно значение:</span><span class="sxs-lookup"><span data-stu-id="61f36-p102">If present, indicates why a call was not bypassed even if the bypass IDs matched. Only one value is defined:</span></span></p>
<p><span data-ttu-id="61f36-135">0x0001 — неизвестный идентификатор обхода для сетевого адаптера по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="61f36-135">0x0001 – Unknown bypass ID for Default network adapter.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61f36-136">каллприорити</span><span class="sxs-lookup"><span data-stu-id="61f36-136">CallPriority</span></span></p></td>
<td><p><span data-ttu-id="61f36-137">int</span><span class="sxs-lookup"><span data-stu-id="61f36-137">int</span></span></p></td>
<td><p><span data-ttu-id="61f36-138">Приоритет вызова.</span><span class="sxs-lookup"><span data-stu-id="61f36-138">Priority of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61f36-139">каллерпул</span><span class="sxs-lookup"><span data-stu-id="61f36-139">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="61f36-140">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="61f36-140">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="61f36-141">Полное доменное имя пула вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="61f36-141">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61f36-142">каллипул</span><span class="sxs-lookup"><span data-stu-id="61f36-142">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="61f36-143">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="61f36-143">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="61f36-144">Полное доменное имя пула вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="61f36-144">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61f36-145">Вызывающая сторона</span><span class="sxs-lookup"><span data-stu-id="61f36-145">Caller</span></span></p></td>
<td><p><span data-ttu-id="61f36-146">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="61f36-146">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="61f36-147">URI вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="61f36-147">Caller’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61f36-148">Вызываемого абонента</span><span class="sxs-lookup"><span data-stu-id="61f36-148">Callee</span></span></p></td>
<td><p><span data-ttu-id="61f36-149">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="61f36-149">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="61f36-150">URI вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="61f36-150">Callee’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61f36-151">каллерусеражент</span><span class="sxs-lookup"><span data-stu-id="61f36-151">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="61f36-152">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="61f36-152">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="61f36-153">Строка агента пользователя вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="61f36-153">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61f36-154">каллерусераженттипе</span><span class="sxs-lookup"><span data-stu-id="61f36-154">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="61f36-155">smallint</span><span class="sxs-lookup"><span data-stu-id="61f36-155">smallint</span></span></p></td>
<td><p><span data-ttu-id="61f36-156">Тип агента пользователя вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="61f36-156">Type of the caller’s user agent.</span></span> <span data-ttu-id="61f36-157">Дополнительные сведения см. <a href="lync-server-2013-useragent-table.md">в таблице UserAgent в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="61f36-157">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61f36-158">каллерусераженткатегори</span><span class="sxs-lookup"><span data-stu-id="61f36-158">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="61f36-159">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="61f36-159">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="61f36-160">Категория агента пользователя вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="61f36-160">Category of the caller’s user agent.</span></span> <span data-ttu-id="61f36-161">Для получения подробных сведений ознакомьтесь со статьей <a href="lync-server-2013-useragentdef-table-qoe.md">таблица таблица useragentdef (QoE) в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="61f36-161">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61f36-162">каллиусеражент</span><span class="sxs-lookup"><span data-stu-id="61f36-162">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="61f36-163">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="61f36-163">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="61f36-164">Строка агента пользователя вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="61f36-164">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61f36-165">каллиусераженттипе</span><span class="sxs-lookup"><span data-stu-id="61f36-165">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="61f36-166">smallint</span><span class="sxs-lookup"><span data-stu-id="61f36-166">smallint</span></span></p></td>
<td><p><span data-ttu-id="61f36-167">Тип агента пользователя вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="61f36-167">Type of callee’s user agent.</span></span> <span data-ttu-id="61f36-168">Сведения о том, как просмотреть <a href="lync-server-2013-useragent-table.md">таблицу UserAgent в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="61f36-168">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61f36-169">каллиусераженткатегори</span><span class="sxs-lookup"><span data-stu-id="61f36-169">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="61f36-170">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="61f36-170">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="61f36-171">Категория агента пользователя вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="61f36-171">Category of callee’s user agent.</span></span> <span data-ttu-id="61f36-172">Для получения дополнительных сведений смотрите <a href="lync-server-2013-useragentdef-table-qoe.md">таблицу таблица useragentdef (QoE) в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="61f36-172">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61f36-173">каллерендпоинт</span><span class="sxs-lookup"><span data-stu-id="61f36-173">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="61f36-174">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="61f36-174">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="61f36-175">Имя конечной точки вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="61f36-175">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61f36-176">каллиендпоинт</span><span class="sxs-lookup"><span data-stu-id="61f36-176">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="61f36-177">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="61f36-177">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="61f36-178">Имя конечной точки вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="61f36-178">Callee’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61f36-179">каллерос</span><span class="sxs-lookup"><span data-stu-id="61f36-179">CallerOS</span></span></p></td>
<td><p><span data-ttu-id="61f36-180">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="61f36-180">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="61f36-181">Операционная система конечной точки вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="61f36-181">Operating system (OS) of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61f36-182">каллиос</span><span class="sxs-lookup"><span data-stu-id="61f36-182">CalleeOS</span></span></p></td>
<td><p><span data-ttu-id="61f36-183">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="61f36-183">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="61f36-184">Операционная система конечной точки вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="61f36-184">Operating system (OS) of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61f36-185">каллеркпунаме</span><span class="sxs-lookup"><span data-stu-id="61f36-185">CallerCPUName</span></span></p></td>
<td><p><span data-ttu-id="61f36-186">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="61f36-186">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="61f36-187">Название ЦП конечной точки вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="61f36-187">CPU name of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61f36-188">калликпунаме</span><span class="sxs-lookup"><span data-stu-id="61f36-188">CalleeCPUName</span></span></p></td>
<td><p><span data-ttu-id="61f36-189">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="61f36-189">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="61f36-190">Название ЦП конечной точки вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="61f36-190">CPU name of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61f36-191">каллеркпунумберофкорес</span><span class="sxs-lookup"><span data-stu-id="61f36-191">CallerCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="61f36-192">smallint</span><span class="sxs-lookup"><span data-stu-id="61f36-192">smallint</span></span></p></td>
<td><p><span data-ttu-id="61f36-193">Число ядер ЦП на конечной точке вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="61f36-193">Number of CPU cores in the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61f36-194">калликпунумберофкорес</span><span class="sxs-lookup"><span data-stu-id="61f36-194">CalleeCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="61f36-195">smallint</span><span class="sxs-lookup"><span data-stu-id="61f36-195">smallint</span></span></p></td>
<td><p><span data-ttu-id="61f36-196">Число ядер ЦП на конечной точке вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="61f36-196">Number of CPU cores in the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61f36-197">каллеркпупроцессорспид</span><span class="sxs-lookup"><span data-stu-id="61f36-197">CallerCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="61f36-198">int</span><span class="sxs-lookup"><span data-stu-id="61f36-198">int</span></span></p></td>
<td><p><span data-ttu-id="61f36-199">Скорость ЦП конечной точки вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="61f36-199">CPU processor speed of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61f36-200">калликпупроцессорспид</span><span class="sxs-lookup"><span data-stu-id="61f36-200">CalleeCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="61f36-201">int</span><span class="sxs-lookup"><span data-stu-id="61f36-201">int</span></span></p></td>
<td><p><span data-ttu-id="61f36-202">Скорость ЦП конечной точки вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="61f36-202">CPU processor speed of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61f36-203">каллервиртуализатионфлаг</span><span class="sxs-lookup"><span data-stu-id="61f36-203">CallerVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="61f36-204">tinyint</span><span class="sxs-lookup"><span data-stu-id="61f36-204">tinyint</span></span></p></td>
<td><p><span data-ttu-id="61f36-205">Указывает, работает ли система вызывающего абонента в виртуализованной среде.</span><span class="sxs-lookup"><span data-stu-id="61f36-205">Indicates whether the caller’s system is running in a virtualized environment.</span></span> <span data-ttu-id="61f36-206">Более подробную информацию можно узнать <a href="lync-server-2013-endpoint-table.md">в таблице конечная точка в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="61f36-206">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61f36-207">калливиртуализатионфлаг</span><span class="sxs-lookup"><span data-stu-id="61f36-207">CalleeVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="61f36-208">tinyint</span><span class="sxs-lookup"><span data-stu-id="61f36-208">tinyint</span></span></p></td>
<td><p><span data-ttu-id="61f36-209">Указывает, работает ли система вызываемого абонента в виртуализованной среде.</span><span class="sxs-lookup"><span data-stu-id="61f36-209">Indicates whether the callee’s system is running in a virtualized environment.</span></span> <span data-ttu-id="61f36-210">Более подробную информацию можно узнать <a href="lync-server-2013-endpoint-table.md">в таблице конечная точка в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="61f36-210">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61f36-211">коррелатионкэй</span><span class="sxs-lookup"><span data-stu-id="61f36-211">CorrelationKey</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="61f36-212">Ключ корреляции.</span><span class="sxs-lookup"><span data-stu-id="61f36-212">Correlation key.</span></span> <span data-ttu-id="61f36-213">Ссылка из <a href="lync-server-2013-sessioncorrelation-table.md">таблицы таблица sessioncorrelation в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="61f36-213">Referenced from the <a href="lync-server-2013-sessioncorrelation-table.md">SessionCorrelation table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61f36-214">коннективитице</span><span class="sxs-lookup"><span data-stu-id="61f36-214">ConnectivityIce</span></span></p></td>
<td><p><span data-ttu-id="61f36-215">tinyint</span><span class="sxs-lookup"><span data-stu-id="61f36-215">tinyint</span></span></p></td>
<td><p><span data-ttu-id="61f36-216">Сведения о канале передачи медиаданных, например прямой или ретранслируемый.</span><span class="sxs-lookup"><span data-stu-id="61f36-216">Information about the media path, such as direct or relayed.</span></span> <span data-ttu-id="61f36-217">Дополнительные сведения см. <a href="lync-server-2013-medialine-table.md">в таблице MediaLine в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="61f36-217">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61f36-218">каллерицеварнингфлагс</span><span class="sxs-lookup"><span data-stu-id="61f36-218">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="61f36-219">int</span><span class="sxs-lookup"><span data-stu-id="61f36-219">int</span></span></p></td>
<td><p><span data-ttu-id="61f36-p111">Сведения о технологии ICE (Interactive Connectivity Establishment), описанные в битовых флагах, для вызывающего абонента. Дополнительные сведения см. в спецификации протокола сервера мониторинга качества взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="61f36-p111">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61f36-222">каллиицеварнингфлагс</span><span class="sxs-lookup"><span data-stu-id="61f36-222">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="61f36-223">int</span><span class="sxs-lookup"><span data-stu-id="61f36-223">int</span></span></p></td>
<td><p><span data-ttu-id="61f36-p112">Сведения о технологии ICE (Interactive Connectivity Establishment), описанные в битовых флагах, для вызываемого абонента. Дополнительные сведения см. в спецификации протокола сервера мониторинга качества взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="61f36-p112">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61f36-226">Transport</span><span class="sxs-lookup"><span data-stu-id="61f36-226">Transport</span></span></p></td>
<td><p><span data-ttu-id="61f36-227">tinyint</span><span class="sxs-lookup"><span data-stu-id="61f36-227">tinyint</span></span></p></td>
<td><p><span data-ttu-id="61f36-228">Тип транспорта: 0 — UDP, 1 — TCP.</span><span class="sxs-lookup"><span data-stu-id="61f36-228">Transport type: 0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61f36-229">каллерипаддр</span><span class="sxs-lookup"><span data-stu-id="61f36-229">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="61f36-230">var (50)</span><span class="sxs-lookup"><span data-stu-id="61f36-230">var(50)</span></span></p></td>
<td><p><span data-ttu-id="61f36-231">IP-адрес вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="61f36-231">IP address of the caller.</span></span> <span data-ttu-id="61f36-232">Это может быть IPv4-адрес или IPv6-адрес.</span><span class="sxs-lookup"><span data-stu-id="61f36-232">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61f36-233">каллерпорт</span><span class="sxs-lookup"><span data-stu-id="61f36-233">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="61f36-234">int</span><span class="sxs-lookup"><span data-stu-id="61f36-234">int</span></span></p></td>
<td><p><span data-ttu-id="61f36-235">Порт, используемый вызывающим абонентом.</span><span class="sxs-lookup"><span data-stu-id="61f36-235">Port used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61f36-236">каллеринсиде</span><span class="sxs-lookup"><span data-stu-id="61f36-236">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="61f36-237">Битовая</span><span class="sxs-lookup"><span data-stu-id="61f36-237">bit</span></span></p></td>
<td><p><span data-ttu-id="61f36-238">Указывает, находится ли вызывающий абонент во внутренней сети: 1 означает, что вызывающий абонент находится внутри корпоративной сети, 0 означает, что вызывающий абонент находится вне сети.</span><span class="sxs-lookup"><span data-stu-id="61f36-238">Indicates whether the caller is inside the interval network: 1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61f36-239">каллиипаддр</span><span class="sxs-lookup"><span data-stu-id="61f36-239">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="61f36-240">var (50)</span><span class="sxs-lookup"><span data-stu-id="61f36-240">var(50)</span></span></p></td>
<td><p><span data-ttu-id="61f36-241">IP-адрес вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="61f36-241">IP address of the callee.</span></span> <span data-ttu-id="61f36-242">Это может быть IPv4-адрес или IPv6-адрес.</span><span class="sxs-lookup"><span data-stu-id="61f36-242">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61f36-243">каллипорт</span><span class="sxs-lookup"><span data-stu-id="61f36-243">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="61f36-244">int</span><span class="sxs-lookup"><span data-stu-id="61f36-244">int</span></span></p></td>
<td><p><span data-ttu-id="61f36-245">Порт, используемый вызываемым абонентом.</span><span class="sxs-lookup"><span data-stu-id="61f36-245">Port used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61f36-246">каллиинсиде</span><span class="sxs-lookup"><span data-stu-id="61f36-246">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="61f36-247">Битовая</span><span class="sxs-lookup"><span data-stu-id="61f36-247">bit</span></span></p></td>
<td><p><span data-ttu-id="61f36-248">Указывает, находится ли вызываемый абонент во внутренней сети: 1 означает, что вызываемый абонент находится внутри корпоративной сети, 0 означает, что вызываемый абонент находится вне сети.</span><span class="sxs-lookup"><span data-stu-id="61f36-248">Indicates whether the callee is inside the interval network: 1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61f36-249">каллерусерсите</span><span class="sxs-lookup"><span data-stu-id="61f36-249">CallerUserSite</span></span></p></td>
<td><p><span data-ttu-id="61f36-250">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="61f36-250">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="61f36-251">Имя сайта вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="61f36-251">Name of the caller’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61f36-252">каллеррегион</span><span class="sxs-lookup"><span data-stu-id="61f36-252">CallerRegion</span></span></p></td>
<td><p><span data-ttu-id="61f36-253">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="61f36-253">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="61f36-254">Название страны или региона, где находится сайт вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="61f36-254">Name of the country/region of the caller’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61f36-255">каллиусерсите</span><span class="sxs-lookup"><span data-stu-id="61f36-255">CalleeUserSite</span></span></p></td>
<td><p><span data-ttu-id="61f36-256">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="61f36-256">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="61f36-257">Имя сайта вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="61f36-257">Name of the callee’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61f36-258">каллирегион</span><span class="sxs-lookup"><span data-stu-id="61f36-258">CalleeRegion</span></span></p></td>
<td><p><span data-ttu-id="61f36-259">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="61f36-259">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="61f36-260">Название страны или региона, где находится сайт вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="61f36-260">Name of the country/region of the callee’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61f36-261">каллеррелайипаддр</span><span class="sxs-lookup"><span data-stu-id="61f36-261">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="61f36-262">var (50)</span><span class="sxs-lookup"><span data-stu-id="61f36-262">var(50)</span></span></p></td>
<td><p><span data-ttu-id="61f36-263">IP-адрес пограничной службы обработки аудио- и видеоданных, используемой вызывающим абонентом.</span><span class="sxs-lookup"><span data-stu-id="61f36-263">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="61f36-264">Дополнительные сведения см. <a href="lync-server-2013-ipaddress-table.md">в таблице IPAddress в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="61f36-264">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61f36-265">каллеррелайпорт</span><span class="sxs-lookup"><span data-stu-id="61f36-265">CallerRelayPort</span></span></p></td>
<td><p><span data-ttu-id="61f36-266">int</span><span class="sxs-lookup"><span data-stu-id="61f36-266">int</span></span></p></td>
<td><p><span data-ttu-id="61f36-267">Порт, используемый вызывающим абонентом в пограничной службе обработки аудио- и видеоданных.</span><span class="sxs-lookup"><span data-stu-id="61f36-267">Port used on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61f36-268">каллирелайипаддр</span><span class="sxs-lookup"><span data-stu-id="61f36-268">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="61f36-269">var (50)</span><span class="sxs-lookup"><span data-stu-id="61f36-269">var(50)</span></span></p></td>
<td><p><span data-ttu-id="61f36-270">IP-адрес пограничной службы обработки аудио- и видеоданных, используемой вызываемым абонентом.</span><span class="sxs-lookup"><span data-stu-id="61f36-270">IP Address key of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="61f36-271">Дополнительные сведения см. <a href="lync-server-2013-ipaddress-table.md">в таблице IPAddress в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="61f36-271">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61f36-272">каллирелайпорт</span><span class="sxs-lookup"><span data-stu-id="61f36-272">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="61f36-273">int</span><span class="sxs-lookup"><span data-stu-id="61f36-273">int</span></span></p></td>
<td><p><span data-ttu-id="61f36-274">Порт, используемый вызываемым абонентом в пограничной службе обработки аудио- и видеоданных.</span><span class="sxs-lookup"><span data-stu-id="61f36-274">Port used on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61f36-275">каллеркаптуредев</span><span class="sxs-lookup"><span data-stu-id="61f36-275">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="61f36-276">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="61f36-276">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="61f36-277">Имя устройства захвата вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="61f36-277">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61f36-278">каллеррендердев</span><span class="sxs-lookup"><span data-stu-id="61f36-278">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="61f36-279">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="61f36-279">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="61f36-280">Имя устройства обработки вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="61f36-280">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61f36-281">каллеркаптуредевдривер</span><span class="sxs-lookup"><span data-stu-id="61f36-281">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="61f36-282">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="61f36-282">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="61f36-283">Имя драйвера для устройства захвата вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="61f36-283">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61f36-284">каллеррендердривер</span><span class="sxs-lookup"><span data-stu-id="61f36-284">CallerRenderDriver</span></span></p></td>
<td><p><span data-ttu-id="61f36-285">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="61f36-285">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="61f36-286">Имя драйвера для устройства обработки вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="61f36-286">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61f36-287">калликаптуредев</span><span class="sxs-lookup"><span data-stu-id="61f36-287">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="61f36-288">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="61f36-288">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="61f36-289">Имя устройства захвата вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="61f36-289">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61f36-290">каллирендердев</span><span class="sxs-lookup"><span data-stu-id="61f36-290">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="61f36-291">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="61f36-291">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="61f36-292">Имя устройства обработки вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="61f36-292">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61f36-293">калликаптуредевдривер</span><span class="sxs-lookup"><span data-stu-id="61f36-293">CalleeCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="61f36-294">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="61f36-294">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="61f36-295">Имя драйвера для устройства захвата вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="61f36-295">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61f36-296">каллирендердевдривер</span><span class="sxs-lookup"><span data-stu-id="61f36-296">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="61f36-297">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="61f36-297">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="61f36-298">Имя драйвера для устройства обработки вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="61f36-298">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61f36-299">каллернетворкконнектионтипе</span><span class="sxs-lookup"><span data-stu-id="61f36-299">CallerNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="61f36-300">tinyint</span><span class="sxs-lookup"><span data-stu-id="61f36-300">tinyint</span></span></p></td>
<td><p><span data-ttu-id="61f36-301">Тип подключения к сети вызывающего абонента: 0 — проводной, 1 — беспроводной.</span><span class="sxs-lookup"><span data-stu-id="61f36-301">Caller’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61f36-302">каллервпн</span><span class="sxs-lookup"><span data-stu-id="61f36-302">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="61f36-303">Битовая</span><span class="sxs-lookup"><span data-stu-id="61f36-303">bit</span></span></p></td>
<td><p><span data-ttu-id="61f36-304">Указывает, подключен ли вызывающий абонент через виртуальную частную сеть: 1 — да, 0 — нет.</span><span class="sxs-lookup"><span data-stu-id="61f36-304">Indicates whether the caller connected over a virtual private network: 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61f36-305">каллерлинкспид</span><span class="sxs-lookup"><span data-stu-id="61f36-305">CallerLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="61f36-306">десятичное число (18, 0)</span><span class="sxs-lookup"><span data-stu-id="61f36-306">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="61f36-307">Скорость сетевого соединения в бит/с для конечной точки вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="61f36-307">Network link speed for the caller's endpoint in bps.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61f36-308">каллинетворкконнектионтипе</span><span class="sxs-lookup"><span data-stu-id="61f36-308">CalleeNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="61f36-309">tinyint</span><span class="sxs-lookup"><span data-stu-id="61f36-309">tinyint</span></span></p></td>
<td><p><span data-ttu-id="61f36-310">Тип подключения к сети вызываемого абонента: 0 — проводной, 1 — беспроводной.</span><span class="sxs-lookup"><span data-stu-id="61f36-310">Callee’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61f36-311">калливпн</span><span class="sxs-lookup"><span data-stu-id="61f36-311">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="61f36-312">Битовая</span><span class="sxs-lookup"><span data-stu-id="61f36-312">bit</span></span></p></td>
<td><p><span data-ttu-id="61f36-313">Указывает, подключен ли вызываемый абонент через виртуальную частную сеть: 1 — да, 0 — нет.</span><span class="sxs-lookup"><span data-stu-id="61f36-313">Indicates whether the caller connected over a virtual private network: 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61f36-314">каллилинкспид</span><span class="sxs-lookup"><span data-stu-id="61f36-314">CalleeLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="61f36-315">десятичное число (18, 0)</span><span class="sxs-lookup"><span data-stu-id="61f36-315">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="61f36-316">Скорость сетевого соединения в бит/с для конечной точки вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="61f36-316">Network link speed for the callee's endpoint in bps.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61f36-317">конверсатионалмос</span><span class="sxs-lookup"><span data-stu-id="61f36-317">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="61f36-318">десятичное число (3, 2)</span><span class="sxs-lookup"><span data-stu-id="61f36-318">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="61f36-319">Узкополосный MOS аудиосеансов (на основе обоих аудиопотоков).</span><span class="sxs-lookup"><span data-stu-id="61f36-319">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61f36-320">апплиедбандвидслимит</span><span class="sxs-lookup"><span data-stu-id="61f36-320">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="61f36-321">int</span><span class="sxs-lookup"><span data-stu-id="61f36-321">int</span></span></p></td>
<td><p><span data-ttu-id="61f36-p117">Фактическая пропускная способность, доступная указанному потоку с учетом заданных параметров политики (TURN, API, SDP, сервер политики и т. д.). Это значение не следует путать с эффективной пропускной способностью, так как эффективная пропускная способность может оказаться ниже на основе оценки полосы пропускания. Это, по сути, максимальная пропускная способность отправляемого потока с учетом ограничений, наложенных оценкой полосы пропускания.</span><span class="sxs-lookup"><span data-stu-id="61f36-p117">Actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on). This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate. This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61f36-325">життеринтерарривал</span><span class="sxs-lookup"><span data-stu-id="61f36-325">JitterInterArrival</span></span></p></td>
<td><p><span data-ttu-id="61f36-326">int</span><span class="sxs-lookup"><span data-stu-id="61f36-326">int</span></span></p></td>
<td><p><span data-ttu-id="61f36-327">Средний уровень дрожания в сети на основе статистики протокола RTCP.</span><span class="sxs-lookup"><span data-stu-id="61f36-327">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61f36-328">життеринтерарривалмакс</span><span class="sxs-lookup"><span data-stu-id="61f36-328">JitterInterArrivalMax</span></span></p></td>
<td><p><span data-ttu-id="61f36-329">int</span><span class="sxs-lookup"><span data-stu-id="61f36-329">int</span></span></p></td>
<td><p><span data-ttu-id="61f36-330">Максимальный уровень дрожания в сети в течение вызова.</span><span class="sxs-lookup"><span data-stu-id="61f36-330">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61f36-331">паккетлоссрате</span><span class="sxs-lookup"><span data-stu-id="61f36-331">PacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="61f36-332">десятичное число (5, 4)</span><span class="sxs-lookup"><span data-stu-id="61f36-332">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="61f36-333">Средний коэффициент потерь пакетов в течение вызова.</span><span class="sxs-lookup"><span data-stu-id="61f36-333">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61f36-334">паккетлоссратемакс</span><span class="sxs-lookup"><span data-stu-id="61f36-334">PacketLossRateMax</span></span></p></td>
<td><p><span data-ttu-id="61f36-335">десятичное число (5, 4)</span><span class="sxs-lookup"><span data-stu-id="61f36-335">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="61f36-336">Максимальная потеря пакетов, наблюдавшаяся в течение вызова.</span><span class="sxs-lookup"><span data-stu-id="61f36-336">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61f36-337">бурстденсити</span><span class="sxs-lookup"><span data-stu-id="61f36-337">BurstDensity</span></span></p></td>
<td><p><span data-ttu-id="61f36-338">десятичное число (9, 4)</span><span class="sxs-lookup"><span data-stu-id="61f36-338">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="61f36-339">Средняя плотность потерь пакетов во время пиков потерь в течение вызова.</span><span class="sxs-lookup"><span data-stu-id="61f36-339">Average density of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61f36-340">бурстдуратион</span><span class="sxs-lookup"><span data-stu-id="61f36-340">BurstDuration</span></span></p></td>
<td><p><span data-ttu-id="61f36-341">int</span><span class="sxs-lookup"><span data-stu-id="61f36-341">int</span></span></p></td>
<td><p><span data-ttu-id="61f36-342">Средняя продолжительность потерь пакетов во время пиков потерь в течение вызова.</span><span class="sxs-lookup"><span data-stu-id="61f36-342">Average duration of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61f36-343">бурстгапденсити</span><span class="sxs-lookup"><span data-stu-id="61f36-343">BurstGapDensity</span></span></p></td>
<td><p><span data-ttu-id="61f36-344">десятичное число (9, 4)</span><span class="sxs-lookup"><span data-stu-id="61f36-344">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="61f36-345">Средняя плотность потерь пакетов в промежутках между пиками потерь.</span><span class="sxs-lookup"><span data-stu-id="61f36-345">Average density of packet loss during gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61f36-346">бурстгапдуратион</span><span class="sxs-lookup"><span data-stu-id="61f36-346">BurstGapDuration</span></span></p></td>
<td><p><span data-ttu-id="61f36-347">int</span><span class="sxs-lookup"><span data-stu-id="61f36-347">int</span></span></p></td>
<td><p><span data-ttu-id="61f36-348">Средняя продолжительность промежутков между пиками потерь пакетов.</span><span class="sxs-lookup"><span data-stu-id="61f36-348">Average duration of gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61f36-349">паккетутилизатион</span><span class="sxs-lookup"><span data-stu-id="61f36-349">PacketUtilization</span></span></p></td>
<td><p><span data-ttu-id="61f36-350">int</span><span class="sxs-lookup"><span data-stu-id="61f36-350">int</span></span></p></td>
<td><p><span data-ttu-id="61f36-351">Количество пакетов для аудиопотока.</span><span class="sxs-lookup"><span data-stu-id="61f36-351">Packet count for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61f36-352">Самый полоса пропускания</span><span class="sxs-lookup"><span data-stu-id="61f36-352">BandwidthEst</span></span></p></td>
<td><p><span data-ttu-id="61f36-353">int</span><span class="sxs-lookup"><span data-stu-id="61f36-353">int</span></span></p></td>
<td><p><span data-ttu-id="61f36-354">Оценка пропускной способности для аудиопотока.</span><span class="sxs-lookup"><span data-stu-id="61f36-354">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61f36-355">деградатионавг</span><span class="sxs-lookup"><span data-stu-id="61f36-355">DegradationAvg</span></span></p></td>
<td><p><span data-ttu-id="61f36-356">десятичное число (3, 2)</span><span class="sxs-lookup"><span data-stu-id="61f36-356">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="61f36-p118">Снижение экспертной оценки качества (MOS) в сети для всего звонка в диапазоне от 0,0 до 5,0. Эта метрика показывает величину уменьшения MOS в сети, обусловленную дрожанием и потерей пакетов. Для приемлемого качества это значение должно быть меньше, чем 0,5.</span><span class="sxs-lookup"><span data-stu-id="61f36-p118">Network MOS Degradation for the whole call. Range is 0.0 to 5.0. This metric shows the amount the Network MOS was reduced because of jitter and packet loss. For acceptable quality it should less than 0.5.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61f36-361">деградатионмакс</span><span class="sxs-lookup"><span data-stu-id="61f36-361">DegradationMax</span></span></p></td>
<td><p><span data-ttu-id="61f36-362">десятичное число (3, 2)</span><span class="sxs-lookup"><span data-stu-id="61f36-362">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="61f36-363">Максимальное снижение экспертной оценки качества (MOS) в сети во время звонка.</span><span class="sxs-lookup"><span data-stu-id="61f36-363">Maximum Network MOS degradation during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61f36-364">деградатионжиттеравг</span><span class="sxs-lookup"><span data-stu-id="61f36-364">DegradationJitterAvg</span></span></p></td>
<td><p><span data-ttu-id="61f36-365">десятичное число (3, 2)</span><span class="sxs-lookup"><span data-stu-id="61f36-365">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="61f36-366">Снижение экспертной оценки качества (MOS) в сети, вызванное дрожанием.</span><span class="sxs-lookup"><span data-stu-id="61f36-366">Network MOS degradation caused by jitter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61f36-367">деградатионпаккетлоссавг</span><span class="sxs-lookup"><span data-stu-id="61f36-367">DegradationPacketLossAvg</span></span></p></td>
<td><p><span data-ttu-id="61f36-368">десятичное число (3, 2)</span><span class="sxs-lookup"><span data-stu-id="61f36-368">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="61f36-369">Снижение экспертной оценки качества (MOS) в сети, вызванное потерей пакетов.</span><span class="sxs-lookup"><span data-stu-id="61f36-369">Network MOS degradation caused by packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61f36-370">PayloadDescription</span><span class="sxs-lookup"><span data-stu-id="61f36-370">PayloadDescription</span></span></p></td>
<td><p><span data-ttu-id="61f36-371">int</span><span class="sxs-lookup"><span data-stu-id="61f36-371">int</span></span></p></td>
<td><p><span data-ttu-id="61f36-372">Аудиокодек, используемый для вызова, на который ссылается <a href="lync-server-2013-payloaddescription-table.md">таблица таблица payloaddescription в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="61f36-372">The audio codec used for the call, referenced from the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61f36-373">аудиосамплерате</span><span class="sxs-lookup"><span data-stu-id="61f36-373">AudioSampleRate</span></span></p></td>
<td><p><span data-ttu-id="61f36-374">int</span><span class="sxs-lookup"><span data-stu-id="61f36-374">int</span></span></p></td>
<td><p><span data-ttu-id="61f36-375">Частота выборки для аудиопотока.</span><span class="sxs-lookup"><span data-stu-id="61f36-375">Sampling rate for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61f36-376">каллерсендсигналлевел</span><span class="sxs-lookup"><span data-stu-id="61f36-376">CallerSendSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="61f36-377">int</span><span class="sxs-lookup"><span data-stu-id="61f36-377">int</span></span></p></td>
<td><p><span data-ttu-id="61f36-p119">Послеаналоговая регулировка уровня звукового сигнала для аудиопотока, отправленного вызывающим абонентом. Единица измерения для этого показателя — дБмо. Для приемлемого качества значение должно быть не менее 30 дБмо. Этот показатель не сообщается сервером аудио- и видеоконференций и IP-телефонами.</span><span class="sxs-lookup"><span data-stu-id="61f36-p119">Post-Analog Gain Control audio signal level for the audio the caller sent. The unit for this metric is dBmo. For acceptable quality, it should be at least 30 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61f36-382">каллерреквсигналлевел</span><span class="sxs-lookup"><span data-stu-id="61f36-382">CallerRecvSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="61f36-383">int</span><span class="sxs-lookup"><span data-stu-id="61f36-383">int</span></span></p></td>
<td><p><span data-ttu-id="61f36-p120">Уровень звукового сигнала для аудиопотока, принятого вызывающим абонентом. Единица измерения для этого показателя — дБмо. Для приемлемого качества значение должно быть не менее 30 дБмо. Этот показатель не сообщается сервером аудио- и видеоконференций и IP-телефонами.</span><span class="sxs-lookup"><span data-stu-id="61f36-p120">Audio signal level for the audio the caller received. The unit for this metric is dBmo. For acceptable quality, it should be at least 30 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61f36-388">каллерсендноиселевел</span><span class="sxs-lookup"><span data-stu-id="61f36-388">CallerSendNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="61f36-389">int</span><span class="sxs-lookup"><span data-stu-id="61f36-389">int</span></span></p></td>
<td><p><span data-ttu-id="61f36-p121">Послеаналоговая регулировка уровня акустического шума для аудиопотока, отправленного вызывающим абонентом. Единица измерения для этого показателя — дБмо. Для приемлемого качества значение должно быть менее 35 дБмо. Этот показатель не сообщается сервером аудио- и видеоконференций и IP-телефонами.</span><span class="sxs-lookup"><span data-stu-id="61f36-p121">Post-Analog Gain Control audio noise level for the audio the caller sent. The unit for this metric is dBmo. For acceptable quality, it should be less than 35 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61f36-394">каллерреквноиселевел</span><span class="sxs-lookup"><span data-stu-id="61f36-394">CallerRecvNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="61f36-395">int</span><span class="sxs-lookup"><span data-stu-id="61f36-395">int</span></span></p></td>
<td><p><span data-ttu-id="61f36-p122">Послеаналоговая регулировка уровня акустического шума для аудиопотока, полученного вызывающим абонентом. Единица измерения для этого показателя — дБмо. Для приемлемого качества значение должно быть менее 35 дБмо. Этот показатель не сообщается сервером аудио- и видеоконференций и IP-телефонами.</span><span class="sxs-lookup"><span data-stu-id="61f36-p122">Post-Analog Gain Control audio noise level for the audio the caller received. The unit for this metric is dBmo. For acceptable quality, it should be less than 35 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61f36-400">каллеречоретурн</span><span class="sxs-lookup"><span data-stu-id="61f36-400">CallerEchoReturn</span></span></p></td>
<td><p><span data-ttu-id="61f36-401">int</span><span class="sxs-lookup"><span data-stu-id="61f36-401">int</span></span></p></td>
<td><p><span data-ttu-id="61f36-p123">Отношение мощностей некомпенсированного и скомпенсированного эхосигнала для вызывающего абонента. Единица измерения для этого показателя — дБ. Чем ниже значение, тем меньше эхосигнал. Этот показатель не сообщается сервером аудио- и видеоконференций и IP-телефонами.</span><span class="sxs-lookup"><span data-stu-id="61f36-p123">Echo Return Loss Enhancement for the caller. The unit for this metric is dB. Lower values represent less echo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61f36-406">каллерспеакерглитчрате</span><span class="sxs-lookup"><span data-stu-id="61f36-406">CallerSpeakerGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="61f36-407">int</span><span class="sxs-lookup"><span data-stu-id="61f36-407">int</span></span></p></td>
<td><p><span data-ttu-id="61f36-p124">Среднее количество временных сбоев за пять минут при воспроизведении акустическими системами вызывающего абонента. Для хорошего качества должно быть не более одного сбоя в пять минут. Этот показатель не сообщается серверами аудио- и видеоконференций, серверами-посредниками и IP-телефонами.</span><span class="sxs-lookup"><span data-stu-id="61f36-p124">Average glitches per five minutes for the caller’s loudspeaker rendering. For good quality, this should be less than one per five minutes. Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61f36-411">каллермикглитчрате</span><span class="sxs-lookup"><span data-stu-id="61f36-411">CallerMicGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="61f36-412">int</span><span class="sxs-lookup"><span data-stu-id="61f36-412">int</span></span></p></td>
<td><p><span data-ttu-id="61f36-p125">Среднее количество временных сбоев за пять минут при захвате звука микрофоном вызывающего абонента. Для хорошего качества должно быть не более одного сбоя в пять минут. Этот показатель не сообщается серверами аудио- и видеоконференций, серверами-посредниками и IP-телефонами.</span><span class="sxs-lookup"><span data-stu-id="61f36-p125">Average glitches per five minutes for the caller’s microphone capture. For good quality this should be less than one per five minutes. Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61f36-416">каллертиместампдрифтратемик</span><span class="sxs-lookup"><span data-stu-id="61f36-416">CallerTimestampDriftRateMic</span></span></p></td>
<td><p><span data-ttu-id="61f36-417">десятичное число (9, 2)</span><span class="sxs-lookup"><span data-stu-id="61f36-417">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="61f36-418">Скорость рассинхронизации часов микрофона вызывающего абонента относительно часов процессора.</span><span class="sxs-lookup"><span data-stu-id="61f36-418">Caller’s microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61f36-419">каллертиместампдрифтратеспк</span><span class="sxs-lookup"><span data-stu-id="61f36-419">CallerTimestampDriftRateSpk</span></span></p></td>
<td><p><span data-ttu-id="61f36-420">десятичное число (9, 2)</span><span class="sxs-lookup"><span data-stu-id="61f36-420">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="61f36-421">Скорость рассинхронизации часов динамика вызывающего абонента относительно часов процессора.</span><span class="sxs-lookup"><span data-stu-id="61f36-421">Caller’s speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61f36-422">каллертиместамперрормикмс</span><span class="sxs-lookup"><span data-stu-id="61f36-422">CallerTimestampErrorMicMs</span></span></p></td>
<td><p><span data-ttu-id="61f36-423">десятичное число (9, 2)</span><span class="sxs-lookup"><span data-stu-id="61f36-423">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="61f36-424">Средняя ошибка метки времени для потока захвата микрофоном, в миллисекундах, в последние 20 секунд вызова.</span><span class="sxs-lookup"><span data-stu-id="61f36-424">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61f36-425">каллертиместамперрорспкмс</span><span class="sxs-lookup"><span data-stu-id="61f36-425">CallerTimestampErrorSpkMs</span></span></p></td>
<td><p><span data-ttu-id="61f36-426">десятичное число (9, 2)</span><span class="sxs-lookup"><span data-stu-id="61f36-426">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="61f36-427">Средняя ошибка метки времени для потока воспроизведения динамиком вызывающего абонента, в миллисекундах, в последние 20 секунд вызова.</span><span class="sxs-lookup"><span data-stu-id="61f36-427">Average of the caller’s speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61f36-428">каллервсентрикаусес</span><span class="sxs-lookup"><span data-stu-id="61f36-428">CallerVsEntryCauses</span></span></p></td>
<td><p><span data-ttu-id="61f36-429">smallint</span><span class="sxs-lookup"><span data-stu-id="61f36-429">smallint</span></span></p></td>
<td><p><span data-ttu-id="61f36-430">Речевой коммутатор — это полудуплексный режим с уменьшенной возможностью прерывания.</span><span class="sxs-lookup"><span data-stu-id="61f36-430">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="61f36-431">Дополнительные сведения см. <a href="lync-server-2013-medialine-table.md">в таблице MediaLine в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="61f36-431">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61f36-432">каллеречоевенткаусес</span><span class="sxs-lookup"><span data-stu-id="61f36-432">CallerEchoEventCauses</span></span></p></td>
<td><p><span data-ttu-id="61f36-433">tinyint</span><span class="sxs-lookup"><span data-stu-id="61f36-433">tinyint</span></span></p></td>
<td><p><span data-ttu-id="61f36-434">Причины события эхосигнала для вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="61f36-434">Causes of an echo event for the caller.</span></span> <span data-ttu-id="61f36-435">Дополнительные сведения см. <a href="lync-server-2013-medialine-table.md">в таблице MediaLine в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="61f36-435">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61f36-436">каллеречоперцентмиЦин</span><span class="sxs-lookup"><span data-stu-id="61f36-436">CallerEchoPercentMicIn</span></span></p></td>
<td><p><span data-ttu-id="61f36-437">десятичное число (5, 2)</span><span class="sxs-lookup"><span data-stu-id="61f36-437">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="61f36-p128">Процент времени, когда в потоке захвата микрофоном вызывающего абонента обнаруживается эхосигнал. Если используется гарнитура, то значение должно быть низким.</span><span class="sxs-lookup"><span data-stu-id="61f36-p128">Percentage of time when echo is detected in the caller’s microphone capture stream. If headset is used, the value should be low.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61f36-440">каллеречоперцентсенд</span><span class="sxs-lookup"><span data-stu-id="61f36-440">CallerEchoPercentSend</span></span></p></td>
<td><p><span data-ttu-id="61f36-441">десятичное число (5, 2)</span><span class="sxs-lookup"><span data-stu-id="61f36-441">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="61f36-p129">Процент времени, когда в потоке, отправленном вызывающим абонентом, обнаруживается эхосигнал. Высокое значение в отправленных потоках указывает на утечку эхосигнала.</span><span class="sxs-lookup"><span data-stu-id="61f36-p129">Percentage of time when echo is detected in the caller’s sent stream. High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61f36-444">каллеррксагксигналлевел</span><span class="sxs-lookup"><span data-stu-id="61f36-444">CallerRxAGCSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="61f36-445">int</span><span class="sxs-lookup"><span data-stu-id="61f36-445">int</span></span></p></td>
<td><p><span data-ttu-id="61f36-p130">Уровень сигнала, полученный на сервере-посреднике от шлюза, для аудиопотока вызывающего абонента; этот показатель относится только к серверу-посреднику. Единица измерения — dBoV. Приемлемый диапазон для хорошего качества — от -30 до -18 dBoV.</span><span class="sxs-lookup"><span data-stu-id="61f36-p130">Received signal level on the Mediation Server from the Gateway for the caller’s audio; this applies only to the Mediation Server. The unit of this metric is dBoV. For good quality, the acceptable range should be -30 to -18 dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61f36-449">каллеррксагкноиселевел</span><span class="sxs-lookup"><span data-stu-id="61f36-449">CallerRxAGCNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="61f36-450">int</span><span class="sxs-lookup"><span data-stu-id="61f36-450">int</span></span></p></td>
<td><p><span data-ttu-id="61f36-p131">Уровень акустического шума, полученный на сервере-посреднике от шлюза, для аудиопотока вызывающего абонента. Этот показатель относится только к серверу-посреднику. Единица измерения — dBoV. Приемлемый диапазон для хорошего качества — ниже -50 dBoV.</span><span class="sxs-lookup"><span data-stu-id="61f36-p131">Received signal level on the Mediation Server from the Gateway for the caller’s audio. This applies only to the Mediation Server. The unit of this metric is dBoV. For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61f36-455">каллеррксагкгаин</span><span class="sxs-lookup"><span data-stu-id="61f36-455">CallerRxAGCGain</span></span></p></td>
<td><p><span data-ttu-id="61f36-456">int</span><span class="sxs-lookup"><span data-stu-id="61f36-456">int</span></span></p></td>
<td><p><span data-ttu-id="61f36-457">Автоматическая регулировка усиления на стороне сервера-посредника, применяемая к аудиопотоку вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="61f36-457">Automatic gain control (AGC) on the Mediation Server side applied to the caller’s audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61f36-458">каллеринитиалсигналлевелрмс</span><span class="sxs-lookup"><span data-stu-id="61f36-458">CallerInitialSignalLevelRMS</span></span></p></td>
<td><p><span data-ttu-id="61f36-459">float</span><span class="sxs-lookup"><span data-stu-id="61f36-459">float</span></span></p></td>
<td><p><span data-ttu-id="61f36-460">Среднеквадратическое отклонение входящего сигнала вызывающего абонента до 30 первых секунд вызова.</span><span class="sxs-lookup"><span data-stu-id="61f36-460">Root mean square (RMS) of the incoming signal to the caller for up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61f36-461">каллисендсигналлевел</span><span class="sxs-lookup"><span data-stu-id="61f36-461">CalleeSendSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="61f36-462">int</span><span class="sxs-lookup"><span data-stu-id="61f36-462">int</span></span></p></td>
<td><p><span data-ttu-id="61f36-p132">Послеаналоговая регулировка уровня звукового сигнала для аудиопотока, отправленного вызываемым абонентом. Единица измерения для этого показателя — дБмо. Для приемлемого качества значение должно быть не менее 30 дБмо. Этот показатель не сообщается сервером аудио- и видеоконференций и IP-телефонами.</span><span class="sxs-lookup"><span data-stu-id="61f36-p132">Represents the Post-Analog Gain Control audio signal level for the audio the callee sent. The unit for this metric is dBmo. For acceptable quality, it should be at least 30 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61f36-467">каллиреквсигналлевел</span><span class="sxs-lookup"><span data-stu-id="61f36-467">CalleeRecvSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="61f36-468">int</span><span class="sxs-lookup"><span data-stu-id="61f36-468">int</span></span></p></td>
<td><p><span data-ttu-id="61f36-p133">Уровень звукового сигнала для аудиопотока, принятого вызываемым абонентом. Единица измерения для этого показателя — дБмо. Для приемлемого качества значение должно быть не менее 30 дБмо. Этот показатель не сообщается сервером аудио- и видеоконференций и IP-телефонами.</span><span class="sxs-lookup"><span data-stu-id="61f36-p133">Audio signal level for the audio the callee received. The unit for this metric is dBmo. For acceptable quality, it should be at least 30 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61f36-473">каллисендноиселевел</span><span class="sxs-lookup"><span data-stu-id="61f36-473">CalleeSendNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="61f36-474">int</span><span class="sxs-lookup"><span data-stu-id="61f36-474">int</span></span></p></td>
<td><p><span data-ttu-id="61f36-p134">Послеаналоговая регулировка уровня акустического шума для аудиопотока, отправленного вызываемым абонентом. Единица измерения для этого показателя — дБмо. Для приемлемого качества значение должно быть менее 35 дБмо. Этот показатель не сообщается сервером аудио- и видеоконференций и IP-телефонами.</span><span class="sxs-lookup"><span data-stu-id="61f36-p134">Post-Analog Gain Control audio noise level for the audio the callee sent. The unit for this metric is dBmo. For acceptable quality, it should be less than 35 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61f36-479">каллиреквноиселевел</span><span class="sxs-lookup"><span data-stu-id="61f36-479">CalleeRecvNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="61f36-480">int</span><span class="sxs-lookup"><span data-stu-id="61f36-480">int</span></span></p></td>
<td><p><span data-ttu-id="61f36-p135">Послеаналоговая регулировка уровня акустического шума для аудиопотока, принятого вызываемым абонентом. Единица измерения для этого показателя — дБмо. Для приемлемого качества значение должно быть менее 35 дБмо. Этот показатель не сообщается сервером аудио- и видеоконференций и IP-телефонами.</span><span class="sxs-lookup"><span data-stu-id="61f36-p135">Post-Analog Gain Control audio noise level for the audio the callee received. The unit for this metric is dBmo. For acceptable quality, it should be less than 35 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61f36-485">каллиечоретурн</span><span class="sxs-lookup"><span data-stu-id="61f36-485">CalleeEchoReturn</span></span></p></td>
<td><p><span data-ttu-id="61f36-486">int</span><span class="sxs-lookup"><span data-stu-id="61f36-486">int</span></span></p></td>
<td><p><span data-ttu-id="61f36-p136">Отношение мощностей некомпенсированного и скомпенсированного эхосигнала для вызываемого абонента. Единица измерения для этого показателя — дБ. Чем ниже значение, тем меньше эхосигнал. Этот показатель не сообщается сервером аудио- и видеоконференций и IP-телефонами.</span><span class="sxs-lookup"><span data-stu-id="61f36-p136">Echo Return Loss Enhancement for the callee. The unit for this metric is dB. Lower values represent less echo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61f36-491">каллиспеакерглитчрате</span><span class="sxs-lookup"><span data-stu-id="61f36-491">CalleeSpeakerGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="61f36-492">int</span><span class="sxs-lookup"><span data-stu-id="61f36-492">int</span></span></p></td>
<td><p><span data-ttu-id="61f36-p137">Среднее количество временных сбоев за пять минут при воспроизведении акустическими системами вызываемого абонента. Для хорошего качества должно быть не более одного сбоя в пять минут. Этот показатель не сообщается серверами аудио- и видеоконференций, серверами-посредниками и IP-телефонами.</span><span class="sxs-lookup"><span data-stu-id="61f36-p137">Average glitches per five minutes for the callee’s loudspeaker rendering. For good quality, this should be less than one per five minutes. Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61f36-496">каллимикглитчрате</span><span class="sxs-lookup"><span data-stu-id="61f36-496">CalleeMicGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="61f36-497">int</span><span class="sxs-lookup"><span data-stu-id="61f36-497">int</span></span></p></td>
<td><p><span data-ttu-id="61f36-p138">Среднее количество временных сбоев за пять минут при захвате звука микрофоном вызываемого абонента. Для хорошего качества должно быть не более одного сбоя в пять минут. Этот показатель не сообщается серверами аудио- и видеоконференций, серверами-посредниками и IP-телефонами.</span><span class="sxs-lookup"><span data-stu-id="61f36-p138">Average glitches per five minutes for the callee’s microphone capture. For good quality this should be less than one per five minutes. Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61f36-501">каллитиместампдрифтратемик</span><span class="sxs-lookup"><span data-stu-id="61f36-501">CalleeTimestampDriftRateMic</span></span></p></td>
<td><p><span data-ttu-id="61f36-502">десятичное число (9, 2)</span><span class="sxs-lookup"><span data-stu-id="61f36-502">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="61f36-503">Скорость рассинхронизации часов микрофона вызываемого абонента относительно часов процессора.</span><span class="sxs-lookup"><span data-stu-id="61f36-503">Callee’s microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61f36-504">каллитиместампдрифтратеспк</span><span class="sxs-lookup"><span data-stu-id="61f36-504">CalleeTimestampDriftRateSpk</span></span></p></td>
<td><p><span data-ttu-id="61f36-505">десятичное число (9, 2)</span><span class="sxs-lookup"><span data-stu-id="61f36-505">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="61f36-506">Скорость рассинхронизации часов динамика вызываемого абонента относительно часов процессора.</span><span class="sxs-lookup"><span data-stu-id="61f36-506">Callee’s speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61f36-507">каллитиместамперрормикмс</span><span class="sxs-lookup"><span data-stu-id="61f36-507">CalleeTimestampErrorMicMs</span></span></p></td>
<td><p><span data-ttu-id="61f36-508">десятичное число (9, 2)</span><span class="sxs-lookup"><span data-stu-id="61f36-508">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="61f36-509">Средняя ошибка метки времени для потока захвата микрофоном, в миллисекундах, в последние 20 секунд вызова.</span><span class="sxs-lookup"><span data-stu-id="61f36-509">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61f36-510">каллитиместамперрорспкмс</span><span class="sxs-lookup"><span data-stu-id="61f36-510">CalleeTimestampErrorSpkMs</span></span></p></td>
<td><p><span data-ttu-id="61f36-511">десятичное число (9, 2)</span><span class="sxs-lookup"><span data-stu-id="61f36-511">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="61f36-512">Средняя ошибка метки времени для потока воспроизведения динамиком вызываемого абонента, в миллисекундах, в последние 20 секунд вызова.</span><span class="sxs-lookup"><span data-stu-id="61f36-512">Average of the callee’s speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61f36-513">калливсентрикаусес</span><span class="sxs-lookup"><span data-stu-id="61f36-513">CalleeVsEntryCauses</span></span></p></td>
<td><p><span data-ttu-id="61f36-514">smallint</span><span class="sxs-lookup"><span data-stu-id="61f36-514">smallint</span></span></p></td>
<td><p><span data-ttu-id="61f36-515">Речевой коммутатор — это полудуплексный режим с уменьшенной возможностью прерывания.</span><span class="sxs-lookup"><span data-stu-id="61f36-515">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="61f36-516">Дополнительные сведения см. <a href="lync-server-2013-medialine-table.md">в таблице MediaLine в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="61f36-516">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61f36-517">каллиечоевенткаусес</span><span class="sxs-lookup"><span data-stu-id="61f36-517">CalleeEchoEventCauses</span></span></p></td>
<td><p><span data-ttu-id="61f36-518">tinyint</span><span class="sxs-lookup"><span data-stu-id="61f36-518">tinyint</span></span></p></td>
<td><p><span data-ttu-id="61f36-519">Причины события эхосигнала для вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="61f36-519">Causes of an echo event for the callee.</span></span> <span data-ttu-id="61f36-520">Дополнительные сведения см. <a href="lync-server-2013-medialine-table.md">в таблице MediaLine в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="61f36-520">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61f36-521">каллиечоперцентмиЦин</span><span class="sxs-lookup"><span data-stu-id="61f36-521">CalleeEchoPercentMicIn</span></span></p></td>
<td><p><span data-ttu-id="61f36-522">десятичное число (5, 2)</span><span class="sxs-lookup"><span data-stu-id="61f36-522">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="61f36-p141">Процент времени, когда в потоке захвата микрофоном вызываемого абонента обнаруживается эхосигнал. Если используется гарнитура, то значение должно быть низким.</span><span class="sxs-lookup"><span data-stu-id="61f36-p141">Percentage of time when echo is detected in the callee’s microphone capture stream. If headset is used, the value should be low.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61f36-525">каллиечоперцентсенд</span><span class="sxs-lookup"><span data-stu-id="61f36-525">CalleeEchoPercentSend</span></span></p></td>
<td><p><span data-ttu-id="61f36-526">десятичное число (5, 2)</span><span class="sxs-lookup"><span data-stu-id="61f36-526">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="61f36-p142">Процент времени, когда в потоке, отправленном вызываемым абонентом, обнаруживается эхосигнал. Высокое значение в отправленных потоках указывает на утечку эхосигнала.</span><span class="sxs-lookup"><span data-stu-id="61f36-p142">Percentage of time when echo is detected in the callee’s sent stream. High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61f36-529">каллирксагксигналлевел</span><span class="sxs-lookup"><span data-stu-id="61f36-529">CalleeRxAGCSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="61f36-530">int</span><span class="sxs-lookup"><span data-stu-id="61f36-530">int</span></span></p></td>
<td><p><span data-ttu-id="61f36-p143">Уровень сигнала, полученный на сервере-посреднике от шлюза, для аудиопотока вызываемого абонента; этот показатель относится только к серверу-посреднику. Единица измерения — dBoV. Приемлемый диапазон для хорошего качества — от -30 до -18 dBoV.</span><span class="sxs-lookup"><span data-stu-id="61f36-p143">Received signal level on the Mediation Server from the Gateway for the callee’s audio; this applies only to the Mediation Server. The unit of this metric is dBoV. For good quality, the acceptable range should be [-30 to -18] dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61f36-534">каллирксагкноиселевел</span><span class="sxs-lookup"><span data-stu-id="61f36-534">CalleeRxAGCNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="61f36-535">int</span><span class="sxs-lookup"><span data-stu-id="61f36-535">int</span></span></p></td>
<td><p><span data-ttu-id="61f36-p144">Уровень акустического шума, полученный на сервере-посреднике от шлюза, для аудиопотока вызываемого абонента. Этот показатель относится только к серверу-посреднику. Единица измерения — dBoV. Приемлемый диапазон для хорошего качества — ниже -50 dBoV.</span><span class="sxs-lookup"><span data-stu-id="61f36-p144">Received signal level on the Mediation Server from the Gateway for the callee’s audio. This applies only to the Mediation Server. The unit of this metric is dBoV. For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61f36-540">каллирксагкгаин</span><span class="sxs-lookup"><span data-stu-id="61f36-540">CalleeRxAGCGain</span></span></p></td>
<td><p><span data-ttu-id="61f36-541">int</span><span class="sxs-lookup"><span data-stu-id="61f36-541">int</span></span></p></td>
<td><p><span data-ttu-id="61f36-542">Автоматическая регулировка усиления на стороне сервера-посредника, применяемая к аудиопотоку вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="61f36-542">Automatic gain control (AGC) on the Mediation Server side applied to the callee’s audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61f36-543">каллиинитиалсигналлевелрмс</span><span class="sxs-lookup"><span data-stu-id="61f36-543">CalleeInitialSignalLevelRMS</span></span></p></td>
<td><p><span data-ttu-id="61f36-544">float</span><span class="sxs-lookup"><span data-stu-id="61f36-544">float</span></span></p></td>
<td><p><span data-ttu-id="61f36-545">Среднеквадратическое отклонение входящего сигнала вызываемого абонента до 30 первых секунд вызова.</span><span class="sxs-lookup"><span data-stu-id="61f36-545">Root mean square (RMS) of the incoming signal to the callee for up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61f36-546">RatioConcealedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="61f36-546">RatioConcealedSamplesAvg</span></span></p></td>
<td><p><span data-ttu-id="61f36-547">десятичное число (5, 2)</span><span class="sxs-lookup"><span data-stu-id="61f36-547">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="61f36-548">Среднее отношение числа скрытых образцов, созданных функцией восстановления звука, к обычным образцам.</span><span class="sxs-lookup"><span data-stu-id="61f36-548">Average ratio of concealed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61f36-549">ратиостретчедсамплесавг</span><span class="sxs-lookup"><span data-stu-id="61f36-549">RatioStretchedSamplesAvg</span></span></p></td>
<td><p><span data-ttu-id="61f36-550">десятичное число (5, 2)</span><span class="sxs-lookup"><span data-stu-id="61f36-550">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="61f36-551">Среднее отношение числа растянутых образцов, созданных функцией восстановления звука, к обычным образцам.</span><span class="sxs-lookup"><span data-stu-id="61f36-551">Average ratio of stretched samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61f36-552">ратиокомпресседсамплесавг</span><span class="sxs-lookup"><span data-stu-id="61f36-552">RatioCompressedSamplesAvg</span></span></p></td>
<td><p><span data-ttu-id="61f36-553">десятичное число (5, 2)</span><span class="sxs-lookup"><span data-stu-id="61f36-553">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="61f36-554">Среднее отношение числа сжатых образцов, созданных функцией восстановления звука, к обычным образцам.</span><span class="sxs-lookup"><span data-stu-id="61f36-554">Average ratio of compressed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61f36-555">Обработки</span><span class="sxs-lookup"><span data-stu-id="61f36-555">RoundTrip</span></span></p></td>
<td><p><span data-ttu-id="61f36-556">int</span><span class="sxs-lookup"><span data-stu-id="61f36-556">int</span></span></p></td>
<td><p><span data-ttu-id="61f36-557">Время приема-передачи на основе статистики RTCP.</span><span class="sxs-lookup"><span data-stu-id="61f36-557">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61f36-558">раундтрипмакс</span><span class="sxs-lookup"><span data-stu-id="61f36-558">RoundTripMax</span></span></p></td>
<td><p><span data-ttu-id="61f36-559">int</span><span class="sxs-lookup"><span data-stu-id="61f36-559">int</span></span></p></td>
<td><p><span data-ttu-id="61f36-560">Максимальное время приема-передачи для аудиопотока.</span><span class="sxs-lookup"><span data-stu-id="61f36-560">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61f36-561">овераллавгнетворкмос</span><span class="sxs-lookup"><span data-stu-id="61f36-561">OverallAvgNetworkMOS</span></span></p></td>
<td><p><span data-ttu-id="61f36-562">десятичное число (3, 2)</span><span class="sxs-lookup"><span data-stu-id="61f36-562">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="61f36-p145">Средняя экспертная оценка качества (MOS) в широкополосной сети для вызова. Значение этого показателя зависит от потерь пакетов, дрожания и используемого кодека. Диапазон — от 1,0 до 5,0.</span><span class="sxs-lookup"><span data-stu-id="61f36-p145">Average wideband Network MOS for the call. This metric depends on the packet loss, jitter, and codec used. Range is 1.0 to 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61f36-566">овераллминнетворкмос</span><span class="sxs-lookup"><span data-stu-id="61f36-566">OverallMinNetworkMOS</span></span></p></td>
<td><p><span data-ttu-id="61f36-567">десятичное число (3, 2)</span><span class="sxs-lookup"><span data-stu-id="61f36-567">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="61f36-568">Минимальная экспертная оценка качества (MOS) в широкополосной сети для вызова.</span><span class="sxs-lookup"><span data-stu-id="61f36-568">Minimum wideband Network MOS for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61f36-569">Значение sendlistenmos</span><span class="sxs-lookup"><span data-stu-id="61f36-569">SendListenMOS</span></span></p></td>
<td><p><span data-ttu-id="61f36-570">десятичное число (3, 2)</span><span class="sxs-lookup"><span data-stu-id="61f36-570">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="61f36-571">Средняя прогнозируемая экспертная оценка качества (MOS) при широкополосном прослушивании для отправленного аудиосигнала, включая характеристики уровня чувствительности микрофона, уровня помех и устройства захвата.</span><span class="sxs-lookup"><span data-stu-id="61f36-571">Average predicted wideband Listening MOS score for audio sent, including speech level, noise level and capture device characteristics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61f36-572">сендлистенмосмин</span><span class="sxs-lookup"><span data-stu-id="61f36-572">SendListenMOSMin</span></span></p></td>
<td><p><span data-ttu-id="61f36-573">десятичное число (3, 2)</span><span class="sxs-lookup"><span data-stu-id="61f36-573">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="61f36-574">Минимальное значение SendListenMOS для вызова.</span><span class="sxs-lookup"><span data-stu-id="61f36-574">Minimum SendListenMOS for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61f36-575">Значение recvlistenmos</span><span class="sxs-lookup"><span data-stu-id="61f36-575">RecvListenMOS</span></span></p></td>
<td><p><span data-ttu-id="61f36-576">десятичное число (3, 2)</span><span class="sxs-lookup"><span data-stu-id="61f36-576">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="61f36-577">Средняя прогнозируемая экспертная оценка качества (MOS) для аудиосигнала, полученного из сети, включая характеристики уровня чувствительности микрофона, уровня помех и устройства захвата.</span><span class="sxs-lookup"><span data-stu-id="61f36-577">Average predicted wideband Listening MOS score for audio received from the network including speech level, noise level, codec, network conditions and capture device characteristics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61f36-578">реквлистенмосмин</span><span class="sxs-lookup"><span data-stu-id="61f36-578">RecvListenMOSMin</span></span></p></td>
<td><p><span data-ttu-id="61f36-579">десятичное число (3, 2)</span><span class="sxs-lookup"><span data-stu-id="61f36-579">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="61f36-580">Минимальное значение RecvListenMOS для вызова.</span><span class="sxs-lookup"><span data-stu-id="61f36-580">Minimum RecvListenMOS for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61f36-581">аудиофекусед</span><span class="sxs-lookup"><span data-stu-id="61f36-581">AudioFECUsed</span></span></p></td>
<td><p><span data-ttu-id="61f36-582">Битовая</span><span class="sxs-lookup"><span data-stu-id="61f36-582">bit</span></span></p></td>
<td><p><span data-ttu-id="61f36-583">Указывает, применялась ли для этого вызова прямая коррекция аудиосигнала.</span><span class="sxs-lookup"><span data-stu-id="61f36-583">Indicates whether audio FEC was used for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61f36-584">сендерискаллерпаи</span><span class="sxs-lookup"><span data-stu-id="61f36-584">SenderIsCallerPAI</span></span></p></td>
<td><p><span data-ttu-id="61f36-585">Битовая</span><span class="sxs-lookup"><span data-stu-id="61f36-585">bit</span></span></p></td>
<td><p><span data-ttu-id="61f36-586">Указывает направление передачи данных P-Asserted-Identity: 1 указывает направление потока от вызывающего абонента к вызываемому; 0 указывает направление потока от вызываемого абонента к вызывающему.</span><span class="sxs-lookup"><span data-stu-id="61f36-586">Indicates direction of the p-asserted identify information; 1 means the stream direction is from the caller to the callee; 0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

