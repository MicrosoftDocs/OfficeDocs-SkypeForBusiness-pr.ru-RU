---
title: 'Lync Server 2013: создание или изменение группы агента'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify an agent group
ms:assetid: f1461fff-51c1-4f4b-9311-8cba02c333fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205370(v=OCS.15)
ms:contentKeyID: 48185784
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0a2765e9ba72501b148e61d0d38789a46b2c3bc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834789"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-an-agent-group-in-lync-server-2013"></a><span data-ttu-id="1ef83-102">Создание или изменение группы агента в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ef83-102">Create or modify an agent group in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1ef83-103">_**Тема последнего изменения:** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="1ef83-103">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="1ef83-104">Используйте одну из следующих процедур для создания или изменения группы агентов.</span><span class="sxs-lookup"><span data-stu-id="1ef83-104">Use one of the following procedures to create or modify an agent group.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1ef83-105">Администратор (например, Ксвоицеадминистратор) должен включить пользователей для корпоративной голосовой связи и Lync Server, прежде чем пользователи смогут назначаться группам агента.</span><span class="sxs-lookup"><span data-stu-id="1ef83-105">An Administrator—for example, CsVoiceAdministrator—must enable users for Enterprise Voice and Lync Server before the users can be assigned to agent groups.</span></span> <span data-ttu-id="1ef83-106">Если вы являетесь одним из руководителей делегированных групп ответа на управляемый рабочий процесс, вы можете создать группы агентов и использовать группы агентов в рабочих процессах, которыми вы управляете.</span><span class="sxs-lookup"><span data-stu-id="1ef83-106">If you are one of the delegated Response Group Managers for a managed workflow, you can create agent groups and use the agent groups in the workflows that you manage.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="1ef83-p102">При назначении пользователей в качестве агентов группы ответа оповестите их о том, что при включенном режиме конфиденциальности им потребуется выполнить поиск контактов "RGS Presence Watcher" и добавить их в список контактов. Агенты с включенным режимом конфиденциальности и без "RGS Presence Watcher" в списке контактов не могут принимать звонки, направленные в группу ответа. На агентов, у которых режим конфиденциальности отключен, данная особенность не распространяется.</span><span class="sxs-lookup"><span data-stu-id="1ef83-p102">When you assign users as response group agents, inform them that, if they have Privacy mode enabled, they need to search for "RGS Presence Watcher" contacts and add them to their Contacts list. Agents who have Privacy mode enabled, but who do not have "RGS Presence Watcher" in their Contacts list, cannot receive calls to the response group. Agents who do not have Privacy mode enabled are not affected.</span></span>



</div>

<div>

## <a name="to-use-lync-server-control-panel-to-create-or-modify-an-agent-group"></a><span data-ttu-id="1ef83-110">Создание и изменение группы агента с помощью панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="1ef83-110">To use Lync Server Control Panel to create or modify an agent group</span></span>

1.  <span data-ttu-id="1ef83-111">Выполните вход как член группы RTCUniversalServerAdmins или одной из предварительно заданных административных ролей, поддерживающих группу ответа.</span><span class="sxs-lookup"><span data-stu-id="1ef83-111">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1ef83-112">Если вы являетесь одним из полномочных менеджеров группы ответа для управляемого рабочего процесса, вы сможете создать группы и назначить им процессы, которыми вы управляете.</span><span class="sxs-lookup"><span data-stu-id="1ef83-112">If you are one of the delegated Response Group Managers for a managed workflow, you can create groups and use them in the workflows that you manage.</span></span>

    
    </div>

2.  <span data-ttu-id="1ef83-113">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1ef83-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="1ef83-114">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="1ef83-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="1ef83-115">В левой области навигации щелкните **Группы ответа**, затем **Группа**.</span><span class="sxs-lookup"><span data-stu-id="1ef83-115">In the left navigation bar, click **Response Groups**, and then click **Group**.</span></span>

