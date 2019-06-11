---
title: 'Lync Server 2013: процесс развертывания функции маршрутизации на основе местоположения'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment process for Location-Based Routing
ms:assetid: 9e923e72-83fc-4a4f-8937-28a55739ed3e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994055(v=OCS.15)
ms:contentKeyID: 51803966
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 108dd35c7f184c974a317f68901c94bc81e9e403
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834476"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="ba1fe-102">Процесс развертывания функции маршрутизации на основе местоположения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ba1fe-102">Deployment process for Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ba1fe-103">_**Тема последнего изменения:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="ba1fe-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="ba1fe-104">В этом разделе приводятся общие сведения о процессе настройки маршрутизации на основе местоположения.</span><span class="sxs-lookup"><span data-stu-id="ba1fe-104">This topic provides an overview of the process involved in configuring Location-Based Routing.</span></span> <span data-ttu-id="ba1fe-105">Перед настройкой маршрутизации на основе местоположения необходимо развернуть Lync Server Enterprise Edition или Standard Edition с корпоративной голосовой связью.</span><span class="sxs-lookup"><span data-stu-id="ba1fe-105">You must deploy Lync Server Enterprise Edition or Standard Edition with Enterprise Voice before you configure Location-Based Routing.</span></span> <span data-ttu-id="ba1fe-106">Компоненты, необходимые для маршрутизации на основе местоположения, уже установлены и включены при развертывании корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="ba1fe-106">The components required by Location-Based Routing are already installed and enabled when you deploy Enterprise Voice.</span></span>

