---
title: 'Lync Server 2013: требования для маршрутизации Location-Based для конференц-связи'
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
ms.openlocfilehash: 66be7f9dd3faeb167519d9ce815e84f8cf692c22
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511856"
---
# <a name="requirements-for-location-based-routing-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="314a6-102">Требования к маршрутизации Location-Based для конференц-связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="314a6-102">Requirements for Location-Based Routing for conferencing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="314a6-103">_**Последнее изменение темы:** 2013-07-19_</span><span class="sxs-lookup"><span data-stu-id="314a6-103">_**Topic Last Modified:** 2013-07-19_</span></span>

<span data-ttu-id="314a6-104">Ниже приведены требования, необходимые для установки и настройки приложения для конференц-связи Location-Based маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="314a6-104">The following are the requirements needed for the installation and configuration of the Location-Based Routing Conferencing application:</span></span>

  - <span data-ttu-id="314a6-105">Накопительный пакет обновления 2 (SP2) для Lync Server 2013 должен быть развернут на всех серверах или в пулах в вашей топологии.</span><span class="sxs-lookup"><span data-stu-id="314a6-105">Lync Server 2013 Cumulative Update 2 must be deployed on all servers or pools in your topology.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="314a6-106">Если на сервере Lync Server или в топологии в вашей топологии не установлен накопительный пакет обновления 2 (SP2) для Lync Server 2013 или более поздней версии, принудительное применение Location-Based маршрутизации собраний Lync не гарантируется.</span><span class="sxs-lookup"><span data-stu-id="314a6-106">If a Lync server or pool in your topology does not have Lync Server 2013 Cumulative Update 2 or higher installed, then enforcement of Location-Based Routing of Lync meetings cannot be guaranteed.</span></span>



</div>

  - <span data-ttu-id="314a6-107">Lync Server 2013 Location-Based маршрутизация является предварительным условием для приложения для конференц-связи Location-Based маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="314a6-107">Lync Server 2013 Location-Based Routing is a pre-requisite for Location-Based Routing Conferencing application.</span></span> <span data-ttu-id="314a6-108">Для получения дополнительных сведений о настройке маршрутизации Location-Based Lync Server 2013 обратитесь к разделу [Настройка маршрутизации Location-Based](lync-server-2013-configuring-location-based-routing.md).</span><span class="sxs-lookup"><span data-stu-id="314a6-108">For further information on configuring Lync Server 2013 Location-Based Routing, please refer to [Configuring Location-Based Routing](lync-server-2013-configuring-location-based-routing.md).</span></span>

  - <span data-ttu-id="314a6-109">Требования к приложению для конференц-связи Location-Based маршрутизации совпадают с требованиями для сервера Lync Server 2013 Location-Based маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="314a6-109">Requirements of Location-Based Routing Conferencing application are the same as the requirements for Lync Server 2013 Location-Based Routing.</span></span> <span data-ttu-id="314a6-110">Для получения дополнительных сведений обратитесь к разделу [планирование Location-Basedной маршрутизации](lync-server-2013-planning-for-location-based-routing.md).</span><span class="sxs-lookup"><span data-stu-id="314a6-110">For more information, please refer to [Planning for Location-Based Routing](lync-server-2013-planning-for-location-based-routing.md).</span></span>

<div>

## <a name="supported-servers"></a><span data-ttu-id="314a6-111">Поддерживаемые серверы</span><span class="sxs-lookup"><span data-stu-id="314a6-111">Supported Servers</span></span>

<span data-ttu-id="314a6-112">Приложение для конференц-связи Location-Based маршрутизации требует, чтобы Lync Server 2013 с накопительным пакетом обновления 2 был развернут на всех пулах Front-End и серверах Standard Edition в вашей топологии.</span><span class="sxs-lookup"><span data-stu-id="314a6-112">The Location-Based Routing Conferencing application requires that Lync Server 2013 Cumulative Update 2 is deployed on all Front-End pools and Standard Edition Servers in your topology.</span></span> <span data-ttu-id="314a6-113">Если накопительный пакет обновления 2 (SP2) для Lync Server 2013 не установлен на некоторых серверах Lync в вашей топологии, Location-Based ограничения маршрутизации не могут быть полностью применены для собраний Lync и передачи вызовов Консультативного.</span><span class="sxs-lookup"><span data-stu-id="314a6-113">If Lync Server 2013 Cumulative Update 2 is not installed on some Lync Servers in your topology, Location-Based Routing restrictions cannot be fully enforced on Lync meetings and consultative call transfers.</span></span>

