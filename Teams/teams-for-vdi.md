---
title: Teams для инфраструктуры виртуальных рабочих столов
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 04/10/2019
ms.topic: article
ms.service: msteams
ms.reviewer: ''
description: Узнайте, как для запуска групп Майкрософт в среде виртуализации инфраструктуры рабочих столов (VDI).
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c351e0cefc5e4de4ff74a175af4dee064bf96f3f
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32223426"
---
# <a name="teams-for-virtualized-desktop-infrastructure"></a><span data-ttu-id="c347b-103">Teams для инфраструктуры виртуальных рабочих столов</span><span class="sxs-lookup"><span data-stu-id="c347b-103">Teams for Virtualized Desktop Infrastructure</span></span>

<span data-ttu-id="c347b-104">В этой статье описаны требования и ограничения при использовании групп Майкрософт в виртуализованной среде.</span><span class="sxs-lookup"><span data-stu-id="c347b-104">This article describes the requirements and limitations for using Microsoft Teams in a virtualized environment.</span></span>

## <a name="what-is-vdi"></a><span data-ttu-id="c347b-105">Что такое инфраструктуры виртуальных рабочих СТОЛОВ?</span><span class="sxs-lookup"><span data-stu-id="c347b-105">What is VDI?</span></span>

<span data-ttu-id="c347b-106">Инфраструктуры виртуальных рабочих столов (VDI) — это технология виртуализации, на котором размещается операционная система и приложения на сервере централизованного в центре обработки данных.</span><span class="sxs-lookup"><span data-stu-id="c347b-106">Virtual Desktop Infrastructure (VDI) is virtualization technology that hosts a desktop operating system and applications on a centralized server in a data center.</span></span> <span data-ttu-id="c347b-107">Это позволяет полностью индивидуально настроенных настольных компьютерах пользователям, имеющим полностью с защитой и ее соответствие требованиям централизованного источника.</span><span class="sxs-lookup"><span data-stu-id="c347b-107">This enables a fully personalized desktop experience to users with a fully secured and compliant centralized source.</span></span> 
 
<span data-ttu-id="c347b-108">На данный момент группы в виртуализованной среде доступна с поддержкой функциональные возможности совместной работы и общаться с выделенной сохраняемого виртуальной машине (виртуальной Машины).</span><span class="sxs-lookup"><span data-stu-id="c347b-108">Currently, Teams in a virtualized environment is available with support for collaboration and chat functionality with a dedicated persistent virtualized machine (VM).</span></span> <span data-ttu-id="c347b-109">Чтобы обеспечить оптимальную пользовательского интерфейса, следуйте указаниям в этой статье.</span><span class="sxs-lookup"><span data-stu-id="c347b-109">To ensure an optimal user experience, follow the guidance in this article.</span></span> 

## <a name="teams-requirements"></a><span data-ttu-id="c347b-110">Требования к группам</span><span class="sxs-lookup"><span data-stu-id="c347b-110">Teams requirements</span></span>

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality-in-teams"></a><span data-ttu-id="c347b-111">Настраивать политики для отключения вызов и функциональности в группах собраний</span><span class="sxs-lookup"><span data-stu-id="c347b-111">Set policies to turn off calling and meeting functionality in Teams</span></span>

<span data-ttu-id="c347b-112">Команды вызова и собрания качества не оптимизирована, в среде VDI (ожидается в ближайшее время).</span><span class="sxs-lookup"><span data-stu-id="c347b-112">The Teams calling and meeting experience isn't optimized for a VDI environment (coming soon).</span></span> <span data-ttu-id="c347b-113">Мы рекомендуем установить политики уровня пользователя, отключение вызова и функциональности в группах собраний.</span><span class="sxs-lookup"><span data-stu-id="c347b-113">We recommend you set user-level policies to turn off calling and meeting functionality in Teams.</span></span>

<span data-ttu-id="c347b-114">По-прежнему можно полностью запуск команд в инфраструктуры виртуальных рабочих СТОЛОВ с помощью классического приложения группы или веб-приложения.</span><span class="sxs-lookup"><span data-stu-id="c347b-114">You can still choose to run Teams fully in VDI using either the Teams desktop app or web app.</span></span> <span data-ttu-id="c347b-115">Тем не менее рекомендуется задавать политики, чтобы избежать риска удобство работы пользователей.</span><span class="sxs-lookup"><span data-stu-id="c347b-115">However, we recommend that you set the policies to avoid compromising the user experience.</span></span>  

<span data-ttu-id="c347b-116">Для изменения политики для распространения может потребоваться некоторое время (несколько часов).</span><span class="sxs-lookup"><span data-stu-id="c347b-116">It can take some time (a few hours) for the policy changes to propagate.</span></span> <span data-ttu-id="c347b-117">Если изменения для указанной учетной записи не отображается немедленно, попробуйте еще раз в несколько часов.</span><span class="sxs-lookup"><span data-stu-id="c347b-117">If you don’t see changes for a given account immediately, try again in a few hours.</span></span>