### <a name="location-based-routing-deployment-process"></a><span data-ttu-id="ba1fe-107">Процесс развертывания маршрутизации с учетом расположения</span><span class="sxs-lookup"><span data-stu-id="ba1fe-107">Location-Based Routing Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ba1fe-108">Этап</span><span class="sxs-lookup"><span data-stu-id="ba1fe-108">Phase</span></span></th>
<th><span data-ttu-id="ba1fe-109">Шаги</span><span class="sxs-lookup"><span data-stu-id="ba1fe-109">Steps</span></span></th>
<th><span data-ttu-id="ba1fe-110">Необходимые группы и роли</span><span class="sxs-lookup"><span data-stu-id="ba1fe-110">Required groups and roles</span></span></th>
<th><span data-ttu-id="ba1fe-111">Документация по развертыванию</span><span class="sxs-lookup"><span data-stu-id="ba1fe-111">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ba1fe-112">Развертывание корпоративной голосовой связи</span><span class="sxs-lookup"><span data-stu-id="ba1fe-112">Deploy Enterprise Voice</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="ba1fe-113">Настройка каналов</span><span class="sxs-lookup"><span data-stu-id="ba1fe-113">Configure Trunks</span></span></p></li>
<li><p><span data-ttu-id="ba1fe-114">Создание политик голосовой связи</span><span class="sxs-lookup"><span data-stu-id="ba1fe-114">Create Voice Policies</span></span></p></li>
<li><p><span data-ttu-id="ba1fe-115">Определение маршрутов голосовой связи</span><span class="sxs-lookup"><span data-stu-id="ba1fe-115">Define Voice Routes</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="ba1fe-116">Ксвоицеадминс</span><span class="sxs-lookup"><span data-stu-id="ba1fe-116">CSVoiceAdmins</span></span><br />
<span data-ttu-id="ba1fe-117">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="ba1fe-117">CsAdministrator</span></span><br />
<span data-ttu-id="ba1fe-118">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="ba1fe-118">CsServerAdministrator</span></span></p></td>
<td><p><span data-ttu-id="ba1fe-119">Развертывание корпоративной голосовой связи</span><span class="sxs-lookup"><span data-stu-id="ba1fe-119">Deploying Enterprise Voice</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba1fe-120">Проверка развертывания голосовой связи в корпоративной среде</span><span class="sxs-lookup"><span data-stu-id="ba1fe-120">Verify your Enterprise Voice deployment</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ba1fe-121">Ксвоицеадминс</span><span class="sxs-lookup"><span data-stu-id="ba1fe-121">CSVoiceAdmins</span></span><br />
<span data-ttu-id="ba1fe-122">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="ba1fe-122">CsAdministrator</span></span><br />
<span data-ttu-id="ba1fe-123">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="ba1fe-123">CsServerAdministrator</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba1fe-124">Настройка регионов, сайтов и подсетей сети</span><span class="sxs-lookup"><span data-stu-id="ba1fe-124">Configure network regions, sites, and subnets</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="ba1fe-125">Создание областей сети</span><span class="sxs-lookup"><span data-stu-id="ba1fe-125">Create network regions</span></span></p></li>
<li><p><span data-ttu-id="ba1fe-126">Создание сайтов сети</span><span class="sxs-lookup"><span data-stu-id="ba1fe-126">Create network sites</span></span></p></li>
<li><p><span data-ttu-id="ba1fe-127">Связывает подсети с сетевыми сайтами</span><span class="sxs-lookup"><span data-stu-id="ba1fe-127">Associates subnets with network sites</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="ba1fe-128">Ксвоицеадминс</span><span class="sxs-lookup"><span data-stu-id="ba1fe-128">CSVoiceAdmins</span></span><br />
<span data-ttu-id="ba1fe-129">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="ba1fe-129">CsAdministrator</span></span><br />
<span data-ttu-id="ba1fe-130">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="ba1fe-130">CsServerAdministrator</span></span></p></td>
<td><p><span data-ttu-id="ba1fe-131">Сетевые регионы, сайты и подсети</span><span class="sxs-lookup"><span data-stu-id="ba1fe-131">About Network Regions, Sites, and Subnets</span></span><br />
<span data-ttu-id="ba1fe-132">Создание и изменение сетевого региона</span><span class="sxs-lookup"><span data-stu-id="ba1fe-132">Create or Modify a Network Region</span></span><br />
<span data-ttu-id="ba1fe-133">Создание или изменение сетевого сайта</span><span class="sxs-lookup"><span data-stu-id="ba1fe-133">Create or Modify a Network Site</span></span><br />
<span data-ttu-id="ba1fe-134">Связывание подсети с сетевым сайтом</span><span class="sxs-lookup"><span data-stu-id="ba1fe-134">Associate a Subnet with a Network Site</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba1fe-135">Настройка маршрутизации на основе местоположения</span><span class="sxs-lookup"><span data-stu-id="ba1fe-135">Configure Location-Based Routing</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="ba1fe-136">Создание политик голосовой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="ba1fe-136">Create voice routing policies</span></span></p></li>
<li><p><span data-ttu-id="ba1fe-137">Определение отдельной конфигурации магистрали для каждой магистрали</span><span class="sxs-lookup"><span data-stu-id="ba1fe-137">Define separate trunk configuration per trunk</span></span></p></li>
<li><p><span data-ttu-id="ba1fe-138">Изменение политик голосовой связи</span><span class="sxs-lookup"><span data-stu-id="ba1fe-138">Modify voice policies</span></span></p></li>
<li><p><span data-ttu-id="ba1fe-139">Включение настройки маршрутизации на основе местоположения</span><span class="sxs-lookup"><span data-stu-id="ba1fe-139">Enable Location-Based Routing configuration</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="ba1fe-140">Ксвоицеадминс</span><span class="sxs-lookup"><span data-stu-id="ba1fe-140">CSVoiceAdmins</span></span><br />
<span data-ttu-id="ba1fe-141">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="ba1fe-141">CsAdministrator</span></span><br />
<span data-ttu-id="ba1fe-142">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="ba1fe-142">CsServerAdministrator</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>

## <a name="sample-deployment"></a><span data-ttu-id="ba1fe-143">Пример развертывания</span><span class="sxs-lookup"><span data-stu-id="ba1fe-143">Sample Deployment</span></span>

<span data-ttu-id="ba1fe-144">Для иллюстрации дальнейших механизмов, включенных с помощью маршрутизации на основе расположения, используется следующее развертывание.</span><span class="sxs-lookup"><span data-stu-id="ba1fe-144">The following deployment is used to illustrate further the mechanisms enabled by Location-Based Routing.</span></span>

<span data-ttu-id="ba1fe-145">![e1bd2230-44da-4784-b359-24572b6ce02d] (images/JJ994055.e1bd2230-44da-4784-b359-24572b6ce02d(OCS.15).png "e1bd2230-44da-4784-b359-24572b6ce02d")</span><span class="sxs-lookup"><span data-stu-id="ba1fe-145">![e1bd2230-44da-4784-b359-24572b6ce02d](images/JJ994055.e1bd2230-44da-4784-b359-24572b6ce02d(OCS.15).png "e1bd2230-44da-4784-b359-24572b6ce02d")</span></span>

