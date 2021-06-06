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
ms.openlocfilehash: fe0c2863c627f728f5418cfeb9b7b17c91d246fa
ms.sourcegitcommit: 17d0108fb4d36a3f56144460683f53d77a8a0a7f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/05/2021
ms.locfileid: "52777930"
---
# <a name="create-a-call-queue"></a><span data-ttu-id="10fcf-103">Создание очереди вызовов</span><span class="sxs-lookup"><span data-stu-id="10fcf-103">Create a call queue</span></span>

<span data-ttu-id="10fcf-104">Очереди вызовов предоставляют способ маршрутизации вызывающих людей в организации, которые могут помочь с определенной проблемой или вопросом.</span><span class="sxs-lookup"><span data-stu-id="10fcf-104">Call queues provide a method of routing callers to people in your organization who can help with a particular issue or question.</span></span> <span data-ttu-id="10fcf-105">Звонки распределяются по одному для людей, которые находятся в очереди (которые называются *агентами).*</span><span class="sxs-lookup"><span data-stu-id="10fcf-105">Calls are distributed one at a time to the people in the queue (who are known as *agents*).</span></span> 

> [!TIP]
> <span data-ttu-id="10fcf-106">Эта статья посвящена крупным организациям.</span><span class="sxs-lookup"><span data-stu-id="10fcf-106">This article is for large organizations.</span></span> <span data-ttu-id="10fcf-107">Если ваша организация малого бизнеса, ознакомьтесь с учебным учебником Создание очереди вызовов [для малого](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb) бизнеса.</span><span class="sxs-lookup"><span data-stu-id="10fcf-107">If your organization is a small business, read [Create a call queue - small business tutorial](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb) instead.</span></span>

<span data-ttu-id="10fcf-108">Очереди вызовов предоставляют:</span><span class="sxs-lookup"><span data-stu-id="10fcf-108">Call queues provide:</span></span>

- <span data-ttu-id="10fcf-109">Приветствие.</span><span class="sxs-lookup"><span data-stu-id="10fcf-109">A greeting message.</span></span>

- <span data-ttu-id="10fcf-110">Музыка, пока люди находятся на удержании в очереди.</span><span class="sxs-lookup"><span data-stu-id="10fcf-110">Music while people are waiting on hold in a queue.</span></span>

- <span data-ttu-id="10fcf-111">Маршрутия вызовов — в порядке first *In, First Out* (FIFO) — агентам.</span><span class="sxs-lookup"><span data-stu-id="10fcf-111">Call routing - in *First In, First Out* (FIFO) order - to agents.</span></span>

- <span data-ttu-id="10fcf-112">Параметры обработки переполнения и времени ожидания в очереди.</span><span class="sxs-lookup"><span data-stu-id="10fcf-112">Handling options for queue overflow and timeout.</span></span>

<span data-ttu-id="10fcf-113">Прежде чем выполнять действия, которые вы выполните в этой [](plan-auto-attendant-call-queue.md#getting-started) [статье, ознакомьтесь](plan-auto-attendant-call-queue.md) со статьей Планирование работы с Teams и очередей вызовов и следуйте этим шагам.</span><span class="sxs-lookup"><span data-stu-id="10fcf-113">Be sure you have read [Plan for Teams auto attendants and call queues](plan-auto-attendant-call-queue.md) and followed the [getting started steps](plan-auto-attendant-call-queue.md#getting-started) before you follow the procedures in this article.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="10fcf-114">Демонстрация видео</span><span class="sxs-lookup"><span data-stu-id="10fcf-114">Video demonstration</span></span>

<span data-ttu-id="10fcf-115">В этом видео показан простой пример создания очереди вызовов в Teams.</span><span class="sxs-lookup"><span data-stu-id="10fcf-115">This video shows a basic example of how to create a call queue in Teams.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWCF23?autoplay=false]

## <a name="create-the-call-queue"></a><span data-ttu-id="10fcf-116">Создание очереди вызовов</span><span class="sxs-lookup"><span data-stu-id="10fcf-116">Create the call queue</span></span>

<span data-ttu-id="10fcf-117">Чтобы настроить очередь вызовов, в Центре администрирования Teams Разойдите в центр администрирования Голосовая почта **,** выберите очереди зовов **и** нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="10fcf-117">To set up a call queue, in the Teams admin center, expand **Voice**, click **Call queues**, and then click **Add**.</span></span>

<span data-ttu-id="10fcf-118">Введите имя очереди вызовов.</span><span class="sxs-lookup"><span data-stu-id="10fcf-118">Type a name for the call queue.</span></span>

### <a name="resource-accounts"></a><span data-ttu-id="10fcf-119">Учетные записи ресурсов</span><span class="sxs-lookup"><span data-stu-id="10fcf-119">Resource accounts</span></span>

