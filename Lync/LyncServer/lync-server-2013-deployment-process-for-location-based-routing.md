---
title: 'Lync Server 2013: процесс развертывания для маршрутизации Location-Based'
description: 'Lync Server 2013: процесс развертывания для маршрутизации Location-Based.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for Location-Based Routing
ms:assetid: 9e923e72-83fc-4a4f-8937-28a55739ed3e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994055(v=OCS.15)
ms:contentKeyID: 51803966
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2c321d9b0eada6e9501b2ded69120feae36be171
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551065"
---
# <a name="deployment-process-for-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="3d9e4-103">Процесс развертывания для маршрутизации Location-Based в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3d9e4-103">Deployment process for Location-Based Routing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3d9e4-104">_**Последнее изменение темы:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="3d9e4-104">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="3d9e4-105">В этом разделе представлен обзор процесса настройки маршрутизации Location-Based.</span><span class="sxs-lookup"><span data-stu-id="3d9e4-105">This topic provides an overview of the process involved in configuring Location-Based Routing.</span></span> <span data-ttu-id="3d9e4-106">Перед настройкой маршрутизации Location-Based необходимо развернуть Lync Server Enterprise Edition или Standard Edition с корпоративной голосовой связью.</span><span class="sxs-lookup"><span data-stu-id="3d9e4-106">You must deploy Lync Server Enterprise Edition or Standard Edition with Enterprise Voice before you configure Location-Based Routing.</span></span> <span data-ttu-id="3d9e4-107">Компоненты, необходимые для маршрутизации Location-Based, уже установлены и включены при развертывании корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="3d9e4-107">The components required by Location-Based Routing are already installed and enabled when you deploy Enterprise Voice.</span></span>

