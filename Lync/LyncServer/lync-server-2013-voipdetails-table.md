---
title: 'Lync Server 2013: таблица VoipDetails'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: VoipDetails table
ms:assetid: 74ffbb71-569b-4018-be1f-4db2bbafcf36
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398566(v=OCS.15)
ms:contentKeyID: 48184522
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f13087202b15cf9b25f0c32741c396c48f628908
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758561"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="voipdetails-table-in-lync-server-2013"></a><span data-ttu-id="f431a-102">Таблица VoipDetails в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f431a-102">VoipDetails table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f431a-103">_**Тема последнего изменения:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="f431a-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="f431a-104">Каждая запись представляет вызов на стороне 1 2, в котором как минимум один пользователь является пользователем VoIP.</span><span class="sxs-lookup"><span data-stu-id="f431a-104">Each record represents one two-party call in which at least one user is a VoIP user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f431a-105">Столбец</span><span class="sxs-lookup"><span data-stu-id="f431a-105">Column</span></span></th>
<th><span data-ttu-id="f431a-106">Тип данных</span><span class="sxs-lookup"><span data-stu-id="f431a-106">Data Type</span></span></th>
<th><span data-ttu-id="f431a-107">Ключ/индекс</span><span class="sxs-lookup"><span data-stu-id="f431a-107">Key/Index</span></span></th>
<th><span data-ttu-id="f431a-108">Сведения</span><span class="sxs-lookup"><span data-stu-id="f431a-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f431a-109"><strong>сессионидтиме</strong></span><span class="sxs-lookup"><span data-stu-id="f431a-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f431a-110">datetime</span><span class="sxs-lookup"><span data-stu-id="f431a-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="f431a-111">Primary</span><span class="sxs-lookup"><span data-stu-id="f431a-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="f431a-112">Время запроса сеанса.</span><span class="sxs-lookup"><span data-stu-id="f431a-112">Time of session request.</span></span> <span data-ttu-id="f431a-113">Используется в сочетании с <strong>сессионидсек</strong> для уникальной идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="f431a-113">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="f431a-114">Дополнительные сведения приведены <a href="lync-server-2013-dialogs-table.md">в таблице диалоговые окна Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f431a-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f431a-115"><strong>сессионидсек</strong></span><span class="sxs-lookup"><span data-stu-id="f431a-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="f431a-116">целое</span><span class="sxs-lookup"><span data-stu-id="f431a-116">int</span></span></p></td>
<td><p><span data-ttu-id="f431a-117">Primary</span><span class="sxs-lookup"><span data-stu-id="f431a-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="f431a-118">ИДЕНТИФИКАЦИОНный номер для идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="f431a-118">ID number to identify the session.</span></span> <span data-ttu-id="f431a-119">Используется в сочетании с <strong>сессионидтиме</strong> для уникальной идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="f431a-119">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="f431a-120">Дополнительные сведения приведены <a href="lync-server-2013-dialogs-table.md">в таблице диалоговые окна Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f431a-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f431a-121"><strong>фромнумберид</strong></span><span class="sxs-lookup"><span data-stu-id="f431a-121"><strong>FromNumberId</strong></span></span></p></td>
<td><p><span data-ttu-id="f431a-122">целое</span><span class="sxs-lookup"><span data-stu-id="f431a-122">int</span></span></p></td>
<td><p><span data-ttu-id="f431a-123">Другом</span><span class="sxs-lookup"><span data-stu-id="f431a-123">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f431a-124"><strong>Фонеид</strong> вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="f431a-124"><strong>PhoneId</strong> of the caller.</span></span> <span data-ttu-id="f431a-125">Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-phones-table.md">таблицей "телефоны" в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f431a-125">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="f431a-126">Если NOT NULL и <strong>фромгатевайид</strong> не NULL, вызывающий абонент являлся пользователем КТСОП.</span><span class="sxs-lookup"><span data-stu-id="f431a-126">If not NULL and <strong>FromGatewayId</strong> is not NULL, then the caller was a PSTN user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f431a-127"><strong>коннектеднумберид</strong></span><span class="sxs-lookup"><span data-stu-id="f431a-127"><strong>ConnectedNumberId</strong></span></span></p></td>
<td><p><span data-ttu-id="f431a-128">целое</span><span class="sxs-lookup"><span data-stu-id="f431a-128">int</span></span></p></td>
<td><p><span data-ttu-id="f431a-129">Другом</span><span class="sxs-lookup"><span data-stu-id="f431a-129">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f431a-130"><strong>Фонеид</strong> получателя звонка.</span><span class="sxs-lookup"><span data-stu-id="f431a-130"><strong>PhoneId</strong> of the call receiver.</span></span> <span data-ttu-id="f431a-131">Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-phones-table.md">таблицей "телефоны" в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f431a-131">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="f431a-132">Если NOT NULL и <strong>тогатевайид</strong> не NULL, получатель звонка был пользователем КТСОП.</span><span class="sxs-lookup"><span data-stu-id="f431a-132">If not NULL and <strong>ToGatewayId</strong> is not NULL, then the call receiver was a PSTN user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f431a-133"><strong>фроммедиатионсерверид</strong></span><span class="sxs-lookup"><span data-stu-id="f431a-133"><strong>FromMediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="f431a-134">целое</span><span class="sxs-lookup"><span data-stu-id="f431a-134">int</span></span></p></td>
<td><p><span data-ttu-id="f431a-135">Другом</span><span class="sxs-lookup"><span data-stu-id="f431a-135">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f431a-136">Сервер, на котором поступил звонок.</span><span class="sxs-lookup"><span data-stu-id="f431a-136">The Mediation Server the call is coming from.</span></span> <span data-ttu-id="f431a-137">Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-mediationservers-table.md">таблицей медиатионсерверс в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f431a-137">See the <a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f431a-138"><strong>томедиатионсерверид</strong></span><span class="sxs-lookup"><span data-stu-id="f431a-138"><strong>ToMediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="f431a-139">целое</span><span class="sxs-lookup"><span data-stu-id="f431a-139">int</span></span></p></td>
<td><p><span data-ttu-id="f431a-140">Другом</span><span class="sxs-lookup"><span data-stu-id="f431a-140">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f431a-141">Будет вызываем сервер для устранения проблем.</span><span class="sxs-lookup"><span data-stu-id="f431a-141">The Mediation Server called is going to.</span></span> <span data-ttu-id="f431a-142">Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-mediationservers-table.md">таблицей медиатионсерверс в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f431a-142">See the <a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f431a-143"><strong>фромгатевайид</strong></span><span class="sxs-lookup"><span data-stu-id="f431a-143"><strong>FromGatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="f431a-144">целое</span><span class="sxs-lookup"><span data-stu-id="f431a-144">int</span></span></p></td>
<td><p><span data-ttu-id="f431a-145">Другом</span><span class="sxs-lookup"><span data-stu-id="f431a-145">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f431a-146">Шлюз, из которого поступил звонок.</span><span class="sxs-lookup"><span data-stu-id="f431a-146">Gateway the call is coming from.</span></span> <span data-ttu-id="f431a-147">Более подробную информацию вы увидите <a href="lync-server-2013-gateways-table.md">в таблице шлюзов в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f431a-147">See the <a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f431a-148"><strong>тогатевайид</strong></span><span class="sxs-lookup"><span data-stu-id="f431a-148"><strong>ToGatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="f431a-149">целое</span><span class="sxs-lookup"><span data-stu-id="f431a-149">int</span></span></p></td>
<td><p><span data-ttu-id="f431a-150">Другом</span><span class="sxs-lookup"><span data-stu-id="f431a-150">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f431a-151">Шлюз, на который проходит звонок.</span><span class="sxs-lookup"><span data-stu-id="f431a-151">Gateway the call is going to.</span></span> <span data-ttu-id="f431a-152">Более подробную информацию вы увидите <a href="lync-server-2013-gateways-table.md">в таблице шлюзов в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f431a-152">See the <a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f431a-153"><strong>дисконнектедбюриид</strong></span><span class="sxs-lookup"><span data-stu-id="f431a-153"><strong>DisconnectedbyURIId</strong></span></span></p></td>
<td><p><span data-ttu-id="f431a-154">целое</span><span class="sxs-lookup"><span data-stu-id="f431a-154">int</span></span></p></td>
<td><p><span data-ttu-id="f431a-155">Другом</span><span class="sxs-lookup"><span data-stu-id="f431a-155">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f431a-156">Универсальный код ресурса (URI) пользователя, который отключил звонок, если пользователь имеет URI.</span><span class="sxs-lookup"><span data-stu-id="f431a-156">URI of the user who disconnected the call, if the user has a URI.</span></span> <span data-ttu-id="f431a-157">Дополнительные сведения <a href="lync-server-2013-users-table.md">можно найти в таблице Users (пользователи) в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f431a-157">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f431a-158"><strong>дисконнектедбифонеид</strong></span><span class="sxs-lookup"><span data-stu-id="f431a-158"><strong>DisconnectedbyPhoneId</strong></span></span></p></td>
<td><p><span data-ttu-id="f431a-159">целое</span><span class="sxs-lookup"><span data-stu-id="f431a-159">int</span></span></p></td>
<td><p><span data-ttu-id="f431a-160">Другом</span><span class="sxs-lookup"><span data-stu-id="f431a-160">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f431a-161">Идентификационный номер телефона, который отключил звонок, был отключен от телефона.</span><span class="sxs-lookup"><span data-stu-id="f431a-161">ID of the phone that disconnected the call was disconnected from a phone.</span></span> <span data-ttu-id="f431a-162">Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-phones-table.md">таблицей "телефоны" в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f431a-162">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

