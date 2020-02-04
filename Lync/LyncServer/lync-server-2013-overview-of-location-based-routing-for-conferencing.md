---
title: 'Lync Server 2013: Общие сведения о маршрутизации на основе местоположения для конференций'
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
ms.openlocfilehash: adb103d1f2314e033d9ef0958dd05a7648012bde
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755523"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-location-based-routing-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="625f2-102">Обзор маршрутизации на основе местоположения для конференций в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="625f2-102">Overview of Location-Based Routing for conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="625f2-103">_**Тема последнего изменения:** 2013-07-19_</span><span class="sxs-lookup"><span data-stu-id="625f2-103">_**Topic Last Modified:** 2013-07-19_</span></span>

<span data-ttu-id="625f2-104">Приложение для конференц-связи с маршрутами на основе местоположения обеспечивает механизм для предотвращения бесплатных бесплатных обоснований на конференциях Lync.</span><span class="sxs-lookup"><span data-stu-id="625f2-104">The Location-Based Routing Conferencing application provides to Lync Conferences a mechanism for the prevention of PSTN toll bypass.</span></span> <span data-ttu-id="625f2-105">Приложение отслеживает активные Конференции и применяет ограничения для маршрутизации на основе местоположения на основе местоположения пользователей Lync.</span><span class="sxs-lookup"><span data-stu-id="625f2-105">The application monitors active conferences and enforces Location-Based Routing restrictions based on the location of the Lync users participating.</span></span>

<span data-ttu-id="625f2-106">Приложение для конференций с маршрутами на основе местоположения определяет, следует ли применять маршрутизацию на основе местоположения на собрании Lync, если выполняются указанные ниже условия.</span><span class="sxs-lookup"><span data-stu-id="625f2-106">The Location-Based Routing Conferencing application determines whether Location-Based Routing is to be enforced on a Lync meeting if the following criteria are met:</span></span>

  - <span data-ttu-id="625f2-107">Организатор собрания включен для маршрутизации на основе местоположения.</span><span class="sxs-lookup"><span data-stu-id="625f2-107">The meeting organizer is enabled for Location-Based Routing.</span></span> <span data-ttu-id="625f2-108">Ограничения маршрутизации, основанные на расположении, будут применяться только к конференц-атакам, упорядоченным по пользователям, для которых включена маршрутизация на основе местоположения.</span><span class="sxs-lookup"><span data-stu-id="625f2-108">Location-Based Routing restrictions will be applied only to conferences that are organized by users who are enabled for Location-Based Routing.</span></span>

  - <span data-ttu-id="625f2-109">Хотя бы один участник собрания является конечной точкой ТСОП.</span><span class="sxs-lookup"><span data-stu-id="625f2-109">At least one meeting participant is a PSTN endpoint.</span></span> <span data-ttu-id="625f2-110">Ограничения маршрутизации, основанные на расположении, применимы только для конференций, использующих конечные точки PSTN.</span><span class="sxs-lookup"><span data-stu-id="625f2-110">Location-Based Routing restrictions are applicable only for conferences that include PSTN endpoints.</span></span>

  - <span data-ttu-id="625f2-111">Сетевой сайт, где находится шлюз ТСОП, используемый для подключения конференции к ТСОП, а также сетевые сайты, из которых подключаются организаторы и участники.</span><span class="sxs-lookup"><span data-stu-id="625f2-111">The network site where the PSTN gateway used to bridge the conference to the PSTN is located as well as the network sites where the organizers and participants are connecting from.</span></span>

