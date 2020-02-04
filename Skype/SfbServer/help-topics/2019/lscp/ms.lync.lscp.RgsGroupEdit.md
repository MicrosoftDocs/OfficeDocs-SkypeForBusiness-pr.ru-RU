---
title: Группы ответов создание новой или изменение существующей группы агента
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.RgsGroupEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 79eaaf6c-6928-4925-8220-c7ada6b37205
ROBOTS: NOINDEX, NOFOLLOW
description: Группы агентов определяют, кто может ответить на звонок в группу ответа (которая также называется агентами), а также параметры, применяемые ко всем агентам в этой группе.
ms.openlocfilehash: 2fde88426c659492cff350007b7e88a53581c67d
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2020
ms.locfileid: "41690914"
---
# <a name="response-groups-create-new-or-edit-existing-agent-group"></a><span data-ttu-id="2394d-103">Группы ответа: создание новой или редактирование существующей группы</span><span class="sxs-lookup"><span data-stu-id="2394d-103">Response Groups: Create New or Edit Existing Agent Group</span></span>

<span data-ttu-id="2394d-104">Группы агентов определяют, кто может ответить на звонок в группу ответа (которая также называется агентами), а также параметры, применяемые ко всем агентам в этой группе.</span><span class="sxs-lookup"><span data-stu-id="2394d-104">Agent groups define who can answer calls to a response group (known as agents) and the settings that apply to all the agents in the group.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="2394d-105">Ссылка на пользовательский интерфейс</span><span class="sxs-lookup"><span data-stu-id="2394d-105">UI Reference</span></span>

<span data-ttu-id="2394d-106">В следующем списке описываются поля на странице.</span><span class="sxs-lookup"><span data-stu-id="2394d-106">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="2394d-107">**Name (имя** ) Каждая группа агента должна иметь уникальное имя.</span><span class="sxs-lookup"><span data-stu-id="2394d-107">**Name** Each agent group requires a unique name.</span></span> <span data-ttu-id="2394d-108">Используйте описательное имя, которое определяет функцию группы.</span><span class="sxs-lookup"><span data-stu-id="2394d-108">Use a descriptive name that identifies the group's function.</span></span> <span data-ttu-id="2394d-109">Например, службы поддержки.</span><span class="sxs-lookup"><span data-stu-id="2394d-109">For example, Help Desk.</span></span>

- <span data-ttu-id="2394d-110">**Description (описание** ) Это поле является необязательным.</span><span class="sxs-lookup"><span data-stu-id="2394d-110">**Description** This field is optional.</span></span> <span data-ttu-id="2394d-111">Используйте его для предоставления дополнительных сведений о группе.</span><span class="sxs-lookup"><span data-stu-id="2394d-111">Use it to provide additional details about the group.</span></span>

- <span data-ttu-id="2394d-112">**Политика участия** Укажите, как агенты должны входить в группу ответа.</span><span class="sxs-lookup"><span data-stu-id="2394d-112">**Participation policy** Specify the way that agents are to sign into the response group:</span></span>

  - <span data-ttu-id="2394d-p103">Выберите значение **Свободная**, чтобы указать, что агентам в группе не требуется совершать вход и выход. Свободные агенты автоматически входят в систему при входе. Значение **Свободная** используется по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="2394d-p103">Select **Informal** to specify that the agents in the group do not need to sign in and out. Informal agents are automatically signed in when they sign in. The default is **Informal**.</span></span>

  - <span data-ttu-id="2394d-115">Выберите **формально** , чтобы указать, что агенты в группе должны входить и выписываться. При выборе этого параметра агенты щелкают элемент меню в клиенте, чтобы открыть браузер и отобразить консоль веб-страницы для входа и выхода из нее.</span><span class="sxs-lookup"><span data-stu-id="2394d-115">Select **Formal** to specify that the agents in the group must sign in and out. When you select this option, agents click a menu item in the client to open a browser and display a web page console for signing in and out.</span></span>

