---
title: 'Lync Server 2013: таблица SessionDetails'
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
ms.openlocfilehash: bfdf5552f150b23c50e8ad6867e90f96a6b586fb
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42182312"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="sessiondetails-table-in-lync-server-2013"></a><span data-ttu-id="ab3c6-102">Таблица SessionDetails в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ab3c6-102">SessionDetails table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ab3c6-103">_**Последнее изменение темы:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="ab3c6-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="ab3c6-104">Каждая запись представляет одноранговый сеанс, которым может быть телефонный звонок VoIP-VoIP, двухсторонний сеанс обмена мгновенными сообщениями или друг тип сеанса.</span><span class="sxs-lookup"><span data-stu-id="ab3c6-104">Each record represents one peer-to-peer session, which could be a VoIP-VoIP phone call, two-party IM session, or other type of session.</span></span> <span data-ttu-id="ab3c6-105">Вы можете выполнить присоединение таблицы к [таблице Media в Lync Server 2013](lync-server-2013-media-table.md) , чтобы найти подробные сведения о каждом из них, участвующих в этом сеансе.</span><span class="sxs-lookup"><span data-stu-id="ab3c6-105">You can perform a table join with the [Media table in Lync Server 2013](lync-server-2013-media-table.md) to find the details of each media involved in this session.</span></span>

