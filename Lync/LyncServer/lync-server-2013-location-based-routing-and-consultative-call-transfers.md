---
title: 'Lync Server 2013: Маршрутизация на основе местоположения и передача вызовов консултативе'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Location-Based Routing and consultative call transfers
ms:assetid: b12460c2-36c8-481f-b867-fe10dc1c0bdf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362836(v=OCS.15)
ms:contentKeyID: 56335089
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d7c7b73efb670c5569b8c4600c1759e981cda211
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833938"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="location-based-routing-and-consultative-call-transfers-in-lync-server-2013"></a><span data-ttu-id="c6b6b-102">Маршрутизация на основе местоположения и передача звонков консултативе в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c6b6b-102">Location-Based Routing and consultative call transfers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c6b6b-103">_**Тема последнего изменения:** 2013-07-31_</span><span class="sxs-lookup"><span data-stu-id="c6b6b-103">_**Topic Last Modified:** 2013-07-31_</span></span>

<span data-ttu-id="c6b6b-104">В дополнение к принудительному применению маршрутизации на основе местоположения к собраниям Lync, приложение для конференц-связи с учетом местоположения обеспечивает ограничения на маршрутизацию на основе местоположения при передаче звонков консултативе в конечные точки PSTN.</span><span class="sxs-lookup"><span data-stu-id="c6b6b-104">In addition to enforcing Location-Based Routing to Lync meetings, the Location-Based Routing Conferencing application enforces Location-Based Routing restrictions on consultative call transfers that egress to PSTN endpoints.</span></span> <span data-ttu-id="c6b6b-105">Переключение консультативного вызова — это вызов, установленный между двумя абонентами, в котором один из абонентов передает вызов новому абоненту.</span><span class="sxs-lookup"><span data-stu-id="c6b6b-105">A consultative call transfer is a call established between two parties where one of the parties transfers the call to a new user.</span></span> <span data-ttu-id="c6b6b-106">Например, конечная точка PSTN вызывает пользователя A (вызываемый Lync).</span><span class="sxs-lookup"><span data-stu-id="c6b6b-106">For example, a PSTN endpoint calls user A (Lync callee).</span></span> <span data-ttu-id="c6b6b-107">Пользователь а определяет, следует ли перенаправлять пользователя PSTN на пользователя B (пользователь Lync).</span><span class="sxs-lookup"><span data-stu-id="c6b6b-107">User A determines the PSTN user should be forwarded to user B (Lync user).</span></span> <span data-ttu-id="c6b6b-108">Абонент A переводит вызов пользователя ТСОП в режим ожидания и вызывает абонента B. Абонент B подтверждает согласие на разговор с пользователем ТСОП.</span><span class="sxs-lookup"><span data-stu-id="c6b6b-108">User A places the call with the PSTN user on hold, and calls user B. User B agrees to talk to the PSTN user.</span></span> <span data-ttu-id="c6b6b-109">Абонент A переключает вызов, находящийся в режиме ожидания, на абонента B.</span><span class="sxs-lookup"><span data-stu-id="c6b6b-109">User A transfers the call on-hold to user B.</span></span>

<span data-ttu-id="c6b6b-110">**Потоки вызовов при переключении консультативных вызовов**</span><span class="sxs-lookup"><span data-stu-id="c6b6b-110">**Consultative call transfer call flow**</span></span>

<span data-ttu-id="c6b6b-111">![Маршрутизация на основе местоположения для схемы конференций] (images/Dn362836.e4d43d6f-23d2-49c9-b12b-15248a743f92(OCS.15).jpg "Маршрутизация на основе местоположения для схемы конференций")</span><span class="sxs-lookup"><span data-stu-id="c6b6b-111">![Location-based routing for conferencing diagram](images/Dn362836.e4d43d6f-23d2-49c9-b12b-15248a743f92(OCS.15).jpg "Location-based routing for conferencing diagram")</span></span>

