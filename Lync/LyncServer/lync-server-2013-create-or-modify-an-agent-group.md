---
title: 'Lync Server 2013: создание или изменение группы агентов'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify an agent group
ms:assetid: f1461fff-51c1-4f4b-9311-8cba02c333fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205370(v=OCS.15)
ms:contentKeyID: 48185784
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 874b73af42869bc5cbe6a66b7efaf792d231b95d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48525756"
---
# <a name="create-or-modify-an-agent-group-in-lync-server-2013"></a><span data-ttu-id="cc716-102">Создание или изменение группы агентов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cc716-102">Create or modify an agent group in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cc716-103">_**Последнее изменение темы:** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="cc716-103">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="cc716-104">Используйте одну из следующих процедур для создания или изменения группы агентов.</span><span class="sxs-lookup"><span data-stu-id="cc716-104">Use one of the following procedures to create or modify an agent group.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="cc716-105">Администратору (например, CsVoiceAdministrator) необходимо разрешить пользователям использовать корпоративную голосовую связь и Lync Server, прежде чем пользователи смогут назначаться группам агентов.</span><span class="sxs-lookup"><span data-stu-id="cc716-105">An Administrator—for example, CsVoiceAdministrator—must enable users for Enterprise Voice and Lync Server before the users can be assigned to agent groups.</span></span> <span data-ttu-id="cc716-106">Если вы являетесь одним из полномочных менеджеров группы ответа для управляемого рабочего процесса, вы сможете создать группы агентов и использовать их в процессах, которыми управляете.</span><span class="sxs-lookup"><span data-stu-id="cc716-106">If you are one of the delegated Response Group Managers for a managed workflow, you can create agent groups and use the agent groups in the workflows that you manage.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="cc716-p102">При назначении пользователей в качестве агентов группы ответа оповестите их о том, что при включенном режиме конфиденциальности им потребуется выполнить поиск контактов "RGS Presence Watcher" и добавить их в список контактов. Агенты с включенным режимом конфиденциальности и без "RGS Presence Watcher" в списке контактов не могут принимать звонки, направленные в группу ответа. На агентов, у которых режим конфиденциальности отключен, данная особенность не распространяется.</span><span class="sxs-lookup"><span data-stu-id="cc716-p102">When you assign users as response group agents, inform them that, if they have Privacy mode enabled, they need to search for "RGS Presence Watcher" contacts and add them to their Contacts list. Agents who have Privacy mode enabled, but who do not have "RGS Presence Watcher" in their Contacts list, cannot receive calls to the response group. Agents who do not have Privacy mode enabled are not affected.</span></span>



</div>

<div>

## <a name="to-use-lync-server-control-panel-to-create-or-modify-an-agent-group"></a><span data-ttu-id="cc716-110">Создание или изменение группы агентов с помощью панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="cc716-110">To use Lync Server Control Panel to create or modify an agent group</span></span>

1.  <span data-ttu-id="cc716-111">Выполните вход в качестве члена группы RTCUniversalServerAdmins или в качестве участника одной из предварительно заданных административных ролей, поддерживающих группу ответа.</span><span class="sxs-lookup"><span data-stu-id="cc716-111">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="cc716-112">Если вы являетесь одним из полномочных менеджеров группы ответа для управляемого рабочего процесса, вы сможете создать группы и назначить им процессы, которыми вы управляете.</span><span class="sxs-lookup"><span data-stu-id="cc716-112">If you are one of the delegated Response Group Managers for a managed workflow, you can create groups and use them in the workflows that you manage.</span></span>

    
    </div>

2.  <span data-ttu-id="cc716-113">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="cc716-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="cc716-114">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="cc716-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="cc716-115">На левой панели навигации щелкните **Группы ответа**, а затем щелкните **Группа**.</span><span class="sxs-lookup"><span data-stu-id="cc716-115">In the left navigation bar, click **Response Groups**, and then click **Group**.</span></span>

