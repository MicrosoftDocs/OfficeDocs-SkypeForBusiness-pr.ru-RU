---
title: Создание или изменение группы агентов в Скайп для бизнеса
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f1461fff-51c1-4f4b-9311-8cba02c333fc
description: Создание или изменение группы агента группы ответа, в Скайп Business Server корпоративной голосовой связи.
ms.openlocfilehash: 0a88052d8ceba244e6971d1ebeffdffa84388ef6
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "23882195"
---
# <a name="create-or-modify-an-agent-group-in-skype-for-business"></a><span data-ttu-id="0edf8-103">Создание или изменение группы агентов в Скайп для бизнеса</span><span class="sxs-lookup"><span data-stu-id="0edf8-103">Create or modify an agent group in Skype for Business</span></span>
 
<span data-ttu-id="0edf8-104">Создание или изменение группы агента группы ответа, в Скайп Business Server корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="0edf8-104">Create or modify an agent group in Response Group, in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="0edf8-105">Когда вы создаете группу агентов, вы выбираете агентов, назначаемых группе, и указываете дополнительные параметры группы, такие как метод маршрутизации и возможность агента выполнять вход в группу и выход из нее.</span><span class="sxs-lookup"><span data-stu-id="0edf8-105">When you create an agent group, you select the agents that are assigned to the group and specify additional group settings, such as the routing method and whether an agent can sign in to and out of the group.</span></span> 
  
<span data-ttu-id="0edf8-106">Агент, необходимо вход и выход из них group, который отличается от вход и выход Скайп для бизнеса, называется неофициальный агент.</span><span class="sxs-lookup"><span data-stu-id="0edf8-106">An agent who must sign in and out of the group, which is different from signing in or out of Skype for Business, is called a formal agent.</span></span> <span data-ttu-id="0edf8-107">Для приема вызовов, направленных в группу, официальные агенты должны сначала войти в группу.</span><span class="sxs-lookup"><span data-stu-id="0edf8-107">Formal agents must be signed in to the group before they can receive calls routed to the group.</span></span> <span data-ttu-id="0edf8-108">Это может быть удобно для агентов, которые отвечают на вызовы из группы неполный рабочий день.</span><span class="sxs-lookup"><span data-stu-id="0edf8-108">This can be useful for agents who answer calls from the group on a part-time basis.</span></span> <span data-ttu-id="0edf8-109">Официальные агенты вход и выход в свои группы, щелкнув пункт меню в Скайп для бизнеса открыть Windows Internet Explorer веб-браузер и отображения консоли веб-страницы.</span><span class="sxs-lookup"><span data-stu-id="0edf8-109">Formal agents sign in and out of their groups by clicking a menu item in Skype for Business to open the Windows Internet Explorer Internet browser and display a webpage console.</span></span>
  
<span data-ttu-id="0edf8-110">Агент, который не входит в группу и не выходит из нее, называется неофициальным агентом.</span><span class="sxs-lookup"><span data-stu-id="0edf8-110">An agent who does not sign in or out of the group is called an informal agent.</span></span> <span data-ttu-id="0edf8-111">Неофициальные агенты автоматически входят группу когда выполняют вход в систему Скайп для бизнеса, и они не удается выйти из группы.</span><span class="sxs-lookup"><span data-stu-id="0edf8-111">Informal agents are automatically signed in to the group when they sign in to Skype for Business, and they cannot sign out of the group.</span></span>
  
<span data-ttu-id="0edf8-112">Агентами могут быть только локальные пользователи.</span><span class="sxs-lookup"><span data-stu-id="0edf8-112">Only on-premises users can be agents.</span></span> <span data-ttu-id="0edf8-113">Если агент перемещается из локальной сети, группа ответа звонки будут перенаправляться не этому агенту.</span><span class="sxs-lookup"><span data-stu-id="0edf8-113">If an agent is moved from on-premises to online, Response Group calls will not be routed to that agent.</span></span>
  
