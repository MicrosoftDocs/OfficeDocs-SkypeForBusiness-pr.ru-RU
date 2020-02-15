---
title: 'Lync Server 2013: процесс развертывания для маршрутизации на основе расположения'
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
ms.openlocfilehash: 93b26498593038231be527c98e62ee1f13865df1
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035181"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="9c71b-102">Процесс развертывания для маршрутизации на основе расположения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9c71b-102">Deployment process for Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9c71b-103">_**Последнее изменение темы:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="9c71b-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="9c71b-104">В этом разделе приведены общие сведения о процессе настройки маршрутизации на основе расположения.</span><span class="sxs-lookup"><span data-stu-id="9c71b-104">This topic provides an overview of the process involved in configuring Location-Based Routing.</span></span> <span data-ttu-id="9c71b-105">Перед настройкой маршрутизации на основе расположения необходимо развернуть Lync Server Enterprise Edition или Standard Edition с корпоративной голосовой связью.</span><span class="sxs-lookup"><span data-stu-id="9c71b-105">You must deploy Lync Server Enterprise Edition or Standard Edition with Enterprise Voice before you configure Location-Based Routing.</span></span> <span data-ttu-id="9c71b-106">Компоненты, необходимые для маршрутизации на основе расположения, уже установлены и включены при развертывании корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="9c71b-106">The components required by Location-Based Routing are already installed and enabled when you deploy Enterprise Voice.</span></span>