- <span data-ttu-id="2394d-116">**Время оповещения (в секундах)** Укажите время (в секундах), по истечении которого агент должен звонить на следующий доступный агент.</span><span class="sxs-lookup"><span data-stu-id="2394d-116">**Alert time (seconds)** Specify the number of seconds to ring an agent before offering the call to the next available agent.</span></span> <span data-ttu-id="2394d-117">Значение должно составлять не менее 10 секунд и менее 180 секунд.</span><span class="sxs-lookup"><span data-stu-id="2394d-117">The value must be at least 10 seconds and less than 180 seconds.</span></span> <span data-ttu-id="2394d-118">Значение по умолчанию — 20 секунд.</span><span class="sxs-lookup"><span data-stu-id="2394d-118">The default is 20 seconds.</span></span>

- <span data-ttu-id="2394d-119">**Метод маршрутизации** Выберите способ определения порядка, в котором агенты получают звонки:</span><span class="sxs-lookup"><span data-stu-id="2394d-119">**Routing method** Select the method for determining the order in which agents receive calls:</span></span>

  - <span data-ttu-id="2394d-120">Выберите **Самый длительный период бездействия**, чтобы предложить новый вызов сначала агенту, который бездействует дольше всех (для которого дольше всего было установлено состояние присутствия **Доступен** или **Неактивен**).</span><span class="sxs-lookup"><span data-stu-id="2394d-120">Select **Longest idle** to offer a new call first to the agent who has been idle (has had a presence of **Available** or **Inactive**) the longest.</span></span>

  - <span data-ttu-id="2394d-p105">Выберите **Параллельно**, чтобы предложить новый вызов одновременно всем доступным агентам. Вызов отправляется первому агенту, который его принимает.</span><span class="sxs-lookup"><span data-stu-id="2394d-p105">Select **Parallel** to offer a new call to all available agents at the same time. The call is sent to the first agent who accepts it.</span></span>

  - <span data-ttu-id="2394d-123">Выберите **Циклический перебор**, чтобы предложить новый вызов каждому агенту по очереди.</span><span class="sxs-lookup"><span data-stu-id="2394d-123">Select **Round robin** to offer a new call to each agent in turn.</span></span>

  - <span data-ttu-id="2394d-124">Выберите **Последовательно**, чтобы всегда предлагать новый вызов агентам в том порядке, в котором они перечислены в списке **Агент**.</span><span class="sxs-lookup"><span data-stu-id="2394d-124">Select **Serial** to always offer a new call to agents in the order in which they are listed in the **Agent** list.</span></span>

  - <span data-ttu-id="2394d-125">Выберите **секретарь** , чтобы предложить новый звонок всем агентам, которые вошли в систему, а приложение группы ответа — независимо от их текущего присутствия.</span><span class="sxs-lookup"><span data-stu-id="2394d-125">Select **Attendant** to offer a new call to all agents who are signed in and the Response Group application at the same time, regardless of their current presence.</span></span> <span data-ttu-id="2394d-126">Ассистенты и пользователи клиента, настроенные как агенты, могут просматривать все ожидающие звонки, а также отвечать на запросы в любом порядке.</span><span class="sxs-lookup"><span data-stu-id="2394d-126">Attendants and client users who are configured as agents can see all the calls that are waiting and can answer waiting calls in any order.</span></span> <span data-ttu-id="2394d-127">Вызов передается первому принимающему его агенту, а другие участники и пользователи больше не видят этот вызов.</span><span class="sxs-lookup"><span data-stu-id="2394d-127">The call is sent to the first agent who accepts it, and the other attendants and users no longer see the call.</span></span>

