---
title: 'Lync Server 2013: требования для маршрутизации на основе местоположения для конференций'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Requirements for Location-Based Routing for conferencing
ms:assetid: 766d9286-2c34-4faf-bb3e-f0ca478a70cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362806(v=OCS.15)
ms:contentKeyID: 56335085
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ac57a32476d80ab1aca5d2ad0928e2862a4c8558
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723819"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="requirements-for-location-based-routing-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="83621-102">Требования для маршрутизации на основе местоположения для конференц-связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="83621-102">Requirements for Location-Based Routing for conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="83621-103">_**Тема последнего изменения:** 2013-07-19_</span><span class="sxs-lookup"><span data-stu-id="83621-103">_**Topic Last Modified:** 2013-07-19_</span></span>

<span data-ttu-id="83621-104">Ниже приведены требования, необходимые для установки и настройки приложения для конференц-связи с учетом местоположения.</span><span class="sxs-lookup"><span data-stu-id="83621-104">The following are the requirements needed for the installation and configuration of the Location-Based Routing Conferencing application:</span></span>

  - <span data-ttu-id="83621-105">Для Lync Server 2013 накопительный пакет обновления 2 должен быть развернут на всех серверах или пулах в вашей топологии.</span><span class="sxs-lookup"><span data-stu-id="83621-105">Lync Server 2013 Cumulative Update 2 must be deployed on all servers or pools in your topology.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="83621-106">Если на сервере Lync или в пуле в топологии не установлен компонент Lync Server 2013 накопительный пакет обновления 2 или более новой версии, принудительное применение маршрутизации на основе местоположения для собраний Lync не гарантируется.</span><span class="sxs-lookup"><span data-stu-id="83621-106">If a Lync server or pool in your topology does not have Lync Server 2013 Cumulative Update 2 or higher installed, then enforcement of Location-Based Routing of Lync meetings cannot be guaranteed.</span></span>



</div>

  - <span data-ttu-id="83621-107">Сервер Lync Server 2013 — это предварительное требование для приложения для конференц-связи с учетом местоположения.</span><span class="sxs-lookup"><span data-stu-id="83621-107">Lync Server 2013 Location-Based Routing is a pre-requisite for Location-Based Routing Conferencing application.</span></span> <span data-ttu-id="83621-108">Дополнительные сведения о настройке маршрутизации на основе местоположения в Lync Server 2013 можно найти в разделе [Настройка маршрутизации на основе местоположения](lync-server-2013-configuring-location-based-routing.md).</span><span class="sxs-lookup"><span data-stu-id="83621-108">For further information on configuring Lync Server 2013 Location-Based Routing, please refer to [Configuring Location-Based Routing](lync-server-2013-configuring-location-based-routing.md).</span></span>

  - <span data-ttu-id="83621-109">Требования к приложению для конференц-связи на основе местоположения аналогичны требованиям для маршрутизации на основе местоположения в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="83621-109">Requirements of Location-Based Routing Conferencing application are the same as the requirements for Lync Server 2013 Location-Based Routing.</span></span> <span data-ttu-id="83621-110">Дополнительные сведения можно найти в разделе [планирование маршрутизации на основе местоположения](lync-server-2013-planning-for-location-based-routing.md).</span><span class="sxs-lookup"><span data-stu-id="83621-110">For more information, please refer to [Planning for Location-Based Routing](lync-server-2013-planning-for-location-based-routing.md).</span></span>

<div>

## <a name="supported-servers"></a><span data-ttu-id="83621-111">Поддерживаемые серверы</span><span class="sxs-lookup"><span data-stu-id="83621-111">Supported Servers</span></span>

<span data-ttu-id="83621-112">Приложение для конференц-связи с учетом местоположения требует, чтобы Lync Server 2013 накопительный пакет обновления 2 развернут на всех интерфейсных пулах и серверах стандартных выпусков в вашей топологии.</span><span class="sxs-lookup"><span data-stu-id="83621-112">The Location-Based Routing Conferencing application requires that Lync Server 2013 Cumulative Update 2 is deployed on all Front-End pools and Standard Edition Servers in your topology.</span></span> <span data-ttu-id="83621-113">Если в вашей топологии Lync Server 2013 накопительный пакет обновления 2 (SP2) не установлен на некоторых серверах Lync, ограничения на маршрутизацию на основе местоположения не будут полностью применены для собраний Lync и консултативе передачи звонков.</span><span class="sxs-lookup"><span data-stu-id="83621-113">If Lync Server 2013 Cumulative Update 2 is not installed on some Lync Servers in your topology, Location-Based Routing restrictions cannot be fully enforced on Lync meetings and consultative call transfers.</span></span>

