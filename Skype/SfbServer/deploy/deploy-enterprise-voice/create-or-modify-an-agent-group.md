---
title: Создание или изменение группы агентов в Skype для бизнеса
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f1461fff-51c1-4f4b-9311-8cba02c333fc
description: Создание или изменение группы агентов в группе ответа в Skype для бизнеса Server Корпоративная голосовая связь.
ms.openlocfilehash: dfa09c3341ad47f2646939738cb67db7b7f27304
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49837099"
---
# <a name="create-or-modify-an-agent-group-in-skype-for-business"></a><span data-ttu-id="68b47-103">Создание или изменение группы агентов в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="68b47-103">Create or modify an agent group in Skype for Business</span></span>
 
<span data-ttu-id="68b47-104">Создание или изменение группы агентов в группе ответа в Skype для бизнеса Server Корпоративная голосовая связь.</span><span class="sxs-lookup"><span data-stu-id="68b47-104">Create or modify an agent group in Response Group, in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="68b47-105">Когда вы создаете группу агентов, вы выбираете агентов, назначаемых группе, и указываете дополнительные параметры группы, такие как метод маршрутизации и возможность агента выполнять вход в группу и выход из нее.</span><span class="sxs-lookup"><span data-stu-id="68b47-105">When you create an agent group, you select the agents that are assigned to the group and specify additional group settings, such as the routing method and whether an agent can sign in to and out of the group.</span></span> 
  
<span data-ttu-id="68b47-106">Агент, который должен войти в группу и выйти из нее, чем вход в Skype для бизнеса или выход из нее, называется формальным агентом.</span><span class="sxs-lookup"><span data-stu-id="68b47-106">An agent who must sign in and out of the group, which is different from signing in or out of Skype for Business, is called a formal agent.</span></span> <span data-ttu-id="68b47-107">Официальные агенты должны войти в группу, прежде чем они смогут получать направленные в нее звонки.</span><span class="sxs-lookup"><span data-stu-id="68b47-107">Formal agents must be signed in to the group before they can receive calls routed to the group.</span></span> <span data-ttu-id="68b47-108">Это может быть удобно для агентов, которые отвечают на звонки из группы неполный рабочий день.</span><span class="sxs-lookup"><span data-stu-id="68b47-108">This can be useful for agents who answer calls from the group on a part-time basis.</span></span> <span data-ttu-id="68b47-109">Формальные агенты входят в свои группы и выходят из них, щелкнув пункт меню в Skype для бизнеса, чтобы открыть браузер Windows Internet Explorer и отобразить консоль веб-страницы.</span><span class="sxs-lookup"><span data-stu-id="68b47-109">Formal agents sign in and out of their groups by clicking a menu item in Skype for Business to open the Windows Internet Explorer Internet browser and display a webpage console.</span></span>
  
<span data-ttu-id="68b47-110">Агент, который не входит в группу и не выходит из нее, называется неофициальным агентом.</span><span class="sxs-lookup"><span data-stu-id="68b47-110">An agent who does not sign in or out of the group is called an informal agent.</span></span> <span data-ttu-id="68b47-111">Неофициальные агенты автоматически вписываются в группу при входе в Skype для бизнеса и не могут выйти из группы.</span><span class="sxs-lookup"><span data-stu-id="68b47-111">Informal agents are automatically signed in to the group when they sign in to Skype for Business, and they cannot sign out of the group.</span></span>
  
<span data-ttu-id="68b47-p103">Агентами могут быть только локальные пользователи. Если агент переходит из локального режима в интерактивный, ему не будут направляться звонки группы ответа.</span><span class="sxs-lookup"><span data-stu-id="68b47-p103">Only on-premises users can be agents. If an agent is moved from on-premises to online, Response Group calls will not be routed to that agent.</span></span>
  
