---
title: 'Lync Server 2013: Location-Based маршрутизации и передачи вызовов Консультативного'
description: 'Lync Server 2013: Location-Based маршрутизации и передачи вызовов Консультативного.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Location-Based Routing and consultative call transfers
ms:assetid: b12460c2-36c8-481f-b867-fe10dc1c0bdf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362836(v=OCS.15)
ms:contentKeyID: 56335089
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0d07cf6a33ff4d6ad57f8913a798fac3bc393a00
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567675"
---
# <a name="location-based-routing-and-consultative-call-transfers-in-lync-server-2013"></a><span data-ttu-id="10b18-103">Location-Based маршрутизации и передачи вызовов Консультативного в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="10b18-103">Location-Based Routing and consultative call transfers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="10b18-104">_**Последнее изменение темы:** 2013-07-31_</span><span class="sxs-lookup"><span data-stu-id="10b18-104">_**Topic Last Modified:** 2013-07-31_</span></span>

<span data-ttu-id="10b18-105">Кроме принудительного применения маршрутизации Location-Based к собраниям Lync, приложение для конференц-связи с Location-Based маршрутизации применяет Location-Based ограничения маршрутизации для передачи вызовов консультативного, которые исполняют конечные точки PSTN.</span><span class="sxs-lookup"><span data-stu-id="10b18-105">In addition to enforcing Location-Based Routing to Lync meetings, the Location-Based Routing Conferencing application enforces Location-Based Routing restrictions on consultative call transfers that egress to PSTN endpoints.</span></span> <span data-ttu-id="10b18-106">Передача вызова Консультативного — это вызов, установленный между двумя сторонами, в которых один из сторон передает вызов новому пользователю.</span><span class="sxs-lookup"><span data-stu-id="10b18-106">A consultative call transfer is a call established between two parties where one of the parties transfers the call to a new user.</span></span> <span data-ttu-id="10b18-107">Например, конечная точка PSTN вызывает пользователя A (вызываемый вызываемый Lync).</span><span class="sxs-lookup"><span data-stu-id="10b18-107">For example, a PSTN endpoint calls user A (Lync callee).</span></span> <span data-ttu-id="10b18-108">Пользователь а определяет, что пользователь PSTN должен быть переадресован пользователю б (пользователь Lync).</span><span class="sxs-lookup"><span data-stu-id="10b18-108">User A determines the PSTN user should be forwarded to user B (Lync user).</span></span> <span data-ttu-id="10b18-109">Пользователь а помещает звонок с помощью пользователя PSTN на удержании и звонит пользователя б. пользователь б соглашается поговорить с пользователем PSTN.</span><span class="sxs-lookup"><span data-stu-id="10b18-109">User A places the call with the PSTN user on hold, and calls user B. User B agrees to talk to the PSTN user.</span></span> <span data-ttu-id="10b18-110">Пользователь а передает вызов на удержание пользователю б.</span><span class="sxs-lookup"><span data-stu-id="10b18-110">User A transfers the call on-hold to user B.</span></span>

<span data-ttu-id="10b18-111">**Процесс передачи вызовов Консультативного**</span><span class="sxs-lookup"><span data-stu-id="10b18-111">**Consultative call transfer call flow**</span></span>

<span data-ttu-id="10b18-112">![Схема маршрутизации для конференц-связи с учетом расположения](images/Dn362836.e4d43d6f-23d2-49c9-b12b-15248a743f92(OCS.15).jpg "Схема маршрутизации для конференц-связи с учетом расположения")</span><span class="sxs-lookup"><span data-stu-id="10b18-112">![Location-based routing for conferencing diagram](images/Dn362836.e4d43d6f-23d2-49c9-b12b-15248a743f92(OCS.15).jpg "Location-based routing for conferencing diagram")</span></span>

