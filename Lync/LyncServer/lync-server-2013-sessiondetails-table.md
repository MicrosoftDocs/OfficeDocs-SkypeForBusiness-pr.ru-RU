---
title: 'Lync Server 2013: таблица SessionDetails'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: SessionDetails table
ms:assetid: 783d2508-e31f-4b54-be0c-63aa5ec21c04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398589(v=OCS.15)
ms:contentKeyID: 48184559
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: faebef9ad03370c2fa969d3b119f13b88d1d3173
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822113"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sessiondetails-table-in-lync-server-2013"></a><span data-ttu-id="049a0-102">Таблица SessionDetails в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="049a0-102">SessionDetails table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="049a0-103">_**Тема последнего изменения:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="049a0-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="049a0-104">Каждая запись представляет один одноранговый сеанс, который может быть телефонным звонком VoIP-VoIP, сеансом обмена мгновенными сообщениями с двумя субъектами или сеансом другого типа.</span><span class="sxs-lookup"><span data-stu-id="049a0-104">Each record represents one peer-to-peer session, which could be a VoIP-VoIP phone call, two-party IM session, or other type of session.</span></span> <span data-ttu-id="049a0-105">Вы можете выполнить соединение таблицы с таблицей [мультимедиа в Lync Server 2013](lync-server-2013-media-table.md) , чтобы найти подробные сведения о каждом носителе, вовлеченном в этот сеанс.</span><span class="sxs-lookup"><span data-stu-id="049a0-105">You can perform a table join with the [Media table in Lync Server 2013](lync-server-2013-media-table.md) to find the details of each media involved in this session.</span></span>

