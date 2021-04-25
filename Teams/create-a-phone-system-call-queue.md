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
ms.openlocfilehash: f60714bc1c4868496209f414583c925da527460a
ms.sourcegitcommit: 900f28c4ac12d65ccbd996028205ba183b4afb03
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/24/2021
ms.locfileid: "51995287"
---
# <a name="create-a-call-queue"></a><span data-ttu-id="93f50-103">Создание очереди вызовов</span><span class="sxs-lookup"><span data-stu-id="93f50-103">Create a call queue</span></span>

<span data-ttu-id="93f50-104">Очереди вызовов предоставляют способ маршрутизации вызывающих людей в организации, которые могут помочь с определенной проблемой или вопросом.</span><span class="sxs-lookup"><span data-stu-id="93f50-104">Call queues provide a method of routing callers to people in your organization who can help with a particular issue or question.</span></span> <span data-ttu-id="93f50-105">Звонки распределяются по одному для людей, которые находятся в очереди (которые называются *агентами).*</span><span class="sxs-lookup"><span data-stu-id="93f50-105">Calls are distributed one at a time to the people in the queue (who are known as *agents*).</span></span> 

<span data-ttu-id="93f50-106">Очереди вызовов предоставляют:</span><span class="sxs-lookup"><span data-stu-id="93f50-106">Call queues provide:</span></span>

- <span data-ttu-id="93f50-107">Приветствие.</span><span class="sxs-lookup"><span data-stu-id="93f50-107">A greeting message.</span></span>

- <span data-ttu-id="93f50-108">Музыка, пока люди находятся на удержании в очереди.</span><span class="sxs-lookup"><span data-stu-id="93f50-108">Music while people are waiting on hold in a queue.</span></span>

- <span data-ttu-id="93f50-109">Маршрутия вызовов — в порядке first *In, First Out* (FIFO) — агентам.</span><span class="sxs-lookup"><span data-stu-id="93f50-109">Call routing - in *First In, First Out* (FIFO) order - to agents.</span></span>

- <span data-ttu-id="93f50-110">Параметры обработки для переполнения и времени ожидания в очереди.</span><span class="sxs-lookup"><span data-stu-id="93f50-110">Handling options for queue overflow and timeout.</span></span>