4.  <span data-ttu-id="1ef83-116">На странице **Группа** выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="1ef83-116">On the **Group** page, do one of the following:</span></span>
    
      - <span data-ttu-id="1ef83-p104">Для создания новой группы агентов щелкните **Создать**. В поле поиска **Выбор службы** полностью или частично введите имя службы **ApplicationServer**, для которой необходимо добавить группу. В сформированном списке служб щелкните требуемую службу, затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="1ef83-p104">To create a new agent group, click **New**. In the **Select a Service** search field, type all or part of the name of the **ApplicationServer** service where you want to add the group. In the resulting list of services, click the service that you want, and then click **OK**.</span></span>
    
      - <span data-ttu-id="1ef83-p105">Для изменения существующей группы агентов полностью или частично введите ее имя в поле поиска. В сформированном списке щелкните требуемую группу и нажмите кнопку **Изменить**, затем **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="1ef83-p105">To modify an existing agent group, type all or part of the name of the agent group in the search field. In the resulting list, click the group that you want, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="1ef83-122">В поле **Имя** введите имя, определяющее группу агентов.</span><span class="sxs-lookup"><span data-stu-id="1ef83-122">In **Name**, type an identifying name for the agent group.</span></span>

6.  <span data-ttu-id="1ef83-123">В поле **Описание** введите описание группы.</span><span class="sxs-lookup"><span data-stu-id="1ef83-123">In **Description**, type a description for the group.</span></span>

7.  <span data-ttu-id="1ef83-124">В разделе **Политика участия** выберите один из следующих режимов входа в группу.</span><span class="sxs-lookup"><span data-stu-id="1ef83-124">In the **Participation policy**, select one of the following to set up the sign-in behavior for the group:</span></span>
    
      - <span data-ttu-id="1ef83-125">Если выбран режим **Свободная**, агентам не требуется входить в группу и выходить из нее.</span><span class="sxs-lookup"><span data-stu-id="1ef83-125">Select **Informal** to specify that agents in the group do not need to sign in and out of the group.</span></span> <span data-ttu-id="1ef83-126">Агенты автоматически подписываются в группу при входе в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1ef83-126">Agents are automatically signed in to the group when they sign in to Lync Server 2013.</span></span>
    
      - <span data-ttu-id="1ef83-127">Если выбран режим **Строгая**, агентам необходимо входить в группу и выходить из нее.</span><span class="sxs-lookup"><span data-stu-id="1ef83-127">Select **Formal** to specify that agents in the group must sign in and out of the group.</span></span> <span data-ttu-id="1ef83-128">Если выбрать этот параметр, агенты щелкают элемент меню в Lync, чтобы открыть Internet Explorer и отобразить консоль веб-страницы для входа и выхода из нее.</span><span class="sxs-lookup"><span data-stu-id="1ef83-128">When you select this option, agents click a menu item in Lync to open Internet Explorer and display a webpage console for signing in and out of the group.</span></span>

8.  <span data-ttu-id="1ef83-129">В поле **Время предупреждения (в секундах)** укажите продолжительность звукового сигнала вызова на телефоне агента в секундах (по умолчанию: 20 секунд). По истечении указанного времени принять вызов предлагается следующему свободному оператору.</span><span class="sxs-lookup"><span data-stu-id="1ef83-129">In **Alert time (seconds)**, specify the number of seconds to ring an agent before offering the call to the next available agent (the default is 20 seconds).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="1ef83-p108">Значение времени оповещения агента не может превышать 180 секунд; в противном случае клиентское приложение отклонит вызов по причине достижения максимального времени ожидания для таймера операций SIP.</span><span class="sxs-lookup"><span data-stu-id="1ef83-p108">The agent alert time setting cannot exceed 180 seconds. If the agent alert time exceeds 180 seconds, the client application rejects the call because the SIP transaction timer reaches its maximum wait time.</span></span>

    
    </div>

