---
title: 'Lync Server 2013: Общие сведения о приложении группы ответа'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of the Response Group application
ms:assetid: 6cc333e7-4029-4372-86b2-016040c415fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398513(v=OCS.15)
ms:contentKeyID: 48184453
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2b01181296a42f786a4739b5ec59d775212baaf5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755423"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-the-response-group-application-in-lync-server-2013"></a><span data-ttu-id="e92a7-102">Общие сведения о приложении "группа ответа" в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e92a7-102">Overview of the Response Group application in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e92a7-103">_**Тема последнего изменения:** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="e92a7-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="e92a7-104">Когда вызывающий абонент звонит в группу ответа, этот вызов направляется агенту, основываясь на сервисной группы или ответах вызывающего абонента на вопросы интерактивного автоответчика (IVR).</span><span class="sxs-lookup"><span data-stu-id="e92a7-104">When a caller calls a response group, the call is routed to an agent based on a hunt group or the caller's answers to interactive voice response (IVR) questions.</span></span> <span data-ttu-id="e92a7-105">Приложение группы ответа использует стандартные методы маршрутизации групп ответа, чтобы направить Звонок на следующий доступный агент.</span><span class="sxs-lookup"><span data-stu-id="e92a7-105">The Response Group application uses standard response group routing methods to route the call to the next available agent.</span></span> <span data-ttu-id="e92a7-106">К методам маршрутизации звонков относятся последовательные, самые продолжительные, незанятые, параллельные и циклические маршруты (то есть все агенты вызываются одновременно для каждого входящего звонка, независимо от их текущего присутствия).</span><span class="sxs-lookup"><span data-stu-id="e92a7-106">Call routing methods include serial, longest-idle, parallel, round robin, and Attendant routing (that is, all agents are called at the same time for every incoming call, regardless of their current presence).</span></span> <span data-ttu-id="e92a7-107">Если агенты недоступны, вызов удерживается в очереди, пока не будет доступен агент.</span><span class="sxs-lookup"><span data-stu-id="e92a7-107">If no agents are available, the call is held in a queue until an agent is available.</span></span> <span data-ttu-id="e92a7-108">Находясь в очереди, вызывающий абонент слышит музыку, пока доступный агент не примет звонок.</span><span class="sxs-lookup"><span data-stu-id="e92a7-108">While in the queue, the caller hears music until an available agent accepts the call.</span></span> <span data-ttu-id="e92a7-109">Если очередь заполнена или истекает время ожидания в очереди, вызывающий абонент может услышать сообщение, а затем либо отсоединено, либо передавалось в другое место назначения.</span><span class="sxs-lookup"><span data-stu-id="e92a7-109">If the queue is full, or if the call times out while in the queue, the caller might hear a message and then is either disconnected or transferred to a different destination.</span></span> <span data-ttu-id="e92a7-110">Когда агент принимает звонок, вызывающий абонент может, в зависимости от того, как администратор настроил группу ответа, мог или не может видеть его удостоверение.</span><span class="sxs-lookup"><span data-stu-id="e92a7-110">When an agent accepts the call, the caller might or might not be able to see the agent's identity, depending on how the administrator configures the response group.</span></span> <span data-ttu-id="e92a7-111">Агенты могут быть формально, что означает, что они должны входить в группу, прежде чем они смогут принимать звонки, перенаправляемые группе, или как неформальные, что означает, что они не будут входить в группу и принимать звонки.</span><span class="sxs-lookup"><span data-stu-id="e92a7-111">Agents can either be formal, which means that they must sign in to the group before they can accept calls routed to the group, or informal, which means that they do not sign into and out of the group to accept calls.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e92a7-112">Агентами могут быть только локальные пользователи.</span><span class="sxs-lookup"><span data-stu-id="e92a7-112">Only on-premises users can be agents.</span></span> <span data-ttu-id="e92a7-113">Если агент перемещается из локальной сети в Online, звонки групп ответов не будут маршрутизироваться этому агенту.</span><span class="sxs-lookup"><span data-stu-id="e92a7-113">If an agent is moved from on-premises to online, Response Group calls will not be routed to that agent.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="e92a7-114">Приложение "группа ответа" использует внутреннюю службу, которая называется созданием соответствия, выставить очередь звонков и находить доступные агенты.</span><span class="sxs-lookup"><span data-stu-id="e92a7-114">The Response Group application uses an internal service, called Match Making, to queue calls and find available agents.</span></span> <span data-ttu-id="e92a7-115">Каждый компьютер, на котором запущено приложение группы ответа, запускает службу поиска совпадений, но в каждый момент времени активен только один из них, позволяющий выполнять обслуживание на каждом пуле Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e92a7-115">Each computer that runs the Response Group application runs the Match Making service, but only one Match Making service per Lync Server pool is active at a time--the others are passive.</span></span> <span data-ttu-id="e92a7-116">Если активная служба установления соответствий оказывается недоступной во время внепланового отключения, то становится активной одна из пассивных служб установления соответствий.</span><span class="sxs-lookup"><span data-stu-id="e92a7-116">If the active Match Making service becomes unavailable during an unplanned outage, one of the passive Match Making services becomes active.</span></span> <span data-ttu-id="e92a7-117">Приложение "группа ответа" — это лучший способ гарантировать, что маршрутизация вызовов и очередь продолжает быть прервана.</span><span class="sxs-lookup"><span data-stu-id="e92a7-117">The Response Group application does its best to make sure that call routing and queuing continues uninterrupted.</span></span> <span data-ttu-id="e92a7-118">Однако, когда происходит переход службы установления соответствий, все передаваемые в это время вызовы теряются.</span><span class="sxs-lookup"><span data-stu-id="e92a7-118">However, when a Match Making service transition occurs, any calls that are in transfer at the time are lost.</span></span> <span data-ttu-id="e92a7-119">Например, если переход происходит из-за того, что сервер переднего плана отключается, все вызовы, которые в настоящее время обрабатываются службой на этом внешнем сервере, будут потеряны.</span><span class="sxs-lookup"><span data-stu-id="e92a7-119">For example, if the transition is due to the Front End Server going down, any calls currently being handled by the active Match Making service on that Front End Server are also lost.</span></span>



