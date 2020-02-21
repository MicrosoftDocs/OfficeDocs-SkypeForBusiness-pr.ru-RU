---
title: 'Lync Server 2013: обзор приложения группы ответа'
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
ms.openlocfilehash: 007d6b21ab37aee16ae8c98b202bd3900f4dab45
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215865"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-the-response-group-application-in-lync-server-2013"></a><span data-ttu-id="c4ba0-102">Обзор приложения группы ответа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c4ba0-102">Overview of the Response Group application in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c4ba0-103">_**Последнее изменение темы:** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="c4ba0-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="c4ba0-104">Когда вызывающий абонент звонит в группу ответа, этот вызов направляется агенту исходя из сервисной группы или ответов вызывающего абонента на вопросы интерактивного автоответчика (IVR).</span><span class="sxs-lookup"><span data-stu-id="c4ba0-104">When a caller calls a response group, the call is routed to an agent based on a hunt group or the caller's answers to interactive voice response (IVR) questions.</span></span> <span data-ttu-id="c4ba0-105">Приложение группы ответа использует стандартные методы маршрутизации группы ответа для маршрутизации вызова следующему доступному агенту.</span><span class="sxs-lookup"><span data-stu-id="c4ba0-105">The Response Group application uses standard response group routing methods to route the call to the next available agent.</span></span> <span data-ttu-id="c4ba0-106">Методы маршрутизации вызова включают последовательную маршрутизацию, маршрутизацию с наибольшим периодом ожидания, параллельную маршрутизацию, циклическую маршрутизацию и маршрутизацию помощника (когда для каждого входящего вызова все агенты вызываются одновременно, независимо от их присутствия в текущий момент).</span><span class="sxs-lookup"><span data-stu-id="c4ba0-106">Call routing methods include serial, longest-idle, parallel, round robin, and Attendant routing (that is, all agents are called at the same time for every incoming call, regardless of their current presence).</span></span> <span data-ttu-id="c4ba0-107">Если ни один агент не доступен, то вызов удерживается в очереди, пока какой-нибудь агент не освободится.</span><span class="sxs-lookup"><span data-stu-id="c4ba0-107">If no agents are available, the call is held in a queue until an agent is available.</span></span> <span data-ttu-id="c4ba0-108">Находясь в очереди, вызывающий абонент слушает музыку, пока доступный агент не примет вызов.</span><span class="sxs-lookup"><span data-stu-id="c4ba0-108">While in the queue, the caller hears music until an available agent accepts the call.</span></span> <span data-ttu-id="c4ba0-109">Если очередь заполнена, или срок пребывания вызова в очереди истек, то вызывающему абоненту может быть воспроизведено сообщение, а затем он будет либо отключен, либо передан в другое место назначения.</span><span class="sxs-lookup"><span data-stu-id="c4ba0-109">If the queue is full, or if the call times out while in the queue, the caller might hear a message and then is either disconnected or transferred to a different destination.</span></span> <span data-ttu-id="c4ba0-110">Когда агент принимает вызов, то в зависимости от того, как администратор настроил группу ответа, вызывающий абонент может видеть или не видеть удостоверение этого агента.</span><span class="sxs-lookup"><span data-stu-id="c4ba0-110">When an agent accepts the call, the caller might or might not be able to see the agent's identity, depending on how the administrator configures the response group.</span></span> <span data-ttu-id="c4ba0-111">Агенты могут быть либо формальными, что означает, что они должны входить в группу, прежде чем смогут принимать направленные в эту группу вызовы, либо неформальными, что означает, что им не нужно входить в группу или выходить из нее, чтобы принять вызов.</span><span class="sxs-lookup"><span data-stu-id="c4ba0-111">Agents can either be formal, which means that they must sign in to the group before they can accept calls routed to the group, or informal, which means that they do not sign into and out of the group to accept calls.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c4ba0-p102">Агентами могут быть только локальные пользователи. Если агент переходит из локального режима в интерактивный, ему не будут направляться звонки группы ответа.</span><span class="sxs-lookup"><span data-stu-id="c4ba0-p102">Only on-premises users can be agents. If an agent is moved from on-premises to online, Response Group calls will not be routed to that agent.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="c4ba0-114">Приложение группы ответа использует внутреннюю службу, выполнив поиск, чтобы поставить в очередь вызовы и найти доступных агентов.</span><span class="sxs-lookup"><span data-stu-id="c4ba0-114">The Response Group application uses an internal service, called Match Making, to queue calls and find available agents.</span></span> <span data-ttu-id="c4ba0-115">Каждый компьютер, на котором работает приложение группы ответа, запускает службу поиска, но в любой момент времени активным может быть только одна служба поиска на каждом пуле Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c4ba0-115">Each computer that runs the Response Group application runs the Match Making service, but only one Match Making service per Lync Server pool is active at a time--the others are passive.</span></span> <span data-ttu-id="c4ba0-116">Если активная служба Match Making становится недоступной в результате внепланового отключения, то становится активной одна из пассивных служб Match Making.</span><span class="sxs-lookup"><span data-stu-id="c4ba0-116">If the active Match Making service becomes unavailable during an unplanned outage, one of the passive Match Making services becomes active.</span></span> <span data-ttu-id="c4ba0-117">Приложение группы ответа позволяет убедиться, что маршрутизация вызовов и очередь продолжает непрерывно.</span><span class="sxs-lookup"><span data-stu-id="c4ba0-117">The Response Group application does its best to make sure that call routing and queuing continues uninterrupted.</span></span> <span data-ttu-id="c4ba0-118">Однако когда происходит переход службы Match Making, все передаваемые в это время вызовы теряются.</span><span class="sxs-lookup"><span data-stu-id="c4ba0-118">However, when a Match Making service transition occurs, any calls that are in transfer at the time are lost.</span></span> <span data-ttu-id="c4ba0-119">Например, если переход осуществляется из-за сбоя сервера переднего плана, все вызовы, обрабатываемые активной службой проверки на этом сервере переднего плана, также теряются.</span><span class="sxs-lookup"><span data-stu-id="c4ba0-119">For example, if the transition is due to the Front End Server going down, any calls currently being handled by the active Match Making service on that Front End Server are also lost.</span></span>