<span data-ttu-id="68b47-114">Используйте одну из следующих процедур для создания или изменения группы агентов.</span><span class="sxs-lookup"><span data-stu-id="68b47-114">Use one of the following procedures to create or modify an agent group.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="68b47-p104">При назначении пользователей в качестве агентов группы ответа оповестите их о том, что при включенном режиме конфиденциальности им потребуется выполнить поиск контактов "RGS Presence Watcher" и добавить их в список контактов. Агенты с включенным режимом конфиденциальности и без "RGS Presence Watcher" в списке контактов не могут принимать звонки, направленные в группу ответа. На агентов, у которых режим конфиденциальности отключен, данная особенность не распространяется.</span><span class="sxs-lookup"><span data-stu-id="68b47-p104">When you assign users as response group agents, inform them that, if they have Privacy mode enabled, they need to search for "RGS Presence Watcher" contacts and add them to their Contacts list. Agents who have Privacy mode enabled, but who do not have "RGS Presence Watcher" in their Contacts list, cannot receive calls to the response group. Agents who do not have Privacy mode enabled are not affected.</span></span> 
  
### <a name="to-use-skype-for-business-server-control-panel-to-create-or-modify-an-agent-group"></a><span data-ttu-id="68b47-118">Использование панели управления Skype для бизнеса Server для создания или изменения группы агентов</span><span class="sxs-lookup"><span data-stu-id="68b47-118">To use Skype for Business Server Control Panel to create or modify an agent group</span></span>

1. <span data-ttu-id="68b47-119">Войдите как член группы RTCUniversalServerAdmins или как член одной из предопределеных административных ролей, которые поддерживают группу ответа.</span><span class="sxs-lookup"><span data-stu-id="68b47-119">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="68b47-120">Если вы являетесь одним из полномочных менеджеров группы ответа для управляемого рабочего процесса, вы сможете создать группы и назначить им процессы, которыми вы управляете.</span><span class="sxs-lookup"><span data-stu-id="68b47-120">If you are one of the delegated Response Group Managers for a managed workflow, you can create groups and use them in the workflows that you manage.</span></span> 
  
2. <span data-ttu-id="68b47-121">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="68b47-121">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="68b47-122">На левой панели навигации щелкните **Группы ответа**, а затем щелкните **Группа**.</span><span class="sxs-lookup"><span data-stu-id="68b47-122">In the left navigation bar, click **Response Groups**, and then click **Group**.</span></span>
    
4. <span data-ttu-id="68b47-123">На странице **Группа** выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="68b47-123">On the **Group** page, do one of the following:</span></span>
    
   - <span data-ttu-id="68b47-p105">Чтобы создать новую группу агентов, щелкните элемент **Создать**. В поле поиска **Выберите услугу** введите полное имя (или часть имени) службы **ApplicationServer**, для которой необходимо добавить группу, щелкните необходимую службу в итоговом списке служб и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="68b47-p105">To create a new agent group, click **New**. In the **Select a Service** search field, type all or part of the name of the **ApplicationServer** service where you want to add the group. In the resulting list of services, click the service that you want, and then click **OK**.</span></span>
    
   - <span data-ttu-id="68b47-p106">Чтобы изменить существующую группу агентов, введите полное имя этой группы агентов или его часть в поле поиска. В итоговом списке выберите необходимую группу, щелкните элемент **Изменить** и элемент **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="68b47-p106">To modify an existing agent group, type all or part of the name of the agent group in the search field. In the resulting list, click the group that you want, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="68b47-129">В поле **Имя** введите определяющее имя для группы агентов.</span><span class="sxs-lookup"><span data-stu-id="68b47-129">In **Name**, type an identifying name for the agent group.</span></span>
    
6. <span data-ttu-id="68b47-130">В поле **Описание** введите описание группы.</span><span class="sxs-lookup"><span data-stu-id="68b47-130">In **Description**, type a description for the group.</span></span>
    