### <a name="location-based-routing-deployment-process"></a><span data-ttu-id="3d9e4-108">Процесс развертывания Location-Based маршрутизации</span><span class="sxs-lookup"><span data-stu-id="3d9e4-108">Location-Based Routing Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3d9e4-109">Этап</span><span class="sxs-lookup"><span data-stu-id="3d9e4-109">Phase</span></span></th>
<th><span data-ttu-id="3d9e4-110">Действия</span><span class="sxs-lookup"><span data-stu-id="3d9e4-110">Steps</span></span></th>
<th><span data-ttu-id="3d9e4-111">Необходимые группы и роли</span><span class="sxs-lookup"><span data-stu-id="3d9e4-111">Required groups and roles</span></span></th>
<th><span data-ttu-id="3d9e4-112">Документация по развертыванию</span><span class="sxs-lookup"><span data-stu-id="3d9e4-112">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3d9e4-113">Развертывание корпоративной голосовой связи</span><span class="sxs-lookup"><span data-stu-id="3d9e4-113">Deploy Enterprise Voice</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="3d9e4-114">Настройка магистральных линий связи</span><span class="sxs-lookup"><span data-stu-id="3d9e4-114">Configure Trunks</span></span></p></li>
<li><p><span data-ttu-id="3d9e4-115">Создание политик голосовой связи</span><span class="sxs-lookup"><span data-stu-id="3d9e4-115">Create Voice Policies</span></span></p></li>
<li><p><span data-ttu-id="3d9e4-116">Определение маршрутов голосовой связи</span><span class="sxs-lookup"><span data-stu-id="3d9e4-116">Define Voice Routes</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="3d9e4-117">ксвоицеадминс</span><span class="sxs-lookup"><span data-stu-id="3d9e4-117">CSVoiceAdmins</span></span><br />
<span data-ttu-id="3d9e4-118">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="3d9e4-118">CsAdministrator</span></span><br />
<span data-ttu-id="3d9e4-119">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="3d9e4-119">CsServerAdministrator</span></span></p></td>
<td><p><span data-ttu-id="3d9e4-120">Развертывание корпоративной голосовой связи</span><span class="sxs-lookup"><span data-stu-id="3d9e4-120">Deploying Enterprise Voice</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3d9e4-121">Проверка развертывания корпоративной голосовой связи</span><span class="sxs-lookup"><span data-stu-id="3d9e4-121">Verify your Enterprise Voice deployment</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3d9e4-122">ксвоицеадминс</span><span class="sxs-lookup"><span data-stu-id="3d9e4-122">CSVoiceAdmins</span></span><br />
<span data-ttu-id="3d9e4-123">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="3d9e4-123">CsAdministrator</span></span><br />
<span data-ttu-id="3d9e4-124">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="3d9e4-124">CsServerAdministrator</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3d9e4-125">Настройка областей сети, сайтов и подсетей</span><span class="sxs-lookup"><span data-stu-id="3d9e4-125">Configure network regions, sites, and subnets</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="3d9e4-126">Создание областей сети</span><span class="sxs-lookup"><span data-stu-id="3d9e4-126">Create network regions</span></span></p></li>
<li><p><span data-ttu-id="3d9e4-127">Создание сетевых сайтов</span><span class="sxs-lookup"><span data-stu-id="3d9e4-127">Create network sites</span></span></p></li>
<li><p><span data-ttu-id="3d9e4-128">Связывает подсети с сетевыми сайтами</span><span class="sxs-lookup"><span data-stu-id="3d9e4-128">Associates subnets with network sites</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="3d9e4-129">ксвоицеадминс</span><span class="sxs-lookup"><span data-stu-id="3d9e4-129">CSVoiceAdmins</span></span><br />
<span data-ttu-id="3d9e4-130">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="3d9e4-130">CsAdministrator</span></span><br />
<span data-ttu-id="3d9e4-131">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="3d9e4-131">CsServerAdministrator</span></span></p></td>
<td><p><span data-ttu-id="3d9e4-132">О сетевых областях, сайтах и подсетях</span><span class="sxs-lookup"><span data-stu-id="3d9e4-132">About Network Regions, Sites, and Subnets</span></span><br />
<span data-ttu-id="3d9e4-133">Создание или изменение сетевой области</span><span class="sxs-lookup"><span data-stu-id="3d9e4-133">Create or Modify a Network Region</span></span><br />
<span data-ttu-id="3d9e4-134">Создание или изменение сетевого сайта</span><span class="sxs-lookup"><span data-stu-id="3d9e4-134">Create or Modify a Network Site</span></span><br />
<span data-ttu-id="3d9e4-135">Связь подсети с сетевым сайтом</span><span class="sxs-lookup"><span data-stu-id="3d9e4-135">Associate a Subnet with a Network Site</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3d9e4-136">Настройка маршрутизации Location-Based</span><span class="sxs-lookup"><span data-stu-id="3d9e4-136">Configure Location-Based Routing</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="3d9e4-137">Создание политик маршрутизации голосовых вызовов</span><span class="sxs-lookup"><span data-stu-id="3d9e4-137">Create voice routing policies</span></span></p></li>
<li><p><span data-ttu-id="3d9e4-138">Определение отдельной конфигурации магистрали для каждой магистрали</span><span class="sxs-lookup"><span data-stu-id="3d9e4-138">Define separate trunk configuration per trunk</span></span></p></li>
<li><p><span data-ttu-id="3d9e4-139">Изменение политик голосовой связи</span><span class="sxs-lookup"><span data-stu-id="3d9e4-139">Modify voice policies</span></span></p></li>
<li><p><span data-ttu-id="3d9e4-140">Включение конфигурации маршрутизации Location-Based</span><span class="sxs-lookup"><span data-stu-id="3d9e4-140">Enable Location-Based Routing configuration</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="3d9e4-141">ксвоицеадминс</span><span class="sxs-lookup"><span data-stu-id="3d9e4-141">CSVoiceAdmins</span></span><br />
<span data-ttu-id="3d9e4-142">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="3d9e4-142">CsAdministrator</span></span><br />
<span data-ttu-id="3d9e4-143">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="3d9e4-143">CsServerAdministrator</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>

## <a name="sample-deployment"></a><span data-ttu-id="3d9e4-144">Пример развертывания</span><span class="sxs-lookup"><span data-stu-id="3d9e4-144">Sample Deployment</span></span>

<span data-ttu-id="3d9e4-145">Для дальнейшего использования механизмов, включенных при маршрутизации Location-Based, используется следующее развертывание.</span><span class="sxs-lookup"><span data-stu-id="3d9e4-145">The following deployment is used to illustrate further the mechanisms enabled by Location-Based Routing.</span></span>