</div>

<span data-ttu-id="c4ba0-120">В Lync Server 2013 для управления группами ответа доступны две роли управления: Диспетчер группы ответа и администратор группы ответа.</span><span class="sxs-lookup"><span data-stu-id="c4ba0-120">In Lync Server 2013, two management roles are available for managing response groups: Response Group Manager and Response Group Administrator.</span></span> <span data-ttu-id="c4ba0-121">Администраторы группы ответа могут управлять любым аспектом любой группы ответа.</span><span class="sxs-lookup"><span data-stu-id="c4ba0-121">Response Group Administrators can manage any aspect of any response group.</span></span> <span data-ttu-id="c4ba0-122">Менеджеры группы ответа могут управлять только определенными аспектами и только для групп ответа, которыми они владеют.</span><span class="sxs-lookup"><span data-stu-id="c4ba0-122">Response Group Managers can manage only certain aspects, and only for the response groups that they own.</span></span> <span data-ttu-id="c4ba0-123">Новая роль руководителя помогает снизить затраты на администрирование, так как вы можете делегировать ограниченные обязанности для определенных групп ответа любому пользователю, для которого включена поддержка корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="c4ba0-123">The new Manager role can help reduce administration costs, because you can delegate limited responsibilities for specific response groups to any user who is enabled for Enterprise Voice.</span></span>

<span data-ttu-id="c4ba0-124">Для размещения новой роли руководителя приложение группы ответа Lync Server 2013 вводит тип управляемого или неуправляемого **рабочего процесса** .</span><span class="sxs-lookup"><span data-stu-id="c4ba0-124">To accommodate the new Manager role, Lync Server 2013 Response Group application introduces a **Workflow Type** of Managed or Unmanaged.</span></span> <span data-ttu-id="c4ba0-125">В следующей таблице описываются управляемые и неуправляемые группы ответа.</span><span class="sxs-lookup"><span data-stu-id="c4ba0-125">The following table describes Managed and Unmanaged response groups.</span></span>