<span data-ttu-id="ab3c6-106">Обратите внимание на то, что поля IsUser1IntegratedWithDeskPhone и IsUser2IntegratedWithDeskPhone удалены из таблицы SessionDetails, используемой в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ab3c6-106">Note that the IsUser1IntegratedWithDeskPhone and the IsUser2IntegratedWithDeskPhone fields have been dropped from the SessionDetails table used in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ab3c6-107">Столбец</span><span class="sxs-lookup"><span data-stu-id="ab3c6-107">Column</span></span></th>
<th><span data-ttu-id="ab3c6-108">Тип данных</span><span class="sxs-lookup"><span data-stu-id="ab3c6-108">Data Type</span></span></th>
<th><span data-ttu-id="ab3c6-109">Ключ или индекс</span><span class="sxs-lookup"><span data-stu-id="ab3c6-109">Key/Index</span></span></th>
<th><span data-ttu-id="ab3c6-110">Сведения</span><span class="sxs-lookup"><span data-stu-id="ab3c6-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ab3c6-111"><strong>сессионидтиме</strong></span><span class="sxs-lookup"><span data-stu-id="ab3c6-111"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ab3c6-112">datetime</span><span class="sxs-lookup"><span data-stu-id="ab3c6-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="ab3c6-113">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="ab3c6-113">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="ab3c6-114">Время запроса сеанса.</span><span class="sxs-lookup"><span data-stu-id="ab3c6-114">Time of session request.</span></span> <span data-ttu-id="ab3c6-115">В сочетании с параметром <strong>SessionIdSeq</strong> определяет сеанс уникальным образом.</span><span class="sxs-lookup"><span data-stu-id="ab3c6-115">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="ab3c6-116">Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ab3c6-116">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab3c6-117"><strong>сессионидсек</strong></span><span class="sxs-lookup"><span data-stu-id="ab3c6-117"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="ab3c6-118">int</span><span class="sxs-lookup"><span data-stu-id="ab3c6-118">int</span></span></p></td>
<td><p><span data-ttu-id="ab3c6-119">Первичный, внешний</span><span class="sxs-lookup"><span data-stu-id="ab3c6-119">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="ab3c6-120">Идентификатор сеанса.</span><span class="sxs-lookup"><span data-stu-id="ab3c6-120">ID number to identify the session.</span></span> <span data-ttu-id="ab3c6-121">Используется совместно с <strong>сессионидтиме</strong> для уникальной идентификации сеанса. \* Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ab3c6-121">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.\* See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab3c6-122"><strong>ИД</strong></span><span class="sxs-lookup"><span data-stu-id="ab3c6-122"><strong>CorrelationId</strong></span></span></p></td>
<td><p><span data-ttu-id="ab3c6-123">идентификатора</span><span class="sxs-lookup"><span data-stu-id="ab3c6-123">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab3c6-124">GUID для корреляции нескольких сеансов.</span><span class="sxs-lookup"><span data-stu-id="ab3c6-124">A GUID to correlate multiple sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab3c6-125"><strong>реплацедиалогидтиме</strong></span><span class="sxs-lookup"><span data-stu-id="ab3c6-125"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ab3c6-126">datetime</span><span class="sxs-lookup"><span data-stu-id="ab3c6-126">datetime</span></span></p></td>
<td><p><span data-ttu-id="ab3c6-127">Правительства</span><span class="sxs-lookup"><span data-stu-id="ab3c6-127">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ab3c6-128">Идентификационный номер для определения диалога, замененного текущим сеансом.</span><span class="sxs-lookup"><span data-stu-id="ab3c6-128">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="ab3c6-129">Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ab3c6-129">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab3c6-130"><strong>реплацедиалогидсек</strong></span><span class="sxs-lookup"><span data-stu-id="ab3c6-130"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="ab3c6-131">int</span><span class="sxs-lookup"><span data-stu-id="ab3c6-131">int</span></span></p></td>
<td><p><span data-ttu-id="ab3c6-132">Правительства</span><span class="sxs-lookup"><span data-stu-id="ab3c6-132">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ab3c6-133">Идентификатор для идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="ab3c6-133">ID number to identify the session.</span></span> <span data-ttu-id="ab3c6-134">Используется в сочетании с <strong>ReplacesDialogIdTime</strong> для уникальной идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="ab3c6-134">Used in conjunction with <strong>ReplacesDialogIdTime</strong> to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="ab3c6-135">Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ab3c6-135">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab3c6-136"><strong>User1Id</strong></span><span class="sxs-lookup"><span data-stu-id="ab3c6-136"><strong>User1Id</strong></span></span></p></td>
<td><p><span data-ttu-id="ab3c6-137">int</span><span class="sxs-lookup"><span data-stu-id="ab3c6-137">int</span></span></p></td>
<td><p><span data-ttu-id="ab3c6-138">Правительства</span><span class="sxs-lookup"><span data-stu-id="ab3c6-138">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ab3c6-139">Идентификатор одного пользователя в сеансе.</span><span class="sxs-lookup"><span data-stu-id="ab3c6-139">ID of one user in the session.</span></span> <span data-ttu-id="ab3c6-140">Дополнительные сведения см. <a href="lync-server-2013-users-table.md">в таблице "Пользователи" в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ab3c6-140">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab3c6-141"><strong>User2Id</strong></span><span class="sxs-lookup"><span data-stu-id="ab3c6-141"><strong>User2Id</strong></span></span></p></td>
<td><p><span data-ttu-id="ab3c6-142">int</span><span class="sxs-lookup"><span data-stu-id="ab3c6-142">int</span></span></p></td>
<td><p><span data-ttu-id="ab3c6-143">Правительства</span><span class="sxs-lookup"><span data-stu-id="ab3c6-143">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ab3c6-144">Идентификатор другого пользователя в сеансе.</span><span class="sxs-lookup"><span data-stu-id="ab3c6-144">ID of the other user in the session.</span></span> <span data-ttu-id="ab3c6-145">Дополнительные сведения см. <a href="lync-server-2013-users-table.md">в таблице "Пользователи" в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ab3c6-145">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab3c6-146"><strong>User1EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="ab3c6-146"><strong>User1EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="ab3c6-147">Идентификатора</span><span class="sxs-lookup"><span data-stu-id="ab3c6-147">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab3c6-148">GUID, идентифицирующий конечную точку, применяемую первым пользователем в сеансе.</span><span class="sxs-lookup"><span data-stu-id="ab3c6-148">GUID that identifies the endpoint used by the first user in the session.</span></span></p>
<p><span data-ttu-id="ab3c6-149">Это поле было введено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ab3c6-149">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab3c6-150"><strong>User2EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="ab3c6-150"><strong>User2EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="ab3c6-151">Идентификатора</span><span class="sxs-lookup"><span data-stu-id="ab3c6-151">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab3c6-152">GUID, идентифицирующий конечную точку, применяемую вторым пользователем в сеансе.</span><span class="sxs-lookup"><span data-stu-id="ab3c6-152">GUID that identifies the endpoint used by the second user in the session.</span></span></p>
<p><span data-ttu-id="ab3c6-153">Это поле было введено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ab3c6-153">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab3c6-154"><strong>TargetUserId</strong></span><span class="sxs-lookup"><span data-stu-id="ab3c6-154"><strong>TargetUserId</strong></span></span></p></td>
<td><p><span data-ttu-id="ab3c6-155">int</span><span class="sxs-lookup"><span data-stu-id="ab3c6-155">int</span></span></p></td>
<td><p><span data-ttu-id="ab3c6-156">Правительства</span><span class="sxs-lookup"><span data-stu-id="ab3c6-156">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ab3c6-157">URI-адрес исходного вызываемого пользователя в SIP-запросе.</span><span class="sxs-lookup"><span data-stu-id="ab3c6-157">The original To user URI in the SIP request.</span></span> <span data-ttu-id="ab3c6-158">Дополнительные сведения см. <a href="lync-server-2013-users-table.md">в таблице "Пользователи" в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ab3c6-158">see the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab3c6-159"><strong>сессионстартедбид</strong></span><span class="sxs-lookup"><span data-stu-id="ab3c6-159"><strong>SessionStartedById</strong></span></span></p></td>
<td><p><span data-ttu-id="ab3c6-160">int</span><span class="sxs-lookup"><span data-stu-id="ab3c6-160">int</span></span></p></td>
<td><p><span data-ttu-id="ab3c6-161">Правительства</span><span class="sxs-lookup"><span data-stu-id="ab3c6-161">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ab3c6-162">Идентификатор пользователя, инициировавшего сеанс.</span><span class="sxs-lookup"><span data-stu-id="ab3c6-162">ID of the user who started the session.</span></span> <span data-ttu-id="ab3c6-163">Дополнительные сведения см. <a href="lync-server-2013-users-table.md">в таблице "Пользователи" в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ab3c6-163">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab3c6-164"><strong>онбехалфофид</strong></span><span class="sxs-lookup"><span data-stu-id="ab3c6-164"><strong>OnBehalfOfId</strong></span></span></p></td>
<td><p><span data-ttu-id="ab3c6-165">int</span><span class="sxs-lookup"><span data-stu-id="ab3c6-165">int</span></span></p></td>
<td><p><span data-ttu-id="ab3c6-166">Правительства</span><span class="sxs-lookup"><span data-stu-id="ab3c6-166">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ab3c6-167">Определяет идентификатор пользователя, которого представляет вызывающий абонент.</span><span class="sxs-lookup"><span data-stu-id="ab3c6-167">Indicates the ID of the user of who the caller is on behalf.</span></span> <span data-ttu-id="ab3c6-168">Дополнительные сведения см. <a href="lync-server-2013-users-table.md">в таблице "Пользователи" в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ab3c6-168">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab3c6-169"><strong>реферредбид</strong></span><span class="sxs-lookup"><span data-stu-id="ab3c6-169"><strong>ReferredById</strong></span></span></p></td>
<td><p><span data-ttu-id="ab3c6-170">int</span><span class="sxs-lookup"><span data-stu-id="ab3c6-170">int</span></span></p></td>
<td><p><span data-ttu-id="ab3c6-171">Правительства</span><span class="sxs-lookup"><span data-stu-id="ab3c6-171">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ab3c6-172">Идентификатор пользователя, который ссылается на вызов.</span><span class="sxs-lookup"><span data-stu-id="ab3c6-172">ID of the user by who the call is referred.</span></span> <span data-ttu-id="ab3c6-173">Дополнительные сведения см. <a href="lync-server-2013-users-table.md">в таблице "Пользователи" в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ab3c6-173">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab3c6-174"><strong>ServerId</strong></span><span class="sxs-lookup"><span data-stu-id="ab3c6-174"><strong>ServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="ab3c6-175">int</span><span class="sxs-lookup"><span data-stu-id="ab3c6-175">int</span></span></p></td>
<td><p><span data-ttu-id="ab3c6-176">Правительства</span><span class="sxs-lookup"><span data-stu-id="ab3c6-176">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ab3c6-177">Идентификатор сервера переднего плана, используемого для этого сеанса.</span><span class="sxs-lookup"><span data-stu-id="ab3c6-177">ID of the front-end server used for this session.</span></span> <span data-ttu-id="ab3c6-178">Дополнительные сведения см. <a href="lync-server-2013-servers-table.md">в таблице Servers в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ab3c6-178">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab3c6-179"><strong>пулид</strong></span><span class="sxs-lookup"><span data-stu-id="ab3c6-179"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="ab3c6-180">int</span><span class="sxs-lookup"><span data-stu-id="ab3c6-180">int</span></span></p></td>
<td><p><span data-ttu-id="ab3c6-181">Правительства</span><span class="sxs-lookup"><span data-stu-id="ab3c6-181">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ab3c6-182">Идентификатор пула, в котором был записан сеанс.</span><span class="sxs-lookup"><span data-stu-id="ab3c6-182">ID of the pool in which the session was captured.</span></span> <span data-ttu-id="ab3c6-183">Дополнительные сведения см. <a href="lync-server-2013-pools-table.md">в таблице Pools в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ab3c6-183">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab3c6-184"><strong>ContentTypeID</strong></span><span class="sxs-lookup"><span data-stu-id="ab3c6-184"><strong>ContentTypeID</strong></span></span></p></td>
<td><p><span data-ttu-id="ab3c6-185">int</span><span class="sxs-lookup"><span data-stu-id="ab3c6-185">int</span></span></p></td>
<td><p><span data-ttu-id="ab3c6-186">Правительства</span><span class="sxs-lookup"><span data-stu-id="ab3c6-186">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ab3c6-187">Тип контента, используемый в сеансе.</span><span class="sxs-lookup"><span data-stu-id="ab3c6-187">Content type used in the session.</span></span> <span data-ttu-id="ab3c6-188">Для получения дополнительных сведений см <a href="lync-server-2013-contenttypes-table.md">таблицу ContentTypes в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ab3c6-188">See the <a href="lync-server-2013-contenttypes-table.md">ContentTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab3c6-189"><strong>User1ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="ab3c6-189"><strong>User1ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="ab3c6-190">int</span><span class="sxs-lookup"><span data-stu-id="ab3c6-190">int</span></span></p></td>
<td><p><span data-ttu-id="ab3c6-191">Правительства</span><span class="sxs-lookup"><span data-stu-id="ab3c6-191">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ab3c6-192">Версия клиента, применяемая пользователем User1.</span><span class="sxs-lookup"><span data-stu-id="ab3c6-192">Client version used by User1.</span></span> <span data-ttu-id="ab3c6-193">Дополнительные сведения см. <a href="lync-server-2013-clientversions-table.md">в таблице таблица clientversions в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ab3c6-193">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab3c6-194"><strong>User2ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="ab3c6-194"><strong>User2ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="ab3c6-195">int</span><span class="sxs-lookup"><span data-stu-id="ab3c6-195">int</span></span></p></td>
<td><p><span data-ttu-id="ab3c6-196">Правительства</span><span class="sxs-lookup"><span data-stu-id="ab3c6-196">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ab3c6-197">Версия клиента, применяемая пользователем User2.</span><span class="sxs-lookup"><span data-stu-id="ab3c6-197">Client version used by User2.</span></span> <span data-ttu-id="ab3c6-198">Дополнительные сведения см. <a href="lync-server-2013-clientversions-table.md">в таблице таблица clientversions в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ab3c6-198">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab3c6-199"><strong>User1EdgeServerid</strong></span><span class="sxs-lookup"><span data-stu-id="ab3c6-199"><strong>User1EdgeServerid</strong></span></span></p></td>
<td><p><span data-ttu-id="ab3c6-200">int</span><span class="sxs-lookup"><span data-stu-id="ab3c6-200">int</span></span></p></td>
<td><p><span data-ttu-id="ab3c6-201">Правительства</span><span class="sxs-lookup"><span data-stu-id="ab3c6-201">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ab3c6-202">Пограничный сервер, применяемый пользователем User1.</span><span class="sxs-lookup"><span data-stu-id="ab3c6-202">Edge Server used by User1.</span></span> <span data-ttu-id="ab3c6-203">Дополнительные сведения см. <a href="lync-server-2013-edgeservers-table.md">в таблице таблица edgeservers в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ab3c6-203">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab3c6-204"><strong>User2EdgeServerid</strong></span><span class="sxs-lookup"><span data-stu-id="ab3c6-204"><strong>User2EdgeServerid</strong></span></span></p></td>
<td><p><span data-ttu-id="ab3c6-205">int</span><span class="sxs-lookup"><span data-stu-id="ab3c6-205">int</span></span></p></td>
<td><p><span data-ttu-id="ab3c6-206">Правительства</span><span class="sxs-lookup"><span data-stu-id="ab3c6-206">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ab3c6-207">Пограничный сервер, применяемый пользователем User2.</span><span class="sxs-lookup"><span data-stu-id="ab3c6-207">Edge Server used by User2.</span></span> <span data-ttu-id="ab3c6-208">Дополнительные сведения см. <a href="lync-server-2013-edgeservers-table.md">в таблице таблица edgeservers в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ab3c6-208">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab3c6-209"><strong>IsUser1Internal</strong></span><span class="sxs-lookup"><span data-stu-id="ab3c6-209"><strong>IsUser1Internal</strong></span></span></p></td>
<td><p><span data-ttu-id="ab3c6-210">Битовая</span><span class="sxs-lookup"><span data-stu-id="ab3c6-210">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab3c6-211">Вошел ли пользователь User1 из внутренней сети или нет.</span><span class="sxs-lookup"><span data-stu-id="ab3c6-211">Whether User1 is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab3c6-212"><strong>IsUser2Internal</strong></span><span class="sxs-lookup"><span data-stu-id="ab3c6-212"><strong>IsUser2Internal</strong></span></span></p></td>
<td><p><span data-ttu-id="ab3c6-213">Битовая</span><span class="sxs-lookup"><span data-stu-id="ab3c6-213">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab3c6-214">Вошел ли пользователь User2 из внутренней сети или нет.</span><span class="sxs-lookup"><span data-stu-id="ab3c6-214">Whether User2 is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab3c6-215"><strong>инвитетиме</strong></span><span class="sxs-lookup"><span data-stu-id="ab3c6-215"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ab3c6-216">datetime</span><span class="sxs-lookup"><span data-stu-id="ab3c6-216">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab3c6-217">Время первого запроса INVITE.</span><span class="sxs-lookup"><span data-stu-id="ab3c6-217">The time of the first INVITE request.</span></span> <span data-ttu-id="ab3c6-218">Это поле обычно заполняется данными, генерируемыми из исходного сообщения INVITE в сеансе.</span><span class="sxs-lookup"><span data-stu-id="ab3c6-218">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="ab3c6-219">Если сообщения INVITE нет, поле заполняется датой и временем первого релевантного SIP-сообщения (BYE, CANCEL, MESSAGE или INFO).</span><span class="sxs-lookup"><span data-stu-id="ab3c6-219">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span> <span data-ttu-id="ab3c6-220">Это поле обычно заполняется данными, генерируемыми из исходного сообщения INVITE в сеансе.</span><span class="sxs-lookup"><span data-stu-id="ab3c6-220">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="ab3c6-221">Если сообщения INVITE нет, поле заполняется датой и временем первого релевантного SIP-сообщения (BYE, CANCEL, MESSAGE или INFO).</span><span class="sxs-lookup"><span data-stu-id="ab3c6-221">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab3c6-222"><strong>респонсетиме</strong></span><span class="sxs-lookup"><span data-stu-id="ab3c6-222"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ab3c6-223">datetime</span><span class="sxs-lookup"><span data-stu-id="ab3c6-223">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab3c6-224">Время ответа на первое сообщение INVITE.</span><span class="sxs-lookup"><span data-stu-id="ab3c6-224">The time of the response to the first INVITE message.</span></span> <span data-ttu-id="ab3c6-225">Обычно это поле содержит данные из первоначального сообщения INVITE в сеансе.</span><span class="sxs-lookup"><span data-stu-id="ab3c6-225">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="ab3c6-226">Если сообщение INVITE отсутствует, в поле записывается дата и время первого соответствующего SIP-сообщения (BYE, CANCEL, MESSAGE или INFO).</span><span class="sxs-lookup"><span data-stu-id="ab3c6-226">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab3c6-227"><strong>респонсекоде</strong></span><span class="sxs-lookup"><span data-stu-id="ab3c6-227"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="ab3c6-228">int</span><span class="sxs-lookup"><span data-stu-id="ab3c6-228">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab3c6-p121">Код SIP-ответа на приглашение в сеанс. Это поле обычно заполняется данными, генерируемыми из исходного сообщения INVITE в сеансе. Если сообщения INVITE нет, поле заполняется датой и временем первого релевантного SIP-сообщения (BYE, CANCEL, MESSAGE или INFO).</span><span class="sxs-lookup"><span data-stu-id="ab3c6-p121">SIP response code to the session invitation. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab3c6-232"><strong>диагностиЦид</strong></span><span class="sxs-lookup"><span data-stu-id="ab3c6-232"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="ab3c6-233">int</span><span class="sxs-lookup"><span data-stu-id="ab3c6-233">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab3c6-234">Идентификатор диагностики из заголовка SIP.</span><span class="sxs-lookup"><span data-stu-id="ab3c6-234">Diagnostic ID captured from SIP header.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab3c6-235"><strong>каллприорити</strong></span><span class="sxs-lookup"><span data-stu-id="ab3c6-235"><strong>CallPriority</strong></span></span></p></td>
<td><p><span data-ttu-id="ab3c6-236">int</span><span class="sxs-lookup"><span data-stu-id="ab3c6-236">int</span></span></p></td>
<td><p><span data-ttu-id="ab3c6-237">Правительства</span><span class="sxs-lookup"><span data-stu-id="ab3c6-237">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ab3c6-238">Приоритет звонка.</span><span class="sxs-lookup"><span data-stu-id="ab3c6-238">Call priority.</span></span> <span data-ttu-id="ab3c6-239">Дополнительные сведения см. <a href="lync-server-2013-callpriorities-table.md">в таблице таблица callpriorities в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ab3c6-239">See the <a href="lync-server-2013-callpriorities-table.md">CallPriorities table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab3c6-240"><strong>User1MessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="ab3c6-240"><strong>User1MessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="ab3c6-241">int</span><span class="sxs-lookup"><span data-stu-id="ab3c6-241">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab3c6-242">Число сообщений, отправленных пользователем User1 в сеансе.</span><span class="sxs-lookup"><span data-stu-id="ab3c6-242">Number of messages sent by User1 during the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab3c6-243"><strong>User2MessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="ab3c6-243"><strong>User2MessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="ab3c6-244">int</span><span class="sxs-lookup"><span data-stu-id="ab3c6-244">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab3c6-245">Число сообщений, отправленных пользователем User2 в сеансе.</span><span class="sxs-lookup"><span data-stu-id="ab3c6-245">Number of messages sent by User2 during the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab3c6-246"><strong>сессионендтиме</strong></span><span class="sxs-lookup"><span data-stu-id="ab3c6-246"><strong>SessionEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ab3c6-247">datetime</span><span class="sxs-lookup"><span data-stu-id="ab3c6-247">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab3c6-248">Время окончания сеанса.</span><span class="sxs-lookup"><span data-stu-id="ab3c6-248">Time at the end of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab3c6-249"><strong>MediaTypes</strong></span><span class="sxs-lookup"><span data-stu-id="ab3c6-249"><strong>MediaTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="ab3c6-250">int</span><span class="sxs-lookup"><span data-stu-id="ab3c6-250">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab3c6-p123">Бит, указывающий тип носителя этого сеанса. Дале перечислены определения типов:</span><span class="sxs-lookup"><span data-stu-id="ab3c6-p123">A bit set that indicates the media type of this session. Listed are the definitions of the types:</span></span></p>
<h3 id="section-1"> </h3>
<div>
<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ab3c6-253">"IM" (Обмен мгновенными сообщениями);</span><span class="sxs-lookup"><span data-stu-id="ab3c6-253">IM</span></span></p></td>
<td><p><span data-ttu-id="ab3c6-254">1,1</span><span class="sxs-lookup"><span data-stu-id="ab3c6-254">1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab3c6-255">FILE_TRANSFER</span><span class="sxs-lookup"><span data-stu-id="ab3c6-255">FILE_TRANSFER</span></span></p></td>
<td><p><span data-ttu-id="ab3c6-256">2</span><span class="sxs-lookup"><span data-stu-id="ab3c6-256">2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab3c6-257">REMOTE_ASSISTANCE</span><span class="sxs-lookup"><span data-stu-id="ab3c6-257">REMOTE_ASSISTANCE</span></span></p></td>
<td><p><span data-ttu-id="ab3c6-258">SP4</span><span class="sxs-lookup"><span data-stu-id="ab3c6-258">4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab3c6-259">APP_SHARING</span><span class="sxs-lookup"><span data-stu-id="ab3c6-259">APP_SHARING</span></span></p></td>
<td><p><span data-ttu-id="ab3c6-260">8 </span><span class="sxs-lookup"><span data-stu-id="ab3c6-260">8</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab3c6-261">ПРОИЗВЕДЕН</span><span class="sxs-lookup"><span data-stu-id="ab3c6-261">AUDIO</span></span></p></td>
<td><p><span data-ttu-id="ab3c6-262">16 </span><span class="sxs-lookup"><span data-stu-id="ab3c6-262">16</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab3c6-263">ВИДЕОМАТЕРИАЛ</span><span class="sxs-lookup"><span data-stu-id="ab3c6-263">VIDEO</span></span></p></td>
<td><p><span data-ttu-id="ab3c6-264">32</span><span class="sxs-lookup"><span data-stu-id="ab3c6-264">32</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab3c6-265">APP_INVITE</span><span class="sxs-lookup"><span data-stu-id="ab3c6-265">APP_INVITE</span></span></p></td>
<td><p><span data-ttu-id="ab3c6-266">64</span><span class="sxs-lookup"><span data-stu-id="ab3c6-266">64</span></span></p></td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab3c6-267"><strong>User1Flag</strong></span><span class="sxs-lookup"><span data-stu-id="ab3c6-267"><strong>User1Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="ab3c6-268">smallint</span><span class="sxs-lookup"><span data-stu-id="ab3c6-268">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab3c6-p124">Бит, обозначающий атрибуты пользователя User1. Далее перечислены определения атрибутов:</span><span class="sxs-lookup"><span data-stu-id="ab3c6-p124">A bit set that indicates the User1 attributes. The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="ab3c6-271">0x01 — интегрировано со стационарным телефоном</span><span class="sxs-lookup"><span data-stu-id="ab3c6-271">0x01 - Integrated with desktop phone</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab3c6-272"><strong>User2Flag</strong></span><span class="sxs-lookup"><span data-stu-id="ab3c6-272"><strong>User2Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="ab3c6-273">smallint</span><span class="sxs-lookup"><span data-stu-id="ab3c6-273">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab3c6-p125">Бит, обозначающий атрибуты пользователя User2. Далее перечислены определения атрибутов:</span><span class="sxs-lookup"><span data-stu-id="ab3c6-p125">A bit set that indicates the User2 attributes. The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="ab3c6-276">0x01 — интегрировано со стационарным телефоном</span><span class="sxs-lookup"><span data-stu-id="ab3c6-276">0x01 - Integrated with desktop phone</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab3c6-277"><strong>каллфлаг</strong></span><span class="sxs-lookup"><span data-stu-id="ab3c6-277"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="ab3c6-278">smallint</span><span class="sxs-lookup"><span data-stu-id="ab3c6-278">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab3c6-p126">Бит, обозначающий атрибуты пользователя User2. Далее перечислены определения атрибутов:</span><span class="sxs-lookup"><span data-stu-id="ab3c6-p126">A bit set that indicates the call attributes. The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="ab3c6-281">0x01 — повторенный сеанс</span><span class="sxs-lookup"><span data-stu-id="ab3c6-281">0x01 - Retried Session</span></span></p></li>
<li><p><span data-ttu-id="ab3c6-282">0x02 — вызов, выполненный агентом от имени группы ответа</span><span class="sxs-lookup"><span data-stu-id="ab3c6-282">0x02 - A call made by agent on behalf of a response group</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab3c6-283"><strong>Обработать</strong></span><span class="sxs-lookup"><span data-stu-id="ab3c6-283"><strong>Processed</strong></span></span></p></td>
<td><p><span data-ttu-id="ab3c6-284">Битовая</span><span class="sxs-lookup"><span data-stu-id="ab3c6-284">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab3c6-285">Для внутреннего использования службой мониторинга.</span><span class="sxs-lookup"><span data-stu-id="ab3c6-285">For internal use by the Monitoring service.</span></span></p>
<p><span data-ttu-id="ab3c6-286">Это поле было введено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ab3c6-286">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="ab3c6-287">\*Для большинства сеансов Сессионидсек будет иметь значение 1.</span><span class="sxs-lookup"><span data-stu-id="ab3c6-287">\* For most sessions, SessionIdSeq will have the value of 1.</span></span> <span data-ttu-id="ab3c6-288">Если несколько сеансов начинаются в одно и то же время, для одного из них SessionIdSeq будет иметь значение 1, для другого — 2 и т. д.</span><span class="sxs-lookup"><span data-stu-id="ab3c6-288">If multiple sessions start at exactly the same time, the SessionIdSeq for one will be 1, for another will be 2, and so on.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