<span data-ttu-id="10b18-113">Когда пользователь, использующий Location-Basedную маршрутизацию, инициирует передачу вызова Консультативного для конечной точки PSTN (как показано на предыдущем рисунке), создается два активных звонка, один вызов между пользователем PSTN и пользователем Lync а, а другой между пользователями Lync A и Lync User B. следующее поведение применяется приложением для конференц-связи Location-Based.</span><span class="sxs-lookup"><span data-stu-id="10b18-113">When a user enabled for Location-Based Routing initiates a consultative call transfer of a PSTN endpoint (as shown in the preceding figure), this creates two active calls, one call between the PSTN user and Lync user A, and the other between Lync user A and Lync user B. the following behavior is enforced by the Location-Based Routing Conferencing application:</span></span>

  - <span data-ttu-id="10b18-114">Если маршрутизация по магистрали SIP получит право перенаправить звонок PSTN на сетевой сайт, где расположен пользователь Lync B (например, цель передачи), то передача вызова будет разрешена; в противном случае передача вызовов Консультативного будет заблокирована.</span><span class="sxs-lookup"><span data-stu-id="10b18-114">If the SIP trunk routing the PSTN call is authorized to re-route the PSTN call to the network site where Lync user B (i.e. transfer target) is located,, then the call transfer will be allowed; otherwise, the consultative call transfer will be blocked.</span></span> <span data-ttu-id="10b18-115">Эта авторизация выполняется в зависимости от расположения передаваемых субъектов, находимого на том же сетевом сайте, что и магистраль SIP, который выполняет маршрутизацию активного вызова в конечную точку PSTN.</span><span class="sxs-lookup"><span data-stu-id="10b18-115">This authorization is performed based on the transferred party’s location being in the same network site as the SIP trunk that is routing the active call to the PSTN endpoint.</span></span>

  - <span data-ttu-id="10b18-116">Если маршрутизация магистральной линии SIP не авторизована для маршрутизации вызовов на сетевой сайт, на котором размещена переданная сторона (Lync User B) или если перемещенная сторона находится на неизвестном сетевом сайте, то передача вызова Консультативного в конечную точку PSTN (то есть цель передачи вызовов) будет заблокирована.</span><span class="sxs-lookup"><span data-stu-id="10b18-116">If the SIP trunk routing the inbound PSTN call is not authorized to route calls to the network site where the transferred party (Lync user B) is located or the transferred party is located in an unknown network site, then the consultative call transfer to the PSTN endpoint (i.e. call transfer target) will be blocked.</span></span>