<span data-ttu-id="83621-114">В следующей таблице указаны комбинации ролей сервера и версий, которые поддерживают маршрутизацию на основе местоположения.</span><span class="sxs-lookup"><span data-stu-id="83621-114">The following table identifies the combination of server roles and versions that support Location-Based Routing.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="83621-115">Версия внешнего пула</span><span class="sxs-lookup"><span data-stu-id="83621-115">Front-End Pool version</span></span></p></td>
<td><p><span data-ttu-id="83621-116">Версия cервера-посредника</span><span class="sxs-lookup"><span data-stu-id="83621-116">Mediation Server version</span></span></p></td>
<td><p><span data-ttu-id="83621-117">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="83621-117">Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83621-118">Накопительный пакет обновления 2 для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="83621-118">Lync Server 2013 Cumulative Update 2</span></span></p></td>
<td><p><span data-ttu-id="83621-119">Накопительный пакет обновления 2 для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="83621-119">Lync Server 2013 Cumulative Update 2</span></span></p></td>
<td><p><span data-ttu-id="83621-120">Да</span><span class="sxs-lookup"><span data-stu-id="83621-120">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83621-121">Накопительный пакет обновления 2 для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="83621-121">Lync Server 2013 Cumulative Update 2</span></span></p></td>
<td><p><span data-ttu-id="83621-122">Накопительный пакет обновления 1 для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="83621-122">Lync Server 2013 Cumulative Update 1</span></span></p></td>
<td><p><span data-ttu-id="83621-123">Нет</span><span class="sxs-lookup"><span data-stu-id="83621-123">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83621-124">Накопительный пакет обновления 2 для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="83621-124">Lync Server 2013 Cumulative Update 2</span></span></p></td>
<td><p><span data-ttu-id="83621-125">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="83621-125">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="83621-126">Нет</span><span class="sxs-lookup"><span data-stu-id="83621-126">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83621-127">Накопительный пакет обновления 2 для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="83621-127">Lync Server 2013 Cumulative Update 2</span></span></p></td>
<td><p><span data-ttu-id="83621-128">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="83621-128">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="83621-129">Нет</span><span class="sxs-lookup"><span data-stu-id="83621-129">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83621-130">Накопительный пакет обновления 1 для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="83621-130">Lync Server 2013 Cumulative Update 1</span></span></p></td>
<td><p><span data-ttu-id="83621-131">Любой</span><span class="sxs-lookup"><span data-stu-id="83621-131">Any</span></span></p></td>
<td><p><span data-ttu-id="83621-132">Нет</span><span class="sxs-lookup"><span data-stu-id="83621-132">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83621-133">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="83621-133">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="83621-134">Любой</span><span class="sxs-lookup"><span data-stu-id="83621-134">Any</span></span></p></td>
<td><p><span data-ttu-id="83621-135">Нет</span><span class="sxs-lookup"><span data-stu-id="83621-135">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83621-136">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="83621-136">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="83621-137">Любой</span><span class="sxs-lookup"><span data-stu-id="83621-137">Any</span></span></p></td>
<td><p><span data-ttu-id="83621-138">Нет</span><span class="sxs-lookup"><span data-stu-id="83621-138">No</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="supported-clients"></a><span data-ttu-id="83621-139">Поддерживаемые клиенты</span><span class="sxs-lookup"><span data-stu-id="83621-139">Supported Clients</span></span>

<span data-ttu-id="83621-140">Клиенты Lync, поддерживающие маршрутизацию на основе местоположения для собраний Lync, — это те же клиенты, которые поддерживают маршрут на основе расположения в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="83621-140">The Lync clients that support Location-Based Routing of Lync meetings are the same clients that support Lync Server 2013 Location-Based Routing.</span></span> <span data-ttu-id="83621-141">Дополнительные сведения можно найти в разделе [Поддержка клиентов и серверов для маршрутизации на основе местоположения](lync-server-2013-client-and-server-support-for-location-based-routing.md).</span><span class="sxs-lookup"><span data-stu-id="83621-141">For more information, please refer to [Client and Server Support for Location-Based Routing](lync-server-2013-client-and-server-support-for-location-based-routing.md).</span></span>

</div>

<div>

## <a name="mediation-server-requirements-for-consultative-call-transfers"></a><span data-ttu-id="83621-142">Требования к серверу исправлений для передачи вызовов Консултативе</span><span class="sxs-lookup"><span data-stu-id="83621-142">Mediation Server Requirements for Consultative Call Transfers</span></span>

