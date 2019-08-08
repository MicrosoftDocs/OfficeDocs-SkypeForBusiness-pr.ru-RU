---
title: Teams для инфраструктуры виртуальных рабочих столов
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 04/10/2019
ms.topic: article
ms.service: msteams
ms.reviewer: rafarhi
audience: admin
description: Сведения о том, как запускать Microsoft Teams в среде виртуализованной инфраструктуры для настольных компьютеров (VDI).
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1d0680e81799152bfc6eb9a976634384eb70954c
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2019
ms.locfileid: "36243824"
---
# <a name="teams-for-virtualized-desktop-infrastructure"></a><span data-ttu-id="49ac8-103">Teams для инфраструктуры виртуальных рабочих столов</span><span class="sxs-lookup"><span data-stu-id="49ac8-103">Teams for Virtualized Desktop Infrastructure</span></span>

<span data-ttu-id="49ac8-104">В этой статье описаны требования и ограничения для использования Microsoft Teams в виртуализованной среде.</span><span class="sxs-lookup"><span data-stu-id="49ac8-104">This article describes the requirements and limitations for using Microsoft Teams in a virtualized environment.</span></span>

## <a name="what-is-vdi"></a><span data-ttu-id="49ac8-105">Что такое VDI?</span><span class="sxs-lookup"><span data-stu-id="49ac8-105">What is VDI?</span></span>

<span data-ttu-id="49ac8-106">Инфраструктура виртуальных рабочих столов (VDI) — это технология виртуализации, в которой на центральном сервере в центре обработки данных размещены приложения для настольных систем и приложений.</span><span class="sxs-lookup"><span data-stu-id="49ac8-106">Virtual Desktop Infrastructure (VDI) is virtualization technology that hosts a desktop operating system and applications on a centralized server in a data center.</span></span> <span data-ttu-id="49ac8-107">Это обеспечивает полное персонализированное взаимодействие с пользователями с полностью защищенным и совместимым централизованным источником.</span><span class="sxs-lookup"><span data-stu-id="49ac8-107">This enables a fully personalized desktop experience to users with a fully secured and compliant centralized source.</span></span> 
 
<span data-ttu-id="49ac8-108">В настоящее время команды в виртуализованной среде доступны благодаря поддержке функций совместной работы и чата с выделенной постоянной виртуальной машиной (ВМ).</span><span class="sxs-lookup"><span data-stu-id="49ac8-108">Currently, Teams in a virtualized environment is available with support for collaboration and chat functionality with a dedicated persistent virtualized machine (VM).</span></span> <span data-ttu-id="49ac8-109">Для обеспечения оптимального взаимодействия с пользователем следуйте рекомендациям, приведенным в этой статье.</span><span class="sxs-lookup"><span data-stu-id="49ac8-109">To ensure an optimal user experience, follow the guidance in this article.</span></span> 

## <a name="teams-requirements"></a><span data-ttu-id="49ac8-110">Требования к Teams</span><span class="sxs-lookup"><span data-stu-id="49ac8-110">Teams requirements</span></span>

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality-in-teams"></a><span data-ttu-id="49ac8-111">Настройка политик для отключения функций звонков и собраний в Teams</span><span class="sxs-lookup"><span data-stu-id="49ac8-111">Set policies to turn off calling and meeting functionality in Teams</span></span>

<span data-ttu-id="49ac8-112">Звонки и собрания в Teams не оптимизированы для работы в среде VDI (скоро).</span><span class="sxs-lookup"><span data-stu-id="49ac8-112">The Teams calling and meeting experience isn't optimized for a VDI environment (coming soon).</span></span> <span data-ttu-id="49ac8-113">Мы рекомендуем настроить политики на уровне пользователей для отключения функций звонков и собраний в Teams.</span><span class="sxs-lookup"><span data-stu-id="49ac8-113">We recommend you set user-level policies to turn off calling and meeting functionality in Teams.</span></span>

<span data-ttu-id="49ac8-114">Вы по-прежнему можете запускать команды полностью в VDI с помощью классического приложения Teams или веб-приложения.</span><span class="sxs-lookup"><span data-stu-id="49ac8-114">You can still choose to run Teams fully in VDI using either the Teams desktop app or web app.</span></span> <span data-ttu-id="49ac8-115">Тем не менее, мы рекомендуем настроить политики, чтобы не порушить безопасность взаимодействия с пользователем.</span><span class="sxs-lookup"><span data-stu-id="49ac8-115">However, we recommend that you set the policies to avoid compromising the user experience.</span></span>  

<span data-ttu-id="49ac8-116">Для распространения изменений политики может потребоваться некоторое время (несколько часов).</span><span class="sxs-lookup"><span data-stu-id="49ac8-116">It can take some time (a few hours) for the policy changes to propagate.</span></span> <span data-ttu-id="49ac8-117">Если вы сразу же не видите изменения для указанной учетной записи, повторите попытку через несколько часов.</span><span class="sxs-lookup"><span data-stu-id="49ac8-117">If you don’t see changes for a given account immediately, try again in a few hours.</span></span>

