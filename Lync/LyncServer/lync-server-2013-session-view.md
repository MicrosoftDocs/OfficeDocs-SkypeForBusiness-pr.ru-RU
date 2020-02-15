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
ms.openlocfilehash: 7d20d748f9c9754efab768a702f1272bc70d889e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051301"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="session-view-in-lync-server-2013"></a><span data-ttu-id="31b19-102">Представление сеанса в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="31b19-102">Session view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="31b19-103">_**Последнее изменение темы:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="31b19-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="31b19-104">В представлении сеанса сохраняются сведения о сеансах, для которых есть записи в базе данных.</span><span class="sxs-lookup"><span data-stu-id="31b19-104">The Session View stores information about sessions that have records in the database.</span></span> <span data-ttu-id="31b19-105">Это представление было представлено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="31b19-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="31b19-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="31b19-106">Column</span></span></th>
<th><span data-ttu-id="31b19-107">Тип данных</span><span class="sxs-lookup"><span data-stu-id="31b19-107">Data Type</span></span></th>
<th><span data-ttu-id="31b19-108">Сведения</span><span class="sxs-lookup"><span data-stu-id="31b19-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="31b19-109">конференцедатетиме</span><span class="sxs-lookup"><span data-stu-id="31b19-109">ConferenceDateTime</span></span></p></td>
<td><p><span data-ttu-id="31b19-110">datetime</span><span class="sxs-lookup"><span data-stu-id="31b19-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="31b19-111">Ссылка из таблицы линии медиаданных.</span><span class="sxs-lookup"><span data-stu-id="31b19-111">Referenced from the MediaLine Table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="31b19-112">конференцеури</span><span class="sxs-lookup"><span data-stu-id="31b19-112">ConferenceURI</span></span></p></td>
<td><p><span data-ttu-id="31b19-113">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="31b19-113">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="31b19-114">URI конференции, если это конференция, или DialogID, если это сеанс между одноранговыми узлами.</span><span class="sxs-lookup"><span data-stu-id="31b19-114">Conference URI if this is a conference, or DialogID if this is a peer-to-peer session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="31b19-115">Correlation</span><span class="sxs-lookup"><span data-stu-id="31b19-115">Correlation</span></span></p></td>
<td><p><span data-ttu-id="31b19-116">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="31b19-116">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="31b19-117">Идентификатор корреляции сеанса</span><span class="sxs-lookup"><span data-stu-id="31b19-117">Correlation ID of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="31b19-118">диалогкатегори</span><span class="sxs-lookup"><span data-stu-id="31b19-118">DialogCategory</span></span></p></td>
<td><p><span data-ttu-id="31b19-119">Битовая</span><span class="sxs-lookup"><span data-stu-id="31b19-119">bit</span></span></p></td>
<td><p><span data-ttu-id="31b19-120">Категория диалоговых окон; 0 — сервер Lync Server — это ветвь сервера-посредника; 1 — сервер-посредник для шлюза PSTN.</span><span class="sxs-lookup"><span data-stu-id="31b19-120">Dialog category; 0 is Lync Server to Mediation Server leg; 1 is Mediation Server to PSTN gateway leg.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="31b19-121">медиатионсервербипассфлаг</span><span class="sxs-lookup"><span data-stu-id="31b19-121">MediationServerBypassFlag</span></span></p></td>
<td><p><span data-ttu-id="31b19-122">Битовая</span><span class="sxs-lookup"><span data-stu-id="31b19-122">bit</span></span></p></td>
<td><p><span data-ttu-id="31b19-123">Указывает, был ли обойден вызов.</span><span class="sxs-lookup"><span data-stu-id="31b19-123">Indicates whether or not the call was bypassed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="31b19-124">медиабипассварнингфлаг</span><span class="sxs-lookup"><span data-stu-id="31b19-124">MediaBypassWarningFlag</span></span></p></td>
<td><p><span data-ttu-id="31b19-125">int</span><span class="sxs-lookup"><span data-stu-id="31b19-125">int</span></span></p></td>
<td><p><span data-ttu-id="31b19-126">Если это поле присутствует, оно указывает, почему вызов не может быть обойден, даже если идентификаторы обхода совпадают.</span><span class="sxs-lookup"><span data-stu-id="31b19-126">This field, if present, indicates why a call was not bypassed even if the bypass IDs matched.</span></span> <span data-ttu-id="31b19-127">Для Lync Server определено только одно значение:</span><span class="sxs-lookup"><span data-stu-id="31b19-127">For Lync Server, only one value is defined:</span></span></p>
<p><span data-ttu-id="31b19-128">0x0001 – неизвестный идентификатор обхода для сетевого адаптера по умолчанию</span><span class="sxs-lookup"><span data-stu-id="31b19-128">0x0001 – Unknown bypass ID for Default network adapter</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="31b19-129">StartTime</span><span class="sxs-lookup"><span data-stu-id="31b19-129">StartTime</span></span></p></td>
<td><p><span data-ttu-id="31b19-130">datetime</span><span class="sxs-lookup"><span data-stu-id="31b19-130">datetime</span></span></p></td>
<td><p><span data-ttu-id="31b19-131">Время начала вызова.</span><span class="sxs-lookup"><span data-stu-id="31b19-131">Call start time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="31b19-132">EndTime</span><span class="sxs-lookup"><span data-stu-id="31b19-132">EndTime</span></span></p></td>
<td><p><span data-ttu-id="31b19-133">datetime</span><span class="sxs-lookup"><span data-stu-id="31b19-133">datetime</span></span></p></td>
<td><p><span data-ttu-id="31b19-134">Время окончания вызова.</span><span class="sxs-lookup"><span data-stu-id="31b19-134">Call end time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="31b19-135">каллерпул</span><span class="sxs-lookup"><span data-stu-id="31b19-135">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="31b19-136">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="31b19-136">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="31b19-137">Полное доменное имя пула вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="31b19-137">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="31b19-138">каллипул</span><span class="sxs-lookup"><span data-stu-id="31b19-138">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="31b19-139">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="31b19-139">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="31b19-140">Полное доменное имя пула вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="31b19-140">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="31b19-141">каллерпаи</span><span class="sxs-lookup"><span data-stu-id="31b19-141">CallerPAI</span></span></p></td>
<td><p><span data-ttu-id="31b19-142">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="31b19-142">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="31b19-143">URI удостоверения PAI вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="31b19-143">Caller’s p-asserted identity URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="31b19-144">каллипаи</span><span class="sxs-lookup"><span data-stu-id="31b19-144">CalleePAI</span></span></p></td>
<td><p><span data-ttu-id="31b19-145">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="31b19-145">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="31b19-146">URI удостоверения PAI вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="31b19-146">Callee’s p-asserted identity URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="31b19-147">каллерендпоинт</span><span class="sxs-lookup"><span data-stu-id="31b19-147">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="31b19-148">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="31b19-148">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="31b19-149">Имя конечной точки вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="31b19-149">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="31b19-150">каллиендпоинт</span><span class="sxs-lookup"><span data-stu-id="31b19-150">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="31b19-151">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="31b19-151">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="31b19-152">Имя конечной точки абонента.</span><span class="sxs-lookup"><span data-stu-id="31b19-152">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="31b19-153">каллерусеражент</span><span class="sxs-lookup"><span data-stu-id="31b19-153">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="31b19-154">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="31b19-154">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="31b19-155">Строка агента пользователя вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="31b19-155">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="31b19-156">каллерусераженттипе</span><span class="sxs-lookup"><span data-stu-id="31b19-156">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="31b19-157">smallint</span><span class="sxs-lookup"><span data-stu-id="31b19-157">smallint</span></span></p></td>
<td><p><span data-ttu-id="31b19-158">Тип агента пользователя звонящего абонента.</span><span class="sxs-lookup"><span data-stu-id="31b19-158">Type of caller’s user agent.</span></span> <span data-ttu-id="31b19-159">Дополнительные сведения см. <a href="lync-server-2013-useragent-table.md">в таблице UserAgent в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="31b19-159">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="31b19-160">каллерусераженткатегори</span><span class="sxs-lookup"><span data-stu-id="31b19-160">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="31b19-161">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="31b19-161">nvarchar (64)</span></span></p></td>
<td><p><span data-ttu-id="31b19-162">Категория агента пользователя вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="31b19-162">Category of caller’s user agent.</span></span> <span data-ttu-id="31b19-163">Для получения подробных сведений ознакомьтесь со статьей <a href="lync-server-2013-useragentdef-table-qoe.md">таблица таблица useragentdef (QoE) в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="31b19-163">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="31b19-164">каллиусеражент</span><span class="sxs-lookup"><span data-stu-id="31b19-164">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="31b19-165">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="31b19-165">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="31b19-166">Строка агента пользователя вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="31b19-166">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="31b19-167">каллиусераженттипе</span><span class="sxs-lookup"><span data-stu-id="31b19-167">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="31b19-168">smallint</span><span class="sxs-lookup"><span data-stu-id="31b19-168">smallint</span></span></p></td>
<td><p><span data-ttu-id="31b19-169">Тип агента пользователя вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="31b19-169">Type of user agent for the callee.</span></span> <span data-ttu-id="31b19-170">Дополнительные сведения см. <a href="lync-server-2013-useragent-table.md">в таблице UserAgent в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="31b19-170">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="31b19-171">каллиусераженткатегори</span><span class="sxs-lookup"><span data-stu-id="31b19-171">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="31b19-172">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="31b19-172">nvarchar (64)</span></span></p></td>
<td><p><span data-ttu-id="31b19-173">Категория агента пользователя вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="31b19-173">User agent category for the callee.</span></span> <span data-ttu-id="31b19-174">Для получения подробных сведений ознакомьтесь со статьей <a href="lync-server-2013-useragentdef-table-qoe.md">таблица таблица useragentdef (QoE) в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="31b19-174">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="31b19-175">каллерури</span><span class="sxs-lookup"><span data-stu-id="31b19-175">CallerURI</span></span></p></td>
<td><p><span data-ttu-id="31b19-176">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="31b19-176">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="31b19-177">URI вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="31b19-177">Caller’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="31b19-178">каллиури</span><span class="sxs-lookup"><span data-stu-id="31b19-178">CalleeURI</span></span></p></td>
<td><p><span data-ttu-id="31b19-179">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="31b19-179">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="31b19-180">URI вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="31b19-180">Callee’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="31b19-181">каллприоирти</span><span class="sxs-lookup"><span data-stu-id="31b19-181">CallPrioirty</span></span></p></td>
<td><p><span data-ttu-id="31b19-182">int</span><span class="sxs-lookup"><span data-stu-id="31b19-182">int</span></span></p></td>
<td><p><span data-ttu-id="31b19-183">Приоритет вызова.</span><span class="sxs-lookup"><span data-stu-id="31b19-183">Priority of the call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