<span data-ttu-id="c6b6b-112">Если пользователь, использующий маршрутизацию на основе местоположения, инициирует передачу вызова консултативе для конечной точки PSTN (как показано на предыдущем рисунке), создается два активных звонка: один звонок между пользователем PSTN и пользователем Lync A, а другой пользователь Lync A и Lync User B. в приложении для конференц-связи с учетом расположения применяются следующие правила:</span><span class="sxs-lookup"><span data-stu-id="c6b6b-112">When a user enabled for Location-Based Routing initiates a consultative call transfer of a PSTN endpoint (as shown in the preceding figure), this creates two active calls, one call between the PSTN user and Lync user A, and the other between Lync user A and Lync user B. the following behavior is enforced by the Location-Based Routing Conferencing application:</span></span>

  - <span data-ttu-id="c6b6b-113">Если магистральная маршрутизация SIP, на которую звонит звонок по протоколу PSTN, может перенаправить звонок на сетевой сайт, на котором находится пользователь B (например, объект передачи), будет разрешено его передача. в противном случае передача вызова консултативе будет заблокирована.</span><span class="sxs-lookup"><span data-stu-id="c6b6b-113">If the SIP trunk routing the PSTN call is authorized to re-route the PSTN call to the network site where Lync user B (i.e. transfer target) is located,, then the call transfer will be allowed; otherwise, the consultative call transfer will be blocked.</span></span> <span data-ttu-id="c6b6b-114">Это разрешение предоставляется при условии, что расположение передаваемого абонента находится в пределах той же сети, что и магистраль SIP, по которой активный вызов направляется в конечную точку ТСОП.</span><span class="sxs-lookup"><span data-stu-id="c6b6b-114">This authorization is performed based on the transferred party’s location being in the same network site as the SIP trunk that is routing the active call to the PSTN endpoint.</span></span>

  - <span data-ttu-id="c6b6b-115">Если маршрутизация по магистральной сети SIP не уполномочена для маршрутизации звонков на сетевой сайт, на котором находится переданный абонент (Lync User B) или если он находится на неизвестном сетевом сайте, то передача консултативе на телефон КТСОП Конечная точка (например, цель передачи вызова) будет заблокирована.</span><span class="sxs-lookup"><span data-stu-id="c6b6b-115">If the SIP trunk routing the inbound PSTN call is not authorized to route calls to the network site where the transferred party (Lync user B) is located or the transferred party is located in an unknown network site, then the consultative call transfer to the PSTN endpoint (i.e. call transfer target) will be blocked.</span></span>

