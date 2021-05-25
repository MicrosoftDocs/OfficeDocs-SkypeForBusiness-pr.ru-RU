---
title: Создание очереди вызовов в Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: colongma
ms.topic: article
ms.assetid: 67ccda94-1210-43fb-a25b-7b9785f8a061
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.callqueues.overview"
- Phone System
- seo-marvel-apr2020
description: Узнайте, как настроить очереди вызовов для крупных организаций в Microsoft Teams, которая предоставляет приветствие, музыку, перенаправление звонка и другие функции.
ms.openlocfilehash: 926e3903f0ee59271d0b4806cf61ad02a6f52088
ms.sourcegitcommit: 330e60ff3549cd5cff5b52ad95dc4259e4e8de13
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/24/2021
ms.locfileid: "52628938"
---
# <a name="create-a-call-queue"></a><span data-ttu-id="91a43-103">Создание очереди вызовов</span><span class="sxs-lookup"><span data-stu-id="91a43-103">Create a call queue</span></span>

<span data-ttu-id="91a43-104">Очереди вызовов предоставляют способ маршрутизации вызывающих людей в организации, которые могут помочь с определенной проблемой или вопросом.</span><span class="sxs-lookup"><span data-stu-id="91a43-104">Call queues provide a method of routing callers to people in your organization who can help with a particular issue or question.</span></span> <span data-ttu-id="91a43-105">Звонки распределяются по одному для людей, которые находятся в очереди (которые называются *агентами).*</span><span class="sxs-lookup"><span data-stu-id="91a43-105">Calls are distributed one at a time to the people in the queue (who are known as *agents*).</span></span> 

> [!TIP]
> <span data-ttu-id="91a43-106">Эта статья посвящена крупным организациям.</span><span class="sxs-lookup"><span data-stu-id="91a43-106">This article is large organizations.</span></span> <span data-ttu-id="91a43-107">Если ваша организация малого бизнеса, ознакомьтесь с учебным учебником Создание очереди вызовов [для малого](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb) бизнеса.</span><span class="sxs-lookup"><span data-stu-id="91a43-107">If your organization is a small business, read [Create a call queue - small business tutorial](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb) instead.</span></span>

<span data-ttu-id="91a43-108">Очереди вызовов предоставляют:</span><span class="sxs-lookup"><span data-stu-id="91a43-108">Call queues provide:</span></span>

- <span data-ttu-id="91a43-109">Приветствие.</span><span class="sxs-lookup"><span data-stu-id="91a43-109">A greeting message.</span></span>

- <span data-ttu-id="91a43-110">Музыка, пока люди находятся на удержании в очереди.</span><span class="sxs-lookup"><span data-stu-id="91a43-110">Music while people are waiting on hold in a queue.</span></span>

- <span data-ttu-id="91a43-111">Маршрутия вызовов — в порядке first *In, First Out* (FIFO) — агентам.</span><span class="sxs-lookup"><span data-stu-id="91a43-111">Call routing - in *First In, First Out* (FIFO) order - to agents.</span></span>

- <span data-ttu-id="91a43-112">Параметры обработки для переполнения и времени ожидания в очереди.</span><span class="sxs-lookup"><span data-stu-id="91a43-112">Handling options for queue overflow and timeout.</span></span>

<span data-ttu-id="91a43-113">Прежде чем выполнять действия, которые вы выполните в этой [](plan-auto-attendant-call-queue.md#getting-started) [статье, ознакомьтесь](plan-auto-attendant-call-queue.md) со статьей Планирование работы с Teams и очередей вызовов и следуйте этим шагам.</span><span class="sxs-lookup"><span data-stu-id="91a43-113">Be sure you have read [Plan for Teams auto attendants and call queues](plan-auto-attendant-call-queue.md) and followed the [getting started steps](plan-auto-attendant-call-queue.md#getting-started) before you follow the procedures in this article.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="91a43-114">Демонстрация видео</span><span class="sxs-lookup"><span data-stu-id="91a43-114">Video demonstration</span></span>

<span data-ttu-id="91a43-115">В этом видео показан простой пример создания очереди вызовов в Teams.</span><span class="sxs-lookup"><span data-stu-id="91a43-115">This video shows a basic example of how to create a call queue in Teams.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWCF23?autoplay=false]

## <a name="create-the-call-queue"></a><span data-ttu-id="91a43-116">Создание очереди вызовов</span><span class="sxs-lookup"><span data-stu-id="91a43-116">Create the call queue</span></span>

