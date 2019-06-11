---
title: 'Lync Server 2013: таблица Session'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Session table
ms:assetid: 7f05529c-794d-41ed-bca4-2e85b87b2dec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398635(v=OCS.15)
ms:contentKeyID: 48184626
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5ab4eb63b95ecdf08c1967babba39cff2b2abf19
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822050"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="session-table-in-lync-server-2013"></a><span data-ttu-id="e48e7-102">Таблица Session в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e48e7-102">Session table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e48e7-103">_**Тема последнего изменения:** 2013-09-09_</span><span class="sxs-lookup"><span data-stu-id="e48e7-103">_**Topic Last Modified:** 2013-09-09_</span></span>

<span data-ttu-id="e48e7-104">Каждая запись представляет собой один сеанс, в котором задействовано звуковое сопровождение, звук и видео.</span><span class="sxs-lookup"><span data-stu-id="e48e7-104">Each record represents one session which involves audio or audio and video.</span></span> <span data-ttu-id="e48e7-105">В нем содержатся общие сведения о сеансе.</span><span class="sxs-lookup"><span data-stu-id="e48e7-105">It contains overall information about the session.</span></span> <span data-ttu-id="e48e7-106">Сеанс определяется как диалоговое окно с помощью звукового или видеосигнала (SIP) между двумя конечными точками.</span><span class="sxs-lookup"><span data-stu-id="e48e7-106">A session is defined as an audio or video Session Initiation Protocol (SIP) dialog between two endpoints.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e48e7-107"><strong>Столбец</strong></span><span class="sxs-lookup"><span data-stu-id="e48e7-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="e48e7-108"><strong>Тип данных</strong></span><span class="sxs-lookup"><span data-stu-id="e48e7-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="e48e7-109"><strong>Ключ/индекс</strong></span><span class="sxs-lookup"><span data-stu-id="e48e7-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="e48e7-110"><strong>Сведения</strong></span><span class="sxs-lookup"><span data-stu-id="e48e7-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e48e7-111"><strong>Конференцедатетиме</strong></span><span class="sxs-lookup"><span data-stu-id="e48e7-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e48e7-112">datetime</span><span class="sxs-lookup"><span data-stu-id="e48e7-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="e48e7-113">Primary</span><span class="sxs-lookup"><span data-stu-id="e48e7-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="e48e7-114">Ссылка из <a href="lync-server-2013-dialog-table.md">таблицы диалогов в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="e48e7-114">Referenced from the <a href="lync-server-2013-dialog-table.md">Dialog table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e48e7-115"><strong>Сессионсек</strong></span><span class="sxs-lookup"><span data-stu-id="e48e7-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="e48e7-116">целое</span><span class="sxs-lookup"><span data-stu-id="e48e7-116">int</span></span></p></td>
<td><p><span data-ttu-id="e48e7-117">Primary</span><span class="sxs-lookup"><span data-stu-id="e48e7-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="e48e7-118">Ссылка из <a href="lync-server-2013-dialog-table.md">таблицы диалогов в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="e48e7-118">Referenced from the <a href="lync-server-2013-dialog-table.md">Dialog table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e48e7-119"><strong>Конференцекэй</strong></span><span class="sxs-lookup"><span data-stu-id="e48e7-119"><strong>ConferenceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="e48e7-120">целое</span><span class="sxs-lookup"><span data-stu-id="e48e7-120">int</span></span></p></td>
<td><p><span data-ttu-id="e48e7-121">Другом</span><span class="sxs-lookup"><span data-stu-id="e48e7-121">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e48e7-122">Клавиша Конференции.</span><span class="sxs-lookup"><span data-stu-id="e48e7-122">Conference key.</span></span> <span data-ttu-id="e48e7-123">На которую ссылается <a href="lync-server-2013-conference-table.md">Таблица конференции в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="e48e7-123">Referenced from the <a href="lync-server-2013-conference-table.md">Conference table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e48e7-124"><strong>Коррелатионкэй</strong></span><span class="sxs-lookup"><span data-stu-id="e48e7-124"><strong>CorrelationKey</strong></span></span></p></td>
<td><p><span data-ttu-id="e48e7-125">целое</span><span class="sxs-lookup"><span data-stu-id="e48e7-125">int</span></span></p></td>
<td><p><span data-ttu-id="e48e7-126">Другом</span><span class="sxs-lookup"><span data-stu-id="e48e7-126">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e48e7-127">Ключ корреляции.</span><span class="sxs-lookup"><span data-stu-id="e48e7-127">Correlation key.</span></span> <span data-ttu-id="e48e7-128">На которую ссылается <a href="lync-server-2013-sessioncorrelation-table.md">Таблица сессионкоррелатион в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="e48e7-128">Referenced from the <a href="lync-server-2013-sessioncorrelation-table.md">SessionCorrelation table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e48e7-129"><strong>Диалогкатегори</strong></span><span class="sxs-lookup"><span data-stu-id="e48e7-129"><strong>DialogCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="e48e7-130">бит</span><span class="sxs-lookup"><span data-stu-id="e48e7-130">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e48e7-131">Категория диалогового окна; 0 — это сервер Lync Server для устранения проблем; 1 — это сервер исправлений для шлюза PSTN Gateway.</span><span class="sxs-lookup"><span data-stu-id="e48e7-131">Dialog category; 0 is Lync Server to Mediation Server leg; 1 is Mediation Server to PSTN gateway leg.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e48e7-132"><strong>Медиатионсервербипассфлаг</strong></span><span class="sxs-lookup"><span data-stu-id="e48e7-132"><strong>MediationServerBypassFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="e48e7-133">бит</span><span class="sxs-lookup"><span data-stu-id="e48e7-133">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e48e7-134">Флаг, указывающий, обходит ли звонок.</span><span class="sxs-lookup"><span data-stu-id="e48e7-134">Flag indicating if the call was bypassed or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e48e7-135"><strong>Медиабипассварнингфлаг</strong></span><span class="sxs-lookup"><span data-stu-id="e48e7-135"><strong>MediaBypassWarningFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="e48e7-136">целое</span><span class="sxs-lookup"><span data-stu-id="e48e7-136">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e48e7-137">Это поле, если оно указано, указывает, почему звонок не обходится даже в том случае, если идентификаторы обхода не совпадают.</span><span class="sxs-lookup"><span data-stu-id="e48e7-137">This field, if present, indicates why a call was not bypassed even if the bypass IDs matched.</span></span> <span data-ttu-id="e48e7-138">Для Lync Server определено только одно значение.</span><span class="sxs-lookup"><span data-stu-id="e48e7-138">For Lync Server, only one value is defined.</span></span></p>
<p><span data-ttu-id="e48e7-139">0x0001 — Неизвестный идентификатор обхода для сетевого адаптера по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e48e7-139">0x0001 – Unknown bypass ID for Default network adapter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e48e7-140"><strong>StartTime</strong></span><span class="sxs-lookup"><span data-stu-id="e48e7-140"><strong>StartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e48e7-141">datetime</span><span class="sxs-lookup"><span data-stu-id="e48e7-141">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e48e7-142">Время начала звонка.</span><span class="sxs-lookup"><span data-stu-id="e48e7-142">Call start time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e48e7-143"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="e48e7-143"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e48e7-144">datetime</span><span class="sxs-lookup"><span data-stu-id="e48e7-144">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e48e7-145">Время окончания звонка.</span><span class="sxs-lookup"><span data-stu-id="e48e7-145">Call end time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e48e7-146"><strong>Каллерпул</strong></span><span class="sxs-lookup"><span data-stu-id="e48e7-146"><strong>CallerPool</strong></span></span></p></td>
<td><p><span data-ttu-id="e48e7-147">целое</span><span class="sxs-lookup"><span data-stu-id="e48e7-147">int</span></span></p></td>
<td><p><span data-ttu-id="e48e7-148">Другом</span><span class="sxs-lookup"><span data-stu-id="e48e7-148">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e48e7-149">Пул вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="e48e7-149">The pool of the caller.</span></span> <span data-ttu-id="e48e7-150">Указана <a href="lync-server-2013-pool-table.md">Таблица пула в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="e48e7-150">Referenced from the <a href="lync-server-2013-pool-table.md">Pool table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e48e7-151"><strong>Каллипул</strong></span><span class="sxs-lookup"><span data-stu-id="e48e7-151"><strong>CalleePool</strong></span></span></p></td>
<td><p><span data-ttu-id="e48e7-152">целое</span><span class="sxs-lookup"><span data-stu-id="e48e7-152">int</span></span></p></td>
<td><p><span data-ttu-id="e48e7-153">Другом</span><span class="sxs-lookup"><span data-stu-id="e48e7-153">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e48e7-154">Пул приемника вызова.</span><span class="sxs-lookup"><span data-stu-id="e48e7-154">The pool of the call receiver.</span></span> <span data-ttu-id="e48e7-155">Указана <a href="lync-server-2013-pool-table.md">Таблица пула в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="e48e7-155">Referenced from the <a href="lync-server-2013-pool-table.md">Pool table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e48e7-156"><strong>Каллипаи</strong></span><span class="sxs-lookup"><span data-stu-id="e48e7-156"><strong>CalleePAI</strong></span></span></p></td>
<td><p><span data-ttu-id="e48e7-157">целое</span><span class="sxs-lookup"><span data-stu-id="e48e7-157">int</span></span></p></td>
<td><p><span data-ttu-id="e48e7-158">Другом</span><span class="sxs-lookup"><span data-stu-id="e48e7-158">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e48e7-159">Универсальный код ресурса (URI) SIP в удостоверении SIP (паи) принимающей конечной точки.</span><span class="sxs-lookup"><span data-stu-id="e48e7-159">SIP URI in the SIP p-asserted identity (PAI) of the receiving endpoint.</span></span> <span data-ttu-id="e48e7-160">Ссылка на которую имеется <a href="lync-server-2013-user-table.md">в таблице Users в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="e48e7-160">Referenced from the <a href="lync-server-2013-user-table.md">User table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e48e7-161"><strong>Каллерури</strong></span><span class="sxs-lookup"><span data-stu-id="e48e7-161"><strong>CallerURI</strong></span></span></p></td>
<td><p><span data-ttu-id="e48e7-162">целое</span><span class="sxs-lookup"><span data-stu-id="e48e7-162">int</span></span></p></td>
<td><p><span data-ttu-id="e48e7-163">Другом</span><span class="sxs-lookup"><span data-stu-id="e48e7-163">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e48e7-164">URI вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="e48e7-164">Caller’s URI.</span></span> <span data-ttu-id="e48e7-165">Ссылка на которую имеется <a href="lync-server-2013-user-table.md">в таблице Users в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="e48e7-165">Referenced from the <a href="lync-server-2013-user-table.md">User table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e48e7-166"><strong>Каллерендпоинт</strong></span><span class="sxs-lookup"><span data-stu-id="e48e7-166"><strong>CallerEndpoint</strong></span></span></p></td>
<td><p><span data-ttu-id="e48e7-167">целое</span><span class="sxs-lookup"><span data-stu-id="e48e7-167">int</span></span></p></td>
<td><p><span data-ttu-id="e48e7-168">Другом</span><span class="sxs-lookup"><span data-stu-id="e48e7-168">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e48e7-169">Конечная точка вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="e48e7-169">Caller’s endpoint.</span></span> <span data-ttu-id="e48e7-170">На которую ссылается <a href="lync-server-2013-endpoint-table.md">Таблица конечная точка в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="e48e7-170">Referenced from the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e48e7-171"><strong>Каллерусеражент</strong></span><span class="sxs-lookup"><span data-stu-id="e48e7-171"><strong>CallerUserAgent</strong></span></span></p></td>
<td><p><span data-ttu-id="e48e7-172">бит</span><span class="sxs-lookup"><span data-stu-id="e48e7-172">bit</span></span></p></td>
<td><p><span data-ttu-id="e48e7-173">Другом</span><span class="sxs-lookup"><span data-stu-id="e48e7-173">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e48e7-174">Агент пользователя вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="e48e7-174">Caller’s user agent.</span></span> <span data-ttu-id="e48e7-175">Ссылка из <a href="lync-server-2013-useragent-table.md">таблицы UserAgent в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="e48e7-175">Referenced from the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e48e7-176"><strong>Каллприорити</strong></span><span class="sxs-lookup"><span data-stu-id="e48e7-176"><strong>CallPriority</strong></span></span></p></td>
<td><p><span data-ttu-id="e48e7-177">smallint</span><span class="sxs-lookup"><span data-stu-id="e48e7-177">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e48e7-178">Приоритет этого звонка.</span><span class="sxs-lookup"><span data-stu-id="e48e7-178">The priority of this call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e48e7-179"><strong>Классифиедпуркалл</strong></span><span class="sxs-lookup"><span data-stu-id="e48e7-179"><strong>ClassifiedPoorCall</strong></span></span></p></td>
<td><p><span data-ttu-id="e48e7-180">бит</span><span class="sxs-lookup"><span data-stu-id="e48e7-180">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e48e7-181">Этот столбец устарел и не используется в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e48e7-181">This column has been deprecated and is not used in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="e48e7-182">Вместо этого эти сведения выводятся в виде линий для отдельных носителей.</span><span class="sxs-lookup"><span data-stu-id="e48e7-182">Instead, this information is reported on a per-media line bases.</span></span> <span data-ttu-id="e48e7-183">Дополнительные сведения можно найти в <a href="lync-server-2013-medialine-table.md">таблице медиалине в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e48e7-183">Refer to the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e48e7-184"><strong>Каллерпаи</strong></span><span class="sxs-lookup"><span data-stu-id="e48e7-184"><strong>CallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="e48e7-185">целое</span><span class="sxs-lookup"><span data-stu-id="e48e7-185">int</span></span></p></td>
<td><p><span data-ttu-id="e48e7-186">Другом</span><span class="sxs-lookup"><span data-stu-id="e48e7-186">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e48e7-187">P-утвержденные-идентификационные данные пользователя, который присоединил звонок.</span><span class="sxs-lookup"><span data-stu-id="e48e7-187">P-Asserted-Identity of the user who placed the call.</span></span> <span data-ttu-id="e48e7-188">Идентификатор P-Assert (паи) используется для передачи истинного удостоверения пользователя, который находил звонок.</span><span class="sxs-lookup"><span data-stu-id="e48e7-188">The P-Asserted-Identity (PAI) is used to convey the true identity of the user who placed the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e48e7-189"><strong>Каллиендпоинт</strong></span><span class="sxs-lookup"><span data-stu-id="e48e7-189"><strong>CalleeEndpoint</strong></span></span></p></td>
<td><p><span data-ttu-id="e48e7-190">целое</span><span class="sxs-lookup"><span data-stu-id="e48e7-190">int</span></span></p></td>
<td><p><span data-ttu-id="e48e7-191">Другом</span><span class="sxs-lookup"><span data-stu-id="e48e7-191">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e48e7-192">Конечная точка, в которой был получен звонок.</span><span class="sxs-lookup"><span data-stu-id="e48e7-192">Endpoint that received the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e48e7-193"><strong>Каллиусеражент</strong></span><span class="sxs-lookup"><span data-stu-id="e48e7-193"><strong>CalleeUserAgent</strong></span></span></p></td>
<td><p><span data-ttu-id="e48e7-194">целое</span><span class="sxs-lookup"><span data-stu-id="e48e7-194">int</span></span></p></td>
<td><p><span data-ttu-id="e48e7-195">Другом</span><span class="sxs-lookup"><span data-stu-id="e48e7-195">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e48e7-196">Агент пользователя, который использовался пользователем, который получил звонок.</span><span class="sxs-lookup"><span data-stu-id="e48e7-196">User agent employed by the user who received the call.</span></span> <span data-ttu-id="e48e7-197">Агенты пользователей представляют собой клиентскую конечную точку.</span><span class="sxs-lookup"><span data-stu-id="e48e7-197">User agents represent the client endpoint device.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e48e7-198"><strong>Каллиури</strong></span><span class="sxs-lookup"><span data-stu-id="e48e7-198"><strong>CalleeUri</strong></span></span></p></td>
<td><p><span data-ttu-id="e48e7-199">целое</span><span class="sxs-lookup"><span data-stu-id="e48e7-199">int</span></span></p></td>
<td><p><span data-ttu-id="e48e7-200">Другом</span><span class="sxs-lookup"><span data-stu-id="e48e7-200">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e48e7-201">Универсальный код ресурса (URI) SIP пользователя, который получил звонок.</span><span class="sxs-lookup"><span data-stu-id="e48e7-201">SIP URI of the user who received the call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

