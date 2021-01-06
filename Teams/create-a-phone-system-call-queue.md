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
description: Узнайте, как настроить телефонную систему для очередей звонков в Microsoft Teams, которые предоставляют приветствие, музыку для удержания, перенаправление звонков и другие функции.
ms.openlocfilehash: d696b37f95d06c529aa330bd77e2ec91e1ffc9ad
ms.sourcegitcommit: 7575fb476a594d70084c603e508dd311ef1d7edb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/05/2021
ms.locfileid: "49765339"
---
# <a name="create-a-call-queue"></a><span data-ttu-id="d38d3-103">Создание очереди вызовов</span><span class="sxs-lookup"><span data-stu-id="d38d3-103">Create a call queue</span></span>

<span data-ttu-id="d38d3-104">Очереди вызовов предоставляют способ маршрутизации вызывающих вызовов для людей в организации, которые могут помочь с определенной проблемой или вопросом.</span><span class="sxs-lookup"><span data-stu-id="d38d3-104">Call queues provide a method of routing callers to people in your organization who can help with a particular issue or question.</span></span> <span data-ttu-id="d38d3-105">Звонки распределяются по одному людям в очереди (которые называются *агентами).*</span><span class="sxs-lookup"><span data-stu-id="d38d3-105">Calls are distributed one at a time to the people in the queue (who are known as *agents*).</span></span> 

<span data-ttu-id="d38d3-106">Очереди вызовов предоставляют:</span><span class="sxs-lookup"><span data-stu-id="d38d3-106">Call queues provide:</span></span>

- <span data-ttu-id="d38d3-107">Приветствие.</span><span class="sxs-lookup"><span data-stu-id="d38d3-107">A greeting message.</span></span>

- <span data-ttu-id="d38d3-108">Музыка, пока люди находятся в очереди на удержание.</span><span class="sxs-lookup"><span data-stu-id="d38d3-108">Music while people are waiting on hold in a queue.</span></span>