</div>

<span data-ttu-id="e92a7-120">В Lync Server 2013 для управления группами ответа доступны две роли управления: Диспетчер групп ответов и администратор групп ответов.</span><span class="sxs-lookup"><span data-stu-id="e92a7-120">In Lync Server 2013, two management roles are available for managing response groups: Response Group Manager and Response Group Administrator.</span></span> <span data-ttu-id="e92a7-121">Администраторы групп ответа могут управлять любым аспектом любой группы ответа.</span><span class="sxs-lookup"><span data-stu-id="e92a7-121">Response Group Administrators can manage any aspect of any response group.</span></span> <span data-ttu-id="e92a7-122">Руководители групп ответа могут управлять только определенными аспектами и только для групп ответов, которым они принадлежат.</span><span class="sxs-lookup"><span data-stu-id="e92a7-122">Response Group Managers can manage only certain aspects, and only for the response groups that they own.</span></span> <span data-ttu-id="e92a7-123">Новая роль руководителя помогает сократить расходы на администрирование, так как вы можете делегировать ограниченные обязанности конкретным группам ответов любому пользователю, которому разрешено пользоваться корпоративной голосовой связью.</span><span class="sxs-lookup"><span data-stu-id="e92a7-123">The new Manager role can help reduce administration costs, because you can delegate limited responsibilities for specific response groups to any user who is enabled for Enterprise Voice.</span></span>

<span data-ttu-id="e92a7-124">Для размещения новой роли руководителя приложение "группа ответа" Lync Server 2013 вводит **тип рабочего процесса** управляемого или неуправляемого.</span><span class="sxs-lookup"><span data-stu-id="e92a7-124">To accommodate the new Manager role, Lync Server 2013 Response Group application introduces a **Workflow Type** of Managed or Unmanaged.</span></span> <span data-ttu-id="e92a7-125">В следующей таблице представлены управляемые и неуправляемые группы ответа.</span><span class="sxs-lookup"><span data-stu-id="e92a7-125">The following table describes Managed and Unmanaged response groups.</span></span>

