---
title: Управление политиками собраний для участников и гостей
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: sonua, shalenc
audience: admin
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingpolicies.participantandguests
- seo-marvel-apr2020
description: Узнайте, как управлять настройками политики собраний в Teams для участников и гостей.
ms.openlocfilehash: 51d121ab9c537e6ba304045e47b6e875cd98afd6
ms.sourcegitcommit: 2d725b9925696e61e3e7338f890f086e009c28f2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/06/2021
ms.locfileid: "51598755"
---
# <a name="meeting-policy-settings---participants--guests"></a><span data-ttu-id="c64db-103">Параметры политики собраний: участники могут & гостей</span><span class="sxs-lookup"><span data-stu-id="c64db-103">Meeting policy settings - Participants & guests</span></span>

<span data-ttu-id="c64db-104"><a name="bkmeetingparticipants"> </a></span><span class="sxs-lookup"><span data-stu-id="c64db-104"><a name="bkmeetingparticipants"> </a></span></span>

<span data-ttu-id="c64db-105">Эти параметры контролируют, какие участники собрания должны ждать в "вестибюле", прежде чем их допустят к собранию, и уровень участия в нем.</span><span class="sxs-lookup"><span data-stu-id="c64db-105">These settings control which meeting participants wait in the lobby before they are admitted to the meeting and the level of participation they are allowed in a meeting.</span></span>