> [!NOTE]
> <span data-ttu-id="49ac8-118">Если в средах виртуальных рабочих столов оптимизируются вызовы и собрания групп, вы можете отменить эти политики и разрешить пользователям использовать группы в обычном режиме.</span><span class="sxs-lookup"><span data-stu-id="49ac8-118">When Teams calling and meetings are optimized for use in virtual desktop environments, you can revert these policies and allow users to use Teams as they normally would.</span></span> 

#### <a name="calling"></a><span data-ttu-id="49ac8-119">Звонки</span><span class="sxs-lookup"><span data-stu-id="49ac8-119">Calling</span></span>

<span data-ttu-id="49ac8-120">Используйте командлеты **кстеамскаллингполици** , чтобы указать, разрешено ли пользователям использовать параметры звонков и звонков в частных и групповых чатах.</span><span class="sxs-lookup"><span data-stu-id="49ac8-120">Use the **CSTeamsCallingPolicy** cmdlets to control whether users are allowed to use calling and calling options in private and group chats.</span></span> <span data-ttu-id="49ac8-121">Ниже приведен список параметров политики и рекомендуемых значений.</span><span class="sxs-lookup"><span data-stu-id="49ac8-121">Here's the list of policy settings and recommended values.</span></span>

|<span data-ttu-id="49ac8-122">Название политики</span><span class="sxs-lookup"><span data-stu-id="49ac8-122">Policy name</span></span>  |<span data-ttu-id="49ac8-123">Описание</span><span class="sxs-lookup"><span data-stu-id="49ac8-123">Description</span></span> |<span data-ttu-id="49ac8-124">Рекомендуемое значение</span><span class="sxs-lookup"><span data-stu-id="49ac8-124">Recommended value</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="49ac8-125">алловкаллинг</span><span class="sxs-lookup"><span data-stu-id="49ac8-125">AllowCalling</span></span>    |<span data-ttu-id="49ac8-126">Управляет возможностями вызова взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="49ac8-126">Controls interop calling capabilities.</span></span> <span data-ttu-id="49ac8-127">Если включить этот параметр, пользователи Skype для бизнеса смогут звонить на один из нескольких пользователей Teams и наоборот.</span><span class="sxs-lookup"><span data-stu-id="49ac8-127">Turning this on allows Skype for Business users to have one-on-one calls with Teams users and vice versa.</span></span>         |<span data-ttu-id="49ac8-128">Установите значение false, чтобы не допустить звонка для пользователей Skype для бизнеса, предназначенных для Teams.</span><span class="sxs-lookup"><span data-stu-id="49ac8-128">Set to False to prevent calls from Skype for Business users landing in Teams.</span></span>          |
|<span data-ttu-id="49ac8-129">алловприватекаллинг</span><span class="sxs-lookup"><span data-stu-id="49ac8-129">AllowPrivateCalling</span></span>     | <span data-ttu-id="49ac8-130">Определяет, будет ли вызывающее приложение доступно на панели приложения в левой части клиента Teams, и должны ли пользователи видеть параметры вызова и видеозвонка в частном чате.</span><span class="sxs-lookup"><span data-stu-id="49ac8-130">Controls whether the Calling app is available in the app bar on the left side of the Teams client and whether users see Calling and Video call options in private chat</span></span>         |<span data-ttu-id="49ac8-131">Установите значение false, чтобы удалить вызывающее приложение из панели приложения в левой части Teams и удалить параметры вызова и видеозвонка в частном чате.</span><span class="sxs-lookup"><span data-stu-id="49ac8-131">Set to False to remove the Calling app from the app bar on the left side of Teams and to remove the Calling and Video call options in private chat.</span></span>          |

#### <a name="create-and-assign-a-calling-policy"></a><span data-ttu-id="49ac8-132">Создание и назначение политики вызова</span><span class="sxs-lookup"><span data-stu-id="49ac8-132">Create and assign a calling policy</span></span>