> [!NOTE]
> <span data-ttu-id="c347b-118">При группы вызова и собраний, оптимизированных для использования в виртуальных средах с рабочего стола, можно восстановить эти политики и разрешить пользователям использовать команды, как они обычно.</span><span class="sxs-lookup"><span data-stu-id="c347b-118">When Teams calling and meetings are optimized for use in virtual desktop environments, you can revert these policies and allow users to use Teams as they normally would.</span></span> 

#### <a name="calling"></a><span data-ttu-id="c347b-119">Звонки</span><span class="sxs-lookup"><span data-stu-id="c347b-119">Calling</span></span>

<span data-ttu-id="c347b-120">Будет ли пользователям разрешено использовать вызов и телефонные номера в конфиденциальном режиме и группы обсуждений с помощью командлетов **CSTeamsCallingPolicy** для элемента управления.</span><span class="sxs-lookup"><span data-stu-id="c347b-120">Use the **CSTeamsCallingPolicy** cmdlets to control whether users are allowed to use calling and calling options in private and group chats.</span></span> <span data-ttu-id="c347b-121">Ниже приведен список параметров политики и рекомендуемые значения.</span><span class="sxs-lookup"><span data-stu-id="c347b-121">Here's the list of policy settings and recommended values.</span></span>

|<span data-ttu-id="c347b-122">Название политики</span><span class="sxs-lookup"><span data-stu-id="c347b-122">Policy name</span></span>  |<span data-ttu-id="c347b-123">Описание</span><span class="sxs-lookup"><span data-stu-id="c347b-123">Description</span></span> |<span data-ttu-id="c347b-124">Рекомендуемое значение</span><span class="sxs-lookup"><span data-stu-id="c347b-124">Recommended value</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="c347b-125">AllowCalling</span><span class="sxs-lookup"><span data-stu-id="c347b-125">AllowCalling</span></span>    |<span data-ttu-id="c347b-126">Вызов возможности взаимодействия элементов управления.</span><span class="sxs-lookup"><span data-stu-id="c347b-126">Controls interop calling capabilities.</span></span> <span data-ttu-id="c347b-127">Это включен, Скайп для бизнес-пользователям имеют индивидуального вызовы с пользователями, группами и наоборот.</span><span class="sxs-lookup"><span data-stu-id="c347b-127">Turning this on allows Skype for Business users to have one-on-one calls with Teams users and vice versa.</span></span>         |<span data-ttu-id="c347b-128">Установите значение False, чтобы вызовы от Скайп для бизнес-пользователи Главная в группах.</span><span class="sxs-lookup"><span data-stu-id="c347b-128">Set to False to prevent calls from Skype for Business users landing in Teams.</span></span>          |
|<span data-ttu-id="c347b-129">AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="c347b-129">AllowPrivateCalling</span></span>     | <span data-ttu-id="c347b-130">Определяет, доступна ли вызов приложения в панели приложения в левой части клиента, групп и ли пользователи видеть вызова и вызовите параметры в частной беседы видео</span><span class="sxs-lookup"><span data-stu-id="c347b-130">Controls whether the Calling app is available in the app bar on the left side of the Teams client and whether users see Calling and Video call options in private chat</span></span>         |<span data-ttu-id="c347b-131">Чтобы удалить вызов приложения из панель приложения в левой части группы и для удаления возможности телефонной и видеосвязи звонков в частной беседы установлено значение False.</span><span class="sxs-lookup"><span data-stu-id="c347b-131">Set to False to remove the Calling app from the app bar on the left side of Teams and to remove the Calling and Video call options in private chat.</span></span>          |

#### <a name="create-and-assign-a-calling-policy"></a><span data-ttu-id="c347b-132">Создайте и назначьте политику вызывающего</span><span class="sxs-lookup"><span data-stu-id="c347b-132">Create and assign a calling policy</span></span>