![Снимок экрана: параметры учетной записи ресурса](media/call-queue-name-language.png)

<span data-ttu-id="10fcf-121">Нажмите **кнопку Добавить учетные** записи , найдите учетную запись ресурса, которую вы хотите использовать с этой очередью вызовов, нажмите кнопку Добавить **и** выберите **добавить**.</span><span class="sxs-lookup"><span data-stu-id="10fcf-121">Click **Add accounts**, search for the resource account that you want to use with this call queue, click **Add**, and then click **Add**.</span></span> <span data-ttu-id="10fcf-122">(Агенты увидят имя учетной записи ресурса, когда получат входящий звонок.)</span><span class="sxs-lookup"><span data-stu-id="10fcf-122">(Agents will see the resource account name when they receive an incoming call.)</span></span>

### <a name="assign-calling-id"></a><span data-ttu-id="10fcf-123">Назначение ИД звонка</span><span class="sxs-lookup"><span data-stu-id="10fcf-123">Assign calling ID</span></span>

![Снимок экрана: параметры ИД звонка](media/call-queue-assign-calling-id.png)

<span data-ttu-id="10fcf-125">Если вы планируете использовать канал Teams для агентов звонков, вы можете назначить им номер исходящие телефонные номера, указав одну или несколько учетных записей ресурсов с телефонным номером.</span><span class="sxs-lookup"><span data-stu-id="10fcf-125">If you plan to use a Teams channel for your call agents, you can assign an outbound caller ID number for the agents by specifying one or more resource accounts with a phone number.</span></span>

<span data-ttu-id="10fcf-126">Нажмите **кнопку** Добавить , найдите учетные записи ресурсов, к которые вы хотите разрешить агентам при звонках по ИД при исходящем звонке, нажмите кнопку **Добавить,** а затем нажмите кнопку **Добавить.**</span><span class="sxs-lookup"><span data-stu-id="10fcf-126">Click **Add**, search for the resource accounts that you want to allow agents to for calling ID purposes when making outbound calls, click **Add**, and then click **Add**.</span></span>

<span data-ttu-id="10fcf-127">Если вы не используете канал Teams для управления членством в агентах, можно непосредственно настроить для участников очереди вызовов номер службы очереди вызовов или соответствующий автослужб.</span><span class="sxs-lookup"><span data-stu-id="10fcf-127">If you are not using a Teams channel to control agent membership, consider directly setting the caller ID for members of the call queue to the service number of the call queue or appropriate auto attendant.</span></span> <span data-ttu-id="10fcf-128">Дополнительные [сведения см.](caller-id-policies.md) в Microsoft Teams управление политиками ИД звоня.</span><span class="sxs-lookup"><span data-stu-id="10fcf-128">See [Manage caller ID policies in Microsoft Teams](caller-id-policies.md) for more information.</span></span>

### <a name="language"></a><span data-ttu-id="10fcf-129">Язык</span><span class="sxs-lookup"><span data-stu-id="10fcf-129">Language</span></span>

![Снимок экрана: языковые параметры](media/call-queue-language.png)

<span data-ttu-id="10fcf-131">Выберите [поддерживаемый язык.](create-a-phone-system-call-queue-languages.md)</span><span class="sxs-lookup"><span data-stu-id="10fcf-131">Choose a [supported language](create-a-phone-system-call-queue-languages.md).</span></span> <span data-ttu-id="10fcf-132">Этот язык будет использоваться для системных голосовых подсказок и транскрибации голосовой почты (если вы их включаете).</span><span class="sxs-lookup"><span data-stu-id="10fcf-132">This language will be used for system-generated voice prompts and voicemail transcription (if you enable them).</span></span>

### <a name="greetings-and-music-on-hold-in-queue"></a><span data-ttu-id="10fcf-133">Приветствия и музыка при удержании в очереди</span><span class="sxs-lookup"><span data-stu-id="10fcf-133">Greetings and music on hold in queue</span></span>

![Снимок экрана: приветствия и музыка при удержании в параметрах очереди](media/call-queue-greetings-music.png)

<span data-ttu-id="10fcf-135">Укажите, хотите ли вы воспроизведения приветствия для вызывающих людей при их поступления в очередь.</span><span class="sxs-lookup"><span data-stu-id="10fcf-135">Specify if you want to play a greeting to callers when they arrive in the queue.</span></span> <span data-ttu-id="10fcf-136">Необходимо отправить файл MP3, WAV или WMA, содержащий приветствие, которое вы хотите воспроизведения.</span><span class="sxs-lookup"><span data-stu-id="10fcf-136">You must upload an MP3, WAV, or WMA file containing the greeting that you want to play.</span></span>