7. <span data-ttu-id="68b47-131">В разделе **Политика участия** выберите один из следующих параметров для настройки процедуры входа для группы:</span><span class="sxs-lookup"><span data-stu-id="68b47-131">In the **Participation policy**, select one of the following to set up the sign-in behavior for the group:</span></span>
    
   - <span data-ttu-id="68b47-132">Выберите **Неформальное**, чтобы указать, что агентам, входящим в группу, не требуется вход в группу и выход из нее.</span><span class="sxs-lookup"><span data-stu-id="68b47-132">Select **Informal** to specify that agents in the group do not need to sign in and out of the group.</span></span> <span data-ttu-id="68b47-133">Агенты автоматически вписываются в группу при входе в Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="68b47-133">Agents are automatically signed in to the group when they sign in to Skype for Business.</span></span>
    
   - <span data-ttu-id="68b47-134">Выберите **Формальное**, чтобы указать, что агентам, входящим в группу, необходимо выполнять вход в группу и выход из нее.</span><span class="sxs-lookup"><span data-stu-id="68b47-134">Select **Formal** to specify that agents in the group must sign in and out of the group.</span></span> <span data-ttu-id="68b47-135">When you select this option, agents click a menu item in Skype for Business to open Internet Explorer and display a webpage console for signing in and out of the group.</span><span class="sxs-lookup"><span data-stu-id="68b47-135">When you select this option, agents click a menu item in Skype for Business to open Internet Explorer and display a webpage console for signing in and out of the group.</span></span>
    
8. <span data-ttu-id="68b47-136">В поле **Время оповещения (секунды)** укажите количество секунд, на протяжении которых телефон агента будет звонить, прежде чем другому свободному оператору будет предложено принять вызов (по умолчанию используется время 20 секунд).</span><span class="sxs-lookup"><span data-stu-id="68b47-136">In **Alert time (seconds)**, specify the number of seconds to ring an agent before offering the call to the next available agent (the default is 20 seconds).</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="68b47-p109">Значение времени оповещения агента не может превышать 180 секунд; в противном случае клиентское приложение отклонит вызов по причине достижения максимального времени ожидания для таймера операций SIP.</span><span class="sxs-lookup"><span data-stu-id="68b47-p109">The agent alert time setting cannot exceed 180 seconds. If the agent alert time exceeds 180 seconds, the client application rejects the call because the SIP transaction timer reaches its maximum wait time.</span></span> 
  
9. <span data-ttu-id="68b47-139">В разделе **Метод маршрутизации** выберите метод маршрутизации вызовов для агентов, входящих в группу, следующим образом:</span><span class="sxs-lookup"><span data-stu-id="68b47-139">In **Routing method**, select the method for routing calls to agents in the group as follows:</span></span>
    
   - <span data-ttu-id="68b47-140">To offer a new call first to the agent who has been idle the longest (has a presence of **Available** or **Inactive** in Skype for Business the longest), click **Longest idle**.</span><span class="sxs-lookup"><span data-stu-id="68b47-140">To offer a new call first to the agent who has been idle the longest (has had a presence of **Available** or **Inactive** in Skype for Business the longest), click **Longest idle**.</span></span> 
    
   - <span data-ttu-id="68b47-p110">Чтобы одновременно предлагать новый вызов всем доступным агентам, щелкните **Параллельно**. Вызов направляется первому агенту, который его принимает.</span><span class="sxs-lookup"><span data-stu-id="68b47-p110">To offer a new call to all available agents at the same time, click **Parallel**. The call is sent to the first agent who accepts it.</span></span>
    
   - <span data-ttu-id="68b47-143">Чтобы предлагать новый вызов каждому агенту поочередно, щелкните **Циклический перебор**.</span><span class="sxs-lookup"><span data-stu-id="68b47-143">To offer a new call to each agent in turn, click **Round robin**.</span></span> 
    
   - <span data-ttu-id="68b47-144">Чтобы всегда предлагать новый вызов агентам в том порядке, в котором они представлены в списке **Агент**, щелкните **Последовательно**.</span><span class="sxs-lookup"><span data-stu-id="68b47-144">To always offer a new call to the agents in the order in which they are listed in the **Agent** list, click **Serial**.</span></span> 
    
   - <span data-ttu-id="68b47-145">Чтобы предложить новый вызов всем агентам, которые одновременно вписались в Skype для бизнеса и приложение группы ответа, независимо от их текущего присутствия, щелкните **"Помощник".**</span><span class="sxs-lookup"><span data-stu-id="68b47-145">To offer a new call to all agents who are signed into Skype for Business and the Response Group application at the same time, regardless of their current presence, click **Attendant**.</span></span> <span data-ttu-id="68b47-146">Пользователи, настроенные в качестве агентов, могут видеть все вызовы, ожидающих вызовы, и отвечать на них в любом порядке.</span><span class="sxs-lookup"><span data-stu-id="68b47-146">Users who are configured as agents can see all the calls that are waiting and answer waiting calls in any order.</span></span> <span data-ttu-id="68b47-147">Вызов отправляется первому агенту, который его принимает, после чего другие агенты больше не видят этот вызов.</span><span class="sxs-lookup"><span data-stu-id="68b47-147">The call is sent to the first agent who accepts it, after which the other agents no longer see the call.</span></span>
    