<span data-ttu-id="0edf8-114">Используйте одну из следующих процедур для создания или изменения группы агентов.</span><span class="sxs-lookup"><span data-stu-id="0edf8-114">Use one of the following procedures to create or modify an agent group.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="0edf8-p104">При назначении пользователей в качестве агентов группы ответа оповестите их о том, что при включенном режиме конфиденциальности им потребуется выполнить поиск контактов "RGS Presence Watcher" и добавить их в список контактов. Агенты с включенным режимом конфиденциальности и без "RGS Presence Watcher" в списке контактов не могут принимать звонки, направленные в группу ответа. На агентов, у которых режим конфиденциальности отключен, данная особенность не распространяется.</span><span class="sxs-lookup"><span data-stu-id="0edf8-p104">When you assign users as response group agents, inform them that, if they have Privacy mode enabled, they need to search for "RGS Presence Watcher" contacts and add them to their Contacts list. Agents who have Privacy mode enabled, but who do not have "RGS Presence Watcher" in their Contacts list, cannot receive calls to the response group. Agents who do not have Privacy mode enabled are not affected.</span></span> 
  
### <a name="to-use-skype-for-business-server-control-panel-to-create-or-modify-an-agent-group"></a><span data-ttu-id="0edf8-118">Чтобы использовать Скайп для панели управления Business Server для создания или изменения группы агентов</span><span class="sxs-lookup"><span data-stu-id="0edf8-118">To use Skype for Business Server Control Panel to create or modify an agent group</span></span>

1. <span data-ttu-id="0edf8-119">Выполните вход как член группы RTCUniversalServerAdmins или одной из предварительно заданных административных ролей, поддерживающих группу ответа.</span><span class="sxs-lookup"><span data-stu-id="0edf8-119">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0edf8-120">Если вы являетесь одним из полномочных менеджеров группы ответа для управляемого рабочего процесса, вы сможете создать группы и назначить им процессы, которыми вы управляете.</span><span class="sxs-lookup"><span data-stu-id="0edf8-120">If you are one of the delegated Response Group Managers for a managed workflow, you can create groups and use them in the workflows that you manage.</span></span> 
  
2. <span data-ttu-id="0edf8-121">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="0edf8-121">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="0edf8-122">В левой области навигации щелкните **Группы ответа**, затем **Группа**.</span><span class="sxs-lookup"><span data-stu-id="0edf8-122">In the left navigation bar, click **Response Groups**, and then click **Group**.</span></span>
    
4. <span data-ttu-id="0edf8-123">На странице **Группа** выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="0edf8-123">On the **Group** page, do one of the following:</span></span>
    
   - <span data-ttu-id="0edf8-p105">Для создания новой группы агентов щелкните **Создать**. В поле поиска **Выбор службы** полностью или частично введите имя службы **ApplicationServer**, для которой необходимо добавить группу. В сформированном списке служб щелкните требуемую службу, затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="0edf8-p105">To create a new agent group, click **New**. In the **Select a Service** search field, type all or part of the name of the **ApplicationServer** service where you want to add the group. In the resulting list of services, click the service that you want, and then click **OK**.</span></span>
    
   - <span data-ttu-id="0edf8-p106">Для изменения существующей группы агентов полностью или частично введите ее имя в поле поиска. В сформированном списке щелкните требуемую группу и нажмите кнопку **Изменить**, затем **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="0edf8-p106">To modify an existing agent group, type all or part of the name of the agent group in the search field. In the resulting list, click the group that you want, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="0edf8-129">В поле **Имя** введите имя, определяющее группу агентов.</span><span class="sxs-lookup"><span data-stu-id="0edf8-129">In **Name**, type an identifying name for the agent group.</span></span>
    
6. <span data-ttu-id="0edf8-130">В поле **Описание** введите описание группы.</span><span class="sxs-lookup"><span data-stu-id="0edf8-130">In **Description**, type a description for the group.</span></span>
    