1. <span data-ttu-id="c347b-133">Начало сеанса Windows PowerShell с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="c347b-133">Start a Windows PowerShell session as an administrator.</span></span>
2. <span data-ttu-id="c347b-134">Подключение к сети соединителя Скайп.</span><span class="sxs-lookup"><span data-stu-id="c347b-134">Connect to the Skype Online Connector.</span></span>

        # Set Office 365 User Name and Password
        $username = “admin email address”
        password = ConvertTo-SecureString "password" -AsPlainText -Force
        $LiveCred = new-object -typename System.Management.Automation.PSCredential -argumentlist $username, $password
        # Connect to Skype Online
        Import-Module SkypeOnlineConnector
        $sfboSession = New-CsOnlineSession -Credential $LiveCred
        Import-PSSession $sfboSession```

3. <span data-ttu-id="c347b-135">Просмотр списка доступных телефонных номеров политики.</span><span class="sxs-lookup"><span data-stu-id="c347b-135">View a list of calling policy options.</span></span>

       Get-CsTeamsCallingPolicy
 
4. <span data-ttu-id="c347b-136">Найдите параметр встроенной политики где отключаются все политики вызова.</span><span class="sxs-lookup"><span data-stu-id="c347b-136">Look for the built-in policy option where all calling policies are disabled.</span></span> <span data-ttu-id="c347b-137">Он выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="c347b-137">It looks like this.</span></span>
   
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

5. <span data-ttu-id="c347b-138">Примените параметр DisallowCalling встроенной политики для всех пользователей, которые будут работать с группами в виртуализованной среде.</span><span class="sxs-lookup"><span data-stu-id="c347b-138">Apply the DisallowCalling built-in policy option to all users who will be using Teams in a virtualized environment.</span></span>

        Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity “user email id”

<span data-ttu-id="c347b-139">Дополнительные сведения о группах вызов политик можно [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy).</span><span class="sxs-lookup"><span data-stu-id="c347b-139">For more information about Teams calling policies, see [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy).</span></span>

#### <a name="meetings"></a><span data-ttu-id="c347b-140">Собрания</span><span class="sxs-lookup"><span data-stu-id="c347b-140">Meetings</span></span>

<span data-ttu-id="c347b-141">Использование командлетов **CsTeamsMeetingPolicy** для управления типом собрания, которые пользователи могут создавать, функции, которые они имеют доступ во время собрания и функциональные возможности собраний, доступные для анонимных и внешними пользователями.</span><span class="sxs-lookup"><span data-stu-id="c347b-141">Use the **CsTeamsMeetingPolicy** cmdlets to control the type of meetings that users can create, the features that they can access while in a meeting, and the meeting features that are available to anonymous and external users.</span></span> <span data-ttu-id="c347b-142">Ниже приведен список параметров политики и рекомендуемые значения.</span><span class="sxs-lookup"><span data-stu-id="c347b-142">Here's the list of policy settings and recommended values.</span></span>

|<span data-ttu-id="c347b-143">Имя политики</span><span class="sxs-lookup"><span data-stu-id="c347b-143">Policy Name</span></span> |<span data-ttu-id="c347b-144">Описание</span><span class="sxs-lookup"><span data-stu-id="c347b-144">Description</span></span>|<span data-ttu-id="c347b-145">Рекомендуемое значение</span><span class="sxs-lookup"><span data-stu-id="c347b-145">Recommended Value</span></span>                   |
|-------------------|-----------------|-----------------------|
|<span data-ttu-id="c347b-146">AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="c347b-146">AllowPrivateMeetingScheduling</span></span>  | <span data-ttu-id="c347b-147">Определяет, разрешено ли пользователь для планирования личных встреч.</span><span class="sxs-lookup"><span data-stu-id="c347b-147">Determines whether a user is allowed to schedule private meetings.</span></span>| <span data-ttu-id="c347b-148">Установлено значение False, чтобы запретить пользователям возможность планировать собрания закрытый.</span><span class="sxs-lookup"><span data-stu-id="c347b-148">Set to False to prohibit the user from being able to schedule private meetings.</span></span>  |
|<span data-ttu-id="c347b-149">AllowChannelMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="c347b-149">AllowChannelMeetingScheduling</span></span>  | <span data-ttu-id="c347b-150">Определяет, разрешено ли пользователь для планирования собраний канала.</span><span class="sxs-lookup"><span data-stu-id="c347b-150">Determines whether a user is allowed to schedule channel meetings.</span></span> | <span data-ttu-id="c347b-151">Установлено значение False, чтобы запретить пользователям возможность планировать собрания канала.</span><span class="sxs-lookup"><span data-stu-id="c347b-151">Set to False to prohibit the user from being able to schedule channel meetings.</span></span>                       |
|<span data-ttu-id="c347b-152">AllowMeetNow</span><span class="sxs-lookup"><span data-stu-id="c347b-152">AllowMeetNow</span></span> |<span data-ttu-id="c347b-153">Определяет, разрешено ли пользователь для создания или запуска незапланированных собраний.</span><span class="sxs-lookup"><span data-stu-id="c347b-153">Determines whether a user is allowed to create or start ad-hoc meetings.</span></span>              |  <span data-ttu-id="c347b-154">Установите значение False, чтобы запретить пользователь не сможет начать незапланированных собраний.</span><span class="sxs-lookup"><span data-stu-id="c347b-154">Set this to False to prohibit the user from being able to start ad-hoc meetings.</span></span>                     |
|<span data-ttu-id="c347b-155">ScreenSharingMode</span><span class="sxs-lookup"><span data-stu-id="c347b-155">ScreenSharingMode</span></span> | <span data-ttu-id="c347b-156">Определяет режим, в котором пользователь может совместно использовать экран в звонков или собрания.</span><span class="sxs-lookup"><span data-stu-id="c347b-156">Determines the mode in which a user is allowed to share their screen in calls or meetings.</span></span> | <span data-ttu-id="c347b-157">Присвоено значение "отключено" запретить пользователям общий доступ к своим экранов</span><span class="sxs-lookup"><span data-stu-id="c347b-157">Set to Disabled to prohibit the user from sharing their screens</span></span>                          |
|<span data-ttu-id="c347b-158">AllowIPVideo</span><span class="sxs-lookup"><span data-stu-id="c347b-158">AllowIPVideo</span></span> |<span data-ttu-id="c347b-159">Определяет, включена ли видео в звонки и встречи пользователя.</span><span class="sxs-lookup"><span data-stu-id="c347b-159">Determines whether video is enabled in a user's meetings or calls.</span></span>                  |    <span data-ttu-id="c347b-160">Задано значение False, чтобы запретить общий доступ к своим видео пользователя</span><span class="sxs-lookup"><span data-stu-id="c347b-160">Set to False to prohibit the user from sharing their video</span></span>                                         |
| <span data-ttu-id="c347b-161">AllowAnonymousUsersToDialOut</span><span class="sxs-lookup"><span data-stu-id="c347b-161">AllowAnonymousUsersToDialOut</span></span> | <span data-ttu-id="c347b-162">Определяет, разрешены ли анонимные пользователи для исходящих звонков ТСОП номер.</span><span class="sxs-lookup"><span data-stu-id="c347b-162">Determines whether anonymous users are allowed to dial out to a PSTN number.</span></span> | <span data-ttu-id="c347b-163">Задано значение False, чтобы запретить анонимным пользователям выходному набору.</span><span class="sxs-lookup"><span data-stu-id="c347b-163">Set to False to prohibit anonymous users from dialing out</span></span>                                  |
| <span data-ttu-id="c347b-164">AllowAnonymousUsersToStartMeeting</span><span class="sxs-lookup"><span data-stu-id="c347b-164">AllowAnonymousUsersToStartMeeting</span></span> | <span data-ttu-id="c347b-165">Определяет, будет ли анонимные пользователи могут начать собрание.</span><span class="sxs-lookup"><span data-stu-id="c347b-165">Determines whether anonymous users can start a meeting.</span></span>     |  <span data-ttu-id="c347b-166">Задано значение False, чтобы запретить пользователям начать собрание</span><span class="sxs-lookup"><span data-stu-id="c347b-166">Set to False to prohibit users from starting a meeting</span></span>                                            |
| <span data-ttu-id="c347b-167">AllowOutlookAddIn</span><span class="sxs-lookup"><span data-stu-id="c347b-167">AllowOutlookAddIn</span></span> |<span data-ttu-id="c347b-168">Определяет, может ли пользователь планировать собрания групп в клиентском Outlook.</span><span class="sxs-lookup"><span data-stu-id="c347b-168">Determines whether a user can schedule Teams meetings in the Outlook desktop client.</span></span>| <span data-ttu-id="c347b-169">Задано значение False, чтобы запретить пользователям планирования собраний группы в клиентском Outlook</span><span class="sxs-lookup"><span data-stu-id="c347b-169">Set to False to prohibit a user from  scheduling Teams meetings in the Outlook desktop client</span></span>|
| <span data-ttu-id="c347b-170">AllowParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="c347b-170">AllowParticipantGiveRequestControl</span></span>|<span data-ttu-id="c347b-171">Определяет участников можно запросить или предоставить управление совместное использование рабочего стола.</span><span class="sxs-lookup"><span data-stu-id="c347b-171">Determines whether participants can request or give control of screen sharing.</span></span>| <span data-ttu-id="c347b-172">Задано значение False, чтобы запретить пользователям давая и запрашивает управление в ходе собрания</span><span class="sxs-lookup"><span data-stu-id="c347b-172">Set to False to prohibit the user from giving and requesting control in a meeting</span></span>    |
| <span data-ttu-id="c347b-173">AllowExternalParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="c347b-173">AllowExternalParticipantGiveRequestControl</span></span> | <span data-ttu-id="c347b-174">Определяет, можно запросить или передать управление совместного использования экрана внешним участникам.</span><span class="sxs-lookup"><span data-stu-id="c347b-174">Determines whether external participants can request or give control of screen sharing.</span></span>| <span data-ttu-id="c347b-175">Значение False для запретить давая, внешний пользователь запрашивает управление в ходе собрания</span><span class="sxs-lookup"><span data-stu-id="c347b-175">Set to False to prohibit an external user from giving, requesting control in a meeting</span></span>|
|<span data-ttu-id="c347b-176">AllowPowerPointSharing</span><span class="sxs-lookup"><span data-stu-id="c347b-176">AllowPowerPointSharing</span></span>|<span data-ttu-id="c347b-177">Определяет, разрешено ли общий доступ к PowerPoint в собраниях пользователя.</span><span class="sxs-lookup"><span data-stu-id="c347b-177">Determines whether PowerPoint sharing is allowed in a user’s meetings.</span></span> |<span data-ttu-id="c347b-178">Задано значение False, чтобы запретить совместное использование файлов PowerPoint на собрании пользователя</span><span class="sxs-lookup"><span data-stu-id="c347b-178">Set to False to prohibit a user from sharing PowerPoint files in a meeting</span></span>  |
|<span data-ttu-id="c347b-179">AllowWhiteboard</span><span class="sxs-lookup"><span data-stu-id="c347b-179">AllowWhiteboard</span></span> | <span data-ttu-id="c347b-180">Определяет, разрешено ли доски в собраниях пользователя.</span><span class="sxs-lookup"><span data-stu-id="c347b-180">Determines whether whiteboard is allowed in a user’s meetings.</span></span> |   <span data-ttu-id="c347b-181">Задано значение False, чтобы запретить использование доски на собрании</span><span class="sxs-lookup"><span data-stu-id="c347b-181">Set to False to prohibit whiteboard in a meeting</span></span> |
| <span data-ttu-id="c347b-182">AllowTranscription</span><span class="sxs-lookup"><span data-stu-id="c347b-182">AllowTranscription</span></span> |<span data-ttu-id="c347b-183">Определяет заголовки в режиме реального времени и/или после собрания и транскрипциями, разрешены ли в собраниях пользователя.</span><span class="sxs-lookup"><span data-stu-id="c347b-183">Determines whether real-time and/or post-meeting captions and transcriptions are allowed in a user's meetings.</span></span>|    <span data-ttu-id="c347b-184">Задано значение False, чтобы запретить транскрибирования и их подписей в ходе собрания</span><span class="sxs-lookup"><span data-stu-id="c347b-184">Set to False to prohibit transcription  and captions in a meeting</span></span>  |  
| <span data-ttu-id="c347b-185">AllowSharedNotes</span><span class="sxs-lookup"><span data-stu-id="c347b-185">AllowSharedNotes</span></span> | <span data-ttu-id="c347b-186">Определяет, разрешено ли пользователям для общих заметок.</span><span class="sxs-lookup"><span data-stu-id="c347b-186">Determines whether users are allowed to take shared notes.</span></span> | <span data-ttu-id="c347b-187">Задано значение False, чтобы запретить пользователям общих заметок</span><span class="sxs-lookup"><span data-stu-id="c347b-187">Set to False to prohibit users from taking shared notes</span></span> |
|<span data-ttu-id="c347b-188">MediaBitRateKB</span><span class="sxs-lookup"><span data-stu-id="c347b-188">MediaBitRateKB</span></span> |<span data-ttu-id="c347b-189">Определяет скорость потока мультимедиа для аудио/видео/приложения общего доступа к передач в собраниях</span><span class="sxs-lookup"><span data-stu-id="c347b-189">Determines the media bit rate for audio/video/app sharing transmissions in meetings</span></span>  | <span data-ttu-id="c347b-190">Предлагаемое значение — 5000 (5 МБ).</span><span class="sxs-lookup"><span data-stu-id="c347b-190">Suggested value is 5000 (5 MB).</span></span> <span data-ttu-id="c347b-191">Можно изменить его в соответствии с потребностями вашей организации.</span><span class="sxs-lookup"><span data-stu-id="c347b-191">You can change it based on your organization’s needs.</span></span>| 

#### <a name="create-and-assign-a-meeting-policy"></a><span data-ttu-id="c347b-192">Создайте и назначьте политику собрания</span><span class="sxs-lookup"><span data-stu-id="c347b-192">Create and assign a meeting policy</span></span>

1. <span data-ttu-id="c347b-193">Начало сеанса Windows PowerShell с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="c347b-193">Start a Windows PowerShell session as an administrator.</span></span>
2. <span data-ttu-id="c347b-194">Подключение к сети соединителя Скайп.</span><span class="sxs-lookup"><span data-stu-id="c347b-194">Connect to the Skype Online Connector.</span></span>

        # Set Office 365 User Name and Password
        $username = “admin email address”
        password = ConvertTo-SecureString "password" -AsPlainText -Force
        $LiveCred = new-object -typename System.Management.Automation.PSCredential -argumentlist $username, $password
        # Connect to Skype Online
        Import-Module SkypeOnlineConnector
        $sfboSession = New-CsOnlineSession -Credential $LiveCred
        Import-PSSession $sfboSession```