- [<span data-ttu-id="c64db-106">Позволить анонимным пользователям начинать собрание</span><span class="sxs-lookup"><span data-stu-id="c64db-106">Let anonymous people start a meeting</span></span>](#let-anonymous-people-start-a-meeting)
- [<span data-ttu-id="c64db-107">Автоматически допустить людей</span><span class="sxs-lookup"><span data-stu-id="c64db-107">Automatically admit people</span></span>](#automatically-admit-people)
- [<span data-ttu-id="c64db-108">Разрешить пользователям телефонного дозвона минуть "вести".</span><span class="sxs-lookup"><span data-stu-id="c64db-108">Allow dial-in users to bypass the lobby</span></span>](#allow-dial-in-users-to-bypass-the-lobby)
- [<span data-ttu-id="c64db-109">Включить субтитры в прямом эфире</span><span class="sxs-lookup"><span data-stu-id="c64db-109">Enable live captions</span></span>](#enable-live-captions)
- [<span data-ttu-id="c64db-110">Разрешение чата на собраниях</span><span class="sxs-lookup"><span data-stu-id="c64db-110">Allow chat in meetings</span></span>](#allow-chat-in-meetings)

> [!NOTE]
><span data-ttu-id="c64db-111">Параметры присоединиться к собранию зависят от настроек для каждой группы Teams и способа подключения.</span><span class="sxs-lookup"><span data-stu-id="c64db-111">Options to join a meeting will vary, depending on the settings for each Teams group, and the connection method.</span></span> <span data-ttu-id="c64db-112">Если в вашей группе есть аудиоконференция и она используется для подключения, см. [эту видеоконференцию.](https://docs.microsoft.com/microsoftteams/audio-conferencing-in-office-365)</span><span class="sxs-lookup"><span data-stu-id="c64db-112">If your group has audio conferencing, and uses it to connect, see [Audio Conferencing](https://docs.microsoft.com/microsoftteams/audio-conferencing-in-office-365).</span></span> <span data-ttu-id="c64db-113">Если в вашей группе Teams нет аудиоконференции, обратитесь к команде ["Присоединиться к собранию в Teams".](https://support.office.com/article/join-a-meeting-in-teams-1613bb53-f3fa-431e-85a9-d6a91e3468c9)</span><span class="sxs-lookup"><span data-stu-id="c64db-113">If your Teams group doesn't have audio conferencing, refer to [Join a meeting in Teams](https://support.office.com/article/join-a-meeting-in-teams-1613bb53-f3fa-431e-85a9-d6a91e3468c9).</span></span>

## <a name="let-anonymous-people-start-a-meeting"></a><span data-ttu-id="c64db-114">Позволить анонимным пользователям начинать собрание</span><span class="sxs-lookup"><span data-stu-id="c64db-114">Let anonymous people start a meeting</span></span>

<span data-ttu-id="c64db-115">Этот параметр является политикой на каждого организатора, которая позволяет использовать собрания с бездережным телефонным и видеоконференцией.</span><span class="sxs-lookup"><span data-stu-id="c64db-115">This setting is a per-organizer policy that allows for leaderless dial-in conferencing meetings.</span></span> <span data-ttu-id="c64db-116">Этот параметр управляет возможностью присоединиться к собранию пользователям с телефонным доступом без участия пользователя, который проходит проверку подлинности из организации.</span><span class="sxs-lookup"><span data-stu-id="c64db-116">This setting controls whether dial-in users can join the meeting without an authenticated user from the organization in attendance.</span></span> <span data-ttu-id="c64db-117">По умолчанию этот параметр отключен, то есть пользователи, которые будут присоединяться к собранию по телефонной связи, будут ждать в "ожидании" до тех пор, пока к собранию не присоединится авторификация пользователя из организации.</span><span class="sxs-lookup"><span data-stu-id="c64db-117">By default, this setting is turned off, which means dial-in users will wait in the lobby until an authenticated user from the organization joins the meeting.</span></span>

> [!NOTE]
> <span data-ttu-id="c64db-118">Если этот параметр отключен и пользователь, присоединяюсь к собранию сначала с помощью телефонного номера, а затем помещается в ""вести", пользователь организации должен присоединиться к собранию с помощью клиента Teams, чтобы допустить пользователя из "вести".</span><span class="sxs-lookup"><span data-stu-id="c64db-118">If this setting is turned off and a dial-in user joins the meeting first and is placed in the lobby, an organization user must join the meeting with a Teams client to admit the user from the lobby.</span></span> <span data-ttu-id="c64db-119">Для пользователей с набраным телефонным номером не доступны средства контроля "в".</span><span class="sxs-lookup"><span data-stu-id="c64db-119">There are no lobby controls available for dialed in users.</span></span>

## <a name="automatically-admit-people"></a><span data-ttu-id="c64db-120">Автоматически допустить людей</span><span class="sxs-lookup"><span data-stu-id="c64db-120">Automatically admit people</span></span>

<span data-ttu-id="c64db-121">Это политика на каждого организатора.</span><span class="sxs-lookup"><span data-stu-id="c64db-121">This is a per-organizer policy.</span></span> <span data-ttu-id="c64db-122">Этот параметр управляет тем, будут ли пользователи присоединяться к собранию напрямую или ждать в "ожидании", пока они не будут допущены пользователем, который проходит проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="c64db-122">This setting controls whether people join a meeting directly or wait in the lobby until they are admitted by an authenticated user.</span></span> <span data-ttu-id="c64db-123">Этот параметр не применяется к пользователям с телефонным доступом.</span><span class="sxs-lookup"><span data-stu-id="c64db-123">This setting does not apply to dial-in users.</span></span>

![Снимок экрана: собрание с пользователем в "вестибюле"](media/meeting-policies-lobby.png)

 <span data-ttu-id="c64db-125">Организаторы собраний могут щелкнуть **"Параметры** собрания" в приглашении на собрание, чтобы изменить этот параметр для каждого собрания, на который они запланют.</span><span class="sxs-lookup"><span data-stu-id="c64db-125">Meeting organizers can click **Meeting Options** in the meeting invitation to change this setting for each meeting they schedule.</span></span>

> [!NOTE]
> <span data-ttu-id="c64db-126">В параметрах собрания этот параметр имеет метку "Кто может минуть "вести".</span><span class="sxs-lookup"><span data-stu-id="c64db-126">In the meeting options the setting is labeled "Who can bypass the lobby".</span></span> <span data-ttu-id="c64db-127">Если изменить параметр по умолчанию для любого пользователя, он будет применяться во всех новых собраниях, организованных этим пользователем, и во всех предыдущих собраниях, где пользователь не внося изменения в параметры собрания.</span><span class="sxs-lookup"><span data-stu-id="c64db-127">If you change the default setting for any user, it will apply to all new meetings organized by that user and any prior meetings where the user didn't modify Meeting options.</span></span>
  
|<span data-ttu-id="c64db-128">Значение параметра</span><span class="sxs-lookup"><span data-stu-id="c64db-128">Setting value</span></span>  |<span data-ttu-id="c64db-129">Поведение при подмылеве</span><span class="sxs-lookup"><span data-stu-id="c64db-129">Join behavior</span></span> |
|---------|---------|
|<span data-ttu-id="c64db-130">**Все**</span><span class="sxs-lookup"><span data-stu-id="c64db-130">**Everyone**</span></span>   |<span data-ttu-id="c64db-131">Все участники собрания присоединяются к собранию напрямую, не дожидаясь в зале ожидания.</span><span class="sxs-lookup"><span data-stu-id="c64db-131">All meeting participants join the meeting directly without waiting in the lobby.</span></span> <span data-ttu-id="c64db-132">К ним относятся пользователи, проверенные подлинности, внешние пользователи из доверенных организаций (федератов), гости и анонимные пользователи.</span><span class="sxs-lookup"><span data-stu-id="c64db-132">This includes authenticated users, external users from trusted organizations (federated), guests, and anonymous users.</span></span>     |
|<span data-ttu-id="c64db-133">**Все в организации и федератированные организации**</span><span class="sxs-lookup"><span data-stu-id="c64db-133">**Everyone in your organization and federated organizations**</span></span>     |<span data-ttu-id="c64db-134">Пользователи, проверенные на подлинности в организации, включая гостевых пользователей и пользователей из надежных организаций, могут присоединиться к собранию прямо в зале ожидания.</span><span class="sxs-lookup"><span data-stu-id="c64db-134">Authenticated users within the organization, including guest users and the users from trusted organizations, join the meeting directly without waiting in the lobby.</span></span>  <span data-ttu-id="c64db-135">Анонимные пользователи будут ждать в "ожидании".</span><span class="sxs-lookup"><span data-stu-id="c64db-135">Anonymous users wait in the lobby.</span></span>   |
|<span data-ttu-id="c64db-136">**Все в организации**</span><span class="sxs-lookup"><span data-stu-id="c64db-136">**Everyone in your organization**</span></span>    |<span data-ttu-id="c64db-137">Пользователи, которые проходит проверку подлинности в организации, в том числе гостевых, могут присоединиться к собранию прямо в зале ожидания.</span><span class="sxs-lookup"><span data-stu-id="c64db-137">Authenticated users from within the organization, including guest users, join the meeting directly without waiting in the lobby.</span></span>  <span data-ttu-id="c64db-138">Пользователи из надежных организаций и анонимные пользователи ждут в "ожидании".</span><span class="sxs-lookup"><span data-stu-id="c64db-138">Users from trusted organizations and anonymous users wait in the lobby.</span></span> <span data-ttu-id="c64db-139">Это настройка по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c64db-139">This is the default setting.</span></span>           |
|<span data-ttu-id="c64db-140">**Только организатор**</span><span class="sxs-lookup"><span data-stu-id="c64db-140">**Organizer only**</span></span>    |<span data-ttu-id="c64db-141">Только организаторы собраний могут присоединиться к собранию напрямую, не дожидаясь в зале ожидания.</span><span class="sxs-lookup"><span data-stu-id="c64db-141">Only meeting organizers can join the meeting directly without waiting in the lobby.</span></span> <span data-ttu-id="c64db-142">Все остальные пользователи, включая пользователей, пройти проверку подлинности в организации, гостевых пользователей, пользователей из надежных организаций и анонимных пользователей, должны подождать в "ожидании".</span><span class="sxs-lookup"><span data-stu-id="c64db-142">Everyone else, including authenticated users within the organization, guest users, users from trusted organizations and anonymous users must wait in the lobby.</span></span>           |

## <a name="allow-dial-in-users-to-bypass-the-lobby"></a><span data-ttu-id="c64db-143">Разрешить пользователям телефонного дозвона минуть "вести".</span><span class="sxs-lookup"><span data-stu-id="c64db-143">Allow dial-in users to bypass the lobby</span></span>

<span data-ttu-id="c64db-144">Это политика на каждого организатора.</span><span class="sxs-lookup"><span data-stu-id="c64db-144">This is a per-organizer policy.</span></span> <span data-ttu-id="c64db-145">Этот параметр управляет тем, могут ли люди, которые присоединяются к собранию по телефону, напрямую или ждать в "ожидании" независимо от настройки параметра "Автоматически допустить **людей".**</span><span class="sxs-lookup"><span data-stu-id="c64db-145">This setting controls whether people who dial in by phone join the meeting directly or wait in the lobby regardless of the **Automatically admit people** setting.</span></span> <span data-ttu-id="c64db-146">По умолчанию этот параметр отключен.</span><span class="sxs-lookup"><span data-stu-id="c64db-146">By default, this setting is turned off.</span></span> <span data-ttu-id="c64db-147">Если этот параметр отключен, пользователи, которые присоединяются к собранию с клиентом Teams, будут ждать в "ожидании", пока пользователь организации не присоединится к собранию с клиентом Teams и не допустит их.</span><span class="sxs-lookup"><span data-stu-id="c64db-147">When this setting is turned off, dial-in users will wait in the lobby until an organization user joins the meeting with a Teams client and admits them.</span></span> <span data-ttu-id="c64db-148">Если этот параметр включен, пользователи, которые присоединяются к собранию по телефонной связи, автоматически присоединяются к собранию, когда пользователь организации присоединяется к собранию.</span><span class="sxs-lookup"><span data-stu-id="c64db-148">When this setting is turned on, dial-in users will automatically join the meeting when an organization user joins the meeting.</span></span>

> [!NOTE]
> <span data-ttu-id="c64db-149">Если пользователь, присоединяясь к собранию с помощью телефонного дозвона, присоединяется к собранию до того, как пользователь организации присоединится к собранию, он будет помещиться в ""вести", пока пользователь организации не присоединится к собранию с помощью клиента Teams и не допустит его.</span><span class="sxs-lookup"><span data-stu-id="c64db-149">If a dial-in user joins a meeting before an organization user joins the meeting, they will be placed in the lobby until an organization user joins the meeting using a Teams client and admits them.</span></span> <span data-ttu-id="c64db-150">Если изменить параметр по умолчанию для любого пользователя, он будет применяться во всех новых собраниях, организованных этим пользователем, и во всех предыдущих собраниях, где пользователь не внося изменения в параметры собрания.</span><span class="sxs-lookup"><span data-stu-id="c64db-150">If you change the default setting for any user, it will apply to all new meetings organized by that user and any prior meetings where the user didn't modify Meeting options.</span></span>

## <a name="enable-live-captions"></a><span data-ttu-id="c64db-151">Включить субтитры в прямом эфире</span><span class="sxs-lookup"><span data-stu-id="c64db-151">Enable live captions</span></span>

<span data-ttu-id="c64db-152">Этот параметр настраивается как политика "на пользователя", которая применяется во время собрания.</span><span class="sxs-lookup"><span data-stu-id="c64db-152">This setting is a per-user policy and applies during a meeting.</span></span> <span data-ttu-id="c64db-153">Этот параметр управляет  возможностью включить субтитры в прямом эфире для пользователя, чтобы включить или отключить субтитры в трансляции собраний, которые посещает пользователь.</span><span class="sxs-lookup"><span data-stu-id="c64db-153">This setting controls whether the **Turn on live captions** option is available for the user to turn on and turn off live captions in meetings that the user attends.</span></span>  

![Снимок экрана: параметр "Включить живые субтитры"](media/meeting-policies-live-captions.png)

|<span data-ttu-id="c64db-155">Значение параметра</span><span class="sxs-lookup"><span data-stu-id="c64db-155">Setting value</span></span> |<span data-ttu-id="c64db-156">Поведение</span><span class="sxs-lookup"><span data-stu-id="c64db-156">Behavior</span></span>  |
|---------|---------|
|<span data-ttu-id="c64db-157">**Отключено, но пользователь может переопределять его**</span><span class="sxs-lookup"><span data-stu-id="c64db-157">**Disabled but the user can override**</span></span>     | <span data-ttu-id="c64db-158">Автоматические субтитры не включались пользователем во время собрания.</span><span class="sxs-lookup"><span data-stu-id="c64db-158">Live captions aren't automatically turned on for the user during a meeting.</span></span> <span data-ttu-id="c64db-159">Пользователь видит параметр **"Включить живые субтитры"** в меню переполнения **(...),** чтобы включить их.</span><span class="sxs-lookup"><span data-stu-id="c64db-159">The user sees the **Turn on live captions** option in the overflow (**...**) menu to turn them on.</span></span> <span data-ttu-id="c64db-160">Это настройка по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c64db-160">This is the default setting.</span></span> |
|<span data-ttu-id="c64db-161">**Отключено**</span><span class="sxs-lookup"><span data-stu-id="c64db-161">**Disabled**</span></span>     | <span data-ttu-id="c64db-162">Субтитры в прямом эфире отключены для пользователя во время собрания.</span><span class="sxs-lookup"><span data-stu-id="c64db-162">Live captions are disabled for the user during a meeting.</span></span> <span data-ttu-id="c64db-163">У пользователя нет возможности включить его.</span><span class="sxs-lookup"><span data-stu-id="c64db-163">The user doesn't have the option to turn them on.</span></span>          |

<span data-ttu-id="c64db-164"><a name="bkcontentsharing"> </a></span><span class="sxs-lookup"><span data-stu-id="c64db-164"><a name="bkcontentsharing"> </a></span></span>

## <a name="allow-chat-in-meetings"></a><span data-ttu-id="c64db-165">Разрешение чата на собраниях</span><span class="sxs-lookup"><span data-stu-id="c64db-165">Allow chat in meetings</span></span>

<span data-ttu-id="c64db-166">Этот параметр настраивается для каждого участника.</span><span class="sxs-lookup"><span data-stu-id="c64db-166">This setting is a per-participant setting.</span></span> <span data-ttu-id="c64db-167">Этот параметр управляет тем, разрешен ли чат собрания на собрании пользователя.</span><span class="sxs-lookup"><span data-stu-id="c64db-167">This setting controls whether meeting chat is allowed in the user's meeting.</span></span>

<span data-ttu-id="c64db-168"><a name="bkparticipantsandguests"> </a></span><span class="sxs-lookup"><span data-stu-id="c64db-168"><a name="bkparticipantsandguests"> </a></span></span>






## <a name="related-topics"></a><span data-ttu-id="c64db-169">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="c64db-169">Related topics</span></span>

- [<span data-ttu-id="c64db-170">Обзор PowerShell в Teams</span><span class="sxs-lookup"><span data-stu-id="c64db-170">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="c64db-171">Назначение политик пользователям в Teams</span><span class="sxs-lookup"><span data-stu-id="c64db-171">Assign policies to your users in Teams</span></span>](assign-policies.md)
- [<span data-ttu-id="c64db-172">Удаление политики собраний RestrictedAnonymousAccess Teams для пользователей</span><span class="sxs-lookup"><span data-stu-id="c64db-172">Remove the RestrictedAnonymousAccess Teams meeting policy from users</span></span>](meeting-policies-restricted-anonymous-access.md)