<span data-ttu-id="83621-143">Приложение для конференц-связи с учетом местоположения требует развертывания изолированных серверов, чтобы обеспечить ограничения маршрутизации на основе местоположения при передаче звонков консултативе.</span><span class="sxs-lookup"><span data-stu-id="83621-143">The Location-Based Routing Conferencing application requires deploying stand-alone Mediation Servers in order to enforce Location-Based Routing restrictions on consultative call transfers.</span></span>

<span data-ttu-id="83621-144">Для принудительного применения маршрутизации, основанной на расположении для передачи вызовов консултативе, сервер-посредник должен быть связан только с одним одноранговым узлом (например, УАТС, шлюзом SIP и т. д.) в сетевых регионах, где требуется маршрутизация на основе местоположения.</span><span class="sxs-lookup"><span data-stu-id="83621-144">To enforce Location-Based Routing of consultative call transfers, the Mediation Server must be associated with only one Mediation Server peer (i.e. PBX, SIP gateway, etc) in network regions where Location-Based Routing is required.</span></span> <span data-ttu-id="83621-145">Если в одном и том же регионе развернуты одноранговые узлы сервера-посредника, то узел сервера-посредника должен быть связан с другим сервером-посредником.</span><span class="sxs-lookup"><span data-stu-id="83621-145">If additional Mediation Server peers are deployed in the same network region, the Mediation Server peer must be associated with a different Mediation Server .</span></span> <span data-ttu-id="83621-146">Это требование подробно описано ниже.</span><span class="sxs-lookup"><span data-stu-id="83621-146">This Requirement is detailed as follows:</span></span>

  - <span data-ttu-id="83621-147">Одноранговый сервер для одного сервера-посредника, когда передача вызова консултативе перенаправляется на одноранговый сервер с несколькими магистральными серверами (например, АТС и шлюзы). консултативе Передача вызова блокируется, чтобы предотвратить бесплатный звонок, если передача вызова консултативе разрешена через некоторые магистральные магистрали SIP, но это запрещено посредством других магистральных каналов SIP.</span><span class="sxs-lookup"><span data-stu-id="83621-147">Single Mediation Server per multiple Mediation Server peers When a consultative call transfer is routed to a Mediation Server peer through a Mediation Server that’s configured with multiple SIP trunks to multiple peers (i.e. PBXs and gateways), the consultative call transfer is blocked to prevent PSTN toll bypass if the consultative call transfer is permitted through some SIP trunks but disallowed through other SIP trunks.</span></span>
    
    <span data-ttu-id="83621-148">Например, в случае одного сервера-посредника, обслуживающего одноранговый сервер шлюза КТСОП и одноранговый сервер обнаружения АТС, будет проблюдаться описанное ниже поведение.</span><span class="sxs-lookup"><span data-stu-id="83621-148">For example, in the case of a single Mediation Server servicing a PSTN Gateway Mediation Server Peer and a PBX Mediation Server Peer, the following behavior will be observed:</span></span>
    
      - <span data-ttu-id="83621-149">Если пользователь Lync с определенного сайта (например, сайт 1) пытается передать Звонок в конечную точку PSTN пользователю Lync из другого сайта (например, сайта 2) через консултативе Transfer, Звонок будет запрещен для предотвращения бесплатных звонков по сети PSTN.</span><span class="sxs-lookup"><span data-stu-id="83621-149">When a Lync user from a given site (i.e. site 1) attempts to transfer a call with a PSTN endpoint to a Lync user from a different site (i.e. site 2) via consultative transfer, the call will be disallowed to prevent PSTN toll bypass.</span></span>
    
      - <span data-ttu-id="83621-150">Если пользователь Lync с определенного сайта (например, сайт 1) пытается передать звонок с помощью конечной точки УАТС в том же сайте (например, на сайте 1) для пользователя Lync с другого сайта (то есть сайта 2) через консултативе Transfer, Звонок будет запрещен, даже если он не повлечет за потенциальные КТСОП Тол l обойти.</span><span class="sxs-lookup"><span data-stu-id="83621-150">When a Lync user from a given site (i.e. site 1) attempts to transfer a call with a PBX endpoint in the same site (site 1) to a Lync user from a different site (i.e. site 2) via consultative transfer, the call will be disallowed even if it doesn’t incur in potential PSTN toll bypassing.</span></span>

  - <span data-ttu-id="83621-151">Отдельные серверы исправлений для одного из серверов исправлений</span><span class="sxs-lookup"><span data-stu-id="83621-151">Separate Mediation Servers per Mediation Server peer</span></span>
    
    <span data-ttu-id="83621-152">Когда консултативе передача предназначена для однорангового сервера-посредника, пересылка консултативе будет оцениваться относительно однорангового сервера единого обслуживания, обслуживаемого сервером-посредником.</span><span class="sxs-lookup"><span data-stu-id="83621-152">When a consultative transfer is targeted at a Mediation Server Peer, the consultative transfer will be evaluated against the single Mediation Server Peer serviced by the Mediation Server.</span></span> <span data-ttu-id="83621-153">Этот звонок не будет разрешен или разрешен в соответствии со своими возможностями, которые могут повлечь за собой бесплатные звонки по бесплатной сети, независимо от того, на каком сервере они обходились, по мере их обслуживания разными серверами-посредниками.</span><span class="sxs-lookup"><span data-stu-id="83621-153">The call will be disallowed or allowed based in its potential to incur in PSTN toll bypass regardless of all other Mediations Server Peers in the site as they’re serviced by separate Mediation Servers.</span></span>
    
    <span data-ttu-id="83621-154">Например, в случае отдельного сервера-посредника, обслуживающего одноранговый сервер шлюза КТСОП и одноранговый сервер обнаружения АТС, будут наблюдаться указанные ниже правила.</span><span class="sxs-lookup"><span data-stu-id="83621-154">For example, in the case of a separate Mediation Servers servicing a PSTN Gateway Mediation Server Peer and a PBX Mediation Server Peer, the following behavior will be observed:</span></span>
    
      - <span data-ttu-id="83621-155">Если пользователь Lync с определенного сайта (например, сайт 1) пытается передать Звонок в конечную точку PSTN пользователю Lync из другого сайта (например, сайта 2) через консултативе Transfer, Звонок будет запрещен для предотвращения бесплатных звонков по сети PSTN.</span><span class="sxs-lookup"><span data-stu-id="83621-155">When a Lync user from a given site (i.e. site 1) attempts to transfer a call with a PSTN endpoint to a Lync user from a different site (i.e. site 2) via consultative transfer, the call will be disallowed to prevent PSTN toll bypass.</span></span>
    
      - <span data-ttu-id="83621-156">Если пользователь Lync с определенного сайта (например, сайт 1) пытается передать Звонок в конечную точку УАТС в том же сайте (например, на сайте 1) для пользователя Lync с другого сайта (то есть для сайта 2) через консултативе Transfer, Звонок будет разрешен, так как он не повлечет за собой потенциальную бесплатный звонок. амперсанд.</span><span class="sxs-lookup"><span data-stu-id="83621-156">When a Lync user from a given site (i.e. site 1) attempts to transfer a call with a PBX endpoint in the same site (site 1) to a Lync user from a different site (i.e. site 2) via consultative transfer, the call will be allowed as it doesn’t incur in potential PSTN toll bypassing.</span></span>

