---
title: 'Lync Server 2013: таблица Session'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Session table
ms:assetid: 7f05529c-794d-41ed-bca4-2e85b87b2dec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398635(v=OCS.15)
ms:contentKeyID: 48184626
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 81b97d6a7521add62817147ae87995508b841f2d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732399"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="session-table-in-lync-server-2013"></a><span data-ttu-id="17a87-102">Таблица Session в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="17a87-102">Session table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="17a87-103">_**Тема последнего изменения:** 2013-09-09_</span><span class="sxs-lookup"><span data-stu-id="17a87-103">_**Topic Last Modified:** 2013-09-09_</span></span>

<span data-ttu-id="17a87-104">Каждая запись представляет собой один сеанс, в котором задействовано звуковое сопровождение, звук и видео.</span><span class="sxs-lookup"><span data-stu-id="17a87-104">Each record represents one session which involves audio or audio and video.</span></span> <span data-ttu-id="17a87-105">В нем содержатся общие сведения о сеансе.</span><span class="sxs-lookup"><span data-stu-id="17a87-105">It contains overall information about the session.</span></span> <span data-ttu-id="17a87-106">Сеанс определяется как диалоговое окно с помощью звукового или видеосигнала (SIP) между двумя конечными точками.</span><span class="sxs-lookup"><span data-stu-id="17a87-106">A session is defined as an audio or video Session Initiation Protocol (SIP) dialog between two endpoints.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="17a87-107"><strong>Столбец</strong></span><span class="sxs-lookup"><span data-stu-id="17a87-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="17a87-108"><strong>Тип данных</strong></span><span class="sxs-lookup"><span data-stu-id="17a87-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="17a87-109"><strong>Ключ/индекс</strong></span><span class="sxs-lookup"><span data-stu-id="17a87-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="17a87-110"><strong>Сведения</strong></span><span class="sxs-lookup"><span data-stu-id="17a87-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="17a87-111"><strong>конференцедатетиме</strong></span><span class="sxs-lookup"><span data-stu-id="17a87-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="17a87-112">datetime</span><span class="sxs-lookup"><span data-stu-id="17a87-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="17a87-113">Primary</span><span class="sxs-lookup"><span data-stu-id="17a87-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="17a87-114">Ссылка из <a href="lync-server-2013-dialog-table.md">таблицы диалогов в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="17a87-114">Referenced from the <a href="lync-server-2013-dialog-table.md">Dialog table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17a87-115"><strong>сессионсек</strong></span><span class="sxs-lookup"><span data-stu-id="17a87-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="17a87-116">целое</span><span class="sxs-lookup"><span data-stu-id="17a87-116">int</span></span></p></td>
<td><p><span data-ttu-id="17a87-117">Primary</span><span class="sxs-lookup"><span data-stu-id="17a87-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="17a87-118">Ссылка из <a href="lync-server-2013-dialog-table.md">таблицы диалогов в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="17a87-118">Referenced from the <a href="lync-server-2013-dialog-table.md">Dialog table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="17a87-119"><strong>конференцекэй</strong></span><span class="sxs-lookup"><span data-stu-id="17a87-119"><strong>ConferenceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="17a87-120">целое</span><span class="sxs-lookup"><span data-stu-id="17a87-120">int</span></span></p></td>
<td><p><span data-ttu-id="17a87-121">Другом</span><span class="sxs-lookup"><span data-stu-id="17a87-121">Foreign</span></span></p></td>
<td><p><span data-ttu-id="17a87-122">Клавиша Конференции.</span><span class="sxs-lookup"><span data-stu-id="17a87-122">Conference key.</span></span> <span data-ttu-id="17a87-123">На которую ссылается <a href="lync-server-2013-conference-table.md">Таблица конференции в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="17a87-123">Referenced from the <a href="lync-server-2013-conference-table.md">Conference table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17a87-124"><strong>коррелатионкэй</strong></span><span class="sxs-lookup"><span data-stu-id="17a87-124"><strong>CorrelationKey</strong></span></span></p></td>
<td><p><span data-ttu-id="17a87-125">целое</span><span class="sxs-lookup"><span data-stu-id="17a87-125">int</span></span></p></td>
<td><p><span data-ttu-id="17a87-126">Другом</span><span class="sxs-lookup"><span data-stu-id="17a87-126">Foreign</span></span></p></td>
<td><p><span data-ttu-id="17a87-127">Ключ корреляции.</span><span class="sxs-lookup"><span data-stu-id="17a87-127">Correlation key.</span></span> <span data-ttu-id="17a87-128">На которую ссылается <a href="lync-server-2013-sessioncorrelation-table.md">Таблица сессионкоррелатион в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="17a87-128">Referenced from the <a href="lync-server-2013-sessioncorrelation-table.md">SessionCorrelation table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="17a87-129"><strong>диалогкатегори</strong></span><span class="sxs-lookup"><span data-stu-id="17a87-129"><strong>DialogCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="17a87-130">бит</span><span class="sxs-lookup"><span data-stu-id="17a87-130">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="17a87-131">Категория диалогового окна; 0 — это сервер Lync Server для устранения проблем; 1 — это сервер исправлений для шлюза PSTN Gateway.</span><span class="sxs-lookup"><span data-stu-id="17a87-131">Dialog category; 0 is Lync Server to Mediation Server leg; 1 is Mediation Server to PSTN gateway leg.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17a87-132"><strong>медиатионсервербипассфлаг</strong></span><span class="sxs-lookup"><span data-stu-id="17a87-132"><strong>MediationServerBypassFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="17a87-133">бит</span><span class="sxs-lookup"><span data-stu-id="17a87-133">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="17a87-134">Флаг, указывающий, обходит ли звонок.</span><span class="sxs-lookup"><span data-stu-id="17a87-134">Flag indicating if the call was bypassed or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="17a87-135"><strong>медиабипассварнингфлаг</strong></span><span class="sxs-lookup"><span data-stu-id="17a87-135"><strong>MediaBypassWarningFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="17a87-136">целое</span><span class="sxs-lookup"><span data-stu-id="17a87-136">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="17a87-137">Это поле, если оно указано, указывает, почему звонок не обходится даже в том случае, если идентификаторы обхода не совпадают.</span><span class="sxs-lookup"><span data-stu-id="17a87-137">This field, if present, indicates why a call was not bypassed even if the bypass IDs matched.</span></span> <span data-ttu-id="17a87-138">Для Lync Server определено только одно значение.</span><span class="sxs-lookup"><span data-stu-id="17a87-138">For Lync Server, only one value is defined.</span></span></p>
<p><span data-ttu-id="17a87-139">0x0001 — Неизвестный идентификатор обхода для сетевого адаптера по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="17a87-139">0x0001 – Unknown bypass ID for Default network adapter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17a87-140"><strong>StartTime</strong></span><span class="sxs-lookup"><span data-stu-id="17a87-140"><strong>StartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="17a87-141">datetime</span><span class="sxs-lookup"><span data-stu-id="17a87-141">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="17a87-142">Время начала звонка.</span><span class="sxs-lookup"><span data-stu-id="17a87-142">Call start time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="17a87-143"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="17a87-143"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="17a87-144">datetime</span><span class="sxs-lookup"><span data-stu-id="17a87-144">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="17a87-145">Время окончания звонка.</span><span class="sxs-lookup"><span data-stu-id="17a87-145">Call end time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17a87-146"><strong>каллерпул</strong></span><span class="sxs-lookup"><span data-stu-id="17a87-146"><strong>CallerPool</strong></span></span></p></td>
<td><p><span data-ttu-id="17a87-147">целое</span><span class="sxs-lookup"><span data-stu-id="17a87-147">int</span></span></p></td>
<td><p><span data-ttu-id="17a87-148">Другом</span><span class="sxs-lookup"><span data-stu-id="17a87-148">Foreign</span></span></p></td>
<td><p><span data-ttu-id="17a87-149">Пул вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="17a87-149">The pool of the caller.</span></span> <span data-ttu-id="17a87-150">Указана <a href="lync-server-2013-pool-table.md">Таблица пула в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="17a87-150">Referenced from the <a href="lync-server-2013-pool-table.md">Pool table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="17a87-151"><strong>каллипул</strong></span><span class="sxs-lookup"><span data-stu-id="17a87-151"><strong>CalleePool</strong></span></span></p></td>
<td><p><span data-ttu-id="17a87-152">целое</span><span class="sxs-lookup"><span data-stu-id="17a87-152">int</span></span></p></td>
<td><p><span data-ttu-id="17a87-153">Другом</span><span class="sxs-lookup"><span data-stu-id="17a87-153">Foreign</span></span></p></td>
<td><p><span data-ttu-id="17a87-154">Пул приемника вызова.</span><span class="sxs-lookup"><span data-stu-id="17a87-154">The pool of the call receiver.</span></span> <span data-ttu-id="17a87-155">Указана <a href="lync-server-2013-pool-table.md">Таблица пула в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="17a87-155">Referenced from the <a href="lync-server-2013-pool-table.md">Pool table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17a87-156"><strong>каллипаи</strong></span><span class="sxs-lookup"><span data-stu-id="17a87-156"><strong>CalleePAI</strong></span></span></p></td>
<td><p><span data-ttu-id="17a87-157">целое</span><span class="sxs-lookup"><span data-stu-id="17a87-157">int</span></span></p></td>
<td><p><span data-ttu-id="17a87-158">Другом</span><span class="sxs-lookup"><span data-stu-id="17a87-158">Foreign</span></span></p></td>
<td><p><span data-ttu-id="17a87-159">Универсальный код ресурса (URI) SIP в удостоверении SIP (паи) принимающей конечной точки.</span><span class="sxs-lookup"><span data-stu-id="17a87-159">SIP URI in the SIP p-asserted identity (PAI) of the receiving endpoint.</span></span> <span data-ttu-id="17a87-160">Ссылка на которую имеется <a href="lync-server-2013-user-table.md">в таблице Users в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="17a87-160">Referenced from the <a href="lync-server-2013-user-table.md">User table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="17a87-161"><strong>каллерури</strong></span><span class="sxs-lookup"><span data-stu-id="17a87-161"><strong>CallerURI</strong></span></span></p></td>
<td><p><span data-ttu-id="17a87-162">целое</span><span class="sxs-lookup"><span data-stu-id="17a87-162">int</span></span></p></td>
<td><p><span data-ttu-id="17a87-163">Другом</span><span class="sxs-lookup"><span data-stu-id="17a87-163">Foreign</span></span></p></td>
<td><p><span data-ttu-id="17a87-164">URI вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="17a87-164">Caller’s URI.</span></span> <span data-ttu-id="17a87-165">Ссылка на которую имеется <a href="lync-server-2013-user-table.md">в таблице Users в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="17a87-165">Referenced from the <a href="lync-server-2013-user-table.md">User table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17a87-166"><strong>каллерендпоинт</strong></span><span class="sxs-lookup"><span data-stu-id="17a87-166"><strong>CallerEndpoint</strong></span></span></p></td>
<td><p><span data-ttu-id="17a87-167">целое</span><span class="sxs-lookup"><span data-stu-id="17a87-167">int</span></span></p></td>
<td><p><span data-ttu-id="17a87-168">Другом</span><span class="sxs-lookup"><span data-stu-id="17a87-168">Foreign</span></span></p></td>
<td><p><span data-ttu-id="17a87-169">Конечная точка вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="17a87-169">Caller’s endpoint.</span></span> <span data-ttu-id="17a87-170">На которую ссылается <a href="lync-server-2013-endpoint-table.md">Таблица конечная точка в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="17a87-170">Referenced from the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="17a87-171"><strong>каллерусеражент</strong></span><span class="sxs-lookup"><span data-stu-id="17a87-171"><strong>CallerUserAgent</strong></span></span></p></td>
<td><p><span data-ttu-id="17a87-172">бит</span><span class="sxs-lookup"><span data-stu-id="17a87-172">bit</span></span></p></td>
<td><p><span data-ttu-id="17a87-173">Другом</span><span class="sxs-lookup"><span data-stu-id="17a87-173">Foreign</span></span></p></td>
<td><p><span data-ttu-id="17a87-174">Агент пользователя вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="17a87-174">Caller’s user agent.</span></span> <span data-ttu-id="17a87-175">Ссылка из <a href="lync-server-2013-useragent-table.md">таблицы UserAgent в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="17a87-175">Referenced from the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17a87-176"><strong>каллприорити</strong></span><span class="sxs-lookup"><span data-stu-id="17a87-176"><strong>CallPriority</strong></span></span></p></td>
<td><p><span data-ttu-id="17a87-177">smallint</span><span class="sxs-lookup"><span data-stu-id="17a87-177">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="17a87-178">Приоритет этого звонка.</span><span class="sxs-lookup"><span data-stu-id="17a87-178">The priority of this call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="17a87-179"><strong>классифиедпуркалл</strong></span><span class="sxs-lookup"><span data-stu-id="17a87-179"><strong>ClassifiedPoorCall</strong></span></span></p></td>
<td><p><span data-ttu-id="17a87-180">бит</span><span class="sxs-lookup"><span data-stu-id="17a87-180">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="17a87-181">Этот столбец устарел и не используется в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="17a87-181">This column has been deprecated and is not used in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="17a87-182">Вместо этого эти сведения выводятся в виде линий для отдельных носителей.</span><span class="sxs-lookup"><span data-stu-id="17a87-182">Instead, this information is reported on a per-media line bases.</span></span> <span data-ttu-id="17a87-183">Дополнительные сведения можно найти в <a href="lync-server-2013-medialine-table.md">таблице медиалине в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="17a87-183">Refer to the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17a87-184"><strong>каллерпаи</strong></span><span class="sxs-lookup"><span data-stu-id="17a87-184"><strong>CallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="17a87-185">целое</span><span class="sxs-lookup"><span data-stu-id="17a87-185">int</span></span></p></td>
<td><p><span data-ttu-id="17a87-186">Другом</span><span class="sxs-lookup"><span data-stu-id="17a87-186">Foreign</span></span></p></td>
<td><p><span data-ttu-id="17a87-187">P-утвержденные-идентификационные данные пользователя, который присоединил звонок.</span><span class="sxs-lookup"><span data-stu-id="17a87-187">P-Asserted-Identity of the user who placed the call.</span></span> <span data-ttu-id="17a87-188">Идентификатор P-Assert (паи) используется для передачи истинного удостоверения пользователя, который находил звонок.</span><span class="sxs-lookup"><span data-stu-id="17a87-188">The P-Asserted-Identity (PAI) is used to convey the true identity of the user who placed the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="17a87-189"><strong>каллиендпоинт</strong></span><span class="sxs-lookup"><span data-stu-id="17a87-189"><strong>CalleeEndpoint</strong></span></span></p></td>
<td><p><span data-ttu-id="17a87-190">целое</span><span class="sxs-lookup"><span data-stu-id="17a87-190">int</span></span></p></td>
<td><p><span data-ttu-id="17a87-191">Другом</span><span class="sxs-lookup"><span data-stu-id="17a87-191">Foreign</span></span></p></td>
<td><p><span data-ttu-id="17a87-192">Конечная точка, в которой был получен звонок.</span><span class="sxs-lookup"><span data-stu-id="17a87-192">Endpoint that received the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17a87-193"><strong>каллиусеражент</strong></span><span class="sxs-lookup"><span data-stu-id="17a87-193"><strong>CalleeUserAgent</strong></span></span></p></td>
<td><p><span data-ttu-id="17a87-194">целое</span><span class="sxs-lookup"><span data-stu-id="17a87-194">int</span></span></p></td>
<td><p><span data-ttu-id="17a87-195">Другом</span><span class="sxs-lookup"><span data-stu-id="17a87-195">Foreign</span></span></p></td>
<td><p><span data-ttu-id="17a87-196">Агент пользователя, который использовался пользователем, который получил звонок.</span><span class="sxs-lookup"><span data-stu-id="17a87-196">User agent employed by the user who received the call.</span></span> <span data-ttu-id="17a87-197">Агенты пользователей представляют собой клиентскую конечную точку.</span><span class="sxs-lookup"><span data-stu-id="17a87-197">User agents represent the client endpoint device.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="17a87-198"><strong>каллиури</strong></span><span class="sxs-lookup"><span data-stu-id="17a87-198"><strong>CalleeUri</strong></span></span></p></td>
<td><p><span data-ttu-id="17a87-199">целое</span><span class="sxs-lookup"><span data-stu-id="17a87-199">int</span></span></p></td>
<td><p><span data-ttu-id="17a87-200">Другом</span><span class="sxs-lookup"><span data-stu-id="17a87-200">Foreign</span></span></p></td>
<td><p><span data-ttu-id="17a87-201">Универсальный код ресурса (URI) SIP пользователя, который получил звонок.</span><span class="sxs-lookup"><span data-stu-id="17a87-201">SIP URI of the user who received the call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

