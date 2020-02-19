---
title: 'Lync Server 2013: таблица таблица voipdetails'
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
ms.openlocfilehash: 4aac4ae26de4c80f7ed1396e647701a0b49a1c4f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42119242"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="voipdetails-table-in-lync-server-2013"></a><span data-ttu-id="26552-102">Таблица Таблица voipdetails в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="26552-102">VoipDetails table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="26552-103">_**Последнее изменение темы:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="26552-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="26552-104">Каждая запись представляет двусторонний звонок, по крайней мере один участник которого является пользователем VoIP.</span><span class="sxs-lookup"><span data-stu-id="26552-104">Each record represents one two-party call in which at least one user is a VoIP user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="26552-105">Столбец</span><span class="sxs-lookup"><span data-stu-id="26552-105">Column</span></span></th>
<th><span data-ttu-id="26552-106">Тип данных</span><span class="sxs-lookup"><span data-stu-id="26552-106">Data Type</span></span></th>
<th><span data-ttu-id="26552-107">Ключ или индекс</span><span class="sxs-lookup"><span data-stu-id="26552-107">Key/Index</span></span></th>
<th><span data-ttu-id="26552-108">Сведения</span><span class="sxs-lookup"><span data-stu-id="26552-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="26552-109"><strong>сессионидтиме</strong></span><span class="sxs-lookup"><span data-stu-id="26552-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="26552-110">datetime</span><span class="sxs-lookup"><span data-stu-id="26552-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="26552-111">Primary</span><span class="sxs-lookup"><span data-stu-id="26552-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="26552-112">Время запроса сеанса.</span><span class="sxs-lookup"><span data-stu-id="26552-112">Time of session request.</span></span> <span data-ttu-id="26552-113">В сочетании с параметром <strong>SessionIdSeq</strong> определяет сеанс уникальным образом.</span><span class="sxs-lookup"><span data-stu-id="26552-113">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="26552-114">Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="26552-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="26552-115"><strong>сессионидсек</strong></span><span class="sxs-lookup"><span data-stu-id="26552-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="26552-116">int</span><span class="sxs-lookup"><span data-stu-id="26552-116">int</span></span></p></td>
<td><p><span data-ttu-id="26552-117">Primary</span><span class="sxs-lookup"><span data-stu-id="26552-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="26552-118">Идентификатор сеанса.</span><span class="sxs-lookup"><span data-stu-id="26552-118">ID number to identify the session.</span></span> <span data-ttu-id="26552-119">В сочетании с параметром <strong>SessionIdTime</strong> определяет сеанс уникальным образом.</span><span class="sxs-lookup"><span data-stu-id="26552-119">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="26552-120">Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="26552-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="26552-121"><strong>фромнумберид</strong></span><span class="sxs-lookup"><span data-stu-id="26552-121"><strong>FromNumberId</strong></span></span></p></td>
<td><p><span data-ttu-id="26552-122">int</span><span class="sxs-lookup"><span data-stu-id="26552-122">int</span></span></p></td>
<td><p><span data-ttu-id="26552-123">Правительства</span><span class="sxs-lookup"><span data-stu-id="26552-123">Foreign</span></span></p></td>
<td><p><span data-ttu-id="26552-124">Идентификатор <strong>PhoneId</strong> звонящего.</span><span class="sxs-lookup"><span data-stu-id="26552-124"><strong>PhoneId</strong> of the caller.</span></span> <span data-ttu-id="26552-125">Дополнительные сведения см. <a href="lync-server-2013-phones-table.md">в таблице phones в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="26552-125">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="26552-126">Если значение этого параметра, а также параметра <strong>FromGatewayId</strong> отлично от NULL, звонящий являлся пользователем ТСОП.</span><span class="sxs-lookup"><span data-stu-id="26552-126">If not NULL and <strong>FromGatewayId</strong> is not NULL, then the caller was a PSTN user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="26552-127"><strong>коннектеднумберид</strong></span><span class="sxs-lookup"><span data-stu-id="26552-127"><strong>ConnectedNumberId</strong></span></span></p></td>
<td><p><span data-ttu-id="26552-128">int</span><span class="sxs-lookup"><span data-stu-id="26552-128">int</span></span></p></td>
<td><p><span data-ttu-id="26552-129">Правительства</span><span class="sxs-lookup"><span data-stu-id="26552-129">Foreign</span></span></p></td>
<td><p><span data-ttu-id="26552-130">Идентификатор <strong>PhoneId</strong> получателя звонка.</span><span class="sxs-lookup"><span data-stu-id="26552-130"><strong>PhoneId</strong> of the call receiver.</span></span> <span data-ttu-id="26552-131">Дополнительные сведения см. <a href="lync-server-2013-phones-table.md">в таблице phones в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="26552-131">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="26552-132">Если значение этого параметра, а также параметра <strong>ToGatewayId</strong> отлично от NULL, получатель являлся пользователем ТСОП.</span><span class="sxs-lookup"><span data-stu-id="26552-132">If not NULL and <strong>ToGatewayId</strong> is not NULL, then the call receiver was a PSTN user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="26552-133"><strong>фроммедиатионсерверид</strong></span><span class="sxs-lookup"><span data-stu-id="26552-133"><strong>FromMediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="26552-134">int</span><span class="sxs-lookup"><span data-stu-id="26552-134">int</span></span></p></td>
<td><p><span data-ttu-id="26552-135">Правительства</span><span class="sxs-lookup"><span data-stu-id="26552-135">Foreign</span></span></p></td>
<td><p><span data-ttu-id="26552-136">Сервер-посредник, с которого поступил звонок.</span><span class="sxs-lookup"><span data-stu-id="26552-136">The Mediation Server the call is coming from.</span></span> <span data-ttu-id="26552-137">Дополнительные сведения см. <a href="lync-server-2013-mediationservers-table.md">в таблице таблица mediationservers в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="26552-137">See the <a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="26552-138"><strong>томедиатионсерверид</strong></span><span class="sxs-lookup"><span data-stu-id="26552-138"><strong>ToMediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="26552-139">int</span><span class="sxs-lookup"><span data-stu-id="26552-139">int</span></span></p></td>
<td><p><span data-ttu-id="26552-140">Правительства</span><span class="sxs-lookup"><span data-stu-id="26552-140">Foreign</span></span></p></td>
<td><p><span data-ttu-id="26552-141">Сервер-посредник, на который направляется звонок.</span><span class="sxs-lookup"><span data-stu-id="26552-141">The Mediation Server called is going to.</span></span> <span data-ttu-id="26552-142">Дополнительные сведения см. <a href="lync-server-2013-mediationservers-table.md">в таблице таблица mediationservers в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="26552-142">See the <a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="26552-143"><strong>фромгатевайид</strong></span><span class="sxs-lookup"><span data-stu-id="26552-143"><strong>FromGatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="26552-144">int</span><span class="sxs-lookup"><span data-stu-id="26552-144">int</span></span></p></td>
<td><p><span data-ttu-id="26552-145">Правительства</span><span class="sxs-lookup"><span data-stu-id="26552-145">Foreign</span></span></p></td>
<td><p><span data-ttu-id="26552-146">Шлюз, из которого поступил звонок.</span><span class="sxs-lookup"><span data-stu-id="26552-146">Gateway the call is coming from.</span></span> <span data-ttu-id="26552-147">Более подробную информацию можно узнать <a href="lync-server-2013-gateways-table.md">в таблице шлюзы в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="26552-147">See the <a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="26552-148"><strong>тогатевайид</strong></span><span class="sxs-lookup"><span data-stu-id="26552-148"><strong>ToGatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="26552-149">int</span><span class="sxs-lookup"><span data-stu-id="26552-149">int</span></span></p></td>
<td><p><span data-ttu-id="26552-150">Правительства</span><span class="sxs-lookup"><span data-stu-id="26552-150">Foreign</span></span></p></td>
<td><p><span data-ttu-id="26552-151">Шлюз, на который направляется звонок.</span><span class="sxs-lookup"><span data-stu-id="26552-151">Gateway the call is going to.</span></span> <span data-ttu-id="26552-152">Более подробную информацию можно узнать <a href="lync-server-2013-gateways-table.md">в таблице шлюзы в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="26552-152">See the <a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="26552-153"><strong>дисконнектедбюриид</strong></span><span class="sxs-lookup"><span data-stu-id="26552-153"><strong>DisconnectedbyURIId</strong></span></span></p></td>
<td><p><span data-ttu-id="26552-154">int</span><span class="sxs-lookup"><span data-stu-id="26552-154">int</span></span></p></td>
<td><p><span data-ttu-id="26552-155">Правительства</span><span class="sxs-lookup"><span data-stu-id="26552-155">Foreign</span></span></p></td>
<td><p><span data-ttu-id="26552-156">Универсальный код ресурса (URI) пользователя, прервавшего звонок (если имеется).</span><span class="sxs-lookup"><span data-stu-id="26552-156">URI of the user who disconnected the call, if the user has a URI.</span></span> <span data-ttu-id="26552-157">Дополнительные сведения см. <a href="lync-server-2013-users-table.md">в таблице "Пользователи" в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="26552-157">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="26552-158"><strong>дисконнектедбифонеид</strong></span><span class="sxs-lookup"><span data-stu-id="26552-158"><strong>DisconnectedbyPhoneId</strong></span></span></p></td>
<td><p><span data-ttu-id="26552-159">int</span><span class="sxs-lookup"><span data-stu-id="26552-159">int</span></span></p></td>
<td><p><span data-ttu-id="26552-160">Правительства</span><span class="sxs-lookup"><span data-stu-id="26552-160">Foreign</span></span></p></td>
<td><p><span data-ttu-id="26552-161">ИД телефона, с которого был прерван звонок.</span><span class="sxs-lookup"><span data-stu-id="26552-161">ID of the phone that disconnected the call was disconnected from a phone.</span></span> <span data-ttu-id="26552-162">Дополнительные сведения см. <a href="lync-server-2013-phones-table.md">в таблице phones в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="26552-162">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