<span data-ttu-id="c6b6b-116">В приведенной ниже таблице показано, как ограничения маршрутизации, основанные на расположении, применяются приложением для конференц-связи на основе местоположения для передачи вызовов консултативе.</span><span class="sxs-lookup"><span data-stu-id="c6b6b-116">The following table describes how Location-Based Routing restrictions are applied by the Location-Based Routing Conferencing application for consultative call transfers.</span></span> <span data-ttu-id="c6b6b-117">Хотя конечные точки УАТС не связаны напрямую с сетевым сайтом, магистрали SIP, к которой подключена УАТС, можно назначить сетевой сайт.</span><span class="sxs-lookup"><span data-stu-id="c6b6b-117">Although PBX endpoints are not directly associated with a network site, the SIP trunk the PBX is connected to can be assigned a network site.</span></span> <span data-ttu-id="c6b6b-118">Таким образом, конечную точку УАТС можно косвенно связать с сетевым сайтом.</span><span class="sxs-lookup"><span data-stu-id="c6b6b-118">Therefore, the PBX endpoint can be indirectly associated with a network site.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c6b6b-119">Сетевой сайт стороны, передавшей вызов</span><span class="sxs-lookup"><span data-stu-id="c6b6b-119">Network site of call transferred party</span></span></p></td>
<td><p><span data-ttu-id="c6b6b-120">Сетевой сайт целевого объекта переключения вызова</span><span class="sxs-lookup"><span data-stu-id="c6b6b-120">Network site of call transfer target</span></span></p></td>
<td><p><span data-ttu-id="c6b6b-121">Поведение</span><span class="sxs-lookup"><span data-stu-id="c6b6b-121">Behavior</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6b6b-122">Конечная точка ТСОП</span><span class="sxs-lookup"><span data-stu-id="c6b6b-122">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="c6b6b-123">Пользователь Lync на сайте сети (например, 1)</span><span class="sxs-lookup"><span data-stu-id="c6b6b-123">Lync user in the same network site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="c6b6b-124">Переключение консультативного вызова после консультации будет разрешено</span><span class="sxs-lookup"><span data-stu-id="c6b6b-124">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6b6b-125">Конечная точка ТСОП</span><span class="sxs-lookup"><span data-stu-id="c6b6b-125">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="c6b6b-126">Пользователь Lync на разных сетевых сайтах (то есть на сайте 2)</span><span class="sxs-lookup"><span data-stu-id="c6b6b-126">Lync user in different network sites (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="c6b6b-127">Переключение консультативного вызова после консультации будет заблокировано</span><span class="sxs-lookup"><span data-stu-id="c6b6b-127">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6b6b-128">Конечная точка ТСОП</span><span class="sxs-lookup"><span data-stu-id="c6b6b-128">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="c6b6b-129">Пользователь Lync на неизвестном сетевом сайте</span><span class="sxs-lookup"><span data-stu-id="c6b6b-129">Lync user in an unknown network site</span></span></p></td>
<td><p><span data-ttu-id="c6b6b-130">Переключение консультативного вызова после консультации будет заблокировано</span><span class="sxs-lookup"><span data-stu-id="c6b6b-130">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6b6b-131">Конечная точка ТСОП</span><span class="sxs-lookup"><span data-stu-id="c6b6b-131">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="c6b6b-132">Федеративный пользователь Lync</span><span class="sxs-lookup"><span data-stu-id="c6b6b-132">Federated Lync user</span></span></p></td>
<td><p><span data-ttu-id="c6b6b-133">Переключение консультативного вызова после консультации будет заблокировано</span><span class="sxs-lookup"><span data-stu-id="c6b6b-133">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6b6b-134">Конечная точка ТСОП</span><span class="sxs-lookup"><span data-stu-id="c6b6b-134">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="c6b6b-135">Конечная точка УАТС на том же сайте (т. е. на сайте 1)</span><span class="sxs-lookup"><span data-stu-id="c6b6b-135">PBX endpoint in the same site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="c6b6b-136">Переключение консультативного вызова после консультации будет разрешено</span><span class="sxs-lookup"><span data-stu-id="c6b6b-136">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6b6b-137">Конечная точка ТСОП</span><span class="sxs-lookup"><span data-stu-id="c6b6b-137">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="c6b6b-138">Конечная точка УАТС на других сайтах (т. е. на сайте 2)</span><span class="sxs-lookup"><span data-stu-id="c6b6b-138">PBX endpoint in a different sites (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="c6b6b-139">Переключение консультативного вызова после консультации будет заблокировано</span><span class="sxs-lookup"><span data-stu-id="c6b6b-139">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6b6b-140">Конечная точка УАТС на том же сайте (т. е. на сайте 1)</span><span class="sxs-lookup"><span data-stu-id="c6b6b-140">PBX endpoint in the same site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="c6b6b-141">Конечная точка ТСОП</span><span class="sxs-lookup"><span data-stu-id="c6b6b-141">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="c6b6b-142">Переключение консультативного вызова после консультации будет разрешено</span><span class="sxs-lookup"><span data-stu-id="c6b6b-142">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6b6b-143">Конечная точка УАТС на другом сайте (т. е. на сайте 2)</span><span class="sxs-lookup"><span data-stu-id="c6b6b-143">PBX endpoint in a different site (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="c6b6b-144">Конечная точка ТСОП</span><span class="sxs-lookup"><span data-stu-id="c6b6b-144">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="c6b6b-145">Переключение консультативного вызова после консультации будет заблокировано</span><span class="sxs-lookup"><span data-stu-id="c6b6b-145">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6b6b-146">Конечная точка УАТС на любом сайте</span><span class="sxs-lookup"><span data-stu-id="c6b6b-146">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="c6b6b-147">Пользователь Lync на сайте сети (например, 1)</span><span class="sxs-lookup"><span data-stu-id="c6b6b-147">Lync user in the same network site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="c6b6b-148">Переключение консультативного вызова после консультации будет разрешено</span><span class="sxs-lookup"><span data-stu-id="c6b6b-148">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6b6b-149">Конечная точка УАТС на любом сайте</span><span class="sxs-lookup"><span data-stu-id="c6b6b-149">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="c6b6b-150">Пользователь Lync на разных сетевых сайтах (то есть на сайте 2)</span><span class="sxs-lookup"><span data-stu-id="c6b6b-150">Lync user in different network sites (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="c6b6b-151">Переключение консультативного вызова после консультации будет разрешено</span><span class="sxs-lookup"><span data-stu-id="c6b6b-151">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6b6b-152">Конечная точка УАТС на любом сайте</span><span class="sxs-lookup"><span data-stu-id="c6b6b-152">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="c6b6b-153">Пользователь Lync на неизвестном сетевом сайте</span><span class="sxs-lookup"><span data-stu-id="c6b6b-153">Lync user in an unknown network site</span></span></p></td>
<td><p><span data-ttu-id="c6b6b-154">Переключение консультативного вызова после консультации будет разрешено</span><span class="sxs-lookup"><span data-stu-id="c6b6b-154">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6b6b-155">Конечная точка УАТС на любом сайте</span><span class="sxs-lookup"><span data-stu-id="c6b6b-155">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="c6b6b-156">Федеративный пользователь Lync</span><span class="sxs-lookup"><span data-stu-id="c6b6b-156">Federated Lync user</span></span></p></td>
<td><p><span data-ttu-id="c6b6b-157">Переключение консультативного вызова после консультации будет разрешено</span><span class="sxs-lookup"><span data-stu-id="c6b6b-157">Consultative transfer will be allowed</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

