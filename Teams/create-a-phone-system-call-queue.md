---
title: Создание очереди звонков в Microsoft Teams
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
description: Сведения о том, как настроить телефонную систему для очередей звонков в Microsoft Teams, которая предоставляет сообщение приветствия, перенаправление музыки, переадресацию звонков и другие возможности.
ms.openlocfilehash: 9825c6ed1780efa78bfdbc86911e9b403be589f6
ms.sourcegitcommit: 273f231098799975dc4cf609a68c9944b8072ce1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2020
ms.locfileid: "48820026"
---
# <a name="create-a-call-queue"></a><span data-ttu-id="87895-103">Создание очереди вызовов</span><span class="sxs-lookup"><span data-stu-id="87895-103">Create a call queue</span></span>

<span data-ttu-id="87895-104">Очереди звонков предоставляют способ маршрутизации вызывающих абонентов людям из вашей организации, которые могут помочь вам с определенной проблемой или вопросом.</span><span class="sxs-lookup"><span data-stu-id="87895-104">Call queues provide a method of routing callers to people in your organization who can help with with a particular issue or question.</span></span> <span data-ttu-id="87895-105">Звонки распределяются по одному за один раз людям в очереди (которые называются *агентами* ).</span><span class="sxs-lookup"><span data-stu-id="87895-105">Calls are distributed one at a time to the people in the queue (who are known as *agents* ).</span></span> 

<span data-ttu-id="87895-106">Очереди звонков предоставляют следующие возможности.</span><span class="sxs-lookup"><span data-stu-id="87895-106">Call queues provide:</span></span>

- <span data-ttu-id="87895-107">Сообщение приветствия.</span><span class="sxs-lookup"><span data-stu-id="87895-107">A greeting message.</span></span>

- <span data-ttu-id="87895-108">Музыка, пока люди ожидают на удержании в очереди.</span><span class="sxs-lookup"><span data-stu-id="87895-108">Music while people are waiting on hold in a queue.</span></span>

- <span data-ttu-id="87895-109">Маршрутизация звонков — *в заказах (FIFO* ) — это агенты.</span><span class="sxs-lookup"><span data-stu-id="87895-109">Call routing - in *First In, First Out* (FIFO) order - to agents.</span></span>

- <span data-ttu-id="87895-110">Параметры обработки для переполнения и тайм-аута очереди.</span><span class="sxs-lookup"><span data-stu-id="87895-110">Handling options for queue overflow and timeout.</span></span>