4.  <span data-ttu-id="cc716-116">На странице **Группа** выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="cc716-116">On the **Group** page, do one of the following:</span></span>
    
      - <span data-ttu-id="cc716-p104">Чтобы создать новую группу агентов, щелкните элемент **Создать**. В поле поиска **Выберите услугу** введите полное имя (или часть имени) службы **ApplicationServer**, для которой необходимо добавить группу, щелкните необходимую службу в итоговом списке служб и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="cc716-p104">To create a new agent group, click **New**. In the **Select a Service** search field, type all or part of the name of the **ApplicationServer** service where you want to add the group. In the resulting list of services, click the service that you want, and then click **OK**.</span></span>
    
      - <span data-ttu-id="cc716-p105">Чтобы изменить существующую группу агентов, введите полное имя этой группы агентов или его часть в поле поиска. В итоговом списке выберите необходимую группу, щелкните элемент **Изменить** и элемент **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="cc716-p105">To modify an existing agent group, type all or part of the name of the agent group in the search field. In the resulting list, click the group that you want, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="cc716-122">В поле **Имя** введите определяющее имя для группы агентов.</span><span class="sxs-lookup"><span data-stu-id="cc716-122">In **Name**, type an identifying name for the agent group.</span></span>

6.  <span data-ttu-id="cc716-123">В поле **Описание** введите описание группы.</span><span class="sxs-lookup"><span data-stu-id="cc716-123">In **Description**, type a description for the group.</span></span>

7.  <span data-ttu-id="cc716-124">В разделе **Политика участия** выберите один из следующих параметров для настройки процедуры входа для группы:</span><span class="sxs-lookup"><span data-stu-id="cc716-124">In the **Participation policy**, select one of the following to set up the sign-in behavior for the group:</span></span>
    
      - <span data-ttu-id="cc716-125">Выберите **Неформальное**, чтобы указать, что агентам, входящим в группу, не требуется вход в группу и выход из нее.</span><span class="sxs-lookup"><span data-stu-id="cc716-125">Select **Informal** to specify that agents in the group do not need to sign in and out of the group.</span></span> <span data-ttu-id="cc716-126">Агенты автоматически подписываются в группу при входе в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cc716-126">Agents are automatically signed in to the group when they sign in to Lync Server 2013.</span></span>
    
      - <span data-ttu-id="cc716-127">Выберите **Формальное**, чтобы указать, что агентам, входящим в группу, необходимо выполнять вход в группу и выход из нее.</span><span class="sxs-lookup"><span data-stu-id="cc716-127">Select **Formal** to specify that agents in the group must sign in and out of the group.</span></span> <span data-ttu-id="cc716-128">При выборе этого параметра агенты щелкают элемент меню в Lync для открытия Internet Explorer и отображения консоли веб-страницы для входа и выхода из нее.</span><span class="sxs-lookup"><span data-stu-id="cc716-128">When you select this option, agents click a menu item in Lync to open Internet Explorer and display a webpage console for signing in and out of the group.</span></span>

8.  <span data-ttu-id="cc716-129">В поле **Время оповещения (секунды)** укажите количество секунд, на протяжении которых телефон агента будет звонить, прежде чем другому свободному оператору будет предложено принять вызов (по умолчанию используется время 20 секунд).</span><span class="sxs-lookup"><span data-stu-id="cc716-129">In **Alert time (seconds)**, specify the number of seconds to ring an agent before offering the call to the next available agent (the default is 20 seconds).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="cc716-p108">Значение времени оповещения агента не может превышать 180 секунд; в противном случае клиентское приложение отклонит вызов по причине достижения максимального времени ожидания для таймера операций SIP.</span><span class="sxs-lookup"><span data-stu-id="cc716-p108">The agent alert time setting cannot exceed 180 seconds. If the agent alert time exceeds 180 seconds, the client application rejects the call because the SIP transaction timer reaches its maximum wait time.</span></span>

    
    </div>