<span data-ttu-id="3d9e4-146">![e1bd2230 — 44da – 4784 — b359 – 24572b6ce02d](images/JJ994055.e1bd2230-44da-4784-b359-24572b6ce02d(OCS.15).png "e1bd2230 — 44da – 4784 — b359 – 24572b6ce02d")</span><span class="sxs-lookup"><span data-stu-id="3d9e4-146">![e1bd2230-44da-4784-b359-24572b6ce02d](images/JJ994055.e1bd2230-44da-4784-b359-24572b6ce02d(OCS.15).png "e1bd2230-44da-4784-b359-24572b6ce02d")</span></span>

<div>

## <a name="incoming-pstn-calls"></a><span data-ttu-id="3d9e4-147">Входящие звонки PSTN</span><span class="sxs-lookup"><span data-stu-id="3d9e4-147">Incoming PSTN calls</span></span>

<span data-ttu-id="3d9e4-148">Администратор может включить магистраль, определенный для маршрутизации вызовов на шлюз "сайт 1", для маршрутизации Location-Based и связать шлюз "сайт 1" с сайтом 1.</span><span class="sxs-lookup"><span data-stu-id="3d9e4-148">An administrator can enable the trunk defined to route calls to “Site 1 Gateway” for Location-Based Routing and associate the “Site 1 Gateway” to site 1.</span></span> <span data-ttu-id="3d9e4-149">После включения вызовы, направляемые через шлюз "сайт 1", будут перенаправляться только пользователям, расположенным на сайте 1.</span><span class="sxs-lookup"><span data-stu-id="3d9e4-149">Once enabled, calls that are routed through “Site 1 Gateway“ will only be routed to users that are located in site 1.</span></span> <span data-ttu-id="3d9e4-150">Все вызовы, направляемые через магистраль "шлюз сайта 1", предназначенные для пользователей на другом сайте, такие как сайт 2, будут заблокированы для предотвращения бесплатных звонков по сети PSTN.</span><span class="sxs-lookup"><span data-stu-id="3d9e4-150">All calls routed through the “Site 1 Gateway” trunk destined to users in a different site, such as site 2 will be blocked to prevent PSTN toll bypass.</span></span>

<span data-ttu-id="3d9e4-151">Все входящие звонки PSTN через шлюз "сайт 1" могут маршрутизироваться только к конечным точкам, расположенным на сайте 1.</span><span class="sxs-lookup"><span data-stu-id="3d9e4-151">All incoming PSTN calls through “Site 1 Gateway” will only be allowed to route to endpoints located in site 1.</span></span> <span data-ttu-id="3d9e4-152">Например, когда "Lync User 1" перемещается на сайт 2, все входящие вызовы PSTN через шлюз "сайт 1" не будут маршрутизироваться в конечные точки "Lync User 1", расположенные на сайте 2.</span><span class="sxs-lookup"><span data-stu-id="3d9e4-152">For example, when “Lync user 1” travels to site 2, all incoming PSTN calls through “Site 1 Gateway” will not be routed to “Lync user 1” endpoints located in site 2.</span></span> <span data-ttu-id="3d9e4-153">То же правило маршрутизации применяется, если сообщение "Lync User 1" перемещается на неизвестный сетевой сайт, на котором невозможно определить расположение пользователя.</span><span class="sxs-lookup"><span data-stu-id="3d9e4-153">The same routing rule applies if “Lync user 1” travels to an unknown network site where the user’s location can’t be determined.</span></span>

<span data-ttu-id="3d9e4-154">В следующей таблице показано взаимодействие с пользователем Lync User 1 в этом контексте.</span><span class="sxs-lookup"><span data-stu-id="3d9e4-154">The following table outlines the user experience of “Lync user 1” in this context.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="3d9e4-155">Конечные точки пользователя Lync 1, расположенные на сетевом сайте 1</span><span class="sxs-lookup"><span data-stu-id="3d9e4-155">Lync user 1 endpoints located in network site 1</span></span></th>
<th><span data-ttu-id="3d9e4-156">Конечные точки пользователя Lync 1, расположенные на сетевом сайте 2</span><span class="sxs-lookup"><span data-stu-id="3d9e4-156">Lync user 1 endpoints located in network site 2</span></span></th>
<th><span data-ttu-id="3d9e4-157">Конечные точки пользователя Lync 1 расположены на неизвестном сетевом сайте</span><span class="sxs-lookup"><span data-stu-id="3d9e4-157">Lync user 1 endpoints located in unknown network site</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3d9e4-158">Входящие вызовы PSTN для пользователя Lync 1</span><span class="sxs-lookup"><span data-stu-id="3d9e4-158">Inbound PSTN calls to Lync user 1</span></span></p></td>
<td><p><span data-ttu-id="3d9e4-159">Звонки направляются на конечные точки в этом расположении</span><span class="sxs-lookup"><span data-stu-id="3d9e4-159">Calls are routed to endpoints in this location</span></span></p></td>
<td><p><span data-ttu-id="3d9e4-160">Звонки не направляются на конечные точки в этом расположении</span><span class="sxs-lookup"><span data-stu-id="3d9e4-160">Calls are not routed to endpoints in this location</span></span></p></td>
<td><p><span data-ttu-id="3d9e4-161">Звонки не направляются на конечные точки в этом расположении</span><span class="sxs-lookup"><span data-stu-id="3d9e4-161">Calls are not routed to endpoints in this location</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="outgoing-pstn-calls"></a><span data-ttu-id="3d9e4-162">Исходящие вызовы PSTN</span><span class="sxs-lookup"><span data-stu-id="3d9e4-162">Outgoing PSTN calls</span></span>