9.  <span data-ttu-id="1ef83-132">В разделе **Метод маршрутизации** выберите способ направления вызовов агентам в группе, выполнив следующие действия.</span><span class="sxs-lookup"><span data-stu-id="1ef83-132">In **Routing method**, select the method for routing calls to agents in the group as follows:</span></span>
    
      - <span data-ttu-id="1ef83-133">Чтобы предложить новый звонок, прежде чем агент, использующий незанятый (он имел доступное или \*\*\*\* неактивное в Lync Server), выберите пункт в **течение длительного периода бездействия**. \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="1ef83-133">To offer a new call first to the agent who has been idle the longest (has had a presence of **Available** or **Inactive** in Lync Server the longest), click **Longest idle**.</span></span>
    
      - <span data-ttu-id="1ef83-p109">Если требуется одновременно предлагать принять новый вызов всем свободным агентам, щелкните **Параллельно**. Вызов направляется первому агенту, который его принимает.</span><span class="sxs-lookup"><span data-stu-id="1ef83-p109">To offer a new call to all available agents at the same time, click **Parallel**. The call is sent to the first agent who accepts it.</span></span>
    
      - <span data-ttu-id="1ef83-136">Если требуется одновременно предлагать принять новый вызов каждому агенту поочередно, щелкните **Циклический перебор**.</span><span class="sxs-lookup"><span data-stu-id="1ef83-136">To offer a new call to each agent in turn, click **Round robin**.</span></span>
    
      - <span data-ttu-id="1ef83-137">Если требуется всегда предлагать принять новый вызов агентам в том порядке, в котором они представлены в списке **Агент**, щелкните **Последовательно**.</span><span class="sxs-lookup"><span data-stu-id="1ef83-137">To always offer a new call to the agents in the order in which they are listed in the **Agent** list, click **Serial**.</span></span>
    
      - <span data-ttu-id="1ef83-138">Чтобы предложить новый звонок всем агентам, которые вошли в Lync Server 2013 и приложение группы ответа одновременно, независимо от их текущего присутствия, выберите элемент **участие**.</span><span class="sxs-lookup"><span data-stu-id="1ef83-138">To offer a new call to all agents who are signed into Lync Server 2013 and the Response Group application at the same time, regardless of their current presence, click **Attendant**.</span></span> <span data-ttu-id="1ef83-139">Пользователи Lync 2010, настроенные как агенты, могут просматривать все звонки, ожидающие звонка, и отвечать на них в любом порядке.</span><span class="sxs-lookup"><span data-stu-id="1ef83-139">Lync 2010 Attendant users who are configured as agents can see all the calls that are waiting and answer waiting calls in any order.</span></span> <span data-ttu-id="1ef83-140">Вызов отправляется первому агенту, принимающему его, после которого другие пользователи Lync 2010 больше не будут видеть этот звонок.</span><span class="sxs-lookup"><span data-stu-id="1ef83-140">The call is sent to the first agent who accepts it, after which the other Lync 2010 Attendant users no longer see the call.</span></span>