</div>

<div>

## <a name="capabilities-not-supported-by-the-location-based-routing-conferencing-application"></a><span data-ttu-id="83621-157">Возможности, не поддерживаемые приложением для организации маршрутизации на основе местоположения</span><span class="sxs-lookup"><span data-stu-id="83621-157">Capabilities Not Supported by the Location-Based Routing Conferencing Application</span></span>

<span data-ttu-id="83621-158">Следующие возможности не поддерживаются в приложении для конференц-связи с учетом расположения.</span><span class="sxs-lookup"><span data-stu-id="83621-158">The following capabilities are not supported by the Location-Based Routing Conferencing application:</span></span>

  - <span data-ttu-id="83621-159">Конференц-связь с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="83621-159">Dial-in conferencing.</span></span> <span data-ttu-id="83621-160">Для конференц-связи с телефонным подключением нельзя применять маршрутизацию на основе местоположения.</span><span class="sxs-lookup"><span data-stu-id="83621-160">Location-Based Routing cannot be enforced for Dial-in conferencing.</span></span> <span data-ttu-id="83621-161">Любой запрос на подключение к данной Конференции не будет ограничен маршрутом на основе местоположения, даже если организатором конференции является пользователь Lync, для которого включена маршрутизация на основе местоположения.</span><span class="sxs-lookup"><span data-stu-id="83621-161">Any dial-in request to a given conference will not be restricted by Location-Based Routing even if the conference organizer is a Lync user enabled for Location-Based Routing.</span></span>

  - <span data-ttu-id="83621-162">Рекомендуется не предоставлять номера доступа к конференциям в регионах, в которых необходимо применять ограничения маршрутизации на основе местоположения.</span><span class="sxs-lookup"><span data-stu-id="83621-162">It’s recommended not to provision conferencing access numbers in regions where Location-Based Routing restrictions need to be enforced.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