3. <span data-ttu-id="c347b-195">Просмотр списка приглашений на собрания параметры политики.</span><span class="sxs-lookup"><span data-stu-id="c347b-195">View a list of meeting policy options.</span></span>

       Get-CsTeamsMeetingPolicy
 
4. <span data-ttu-id="c347b-196">Найдите параметр встроенной политики где отключаются все политики собрания.</span><span class="sxs-lookup"><span data-stu-id="c347b-196">Look for the built-in policy option where all meeting policies are disabled.</span></span> <span data-ttu-id="c347b-197">Он выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="c347b-197">It looks like this.</span></span>
   
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

5. <span data-ttu-id="c347b-198">Примените параметр AllOff встроенной политики для всех пользователей, которые будут работать с группами в виртуализованной среде.</span><span class="sxs-lookup"><span data-stu-id="c347b-198">Apply the AllOff built-in policy option to all users who will be using Teams in a virtualized environment.</span></span> 

        Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity “user email id”

 <span data-ttu-id="c347b-199">Дополнительные сведения о политиках собрания команды [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy)см.</span><span class="sxs-lookup"><span data-stu-id="c347b-199">For more information about Teams meeting policies, see [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy).</span></span>

### <a name="virtualization-provider-requirements"></a><span data-ttu-id="c347b-200">Требования к виртуализации поставщика</span><span class="sxs-lookup"><span data-stu-id="c347b-200">Virtualization provider requirements</span></span>