<span data-ttu-id="625f2-112">Приложение для конференц-связи с маршрутизацией на основе местоположения предотвращает участие пользователей Lync и КОММУТИРУЕМых конечных точек с разных сетевых сайтов для одной конференции.</span><span class="sxs-lookup"><span data-stu-id="625f2-112">The Location-Based Routing Conferencing application prevents the participation of Lync users and PSTN endpoints from different network sites to the same conference.</span></span> <span data-ttu-id="625f2-113">Если для организатора собрания включена маршрутизация на основе местоположения, приложение для конференц-связи накладывает указанные ниже ограничения.</span><span class="sxs-lookup"><span data-stu-id="625f2-113">If the organizer of a meeting is enabled for Location-Based Routing, the Conferencing application enforces the following restrictions:</span></span>

  - <span data-ttu-id="625f2-114">Конечные точки, которые могут присоединиться к собранию Lync, зависят от конечных точек, которые уже присоединились к Конференции, и это ограничение настраивается так, чтобы присоединиться к Конференции и добавить конечные точки.</span><span class="sxs-lookup"><span data-stu-id="625f2-114">The endpoints that can join a Lync meeting depend on the endpoints that already joined the conference, and this restriction adjusts as joined endpoints leave and new endpoints join the conference.</span></span> <span data-ttu-id="625f2-115">Если организаторов и участники присоединяются к собранию Lync с помощью того же сайта сети, конечная точка PSTN, другой участник на том же сайте сети или другой участник с неизвестного сетевого сайта может объединения.</span><span class="sxs-lookup"><span data-stu-id="625f2-115">If organizers and participants are joining a Lync meeting from the same network site, then a PSTN endpoint, another participant from the same network site, another participant from a different network site or a participant from an unknown network site are allowed to join.</span></span>

  - <span data-ttu-id="625f2-116">Если организаторы и участники присоединились к собранию из разных или неизвестных сетевых сайтов, конечной точке ТСОП запрещено присоединяться к собранию в случае, если звонок ТСОП поступает из магистрали SIP, для которой включена маршрутизация на основе расположения.</span><span class="sxs-lookup"><span data-stu-id="625f2-116">If organizers and participants are joining the meeting from different or unknown network sites, a PSTN endpoint is not allowed to join the meeting if the PSTN call ingresses from a SIP trunk enabled for Location-Based Routing.</span></span>

  - <span data-ttu-id="625f2-117">Если организаторов и участники присоединяются к собранию из того же сайта сети, а участники, присоединяющиеся к этому же собранию, не могут присоединиться к собранию, в конечную точку Lync с другого сайта сети.</span><span class="sxs-lookup"><span data-stu-id="625f2-117">If organizers and participants are all joining the meeting from the same network site and there are participants joining the same meeting from the PSTN, a Lync endpoint from a different network site is not allowed to join the meeting.</span></span>