<span data-ttu-id="91a43-117">Чтобы настроить очередь вызовов, в Центре администрирования Teams Разойдите в центр администрирования Голосовая почта **,** щелкните Очереди зовов **и** нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="91a43-117">To set up a call queue, in the Teams admin center, expand **Voice**, click **Call queues**, and then click **Add**.</span></span>

### <a name="resource-account-and-language"></a><span data-ttu-id="91a43-118">Учетная запись ресурса и язык</span><span class="sxs-lookup"><span data-stu-id="91a43-118">Resource account and language</span></span>

![Снимок экрана: учетная запись ресурса и языковые параметры](media/call-queue-name-language.png)

1. <span data-ttu-id="91a43-120">Введите имя очереди вызовов.</span><span class="sxs-lookup"><span data-stu-id="91a43-120">Type a name for the call queue.</span></span>

2. <span data-ttu-id="91a43-121">Нажмите **кнопку Добавить учетные** записи , найдите учетную запись ресурса, которую вы хотите использовать с этой очередью вызовов, нажмите кнопку **Добавить,** а затем нажмите кнопку **Добавить.**</span><span class="sxs-lookup"><span data-stu-id="91a43-121">Click **Add accounts**, search for the resource account that you want to use with this call queue, click **Add**, and then click **Add**.</span></span> <span data-ttu-id="91a43-122">(Агенты увидят имя учетной записи ресурса, когда получат входящий звонок.)</span><span class="sxs-lookup"><span data-stu-id="91a43-122">(Agents will see the resource account name when they receive an incoming call.)</span></span>

3. <span data-ttu-id="91a43-123">Выберите [поддерживаемый язык.](create-a-phone-system-call-queue-languages.md)</span><span class="sxs-lookup"><span data-stu-id="91a43-123">Choose a [supported language](create-a-phone-system-call-queue-languages.md).</span></span> <span data-ttu-id="91a43-124">Этот язык будет использоваться для системных голосовых подсказок и транскрибации голосовой почты (если вы их включаете).</span><span class="sxs-lookup"><span data-stu-id="91a43-124">This language will be used for system-generated voice prompts and voicemail transcription (if you enable them).</span></span>

### <a name="greetings-and-music-on-hold-in-queue"></a><span data-ttu-id="91a43-125">Приветствия и музыка на удержании в очереди</span><span class="sxs-lookup"><span data-stu-id="91a43-125">Greetings and music on hold in queue</span></span>

<span data-ttu-id="91a43-126">Укажите, хотите ли вы, чтобы вызыватели могли разозвать приветствие при их поступления в очередь.</span><span class="sxs-lookup"><span data-stu-id="91a43-126">Specify if you want to play a greeting to callers when they arrive in the queue.</span></span> <span data-ttu-id="91a43-127">Необходимо отправить файл MP3, WAV или WMA, содержащий приветствие, которое вы хотите воспроизведения.</span><span class="sxs-lookup"><span data-stu-id="91a43-127">You must upload an MP3, WAV, or WMA file containing the greeting that you want to play.</span></span>

<span data-ttu-id="91a43-128">Teams предоставляет вызывателям музыку по умолчанию, когда они находятся на удержании в очереди.</span><span class="sxs-lookup"><span data-stu-id="91a43-128">Teams provides default music to callers while they are on hold in a queue.</span></span> <span data-ttu-id="91a43-129">Если вы хотите воспроизведения определенного  звукового файла, выберите Вариант воспроизведения звукового файла и загрузите файл MP3, WAV или WMA.</span><span class="sxs-lookup"><span data-stu-id="91a43-129">If you want to play a specific audio file, choose **Play an audio file** and upload an MP3, WAV, or WMA file.</span></span>

> [!NOTE]
> <span data-ttu-id="91a43-130">Размер загруженной записи не должен быть больше 5 МБ.</span><span class="sxs-lookup"><span data-stu-id="91a43-130">The uploaded recording can be no larger than 5 MB.</span></span>
> <span data-ttu-id="91a43-131">По умолчанию музыка, которая поставляется Teams очередях вызовов, не предоставляется вашей организацией.</span><span class="sxs-lookup"><span data-stu-id="91a43-131">The default music supplied in Teams call queues is free of any royalties payable by your organization.</span></span> 

### <a name="call-agents"></a><span data-ttu-id="91a43-132">Агенты вызовов</span><span class="sxs-lookup"><span data-stu-id="91a43-132">Call agents</span></span>

