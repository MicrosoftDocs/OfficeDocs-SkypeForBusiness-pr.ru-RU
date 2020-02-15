---
title: 'Lync Server 2013: Обзор маршрутизации на основе расположения для конференций'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Location-Based Routing for conferencing
ms:assetid: 8b86740e-db95-4304-bb83-64d0cbb91d47
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362815(v=OCS.15)
ms:contentKeyID: 56335084
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 28ca4ea233f783271c91490aa0550bc2344bdaad
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051031"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-location-based-routing-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="08840-102">Обзор маршрутизации на основе расположения для конференций в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="08840-102">Overview of Location-Based Routing for conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="08840-103">_**Последнее изменение темы:** 2013-07-19_</span><span class="sxs-lookup"><span data-stu-id="08840-103">_**Topic Last Modified:** 2013-07-19_</span></span>

<span data-ttu-id="08840-104">Приложение для конференц-связи с маршрутизацией на основе расположения предоставляет механизм для защиты от использования бесплатных звонков в Lync.</span><span class="sxs-lookup"><span data-stu-id="08840-104">The Location-Based Routing Conferencing application provides to Lync Conferences a mechanism for the prevention of PSTN toll bypass.</span></span> <span data-ttu-id="08840-105">Приложение отслеживает активные Конференции и применяет ограничения на маршрутизацию на основе расположения на основе расположения участвующих пользователей Lync.</span><span class="sxs-lookup"><span data-stu-id="08840-105">The application monitors active conferences and enforces Location-Based Routing restrictions based on the location of the Lync users participating.</span></span>

<span data-ttu-id="08840-106">Приложение для конференц-связи с маршрутизацией на основе расположения определяет, следует ли применять маршрутизацию на основе расположения на собрании Lync при соблюдении следующих условий:</span><span class="sxs-lookup"><span data-stu-id="08840-106">The Location-Based Routing Conferencing application determines whether Location-Based Routing is to be enforced on a Lync meeting if the following criteria are met:</span></span>

  - <span data-ttu-id="08840-107">Организатор собрания включается для маршрутизации на основе расположения.</span><span class="sxs-lookup"><span data-stu-id="08840-107">The meeting organizer is enabled for Location-Based Routing.</span></span> <span data-ttu-id="08840-108">Ограничения маршрутизации на основе расположения будут применяться только к конференциям, организованным пользователями, для которых включена маршрутизация на основе расположения.</span><span class="sxs-lookup"><span data-stu-id="08840-108">Location-Based Routing restrictions will be applied only to conferences that are organized by users who are enabled for Location-Based Routing.</span></span>

  - <span data-ttu-id="08840-109">По крайней мере один участник собрания является конечной точкой PSTN.</span><span class="sxs-lookup"><span data-stu-id="08840-109">At least one meeting participant is a PSTN endpoint.</span></span> <span data-ttu-id="08840-110">Ограничения маршрутизации на основе расположения применяются только к конференциям, включающим конечные точки PSTN.</span><span class="sxs-lookup"><span data-stu-id="08840-110">Location-Based Routing restrictions are applicable only for conferences that include PSTN endpoints.</span></span>

  - <span data-ttu-id="08840-111">Сетевой сайт, на котором размещается шлюз PSTN, используемый для моста конференции в PSTN, а также сетевые сайты, с которых подключаются организаторов и участники.</span><span class="sxs-lookup"><span data-stu-id="08840-111">The network site where the PSTN gateway used to bridge the conference to the PSTN is located as well as the network sites where the organizers and participants are connecting from.</span></span>