9.  <span data-ttu-id="cc716-132">В разделе **Метод маршрутизации** выберите метод маршрутизации вызовов для агентов, входящих в группу, следующим образом:</span><span class="sxs-lookup"><span data-stu-id="cc716-132">In **Routing method**, select the method for routing calls to agents in the group as follows:</span></span>
    
      - <span data-ttu-id="cc716-133">Чтобы создать новый вызов сначала агенту, который находится в неактивном состоянии (на сервере Lync Server он имеет **доступ** или **неактивен** ), выберите значение **длительное время бездействия**.</span><span class="sxs-lookup"><span data-stu-id="cc716-133">To offer a new call first to the agent who has been idle the longest (has had a presence of **Available** or **Inactive** in Lync Server the longest), click **Longest idle**.</span></span>
    
      - <span data-ttu-id="cc716-p109">Чтобы одновременно предлагать новый вызов всем доступным агентам, щелкните **Параллельно**. Вызов направляется первому агенту, который его принимает.</span><span class="sxs-lookup"><span data-stu-id="cc716-p109">To offer a new call to all available agents at the same time, click **Parallel**. The call is sent to the first agent who accepts it.</span></span>
    
      - <span data-ttu-id="cc716-136">Чтобы предлагать новый вызов каждому агенту поочередно, щелкните **Циклический перебор**.</span><span class="sxs-lookup"><span data-stu-id="cc716-136">To offer a new call to each agent in turn, click **Round robin**.</span></span>
    
      - <span data-ttu-id="cc716-137">Чтобы всегда предлагать новый вызов агентам в том порядке, в котором они представлены в списке **Агент**, щелкните **Последовательно**.</span><span class="sxs-lookup"><span data-stu-id="cc716-137">To always offer a new call to the agents in the order in which they are listed in the **Agent** list, click **Serial**.</span></span>
    
      - <span data-ttu-id="cc716-138">Чтобы предоставить новый вызов всем агентам, которые вошли в Lync Server 2013 и приложение группы ответа одновременно, независимо от текущего присутствия, щелкните элемент **помощник**.</span><span class="sxs-lookup"><span data-stu-id="cc716-138">To offer a new call to all agents who are signed into Lync Server 2013 and the Response Group application at the same time, regardless of their current presence, click **Attendant**.</span></span> <span data-ttu-id="cc716-139">Пользователи Lync 2010, настроенные как агенты, могут видеть все вызовы, ожидающие и отвечающие на ожидающие звонки в любом порядке.</span><span class="sxs-lookup"><span data-stu-id="cc716-139">Lync 2010 Attendant users who are configured as agents can see all the calls that are waiting and answer waiting calls in any order.</span></span> <span data-ttu-id="cc716-140">Вызов отправляется первому агенту, который принимает его, после которого другие пользователи Lync 2010 не видят вызов.</span><span class="sxs-lookup"><span data-stu-id="cc716-140">The call is sent to the first agent who accepts it, after which the other Lync 2010 Attendant users no longer see the call.</span></span>

