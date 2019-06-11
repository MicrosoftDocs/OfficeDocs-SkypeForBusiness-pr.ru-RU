---
title: 'Lync Server 2013: представление сеанса'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Session view
ms:assetid: 49e33f5b-45d0-4146-a5a4-76954d895a98
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688048(v=OCS.15)
ms:contentKeyID: 49733641
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a90d6a3f066caccb20b141daa485cabea29e2352
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822036"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="session-view-in-lync-server-2013"></a><span data-ttu-id="e9d75-102">Представление сеанса в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9d75-102">Session view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e9d75-103">_**Тема последнего изменения:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="e9d75-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="e9d75-104">В представлении сеанса хранятся сведения о сеансах с записями в базе данных.</span><span class="sxs-lookup"><span data-stu-id="e9d75-104">The Session View stores information about sessions that have records in the database.</span></span> <span data-ttu-id="e9d75-105">Это представление было представлено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e9d75-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e9d75-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="e9d75-106">Column</span></span></th>
<th><span data-ttu-id="e9d75-107">Тип данных</span><span class="sxs-lookup"><span data-stu-id="e9d75-107">Data Type</span></span></th>
<th><span data-ttu-id="e9d75-108">Подробности</span><span class="sxs-lookup"><span data-stu-id="e9d75-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e9d75-109">Конференцедатетиме</span><span class="sxs-lookup"><span data-stu-id="e9d75-109">ConferenceDateTime</span></span></p></td>
<td><p><span data-ttu-id="e9d75-110">datetime</span><span class="sxs-lookup"><span data-stu-id="e9d75-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="e9d75-111">На которую ссылается таблица Медиалине.</span><span class="sxs-lookup"><span data-stu-id="e9d75-111">Referenced from the MediaLine Table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9d75-112">Конференцеури</span><span class="sxs-lookup"><span data-stu-id="e9d75-112">ConferenceURI</span></span></p></td>
<td><p><span data-ttu-id="e9d75-113">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="e9d75-113">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="e9d75-114">Универсальный код ресурса (URI) для Конференции, если это конференция, или Диалогид, если это одноранговый сеанс.</span><span class="sxs-lookup"><span data-stu-id="e9d75-114">Conference URI if this is a conference, or DialogID if this is a peer-to-peer session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9d75-115">Анализ</span><span class="sxs-lookup"><span data-stu-id="e9d75-115">Correlation</span></span></p></td>
<td><p><span data-ttu-id="e9d75-116">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="e9d75-116">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="e9d75-117">Идентификатор корреляции для сеанса.</span><span class="sxs-lookup"><span data-stu-id="e9d75-117">Correlation ID of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9d75-118">Диалогкатегори</span><span class="sxs-lookup"><span data-stu-id="e9d75-118">DialogCategory</span></span></p></td>
<td><p><span data-ttu-id="e9d75-119">бит</span><span class="sxs-lookup"><span data-stu-id="e9d75-119">bit</span></span></p></td>
<td><p><span data-ttu-id="e9d75-120">Категория диалогового окна; 0 — это сервер Lync Server для устранения проблем; 1 — это сервер исправлений для шлюза PSTN Gateway.</span><span class="sxs-lookup"><span data-stu-id="e9d75-120">Dialog category; 0 is Lync Server to Mediation Server leg; 1 is Mediation Server to PSTN gateway leg.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9d75-121">Медиатионсервербипассфлаг</span><span class="sxs-lookup"><span data-stu-id="e9d75-121">MediationServerBypassFlag</span></span></p></td>
<td><p><span data-ttu-id="e9d75-122">бит</span><span class="sxs-lookup"><span data-stu-id="e9d75-122">bit</span></span></p></td>
<td><p><span data-ttu-id="e9d75-123">Указывает, был ли звонок пропущен.</span><span class="sxs-lookup"><span data-stu-id="e9d75-123">Indicates whether or not the call was bypassed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9d75-124">Медиабипассварнингфлаг</span><span class="sxs-lookup"><span data-stu-id="e9d75-124">MediaBypassWarningFlag</span></span></p></td>
<td><p><span data-ttu-id="e9d75-125">целое</span><span class="sxs-lookup"><span data-stu-id="e9d75-125">int</span></span></p></td>
<td><p><span data-ttu-id="e9d75-126">Это поле, если оно указано, указывает, почему звонок не обходится даже в том случае, если идентификаторы обхода не совпадают.</span><span class="sxs-lookup"><span data-stu-id="e9d75-126">This field, if present, indicates why a call was not bypassed even if the bypass IDs matched.</span></span> <span data-ttu-id="e9d75-127">Для Lync Server определено только одно значение:</span><span class="sxs-lookup"><span data-stu-id="e9d75-127">For Lync Server, only one value is defined:</span></span></p>
<p><span data-ttu-id="e9d75-128">0x0001 — Неизвестный идентификатор обхода для сетевого адаптера по умолчанию</span><span class="sxs-lookup"><span data-stu-id="e9d75-128">0x0001 – Unknown bypass ID for Default network adapter</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9d75-129">StartTime</span><span class="sxs-lookup"><span data-stu-id="e9d75-129">StartTime</span></span></p></td>
<td><p><span data-ttu-id="e9d75-130">datetime</span><span class="sxs-lookup"><span data-stu-id="e9d75-130">datetime</span></span></p></td>
<td><p><span data-ttu-id="e9d75-131">Время начала звонка.</span><span class="sxs-lookup"><span data-stu-id="e9d75-131">Call start time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9d75-132">EndTime</span><span class="sxs-lookup"><span data-stu-id="e9d75-132">EndTime</span></span></p></td>
<td><p><span data-ttu-id="e9d75-133">datetime</span><span class="sxs-lookup"><span data-stu-id="e9d75-133">datetime</span></span></p></td>
<td><p><span data-ttu-id="e9d75-134">Время окончания звонка.</span><span class="sxs-lookup"><span data-stu-id="e9d75-134">Call end time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9d75-135">Каллерпул</span><span class="sxs-lookup"><span data-stu-id="e9d75-135">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="e9d75-136">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e9d75-136">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e9d75-137">Полное доменное имя пула вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="e9d75-137">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9d75-138">Каллипул</span><span class="sxs-lookup"><span data-stu-id="e9d75-138">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="e9d75-139">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e9d75-139">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e9d75-140">Полное доменное имя пула вызываемых абонентов.</span><span class="sxs-lookup"><span data-stu-id="e9d75-140">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9d75-141">Каллерпаи</span><span class="sxs-lookup"><span data-stu-id="e9d75-141">CallerPAI</span></span></p></td>
<td><p><span data-ttu-id="e9d75-142">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="e9d75-142">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="e9d75-143">Универсальный код ресурса (URI) удостоверения вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="e9d75-143">Caller’s p-asserted identity URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9d75-144">Каллипаи</span><span class="sxs-lookup"><span data-stu-id="e9d75-144">CalleePAI</span></span></p></td>
<td><p><span data-ttu-id="e9d75-145">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="e9d75-145">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="e9d75-146">КОД URI удостоверения, утвержденный вызываемым p.</span><span class="sxs-lookup"><span data-stu-id="e9d75-146">Callee’s p-asserted identity URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9d75-147">Каллерендпоинт</span><span class="sxs-lookup"><span data-stu-id="e9d75-147">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="e9d75-148">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e9d75-148">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e9d75-149">Имя конечной точки вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="e9d75-149">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9d75-150">Каллиендпоинт</span><span class="sxs-lookup"><span data-stu-id="e9d75-150">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="e9d75-151">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e9d75-151">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e9d75-152">Имя конечной точки вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="e9d75-152">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9d75-153">Каллерусеражент</span><span class="sxs-lookup"><span data-stu-id="e9d75-153">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="e9d75-154">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e9d75-154">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e9d75-155">Строка агента пользователя вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="e9d75-155">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9d75-156">Каллерусераженттипе</span><span class="sxs-lookup"><span data-stu-id="e9d75-156">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="e9d75-157">smallint</span><span class="sxs-lookup"><span data-stu-id="e9d75-157">smallint</span></span></p></td>
<td><p><span data-ttu-id="e9d75-158">Тип агента пользователя вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="e9d75-158">Type of caller’s user agent.</span></span> <span data-ttu-id="e9d75-159">Дополнительные сведения: <a href="lync-server-2013-useragent-table.md">Таблица UserAgent в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e9d75-159">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9d75-160">Каллерусераженткатегори</span><span class="sxs-lookup"><span data-stu-id="e9d75-160">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="e9d75-161">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="e9d75-161">nvarchar (64)</span></span></p></td>
<td><p><span data-ttu-id="e9d75-162">Категория агента пользователя вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="e9d75-162">Category of caller’s user agent.</span></span> <span data-ttu-id="e9d75-163">Дополнительные сведения <a href="lync-server-2013-useragentdef-table-qoe.md">усеражентдеф в таблице "QoE" в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e9d75-163">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9d75-164">Каллиусеражент</span><span class="sxs-lookup"><span data-stu-id="e9d75-164">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="e9d75-165">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e9d75-165">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e9d75-166">Строка агента пользователя вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="e9d75-166">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9d75-167">Каллиусераженттипе</span><span class="sxs-lookup"><span data-stu-id="e9d75-167">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="e9d75-168">smallint</span><span class="sxs-lookup"><span data-stu-id="e9d75-168">smallint</span></span></p></td>
<td><p><span data-ttu-id="e9d75-169">Тип агента пользователя для вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="e9d75-169">Type of user agent for the callee.</span></span> <span data-ttu-id="e9d75-170">Дополнительные сведения: <a href="lync-server-2013-useragent-table.md">Таблица UserAgent в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e9d75-170">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9d75-171">Каллиусераженткатегори</span><span class="sxs-lookup"><span data-stu-id="e9d75-171">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="e9d75-172">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="e9d75-172">nvarchar (64)</span></span></p></td>
<td><p><span data-ttu-id="e9d75-173">Категория агента пользователя для вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="e9d75-173">User agent category for the callee.</span></span> <span data-ttu-id="e9d75-174">Дополнительные сведения <a href="lync-server-2013-useragentdef-table-qoe.md">усеражентдеф в таблице "QoE" в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e9d75-174">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9d75-175">Каллерури</span><span class="sxs-lookup"><span data-stu-id="e9d75-175">CallerURI</span></span></p></td>
<td><p><span data-ttu-id="e9d75-176">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="e9d75-176">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="e9d75-177">URI вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="e9d75-177">Caller’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9d75-178">Каллиури</span><span class="sxs-lookup"><span data-stu-id="e9d75-178">CalleeURI</span></span></p></td>
<td><p><span data-ttu-id="e9d75-179">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="e9d75-179">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="e9d75-180">Универсальный код ресурса (URI) вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="e9d75-180">Callee’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9d75-181">Каллприоирти</span><span class="sxs-lookup"><span data-stu-id="e9d75-181">CallPrioirty</span></span></p></td>
<td><p><span data-ttu-id="e9d75-182">целое</span><span class="sxs-lookup"><span data-stu-id="e9d75-182">int</span></span></p></td>
<td><p><span data-ttu-id="e9d75-183">Приоритет звонка.</span><span class="sxs-lookup"><span data-stu-id="e9d75-183">Priority of the call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