<span data-ttu-id="314a6-114">В следующей таблице указаны комбинации ролей и версий сервера, поддерживающих маршрутизацию Location-Based.</span><span class="sxs-lookup"><span data-stu-id="314a6-114">The following table identifies the combination of server roles and versions that support Location-Based Routing.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="314a6-115">Версия пула Front-End</span><span class="sxs-lookup"><span data-stu-id="314a6-115">Front-End Pool version</span></span></p></td>
<td><p><span data-ttu-id="314a6-116">Версия сервера-посредника</span><span class="sxs-lookup"><span data-stu-id="314a6-116">Mediation Server version</span></span></p></td>
<td><p><span data-ttu-id="314a6-117">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="314a6-117">Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="314a6-118">Накопительный пакет обновления 2 для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="314a6-118">Lync Server 2013 Cumulative Update 2</span></span></p></td>
<td><p><span data-ttu-id="314a6-119">Накопительный пакет обновления 2 для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="314a6-119">Lync Server 2013 Cumulative Update 2</span></span></p></td>
<td><p><span data-ttu-id="314a6-120">Да</span><span class="sxs-lookup"><span data-stu-id="314a6-120">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="314a6-121">Накопительный пакет обновления 2 для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="314a6-121">Lync Server 2013 Cumulative Update 2</span></span></p></td>
<td><p><span data-ttu-id="314a6-122">Накопительный пакет обновления 1 для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="314a6-122">Lync Server 2013 Cumulative Update 1</span></span></p></td>
<td><p><span data-ttu-id="314a6-123">Нет</span><span class="sxs-lookup"><span data-stu-id="314a6-123">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="314a6-124">Накопительный пакет обновления 2 для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="314a6-124">Lync Server 2013 Cumulative Update 2</span></span></p></td>
<td><p><span data-ttu-id="314a6-125">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="314a6-125">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="314a6-126">Нет</span><span class="sxs-lookup"><span data-stu-id="314a6-126">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="314a6-127">Накопительный пакет обновления 2 для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="314a6-127">Lync Server 2013 Cumulative Update 2</span></span></p></td>
<td><p><span data-ttu-id="314a6-128">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="314a6-128">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="314a6-129">Нет</span><span class="sxs-lookup"><span data-stu-id="314a6-129">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="314a6-130">Накопительный пакет обновления 1 для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="314a6-130">Lync Server 2013 Cumulative Update 1</span></span></p></td>
<td><p><span data-ttu-id="314a6-131">Любой</span><span class="sxs-lookup"><span data-stu-id="314a6-131">Any</span></span></p></td>
<td><p><span data-ttu-id="314a6-132">Нет</span><span class="sxs-lookup"><span data-stu-id="314a6-132">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="314a6-133">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="314a6-133">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="314a6-134">Любой</span><span class="sxs-lookup"><span data-stu-id="314a6-134">Any</span></span></p></td>
<td><p><span data-ttu-id="314a6-135">Нет</span><span class="sxs-lookup"><span data-stu-id="314a6-135">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="314a6-136">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="314a6-136">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="314a6-137">Любой</span><span class="sxs-lookup"><span data-stu-id="314a6-137">Any</span></span></p></td>
<td><p><span data-ttu-id="314a6-138">Нет</span><span class="sxs-lookup"><span data-stu-id="314a6-138">No</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="supported-clients"></a><span data-ttu-id="314a6-139">Поддерживаемые клиенты</span><span class="sxs-lookup"><span data-stu-id="314a6-139">Supported Clients</span></span>

<span data-ttu-id="314a6-140">Клиенты Lync, поддерживающие Location-Basedную маршрутизацию собраний Lync, это те же клиенты, которые поддерживают маршрутизацию Lync Server 2013 Location-Based.</span><span class="sxs-lookup"><span data-stu-id="314a6-140">The Lync clients that support Location-Based Routing of Lync meetings are the same clients that support Lync Server 2013 Location-Based Routing.</span></span> <span data-ttu-id="314a6-141">Для получения дополнительных сведений обратитесь к разделу [Поддержка клиентов и серверов для маршрутизации Location-Based](lync-server-2013-client-and-server-support-for-location-based-routing.md).</span><span class="sxs-lookup"><span data-stu-id="314a6-141">For more information, please refer to [Client and Server Support for Location-Based Routing](lync-server-2013-client-and-server-support-for-location-based-routing.md).</span></span>

</div>

<div>

## <a name="mediation-server-requirements-for-consultative-call-transfers"></a><span data-ttu-id="314a6-142">Требования к серверу-посреднику при передаче вызовов Консультативного</span><span class="sxs-lookup"><span data-stu-id="314a6-142">Mediation Server Requirements for Consultative Call Transfers</span></span>

