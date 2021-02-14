---
title: Создание или изменение существующей группы агентов в группах ответа
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.RgsGroupEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 79eaaf6c-6928-4925-8220-c7ada6b37205
description: Группы агентов определяют, кто может ответить на звонок в группу ответа (которая также называется агентами), а также параметры, применяемые ко всем агентам в этой группе.
ms.openlocfilehash: 19ff8272e70ef56dfb92b537422fddefe0e69842
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49819189"
---
# <a name="response-groups-create-new-or-edit-existing-agent-group"></a><span data-ttu-id="a8528-103">Группы ответа: создание новой или редактирование существующей группы</span><span class="sxs-lookup"><span data-stu-id="a8528-103">Response Groups: Create New or Edit Existing Agent Group</span></span>

<span data-ttu-id="a8528-104">Группы агентов определяют, кто может ответить на звонок в группу ответа (которая также называется агентами), а также параметры, применяемые ко всем агентам в этой группе.</span><span class="sxs-lookup"><span data-stu-id="a8528-104">Agent groups define who can answer calls to a response group (known as agents) and the settings that apply to all the agents in the group.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="a8528-105">Ссылка на пользовательский интерфейс</span><span class="sxs-lookup"><span data-stu-id="a8528-105">UI Reference</span></span>

<span data-ttu-id="a8528-106">В следующем списке описываются поля на странице.</span><span class="sxs-lookup"><span data-stu-id="a8528-106">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="a8528-107">**Имя** Каждой группе агентов требуется уникальное имя.</span><span class="sxs-lookup"><span data-stu-id="a8528-107">**Name** Each agent group requires a unique name.</span></span> <span data-ttu-id="a8528-108">Используйте описательное имя, идентифицирующие функцию группы.</span><span class="sxs-lookup"><span data-stu-id="a8528-108">Use a descriptive name that identifies the group's function.</span></span> <span data-ttu-id="a8528-109">Например, "Help Desk".</span><span class="sxs-lookup"><span data-stu-id="a8528-109">For example, Help Desk.</span></span>

- <span data-ttu-id="a8528-110">**Описание** Это поле является необязательным.</span><span class="sxs-lookup"><span data-stu-id="a8528-110">**Description** This field is optional.</span></span> <span data-ttu-id="a8528-111">Используйте его для предоставления дополнительных сведений о группе.</span><span class="sxs-lookup"><span data-stu-id="a8528-111">Use it to provide additional details about the group.</span></span>

- <span data-ttu-id="a8528-112">**Политика участия** Укажите способ входов агентов в группу ответа:</span><span class="sxs-lookup"><span data-stu-id="a8528-112">**Participation policy** Specify the way that agents are to sign into the response group:</span></span>

  - <span data-ttu-id="a8528-113">Выберите  "Неформальный", чтобы указать, что агентам в группе не требуется вход и выход. Неофициальные агенты автоматически вписываются при входе в неформальные агенты.</span><span class="sxs-lookup"><span data-stu-id="a8528-113">Select **Informal** to specify that the agents in the group do not need to sign in and out. Informal agents are automatically signed in when they sign in.</span></span> <span data-ttu-id="a8528-114">Значение **Свободная** используется по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="a8528-114">The default is **Informal**.</span></span>

  - <span data-ttu-id="a8528-115">Выберите **"Формальный",** чтобы указать, что агенты в группе должны войти и выйти. При выборе этого параметра агенты щелкают пункт меню в клиенте, чтобы открыть браузер и отобразить консоль веб-страницы для входов и выходов.</span><span class="sxs-lookup"><span data-stu-id="a8528-115">Select **Formal** to specify that the agents in the group must sign in and out. When you select this option, agents click a menu item in the client to open a browser and display a web page console for signing in and out.</span></span>

- <span data-ttu-id="a8528-116">**Время оповещения (в секундах)** Укажите время в секундах для звонка агенту, прежде чем предлагать вызов следующему доступного агента.</span><span class="sxs-lookup"><span data-stu-id="a8528-116">**Alert time (seconds)** Specify the number of seconds to ring an agent before offering the call to the next available agent.</span></span> <span data-ttu-id="a8528-117">Значение должно быть не менее 10 секунд и менее 180 секунд.</span><span class="sxs-lookup"><span data-stu-id="a8528-117">The value must be at least 10 seconds and less than 180 seconds.</span></span> <span data-ttu-id="a8528-118">Значение по умолчанию: 20 секунд.</span><span class="sxs-lookup"><span data-stu-id="a8528-118">The default is 20 seconds.</span></span>

