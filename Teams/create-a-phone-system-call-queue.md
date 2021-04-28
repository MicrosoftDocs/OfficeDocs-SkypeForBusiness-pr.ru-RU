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
description: Узнайте, как настроить телефонную систему для очередей звонков в Microsoft Teams, которая предоставляет приветствие, музыку, перенаправление звонков и другие функции.
ms.openlocfilehash: 8b4fe4283ac9734c1dc29bf33759039098578744
ms.sourcegitcommit: 03ff569a0b7a8e04d7b0ab32f370a9a537fa7fe7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2021
ms.locfileid: "52064805"
---
# <a name="create-a-call-queue"></a><span data-ttu-id="a01b4-103">Создание очереди вызовов</span><span class="sxs-lookup"><span data-stu-id="a01b4-103">Create a call queue</span></span>

<span data-ttu-id="a01b4-104">Очереди вызовов предоставляют способ маршрутизации вызывающих людей в организации, которые могут помочь с определенной проблемой или вопросом.</span><span class="sxs-lookup"><span data-stu-id="a01b4-104">Call queues provide a method of routing callers to people in your organization who can help with a particular issue or question.</span></span> <span data-ttu-id="a01b4-105">Звонки распределяются по одному для людей, которые находятся в очереди (которые называются *агентами).*</span><span class="sxs-lookup"><span data-stu-id="a01b4-105">Calls are distributed one at a time to the people in the queue (who are known as *agents*).</span></span> 

<span data-ttu-id="a01b4-106">Очереди вызовов предоставляют:</span><span class="sxs-lookup"><span data-stu-id="a01b4-106">Call queues provide:</span></span>

- <span data-ttu-id="a01b4-107">Приветствие.</span><span class="sxs-lookup"><span data-stu-id="a01b4-107">A greeting message.</span></span>

- <span data-ttu-id="a01b4-108">Музыка, пока люди находятся на удержании в очереди.</span><span class="sxs-lookup"><span data-stu-id="a01b4-108">Music while people are waiting on hold in a queue.</span></span>

- <span data-ttu-id="a01b4-109">Маршрутия вызовов — в порядке first *In, First Out* (FIFO) — агентам.</span><span class="sxs-lookup"><span data-stu-id="a01b4-109">Call routing - in *First In, First Out* (FIFO) order - to agents.</span></span>

- <span data-ttu-id="a01b4-110">Параметры обработки для переполнения и времени ожидания в очереди.</span><span class="sxs-lookup"><span data-stu-id="a01b4-110">Handling options for queue overflow and timeout.</span></span>

<span data-ttu-id="a01b4-111">Прежде чем выполнять действия, которые вы выполните в [](plan-auto-attendant-call-queue.md#getting-started) этой статье, ознакомьтесь со статьей Планирование автоотводников и очередей вызовов [Teams](plan-auto-attendant-call-queue.md) и следуйте этим шагам.</span><span class="sxs-lookup"><span data-stu-id="a01b4-111">Be sure you have read [Plan for Teams auto attendants and call queues](plan-auto-attendant-call-queue.md) and followed the [getting started steps](plan-auto-attendant-call-queue.md#getting-started) before you follow the procedures in this article.</span></span>

<span data-ttu-id="a01b4-112">Чтобы настроить очередь вызовов, в Центре администрирования Teams разйдите в центр администрирования Teams кнопку **Голосовая** почта, выберите очереди зовов **и** нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="a01b4-112">To set up a call queue, in the Teams admin center, expand **Voice**, click **Call queues**, and then click **Add**.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="a01b4-113">Демонстрация видео</span><span class="sxs-lookup"><span data-stu-id="a01b4-113">Video demonstration</span></span>

<span data-ttu-id="a01b4-114">В этом видео показан простой пример создания очереди вызовов в Teams.</span><span class="sxs-lookup"><span data-stu-id="a01b4-114">This video shows a basic example of how to create a call queue in Teams.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWCF23?autoplay=false]

## <a name="resource-account-and-language"></a><span data-ttu-id="a01b4-115">Учетная запись ресурса и язык</span><span class="sxs-lookup"><span data-stu-id="a01b4-115">Resource account and language</span></span>

![Снимок экрана: учетная запись ресурса и языковые параметры](media/call-queue-name-language.png)

1. <span data-ttu-id="a01b4-117">Введите имя очереди вызовов.</span><span class="sxs-lookup"><span data-stu-id="a01b4-117">Type a name for the call queue.</span></span>