<span data-ttu-id="314a6-143">Приложение для конференц-связи Location-Based маршрутизации требует развертывания изолированных серверов-посредников для применения Location-Based ограничений маршрутизации при передаче вызовов Консультативного.</span><span class="sxs-lookup"><span data-stu-id="314a6-143">The Location-Based Routing Conferencing application requires deploying stand-alone Mediation Servers in order to enforce Location-Based Routing restrictions on consultative call transfers.</span></span>

<span data-ttu-id="314a6-144">Чтобы обеспечить Location-Based маршрутизацию вызовов консультативного, сервер-посредник должен быть связан только с одним одноранговым узлом сервера-посредником (УАТС, шлюзом SIP и т. д.) в областях сети, где требуется Location-Based маршрутизация.</span><span class="sxs-lookup"><span data-stu-id="314a6-144">To enforce Location-Based Routing of consultative call transfers, the Mediation Server must be associated with only one Mediation Server peer (i.e. PBX, SIP gateway, etc) in network regions where Location-Based Routing is required.</span></span> <span data-ttu-id="314a6-145">Если дополнительные одноранговые серверы-посредники развернуты в одном регионе сети, узел сервера-посредника должен быть связан с другим сервером-посредником.</span><span class="sxs-lookup"><span data-stu-id="314a6-145">If additional Mediation Server peers are deployed in the same network region, the Mediation Server peer must be associated with a different Mediation Server .</span></span> <span data-ttu-id="314a6-146">Ниже приведено описание этого требования.</span><span class="sxs-lookup"><span data-stu-id="314a6-146">This Requirement is detailed as follows:</span></span>

  - <span data-ttu-id="314a6-147">Один сервер-посредник на несколько одноранговых серверов-посредников, когда передача вызовов Консультативного направляется на узел сервера-посредника через сервер-посредник, настроенный на несколько магистральных каналов SIP на несколько одноранговых узлов (то есть УАТС и шлюзы). Передача вызовов Консультативного блокируется, чтобы предотвратить бесплатный звонок по протоколу PSTN, если передача вызовов Консультативного разрешена через некоторые магистральные линии SIP, но запрещены через другие магистральные линии SIP.</span><span class="sxs-lookup"><span data-stu-id="314a6-147">Single Mediation Server per multiple Mediation Server peers When a consultative call transfer is routed to a Mediation Server peer through a Mediation Server that’s configured with multiple SIP trunks to multiple peers (i.e. PBXs and gateways), the consultative call transfer is blocked to prevent PSTN toll bypass if the consultative call transfer is permitted through some SIP trunks but disallowed through other SIP trunks.</span></span>
    
    <span data-ttu-id="314a6-148">Например, в случае одного сервера-посредника, обслуживающего одноранговый сервер-посредник шлюза PSTN и узел сервера-посредника УАТС, будет наблюдаться следующее поведение:</span><span class="sxs-lookup"><span data-stu-id="314a6-148">For example, in the case of a single Mediation Server servicing a PSTN Gateway Mediation Server Peer and a PBX Mediation Server Peer, the following behavior will be observed:</span></span>
    
      - <span data-ttu-id="314a6-149">Если пользователь Lync с определенного сайта (то есть сайт 1) пытается передать вызов с конечной точкой PSTN на пользователя Lync с другого сайта (то есть сайта 2) с помощью передачи консультативного, вызов будет запрещен для предотвращения бесплатных звонков по сети PSTN.</span><span class="sxs-lookup"><span data-stu-id="314a6-149">When a Lync user from a given site (i.e. site 1) attempts to transfer a call with a PSTN endpoint to a Lync user from a different site (i.e. site 2) via consultative transfer, the call will be disallowed to prevent PSTN toll bypass.</span></span>
    
      - <span data-ttu-id="314a6-150">Когда пользователь Lync с определенного сайта (то есть сайт 1) пытается передать вызов с помощью конечной точки УАТС на том же сайте (сайте 1) на другой сайт (например, сайт 2) в Консультативного Transfer, вызов будет запрещен даже в том случае, если он не повлечет за собой потенциального беспроблемного звонка.</span><span class="sxs-lookup"><span data-stu-id="314a6-150">When a Lync user from a given site (i.e. site 1) attempts to transfer a call with a PBX endpoint in the same site (site 1) to a Lync user from a different site (i.e. site 2) via consultative transfer, the call will be disallowed even if it doesn’t incur in potential PSTN toll bypassing.</span></span>

  - <span data-ttu-id="314a6-151">Отдельные серверы-посредники для каждого узла серверов-посредников</span><span class="sxs-lookup"><span data-stu-id="314a6-151">Separate Mediation Servers per Mediation Server peer</span></span>
    
    <span data-ttu-id="314a6-152">Если передача Консультативного нацелена на узел сервера-посредника, то передача Консультативного будет оцениваться относительно одного однорангового сервера-посредника, обслуживаемого сервером-посредником.</span><span class="sxs-lookup"><span data-stu-id="314a6-152">When a consultative transfer is targeted at a Mediation Server Peer, the consultative transfer will be evaluated against the single Mediation Server Peer serviced by the Mediation Server.</span></span> <span data-ttu-id="314a6-153">Вызов будет запрещен или запрещен в соответствии с его потенциалом, который может повлечь за собой невзирая на независимые узлы серверов-посредников, независимо от других серверов-посредников, обслуживаемых отдельными серверами-посредниками.</span><span class="sxs-lookup"><span data-stu-id="314a6-153">The call will be disallowed or allowed based in its potential to incur in PSTN toll bypass regardless of all other Mediations Server Peers in the site as they’re serviced by separate Mediation Servers.</span></span>
    
    <span data-ttu-id="314a6-154">Например, в случае отдельных серверов-посредников, обслуживающих одноранговый сервер-посредник шлюза PSTN и узел сервера-посредника УАТС, будет наблюдаться следующее поведение:</span><span class="sxs-lookup"><span data-stu-id="314a6-154">For example, in the case of a separate Mediation Servers servicing a PSTN Gateway Mediation Server Peer and a PBX Mediation Server Peer, the following behavior will be observed:</span></span>
    
      - <span data-ttu-id="314a6-155">Если пользователь Lync с определенного сайта (то есть сайт 1) пытается передать вызов с конечной точкой PSTN на пользователя Lync с другого сайта (то есть сайта 2) с помощью передачи консультативного, вызов будет запрещен для предотвращения бесплатных звонков по сети PSTN.</span><span class="sxs-lookup"><span data-stu-id="314a6-155">When a Lync user from a given site (i.e. site 1) attempts to transfer a call with a PSTN endpoint to a Lync user from a different site (i.e. site 2) via consultative transfer, the call will be disallowed to prevent PSTN toll bypass.</span></span>
    
      - <span data-ttu-id="314a6-156">Если пользователь Lync с определенного сайта (то есть сайт 1) пытается передать вызов с помощью конечной точки УАТС на том же сайте (сайте 1) на другой сайт (например, сайт 2) с помощью передачи консультативного, вызов будет разрешен, так как он не будет возникать при невозможности обойти потенциальное бесплатный звонок.</span><span class="sxs-lookup"><span data-stu-id="314a6-156">When a Lync user from a given site (i.e. site 1) attempts to transfer a call with a PBX endpoint in the same site (site 1) to a Lync user from a different site (i.e. site 2) via consultative transfer, the call will be allowed as it doesn’t incur in potential PSTN toll bypassing.</span></span>