<div>

## <a name="incoming-pstn-calls"></a><span data-ttu-id="ba1fe-146">Входящие звонки PSTN</span><span class="sxs-lookup"><span data-stu-id="ba1fe-146">Incoming PSTN calls</span></span>

<span data-ttu-id="ba1fe-147">Администратор может включить магистраль, вызываемый для маршрутизации звонков на шлюз сайта 1, и связать его с узлом 1, используя шлюз "сайт 1".</span><span class="sxs-lookup"><span data-stu-id="ba1fe-147">An administrator can enable the trunk defined to route calls to “Site 1 Gateway” for Location-Based Routing and associate the “Site 1 Gateway” to site 1.</span></span> <span data-ttu-id="ba1fe-148">После того как вы включите этот флажок, звонки, направляемые через шлюз "сайт 1", будут перенаправляться только тем пользователям, которые находятся на сайте 1.</span><span class="sxs-lookup"><span data-stu-id="ba1fe-148">Once enabled, calls that are routed through “Site 1 Gateway“ will only be routed to users that are located in site 1.</span></span> <span data-ttu-id="ba1fe-149">Все звонки, находящиеся на магистральном шлюзе "сайт 1", предназначенные для пользователей на другом сайте, например "сайт 2", будут заблокированы для предотвращения бесплатных звонков по сети PSTN.</span><span class="sxs-lookup"><span data-stu-id="ba1fe-149">All calls routed through the “Site 1 Gateway” trunk destined to users in a different site, such as site 2 will be blocked to prevent PSTN toll bypass.</span></span>

<span data-ttu-id="ba1fe-150">Все входящие звонки по коммутируемой телефонной связи через шлюз сайта 1 будут разрешены только для маршрутизации конечных точек, расположенных на сайте 1.</span><span class="sxs-lookup"><span data-stu-id="ba1fe-150">All incoming PSTN calls through “Site 1 Gateway” will only be allowed to route to endpoints located in site 1.</span></span> <span data-ttu-id="ba1fe-151">Например, когда "Lync User 1" перемещается на сайт 2, все входящие звонки PSTN через шлюз сайта 1 не будут перенаправлены в конечные точки "Lync User 1", расположенные на сайте 2.</span><span class="sxs-lookup"><span data-stu-id="ba1fe-151">For example, when “Lync user 1” travels to site 2, all incoming PSTN calls through “Site 1 Gateway” will not be routed to “Lync user 1” endpoints located in site 2.</span></span> <span data-ttu-id="ba1fe-152">Одно и то же правило маршрутизации применимо, если "пользователь Lync 1" перемещается на неизвестный сетевой сайт, на котором невозможно определить расположение пользователя.</span><span class="sxs-lookup"><span data-stu-id="ba1fe-152">The same routing rule applies if “Lync user 1” travels to an unknown network site where the user’s location can’t be determined.</span></span>

<span data-ttu-id="ba1fe-153">В таблице ниже приведено краткое руководство по работе пользователей Lync User 1 в этом контексте.</span><span class="sxs-lookup"><span data-stu-id="ba1fe-153">The following table outlines the user experience of “Lync user 1” in this context.</span></span>


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
<th><span data-ttu-id="ba1fe-154">Конечные точки пользователей Lync 1, размещенные на сетевом сайте 1</span><span class="sxs-lookup"><span data-stu-id="ba1fe-154">Lync user 1 endpoints located in network site 1</span></span></th>
<th><span data-ttu-id="ba1fe-155">Конечные точки пользователей Lync 1, расположенные на сайте сети 2</span><span class="sxs-lookup"><span data-stu-id="ba1fe-155">Lync user 1 endpoints located in network site 2</span></span></th>
<th><span data-ttu-id="ba1fe-156">Конечные точки пользователей Lync 1, расположенные на неизвестном сетевом сайте</span><span class="sxs-lookup"><span data-stu-id="ba1fe-156">Lync user 1 endpoints located in unknown network site</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ba1fe-157">Входящие звонки PSTN в Lync User 1</span><span class="sxs-lookup"><span data-stu-id="ba1fe-157">Inbound PSTN calls to Lync user 1</span></span></p></td>
<td><p><span data-ttu-id="ba1fe-158">Звонки направляются в конечные точки в этом расположении</span><span class="sxs-lookup"><span data-stu-id="ba1fe-158">Calls are routed to endpoints in this location</span></span></p></td>
<td><p><span data-ttu-id="ba1fe-159">Звонки не передаются в конечные точки в этом расположении</span><span class="sxs-lookup"><span data-stu-id="ba1fe-159">Calls are not routed to endpoints in this location</span></span></p></td>
<td><p><span data-ttu-id="ba1fe-160">Звонки не передаются в конечные точки в этом расположении</span><span class="sxs-lookup"><span data-stu-id="ba1fe-160">Calls are not routed to endpoints in this location</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="outgoing-pstn-calls"></a><span data-ttu-id="ba1fe-161">Исходящие звонки PSTN</span><span class="sxs-lookup"><span data-stu-id="ba1fe-161">Outgoing PSTN calls</span></span>