<span data-ttu-id="049a0-106">Обратите внимание, что поля IsUser1IntegratedWithDeskPhone и IsUser2IntegratedWithDeskPhone удалены из таблицы Сессиондетаилс, используемой в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="049a0-106">Note that the IsUser1IntegratedWithDeskPhone and the IsUser2IntegratedWithDeskPhone fields have been dropped from the SessionDetails table used in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="049a0-107">Столбец</span><span class="sxs-lookup"><span data-stu-id="049a0-107">Column</span></span></th>
<th><span data-ttu-id="049a0-108">Тип данных</span><span class="sxs-lookup"><span data-stu-id="049a0-108">Data Type</span></span></th>
<th><span data-ttu-id="049a0-109">Ключ/индекс</span><span class="sxs-lookup"><span data-stu-id="049a0-109">Key/Index</span></span></th>
<th><span data-ttu-id="049a0-110">Сведения</span><span class="sxs-lookup"><span data-stu-id="049a0-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="049a0-111"><strong>Сессионидтиме</strong></span><span class="sxs-lookup"><span data-stu-id="049a0-111"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="049a0-112">datetime</span><span class="sxs-lookup"><span data-stu-id="049a0-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="049a0-113">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="049a0-113">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="049a0-114">Время запроса сеанса.</span><span class="sxs-lookup"><span data-stu-id="049a0-114">Time of session request.</span></span> <span data-ttu-id="049a0-115">Используется в сочетании с <strong>сессионидсек</strong> для уникальной идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="049a0-115">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="049a0-116">Дополнительные сведения приведены <a href="lync-server-2013-dialogs-table.md">в таблице диалоговые окна Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="049a0-116">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="049a0-117"><strong>Сессионидсек</strong></span><span class="sxs-lookup"><span data-stu-id="049a0-117"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="049a0-118">целое</span><span class="sxs-lookup"><span data-stu-id="049a0-118">int</span></span></p></td>
<td><p><span data-ttu-id="049a0-119">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="049a0-119">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="049a0-120">ИДЕНТИФИКАЦИОНный номер для идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="049a0-120">ID number to identify the session.</span></span> <span data-ttu-id="049a0-121">Используется в сочетании с <strong>сессионидтиме</strong> для уникальной идентификации сеанса. \* Дополнительные сведения можно найти <a href="lync-server-2013-dialogs-table.md">в таблице диалоговые окна Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="049a0-121">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.\* See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="049a0-122"><strong>Корреляци</strong></span><span class="sxs-lookup"><span data-stu-id="049a0-122"><strong>CorrelationId</strong></span></span></p></td>
<td><p><span data-ttu-id="049a0-123">идентификатора</span><span class="sxs-lookup"><span data-stu-id="049a0-123">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="049a0-124">Идентификатор GUID для корреляции нескольких сеансов.</span><span class="sxs-lookup"><span data-stu-id="049a0-124">A GUID to correlate multiple sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="049a0-125"><strong>Реплацедиалогидтиме</strong></span><span class="sxs-lookup"><span data-stu-id="049a0-125"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="049a0-126">datetime</span><span class="sxs-lookup"><span data-stu-id="049a0-126">datetime</span></span></p></td>
<td><p><span data-ttu-id="049a0-127">Другом</span><span class="sxs-lookup"><span data-stu-id="049a0-127">Foreign</span></span></p></td>
<td><p><span data-ttu-id="049a0-128">ИДЕНТИФИКАЦИОНный номер, определяющий диалоговое окно, которое было заменено текущим сеансом.</span><span class="sxs-lookup"><span data-stu-id="049a0-128">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="049a0-129">Дополнительные сведения приведены <a href="lync-server-2013-dialogs-table.md">в таблице диалоговые окна Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="049a0-129">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="049a0-130"><strong>Реплацедиалогидсек</strong></span><span class="sxs-lookup"><span data-stu-id="049a0-130"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="049a0-131">целое</span><span class="sxs-lookup"><span data-stu-id="049a0-131">int</span></span></p></td>
<td><p><span data-ttu-id="049a0-132">Другом</span><span class="sxs-lookup"><span data-stu-id="049a0-132">Foreign</span></span></p></td>
<td><p><span data-ttu-id="049a0-133">ИДЕНТИФИКАЦИОНный номер для идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="049a0-133">ID number to identify the session.</span></span> <span data-ttu-id="049a0-134">Используется в сочетании с <strong>реплацесдиалогидтиме</strong> для уникальной идентификации сеанса, который заменяется этим сеансом.</span><span class="sxs-lookup"><span data-stu-id="049a0-134">Used in conjunction with <strong>ReplacesDialogIdTime</strong> to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="049a0-135">Дополнительные сведения приведены <a href="lync-server-2013-dialogs-table.md">в таблице диалоговые окна Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="049a0-135">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="049a0-136"><strong>User1Id</strong></span><span class="sxs-lookup"><span data-stu-id="049a0-136"><strong>User1Id</strong></span></span></p></td>
<td><p><span data-ttu-id="049a0-137">целое</span><span class="sxs-lookup"><span data-stu-id="049a0-137">int</span></span></p></td>
<td><p><span data-ttu-id="049a0-138">Другом</span><span class="sxs-lookup"><span data-stu-id="049a0-138">Foreign</span></span></p></td>
<td><p><span data-ttu-id="049a0-139">ИДЕНТИФИКАТОР одного пользователя в сеансе.</span><span class="sxs-lookup"><span data-stu-id="049a0-139">ID of one user in the session.</span></span> <span data-ttu-id="049a0-140">Дополнительные сведения <a href="lync-server-2013-users-table.md">можно найти в таблице Users (пользователи) в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="049a0-140">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="049a0-141"><strong>User2Id</strong></span><span class="sxs-lookup"><span data-stu-id="049a0-141"><strong>User2Id</strong></span></span></p></td>
<td><p><span data-ttu-id="049a0-142">целое</span><span class="sxs-lookup"><span data-stu-id="049a0-142">int</span></span></p></td>
<td><p><span data-ttu-id="049a0-143">Другом</span><span class="sxs-lookup"><span data-stu-id="049a0-143">Foreign</span></span></p></td>
<td><p><span data-ttu-id="049a0-144">ИДЕНТИФИКАТОР другого пользователя в сеансе.</span><span class="sxs-lookup"><span data-stu-id="049a0-144">ID of the other user in the session.</span></span> <span data-ttu-id="049a0-145">Дополнительные сведения <a href="lync-server-2013-users-table.md">можно найти в таблице Users (пользователи) в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="049a0-145">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="049a0-146"><strong>User1EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="049a0-146"><strong>User1EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="049a0-147">Идентификатора</span><span class="sxs-lookup"><span data-stu-id="049a0-147">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="049a0-148">Идентификатор GUID, который определяет конечную точку, используемую первым пользователем сеанса.</span><span class="sxs-lookup"><span data-stu-id="049a0-148">GUID that identifies the endpoint used by the first user in the session.</span></span></p>
<p><span data-ttu-id="049a0-149">Это поле было введено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="049a0-149">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="049a0-150"><strong>User2EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="049a0-150"><strong>User2EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="049a0-151">Идентификатора</span><span class="sxs-lookup"><span data-stu-id="049a0-151">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="049a0-152">Идентификатор GUID, который определяет конечную точку, используемую вторым пользователем в сеансе.</span><span class="sxs-lookup"><span data-stu-id="049a0-152">GUID that identifies the endpoint used by the second user in the session.</span></span></p>
<p><span data-ttu-id="049a0-153">Это поле было введено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="049a0-153">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="049a0-154"><strong>Таржетусерид</strong></span><span class="sxs-lookup"><span data-stu-id="049a0-154"><strong>TargetUserId</strong></span></span></p></td>
<td><p><span data-ttu-id="049a0-155">целое</span><span class="sxs-lookup"><span data-stu-id="049a0-155">int</span></span></p></td>
<td><p><span data-ttu-id="049a0-156">Другом</span><span class="sxs-lookup"><span data-stu-id="049a0-156">Foreign</span></span></p></td>
<td><p><span data-ttu-id="049a0-157">Исходный код ресурса (URI) пользователя в запросе SIP.</span><span class="sxs-lookup"><span data-stu-id="049a0-157">The original To user URI in the SIP request.</span></span> <span data-ttu-id="049a0-158">Дополнительные сведения <a href="lync-server-2013-users-table.md">можно найти в таблице Users (пользователи) в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="049a0-158">see the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="049a0-159"><strong>Сессионстартедбид</strong></span><span class="sxs-lookup"><span data-stu-id="049a0-159"><strong>SessionStartedById</strong></span></span></p></td>
<td><p><span data-ttu-id="049a0-160">целое</span><span class="sxs-lookup"><span data-stu-id="049a0-160">int</span></span></p></td>
<td><p><span data-ttu-id="049a0-161">Другом</span><span class="sxs-lookup"><span data-stu-id="049a0-161">Foreign</span></span></p></td>
<td><p><span data-ttu-id="049a0-162">Идентификатор пользователя, запустившего сеанс.</span><span class="sxs-lookup"><span data-stu-id="049a0-162">ID of the user who started the session.</span></span> <span data-ttu-id="049a0-163">Дополнительные сведения <a href="lync-server-2013-users-table.md">можно найти в таблице Users (пользователи) в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="049a0-163">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="049a0-164"><strong>Онбехалфофид</strong></span><span class="sxs-lookup"><span data-stu-id="049a0-164"><strong>OnBehalfOfId</strong></span></span></p></td>
<td><p><span data-ttu-id="049a0-165">целое</span><span class="sxs-lookup"><span data-stu-id="049a0-165">int</span></span></p></td>
<td><p><span data-ttu-id="049a0-166">Другом</span><span class="sxs-lookup"><span data-stu-id="049a0-166">Foreign</span></span></p></td>
<td><p><span data-ttu-id="049a0-167">Идентификатор пользователя, от имени которого вызывающим абонентом является.</span><span class="sxs-lookup"><span data-stu-id="049a0-167">Indicates the ID of the user of who the caller is on behalf.</span></span> <span data-ttu-id="049a0-168">Дополнительные сведения <a href="lync-server-2013-users-table.md">можно найти в таблице Users (пользователи) в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="049a0-168">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="049a0-169"><strong>Реферредбид</strong></span><span class="sxs-lookup"><span data-stu-id="049a0-169"><strong>ReferredById</strong></span></span></p></td>
<td><p><span data-ttu-id="049a0-170">целое</span><span class="sxs-lookup"><span data-stu-id="049a0-170">int</span></span></p></td>
<td><p><span data-ttu-id="049a0-171">Другом</span><span class="sxs-lookup"><span data-stu-id="049a0-171">Foreign</span></span></p></td>
<td><p><span data-ttu-id="049a0-172">Идентификационный номер пользователя, на который ссылается вызов.</span><span class="sxs-lookup"><span data-stu-id="049a0-172">ID of the user by who the call is referred.</span></span> <span data-ttu-id="049a0-173">Дополнительные сведения <a href="lync-server-2013-users-table.md">можно найти в таблице Users (пользователи) в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="049a0-173">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="049a0-174"><strong>Серверид</strong></span><span class="sxs-lookup"><span data-stu-id="049a0-174"><strong>ServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="049a0-175">целое</span><span class="sxs-lookup"><span data-stu-id="049a0-175">int</span></span></p></td>
<td><p><span data-ttu-id="049a0-176">Другом</span><span class="sxs-lookup"><span data-stu-id="049a0-176">Foreign</span></span></p></td>
<td><p><span data-ttu-id="049a0-177">Идентификатор сервера переднего плана, используемого для этого сеанса.</span><span class="sxs-lookup"><span data-stu-id="049a0-177">ID of the front-end server used for this session.</span></span> <span data-ttu-id="049a0-178">Более подробную информацию вы видите <a href="lync-server-2013-servers-table.md">в таблице Servers (серверы) в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="049a0-178">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="049a0-179"><strong>Пулид</strong></span><span class="sxs-lookup"><span data-stu-id="049a0-179"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="049a0-180">целое</span><span class="sxs-lookup"><span data-stu-id="049a0-180">int</span></span></p></td>
<td><p><span data-ttu-id="049a0-181">Другом</span><span class="sxs-lookup"><span data-stu-id="049a0-181">Foreign</span></span></p></td>
<td><p><span data-ttu-id="049a0-182">Идентификатор пула, в котором был собран сеанс.</span><span class="sxs-lookup"><span data-stu-id="049a0-182">ID of the pool in which the session was captured.</span></span> <span data-ttu-id="049a0-183">Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-pools-table.md">таблицей пулы в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="049a0-183">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="049a0-184"><strong>Контенттипеид</strong></span><span class="sxs-lookup"><span data-stu-id="049a0-184"><strong>ContentTypeID</strong></span></span></p></td>
<td><p><span data-ttu-id="049a0-185">целое</span><span class="sxs-lookup"><span data-stu-id="049a0-185">int</span></span></p></td>
<td><p><span data-ttu-id="049a0-186">Другом</span><span class="sxs-lookup"><span data-stu-id="049a0-186">Foreign</span></span></p></td>
<td><p><span data-ttu-id="049a0-187">Тип контента, используемый в сеансе.</span><span class="sxs-lookup"><span data-stu-id="049a0-187">Content type used in the session.</span></span> <span data-ttu-id="049a0-188">Дополнительные сведения приведены <a href="lync-server-2013-contenttypes-table.md">в таблице ContentTypes в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="049a0-188">See the <a href="lync-server-2013-contenttypes-table.md">ContentTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="049a0-189"><strong>User1ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="049a0-189"><strong>User1ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="049a0-190">целое</span><span class="sxs-lookup"><span data-stu-id="049a0-190">int</span></span></p></td>
<td><p><span data-ttu-id="049a0-191">Другом</span><span class="sxs-lookup"><span data-stu-id="049a0-191">Foreign</span></span></p></td>
<td><p><span data-ttu-id="049a0-192">Версия клиента, используемая Пользователь1.</span><span class="sxs-lookup"><span data-stu-id="049a0-192">Client version used by User1.</span></span> <span data-ttu-id="049a0-193">Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-clientversions-table.md">таблицей клиентверсионс в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="049a0-193">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="049a0-194"><strong>User2ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="049a0-194"><strong>User2ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="049a0-195">целое</span><span class="sxs-lookup"><span data-stu-id="049a0-195">int</span></span></p></td>
<td><p><span data-ttu-id="049a0-196">Другом</span><span class="sxs-lookup"><span data-stu-id="049a0-196">Foreign</span></span></p></td>
<td><p><span data-ttu-id="049a0-197">Версия клиента, используемая Пользователь2.</span><span class="sxs-lookup"><span data-stu-id="049a0-197">Client version used by User2.</span></span> <span data-ttu-id="049a0-198">Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-clientversions-table.md">таблицей клиентверсионс в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="049a0-198">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="049a0-199"><strong>User1EdgeServerid</strong></span><span class="sxs-lookup"><span data-stu-id="049a0-199"><strong>User1EdgeServerid</strong></span></span></p></td>
<td><p><span data-ttu-id="049a0-200">целое</span><span class="sxs-lookup"><span data-stu-id="049a0-200">int</span></span></p></td>
<td><p><span data-ttu-id="049a0-201">Другом</span><span class="sxs-lookup"><span data-stu-id="049a0-201">Foreign</span></span></p></td>
<td><p><span data-ttu-id="049a0-202">Пограничный сервер, используемый Пользователь1.</span><span class="sxs-lookup"><span data-stu-id="049a0-202">Edge Server used by User1.</span></span> <span data-ttu-id="049a0-203">Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-edgeservers-table.md">таблицей еджесерверс в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="049a0-203">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="049a0-204"><strong>User2EdgeServerid</strong></span><span class="sxs-lookup"><span data-stu-id="049a0-204"><strong>User2EdgeServerid</strong></span></span></p></td>
<td><p><span data-ttu-id="049a0-205">целое</span><span class="sxs-lookup"><span data-stu-id="049a0-205">int</span></span></p></td>
<td><p><span data-ttu-id="049a0-206">Другом</span><span class="sxs-lookup"><span data-stu-id="049a0-206">Foreign</span></span></p></td>
<td><p><span data-ttu-id="049a0-207">Пограничный сервер, используемый Пользователь2.</span><span class="sxs-lookup"><span data-stu-id="049a0-207">Edge Server used by User2.</span></span> <span data-ttu-id="049a0-208">Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-edgeservers-table.md">таблицей еджесерверс в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="049a0-208">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="049a0-209"><strong>IsUser1Internal</strong></span><span class="sxs-lookup"><span data-stu-id="049a0-209"><strong>IsUser1Internal</strong></span></span></p></td>
<td><p><span data-ttu-id="049a0-210">бит</span><span class="sxs-lookup"><span data-stu-id="049a0-210">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="049a0-211">Есть ли у пользователя Пользователь1 вход из внутренней сети или нет.</span><span class="sxs-lookup"><span data-stu-id="049a0-211">Whether User1 is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="049a0-212"><strong>IsUser2Internal</strong></span><span class="sxs-lookup"><span data-stu-id="049a0-212"><strong>IsUser2Internal</strong></span></span></p></td>
<td><p><span data-ttu-id="049a0-213">бит</span><span class="sxs-lookup"><span data-stu-id="049a0-213">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="049a0-214">, Вошел ли Пользователь2 из внутреннего или нет.</span><span class="sxs-lookup"><span data-stu-id="049a0-214">Whether User2 is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="049a0-215"><strong>Инвитетиме</strong></span><span class="sxs-lookup"><span data-stu-id="049a0-215"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="049a0-216">datetime</span><span class="sxs-lookup"><span data-stu-id="049a0-216">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="049a0-217">Время первого запроса приглашения.</span><span class="sxs-lookup"><span data-stu-id="049a0-217">The time of the first INVITE request.</span></span> <span data-ttu-id="049a0-218">Это поле обычно заполняется данными, созданными на основе исходного сообщения INVITE в сеансе.</span><span class="sxs-lookup"><span data-stu-id="049a0-218">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="049a0-219">Если сообщение приглашения отсутствует, поле заполняется датой и временем первого соответствующего сообщения SIP (пока, CANCEL, MESSAGE или INFO).</span><span class="sxs-lookup"><span data-stu-id="049a0-219">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span> <span data-ttu-id="049a0-220">Это поле обычно заполняется данными, созданными на основе исходного сообщения INVITE в сеансе.</span><span class="sxs-lookup"><span data-stu-id="049a0-220">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="049a0-221">Если сообщение приглашения отсутствует, поле заполняется датой и временем первого соответствующего сообщения SIP (пока, CANCEL, MESSAGE или INFO).</span><span class="sxs-lookup"><span data-stu-id="049a0-221">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="049a0-222"><strong>Респонсетиме</strong></span><span class="sxs-lookup"><span data-stu-id="049a0-222"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="049a0-223">datetime</span><span class="sxs-lookup"><span data-stu-id="049a0-223">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="049a0-224">Время ответа на первое сообщение приглашения.</span><span class="sxs-lookup"><span data-stu-id="049a0-224">The time of the response to the first INVITE message.</span></span> <span data-ttu-id="049a0-225">Это поле обычно заполняется данными, созданными на основе исходного сообщения INVITE в сеансе.</span><span class="sxs-lookup"><span data-stu-id="049a0-225">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="049a0-226">Если сообщение приглашения отсутствует, поле заполняется датой и временем первого соответствующего сообщения SIP (пока, CANCEL, MESSAGE или INFO).</span><span class="sxs-lookup"><span data-stu-id="049a0-226">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="049a0-227"><strong>Респонсекоде</strong></span><span class="sxs-lookup"><span data-stu-id="049a0-227"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="049a0-228">целое</span><span class="sxs-lookup"><span data-stu-id="049a0-228">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="049a0-229">Код ответа SIP на приглашение на сеанс.</span><span class="sxs-lookup"><span data-stu-id="049a0-229">SIP response code to the session invitation.</span></span> <span data-ttu-id="049a0-230">Это поле обычно заполняется данными, созданными на основе исходного сообщения INVITE в сеансе.</span><span class="sxs-lookup"><span data-stu-id="049a0-230">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="049a0-231">Если сообщение приглашения отсутствует, поле заполняется датой и временем первого соответствующего сообщения SIP (пока, CANCEL, MESSAGE или INFO).</span><span class="sxs-lookup"><span data-stu-id="049a0-231">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="049a0-232"><strong>ДиагностиЦид</strong></span><span class="sxs-lookup"><span data-stu-id="049a0-232"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="049a0-233">целое</span><span class="sxs-lookup"><span data-stu-id="049a0-233">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="049a0-234">Идентификатор диагностики, полученный в заголовке SIP.</span><span class="sxs-lookup"><span data-stu-id="049a0-234">Diagnostic ID captured from SIP header.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="049a0-235"><strong>Каллприорити</strong></span><span class="sxs-lookup"><span data-stu-id="049a0-235"><strong>CallPriority</strong></span></span></p></td>
<td><p><span data-ttu-id="049a0-236">целое</span><span class="sxs-lookup"><span data-stu-id="049a0-236">int</span></span></p></td>
<td><p><span data-ttu-id="049a0-237">Другом</span><span class="sxs-lookup"><span data-stu-id="049a0-237">Foreign</span></span></p></td>
<td><p><span data-ttu-id="049a0-238">Приоритет звонка.</span><span class="sxs-lookup"><span data-stu-id="049a0-238">Call priority.</span></span> <span data-ttu-id="049a0-239">Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-callpriorities-table.md">таблицей каллприоритиес в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="049a0-239">See the <a href="lync-server-2013-callpriorities-table.md">CallPriorities table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="049a0-240"><strong>User1MessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="049a0-240"><strong>User1MessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="049a0-241">целое</span><span class="sxs-lookup"><span data-stu-id="049a0-241">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="049a0-242">Количество сообщений, отправленных Пользователь1 в течение сеанса.</span><span class="sxs-lookup"><span data-stu-id="049a0-242">Number of messages sent by User1 during the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="049a0-243"><strong>User2MessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="049a0-243"><strong>User2MessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="049a0-244">целое</span><span class="sxs-lookup"><span data-stu-id="049a0-244">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="049a0-245">Количество сообщений, отправленных Пользователь2 во время сеанса.</span><span class="sxs-lookup"><span data-stu-id="049a0-245">Number of messages sent by User2 during the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="049a0-246"><strong>Сессионендтиме</strong></span><span class="sxs-lookup"><span data-stu-id="049a0-246"><strong>SessionEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="049a0-247">datetime</span><span class="sxs-lookup"><span data-stu-id="049a0-247">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="049a0-248">Время окончания сеанса.</span><span class="sxs-lookup"><span data-stu-id="049a0-248">Time at the end of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="049a0-249"><strong>Медиатипес</strong></span><span class="sxs-lookup"><span data-stu-id="049a0-249"><strong>MediaTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="049a0-250">целое</span><span class="sxs-lookup"><span data-stu-id="049a0-250">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="049a0-251">Битовый набор, указывающий тип мультимедиа для этого сеанса.</span><span class="sxs-lookup"><span data-stu-id="049a0-251">A bit set that indicates the media type of this session.</span></span> <span data-ttu-id="049a0-252">Ниже перечислены определения типов.</span><span class="sxs-lookup"><span data-stu-id="049a0-252">Listed are the definitions of the types:</span></span></p>
<h3 id="section-1"> </h3>
<div>
<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="049a0-253">Сообщения</span><span class="sxs-lookup"><span data-stu-id="049a0-253">IM</span></span></p></td>
<td><p><span data-ttu-id="049a0-254">1</span><span class="sxs-lookup"><span data-stu-id="049a0-254">1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="049a0-255">ФИЛЕ_ТРАНСФЕР</span><span class="sxs-lookup"><span data-stu-id="049a0-255">FILE_TRANSFER</span></span></p></td>
<td><p><span data-ttu-id="049a0-256">2</span><span class="sxs-lookup"><span data-stu-id="049a0-256">2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="049a0-257">РЕМОТЕ_АССИСТАНЦЕ</span><span class="sxs-lookup"><span data-stu-id="049a0-257">REMOTE_ASSISTANCE</span></span></p></td>
<td><p><span data-ttu-id="049a0-258">4</span><span class="sxs-lookup"><span data-stu-id="049a0-258">4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="049a0-259">АПП_ШАРИНГ</span><span class="sxs-lookup"><span data-stu-id="049a0-259">APP_SHARING</span></span></p></td>
<td><p><span data-ttu-id="049a0-260">No8</span><span class="sxs-lookup"><span data-stu-id="049a0-260">8</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="049a0-261">ЗВУКОВ</span><span class="sxs-lookup"><span data-stu-id="049a0-261">AUDIO</span></span></p></td>
<td><p><span data-ttu-id="049a0-262">шестнадцат</span><span class="sxs-lookup"><span data-stu-id="049a0-262">16</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="049a0-263">ВИЗУАЛИЗАЦИИ</span><span class="sxs-lookup"><span data-stu-id="049a0-263">VIDEO</span></span></p></td>
<td><p><span data-ttu-id="049a0-264">32</span><span class="sxs-lookup"><span data-stu-id="049a0-264">32</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="049a0-265">АПП_ИНВИТЕ</span><span class="sxs-lookup"><span data-stu-id="049a0-265">APP_INVITE</span></span></p></td>
<td><p><span data-ttu-id="049a0-266">64</span><span class="sxs-lookup"><span data-stu-id="049a0-266">64</span></span></p></td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="049a0-267"><strong>User1Flag</strong></span><span class="sxs-lookup"><span data-stu-id="049a0-267"><strong>User1Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="049a0-268">smallint</span><span class="sxs-lookup"><span data-stu-id="049a0-268">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="049a0-269">Битовый набор, обозначающий атрибуты User1.</span><span class="sxs-lookup"><span data-stu-id="049a0-269">A bit set that indicates the User1 attributes.</span></span> <span data-ttu-id="049a0-270">Следующие определения атрибутов перечислены ниже.</span><span class="sxs-lookup"><span data-stu-id="049a0-270">The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="049a0-271">0x01 — интеграция с настольным телефоном</span><span class="sxs-lookup"><span data-stu-id="049a0-271">0x01 - Integrated with desktop phone</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="049a0-272"><strong>User2Flag</strong></span><span class="sxs-lookup"><span data-stu-id="049a0-272"><strong>User2Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="049a0-273">smallint</span><span class="sxs-lookup"><span data-stu-id="049a0-273">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="049a0-274">Битовый набор, обозначающий атрибуты Пользователь2.</span><span class="sxs-lookup"><span data-stu-id="049a0-274">A bit set that indicates the User2 attributes.</span></span> <span data-ttu-id="049a0-275">Следующие определения атрибутов перечислены ниже.</span><span class="sxs-lookup"><span data-stu-id="049a0-275">The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="049a0-276">0x01 — интеграция с настольным телефоном</span><span class="sxs-lookup"><span data-stu-id="049a0-276">0x01 - Integrated with desktop phone</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="049a0-277"><strong>Каллфлаг</strong></span><span class="sxs-lookup"><span data-stu-id="049a0-277"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="049a0-278">smallint</span><span class="sxs-lookup"><span data-stu-id="049a0-278">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="049a0-279">Битовый набор, обозначающий атрибуты вызова.</span><span class="sxs-lookup"><span data-stu-id="049a0-279">A bit set that indicates the call attributes.</span></span> <span data-ttu-id="049a0-280">Следующие определения атрибутов перечислены ниже.</span><span class="sxs-lookup"><span data-stu-id="049a0-280">The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="049a0-281">0x01 — сеанс повторной попытки</span><span class="sxs-lookup"><span data-stu-id="049a0-281">0x01 - Retried Session</span></span></p></li>
<li><p><span data-ttu-id="049a0-282">0x02 — вызов, сделанный агентом от имени группы ответа</span><span class="sxs-lookup"><span data-stu-id="049a0-282">0x02 - A call made by agent on behalf of a response group</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="049a0-283"><strong>Обработка</strong></span><span class="sxs-lookup"><span data-stu-id="049a0-283"><strong>Processed</strong></span></span></p></td>
<td><p><span data-ttu-id="049a0-284">бит</span><span class="sxs-lookup"><span data-stu-id="049a0-284">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="049a0-285">Для внутреннего использования службой мониторинга.</span><span class="sxs-lookup"><span data-stu-id="049a0-285">For internal use by the Monitoring service.</span></span></p>
<p><span data-ttu-id="049a0-286">Это поле было введено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="049a0-286">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="049a0-287">\*Для большинства сеансов для Сессионидсек будет задано значение 1.</span><span class="sxs-lookup"><span data-stu-id="049a0-287">\* For most sessions, SessionIdSeq will have the value of 1.</span></span> <span data-ttu-id="049a0-288">Если несколько сеансов начинаются в одно и то же время, Сессионидсек для одного из них будет равен 1, а для другого — 2 и т. д.</span><span class="sxs-lookup"><span data-stu-id="049a0-288">If multiple sessions start at exactly the same time, the SessionIdSeq for one will be 1, for another will be 2, and so on.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

