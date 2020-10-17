---
title: 'Lync Server 2013: таблица SessionDetails'
description: 'Lync Server 2013: таблица SessionDetails.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SessionDetails table
ms:assetid: 783d2508-e31f-4b54-be0c-63aa5ec21c04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398589(v=OCS.15)
ms:contentKeyID: 48184559
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fd927f784fb0f2a835c896824105fe8bb112c7a1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569935"
---
# <a name="sessiondetails-table-in-lync-server-2013"></a><span data-ttu-id="4f78f-103">Таблица SessionDetails в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4f78f-103">SessionDetails table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4f78f-104">_**Последнее изменение темы:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="4f78f-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="4f78f-105">Каждая запись представляет одноранговый сеанс, которым может быть телефонный звонок VoIP-VoIP, двухсторонний сеанс обмена мгновенными сообщениями или друг тип сеанса.</span><span class="sxs-lookup"><span data-stu-id="4f78f-105">Each record represents one peer-to-peer session, which could be a VoIP-VoIP phone call, two-party IM session, or other type of session.</span></span> <span data-ttu-id="4f78f-106">Вы можете выполнить присоединение таблицы к [таблице Media в Lync Server 2013](lync-server-2013-media-table.md) , чтобы найти подробные сведения о каждом из них, участвующих в этом сеансе.</span><span class="sxs-lookup"><span data-stu-id="4f78f-106">You can perform a table join with the [Media table in Lync Server 2013](lync-server-2013-media-table.md) to find the details of each media involved in this session.</span></span>