- <span data-ttu-id="d38d3-109">Маршрутка вызовов ( *в порядке first In, First Out* (FIFO) для агентов.</span><span class="sxs-lookup"><span data-stu-id="d38d3-109">Call routing - in *First In, First Out* (FIFO) order - to agents.</span></span>

- <span data-ttu-id="d38d3-110">Параметры обработки для переполнения очереди и времени ожидания.</span><span class="sxs-lookup"><span data-stu-id="d38d3-110">Handling options for queue overflow and timeout.</span></span>

<span data-ttu-id="d38d3-111">Прежде чем выполнять действия, которые вы выполните в [](plan-auto-attendant-call-queue.md#getting-started) этой статье, ознакомьтесь с планом для автоотетаря и очередей вызовов [Teams](plan-auto-attendant-call-queue.md) и следуйте этим шагам.</span><span class="sxs-lookup"><span data-stu-id="d38d3-111">Be sure you have read [Plan for Teams auto attendants and call queues](plan-auto-attendant-call-queue.md) and followed the [getting started steps](plan-auto-attendant-call-queue.md#getting-started) before you follow the procedures in this articles.</span></span>

<span data-ttu-id="d38d3-112">Чтобы настроить очередь вызовов, в Центре администрирования Teams раззовите "Голосовая команда", выберите "Очереди зовов" и нажмите кнопку  "Добавить". </span><span class="sxs-lookup"><span data-stu-id="d38d3-112">To set up a call queue, in the Teams admin center, expand **Voice**, click **Call queues**, and then click **Add**.</span></span>

## <a name="resource-account-and-language"></a><span data-ttu-id="d38d3-113">Учетная запись ресурса и язык</span><span class="sxs-lookup"><span data-stu-id="d38d3-113">Resource account and language</span></span>

![Снимок экрана: учетная запись ресурса и языковые параметры](media/call-queue-name-language.png)

1. <span data-ttu-id="d38d3-115">Введите имя очереди звонка.</span><span class="sxs-lookup"><span data-stu-id="d38d3-115">Type a name for the call queue.</span></span> <span data-ttu-id="d38d3-116">Это имя будет видно агентам при входящих вызовах из очереди.</span><span class="sxs-lookup"><span data-stu-id="d38d3-116">Agents will see this name when they receive an incoming call from the queue.</span></span>

2. <span data-ttu-id="d38d3-117">Нажмите **кнопку "Добавить учетные** записи", найдите учетную запись ресурса, которую вы хотите использовать с этой очередью вызовов, нажмите кнопку "Добавить", а затем нажмите кнопку **"Добавить".**</span><span class="sxs-lookup"><span data-stu-id="d38d3-117">Click **Add accounts**, search for the resource account that you want to use with this call queue, click **Add**, and then click **Add**.</span></span>

3. <span data-ttu-id="d38d3-118">Выберите язык.</span><span class="sxs-lookup"><span data-stu-id="d38d3-118">Choose a language.</span></span> <span data-ttu-id="d38d3-119">Этот язык будет использоваться для системных голосовых подсказок и транскрибации голосовой почты (если вы их включаете).</span><span class="sxs-lookup"><span data-stu-id="d38d3-119">This language will be used for system-generated voice prompts and voicemail transcription (if you enable them).</span></span>

## <a name="greetings-and-music-on-hold-in-queue"></a><span data-ttu-id="d38d3-120">Приветствия и музыка в очереди</span><span class="sxs-lookup"><span data-stu-id="d38d3-120">Greetings and music on hold in queue</span></span>

<span data-ttu-id="d38d3-121">Укажите, хотите ли вы воспроизведения приветствия вызывателям при их поступления в очередь.</span><span class="sxs-lookup"><span data-stu-id="d38d3-121">Specify if you want to play a greeting to callers when they arrive in the queue.</span></span> <span data-ttu-id="d38d3-122">Необходимо отправить файл MP3, WAV или WMA, содержащий приветствие, которое вы хотите воспроизведения.</span><span class="sxs-lookup"><span data-stu-id="d38d3-122">You must upload an MP3, WAV, or WMA file containing the greeting that you want to play.</span></span>

<span data-ttu-id="d38d3-123">Teams предоставляет музыку по умолчанию вызывателям, пока они находятся на удержании в очереди.</span><span class="sxs-lookup"><span data-stu-id="d38d3-123">Teams provides default music to callers while they are on hold in a queue.</span></span> <span data-ttu-id="d38d3-124">Если вы хотите воспроизведения определенного  звукового файла, выберите "Воспроизведения звукового файла" и загрузите файл MP3, WAV или WMA.</span><span class="sxs-lookup"><span data-stu-id="d38d3-124">If you want to play a specific audio file, choose **Play an audio file** and upload an MP3, WAV, or WMA file.</span></span>

> [!NOTE]
> <span data-ttu-id="d38d3-125">Размер добавленной записи не должен быть больше 5 МБ.</span><span class="sxs-lookup"><span data-stu-id="d38d3-125">The uploaded recording can be no larger than 5 MB.</span></span>
> <span data-ttu-id="d38d3-126">По умолчанию музыка, которая предоставляется в очередях вызовов Teams, не предоставляется вашей организацией.</span><span class="sxs-lookup"><span data-stu-id="d38d3-126">The default music supplied in Teams call queues is free of any royalties payable by your organization.</span></span> 

## <a name="call-agents"></a><span data-ttu-id="d38d3-127">Агенты вызовов</span><span class="sxs-lookup"><span data-stu-id="d38d3-127">Call agents</span></span>

<span data-ttu-id="d38d3-128">Чтобы добавить [агентов](plan-auto-attendant-call-queue.md#prerequisites) в очередь звонка, обратитесь к условиям.</span><span class="sxs-lookup"><span data-stu-id="d38d3-128">Please refer to the [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) in order to be able to add agents to a call queue.</span></span>

![Снимок экрана: параметры пользователей и групп для очередей вызовов](media/call-queue-users-groups.png)

<span data-ttu-id="d38d3-130">Вы можете добавить до 20 агентов по отдельности и до 200 агентов с помощью групп.</span><span class="sxs-lookup"><span data-stu-id="d38d3-130">You can add up to 20 agents individually and up to 200 agents via groups.</span></span>

<span data-ttu-id="d38d3-131">Чтобы добавить пользователя в очередь, нажмите кнопку "Добавить пользователей", найдите нужного пользователя, нажмите кнопку "Добавить" и выберите "Добавить". </span><span class="sxs-lookup"><span data-stu-id="d38d3-131">To add a user to the queue, click **Add users**, search for the user, click **Add**, and then click **Add**.</span></span>

<span data-ttu-id="d38d3-132">Чтобы добавить группу в очередь, нажмите кнопку "Добавить **группы",** найдите группу, нажмите кнопку "Добавить" и выберите "Добавить". </span><span class="sxs-lookup"><span data-stu-id="d38d3-132">To add a group to the queue, click **Add groups**, search for the group, click **Add**, and then click **Add**.</span></span> <span data-ttu-id="d38d3-133">Вы можете использовать списки рассылки, группы безопасности, группы Microsoft 365 или команды Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d38d3-133">You can use distribution lists, security groups, and Microsoft 365 groups or Microsoft Teams teams.</span></span>

> [!NOTE]
> <span data-ttu-id="d38d3-134">Для первого вызова новых пользователей, добавленных в группу, может быть до восьми часов.</span><span class="sxs-lookup"><span data-stu-id="d38d3-134">New users added to a group can take up to eight hours for their first call to arrive.</span></span>

## <a name="call-routing"></a><span data-ttu-id="d38d3-135">Маршрутизация вызовов</span><span class="sxs-lookup"><span data-stu-id="d38d3-135">Call routing</span></span>

![Снимок экрана: режим конференции и параметры метода маршрутации](media/call-queue-conference-mode-routing-method.png)

<span data-ttu-id="d38d3-137">**Режим конференц-связи** значительно сокращает время, необходимое для связи с агентом после того, как агент принимает звонок.</span><span class="sxs-lookup"><span data-stu-id="d38d3-137">**Conference mode** significantly reduces the amount of time it takes for a caller to be connected to an agent, after the agent accepts the call.</span></span> <span data-ttu-id="d38d3-138">Чтобы можно было работать в режиме конференции, агенты из очереди звонка должны использовать один из следующих клиентов:</span><span class="sxs-lookup"><span data-stu-id="d38d3-138">For conference mode to work, agents in the call queue must use one of the following clients:</span></span>

  - <span data-ttu-id="d38d3-139">Последняя версия клиента Microsoft Teams для настольных ПК, приложения Android или приложения для iOS</span><span class="sxs-lookup"><span data-stu-id="d38d3-139">The latest version of the Microsoft Teams desktop client, Android app, or iOS app</span></span>
  - <span data-ttu-id="d38d3-140">Телефон Microsoft Teams версии 1449/1.0.94.2020051601 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="d38d3-140">Microsoft Teams phone version 1449/1.0.94.2020051601 or later</span></span>
  
<span data-ttu-id="d38d3-141">Учетные записи Агентов в Teams должны быть настроены в режиме "Только teams".</span><span class="sxs-lookup"><span data-stu-id="d38d3-141">Agents' Teams accounts need to be set to Teams-only mode.</span></span> <span data-ttu-id="d38d3-142">Агенты, не отвечающие требованиям, не включаются в список маршрутов вызовов.</span><span class="sxs-lookup"><span data-stu-id="d38d3-142">Agents who don't meet the requirements aren't included in the call routing list.</span></span> <span data-ttu-id="d38d3-143">Мы рекомендуем использовать режим конференции для очередей звонка, если все ваши агенты используют совместимые клиенты.</span><span class="sxs-lookup"><span data-stu-id="d38d3-143">We recommend enabling conference mode for your call queues if your agents are all using compatible clients.</span></span>

> [!NOTE]
> <span data-ttu-id="d38d3-144">Заняты в режиме занятости не поддерживается режимом конференции.</span><span class="sxs-lookup"><span data-stu-id="d38d3-144">Busy on Busy is not supported by conference mode.</span></span> <span data-ttu-id="d38d3-145">Агенты, которые находятся в очереди звонков, могут по-прежнему получить вызов в очереди звонков, если не включена маршрутия на основе присутствия.</span><span class="sxs-lookup"><span data-stu-id="d38d3-145">Agents on non-call queue calls may still be presented with a call queue call if presence-based routing is not enabled.</span></span>

<span data-ttu-id="d38d3-146">**Способ маршрутики определяет** порядок, в котором агенты получают звонки из очереди.</span><span class="sxs-lookup"><span data-stu-id="d38d3-146">**Routing method** determines the order in which agents receive calls from the queue.</span></span> <span data-ttu-id="d38d3-147">Выберите один из этих вариантов:</span><span class="sxs-lookup"><span data-stu-id="d38d3-147">Choose from these options:</span></span>

- <span data-ttu-id="d38d3-148">**Маршрутка с помощником** одновременно звонит всем агентам в очереди.</span><span class="sxs-lookup"><span data-stu-id="d38d3-148">**Attendant routing** rings all agents in the queue at the same time.</span></span> <span data-ttu-id="d38d3-149">Звонок получает первый агент, который звонит.</span><span class="sxs-lookup"><span data-stu-id="d38d3-149">The first call agent to pick up the call gets the call.</span></span>

- <span data-ttu-id="d38d3-150">**В последовательной маршрутке** все агенты звонят по одному в порядке, указанном в списке агентов **по звонкам.**</span><span class="sxs-lookup"><span data-stu-id="d38d3-150">**Serial routing** rings all call agents one by one in the order specified in the **Call agents** list.</span></span> <span data-ttu-id="d38d3-151">Если агент отклоает или не берет звонок, звонок будет звонить следующему агенту и будет пытаться все агенты до тех пор, пока он не будет разозвать или невызовется.</span><span class="sxs-lookup"><span data-stu-id="d38d3-151">If an agent dismisses or does not pick up a call, the call will ring the next agent and will try all agents until it is picked up or times out.</span></span>

- <span data-ttu-id="d38d3-152">**Round balances** the routing of incoming calls so each call agent gets the same number of calls from the queue.</span><span class="sxs-lookup"><span data-stu-id="d38d3-152">**Round robin** balances the routing of incoming calls so that each call agent gets the same number of calls from the queue.</span></span> <span data-ttu-id="d38d3-153">Это может быть нежелательно в среде входящие продаж, чтобы гарантировать равные возможности для всех агентов по звонкам.</span><span class="sxs-lookup"><span data-stu-id="d38d3-153">This may be desirable in an inbound sales environment to assure equal opportunity among all the call agents.</span></span>

- <span data-ttu-id="d38d3-154">**Наиболее длинные** неавтомитные маршруты каждый звонок агенту, который простаивает самый длительный срок.</span><span class="sxs-lookup"><span data-stu-id="d38d3-154">**Longest idle** routes each call to the agent who has been idle the longest time.</span></span> <span data-ttu-id="d38d3-155">Агент считается неающим, если его состояние присутствия "В сети" или состояние присутствия "Нет на сети" менее 10 минут.</span><span class="sxs-lookup"><span data-stu-id="d38d3-155">An agent is considered idle if their presence state is Available or if their presence state has been Away for less than 10 minutes.</span></span> <span data-ttu-id="d38d3-156">Агенты, состояние присутствия которых отсутствует более 10 минут, не считаются неавными и не смогут получать звонки, пока не изменят свое состояние присутствия на "В сети".</span><span class="sxs-lookup"><span data-stu-id="d38d3-156">Agents whose presence state has been Away for more than 10 minutes are not considered idle and will not be eligible to receive calls until they change their presence to Available.</span></span> 

![Снимок экрана: параметры времени маршрутинга, отказа от работы и оповещений](media/call-queue-presence-agents-time.png)


<span data-ttu-id="d38d3-158">**В маршрутике** на основе присутствия используется состояние доступности агентов для определения того, следует ли включить агента в список маршрутов для выбранного метода маршрутинга.</span><span class="sxs-lookup"><span data-stu-id="d38d3-158">**Presence-based routing** uses the availability status of call agents to determine whether an agent should be included in the call routing list for the selected routing method.</span></span> <span data-ttu-id="d38d3-159">Call agents whose availability status is **set to Available are** included in the call routing list and can receive calls.</span><span class="sxs-lookup"><span data-stu-id="d38d3-159">Call agents whose availability status is set to **Available** are included in the call routing list and can receive calls.</span></span> <span data-ttu-id="d38d3-160">Агенты с любым другим состоянием доступности исключаются из списка маршрутов звонков и не будут получать звонки, пока их состояние не изменится на "В **наличии".**</span><span class="sxs-lookup"><span data-stu-id="d38d3-160">Agents whose availability status is set to any other status are excluded from the call routing list and won't receive calls until their availability status changes back to **Available**.</span></span> 

<span data-ttu-id="d38d3-161">Вы можете включить маршрутную маршрутику на основе присутствия с помощью любого из ее способов.</span><span class="sxs-lookup"><span data-stu-id="d38d3-161">You can enable presence-based call routing with any of the routing methods.</span></span>

<span data-ttu-id="d38d3-162">Если агент отключит получение звонков, он не будет включен в список маршрутов звонков независимо от задайте для него состояние доступности.</span><span class="sxs-lookup"><span data-stu-id="d38d3-162">If an agent opts out of getting calls, they won't be included in the call routing list regardless of what their availability status is set to.</span></span> 

> [!NOTE]
> <span data-ttu-id="d38d3-163">Агенты, которые используют клиент Skype для бизнеса, не включаются в список маршрутов звонков, если включена маршрутка на основе присутствия.</span><span class="sxs-lookup"><span data-stu-id="d38d3-163">Agents who use the Skype for Business client aren't included in the call routing list when presence-based routing is enabled.</span></span> <span data-ttu-id="d38d3-164">Если у вас есть агенты, которые используют Skype для бизнеса, не в включаете маршруты звонков на основе присутствия.</span><span class="sxs-lookup"><span data-stu-id="d38d3-164">If you have agents who use Skype for Business, don't enable presence-based call routing.</span></span>

<span data-ttu-id="d38d3-165">**Время оповещения агента** определяет, как долго телефон агента будет звонить до того, как очередь перенаправит звонок следующему агенту.</span><span class="sxs-lookup"><span data-stu-id="d38d3-165">**Agent alert time** specifies how long an agent's phone will ring before the queue redirects the call to the next agent.</span></span>

<span data-ttu-id="d38d3-166">Для очередей с высоким уровнем громкости рекомендуем использовать следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="d38d3-166">For high volume queues, we recommend the following settings:</span></span>

- <span data-ttu-id="d38d3-167">**Режим конференции с** **автоматическим**</span><span class="sxs-lookup"><span data-stu-id="d38d3-167">**Conference mode** to **Auto**</span></span>
- <span data-ttu-id="d38d3-168">**Способ маршрутинга для** **маршрутов Attendant**</span><span class="sxs-lookup"><span data-stu-id="d38d3-168">**Routing method** to **Attendant routing**</span></span>
- <span data-ttu-id="d38d3-169">**Маршрут с учетом присутствия в "В** **сети"**</span><span class="sxs-lookup"><span data-stu-id="d38d3-169">**Presence-based routing** to **On**</span></span>
- <span data-ttu-id="d38d3-170">**Время оповещения агента:** **до 20 секунд**</span><span class="sxs-lookup"><span data-stu-id="d38d3-170">**Agent alert time:** to **20 seconds**</span></span>

## <a name="call-overflow-handling"></a><span data-ttu-id="d38d3-171">Обработка переполнения вызовов</span><span class="sxs-lookup"><span data-stu-id="d38d3-171">Call overflow handling</span></span>

![Снимок экрана: параметры переполнения вызовов](media/call-queue-overflow-handling.png)

<span data-ttu-id="d38d3-173">**Максимальное число звонков** в очереди определяет максимальное количество звонков, которые могут быть в очереди в любое время.</span><span class="sxs-lookup"><span data-stu-id="d38d3-173">**Maximum calls in the queue** specifies the maximum number of calls that can wait in the queue at any given time.</span></span> <span data-ttu-id="d38d3-174">Значение по умолчанию — 50, но может быть в диапазоне от 0 до 200.</span><span class="sxs-lookup"><span data-stu-id="d38d3-174">The default is 50, but it can range from 0 to 200.</span></span> <span data-ttu-id="d38d3-175">По такому ограничению звонок обрабатывается в том случае, если установлено максимальное число **звонков.**</span><span class="sxs-lookup"><span data-stu-id="d38d3-175">When this limit is reached, the call is handled as specified by the **When the maximum number of calls is reached** setting.</span></span>

<span data-ttu-id="d38d3-176">Вы можете отключить звонок или перенаправить его в любую из маршрутизов.</span><span class="sxs-lookup"><span data-stu-id="d38d3-176">You can choose to disconnect the call or redirect it to any of the call routing destinations.</span></span> <span data-ttu-id="d38d3-177">Например, вы можете оставить голосовое сообщение для агентов в очереди.</span><span class="sxs-lookup"><span data-stu-id="d38d3-177">For example, you might have the caller leave a voicemail for the agents in the queue.</span></span> <span data-ttu-id="d38d3-178">Сведения о внешних [](plan-auto-attendant-call-queue.md#prerequisites) денежных переводах: предварительные условия и передача внешних номеров телефонов [—](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) технические сведения о формате номеров.</span><span class="sxs-lookup"><span data-stu-id="d38d3-178">For external transfers, please refer to [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) and the [external phone number transfers - technical details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) for number formatting.</span></span>

> [!NOTE]
> <span data-ttu-id="d38d3-179">Если максимальное число звонков — 0, приветствие не будет воспроизведения.</span><span class="sxs-lookup"><span data-stu-id="d38d3-179">If the maximum number of calls is set to 0 then the greeting message will not play.</span></span>

## <a name="call-timeout-handling"></a><span data-ttu-id="d38d3-180">Обработка времени вызова</span><span class="sxs-lookup"><span data-stu-id="d38d3-180">Call timeout handling</span></span>

![Снимок экрана: параметры времени и времени вызова](media/call-queue-timeout-handling.png)

<span data-ttu-id="d38d3-182">**Время ожидания звонка: максимальное** время ожидания определяет максимальное время удержания звонка в очереди перед его перенаправлением или отключением.</span><span class="sxs-lookup"><span data-stu-id="d38d3-182">**Call Timeout: maximum wait time** specifies the maximum time a call can be on hold in the queue before it is redirected or disconnected.</span></span> <span data-ttu-id="d38d3-183">Можно указать значение от 0 до 45 минут.</span><span class="sxs-lookup"><span data-stu-id="d38d3-183">You can specify a value from 0 seconds to 45 minutes.</span></span>

<span data-ttu-id="d38d3-184">Вы можете отключить звонок или перенаправить его в одно из маршрутов.</span><span class="sxs-lookup"><span data-stu-id="d38d3-184">You can choose to disconnect the call or redirect it to one of the call routing destinations.</span></span> <span data-ttu-id="d38d3-185">Например, вы можете оставить голосовое сообщение для агентов в очереди.</span><span class="sxs-lookup"><span data-stu-id="d38d3-185">For example, you might have the caller leave a voicemail for the agents in the queue.</span></span> <span data-ttu-id="d38d3-186">Сведения о внешних [](plan-auto-attendant-call-queue.md#prerequisites) денежных переводах: предварительные условия и передача внешних номеров телефонов [—](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) технические сведения о формате номеров.</span><span class="sxs-lookup"><span data-stu-id="d38d3-186">For external transfers, please refer to [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) and the [external phone number transfers - technical details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) for number formatting.</span></span>

<span data-ttu-id="d38d3-187">Выбрав параметры времени и времени и времени вызова, нажмите кнопку **"Сохранить".**</span><span class="sxs-lookup"><span data-stu-id="d38d3-187">When you have selected your call timeout options, click **Save**.</span></span>

## <a name="caller-id-for-outbound-calls"></a><span data-ttu-id="d38d3-188">ИД вызываемой звонков для исходящие вызовы</span><span class="sxs-lookup"><span data-stu-id="d38d3-188">Caller ID for outbound calls</span></span>

<span data-ttu-id="d38d3-189">Так как агенты из очереди параметров могут звонить и возвращать клиентский звонок, можно установить для участников очереди параметров номера службы для соответствующего автослужбу.</span><span class="sxs-lookup"><span data-stu-id="d38d3-189">Since agents in a call queue may dial out to return a customer call, consider setting the caller ID for members of a call queue to the service number of an appropriate auto attendant.</span></span> <span data-ttu-id="d38d3-190">Дополнительные сведения см. в сведениях об управлении политиками ИД вызываемой [службы в Microsoft Teams.](caller-id-policies.md)</span><span class="sxs-lookup"><span data-stu-id="d38d3-190">See [Manage caller ID policies in Microsoft Teams](caller-id-policies.md) for more information.</span></span>

## <a name="supported-clients"></a><span data-ttu-id="d38d3-191">Поддерживаемые клиенты</span><span class="sxs-lookup"><span data-stu-id="d38d3-191">Supported clients</span></span>

<span data-ttu-id="d38d3-192">Для агентов, которые находятся в очереди звонка, поддерживаются следующие клиенты:</span><span class="sxs-lookup"><span data-stu-id="d38d3-192">The following clients are supported for call agents in a call queue:</span></span>

  - <span data-ttu-id="d38d3-193">Клиент Skype для бизнеса для настольных ПК 2016 (32- и 64-битные версии)</span><span class="sxs-lookup"><span data-stu-id="d38d3-193">Skype for Business desktop client 2016 (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="d38d3-194">Клиент Lync для настольных пк 2013 (32- и 64-битные версии)</span><span class="sxs-lookup"><span data-stu-id="d38d3-194">Lync desktop client 2013 (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="d38d3-195">Все модели IP-телефонов, поддерживаемые в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d38d3-195">All IP phone models supported for Microsoft Teams.</span></span> <span data-ttu-id="d38d3-196">См. ["Получение телефонов для Skype для бизнеса Online".](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online)</span><span class="sxs-lookup"><span data-stu-id="d38d3-196">See [Getting phones for Skype for Business Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span></span>
  - <span data-ttu-id="d38d3-197">Клиент Mac Skype для бизнеса (версия 16.8.196 и более поздние)</span><span class="sxs-lookup"><span data-stu-id="d38d3-197">Mac Skype for Business Client (version 16.8.196 and later)</span></span>
  - <span data-ttu-id="d38d3-198">Клиент Android Skype для бизнеса (версия 6.16.0.9 и более поздние)</span><span class="sxs-lookup"><span data-stu-id="d38d3-198">Android Skype for Business Client (version 6.16.0.9 and later)</span></span>
  - <span data-ttu-id="d38d3-199">Клиент iPhone Skype для бизнеса (версия 6.16.0 и более поздние)</span><span class="sxs-lookup"><span data-stu-id="d38d3-199">iPhone Skype for Business Client (version 6.16.0 and later)</span></span>
  - <span data-ttu-id="d38d3-200">Клиент iPad Skype для бизнеса (версия 6.16.0 и более поздние)</span><span class="sxs-lookup"><span data-stu-id="d38d3-200">iPad Skype for Business Client (version 6.16.0 and later)</span></span>
  - <span data-ttu-id="d38d3-201">Клиент Microsoft Teams для Windows (32- и 64-битные версии)</span><span class="sxs-lookup"><span data-stu-id="d38d3-201">Microsoft Teams Windows client (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="d38d3-202">Клиент Microsoft Teams Mac</span><span class="sxs-lookup"><span data-stu-id="d38d3-202">Microsoft Teams Mac client</span></span>
  - <span data-ttu-id="d38d3-203">Приложение Microsoft Teams для iPhone</span><span class="sxs-lookup"><span data-stu-id="d38d3-203">Microsoft Teams iPhone app</span></span>
  - <span data-ttu-id="d38d3-204">Приложение Microsoft Teams для Android</span><span class="sxs-lookup"><span data-stu-id="d38d3-204">Microsoft Teams Android app</span></span>

    > [!NOTE]
    > <span data-ttu-id="d38d3-205">Очереди звонков, которые имеют прямой маршрутный номер, не поддерживают в качестве агентов клиенты Skype для бизнеса, клиенты Lync и IP-телефоны Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="d38d3-205">Call queues that are assigned a direct routing number don't support Skype for Business clients, Lync clients, or Skype for Business IP Phones as agents.</span></span>

## <a name="call-queue-cmdlets"></a><span data-ttu-id="d38d3-206">Командлеты для работы с очередями звонков</span><span class="sxs-lookup"><span data-stu-id="d38d3-206">Call queue cmdlets</span></span>

<span data-ttu-id="d38d3-207">Для создания и настройки очередей звонков также можно использовать Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d38d3-207">You can also use Windows PowerShell to create and set up call queues.</span></span> <span data-ttu-id="d38d3-208">Ниже находятся cmdlets, которые используются для управления очередью вызовов.</span><span class="sxs-lookup"><span data-stu-id="d38d3-208">Here are the cmdlets that you use to manage a call queue.</span></span>

- [<span data-ttu-id="d38d3-209">New-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="d38d3-209">New-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/new-CsCallQueue)

- [<span data-ttu-id="d38d3-210">Set-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="d38d3-210">Set-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/set-CsCallQueue)

- [<span data-ttu-id="d38d3-211">Get-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="d38d3-211">Get-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/get-CsCallQueue)

- [<span data-ttu-id="d38d3-212">Remove-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="d38d3-212">Remove-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-CsCallQueue)

## <a name="related-topics"></a><span data-ttu-id="d38d3-213">См. также</span><span class="sxs-lookup"><span data-stu-id="d38d3-213">Related topics</span></span>

[<span data-ttu-id="d38d3-214">Возможности телефонной системы</span><span class="sxs-lookup"><span data-stu-id="d38d3-214">Here's what you get with Phone System</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="d38d3-215">Получение номеров телефонов служб</span><span class="sxs-lookup"><span data-stu-id="d38d3-215">Getting service phone numbers</span></span>](getting-service-phone-numbers.md)

[<span data-ttu-id="d38d3-216">Доступность аудиоконференций и планов звонков в различных странах и регионах</span><span class="sxs-lookup"><span data-stu-id="d38d3-216">Country and region availability for Audio Conferencing and Calling Plans</span></span>](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[<span data-ttu-id="d38d3-217">New-CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="d38d3-217">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance)

[<span data-ttu-id="d38d3-218">Введение в Windows PowerShell и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="d38d3-218">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