### <a name="location-based-routing-deployment-process"></a><span data-ttu-id="9c71b-107">Процесс развертывания маршрутизации на основе расположения</span><span class="sxs-lookup"><span data-stu-id="9c71b-107">Location-Based Routing Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9c71b-108">Этап</span><span class="sxs-lookup"><span data-stu-id="9c71b-108">Phase</span></span></th>
<th><span data-ttu-id="9c71b-109">Шаги</span><span class="sxs-lookup"><span data-stu-id="9c71b-109">Steps</span></span></th>
<th><span data-ttu-id="9c71b-110">Необходимые группы и роли</span><span class="sxs-lookup"><span data-stu-id="9c71b-110">Required groups and roles</span></span></th>
<th><span data-ttu-id="9c71b-111">Документация по развертыванию</span><span class="sxs-lookup"><span data-stu-id="9c71b-111">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9c71b-112">Развертывание корпоративной голосовой связи</span><span class="sxs-lookup"><span data-stu-id="9c71b-112">Deploy Enterprise Voice</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="9c71b-113">Настройка магистральных линий связи</span><span class="sxs-lookup"><span data-stu-id="9c71b-113">Configure Trunks</span></span></p></li>
<li><p><span data-ttu-id="9c71b-114">Создание политик голосовой связи</span><span class="sxs-lookup"><span data-stu-id="9c71b-114">Create Voice Policies</span></span></p></li>
<li><p><span data-ttu-id="9c71b-115">Определение маршрутов голосовой связи</span><span class="sxs-lookup"><span data-stu-id="9c71b-115">Define Voice Routes</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="9c71b-116">ксвоицеадминс</span><span class="sxs-lookup"><span data-stu-id="9c71b-116">CSVoiceAdmins</span></span><br />
<span data-ttu-id="9c71b-117">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="9c71b-117">CsAdministrator</span></span><br />
<span data-ttu-id="9c71b-118">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="9c71b-118">CsServerAdministrator</span></span></p></td>
<td><p><span data-ttu-id="9c71b-119">Развертывание корпоративной голосовой связи</span><span class="sxs-lookup"><span data-stu-id="9c71b-119">Deploying Enterprise Voice</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c71b-120">Проверка развертывания корпоративной голосовой связи</span><span class="sxs-lookup"><span data-stu-id="9c71b-120">Verify your Enterprise Voice deployment</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9c71b-121">ксвоицеадминс</span><span class="sxs-lookup"><span data-stu-id="9c71b-121">CSVoiceAdmins</span></span><br />
<span data-ttu-id="9c71b-122">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="9c71b-122">CsAdministrator</span></span><br />
<span data-ttu-id="9c71b-123">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="9c71b-123">CsServerAdministrator</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9c71b-124">Настройка областей сети, сайтов и подсетей</span><span class="sxs-lookup"><span data-stu-id="9c71b-124">Configure network regions, sites, and subnets</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="9c71b-125">Создание областей сети</span><span class="sxs-lookup"><span data-stu-id="9c71b-125">Create network regions</span></span></p></li>
<li><p><span data-ttu-id="9c71b-126">Создание сетевых сайтов</span><span class="sxs-lookup"><span data-stu-id="9c71b-126">Create network sites</span></span></p></li>
<li><p><span data-ttu-id="9c71b-127">Связывает подсети с сетевыми сайтами</span><span class="sxs-lookup"><span data-stu-id="9c71b-127">Associates subnets with network sites</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="9c71b-128">ксвоицеадминс</span><span class="sxs-lookup"><span data-stu-id="9c71b-128">CSVoiceAdmins</span></span><br />
<span data-ttu-id="9c71b-129">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="9c71b-129">CsAdministrator</span></span><br />
<span data-ttu-id="9c71b-130">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="9c71b-130">CsServerAdministrator</span></span></p></td>
<td><p><span data-ttu-id="9c71b-131">О сетевых областях, сайтах и подсетях</span><span class="sxs-lookup"><span data-stu-id="9c71b-131">About Network Regions, Sites, and Subnets</span></span><br />
<span data-ttu-id="9c71b-132">Создание или изменение сетевой области</span><span class="sxs-lookup"><span data-stu-id="9c71b-132">Create or Modify a Network Region</span></span><br />
<span data-ttu-id="9c71b-133">Создание или изменение сетевого сайта</span><span class="sxs-lookup"><span data-stu-id="9c71b-133">Create or Modify a Network Site</span></span><br />
<span data-ttu-id="9c71b-134">Связь подсети с сетевым сайтом</span><span class="sxs-lookup"><span data-stu-id="9c71b-134">Associate a Subnet with a Network Site</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c71b-135">Настройка маршрутизации на основе расположения</span><span class="sxs-lookup"><span data-stu-id="9c71b-135">Configure Location-Based Routing</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="9c71b-136">Создание политик маршрутизации голосовых вызовов</span><span class="sxs-lookup"><span data-stu-id="9c71b-136">Create voice routing policies</span></span></p></li>
<li><p><span data-ttu-id="9c71b-137">Определение отдельной конфигурации магистрали для каждой магистрали</span><span class="sxs-lookup"><span data-stu-id="9c71b-137">Define separate trunk configuration per trunk</span></span></p></li>
<li><p><span data-ttu-id="9c71b-138">Изменение политик голосовой связи</span><span class="sxs-lookup"><span data-stu-id="9c71b-138">Modify voice policies</span></span></p></li>
<li><p><span data-ttu-id="9c71b-139">Включение настройки маршрутизации на основе расположения</span><span class="sxs-lookup"><span data-stu-id="9c71b-139">Enable Location-Based Routing configuration</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="9c71b-140">ксвоицеадминс</span><span class="sxs-lookup"><span data-stu-id="9c71b-140">CSVoiceAdmins</span></span><br />
<span data-ttu-id="9c71b-141">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="9c71b-141">CsAdministrator</span></span><br />
<span data-ttu-id="9c71b-142">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="9c71b-142">CsServerAdministrator</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>

## <a name="sample-deployment"></a><span data-ttu-id="9c71b-143">Пример развертывания</span><span class="sxs-lookup"><span data-stu-id="9c71b-143">Sample Deployment</span></span>

<span data-ttu-id="9c71b-144">Для дальнейшего использования механизмов, включенных службой маршрутизации на основе расположения, используется следующее развертывание.</span><span class="sxs-lookup"><span data-stu-id="9c71b-144">The following deployment is used to illustrate further the mechanisms enabled by Location-Based Routing.</span></span>

<span data-ttu-id="9c71b-145">![e1bd2230 — 44da – 4784 — b359 – 24572b6ce02d](images/JJ994055.e1bd2230-44da-4784-b359-24572b6ce02d(OCS.15).png "e1bd2230 — 44da – 4784 — b359 – 24572b6ce02d")</span><span class="sxs-lookup"><span data-stu-id="9c71b-145">![e1bd2230-44da-4784-b359-24572b6ce02d](images/JJ994055.e1bd2230-44da-4784-b359-24572b6ce02d(OCS.15).png "e1bd2230-44da-4784-b359-24572b6ce02d")</span></span>