<span data-ttu-id="08840-112">Приложение для конференц-связи с маршрутизацией на основе расположения предотвращает участие пользователей Lync и конечных точек PSTN от разных сетевых сайтов до одной конференции.</span><span class="sxs-lookup"><span data-stu-id="08840-112">The Location-Based Routing Conferencing application prevents the participation of Lync users and PSTN endpoints from different network sites to the same conference.</span></span> <span data-ttu-id="08840-113">Если организатор собрания включен для маршрутизации на основе расположения, приложение для конференц-связи применяет следующие ограничения:</span><span class="sxs-lookup"><span data-stu-id="08840-113">If the organizer of a meeting is enabled for Location-Based Routing, the Conferencing application enforces the following restrictions:</span></span>

  - <span data-ttu-id="08840-114">Конечные точки, которые могут присоединиться к собранию Lync, зависят от конечных точек, которые уже присоединились к Конференции, и это ограничение изменяется как присоединяемые конечные точки, которые присоединяются к Конференции.</span><span class="sxs-lookup"><span data-stu-id="08840-114">The endpoints that can join a Lync meeting depend on the endpoints that already joined the conference, and this restriction adjusts as joined endpoints leave and new endpoints join the conference.</span></span> <span data-ttu-id="08840-115">Если организаторов и участники присоединяются к собранию Lync с того же сетевого сайта, то конечная точка PSTN, другой участник с того же сетевого сайта, другой участник из другого сетевого сайта или участник с неизвестного сетевого сайта, могут соединит.</span><span class="sxs-lookup"><span data-stu-id="08840-115">If organizers and participants are joining a Lync meeting from the same network site, then a PSTN endpoint, another participant from the same network site, another participant from a different network site or a participant from an unknown network site are allowed to join.</span></span>

  - <span data-ttu-id="08840-116">Если организаторов и участники присоединяются к собранию из разных или неизвестных сетевых сайтов, то конечная точка PSTN не может присоединиться к собранию, если для маршрутизации на основе расположения включена функция PSTN Call ингрессес из магистральной линии SIP.</span><span class="sxs-lookup"><span data-stu-id="08840-116">If organizers and participants are joining the meeting from different or unknown network sites, a PSTN endpoint is not allowed to join the meeting if the PSTN call ingresses from a SIP trunk enabled for Location-Based Routing.</span></span>

  - <span data-ttu-id="08840-117">Если организаторов и участники присоединяются к собранию из одного и того же сетевого сайта, а участники, присоединяющиеся к тому же собранию из сети PSTN, не могут присоединяться к собранию с помощью конечной точки Lync с другого сетевого сайта.</span><span class="sxs-lookup"><span data-stu-id="08840-117">If organizers and participants are all joining the meeting from the same network site and there are participants joining the same meeting from the PSTN, a Lync endpoint from a different network site is not allowed to join the meeting.</span></span>