<span data-ttu-id="ba1fe-162">На голосовые маршруты указываются и политики голосовой связи, назначенные пользователям, и политики маршрутизации голосовой связи, назначенные сетевым сайтам.</span><span class="sxs-lookup"><span data-stu-id="ba1fe-162">Voice routes are referenced in both Voice Policies assigned directly to users, and Voice Routing Policies assigned to network sites.</span></span> <span data-ttu-id="ba1fe-163">Обе политики содержат ссылки на маршруты, которые можно использовать для того, чтобы направлять звонок другим образом.</span><span class="sxs-lookup"><span data-stu-id="ba1fe-163">Both policies contain references to routes, which can be used to route a call differently.</span></span> <span data-ttu-id="ba1fe-164">Например, администратор может настроить политику маршрутизации голосовой связи для всех пользователей, расположенных на сайте сети 1, для маршрутизации всех исходящих вызовов через шлюз сайта 1, в то время как политика голосовой связи для некоторых пользователей определяет маршрут для всех исходящих звонков с помощью шлюза сайта 2.</span><span class="sxs-lookup"><span data-stu-id="ba1fe-164">For example, an administrator can define a Voice Routing Policy for all users located in network site 1 to route all outbound calls through the “Site 1 Gateway” while the Voice Policy of some users define a route for all outbound calls through the “Site 2 Gateway”.</span></span> <span data-ttu-id="ba1fe-165">Несмотря на то что эти пользователи находятся в сетевом сайте 1, исходящие звонки будут маршрутизироваться через шлюз сайта 1.</span><span class="sxs-lookup"><span data-stu-id="ba1fe-165">While these users are located in network site 1, their outbound calls will be routed through the “Site 1 Gateway”.</span></span>

<span data-ttu-id="ba1fe-166">Когда пользователь находится на сетевом сайте, настроенном для маршрутизации на основе местоположения, маршрут политики голосовой маршрутизации на сетевом сайте переопределяет маршрут политики голосовой связи пользователя.</span><span class="sxs-lookup"><span data-stu-id="ba1fe-166">When a user is located in a network site configured for Location-Based Routing, the network site’s Voice Routing Policy route overrides the user’s Voice Policy route.</span></span> <span data-ttu-id="ba1fe-167">Это правило особенно удобно для пользователей, которые временно перемещаются на другой сайт.</span><span class="sxs-lookup"><span data-stu-id="ba1fe-167">This rule is particularly useful for users that temporarily move to a different site.</span></span> <span data-ttu-id="ba1fe-168">В этом конкретном случае пользователь всегда будет использовать локальный шлюз для своего местоположения; Если "Lync User 3" находится на сайте 2, все его исходящие звонки будут маршрутизироваться через шлюз сайта 2, но если он перейдет на сайт 1, все входящие звонки, помещенные на сайт 1, будут маршрутизироваться через шлюз "сайт 1".</span><span class="sxs-lookup"><span data-stu-id="ba1fe-168">In this particular case a user will always use a gateway that is local to his location; if “Lync user 3” is located at “Site 2”, all his outbound calls will be routed via “Site 2 Gateway”, but if he travels to site 1, all his outbound calls placed while he’s at site 1 will be routed through “Site 1 Gateway”.</span></span>