<div>

## <a name="incoming-pstn-calls"></a><span data-ttu-id="9c71b-146">Входящие звонки PSTN</span><span class="sxs-lookup"><span data-stu-id="9c71b-146">Incoming PSTN calls</span></span>

<span data-ttu-id="9c71b-147">Администратор может включить магистраль, заданный для маршрутизации вызовов на шлюз "сайт 1" для маршрутизации на основе расположения, и связать шлюз "сайт 1" с сайтом 1.</span><span class="sxs-lookup"><span data-stu-id="9c71b-147">An administrator can enable the trunk defined to route calls to “Site 1 Gateway” for Location-Based Routing and associate the “Site 1 Gateway” to site 1.</span></span> <span data-ttu-id="9c71b-148">После включения вызовы, направляемые через шлюз "сайт 1", будут перенаправляться только пользователям, расположенным на сайте 1.</span><span class="sxs-lookup"><span data-stu-id="9c71b-148">Once enabled, calls that are routed through “Site 1 Gateway“ will only be routed to users that are located in site 1.</span></span> <span data-ttu-id="9c71b-149">Все вызовы, направляемые через магистраль "шлюз сайта 1", предназначенные для пользователей на другом сайте, такие как сайт 2, будут заблокированы для предотвращения бесплатных звонков по сети PSTN.</span><span class="sxs-lookup"><span data-stu-id="9c71b-149">All calls routed through the “Site 1 Gateway” trunk destined to users in a different site, such as site 2 will be blocked to prevent PSTN toll bypass.</span></span>

<span data-ttu-id="9c71b-150">Все входящие звонки PSTN через шлюз "сайт 1" могут маршрутизироваться только к конечным точкам, расположенным на сайте 1.</span><span class="sxs-lookup"><span data-stu-id="9c71b-150">All incoming PSTN calls through “Site 1 Gateway” will only be allowed to route to endpoints located in site 1.</span></span> <span data-ttu-id="9c71b-151">Например, когда "Lync User 1" перемещается на сайт 2, все входящие вызовы PSTN через шлюз "сайт 1" не будут маршрутизироваться в конечные точки "Lync User 1", расположенные на сайте 2.</span><span class="sxs-lookup"><span data-stu-id="9c71b-151">For example, when “Lync user 1” travels to site 2, all incoming PSTN calls through “Site 1 Gateway” will not be routed to “Lync user 1” endpoints located in site 2.</span></span> <span data-ttu-id="9c71b-152">То же правило маршрутизации применяется, если сообщение "Lync User 1" перемещается на неизвестный сетевой сайт, на котором невозможно определить расположение пользователя.</span><span class="sxs-lookup"><span data-stu-id="9c71b-152">The same routing rule applies if “Lync user 1” travels to an unknown network site where the user’s location can’t be determined.</span></span>

<span data-ttu-id="9c71b-153">В следующей таблице показано взаимодействие с пользователем Lync User 1 в этом контексте.</span><span class="sxs-lookup"><span data-stu-id="9c71b-153">The following table outlines the user experience of “Lync user 1” in this context.</span></span>


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
<th><span data-ttu-id="9c71b-154">Конечные точки пользователя Lync 1, расположенные на сетевом сайте 1</span><span class="sxs-lookup"><span data-stu-id="9c71b-154">Lync user 1 endpoints located in network site 1</span></span></th>
<th><span data-ttu-id="9c71b-155">Конечные точки пользователя Lync 1, расположенные на сетевом сайте 2</span><span class="sxs-lookup"><span data-stu-id="9c71b-155">Lync user 1 endpoints located in network site 2</span></span></th>
<th><span data-ttu-id="9c71b-156">Конечные точки пользователя Lync 1 расположены на неизвестном сетевом сайте</span><span class="sxs-lookup"><span data-stu-id="9c71b-156">Lync user 1 endpoints located in unknown network site</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9c71b-157">Входящие вызовы PSTN для пользователя Lync 1</span><span class="sxs-lookup"><span data-stu-id="9c71b-157">Inbound PSTN calls to Lync user 1</span></span></p></td>
<td><p><span data-ttu-id="9c71b-158">Звонки направляются на конечные точки в этом расположении</span><span class="sxs-lookup"><span data-stu-id="9c71b-158">Calls are routed to endpoints in this location</span></span></p></td>
<td><p><span data-ttu-id="9c71b-159">Звонки не направляются на конечные точки в этом расположении</span><span class="sxs-lookup"><span data-stu-id="9c71b-159">Calls are not routed to endpoints in this location</span></span></p></td>
<td><p><span data-ttu-id="9c71b-160">Звонки не направляются на конечные точки в этом расположении</span><span class="sxs-lookup"><span data-stu-id="9c71b-160">Calls are not routed to endpoints in this location</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="outgoing-pstn-calls"></a><span data-ttu-id="9c71b-161">Исходящие вызовы PSTN</span><span class="sxs-lookup"><span data-stu-id="9c71b-161">Outgoing PSTN calls</span></span>