<span data-ttu-id="c347b-201">Приложение группы проверки на ведущие поставщики решений виртуализации.</span><span class="sxs-lookup"><span data-stu-id="c347b-201">The Teams app has been validated on leading virtualization solution providers.</span></span> <span data-ttu-id="c347b-202">С несколькими поставщиками рынка обратитесь к поставщика решений виртуализации, чтобы убедиться, что выполняются минимальные требования.</span><span class="sxs-lookup"><span data-stu-id="c347b-202">With multiple market providers, consult your virtualization solution provider to ensure minimum requirements are met.</span></span>

### <a name="virtual-machine-requirements"></a><span data-ttu-id="c347b-203">Требования к виртуальной машине</span><span class="sxs-lookup"><span data-stu-id="c347b-203">Virtual Machine requirements</span></span>

<span data-ttu-id="c347b-204">С помощью различных рабочих нагрузок и пользовательских задач в виртуализованной среде ниже приведен по меньшей мере Рекомендуемая конфигурация виртуальной Машины.</span><span class="sxs-lookup"><span data-stu-id="c347b-204">With the diverse workloads and user needs in a virtualized environment, the following is the minimum recommended VM configuration.</span></span>

|<span data-ttu-id="c347b-205">Параметр</span><span class="sxs-lookup"><span data-stu-id="c347b-205">Parameter</span></span>  |<span data-ttu-id="c347b-206">Измерения</span><span class="sxs-lookup"><span data-stu-id="c347b-206">Measure</span></span>  |
|---------|---------|
|<span data-ttu-id="c347b-207">vCPU</span><span class="sxs-lookup"><span data-stu-id="c347b-207">vCPU</span></span>    |  <span data-ttu-id="c347b-208">2 ядра</span><span class="sxs-lookup"><span data-stu-id="c347b-208">2 cores</span></span>       |
|<span data-ttu-id="c347b-209">ОЗУ</span><span class="sxs-lookup"><span data-stu-id="c347b-209">RAM</span></span>     |  <span data-ttu-id="c347b-210">4 ГБ</span><span class="sxs-lookup"><span data-stu-id="c347b-210">4 GB</span></span>      |
|<span data-ttu-id="c347b-211">Хранилище</span><span class="sxs-lookup"><span data-stu-id="c347b-211">Storage</span></span>     | <span data-ttu-id="c347b-212">8 ГБ</span><span class="sxs-lookup"><span data-stu-id="c347b-212">8 GB</span></span>       |