7. <span data-ttu-id="0edf8-131">В разделе **Политика участия** выберите один из следующих режимов входа в группу.</span><span class="sxs-lookup"><span data-stu-id="0edf8-131">In the **Participation policy**, select one of the following to set up the sign-in behavior for the group:</span></span>
    
   - <span data-ttu-id="0edf8-132">Если выбран режим **Свободная**, агентам не требуется входить в группу и выходить из нее.</span><span class="sxs-lookup"><span data-stu-id="0edf8-132">Select **Informal** to specify that agents in the group do not need to sign in and out of the group.</span></span> <span data-ttu-id="0edf8-133">Агенты автоматически входят в группу когда выполняют вход в систему Скайп для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="0edf8-133">Agents are automatically signed in to the group when they sign in to Skype for Business.</span></span>
    
   - <span data-ttu-id="0edf8-134">Если выбран режим **Строгая**, агентам необходимо входить в группу и выходить из нее.</span><span class="sxs-lookup"><span data-stu-id="0edf8-134">Select **Formal** to specify that agents in the group must sign in and out of the group.</span></span> <span data-ttu-id="0edf8-135">При выборе этого параметра агенты щелкните элемент меню в Скайп для бизнеса для откройте Internet Explorer и отображения консоли веб-страницы для подписания и выходить из нее в группу.</span><span class="sxs-lookup"><span data-stu-id="0edf8-135">When you select this option, agents click a menu item in Skype for Business to open Internet Explorer and display a webpage console for signing in and out of the group.</span></span>
    
8. <span data-ttu-id="0edf8-136">В поле **Время предупреждения (в секундах)** укажите продолжительность звукового сигнала вызова на телефоне агента в секундах (по умолчанию: 20 секунд). По истечении указанного времени принять вызов предлагается следующему свободному оператору.</span><span class="sxs-lookup"><span data-stu-id="0edf8-136">In **Alert time (seconds)**, specify the number of seconds to ring an agent before offering the call to the next available agent (the default is 20 seconds).</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="0edf8-p109">Значение времени оповещения агента не может превышать 180 секунд; в противном случае клиентское приложение отклонит вызов по причине достижения максимального времени ожидания для таймера операций SIP.</span><span class="sxs-lookup"><span data-stu-id="0edf8-p109">The agent alert time setting cannot exceed 180 seconds. If the agent alert time exceeds 180 seconds, the client application rejects the call because the SIP transaction timer reaches its maximum wait time.</span></span> 
  
9. <span data-ttu-id="0edf8-139">В разделе **Метод маршрутизации** выберите способ направления вызовов агентам в группе, выполнив следующие действия.</span><span class="sxs-lookup"><span data-stu-id="0edf8-139">In **Routing method**, select the method for routing calls to agents in the group as follows:</span></span>
    
   - <span data-ttu-id="0edf8-140">Чтобы сначала предложить Новый звонок агенту, который бездействовал дольше остальных (у которого состояние присутствия **доступен** или **неактивен** в Скайп для бизнеса дольше), нажмите кнопку **длинным простоя**.</span><span class="sxs-lookup"><span data-stu-id="0edf8-140">To offer a new call first to the agent who has been idle the longest (has had a presence of **Available** or **Inactive** in Skype for Business the longest), click **Longest idle**.</span></span> 
    
   - <span data-ttu-id="0edf8-p110">Если требуется одновременно предлагать принять новый вызов всем свободным агентам, щелкните **Параллельно**. Вызов направляется первому агенту, который его принимает.</span><span class="sxs-lookup"><span data-stu-id="0edf8-p110">To offer a new call to all available agents at the same time, click **Parallel**. The call is sent to the first agent who accepts it.</span></span>
    
   - <span data-ttu-id="0edf8-143">Если требуется одновременно предлагать принять новый вызов каждому агенту поочередно, щелкните **Циклический перебор**.</span><span class="sxs-lookup"><span data-stu-id="0edf8-143">To offer a new call to each agent in turn, click **Round robin**.</span></span> 
    
   - <span data-ttu-id="0edf8-144">Если требуется всегда предлагать принять новый вызов агентам в том порядке, в котором они представлены в списке **Агент**, щелкните **Последовательно**.</span><span class="sxs-lookup"><span data-stu-id="0edf8-144">To always offer a new call to the agents in the order in which they are listed in the **Agent** list, click **Serial**.</span></span> 
    
   - <span data-ttu-id="0edf8-145">Чтобы предложить Новый звонок для всех агентов, которые были подписаны в Скайп для бизнеса и приложения группы ответа в то же время, независимо от их текущего сведения о присутствии щелкните **помощника**.</span><span class="sxs-lookup"><span data-stu-id="0edf8-145">To offer a new call to all agents who are signed into Skype for Business and the Response Group application at the same time, regardless of their current presence, click **Attendant**.</span></span> <span data-ttu-id="0edf8-146">Пользователи, настроенные как агенты могут видеть все звонки, которые ожидают и отвечать на звонки ожидания в любом порядке.</span><span class="sxs-lookup"><span data-stu-id="0edf8-146">Users who are configured as agents can see all the calls that are waiting and answer waiting calls in any order.</span></span> <span data-ttu-id="0edf8-147">Вызов отправляется первого агенту, который принимает его, после чего другие агенты больше не видели вызов.</span><span class="sxs-lookup"><span data-stu-id="0edf8-147">The call is sent to the first agent who accepts it, after which the other agents no longer see the call.</span></span>
    