<span data-ttu-id="ba1fe-169">В таблице ниже показано, как пользователь Lync 1 помещает исходящий звонок на следующие сайты сети.</span><span class="sxs-lookup"><span data-stu-id="ba1fe-169">The following table illustrates the user experience of Lync user 1 placing an outbound call from the following network sites.</span></span>


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
<th><span data-ttu-id="ba1fe-170">Сетевой сайт 1</span><span class="sxs-lookup"><span data-stu-id="ba1fe-170">Network site 1</span></span></th>
<th><span data-ttu-id="ba1fe-171">Сетевой сайт 2</span><span class="sxs-lookup"><span data-stu-id="ba1fe-171">Network site 2</span></span></th>
<th><span data-ttu-id="ba1fe-172">"Неизвестный сетевой сайт" или "не включена" для маршрутизации с учетом расположения</span><span class="sxs-lookup"><span data-stu-id="ba1fe-172">Unknown network site or not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ba1fe-173">Авторизация исходящих звонков</span><span class="sxs-lookup"><span data-stu-id="ba1fe-173">Authorization of outbound calls</span></span></p></td>
<td><p><span data-ttu-id="ba1fe-174">Политика голосовой связи пользователя Lync 1</span><span class="sxs-lookup"><span data-stu-id="ba1fe-174">Lync user 1 voice policy</span></span></p></td>
<td><p><span data-ttu-id="ba1fe-175">Политика голосовой связи пользователя Lync 1</span><span class="sxs-lookup"><span data-stu-id="ba1fe-175">Lync user 1 voice policy</span></span></p></td>
<td><p><span data-ttu-id="ba1fe-176">Политика голосовой связи пользователя Lync 1</span><span class="sxs-lookup"><span data-stu-id="ba1fe-176">Lync user 1 voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba1fe-177">Маршрутизация исходящих звонков</span><span class="sxs-lookup"><span data-stu-id="ba1fe-177">Routing of outbound calls</span></span></p></td>
<td><p><span data-ttu-id="ba1fe-178">Политика маршрутизации голосовой связи для сайта 1</span><span class="sxs-lookup"><span data-stu-id="ba1fe-178">Site 1 voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="ba1fe-179">Политика маршрутизации голосовой связи на сайте 2</span><span class="sxs-lookup"><span data-stu-id="ba1fe-179">Site 2 voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="ba1fe-180">Голосовая политика пользователя и только системы, для которых не включена маршрутизация на основе местоположения.</span><span class="sxs-lookup"><span data-stu-id="ba1fe-180">User’s voice policy and only to systems not enabled for Location-Based Routing</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="call-transfers-and-forwards"></a><span data-ttu-id="ba1fe-181">Передача и переадресация звонков</span><span class="sxs-lookup"><span data-stu-id="ba1fe-181">Call transfers and forwards</span></span>

<span data-ttu-id="ba1fe-182">При передаче или пересылке звонков на них влияет маршрутизация на основе местоположения.</span><span class="sxs-lookup"><span data-stu-id="ba1fe-182">When calls are transferred or forwarded, the routing of calls is affected by Location-Based Routing.</span></span>