<span data-ttu-id="9c71b-162">Маршруты голосовых вызовов указываются в политиках голосовой связи, назначенных непосредственно пользователям, и политиках маршрутизации голосовой связи, назначенных сетевым сайтам.</span><span class="sxs-lookup"><span data-stu-id="9c71b-162">Voice routes are referenced in both Voice Policies assigned directly to users, and Voice Routing Policies assigned to network sites.</span></span> <span data-ttu-id="9c71b-163">Обе политики содержат ссылки на маршруты, которые можно использовать для нахождения вызова по-другому.</span><span class="sxs-lookup"><span data-stu-id="9c71b-163">Both policies contain references to routes, which can be used to route a call differently.</span></span> <span data-ttu-id="9c71b-164">Например, администратор может определить политику маршрутизации голосовых вызовов для всех пользователей, расположенных на сетевом сайте 1, для маршрутизации всех исходящих вызовов через шлюз "сайт 1", в то время как политика голосовой связи для всех исходящих вызовов через шлюз "сайт 2".</span><span class="sxs-lookup"><span data-stu-id="9c71b-164">For example, an administrator can define a Voice Routing Policy for all users located in network site 1 to route all outbound calls through the “Site 1 Gateway” while the Voice Policy of some users define a route for all outbound calls through the “Site 2 Gateway”.</span></span> <span data-ttu-id="9c71b-165">Хотя эти пользователи находятся в сетевом сайте 1, их исходящие звонки будут маршрутизироваться через шлюз "сайт 1".</span><span class="sxs-lookup"><span data-stu-id="9c71b-165">While these users are located in network site 1, their outbound calls will be routed through the “Site 1 Gateway”.</span></span>

<span data-ttu-id="9c71b-166">Когда пользователь находится на сетевом сайте, настроенном для маршрутизации на основе расположения, маршрут политики маршрутизации голосовой связи на сетевом сайте переопределяет маршрут политики голосовой связи пользователя.</span><span class="sxs-lookup"><span data-stu-id="9c71b-166">When a user is located in a network site configured for Location-Based Routing, the network site’s Voice Routing Policy route overrides the user’s Voice Policy route.</span></span> <span data-ttu-id="9c71b-167">Это правило особенно удобно для пользователей, которые временно переходят на другой сайт.</span><span class="sxs-lookup"><span data-stu-id="9c71b-167">This rule is particularly useful for users that temporarily move to a different site.</span></span> <span data-ttu-id="9c71b-168">В этом конкретном случае пользователь всегда будет использовать шлюз, который является локальным по отношению к его расположению; Если "Lync User 3" расположен по адресу "сайт 2", все его исходящие звонки будут маршрутизироваться через шлюз сайта 2, но если он перейдет на сайт 1, все исходящие звонки, размещенные на сайте 1, будут маршрутизироваться через шлюз "сайт 1".</span><span class="sxs-lookup"><span data-stu-id="9c71b-168">In this particular case a user will always use a gateway that is local to his location; if “Lync user 3” is located at “Site 2”, all his outbound calls will be routed via “Site 2 Gateway”, but if he travels to site 1, all his outbound calls placed while he’s at site 1 will be routed through “Site 1 Gateway”.</span></span>