<span data-ttu-id="10fcf-137">Teams предоставляет вызывателям музыку по умолчанию, когда они находятся на удержании в очереди.</span><span class="sxs-lookup"><span data-stu-id="10fcf-137">Teams provides default music to callers while they are on hold in a queue.</span></span> <span data-ttu-id="10fcf-138">Если вы хотите воспроизведения определенного  звукового файла, выберите Вариант воспроизведения звукового файла и загрузите файл MP3, WAV или WMA.</span><span class="sxs-lookup"><span data-stu-id="10fcf-138">If you want to play a specific audio file, choose **Play an audio file** and upload an MP3, WAV, or WMA file.</span></span>

> [!NOTE]
> <span data-ttu-id="10fcf-139">Размер загруженной записи не должен быть больше 5 МБ.</span><span class="sxs-lookup"><span data-stu-id="10fcf-139">The uploaded recording can be no larger than 5 MB.</span></span>
> <span data-ttu-id="10fcf-140">Музыка по умолчанию, которая поставляется Teams очередях вызовов, не предоставляется вашей организацией.</span><span class="sxs-lookup"><span data-stu-id="10fcf-140">The default music supplied in Teams call queues is free of any royalties payable by your organization.</span></span> 

### <a name="call-agents"></a><span data-ttu-id="10fcf-141">Агенты вызовов</span><span class="sxs-lookup"><span data-stu-id="10fcf-141">Call agents</span></span>