1. <span data-ttu-id="49ac8-133">Запустите сеанс Windows PowerShell с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="49ac8-133">Start a Windows PowerShell session as an administrator.</span></span>
2. <span data-ttu-id="49ac8-134">Подключитесь к разъему Skype Online.</span><span class="sxs-lookup"><span data-stu-id="49ac8-134">Connect to the Skype Online Connector.</span></span>

        # Set Office 365 User Name and Password
        $username = “admin email address”
        password = ConvertTo-SecureString "password" -AsPlainText -Force
        $LiveCred = new-object -typename System.Management.Automation.PSCredential -argumentlist $username, $password
        # Connect to Skype Online
        Import-Module SkypeOnlineConnector
        $sfboSession = New-CsOnlineSession -Credential $LiveCred
        Import-PSSession $sfboSession```

3. <span data-ttu-id="49ac8-135">Просмотр списка параметров политики звонков.</span><span class="sxs-lookup"><span data-stu-id="49ac8-135">View a list of calling policy options.</span></span>

       Get-CsTeamsCallingPolicy
 
4. <span data-ttu-id="49ac8-136">Найдите параметр встроенной политики, в котором отключены все политики звонков.</span><span class="sxs-lookup"><span data-stu-id="49ac8-136">Look for the built-in policy option where all calling policies are disabled.</span></span> <span data-ttu-id="49ac8-137">Оно выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="49ac8-137">It looks like this.</span></span>
   
        Identity                        : Tag:DisallowCalling
        AllowCalling                    : False
        AllowPrivateCalling             : False
        AllowVoicemail                  : False
        AllowCallGroups                 : False
        AllowDelegation                 : False
        AllowUserControl                : False
        AllowCallForwardingToUser       : False
        AllowCallForwardingToPhone      : False
        PreventTollBypass               : False

5. <span data-ttu-id="49ac8-138">Примените встроенный параметр Дисалловкаллинг ко всем пользователям, которые будут использовать команды в виртуализованной среде.</span><span class="sxs-lookup"><span data-stu-id="49ac8-138">Apply the DisallowCalling built-in policy option to all users who will be using Teams in a virtualized environment.</span></span>

        Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity “user email id”

<span data-ttu-id="49ac8-139">Дополнительные сведения о политиках вызова команд: [Set-кстеамскаллингполици](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy).</span><span class="sxs-lookup"><span data-stu-id="49ac8-139">For more information about Teams calling policies, see [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy).</span></span>

#### <a name="meetings"></a><span data-ttu-id="49ac8-140">Собрания</span><span class="sxs-lookup"><span data-stu-id="49ac8-140">Meetings</span></span>

<span data-ttu-id="49ac8-141">С помощью командлетов **кстеамсмитингполици** можно управлять типами собраний, которые могут быть созданы пользователями, а также функциями собраний, доступными для анонимных и внешних пользователей.</span><span class="sxs-lookup"><span data-stu-id="49ac8-141">Use the **CsTeamsMeetingPolicy** cmdlets to control the type of meetings that users can create, the features that they can access while in a meeting, and the meeting features that are available to anonymous and external users.</span></span> <span data-ttu-id="49ac8-142">Ниже приведен список параметров политики и рекомендуемых значений.</span><span class="sxs-lookup"><span data-stu-id="49ac8-142">Here's the list of policy settings and recommended values.</span></span>

|<span data-ttu-id="49ac8-143">Имя политики</span><span class="sxs-lookup"><span data-stu-id="49ac8-143">Policy Name</span></span> |<span data-ttu-id="49ac8-144">Описание</span><span class="sxs-lookup"><span data-stu-id="49ac8-144">Description</span></span>|<span data-ttu-id="49ac8-145">Рекомендуемое значение</span><span class="sxs-lookup"><span data-stu-id="49ac8-145">Recommended Value</span></span>                   |
|-------------------|-----------------|-----------------------|
|<span data-ttu-id="49ac8-146">алловприватемитингсчедулинг</span><span class="sxs-lookup"><span data-stu-id="49ac8-146">AllowPrivateMeetingScheduling</span></span>  | <span data-ttu-id="49ac8-147">Определяет, может ли пользователь планировать закрытые собрания.</span><span class="sxs-lookup"><span data-stu-id="49ac8-147">Determines whether a user is allowed to schedule private meetings.</span></span>| <span data-ttu-id="49ac8-148">Установите значение false, чтобы запретить пользователю планировать закрытые собрания.</span><span class="sxs-lookup"><span data-stu-id="49ac8-148">Set to False to prohibit the user from being able to schedule private meetings.</span></span>  |
|<span data-ttu-id="49ac8-149">алловчаннелмитингсчедулинг</span><span class="sxs-lookup"><span data-stu-id="49ac8-149">AllowChannelMeetingScheduling</span></span>  | <span data-ttu-id="49ac8-150">Определяет, разрешено ли пользователю планировать собрания каналов.</span><span class="sxs-lookup"><span data-stu-id="49ac8-150">Determines whether a user is allowed to schedule channel meetings.</span></span> | <span data-ttu-id="49ac8-151">Установите значение false, чтобы запретить пользователю планировать собрания каналов.</span><span class="sxs-lookup"><span data-stu-id="49ac8-151">Set to False to prohibit the user from being able to schedule channel meetings.</span></span>                       |
|<span data-ttu-id="49ac8-152">алловмитнов</span><span class="sxs-lookup"><span data-stu-id="49ac8-152">AllowMeetNow</span></span> |<span data-ttu-id="49ac8-153">Определяет, может ли пользователь создавать или запускать специальные собрания.</span><span class="sxs-lookup"><span data-stu-id="49ac8-153">Determines whether a user is allowed to create or start ad-hoc meetings.</span></span>              |  <span data-ttu-id="49ac8-154">Задайте для него значение false, чтобы запретить пользователю выполнять одноранговые собрания.</span><span class="sxs-lookup"><span data-stu-id="49ac8-154">Set this to False to prohibit the user from being able to start ad-hoc meetings.</span></span>                     |
|<span data-ttu-id="49ac8-155">скриншарингмоде</span><span class="sxs-lookup"><span data-stu-id="49ac8-155">ScreenSharingMode</span></span> | <span data-ttu-id="49ac8-156">Определяет режим, в котором пользователь может демонстрировать экран в звонках или собраниях.</span><span class="sxs-lookup"><span data-stu-id="49ac8-156">Determines the mode in which a user is allowed to share their screen in calls or meetings.</span></span> | <span data-ttu-id="49ac8-157">Значение "отключено", чтобы запретить пользователю предоставлять общий доступ к экранам</span><span class="sxs-lookup"><span data-stu-id="49ac8-157">Set to Disabled to prohibit the user from sharing their screens</span></span>                          |
|<span data-ttu-id="49ac8-158">AllowIPVideo</span><span class="sxs-lookup"><span data-stu-id="49ac8-158">AllowIPVideo</span></span> |<span data-ttu-id="49ac8-159">Определяет, включено ли видео в собраниях или звонках пользователя.</span><span class="sxs-lookup"><span data-stu-id="49ac8-159">Determines whether video is enabled in a user's meetings or calls.</span></span>                  |    <span data-ttu-id="49ac8-160">Установите значение false, чтобы запретить пользователю предоставлять общий доступ к видео</span><span class="sxs-lookup"><span data-stu-id="49ac8-160">Set to False to prohibit the user from sharing their video</span></span>                                         |
| <span data-ttu-id="49ac8-161">AllowAnonymousUsersToDialOut</span><span class="sxs-lookup"><span data-stu-id="49ac8-161">AllowAnonymousUsersToDialOut</span></span> | <span data-ttu-id="49ac8-162">Определяет, разрешено ли анонимным пользователям звонить на номера PSTN.</span><span class="sxs-lookup"><span data-stu-id="49ac8-162">Determines whether anonymous users are allowed to dial out to a PSTN number.</span></span> | <span data-ttu-id="49ac8-163">Установите значение false, чтобы запретить исходящие вызовы анонимных пользователей</span><span class="sxs-lookup"><span data-stu-id="49ac8-163">Set to False to prohibit anonymous users from dialing out</span></span>                                  |
| <span data-ttu-id="49ac8-164">аллованонимаусусерстостартмитинг</span><span class="sxs-lookup"><span data-stu-id="49ac8-164">AllowAnonymousUsersToStartMeeting</span></span> | <span data-ttu-id="49ac8-165">Определяет, могут ли анонимные пользователи начать собрание.</span><span class="sxs-lookup"><span data-stu-id="49ac8-165">Determines whether anonymous users can start a meeting.</span></span>     |  <span data-ttu-id="49ac8-166">Установите значение false, чтобы запретить пользователям начинать собрание</span><span class="sxs-lookup"><span data-stu-id="49ac8-166">Set to False to prohibit users from starting a meeting</span></span>                                            |
| <span data-ttu-id="49ac8-167">алловаутлукаддин</span><span class="sxs-lookup"><span data-stu-id="49ac8-167">AllowOutlookAddIn</span></span> |<span data-ttu-id="49ac8-168">Определяет, может ли пользователь планировать собрания Teams в классическом клиенте Outlook.</span><span class="sxs-lookup"><span data-stu-id="49ac8-168">Determines whether a user can schedule Teams meetings in the Outlook desktop client.</span></span>| <span data-ttu-id="49ac8-169">Установите значение false, чтобы запретить пользователю планировать собрания Teams в классическом клиенте Outlook.</span><span class="sxs-lookup"><span data-stu-id="49ac8-169">Set to False to prohibit a user from  scheduling Teams meetings in the Outlook desktop client</span></span>|
| <span data-ttu-id="49ac8-170">алловпартиЦипантгиверекуестконтрол</span><span class="sxs-lookup"><span data-stu-id="49ac8-170">AllowParticipantGiveRequestControl</span></span>|<span data-ttu-id="49ac8-171">Определяет, могут ли участники запрашивать или предоставлять управление демонстрацией экрана.</span><span class="sxs-lookup"><span data-stu-id="49ac8-171">Determines whether participants can request or give control of screen sharing.</span></span>| <span data-ttu-id="49ac8-172">Установите значение false, чтобы запретить пользователю предоставлять или запрашивать управление на собрании.</span><span class="sxs-lookup"><span data-stu-id="49ac8-172">Set to False to prohibit the user from giving and requesting control in a meeting</span></span>    |
| <span data-ttu-id="49ac8-173">алловекстерналпартиЦипантгиверекуестконтрол</span><span class="sxs-lookup"><span data-stu-id="49ac8-173">AllowExternalParticipantGiveRequestControl</span></span> | <span data-ttu-id="49ac8-174">Определяет, могут ли внешние участники запрашивать или предоставлять управление демонстрацией экрана.</span><span class="sxs-lookup"><span data-stu-id="49ac8-174">Determines whether external participants can request or give control of screen sharing.</span></span>| <span data-ttu-id="49ac8-175">Установите значение false, чтобы запретить внешнему пользователю предоставлять управление на собрании.</span><span class="sxs-lookup"><span data-stu-id="49ac8-175">Set to False to prohibit an external user from giving, requesting control in a meeting</span></span>|
|<span data-ttu-id="49ac8-176">алловповерпоинтшаринг</span><span class="sxs-lookup"><span data-stu-id="49ac8-176">AllowPowerPointSharing</span></span>|<span data-ttu-id="49ac8-177">Определяет, разрешено ли совместное использование PowerPoint в собраниях пользователя.</span><span class="sxs-lookup"><span data-stu-id="49ac8-177">Determines whether PowerPoint sharing is allowed in a user’s meetings.</span></span> |<span data-ttu-id="49ac8-178">Установите значение false, чтобы запретить пользователям предоставлять общий доступ к файлам PowerPoint на собрании.</span><span class="sxs-lookup"><span data-stu-id="49ac8-178">Set to False to prohibit a user from sharing PowerPoint files in a meeting</span></span>  |
|<span data-ttu-id="49ac8-179">алловвхитебоард</span><span class="sxs-lookup"><span data-stu-id="49ac8-179">AllowWhiteboard</span></span> | <span data-ttu-id="49ac8-180">Определяет, разрешена ли доска в собраниях пользователя.</span><span class="sxs-lookup"><span data-stu-id="49ac8-180">Determines whether whiteboard is allowed in a user’s meetings.</span></span> |   <span data-ttu-id="49ac8-181">Установите значение false, чтобы запретить доску на собрании</span><span class="sxs-lookup"><span data-stu-id="49ac8-181">Set to False to prohibit whiteboard in a meeting</span></span> |
| <span data-ttu-id="49ac8-182">алловтранскриптион</span><span class="sxs-lookup"><span data-stu-id="49ac8-182">AllowTranscription</span></span> |<span data-ttu-id="49ac8-183">Определяет, разрешены ли в собраниях пользователя и (или), и в режиме реального времени заголовки и записи для собраний.</span><span class="sxs-lookup"><span data-stu-id="49ac8-183">Determines whether real-time and/or post-meeting captions and transcriptions are allowed in a user's meetings.</span></span>|    <span data-ttu-id="49ac8-184">Установите значение false, чтобы запретить использование транскрипции и субтитров на собрании.</span><span class="sxs-lookup"><span data-stu-id="49ac8-184">Set to False to prohibit transcription  and captions in a meeting</span></span>  |  
| <span data-ttu-id="49ac8-185">AllowSharedNotes</span><span class="sxs-lookup"><span data-stu-id="49ac8-185">AllowSharedNotes</span></span> | <span data-ttu-id="49ac8-186">Определяет, разрешено ли пользователям делать общие заметки.</span><span class="sxs-lookup"><span data-stu-id="49ac8-186">Determines whether users are allowed to take shared notes.</span></span> | <span data-ttu-id="49ac8-187">Установите значение false, чтобы запретить пользователям делать общие заметки.</span><span class="sxs-lookup"><span data-stu-id="49ac8-187">Set to False to prohibit users from taking shared notes</span></span> |
|<span data-ttu-id="49ac8-188">медиабитратекб</span><span class="sxs-lookup"><span data-stu-id="49ac8-188">MediaBitRateKB</span></span> |<span data-ttu-id="49ac8-189">Определяет скорость потока мультимедиа для обмена аудио-и видеофайлами и приложениями в собраниях.</span><span class="sxs-lookup"><span data-stu-id="49ac8-189">Determines the media bit rate for audio/video/app sharing transmissions in meetings</span></span>  | <span data-ttu-id="49ac8-190">Рекомендуемое значение — 5000 (5 МБ).</span><span class="sxs-lookup"><span data-stu-id="49ac8-190">Suggested value is 5000 (5 MB).</span></span> <span data-ttu-id="49ac8-191">Вы можете изменить его в соответствии с потребностями Организации.</span><span class="sxs-lookup"><span data-stu-id="49ac8-191">You can change it based on your organization’s needs.</span></span>| 

#### <a name="create-and-assign-a-meeting-policy"></a><span data-ttu-id="49ac8-192">Создание и назначение политики собраний</span><span class="sxs-lookup"><span data-stu-id="49ac8-192">Create and assign a meeting policy</span></span>

1. <span data-ttu-id="49ac8-193">Запустите сеанс Windows PowerShell с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="49ac8-193">Start a Windows PowerShell session as an administrator.</span></span>
2. <span data-ttu-id="49ac8-194">Подключитесь к разъему Skype Online.</span><span class="sxs-lookup"><span data-stu-id="49ac8-194">Connect to the Skype Online Connector.</span></span>

        # Set Office 365 User Name and Password
        $username = “admin email address”
        password = ConvertTo-SecureString "password" -AsPlainText -Force
        $LiveCred = new-object -typename System.Management.Automation.PSCredential -argumentlist $username, $password
        # Connect to Skype Online
        Import-Module SkypeOnlineConnector
        $sfboSession = New-CsOnlineSession -Credential $LiveCred
        Import-PSSession $sfboSession```