<span data-ttu-id="9c71b-169">В следующей таблице показано, как пользователь Lync User 1 помещает исходящий вызов со следующих сетевых сайтов.</span><span class="sxs-lookup"><span data-stu-id="9c71b-169">The following table illustrates the user experience of Lync user 1 placing an outbound call from the following network sites.</span></span>


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
<th><span data-ttu-id="9c71b-170">Сетевой сайт 1</span><span class="sxs-lookup"><span data-stu-id="9c71b-170">Network site 1</span></span></th>
<th><span data-ttu-id="9c71b-171">Сетевой сайт 2</span><span class="sxs-lookup"><span data-stu-id="9c71b-171">Network site 2</span></span></th>
<th><span data-ttu-id="9c71b-172">Неизвестный сетевой сайт или не включен для маршрутизации на основе расположения</span><span class="sxs-lookup"><span data-stu-id="9c71b-172">Unknown network site or not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9c71b-173">Авторизация исходящих вызовов</span><span class="sxs-lookup"><span data-stu-id="9c71b-173">Authorization of outbound calls</span></span></p></td>
<td><p><span data-ttu-id="9c71b-174">Политика голосовой связи пользователя Lync 1</span><span class="sxs-lookup"><span data-stu-id="9c71b-174">Lync user 1 voice policy</span></span></p></td>
<td><p><span data-ttu-id="9c71b-175">Политика голосовой связи пользователя Lync 1</span><span class="sxs-lookup"><span data-stu-id="9c71b-175">Lync user 1 voice policy</span></span></p></td>
<td><p><span data-ttu-id="9c71b-176">Политика голосовой связи пользователя Lync 1</span><span class="sxs-lookup"><span data-stu-id="9c71b-176">Lync user 1 voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c71b-177">Маршрутизация исходящих вызовов</span><span class="sxs-lookup"><span data-stu-id="9c71b-177">Routing of outbound calls</span></span></p></td>
<td><p><span data-ttu-id="9c71b-178">Политика маршрутизации голосовой связи для сайта 1</span><span class="sxs-lookup"><span data-stu-id="9c71b-178">Site 1 voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="9c71b-179">Политика маршрутизации голосовой связи на сайте 2</span><span class="sxs-lookup"><span data-stu-id="9c71b-179">Site 2 voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="9c71b-180">Политика голосовой связи пользователя и только для тех систем, для которых не включена маршрутизация на основе расположения</span><span class="sxs-lookup"><span data-stu-id="9c71b-180">User’s voice policy and only to systems not enabled for Location-Based Routing</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="call-transfers-and-forwards"></a><span data-ttu-id="9c71b-181">Передача и переадресация звонков</span><span class="sxs-lookup"><span data-stu-id="9c71b-181">Call transfers and forwards</span></span>

<span data-ttu-id="9c71b-182">Когда звонки передаются или пересылаются, маршрутизация вызовов зависит от маршрутизации на основе расположения.</span><span class="sxs-lookup"><span data-stu-id="9c71b-182">When calls are transferred or forwarded, the routing of calls is affected by Location-Based Routing.</span></span>