### <a name="managed-and-unmanaged-response-groups"></a><span data-ttu-id="c4ba0-126">Управляемые и неуправляемые группы ответа</span><span class="sxs-lookup"><span data-stu-id="c4ba0-126">Managed and Unmanaged Response Groups</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c4ba0-127">Тип группы ответа</span><span class="sxs-lookup"><span data-stu-id="c4ba0-127">Response group type</span></span></th>
<th><span data-ttu-id="c4ba0-128">Описание</span><span class="sxs-lookup"><span data-stu-id="c4ba0-128">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c4ba0-129">Неуправляемые</span><span class="sxs-lookup"><span data-stu-id="c4ba0-129">Unmanaged</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="c4ba0-130">Неуправляемые группы ответа не имеют назначенных менеджеров.</span><span class="sxs-lookup"><span data-stu-id="c4ba0-130">Unmanaged response groups have no assigned Managers.</span></span> <span data-ttu-id="c4ba0-131">Только администратор группы ответа может настраивать эти группы ответа.</span><span class="sxs-lookup"><span data-stu-id="c4ba0-131">Only the Response Group Administrator can configure these response groups.</span></span></p></li>
<li><p><span data-ttu-id="c4ba0-132">Несколько неуправляемых групп ответа могут совместно использовать очередь или группу агентов.</span><span class="sxs-lookup"><span data-stu-id="c4ba0-132">Multiple unmanaged response groups can share a queue or agent group.</span></span></p></li>
<li><p><span data-ttu-id="c4ba0-133">При переносе групп ответа из предыдущей версии в Lync Server 2013 для этого типа устанавливается значение "неуправляемый".</span><span class="sxs-lookup"><span data-stu-id="c4ba0-133">When you migrate response groups from a prior version to Lync Server 2013, the type is set to Unmanaged.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4ba0-134">Managed (Управляемая)</span><span class="sxs-lookup"><span data-stu-id="c4ba0-134">Managed</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="c4ba0-135">Администраторы группы ответа могут настраивать любой аспект управляемых групп ответа.</span><span class="sxs-lookup"><span data-stu-id="c4ba0-135">Response Group Administrators can configure any aspect of managed response groups.</span></span></p></li>
<li><p><span data-ttu-id="c4ba0-136">Менеджеры группы ответа не могут просматривать или изменять группы ответа, которые не были явно назначены им.</span><span class="sxs-lookup"><span data-stu-id="c4ba0-136">Response Group Managers cannot view or modify response groups that are not explicitly assigned to them.</span></span></p></li>
<li><p><span data-ttu-id="c4ba0-137">Менеджеры группы ответа могут настраивать только те параметры групп ответа, которые явно назначены им.</span><span class="sxs-lookup"><span data-stu-id="c4ba0-137">Response Group Managers can configure only some settings for the response groups that are explicitly assigned to them.</span></span></p></li>
<li><p><span data-ttu-id="c4ba0-138">Управляемые группы ответа не могут иметь общий доступ к каким-либо очередям или группам агентов с любыми другими группами ответа, управляемыми или неуправляемыми.</span><span class="sxs-lookup"><span data-stu-id="c4ba0-138">Managed response groups can't share any queues or agent groups with any other response group, managed or unmanaged.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c4ba0-139">В следующей таблице описываются действия, которые руководители групп ответа могут и не могут выполнять для групп ответа, назначенных им.</span><span class="sxs-lookup"><span data-stu-id="c4ba0-139">The following table describes the actions that Response Group Managers can and cannot perform for the response groups assigned to them.</span></span>