- <span data-ttu-id="a8528-119">**Метод маршрутной маршрутки** Выберите метод определения порядка, в котором агенты получают вызовы:</span><span class="sxs-lookup"><span data-stu-id="a8528-119">**Routing method** Select the method for determining the order in which agents receive calls:</span></span>

  - <span data-ttu-id="a8528-120">Выберите **Самый длительный период бездействия**, чтобы предложить новый вызов сначала агенту, который бездействует дольше всех (для которого дольше всего было установлено состояние присутствия **Доступен** или **Неактивен**).</span><span class="sxs-lookup"><span data-stu-id="a8528-120">Select **Longest idle** to offer a new call first to the agent who has been idle (has had a presence of **Available** or **Inactive**) the longest.</span></span>

  - <span data-ttu-id="a8528-p105">Выберите **Параллельно**, чтобы предложить новый вызов одновременно всем доступным агентам. Вызов отправляется первому агенту, который его принимает.</span><span class="sxs-lookup"><span data-stu-id="a8528-p105">Select **Parallel** to offer a new call to all available agents at the same time. The call is sent to the first agent who accepts it.</span></span>

  - <span data-ttu-id="a8528-123">Выберите **Циклический перебор**, чтобы предложить новый вызов каждому агенту по очереди.</span><span class="sxs-lookup"><span data-stu-id="a8528-123">Select **Round robin** to offer a new call to each agent in turn.</span></span>

  - <span data-ttu-id="a8528-124">Выберите **Последовательно**, чтобы всегда предлагать новый вызов агентам в том порядке, в котором они перечислены в списке **Агент**.</span><span class="sxs-lookup"><span data-stu-id="a8528-124">Select **Serial** to always offer a new call to agents in the order in which they are listed in the **Agent** list.</span></span>

  - <span data-ttu-id="a8528-125">Select **Attendant** to offer a new call to all agents who are signed in and the Response Group application at the same time, regardless of their current presence.</span><span class="sxs-lookup"><span data-stu-id="a8528-125">Select **Attendant** to offer a new call to all agents who are signed in and the Response Group application at the same time, regardless of their current presence.</span></span> <span data-ttu-id="a8528-126">Помощники и клиентские пользователи, настроенные в качестве агентов, могут видеть все ожидающие вызовы и отвечать на них в любом порядке.</span><span class="sxs-lookup"><span data-stu-id="a8528-126">Attendants and client users who are configured as agents can see all the calls that are waiting and can answer waiting calls in any order.</span></span> <span data-ttu-id="a8528-127">Вызов отправляется первому агенту, который его принимает, а остальные участники и пользователи больше не видят этот вызов.</span><span class="sxs-lookup"><span data-stu-id="a8528-127">The call is sent to the first agent who accepts it, and the other attendants and users no longer see the call.</span></span>

- <span data-ttu-id="a8528-128">**Агенты** Выберите пользователей, которые будут агентами группы ответа, одним из следующих способов:</span><span class="sxs-lookup"><span data-stu-id="a8528-128">**Agents** Select the users who are to be agents for the response group in one of the following ways:</span></span>

  - <span data-ttu-id="a8528-129">Выберите **"Использовать существующий список рассылки электронной почты** для использования списка рассылки Exchange".</span><span class="sxs-lookup"><span data-stu-id="a8528-129">Select **Use an existing email distribution list** to use an Exchange distribution list.</span></span> <span data-ttu-id="a8528-130">Введите адрес электронной почты списка рассылки в поле **Адрес списка рассылки**.</span><span class="sxs-lookup"><span data-stu-id="a8528-130">Type the email address of the distribution list in **Distribution list address**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a8528-p108">Для группы агентов вы можете выбрать только один список рассылки. Если список содержит вложенные списки рассылки, они не включаются в группу агентов.</span><span class="sxs-lookup"><span data-stu-id="a8528-p108">You can select only one distribution list for an agent group. If the distribution list includes nested distribution lists, the nested distribution lists are not included in the agent group.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a8528-133">Порядок, в котором агенты указаны в списке рассылки, влияет на порядок получения ими вызовов при циклической и последовательной маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="a8528-133">The order in which agents are listed in the distribution list affects the order in which agents receive calls for round robin and serial routing.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a8528-134">Скрытые членство или скрытые списки могут стать видимыми администраторам или пользователям группы ответа.</span><span class="sxs-lookup"><span data-stu-id="a8528-134">Hidden memberships or hidden lists might become visible to Response Group administrators or users.</span></span> <span data-ttu-id="a8528-135">Дополнительные сведения см. в сведениях о создании или [изменении группы агентов в Skype для бизнеса 2015.](../../deploy/deploy-enterprise-voice/create-or-modify-an-agent-group.md)</span><span class="sxs-lookup"><span data-stu-id="a8528-135">For details, see [Create or modify an agent group in Skype for Business 2015](../../deploy/deploy-enterprise-voice/create-or-modify-an-agent-group.md).</span></span>

  - <span data-ttu-id="a8528-p110">Выберите **Определить настраиваемую группу агентов**, чтобы выбрать пользователей, которых требуется назначить в качестве агентов для группы ответа. Щелкните **Выбрать** для добавления агента в список. Щелкните **Удалить** для удаления выбранного агента из списка.</span><span class="sxs-lookup"><span data-stu-id="a8528-p110">Select **Define a custom group of agents** to select the users you want to assign as agents for the response group. Click **Select** to add an agent to the list. Click **Remove** to delete a selected agent from the list.</span></span>

    <span data-ttu-id="a8528-p111">Стрелки вверх и вниз позволяют переместить выбранного агента вверх и вниз в списке агентов. Порядок агентов в списке влияет на порядок получения ими вызовов при циклической и последовательной маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="a8528-p111">The up and down arrows move a selected agent up and down in the agent list. The order of agents in the list affects the order in which agents receive calls for round robin and serial routing.</span></span>

<span data-ttu-id="a8528-141">For details about Response Group features and capabilities, see [Plan for the Response Group application in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/response-group.md) in the Planning documentation.</span><span class="sxs-lookup"><span data-stu-id="a8528-141">For details about Response Group features and capabilities, see [Plan for the Response Group application in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/response-group.md) in the Planning documentation.</span></span> <span data-ttu-id="a8528-142">Дополнительные сведения о работе с группами агентов см. в разделе [Managing Agent Groups](https://technet.microsoft.com/library/36084cdc-38f1-4c45-922f-f81c7e86210c.aspx) документации по использованию.</span><span class="sxs-lookup"><span data-stu-id="a8528-142">For details about working with agent groups, see [Managing Agent Groups](https://technet.microsoft.com/library/36084cdc-38f1-4c45-922f-f81c7e86210c.aspx) in the Operations documentation.</span></span>