<span data-ttu-id="ba1fe-183">В приведенной ниже таблице показано, как пользователь Lync 1 передает или перенаправляет Звонок на другой пользователь Lync.</span><span class="sxs-lookup"><span data-stu-id="ba1fe-183">The following table depicts Lync user 1 transferring or forwarding a PSTN call to another Lync user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ba1fe-184">Передача или пересылка звонка пользователем</span><span class="sxs-lookup"><span data-stu-id="ba1fe-184">User initiating call transfer or forward</span></span></th>
<th><span data-ttu-id="ba1fe-185">Пользователь Lync 2</span><span class="sxs-lookup"><span data-stu-id="ba1fe-185">Lync user 2</span></span></th>
<th><span data-ttu-id="ba1fe-186">Пользователь Lync 4</span><span class="sxs-lookup"><span data-stu-id="ba1fe-186">Lync user 4</span></span></th>
<th><span data-ttu-id="ba1fe-187">Пользователь Lync на сайте сети не включен для маршрутизации с учетом расположения</span><span class="sxs-lookup"><span data-stu-id="ba1fe-187">Lync user in network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ba1fe-188">Пользователь Lync 1</span><span class="sxs-lookup"><span data-stu-id="ba1fe-188">Lync user 1</span></span></p></td>
<td><p><span data-ttu-id="ba1fe-189">Переключение или переадресация звонка разрешены</span><span class="sxs-lookup"><span data-stu-id="ba1fe-189">Call forward or transfer is allowed</span></span></p></td>
<td><p><span data-ttu-id="ba1fe-190">Переключение или переадресация звонка не разрешены</span><span class="sxs-lookup"><span data-stu-id="ba1fe-190">Call forward or transfer is not allowed</span></span></p></td>
<td><p><span data-ttu-id="ba1fe-191">Переключение или переадресация звонка не разрешены</span><span class="sxs-lookup"><span data-stu-id="ba1fe-191">Call forward or transfer is not allowed</span></span></p></td>
</tr>
</tbody>
</table>

  
<span data-ttu-id="ba1fe-192">В следующей таблице показано, как маршрутизация на основе местоположения влияет на способ маршрутизации звонка в зависимости от расположения передаваемого пользователя Lync (Lync User 2, Lync User 4 и т. д.) в конечную точку PSTN.</span><span class="sxs-lookup"><span data-stu-id="ba1fe-192">The following table illustrates how Location-Based Routing affects how the call is routed based on the location of the Lync user being transferred (Lync user 2, Lync user 4, etc) to a PSTN endpoint</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ba1fe-193">Конечная точка, в которую передается или пересылается Звонок</span><span class="sxs-lookup"><span data-stu-id="ba1fe-193">Endpoint where call is transferred or forwarded to</span></span></th>
<th><span data-ttu-id="ba1fe-194">Пользователь Lync 2</span><span class="sxs-lookup"><span data-stu-id="ba1fe-194">Lync user 2</span></span></th>
<th><span data-ttu-id="ba1fe-195">Пользователь Lync 4</span><span class="sxs-lookup"><span data-stu-id="ba1fe-195">Lync user 4</span></span></th>
<th><span data-ttu-id="ba1fe-196">Пользователь Lync на сайте сети не включен для маршрутизации с учетом расположения</span><span class="sxs-lookup"><span data-stu-id="ba1fe-196">Lync user in network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ba1fe-197">Конечная точка ТСОП</span><span class="sxs-lookup"><span data-stu-id="ba1fe-197">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="ba1fe-198">Переадресация и пересылка звонков осуществляется с помощью политики маршрутизации голосовой связи сайта 1 и выхода через шлюз сайта 1</span><span class="sxs-lookup"><span data-stu-id="ba1fe-198">Call forward or transfer is routed through site 1 voice routing policy and egress via Site 1 Gateway</span></span></p></td>
<td><p><span data-ttu-id="ba1fe-199">Переадресация и пересылка звонков осуществляется с помощью политики маршрутизации голосовой связи сайта 2 и выхода через шлюз сайта 2</span><span class="sxs-lookup"><span data-stu-id="ba1fe-199">Call forward or transfer is routed through site 2 voice routing policy and egress via Site 2 Gateway</span></span></p></td>
<td><p><span data-ttu-id="ba1fe-200">Переадресация звонков или передача данных осуществляется посредством политики голосовой связи пользователя Lync и выхода через шлюз, не включенный для маршрутизации на основе местоположения (если она доступна).</span><span class="sxs-lookup"><span data-stu-id="ba1fe-200">Call forward or transfer is routed through the Lync user voice policy and egress via a gateway not enabled for location-based routing (if available)</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="simultaneous-ringing"></a><span data-ttu-id="ba1fe-201">Одновременный звонок</span><span class="sxs-lookup"><span data-stu-id="ba1fe-201">Simultaneous ringing</span></span>

<span data-ttu-id="ba1fe-202">После настройки маршрутизации на основе местоположения в образце топологии применяются следующие взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="ba1fe-202">Once location-based routing is configured in the sample topology, the following interactions are enforced.</span></span>