10. <span data-ttu-id="68b47-148">В области **Агенты** определите способ создания списка агентов:</span><span class="sxs-lookup"><span data-stu-id="68b47-148">In **Agents**, specify how you want to create your agents list:</span></span>
    
    - <span data-ttu-id="68b47-149">Чтобы использовать настраиваемый список агентов, щелкните элемент **Определить настраиваемую группу агентов** и выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="68b47-149">To use a custom list of agents, click **Define a custom group of agents**, and do one of the following:</span></span>
    
    - <span data-ttu-id="68b47-p112">Чтобы добавить пользователя в группу агентов, щелкните **Выбрать**, а затем в поле поиска **Выбор агентов** введите имя (полностью или частично) пользователя, которого необходимо добавить в эту группу, после чего щелкните **Найти**. В итоговом списке агентов выберите пользователя, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="68b47-p112">To add a user to the agent group, click **Select**, and then in the **Select Agents** search field, type all or part of the name of the user that you want to add to this group, and then click **Find**. In the resulting list of agents, click the user, and then click **OK**.</span></span>
    
    - <span data-ttu-id="68b47-152">Чтобы удалить пользователя из группы агентов, щелкните этого пользователя в списке агентов и нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="68b47-152">To remove a user from the agent group, in the list of agents, click the user you want to remove, and then click **Remove**.</span></span>
    
    - <span data-ttu-id="68b47-153">Чтобы изменить порядок агентов, в котором им предлагаются звонки в группах с последовательной маршрутизацией или маршрутизацией с циклическим перебором, щелкните агента в списке агентов, а затем нажмите кнопку со стрелкой вверх или вниз.</span><span class="sxs-lookup"><span data-stu-id="68b47-153">To change the order in which agents are offered calls in groups that use either round robin routing or serial routing, in the list of agents, click a user, and then click the up arrow or down arrow.</span></span> 
    
    - <span data-ttu-id="68b47-154">Для использования списка рассылки Microsoft Exchange Server в качестве группы агентов щелкните **Использовать существующий список рассылки электронной почты**, а затем введите адрес электронной почты списка рассылки (например, NetworkSupport@contoso.com) в поле **Адрес списка рассылки**.</span><span class="sxs-lookup"><span data-stu-id="68b47-154">To use a Microsoft Exchange Server distribution list as your agent group, click **Use an existing email distribution list**, and then in **Distribution list address**, type the email address of the distribution list (for example, NetworkSupport@contoso.com).</span></span>
    
      <span data-ttu-id="68b47-155">Если вы используете список рассылки по электронной почте, накладываются следующие ограничения:</span><span class="sxs-lookup"><span data-stu-id="68b47-155">If you use an email distribution list, you are subject to the following constraints:</span></span>
    
      - <span data-ttu-id="68b47-p113">Нельзя выбрать несколько списков рассылки для группы агентов. Каждая группа поддерживает только один список рассылки.</span><span class="sxs-lookup"><span data-stu-id="68b47-p113">You cannot select multiple distribution lists for the agent group. Each group supports only a single distribution list.</span></span>
    
      - <span data-ttu-id="68b47-158">Если список рассылки содержит один или несколько списков рассылки, члены вложенных списков рассылки не добавляются в список агентов.</span><span class="sxs-lookup"><span data-stu-id="68b47-158">If the distribution list contains one or more distribution lists, members of the nested distribution lists are not added to the agent list.</span></span>
    
      - <span data-ttu-id="68b47-159">Если выбрана последовательная маршрутизация или маршрутизация с циклическим перебором, сервер предлагает входящий звонок соответствующему агенту в соответствии с методом маршрутизации и порядком, в котором агенты представлены в списке рассылки.</span><span class="sxs-lookup"><span data-stu-id="68b47-159">If serial or round robin routing is selected, the server offers an incoming call to the appropriate agent according to the routing method and according to the order in which agents are listed in the distribution list.</span></span>
    
      - <span data-ttu-id="68b47-160">Если список рассылки содержит пользователей, для которых включен Lync Server 2010, но Корпоративная голосовая связь не включен, они будут добавлены в группу агентов в качестве неавтоментных агентов.</span><span class="sxs-lookup"><span data-stu-id="68b47-160">If the distribution list contains users for which Lync Server 2010 is enabled but Enterprise Voice is not enabled, they will be added to the agent group as dysfunctional agents.</span></span> <span data-ttu-id="68b47-161">Убедитесь, что все участники списка рассылки Корпоративная голосовая связь для своих учетных записей пользователей.</span><span class="sxs-lookup"><span data-stu-id="68b47-161">Make sure that all members of the distribution list have Enterprise Voice enabled for their user accounts.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="68b47-162">Если вы используете список рассылки электронной почты, скрытые членство или скрытые списки могут стать видимыми администратору или пользователям группы ответа.</span><span class="sxs-lookup"><span data-stu-id="68b47-162">If you use an email distribution list, hidden memberships or hidden lists might become visible to the Response Group administrator or users.</span></span> 
  
    <span data-ttu-id="68b47-163">Скрытое членство или скрытые списки могут отображаться в следующих случаях:</span><span class="sxs-lookup"><span data-stu-id="68b47-163">Hidden memberships or hidden lists can become visible as follows:</span></span>
    
     - <span data-ttu-id="68b47-164">Если список рассылки был настроен таким образом, что членство скрыто, а администратор группы ответа назначает список рассылки списку агентов, пользователи могут вызвать группу, чтобы узнать, кто является ее участниками.</span><span class="sxs-lookup"><span data-stu-id="68b47-164">If a distribution list was configured so that the membership is hidden and the Response Group administrator assigns the distribution list to the agent list, users can call the group to find out who the members are.</span></span> 
    
     - <span data-ttu-id="68b47-165">Если список рассылки был настроен таким образом, что он скрыт в глобальном списке адресов Exchange, администратор группы ответа может увидеть список рассылки и назначить его списку агентов, если процесс группы ответа имеет соответствующие права и разрешения пользователя, даже если у администратора нет соответствующих прав и разрешений.</span><span class="sxs-lookup"><span data-stu-id="68b47-165">If a distribution list was configured so that it is hidden in the Exchange Global Address List, the Response Group administrator might be able to see the distribution list and assign it to the agent list if the Response Group process has the appropriate user rights and permissions, even if the administrator does not have the appropriate user rights and permissions.</span></span>
    