<span data-ttu-id="3d9e4-163">Маршруты голосовых вызовов указываются в политиках голосовой связи, назначенных непосредственно пользователям, и политиках маршрутизации голосовой связи, назначенных сетевым сайтам.</span><span class="sxs-lookup"><span data-stu-id="3d9e4-163">Voice routes are referenced in both Voice Policies assigned directly to users, and Voice Routing Policies assigned to network sites.</span></span> <span data-ttu-id="3d9e4-164">Обе политики содержат ссылки на маршруты, которые можно использовать для нахождения вызова по-другому.</span><span class="sxs-lookup"><span data-stu-id="3d9e4-164">Both policies contain references to routes, which can be used to route a call differently.</span></span> <span data-ttu-id="3d9e4-165">Например, администратор может определить политику маршрутизации голосовых вызовов для всех пользователей, расположенных на сетевом сайте 1, для маршрутизации всех исходящих вызовов через шлюз "сайт 1", в то время как политика голосовой связи для всех исходящих вызовов через шлюз "сайт 2".</span><span class="sxs-lookup"><span data-stu-id="3d9e4-165">For example, an administrator can define a Voice Routing Policy for all users located in network site 1 to route all outbound calls through the “Site 1 Gateway” while the Voice Policy of some users define a route for all outbound calls through the “Site 2 Gateway”.</span></span> <span data-ttu-id="3d9e4-166">Хотя эти пользователи находятся в сетевом сайте 1, их исходящие звонки будут маршрутизироваться через шлюз "сайт 1".</span><span class="sxs-lookup"><span data-stu-id="3d9e4-166">While these users are located in network site 1, their outbound calls will be routed through the “Site 1 Gateway”.</span></span>

<span data-ttu-id="3d9e4-167">Когда пользователь находится на сетевом сайте, настроенном для маршрутизации Location-Based, маршрут политики маршрутизации голосовой связи на сетевом сайте переопределяет маршрут политики голосовой связи пользователя.</span><span class="sxs-lookup"><span data-stu-id="3d9e4-167">When a user is located in a network site configured for Location-Based Routing, the network site’s Voice Routing Policy route overrides the user’s Voice Policy route.</span></span> <span data-ttu-id="3d9e4-168">Это правило особенно удобно для пользователей, которые временно переходят на другой сайт.</span><span class="sxs-lookup"><span data-stu-id="3d9e4-168">This rule is particularly useful for users that temporarily move to a different site.</span></span> <span data-ttu-id="3d9e4-169">В этом конкретном случае пользователь всегда будет использовать шлюз, который является локальным по отношению к его расположению; Если "Lync User 3" расположен по адресу "сайт 2", все его исходящие звонки будут маршрутизироваться через шлюз сайта 2, но если он перейдет на сайт 1, все исходящие звонки, размещенные на сайте 1, будут маршрутизироваться через шлюз "сайт 1".</span><span class="sxs-lookup"><span data-stu-id="3d9e4-169">In this particular case a user will always use a gateway that is local to his location; if “Lync user 3” is located at “Site 2”, all his outbound calls will be routed via “Site 2 Gateway”, but if he travels to site 1, all his outbound calls placed while he’s at site 1 will be routed through “Site 1 Gateway”.</span></span>