<span data-ttu-id="91a43-133">Просмотрите [предварительные условия для добавления агентов в очередь вызовов.](plan-auto-attendant-call-queue.md#prerequisites)</span><span class="sxs-lookup"><span data-stu-id="91a43-133">Review the [prerequisites for adding agents to a call queue](plan-auto-attendant-call-queue.md#prerequisites).</span></span>

![Снимок экрана: параметры пользователей и групп для очередей вызовов](media/call-queue-users-groups.png)

##### <a name="teams-channel"></a><span data-ttu-id="91a43-135">Teams канале</span><span class="sxs-lookup"><span data-stu-id="91a43-135">Teams channel</span></span>

<span data-ttu-id="91a43-136">Вы можете добавить до 200 агентов через Teams канале.</span><span class="sxs-lookup"><span data-stu-id="91a43-136">You can add up to 200 agents via a Teams channel.</span></span>

<span data-ttu-id="91a43-137">Если вы хотите [использовать канал Teams](https://support.microsoft.com/office/9f07dabe-91c6-4a9b-a545-8ffdddd2504e)для управления очередью, выберите команду Выбрать команду и щелкните Добавить **канал**. </span><span class="sxs-lookup"><span data-stu-id="91a43-137">If you want to [use a Teams channel to manage the queue](https://support.microsoft.com/office/9f07dabe-91c6-4a9b-a545-8ffdddd2504e), select the **Choose a team** option and click **Add a channel**.</span></span> <span data-ttu-id="91a43-138">Найдите команду, которую хотите использовать, выберите ее и нажмите кнопку **Добавить.**</span><span class="sxs-lookup"><span data-stu-id="91a43-138">Search for the team that you want to use, select it, and click **Add**.</span></span> <span data-ttu-id="91a43-139">Выберите канал, который вы хотите использовать, и нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="91a43-139">Select the channel that you want to use and click **Apply**.</span></span>

<span data-ttu-id="91a43-140">При использовании канала Teams для очередей вызовов поддерживаются следующие клиенты:</span><span class="sxs-lookup"><span data-stu-id="91a43-140">The following clients are supported when using a Teams channel for call queues:</span></span> 

  - <span data-ttu-id="91a43-141">Microsoft Teams Windows клиента</span><span class="sxs-lookup"><span data-stu-id="91a43-141">Microsoft Teams Windows client</span></span>
  - <span data-ttu-id="91a43-142">Клиент Microsoft Teams Mac</span><span class="sxs-lookup"><span data-stu-id="91a43-142">Microsoft Teams Mac client</span></span>

##### <a name="users-and-groups"></a><span data-ttu-id="91a43-143">Пользователи и группы</span><span class="sxs-lookup"><span data-stu-id="91a43-143">Users and groups</span></span>

<span data-ttu-id="91a43-144">Вы можете добавить до 20 агентов по отдельности и до 200 агентов с помощью групп.</span><span class="sxs-lookup"><span data-stu-id="91a43-144">You can add up to 20 agents individually and up to 200 agents via groups.</span></span>

<span data-ttu-id="91a43-145">Если вы хотите добавить отдельных пользователей или группы в очередь, выберите **параметр Выбрать пользователей и** группы.</span><span class="sxs-lookup"><span data-stu-id="91a43-145">If you want to add individual users or groups to the queue, select the **Choose users and groups** option.</span></span> 

<span data-ttu-id="91a43-146">Чтобы добавить пользователя в очередь, нажмите **кнопку** Добавить пользователей , найдите пользователя, нажмите кнопку Добавить **и** выберите **добавить**.</span><span class="sxs-lookup"><span data-stu-id="91a43-146">To add a user to the queue, click **Add users**, search for the user, click **Add**, and then click **Add**.</span></span>

<span data-ttu-id="91a43-147">Чтобы добавить группу в очередь, нажмите кнопку Добавить группы **,** найдите группу, нажмите кнопку Добавить **и** выберите **добавить**.</span><span class="sxs-lookup"><span data-stu-id="91a43-147">To add a group to the queue, click **Add groups**, search for the group, click **Add**, and then click **Add**.</span></span> <span data-ttu-id="91a43-148">Вы можете использовать списки рассылки, группы безопасности и Microsoft 365 группы или Microsoft Teams группы.</span><span class="sxs-lookup"><span data-stu-id="91a43-148">You can use distribution lists, security groups, and Microsoft 365 groups or Microsoft Teams teams.</span></span>

> [!NOTE]
> <span data-ttu-id="91a43-149">Первые вызовы новых пользователей, добавленных в группу, могут принимать до восьми часов.</span><span class="sxs-lookup"><span data-stu-id="91a43-149">New users added to a group can take up to eight hours for their first call to arrive.</span></span>

### <a name="call-routing"></a><span data-ttu-id="91a43-150">Маршрутизация вызовов</span><span class="sxs-lookup"><span data-stu-id="91a43-150">Call routing</span></span>

![Снимок экрана: режим конференции и параметры метода маршрутации](media/call-queue-conference-mode-routing-method.png)

<span data-ttu-id="91a43-152">**Режим конференции** значительно сокращает время, необходимое для связи звоняного с агентом, после того как агент принимает звонок.</span><span class="sxs-lookup"><span data-stu-id="91a43-152">**Conference mode** significantly reduces the amount of time it takes for a caller to be connected to an agent, after the agent accepts the call.</span></span> <span data-ttu-id="91a43-153">Чтобы режим конференции работал, агенты в очереди зовов должны использовать один из следующих клиентов:</span><span class="sxs-lookup"><span data-stu-id="91a43-153">For conference mode to work, agents in the call queue must use one of the following clients:</span></span>

  - <span data-ttu-id="91a43-154">Последняя версия клиента Microsoft Teams, приложения для Android или приложения для iOS</span><span class="sxs-lookup"><span data-stu-id="91a43-154">The latest version of the Microsoft Teams desktop client, Android app, or iOS app</span></span>
  - <span data-ttu-id="91a43-155">Microsoft Teams версии телефона 1449/1.0.94.2020051601 или более поздней</span><span class="sxs-lookup"><span data-stu-id="91a43-155">Microsoft Teams phone version 1449/1.0.94.2020051601 or later</span></span>
  
<span data-ttu-id="91a43-156">Для Teams агентов необходимо настроить режим Teams только для агентов.</span><span class="sxs-lookup"><span data-stu-id="91a43-156">Agents' Teams accounts need to be set to Teams-only mode.</span></span> <span data-ttu-id="91a43-157">Агенты, не отвечающие требованиям, не включаются в список маршрутов зовов.</span><span class="sxs-lookup"><span data-stu-id="91a43-157">Agents who don't meet the requirements aren't included in the call routing list.</span></span> <span data-ttu-id="91a43-158">Мы рекомендуем использовать режим конференции для очередей вызовов, если все ваши агенты используют совместимые клиенты.</span><span class="sxs-lookup"><span data-stu-id="91a43-158">We recommend enabling conference mode for your call queues if your agents are all using compatible clients.</span></span>

> [!NOTE]
> <span data-ttu-id="91a43-159">Режим конференции не поддерживается, если телефонные звонки перенаправлются в очередь из шлюза прямой маршрутации, который включен для маршрутизов по расположению.</span><span class="sxs-lookup"><span data-stu-id="91a43-159">Conference mode is not supported if phone calls are routed to the queue from a Direct Routing gateway that is enabled for Location Based Routing.</span></span>

<span data-ttu-id="91a43-160">**Способ маршрутики определяет** порядок, в котором агенты будут принимать звонки из очереди.</span><span class="sxs-lookup"><span data-stu-id="91a43-160">**Routing method** determines the order in which agents receive calls from the queue.</span></span> <span data-ttu-id="91a43-161">Выберите один из этих вариантов:</span><span class="sxs-lookup"><span data-stu-id="91a43-161">Choose from these options:</span></span>

- <span data-ttu-id="91a43-162">**Маршруты помощника одновременно** звонят всем агентам в очереди.</span><span class="sxs-lookup"><span data-stu-id="91a43-162">**Attendant routing** rings all agents in the queue at the same time.</span></span> <span data-ttu-id="91a43-163">Звонок получит первый агент звонка.</span><span class="sxs-lookup"><span data-stu-id="91a43-163">The first call agent to pick up the call gets the call.</span></span>

- <span data-ttu-id="91a43-164">**Порядковая маршрутия** звонит всем агентам по одному в порядке, указанном в списке **"Агенты звонка".**</span><span class="sxs-lookup"><span data-stu-id="91a43-164">**Serial routing** rings all call agents one by one in the order specified in the **Call agents** list.</span></span> <span data-ttu-id="91a43-165">Если агент отклоает звонок или не звонит, звонок звонит следующему агенту и пробует всех агентов до тех пор, пока он не будет отклонен или не будет разозваться.</span><span class="sxs-lookup"><span data-stu-id="91a43-165">If an agent dismisses or does not pick up a call, the call will ring the next agent and will try all agents until it is picked up or times out.</span></span>

- <span data-ttu-id="91a43-166">**Round balances** the routing of incoming calls so each call agent gets the same number of calls from the queue.</span><span class="sxs-lookup"><span data-stu-id="91a43-166">**Round robin** balances the routing of incoming calls so that each call agent gets the same number of calls from the queue.</span></span> <span data-ttu-id="91a43-167">Это может быть нежелательно в среде входящие продаж, чтобы обеспечить равные возможности для всех агентов звонка.</span><span class="sxs-lookup"><span data-stu-id="91a43-167">This may be desirable in an inbound sales environment to assure equal opportunity among all the call agents.</span></span>

- <span data-ttu-id="91a43-168">**Наиболее длинные** неавтоматные маршруты каждый звонок передается агенту, который простаивает в течение долгого времени.</span><span class="sxs-lookup"><span data-stu-id="91a43-168">**Longest idle** routes each call to the agent who has been idle the longest time.</span></span> <span data-ttu-id="91a43-169">Агент считается неающим, если его состояние присутствия доступно или состояние присутствия "Нет на нем" менее 10 минут.</span><span class="sxs-lookup"><span data-stu-id="91a43-169">An agent is considered idle if their presence state is Available or if their presence state has been Away for less than 10 minutes.</span></span> <span data-ttu-id="91a43-170">Агенты, состояние присутствия которых отсутствует более 10 минут, не считаются неавтными и не смогут принимать звонки, пока они не изменят свое состояние присутствия на В сети.</span><span class="sxs-lookup"><span data-stu-id="91a43-170">Agents whose presence state has been Away for more than 10 minutes are not considered idle and will not be eligible to receive calls until they change their presence to Available.</span></span> 

![Снимок экрана: параметры времени маршрутки, отказа и оповещений](media/call-queue-presence-agents-time.png)


<span data-ttu-id="91a43-172">**В маршрутике** на основе присутствия используется состояние доступности агентов звонка, чтобы определить, следует ли включить агента в список маршрутов зовов для выбранного метода маршрутики.</span><span class="sxs-lookup"><span data-stu-id="91a43-172">**Presence-based routing** uses the availability status of call agents to determine whether an agent should be included in the call routing list for the selected routing method.</span></span> <span data-ttu-id="91a43-173">Звонки от агентов, у  которых установлено состояние "В наличии", включаются в список маршрутов звонков и могут принимать звонки.</span><span class="sxs-lookup"><span data-stu-id="91a43-173">Call agents whose availability status is set to **Available** are included in the call routing list and can receive calls.</span></span> <span data-ttu-id="91a43-174">Агенты, состояние доступности которых имеет любое другое состояние, исключаются из списка маршрутов звонков и не будут получать звонки, пока их состояние доступности не изменится на **Доступно.**</span><span class="sxs-lookup"><span data-stu-id="91a43-174">Agents whose availability status is set to any other status are excluded from the call routing list and won't receive calls until their availability status changes back to **Available**.</span></span> 

<span data-ttu-id="91a43-175">Вы можете включить маршрутику вызовов на основе присутствия с помощью любого из способов маршрутизов.</span><span class="sxs-lookup"><span data-stu-id="91a43-175">You can enable presence-based call routing with any of the routing methods.</span></span>

<span data-ttu-id="91a43-176">Если агент отключит получение звонков, он не будет включен в список маршрутов звонков независимо от состояния доступности.</span><span class="sxs-lookup"><span data-stu-id="91a43-176">If an agent opts out of getting calls, they won't be included in the call routing list regardless of what their availability status is set to.</span></span> 

> [!NOTE]
> <span data-ttu-id="91a43-177">Агенты, которые используют Skype для бизнеса клиента, не включаются в список маршрутов зовов, если включена маршрутия на основе присутствия.</span><span class="sxs-lookup"><span data-stu-id="91a43-177">Agents who use the Skype for Business client aren't included in the call routing list when presence-based routing is enabled.</span></span> <span data-ttu-id="91a43-178">Если у вас есть агенты, Skype для бизнеса, не в включаете маршрутику вызовов на основе присутствия.</span><span class="sxs-lookup"><span data-stu-id="91a43-178">If you have agents who use Skype for Business, don't enable presence-based call routing.</span></span>

<span data-ttu-id="91a43-179">**Время оповещения агента** определяет, как долго телефон агента будет звонить, прежде чем очередь перенаправит звонок следующему агенту.</span><span class="sxs-lookup"><span data-stu-id="91a43-179">**Agent alert time** specifies how long an agent's phone will ring before the queue redirects the call to the next agent.</span></span>

<span data-ttu-id="91a43-180">Рекомендуется использовать следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="91a43-180">The following settings are recommended:</span></span>

- <span data-ttu-id="91a43-181">**Режим конференции с** **автоматическим**</span><span class="sxs-lookup"><span data-stu-id="91a43-181">**Conference mode** to **Auto**</span></span>
- <span data-ttu-id="91a43-182">**Способ маршрутинга до** **round или** **longest idle**</span><span class="sxs-lookup"><span data-stu-id="91a43-182">**Routing method** to **Round robin** or **Longest idle**</span></span>
- <span data-ttu-id="91a43-183">**Маршруты на основе присутствия в** В **сети**</span><span class="sxs-lookup"><span data-stu-id="91a43-183">**Presence-based routing** to **On**</span></span>
- <span data-ttu-id="91a43-184">**Время оповещения агента:** **до 20 секунд**</span><span class="sxs-lookup"><span data-stu-id="91a43-184">**Agent alert time:** to **20 seconds**</span></span>

> [!NOTE]
> <span data-ttu-id="91a43-185">Если маршрутия на основе присутствия не включена и в очереди несколько звонков, система будет одновременно представлять эти звонки агентам независимо от их состояния присутствия.</span><span class="sxs-lookup"><span data-stu-id="91a43-185">If presence-based routing is not enabled and there are multiple calls in the queue, the system will present these calls simultaneously to the agents regardless of their presence status.</span></span> <span data-ttu-id="91a43-186">В результате агенты получат несколько уведомлений о звонках, особенно если некоторые агенты не ответят на первоначальный звонок.</span><span class="sxs-lookup"><span data-stu-id="91a43-186">This will result in multiple call notifications to agents, particularly if some agents don’t answer the initial call presented to them.</span></span>

### <a name="call-overflow-handling"></a><span data-ttu-id="91a43-187">Обработка переполнения вызовов</span><span class="sxs-lookup"><span data-stu-id="91a43-187">Call overflow handling</span></span>

![Снимок экрана: параметры переполнения звонка](media/call-queue-overflow-handling.png)

<span data-ttu-id="91a43-189">**Максимальное число звонков** в очереди определяет максимальное количество звонков, которые могут быть в очереди в любое время.</span><span class="sxs-lookup"><span data-stu-id="91a43-189">**Maximum calls in the queue** specifies the maximum number of calls that can wait in the queue at any given time.</span></span> <span data-ttu-id="91a43-190">Значение по умолчанию — 50, но может быть от 0 до 200.</span><span class="sxs-lookup"><span data-stu-id="91a43-190">The default is 50, but it can range from 0 to 200.</span></span> <span data-ttu-id="91a43-191">Когда достигается это ограничение, звонок обрабатывается, как указано в параметре Когда достигается **максимальное количество звонков.**</span><span class="sxs-lookup"><span data-stu-id="91a43-191">When this limit is reached, the call is handled as specified by the **When the maximum number of calls is reached** setting.</span></span>

<span data-ttu-id="91a43-192">Вы можете отключить звонок или перенаправить его в любую из маршрутизов.</span><span class="sxs-lookup"><span data-stu-id="91a43-192">You can choose to disconnect the call or redirect it to any of the call routing destinations.</span></span> <span data-ttu-id="91a43-193">Например, вы можете оставить голосовое сообщение для агентов в очереди.</span><span class="sxs-lookup"><span data-stu-id="91a43-193">For example, you might have the caller leave a voicemail for the agents in the queue.</span></span> <span data-ttu-id="91a43-194">Сведения о внешних [](plan-auto-attendant-call-queue.md#prerequisites) переводах: [](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) технические сведения о формате номеров.</span><span class="sxs-lookup"><span data-stu-id="91a43-194">For external transfers, please refer to [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) and the [external phone number transfers - technical details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) for number formatting.</span></span>

> [!NOTE]
> <span data-ttu-id="91a43-195">Если максимальное количество звонков — 0, приветствие не будет воспроизведения.</span><span class="sxs-lookup"><span data-stu-id="91a43-195">If the maximum number of calls is set to 0 then the greeting message will not play.</span></span>

### <a name="call-timeout-handling"></a><span data-ttu-id="91a43-196">Обработка времени вызова</span><span class="sxs-lookup"><span data-stu-id="91a43-196">Call timeout handling</span></span>

![Снимок экрана: параметры времени и времени вызова](media/call-queue-timeout-handling.png)

<span data-ttu-id="91a43-198">**Время ожидания звонка: максимальное** время ожидания определяет максимальное время удержания звонка в очереди перед перенаправлением или отключением.</span><span class="sxs-lookup"><span data-stu-id="91a43-198">**Call Timeout: maximum wait time** specifies the maximum time a call can be on hold in the queue before it is redirected or disconnected.</span></span> <span data-ttu-id="91a43-199">Можно указать значение от 0 секунд до 45 минут.</span><span class="sxs-lookup"><span data-stu-id="91a43-199">You can specify a value from 0 seconds to 45 minutes.</span></span>

<span data-ttu-id="91a43-200">Вы можете отключить звонок или перенаправить его в одну из маршрутизов.</span><span class="sxs-lookup"><span data-stu-id="91a43-200">You can choose to disconnect the call or redirect it to one of the call routing destinations.</span></span> <span data-ttu-id="91a43-201">Например, вы можете оставить голосовое сообщение для агентов в очереди.</span><span class="sxs-lookup"><span data-stu-id="91a43-201">For example, you might have the caller leave a voicemail for the agents in the queue.</span></span> <span data-ttu-id="91a43-202">Сведения о внешних [](plan-auto-attendant-call-queue.md#prerequisites) переводах: [](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) технические сведения о формате номеров.</span><span class="sxs-lookup"><span data-stu-id="91a43-202">For external transfers, please refer to [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) and the [external phone number transfers - technical details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) for number formatting.</span></span>

<span data-ttu-id="91a43-203">Выбрав параметры времени и времени вызова, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="91a43-203">When you have selected your call timeout options, click **Save**.</span></span>

## <a name="caller-id-for-outbound-calls"></a><span data-ttu-id="91a43-204">ИД вызываемой звонков для исходящие вызовы</span><span class="sxs-lookup"><span data-stu-id="91a43-204">Caller ID for outbound calls</span></span>

<span data-ttu-id="91a43-205">Так как агенты в очереди зовов могут звонить, чтобы вернуть звонок клиента, можно установить для участников очереди зовов номер службы соответствующего автослужбу.</span><span class="sxs-lookup"><span data-stu-id="91a43-205">Since agents in a call queue may dial out to return a customer call, consider setting the caller ID for members of a call queue to the service number of an appropriate auto attendant.</span></span> <span data-ttu-id="91a43-206">Дополнительные [сведения см.](caller-id-policies.md) в Microsoft Teams управление политиками ИД звоня.</span><span class="sxs-lookup"><span data-stu-id="91a43-206">See [Manage caller ID policies in Microsoft Teams](caller-id-policies.md) for more information.</span></span>

## <a name="supported-clients"></a><span data-ttu-id="91a43-207">Поддерживаемые клиенты</span><span class="sxs-lookup"><span data-stu-id="91a43-207">Supported clients</span></span>

<span data-ttu-id="91a43-208">Для агентов, которые находятся в очереди зовов, поддерживаются следующие клиенты:</span><span class="sxs-lookup"><span data-stu-id="91a43-208">The following clients are supported for call agents in a call queue:</span></span>

  - <span data-ttu-id="91a43-209">Skype для бизнеса 2016 (32- и 64-битные версии)</span><span class="sxs-lookup"><span data-stu-id="91a43-209">Skype for Business desktop client 2016 (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="91a43-210">Клиент Lync для настольных пк 2013 (32- и 64-битные версии)</span><span class="sxs-lookup"><span data-stu-id="91a43-210">Lync desktop client 2013 (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="91a43-211">Все модели IP-телефонов, поддерживаемые Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="91a43-211">All IP phone models supported for Microsoft Teams.</span></span> <span data-ttu-id="91a43-212">См. [получение телефонов для Skype для бизнеса Online.](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online)</span><span class="sxs-lookup"><span data-stu-id="91a43-212">See [Getting phones for Skype for Business Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span></span>
  - <span data-ttu-id="91a43-213">Клиент Mac Skype для бизнеса (версия 16.8.196 и более поздние)</span><span class="sxs-lookup"><span data-stu-id="91a43-213">Mac Skype for Business Client (version 16.8.196 and later)</span></span>
  - <span data-ttu-id="91a43-214">Клиент Android Skype для бизнеса (версия 6.16.0.9 и более поздние)</span><span class="sxs-lookup"><span data-stu-id="91a43-214">Android Skype for Business Client (version 6.16.0.9 and later)</span></span>
  - <span data-ttu-id="91a43-215">Клиент iPhone Skype для бизнеса (версия 6.16.0 и более поздние)</span><span class="sxs-lookup"><span data-stu-id="91a43-215">iPhone Skype for Business Client (version 6.16.0 and later)</span></span>
  - <span data-ttu-id="91a43-216">Клиент iPad Skype для бизнеса (версия 6.16.0 и более поздние)</span><span class="sxs-lookup"><span data-stu-id="91a43-216">iPad Skype for Business Client (version 6.16.0 and later)</span></span>
  - <span data-ttu-id="91a43-217">Microsoft Teams Windows (32- и 64-битные версии)</span><span class="sxs-lookup"><span data-stu-id="91a43-217">Microsoft Teams Windows client (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="91a43-218">Клиент Microsoft Teams Mac</span><span class="sxs-lookup"><span data-stu-id="91a43-218">Microsoft Teams Mac client</span></span>
  - <span data-ttu-id="91a43-219">Microsoft Teams в инфраструктуре [виртуальных](/microsoftteams/teams-for-vdi) рабочих Windows (виртуальный рабочий стол, Citrix и VMWARE)</span><span class="sxs-lookup"><span data-stu-id="91a43-219">Microsoft Teams on [Virtualized Desktop Infrastructure](/microsoftteams/teams-for-vdi) (Windows Virtual Desktop, Citrix, and VMware)</span></span>
  - <span data-ttu-id="91a43-220">Microsoft Teams iPhone приложение</span><span class="sxs-lookup"><span data-stu-id="91a43-220">Microsoft Teams iPhone app</span></span>
  - <span data-ttu-id="91a43-221">Microsoft Teams Приложение для Android</span><span class="sxs-lookup"><span data-stu-id="91a43-221">Microsoft Teams Android app</span></span>

    > [!NOTE]
    > <span data-ttu-id="91a43-222">Очереди вызовов, которые назначены прямой маршрутизов, не поддерживают клиенты Skype для бизнеса, клиенты Lync и Skype для бизнеса IP-телефоны в качестве агентов.</span><span class="sxs-lookup"><span data-stu-id="91a43-222">Call queues that are assigned a direct routing number don't support Skype for Business clients, Lync clients, or Skype for Business IP Phones as agents.</span></span>

## <a name="call-queue-cmdlets"></a><span data-ttu-id="91a43-223">Командлеты для работы с очередями звонков</span><span class="sxs-lookup"><span data-stu-id="91a43-223">Call queue cmdlets</span></span>

<span data-ttu-id="91a43-224">Для создания и настройки очередей звонков также можно использовать Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="91a43-224">You can also use Windows PowerShell to create and set up call queues.</span></span> <span data-ttu-id="91a43-225">Ниже 2010 г. вы можете использовать для управления очередью вызовов.</span><span class="sxs-lookup"><span data-stu-id="91a43-225">Here are the cmdlets that you use to manage a call queue.</span></span>

- [<span data-ttu-id="91a43-226">New-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="91a43-226">New-CsCallQueue</span></span>](/powershell/module/skype/new-CsCallQueue)

- [<span data-ttu-id="91a43-227">Set-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="91a43-227">Set-CsCallQueue</span></span>](/powershell/module/skype/set-CsCallQueue)

- [<span data-ttu-id="91a43-228">Get-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="91a43-228">Get-CsCallQueue</span></span>](/powershell/module/skype/get-CsCallQueue)

- [<span data-ttu-id="91a43-229">Remove-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="91a43-229">Remove-CsCallQueue</span></span>](/powershell/module/skype/remove-CsCallQueue)

## <a name="related-topics"></a><span data-ttu-id="91a43-230">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="91a43-230">Related topics</span></span>

[<span data-ttu-id="91a43-231">Возможности телефонной системы</span><span class="sxs-lookup"><span data-stu-id="91a43-231">Here's what you get with Phone System</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="91a43-232">Получение номеров телефонов служб</span><span class="sxs-lookup"><span data-stu-id="91a43-232">Getting service phone numbers</span></span>](getting-service-phone-numbers.md)

[<span data-ttu-id="91a43-233">Доступность аудиоконференций и планов звонков в различных странах и регионах</span><span class="sxs-lookup"><span data-stu-id="91a43-233">Country and region availability for Audio Conferencing and Calling Plans</span></span>](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[<span data-ttu-id="91a43-234">New-CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="91a43-234">New-CsOnlineApplicationInstance</span></span>](/powershell/module/skype/new-csonlineapplicationinstance)

[<span data-ttu-id="91a43-235">Введение в Windows PowerShell и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="91a43-235">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
