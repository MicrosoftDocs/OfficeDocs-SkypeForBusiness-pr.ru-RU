---
title: 'Lync Server 2013: таблица таблица voipdetails'
description: 'Lync Server 2013: таблица таблица voipdetails.'
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
ms.openlocfilehash: f23d991c1d577a15717de2572d744e1b65ba6bab
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566285"
---
# <a name="voipdetails-table-in-lync-server-2013"></a><span data-ttu-id="1b145-103">Таблица Таблица voipdetails в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1b145-103">VoipDetails table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1b145-104">_**Последнее изменение темы:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="1b145-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="1b145-105">Каждая запись представляет двусторонний звонок, по крайней мере один участник которого является пользователем VoIP.</span><span class="sxs-lookup"><span data-stu-id="1b145-105">Each record represents one two-party call in which at least one user is a VoIP user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1b145-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="1b145-106">Column</span></span></th>
<th><span data-ttu-id="1b145-107">Тип данных</span><span class="sxs-lookup"><span data-stu-id="1b145-107">Data Type</span></span></th>
<th><span data-ttu-id="1b145-108">Ключ или индекс</span><span class="sxs-lookup"><span data-stu-id="1b145-108">Key/Index</span></span></th>
<th><span data-ttu-id="1b145-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="1b145-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1b145-110"><strong>сессионидтиме</strong></span><span class="sxs-lookup"><span data-stu-id="1b145-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="1b145-111">datetime</span><span class="sxs-lookup"><span data-stu-id="1b145-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="1b145-112">Primary</span><span class="sxs-lookup"><span data-stu-id="1b145-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="1b145-113">Время запроса сеанса.</span><span class="sxs-lookup"><span data-stu-id="1b145-113">Time of session request.</span></span> <span data-ttu-id="1b145-114">В сочетании с параметром <strong>SessionIdSeq</strong> определяет сеанс уникальным образом.</span><span class="sxs-lookup"><span data-stu-id="1b145-114">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="1b145-115">Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="1b145-115">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b145-116"><strong>сессионидсек</strong></span><span class="sxs-lookup"><span data-stu-id="1b145-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="1b145-117">int</span><span class="sxs-lookup"><span data-stu-id="1b145-117">int</span></span></p></td>
<td><p><span data-ttu-id="1b145-118">Primary</span><span class="sxs-lookup"><span data-stu-id="1b145-118">Primary</span></span></p></td>
<td><p><span data-ttu-id="1b145-119">Идентификатор сеанса.</span><span class="sxs-lookup"><span data-stu-id="1b145-119">ID number to identify the session.</span></span> <span data-ttu-id="1b145-120">В сочетании с параметром <strong>SessionIdTime</strong> определяет сеанс уникальным образом.</span><span class="sxs-lookup"><span data-stu-id="1b145-120">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="1b145-121">Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="1b145-121">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b145-122"><strong>фромнумберид</strong></span><span class="sxs-lookup"><span data-stu-id="1b145-122"><strong>FromNumberId</strong></span></span></p></td>
<td><p><span data-ttu-id="1b145-123">int</span><span class="sxs-lookup"><span data-stu-id="1b145-123">int</span></span></p></td>
<td><p><span data-ttu-id="1b145-124">Правительства</span><span class="sxs-lookup"><span data-stu-id="1b145-124">Foreign</span></span></p></td>
<td><p><span data-ttu-id="1b145-125">Идентификатор <strong>PhoneId</strong> звонящего.</span><span class="sxs-lookup"><span data-stu-id="1b145-125"><strong>PhoneId</strong> of the caller.</span></span> <span data-ttu-id="1b145-126">Дополнительные сведения см. <a href="lync-server-2013-phones-table.md">в таблице phones в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="1b145-126">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="1b145-127">Если значение этого параметра, а также параметра <strong>FromGatewayId</strong> отлично от NULL, звонящий являлся пользователем ТСОП.</span><span class="sxs-lookup"><span data-stu-id="1b145-127">If not NULL and <strong>FromGatewayId</strong> is not NULL, then the caller was a PSTN user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b145-128"><strong>коннектеднумберид</strong></span><span class="sxs-lookup"><span data-stu-id="1b145-128"><strong>ConnectedNumberId</strong></span></span></p></td>
<td><p><span data-ttu-id="1b145-129">int</span><span class="sxs-lookup"><span data-stu-id="1b145-129">int</span></span></p></td>
<td><p><span data-ttu-id="1b145-130">Правительства</span><span class="sxs-lookup"><span data-stu-id="1b145-130">Foreign</span></span></p></td>
<td><p><span data-ttu-id="1b145-131">Идентификатор <strong>PhoneId</strong> получателя звонка.</span><span class="sxs-lookup"><span data-stu-id="1b145-131"><strong>PhoneId</strong> of the call receiver.</span></span> <span data-ttu-id="1b145-132">Дополнительные сведения см. <a href="lync-server-2013-phones-table.md">в таблице phones в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="1b145-132">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="1b145-133">Если значение этого параметра, а также параметра <strong>ToGatewayId</strong> отлично от NULL, получатель являлся пользователем ТСОП.</span><span class="sxs-lookup"><span data-stu-id="1b145-133">If not NULL and <strong>ToGatewayId</strong> is not NULL, then the call receiver was a PSTN user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b145-134"><strong>фроммедиатионсерверид</strong></span><span class="sxs-lookup"><span data-stu-id="1b145-134"><strong>FromMediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="1b145-135">int</span><span class="sxs-lookup"><span data-stu-id="1b145-135">int</span></span></p></td>
<td><p><span data-ttu-id="1b145-136">Правительства</span><span class="sxs-lookup"><span data-stu-id="1b145-136">Foreign</span></span></p></td>
<td><p><span data-ttu-id="1b145-137">Сервер-посредник, с которого поступил звонок.</span><span class="sxs-lookup"><span data-stu-id="1b145-137">The Mediation Server the call is coming from.</span></span> <span data-ttu-id="1b145-138">Дополнительные сведения см. <a href="lync-server-2013-mediationservers-table.md">в таблице таблица mediationservers в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="1b145-138">See the <a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b145-139"><strong>томедиатионсерверид</strong></span><span class="sxs-lookup"><span data-stu-id="1b145-139"><strong>ToMediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="1b145-140">int</span><span class="sxs-lookup"><span data-stu-id="1b145-140">int</span></span></p></td>
<td><p><span data-ttu-id="1b145-141">Правительства</span><span class="sxs-lookup"><span data-stu-id="1b145-141">Foreign</span></span></p></td>
<td><p><span data-ttu-id="1b145-142">Сервер-посредник, на который направляется звонок.</span><span class="sxs-lookup"><span data-stu-id="1b145-142">The Mediation Server called is going to.</span></span> <span data-ttu-id="1b145-143">Дополнительные сведения см. <a href="lync-server-2013-mediationservers-table.md">в таблице таблица mediationservers в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="1b145-143">See the <a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b145-144"><strong>фромгатевайид</strong></span><span class="sxs-lookup"><span data-stu-id="1b145-144"><strong>FromGatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="1b145-145">int</span><span class="sxs-lookup"><span data-stu-id="1b145-145">int</span></span></p></td>
<td><p><span data-ttu-id="1b145-146">Правительства</span><span class="sxs-lookup"><span data-stu-id="1b145-146">Foreign</span></span></p></td>
<td><p><span data-ttu-id="1b145-147">Шлюз, из которого поступил звонок.</span><span class="sxs-lookup"><span data-stu-id="1b145-147">Gateway the call is coming from.</span></span> <span data-ttu-id="1b145-148">Более подробную информацию можно узнать <a href="lync-server-2013-gateways-table.md">в таблице шлюзы в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="1b145-148">See the <a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b145-149"><strong>тогатевайид</strong></span><span class="sxs-lookup"><span data-stu-id="1b145-149"><strong>ToGatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="1b145-150">int</span><span class="sxs-lookup"><span data-stu-id="1b145-150">int</span></span></p></td>
<td><p><span data-ttu-id="1b145-151">Правительства</span><span class="sxs-lookup"><span data-stu-id="1b145-151">Foreign</span></span></p></td>
<td><p><span data-ttu-id="1b145-152">Шлюз, на который направляется звонок.</span><span class="sxs-lookup"><span data-stu-id="1b145-152">Gateway the call is going to.</span></span> <span data-ttu-id="1b145-153">Более подробную информацию можно узнать <a href="lync-server-2013-gateways-table.md">в таблице шлюзы в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="1b145-153">See the <a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b145-154"><strong>дисконнектедбюриид</strong></span><span class="sxs-lookup"><span data-stu-id="1b145-154"><strong>DisconnectedbyURIId</strong></span></span></p></td>
<td><p><span data-ttu-id="1b145-155">int</span><span class="sxs-lookup"><span data-stu-id="1b145-155">int</span></span></p></td>
<td><p><span data-ttu-id="1b145-156">Правительства</span><span class="sxs-lookup"><span data-stu-id="1b145-156">Foreign</span></span></p></td>
<td><p><span data-ttu-id="1b145-157">Универсальный код ресурса (URI) пользователя, прервавшего звонок (если имеется).</span><span class="sxs-lookup"><span data-stu-id="1b145-157">URI of the user who disconnected the call, if the user has a URI.</span></span> <span data-ttu-id="1b145-158">Дополнительные сведения см. <a href="lync-server-2013-users-table.md">в таблице "Пользователи" в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="1b145-158">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b145-159"><strong>дисконнектедбифонеид</strong></span><span class="sxs-lookup"><span data-stu-id="1b145-159"><strong>DisconnectedbyPhoneId</strong></span></span></p></td>
<td><p><span data-ttu-id="1b145-160">int</span><span class="sxs-lookup"><span data-stu-id="1b145-160">int</span></span></p></td>
<td><p><span data-ttu-id="1b145-161">Правительства</span><span class="sxs-lookup"><span data-stu-id="1b145-161">Foreign</span></span></p></td>
<td><p><span data-ttu-id="1b145-162">ИД телефона, с которого был прерван звонок.</span><span class="sxs-lookup"><span data-stu-id="1b145-162">ID of the phone that disconnected the call was disconnected from a phone.</span></span> <span data-ttu-id="1b145-163">Дополнительные сведения см. <a href="lync-server-2013-phones-table.md">в таблице phones в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="1b145-163">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

