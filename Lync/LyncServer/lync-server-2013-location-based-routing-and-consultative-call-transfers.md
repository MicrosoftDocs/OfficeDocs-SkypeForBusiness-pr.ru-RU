---
title: 'Lync Server 2013: Location-Based маршрутизации и передачи вызовов Консультативного'
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
ms.openlocfilehash: 75284736af1307aff4e9c51c8118cf64dbd08568
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513816"
---
# <a name="location-based-routing-and-consultative-call-transfers-in-lync-server-2013"></a><span data-ttu-id="61679-102">Location-Based маршрутизации и передачи вызовов Консультативного в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61679-102">Location-Based Routing and consultative call transfers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="61679-103">_**Последнее изменение темы:** 2013-07-31_</span><span class="sxs-lookup"><span data-stu-id="61679-103">_**Topic Last Modified:** 2013-07-31_</span></span>

<span data-ttu-id="61679-104">Кроме принудительного применения маршрутизации Location-Based к собраниям Lync, приложение для конференц-связи с Location-Based маршрутизации применяет Location-Based ограничения маршрутизации для передачи вызовов консультативного, которые исполняют конечные точки PSTN.</span><span class="sxs-lookup"><span data-stu-id="61679-104">In addition to enforcing Location-Based Routing to Lync meetings, the Location-Based Routing Conferencing application enforces Location-Based Routing restrictions on consultative call transfers that egress to PSTN endpoints.</span></span> <span data-ttu-id="61679-105">Передача вызова Консультативного — это вызов, установленный между двумя сторонами, в которых один из сторон передает вызов новому пользователю.</span><span class="sxs-lookup"><span data-stu-id="61679-105">A consultative call transfer is a call established between two parties where one of the parties transfers the call to a new user.</span></span> <span data-ttu-id="61679-106">Например, конечная точка PSTN вызывает пользователя A (вызываемый вызываемый Lync).</span><span class="sxs-lookup"><span data-stu-id="61679-106">For example, a PSTN endpoint calls user A (Lync callee).</span></span> <span data-ttu-id="61679-107">Пользователь а определяет, что пользователь PSTN должен быть переадресован пользователю б (пользователь Lync).</span><span class="sxs-lookup"><span data-stu-id="61679-107">User A determines the PSTN user should be forwarded to user B (Lync user).</span></span> <span data-ttu-id="61679-108">Пользователь а помещает звонок с помощью пользователя PSTN на удержании и звонит пользователя б. пользователь б соглашается поговорить с пользователем PSTN.</span><span class="sxs-lookup"><span data-stu-id="61679-108">User A places the call with the PSTN user on hold, and calls user B. User B agrees to talk to the PSTN user.</span></span> <span data-ttu-id="61679-109">Пользователь а передает вызов на удержание пользователю б.</span><span class="sxs-lookup"><span data-stu-id="61679-109">User A transfers the call on-hold to user B.</span></span>

<span data-ttu-id="61679-110">**Процесс передачи вызовов Консультативного**</span><span class="sxs-lookup"><span data-stu-id="61679-110">**Consultative call transfer call flow**</span></span>

<span data-ttu-id="61679-111">![Схема маршрутизации для конференц-связи с учетом расположения](images/Dn362836.e4d43d6f-23d2-49c9-b12b-15248a743f92(OCS.15).jpg "Схема маршрутизации для конференц-связи с учетом расположения")</span><span class="sxs-lookup"><span data-stu-id="61679-111">![Location-based routing for conferencing diagram](images/Dn362836.e4d43d6f-23d2-49c9-b12b-15248a743f92(OCS.15).jpg "Location-based routing for conferencing diagram")</span></span>