<span data-ttu-id="10b18-117">В следующей таблице показано, как Location-Based ограничения маршрутизации в приложении Location-Based маршрутизации для передачи вызовов Консультативного.</span><span class="sxs-lookup"><span data-stu-id="10b18-117">The following table describes how Location-Based Routing restrictions are applied by the Location-Based Routing Conferencing application for consultative call transfers.</span></span> <span data-ttu-id="10b18-118">Несмотря на то, что конечные точки УАТС напрямую не связаны с сетевым сайтом, магистральная линия SIP, к которой подключена УАТС, может быть назначена сетевому сайту.</span><span class="sxs-lookup"><span data-stu-id="10b18-118">Although PBX endpoints are not directly associated with a network site, the SIP trunk the PBX is connected to can be assigned a network site.</span></span> <span data-ttu-id="10b18-119">Таким образом, конечная точка УАТС может быть косвенно связана с сетевым сайтом.</span><span class="sxs-lookup"><span data-stu-id="10b18-119">Therefore, the PBX endpoint can be indirectly associated with a network site.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="10b18-120">Сетевой сайт абонентской стороны с передаваемым звонком</span><span class="sxs-lookup"><span data-stu-id="10b18-120">Network site of call transferred party</span></span></p></td>
<td><p><span data-ttu-id="10b18-121">Сетевой сайт цели передачи вызовов</span><span class="sxs-lookup"><span data-stu-id="10b18-121">Network site of call transfer target</span></span></p></td>
<td><p><span data-ttu-id="10b18-122">Поведение</span><span class="sxs-lookup"><span data-stu-id="10b18-122">Behavior</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10b18-123">Конечная точка PSTN</span><span class="sxs-lookup"><span data-stu-id="10b18-123">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="10b18-124">Пользователь Lync на том же сетевом сайте (то есть на сайте 1)</span><span class="sxs-lookup"><span data-stu-id="10b18-124">Lync user in the same network site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="10b18-125">Передача Консультативного будет разрешена</span><span class="sxs-lookup"><span data-stu-id="10b18-125">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10b18-126">Конечная точка PSTN</span><span class="sxs-lookup"><span data-stu-id="10b18-126">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="10b18-127">Пользователь Lync на различных сетевых сайтах (то есть на сайте 2)</span><span class="sxs-lookup"><span data-stu-id="10b18-127">Lync user in different network sites (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="10b18-128">Передача Консультативного будет запрещена</span><span class="sxs-lookup"><span data-stu-id="10b18-128">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10b18-129">Конечная точка PSTN</span><span class="sxs-lookup"><span data-stu-id="10b18-129">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="10b18-130">Пользователь Lync на неизвестном сетевом сайте</span><span class="sxs-lookup"><span data-stu-id="10b18-130">Lync user in an unknown network site</span></span></p></td>
<td><p><span data-ttu-id="10b18-131">Передача Консультативного будет запрещена</span><span class="sxs-lookup"><span data-stu-id="10b18-131">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10b18-132">Конечная точка PSTN</span><span class="sxs-lookup"><span data-stu-id="10b18-132">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="10b18-133">Федеративный пользователь Lync</span><span class="sxs-lookup"><span data-stu-id="10b18-133">Federated Lync user</span></span></p></td>
<td><p><span data-ttu-id="10b18-134">Передача Консультативного будет запрещена</span><span class="sxs-lookup"><span data-stu-id="10b18-134">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10b18-135">Конечная точка PSTN</span><span class="sxs-lookup"><span data-stu-id="10b18-135">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="10b18-136">Конечная точка УАТС на одном сайте (то есть на сайте 1)</span><span class="sxs-lookup"><span data-stu-id="10b18-136">PBX endpoint in the same site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="10b18-137">Передача Консультативного будет разрешена</span><span class="sxs-lookup"><span data-stu-id="10b18-137">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10b18-138">Конечная точка PSTN</span><span class="sxs-lookup"><span data-stu-id="10b18-138">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="10b18-139">Конечная точка УАТС на разных сайтах (то есть на сайте 2)</span><span class="sxs-lookup"><span data-stu-id="10b18-139">PBX endpoint in a different sites (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="10b18-140">Передача Консультативного будет запрещена</span><span class="sxs-lookup"><span data-stu-id="10b18-140">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10b18-141">Конечная точка УАТС на одном сайте (то есть на сайте 1)</span><span class="sxs-lookup"><span data-stu-id="10b18-141">PBX endpoint in the same site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="10b18-142">Конечная точка PSTN</span><span class="sxs-lookup"><span data-stu-id="10b18-142">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="10b18-143">Передача Консультативного будет разрешена</span><span class="sxs-lookup"><span data-stu-id="10b18-143">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10b18-144">Конечная точка УАТС на другом сайте (то есть на сайте 2)</span><span class="sxs-lookup"><span data-stu-id="10b18-144">PBX endpoint in a different site (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="10b18-145">Конечная точка PSTN</span><span class="sxs-lookup"><span data-stu-id="10b18-145">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="10b18-146">Передача Консультативного будет запрещена</span><span class="sxs-lookup"><span data-stu-id="10b18-146">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10b18-147">Конечная точка УАТС на любом сайте</span><span class="sxs-lookup"><span data-stu-id="10b18-147">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="10b18-148">Пользователь Lync на том же сетевом сайте (то есть на сайте 1)</span><span class="sxs-lookup"><span data-stu-id="10b18-148">Lync user in the same network site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="10b18-149">Передача Консультативного будет разрешена</span><span class="sxs-lookup"><span data-stu-id="10b18-149">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10b18-150">Конечная точка УАТС на любом сайте</span><span class="sxs-lookup"><span data-stu-id="10b18-150">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="10b18-151">Пользователь Lync на различных сетевых сайтах (то есть на сайте 2)</span><span class="sxs-lookup"><span data-stu-id="10b18-151">Lync user in different network sites (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="10b18-152">Передача Консультативного будет разрешена</span><span class="sxs-lookup"><span data-stu-id="10b18-152">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10b18-153">Конечная точка УАТС на любом сайте</span><span class="sxs-lookup"><span data-stu-id="10b18-153">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="10b18-154">Пользователь Lync на неизвестном сетевом сайте</span><span class="sxs-lookup"><span data-stu-id="10b18-154">Lync user in an unknown network site</span></span></p></td>
<td><p><span data-ttu-id="10b18-155">Передача Консультативного будет разрешена</span><span class="sxs-lookup"><span data-stu-id="10b18-155">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10b18-156">Конечная точка УАТС на любом сайте</span><span class="sxs-lookup"><span data-stu-id="10b18-156">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="10b18-157">Федеративный пользователь Lync</span><span class="sxs-lookup"><span data-stu-id="10b18-157">Federated Lync user</span></span></p></td>
<td><p><span data-ttu-id="10b18-158">Передача Консультативного будет разрешена</span><span class="sxs-lookup"><span data-stu-id="10b18-158">Consultative transfer will be allowed</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