### <a name="managed-and-unmanaged-response-groups"></a><span data-ttu-id="e92a7-126">Управляемые и неуправляемые группы ответа</span><span class="sxs-lookup"><span data-stu-id="e92a7-126">Managed and Unmanaged Response Groups</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e92a7-127">Тип группы ответа</span><span class="sxs-lookup"><span data-stu-id="e92a7-127">Response group type</span></span></th>
<th><span data-ttu-id="e92a7-128">Описание</span><span class="sxs-lookup"><span data-stu-id="e92a7-128">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e92a7-129">Неуправляемая</span><span class="sxs-lookup"><span data-stu-id="e92a7-129">Unmanaged</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="e92a7-130">Неуправляемые группы ответа не имеют назначенных диспетчеров.</span><span class="sxs-lookup"><span data-stu-id="e92a7-130">Unmanaged response groups have no assigned Managers.</span></span> <span data-ttu-id="e92a7-131">Настраивать эти группы ответа может только администратор группы ответа.</span><span class="sxs-lookup"><span data-stu-id="e92a7-131">Only the Response Group Administrator can configure these response groups.</span></span></p></li>
<li><p><span data-ttu-id="e92a7-132">Несколько неуправляемых групп ответа могут совместно использовать очередь или группу агентов.</span><span class="sxs-lookup"><span data-stu-id="e92a7-132">Multiple unmanaged response groups can share a queue or agent group.</span></span></p></li>
<li><p><span data-ttu-id="e92a7-133">При миграции групп ответов из предыдущей версии в Lync Server 2013 для этого типа устанавливается значение неуправляемый.</span><span class="sxs-lookup"><span data-stu-id="e92a7-133">When you migrate response groups from a prior version to Lync Server 2013, the type is set to Unmanaged.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e92a7-134">Управляемая</span><span class="sxs-lookup"><span data-stu-id="e92a7-134">Managed</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="e92a7-135">Администраторы групп ответа могут настраивать любой аспект управляемых групп ответа.</span><span class="sxs-lookup"><span data-stu-id="e92a7-135">Response Group Administrators can configure any aspect of managed response groups.</span></span></p></li>
<li><p><span data-ttu-id="e92a7-136">Руководители групп ответа не могут просматривать или изменять группы ответа, которым они не назначены явным образом.</span><span class="sxs-lookup"><span data-stu-id="e92a7-136">Response Group Managers cannot view or modify response groups that are not explicitly assigned to them.</span></span></p></li>
<li><p><span data-ttu-id="e92a7-137">Руководители групп ответа могут настраивать только некоторые параметры для групп ответа, которым они назначены явным образом.</span><span class="sxs-lookup"><span data-stu-id="e92a7-137">Response Group Managers can configure only some settings for the response groups that are explicitly assigned to them.</span></span></p></li>
<li><p><span data-ttu-id="e92a7-138">Управляемые группы ответа не могут иметь общий доступ к каким-либо очередям или группам агентов с любыми другими группами ответа, управляемыми или неуправляемыми.</span><span class="sxs-lookup"><span data-stu-id="e92a7-138">Managed response groups can't share any queues or agent groups with any other response group, managed or unmanaged.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<span data-ttu-id="e92a7-139">В приведенной ниже таблице описаны действия, которые руководители групп ответов могут и не могут выполнить для групп ответа, которым они назначены.</span><span class="sxs-lookup"><span data-stu-id="e92a7-139">The following table describes the actions that Response Group Managers can and cannot perform for the response groups assigned to them.</span></span>