<span data-ttu-id="4f78f-107">Обратите внимание на то, что поля IsUser1IntegratedWithDeskPhone и IsUser2IntegratedWithDeskPhone удалены из таблицы SessionDetails, используемой в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4f78f-107">Note that the IsUser1IntegratedWithDeskPhone and the IsUser2IntegratedWithDeskPhone fields have been dropped from the SessionDetails table used in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4f78f-108">Столбец</span><span class="sxs-lookup"><span data-stu-id="4f78f-108">Column</span></span></th>
<th><span data-ttu-id="4f78f-109">Тип данных</span><span class="sxs-lookup"><span data-stu-id="4f78f-109">Data Type</span></span></th>
<th><span data-ttu-id="4f78f-110">Ключ или индекс</span><span class="sxs-lookup"><span data-stu-id="4f78f-110">Key/Index</span></span></th>
<th><span data-ttu-id="4f78f-111">Сведения</span><span class="sxs-lookup"><span data-stu-id="4f78f-111">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4f78f-112"><strong>сессионидтиме</strong></span><span class="sxs-lookup"><span data-stu-id="4f78f-112"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="4f78f-113">datetime</span><span class="sxs-lookup"><span data-stu-id="4f78f-113">datetime</span></span></p></td>
<td><p><span data-ttu-id="4f78f-114">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="4f78f-114">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="4f78f-115">Время запроса сеанса.</span><span class="sxs-lookup"><span data-stu-id="4f78f-115">Time of session request.</span></span> <span data-ttu-id="4f78f-116">В сочетании с параметром <strong>SessionIdSeq</strong> определяет сеанс уникальным образом.</span><span class="sxs-lookup"><span data-stu-id="4f78f-116">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="4f78f-117">Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="4f78f-117">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f78f-118"><strong>сессионидсек</strong></span><span class="sxs-lookup"><span data-stu-id="4f78f-118"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="4f78f-119">int</span><span class="sxs-lookup"><span data-stu-id="4f78f-119">int</span></span></p></td>
<td><p><span data-ttu-id="4f78f-120">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="4f78f-120">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="4f78f-121">Идентификатор для идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="4f78f-121">ID number to identify the session.</span></span> <span data-ttu-id="4f78f-122">Используется совместно с <strong>сессионидтиме</strong> для уникальной идентификации сеанса. \* Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="4f78f-122">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.\* See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f78f-123"><strong>ИД</strong></span><span class="sxs-lookup"><span data-stu-id="4f78f-123"><strong>CorrelationId</strong></span></span></p></td>
<td><p><span data-ttu-id="4f78f-124">идентификатора</span><span class="sxs-lookup"><span data-stu-id="4f78f-124">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4f78f-125">GUID для корреляции нескольких сеансов.</span><span class="sxs-lookup"><span data-stu-id="4f78f-125">A GUID to correlate multiple sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f78f-126"><strong>реплацедиалогидтиме</strong></span><span class="sxs-lookup"><span data-stu-id="4f78f-126"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="4f78f-127">datetime</span><span class="sxs-lookup"><span data-stu-id="4f78f-127">datetime</span></span></p></td>
<td><p><span data-ttu-id="4f78f-128">Правительства</span><span class="sxs-lookup"><span data-stu-id="4f78f-128">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4f78f-129">Идентификационный номер для определения диалога, замененного текущим сеансом.</span><span class="sxs-lookup"><span data-stu-id="4f78f-129">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="4f78f-130">Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="4f78f-130">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f78f-131"><strong>реплацедиалогидсек</strong></span><span class="sxs-lookup"><span data-stu-id="4f78f-131"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="4f78f-132">int</span><span class="sxs-lookup"><span data-stu-id="4f78f-132">int</span></span></p></td>
<td><p><span data-ttu-id="4f78f-133">Правительства</span><span class="sxs-lookup"><span data-stu-id="4f78f-133">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4f78f-134">Идентификатор для идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="4f78f-134">ID number to identify the session.</span></span> <span data-ttu-id="4f78f-135">Используется в сочетании с <strong>ReplacesDialogIdTime</strong> для уникальной идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="4f78f-135">Used in conjunction with <strong>ReplacesDialogIdTime</strong> to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="4f78f-136">Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="4f78f-136">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f78f-137"><strong>User1Id</strong></span><span class="sxs-lookup"><span data-stu-id="4f78f-137"><strong>User1Id</strong></span></span></p></td>
<td><p><span data-ttu-id="4f78f-138">int</span><span class="sxs-lookup"><span data-stu-id="4f78f-138">int</span></span></p></td>
<td><p><span data-ttu-id="4f78f-139">Правительства</span><span class="sxs-lookup"><span data-stu-id="4f78f-139">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4f78f-140">Идентификатор одного пользователя в сеансе.</span><span class="sxs-lookup"><span data-stu-id="4f78f-140">ID of one user in the session.</span></span> <span data-ttu-id="4f78f-141">Дополнительные сведения см. <a href="lync-server-2013-users-table.md">в таблице "Пользователи" в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="4f78f-141">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f78f-142"><strong>User2Id</strong></span><span class="sxs-lookup"><span data-stu-id="4f78f-142"><strong>User2Id</strong></span></span></p></td>
<td><p><span data-ttu-id="4f78f-143">int</span><span class="sxs-lookup"><span data-stu-id="4f78f-143">int</span></span></p></td>
<td><p><span data-ttu-id="4f78f-144">Правительства</span><span class="sxs-lookup"><span data-stu-id="4f78f-144">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4f78f-145">Идентификатор другого пользователя в сеансе.</span><span class="sxs-lookup"><span data-stu-id="4f78f-145">ID of the other user in the session.</span></span> <span data-ttu-id="4f78f-146">Дополнительные сведения см. <a href="lync-server-2013-users-table.md">в таблице "Пользователи" в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="4f78f-146">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f78f-147"><strong>User1EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="4f78f-147"><strong>User1EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="4f78f-148">Идентификатора</span><span class="sxs-lookup"><span data-stu-id="4f78f-148">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4f78f-149">GUID, идентифицирующий конечную точку, применяемую первым пользователем в сеансе.</span><span class="sxs-lookup"><span data-stu-id="4f78f-149">GUID that identifies the endpoint used by the first user in the session.</span></span></p>
<p><span data-ttu-id="4f78f-150">Это поле было введено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4f78f-150">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f78f-151"><strong>User2EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="4f78f-151"><strong>User2EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="4f78f-152">Идентификатора</span><span class="sxs-lookup"><span data-stu-id="4f78f-152">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4f78f-153">GUID, идентифицирующий конечную точку, применяемую вторым пользователем в сеансе.</span><span class="sxs-lookup"><span data-stu-id="4f78f-153">GUID that identifies the endpoint used by the second user in the session.</span></span></p>
<p><span data-ttu-id="4f78f-154">Это поле было введено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4f78f-154">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f78f-155"><strong>TargetUserId</strong></span><span class="sxs-lookup"><span data-stu-id="4f78f-155"><strong>TargetUserId</strong></span></span></p></td>
<td><p><span data-ttu-id="4f78f-156">int</span><span class="sxs-lookup"><span data-stu-id="4f78f-156">int</span></span></p></td>
<td><p><span data-ttu-id="4f78f-157">Правительства</span><span class="sxs-lookup"><span data-stu-id="4f78f-157">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4f78f-158">URI-адрес исходного вызываемого пользователя в SIP-запросе.</span><span class="sxs-lookup"><span data-stu-id="4f78f-158">The original To user URI in the SIP request.</span></span> <span data-ttu-id="4f78f-159">Дополнительные сведения см. <a href="lync-server-2013-users-table.md">в таблице "Пользователи" в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="4f78f-159">see the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f78f-160"><strong>сессионстартедбид</strong></span><span class="sxs-lookup"><span data-stu-id="4f78f-160"><strong>SessionStartedById</strong></span></span></p></td>
<td><p><span data-ttu-id="4f78f-161">int</span><span class="sxs-lookup"><span data-stu-id="4f78f-161">int</span></span></p></td>
<td><p><span data-ttu-id="4f78f-162">Правительства</span><span class="sxs-lookup"><span data-stu-id="4f78f-162">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4f78f-163">Идентификатор пользователя, инициировавшего сеанс.</span><span class="sxs-lookup"><span data-stu-id="4f78f-163">ID of the user who started the session.</span></span> <span data-ttu-id="4f78f-164">Дополнительные сведения см. <a href="lync-server-2013-users-table.md">в таблице "Пользователи" в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="4f78f-164">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f78f-165"><strong>онбехалфофид</strong></span><span class="sxs-lookup"><span data-stu-id="4f78f-165"><strong>OnBehalfOfId</strong></span></span></p></td>
<td><p><span data-ttu-id="4f78f-166">int</span><span class="sxs-lookup"><span data-stu-id="4f78f-166">int</span></span></p></td>
<td><p><span data-ttu-id="4f78f-167">Правительства</span><span class="sxs-lookup"><span data-stu-id="4f78f-167">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4f78f-168">Определяет идентификатор пользователя, которого представляет вызывающий абонент.</span><span class="sxs-lookup"><span data-stu-id="4f78f-168">Indicates the ID of the user of who the caller is on behalf.</span></span> <span data-ttu-id="4f78f-169">Дополнительные сведения см. <a href="lync-server-2013-users-table.md">в таблице "Пользователи" в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="4f78f-169">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f78f-170"><strong>реферредбид</strong></span><span class="sxs-lookup"><span data-stu-id="4f78f-170"><strong>ReferredById</strong></span></span></p></td>
<td><p><span data-ttu-id="4f78f-171">int</span><span class="sxs-lookup"><span data-stu-id="4f78f-171">int</span></span></p></td>
<td><p><span data-ttu-id="4f78f-172">Правительства</span><span class="sxs-lookup"><span data-stu-id="4f78f-172">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4f78f-173">Идентификатор пользователя, который ссылается на вызов.</span><span class="sxs-lookup"><span data-stu-id="4f78f-173">ID of the user by who the call is referred.</span></span> <span data-ttu-id="4f78f-174">Дополнительные сведения см. <a href="lync-server-2013-users-table.md">в таблице "Пользователи" в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="4f78f-174">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f78f-175"><strong>ServerId</strong></span><span class="sxs-lookup"><span data-stu-id="4f78f-175"><strong>ServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="4f78f-176">int</span><span class="sxs-lookup"><span data-stu-id="4f78f-176">int</span></span></p></td>
<td><p><span data-ttu-id="4f78f-177">Правительства</span><span class="sxs-lookup"><span data-stu-id="4f78f-177">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4f78f-178">Идентификатор сервера переднего плана, используемого для этого сеанса.</span><span class="sxs-lookup"><span data-stu-id="4f78f-178">ID of the front-end server used for this session.</span></span> <span data-ttu-id="4f78f-179">Дополнительные сведения см. <a href="lync-server-2013-servers-table.md">в таблице Servers в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="4f78f-179">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f78f-180"><strong>пулид</strong></span><span class="sxs-lookup"><span data-stu-id="4f78f-180"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="4f78f-181">int</span><span class="sxs-lookup"><span data-stu-id="4f78f-181">int</span></span></p></td>
<td><p><span data-ttu-id="4f78f-182">Правительства</span><span class="sxs-lookup"><span data-stu-id="4f78f-182">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4f78f-183">Идентификатор пула, в котором был записан сеанс.</span><span class="sxs-lookup"><span data-stu-id="4f78f-183">ID of the pool in which the session was captured.</span></span> <span data-ttu-id="4f78f-184">Дополнительные сведения см. <a href="lync-server-2013-pools-table.md">в таблице Pools в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="4f78f-184">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f78f-185"><strong>ContentTypeID</strong></span><span class="sxs-lookup"><span data-stu-id="4f78f-185"><strong>ContentTypeID</strong></span></span></p></td>
<td><p><span data-ttu-id="4f78f-186">int</span><span class="sxs-lookup"><span data-stu-id="4f78f-186">int</span></span></p></td>
<td><p><span data-ttu-id="4f78f-187">Правительства</span><span class="sxs-lookup"><span data-stu-id="4f78f-187">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4f78f-188">Тип контента, используемый в сеансе.</span><span class="sxs-lookup"><span data-stu-id="4f78f-188">Content type used in the session.</span></span> <span data-ttu-id="4f78f-189">Для получения дополнительных сведений см <a href="lync-server-2013-contenttypes-table.md">таблицу ContentTypes в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="4f78f-189">See the <a href="lync-server-2013-contenttypes-table.md">ContentTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f78f-190"><strong>User1ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="4f78f-190"><strong>User1ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="4f78f-191">int</span><span class="sxs-lookup"><span data-stu-id="4f78f-191">int</span></span></p></td>
<td><p><span data-ttu-id="4f78f-192">Правительства</span><span class="sxs-lookup"><span data-stu-id="4f78f-192">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4f78f-193">Версия клиента, применяемая пользователем User1.</span><span class="sxs-lookup"><span data-stu-id="4f78f-193">Client version used by User1.</span></span> <span data-ttu-id="4f78f-194">Дополнительные сведения см. <a href="lync-server-2013-clientversions-table.md">в таблице таблица clientversions в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="4f78f-194">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f78f-195"><strong>User2ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="4f78f-195"><strong>User2ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="4f78f-196">int</span><span class="sxs-lookup"><span data-stu-id="4f78f-196">int</span></span></p></td>
<td><p><span data-ttu-id="4f78f-197">Правительства</span><span class="sxs-lookup"><span data-stu-id="4f78f-197">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4f78f-198">Версия клиента, применяемая пользователем User2.</span><span class="sxs-lookup"><span data-stu-id="4f78f-198">Client version used by User2.</span></span> <span data-ttu-id="4f78f-199">Дополнительные сведения см. <a href="lync-server-2013-clientversions-table.md">в таблице таблица clientversions в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="4f78f-199">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f78f-200"><strong>User1EdgeServerid</strong></span><span class="sxs-lookup"><span data-stu-id="4f78f-200"><strong>User1EdgeServerid</strong></span></span></p></td>
<td><p><span data-ttu-id="4f78f-201">int</span><span class="sxs-lookup"><span data-stu-id="4f78f-201">int</span></span></p></td>
<td><p><span data-ttu-id="4f78f-202">Правительства</span><span class="sxs-lookup"><span data-stu-id="4f78f-202">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4f78f-203">Пограничный сервер, применяемый пользователем User1.</span><span class="sxs-lookup"><span data-stu-id="4f78f-203">Edge Server used by User1.</span></span> <span data-ttu-id="4f78f-204">Дополнительные сведения см. <a href="lync-server-2013-edgeservers-table.md">в таблице таблица edgeservers в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="4f78f-204">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f78f-205"><strong>User2EdgeServerid</strong></span><span class="sxs-lookup"><span data-stu-id="4f78f-205"><strong>User2EdgeServerid</strong></span></span></p></td>
<td><p><span data-ttu-id="4f78f-206">int</span><span class="sxs-lookup"><span data-stu-id="4f78f-206">int</span></span></p></td>
<td><p><span data-ttu-id="4f78f-207">Правительства</span><span class="sxs-lookup"><span data-stu-id="4f78f-207">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4f78f-208">Пограничный сервер, применяемый пользователем User2.</span><span class="sxs-lookup"><span data-stu-id="4f78f-208">Edge Server used by User2.</span></span> <span data-ttu-id="4f78f-209">Дополнительные сведения см. <a href="lync-server-2013-edgeservers-table.md">в таблице таблица edgeservers в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="4f78f-209">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f78f-210"><strong>IsUser1Internal</strong></span><span class="sxs-lookup"><span data-stu-id="4f78f-210"><strong>IsUser1Internal</strong></span></span></p></td>
<td><p><span data-ttu-id="4f78f-211">Битовая</span><span class="sxs-lookup"><span data-stu-id="4f78f-211">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4f78f-212">Вошел ли пользователь User1 из внутренней сети или нет.</span><span class="sxs-lookup"><span data-stu-id="4f78f-212">Whether User1 is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f78f-213"><strong>IsUser2Internal</strong></span><span class="sxs-lookup"><span data-stu-id="4f78f-213"><strong>IsUser2Internal</strong></span></span></p></td>
<td><p><span data-ttu-id="4f78f-214">Битовая</span><span class="sxs-lookup"><span data-stu-id="4f78f-214">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4f78f-215">Вошел ли пользователь User2 из внутренней сети или нет.</span><span class="sxs-lookup"><span data-stu-id="4f78f-215">Whether User2 is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f78f-216"><strong>инвитетиме</strong></span><span class="sxs-lookup"><span data-stu-id="4f78f-216"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="4f78f-217">datetime</span><span class="sxs-lookup"><span data-stu-id="4f78f-217">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4f78f-218">Время первого запроса INVITE.</span><span class="sxs-lookup"><span data-stu-id="4f78f-218">The time of the first INVITE request.</span></span> <span data-ttu-id="4f78f-219">Это поле обычно заполняется данными, генерируемыми из исходного сообщения INVITE в сеансе.</span><span class="sxs-lookup"><span data-stu-id="4f78f-219">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="4f78f-220">Если сообщения INVITE нет, поле заполняется датой и временем первого релевантного SIP-сообщения (BYE, CANCEL, MESSAGE или INFO).</span><span class="sxs-lookup"><span data-stu-id="4f78f-220">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span> <span data-ttu-id="4f78f-221">Это поле обычно заполняется данными, генерируемыми из исходного сообщения INVITE в сеансе.</span><span class="sxs-lookup"><span data-stu-id="4f78f-221">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="4f78f-222">Если сообщения INVITE нет, поле заполняется датой и временем первого релевантного SIP-сообщения (BYE, CANCEL, MESSAGE или INFO).</span><span class="sxs-lookup"><span data-stu-id="4f78f-222">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f78f-223"><strong>респонсетиме</strong></span><span class="sxs-lookup"><span data-stu-id="4f78f-223"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="4f78f-224">datetime</span><span class="sxs-lookup"><span data-stu-id="4f78f-224">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4f78f-225">Время ответа на первое сообщение INVITE.</span><span class="sxs-lookup"><span data-stu-id="4f78f-225">The time of the response to the first INVITE message.</span></span> <span data-ttu-id="4f78f-226">Обычно это поле содержит данные из первоначального сообщения INVITE в сеансе.</span><span class="sxs-lookup"><span data-stu-id="4f78f-226">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="4f78f-227">Если сообщение INVITE отсутствует, в поле записывается дата и время первого соответствующего SIP-сообщения (BYE, CANCEL, MESSAGE или INFO).</span><span class="sxs-lookup"><span data-stu-id="4f78f-227">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f78f-228"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="4f78f-228"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="4f78f-229">int</span><span class="sxs-lookup"><span data-stu-id="4f78f-229">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4f78f-p121">Код SIP-ответа на приглашение в сеанс. Это поле обычно заполняется данными, генерируемыми из исходного сообщения INVITE в сеансе. Если сообщения INVITE нет, поле заполняется датой и временем первого релевантного SIP-сообщения (BYE, CANCEL, MESSAGE или INFO).</span><span class="sxs-lookup"><span data-stu-id="4f78f-p121">SIP response code to the session invitation. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f78f-233"><strong>диагностиЦид</strong></span><span class="sxs-lookup"><span data-stu-id="4f78f-233"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="4f78f-234">int</span><span class="sxs-lookup"><span data-stu-id="4f78f-234">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4f78f-235">Идентификатор диагностики из заголовка SIP.</span><span class="sxs-lookup"><span data-stu-id="4f78f-235">Diagnostic ID captured from SIP header.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f78f-236"><strong>каллприорити</strong></span><span class="sxs-lookup"><span data-stu-id="4f78f-236"><strong>CallPriority</strong></span></span></p></td>
<td><p><span data-ttu-id="4f78f-237">int</span><span class="sxs-lookup"><span data-stu-id="4f78f-237">int</span></span></p></td>
<td><p><span data-ttu-id="4f78f-238">Правительства</span><span class="sxs-lookup"><span data-stu-id="4f78f-238">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4f78f-239">Приоритет звонка.</span><span class="sxs-lookup"><span data-stu-id="4f78f-239">Call priority.</span></span> <span data-ttu-id="4f78f-240">Дополнительные сведения см. <a href="lync-server-2013-callpriorities-table.md">в таблице таблица callpriorities в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="4f78f-240">See the <a href="lync-server-2013-callpriorities-table.md">CallPriorities table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f78f-241"><strong>User1MessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="4f78f-241"><strong>User1MessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="4f78f-242">int</span><span class="sxs-lookup"><span data-stu-id="4f78f-242">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4f78f-243">Число сообщений, отправленных пользователем User1 в сеансе.</span><span class="sxs-lookup"><span data-stu-id="4f78f-243">Number of messages sent by User1 during the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f78f-244"><strong>User2MessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="4f78f-244"><strong>User2MessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="4f78f-245">int</span><span class="sxs-lookup"><span data-stu-id="4f78f-245">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4f78f-246">Число сообщений, отправленных пользователем User2 в сеансе.</span><span class="sxs-lookup"><span data-stu-id="4f78f-246">Number of messages sent by User2 during the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f78f-247"><strong>сессионендтиме</strong></span><span class="sxs-lookup"><span data-stu-id="4f78f-247"><strong>SessionEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="4f78f-248">datetime</span><span class="sxs-lookup"><span data-stu-id="4f78f-248">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4f78f-249">Время окончания сеанса.</span><span class="sxs-lookup"><span data-stu-id="4f78f-249">Time at the end of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f78f-250"><strong>MediaTypes</strong></span><span class="sxs-lookup"><span data-stu-id="4f78f-250"><strong>MediaTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="4f78f-251">int</span><span class="sxs-lookup"><span data-stu-id="4f78f-251">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4f78f-p123">Бит, указывающий тип носителя этого сеанса. Дале перечислены определения типов:</span><span class="sxs-lookup"><span data-stu-id="4f78f-p123">A bit set that indicates the media type of this session. Listed are the definitions of the types:</span></span></p>
<h3 id="section-1"> </h3>
<div>
<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4f78f-254">"IM" (Обмен мгновенными сообщениями);</span><span class="sxs-lookup"><span data-stu-id="4f78f-254">IM</span></span></p></td>
<td><p><span data-ttu-id="4f78f-255">1,1</span><span class="sxs-lookup"><span data-stu-id="4f78f-255">1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f78f-256">FILE_TRANSFER</span><span class="sxs-lookup"><span data-stu-id="4f78f-256">FILE_TRANSFER</span></span></p></td>
<td><p><span data-ttu-id="4f78f-257">2</span><span class="sxs-lookup"><span data-stu-id="4f78f-257">2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f78f-258">REMOTE_ASSISTANCE</span><span class="sxs-lookup"><span data-stu-id="4f78f-258">REMOTE_ASSISTANCE</span></span></p></td>
<td><p><span data-ttu-id="4f78f-259">4 </span><span class="sxs-lookup"><span data-stu-id="4f78f-259">4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f78f-260">APP_SHARING</span><span class="sxs-lookup"><span data-stu-id="4f78f-260">APP_SHARING</span></span></p></td>
<td><p><span data-ttu-id="4f78f-261">8 </span><span class="sxs-lookup"><span data-stu-id="4f78f-261">8</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f78f-262">ПРОИЗВЕДЕН</span><span class="sxs-lookup"><span data-stu-id="4f78f-262">AUDIO</span></span></p></td>
<td><p><span data-ttu-id="4f78f-263">16 </span><span class="sxs-lookup"><span data-stu-id="4f78f-263">16</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f78f-264">ВИДЕОМАТЕРИАЛ</span><span class="sxs-lookup"><span data-stu-id="4f78f-264">VIDEO</span></span></p></td>
<td><p><span data-ttu-id="4f78f-265">32</span><span class="sxs-lookup"><span data-stu-id="4f78f-265">32</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f78f-266">APP_INVITE</span><span class="sxs-lookup"><span data-stu-id="4f78f-266">APP_INVITE</span></span></p></td>
<td><p><span data-ttu-id="4f78f-267">64</span><span class="sxs-lookup"><span data-stu-id="4f78f-267">64</span></span></p></td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f78f-268"><strong>User1Flag</strong></span><span class="sxs-lookup"><span data-stu-id="4f78f-268"><strong>User1Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="4f78f-269">smallint</span><span class="sxs-lookup"><span data-stu-id="4f78f-269">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4f78f-p124">Бит, обозначающий атрибуты пользователя User1. Далее перечислены определения атрибутов:</span><span class="sxs-lookup"><span data-stu-id="4f78f-p124">A bit set that indicates the User1 attributes. The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="4f78f-272">0x01 — интегрировано со стационарным телефоном</span><span class="sxs-lookup"><span data-stu-id="4f78f-272">0x01 - Integrated with desktop phone</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f78f-273"><strong>User2Flag</strong></span><span class="sxs-lookup"><span data-stu-id="4f78f-273"><strong>User2Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="4f78f-274">smallint</span><span class="sxs-lookup"><span data-stu-id="4f78f-274">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4f78f-p125">Бит, обозначающий атрибуты пользователя User2. Далее перечислены определения атрибутов:</span><span class="sxs-lookup"><span data-stu-id="4f78f-p125">A bit set that indicates the User2 attributes. The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="4f78f-277">0x01 — интегрировано со стационарным телефоном</span><span class="sxs-lookup"><span data-stu-id="4f78f-277">0x01 - Integrated with desktop phone</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f78f-278"><strong>каллфлаг</strong></span><span class="sxs-lookup"><span data-stu-id="4f78f-278"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="4f78f-279">smallint</span><span class="sxs-lookup"><span data-stu-id="4f78f-279">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4f78f-p126">Бит, обозначающий атрибуты пользователя User2. Далее перечислены определения атрибутов:</span><span class="sxs-lookup"><span data-stu-id="4f78f-p126">A bit set that indicates the call attributes. The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="4f78f-282">0x01 — повторенный сеанс</span><span class="sxs-lookup"><span data-stu-id="4f78f-282">0x01 - Retried Session</span></span></p></li>
<li><p><span data-ttu-id="4f78f-283">0x02 — вызов, выполненный агентом от имени группы ответа</span><span class="sxs-lookup"><span data-stu-id="4f78f-283">0x02 - A call made by agent on behalf of a response group</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f78f-284"><strong>Обработать</strong></span><span class="sxs-lookup"><span data-stu-id="4f78f-284"><strong>Processed</strong></span></span></p></td>
<td><p><span data-ttu-id="4f78f-285">Битовая</span><span class="sxs-lookup"><span data-stu-id="4f78f-285">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4f78f-286">Для внутреннего использования службой мониторинга.</span><span class="sxs-lookup"><span data-stu-id="4f78f-286">For internal use by the Monitoring service.</span></span></p>
<p><span data-ttu-id="4f78f-287">Это поле было введено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4f78f-287">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="4f78f-288">\* Для большинства сеансов Сессионидсек будет иметь значение 1.</span><span class="sxs-lookup"><span data-stu-id="4f78f-288">\* For most sessions, SessionIdSeq will have the value of 1.</span></span> <span data-ttu-id="4f78f-289">Если несколько сеансов начинаются в одно и то же время, для одного из них SessionIdSeq будет иметь значение 1, для другого — 2 и т. д.</span><span class="sxs-lookup"><span data-stu-id="4f78f-289">If multiple sessions start at exactly the same time, the SessionIdSeq for one will be 1, for another will be 2, and so on.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