<span data-ttu-id="9c71b-183">В приведенной ниже таблице показано, как пользователь Lync 1 пересылает или пересылает вызовы PSTN другому пользователю Lync.</span><span class="sxs-lookup"><span data-stu-id="9c71b-183">The following table depicts Lync user 1 transferring or forwarding a PSTN call to another Lync user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9c71b-184">Пользователь, инициирующий передачу или переадресацию вызовов</span><span class="sxs-lookup"><span data-stu-id="9c71b-184">User initiating call transfer or forward</span></span></th>
<th><span data-ttu-id="9c71b-185">Пользователь Lync 2</span><span class="sxs-lookup"><span data-stu-id="9c71b-185">Lync user 2</span></span></th>
<th><span data-ttu-id="9c71b-186">Пользователь Lync 4</span><span class="sxs-lookup"><span data-stu-id="9c71b-186">Lync user 4</span></span></th>
<th><span data-ttu-id="9c71b-187">Пользователь Lync на сетевом сайте не включен для маршрутизации на основе расположения</span><span class="sxs-lookup"><span data-stu-id="9c71b-187">Lync user in network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9c71b-188">Пользователь Lync 1</span><span class="sxs-lookup"><span data-stu-id="9c71b-188">Lync user 1</span></span></p></td>
<td><p><span data-ttu-id="9c71b-189">Переадресация звонков или передача разрешена</span><span class="sxs-lookup"><span data-stu-id="9c71b-189">Call forward or transfer is allowed</span></span></p></td>
<td><p><span data-ttu-id="9c71b-190">Переадресация вызовов и передача запрещены</span><span class="sxs-lookup"><span data-stu-id="9c71b-190">Call forward or transfer is not allowed</span></span></p></td>
<td><p><span data-ttu-id="9c71b-191">Переадресация вызовов и передача запрещены</span><span class="sxs-lookup"><span data-stu-id="9c71b-191">Call forward or transfer is not allowed</span></span></p></td>
</tr>
</tbody>
</table>

  
<span data-ttu-id="9c71b-192">В следующей таблице показано, как маршрутизация на основе расположения влияет на маршрутизацию вызовов на основе расположения передаваемых пользователей Lync (Lync User 2, Lync User 4 и т. д.) на конечную точку PSTN.</span><span class="sxs-lookup"><span data-stu-id="9c71b-192">The following table illustrates how Location-Based Routing affects how the call is routed based on the location of the Lync user being transferred (Lync user 2, Lync user 4, etc) to a PSTN endpoint</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9c71b-193">Конечная точка, в которую пересылается или передается вызов</span><span class="sxs-lookup"><span data-stu-id="9c71b-193">Endpoint where call is transferred or forwarded to</span></span></th>
<th><span data-ttu-id="9c71b-194">Пользователь Lync 2</span><span class="sxs-lookup"><span data-stu-id="9c71b-194">Lync user 2</span></span></th>
<th><span data-ttu-id="9c71b-195">Пользователь Lync 4</span><span class="sxs-lookup"><span data-stu-id="9c71b-195">Lync user 4</span></span></th>
<th><span data-ttu-id="9c71b-196">Пользователь Lync на сетевом сайте не включен для маршрутизации на основе расположения</span><span class="sxs-lookup"><span data-stu-id="9c71b-196">Lync user in network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9c71b-197">Конечная точка PSTN</span><span class="sxs-lookup"><span data-stu-id="9c71b-197">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="9c71b-198">Переадресация звонков или передача выполняется через политику маршрутизации голосовой связи на сайте 1 и исходящий через шлюз сайта 1</span><span class="sxs-lookup"><span data-stu-id="9c71b-198">Call forward or transfer is routed through site 1 voice routing policy and egress via Site 1 Gateway</span></span></p></td>
<td><p><span data-ttu-id="9c71b-199">Переадресация звонков или передача выполняется через политику маршрутизации голосовой связи на сайте 2 и исходящий через шлюз сайта 2</span><span class="sxs-lookup"><span data-stu-id="9c71b-199">Call forward or transfer is routed through site 2 voice routing policy and egress via Site 2 Gateway</span></span></p></td>
<td><p><span data-ttu-id="9c71b-200">Переадресация звонка или передача направляются через политику голосовой связи пользователя Lync и исходящий через шлюз, не включенный для маршрутизации на основе расположения (при наличии).</span><span class="sxs-lookup"><span data-stu-id="9c71b-200">Call forward or transfer is routed through the Lync user voice policy and egress via a gateway not enabled for location-based routing (if available)</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="simultaneous-ringing"></a><span data-ttu-id="9c71b-201">Одновременный звонок</span><span class="sxs-lookup"><span data-stu-id="9c71b-201">Simultaneous ringing</span></span>

<span data-ttu-id="9c71b-202">После настройки маршрутизации на основе расположения в образце топологии применяются следующие взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="9c71b-202">Once location-based routing is configured in the sample topology, the following interactions are enforced.</span></span>