2. <span data-ttu-id="a01b4-118">Нажмите **кнопку Добавить учетные** записи , найдите учетную запись ресурса, которую вы хотите использовать с этой очередью вызовов, нажмите кнопку **Добавить,** а затем нажмите кнопку **Добавить.**</span><span class="sxs-lookup"><span data-stu-id="a01b4-118">Click **Add accounts**, search for the resource account that you want to use with this call queue, click **Add**, and then click **Add**.</span></span> <span data-ttu-id="a01b4-119">(Агенты увидят имя учетной записи ресурса, когда получат входящий звонок.)</span><span class="sxs-lookup"><span data-stu-id="a01b4-119">(Agents will see the resource account name when they receive an incoming call.)</span></span>

3. <span data-ttu-id="a01b4-120">Выберите [поддерживаемый язык.](create-a-phone-system-call-queue-languages.md)</span><span class="sxs-lookup"><span data-stu-id="a01b4-120">Choose a [supported language](create-a-phone-system-call-queue-languages.md).</span></span> <span data-ttu-id="a01b4-121">Этот язык будет использоваться для системных голосовых подсказок и транскрибации голосовой почты (если вы их включаете).</span><span class="sxs-lookup"><span data-stu-id="a01b4-121">This language will be used for system-generated voice prompts and voicemail transcription (if you enable them).</span></span>

## <a name="greetings-and-music-on-hold-in-queue"></a><span data-ttu-id="a01b4-122">Приветствия и музыка на удержании в очереди</span><span class="sxs-lookup"><span data-stu-id="a01b4-122">Greetings and music on hold in queue</span></span>

<span data-ttu-id="a01b4-123">Укажите, хотите ли вы, чтобы вызыватели могли разозвать приветствие при их поступления в очередь.</span><span class="sxs-lookup"><span data-stu-id="a01b4-123">Specify if you want to play a greeting to callers when they arrive in the queue.</span></span> <span data-ttu-id="a01b4-124">Необходимо отправить файл MP3, WAV или WMA, содержащий приветствие, которое вы хотите воспроизведения.</span><span class="sxs-lookup"><span data-stu-id="a01b4-124">You must upload an MP3, WAV, or WMA file containing the greeting that you want to play.</span></span>

<span data-ttu-id="a01b4-125">Teams предоставляет музыку по умолчанию вызывателям, когда они находятся на удержании в очереди.</span><span class="sxs-lookup"><span data-stu-id="a01b4-125">Teams provides default music to callers while they are on hold in a queue.</span></span> <span data-ttu-id="a01b4-126">Если вы хотите воспроизведения определенного  звукового файла, выберите Вариант воспроизведения звукового файла и загрузите файл MP3, WAV или WMA.</span><span class="sxs-lookup"><span data-stu-id="a01b4-126">If you want to play a specific audio file, choose **Play an audio file** and upload an MP3, WAV, or WMA file.</span></span>

> [!NOTE]
> <span data-ttu-id="a01b4-127">Размер загруженной записи не должен быть больше 5 МБ.</span><span class="sxs-lookup"><span data-stu-id="a01b4-127">The uploaded recording can be no larger than 5 MB.</span></span>
> <span data-ttu-id="a01b4-128">Музыка по умолчанию, которая предоставляется в очередях вызовов Teams, не предоставляется вашей организацией.</span><span class="sxs-lookup"><span data-stu-id="a01b4-128">The default music supplied in Teams call queues is free of any royalties payable by your organization.</span></span> 

## <a name="call-agents"></a><span data-ttu-id="a01b4-129">Агенты вызовов</span><span class="sxs-lookup"><span data-stu-id="a01b4-129">Call agents</span></span>