</div>

<div>

## <a name="capabilities-not-supported-by-the-location-based-routing-conferencing-application"></a><span data-ttu-id="314a6-157">Возможности, не поддерживаемые приложением для конференц-связи Location-Based маршрутизации</span><span class="sxs-lookup"><span data-stu-id="314a6-157">Capabilities Not Supported by the Location-Based Routing Conferencing Application</span></span>

<span data-ttu-id="314a6-158">Приложение для конференц-связи с Location-Based маршрутизации не поддерживает следующие возможности:</span><span class="sxs-lookup"><span data-stu-id="314a6-158">The following capabilities are not supported by the Location-Based Routing Conferencing application:</span></span>

  - <span data-ttu-id="314a6-159">Конференц-связь с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="314a6-159">Dial-in conferencing.</span></span> <span data-ttu-id="314a6-160">Для конференц-связи с телефонным подключением невозможно применять маршрутизацию Location-Based.</span><span class="sxs-lookup"><span data-stu-id="314a6-160">Location-Based Routing cannot be enforced for Dial-in conferencing.</span></span> <span data-ttu-id="314a6-161">Любой запрос на подключение к данной Конференции не будет ограничен Location-Based маршрутизации, даже если организатором конференции является пользователь Lync, поддерживающий маршрутизацию Location-Based.</span><span class="sxs-lookup"><span data-stu-id="314a6-161">Any dial-in request to a given conference will not be restricted by Location-Based Routing even if the conference organizer is a Lync user enabled for Location-Based Routing.</span></span>

  - <span data-ttu-id="314a6-162">Не рекомендуется предоставлять номера доступа к конференциям в регионах, где необходимо применять ограничения маршрутизации Location-Based.</span><span class="sxs-lookup"><span data-stu-id="314a6-162">It’s recommended not to provision conferencing access numbers in regions where Location-Based Routing restrictions need to be enforced.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