11. <span data-ttu-id="68b47-166">Щелкните **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="68b47-166">Click **Commit**.</span></span>
    
### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-an-agent-group"></a><span data-ttu-id="68b47-167">Использование Skype для бизнеса Server Management Shell для создания или изменения группы агентов</span><span class="sxs-lookup"><span data-stu-id="68b47-167">To use Skype for Business Server Management Shell to create or modify an agent group</span></span>

1. <span data-ttu-id="68b47-168">Войдите как член группы RTCUniversalServerAdmins или как член одной из предопределеных административных ролей, которые поддерживают группу ответа.</span><span class="sxs-lookup"><span data-stu-id="68b47-168">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
2. <span data-ttu-id="68b47-169">Запустите оболочку управления Skype для бизнеса Server: нажмите кнопку "Начните", выберите "Все программы", "Skype для бизнеса **2015",** а затем щелкните "Skype для бизнеса Server Management **Shell".**</span><span class="sxs-lookup"><span data-stu-id="68b47-169">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="68b47-170">Используйте **New-CsRgsAgentGroup** для создания новой группы агентов.</span><span class="sxs-lookup"><span data-stu-id="68b47-170">Use **New-CsRgsAgentGroup** to create a new agent group.</span></span> <span data-ttu-id="68b47-171">Используйте **Set-CsRgsAgentGroup** для изменения существующей группы агентов.</span><span class="sxs-lookup"><span data-stu-id="68b47-171">Use **Set-CsRgsAgentGroup** to modify an existing agent group.</span></span> <span data-ttu-id="68b47-172">В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="68b47-172">At the command line, run:</span></span>
    
   ```powershell
   New-CsRgsAgentGroup -Name "<agent group name>" -Parent $serviceId [-Description "<agent group description>"] -[AgentAlertTime <# seconds until call is routed to next agent>] [-ParticipationPolicy <Formal | Informal>] [-RoutingMethod <method for routing calls>] [-AgentsByUri("<first agent's SIP address>","<second agent's SIP address>")];
   ```

    <span data-ttu-id="68b47-173">Пример:</span><span class="sxs-lookup"><span data-stu-id="68b47-173">For example:</span></span>
    
   ```powershell
   New-CsRgsAgentGroup -Name "Help Desk" -Parent "service:ApplicationServer:atl-cs-001.contoso.com"  -Description "Contoso Help Desk" -AgentAlertTime 20 -ParticipationPolicy Formal -RoutingMethod RoundRobin -AgentsByUri("sip:mindy@contoso.com","sip:bob@contoso.com")
   ```

    > [!IMPORTANT]
    > <span data-ttu-id="68b47-p116">Значение времени оповещения агента не может превышать 180 секунд; в противном случае клиентское приложение отклонит вызов по причине достижения максимального времени ожидания для таймера операций SIP.</span><span class="sxs-lookup"><span data-stu-id="68b47-p116">The agent alert time setting cannot exceed 180 seconds. If the agent alert time is greater than 180 seconds, the client application rejects the call because the SIP transaction timer reaches its maximum wait time.</span></span> 
  
