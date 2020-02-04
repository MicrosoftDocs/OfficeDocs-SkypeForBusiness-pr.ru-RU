---
title: 'Lync Server 2013: представление сеанса'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Session view
ms:assetid: 49e33f5b-45d0-4146-a5a4-76954d895a98
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688048(v=OCS.15)
ms:contentKeyID: 49733641
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6a153899fd484da861088a8e7672a69707e46a59
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764817"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="session-view-in-lync-server-2013"></a><span data-ttu-id="fa30c-102">Представление сеанса в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fa30c-102">Session view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fa30c-103">_**Тема последнего изменения:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="fa30c-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="fa30c-104">В представлении сеанса хранятся сведения о сеансах с записями в базе данных.</span><span class="sxs-lookup"><span data-stu-id="fa30c-104">The Session View stores information about sessions that have records in the database.</span></span> <span data-ttu-id="fa30c-105">Это представление было представлено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fa30c-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fa30c-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="fa30c-106">Column</span></span></th>
<th><span data-ttu-id="fa30c-107">Тип данных</span><span class="sxs-lookup"><span data-stu-id="fa30c-107">Data Type</span></span></th>
<th><span data-ttu-id="fa30c-108">Подробности</span><span class="sxs-lookup"><span data-stu-id="fa30c-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fa30c-109">конференцедатетиме</span><span class="sxs-lookup"><span data-stu-id="fa30c-109">ConferenceDateTime</span></span></p></td>
<td><p><span data-ttu-id="fa30c-110">datetime</span><span class="sxs-lookup"><span data-stu-id="fa30c-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="fa30c-111">На которую ссылается таблица Медиалине.</span><span class="sxs-lookup"><span data-stu-id="fa30c-111">Referenced from the MediaLine Table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa30c-112">конференцеури</span><span class="sxs-lookup"><span data-stu-id="fa30c-112">ConferenceURI</span></span></p></td>
<td><p><span data-ttu-id="fa30c-113">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="fa30c-113">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="fa30c-114">Универсальный код ресурса (URI) для Конференции, если это конференция, или Диалогид, если это одноранговый сеанс.</span><span class="sxs-lookup"><span data-stu-id="fa30c-114">Conference URI if this is a conference, or DialogID if this is a peer-to-peer session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa30c-115">Анализ</span><span class="sxs-lookup"><span data-stu-id="fa30c-115">Correlation</span></span></p></td>
<td><p><span data-ttu-id="fa30c-116">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="fa30c-116">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="fa30c-117">Идентификатор корреляции для сеанса.</span><span class="sxs-lookup"><span data-stu-id="fa30c-117">Correlation ID of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa30c-118">диалогкатегори</span><span class="sxs-lookup"><span data-stu-id="fa30c-118">DialogCategory</span></span></p></td>
<td><p><span data-ttu-id="fa30c-119">бит</span><span class="sxs-lookup"><span data-stu-id="fa30c-119">bit</span></span></p></td>
<td><p><span data-ttu-id="fa30c-120">Категория диалогового окна; 0 — это сервер Lync Server для устранения проблем; 1 — это сервер исправлений для шлюза PSTN Gateway.</span><span class="sxs-lookup"><span data-stu-id="fa30c-120">Dialog category; 0 is Lync Server to Mediation Server leg; 1 is Mediation Server to PSTN gateway leg.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa30c-121">медиатионсервербипассфлаг</span><span class="sxs-lookup"><span data-stu-id="fa30c-121">MediationServerBypassFlag</span></span></p></td>
<td><p><span data-ttu-id="fa30c-122">бит</span><span class="sxs-lookup"><span data-stu-id="fa30c-122">bit</span></span></p></td>
<td><p><span data-ttu-id="fa30c-123">Указывает, был ли звонок пропущен.</span><span class="sxs-lookup"><span data-stu-id="fa30c-123">Indicates whether or not the call was bypassed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa30c-124">медиабипассварнингфлаг</span><span class="sxs-lookup"><span data-stu-id="fa30c-124">MediaBypassWarningFlag</span></span></p></td>
<td><p><span data-ttu-id="fa30c-125">целое</span><span class="sxs-lookup"><span data-stu-id="fa30c-125">int</span></span></p></td>
<td><p><span data-ttu-id="fa30c-126">Это поле, если оно указано, указывает, почему звонок не обходится даже в том случае, если идентификаторы обхода не совпадают.</span><span class="sxs-lookup"><span data-stu-id="fa30c-126">This field, if present, indicates why a call was not bypassed even if the bypass IDs matched.</span></span> <span data-ttu-id="fa30c-127">Для Lync Server определено только одно значение:</span><span class="sxs-lookup"><span data-stu-id="fa30c-127">For Lync Server, only one value is defined:</span></span></p>
<p><span data-ttu-id="fa30c-128">0x0001 — Неизвестный идентификатор обхода для сетевого адаптера по умолчанию</span><span class="sxs-lookup"><span data-stu-id="fa30c-128">0x0001 – Unknown bypass ID for Default network adapter</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa30c-129">StartTime</span><span class="sxs-lookup"><span data-stu-id="fa30c-129">StartTime</span></span></p></td>
<td><p><span data-ttu-id="fa30c-130">datetime</span><span class="sxs-lookup"><span data-stu-id="fa30c-130">datetime</span></span></p></td>
<td><p><span data-ttu-id="fa30c-131">Время начала звонка.</span><span class="sxs-lookup"><span data-stu-id="fa30c-131">Call start time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa30c-132">EndTime</span><span class="sxs-lookup"><span data-stu-id="fa30c-132">EndTime</span></span></p></td>
<td><p><span data-ttu-id="fa30c-133">datetime</span><span class="sxs-lookup"><span data-stu-id="fa30c-133">datetime</span></span></p></td>
<td><p><span data-ttu-id="fa30c-134">Время окончания звонка.</span><span class="sxs-lookup"><span data-stu-id="fa30c-134">Call end time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa30c-135">каллерпул</span><span class="sxs-lookup"><span data-stu-id="fa30c-135">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="fa30c-136">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="fa30c-136">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fa30c-137">Полное доменное имя пула вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="fa30c-137">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa30c-138">каллипул</span><span class="sxs-lookup"><span data-stu-id="fa30c-138">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="fa30c-139">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="fa30c-139">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fa30c-140">Полное доменное имя пула вызываемых абонентов.</span><span class="sxs-lookup"><span data-stu-id="fa30c-140">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa30c-141">каллерпаи</span><span class="sxs-lookup"><span data-stu-id="fa30c-141">CallerPAI</span></span></p></td>
<td><p><span data-ttu-id="fa30c-142">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="fa30c-142">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="fa30c-143">Универсальный код ресурса (URI) удостоверения вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="fa30c-143">Caller’s p-asserted identity URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa30c-144">каллипаи</span><span class="sxs-lookup"><span data-stu-id="fa30c-144">CalleePAI</span></span></p></td>
<td><p><span data-ttu-id="fa30c-145">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="fa30c-145">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="fa30c-146">КОД URI удостоверения, утвержденный вызываемым p.</span><span class="sxs-lookup"><span data-stu-id="fa30c-146">Callee’s p-asserted identity URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa30c-147">каллерендпоинт</span><span class="sxs-lookup"><span data-stu-id="fa30c-147">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="fa30c-148">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="fa30c-148">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fa30c-149">Имя конечной точки вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="fa30c-149">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa30c-150">каллиендпоинт</span><span class="sxs-lookup"><span data-stu-id="fa30c-150">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="fa30c-151">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="fa30c-151">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fa30c-152">Имя конечной точки вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="fa30c-152">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa30c-153">каллерусеражент</span><span class="sxs-lookup"><span data-stu-id="fa30c-153">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="fa30c-154">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="fa30c-154">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fa30c-155">Строка агента пользователя вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="fa30c-155">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa30c-156">каллерусераженттипе</span><span class="sxs-lookup"><span data-stu-id="fa30c-156">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="fa30c-157">smallint</span><span class="sxs-lookup"><span data-stu-id="fa30c-157">smallint</span></span></p></td>
<td><p><span data-ttu-id="fa30c-158">Тип агента пользователя вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="fa30c-158">Type of caller’s user agent.</span></span> <span data-ttu-id="fa30c-159">Дополнительные сведения: <a href="lync-server-2013-useragent-table.md">Таблица UserAgent в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="fa30c-159">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa30c-160">каллерусераженткатегори</span><span class="sxs-lookup"><span data-stu-id="fa30c-160">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="fa30c-161">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="fa30c-161">nvarchar (64)</span></span></p></td>
<td><p><span data-ttu-id="fa30c-162">Категория агента пользователя вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="fa30c-162">Category of caller’s user agent.</span></span> <span data-ttu-id="fa30c-163">Дополнительные сведения <a href="lync-server-2013-useragentdef-table-qoe.md">усеражентдеф в таблице "QoE" в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="fa30c-163">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa30c-164">каллиусеражент</span><span class="sxs-lookup"><span data-stu-id="fa30c-164">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="fa30c-165">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="fa30c-165">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fa30c-166">Строка агента пользователя вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="fa30c-166">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa30c-167">каллиусераженттипе</span><span class="sxs-lookup"><span data-stu-id="fa30c-167">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="fa30c-168">smallint</span><span class="sxs-lookup"><span data-stu-id="fa30c-168">smallint</span></span></p></td>
<td><p><span data-ttu-id="fa30c-169">Тип агента пользователя для вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="fa30c-169">Type of user agent for the callee.</span></span> <span data-ttu-id="fa30c-170">Дополнительные сведения: <a href="lync-server-2013-useragent-table.md">Таблица UserAgent в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="fa30c-170">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa30c-171">каллиусераженткатегори</span><span class="sxs-lookup"><span data-stu-id="fa30c-171">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="fa30c-172">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="fa30c-172">nvarchar (64)</span></span></p></td>
<td><p><span data-ttu-id="fa30c-173">Категория агента пользователя для вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="fa30c-173">User agent category for the callee.</span></span> <span data-ttu-id="fa30c-174">Дополнительные сведения <a href="lync-server-2013-useragentdef-table-qoe.md">усеражентдеф в таблице "QoE" в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="fa30c-174">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa30c-175">каллерури</span><span class="sxs-lookup"><span data-stu-id="fa30c-175">CallerURI</span></span></p></td>
<td><p><span data-ttu-id="fa30c-176">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="fa30c-176">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="fa30c-177">URI вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="fa30c-177">Caller’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa30c-178">каллиури</span><span class="sxs-lookup"><span data-stu-id="fa30c-178">CalleeURI</span></span></p></td>
<td><p><span data-ttu-id="fa30c-179">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="fa30c-179">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="fa30c-180">Универсальный код ресурса (URI) вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="fa30c-180">Callee’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa30c-181">каллприоирти</span><span class="sxs-lookup"><span data-stu-id="fa30c-181">CallPrioirty</span></span></p></td>
<td><p><span data-ttu-id="fa30c-182">целое</span><span class="sxs-lookup"><span data-stu-id="fa30c-182">int</span></span></p></td>
<td><p><span data-ttu-id="fa30c-183">Приоритет звонка.</span><span class="sxs-lookup"><span data-stu-id="fa30c-183">Priority of the call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