### <a name="response-group-manager-capabilities"></a><span data-ttu-id="e92a7-140">Возможности диспетчера группы ответа</span><span class="sxs-lookup"><span data-stu-id="e92a7-140">Response Group Manager Capabilities</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e92a7-141">Может настраивать:</span><span class="sxs-lookup"><span data-stu-id="e92a7-141">Can configure:</span></span></th>
<th><span data-ttu-id="e92a7-142">Может создавать, удалять или настраивать:</span><span class="sxs-lookup"><span data-stu-id="e92a7-142">Can create, delete, or configure:</span></span></th>
<th><span data-ttu-id="e92a7-143">Не может:</span><span class="sxs-lookup"><span data-stu-id="e92a7-143">Cannot:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><ul>
<li><p><span data-ttu-id="e92a7-144">Агенты</span><span class="sxs-lookup"><span data-stu-id="e92a7-144">Agents</span></span></p></li>
<li><p><span data-ttu-id="e92a7-145">Приветственное сообщение</span><span class="sxs-lookup"><span data-stu-id="e92a7-145">Welcome message</span></span></p></li>
<li><p><span data-ttu-id="e92a7-146">Имя группы ответа</span><span class="sxs-lookup"><span data-stu-id="e92a7-146">Response Group name</span></span></p></li>
<li><p><span data-ttu-id="e92a7-147">Описание</span><span class="sxs-lookup"><span data-stu-id="e92a7-147">Description</span></span></p></li>
<li><p><span data-ttu-id="e92a7-148">Отображаемый номер</span><span class="sxs-lookup"><span data-stu-id="e92a7-148">Display number</span></span></p></li>
<li><p><span data-ttu-id="e92a7-149">Рабочие часы</span><span class="sxs-lookup"><span data-stu-id="e92a7-149">Business hours</span></span></p></li>
<li><p><span data-ttu-id="e92a7-150">Музыка при удержании</span><span class="sxs-lookup"><span data-stu-id="e92a7-150">Music on hold</span></span></p></li>
<li><p><span data-ttu-id="e92a7-151">Состояние (активное или неактивное)</span><span class="sxs-lookup"><span data-stu-id="e92a7-151">Status (active/inactive)</span></span></p></li>
<li><p><span data-ttu-id="e92a7-152">Рабочие процессы сервисной группы или рабочие процессы интерактивного автоответчика (IVR)</span><span class="sxs-lookup"><span data-stu-id="e92a7-152">Hunt group workflows or Interactive voice response (IVR) workflows</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="e92a7-153">Группы агентов</span><span class="sxs-lookup"><span data-stu-id="e92a7-153">Agent Groups</span></span></p></li>
<li><p><span data-ttu-id="e92a7-154">Очереди</span><span class="sxs-lookup"><span data-stu-id="e92a7-154">Queues</span></span></p></li>
<li><p><span data-ttu-id="e92a7-155">Праздничные дни</span><span class="sxs-lookup"><span data-stu-id="e92a7-155">Holiday sets</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="e92a7-156">Создавать или удалять любой тип рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="e92a7-156">Create or delete any type of workflow</span></span></p></li>
<li><p><span data-ttu-id="e92a7-157">Вносить изменения в основные параметры групп ответа, такие как <strong>SIP URI</strong>, <strong>Номер телефона</strong> или <strong>Тип рабочего процесса</strong>.</span><span class="sxs-lookup"><span data-stu-id="e92a7-157">Modify core response group settings, such as: <strong>SIP URI</strong>, <strong>Telephone Number</strong>, or <strong>Workflow Type</strong>.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<span data-ttu-id="e92a7-158">Для управления назначенными группами ответов Диспетчер групп ответов может использовать указанные ниже инструменты.</span><span class="sxs-lookup"><span data-stu-id="e92a7-158">Response Group Managers can use the following tools to manage their designated response groups.</span></span>

  - <span data-ttu-id="e92a7-159">Панель управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="e92a7-159">Lync Server Control Panel</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e92a7-160">Диспетчер групп ответов может управлять параметрами группы ответа только с помощью этого инструмента.</span><span class="sxs-lookup"><span data-stu-id="e92a7-160">Response Group Managers can only manage Response Group settings with this tool.</span></span> <span data-ttu-id="e92a7-161">Другие параметры сервера Lync недоступны для руководителей.</span><span class="sxs-lookup"><span data-stu-id="e92a7-161">Other Lync Server settings are not available to Managers.</span></span>

    
    </div>

  - <span data-ttu-id="e92a7-162">настройки группы ответа</span><span class="sxs-lookup"><span data-stu-id="e92a7-162">Response Group Configuration Tool</span></span>

  - <span data-ttu-id="e92a7-163">Командная консоль Lync Server</span><span class="sxs-lookup"><span data-stu-id="e92a7-163">Lync Server Management Shell</span></span>

<span data-ttu-id="e92a7-164">Группа ответа удобна для сред отделов или рабочих групп (Дополнительные сведения можно найти в разделе [Планирование производительности для группы ответа в Lync Server 2013](lync-server-2013-capacity-planning-for-response-group.md)) и при развертывании в полностью новой версии телефонной связи.</span><span class="sxs-lookup"><span data-stu-id="e92a7-164">Response Group scales well to departmental or workgroup environments (for details, see [Capacity planning for Response Group in Lync Server 2013](lync-server-2013-capacity-planning-for-response-group.md)) and can be deployed in entirely new telephony installations.</span></span> <span data-ttu-id="e92a7-165">Она поддерживает входящие звонки из корпоративной голосовой разгрузки и из локальной сети перевозчика.</span><span class="sxs-lookup"><span data-stu-id="e92a7-165">It supports incoming calls from the Enterprise Voice deployment and from the local carrier network.</span></span> <span data-ttu-id="e92a7-166">Агенты могут использовать Lync 2013, Lync 2010, Lync 2010 или Lync Phone Edition, чтобы принимать звонки, направляемые им.</span><span class="sxs-lookup"><span data-stu-id="e92a7-166">Agents can use Lync 2013, Lync 2010, Lync 2010 Attendant, or Lync Phone Edition to take the calls routed to them.</span></span>

<span data-ttu-id="e92a7-167">Приложение группы ответа — это компонент корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="e92a7-167">The Response Group application is a component of Enterprise Voice.</span></span> <span data-ttu-id="e92a7-168">При развертывании корпоративной голосовой связи приложение группы ответа устанавливается и активируется автоматически.</span><span class="sxs-lookup"><span data-stu-id="e92a7-168">When you deploy Enterprise Voice, the Response Group application is installed and activated automatically.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