<span data-ttu-id="61679-112">Когда пользователь, использующий Location-Basedную маршрутизацию, инициирует передачу вызова Консультативного для конечной точки PSTN (как показано на предыдущем рисунке), создается два активных звонка, один вызов между пользователем PSTN и пользователем Lync а, а другой между пользователями Lync A и Lync User B. следующее поведение применяется приложением для конференц-связи Location-Based.</span><span class="sxs-lookup"><span data-stu-id="61679-112">When a user enabled for Location-Based Routing initiates a consultative call transfer of a PSTN endpoint (as shown in the preceding figure), this creates two active calls, one call between the PSTN user and Lync user A, and the other between Lync user A and Lync user B. the following behavior is enforced by the Location-Based Routing Conferencing application:</span></span>

  - <span data-ttu-id="61679-113">Если маршрутизация по магистрали SIP получит право перенаправить звонок PSTN на сетевой сайт, где расположен пользователь Lync B (например, цель передачи), то передача вызова будет разрешена; в противном случае передача вызовов Консультативного будет заблокирована.</span><span class="sxs-lookup"><span data-stu-id="61679-113">If the SIP trunk routing the PSTN call is authorized to re-route the PSTN call to the network site where Lync user B (i.e. transfer target) is located,, then the call transfer will be allowed; otherwise, the consultative call transfer will be blocked.</span></span> <span data-ttu-id="61679-114">Эта авторизация выполняется в зависимости от расположения передаваемых субъектов, находимого на том же сетевом сайте, что и магистраль SIP, который выполняет маршрутизацию активного вызова в конечную точку PSTN.</span><span class="sxs-lookup"><span data-stu-id="61679-114">This authorization is performed based on the transferred party’s location being in the same network site as the SIP trunk that is routing the active call to the PSTN endpoint.</span></span>

  - <span data-ttu-id="61679-115">Если маршрутизация магистральной линии SIP не авторизована для маршрутизации вызовов на сетевой сайт, на котором размещена переданная сторона (Lync User B) или если перемещенная сторона находится на неизвестном сетевом сайте, то передача вызова Консультативного в конечную точку PSTN (то есть цель передачи вызовов) будет заблокирована.</span><span class="sxs-lookup"><span data-stu-id="61679-115">If the SIP trunk routing the inbound PSTN call is not authorized to route calls to the network site where the transferred party (Lync user B) is located or the transferred party is located in an unknown network site, then the consultative call transfer to the PSTN endpoint (i.e. call transfer target) will be blocked.</span></span>