### <a name="response-group-manager-capabilities"></a><span data-ttu-id="c4ba0-140">Возможности менеджера группы ответа</span><span class="sxs-lookup"><span data-stu-id="c4ba0-140">Response Group Manager Capabilities</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c4ba0-141">Может настраивать:</span><span class="sxs-lookup"><span data-stu-id="c4ba0-141">Can configure:</span></span></th>
<th><span data-ttu-id="c4ba0-142">Может создавать, удалять или настраивать:</span><span class="sxs-lookup"><span data-stu-id="c4ba0-142">Can create, delete, or configure:</span></span></th>
<th><span data-ttu-id="c4ba0-143">Доступ</span><span class="sxs-lookup"><span data-stu-id="c4ba0-143">Cannot:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><ul>
<li><p><span data-ttu-id="c4ba0-144">Агенты</span><span class="sxs-lookup"><span data-stu-id="c4ba0-144">Agents</span></span></p></li>
<li><p><span data-ttu-id="c4ba0-145">Приветственное сообщение</span><span class="sxs-lookup"><span data-stu-id="c4ba0-145">Welcome message</span></span></p></li>
<li><p><span data-ttu-id="c4ba0-146">Имя группы ответа</span><span class="sxs-lookup"><span data-stu-id="c4ba0-146">Response Group name</span></span></p></li>
<li><p><span data-ttu-id="c4ba0-147">Описание</span><span class="sxs-lookup"><span data-stu-id="c4ba0-147">Description</span></span></p></li>
<li><p><span data-ttu-id="c4ba0-148">Отображаемый номер</span><span class="sxs-lookup"><span data-stu-id="c4ba0-148">Display number</span></span></p></li>
<li><p><span data-ttu-id="c4ba0-149">Рабочие часы</span><span class="sxs-lookup"><span data-stu-id="c4ba0-149">Business hours</span></span></p></li>
<li><p><span data-ttu-id="c4ba0-150">Музыка при удержании</span><span class="sxs-lookup"><span data-stu-id="c4ba0-150">Music on hold</span></span></p></li>
<li><p><span data-ttu-id="c4ba0-151">Состояние (активное или неактивное)</span><span class="sxs-lookup"><span data-stu-id="c4ba0-151">Status (active/inactive)</span></span></p></li>
<li><p><span data-ttu-id="c4ba0-152">Рабочие процессы сервисной группы или рабочие процессы интерактивного автоответчика (IVR)</span><span class="sxs-lookup"><span data-stu-id="c4ba0-152">Hunt group workflows or Interactive voice response (IVR) workflows</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="c4ba0-153">Группы агентов</span><span class="sxs-lookup"><span data-stu-id="c4ba0-153">Agent Groups</span></span></p></li>
<li><p><span data-ttu-id="c4ba0-154">Очереди</span><span class="sxs-lookup"><span data-stu-id="c4ba0-154">Queues</span></span></p></li>
<li><p><span data-ttu-id="c4ba0-155">Праздничные дни</span><span class="sxs-lookup"><span data-stu-id="c4ba0-155">Holiday sets</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="c4ba0-156">Создавать или удалять любой тип рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="c4ba0-156">Create or delete any type of workflow</span></span></p></li>
<li><p><span data-ttu-id="c4ba0-157">Изменять основные параметры групп ответа, такие как <strong>SIP URI</strong>, <strong>Telephone Number (Телефонный номер)</strong> или <strong>Workflow Type (Тип рабочего процесса)</strong>.</span><span class="sxs-lookup"><span data-stu-id="c4ba0-157">Modify core response group settings, such as: <strong>SIP URI</strong>, <strong>Telephone Number</strong>, or <strong>Workflow Type</strong>.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c4ba0-158">Менеджеры групп ответа могут использовать следующие средства для управления назначенными группами ответа.</span><span class="sxs-lookup"><span data-stu-id="c4ba0-158">Response Group Managers can use the following tools to manage their designated response groups.</span></span>

  - <span data-ttu-id="c4ba0-159">Панель управления сервера Lync</span><span class="sxs-lookup"><span data-stu-id="c4ba0-159">Lync Server Control Panel</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c4ba0-160">Менеджеры группы ответа могут управлять параметрами группы ответа только с помощью этого средства.</span><span class="sxs-lookup"><span data-stu-id="c4ba0-160">Response Group Managers can only manage Response Group settings with this tool.</span></span> <span data-ttu-id="c4ba0-161">Другие параметры Lync Server недоступны руководителям.</span><span class="sxs-lookup"><span data-stu-id="c4ba0-161">Other Lync Server settings are not available to Managers.</span></span>

    
    </div>

  - <span data-ttu-id="c4ba0-162">Средство настройки группы ответа</span><span class="sxs-lookup"><span data-stu-id="c4ba0-162">Response Group Configuration Tool</span></span>

  - <span data-ttu-id="c4ba0-163">Командная консоль Lync Server</span><span class="sxs-lookup"><span data-stu-id="c4ba0-163">Lync Server Management Shell</span></span>

<span data-ttu-id="c4ba0-164">Группа ответа хорошо масштабируется в среде отдела или рабочей группы (Дополнительные сведения см. в статье [планирование емкости для группы ответа в Lync Server 2013](lync-server-2013-capacity-planning-for-response-group.md)) и могут быть развернуты полностью в новых установках телефонии.</span><span class="sxs-lookup"><span data-stu-id="c4ba0-164">Response Group scales well to departmental or workgroup environments (for details, see [Capacity planning for Response Group in Lync Server 2013](lync-server-2013-capacity-planning-for-response-group.md)) and can be deployed in entirely new telephony installations.</span></span> <span data-ttu-id="c4ba0-165">Он поддерживает входящие вызовы из развертывания корпоративной голосовой связи и из локальной сети перевозчика.</span><span class="sxs-lookup"><span data-stu-id="c4ba0-165">It supports incoming calls from the Enterprise Voice deployment and from the local carrier network.</span></span> <span data-ttu-id="c4ba0-166">Агенты могут использовать Lync 2013, Lync 2010, Lync 2010 Attendant или Lync Phone Edition, чтобы совершать вызовы, направляемые им.</span><span class="sxs-lookup"><span data-stu-id="c4ba0-166">Agents can use Lync 2013, Lync 2010, Lync 2010 Attendant, or Lync Phone Edition to take the calls routed to them.</span></span>

<span data-ttu-id="c4ba0-167">Приложение группы ответа является компонентом корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="c4ba0-167">The Response Group application is a component of Enterprise Voice.</span></span> <span data-ttu-id="c4ba0-168">При развертывании корпоративной голосовой связи приложение группы ответа устанавливается и активируется автоматически.</span><span class="sxs-lookup"><span data-stu-id="c4ba0-168">When you deploy Enterprise Voice, the Response Group application is installed and activated automatically.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