10. <span data-ttu-id="1ef83-141">В разделе **Агенты** укажите вариант создания списка агентов.</span><span class="sxs-lookup"><span data-stu-id="1ef83-141">In **Agents**, specify how you want to create your agents list:</span></span>
    
      - <span data-ttu-id="1ef83-142">Для создания пользовательского списка агентов щелкните **Определить настраиваемую группу агентов** и выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="1ef83-142">To use a custom list of agents, click **Define a custom group of agents**, and do one of the following:</span></span>
        
          - <span data-ttu-id="1ef83-p111">Для добавления пользователя к группе агентов щелкните **Выбрать**, затем в поле поиска **Выбор агентов** полностью или частично введите имя пользователя, которого требуется добавить к этой группе, и нажмите кнопку **Найти**. В сформированном списке агентов щелкните пользователя, затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="1ef83-p111">To add a user to the agent group, click **Select**, and then in the **Select Agents** search field, type all or part of the name of the user that you want to add to this group, and then click **Find**. In the resulting list of agents, click the user, and then click **OK**.</span></span>
        
          - <span data-ttu-id="1ef83-145">Для удаления пользователя из группы агентов щелкните этого пользователя в списке агентов, затем нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="1ef83-145">To remove a user from the agent group, in the list of agents, click the user you want to remove, and then click **Remove**.</span></span>
        
          - <span data-ttu-id="1ef83-146">Чтобы изменить порядок агентов, в котором им предлагаются звонки в группах с последовательной маршрутизацией или маршрутизацией с циклическим перебором, щелкните агента в списке агентов, а затем нажмите кнопку со стрелкой вверх или вниз.</span><span class="sxs-lookup"><span data-stu-id="1ef83-146">To change the order in which agents are offered calls in groups that use either round robin routing or serial routing, in the list of agents, click a user, and then click the up arrow or down arrow.</span></span>
    
      - <span data-ttu-id="1ef83-147">Для преобразования списка рассылки Microsoft Exchange Server в группу агентов щелкните **Использовать существующий список рассылки электронной почты**, затем в поле **Адрес списка рассылки** введите адрес электронной почты списка рассылки (например, NetworkSupport@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="1ef83-147">To use a Microsoft Exchange Server distribution list as your agent group, click **Use an existing email distribution list**, and then in **Distribution list address**, type the email address of the distribution list (for example, NetworkSupport@contoso.com).</span></span>
        
        <span data-ttu-id="1ef83-148">Если вы используете список рассылки по электронной почте, накладываются следующие ограничения:</span><span class="sxs-lookup"><span data-stu-id="1ef83-148">If you use an email distribution list, you are subject to the following constraints:</span></span>
        
          - <span data-ttu-id="1ef83-p112">Нельзя выбрать несколько списков рассылки для группы агентов. Каждая группа поддерживает только один список рассылки.</span><span class="sxs-lookup"><span data-stu-id="1ef83-p112">You cannot select multiple distribution lists for the agent group. Each group supports only a single distribution list.</span></span>
        
          - <span data-ttu-id="1ef83-151">Если список рассылки содержит один или несколько списков рассылки, члены вложенных списков рассылки не добавляются в список агентов.</span><span class="sxs-lookup"><span data-stu-id="1ef83-151">If the distribution list contains one or more distribution lists, members of the nested distribution lists are not added to the agent list.</span></span>
        
          - <span data-ttu-id="1ef83-152">Если выбрана последовательная маршрутизация или маршрутизация с циклическим перебором, сервер предлагает входящий звонок соответствующему агенту в соответствии с методом маршрутизации и порядком, в котором агенты представлены в списке рассылки.</span><span class="sxs-lookup"><span data-stu-id="1ef83-152">If serial or round robin routing is selected, the server offers an incoming call to the appropriate agent according to the routing method and according to the order in which agents are listed in the distribution list.</span></span>
        
          - <span data-ttu-id="1ef83-p113">Если список рассылки содержит пользователей, для которых использование Lync Server 2010 разрешено, но корпоративная голосовая связь не включена, они будут добавлены в группу агентов как неработоспособные агенты. Убедитесь, что для учетных записей всех участников списка рассылки включена корпоративная голосовая связь.</span><span class="sxs-lookup"><span data-stu-id="1ef83-p113">If the distribution list contains users for which Lync Server 2010 is enabled but Enterprise Voice is not enabled, they will be added to the agent group as dysfunctional agents. Make sure that all members of the distribution list have Enterprise Voice enabled for their user accounts.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="1ef83-155">Если вы используете список рассылки электронной почты, скрытые участники или скрытые списки могут стать видимыми для администратора группы ответа или пользователей.</span><span class="sxs-lookup"><span data-stu-id="1ef83-155">If you use an email distribution list, hidden memberships or hidden lists might become visible to the Response Group administrator or users.</span></span>

        
        </div>
        
        <span data-ttu-id="1ef83-156">Скрытое членство или скрытые списки могут отображаться в следующих случаях:</span><span class="sxs-lookup"><span data-stu-id="1ef83-156">Hidden memberships or hidden lists can become visible as follows:</span></span>
        
          - <span data-ttu-id="1ef83-157">Если вы настроили список рассылки таким образом, что членство скрыты, а администратор группы отвечает за предоставление списка рассылки для списка, пользователи смогут вызвать эту группу, чтобы узнать, кто является ее участником.</span><span class="sxs-lookup"><span data-stu-id="1ef83-157">If a distribution list was configured so that the membership is hidden and the Response Group administrator assigns the distribution list to the agent list, users can call the group to find out who the members are.</span></span>
        
          - <span data-ttu-id="1ef83-158">Если список рассылки настроен таким образом, что он скрыт в глобальном списке адресов Exchange, администратор группы ответа может видеть список рассылки и назначать его в список агента, если процесс группы ответа имеет соответствующие права пользователя и разрешения, даже если администратор не обладает необходимыми правами и разрешениями пользователей.</span><span class="sxs-lookup"><span data-stu-id="1ef83-158">If a distribution list was configured so that it is hidden in the Exchange Global Address List, the Response Group administrator might be able to see the distribution list and assign it to the agent list if the Response Group process has the appropriate user rights and permissions, even if the administrator does not have the appropriate user rights and permissions.</span></span>

11. <span data-ttu-id="1ef83-159">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="1ef83-159">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-an-agent-group"></a><span data-ttu-id="1ef83-160">Создание и изменение группы агента с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1ef83-160">To use Windows PowerShell to create or modify an agent group</span></span>

1.  <span data-ttu-id="1ef83-161">Выполните вход как член группы RTCUniversalServerAdmins или одной из предварительно заданных административных ролей, поддерживающих группу ответа.</span><span class="sxs-lookup"><span data-stu-id="1ef83-161">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="1ef83-162">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="1ef83-162">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="1ef83-163">Используйте **New-ксргсажентграуп** для создания группы агента.</span><span class="sxs-lookup"><span data-stu-id="1ef83-163">Use **New-CsRgsAgentGroup** to create a new agent group.</span></span> <span data-ttu-id="1ef83-164">С помощью **Set-ксргсажентграуп** можно изменить существующую группу агента.</span><span class="sxs-lookup"><span data-stu-id="1ef83-164">Use **Set-CsRgsAgentGroup** to modify an existing agent group.</span></span> <span data-ttu-id="1ef83-165">В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="1ef83-165">At the command line, run:</span></span>
    
        New-CsRgsAgentGroup -Name "<agent group name>" -Parent $serviceId [-Description "<agent group description>"] -[AgentAlertTime <# seconds until call is routed to next agent>] [-ParticipationPolicy <Formal | Informal>] [-RoutingMethod <method for routing calls>] [-AgentsByUri("<first agent's SIP address>","<second agent's SIP address>")];
    
    <span data-ttu-id="1ef83-166">Например:</span><span class="sxs-lookup"><span data-stu-id="1ef83-166">For example:</span></span>
    
        New-CsRgsAgentGroup -Name "Help Desk" -Parent "service:ApplicationServer:atl-cs-001.contoso.com"  -Description "Contoso Help Desk" -AgentAlertTime 20 -ParticipationPolicy Formal -RoutingMethod RoundRobin -AgentsByUri("sip:mindy@contoso.com","sip:bob@contoso.com")
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="1ef83-p115">Значение времени оповещения агента не может превышать 180 секунд; в противном случае клиентское приложение отклонит вызов по причине достижения максимального времени ожидания для таймера операций SIP.</span><span class="sxs-lookup"><span data-stu-id="1ef83-p115">The agent alert time setting cannot exceed 180 seconds. If the agent alert time is greater than 180 seconds, the client application rejects the call because the SIP transaction timer reaches its maximum wait time.</span></span>

    
    </div>

4.  <span data-ttu-id="1ef83-p116">Чтобы убедиться, что группа агентов была создана, введите:</span><span class="sxs-lookup"><span data-stu-id="1ef83-p116">Confirm that the agent group is created. Run:</span></span>
    
        Get-CsRgsAgentGroup -Name "Help Desk"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1ef83-171">См. также</span><span class="sxs-lookup"><span data-stu-id="1ef83-171">See Also</span></span>


[<span data-ttu-id="1ef83-172">Удаление группы агента в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ef83-172">Delete an agent group in Lync Server 2013</span></span>](lync-server-2013-delete-an-agent-group.md)  


[<span data-ttu-id="1ef83-173">Управление группами агентов группы ответа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ef83-173">Managing Response Group agent groups in Lync Server 2013</span></span>](lync-server-2013-managing-response-group-agent-groups.md)  
[<span data-ttu-id="1ef83-174">Get-CsService</span><span class="sxs-lookup"><span data-stu-id="1ef83-174">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
[<span data-ttu-id="1ef83-175">New-CsRgsAgentGroup</span><span class="sxs-lookup"><span data-stu-id="1ef83-175">New-CsRgsAgentGroup</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsAgentGroup)  
[<span data-ttu-id="1ef83-176">Set-Ксргсажентграуп</span><span class="sxs-lookup"><span data-stu-id="1ef83-176">Set-CsRgsAgentGroup</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsRgsAgentGroup)  
[<span data-ttu-id="1ef83-177">Get-CsRgsAgentGroup</span><span class="sxs-lookup"><span data-stu-id="1ef83-177">Get-CsRgsAgentGroup</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsAgentGroup)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