<span data-ttu-id="9c71b-203">В следующей таблице показано, позволяет ли маршрутизация на основе расположения использовать одновременные звонки для разных пользователей Lync (то есть Lync User 2, Lync User 4 и т. д.).</span><span class="sxs-lookup"><span data-stu-id="9c71b-203">The following table illustrates whether Location-Based Routing allows simultaneous ringing for different Lync users (i.e. Lync user 2, Lync user 4, etc).</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9c71b-204">Входящий конечный звонок для PSTN</span><span class="sxs-lookup"><span data-stu-id="9c71b-204">Incoming PSTN call target</span></span></th>
<th><span data-ttu-id="9c71b-205">Пользователь Lync 2</span><span class="sxs-lookup"><span data-stu-id="9c71b-205">Lync user 2</span></span></th>
<th><span data-ttu-id="9c71b-206">Пользователь Lync 4</span><span class="sxs-lookup"><span data-stu-id="9c71b-206">Lync user 4</span></span></th>
<th><span data-ttu-id="9c71b-207">Пользователь Lync на сетевом сайте не включен для маршрутизации на основе расположения</span><span class="sxs-lookup"><span data-stu-id="9c71b-207">Lync user in network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9c71b-208">Пользователь Lync 1</span><span class="sxs-lookup"><span data-stu-id="9c71b-208">Lync user 1</span></span></p></td>
<td><p><span data-ttu-id="9c71b-209">Одновременный звонок разрешен</span><span class="sxs-lookup"><span data-stu-id="9c71b-209">Simultaneous ring is allowed</span></span></p></td>
<td><p><span data-ttu-id="9c71b-210">Одновременный звонок не разрешен</span><span class="sxs-lookup"><span data-stu-id="9c71b-210">Simultaneous ring is not allowed</span></span></p></td>
<td><p><span data-ttu-id="9c71b-211">Одновременный звонок не разрешен</span><span class="sxs-lookup"><span data-stu-id="9c71b-211">Simultaneous ring is not allowed</span></span></p></td>
</tr>
</tbody>
</table>

  
<span data-ttu-id="9c71b-212">В следующей таблице показано, позволяет ли маршрутизация на основе расположения использовать Одновременный звонок в конечную точку PSTN от разных пользователей Lync (то есть Lync User 2, Lync User 4 и т. д.).</span><span class="sxs-lookup"><span data-stu-id="9c71b-212">The following table illustrates whether Location-Based Routing allows simultaneous ringing to a PSTN endpoint from different Lync users (i.e. Lync user 2, Lync user 4, etc).</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9c71b-213">Цель одновременных звонков</span><span class="sxs-lookup"><span data-stu-id="9c71b-213">Simultaneous ring target</span></span></th>
<th><span data-ttu-id="9c71b-214">Пользователь Lync 2</span><span class="sxs-lookup"><span data-stu-id="9c71b-214">Lync user 2</span></span></th>
<th><span data-ttu-id="9c71b-215">Пользователь Lync 4</span><span class="sxs-lookup"><span data-stu-id="9c71b-215">Lync user 4</span></span></th>
<th><span data-ttu-id="9c71b-216">Пользователь Lync на сетевом сайте не включен для маршрутизации на основе расположения</span><span class="sxs-lookup"><span data-stu-id="9c71b-216">Lync user in network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9c71b-217">Мобильный телефон пользователя Lync 1 (конечная точка PSTN)</span><span class="sxs-lookup"><span data-stu-id="9c71b-217">Lync user 1 mobile phone (PSTN endpoint)</span></span></p></td>
<td><p><span data-ttu-id="9c71b-218">Вызов, направляемый через политику маршрутизации голосовой связи на сетевом сайте 1 и исходящий через шлюз сайта 1</span><span class="sxs-lookup"><span data-stu-id="9c71b-218">Call routed through network site 1’s voice routing policy and egress via site 1 gateway</span></span></p></td>
<td><p><span data-ttu-id="9c71b-219">Вызов, направляемый через политику маршрутизации голосовой связи на сетевом сайте 2 и исходящий через шлюз сайта 2</span><span class="sxs-lookup"><span data-stu-id="9c71b-219">Call routed through network site 2’s voice routing policy and egress via site 2 gateway</span></span></p></td>
<td><p><span data-ttu-id="9c71b-220">Вызов направляется через абонентскую политику голосовой связи и будет исходящий через шлюз PSTN, не включенный для маршрутизации на основе расположения</span><span class="sxs-lookup"><span data-stu-id="9c71b-220">Call routed through the caller voice policy and will egress via a PSTN gateway not enabled for Location-Based Routing</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9c71b-221">См. также</span><span class="sxs-lookup"><span data-stu-id="9c71b-221">See Also</span></span>


[<span data-ttu-id="9c71b-222">Планирование маршрутизации на основе расположения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9c71b-222">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