<span data-ttu-id="a01b4-130">Просмотрите [предварительные условия для добавления агентов в очередь вызовов.](plan-auto-attendant-call-queue.md#prerequisites)</span><span class="sxs-lookup"><span data-stu-id="a01b4-130">Review the [prerequisites for adding agents to a call queue](plan-auto-attendant-call-queue.md#prerequisites).</span></span>

![Снимок экрана: параметры пользователей и групп для очередей вызовов](media/call-queue-users-groups.png)

##### <a name="teams-channel"></a><span data-ttu-id="a01b4-132">Канал Teams</span><span class="sxs-lookup"><span data-stu-id="a01b4-132">Teams channel</span></span>

<span data-ttu-id="a01b4-133">В канале Teams можно добавить до 200 агентов.</span><span class="sxs-lookup"><span data-stu-id="a01b4-133">You can add up to 200 agents via a Teams channel.</span></span>

<span data-ttu-id="a01b4-134">Если вы хотите использовать [канал Teams](https://support.microsoft.com/office/9f07dabe-91c6-4a9b-a545-8ffdddd2504e)для управления очередью , выберите команду Выбрать **команду** и щелкните **Добавить канал**.</span><span class="sxs-lookup"><span data-stu-id="a01b4-134">If you want to [use a Teams channel to manage the queue](https://support.microsoft.com/office/9f07dabe-91c6-4a9b-a545-8ffdddd2504e), select the **Choose a team** option and click **Add a channel**.</span></span> <span data-ttu-id="a01b4-135">Найдите команду, которую хотите использовать, выберите ее и нажмите кнопку **Добавить.**</span><span class="sxs-lookup"><span data-stu-id="a01b4-135">Search for the team that you want to use, select it, and click **Add**.</span></span> <span data-ttu-id="a01b4-136">Выберите канал, который вы хотите использовать, и нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="a01b4-136">Select the channel that you want to use and click **Apply**.</span></span>

<span data-ttu-id="a01b4-137">При использовании канала Teams для очередей вызовов поддерживаются следующие клиенты:</span><span class="sxs-lookup"><span data-stu-id="a01b4-137">The following clients are supported when using a Teams channel for call queues:</span></span> 

  - <span data-ttu-id="a01b4-138">Клиент Microsoft Teams для Windows</span><span class="sxs-lookup"><span data-stu-id="a01b4-138">Microsoft Teams Windows client</span></span>
  - <span data-ttu-id="a01b4-139">Клиент Microsoft Teams Mac</span><span class="sxs-lookup"><span data-stu-id="a01b4-139">Microsoft Teams Mac client</span></span>

##### <a name="users-and-groups"></a><span data-ttu-id="a01b4-140">Пользователи и группы</span><span class="sxs-lookup"><span data-stu-id="a01b4-140">Users and groups</span></span>

<span data-ttu-id="a01b4-141">Вы можете добавить до 20 агентов по отдельности и до 200 агентов с помощью групп.</span><span class="sxs-lookup"><span data-stu-id="a01b4-141">You can add up to 20 agents individually and up to 200 agents via groups.</span></span>

<span data-ttu-id="a01b4-142">Если вы хотите добавить отдельных пользователей или группы в очередь, выберите **параметр Выбрать пользователей и** группы.</span><span class="sxs-lookup"><span data-stu-id="a01b4-142">If you want to add individual users or groups to the queue, select the **Choose users and groups** option.</span></span> 

<span data-ttu-id="a01b4-143">Чтобы добавить пользователя в очередь, нажмите **кнопку** Добавить пользователей , найдите пользователя, нажмите кнопку Добавить **и** выберите **добавить**.</span><span class="sxs-lookup"><span data-stu-id="a01b4-143">To add a user to the queue, click **Add users**, search for the user, click **Add**, and then click **Add**.</span></span>

<span data-ttu-id="a01b4-144">Чтобы добавить группу в очередь, нажмите кнопку Добавить группы **,** найдите группу, нажмите кнопку Добавить **и** выберите **добавить**.</span><span class="sxs-lookup"><span data-stu-id="a01b4-144">To add a group to the queue, click **Add groups**, search for the group, click **Add**, and then click **Add**.</span></span> <span data-ttu-id="a01b4-145">Вы можете использовать списки рассылки, группы безопасности и группы Microsoft 365 или команды Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="a01b4-145">You can use distribution lists, security groups, and Microsoft 365 groups or Microsoft Teams teams.</span></span>

> [!NOTE]
> <span data-ttu-id="a01b4-146">Первые вызовы новых пользователей, добавленных в группу, могут принимать до восьми часов.</span><span class="sxs-lookup"><span data-stu-id="a01b4-146">New users added to a group can take up to eight hours for their first call to arrive.</span></span>

## <a name="call-routing"></a><span data-ttu-id="a01b4-147">Маршрутизация вызовов</span><span class="sxs-lookup"><span data-stu-id="a01b4-147">Call routing</span></span>

![Снимок экрана: режим конференции и параметры метода маршрутации](media/call-queue-conference-mode-routing-method.png)

<span data-ttu-id="a01b4-149">**Режим конференции** значительно сокращает время, необходимое для связи звоняного с агентом, после того как агент принимает звонок.</span><span class="sxs-lookup"><span data-stu-id="a01b4-149">**Conference mode** significantly reduces the amount of time it takes for a caller to be connected to an agent, after the agent accepts the call.</span></span> <span data-ttu-id="a01b4-150">Чтобы режим конференции работал, агенты в очереди зовов должны использовать один из следующих клиентов:</span><span class="sxs-lookup"><span data-stu-id="a01b4-150">For conference mode to work, agents in the call queue must use one of the following clients:</span></span>

  - <span data-ttu-id="a01b4-151">Последняя версия клиента Microsoft Teams для настольных пк, приложения Android или приложения для iOS</span><span class="sxs-lookup"><span data-stu-id="a01b4-151">The latest version of the Microsoft Teams desktop client, Android app, or iOS app</span></span>
  - <span data-ttu-id="a01b4-152">Телефон Microsoft Teams версии 1449/1.0.94.2020051601 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="a01b4-152">Microsoft Teams phone version 1449/1.0.94.2020051601 or later</span></span>
  
<span data-ttu-id="a01b4-153">Учетные записи Teams агентов должны быть настроены в режиме только Teams.</span><span class="sxs-lookup"><span data-stu-id="a01b4-153">Agents' Teams accounts need to be set to Teams-only mode.</span></span> <span data-ttu-id="a01b4-154">Агенты, не отвечающие требованиям, не включаются в список маршрутов зовов.</span><span class="sxs-lookup"><span data-stu-id="a01b4-154">Agents who don't meet the requirements aren't included in the call routing list.</span></span> <span data-ttu-id="a01b4-155">Мы рекомендуем использовать режим конференции для очередей вызовов, если все ваши агенты используют совместимые клиенты.</span><span class="sxs-lookup"><span data-stu-id="a01b4-155">We recommend enabling conference mode for your call queues if your agents are all using compatible clients.</span></span>

> [!NOTE]
> <span data-ttu-id="a01b4-156">Режим конференции не поддерживается, если телефонные звонки перенаправлются в очередь из шлюза прямой маршрутации, который включен для маршрутизов по расположению.</span><span class="sxs-lookup"><span data-stu-id="a01b4-156">Conference mode is not supported if phone calls are routed to the queue from a Direct Routing gateway that is enabled for Location Based Routing.</span></span>

<span data-ttu-id="a01b4-157">**Способ маршрутики определяет** порядок, в котором агенты будут принимать звонки из очереди.</span><span class="sxs-lookup"><span data-stu-id="a01b4-157">**Routing method** determines the order in which agents receive calls from the queue.</span></span> <span data-ttu-id="a01b4-158">Выберите один из этих вариантов:</span><span class="sxs-lookup"><span data-stu-id="a01b4-158">Choose from these options:</span></span>

- <span data-ttu-id="a01b4-159">**Маршруты помощника одновременно** звонят всем агентам в очереди.</span><span class="sxs-lookup"><span data-stu-id="a01b4-159">**Attendant routing** rings all agents in the queue at the same time.</span></span> <span data-ttu-id="a01b4-160">Звонок получит первый агент звонка.</span><span class="sxs-lookup"><span data-stu-id="a01b4-160">The first call agent to pick up the call gets the call.</span></span>

- <span data-ttu-id="a01b4-161">**Порядковая маршрутия** звонит всем агентам по одному в порядке, указанном в списке **"Агенты звонка".**</span><span class="sxs-lookup"><span data-stu-id="a01b4-161">**Serial routing** rings all call agents one by one in the order specified in the **Call agents** list.</span></span> <span data-ttu-id="a01b4-162">Если агент отклоает звонок или не звонит, звонок звонит следующему агенту и пробует всех агентов до тех пор, пока он не будет отклонен или не будет разозваться.</span><span class="sxs-lookup"><span data-stu-id="a01b4-162">If an agent dismisses or does not pick up a call, the call will ring the next agent and will try all agents until it is picked up or times out.</span></span>

- <span data-ttu-id="a01b4-163">**Round balances** the routing of incoming calls so each call agent gets the same number of calls from the queue.</span><span class="sxs-lookup"><span data-stu-id="a01b4-163">**Round robin** balances the routing of incoming calls so that each call agent gets the same number of calls from the queue.</span></span> <span data-ttu-id="a01b4-164">Это может быть нежелательно в среде входящие продаж, чтобы обеспечить равные возможности для всех агентов звонка.</span><span class="sxs-lookup"><span data-stu-id="a01b4-164">This may be desirable in an inbound sales environment to assure equal opportunity among all the call agents.</span></span>

- <span data-ttu-id="a01b4-165">**Наиболее длинные** неавтоматные маршруты каждый звонок передается агенту, который простаивает в течение долгого времени.</span><span class="sxs-lookup"><span data-stu-id="a01b4-165">**Longest idle** routes each call to the agent who has been idle the longest time.</span></span> <span data-ttu-id="a01b4-166">Агент считается неающим, если его состояние присутствия доступно или состояние присутствия "Нет на нем" менее 10 минут.</span><span class="sxs-lookup"><span data-stu-id="a01b4-166">An agent is considered idle if their presence state is Available or if their presence state has been Away for less than 10 minutes.</span></span> <span data-ttu-id="a01b4-167">Агенты, состояние присутствия которых отсутствует более 10 минут, не считаются неавтными и не смогут принимать звонки, пока они не изменят свое состояние присутствия на В сети.</span><span class="sxs-lookup"><span data-stu-id="a01b4-167">Agents whose presence state has been Away for more than 10 minutes are not considered idle and will not be eligible to receive calls until they change their presence to Available.</span></span> 

![Снимок экрана: параметры времени маршрутки, отказа и оповещений](media/call-queue-presence-agents-time.png)


<span data-ttu-id="a01b4-169">**В маршрутике** на основе присутствия используется состояние доступности агентов звонка, чтобы определить, следует ли включить агента в список маршрутов зовов для выбранного метода маршрутики.</span><span class="sxs-lookup"><span data-stu-id="a01b4-169">**Presence-based routing** uses the availability status of call agents to determine whether an agent should be included in the call routing list for the selected routing method.</span></span> <span data-ttu-id="a01b4-170">Звонки от агентов, у  которых установлено состояние "В наличии", включаются в список маршрутов звонков и могут принимать звонки.</span><span class="sxs-lookup"><span data-stu-id="a01b4-170">Call agents whose availability status is set to **Available** are included in the call routing list and can receive calls.</span></span> <span data-ttu-id="a01b4-171">Агенты, состояние доступности которых имеет любое другое состояние, исключаются из списка маршрутов звонков и не будут получать звонки, пока их состояние доступности не изменится на **Доступно.**</span><span class="sxs-lookup"><span data-stu-id="a01b4-171">Agents whose availability status is set to any other status are excluded from the call routing list and won't receive calls until their availability status changes back to **Available**.</span></span> 

<span data-ttu-id="a01b4-172">Вы можете включить маршрутику вызовов на основе присутствия с помощью любого из способов маршрутизов.</span><span class="sxs-lookup"><span data-stu-id="a01b4-172">You can enable presence-based call routing with any of the routing methods.</span></span>

<span data-ttu-id="a01b4-173">Если агент отключит получение звонков, он не будет включен в список маршрутов звонков независимо от состояния доступности.</span><span class="sxs-lookup"><span data-stu-id="a01b4-173">If an agent opts out of getting calls, they won't be included in the call routing list regardless of what their availability status is set to.</span></span> 

> [!NOTE]
> <span data-ttu-id="a01b4-174">Агенты, которые используют клиент Skype для бизнеса, не включаются в список маршрутов звонков, если включена маршрутия на основе присутствия.</span><span class="sxs-lookup"><span data-stu-id="a01b4-174">Agents who use the Skype for Business client aren't included in the call routing list when presence-based routing is enabled.</span></span> <span data-ttu-id="a01b4-175">Если у вас есть агенты, которые используют Skype для бизнеса, не в включаете маршрутику звонков на основе присутствия.</span><span class="sxs-lookup"><span data-stu-id="a01b4-175">If you have agents who use Skype for Business, don't enable presence-based call routing.</span></span>

<span data-ttu-id="a01b4-176">**Время оповещения агента** определяет, как долго телефон агента будет звонить, прежде чем очередь перенаправит звонок следующему агенту.</span><span class="sxs-lookup"><span data-stu-id="a01b4-176">**Agent alert time** specifies how long an agent's phone will ring before the queue redirects the call to the next agent.</span></span>

<span data-ttu-id="a01b4-177">Рекомендуется использовать следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="a01b4-177">The following settings are recommended:</span></span>

- <span data-ttu-id="a01b4-178">**Режим конференции с** **автоматическим**</span><span class="sxs-lookup"><span data-stu-id="a01b4-178">**Conference mode** to **Auto**</span></span>
- <span data-ttu-id="a01b4-179">**Способ маршрутинга до** **round или** **longest idle**</span><span class="sxs-lookup"><span data-stu-id="a01b4-179">**Routing method** to **Round robin** or **Longest idle**</span></span>
- <span data-ttu-id="a01b4-180">**Маршруты на основе присутствия в** В **сети**</span><span class="sxs-lookup"><span data-stu-id="a01b4-180">**Presence-based routing** to **On**</span></span>
- <span data-ttu-id="a01b4-181">**Время оповещения агента:** **до 20 секунд**</span><span class="sxs-lookup"><span data-stu-id="a01b4-181">**Agent alert time:** to **20 seconds**</span></span>

> [!NOTE]
> <span data-ttu-id="a01b4-182">Если маршрутия на основе присутствия не включена и в очереди несколько звонков, система будет одновременно представлять эти звонки агентам независимо от их состояния присутствия.</span><span class="sxs-lookup"><span data-stu-id="a01b4-182">If presence-based routing is not enabled and there are multiple calls in the queue, the system will present these calls simultaneously to the agents regardless of their presence status.</span></span> <span data-ttu-id="a01b4-183">В результате агенты получат несколько уведомлений о звонках, особенно если некоторые агенты не ответят на первоначальный звонок.</span><span class="sxs-lookup"><span data-stu-id="a01b4-183">This will result in multiple call notifications to agents, particularly if some agents don’t answer the initial call presented to them.</span></span>

## <a name="call-overflow-handling"></a><span data-ttu-id="a01b4-184">Обработка переполнения вызовов</span><span class="sxs-lookup"><span data-stu-id="a01b4-184">Call overflow handling</span></span>

![Снимок экрана: параметры переполнения звонка](media/call-queue-overflow-handling.png)

<span data-ttu-id="a01b4-186">**Максимальное число звонков** в очереди определяет максимальное количество звонков, которые могут быть в очереди в любое время.</span><span class="sxs-lookup"><span data-stu-id="a01b4-186">**Maximum calls in the queue** specifies the maximum number of calls that can wait in the queue at any given time.</span></span> <span data-ttu-id="a01b4-187">Значение по умолчанию — 50, но может быть от 0 до 200.</span><span class="sxs-lookup"><span data-stu-id="a01b4-187">The default is 50, but it can range from 0 to 200.</span></span> <span data-ttu-id="a01b4-188">Когда достигается это ограничение, звонок обрабатывается, как указано в параметре Когда достигается **максимальное количество звонков.**</span><span class="sxs-lookup"><span data-stu-id="a01b4-188">When this limit is reached, the call is handled as specified by the **When the maximum number of calls is reached** setting.</span></span>

<span data-ttu-id="a01b4-189">Вы можете отключить звонок или перенаправить его в любую из маршрутизов.</span><span class="sxs-lookup"><span data-stu-id="a01b4-189">You can choose to disconnect the call or redirect it to any of the call routing destinations.</span></span> <span data-ttu-id="a01b4-190">Например, вы можете оставить голосовое сообщение для агентов в очереди.</span><span class="sxs-lookup"><span data-stu-id="a01b4-190">For example, you might have the caller leave a voicemail for the agents in the queue.</span></span> <span data-ttu-id="a01b4-191">Сведения о внешних [](plan-auto-attendant-call-queue.md#prerequisites) переводах: [](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) технические сведения о формате номеров.</span><span class="sxs-lookup"><span data-stu-id="a01b4-191">For external transfers, please refer to [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) and the [external phone number transfers - technical details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) for number formatting.</span></span>

> [!NOTE]
> <span data-ttu-id="a01b4-192">Если максимальное количество звонков — 0, приветствие не будет воспроизведения.</span><span class="sxs-lookup"><span data-stu-id="a01b4-192">If the maximum number of calls is set to 0 then the greeting message will not play.</span></span>

## <a name="call-timeout-handling"></a><span data-ttu-id="a01b4-193">Обработка времени вызова</span><span class="sxs-lookup"><span data-stu-id="a01b4-193">Call timeout handling</span></span>

![Снимок экрана: параметры времени и времени вызова](media/call-queue-timeout-handling.png)

<span data-ttu-id="a01b4-195">**Время ожидания звонка: максимальное** время ожидания определяет максимальное время удержания звонка в очереди перед перенаправлением или отключением.</span><span class="sxs-lookup"><span data-stu-id="a01b4-195">**Call Timeout: maximum wait time** specifies the maximum time a call can be on hold in the queue before it is redirected or disconnected.</span></span> <span data-ttu-id="a01b4-196">Можно указать значение от 0 секунд до 45 минут.</span><span class="sxs-lookup"><span data-stu-id="a01b4-196">You can specify a value from 0 seconds to 45 minutes.</span></span>

<span data-ttu-id="a01b4-197">Вы можете отключить звонок или перенаправить его в одну из маршрутизов.</span><span class="sxs-lookup"><span data-stu-id="a01b4-197">You can choose to disconnect the call or redirect it to one of the call routing destinations.</span></span> <span data-ttu-id="a01b4-198">Например, вы можете оставить голосовое сообщение для агентов в очереди.</span><span class="sxs-lookup"><span data-stu-id="a01b4-198">For example, you might have the caller leave a voicemail for the agents in the queue.</span></span> <span data-ttu-id="a01b4-199">Сведения о внешних [](plan-auto-attendant-call-queue.md#prerequisites) переводах: [](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) технические сведения о формате номеров.</span><span class="sxs-lookup"><span data-stu-id="a01b4-199">For external transfers, please refer to [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) and the [external phone number transfers - technical details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) for number formatting.</span></span>

<span data-ttu-id="a01b4-200">Выбрав параметры времени и времени вызова, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="a01b4-200">When you have selected your call timeout options, click **Save**.</span></span>

## <a name="caller-id-for-outbound-calls"></a><span data-ttu-id="a01b4-201">ИД вызываемой звонков для исходящие вызовы</span><span class="sxs-lookup"><span data-stu-id="a01b4-201">Caller ID for outbound calls</span></span>

<span data-ttu-id="a01b4-202">Так как агенты в очереди зовов могут звонить, чтобы вернуть звонок клиента, можно установить для участников очереди зовов номер службы соответствующего автослужбу.</span><span class="sxs-lookup"><span data-stu-id="a01b4-202">Since agents in a call queue may dial out to return a customer call, consider setting the caller ID for members of a call queue to the service number of an appropriate auto attendant.</span></span> <span data-ttu-id="a01b4-203">Дополнительные [сведения см.](caller-id-policies.md) в этой записи.</span><span class="sxs-lookup"><span data-stu-id="a01b4-203">See [Manage caller ID policies in Microsoft Teams](caller-id-policies.md) for more information.</span></span>

## <a name="supported-clients"></a><span data-ttu-id="a01b4-204">Поддерживаемые клиенты</span><span class="sxs-lookup"><span data-stu-id="a01b4-204">Supported clients</span></span>

<span data-ttu-id="a01b4-205">Для агентов, которые находятся в очереди зовов, поддерживаются следующие клиенты:</span><span class="sxs-lookup"><span data-stu-id="a01b4-205">The following clients are supported for call agents in a call queue:</span></span>

  - <span data-ttu-id="a01b4-206">Клиент Skype для бизнеса для настольных ПК 2016 (32- и 64-битные версии)</span><span class="sxs-lookup"><span data-stu-id="a01b4-206">Skype for Business desktop client 2016 (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="a01b4-207">Клиент Lync для настольных пк 2013 (32- и 64-битные версии)</span><span class="sxs-lookup"><span data-stu-id="a01b4-207">Lync desktop client 2013 (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="a01b4-208">Все модели IP-телефонов, поддерживаемые в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="a01b4-208">All IP phone models supported for Microsoft Teams.</span></span> <span data-ttu-id="a01b4-209">См. [получение телефонов для Skype для бизнеса Online.](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online)</span><span class="sxs-lookup"><span data-stu-id="a01b4-209">See [Getting phones for Skype for Business Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span></span>
  - <span data-ttu-id="a01b4-210">Клиент Mac Skype для бизнеса (версия 16.8.196 и более поздние)</span><span class="sxs-lookup"><span data-stu-id="a01b4-210">Mac Skype for Business Client (version 16.8.196 and later)</span></span>
  - <span data-ttu-id="a01b4-211">Клиент Android Skype для бизнеса (версия 6.16.0.9 и более поздние)</span><span class="sxs-lookup"><span data-stu-id="a01b4-211">Android Skype for Business Client (version 6.16.0.9 and later)</span></span>
  - <span data-ttu-id="a01b4-212">Клиент iPhone Skype для бизнеса (версия 6.16.0 и более поздние)</span><span class="sxs-lookup"><span data-stu-id="a01b4-212">iPhone Skype for Business Client (version 6.16.0 and later)</span></span>
  - <span data-ttu-id="a01b4-213">Клиент iPad Skype для бизнеса (версия 6.16.0 и более поздние)</span><span class="sxs-lookup"><span data-stu-id="a01b4-213">iPad Skype for Business Client (version 6.16.0 and later)</span></span>
  - <span data-ttu-id="a01b4-214">Клиент Microsoft Teams для Windows (32- и 64-битные версии)</span><span class="sxs-lookup"><span data-stu-id="a01b4-214">Microsoft Teams Windows client (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="a01b4-215">Клиент Microsoft Teams Mac</span><span class="sxs-lookup"><span data-stu-id="a01b4-215">Microsoft Teams Mac client</span></span>
  - <span data-ttu-id="a01b4-216">Microsoft Teams в [виртуальной инфраструктуре рабочего стола](/microsoftteams/teams-for-vdi) (виртуальный рабочий стол Windows, Citrix и VMWARE)</span><span class="sxs-lookup"><span data-stu-id="a01b4-216">Microsoft Teams on [Virtualized Desktop Infrastructure](/microsoftteams/teams-for-vdi) (Windows Virtual Desktop, Citrix, and VMware)</span></span>
  - <span data-ttu-id="a01b4-217">Приложение Microsoft Teams для iPhone</span><span class="sxs-lookup"><span data-stu-id="a01b4-217">Microsoft Teams iPhone app</span></span>
  - <span data-ttu-id="a01b4-218">Приложение Microsoft Teams для Android</span><span class="sxs-lookup"><span data-stu-id="a01b4-218">Microsoft Teams Android app</span></span>

    > [!NOTE]
    > <span data-ttu-id="a01b4-219">Очереди звонков, которые имеют прямой маршрутный номер, не поддерживают клиенты Skype для бизнеса, клиенты Lync и IP-телефоны Skype для бизнеса в качестве агентов.</span><span class="sxs-lookup"><span data-stu-id="a01b4-219">Call queues that are assigned a direct routing number don't support Skype for Business clients, Lync clients, or Skype for Business IP Phones as agents.</span></span>

## <a name="call-queue-cmdlets"></a><span data-ttu-id="a01b4-220">Командлеты для работы с очередями звонков</span><span class="sxs-lookup"><span data-stu-id="a01b4-220">Call queue cmdlets</span></span>

<span data-ttu-id="a01b4-221">Для создания и настройки очередей звонков также можно использовать Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a01b4-221">You can also use Windows PowerShell to create and set up call queues.</span></span> <span data-ttu-id="a01b4-222">Ниже 2010 г. вы можете использовать для управления очередью вызовов.</span><span class="sxs-lookup"><span data-stu-id="a01b4-222">Here are the cmdlets that you use to manage a call queue.</span></span>

- [<span data-ttu-id="a01b4-223">New-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="a01b4-223">New-CsCallQueue</span></span>](/powershell/module/skype/new-CsCallQueue)

- [<span data-ttu-id="a01b4-224">Set-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="a01b4-224">Set-CsCallQueue</span></span>](/powershell/module/skype/set-CsCallQueue)

- [<span data-ttu-id="a01b4-225">Get-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="a01b4-225">Get-CsCallQueue</span></span>](/powershell/module/skype/get-CsCallQueue)

- [<span data-ttu-id="a01b4-226">Remove-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="a01b4-226">Remove-CsCallQueue</span></span>](/powershell/module/skype/remove-CsCallQueue)

## <a name="related-topics"></a><span data-ttu-id="a01b4-227">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="a01b4-227">Related topics</span></span>

[<span data-ttu-id="a01b4-228">Возможности телефонной системы</span><span class="sxs-lookup"><span data-stu-id="a01b4-228">Here's what you get with Phone System</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="a01b4-229">Получение номеров телефонов служб</span><span class="sxs-lookup"><span data-stu-id="a01b4-229">Getting service phone numbers</span></span>](getting-service-phone-numbers.md)

[<span data-ttu-id="a01b4-230">Доступность аудиоконференций и планов звонков в различных странах и регионах</span><span class="sxs-lookup"><span data-stu-id="a01b4-230">Country and region availability for Audio Conferencing and Calling Plans</span></span>](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[<span data-ttu-id="a01b4-231">New-CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="a01b4-231">New-CsOnlineApplicationInstance</span></span>](/powershell/module/skype/new-csonlineapplicationinstance)

[<span data-ttu-id="a01b4-232">Введение в Windows PowerShell и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="a01b4-232">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