### <a name="virtual-machine-operating-system-requirements"></a><span data-ttu-id="c347b-213">Требования к операционной системе виртуальной машины</span><span class="sxs-lookup"><span data-stu-id="c347b-213">Virtual Machine operating system requirements</span></span>

<span data-ttu-id="c347b-214">Поддерживаемые операционные системы для виртуальной Машины являются:</span><span class="sxs-lookup"><span data-stu-id="c347b-214">The supported operating systems for VM are:</span></span>

- <span data-ttu-id="c347b-215">Windows 10 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="c347b-215">Windows 10 and later</span></span>
- <span data-ttu-id="c347b-216">Windows Server 2012 R2 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="c347b-216">Windows Server 2012 R2 and later</span></span>

## <a name="install-teams-on-vdi"></a><span data-ttu-id="c347b-217">Установка группы на инфраструктуры виртуальных рабочих СТОЛОВ</span><span class="sxs-lookup"><span data-stu-id="c347b-217">Install Teams on VDI</span></span>

<span data-ttu-id="c347b-218">Ниже приведен процесс и средства для развертывания классического приложения группы.</span><span class="sxs-lookup"><span data-stu-id="c347b-218">Here's the process and tools to deploy the Teams desktop app.</span></span> 

1. <span data-ttu-id="c347b-219">Загрузите пакет MSI группами, с помощью одного из следующих ссылок в зависимости от среды.</span><span class="sxs-lookup"><span data-stu-id="c347b-219">Download the Teams MSI package using one of the following links depending on the environment.</span></span> <span data-ttu-id="c347b-220">Мы рекомендуем 64-разрядная версия для виртуальной Машины инфраструктуры виртуальных рабочих СТОЛОВ с 64-разрядной операционной системы.</span><span class="sxs-lookup"><span data-stu-id="c347b-220">We recommend the 64-bit version for a VDI VM with a 64-bit operating system.</span></span>

    - [<span data-ttu-id="c347b-221">32-разрядная версия</span><span class="sxs-lookup"><span data-stu-id="c347b-221">32-bit version</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true)
    - [<span data-ttu-id="c347b-222">64-разрядная версия</span><span class="sxs-lookup"><span data-stu-id="c347b-222">64-bit version</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true&arch=x64)