3. <span data-ttu-id="49ac8-195">Просмотр списка параметров политики собраний.</span><span class="sxs-lookup"><span data-stu-id="49ac8-195">View a list of meeting policy options.</span></span>

       Get-CsTeamsMeetingPolicy
 
4. <span data-ttu-id="49ac8-196">Найдите параметр встроенной политики, в котором отключены все политики собраний.</span><span class="sxs-lookup"><span data-stu-id="49ac8-196">Look for the built-in policy option where all meeting policies are disabled.</span></span> <span data-ttu-id="49ac8-197">Оно выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="49ac8-197">It looks like this.</span></span>
   
        Identity                                    : Tag:AllOff
        Description                                 :
        AllowChannelMeetingScheduling               : False
        AllowMeetNow                                : False
        AllowIPVideo                                : False
        AllowAnonymousUsersToDialOut                : False
        AllowAnonymousUsersToStartMeeting           : False
        AllowPrivateMeetingScheduling               : False
        AutoAdmittedUsers                           : False
        AllowCloudRecording                         : False
        AllowOutlookAddIn                           : False
        AllowPowerPointSharing                      : False
        AllowParticipantGiveRequestControl          : False
        AllowExternalParticipantGiveRequestControl  : False
        AllowSharedNotes                            : False
        AllowWhiteboard                             : False
        AllowTranscription                          : False
        MediaBitRateKb                              : False
        ScreenSharingMode                           : False