- <span data-ttu-id="2394d-128">**Агенты** Выберите пользователей, которые должны быть агентами для группы ответа, одним из указанных ниже способов.</span><span class="sxs-lookup"><span data-stu-id="2394d-128">**Agents** Select the users who are to be agents for the response group in one of the following ways:</span></span>

  - <span data-ttu-id="2394d-129">Выберите **использовать существующий список рассылки электронной почты** , чтобы использовать список рассылки Exchange.</span><span class="sxs-lookup"><span data-stu-id="2394d-129">Select **Use an existing email distribution list** to use an Exchange distribution list.</span></span> <span data-ttu-id="2394d-130">Введите адрес электронной почты списка рассылки в поле **Адрес списка рассылки**.</span><span class="sxs-lookup"><span data-stu-id="2394d-130">Type the email address of the distribution list in **Distribution list address**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2394d-p108">Для группы агентов вы можете выбрать только один список рассылки. Если список содержит вложенные списки рассылки, они не включаются в группу агентов.</span><span class="sxs-lookup"><span data-stu-id="2394d-p108">You can select only one distribution list for an agent group. If the distribution list includes nested distribution lists, the nested distribution lists are not included in the agent group.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2394d-133">Порядок, в котором агенты указаны в списке рассылки, влияет на порядок получения ими вызовов при циклической и последовательной маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="2394d-133">The order in which agents are listed in the distribution list affects the order in which agents receive calls for round robin and serial routing.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2394d-134">Скрытые и скрытые списки могут стать видимыми для администраторов и пользователей группы ответа.</span><span class="sxs-lookup"><span data-stu-id="2394d-134">Hidden memberships or hidden lists might become visible to Response Group administrators or users.</span></span> <span data-ttu-id="2394d-135">Подробные сведения можно найти [в разделе Создание или изменение группы агента в Skype для бизнеса](../../../deploy/deploy-enterprise-voice/create-or-modify-an-agent-group.md).</span><span class="sxs-lookup"><span data-stu-id="2394d-135">For details, see [Create or modify an agent group in Skype for Business](../../../deploy/deploy-enterprise-voice/create-or-modify-an-agent-group.md).</span></span>

  - <span data-ttu-id="2394d-p110">Выберите **Определить настраиваемую группу агентов**, чтобы выбрать пользователей, которых требуется назначить в качестве агентов для группы ответа. Нажмите **Выбрать** для добавления агента в список или **Удалить** для удаления выбранного агента из списка.</span><span class="sxs-lookup"><span data-stu-id="2394d-p110">Select **Define a custom group of agents** to select the users you want to assign as agents for the response group. Click **Select** to add an agent to the list. Click **Remove** to delete a selected agent from the list.</span></span>

    <span data-ttu-id="2394d-p111">Стрелки вверх и вниз позволяют переместить выбранного агента вверх и вниз в списке агентов. Порядок агентов в списке влияет на порядок получения ими вызовов при циклической и последовательной маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="2394d-p111">The up and down arrows move a selected agent up and down in the agent list. The order of agents in the list affects the order in which agents receive calls for round robin and serial routing.</span></span>

<span data-ttu-id="2394d-141">Дополнительные сведения о функциях и возможностях групп ответов можно найти [в разделе Планирование приложения группы ответа в Skype для бизнеса Server](../../../plan-your-deployment/enterprise-voice-solution/response-group.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="2394d-141">For details about Response Group features and capabilities, see [Plan for the Response Group application in Skype for Business Server](../../../plan-your-deployment/enterprise-voice-solution/response-group.md) in the Planning documentation.</span></span> <span data-ttu-id="2394d-142">Дополнительные сведения о работе с группами агентов см. в разделе [Managing Agent Groups](https://technet.microsoft.com/library/36084cdc-38f1-4c45-922f-f81c7e86210c.aspx) документации по использованию.</span><span class="sxs-lookup"><span data-stu-id="2394d-142">For details about working with agent groups, see [Managing Agent Groups](https://technet.microsoft.com/library/36084cdc-38f1-4c45-922f-f81c7e86210c.aspx) in the Operations documentation.</span></span>