<span data-ttu-id="625f2-118">В таблице ниже приведены ограничения на маршрутизацию на основе местоположения.</span><span class="sxs-lookup"><span data-stu-id="625f2-118">These conferencing Location-Based Routing restrictions are summarized in the following table.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="625f2-119">Пользователи конференции на данный момент</span><span class="sxs-lookup"><span data-stu-id="625f2-119">User(s) in a conference at any given point</span></span></p></td>
<td><p><span data-ttu-id="625f2-120">Пользователи, которым разрешено присоединяться к конференции</span><span class="sxs-lookup"><span data-stu-id="625f2-120">User(s) allowed to join the conference</span></span></p></td>
<td><p><span data-ttu-id="625f2-121">Пользователи, которым запрещено присоединяться к конференции</span><span class="sxs-lookup"><span data-stu-id="625f2-121">User(s) not allowed to join the conference</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="625f2-122">Пользователи клиентов Lync VoIP с одного сайта сети</span><span class="sxs-lookup"><span data-stu-id="625f2-122">Lync VoIP client user(s) from a single network site</span></span></p></td>
<td><p><span data-ttu-id="625f2-123">Пользовательский клиент Lync VoIP с того же сайта сети</span><span class="sxs-lookup"><span data-stu-id="625f2-123">Lync VoIP client user from the same network site</span></span></p>
<p><span data-ttu-id="625f2-124">Пользовательский клиент Lync VoIP с другого сайта сети</span><span class="sxs-lookup"><span data-stu-id="625f2-124">Lync VoIP client user from a different network site</span></span></p>
<p><span data-ttu-id="625f2-125">Пользовательский клиент Lync VoIP с неизвестного сетевого сайта</span><span class="sxs-lookup"><span data-stu-id="625f2-125">Lync VoIP client user from an unknown network site</span></span></p>
<p><span data-ttu-id="625f2-126">Пользователь федеративного клиента Lync VoIP</span><span class="sxs-lookup"><span data-stu-id="625f2-126">Federated Lync VoIP client user</span></span></p>
<p><span data-ttu-id="625f2-127">Пользователь, присоединяющийся с помощью конечной точки ТСОП</span><span class="sxs-lookup"><span data-stu-id="625f2-127">User joining from a PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="625f2-128">Нет</span><span class="sxs-lookup"><span data-stu-id="625f2-128">None</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="625f2-129">Пользователи клиентов Lync VoIP с неизвестного сетевого сайта</span><span class="sxs-lookup"><span data-stu-id="625f2-129">Lync VoIP client user(s) from an unknown network site</span></span></p></td>
<td><p><span data-ttu-id="625f2-130">Пользовательский клиент Lync VoIP с любого сайта</span><span class="sxs-lookup"><span data-stu-id="625f2-130">Lync VoIP client user from any site</span></span></p>
<p><span data-ttu-id="625f2-131">Пользователь Lync для клиента VoIP с неизвестного сайта</span><span class="sxs-lookup"><span data-stu-id="625f2-131">Lync VoIP client user from an unknown site</span></span></p>
<p><span data-ttu-id="625f2-132">Пользователь федеративного клиента Lync VoIP</span><span class="sxs-lookup"><span data-stu-id="625f2-132">Federated Lync VoIP client user</span></span></p></td>
<td><p><span data-ttu-id="625f2-133">Пользователь, присоединяющийся с помощью конечной точки ТСОП</span><span class="sxs-lookup"><span data-stu-id="625f2-133">User joining via a PSTN endpoint</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="625f2-134">Пользователи клиентов Lync VoIP с разных сетевых сайтов</span><span class="sxs-lookup"><span data-stu-id="625f2-134">Lync VoIP client users from different network sites</span></span></p></td>
<td><p><span data-ttu-id="625f2-135">Пользовательский клиент Lync VoIP с любого сайта сети</span><span class="sxs-lookup"><span data-stu-id="625f2-135">Lync VoIP client user from any network site</span></span></p>
<p><span data-ttu-id="625f2-136">Пользовательский клиент Lync VoIP с неизвестного сетевого сайта</span><span class="sxs-lookup"><span data-stu-id="625f2-136">Lync VoIP client user from an unknown network site</span></span></p>
<p><span data-ttu-id="625f2-137">Пользователь федеративного клиента Lync VoIP</span><span class="sxs-lookup"><span data-stu-id="625f2-137">Federated Lync VoIP client user</span></span></p></td>
<td><p><span data-ttu-id="625f2-138">Пользователь, присоединяющийся с помощью конечной точки ТСОП</span><span class="sxs-lookup"><span data-stu-id="625f2-138">User joining via a PSTN endpoint</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="625f2-139">Пользователи пользователей Lync VoIP с одного сайта сети и пользователями, присоединенными из конечной точки PSTN</span><span class="sxs-lookup"><span data-stu-id="625f2-139">Lync VoIP client user(s) from a single network site and users joining from a PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="625f2-140">Пользовательский клиент Lync VoIP с того же сайта сети</span><span class="sxs-lookup"><span data-stu-id="625f2-140">Lync VoIP client user from the same network site</span></span></p></td>
<td><p><span data-ttu-id="625f2-141">Пользовательский клиент Lync VoIP с другого сайта сети</span><span class="sxs-lookup"><span data-stu-id="625f2-141">Lync VoIP client user from a different network site</span></span></p>
<p><span data-ttu-id="625f2-142">Пользовательский клиент Lync VoIP с неизвестного сетевого сайта</span><span class="sxs-lookup"><span data-stu-id="625f2-142">Lync VoIP client user from an unknown network site</span></span></p>
<p><span data-ttu-id="625f2-143">Пользователь федеративного клиента Lync VoIP</span><span class="sxs-lookup"><span data-stu-id="625f2-143">Federated Lync VoIP client user</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="625f2-144">Ниже приведены дополнительные характеристики приложения для конференц-связи с использованием маршрутов.</span><span class="sxs-lookup"><span data-stu-id="625f2-144">The following are additional characteristics of the Location-Based Routing Conferencing application:</span></span>

  - <span data-ttu-id="625f2-145">Если пользователю не разрешено присоединиться к Конференции с учетом ограничений на использование местоположения, пользователи, вызывающие конференцию, будут отвергнуты, а клиент Lync сообщит о том, что звонок не был завершен или закончился.</span><span class="sxs-lookup"><span data-stu-id="625f2-145">When a user is not allowed to join a conference given Location-Based Routing restrictions, the users call to the conference will be rejected and his Lync Client will report that the call was not completed or has ended.</span></span>

  - <span data-ttu-id="625f2-146">Конечная точка PSTN, соединяющая конференцию с принудительной маршрутизацией на основе местоположения, не сможет присоединиться к Конференции вне зависимости от ее состояния, если конечная точка присоединяется по каналу, для которого не включена маршрутизация на основе местоположения.</span><span class="sxs-lookup"><span data-stu-id="625f2-146">A PSTN endpoint joining a conference with Location-Based Routing enforcements will not be restricted to join the conference regardless of its state if the endpoint joins via a trunk that is not enabled for Location-Based Routing.</span></span>

  - <span data-ttu-id="625f2-147">Система УАТС, подключенная к серверу-источнику данных, на магистральной магистрали SIP, не использующая звонки в КТСОП, будет выполнять те же принудительные применения, что и пользователи Lync, находящиеся на веб-сайте, на котором определена магистральная сеть SIP.</span><span class="sxs-lookup"><span data-stu-id="625f2-147">A PBX system connected to a Mediations Server over a SIP trunk that does not egress calls to the PSTN will have the same enforcements as Lync users located in the same network site where the SIP trunk is defined.</span></span> <span data-ttu-id="625f2-148">Например, конечная точка PSTN сможет присоединиться к Конференции с помощью пользователя УАТС и пользователя Lync, если они находятся на одном сайте сети. в противном случае конечной точке PSTN не будет разрешено присоединиться к Конференции, если пользователь УАТС находится на другом сайте сети, чем пользователь Lync.</span><span class="sxs-lookup"><span data-stu-id="625f2-148">For example, a PSTN endpoint will be able to join a conference with a PBX user and a Lync user if they are located in the same network site; otherwise, the PSTN endpoint will not be allowed to join the conference if the PBX user is in a different network site than the Lync user.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