5. <span data-ttu-id="49ac8-198">Примените встроенный параметр Аллофф ко всем пользователям, которые будут использовать команды в виртуализованной среде.</span><span class="sxs-lookup"><span data-stu-id="49ac8-198">Apply the AllOff built-in policy option to all users who will be using Teams in a virtualized environment.</span></span> 

        Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity “user email id”

 <span data-ttu-id="49ac8-199">Дополнительные сведения о политиках собраний Teams можно найти в разделе [Set-кстеамсмитингполици](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy).</span><span class="sxs-lookup"><span data-stu-id="49ac8-199">For more information about Teams meeting policies, see [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy).</span></span>

### <a name="virtualization-provider-requirements"></a><span data-ttu-id="49ac8-200">Требования поставщика виртуализации</span><span class="sxs-lookup"><span data-stu-id="49ac8-200">Virtualization provider requirements</span></span>

<span data-ttu-id="49ac8-201">Приложение Teams было проверено ведущими поставщиками решений для виртуализации.</span><span class="sxs-lookup"><span data-stu-id="49ac8-201">The Teams app has been validated on leading virtualization solution providers.</span></span> <span data-ttu-id="49ac8-202">В случае с несколькими поставщиками рынка ознакомьтесь с поставщиком решений для виртуализации, чтобы убедиться в соблюдении минимальных требований.</span><span class="sxs-lookup"><span data-stu-id="49ac8-202">With multiple market providers, consult your virtualization solution provider to ensure minimum requirements are met.</span></span>