10. <span data-ttu-id="cc716-141">В области **Агенты** определите способ создания списка агентов:</span><span class="sxs-lookup"><span data-stu-id="cc716-141">In **Agents**, specify how you want to create your agents list:</span></span>
    
      - <span data-ttu-id="cc716-142">Чтобы использовать настраиваемый список агентов, щелкните элемент **Определить настраиваемую группу агентов** и выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="cc716-142">To use a custom list of agents, click **Define a custom group of agents**, and do one of the following:</span></span>
        
          - <span data-ttu-id="cc716-p111">Чтобы добавить пользователя в группу агентов, щелкните **Выбрать**, а затем в поле поиска \*\*Выбор агентов \*\* введите имя (полностью или частично) пользователя, которого необходимо добавить в эту группу, после чего щелкните **Найти**. В итоговом списке агентов выберите пользователя, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="cc716-p111">To add a user to the agent group, click **Select**, and then in the **Select Agents** search field, type all or part of the name of the user that you want to add to this group, and then click **Find**. In the resulting list of agents, click the user, and then click **OK**.</span></span>
        
          - <span data-ttu-id="cc716-145">Чтобы удалить пользователя из группы агентов, щелкните этого пользователя в списке агентов и нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="cc716-145">To remove a user from the agent group, in the list of agents, click the user you want to remove, and then click **Remove**.</span></span>
        
          - <span data-ttu-id="cc716-146">Чтобы изменить порядок агентов, в котором им предлагаются звонки в группах с последовательной маршрутизацией или маршрутизацией с циклическим перебором, щелкните агента в списке агентов, а затем нажмите кнопку со стрелкой вверх или вниз.</span><span class="sxs-lookup"><span data-stu-id="cc716-146">To change the order in which agents are offered calls in groups that use either round robin routing or serial routing, in the list of agents, click a user, and then click the up arrow or down arrow.</span></span>
    
      - <span data-ttu-id="cc716-147">Для использования списка рассылки Microsoft Exchange Server в качестве группы агентов щелкните **Использовать существующий список рассылки электронной почты**, а затем введите адрес электронной почты списка рассылки (например, NetworkSupport@contoso.com) в поле **Адрес списка рассылки**.</span><span class="sxs-lookup"><span data-stu-id="cc716-147">To use a Microsoft Exchange Server distribution list as your agent group, click **Use an existing email distribution list**, and then in **Distribution list address**, type the email address of the distribution list (for example, NetworkSupport@contoso.com).</span></span>
        
        <span data-ttu-id="cc716-148">Если вы используете список рассылки по электронной почте, накладываются следующие ограничения:</span><span class="sxs-lookup"><span data-stu-id="cc716-148">If you use an email distribution list, you are subject to the following constraints:</span></span>
        
          - <span data-ttu-id="cc716-p112">Нельзя выбрать несколько списков рассылки для группы агентов. Каждая группа поддерживает только один список рассылки.</span><span class="sxs-lookup"><span data-stu-id="cc716-p112">You cannot select multiple distribution lists for the agent group. Each group supports only a single distribution list.</span></span>
        
          - <span data-ttu-id="cc716-151">Если список рассылки содержит один или несколько списков рассылки, члены вложенных списков рассылки не добавляются в список агентов.</span><span class="sxs-lookup"><span data-stu-id="cc716-151">If the distribution list contains one or more distribution lists, members of the nested distribution lists are not added to the agent list.</span></span>
        
          - <span data-ttu-id="cc716-152">Если выбрана последовательная маршрутизация или маршрутизация с циклическим перебором, сервер предлагает входящий звонок соответствующему агенту в соответствии с методом маршрутизации и порядком, в котором агенты представлены в списке рассылки.</span><span class="sxs-lookup"><span data-stu-id="cc716-152">If serial or round robin routing is selected, the server offers an incoming call to the appropriate agent according to the routing method and according to the order in which agents are listed in the distribution list.</span></span>
        
          - <span data-ttu-id="cc716-153">Если список рассылки содержит пользователей, для которых Lync Server 2010 включен, но Корпоративная голосовая связь не включена, они будут добавлены в группу агентов как агенты неработоспособные.</span><span class="sxs-lookup"><span data-stu-id="cc716-153">If the distribution list contains users for which Lync Server 2010 is enabled but Enterprise Voice is not enabled, they will be added to the agent group as dysfunctional agents.</span></span> <span data-ttu-id="cc716-154">Убедитесь, что для всех участников списка рассылки включена поддержка корпоративной голосовой связи для учетных записей пользователей.</span><span class="sxs-lookup"><span data-stu-id="cc716-154">Make sure that all members of the distribution list have Enterprise Voice enabled for their user accounts.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="cc716-155">Если вы используете список рассылки электронной почты, скрытые члены или скрытые списки могут стать видимыми для администраторов или пользователей группы ответа.</span><span class="sxs-lookup"><span data-stu-id="cc716-155">If you use an email distribution list, hidden memberships or hidden lists might become visible to the Response Group administrator or users.</span></span>

        
        </div>
        
        <span data-ttu-id="cc716-156">Скрытое членство или скрытые списки могут отображаться в следующих случаях:</span><span class="sxs-lookup"><span data-stu-id="cc716-156">Hidden memberships or hidden lists can become visible as follows:</span></span>
        
          - <span data-ttu-id="cc716-157">Если список рассылки был настроен таким образом, что членство скрыто, а администратор группы ответа назначает список рассылки списку агентов, пользователи могут вызвать группу, чтобы узнать, кто является ее участником.</span><span class="sxs-lookup"><span data-stu-id="cc716-157">If a distribution list was configured so that the membership is hidden and the Response Group administrator assigns the distribution list to the agent list, users can call the group to find out who the members are.</span></span>
        
          - <span data-ttu-id="cc716-158">Если список рассылки был настроен таким образом, что он скрыт в глобальном списке адресов Exchange, администратор группы ответа может видеть список рассылки и назначать его списку агентов, если процесс группы ответа имеет соответствующие права и разрешения пользователя, даже если у администратора нет соответствующих прав и разрешений.</span><span class="sxs-lookup"><span data-stu-id="cc716-158">If a distribution list was configured so that it is hidden in the Exchange Global Address List, the Response Group administrator might be able to see the distribution list and assign it to the agent list if the Response Group process has the appropriate user rights and permissions, even if the administrator does not have the appropriate user rights and permissions.</span></span>