2. <span data-ttu-id="c347b-223">Выполните следующую команду для установки MSI-файла для виртуальной Машины инфраструктуры виртуальных рабочих СТОЛОВ (или выполнить его обновление).</span><span class="sxs-lookup"><span data-stu-id="c347b-223">Run the following command to install the MSI to the VDI VM (or complete updating it).</span></span>

        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1

    <span data-ttu-id="c347b-224">Это устанавливает группами Program Files.</span><span class="sxs-lookup"><span data-stu-id="c347b-224">This installs Teams to Program Files.</span></span> <span data-ttu-id="c347b-225">На этом этапе Настройка эталонные изображения завершена.</span><span class="sxs-lookup"><span data-stu-id="c347b-225">At this point, the golden image setup is complete.</span></span>
 
    <span data-ttu-id="c347b-226">Следующего интерактивного входа в систему начинается групп и запрашивает учетные данные.</span><span class="sxs-lookup"><span data-stu-id="c347b-226">The next interactive logon session starts Teams and asks for credentials.</span></span> <span data-ttu-id="c347b-227">Обратите внимание на то, что не можно отключить автоматический запуск команд при установке групп с помощью свойства ALLUSER инфраструктуры виртуальных рабочих СТОЛОВ.</span><span class="sxs-lookup"><span data-stu-id="c347b-227">Note that it's not possible to disable auto-launch of Teams when installing Teams on VDI using the ALLUSER property.</span></span> 

3. <span data-ttu-id="c347b-228">Выполните следующую команду, чтобы удалить MSI-файла из виртуальной Машины инфраструктуры виртуальных рабочих СТОЛОВ (или подготовки к их обновление).</span><span class="sxs-lookup"><span data-stu-id="c347b-228">Run the following command to uninstall the MSI from the VDI VM (or prepare for updating it).</span></span>

        msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>

    <span data-ttu-id="c347b-229">Это удаление групп из Program Files.</span><span class="sxs-lookup"><span data-stu-id="c347b-229">This uninstalls Teams from Program Files.</span></span>

## <a name="known-issues-and-limitations"></a><span data-ttu-id="c347b-230">Известные проблемы и ограничения</span><span class="sxs-lookup"><span data-stu-id="c347b-230">Known issues and limitations</span></span>

<span data-ttu-id="c347b-231">Далее представлены известные проблемы и ограничения для групп на инфраструктуры виртуальных рабочих СТОЛОВ.</span><span class="sxs-lookup"><span data-stu-id="c347b-231">The following are known issues and limitations for Teams on VDI.</span></span>

- <span data-ttu-id="c347b-232">**Развертываний тип узла сеанса Shared**: Shared сеанса узла тип развертывания (например, общих непостоянные виртуальной Машины конфигурация) не входят в область.</span><span class="sxs-lookup"><span data-stu-id="c347b-232">**Shared session host type deployments**: Shared session host type deployments (for example, shared non-persistent VM configuration) aren't in scope.</span></span>
- <span data-ttu-id="c347b-233">**Звонков и собраний**:</span><span class="sxs-lookup"><span data-stu-id="c347b-233">**Calling and meetings**:</span></span>

    - <span data-ttu-id="c347b-234">Звонков и собраний сценарии не оптимизирован для инфраструктуры виртуальных рабочих СТОЛОВ.</span><span class="sxs-lookup"><span data-stu-id="c347b-234">Calling and meeting scenarios aren't optimized for VDI.</span></span> <span data-ttu-id="c347b-235">Эти сценарии будут выполнять неудачно.</span><span class="sxs-lookup"><span data-stu-id="c347b-235">These scenarios will perform poorly.</span></span> <span data-ttu-id="c347b-236">Рекомендуется использовать политики уровня пользователя, как описано в разделе [Настройка политики для отключения вызова и функциональности в группах собраний](#set-policies-to-turn-off-calling-and-meeting-functionality-in-teams) .</span><span class="sxs-lookup"><span data-stu-id="c347b-236">We recommend using user-level policies as described in the [Set policies to turn off calling and meeting functionality in Teams](#set-policies-to-turn-off-calling-and-meeting-functionality-in-teams) section.</span></span>  
    - <span data-ttu-id="c347b-237">Применение политики, описанные в этой статье влияет на возможность использования функции вызова и собрание, которые в зависимости от других политик может повлиять на других пользователей в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="c347b-237">Applying the policies described in this article impacts the ability to use calling and meeting functionality, which depending on other policies, may affect other users in your organization.</span></span> <span data-ttu-id="c347b-238">Если пользователи в вашей организации используют клиенты не инфраструктуры виртуальных рабочих СТОЛОВ, вы можете не политиками.</span><span class="sxs-lookup"><span data-stu-id="c347b-238">If users in your organization use non-VDI clients, you can choose to not apply the policies.</span></span>  