### <a name="virtual-machine-requirements"></a><span data-ttu-id="49ac8-203">Требования к виртуальной машине</span><span class="sxs-lookup"><span data-stu-id="49ac8-203">Virtual Machine requirements</span></span>

<span data-ttu-id="49ac8-204">В виртуализованной среде для разнообразных задач и потребностей пользователей ниже приведена минимальная рекомендуемая конфигурация виртуальной машины.</span><span class="sxs-lookup"><span data-stu-id="49ac8-204">With the diverse workloads and user needs in a virtualized environment, the following is the minimum recommended VM configuration.</span></span>

|<span data-ttu-id="49ac8-205">Параметр</span><span class="sxs-lookup"><span data-stu-id="49ac8-205">Parameter</span></span>  |<span data-ttu-id="49ac8-206">Измерений</span><span class="sxs-lookup"><span data-stu-id="49ac8-206">Measure</span></span>  |
|---------|---------|
|<span data-ttu-id="49ac8-207">вкпу</span><span class="sxs-lookup"><span data-stu-id="49ac8-207">vCPU</span></span>    |  <span data-ttu-id="49ac8-208">2 ядра</span><span class="sxs-lookup"><span data-stu-id="49ac8-208">2 cores</span></span>       |
|<span data-ttu-id="49ac8-209">ДОСТУПНОЙ</span><span class="sxs-lookup"><span data-stu-id="49ac8-209">RAM</span></span>     |  <span data-ttu-id="49ac8-210">4 ГБ</span><span class="sxs-lookup"><span data-stu-id="49ac8-210">4 GB</span></span>      |
|<span data-ttu-id="49ac8-211">Склад</span><span class="sxs-lookup"><span data-stu-id="49ac8-211">Storage</span></span>     | <span data-ttu-id="49ac8-212">8 ГБ</span><span class="sxs-lookup"><span data-stu-id="49ac8-212">8 GB</span></span>       |

### <a name="virtual-machine-operating-system-requirements"></a><span data-ttu-id="49ac8-213">Требования к операционной системе виртуальной машины</span><span class="sxs-lookup"><span data-stu-id="49ac8-213">Virtual Machine operating system requirements</span></span>

<span data-ttu-id="49ac8-214">Ниже перечислены поддерживаемые операционные системы для виртуальных машин.</span><span class="sxs-lookup"><span data-stu-id="49ac8-214">The supported operating systems for VM are:</span></span>