4. <span data-ttu-id="68b47-p117">Чтобы убедиться, что группа агентов была создана, введите:</span><span class="sxs-lookup"><span data-stu-id="68b47-p117">Confirm that the agent group is created. Run:</span></span>
    
   ```powershell
   Get-CsRgsAgentGroup -Name "Help Desk"
   ```

## <a name="see-also"></a><span data-ttu-id="68b47-178">См. также</span><span class="sxs-lookup"><span data-stu-id="68b47-178">See also</span></span>

[<span data-ttu-id="68b47-179">Get-CsService</span><span class="sxs-lookup"><span data-stu-id="68b47-179">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps)
  
[<span data-ttu-id="68b47-180">New-CsRgsAgentGroup</span><span class="sxs-lookup"><span data-stu-id="68b47-180">New-CsRgsAgentGroup</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csrgsagentgroup?view=skype-ps)
  
[<span data-ttu-id="68b47-181">Set-CsRgsAgentGroup</span><span class="sxs-lookup"><span data-stu-id="68b47-181">Set-CsRgsAgentGroup</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csrgsagentgroup?view=skype-ps)
  
[<span data-ttu-id="68b47-182">Get-CsRgsAgentGroup</span><span class="sxs-lookup"><span data-stu-id="68b47-182">Get-CsRgsAgentGroup</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csrgsagentgroup?view=skype-ps)
