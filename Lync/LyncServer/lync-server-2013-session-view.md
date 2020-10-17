---
title: 'Lync Server 2013: представление сеанса'
description: 'Lync Server 2013: представление сеанса.'
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
ms.openlocfilehash: ff4bc4abbd55e073006693d28f092f077698ef75
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545015"
---
# <a name="session-view-in-lync-server-2013"></a><span data-ttu-id="42871-103">Представление сеанса в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="42871-103">Session view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="42871-104">_**Последнее изменение темы:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="42871-104">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="42871-105">В представлении сеанса сохраняются сведения о сеансах, для которых есть записи в базе данных.</span><span class="sxs-lookup"><span data-stu-id="42871-105">The Session View stores information about sessions that have records in the database.</span></span> <span data-ttu-id="42871-106">Это представление было представлено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="42871-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="42871-107">Столбец</span><span class="sxs-lookup"><span data-stu-id="42871-107">Column</span></span></th>
<th><span data-ttu-id="42871-108">Тип данных</span><span class="sxs-lookup"><span data-stu-id="42871-108">Data Type</span></span></th>
<th><span data-ttu-id="42871-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="42871-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="42871-110">конференцедатетиме</span><span class="sxs-lookup"><span data-stu-id="42871-110">ConferenceDateTime</span></span></p></td>
<td><p><span data-ttu-id="42871-111">datetime</span><span class="sxs-lookup"><span data-stu-id="42871-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="42871-112">Ссылка из таблицы линии медиаданных.</span><span class="sxs-lookup"><span data-stu-id="42871-112">Referenced from the MediaLine Table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42871-113">конференцеури</span><span class="sxs-lookup"><span data-stu-id="42871-113">ConferenceURI</span></span></p></td>
<td><p><span data-ttu-id="42871-114">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="42871-114">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="42871-115">URI конференции, если это конференция, или DialogID, если это сеанс между одноранговыми узлами.</span><span class="sxs-lookup"><span data-stu-id="42871-115">Conference URI if this is a conference, or DialogID if this is a peer-to-peer session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="42871-116">Correlation</span><span class="sxs-lookup"><span data-stu-id="42871-116">Correlation</span></span></p></td>
<td><p><span data-ttu-id="42871-117">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="42871-117">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="42871-118">Идентификатор корреляции сеанса</span><span class="sxs-lookup"><span data-stu-id="42871-118">Correlation ID of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42871-119">диалогкатегори</span><span class="sxs-lookup"><span data-stu-id="42871-119">DialogCategory</span></span></p></td>
<td><p><span data-ttu-id="42871-120">Битовая</span><span class="sxs-lookup"><span data-stu-id="42871-120">bit</span></span></p></td>
<td><p><span data-ttu-id="42871-121">Категория диалоговых окон; 0 — сервер Lync Server — это ветвь сервера-посредника; 1 — сервер-посредник для шлюза PSTN.</span><span class="sxs-lookup"><span data-stu-id="42871-121">Dialog category; 0 is Lync Server to Mediation Server leg; 1 is Mediation Server to PSTN gateway leg.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="42871-122">медиатионсервербипассфлаг</span><span class="sxs-lookup"><span data-stu-id="42871-122">MediationServerBypassFlag</span></span></p></td>
<td><p><span data-ttu-id="42871-123">Битовая</span><span class="sxs-lookup"><span data-stu-id="42871-123">bit</span></span></p></td>
<td><p><span data-ttu-id="42871-124">Указывает, был ли обойден вызов.</span><span class="sxs-lookup"><span data-stu-id="42871-124">Indicates whether or not the call was bypassed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42871-125">медиабипассварнингфлаг</span><span class="sxs-lookup"><span data-stu-id="42871-125">MediaBypassWarningFlag</span></span></p></td>
<td><p><span data-ttu-id="42871-126">int</span><span class="sxs-lookup"><span data-stu-id="42871-126">int</span></span></p></td>
<td><p><span data-ttu-id="42871-127">Если это поле присутствует, оно указывает, почему вызов не может быть обойден, даже если идентификаторы обхода совпадают.</span><span class="sxs-lookup"><span data-stu-id="42871-127">This field, if present, indicates why a call was not bypassed even if the bypass IDs matched.</span></span> <span data-ttu-id="42871-128">Для Lync Server определено только одно значение:</span><span class="sxs-lookup"><span data-stu-id="42871-128">For Lync Server, only one value is defined:</span></span></p>
<p><span data-ttu-id="42871-129">0x0001 – неизвестный идентификатор обхода для сетевого адаптера по умолчанию</span><span class="sxs-lookup"><span data-stu-id="42871-129">0x0001 – Unknown bypass ID for Default network adapter</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="42871-130">StartTime</span><span class="sxs-lookup"><span data-stu-id="42871-130">StartTime</span></span></p></td>
<td><p><span data-ttu-id="42871-131">datetime</span><span class="sxs-lookup"><span data-stu-id="42871-131">datetime</span></span></p></td>
<td><p><span data-ttu-id="42871-132">Время начала вызова.</span><span class="sxs-lookup"><span data-stu-id="42871-132">Call start time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42871-133">EndTime</span><span class="sxs-lookup"><span data-stu-id="42871-133">EndTime</span></span></p></td>
<td><p><span data-ttu-id="42871-134">datetime</span><span class="sxs-lookup"><span data-stu-id="42871-134">datetime</span></span></p></td>
<td><p><span data-ttu-id="42871-135">Время окончания вызова.</span><span class="sxs-lookup"><span data-stu-id="42871-135">Call end time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="42871-136">каллерпул</span><span class="sxs-lookup"><span data-stu-id="42871-136">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="42871-137">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="42871-137">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="42871-138">Полное доменное имя пула вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="42871-138">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42871-139">каллипул</span><span class="sxs-lookup"><span data-stu-id="42871-139">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="42871-140">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="42871-140">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="42871-141">Полное доменное имя пула вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="42871-141">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="42871-142">каллерпаи</span><span class="sxs-lookup"><span data-stu-id="42871-142">CallerPAI</span></span></p></td>
<td><p><span data-ttu-id="42871-143">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="42871-143">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="42871-144">URI удостоверения PAI вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="42871-144">Caller’s p-asserted identity URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42871-145">каллипаи</span><span class="sxs-lookup"><span data-stu-id="42871-145">CalleePAI</span></span></p></td>
<td><p><span data-ttu-id="42871-146">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="42871-146">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="42871-147">URI удостоверения PAI вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="42871-147">Callee’s p-asserted identity URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="42871-148">каллерендпоинт</span><span class="sxs-lookup"><span data-stu-id="42871-148">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="42871-149">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="42871-149">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="42871-150">Имя конечной точки вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="42871-150">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42871-151">каллиендпоинт</span><span class="sxs-lookup"><span data-stu-id="42871-151">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="42871-152">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="42871-152">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="42871-153">Имя конечной точки абонента.</span><span class="sxs-lookup"><span data-stu-id="42871-153">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="42871-154">каллерусеражент</span><span class="sxs-lookup"><span data-stu-id="42871-154">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="42871-155">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="42871-155">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="42871-156">Строка агента пользователя вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="42871-156">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42871-157">каллерусераженттипе</span><span class="sxs-lookup"><span data-stu-id="42871-157">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="42871-158">smallint</span><span class="sxs-lookup"><span data-stu-id="42871-158">smallint</span></span></p></td>
<td><p><span data-ttu-id="42871-159">Тип агента пользователя звонящего абонента.</span><span class="sxs-lookup"><span data-stu-id="42871-159">Type of caller’s user agent.</span></span> <span data-ttu-id="42871-160">Дополнительные сведения см. <a href="lync-server-2013-useragent-table.md">в таблице UserAgent в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="42871-160">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="42871-161">каллерусераженткатегори</span><span class="sxs-lookup"><span data-stu-id="42871-161">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="42871-162">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="42871-162">nvarchar (64)</span></span></p></td>
<td><p><span data-ttu-id="42871-163">Категория агента пользователя вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="42871-163">Category of caller’s user agent.</span></span> <span data-ttu-id="42871-164">Для получения подробных сведений ознакомьтесь со статьей <a href="lync-server-2013-useragentdef-table-qoe.md">таблица таблица useragentdef (QoE) в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="42871-164">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42871-165">каллиусеражент</span><span class="sxs-lookup"><span data-stu-id="42871-165">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="42871-166">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="42871-166">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="42871-167">Строка агента пользователя вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="42871-167">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="42871-168">каллиусераженттипе</span><span class="sxs-lookup"><span data-stu-id="42871-168">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="42871-169">smallint</span><span class="sxs-lookup"><span data-stu-id="42871-169">smallint</span></span></p></td>
<td><p><span data-ttu-id="42871-170">Тип агента пользователя вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="42871-170">Type of user agent for the callee.</span></span> <span data-ttu-id="42871-171">Дополнительные сведения см. <a href="lync-server-2013-useragent-table.md">в таблице UserAgent в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="42871-171">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42871-172">каллиусераженткатегори</span><span class="sxs-lookup"><span data-stu-id="42871-172">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="42871-173">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="42871-173">nvarchar (64)</span></span></p></td>
<td><p><span data-ttu-id="42871-174">Категория агента пользователя вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="42871-174">User agent category for the callee.</span></span> <span data-ttu-id="42871-175">Для получения подробных сведений ознакомьтесь со статьей <a href="lync-server-2013-useragentdef-table-qoe.md">таблица таблица useragentdef (QoE) в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="42871-175">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="42871-176">каллерури</span><span class="sxs-lookup"><span data-stu-id="42871-176">CallerURI</span></span></p></td>
<td><p><span data-ttu-id="42871-177">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="42871-177">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="42871-178">URI вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="42871-178">Caller’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42871-179">каллиури</span><span class="sxs-lookup"><span data-stu-id="42871-179">CalleeURI</span></span></p></td>
<td><p><span data-ttu-id="42871-180">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="42871-180">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="42871-181">URI вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="42871-181">Callee’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="42871-182">каллприоирти</span><span class="sxs-lookup"><span data-stu-id="42871-182">CallPrioirty</span></span></p></td>
<td><p><span data-ttu-id="42871-183">int</span><span class="sxs-lookup"><span data-stu-id="42871-183">int</span></span></p></td>
<td><p><span data-ttu-id="42871-184">Приоритет вызова.</span><span class="sxs-lookup"><span data-stu-id="42871-184">Priority of the call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