10. <span data-ttu-id="0edf8-148">В разделе **Агенты** укажите вариант создания списка агентов.</span><span class="sxs-lookup"><span data-stu-id="0edf8-148">In **Agents**, specify how you want to create your agents list:</span></span>
    
   - <span data-ttu-id="0edf8-149">Для создания пользовательского списка агентов щелкните **Определить настраиваемую группу агентов** и выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="0edf8-149">To use a custom list of agents, click **Define a custom group of agents**, and do one of the following:</span></span>
    
   - <span data-ttu-id="0edf8-p112">Для добавления пользователя к группе агентов щелкните **Выбрать**, затем в поле поиска **Выбор агентов** полностью или частично введите имя пользователя, которого требуется добавить к этой группе, и нажмите кнопку **Найти**. В сформированном списке агентов щелкните пользователя, затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="0edf8-p112">To add a user to the agent group, click **Select**, and then in the **Select Agents** search field, type all or part of the name of the user that you want to add to this group, and then click **Find**. In the resulting list of agents, click the user, and then click **OK**.</span></span>
    
   - <span data-ttu-id="0edf8-152">Для удаления пользователя из группы агентов щелкните этого пользователя в списке агентов, затем нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="0edf8-152">To remove a user from the agent group, in the list of agents, click the user you want to remove, and then click **Remove**.</span></span>
    
   - <span data-ttu-id="0edf8-153">Чтобы изменить порядок агентов, в котором им предлагаются звонки в группах с последовательной маршрутизацией или маршрутизацией с циклическим перебором, щелкните агента в списке агентов, а затем нажмите кнопку со стрелкой вверх или вниз.</span><span class="sxs-lookup"><span data-stu-id="0edf8-153">To change the order in which agents are offered calls in groups that use either round robin routing or serial routing, in the list of agents, click a user, and then click the up arrow or down arrow.</span></span> 
    
   - <span data-ttu-id="0edf8-154">Для преобразования списка рассылки Microsoft Exchange Server в группу агентов щелкните **Использовать существующий список рассылки электронной почты**, затем в поле **Адрес списка рассылки** введите адрес электронной почты списка рассылки (например, NetworkSupport@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="0edf8-154">To use a Microsoft Exchange Server distribution list as your agent group, click **Use an existing email distribution list**, and then in **Distribution list address**, type the email address of the distribution list (for example, NetworkSupport@contoso.com).</span></span>
    
     <span data-ttu-id="0edf8-155">Если вы используете список рассылки по электронной почте, накладываются следующие ограничения:</span><span class="sxs-lookup"><span data-stu-id="0edf8-155">If you use an email distribution list, you are subject to the following constraints:</span></span>
    
     - <span data-ttu-id="0edf8-p113">Нельзя выбрать несколько списков рассылки для группы агентов. Каждая группа поддерживает только один список рассылки.</span><span class="sxs-lookup"><span data-stu-id="0edf8-p113">You cannot select multiple distribution lists for the agent group. Each group supports only a single distribution list.</span></span>
    
     - <span data-ttu-id="0edf8-158">Если список рассылки содержит один или несколько списков рассылки, члены вложенных списков рассылки не добавляются в список агентов.</span><span class="sxs-lookup"><span data-stu-id="0edf8-158">If the distribution list contains one or more distribution lists, members of the nested distribution lists are not added to the agent list.</span></span>
    
     - <span data-ttu-id="0edf8-159">Если выбрана последовательная маршрутизация или маршрутизация с циклическим перебором, сервер предлагает входящий звонок соответствующему агенту в соответствии с методом маршрутизации и порядком, в котором агенты представлены в списке рассылки.</span><span class="sxs-lookup"><span data-stu-id="0edf8-159">If serial or round robin routing is selected, the server offers an incoming call to the appropriate agent according to the routing method and according to the order in which agents are listed in the distribution list.</span></span>
    
     - <span data-ttu-id="0edf8-p114">Если список рассылки содержит пользователей, для которых использование Lync Server 2010 разрешено, но корпоративная голосовая связь не включена, они будут добавлены в группу агентов как неработоспособные агенты. Убедитесь, что для учетных записей всех участников списка рассылки включена корпоративная голосовая связь.</span><span class="sxs-lookup"><span data-stu-id="0edf8-p114">If the distribution list contains users for which Lync Server 2010 is enabled but Enterprise Voice is not enabled, they will be added to the agent group as dysfunctional agents. Make sure that all members of the distribution list have Enterprise Voice enabled for their user accounts.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="0edf8-162">Если вы используете список рассылки по электронной почте, скрытые члены или скрытые списки могут стать видны группы ответа Администраторы или пользователи.</span><span class="sxs-lookup"><span data-stu-id="0edf8-162">If you use an email distribution list, hidden memberships or hidden lists might become visible to the Response Group administrator or users.</span></span> 
  
    <span data-ttu-id="0edf8-163">Скрытое членство или скрытые списки могут отображаться в следующих случаях:</span><span class="sxs-lookup"><span data-stu-id="0edf8-163">Hidden memberships or hidden lists can become visible as follows:</span></span>
    
     - <span data-ttu-id="0edf8-164">Если список рассылки был настроен, чтобы скрыт членства и группы ответа администратор назначает списка рассылки в список агентов, пользователи могут позвонить группе, чтобы узнать, кто входит члены.</span><span class="sxs-lookup"><span data-stu-id="0edf8-164">If a distribution list was configured so that the membership is hidden and the Response Group administrator assigns the distribution list to the agent list, users can call the group to find out who the members are.</span></span> 
    
     - <span data-ttu-id="0edf8-165">Если список рассылки был настроен, чтобы оно скрыто в глобальном списке адресов Exchange, администратор группы ответа могут могут видеть распространения списка и назначьте его в список агентов, в котором процесс группы ответа имеет соответствующие права и разрешения, даже если администратор не имеет права и разрешения.</span><span class="sxs-lookup"><span data-stu-id="0edf8-165">If a distribution list was configured so that it is hidden in the Exchange Global Address List, the Response Group administrator might be able to see the distribution list and assign it to the agent list if the Response Group process has the appropriate user rights and permissions, even if the administrator does not have the appropriate user rights and permissions.</span></span>
    
11. <span data-ttu-id="0edf8-166">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="0edf8-166">Click **Commit**.</span></span>
    
### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-an-agent-group"></a><span data-ttu-id="0edf8-167">Чтобы использовать Скайп для консоли Business Server для создания или изменения группы агентов</span><span class="sxs-lookup"><span data-stu-id="0edf8-167">To use Skype for Business Server Management Shell to create or modify an agent group</span></span>

1. <span data-ttu-id="0edf8-168">Выполните вход как член группы RTCUniversalServerAdmins или одной из предварительно заданных административных ролей, поддерживающих группу ответа.</span><span class="sxs-lookup"><span data-stu-id="0edf8-168">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
2. <span data-ttu-id="0edf8-169">Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="0edf8-169">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="0edf8-170">Используйте **Командлет New-CsRgsAgentGroup** , чтобы создать новую группу агентов.</span><span class="sxs-lookup"><span data-stu-id="0edf8-170">Use **New-CsRgsAgentGroup** to create a new agent group.</span></span> <span data-ttu-id="0edf8-171">Командлет **Set-CsRgsAgentGroup** для изменения существующей группы агентов.</span><span class="sxs-lookup"><span data-stu-id="0edf8-171">Use **Set-CsRgsAgentGroup** to modify an existing agent group.</span></span> <span data-ttu-id="0edf8-172">В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="0edf8-172">At the command line, run:</span></span>
    
   ```
   New-CsRgsAgentGroup -Name "<agent group name>" -Parent $serviceId [-Description "<agent group description>"] -[AgentAlertTime <# seconds until call is routed to next agent>] [-ParticipationPolicy <Formal | Informal>] [-RoutingMethod <method for routing calls>] [-AgentsByUri("<first agent's SIP address>","<second agent's SIP address>")];
   ```

    <span data-ttu-id="0edf8-173">Например:</span><span class="sxs-lookup"><span data-stu-id="0edf8-173">For example:</span></span>
    
   ```
   New-CsRgsAgentGroup -Name "Help Desk" -Parent "service:ApplicationServer:atl-cs-001.contoso.com"  -Description "Contoso Help Desk" -AgentAlertTime 20 -ParticipationPolicy Formal -RoutingMethod RoundRobin -AgentsByUri("sip:mindy@contoso.com","sip:bob@contoso.com")
   ```

    > [!IMPORTANT]
    > <span data-ttu-id="0edf8-p116">Значение времени оповещения агента не может превышать 180 секунд; в противном случае клиентское приложение отклонит вызов по причине достижения максимального времени ожидания для таймера операций SIP.</span><span class="sxs-lookup"><span data-stu-id="0edf8-p116">The agent alert time setting cannot exceed 180 seconds. If the agent alert time is greater than 180 seconds, the client application rejects the call because the SIP transaction timer reaches its maximum wait time.</span></span> 
  
4. <span data-ttu-id="0edf8-p117">Чтобы убедиться, что группа агентов была создана, введите:</span><span class="sxs-lookup"><span data-stu-id="0edf8-p117">Confirm that the agent group is created. Run:</span></span>
    
   ```
   Get-CsRgsAgentGroup -Name "Help Desk"
   ```

## <a name="see-also"></a><span data-ttu-id="0edf8-178">См. также</span><span class="sxs-lookup"><span data-stu-id="0edf8-178">See also</span></span>

[<span data-ttu-id="0edf8-179">Командлет Get-CsService</span><span class="sxs-lookup"><span data-stu-id="0edf8-179">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps)
  
[<span data-ttu-id="0edf8-180">Командлет New-CsRgsAgentGroup</span><span class="sxs-lookup"><span data-stu-id="0edf8-180">New-CsRgsAgentGroup</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csrgsagentgroup?view=skype-ps)
  
[<span data-ttu-id="0edf8-181">Командлет Set-CsRgsAgentGroup</span><span class="sxs-lookup"><span data-stu-id="0edf8-181">Set-CsRgsAgentGroup</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csrgsagentgroup?view=skype-ps)
  
[<span data-ttu-id="0edf8-182">Командлет Get-CsRgsAgentGroup</span><span class="sxs-lookup"><span data-stu-id="0edf8-182">Get-CsRgsAgentGroup</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csrgsagentgroup?view=skype-ps)