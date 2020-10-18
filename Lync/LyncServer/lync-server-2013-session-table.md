---
title: 'Lync Server 2013: таблица Session'
description: 'Lync Server 2013: таблица Session.'
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
ms.openlocfilehash: e1a52813dfea808253cc934f71a9d4c846c2dbbd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576455"
---
# <a name="session-table-in-lync-server-2013"></a><span data-ttu-id="d963e-103">Таблица Sessions в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d963e-103">Session table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d963e-104">_**Последнее изменение темы:** 2013-09-09_</span><span class="sxs-lookup"><span data-stu-id="d963e-104">_**Topic Last Modified:** 2013-09-09_</span></span>

<span data-ttu-id="d963e-105">Каждая запись представляет один сеанс, который включает звук, аудио и видео.</span><span class="sxs-lookup"><span data-stu-id="d963e-105">Each record represents one session which involves audio or audio and video.</span></span> <span data-ttu-id="d963e-106">Он содержит общие сведения о сеансе.</span><span class="sxs-lookup"><span data-stu-id="d963e-106">It contains overall information about the session.</span></span> <span data-ttu-id="d963e-107">Сеанс определяется как диалоговое окно аудио-и видеоинициации (SIP) между двумя конечными точками.</span><span class="sxs-lookup"><span data-stu-id="d963e-107">A session is defined as an audio or video Session Initiation Protocol (SIP) dialog between two endpoints.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d963e-108"><strong>Column</strong></span><span class="sxs-lookup"><span data-stu-id="d963e-108"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="d963e-109"><strong>Тип данных</strong></span><span class="sxs-lookup"><span data-stu-id="d963e-109"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="d963e-110"><strong>Ключ или индекс</strong></span><span class="sxs-lookup"><span data-stu-id="d963e-110"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="d963e-111"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="d963e-111"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d963e-112"><strong>конференцедатетиме</strong></span><span class="sxs-lookup"><span data-stu-id="d963e-112"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="d963e-113">datetime</span><span class="sxs-lookup"><span data-stu-id="d963e-113">datetime</span></span></p></td>
<td><p><span data-ttu-id="d963e-114">Primary</span><span class="sxs-lookup"><span data-stu-id="d963e-114">Primary</span></span></p></td>
<td><p><span data-ttu-id="d963e-115">Ссылка из <a href="lync-server-2013-dialog-table.md">таблицы диалогов в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="d963e-115">Referenced from the <a href="lync-server-2013-dialog-table.md">Dialog table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d963e-116"><strong>сессионсек</strong></span><span class="sxs-lookup"><span data-stu-id="d963e-116"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="d963e-117">int</span><span class="sxs-lookup"><span data-stu-id="d963e-117">int</span></span></p></td>
<td><p><span data-ttu-id="d963e-118">Primary</span><span class="sxs-lookup"><span data-stu-id="d963e-118">Primary</span></span></p></td>
<td><p><span data-ttu-id="d963e-119">Ссылка из <a href="lync-server-2013-dialog-table.md">таблицы диалогов в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="d963e-119">Referenced from the <a href="lync-server-2013-dialog-table.md">Dialog table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d963e-120"><strong>конференцекэй</strong></span><span class="sxs-lookup"><span data-stu-id="d963e-120"><strong>ConferenceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="d963e-121">int</span><span class="sxs-lookup"><span data-stu-id="d963e-121">int</span></span></p></td>
<td><p><span data-ttu-id="d963e-122">Правительства</span><span class="sxs-lookup"><span data-stu-id="d963e-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d963e-123">Ключ конференции.</span><span class="sxs-lookup"><span data-stu-id="d963e-123">Conference key.</span></span> <span data-ttu-id="d963e-124">Ссылка из <a href="lync-server-2013-conference-table.md">таблицы конференций в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="d963e-124">Referenced from the <a href="lync-server-2013-conference-table.md">Conference table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d963e-125"><strong>коррелатионкэй</strong></span><span class="sxs-lookup"><span data-stu-id="d963e-125"><strong>CorrelationKey</strong></span></span></p></td>
<td><p><span data-ttu-id="d963e-126">int</span><span class="sxs-lookup"><span data-stu-id="d963e-126">int</span></span></p></td>
<td><p><span data-ttu-id="d963e-127">Правительства</span><span class="sxs-lookup"><span data-stu-id="d963e-127">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d963e-128">Ключ корреляции.</span><span class="sxs-lookup"><span data-stu-id="d963e-128">Correlation key.</span></span> <span data-ttu-id="d963e-129">Ссылка из <a href="lync-server-2013-sessioncorrelation-table.md">таблицы таблица sessioncorrelation в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="d963e-129">Referenced from the <a href="lync-server-2013-sessioncorrelation-table.md">SessionCorrelation table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d963e-130"><strong>диалогкатегори</strong></span><span class="sxs-lookup"><span data-stu-id="d963e-130"><strong>DialogCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="d963e-131">Битовая</span><span class="sxs-lookup"><span data-stu-id="d963e-131">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d963e-132">Категория диалоговых окон; 0 — сервер Lync Server — это ветвь сервера-посредника; 1 — сервер-посредник для шлюза PSTN.</span><span class="sxs-lookup"><span data-stu-id="d963e-132">Dialog category; 0 is Lync Server to Mediation Server leg; 1 is Mediation Server to PSTN gateway leg.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d963e-133"><strong>медиатионсервербипассфлаг</strong></span><span class="sxs-lookup"><span data-stu-id="d963e-133"><strong>MediationServerBypassFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="d963e-134">Битовая</span><span class="sxs-lookup"><span data-stu-id="d963e-134">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d963e-135">Флаг, указывающий, выполнял ли вызов обход сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="d963e-135">Flag indicating if the call was bypassed or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d963e-136"><strong>медиабипассварнингфлаг</strong></span><span class="sxs-lookup"><span data-stu-id="d963e-136"><strong>MediaBypassWarningFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="d963e-137">int</span><span class="sxs-lookup"><span data-stu-id="d963e-137">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d963e-138">Если это поле присутствует, оно указывает, почему вызов не может быть обойден, даже если идентификаторы обхода совпадают.</span><span class="sxs-lookup"><span data-stu-id="d963e-138">This field, if present, indicates why a call was not bypassed even if the bypass IDs matched.</span></span> <span data-ttu-id="d963e-139">Для Lync Server определено только одно значение.</span><span class="sxs-lookup"><span data-stu-id="d963e-139">For Lync Server, only one value is defined.</span></span></p>
<p><span data-ttu-id="d963e-140">0x0001 — неизвестный идентификатор обхода для сетевого адаптера по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d963e-140">0x0001 – Unknown bypass ID for Default network adapter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d963e-141"><strong>StartTime</strong></span><span class="sxs-lookup"><span data-stu-id="d963e-141"><strong>StartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="d963e-142">datetime</span><span class="sxs-lookup"><span data-stu-id="d963e-142">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d963e-143">Время начала вызова.</span><span class="sxs-lookup"><span data-stu-id="d963e-143">Call start time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d963e-144"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="d963e-144"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="d963e-145">datetime</span><span class="sxs-lookup"><span data-stu-id="d963e-145">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d963e-146">Время окончания вызова.</span><span class="sxs-lookup"><span data-stu-id="d963e-146">Call end time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d963e-147"><strong>каллерпул</strong></span><span class="sxs-lookup"><span data-stu-id="d963e-147"><strong>CallerPool</strong></span></span></p></td>
<td><p><span data-ttu-id="d963e-148">int</span><span class="sxs-lookup"><span data-stu-id="d963e-148">int</span></span></p></td>
<td><p><span data-ttu-id="d963e-149">Правительства</span><span class="sxs-lookup"><span data-stu-id="d963e-149">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d963e-150">Пул вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="d963e-150">The pool of the caller.</span></span> <span data-ttu-id="d963e-151">Указан из <a href="lync-server-2013-pool-table.md">таблицы пула в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="d963e-151">Referenced from the <a href="lync-server-2013-pool-table.md">Pool table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d963e-152"><strong>каллипул</strong></span><span class="sxs-lookup"><span data-stu-id="d963e-152"><strong>CalleePool</strong></span></span></p></td>
<td><p><span data-ttu-id="d963e-153">int</span><span class="sxs-lookup"><span data-stu-id="d963e-153">int</span></span></p></td>
<td><p><span data-ttu-id="d963e-154">Правительства</span><span class="sxs-lookup"><span data-stu-id="d963e-154">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d963e-155">Пул приемника вызовов.</span><span class="sxs-lookup"><span data-stu-id="d963e-155">The pool of the call receiver.</span></span> <span data-ttu-id="d963e-156">Указан из <a href="lync-server-2013-pool-table.md">таблицы пула в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="d963e-156">Referenced from the <a href="lync-server-2013-pool-table.md">Pool table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d963e-157"><strong>каллипаи</strong></span><span class="sxs-lookup"><span data-stu-id="d963e-157"><strong>CalleePAI</strong></span></span></p></td>
<td><p><span data-ttu-id="d963e-158">int</span><span class="sxs-lookup"><span data-stu-id="d963e-158">int</span></span></p></td>
<td><p><span data-ttu-id="d963e-159">Правительства</span><span class="sxs-lookup"><span data-stu-id="d963e-159">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d963e-160">Универсальный код ресурса (URI) SIP в удостоверении (PAI) принимающей конечной точки.</span><span class="sxs-lookup"><span data-stu-id="d963e-160">SIP URI in the SIP p-asserted identity (PAI) of the receiving endpoint.</span></span> <span data-ttu-id="d963e-161">Ссылка из <a href="lync-server-2013-user-table.md">таблицы Users в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="d963e-161">Referenced from the <a href="lync-server-2013-user-table.md">User table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d963e-162"><strong>каллерури</strong></span><span class="sxs-lookup"><span data-stu-id="d963e-162"><strong>CallerURI</strong></span></span></p></td>
<td><p><span data-ttu-id="d963e-163">int</span><span class="sxs-lookup"><span data-stu-id="d963e-163">int</span></span></p></td>
<td><p><span data-ttu-id="d963e-164">Правительства</span><span class="sxs-lookup"><span data-stu-id="d963e-164">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d963e-165">URI вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="d963e-165">Caller’s URI.</span></span> <span data-ttu-id="d963e-166">Ссылка из <a href="lync-server-2013-user-table.md">таблицы Users в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="d963e-166">Referenced from the <a href="lync-server-2013-user-table.md">User table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d963e-167"><strong>каллерендпоинт</strong></span><span class="sxs-lookup"><span data-stu-id="d963e-167"><strong>CallerEndpoint</strong></span></span></p></td>
<td><p><span data-ttu-id="d963e-168">int</span><span class="sxs-lookup"><span data-stu-id="d963e-168">int</span></span></p></td>
<td><p><span data-ttu-id="d963e-169">Правительства</span><span class="sxs-lookup"><span data-stu-id="d963e-169">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d963e-170">Конечная точка вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="d963e-170">Caller’s endpoint.</span></span> <span data-ttu-id="d963e-171">Указана в <a href="lync-server-2013-endpoint-table.md">таблице конечная точка в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="d963e-171">Referenced from the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d963e-172"><strong>каллерусеражент</strong></span><span class="sxs-lookup"><span data-stu-id="d963e-172"><strong>CallerUserAgent</strong></span></span></p></td>
<td><p><span data-ttu-id="d963e-173">Битовая</span><span class="sxs-lookup"><span data-stu-id="d963e-173">bit</span></span></p></td>
<td><p><span data-ttu-id="d963e-174">Правительства</span><span class="sxs-lookup"><span data-stu-id="d963e-174">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d963e-175">Агент пользователя вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="d963e-175">Caller’s user agent.</span></span> <span data-ttu-id="d963e-176">Ссылка из <a href="lync-server-2013-useragent-table.md">таблицы UserAgent в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="d963e-176">Referenced from the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d963e-177"><strong>каллприорити</strong></span><span class="sxs-lookup"><span data-stu-id="d963e-177"><strong>CallPriority</strong></span></span></p></td>
<td><p><span data-ttu-id="d963e-178">smallint</span><span class="sxs-lookup"><span data-stu-id="d963e-178">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d963e-179">Приоритет этого вызова.</span><span class="sxs-lookup"><span data-stu-id="d963e-179">The priority of this call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d963e-180"><strong>классифиедпуркалл</strong></span><span class="sxs-lookup"><span data-stu-id="d963e-180"><strong>ClassifiedPoorCall</strong></span></span></p></td>
<td><p><span data-ttu-id="d963e-181">Битовая</span><span class="sxs-lookup"><span data-stu-id="d963e-181">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d963e-182">Этот столбец устарел и не используется в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d963e-182">This column has been deprecated and is not used in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="d963e-183">Вместо этого эти сведения выводятся на основе линий отдельных носителей.</span><span class="sxs-lookup"><span data-stu-id="d963e-183">Instead, this information is reported on a per-media line bases.</span></span> <span data-ttu-id="d963e-184">Для получения дополнительных сведений обратитесь к <a href="lync-server-2013-medialine-table.md">таблице MediaLine в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="d963e-184">Refer to the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d963e-185"><strong>каллерпаи</strong></span><span class="sxs-lookup"><span data-stu-id="d963e-185"><strong>CallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="d963e-186">int</span><span class="sxs-lookup"><span data-stu-id="d963e-186">int</span></span></p></td>
<td><p><span data-ttu-id="d963e-187">Правительства</span><span class="sxs-lookup"><span data-stu-id="d963e-187">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d963e-188">P — утверждено — идентификатор пользователя, который поместил вызов.</span><span class="sxs-lookup"><span data-stu-id="d963e-188">P-Asserted-Identity of the user who placed the call.</span></span> <span data-ttu-id="d963e-189">P-Assert-Identity (PAI) используется для передачи истинного удостоверения пользователя, который поместил вызов.</span><span class="sxs-lookup"><span data-stu-id="d963e-189">The P-Asserted-Identity (PAI) is used to convey the true identity of the user who placed the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d963e-190"><strong>каллиендпоинт</strong></span><span class="sxs-lookup"><span data-stu-id="d963e-190"><strong>CalleeEndpoint</strong></span></span></p></td>
<td><p><span data-ttu-id="d963e-191">int</span><span class="sxs-lookup"><span data-stu-id="d963e-191">int</span></span></p></td>
<td><p><span data-ttu-id="d963e-192">Правительства</span><span class="sxs-lookup"><span data-stu-id="d963e-192">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d963e-193">Конечная точка, в которой был получен вызов.</span><span class="sxs-lookup"><span data-stu-id="d963e-193">Endpoint that received the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d963e-194"><strong>каллиусеражент</strong></span><span class="sxs-lookup"><span data-stu-id="d963e-194"><strong>CalleeUserAgent</strong></span></span></p></td>
<td><p><span data-ttu-id="d963e-195">int</span><span class="sxs-lookup"><span data-stu-id="d963e-195">int</span></span></p></td>
<td><p><span data-ttu-id="d963e-196">Правительства</span><span class="sxs-lookup"><span data-stu-id="d963e-196">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d963e-197">Агент пользователя, который использовался пользователем, получившим вызов.</span><span class="sxs-lookup"><span data-stu-id="d963e-197">User agent employed by the user who received the call.</span></span> <span data-ttu-id="d963e-198">Агенты пользователей представляют устройство конечной точки клиента.</span><span class="sxs-lookup"><span data-stu-id="d963e-198">User agents represent the client endpoint device.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d963e-199"><strong>каллиури</strong></span><span class="sxs-lookup"><span data-stu-id="d963e-199"><strong>CalleeUri</strong></span></span></p></td>
<td><p><span data-ttu-id="d963e-200">int</span><span class="sxs-lookup"><span data-stu-id="d963e-200">int</span></span></p></td>
<td><p><span data-ttu-id="d963e-201">Правительства</span><span class="sxs-lookup"><span data-stu-id="d963e-201">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d963e-202">Универсальный код ресурса (URI) SIP пользователя, который получил вызов.</span><span class="sxs-lookup"><span data-stu-id="d963e-202">SIP URI of the user who received the call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