- <span data-ttu-id="49ac8-215">Windows 10 и более поздние версии</span><span class="sxs-lookup"><span data-stu-id="49ac8-215">Windows 10 and later</span></span>
- <span data-ttu-id="49ac8-216">Windows Server 2012 R2 и более поздние версии</span><span class="sxs-lookup"><span data-stu-id="49ac8-216">Windows Server 2012 R2 and later</span></span>

## <a name="install-teams-on-vdi"></a><span data-ttu-id="49ac8-217">Установка Teams в VDI</span><span class="sxs-lookup"><span data-stu-id="49ac8-217">Install Teams on VDI</span></span>

<span data-ttu-id="49ac8-218">Вот процесс и инструменты для развертывания классического приложения Teams.</span><span class="sxs-lookup"><span data-stu-id="49ac8-218">Here's the process and tools to deploy the Teams desktop app.</span></span> 

1. <span data-ttu-id="49ac8-219">Скачайте пакет MSI Teams с помощью одной из приведенных ниже ссылок в зависимости от среды.</span><span class="sxs-lookup"><span data-stu-id="49ac8-219">Download the Teams MSI package using one of the following links depending on the environment.</span></span> <span data-ttu-id="49ac8-220">Рекомендуем использовать 64-разрядную версию для виртуальной машины VDI с 64-разрядной операционной системой.</span><span class="sxs-lookup"><span data-stu-id="49ac8-220">We recommend the 64-bit version for a VDI VM with a 64-bit operating system.</span></span>

    - [<span data-ttu-id="49ac8-221">32-разрядная версия</span><span class="sxs-lookup"><span data-stu-id="49ac8-221">32-bit version</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true)
    - [<span data-ttu-id="49ac8-222">64-разрядная версия</span><span class="sxs-lookup"><span data-stu-id="49ac8-222">64-bit version</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true&arch=x64)

2. <span data-ttu-id="49ac8-223">Выполните следующую команду, чтобы установить MSI на виртуальную машину VDI (или завершить ее обновление).</span><span class="sxs-lookup"><span data-stu-id="49ac8-223">Run the following command to install the MSI to the VDI VM (or complete updating it).</span></span>

        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1

    <span data-ttu-id="49ac8-224">Эти команды устанавливаются в файлы программы.</span><span class="sxs-lookup"><span data-stu-id="49ac8-224">This installs Teams to Program Files.</span></span> <span data-ttu-id="49ac8-225">На этом этапе Настройка первоначальных изображений завершена.</span><span class="sxs-lookup"><span data-stu-id="49ac8-225">At this point, the golden image setup is complete.</span></span>
 
    <span data-ttu-id="49ac8-226">Следующий интерактивный сеанс входа запускает Teams и запрашивает учетные данные.</span><span class="sxs-lookup"><span data-stu-id="49ac8-226">The next interactive logon session starts Teams and asks for credentials.</span></span> <span data-ttu-id="49ac8-227">Обратите внимание, что при установке Teams в VDI невозможно отключить автоматическое запуск Teams с помощью свойства АЛЛУСЕР.</span><span class="sxs-lookup"><span data-stu-id="49ac8-227">Note that it's not possible to disable auto-launch of Teams when installing Teams on VDI using the ALLUSER property.</span></span> 

3. <span data-ttu-id="49ac8-228">Выполните следующую команду, чтобы удалить MSI из виртуальной машины VDI (или подготовиться к его обновлению).</span><span class="sxs-lookup"><span data-stu-id="49ac8-228">Run the following command to uninstall the MSI from the VDI VM (or prepare for updating it).</span></span>

        msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>

    <span data-ttu-id="49ac8-229">Это действие удаляет группы из файлов программы.</span><span class="sxs-lookup"><span data-stu-id="49ac8-229">This uninstalls Teams from Program Files.</span></span>

## <a name="known-issues-and-limitations"></a><span data-ttu-id="49ac8-230">Известные проблемы и ограничения</span><span class="sxs-lookup"><span data-stu-id="49ac8-230">Known issues and limitations</span></span>

<span data-ttu-id="49ac8-231">Ниже описаны известные проблемы и ограничения для Teams в VDI.</span><span class="sxs-lookup"><span data-stu-id="49ac8-231">The following are known issues and limitations for Teams on VDI.</span></span>