11. <span data-ttu-id="cc716-159">Щелкните **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="cc716-159">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-an-agent-group"></a><span data-ttu-id="cc716-160">Использование Windows PowerShell для создания или изменения группы агентов</span><span class="sxs-lookup"><span data-stu-id="cc716-160">To use Windows PowerShell to create or modify an agent group</span></span>

1.  <span data-ttu-id="cc716-161">Выполните вход в качестве члена группы RTCUniversalServerAdmins или в качестве участника одной из предварительно заданных административных ролей, поддерживающих группу ответа.</span><span class="sxs-lookup"><span data-stu-id="cc716-161">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="cc716-162">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="cc716-162">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="cc716-163">Используйте **New-CsRgsAgentGroup** для создания новой группы агентов.</span><span class="sxs-lookup"><span data-stu-id="cc716-163">Use **New-CsRgsAgentGroup** to create a new agent group.</span></span> <span data-ttu-id="cc716-164">Используйте **Set-CsRgsAgentGroup** для изменения существующей группы агентов.</span><span class="sxs-lookup"><span data-stu-id="cc716-164">Use **Set-CsRgsAgentGroup** to modify an existing agent group.</span></span> <span data-ttu-id="cc716-165">В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="cc716-165">At the command line, run:</span></span>
    
        New-CsRgsAgentGroup -Name "<agent group name>" -Parent $serviceId [-Description "<agent group description>"] -[AgentAlertTime <# seconds until call is routed to next agent>] [-ParticipationPolicy <Formal | Informal>] [-RoutingMethod <method for routing calls>] [-AgentsByUri("<first agent's SIP address>","<second agent's SIP address>")];
    
    <span data-ttu-id="cc716-166">Пример:</span><span class="sxs-lookup"><span data-stu-id="cc716-166">For example:</span></span>
    
        New-CsRgsAgentGroup -Name "Help Desk" -Parent "service:ApplicationServer:atl-cs-001.contoso.com"  -Description "Contoso Help Desk" -AgentAlertTime 20 -ParticipationPolicy Formal -RoutingMethod RoundRobin -AgentsByUri("sip:mindy@contoso.com","sip:bob@contoso.com")
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="cc716-p115">Значение времени оповещения агента не может превышать 180 секунд; в противном случае клиентское приложение отклонит вызов по причине достижения максимального времени ожидания для таймера операций SIP.</span><span class="sxs-lookup"><span data-stu-id="cc716-p115">The agent alert time setting cannot exceed 180 seconds. If the agent alert time is greater than 180 seconds, the client application rejects the call because the SIP transaction timer reaches its maximum wait time.</span></span>

    
    </div>

4.  <span data-ttu-id="cc716-p116">Чтобы убедиться, что группа агентов была создана, введите:</span><span class="sxs-lookup"><span data-stu-id="cc716-p116">Confirm that the agent group is created. Run:</span></span>
    
        Get-CsRgsAgentGroup -Name "Help Desk"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="cc716-171">См. также</span><span class="sxs-lookup"><span data-stu-id="cc716-171">See Also</span></span>


[<span data-ttu-id="cc716-172">Удаление группы агентов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cc716-172">Delete an agent group in Lync Server 2013</span></span>](lync-server-2013-delete-an-agent-group.md)  


[<span data-ttu-id="cc716-173">Управление группами агентов группы ответа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cc716-173">Managing Response Group agent groups in Lync Server 2013</span></span>](lync-server-2013-managing-response-group-agent-groups.md)  
[<span data-ttu-id="cc716-174">Get — CsService</span><span class="sxs-lookup"><span data-stu-id="cc716-174">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
[<span data-ttu-id="cc716-175">New — CsRgsAgentGroup</span><span class="sxs-lookup"><span data-stu-id="cc716-175">New-CsRgsAgentGroup</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsAgentGroup)  
[<span data-ttu-id="cc716-176">Set — CsRgsAgentGroup</span><span class="sxs-lookup"><span data-stu-id="cc716-176">Set-CsRgsAgentGroup</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsRgsAgentGroup)  
[<span data-ttu-id="cc716-177">Get — CsRgsAgentGroup</span><span class="sxs-lookup"><span data-stu-id="cc716-177">Get-CsRgsAgentGroup</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsAgentGroup)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