<span data-ttu-id="87895-111">Перед выполнением процедур в этой статье убедитесь, что у вас есть план прочтения [для команд автосекретаря и очереди звонков](plan-auto-attendant-call-queue.md) , а затем следуйте [инструкциям по началу работы](plan-auto-attendant-call-queue.md#getting-started) .</span><span class="sxs-lookup"><span data-stu-id="87895-111">Be sure you have read [Plan for Teams auto attendants and call queues](plan-auto-attendant-call-queue.md) and followed the [getting started steps](plan-auto-attendant-call-queue.md#getting-started) before you follow the procedures in this articles.</span></span>

<span data-ttu-id="87895-112">Чтобы настроить очередь звонков, в центре администрирования Teams разверните элемент **Голосовая связь** , выберите пункт **очереди звонков** , а затем нажмите кнопку **добавить** .</span><span class="sxs-lookup"><span data-stu-id="87895-112">To set up a call queue, in the Teams admin center, expand **Voice** , click **Call queues** , and then click **Add** .</span></span>

## <a name="resource-account-and-language"></a><span data-ttu-id="87895-113">Учетные записи ресурсов и язык</span><span class="sxs-lookup"><span data-stu-id="87895-113">Resource account and language</span></span>

![Снимок экрана: учетная запись ресурса и языковые параметры](media/call-queue-name-language.png)

1. <span data-ttu-id="87895-115">Введите имя очереди звонков.</span><span class="sxs-lookup"><span data-stu-id="87895-115">Type a name for the call queue.</span></span> <span data-ttu-id="87895-116">Агенты увидят это имя при получении входящего звонка из очереди.</span><span class="sxs-lookup"><span data-stu-id="87895-116">Agents will see this name when they receive an incoming call from the queue.</span></span>

2. <span data-ttu-id="87895-117">Нажмите кнопку **Добавить учетные записи** , выполните поиск учетной записи ресурса, которую вы хотите использовать в этой очереди звонков, нажмите кнопку **Добавить** , а затем — **добавить** .</span><span class="sxs-lookup"><span data-stu-id="87895-117">Click **Add accounts** , search for the resource account that you want to use with this call queue, click **Add** , and then click **Add** .</span></span>

3. <span data-ttu-id="87895-118">Выберите язык.</span><span class="sxs-lookup"><span data-stu-id="87895-118">Choose a language.</span></span> <span data-ttu-id="87895-119">Этот язык будет использоваться для создаваемых системой голосовых запросов и транскрипции голосовой почты (если вы включите их).</span><span class="sxs-lookup"><span data-stu-id="87895-119">This language will be used for system-generated voice prompts and voicemail transcription (if you enable them).</span></span>

## <a name="greetings-and-hold-music"></a><span data-ttu-id="87895-120">Поздравления и удержание музыки</span><span class="sxs-lookup"><span data-stu-id="87895-120">Greetings and hold music</span></span>

<span data-ttu-id="87895-121">Укажите, нужно ли воспроизводить приветствие для вызывающих абонентов при их поступлении в очередь.</span><span class="sxs-lookup"><span data-stu-id="87895-121">Specify if you want to play a greeting to callers when they arrive in the queue.</span></span> <span data-ttu-id="87895-122">Необходимо загрузить файл MP3, WAV или WMA, содержащий приветствие, которое вы хотите воспроизвести.</span><span class="sxs-lookup"><span data-stu-id="87895-122">You must upload an MP3, WAV, or WMA file containing the greeting that you want to play.</span></span>

<span data-ttu-id="87895-123">Teams по умолчанию предоставляет музыку для звонков, пока они находятся на удержании в очереди.</span><span class="sxs-lookup"><span data-stu-id="87895-123">Teams provides default music to callers while they are on hold in a queue.</span></span> <span data-ttu-id="87895-124">Если вы хотите воспроизводить определенный звуковой файл, выберите **Воспроизвести звуковой файл** и загрузить MP3, WAV-или WMA-файл.</span><span class="sxs-lookup"><span data-stu-id="87895-124">If you want to play a specific audio file, choose **Play an audio file** and upload an MP3, WAV, or WMA file.</span></span>

> [!NOTE]
> <span data-ttu-id="87895-125">Размер отправленной записи не может превышать 5 МБ.</span><span class="sxs-lookup"><span data-stu-id="87895-125">The uploaded recording can be no larger than 5 MB.</span></span>
> <span data-ttu-id="87895-126">Музыкальные данные по умолчанию, предоставленные в очередях звонков в Teams, не являются бесплатными для всех royaltiesных счетов вашей организации.</span><span class="sxs-lookup"><span data-stu-id="87895-126">The default music supplied in Teams call queues is free of any royalties payable by your organization.</span></span> 

## <a name="call-agents"></a><span data-ttu-id="87895-127">Агенты звонков</span><span class="sxs-lookup"><span data-stu-id="87895-127">Call agents</span></span>

<span data-ttu-id="87895-128">Выбранные агенты звонков должны быть одним из следующих:</span><span class="sxs-lookup"><span data-stu-id="87895-128">Call agents selected must be one of the following:</span></span> 

- <span data-ttu-id="87895-129">Пользователи в сети с лицензией на телефонную систему и включенной корпоративной голосовой связью</span><span class="sxs-lookup"><span data-stu-id="87895-129">Online users with a Phone System license and Enterprise Voice enabled</span></span>
- <span data-ttu-id="87895-130">Пользователи в сети с помощью тарифного плана</span><span class="sxs-lookup"><span data-stu-id="87895-130">Online users with a Calling Plan</span></span>
- <span data-ttu-id="87895-131">Локальные пользователи Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="87895-131">On-premises Skype for Business Server users</span></span>
- <span data-ttu-id="87895-132">Если агенты используют приложение Microsoft Teams для вызова очереди звонков, они должны находиться в режиме TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="87895-132">If your agents are using the Microsoft Teams app for call queue calls, they need to be in TeamsOnly mode.</span></span>

![Снимок экрана: параметры пользователей и групп для очередей звонков](media/call-queue-users-groups.png)

<span data-ttu-id="87895-134">С помощью групп вы можете добавить до 20 агентов по отдельности и до 200 агентами.</span><span class="sxs-lookup"><span data-stu-id="87895-134">You can add up to 20 agents individually and up to 200 agents via groups.</span></span>

<span data-ttu-id="87895-135">Чтобы добавить пользователя в очередь, нажмите кнопку **Добавить пользователей** , найдите пользователя, нажмите кнопку **Добавить** , а затем нажмите кнопку **добавить** .</span><span class="sxs-lookup"><span data-stu-id="87895-135">To add a user to the queue, click **Add users** , search for the user, click **Add** , and then click **Add** .</span></span>

<span data-ttu-id="87895-136">Чтобы добавить группу в очередь, нажмите кнопку **Добавить группы** , выполните поиск группы, нажмите кнопку **Добавить** , а затем нажмите кнопку **добавить** .</span><span class="sxs-lookup"><span data-stu-id="87895-136">To add a group to the queue, click **Add groups** , search for the group, click **Add** , and then click **Add** .</span></span> <span data-ttu-id="87895-137">Вы можете использовать списки рассылки, группы безопасности и группы Microsoft 365 или Microsoft Teams Teams.</span><span class="sxs-lookup"><span data-stu-id="87895-137">You can use distribution lists, security groups, and Microsoft 365 groups or Microsoft Teams teams.</span></span>

> [!NOTE]
> <span data-ttu-id="87895-138">Для первого звонка новых пользователей, добавленных в группу, может потребоваться до восьми часов.</span><span class="sxs-lookup"><span data-stu-id="87895-138">New users added to a group can take up to eight hours for their first call to arrive.</span></span>

## <a name="call-routing"></a><span data-ttu-id="87895-139">Маршрутизация вызовов</span><span class="sxs-lookup"><span data-stu-id="87895-139">Call routing</span></span>

![Снимок экрана: режим конференции и параметры метода маршрутизации](media/call-queue-conference-mode-routing-method.png)

<span data-ttu-id="87895-141">**Режим конференции** значительно сокращает количество времени, затрачиваемого на подключение вызывающего абонента к агенту после того, как агент допускает звонок.</span><span class="sxs-lookup"><span data-stu-id="87895-141">**Conference mode** significantly reduces the amount of time it takes for a caller to be connected to an agent, after the agent accepts the call.</span></span> <span data-ttu-id="87895-142">Для работы режима конференции агенты в очереди звонков должны использовать один из следующих клиентов:</span><span class="sxs-lookup"><span data-stu-id="87895-142">For conference mode to work, agents in the call queue must use one of the following clients:</span></span>

  - <span data-ttu-id="87895-143">Новейшая версия клиента Microsoft Teams для настольных компьютеров, приложения Android или приложения для iOS</span><span class="sxs-lookup"><span data-stu-id="87895-143">The latest version of the Microsoft Teams desktop client, Android app, or iOS app</span></span>
  - <span data-ttu-id="87895-144">Microsoft Teams Phone версии 1449/1.0.94.2020051601 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="87895-144">Microsoft Teams phone version 1449/1.0.94.2020051601 or later</span></span>
  
<span data-ttu-id="87895-145">Учетные записи Teams должны быть установлены в режим только для Teams.</span><span class="sxs-lookup"><span data-stu-id="87895-145">Agents' Teams accounts need to be set to Teams-only mode.</span></span> <span data-ttu-id="87895-146">Агенты, которые не соответствуют требованиям, не включаются в список маршрутизации звонков.</span><span class="sxs-lookup"><span data-stu-id="87895-146">Agents who don't meet the requirements aren't included in the call routing list.</span></span> <span data-ttu-id="87895-147">Мы рекомендуем включить режим конференции для очередей звонков, если все агенты используют совместимые клиенты.</span><span class="sxs-lookup"><span data-stu-id="87895-147">We recommend enabling conference mode for your call queues if your agents are all using compatible clients.</span></span>

> [!NOTE]
> <span data-ttu-id="87895-148">Функция Busy on Busy не поддерживается режимом Конференции.</span><span class="sxs-lookup"><span data-stu-id="87895-148">Busy on Busy is not supported by conference mode.</span></span> <span data-ttu-id="87895-149">Если маршрутизация на основе сведений о присутствии не включена, агенты для вызовов из очереди, не вызывающей звонки, могут по-прежнему представляться в очереди звонков.</span><span class="sxs-lookup"><span data-stu-id="87895-149">Agents on non-call queue calls may still be presented with a call queue call if presence-based routing is not enabled.</span></span>

<span data-ttu-id="87895-150">**Метод маршрутизации** определяет порядок, в котором агенты принимают звонки из очереди.</span><span class="sxs-lookup"><span data-stu-id="87895-150">**Routing method** determines the order in which agents receive calls from the queue.</span></span> <span data-ttu-id="87895-151">Выберите один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="87895-151">Choose from these options:</span></span>

- <span data-ttu-id="87895-152">**Участники, маршрутизация с участием** всех агентов в очереди.</span><span class="sxs-lookup"><span data-stu-id="87895-152">**Attendant routing** rings all agents in the queue at the same time.</span></span> <span data-ttu-id="87895-153">Вызов вызывается агентом первого вызова для выбора звонка.</span><span class="sxs-lookup"><span data-stu-id="87895-153">The first call agent to pick up the call gets the call.</span></span>

- <span data-ttu-id="87895-154">**Последовательная маршрутизация** – это все агенты звонков по одному на один на единицу в порядке, указанном в списке **агенты звонков** .</span><span class="sxs-lookup"><span data-stu-id="87895-154">**Serial routing** rings all call agents one by one in the order specified in the **Call agents** list.</span></span> <span data-ttu-id="87895-155">Если агент закрывает или не берет на себя звонок, Звонок будет поступать на следующий агент и будет пытаться выполнить все агенты до тех пор, пока не будет выбрано или истечет время ожидания.</span><span class="sxs-lookup"><span data-stu-id="87895-155">If an agent dismisses or does not pick up a call, the call will ring the next agent and will try all agents until it is picked up or times out.</span></span>

- <span data-ttu-id="87895-156">Функция " **циклический перебор** " обеспечивает маршрутизацию входящих звонков, так что каждый агент вызова получает одинаковое количество звонков из очереди.</span><span class="sxs-lookup"><span data-stu-id="87895-156">**Round robin** balances the routing of incoming calls so that each call agent gets the same number of calls from the queue.</span></span> <span data-ttu-id="87895-157">Это может быть предпочтительнее в входящей среде продаж для обеспечения возможной возможности между всеми агентами звонков.</span><span class="sxs-lookup"><span data-stu-id="87895-157">This may be desirable in an inbound sales environment to assure equal opportunity among all the call agents.</span></span>

- <span data-ttu-id="87895-158">**Наиболее продолжительные простаивающие** маршруты каждый раз при каждом вызове агента, который был неактивен в течение длительного времени.</span><span class="sxs-lookup"><span data-stu-id="87895-158">**Longest idle** routes each call to the agent who has been idle the longest time.</span></span> <span data-ttu-id="87895-159">Агент считается бездействует, если его состояние присутствия доступно, или если состояние присутствия установлено менее 10 минут.</span><span class="sxs-lookup"><span data-stu-id="87895-159">An agent is considered idle if their presence state is Available or if their presence state has been Away for less than 10 minutes.</span></span> <span data-ttu-id="87895-160">Агенты с состоянием присутствия больше 10 минут не рассматриваются как неактивные и не могут принимать звонки до тех пор, пока они не изменяют их присутствие на доступ.</span><span class="sxs-lookup"><span data-stu-id="87895-160">Agents whose presence state has been Away for more than 10 minutes are not considered idle and will not be eligible to receive calls until they change their presence to Available.</span></span> 

![Снимок экрана: параметры маршрутизации, отказа и времени оповещения](media/call-queue-presence-agents-time.png)


<span data-ttu-id="87895-162">**Маршрутизация на основе присутствия** использует состояние доступности агенты по вызову, чтобы определить, должен ли агент быть включен в список маршрутизации звонков для выбранного метода маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="87895-162">**Presence-based routing** uses the availability status of call agents to determine whether an agent should be included in the call routing list for the selected routing method.</span></span> <span data-ttu-id="87895-163">Агенты звонков, состояние доступности которых равно " **доступен** ", включаются в список маршрутизации звонков и могут принимать звонки.</span><span class="sxs-lookup"><span data-stu-id="87895-163">Call agents whose availability status is set to **Available** are included in the call routing list and can receive calls.</span></span> <span data-ttu-id="87895-164">Агенты с состоянием доступности, для которого задано другое состояние, исключаются из списка маршрутизации звонков и не будут получать звонки до тех пор, пока их состояние доступности не изменится на " **недоступно** ".</span><span class="sxs-lookup"><span data-stu-id="87895-164">Agents whose availability status is set to any other status are excluded from the call routing list and won't receive calls until their availability status changes back to **Available** .</span></span> 

<span data-ttu-id="87895-165">Вы можете включить маршрутизацию звонков на основе присутствия, используя любой из методов маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="87895-165">You can enable presence-based call routing with any of the routing methods.</span></span>

<span data-ttu-id="87895-166">Если агент выводит из приема звонков, они не включаются в список маршрутизации звонков независимо от того, какое состояние доступности установлено.</span><span class="sxs-lookup"><span data-stu-id="87895-166">If an agent opts out of getting calls, they won't be included in the call routing list regardless of what their availability status is set to.</span></span> 

> [!NOTE]
> <span data-ttu-id="87895-167">Агенты, которые используют клиента Skype для бизнеса, не включаются в список маршрутизации звонков, когда включена маршрутизация на основе присутствия.</span><span class="sxs-lookup"><span data-stu-id="87895-167">Agents who use the Skype for Business client aren't included in the call routing list when presence-based routing is enabled.</span></span> <span data-ttu-id="87895-168">Если у вас есть агенты, использующие Skype для бизнеса, не включайте маршрутизацию звонков на основе присутствия.</span><span class="sxs-lookup"><span data-stu-id="87895-168">If you have agents who use Skype for Business, don't enable presence-based call routing.</span></span>

<span data-ttu-id="87895-169">**Время оповещения агента** указывает, как долго телефон агента будет звонить, прежде чем очередь перенаправит звонок на следующий агент.</span><span class="sxs-lookup"><span data-stu-id="87895-169">**Agent alert time** specifies how long an agent's phone will ring before the queue redirects the call to the next agent.</span></span>

<span data-ttu-id="87895-170">Для очереди больших объемов рекомендуется использовать указанные ниже параметры.</span><span class="sxs-lookup"><span data-stu-id="87895-170">For high volume queues, we recommend the following settings:</span></span>

- <span data-ttu-id="87895-171">**Автоматическое воспроизведение** **режима конференции**</span><span class="sxs-lookup"><span data-stu-id="87895-171">**Conference mode** to **Auto**</span></span>
- <span data-ttu-id="87895-172">**Метод маршрутизации** для **службы секретаря**</span><span class="sxs-lookup"><span data-stu-id="87895-172">**Routing method** to **Attendant routing**</span></span>
- <span data-ttu-id="87895-173">**Маршрутизация на основе присутствия** **On**</span><span class="sxs-lookup"><span data-stu-id="87895-173">**Presence-based routing** to **On**</span></span>
- <span data-ttu-id="87895-174">**Время оповещения агента:** **20 секунд**</span><span class="sxs-lookup"><span data-stu-id="87895-174">**Agent alert time:** to **20 seconds**</span></span>

## <a name="call-overflow-handling"></a><span data-ttu-id="87895-175">Обработка переполнения вызова</span><span class="sxs-lookup"><span data-stu-id="87895-175">Call overflow handling</span></span>

![Снимок экрана: параметры переполнения звонка](media/call-queue-overflow-handling.png)

<span data-ttu-id="87895-177">**Максимальное число вызовов в очереди** определяет максимальное количество звонков, которые могут ожидать в очереди в любой момент времени.</span><span class="sxs-lookup"><span data-stu-id="87895-177">**Maximum calls in the queue** specifies the maximum number of calls that can wait in the queue at any given time.</span></span> <span data-ttu-id="87895-178">Значение по умолчанию — 50, но может принимать значения от 0 до 200.</span><span class="sxs-lookup"><span data-stu-id="87895-178">The default is 50, but it can range from 0 to 200.</span></span> <span data-ttu-id="87895-179">По достижении этого ограничения вызов обрабатывается, как указано в соответствии с настройкой **максимального количества звонков** .</span><span class="sxs-lookup"><span data-stu-id="87895-179">When this limit is reached, the call is handled as specified by the **When the maximum number of calls is reached** setting.</span></span>

<span data-ttu-id="87895-180">Вы можете отключить звонок или перенаправить его на любой из [назначений маршрутизации звонков](create-a-phone-system-auto-attendant.md#call-routing-options) за исключением оператора.</span><span class="sxs-lookup"><span data-stu-id="87895-180">You can choose to disconnect the call or redirect it to any of the [call routing destinations](create-a-phone-system-auto-attendant.md#call-routing-options) except the operator.</span></span> <span data-ttu-id="87895-181">Например, возможно, что вызывающий абонент оставит в очереди голосовую почту для агентов.</span><span class="sxs-lookup"><span data-stu-id="87895-181">For example, you might have the caller leave a voicemail for the agents in the queue.</span></span> <span data-ttu-id="87895-182">(Обратите внимание на [эти данные](https://docs.microsoft.com/microsoftteams/create-a-phone-system-auto-attendant#external-phone-number-transfers---technical-details) , если вы переносите на внешний номер.)</span><span class="sxs-lookup"><span data-stu-id="87895-182">(Note [these details](https://docs.microsoft.com/microsoftteams/create-a-phone-system-auto-attendant#external-phone-number-transfers---technical-details) if you're transferring to an external number.)</span></span>

> [!NOTE]
> <span data-ttu-id="87895-183">Если для максимального количества звонков задано значение 0, сообщение приветствия не будет воспроизводиться.</span><span class="sxs-lookup"><span data-stu-id="87895-183">If the maximum number of calls is set to 0 then the greeting message will not play.</span></span>

## <a name="call-timeout-handling"></a><span data-ttu-id="87895-184">Обработка таймаутов звонков</span><span class="sxs-lookup"><span data-stu-id="87895-184">Call timeout handling</span></span>

![Снимок экрана: параметры времени ожидания звонков](media/call-queue-timeout-handling.png)

<span data-ttu-id="87895-186">**Таймаут звонков: максимальное время ожидания** указывает максимальное время, в течение которого звонок может быть заблокирован в очереди перед тем, как он будет перенаправлен или отсоединен.</span><span class="sxs-lookup"><span data-stu-id="87895-186">**Call Timeout: maximum wait time** specifies the maximum time a call can be on hold in the queue before it is redirected or disconnected.</span></span> <span data-ttu-id="87895-187">Вы можете указать значение в интервале от 15 до 45 минут.</span><span class="sxs-lookup"><span data-stu-id="87895-187">You can specify a value from 15 seconds to 45 minutes.</span></span>

<span data-ttu-id="87895-188">Вы можете отключить звонок или перенаправить его на один из назначений маршрутизации звонков.</span><span class="sxs-lookup"><span data-stu-id="87895-188">You can choose to disconnect the call or redirect it to one of the call routing destinations.</span></span> <span data-ttu-id="87895-189">Например, возможно, что вызывающий абонент оставит в очереди голосовую почту для агентов.</span><span class="sxs-lookup"><span data-stu-id="87895-189">For example, you might have the caller leave a voicemail for the agents in the queue.</span></span>

<span data-ttu-id="87895-190">Выбрав параметры тайм-аута звонка, нажмите кнопку **сохранить** .</span><span class="sxs-lookup"><span data-stu-id="87895-190">When you have selected your call timeout options, click **Save** .</span></span>

## <a name="caller-id-for-outbound-calls"></a><span data-ttu-id="87895-191">ИДЕНТИФИКАЦИя вызывающего абонента для исходящих звонков</span><span class="sxs-lookup"><span data-stu-id="87895-191">Caller ID for outbound calls</span></span>

<span data-ttu-id="87895-192">Так как агенты в очереди звонков могут выпустить звонок, чтобы вернуть клиентскую функцию, можно задать для участников очереди звонков номер службы соответствующего автосекретаря.</span><span class="sxs-lookup"><span data-stu-id="87895-192">Since agents in a call queue may dial out to return a customer call, consider setting the caller ID for members of a call queue to the service number of an appropriate auto attendant.</span></span> <span data-ttu-id="87895-193">Дополнительные сведения приведены [в разделе Управление политиками идентификации вызывающего абонента в Microsoft Teams](caller-id-policies.md) .</span><span class="sxs-lookup"><span data-stu-id="87895-193">See [Manage caller ID policies in Microsoft Teams](caller-id-policies.md) for more information.</span></span>

## <a name="supported-clients"></a><span data-ttu-id="87895-194">Поддерживаемые клиенты</span><span class="sxs-lookup"><span data-stu-id="87895-194">Supported clients</span></span>

- <span data-ttu-id="87895-195">Для агентов звонков в очереди звонков поддерживаются следующие клиенты:</span><span class="sxs-lookup"><span data-stu-id="87895-195">The following clients are supported for call agents in a call queue:</span></span>

  - <span data-ttu-id="87895-196">Настольный клиент 2016 для настольных компьютеров Skype для бизнеса (32-разр и 64-разрядная версия)</span><span class="sxs-lookup"><span data-stu-id="87895-196">Skype for Business desktop client 2016 (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="87895-197">Классическое приложение Lync 2013 (32-разр и 64-разрядные версии)</span><span class="sxs-lookup"><span data-stu-id="87895-197">Lync desktop client 2013 (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="87895-198">Все модели IP-телефонов, поддерживаемые в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="87895-198">All IP phone models supported for Microsoft Teams.</span></span> <span data-ttu-id="87895-199">Узнайте о том, как [получить телефоны в Skype для бизнеса Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span><span class="sxs-lookup"><span data-stu-id="87895-199">See [Getting phones for Skype for Business Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span></span>
  - <span data-ttu-id="87895-200">Клиент Mac Skype для бизнеса (версия 16.8.196 и более поздние)</span><span class="sxs-lookup"><span data-stu-id="87895-200">Mac Skype for Business Client (version 16.8.196 and later)</span></span>
  - <span data-ttu-id="87895-201">Клиент Android Skype для бизнеса (версия 6.16.0.9 и более поздние)</span><span class="sxs-lookup"><span data-stu-id="87895-201">Android Skype for Business Client (version 6.16.0.9 and later)</span></span>
  - <span data-ttu-id="87895-202">Клиент iPhone Skype для бизнеса (версия 6.16.0 и более поздние)</span><span class="sxs-lookup"><span data-stu-id="87895-202">iPhone Skype for Business Client (version 6.16.0 and later)</span></span>
  - <span data-ttu-id="87895-203">Клиент iPad Skype для бизнеса (версия 6.16.0 и более поздние)</span><span class="sxs-lookup"><span data-stu-id="87895-203">iPad Skype for Business Client (version 6.16.0 and later)</span></span>
  - <span data-ttu-id="87895-204">Клиент Microsoft Teams для Windows (32-разрядная версия и 64-разр.)</span><span class="sxs-lookup"><span data-stu-id="87895-204">Microsoft Teams Windows client (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="87895-205">Клиент Microsoft Teams Mac</span><span class="sxs-lookup"><span data-stu-id="87895-205">Microsoft Teams Mac client</span></span>
  - <span data-ttu-id="87895-206">Приложение Microsoft Teams для iPhone</span><span class="sxs-lookup"><span data-stu-id="87895-206">Microsoft Teams iPhone app</span></span>
  - <span data-ttu-id="87895-207">Приложение Microsoft Teams для Android</span><span class="sxs-lookup"><span data-stu-id="87895-207">Microsoft Teams Android app</span></span>

    > [!NOTE]
    > <span data-ttu-id="87895-208">Очереди звонков, которым назначен прямой номер маршрутизации, не поддерживают клиентов Skype для бизнеса, клиентов Lync и IP-телефоны Skype для бизнеса в качестве агентов.</span><span class="sxs-lookup"><span data-stu-id="87895-208">Call queues that are assigned a direct routing number don't support Skype for Business clients, Lync clients, or Skype for Business IP Phones as agents.</span></span>

## <a name="call-queue-cmdlets"></a><span data-ttu-id="87895-209">Командлеты для работы с очередями звонков</span><span class="sxs-lookup"><span data-stu-id="87895-209">Call queue cmdlets</span></span>

<span data-ttu-id="87895-210">Для создания и настройки очередей звонков также можно использовать Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="87895-210">You can also use Windows PowerShell to create and set up call queues.</span></span> <span data-ttu-id="87895-211">Ниже приведены командлеты, которые вы используете для управления очередью звонков.</span><span class="sxs-lookup"><span data-stu-id="87895-211">Here are the cmdlets that you use to manage a call queue.</span></span>

- [<span data-ttu-id="87895-212">New-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="87895-212">New-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/new-CsCallQueue)

- [<span data-ttu-id="87895-213">Set-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="87895-213">Set-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/set-CsCallQueue)

- [<span data-ttu-id="87895-214">Get-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="87895-214">Get-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/get-CsCallQueue)

- [<span data-ttu-id="87895-215">Remove-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="87895-215">Remove-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-CsCallQueue)

## <a name="related-topics"></a><span data-ttu-id="87895-216">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="87895-216">Related topics</span></span>

[<span data-ttu-id="87895-217">Возможности телефонной системы</span><span class="sxs-lookup"><span data-stu-id="87895-217">Here's what you get with Phone System</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="87895-218">Получение номеров телефонов служб</span><span class="sxs-lookup"><span data-stu-id="87895-218">Getting service phone numbers</span></span>](getting-service-phone-numbers.md)

[<span data-ttu-id="87895-219">Доступность аудиоконференций и планов звонков в различных странах и регионах</span><span class="sxs-lookup"><span data-stu-id="87895-219">Country and region availability for Audio Conferencing and Calling Plans</span></span>](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[<span data-ttu-id="87895-220">New-CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="87895-220">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance)

[<span data-ttu-id="87895-221">Введение в Windows PowerShell и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="87895-221">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