<span data-ttu-id="08840-118">В следующей таблице приведена сводка по ограничениям маршрутизации на основе расположения для конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="08840-118">These conferencing Location-Based Routing restrictions are summarized in the following table.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="08840-119">Пользователи в конференции на любой заданный момент</span><span class="sxs-lookup"><span data-stu-id="08840-119">User(s) in a conference at any given point</span></span></p></td>
<td><p><span data-ttu-id="08840-120">Пользователи, которым разрешено присоединяться к Конференции</span><span class="sxs-lookup"><span data-stu-id="08840-120">User(s) allowed to join the conference</span></span></p></td>
<td><p><span data-ttu-id="08840-121">Пользователям не разрешено присоединяться к Конференции</span><span class="sxs-lookup"><span data-stu-id="08840-121">User(s) not allowed to join the conference</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08840-122">Пользователи клиента VoIP для Lync с одного сетевого сайта</span><span class="sxs-lookup"><span data-stu-id="08840-122">Lync VoIP client user(s) from a single network site</span></span></p></td>
<td><p><span data-ttu-id="08840-123">Пользователь клиента VoIP для Lync с того же сетевого сайта</span><span class="sxs-lookup"><span data-stu-id="08840-123">Lync VoIP client user from the same network site</span></span></p>
<p><span data-ttu-id="08840-124">Пользователь клиента VoIP для Lync с другого сетевого сайта</span><span class="sxs-lookup"><span data-stu-id="08840-124">Lync VoIP client user from a different network site</span></span></p>
<p><span data-ttu-id="08840-125">Пользователь клиента VoIP для Lync с неизвестного сетевого сайта</span><span class="sxs-lookup"><span data-stu-id="08840-125">Lync VoIP client user from an unknown network site</span></span></p>
<p><span data-ttu-id="08840-126">Федеративный пользователь клиента VoIP для Lync</span><span class="sxs-lookup"><span data-stu-id="08840-126">Federated Lync VoIP client user</span></span></p>
<p><span data-ttu-id="08840-127">Пользователь присоединяется к конечной точке PSTN</span><span class="sxs-lookup"><span data-stu-id="08840-127">User joining from a PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="08840-128">Нет</span><span class="sxs-lookup"><span data-stu-id="08840-128">None</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="08840-129">Пользователи клиента VoIP для Lync с неизвестного сетевого сайта</span><span class="sxs-lookup"><span data-stu-id="08840-129">Lync VoIP client user(s) from an unknown network site</span></span></p></td>
<td><p><span data-ttu-id="08840-130">Пользователь клиента VoIP для Lync с любого сайта</span><span class="sxs-lookup"><span data-stu-id="08840-130">Lync VoIP client user from any site</span></span></p>
<p><span data-ttu-id="08840-131">Пользователь клиента VoIP для Lync с неизвестного сайта</span><span class="sxs-lookup"><span data-stu-id="08840-131">Lync VoIP client user from an unknown site</span></span></p>
<p><span data-ttu-id="08840-132">Федеративный пользователь клиента VoIP для Lync</span><span class="sxs-lookup"><span data-stu-id="08840-132">Federated Lync VoIP client user</span></span></p></td>
<td><p><span data-ttu-id="08840-133">Пользователь, присоединяющийся с помощью конечной точки PSTN</span><span class="sxs-lookup"><span data-stu-id="08840-133">User joining via a PSTN endpoint</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08840-134">Пользователи клиента VoIP для Lync с разных сетевых сайтов</span><span class="sxs-lookup"><span data-stu-id="08840-134">Lync VoIP client users from different network sites</span></span></p></td>
<td><p><span data-ttu-id="08840-135">Пользователь клиента VoIP для Lync с любого сетевого сайта</span><span class="sxs-lookup"><span data-stu-id="08840-135">Lync VoIP client user from any network site</span></span></p>
<p><span data-ttu-id="08840-136">Пользователь клиента VoIP для Lync с неизвестного сетевого сайта</span><span class="sxs-lookup"><span data-stu-id="08840-136">Lync VoIP client user from an unknown network site</span></span></p>
<p><span data-ttu-id="08840-137">Федеративный пользователь клиента VoIP для Lync</span><span class="sxs-lookup"><span data-stu-id="08840-137">Federated Lync VoIP client user</span></span></p></td>
<td><p><span data-ttu-id="08840-138">Пользователь, присоединяющийся с помощью конечной точки PSTN</span><span class="sxs-lookup"><span data-stu-id="08840-138">User joining via a PSTN endpoint</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="08840-139">Пользователи клиента VoIP VoIP из одного сетевого сайта и пользователей, присоединяющихся к конечной точке PSTN</span><span class="sxs-lookup"><span data-stu-id="08840-139">Lync VoIP client user(s) from a single network site and users joining from a PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="08840-140">Пользователь клиента VoIP для Lync с того же сетевого сайта</span><span class="sxs-lookup"><span data-stu-id="08840-140">Lync VoIP client user from the same network site</span></span></p></td>
<td><p><span data-ttu-id="08840-141">Пользователь клиента VoIP для Lync с другого сетевого сайта</span><span class="sxs-lookup"><span data-stu-id="08840-141">Lync VoIP client user from a different network site</span></span></p>
<p><span data-ttu-id="08840-142">Пользователь клиента VoIP для Lync с неизвестного сетевого сайта</span><span class="sxs-lookup"><span data-stu-id="08840-142">Lync VoIP client user from an unknown network site</span></span></p>
<p><span data-ttu-id="08840-143">Федеративный пользователь клиента VoIP для Lync</span><span class="sxs-lookup"><span data-stu-id="08840-143">Federated Lync VoIP client user</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="08840-144">Ниже приведены дополнительные характеристики приложения для конференц-связи с маршрутизацией на основе расположения.</span><span class="sxs-lookup"><span data-stu-id="08840-144">The following are additional characteristics of the Location-Based Routing Conferencing application:</span></span>

  - <span data-ttu-id="08840-145">Если пользователю не разрешено присоединяться к Конференции по определенным ограничениям маршрутизации, пользователи, вызываемые в конференции, будут отклонены, а клиент Lync будет сообщать о том, что вызов не был завершен или закончился.</span><span class="sxs-lookup"><span data-stu-id="08840-145">When a user is not allowed to join a conference given Location-Based Routing restrictions, the users call to the conference will be rejected and his Lync Client will report that the call was not completed or has ended.</span></span>

  - <span data-ttu-id="08840-146">Конечная точка PSTN, присоединяющаяся к Конференции с применением маршрутизации на основе расположения, не будет ограничена для присоединения к Конференции независимо от ее состояния, если конечная точка присоединяется через магистраль, для которого не включена маршрутизация на основе расположения.</span><span class="sxs-lookup"><span data-stu-id="08840-146">A PSTN endpoint joining a conference with Location-Based Routing enforcements will not be restricted to join the conference regardless of its state if the endpoint joins via a trunk that is not enabled for Location-Based Routing.</span></span>

  - <span data-ttu-id="08840-147">Система УАТС, подключенная к серверу-посреднику по магистральной линии SIP, которая не исходит звонки в PSTN, будет иметь те же применения, что и пользователи Lync, находящиеся на том же сетевом сайте, где определена магистральная линия SIP.</span><span class="sxs-lookup"><span data-stu-id="08840-147">A PBX system connected to a Mediations Server over a SIP trunk that does not egress calls to the PSTN will have the same enforcements as Lync users located in the same network site where the SIP trunk is defined.</span></span> <span data-ttu-id="08840-148">Например, конечная точка PSTN будет иметь возможность присоединиться к Конференции с пользователем УАТС и пользователем Lync, если они находятся на одном сетевом сайте; в противном случае конечная точка PSTN не сможет присоединиться к Конференции, если пользователь УАТС находится на другом сетевом сайте, отличном от пользователя Lync.</span><span class="sxs-lookup"><span data-stu-id="08840-148">For example, a PSTN endpoint will be able to join a conference with a PBX user and a Lync user if they are located in the same network site; otherwise, the PSTN endpoint will not be allowed to join the conference if the PBX user is in a different network site than the Lync user.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