<span data-ttu-id="10fcf-142">Просмотрите [предварительные условия для добавления агентов в очередь вызовов.](plan-auto-attendant-call-queue.md#prerequisites)</span><span class="sxs-lookup"><span data-stu-id="10fcf-142">Review the [prerequisites for adding agents to a call queue](plan-auto-attendant-call-queue.md#prerequisites).</span></span>

![Снимок экрана: параметры пользователей и групп для очередей вызовов](media/call-queue-users-groups.png)

##### <a name="teams-channel"></a><span data-ttu-id="10fcf-144">Teams канале</span><span class="sxs-lookup"><span data-stu-id="10fcf-144">Teams channel</span></span>

<span data-ttu-id="10fcf-145">Вы можете добавить до 200 агентов через Teams канале.</span><span class="sxs-lookup"><span data-stu-id="10fcf-145">You can add up to 200 agents via a Teams channel.</span></span>

<span data-ttu-id="10fcf-146">Если вы хотите использовать [канал Teams](https://support.microsoft.com/office/9f07dabe-91c6-4a9b-a545-8ffdddd2504e)для управления очередью, выберите команду Выбрать команду и нажмите кнопку **Добавить канал**. </span><span class="sxs-lookup"><span data-stu-id="10fcf-146">If you want to [use a Teams channel to manage the queue](https://support.microsoft.com/office/9f07dabe-91c6-4a9b-a545-8ffdddd2504e), select the **Choose a team** option and click **Add a channel**.</span></span> <span data-ttu-id="10fcf-147">Найдите команду, которую хотите использовать, выберите ее и нажмите кнопку **Добавить.**</span><span class="sxs-lookup"><span data-stu-id="10fcf-147">Search for the team that you want to use, select it, and click **Add**.</span></span> <span data-ttu-id="10fcf-148">Выберите канал, который вы хотите использовать, и нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="10fcf-148">Select the channel that you want to use and click **Apply**.</span></span>

<span data-ttu-id="10fcf-149">При использовании канала Teams для очередей вызовов поддерживаются следующие клиенты:</span><span class="sxs-lookup"><span data-stu-id="10fcf-149">The following clients are supported when using a Teams channel for call queues:</span></span> 

  - <span data-ttu-id="10fcf-150">Microsoft Teams Windows клиента</span><span class="sxs-lookup"><span data-stu-id="10fcf-150">Microsoft Teams Windows client</span></span>
  - <span data-ttu-id="10fcf-151">Клиент Microsoft Teams Mac</span><span class="sxs-lookup"><span data-stu-id="10fcf-151">Microsoft Teams Mac client</span></span>

##### <a name="users-and-groups"></a><span data-ttu-id="10fcf-152">Пользователи и группы</span><span class="sxs-lookup"><span data-stu-id="10fcf-152">Users and groups</span></span>

<span data-ttu-id="10fcf-153">Вы можете добавить до 20 агентов по отдельности и до 200 агентов с помощью групп.</span><span class="sxs-lookup"><span data-stu-id="10fcf-153">You can add up to 20 agents individually and up to 200 agents via groups.</span></span>

<span data-ttu-id="10fcf-154">Если вы хотите добавить отдельных пользователей или группы в очередь, выберите **вариант Выбрать пользователей и** группы.</span><span class="sxs-lookup"><span data-stu-id="10fcf-154">If you want to add individual users or groups to the queue, select the **Choose users and groups** option.</span></span> 

<span data-ttu-id="10fcf-155">Чтобы добавить пользователя в очередь, нажмите **кнопку** Добавить пользователей , найдите пользователя, нажмите кнопку Добавить **и** выберите **добавить**.</span><span class="sxs-lookup"><span data-stu-id="10fcf-155">To add a user to the queue, click **Add users**, search for the user, click **Add**, and then click **Add**.</span></span>

<span data-ttu-id="10fcf-156">Чтобы добавить группу в очередь, нажмите **кнопку** Добавить группы , найдите группу, нажмите кнопку Добавить **и** выберите **добавить**.</span><span class="sxs-lookup"><span data-stu-id="10fcf-156">To add a group to the queue, click **Add groups**, search for the group, click **Add**, and then click **Add**.</span></span> <span data-ttu-id="10fcf-157">Вы можете использовать списки рассылки, группы безопасности и Microsoft 365 группы или Microsoft Teams группы.</span><span class="sxs-lookup"><span data-stu-id="10fcf-157">You can use distribution lists, security groups, and Microsoft 365 groups or Microsoft Teams teams.</span></span>

> [!NOTE]
> <span data-ttu-id="10fcf-158">Для первого звонка новым пользователям, добавленным в группу, может быть до восьми часов.</span><span class="sxs-lookup"><span data-stu-id="10fcf-158">New users added to a group can take up to eight hours for their first call to arrive.</span></span>

### <a name="call-routing"></a><span data-ttu-id="10fcf-159">Маршрутизация вызовов</span><span class="sxs-lookup"><span data-stu-id="10fcf-159">Call routing</span></span>

![Снимок экрана: режим конференции и параметры метода маршрутации](media/call-queue-conference-mode-routing-method.png)

<span data-ttu-id="10fcf-161">**Режим конференции** значительно сокращает время, необходимое для связи звоняного с агентом, после того как агент принимает звонок.</span><span class="sxs-lookup"><span data-stu-id="10fcf-161">**Conference mode** significantly reduces the amount of time it takes for a caller to be connected to an agent, after the agent accepts the call.</span></span> <span data-ttu-id="10fcf-162">Чтобы режим конференции работал, агенты из очереди зовов должны использовать один из следующих клиентов:</span><span class="sxs-lookup"><span data-stu-id="10fcf-162">For conference mode to work, agents in the call queue must use one of the following clients:</span></span>

  - <span data-ttu-id="10fcf-163">Последняя версия клиента Microsoft Teams, приложения для Android или приложения для iOS</span><span class="sxs-lookup"><span data-stu-id="10fcf-163">The latest version of the Microsoft Teams desktop client, Android app, or iOS app</span></span>
  - <span data-ttu-id="10fcf-164">Microsoft Teams версии телефона 1449/1.0.94.2020051601 или более поздней</span><span class="sxs-lookup"><span data-stu-id="10fcf-164">Microsoft Teams phone version 1449/1.0.94.2020051601 or later</span></span>
  
<span data-ttu-id="10fcf-165">Для Teams агентов необходимо установить режим Teams только для агентов.</span><span class="sxs-lookup"><span data-stu-id="10fcf-165">Agents' Teams accounts need to be set to Teams-only mode.</span></span> <span data-ttu-id="10fcf-166">Агенты, не отвечающие требованиям, не включаются в список маршрутов зовов.</span><span class="sxs-lookup"><span data-stu-id="10fcf-166">Agents who don't meet the requirements aren't included in the call routing list.</span></span> <span data-ttu-id="10fcf-167">Мы рекомендуем использовать режим конференции для очередей вызовов, если все ваши агенты используют совместимые клиенты.</span><span class="sxs-lookup"><span data-stu-id="10fcf-167">We recommend enabling conference mode for your call queues if your agents are all using compatible clients.</span></span>

> [!NOTE]
> <span data-ttu-id="10fcf-168">Режим конференции не поддерживается, если телефонные звонки перенаправят в очередь из шлюза прямой маршрутации, который включен для маршрутизов по расположению.</span><span class="sxs-lookup"><span data-stu-id="10fcf-168">Conference mode is not supported if phone calls are routed to the queue from a Direct Routing gateway that is enabled for Location Based Routing.</span></span>

<span data-ttu-id="10fcf-169">**Способ маршрутики определяет** порядок, в котором агенты будут принимать звонки из очереди.</span><span class="sxs-lookup"><span data-stu-id="10fcf-169">**Routing method** determines the order in which agents receive calls from the queue.</span></span> <span data-ttu-id="10fcf-170">Выберите один из этих вариантов:</span><span class="sxs-lookup"><span data-stu-id="10fcf-170">Choose from these options:</span></span>

- <span data-ttu-id="10fcf-171">**Маршруты attendant одновременно** звонят всем агентам в очереди.</span><span class="sxs-lookup"><span data-stu-id="10fcf-171">**Attendant routing** rings all agents in the queue at the same time.</span></span> <span data-ttu-id="10fcf-172">Звонок получит первый агент вызова.</span><span class="sxs-lookup"><span data-stu-id="10fcf-172">The first call agent to pick up the call gets the call.</span></span>

- <span data-ttu-id="10fcf-173">**Порядковая маршрутия** звонит всем агентам по одному в порядке, указанном в списке **"Агенты звонка".**</span><span class="sxs-lookup"><span data-stu-id="10fcf-173">**Serial routing** rings all call agents one by one in the order specified in the **Call agents** list.</span></span> <span data-ttu-id="10fcf-174">Если агент отклоает звонок или не звонит, звонок звонит следующему агенту и пробует всех агентов до тех пор, пока он не будет отклонен или разоберется.</span><span class="sxs-lookup"><span data-stu-id="10fcf-174">If an agent dismisses or does not pick up a call, the call will ring the next agent and will try all agents until it is picked up or times out.</span></span>

- <span data-ttu-id="10fcf-175">**Round balances** the routing of incoming calls so each call agent gets the same number of calls from the queue.</span><span class="sxs-lookup"><span data-stu-id="10fcf-175">**Round robin** balances the routing of incoming calls so that each call agent gets the same number of calls from the queue.</span></span> <span data-ttu-id="10fcf-176">Это может быть нежелательно в среде входящие продаж, чтобы обеспечить равные возможности для всех агентов звонка.</span><span class="sxs-lookup"><span data-stu-id="10fcf-176">This may be desirable in an inbound sales environment to assure equal opportunity among all the call agents.</span></span>

- <span data-ttu-id="10fcf-177">**Наиболее длинные** неавтоматные маршруты каждый звонок передается агенту, который простаивает в течение длительного времени.</span><span class="sxs-lookup"><span data-stu-id="10fcf-177">**Longest idle** routes each call to the agent who has been idle the longest time.</span></span> <span data-ttu-id="10fcf-178">Агент считается неающим, если его состояние присутствия доступно или состояние присутствия "Нет на сети" менее 10 минут.</span><span class="sxs-lookup"><span data-stu-id="10fcf-178">An agent is considered idle if their presence state is Available or if their presence state has been Away for less than 10 minutes.</span></span> <span data-ttu-id="10fcf-179">Агенты, состояние присутствия которых отсутствует более 10 минут, не считаются неавтными и не смогут принимать звонки, пока они не изменят свое состояние присутствия на В сети.</span><span class="sxs-lookup"><span data-stu-id="10fcf-179">Agents whose presence state has been Away for more than 10 minutes are not considered idle and will not be eligible to receive calls until they change their presence to Available.</span></span> 

![Снимок экрана: параметры времени маршрутинга, отказа и оповещений](media/call-queue-presence-agents-time.png)

<span data-ttu-id="10fcf-181">**В маршрутике** на основе присутствия используется состояние доступности агентов звонка, чтобы определить, следует ли включить агента в список маршрутов зовов для выбранного метода маршрутики.</span><span class="sxs-lookup"><span data-stu-id="10fcf-181">**Presence-based routing** uses the availability status of call agents to determine whether an agent should be included in the call routing list for the selected routing method.</span></span> <span data-ttu-id="10fcf-182">Агенты звонков, у  которых установлено состояние "В наличии", включаются в список маршрутов звонков и могут принимать звонки.</span><span class="sxs-lookup"><span data-stu-id="10fcf-182">Call agents whose availability status is set to **Available** are included in the call routing list and can receive calls.</span></span> <span data-ttu-id="10fcf-183">Агенты, состояние доступности которых имеет любое другое состояние, исключаются из списка маршрутов звонков и не будут принимать звонки, пока их состояние доступности не изменится на **Доступно.**</span><span class="sxs-lookup"><span data-stu-id="10fcf-183">Agents whose availability status is set to any other status are excluded from the call routing list and won't receive calls until their availability status changes back to **Available**.</span></span> 

<span data-ttu-id="10fcf-184">Вы можете включить маршрутику вызовов на основе присутствия с помощью любого из способов маршрутизов.</span><span class="sxs-lookup"><span data-stu-id="10fcf-184">You can enable presence-based call routing with any of the routing methods.</span></span>

> [!NOTE]
> <span data-ttu-id="10fcf-185">Если  в качестве способа маршрутки выбран режим "Самый длинный неавместимый", маршрутная маршрутия на основе  присутствия является обязательной и автоматически включена, даже если для переключения маршрутов на основе присутствия будет отключена и неанимна.</span><span class="sxs-lookup"><span data-stu-id="10fcf-185">When **Longest idle** is selected as the routing method, presence-based routing is required and automatically enabled even though the Presence-based routing toggle will be **Off** and grayed out.</span></span>

<span data-ttu-id="10fcf-186">Если агент отключит получение звонков, он не будет включен в список маршрутов звонков независимо от состояния доступности.</span><span class="sxs-lookup"><span data-stu-id="10fcf-186">If an agent opts out of getting calls, they won't be included in the call routing list regardless of what their availability status is set to.</span></span> 

> [!NOTE]
> <span data-ttu-id="10fcf-187">Агенты, которые используют Skype для бизнеса клиента, не включаются в список маршрутов зовов, если включена маршрутия на основе присутствия.</span><span class="sxs-lookup"><span data-stu-id="10fcf-187">Agents who use the Skype for Business client aren't included in the call routing list when presence-based routing is enabled.</span></span> <span data-ttu-id="10fcf-188">Если у вас есть агенты, которые Skype для бизнеса, не в включаете маршрутику вызовов на основе присутствия.</span><span class="sxs-lookup"><span data-stu-id="10fcf-188">If you have agents who use Skype for Business, don't enable presence-based call routing.</span></span>

<span data-ttu-id="10fcf-189">**Время оповещения агента** определяет, как долго телефон агента будет звонить, прежде чем очередь перенаправит звонок следующему агенту.</span><span class="sxs-lookup"><span data-stu-id="10fcf-189">**Agent alert time** specifies how long an agent's phone will ring before the queue redirects the call to the next agent.</span></span>

<span data-ttu-id="10fcf-190">Рекомендуется использовать следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="10fcf-190">The following settings are recommended:</span></span>

- <span data-ttu-id="10fcf-191">**Режим конференции с** **автоматическим**</span><span class="sxs-lookup"><span data-stu-id="10fcf-191">**Conference mode** to **Auto**</span></span>
- <span data-ttu-id="10fcf-192">**Способ маршрутиста в** **round или** **longest idle**</span><span class="sxs-lookup"><span data-stu-id="10fcf-192">**Routing method** to **Round robin** or **Longest idle**</span></span>
- <span data-ttu-id="10fcf-193">**Маршруты на основе присутствия в** В **сети**</span><span class="sxs-lookup"><span data-stu-id="10fcf-193">**Presence-based routing** to **On**</span></span>
- <span data-ttu-id="10fcf-194">**Время оповещения агента:** **до 20 секунд**</span><span class="sxs-lookup"><span data-stu-id="10fcf-194">**Agent alert time:** to **20 seconds**</span></span>

> [!NOTE]
> <span data-ttu-id="10fcf-195">Если маршрутия на основе присутствия не включена и в очереди несколько звонков, система будет одновременно представлять эти звонки агентам независимо от их состояния присутствия.</span><span class="sxs-lookup"><span data-stu-id="10fcf-195">If presence-based routing is not enabled and there are multiple calls in the queue, the system will present these calls simultaneously to the agents regardless of their presence status.</span></span> <span data-ttu-id="10fcf-196">В результате агенты получат несколько уведомлений о звонках, особенно если некоторые агенты не ответят на первоначальный звонок.</span><span class="sxs-lookup"><span data-stu-id="10fcf-196">This will result in multiple call notifications to agents, particularly if some agents don’t answer the initial call presented to them.</span></span>

### <a name="call-overflow-handling"></a><span data-ttu-id="10fcf-197">Обработка переполнения вызовов</span><span class="sxs-lookup"><span data-stu-id="10fcf-197">Call overflow handling</span></span>

![Снимок экрана: параметры переполнения звонка](media/call-queue-overflow-handling.png)

<span data-ttu-id="10fcf-199">**Максимальное число звонков** в очереди определяет максимальное количество звонков, которые могут быть в очереди в любое время.</span><span class="sxs-lookup"><span data-stu-id="10fcf-199">**Maximum calls in the queue** specifies the maximum number of calls that can wait in the queue at any given time.</span></span> <span data-ttu-id="10fcf-200">Значение по умолчанию — 50, но может быть от 0 до 200.</span><span class="sxs-lookup"><span data-stu-id="10fcf-200">The default is 50, but it can range from 0 to 200.</span></span> <span data-ttu-id="10fcf-201">Когда достигается это ограничение, звонок обрабатывается в том случае, если установлено максимальное количество **звонков.**</span><span class="sxs-lookup"><span data-stu-id="10fcf-201">When this limit is reached, the call is handled as specified by the **When the maximum number of calls is reached** setting.</span></span>

<span data-ttu-id="10fcf-202">Вы можете отключить звонок или перенаправить его в любую из маршрутизов.</span><span class="sxs-lookup"><span data-stu-id="10fcf-202">You can choose to disconnect the call or redirect it to any of the call routing destinations.</span></span> <span data-ttu-id="10fcf-203">Например, вы можете оставить голосовое сообщение для агентов в очереди.</span><span class="sxs-lookup"><span data-stu-id="10fcf-203">For example, you might have the caller leave a voicemail for the agents in the queue.</span></span> <span data-ttu-id="10fcf-204">Сведения о внешних [](plan-auto-attendant-call-queue.md#prerequisites) переводах: [](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) технические сведения о формате номеров.</span><span class="sxs-lookup"><span data-stu-id="10fcf-204">For external transfers, please refer to [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) and the [external phone number transfers - technical details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) for number formatting.</span></span>

> [!NOTE]
> <span data-ttu-id="10fcf-205">Если максимальное количество звонков — 0, приветствие не будет воспроизведения.</span><span class="sxs-lookup"><span data-stu-id="10fcf-205">If the maximum number of calls is set to 0 then the greeting message will not play.</span></span>

### <a name="call-timeout-handling"></a><span data-ttu-id="10fcf-206">Обработка времени вызова</span><span class="sxs-lookup"><span data-stu-id="10fcf-206">Call timeout handling</span></span>

![Снимок экрана: параметры времени времени вызова](media/call-queue-timeout-handling.png)

<span data-ttu-id="10fcf-208">**Время ожидания звонка: максимальное** время ожидания определяет максимальное время удержания звонка в очереди перед перенаправлением или отключением.</span><span class="sxs-lookup"><span data-stu-id="10fcf-208">**Call Timeout: maximum wait time** specifies the maximum time a call can be on hold in the queue before it is redirected or disconnected.</span></span> <span data-ttu-id="10fcf-209">Можно указать значение от 0 секунд до 45 минут.</span><span class="sxs-lookup"><span data-stu-id="10fcf-209">You can specify a value from 0 seconds to 45 minutes.</span></span>

<span data-ttu-id="10fcf-210">Вы можете отключить звонок или перенаправить его в одну из маршрутизов.</span><span class="sxs-lookup"><span data-stu-id="10fcf-210">You can choose to disconnect the call or redirect it to one of the call routing destinations.</span></span> <span data-ttu-id="10fcf-211">Например, вы можете оставить голосовое сообщение для агентов в очереди.</span><span class="sxs-lookup"><span data-stu-id="10fcf-211">For example, you might have the caller leave a voicemail for the agents in the queue.</span></span> <span data-ttu-id="10fcf-212">Сведения о внешних [](plan-auto-attendant-call-queue.md#prerequisites) переводах: [](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) технические сведения о формате номеров.</span><span class="sxs-lookup"><span data-stu-id="10fcf-212">For external transfers, please refer to [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) and the [external phone number transfers - technical details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) for number formatting.</span></span>

<span data-ttu-id="10fcf-213">Выбрав параметры времени и времени вызова, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="10fcf-213">When you have selected your call timeout options, click **Save**.</span></span>

## <a name="supported-clients"></a><span data-ttu-id="10fcf-214">Поддерживаемые клиенты</span><span class="sxs-lookup"><span data-stu-id="10fcf-214">Supported clients</span></span>

<span data-ttu-id="10fcf-215">Для агентов, которые находятся в очереди зовов, поддерживаются следующие клиенты:</span><span class="sxs-lookup"><span data-stu-id="10fcf-215">The following clients are supported for call agents in a call queue:</span></span>

  - <span data-ttu-id="10fcf-216">Skype для бизнеса 2016 (32- и 64-битные версии)</span><span class="sxs-lookup"><span data-stu-id="10fcf-216">Skype for Business desktop client 2016 (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="10fcf-217">Клиент Lync для настольных пк 2013 (32- и 64-битные версии)</span><span class="sxs-lookup"><span data-stu-id="10fcf-217">Lync desktop client 2013 (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="10fcf-218">Все модели IP-телефонов, поддерживаемые Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="10fcf-218">All IP phone models supported for Microsoft Teams.</span></span> <span data-ttu-id="10fcf-219">См. [получение телефонов для Skype для бизнеса Online.](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online)</span><span class="sxs-lookup"><span data-stu-id="10fcf-219">See [Getting phones for Skype for Business Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span></span>
  - <span data-ttu-id="10fcf-220">Клиент Mac Skype для бизнеса (версия 16.8.196 и более поздние)</span><span class="sxs-lookup"><span data-stu-id="10fcf-220">Mac Skype for Business Client (version 16.8.196 and later)</span></span>
  - <span data-ttu-id="10fcf-221">Клиент Android Skype для бизнеса (версия 6.16.0.9 и более поздние)</span><span class="sxs-lookup"><span data-stu-id="10fcf-221">Android Skype for Business Client (version 6.16.0.9 and later)</span></span>
  - <span data-ttu-id="10fcf-222">Клиент iPhone Skype для бизнеса (версия 6.16.0 и более поздние)</span><span class="sxs-lookup"><span data-stu-id="10fcf-222">iPhone Skype for Business Client (version 6.16.0 and later)</span></span>
  - <span data-ttu-id="10fcf-223">Клиент iPad Skype для бизнеса (версия 6.16.0 и более поздние)</span><span class="sxs-lookup"><span data-stu-id="10fcf-223">iPad Skype for Business Client (version 6.16.0 and later)</span></span>
  - <span data-ttu-id="10fcf-224">Microsoft Teams Windows (32- и 64-битные версии)</span><span class="sxs-lookup"><span data-stu-id="10fcf-224">Microsoft Teams Windows client (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="10fcf-225">Клиент Microsoft Teams Mac</span><span class="sxs-lookup"><span data-stu-id="10fcf-225">Microsoft Teams Mac client</span></span>
  - <span data-ttu-id="10fcf-226">Microsoft Teams в инфраструктуре [виртуальных](/microsoftteams/teams-for-vdi) рабочих Windows (виртуальный рабочий стол, Citrix и VMWARE)</span><span class="sxs-lookup"><span data-stu-id="10fcf-226">Microsoft Teams on [Virtualized Desktop Infrastructure](/microsoftteams/teams-for-vdi) (Windows Virtual Desktop, Citrix, and VMware)</span></span>
  - <span data-ttu-id="10fcf-227">Microsoft Teams iPhone приложение</span><span class="sxs-lookup"><span data-stu-id="10fcf-227">Microsoft Teams iPhone app</span></span>
  - <span data-ttu-id="10fcf-228">Microsoft Teams Приложение для Android</span><span class="sxs-lookup"><span data-stu-id="10fcf-228">Microsoft Teams Android app</span></span>

    > [!NOTE]
    > <span data-ttu-id="10fcf-229">Очереди вызовов, которые назначены прямой маршрутизов, не поддерживают Skype для бизнеса клиентов, клиентов Lync и Skype для бизнеса IP-телефонов в качестве агентов.</span><span class="sxs-lookup"><span data-stu-id="10fcf-229">Call queues that are assigned a direct routing number don't support Skype for Business clients, Lync clients, or Skype for Business IP Phones as agents.</span></span>

## <a name="call-queue-cmdlets"></a><span data-ttu-id="10fcf-230">Командлеты для работы с очередями звонков</span><span class="sxs-lookup"><span data-stu-id="10fcf-230">Call queue cmdlets</span></span>

<span data-ttu-id="10fcf-231">Для создания и настройки очередей звонков также можно использовать Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="10fcf-231">You can also use Windows PowerShell to create and set up call queues.</span></span> <span data-ttu-id="10fcf-232">Ниже 2016 2010:</span><span class="sxs-lookup"><span data-stu-id="10fcf-232">Here are the cmdlets that you use to manage a call queue.</span></span>

- [<span data-ttu-id="10fcf-233">New-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="10fcf-233">New-CsCallQueue</span></span>](/powershell/module/skype/new-CsCallQueue)

- [<span data-ttu-id="10fcf-234">Set-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="10fcf-234">Set-CsCallQueue</span></span>](/powershell/module/skype/set-CsCallQueue)

- [<span data-ttu-id="10fcf-235">Get-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="10fcf-235">Get-CsCallQueue</span></span>](/powershell/module/skype/get-CsCallQueue)

- [<span data-ttu-id="10fcf-236">Remove-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="10fcf-236">Remove-CsCallQueue</span></span>](/powershell/module/skype/remove-CsCallQueue)

## <a name="related-topics"></a><span data-ttu-id="10fcf-237">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="10fcf-237">Related topics</span></span>

[<span data-ttu-id="10fcf-238">Возможности телефонной системы</span><span class="sxs-lookup"><span data-stu-id="10fcf-238">Here's what you get with Phone System</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="10fcf-239">Получение номеров телефонов служб</span><span class="sxs-lookup"><span data-stu-id="10fcf-239">Getting service phone numbers</span></span>](getting-service-phone-numbers.md)

[<span data-ttu-id="10fcf-240">Доступность аудиоконференций и планов звонков в различных странах и регионах</span><span class="sxs-lookup"><span data-stu-id="10fcf-240">Country and region availability for Audio Conferencing and Calling Plans</span></span>](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[<span data-ttu-id="10fcf-241">New-CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="10fcf-241">New-CsOnlineApplicationInstance</span></span>](/powershell/module/skype/new-csonlineapplicationinstance)

[<span data-ttu-id="10fcf-242">Введение в Windows PowerShell и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="10fcf-242">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