<span data-ttu-id="61679-116">В следующей таблице показано, как Location-Based ограничения маршрутизации в приложении Location-Based маршрутизации для передачи вызовов Консультативного.</span><span class="sxs-lookup"><span data-stu-id="61679-116">The following table describes how Location-Based Routing restrictions are applied by the Location-Based Routing Conferencing application for consultative call transfers.</span></span> <span data-ttu-id="61679-117">Несмотря на то, что конечные точки УАТС напрямую не связаны с сетевым сайтом, магистральная линия SIP, к которой подключена УАТС, может быть назначена сетевому сайту.</span><span class="sxs-lookup"><span data-stu-id="61679-117">Although PBX endpoints are not directly associated with a network site, the SIP trunk the PBX is connected to can be assigned a network site.</span></span> <span data-ttu-id="61679-118">Таким образом, конечная точка УАТС может быть косвенно связана с сетевым сайтом.</span><span class="sxs-lookup"><span data-stu-id="61679-118">Therefore, the PBX endpoint can be indirectly associated with a network site.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="61679-119">Сетевой сайт абонентской стороны с передаваемым звонком</span><span class="sxs-lookup"><span data-stu-id="61679-119">Network site of call transferred party</span></span></p></td>
<td><p><span data-ttu-id="61679-120">Сетевой сайт цели передачи вызовов</span><span class="sxs-lookup"><span data-stu-id="61679-120">Network site of call transfer target</span></span></p></td>
<td><p><span data-ttu-id="61679-121">Поведение</span><span class="sxs-lookup"><span data-stu-id="61679-121">Behavior</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61679-122">Конечная точка PSTN</span><span class="sxs-lookup"><span data-stu-id="61679-122">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="61679-123">Пользователь Lync на том же сетевом сайте (то есть на сайте 1)</span><span class="sxs-lookup"><span data-stu-id="61679-123">Lync user in the same network site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="61679-124">Передача Консультативного будет разрешена</span><span class="sxs-lookup"><span data-stu-id="61679-124">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61679-125">Конечная точка PSTN</span><span class="sxs-lookup"><span data-stu-id="61679-125">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="61679-126">Пользователь Lync на различных сетевых сайтах (то есть на сайте 2)</span><span class="sxs-lookup"><span data-stu-id="61679-126">Lync user in different network sites (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="61679-127">Передача Консультативного будет запрещена</span><span class="sxs-lookup"><span data-stu-id="61679-127">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61679-128">Конечная точка PSTN</span><span class="sxs-lookup"><span data-stu-id="61679-128">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="61679-129">Пользователь Lync на неизвестном сетевом сайте</span><span class="sxs-lookup"><span data-stu-id="61679-129">Lync user in an unknown network site</span></span></p></td>
<td><p><span data-ttu-id="61679-130">Передача Консультативного будет запрещена</span><span class="sxs-lookup"><span data-stu-id="61679-130">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61679-131">Конечная точка PSTN</span><span class="sxs-lookup"><span data-stu-id="61679-131">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="61679-132">Федеративный пользователь Lync</span><span class="sxs-lookup"><span data-stu-id="61679-132">Federated Lync user</span></span></p></td>
<td><p><span data-ttu-id="61679-133">Передача Консультативного будет запрещена</span><span class="sxs-lookup"><span data-stu-id="61679-133">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61679-134">Конечная точка PSTN</span><span class="sxs-lookup"><span data-stu-id="61679-134">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="61679-135">Конечная точка УАТС на одном сайте (то есть на сайте 1)</span><span class="sxs-lookup"><span data-stu-id="61679-135">PBX endpoint in the same site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="61679-136">Передача Консультативного будет разрешена</span><span class="sxs-lookup"><span data-stu-id="61679-136">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61679-137">Конечная точка PSTN</span><span class="sxs-lookup"><span data-stu-id="61679-137">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="61679-138">Конечная точка УАТС на разных сайтах (то есть на сайте 2)</span><span class="sxs-lookup"><span data-stu-id="61679-138">PBX endpoint in a different sites (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="61679-139">Передача Консультативного будет запрещена</span><span class="sxs-lookup"><span data-stu-id="61679-139">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61679-140">Конечная точка УАТС на одном сайте (то есть на сайте 1)</span><span class="sxs-lookup"><span data-stu-id="61679-140">PBX endpoint in the same site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="61679-141">Конечная точка PSTN</span><span class="sxs-lookup"><span data-stu-id="61679-141">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="61679-142">Передача Консультативного будет разрешена</span><span class="sxs-lookup"><span data-stu-id="61679-142">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61679-143">Конечная точка УАТС на другом сайте (то есть на сайте 2)</span><span class="sxs-lookup"><span data-stu-id="61679-143">PBX endpoint in a different site (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="61679-144">Конечная точка PSTN</span><span class="sxs-lookup"><span data-stu-id="61679-144">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="61679-145">Передача Консультативного будет запрещена</span><span class="sxs-lookup"><span data-stu-id="61679-145">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61679-146">Конечная точка УАТС на любом сайте</span><span class="sxs-lookup"><span data-stu-id="61679-146">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="61679-147">Пользователь Lync на том же сетевом сайте (то есть на сайте 1)</span><span class="sxs-lookup"><span data-stu-id="61679-147">Lync user in the same network site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="61679-148">Передача Консультативного будет разрешена</span><span class="sxs-lookup"><span data-stu-id="61679-148">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61679-149">Конечная точка УАТС на любом сайте</span><span class="sxs-lookup"><span data-stu-id="61679-149">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="61679-150">Пользователь Lync на различных сетевых сайтах (то есть на сайте 2)</span><span class="sxs-lookup"><span data-stu-id="61679-150">Lync user in different network sites (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="61679-151">Передача Консультативного будет разрешена</span><span class="sxs-lookup"><span data-stu-id="61679-151">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61679-152">Конечная точка УАТС на любом сайте</span><span class="sxs-lookup"><span data-stu-id="61679-152">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="61679-153">Пользователь Lync на неизвестном сетевом сайте</span><span class="sxs-lookup"><span data-stu-id="61679-153">Lync user in an unknown network site</span></span></p></td>
<td><p><span data-ttu-id="61679-154">Передача Консультативного будет разрешена</span><span class="sxs-lookup"><span data-stu-id="61679-154">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61679-155">Конечная точка УАТС на любом сайте</span><span class="sxs-lookup"><span data-stu-id="61679-155">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="61679-156">Федеративный пользователь Lync</span><span class="sxs-lookup"><span data-stu-id="61679-156">Federated Lync user</span></span></p></td>
<td><p><span data-ttu-id="61679-157">Передача Консультативного будет разрешена</span><span class="sxs-lookup"><span data-stu-id="61679-157">Consultative transfer will be allowed</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