<span data-ttu-id="ba1fe-203">В следующей таблице показано, позволяет ли маршрутизация на основе местоположения допускает Одновременный звонок для разных пользователей Lync (например, пользователи Lync 2, Lync User и т. д.).</span><span class="sxs-lookup"><span data-stu-id="ba1fe-203">The following table illustrates whether Location-Based Routing allows simultaneous ringing for different Lync users (i.e. Lync user 2, Lync user 4, etc).</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ba1fe-204">Нацеливание на входящий звонок по КОММУТИРУЕМой сети</span><span class="sxs-lookup"><span data-stu-id="ba1fe-204">Incoming PSTN call target</span></span></th>
<th><span data-ttu-id="ba1fe-205">Пользователь Lync 2</span><span class="sxs-lookup"><span data-stu-id="ba1fe-205">Lync user 2</span></span></th>
<th><span data-ttu-id="ba1fe-206">Пользователь Lync 4</span><span class="sxs-lookup"><span data-stu-id="ba1fe-206">Lync user 4</span></span></th>
<th><span data-ttu-id="ba1fe-207">Пользователь Lync на сайте сети не включен для маршрутизации с учетом расположения</span><span class="sxs-lookup"><span data-stu-id="ba1fe-207">Lync user in network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ba1fe-208">Пользователь Lync 1</span><span class="sxs-lookup"><span data-stu-id="ba1fe-208">Lync user 1</span></span></p></td>
<td><p><span data-ttu-id="ba1fe-209">Одновременный звонок разрешен</span><span class="sxs-lookup"><span data-stu-id="ba1fe-209">Simultaneous ring is allowed</span></span></p></td>
<td><p><span data-ttu-id="ba1fe-210">Одновременный звонок не разрешен</span><span class="sxs-lookup"><span data-stu-id="ba1fe-210">Simultaneous ring is not allowed</span></span></p></td>
<td><p><span data-ttu-id="ba1fe-211">Одновременный звонок не разрешен</span><span class="sxs-lookup"><span data-stu-id="ba1fe-211">Simultaneous ring is not allowed</span></span></p></td>
</tr>
</tbody>
</table>

  
<span data-ttu-id="ba1fe-212">В следующей таблице показано, разрешено ли маршрутизация на основе местоположения для одновременных звонков в конечную точку PSTN из различных пользователей Lync (например, Lync User 2, Lync User и т. д.).</span><span class="sxs-lookup"><span data-stu-id="ba1fe-212">The following table illustrates whether Location-Based Routing allows simultaneous ringing to a PSTN endpoint from different Lync users (i.e. Lync user 2, Lync user 4, etc).</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ba1fe-213">Цель одновременного вызова</span><span class="sxs-lookup"><span data-stu-id="ba1fe-213">Simultaneous ring target</span></span></th>
<th><span data-ttu-id="ba1fe-214">Пользователь Lync 2</span><span class="sxs-lookup"><span data-stu-id="ba1fe-214">Lync user 2</span></span></th>
<th><span data-ttu-id="ba1fe-215">Пользователь Lync 4</span><span class="sxs-lookup"><span data-stu-id="ba1fe-215">Lync user 4</span></span></th>
<th><span data-ttu-id="ba1fe-216">Пользователь Lync на сайте сети не включен для маршрутизации с учетом расположения</span><span class="sxs-lookup"><span data-stu-id="ba1fe-216">Lync user in network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ba1fe-217">Мобильный телефон пользователя Lync 1 (конечная точка PSTN)</span><span class="sxs-lookup"><span data-stu-id="ba1fe-217">Lync user 1 mobile phone (PSTN endpoint)</span></span></p></td>
<td><p><span data-ttu-id="ba1fe-218">Вызов, направляемый по политике голосовой маршрутизации на сетевом сайте 1 и выходному каналу через шлюз сайта 1</span><span class="sxs-lookup"><span data-stu-id="ba1fe-218">Call routed through network site 1’s voice routing policy and egress via site 1 gateway</span></span></p></td>
<td><p><span data-ttu-id="ba1fe-219">Вызов, направляемый по политике голосовой маршрутизации на сетевом сайте 2 и выходному каналу через шлюз сайта 2</span><span class="sxs-lookup"><span data-stu-id="ba1fe-219">Call routed through network site 2’s voice routing policy and egress via site 2 gateway</span></span></p></td>
<td><p><span data-ttu-id="ba1fe-220">Вызов, направляемый через голосовую политику вызывающего абонента, будет исключаться через шлюз PSTN, не включенный для маршрутизации на основе местоположения</span><span class="sxs-lookup"><span data-stu-id="ba1fe-220">Call routed through the caller voice policy and will egress via a PSTN gateway not enabled for Location-Based Routing</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ba1fe-221">См. также</span><span class="sxs-lookup"><span data-stu-id="ba1fe-221">See Also</span></span>


[<span data-ttu-id="ba1fe-222">Планирование маршрутизации на основе местоположения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ba1fe-222">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