<span data-ttu-id="3d9e4-170">В следующей таблице показано, как пользователь Lync User 1 помещает исходящий вызов со следующих сетевых сайтов.</span><span class="sxs-lookup"><span data-stu-id="3d9e4-170">The following table illustrates the user experience of Lync user 1 placing an outbound call from the following network sites.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="3d9e4-171">Сетевой сайт 1</span><span class="sxs-lookup"><span data-stu-id="3d9e4-171">Network site 1</span></span></th>
<th><span data-ttu-id="3d9e4-172">Сетевой сайт 2</span><span class="sxs-lookup"><span data-stu-id="3d9e4-172">Network site 2</span></span></th>
<th><span data-ttu-id="3d9e4-173">Неизвестный сетевой сайт или не включена маршрутизация Location-Based</span><span class="sxs-lookup"><span data-stu-id="3d9e4-173">Unknown network site or not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3d9e4-174">Авторизация исходящих вызовов</span><span class="sxs-lookup"><span data-stu-id="3d9e4-174">Authorization of outbound calls</span></span></p></td>
<td><p><span data-ttu-id="3d9e4-175">Политика голосовой связи пользователя Lync 1</span><span class="sxs-lookup"><span data-stu-id="3d9e4-175">Lync user 1 voice policy</span></span></p></td>
<td><p><span data-ttu-id="3d9e4-176">Политика голосовой связи пользователя Lync 1</span><span class="sxs-lookup"><span data-stu-id="3d9e4-176">Lync user 1 voice policy</span></span></p></td>
<td><p><span data-ttu-id="3d9e4-177">Политика голосовой связи пользователя Lync 1</span><span class="sxs-lookup"><span data-stu-id="3d9e4-177">Lync user 1 voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3d9e4-178">Маршрутизация исходящих вызовов</span><span class="sxs-lookup"><span data-stu-id="3d9e4-178">Routing of outbound calls</span></span></p></td>
<td><p><span data-ttu-id="3d9e4-179">Политика маршрутизации голосовой связи для сайта 1</span><span class="sxs-lookup"><span data-stu-id="3d9e4-179">Site 1 voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="3d9e4-180">Политика маршрутизации голосовой связи на сайте 2</span><span class="sxs-lookup"><span data-stu-id="3d9e4-180">Site 2 voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="3d9e4-181">Политика голосовой связи пользователя и только для тех систем, для которых не включена маршрутизация Location-Based</span><span class="sxs-lookup"><span data-stu-id="3d9e4-181">User’s voice policy and only to systems not enabled for Location-Based Routing</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="call-transfers-and-forwards"></a><span data-ttu-id="3d9e4-182">Передача и переадресация звонков</span><span class="sxs-lookup"><span data-stu-id="3d9e4-182">Call transfers and forwards</span></span>

<span data-ttu-id="3d9e4-183">При передаче или пересылке вызовов на маршрутизацию вызовов влияет Location-Based маршрутизация.</span><span class="sxs-lookup"><span data-stu-id="3d9e4-183">When calls are transferred or forwarded, the routing of calls is affected by Location-Based Routing.</span></span>