<span data-ttu-id="93f50-111">Прежде чем выполнять действия, которые вы выполните в [](plan-auto-attendant-call-queue.md#getting-started) этой статье, ознакомьтесь со статьей Планирование автоотводников и очередей вызовов [Teams](plan-auto-attendant-call-queue.md) и следуйте этим шагам.</span><span class="sxs-lookup"><span data-stu-id="93f50-111">Be sure you have read [Plan for Teams auto attendants and call queues](plan-auto-attendant-call-queue.md) and followed the [getting started steps](plan-auto-attendant-call-queue.md#getting-started) before you follow the procedures in this article.</span></span>

<span data-ttu-id="93f50-112">Чтобы настроить очередь вызовов, в Центре администрирования Teams разйдите в центр администрирования Teams кнопку **Голосовая** почта, выберите очереди зовов **и** нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="93f50-112">To set up a call queue, in the Teams admin center, expand **Voice**, click **Call queues**, and then click **Add**.</span></span>

## <a name="resource-account-and-language"></a><span data-ttu-id="93f50-113">Учетная запись ресурса и язык</span><span class="sxs-lookup"><span data-stu-id="93f50-113">Resource account and language</span></span>

![Снимок экрана: учетная запись ресурса и языковые параметры](media/call-queue-name-language.png)

1. <span data-ttu-id="93f50-115">Введите имя очереди вызовов.</span><span class="sxs-lookup"><span data-stu-id="93f50-115">Type a name for the call queue.</span></span>

2. <span data-ttu-id="93f50-116">Нажмите **кнопку Добавить учетные** записи , найдите учетную запись ресурса, которую вы хотите использовать с этой очередью вызовов, нажмите кнопку **Добавить,** а затем нажмите кнопку **Добавить.**</span><span class="sxs-lookup"><span data-stu-id="93f50-116">Click **Add accounts**, search for the resource account that you want to use with this call queue, click **Add**, and then click **Add**.</span></span> <span data-ttu-id="93f50-117">(Агенты увидят имя учетной записи ресурса, когда получат входящий звонок.)</span><span class="sxs-lookup"><span data-stu-id="93f50-117">(Agents will see the resource account name when they receive an incoming call.)</span></span>

3. <span data-ttu-id="93f50-118">Выберите [поддерживаемый язык.](create-a-phone-system-call-queue-languages.md)</span><span class="sxs-lookup"><span data-stu-id="93f50-118">Choose a [supported language](create-a-phone-system-call-queue-languages.md).</span></span> <span data-ttu-id="93f50-119">Этот язык будет использоваться для системных голосовых подсказок и транскрибации голосовой почты (если вы их включаете).</span><span class="sxs-lookup"><span data-stu-id="93f50-119">This language will be used for system-generated voice prompts and voicemail transcription (if you enable them).</span></span>

## <a name="greetings-and-music-on-hold-in-queue"></a><span data-ttu-id="93f50-120">Приветствия и музыка на удержании в очереди</span><span class="sxs-lookup"><span data-stu-id="93f50-120">Greetings and music on hold in queue</span></span>

<span data-ttu-id="93f50-121">Укажите, хотите ли вы, чтобы вызыватели могли разозвать приветствие при их поступления в очередь.</span><span class="sxs-lookup"><span data-stu-id="93f50-121">Specify if you want to play a greeting to callers when they arrive in the queue.</span></span> <span data-ttu-id="93f50-122">Необходимо отправить файл MP3, WAV или WMA, содержащий приветствие, которое вы хотите воспроизведения.</span><span class="sxs-lookup"><span data-stu-id="93f50-122">You must upload an MP3, WAV, or WMA file containing the greeting that you want to play.</span></span>

<span data-ttu-id="93f50-123">Teams предоставляет музыку по умолчанию вызывателям, когда они находятся на удержании в очереди.</span><span class="sxs-lookup"><span data-stu-id="93f50-123">Teams provides default music to callers while they are on hold in a queue.</span></span> <span data-ttu-id="93f50-124">Если вы хотите воспроизведения определенного  звукового файла, выберите Вариант воспроизведения звукового файла и загрузите файл MP3, WAV или WMA.</span><span class="sxs-lookup"><span data-stu-id="93f50-124">If you want to play a specific audio file, choose **Play an audio file** and upload an MP3, WAV, or WMA file.</span></span>

> [!NOTE]
> <span data-ttu-id="93f50-125">Размер загруженной записи не должен быть больше 5 МБ.</span><span class="sxs-lookup"><span data-stu-id="93f50-125">The uploaded recording can be no larger than 5 MB.</span></span>
> <span data-ttu-id="93f50-126">Музыка по умолчанию, которая предоставляется в очередях вызовов Teams, не предоставляется вашей организацией.</span><span class="sxs-lookup"><span data-stu-id="93f50-126">The default music supplied in Teams call queues is free of any royalties payable by your organization.</span></span> 

## <a name="call-agents"></a><span data-ttu-id="93f50-127">Агенты вызовов</span><span class="sxs-lookup"><span data-stu-id="93f50-127">Call agents</span></span>

<span data-ttu-id="93f50-128">Просмотрите [предварительные условия для добавления агентов в очередь вызовов.](plan-auto-attendant-call-queue.md#prerequisites)</span><span class="sxs-lookup"><span data-stu-id="93f50-128">Review the [prerequisites for adding agents to a call queue](plan-auto-attendant-call-queue.md#prerequisites).</span></span>

![Снимок экрана: параметры пользователей и групп для очередей вызовов](media/call-queue-users-groups.png)

##### <a name="teams-channel"></a><span data-ttu-id="93f50-130">Канал Teams</span><span class="sxs-lookup"><span data-stu-id="93f50-130">Teams channel</span></span>

<span data-ttu-id="93f50-131">В канале Teams можно добавить до 200 агентов.</span><span class="sxs-lookup"><span data-stu-id="93f50-131">You can add up to 200 agents via a Teams channel.</span></span>

<span data-ttu-id="93f50-132">Если вы хотите использовать [канал Teams](https://support.microsoft.com/office/9f07dabe-91c6-4a9b-a545-8ffdddd2504e)для управления очередью , выберите команду Выбрать **команду** и щелкните **Добавить канал**.</span><span class="sxs-lookup"><span data-stu-id="93f50-132">If you want to [use a Teams channel to manage the queue](https://support.microsoft.com/office/9f07dabe-91c6-4a9b-a545-8ffdddd2504e), select the **Choose a team** option and click **Add a channel**.</span></span> <span data-ttu-id="93f50-133">Найдите команду, которую хотите использовать, выберите ее и нажмите кнопку **Добавить.**</span><span class="sxs-lookup"><span data-stu-id="93f50-133">Search for the team that you want to use, select it, and click **Add**.</span></span> <span data-ttu-id="93f50-134">Выберите канал, который вы хотите использовать, и нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="93f50-134">Select the channel that you want to use and click **Apply**.</span></span>

<span data-ttu-id="93f50-135">При использовании канала Teams для очередей вызовов поддерживаются следующие клиенты:</span><span class="sxs-lookup"><span data-stu-id="93f50-135">The following clients are supported when using a Teams channel for call queues:</span></span> 

  - <span data-ttu-id="93f50-136">Клиент Microsoft Teams для Windows</span><span class="sxs-lookup"><span data-stu-id="93f50-136">Microsoft Teams Windows client</span></span>
  - <span data-ttu-id="93f50-137">Клиент Microsoft Teams Mac</span><span class="sxs-lookup"><span data-stu-id="93f50-137">Microsoft Teams Mac client</span></span>

##### <a name="users-and-groups"></a><span data-ttu-id="93f50-138">Пользователи и группы</span><span class="sxs-lookup"><span data-stu-id="93f50-138">Users and groups</span></span>

<span data-ttu-id="93f50-139">Вы можете добавить до 20 агентов по отдельности и до 200 агентов с помощью групп.</span><span class="sxs-lookup"><span data-stu-id="93f50-139">You can add up to 20 agents individually and up to 200 agents via groups.</span></span>

<span data-ttu-id="93f50-140">Если вы хотите добавить отдельных пользователей или группы в очередь, выберите **параметр Выбрать пользователей и** группы.</span><span class="sxs-lookup"><span data-stu-id="93f50-140">If you want to add individual users or groups to the queue, select the **Choose users and groups** option.</span></span> 

<span data-ttu-id="93f50-141">Чтобы добавить пользователя в очередь, нажмите **кнопку** Добавить пользователей , найдите пользователя, нажмите кнопку Добавить **и** выберите **добавить**.</span><span class="sxs-lookup"><span data-stu-id="93f50-141">To add a user to the queue, click **Add users**, search for the user, click **Add**, and then click **Add**.</span></span>

<span data-ttu-id="93f50-142">Чтобы добавить группу в очередь, нажмите кнопку Добавить группы **,** найдите группу, нажмите кнопку Добавить **и** выберите **добавить**.</span><span class="sxs-lookup"><span data-stu-id="93f50-142">To add a group to the queue, click **Add groups**, search for the group, click **Add**, and then click **Add**.</span></span> <span data-ttu-id="93f50-143">Вы можете использовать списки рассылки, группы безопасности и группы Microsoft 365 или команды Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="93f50-143">You can use distribution lists, security groups, and Microsoft 365 groups or Microsoft Teams teams.</span></span>

> [!NOTE]
> <span data-ttu-id="93f50-144">Первые вызовы новых пользователей, добавленных в группу, могут принимать до восьми часов.</span><span class="sxs-lookup"><span data-stu-id="93f50-144">New users added to a group can take up to eight hours for their first call to arrive.</span></span>

## <a name="call-routing"></a><span data-ttu-id="93f50-145">Маршрутизация вызовов</span><span class="sxs-lookup"><span data-stu-id="93f50-145">Call routing</span></span>

![Снимок экрана: режим конференции и параметры метода маршрутации](media/call-queue-conference-mode-routing-method.png)

<span data-ttu-id="93f50-147">**Режим конференции** значительно сокращает время, необходимое для связи звоняного с агентом, после того как агент принимает звонок.</span><span class="sxs-lookup"><span data-stu-id="93f50-147">**Conference mode** significantly reduces the amount of time it takes for a caller to be connected to an agent, after the agent accepts the call.</span></span> <span data-ttu-id="93f50-148">Чтобы режим конференции работал, агенты в очереди зовов должны использовать один из следующих клиентов:</span><span class="sxs-lookup"><span data-stu-id="93f50-148">For conference mode to work, agents in the call queue must use one of the following clients:</span></span>

  - <span data-ttu-id="93f50-149">Последняя версия клиента Microsoft Teams для настольных пк, приложения Android или приложения для iOS</span><span class="sxs-lookup"><span data-stu-id="93f50-149">The latest version of the Microsoft Teams desktop client, Android app, or iOS app</span></span>
  - <span data-ttu-id="93f50-150">Телефон Microsoft Teams версии 1449/1.0.94.2020051601 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="93f50-150">Microsoft Teams phone version 1449/1.0.94.2020051601 or later</span></span>
  
<span data-ttu-id="93f50-151">Учетные записи Teams агентов должны быть настроены в режиме только Teams.</span><span class="sxs-lookup"><span data-stu-id="93f50-151">Agents' Teams accounts need to be set to Teams-only mode.</span></span> <span data-ttu-id="93f50-152">Агенты, не отвечающие требованиям, не включаются в список маршрутов зовов.</span><span class="sxs-lookup"><span data-stu-id="93f50-152">Agents who don't meet the requirements aren't included in the call routing list.</span></span> <span data-ttu-id="93f50-153">Мы рекомендуем использовать режим конференции для очередей вызовов, если все ваши агенты используют совместимые клиенты.</span><span class="sxs-lookup"><span data-stu-id="93f50-153">We recommend enabling conference mode for your call queues if your agents are all using compatible clients.</span></span>

> [!NOTE]
> <span data-ttu-id="93f50-154">Режим конференции не поддерживается, если телефонные звонки перенаправлются в очередь из шлюза прямой маршрутации, который включен для маршрутизов по расположению.</span><span class="sxs-lookup"><span data-stu-id="93f50-154">Conference mode is not supported if phone calls are routed to the queue from a Direct Routing gateway that is enabled for Location Based Routing.</span></span>

<span data-ttu-id="93f50-155">**Способ маршрутики определяет** порядок, в котором агенты будут принимать звонки из очереди.</span><span class="sxs-lookup"><span data-stu-id="93f50-155">**Routing method** determines the order in which agents receive calls from the queue.</span></span> <span data-ttu-id="93f50-156">Выберите один из этих вариантов:</span><span class="sxs-lookup"><span data-stu-id="93f50-156">Choose from these options:</span></span>

- <span data-ttu-id="93f50-157">**Маршруты помощника одновременно** звонят всем агентам в очереди.</span><span class="sxs-lookup"><span data-stu-id="93f50-157">**Attendant routing** rings all agents in the queue at the same time.</span></span> <span data-ttu-id="93f50-158">Звонок получит первый агент звонка.</span><span class="sxs-lookup"><span data-stu-id="93f50-158">The first call agent to pick up the call gets the call.</span></span>

- <span data-ttu-id="93f50-159">**Порядковая маршрутия** звонит всем агентам по одному в порядке, указанном в списке **"Агенты звонка".**</span><span class="sxs-lookup"><span data-stu-id="93f50-159">**Serial routing** rings all call agents one by one in the order specified in the **Call agents** list.</span></span> <span data-ttu-id="93f50-160">Если агент отклоает звонок или не звонит, звонок звонит следующему агенту и пробует всех агентов до тех пор, пока он не будет отклонен или не будет разозваться.</span><span class="sxs-lookup"><span data-stu-id="93f50-160">If an agent dismisses or does not pick up a call, the call will ring the next agent and will try all agents until it is picked up or times out.</span></span>

- <span data-ttu-id="93f50-161">**Round balances** the routing of incoming calls so each call agent gets the same number of calls from the queue.</span><span class="sxs-lookup"><span data-stu-id="93f50-161">**Round robin** balances the routing of incoming calls so that each call agent gets the same number of calls from the queue.</span></span> <span data-ttu-id="93f50-162">Это может быть нежелательно в среде входящие продаж, чтобы обеспечить равные возможности для всех агентов звонка.</span><span class="sxs-lookup"><span data-stu-id="93f50-162">This may be desirable in an inbound sales environment to assure equal opportunity among all the call agents.</span></span>

- <span data-ttu-id="93f50-163">**Наиболее длинные** неавтоматные маршруты каждый звонок передается агенту, который простаивает в течение долгого времени.</span><span class="sxs-lookup"><span data-stu-id="93f50-163">**Longest idle** routes each call to the agent who has been idle the longest time.</span></span> <span data-ttu-id="93f50-164">Агент считается неающим, если его состояние присутствия доступно или состояние присутствия "Нет на нем" менее 10 минут.</span><span class="sxs-lookup"><span data-stu-id="93f50-164">An agent is considered idle if their presence state is Available or if their presence state has been Away for less than 10 minutes.</span></span> <span data-ttu-id="93f50-165">Агенты, состояние присутствия которых отсутствует более 10 минут, не считаются неавтными и не смогут принимать звонки, пока они не изменят свое состояние присутствия на В сети.</span><span class="sxs-lookup"><span data-stu-id="93f50-165">Agents whose presence state has been Away for more than 10 minutes are not considered idle and will not be eligible to receive calls until they change their presence to Available.</span></span> 

![Снимок экрана: параметры времени маршрутки, отказа и оповещений](media/call-queue-presence-agents-time.png)


<span data-ttu-id="93f50-167">**В маршрутике** на основе присутствия используется состояние доступности агентов звонка, чтобы определить, следует ли включить агента в список маршрутов зовов для выбранного метода маршрутики.</span><span class="sxs-lookup"><span data-stu-id="93f50-167">**Presence-based routing** uses the availability status of call agents to determine whether an agent should be included in the call routing list for the selected routing method.</span></span> <span data-ttu-id="93f50-168">Звонки от агентов, у  которых установлено состояние "В наличии", включаются в список маршрутов звонков и могут принимать звонки.</span><span class="sxs-lookup"><span data-stu-id="93f50-168">Call agents whose availability status is set to **Available** are included in the call routing list and can receive calls.</span></span> <span data-ttu-id="93f50-169">Агенты, состояние доступности которых имеет любое другое состояние, исключаются из списка маршрутов звонков и не будут получать звонки, пока их состояние доступности не изменится на **Доступно.**</span><span class="sxs-lookup"><span data-stu-id="93f50-169">Agents whose availability status is set to any other status are excluded from the call routing list and won't receive calls until their availability status changes back to **Available**.</span></span> 

<span data-ttu-id="93f50-170">Вы можете включить маршрутику вызовов на основе присутствия с помощью любого из способов маршрутизов.</span><span class="sxs-lookup"><span data-stu-id="93f50-170">You can enable presence-based call routing with any of the routing methods.</span></span>

<span data-ttu-id="93f50-171">Если агент отключит получение звонков, он не будет включен в список маршрутов звонков независимо от состояния доступности.</span><span class="sxs-lookup"><span data-stu-id="93f50-171">If an agent opts out of getting calls, they won't be included in the call routing list regardless of what their availability status is set to.</span></span> 

> [!NOTE]
> <span data-ttu-id="93f50-172">Агенты, которые используют клиент Skype для бизнеса, не включаются в список маршрутов звонков, если включена маршрутия на основе присутствия.</span><span class="sxs-lookup"><span data-stu-id="93f50-172">Agents who use the Skype for Business client aren't included in the call routing list when presence-based routing is enabled.</span></span> <span data-ttu-id="93f50-173">Если у вас есть агенты, которые используют Skype для бизнеса, не в включаете маршрутику звонков на основе присутствия.</span><span class="sxs-lookup"><span data-stu-id="93f50-173">If you have agents who use Skype for Business, don't enable presence-based call routing.</span></span>

<span data-ttu-id="93f50-174">**Время оповещения агента** определяет, как долго телефон агента будет звонить, прежде чем очередь перенаправит звонок следующему агенту.</span><span class="sxs-lookup"><span data-stu-id="93f50-174">**Agent alert time** specifies how long an agent's phone will ring before the queue redirects the call to the next agent.</span></span>

<span data-ttu-id="93f50-175">Рекомендуется использовать следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="93f50-175">The following settings are recommended:</span></span>

- <span data-ttu-id="93f50-176">**Режим конференции с** **автоматическим**</span><span class="sxs-lookup"><span data-stu-id="93f50-176">**Conference mode** to **Auto**</span></span>
- <span data-ttu-id="93f50-177">**Способ маршрутинга до** **round или** **longest idle**</span><span class="sxs-lookup"><span data-stu-id="93f50-177">**Routing method** to **Round robin** or **Longest idle**</span></span>
- <span data-ttu-id="93f50-178">**Маршруты на основе присутствия в** В **сети**</span><span class="sxs-lookup"><span data-stu-id="93f50-178">**Presence-based routing** to **On**</span></span>
- <span data-ttu-id="93f50-179">**Время оповещения агента:** **до 20 секунд**</span><span class="sxs-lookup"><span data-stu-id="93f50-179">**Agent alert time:** to **20 seconds**</span></span>

> [!NOTE]
> <span data-ttu-id="93f50-180">Если маршрутия на основе присутствия не включена и в очереди несколько звонков, система будет одновременно представлять эти звонки агентам независимо от их состояния присутствия.</span><span class="sxs-lookup"><span data-stu-id="93f50-180">If presence-based routing is not enabled and there are multiple calls in the queue, the system will present these calls simultaneously to the agents regardless of their presence status.</span></span> <span data-ttu-id="93f50-181">В результате агенты получат несколько уведомлений о звонках, особенно если некоторые агенты не ответят на первоначальный звонок.</span><span class="sxs-lookup"><span data-stu-id="93f50-181">This will result in multiple call notifications to agents, particularly if some agents don’t answer the initial call presented to them.</span></span>

## <a name="call-overflow-handling"></a><span data-ttu-id="93f50-182">Обработка переполнения вызовов</span><span class="sxs-lookup"><span data-stu-id="93f50-182">Call overflow handling</span></span>

![Снимок экрана: параметры переполнения звонка](media/call-queue-overflow-handling.png)

<span data-ttu-id="93f50-184">**Максимальное число звонков** в очереди определяет максимальное количество звонков, которые могут быть в очереди в любое время.</span><span class="sxs-lookup"><span data-stu-id="93f50-184">**Maximum calls in the queue** specifies the maximum number of calls that can wait in the queue at any given time.</span></span> <span data-ttu-id="93f50-185">Значение по умолчанию — 50, но может быть от 0 до 200.</span><span class="sxs-lookup"><span data-stu-id="93f50-185">The default is 50, but it can range from 0 to 200.</span></span> <span data-ttu-id="93f50-186">Когда достигается это ограничение, звонок обрабатывается, как указано в параметре Когда достигается **максимальное количество звонков.**</span><span class="sxs-lookup"><span data-stu-id="93f50-186">When this limit is reached, the call is handled as specified by the **When the maximum number of calls is reached** setting.</span></span>

<span data-ttu-id="93f50-187">Вы можете отключить звонок или перенаправить его в любую из маршрутизов.</span><span class="sxs-lookup"><span data-stu-id="93f50-187">You can choose to disconnect the call or redirect it to any of the call routing destinations.</span></span> <span data-ttu-id="93f50-188">Например, вы можете оставить голосовое сообщение для агентов в очереди.</span><span class="sxs-lookup"><span data-stu-id="93f50-188">For example, you might have the caller leave a voicemail for the agents in the queue.</span></span> <span data-ttu-id="93f50-189">Сведения о внешних [](plan-auto-attendant-call-queue.md#prerequisites) переводах: [](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) технические сведения о формате номеров.</span><span class="sxs-lookup"><span data-stu-id="93f50-189">For external transfers, please refer to [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) and the [external phone number transfers - technical details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) for number formatting.</span></span>

> [!NOTE]
> <span data-ttu-id="93f50-190">Если максимальное количество звонков — 0, приветствие не будет воспроизведения.</span><span class="sxs-lookup"><span data-stu-id="93f50-190">If the maximum number of calls is set to 0 then the greeting message will not play.</span></span>

## <a name="call-timeout-handling"></a><span data-ttu-id="93f50-191">Обработка времени вызова</span><span class="sxs-lookup"><span data-stu-id="93f50-191">Call timeout handling</span></span>

![Снимок экрана: параметры времени и времени вызова](media/call-queue-timeout-handling.png)

<span data-ttu-id="93f50-193">**Время ожидания звонка: максимальное** время ожидания определяет максимальное время удержания звонка в очереди перед перенаправлением или отключением.</span><span class="sxs-lookup"><span data-stu-id="93f50-193">**Call Timeout: maximum wait time** specifies the maximum time a call can be on hold in the queue before it is redirected or disconnected.</span></span> <span data-ttu-id="93f50-194">Можно указать значение от 0 секунд до 45 минут.</span><span class="sxs-lookup"><span data-stu-id="93f50-194">You can specify a value from 0 seconds to 45 minutes.</span></span>

<span data-ttu-id="93f50-195">Вы можете отключить звонок или перенаправить его в одну из маршрутизов.</span><span class="sxs-lookup"><span data-stu-id="93f50-195">You can choose to disconnect the call or redirect it to one of the call routing destinations.</span></span> <span data-ttu-id="93f50-196">Например, вы можете оставить голосовое сообщение для агентов в очереди.</span><span class="sxs-lookup"><span data-stu-id="93f50-196">For example, you might have the caller leave a voicemail for the agents in the queue.</span></span> <span data-ttu-id="93f50-197">Сведения о внешних [](plan-auto-attendant-call-queue.md#prerequisites) переводах: [](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) технические сведения о формате номеров.</span><span class="sxs-lookup"><span data-stu-id="93f50-197">For external transfers, please refer to [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) and the [external phone number transfers - technical details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) for number formatting.</span></span>

<span data-ttu-id="93f50-198">Выбрав параметры времени и времени вызова, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="93f50-198">When you have selected your call timeout options, click **Save**.</span></span>

## <a name="caller-id-for-outbound-calls"></a><span data-ttu-id="93f50-199">ИД вызываемой звонков для исходящие вызовы</span><span class="sxs-lookup"><span data-stu-id="93f50-199">Caller ID for outbound calls</span></span>

<span data-ttu-id="93f50-200">Так как агенты в очереди зовов могут звонить, чтобы вернуть звонок клиента, можно установить для участников очереди зовов номер службы соответствующего автослужбу.</span><span class="sxs-lookup"><span data-stu-id="93f50-200">Since agents in a call queue may dial out to return a customer call, consider setting the caller ID for members of a call queue to the service number of an appropriate auto attendant.</span></span> <span data-ttu-id="93f50-201">Дополнительные [сведения см.](caller-id-policies.md) в этой записи.</span><span class="sxs-lookup"><span data-stu-id="93f50-201">See [Manage caller ID policies in Microsoft Teams](caller-id-policies.md) for more information.</span></span>

## <a name="supported-clients"></a><span data-ttu-id="93f50-202">Поддерживаемые клиенты</span><span class="sxs-lookup"><span data-stu-id="93f50-202">Supported clients</span></span>

<span data-ttu-id="93f50-203">Для агентов, которые находятся в очереди зовов, поддерживаются следующие клиенты:</span><span class="sxs-lookup"><span data-stu-id="93f50-203">The following clients are supported for call agents in a call queue:</span></span>

  - <span data-ttu-id="93f50-204">Клиент Skype для бизнеса для настольных ПК 2016 (32- и 64-битные версии)</span><span class="sxs-lookup"><span data-stu-id="93f50-204">Skype for Business desktop client 2016 (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="93f50-205">Клиент Lync для настольных пк 2013 (32- и 64-битные версии)</span><span class="sxs-lookup"><span data-stu-id="93f50-205">Lync desktop client 2013 (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="93f50-206">Все модели IP-телефонов, поддерживаемые в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="93f50-206">All IP phone models supported for Microsoft Teams.</span></span> <span data-ttu-id="93f50-207">См. [получение телефонов для Skype для бизнеса Online.](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online)</span><span class="sxs-lookup"><span data-stu-id="93f50-207">See [Getting phones for Skype for Business Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span></span>
  - <span data-ttu-id="93f50-208">Клиент Mac Skype для бизнеса (версия 16.8.196 и более поздние)</span><span class="sxs-lookup"><span data-stu-id="93f50-208">Mac Skype for Business Client (version 16.8.196 and later)</span></span>
  - <span data-ttu-id="93f50-209">Клиент Android Skype для бизнеса (версия 6.16.0.9 и более поздние)</span><span class="sxs-lookup"><span data-stu-id="93f50-209">Android Skype for Business Client (version 6.16.0.9 and later)</span></span>
  - <span data-ttu-id="93f50-210">Клиент iPhone Skype для бизнеса (версия 6.16.0 и более поздние)</span><span class="sxs-lookup"><span data-stu-id="93f50-210">iPhone Skype for Business Client (version 6.16.0 and later)</span></span>
  - <span data-ttu-id="93f50-211">Клиент iPad Skype для бизнеса (версия 6.16.0 и более поздние)</span><span class="sxs-lookup"><span data-stu-id="93f50-211">iPad Skype for Business Client (version 6.16.0 and later)</span></span>
  - <span data-ttu-id="93f50-212">Клиент Microsoft Teams для Windows (32- и 64-битные версии)</span><span class="sxs-lookup"><span data-stu-id="93f50-212">Microsoft Teams Windows client (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="93f50-213">Клиент Microsoft Teams Mac</span><span class="sxs-lookup"><span data-stu-id="93f50-213">Microsoft Teams Mac client</span></span>
  - <span data-ttu-id="93f50-214">Microsoft Teams в [виртуальной инфраструктуре рабочего стола](/microsoftteams/teams-for-vdi) (виртуальный рабочий стол Windows, Citrix и VMWARE)</span><span class="sxs-lookup"><span data-stu-id="93f50-214">Microsoft Teams on [Virtualized Desktop Infrastructure](/microsoftteams/teams-for-vdi) (Windows Virtual Desktop, Citrix, and VMware)</span></span>
  - <span data-ttu-id="93f50-215">Приложение Microsoft Teams для iPhone</span><span class="sxs-lookup"><span data-stu-id="93f50-215">Microsoft Teams iPhone app</span></span>
  - <span data-ttu-id="93f50-216">Приложение Microsoft Teams для Android</span><span class="sxs-lookup"><span data-stu-id="93f50-216">Microsoft Teams Android app</span></span>

    > [!NOTE]
    > <span data-ttu-id="93f50-217">Очереди звонков, которые имеют прямой маршрутный номер, не поддерживают клиенты Skype для бизнеса, клиенты Lync и IP-телефоны Skype для бизнеса в качестве агентов.</span><span class="sxs-lookup"><span data-stu-id="93f50-217">Call queues that are assigned a direct routing number don't support Skype for Business clients, Lync clients, or Skype for Business IP Phones as agents.</span></span>

## <a name="call-queue-cmdlets"></a><span data-ttu-id="93f50-218">Командлеты для работы с очередями звонков</span><span class="sxs-lookup"><span data-stu-id="93f50-218">Call queue cmdlets</span></span>

<span data-ttu-id="93f50-219">Для создания и настройки очередей звонков также можно использовать Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="93f50-219">You can also use Windows PowerShell to create and set up call queues.</span></span> <span data-ttu-id="93f50-220">Ниже 2010 г. вы можете использовать для управления очередью вызовов.</span><span class="sxs-lookup"><span data-stu-id="93f50-220">Here are the cmdlets that you use to manage a call queue.</span></span>

- [<span data-ttu-id="93f50-221">New-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="93f50-221">New-CsCallQueue</span></span>](/powershell/module/skype/new-CsCallQueue)

- [<span data-ttu-id="93f50-222">Set-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="93f50-222">Set-CsCallQueue</span></span>](/powershell/module/skype/set-CsCallQueue)

- [<span data-ttu-id="93f50-223">Get-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="93f50-223">Get-CsCallQueue</span></span>](/powershell/module/skype/get-CsCallQueue)

- [<span data-ttu-id="93f50-224">Remove-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="93f50-224">Remove-CsCallQueue</span></span>](/powershell/module/skype/remove-CsCallQueue)

## <a name="related-topics"></a><span data-ttu-id="93f50-225">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="93f50-225">Related topics</span></span>

[<span data-ttu-id="93f50-226">Возможности телефонной системы</span><span class="sxs-lookup"><span data-stu-id="93f50-226">Here's what you get with Phone System</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="93f50-227">Получение номеров телефонов служб</span><span class="sxs-lookup"><span data-stu-id="93f50-227">Getting service phone numbers</span></span>](getting-service-phone-numbers.md)

[<span data-ttu-id="93f50-228">Доступность аудиоконференций и планов звонков в различных странах и регионах</span><span class="sxs-lookup"><span data-stu-id="93f50-228">Country and region availability for Audio Conferencing and Calling Plans</span></span>](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[<span data-ttu-id="93f50-229">New-CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="93f50-229">New-CsOnlineApplicationInstance</span></span>](/powershell/module/skype/new-csonlineapplicationinstance)

[<span data-ttu-id="93f50-230">Введение в Windows PowerShell и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="93f50-230">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