- <span data-ttu-id="c347b-239">**Объединение звонков и собраний, созданные другими пользователями**: несмотря на то, что политики Запретить пользователям Создание собраний, они могут по-прежнему присоединяться к собраниям Если другой пользователь набирает номер им из собрания.</span><span class="sxs-lookup"><span data-stu-id="c347b-239">**Joining calls and meetings created by other users**: Although the policies restrict users from creating meetings, they can still join meetings if another user dials out to them from the meeting.</span></span> <span data-ttu-id="c347b-240">В этих собраний, возможность совместного использования видео, использовать доску и другие функции зависят от ли вы отключили этих компонентов с помощью TeamsMeetingPolicy.</span><span class="sxs-lookup"><span data-stu-id="c347b-240">In these meetings, the user's ability to share video, use whiteboard and other features depend on whether you disabled those features using TeamsMeetingPolicy.</span></span>  
- <span data-ttu-id="c347b-241">**Содержимое кэширования**: Если виртуальной среды в команды, которые running не сохраняемого (и очистки данных в конце каждого сеанса пользователя), пользователи могут заметить снижение производительности из-за обновление контента, независимо от того, является ли пользователь получить доступ к таким же содержимое в предыдущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="c347b-241">**Cached content**: If the virtual environment in which Teams is running isn't persistent (and data is cleaned up at the end of each user session), users may notice performance degradation due to content refresh, regardless of whether the user accessed the same content in a previous session.</span></span>
- <span data-ttu-id="c347b-242">**Обновления клиента**: команды на инфраструктуры виртуальных рабочих СТОЛОВ не будет автоматически обновлен аналогично функции клиентов, не являющиеся инфраструктуры виртуальных рабочих СТОЛОВ группы.</span><span class="sxs-lookup"><span data-stu-id="c347b-242">**Client updates**: Teams on VDI isn't automatically updated like the way that non-VDI Teams clients are.</span></span>  <span data-ttu-id="c347b-243">Необходимо обновить образ виртуальной Машины путем установки нового MSI, как описано в разделе [Установка группы на инфраструктуры виртуальных рабочих СТОЛОВ](#install-teams-on-vdi) .</span><span class="sxs-lookup"><span data-stu-id="c347b-243">You have to update the VM image by installing a new MSI as described in the [Install Teams on VDI](#install-teams-on-vdi) section.</span></span> <span data-ttu-id="c347b-244">Необходимо удалить текущую версию, чтобы обновление до новой версии.</span><span class="sxs-lookup"><span data-stu-id="c347b-244">You must uninstall the current version to update to a newer version.</span></span>
- <span data-ttu-id="c347b-245">**Взаимодействие с пользователем**: взаимодействие с пользователем групп в среде VDI может отличаться от в среде без инфраструктуры виртуальных рабочих СТОЛОВ.</span><span class="sxs-lookup"><span data-stu-id="c347b-245">**User experience**: The Teams user experience in a VDI environment may be different from a non-VDI environment.</span></span> <span data-ttu-id="c347b-246">Различия может быть из-за параметров политики и функции поддержки в среде.</span><span class="sxs-lookup"><span data-stu-id="c347b-246">The differences may be because of policy settings and/or feature support in the environment.</span></span>

<span data-ttu-id="c347b-247">Известные проблемы, которые не относятся к VDI командами в разделе [Известные проблемы, связанные с группами Майкрософт](Known-issues.md).</span><span class="sxs-lookup"><span data-stu-id="c347b-247">For Teams known issues that aren't related to VDI, see [Known issues for Microsoft Teams](Known-issues.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="c347b-248">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="c347b-248">Related topics</span></span>

- [<span data-ttu-id="c347b-249">Установка группами Майкрософт, с помощью MSI</span><span class="sxs-lookup"><span data-stu-id="c347b-249">Install Microsoft Teams using MSI</span></span>](msi-deployment.md)