<span data-ttu-id="3d9e4-184">В приведенной ниже таблице показано, как пользователь Lync 1 пересылает или пересылает вызовы PSTN другому пользователю Lync.</span><span class="sxs-lookup"><span data-stu-id="3d9e4-184">The following table depicts Lync user 1 transferring or forwarding a PSTN call to another Lync user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3d9e4-185">Пользователь, инициирующий передачу или переадресацию вызовов</span><span class="sxs-lookup"><span data-stu-id="3d9e4-185">User initiating call transfer or forward</span></span></th>
<th><span data-ttu-id="3d9e4-186">Пользователь Lync 2</span><span class="sxs-lookup"><span data-stu-id="3d9e4-186">Lync user 2</span></span></th>
<th><span data-ttu-id="3d9e4-187">Пользователь Lync 4</span><span class="sxs-lookup"><span data-stu-id="3d9e4-187">Lync user 4</span></span></th>
<th><span data-ttu-id="3d9e4-188">Пользователь Lync на сетевом сайте не включен для маршрутизации Location-Based</span><span class="sxs-lookup"><span data-stu-id="3d9e4-188">Lync user in network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3d9e4-189">Пользователь Lync 1</span><span class="sxs-lookup"><span data-stu-id="3d9e4-189">Lync user 1</span></span></p></td>
<td><p><span data-ttu-id="3d9e4-190">Переадресация звонков или передача разрешена</span><span class="sxs-lookup"><span data-stu-id="3d9e4-190">Call forward or transfer is allowed</span></span></p></td>
<td><p><span data-ttu-id="3d9e4-191">Переадресация вызовов и передача запрещены</span><span class="sxs-lookup"><span data-stu-id="3d9e4-191">Call forward or transfer is not allowed</span></span></p></td>
<td><p><span data-ttu-id="3d9e4-192">Переадресация вызовов и передача запрещены</span><span class="sxs-lookup"><span data-stu-id="3d9e4-192">Call forward or transfer is not allowed</span></span></p></td>
</tr>
</tbody>
</table>

  
<span data-ttu-id="3d9e4-193">В следующей таблице показано, как маршрутизация Location-Based влияет на маршрутизацию вызовов в зависимости от расположения передаваемого пользователя Lync (Lync User 2, Lync User 4 и т. д.) на конечную точку PSTN.</span><span class="sxs-lookup"><span data-stu-id="3d9e4-193">The following table illustrates how Location-Based Routing affects how the call is routed based on the location of the Lync user being transferred (Lync user 2, Lync user 4, etc) to a PSTN endpoint</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3d9e4-194">Конечная точка, в которую пересылается или передается вызов</span><span class="sxs-lookup"><span data-stu-id="3d9e4-194">Endpoint where call is transferred or forwarded to</span></span></th>
<th><span data-ttu-id="3d9e4-195">Пользователь Lync 2</span><span class="sxs-lookup"><span data-stu-id="3d9e4-195">Lync user 2</span></span></th>
<th><span data-ttu-id="3d9e4-196">Пользователь Lync 4</span><span class="sxs-lookup"><span data-stu-id="3d9e4-196">Lync user 4</span></span></th>
<th><span data-ttu-id="3d9e4-197">Пользователь Lync на сетевом сайте не включен для маршрутизации Location-Based</span><span class="sxs-lookup"><span data-stu-id="3d9e4-197">Lync user in network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3d9e4-198">Конечная точка PSTN</span><span class="sxs-lookup"><span data-stu-id="3d9e4-198">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="3d9e4-199">Переадресация звонков или передача выполняется через политику маршрутизации голосовой связи на сайте 1 и исходящий через шлюз сайта 1</span><span class="sxs-lookup"><span data-stu-id="3d9e4-199">Call forward or transfer is routed through site 1 voice routing policy and egress via Site 1 Gateway</span></span></p></td>
<td><p><span data-ttu-id="3d9e4-200">Переадресация звонков или передача выполняется через политику маршрутизации голосовой связи на сайте 2 и исходящий через шлюз сайта 2</span><span class="sxs-lookup"><span data-stu-id="3d9e4-200">Call forward or transfer is routed through site 2 voice routing policy and egress via Site 2 Gateway</span></span></p></td>
<td><p><span data-ttu-id="3d9e4-201">Переадресация звонка или передача направляются через политику голосовой связи пользователя Lync и исходящий через шлюз, не включенный для маршрутизации на основе расположения (при наличии).</span><span class="sxs-lookup"><span data-stu-id="3d9e4-201">Call forward or transfer is routed through the Lync user voice policy and egress via a gateway not enabled for location-based routing (if available)</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="simultaneous-ringing"></a><span data-ttu-id="3d9e4-202">Одновременный звонок</span><span class="sxs-lookup"><span data-stu-id="3d9e4-202">Simultaneous ringing</span></span>

<span data-ttu-id="3d9e4-203">После настройки маршрутизации на основе расположения в образце топологии применяются следующие взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="3d9e4-203">Once location-based routing is configured in the sample topology, the following interactions are enforced.</span></span>

