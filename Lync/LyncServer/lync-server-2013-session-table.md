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
ms.openlocfilehash: d74d2732d2f8ad293450f4945eef00bccb9a572d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48510086"
---
# <a name="session-table-in-lync-server-2013"></a><span data-ttu-id="dc1ee-102">Таблица Sessions в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dc1ee-102">Session table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dc1ee-103">_**Последнее изменение темы:** 2013-09-09_</span><span class="sxs-lookup"><span data-stu-id="dc1ee-103">_**Topic Last Modified:** 2013-09-09_</span></span>

<span data-ttu-id="dc1ee-104">Каждая запись представляет один сеанс, который включает звук, аудио и видео.</span><span class="sxs-lookup"><span data-stu-id="dc1ee-104">Each record represents one session which involves audio or audio and video.</span></span> <span data-ttu-id="dc1ee-105">Он содержит общие сведения о сеансе.</span><span class="sxs-lookup"><span data-stu-id="dc1ee-105">It contains overall information about the session.</span></span> <span data-ttu-id="dc1ee-106">Сеанс определяется как диалоговое окно аудио-и видеоинициации (SIP) между двумя конечными точками.</span><span class="sxs-lookup"><span data-stu-id="dc1ee-106">A session is defined as an audio or video Session Initiation Protocol (SIP) dialog between two endpoints.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dc1ee-107"><strong>Column</strong></span><span class="sxs-lookup"><span data-stu-id="dc1ee-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="dc1ee-108"><strong>Тип данных</strong></span><span class="sxs-lookup"><span data-stu-id="dc1ee-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="dc1ee-109"><strong>Ключ или индекс</strong></span><span class="sxs-lookup"><span data-stu-id="dc1ee-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="dc1ee-110"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="dc1ee-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dc1ee-111"><strong>конференцедатетиме</strong></span><span class="sxs-lookup"><span data-stu-id="dc1ee-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="dc1ee-112">datetime</span><span class="sxs-lookup"><span data-stu-id="dc1ee-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="dc1ee-113">Primary</span><span class="sxs-lookup"><span data-stu-id="dc1ee-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="dc1ee-114">Ссылка из <a href="lync-server-2013-dialog-table.md">таблицы диалогов в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="dc1ee-114">Referenced from the <a href="lync-server-2013-dialog-table.md">Dialog table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dc1ee-115"><strong>сессионсек</strong></span><span class="sxs-lookup"><span data-stu-id="dc1ee-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="dc1ee-116">int</span><span class="sxs-lookup"><span data-stu-id="dc1ee-116">int</span></span></p></td>
<td><p><span data-ttu-id="dc1ee-117">Primary</span><span class="sxs-lookup"><span data-stu-id="dc1ee-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="dc1ee-118">Ссылка из <a href="lync-server-2013-dialog-table.md">таблицы диалогов в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="dc1ee-118">Referenced from the <a href="lync-server-2013-dialog-table.md">Dialog table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dc1ee-119"><strong>конференцекэй</strong></span><span class="sxs-lookup"><span data-stu-id="dc1ee-119"><strong>ConferenceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="dc1ee-120">int</span><span class="sxs-lookup"><span data-stu-id="dc1ee-120">int</span></span></p></td>
<td><p><span data-ttu-id="dc1ee-121">Правительства</span><span class="sxs-lookup"><span data-stu-id="dc1ee-121">Foreign</span></span></p></td>
<td><p><span data-ttu-id="dc1ee-122">Ключ конференции.</span><span class="sxs-lookup"><span data-stu-id="dc1ee-122">Conference key.</span></span> <span data-ttu-id="dc1ee-123">Ссылка из <a href="lync-server-2013-conference-table.md">таблицы конференций в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="dc1ee-123">Referenced from the <a href="lync-server-2013-conference-table.md">Conference table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dc1ee-124"><strong>коррелатионкэй</strong></span><span class="sxs-lookup"><span data-stu-id="dc1ee-124"><strong>CorrelationKey</strong></span></span></p></td>
<td><p><span data-ttu-id="dc1ee-125">int</span><span class="sxs-lookup"><span data-stu-id="dc1ee-125">int</span></span></p></td>
<td><p><span data-ttu-id="dc1ee-126">Правительства</span><span class="sxs-lookup"><span data-stu-id="dc1ee-126">Foreign</span></span></p></td>
<td><p><span data-ttu-id="dc1ee-127">Ключ корреляции.</span><span class="sxs-lookup"><span data-stu-id="dc1ee-127">Correlation key.</span></span> <span data-ttu-id="dc1ee-128">Ссылка из <a href="lync-server-2013-sessioncorrelation-table.md">таблицы таблица sessioncorrelation в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="dc1ee-128">Referenced from the <a href="lync-server-2013-sessioncorrelation-table.md">SessionCorrelation table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dc1ee-129"><strong>диалогкатегори</strong></span><span class="sxs-lookup"><span data-stu-id="dc1ee-129"><strong>DialogCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="dc1ee-130">Битовая</span><span class="sxs-lookup"><span data-stu-id="dc1ee-130">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="dc1ee-131">Категория диалоговых окон; 0 — сервер Lync Server — это ветвь сервера-посредника; 1 — сервер-посредник для шлюза PSTN.</span><span class="sxs-lookup"><span data-stu-id="dc1ee-131">Dialog category; 0 is Lync Server to Mediation Server leg; 1 is Mediation Server to PSTN gateway leg.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dc1ee-132"><strong>медиатионсервербипассфлаг</strong></span><span class="sxs-lookup"><span data-stu-id="dc1ee-132"><strong>MediationServerBypassFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="dc1ee-133">Битовая</span><span class="sxs-lookup"><span data-stu-id="dc1ee-133">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dc1ee-134">Флаг, указывающий, выполнял ли вызов обход сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="dc1ee-134">Flag indicating if the call was bypassed or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dc1ee-135"><strong>медиабипассварнингфлаг</strong></span><span class="sxs-lookup"><span data-stu-id="dc1ee-135"><strong>MediaBypassWarningFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="dc1ee-136">int</span><span class="sxs-lookup"><span data-stu-id="dc1ee-136">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dc1ee-137">Если это поле присутствует, оно указывает, почему вызов не может быть обойден, даже если идентификаторы обхода совпадают.</span><span class="sxs-lookup"><span data-stu-id="dc1ee-137">This field, if present, indicates why a call was not bypassed even if the bypass IDs matched.</span></span> <span data-ttu-id="dc1ee-138">Для Lync Server определено только одно значение.</span><span class="sxs-lookup"><span data-stu-id="dc1ee-138">For Lync Server, only one value is defined.</span></span></p>
<p><span data-ttu-id="dc1ee-139">0x0001 — неизвестный идентификатор обхода для сетевого адаптера по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="dc1ee-139">0x0001 – Unknown bypass ID for Default network adapter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dc1ee-140"><strong>StartTime</strong></span><span class="sxs-lookup"><span data-stu-id="dc1ee-140"><strong>StartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="dc1ee-141">datetime</span><span class="sxs-lookup"><span data-stu-id="dc1ee-141">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="dc1ee-142">Время начала вызова.</span><span class="sxs-lookup"><span data-stu-id="dc1ee-142">Call start time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dc1ee-143"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="dc1ee-143"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="dc1ee-144">datetime</span><span class="sxs-lookup"><span data-stu-id="dc1ee-144">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="dc1ee-145">Время окончания вызова.</span><span class="sxs-lookup"><span data-stu-id="dc1ee-145">Call end time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dc1ee-146"><strong>каллерпул</strong></span><span class="sxs-lookup"><span data-stu-id="dc1ee-146"><strong>CallerPool</strong></span></span></p></td>
<td><p><span data-ttu-id="dc1ee-147">int</span><span class="sxs-lookup"><span data-stu-id="dc1ee-147">int</span></span></p></td>
<td><p><span data-ttu-id="dc1ee-148">Правительства</span><span class="sxs-lookup"><span data-stu-id="dc1ee-148">Foreign</span></span></p></td>
<td><p><span data-ttu-id="dc1ee-149">Пул вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="dc1ee-149">The pool of the caller.</span></span> <span data-ttu-id="dc1ee-150">Указан из <a href="lync-server-2013-pool-table.md">таблицы пула в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="dc1ee-150">Referenced from the <a href="lync-server-2013-pool-table.md">Pool table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dc1ee-151"><strong>каллипул</strong></span><span class="sxs-lookup"><span data-stu-id="dc1ee-151"><strong>CalleePool</strong></span></span></p></td>
<td><p><span data-ttu-id="dc1ee-152">int</span><span class="sxs-lookup"><span data-stu-id="dc1ee-152">int</span></span></p></td>
<td><p><span data-ttu-id="dc1ee-153">Правительства</span><span class="sxs-lookup"><span data-stu-id="dc1ee-153">Foreign</span></span></p></td>
<td><p><span data-ttu-id="dc1ee-154">Пул приемника вызовов.</span><span class="sxs-lookup"><span data-stu-id="dc1ee-154">The pool of the call receiver.</span></span> <span data-ttu-id="dc1ee-155">Указан из <a href="lync-server-2013-pool-table.md">таблицы пула в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="dc1ee-155">Referenced from the <a href="lync-server-2013-pool-table.md">Pool table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dc1ee-156"><strong>каллипаи</strong></span><span class="sxs-lookup"><span data-stu-id="dc1ee-156"><strong>CalleePAI</strong></span></span></p></td>
<td><p><span data-ttu-id="dc1ee-157">int</span><span class="sxs-lookup"><span data-stu-id="dc1ee-157">int</span></span></p></td>
<td><p><span data-ttu-id="dc1ee-158">Правительства</span><span class="sxs-lookup"><span data-stu-id="dc1ee-158">Foreign</span></span></p></td>
<td><p><span data-ttu-id="dc1ee-159">Универсальный код ресурса (URI) SIP в удостоверении (PAI) принимающей конечной точки.</span><span class="sxs-lookup"><span data-stu-id="dc1ee-159">SIP URI in the SIP p-asserted identity (PAI) of the receiving endpoint.</span></span> <span data-ttu-id="dc1ee-160">Ссылка из <a href="lync-server-2013-user-table.md">таблицы Users в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="dc1ee-160">Referenced from the <a href="lync-server-2013-user-table.md">User table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dc1ee-161"><strong>каллерури</strong></span><span class="sxs-lookup"><span data-stu-id="dc1ee-161"><strong>CallerURI</strong></span></span></p></td>
<td><p><span data-ttu-id="dc1ee-162">int</span><span class="sxs-lookup"><span data-stu-id="dc1ee-162">int</span></span></p></td>
<td><p><span data-ttu-id="dc1ee-163">Правительства</span><span class="sxs-lookup"><span data-stu-id="dc1ee-163">Foreign</span></span></p></td>
<td><p><span data-ttu-id="dc1ee-164">URI вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="dc1ee-164">Caller’s URI.</span></span> <span data-ttu-id="dc1ee-165">Ссылка из <a href="lync-server-2013-user-table.md">таблицы Users в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="dc1ee-165">Referenced from the <a href="lync-server-2013-user-table.md">User table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dc1ee-166"><strong>каллерендпоинт</strong></span><span class="sxs-lookup"><span data-stu-id="dc1ee-166"><strong>CallerEndpoint</strong></span></span></p></td>
<td><p><span data-ttu-id="dc1ee-167">int</span><span class="sxs-lookup"><span data-stu-id="dc1ee-167">int</span></span></p></td>
<td><p><span data-ttu-id="dc1ee-168">Правительства</span><span class="sxs-lookup"><span data-stu-id="dc1ee-168">Foreign</span></span></p></td>
<td><p><span data-ttu-id="dc1ee-169">Конечная точка вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="dc1ee-169">Caller’s endpoint.</span></span> <span data-ttu-id="dc1ee-170">Указана в <a href="lync-server-2013-endpoint-table.md">таблице конечная точка в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="dc1ee-170">Referenced from the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dc1ee-171"><strong>каллерусеражент</strong></span><span class="sxs-lookup"><span data-stu-id="dc1ee-171"><strong>CallerUserAgent</strong></span></span></p></td>
<td><p><span data-ttu-id="dc1ee-172">Битовая</span><span class="sxs-lookup"><span data-stu-id="dc1ee-172">bit</span></span></p></td>
<td><p><span data-ttu-id="dc1ee-173">Правительства</span><span class="sxs-lookup"><span data-stu-id="dc1ee-173">Foreign</span></span></p></td>
<td><p><span data-ttu-id="dc1ee-174">Агент пользователя вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="dc1ee-174">Caller’s user agent.</span></span> <span data-ttu-id="dc1ee-175">Ссылка из <a href="lync-server-2013-useragent-table.md">таблицы UserAgent в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="dc1ee-175">Referenced from the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dc1ee-176"><strong>каллприорити</strong></span><span class="sxs-lookup"><span data-stu-id="dc1ee-176"><strong>CallPriority</strong></span></span></p></td>
<td><p><span data-ttu-id="dc1ee-177">smallint</span><span class="sxs-lookup"><span data-stu-id="dc1ee-177">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dc1ee-178">Приоритет этого вызова.</span><span class="sxs-lookup"><span data-stu-id="dc1ee-178">The priority of this call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dc1ee-179"><strong>классифиедпуркалл</strong></span><span class="sxs-lookup"><span data-stu-id="dc1ee-179"><strong>ClassifiedPoorCall</strong></span></span></p></td>
<td><p><span data-ttu-id="dc1ee-180">Битовая</span><span class="sxs-lookup"><span data-stu-id="dc1ee-180">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dc1ee-181">Этот столбец устарел и не используется в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="dc1ee-181">This column has been deprecated and is not used in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="dc1ee-182">Вместо этого эти сведения выводятся на основе линий отдельных носителей.</span><span class="sxs-lookup"><span data-stu-id="dc1ee-182">Instead, this information is reported on a per-media line bases.</span></span> <span data-ttu-id="dc1ee-183">Для получения дополнительных сведений обратитесь к <a href="lync-server-2013-medialine-table.md">таблице MediaLine в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="dc1ee-183">Refer to the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dc1ee-184"><strong>каллерпаи</strong></span><span class="sxs-lookup"><span data-stu-id="dc1ee-184"><strong>CallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="dc1ee-185">int</span><span class="sxs-lookup"><span data-stu-id="dc1ee-185">int</span></span></p></td>
<td><p><span data-ttu-id="dc1ee-186">Правительства</span><span class="sxs-lookup"><span data-stu-id="dc1ee-186">Foreign</span></span></p></td>
<td><p><span data-ttu-id="dc1ee-187">P — утверждено — идентификатор пользователя, который поместил вызов.</span><span class="sxs-lookup"><span data-stu-id="dc1ee-187">P-Asserted-Identity of the user who placed the call.</span></span> <span data-ttu-id="dc1ee-188">P-Assert-Identity (PAI) используется для передачи истинного удостоверения пользователя, который поместил вызов.</span><span class="sxs-lookup"><span data-stu-id="dc1ee-188">The P-Asserted-Identity (PAI) is used to convey the true identity of the user who placed the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dc1ee-189"><strong>каллиендпоинт</strong></span><span class="sxs-lookup"><span data-stu-id="dc1ee-189"><strong>CalleeEndpoint</strong></span></span></p></td>
<td><p><span data-ttu-id="dc1ee-190">int</span><span class="sxs-lookup"><span data-stu-id="dc1ee-190">int</span></span></p></td>
<td><p><span data-ttu-id="dc1ee-191">Правительства</span><span class="sxs-lookup"><span data-stu-id="dc1ee-191">Foreign</span></span></p></td>
<td><p><span data-ttu-id="dc1ee-192">Конечная точка, в которой был получен вызов.</span><span class="sxs-lookup"><span data-stu-id="dc1ee-192">Endpoint that received the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dc1ee-193"><strong>каллиусеражент</strong></span><span class="sxs-lookup"><span data-stu-id="dc1ee-193"><strong>CalleeUserAgent</strong></span></span></p></td>
<td><p><span data-ttu-id="dc1ee-194">int</span><span class="sxs-lookup"><span data-stu-id="dc1ee-194">int</span></span></p></td>
<td><p><span data-ttu-id="dc1ee-195">Правительства</span><span class="sxs-lookup"><span data-stu-id="dc1ee-195">Foreign</span></span></p></td>
<td><p><span data-ttu-id="dc1ee-196">Агент пользователя, который использовался пользователем, получившим вызов.</span><span class="sxs-lookup"><span data-stu-id="dc1ee-196">User agent employed by the user who received the call.</span></span> <span data-ttu-id="dc1ee-197">Агенты пользователей представляют устройство конечной точки клиента.</span><span class="sxs-lookup"><span data-stu-id="dc1ee-197">User agents represent the client endpoint device.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dc1ee-198"><strong>каллиури</strong></span><span class="sxs-lookup"><span data-stu-id="dc1ee-198"><strong>CalleeUri</strong></span></span></p></td>
<td><p><span data-ttu-id="dc1ee-199">int</span><span class="sxs-lookup"><span data-stu-id="dc1ee-199">int</span></span></p></td>
<td><p><span data-ttu-id="dc1ee-200">Правительства</span><span class="sxs-lookup"><span data-stu-id="dc1ee-200">Foreign</span></span></p></td>
<td><p><span data-ttu-id="dc1ee-201">Универсальный код ресурса (URI) SIP пользователя, который получил вызов.</span><span class="sxs-lookup"><span data-stu-id="dc1ee-201">SIP URI of the user who received the call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