- <span data-ttu-id="49ac8-232">**Развертывание типа узла общего сеанса**: развертывание общих типов узлов сеансов (например, Общая несохраняемая Конфигурация виртуальной машины) не находится в области.</span><span class="sxs-lookup"><span data-stu-id="49ac8-232">**Shared session host type deployments**: Shared session host type deployments (for example, shared non-persistent VM configuration) aren't in scope.</span></span>
- <span data-ttu-id="49ac8-233">**Звонки и собрания**:</span><span class="sxs-lookup"><span data-stu-id="49ac8-233">**Calling and meetings**:</span></span>

    - <span data-ttu-id="49ac8-234">Сценарии звонков и собраний не оптимизированы для VDI.</span><span class="sxs-lookup"><span data-stu-id="49ac8-234">Calling and meeting scenarios aren't optimized for VDI.</span></span> <span data-ttu-id="49ac8-235">Эти сценарии будут работать плохо.</span><span class="sxs-lookup"><span data-stu-id="49ac8-235">These scenarios will perform poorly.</span></span> <span data-ttu-id="49ac8-236">Мы рекомендуем использовать политики на уровне пользователей, как описано в разделе [Настройка политик для отключения функций звонков и собраний в](#set-policies-to-turn-off-calling-and-meeting-functionality-in-teams) раздел Teams.</span><span class="sxs-lookup"><span data-stu-id="49ac8-236">We recommend using user-level policies as described in the [Set policies to turn off calling and meeting functionality in Teams](#set-policies-to-turn-off-calling-and-meeting-functionality-in-teams) section.</span></span>  
    - <span data-ttu-id="49ac8-237">Применение описанных в этой статье политик влияет на возможность звонков и собраний, в зависимости от других политик, может повлиять на других пользователей организации.</span><span class="sxs-lookup"><span data-stu-id="49ac8-237">Applying the policies described in this article impacts the ability to use calling and meeting functionality, which depending on other policies, may affect other users in your organization.</span></span> <span data-ttu-id="49ac8-238">Если пользователи в вашей организации используют клиенты, не использующие VDI, вы можете выбрать вариант не применять эти политики.</span><span class="sxs-lookup"><span data-stu-id="49ac8-238">If users in your organization use non-VDI clients, you can choose to not apply the policies.</span></span>  

- <span data-ttu-id="49ac8-239">**Присоединение к звонкам и собраниям, созданным другими пользователями**: Несмотря на то, что политики ограничивают пользователей для создания собраний, они могут присоединяться к собраниям, если они будут звонить другим пользователям из собрания.</span><span class="sxs-lookup"><span data-stu-id="49ac8-239">**Joining calls and meetings created by other users**: Although the policies restrict users from creating meetings, they can still join meetings if another user dials out to them from the meeting.</span></span> <span data-ttu-id="49ac8-240">В этих собраниях пользователь может поделиться видео, использовать доску и другие возможности, зависят от того, были ли отключены эти функции с помощью Теамсмитингполици.</span><span class="sxs-lookup"><span data-stu-id="49ac8-240">In these meetings, the user's ability to share video, use whiteboard and other features depend on whether you disabled those features using TeamsMeetingPolicy.</span></span>  
- <span data-ttu-id="49ac8-241">**Кэшированное содержимое**: Если виртуальная среда, в которой работает Teams, не является постоянной (и данные очищаются по окончании каждого пользовательского сеанса), пользователи могут заметить снижение производительности из-за обновления содержимого независимо от того, есть ли у пользователя тот же самый доступ. содержимое в предыдущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="49ac8-241">**Cached content**: If the virtual environment in which Teams is running isn't persistent (and data is cleaned up at the end of each user session), users may notice performance degradation due to content refresh, regardless of whether the user accessed the same content in a previous session.</span></span>
- <span data-ttu-id="49ac8-242">**Обновления клиента**: teams в VDI автоматически не обновляется при установке MSI для компьютера.</span><span class="sxs-lookup"><span data-stu-id="49ac8-242">**Client updates**: Teams on VDI isn't automatically updated with per-machine MSI installation.</span></span> <span data-ttu-id="49ac8-243">Вы должны обновить образ виртуальной машины установкой нового MSI-файла, как описано в разделе [Установка Teams в VDI](#install-teams-on-vdi) .</span><span class="sxs-lookup"><span data-stu-id="49ac8-243">You have to update the VM image by installing a new MSI as described in the [Install Teams on VDI](#install-teams-on-vdi) section.</span></span> <span data-ttu-id="49ac8-244">Вы должны удалить текущую версию, чтобы обновить ее до новой версии.</span><span class="sxs-lookup"><span data-stu-id="49ac8-244">You must uninstall the current version to update to a newer version.</span></span>
- <span data-ttu-id="49ac8-245">**Взаимодействие с пользователем**: взаимодействие с пользователями Teams в среде VDI может отличаться от среды, отличной от VDI.</span><span class="sxs-lookup"><span data-stu-id="49ac8-245">**User experience**: The Teams user experience in a VDI environment may be different from a non-VDI environment.</span></span> <span data-ttu-id="49ac8-246">Это может быть вызвано параметрами политики и/или поддержкой функций в среде.</span><span class="sxs-lookup"><span data-stu-id="49ac8-246">The differences may be because of policy settings and/or feature support in the environment.</span></span>

<span data-ttu-id="49ac8-247">Известные проблемы, которые не относятся к VDI, приведены в разделе [Известные проблемы в Microsoft Teams](Known-issues.md).</span><span class="sxs-lookup"><span data-stu-id="49ac8-247">For Teams known issues that aren't related to VDI, see [Known issues for Microsoft Teams](Known-issues.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="49ac8-248">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="49ac8-248">Related topics</span></span>

- [<span data-ttu-id="49ac8-249">Установка Microsoft Teams с помощью MSI</span><span class="sxs-lookup"><span data-stu-id="49ac8-249">Install Microsoft Teams using MSI</span></span>](msi-deployment.md)