<span data-ttu-id="3d9e4-204">В следующей таблице показано, поддерживает ли маршрутизацию Location-Based одновременные звонки для разных пользователей Lync (например, пользователи Lync 2, Lync User 4 и т. д.).</span><span class="sxs-lookup"><span data-stu-id="3d9e4-204">The following table illustrates whether Location-Based Routing allows simultaneous ringing for different Lync users (i.e. Lync user 2, Lync user 4, etc).</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3d9e4-205">Входящий конечный звонок для PSTN</span><span class="sxs-lookup"><span data-stu-id="3d9e4-205">Incoming PSTN call target</span></span></th>
<th><span data-ttu-id="3d9e4-206">Пользователь Lync 2</span><span class="sxs-lookup"><span data-stu-id="3d9e4-206">Lync user 2</span></span></th>
<th><span data-ttu-id="3d9e4-207">Пользователь Lync 4</span><span class="sxs-lookup"><span data-stu-id="3d9e4-207">Lync user 4</span></span></th>
<th><span data-ttu-id="3d9e4-208">Пользователь Lync на сетевом сайте не включен для маршрутизации Location-Based</span><span class="sxs-lookup"><span data-stu-id="3d9e4-208">Lync user in network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3d9e4-209">Пользователь Lync 1</span><span class="sxs-lookup"><span data-stu-id="3d9e4-209">Lync user 1</span></span></p></td>
<td><p><span data-ttu-id="3d9e4-210">Одновременный звонок разрешен</span><span class="sxs-lookup"><span data-stu-id="3d9e4-210">Simultaneous ring is allowed</span></span></p></td>
<td><p><span data-ttu-id="3d9e4-211">Одновременный звонок не разрешен</span><span class="sxs-lookup"><span data-stu-id="3d9e4-211">Simultaneous ring is not allowed</span></span></p></td>
<td><p><span data-ttu-id="3d9e4-212">Одновременный звонок не разрешен</span><span class="sxs-lookup"><span data-stu-id="3d9e4-212">Simultaneous ring is not allowed</span></span></p></td>
</tr>
</tbody>
</table>

  
<span data-ttu-id="3d9e4-213">В следующей таблице показано, поддерживает ли маршрутизацию Location-Based Одновременный звонок на конечную точку PSTN от разных пользователей Lync (например, Lync User 2, Lync User 4 и т. д.).</span><span class="sxs-lookup"><span data-stu-id="3d9e4-213">The following table illustrates whether Location-Based Routing allows simultaneous ringing to a PSTN endpoint from different Lync users (i.e. Lync user 2, Lync user 4, etc).</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3d9e4-214">Цель одновременных звонков</span><span class="sxs-lookup"><span data-stu-id="3d9e4-214">Simultaneous ring target</span></span></th>
<th><span data-ttu-id="3d9e4-215">Пользователь Lync 2</span><span class="sxs-lookup"><span data-stu-id="3d9e4-215">Lync user 2</span></span></th>
<th><span data-ttu-id="3d9e4-216">Пользователь Lync 4</span><span class="sxs-lookup"><span data-stu-id="3d9e4-216">Lync user 4</span></span></th>
<th><span data-ttu-id="3d9e4-217">Пользователь Lync на сетевом сайте не включен для маршрутизации Location-Based</span><span class="sxs-lookup"><span data-stu-id="3d9e4-217">Lync user in network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3d9e4-218">Мобильный телефон пользователя Lync 1 (конечная точка PSTN)</span><span class="sxs-lookup"><span data-stu-id="3d9e4-218">Lync user 1 mobile phone (PSTN endpoint)</span></span></p></td>
<td><p><span data-ttu-id="3d9e4-219">Вызов, направляемый через политику маршрутизации голосовой связи на сетевом сайте 1 и исходящий через шлюз сайта 1</span><span class="sxs-lookup"><span data-stu-id="3d9e4-219">Call routed through network site 1’s voice routing policy and egress via site 1 gateway</span></span></p></td>
<td><p><span data-ttu-id="3d9e4-220">Вызов, направляемый через политику маршрутизации голосовой связи на сетевом сайте 2 и исходящий через шлюз сайта 2</span><span class="sxs-lookup"><span data-stu-id="3d9e4-220">Call routed through network site 2’s voice routing policy and egress via site 2 gateway</span></span></p></td>
<td><p><span data-ttu-id="3d9e4-221">Вызов направляется через абонентскую политику голосовой связи и будет исходящий через шлюз PSTN, не включенный для маршрутизации Location-Based</span><span class="sxs-lookup"><span data-stu-id="3d9e4-221">Call routed through the caller voice policy and will egress via a PSTN gateway not enabled for Location-Based Routing</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3d9e4-222">См. также</span><span class="sxs-lookup"><span data-stu-id="3d9e4-222">See Also</span></span>


[<span data-ttu-id="3d9e4-223">Планирование маршрутизации Location-Based в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3d9e4-223">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

